# SketchGrass 2.5.2

Independent Grasshopper-inspired visual parametric modeling extension for **SketchUp 2023**. Built with the SketchUp Ruby API and HtmlDialog; Rhino is not required.

## 2.5.2 — Architectural Component Library Foundation

Adds five native schematic architecture components to the visual parametric canvas:

- **Wall (Linear):** start/end points, height and thickness.
- **Floor Slab:** origin, width, depth and thickness.
- **Column Grid:** bay counts and X/Y spacing.
- **Facade Panel Grid:** width, height and panel dimensions.
- **Roof Plate:** origin, width, depth and elevation.

All dimensional inputs use meters. Geometry is generated through SketchGrass' existing SketchUp-native output pipeline. These are foundational modeling components, not structural-analysis or construction-documentation tools; openings, material assignment, reinforcement, load analysis and code checking are not included.

## Downloads and documentation
- [2.5.2 release notes](./RELEASE_NOTES_2.5.2.md)
- [User guide](./USER_GUIDE.md)
- [Component reference](./COMPONENT_REFERENCE.md)
- [Roadmap](./ROADMAP.md)

The 2.5.2 installer and source archive are distributed with this release package. A GitHub binary release asset is not published.

## Compatibility and testing
Target: SketchUp 2023. Ruby syntax, JavaScript syntax and ZIP integrity checks passed. This package has **not** been runtime-tested inside SketchUp 2023. Test on a copy of your model before production use.

## Creator
**Palwinder James Singh** — School of Architecture, National University Philippines; Creator & Developer of SketchGrass.
