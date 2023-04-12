# Total Variation Diminishing Schemes

## TVD (Total Variation Diminishing) Schemes

TVD (Total Variation Diminishing) schemes are a class of numerical methods used for solving partial differential equations (PDEs) that are subject to shocks or discontinuities. The idea behind TVD schemes is to maintain the total variation of the solution, which measures the amount of variation in the function over a given interval. The total variation should be conserved in order to prevent spurious oscillations or overshoots that can occur with some numerical methods such as the upwind scheme or the leapfrog scheme.

The upwind scheme is a first-order method that uses a one-sided approximation of the spatial derivative based on the direction of the flow. Specifically, the upwind scheme uses a forward difference approximation for the spatial derivative when the flow is moving to the right, and a backward difference approximation when the flow is moving to the left. This ensures that the numerical solution is always downstream of the true solution, and is therefore stable.

The leapfrog scheme is a second-order method that uses a centered difference approximation of the spatial derivative, which is more accurate than the upwind scheme. However, the leapfrog scheme can be unstable for certain types of flows, particularly those that involve shocks or other discontinuities.

The TVD scheme combines the advantages of both the upwind scheme and the leapfrog scheme by using a flux limiter to ensure that the numerical solution is TVD, meaning that the total variation of the solution is conserved. This helps to prevent the formation of spurious oscillations or overshoots that can occur with other numerical methods.

## TVD Scheme Theory

TVD schemes achieve conservation of total variation by using a limiter function to restrict the amount of numerical diffusion introduced by the scheme. The limiter function is designed to detect the presence of discontinuities or shocks in the solution and to reduce the amount of diffusion introduced in these regions. By reducing the amount of numerical diffusion, TVD schemes are able to preserve sharp gradients and discontinuities in the solution while maintaining stability.

The basic idea behind a TVD scheme is to add a flux limiter to the numerical fluxes used in the numerical method. The flux limiter modifies the numerical fluxes to prevent overshooting and undershooting at sharp gradients or discontinuities in the solution. The flux limiter function is usually chosen based on the local gradient of the solution, and can take various forms.

One example of a TVD scheme is the Total Variation Diminishing Upwind Scheme (TVDUS). The TVDUS scheme can be expressed mathematically as:

$$
u_m^{n+1} = u_m^{n} - \frac{\Delta t}{\Delta x}(f_{m+\frac{1}{2}}-f_{m-\frac{1}{2}})
$$

where $u_m^{n+1}$ is the value of the solution at grid point $m$ and time $n+1$, $u_m^n$ is the value of the solution at grid point $m$ and time $n$, $f_{m+\frac{1}{2}}$ is the numerical flux at the interface between grid points $m$ and $m+1$, and $f_{m-\frac{1}{2}}$ is the numerical flux at the interface between grid points $m$ and $m-1$. The fluxes $f_{m+\frac{1}{2}}$ and $f_{m-\frac{1}{2}}$ are modified by the flux limiter to prevent overshooting and undershooting.

One example of a flux limiter function that can be used in TVD schemes is the minmod limiter. The minmod limiter function is defined as:

$$
\phi(r)=max(0,min(1,r))
$$

where $r$ is the ratio of the difference between two adjacent values to the average of the two values. The minmod limiter ensures that the numerical fluxes do not exceed the maximum and minimum values of the adjacent grid points, thus preserving the total variation of the solution.

