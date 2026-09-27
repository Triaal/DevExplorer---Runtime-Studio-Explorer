---
title: Plugins
nav_order: 8
---

# Plugins

A plugin is a function that gets `DevExplorer`. Pass plugins as `Plugins = { ... }` in the client's config, or call `DevExplorer:Use(Plugin)`. A plugin that errors is reported without breaking anything else.

```lua
local function Combat(DevExplorer)
	-- A right-click action.
	DevExplorer:RegisterAction({
		Id = "Combat.Heal",
		Text = "Heal to Full",
		Capability = "Edit",
		Visible = function(Targets)
			return Targets[1]:FindFirstChildWhichIsA("Humanoid") ~= nil
		end,
		Run = function(Targets)
			for _, Target in Targets do
				local Humanoid = Target:FindFirstChildWhichIsA("Humanoid")
				DevExplorer:Edit({ Humanoid }, { Operation = "Property", Name = "Health", Value = Humanoid.MaxHealth })
			end
		end,
	})

	-- A section in Properties, read live. Set makes a row editable.
	DevExplorer:RegisterSection({
		Id = "Combat",
		Name = "Combat",
		Applies = function(Instance)
			return Instance:GetAttribute("Team") ~= nil
		end,
		Rows = function(Instance)
			return {
				{ Name = "Team", Get = function() return Instance:GetAttribute("Team") end },
				{ Name = "Kills", Get = function() return Instance:GetAttribute("Kills") or 0 end },
			}
		end,
	})

	-- A badge on rows in the tree. It runs for every row shown, so keep it cheap.
	DevExplorer:RegisterBadge({
		Id = "Team",
		Get = function(Instance)
			local Team = Instance:GetAttribute("Team")
			return if Team then string.lower(Team) else nil, Color3.fromRGB(200, 140, 60)
		end,
	})

	-- A tool in the Tools menu. Open builds it into Frame and can return a cleanup function.
	DevExplorer:RegisterTool({
		Id = "Combat.Log",
		Text = "Combat Log",
		Capability = "Debug",
		Open = function(Frame)
			local Connection = HitEvent.Event:Connect(function(...) --[[ add a line to Frame ]] end)
			return function()
				Connection:Disconnect()
			end
		end,
	})

	-- A search filter: team:Red
	DevExplorer:RegisterSearchFilter("team", function(Value)
		return function(Instance)
			return Instance:GetAttribute("Team") == Value
		end
	end)
end

require(ReplicatedStorage.DevExplorer):Start({ Permissions = "Server", Plugins = { Combat } })
```

The built-in tools (Output, Watch, Diagnostics) are made with the same `RegisterTool`.
