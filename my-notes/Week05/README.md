### Lecture - 31.10.19

## Math in Game Engines

### Application in math

### Coordinate systems
* Definition
* Types
* Handedness

### Vectors
* Definition
** In algebra: a tuple of numbers
** In geometry: a structure with direction and magnitude
* Square root of a vector is slow and should be optimized

**The processor uses matrix to do 4 operation i one tack**

### Quaternion
* Rotation is a heavy operation and supports 4 formal solving methods:
** Euler angles: bad for computing but easy for the people, gimbal lock
** Axis + angle
** Rotation matrix
** Quaternion

### Interpolation
* Definition: **Check video**

### Interesting: крива на Безие

### Seminar - 08.11.19

## Coding Practice

### virtual function mindfuckery
`virtual` does not allow to be override by the blueprint UI - BlueprinCallable.
We need to write a wrapper which is not virtual that allows us to to override
in the blueprint - BlueprintImplementable

### Timers
We can have timers for cooldown and cooldown dilation if we want to have an
ability that changed cooldowns