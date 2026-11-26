# Body Fat Prediction Dataset

## Overview

This dataset contains estimates of the percentage of body fat determined by underwater weighing and various body circumference measurements for **252 men**. The dataset is designed to illustrate multiple regression techniques for predicting body fat percentage using simple, non-invasive measurements.

## Context

Accurate measurement of body fat is inconvenient and costly (requiring underwater weighing), making it desirable to have easy methods of estimating body fat that are not inconvenient or costly. This dataset allows researchers to develop predictive equations using simple body circumference measurements that can be easily obtained.

## Source

**Data Provider**: Dr. A. Garth Fisher  
**Permission**: Data freely distributed for non-commercial purposes

**Contact**:  
Roger W. Johnson  
Department of Mathematics & Computer Science  
South Dakota School of Mines & Technology  
501 East St. Joseph Street  
Rapid City, SD 57701  

**Email**: rwjohnso@silver.sdsmt.edu  
**Web**: http://silver.sdsmt.edu/~rwjohnso

## Dataset Information

- **Total Instances**: 252
- **Number of Attributes**: 15 (2 target variables + 13 predictor variables)
- **Data Format**: CSV
- **Task**: Regression (predicting body fat percentage or density)

## Educational Use

This dataset can be used to illustrate:
- **Multiple Regression Techniques**: Building predictive models with multiple predictors
- **Feature Selection**: Identifying which body measurements are most predictive
- **Model Comparison**: Comparing different regression approaches
- **Cross-Validation**: Evaluating model performance on unseen data

## Variable Descriptions

### Target Variables

1. **Density** (numeric)
   - Body density determined from underwater weighing
   - Measured in grams per cubic centimeter (gm/cm³)
   - Range: approximately 0.995 to 1.109 gm/cm³
   - **Note**: This is the primary measurement from underwater weighing

2. **BodyFat** (numeric)
   - Percent body fat from Siri's (1956) equation
   - Calculated using: **Percentage of Body Fat = 495/Density - 450**
   - Measured as percentage
   - Range: approximately 0% to 47.5%

### Demographic Variables

3. **Age** (numeric)
   - Age in years
   - Range: 22 to 81 years

### Anthropometric Variables

4. **Weight** (numeric)
   - Body weight
   - Measured in pounds (lbs)
   - Range: approximately 118.5 to 363.1 lbs

5. **Height** (numeric)
   - Body height
   - Measured in inches
   - Range: approximately 29.5 to 77.75 inches

### Body Circumference Measurements

All circumference measurements are in centimeters (cm) and follow the measurement standards listed in Behnke and Wilmore (1974), pp. 45-48.

6. **Neck** (numeric)
   - Neck circumference (cm)

7. **Chest** (numeric)
   - Chest circumference (cm)

8. **Abdomen** (numeric)
   - Abdomen 2 circumference (cm)
   - **Measurement**: Laterally, at the level of the iliac crests, and anteriorly, at the umbilicus
   - This is often one of the most predictive measurements for body fat

9. **Hip** (numeric)
   - Hip circumference (cm)

10. **Thigh** (numeric)
    - Thigh circumference (cm)

11. **Knee** (numeric)
    - Knee circumference (cm)

12. **Ankle** (numeric)
    - Ankle circumference (cm)

13. **Biceps** (numeric)
    - Biceps (extended) circumference (cm)

14. **Forearm** (numeric)
    - Forearm circumference (cm)

15. **Wrist** (numeric)
    - Wrist circumference (cm)

## Body Fat Calculation: Siri's Equation

The percentage of body fat is calculated from body density using Siri's equation, which is based on the two-component model of body composition:

### Two-Component Model

The body is assumed to consist of two components:
- **Lean body tissue** (density = 1.10 gm/cm³)
- **Fat tissue** (density = 0.90 gm/cm³)

### Mathematical Derivation

Let:
- **D** = Body Density (gm/cm³)
- **A** = proportion of lean body tissue
- **B** = proportion of fat tissue (A + B = 1)
- **a** = density of lean body tissue (1.10 gm/cm³)
- **b** = density of fat tissue (0.90 gm/cm³)

Then:
```
D = 1/[(A/a) + (B/b)]
```

Solving for B (proportion of fat):
```
B = (1/D) × [ab/(a-b)] - [b/(a-b)]
```

### Siri's Equation

Using the estimates a = 1.10 gm/cm³ and b = 0.90 gm/cm³:

**Percentage of Body Fat = 495/D - 450**

This equation converts body density to percentage body fat.

## Underwater Weighing Method

Body density is accurately measured using underwater weighing:

### Principle

Body volume is computed as the difference between body weight measured in air and weight measured during water submersion. Body volume equals the loss of weight in water with appropriate temperature correction for the water's density.

### Formula

```
Body Density = WA/[(WA-WW)/c.f. - LV]
```

Where:
- **WA** = Weight in air (kg)
- **WW** = Weight in water (kg)
- **c.f.** = Water correction factor
  - = 1 at 39.2°F (one gram of water occupies exactly one cm³ at this temperature)
  - = 0.997 at 76-78°F
- **LV** = Residual Lung Volume (liters)

## Research Application

### Original Research

These data were used to produce predictive equations for lean body weight in the abstract:

**"Generalized body composition prediction equation for men using simple measurement techniques"**  
K.W. Penrose, A.G. Nelson, A.G. Fisher, FACSM  
Human Performance Research Center, Brigham Young University, Provo, Utah 84602  

Published in: **Medicine and Science in Sports and Exercise**, vol. 17, no. 2, April 1985, p. 189

**Note**: The predictive equations were obtained from the first 143 of the 252 cases listed in this dataset.

## Usage

This dataset is suitable for:

- **Regression Analysis**: Predicting body fat percentage or density from body measurements
- **Feature Selection**: Identifying which measurements are most predictive
- **Multiple Regression**: Building models with multiple predictors
- **Model Validation**: Testing predictive equations on held-out data
- **Educational Purposes**: Teaching regression techniques with real-world data
- **Health Applications**: Developing practical body fat estimation methods

## Important Considerations

1. **Sample Size**: The dataset contains 252 instances, which is moderate for regression analysis. Consider:
   - Using cross-validation for model evaluation
   - Being cautious with complex models (many parameters)
   - The first 143 cases were used for model development in the original research

2. **Target Variable**: You can predict either:
   - **BodyFat** (percentage): More interpretable for health applications
   - **Density**: The primary measurement, BodyFat is derived from it

3. **Measurement Units**: Be aware of the units:
   - Weight: pounds (lbs)
   - Height: inches
   - Circumferences: centimeters (cm)
   - Density: gm/cm³

4. **Feature Engineering**: Consider creating:
   - Body Mass Index (BMI): Weight / Height²
   - Waist-to-Hip ratio: Abdomen / Hip
   - Waist-to-Height ratio: Abdomen / Height
   - Sum of circumferences
   - Ratios between different body parts

5. **Multicollinearity**: Body measurements are likely correlated. Consider:
   - Checking for multicollinearity
   - Using regularization (Ridge, Lasso)
   - Principal Component Analysis (PCA)

6. **Outliers**: Check for outliers in measurements, especially:
   - Extreme body fat percentages
   - Unusual height/weight combinations
   - Measurement errors

7. **Abdomen Measurement**: The abdomen circumference is often highly predictive. This measurement is taken "laterally, at the level of the iliac crests, and anteriorly, at the umbilicus" (Behnke and Wilmore, 1974).

## Evaluation Metrics

For regression tasks, consider:
- **R² (Coefficient of Determination)**: Proportion of variance explained
- **RMSE (Root Mean Squared Error)**: Average prediction error
- **MAE (Mean Absolute Error)**: Average absolute prediction error
- **MAPE (Mean Absolute Percentage Error)**: Percentage error
- **Cross-Validation**: K-fold cross-validation for robust evaluation

## Practical Applications

### Health Assessment

A variety of popular health books suggest assessing health by estimating percentage of body fat. This dataset supports:
- Development of simple estimation methods
- Validation of existing prediction equations
- Creation of new predictive models

### Alternative Methods

Other methods for estimating body fat include:
- **Skin-fold measurements**: Using calipers at specific body sites
- **Body circumference equations**: Using combinations of measurements
- **Bioelectrical impedance**: Using electrical resistance
- **DEXA scans**: Dual-energy X-ray absorptiometry

This dataset focuses on circumference-based methods as they are relatively simple and non-invasive.

## References

1. **Bailey, Covert (1994)**. Smart Exercise: Burning Fat, Getting Fit, Houghton-Mifflin Co., Boston, pp. 179-186.

2. **Behnke, A.R. and Wilmore, J.H. (1974)**. Evaluation and Regulation of Body Build and Composition, Prentice-Hall, Englewood Cliffs, N.J.

3. **Siri, W.E. (1956)**, "Gross composition of the body", in Advances in Biological and Medical Physics, vol. IV, edited by J.H. Lawrence and C.A. Tobias, Academic Press, Inc., New York.

4. **Katch, Frank and McArdle, William (1977)**. Nutrition, Weight Control, and Exercise, Houghton Mifflin Co., Boston.

5. **Wilmore, Jack (1976)**. Athletic Training and Physical Fitness: Physiological Principles of the Conditioning Process, Allyn and Bacon, Inc., Boston.

6. **Penrose, K.W., Nelson, A.G., Fisher, A.G. (1985)**. "Generalized body composition prediction equation for men using simple measurement techniques", Medicine and Science in Sports and Exercise, vol. 17, no. 2, April 1985, p. 189.

## Files

- `bodyfat.csv`: Dataset in CSV format with all measurements

## Additional Notes

- All subjects are **men** (252 male participants)
- Measurements follow standardized protocols from Behnke and Wilmore (1974)
- Body density is the primary measurement from underwater weighing
- Body fat percentage is calculated using Siri's equation
- The dataset is well-suited for teaching regression analysis
- Original research used first 143 cases for model development, remaining cases for validation


