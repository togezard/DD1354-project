## First Blog Entry
# Background
As light passes through water, metallic or transparent surfaces, the refraction of light causes a phenomenon known as caustics. Caustics are famously difficult to simulate with a limited time budget [1], leading to them being ignored or roughly handled.


Fig 1: Caustics created from light passing through the surface of the water [2].

Taking inspiration from previous projects in the course;

https://simulatingoptics.wordpress.com/ 

2. Implementation specifics (as many as possible)
Technologies, physics problem, constraints 

Yo, we will use

Create water
Start with still water
Add waves later
Create a ground
Start with a flat surface
Create a more complex surface after (if time permits)
Have lightbeams refract through water
What is the light source?
Start with sunlight (parallel light from far away)
Then add light from a point
Maybe add light from a surface? (if time permits)
Record a few lightbeam hits
Connect them with lines

What parameters will the user be able to change?
direction of light
height of waves
Ground complexity?
light source (sunlight, point, surface)
Amount of light rays
Ability to see lightray path. 
3. Specifics of what the final system will look like
and do

Fig 2: Sketch of how the final system will work.

5. Potential risks/challenges
The main risk is that we are too ambitious, and want to do too much. The way we tried to avoid that is by prioritising certain tasks as tasks we’ll do if and only if we have time. 

Another risk is that this won’t be able to be done in real time. 
Another risk is that the way we try to implement caustics may not look realistic, especially for lower light ray counts or perhaps more complex surfaces. 
There’s a risk that we cannot properly refract the light rays through the water because of missing normal information. This however could be mitigated by just using a simple 3D-object the shape of waves.
6. Degree of simulation
To what degree will the simulation use existing physics libraries versus being implemented from the ground up

We will take an existing water simulation, possibly philipsocean form the labs. 
7. Link to blog containing first blog entry
Link: https://togezard.github.io/DD1354-project/ 

We are aiming for grade A


4. References (look into more references)
[1]	X. Yang och Y. Ouyang, ”Real-Time Ray Traced Caustics”, i Ray Tracing Gems II: Next Generation Real-Time Rendering with DXR, Vulkan, and OptiX, A. Marrs, P. Shirley, och I. Wald, Red., Berkeley, CA: Apress, 2021, s. 469–497. doi: 10.1007/978-1-4842-7185-8_30. 
[2]	”Caustic (optics)”, Wikipedia. 08 februari 2026. Åtkomstdatum: 20 februari 2026. [Online]. Tillgänglig vid: https://en.wikipedia.org/w/index.php?title=Caustic_(optics)&oldid=1337319409 


