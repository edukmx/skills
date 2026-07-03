# skills

Agent skills for AI coding agents, installable with the [`skills`](https://github.com/vercel-labs/skills) CLI and discoverable on [skills.sh](https://skills.sh).

[![skills.sh](https://skills.sh/b/edukmx/skills)](https://skills.sh/edukmx/skills)

## Install

```bash
# install every skill in this repo
npx skills add edukmx/skills

# list what's available
npx skills add edukmx/skills --list

# install a specific skill
npx skills add edukmx/skills --skill project-audit
```

Skills work across Cursor, Claude Code, Codex, and [many more agents](https://github.com/vercel-labs/skills#supported-agents).

## Skills

### `project-audit`

Audits a whole Go project for **SOLID**, **clean code**, **code smells**, **good practices & patterns**, **Go conventions**, and **concurrency/performance** (race conditions, concurrency misuse, latency), validating it against a chosen architecture profile.

- Invoke as `/project-audit [architecture]`.
- Supported architecture profiles: `hexagonal`, `go-library`, `cqrs`, `clean-architecture`, `layered`, `event-driven`, `microservice`.
- Orchestrator-style: forces **one dedicated sub-agent per audit category** (six read-only auditors run in parallel) and merges everything into a single report with per-category verdicts and a prioritized remediation list.
- Runs a comment-cleanup write sub-agent first (on `composer-2.5-fast`) that strips novel/narrative code comments, keeping only strictly necessary ones, respecting the target repo's comment policy.

```bash
/project-audit hexagonal
```

## License

MIT — see [LICENSE](LICENSE).
