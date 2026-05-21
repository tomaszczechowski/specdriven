# Changelog

All notable changes to the specdriven CLI are documented here.

## [2.0.0] - 2026-05-20

### Breaking changes

- The CLI is now spec-only. The `kind` argument (`skill | spec`) has been removed from every command. All commands implicitly operate on specs.
- The `add skill`, `find skill`, `list skill`, `init skill`, `remove skill` workflows are gone. Skills are now part of specs (see below).
- API URLs changed from `/api/content/<kind>/<slug>/...` to `/api/content/<slug>/...`. Users on the previous CLI will continue to work against the legacy routes until they upgrade.

### Added

- Skills are now bundled inside their parent spec. When you `add <slug>`, any internal skills under the spec's `skills/` subdirectory are installed along with it.
- External skills declared in a spec's `specdriven-metadata.json` are printed after a successful install as a list of `npx skills add ...` commands users can copy-paste — no scraping, no in-CLI subprocess, and no third-party runtime dependency. Skill installation runs through the open `skills` ecosystem CLI on demand.
- Spec install summary now reports the number of bundled internal skills and lists paired external skills with their install commands.

### Changed

- `add [slug]` — install a spec (and its bundled + pointer skills).
- `find [query]` — search the spec catalog.
- `list` — list all specs.
- `init [slug]` — scaffold a new spec.
- `remove <slug>` — remove an installed spec.

### Removed

- The `kind` argument across every command.
- `pluralKind`, `Kind`, `VALID_KINDS`, `isKind` from `lib/config.ts`.
- The standalone skills catalog browsing flow on the CLI.

## [1.0.0] - 2026-05-20

### Added

- Initial public release of the `specdriven` CLI
- `add [kind] [slug]` — install a skill or spec into your agent's config folder
- `find <kind> <query>` — search for available skills and specs
- `init` — initialise specdriven in the current project
- `list` — list installed skills and specs
- `remove [kind] [slug]` — remove an installed skill or spec
- Supports `--agent`, `--global`, `--dest`, `--force`, and `--yes` flags on `add`
- Resolves specs and skills from the specdriven.sh registry
