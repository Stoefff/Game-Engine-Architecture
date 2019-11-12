### Lecture - 03.10.19

## Introduction to game engines

### What is a game
Varies in definition, as user see fit :D  
Formal: a structured form of play

### 3 types of devs in the team
* Game devs
* Engine devs
* Tools devs

### Game properties
* Soft-realtime
* Interactive
* Agent-based
* Simulation

### Game engine architecture
* OS
* Middleware
* Platform independence layer
* Core systems - for programming
* Asset pipeline
* Rendering
* Physics
* Gameplay systems - make it accessible for game designers
* Game front end

### Different game engines

### Seminar 04.10.19

## Unreal engine overview

### Cooking
The process of optimizing the game's content for the target platform

### Modules
* Collection of code that implements some functionality
* The whole engine/game is separated in such
* All code must belong to a module

### Essential files
* Target.cs - setup the build env
* .uproject* - general info / meta data about the game
* .uplugin* - the same but for plugins

### Core modules categories - in /engine/source

### Coding standarts
* UObject - The root object, provides reflection and garbage collection
* AActor - the root of everyting placeable in the world, child of UObject
* APawn - the root everything possessable in the world, child of AActor
* AController - can possess a Pawn, child of UObject
* SWidget - Widgets

### All types have prefixes
Check presentation