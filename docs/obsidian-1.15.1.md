# Obsidian 1.15.1 assessment — 16 November 2026

Source assessed: `a73cee13cf44f41597cefc05f99af2df0b456ada`, plugin 0.2.1. This repository remains the preserved native File Explorer prototype. [Folder Sort View](https://community.obsidian.md/plugins/folder-sort-view) is the maintained replacement; this assessment does not restart prototype releases.

[Obsidian desktop 1.15.1](https://obsidian.md/changelog/2026-11-12-desktop-v1.15.1/) changes startup and File Explorer performance. This plugin patches private `getSortedFolderItems` and calls `requestSort`, so static inspection cannot establish compatibility. Its timer already uses `window.setTimeout`; the active-window timer change does not require a source edit.

Local checks passed on macOS: `npm ci --ignore-scripts`, `npm run lint`, `npm run typecheck`, and `npm test` (three sorting/support tests, production build and bundle smoke). The build SHA-256 was `d04511a519fac7347a18cc505f1d3c134c16110ce58bf4939e0ef2783308760d`. These checks exercise test doubles, not an Obsidian 1.15.1 host.

Actual startup, native sorting settings, large folders and enable/disable in the designated test vault remain unverified. No established background connection to a 1.15.1 host was available; the existing application and other users' fixtures/settings were left untouched. [Issue #3](https://github.com/viggomeesters/obsidian-folder-sort-z-to-a/issues/3) remains open. No new compatibility claim or release follows from the local checks.

Dependency triage: the locked development tree reported two moderate npm audit findings through the Obsidian SDK/Moment chain. `npm audit --omit=dev` reported none. These counts concern the build environment; they do not establish the safety of the host-provided runtime. A trial of npm's compatible automatic fix also refreshed unrelated peers, so that lockfile change was discarded. Dependency upgrades remain separate from this compatibility assessment.
