# Example — A small documentation task

**Goal:** Improve the quick start in a fictional project's README, without changing application code.

**Manager → executor:** Use the short handoff in `AGENTS.md`: goal, branch, allowed files, acceptance check and stop conditions.

**Executor → manager:** Return the files changed, commit SHA (if available), checks actually run and any unverified claims. **Do not write `work/TASK_REPORT.md`.**

**Manager closeout:** Inspect the diff, check any claimed validation, and **complete `work/TASK_REPORT.md` even for this small task**. Mark anything not tested as unknown. If the manager has no filesystem access, provide the completed report text to the operator.
