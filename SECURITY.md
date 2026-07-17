# Security Policy

## Secret handling

Never commit API keys, OAuth credentials, session secrets, database passwords, private keys, production endpoints, customer prompts, or exported conversation data.

Client-side code is public to every browser user. Any credential embedded in JavaScript, HTML, mobile bundles, or public environment variables must be treated as disclosed.

Use server-side environment variables or a managed secret store. Commit only placeholder values in `.env.example` files.

## Incident response

If a credential has ever been committed:

1. Revoke or rotate it immediately.
2. Review provider usage and billing logs.
3. Remove it from the current tree and Git history.
4. Check forks, build artifacts, deployment logs, and caches.
5. Document the root cause and prevention action.

Deleting the latest file is not sufficient because Git history remains accessible.

## Reporting

Report suspected vulnerabilities privately to the repository owner. Do not publish live credentials, personal data, exploit details, or production URLs in issues.

## Required controls

- Keep model-provider keys exclusively on the server.
- Apply authentication, authorization, rate limiting, request-size limits, and audit logging.
- Do not log complete prompts or responses by default.
- Redact tokens, cookies, authorization headers, and personal data.
- Review dependency and workflow changes before merge.
