# Pedrito-fabric-exts
Pedro Cabrera's extensions and presets for Fabric Engine


##PC_BasicTools

####Lines:
  
- **PC_GetPerLineLentghs**:  Returns an array with each line lengtgh , and an array of arrays with each linePointLength (distance from each point to the first point).

- **PC_GetPerLinePositions**:  Returns an array of arrays (each sub array contains each line point positions).

- **PC_SetPerLinePositions**:  Sets the line positions based on arrays of arrays (like the getPerLienPositions).

- **PC_GetPerLineTransforms**:  Returns an array of arrays (each sub array contains each line point transform).

- **PC_PerLineDataToStrip**:  Convert an array of arrays into a sigle array and return also an array with each subarray size.

####Math/Vec3Curves:
 - **PC_Vec3_BezierCurve**:  Returns a bezier curve(Vec3_Array) of an input control points array based on an input uArray.

- **PC_Vec3_BezierCurve_Arrays**:  Same as previus but per arrays of arrays ( this means you can use it to create bezier lines from an input line using the PC_GetPerLinePositions node).

- **PC_Vec3_GetCurveLengths**:  Return the length of an input Vec3 Array curve, just the same as PC_GetPerLineLentghs ( in fact PC_GetPerLineLentghs uses the array version of it).

- **PC_Vec3_GetCurveLengths_Array**:  Same as previus but per arrays of arrays.

####Geometry/PolyIslands:
- **PC_Polymesh_To_Islands**:   Takes a PolygonMesh as input and returns the Nb os islands, the island index per point array, the island center per point array, and the same for each island. it Also returns and array of PolygonMeshes, each one of the islands "ZeroPositioned".
  ¡¡especial thanks to [BigRoy](https://github.com/BigRoy) for the help with the recursive algorithm!!
  [FE Forums: PC_Polymesh_To_Islands](http://forums.fabricengine.com/discussion/64/pc-polymesh-to-islands#latest)

##PC_HighLevelTools
####Lines/Defform:
- **PC_AdaptLinesToGeo**: Adapt lines to a input geometry with distance and pusth controls.
- **PC_ResampleLines**: Resample a set of input lines by percentage, it has two options:
    - EvenSpace: this method will calculate atomatically the nb of output points based on de division of the curve and de EvenSpace input factor resulting in a fitted curve for the desired EvenSpace. This method also support start and end values(actually just one per all subcurves but it can be modified if needed).
    - Percentage from Array: this method asks for an input array of percentage values (one is allowed but will not create lines). Note tha the percentage range is 0-1.
  
  The resulting NewLines have their points even spaced, and the Points array are all the points in all subcurves.

- **PC_SmoothLines**: this is a simple neighbour smoothing algorithm.

####Lines/Procedural:
- **PC_CreateDnaChainOnLines**: It creates DNA like curves from a set of input curves, you have control over the percentage, the union speed and some others.
[FE Forums: Some Line/Curve Basic Tools](http://forums.fabricengine.com/discussion/118/some-line-curve-basic-tools#latest)
