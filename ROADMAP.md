# SketchGrass Roadmap — Version Manager

## Planned for SketchGrass 2.3.0

The next release is planned to include an in-app **Version Manager** and **Automatic Project Saving**.

### Automatic Project Saving
- Automatically save the active `.sgproj` graph after edits, using a short debounce so continuous slider dragging does not write the file on every mouse movement.
- Also run a configurable periodic save (default target: every 30 seconds) while the graph is dirty.
- For projects that have already been saved, update the existing project file safely using a temporary file and atomic replacement where supported.
- For a new, never-saved graph, write recovery copies to a dedicated SketchGrass autosave/recovery folder; do not silently choose a user-facing project filename or overwrite an unrelated file.
- Show a clear status in the editor: **Saved**, **Saving…**, or **Unsaved changes**.
- Provide settings to enable/disable autosave and adjust the interval.
- Keep a small rolling set of recovery snapshots (target: last 5) and offer recovery after an unexpected SketchUp/editor shutdown.
- Preserve the normal **Save** and **Save As** commands; autosave is a safety net, not a replacement for deliberate project management.
- Autosave the `.sgproj` graph data only. Saving the SketchUp model geometry still requires saving the `.skp` model in SketchUp.
- Avoid writing when the graph has not changed, and handle write failures without marking the project as saved.

### User interface
- Add an **Update** button in the SketchGrass main toolbar or settings area.
- Open a Version Manager panel showing the installed version and available releases.
- Let the user choose a release from a version list, including older compatible releases.
- Clearly label the actions as **Upgrade** or **Downgrade** based on the selected version.
- Show release date, change notes, SketchUp compatibility, and known migration warnings before confirmation.

### Update and rollback safety
1. Fetch a release manifest from the official SketchGrass GitHub repository over HTTPS.
2. Show only published, supported releases; do not silently install prerelease builds.
3. Verify the downloaded installer against a published SHA-256 checksum before staging it.
4. Ask for explicit confirmation before changing versions.
5. Back up the currently installed SketchGrass files and version metadata before replacing anything.
6. Stage the selected version and apply it at a safe restart/install point. If SketchUp does not allow a safe in-process replacement, guide the user through Extension Manager rather than force-replacing loaded Ruby files.
7. Keep a recovery copy and provide a **Restore previous version** action if the new build fails.
8. Warn when opening a project saved by a newer version or when downgrading could affect project compatibility.

### Version selection
- **Latest stable:** install the newest stable compatible release.
- **Choose version:** select a specific older or newer published release.
- **Downgrade confirmation:** explain that newer project features may not be available in the selected older version.
- **Cancel:** leave the current installation untouched.

### Release publishing requirements
For the Version Manager to work, each release must be published consistently on GitHub with:
- A version tag such as `v2.3.0`.
- A release title and change log.
- A SketchUp-compatible `.rbz` asset.
- A SHA-256 checksum for that exact asset.
- A manifest entry containing version, download URL, checksum, release notes URL, minimum/maximum SketchUp compatibility, and stable/prerelease status.

The Version Manager must not treat a source ZIP, arbitrary repository file, or unverified download as an installer.

### Security and compatibility
- Do not execute downloaded Ruby, DLL, GHA, or GHPY code directly from the network.
- Do not load Rhino/Grasshopper assemblies.
- Never downgrade automatically.
- Never overwrite the current install before the backup and checksum verification succeed.
- Keep the user in control: no silent updates, no forced downgrade, and no deletion of user .sgproj files.

## Component Package Ecosystem and Interoperability

### Expanded native component library
Build a larger, modular library focused on practical architectural and computational-design workflows. Priority families:
- **Geometry parameters:** planes, frames, boxes, vectors, meshes, faces, edges, solids, text, materials, and model/entity references.
- **Math and domains:** trigonometry, expressions, interpolation, remapping, statistics, matrices, and unit conversion.
- **Lists and data trees:** graft, flatten, simplify, path mapping, merge, partition, dispatch, cull patterns, and tree/list inspection.
- **Curve tools:** offsets, fillets, joins, trims, intersections, projections, frames, tangents, curvature sampling, and curve division.
- **Surface and solid tools:** loft, sweep, revolve, planar surface, boundary surface, offset, thicken, boolean operations, shell, and sectioning, subject to SketchUp API geometry limits.
- **Mesh tools:** mesh creation, triangulation, subdivision utilities, normals, face/vertex extraction, and mesh transforms.
- **Transform and array tools:** rotate, mirror, orient, align, polar/rectangular arrays, attractor transforms, and pattern placement.
- **Architectural generators:** grids, panels, louvers, fins, mullions, shading systems, stairs, ramps, trusses, space frames, room/area layouts, and component-based assemblies.
- **Analysis and documentation:** dimensions, area/volume summaries, sun/shadow inputs where available, schedules, labels, reports, and geometry diagnostics.
- **Model integration:** tags/layers, materials, component definitions/instances, attributes, scene/camera helpers, and controlled read/write of SketchUp model entities.

Each new component must document its inputs, outputs, units, supported geometry, error behavior, and test cases. Do not advertise a component as implemented until its operation is registered and tested.

### Native package ecosystem
- Establish a documented **SketchGrass Component SDK** and versioned package manifest.
- Support installable component bundles (proposed `.sgpkg`) containing a manifest, component definitions, icons, documentation, compatibility metadata, and dependency declarations.
- Add package manager actions: browse/import, install, enable/disable, update, uninstall, dependency inspection, conflict detection, and package validation.
- Provide package signing/checksum verification and explicit trust prompts.
- Support a safe declarative component format first; add reviewed native adapters for trusted Ruby implementations. Do not execute arbitrary downloaded scripts or binaries.
- Allow third-party developers to publish independently versioned component packs, with per-package compatibility declarations for SketchUp and SketchGrass versions.

### Connecting to other parametric plugins
Create a public **Parametric Interoperability API** so SketchGrass can exchange data and geometry with other SketchUp extensions and external parametric tools through adapters:
- A stable typed data contract for numbers, booleans, strings, points, vectors, planes, curves, surfaces, meshes, lists, and nested data paths.
- Import/export through documented JSON-based graph/data exchange, plus geometry exchange using supported neutral formats when appropriate.
- A SketchUp extension bridge/API for other Ruby plugins to register providers, expose operations, send typed inputs/outputs, and request controlled model-geometry access.
- Adapter packages for specific third-party tools only after their public APIs and licensing allow integration.
- Clear source/target mapping, unit and coordinate-system handling, version negotiation, and actionable errors when a data type cannot be represented.
- Optional live-link sessions with explicit user approval, connection status, and manual/automatic recompute controls.

**Compatibility boundary:** this is an interoperability layer, not a promise that every parametric plugin can be connected automatically. Each external plugin needs a supported public API or file/data exchange route and, where necessary, a dedicated adapter. Rhino Grasshopper `.gha`/`.ghpy`/`.dll` packages still cannot run directly inside SketchGrass; compatible functionality must be ported or bridged through an explicitly supported integration.

## Status
**Planned — not included in SketchGrass 2.2.0.** This roadmap records requested future capabilities; it is not a claim that the updater, autosave, expanded SDK, or interoperability bridge already exists.
