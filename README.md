# Non-Markovian escape under stochastic resetting
In the attached code, we have computed the escape kinetics process of a particle trapped in a harmonic potential well acted by fractional Gaussian noise (fGn). The dynamics is represented as a generalised Langevin equation (GLE), which correlates the fGn with the friction coefficient, and as a result, memory of previous events persists. The dynamics of a particle with mass $m$ in such an environment can be written as an overdamped GLE,

$$
m\omega^{2}x(t) = -\zeta \int_{0}^{t} dt^{\prime} K(t-t^{\prime}) \dot{x}(t^{\prime}) + \theta(t)
$$

where, $\omega$ is the trap frequency, $\zeta$ is the friction coefficient, and $\theta$ is the correlated random force. The term $K(t-t^{\prime})$ is the memory kernel carrying the memory of past events, and is related to the noise by the fluctuation-dissipation relation as $\big\langle \theta(t) \theta(t^{\prime}) \big\rangle = \zeta k_{\text{B}}T K(t-t^{\prime})$. The memory kernel has the functional form of $K(t-t^{\prime}) = 2H(2H-1)|t-t^{\prime}|^{2H-2}$, a power-law decay in time.
