---
title: Home
nav_order: 1
---

# DevExplorer

Inspired by runtime explorers like Dex, I wanted to create a tool built for developers, not exploiting. While tools like Dex offered amazing features for inspecting and editing games, they were associated with exploiting, and the existing alternatives I found were either outdated or lacking in features. That's why I made DevExplorer: a powerful, optimized explorer designed for Roblox developers, running inside your live game.

**[Get the model](https://github.com/Triaal/DevExplorer---Runtime-Studio-Explorer/releases/tag/1.0.0)**

## Features

- A tree of the whole game, with the ability to view both the client and the server.
- Every player's `PlayerGui`, `Backpack` and `StarterGear` visible and ready to edit, so you can edit other players' UI directly.
- A search with powerful filters: `class:BasePart`, `tag:Enemy`, `attr:Health>50`, `prop:Anchored=false`, `in:workspace.Map`, and more.
- Keybinds to use the explorer efficiently, including undo and redo for every edit.
- A customizable UI: six themes (or make your own), and tabs you can dock and undock.
- Visual editing, for example changing a BrickColor opens the BrickColor palette.
- Choose whether your changes apply on the server or the client.
- An Output tab with the client's and the server's logs, working almost identically to Roblox Studio's.
- An (optional) command line that runs Luau, with syntax highlighting, line numbers, auto indent, autocomplete, errors as you type, snippets and more, as if it's Roblox's code editor.
- Pin any property or attribute to watch it for changes.
- A Diagnostics tab where you can see the client's and the server's FPS, memory, etc.
- (Optional) saving, so your layout, window positions, favourites, theme, etc. are remembered.
- A whole plugin API, so you can make your own tools, actions and inspector sections for the explorer.
- Proper security: nothing is allowed until you grant it, server-only instances are only visible in the folders you expose, you can protect folders from edits, and the server checks every request.
- Click an error in the Output to go to its script.
- And so, so much more.

## Credits

Made by [Triaal](https://www.roblox.com/users/400509658/profile). Free to use in any game under the MIT license.

The command line uses [Fiu](https://github.com/rce-incorporated/Fiu) by TheGreatSageEqualToHeaven and the Luau compiler built with [LuauCeption](https://github.com/RadiatedExodus/LuauCeption) by RadiatedExodus (both MIT).

### If you encounter any bugs, or have any feature requests, let me know!
