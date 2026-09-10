# Credit Risk Modeling and Validation

This project compares Logistic Regression and XGBoost for probability of default (PD) estimation using LendingClub loan data. The accompanying Jupyter notebook covers data preparation, model estimation, out-of-sample validation and an illustrative lending-policy exercise based on predicted PDs.

## Notebook

`credit_risk_modeling_and_validation.ipynb`

The notebook contains:

- preparation of a reproducible 10,000-loan sample from loans issued in 2014,
- regularized and unregularized Logistic Regression benchmarks,
- XGBoost models with cross-validated boosting rounds,
- out-of-sample discrimination and calibration using ROC/AUC, Brier score and Expected Calibration Error (ECE),
- illustrative PD-threshold and acceptance-rate strategies,
- bad rate and expected loss calculations.

All outputs and figures are saved in the notebook, so the analysis can be reviewed without rerunning the code.

## Data

The analysis uses the Kaggle dataset **Lending Club 2007–2020Q3**:

https://www.kaggle.com/datasets/ethon0426/lending-club-20072020q1

The raw data are not included in this repository. To rerun the notebook, download `Loan_status_2007-2020Q3.gzip` and place it at:

```text
data/Loan_status_2007-2020Q3.gzip
```

Variable definitions are documented in `LCDataDictionary.xlsx`, which is included in the same Kaggle dataset.

## Requirements

Python 3.13.5 with `pandas`, `numpy`, `scikit-learn`, `xgboost` and `matplotlib`.

## Scope and limitations

Because final loan outcomes are used for both 36- and 60-month loans, the modeled target is not the one-year PD used in the Basel IRB framework. A one-year version would require redefining the target as default within 12 months after loan issuance.

**AI assistance:** AI tools were used for coding support, review and documentation. The project design, modeling choices and interpretation are my own.
