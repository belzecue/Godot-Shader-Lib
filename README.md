# Godot-Shader-Lib
Visual shader node library for Godot engine.

Adds various extra nodes to use in built-in visual shader editor.
# Installation
Copy the contents of **_addons/ShaderLib_** into the same folder in your project. No activation needed. Custom visual shader nodes work the same way as standard visual shader nodes.
# Uninstallation
Delete the contents of **_addons/ShaderLib_** folder from your project. Make sure to delete it using the Godot editor instead of your default file system program.
# Nodes documentation
<details>
<summary><h1>Procedural nodes</h1></summary>
<details>
<summary><h3>Checker Board node</h3></summary>
Generates a checkerboard of alternating colors between inputs <b><i>color A</i></b> and <b><i>color B</i></b> based on input UV.
<hr>  

**Inputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|UV|Input UV value|
|color a|vec3|none|First checker color|
|color b|vec3|none|Second checker color|
|frequency|vec2|none|Scale of checkerboard per axis|
  
**Outputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|output|vec3|None|Output checkerboard value|
___
</details>
<details>
<summary><h2>Noise</h2></summary>
<details>
<summary><h3>Gradient Noise node</h3></summary>
Generates a gradient, or Perlin, noise based on input UV. The resulting <b><i>output</i></b> values will be between -1 and 1.
<hr>

**Inputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|UV|Input UV value|
|scale|float|none|Noise scale|
  
**Outputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|output|float|None|Output noise value|
___
</details>
<details>
<summary><h3>Simple Noise node</h3></summary>
Generates a simple, or Value, noise based on input UV. The resulting <b><i>output</i></b> values will be between 0 and 1.
<hr>

**Inputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|UV|Input UV value|
|scale|float|none|Noise scale|
  
**Outputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|output|float|None|Output noise value|
___
</details>
<details>
<summary><h3>Voronoi node</h3></summary>
Generates a Voronoi or Worley noise based on input UV. Voronoi noise is generated by calculating distances between a pixel and a lattice of points. By offsetting these points by a pseudo-random number, controlled by <b><i>angle offset</i></b>, a cluster of cells can be generated.
<hr>

**Inputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|UV|Input UV value|
|cell density|float|none|Density of generated cells|
|angle offset|float|none|Offset values for points|
  
**Outputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|output|float|None|Output noise value|
|cells|float|None|Raw cell data|
___
</details>
</details>
</details>
<details>
<summary><h1>UV nodes</h1></summary>
<details>
<summary><h3>Flipbook node</h3></summary>
Creates a flipbook, or texture sheet animation, of the UVs supplied to input UV. The amount of tiles on the sheet are defined by the values of the inputs <b><i>rows</i></b> and <b><i>columns</i></b>.
This node can be used to create a texture animation functionality, commonly used for particle effects and sprites, by supplying Time to the input Tile and outputting to the UV input slot of a Texture Sampler.
<hr>

**Inputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|UV|Input UV value|
|rows|int|none|Amount of horizontal tiles in texture sheet|
|columns|int|none|Amount of vertical tiles in texture sheet|
|start frame|int|none|Start tile index texture sheet|
|end frame|int|none|End tile index texture sheet|
|anim speed|float|none|Animation speed|

**Outputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|None|Output UV value|
___
</details>
<details>
<summary><h3>Radial Shear node</h3></summary>
Applies a radial shear warping effect similar to a wave to the value of input UV.
<hr>

**Inputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|UV|Input UV value|
|center|vec2|none|Center reference point|
|strength|float|none|Strength of the effect|
|offset|vec2|none|Individual channel offsets|

**Outputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|None|Output UV value|
___
</details>
<details>
<summary><h3>Rotate node</h3></summary>
Rotates value of input UV around a reference point defined by input <b><i>center</i></b> by the amount of input <b><i>rotation</i></b>.
<hr>

**Inputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|UV|Input UV value|
|center|vec2|none|Center reference point|
|rotation|float|none|Rotation amount in radians|
|use degrees|bool|none|Use degrees instead of radians for <b><i>rotation</i></b> amount|

**Outputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|None|Output UV value|
___
</details>
<details>
<summary><h3>Spherize node</h3></summary>
Applies a spherical warping effect similar to a fisheye camera lens to the value of input UV.
<hr>

**Inputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|UV|Input UV value|
|center|vec2|none|Center reference point|
|strength|float|none|Strength of the effect|
|offset|vec2|none|Individual channel offsets|

**Outputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|None|Output UV value|
___
</details>
<details>
<summary><h3>Tiling and Offset node</h3></summary>
Tiles and offsets the value of input UV by the inputs <b><i>tiling</i></b> and <b><i>offset</i></b> respectively. This is commonly used for detail maps and scrolling textures over TIME.
<hr>

**Inputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|UV|Input UV value|
|tiling|vec2|none|Amount of tiling to apply per channel|
|offset|vec2|none|Amount of offset to apply per channel|

**Outputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|None|Output UV value|
___
</details>
<details>
<summary><h3>Twirl node</h3></summary>
Applies a twirl warping effect similar to a black hole to the value of input UV.
<hr>

**Inputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|UV|Input UV value|
|center|vec2|none|Center reference point|
|strength|float|none|Strength of the effect|
|offset|vec2|none|Individual channel offsets|

**Outputs**
|Name|Type|Binding|Description|
|---|---|---|---|
|uv|vec2|None|Output UV value|
___
</details>
</details>