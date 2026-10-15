# Archived development branches

- [02: Planning after learning](02_planning_after_learning.ipynb): compare motion execution before learning, after learning, and with an oracle model. Requires the result exported by Notebook 1.
- [03: Batch validation](03_batch_validation.ipynb): repeat identification and task execution across hidden masses and noise seeds.
- [04: Dynamic friction identification](04_dynamic_friction_identification.ipynb): independent dynamic simulation and position-history estimation of mass and Coulomb friction. Its model is not integrated into current Notebook 6.
- [05: Frozen-gain information-aware probing](05_information_aware_probing_frozen.ipynb): earlier outer/inner planning baseline. Use the full-history notebook in `notebooks/` for the later formulation.

- [06: Original smooth baseline](06_adaptive_sls_smooth_baseline.ipynb): complete adaptive loop using the same simplified smooth model for prediction and synthetic execution, plus assumed bounded process error. This is distinct from nonsmooth Drake execution in the main Notebook 6.

Outputs are cleared. Archived files are research history, not a promise of compatibility with the latest upstream repositories.
