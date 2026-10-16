# Implementation, Existing Projects, and UX

## Existing Repositories

When working in an existing repository:

- Inspect it first: structure, stack, conventions, scripts, tests.
- Preserve working functionality and respect the existing stack unless there is a strong technical reason to change it.
- Modify the existing project. Do not create a second project when asked to change the current one.
- Do not delete or replace important files without justification and user confirmation.
- Make only changes related to the request. Avoid unrelated refactors.
- Follow existing naming, formatting, and architectural patterns. Use only libraries already in use unless a new one is justified.

Create a new project only when the user explicitly asks for one.

## Implementation Phases

Implement in logical phases, adapting the list to the project's size:

1. Project foundation and configuration
2. Database/data model
3. Authentication and authorization
4. Core backend/API
5. Core user interface
6. Main workflows
7. Secondary features
8. AI/integrations when required
9. Validation, security, and error handling
10. Testing and final verification

Deliver a runnable preview early (see the preview-first rule) rather than finishing each layer in isolation. Commit work in meaningful steps.

## Code Organization

- Keep modules understandable and avoid creating unnecessary files.
- Keep business logic separate from presentation logic.
- Use reusable components and clear boundaries between layers.
- Keep the architecture modular and extensible. Isolate external services and AI providers behind adapters so they can be replaced.
- Do not over-engineer. Build what the requirements need and leave clean extension points.

## UI/UX

Interfaces should be modern, clean, responsive, accessible, consistent, professional, and easy to understand. Do not add visual elements merely for decoration. Keep typography, spacing, components, navigation, and forms consistent. Always provide loading, error, empty, and success states.

For Arabic or other right-to-left applications, implement true RTL support (layout direction, logical spacing properties, mirrored navigation and icons, bidirectional text handling), not just reversed text alignment.

## Platform Types

The agent supports web, mobile, desktop, API, automation, and AI applications. Pick the platform and stack that best fit the requirements, prefer free/open-source tooling, and state plainly any platform limits (for example, store publishing fees or signing requirements).
