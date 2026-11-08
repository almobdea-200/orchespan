# Example: operator-led multi-model workflow

> An **optional real-world working pattern**, not a required Orchespan configuration. Model names and effort settings below reflect one operator's stated preferences; availability and supported capabilities can change. The basic Markdown kit works without any of these particular models.

## The roles

| Role | Example setup | Responsibility |
| --- | --- | --- |
| Operator + **SOL** | ChatGPT, High or Extra High thinking | Agree on the outcome, scope, key tradeoffs and verification. SOL prepares the contract and a short manager kickoff. |
| **Manager** | Claude Sonnet 5.5, Medium | Stay in one accountable session; check current `main` and the owning branch/worktree, delegate, review evidence and approve the report. |
| **Primary executor** | Direct `agy`, Gemini 3.8 Flash, Medium | Implement the scoped change, run relevant checks, and return a reviewable result. |
| **Rescue executor** | Codex Luna 6, Medium | Continue the *same task and branch* when agy reaches a real limit, fails, or lacks a necessary capability. Do not start discovery again. |
| **Manager's helper** | Claude Haiku | Perform bounded reading, summaries and routine writing. As an **authorized scribe**, Haiku may write `TASK_REPORT.md`; the manager reviews and approves it. |
| **Expert** | Claude Opus | Consult for difficult architecture, critical decisions, hard diagnosis or independent high-risk review—not every task. |

These are preferences for this example, **not model requirements or verified provider capability guarantees**. Substitute supported tools when needed. Using a subscription directly does not automatically permit unattended third-party orchestration.

## Typical sequence

1. **Plan:** The operator and SOL discuss the task, often at High or Extra High thinking effort, and settle scope and acceptance criteria.
2. **Prepare:** SOL updates `work/SOL_CONTRACT.md` with the agreed plan and gives the operator a *short* kickoff prompt. This operator likes a contract for every task; the reusable Orchespan starter makes it optional for routine work.
3. **Kick off:** The operator gives the prompt to Sonnet (manager). Sonnet checks the latest `main` and the current repository/branch **without discarding local changes**, then reads only the relevant instructions and contract.
4. **Delegate:** Sonnet prepares one substantive, end-to-end handoff; the operator passes it to a directly operated agy session when supported. It does not take over ordinary implementation commands. Additional workers are used only for independent work with proper isolation.
5. **Recover if needed:** When agy runs out of capacity or encounters a concrete failure, Sonnet routes *remaining work* to Codex with the current branch/SHA, what was completed, the exact blocker and acceptance checks. A task-specific contract may choose Codex first instead.
6. **Get help selectively:** Sonnet may assign Haiku a bounded read, summary or write. Escalate to Opus only when a consequential decision or difficult problem genuinely needs expert judgment.
7. **Verify and report:** Executors return changes, checks, results and blockers. Sonnet reviews the actual evidence and **owns `work/TASK_REPORT.md` for every outcome**, including failure. Haiku may draft or physically update it *only at Sonnet's direction*; Sonnet checks and approves the final report.

A separate chat/CLI cannot silently observe another session. For supported direct tools, use an operator-mediated short handoff when integration is unavailable or not permitted.

## Short kickoff prompt for Sonnet

```text
Fetch the latest `origin/main` and follow the active contract in `work/SOL_CONTRACT.md`.
Read AGENTS.md and CLAUDE.md; confirm the owning branch/worktree.
Do not overwrite uncommitted work.

Manage this task through verified closeout. Delegate substantive
implementation to the appropriate capable executor. Prefer a direct agy
session when supported; use Codex as a continuation/rescue when justified.
Keep handoffs short and preserve existing progress.

Collect the executor's changed files, commits, checks and blockers.
Review the evidence. Maintain and finally approve work/TASK_REPORT.md;
you may assign Haiku as the report scribe, but implementation executors
must not edit that report. Escalate material decisions or unsafe actions.
```

**Keep the kickoff short:** the contract, not a giant repeated prompt, is the durable task brief.

## The boundaries that make this work

- **No API billing required:** use only authentication and execution modes the provider supports. The Markdown files do not launch or monitor models.
- **No automatic fallback guarantee:** if the manager cannot dispatch an agent through an authorized tool, the operator passes the handoff manually.
- **No unearned PASS:** distinguish the executor's report from independently checked evidence; unavailable time, token and cost measurements remain unknown.
- **No agent sprawl:** Sonnet is the accountable manager, Haiku is an optional helper, Opus is exceptional, and the default is one capable executor.
- **No private project assumptions:** supply the owning repository's actual check commands, permissions and operational boundaries when adopting the example.
