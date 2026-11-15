# LAAD-PIA-VFL implementation map

The executable source of truth is `../examples/LAAD_PIA_VFL_full_experiments.ipynb`.
The notebook currently contains the integrated end-to-end implementation; this
repository does not fabricate separate Python modules that are not present in
the submitted implementation.

| Reference-style area | Research implementation component |
|---|---|
| `configs/` | experiment configuration and controller parameters |
| `datasets/` | six VFL benchmark dataset loaders/preflight and task-property definitions |
| `evaluation_metrics/` | primary-task utility, PIA attack, calibration and prevalence metrics |
| `loss/` | primary-task optimization and representation perturbation logic |
| `models/` | two-party VFL models and attack/probe models |
| `utils/` | leakage monitoring, risk estimation, hysteresis control, logging and plotting |

Use the notebook for execution and reproducibility. The directories below
contain focused documentation for navigation; they do not claim to be
independently importable source modules.
