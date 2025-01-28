# Electric Thermo

Let's explore some simple systems that are not gases! How exciting. You can find this in **Zemansky ch. 2.8-2.9**

[toc]

# Dielectrics

A **dielectric** is any material that when an electric field passes through, it changes. In practice, all materials are dielectrics in some way, it is just that some of them, like air, change the electric field in such a minuscule way that we ignore them. Let's be more precise about how these materials change the electric field.

## Polarization

Everything is made out of atoms. Atoms must have at least some positive charge, as well as some wiggle in their position. When a charge is in some electric field it moves.

Therefore when you place a material inside an electric field the charges will also move! Depending on a billion parameters, the charge configuration of the material will change. Lemme show you an example.

**<u>Example:</u>** *(Some crystal)* Consider a molecule that is electrically neutral. One example can be this Carbon Tetrachloride thing. Here is how it looks when it remains untouched.

|                         Unpolarized                          |                          Polarized                           |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| ![Unpolarized](https://raw.githubusercontent.com/PanosEconomou/thermo-notes/refs/heads/main/_electric-thermo.assets/unpolarized.svg) | ![Polarized](https://raw.githubusercontent.com/PanosEconomou/thermo-notes/refs/heads/main/_electric-thermo.assets/polarized.svg) |

As you can see from my expert drawing, carbon tetrachloride is a pyramid that has a carbon (black circle) at the center, and 4 chlorine atoms on each side. When there is no external electric field, the molecule is unpolarized since each chlorine atom attracts each other exactly the same amount. When an external electric field $\vec{E}$ is added though, the chlorides move! This is eventually canceled by some induced electric field (the blue arrow). 

In a material these induced electric fields are add up, and eventually there is a minor electric field induced inside the material that makes it look like the electric field insider the material is different from the one outside!

----

Here is a nice way to quantify this weird phenomenon.

**<u>Definition:</u>** An **electric dipole moment** is a vector $\mu$ that quantifies the separation of two like charges.

**<u>Example:</u>** The dipole moment of two point charges $\pm q$ separated by a displacement $s$, that is usually a vector, is $\mu = qs$.

Adding up the dipole moments over an entire material gives the total polarization $\mathcal{P}$. A useful quantity in electrostatics is the **average polarization density** given by $P = \frac{\mathcal{P}}{V}$ where $V$ is the volume of the material. In fact, in order to use Maxwell's equations we often introduce the **displacement field** $D$ given by
$$
D = \epsilon_0 E  + P= \epsilon_0 E + \frac{\mathcal{P}}{V},
$$
where $E$ is the total electric field. 



## Linear Dielectrics

As you might have seen, sometimes the polarization is in the same direction as the electric field $E$. We call those dielectrics **linear** and we have the equation
$$
\frac{\mathcal{P}}{V} = P = \epsilon_0 \chi E
$$
we call $\chi$ the **electric susceptibility**. That constant is of central interest in thermodynamics. Indeed we can see that for an abundance of systems this constant depends only on temperature like so
$$
\chi = \frac{1}{\epsilon_0}\left( a + \frac{b}{T} \right),
$$
for constants $a,b$. So in principle we could use three thermodynamic coordinates with only 1 equation of state:
$$
\boxed{\frac{\mathcal{P}}{V} = \left( a + \frac{b}{T} \right) E}.
$$


# Paramagnetism

Another super useful system to study in thermodynamics are magnets! In particular how does a material magnetize under an external magnetic field. Paramagnets are to magnetic fields what dielectrics are to electric fields. 


## Magnetic Displacement

The relevant quantity here, instead of the polarization is the **magnetization** $M$ which is the sum of the magnetic moments $\mu$ in the material. In an identical fashion to the electric displacement we define a quantity 
$$
H = \frac{B}{\mu_0} - \frac{M}{V},
$$
where $B$ is the total magnetic field, and $V$ is the volume of the material. The only difference between the electric and magnetic susceptibilities is that $H$ can be interpreted as the external magnetic field applied to the material! (Read Griffiths or ask me in recitation why $D$ can't be thought of as the external electric field applied to the material in the case of polarization above).

Experimentally, it is obviously much, much, MUCH, easier to measure $H$ than $B$. Have fun trying to place a magnetic probe *inside* your material without effing up the total magnetic field! That's why we want to use $H$ as our thermodynamic coordinate instead of $B$. 



## Linear Response 

In so so so many paramagnets the induced magnetization is proportional to the external field. Therefore we get
$$
M = \chi H,
$$
where $\chi$ is the **magnetic susceptibility**. A material is a **paramagnet** if $\chi > 0$ (otherwise it is a diamagnet or a notamagnet). 

In thermodynamics this is the quantity that depends on temperature. In fact, one experimental thermodynamic relation is called Curie's law, that says that
$$
\chi = \frac{C}{T},
$$
where $C$ is some constant. Therefore we can introduce the following equation of state:
$$
    \boxed{M = \frac{C}{T} H.}
$$
You can also derive this result using quantum mechanics! If you're interested ask me in office hours! If you don't wanna ask me Google 1-dimensional quantum Ising model. 

