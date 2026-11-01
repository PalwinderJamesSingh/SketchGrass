# SketchGrass 2.5.2 — Architectural Component Library Foundation

## Added
- **Wall (Linear):** generates a straight wall from start/end points, height and thickness.
- **Floor Slab:** creates a rectangular slab with thickness.
- **Column Grid:** generates a regular point grid from bay counts and spacings.
- **Facade Panel Grid:** subdivides a planar facade into rectangular panels.
- **Roof Plate:** creates a planar roof plate at a specified elevation.

## Modeling notes
- Coordinates and dimensional inputs are in meters.
- Grid counts and facade subdivisions are capped to protect responsiveness.
- Geometry is generated through the existing SketchUp-native output pipeline.
- These are foundational schematic components, not construction-documentation or structural-analysis tools.
- Wall, slab and panel geometry is basic planar geometry; no openings, joins, material assignment, reinforcement, load analysis or code checking is included.

## Validation
- Ruby and JavaScript syntax checks and RBZ archive integrity checks passed.
- Not runtime-tested inside SketchUp 2023; test on a copy of your model before production use.
