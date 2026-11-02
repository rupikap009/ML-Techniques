# ML Techniques

Practical, reproducible machine-learning case studies implemented in Jupyter notebooks. Each notebook focuses on one algorithm, explains the modeling decisions, and includes evaluation metrics and visual diagnostics.

> **Learning project:** These notebooks are educational baselines, not production systems or professional advice.

## Notebook guide

| Notebook | Technique | Prediction task |
| --- | --- | --- |
| [01 · House Rent Regression](notebooks/01_house_rent_regression.ipynb) | OLS and Ridge Regression | Predict monthly house rent |
| [02 · Phishing URL Classification](notebooks/02_phishing_url_classification.ipynb) | Logistic Regression | Classify URLs as legitimate or phishing |
| [03 · Insurance Fraud Detection](notebooks/03_insurance_fraud_decision_tree.ipynb) | CART Decision Tree | Identify potentially fraudulent claims |
| [04 · Water Potability](notebooks/04_water_potability_knn.ipynb) | K-Nearest Neighbors | Classify water as potable or non-potable |
| [05 · Sleep Health Classification](notebooks/05_sleep_health_svm.ipynb) | RBF-kernel Support Vector Machine | Predict sleep-disorder categories |

## What each notebook demonstrates

### 01 · House rent regression

An interpretable linear baseline for monthly rent prediction, with one-hot encoding, log-target modeling, Ridge regularization, cross-validation, and metrics reported on both log and original-rent scales.

### 02 · Phishing URL classification

An interpretable Logistic Regression workflow using URL features and registered-domain group validation. Group-based splitting helps prevent closely related URLs from appearing in both the training and test sets.

### 03 · Insurance fraud detection

An intentionally shallow CART Decision Tree for vehicle-insurance claim fraud. Class weighting, classification metrics, a confusion matrix, and the learned tree make the baseline easy to inspect.

### 04 · Water potability

A KNN workflow that demonstrates why missing-value imputation and feature scaling must be fitted on training data before distance-based modeling. The notebook also visualizes the effect of different values of `k`.

### 05 · Sleep health classification

An RBF-kernel SVM for multiclass sleep-disorder classification. The workflow includes standardized features, a stratified split, per-class metrics, and visual diagnostics.

## Running the notebooks

### Option 1: Google Colab

Open any notebook and select **Open in Colab**, or use the notebook links above after opening the file on GitHub.

### Option 2: Local Jupyter

```bash
git clone https://github.com/rupikap009/ML-Techniques.git
cd ML-Techniques
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install jupyter numpy pandas scikit-learn matplotlib seaborn
jupyter notebook
```

Open the notebook you want to run and execute the cells from top to bottom. A clean Python 3 environment or Google Colab runtime is recommended.

## Datasets and reproducibility

Datasets are intentionally not committed to this repository. This keeps the project lightweight and avoids redistributing downloaded copies. Each notebook documents its source and loading logic.

| Notebook | Dataset source |
| --- | --- |
| House rent | [House Rent Prediction Dataset](https://www.kaggle.com/datasets/iamsouravbanerjee/house-rent-prediction-dataset) |
| Phishing URLs | [UCI PhiUSIIL Phishing URL Dataset](https://archive.ics.uci.edu/dataset/967/phiusiil+phishing+url+dataset) |
| Insurance fraud | [Vehicle Insurance Claim Fraud Detection Dataset](https://www.kaggle.com/datasets/gunavathibaskaran/fraud-insurance-analysis) |
| Water potability | [Water Potability Dataset](https://www.kaggle.com/datasets/adityakadiwal/water-potability) |
| Sleep health | [Sleep Health and Lifestyle Dataset](https://www.kaggle.com/datasets/uom190346a/sleep-health-and-lifestyle-dataset) |

When reporting results, record the dataset version, access date, preprocessing choices, and whether the notebook used the original dataset or its clearly labeled synthetic demonstration fallback.

## Evaluation notes and limitations

- Results from synthetic fallback data are illustrative only and must not be reported as results on the real datasets.
- The phishing notebook uses domain-group validation, but this does not guarantee zero-day or production performance.
- The insurance notebook is an educational shallow-tree baseline; stricter leakage-safe preprocessing and time-aware validation would strengthen the study.
- The water-potability notebook currently uses the held-out test partition when exploring `k`; training-fold cross-validation should be used for an unbiased final estimate.
- The sleep-health notebook uses fixed RBF SVM settings; tuning and repeated validation would be needed for stronger conclusions.
- All results depend on the source data, sampling process, feature choices, and assumptions documented in the relevant notebook.

## Repository structure

```text
ML-Techniques/
├── README.md
└── notebooks/
    ├── 01_house_rent_regression.ipynb
    ├── 02_phishing_url_classification.ipynb
    ├── 03_insurance_fraud_decision_tree.ipynb
    ├── 04_water_potability_knn.ipynb
    └── 05_sleep_health_svm.ipynb
```

## License

No license has been specified yet. Dataset licenses and terms remain the responsibility of the respective dataset providers.
