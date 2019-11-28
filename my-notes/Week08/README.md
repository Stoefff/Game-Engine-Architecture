### Lecture - 28.11.19

### Mistakes form the exam:
* Time can be float, if we do sum many times and we use a small value
* Time in UE is float
* Every pointer should be checked for NULL

## Animations

### Cell and Sprite animations
* Objects with many drawn positions
* Fast changing of the positions gives us the animation
* Good for 2D games and UI
* Very bad in 3D

### Rigid Body Hierarchy
* Represents the objects as a collection of movable body part e.g. bones
* Problems with the joint movement

### Morph targets
* Solves the problems of RGH
* Almost impossible to create
* Takes a ton of memory and impossible to do run time
* Simplified version of this is used a facial expression animation

### Skinned animation
* Allows the polygons (triangles) of the object to move/resize/change
* Every model consists of skeleton - bones and joints - and skins (mesh)
* Every vertex of the skin is attached to some bone
* Bone and joints are practically the same but note that we do not move the
bone but rather program the possible movements of the joint

### Poses
* Current transformation
* Default T Pose - easy to animate form
* The pose of the skeleton is the pose of all joints and in turn all of their
pairs
* Global and local poses
* The global pose is what we want to draw in the game worlds
* If we want to find the position(pose?) of a certain joint , we start from it
and recursively go through(get the product of the all the matrix) the parents
of each joint. When reach the root, then we calculate the position in the world
and know we know the pose of the joint the world
* When we want to animate a action, we only have the starting position of the
skeleton(T pose) and the final position. The intermediate steps are done by
interpolation all all the joints with their start and end poses

### Animation clips
* Collection of poses or rather complex animation
* Clip time

### More complex skin animation
* A vertex can be changed by many joints
* A joint can a have a percentage of influence to a certain vertex
* In UE4 a vertex can be influenced by max 4 joints

### Blending
* Combining clips and poses
* Done again by linear interpolation
* However matrix cant be interpolated and so we can decompose the translation
matrix and interpolate the needed elements

### Partial blending
* We turn of completely some joints for some animations
* Not very good

### Additive blending
* Calculete the transition matrices for each animation( and each joint)
* The add the all the transition matrices to form the final translation matrix
* Also have some problems

### Post-Processing
* Rag-doll - detach all the current animations and handle all the skeleton movement
to physics in order to affect the skeleton by some physics event e.g. explosion
* Inverse kinematics - create animation against the environment e.g. if we have a
animation for stairs walking but in this case all the stars should be with the
same size. We want the animation to work for all types of stairs. So we build
the animation next to the environment

### Compression
* Animation takes a lot of memory and process time
* We should optimize that

### State machines (Deterministic finite automata)
* Controls which animations are called after which and so can create complex
and intuitive animation scenes