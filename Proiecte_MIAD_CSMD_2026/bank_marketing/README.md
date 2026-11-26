# Bank Marketing Dataset

## Overview

This dataset is based on the "Bank Marketing" UCI dataset, enriched with five new social and economic features/attributes (national wide indicators from a ~10M population country). The data was published by the Banco de Portugal and is publicly available. The binary classification goal is to predict if the client will subscribe a bank term deposit (variable `y`).

## Source

**Created by**: Sérgio Moro (ISCTE-IUL), Paulo Cortez (Univ. Minho) and Paulo Rita (ISCTE-IUL) @ 2014

**Original Dataset**: Based on "Bank Marketing" UCI dataset  
**UCI Dataset**: http://archive.ics.uci.edu/ml/datasets/Bank+Marketing

**Social and Economic Indicators**: Published by the Banco de Portugal  
**Source**: https://www.bportugal.pt/estatisticasweb

## Citation

This dataset is publicly available for research. The details are described in [Moro et al., 2014]. Please include this citation if you plan to use this database:

**Citation**:  
S. Moro, P. Cortez and P. Rita. A Data-Driven Approach to Predict the Success of Bank Telemarketing. Decision Support Systems, In press, http://dx.doi.org/10.1016/j.dss.2014.03.001

**Available at**:
- [PDF] http://dx.doi.org/10.1016/j.dss.2014.03.001
- [BibTeX] http://www3.dsi.uminho.pt/pcortez/bib/2014-dss.txt

## Dataset Information

- **Total Instances**: 41,188 (bank-additional-full.csv)
- **Number of Attributes**: 20 input attributes + 1 output attribute
- **Time Period**: May 2008 to November 2010 (ordered by date)
- **Data Format**: CSV (semicolon-separated)

## Files

1. **bank-additional-full.csv**: Complete dataset with all 41,188 examples, ordered by date (from May 2008 to November 2010)
2. **bank-additional.csv**: Subset with 10% of the examples (4,119), randomly selected from bank-additional-full.csv. This smaller dataset is provided to test more computationally demanding machine learning algorithms (e.g., SVM).

**Note**: The file can be read in R using: `d=read.table("bank-additional-full.csv",header=TRUE,sep=";")`

## Key Findings

Using the rminer package and R tool (http://cran.r-project.org/web/packages/rminer/), the authors found that the addition of the five new social and economic attributes (made available here) lead to substantial improvement in the prediction of success, even when the duration of the call is not included.

## Variable Descriptions

### Bank Client Data

1. **age** (numeric)
   - Age of the client

2. **job** (categorical)
   - Type of job
   - Values: `"admin."`, `"blue-collar"`, `"entrepreneur"`, `"housemaid"`, `"management"`, `"retired"`, `"self-employed"`, `"services"`, `"student"`, `"technician"`, `"unemployed"`, `"unknown"`

3. **marital** (categorical)
   - Marital status
   - Values: `"divorced"`, `"married"`, `"single"`, `"unknown"`
   - **Note**: "divorced" means divorced or widowed

4. **education** (categorical)
   - Education level
   - Values: `"basic.4y"`, `"basic.6y"`, `"basic.9y"`, `"high.school"`, `"illiterate"`, `"professional.course"`, `"university.degree"`, `"unknown"`

5. **default** (categorical)
   - Has credit in default?
   - Values: `"no"`, `"yes"`, `"unknown"`

6. **housing** (categorical)
   - Has housing loan?
   - Values: `"no"`, `"yes"`, `"unknown"`

7. **loan** (categorical)
   - Has personal loan?
   - Values: `"no"`, `"yes"`, `"unknown"`

### Related with the Last Contact of the Current Campaign

8. **contact** (categorical)
   - Contact communication type
   - Values: `"cellular"`, `"telephone"`

9. **month** (categorical)
   - Last contact month of year
   - Values: `"jan"`, `"feb"`, `"mar"`, `"apr"`, `"may"`, `"jun"`, `"jul"`, `"aug"`, `"sep"`, `"oct"`, `"nov"`, `"dec"`

10. **day_of_week** (categorical)
    - Last contact day of the week
    - Values: `"mon"`, `"tue"`, `"wed"`, `"thu"`, `"fri"`

11. **duration** (numeric)
    - Last contact duration, in seconds
    - **⚠️ Important Note**: This attribute highly affects the output target (e.g., if duration=0 then y="no"). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. **Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.**

### Other Attributes

12. **campaign** (numeric)
    - Number of contacts performed during this campaign and for this client
    - Includes the last contact

13. **pdays** (numeric)
    - Number of days that passed by after the client was last contacted from a previous campaign
    - **Special value**: 999 means client was not previously contacted

14. **previous** (numeric)
    - Number of contacts performed before this campaign and for this client

15. **poutcome** (categorical)
    - Outcome of the previous marketing campaign
    - Values: `"failure"`, `"nonexistent"`, `"success"`

### Social and Economic Context Attributes

These five attributes are national wide indicators from a ~10M population country, published by the Banco de Portugal. These were added to the original UCI Bank Marketing dataset and have been shown to substantially improve prediction performance.

16. **emp.var.rate** (numeric)
    - Employment variation rate
    - Quarterly indicator

17. **cons.price.idx** (numeric)
    - Consumer price index
    - Monthly indicator

18. **cons.conf.idx** (numeric)
    - Consumer confidence index
    - Monthly indicator

19. **euribor3m** (numeric)
    - Euribor 3 month rate
    - Daily indicator
    - Euribor (Euro Interbank Offered Rate) is a reference rate for the euro area

20. **nr.employed** (numeric)
    - Number of employees
    - Quarterly indicator

### Output Variable (Target)

21. **y** (binary)
    - Has the client subscribed a term deposit?
    - Values: `"yes"`, `"no"`
    - This is the target variable for the classification task

## Missing Values

There are several missing values in some categorical attributes, all coded with the `"unknown"` label. These missing values can be treated as:
- A possible class label (keep "unknown" as a valid category)
- Using deletion techniques (remove rows with unknown values)
- Using imputation techniques (replace unknown with most common value, etc.)

## Usage

This dataset is suitable for:

- **Binary Classification**: Predicting whether a client will subscribe to a term deposit
- **Marketing Analytics**: Understanding factors that influence marketing campaign success
- **Feature Engineering**: Exploring the impact of social and economic indicators on marketing outcomes
- **Benchmarking**: Testing machine learning algorithms (use bank-additional.csv for computationally intensive methods)
- **Research**: Academic research on predictive modeling in marketing

## Important Considerations

1. **Duration Attribute**: The `duration` attribute should be excluded when building realistic predictive models, as it is not known before a call is performed. It should only be used for benchmark purposes.

2. **Temporal Ordering**: The full dataset (bank-additional-full.csv) is ordered by date (May 2008 to November 2010). Consider this when splitting data for training/testing to avoid data leakage.

3. **Social/Economic Indicators**: The five additional social and economic context attributes have been shown to significantly improve prediction performance. These provide valuable macroeconomic context that can enhance model accuracy.

4. **Class Imbalance**: The dataset likely has class imbalance (more "no" than "yes" responses), which is common in marketing datasets. Consider appropriate techniques for handling imbalanced data.

## Related Research

The full dataset (bank-additional-full.csv) was described and analyzed in:

**Moro, S., Cortez, P., & Rita, P. (2014).** A Data-Driven Approach to Predict the Success of Bank Telemarketing. Decision Support Systems, doi:10.1016/j.dss.2014.03.001.

## Additional Resources

- **UCI Machine Learning Repository**: http://archive.ics.uci.edu/ml/datasets/Bank+Marketing
- **Banco de Portugal Statistics**: https://www.bportugal.pt/estatisticasweb
- **rminer R Package**: http://cran.r-project.org/web/packages/rminer/

