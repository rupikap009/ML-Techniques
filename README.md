# ML Techniques

This repository contains two reproducible machine-learning case studies:

- `notebooks/01_house_rent_regression.ipynb` — an interpretable house-rent regression baseline.
- `notebooks/02_phishing_url_classification.ipynb.ipynb` — a phishing URL classifier evaluated on unseen domains.

## Reproducibility

The datasets are not committed to this repository. Follow the loading instructions at the start of each notebook, record the exact dataset version and access date in an academic report, and run all cells from a clean Python 3 or Google Colab session.

The rent notebook expects `House_Rent_Dataset.csv` beside the notebook, in `data/`, or in `/content/`. The referenced source is [House Rent Prediction Dataset on Kaggle](https://www.kaggle.com/datasets/iamsouravbanerjee/house-rent-prediction-dataset); cite its author, version, and access date.

The phishing notebook downloads or accepts `PhiUSIIL_Phishing_URL_Dataset.csv` from the [UCI PhiUSIIL dataset page](https://archive.ics.uci.edu/dataset/967/phiusiil+phishing+url+dataset). In the UCI convention, `label = 1` is legitimate and `label = 0` is phishing; the notebook explicitly converts this to `is_phishing` so that `1` consistently means phishing during evaluation.

## Evaluation scope

Both notebooks compare against a simple baseline and use cross-validation. The phishing study uses grouped splits by domain and audits exact duplicates when a URL column is available. It does not claim temporal generalization when no reliable timestamp is present, and it documents the limitation that upstream feature construction cannot be independently reconstructed from the released CSV.

The reported models are academic baselines, not production systems. Results should be interpreted with the dataset limitations and feature-selection decisions documented in the notebooks.