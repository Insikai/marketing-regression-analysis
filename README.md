# Simple Linear Regression - Marketing ROI Analysis

## Project Overview

This project analyzes a marketing dataset using Python and `statsmodels` to build a **Simple Linear Regression model**. The goal is to understand which marketing channel (TV, Radio, or Social Media) has the strongest impact on Sales and provide data-driven recommendations for budget allocation.

### Key Objectives

- ✅ Load and clean the marketing dataset
- ✅ Perform exploratory data analysis (EDA) with visualizations
- ✅ Identify the independent variable most correlated with Sales
- ✅ Build an OLS regression model using statsmodels
- ✅ Create diagnostic plots to validate regression assumptions
- ✅ Interpret R-squared, coefficients, and p-values
- ✅ Formulate ROI-based business recommendations

## Dataset

**File:** `marketing_and_sales_data_evaluate_lr.csv`

**Columns:**
- `TV`: TV advertising spend (in units)
- `Radio`: Radio advertising spend (in units)
- `Social_Media`: Social Media advertising spend (in units)
- `Sales`: Product sales revenue (in units)

**Focus Variable:** Radio (independent variable)

## Installation & Setup

### Prerequisites

- Python 3.7 or higher
- Jupyter Notebook or JupyterLab

### Install Required Packages

```bash
pip install pandas numpy matplotlib seaborn statsmodels scipy scikit-learn
```

Or install from the requirements file:

```bash
pip install -r requirements.txt
```

## Project Structure

```
marketing-regression-analysis/
├── README.md
├── requirements.txt
├── regression_analysis.ipynb          # Main Jupyter Notebook
├── marketing_and_sales_data_evaluate_lr.csv  # Dataset
└── diagnostic_plots/                  # Output directory (created during analysis)
    ├── correlation_heatmap.png
    ├── distribution_plots.png
    ├── residuals_vs_fitted.png
    ├── qq_plot.png
    └── scale_location_plot.png
```

## Running the Analysis

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Insikai/marketing-regression-analysis.git
   cd marketing-regression-analysis
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Open the Jupyter Notebook:**
   ```bash
   jupyter notebook regression_analysis.ipynb
   ```

4. **Run all cells** to execute the complete analysis

## Analysis Steps

### 1. Data Loading & Exploration
- Load the CSV file
- Display basic statistics
- Check for missing values
- Examine data types

### 2. Exploratory Data Analysis (EDA)
- Univariate analysis: Distribution of each variable
- Bivariate analysis: Correlation matrix
- Visualizations: Histograms, scatter plots, heatmaps

### 3. Variable Selection
- Calculate correlation coefficients
- Justify selection of Radio as the independent variable
- Discuss expected business impact

### 4. Model Building
- Prepare data (add constant for intercept)
- Fit OLS regression model
- Display model summary with statistics

### 5. Assumption Validation
- **Linearity:** Scatter plot with regression line
- **Normality:** Q-Q plot of residuals
- **Homoscedasticity:** Residuals vs. Fitted values plot
- **Independence:** Durbin-Watson test (if applicable)

### 6. Model Interpretation
- **R-squared:** Proportion of variance explained
- **Coefficients:** Slope and intercept interpretation
- **P-values:** Statistical significance testing
- **Confidence Intervals:** Range of coefficient estimates

### 7. Business Recommendations
- ROI calculation based on model results
- Budget allocation strategy
- Risk considerations and limitations

## Key Outputs

### Model Summary Statistics
```
                            OLS Regression Results                            
==============================================================================
Dep. Variable:                  Sales   R-squared:                       0.XXX
Model:                            OLS   Adj. R-squared:                  0.XXX
Method:                 Least Squares   F-statistic:                     XXX
Date:                                   Prob (F-statistic):              0.XXX
Time:                                   Log-Likelihood:                  XXX
No. Observations:                  XX   AIC:                             XXX
Df Residuals:                      XX   BIC:                             XXX
Df Model:                           1
Covariance Type:            nonrobust
==============================================================================
                 coef    std err          t      P>|t|      [0.025      0.975]
------------------------------------------------------------------------------
const          XXX      XXX        XXX      XXX        XXX        XXX
Radio          XXX      XXX        XXX      XXX        XXX        XXX
==============================================================================
```

### Diagnostic Plots
1. **Residuals vs Fitted Values** - Check for patterns
2. **Q-Q Plot** - Test normality of residuals
3. **Scale-Location Plot** - Check homoscedasticity
4. **Correlation Heatmap** - Show variable relationships

## Business Insights

### Radio Channel ROI Analysis

**Key Findings:**
- Radio advertising shows a strong correlation with sales
- For every unit increase in Radio spending, sales increase by approximately [coefficient] units
- The model explains [R-squared]% of the variation in sales
- Statistical significance level: p-value = [value] (significant at α = 0.05)

### Recommendations

1. **Budget Allocation:** Increase Radio advertising investment based on the positive ROI
2. **Scale:** Consider the elasticity of sales with respect to Radio spending
3. **Testing:** Run A/B tests to validate model predictions
4. **Monitoring:** Track actual vs. predicted sales regularly

## Limitations & Considerations

- Small sample size (n=17) - results may not generalize
- Missing value in TV (row 14) - handled through removal
- Assumes linear relationship - may not capture complex interactions
- External factors not included in the model
- Temporal trends not accounted for

## Technologies Used

- **Python 3.x**
- **Pandas:** Data manipulation and analysis
- **NumPy:** Numerical computations
- **Matplotlib & Seaborn:** Data visualization
- **Statsmodels:** OLS regression and diagnostics
- **Scikit-learn:** Additional statistical metrics

## References

- [Statsmodels Documentation](https://www.statsmodels.org/)
- [OLS Regression Guide](https://www.statsmodels.org/stable/generated/statsmodels.regression.linear_model.OLS.html)
- [Regression Diagnostics](https://www.statsmodels.org/stable/graphics.html)

## Author

**Insikai**

## License

MIT License - Feel free to use this project for educational purposes.

---

## Questions or Issues?

If you encounter any problems:
1. Check that all dependencies are installed: `pip install -r requirements.txt`
2. Ensure the CSV file is in the correct directory
3. Verify the notebook cells run in order
4. Check Python version compatibility (3.7+)

Happy analyzing! 📊📈