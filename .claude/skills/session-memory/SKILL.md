---
name: session-memory
description: Chronological record of work sessions (decisions, files changed, open threads) so new conversations pick up where the last left off. Read recent session files at session start; write one when the user says "wrap up", "save memory", "end session", or asks "what did we work on last time" / "catch me up".
---

# Session Memory Skill

A running record of every work session so that new conversations can pick up where previous ones left off. This solves the core problem of context loss between sessions — no more re-explaining what you were working on yesterday.

---

## How It's Different from the Learning Log

Think of it this way:

- **Learning Log** = "How I like things done" (preferences, patterns, corrections). Timeless knowledge.
- **Session Memory** = "What happened on March 15th" (topics, decisions, files, open threads). Chronological history.

Both are essential. The learning log prevents repeated mistakes. Session memory prevents repeated conversations.

---

## Setup

### Step 1: Create your memory folder

Create a folder in your workspace:

```
./session-memory/
```

Update the storage path below to match your setup.

### Step 2: That's it

Session memory files are created automatically during work sessions. No templates to fill in. Just start working and the system captures what matters.

---

## Storage

**Path:** `./session-memory/`

Each session gets one file named: `YYYY-MM-DD-[brief-topic].md`

If there are multiple sessions on the same day, append a counter: `2026-03-15-project-alpha.md`, `2026-03-15-marketing-plan.md`

---

## File Format

```markdown
# Session: [Date] — [Brief Topic]

**Date:** YYYY-MM-DD
**Duration:** ~[estimate]
**Primary focus:** [1-2 sentence summary]

## Key Decisions
- [Decision made, with brief reasoning]

## Topics Discussed
- [Topic 1]: [What was discussed, outcome]
- [Topic 2]: [What was discussed, outcome]

## Files Changed
- `path/to/file.ext` — [what changed and why]

## Open Threads
- [Thing started but not finished]
- [Question that needs follow-up]
- [Next step agreed on but not yet done]

## Context for Next Session
[2-3 sentences a future AI session needs to read to understand where things stand. Write this as if briefing a colleague picking up your work.]
```

---

## When AI Should Use This Skill

### At Session Start

Read the 2-3 most recent memory files from your session-memory folder. Don't announce this — just absorb the context silently. If there are open threads from the last session, briefly mention them: "Last time we left off with [X] — want to pick that up?"

### During the Session

After each significant piece of work, capture it in a running memory draft. Significant = any of these:
- A decision was made
- A file was created or substantially changed
- A new direction was agreed on
- An important piece of information was shared
- A task was completed or abandoned

Don't log every small tool call or file read. Focus on things that would matter to a future session.

### At Session End

When the user signals they're done ("wrap up", "save memory", "that's it", "end session"), or when the conversation is winding down:

1. Write the full session memory file
2. Include everything from the running notes plus a "Context for Next Session" summary
3. Confirm: "Session memory saved."

### When Asked for Context

If the user asks "what did we work on last time" or "catch me up", read the recent memory files and provide a concise briefing — highlights and open threads, not a dump of everything.

---

## Writing Quality

Session memory should be scannable. A future AI session will read this in seconds before starting work. Write for that reader:

- Use short bullet points, not paragraphs
- Include file paths so the reader knows where to look
- Be specific about decisions ("priced at $59" not "discussed pricing")
- **Open threads are the most important section** — this is what drives continuity
- Context for Next Session is a 2-3 sentence executive summary

---

## Connected Skills

- **Brand Identity** → Session memory may reference brand decisions. Check brand identity for current standards.
- **Learning Log** → Session memory captures WHAT happened. Learning log captures WHAT WAS LEARNED. If a session reveals a reusable preference or pattern, write to BOTH systems:
  - Decision about a project → session memory
  - Reusable preference discovered → learning log
  - Both in one session → write to both

---

## Maintenance

After 30+ files accumulate, older sessions lose relevance. Options:
- Archive old files to a subfolder
- Consolidate a month's sessions into a single `YYYY-MM-summary.md`
- Delete sessions older than 3 months (the learning log retains the important patterns)

Don't do this automatically — wait for the user to ask.

---

## Example

```markdown
# Session: 2026-03-15 — Website Redesign Planning

**Date:** 2026-03-15
**Duration:** ~60 min
**Primary focus:** Planned the homepage redesign, chose color palette, drafted hero section copy.

## Key Decisions
- Going with dark theme (navy #1E2761 base) instead of current white
- Hero headline: "From data to decisions." — tested 5 options, this won
- Mobile-first approach — design for 375px width first

## Topics Discussed
- **Color palette**: Tested 4 options. Midnight Executive palette selected (navy + ice blue + white)
- **Hero section**: Wrote 5 headline variants, narrowed to 2, picked final
- **Navigation**: Decided on sticky nav with 4 items max. No mega menu.

## Files Changed
- `design/color-palette.md` — CREATED: Full color system with usage rules
- `content/homepage-copy.md` — CREATED: Hero + 3 sections drafted

## Open Threads
- Footer design not started — do next session
- Need to source hero background image
- CTA button color undecided (accent blue vs green)

## Context for Next Session
Homepage redesign is in progress. Color palette and hero copy are done (see files above). Next steps: design the footer, source a hero image, and decide on CTA button color. The dark theme decision is final — don't revisit.
```

---

## Getting Started

1. Create your `session-memory/` folder
2. Start your next work session normally
3. At the end, ask AI to "save session memory"
4. Next session, AI reads it automatically and picks up where you left off
