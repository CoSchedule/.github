# Contributing at CoSchedule

This applies to every CoSchedule repo that doesn't have its own `CONTRIBUTING.md`. People and AI agents follow the same rules.

## Before you start

- Read the repo's `AGENTS.md`. It has the commands, conventions and gotchas for that repo.
- Run `scripts/setup-dev.sh` to install dependencies the same way CI does.
- Bigger changes start from an issue with acceptance criteria. Decisions others will need to follow go in `docs/decisions/`.

## Making a change

- Branch from the default branch (`production`).
- Keep each PR to one reviewable change, roughly 400 changed lines or less, not counting lockfiles and generated files. Split or stack larger work.
- Run the repo's `check` script before opening the PR, and make sure it passes.
- For UI changes, check the change in a browser and attach a screenshot to the PR.

## Pull requests

- The PR title is a conventional commit: `type(scope): summary`, for example `fix(api): handle expired session tokens`. The title check enforces the repo's allowed scopes.
- PRs are squash-merged, so the PR title becomes the commit on the default branch.
- Fill in the PR template, including the testing, risk and AI assistance sections.

## Review

- Every PR needs one approval from someone other than the last person who pushed to it, plus a code owner.
- AI review runs on every PR and comments on bugs, edge cases and missing tests. It never approves.
- The human reviewer owns what AI can't judge: security, data handling, product behavior and architecture.
- Resolve every review conversation before merging.

## How we build with AI

- **Approved tools:** the AI coding agents the company provides. Other AI tools need approval from an engineering admin before they touch company code.
- **Never put in a prompt:** customer personal data, production data exports, secrets, API keys or credentials.
- **You own what you merge.** Every PR has a human author and a human reviewer, whether an agent wrote the code or not.
- **Verify, don't trust.** Agents run the `check` script and show its output. UI changes include a screenshot.
- **Cloud agents** are for well-specified work, meaning an issue with clear acceptance criteria. They never get production credentials, and their PRs go through the same review as everyone else's.
- **Close the loop.** When a review or incident finds a mistake an agent could repeat, add a rule to the repo's `AGENTS.md` or `REVIEW.md` in the same PR as the fix.
- **On pull requests:** comment `/ai <request>` to ask the AI assistant for help. Add the `ai-fix` label to have it try to fix failing checks.
