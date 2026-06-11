---
layout: page
title: "Software"
permalink: /software/
---

I treat well-engineered, open-source software as a first-class research output. All projects are on [GitHub](https://github.com/mjayadharan).

## DAE-FINDER

[github.com/mjayadharan/DAE-FINDER_dev](https://github.com/mjayadharan/DAE-FINDER_dev) · [`dae-finder` on PyPI](https://pypi.org/project/dae-finder/) · Python

A model-agnostic scientific-ML package for discovering differential-algebraic equations from noisy data via sparse optimization. The package exposes a scikit-learn-compatible `.fit()`/`.score()` interface and supports any algorithm conforming to that API, making it a benchmarking substrate for the broader equation-discovery community (SINDy, Weak-SINDy, IDENT, and SODAs variants on a common footing). I led the design and open-source release, and I actively maintain it. Its method-agnostic architecture was inspired by the asset-agnostic pricing-library framework I worked on at Citigroup.

## FluidLearn

[github.com/mjayadharan/FluidLearn](https://github.com/mjayadharan/FluidLearn) · Python, TensorFlow/Keras

A framework for solving fluid-flow PDEs using physics-informed neural networks (PINNs), packaged so that domain scientists can define geometry, boundary conditions, and physics without touching the underlying ML code.

## SpaceTimeDD

[github.com/mjayadharan/MMMFE-ST-DD](https://github.com/mjayadharan/MMMFE-ST-DD) · C++, deal.II

A parabolic-PDE solver using space-time multiscale mortar mixed finite elements with domain decomposition. Allows different spatial and temporal discretizations on different subdomains, which the time-dependent problems in the associated *SIAM J. Numer. Anal.* paper exploit.

## BiotDDSolver

[github.com/mjayadharan/BiotDD](https://github.com/mjayadharan/BiotDD) · C++, MPI, deal.II

A poroelastic fluid-flow simulator using MPI-based non-overlapping domain decomposition for the Biot system. Subdomain solves are independent and map naturally onto distributed-memory architectures.

## Contributions to deal.II

I am a [contributor](https://www.dealii.org/authors.html) to deal.II, the widely used open-source C++ finite element library that powers most of my HPC packages.

## In development

- An open, documented version of the electrochemical transport solver (coupled Poisson-Nernst-Planck with Butler-Volmer boundary conditions) developed at Northwestern's Trienens Institute.
- A library of reusable **agentic skill sets** and validation protocols for AI-assisted scientific computing, growing out of my current research program and the Fall 2026 Northwestern course *Agentic AI for Scientific Computing*.
