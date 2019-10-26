### Lecture - 17.10.19

**We use assert only in DEV mode, not in production**

## Game Engines Architectures

In the main we have infinite loop  

### Windows infinite game loop
The windows API have a massage system for catching certain events
They are handled by a certain func

### Normal main
* Initialize()
* Game (inf game loop)
* Deinitilize()

A frame of the game is a iteration of this game loop, so it should be max
16ms for it to be 60 fps

### Game loop
Abstract jobs:
* Process input
* Update world - N.B. All the functions are continuous and the code is run many
times in a second, which something to keep in mind, because its strange to
normal programmers
* Update render state - the cool animation of spawning and despawning
* Render

### Multithreaded Architectures
Different threads for different tasks

### Double and Triple buffering
So the render is one step back from that of the the game play update in order
to synchronize the jobs  
Double buffering - we keep 2 sets of game play data info, so that the input does
not update outdated info

### Time
Speed is determined by time
We should we keep in mind that speed should not depend by the fps xD
We should make our own timer

### Delta Time - solves this problem

### Big morals
* Never compute time by accumulating time deltas
* Use now() for time
* Use correct types to store time

### Game objects
Normal OOP principles does not work in game design, it has problems:  
* Tight coupling because of inheritance
* Dynamic support is slow

**Instead of inheritance we use composition**

### Components
Can be used by game designers xD  
Entities have components, which define its properties

### Data-Oriented Programming

**Check what are cache misses**

Use of Array of Structures - when using many objects of the same class, the
memory cache is located poorly. When we use DoD we what to use structures
which are easily computed by the processor.

**The big idea: when we have a list of things we should do, in oop the order
of the tasks if determined by the current object, which executes different task
for the object, after that the next object executes the same DIFFERENT tasks.
That way of working is not CPU friendly. Instead we should group the same task
for the different objects, to be executed one after another, so it could be
optimized by the processor**

### Pure entity system aka ECS
* Components are just data
* Entities are just recognized by IDs
* Systems are just functions

### Seminar - 18.10.19

## UE4 Architecture

There is a good std class for time: Timer;

### UObject
* Support Garbage collection
* Support Reflection

### UClass
Normal cpp class but with the following properties:
* Macros for integrating within the UN systems
* Generated_body() for the same purpose

### UStructures
* Does not support methods
* More lightweight than normal

### Game object model
* We use components if the work is more for the designers
* We use OOP if the work is more with programmers

### UWorld and UActor
* The Root object of the game is UWorld
* The world is full Actors
* Actors are spawned by a UWorld Function

### GameMode and GameState
* GameMode is an Actor for the logic of the game
* GameState are stats of a certain game mode

### ShortCuts
* Shift + F1 to pause game  