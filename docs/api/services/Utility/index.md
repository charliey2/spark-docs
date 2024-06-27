[Table]: ./Table.md
[Number]: ./Number.md
[Object]: ./Object.md
[RichText]: ./RichText.md

# Utility

## Overview

***

## Call Service

Utility modules can be imported by calling the Utility service; the order of utility module names passed dictates the order of the returned modules (tuple).

```lua
local Utility = shared:GetService("Utility")

local Table, Object = Utility { "Table" "Object" }
```

!!! tip
    If you only need to use one module in a script, indexing the module directly is faster and more efficient.

    ```lua
    local Utility = shared:GetService("Utility")

    local Table = Utility.Table
    ```

## Properties

### Table <small><[Table]\></small> { #Table data-toc-label="Table" }

References the [Table] utility.

### Number <small><[Number]\></small> { #Number data-toc-label="Number" }

References the [Number] utility.

### Object <small><[Object]\></small> { #Object data-toc-label="Object" }

References the [Object] utility.

### RichText <small><[RichText]\></small> { #RichText data-toc-label="RichText" }

References the [RichText] utility.