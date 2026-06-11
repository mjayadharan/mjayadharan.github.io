---
layout: page
title: "Research"
permalink: /research/
---

My research sits at the intersection of scientific computing, numerical analysis, inverse problems, and scientific machine learning, organized along two complementary directions: **forward problems** (accurate, stable, efficient numerical solvers for complex multiphysics PDE models) and **inverse problems and model discovery** (methods that infer governing equations, hidden mechanisms, or parameters from data in ways that are interpretable, stable, and useful to domain scientists).

The unifying triad across all of it: **stability, interpretability, usability**.

## 1. Stabilizing library-based equation discovery

Sparse-regression methods for discovering equations from data (the SINDy family and our own SODAs) can be ill-posed under correlated features, conservation laws, and limited data. I diagnose these failure modes through the lens of inverse-problem theory and develop fixes, including QR-based simultaneous orthogonalization and minimal library determination.

Our algorithm **SODAs** (*Proc. Royal Society A*, 2026) extends sparse equation learning to differential-algebraic systems, recovering both dynamic equations and algebraic constraints without reducing the system to ODEs. It scales from chemical reaction networks to full power-grid models.

<div class="figrow">
<figure>
<img src="/items/im/research/ieee39_powergrid.svg" alt="Percentage of algebraic relationships correctly identified vs number of perturbations on the IEEE-39 power grid, for several noise levels">
<figcaption>SODAs on the IEEE-39 bus power grid: algebraic constraints are recovered reliably as perturbation data accumulates, even at 20&ndash;40dB measurement noise.</figcaption>
</figure>
<figure>
<img src="/items/im/research/crn_svd_noisy.svg" alt="SVD analysis of a chemical reaction network candidate library with 15% noise">
<figcaption>Diagnosing ill-conditioning: SVD spectra of candidate libraries reveal structural redundancy that makes naive sparse regression fragile under noise.</figcaption>
</figure>
</div>

## 2. Optimization for ill-conditioned scientific inverse problems

Parameter estimation where every step requires a stiff ODE/PDE solve. Current contribution: a multiple-shooting framework with guess propagation that converges where single-forward-solve optimization fails, with supporting small-noise convergence theory.

## 3. Fast and flexible solvers for hybrid electrochemical systems

Galerkin weak-form solvers for coupled Poisson-Nernst-Planck equations with nonlinear Butler-Volmer boundary conditions, handling heterogeneous media and complex geometries, designed for inverse-problem compatibility. Part of the Trienens Institute for Sustainability and Energy at Northwestern, in collaboration with chemical engineers working on reactor design and battery materials.

## 4. Hybrid mechanistic and machine-learning models

Monomial- and polynomial-augmented neural ODEs that outperform vanilla neural ODEs in extrapolation and allow symbolic structure recovery.

## 5. Agentic AI for scientific computing (emerging, 2025 to present)

Protocols, validation frameworks, and reusable agentic skill sets for using frontier AI agents in scientific computing workflows, anchored in a coupled PNP electrochemical inverse problem. Includes a strong accessibility angle: cost-aware workflows that let researchers on smaller models achieve outcomes associated with frontier models. First formal course offering: *Agentic AI for Scientific Computing*, Northwestern Applied Mathematics, Fall 2026.

<figure>
<img src="/items/im/research/agentic_ai_workflow.svg" alt="Workflow: a computational scientist steers frontier AI agents through agentic skill sets; agent outputs are audited by validation protocols before results are trusted">
<figcaption>The agentic-AI research program: skill sets carry discipline-specific context to the agent, and validation protocols audit every output before it is trusted.</figcaption>
</figure>

## PhD-era foundations: multiphysics PDEs and domain decomposition

Domain decomposition and time-splitting methods for the Biot system of poroelasticity, and space-time multiscale mortar mixed finite-element methods for parabolic equations, with applications to geomechanics and subsurface flow. The MPI-based parallel implementations are released as open-source packages.

<figure>
<img src="/items/im/research/biotdd_simulation.gif" alt="Animated poroelastic flow simulation computed with BiotDD">
<figcaption>Poroelastic flow simulated with <a href="https://github.com/mjayadharan/BiotDD">BiotDD</a>, my MPI-parallel domain-decomposition solver for the Biot system.</figcaption>
</figure>

<div class="figrow">
<figure>
<img src="/items/im/research/spacetime_dd.png" alt="Space-time domain decomposition: non-matching subdomain meshes and the computed pressure solution">
<figcaption>Space-time domain decomposition with non-matching grids across subdomains (<a href="https://github.com/mjayadharan/MMMFE-ST-DD">MMMFE-ST-DD</a>).</figcaption>
</figure>
<figure>
<img src="/items/im/research/pressure_spacetime.png" alt="Pressure solution visualized on a global space-time grid">
<figcaption>Computed pressure visualized on the global space-time grid: two space dimensions plus time as the vertical axis.</figcaption>
</figure>
</div>

## Application domains

Electrochemistry and reactor design · battery modeling and energy storage · systems biology and biophysics · power-grid dynamics · chemical engineering · fluid dynamics and poroelasticity · quantitative finance.

## Collaborations

I work with collaborators across applied mathematics, chemical and biological engineering, and electrical engineering, at Northwestern (Mangan group, Trienens Institute, NITMB, and discussions with the Center for Optimization and Statistical Learning), the University of Pittsburgh, City University of Hong Kong, and the Indian Institute of Space Science and Technology (IIST).

See also: [Publications](/publications/) · [Software](/software/) · [Recent research overview](/recent-research/)
