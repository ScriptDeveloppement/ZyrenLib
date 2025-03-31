# ZyrenLib
This documentation is for the stable release of ZyrenLib.

## Booting the Library
```lua
local Zyren = loadstring(game:HttpGet("https://raw.githubusercontent.com/YourUsername/ZyrenLib/main/Source.lua"))({
    WindowTitle = "Your Title",  -- Window title text
    ColorTheme = "Synapse"       -- Theme name (Synapse, Dark, Red, Ocean, Midnight, GrapeTheme)
})
```
## Creating a Tab
```lua
local MainTab = Zyren:CreateTab("Main")
})

--[[
Name = <string> - The name of the tab.
Icon = <string> - The icon of the tab.
PremiumOnly = <bool> - Makes the tab accessible to Sirus Premium users only.
]]
```
## Creating Groupboxes
```lua
local LeftGroupbox = MainTab:CreateGroup("Combat", "left")  -- "left" or "right" column
local RightGroupbox = MainTab:CreateGroup("Movement", "right")
```
You can add elements to sections the same way you would add them to a tab normally.

## Creating a Button
```lua
Tab:AddButton({
    Text = "Button",
    Callback = function()
        print("Button pressed!")
    end
})
```


## Creating Toggle
```lua
Tab:AddToggle({
    Text = "Toggle",
    Default = false,
    Callback = function(value)
        print("Aimbot:", value)
    end
})
```

### Changing the value of an existing Toggle
```lua
CoolToggle:Set(true)
```



## Creating a Color Picker
```lua
Tab:AddColorPicker(config)
    local ColorPicker = {
        Name = "Color Picker",
        Value = (255, 255, 255),
        Callback = config.Callback
    }
    
    -- Implementation would go here
    -- Returns color picker object
end
```

## Creating a Slider
```lua
CombatGroup:AddSlider({
    Text = "Slider",
    Min = 1,
    Max = 360,
    Default = 90,
    Rounding = 1,
    Suffix = "°",  -- Optional suffix
    Callback = function(value)
        print(value)
    end
})
```




## Creating a Dropdown menu
```lua
function Group:AddDropdown(config)
    local Dropdown = {
        Name = "",
        Value = "Default",
        Options = ("Default, Default 2"),
        Open = false
    }
    
    -- Implementation would go here
    -- Returns dropdown object
end
```
