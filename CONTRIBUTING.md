# Contributing to specdriven

Thanks for considering a contribution! This repo is the **docs hub** for the project — it covers the methodology (Spec Driven Development), how the ecosystem fits together, and routes you to the right place to contribute.

## Where to contribute

| You want to... | Submit to |
|----------------|-----------|
| Add a new **spec** (or a bundled skill inside one) | [`specdriven-specs`](https://github.com/tomaszczechowski/specdriven-specs) |
| Improve **website pages** | [`specdriven-website`](https://github.com/tomaszczechowski/specdriven-website) |
| Report a **CLI bug** or request a feature | [Open an issue here](https://github.com/tomaszczechowski/specdriven/issues) — the CLI source is in a private repo |
| Fix a typo in **this README / hub docs** | This repo |

## Spec submissions

The catalog has its own contributor guide: **[specdriven-specs/CONTRIBUTING.md](https://github.com/tomaszczechowski/specdriven-specs/blob/main/CONTRIBUTING.md)**.

The basics:

1. Scaffold from the template — `npx specdriven init my-stack`
2. Edit `SPEC.md` (the body) and `specdriven-metadata.json` (catalog metadata)
3. Optionally bundle internal skills under `skills/<name>/` or reference external ones via `skills.external` in the metadata
4. Run `npm run validate` to check the frontmatter and content
5. Open a PR — CI re-runs the validator and a maintainer reviews within 48 hours

## Hosting modes — internal vs external

A spec itself can be hosted in one of two modes:

- **Internal** — full content lives in the catalog repo. Best for atomic, community-curated contributions.
- **External** — metadata-only entry in the catalog with a `source` field pointing to your own GitHub repo. Best when you maintain a larger project elsewhere.

Skills paired with a spec follow a similar pattern:

- **Internal skills** — bundled under `skills/<name>/` inside the spec directory. Installed alongside the spec automatically.
- **External skills** — declared in `specdriven-metadata.json` under `skills.external` with a `name`, a `command` (the `npx skills add ...` invocation users run via the open [`skills` ecosystem CLI](https://www.skills.sh)), and optional `source` / `author`. The CLI prints these commands after a successful install — it never executes them itself.

See [specdriven.sh/docs#internal-vs-external](https://specdriven.sh/docs#internal-vs-external) for the full explanation.

## Bug reports

Open an [issue](https://github.com/tomaszczechowski/specdriven/issues) with:

- What you tried (command + flags)
- Expected behavior
- Actual behavior
- Your agent (e.g., Claude Code, Cursor) + OS

For security issues, please email rather than opening a public issue.

## Code of conduct

Be kind. Assume good intent. The goal is to make AI tooling more useful for everyone.

## License

By submitting, you agree your contribution is licensed under [MIT](./LICENSE) — the same license as the rest of the project. You retain copyright on the code you contribute; the license grants the project (and its users) the right to use it.
