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


---

### 2. Quadrature Operators & Phase Space Uncertainty Disks
**Reference:** Gerry & Knight, *Introductory Quantum Optics*, Section 2.3 (Eqs. 2.30 – 2.45)

#### The Physics & Mathematics
The non-Hermitian photon annihilation and creation operators ($\hat{a}, \hat{a}^\dagger$) can be decomposed into two dimensionless, Hermitian quadrature operators representing the real (in-phase) and imaginary (out-of-phase) components of the field:
$$\hat{X}_1 = \frac{1}{2}(\hat{a} + \hat{a}^\dagger), \quad \hat{X}_2 = \frac{1}{2i}(\hat{a} - \hat{a}^\dagger)$$

These operators satisfy the commutation relation $[\hat{X}_1, \hat{X}_2] = \frac{i}{2}$, which leads directly to the Heisenberg uncertainty relation:
$$\Delta X_1 \Delta X_2 \ge \frac{1}{4}$$

For a Fock state $|n\rangle$:
- **Mean values vanish:** $\langle n | \hat{X}_1 | n \rangle = \langle n | \hat{X}_2 | n \rangle = 0$
- **Quadrature variances are equal and isotropic:**
  $$\Delta X_1 = \Delta X_2 = \sqrt{\frac{2n + 1}{4}}$$
- **Uncertainty product:**
  $$\Delta X_1 \Delta X_2 = \frac{2n + 1}{4}$$

For the vacuum state ($n = 0$), the equality holds ($\Delta X_1 \Delta X_2 = 1/4$), meaning the **vacuum is a minimum-uncertainty state**.

#### Simulation Output
![Quadrature Phase Space](figures/sim2_quadrature_phase_space.png)

#### Physical Interpretation
1. **Symmetric Vacuum Disk:** The ground state $|0\rangle$ occupies a symmetric, circular area in phase space with radius $\Delta X = 1/2$. It represents the irreducible quantum noise floor.
2. **Complete Phase Indeterminacy:** For number states ($|n \ge 1\rangle$), the exact photon number is known ($\Delta n = 0$), but according to the number-phase complementarity, the phase is completely random ($[0, 2\pi]$). This renders each state as a symmetric circular annulus (doughnut) of mean radius $\sqrt{n}$ centered at the origin.
3. **Linear Growth of Uncertainty:** As the photon number $n$ increases, the area of uncertainty in phase space expands linearly with $n$.
