# Credit Card Fraud Detection with Machine Learning

A Jupyter notebook that explores a credit card transaction dataset, engineers features, and compares classification models for fraud detection. The workflow includes exploratory plots, preprocessing, model evaluation, and a comparison of fraud-class F1 score and ROC AUC.

## Models in the notebook

- Logistic Regression with feature scaling and class weighting
- SGD Classifier with feature scaling and class weighting
- XGBoost
- LightGBM
- An optional Linear Regression baseline, included for comparison

The notebook reports accuracy, precision, recall, F1 score, ROC AUC where available, confusion matrices, ROC curves, and training time. For this imbalanced classification task, review fraud-class precision and recall alongside F1 and ROC AUC; accuracy alone can be misleading.

## Project files

```text
.
├── Credit_Card_Fraud_Detection.ipynb
├── Datasets/
│   ├── fraudTrain.csv   # provide locally; not included in this repository
│   └── fraudTest.csv    # provide locally; not included in this repository
├── requirements.txt
└── .gitignore
```

## Dataset setup

The notebook reads these relative paths:

```text
Datasets/fraudTrain.csv
Datasets/fraudTest.csv
```

If you already have `Datasets/fraudTrain.csv` and `Datasets/fraudTest.csv` beside the notebook, no additional data setup is needed. Otherwise, create a `Datasets` folder beside the notebook and place the two CSV files there. The CSVs are intentionally excluded from Git by `.gitignore`; keep them local and add them only to sources where you are authorized to store them. The notebook does not download the data automatically.

## Run in VS Code

1. Open this folder in VS Code.
2. Install the **Python** and **Jupyter** extensions if prompted.
3. Create and activate a virtual environment in the integrated terminal:

   **Windows PowerShell**
   ```powershell
   py -m venv .venv
   .\.venv\Scripts\Activate.ps1
   python -m pip install -r requirements.txt
   ```

   **macOS/Linux**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   python -m pip install -r requirements.txt
   ```

4. Open `Credit_Card_Fraud_Detection.ipynb`, choose the `.venv` Python kernel, and run the cells from top to bottom.

Model training can take time and uses CPU resources. Runtime depends on the machine and the size of the CSV files.

## Notes

- The notebook expects the CSV columns used by the feature engineering and target steps, including `is_fraud`, transaction timestamps, cardholder fields, location fields, and transaction `category`.
- The train and test files are loaded separately. The notebook aligns the test feature columns to the training columns after one-hot encoding.
- The notebook's saved cell outputs have been cleared in this repository copy. Run the notebook to regenerate charts and metrics for your local data.
