# Housing Price Regression Project

This project explores house-price prediction using two regression approaches: Simple Linear Regression and Multiple Linear Regression. Both notebooks use the same housing dataset.

## Project Structure

```text
Housing-Price-Regression/
├── Simple Linear Regression/
│   └── simple_linear_regression.ipynb
├── Multiple Linear Regression/
│   └── multiple_linear_regression.ipynb
├── regression_housing_dataset.csv
├── requirements.txt
└── README.md
```

> Keep `regression_housing_dataset.csv` in the project root, alongside the two folders, so the notebooks can load it using `pd.read_csv('regression_housing_dataset.csv')`.

## Project Objectives

- Explore the relationship between house prices and housing features.
- Build and evaluate a Simple Linear Regression model using one predictor.
- Build and compare Multiple Linear Regression models using multiple predictors.
- Evaluate predictive performance using R² and RMSE; the Simple Linear Regression notebook also reports MAE.
- Examine OLS coefficients and statistical significance.

## Notebooks

### 1. Simple Linear Regression

Uses `square_feet` to predict `price_usd_k`.

- Visualizes the relationship using a scatter plot.
- Fits OLS with `statsmodels` to inspect coefficients, p-values, and R².
- Splits data into training and testing sets (80/20, `random_state=20`).
- Trains a `scikit-learn` Linear Regression model.
- Evaluates train and test performance using R², RMSE, and MAE.
- Includes a fitted regression line, predictions, and residual analysis.

### 2. Multiple Linear Regression

Uses multiple dataset features to predict `price_usd_k`.

- Splits data into training and testing sets (80/20, `random_state=20`).
- Fits an OLS model using `statsmodels` and reviews coefficient hypothesis tests.
- Standardizes features for regularized models.
- Fits and compares Ridge, Lasso, and Elastic Net, with cross-validation to select regularization parameters.
- Evaluates models using test-set R² and RMSE.
- Compares coefficients across OLS, Ridge, Lasso, and Elastic Net.

## Dataset

- **File:** `regression_housing_dataset.csv`
- **Target:** `price_usd_k` (house price in thousands of USD)
- **Simple Linear Regression predictor:** `square_feet`
- **Multiple Linear Regression predictors:** all other columns in the dataset

## Requirements

Python 3.9+ recommended.

Install the required packages:

```bash
pip install -r requirements.txt
```

Required libraries:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `statsmodels`
- `scikit-learn`

## How to Run

1. Download or clone the project.
2. Ensure the dataset and notebook folders follow the project structure above.
3. Install the dependencies.
4. Open either notebook in Jupyter Notebook, JupyterLab, or VS Code.
5. Run the notebook cells from top to bottom.

## Notes

- The notebooks use the relative dataset path `regression_housing_dataset.csv`; run them from the project root or adjust the path if needed.
- The multiple regression notebook uses original-scale features for OLS and standardized features for regularized models. Coefficient magnitudes should therefore be interpreted with feature scaling in mind.
- Results describe the dataset and train/test split used in the notebooks; they are not guarantees for new data.
