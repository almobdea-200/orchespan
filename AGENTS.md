# Orchespan project instructions

A portable, Markdown-first guide for AI development. Adapt it to your project; never include secrets or confidential operational information.

## This project (fill in when copying)

- Main check command: (e.g., your project's test command)
- Key directories: (only what agents need to know)
- Out-of-scope files or operations: (list exclusions)

## Authority and roles

1. Human operator instructions and explicit approvals.
2. `work/SOL_CONTRACT.md` when a substantial task is active.
3. This file and the relevant role instructions.
4. Verified repository and runtime evidence.
5. Historical notes, which cannot override current evidence.

- **Operator:** defines the goal and approves consequential actions.
- **Manager:** remains accountable; assigns bounded work, checks returned evidence, and **owns and approves `work/TASK_REPORT.md` for every task** (including failed/blocked tasks).
- **Executor:** implements and tests a bounded task, returns facts and evidence to the manager. **Never create, modify or close `TASK_REPORT.md`.**
- **Manager's helper/scribe (optional, e.g. Haiku):** may draft or physically update `TASK_REPORT.md` only when explicitly assigned by the manager. The manager reviews and approves the final content. This limited reporting role does not authorize implementation executors to edit the report.
- **Optional planner/reviewer:** assists with major decisions or independent verification only when useful.

If no separate AI manager is used, the human operator acts as manager and maintains the report. If a manager has no filesystem access, it must provide the full report text for the operator to save.

## Short handoff

Manager → executor:

```text
Goal:
Repository / branch:
Scope and exclusions:
Acceptance check:
Permissions / stop conditions:
```

Executor → manager:

```text
Changes and files / commit SHA:
Checks actually run and results:
Blockers / unverified claims:
Next recommended action:
```

For a substantial task, `work/TASK_STATE.md` can carry the current shared checkpoint. It is not another instruction source; the manager maintains its status.

## Execution and closeout

- Prefer one capable executor. Use parallel workers only for independent tasks on isolated branches/worktrees and within supported provider terms. Markdown alone cannot spawn agents.
- Manager reviews the returned diff, runs or checks relevant verification, and **ensures `work/TASK_REPORT.md` is updated and approved before closing each task**. An authorized helper may write the draft; ownership stays with the manager. Label reported-but-unverified claims clearly; never invent measurements or a PASS.
- Optional `work/SOL_CONTRACT.md` defines a substantial task; `TASK_STATE.md` tracks a checkpoint; `TASK_LEDGER.md` records multi-task status. **`TASK_REPORT.md` is always required and is evidence only**, not a competing contract or status register.
- Respect provider authentication, usage limits, and third-party automation restrictions. Use direct manual handoffs when an integration is unsupported.

## Safety boundaries

- Never print, read or reveal credential stores, `.env` secrets, raw auth headers or unfiltered sensitive logs.
- Worktrees isolate Git state, **not** host filesystem, network or provider permissions.
- No force-push, irreversible data modification, live payments, publishing or real-user communication without appropriately scoped operator approval.
- Preserve unrelated changes; do not overwrite dirty branches. Distinguish implemented, tested, merged, deployed and verified.
