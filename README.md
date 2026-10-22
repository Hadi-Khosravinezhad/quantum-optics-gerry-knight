### 1. Single-Mode Quantum Field Fluctuations & Vacuum Noise
**Reference:** Gerry & Knight, *Introductory Quantum Optics*, Section 2.2 (Eqs. 2.22 – 2.26)

#### The Physics & Mathematics
In classical optics, the electric field of an empty cavity is identically zero. In quantum optics, the single-mode field operator inside a 1D cavity along the $z$-axis is:
$$\hat{E}_x(z, t) = 2 \mathcal{E}_0 \hat{X}_1 \sin(kz) \cos(\omega t) + 2 \mathcal{E}_0 \hat{X}_2 \sin(kz) \sin(\omega t)$$

For any photon number state (Fock state $|n\rangle$):
- **Mean field is zero:** $\langle n | \hat{E}_x(z, t) | n \rangle = 0$
- **Field variance is non-zero:**
  $$\Delta E_x(z) = \sqrt{\langle \hat{E}_x^2 \rangle - \langle \hat{E}_x \rangle^2} = 2 \mathcal{E}_0 \sqrt{n + \frac{1}{2}} |\sin(kz)|$$

Even for the vacuum state ($n = 0$), the zero-point energy induces non-vanishing vacuum fluctuations:
$$\Delta E_{\text{vac}}(z) = \sqrt{2} \mathcal{E}_0 |\sin(kz)|$$

#### Simulation Output
![Quantum Field Fluctuations](figures/sim1_field_fluctuations.png)

#### Physical Interpretation
1. **Uncertainty Envelope:** Although the classical average field is zero everywhere, there exists a standing-wave "uncertainty band". The quantum field constantly fluctuates around zero with an amplitude proportional to $\sqrt{n + 1/2}$.
2. **Vacuum Noise:** Even in complete darkness ($|0\rangle$), the field variance does not drop to zero. This zero-point fluctuation is purely quantum mechanical and has no classical counterpart.
