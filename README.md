# R Programming & Statistical Methods Assignment

This folder contains R scripts and an analytical report detailing various statistical procedures, simulations, and modeling techniques. The scripts cover probability distributions, Monte Carlo approximations, bootstrapping, and data merging/regression analysis.

---

## Overview

The directory focuses on applying basic and advanced statistical computational methods in the R programming language:
1. **Descriptive Statistics**: R-based calculation of custom vector means, lengths, and custom standard deviations/variance metrics.
2. **Probability & Distributions**: Modeling uniform continuous distributions and generating visual histograms.
3. **Monte Carlo Pi Estimation**: Programmatic estimation of the value of $\pi$ by plotting random coordinate pairs $(x, y)$ inside a bounding box and determining the ratio that falls within a unit circle.
4. **Bootstrapping**: Non-parametric bootstrap resampling to calculate the mean and standard error of a sample, producing a 95% confidence interval.
5. **Macroeconomic Regression**: Merging historical GDP and Unemployment datasets on a date key, resolving null values, and fitting an Ordinary Least Squares (OLS) regression line ($UNRATE = \beta_0 + \beta_1 \cdot GDP + \epsilon$) to evaluate economic correlation.

---

## Folder Contents

| File Name | Format | Description |
| :--- | :--- | :--- |
| [`867 finished Assignment`](file:///c:/Users/HP/OneDrive/Desktop/Projectssssss/867%20Assignment/867%20finished%20Assignment) | R Script (No Ext) | Interactive R code notebook compiling statistical simulations, bootstrapping, and regression routines. |
| [`Report_ Interpretation of Linear Regression Analysis Results (1).pdf`](file:///c:/Users/HP/OneDrive/Desktop/Projectssssss/867%20Assignment/Report_%20Interpretation%20of%20Linear%20Regression%20Analysis%20Results%20(1).pdf) | PDF | Diagnostic report reviewing the statistical significance, intercept, coefficients, and $R^2$ metrics of the GDP-Unemployment regression model. |

---

## Detailed Script Mechanics

The R script is structured into multiple functional phases:
* **Monte Carlo Circle Sampling**:
  Generating $N = 1000$ coordinates $x, y \sim \text{Uniform}(-1, 1)$. The ratio of points satisfying $x^2 + y^2 \le 1$ to the total samples is scaled by 4 to approximate $\pi$.
* **Non-Parametric Bootstrap Resampling**:
  Draws $B = 1000$ bootstrap replicates with replacement from a normal sample ($N=100, \mu=5, \sigma=2$). Computes sample means and quantiles for a 95% confidence interval:
  $$\text{CI}_{95\%} = [q_{0.025}, q_{0.975}]$$
* **Data Integration & Regression**:
  Performs an inner join of GDP and Unemployment datasets (`gdp_data.csv` and `unemployment_data.csv`) using the `DATE` identifier. A linear model is fitted:
  ```r
  model <- lm(UNRATE ~ GDP, data=cleaned_data)
  summary(model)
  ```

---

## Usage

To execute the R scripts:
1. Ensure R or RStudio is installed.
2. Open an R console and run the file:
   ```r
   source("867 finished Assignment")
   ```
3. Open the PDF report to review the regression diagnostic write-ups and results interpretation.

## Dependencies
* **R Environment** (v4.0.0 or higher recommended)
* Base R graphics package (for `hist`, `boxplot`, and `plot` calls)
