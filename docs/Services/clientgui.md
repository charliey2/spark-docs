# ClientGui

## Overview

The `ClientGui` service provides client side access to `GuiBase` objects. It also acts as a wrapper for certain built-in `CoreGui` methods.

***

## Methods

### GetInterface <small>GuiBase?</small> { #GetInterface data-toc-label="GetInterface" }
Client Only
{ .flag .client }

Prints a message if the conditional is true. If `shouldYield` is `true`, the script will yield until the interface object is created. If `shouldYield` is `false`, the script will look for an already loaded interface object with the given `interfaceName` and return it if found, otherwise the script will attempt to load and return a new interface object from a template with the same `interfaceName`. If no object can be loaded, `nil` is returned.

| Argument | Type | Required | Default |
| :---: | :---: | :---: | :---: |
| interfaceName | string | ✔︎ |  |
| shouldYield | boolean |  | `false` |

=== "Without Yielding"

    ```lua
    local ClientGui = shared:GetService("ClientGui")

    local mainMenuGui = ClientGui:GetInterface("MainMenu")
    ```

=== "With Yielding"

    === "Script 1"

        ```lua
        local ClientGui = shared:GetService("ClientGui")

        -- Will yield until another script loads MainMenu
        -- *If the interface is already loaded it will be returned without yielding
        local mainMenuGui = ClientGui:GetInterface("MainMenu", true)
        ```

    === "Script 2"

        ```lua
        local ClientGui = shared:GetService("ClientGui")

        -- Loads the object and returns it, also returns the object to all yielding methods
        local mainMenuGui = ClientGui:GetInterface("MainMenu")
        ```

### SetCoreGuiEnabled <small>void</small> { #SetCoreGuiEnabled data-toc-label="SetCoreGuiEnabled" }
Client Only
{ .flag .client }

| Argument | Type | Required |
| :---: | :---: | :---: |
| coreGuiType | `Enum.CoreGuiType` | ✔︎ |
| enabled | boolean | ✔︎ |

### GetCoreGuiEnabled <small>boolean</small> { #GetCoreGuiEnabled data-toc-label="GetCoreGuiEnabled" }
Client Only
{ .flag .client }

| Argument | Type | Required |
| :---: | :---: | :---: |
| coreGuiType | `Enum.CoreGuiType` | ✔︎ |