# 🧠 personal-context-repo

中文版说明 → [README.zh-CN.md](README.zh-CN.md)

A self-initializing personal context system for AI-assisted work and life.

## What This Is

You keep re-explaining yourself to AI — who you are, what you're working on, what changed since last time. `personal-context-repo` fixes that. You drop a single file (`AGENTS.md`) into any directory, start talking to your AI assistant, and it builds a structured context repository around you — in your language, based on your real situation.

After setup, the same file governs how context gets captured, routed, tagged, and maintained across every future conversation. It's not just AI memory. It tracks your projects, decisions, open questions, evolving ideas, and the trail of how your thinking changed over time.

## 🚀 Getting Started

1. Drop `AGENTS.md` into an empty directory or an existing project
2. Start a conversation with your AI assistant — it detects the repo isn't initialized, asks a few questions about you
3. AI generates the full structure in your language, populated with your real context

## 📁 What Gets Created

```text
your-repo/
├── AGENTS.md           # AI daily operating rules
├── INIT.md             # One-time initialization guide (read once, then ignored)
├── CONVENTIONS.md      # Maintenance rules (auto-generated)
├── current.md          # Current status snapshot
├── me/
│   └── profile.md      # Who you are
├── journal/            # Daily thoughts and notes
├── projects/           # Active projects and ideas
├── references/         # External materials
└── skills/             # Optional AI workflow skills
```

## 💡 See It In Action

### Origin Tagging — know who thought what

Every insight written to the repo is tagged with its source:

```markdown
The real bottleneck is not AI's capability, but human attention.
When your prompt is vague, AI compensates by flooding you with
new concepts — and you end up more confused than before.
<!-- origin: co-created | Started from "why doesn't AI make
     learning faster", discovered the issue is attention
     overload, not information scarcity -->

This suggests the product should clarify the user's question
before answering it, not add checkpoints after.
<!-- origin: self -->

Consider a scaffolding approach: instead of blocking the user
from asking AI directly, design a workflow that naturally
guides them to think first.
<!-- origin: ai-generated -->
```

Three months later, you can still tell which judgments were yours, which were AI's suggestions, and which emerged from discussion.

### Cross-Session Convergence — ideas sharpen over time

The same topic evolves across multiple conversations, and every step is recorded:

```text
Mar 15 — "Maybe the product should add cognitive checkpoints
          after AI completes a task"

Mar 22 — "Checkpoints after the fact don't work — the user is
          already passive. Better to intervene at the source:
          help clarify the question before AI answers."

Apr 03 — "This isn't just about questions. It's about helping
          people maintain their own coordinate system — taste,
          judgment, intent — when AI can generate everything."

Apr 17 — "Don't rush to define a product. First define a
          worldview: what should the human-AI relationship
          look like when AI is extremely capable?"
```

Each new session picks up where the last one left off, instead of starting from zero.

## ⚔️ Why Not Mem0, Zep, or Other Agent Memory

Mem0, Zep, Graphiti, Letta, Supermemory — they all promise automatic cross-session memory. In practice, automatic extraction produces low-quality, opaque, and often wrong context. A widely cited Mem0 production audit found **97% of auto-extracted memories were garbage** after 32 days — duplicates, prompt fragments, hallucinated preferences, noise.

The deeper problem is control. You can't see what the system remembered, can't easily fix it, can't organize it your way. The "autonomous" part becomes the hardest part to live with.

`personal-context-repo` goes the opposite direction: nothing is auto-extracted. You write what matters, in plain files you can read and edit. The trade-off is a small maintenance cost — far less than repeatedly correcting bad automatic memories, or worse, not noticing they're wrong.

## ✨ Key Features

- 🔄 **Self-initializing** — AI builds the repo for you, no manual setup
- 🌍 **Language-adaptive** — works in any language
- 👤 **Human-curated** — you control what AI knows about you
- 🏷️ **Origin tagging** — track whether ideas came from you, AI, or co-created
- 📝 **Write-through** — insights saved during conversation, not after
- 📂 **Plain Markdown + Git** — transparent, portable, version-controlled

## 🔧 Works With

Claude Code · Cursor · Codex · OpenCode · Windsurf · any assistant that reads `AGENTS.md` / `CLAUDE.md` / `.cursorrules`

## 📌 Coming Soon

A companion Agent Skill for seamless integration with Claude Code, Codex, and OpenCode ecosystems.

## License

MIT
