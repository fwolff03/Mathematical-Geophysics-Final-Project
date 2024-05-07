# Final Report on Saint-Venant Equations
## By Max Ercolani and Finley Wolff

### Description of PDE, applications (250-400 words, 1-2 figures)

The St. Venant system of equations models unsteady open channel flows. The equations solve for discharge (volume/time), and wetted area of the channel. This allows modelling of systems such as rivers, stormwater systems, irrigation channels, hydropower channels, and spillway systems, to optimize those sytems, and to avoid flooding [1][2]. There are a variety of assumptions made when using the St. Venant equations, and these are most compatible with artificial channels that have very simple and consistent geometries, paths, etc. Therefore, the greatest use of the St. Venant equations are for designing and monitoring channels for irrigation, stormwater, and spillways. This allows engineers and officials to predict when floods might be possible, and based on a variety of factors, how much discharge there could be, and how much the channel could overflow.

### Description of PDE, all variables and behavior (400-600 words, 1-2 figures)

The Saint-Venant Equations are a set of two partial differential equations, commonly known as the Shallow Water Equations. It consists of the continuity or conservation of mass equation and conservation of momentum equation which simulate the movement of unsteady flows in open channels [3]. The conservation mass equation is linear while the conservation of momentum equation is non-linear. When looking at the Saint-Venant Equations, shallow flow is defined as the water depth being small when compared to the width of the body of water. This can be seen in manmade river canals, farm ditches, river and streams. 

When looking at one dimensional Saint-Venant Equations, the dimension we are looking at is the spacial dimension. This means that the depth is assumed to be uniform across the width of the channel and the fluid's velocity is uniform in both the depth and width. In this case, we assume that the vertical acceleration and the hydrostatic pressure are negligible and that the streamline curvature is negligible. Although the one-dimension Saint-Venant Equations are simplified, they are still useful for understanding water movements in different water channels. 

In this study, we will be looking at the steady state 1D Saint-Venant Equations. The steady state assumes that the set of one dimensional equations [4] are not dependent on time, which will simplify our equations and simulation. The resulting equations when looking at the steady state 1D Saint-Venant Equations are:  

1) $\frac{\partial(uh)}{\partial x} = 0$

2) $\frac{\partial(u^2h + \frac{gh^2}{2})}{\partial x} = -gh\frac{\partial xz}{\partial x} - ghSf$

In these equations, the variable u represents the velocity of water in the channel and is measured in meters per second. The variable h is the water's height in the channel or depth and is measured in meters. Gravity is shown by g, and for this study we will assume the gravitational acceleration is 9.81 meters per second. The bed level is shown by z and is measured in meters. Finally, Sf represents the friction slope. Sf is calculated by: 

$S_f = \frac{n^2 |u| u}{h^{4/3}}$
where n is the Mannings coefficient which shows the roughness of a surface, u is the stream velocity, and h is the depth of the stream at a certain spot along the length of the channel. 

When the Saint-Venant PDE’s are in a steady state, their behavior shows the balance between the forces driving the flow of a channel of water and the forces resisting the flow. The gravitational forces are driving the flow of water while friction is resisting the flow. This balance comes after there has been enough time for the conservation of mass and conservation of momentum equations to reach equilibrium.  

### Limitations of PDE or simplifying assumptions (100-200 words)

The one dimensional version of the St. Venant System of Equations operate on many basic assumptions about flow. First of all, the flow is one dimensional, this means that the two functions are velocity and water depth. The first assumption is the velocity of the channel is uniform across the cross section of flow, meaning the flow only has one value at any position (x) and time (t) along the channel. The second assumption is Manning's equation 
for friction ($S_f$). The third assumption is a low incline of the channel and flow, meaning a very flat channel. The fourth assumption is that the water (or fluid) has a constant denisty, and is thus incompressible. Lastly, we assume that there is no sediment movement from transportation or deposition [1][3].

We have gone a step further in assuming a steady state solution to the one dimensional St. Venant System of Equations. All of the time dependent terms are removed, and the equations are reduced to:

Equation 1: $$\frac{\displaystyle \partial (uh)}{\displaystyle \partial x}  = 0$$

Equation 2: $$\frac{\displaystyle \partial (u^2h)}{\displaystyle \partial x} + \frac{\displaystyle g}{\displaystyle 2}\frac{\displaystyle \partial (h^2)}{\displaystyle \partial x} + (\frac{\displaystyle (uh)^2}{\displaystyle h^2} - gh)\frac{\displaystyle \partial h}{\displaystyle \partial x} + (1 + gh) \frac{\displaystyle n^2u|u|}{\displaystyle h^{4/3}} = 0$$

- 1D flow, velocity is uniform across the cross section of flow.

- Minimal curvature of the stream, there is no stratification of the water, or differences in pressure vertically.

- Manning's equation for friction

- Low incline of flow. The bed slope $\theta$ is small enough to satisfy $cos\theta \approx 1$, and $sine\theta \approx tan\theta$

- Fluid maintains a constant density (incompressible)

- No sediment transport or deposition

We have derived Equations 1 and 2 using a similar approach to Thi in a research paper on the 1 dimensional St. Venant Equations [3]. We dec

### Complete description of first PDE simulation and interaction with software package (300-500 words, 1-2 figures)

### Interpretation of results from first PDE simulation (200-350 words, 1-2 figures)

### Description of linearity and superposition principles as applicable (200-350 words and must include blocks of equations or math work, can include diagrams as needed)

### Full description of computational experiments’ comparison to check validity of linearity or superposition principles (250-350 words, 1 figure)

### Description of results and interpretation of computational experiments’ comparison to check validity of linearity of superposition principles (150-250 words, 1-2 figures)

### Sources

[1] H. Chanson, “16 - Unsteady open channel flows: 1. Basic equations,” in Hydraulics of Open Channel Flow, Second., Butterworth-Heinemann, 2004. https://doi.org/10.1016/B978-075065978-9/50023-4 (accessed May 7, 2024).

[2] H. Chanson, “Saint‐Venant Equations & the simplification of the Dynamic equation,” YouTube, https://www.youtube.com/watch?v=s1uZ6FFdivI (accessed May 7, 2024). 

[3] C. Hewett, “1D hydrodynamic models,” YouTube, https://www.youtube.com/watch?v=FHLCbNClRFY (accessed May 7, 2024). 

[4] Ngoc Tuoi Vo Thi. One dimensional Saint-Venant system. Analysis of PDEs [math.AP]. 2008. ffdumas00597434f
