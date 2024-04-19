# SourceIndex

## Overview

The `SourceIndex` class contains methods for accessing modules and packages from source directories.

***

## Methods

### GetModule <small><any?\></small> { #GetModule data-toc-label="GetModule" }

Used to get a module from the given `moduleName`. Returns a `ModuleSource` if found, otherwise it will throw an error.

| Argument | Type | Required |
| :---: | :---: | :---: |
| moduleName | string | ✔︎ |

=== "Script"

    ```lua
    local Source = shared:GetService("Source")
    local SharedSourceIndex: SourceIndex = Source:GetSharedSourceIndex()

    local MyModule = SharedSourceIndex:GetModule("MyModule")

    print(MyModule.foo())
    --> "Hello World!"
    ```

=== "MyModule"

    ```lua
    local MyModule = {  }

    function MyModule.foo(): string
        return "Hello World!"
    end

    return MyModule
    ```

</br>

### GetPackage <small><any?\></small> { #GetPackage data-toc-label="GetPackage" }

Used to get a package from the given `packageName`. Returns a `ModuleSource` if found, otherwise it will throw an error.

| Argument | Type | Required |
| :---: | :---: | :---: |
| packageName | string | ✔︎ |

??? warning "Package Context Warning"
    Only the server context and shared context have packages. Attempting to access `GetPackage` on a client `GetContextSourceIndex` SourceIndex will throw an error.

    ```lua
    --// Client Context Script
    local Source = shared:GetService("Source")
    local ContextSourceIndex: SourceIndex = Source:GetContextSourceIndex()
    local SharedSourceIndex: SourceIndex = Source:GetSharedSourceIndex()

    --> this line will error
    local SuperCoolPackage = ContextSourceIndex:GetPackage("SuperCoolPackage")

    --> this line will not error
    local SuperCoolPackage = SharedSourceIndex:GetPackage("SuperCoolPackage")
    ```

=== "Script"

    ```lua
    local Source = shared:GetService("Source")
    local SharedSourceIndex: SourceIndex = Source:GetSharedSourceIndex()

    local MyPackage = SharedSourceIndex:GetPackage("MyPackage")

    print(MyModule.foo())
    --> "Hello World!"
    ```

=== "MyPackage"

    ```lua
    local MyPackage = {  }

    function MyPackage.foo(): string
        return "Hello World!"
    end

    return MyPackage
    ```