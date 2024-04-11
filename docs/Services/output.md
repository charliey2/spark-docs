# Output

## Overview

The `Output` service provides .... more text here....??

***

## Methods

### printIf <small>void</small> { #printIf data-toc-label="printIf" }

Prints a message if the conditional is true.

| Argument | Type | Required |
| :---: | :---: | :---: |
| conditional | boolean | ✔︎ |
| params | tuple | ✔︎ | 

=== "Example 1"

    ```lua
    local Output = shared:GetService("Output")

    Output.printIf(1 + 1 == 2, "Math works!")
    --> "Math works!"
    ```

=== "Example 2"

    ```lua
    local Output = shared:GetService("Output")

    Output.printIf(1 + 1 == 2, "1", "+", "1", "= 2")
    --> "1 + 1 = 2"
    ```

### warnIf <small>void</small> { #warnIf data-toc-label="warnIf" }

Warns (1) a message if the conditional is true.
{ .annotate }

1. This is similar to printing, but the text is orange.

| Argument | Type | Required |
| :---: | :---: | :---: |
| conditional | boolean | ✔︎ |
| params | tuple | ✔︎ | 

=== "Example 1"

    ```lua
    local Output = shared:GetService("Output")

    Output.warnIf(1 + 1 == 2, "Math works!")
    --> "Math works!"
    ```

=== "Example 2"

    ```lua
    local Output = shared:GetService("Output")

    Output.warnIf(1 + 1 == 2, "1", "+", "1", "= 2")
    --> "1 + 1 = 2"
    ```

### errorIf <small>void</small> { #errorIf data-toc-label="errorIf" }

Errors if the conditional is true.

| Argument | Type | Required |
| :---: | :---: | :---: |
| conditional | boolean | ✔︎ |
| message | string | ✔︎ |
| level | number |  |