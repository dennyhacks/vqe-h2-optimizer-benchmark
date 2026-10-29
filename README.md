# VQE H2 Optimizer & Ansatz Benchmark

A quantum computing project comparing classical optimizers (`COBYLA`, `SPSA`, `SLSQP`) and ansatz depths (`RealAmplitudes` reps=1 vs reps=2) for finding the ground-state energy of the Hydrogen molecule ($H_2$) at equilibrium bond length (0.735 Å), evaluated under both noiseless and noisy quantum simulations.

## Project Highlights
- **Target Molecule:** $H_2$ at bond distance $R = 0.735$ Å (2-qubit Jordan-Wigner Hamiltonian).
- **Exact Ground State:** $-1.137306$ Hartree (including $+0.719968$ Hartree nuclear repulsion).
- **12 Experimental Configurations:**
  - 2 Regimes: Ideal Statevector (Noiseless) vs. 1024 Shots + Depolarizing Gate Noise (Noisy).
  - 2 Ansatz Depths: Shallow (`reps=1`, 4 parameters) vs. Deeper (`reps=2`, 6 parameters).
  - 3 Optimizers: COBYLA, SPSA, SLSQP (`maxiter=100`, fixed seed 42).
- **Educational Explanations:** Every code section includes beginner-friendly markdown explanations with real-world analogies (`📘 EXPLAIN:`).
- **Academic Sections:** Results & Discussion, Limitations, Syllabus Mapping, 10 Viva Q&As, and a 6-Slide Defense Outline.

## Key Findings
1. **Noiseless:** SLSQP converged fastest (~31 evaluations) with micro-Hartree error.
2. **Noisy:** SPSA and COBYLA exhibited superior resilience against measurement and gate noise.
3. **Circuit Depth:** Deeper circuits (`reps=2`) accumulated almost double the error of shallow circuits (`reps=1`) under noise, demonstrating that shallow circuits are optimal for NISQ hardware.

## Installation & Usage

```bash
git clone https://github.com/dennyhacks/vqe-h2-optimizer-benchmark.git
cd vqe-h2-optimizer-benchmark
pip install -r requirements.txt
jupyter notebook vqe_h2.ipynb
```

## Tech Stack
- Python 3.9+
- Qiskit 1.x
- Qiskit-Aer
- Qiskit-Algorithms
- SciPy, NumPy, Matplotlib, Pandas
