# Reproducibility notes

## Configuration recorded with the supplied run

The `results/config_record.json` file records the configuration snapshot associated with the supplied result archive. The main settings include:

| Setting | Value |
|---|---:|
| Datasets | Adult, Bank, Census, Health, Lawschool, CelebA |
| Random seeds | 0–9 (10 seeds) |
| Epochs | 30 |
| Train / simulated attacker / reference / test split | 60% / 10% / 10% / 20% |
| Clipping norm | 1.0 |
| Gaussian noise range | 0.0–0.30 |
| Fixed noise strengths | 0.05, 0.10, 0.20, 0.30 |
| Calibration strengths | 0.00, 0.05, 0.10, 0.20, 0.30 |
| Leakage budget | 0.30 |
| Hysteresis half-width | 0.05 |
| Proportional gain | 0.15 |
| EMA smoothing | 0.70 |
| Initial noise strength | 0.05 |
| Auxiliary prevalence shifts | 0.0, 0.3, 0.6 |
| Monitor weights (JSD / Wasserstein / SMD / probe) | 0.35 / 0.25 / 0.15 / 0.25 |

The notebook itself is authoritative if a README value and notebook setting ever differ.

## Run environment

The supplied result manifest records a CUDA-enabled PyTorch environment. For a fresh run, use a Kaggle GPU runtime and install/check the packages listed in `requirements.txt`. The notebook prints the actual runtime versions and device.

## Run procedure

1. Attach all six datasets.
2. Run the notebook from the first cell through the final packaging cell.
3. Check the preflight output before training.
4. Preserve the run tag when resuming the same experiment. Change `RUN_TAG` when intentionally starting a new independent run.
5. Do not use test data for tuning. The notebook's tuning cell is explicitly validation-only.
6. Run optional reviewer add-ons only after the main driver has produced the required artifacts.
7. Review the final audit checklist in the notebook before making paper claims.

## Interpretation cautions

- Sample-level attack AUC and population-level prevalence-estimation metrics are different objectives and must be reported separately.
- Read prior-relative gain together with prevalence MAE and the auxiliary-prior baseline.
- A risk budget is a controller target, not a formal guarantee.
- Reviewer baseline proxies are explicitly identified in the notebook and should not be described as faithful reproductions of named methods unless the exact method/protocol has been independently verified.
- The result archive does not include the raw datasets or model checkpoints. A fresh run is required to regenerate model states.
