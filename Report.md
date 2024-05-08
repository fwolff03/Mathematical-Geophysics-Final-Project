# Final Report on Saint-Venant Equations
## By Max Ercolani and Finley Wolff

### Description of PDE, Applications

The St. Venant system of equations models unsteady open channel flows. The equations solve for discharge (volume/time), and wetted area of the channel. This allows modelling of systems such as rivers, stormwater systems, irrigation channels, hydropower channels, and spillway systems, to optimize those sytems, and to avoid flooding [1][2]. There are a variety of assumptions made when using the St. Venant equations, and these are most compatible with artificial channels that have very simple and consistent geometries, paths, etc. Therefore, the greatest use of the St. Venant equations are for designing and monitoring channels for irrigation, stormwater, and spillways. This allows engineers and officials to predict when floods might be possible, and based on a variety of factors, how much discharge there could be, and how much the channel could overflow.

![damage-Artboard_1](https://github.com/fwolff03/Mathematical-Geophysics-Final-Project/assets/156112784/63ffa5c0-f5fb-4c2b-aa58-1175cfee1942)

In the above figure from the [New York Times](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.nytimes.com%2Finteractive%2F2017%2F02%2F13%2Fus%2Foroville-dam.html&psig=AOvVaw29LTzNBueH3xNPRz2CeKEh&ust=1715231428174000&source=images&cd=vfe&opi=89978449&ved=0CBQQjhxqFwoTCLC7zJOl_YUDFQAAAAAdAAAAABBF) the Lake Oroville dam spillway is shown. While the failure shown was not due to any explicit application or non-application of the St. Venant equations, it does show how important water infrastructure is to our country, and why we should take great effort in designing water channels.

### Description of PDE, All Variables and Behavior

The Saint-Venant Equations are a set of two partial differential equations, commonly known as the Shallow Water Equations. It consists of the continuity or conservation of mass equation and conservation of momentum equation which simulate the movement of unsteady flows in open channels [3]. The conservation mass equation is linear while the conservation of momentum equation is non-linear. When looking at the Saint-Venant Equations, shallow flow is defined as the water depth being small when compared to the width of the body of water. This can be seen in manmade river canals, farm ditches, river and streams. 

When looking at one dimensional Saint-Venant Equations, the dimension we are looking at is the spacial dimension. This means that the depth is assumed to be uniform across the width of the channel and the fluid's velocity is uniform in both the depth and width. In this case, we assume that the vertical acceleration and the hydrostatic pressure are negligible and that the streamline curvature is negligible. Although the one-dimension Saint-Venant Equations are simplified, they are still useful for understanding water movements in different water channels. 

In this study, we will be looking at the steady state 1D Saint-Venant Equations. The steady state assumes that the set of one dimensional equations [4] are not dependent on time, which will simplify our equations and simulation. The resulting equations when looking at the steady state 1D Saint-Venant Equations are [5][6]:  

Equation 1 $$\frac{\partial(uh)}{\partial x} = 0$$

Equation 2 $$\frac{\partial(u^2h + \frac{gh^2}{2})}{\partial x} = -gh\frac{\partial xz}{\partial x} - ghSf$$

![IMG_0087](https://github.com/fwolff03/Mathematical-Geophysics-Final-Project/assets/156112882/6aa8aeef-67cb-4840-8c5b-e2ba2a2dd831)

In these equations and diagram, the variable u represents the velocity of water in the channel and is measured in meters per second. The variable h is the water's height in the channel or depth and is measured in meters. Gravity is shown by g, and for this study we will assume the gravitational acceleration is 9.81 meters per second. The bed level is shown by z and is measured in meters. Finally, Sf represents the friction slope. Sf is calculated by: 

$S_f = \frac{n^2 |u| u}{h^{4/3}}$

where n is the Mannings coefficient which shows the roughness of a surface, u is the stream velocity, and h is the depth of the stream at a certain spot along the length of the channel. 

When the Saint-Venant PDE’s are in a steady state, their behavior shows the balance between the forces driving the flow of a channel of water and the forces resisting the flow. The gravitational forces are driving the flow of water while friction is resisting the flow. This balance comes after there has been enough time for the conservation of mass and conservation of momentum equations to reach equilibrium.  

### Limitations of PDE and Simplifying Assumptions

The one dimensional version of the St. Venant System of Equations operate on many basic assumptions about flow. First of all, the flow is one dimensional, this means that the two functions are velocity and water depth. The first assumption is the velocity of the channel is uniform across the cross section of flow, meaning the flow only has one value at any position (x) and time (t) along the channel. The second assumption is Manning's equation 
for friction ($S_f$). The third assumption is a low incline of the channel and flow, meaning a very flat channel. The fourth assumption is that the water (or fluid) has a constant denisty, and is thus incompressible. Lastly, we assume that there is no sediment movement from transportation or deposition [1][3].

We have derived Equations 1 and 2 using a similar approach to Thi in a research paper on the 1 dimensional St. Venant Equations [4]. We have gone a step further in assuming a steady state solution to the one dimensional St. Venant System of Equations. All of the time dependent terms are removed, and the equations are reduced to:

Equation 1: $$\frac{\displaystyle \partial (uh)}{\displaystyle \partial x}  = 0$$

Equation 2: $$\frac{\displaystyle \partial (u^2h)}{\displaystyle \partial x} + \frac{\displaystyle g}{\displaystyle 2}\frac{\displaystyle \partial (h^2)}{\displaystyle \partial x} + (\frac{\displaystyle (uh)^2}{\displaystyle h^2} - gh)\frac{\displaystyle \partial h}{\displaystyle \partial x} + (1 + gh) \frac{\displaystyle n^2u|u|}{\displaystyle h^{4/3}} = 0$$

### Complete description of first PDE simulation and interaction with software package

We completed our first steady state 1 dimensional simulation of the Saint-Venant Equations, or the Shallow Water Equations was done with the SWE_Solver with Python. The SWE_Solver, which stands for the Shallow Water Equation Solver, was created by Daniel Cortild and is public on GitHub. It solves shallow water equations such as the Saint-Venant partial differential equations. Below is a photo of an example of the code used to run the SWE_Solver.

![image](https://github.com/fwolff03/Mathematical-Geophysics-Final-Project/assets/156112882/589b6a59-6d96-48f8-93a0-fe5604d4a960)

The SWE_Solver it takes the input, B or the bottom topography function, which defines the topographic profile. It takes spatial coordinates as an input and returns the bottom height at each of those coordinates. Since our simulation is in 1 dimension, this function is only with respect to x, or the length of the channel meaning the bottom topography is consistent across the width of the channel. Additionally, it takes an input of Nx or the number of spatial grid point. It also requires the input h0, or the water height profile. It takes an array that must be the same length as Nx. The solver also takes an input of u0 or the water velocity profile. This also takes an input of an array that must be the same length as Nx. Finally, it uses the inputs of tEnd and timePoints. While we are trying to simulate the steady state of the 1d Saint-Venant equations, this solver requires these inputs. In attempt to navigate these inputs, I initially set tEnd to a large number, 100, however, it took nearly 20 minutes to run. After some testing, using similar initializing to the SWE_Solvers example for steady states, I found the water heights to nearly converge around nearly 15 seconds, which I show in my initial simulation. In the simulation, g is the gravitational constant and for this simulator, a g value of 1 is “normal”. Additionally, they take an input of a method which is how they solve the equations. While there was no written documentation on how the methods, A, B, C and D differ, after looking at the code and some of my own experimentation, I found method C to be their default method and I found method A to have the quickest run time. I decided to use method A to make the simulations more efficient. When you run plotSWE, it outputs h and u. The array h contains the water height profile at the final time point and u is an array with the water velocity profile at the final time point. The SWE_Solver does not include viscosity and bottom friction, which is something to be aware of when comparing this to our other equations, diagrams and proofs of linearity. 

### Interpretation of results from first PDE simulation

![image](https://github.com/fwolff03/Mathematical-Geophysics-Final-Project/assets/156112882/882ab23a-0062-48a7-a6b8-d668218abd06) 

This simulation has a Nx equal to 50 or 50 spatial grid points. I found 50 to be an adequate amount without making the simulation rather inefficient. The bottom topography in the simulation is -x or a down sloping bottom with a slope of -1. The water height profile is defined as [2 - B(_ / (Nx-1)) for _ in range(Nx)] which was standard in their simulations. I defined the initial stream velocity similar to their examples as well by 5 for _ in range(Nx). The end time is set to 15 seconds, which as discussed previously, is where I found the happy medium between nearly steady state and an acceptable run time. For the purpose of showing this in the initial visualization, I am plotting the water height at t = 0, t=7, t=14 and t=15. In the figure, you can see the y axis is depth and the x axis is the length of the channel which you can not change in the simulation. The blue line represents the water height at t=0 or the beginning of the simulation. The blue line sits at a constant height of 2 meters. When t=7, you can see the water height is nearly 1.63 meters at x=0. Then after another 7 seconds, it decreases to 1.4 at x=0. Then at t=15 it is just slightly below 1.4 at x=0. These three are all parallel meaning the water height decreases proportionally throughout the length of the channel which would make sense in a 1D steady state version of the Saint-Venant equations. 

### Description of linearity and superposition principles

We evaluated the linearity of both equations using the (assumed) linear operators $L_1$ and $L_2$ which represent the PDEs. We used the definition of linearity that if $L_1(u, h) = L_1(au_1 + bu_2, h)$ or $L_2(u, h) = L_2(u, ah_1 + bh_2)$ where *a* and *b* are constants in $\mathbb{R}$,where *a* and *b* are constants in $\mathbb{R}$,

then, if $L_1(au_1 + bu_2, h) = aL_1(u_1, h) + bL_1(u_2, h)$, then the PDE is linear.

For Equation 1:

$L_1(au_1 + bu_2, h) = 0$

$\frac{\displaystyle \partial (au_1 + bu_2) h}{\displaystyle \partial x}= 0$

$a\frac{\displaystyle \partial u_1h}{\displaystyle \partial x} + b\frac{\displaystyle \partial u_2h}{\displaystyle \partial x} = 0$

$= aL_1(u_1, h) + bL_1(u_2, h)$

and

$L_2(u, ah_1 + bh_2) = 0$

$\frac{\displaystyle \partial u (ah_1 + bh_2)}{\displaystyle \partial x}= 0$

$a\frac{\displaystyle \partial uh_1}{\displaystyle \partial x} + b\frac{\displaystyle \partial uh_2}{\displaystyle \partial x} = 0$

$= aL_1(u, h_1) + bL_1(u, h_2)$ 

**Therefore, Equation 1 is linear**

For Equation 2:

$L_1(au_1 + bu_2, h) = 0$

$\frac{\displaystyle \partial ((au_1 + bu_2)^2h)}{\displaystyle \partial x} + \frac{\displaystyle g}{\displaystyle 2}\frac{\displaystyle \partial (h^2)}{\displaystyle \partial x} + (\frac{\displaystyle ((au_1 + bu_2)h)^2}{\displaystyle h^2} - gh)\frac{\displaystyle \partial h}{\displaystyle \partial x} + (1 + gh) \frac{\displaystyle n^2(au_1 + bu_2)|(au_1 + bu_2)|}{\displaystyle h^{4/3}} = 0$

Because of the various instances of the polynomial (au_1 + bu_2) being squared, the left hand side of the equation cannot be manipulated into the form of:

$aL_1(u, h_1) + bL_1(u, h_2)$

meaning, $L_1(au_1 + bu_2, h) \neq aL_1(u, h_1) + bL_1(u, h_2)$.

Equation 2 is, therefore, a **non linear PDE**

#### Superposition

Equation 1 is linear and homogeneous, 

assume $q = uh$

$(q)= (q_1 + q_2)$ where *a* and *b* are constants in $\mathbb{R}$,

$g(q_1x + q_2x) = L_1(aq_1 + bq_2)$

$g = a_0L(q_1) + b_0L(q_2)$

$g = a_0g + b_0g$

$a_0 + b_0 = 1$

Thus, Equation 1 **has a property of superposition** if the coefficients of the solutions of the homogeneous equation being combined sum to 1.

Equation 2 is non linear, and inhomogeneous, and thus **does not have any property of superposition**

### Full description of computational experiments’ comparison to check validity of linearity and superposition principles

To complete a computational experiment to check the validity of the linearity and superposition principles, we have decided to run the initial simulation and change the initial conditions for height and stream velocity. We are going to double the initial height first and see if it has a linear relationship on the steady state height or the height at t=15. Then we are going to return to the initial height and double the initial stream velocity. We will see if this has a linear relationship on the steady state water depth. As described above, if a system of PDEs have a principle of superposition, that means that any combination of any solutions to the linear PDE is also a solution. While we have determined that the 1D steady state St. Venant system of equations is non-linear, this computational experiment will justify that hypothesis. To check the validity of our understanding of the linearity and superposition principles of our PDE system, we have decided to run the initial simulation, changing the boundary conditions for height and stream velocity. If one solution with certain boundary conditions is a consistent solution, then doubling those boundary conditions, which is effectively combining those solutions together, should yield a solution that has a linear relationship with the first solution. This would look like a water depth that is changed by a factor of two, or a velocity that has been changed by a factor of two. We will double the boundary height first and see if there is a linear relationship between the steady state height and the height at a time of 15. Then we are going to return to the boundary height and double the boundary stream velocity. We will determine if there is a linear relationship between the steady state water depth, and the water depth at a time of 15. 

### Description of results and interpretation of computational experiments’ comparison to check validity of linearity and superposition principles

In the figure shown below, we expiremented with doubling the boundary water depth value. This yields different values for the system, but a very similar slope of water depth with increasing position (x). This would suggest a linear relationship between the boundary water depth and the water depth solution, as the values are different, but have similar, if not equal, trends.

![Screenshot (156)](https://github.com/fwolff03/Mathematical-Geophysics-Final-Project/assets/156112882/282a05c5-864c-4be6-a90c-dffd07c4445f)


In the next figure, we doubled the velocity. This yields a very different solution to the water depth, with a much different slope with increasing position (x). This reveals a non-linear relationship, at least between the boundary velocity value, and the water depth solution. 

![Screenshot (157)](https://github.com/fwolff03/Mathematical-Geophysics-Final-Project/assets/156112882/b96c3c63-d0be-4217-81da-b89d7f47023a)

Because any non-linear relationships, even when accompanied by linear relationships, reveal a system to be non-linear, we have determined our expirement to have proved our hypothesis. The steady state solution to the 1D St Venant system of equations is indeed non-linear.

### Sources

[1] H. Chanson, “16 - Unsteady open channel flows: 1. Basic equations,” in Hydraulics of Open Channel Flow, Second., Butterworth-Heinemann, 2004. https://doi.org/10.1016/B978-075065978-9/50023-4 (accessed May 7, 2024).

[2] H. Chanson, “Saint‐Venant Equations & the simplification of the Dynamic equation,” YouTube, https://www.youtube.com/watch?v=s1uZ6FFdivI (accessed May 7, 2024). 

[3] C. Hewett, “1D hydrodynamic models,” YouTube, https://www.youtube.com/watch?v=FHLCbNClRFY (accessed May 7, 2024). 

[4] Ngoc Tuoi Vo Thi. One dimensional Saint-Venant system. Analysis of PDEs [math.AP]. 2008. ffdumas00597434f

[5] D. Cortild, “Well-Balanced Schemes for Shallow Water Equations,” github.com, https://github.com/DanielCortild/SWE-Solver/blob/main/paper.pdf (accessed May 5, 2024). 

[6] One dimensional Saint-Venant System - Dumas, https://dumas.ccsd.cnrs.fr/dumas-00597434v1/document (accessed May 8, 2024). 
