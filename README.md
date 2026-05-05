# Cowork Project Governance

A lightweight sprint-based project management framework for [Claude Cowork](https://claude.ai/). Provides structure for running projects through planning, execution, and closeout sprints — governed by a single authority file and three installable skills.

---

## What This Is

This framework gives Claude a consistent way to manage projects across multiple sessions. It enforces a sprint lifecycle, maintains a persistent backlog and memory, and writes permanent sprint logs at closeout. All rules live in `GOVERNANCE.md` — the skills load it at the start of every invocation.

---

## Folder Placement — Important

The skills in this framework hardcode the path to `GOVERNANCE.md` as:

```
PROJECTS/PROJECT_GOVERNANCE/GOVERNANCE.md
```

**This folder must live inside a `PROJECTS/` parent directory in your Cowork file system.** The expected structure is:

```
PROJECTS/
└── PROJECT_GOVERNANCE/     ← this repo goes here
│   ├── GOVERNANCE.md
│   ├── SETUP.md
│   ├── README.md
│   ├── templates/
│   └── skills/
└── YOUR_PROJECT_NAME/      ← your project folders go here
    ├── BACKLOG.md
    ├── SPRINT.md
    └── MEMORY.md
```

If you place `PROJECT_GOVERNANCE/` elsewhere, the skills will not be able to load `GOVERNANCE.md` and the framework will not function correctly.

---

## What's Included

| File / Folder | Purpose |
|---|---|
| `GOVERNANCE.md` | Universal rules — loaded by every skill, takes precedence over all other files |
| `SETUP.md` | Step-by-step instructions for starting a new project or migrating an existing one |
| `templates/BACKLOG.md` | Template to copy into each new project folder |
| `templates/SPRINT.md` | Template to copy into each new project folder |
| `templates/MEMORY.md` | Template to copy into each new project folder |
| `skills/pg-sprint-planning.skill` | Install in Cowork to enable sprint planning |
| `skills/pg-sprint-execution.skill` | Install in Cowork to enable sprint work sessions |
| `skills/pg-sprint-closeout.skill` | Install in Cowork to enable sprint closeout |
| `skills/*/SKILL.md` | Human-readable source for each skill |

---

## Setup

1. Place this folder at `PROJECTS/PROJECT_GOVERNANCE/` in your Cowork file system
2. Install the three `.skill` files via the Cowork interface:
   - `pg-sprint-planning`
   - `pg-sprint-execution`
   - `pg-sprint-closeout`
3. Follow `SETUP.md` to create your first project

---

## The Three Habits

Once set up, the framework runs on three commands:

1. **Start every sprint** — invoke `pg-sprint-planning`
2. **Start every work session** — invoke `pg-sprint-execution`
3. **End every sprint** — invoke `pg-sprint-closeout`

---

## Note on Claude Code Projects

This framework is designed for **non-Claude Code projects** running inside Cowork. If you're managing a Claude Code project with its own repository, a separate Claude Code-native governance framework may be more appropriate, such as the [bcf-governance](https://github.com/mjgolaszewski/bcf-governance) framework this was based on.
