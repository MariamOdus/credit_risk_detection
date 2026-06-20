## Project overview

This repository contains work for the Advanced Programming - Data Visualisation assessment. The main focus is exploratory data analysis and modelling on a credit risk dataset, with results and visualisations captured in Jupyter notebooks.

Contents
- `ml.ipynb` — primary notebook (root)
- `data/credit_risk_dataset.csv` — dataset used throughout the notebooks

## Dataset

The dataset `data/credit_risk_dataset.csv` contains borrower information and labels indicating credit risk. The notebooks load this CSV and perform cleaning, exploratory visualisations, feature engineering, and modelling experiments.

Key dataset notes:
- Typical columns: demographic features, financial features, and a target risk label.
- Missing values and categorical encodings are handled inside the notebooks before modelling.

## Notebooks and what they contain

- `ml.ipynb` (root): The main assignment notebook. Includes data loading, cleaning, EDA, feature engineering, model training (classification), evaluation (confusion matrix, ROC/AUC), and interpretable visualisations.

- `misc/submission/assessment.ipynb` and its `data/` copy: packaged submission copy of the main assessment.

## Main steps performed (high level)

1. Data loading and validation — verify schema, types, and missingness.
2. Data cleaning — handle missing values, outliers, and inconsistent categories.
3. Exploratory data analysis — distribution plots, correlation heatmaps, and insights into predictive features.
4. Feature engineering — encoding categorical variables, scaling numeric features, and creating interaction features where helpful.
5. Modelling experiments — baseline classifiers (e.g., logistic regression), tree-based models, evaluation, and comparison.
6. Visualisation & interpretation — performance plots, feature importances, and diagnostic visuals.

## Key findings (summary)

- Predictive performance varies with feature selection and preprocessing; tree-based models often capture nonlinearities better for this dataset.
- Several demographic and financial variables show strong correlation with the risk target; these are highlighted in the `assessment.ipynb` EDA section.

For detailed figures and quantitative results, open `assessment.ipynb` and run the evaluation cells.

## How to run this project locally

Prerequisites:
- Python 3.8+ recommended

Install required packages (run in your project root):

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyterlab notebook
```

Open the main notebook:

```bash
# start Jupyter in the repo root
jupyter lab
# or
jupyter notebook
```

Then open `ml.ipynb` in the browser and run cells sequentially. If you prefer a headless run (to re-run all cells and export results):

```bash
pip install nbconvert
jupyter nbconvert --to html --execute assessment.ipynb --output assessment_executed.html
```

Notes:
- If you create a `requirements.txt`, use `pip install -r requirements.txt`.
- Some notebooks may assume inline plotting; ensure your environment supports notebook rendering.

## Reproducibility

- Random seeds: where randomness is used (model training, cross-validation), seeds are set inside the notebooks for reproducible results.
- Data snapshot: the repository includes the CSV under `data/` to ensure reproducible runs.

## Suggestions for improvement and next steps

- Add a `requirements.txt` or `environment.yml` to pin exact package versions.
- Convert key analysis sections into Python scripts for automated testing and CI.
- Add unit tests around data preprocessing steps to catch schema drift.
- Explore additional models (ensemble stacking, XGBoost/LightGBM) and hyperparameter tuning with `GridSearchCV` or `Optuna`.

## License & contact

This repository is for coursework. If you want to reuse any part of the code, please contact the author for permission and attribution.

If you want me to update the README with more details (figures, explicit model metrics, or a `requirements.txt`), tell me which parts to expand.
