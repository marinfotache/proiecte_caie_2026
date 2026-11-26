# Mushroom Classification Dataset

## Overview

This dataset includes descriptions of hypothetical samples corresponding to 23 species of gilled mushrooms in the Agaricus and Lepiota Family. Each species is identified as definitely edible, definitely poisonous, or of unknown edibility and not recommended. The latter class was combined with the poisonous one. The Guide clearly states that there is no simple rule for determining the edibility of a mushroom; no rule like "leaflets three, let it be" for Poisonous Oak and Ivy.

## Source Information

**Source**: Mushroom records drawn from The Audubon Society Field Guide to North American Mushrooms (1981). G. H. Lincoff (Pres.), New York: Alfred A. Knopf

**Donor**: Jeff Schlimmer (Jeffrey.Schlimmer@a.gp.cs.cmu.edu)

**Date**: 27 April 1987

## Dataset Information

- **Total Instances**: 8,124
- **Number of Attributes**: 22 input attributes + 1 target variable (all nominally valued)
- **Data Format**: CSV (converted from ARFF format)
- **Task**: Binary classification (edible vs. poisonous)

## Target Variable

**class** (categorical)
- `e`: Edible
- `p`: Poisonous (includes definitely poisonous and unknown edibility)

### Class Distribution

| Class | Number of Instances | Percentage |
|-------|---------------------|------------|
| Edible (e) | 4,208 | 51.8% |
| Poisonous (p) | 3,916 | 48.2% |
| **Total** | **8,124** | **100%** |

## Variable Descriptions

All attributes are categorical (nominally valued) with single-letter codes.

### Cap Features

1. **cap-shape** (categorical)
   - Shape of the mushroom cap
   - Values: `b` (bell), `c` (conical), `f` (flat), `k` (knobbed), `s` (sunken), `x` (convex)

2. **cap-surface** (categorical)
   - Surface texture of the cap
   - Values: `f` (fibrous), `g` (grooves), `s` (smooth), `y` (scaly)

3. **cap-color** (categorical)
   - Color of the cap
   - Values: `b` (buff), `c` (cinnamon), `e` (red), `g` (gray), `n` (brown), `p` (pink), `r` (green), `u` (purple), `w` (white), `y` (yellow)

4. **bruises?** (binary)
   - Whether the mushroom has bruises
   - Values: `t` (bruises), `f` (no bruises)

### Odor

5. **odor** (categorical)
   - Odor of the mushroom
   - Values: `a` (almond), `c` (creosote), `f` (foul), `l` (anise), `m` (musty), `n` (none), `p` (pungent), `s` (spicy), `y` (fishy)
   - **Important**: Odor is one of the most predictive features for edibility

### Gill Features

6. **gill-attachment** (categorical)
   - How gills attach to the stalk
   - Values: `a` (attached), `d` (descending), `f` (free), `n` (notched)

7. **gill-spacing** (categorical)
   - Spacing of gills
   - Values: `c` (close), `d` (distant), `w` (crowded)

8. **gill-size** (categorical)
   - Size of gills
   - Values: `b` (broad), `n` (narrow)

9. **gill-color** (categorical)
   - Color of gills
   - Values: `b` (buff), `e` (red), `g` (gray), `h` (chocolate), `k` (black), `n` (brown), `o` (orange), `p` (pink), `r` (green), `u` (purple), `w` (white), `y` (yellow)

### Stalk Features

10. **stalk-shape** (categorical)
    - Shape of the stalk
    - Values: `e` (enlarging), `t` (tapering)

11. **stalk-root** (categorical)
    - Root structure of the stalk
    - Values: `b` (bulbous), `c` (club), `e` (equal), `r` (rooted), `u` (cup), `z` (rhizomorphs)
    - **Missing Values**: 2,480 instances (30.5% of the dataset)
    - Missing values are denoted by `?` in the original data

12. **stalk-surface-above-ring** (categorical)
    - Surface texture of stalk above the ring
    - Values: `f` (fibrous), `k` (silky), `s` (smooth), `y` (scaly)

13. **stalk-surface-below-ring** (categorical)
    - Surface texture of stalk below the ring
    - Values: `f` (fibrous), `k` (silky), `s` (smooth), `y` (scaly)

14. **stalk-color-above-ring** (categorical)
    - Color of stalk above the ring
    - Values: `b` (buff), `c` (cinnamon), `e` (red), `g` (gray), `n` (brown), `o` (orange), `p` (pink), `w` (white), `y` (yellow)

15. **stalk-color-below-ring** (categorical)
    - Color of stalk below the ring
    - Values: `b` (buff), `c` (cinnamon), `e` (red), `g` (gray), `n` (brown), `o` (orange), `p` (pink), `w` (white), `y` (yellow)

### Veil and Ring Features

16. **veil-type** (categorical)
    - Type of veil
    - Values: `p` (partial), `u` (universal)

17. **veil-color** (categorical)
    - Color of the veil
    - Values: `n` (brown), `o` (orange), `w` (white), `y` (yellow)

18. **ring-number** (categorical)
    - Number of rings
    - Values: `n` (none), `o` (one), `t` (two)

19. **ring-type** (categorical)
    - Type of ring
    - Values: `c` (cobwebby), `e` (evanescent), `f` (flaring), `l` (large), `n` (none), `p` (pendant), `s` (sheathing), `z` (zone)

### Spore and Habitat Features

20. **spore-print-color** (categorical)
    - Color of the spore print
    - Values: `b` (buff), `h` (chocolate), `k` (black), `n` (brown), `o` (orange), `r` (green), `u` (purple), `w` (white), `y` (yellow)
    - **Important**: Spore print color is highly predictive of edibility

21. **population** (categorical)
    - Population pattern
    - Values: `a` (abundant), `c` (clustered), `n` (numerous), `s` (scattered), `v` (several), `y` (solitary)

22. **habitat** (categorical)
    - Habitat where mushroom is found
    - Values: `d` (woods), `g` (grasses), `l` (leaves), `m` (meadows), `p` (paths), `u` (urban), `w` (waste)

### Target Variable

23. **class** (categorical)
    - Edibility classification
    - Values: `e` (edible), `p` (poisonous)
    - This is the target variable for classification

## Missing Values

- **Total Missing Values**: 2,480
- **Location**: All missing values are in the `stalk-root` attribute (attribute #11)
- **Percentage**: 30.5% of instances have missing stalk-root values
- **Representation**: Missing values are represented as `NA` in the CSV file (originally marked as `?` in the ARFF file)

## Key Findings from Research

### Simple Logical Rules

Research has identified simple logical rules for classifying mushrooms. The simplest rules found involve only 6 attributes:

**Rules for Poisonous Mushrooms** (from most general to most specific):

1. **P_1**: `odor != (almond OR anise OR none)`
   - 120 poisonous cases missed, 98.52% accuracy

2. **P_2**: `spore-print-color = green`
   - 48 cases missed, 99.41% accuracy

3. **P_3**: `odor = none AND stalk-surface-below-ring = scaly AND stalk-color-above-ring != brown`
   - 8 cases missed, 99.90% accuracy

4. **P_4**: `habitat = leaves AND cap-color = white`
   - 100% accuracy

**Alternative P_4**: `population = clustered AND cap-color = white`

**Rules for Edible Mushrooms**:
- Can be obtained as negation of the poisonous rules
- Example: `odor = (almond OR anise OR none) AND spore-print-color != green`
  - 48 errors, 99.41% accuracy

### Most Important Attributes

Based on research, the most predictive attributes are:
1. **odor** - Highly predictive
2. **spore-print-color** - Very important, especially green color
3. **stalk-surface-below-ring** - Important in combination with other features
4. **cap-color** - Important in specific combinations
5. **habitat** - Important in combination with cap-color
6. **population** - Alternative to habitat in some rules

## Usage

This dataset is suitable for:

- **Binary Classification**: Predicting mushroom edibility (edible vs. poisonous)
- **Rule Learning**: Discovering simple logical rules for classification
- **Feature Selection**: Identifying the most important attributes for classification
- **Educational Purposes**: Teaching classification algorithms with a well-studied dataset
- **Benchmarking**: Comparing different machine learning algorithms
- **Decision Tree Learning**: Excellent for decision tree and rule-based algorithms

## Important Considerations

1. **Missing Values**: The `stalk-root` attribute has 2,480 missing values (30.5%). Consider:
   - Imputation techniques (mode, or treat as separate category)
   - Removing the attribute if it's not critical
   - Using algorithms that handle missing values
   - Analyzing patterns in missing data

2. **All Categorical Attributes**: All attributes are categorical. Consider:
   - Encoding strategies (one-hot encoding, label encoding, etc.)
   - Decision trees and rule-based algorithms work well
   - Some algorithms may require encoding transformations

3. **Class Balance**: The dataset is relatively balanced (51.8% vs 48.2%), but consider:
   - Using appropriate evaluation metrics
   - The slight imbalance may still warrant attention

4. **High Predictability**: This dataset is known to be highly predictable with simple rules. Consider:
   - This makes it excellent for educational purposes
   - May not be representative of real-world classification problems
   - Good for demonstrating algorithm capabilities

5. **Safety Warning**: 
   - **NEVER use this dataset or any model trained on it for actual mushroom identification**
   - Mushroom identification requires expert knowledge
   - Consuming misidentified mushrooms can be fatal
   - This is a hypothetical dataset for educational purposes only

## Evaluation Metrics

For binary classification, consider:
- **Accuracy**: Overall classification accuracy (can achieve very high accuracy with simple rules)
- **Precision**: Of predicted poisonous mushrooms, how many are actually poisonous?
- **Recall (Sensitivity)**: Of actual poisonous mushrooms, how many did we correctly identify?
- **Specificity**: Of actual edible mushrooms, how many did we correctly identify?
- **F1-Score**: Harmonic mean of precision and recall
- **ROC-AUC**: Area under the ROC curve

Given the safety implications, **recall (sensitivity) for poisonous mushrooms is critical** - we want to minimize false negatives (classifying poisonous mushrooms as edible).

## Past Research

This dataset has been extensively studied:

1. **Schlimmer (1987)**: STAGGER algorithm achieved 95% classification accuracy after reviewing 1000 instances

2. **Iba, Wogulis, & Langley (1988)**: HILLARY algorithm achieved approximately the same results

3. **Duch et al. (1996, 1997)**: Extracted simple logical rules using backpropagation networks, achieving very high accuracy with rules involving only 6 attributes

## Files

- `mushroom.csv`: Dataset in CSV format with proper column headers
- `mushroom.arff`: Original dataset in ARFF (Attribute-Relation File Format)

## Additional Notes

- The dataset represents 23 species of gilled mushrooms from the Agaricus and Lepiota Family
- All attributes are categorical with single-letter codes
- The dataset is well-known in machine learning research for its high predictability
- Simple logical rules can achieve very high accuracy (99%+)
- The dataset is excellent for teaching and benchmarking classification algorithms

## Safety Disclaimer

**⚠️ CRITICAL WARNING**: This dataset is intended **ONLY for educational and research purposes**. It should **NEVER** be used for actual mushroom identification or consumption decisions. Mushroom identification requires expert mycological knowledge, and consuming misidentified mushrooms can result in serious illness or death. Always consult qualified mycologists or field guides for actual mushroom identification.

