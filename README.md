# SketchGrass 2.2.0

Independent Grasshopper-inspired visual parametric modeling extension for SketchUp 2023. SketchGrass is built with the SketchUp Ruby API and HtmlDialog; it does not require Rhino.

## Latest version

**Version:** 2.2.0  
**Target:** SketchUp 2023  
**Component library:** 55 built-in native component definitions across 8 categories.

### Component categories

| Category | Components |
|---|---:|
| Params | 5 |
| Maths | 18 |
| Sets | 10 |
| Vector | 10 |
| Curve | 6 |
| Surface | 2 |
| Transform | 3 |
| Display | 1 |
| **Total** | **55** |

The expanded library includes numeric operations, list operations, vector construction and analysis, basic curve construction and division, rectangle/extrusion tools, point and geometry transforms, and geometry output.

## Download

The 2.2.0 installer and source archive are not yet attached to this repository. The existing `SketchGrass_1.0.0.rbz` is an older build and must **not** be used as the 2.2.0 installer. A direct binary upload is still required before this repository can provide a one-click 2.2.0 download.

## Install (once the 2.2.0 RBZ is available)

1. Open SketchUp 2023.
2. Open **Extension Manager**.
3. Choose **Install Extension** and select `SketchGrass_2.2.0.rbz`.
4. Open **Extensions > SketchGrass**.

## Compatibility and limitations

- SketchGrass reimplements supported operations using the SketchUp Ruby API; it does not host Rhino or Grasshopper.
- Native Rhino Grasshopper `.gha`, `.ghpy`, and .NET `.dll` files cannot be executed directly. They require dependency inspection and a native port.
- The 55-component count describes the current built-in library definitions, not full Grasshopper parity.
- Advanced data trees, NURBS, robust mesh/solid algorithms, broad surface operations, and full third-party component SDK compatibility remain future work.
- The 2.2.0 build has not been runtime-verified in SketchUp 2023. Test on a copy of a model before production use.

## Development history

- 1.0.0 — initial node editor and basic geometry.
- 2.0.0 — expanded graph editor, geometry, and project persistence.
- 2.1.0 — native component registry and GHA/GHPY metadata inspection/scaffolding.
- 2.2.0 — expanded built-in component library.
