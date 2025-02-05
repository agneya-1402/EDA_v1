# Exploratory Data Analysis (EDA) on Wine Quality Dataset

![EDA](https://img.shields.io/badge/Analysis-Exploratory%20Data%20Analysis-blue)
![Python](https://img.shields.io/badge/Language-Python-green)
![Pandas](https://img.shields.io/badge/Tools-Pandas%20|%20Seaborn%20|%20Matplotlib-orange)

This project demonstrates an **Exploratory Data Analysis (EDA)** on the [WineQT Dataset](https://www.kaggle.com/datasets/rajyellow46/wine-quality), focusing on understanding patterns, trends, and relationships in wine quality using statistical tools and visualizations.

## Overview
EDA is a critical step in data analysis to uncover insights through visualization and statistical summaries. This project covers:
- **Univariate Analysis**: Distribution of individual features.
- **Bivariate Analysis**: Relationships between pairs of features.
- **Multivariate Analysis**: Correlation and interactions among multiple variables.

## Dataset Description
- **Source**: [WineQT Dataset](https://www.kaggle.com/datasets/rajyellow46/wine-quality)
- **Rows**: 1143 | **Columns**: 13
- **Features**:
  - `fixed acidity`, `volatile acidity`, `citric acid`, `residual sugar`, `chlorides`, `free sulfur dioxide`, `total sulfur dioxide`, `density`, `pH`, `sulphates`, `alcohol`, `quality`, `Id`

## Key Steps

### 1. Data Loading & Initial Checks
- Loaded dataset with `pandas`.
- Checked dimensions, data types, and missing values.
- Generated descriptive statistics.

```
import pandas as pd
df = pd.read_csv("/content/WineQT.csv")
df.info()
```
### 2. Handling Missing Values & Duplicates
Missing Values: No null values detected.
Duplicates: Identified unique counts per feature.

```
df.isnull().sum()  # No missing values
df.nunique()       # Unique values per column
```
### 3. Univariate Analysis
Quality Distribution: Most wines rated 5–6 on quality (scale: 3–8).
Feature Skewness: Identified skewed distributions (e.g., chlorides, residual sugar).
Quality Distribution

```
sns.histplot(df['quality'], kde=False)
```
### 4. Bivariate Analysis
Alcohol vs. Quality: Higher alcohol content correlates with better quality. 
Outliers Detected: Swarm plots revealed outliers in free sulfur dioxide.
Swarm Plot

```
sns.swarmplot(x="quality", y="alcohol", data=df)
```
### 5. Multivariate Analysis
Correlation Heatmap:
alcohol positively correlates with quality (+0.48).
density negatively correlates with alcohol (-0.69).
Correlation Matrix

```
sns.heatmap(df.corr(), annot=True)
```

## Installation
Clone the repository:

```
git clone https://github.com/agneya-1402/EDA_v1.git
```

## Install dependencies:

```
pip install pandas numpy matplotlib seaborn
```

## Usage
Run the Jupyter notebook to reproduce the analysis:

```
jupyter notebook EDA_v1.ipynb
```

## Results
Quality Insights: 82% of wines rated 5–6.

Key Correlations:
Positive: alcohol ➔ quality.
Negative: density ➔ alcohol.
Outliers: Detected in free sulfur dioxide and chlorides.

## Conclusion
EDA revealed critical relationships impacting wine quality.
Alcohol content and acidity levels are significant quality indicators.
Further analysis could involve predictive modeling (e.g., classification).

## References
Dataset: WineQT Dataset
Inspired by: GeeksforGeeks EDA Guide
