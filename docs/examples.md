# Usage Examples

## Example 1: Frontend Component Generation

**Context**: Working in a `frontend_repo`

**Prompt**:
```
Active repo: frontend_repo
Generate a wallet connect button for Bitcoin Ordinals
```

**Expected Output**: Raw TSX with Tailwind classes, no markdown wrapper.

---

## Example 2: Backend API Schema

**Context**: Working in a `backend_repo`

**Prompt**:
```
Active repo: backend_repo
Create an endpoint schema for listing Rune balances
```

**Expected Output**: JSON OpenAPI spec or Pydantic model, no explanations.

---

## Example 3: RAG Pipeline

**Context**: Working in a `rag_repo`

**Prompt**:
```
Active repo: rag_repo
Create a document chunking function for markdown files
```

**Expected Output**: Python function with type hints, no markdown.

---

## Example 4: Multi-Tool Workflow

**Using**: `full_stack_feature` workflow from `workflows.json`

**Steps**:
1. Abacus AI Deep Agent analyzes repo → outputs schema
2. Claude Sonnet takes schema → outputs TSX components
3. FLUX takes component specs → outputs visual assets

---

## Switching Contexts

To switch repo context mid-conversation:

```
Switching to: backend_repo
[Your request here]
```

The AI will now output only JSON/SQL formats.
