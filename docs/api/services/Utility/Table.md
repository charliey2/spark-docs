# Table

## Overview

***

## Methods

### DeepCopy <small><table\></small> { #DeepCopy data-toc-label="DeepCopy" }

Returns a deep copy of the provided table.

| Argument | Type | Required |
| :---: | :---: | :---: |
| sourceTable | table | ✔︎ |

=== "Script"

    ```lua
    local Table = Utility.Table

    local myDictionary = {
        fruits = {
            { "granny smith", "sour apple" },
            "banana",
            "cherry"
        },

        inSeason = true
    }

    local deepCopy = Table:DeepCopy(myDictionary)

    print(deepCopy)
    ```

=== "Output"
    
    ```lua
    {
        fruits = {
            { "granny smith", "sour apple" },
            "banana",
            "cherry"
        },

        inSeason = true
    }
    ```

### SizeOf <small><number\></small> { #SizeOf data-toc-label="SizeOf" }

Returns the `number` size of the provided table. When using the recursive option, note that nested tables will have their `Size + 1` added to the total size.

| Argument | Type | Required | Default |
| :---: | :---: | :---: | |
| sourceTable | table | ✔︎ | |
| recursive | boolean |  | `false` |

```lua
local Table = Utility.Table

local myDictionary = {
    fruits = {
        { "granny smith", "sour apple" },
        "banana",
        "cherry"
    },

    inSeason = true
}

local size = Table:SizeOf(myDictionary, true)

print(size) --> 7 (2 without recursive option)
```

### Reconcile <small><table\></small> { #Reconcile data-toc-label="Reconcile" }

| Argument | Type | Required |
| :---: | :---: | :---: |
| sourceTable | table | ✔︎ |
| templateTable | table | ✔︎ |

### DisconnectAndClear <small><void\></small> { #DisconnectAndClear data-toc-label="DisconnectAndClear" }

Disconnects all `RBXScriptConnection` and custom signal implementations (if they have a `Disconnect` method) from the provided table, then clears the table.

| Argument | Type | Required |
| :---: | :---: | :---: |
| sourceTable | table | ✔︎ |