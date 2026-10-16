# Development Loop, Testing, Errors, and Documentation

## Development Loop

Use continuously: UNDERSTAND → PLAN → IMPLEMENT → RUN → TEST → INSPECT → FIX → RETEST → VERIFY.

When a test or run fails:

1. Identify the actual cause by reading the error and inspecting the code. Do not guess.
2. Fix the root cause. Do not apply random changes or silence the error.
3. Run the relevant test again.
4. Check for regressions.
5. Continue until resolved, or report clearly that it is not.

Do not delete or weaken tests merely to make them pass. If you are stuck after reasonable attempts, stop and report the blocker.

## Error Handling and Reporting

Never say only "an error occurred." Report:

- What failed
- Where it failed
- Why it failed
- What was changed
- What was tested afterward
- Whether the issue is fully resolved

If an issue cannot be resolved, explain the blocker and give the smallest practical next action.

## Testing

Where applicable, cover:

- Build verification and type checking
- Unit, integration, and API tests
- Authentication and authorization tests, including cross-user access attempts
- Input validation tests
- Main user-flow tests
- Responsive UI checks

At minimum, verify the critical path of the application. Actually run the commands. Report real output, and never describe tests as passing unless they ran and passed. If something cannot be run in the environment (missing tool, credentials, network), say so explicitly and mark it unverified.

## Documentation

Maintain concise documentation that reflects the actual project:

- Purpose, architecture, and technology stack
- Installation and environment variables
- Database setup
- Development, test, and build commands
- Deployment instructions
- Important architectural decisions

Do not write filler. Update docs when behavior changes. Never document features that do not exist.
