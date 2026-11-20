# test-audit

`test-audit` sets one value bar for tests and applies it in three modes. Authoring mode gates every new or changed test with four questions and a list of junk patterns. Audit mode looks for existing tests that re-assert source, duplicate stronger proof, couple behavior to implementation, or keep test-only production seams alive. Campaign mode, described in [CAMPAIGN.md](CAMPAIGN.md), prunes one subsystem's whole test surface.

The skill does not assume a language, test runner, or directory layout. It reads the repository's own agent instructions (`AGENTS.md`, `CLAUDE.md`, or equivalent) for test commands, formatters, and CI checks.

## Credits

Adapted from the [`test-audit`](https://github.com/openclaw/openclaw/tree/80930af448ebabc84174146b56bc106d37fab3b4/.agents/skills/test-audit) skill in [openclaw/openclaw](https://github.com/openclaw/openclaw) at commit `80930af448ebabc84174146b56bc106d37fab3b4`. Copyright (c) 2026 OpenClaw Foundation, MIT License; the full notice is in [LICENSE](LICENSE).

Changes from upstream: OpenClaw-specific tooling (Vitest scripts, `$openclaw-testing`, `$crabbox`, `$autoreview`, the `scripts/pr` flow) and directory names are replaced with project-neutral wording, and lanes run in parallel only when the user has authorized sub-agents. The Telegram examples in `CAMPAIGN.md` are kept from the upstream campaign.
