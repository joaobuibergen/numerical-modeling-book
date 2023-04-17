# The two dimensional advection equation

1. Consider the 2d advection of field $F$ under the velocity field $\vec{V}$:

$$
\frac{\partial F}{\partial t} + \vec{V}\cdot \nabla F = 0, \quad \vec{V}=u\vec{i}+v\vec{j}.
$$

Let $(x_m,y_l)=(m\Delta x, l\Delta y)$ and $t^n=n\Delta t$. Applying central difference formulas to the time and spatial derivatives of $F$, we obtain:

$$
\frac{F_{m,l}^{n+1}-F_{m,l}^{n-1}{2\Delta t}=-u\left( \frac{F_{m+1,l}^{n}-F_{m-1,l}^{n}{2\Delta x}\right) - 
v\left( \frac{F_{m,l+1}^{n}-F_{m,l-1}^{n}{2\Delta y}\right) \Leftrightarrow \\
F_{m,l}^{n+1}=F_{m,l}^{n-1}=-u\frac{\Delta t}{\Delta x}\left( F_{m+1,l}^{n}-F_{m-1,l}^{n}\right) - 
v\frac{\Delta t}{\Delta y}\left( F_{m,l+1}^{n}-F_{m,l-1}^{n}\right).
$$ (eq:twoDLeapfrog)

We shall apply Von Neumann stability analysis to {eq}`eq:twoDLeapfrog`, by substituting a solution of the type:

$$
F_{m,l}^n=B^ne^{k_xm\Delta x+k_yl\Delta y},
$$

where $k_x$ and $k_y$ are the wavenumbers in $x$ and $y$. After some manipulation, we have

$$
B^{n+1}=B^{n-1}-2i\Delta t\left( u\frac{\sin k_x\Delta x}{\Deltax}+v\frac{\sin k_y\Delta y}{\Deltay}\right)B^n.
$$ (eq:amplificationEquation)

Defining $D^n=B^{n-1}$, we can write {eq}`eq:amplificationEquation` as matrix recurrence relationship:

$$
\begin{bmatrix}
 B^{n+1}\\
 D^{n+1}
\end{bmatrix}
=
\begin{bmatrix}
 -2i\Delta tr  & 1\\
      1        & 0
\end{bmatrix}
\begin{bmatrix}
 B^{n}\\
 D^{n}
\end{bmatrix},
$$ (eq:matrixFormula)

where $r=u\frac{\sin k_x\Delta x}{\Deltax}+v\frac{\sin k_y\Delta y}{\Deltay}$. The eigenvalues of the recurrence matrix of {eq}`eq:matrixFormula` are given by

$$
\lambda_\pm = -i\Delta tr \pm \sqrt{1-(\Delta tr)^2}.
$$

For the scheme to be stable, we must have $|\lambda_\pm| \leq 1$, which is true if $\Delta tr \leq 1$.



