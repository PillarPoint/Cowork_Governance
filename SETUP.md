# Project Kickoff — Setup Instructions

---

## IMPORTANT: PROJECT_GOVERNANCE Is Read-Only

The `PROJECT_GOVERNANCE/` folder is the framework itself. **Do not modify any file in this folder as part of project work.** This includes GOVERNANCE.md, SETUP.md, templates, and skill source files.

- If you are working on a project and think you need to change a governance rule, stop and discuss with the project owner first.
- Changes to the framework affect all projects — they require deliberate review, not in-sprint edits.
- Project work happens in project folders. Governance work happens in PROJECT_GOVERNANCE — and only intentionally.
- Important:  This is for non Claude Code projects only.  If building a claude Code project use the GitHub repository:  https://github.com/mjgolaszewski/bcf-governance

---

## Step 0 — Verify Required Skills Are Installed

Before setting up a project, confirm the three governance skills are installed in Cowork:

- `pg-sprint-planning`
- `pg-sprint-execution`
- `pg-sprint-closeout`

**How to verify:** Ask the user: "Can you confirm that pg-sprint-planning, pg-sprint-execution, and pg-sprint-closeout are installed in Cowork?"

If any skill is missing:
1. The `.skill` files are located at `PROJECTS/PROJECT_GOVERNANCE/skills/`
2. Instruct the user to upload the missing `.skill` file(s) via the Cowork interface
3. Do not proceed with project setup until all three skills are confirmed installed

---

## New Project Setup

Follow these steps when starting a brand new project.

### Step 1 — Create the Project Folder

Create a new folder for your project in `PROJECTS/`:

```
PROJECTS/
└── YOUR_PROJECT_NAME/
```

### Step 2 — Copy the Three Template Files

Copy these files from `PROJECT_GOVERNANCE/templates/` into your new project folder:

- `BACKLOG.md`
- `SPRINT.md`
- `MEMORY.md`

Do not rename them. The skills depend on these exact filenames.

### Step 3 — Populate the Templates

Open each file and replace all `{{PLACEHOLDER}}` values:

**BACKLOG.md**
- `{{PROJECT_NAME}}` — your project name
- `{{DATE}}` — today's date
- Project goal — one sentence describing what this project produces
- Add your initial backlog items with acceptance criteria
- Delete placeholder rows

**SPRINT.md**
- Leave as-is — `pg-sprint-planning` will populate it when you start Sprint 01

**MEMORY.md**
- `{{PROJECT_NAME}}` — your project name
- `{{DATE}}` — today's date
- Add any known constraints or facts before the first sprint
- Leave decision tables empty — these fill in over time

### Step 4 — Run Sprint Planning

Invoke `pg-sprint-planning` to define your first sprint. Done — your project is live.

---

## Migrating an Existing Project

Use this path if a project already exists with its own structure and you want to bring it under this governance framework.

### Step 1 — Verify Skills (same as above)

Confirm all three `pg-*` skills are installed before proceeding.

### Step 2 — Audit the Existing Project

Read all existing project files. Identify:
- What is the project goal?
- What work has already been completed?
- What work is in progress or planned?
- Are there existing sprint folders, trackers, or logs?
- Are there any settled decisions or confirmed constraints documented anywhere?

Do not discard existing work. Understand it first.

### Step 3 — Create the Three Governance Files

Copy templates from `PROJECT_GOVERNANCE/templates/` into the existing project folder and populate them by migrating from what already exists:

**BACKLOG.md** — Translate existing planned/in-progress work into backlog items with acceptance criteria. Items already completed go directly into the Done section. Items that were dropped or descoped go into Deferred with a reason.

**MEMORY.md** — Extract settled decisions, confirmed constraints, and stable facts from existing documents. Do not copy execution notes or in-progress work — only things that are decided and stable.

**SPRINT.md** — If there is an active sprint in progress, capture its current state here: sprint goal, active items, and any outcomes already reached. If no sprint is active, leave SPRINT.md as a blank template and run `pg-sprint-planning` to start fresh.

### Step 4 — Handle Existing Sprint Records

If the project has existing sprint folders or logs:
- Leave them in place — do not delete prior work
- Add a Sprint History entry in MEMORY.md for each completed sprint, summarizing what it produced
- The sprint numbering for new sprints should continue from where the project left off (e.g., if Sprint 3 is the last completed sprint, the next sprint is Sprint 4)

### Step 5 — Confirm the Migration with the User

Before running any sprint work, present a summary:
- What was captured in BACKLOG.md
- What was captured in MEMORY.md
- Current sprint state (active or starting fresh)
- Sprint number to use going forward

Ask: "Does this migration look accurate? Confirm to proceed."

Do not run `pg-sprint-planning` or `pg-sprint-execution` until the user confirms the migration is correct.

---

## Reference: Framework File Map

| File | Location | Purpose |
|---|---|---|
| `GOVERNANCE.md` | `PROJECT_GOVERNANCE/` | Universal rules — loaded by every skill |
| `SETUP.md` | `PROJECT_GOVERNANCE/` | This file — read once per new project or migration |
| Template files | `PROJECT_GOVERNANCE/templates/` | Blank templates to copy into project folders |
| Skill source files | `PROJECT_GOVERNANCE/skills/*/SKILL.md` | Skill definitions (source of truth) |
| Skill packages | `PROJECT_GOVERNANCE/skills/*.skill` | Upload these to Cowork to install |
| `BACKLOG.md` | Your project folder | Active backlog for this project |
| `SPRINT.md` | Your project folder | Current sprint state |
| `MEMORY.md` | Your project folder | Settled decisions and facts |
| `sprint-NN-log.md` | Your project folder | Permanent closeout log per sprint |

---

## The Three Habits

1. **Start every sprint:** invoke `pg-sprint-planning`
2. **Start every work session:** invoke `pg-sprint-execution`
3. **End every sprint:** invoke `pg-sprint-closeout` before you stop working
