# The 1-d linear advection equation

The 1-d linear advection equation is a first order partial differential equation that represents, in a simple form, the important process of advection in the atmosphere and ocean. The equation

$$
	\frac{\partial u}{\partial t} + c \frac{\partial u}{\partial x} = 0, c>0
$$(eqAdvection)

models the advection of a signal $u(x,t)$ across 1-d space with velocity $c$, that may also be interpreted as a phase speed of a wave that propagates in the positive $x$-direction. Equation {eq}`eqAdvection` is similar to the first two terms of the momentum equations, that represent the nonlinear advection of momentum by the motions of the fluid. Its simplicity and its closeness to the important equations that govern fluid flow make it an attractive model with which to study the solution of partial differential equations with numerical methods. The simplicity of {eq}`eqAdvection` makes possible obtaining an analytic solution and also solve the associated difference equations, allowing a direct comparison to numerical solutions.

The analytic solution of {eq}`eqAdvection` can be obtained by the method of the separation of variables. We shall assume an initial condition in the form of a simple wave:

$$
	u(x,0)=A e^{i k x},
$$ (initialCond)

where $k = 2\pi/\lambda$ is the wave number ($\lambda$ is the wavelength). Let the solution to {eq}`eqAdvection` with initial condition {eq}`initialCond` be given by

$$
	u(x,t)=G(t)H(x).
$$ (sepVar)

Substituting in {eq}`eqAdvection`, we have

\begin{align*} 
   \frac{\partial }{\partial t} (G(t)H(x))=& -c \frac{\partial }{\partial x} (G(t)H(x)) \\
   H(x) \frac{\partial G(t)}{\partial t} =& -c G(t) \frac{\partial H(x)}{\partial x} \\
   \frac{1}{\partial G(t)} \frac{\partial G(t)}{\partial t} =& -c \frac{1}{\partial H(x)} \frac{\partial H(x)}{\partial x}, 
\end{align*}

that to be valid for all $(x,t)$ must be equal to a constant $-\alpha$. Integration yields

\begin{align*} 
      \frac{1}{\partial G(t)} \frac{\partial G(t)}{\partial t} =& -\alpha \Leftrightarrow G(t)=A_1e^{-\alpha t} \\
      -c \frac{1}{\partial H(x)} \frac{\partial H(x)}{\partial x}=& -\alpha \Leftrightarrow H(x)=A_2e^{\alpha x/c},
\end{align*}

and we find $u(x,t)=G(t)H(x)=A_1A_2e^{-\alpha t}e^{\alpha x/c}$. At $t=0$ we have $u(x,0)=A_1A_2e^{\alpha x/c}$, so we know that $A=A_1A_2$ and $ik = \alpha/c$ and so $\alpha=ikc$. Finally, we can write:

\begin{equation}\label{eqn:anaSol}
	u(x,t)=Ae^{-ikct}e^{ikcx/c}=Ae^{ik(x-ct)},
\end{equation}

which is the solution of {eq}`eqAdvection` given the initial condition {eq}`initialCond`. This solution represents the initial condition moving along the positive $x$-direction with a speed of translation $c$.

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
 

