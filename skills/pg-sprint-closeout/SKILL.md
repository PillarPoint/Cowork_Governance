---
name: pg-sprint-closeout
description: >
  Close a completed project sprint using the project governance framework. Verifies all items have outcomes,
  walks through user acceptance, handles deferred and blocked items, updates MEMORY.md, writes the permanent
  sprint log, and closes SPRINT.md. Invoke when the user has reviewed the sprint and is ready to close it,
  or on phrases like "close the sprint", "sprint closeout", "wrap up the sprint", "finish the sprint",
  "end of sprint", "sprint review", "let's close this sprint", "sprint is done".
---

# pg-sprint-closeout

You are running the pg-sprint-closeout skill. This is the governance gate — a sprint is not closed until this skill completes. Follow every step.

---

## Step 1 — Load Governance and Sprint State

Read the following files before doing anything else:
- `PROJECTS/PROJECT_GOVERNANCE/GOVERNANCE.md` — governing rules
- `SPRINT.md` (project folder) — current sprint with all item outcomes
- `BACKLOG.md` (project folder) — full backlog
- `MEMORY.md` (project folder) — existing settled decisions

---

## Step 2 — Verify Completion

Check that every sprint item has a documented outcome: `done`, `deferred`, or `blocked`.

If any item has no outcome, stop and flag it to the user. Do not proceed until every item has an outcome. Even if the outcome is "deferred" or "blocked," it must be documented.

---

## Step 3 — Walk Through Items with User

For each item marked `done`:
- Confirm the user accepts it as complete
- Confirm it met its acceptance criteria
- If the user does not accept an item, change its outcome to `deferred` and note the reason

Do not close the sprint with any item the user has not explicitly accepted.

---

## Step 4 — Handle Deferred and Blocked Items

**Deferred items:**
- Return to BACKLOG.md under "Ready for Sprint" or "Needs Definition" based on whether more scoping is needed
- Add a note explaining why it was deferred
- Remove from active sprint items

**Blocked items:**
- Return to BACKLOG.md with the blocker and unblock condition noted
- Flag to the user that this item needs attention before it can be re-sprinted

---

## Step 5 — Update MEMORY.md

Review the sprint for anything worth preserving as settled knowledge. Add to MEMORY.md:
- Decisions made during the sprint that affect future work
- Approaches confirmed or ruled out
- New constraints surfaced
- Update the Sprint History table with this sprint's entry (sprint number, goal, outcome summary, log filename)

Do not add execution notes or content outputs. Only decisions, facts, and constraints belong in MEMORY.md.

---

## Step 6 — Write the Sprint Log

Create `sprint-NN-log.md` in the project folder (NN = sprint number). This file is permanent and is never edited after creation.

Include:
- Sprint number, goal, start and close dates
- Full item list with outcomes and acceptance criteria check
- Items deferred or blocked with reasons
- Decisions logged to MEMORY.md this closeout
- Notes on what the next sprint should prioritize
- Confirmation that the user reviewed and accepted the sprint

---

## Step 7 — Close SPRINT.md

Update SPRINT.md:
- Fill in the Closeout Summary section (items done, deferred, blocked; decisions logged; next sprint focus)
- Set status to `closed`
- Set closed date to today

---

## Step 8 — Final Readback

Summarize:
- What was completed and accepted
- What was deferred or blocked and where it went
- What was added to MEMORY.md
- Sprint log filename written
- Suggested focus for next sprint based on BACKLOG.md priority order

Ask: "Does this closeout look accurate? Confirm to finalize."

Do not write the sprint log or set SPRINT.md status to `closed` until the user confirms.
