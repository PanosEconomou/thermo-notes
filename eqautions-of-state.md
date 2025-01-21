# Equations of State

Let’s understand equations of state from the ground up. We will begin by talking about thermodynamic theories and building up a framework to describe them from scratch.

[toc]

# Equilibrium

To even understand what equilibrium is, we first need to understand what a termodynamic system is!

## Thermodynamic Systems

As an idea, thermodynamics is studying how a **system reacts under external influence**. That’s why it is so powerful! 

In principle, a thermodynamic system is an *encapsulation* of a physical system (known as a microscopic system) that removes any reference to the internal mechanism of it. It only keeps the bare minimum information about it that would be useful in predicting its behavior under external influence.

**<u>Example:</u>** *(Ideal Gas)* To predict the pressure of an Ideal gas, one could go all the way and place an imaginary surface at some part of the gas, log the position and momentum of every molecule, and then calculate how many colisions would occur in this surface, then integrate that over all surfaces and all possible position and momenta in the gas. With enough tears they would have calculate the pressure. 

The point of thermodynamics is to ignore what happens at the particles! The pressure of a real gas doesn’t care about where the particles are at any given moment! We could, in fact, figure it out just by knowing the volume of the container and its temperature. 

These **variables** are the left over information of the microscopic system that matter to predict how it reacts under external influence. In other words, if I manage to tell you how a particular process changes the temperature, volume, etc. then I don’t need to know anything else about the system to tell you how it will react!
$$
\begin{equation}\tag*{$\Box$}\end{equation} 
$$
The left over, relevant information are called **macroscopic variables**, other names for them are **thermodynamic, or state variables**. 

We will see that a **thermodynamic system** is a set of “thermodynamic states” that one can measure with at least two ways: Temperature and Entropy. These are functions from this set that obey a particular relationship that we will explore. 



## Does that actually work?

But wait a second, what if I put a surface at one part of the gas, measure a pressure there, the put it at a different one and measure a different pressure? Could I say then that I don’t need the rest of the information?

The answer is no! If the pressure is not the same everywhere, then talking about *“the pressure of the whole gass”* is nonsensical. This would mean that our entire description of the microscopic system as a macroscopic one is useless. 

> But fear not! Turns out there is an easy fix. We can just, **not care about such systems!** 

What I mean, in particular, is that thermodynamics as a field of study doesn’t care about systems that are *“non-uniform”* in that sense. That condition for systems to be *“uniform”* is called **thermodynamic equilibrium**. 

> It is not possible to define macroscopic variables outside of thermodynamic equilibrium.

Does this mean that the system cannot change pressure, temperature, or whatever without breaking equilibrium? No! A system can change its macroscopic variables and still be at equilibrium. For example, the pressure of a gas can change as a whole. If that happens we call it a **reversible process**, which is just a certain type of thermodynamic process. 

Since most systems are not in equilibrium we approximate them to be by taking their their average values as the macroscopic variables instead. In principle, thermodynamics doesn’t know anything about averages, statistics, etc. We could apply it to a completely determined system like Capacitors or Black holes!



# How many Variables?

Therefore, a system in equilibrium can be described exactly via thermodynamic variables. The next natural question is: **How many variables do I need?** And this is where the *equations of state* come in.

## Equations of state

Ok so in principle there is this theoretical space of thermodynamical states, but how many macroscopic variables do I need to fully describe it? In other words, how many dimensions is this space?

A mathematician would simply start by assuming the dimension and working from there. However, since we are physicists and actually care about getting any result we would probably go the other way around. Here is a step by step guide.

1. Take a chunk of system (for example a box of some gas at equilibrium)
2. Start measuring things (things like temperature, volume, pressure, number of particles, entropy, what have you)
3. Find relations between the quantities that you have been measuring. 

If you do this right, you will find that after some point, all your new variables are useless (in the sense that they don’t offer new information about the system, they just depend on the previous ones). The relations among the variables are called **equations of state.**

**<u>Example:</u>** *(Ideal Gas with fixed umber of particles)* If you start measuring the energy $E$, temperature $T$, pressure $P$, and volume $V$ of an ideal gas, after doing a heck of a lot of experiments (or some algebra) you will find that
$$
E = kT = PV
$$
where $k$ is some constant. These are the two equations of state for an ideal gas. You have four variables with two equations, therefore the space of thermodynamic states is two dimensional (2 equations with 4 unknowns give 2 left over variables). 

How do you know that there aren’t any more independent equations of state? Well you prove it using math from first principles. We will do it soon!
$$
\begin{equation}\tag*{$\Box$}\end{equation} 
$$
Ok, but gasses aren’t that pretty. Let’s see some cooler examples. 

**<u>Example:</u>** *(Rubber Band)* YES! Consider a rubber band. Things you can measure are the tension $f$ you apply when you stretch it, the temperatuer $T$, and its length $l$. If you do a bunch of stretching you will find that they are related kinda like this
$$
f = kT \left( \frac{l}{l_0} - \frac{l_0^2}{l^2} \right),
$$
where $l_0 \in \mathbb{R}$ the unstretched length, and $k\in \mathbb{R}$ is some coefficient. 

**<u>Example:</u>** *(Black Holes)* What are things you can measure from a black hole? Let’s assume it is electrically neutral and it has no rotation so that the equations are simpler. This already introduced two equations of state btw $Q=L=0$. Other things we could measure about them are the temperature $T$ the radius $r$ of the event horizon, and the mass $M$. What we will find is that
$$
\begin{align*}
T = \frac{k}{M} && r = k'M,
\end{align*} 
$$
 where $k,k' \in \mathbb{R}$ are constants. That’s pretty cool! We can treat a black hole as a thermodynamic system too! Also we can see that we only need one variable since we have three variables and 2 equations. So in this case, the thermodynamics of such a black hole depend only on its mass!
$$
\begin{equation}\tag*{$\Box$}\end{equation} 
$$




 