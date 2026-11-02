# ML Techniques

This repository contains five reproducible machine-learning case studies. Each notebook keeps the algorithm and visual diagnostics visible so the workflow can be followed from data loading through evaluation.

- `notebooks/01_house_rent_regression.ipynb` — an interpretable OLS and Ridge baseline for monthly house-rent prediction.
- `notebooks/02_phishing_url_classification.ipynb` — Logistic Regression for phishing URL classification with registered-domain group validation.
- `notebooks/03_insurance_fraud_decision_tree.ipynb` — an interpretable CART Decision Tree for vehicle insurance claim fraud detection.
- `notebooks/04_water_potability_knn.ipynb` — K-Nearest Neighbors classification for water potability.
- `notebooks/05_sleep_health_svm.ipynb` — an RBF-kernel Support Vector Machine for sleep-disorder classification.

## Reproducibility

The datasets are not committed to this repository. This keeps the repository lightweight and avoids redistributing downloaded copies. Follow each notebook's loading instructions, record the exact dataset version and access date in an academic report, and run all cells from a clean Python 3 or Google Colab session.

The rent notebook expects `House_Rent_Dataset.csv` beside the notebook, in `data/`, or in `/content/`. The source is the [House Rent Prediction Dataset on Kaggle](https://www.kaggle.com/datasets/iamsouravbanerjee/house-rent-prediction-dataset).

The phishing notebook expects the UCI `PhiUSIIL_Phishing_URL_Dataset.csv` and uses a clearly labeled synthetic fallback only to demonstrate the workflow when the file is unavailable. In the UCI convention, `label = 1` is legitimate and `label = 0` is phishing; verify the target mapping used by the local file before interpreting results.

The insurance, water-potability, and sleep-health notebooks check Google Drive and document fallback sources or synthetic demonstration data where applicable. Metrics from synthetic fallback data are illustrative and must not be presented as results on the real datasets.

## Evaluation scope and limitations

The notebooks are educational baselines, not production systems. They use train/test splits and model-specific diagnostics, but some choices remain intentionally simple:

- The rent notebook reports both log-scale and original-rent metrics and documents its feature and dataset limitations.
- The phishing notebook uses domain-group validation to reduce URL-family leakage, but this does not prove zero-day or production performance.
- The insurance notebook uses class weighting and a shallow tree; stricter leakage-safe preprocessing and time-aware validation would strengthen a future study.
- The KNN notebook correctly places imputation and scaling in a pipeline, but its exploratory selection of `k` from test accuracy should be replaced by training-fold cross-validation for an unbiased final estimate.
- The SVM notebook uses standardized features and a fixed RBF baseline; tuning and repeated validation would be needed for stronger conclusions.

Results should always be interpreted alongside the dataset source, sampling limitations, feature-selection decisions, and the assumptions documented in the relevant notebook.
