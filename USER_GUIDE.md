# SketchGrass 2.2.0 — Getting Started Guide

This guide explains the current editor. SketchGrass is an independent SketchUp extension inspired by Grasshopper; it is not Rhino Grasshopper.

## 1. Install and open
1. Download SketchGrass_2.2.0.rbz from the repository.
2. Start SketchUp 2023 and open Window > Extension Manager.
3. Choose Install Extension and select the RBZ.
4. Restart SketchUp if prompted.
5. Open Extensions > SketchGrass.

Install the RBZ. The source ZIP is for developers, not the installer.

## 2. Know the editor
- Top bar: New, Open, Save, Recompute, Generate in SketchUp, Clear Output.
- Category ribbon: Params, Maths, Sets, Vector, Curve, Surface, Transform, Display.
- Component browser (left): search for a component; click it or drag it onto the canvas.
- Canvas (middle): node graph. Inputs are on the left side of a node; outputs are on the right.
- Properties / Documentation (right): select a node to inspect its parameters and documentation.
- Status line: reports actions and errors.

## 3. First definition: create a point
1. In Params, add Construct Point.
2. Add three Number Slider nodes.
3. Drag from each slider's output socket to the matching X, Y, and Z input socket on Construct Point.
4. Add Geometry Output from Display.
5. Connect Construct Point's Point output to Geometry Output's Geometry input.
6. Click Recompute.
7. Click Generate in SketchUp to bake the evaluated point into the active model.

Change a slider and recompute, then generate again. The point parameter coordinates are expressed in model meters in the current implementation.

## 4. Create a line
1. Add two Construct Point nodes and provide X, Y, Z values for each.
2. Add Construct Line or Line Between Points.
3. Connect the points to A/B or Start/End.
4. Add Geometry Output and connect the line output to its Geometry input.
5. Click Recompute, then Generate in SketchUp.

## 5. Connect, move, and navigate
- Connect: drag from an output socket (right) to an input socket (left).
- Move a node: drag its header.
- Select a node: click it; its properties appear on the right.
- Delete: select a node and press Delete or Backspace.
- Duplicate / fit canvas: right-click the canvas and choose the relevant menu item.
- Zoom: mouse wheel over the canvas.
- Pan: middle mouse button and drag.
- Search: type a component name in the component browser search field.

## 6. Save and reopen
- Save creates a portable .sgproj file containing the node graph, connections, and properties.
- Open loads an existing .sgproj.
- A .sgproj is a SketchGrass definition, not a SketchUp model. Save the .skp model separately.

## 7. Component families
The built-in library contains 55 definitions:
- Params: Number Slider, Number, Boolean, Point, Construct Point.
- Maths: Addition, Subtraction, Multiplication, Division, Construct Domain, Remap Numbers, Absolute, Square Root, Power, Modulus, Minimum, Maximum, Average, Sine, Cosine, Tangent, Round, Clamp.
- Sets: Series, Range, List Length, List Item, Construct List, Reverse List, Sort List, Cull Index, Dispatch, Weave.
- Vector: Construct Vector, Vector Length, Deconstruct Vector, Unit Vector, Reverse Vector, Vector Addition, Vector Subtraction, Vector Scale, Dot Product, Cross Product.
- Curve: Construct Line, Line Between Points, Polyline, Circle, Divide Curve, Curve Length.
- Surface: Rectangle, Extrude.
- Transform: Move Point, Move Geometry, Scale Point.
- Display: Geometry Output.

A component in the catalogue does not imply full Grasshopper data-type or Rhino geometry compatibility.

## 8. Grasshopper imports: read this before using GHA2SG
The GHA2SG button inspects a .gha or .ghpy file and can save a declarative .sgp scaffold. It does not run, decompile, or automatically convert the original component.
- .gha files are commonly compiled .NET assemblies and may depend on Grasshopper, RhinoCommon, and other DLLs.
- .ghpy files may contain Python code or packaged component data.
- .dll files are compiled libraries/dependencies. SketchGrass does not load them as Grasshopper components.
- A generated scaffold is intentionally marked as not implemented. It must be reviewed and manually ported to a supported native SketchGrass operation before installation.
- The package installer accepts only a limited allowlist of native operations. A scaffold will be rejected until it has been genuinely ported and reviewed.

Do not rename DLLs or remove dependencies expecting the Grasshopper component to work. Never install untrusted code.

## 9. Troubleshooting
- Editor does not appear: confirm SketchGrass is enabled in Extension Manager, restart SketchUp, then open it from Extensions.
- Component not found: switch category or search by exact name.
- No geometry appears: connect the geometry-producing node to Geometry Output, click Recompute, then Generate in SketchUp.
- Evaluates but does not bake: supported output geometry is limited to points, lines, polylines, circles, and polygon faces.
- .gha, .ghpy, or .dll fails: this is expected for native Rhino/Grasshopper binaries; GHA2SG is inspection only.
- Package install fails: check valid JSON, required manifest fields, SketchGrass API 2.x, allowed operation, and absence of SCAFFOLD_ONLY status.

## 10. What is not complete
SketchGrass 2.2.0 is an early native parametric foundation, not a complete Grasshopper replacement. Missing areas include data trees and matching, NURBS and advanced surfaces, mesh generation/editing, solid Boolean/intersection operations, robust curve/surface intersections, fields/physics/optimization, broad package compatibility, and automatic .gha/.ghpy/.dll conversion.

Static syntax/archive checks are documented in the source package. The manual acceptance checklist still needs to be run inside SketchUp 2023. Back up your model and test on a copy before production use.
