# Student Performance Dataset

## Overview

This dataset provides a comprehensive overview of various factors affecting student performance in exams. It includes information on study habits, attendance, parental involvement, and other aspects influencing academic success. The dataset contains 6,607 student records with 20 features covering academic, demographic, socioeconomic, and environmental factors that may impact exam performance.

## Dataset Information

- **Number of Rows**: 6,607
- **Number of Columns**: 20
- **Missing Values**: 235 total (distributed across 3 columns)
  - Teacher_Quality: 78 missing values
  - Parental_Education_Level: 90 missing values
  - Distance_from_Home: 67 missing values
- **Target Variable**: `Exam_Score` (continuous, regression problem)
- **Problem Type**: Regression (predicting exam scores based on various factors)

## Dataset Columns

### 1. Hours_Studied
- **Type**: Numeric (Integer)
- **Description**: Number of hours spent studying per week.
- **Range**: 1 - 44 hours
- **Mean**: 19.98 hours

### 2. Attendance
- **Type**: Numeric (Float)
- **Description**: Percentage of classes attended.
- **Range**: 0-100%

### 3. Parental_Involvement
- **Type**: Categorical (Ordinal)
- **Description**: Level of parental involvement in the student's education.
- **Values**: Low, Medium, High
- **Distribution**:
  - Medium: 3,362 (50.9%)
  - High: 1,908 (28.9%)
  - Low: 1,337 (20.2%)

### 4. Access_to_Resources
- **Type**: Categorical (Ordinal)
- **Description**: Availability of educational resources.
- **Values**: Low, Medium, High
- **Distribution**:
  - Medium: 3,319 (50.2%)
  - High: 1,975 (29.9%)
  - Low: 1,313 (19.9%)

### 5. Extracurricular_Activities
- **Type**: Categorical (Binary)
- **Description**: Participation in extracurricular activities.
- **Values**: Yes, No
- **Distribution**:
  - Yes: 3,938 (59.6%)
  - No: 2,669 (40.4%)

### 6. Sleep_Hours
- **Type**: Numeric (Integer)
- **Description**: Average number of hours of sleep per night.
- **Range**: 4 - 10 hours
- **Mean**: 7.03 hours

### 7. Previous_Scores
- **Type**: Numeric (Integer/Float)
- **Description**: Scores from previous exams.

### 8. Motivation_Level
- **Type**: Categorical (Ordinal)
- **Description**: Student's level of motivation.
- **Values**: Low, Medium, High
- **Distribution**:
  - Medium: 3,351 (50.7%)
  - Low: 1,937 (29.3%)
  - High: 1,319 (20.0%)

### 9. Internet_Access
- **Type**: Categorical (Binary)
- **Description**: Availability of internet access.
- **Values**: Yes, No
- **Distribution**:
  - Yes: 6,108 (92.5%)
  - No: 499 (7.5%)

### 10. Tutoring_Sessions
- **Type**: Numeric (Integer)
- **Description**: Number of tutoring sessions attended per month.

### 11. Family_Income
- **Type**: Categorical (Ordinal)
- **Description**: Family income level.
- **Values**: Low, Medium, High
- **Distribution**:
  - Low: 2,672 (40.4%)
  - Medium: 2,666 (40.3%)
  - High: 1,269 (19.2%)

### 12. Teacher_Quality
- **Type**: Categorical (Ordinal)
- **Description**: Quality of the teachers.
- **Values**: Low, Medium, High
- **Distribution**:
  - Medium: 3,925 (59.4%)
  - High: 1,947 (29.5%)
  - Low: 657 (9.9%)
  - Missing: 78 (1.2%)

### 13. School_Type
- **Type**: Categorical
- **Description**: Type of school attended.
- **Values**: Public, Private
- **Distribution**:
  - Public: 4,598 (69.6%)
  - Private: 2,009 (30.4%)

### 14. Peer_Influence
- **Type**: Categorical
- **Description**: Influence of peers on academic performance.
- **Values**: Positive, Neutral, Negative
- **Distribution**:
  - Positive: 2,638 (39.9%)
  - Neutral: 2,592 (39.2%)
  - Negative: 1,377 (20.8%)

### 15. Physical_Activity
- **Type**: Numeric (Integer/Float)
- **Description**: Average number of hours of physical activity per week.

### 16. Learning_Disabilities
- **Type**: Categorical (Binary)
- **Description**: Presence of learning disabilities.
- **Values**: Yes, No
- **Distribution**:
  - No: 5,912 (89.5%)
  - Yes: 695 (10.5%)

### 17. Parental_Education_Level
- **Type**: Categorical (Ordinal)
- **Description**: Highest education level of parents.
- **Values**: High School, College, Postgraduate
- **Distribution**:
  - High School: 3,223 (48.8%)
  - College: 1,989 (30.1%)
  - Postgraduate: 1,305 (19.8%)
  - Missing: 90 (1.4%)

### 18. Distance_from_Home
- **Type**: Categorical (Ordinal)
- **Description**: Distance from home to school.
- **Values**: Near, Moderate, Far
- **Distribution**:
  - Near: 3,884 (58.8%)
  - Moderate: 1,998 (30.3%)
  - Far: 658 (10.0%)
  - Missing: 67 (1.0%)

### 19. Gender
- **Type**: Categorical
- **Description**: Gender of the student.
- **Values**: Male, Female
- **Distribution**:
  - Male: 3,814 (57.7%)
  - Female: 2,793 (42.3%)

### 20. Exam_Score
- **Type**: Numeric (Integer/Float) - **Target Variable**
- **Description**: Final exam score.
- **Range**: 55 - 101
- **Mean**: 67.24
- **Median**: 67

## Data Characteristics

### Target Variable Distribution
- **Range**: 55 to 101
- **Mean**: 67.24
- **Median**: 67
- The distribution appears relatively balanced around the mean, suitable for regression analysis.

### Data Quality
- **Missing Values**: 235 missing values (3.6% of total data) across 3 columns:
  - Teacher_Quality: 78 (1.2%)
  - Parental_Education_Level: 90 (1.4%)
  - Distance_from_Home: 67 (1.0%)
- **Data Types**: Mix of numeric (continuous and discrete) and categorical variables.
- **Imbalanced Features**: Some categorical features show imbalanced distributions (e.g., Internet_Access: 92.5% Yes, Learning_Disabilities: 89.5% No).

### Feature Categories
- **Academic**: Hours_Studied, Attendance, Previous_Scores, Tutoring_Sessions, Exam_Score (target)
- **Demographic**: Gender, Age (if present)
- **Socioeconomic**: Family_Income, Parental_Education_Level, Access_to_Resources
- **Family/Home**: Parental_Involvement, Distance_from_Home
- **School Environment**: Teacher_Quality, School_Type, Peer_Influence
- **Lifestyle**: Sleep_Hours, Physical_Activity, Extracurricular_Activities
- **Personal**: Motivation_Level, Learning_Disabilities, Internet_Access

## Usage

This dataset is suitable for:

1. **Regression Analysis**: Predict exam scores based on various academic, demographic, and environmental factors.
2. **Exploratory Data Analysis (EDA)**: Understand relationships between different factors and academic performance.
3. **Machine Learning Practice**: Build regression models (linear regression, random forest, gradient boosting, neural networks).
4. **Feature Importance Analysis**: Identify which factors most strongly influence student performance.
5. **Clustering**: Identify student groups with similar characteristics and performance patterns.
6. **Data Visualization**: Create compelling visualizations showing correlations between factors and exam scores.
7. **Educational Research**: Study the impact of various factors on student academic outcomes.
8. **Policy Analysis**: Understand how different educational policies and resources affect student performance.

## Considerations

1. **Missing Values**: Handle missing values in Teacher_Quality, Parental_Education_Level, and Distance_from_Home. Options include:
   - Imputation (mean, median, mode, or predictive imputation)
   - Dropping rows with missing values (if acceptable)
   - Creating a "Missing" category for categorical variables

2. **Feature Scaling**: For machine learning models, consider scaling numeric features (Hours_Studied, Attendance, Sleep_Hours, Physical_Activity, etc.), especially if using distance-based algorithms or neural networks.

3. **Categorical Encoding**: Categorical variables may need encoding:
   - **Ordinal variables** (Parental_Involvement, Access_to_Resources, Motivation_Level, Family_Income, Teacher_Quality, Parental_Education_Level, Distance_from_Home): Use ordinal encoding or label encoding
   - **Nominal variables** (Gender, School_Type, Peer_Influence, Extracurricular_Activities, Internet_Access, Learning_Disabilities): Use one-hot encoding

4. **Feature Interactions**: Consider creating interaction features (e.g., Hours_Studied × Motivation_Level, Parental_Involvement × Access_to_Resources) as they may capture complex relationships.

5. **Outliers**: Check for outliers in numeric features, especially in Hours_Studied (max: 44 hours), Exam_Score, and Previous_Scores.

6. **Multicollinearity**: Some features may be correlated (e.g., Family_Income and Access_to_Resources, Parental_Education_Level and Parental_Involvement). Consider checking for multicollinearity if using linear models.

7. **Class Imbalance**: Some binary/categorical features are imbalanced (Internet_Access: 92.5% Yes, Learning_Disabilities: 89.5% No). This may affect feature importance in some models.

8. **Causation vs. Correlation**: The dataset shows correlations between factors and exam scores, but does not establish causation. Be cautious when interpreting results.

9. **Data Quality**: Verify the consistency of data (e.g., ensure Exam_Score values are within expected ranges, Hours_Studied values are reasonable).

## Evaluation Metrics

For regression tasks, consider using:
- **Mean Absolute Error (MAE)**: Average absolute difference between predicted and actual scores.
- **Mean Squared Error (MSE)**: Average squared difference (penalizes larger errors more).
- **Root Mean Squared Error (RMSE)**: Square root of MSE (in same units as target).
- **R² Score (Coefficient of Determination)**: Proportion of variance explained by the model.
- **Adjusted R²**: R² adjusted for the number of features.
- **Mean Absolute Percentage Error (MAPE)**: Percentage-based error metric.

## Research Questions

Potential research questions to explore:
1. How do study hours correlate with exam scores?
2. What is the impact of attendance on academic performance?
3. How does parental involvement affect student performance?
4. What role does access to resources play in exam scores?
5. Do extracurricular activities positively or negatively impact grades?
6. How does sleep duration relate to academic performance?
7. What is the relationship between previous scores and current exam performance?
8. How does motivation level influence exam scores?
9. Does internet access significantly impact student performance?
10. What is the effect of tutoring sessions on exam scores?
11. How does family income correlate with academic performance?
12. What role does teacher quality play in student outcomes?
13. Do public or private school students perform better?
14. How does peer influence affect academic performance?
15. What is the relationship between physical activity and exam scores?
16. How do learning disabilities impact student performance?
17. Does parental education level correlate with student exam scores?
18. How does distance from home affect academic performance?
19. Are there gender differences in exam performance?
20. What combination of factors best predicts exam scores?

## Feature Engineering Ideas

1. **Study Efficiency**: `Exam_Score / Hours_Studied` (score per study hour)
2. **Improvement Score**: `Exam_Score - Previous_Scores` (improvement from previous exams)
3. **Academic Engagement Index**: Combine Hours_Studied, Attendance, and Motivation_Level
4. **Resource Advantage**: Combine Access_to_Resources, Internet_Access, and Family_Income
5. **Support System Score**: Combine Parental_Involvement, Parental_Education_Level, and Tutoring_Sessions
6. **School Environment Index**: Combine Teacher_Quality, School_Type, and Peer_Influence
7. **Lifestyle Balance**: Combine Sleep_Hours, Physical_Activity, and Extracurricular_Activities
8. **Socioeconomic Status**: Encode Family_Income and Parental_Education_Level as composite score
9. **Distance Impact**: Convert Distance_from_Home to numeric (Near=1, Moderate=2, Far=3)
10. **Parental Support Index**: Interaction between Parental_Involvement and Parental_Education_Level
11. **Study-Sleep Balance**: Ratio of Hours_Studied to Sleep_Hours
12. **Tutoring Effectiveness**: Interaction between Tutoring_Sessions and Teacher_Quality
13. **Resource Utilization**: Interaction between Access_to_Resources and Internet_Access
14. **Motivation-Study Interaction**: Hours_Studied × Motivation_Level (encoded)
15. **Risk Factors**: Composite score for students with Learning_Disabilities, Low Motivation, and Poor Attendance

## Model Suggestions

### Regression Models
- **Linear Regression**: Baseline model, interpretable coefficients
- **Ridge/Lasso Regression**: Handle multicollinearity and feature selection
- **Elastic Net**: Balance between Ridge and Lasso
- **Random Forest**: Capture non-linear relationships and feature interactions
- **Gradient Boosting** (XGBoost, LightGBM, CatBoost): High performance, handles mixed data types well
- **Neural Networks**: Complex non-linear relationships
- **Support Vector Regression (SVR)**: Non-linear relationships with kernel tricks

### Clustering Models
- **K-Means**: Identify student groups with similar characteristics
- **Hierarchical Clustering**: Understand cluster relationships
- **DBSCAN**: Find density-based student groups

## Visualization Ideas

1. **Correlation Heatmap**: Show correlations between all numeric features
2. **Scatter Plots**: Hours_Studied vs. Exam_Score, Attendance vs. Exam_Score, Previous_Scores vs. Exam_Score
3. **Box Plots**: Exam scores by Parental_Involvement, Motivation_Level, School_Type, Gender
4. **Distribution Plots**: Histograms of Exam_Score, Hours_Studied, Sleep_Hours
5. **Pair Plots**: Relationships between key numeric features
6. **Violin Plots**: Distribution of exam scores across different categories
7. **Feature Importance**: From tree-based models (Random Forest, XGBoost)
8. **Missing Values Visualization**: Show patterns in missing data
9. **Interaction Plots**: Visualize how combinations of factors affect performance

## Educational Context

This dataset is designed for:
- **Machine Learning Courses**: Regression, feature engineering, model evaluation, handling missing data
- **Data Science Projects**: End-to-end analysis from EDA to model deployment
- **Statistics Courses**: Correlation analysis, regression modeling, hypothesis testing
- **Educational Research**: Understanding factors affecting student performance
- **Policy Analysis**: Examining how different educational factors impact outcomes

## Missing Data Handling

The dataset contains 235 missing values across 3 columns:
- **Teacher_Quality**: 78 missing (1.2%)
- **Parental_Education_Level**: 90 missing (1.4%)
- **Distance_from_Home**: 67 missing (1.0%)

**Recommended approaches**:
1. **For categorical variables**: Create a "Missing" or "Unknown" category
2. **For predictive imputation**: Use other features to predict missing values
3. **For complete case analysis**: Drop rows with missing values (if acceptable and doesn't introduce bias)
4. **For multiple imputation**: Use advanced imputation techniques if conducting statistical analysis

## Important Notes

- This dataset contains a comprehensive set of factors that may influence student performance.
- The relationships between features and exam scores may be complex and non-linear.
- Consider domain knowledge when interpreting results (e.g., very high study hours may indicate stress rather than effectiveness).
- Be mindful of potential confounding variables and spurious correlations.
- The dataset may be useful for identifying at-risk students or factors that need intervention.

---

**Note**: This dataset is suitable for educational and research purposes. When interpreting results, remember that correlation does not imply causation, and real-world educational outcomes are influenced by many complex, interacting factors.

