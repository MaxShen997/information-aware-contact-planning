# Setup

This is an integration snapshot, not a standalone solver distribution or a locked environment.

## Upstream prerequisites

Keep separate checkouts of:

- `trustworthyrobotics/adaptive_sls`, installed with its own dependencies and information-cost interface.
- `trustworthyrobotics/quasistatic-contact-SLS`, built with its custom Drake bindings. Confirm that `from pydrake.all import QuasidynamicLinearPusher` works in the contact environment.

Follow each upstream repository's build instructions. This repository does not vendor either checkout or replace their dependency setup.

## Notebook 6

Use the existing `adaptive_sls` environment with Jupyter and an installed kernel:

```bash
conda activate adaptive_sls
python -m pip install jupyterlab ipykernel
python -m ipykernel install --user --name adaptive_sls --display-name "Python (adaptive_sls)"
cd /path/to/information-aware-contact-planning
export ADAPTIVE_SLS_REPO=/absolute/path/to/adaptive_sls_complete
export CONTACT_SLS_REPO=/absolute/path/to/quasistatic-contact-SLS
export PUSHER_PROJECT="$PWD"
jupyter lab
```

Choose **Python (adaptive_sls)**. In the first code cell, review `REPO`, `CONTACT_REPO`, and `DRAKE_LAUNCH`. The default launch uses the existing Conda environment named `quasistatic-contact-SLS`; change it if your working custom Drake interpreter has another location. `CONDA_EXE` must point to your Conda executable if automatic discovery is unsuitable.

The adaptive environment runs JAX planning. A separate process in the contact environment runs Drake. Both environments must exist before running the notebook.

CPU is the default (`NB06_PLATFORM=cpu`). Set `NB06_PLATFORM=cuda` before launching Jupyter only after installing a compatible GPU JAX stack. Restart the kernel after changing platforms and inspect `jax.devices()`; no GPU benchmark is supplied here.

Review execution flags before Run All: interface audits, demonstration planning, closed-loop execution, optional comparison, result export, and worker shutdown are separate cells/options. Run code cells in order. Their numbered headings refer to code cells; introductory markdown does not change that numbering.

## Notebooks 1 and 5

Use the working custom Drake environment/kernel. Notebook 5 also reads adaptive source functions and imports the contact repository's `TrajOptProblem` and `IterativeTO` modules. Its source-parity checks can reject a different upstream API; do not silently bypass them. Notebook 5 and Notebook 6 target different stages of the integration and are not guaranteed to support the same upstream revision.

Set `PUSHER_PROJECT` to the clone root for result exports. Notebook 5 uses the environment variables above to locate dependencies; these replace its earlier machine-specific project paths. Notebook 1's final export uses the same project override. The archived notebooks retain historical notes and may need local export-path review.

## Reproducibility

No verified dependency lock or historical upstream commit pin is available in this snapshot. Notebook 6 records upstream Git commits and source hashes at runtime; retain those with exported results. Do not interpret a current upstream checkout as the exact revision used in earlier experiments.
