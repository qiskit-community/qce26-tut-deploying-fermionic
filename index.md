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

- **Session 1:** 1:00–2:30 PM EDT
- **Session 2:** 3:00–4:30 PM EDT

## Abstract

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

Participants are expected to have basic familiarity with Python and linear
algebra.

## Target audience

The target audience for this tutorial includes academic and industry researchers
looking to apply QCSC workflows to tackle problems they encounter in their own
work, as well as quantum computational scientists, developers, and educators
seeking to learn state-of-the-art techniques for simulating chemistry and
materials systems.

## Agenda

The tutorial is delivered in two 90-minute sessions. The first session covers
software tools for building and simulating quantum circuits for fermionic
simulations, and executing quantum algorithms for the fermionic ground state
problem suitable for QCSC workflows. The second session covers the actual
implementation of the algorithms on QCSC infrastructure.

### Session 1 — Quantum simulation of fermionic systems

#### 1:00–2:30 PM EDT, Wed Sep 16, 2026

| Duration | Format           | Topic                                                                                                                            |
| -------- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| 15 min   | Slides           | Review of quantum simulation of fermions, including second quantization and the ground state problem.                            |
| 45 min   | Jupyter notebooks | Map fermions to qubits using `qiskit-fermions`; construct and simulate quantum circuits for variational ansatzes and time evolution using `ffsim`. |
| 30 min   | Jupyter notebooks | Approximate ground state energies with SQD and SKQD using `qiskit-addon-sqd`.                                                     |

### Session 2 — QCSC workflow

#### 3:00–4:30 PM EDT, Wed Sep 16, 2026

| Duration | Format           | Topic                                                                                                                    |
| -------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------ |
| 15 min   | Slides           | Overview of QCSC infrastructure.                                                                                         |
| 30 min   | Jupyter notebooks | Quantum resource management using `qrmi`.                                                                                |
| 45 min   | Jupyter notebooks | Combine the previously introduced software tools to run SQD and SKQD within a QCSC workflow, using IBM QPUs.             |

## Notebooks and installation

Notebooks and installation instructions will be posted here
before the tutorial. Note that some notebooks require internet
access to submit jobs to and retrieve results from quantum hardware.

## Software tools

- [`ffsim`](https://github.com/qiskit-community/ffsim) — construct and simulate
  quantum circuits for variational ansatzes and time evolution.
- [`qiskit-addon-sqd`](https://github.com/Qiskit/qiskit-addon-sqd) — run SQD and
  SKQD.
- [`qiskit-fermions`](https://github.com/Qiskit/qiskit-fermions) — map fermionic
  operators to qubit operators.
- [`qrmi`](https://github.com/qiskit-community/qrmi) — quantum resource management
  interface for QCSC workflows.

## Presenters

**Kevin J. Sung**. Software developer and researcher at IBM. Lead developer of `ffsim` and `qiskit-addon-sqd`.

**Thaddeus Pellegrini**. Quantum algorithm engineer at IBM. Lead developer of Quantum Fragment Methods, a Python framework developed in collaboration with the Cleveland Clinic Foundation for quantum chemistry simulations of proteins and drug targets.

**Pedro Rivero**. Global technical lead and manager at IBM. Leads collaborations with U.S. national labs, research institutions, and industry partners to expand the practical applications of quantum technologies.

## Further reading

- **SQD** — *Chemistry beyond the scale of exact diagonalization on a
  quantum-centric supercomputer*, Science Advances **11**(25):eadu9991 (2025).
  [doi:10.1126/sciadv.adu9991](https://doi.org/10.1126/sciadv.adu9991)
- **SKQD** — *Sample-based Krylov quantum diagonalization*.
  [arXiv:2501.09702](https://arxiv.org/abs/2501.09702)
- **QRMI** — *Quantum resource management interface*.
  [arXiv:2506.10052](https://arxiv.org/abs/2506.10052)
- **`ffsim` LUCJ ansatz explanation** —
  <https://qiskit-community.github.io/ffsim/explanations/lucj.html>
- **IBM SQD tutorial** —
  <https://quantum.cloud.ibm.com/docs/en/tutorials/sample-based-quantum-diagonalization>
