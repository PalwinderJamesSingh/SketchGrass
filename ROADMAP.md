# SketchGrass Roadmap

## 2.5.0 — safer update preparation
- Save the current SketchGrass definition before update preparation.
- Save the active SketchUp model; prompt for a path if it is untitled.
- Abort update preparation if either save is cancelled or fails.
- Stage the RBZ without force-quitting or force-relaunching SketchUp.
- Use one unified v2.5.0 label in the visible interface.

Not yet verified in SketchUp 2023. The updater requires the user to close SketchUp normally and reopen it; it does not promise automatic relaunch or seamless in-process replacement.

## Next priorities
1. Runtime test startup project selection, recovery, save behavior, menu interactions, and update staging in SketchUp 2023.
2. Repair and regression-test HtmlDialog menu interactions and the reported white-screen issue.
3. Implement explicit Save All for both .sgproj and .skp, with clear status and failure handling.
4. Build architecture, structural, and construction component libraries.
5. Expand geometry engine, data trees, and interoperability.