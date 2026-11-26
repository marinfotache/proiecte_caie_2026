# Customer Churn Dataset

## Overview

This dataset is a telecommunications customer churn dataset taken from the Penn Machine Learning Benchmark. The dataset contains customer account information and usage patterns to predict customer churn (whether a customer will leave the service provider).

## Source

**Dataset**: Penn Machine Learning Benchmark  
**Note**: This ARFF file is automatically generated. The data types of attributes are inferred from the data. In particular, this means there is some uncertainty as to whether an attribute truly is categorical, numerical, or ordinal.

## Dataset Information

- **Total Instances**: 5,000
- **Number of Attributes**: 20 input attributes + 1 target attribute (class)
- **Data Format**: CSV (converted from ARFF format)
- **Task**: Binary classification (predicting customer churn)

## Target Variable

**class** (binary)
- `0`: Customer did not churn (stayed with the service)
- `1`: Customer churned (left the service)

### Class Distribution
- **No Churn (0)**: 4,293 instances (85.86%)
- **Churn (1)**: 707 instances (14.14%)

**Note**: The dataset is imbalanced, with significantly more non-churning customers than churning customers. This is typical for churn prediction problems.

## Variable Descriptions

### Customer Account Information

1. **state** (numeric)
   - State code (encoded as numeric)
   - Represents the customer's state of residence

2. **account_length** (numeric)
   - Number of months the customer has been with the current service provider
   - Measured in months

3. **area_code** (categorical)
   - Area code of the customer's phone number
   - Values: `408`, `415`, `510`

4. **phone_number** (numeric)
   - Customer's phone number (encoded as numeric)
   - **Note**: This is likely an identifier and may not be useful for prediction

### Service Plans

5. **international_plan** (binary)
   - Whether the customer has an international calling plan
   - Values: `0` (no), `1` (yes)
   - Distribution: 4,527 without plan (90.54%), 473 with plan (9.46%)

6. **voice_mail_plan** (binary)
   - Whether the customer has a voice mail plan
   - Values: `0` (no), `1` (yes)
   - Distribution: 3,677 without plan (73.54%), 1,323 with plan (26.46%)

7. **number_vmail_messages** (numeric)
   - Number of voice mail messages
   - Continuous variable

### Daytime Usage (Day)

8. **total_day_minutes** (numeric)
   - Total minutes of calls during the day
   - Measured in minutes

9. **total_day_calls** (numeric)
   - Total number of calls made during the day
   - Count variable

10. **total_day_charge** (numeric)
    - Total charge for daytime calls
    - Measured in currency units

### Evening Usage (Eve)

11. **total_eve_minutes** (numeric)
    - Total minutes of calls during the evening
    - Measured in minutes

12. **total_eve_calls** (numeric)
    - Total number of calls made during the evening
    - Count variable

13. **total_eve_charge** (numeric)
    - Total charge for evening calls
    - Measured in currency units

### Night Usage (Night)

14. **total_night_minutes** (numeric)
    - Total minutes of calls during the night
    - Measured in minutes

15. **total_night_calls** (numeric)
    - Total number of calls made during the night
    - Count variable

16. **total_night_charge** (numeric)
    - Total charge for night calls
    - Measured in currency units

### International Usage

17. **total_intl_minutes** (numeric)
    - Total minutes of international calls
    - Measured in minutes

18. **total_intl_calls** (numeric)
    - Total number of international calls made
    - Count variable

19. **total_intl_charge** (numeric)
    - Total charge for international calls
    - Measured in currency units

### Customer Service

20. **number_customer_service_calls** (categorical/ordinal)
    - Number of customer service calls made by the customer
    - Values: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`
    - **Important**: Higher numbers of customer service calls are often correlated with churn

### Target Variable

21. **class** (binary)
    - Customer churn indicator
    - Values: `0` (no churn), `1` (churn)
    - This is the target variable for prediction

## Data Characteristics

### Usage Patterns

The dataset captures customer usage across different time periods:
- **Daytime**: Business hours usage
- **Evening**: After-work hours usage
- **Night**: Late night/early morning usage
- **International**: International calling patterns

For each time period, the dataset includes:
- Minutes of usage
- Number of calls
- Charges incurred

### Key Insights

1. **Service Plans**: The dataset includes information about international and voice mail plans, which can be important predictors of churn.

2. **Customer Service Calls**: The number of customer service calls is often a strong indicator of customer dissatisfaction and potential churn.

3. **Usage Patterns**: Changes in usage patterns (minutes, calls, charges) across different time periods can indicate customer behavior changes that may lead to churn.

4. **Account Length**: The length of time a customer has been with the service provider can be a factor in churn prediction.

## Usage

This dataset is suitable for:

- **Binary Classification**: Predicting customer churn (class: 0 or 1)
- **Customer Retention Analysis**: Understanding factors that lead to customer churn
- **Feature Engineering**: Creating derived features from usage patterns
- **Imbalanced Classification**: Practicing techniques for handling imbalanced datasets
- **Business Analytics**: Analyzing customer behavior and service usage patterns
- **Machine Learning Benchmarking**: Testing classification algorithms on a real-world business problem

## Important Considerations

1. **Class Imbalance**: The dataset is imbalanced (85.86% no churn vs. 14.14% churn). Consider using techniques such as:
   - Resampling (oversampling minority class or undersampling majority class)
   - Class weights in algorithms
   - Appropriate evaluation metrics (precision, recall, F1-score, ROC-AUC)

2. **Phone Number**: The `phone_number` attribute is likely an identifier and may not be useful for prediction. Consider excluding it from models.

3. **State Encoding**: The `state` attribute is encoded as numeric, but it may be more appropriately treated as categorical.

4. **Data Type Uncertainty**: As noted in the source, data types are inferred and there may be uncertainty about whether attributes are truly categorical, numerical, or ordinal.

5. **Feature Relationships**: Usage minutes, calls, and charges are likely correlated. Consider feature selection or dimensionality reduction techniques.

6. **Customer Service Calls**: This is often one of the strongest predictors of churn - customers with more service calls are more likely to churn.

## Evaluation Metrics

For imbalanced classification problems like churn prediction, consider using:
- **Precision**: Of predicted churns, how many actually churned?
- **Recall**: Of actual churns, how many did we correctly predict?
- **F1-Score**: Harmonic mean of precision and recall
- **ROC-AUC**: Area under the ROC curve
- **Confusion Matrix**: Detailed breakdown of predictions vs. actuals

## Related Resources

- **Penn Machine Learning Benchmark**: Source of the original dataset
- **Churn Prediction**: Common problem in customer relationship management (CRM)
- **Telecommunications Analytics**: Industry-specific applications of predictive modeling

## Files

- `churn.csv`: Dataset in CSV format with proper column headers
- `churn.arff`: Original dataset in ARFF (Attribute-Relation File Format)

