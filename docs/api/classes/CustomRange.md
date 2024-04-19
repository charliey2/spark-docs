# CustomRange

## Overview

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

If inclusive, checks if `number` `x >= Min` and `x <= Max`. Otherwise, checks if `number` `x > Min` and `x < Max`.

| Argument | Type | Required | Default |
| :---: | :---: | :---: |  |
| x | number | ✔︎ |  |
| inclusive | boolean |  | `false` |

### Values <small><number, number\></small> { #Values data-toc-label="Values" }

Returns the minimum and maximum values of the range as a tuple.