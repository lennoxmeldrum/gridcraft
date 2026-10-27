# WordCell patches

This fork's `wordcell` branch is [storytold/gridcraft](https://github.com/storytold/gridcraft)
`main` plus the small "host mode" changes [WordCell](https://github.com/lennoxmeldrum/wordcell)
needs to show GridCraft as one of its tabs. `main` mirrors upstream unchanged. Each change is its
own commit and is meant to be offered upstream; when upstream has it, drop it here.

| # | Change | Commit subject | Upstream PR |
|---|---|---|---|
| G1 | `Session::document_mut(uid)`: a host marks any open workbook saved | WordCell host: Session::document_mut by uid | not yet opened |
| G5 | `SheetApp::reinstall_context`: install GridCraft's fonts and theme again | WordCell host: SheetApp::reinstall_context | not yet opened |

GridCraft needs nothing else to be hosted: `Chrome` and `Services` already exist for hosts, and
`SheetApp` without `DocWindows` draws one window. The plan these come from is
`docs/implementation-plan.md` §6 in the WordCell repository.

The upstream workflows in `.github/workflows/` don't run in this fork unless Actions is enabled in
the fork's Actions tab. Leave them off: they need storytold's secrets and shared actions.
