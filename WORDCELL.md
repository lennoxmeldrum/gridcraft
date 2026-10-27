# WordCell patches

This fork's `wordcell` branch is [storytold/gridcraft](https://github.com/storytold/gridcraft)
`main` plus the small "host mode" changes [WordCell](https://github.com/lennoxmeldrum/wordcell)
needs to show GridCraft as one of its tabs. `main` mirrors upstream unchanged. Each change is its
own commit and is meant to be offered upstream; when upstream has it, drop it here.

| # | Change | Commit subject | Upstream PR |
|---|---|---|---|
| G1 | `Session::document_mut(uid)`: a host marks any open workbook saved | WordCell host: Session::document_mut by uid | not yet opened |
| G5 | `SheetApp::reinstall_context`: install GridCraft's fonts and theme again | WordCell host: SheetApp::reinstall_context | not yet opened |
| G4 | `SheetApp::mac_title_inset`: a host can drop the room left for the macOS window buttons | WordCell host: optional macOS title-bar inset | not yet opened |

GridCraft needs nothing else to be hosted: `Chrome` and `Services` already exist for hosts, and
`SheetApp` without `DocWindows` draws one window. The plan these come from is
`docs/implementation-plan.md` §6 in the WordCell repository.

Upstream's own workflows are disabled in this fork (Actions › each workflow › Disable): they need
storytold's secrets and shared actions. Only `sync-upstream.yml` runs: daily, it mirrors upstream
`main` and merges it into `wordcell` (or opens an issue if WordCell's patches conflict). It needs a
`WORDCELL_BOT_TOKEN` secret; see that file's header.
