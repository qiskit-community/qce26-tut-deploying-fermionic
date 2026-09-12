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

Simulating fermionic systems, such as molecules and materials, is a widely
anticipated application of quantum computers with scientific and industrial
relevance. In recent years, quantum-centric supercomputing (QCSC) has emerged as
a promising paradigm for achieving practical applications in this domain, even
before fault-tolerant quantum computers are built. In a QCSC system, quantum
processing units (QPUs) are tightly integrated with GPUs and CPUs, and these
classical and quantum resources work together to solve problems beyond the reach
of either resource working alone.

In this tutorial, participants will learn how to use open-source software tools,
primarily from the Qiskit ecosystem, to map fermionic problems onto quantum
computers and run them on QCSC systems. The ground state problem for fermionic
systems will be used as a motivating example, and it will be solved using the
sample-based quantum diagonalization (SQD) algorithm and its variant,
sample-based Krylov quantum diagonalization (SKQD). After learning the theory of
these algorithms and simulating small example workflows, participants will run a
larger QCSC workflow using the recently introduced quantum resource management
interface (QRMI).

Participants will use `qiskit-fermions` to map fermionic operators to qubit
operators, `ffsim` to construct and simulate quantum circuits for variational
ansatzes and time evolution, `qiskit-addon-sqd` to run sample-based quantum
diagonalization (SQD) and sample-based Krylov quantum diagonalization (SKQD),
and `qrmi` to deploy and manage resources within a QCSC workflow.

## Target audience

The target audience for this tutorial includes academic and industry researchers
looking to apply QCSC workflows to tackle problems they encounter in their own
work, as well as quantum computational scientists, developers, and educators
seeking to learn state-of-the-art techniques for simulating chemistry and
materials systems.

## Learning objectives

By the end of the tutorial, participants will be able to:

- Use `qiskit-fermions` to map fermionic operators to qubit operators.
- Use `ffsim` to construct and simulate fermionic circuits for variational
  ansatzes and time evolution.
- Approximate ground state energies of molecular and materials systems with the
  SQD and SKQD algorithms using `qiskit-addon-sqd`.
- Deploy and manage quantum resources within a QCSC workflow using `qrmi`.

Attendees will benefit by gaining practical, hands-on experience with
state-of-the-art quantum algorithms and infrastructure relevant to near-term
applications in quantum chemistry, biophysics, and materials science.

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

| Duration | Format           | Topic                                                                                                                    |
| -------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------ |
| 15 min   | Slides           | Overview of QCSC infrastructure.                                                                                         |
| 30 min   | Jupyter notebooks | Quantum resource management using `qrmi`.                                                                                |
| 45 min   | Jupyter notebooks | Combine the previously introduced software tools to run SQD and SKQD within a QCSC workflow, using IBM QPUs.             |

## Notebooks

This tutorial will use the following notebooks:
- [Sample-based quantum diagonalization of a chemistry Hamiltonian](https://quantum.cloud.ibm.com/docs/en/tutorials/sample-based-quantum-diagonalization)
- [Scale SQD chemistry workflows with Fulqrum](https://github.com/Qiskit/qiskit-addon-sqd/blob/main/docs/guides/integrate_fulqrum.ipynb)
- [Simulate Hamming weight-preserving Qiskit circuits with ffsim](https://qiskit-community.github.io/ffsim/how-to-guides/qiskit-circuits-sim.html)

## Software tools

- [`ffsim`](https://github.com/qiskit-community/ffsim) — build and simulate quantum circuits for variational ansatzes and time evolution.
- [`qiskit-addon-sqd`](https://github.com/Qiskit/qiskit-addon-sqd) — run the SQD configuration recovery loop.
- [`fulqrum`](https://github.com/qiskit-community/fulqrum) — interface to faster eigenvalue solvers for SQD.
- [`qrmi`](https://github.com/qiskit-community/qrmi) — vendor-agnostic library to manage QPU resources on HPC systems.
- [`qiskit-fermions`](https://github.com/Qiskit/qiskit-fermions) — fermionic circuit class, fermion-to-qubit mappings, and circuit transpilation beyond Jordan-Wigner.

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
