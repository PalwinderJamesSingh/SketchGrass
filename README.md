# SketchGrass 1.0.0

Independent Grasshopper-inspired visual parametric modeling extension for SketchUp 2023. No Rhino or Grasshopper installation required.

## Download
The installer is provided as `SketchGrass_1.0.0.rbz` in this repository.

## Install
1. Open SketchUp 2023.
2. Open Extension Manager.
3. Choose Install Extension and select the RBZ file.
4. Open Extensions > SketchGrass.

## Current scope
Includes a classic-style node editor, basic numeric nodes, point and line construction, SketchUp geometry output, and a declarative `.sgp` component package manager.

## Compatibility note
Native Rhino Grasshopper `.gha` and `.ghpy` plugins cannot run directly in SketchUp. They must be ported to the SketchGrass component API. Installed `.sgp` declarations are validated and stored, but dynamic registration/execution is a later milestone.

## Limitations
This is a 1.0 foundation build. Geometry output currently supports construction points and straight lines. Advanced data trees, curves, surfaces, solids, scripting, graph persistence, undo/redo, and dynamic third-party component execution are not included. Runtime testing in SketchUp 2023 remains necessary.