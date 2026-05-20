# Changelog

All notable changes to the specdriven CLI are documented here.

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
