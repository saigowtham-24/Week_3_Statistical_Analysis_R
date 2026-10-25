# Week 3: Statistical Analysis and Predictive Modeling using R

## Project overview
This project analyzes the Titanic passenger training dataset using descriptive statistics, hypothesis testing, correlation analysis, and predictive classification. The R script provides a reproducible workflow for preprocessing, statistical tests, Logistic Regression, Random Forest, cross-validation, model evaluation, and plots.

## Contents
- `statistical_analysis_week3.R` — complete R analysis workflow.
- `Week_3_Statistical_Analysis_Report.docx` — formatted project report.
- `data/titanic_analysis_data.csv` — Titanic training data used for the project.
- `plots/` — visualizations for survival distribution, age, fare, subgroup survival, correlations, ROC, confusion matrix, and variable importance.
- `outputs/` — descriptive statistics, missingness, hypothesis tests, model metrics, confusion matrix, predictions, permutation importance, and a concise summary.
- `screenshots/` — directory for genuine RStudio screenshots of code execution and output.

## Run the R workflow
1. Open this folder as the project root in RStudio.
2. Open `statistical_analysis_week3.R`.
3. Run the script from top to bottom. It installs missing packages and downloads the public dataset if the local data file is absent.
4. The script regenerates the plots and CSV/text outputs in the project folders.

## Methods
- Missing-value review and median/mode imputation
- Descriptive statistics and Pearson correlation
- Chi-square tests for sex/class associations with survival
- Wilcoxon rank-sum and Shapiro–Wilk tests
- Stratified 80/20 train/test split and repeated 5-fold cross-validation
- Logistic Regression and Random Forest
- Accuracy, precision, recall, specificity, F1-score, ROC-AUC, confusion matrix, and permutation importance

## Data source
Titanic training data published in the `datasciencedojo/datasets` GitHub repository: `https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv`.
