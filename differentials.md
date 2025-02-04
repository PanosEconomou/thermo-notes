# Differentials In Thermodynamics

Let's understand what is a $df$ other than: "a small change in $f$." We will see that thinking about small changes does yield the right intuition in certain cases, but understanding what small changes mean in this context will expand the things we can do with this!

[toc]

# Small Change = Direction

Ok let's try to establish some intuition about what small changes really mean. 

## Intuition

Think of your favorite smooth shape. Like a curvy line, some smooth blob, a circle, the surface of a doughnut idk. Now say that there is a tiny point-shaped person hanging out at some position in your shape. 

Now nudge them such that they remain on the shape. Wait that must have been too far. Try to nudge them less from their initial position. Now even less. If you keep going without zooming in it becomes harder and harder to see how far you have nudged them. So in essence, for a small enough change, the amount or even the final position are irrelevant quantities! 

So what is the relevant information? If you think about it, it's always how fast did you try to move them and in what direction!

As a result, intuitively, what we care about when we are performing small changes, is never the actual magnitude of the change, but rather the direction we chose and how fast we performed it. 



## A little more precisely

This might seem obvious at first, but exploring it further leads to a much simpler characterization of "small changes." In particular think of nudging this point twice. The first time you do it fast, and the second slow. As you decrease the amount that you displace the point while keeping the velocity of your change constant, the displacement becomes irrelevant . However, you can still tell these "small changes" apart via studying the magnitude of the velocity and direction.

Immediately, you realize that in order to create a mathematical object that describes small changes, at a point on your favorite cure, that object needs to be completely defined by a magnitude and a direction, aka your object must be a vector!

This leads to the first realization and the end of our wishy washy intuition. 

> Small changes are encoded by vectors.

Now all we need to do to figure out all the possible allowed small changes in our setup is to figure out all the possible directions one can move along our curve from a point, and then we are done!

Luckily this is easy. Draw a tangent "plane" (if your curve is 1 dimensional, like a circle, this would be a tangent line for example, so by plane I really mean hyperplane) and then all the vectors there are the possible directions one can move away from the point. This leads to our second formal realization!

> A tangent "plane" at a point contains all possible small changes. 

This is so nice! Because a plane is a vector space, and we know how to use a vector space! Let's get a bit crazy now.

# Direction = Derivative

Ok this is pretty cool. What we argued in the previous section is that the mathematical structure that encodes a "small change" of a point on some curve is a vector on a tangent "plane" to the curve at that point. Now we will motivate an incredible relationship between the two.

## Partial Derivatives Encode Directions

The fact that direction is encoded in partial derivatives should not be surprising. After all, in calculus we have introduced the **directional derivative** at $p=(p_x.p_y,p_z) \in \mathbb{R}^3$ for a given vector $v = (v_x,v_y,v_z) \in \mathbb{R}^3$ that is given by
$$
\left.D_v\right|_p = v^i \left.\frac{\partial }{\partial x^i}\right|_p = v_x \left.\frac{\partial }{\partial x}\right|_p + v_y \left.\frac{\partial }{\partial y}\right|_p + v_z \left.\frac{\partial }{\partial z}\right|_p,
$$
where we have used Einstein notation. One will notice that if we where to pick a basis ${e_x,e_y,e_z} \subset \mathbb{R}^3$ then under the mapping $\left.\frac{\partial }{\partial x^i}\right|_p \mapsto e_i$ the directional derivative $D_v$ is mapped to vector $v$! In fact this becomes clearer by writing $v$ as 
$$
v = v^i e_i = v_x e_x + v_ye_y + v_z e_z.
$$
One of the most famous results in geometry is that **there is a 1-1 and onto map (a bijection) of vector space between the vector space of partial derivatives**. In other words for every vector there is a corresponding partial derivative we can take along it, and for every partial derivative there is exactly one vector that tells us the direction it is applied on.

So here is our third super amazing result in dealing with describing small changes

> A **small change at a point is** (completely described by) a **partial derivation at that point**.

While I didn't prove to you this bijection, which is outside of the scope of thermodynamics, it is easy to see by playing around and considering all the possible tangent vectors and the possible derivatives one can take along a surface. 

## Why this is fantastic

We usually associate smallness to include derivatives in some way. Here we didn't assume that! Derivatives almost miraculously arose as a natural tool to classify all possible small changes. The good thing is that we know how to work with derivatives. Therefore we can port our intuition directly.

Say that you want to quantify a collection of small changes in a region, then you can use a vector field! That vector field is such that at every point you evaluate the derivative at that point!

# Small change in *Something* = Form

This may still be unsatisfying. In fact if it isn't it should become. So far we talked about small changes and we found out that each one is perfectly modeled by the act of taking a partial derivative. However, we didn't mention anything about how to **measure small changes**.

## Small change in *what*?

We usually talk about small changes in something. Like small changes in position, small changes in the value of a function or whatever. Here it seems that we have defined a **small change** independently of what we use to measure the change itself. 

A mathematician would love this abstract representation, but a physicist would want to actually quantify the change. In order to understand how to interpret measuring small changes we first need to understand how to *measure* curves.

## Measuring Curves with Functions

*(For math people, measuring is the wrong word for what I am about to describe since it isn't directly the same concept as the one Analysis. However, it captures the intuition we are interested in here.)* 

In physics we usually represent any physical system as a point on some shape, and then study paths that that point can move along with on the shape. But most of the physical intuition we have comes from **measuring the system**. This usually includes adding functions on top of the shape and seeing their value at the point that describes our system. 

Let's examine this more carefully in the context of thermodynamics. 

**<u>Definition:</u>** For us a **curve** or **thermodynamic configuration space** $S$ is the zero set of some smooth function $f:\mathbb{R}^n \to \R$ called the **equation of state**. In other words
$$
S \coloneqq f^{-1}(0) = \{x \in \mathbb{R}^n \mid f(x) =0\}.
$$
Now, almost everything we can measure about our system can be given by a function $h:S \to \mathbb{R}$. 

**<u>Example:</u>** *(Ideal Gas)* Consider the function $f:\mathbb{R}^3 \to \mathbb{R}$ given by 
$$
(P,V,T) \mapsto f(P,V,T)= PV - NkT,
$$
for some positive constants $N,k > 0$. This is known as the ideal gas law. Therefore the thermodynamic configuration space $S$ of the ideal gas, can be parameterized by two coordinates. Say that we use $P,V$ to measure it. Then we can introduce the function $T : S \to \mathbb{R}$ given by $T(P,V) = \frac{PV}{Nk}$ that measures the **temperature** of the system. We could also introduce other things to measure, like the **number of the particles**, which is a constant function $N:S \to \mathbb{R}$ that has the same value for all points in $S$. 

Another thing we could measure is the actual coordinates themselves! For example, $P:S\to \mathbb{R}$ is a function that takes a point on the thermodynamic configuration space $S$ of the ideal gas and returns its $P$ coordinate. So is $V: S \to \mathbb{R}$.



## Small Changes in Coordinates

The point of the section above was that most measurements we can do in a physical system can be described by functions on the configuration space. Additionally, and more importantly, the coordinates of the configuration space are also such functions! 

Since every other function can be given in terms of the coordinate functions, when it comes to studying *small changes in X*, it is probably better to start exploring what a small change in coordinates is and then generalize.

We have seen that any small change can be given a vector field $X$ that can be written in terms of partial derivatives as
$$
X = X^i \frac{\partial }{\partial x^i},
$$
where we have used Einstein summation, $x^i : S \to \mathbb{R}$ are the coordinate functions, and $X^i: S \to \mathbb{R}$ are the components of the corresponding vector. 

So let's introduce what a small change in the coordinate $x^i$ should mean. From our discussion at the start, it makes sense to not talk about the magnitude of the change, but rather how fast the change is. So in other words it would make sense to say the following.

**<u>Pseudo-Definition:</u>** Under a small change $X = X^i \frac{\partial }{\partial x^i}$, a **small change along** $x^i$ is the component $X^i$.

**<u>Example:</u>** Say that we are in our ideal gas where the thermodynamic configuration space is parameterized by $P$ and $V$. Then any small change $X$ is given by
$$
X = X_P \frac{\partial }{\partial P} + X_V \frac{\partial }{\partial V},
$$
for some functions $X_P(P,V)$ and $X_V(P,V)$. In this case, the small change along $P$ is $X_P$ and the small change along $V$ is $X_V$.



## One-Forms

**We can introduce a convenient notation.** Since $P$ is an object that takes a point and gives you back its $P$-coordinate, we can introduce the object $dP$ which would take a small change $X$ and give you back the **small change along** $P$ under $X$. 

In fact such an object that takes in vector fields and gives you back functions in a linear way (like picking out the components) is called a one form. They appear all the time in math just like vectors, so let's be slightly more precise.

**<u>Definition:</u>** A **one-form** $\omega$ on a surface $S$ is any linear map of vector vector fields on $S$ to smooth functions on $S$. 

As a result we can define a small change along a coordinate like so:

**<u>Definition:</u>** A small change along a coordinate $x^i$ of $S$ is the form $dx^i$ that given a vector field in the form
$$
X = X^i \frac{\partial }{\partial x^i},
$$
it evaluates to
$$
dx^i(X) = X^i.
$$
An equivalent way of defining $dx^i$ would the following.

**<u>Definition:</u>** *(Alternative)* $dx^i$ is the unique one-form such that
$$
dx^i \left(\frac{\partial }{\partial x^j} \right) = \delta^i_j.
$$


These two are the same because one can evaluate 
$$
dx^i(X) = X^j dx^i\left( \frac{\partial }{\partial x^j} \right) = X^j \delta ^i_j = X^i.
$$
This is where the notation $dx,dy,dz$ comes from! And with that we are ready to generalize to more arbitrary changes!



## Small Changes in General Functions

We area ready! Let's consider small changes in a general function $h:S\to \mathbb{R}$ of the configuration space $S$. Now we have to be careful. Since we have coordinates $x^i : S \to \mathbb{R}$ every function $h$ can be given in terms of the values of the coordinates. We are therefore hopeful in assuming that under a small change $X$, the corresponding small change in $h$ (which we will denote as $dh(X)$) will still be given by the corresponding small changes in the coordinates $dx^i(X)$.

To derive this using our intuition consider once more what we would mean by a *small change in* $h$. We wouldn't care about the magnitude of the change, but we would care about the rate at which it is changing!

The rate? But this we know how to calculate easily using partial derivatives! Given some directional derivative $X = X^i \frac{\partial }{\partial x^i}$, the rate of change of $h$ is given by 
$$
Xh = X^i \frac{\partial h}{\partial x^i}.
$$
 This is fantastic! If this doesn't look familiar it is likely because this is a different notation. Let's fix this by looking at an example.

**<u>Example:</u>** Let's calculate the **rate of change of** the function $h : \mathbb{R}^2 \to \mathbb{R}$, given by $h(x,y) = x^2y$ along the direction $v= 2e_x +3e_y$. The corresponding directional derivative (or small change) $X$ is given by
$$
X = 2\frac{\partial }{\partial x} + 3 \frac{\partial }{\partial y},
$$
and as we know from calculus the rate of change of $h$ along $v$ is given by
$$
\begin{align*}
D_vh 
&= v_x\frac{\partial h}{\partial x} + v_y \frac{\partial h}{\partial y}\\
&= 2\frac{\partial h}{\partial x} + 3 \frac{\partial h}{\partial y}\\
&= Xh\\
&= 4y + 3x^2.
\end{align*}
$$
In other words $dh(X) = Xh$.

By the way we can use the same notation to find out $dx^i$. In this example, we can try to calculate
$$
\begin{align*}
dy(X) &= 2 \frac{\partial y}{\partial x} + 3 \frac{\partial y}{\partial y}\\
&= 3,
\end{align*}
$$
which is what we defined it to be in the previous section! So our definition is consistent. 



## Putting Everything Together

In fact, this leads to the notion of the **differential of a function**. To describe small change along some function $h:S\to \mathbb{R}$ given a small change $X = X^i \frac{\partial }{\partial x^i}$, we introduced the object $dh$ that takes in $X$ and gives us the rate of change of $h$ along $X$. 

This $d$ is a much more powerful operator (as we will see soon) called the exterior differential, or exterior derivative. In fact, here is a (general enough for functions) definition.

**<u>Definition:</u>** Given a function $h:S \to \mathbb{R}$ from some configuration space $S$, its differential $dh$ is a linear map of vector fields evaluated for each vector field $X$ by
$$
dh(X) = Xh.
$$


This is enough to derive all the properties we are used to! More specifically, let's see how to calculate this for a general $X$. We have that
$$
dh(X) = Xh = X^i \frac{\partial h}{\partial x^i}.
$$
However, we notice that $X^i = dx^i(X)$ from our previous discussion. Therefore we can write that for any $X$
$$
dh(X) = \frac{\partial h}{\partial x^i} dx^i(X).
$$
Or in the more familiar notation before plugging in the $X$
$$
dh = \frac{\partial h}{\partial x^i} dx^i.
$$
**<u>Proposition:</u>** For a smooth function $h$ on configuration space with coordinates $x^i$, its exterior derivative is given by
$$
dh = \frac{\partial h}{\partial x^i}dx^i.
$$
And we have finally derived what we really mean by small changes. So here is a recap.

> A **small change** *by itself* characterizes the motion of a point in a configuration space and is given by a vector field $X = X^i\frac{\partial}{\partial x^i}$. A **small change in a function $h$ resulting from a small change $X$** is the rate of change of $h$ along $X$ given by $dh(X) = Xh$. From there we obtain the notion of $dh$, the **differential of $h$** which is the map that takes in a small change $X$ and gives your the corresponding rate of change of $h$.

As a result, the differential $dh$ encompasses the response of $h$ on all possible small changes, which is why we sometimes abuse our notation and forget all of this to think of it as a small change itself. But in reality it is a much more rich object.



# From Small to Large Changes

This is where things become more interesting. All this time we saw that while the amount of a small/infinitesimal change doesn’t matter, the rate and direction do. But what happens when we want to express large changes? We essentially want to add up these tiny changes along a path. This is integration of one-forms! And you already know about it. 



## Integrating Small Changes

Let’s do this in practice! Say that we have some path $\gamma: [a,b] \to S$ on our configuration space, and a function $h$ that we want to measure. Then a small change in $h$ can be given by the one-form $dh$, and a large change can be given by
$$
\Delta h = \int_{\gamma} dh.
$$
How do you evaluate this integral? It’s the same integral that you encountered in calculus! Say that $S = \mathbb{R}^2$ and $\gamma(t) = (x(t),y(t))$ for some functions $x,y: [a,b] \to \mathbb{R}$. Then the integral becomes
$$
\Delta_{\gamma} h = \int_a^b d[h(x(t),y(t))]= \int_a^b \left(\frac{\partial h}{\partial x} \frac{dx}{dt} + \frac{\partial h}{\partial y} \frac{dy}{dt}\right) dt.
$$
It’s the same! And the rules of taking the differential we introduced before, work out to be what you expect.



**<u>Example:</u>** *(Isothermal Transition)* Let’s go to our favorite example of the ideal gas. An isothermal process in the thermodynamic configuration space for the ideal gas, is a path $\gamma : [a,b] \to S$ such that $V(\gamma(t)) = V_0$ for some constant $V_0 > 0$. Let’s find the change in pressure under such a process.

If we think of $S$ to be parameterized by $V,T$ then we have that pressure $P$ is a the function $P(V,T) = \frac{NkT}{V}$. Therefore the change in presure along the isothermal transition is given by 
$$
\begin{align*}
\Delta_\gamma P = \int_{\gamma} dP = \int_{a}^b d(P(\gamma))= \int_a^b \frac{Nk}{V}dT(\gamma) + \cancelto{0}{\frac{\partial P}{\partial V} \frac{d V(\gamma)}{dt}} dt  = \frac{Nk}{V} \int_\gamma dT = \frac{Nk}{V} \Delta_\gamma T.
\end{align*} 
$$
This is a very convoluted way of writing this, but it is the true order of the secret operations we sometimes perform during integration. 
$$
\begin{equation}\tag*{$\Box$}\end{equation} 
$$


The most important theorem in calculating these changes is the familiar Stoke’s theorem! Here it is in its true glory (for one-forms). Notice that the boundary of a line $\gamma : [a,b] \to S$ is the set of two points $\partial \gamma = \{\gamma(a),\gamma(b)\}$. 

**<u>Theorem:</u>** *(Stoke’s Theorem)* Let $h:S\to \mathbb{R}$ be a smooth function, and $\gamma: [a,b] \to S$ be a smooth path. Then the following is true
$$
\int_\gamma dh = \int_{\partial \gamma} h = h(\gamma(b)) - h(\gamma(a)).
$$
The reason for writing it like this is because it generalizes suuuper nicely as we will see soon. 



## Exact vs Inexact Small Changes

All of this was just recasting Calc-III things in an arguably more complicated notation. When will this notation finally be useful? 

Our current notation has introduced forms to be these linear maps of vector fields. But all the examples we have seen are differentials of functions, i.e. things like $df$ and $dx^{i}$. But one might notice that in $\mathbb{R}^2$ the following is still a linear map of vector fields
$$
\omega = ydx.
$$
This is not an unusual object! In fact we integrate things like this all the time. The interesting part though is that this can’t be written as $d(\text{something})$. 

Yet, casting our intuition, this obbject, still describes a small change of something, even if that something is not a function on our space. While this might look weird there is a very common example of this that we have encountered before. Work!

**<u>Example:</u>** We usually call the infinitesimal change in work $\delta W = - P dV$. This is a perfectly valid one form, however, without any extra conditions (i.e. that $P = \frac{d F}{d V}$ for some function $F$ which almost never true) is is not possible to write $\delta W = dh$ for some function $h$ on the thermodynamic phase space. 

We call such a form **inexact**. In fact here is a definition.

**<u>Definition:</u>** An **exact one-form** $\omega$ (sometimes also known as exact differnetial or exact quantity) is a form such that $\omega = df$ for some smooth function $f$. If no such function exists, the one-form is known as **inexact**.

You might might be comfortable with referring to an inexact form as a small change of something other than a function. But what is that something? To find that out let’s integrate an inexact and an exact form along a path. 

**<u>Example:</u>** *(Exact vs Inexact)* Consider the following paths $\alpha,\beta: [0,1] \to \mathbb{R}^2$ given by
$$
\begin{align*}
\alpha(t)&= (t,0)\\
\beta(t) &= \left(t,\frac{1 - |2t-1|}{2}\right).
\end{align*}
$$
And the two forms $\omega = dx$ and $\eta = ydx$. One is exact, the other one inexact. Here is what happens when we integrate them along the paths. 

|  Integrals of $\omega$  |        Integrals of $\eta$        |
| :---------------------: | :-------------------------------: |
| $ \int_{\alpha} dx = 1$ |     $ \int_{\alpha} ydx = 0$      |
| $ \int_{\beta} dx = 1$  | $ \int_{\beta} ydx = \frac{1}{4}$ |

Try to work out these integrals yourself to make sure you understand the mechanics of this. What you notice is that the integral of $\omega$ was intdependent of path, while the integral of $\eta$ was dependent on the path. Notice that both of these paths though had the same endpoints!



This is the interesting result. If the small change of something is given by an exact form, then the large change along the path only depends on the endpoints of the path, and not how we got there. On the other hand, if a small change of something is given by an inexact form, then the large change along a path depends on the path itself! This makes sense because in the inexact case the quantity we are interested can never be merely a scalar function of the configuration space.  Here is this tied up in a neat proposition.

**<u>Proposition:</u>** Given a one-form $\omega$ then it is inexact if and only if there exist two paths $\alpha, \beta : [a,b] \to S$ with the same endpoints (i.e. $\alpha(a) = \beta(a),\ \alpha(b) = \beta(b)$) such that
$$
\int_\alpha \omega \neq \int_\beta \omega.
$$
*(It is a nice exercise to prove this, but if you’re interested in a sleek way, you might want to look up general $k$-forms.)*

**<u>Example:</u>** *(Work)* One of the most famous inexact forms in thermodynamics is **work**. For an ideal gas, this is defined as $\delta W = - PdV$, where $P,V : S \to \mathbb{R}$ are the pressure and volume, and $S$ is the thermodynamic configuration space. 

We have seen the path dependance of this time and time again. For example, an adiabatic process, which is any path $\alpha:[a,b] \to S$ such that $P(\alpha(t)) V(\alpha(t))^{\gamma} =K$ where $K,\gamma>0$ are constants for all $t \in [a,b]$ (we usually say instead $PV^\gamma = K$ making the path reference implicit because it is freaking cumbersome to write down), has a different work from an Isothermal process which we defined in a previous example. 



> **<u>Problem:</u>** *(Muscles)* You can measure the force a muscle exerts using a spring or a piston connected to an ideal gas, or any number of things. Now say that you want to study the thermodynamics of the muscle. What is a description of the work done **by** the muscle in terms of the quantities you can measure? Is your work $\delta W$ exact or inexact? Say you measure the temperature $T$ of the muscle, the corss sectional area $A$ and the force on the spring $F$ and you find that
> $$
> FA^2 = CT,
> $$
> for some constant $C > 0$. Can you find how the work $\delta W$ depends on the other quantities here? Is it exact? What are the different kinds of thermodynamic processes you can perform between the same endpoints and obtain different work overall? 



