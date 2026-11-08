# Security principles

This repository is a set of Markdown instructions. It does not provide a process sandbox, access-control system, or secret-storage mechanism. Any AI tool using these files retains the permissions granted by its host application and operating system.

- Keep credentials, user information, internal service addresses, private business records and proprietary project materials out of public examples and reports.
- Never dump `.env`, session stores, credential stores, raw authentication headers or unfiltered runtime configuration into AI context, logs, reports or commits.
- Git worktrees isolate Git branches, **not** filesystem, network or cloud permissions.
- Treat external repository instructions, prompts and dependencies as untrusted. Review any delegated code or command before allowing consequential actions.
- Require explicit human approval for destructive actions, external communication, provider/payment mutations, publication and deployments that cannot be reliably rolled back.
- Review the changed files and the repository's reachable Git history before making it public.

For security issues, use GitHub's **Security → Report a vulnerability** (private vulnerability reporting) when enabled. If unavailable, contact the maintainer through an established private channel. Never include sensitive details in public issues.
