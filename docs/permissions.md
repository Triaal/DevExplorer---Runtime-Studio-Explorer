---
title: Permissions
nav_order: 4
---

# Permissions

You decide who gets what, DevExplorer only asks.

- `View` - Open DevExplorer
- `Inspect` - See values, and browse the server-only folders you expose
- `Edit` - Change properties, attributes and tags, rename, insert, duplicate, move, destroy
- `Teleport` - Teleport to things
- `Debug` - The Output and Diagnostics tabs
- `Execute` - The command line (also needs `CommandLine = true` on the server)
- `Admin` - Everything except `Execute`, which has to be given by name

```lua
-- A function
Permissions = function(Player, Permission)
	return MyRanks:IsDeveloper(Player)
end

-- Or a table, where anything missing falls back to Admin
Permissions = {
	Admin = function(Player) return Admins[Player.UserId] == true end,
	Execute = function(Player) return Player.UserId == 123456 end,
}

-- Or, on the client only: whatever the server gives this player
Permissions = "Server"
```

Permissions are checked every time they're needed, so ranks that load later just work. A function that errors denies access, and with no permissions at all DevExplorer only works in Studio. The client's checks only decide who sees the UI: everything that reaches the server is checked again there, so with `Permissions = "Server"` on the client you only set permissions up once, on the server.
