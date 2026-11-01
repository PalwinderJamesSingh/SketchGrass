# SketchGrass 2.6.0

Independent Grasshopper-inspired visual parametric modeling extension for **SketchUp 2023**. Built with the SketchUp Ruby API and HtmlDialog; Rhino is not required.

## 2.6.0 — Advanced Geometry Engine

Adds seven curve, surface and transformation components:

- **Loft:** creates a quad-strip surface between two section curves.
- **Sweep 1 Rail:** sweeps a profile along a sampled polyline rail.
- **Revolve:** creates a rotational surface around the world Z axis.
- **Offset Polyline:** offsets a planar XY polyline.
- **Linear Array:** creates translated copies along a vector.
- **Project to XY:** projects supported geometry onto a selected elevation.
- **Section at Z:** extracts approximate intersections at a horizontal elevation.

These operations generate SketchUp-native faces, edges and points. Loft, sweep and revolve are tessellated polygon approximations, not NURBS surfaces. Offset and section operations have documented geometric limitations; this is not a general-purpose solid modeling kernel.

## Previous architecture components

Wall (Linear), Floor Slab, Column Grid, Facade Panel Grid and Roof Plate remain available.

## Downloads and documentation
- [2.6.0 release notes](./RELEASE_NOTES_2.6.0.md)
- [User guide](./USER_GUIDE.md)
- [Component reference](./COMPONENT_REFERENCE.md)
- [Roadmap](./ROADMAP.md)

The 2.6.0 installer and source archive are distributed with the release package. A GitHub binary release asset is not published.

## Compatibility and testing
Target: SketchUp 2023. Ruby and JavaScript syntax checks and ZIP integrity checks passed. This package has **not** been runtime-tested inside SketchUp 2023. Test on a copy of your model before production use.

## Creator
**Palwinder James Singh** — School of Architecture, National University Philippines; Creator & Developer of SketchGrass.
