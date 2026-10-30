# Simple Linear Regression

Predicts house price from a single feature, `square_feet`.

## Objective

Model the relationship `price = β0 + β1 × square_feet` and evaluate how well one feature predicts price.

## Approach

1. Load and check the housing dataset.
2. Select `square_feet` as the predictor and `price_usd_k` as the target.
3. Visualize the relationship with a scatter plot and calculate correlation.
4. Fit an OLS model with `statsmodels` to inspect coefficients, p-values, and R².
5. Perform a hypothesis test on the slope coefficient.
6. Split the data into 80% training and 20% testing sets.
7. Train a `scikit-learn` Linear Regression model and evaluate it using R², RMSE, and MAE.
8. Plot the fitted regression line, predict prices for new houses, and analyze residuals.

Standardization is not used because this model has one predictor and does not use regularization.

## Results

| Metric | Train | Test |
|---|---:|---:|
| R² | 0.4380 | 0.4374 |
| RMSE | 46.55 | 47.95 |
| MAE | 37.74 | 37.85 |

- Each extra square foot is associated with an increase of about 0.105k USD in predicted house price (p < 0.001).
- Square feet alone explains about 44% of the variation in house prices.
- Train and test scores are similar, indicating consistent performance across the split.

## Files

- `simple_linear_regression.ipynb`: notebook with code, visualizations, and analysis.
- `regression_housing_dataset.csv`: dataset used by the notebook.
