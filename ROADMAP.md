# SketchGrass Development Roadmap

**Current baseline:** 2.6.0 — Advanced Geometry Engine  
**Target platform:** SketchUp 2023

This roadmap describes the intended development sequence. A feature is not considered released until it is implemented, validated, documented, and tested in SketchUp.

## Product direction

SketchGrass aims to become an independent visual parametric modeling environment built around SketchUp-native geometry for architecture, structures, and construction. It combines a node-based canvas, reusable components, project management, geometry operations, and domain-specific modeling tools. The core uses the SketchUp Ruby API and HtmlDialog; Rhino is not required for native SketchGrass operations.

## Current release — 2.6.0: Advanced Geometry Engine

**Status: Implemented; static checks completed; SketchUp runtime testing remains outstanding.**

The 2.6.0 baseline includes:
- Loft between two compatible section curves.
- Sweep 1 Rail along a sampled polyline rail.
- Revolve around the world Z axis.
- Offset Polyline for planar XY polylines.
- Linear Array along a translation vector.
- Project to XY at a selected elevation.
- Section at Z for approximate horizontal intersections.
- Earlier architectural primitives: Wall (Linear), Floor Slab, Column Grid, Facade Panel Grid, and Roof Plate.

### Known geometry limitations
- Loft, sweep, and revolve create tessellated SketchUp-native geometry, not exact NURBS surfaces.
- Sweep framing is simplified and may show discontinuities around sharp rail corners.
- Offset does not yet robustly resolve self-intersections or complex joins.
- Section at Z is an approximation, not a robust solid-section or boolean-intersection solver.
- A general-purpose solid kernel, exact surface intersections, fillets, trims, and robust booleans are not part of this release.

## 2.6.1 — Stabilization and reliability

**Priority: Highest | Planned**

Focus: make the existing application dependable before expanding its feature set.

Planned work:
- Runtime-test installation, startup, project selection, recovery, save/load, and update preparation in SketchUp 2023.
- Investigate and resolve the reported white-screen and dialog lifecycle issues.
- Regression-test the node canvas, component finder, wires, sliders, graph evaluation, and geometry output.
- Audit every menu item and connect, implement, or clearly disable incomplete actions.
- Implement a consistent Save All workflow for the SketchGrass definition (.sgproj) and active SketchUp model (.skp).
- Improve error reporting, input validation, and recovery from malformed project files.
- Test autosave timing, recovery snapshots, and startup modal sequencing.
- Document known limitations and provide a repeatable test checklist.

**Exit criteria**
- No known startup-blocking dialog or white-screen regression in the tested SketchUp 2023 environment.
- Core project save, reopen, recovery, and update-preparation workflows pass documented manual tests.
- No visible menu action silently claims to work when it is not implemented.
- Release package passes Ruby/JavaScript syntax and archive-integrity checks.

## 2.7.0 — Architectural Modeling Library

**Priority: High | Planned**

Focus: expand SketchGrass into a practical architectural parametric modeling toolkit.

### Building envelope
- Wall systems with thickness, height, baseline, and alignment controls.
- Door and window openings with configurable dimensions and placement.
- Curtain-wall and storefront grids.
- Facade panelization, louvers, fins, screens, and shading devices.
- Building envelope and facade pattern generators.

### Interior and spatial systems
- Room and space layout primitives.
- Partitions and interior wall systems.
- Floors, ceilings, and modular finish layouts.
- Stairs, ramps, landings, and railings.
- Basic room adjacency and area schedules.

### Roof and landscape architecture
- Flat, pitched, folded, and configurable roof systems.
- Roof framing and panel layouts.
- Canopies, pergolas, and shading structures.
- Paths, steps, terraces, planters, and site furniture.
- Topography-aware placement tools where supported by SketchUp geometry.

**Exit criteria**
- Components expose documented inputs, outputs, units, and valid input ranges.
- Components generate editable SketchUp-native geometry.
- Repeated elements use groups or component instances where appropriate.
- A sample architectural definition demonstrates a coordinated building envelope and spatial system.

## 2.8.0 — Structural and Construction Systems

**Priority: High | Planned**

Focus: provide conceptual structural modeling and construction-oriented assembly tools.

### Structural modeling
- Structural grids and reference axes.
- Columns, beams, braces, and framing members.
- Trusses and configurable space-frame layouts.
- Slabs, basic foundation layouts, and pile/grid placement.
- Structural bay and framing pattern generators.
- Parametric connection and node-location placeholders.

### Construction systems
- Assembly and subassembly generators.
- Modular construction and panel layout tools.
- Basic layer/build-up definitions for walls, floors, and roofs.
- Construction sequence and phase visualization.
- Component counts, lengths, areas, and preliminary quantity take-offs.
- Model organization by system, level, phase, and assembly.

**Important boundary:** These tools are intended for geometric modeling, coordination, and preliminary quantity workflows. They are not a substitute for structural analysis, engineering design, code compliance, connection design, or professional construction documentation.

**Exit criteria**
- Structural and construction components generate consistent, editable geometry.
- Units and quantity calculations are documented and tested against sample models.
- Model outputs can be organized and filtered by system and construction phase.
- Engineering limitations are visible in the documentation and interface.

## 2.9.0 — Interoperability and Data Exchange

**Priority: Medium-High | Planned**

Focus: exchange supported parametric data with other design tools without promising unsupported plug-in execution.

Planned work:
- Define a versioned, documented SketchGrass interchange format.
- Support structured geometry and parameter exchange through formats such as JSON and supported geometry files.
- Improve import/export workflows for SketchUp-native geometry.
- Explore a Grasshopper companion workflow for exchanging supported data with Rhino/Grasshopper.
- Explore Dynamo data exchange for supported geometry and parameters.
- Add component metadata inspection and compatibility reporting.
- Provide migration and validation tools for older SketchGrass project files.

### Compatibility boundaries
- Native Rhino .gha and .ghpy plug-ins do not execute directly inside SketchUp's Ruby environment.
- Arbitrary compiled Grasshopper plug-ins, RhinoCommon dependencies, and Python/C# scripts cannot be universally translated into SketchGrass components.
- Interoperability will focus on documented data exchange, supported definitions, and purpose-built adapters.

**Exit criteria**
- Interchange schema and supported data types are documented.
- Import/export tests cover supported geometry, units, and parameter values.
- Unsupported content produces clear warnings rather than being silently discarded.

## 3.0.0 — Complete Parametric Studio

**Priority: Long-term | Planned**

Focus: mature the modeling environment into an extensible parametric platform.

Planned work:
- More capable data trees and structured list operations.
- Reusable definitions, clusters, and nested graphs.
- Custom component authoring and a documented component SDK.
- Package manager for installing, updating, enabling, and removing component packages.
- Component search, categories, favorites, and dependency reporting.
- Improved graph evaluation, caching, and performance for larger definitions.
- Project versioning, migration, backups, and recovery tools.
- Expanded documentation, examples, and learning resources.
- Optional collaboration and definition-sharing workflows.

**Exit criteria**
- Users can author, package, install, and share custom components through a documented workflow.
- Project and component version compatibility is managed explicitly.
- Larger definitions have predictable evaluation and recovery behavior.
- The core application has a maintained test suite and release process.

## Cross-version systems

| System | Ongoing responsibility |
|---|---|
| Node Canvas | Graph editing, wires, selection, navigation, grouping, and evaluation feedback |
| Component Browser | Search, categories, documentation, favorites, and placement |
| Geometry Engine | Native geometry generation, validation, and performance |
| Project Manager | New/open/save, recent projects, autosave, recovery, and version migration |
| Update Manager | Safe package staging, compatibility checks, and user-controlled installation |
| Package Manager | Third-party component packages, dependencies, and versioning |
| Documentation | Component reference, user guide, release notes, and sample projects |

## Recommended implementation order

1. Stabilize and runtime-test the 2.6.0 baseline in SketchUp 2023.
2. Complete the architectural component library.
3. Build structural and construction modeling systems.
4. Add documented interoperability and data exchange.
5. Mature data trees, custom components, package management, and performance for 3.0.0.

## Release and quality policy

A planned milestone is not a release commitment. Before a version is described as released, its implementation should be complete, static checks should pass, the package should be inspected, and supported workflows should be tested in the target SketchUp version. Untested areas and known limitations must be stated in release notes.

**Current verification note:** 2.6.0 has passed the reported Ruby/JavaScript syntax and ZIP integrity checks, but has not yet been runtime-tested inside SketchUp 2023.
