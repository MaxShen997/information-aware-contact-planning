# Supplied Notebook 6 run output
Extracted from the user-uploaded executed notebook; not rerun during publication.
This is a saved single-run record, not an independent reproduction or multi-case validation.

## Uploaded notebook cell index 20 (zero based)

```text
Compiling and solving the smooth-model plan with error bounds enabled...
Information weight: 3.0
Diagnostics: {'sls_converged': True, 'sls_residual': 5.174954837124e-07, 'admm_converged': True, 'admm_iterations': 125, 'admm_primal_residual': 9.713573153957986e-07, 'admm_dual_residual': 1.4851911240883273e-06, 'admm_primal_tolerance': 1.000010007993752e-06, 'admm_dual_tolerance': 1.515288690982949e-06, 'admm_primal_worst_flat_index': 44, 'admm_primal_worst_z': -2.944205980964691e-08, 'admm_primal_worst_w': -1.0007993752054455e-06, 'seconds': 7.046372261000215, 'dynamics_defect': 4.0939474033052647e-16, 'nominal_violation': -3.4649880707726677e-07, 'tightened_violation': 9.713573154014042e-07, 'parameter_domain_ok': True, 'worst_constraint': 'minimum excitation', 'worst_stage': 3, 'max_taylor_allowance_um': [99.50175322949634, 26.761864896467724, 0.0]}
Plan accepted: True | first-step guard: True {'max_residual': -0.024255618910745787, 'force_upper_N': np.float64(0.003831572052248966), 'object_lower_m': 0.20004255618910746, 'object_upper_m': 0.20028624076302817, 'next_state_lower_scaled': array([0.00231272, 0.00425562, 0.38546992]), 'next_state_upper_scaled': array([0.04072809, 0.02862408, 0.38546992])}
Six command offsets [mm]: [3.85469921 1.16826089 1.21232119 1.25638398 1.30046088 1.34453902]
Nominal object displacement [mm]: [0.         0.16824473 0.21231279 0.25638052 0.30044803 0.34451595
 0.38858431]
No command executed in this cell.

```

## Uploaded notebook cell index 22 (zero based)

```text
Planning step 1/6...
  solve=3.39s, ADMM=True, SLS=True, guard=True
  Drake travel=0.1001 mm, mass interval=[13.69453958 16.46577692] g, covered=True
Planning step 2/6...
  solve=0.06s, ADMM=True, SLS=True, guard=True
  Drake travel=0.1261 mm, mass interval=[13.69453958 16.46577692] g, covered=True
Planning step 3/6...
  solve=0.13s, ADMM=True, SLS=True, guard=True
  Drake travel=0.1522 mm, mass interval=[13.69453958 16.46577692] g, covered=True
Planning step 4/6...
  solve=0.13s, ADMM=True, SLS=True, guard=True
  Drake travel=0.1782 mm, mass interval=[13.69453958 16.46577692] g, covered=True
Planning step 5/6...
  solve=0.13s, ADMM=True, SLS=True, guard=True
  Drake travel=0.2042 mm, mass interval=[13.69453958 16.46577692] g, covered=True
Planning step 6/6...
  solve=0.13s, ADMM=True, SLS=True, guard=True
  Drake travel=0.2302 mm, mass interval=[13.69453958 16.46577692] g, covered=True
Status: completed | learned from 6 / 6 executions

```

## Uploaded notebook cell index 24 (zero based)

```text
Status: completed
Recorded information weight: 3.0
step 1: travel=0.1001 mm, force=3.755 mN, width=2.7712 g, covered=True, bound=True
step 2: travel=0.1261 mm, force=0.976 mN, width=2.7712 g, covered=True, bound=True
step 3: travel=0.1522 mm, force=0.976 mN, width=2.7712 g, covered=True, bound=True
step 4: travel=0.1782 mm, force=0.976 mN, width=2.7712 g, covered=True, bound=True
step 5: travel=0.2042 mm, force=0.976 mN, width=2.7712 g, covered=True, bound=True
step 6: travel=0.2302 mm, force=0.976 mN, width=2.7712 g, covered=True, bound=True
Final mass width [g]: 2.7712373483044557
Final object displacement [mm]: 0.2302083810197808
Peak executed model force [mN]: 3.754771390511516

```

