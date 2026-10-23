# Quantum Optics Simulations (Gerry & Knight)

Interactive computational simulations of core concepts based on **"Introductory Quantum Optics" by Christopher C. Gerry and Sir Peter L. Knight**.

---

### 1. Single-Mode Quantum Field Fluctuations & Vacuum Noise
**Reference:** Chapter 2 (*Field Quantization*), Section 2.2: *Quantum Fluctuations of a Single-Mode Field*

#### The Physics & Mathematics
In classical optics, an empty cavity contains no energy, and the electric field is identically zero everywhere. In quantum optics, the electric field inside a single-mode 1D cavity along the $z$-axis is quantized:
$$\hat{E}_x(z, t) = \mathcal{E}_0 \left(\hat{a} e^{-i\omega t} + \hat{a}^\dagger e^{i\omega t}\right) \sin(kz)$$

For any photon number state (Fock state $|n\rangle$):
- **Expectation value vanishes:**
  $$\langle n | \hat{E}_x(z, t) | n \rangle = 0$$
- **Field uncertainty (fluctuation envelope) is non-zero:**
  $$\Delta E_x(z) = \sqrt{\langle \hat{E}_x^2 \rangle - \langle \hat{E}_x \rangle^2} = 2 \mathcal{E}_0 \sqrt{n + \frac{1}{2}} |\sin(kz)|$$

For the vacuum state ($n = 0$), zero-point energy induces non-vanishing vacuum noise:
$$\Delta E_{\text{vac}}(z) = \sqrt{2} \mathcal{E}_0 |\sin(kz)|$$

#### Simulation Output
![Quantum Field Fluctuations](figures/sim1_field_fluctuations.png)

#### Detailed Plot Guide & Analysis
* **Subplot (a) — Spatial Profile of Quantum Fluctuations:**
  * **X-Axis ($z/L$):** Position inside the optical cavity, from the left mirror ($z=0$) to the right mirror ($z=1$).
  * **Y-Axis ($E_x / \mathcal{E}_0$):** Normalized electric field amplitude.
  * **Black Dashed Line ($\langle E \rangle = 0$):** The classical average of the field is exactly zero everywhere across the cavity.
  * **Colored Shaded Bands ($\pm \Delta E$):** Represent the quantum uncertainty region around the zero mean. Because the field is constrained by conducting cavity boundaries, fluctuations drop to zero at the walls ($z=0, 1$) and peak at the antinode ($z/L = 0.5$).
  * **Blue Band ($|0\rangle$ Vacuum State):** **The fundamental takeaway!** Even when there are zero photons in the cavity, the field is not dead; it fluctuates within an envelope of $\pm \sqrt{2}\mathcal{E}_0$.
  * **Green ($|1\rangle$) & Red ($|3\rangle$) Bands:** As more photons are injected into the cavity, the spread of quantum noise widens proportional to $\sqrt{n + 1/2}$.

* **Subplot (b) — Fluctuation Amplitude vs. Photon Number:**
  * **X-Axis ($n$):** Number of photons in the cavity mode ($n = 0, 1, 2, \dots, 10$).
  * **Y-Axis:** Peak field uncertainty at the cavity center ($z = L/2$).
  * **Blue Dot at $n=0$:** Highlights the irreducible zero-point vacuum noise ($\Delta E \approx 1.414 \mathcal{E}_0$).
  * **Brown Curve:** Shows that field uncertainty grows sub-linearly with photon number as $\sim \sqrt{n}$.

---

### 2. Quadrature Operators & Phase Space Uncertainty Disks
**Reference:** Chapter 2 (*Field Quantization*), Section 2.3: *Quadrature Operators for a Single-Mode Field*

#### The Physics & Mathematics
The non-Hermitian creation and annihilation operators ($\hat{a}, \hat{a}^\dagger$) can be decomposed into two dimensionless, Hermitian quadrature operators:
$$\hat{X}_1 = \frac{1}{2}(\hat{a} + \hat{a}^\dagger), \quad \hat{X}_2 = \frac{1}{2i}(\hat{a} - \hat{a}^\dagger)$$

These operators are optical analogues of dimensionless position and momentum, satisfying $[\hat{X}_1, \hat{X}_2] = \frac{i}{2}$, which imposes the Heisenberg uncertainty relation:
$$\Delta X_1 \Delta X_2 \ge \frac{1}{4}$$

For any Fock state $|n\rangle$:
- **Mean values vanish:** $\langle n | \hat{X}_1 | n \rangle = \langle n | \hat{X}_2 | n \rangle = 0$
- **Isotropic uncertainties:**
  $$\Delta X_1 = \Delta X_2 = \sqrt{\frac{2n + 1}{4}}$$
- **Uncertainty product:**
  $$\Delta X_1 \Delta X_2 = \frac{2n + 1}{4}$$

#### Simulation Output
![Quadrature Phase Space](figures/sim2_quadrature_phase_space.png)

#### Detailed Plot Guide & Analysis
* **Subplot (a) — Quadrature Phase Space $(X_1 - X_2)$:**
  * **Axes ($X_1, X_2$):** Represent the in-phase and out-of-phase field amplitudes (equivalent to real and imaginary components of the complex electric field amplitude).
  * **Blue Solid Disk ($|0\rangle$ Vacuum State):** Classically, an empty state would be a single point at the origin $(0, 0)$. In quantum mechanics, the uncertainty principle forbids this. Instead, the vacuum occupies a symmetric circular disk of radius $\Delta X = 1/2$.
  * **Concentric Rings ($|1\rangle, |2\rangle, |3\rangle$ Fock States):** 
    * Why are they shaped like rings (doughnuts)? In a Fock state, the photon number $n$ is known with absolute precision ($\Delta n = 0$). By the quantum number-phase complementarity, its phase $\phi$ is completely undetermined and uniformly spread over $[0, 2\pi)$.
    * The ring's mean radius is $\sqrt{n}$, and its radial thickness corresponds to the quantum noise.
  * **Phase Symmetry:** Notice that all states are centered at $(0,0)$ and rotationally symmetric, confirming that number states carry no preferred optical phase.

* **Subplot (b) — Quadrature Uncertainty Product:**
  * **Black Dashed Line ($1/4$):** The ultimate quantum limit dictated by Heisenberg's uncertainty principle ($\Delta X_1 \Delta X_2 \ge 1/4$).
  * **Blue Point ($n=0$):** The vacuum state touches the lower bound exactly ($\Delta X_1 \Delta X_2 = 1/4$). Hence, **the vacuum is a minimum-uncertainty state**.
  * **Purple Line ($n \ge 1$):** Shows that Fock states with $n \ge 1$ are *not* minimum-uncertainty states; their uncertainty area in phase space grows linearly with photon number as $\frac{2n+1}{4}$.
