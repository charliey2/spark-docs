# Setup

## Project Format

!!! note "Source Management Only"
    irisCORE is only used for managing source files, such as scripts, modules, and packages. All 3D world-related things and interface objects should be managed from within Roblox Studio.

```bash
.
└── DataModel/
    ├── ReplicatedStorage/
    │   └── irisSHARED/
    │       └── Source/
    │           ├── Modules
    │           ├── Packages # Read Only (Package manager)
    │           └── Services # Read Only
    ├── ServerScriptService/
    │   └── irisSERVER/
    │       └── Source/
    │           ├── Modules
    │           ├── Packages # Read Only (Package manager)
    │           └── Scripts
    └── StarterPlayer/
        └── StarterPlayerScripts/
            └── irisCLIENT/
                └── Source/
                    ├── Modules
                    └── Scripts
```

## Definitions

### Module

A collection of functions and variables that can be included in other scripts. These are written by the developer and not imported using a package manager.

### Package

A collection of modules that are imported using a package manager. These should not be manually inserted or modified.

!!! danger
    Packages should never make references to game modules or services. This can result in circular dependencies and stack overflows.

### Service

Systems built into irisCORE and Roblox that provide functionality to other scripts. They should not be modified by the developer.

!!! warning
    Services should not be modified or overridden. Doing so can cause unexpected behavior and break the game. If you need to modify a service, create a module that interacts with the service instead.