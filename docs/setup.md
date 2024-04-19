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

### Service

Systems built into irisCORE and Roblox that provide functionality to other scripts. They should not be modified by the developer.