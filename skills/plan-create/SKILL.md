# /plan-create

Scaffold a multi-phase implementation plan for a complex task.

## Usage

```
/plan-create <plan-name>
```

Example: `/plan-create auth-system` → creates `docs/plans/auth-system/`

## Instructions

1. Parse the `<plan-name>` argument. If no name is provided, ask the user for one.

2. Create the directory structure:
   ```
   docs/plans/<plan-name>/
   ├── plan.md
   └── progress.md
   ```

3. Draft `plan.md` using the current conversation context:
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
   Fill in the phases, files involved, and acceptance criteria based on what you know from the conversation. If context is insufficient, add placeholder sections and note what needs to be filled in.

4. Initialize `progress.md` with all phases set to "Not Started":
   ```markdown
   # Progress: <Title>

   ## Current Status: Not Started

   | Phase | Status | Updated | Notes |
   |-------|--------|---------|-------|
   | 1. <Name> | Not Started | — | — |
   | 2. <Name> | Not Started | — | — |

   ## Handoff Notes
   _No sessions completed yet._
   ```

5. Present the drafted plan to the user and ask them to review before proceeding with implementation.
