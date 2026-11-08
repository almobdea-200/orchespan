# agy / Antigravity CLI — Direct executor role

This file provides instructions for using `agy` **directly**. `agy` and Gemini CLI are not the same tool. Ask the session explicitly to read this file and `AGENTS.md`; do not assume either is automatically loaded.

## Do the bounded work

- Confirm the owning repository/branch and the manager's scope before editing.
- Inspect relevant source, implement the outcome, run the smallest meaningful checks, and inspect your own diff.
- Do not widen scope, discard unrelated changes, publish, deploy or access credentials without scoped approval.
- Return the result to the manager in this format:

```text
Changes and files / commit SHA:
Checks actually run and results:
Blockers / unverified claims:
Next recommended action:
```

**Do not create or edit `work/TASK_REPORT.md`.** The manager owns that required report, using your evidence and its own verification.

For consumer subscriptions, use `agy` as an official, directly operated tool. Do not assume it can be wrapped by a separate agent or application; follow the provider's current terms. For separate sessions, transfer the short handoff manually.
