# Algebraic approximation of the first derivative

Let us consider a function $u(t)$ that depends continously on $t$. The derivative of $u(t)$ is:

$$
\frac{du}{dt} = \lim_{\Delta t \to 0} \frac{u(t+\Delta t)-u(t)}{\Delta t}.
$$

We can obtain an algebraic approximation to $du/dt$ simply by relaxing the requirement that $\Delta t \to 0$, retaining a finite $\Delta t$:

$$
\frac{du}{dt} \approx \frac{u(t+\Delta t)-u(t)}{\Delta t}.
$$

If instead of a continuos $t$, we use values $t^n=n\Delta t$, we can write the algberaic approximation as:

$$
\frac{du}{dt} \approx \frac{u^{n+1}-u^n}{\Delta t},
$$

where $u^{n+1}=u(t^{n+1})=u(t^n+\Delta t)$ and $u^{n}=u(t^n)$.

When dropping the requirement $\Delta t \to 0$ to obtain the algebraic approximation, we are irrevically introducing errors in the calculation of $du/dt$. We must now find out how large can these errors be.