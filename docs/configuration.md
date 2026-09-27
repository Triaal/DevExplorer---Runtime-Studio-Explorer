---
title: Configuration
nav_order: 3
---

# Configuration

**Client** - `DevExplorer:Start({ ... })`, everything is optional

- `Permissions` - Your own function that decides who gets what, or `"Server"` to use the server's permissions. Without it, it only works in Studio
- `Keybind` - Any `Enum.KeyCode` (`F2` by default), or `false` if you want to open/close the explorer yourself with `DevExplorer:Toggle()`
- `Theme` - The theme it starts with (`"Midnight"` by default), or your own colors and fonts, e.g. `{ Name = "My Game", Accent = Color3.fromRGB(255, 170, 0) }`
- `Themes` - More themes to pick from in Settings, `{ [Name] = { Accent = ..., ... } }`
- `Size` / `Position` - Where the window opens, 820×500 in the top right by default
- `Open` - Open it right away, `false` by default
- `World` - `false` removes highlighting, picking, the free camera and teleporting
- `EditMode` - Where edits apply at first, `"Server"` (default) or `"Client"`
- `Plugins` - Plugins to load, see Plugins
- `Tools` - The tools docked on the right the first time it opens, `{ "Output", "About" }` by default
- `CommandLine` - The client command line, for games without the server half
- `Preferences` - `{ Load, Save }` to keep the layout in your own data instead

**Server** - `DevExplorer.Server:Start({ ... })`

- `Permissions` - Same as the client's, checked on every request
- `Expose` - Server-only folders to show, e.g. `{ ServerStorage }`, or a function per player. Nothing is shown by default
- `ExposePlayers` - Shows every player's `PlayerGui`, `Backpack` and `StarterGear`
- `Filter` - `function(Player, Operation, Target)`, return `false` to protect something from edits
- `OnEdit` - Called after every edit, for your own audit log
- `CommandLine` - Turns the command line on (it also needs the `Execute` permission)
- `OnCommand` - Called with every command, for your own audit log
- `Persist` - Saves layouts, `true` for a DataStore or your own `{ Load, Save }` (e.g. your ProfileService data)
