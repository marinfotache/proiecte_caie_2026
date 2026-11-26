# Vehicle Insurance Prediction Dataset

## Overview

This dataset is from an Insurance company that has provided Health Insurance to its customers. The goal is to build a model to predict whether policyholders (customers) from the past year will also be interested in Vehicle Insurance provided by the company.

An insurance policy is an arrangement by which a company undertakes to provide a guarantee of compensation for specified loss, damage, illness, or death in return for the payment of a specified premium. A premium is a sum of money that the customer needs to pay regularly to an insurance company for this guarantee.

For example, you may pay a premium of Rs. 5000 each year for a health insurance cover of Rs. 200,000/- so that if, God forbid, you fall ill and need to be hospitalised in that year, the insurance provider company will bear the cost of hospitalisation etc. for upto Rs. 200,000. Now if you are wondering how can company bear such high hospitalisation cost when it charges a premium of only Rs. 5000/-, that is where the concept of probabilities comes in picture. For example, like you, there may be 100 customers who would be paying a premium of Rs. 5000 every year, but only a few of them (say 2-3) would get hospitalised that year and not everyone. This way everyone shares the risk of everyone else.

Just like medical insurance, there is vehicle insurance where every year customer needs to pay a premium of certain amount to insurance provider company so that in case of unfortunate accident by the vehicle, the insurance provider company will provide a compensation (called 'sum assured') to the customer.

Building a model to predict whether a customer would be interested in Vehicle Insurance is extremely helpful for the company because it can then accordingly plan its communication strategy to reach out to those customers and optimise its business model and revenue.

## Dataset Information

- **Number of Rows**: 381,109
- **Number of Columns**: 12
- **Missing Values**: None
- **Target Variable**: `Response` (binary classification problem)
- **Problem Type**: Binary Classification (predicting customer interest in Vehicle Insurance)
- **Business Objective**: Identify customers likely to be interested in Vehicle Insurance for targeted marketing campaigns

## Dataset Columns

### 1. id
- **Type**: Numeric (Integer)
- **Description**: Unique ID for the customer.
- **Note**: This is an identifier and should typically be excluded from model training.

### 2. Gender
- **Type**: Categorical
- **Description**: Gender of the customer.
- **Values**: Male, Female
- **Distribution**:
  - Male: 206,089 (54.1%)
  - Female: 175,020 (45.9%)

### 3. Age
- **Type**: Numeric (Integer)
- **Description**: Age of the customer.
- **Range**: 20 - 85 years
- **Mean**: 38.82 years
- **Median**: 36 years

### 4. Driving_License
- **Type**: Binary (Numeric)
- **Description**: Whether the customer has a driving license.
- **Values**: 
  - 0: Customer does not have DL
  - 1: Customer already has DL
- **Distribution**:
  - 1 (Has DL): 380,297 (99.8%)
  - 0 (No DL): 812 (0.2%)

### 5. Region_Code
- **Type**: Numeric (Float)
- **Description**: Unique code for the region of the customer.
- **Unique Values**: 53 different region codes
- **Note**: This is a categorical variable encoded as numeric. Consider treating it as categorical or using target encoding.

### 6. Previously_Insured
- **Type**: Binary (Numeric)
- **Description**: Whether the customer already has Vehicle Insurance.
- **Values**:
  - 0: Customer doesn't have Vehicle Insurance
  - 1: Customer already has Vehicle Insurance
- **Distribution**:
  - 0 (Not Previously Insured): 206,481 (54.2%)
  - 1 (Previously Insured): 174,628 (45.8%)
- **Note**: This is a critical feature - customers who already have vehicle insurance are less likely to be interested.

### 7. Vehicle_Age
- **Type**: Categorical (Ordinal)
- **Description**: Age of the Vehicle.
- **Values**: "< 1 Year", "1-2 Year", "> 2 Years"
- **Distribution**:
  - 1-2 Year: 200,316 (52.5%)
  - < 1 Year: 164,786 (43.2%)
  - > 2 Years: 16,007 (4.2%)

### 8. Vehicle_Damage
- **Type**: Binary (Categorical)
- **Description**: Whether the customer got his/her vehicle damaged in the past.
- **Values**:
  - Yes: Customer got his/her vehicle damaged in the past
  - No: Customer didn't get his/her vehicle damaged in the past
- **Distribution**:
  - Yes: 192,413 (50.5%)
  - No: 188,696 (49.5%)
- **Note**: Customers with vehicle damage history may be more likely to be interested in insurance.

### 9. Annual_Premium
- **Type**: Numeric (Float)
- **Description**: The amount customer needs to pay as premium in the year.
- **Range**: 2,630 - 540,165
- **Mean**: 30,564.39
- **Median**: 31,669
- **Note**: This is a key financial feature. Consider checking for outliers and potentially log-transforming if the distribution is skewed.

### 10. Policy_Sales_Channel
- **Type**: Numeric (Float)
- **Description**: Anonymized Code for the channel of outreaching to the customer (e.g., Different Agents, Over Mail, Over Phone, In Person, etc.).
- **Unique Values**: 155 different sales channels
- **Note**: This is a categorical variable encoded as numeric. Consider treating it as categorical or using target encoding/embedding.

### 11. Vintage
- **Type**: Numeric (Integer)
- **Description**: Number of Days, Customer has been associated with the company.
- **Range**: 10 - 299 days
- **Mean**: 154.35 days
- **Note**: Measures customer loyalty/tenure with the company.

### 12. Response
- **Type**: Binary (Numeric) - **Target Variable**
- **Description**: Whether the customer is interested in Vehicle Insurance.
- **Values**:
  - 1: Customer is interested
  - 0: Customer is not interested
- **Distribution**:
  - 0 (Not Interested): 334,399 (87.7%)
  - 1 (Interested): 46,710 (12.3%)
- **Note**: **Severe class imbalance** - this is a critical consideration for model training and evaluation.

## Data Characteristics

### Target Variable Distribution
- **Class Imbalance**: Severe imbalance with only 12.3% positive class (interested customers)
- **Implications**: 
  - Accuracy alone is not a good metric (a naive model predicting "0" would achieve 87.7% accuracy)
  - Use appropriate metrics: Precision, Recall, F1-Score, ROC-AUC, PR-AUC
  - Consider resampling techniques: SMOTE, undersampling, or class weighting
  - Focus on identifying the minority class (interested customers)

### Data Quality
- **No Missing Values**: The dataset is complete with no missing values across all 12 columns.
- **Data Types**: Mix of numeric (continuous and discrete) and categorical variables.
- **High Cardinality**: Region_Code (53 unique values) and Policy_Sales_Channel (155 unique values) have high cardinality.

### Feature Categories
- **Demographic**: Gender, Age
- **License/Vehicle**: Driving_License, Vehicle_Age, Vehicle_Damage
- **Insurance History**: Previously_Insured
- **Financial**: Annual_Premium
- **Geographic**: Region_Code
- **Operational**: Policy_Sales_Channel, Vintage
- **Target**: Response

## Business Context

### Problem Statement
The insurance company wants to:
1. **Identify potential customers** for Vehicle Insurance from their existing Health Insurance customer base
2. **Optimize marketing campaigns** by targeting customers most likely to be interested
3. **Improve conversion rates** and reduce marketing costs
4. **Increase revenue** through cross-selling Vehicle Insurance

### Key Business Insights
- Customers who **already have Vehicle Insurance** (Previously_Insured = 1) are likely **not interested** in purchasing again
- Customers with **vehicle damage history** (Vehicle_Damage = Yes) may be more likely to be interested
- **Annual Premium** may indicate willingness to pay for additional insurance
- **Vintage** (customer tenure) may indicate loyalty and likelihood to purchase additional products

## Usage

This dataset is suitable for:

1. **Binary Classification**: Predict customer interest in Vehicle Insurance
2. **Customer Segmentation**: Identify customer segments most likely to be interested
3. **Marketing Campaign Optimization**: Target customers for vehicle insurance campaigns
4. **Feature Importance Analysis**: Understand which factors drive customer interest
5. **Machine Learning Practice**: Handle class imbalance, high cardinality features, and business metrics
6. **Business Analytics**: Analyze customer behavior and insurance purchasing patterns

## Considerations

### 1. Class Imbalance
- **Severe imbalance** (87.7% vs 12.3%) requires special handling:
  - Use appropriate evaluation metrics (F1-score, ROC-AUC, PR-AUC)
  - Apply resampling techniques (SMOTE, ADASYN, undersampling)
  - Use class weights in models
  - Consider cost-sensitive learning

### 2. High Cardinality Features
- **Region_Code** (53 values) and **Policy_Sales_Channel** (155 values) have high cardinality:
  - Consider target encoding (mean encoding)
  - Use frequency encoding
  - Group rare categories
  - Use embedding layers in neural networks

### 3. Feature Engineering
- **Age Groups**: Create age bins (e.g., 20-30, 31-40, 41-50, 51+)
- **Premium Categories**: Bin Annual_Premium into categories
- **Vintage Groups**: Categorize customer tenure
- **Interaction Features**: 
  - Vehicle_Damage × Previously_Insured
  - Age × Annual_Premium
  - Vehicle_Age × Vehicle_Damage

### 4. Data Preprocessing
- **Categorical Encoding**: 
  - Gender, Vehicle_Age, Vehicle_Damage: One-hot encoding or label encoding
  - Region_Code, Policy_Sales_Channel: Target encoding or frequency encoding
- **Feature Scaling**: Scale numeric features (Age, Annual_Premium, Vintage) for distance-based algorithms
- **Outlier Handling**: Check for outliers in Annual_Premium (max: 540,165 seems high)

### 5. Business Logic
- **Previously_Insured = 1**: These customers likely don't need another policy. Consider filtering or creating a separate model.
- **Driving_License = 0**: Very few customers (0.2%) - may not be useful for prediction.

### 6. Evaluation Metrics
- **Primary Metrics**: 
  - Precision (minimize false positives - don't waste marketing budget)
  - Recall (maximize true positives - don't miss potential customers)
  - F1-Score (balance between precision and recall)
  - ROC-AUC (overall model performance)
  - PR-AUC (better for imbalanced data)
- **Business Metrics**:
  - Conversion rate
  - Cost per acquisition
  - Revenue per customer

## Evaluation Metrics

For binary classification with class imbalance, consider:

### Primary Metrics
- **Precision**: Proportion of predicted positives that are actually positive (important for marketing budget)
- **Recall (Sensitivity)**: Proportion of actual positives correctly identified (important for not missing customers)
- **F1-Score**: Harmonic mean of precision and recall
- **ROC-AUC**: Area under the ROC curve (overall discriminative ability)
- **PR-AUC**: Area under the Precision-Recall curve (better for imbalanced data)

### Additional Metrics
- **Confusion Matrix**: Visualize true positives, false positives, true negatives, false negatives
- **Specificity**: Proportion of actual negatives correctly identified
- **Balanced Accuracy**: Average of sensitivity and specificity

### Business Metrics
- **Conversion Rate**: Percentage of targeted customers who purchase
- **Lift**: Improvement over random targeting
- **Cost per Acquisition**: Marketing cost per converted customer

## Model Suggestions

### Classification Models
- **Logistic Regression**: Baseline model, interpretable coefficients
- **Random Forest**: Handle non-linear relationships, feature importance
- **Gradient Boosting** (XGBoost, LightGBM, CatBoost): High performance, handles mixed data types, built-in handling of categorical features
- **Neural Networks**: Complex non-linear relationships, embedding layers for high cardinality features
- **Ensemble Methods**: Combine multiple models for better performance

### Handling Class Imbalance
- **SMOTE**: Synthetic Minority Oversampling Technique
- **ADASYN**: Adaptive Synthetic Sampling
- **Class Weights**: Adjust class weights in models
- **Threshold Tuning**: Optimize classification threshold based on business needs

## Feature Engineering Ideas

1. **Age Groups**: Categorize age into bins (Young: 20-30, Middle: 31-50, Senior: 51+)
2. **Premium Categories**: Bin Annual_Premium (Low, Medium, High)
3. **Vintage Groups**: Categorize customer tenure (New: <100 days, Medium: 100-200, Long: >200)
4. **Risk Score**: Combine Vehicle_Damage, Vehicle_Age, and Previously_Insured
5. **Customer Value**: Interaction between Annual_Premium and Vintage
6. **Region Clustering**: Group similar Region_Codes based on response rates
7. **Channel Effectiveness**: Calculate conversion rates by Policy_Sales_Channel
8. **Vehicle_Age Encoding**: Ordinal encoding (< 1 Year = 0, 1-2 Year = 1, > 2 Years = 2)
9. **Interaction Features**:
   - Vehicle_Damage × Previously_Insured
   - Age × Annual_Premium
   - Vehicle_Age × Vehicle_Damage
   - Gender × Age
10. **Target Encoding**: For Region_Code and Policy_Sales_Channel (mean response rate by category)

## Research Questions

Potential research questions to explore:
1. What demographic factors (age, gender) influence interest in Vehicle Insurance?
2. How does having a previous vehicle insurance policy affect interest?
3. What is the relationship between vehicle damage history and insurance interest?
4. How does annual premium correlate with customer interest?
5. Which sales channels are most effective for vehicle insurance?
6. How does customer tenure (Vintage) relate to interest in additional products?
7. Are there regional differences in insurance interest?
8. What combination of factors best predicts customer interest?
9. How can we balance precision and recall for marketing campaigns?
10. What is the optimal targeting strategy to maximize ROI?

## Business Applications

### Marketing Campaign Optimization
- **Targeted Campaigns**: Focus marketing efforts on customers with high predicted interest
- **Budget Allocation**: Allocate marketing budget based on predicted conversion probability
- **Channel Selection**: Identify most effective sales channels for vehicle insurance
- **Personalization**: Customize messaging based on customer characteristics

### Customer Segmentation
- **High-Value Segments**: Identify customer segments most likely to purchase
- **Risk Profiling**: Understand risk factors that drive insurance interest
- **Cross-Selling Strategy**: Develop strategies for cross-selling to health insurance customers

### Business Intelligence
- **Conversion Analysis**: Understand factors driving insurance purchases
- **Customer Behavior**: Analyze patterns in insurance purchasing behavior
- **Market Insights**: Gain insights into customer preferences and needs

## Important Notes

1. **Class Imbalance**: This is the most critical consideration. Standard accuracy metrics are misleading.
2. **Business Logic**: Customers with Previously_Insured = 1 are unlikely to be interested. Consider this in feature engineering.
3. **High Cardinality**: Region_Code and Policy_Sales_Channel require special encoding techniques.
4. **Outliers**: Check Annual_Premium for outliers (max value: 540,165 seems unusually high).
5. **Feature Importance**: Understanding which features drive predictions is crucial for business insights.
6. **Cost-Benefit Analysis**: Consider the cost of false positives (wasted marketing) vs. false negatives (missed opportunities).

## Data Split Recommendation

For model development:
- **Train Set**: 70-80% of data
- **Validation Set**: 10-15% of data (for hyperparameter tuning)
- **Test Set**: 10-15% of data (for final evaluation)
- **Stratified Split**: Ensure class distribution is maintained across splits

## Citation

If you use this dataset in your research or projects, please acknowledge the source appropriately.

---

**Note**: This dataset is designed for educational and business analytics purposes. When building models, prioritize business metrics (conversion rate, ROI) alongside statistical metrics. The goal is not just high accuracy, but actionable insights that drive business value.

