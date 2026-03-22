# RichText

## Overview

A simple service that makes using RichText easier by providing a set of methods to format strings instead of memorizing the RichText syntax. It does not provide formatting for all RichText features, but it does provide the most commonly used ones.

***

## Constructors

### color <small><string\></small> { #color data-toc-label="color" }

Used to format a string with a given Color3. Returns the RichText formatted string.

| Argument | Type | Required |
| :---: | :---: | :---: |
| text | string | ✔︎ |
| color | Color3 | |

```lua
local RichText = Utility.RichText

local someGui: TextLabel = ...

local redHelloText: string = RichText.color("Hello", Color3.fromRGB(255, 0, 0))
local blueWorldText: string = RichText.color("world", Color3.fromRGB(0, 0, 255))

someGui.Text = redHelloText .. " " .. blueWorldText .. "!"
```

### bold <small><string\></small> { #bold data-toc-label="bold" }

Used to format a string in bold. Returns the RichText formatted string.

| Argument | Type | Required |
| :---: | :---: | :---: |
| text | string | ✔︎ |

### italicize <small><string\></small> { #italicize data-toc-label="italicize" }

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