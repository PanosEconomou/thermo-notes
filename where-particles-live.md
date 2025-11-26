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

This leads to the third, most powerful, yet at the same time most underrepresented piece of the phase space. **A way to take a function, like a Hamiltonian, and convert it to a flow over the space**. 

We said that a Hamiltonian, i.e. an energy function over phase space, defines the physics of our system. What we mean by that, is that if we know the phase space and the Hamiltonian we should be able to predict where the particle will move to in the future given an initial point. In other words it looks like all of these ingredients define a **flow** of points in phase space. 

There are many ways to define flows in math, but perhaps one of the more useful to work with is **vector fields**. So somehow we need to covert our Hamiltonian function to a vector field. The machinery that does this is a **Poisson bracket,** or equivalently a **symplectic form.**

While you may be familiar with these structures from classical mechanics, we will not be needing them explicitly. What we will need however, is the following idea.

> A **Hamiltonian** on a phase space can be converted into a **flow**. The physical system follows this flow over time.



# Equipartition Theorem

Now we are finally getting to cool statistical mechanics. As we said a statistical mechanics theory cares about defining an additional piece of structure on the phase space of the system which is a **probability distribution.** If we have this probability distribution we can then do all the stuff we need such as taking statistical averages, moments, looking at interesting consequences, and more.  

## The Probability Distribution

We have seen that the probability distribution is proportional to
$$
e^{-\beta H},
$$
where $H:M\to \mathbb{R}$ is the Hamiltonian ($M$ is the phase space), and $\beta \in \mathbb{R}$ is the inverse of the temperature. the probability distribution might have other factors, but it must always be proportional to this one. Sometimes the probability distribution will be proportional to $e^{-\beta (H + \mu N)}$ where $N$ is the number of particles in the big system, or even other stuff. 

But let's stick with the simplest case for now where the probability is directly proportional to $e^{-\beta H}$ (by the way, this is called the **canonical ensemble** but that name is not important for what we are about to show). In this case we can calculate the partition function as
$$
Z  = \int_M e^{-\beta H} dM, 
$$
where $dM$ is a notation for the volume measure of $M$ for example if $M = \mathbb{R}^{100}$ we would usually write something like $dM = d^{100}x$.  Therefore the probability distribution is given by the function $\rho : M \to \mathbb{R}$ defined by
$$
\rho = \frac{e^{-\beta H}}{Z}.
$$
Now that we have this we can take averages and all the good stuff. For example given a function $f: M \to \mathbb{R}$ we can find its **thermodynamic average** $\langle f\rangle$ by taking
$$
\langle f \rangle = \int_M f \,\rho\, dM = \frac{1}{Z}\int_M f e^{-\beta H} dM.
$$


## Does the probability distribution move over time?

If we have a Hamiltonian we have discussed that it defines a way for the points of phase space to *flow* over time. Since the probability is a function of phase space and the points of phase space can move why shouldn't we be expecting it to do the same?

This seems reasonable until you say: **"WAIT WHAT?** I thought the point of thermodynamics was the we didn't care about time, and suddenly you tell me that the probability distribution itself can change over time? What gives?"

This realization led to the famous equipartition theorem. The key point is that the probability distribution can move over time, but never in a way such that it changes the thermodynamic averages. Let's see how this works



## Quantifying Probability Spreading

So the probability distribution must be spreading. It would be interesting to quantify by how much. Often though taking something like the average spreading distance is cumbersome and unusable, so what if we ask how much **energy does is used** for spreading along a direction? This answer to this is going to be $\frac{1}{\beta}= kT$ and then we will call this the equipartition theorem. But let's take things step by step.

It's finally time to put some coordinates $(x^1,x^2,\cdots, x^N)$ on our phase space $M$. Therefore we can write the Hamiltonian $H:M\to \mathbb{R}$ as a function of these coordinates. If the system is near point $p \in M$ in the phase space then what is the force it feels to nudge it away?

This might seem a hard question to ask in a general system, however we shouldn't forget that we have the Hamiltonian, and the force to nudge the particle in direction $x^i$ is simply
$$
F_i = \frac{\partial H}{\partial x^i}.
$$
The energy that was spent during that nudging we already know is $x^i F_i$ by the definition of work. Therefore the question we can ask is what is the average energy for nudging the system along the direction $x^i$? Well it is this:
$$
\langle x^iF_i \rangle = \langle x^i \frac{\partial H}{\partial x^i} \rangle.
$$
So here is the theorem,

**<u>Theorem:</u>** *(Equipartition Theorem)* The average energy spent to move in any direction in phase space is $\frac{1}{\beta}$. In other words
$$
\langle x^i \frac{\partial H}{\partial x^j} \rangle = \frac{\delta^i_j }{\beta}= \delta^i_j kT.
$$
 ***Proof:*** This is a remarkable result! The proof is done by integration by parts. Notice that
$$
\frac{\partial \rho}{\partial x^i} = -\beta\frac{\partial H}{\partial x^i} \rho.
$$
Therefore we have that
$$
\langle x^i \frac{\partial H}{\partial x^j} \rangle = \int_M x^i \frac{\partial H}{\partial x^j} \rho\, dM = -\frac{1}{\beta} \int_M x^i \frac{\partial \rho}{\partial x^j}dM = \frac{\delta^i_j}{\beta} \int_M \rho\, dM =\frac{\delta^i_j}{\beta} .
$$
Where we have used integration by parts assuming that $\partial M = \empty$.
$$
\begin{equation}\tag*{$\Box$}\end{equation} 
$$
The proof is just application of integration by parts, but the result is incredible! It says that if the Hamiltonian depends on $x^i$, i.e. $\frac{\partial H}{\partial x^i} \neq 0$ then the average energy needed for the system to move in that direction is the same regardless of the direction! 



## Side-Benefit Thermodynamic Degrees of Freedom

The interesting thing that we have apart from this incredible theorem is that we have stumbled upon a pretty intuitive definition of thermodynamic degrees of freedom. 

> A thermodynamic degree of freedom is a direction in phase space along which the energy changes. Or in better words
>
> A **thermodynamic degree of freedom** is any degree of freedom of the system that **contributes to its total energy**.

**<u>Example:</u>** *(Ideal Gas)* The Hamiltonian for an ideal gas of $N$ particles is the sum of the momenta. Namely
$$
H = \sum_{i=1}^N \frac{1}{2m} \sum_{j=1}^3 (p_i^j)^2.
$$
Notice that while there are $6N$ degrees of freedom int he phase space, only the ones corresponding to the momentum directions contribute to the energy. So there are $3N$ thermodynamic degrees of freedom.







