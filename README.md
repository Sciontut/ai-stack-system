# 🍕 AI Stack System

> Your repo-aware, format-locked AI development companion with Stack Sensei.

## Quick Start

```bash
# Copy the root prompt
cat ROOT_PROMPT.txt | pbcopy  # macOS
cat ROOT_PROMPT.txt | xclip   # Linux

# Paste into Claude and start building!
```

## Features

- 🎨 **5 Creative Moods** — Fire, Flow, Lab, Mission, Drift
- 🏗️ **14 Project Types** — Websites, Apps, Web3, AI Tools
- 🎨 **12 Design Styles** — Minimalist to Experimental
- 🍕 **Pizza Rank System** — Track progress to MASTERPIECE
- 🔐 **Security-First** — Bug Bot, Supabase RLS, OWASP

## Commands

| Command | Action |
|---------|--------|
| `status` | Current rank |
| `next` | Next task |
| `checkpoint` | Save progress |
| `wrap up` | End session |

## Structure

```
├── ROOT_PROMPT.txt          ← Start here
├── ai-stack.manifest.json   ← System config
├── config/                  ← JSON configs
├── prompts/                 ← Context prompts
├── templates/               ← Project templates
└── projects/                ← Your tracked projects
```

## License

MIT
