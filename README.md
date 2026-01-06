# AI Stack System

A repo-aware, format-locked, multi-agent AI system for deterministic full-stack product creation.

## Quick Start

1. Clone this repo alongside your project repos
2. Reference `ai-stack.manifest.json` in your AI tool configuration
3. Use prompt templates from `/prompts` for context-specific generation

## File Authority

| File Type | Purpose | Authority |
|-----------|---------|-----------|
| `*.json` | System configuration | **Machine truth** |
| `*.txt` | Prompt templates | Context overrides |
| `*.md` | Documentation | Human reference |

## Directory Structure

```
ai-stack-system/
├── ai-stack.manifest.json    # Primary system truth
├── claude.system.prompt.txt  # Anti-hallucination rules
├── config/
│   ├── repo-capability-map.json   # Output formats per repo type
│   └── workflows.json             # Multi-tool pipelines
├── prompts/
│   ├── frontend.txt    # TSX/React context
│   ├── backend.txt     # API/JSON context
│   ├── rag.txt         # Python/RAG context
│   ├── infra.txt       # DevOps/YAML context
│   └── web3.txt        # Bitcoin/Ordinals context
└── docs/
    └── architecture.md  # System design reference
```

## Supported Repo Types

- **frontend_repo**: TSX, HTML, CSS outputs
- **backend_repo**: JSON, SQL outputs
- **fullstack_monorepo**: TSX, JSON, SQL outputs
- **rag_repo**: Python, JSON outputs
- **infra_repo**: YAML, Dockerfile, HCL outputs
- **web3_repo**: TypeScript, JSON, YAML outputs

## Usage with Claude Code

Point Claude to `ai-stack.manifest.json` as the first file to read. The execution rules will constrain outputs to defined formats only.

## Execution Rules

- `repo_aware`: Output format determined by active repo type
- `format_locked_outputs`: Single format per response
- `no_markdown_by_default`: Raw code unless explicitly requested
- `single_format_per_response`: No mixed outputs

## License

MIT
