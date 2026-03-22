# CustomRange

## Overview

A `CustomRange` is almost identical to the Roblox [NumberRange](https://create.roblox.com/docs/en-us/reference/engine/datatypes/NumberRange) except it provides two extra functions.

***

## Properties

### Min <small><number\></small> { #Min data-toc-label="Min" }
Read Only
{ .flag .plain }

References the minimum value of the range.

### Max <small><number\></small> { #Max data-toc-label="Max" }
Read Only
{ .flag .plain }

References the maximum value of the range.

***

## Methods

### InRange <small><boolean\></small> { #InRange data-toc-label="InRange" }

If inclusive, checks if `x >= Min` and `x <= Max`. Otherwise, checks if `x > Min` and `x < Max`.

| Argument | Type | Required | Default |
| :---: | :---: | :---: |  |
| x | number | ✔︎ |  |
| inclusive | boolean |  | `true` |

### Values <small><number, number\></small> { #Values data-toc-label="Values" }

Returns the minimum and maximum values of the range as a tuple.