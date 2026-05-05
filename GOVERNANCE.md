# Project Governance — Universal Backbone
*Version 1.0 | Do not modify during a project. Changes require explicit owner review.*

---

## 1. Purpose

This file is the governing authority for all projects run under this framework. It defines how projects are structured, how sprints are run, and what rules Claude must follow. It is loaded at the start of every skill invocation and takes precedence over conversation history and any per-project file.

---

## 2. Authority Hierarchy

When instructions conflict, this is the order of precedence (highest to lowest):

1. **GOVERNANCE.md** (this file) — universal rules, never overridden by project files
2. **MEMORY.md** — settled decisions for this project, not re-litigated
3. **BACKLOG.md** — what the project contains and its current priority order
4. **SPRINT.md** — current sprint goal, items, and status
5. **Sprint logs** (`sprint-NN-log.md`) — execution evidence, read-only after closeout
6. **Conversation context** — lowest priority; never overrides any file above

**Invariant:** If conversation context contradicts any file above, the file wins. Flag the conflict to the user rather than silently resolving it.

---

## 3. Project File Structure

Every project using this framework contains exactly these files:

| File | Owned by | Modified when |
|---|---|---|
| `GOVERNANCE.md` | Framework | Never during a project |
| `MEMORY.md` | sprint-closeout skill | At sprint closeout only |
| `BACKLOG.md` | sprint-planning + sprint-closeout | At sprint planning and closeout |
| `SPRINT.md` | sprint-planning skill | Overwritten at each new sprint |
| `sprint-NN-log.md` | sprint-closeout skill | Written once at closeout, never edited |

**File ownership is strict.** Claude must not update a file outside of the skill that owns it unless the user explicitly instructs otherwise — and must flag when doing so.

---

## 4. Sprint Lifecycle

### Statuses
- `planned` — sprint defined, work not started
- `active` — sprint is in progress
- `blocked` — work has stopped; reason and unblock condition must be recorded in SPRINT.md
- `paused` — intentionally parked; reason and resume condition must be recorded
- `completed` — all items addressed, pending user review
- `closed` — user has accepted; sprint-closeout skill has run; log written

### Transition Rules
- `planned → active`: sprint-planning skill must have run; SPRINT.md must be written
- `active → completed`: all items have a documented outcome (done, deferred, or blocked with reason)
- `completed → closed`: user has explicitly accepted; sprint-closeout skill must run before status is written

**A sprint is not closed until sprint-closeout has run.** Do not mark status as `closed` in SPRINT.md or write a sprint log without the closeout skill completing.

---

## 5. Mandatory Skill Checkpoints

These skills are required at specific moments. Claude must not bypass them:

| Moment | Skill | Required action |
|---|---|---|
| Starting a new sprint | `sprint-planning` | Must run before SPRINT.md is written |
| Working within a sprint | `sprint-execution` | Must run at the start of each work session |
| Ending a sprint | `sprint-closeout` | Must run before sprint is marked closed |

If a skill was not invoked and governance requires it, flag the gap to the user before proceeding.

---

## 6. Definitions of Done

An item is **done** when:
- The deliverable exists (file, document, skill, decision, etc.)
- It has been reviewed against its acceptance criteria
- Any quality gate relevant to the item type has been applied (e.g., qa-checker for content)
- It is documented in SPRINT.md with outcome noted

An item is **deferred** (not failed) when:
- It was attempted but descoped mid-sprint with user agreement
- The reason is recorded in SPRINT.md
- It is returned to BACKLOG.md with updated context

An item is **blocked** when:
- Work cannot continue without external input or a dependency
- The blocker and unblock condition are recorded in SPRINT.md

---

## 7. Memory Rules

`MEMORY.md` holds **settled decisions and stable facts** — things that should not be re-litigated in future sessions.

**Write to MEMORY.md:**
- Decisions made that affect future sprints
- Constraints or non-negotiables confirmed by the user
- Approaches that were tried and rejected (with reason)
- Key facts about the project that aren't obvious from deliverables

**Do not write to MEMORY.md:**
- In-progress work or current sprint state (that belongs in SPRINT.md)
- Execution notes or meeting transcripts (that belongs in sprint logs)
- Anything that changes sprint to sprint

---

## 8. Governance Invariants

These rules hold at all times. They may not be overridden by user instruction during a session — if a user asks Claude to bypass one, flag it and ask for confirmation:

- **GOVERNANCE.md is instruction-only.** No execution notes, sprint outputs, or decisions go here.
- **Sprint logs are permanent.** Once written at closeout, a sprint log is never edited.
- **SPRINT.md reflects current state only.** It is overwritten at each sprint — history lives in logs.
- **MEMORY.md does not hold secrets, credentials, or personally identifiable information.**
- **A sprint cannot close without a log.** If the log doesn't exist, the sprint is not closed.
- **Deferred items return to the backlog.** Nothing is silently dropped — every item has a documented outcome.
