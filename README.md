# SketchGrass 2.5.0

Independent Grasshopper-inspired visual parametric modeling extension for **SketchUp 2023**. Built with the SketchUp Ruby API and HtmlDialog; Rhino is not required.

## 2.5.0 update
- Safer update preparation asks permission to save the active SketchGrass definition (.sgproj) and active SketchUp model (.skp) before restart.
- Untitled SketchUp models trigger Save As. Existing modified models are saved to their current location.
- Cancelled or failed saves stop update preparation; SketchUp is not force-closed.
- The updater stages the RBZ and asks the user to close SketchUp normally and reopen it. Forced process relaunch was removed to avoid unstable restart behavior.
- Unified visible version label: v2.5.0.

## Downloads and documentation
- [2.5.0 release notes](./RELEASE_NOTES_2.5.0.md)
- [User guide](./USER_GUIDE.md)
- [Component reference](./COMPONENT_REFERENCE.md)
- [Roadmap](./ROADMAP.md)

The 2.5.0 installer and source archive are distributed separately; a GitHub binary release asset has not been published.

## Compatibility and testing
Target: SketchUp 2023. Ruby and JavaScript syntax checks and archive integrity checks passed. This package has not been runtime-tested inside SketchUp 2023.

## Creator
**Palwinder James Singh** — School of Architecture, National University Philippines; Creator & Developer of SketchGrass.