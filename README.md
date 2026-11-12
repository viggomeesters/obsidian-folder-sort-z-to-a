# Folder Sort Z to A

## Use Folder Sort View

This repository preserves the older native File Explorer prototype. It is not submitted to the Community catalog. For the maintained Community plugin, install [Folder Sort View](https://community.obsidian.md/plugins/folder-sort-view).

Folder Sort View uses public APIs and displays Z-to-A navigation in its own pane. It does not change the native File Explorer. Disable **Folder Sort Z to A** before switching, then install and enable **Folder Sort View** and open its pane.

The prototype below patches private File Explorer methods. It has known lifecycle and interoperability limitations and is retained for existing release links, not recommended for new installations. No files need to be moved or converted.

Sort folders Z-to-A in Obsidian's native File Explorer without changing files or vault content.

## Features

- keeps folders grouped before files;
- sorts folder names Z-to-A;
- preserves the native file ordering behavior;
- restores native File Explorer behavior when the plugin unloads;
- does not create, rename, delete, or modify vault files.

## Development

```bash
npm install
npm run lint
npm run typecheck
npm test
npm run build
npm run sync:test-vault
npm run smoke:cdp
npm run community:check
```

`npm run sync:test-vault` copies only `main.js`, `manifest.json`, and `styles.css` to:

```text
/mnt/c/Users/viggo/github/obsidian-test-vault/.obsidian/plugins/folder-sort-z-to-a
```

The sync script refuses `Syncthing/vault` targets.

## Release

Create a GitHub release whose tag exactly matches `manifest.json.version` and attach:

- `main.js`
- `manifest.json`
- `styles.css`
