# Wine Quality Analysis — Data Science Capstone

## 1. Project Overview

This project demonstrates an end-to-end data science workflow using Python and the UCI Wine Quality dataset. It investigates whether physicochemical properties of red and white wines can help predict sensory quality scores and explores whether wines form groups based on their measured characteristics.

## 2. Objectives

- Acquire a publicly available dataset.
- Inspect, clean, and preprocess the data.
- Perform exploratory data analysis (EDA) and create visualizations.
- Build and evaluate supervised machine learning models.
- Apply unsupervised learning to identify potential groups in the dataset.
- Interpret results and provide recommendations for future analysis.

## 3. Dataset Information

**Dataset:** Wine Quality  
**Source:** UCI Machine Learning Repository  
**URL:** https://archive.ics.uci.edu/dataset/186/wine+quality

The dataset contains red and white wine samples with physicochemical measurements, including:

- Fixed acidity
- Volatile acidity
- Citric acid
- Residual sugar
- Chlorides
- Free and total sulfur dioxide
- Density
- pH
- Sulphates
- Alcohol

The target variable is `quality`, representing the sensory quality score. The notebook also includes a `wine_type` feature to distinguish red and white wines.

## 4. Project Structure

```text
Wine-Quality-Capstone/
│
├── wine_quality_data_science_capstone.ipynb
├── wine_quality_capstone_report_completed.docx
├── regression_model_results.csv
├── feature_importance.csv
├── clustering_silhouette_scores.csv
├── cluster_profiles.csv
└── README.md
```

## 5. Technologies and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Requests
- Jupyter Notebook

## 6. Installation

Install the required Python libraries using:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn requests jupyter
```

## 7. How to Run the Project

1. Download the project files.
2. Open the Jupyter Notebook in Jupyter Notebook or Google Colab.
3. Ensure the required Python libraries are installed.
4. Run the notebook cells sequentially, from beginning to end.
5. Review the data summaries, charts, model evaluation metrics, and clustering outputs.
6. Verify that the CSV output files contain the latest results.
7. Review the Word report and personalize the author information before submission.

The notebook attempts to download the dataset automatically. If internet access is unavailable, download the red and white wine CSV files from the UCI website and place them in a local `data/` folder.

## 8. Project Methodology

### 8.1 Data Acquisition

The dataset is obtained from the UCI Machine Learning Repository. The red and white wine datasets are combined into a single DataFrame.

### 8.2 Data Cleaning and Preprocessing

The notebook checks:

- Dataset dimensions and data types
- Missing values
- Duplicate records
- Numeric summaries and potential invalid values

Exact duplicate records are removed, and the target variable is converted to numeric format. Wine type is encoded for use in machine learning.

### 8.3 Exploratory Data Analysis

EDA includes:

- Wine quality score distributions
- Alcohol levels by wine type
- Correlation heatmap
- Group-level summary statistics
- Relationships between physicochemical measurements and quality

### 8.4 Supervised Machine Learning

A Random Forest Regressor is trained to predict wine quality scores.

A mean-prediction baseline is used for comparison.

The evaluation metrics are:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R-squared (R²)

### 8.5 Unsupervised Machine Learning

K-Means clustering is applied to standardized numeric physicochemical features, excluding the quality target.

Silhouette scores are compared for different cluster counts to assess cluster separation. Cluster profiles are then examined to understand differences between the resulting groups.

### 8.6 Optional Classification

The notebook also includes an optional classification task that labels wines with quality scores of 7 or higher as the higher-quality class.

This extension uses classification metrics such as precision, recall, F1-score, and accuracy.

## 9. Results

The supplied regression results are:

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Mean baseline | 0.694 | 0.868 | -0.001 |
| Random Forest | 0.510 | 0.664 | 0.413 |

The Random Forest model performs better than the mean baseline across the reported metrics.

Its R² of approximately 0.413 indicates that the model explains around 41.3% of the variation in quality scores in the held-out test set.

Among the tested K-Means configurations, two clusters achieved the highest silhouette score, approximately 0.270. This indicates modest cluster separation rather than clearly separated groups.

These results should be verified by rerunning the notebook.

## 10. Key Insights

- The Random Forest model provides better predictive performance than the simple mean baseline.
- Alcohol and volatile acidity are among the most important features in the supplied model results.
- K-Means identifies two groups with different average physicochemical characteristics.
- Feature importance indicates predictive association, not causation.
- Model predictions should support analysis rather than replace expert sensory assessment.

## 11. Limitations

- Wine quality scores are subjective.
- The test results are based on a particular train/test split.
- Feature importance can be affected by correlated variables.
- K-Means results depend on feature selection, scaling, and the chosen number of clusters.
- Performance may differ for wines from other producers, regions, or vintages.

## 12. Future Improvements

- Perform cross-validation and hyperparameter tuning.
- Compare Random Forest with gradient boosting and other regression methods.
- Explore permutation importance or SHAP for model interpretation.
- Validate the model using an independent dataset.
- Investigate additional contextual information if available.

## 13. Deliverables

- **Jupyter Notebook:** executable Python code, analysis, visualizations, and modeling.
- **Word Report:** project background, methodology, findings, evaluation, and recommendations.
- **CSV Files:** model results, feature importance, silhouette scores, and cluster profiles.
- **README.md:** project overview, installation, execution instructions, methodology, and results.

## 14. References

1. Cortez, P., Cerdeira, A., Almeida, F., Matos, T., & Reis, J. (2009). *Modeling wine preferences by data mining from physicochemical properties*. Decision Support Systems, 47(4), 547–553.
2. UCI Machine Learning Repository. Wine Quality Dataset. https://archive.ics.uci.edu/dataset/186/wine+quality
3. Scikit-learn Documentation. https://scikit-learn.org/stable/

## 15. Author Information

- **Name:** Chidananda M


