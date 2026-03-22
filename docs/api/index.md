# Root API

## Overview

***

## Properties

### Source <small><Folder\></small> { #Source data-toc-label="Source" }
Read Only
{ .flag .plain }

Hidden
{ .flag .plain }

References the current script conext source `Folder`. This folder contains all the source files for the current script context. For example, if the script is running on the server, this folder will contain all the server source files.

***

## Methods

### GetService <small><ServiceRoot\></small> { #GetService data-toc-label="GetService" }

Returns the service object for the given service name. If the service does not exist, an error will be thrown. This is the primary way to access irisCORE services.

!!! tip
    This is the recommended way to access services in irisCORE as it ensures that the service exists and is properly initialized.

```lua
local Utility = shared:GetService("Utility")

--> Utility service object
```