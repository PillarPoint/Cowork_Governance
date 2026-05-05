# Skill: sprint-planning

**Invoke when:** Starting a new sprint — before any sprint work begins.
**Owned files:** SPRINT.md, BACKLOG.md (status updates only)

---

## Instructions

You are running the sprint-planning skill. Follow these steps in order. Do not skip steps.

### Step 1 — Load Governance and Project State

Read the following files before doing anything else:
- `PROJECTS/PROJECT_GOVERNANCE/GOVERNANCE.md` — governing rules for this session
- `MEMORY.md` (project folder) — settled decisions and constraints
- `BACKLOG.md` (project folder) — current backlog and item statuses

Confirm to the user: "Governance and project state loaded. Ready to plan Sprint [NN]."

### Step 2 — Review the Backlog Together

Present the user with:
- Items in the "Ready for Sprint" section, in priority order
- Any items in "Needs Definition" that could be scoped and promoted
- Current state of "Done" and "Deferred" sections for context

Ask the user: "Which items do you want to pull into this sprint? Let's also confirm the sprint goal."

### Step 3 — Define the Sprint

Work with the user to confirm:
1. **Sprint goal** — one sentence describing what a successful sprint produces
2. **Sprint items** — specific items pulled from the backlog, each with clear acceptance criteria
3. **Sprint number** — increment from the last closed sprint log (check for existing `sprint-NN-log.md` files to determine the correct number)

If acceptance criteria are vague, push back and define them before finalizing. A sprint item without clear acceptance criteria cannot be closed.

### Step 4 — Update BACKLOG.md

Mark pulled items as `in sprint` in BACKLOG.md. Do not change any other item statuses.

### Step 5 — Write SPRINT.md

Overwrite SPRINT.md with the new sprint. Use the SPRINT.md template structure:
- Sprint number and goal
- Items table with acceptance criteria (Outcome column left blank — filled during/after sprint)
- Status set to `active`
- Start date set to today

### Step 6 — Confirm with User

Read back the sprint plan:
- Sprint goal
- Each item with its acceptance criteria
- Any constraints or risks noted

Ask: "Does this sprint plan look right? Confirm to begin."

Do not finalize SPRINT.md until the user confirms.
