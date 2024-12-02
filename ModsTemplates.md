*1.* Mod that gives all the tools in the **Tools** folder
```lua
local mod = {}

mod.Name = "Tools Mod" --To choose from.

mod.Description = "Mod that adds tools." --To choose from.

mod.ImageId = "rbxasset://textures/ui/GuiImagePlaceholder.png" --To choose from.

local ToolsTable = {}

function mod.new(Player)
	Tools = script:WaitForChild("Tools")
	for i,x in pairs(Tools:GetChildren()) do
		newTool = x:Clone()
		newTool.Parent = Player.Backpack
		table.insert(ToolsTable,newTool)
	end
end

function mod.delete()
	for i = 1,table.maxn(ToolsTable) do
		ToolsTable[i]:Destroy()
	end
end

return mod

```
