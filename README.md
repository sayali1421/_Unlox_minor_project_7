# QuickCart Market Basket Analysis

## Project Overview

QuickCart Market Basket Analysis is an Unsupervised Machine Learning project that uses frequent itemsets and association rules to identify products that are commonly purchased together.

The project analyzes the supplied QuickCart frequent-itemset data, generates association rules, verifies six predefined product-pair patterns, and identifies useful rules for business recommendations.

## Objective

The main objectives of this project are:

* Analyze frequent product combinations.
* Generate association rules.
* Calculate support, confidence, and lift.
* Verify the six specified QuickCart patterns.
* Identify actionable product relationships.
* Provide business recommendations based on the results.

## Dataset Used

The project uses the supplied QuickCart SKU catalog and frequent-itemset reference data.

* **SKU catalog:** 60 products
* **Frequent itemsets:** 256

### Frequent Itemsets

| Itemset Size |  Number |
| ------------ | ------: |
| 1-itemsets   |      60 |
| 2-itemsets   |      78 |
| 3-itemsets   |      86 |
| 4-itemsets   |      30 |
| 5-itemsets   |       2 |
| **Total**    | **256** |

## Technologies Used

* Python
* Pandas
* itertools
* Jupyter Notebook / Google Colab

## Methodology

### 1. Frequent Itemset Data

The supplied frequent-itemset data is loaded into a Pandas DataFrame.

Each itemset is converted into a Python `frozenset` so that the itemsets can be used for association-rule generation.

### 2. Association Rule Generation

Rules are generated from the frequent itemsets.

For a rule:

`A → B`

the following measures are calculated:

**Support**

Support represents how frequently the complete itemset occurs.

**Confidence**

Confidence is calculated as:

`Confidence = Support(A ∪ B) / Support(A)`

**Lift**

Lift is calculated as:

`Lift = Confidence / Support(B)`

### 3. Generated Rules

The project generated:

**1,152 association rules**

The rules are sorted according to lift to identify strong product associations.

## Actionable Rules

Rules are filtered using:

* Support > **5%**
* Lift > **2**

For recommendation purposes, rules with confidence of at least **75%** are further considered.

## Verified Product Patterns

The project verifies the following six predefined patterns:

| Rule                                     | Support | Confidence | Lift |
| ---------------------------------------- | ------: | ---------: | ---: |
| Toned Milk 1L → White Bread 400g         |  23.84% |     93.86% | 3.69 |
| Basmati Rice 5kg → Toor Dal 1kg          |  15.34% |     77.40% | 3.74 |
| Potato Chips 90g → Cola 750ml            |  19.74% |     90.38% | 4.18 |
| Ghee 500ml → Poha 500g                   |  14.68% |     86.05% | 5.07 |
| Instant Coffee 100g → Choco Cookies 150g |  15.20% |     85.88% | 4.84 |
| Hand Sanitizer 200ml → Face Wash 100ml   |  13.18% |     79.30% | 5.05 |

All six predefined patterns were successfully verified against the supplied frequent-itemset data.

## Business Recommendations

### Shelf Placement

Products with strong associations can be placed close to each other:

* Toned Milk + White Bread
* Basmati Rice + Toor Dal
* Potato Chips + Cola
* Ghee + Poha
* Instant Coffee + Choco Cookies
* Hand Sanitizer + Face Wash

### Bundle Offers

The identified product pairs can be used to create:

* Breakfast Combo
* Thali Staples Combo
* Snack-Drink Combo
* Ghar Breakfast Combo
* Tea-Time Combo
* Personal Care Restock Combo

### App Recommendations

High-confidence and reasonably supported rules can be used for product recommendations such as **Frequently Bought Together** suggestions.

## Important Observation

Lift should not be considered alone.

Some rules can have very high lift because their products have relatively low support. Therefore, support, confidence, and lift should be considered together when selecting business recommendations.

## Project Result

The analysis successfully produced:

* **60** 1-itemsets
* **78** 2-itemsets
* **86** 3-itemsets
* **30** 4-itemsets
* **2** 5-itemsets
* **256 total frequent itemsets**
* **1,152 association rules**
* **6/6 predefined patterns verified successfully**

## Conclusion

The QuickCart Market Basket Analysis successfully identifies strong relationships between products using frequent itemsets and association rules.

The verified patterns can be used for shelf placement, bundle offers, cross-selling, and product recommendations. The analysis also demonstrates why support, confidence, and lift should be considered together when selecting useful business rules.
