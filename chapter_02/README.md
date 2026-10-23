# Chapter 2: Field Quantization
### Numerical Simulations & Visual Interpretations
Based on **"Introductory Quantum Optics" by Christopher C. Gerry and Sir Peter L. Knight**, Chapter 2: *Field Quantization*.

---

## 📌 Chapter Overview
This folder contains computational models and phase-space representations illustrating the quantum nature of single-mode electromagnetic fields inside an optical cavity.

- [x] **1. Single-Mode Quantum Field Fluctuations & Vacuum Noise** (Sec. 2.2)
- [x] **2. Quadrature Operators & Phase Space Uncertainty Disks** (Sec. 2.3)
- [ ] **3. Photon Number Statistics: Thermal vs. Coherent Light** (Sec. 2.5) *(Next)*
- [ ] **4. Zero-Point Energy & Casimir Effect Regularization** (Sec. 2.6) *(Next)*

---

### 1. Single-Mode Quantum Field Fluctuations & Vacuum Noise
**Reference:** Chapter 2 (*Field Quantization*), Section 2.2: *Quantum Fluctuations of a Single-Mode Field*

#### The Physics & Mathematics
In classical optics, an empty cavity contains no energy, and the electric field is identically zero everywhere. In quantum optics, the electric field operator inside a 1D single-mode cavity along the $z$-axis is quantized as:
$$\hat{E}_x(z, t) = \mathcal{E}_0 \left(\hat{a} e^{-i\omega t} + \hat{a}^\dagger e^{i\omega t}\right) \sin(kz)$$

where $\mathcal{E}_0 = \sqrt{\frac{\hbar \omega}{\epsilon_0 V}}$ is the electric field per photon, and $\hat{a}, \hat{a}^\dagger$ are the bosonic annihilation and creation operators.

For any photon number state (Fock state $|n\rangle$):
- **Expectation value vanishes everywhere:**
  $$\langle n | \hat{E}_x(z, t) | n \rangle = 0$$
- **Field uncertainty (fluctuation envelope) is non-vanishing:**
  $$\Delta E_x(z) = \sqrt{\langle \hat{E}_x^2 \rangle - \langle \hat{E}_x \rangle^2} = 2 \mathcal{E}_0 \sqrt{n + \frac{1}{2}} |\sin(kz)|$$

For the vacuum state ($n = 0$), zero-point energy induces irreducible quantum fluctuations:
$$\Delta E_{\text{vac}}(z) = \sqrt{2} \mathcal{E}_0 |\sin(kz)|$$

#### Simulation Output
![Quantum Field Fluctuations](figures/sim1_field_fluctuations.png)

#### Detailed Plot Guide & Analysis
* **Subplot (a) — Spatial Profile of Quantum Fluctuations:**
  * **X-Axis ($z/L$):** Normalized spatial coordinate along the cavity axis, from mirror $z = 0$ to mirror $z = 1$.
  * **Y-Axis ($E_x / \mathcal{E}_0$):** Normalized electric field amplitude.
  * **Black Dashed Line ($\langle E \rangle = 0$):** The classical average of the field is exactly zero everywhere across the cavity at all times.
  * **Colored Shaded Bands ($\pm \Delta E$):** The quantum uncertainty envelope around the zero mean. Because the field is constrained by perfectly conducting cavity walls, fluctuations vanish at the mirrors ($z=0, 1$) and reach maximum amplitude at the antinode ($z/L = 0.5$).
  * **Blue Band ($|0\rangle$ Vacuum State):** **The primary quantum takeaway!** Even with zero photons in the cavity, the field is never quiescent; it fluctuates within an envelope of $\pm \sqrt{2}\mathcal{E}_0$.
  * **Green ($|1\rangle$) & Red ($|3\rangle$) Bands:** Injecting photons expands the variance envelope proportional to $\sqrt{n + 1/2}$.

* **Subplot (b) — Fluctuation Amplitude vs. Photon Number:**
  * **X-Axis ($n$):** Cavity photon number ($n = 0, 1, 2, \dots, 10$).
  * **Y-Axis:** Peak field uncertainty at the antinode center ($z = L/2$).
  * **Blue Dot at $n=0$:** Highlights the irreducible zero-point vacuum noise floor ($\Delta E \approx 1.414 \mathcal{E}_0$).
  * **Brown Curve:** Demonstrates that the field fluctuation amplitude grows sub-linearly with excitation number as $\sim \sqrt{n + 1/2}$.

---

### 2. Quadrature Operators & Phase Space Uncertainty Disks
**Reference:** Chapter 2 (*Field Quantization*), Section 2.3: *Quadrature Operators for a Single-Mode Field*

#### The Physics & Mathematics
The non-Hermitian ladder operators ($\hat{a}, \hat{a}^\dagger$) can be decomposed into two dimensionless, Hermitian quadrature operators:
$$\hat{X}_1 = \frac{1}{2}(\hat{a} + \hat{a}^\dagger), \quad \hat{X}_2 = \frac{1}{2i}(\hat{a} - \hat{a}^\dagger)$$

These operators are optical analogues of dimensionless position and momentum, obeying the fundamental commutation relation $[\hat{X}_1, \hat{X}_2] = \frac{i}{2}$, which establishes the Heisenberg uncertainty relation:
$$\Delta X_1 \Delta X_2 \ge \frac{1}{4}$$

For any Fock state $|n\rangle$:
- **Mean quadrature values vanish:** $\langle n | \hat{X}_1 | n \rangle = \langle n | \hat{X}_2 | n \rangle = 0$
- **Isotropic uncertainties:**
  $$\Delta X_1 = \Delta X_2 = \sqrt{\frac{2n + 1}{4}}$$
- **Uncertainty product:**
  $$\Delta X_1 \Delta X_2 = \frac{2n + 1}{4}$$

For the vacuum state ($n = 0$), the equality holds ($\Delta X_1 \Delta X_2 = 1/4$), proving that the **vacuum is an ideal minimum-uncertainty state**.

#### Simulation Output
![Quadrature Phase Space](figures/sim2_quadrature_phase_space.png)

#### Detailed Plot Guide & Analysis
* **Subplot (a) — Quadrature Phase Space $(X_1 - X_2)$:**
  * **Axes ($X_1, X_2$):** Represent the in-phase and out-of-phase field amplitudes (equivalent to real and imaginary components of the complex optical field).
  * **Blue Solid Disk ($|0\rangle$ Vacuum State):** Classically, a quiescent field would be a point at $(0, 0)$. In quantum optics, the uncertainty principle enforces a minimum fuzzy area: a circular disk of radius $\Delta X = 1/2$.
  * **Concentric Rings ($|1\rangle, |2\rangle, |3\rangle$ Fock States):** 
    * Why rings? In a Fock state, the photon number $n$ is known with zero uncertainty ($\Delta n = 0$). By the quantum number-phase complementarity, its optical phase $\phi$ is completely undefined and uniformly distributed over $[0, 2\pi)$.
    * The ring has mean radius $\sqrt{n}$, and its radial thickness matches the quantum quadrature noise.
  * **Phase Symmetry:** All states are strictly rotationally symmetric around $(0,0)$, confirming that number states carry no preferred optical phase.

* **Subplot (b) — Quadrature Uncertainty Product:**
  * **Black Dashed Line ($1/4$):** The lower quantum bound enforced by Heisenberg's uncertainty principle ($\Delta X_1 \Delta X_2 \ge 1/4$).
  * **Blue Point ($n=0$):** The vacuum state touches the lower bound exactly, validating its status as a minimum-uncertainty state.
  * **Purple Line ($n \ge 1$):** Number states with $n \ge 1$ are *not* minimum-uncertainty states; their phase-space uncertainty area scales linearly with photon number as $\frac{2n+1}{4}$.
