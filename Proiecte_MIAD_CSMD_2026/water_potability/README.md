# Water Potability Dataset

## Overview

Access to safe drinking-water is essential to health, a basic human right and a component of effective policy for health protection. This is important as a health and development issue at a national, regional and local level. In some regions, it has been shown that investments in water supply and sanitation can yield a net economic benefit, since the reductions in adverse health effects and health care costs outweigh the costs of undertaking the interventions.

The water_potability.csv file contains water quality metrics for 3,276 different water bodies. This dataset is designed to predict whether water is safe for human consumption based on various chemical and physical properties.

## Dataset Information

- **Number of Rows**: 3,276
- **Number of Columns**: 10
- **Missing Values**: 1,434 total (43.8% of data points)
  - pH: 491 missing (15.0%)
  - Sulfate: 781 missing (23.8%)
  - Trihalomethanes: 162 missing (4.9%)
- **Target Variable**: `Potability` (binary classification problem)
- **Problem Type**: Binary Classification (predicting water safety for human consumption)

## Dataset Columns

### 1. ph
- **Type**: Numeric (Float)
- **Description**: pH value - an important parameter in evaluating the acid–base balance of water. It is also the indicator of acidic or alkaline condition of water status.
- **WHO Standard**: Maximum permissible limit from 6.5 to 8.5
- **Range**: 0 - 14
- **Mean**: 7.08
- **Median**: 7.04
- **Missing Values**: 491 (15.0%)
- **Note**: Values outside the WHO range (6.5-8.5) may indicate non-potable water.

### 2. Hardness
- **Type**: Numeric (Float)
- **Description**: Hardness is mainly caused by calcium and magnesium salts. These salts are dissolved from geologic deposits through which water travels. The length of time water is in contact with hardness producing material helps determine how much hardness there is in raw water. Hardness was originally defined as the capacity of water to precipitate soap caused by Calcium and Magnesium.
- **Range**: 47.43 - 323.12
- **Mean**: 196.37
- **Median**: 196.97
- **Missing Values**: None
- **Units**: Typically measured in mg/L (milligrams per liter) or ppm (parts per million)

### 3. Solids (Total Dissolved Solids - TDS)
- **Type**: Numeric (Float)
- **Description**: Water has the ability to dissolve a wide range of inorganic and some organic minerals or salts such as potassium, calcium, sodium, bicarbonates, chlorides, magnesium, sulfates etc. These minerals produced un-wanted taste and diluted color in appearance of water. This is the important parameter for the use of water. The water with high TDS value indicates that water is highly mineralized.
- **WHO Standard**: 
  - Desirable limit: 500 mg/L
  - Maximum limit: 1000 mg/L (prescribed for drinking purpose)
- **Range**: 320.94 - 61,227.20
- **Mean**: 22,014.09
- **Median**: 20,927.83
- **Missing Values**: None
- **Units**: mg/L (milligrams per liter)
- **Note**: Many values exceed the WHO maximum limit of 1000 mg/L, indicating potential non-potability.

### 4. Chloramines
- **Type**: Numeric (Float)
- **Description**: Chlorine and chloramine are the major disinfectants used in public water systems. Chloramines are most commonly formed when ammonia is added to chlorine to treat drinking water.
- **WHO Standard**: Chlorine levels up to 4 milligrams per liter (mg/L or 4 parts per million (ppm)) are considered safe in drinking water.
- **Range**: 0.35 - 13.13
- **Mean**: 7.12
- **Median**: 7.13
- **Missing Values**: None
- **Units**: mg/L (milligrams per liter)
- **Note**: Many values exceed the WHO safe limit of 4 mg/L.

### 5. Sulfate
- **Type**: Numeric (Float)
- **Description**: Sulfates are naturally occurring substances that are found in minerals, soil, and rocks. They are present in ambient air, groundwater, plants, and food. The principal commercial use of sulfate is in the chemical industry. Sulfate concentration in seawater is about 2,700 milligrams per liter (mg/L). It ranges from 3 to 30 mg/L in most freshwater supplies, although much higher concentrations (1000 mg/L) are found in some geographic locations.
- **Range**: 129.00 - 481.03
- **Mean**: 333.78
- **Median**: 333.07
- **Missing Values**: 781 (23.8%)
- **Units**: mg/L (milligrams per liter)

### 6. Conductivity
- **Type**: Numeric (Float)
- **Description**: Pure water is not a good conductor of electric current rather's a good insulator. Increase in ions concentration enhances the electrical conductivity of water. Generally, the amount of dissolved solids in water determines the electrical conductivity. Electrical conductivity (EC) actually measures the ionic process of a solution that enables it to transmit current.
- **WHO Standard**: EC value should not exceed 400 μS/cm (microsiemens per centimeter)
- **Range**: 181.48 - 753.34
- **Mean**: 426.21
- **Median**: 421.88
- **Missing Values**: None
- **Units**: μS/cm (microsiemens per centimeter)
- **Note**: Many values exceed the WHO standard of 400 μS/cm.

### 7. Organic_carbon
- **Type**: Numeric (Float)
- **Description**: Total Organic Carbon (TOC) in source waters comes from decaying natural organic matter (NOM) as well as synthetic sources. TOC is a measure of the total amount of carbon in organic compounds in pure water.
- **US EPA Standard**: 
  - < 2 mg/L as TOC in treated/drinking water
  - < 4 mg/L in source water which is used for treatment
- **Range**: 2.20 - 28.30
- **Mean**: 14.28
- **Median**: 14.22
- **Missing Values**: None
- **Units**: mg/L (milligrams per liter)
- **Note**: Most values exceed the EPA standard of 2-4 mg/L.

### 8. Trihalomethanes
- **Type**: Numeric (Float)
- **Description**: THMs are chemicals which may be found in water treated with chlorine. The concentration of THMs in drinking water varies according to the level of organic material in the water, the amount of chlorine required to treat the water, and the temperature of the water that is being treated.
- **WHO Standard**: THM levels up to 80 ppm (parts per million) is considered safe in drinking water.
- **Range**: 0.74 - 124.00
- **Mean**: 66.40
- **Median**: 66.62
- **Missing Values**: 162 (4.9%)
- **Units**: ppm (parts per million)
- **Note**: Some values exceed the WHO safe limit of 80 ppm.

### 9. Turbidity
- **Type**: Numeric (Float)
- **Description**: The turbidity of water depends on the quantity of solid matter present in the suspended state. It is a measure of light emitting properties of water and the test is used to indicate the quality of waste discharge with respect to colloidal matter.
- **WHO Standard**: Recommended value of 5.00 NTU (Nephelometric Turbidity Units)
- **Range**: 1.45 - 6.74
- **Mean**: 3.97
- **Median**: 3.96
- **Missing Values**: None
- **Units**: NTU (Nephelometric Turbidity Units)
- **Note**: Most values are within the WHO recommended limit of 5.00 NTU.

### 10. Potability
- **Type**: Binary (Numeric) - **Target Variable**
- **Description**: Indicates if water is safe for human consumption.
- **Values**:
  - 1: Potable (safe for human consumption)
  - 0: Not potable (unsafe for human consumption)
- **Distribution**:
  - 0 (Not Potable): 1,998 (61.0%)
  - 1 (Potable): 1,278 (39.0%)
- **Note**: Slight class imbalance - this should be considered when building models.

## Data Characteristics

### Target Variable Distribution
- **Class Imbalance**: Moderate imbalance with 61.0% non-potable vs 39.0% potable
- **Implications**: 
  - Consider using appropriate metrics (F1-score, ROC-AUC, PR-AUC)
  - May benefit from class weighting or resampling techniques
  - Focus on correctly identifying potable water (minority class)

### Data Quality
- **Missing Values**: 1,434 missing values (43.8% of total data points) across 3 columns:
  - pH: 491 missing (15.0%)
  - Sulfate: 781 missing (23.8%) - highest missing rate
  - Trihalomethanes: 162 missing (4.9%)
- **Data Types**: All features are numeric (continuous).
- **Outliers**: Some features show values outside WHO/EPA standards, which may indicate non-potable water.

### Feature Categories
- **Acidity/Basicity**: pH
- **Mineral Content**: Hardness, Solids (TDS), Sulfate
- **Chemical Treatment**: Chloramines, Trihalomethanes
- **Physical Properties**: Conductivity, Turbidity
- **Organic Matter**: Organic_carbon
- **Target**: Potability

## WHO/EPA Standards Summary

| Parameter | WHO/EPA Standard | Dataset Range | Notes |
|-----------|------------------|---------------|-------|
| pH | 6.5 - 8.5 | 0 - 14 | Many values outside range |
| TDS (Solids) | 500-1000 mg/L | 320.94 - 61,227.20 | Most values exceed limit |
| Chloramines | ≤ 4 mg/L | 0.35 - 13.13 | Many values exceed limit |
| Conductivity | ≤ 400 μS/cm | 181.48 - 753.34 | Many values exceed limit |
| Organic Carbon | < 2-4 mg/L | 2.20 - 28.30 | Most values exceed limit |
| Trihalomethanes | ≤ 80 ppm | 0.74 - 124.00 | Some values exceed limit |
| Turbidity | ≤ 5.00 NTU | 1.45 - 6.74 | Most values within limit |

## Usage

This dataset is suitable for:

1. **Binary Classification**: Predict water potability based on chemical and physical properties
2. **Water Quality Assessment**: Understand which factors determine water safety
3. **Feature Importance Analysis**: Identify critical water quality parameters
4. **Machine Learning Practice**: Handle missing values, class imbalance, and multi-feature classification
5. **Public Health Research**: Analyze water quality standards and compliance
6. **Environmental Monitoring**: Develop models for automated water quality testing

## Considerations

### 1. Missing Values
- **High Missing Rate**: 43.8% of data points have at least one missing value
- **Missing Patterns**: 
  - pH: 15.0% missing
  - Sulfate: 23.8% missing (highest)
  - Trihalomethanes: 4.9% missing
- **Handling Strategies**:
  - **Imputation**: Use mean, median, mode, or predictive imputation (KNN, iterative imputer)
  - **Complete Case Analysis**: Drop rows with missing values (may lose significant data)
  - **Missing Indicator**: Create binary features indicating missingness
  - **Domain Knowledge**: Use WHO standards or typical values for imputation

### 2. Class Imbalance
- **Moderate Imbalance**: 61.0% vs 39.0%
- **Handling Strategies**:
  - Use appropriate metrics (F1-score, ROC-AUC, PR-AUC)
  - Apply class weights in models
  - Consider SMOTE or other resampling techniques
  - Focus on recall for potable water (safety-critical)

### 3. Feature Engineering
- **Standard Compliance Indicators**: Create binary features indicating if each parameter meets WHO/EPA standards
- **Composite Scores**: Create water quality indices combining multiple parameters
- **Ratio Features**: Create ratios between related parameters
- **Outlier Indicators**: Flag values significantly outside normal ranges
- **Missing Value Patterns**: Analyze if missingness correlates with potability

### 4. Data Preprocessing
- **Feature Scaling**: Scale numeric features (StandardScaler, MinMaxScaler) for distance-based algorithms
- **Outlier Handling**: Check for and handle outliers, especially in Solids (TDS) which has very high max value
- **Log Transformation**: Consider log transformation for highly skewed features (e.g., Solids)

### 5. Domain Knowledge
- **WHO Standards**: Use WHO/EPA standards to create rule-based features
- **Parameter Relationships**: Understand chemical relationships (e.g., TDS and Conductivity are related)
- **Safety Priority**: False negatives (predicting potable when not) are critical for public health

### 6. Evaluation Metrics
- **Primary Metrics**: 
  - Precision (minimize false positives - don't declare unsafe water as safe)
  - Recall (maximize true positives - don't miss unsafe water)
  - F1-Score (balance between precision and recall)
  - ROC-AUC (overall discriminative ability)
  - PR-AUC (better for imbalanced data)
- **Safety Metrics**: 
  - Focus on recall for non-potable class (safety-critical)
  - Minimize false negatives (unsafe water predicted as safe)

## Evaluation Metrics

For binary classification with class imbalance, consider:

### Primary Metrics
- **Precision**: Proportion of predicted potable water that is actually potable
- **Recall (Sensitivity)**: Proportion of actual potable water correctly identified
- **F1-Score**: Harmonic mean of precision and recall
- **ROC-AUC**: Area under the ROC curve (overall discriminative ability)
- **PR-AUC**: Area under the Precision-Recall curve (better for imbalanced data)

### Safety-Critical Metrics
- **Recall for Non-Potable Class**: Critical - must identify unsafe water
- **False Negative Rate**: Minimize unsafe water predicted as safe
- **Confusion Matrix**: Visualize classification performance

## Model Suggestions

### Classification Models
- **Logistic Regression**: Baseline model, interpretable coefficients
- **Random Forest**: Handle non-linear relationships, feature importance, robust to missing values
- **Gradient Boosting** (XGBoost, LightGBM, CatBoost): High performance, handles missing values well
- **Neural Networks**: Complex non-linear relationships
- **Support Vector Machines (SVM)**: Non-linear relationships with kernel tricks
- **Ensemble Methods**: Combine multiple models for better performance

### Handling Missing Values
- **XGBoost/LightGBM**: Built-in handling of missing values
- **Iterative Imputer**: Use relationships between features to impute
- **KNN Imputer**: Use similar samples for imputation
- **Domain-Based Imputation**: Use WHO standards or typical values

## Feature Engineering Ideas

1. **WHO Compliance Features**: Binary indicators for each parameter meeting WHO standards
   - `ph_in_range`: 1 if 6.5 ≤ pH ≤ 8.5, else 0
   - `tds_acceptable`: 1 if Solids ≤ 1000, else 0
   - `chloramines_safe`: 1 if Chloramines ≤ 4, else 0
   - `conductivity_safe`: 1 if Conductivity ≤ 400, else 0
   - `organic_carbon_safe`: 1 if Organic_carbon < 4, else 0
   - `trihalomethanes_safe`: 1 if Trihalomethanes ≤ 80, else 0
   - `turbidity_safe`: 1 if Turbidity ≤ 5, else 0

2. **Compliance Score**: Count of parameters meeting WHO standards (0-7)

3. **Ratio Features**:
   - `tds_to_conductivity`: Solids / Conductivity
   - `chloramines_to_organic_carbon`: Chloramines / Organic_carbon

4. **Outlier Indicators**: Binary features indicating extreme values

5. **Missing Value Indicators**: Binary features indicating missingness in pH, Sulfate, Trihalomethanes

6. **Composite Indices**:
   - `mineral_content`: (Hardness + Solids) / 2
   - `treatment_level`: (Chloramines + Trihalomethanes) / 2

7. **Log Transformations**: Log transform highly skewed features (e.g., Solids)

8. **Binning**: Create categorical features from continuous ones (e.g., pH categories: acidic, neutral, alkaline)

## Research Questions

Potential research questions to explore:
1. Which water quality parameters are most predictive of potability?
2. How do different combinations of parameters affect water safety?
3. What is the relationship between TDS and Conductivity?
4. How does pH relate to other chemical parameters?
5. Which parameters most frequently violate WHO standards?
6. Can we predict potability with missing values in some parameters?
7. What is the minimum set of parameters needed for accurate prediction?
8. How do treatment chemicals (Chloramines, Trihalomethanes) relate to organic carbon?
9. Are there regional patterns in water quality (if location data available)?
10. What is the optimal threshold for each parameter to ensure potability?

## Public Health Applications

### Water Quality Monitoring
- **Automated Testing**: Develop models for rapid water quality assessment
- **Early Warning Systems**: Identify potentially unsafe water sources
- **Resource Allocation**: Prioritize water treatment resources

### Policy and Regulation
- **Compliance Monitoring**: Assess adherence to WHO/EPA standards
- **Risk Assessment**: Identify high-risk water sources
- **Treatment Planning**: Determine necessary treatment levels

### Research and Development
- **Parameter Importance**: Understand which factors most affect safety
- **Standard Development**: Inform future water quality standards
- **Treatment Optimization**: Optimize water treatment processes

## Important Notes

1. **Missing Values**: High missing rate (43.8%) requires careful handling. Consider using models that handle missing values well (e.g., XGBoost, LightGBM).

2. **Class Imbalance**: Moderate imbalance (61% vs 39%) should be addressed with appropriate metrics and techniques.

3. **Safety Priority**: False negatives (predicting potable when not) are critical for public health. Prioritize recall for non-potable class.

4. **WHO Standards**: Many values exceed WHO/EPA standards, which may be intentional to include both safe and unsafe water samples.

5. **Feature Relationships**: Some features are related (e.g., TDS and Conductivity). Consider multicollinearity in linear models.

6. **Outliers**: Some features have extreme values (e.g., Solids max: 61,227.20). Investigate and handle appropriately.

7. **Domain Knowledge**: Understanding water chemistry and WHO standards is valuable for feature engineering and interpretation.

## Data Split Recommendation

For model development:
- **Train Set**: 70-80% of data
- **Validation Set**: 10-15% of data (for hyperparameter tuning)
- **Test Set**: 10-15% of data (for final evaluation)
- **Stratified Split**: Ensure class distribution is maintained across splits

## Citation

If you use this dataset in your research or projects, please acknowledge the source appropriately and cite relevant WHO/EPA standards.

---

**Note**: This dataset is designed for educational and research purposes. When building models for real-world water quality assessment, ensure proper validation, consider regulatory requirements, and consult with water quality experts. Public health and safety should be the primary consideration when deploying such models.

