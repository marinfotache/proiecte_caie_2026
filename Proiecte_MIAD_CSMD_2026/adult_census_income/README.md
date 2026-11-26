# Adult Census Income Dataset

## Overview

This dataset was extracted from the 1994 Census Bureau database. The prediction task is to determine whether a person makes over 50K a year based on census data.

## Source

- **Original Source**: Census Bureau database (http://www.census.gov/ftp/pub/DES/www/welcome.html)
- **Donors**: Ronny Kohavi and Barry Becker, Data Mining and Visualization, Silicon Graphics
- **Contact**: ronnyk@sgi.com for questions
- **Extraction**: Done by Barry Becker from the 1994 Census database

## Dataset Information

- **Total Instances**: 48,842 (mix of continuous and discrete)
  - Training set: 32,561 instances
  - Test set: 16,281 instances
- **Instances with unknown values removed**: 45,222
  - Training set: 30,162 instances
  - Test set: 15,060 instances
- **Duplicate or conflicting instances**: 6

## Class Distribution

- **Probability for '>50K'**: 23.93% / 24.78% (without unknowns)
- **Probability for '<=50K'**: 76.07% / 75.22% (without unknowns)

## Data Extraction Criteria

A set of reasonably clean records was extracted using the following conditions:
- Age > 16
- Adjusted Gross Income (AGI) > 100
- Final Weight (AFNLWGT) > 1
- Hours per Week (HRSWK) > 0

## Data Preprocessing

1. Discretized gross income into two ranges with threshold 50,000
2. Converted "U.S." to "US" to avoid periods
3. Converted "Unknown" to "?"
4. Split into train/test sets using MLC++ GenCVFiles (2/3 train, 1/3 test random split)

## Variable Descriptions

### Target Variable
- **income**: Binary classification target
  - `>50K`: Annual income greater than 50,000
  - `<=50K`: Annual income less than or equal to 50,000

### Features

1. **age** (continuous): Age of the individual

2. **workclass** (categorical): Type of employment
   - Private
   - Self-emp-not-inc
   - Self-emp-inc
   - Federal-gov
   - Local-gov
   - State-gov
   - Without-pay
   - Never-worked
   - ? (unknown)

3. **fnlwgt** (continuous): Final weight - a statistical weight used by the Census Bureau to adjust for sampling bias. People with similar demographic characteristics should have similar weights (within state).

4. **education** (categorical): Highest level of education
   - Bachelors
   - Some-college
   - 11th
   - HS-grad
   - Prof-school
   - Assoc-acdm
   - Assoc-voc
   - 9th
   - 7th-8th
   - 12th
   - Masters
   - 1st-4th
   - 10th
   - Doctorate
   - 5th-6th
   - Preschool

5. **education_num** (continuous): Numeric representation of education level

6. **marital_status** (categorical): Marital status
   - Married-civ-spouse
   - Divorced
   - Never-married
   - Separated
   - Widowed
   - Married-spouse-absent
   - Married-AF-spouse

7. **occupation** (categorical): Type of occupation
   - Tech-support
   - Craft-repair
   - Other-service
   - Sales
   - Exec-managerial
   - Prof-specialty
   - Handlers-cleaners
   - Machine-op-inspct
   - Adm-clerical
   - Farming-fishing
   - Transport-moving
   - Priv-house-serv
   - Protective-serv
   - Armed-Forces
   - ? (unknown)

8. **relationship** (categorical): Relationship status
   - Wife
   - Own-child
   - Husband
   - Not-in-family
   - Other-relative
   - Unmarried

9. **race** (categorical): Race
   - White
   - Asian-Pac-Islander
   - Amer-Indian-Eskimo
   - Other
   - Black

10. **sex** (categorical): Gender
    - Female
    - Male

11. **capital_gain** (continuous): Capital gains income

12. **capital_loss** (continuous): Capital losses

13. **hours_per_week** (continuous): Hours worked per week

14. **native_country** (categorical): Country of origin
    - United-States
    - Cambodia, England, Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc), India, Japan, Greece, South, China, Cuba, Iran, Honduras, Philippines, Italy, Poland, Jamaica, Vietnam, Mexico, Portugal, Ireland, France, Dominican-Republic, Laos, Ecuador, Taiwan, Haiti, Columbia, Hungary, Guatemala, Nicaragua, Scotland, Thailand, Yugoslavia, El-Salvador, Trinadad&Tobago, Peru, Hong, Holand-Netherlands
    - ? (unknown)

## About Final Weight (fnlwgt)

The weights on the CPS (Current Population Survey) files are controlled to independent estimates of the civilian noninstitutional population of the US. These are prepared monthly by the Population Division at the Census Bureau. Three sets of controls are used:

1. A single cell estimate of the population 16+ for each state
2. Controls for Hispanic Origin by age and sex
3. Controls by Race, age and sex

All three sets of controls are used in the weighting program and "raked" through 6 times. The term "estimate" refers to population totals derived from CPS by creating "weighted tallies" of any specified socio-economic characteristics of the population.

**Important Note**: Since the CPS sample is actually a collection of 51 state samples, each with its own probability of selection, the statement that people with similar demographic characteristics should have similar weights only applies within state.

## Citation

First cited in:
```
@inproceedings{kohavi-nbtree,
   author={Ron Kohavi},
   title={Scaling Up the Accuracy of Naive-Bayes Classifiers: a
          Decision-Tree Hybrid},
   booktitle={Proceedings of the Second International Conference on
              Knowledge Discovery and Data Mining},
   year = 1996,
   pages={to appear}
}
```

## Benchmark Results

Error rates reported after removal of unknowns from train/test sets:

- **C4.5**: 84.46% ± 0.30%
- **Naive-Bayes**: 83.88% ± 0.30%
- **NBTree**: 85.90% ± 0.28%

Additional algorithm results (all after removal of unknowns, using original train/test split, MLC++ with default values):

| Algorithm | Error Rate |
|-----------|------------|
| FSS Naive Bayes | 14.05% |
| NBTree | 14.10% |
| C4.5-auto | 14.46% |
| IDTM (Decision table) | 14.46% |
| HOODG | 14.82% |
| C4.5 rules | 14.94% |
| OC1 | 15.04% |
| C4.5 | 15.54% |
| Voted ID3 (0.6) | 15.64% |
| CN2 | 16.00% |
| Naive-Bayes | 16.12% |
| Voted ID3 (0.8) | 16.47% |
| T2 | 16.84% |
| 1R | 19.54% |
| Nearest-neighbor (3) | 20.35% |
| Nearest-neighbor (1) | 21.42% |

## Files

- `adult.csv`: Combined dataset in CSV format with proper column headers
- `adult.data`: Original training data file
- `adult.test`: Original test data file
- `adult.names`: Original dataset description file

## Usage

This dataset is commonly used for:
- Binary classification tasks
- Income prediction
- Demographic analysis
- Machine learning algorithm benchmarking
- Educational purposes in data mining and machine learning courses

