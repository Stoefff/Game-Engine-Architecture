### Lecture - 21.11.19

### From last time
* Rasterization, Z Buffer
* BRDF and what it means
* G buffer and what it stores

## Rendering #2

* Graphical Proccessing Units
* DirectX 12 API
* Rendering components

### Representing light as a function
* Functional programming is useful when thinking about light because there
are no side effects
* BRDF - is a filter of light

### Light input
* Direct
* Indirect - we need the direct light to calculate the indirect

### Post Lighting processing
* Tone Mapping - The human eye can distinglish 1 to 10 000 contrast, but the monitors
used 256 values to represent contrast so we need tone mapping

### Rasterization
We can да си го представим like a mesh infront of out eye and we shoot light from
every point from it and we process the input

### Definiton
* Latency - Time to finish task - 33 or 16 ms frame
* Tasks per unit time -

### Processors history
* Moore's law
* Wire are taking a lot of space in the chip
* TDP
* Transistor count/Clock speed/Power/Task Speed relation

### Memory
* Speed / Capasity relation in time
* Memory price over time
* Processor - Memory performance gap

### CPU vs GPU comparison
* We should always consider what are we going to use in out program
* When we use big data - GPU
* When we use fast data - CPU

### CPU
* ALU
*
* Branch predictors - Static and Dynamic
* Profile ... optimizition for user stimulated branch prediction
* Out of order logic
* Memory prefetch
* L1 to L3 caches speed

### GPU
* ALU
* Fetch
* Execution

### GPU fetch logic
* Milty Treaded by deafult
* Traslated to byte code which is then translated to accembler
* if branches are very slow

### GPU stalls and GPU registers and how to optimize them

### GPU Stats and operation
* 80% process saturation

### GPU bandwith
* Bit wise operation are good
* there should not any memory gaps

### Memory blocks
* L1 and L2 Cache
* Texture Cache

### Graphical blocks

### Why Ray tracing is slow:
* Rendering static objects with RT is ok
* Rendering dynamic objects with RT creates KD trees and ... trees which can
be 1 or 2 GB they are bad data structures for the GPU to work with

### GPU API-s
* DirectX 12
* Vulcan
* Abstraction of the hardware

### AMD PAL
* AMD library for creating abstraction for the drivers

### DirectX 9, 11 / Open GL
* Delayed libraries - meaning we should first always prepare the data and then
execute
* Intel, AMD, and nVidia have different methods of solving threads problems

### DirectX12, Vulkan
* Even more lower abstraction than DirectX11

### Main API components
* Memory
* Commands
* Sync
* Pipeline State
* Transitions

### Memory
* Heaps - different type for different data, the heap should be optimized
for the current tasks/resources

### Placed resources
* The main difference between DX11 and DX12
* Adds just reserved resources, that do not require actual physical memory

### Commands
* Bundles
* Transmitted through queues
* Fence maechanism to sync queues

### Pipeline states
* DX12 is very fast compared to DX11 because of this
* Groups up tasks and speeds up the process

### Resource transition
* Big problem because its different for different hardware
* GPU sync and data flush
* Solved with resource barriers, which are abstraction of the cache

### Submiting work to the GPU
* Data should be in lists - Data Oriented Programming
* Graphic and gameplay data should be separated

**Destiny is with slightly faster rendering form n to n+1 frame**

### Render Graph

### Seminar - 22.11.19

## Rendering UE4

### From last time
* The main 5 arguments to TimerManager::SetTimer

**UE4 rendering docs are pretty good, should be checked**

### Overview of rendering
* 3 levels of rendering
* RHI, RenderCore, Renderer

### RHI
* Rendering Hardware Interface
* Low level
* Abstraction over the GPU pipeline -> Graphics device API
* There is RHI for every major GPU lib - DirectX, Vulcan, etc.

### Command task pattern
* Creates a functor that holds some state
* Store the functor in a queue of commands
* Execute when neccessary
* Useful with threads
* Useful to create Undo/Redo functionality
* FRHICommandList is such a queue

### Shaders
* Written in HLSL
* Unreal uses Unreal Shaders Language meaning shaders are compiled for the
current platform

### Render core
* Gives us the multi-threading
* FRenderCommandFence - like mutex/semafors synchronization ??

### Renderer architecture
* Objects in Unreal are not thread save
* The renderer is always 1 or 2 frames behind

### Materials
* Their expression compile down to HLSL(they ARE shadders)
* Physically Based Rendering
* Base color
* Roughness
* Metallic
* Specular
* Can be inherited
* Normal Maps

### Lights
* Directional
* Point
* Area
* Sky
* SwarmAgent
