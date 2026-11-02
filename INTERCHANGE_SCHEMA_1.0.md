# SketchGrass Interchange Schema 1.0 (`.sgx`)

The `.sgx` format is a UTF-8 JSON data contract for moving supported SketchGrass definitions and geometry between applications. It is not an executable plug-in format.

## Top-level fields

| Field | Type | Required | Meaning |
|---|---|---:|---|
| `format` | string | yes | Must be `sketchgrass-interchange`. |
| `schema_version` | integer | yes | Must be `1`. |
| `application` | object | yes | Producer name and version. |
| `created_at` | ISO-8601 string | no | Export timestamp. |
| `units` | object | yes | `length: meter`, `angle: degree`. |
| `coordinate_system` | object | yes | `handedness: right`, `up_axis: Z`, `origin: model`. |
| `definition` | object | yes | A SketchGrass project envelope with `format`, `format_version`, `nodes`, and `wires`. For geometry-only exchanges, use empty node and wire arrays. |
| `required_components` | string array | no | Component type identifiers needed to evaluate the definition. |
| `component_catalog` | object array | no | Component title, category, description, input and output socket labels. |
| `parameters` | object array | no | A normalized index of parameter-node values; the complete values also remain in `definition.nodes[].props`. |
| `geometry` | object array | yes | Evaluated geometry snapshot in model metres. |

## Supported geometry records

All points use numeric `x`, `y`, and `z` values in metres.

```json
{
  "format": "sketchgrass-interchange",
  "schema_version": 1,
  "application": {"name": "External Adapter", "version": "1.0"},
  "units": {"length": "meter", "angle": "degree"},
  "coordinate_system": {"handedness": "right", "up_axis": "Z", "origin": "model"},
  "definition": {
    "format": "sketchgrass-project",
    "format_version": 1,
    "nodes": [],
    "wires": [],
    "next_id": 1,
    "canvas": {"scale": 1, "pan_x": 0, "pan_y": 0}
  },
  "required_components": [],
  "component_catalog": [],
  "parameters": [],
  "geometry": [
    {"kind": "point", "x": 0, "y": 0, "z": 0},
    {"kind": "line", "a": {"x": 0, "y": 0, "z": 0}, "b": {"x": 5, "y": 0, "z": 0}},
    {"kind": "polyline", "closed": false, "points": [{"x": 0, "y": 0, "z": 0}, {"x": 5, "y": 0, "z": 0}]},
    {"kind": "face", "points": [{"x": 0, "y": 0, "z": 0}, {"x": 5, "y": 0, "z": 0}, {"x": 5, "y": 4, "z": 0}]},
    {"kind": "circle", "center": {"x": 0, "y": 0, "z": 0}, "radius": 2, "segments": 36},
    {"kind": "extrusion", "base": [{"x": 0, "y": 0, "z": 0}, {"x": 2, "y": 0, "z": 0}, {"x": 2, "y": 2, "z": 0}], "top": [{"x": 0, "y": 0, "z": 3}, {"x": 2, "y": 0, "z": 3}, {"x": 2, "y": 2, "z": 3}]}
  ]
}
```

Supported `kind` values are `point`, `line`, `polyline`, `face`, `circle`, and `extrusion`. An extrusion is represented as matching `base` and `top` point loops. It is boundary data, not a guaranteed watertight solid or B-rep.

## Graph exchange

`definition.nodes` entries use SketchGrass component type IDs and node properties. `definition.wires` entries connect `{node, index}` endpoints under `from` and `to`. Importers should preserve unknown fields when practical. SketchGrass checks component IDs against locally available components; unknown nodes are reported and omitted only after user confirmation.

## Geometry-only import

For a geometry-only exchange from another application, set `definition.nodes` and `definition.wires` to empty arrays and populate `geometry`. SketchGrass imports the geometry into a **Geometry Input** parameter component. The geometry can then be wired to supported downstream components.

## Adapter responsibilities

A Grasshopper/Rhino or Dynamo adapter must translate its own native geometry and parameter data into this JSON contract. Coordinate transformations and units must be explicit. Adapters should not assume that SketchGrass can run external plug-in code. Schema version changes will be additive where possible; incompatible changes require a new `schema_version`.

## Current limitations

Schema v1 does not encode materials, layers/tags, object styles, arbitrary NURBS surfaces, trim loops, mesh topology metadata, or full solid/B-rep semantics. Graph definitions using external or locally unavailable components can only be partially imported.
