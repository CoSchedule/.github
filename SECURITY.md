# Security

## Reporting a vulnerability

Please don't open a public issue for a security problem.

- **In a public CoSchedule repository:** use **Report a vulnerability** on the repository's **Security** tab. That opens a private report that only maintainers can see.
- **Anywhere else:** contact CoSchedule support and ask for the report to go to the engineering team.

Include what you found, how to reproduce it, and what an attacker could do with it. We'll confirm receipt and keep you updated while we fix it.

## For CoSchedule engineers

- Never commit secrets, `.env` files or keys. Credentials come from CI secrets, AWS Secrets Manager or OIDC.
- If a secret is committed or leaked, rotate it right away, then tell the Infrastructure team. Removing it from git history doesn't make it safe again.
- Dependabot security updates are grouped weekly per folder and merge automatically once CI passes.
