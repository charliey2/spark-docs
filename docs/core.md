## Accessing Core

The `Core` is the most important part of the framework. It provides access to all services, runs scripts, contains modules, packages, and game assets.

!!! tip
    The `Core` will always be finished loading before scripts run. Both the `Source` folder and all services will exist and be ready for use immediately.

```lua
local irisCORE = shared
```

exampletext
{ .flag .deprecated }

exampletext
{ .flag .server }

exampletext
{ .flag .client }

***

## Methods

### GetService <small>Service</small> { #GetService data-toc-label="GetService" }

Used to get a `Service` from the given `serviceName`.

| Argument | Type | Required |
| :---: | :---: | :---: |
| serviceName | string | ✔︎ |

```lua
local Utility = irisCORE:GetService("Utility")
```

***

## Properties

### Source <small>Folder</small> { #Source data-toc-label="Source" }

Reference to either the Server source directory if the script context is Server, or the Client source directory if the script context is Client.

```lua
-- Client Context Script
local irisCORE = shared

local sourceFolder: Folder = irisCORE.Source
local clientScripts: { ModuleScript } = sourceFolder:WaitForChild("Scripts"):GetChildren()
```
