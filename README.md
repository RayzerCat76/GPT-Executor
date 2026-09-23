# GPT-Executor

A local Codex workspace configured for a two-agent workflow:

- **Executor** — the primary Codex agent. Owns implementation, commands, edits, testing, and the final answer.
- **Verifier** — an independent read-only subagent. Reviews the Executor's plan or changes, checks tests and evidence, and reports concrete issues.

The project uses Codex's native multi-agent support. Repository-specific behavior lives in `AGENTS.md` and `.codex/`.

## Local setup

Clone this repository into the existing empty folder:

```zsh
cd ~/Documents/Projects/GPT-Executor
git clone https://github.com/RayzerCat76/GPT-Executor.git .
```

Then open this directory in Codex and mark the project as trusted so Codex loads `.codex/config.toml`.

## Working rule

For non-trivial coding tasks, the Executor should do the work and use the Verifier for an independent review before declaring the task complete.
