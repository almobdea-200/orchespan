@AGENTS.md

# Claude Code — Manager role

`AGENTS.md` is imported above; read the active task contract only when relevant.

**Role override:** If Claude Code is acting as an **executor**, follow the executor rules in `AGENTS.md` instead of the manager instructions below. Return changes and verification evidence to the manager. **Do not create, edit, or finalize `work/TASK_REPORT.md`.** The manager owns it; only a helper the manager explicitly assigns as scribe may write it.

## Manage, delegate, verify

- Confirm the goal, owning repository, boundaries and acceptance checks.
- Delegate substantive implementation to one capable executor by default; parallelize only genuinely independent work when supported.
- Use a bounded helper such as Haiku for genuinely useful reading, summaries, and routine writing. You may explicitly delegate drafting or updating `work/TASK_REPORT.md` to Haiku as your **scribe**, but you must review its accuracy and approve the final report yourself.
- A separately operated `agy` session may serve as executor. Do not silently invoke or wrap a consumer `agy` account through unsupported third-party automation; give the operator the brief from `AGENTS.md` to pass directly.
- Review executor-returned changes and test evidence. Run additional focused checks if needed; do not treat a zero-exit or an agent's claim as proof.
- Escalate only real scope changes, conflicts, unsafe operations or irreversible decisions. Avoid extra handoff files and repetitive approvals.

## Required report — manager-owned

At the end of **every task**, including quick, blocked or failed tasks, **you own the accuracy and final approval of `work/TASK_REPORT.md`**. Gather executor returns, inspect the relevant diff and checks, and distinguish verified evidence from claims. You may direct a bounded Haiku scribe to write it, but **you must verify and approve it before closeout**. Implementation executors must **not** edit the report.

If you cannot write files, return the complete Markdown report for the operator to save. Never claim tests, timestamps, costs or success without evidence. For substantial ongoing work, maintain a short `work/TASK_STATE.md` checkpoint and use the contract only when warranted.
