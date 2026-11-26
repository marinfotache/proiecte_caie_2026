# Stroke Prediction Dataset

## Overview

According to the World Health Organization (WHO), **stroke is the 2nd leading cause of death globally**, responsible for approximately **11% of total deaths**. This dataset is used to predict whether a patient is likely to get stroke based on input parameters like gender, age, various diseases, and smoking status. Each row in the data provides relevant information about the patient.

## Context

Stroke is a serious medical condition that occurs when blood supply to part of the brain is interrupted or reduced, preventing brain tissue from getting oxygen and nutrients. Early prediction and identification of stroke risk factors can help in prevention and timely intervention.

## Dataset Information

- **Total Instances**: 5,110
- **Number of Attributes**: 11 input features + 1 target variable
- **Data Format**: CSV
- **Task**: Binary classification (predicting stroke occurrence)

## Target Variable

**stroke** (binary)
- `1`: Patient had a stroke
- `0`: Patient did not have a stroke

### Class Distribution
- **No Stroke (0)**: 4,861 instances (95.1%)
- **Stroke (1)**: 249 instances (4.9%)

**⚠️ Critical Note**: The dataset is **highly imbalanced**, with stroke cases representing less than 5% of the data. This is typical for medical datasets where the condition of interest is relatively rare.

## Variable Descriptions

### Identification

1. **id** (numeric)
   - Unique identifier for each patient
   - Patient ID number

### Demographic Variables

2. **gender** (categorical)
   - Gender of the patient
   - Values: `Male`, `Female`, `Other`
   - Distribution: Female (2,994, 58.6%), Male (2,115, 41.4%), Other (1, 0.02%)

3. **age** (numeric)
   - Age of the patient
   - Measured in years
   - Range: 0.08 to 82 years
   - **Note**: Dataset includes children (age < 18)

4. **ever_married** (categorical)
   - Marital status
   - Values: `No`, `Yes`
   - Indicates whether the patient has ever been married

5. **work_type** (categorical)
   - Type of work
   - Values:
     - `children`: For children/students
     - `Govt_job`: Government job
     - `Never_worked`: Never worked
     - `Private`: Private sector employment
     - `Self-employed`: Self-employed
   - Distribution: Private (2,925, 57.2%), Self-employed (819, 16.0%), Govt_job (657, 12.9%), children (687, 13.4%), Never_worked (22, 0.4%)

6. **Residence_type** (categorical)
   - Type of residence
   - Values: `Rural`, `Urban`
   - Indicates whether the patient lives in a rural or urban area

### Medical Conditions

7. **hypertension** (binary)
   - Hypertension (high blood pressure) status
   - Values: `0` (no hypertension), `1` (has hypertension)
   - Hypertension is a major risk factor for stroke

8. **heart_disease** (binary)
   - Heart disease status
   - Values: `0` (no heart disease), `1` (has heart disease)
   - Heart disease increases stroke risk

### Laboratory and Health Metrics

9. **avg_glucose_level** (numeric)
   - Average glucose level in blood
   - Measured in mg/dl (milligrams per deciliter)
   - Elevated glucose levels (diabetes/prediabetes) are a stroke risk factor
   - Normal fasting glucose: typically 70-100 mg/dl
   - Prediabetes: 100-125 mg/dl
   - Diabetes: ≥126 mg/dl

10. **bmi** (numeric/character)
    - Body Mass Index
    - Calculated as weight (kg) / height (m)²
    - **Missing Values**: 201 instances have "N/A" (3.9% of dataset)
    - Normal BMI: 18.5-24.9
    - Overweight: 25-29.9
    - Obese: ≥30

### Lifestyle Factors

11. **smoking_status** (categorical)
    - Smoking status of the patient
    - Values:
      - `never smoked`: Patient has never smoked
      - `formerly smoked`: Patient used to smoke but has quit
      - `smokes`: Patient currently smokes
      - `Unknown`: Information is unavailable for this patient
    - Distribution: never smoked (1,892, 37.0%), Unknown (1,544, 30.2%), formerly smoked (885, 17.3%), smokes (789, 15.4%)
    - **Note**: "Unknown" means that the information is unavailable for this patient

### Target Variable

12. **stroke** (binary)
    - Stroke occurrence
    - Values: `1` (patient had a stroke), `0` (patient did not have a stroke)
    - This is the target variable for prediction

## Data Characteristics

### Class Imbalance

The dataset is **highly imbalanced**:
- Only 4.9% of patients had a stroke
- This reflects the real-world prevalence of stroke
- Requires special handling techniques

### Missing Values

- **BMI**: 201 instances (3.9%) have missing values, represented as "N/A"
- **Smoking Status**: 1,544 instances (30.2%) have "Unknown" status
- Other variables appear to be complete

### Age Distribution

- Range: 0.08 to 82 years
- Includes children (work_type = "children")
- Age is a significant risk factor for stroke (risk increases with age)

## Usage

This dataset is suitable for:

- **Binary Classification**: Predicting stroke occurrence based on patient characteristics
- **Risk Stratification**: Identifying patients at high risk for stroke
- **Feature Importance Analysis**: Understanding which factors are most predictive of stroke
- **Medical Research**: Studying stroke risk factors
- **Healthcare Analytics**: Developing predictive models for stroke prevention
- **Educational Purposes**: Teaching classification algorithms with imbalanced medical data

## Important Considerations

1. **Severe Class Imbalance**: The dataset is highly imbalanced (95.1% vs 4.9%). Consider:
   - **Resampling techniques**: 
     - Oversampling minority class (SMOTE, ADASYN)
     - Undersampling majority class
     - Combination approaches
   - **Evaluation metrics**: 
     - Precision, Recall, F1-score (especially recall for medical applications)
     - ROC-AUC, Precision-Recall AUC
     - Confusion matrix
   - **Class weights**: Using class weights in algorithms
   - **Cost-sensitive learning**: Penalizing misclassification of stroke cases more heavily

2. **Missing Values**: 
   - **BMI**: 201 missing values (3.9%). Consider:
     - Imputation (mean, median, mode, or model-based)
     - Creating a "BMI_missing" indicator variable
     - Removing instances with missing BMI (if acceptable)
   - **Smoking Status**: "Unknown" category (30.2%). Consider:
     - Treating "Unknown" as a separate category
     - Imputation based on other features
     - Analyzing patterns in unknown smoking status

3. **Age Range**: Dataset includes children (age 0.08 years). Consider:
   - Stroke in children is rare and may have different risk factors
   - Analyzing adults separately (age ≥ 18)
   - Creating age groups (children, adults, elderly)
   - Age is a strong risk factor (stroke risk increases significantly with age)

4. **Medical Context**: 
   - This dataset should not replace professional medical diagnosis
   - Always consult healthcare professionals for actual diagnosis
   - Consider regulatory and ethical implications for medical AI applications

5. **Feature Engineering**: Consider creating:
   - Age groups (e.g., <18, 18-40, 41-60, 61-80, >80)
   - BMI categories (underweight, normal, overweight, obese)
   - Glucose level categories (normal, prediabetes, diabetes)
   - Risk score composites
   - Interaction terms (e.g., age × hypertension, age × heart_disease)

6. **Data Quality**: 
   - Verify reasonable ranges for continuous variables
   - Check for outliers in age, glucose, BMI
   - Validate categorical variable encodings
   - Note: BMI stored as character with "N/A" values (needs conversion)

7. **Work Type**: The "children" category indicates pediatric patients. Consider:
   - Pediatric strokes are rare and may need separate analysis
   - Different risk factors may apply to children
   - May want to filter or analyze separately

## Evaluation Metrics

For binary classification with severe imbalance, prioritize:

- **Recall (Sensitivity)**: Of actual stroke cases, how many did we correctly identify?
  - **Critical for medical applications** - missing a stroke case can be fatal
  - Aim for high recall to minimize false negatives

- **Precision**: Of predicted stroke cases, how many actually had a stroke?
  - Important to avoid unnecessary alarm/medical intervention

- **F1-Score**: Harmonic mean of precision and recall
  - Balanced metric, but may not be sufficient for imbalanced data

- **ROC-AUC**: Area under the ROC curve
  - Good overall measure, but can be misleading with severe imbalance

- **Precision-Recall AUC**: Area under the precision-recall curve
  - **Better for imbalanced data** than ROC-AUC
  - Focuses on the minority class performance

- **Confusion Matrix**: Detailed breakdown of predictions
  - Essential for understanding model performance

**Recommendation**: Focus on **Recall** and **Precision-Recall AUC** for this imbalanced medical dataset.

## Medical Notes

### Stroke Risk Factors

The dataset captures several well-established stroke risk factors:

- **Age**: Risk increases significantly with age
- **Hypertension**: Major modifiable risk factor
- **Heart Disease**: Increases risk of stroke (especially atrial fibrillation)
- **Diabetes/High Glucose**: Elevated blood sugar is a risk factor
- **Smoking**: Current and former smoking increase risk
- **Obesity (High BMI)**: Associated with increased stroke risk

### Stroke Prevention

Early identification of risk factors allows for:
- Lifestyle modifications (diet, exercise, smoking cessation)
- Medical management (blood pressure control, diabetes management)
- Preventive medications (anticoagulants for heart disease)
- Regular monitoring and screening

### Clinical Significance

- **Hypertension**: Most important modifiable risk factor
- **Age**: Non-modifiable but critical for risk assessment
- **Heart Disease**: Especially atrial fibrillation increases stroke risk
- **Diabetes**: High glucose levels damage blood vessels
- **Smoking**: Damages blood vessels and increases clot formation

## Feature Engineering Opportunities

1. **Age Groups**: 
   - Children (<18), Young adults (18-40), Middle-aged (41-60), Elderly (61-80), Very elderly (>80)

2. **BMI Categories**: 
   - Underweight (<18.5), Normal (18.5-24.9), Overweight (25-29.9), Obese (≥30)

3. **Glucose Categories**: 
   - Normal (<100), Prediabetes (100-125), Diabetes (≥126)

4. **Risk Score**: 
   - Composite score combining multiple risk factors

5. **Missing Indicators**: 
   - BMI_missing flag
   - Smoking_unknown flag

6. **Interactions**: 
   - Age × Hypertension
   - Age × Heart Disease
   - Hypertension × Heart Disease
   - BMI × Glucose Level

## Files

- `stroke.csv`: Dataset in CSV format with all features and target variable

## Additional Notes

- The dataset includes pediatric patients (children)
- BMI values are stored as character with "N/A" for missing values (needs conversion to numeric)
- Smoking status has a significant "Unknown" category (30.2%)
- The dataset represents real-world medical data with typical challenges (imbalance, missing values)
- Large dataset size (5,110 instances) allows for robust model training despite imbalance

## Research Questions

This dataset can help answer:
- What are the most important risk factors for stroke?
- How do different combinations of risk factors affect stroke probability?
- Can we accurately predict stroke risk using simple demographic and clinical features?
- What is the relative importance of modifiable vs. non-modifiable risk factors?
- How does age interact with other risk factors?

## Citation

**Source**: (Confidential Source) - Use only for educational purposes

If you use this dataset in your research, please credit the author.

**Note**: This dataset is intended for educational and research purposes only. It should not be used for actual medical diagnosis. Always consult qualified healthcare professionals for medical advice, diagnosis, and treatment.

## Disclaimer

This dataset is intended for **educational and research purposes only**. It should **NOT** be used for actual medical diagnosis or treatment decisions. Machine learning models should be validated in clinical settings before use in medical decision-making. Always consult qualified healthcare professionals for medical advice, diagnosis, and treatment.

