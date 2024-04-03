# SourceIndex

## Overview

***

## Methods

### GetModule <small>any?</small> { #GetModule data-toc-label="GetModule" }

Used to get a module from the given `moduleName`. Returns a `ModuleSource` if found, otherwise it will throw an error.

| Argument | Type | Required |
| :---: | :---: | :---: |
| moduleName | string | ✔︎ |

=== "Script"

    ```lua
    local Source = shared.Core:GetService("Source")
    local SharedSourceIndex: SourceIndex = Source:GetSharedSourceIndex()

    local MyModule = SharedSourceIndex:GetModule("MyModule")

    print(MyModule.foo())
    ```

=== "MyModule"

    ```lua
    local MyModule = {  }

    function MyModule.foo(): string
        return "Hello World!"
    end

    return MyModule
    ```

### GetPackage <small>any?</small> { #GetPackage data-toc-label="GetPackage" }

Used to get a package from the given `packageName`. Returns a `ModuleSource` if found, otherwise it will throw an error.

| Argument | Type | Required |
| :---: | :---: | :---: |
| packageName | string | ✔︎ |

=== "Script"

    ```lua
    local Source = shared.Core:GetService("Source")
    local SharedSourceIndex: SourceIndex = Source:GetSharedSourceIndex()

    local MyPackage = SharedSourceIndex:GetPackage("MyPackage")

    print(MyModule.foo())
    ```

=== "MyPackage"

    ```lua
    local MyPackage = {  }

    function MyPackage.foo(): string
        return "Hello World!"
    end

    return MyPackage
    ```