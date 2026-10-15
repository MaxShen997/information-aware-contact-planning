# Validation status

This publication was checked for notebook JSON readability and Python code-cell syntax. It was not executed during packaging.

| Component | What can be said |
| --- | --- |
| Notebook 1 | Earlier local experiments compared analytical and Drake transitions, estimated mass, and evaluated held-out predictions. Initial stringent all-state agreement checks did not pass everywhere, particularly near contact onset. Operating-range allowances are empirical. |
| Notebook 5 | Earlier local runs evaluated predicted information versus observed interval width and displacement across masses/seeds. Full-history optimization was not universally better; some settings reached iteration limits. Outputs are not included as a reproducibility claim. |
| Original smooth-only Notebook 6 | Archived as the matched synthetic plant baseline with assumed process bounds. Its earlier results do not establish validation of the new Drake integration. |
| Current Notebook 6 | The uploaded notebook records nine completed source/interface fixtures and a completed six-step Drake experiment. All six reported SLS/ADMM/guard checks passed; final displacement was 0.230208 mm, final mass interval approximately [13.694540, 16.465777] g, and peak executed model force 3.754771 mN. Saved text is linked below. This is one supplied run, not independent or broad validation. |
| Archived Notebook 4 | Dynamic mass/friction identification was explored separately. Significant timestep-refinement discrepancies limit claims about continuous-physics accuracy. |

Before reporting new results, retain upstream source provenance, solver convergence and constraint diagnostics, source-parity audits, numerical-budget checks, coverage evaluations, and paired information-weight comparisons. A failed/stopped run must remain visible. Observed coverage is not an unconditional guarantee, and a predicted information score is not measured mass-interval width.

[Saved Notebook 6 run output](supplied_nb06_run.md) preserves the supplied execution log. The same upload reports CPU execution (`CpuDevice(id=0)`), so this run is not a GPU benchmark. No paired information-weight comparison is shown in that saved log; it cannot establish an advantage over the no-information baseline by itself.

Current scope excludes hardware validation, planar pushing, sensor-noise-aware state estimation in Notebook 6, and an integrated friction-learning contact planner.
