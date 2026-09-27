---
title: API
nav_order: 7
---

# API

- `DevExplorer:Start(Config?)` - Starts it on this client. Nothing is built until someone allowed opens it
- `:Open()` / `:Close()` / `:Toggle()` / `:IsOpen()` - The window
- `:Select(Instance)` - Opens it with Instance selected and revealed in the tree
- `:GetSelection()` / `.SelectionChanged` - The selected instances, and a signal when they change
- `:Find(Query)` - Shows search results, e.g. `"tag:Enemy"`
- `:Can(Permission)` - Whether the local player has a permission
- `:Notify(Text, Kind?)` - A status bar message, Kind `"Info"`, `"Success"` or `"Error"`
- `:Edit(Targets, Request, OnDone?)` - Makes an edit like the Properties panel does, on the server or client
- `:Insert(Targets, ClassName)` - Inserts a new instance into each target, like Insert Object
- `:OpenTool(Id)` - Opens a tool, e.g. `"Output"`
- `:SetTheme(Name)` / `:GetTheme()` / `.ThemeChanged` - Switch themes, list them, and a signal after switching
- `:SetKeybind(KeyCode)` - Changes the key for this player
- `:ResetLayout()` - Puts the window and tools back the way a first start has them
- `:Use(Plugin)` / `:Register...` - Plugins, see below
- `:Refresh()` - Re-renders the tree and Properties after your plugin's data changed
- `:Stop()` - Removes everything
