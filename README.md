# First blog Post!

## 1\. Background

As light passes through water, metallic or transparent surfaces, the refraction of light causes a phenomenon known as caustics. Caustics are famously difficult to simulate with a limited time budget \[1\], leading to them being ignored or roughly handled.

![][image1]  
Fig 1: Caustics created from light passing through the surface of the water \[2\].

The brighter parts of the surface are where the light converges, while the darker parts are where light diverges, as can be seen in Fig 2\. The refraction happens according to Snell’s law: 

$n_1 \sin(\theta_1) = n_2 \sin(\theta_2)$

Where n represents the refraction index and θ represents the angle of light as well as the refraction angle. What causes the different wavelengths of light to refract differently, which can be seen in Fig 1, is that water has different refractive indices for different wavelengths.

![][image2]  
Fig 2: How light diverges and converges to create caustics\[5\].

## 2\. Implementation specifics (as many as possible)

The main implementation will be created in Blender using a method showcased by the YouTube-channel 3Dan \[3\]. The approach is done through Blender’s geometry nodes feature and uses a similar mesh-based projection methodology to Evan Wallace’s 2011 WebGL based realtime water and caustics simulation \[4\]. In this method, every vertex of a mesh is treated like a light ray and traced down to a different mesh, where the triangles (or rectangles, depending on the geometry chosen) with a smaller area represent where the light is brighter and larger area where the light is darker.

![][image3]  
Fig 3: Mesh based light refraction method \[4\].

This creates a faster way of simulating caustics than true ray tracing, however the method in 3Dan’s video has some limitations. For one, it does not visualise the paths of the light rays, nor does it simulate the light dispersion in a physically accurate way. This we feel that we can improve on through our project.

For accurate light dispersion we will either be trying to use Snell’s law for different wavelengths individually or take inspiration from another project from this course \[6\] and use the Sellmeier equation:

$$ n^2(\lambda) = 1 + \sum_i \frac{B_i \lambda^2}{\lambda^2 - C_i} $$

where C and B represent the Sellmeier coefficients for water and air.

## 3\. Specifics of what the final system will look like and do

The main part of the system will be using the method described in Fig 3, with Blender’s ocean modifier being used to create the waves. The base of how this will look can be seen in Fig 4 bwloe. From there we will add lines that show the projection of vertices as well as implement physically accurate dispersion based on the different refractive indexes of water for different wave lengths.

![][image4]  
Fig 4: Screenshot from 3Dan’s video tutorial on simulating caustics in Blender \[3\].

We also want to add more user control to further explore the simulation of caustics, where the user will be able to control:

* Direction of light  
* Amount of light rays  
* Ability to see lightray path.   
* Type of liquid (index of refraction and Sellmeier equation)

## 5\. Potential risks/challenges

The main risk is that we are too ambitious, and want to do too much, which we will attempt to avoid by prioritising certain tasks and have other tasks be ones we can do if we have time left over. While realtime isn’t the main focus of our simulation, there is still a risk that our work will be slowed down by Blender’s typically computationally intensive processes. There’s also a risk that Blender doesn’t have the tools available for our goals of this project, however this seems like a relatively small risk.

## 6\. Degree of simulation

The simulation will rely entirely on Blender’s built-in physics system. Rather than implementing custom physics from the ground up, the project will follow an existing Blender tutorial and use Blender’s native physics libraries and solvers to handle all physical interactions.

7\. Link to blog containing first blog entry: [https://togezard.github.io/DD1354-project/](https://togezard.github.io/DD1354-project/)   
We aim to reach as high of a grade as possible, ideally an A.

## Bibliography

\[1\]	X. Yang och Y. Ouyang, ”Real-Time Ray Traced Caustics”, i *Ray Tracing Gems II: Next Generation Real-Time Rendering with DXR, Vulkan, and OptiX*, A. Marrs, P. Shirley, och I. Wald, Red., Berkeley, CA: Apress, 2021, s. 469–497. doi: 10.1007/978-1-4842-7185-8\_30.   
\[2\]	”Caustic (optics)”, *Wikipedia*. 08 februari 2026\. Åtkomstdatum: 20 februari 2026\. \[Online\]. Tillgänglig vid: https://en.wikipedia.org/w/index.php?title=Caustic\_(optics)\&oldid=1337319409   
\[3\]	3Dan, *Simulating Caustics In Blender*, (07 oktober 2025). Åtkomstdatum: 27 februari 2026\. \[Online Video\]. Tillgänglig vid: https://www.youtube.com/watch?v=EOGS73npKsI   
\[4\]	E. Wallace, ”Rendering Realtime Caustics in WebGL”, Medium. Åtkomstdatum: 27 februari 2026\. \[Online\]. Tillgänglig vid: https://medium.com/@evanwallace/rendering-realtime-caustics-in-webgl-2a99a29a0b2c   
\[5\]	L. Jacobson och A. Stenkrona, ”Water Caustics and Water Simulation”, 2020\. \[Online\]. Tillgänglig vid: https://fileadmin.cs.lth.se/cs/Education/EDAN35/projects/20ArneLinus\_Water.pdf   
\[6\]	”Simulating optics”, Simulating optics. Åtkomstdatum: 27 februari 2026\. \[Online\]. Tillgänglig vid: https://simulatingoptics.wordpress.com/   


[image1]: img/caustic_wiki

[image2]: img/light_path

[image3]: img/light_mesh

[image4]: img/caustics_video_example.png
