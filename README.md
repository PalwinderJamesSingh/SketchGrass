# SketchGrass 2.6.1

Independent Grasshopper-inspired visual parametric modeling extension for **SketchUp 2023**. Built with the SketchUp Ruby API and HtmlDialog; Rhino is not required for native SketchGrass operations.

## Current build: 2.6.1 — Stabilization and Project Safety

This update hardens project validation and named-project saving while retaining the 2.6.0 geometry engine. Project data is validated and written to a temporary file before replacing the current save; a `.bak` copy of the previous named `.sgproj` is retained. Graph size and node/wire structure are validated before loading or saving.

### Geometry components retained from 2.6.0
Loft, Sweep 1 Rail, Revolve, Offset Polyline, Linear Array, Project to XY, and Section at Z, plus Wall (Linear), Floor Slab, Column Grid, Facade Panel Grid, and Roof Plate. Loft, sweep, and revolve create tessellated SketchUp-native geometry, not NURBS surfaces. Offset and section operations remain approximate.

## Documentation
- [Development roadmap](./ROADMAP.md)
- [2.6.1 release notes](./RELEASE_NOTES_2.6.1.md)
- [2.6.0 geometry release notes](./RELEASE_NOTES_2.6.0.md)

## Compatibility and testing
**Target:** SketchUp 2023. Ruby/JavaScript syntax checks and archive integrity checks passed. This package has **not** been runtime-tested inside SketchUp 2023. The updater stages packages but does not force-restart SketchUp; install staged updates manually through Extension Manager after closing SketchUp normally. Test on copies of important models before production use.

## Creator
**Palwinder James Singh** — School of Architecture, National University Philippines; Creator & Developer of SketchGrass.
