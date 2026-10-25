# Week 3: Statistical Analysis and Predictive Modeling Using R

## 1. Project Overview

This project focuses on statistical analysis and predictive modeling using the Titanic passenger training dataset and the R programming language. It explores passenger demographics, survival patterns, relationships between variables, and the factors associated with survival.

The project follows a structured data analysis workflow, including data preprocessing, descriptive statistics, hypothesis testing, correlation analysis, predictive model development, and model evaluation.

Two classification algorithms—**Logistic Regression** and **Random Forest**—are used to predict passenger survival. Their performance is assessed using a stratified training and testing split, repeated cross-validation, and multiple classification metrics.

The analysis produces statistical summaries, hypothesis-testing results, diagnostic visualizations, model performance comparisons, and predictions.

## 2. Project Objectives

* Examine the Titanic dataset and understand its structure.
* Identify and handle missing values in relevant variables.
* Calculate descriptive statistics for numerical variables.
* Analyze relationships between passenger characteristics and survival.
* Perform hypothesis tests to investigate associations and group differences.
* Examine variable distributions and assess normality.
* Calculate correlations between numerical variables.
* Develop Logistic Regression and Random Forest classification models.
* Evaluate model performance using cross-validation and a held-out test dataset.
* Visualize statistical findings and model evaluation results.
* Communicate the results through a structured project report.

## 3. Repository Structure

```text
Week_3_Statistical_Analysis_R/
│
├── README.md
├── .gitignore
├── statistical_analysis_week3.R
├── Week_3_Statistical_Analysis_Report.docx
│
├── data/
│   └── titanic_analysis_data.csv
│
├── screenshots/
│   └── README.md
│
├── plots/
│   ├── README.md
│   ├── survival_distribution.png
│   ├── age_distribution.png
│   ├── fare_by_class_boxplot.png
│   ├── survival_by_sex_class.png
│   ├── correlation_heatmap.png
│   ├── roc_curve.png
│   ├── confusion_matrix.png
│   └── variable_importance.png
│
└── outputs/
    ├── README.md
    ├── descriptive_statistics.csv
    ├── missing_values.csv
    ├── hypothesis_test_results.csv
    ├── model_comparison.csv
    ├── confusion_matrix.csv
    ├── test_predictions.csv
    ├── permutation_importance.csv
    └── analysis_summary.txt
```

## 4. Dataset Description

The project uses the Titanic passenger training dataset, which contains passenger information and survival outcomes.

The dataset includes variables such as:

| Variable   | Description                                                        |
| ---------- | ------------------------------------------------------------------ |
| `Survived` | Survival status: 0 indicates did not survive; 1 indicates survived |
| `Pclass`   | Passenger class                                                    |
| `Sex`      | Passenger sex                                                      |
| `Age`      | Passenger age                                                      |
| `SibSp`    | Number of siblings and spouses aboard                              |
| `Parch`    | Number of parents and children aboard                              |
| `Fare`     | Passenger fare                                                     |
| `Embarked` | Port of embarkation                                                |

The dataset also contains passenger identifiers and other descriptive fields.

### Data Source

The Titanic training dataset is available from the following public GitHub repository:

[ Titanic Dataset — DataSciencoDojo Datasets](https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv)

The R workflow uses the local CSV file when available and can download the dataset if the local file is absent, as implemented in the script.

## 5. Tools and Technologies

* **R:** Statistical analysis and predictive modeling.
* **RStudio:** Development and execution environment.
* **ggplot2:** Data visualization.
* **dplyr:** Data manipulation.
* **tidyr:** Data organization and transformation.
* **caret:** Data splitting, cross-validation, and model evaluation.
* **randomForest:** Random Forest classification.
* **pROC:** Receiver Operating Characteristic (ROC) analysis.

The script should load or install the required packages before performing the analysis.

## 6. Methodology

### 6.1 Data Preprocessing

The dataset is examined for missing values, data types, and relevant variables. Missingness is summarized before and after preprocessing.

Median imputation is applied to selected numerical variables, including age and fare, while mode imputation is used for the embarkation variable.

The preprocessing workflow prepares the data for statistical analysis and model development.

### 6.2 Descriptive Statistical Analysis

Descriptive statistics are calculated to summarize numerical variables. These statistics help characterize passenger demographics, ticket fares, and other relevant attributes.

The analysis includes measures such as:

* Mean and median
* Standard deviation
* Minimum and maximum
* Quartiles and distribution summaries

The results are exported to `outputs/descriptive_statistics.csv`.

### 6.3 Hypothesis Testing

Hypothesis tests are used to investigate relationships between passenger characteristics and survival outcomes.

The analysis includes:

* **Chi-square tests:** Examine associations between survival and categorical variables, including sex and passenger class.
* **Wilcoxon rank-sum test:** Compares age distributions between survival groups.
* **Shapiro–Wilk test:** Assesses normality for selected numerical variables.

The results are recorded in `outputs/hypothesis_test_results.csv`.

Statistical conclusions should be based on the calculated test statistics, p-values, significance level, and relevant test assumptions.

### 6.4 Correlation Analysis

Pearson correlation is used to examine linear relationships between selected numerical variables.

A correlation heatmap provides a visual summary of the relationships. Correlation indicates the strength and direction of a linear association; it does not establish causation.

The correlation results are used to support exploratory analysis and interpretation.

### 6.5 Predictive Modeling

Two classification algorithms are developed to predict passenger survival.

**Logistic Regression**

Logistic Regression estimates the probability of survival using the selected passenger attributes. It provides a statistical baseline for binary classification.

**Random Forest**

Random Forest combines predictions from multiple decision trees. It can capture nonlinear relationships and interactions between variables.

Both models are evaluated using the same general train/test evaluation framework to support a meaningful comparison.

### 6.6 Training, Testing, and Cross-Validation

The workflow uses a stratified 80/20 training and testing split to preserve the distribution of the survival outcome as far as possible.

Repeated five-fold cross-validation is used during model training. This helps assess performance across multiple training and validation partitions.

The held-out test set is used to evaluate final model performance on observations that were not used to fit the models.

### 6.7 Model Evaluation Metrics

The models are evaluated using the following metrics:

| Metric           | Purpose                                                                   |
| ---------------- | ------------------------------------------------------------------------- |
| Accuracy         | Proportion of all predictions that are correct                            |
| Precision        | Proportion of predicted survivors who actually survived                   |
| Recall           | Proportion of actual survivors correctly identified                       |
| Specificity      | Proportion of actual non-survivors correctly identified                   |
| F1-score         | Harmonic mean of precision and recall                                     |
| ROC-AUC          | Measures how well the model distinguishes between the two outcome classes |
| Confusion matrix | Summarizes correct and incorrect classifications                          |

The evaluation results are saved in `outputs/model_comparison.csv` and `outputs/confusion_matrix.csv`.

### 6.8 Visualizations and Diagnostics

The project includes visualizations to communicate the statistical findings and predictive model performance.

The plots cover:

* Survival distribution
* Age distribution
* Fare distribution across passenger classes
* Survival patterns by sex and passenger class
* Correlation heatmap
* ROC curve
* Confusion matrix
* Random Forest variable importance

These visualizations help interpret the dataset, compare model behavior, and identify variables that may contribute to predictive performance.

## 7. Output Files

The `outputs/` directory stores the results produced by the analysis script.

| File                          | Description                                              |
| ----------------------------- | -------------------------------------------------------- |
| `descriptive_statistics.csv`  | Descriptive summaries of selected variables              |
| `missing_values.csv`          | Missing-value information before and after preprocessing |
| `hypothesis_test_results.csv` | Results of the statistical tests                         |
| `model_comparison.csv`        | Performance comparison of the classification models      |
| `confusion_matrix.csv`        | Classification results for the evaluated model           |
| `test_predictions.csv`        | Predictions for the held-out test observations           |
| `permutation_importance.csv`  | Variable importance estimates based on permutation       |
| `analysis_summary.txt`        | Concise summary of the analysis results                  |

The `plots/` directory stores the visualizations generated by the workflow.

The `screenshots/` directory is intended to hold genuine screenshots captured during execution in RStudio, such as the analysis code, statistical output, model evaluation, and diagnostic results.

## 8. How to Run the Project

### Prerequisites

Install R and RStudio on your computer.

### Execution Steps

1. Clone or download the repository.
2. Open the project folder in RStudio.
3. Open `statistical_analysis_week3.R`.
4. Ensure the required R packages are available.
5. Run the script from top to bottom.
6. Review the generated plots and output files.
7. Open the Word report to review the analysis and findings.

The script is designed to generate the analysis outputs in the relevant project directories. The actual output files and results should be reviewed after execution.

## 9. Reproducibility and Validation

The R script is the primary source for reproducing the statistical analysis and predictive modeling workflow.

For reproducible results:

* Use the same dataset and preprocessing procedures.
* Preserve the specified training and testing approach.
* Review model settings and cross-validation configuration.
* Confirm that the output files correspond to the latest script execution.
* Base reported performance metrics and statistical conclusions on the generated results.
* Capture screenshots directly from RStudio when documenting code execution and output.

## 10. Conclusion

This project demonstrates the application of statistical analysis and predictive classification using R. It combines data preprocessing, descriptive statistics, hypothesis testing, correlation analysis, Logistic Regression, Random Forest, cross-validation, and model evaluation in a structured workflow.

The project provides a foundation for understanding passenger survival patterns and comparing classification approaches. The statistical findings and predictive performance should be interpreted using the actual generated outputs, while considering the assumptions and limitations of the dataset and modeling methods.

## 11. Author

**Project:** Week 3 — Statistical Analysis and Predictive Modeling Using R
**Programming Language:** R
**Dataset:** Titanic Passenger Training Dataset
**Repository:** `Week_3_Statistical_Analysis_R`
