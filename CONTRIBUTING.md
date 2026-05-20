# Contributing to specdriven

Thanks for considering a contribution! This repo is the **docs hub** for the project — it covers the methodology (Spec Driven Development), how the ecosystem fits together, and routes you to the right place to contribute.

## Where to contribute

| You want to... | Submit to |
|----------------|-----------|
| Add a new **skill** | [`specdriven-skills`](https://github.com/tomaszczechowski/specdriven-skills) |
| Add a new **spec** | [`specdriven-specs`](https://github.com/tomaszczechowski/specdriven-specs) |
| Improve **website pages** | [`specdriven-website`](https://github.com/tomaszczechowski/specdriven-website) |
| Report a **CLI bug** or request a feature | [Open an issue here](https://github.com/tomaszczechowski/specdriven/issues) — the CLI source is in a private repo |
| Fix a typo in **this README / hub docs** | This repo |

## Catalog submissions (skills & specs)

Each catalog has its own contributor guide:

- 📋 **[specdriven-specs/CONTRIBUTING.md](https://github.com/tomaszczechowski/specdriven-specs/blob/main/CONTRIBUTING.md)**
- ⚡ **[specdriven-skills/CONTRIBUTING.md](https://github.com/tomaszczechowski/specdriven-skills/blob/main/CONTRIBUTING.md)**

The basics, regardless of which catalog:

1. Scaffold from the template — `npx specdriven init skill my-skill` or `npx specdriven init spec my-stack`
2. Edit the body (`SKILL.md` / `SPEC.md`) and metadata (`specdriven-metadata.json`)
3. Run `npm run validate` to check the frontmatter and content
4. Open a PR — CI re-runs the validator and a maintainer reviews within 48 hours

## Hosting modes — internal vs external

When submitting a skill or spec, you choose between two hosting modes:

- **Internal** — full content lives in the catalog repo. Best for atomic, community-curated contributions.
- **External** — metadata-only entry in the catalog with a `source` field pointing to your own GitHub repo. Best when you maintain a larger project elsewhere.

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
