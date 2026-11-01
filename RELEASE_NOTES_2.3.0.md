# SketchGrass 2.3.0 Preview — Release Notes

## Added
- Application menu bar with File, Edit, View, Canvas, Components, Project, Tools, Extensions, and Help entries.
- Help → About Me profile for Palwinder James Singh, School of Architecture, National University Philippines, including the supplied portrait.
- Extensions → Install New Update… to select a local RBZ, validate its ZIP signature, and stage it in the SketchGrass updates folder.
- Extensions → Check for Updates and Version History shortcuts.

## Important updater limitation
This preview does not replace loaded Ruby code in the active SketchUp process. It stages a validated RBZ and informs the user that SketchUp must be restarted before installation. Seamless hot-reload, background downloading, automated rollback, and the full version selector are not implemented.

## Retained capabilities
- Visual node graph editor, category ribbon, and component browser.
- Existing native component library and geometry output.
- `.sgproj` save/open.
- Declarative component package installation and GHA2SG inspection/scaffold workflow.

## Validation
Ruby syntax and ZIP archive integrity checked. Not runtime-tested inside SketchUp 2023. This is a preview build, not a production-stable release.
