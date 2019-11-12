### Lecture - 10.10.19

## Fundamentals

### CPP Fundamentals
* Move semantics

### CPP 11/17 new fundamentals
* Lambda functions
* Ranged for loops
* auto

### std::algorithm
* find_if
* remove_if
* SFINAE

### Delegates - тип на функция, която е динамично свързана с друга функция
A mechanism for calling one or many functions without knowing which functions
are in advance. Also known as dynamic dispatching
* Solves the clunkiness of the function pointers
* std::function - single cast delegates, can only store one function

### Multicast delegates
Cant have a return value

### Events and callbacks
* Event source / dispatcher
* Event listener / subscriber
* Callback - something that should happen after an event

### RAII and smart pointers
* std::unique_ptr - can not be copied, but can be moved, owner relation
* std::shared_ptr - can be copied, deletes only if no copies are left
** std::shared_ptr::reset - can be use to reset/delete also
* std::weak_ptr - gets a copy of the shared pointer

### Error handling
* Exception bad
* Error codes bad
* Logging good
* Assertion good
* Crash-handling

### STL
* Not good enough
* Alternative - see presentation

### PC architecture
* Warm cache, happy user
* Enemies: std::list, std::map, std::set
* Shared pointers
* Virtual functions

### Libraries
* executable - .exe, .out
* static - .lib, .a
* dynamic - dll, .so

### Seminar - 11.10.19

## Basic instruments and methods

### Delegates

### Blueprint
The block scheme of the games
Usually non-programmers write this

[Funny stuff](https://blueprintsfromhell.tumblr.com/)

### UFunctions - macros
Specifies certain properties of functions and add metadata  
As far as I know now, used mostly to orientate and add programmable features to
the blueprint UI

### UProperty
Used for garbage collector metadata

### Plugins
Addable code and even whole games

### HW
Used blueprint to code a movement or a feature
What are the pros and cons of blueprint