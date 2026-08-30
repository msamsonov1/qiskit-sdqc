# ⚛️ ⁠qiskit-sdqc⁠ — Software-Defined Quantum Control & Pulse Noise Inversion
Python 3.9+
Qiskit 1.0+
Open in Colab
📌 Overview
Physical quantum computing hardware in the NISQ (Noisy Intermediate-Scale Quantum) era suffers from coherent and stochastic errors: ￼ dephasing, phase jitter, laser intensity drift, and ambient electromagnetic interference (EMI).
⁠qiskit-sdqc⁠ implements firmware-level Software-Defined Quantum Control (SDQC). Rather than relying solely on physical shielding or brute-force hardware redesigns, ⁠qiskit-sdqc⁠ customizes the analog microwave/optical pulses injected into qubits. By synthesizing constructive interference for target state transformations while dynamically creating spectral notches (￼) at dominant noise frequencies, it suppresses dephasing and eliminates ￼ leakage transitions.
🔬 Key Capabilities
￼ Filter-Function Spectral Noise Inversion: Dynamically shapes ￼ and ￼ envelopes to place spectral nulls at target noise frequencies (￼ pink noise, 50 Hz power-grid EMI, high-frequency phase jitter).
￼ Multi-Derivative DRAG (Derivative Removal by Adiabatic Gate): Suppresses non-computational leakage state ￼ excitation in weakly anharmonic systems (Transmons & Neutral Atoms).
￼ Hardware-Agnostic Interface: Compatible with IBM Quantum (Qiskit Pulse / OpenPulse) and neutral-atom laser driving manifolds (￼ / ￼).
￼ Proven Improvement: Targets a ￼ boost in algorithmic quantum circuit depth and ￼ reduction in 2-qubit physical gate error rates.
📐 Mathematical Formulation
1. Driven System Hamiltonian
Under open quantum system dynamics:
2. Filter-Function Infidelity Integral
Gate infidelity ￼ under classical noise power spectral density ￼ is given by:
Where ￼ is engineered such that:
3. Generalized DRAG Envelope
🚀 Quick Start
1. Installation
2. Synthesizing a Noise-Inverting ￼-Pulse
🏗️ 4-Layer System Architecture
Layer
Module Name
Key Functional Scope
Core Stack
Layer 4
Circuit Transpiler & IR
OpenQASM 3.0 / QIR parsing, virtual-Z frame tracking
Rust, Python, QIR
Layer 3
GPU Pulse Synthesis Engine
GPU-accelerated GRAPE, Krotov, autodiff pulse shaping
C++20, CUDA, JAX, PyTorch
Layer 2
Noise Spectrometry
Automated Ramsey / CPMG tomography, Bayesian S(\omega) reconstruction
NumPy, SciPy, Filter Theory
Layer 1
Hardware Abstraction (HAL)
IBM Qiskit Pulse, Bloqade/Pulser (Neutral Atoms), AWG/FPGA drivers
gRPC, OpenPulse, JSON-RPC

📊 1-Year Proof of Concept (PoC) Roadmap
￼ Q1 (M1–M3): Master equation solver testbed; simulated gate fidelity ￼ under synthetic ￼ noise.
￼ Q2 (M4–M6): Real-time Bayesian noise spectrometry engine (￼ reconstruction).
￼ Q3 (M7–M9): Hardware validation on IBM Quantum / Neutral Atom QPUs (￼ 2-qubit error reduction).
￼ Q4 (M10–M12): Multi-qubit algorithmic execution (VQE/QAOA); ￼ Quantum Volume scaling on 16+ qubits.
📄 License & Attribution
Distributed under the MIT License. Created as part of the Software-Defined Quantum Control Research Initiative. Pull requests and algorithmic contributions are welcome!qiskit-sdqc