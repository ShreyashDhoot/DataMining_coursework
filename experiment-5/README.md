# Experiment 5: Market Basket Analysis Using Apriori

## Overview
This experiment applies association rule mining on transaction data using the Apriori algorithm.
The dataset used is a grocery-style basket dataset where each row represents one transaction and each column contains an item purchased in that transaction.

## Objective
1. Build an Apriori model using the Market_Basket_Optimisation dataset.
2. Extract and inspect the top association rules for a buy 1 get 1 free style offer.
3. Observe how rules change when offer conditions are made stricter (for example, buy 2 get 2 free style interpretation through stronger thresholds).

## Files
- Market_Basket_Optimisation.csv: Transaction dataset
- Apriori_algo.ipynb: Main notebook with full workflow and analysis
- aprior-algorithm.ipynb: Initial/shorter working notebook

## Libraries Used
- pandas
- numpy
- matplotlib
- seaborn
- apyori

Install missing package if needed:

```bash
pip install apyori
```

## Workflow Implemented
1. Import required libraries.
2. Load dataset with header set to None.
3. Inspect shape and sample rows.
4. Handle missing values by replacing NaN with the string nan temporarily.
5. Convert each transaction row into a Python list.
6. Remove placeholder nan values from each transaction list.
7. Run Apriori on cleaned transaction lists using configurable thresholds.
8. Convert generated rules to a list and inspect results.
9. Display top rules and interpret support, confidence, and lift.
10. Perform additional frequency analysis for maximum sold and minimum sold items.
11. Visualize top-selling items using a bar plot.

## Apriori Parameters Used in Notebook
- minimum_support = 0.003
- minimum_confidence = 0.50
- min_lift = 3
- min_length = 2

These values can be tuned based on business goals and strictness of recommendation quality.

## Offer-Based Interpretation
### Buy 1 Get 1 Free
Use moderate support and confidence to capture a broader set of frequent co-purchases.
Then select top rules by lift/confidence for promotion design.

### Buy 2 Get 2 Free (Stricter Condition)
Use stricter thresholds to focus on stronger and more reliable combinations, for example:
- increase minimum_confidence
- increase min_lift
- optionally increase minimum_support

Expected effect:
- fewer total rules
- stronger average rule quality
- more conservative and targeted promotional combinations

## Key Outputs
- List of generated association rules
- Top rule examples with support, confidence, and lift
- Top 10 maximum sold items
- Top 10 minimum sold items
- Bar chart of top-selling items

## How to Run
1. Open Apriori_algo.ipynb.
2. Run cells sequentially from top to bottom.
3. If apyori is missing, install it and rerun.
4. To compare offers, rerun Apriori with adjusted thresholds and compare:
- total number of rules
- top rule confidence and lift
- item combinations selected

## Learning Outcomes
After completing this experiment, you can:
- preprocess transaction baskets for association mining
- apply Apriori algorithm in Python
- evaluate rules using support, confidence, and lift
- map association rules to practical retail promotion strategies
