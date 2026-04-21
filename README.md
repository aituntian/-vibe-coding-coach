# Vibe Coding Coach

[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md)

> Upgrade from "chatting with AI and praying for code" to "directing AI to build products systematically"

---

## What is this?

A **Skill plugin** for AI coding assistants (Claude Code, Cursor, Windsurf, etc.).

When you say "I want to build X", the AI won't immediately start writing code.
Instead, it acts like an experienced technical co-founder — asks the right questions,
generates 6 specification documents, then builds step by step.

**Core value: Turn AI coding from "random walk" into "construction with blueprints".**

---

## Why do you need it?

### Without this Skill

```
You:  Build me a task management app
AI:   Sure! [generates 500 lines of code]
You:  No, I need it on mobile
AI:   Got it! [rewrites 500 lines]
You:  Actually, WeChat Mini Program
AI:   Of course! [rewrites again]
...3 days later: lots of code, no product
```

### With this Skill

```
You:  Build me a task management app
AI:   Let me ask a few things first —
      Who's it for? Mobile or desktop? Login required?
      Where does data live? Any apps you like as reference?
      [10 min interrogation]
      Great. I've generated 6 spec docs. Let's start with step 1.
...3 days later: a shippable product
```

---

## Who is it for?

### 🌱 No-code Creators
Product managers, designers, entrepreneurs with ideas but no coding background.
Vibe Coding lets you direct AI with natural language — but without structure, AI spirals out of control fast.

**This Skill gives you a director's handbook.** You don't write code. You just need to know what story you're telling.

### ⚡ Solo Builders / One-Person Companies
You're doing product, design, dev, and ops alone. Time is your scarcest resource.

**This Skill makes your AI 3-5x more efficient:**
- No more time lost to "AI guessing your intent"
- No more time lost to "fixing bugs AI introduced"
- Checkpoint every 15-20 min — pause and resume anytime

### 👨‍💻 Independent Developers / Full-Stack Engineers
You're already using AI coding tools, but noticing:
- AI "forgets" goals after long conversations
- Same bug fixed three times, still broken
- AI starts making contradictory decisions as the project grows

**This Skill gives your AI a project memory system** — CLAUDE.md + progress.txt + lessons.md.
Every new session picks up exactly where you left off.

### 🏢 AI-Native Teams
You're building with AI, but team collaboration is messy:
- Everyone has a different AI workflow
- New members don't know the "AI rules" for the project
- AI makes conflicting decisions across sessions

**This Skill gives your team a shared AI context standard.**
6 spec docs + CLAUDE.md as a shared source of truth — anyone opens a new session and immediately gets up to speed.

### 🔄 Traditional Teams Adopting AI
You want to introduce AI coding but worry about losing control.

**Start with the documents, not the code.** This Skill's document-first approach gives you guardrails before AI touches a single line.

---

## Core Features

### 1. Relentless Interrogation
Before any code is written, the AI uses structured multiple-choice + open questions to eliminate every assumption. Better to ask 10 extra questions than carry 1 wrong assumption into code.

### 2. 6 Auto-Generated Spec Documents

| Document | Purpose |
|----------|---------|
| `PRD.md` | Features, user stories, success criteria, non-goals |
| `APP_FLOW.md` | Every page, navigation paths, decision points |
| `TECH_STACK.md` | Every package pinned to exact version |
| `FRONTEND_GUIDELINES.md` | Color palette, spacing, typography, component specs |
| `BACKEND_STRUCTURE.md` | Database schema, API endpoints, auth |
| `IMPLEMENTATION_PLAN.md` | Numbered step-by-step build sequence |

### 3. Session Memory System
- `CLAUDE.md` — The AI's "project constitution", auto-loaded every session
- `progress.txt` — Current state snapshot for cross-session recovery
- `lessons.md` — Error log so AI never repeats the same mistake

### 4. Structured Debugging
Stuck? Not "keep trying" — instead: collect info → generate hypotheses → validate one by one → three-strikes rule: delete and rethink.

### 5. Skill Orchestration
At each phase, proactively calls the right specialist Skill (debugging, TDD, frontend design, parallel agents). Not one Skill that does everything — a coach that knows when to call which expert.

---

## Intellectual Lineage

This Skill synthesizes methods from world-class AI coding practitioners:

| Source | Contribution |
|--------|-------------|
| **Andrej Karpathy** | Coined "Vibe Coding": direct AI with natural language, no need to understand every line |
| **Andrew Ng** | Three-strikes rule: if a bug isn't fixed after 3 attempts, delete and rethink |
| **Harper Reed** (ex-OpenAI CTO) | Document-driven AI workflow: write specs first, then let AI execute against them |
| **Cursor/Windsurf community** | CLAUDE.md / .cursorrules as persistent AI context anchors |
| **歸藏, 宝玉, 王树义** | Systematic practice and evangelism of AI coding methodology in the Chinese community |
| **Super 黄, 老金** | Deep exploration of "meta" concepts and AI Native workflows |

> "AI is a translator — it converts intent into code. Vague intent = spaghetti code."

---

## About the Author

**雲天 (Yuntun)** — AI Product Manager, explorer and surfer of the AI era, extreme sports enthusiast.

Long-term focus on AI products, Vibe Coding, going global (出海), and GTM. Dedicated to exploring AI productivity innovation and helping individuals & teams break through with AI transformation.

This Skill is distilled from real project experience: patterns that worked, pitfalls that burned time, workflows that scale from solo to team.

📧 juging_lau@163.com

<img src="wechat-qr.png" width="200" alt="WeChat QR Code" />

---

## Installation

### Option 1: npx one-liner (recommended)

```bash
npx skills add aituntian/-vibe-coding-coach
```

### Option 2: Manual

```bash
git clone https://github.com/aituntian/-vibe-coding-coach \
  ~/.claude/skills/vibe-coding-coach
```

---

## Usage

```
# New project
"I want to build X, use vibe coding coach to get started"

# Resume context
"I'm back, let's continue the project"

# Stuck on a bug
"Can't fix this bug, help me debug"

# Feature complete
"This feature is done, let's do a checkpoint"
```

---

## File Structure

```
vibe-coding-coach/
├── SKILL.md                    # Main skill file (AI instructions)
└── references/
    ├── interrogation-guide.md  # Question bank for interrogation phase
    ├── doc-templates.md        # Templates for all 6 spec documents
    ├── session-files.md        # Session file templates & self-running mechanism
    ├── debugging.md            # Structured debugging workflow
    └── principles.md           # Core principles & common pitfalls
```

---

## How it compares

| | Without Skill | With Vibe Coding Coach |
|--|--------------|----------------------|
| Requirements | AI guesses, often wrong | Structured interrogation, zero assumptions |
| Cross-session memory | Re-explain project every time | CLAUDE.md auto-restores context |
| Bug handling | Fix same bug repeatedly | Three-strikes: delete and rethink |
| Project standards | AI decides arbitrarily | 6 docs lock every decision |
| Team collaboration | Everyone has different workflow | Shared AI context standard |
| Technical debt | Silently accumulates | Explicitly logged in lessons.md |

---

## License

MIT
