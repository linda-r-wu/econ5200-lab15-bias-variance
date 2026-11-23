[README.md](https://github.com/user-attachments/files/35303891/README.md)
# Bias, Variance and an Unbiased Cross-Validation Score

## Objective

I studied how model selection affects reported prediction error and how cross-validation can give a fairer estimate of performance on new data.

## Methodology

- Compared polynomials of degree 1 to 12 using cross-validation on 80 simulated points.
- Tested the selected model on 20,000 new points.
- Used nested cross-validation to evaluate the whole model-selection process.
- Separated expected prediction error into bias squared, variance and noise through simulation.
- Wrote a k-fold cross-validation function for scikit-learn models and checked it with different folds, models and column names.

## Key Findings

I selected degree **5**, which had a CV error of **0.1853**, but its error on new data was **0.2330**. Picking the lowest CV score made its performance look better than it was.

Nested cross-validation estimated **0.1910**. It separated model selection from evaluation, but it still underestimated the new-data error in this sample. The noise alone contributed **0.2025** to expected error.

My cross-validation function passed all checks. For degree 5, it returned **0.1853 with 5 folds** and **0.1921 with 10 folds**.
