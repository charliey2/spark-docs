# Object

## Overview

***

## Methods

### Create <small><Instance\></small> { #Create data-toc-label="Create" }

Meant to replace Roblox's built in `Instance.new` method, this contructor provides a more robust way to create instances. The properties argument is an array that contains sub-arrays formatted as such: `{ "PropertyName", Value }`; however, there are some unique property flags that can be used to create large `Instance` trees with ease. Properties are applied in the order they are provided.

| Argument | Type | Required |
| :---: | :---: | :---: |
| className | string | ✔︎ |
| properties | array |  |

=== "Standard Use"

    ```lua
    local Object = ...

    Object.Create("Part", {
        { "Name", "NewPart" },
        { "Size", Vector3.new(1, 1, 1) },
        { "Position", Vector3.new(0, 15, 0) },
        { "Anchored", true },
        { "Parent", workspace }
    })
    ```

=== "Property Flags"

    === "__Children"

        `__Children` is a special property flag that allows you to create a tree of `Instance` objects. The value of `__Children` should be an array of `Instance` objects or arrays that contain a `ClassName` and properties to be used to construct a new `Instance`. The `Instance` objects are created in the order they are provided. Every `Instance` object created in the `__Children` array will be parented to the `Instance` object that `__Children` is a property of.

        The entire `Instance` tree will be finished before the absolute parent `Instance` is returned.

        === "Example 1"

            ``` lua
            local Object = ...

            Object.Create("Model", {
                { "Name", "NewModel" },
                { "__Children", {
                    Object.Create("Part", {
                        { "Name", "BottomPart" },
                        { "Size", Vector3.new(1, 1, 1) },
                        { "Position", Vector3.new(0, 10, 0) },
                        { "BrickColor", BrickColor.new("Bright blue") },
                        { "Anchored", true }
                    }),
                    Object.Create("Part", {
                        { "Name", "TopPart" },
                        { "Size", Vector3.new(1, 1, 1) },
                        { "Position", Vector3.new(0, 15, 0) },
                        { "BrickColor", BrickColor.new("Bright red") },
                        { "Anchored", true }
                    })
                } },
                { "Parent", workspace }
            })
            ```
            
            ```bash
            .
            └── Workspace/
                └── Model "NewModel"/
                    ├── Part "BottomPart"
                    └── Part "TopPart"
            ```

        === "Example 2"

            ```lua
            local Object = ...

            local bottomPart: Part = Object.Create("Part", {
                { "Name", "BottomPart" },
                { "Size", Vector3.new(1, 1, 1) },
                { "Position", Vector3.new(0, 10, 0) },
                { "BrickColor", BrickColor.new("Bright blue") },
                { "Anchored", true }
            })

            Object.Create("Model", {
                { "Name", "NewModel" },
                { "__Children", {
                    bottomPart,
                    Object.Create("Part", {
                        { "Name", "MiddlePart" },
                        { "Size", Vector3.new(1, 1, 1) },
                        { "Position", Vector3.new(0, 12.5, 0) },
                        { "BrickColor", BrickColor.new("Bright yellow") },
                        { "Anchored", true },
                        { "__Children", {
                            Object.Create("PointLight", {
                                { "Name", "Light" },
                                { "Range", 10 },
                                { "Color", Color3.fromRGB(255, 255, 0) },
                                { "Brightness", 2 }
                            })
                        } }
                    }),
                    { "Part", {
                        { "Name", "TopPart" },
                        { "Size", Vector3.new(1, 1, 1) },
                        { "Position", Vector3.new(0, 15, 0) },
                        { "BrickColor", BrickColor.new("Bright red") },
                        { "Anchored", true }
                    } }
                } },
                { "Parent", workspace }
            })
            ```

            ```bash
            .
            └── Workspace/
                └── Model "NewModel"/
                    ├── Part "BottomPart"
                    ├── Part "MiddlePart"/
                    │   └── PointLight "Light"
                    └── Part "TopPart"
            ```

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