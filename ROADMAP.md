# SketchGrass Development Roadmap

**Current build:** 2.9.0 — Interoperability & Data Exchange  
**Target platform:** SketchUp 2023

A feature is considered released only when implemented, documented, validated, and tested in the target SketchUp version. Static checks do not replace SketchUp runtime testing.

## Delivered — 2.9.0: Interoperability & Data Exchange
- Versioned `.sgx` interchange format (`schema_version: 1`).
- Export of graph nodes/wires, required component IDs, component metadata, parameter values, unit/coordinate metadata, and evaluated geometry snapshot.
- Import with schema validation, compatibility report, and unsupported-component handling.
- Geometry-only import through the Geometry Input parameter component.
- Metre units, right-handed coordinate system, Z-up axis, and documented supported geometry schema.
- 50 MB file-size limit and structural validation of supported geometry records.
- Interchange schema documentation for third-party adapter authors.

**Boundary:** this release provides a documented data-exchange contract, not live Grasshopper/Rhino or Dynamo execution. Third-party plug-ins and their code are not executed or automatically translated. Schema v1 supports points, lines, polylines, planar faces, circles, and extrusion boundary data; full NURBS/B-rep semantics and materials/tags are outside its scope.

## Delivered — 2.8.3: Animated Guide & Output Preview
- Per-input suggested source components and per-output downstream recommendations.
- Add-and-connect workflows.
- Schematic preview and geometry summary before generating into SketchUp.

## Delivered — 2.8.2: Animated Component Guide & Connection Assistant
- Searchable guide metadata for component purpose, sockets, defaults, and animated data flow.
- Connection assistant for missing inputs and unused outputs.

## Delivered — 2.8.1: Component Browser Fix
- Corrected the component-definition separator that prevented the 2.8.0 browser from initializing.
- Restored the ALL view and category counts.

## Delivered — 2.8.0: Advanced Parametric & Modeling Tools
- Graph mapping, attractor falloff, list operations, curve evaluation and sampling, arrays, transformations, panelization, adaptive facade tools, tower massing, spiral stairs, and conceptual space frames.

## Delivered — 2.7.0: Architecture, Structure & Construction Suite
- Architectural building elements and façade systems.
- Structural grids, columns, beams, trusses, and conceptual framing.
- Construction assemblies, phases, and preliminary quantity reporting.

## 3.0.0 — Complete Parametric Studio (planned)
- Hierarchical data trees and structured list operations.
- Reusable definitions, clusters, and nested graphs.
- Custom component authoring and a documented SDK.
- Package manager, dependency/version compatibility, and component publishing.
- Graph evaluation caching, diagnostics, and large-definition performance.
- Project revision history, migration, backups, and recovery improvements.

## Cross-version priorities
| System | Responsibility |
|---|---|
| Node Canvas | Graph editing, wires, grouping, evaluation feedback |
| Component Browser | Search, categories, documentation, favorites, placement |
| Geometry Engine | Native geometry generation, validation, performance |
| Interchange | Versioned schema, import/export, adapter compatibility |
| Project Manager | Save/load, autosave, recovery, migration |
| Update Manager | Safe staging and user-controlled installation |

## Release quality policy
Before describing a version as runtime-verified, test installation, startup, save/load, recovery, graph evaluation, geometry preview/generation, and interchange workflows inside SketchUp 2023. State all untested areas and limitations in release notes.
