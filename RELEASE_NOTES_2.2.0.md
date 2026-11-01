# SketchGrass 2.2.0 — Release Notes

## Scope
Expanded the built-in SketchGrass component library to 55 native component definitions across Params, Maths, Sets, Vector, Curve, Surface, Transform, and Display.

## Added/expanded operations
- Maths: absolute value, square root, power, modulus, average, trigonometric functions, rounding, and clamping.
- Sets: list construction, reverse, sort, cull, dispatch, and weave.
- Vector: deconstruct, unitize, reverse, add, subtract, scale, dot product, and cross product.
- Curve: curve division and length.
- Surface: extrusion.
- Transform: move geometry and scale point.

## Important
This release is an expanded native component foundation, not complete Grasshopper parity. Native Rhino `.gha`, `.ghpy`, and .NET `.dll` packages are not executable in SketchUp; they need to be ported to SketchGrass APIs. The 2.2.0 package has not been runtime-tested inside SketchUp 2023.

## Distribution status
The 2.2.0 RBZ and source ZIP still need to be attached as binary assets. The repository's existing 1.0.0 RBZ is obsolete and is not the 2.2.0 installer.
