# Final Report on Saint-Venant Equations
## By Max Ercolani and Finley Wolff

### Description of PDE, applications (250-400 words, 1-2 figures)

### Description of PDE, all variables and behavior (400-600 words, 1-2 figures)

The Saint-Venant Equations are a set of two partial differential equations, commonly known as the Shallow Water Equations. It consists of the continuity or conservation of mass equation and conservation of momentum equation which simulate the movement of unsteady flows in open channels. The conservation mass equation is linear while the conservation of momentum equation is non-linear. When looking at the Saint-Venant Equations, shallow flow is defined as the water depth being small when compared to the width of the body of water. This can be seen in manmade river canals, farm ditches, river and streams. 

When looking at one dimensional Saint-Venant Equations, the dimension we are looking at is the spacial dimension. This means that the depth is assumed to be uniform across the width of the channel and the fluid's velocity is uniform in both the depth and width. In this case, we assume that the vertical acceleration and the hydrostatic pressure are negligible and that the streamline curvature is negligible. Although the one-dimension Saint-Venant Equations are simplified, they are still useful for understanding water movements in different water channels. 

In this study, we will be looking at the steady state 1D Saint-Venant Equations. The steady state assumes that the set of equations are not dependent on time, which will simplify our equations and simulation. The resulting equations when looking at the steady state 1D Saint-Venant Equations are:  

1) $\frac{\partial(uh)}{\partial x} = 0$

2) $\frac{\partial(u^2h + \frac{gh^2}{2})}{\partial t} = -gh\frac{\partial xz}{\partial x} - ghSf$

In these equations, the variable u represents the velocity of water in the channel and is measured in meters per second. The variable h is the water's height in the channel or depth and is measured in meters. Gravity is shown by g, and for this study we will assume the gravitational acceleration is 9.81 meters per second. The bed level is shown by z and is measured in meters. Finally, Sf represents the friction slope. Sf is calculated by: 

$S_f = \frac{n^2 |u| u}{h^{4/3}}$
where n is the Mannings coefficient which shows the roughness of a surface, u is the stream velocity, and h is the depth of the stream at a certain spot along the length of the channel. 

When the Saint-Venant PDE’s are in a steady state, their behavior shows the balance between the forces driving the flow of a channel of water and the forces resisting the flow. The gravitational forces are driving the flow of water while friction is resisting the flow. This balance comes after there has been enough time for the conservation of mass and conservation of momentum equations to reach equilibrium.  

### Limitations of PDE or simplifying assumptions (100-200 words)

### Complete description of first PDE simulation and interaction with software package (300-500 words, 1-2 figures)

### Interpretation of results from first PDE simulation (200-350 words, 1-2 figures)

### Description of linearity and superposition principles as applicable (200-350 words and must include blocks of equations or math work, can include diagrams as needed)

### Full description of computational experiments’ comparison to check validity of linearity or superposition principles (250-350 words, 1 figure)

### Description of results and interpretation of computational experiments’ comparison to check validity of linearity of superposition principles (150-250 words, 1-2 figures)
