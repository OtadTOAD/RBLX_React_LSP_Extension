# RBLX React LSP

Provides auto-complete suggestions for instances and their properties when using React.createElement in Lua/Luau files.

## Features

- Provides auto completion suggestions for instance's properties
- Provides auto completion suggestions for instance's names

## How to Use

This extension detects whenever any variable is assigned a value matching the pattern `require(Anything.React)`.
<details>
  <summary>For context</summary>
  `Anything` here could be any string, but must be at least one character.
</details>
If this pattern is not detected, the LSP will not provide auto completion suggestions.

**Warning: If you have multiple assignments, only _first one_ will be treated as valid for simplicty.** 

Once the variable is found, its name will be used to identify patterns like `name.createElement(Context)`
<details>
  <summary>For context</summary>
  `name` here must be equal to variable name.
</details>

Whenever your text cursor is within `Context` span, LSP will provide auto complete suggestions.
* If the cursor is within the **first quotes**, it will suggest Roblox **instance names**.
* If the cursor is within the **first set of brackets** and **not** on **the right side of an equals sign** (on the same line), it will try to:
    * Look up the instance using name you entered in the first quotes.
    * Provide its **properties** from Roblox's API dump, if found.

## Repositories

- **Frontend:** [VS Code Extension](https://github.com/OtadTOAD/RBLX_React_LSP_Extension.git)
- **Backend:** [LSP Server](https://github.com/OtadTOAD/RBLX_React_LSP_Backend.git)