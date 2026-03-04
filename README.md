# Roblox React LSP: IntelliSense & Autocomplete for Luau

![Visual Studio Marketplace Version](https://img.shields.io/visual-studio-marketplace/v/OtadTOAD.rblx-react-lsp)

Auto-complete for Roblox instances, properties, and events inside `React.createElement` calls in Luau.

![Extension Example](https://i.imgur.com/dR64GKP.gif)

## Features
- Instance name suggestions inside `createElement` (Part, Frame, UIStroke, etc.)
- Property IntelliSense pulled directly from the Roblox API
- Event suggestions inside `[React.Event.X]`
- Property change suggestions inside `[React.Change.X]`
- Results ranked by how frequently you use them in the current file
- Works with `createElement` macros like `local e = React.createElement`

## Setup
On first install, run the **Generate and Cache API Metadata** command to download and cache the Roblox API:
1. Open Command Palette (`Ctrl+Shift+P`)
2. Search for `RBLX React: Generate and Cache API Metadata`
3. Wait for the success notification in the bottom left

Run this again whenever you want the latest Roblox API changes.

> **Tip:** If completions don't appear automatically, press `Ctrl+Space` to trigger them manually, especially useful inside quotes when typing instance names.

## Usage

The extension activates when it detects a React require anywhere in your file (case-insensitive):
```lua
local React = require(somewhere.React)
```

Completions trigger automatically inside `createElement` calls:
```lua
React.createElement("Fra|")               -- Roblox instance names
React.createElement("Frame", { Vis|  })   -- instance properties
React.createElement("Frame", {
    [React.Event.Mo|]                      -- instance events
})
React.createElement("Frame", {
    [React.Change.Vi|]                     -- property change listeners
})
```

Supports `createElement` macros too:
```lua
local e = React.createElement
e("Frame", { Vis| })  -- works the same
```

## Compatibility
- Works alongside **Luau LSP** and **Roblox LSP**, enable per-workspace to avoid conflicts with other language servers
- Built for **Rojo**-based workflows where React-Luau/Roact is required from a package

## Notes
- Only the **first** `require(...React)` in a file is used as the React variable
- The extension currently activates on all Lua/Luau files, it's recommended to enable it per-workspace only where Roblox React is used

## Repositories
- [VS Code Extension](https://github.com/OtadTOAD/RBLX_React_LSP_Extension)
- [LSP Server (Rust)](https://github.com/OtadTOAD/RBLX_React_LSP_Backend)