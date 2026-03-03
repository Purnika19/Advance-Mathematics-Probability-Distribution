# Probability Distribution Analysis

## Overview

This project performs mathematical analysis on NO₂ concentration data by fitting a custom probability distribution function to transformed and normalized data.

The transformation parameters are computed using roll number 102303412.

Transformation used:

z = x + 0.5 sin(0.9 x)

The analysis demonstrates data preprocessing, statistical modeling, non-linear curve fitting, and probability density estimation using Python.

---

## Project Structure

. Advance_Mathematics.ipynb – Jupyter Notebook containing the complete step-by-step analysis  
. advance_mathematics.py – Python script version of the implementation  
. README.md – Documentation file  

---

## Dependencies

The following Python packages are required:

. pandas – Data manipulation  
. numpy – Numerical computing  
. matplotlib – Visualization  
. scikit-learn – Statistical utilities  
. scipy – Optimization and curve fitting  

Install dependencies using:

pip install pandas numpy matplotlib scikit-learn scipy

---

## Code Workflow

### 1. Data Loading

. Loads NO₂ concentration data from `data.csv`  
. Uses pandas for structured data handling  
. Extracts the NO₂ column for analysis  

---

### 2. Data Transformation

. Uses roll number 102303412  
. Computes transformation parameters:  
  . a_r = 0.5  
  . b_r = 0.9  
. Applies non-linear sinusoidal transformation:

z = x + 0.5 sin(0.9 x)

This transformation introduces controlled non-linearity into the dataset.

---

### 3. Normalization

. Computes mean (z_mean) and standard deviation (z_std)  
. Applies Z-score normalization:

z_norm = (z − z_mean) / z_std  

This standardizes the dataset to zero mean and unit variance.

---

### 4. Histogram Computation

. Constructs histogram with 30 bins  
. Uses `density=True` to obtain probability density values  
. Computes bin centers for curve fitting  

The histogram approximates the empirical PDF.

---

### 5. PDF Model Definition

The fitted model is a Gaussian-like exponential-quadratic function:

pdf_model(x) = c · exp(−λ (x − μ)²)

Where:

. c – Scaling constant  
. λ – Shape parameter controlling spread  
. μ – Location parameter (mean shift)  

---

### 6. Curve Fitting

. Uses `scipy.optimize.curve_fit()`  
. Initial parameter estimates:  
  . c₀ = max(histogram density)  
  . λ₀ = 1.0  
  . μ₀ = 0.0  
. Constrains λ and μ within reasonable bounds  
. Allows up to 50,000 function evaluations for convergence  

This performs non-linear least squares optimization.

---


## Output

The program prints the estimated distribution parameters:

FINAL PARAMETERS  
c = [estimated value]  
lambda = [estimated value]  
mu = [estimated value]  

These parameters define the fitted exponential-quadratic PDF.

---

---

## Mathematical Background

This project demonstrates:

. Non-linear transformation of real-world data  
. Statistical normalization  
. Empirical PDF approximation  
. Non-linear curve fitting using least squares  
. Parameter estimation of probability models  

The fitted exponential-quadratic model approximates the empirical distribution of transformed NO₂ values and enables:

. Probabilistic modeling  
. Density estimation  
. Comparison with theoretical distributions  

This analysis connects data transformation, optimization, and probability theory in a practical statistical modeling framework.r data ranges
Compare with theoretical distributions
