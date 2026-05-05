# Skill: sprint-closeout

**Invoke when:** The user has reviewed the sprint and is ready to close it.
**Owned files:** SPRINT.md (closeout summary + status), BACKLOG.md (move done/deferred items), MEMORY.md (new decisions), sprint-NN-log.md (creates this file)

---

## Instructions

You are running the sprint-closeout skill. This is the governance gate — nothing closes without this skill completing. Follow every step.

### Step 1 — Load Governance and Sprint State

Read the following files before doing anything else:
- `PROJECTS/PROJECT_GOVERNANCE/GOVERNANCE.md` — governing rules
- `SPRINT.md` (project folder) — current sprint with all item outcomes
- `BACKLOG.md` (project folder) — full backlog
- `MEMORY.md` (project folder) — existing settled decisions

### Step 2 — Verify Completion

Check that every sprint item has a documented outcome: `done`, `deferred`, or `blocked`.

If any item has no outcome, stop and flag it to the user. Do not proceed until every item has an outcome — even if the outcome is "deferred" or "blocked."

### Step 3 — Walk Through Items with User

For each item marked `done`:
- Confirm the user accepts it as complete
- Confirm it met its acceptance criteria
- If the user does not accept an item, change its outcome to `deferred` and note the reason

Do not close the sprint with any item the user has not explicitly accepted.

### Step 4 — Handle Deferred and Blocked Items

For each `deferred` item:
- Return it to BACKLOG.md under "Ready for Sprint" or "Needs Definition" depending on whether it needs more scoping
- Add a note explaining why it was deferred
- Remove it from the active sprint

For each `blocked` item:
- Return it to BACKLOG.md with the blocker and unblock condition noted
- Flag to the user that this item needs attention before it can be re-sprinted

### Step 5 — Update MEMORY.md

Review the sprint for anything worth preserving as settled knowledge. Add to MEMORY.md:
- Any decisions made during the sprint that affect future work
- Any approaches confirmed or ruled out
- Any new constraints surfaced
- Update the Sprint History table with this sprint's entry

Do not add execution notes or content outputs — only decisions, facts, and constraints.

### Step 6 — Write the Sprint Log

Create `sprint-NN-log.md` in the project folder (where NN matches the sprint number). This file is permanent — it is never edited after creation.

Include:
- Sprint number, goal, dates
- Full item list with outcomes and acceptance criteria check
- Items deferred or blocked with reasons
- Decisions logged to MEMORY.md this closeout
- Any notes on what the next sprint should address
- User acceptance confirmation (note that user reviewed and accepted)

### Step 7 — Close SPRINT.md

Update SPRINT.md:
- Fill in the Closeout Summary section
- Set status to `closed`
- Set closed date to today

### Step 8 — Provide Final Readback

Summarize for the user:
- What was completed and accepted
- What was deferred or blocked and where it went
- What was added to MEMORY.md
- Sprint log filename written
- Suggested focus for next sprint (based on BACKLOG.md priority)

Ask: "Does this closeout look accurate? Confirm to finalize."

Do not write the sprint log or update SPRINT.md status to `closed` until the user confirms.
