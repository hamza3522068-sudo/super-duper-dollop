# Security, External Services, and AI Features

## Security (mandatory for every application)

- Enforce authorization on the server/backend. Never rely on hidden or disabled frontend controls.
- Validate and sanitize all important inputs on the server.
- Protect authentication flows, sessions, and API endpoints. Hash passwords with a vetted algorithm; never store them in plain text.
- Prevent unauthorized resource access, including IDOR. In multi-user systems, verify that one user cannot access another's data by changing an ID, URL, request body, or parameter.
- Apply least privilege to roles, database access, and service credentials.
- Do not expose private fields unnecessarily. Return only what the client needs.
- Never expose API keys or secrets to the client. Never commit secrets. Use environment variables, provide a `.env.example` with placeholders only, and keep real `.env` files out of version control.
- Log security-relevant events where appropriate, without logging secrets or sensitive personal data.
- Handle errors without leaking stack traces, queries, or internals to end users.
- Prefer well-maintained libraries over custom cryptography or auth code.

## External Services and Integrations

For every external service:

1. Verify that the service actually exists.
2. Verify its current API capabilities (check the official documentation) when possible.
3. Verify authentication requirements.
4. Verify whether the needed feature is free, and its limits.
5. Provide a fallback when practical.
6. Never hard-code fake endpoints or fabricate credentials.
7. If credentials are required, state exactly what the user must provide and where it goes (environment variable name).

If a service cannot be used, do not fake a successful result. Create a clearly labeled adapter or mock only when useful, and say plainly that it is a mock.

## AI Features

- First decide whether AI is actually necessary.
- Prefer free, open-source, or local models, then free tiers, then low-cost APIs, when they satisfy the requirements.
- Never pretend an AI integration exists if the service is unavailable or unconfigured.
- Keep AI logic behind a provider-agnostic interface so the model or provider can be replaced.
- Keep API keys server-side only.
- Treat model output as untrusted input: validate it, and never execute it blindly.
- AI must not perform destructive or sensitive actions automatically. Require appropriate authorization and explicit user confirmation.
- Be honest about AI limitations such as accuracy, cost, latency, and privacy of data sent to third-party providers.
