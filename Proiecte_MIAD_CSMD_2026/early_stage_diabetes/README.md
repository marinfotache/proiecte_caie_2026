# Early Stage Diabetes Risk Prediction Dataset

## Overview

This dataset contains clinical and demographic information for predicting early-stage diabetes risk. The dataset includes various symptoms and patient characteristics that are commonly associated with diabetes, making it suitable for binary classification tasks to predict whether a patient has diabetes (Positive) or not (Negative).

## Dataset Information

- **Total Instances**: 520
- **Number of Attributes**: 16 input features + 1 target variable
- **Data Format**: CSV
- **Task**: Binary classification (diabetes prediction)

## Target Variable

**class** (binary)
- `Positive`: Patient has diabetes
- `Negative`: Patient does not have diabetes

### Class Distribution
- **Positive**: 320 instances (61.5%)
- **Negative**: 200 instances (38.5%)

**Note**: The dataset is slightly imbalanced, with more positive cases than negative cases.

## Variable Descriptions

### Demographic Attributes

1. **Age** (numeric)
   - Age of the patient in years
   - Continuous variable

2. **Gender** (categorical)
   - Gender of the patient
   - Values: `Male`, `Female`
   - Distribution: Male (328, 63.1%), Female (192, 36.9%)

### Clinical Symptoms and Signs

All symptom attributes are binary (Yes/No) indicating the presence or absence of the symptom:

3. **Polyuria** (binary)
   - Excessive production of urine
   - Values: `Yes`, `No`
   - **Medical Note**: Polyuria is a common early symptom of diabetes, often caused by high blood sugar levels leading to increased urine production.

4. **Polydipsia** (binary)
   - Excessive thirst
   - Values: `Yes`, `No`
   - **Medical Note**: Polydipsia often accompanies polyuria in diabetes, as the body tries to compensate for fluid loss.

5. **sudden weight loss** (binary)
   - Unexpected or rapid weight loss
   - Values: `Yes`, `No`
   - **Medical Note**: Unexplained weight loss can be an early sign of diabetes, particularly type 1 diabetes, due to the body's inability to use glucose for energy.

6. **weakness** (binary)
   - General feeling of weakness or fatigue
   - Values: `Yes`, `No`
   - **Medical Note**: Weakness and fatigue are common symptoms of diabetes due to the body's inability to properly utilize glucose for energy.

7. **Polyphagia** (binary)
   - Excessive hunger or increased appetite
   - Values: `Yes`, `No`
   - **Medical Note**: Polyphagia occurs in diabetes because the body cannot properly use glucose, leading to increased hunger despite eating.

8. **Genital thrush** (binary)
   - Genital yeast infection (candidiasis)
   - Values: `Yes`, `No`
   - **Medical Note**: High blood sugar levels create an environment favorable for yeast growth, making genital thrush more common in people with diabetes.

9. **visual blurring** (binary)
   - Blurred vision
   - Values: `Yes`, `No`
   - **Medical Note**: High blood sugar levels can cause the lens of the eye to swell, leading to temporary blurred vision.

10. **Itching** (binary)
    - Itchy skin
    - Values: `Yes`, `No`
    - **Medical Note**: Itching can be a symptom of diabetes, often related to dry skin or yeast infections that are more common in diabetic patients.

11. **Irritability** (binary)
    - Increased irritability or mood changes
    - Values: `Yes`, `No`
    - **Medical Note**: Blood sugar fluctuations can affect mood and lead to irritability in people with diabetes.

12. **delayed healing** (binary)
    - Slow healing of wounds or cuts
    - Values: `Yes`, `No`
    - **Medical Note**: High blood sugar levels can impair the body's ability to heal wounds, making delayed healing a common sign of diabetes.

13. **partial paresis** (binary)
    - Partial muscle weakness or paralysis
    - Values: `Yes`, `No`
    - **Medical Note**: Diabetes can cause nerve damage (neuropathy) leading to muscle weakness or partial paralysis.

14. **muscle stiffness** (binary)
    - Stiffness in muscles
    - Values: `Yes`, `No`
    - **Medical Note**: Muscle stiffness can be associated with diabetes, particularly when related to poor circulation or nerve damage.

15. **Alopecia** (binary)
    - Hair loss
    - Values: `Yes`, `No`
    - **Medical Note**: Hair loss can be associated with diabetes, often related to poor circulation, hormonal imbalances, or stress on the body.

16. **Obesity** (binary)
    - Presence of obesity
    - Values: `Yes`, `No`
    - **Medical Note**: Obesity is a major risk factor for type 2 diabetes. Excess body fat, especially around the abdomen, increases insulin resistance.

### Target Variable

17. **class** (binary)
    - Diabetes diagnosis
    - Values: `Positive` (has diabetes), `Negative` (does not have diabetes)
    - This is the target variable for prediction

This dataset is intended for educational and research purposes only. It should not be used for actual medical diagnosis. Always consult qualified healthcare professionals for medical advice and diagnosis.

