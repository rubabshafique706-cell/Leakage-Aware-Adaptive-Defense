# Dataset preparation

The notebook expects one private Kaggle Dataset attached under `/kaggle/input`. It recursively discovers the supported files and stops during preflight if a required dataset is missing or malformed.

Expected logical layout:

```text
raad-datasets/
├── adult/
│   └── adult.csv
├── bank/
│   └── bank-full.csv
├── census/
│   ├── census-income.data
│   └── census-income.test
├── health/
│   └── diabetic_data.csv
├── lawschool/
│   └── bar_pass_prediction.csv
└── celeba/
    ├── img_align_celeba.zip
    └── list_attr_celeba.csv
```

Dataset roles and settings in the supplied notebook:
- Adult: task label `income`, target property `sex`.
- Bank Marketing: task label `y`, target property `marital`.
- Census-Income KDD: task label `income`, target property `sex`.
- Health / Diabetes 130-US Hospitals: task label `readmitted`, target property `age`.
- Lawschool: task label `pass_bar`, target property `male`.
- CelebA: task label `Smiling`, target property `Male`; image mode uses left/right face halves as the two parties.

The notebook's dataset specification and preflight cell are authoritative for exact filenames, column handling, filtering, and feature partitioning. Do not substitute similarly named files without checking those cells.

**Do not commit private datasets, CelebA images, credentials, or other restricted data to a public GitHub repository.** The repository `.gitignore` excludes common local data paths.
