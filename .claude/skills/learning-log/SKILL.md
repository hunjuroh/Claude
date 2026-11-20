---
name: learning-log
description: Persistent log of user corrections, preferences, and patterns. Read the relevant log before starting work; write an entry when the user says "remember this", "log this", "from now on", "don't do that again", or corrects you / states a preference.
---

# Learning Log Skill

A persistent memory system that captures corrections, preferences, and patterns. AI reads this before starting work and writes to it whenever something worth remembering happens. Over time, your AI stops making the same mistakes and applies your preferences automatically.

---

## How It Works

You correct AI once. It logs the correction. Next session, it reads the log and never makes that mistake again. After a few weeks, you'll notice AI getting noticeably better at your specific work — not because the model improved, but because your learning log did.

---

## Setup

### Step 1: Create your learnings folder

Create a folder in your workspace for log files:

```
./learnings/
```

Update the storage path below to match your setup.

### Step 2: Create your first log files

Start with 2-3 topic files relevant to your work. Each file covers one domain.

**Examples (pick what fits you):**

| Your work | Suggested log files |
|-----------|-------------------|
| Web development | `frontend.md`, `backend.md`, `deployment.md` |
| Data analytics | `sql-patterns.md`, `visualization.md`, `data-modeling.md` |
| Content creation | `writing-style.md`, `seo.md`, `social-media.md` |
| Consulting | `client-[name].md`, `deliverables.md`, `communication.md` |
| Design | `visual-design.md`, `typography.md`, `brand-application.md` |
| General | `workflow.md`, `tools.md`, `preferences.md` |

You don't need many files to start. One or two is fine. Add more as patterns emerge.

### Step 3: Seed with known preferences (optional)

If you already know things AI gets wrong, add them as entries right away. This gives you a head start.

---

## Storage

**Path:** `./learnings/`

Each file follows the naming convention: `topic-name.md` (lowercase, hyphens for spaces).

---

## Log File Format

Every log file uses the same structure:

```markdown
# [Topic] — Learning Log

> Auto-maintained by AI. You can edit directly.
> Entries are newest-first.

---

### [YYYY-MM-DD] — [Short descriptive title]
**Context:** [What were we working on?]
**Learning:** [The specific, actionable thing to remember]
**Category:** [preference | process | technical | correction]

---
```

### Entry Quality Rules

- **Be specific.** Not "use clean designs" but "use 24px padding inside cards, 16px gap between cards"
- **Be actionable.** Each entry should change what AI does next time
- **Include context.** Future sessions need to know where this came from
- **One learning per entry.** Multiple learnings = multiple entries

### Categories

| Category | When to use |
|----------|------------|
| `preference` | How you like things done (style, format, approach) |
| `process` | Workflow steps, ordering, methodology |
| `technical` | Code patterns, tool configurations, formulas |
| `correction` | Something AI got wrong that should be avoided |

---

## When AI Should READ the Log

Before starting work on any topic, read the relevant log file(s). This prevents repeating past mistakes.

| Task | Read these files |
|------|-----------------|
| Any written deliverable | `[your style file]`, `[your preferences file]` |
| Technical work | `[your domain file]` |
| Client project | `[client-specific file]`, `[domain file]` |

Don't read ALL files every time — just the 1-3 most relevant to the current task.

---

## When AI Should WRITE to the Log

### Explicit triggers (the user says):
- "Remember this"
- "Log this" / "Note this"
- "From now on, always do X"
- "Don't do that again"

### Implicit triggers (AI detects):
- A correction: "No, not like that — do it this way"
- A repeated pattern: same adjustment requested 2+ times
- A preference statement: "I prefer X over Y"
- A breakthrough: a solution found after troubleshooting

### How to log

1. Acknowledge: "Got it — I'll log that."
2. Write the entry to the correct file (newest first)
3. Confirm: "Added to [filename]."

Don't ask permission every time. Just log and confirm. The user can always review and edit the files.

---

## Connected Skills

- **Brand Identity** → The learning log may capture corrections to brand application. Check brand identity skill first, log deviations here.
- **Session Memory** → Session memory captures WHAT happened. Learning log captures WHAT WAS LEARNED. If a session reveals a reusable preference, it goes in both systems.

---

## Maintenance

After 50+ entries in a single file, review it:
- Remove entries superseded by newer ones
- Merge related entries
- Move fundamental preferences to the **Brand Identity** skill (they belong there, not here)

The user can trigger this: "Clean up the learning log" or "Review learnings for [topic]."

---

## Example Entries

Here are examples of good log entries to help you understand the format:

```markdown
### 2026-03-15 — Always use CALCULATE with DATESYTD on date table
**Context:** Writing a YTD variance measure for a financial dashboard.
**Learning:** When calculating YTD values, use CALCULATE with DATESYTD on the date table's Date column, not the fact table's OrderDate. The fact table date causes double-counting when orders span periods.
**Category:** technical

---

### 2026-03-14 — Meta descriptions must be under 135 characters
**Context:** Writing SEO metadata for a blog post.
**Learning:** Meta descriptions should be 135 characters max (not the commonly cited 155-160). This ensures full display across all devices including mobile. Must include the primary keyword and a call-to-action.
**Category:** process

---

### 2026-03-12 — Never use "excited to announce" in social posts
**Context:** Drafted a LinkedIn post that started with "Excited to announce..."
**Learning:** Never use "excited to announce", "thrilled to share", or similar corporate phrases. Use direct, specific openings instead. Example: "I built X. Here's how it works." not "I'm excited to share that I built X."
**Category:** preference
```

---

## Getting Started

1. Create your `learnings/` folder
2. Create one log file for your primary work domain
3. Add 3-5 things you already know AI gets wrong about your work
4. Start working — the log grows naturally from here
