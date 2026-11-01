# SketchGrass 2.2.0 — Release Notes

## Included
- 55 built-in component definitions across Params, Maths, Sets, Vector, Curve, Surface, Transform, and Display.
- Node graph editor with draggable nodes, sockets, wires, recomputation, and editable component properties.
- Geometry output for the currently supported native geometry subset.
- .sgproj save/open workflow.
- Declarative .sgp package registry and GHA2SG metadata-inspection scaffold.

## Added/expanded component families
- Maths: absolute value, square root, power, modulus, average, trigonometry, rounding, and clamping.
- Sets: list construction, reverse, sort, cull, dispatch, and weave.
- Vector: deconstruct, unitize, reverse, add, subtract, scale, dot product, and cross product.
- Curve: line between points, curve division, and curve length.
- Surface: extrusion.
- Transform: move geometry and scale point.

## Distribution
The repository includes the SketchGrass_2.2.0.rbz installer. The source archive is for developers and is not required to install the extension.

## Known limitations
This is an expanded native component foundation, not complete Grasshopper parity. Native Rhino .gha, .ghpy, and .NET .dll packages are not executable in SketchUp. GHA2SG only performs heuristic metadata inspection and generates a scaffold; every component needs a reviewed native implementation. The package registry accepts a limited operation allowlist, not arbitrary component code.

Data trees, NURBS, advanced mesh/solid operations, broad surface/intersection tools, automatic code translation, and a general third-party SDK are not implemented.

## Testing status
Static syntax/archive checks are documented in the source package. The manual SketchUp 2023 acceptance checklist remains outstanding; do not treat this release as fully runtime-verified.
