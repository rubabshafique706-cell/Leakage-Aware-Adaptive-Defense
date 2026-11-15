# Leakage-Aware Adaptive Defense Against Property Inference in VFL (LAAD-PIA-VFL)

This repository contains the author's VFL property-inference defense
implementation, research paper, and experiment output. All research methods and artifacts here
belong to the LAAD-PIA-VFL project.

## Repository structure

```text
LAAD-PIA-VFL/
├── README.md
├── requirements.txt
├── assets/
├── datasets/
├── docs/
│   ├── paper/
│   └── REPRODUCIBILITY.md
├── evaluation_metrics/
├── examples/
│   ├── README.md
│   └── LAAD_PIA_VFL_full_experiments.ipynb
├── files/
├── idm/
│   ├── configs/
│   ├── datasets/
│   ├── evaluation_metrics/
│   ├── loss/
│   ├── models/
│   └── utils/
├── loss/
├── models/
├── results/
│   ├── figures/
│   ├── latex/
│   ├── logs/
│   ├── risk/
│   └── tables/
├── tests/
└── utils/
```

The executable implementation supplied by the author is a complete notebook.
The reference repository is organized as a multi-module Python project; this
project's notebook-contained components are documented in the corresponding
reference-style directories rather than being falsely represented as
separate importable modules. See `idm/README.md` for the component map.

## Research method

The project studies property inference attacks in vertical federated learning
and proposes a leakage-aware adaptive defense. Its integrated workflow
measures leakage using Jensen–Shannon divergence, Wasserstein distance,
standardized mean difference, and a probe-based signal; maps the composite
score to attack risk with an isotonic estimator; and adjusts representation
perturbation using a hysteresis-based feedback controller.

## Experiments and outputs

The supplied experiments cover Adult, Bank Marketing, Census-Income KDD,
Health, Lawschool, and CelebA, with 10 random seeds. Existing outputs are
preserved under `results/` (tables, logs, risk records, figures and LaTeX
tables). The research paper is in `docs/paper/`.

Raw datasets and model checkpoints are not included. See `docs/REPRODUCIBILITY.md`
and the notebook's preflight section for setup and execution. The included
results are the supplied run artifacts; they are not automatically regenerated
by extracting this repository.

## Important scientific scope

The notebook documents the implemented baselines and reviewer audits.
Proxy baselines are not claimed to be faithful reproductions of named
state-of-the-art methods, and the perturbation mechanism is not claimed to
provide a formal differential-privacy guarantee.
