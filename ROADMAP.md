# SketchGrass Development Roadmap

**Current build:** 2.6.1 — Stabilization and Project Safety  
**Target platform:** SketchUp 2023

The roadmap describes intended development. A feature is not considered fully released until implemented, validated, documented, and tested in the target SketchUp version.

## Product direction

SketchGrass is an independent visual parametric modeling environment built around SketchUp-native geometry for architecture, structures, and construction. The core uses the SketchUp Ruby API and HtmlDialog; Rhino is not required for native SketchGrass operations.

## 2.6.1 — Stabilization and Project Safety

**Status: Code update implemented; static checks passed; SketchUp runtime testing outstanding.**

- Unified extension registration, toolbar, menu, workspace, and project metadata version.
- Strengthened project validation for object structure and graph size.
- Validates and serializes project data before writing a temporary file.
- Reads back and validates the temporary file before replacing the named project.
- Retains a `.bak` copy of the previous named `.sgproj` save.
- Retains the 2.6.0 geometry and architectural components.

**Limitations:** the backup covers named `.sgproj` files, not the SketchUp `.skp` model. Save All is not an atomic transaction. The updater still requires manual installation through Extension Manager after a normal SketchUp close. This release has not been runtime-tested inside SketchUp 2023.

## 2.7.0 — Architectural Modeling Library

**Planned**

### Building envelope
- Wall systems with thickness, height, baseline, and alignment controls.
- Door and window openings with configurable dimensions and placement.
- Curtain-wall and storefront grids.
- Facade panelization, louvers, fins, screens, and shading devices.
- Building envelope and facade pattern generators.

### Interior and spatial systems
- Room and space layout primitives.
- Partitions, interior wall systems, floors, ceilings, and modular finish layouts.
- Stairs, ramps, landings, and railings.
- Basic room adjacency and area schedules.

### Roof and landscape architecture
- Flat, pitched, folded, and configurable roof systems.
- Roof framing and panel layouts, canopies, and pergolas.
- Paths, terraces, planters, site furniture, and topography-aware placement tools.

**Exit criteria:** documented inputs/outputs/units; editable SketchUp-native geometry; repeatable sample definitions; tested component behavior.

## 2.8.0 — Structural and Construction Systems

**Planned**

- Structural grids, columns, beams, braces, trusses, and space frames.
- Slabs, basic foundation layouts, and pile/grid placement.
- Parametric connection and node-location placeholders.
- Assemblies and subassemblies; modular construction and panel layouts.
- Basic wall/floor/roof build-ups.
- Construction sequence and phase visualization.
- Preliminary component counts, lengths, areas, and quantity take-offs.
- Organization by system, level, phase, and assembly.

**Boundary:** these are geometric modeling and preliminary coordination tools, not structural analysis, engineering design, code compliance, connection design, or professional construction documentation.

## 2.9.0 — Interoperability and Data Exchange

**Planned**

- Versioned SketchGrass interchange format.
- Structured geometry and parameter exchange through supported formats.
- Improved SketchUp-native geometry import/export.
- Explore purpose-built Grasshopper/Rhino companion and Dynamo data-exchange workflows.
- Component metadata inspection, compatibility reports, and project migration tools.

**Compatibility boundary:** native `.gha` and `.ghpy` plug-ins do not execute directly in SketchUp's Ruby environment. Arbitrary compiled plug-ins, RhinoCommon dependencies, and Python/C# scripts cannot be universally translated. Interoperability will focus on documented data exchange and supported adapters.

## 3.0.0 — Complete Parametric Studio

**Planned**

- More capable data trees and structured list operations.
- Reusable definitions, clusters, and nested graphs.
- Custom component authoring and a documented component SDK.
- Package manager for third-party components and dependency management.
- Component search, categories, favorites, and version compatibility.
- Improved graph evaluation, caching, and large-definition performance.
- Project versioning, migration, backups, and recovery.
- Expanded documentation, examples, and optional collaboration workflows.

## Cross-version systems

| System | Ongoing responsibility |
|---|---|
| Node Canvas | Graph editing, wires, selection, navigation, grouping, evaluation feedback |
| Component Browser | Search, categories, documentation, favorites, placement |
| Geometry Engine | Native geometry generation, validation, performance |
| Project Manager | New/open/save, recent projects, autosave, recovery, migration |
| Update Manager | Safe package staging, compatibility checks, user-controlled installation |
| Package Manager | Third-party components, dependencies, versioning |
| Documentation | Component reference, user guide, release notes, sample projects |

## Recommended implementation order

1. Runtime-test and stabilize 2.6.1 in SketchUp 2023.
2. Complete the architectural component library.
3. Build structural and construction modeling systems.
4. Add documented interoperability and data exchange.
5. Mature data trees, custom components, package management, and performance for 3.0.0.

## Release quality policy

Before a version is described as fully verified, test installation, startup, save/load, recovery, geometry generation, and update workflows in the target SketchUp version. Static syntax and archive checks are necessary but do not replace runtime testing. State all untested areas and known limitations in release notes.
