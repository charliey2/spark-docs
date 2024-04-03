## Accessing Core

The `Core` is the most important part of the framework. It provides access to all services, runs scripts, contains modules, packages, and game assets.

```lua
local irisCORE = shared.Core
```

***

## Methods

### GetService <small>Service</small> { #GetService data-toc-label="GetService" }

Used to get a `Service` from the given `serviceName`.

| Argument | Type | Required |
| :---: | :---: | :---: |
| serviceName | string | ✔︎ |

```lua
local irisCORE = shared.Core
local Utility = irisCORE:GetService("Utility")
```

***

## Properties

### Source <small>Folder</small> { #Source data-toc-label="Source" }

Reference to either the Server source directory if the script context is Server, or the Client source directory if the script context is Client.

```lua
-- Client Context Script
local irisCORE = shared.Core

local sourceFolder: Folder = irisCORE.Source
local clientScripts: { ModuleScript } = sourceFolder:WaitForChild("Scripts"):GetChildren()
```
