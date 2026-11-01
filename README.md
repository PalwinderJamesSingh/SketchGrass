# SketchGrass 2.2.0

Independent Grasshopper-inspired visual parametric modeling extension for **SketchUp 2023**. Built with the SketchUp Ruby API and HtmlDialog; Rhino is not required.

## Download
- **Installer:** [SketchGrass_2.2.0.rbz](./SketchGrass_2.2.0.rbz)
- **Getting started:** [USER_GUIDE.md](./USER_GUIDE.md)
- **Component reference:** [COMPONENT_REFERENCE.md](./COMPONENT_REFERENCE.md)
- **Release notes:** [RELEASE_NOTES_2.2.0.md](./RELEASE_NOTES_2.2.0.md)
- **Roadmap:** [ROADMAP.md](./ROADMAP.md)

The RBZ is the installer. The source archive is for developers and is not required to install the extension.

## Install
1. Download the RBZ installer from this repository.
2. In SketchUp 2023, open **Window > Extension Manager**.
3. Choose **Install Extension** and select **SketchGrass_2.2.0.rbz**.
4. Restart SketchUp if prompted.
5. Open **Extensions > SketchGrass**.

## First use
1. Add **Construct Point** and three **Number Slider** nodes.
2. Connect the sliders to X, Y, Z.
3. Add **Geometry Output** and connect the Point output to its Geometry input.
4. Click **Recompute**, then **Generate in SketchUp**.
5. Save the graph as .sgproj with **Save**. Save the SketchUp model separately as .skp.

See USER_GUIDE.md for node connections, canvas navigation, saving, troubleshooting, and import limitations.

## Built-in library
55 component definitions across 8 categories:

| Category | Count |
|---|---:|
| Params | 5 |
| Maths | 18 |
| Sets | 10 |
| Vector | 10 |
| Curve | 6 |
| Surface | 2 |
| Transform | 3 |
| Display | 1 |
| **Total** | **55** |

## Planned next feature: Version Manager
SketchGrass 2.3.0 is planned to add an in-app **Update** button and Version Manager. Users will be able to choose a published compatible release to upgrade or downgrade, review release notes, and confirm the change. The design includes installer checksum verification, backup, staged installation, and rollback/recovery. This feature is **not present in 2.2.0** yet. See [ROADMAP.md](./ROADMAP.md).

## Important compatibility limits
- SketchGrass is a native SketchUp implementation, not Rhino/Grasshopper running inside SketchUp.
- Native Grasshopper .gha, .ghpy, and .NET .dll files cannot be executed directly. GHA2SG performs heuristic metadata inspection and creates a porting scaffold, not automatic conversion.
- The component catalogue is a limited native subset. It does not include full Grasshopper parity, data trees, general NURBS, advanced mesh/solid operations, or broad surface/intersection tools.
- Native package installation supports only a small allowlist of operations. Imported scaffolds must be manually ported and reviewed.
- Static syntax/archive checks are documented in the source package. Manual acceptance tests inside SketchUp 2023 have not been completed in this build environment.

Back up your model and test on a copy before production use. Report issues with SketchUp version, steps, expected behavior, and actual behavior.
