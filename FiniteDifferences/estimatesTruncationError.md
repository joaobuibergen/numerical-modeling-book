# Estimates of the truncation error

To obtain an estimate of the truncation error, we must first estimate the magnitude of the derivatives $du/dt$, $d^2u/dt^2$, $d^3u/dt^3$, and so on. Let us consider a signal $u(t)$ such as the following:

```{figure} UTscales.png
---
height: 80px
name: figUTscales
---
Time and space scales of signal $u(t)$.
```

We observe that over time interval $\mathbf{T}$ the signal shows a variation of size $\mathbf{U}$. These characteristic values may be thought of as time and signal scales of $u$. Since the derivative of $u(t)$ is the variation $\Delta u$ that occurs over time interval $\Delta t$, we can say that $\mathbf{U}$ and $\mathbf{T}$ are the characteristic values of $\Delta u$ and $\Delta t$ and write

$$
\frac{du}{dt} \approx \frac{\mathbf{U}}{\mathbf{T}}.
$$

To obtain an estimate of the second derivative, we may assume that the variations in $du/dt$ also occur over a $\mathbf{T}$ characteristic time and write

$$
\frac{d^2u}{dt^2} = \frac{d}{dt} \frac{du}{dt} \approx \frac{\mathbf{U}/\mathbf{T}}{\mathbf{T}} = \frac{\mathbf{U}}{\mathbf{T}^2}.
$$

For higher order derivatives, the reasoning is the same. 

Coming back to the magnitude of the truncation error, the size of the terms of XX will be

$$
\Delta t \frac{\mathbf{U}}{\mathbf{T}^2}, \quad \Delta t^2 \frac{\mathbf{U}}{\mathbf{T}^3}, \quad \Delta t^3 \frac{\mathbf{U}}{\mathbf{T}^3}, \quad \mathrm{etc.}
$$

For small $\Delta t$, we can retain the leading order error term in YY:

$$
\frac{du}{dt}=\frac{u^{n+1}-u^n}{\Delta t} + O\left( \frac{\Delta t}{T}\frac{U}{T}\right).
$$

Now we see that the *order* of the relative error $\varepsilon$, i.e. the difference between the exact derivative and the approximation divided by the magnitude of the derivative, is

$$
O(\varepsilon)=O(\frac{\Delta t}{T}).
$$

This implies that to have an acceptable approximation to the derivative $du/dt$, we should have $O(\varepsilon)\ll 1$, which implies that

$$
\frac{\Delta t}{T} \ll 1 \implies \Delta t \ll T.
$$

This condition carries over easily to spatial derivatives, where the equivalent condition is $\Delta x \ll L$, where $L$ is the characteristic length, or *length scale* of the signal. 