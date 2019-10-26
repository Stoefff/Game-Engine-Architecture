### Lecture - 24.10.18

### Recap from last time
**Very important thing to remember used in all game engines: all engines
are based on the entity and component structure like it was explained form
last time**

## Low level systems

The ECS model isn't used in all systems, especially in the low level systems

### Code separation as libs and modules
Benefits:
* Easy testing
* Plugin support
* Better performance

### Low-level systems are mostly singleton

### Login system
* Help us understand the program flow
* Should be very fast so performance should be changed
* Good categorization
* Should handle crash management

Some libs for logging:
* boost - is bad
* can find good on GitHub

### Input management

### Memory management with C++ <3
* malloc / free are not actually OS functions
* placement new - using already allocated memory for placeholder of the new obj
* overloading operator new with user defined args
* Allocators

### Linear / Stack Allocators
Easiest solution, if we need something to live for one frame, we need to
optimize the allocator

**All stl and smart pointers have support for custom allocators**

### Garbage collection
We should make the game easy for designer with the blueprint

### Resource management and IO

### String interning - check

### Reflection
* Helps with code introspection
* Allows to thread code a resource
* Helps serialization - we don't wanna write serialize function for every class
* With reflection we can write serializing for all types once

### Configuration - text and binary
* We can even store whole games in the config files  
* Config placeholders - ini files are good, Naughty dog use functional languages
for config files
* Config files are translated to binary for the game to use
* Runtime configuration - e.g. add terminal to the game like CS

### Seminar - 25.10.19

* UObject - The most basic class support to reflection
* Actor - the most basic class,
* UFunction - macros for meta data for like reflection and blueprint support
* UProperty - macros for meta data for like reflection and blueprint support

### Resource management
Strange was to load assets with the code

### Reflection
Many thing we should do  
Check header: `HeaderParser.cpp`

### Engine Configuration
Do NOT check the background optimization option cause it causes a lot of
problems  

### Engine config classes
They touch the .ini configuration files
These .ini files have a special ways of editing - check lecture

### Game console
* Very important for designers and QA
* CMD arguments for starting the game
