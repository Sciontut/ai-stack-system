# System Architecture

## Design Philosophy

This system enforces **deterministic AI outputs** by:

1. **Repo-awareness**: Output format is tied to repository type
2. **Format-locking**: One format per response, no mixing
3. **Authority hierarchy**: JSON > prompts > markdown

## Data Flow

```
User Request
     │
     ▼
┌─────────────────────┐
│ ai-stack.manifest   │  ← System truth (capabilities, rules)
└─────────────────────┘
     │
     ▼
┌─────────────────────┐
│ repo-capability-map │  ← What formats are valid?
└─────────────────────┘
     │
     ▼
┌─────────────────────┐
│ Context Prompt      │  ← /prompts/{repo_type}.txt
└─────────────────────┘
     │
     ▼
┌─────────────────────┐
│ Format-Locked Output│  ← Single format, no markdown
└─────────────────────┘
```

## Capability Layers

### Foundation Layer
Learning resources and conceptual grounding. Not directly invoked but informs system design.

### Data Layer
Preprocessing tools for structured and unstructured data:
- Tabular: Pandas, NumPy
- Text: spaCy, HuggingFace
- Vision: Roboflow

### LLM Layer
Core reasoning engines with constraints:
- Claude Sonnet (primary)
- GPT-4, Gemini Pro, Mistral (alternatives)
- Constraints: `repo_aware`, `format_locked`

### Multimodal Layer
Asset generation tools:
- Image: Midjourney, FLUX, Stable Diffusion
- Video: Runway, Kling, Sora
- Audio: ElevenLabs

### RAG Layer
Retrieval-augmented generation:
- Vector stores: Pinecone, Weaviate, Chroma, FAISS
- Orchestration: LangChain, LlamaIndex

### Agent Layer
Autonomous execution:
- Abacus AI Deep Agent for full-stack generation
- Repo execution and instant deploy capabilities

### Deployment Layer
Production tooling:
- API: FastAPI
- Containers: Docker, Kubernetes
- Serverless: Vercel, Modal
- Demos: Gradio

### Governance Layer
Safety and explainability:
- Content moderation: OpenAI Moderation API
- Fairness: IBM AI Fairness 360
- Explainability: SHAP, LIME

## Anti-Hallucination Strategy

1. **Explicit capability listing**: Only tools in manifest are valid
2. **Format constraints**: Repo type determines output language
3. **No inference**: If not defined, it doesn't exist
4. **Clarification prompts**: Ask before assuming context
