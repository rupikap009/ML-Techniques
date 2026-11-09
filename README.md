# ML Techniques

An educational machine-learning project containing five Jupyter notebooks. Each notebook studies one dataset and one main algorithm from data cleaning through model evaluation.

> **Important:** These are learning-focused baselines, not production systems. Reported results depend on the downloaded dataset, preprocessing decisions, feature selection, and train/test split.

## Project overview

| Notebook | Algorithm | Task |
| --- | --- | --- |
| [01 · House Rent Regression](notebooks/01_house_rent_regression.ipynb) | Linear and Ridge Regression | Predict monthly house rent |
| [02 · Phishing URL Classification](notebooks/02_phishing_url_classification.ipynb) | Logistic Regression | Classify URLs as legitimate or phishing |
| [03 · Insurance Fraud Detection](notebooks/03_insurance_fraud_decision_tree.ipynb) | Entropy-based Decision Tree | Identify potentially fraudulent claims |
| [04 · Water Potability](notebooks/04_water_potability_knn.ipynb) | K-Nearest Neighbors | Classify water as potable or non-potable |
| [05 · Sleep Health Classification](notebooks/05_sleep_health_svm.ipynb) | RBF-kernel SVM | Predict sleep-disorder categories |

## What is inside each notebook?

The notebooks follow a common student-friendly structure:

1. Research question and simple algorithm definitions
2. Dataset source, purpose, and column descriptions
3. Data cleaning and preprocessing
4. Exploratory data analysis and visualizations
5. Feature selection and justification
6. Model training, splitting strategy, and evaluation
7. Confusion-matrix or regression metrics
8. Model-specific visual diagnostics
9. **Compare**
10. **Summarize**
11. **Conclude**, including limitations and possible improvements

Each major stage includes numbered `INSIGHT` explanations describing what the output means and why the next decision was made.

## Notebook highlights

### House rent regression

Uses linear and Ridge regression with categorical encoding, log-target modeling, cross-validation, residual diagnostics, actual-versus-predicted plots, and regression metrics such as MAE, RMSE, and \(R^2\). A clearly labeled high-rent threshold analysis is included only as an auxiliary confusion-matrix example; rent prediction itself is a regression problem.

### Phishing URL classification

Uses numeric URL and domain features with Logistic Regression. The `Domain` column is used as a grouping key rather than as a predictor, preventing URLs from the same domain from appearing in both partitions. The notebook includes:

- proxy-feature auditing;
- grouped five-fold cross-validation;
- unseen-domain testing;
- 15%, 20%, 25%, and 30% grouped test-size comparisons;
- five random seeds for each test size;
- sigmoid, probability, ROC, precision-recall, confusion-matrix, coefficient, and split-sensitivity plots.

### Insurance fraud detection

Uses an intentionally shallow entropy-based Decision Tree. The notebook explains entropy and information gain, uses class balancing, and visualizes the confusion matrix, ROC curve, feature importance, and learned tree.

### Water potability

Uses Euclidean-distance KNN with median imputation, standardization, uniform voting, and training-only cross-validation to choose `k`. The notebook demonstrates why scaling is essential for a distance-based algorithm and includes KNN performance visualizations.

### Sleep health classification

Uses an RBF-kernel SVM for multiclass sleep-disorder prediction. The notebook explains margins, support vectors, kernels, `C`, and `gamma`, and includes per-class metrics, multiclass ROC analysis, support-vector diagnostics, and split-sensitivity analysis.

## Running the notebooks

### Google Colab

Open a notebook on GitHub and select **Open in Colab**, or open the notebook link directly in Colab.

### Local Jupyter

```bash
git clone https://github.com/rupikap009/ML-Techniques.git
cd ML-Techniques
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
python -m pip install --upgrade pip
pip install jupyter numpy pandas scikit-learn matplotlib seaborn scipy
jupyter notebook
```

Open a notebook and run its cells from top to bottom. Python 3.10+ and a clean virtual environment are recommended.

## Datasets

Dataset files are intentionally not committed. Download the source dataset and place the required file where the notebook's loading cell expects it. Each notebook documents its filename, source, schema, and fallback behavior.

| Notebook | Dataset source |
| --- | --- |
| House rent | [House Rent Prediction Dataset](https://www.kaggle.com/datasets/iamsouravbanerjee/house-rent-prediction-dataset) |
| Phishing URLs | [UCI PhiUSIIL Phishing URL Dataset](https://archive.ics.uci.edu/dataset/967/phiusiil+phishing+url+dataset) |
| Insurance fraud | [Vehicle Insurance Claim Fraud Detection Dataset](https://www.kaggle.com/datasets/gunavathibaskaran/fraud-insurance-analysis) |
| Water potability | [Water Potability Dataset](https://www.kaggle.com/datasets/adityakadiwal/water-potability) |
| Sleep health | [Sleep Health and Lifestyle Dataset](https://www.kaggle.com/datasets/uom190346a/sleep-health-and-lifestyle-dataset) |

For reproducible reporting, record the dataset version, download date, source, preprocessing choices, selected features, split settings, and whether the original data or a clearly labeled demonstration fallback was used.

## How to interpret the results

- **Classification:** accuracy, balanced accuracy, precision, recall/sensitivity, specificity, F1, ROC-AUC, PR-AUC, and the confusion matrix are used where appropriate.
- **Regression:** MAE, MSE, RMSE, \(R^2\), residual plots, and actual-versus-predicted plots are used.
- **Generalization:** training scores are compared with held-out scores and cross-validation results. A score above 90% is not automatically overfitting; the train/test gap, validation design, leakage checks, and split stability matter.
- **Data leakage:** preprocessing statistics are fitted within training data or pipelines. The phishing notebook additionally checks that grouped domains do not overlap.
- **Visualizations:** plots are included to explain distributions, relationships, model behavior, errors, and validation stability—not simply to repeat the same metric.

## Limitations

- Dataset results may not represent real-world performance or future data.
- The phishing grouped split is stronger than a random row split, but it is not temporal validation and does not guarantee zero-day performance.
- The insurance, water, and sleep notebooks are educational baselines; deployment would require broader validation, monitoring, and domain expertise.
- Dataset sampling, class definitions, missing-value assumptions, feature choices, and threshold choices affect the results.
- Synthetic or demonstration fallback data must not be presented as performance on the original dataset.

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

No repository license has been specified. Dataset licenses and usage terms remain the responsibility of the respective dataset providers.
