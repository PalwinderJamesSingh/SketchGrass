# SketchGrass 2.6.1 — Stabilization and Project Safety

## Improvements
- Unified the extension registration, toolbar, menu, workspace, and project metadata version to 2.6.1.
- Hardened project validation: project data must be an object; nodes and wires must be arrays of objects; excessive graph sizes are rejected with clear errors.
- Improved named-project save safety: validate and serialize before replacing the destination, write and verify a temporary file, and retain a `.bak` copy of the previous named project.
- Updated the What's New dialog and release-history link for 2.6.1.
- Retained all 2.6.0 geometry components and architectural primitives.

## Important limitations
- The backup is for named `.sgproj` project saves. It does not back up the SketchUp `.skp` model.
- Save All across `.sgproj` and `.skp` is not implemented as a single atomic transaction.
- The updater stages packages and requires the user to close SketchUp normally and install through Extension Manager; it does not automatically restart SketchUp.
- This release has not been runtime-tested inside SketchUp 2023.

## Validation performed
- Ruby syntax checks for all Ruby source files.
- JavaScript syntax checks for the application script and inline scripts.
- RBZ and source ZIP integrity checks.

Static checks do not replace manual installation and workflow testing in SketchUp 2023. Test on copies of important projects before production use.
