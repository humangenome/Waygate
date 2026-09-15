# Release notes

One file per release, named after its tag: `v0.1.0.md`.

The release workflow publishes the matching file verbatim as the release body and **fails if it is missing** — a release cannot go out with a body nobody wrote.

## Shape

```
## Client

### Added

- A plain bullet, written for a player.

### Fixed

- Another one.

---

Hosting: [SurvivalServers.com](https://www.survivalservers.com/services/game_servers/dimraeth/?utm_source=github&utm_medium=release_notes&utm_campaign=waygate) runs Waygate for you.
```

Rules, all enforced by `tools/ci/lint-release-notes.sh`:

- No version heading. GitHub already prints the version and date above the body.
- Top-level headings are exactly `## Server` and `## Client`. Nothing else — a launcher change is a Client change.
- Under a component: `### Added`, `### Changed`, `### Fixed`, `### Removed`, in that order, only the ones that apply.
- Plain bullets. No bold lead-ins except a literal `**Breaking:**`. No emoji, no marketing, no superlatives.
- No internal references — no host paths, addresses, ticket numbers, or panel terminology.
- Last block is a `---` rule then the hosting line above, exactly. The linter fetches that URL and fails on anything but a 200, because the wrong path and the wrong slug both 404 and both have shipped before.

A marquee release may open with one short feature headline before the component sections. Point releases skip it.

## Migration steps

If a release needs the user to do something the new build cannot do for them — re-download an installer, re-run a tool, clear a cache — that step goes in an `### Upgrade` block under the affected component, naming the exact click or command. It also goes in the README's troubleshooting section, because the person who missed it searches there and not in a superseded release page.
