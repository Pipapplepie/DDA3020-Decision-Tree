# Decision Tree

## Motivision

Till now, we have learnt 3 **parametric models**; linear regression, logistic regression, and SVM. (they are also supervised learning models) Their **limitations**:

1. The adopted model is determined by the trainer, which may be far from the ground-truth relationship between the input and the output.

2. The dicision/ prediction is difficult to understand/ explain.

Thus, we introduce **nonparametric models**, for example, KNN classification model, and decision tree (DT). They don't need strong assumptions and the data are allowed to speak for themselves. 

## Definition of DT

_Def._ DT is a **hierarchical** nonparameric model for supervised learning whereby the local region is identified in a sequence of **recursive spilits**. 

In a **univariate** tree, in each internal node, the test uses only one of the input dimensions.

<img src="https://user-images.githubusercontent.com/107236740/224930552-207ad562-ad75-49e7-990d-309d3d2d7356.png" width="300">

## Tree Learning

Tree induction (also Tree Learning or Growing) is the construction of tree given a training set.

**Goal:** For a given set, there are many trees that code it with no error, but we are only interested in the **smallest tree**. (the tree size is measured by # nodes in the tree and the complexity of the decision node.)

**Difficulty:** Finding the samllest tree is NP-hard. (Quinlan, 1968)

## Build the Tree

1. Select an attribute and split the data into its children in a tree;
2. Continue splitting with available attributes;

**Until,**

3. Leaf node(s) are pure (only one class remains);

  Or, A maximum depth is reached;
  
  Or, A performance metric is achieved.
  
The tree is constructed in a  **recursive** way, but: What is the **best attribute**? What is the **best split**?

### Best Attribute:

**Impurity Measure Rule**: the attribute that has the **largest reduction of impurity**.

Impurity:

$$\hat{P}(C_i|x,m) = p_m^i = \frac{N_m^i}{N_m}$$

This means for node m, $N_m$: # training instances reaching node m.

$N_m^i$ of $N_m$ belong to $C_i$, i = 1,...,k with $\sum_i N_m^i = N_m$.

Node m is **pure** if $p^i_m$ for all i are either 0 or 1.

### Impurity Measure:

1. For classifiction tree, the goodness of split/ impurity can be quantified by the **classification error**.
i.e.,

2. Entropy (for multi-class node): $I_m = - \sum_{i=1}^K p^i_m log_2 p_m^i$.
