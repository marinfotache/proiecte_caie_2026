# Student Habits and Academic Performance Dataset

## Overview

This is a simulated dataset exploring how lifestyle habits affect academic performance in students. With 1,000 synthetic student records and 16 features including study hours, sleep patterns, social media usage, diet quality, mental health, and final exam scores, it's perfect for ML projects, regression analysis, clustering, and data visualization. Created using realistic patterns for educational practice.

Ever wondered how much Netflix, sleep, or TikTok scrolling affects your grades? 👀 This dataset simulates 1,000 students' daily habits—from study time to mental health—and compares them to final exam scores. It's like spying on your GPA through the lens of lifestyle. Perfect for EDA, ML practice, or just vibing with data while pretending to be productive.

## Dataset Information

- **Number of Rows**: 1,000
- **Number of Columns**: 16
- **Missing Values**: None
- **Target Variable**: `exam_score` (continuous, regression problem)
- **Problem Type**: Regression (predicting exam scores based on lifestyle factors)

## Dataset Columns

### 1. student_id
- **Type**: Categorical (String)
- **Description**: Unique identifier for each student (e.g., S1000, S1001, etc.).

### 2. age
- **Type**: Numeric (Integer)
- **Description**: Age of the student in years.
- **Range**: Typically 18-24 (college/university age range)

### 3. gender
- **Type**: Categorical
- **Description**: Gender of the student.
- **Values**: Female, Male, Other
- **Distribution**:
  - Female: 481 (48.1%)
  - Male: 477 (47.7%)
  - Other: 42 (4.2%)

### 4. study_hours_per_day
- **Type**: Numeric (Float)
- **Description**: Number of hours the student studies per day.
- **Range**: 0.0 - 8.3 hours
- **Mean**: 3.55 hours

### 5. social_media_hours
- **Type**: Numeric (Float)
- **Description**: Number of hours spent on social media per day (e.g., TikTok, Instagram, Facebook, Twitter).

### 6. netflix_hours
- **Type**: Numeric (Float)
- **Description**: Number of hours spent watching Netflix or streaming services per day.

### 7. part_time_job
- **Type**: Categorical (Binary)
- **Description**: Whether the student has a part-time job.
- **Values**: Yes, No
- **Distribution**:
  - No: 785 (78.5%)
  - Yes: 215 (21.5%)

### 8. attendance_percentage
- **Type**: Numeric (Float)
- **Description**: Percentage of classes attended by the student.
- **Range**: 0-100%

### 9. sleep_hours
- **Type**: Numeric (Float)
- **Description**: Average number of hours of sleep per night.
- **Range**: 3.2 - 10.0 hours
- **Mean**: 6.47 hours

### 10. diet_quality
- **Type**: Categorical
- **Description**: Quality of the student's diet.
- **Values**: Poor, Fair, Good
- **Distribution**:
  - Fair: 437 (43.7%)
  - Good: 378 (37.8%)
  - Poor: 185 (18.5%)

### 11. exercise_frequency
- **Type**: Numeric (Integer)
- **Description**: Frequency of exercise per week (number of times).

### 12. parental_education_level
- **Type**: Categorical
- **Description**: Highest level of education completed by parents.
- **Values**: None, High School, Bachelor, Master
- **Distribution**:
  - High School: 392 (39.2%)
  - Bachelor: 350 (35.0%)
  - Master: 167 (16.7%)
  - None: 91 (9.1%)

### 13. internet_quality
- **Type**: Categorical
- **Description**: Quality of internet connection available to the student.
- **Values**: Poor, Average, Good
- **Distribution**:
  - Good: 447 (44.7%)
  - Average: 391 (39.1%)
  - Poor: 162 (16.2%)

### 14. mental_health_rating
- **Type**: Numeric (Integer)
- **Description**: Self-reported mental health rating on a scale of 1-10, where higher values indicate better mental health.
- **Range**: 1-10
- **Mean**: 5.44

### 15. extracurricular_participation
- **Type**: Categorical (Binary)
- **Description**: Whether the student participates in extracurricular activities (sports, clubs, etc.).
- **Values**: Yes, No
- **Distribution**:
  - No: 682 (68.2%)
  - Yes: 318 (31.8%)

### 16. exam_score
- **Type**: Numeric (Float) - **Target Variable**
- **Description**: Final exam score (out of 100).
- **Range**: 18.4 - 100.0
- **Mean**: 69.6
- **Median**: 70.5

## Data Characteristics

### Target Variable Distribution
- **Range**: 18.4 to 100.0
- **Mean**: 69.6
- **Median**: 70.5
- The distribution appears relatively balanced around the mean, suitable for regression analysis.

### Data Quality
- **No Missing Values**: The dataset is complete with no missing values across all 16 columns.
- **Data Types**: Mix of numeric (continuous and discrete) and categorical variables.
- **Synthetic Data**: This is simulated data created for educational purposes with realistic patterns.

### Feature Categories
- **Demographic**: age, gender
- **Academic**: study_hours_per_day, attendance_percentage, exam_score (target)
- **Lifestyle**: sleep_hours, diet_quality, exercise_frequency
- **Digital Habits**: social_media_hours, netflix_hours, internet_quality
- **Socioeconomic**: parental_education_level, part_time_job
- **Wellness**: mental_health_rating, extracurricular_participation

## Usage

This dataset is suitable for:

1. **Regression Analysis**: Predict exam scores based on lifestyle and academic factors.
2. **Exploratory Data Analysis (EDA)**: Understand relationships between lifestyle habits and academic performance.
3. **Machine Learning Practice**: Build regression models (linear regression, random forest, gradient boosting, neural networks).
4. **Clustering**: Identify student groups with similar lifestyle patterns.
5. **Data Visualization**: Create compelling visualizations showing correlations between habits and grades.
6. **Feature Engineering**: Create derived features and interaction terms.
7. **Educational Research**: Study the impact of various factors on student performance.

## Considerations

1. **Synthetic Data**: This dataset is simulated and created for educational purposes. Results should not be generalized to real-world populations.

2. **Correlation vs. Causation**: The dataset shows correlations between lifestyle factors and exam scores, but does not establish causation. Be cautious when interpreting results.

3. **Feature Scaling**: For machine learning models, consider scaling numeric features (age, study hours, sleep hours, etc.) especially if using distance-based algorithms or neural networks.

4. **Categorical Encoding**: Categorical variables (gender, diet_quality, parental_education_level, etc.) may need encoding (one-hot encoding, label encoding, or ordinal encoding depending on the model).

5. **Feature Interactions**: Consider creating interaction features (e.g., study_hours × sleep_hours, social_media_hours × netflix_hours) as they may capture complex relationships.

6. **Outliers**: Check for outliers in numeric features, especially in exam_score, study_hours_per_day, and sleep_hours.

7. **Multicollinearity**: Some features may be correlated (e.g., social_media_hours and netflix_hours). Consider checking for multicollinearity if using linear models.

8. **Class Imbalance**: While not directly applicable to regression, check for imbalanced distributions in categorical features that might affect model performance.

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
2. What is the impact of sleep duration on academic performance?
3. Do social media and Netflix consumption negatively affect grades?
4. How does mental health rating relate to exam performance?
5. Does having a part-time job impact academic performance?
6. What role does attendance percentage play in exam scores?
7. How do lifestyle factors (diet, exercise) influence academic outcomes?
8. Does parental education level correlate with student performance?
9. What is the optimal balance between study time and leisure activities?
10. How do multiple factors interact to predict exam scores?

## Feature Engineering Ideas

1. **Total Screen Time**: `social_media_hours + netflix_hours` (total entertainment screen time)
2. **Study-to-Screen Ratio**: `study_hours_per_day / (social_media_hours + netflix_hours + 1)` (avoid division by zero)
3. **Sleep Quality Indicator**: Categorize sleep_hours (Insufficient: <6, Adequate: 6-8, Excessive: >8)
4. **Study Efficiency**: `exam_score / study_hours_per_day` (score per study hour)
5. **Lifestyle Score**: Combine diet_quality, exercise_frequency, and sleep_hours into a composite health score
6. **Digital Detox Score**: Inverse of total screen time (lower screen time = higher score)
7. **Academic Engagement**: `study_hours_per_day + attendance_percentage/10` (weighted combination)
8. **Stress Indicator**: Inverse of mental_health_rating (lower rating = higher stress)
9. **Socioeconomic Status**: Encode parental_education_level as ordinal (None=0, High School=1, Bachelor=2, Master=3)
10. **Work-Study Balance**: Interaction between part_time_job and study_hours_per_day
11. **Wellness Index**: Combine mental_health_rating, exercise_frequency, and diet_quality
12. **Age Groups**: Create age bins (18-19, 20-21, 22-23, 24+)

## Model Suggestions

### Regression Models
- **Linear Regression**: Baseline model, interpretable coefficients
- **Ridge/Lasso Regression**: Handle multicollinearity and feature selection
- **Random Forest**: Capture non-linear relationships and feature interactions
- **Gradient Boosting** (XGBoost, LightGBM, CatBoost): High performance, handles mixed data types
- **Neural Networks**: Complex non-linear relationships
- **Support Vector Regression (SVR)**: Non-linear relationships with kernel tricks

### Clustering Models
- **K-Means**: Identify student lifestyle clusters
- **Hierarchical Clustering**: Understand cluster relationships
- **DBSCAN**: Find density-based student groups

## Visualization Ideas

1. **Correlation Heatmap**: Show correlations between all numeric features
2. **Scatter Plots**: Study hours vs. exam score, sleep hours vs. exam score
3. **Box Plots**: Exam scores by diet quality, gender, part-time job status
4. **Distribution Plots**: Histograms of exam scores, study hours, sleep hours
5. **Pair Plots**: Relationships between key features
6. **Violin Plots**: Distribution of exam scores across different categories
7. **3D Scatter Plots**: Study hours, sleep hours, and exam scores
8. **Feature Importance**: From tree-based models

## Educational Context

This dataset is designed for:
- **Machine Learning Courses**: Regression, feature engineering, model evaluation
- **Data Science Projects**: End-to-end analysis from EDA to model deployment
- **Statistics Courses**: Correlation analysis, regression modeling
- **Educational Research**: Understanding factors affecting student performance (with caveat that data is synthetic)

## Disclaimer

⚠️ **Important**: This dataset contains synthetic/simulated data created for educational and practice purposes. The relationships and patterns are designed to be realistic but should not be used to draw conclusions about real student populations or to make policy decisions. For real-world applications, use validated educational datasets from reputable sources.

---

**Note**: This dataset is perfect for learning and practicing data science skills, but remember—correlation does not imply causation! Use it to build your skills in EDA, feature engineering, and machine learning modeling.

