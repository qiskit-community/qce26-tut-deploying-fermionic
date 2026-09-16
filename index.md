---
title: Deploying fermionic simulations on quantum-centric supercomputers
layout: page
---

A hands-on tutorial on using open-source software tools, primarily from the
Qiskit ecosystem, to simulate fermionic systems on quantum-centric
supercomputing (QCSC) infrastructure — covering the full workflow from mapping
fermions to qubits through executing sample-based quantum diagonalization
algorithms on real quantum hardware.

**Part of [QCE 2026 — IEEE Quantum Week](https://qce.quantum.ieee.org/2026/)**
([tutorials schedule](https://qce.quantum.ieee.org/2026/qce26-schedule/tutorial-schedule/))

**Wednesday, September 16, 2026**:

- **Session 1:** 10:00–11:30 AM EDT
- **Session 2:** 1:00–2:30 PM EDT

## Summary

Simulating fermionic systems, including molecules and materials, is one of the most widely anticipated scientific applications of quantum computing. Quantum-centric supercomputing (QCSC) provides a practical framework for pursuing these applications before fault-tolerant quantum computers are available by integrating quantum processing units (QPUs) with CPUs and GPUs in heterogeneous scientific workflows. Rather than treating the QPU as a standalone accelerator, QCSC combines quantum sampling, classical electronic-structure methods, high-performance computing, and resource management so that each computational resource is used where it is most effective.

In this tutorial, participants will learn how to build and execute fermionic simulation workflows using open-source tools from the Qiskit ecosystem. The ground-state problem will serve as the primary application. The tutorial begins with the foundations of sample-based quantum diagonalization (SQD) and sample-based Krylov quantum diagonalization (SKQD), including fermion-to-qubit mappings, quantum state preparation, sampling, and classical subspace diagonalization. Participants will first explore these algorithms on small systems where the complete workflow can be understood and simulated directly.

The tutorial then develops the QCSC perspective further by showing how large fermionic problems can be decomposed into embedded correlated subproblems and solved using heterogeneous classical and quantum solvers. Using the open-source Quantum Fragment Methods workflow, participants will see how an embedded wavefunction (EWF) calculation can route different fragments to FCI, CCSD, or SQD depending on their computational requirements, reconstruct molecular observables from fragment solutions, and reuse quantum samples with alternative post-processing strategies such as TrimSQD. This provides a concrete example of how quantum algorithms can operate as components within much larger electronic-structure calculations rather than requiring the full scientific problem to fit on a QPU.

Finally, participants will examine the systems layer needed to execute these workflows on QCSC infrastructure. The tutorial introduces the Quantum Resource Management Interface (QRMI), including its resource lifecycle, vendor-portable abstraction, environment-based configuration, and integration with HPC schedulers such as Slurm. Participants will see how QPUs can be allocated and consumed alongside conventional HPC resources, connecting the quantum algorithm layer to heterogeneous CPU/GPU/QPU execution.

Participants will use qiskit-fermions to map fermionic operators to qubit operators, ffsim to construct and simulate quantum circuits for variational ansatzes and time evolution, qiskit-addon-sqd to run SQD and SKQD, Quantum Fragment Methods to construct embedded and adaptively routed fermionic workflows, and qrmi to access and manage quantum resources within QCSC environments.

## Target audience

The target audience for this tutorial includes academic and industry researchers
looking to apply QCSC workflows to tackle problems they encounter in their own
work, as well as quantum computational scientists, developers, and educators
seeking to learn state-of-the-art techniques for simulating chemistry and
materials systems.

## Learning objectives

By the end of the tutorial, participants will be able to:

- Use qiskit-fermions to map fermionic operators to qubit operators.
- Use ffsim to construct and simulate fermionic circuits for variational ansatzes and time evolution.
- Approximate ground state energies of molecular and materials systems with the SQD and SKQD algorithms using qiskit-addon-sqd.
- Construct and reason about heterogeneous fermionic workflows in which embedded subproblems are assigned to different classical and quantum solvers.
- Understand how quantum sampling, classical post-processing, embedding, and reconstruction interact within a larger QCSC workflow.
- Deploy and manage quantum resources within a QCSC workflow using qrmi, including resource discovery, lifecycle management, and integration with HPC schedulers.

Attendees will benefit by gaining practical, hands-on experience with state-of-the-art quantum algorithms and infrastructure relevant to near-term applications in quantum chemistry, biophysics, and materials science, while also developing an understanding of how these tools fit together in scalable CPU/GPU/QPU workflows.

## Prerequisites

You should have basic familiarity with Python and linear algebra.

You are expected to bring their own computer with Qiskit installed.
To install Qiskit, follow the instructions [here](https://quantum.cloud.ibm.com/docs/en/guides/install-qiskit).
The tutorial will involve submitting jobs to IBM QPUs. To participate in this
activity, install the IBM Quantum Compute client following the instructions
[here](https://quantum.cloud.ibm.com/docs/en/guides/install-qiskit-runtime).

The tutorial involves running software that only supports Linux or macOS. If you use Windows, we recommend that you set up [Windows Subsystem for Linux (WSL)](https://learn.microsoft.com/en-us/windows/wsl/), which provides an appropriate Linux environment.

## Agenda

The tutorial is delivered in two 90-minute sessions. The first session covers
software tools for building and simulating quantum circuits for fermionic
simulations, and executing quantum algorithms for the fermionic ground state
problem suitable for QCSC workflows. The second session covers the actual
implementation of the algorithms on QCSC infrastructure.

### Session 1 — Quantum simulation of fermionic systems

#### 10:00–11:30 AM EDT, Wed Sep 16, 2026

| Duration | Format           | Topic                                                                                                                            |
| -------- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| 15 min   | Slides           | Review of quantum simulation of fermions, including second quantization and the ground state problem.                            |
| 30 min   | Jupyter notebooks | Construct and simulate fermionic quantum circuits using `ffsim`. Approximate ground state energies with SQD using `qiskit-addon-sqd`.|
| 45 min   | Jupyter notebooks | Guided coding -- Improve SQD efficiency with `fulqrum`. Explore impact of SQD hyperparameters. Explore SKQD. |

### Session 2 — QCSC workflow

#### 1:00–2:30 PM EDT, Wed Sep 16, 2026

| Duration | Format           | Topic                                                                                                                                 |
| -------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| 40 min   | Slides                        | Overview of QCSC infrastructure.                                                                                         |
| 30 min   | Guided tutorial walkthrough   | Quantum resource management using `qrmi`.                                                                                |
| 45 min   | Slides + software walkthrough | Combine the previously introduced software tools to run SQD and SKQD within a QCSC workflow, using IBM QPUs.             |

## Notebooks

This tutorial will use the following notebooks:
- [Sample-based quantum diagonalization of a chemistry Hamiltonian](https://quantum.cloud.ibm.com/docs/en/tutorials/sample-based-quantum-diagonalization)
- [Scale SQD chemistry workflows with Fulqrum](https://github.com/Qiskit/qiskit-addon-sqd/blob/main/docs/guides/integrate_fulqrum.ipynb)
- [Simulate Hamming weight-preserving Qiskit circuits with ffsim](https://qiskit-community.github.io/ffsim/how-to-guides/qiskit-circuits-sim.html)
- [Run the macromolecule simulation with Quantum Fragment Methods](https://github.com/qiskit-community/quantum-fragment-methods/blob/IEEE_QW_2026/examples/notebook_demos/ewf_sqd_demo/ewf_sqd.ipynb)
- [Run quantum workloads with QRMI](https://quantum.cloud.ibm.com/docs/en/tutorials/run-quantum-workloads-with-qrmi)

## Software tools

- [`ffsim`](https://github.com/qiskit-community/ffsim) — build and simulate quantum circuits for variational ansatzes and time evolution.
- [`qiskit-addon-sqd`](https://github.com/Qiskit/qiskit-addon-sqd) — run the SQD configuration recovery loop.
- [`fulqrum`](https://github.com/qiskit-community/fulqrum) — interface to faster eigenvalue solvers for SQD.
- [`qrmi`](https://github.com/qiskit-community/qrmi) — vendor-agnostic library to manage QPU resources on HPC systems.
- [`qiskit-fermions`](https://github.com/Qiskit/qiskit-fermions) — fermionic circuit class, fermion-to-qubit mappings, and circuit transpilation beyond Jordan-Wigner.
- [`quantum-fragment-methods`](https://github.com/qiskit-community/quantum-fragment-methods) - Python package for quantum chemistry tailored toward fragment-based embedding and quantum algorithms applied to macromolecule simulations. 
## Presenters

**Kevin J. Sung**. Quantum algorithm engineer at IBM. Lead developer of `ffsim` and `qiskit-addon-sqd`.

**Thaddeus Pellegrini**. Quantum algorithm engineer at IBM.
Lead developer of [`quantum-fragment-methods`](https://github.com/qiskit-community/quantum-fragment-methods),
a Python framework developed in collaboration with the Cleveland Clinic Foundation for quantum chemistry simulations of proteins and drug targets.

## Further reading

- [SQD paper](https://doi.org/10.1126/sciadv.adu9991)
- [SKQD paper](https://arxiv.org/abs/2501.09702)
- [QRMI paper](https://arxiv.org/abs/2506.10052)
- [LUCJ explanation at ffsim docs](https://qiskit-community.github.io/ffsim/explanations/lucj.html)
- [Crossing the 12,000-atom barrier with heterogeneous quantum-classical supercomputing: quantum chemistry of protein-ligand complexes](https://arxiv.org/abs/2605.01138)
- [Protein-Ligand Free Energy Perturbation on Quantum Hardware](https://arxiv.org/abs/2604.09857?utm_source=chatgpt.com)
- [Quantum Computations on Fusion Blanket Molten Salts](https://arxiv.org/abs/2606.30402?utm_source=chatgpt.com)
