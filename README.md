# XYZ Corp Predictive Maintenance System

## Problem Statement
XYZ Corp, a leading manufacturer of mining equipment, is facing challenges with unexpected machine failures in their rock drilling tools. These failures lead to costly downtime and reduced productivity at mining sites. The company aims to enhance its equipment performance and minimize unplanned maintenance by implementing a predictive maintenance system using the AI4I 2020 Predictive Maintenance Dataset.

## Objectives
1. Accurately predict potential machine failures before they occur.
2. Identify the most critical factors contributing to different types of failures (TWF, HDF, PWF, OSF, RNF).
3. Provide actionable insights to optimize operational parameters and maintenance schedules.
4. Reduce unexpected downtime by at least 25%.
5. Increase the overall equipment effectiveness (OEE) by 15%.
6. Optimize maintenance schedules to reduce costs while ensuring equipment reliability.
7. Provide real-time monitoring and early warning systems for potential failures.

## Dataset Description
The dataset simulates real-world industrial machinery data and includes the following features:

1. **UID**: Unique identifier for each data point (1-10,000).
2. **Product ID**: Identifier for the product quality (L, M, H) and variant-specific serial number.
3. **Type**: Product quality indicator (L, M, H).
4. **Air Temperature [K]**: Measured in Kelvin.
5. **Process Temperature [K]**: Measured in Kelvin.
6. **Rotational Speed [rpm]**: Revolutions per minute.
7. **Torque [Nm]**: Measured in Newton meters.
8. **Tool Wear [min]**: Tool wear time in minutes.
9. **Machine Failure**: Binary label indicating machine failure (0 for no failure, 1 for failure).
10. **Failure Modes**: TWF, HDF, PWF, OSF, RNF (binary indicators for specific failure types).

## Methodology
1. Data Collection and Cleaning
2. Exploratory Data Analysis (EDA)
3. Feature Engineering
4. Model Training and Evaluation
5. Model Improvement

## Exploratory Data Analysis (EDA)
- Analyzed the distribution of machine failures.
- Investigated correlations between features.
- Examined the relationship between equipment parameters and machine failures.

### Key Findings
- The dataset contains 3.39% machine failures, indicating most machines are working fine.
- Strong positive correlation (0.88) between process temperature and air temperature.
- Strong negative correlation (-0.88) between torque and rotational speed.
- Random Forest and Gradient Boosting models performed best in initial testing.
- Torque was identified as the most important feature for predicting equipment failure.

## Model Training and Evaluation
- Separated features and target.
- Split the data into training and testing sets.
- Scaled the features.
- Defined and evaluated multiple models (Random Forest, Gradient Boosting, SVM, Logistic Regression, K-Nearest Neighbors).

### Initial Model Performance
- Random Forest and Gradient Boosting models showed high accuracy and low variability.
- Random Forest model was chosen for further improvement.

### Model Improvement
- Addressed class imbalance with SMOTE.
- Performed feature engineering.
- Conducted hyperparameter tuning.

## Model Performance
Initial Random Forest model:
- **Accuracy**: 0.983
- **Precision for failure detection**: 0.80
- **Recall for failure detection**: 0.59

Improved model with SMOTE and feature engineering:
- **Accuracy**: 0.985
- **Precision for failure detection**: 0.86
- **Recall for failure detection**: 0.62

## Conclusions and Recommendations
1. Implement real-time monitoring of torque as it's the most critical factor in predicting failures.
2. Focus on improving the model's ability to detect actual failures (recall) while maintaining a balance with precision.
3. Continuously update and retrain the model with new data to improve its performance over time.

## Future Work
1. Explore more advanced feature engineering techniques.
2. Investigate deep learning models for more complex pattern recognition.
3. Implement a cost-sensitive learning approach to balance the importance of detecting failures vs. overall accuracy.
4. Develop a user-friendly interface for real-time monitoring and alerts.

## Hypothesis Testing
We conducted hypothesis testing to investigate the relationship between rotational speed and machine failures.

**Hypothesis**:
- **Null Hypothesis (H0)**: There is no significant difference in rotational speed between machines that fail and those that don't.
- **Alternative Hypothesis (H1)**: There is a significant difference in rotational speed between machines that fail and those that don't.

**Significance Level**: We set alpha (α) = 0.05.

**Statistical Test**:
We performed an independent samples t-test to compare the rotational speeds between failed and non-failed machines.

**Results**:
- **T-statistic**: -4.4226
- **P-value**: 9.8535e-06

**Conclusion**:
Since the p-value is significantly lower than the alpha level of 0.05, we reject the null hypothesis, indicating a significant difference in rotational speed between machines that fail and those that don't. This suggests that rotational speed is a crucial factor in predicting machine failures.

## Tools and Technologies Used
- Python
- Pandas for data manipulation
- Matplotlib and Seaborn for data visualization
- Scikit-learn for machine learning models
- Imbalanced-learn for handling class imbalance

## How to Use This Repository
1. Clone the repository.
2. Install the required Python libraries using `pip install -r requirements.txt`.
3. Run the Jupyter notebooks or Python scripts to reproduce the analysis and models.

## Contributors
Nikhil Bhati
