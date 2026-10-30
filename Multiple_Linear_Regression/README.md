# Multiple Linear Regression

Predicts house price using multiple features from the housing dataset. The notebook compares OLS, Ridge, Lasso, and Elastic Net regression.

## Objective

Model the relationship between house price and multiple predictors, examine the statistical significance of OLS coefficients, and compare regularized regression models.

## Approach

1. Load the housing dataset and separate the predictors from the target `price_usd_k`.
2. Split the data into 80% training and 20% testing sets.
3. Standardize the predictor features for the regularized models. The scaler is fitted on the training data and applied to the test data.
4. Fit an OLS multiple regression model using the original, unscaled features.
5. Perform hypothesis tests on the OLS regression coefficients and review the overall model test.
6. Fit Ridge, Lasso, and Elastic Net models using cross-validation to select their regularization parameters.
7. Evaluate each model on the same test set using R² and RMSE.
8. Compare the coefficients from OLS, Ridge, Lasso, and Elastic Net in a single table.

## Models

- **OLS:** Estimates regression coefficients without regularization and provides coefficient significance tests.
- **Ridge:** Uses L2 regularization to shrink coefficients toward zero.
- **Lasso:** Uses L1 regularization and can set some coefficients to zero.
- **Elastic Net:** Combines L1 and L2 regularization.

## Results

The notebook displays the test-set R² and RMSE for each model in a performance comparison table. It also displays the coefficients side by side.

- In the OLS model, `square_feet`, `bedrooms`, `bathrooms`, and `age_years` are statistically significant at the 5% significance level.
- The overall OLS model is statistically significant, with R² = 0.956 on the training data.
- Ridge, Lasso, and Elastic Net regularize the coefficients; Lasso can exclude features by assigning their coefficients a value of zero.
- Compare test-set R² and RMSE to determine which model performs best on unseen data. The coefficient table alone does not identify the best predictive model.

**Note:** OLS uses original, unscaled features, while the regularized models use standardized features. Therefore, coefficient magnitudes should not be compared directly across these models without considering the feature scales.

## Files

- `multiple_linear_regression.ipynb`: notebook with OLS, regularized models, hypothesis testing, coefficient comparison, and model evaluation.
- `regression_housing_dataset.csv`: dataset used by the notebook.
