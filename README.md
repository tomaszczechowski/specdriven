<div align="center">
  <img src=".github/assets/header.svg" alt="specdriven.sh - Spec Driven Development" width="100%"/>
</div>

<p align="center">
  <a href="https://specdriven.sh"><img src="https://img.shields.io/badge/AI%20Agent%20Engineering-active-22d3ee?style=flat-square&labelColor=0a0a0a" alt="AI Agent Engineering"/></a>
  <a href="https://github.com/tomaszczechowski/specdriven-specs/tree/main/content/specs"><img src="https://img.shields.io/github/directory-file-count/tomaszczechowski/specdriven-specs/content%2Fspecs?type=dir&label=specs&style=flat-square&color=22d3ee&labelColor=0a0a0a" alt="Specs in catalog"/></a>
  <a href="https://github.com/tomaszczechowski/specdriven-skills/tree/main/content/skills"><img src="https://img.shields.io/github/directory-file-count/tomaszczechowski/specdriven-skills/content%2Fskills?type=dir&label=skills&style=flat-square&color=fbbf24&labelColor=0a0a0a" alt="Skills in catalog"/></a>
  <a href="https://github.com/tomaszczechowski/specdriven/commits/main"><img src="https://img.shields.io/github/last-commit/tomaszczechowski/specdriven?style=flat-square&labelColor=0a0a0a" alt="Last update"/></a>
  <a href="https://www.npmjs.com/package/specdriven"><img src="https://img.shields.io/npm/v/specdriven?style=flat-square&labelColor=0a0a0a&color=22d3ee" alt="npm version"/></a>
  <a href="./LICENSE"><img src="https://img.shields.io/github/license/tomaszczechowski/specdriven?style=flat-square&labelColor=0a0a0a" alt="License"/></a>
</p>

<p align="center">
  <a href="https://github.com/tomaszczechowski/specdriven-specs"><img src="https://img.shields.io/badge/%F0%9F%93%8B_Browse_Specs-22d3ee?style=for-the-badge&logo=github&logoColor=white&labelColor=0a0a0a" alt="Browse Specs"/></a>
  <a href="https://github.com/tomaszczechowski/specdriven-skills"><img src="https://img.shields.io/badge/%E2%9A%A1_Browse_Skills-fbbf24?style=for-the-badge&logo=github&logoColor=white&labelColor=0a0a0a" alt="Browse Skills"/></a>
  <a href="https://specdriven.sh"><img src="https://img.shields.io/badge/%F0%9F%8C%90_Live_Catalog-f5f5f5?style=for-the-badge&logoColor=0a0a0a&labelColor=0a0a0a" alt="Live Catalog"/></a>
</p>

<p align="center">
  <a href="https://github.com/sponsors/tomaszczechowski"><img src="https://img.shields.io/badge/Sponsor-on%20GitHub-ea4aaa?style=for-the-badge&logo=githubsponsors&logoColor=white" alt="Sponsor"/></a>
  <a href="https://www.buymeacoffee.com/tomaszczechowski"><img src="https://img.shields.io/badge/Buy%20Me%20a%20Coffee-fbbf24?style=for-the-badge&logo=buymeacoffee&logoColor=0a0a0a" alt="Buy Me a Coffee"/></a>
</p>

---

**Production project blueprints with AI built in.** Skip the three days of stack debates. Install an opinionated tech stack, architecture, and the AI skills paired with it - all from a single CLI command.

> **Demo:** _Asciinema cast coming soon - watch this space._

## Quick Start

```bash
# Install a complete project spec
npx specdriven add spec nextjs-saas

# Or pick interactively
npx specdriven add

# Browse the catalog from the terminal
npx specdriven list spec
npx specdriven find skill testing
```

That's it. The CLI fetches the spec (or skill) from the public catalog and installs it into your agent's config directory - Claude Code, Cursor, Copilot, Codex, and 50+ others.

## What is SDD?

**Spec Driven Development (SDD)** is a methodology where AI-generated specifications drive your project from day one. Rather than bolting AI assistance onto an existing workflow, SDD treats specs as the source of truth - they describe your stack, your architecture, and the AI skills that come bundled with them.

The ecosystem revolves around two primitives:

| Primitive | What it is |
|-----------|------------|
| **Spec** | A complete project blueprint - tech stack + architecture + a bundled set of skills. Scaffold a new project from one. |
| **Skill** | An atomic, reusable AI instruction - a prompt, workflow, or technique that works across Claude, GPT, and other agents. |

Specs compose from skills. Skills work standalone. Both live in public, community-maintained catalogs.

## Ecosystem

This repo is the **docs hub** for the project. The actual code, specs, and skills live in dedicated repos:

| Repo | Purpose |
|------|---------|
| **[specdriven-specs](https://github.com/tomaszczechowski/specdriven-specs)** | Community catalog of project specs |
| **[specdriven-skills](https://github.com/tomaszczechowski/specdriven-skills)** | Community catalog of AI skills |
| **[specdriven.sh](https://specdriven.sh)** | Web catalog, browse UI, and online docs |

## CLI Reference

Install once and use anywhere:

```bash
npm install -g specdriven
# or run ad-hoc via npx specdriven <command>
```

Global helpers:

```bash
specdriven --version            # print the installed version
specdriven --help               # top-level help
specdriven <command> --help     # per-command help (e.g. specdriven add --help)
```

> **`<kind>` argument** - every command takes a `kind` of either `skill` or `spec`. When optional (e.g. `add`, `init`), omitting it triggers an interactive prompt.

### `add` - install a skill or spec

```bash
specdriven add [kind] [slug] [options]
```

```bash
specdriven add spec nextjs-saas              # install a spec
specdriven add skill code-review             # install a skill
specdriven add                               # interactive prompts
specdriven add spec nextjs-saas --global     # install into user-level config
specdriven add skill review --agent cursor   # target a specific agent
```

| Option | Description |
|--------|-------------|
| `-a, --agent <id>` | Target agent (e.g. `claude-code`, `cursor`) |
| `-g, --global` | Install into the user-level config dir |
| `-d, --dest <path>` | Override the destination root |
| `-f, --force` | Overwrite if the destination already exists |
| `-y, --yes` | Skip prompts; require all args/flags |

### `find` - search the catalog

Partial-substring search across slug, title, description, and tags. Omit the query to list everything for the given kind.

```bash
specdriven find <kind> [query]
```

```bash
specdriven find skill testing       # matches any skill mentioning "testing"
specdriven find spec next           # matches "nextjs-saas", "next-blog", etc.
specdriven find skill               # list every skill in the catalog
```

_No options - this is a read-only search command._

### `list` (alias: `ls`) - browse the catalog

Lists the catalog alphabetically, 20 entries per page. Useful when you want to scan the full library rather than search.

```bash
specdriven list <kind>
```

```bash
specdriven list spec
specdriven ls skill                 # alias form
```

_No options - output is paginated automatically._

### `init` - scaffold a new skill or spec

Creates a new skill or spec from the official template, ready to author and contribute back upstream.

```bash
specdriven init [kind] [slug] [options]
```

```bash
specdriven init skill my-new-skill
specdriven init spec my-stack --global
specdriven init                                 # interactive: pick kind + name
specdriven init skill review-bot --agent cursor # scaffold targeting cursor's layout
```

If `slug` is omitted, it defaults to `<kind>-example`.

| Option | Description |
|--------|-------------|
| `-a, --agent <id>` | Target agent (`claude-code`, `cursor`, etc.) |
| `-g, --global` | Scaffold into the user-level config dir |
| `-d, --dest <path>` | Override the destination root |
| `-f, --force` | Overwrite if the destination already exists |
| `-y, --yes` | Skip prompts; require all args/flags |

### `remove` (alias: `rm`) - uninstall

Removes a previously installed skill or spec from your agent's config directory. Asks for confirmation unless `--yes` is passed.

```bash
specdriven remove <kind> <slug> [options]
```

```bash
specdriven remove spec nextjs-saas
specdriven rm skill code-review --yes           # alias + skip confirmation
specdriven remove spec my-stack --global        # remove from user-level config
specdriven rm skill review --agent cursor       # target a specific agent's path
```

| Option | Description |
|--------|-------------|
| `-a, --agent <id>` | Target agent |
| `-g, --global` | Remove from user-level config |
| `-d, --dest <path>` | Override the destination root |
| `-y, --yes` | Skip confirmation |

## Supported Agents

specdriven works with **55 AI coding agents** out of the box. Pass `--agent <id>` to target a specific one, or let the CLI auto-detect from your project. Agent IDs align with the open `skills` ecosystem so installed content interops across tools.

### Top 5

| Agent | ID |
|-------|----|
| Claude Code | `claude-code` |
| Cursor | `cursor` |
| GitHub Copilot | `github-copilot` |
| Codex | `codex` |
| OpenClaw | `openclaw` |

<details>
<summary><b>Show all 55 supported agents</b></summary>

<br/>

| Agent | ID |
|-------|----|
| AdaL | `adal` |
| AiderDesk | `aider-desk` |
| Amp | `amp` |
| Antigravity | `antigravity` |
| Augment | `augment` |
| Cline | `cline` |
| Code Studio | `codestudio` |
| CodeArts Agent | `codearts-agent` |
| CodeBuddy | `codebuddy` |
| Codemaker | `codemaker` |
| Codex | `codex` |
| Command Code | `command-code` |
| Continue | `continue` |
| Cortex Code | `cortex` |
| Crush | `crush` |
| Cursor | `cursor` |
| Claude Code | `claude-code` |
| Deep Agents | `deepagents` |
| Devin for Terminal | `devin` |
| Dexto | `dexto` |
| Droid | `droid` |
| Firebender | `firebender` |
| ForgeCode | `forgecode` |
| Gemini CLI | `gemini-cli` |
| GitHub Copilot | `github-copilot` |
| Goose | `goose` |
| Hermes Agent | `hermes-agent` |
| IBM Bob | `bob` |
| iFlow CLI | `iflow-cli` |
| Junie | `junie` |
| Kilo Code | `kilo` |
| Kimi Code CLI | `kimi-cli` |
| Kiro CLI | `kiro-cli` |
| Kode | `kode` |
| MCPJam | `mcpjam` |
| Mistral Vibe | `mistral-vibe` |
| Mux | `mux` |
| Neovate | `neovate` |
| OpenClaw | `openclaw` |
| OpenCode | `opencode` |
| OpenHands | `openhands` |
| Pi | `pi` |
| Pochi | `pochi` |
| Qoder | `qoder` |
| Qwen Code | `qwen-code` |
| Replit | `replit` |
| Roo Code | `roo` |
| Rovo Dev | `rovodev` |
| Tabnine CLI | `tabnine-cli` |
| Trae | `trae` |
| Trae CN | `trae-cn` |
| Universal | `universal` |
| Warp | `warp` |
| Windsurf | `windsurf` |
| Zencoder | `zencoder` |

> Missing your agent? [Open an issue](https://github.com/tomaszczechowski/specdriven-cli/issues/new) on `specdriven-cli` and we'll add it.

</details>

## Contributing

This repo houses **docs and the project hub** - it doesn't accept spec or skill submissions directly. Open contributions go to the dedicated catalogs:

- 📋 **[specdriven-specs](https://github.com/tomaszczechowski/specdriven-specs)** - submit a project spec ([CONTRIBUTING](https://github.com/tomaszczechowski/specdriven-specs/blob/main/CONTRIBUTING.md))
- ⚡ **[specdriven-skills](https://github.com/tomaszczechowski/specdriven-skills)** - submit an AI skill ([CONTRIBUTING](https://github.com/tomaszczechowski/specdriven-skills/blob/main/CONTRIBUTING.md))

Each repo has its own workflow: CI validates frontmatter and content, a maintainer reviews, and on merge your contribution syncs to [specdriven.sh](https://specdriven.sh) within an hour.

For doc improvements, typo fixes, or issues with the CLI itself, open a PR or issue on this repo.

## Support

If specdriven saves you time, consider supporting development:

<p align="left">
  <a href="https://github.com/sponsors/tomaszczechowski"><img src="https://img.shields.io/badge/Sponsor-on%20GitHub-ea4aaa?style=for-the-badge&logo=githubsponsors&logoColor=white" alt="Sponsor"/></a>
  &nbsp;
  <a href="https://www.buymeacoffee.com/tomaszczechowski"><img src="https://img.shields.io/badge/Buy%20Me%20a%20Coffee-fbbf24?style=for-the-badge&logo=buymeacoffee&logoColor=0a0a0a" alt="Buy Me a Coffee"/></a>
</p>

## Status

**v0.x - actively developed.** Expect breaking changes between minor releases; pin versions for production use.

## License

[MIT](./LICENSE) - Copyright (c) 2026 Tomasz Czechowski.
