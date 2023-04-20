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

A more practical approach is to "reverse" the procedure.  {numref}`fig:semiLagrangia-grid` shows a part of the t-x diagram between time steps $n$ and $n+1$ and grid positions $m-2$ to $m+2$.

```{figure} numerical-schemes-semi-lagrangian-grid.png
---
height: 400px
name: fig:semiLagrangia-grid
---
t-x diagram between time steps $n$ and $n+1$. The particle at $x_{m+2}$ at time $t^{n+1}$ was at $x_{\ast}$ at time $t^n$.
```
The value of $u_{m+2}^{n+1}$ is $U_{m+2}^{n+1}$, the value of $u$ carried by the particle that occupies $x_{m+2}$ at $t^{n+1}$. According to {eq}`eq:schemeLagrangian`, this value is $U_{\ast}^{n}$, the value of $u$ at $x_{\ast}$ at $t^n$, which is the position that the particle occupied at $t^n$. 

During one time step, the particle moves a distance $s=c\Delta t$. Let $\sigma=c\Delta t/\Delta x=1.25$ ({numref}`fig:semiLagrangia-grid`), so that $s=\sigma\Delta x=1.25\Delta x$. In general, the particle's departure point $x_{\ast}$ does not coincide with the grid nodes, so we must interpolate $u$ to find $u(x_{\ast},t^n)$.

Let $p=[\sigma]$ be the integer part of $\sigma$ and $\alpha=\sigma-p$, the fractional part of $\sigma$. In this example, $p=1$ and $\alpha=0.25$. The departure point falls between $m-p-1$ and $m-p$, and we can use linear interpolation to obtain $U_{\ast}^n$:

$$
U_{\ast}^n=\alpha u_{m-p-1}^n + (1-\alpha)u_{m-p}^n=u_{m+2}^{n+1}, 
$$

which is $u_{m+2}^{n+1}$ because of {eq}`eq:schemeLagrangian`. 

