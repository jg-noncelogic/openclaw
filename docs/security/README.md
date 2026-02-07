# Ironclaw Security Threat Registry

This directory documents security threats identified and addressed in the Ironclaw fork.
Each threat advisory follows a structured format that captures the vulnerability, its impact,
the mitigation implemented, and how it aligns with the Ironclaw philosophy.

## The Shogun Principle

Ironclaw embeds a core belief: **an AI agent must operate honorably for the user.**

Like a shogun bound by bushido, the agent's power is constrained by duty. Every external
action — pushing code, publishing packages, sending data — requires the user's explicit
blessing. The agent does not act on the user's behalf without the user's knowledge.

This isn't just a policy. It's architecture. The threat advisories in this directory document
how Ironclaw enforces this principle at the tool level, closing gaps that prompt-level
directives alone cannot cover.

## How This Differs from Upstream

Upstream OpenClaw provides a flexible exec approval system, but it operates at the
**binary level** — allowlisting `git` allows `git push` just as easily as `git status`.
Ironclaw adds layers of enforcement:

- **Denylist**: Pre-allowlist gate for high-risk subcommands
- **Subcommand awareness**: Granular control beyond binary names
- **Audit trail**: Logged evidence of blocked and approved actions
- **Documented threat model**: Every security change tied to a specific advisory

## Advisory Format

Each advisory file follows this naming convention:

```
IRCL-NNNN-short-description.md
```

Where `IRCL` = Ironclaw, `NNNN` = sequential number.

## Index

| Advisory                                          | Severity | Status    | Title                                             |
| ------------------------------------------------- | -------- | --------- | ------------------------------------------------- |
| [IRCL-0001](./IRCL-0001-exec-allowlist-bypass.md) | High     | Mitigated | Exec allowlist bypass via subcommand              |
| [IRCL-0002](./IRCL-0002-self-modifying-agent.md)  | Critical | Mitigated | Self-modifying agent can push to its own codebase |
