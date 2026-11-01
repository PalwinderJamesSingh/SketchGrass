# SketchGrass 2.6.0 — Advanced Geometry Engine

## New components
- **Loft:** quad-strip surface between two compatible section curves; section curves are resampled to matching point counts.
- **Sweep 1 Rail:** sweeps a profile along a polyline rail using sampled translation frames.
- **Revolve:** rotational surface around the world Z axis, with angle and segment controls.
- **Offset Polyline:** planar XY offset for polyline geometry.
- **Linear Array:** creates translated copies along a vector.
- **Project to XY:** projects supported points, lines, polylines and faces to a selected elevation.
- **Section at Z:** extracts approximate line intersections at a horizontal elevation from supported geometry vertex sequences.

## Limits and modeling notes
- Geometry is represented as SketchUp-native faces, edges and points. Loft, sweep and revolve generate tessellated polygon strips; they are not NURBS surfaces.
- Sweep uses translation along the rail and does not yet calculate full rotation-minimizing frames; sharp corners may produce discontinuities.
- Offset is a planar XY operation; it does not resolve self-intersections or complex joins.
- Section extraction is an approximate vertex-sequence method, not a robust boolean section solver.
- No general-purpose solid boolean, fillet, trim, join, NURBS kernel, or exact surface intersection is included in this release.
- Tessellation and copy counts are capped to help protect SketchUp responsiveness.

## Compatibility and validation
Target: SketchUp 2023. Ruby and JavaScript syntax checks and RBZ archive integrity checks passed. It has not been runtime-tested inside SketchUp 2023; test on a copy of your model before production use.
