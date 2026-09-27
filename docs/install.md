---
title: Installation
nav_order: 2
---

# Installation

1. Put the **DevExplorer** module in `ReplicatedStorage`.
2. Require it and start it on the server and the client:

## Server
A Script in `ServerScriptService`:
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local ServerStorage = game:GetService("ServerStorage")

local Admins = { [123456] = true }
local ExecutePerms = { [123456] = true }

require(ReplicatedStorage.DevExplorer.Server):Start({
	Permissions = {
		Admin = function(Player) return Admins[Player.UserId] == true end,
		Execute = function(Player) return ExecutePerms[Player.UserId] == true end,
	},
	Expose = { ServerStorage },
	ExposePlayers = true,
	CommandLine = true,
})
```

## Client
A LocalScript in `StarterPlayerScripts`:
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")

require(ReplicatedStorage.DevExplorer):Start({
	Permissions = "Server",
})
```

To open the explorer, press **F2**.
