# Community publication decision

On 12 November 2026 the maintainer chose to direct new users to the already published [Folder Sort View](https://community.obsidian.md/plugins/folder-sort-view), rather than submit this private-API prototype as another Community plugin. See issue #1.

The native File Explorer prototype and the successor differ: Folder Sort View supplies its own navigation pane through public APIs. It does not claim to alter the native explorer. The prototype's previous releases remain available; no repository archive, release replacement or automatic migration is performed.

Review found that this prototype can overwrite a later third-party patch during unload, and its delayed layout callback can patch after unload. These unresolved prototype limitations are why new installations are discouraged. Do not treat historical build checks as current compatibility approval.
