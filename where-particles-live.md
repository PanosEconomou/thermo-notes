# Phase Spaces

Here we explore one of the most foundational concepts in physics, the Phase space! We will use it as a way to motivate our statistical physics exploration, as well as provide some visuals that should come up when we use it. 

[toc]

# States form a Shape

A phase space is a physicist's wet dream. In some loose sense, every point in a phase space contains all the data we need about the state of a system to predict its future evolution. We then package these points with a notion of **closeness** and turn it into a shape!

> **<u>Loose Definition:</u>** A **phase space** is the shape formed by placing all possible initial conditions next to each other.

This is a useless definition, but it is the motivating principle behind one of the most central tools in statistical physics. Here are some examples.

**<u>Example:</u>** *(Single Particle)* Given a single particle living in 3D all the information we really need to specify its future are its momentum and position. Therefore its phase space is $M = \mathbb{R}^3\times \mathbb{R}^3 = \mathbb{R}^6$. Each point in $\mathbb{R}^6$ can be described using $6$ numbers. The $3$ coordinates of the particle in space, and the $3$ momenta of the particle.

**<u>Example:</u>** *(Pendulum)* A pendulum with a sufficiently taught string is confined to move in a circle. Yet the momentum can be anything! Its position on the circle and its momentum are all the ingredients we need to describe its motion, therefore its phase space $M = S^1 \times \mathbb{R}$ is a Tube! By the way we often picture it as a plane with the ends identified, but it has always been a tube. 

**<u>Example:</u>** *(Multiple particles)* If one particle in 3D needs 6 numbers to specify its state, then 2 particles will need 6 each = 12! So $N$ particles need $6N$ real numbers to specify their state resulting in $M = \mathbb{R}^{6N}$ as the phase space. This is a super large phase space - for any practical purpose $N=10^{23}$ - but its amazing that we can actually productively work in it.

## Hamiltonian

Yet that seems wrong. What if there is an electric field? What if the particle is in a vacuum, or experiencing turbulence? We clearly need more information than $\mathbb{R}^6$ can provide us with.  Here is where the **Hamiltonian comes in**. Without it while we would perfectly know where the particle is we would have no idea how to predict where it's gonna go!

**<u>Definition:</u>** A **Hamiltonian** is any smooth real function $H:M \to \mathbb{R}$. A **physical Hamiltonian** is a smooth real function such that it is bounded from below.

This is a slightly more technical definition, even though extensions exist that allow us to think beyond smoothness. From a physics point of view the Hamiltonian is the energy function, which is why it has to be typically bounded from below. The discovery that the energy function of your system fully encapsulates its time evolution is incredible!

Think about it, you only need to know how your system acquires energy at different states to know how it will evolve in the future. We have essentially boiled down the *foundational problem of physics* in simply searching for the right energy formula. 



## Symplectic Forms (AKA Poisson Brackets)

> But I hear you say: **So what? We have a function, and? How does that give us where the system will be in the future?**   

This leads to the third, most powerful, yet at the same time most underrepresented 











