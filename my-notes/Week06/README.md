### Lecture - 14.11.19

### Recap from last time
* Dot product
* Normal vector
* Ways of representing cordinates

**There is course for rendering: трасиране на лъчи, held 1 time at 2 years**

## Rendering

### Coloring
* RGB
* HSL - Hue, Saturation, whiteness - used by painters
* CMYK - used by printers

### What is 3D scene
* Geometries: actually an array of triangles
* Lights
* Objects
* Camera

### Geometries
* Represented by equations for triangles
* NURBS - complex lines with parameters
* Triangles - simplest type of polygon, everything is represented by them
* Tesselation - Using algos to create to split big triangles into more triangles
adding more detail to the object - DEMO

### Lights
* Directional lights - lines of lights, not realistic
* Point light - single point in space, that emit light in all directions
* Spot lights -
* Area light - the lit area of objects
* Emissive - lights emmited by objects

### Materials
* What are they - BRDF - gives us the information about the emited light
from the material of the object

### Camera and FOV
The name of the piramid, representing what we see

### Rendering equations
* All rendering algos solves the big render equation
* Different algos solve the equation in different
* Lo - What we should see
* Le - light emited ? -check video
* The integral describes a полусфера and the light coming out of it
* fr - is the BRDF function

### Phong lighting model
* Ambient light
* Diffuse light
* Specular light
* The 3 combined gives us the the rendered image
* Not physically correct

### Physically based rendering - PBR
* More physically correct that phong, but still not enough
* Add more properties like metallic-ness, shaders edges (грубост)
* Invented by disney at 2011 :(

### Global illumination
* Direct light
* Indirect light (global)
* All the global lighting should be recalculated when we move the camera
* For all the pixels, we calculate an the equation, sometimes more than one

**Monte Carlo algos - we use Numerical methods to solve the big integral**

### Rendering algos
* Painters algorithm
* Ray tracing - ineffective in the physical way, we use the рефлективно property
of the BRDF and we emit light form the camera and see where are the shadows but
this properties make the algo not physically correct
* Rasterization - using z buffer to calculate depth and decide which object
should be rendered in front of which other objects

### Textures
* Mesh grid
* 2D mapping to the 3D objects

### Mipmapping
* Recalculating the objects if they are far away from the camera
* It combines all the properties of the object so it can be различен from far away
* Way of texture filtering - bilinear, trilinear, Anisoftopic

### Rendering dictionary
* Forward rendering - calculated all the geometries and the light properties
for each rendered object one after another - slow calculation
* Deffered Rendering - G buffer to store all lighting properties and then
calculated all pixels lighting at once and once - big memory usage because
of the all the properties buffers
* Tiled Rendering - allows for many lights, represents the scene as 2D titles
which are either lit or not
* Cluster Rendering - same as Tiled rendering but 3D

### Reflections
* Ray tracing in a specific spot

### Ambient Occlusion - AO / SSAO / HBAO
* Comes in ray tracing by default
* Calculates where the angles that global lighting should no be seen

### Shadow maps
* Like z buffer - stores shadows
* Cascaded shadows maps -  creates the maps by combining these cascades, which
are like shadows maps, for different distances form the camera

### Global illumination
* Lightmaps - statically create a map for stationary objects
* GI probing - probe dynamic/moving objects to ? precalculate the integral for
these objects

### Volumetric lighting
* Comes by default by

### Level of detail
Changed dynamically where the object is near or far away form the camera

### Anti-Aliasing
* Comes by default in ray tracing
* MSAA - has its weaknesses, only for front rendering, hardware accelerated
* FXAA - blurs the edges, bad, post-process algo?
* TXAA - using the previous frame to calculate with time the right edge
* Other

### Post precessing
* Depth of view - blur when objects are not in the focus
* Lens flare
* Motion blur
* Bloom
* HDR - also gives us the eye light adaptation with it

### The special things about RTX
Gives a hardware buffer? in order to calculate пресичането на лъчи fast 