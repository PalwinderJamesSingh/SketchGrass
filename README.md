# SketchGrass 2.9.0 — Interoperability & Data Exchange

Independent Grasshopper-inspired visual parametric modeling extension for **SketchUp 2023**. SketchGrass uses the SketchUp Ruby API and HtmlDialog; Rhino is not required for native SketchGrass operations.

## Current build: 2.9.0

This release introduces a versioned `.sgx` interchange format for sharing a SketchGrass graph definition, component requirements and metadata, parameter values, units, coordinate-system metadata, and an evaluated geometry snapshot.

### 2.9.0 highlights
- Export a complete definition and evaluated geometry snapshot to `.sgx` JSON.
- Import `.sgx` files with a compatibility report for missing component types.
- Import supported geometry-only exchange files through the new **Geometry Input** parameter component.
- Explicit schema versioning (`schema_version: 1`), metre-based length units, right-handed coordinates, and Z-up convention.
- File validation, geometry-type checks, and a 50 MB import safety limit.
- Documented interchange schema for future Grasshopper/Rhino and Dynamo adapters.

### Important interoperability boundary
The `.sgx` format is a data-exchange contract, not a live integration. It does not execute `.gha`, `.ghpy`, RhinoCommon, Dynamo, C#, or Python plug-ins inside SketchUp. External tools must implement an adapter that reads/writes the documented JSON schema. The current geometry exchange supports points, lines, polylines, planar faces, circles, and extrusion boundary data. Materials, native SketchUp tags, arbitrary NURBS surfaces, and full solid-B-rep semantics are not part of schema v1.

## Install
1. Close SketchUp normally.
2. In SketchUp 2023, open **Extension Manager → Install Extension**.
3. Select `SketchGrass_2.9.0.rbz`.
4. Reopen SketchUp and open SketchGrass from the Extensions menu or toolbar.

Back up important `.sgproj` and `.skp` files before updating.

## Interchange workflow
- **File → Export Interchange (.sgx)** writes the current graph, component metadata, parameter records, and the latest evaluated geometry snapshot.
- **File → Import Interchange (.sgx)** validates the schema and displays a component compatibility report before replacing the current definition.
- A geometry-only file (an empty definition plus a geometry array) creates a **Geometry Input** node so the imported geometry can be connected to downstream components.

See [Interchange Schema 1.0](./INTERCHANGE_SCHEMA_1.0.md) for the exact format.

## Previous capabilities retained
The 2.7.x/2.8.x architecture, structural, construction, parametric modeling library, animated component guide, per-socket connection recommendations, and pre-generation geometry preview are retained.

## Testing and limitations
Ruby and JavaScript static syntax checks, interchange schema validation, round-trip payload tests, and archive integrity checks passed. These checks do not replace runtime validation inside SketchUp 2023. No direct Grasshopper/Rhino or Dynamo application connection is claimed. Structural components remain conceptual geometry, not structural analysis or engineering design. The modeling kernel remains tessellated and does not provide a general NURBS or B-rep solid engine.

## Creator
**Palwinder James Singh** — School of Architecture, National University Philippines; Creator & Developer of SketchGrass.
