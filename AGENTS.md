- add always use new git branch for changes

## Workflow Orchestration

### 1. Plan Node Default

- Enter plan mode for **any** non-trivial task (3+ steps or architectural decisions)
- If something goes sideways, **stop and re-plan immediately** — don’t keep pushing
- Use plan mode for **verification steps**, not just building
- Write detailed specs upfront to reduce ambiguity

### 2. Subagent Strategy

- Use subagents liberally to keep the main context window clean
- Offload coding, code changes, research, exploration, and parallel analysis to subagents
- For complex problems, throw more compute at it via subagents
- One task per subagent for focused execution

### 3. Self-Improvement Loop

- After **any** correction from the user: update `tasks/lessons.md` with the pattern
- Write rules for yourself that prevent the same mistake
- Ruthlessly iterate on these lessons until mistake rate drops
- Review lessons at session start for the relevant project

### 4. Verification Before Done

- Never mark a task complete without proving it works
- Diff behavior between main and your changes when relevant
- Ask yourself: “Would a staff engineer approve this?”
- Run tests, check logs, demonstrate correctness

### 5. Demand Elegance (Balanced)

- For non-trivial changes: pause and ask “is there a more elegant way?”
- If a fix feels hacky: “Knowing everything I know now, implement the elegant solution”
- Skip this for simple, obvious fixes — don’t over-engineer
- Challenge your own work before presenting it

### 6. Autonomous Bug Fixing

- When given a bug report: just fix it — don’t ask for hand-holding
- Point at logs, errors, failing tests — then resolve them
- Zero context switching required from the user
- Go fix failing CI tests without being told how

### 7. Git Hygiene

- Always write **clear, category-based** commit messages.
- Format: `<type>(<scope>): <short summary>`
- Types to use:
  * `feat`: new feature
  * `fix`: bug fix
  * `chore`: maintenance / tooling / non-product work
  * `docs`: documentation only
  * `refactor`: code restructure (no behavior change)
  * `perf`: performance improvement
  * `test`: add/update tests
  * `ci`: CI/CD changes
  * `build`: build system / dependencies
  * `style`: formatting only (no logic change)

Examples:
* `feat(fpx): add webhook signature verification`
* `fix(login): handle timeout retry correctly`
* `chore(deps): bump react to 19.0.2`
* `docs(api): update FPX callback notes`
* `refactor(settlement): extract fee calculator`
* `ci(github): run tests on pull_request`


## Task Management

1. **Plan First**: Write plan to `tasks/todo.md` with checkable items
2. **Verify Plan**: Check in before starting implementation
3. **Track Progress**: Mark items complete as you go
4. **Explain Changes**: High-level summary at each step
5. **Document Results**: Add a review section to `tasks/todo.md`
6. **Capture Lessons**: Update `tasks/lessons.md` after corrections

## Core Principles

- **Simplicity First**: Make every change as simple as possible. Minimal code impact.
- **No Laziness**: Find root causes. No temporary fixes. Senior developer standards.
- **Minimal Impact**: Touch only what’s necessary. Avoid introducing bugs.
