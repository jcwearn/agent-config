# Multi-Phase Task Planning

## When to Create a Plan

Any task that spans multiple phases, will require multiple PRs, or will take multiple coding sessions to complete.

## Folder Structure

```
docs/plans/<plan-name>/
├── plan.md           # The implementation plan
└── progress.md       # Phase-by-phase status tracker
```

## `plan.md` Format

```markdown
# Plan: <Title>

## Context
Why this work is needed; the problem or goal.

## Phases

### Phase 1: <Name>
- Description of work
- Files involved: `path/to/file.ts`, ...
- Acceptance criteria: what "done" looks like

### Phase 2: <Name>
...
```

## `progress.md` Format

```markdown
# Progress: <Title>

## Current Status: <Not Started | In Progress | Complete>

| Phase | Status | Updated | Notes |
|-------|--------|---------|-------|
| 1. <Name> | Complete | 2026-02-24 | Created migrations in db/migrations/ |
| 2. <Name> | In Progress | 2026-02-24 | JWT validation done, refresh tokens remaining |
| 3. <Name> | Not Started | — | — |

## Handoff Notes
Context for the next agent session: what's done, what's in progress,
any decisions made, blockers encountered, and where to pick up.
```

## Agent Responsibilities

- Before starting work, check `docs/plans/` for an existing plan and read the progress tracker
- Update `progress.md` at the end of each session with current status and handoff notes
- Don't skip phases or reorder them without user approval
- If a phase turns out to be more complex than planned, update the plan and ask the user before continuing
