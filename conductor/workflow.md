# Development Workflow

## Task Execution

- Complete one task at a time
- Commit after each task with a descriptive message
- Use `conductor(<track_id>): <description>` format for commit messages

## Testing

- Target test coverage: >80%
- Run existing tests before and after changes
- Backend: `cd backend && uv run pytest`
- Write tests for new functionality

## Code Review

- Self-review diff before committing
- Check for secrets, hardcoded values, and debug artifacts

## Task Summary

- Use Git Notes for task summaries: `git notes add -m "<summary>"`
- Summaries should capture: what changed, why, and any gotchas

## User Manual Verification Protocol

At the end of each phase, perform manual verification:

1. List all tasks completed in the phase
2. Verify each task's expected behavior
3. Run the full test suite
4. Document any issues found
5. Get user approval before proceeding to next phase

## Branch Strategy

- Conductor commits locally but never pushes
- User decides when to push to remote
