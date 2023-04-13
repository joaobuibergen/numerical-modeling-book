# Truncation Error

The accuracy of the algebraic approximation to $du/dt$ can be determined with the help of the Taylor series expansion of $u(t)$: 

$$
u(t+\Delta t)=u(t)+\Delta t\frac{du}{dt} + \displaystyle\sum_{p=2}^{\infty} \frac{\Delta t^p}{p!}\frac{d^pu}{dt^p}
$$

Rearranging for $du/dt$, we obtain, using the discretized $t^n$:

$$
\frac{du}{dt} = \frac{u^{n+1}-u^n}{\Delta t} - \displaystyle\sum_{p=2}^{\infty} \frac{(-1)^p\Delta t^{p-1}}{p!}\frac{d^pu}{dt^p}.
$$

The difference between the exact derivative and our algebraic approximation is the last term of the right hand side of the previous equation. Expanding this term up to $i=4$, we see its general form:

$$
\frac{\Delta t}{2!}\frac{d^2u}{dt^2}+\frac{\Delta t^2}{3!}\frac{d^3u}{dt^3}+O(\Delta t^3),
$$

where $O(\Delta t^3)$ represents terms proportional to $\Delta t^3$ and higher powers of $\Delta t$. This is the error we incurr when we approximate the exact derivative with the algebraic expression and it is called the **truncation error**. 

The algebraic approximations can thus be written as:

$$
\frac{du}{dt} = \frac{u^{n+1}-u^n}{\Delta t} + O(\Delta t),
$$

where $O(\Delta t)$ represents the truncation error of the approximation, whose first term, the *leadind order* term is proportional to $\Delta t$. Since the leading order term is proportional to the first power of $\Delta t$, we say that this approximation is a *first order* approximation to the first derivative. 
