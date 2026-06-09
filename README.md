# Simple Linear Regression - Marketing ROI Analysis

Overview
This project analyzes a marketing dataset using Python and statsmodels to build a Simple Linear Regression model. The goal is to determine which marketing channel (TV, Radio, or Social Media) has the strongest impact on Sales and to produce clear, ROI-based recommendations for marketing budget allocation.

Dataset
- File: marketing_and_sales_data_evaluate_lr.csv
- Columns:
  - TV: TV advertising spend (units)
  - Radio: Radio advertising spend (units)
  - Social_Media: Social Media advertising spend (units)
  - Sales: Product sales revenue (units)

Quick summary of results (from regression_analysis.ipynb)
- Sample size after cleaning: n = 16 (one row with missing TV removed)
- Regression equation: Sales = 21.4931 + 8.5564 * Radio
- R-squared: 0.8951 (89.51%)
- Adjusted R-squared: 0.8871
- F-statistic: 119.7995 (Prob (F-statistic) ≈ 1.13e-08)
- Radio coefficient (slope): 8.5564
  - Std. error: 0.7811
  - t-statistic: 10.9547
  - p-value: 2.75e-08
  - 95% CI: [6.8804, 10.2324]
- Assumption tests:
  - Shapiro–Wilk (residual normality) p-value: 0.921176 → pass
  - Breusch–Pagan (heteroscedasticity) p-value: 0.687621 → pass
  - Durbin–Watson (independence) statistic: 1.937429 → no concerning autocorrelation

Interpretation (business-friendly)
- For every 1 unit increase in Radio spend, Sales increase by ≈ 8.5564 units (statistically significant, p << 0.05).
- The model explains ~89.5% of the variability in Sales — an excellent fit for a single predictor model.
- Diagnostic tests and plots (Residuals vs Fitted, Q-Q, Scale-Location) do not indicate major violations of OLS assumptions on this dataset.

ROI note (as implemented in notebook)
- If you interpret 1 unit spent → 8.5564 units revenue, net return (simplified) = 8.5564 - 1 = 7.5564 units per unit spent → ~755.64% (this is a simplified metric; use business margins and costs for a real ROI calculation).

Project structure

```
marketing-regression-analysis/
├── README.md
├── requirements.txt
├── regression_analysis.ipynb          # Main Jupyter Notebook (cleaned & contains results)
├── marketing_and_sales_data_evaluate_lr.csv  # Dataset
└── diagnostic_plots/                  # Optional: generated plots (if executed)
    ├── correlation_heatmap.png
    ├── distribution_plots.png
    ├── bivariate_analysis.png
    ├── diagnostic_plots.png
    └── regression_line_plot.png
```

How to reproduce (steps)
1. Clone repo:
   git clone https://github.com/Insikai/marketing-regression-analysis.git
   cd marketing-regression-analysis
2. Install dependencies:
   pip install -r requirements.txt
   (or pip install pandas numpy matplotlib seaborn statsmodels scipy scikit-learn)
3. Execute the notebook so all outputs and plots are embedded:
   Option A — interactive:
     jupyter lab
     Open regression_analysis.ipynb → Kernel → Restart & Run All → Save
   Option B — headless:
     jupyter nbconvert --to notebook --execute --inplace regression_analysis.ipynb --ExecutePreprocessor.timeout=600
4. Confirm that plots render, then commit any additional files (e.g., diagnostic_plots images) if needed.

Notes & limitations
- Small sample size (n = 16) — interpret results with caution and prefer validating with more data.
- The ROI calculation shown in the notebook is simplified; for business decisions include profit margins and costs.
- Correlation does not imply causation — consider A/B tests or controlled experiments to validate causal impact.

What I fixed / why
- The notebook file regression_analysis.ipynb previously had invalid JSON / control-character metadata that prevented Jupyter/GitHub from opening it. I repaired the JSON so the notebook opens. The notebook already contains executed outputs and the numeric results listed above.

Next actions I can take for you
- Re-run the notebook headlessly, save the generated PNG diagnostic plots into diagnostic_plots/, and push them to the repo.
- Produce a one-page PDF report (including plots) for submission.

If you want me to proceed with re-running the notebook and pushing plots (or producing a PDF), confirm which action(s) you want and I’ll perform them.