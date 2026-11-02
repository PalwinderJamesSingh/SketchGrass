# SketchGrass 2.9.0 — Interoperability & Data Exchange

## New in 2.9.0

### Versioned `.sgx` interchange
- Added schema version 1 for a portable JSON-based exchange package.
- Export includes the parametric definition (nodes, wires, node parameter values), required component IDs, component metadata, unit and coordinate-system metadata, and evaluated geometry snapshot.
- Import performs schema validation and shows a compatibility report listing unrecognized component types before replacing the current graph.
- Unsupported component nodes are skipped by the existing project loader after the user confirms; compatible nodes and wires are retained.
- Geometry-only `.sgx` files can be imported as a new Geometry Input parameter node for downstream modeling.

### Geometry Input component
- New parameter component for imported geometry snapshots.
- Can output supported point, line, polyline, face, circle, and extrusion boundary values for connection to the graph.

### Safety and validation
- Validates exchange format and schema version.
- Limits import files to 50 MB; caps graph and geometry collections.
- Validates supported geometry records and numeric coordinates.
- External package code is never executed by the interchange importer.

## Data contract
- Length unit: metre.
- Coordinate system: right-handed, Z-up, model origin.
- Geometry v1: points, lines, polylines, faces, circles, and extrusion boundaries.
- See `INTERCHANGE_SCHEMA_1.0.md` for schema details and example payload.

## Compatibility boundaries
- `.sgx` is a documented data exchange format, not a live Grasshopper/Rhino or Dynamo integration.
- Native `.gha`/`.ghpy` plug-ins, RhinoCommon dependencies, Dynamo nodes, and arbitrary C#/Python code do not execute in SketchUp.
- Schema v1 does not preserve materials, SketchUp tags, arbitrary NURBS surfaces, or full B-rep/solid-kernel semantics.

## Validation status
- Ruby syntax checks: passed.
- JavaScript syntax checks: passed.
- Exchange schema positive/negative validation tests: passed.
- Export/import data-contract round-trip tests: passed.
- RBZ/source archive integrity checks: passed.
- SketchUp 2023 application runtime tests: **not yet performed**.
