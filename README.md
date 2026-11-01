# SketchGrass 2.3.0 Preview

Independent Grasshopper-inspired visual parametric modeling extension for **SketchUp 2023**. Built with the SketchUp Ruby API and HtmlDialog; Rhino is not required.

## Latest preview: 2.3.0

This preview builds on the 2.2.x component editor and adds:
- Application menu bar with Help and Extensions dropdowns.
- **Help → About Me** developer profile for Palwinder James Singh, School of Architecture, National University Philippines.
- **Extensions → Install New Update…** to select a local RBZ, validate its ZIP signature, and stage it in SketchGrass' update folder.
- **Extensions → Check for Updates** and **Version History** shortcuts.

**Updater limitation:** this preview stages a selected RBZ package but does not replace loaded Ruby code in the active SketchUp process. SketchUp must be restarted before the staged extension can be installed. Seamless hot-reload, automatic background downloads, automated rollback, and the full version selector are not implemented in this preview.

## Downloads and documentation

- [SketchGrass 2.3.0 Preview release notes](./RELEASE_NOTES_2.3.0.md)
- [User guide](./USER_GUIDE.md)
- [Component reference](./COMPONENT_REFERENCE.md)
- [Roadmap](./ROADMAP.md)
- [Previous 2.2.0 installer](./SketchGrass_2.2.0.rbz)

The 2.3.0 preview installer and source package are provided separately in this conversation. They have not yet been attached as GitHub binary release assets.

## Install

1. Download the 2.3.0 RBZ package.
2. In SketchUp 2023, open **Window → Extension Manager**.
3. Choose **Install Extension** and select `SketchGrass_2.3.0.rbz`.
4. Restart SketchUp if prompted.
5. Open **Extensions → SketchGrass**.

## Retained capabilities

- Visual node graph editor, category ribbon and component browser.
- Existing native component library and geometry output.
- `.sgproj` project save/open.
- Declarative component package installation and GHA2SG inspection/scaffold workflow.

## Compatibility and testing

Target: SketchUp 2023. Ruby syntax and archive integrity checks passed for this preview package. It has **not** been runtime-tested inside SketchUp 2023. Treat it as a preview build, not a production-stable release.

## Creator

**Palwinder James Singh**  
School of Architecture, National University Philippines  
Creator & Developer of SketchGrass
