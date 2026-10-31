# Computational Quantum Optics: Gerry & Knight Simulations

A pedagogical collection of numerical simulations, phase-space visualizations, and theoretical derivations based on the textbook:  
**"Introductory Quantum Optics" by Christopher C. Gerry and Sir Peter L. Knight** (Cambridge University Press).

All interactive implementations are developed in Python / Jupyter Notebooks, designed to run seamlessly on Kaggle and local environments.

---

## 📚 Table of Contents & Roadmap

- [x] [**Chapter 2: Field Quantization**](chapter_02/)
  - **Sim 01:** Single-Mode Quantum Field Fluctuations & Vacuum Noise (Sec. 2.2)
  - **Sim 02:** Quadrature operators for a single-modefield (Sec. 2.3)
  - **Sim 03:** Thermal Light Statistics (Bose-Einstein) vs. Coherent States (Sec. 2.5)
  - **Sim 04:** Vacuum Zero-Point Energy & Casimir Force Regularization (Sec. 2.6)
- [x] [**Chapter 3: Coherent States of Light**](chapter_03/)
  - **Sim 01:** Classical Limit & Electric Field Dynamics with Quantum Uncertainty Tube (Sec. 3.1 & 3.5)
  - **Sim 02:** Poissonian Photon Statistics & Mandel Q-Parameter (Sec. 3.2)
  - **Sim 03:** Non-Orthogonality & Quantum Overcompleteness in Phase Space (Sec. 3.2)
  - **Sim 04:** Phase-Space Quasi-Probability Distributions (Wigner & Husimi-Q) & Schrödinger Cat (Sec. 3.3 & 3.6)
- [ ] **Chapter 4: Squeezed States of Light** *(Upcoming)*
  - Squeeze operator, quadrature variance reduction below the vacuum level.
- [ ] **Chapter 5: Resonant Light-Atom Interactions** *(Upcoming)*
  - The Jaynes-Cummings model and Rabi oscillations.

---

## 📂 Repository Structure

```text
quantum-optics-gerry-knight/
│
├── README.md                      # Global table of contents & roadmap
│
├── chapter_02/                    # Chapter 2: Field Quantization
│   ├── README.md                  # In-depth physics, formulas & plot analysis
│   ├── notebooks/                 # Executable Jupyter notebooks (.ipynb)
│   └── figures/                   # Generated publication-quality figures (.png)
│
├── chapter_03/                    # Chapter 3: Coherent States of Light
│   ├── README.md                  # Physics theory, operator derivations & analysis
│   ├── notebooks/                 # Executable Jupyter notebooks (.ipynb)
│   └── figures/                   # Generated publication-quality figures (.png)
│
└── ... (future chapters)
