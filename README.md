# Information-Aware Contact Planning

Research notebooks for planning informative robotic pushes while limiting object displacement, contact force, and command variation. The current development reference connects adaptive SLS planning to smooth contact prediction and nonsmooth Drake execution.

**Status:** research prototype. The current integration is one-dimensional and mass-only. The supplied Notebook 6 includes one completed local six-step Drake run; see [saved run evidence](docs/supplied_nb06_run.md). Broader validation remains open. Planar pushing and integrated mass/friction learning are future extensions.

## Start here

| Notebook | Purpose | Position in the project |
| --- | --- | --- |
| [01: Linear pusher identification](notebooks/01_linear_pusher_identification.ipynb) | Analytical response, Drake comparison, and bounded mass estimation from displacement | Foundation |
| [05: Full-history information-aware probing](notebooks/05_information_aware_probing_full_history.ipynb) | Balance disturbance and predicted learning using full-history derivatives and Drake trajectory-optimization subproblems | Earlier planning formulation |
| [06: Adaptive SLS / Drake integration](notebooks/06_adaptive_sls_drake_integration.ipynb) | Smooth prediction, smoothing-error allowances, adaptive planning, nonsmooth Drake observations, and online estimation | **Main development reference; supplied local run completed** |

[Archived experiments](archive/README.md) preserve the dynamic-friction identification branch and frozen-gain planning baseline. Notebook numbering follows development history; missing numbers are intentional.

## Current architecture

At each executed step, the controller plans six position commands, checks convergence and first-step limits, executes only the first command, updates the parameter estimate and uncertainty, and replans from the observed state.

- **Prediction:** a differentiable JAX specialization of the fixed-barrier, single-contact pusher model.
- **Planning:** the upstream adaptive SLS controller, with motion, force, and command-change penalties plus its information-reward machinery.
- **Execution:** the custom nonsmooth `QuasidynamicLinearPusher` in Drake, launched in a separate environment.
- **Learning:** upstream observable-subspace and posterior-generator functions, connected to the observed transition by notebook-specific code.
- **Error allowances:** analytic smoothing enclosure, separate numerical-solver budgets, and parameter/trajectory Taylor allowances. Numerical budgets remain assumptions checked during execution.

Notebook 6 uses exact state observations and object-position-based parameter updates. It does not model table friction or inertial velocity. The archived friction notebook uses a separate dynamic model.

## Running

Follow [setup.md](docs/setup.md). These notebooks require custom upstream repositories; installing standard `pydrake` alone is insufficient. Start with CPU execution. GPU support in the adaptive solver does not imply that a particular experiment ran on a GPU.

Outputs are cleared to keep notebooks readable and avoid stale displays. Selected text from the supplied Notebook 6 run is preserved separately. Run notebooks manually in the documented kernels. No simulations were rerun for this publication, and no independent reproduction is claimed. See [validation status](docs/validation.md).

## Sources and contribution

This repository contains experiment definitions, integration code, estimators/adapters, planning formulations, and diagnostics developed around existing research software. It does not claim authorship of the upstream adaptive solver or contact simulator.

- [trustworthyrobotics/adaptive_sls](https://github.com/trustworthyrobotics/adaptive_sls): adaptive SQP/SLS/ADMM planning, information-cost machinery, and posterior uncertainty updates.
- [trustworthyrobotics/quasistatic-contact-SLS](https://github.com/trustworthyrobotics/quasistatic-contact-SLS): contact dynamics, custom Drake pusher, and earlier trajectory-optimization interfaces.
- [Certified Gradient-Based Contact-Rich Manipulation via Smoothing-Error Reachable Tubes](https://arxiv.org/abs/2602.09368), version 2: smoothing-error construction used in Notebook 6.
- *Planning to Learn: Real-Time Robust Adaptive Control on the GPU with Guaranteed Future Learning*: adaptive-planning research underlying the upstream adaptive implementation.

See [source mapping and reproducibility notes](docs/sources.md). Upstream repositories and paper PDFs are not bundled. No project-wide license is assigned in this initial snapshot; upstream components retain their own terms.
