---
title: Advance Learning Algorithms
tags: [Learning, Machine Learning, Artificial Intelligence]
style: fill
color: info
description: RECAP of Deeplearning.AI - Advance Learning Algorithm
---
## Week 3 - Advice on applying ML

### Error metrics for skewed datasets
- Generate confusion matrix and look at precision and recall
- Precision = True Positive / Total Predicted Positive 
- Recall = True Positives / Total Actual Positive
- AUC for representation of threshold adjustments
- F1 score (Harmonic Mean of P and R, emphasized the smaller value) measure the trade-off P and R in one score:
$$ F1 = {1 \over {1 \over 2}({1\over P} + {1\over R})} = 2 {PR \over P + R} $$



## Week 4 - Decision Tree / Tree Ensembles
### Decision tree
#### **Steps:**
- Start with all examples at the root node
- Calculate information gain for all possible features, and pick the one with
the highest information gain
- Split dataset according to selected feature, and create left and right
branches of the tree
- Keep repeating splitting process until stopping criteria is met:
    - When a node is 100% one class
    - When splitting a node will result in the tree exceeding a maximum
depth
    - Information gain from additional splits is less than threshold
    - When number of examples in a node is below a threshold

#### Decisions
1. How to choose what feature to split on at each node?
    - Maximize Purity (or minimize impurity): How even the split (more = good)?
        - Measured by [entropy or gini or log_loss](https://scikit-learn.org/stable/modules/tree.html#tree-mathematical-formulation)
        - In decision tree learning, the reduction of entropy is called information gain.

        
1. When do you stop splitting?
    - When a node is 100% one class
    - When splitting a node will result in the tree exceeding a maximum depth (defined parameter)
    - When improvements in purity score are below a threshold
    - When number of examples in a node is below a threshold

#### Regression Decision Tree
- Choosing a split is based on weighted average variance. It plays a very similar role to the weighted average entropy that we had used when deciding what split to use for a classification problem. Result show how much variance it reduced.

#### Tree Ensemble (Multiple Decision Trees)
- Bagging (Parallel)
    - Bootstrap samples with replacement (smaller subset of full training)
    - Generated samples are run with weak learners and aggregated through methods like voting
    - Aim to decrease variance, not bias
    - E.g. Random Forest

- Boosting (Sequential)
    - Focus more on subset of examples that not doing well (increase probability of selection)
    - Built in regularization to prevent overfitting
    - Aim to decrease bias, not variance.
    - E.g. XGBoost

#### When to use Decision Tree and Tree Ensembles
- Works well on tabular (structured) data
- Not recommended for unstructured data
- Fast
- Small decision trees may be human interpretable

#### Neural Networks
- Works well on all types of data
- May be slower
- Works with transfer learning
- Easier to string together multiple neural networks


