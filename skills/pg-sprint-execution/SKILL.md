---
name: pg-sprint-execution
description: >
  Start a project sprint work session using the project governance framework. Loads current sprint state,
  orients to active items, runs sprint work, checks deliverables against acceptance criteria, and updates
  SPRINT.md. Invoke at the start of any sprint work session, when resuming sprint work, or on phrases like
  "run the sprint", "let's work on the sprint", "start a sprint session", "continue the sprint",
  "sprint execution", "start working", "let's do sprint work".
---

# pg-sprint-execution

You are running the pg-sprint-execution skill. Follow these steps in order.

---

## Step 1 — Load Governance and Sprint State

Read the following files before doing anything else:
- `PROJECTS/PROJECT_GOVERNANCE/GOVERNANCE.md` — governing rules; these take precedence over conversation history
- `MEMORY.md` (project folder) — settled decisions; do not re-litigate anything recorded here
- `SPRINT.md` (project folder) — current sprint goal, items, and status
- Most recent `sprint-NN-log.md` in the project folder if one exists — for context on what the last sprint produced

Also load any project-specific context files relevant to the work this sprint. These are noted in MEMORY.md or BACKLOG.md.

---

## Step 2 — Orient the User

Provide a brief readback:
- Current sprint goal
- Each item and its current outcome status (blank = not yet done, done/deferred/blocked otherwise)
- Any items currently marked blocked or deferred

Ask: "Which item are we working on today?" If the user already stated this, proceed directly.

---

## Step 3 — Run the Work

Execute the sprint item. As you work:
- Pull relevant skills or context files as the work requires
- Apply quality gates appropriate to the item type (e.g., invoke qa-checker before finalizing any content deliverable)
- Stay within sprint scope — if new work surfaces that is not in the current sprint, flag it to the user and offer to add it to the backlog rather than doing it silently
- If a blocker surfaces, stop and flag it immediately rather than working around it

---

## Step 4 — Check Against Acceptance Criteria

When an item is complete, check it explicitly against its acceptance criteria from SPRINT.md before declaring it done.

- Criteria met → mark `done` in SPRINT.md, note any observations in Sprint Notes
- Criteria not met → document what is missing, discuss with user — defer or continue, do not mark done

---

## Step 5 — Update SPRINT.md

Update only:
- The Outcome column for completed items
- The Sprint Notes section

Do not change the sprint goal, items list structure, sprint number, or status field. Those are owned by pg-sprint-planning and pg-sprint-closeout.

---

## Step 6 — End-of-Session Check

Before ending the session, confirm:
- Which items were completed this session
- Which items remain open
- Anything that should be flagged as blocked or at risk

If all items show an outcome (done/deferred/blocked), prompt: "All sprint items have outcomes. Would you like to run pg-sprint-closeout to close this sprint?"
