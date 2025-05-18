# Skid Softworks UI Library

Skid Softworks is a powerful and lightweight UI library for Roblox, designed to create intuitive and customizable graphical user interfaces. Inspired by popular UI libraries, it provides a simple API for creating windows, tabs, sections, and various UI elements like buttons, toggles, and sliders.

## Features
- **Drag-and-Drop Windows**: Create resizable and movable windows.
- **Tab System**: Organize content into multiple tabs.
- **Customizable Elements**: Includes buttons, toggles, sliders, and more.
- **Lightweight**: Minimal performance impact.
- **Easy to Use**: Simple and intuitive API.

## Installation
1. **Download the Library**:
   - Copy the `SkidSoftworks.lua` file into your Roblox project.
   - Alternatively, load it via HTTP (if allowed in your environment):
     ```lua
     local SkidSoftworks = loadstring(game:HttpGet("https://raw.githubusercontent.com/YourRepo/SkidSoftworks/main/SkidSoftworks.lua"))()
     ```

2. **Include in Your Script**:
   - Require the library in your Lua script:
     ```lua
     local SkidSoftworks = require(game.ReplicatedStorage.SkidSoftworks)
     ```

3. **Initialize the Library**:
   - Create a new instance of the library:
     ```lua
     local UI = SkidSoftworks.new()
     ```

## Usage
### Creating a Window
Create a window with a custom title:
```lua
local window = UI:MakeWindow({Title = "My Skid Softworks UI"})
```

### Adding Tabs
Add tabs to organize content:
```lua
local tab1 = UI:MakeTab(window, "Main")
local tab2 = UI:MakeTab(window, "Settings")
```

### Adding Sections
Group elements within tabs using sections:
```lua
local section = UI:AddSection(tab1, "General")
```

### Adding UI Elements
#### Button
Add a clickable button:
```lua
UI:AddButton(section, {
    Name = "Click Me",
    Callback = function()
        print("Button clicked!")
    end
})
```

#### Toggle
Add a toggle switch:
```lua
UI:AddToggle(section, {
    Name = "Enable Feature",
    Default = false,
    Callback = function(state)
        print("Toggle state: " .. tostring(state))
    end
})
```

#### Slider
Add a slider for numerical input:
```lua
UI:AddSlider(section, {
    Name = "Volume",
    Min = 0,
    Max = 100,
    Default = 50,
    Callback = function(value)
        print("Slider value: " .. value)
    end
})
```

## Example Script
Here's a complete example that creates a UI with multiple tabs and elements:
```lua
local SkidSoftworks = require(game.ReplicatedStorage.SkidSoftworks)
local UI = SkidSoftworks.new()

local window = UI:MakeWindow({Title = "Example UI"})

local tab1 = UI:MakeTab(window, "Home")
local section1 = UI:AddSection(tab1, "Controls")

UI:AddButton(section1, {
    Name = "Test Button",
    Callback = function()
        print("Button pressed!")
    end
})

UI:AddToggle(section1, {
    Name = "God Mode",
    Default = false,
    Callback = function(state)
        print("God Mode: " .. tostring(state))
    end
})

UI:AddSlider(section1, {
    Name = "Speed",
    Min = 16,
    Max = 100,
    Default = 16,
    Callback = function(value)
        print("Speed set to: " .. value)
    end
})

local tab2 = UI:MakeTab(window, "Settings")
local section2 = UI:AddSection(tab2, "Preferences")

UI:AddToggle(section2, {
    Name = "Dark Mode",
    Default = true,
    Callback = function(state)
        print("Dark Mode: " .. tostring(state))
    end
})
```

## API Reference
### SkidSoftworks.new()
Creates a new UI instance.
- Returns: UI instance

### UI:MakeWindow(options)
Creates a new window.
- `options.Title` (string): Window title (default: "Skid Softworks UI")
- Returns: Window object

### UI:MakeTab(window, name)
Creates a new tab in the specified window.
- `window` (table): Window object
- `name` (string): Tab name
- Returns: Tab object

### UI:AddSection(tab, name)
Creates a new section in the specified tab.
- `tab` (table): Tab object
- `name` (string): Section name
- Returns: Section object

### UI:AddButton(section, options)
Adds a button to the specified section.
- `section` (table): Section object
- `options.Name` (string): Button text
- `options.Callback` (function): Function to call when clicked
- Returns: Button object

### UI:AddToggle(section, options)
Adds a toggle to the specified section.
- `section` (table): Section object
- `options.Name` (string): Toggle label
- `options.Default` (boolean): Initial state
- `options.Callback` (function): Function to call when state changes
- Returns: Toggle object

### UI:AddSlider(section, options)
Adds a slider to the specified section.
- `section` (table): Section object
- `options.Name` (string): Slider label
- `options.Min` (number): Minimum value
- `options.Max` (number): Maximum value
- `options.Default` (number): Initial value
- `options.Callback` (function): Function to call when value changes
- Returns: Slider object

## Notes
- Ensure the library is placed in a location accessible to your scripts (e.g., `ReplicatedStorage`).
- HTTP loading may be restricted in some Roblox environments; use local files if necessary.
- The library uses Roblox's built-in UI services, so no external dependencies are required.

## Contributing
Contributions are welcome! Please submit pull requests or open issues on the [GitHub repository](https://github.com/YourRepo/SkidSoftworks).

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
