# INIT.md — Repository Initialization Guide

This file is read **only once**, when `AGENTS.md` has `INIT_STATUS: pending`. After initialization is complete, this file will never be loaded again.

Follow every step below in order.

---

## Step 1: Detect Language

Detect the user's language from their first message. If unclear, ask:

> "What language would you like this repository to use?"

All generated files, comments, and future interactions should use this language.

## Step 2: Gather Context Through Conversation

Have a natural conversation with the user to understand:

1. **Who they are** — name, current role (student / engineer / designer / freelancer / ...), location, education or career background
2. **What they're currently focused on** — main projects, job search, studies, personal goals, deadlines
3. **What pressures or challenges they face** — time constraints, career uncertainty, skill gaps, life transitions
4. **What they want this repository for** — personal development, project tracking, career planning, learning notes, or a mix
5. **Their personality and working style** — how they think, what they care about, known cognitive patterns

Do NOT ask these as a rigid questionnaire. Have a real conversation. Gather enough to populate the initial files meaningfully, but don't interrogate.

## Step 3: Create Directory Structure

Create the following:

```
(repo root)/
├── AGENTS.md              ← already exists
├── INIT.md                ← already exists
├── CONVENTIONS.md         ← generate (see Step 5)
├── current.md             ← generate (see Step 4.1)
├── me/
│   └── profile.md         ← generate (see Step 4.2)
├── journal/               ← create empty directory
├── projects/              ← create empty directory
├── references/
│   └── README.md          ← generate (see Step 4.3)
└── skills/                ← create empty directory
```

## Step 4: Generate Core Files

Generate each file in the user's chosen language. Fill in what you learned from the conversation. Leave sections empty with a guiding comment if the user didn't mention anything relevant.

Every generated file must have:
- A 2-3 sentence summary at the top (in a blockquote)
- A `Last updated: YYYY-MM-DD` date

---

### 4.1 current.md — Current Status Snapshot

This is the highest-priority file. AI reads it first in every conversation to understand "what is happening right now."

Required sections:

```markdown
# Current Status Snapshot

> **Summary**: (2-3 sentences describing overall current situation)

> **Last updated**: YYYY-MM-DD

## Current Priorities

(The 3-5 most important things right now, ranked by urgency)
(For each: what it is, why it matters, current status)

## Time Allocation

(How time is roughly distributed right now)
(Example: work 50%, personal project 30%, study 20%)

## Recent Realizations

(Important insights or judgments formed recently)
(These help AI understand the user's current thinking)

## Current Challenges

(What's blocking progress or causing stress)
(Be honest — this helps AI provide relevant support)

## Mental State

(Brief description of current emotional baseline)
(Helps AI calibrate tone and approach)
```

Guidelines:
- This file changes frequently — it should reflect the user's situation THIS WEEK, not in general
- Keep it concise. If a section grows too long, the detail probably belongs in `projects/` or `journal/`
- When updating, replace outdated info rather than appending indefinitely

---

### 4.2 me/profile.md — Personal Profile

This is the "who I am" file. Relatively stable, updated less frequently than current.md.

Required sections:

```markdown
# Personal Profile

> **Summary**: (2-3 sentences: who this person is)

> **Last updated**: YYYY-MM-DD

## Basic Info

- **Name**:
- **Current role**: (student / engineer / designer / freelancer / ...)
- **Location**:

## Education / Career Background

(Brief education history and/or career trajectory)

## Skills / Tech Stack

(Main skills — not limited to technical skills)

## Current Interests

(What they're most interested in or exploring right now)

## Personality & Cognitive Traits

(Thinking style, personality traits, known cognitive patterns)
(This helps AI understand communication style and potential blind spots)
(Examples: "tends to overthink before acting", "strong intuition for trends
but weak on follow-through", "prefers depth over breadth")

## Hobbies & Interests

(Outside of work — helps AI understand the whole person)

## Energy & Physical State

(Optional: sleep patterns, exercise habits, energy management issues)
(Include only if the user mentioned these or they're relevant)
```

Guidelines:
- Only record things the user actually shared. Don't invent or assume.
- Personality traits should be written as observations, not judgments
- This file should help a new AI session quickly understand "what kind of person am I talking to"

---

### 4.3 references/README.md — External Materials Guide

Brief file explaining what the references/ directory is for.

```markdown
# references/ — External Materials

Store external source materials here: papers, articles, web archives,
screenshots, bookmarks, etc.

## Principles

- Only external sources go here — your own thoughts belong in projects/ or journal/
- Create subdirectories by source type as needed (papers/, web/, books/, etc.)
- For each item, include: source link, save date, brief note on why it's worth keeping

## How It Differs From Other Directories

- references/ = other people's work (external input)
- projects/ = your thinking and output
- journal/ = your daily thoughts and records
```

---

## Step 5: Generate CONVENTIONS.md

This file defines repository maintenance rules. Generate it in the user's language with the following content:

```markdown
# Repository Conventions

> This file defines maintenance rules for the personal context repository.
> Goal: keep information organized, retrievable, and manageable over time.

> **Last updated**: YYYY-MM-DD

## Core Principles

1. **AGENTS.md is the AI entry point**
   Every AI conversation starts by reading AGENTS.md, which directs the AI
   to read current.md and me/profile.md first.

2. **Every file has a summary at the top**
   2-3 sentences explaining what the file contains. AI can read just the
   summary to decide whether to read the full file.

3. **One file, one topic**
   Don't mix unrelated content in the same file.

4. **Mark last-updated dates**
   Every file header includes: Last updated: YYYY-MM-DD

5. **Write during conversation, not after**
   AI loses context when sessions end. Save valuable information immediately.

6. **External materials go in references/**
   Raw external content (articles, papers, screenshots) belongs in references/,
   not mixed into project or journal files.

## File Lifecycle

### Creating files
1. Create .md file in the appropriate directory
2. Add summary + last-updated date at the top
3. If it's an important file, mention it in AGENTS.md

### Updating files
1. Edit content
2. Update the last-updated date

### Archiving old content
- When content is outdated but still valuable, move to archive/
- Archiving is not deleting — it's lowering priority

## Anti-Bloat Strategy

### Context compression
When a file exceeds 500 lines:
1. Extract core content into a new concise version
2. Move the original to archive/
3. Link to the original from the new version

### journal/ organization
- One directory per month: journal/YYYY-MM/
- One file per day: YYYY-MM-DD.md
- Record thoughts, inspirations, reading notes, emotions
- Optional monthly summary.md at month end

### projects/ organization
- One subdirectory or file per project
- Project files contain your thinking and conclusions
- External references link to references/, not embedded directly

### references/ organization
- Subdirectories by source type (papers/, web/, etc.)
- Each item should include: source link, save date, brief description

## Directory Structure

(repo root)/
├── AGENTS.md           # AI instructions (daily rules)
├── CONVENTIONS.md      # This file
├── current.md          # Current status snapshot
├── me/
│   └── profile.md      # Personal profile
├── journal/            # Daily thoughts (by month)
├── projects/           # Projects and ideas
├── references/         # External materials
└── skills/             # Optional AI workflow skills

## Additional Rules

- Prefer appending to existing files over creating new ones
- Only create new files for genuinely new topics that will accumulate
- File names should be direct, searchable, and understandable long-term
- After any directory restructuring, verify AGENTS.md still routes correctly
```

---

## Step 6: Create First Journal Entry

Create `journal/YYYY-MM/YYYY-MM-DD.md` (using today's date) with a brief record of the initialization conversation — what the user shared, what was set up, and any initial thoughts or goals that came up.

This serves as the "day zero" entry and demonstrates the journal format.

---

## Step 7: Finalize

After all files are created:

1. Update `AGENTS.md`: change `INIT_STATUS` from `pending` to `done`
2. Update `AGENTS.md`: fill in `INIT_DATE` with today's date
3. Run `git add -A && git commit` with a clear message like: "Initialize personal context repository"
4. Tell the user what was created and give a brief summary
5. Remind the user: "From now on, every conversation will start by reading your context. You can update any file at any time — just tell me what changed."
