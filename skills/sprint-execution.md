# Skill: sprint-execution

**Invoke when:** Starting any work session within an active sprint.
**Owned files:** SPRINT.md (notes and outcome fields only — no structural changes)

---

## Instructions

You are running the sprint-execution skill. Follow these steps in order.

### Step 1 — Load Governance and Sprint State

Read the following files before doing anything else:
- `PROJECTS/PROJECT_GOVERNANCE/GOVERNANCE.md` — governing rules for this session
- `MEMORY.md` (project folder) — settled decisions; do not re-litigate anything recorded here
- `SPRINT.md` (project folder) — current sprint goal, items, and status
- Most recent `sprint-NN-log.md` if it exists — for context on what the last closed sprint produced

Also load any project-specific context files relevant to the work (e.g., brand voice, editorial rules, personas) — these are specified in the project's MEMORY.md or BACKLOG.md.

### Step 2 — Orient the User

Provide a brief readback:
- Current sprint goal
- Items and their current outcome status (blank = not yet done)
- Any items marked blocked or deferred

Ask: "Which item are we working on today?" If the user already stated this, proceed directly.

### Step 3 — Run the Work

Execute the sprint item. As you work:
- Pull relevant skills or context files as the work requires (e.g., invoke qa-checker before finalizing content deliverables)
- Stay within sprint scope — if new work surfaces that isn't in the sprint, flag it to the user and offer to add it to the backlog rather than doing it silently
- If a dependency or blocker surfaces, stop and flag it immediately rather than working around it

### Step 4 — Check Against Acceptance Criteria

When an item is complete, check it explicitly against its acceptance criteria from SPRINT.md before declaring it done.

If criteria are met: mark the item `done` in SPRINT.md and note any relevant observations in Sprint Notes.
If criteria are not met: document what's missing and discuss with the user — defer or continue, do not mark done.

### Step 5 — Update SPRINT.md

Update only the Outcome column and Sprint Notes section. Do not change the sprint goal, items list structure, or status field (those are owned by sprint-planning and sprint-closeout).

### Step 6 — End-of-Session Check

Before ending the session, confirm:
- Which items were completed this session
- Which items remain open
- Whether anything should be flagged as blocked or at risk

If all items show an outcome (done/deferred/blocked), prompt the user: "All sprint items have outcomes. Would you like to run sprint-closeout to close this sprint?"
