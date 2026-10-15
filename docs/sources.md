# Source mapping

| Upstream file | Use |
| --- | --- |
| Contact: `multibody/quasidynamic/quasidynamic_linear_pusher.cc` | Single-contact pusher dynamics and nonsmooth Drake execution |
| Contact: `multibody/quasidynamic/quasidynamic_differentiable_contact_model.cc` | Smooth contact model and disturbance representation |
| Contact: `solvers/solve_conic_program.cc` | Underlying nonsmooth / log-barrier optimization conventions |
| Contact: `examples/planning_through_contact/algorithms/traj_opt_problem.py` | Notebook 5 trajectory-optimization problem interface |
| Contact: `examples/planning_through_contact/algorithms/iterative_to.py` | Notebook 5 local trajectory-optimization subproblems |
| Adaptive: `src/gpu_sls/generic_mpc_wrapper.py` | Notebook 6 high-level controller interface |
| Adaptive: `src/gpu_sls/sqp.py` | Nonlinear optimization and local search directions |
| Adaptive: `src/gpu_sls/gpu_sls.py` | Uncertainty propagation, information reward, constraint tightening, and estimator primitives |
| Adaptive: `src/gpu_sls/gpu_admm.py` | Numerical constrained subproblem solution |

Notebook 5 uses an adapted scalar uncertainty forecast with an outer planning iteration and Drake subproblems. Its full-history version differentiates the forecast through earlier commands. Notebook 6 invokes the complete adaptive planning stack instead of that notebook-level frozen-gain outer/inner structure. The upstream solver still has its own internal iterations.

Notebook 6 prediction is a JAX implementation of the analytic one-contact specialization, not a call into Drake on each optimizer evaluation. Drake is used for execution and optional parity audits. Its error budgets distinguish smoothing mismatch, numerical acceptance allowances, and Taylor remainders.

The notebook includes narrowly guarded compatibility handling for a known JAX diagnostic-index dtype issue and binds a custom analytic remainder callback through a private solver interface. These are source-version-sensitive integrations, not upstream API guarantees. No upstream checkout is modified by the notebook.

Historical dependency SHAs are not asserted. Runtime provenance is recorded in Notebook 6. `notebook_manifest.json` records hashes of the input notebook snapshots and publication copies; those hashes are file provenance, not evidence of successful execution.

The publication copies clear outputs, add a publication note, and make legacy Notebook 1/5 paths configurable. Mathematical code is otherwise preserved. Papers, build trees, environment directories, and complete upstream repositories are excluded.
