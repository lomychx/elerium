# Elerium

Elerium is a UI library for Roblox Lua, designed to make creating user interfaces easier and more intuitive. It provides a set of functions for creating windows, tabs, and various UI elements such as labels, buttons, text boxes, switches, sliders, keybinds, dropdowns, color pickers, and consoles.

To create a new window, use the `AddWindow` function:

```lua
local window = library:AddWindow("My Window")
```

This function returns a table consisting of more functions that you can use on this window. To add a tab to our window, use the AddTab function:
```lua
local tab = window:AddTab("My Tab")
```

This function also returns a table with functions. To make this tab show as the first thing, call the Show function:
```lua
tab:Show()
```
Now you can begin adding UI elements to this tab. Here are some examples:
## AddLabel
```lua
tab:AddLabel("Hello World!")
```
## AddButton
```lua
tab:AddButton("Click me!", function()
    print("Button clicked!")
end)
```
## AddTextBox
```lua
tab:AddTextBox("Enter text here", function(text)
    print("Entered text: " .. text)
end)
```
## AddSwitch
```lua
local switch = tab:AddSwitch("Toggle me", function(state)
    print("Switch state: " .. tostring(state))
end)
switch:Set(true) -- set the initial state
```
## AddSlider
```lua
local slider = tab:AddSlider("Adjust value", function(value)
    print("Slider value: " .. value)
end, {
    min = 0,
    max = 100,
})
slider:Set(50) -- set the initial value
```
## AddKeybind
```lua
local keybind = tab:AddKeybind("Toggle UI", function(key)
    print("Keybind pressed: " .. tostring(key))
end)
```
## AddDropdown
```lua
local dropdown = tab:AddDropdown("Choose an option", function(option)
    print("Selected: " .. option)
end)
local option1 = dropdown:Add("Option 1")
local option2 = dropdown:Add("Option 2")
option2:Remove() -- remove an option
```
## AddColorPicker
```lua
local colorpicker = tab:AddColorPicker(function(color)
    print("Selected color: " .. tostring(color))
end)
```
## AddFolder
```lua
local folder = tab:AddFolder("My Folder")
folder:AddLabel("Hello from inside a folder!")
```
## Usage
```lua
local library = loadstring(game:HttpGet('https://raw.githubusercontent.com/lomychx/elerium/main/lib.lua'))()
```
You can then use the library table to create UI elements in your game.
