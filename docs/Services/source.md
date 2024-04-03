[SourceIndex]: https://www.google.com

## Overview

The `Source` service provides easy access to both shared and context-locked (server/client) source files. This service can only get modules and packages and should not be used to get world, interface, or effect assets.

***

## Methods

### GetContextSourceIndex <small>[SourceIndex]</small> { #GetContextSourceIndex data-toc-label="GetContextSourceIndex" }

Gets the source index for the current script context. Respects context-locked source files, eg. Server context scripts can only access server source files. Returns a [SourceIndex].

```lua
local irisCORE = shared.Core
local Source = irisCORE:GetService("Source")

local ContextSourceIndex: SourceIndex = Source:GetContextSourceIndex()
local MyCoolPackage = ContextSourceIndex:GetPackage("MyCoolPackage")
```

### GetSharedSourceIndex <small>[SourceIndex]</small> { #GetSharedSourceIndex data-toc-label="GetSharedSourceIndex" }

Gets the shared source index. Shared source files are always accessible by both the client and the server. Returns a [SourceIndex].

```lua
local irisCORE = shared.Core
local Source = irisCORE:GetService("Source")

local SharedSourceIndex: SourceIndex = Source:GetSharedSourceIndex()
local MyCoolPackage = SharedSourceIndex:GetPackage("MyCoolPackage")
```