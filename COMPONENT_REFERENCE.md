# SketchGrass 2.2.0 — Component Reference

This is the implemented component inventory, not a promise of full Grasshopper compatibility.

| Category | Component | Main purpose |
|---|---|---|
| Params | Number Slider | Interactive numeric input |
| Params | Number | Numeric constant |
| Params | Boolean | True/false input |
| Params | Point | Point parameter |
| Params | Construct Point | Build a point from X, Y, Z |
| Maths | Addition | A + B |
| Maths | Subtraction | A - B |
| Maths | Multiplication | A × B |
| Maths | Division | A ÷ B |
| Maths | Construct Domain | Numeric interval |
| Maths | Remap Numbers | Remap a value between domains |
| Maths | Absolute | Absolute value |
| Maths | Square Root | Square root |
| Maths | Power | A raised to B |
| Maths | Modulus | Remainder |
| Maths | Minimum | Smaller of A and B |
| Maths | Maximum | Larger of A and B |
| Maths | Average | Average of values |
| Maths | Sine | Sine (radians) |
| Maths | Cosine | Cosine (radians) |
| Maths | Tangent | Tangent (radians) |
| Maths | Round | Round to decimal places |
| Maths | Clamp | Constrain a value to a range |
| Sets | Series | Generate a numeric sequence |
| Sets | Range | Generate evenly spaced values |
| Sets | List Length | Number of list items |
| Sets | List Item | Retrieve an item by index |
| Sets | Construct List | Combine input values into a list |
| Sets | Reverse List | Reverse list order |
| Sets | Sort List | Sort list values |
| Sets | Cull Index | Remove an item by index |
| Sets | Dispatch | Split a list by Boolean pattern |
| Sets | Weave | Interleave two lists |
| Vector | Construct Vector | Build a 3D vector |
| Vector | Vector Length | Calculate vector magnitude |
| Vector | Deconstruct Vector | Extract X, Y, Z |
| Vector | Unit Vector | Normalize a vector |
| Vector | Reverse Vector | Reverse vector direction |
| Vector | Vector Addition | Add vectors |
| Vector | Vector Subtraction | Subtract vectors |
| Vector | Vector Scale | Scale a vector |
| Vector | Dot Product | Calculate dot product |
| Vector | Cross Product | Calculate cross product |
| Curve | Construct Line | Create a line from two points |
| Curve | Line Between Points | Create a line from Start and End |
| Curve | Polyline | Create a polyline from points |
| Curve | Circle | Create a circle in the XY plane |
| Curve | Divide Curve | Divide supported line/polyline geometry |
| Curve | Curve Length | Measure supported line/polyline/circle length |
| Surface | Rectangle | Create a rectangular planar face |
| Surface | Extrude | Extrude a supported planar face along a vector |
| Transform | Move Point | Translate a point by a vector |
| Transform | Move Geometry | Translate supported geometry |
| Transform | Scale Point | Scale a point about the world origin |
| Display | Geometry Output | Bake evaluated geometry into SketchUp |

## Geometry support boundary
The current adapter documents baking points, lines, polylines, circles, and polygon faces. Curve division supports lines and polylines. Curve length supports lines, polylines, and circles. Extrusion is limited to planar polygon faces. General NURBS, mesh, and solid operations are not implemented as a full geometry kernel.

## Suggested first tests
1. Number Slider × Number → Addition → Recompute.
2. Construct Point → Construct Line → Geometry Output → Generate in SketchUp.
3. Construct Point values → Polyline → Geometry Output → Generate in SketchUp.
4. Rectangle → Extrude with Construct Vector → Geometry Output → Generate in SketchUp.

Use USER_GUIDE.md for editor controls, saving, troubleshooting, and Grasshopper import limitations.
