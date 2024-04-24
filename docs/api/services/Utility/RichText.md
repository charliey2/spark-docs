# RichText

## Overview

A simple service that makes using RichText easier by providing a set of methods to format strings instead of memorizing the RichText syntax. It does not provide formatting for all RichText features, but it does provide the most commonly used ones.

***

## Methods

### Color <small><string\></small> { #Color data-toc-label="Color" }

Used to format a string with a given Color3. Returns the RichText formatted string.

| Argument | Type | Required |
| :---: | :---: | :---: |
| text | string | ✔︎ |
| color | Color3 | |

```lua
local RichText = Utility.RichText

local someGui: TextLabel = ...

local redHelloText: string = RichText.Color("Hello", Color3.fromRGB(255, 0, 0))
local blueWorldText: string = RichText.Color("world", Color3.fromRGB(0, 0, 255))

someGui.Text = redHelloText .. " " .. blueWorldText .. "!"
```

### Bold <small><string\></small> { #Bold data-toc-label="Bold" }

Used to format a string in bold. Returns the RichText formatted string.

| Argument | Type | Required |
| :---: | :---: | :---: |
| text | string | ✔︎ |

### Italicize <small><string\></small> { #Italicize data-toc-label="Italicize" }

Used to format a string in italics. Returns the RichText formatted string.

| Argument | Type | Required |
| :---: | :---: | :---: |
| text | string | ✔︎ |

## Quick Styling
Experimental
{ .flag .plain }

Quick styling allows you to call the service directly with a provided string, quick style code and parameters.

```lua
local RichText = Utility.RichText

local someGui: TextLabel = ...

someGui.Text = RichText("C", "Hello", Color3.fromRGB(255, 0, 0)) .. " " .. RichText("C", "world", Color3.fromRGB(0, 0, 255)) .. "!"
```

| Code | Keys | Parameters |
| :---: | :---: | :---: |
| Color | `C` `c` | `<string, Color3?>` |
| Bold | `B` `b` | `<string>` |
| Italicize | `I` `i` | `<string>` |