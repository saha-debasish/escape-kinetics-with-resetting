# Non-Markovian escape under stochastic resetting
In the attached code, we have computed the escape kinetics process of a particle trapped in a harmonic potential well acted by fractional Gaussian noise (fGn). The dynamics is represented as a generalised Langevin equation (GLE), which correlates the fGn with the friction coefficient, and as a result, memory of previous events persists. The dynamics of a particle with mass $m$ in such an environment can be written as an overdamped GLE,

$$
m\omega^{2}x(t) = -\zeta \int_{0}^{t} dt^{\prime} K(t-t^{\prime}) \dot{x}(t^{\prime}) + \theta(t)
$$

where, $\omega$ is the trap frequency, $\zeta$ is the friction coefficient, and $\theta$ is the correlated random force. The term $K(t-t^{\prime})$ is the memory kernel carrying the memory of past events, and is related to the noise by the fluctuation-dissipation relation as $\big\langle \theta(t) \theta(t^{\prime}) \big\rangle = \zeta k_{\text{B}}T K(t-t^{\prime})$. 

The memory kernel has the functional form of $K(t-t^{\prime}) = 2H(2H-1)|t-t^{\prime}|^{2H-2}$, a power-law decay in time. Here, $H$ is the Hurst index, which varies between $1/2 \leq H < 1$, with $H = 1/2$ corresponding to the pure Markovian limit, where fluctuations are uncorrelated, and $H > 0.5$ representing the non-Markovian limit. The higher the value of $H$, the stronger the noise correlation becomes.

To simulate the above GLE numerically, we need to discretise it, where the entire process can be expressed as a discrete set of events. The total time $t$ is divided uniformly in $N$ intervals with $\Delta t = t/N$. For $N \to \infty$ and $\Delta t \to 0$, we can write

$$
x_{N} = x(0) + \frac{1}{A} [ -\frac{m\omega^{2}(\Delta t)^{\alpha}}{\Gamma(\alpha+1)} \sum_{j=1}^{N} x_{j-1} [(N-j+1)^{\alpha} - (N-j)^{\alpha}] + G(N\Delta t)]
$$

where, $A = 2\zeta H(2H-1) \Gamma(1-\alpha)$, $\alpha = 2-2H$, and $G$ is the fractional Brownian motion. To see the complete derivation, follow the preprint at https://arxiv.org/abs/2509.11608.

The random noise $G$ is sampled using the $\tt{FractionalBrownianMotion}$ module from Stochastic, available at https://stochastic.readthedocs.io/.
