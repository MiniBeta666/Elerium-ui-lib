AddLabel:
```
tab:AddLabel("Hello World!")
```

AddButton:
```
tab:AddButton("Give ...", function()
	print("Gave ... !")
end)
```

AddTextBox:
```
tab:AddTextBox("Teleport to Player", function(text)
	teleport_to(game:GetService("Players"):FindFirstChild("text") or game:GetService("Players").LocalPlayer)
end)
```

AddSwitch:
```
local switch = tab:AddSwitch("God Mode", function(bool)
	toggle_god_mode(bool)
end)
switch:Set(true)
```

AddSlider:
```
local slider = tab:AddSlider("WalkSpeed", function(p)
	setwalkspeed(p)
end, {
	["min"] = 16,
	["max"] = 100,
})
slider:Set(16)
```

AddKeybind:
```
local keybind = tab:AddKeybind("Toggle", function(obj)
	ui_options.toggle_key = obj
end, {
	["standard"] = Enum.KeyCode.RightShift,
})
```

AddDropdown:
```
local dropdown = tab:AddDropdown("Teleport to Location", function(text)
	if text == "Mars" then
		teleport(CFrame.new(...))
	elseif ...
	end
end)
local mars = dropdown:Add("Mars")
local earth = dropdown:Add("Earth")
local not_a_planet = dropdown:Add("Iridocyclitis")
not_a_planet:Remove()
```

AddColorPicker:
```
tab:AddLabel("Theme color")
local cp = tab:AddColorPicker(function(color)
	ui_options.main_color = color
end)
```

AddFolder:
```
local folder = tab:AddFolder()
folder:AddSwitch()
folder:AddLabel("Woo! I'm inside a folder!")

local folder2 = folder:AddFolder()
folder2:AddLabel("I'm inside *two* folders :smirk:")
```

[Adding Options]:
The only two element-functions taking options right now is "AddSlider" and "AddTextBox".
To set options, simply add a table as the last argument, like this:
```
tab:AddSlider("WalkSpeed", function(x)
	setwalkspeed(x)
end, {
	["min"] = 16, -- default : 0
	["max"] = 100, -- default : 100
})
```

Now for AddTextBox example:
```
tab:AddTextBox("Epic", function(text)
	print("TextBox : " .. text)
end, {
	["clear"] = false, -- default : true
})
```

AddConsole example:
```
tab:AddConsole({
	["y"] = 210,
	["readonly"] = false,
	["source"] = "Lua",
})
```
