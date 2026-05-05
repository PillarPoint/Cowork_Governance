---
name: pg-sprint-planning
description: >
  Plan a new project sprint using the project governance framework. Reads the project backlog, defines
  sprint goal and items with acceptance criteria, and writes the sprint plan to SPRINT.md.
  Invoke when starting a new sprint, planning what goes into a sprint, kicking off sprint planning,
  or on phrases like "start a new sprint", "plan the sprint", "sprint planning", "what goes in this sprint",
  "let's plan sprint", "kick off a sprint".
---

# pg-sprint-planning

You are running the pg-sprint-planning skill. Follow these steps in order. Do not skip steps.

---

## Step 1 — Load Governance and Project State

Read the following files before doing anything else:
- `PROJECTS/PROJECT_GOVERNANCE/GOVERNANCE.md` — governing rules for this session
- `MEMORY.md` (project folder) — settled decisions and constraints
- `BACKLOG.md` (project folder) — current backlog and item statuses

Confirm to the user: "Governance and project state loaded. Ready to plan Sprint [NN]."

---

## Step 2 — Review the Backlog Together

Present the user with:
- Items in the "Ready for Sprint" section, in priority order
- Any items in "Needs Definition" that could be scoped and promoted
- Current state of "Done" and "Deferred" sections for context

Ask: "Which items do you want to pull into this sprint? Let's also confirm the sprint goal."

---

## Step 3 — Define the Sprint

Work with the user to confirm:
1. **Sprint goal** — one sentence describing what a successful sprint produces
2. **Sprint items** — specific items pulled from the backlog, each with clear acceptance criteria
3. **Sprint number** — check for existing `sprint-NN-log.md` files in the project folder to determine the correct next number

If acceptance criteria are vague, push back and define them before finalizing. A sprint item without clear acceptance criteria cannot be closed at the end of the sprint.

---

## Step 4 — Update BACKLOG.md

Mark pulled items as `in sprint` in BACKLOG.md. Do not change any other item statuses.

---

## Step 5 — Write SPRINT.md

Overwrite SPRINT.md with the new sprint using this structure:

```
# [PROJECT NAME] — Sprint [NN]
Status: `active` | Started: [TODAY] | Closed: —

## Sprint Goal
[One sentence]

## Sprint Items
| # | Item | Acceptance Criteria | Outcome | Notes |
|---|---|---|---|---|
| 01 | ... | ... | — | — |

## Blocked Items
[empty]

## Deferred Items
[empty]

## Sprint Notes
[empty]

## Closeout Summary
[empty — filled by pg-sprint-closeout]
```

---

## Step 6 — Confirm with User

Read back:
- Sprint goal
- Each item with its acceptance criteria

Ask: "Does this sprint plan look right? Confirm to begin."

Do not finalize SPRINT.md until the user confirms.
