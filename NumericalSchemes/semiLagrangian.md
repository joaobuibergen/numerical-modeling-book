# The semi-lagrangian scheme

We have been using the linear advection equation in its Eulerian form {eq}`eqAdvection`. An alternative form of this equation is 

$$
\frac{dU}{dt}=0,
$$ (eq:advectionLagrangian)

where $U(t)=u(x(t),t)$ is the quantity $u(x,t)$ carried by a particle whose trajectory is $x(t)=x(0)+ct$. Equation {eq}`eq:advectionLagrangian` is called the *Lagrangian* form of {eq}`eqAdvection` and it states that $u$ is conserved along particle trajectories.

Both forms are equivalent, as we can see if we expand {eq}`eq:advectionLagrangian`:

$$
\frac{dU}{dt}=\frac{du(x(t),t)}{dt}=\frac{\partial u}{\partial t} + \frac{\partial u}{\partial x}\frac{\partial x}{\partial t}=\frac{\partial u}{\partial t} + c\frac{\partial u}{\partial x}=0.
$$ (eq:advectionEulerianLagrangian)

The conservation of $u$ implies that, over a time interval $[n\Delta t, (n+1)\Delta t]$,

$$
U^{n+1}=U^{n}.
$$ (eq:schemeLagrangian)

This means that if we know $U^0$, we know the all subsequent $U^n$, along the trajectories of fluid particles. However, this does not work in practice because we don't know the particle trajectories. 

A more practical approach is to "reverse" the procedure.  

