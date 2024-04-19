# Object

## Overview

***

## Methods

### Create <small><Instance\></small> { #Create data-toc-label="Create" }

Docs todo...

### GetChildrenOfClass <small><array\></small> { #GetChildrenOfClass data-toc-label="GetChildrenOfClass" }

Returns an array of `Instance` children that have the specific `ClassName`. It does not check for class inheritance. Use `GetChildrenWhichAre` to respect class inheritance.

| Argument | Type | Required |
| :---: | :---: | :---: |
| parent | Instance | ✔︎ |
| className | string | ✔︎ |

```lua
local Object = ...

local parts: { Part } = Object.GetChildrenOfClass(workspace, "Part")

for _, part: Part in parts do
    print(part.Name, "is a Part in workspace!")
end
```

### GetChildrenWhichAre <small><array\></small> { #GetChildrenWhichAre data-toc-label="GetChildrenWhichAre" }

Returns an array of `Instance` children that are of the specific `ClassName` or inherit from it. Uses `IsA` to check for class inheritance.

| Argument | Type | Required |
| :---: | :---: | :---: |
| parent | Instance | ✔︎ |
| className | string | ✔︎ |

```lua
local Object = ...

local parts: { BasePart } = Object.GetChildrenWhichAre(workspace, "BasePart")

for _, part: BasePart in parts do
    print(part.Name, "is a BasePart in workspace!")
end
```

### ClearChildrenOfClass <small><void\></small> { #ClearChildrenOfClass data-toc-label="ClearChildrenOfClass" }

Removes all children of the parent that have the specific `ClassName`. It does not check for class inheritance. Use `ClearChildrenWhichAre` to respect class inheritance.

| Argument | Type | Required |
| :---: | :---: | :---: |
| parent | Instance | ✔︎ |
| className | string | ✔︎ |

```lua
local Object = ...

Object.ClearChildrenOfClass(workspace, "Part")
```

### ClearChildrenWhichAre <small><void\></small> { #ClearChildrenWhichAre data-toc-label="ClearChildrenWhichAre" }

Removes all children of the parent that are of the specific `ClassName` or inherit from it. Uses `IsA` to check for class inheritance

| Argument | Type | Required |
| :---: | :---: | :---: |
| parent | Instance | ✔︎ |
| className | string | ✔︎ |

```lua
local Object = ...

Object.ClearChildrenWhichAre(workspace, "BasePart")
```

### WaitForPropertyValueChange <small><any\></small> { #WaitForPropertyValueChange data-toc-label="WaitForPropertyValueChange" }
Can Yield
{ .flag .plain }

Waits for a property of an object to change to a specific value. Returns the new value of the property.

| Argument | Type | Required |
| :---: | :---: | :---: |
| object | Instance | ✔︎ |
| property | string | ✔︎ |

```lua
local Object = ...

local part: BasePart = workspace:WaitForChild("Part")
local newName: string = Object.WaitForPropertyValueChange(part, "Name")

print(newName)
```