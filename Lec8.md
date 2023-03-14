# Decision Tree

## Motivision

Till now, we have learnt 3 **parametric models**; linear regression, logistic regression, and SVM. (also supervised learning models) Their **limitations**:

1. The adopted model is determined by the trainer, which may be far from the ground-truth relationship between the input and the output.

2. The dicision/ prediction is difficult to understand/ explain.

Thus, we introduce **nonparametric models**, for example, KNN classification model, and decision tree (DT). They don't need strong assumptions and the data are allowed to speak for themselves. 

## Definition of DT
_Def._ DT is a **hierarchical** nonparameric model for supervised learning whereby the local region is identified in a sequence of **recursive spilits**. In a **univariate** tree, in each internal node, the test uses only one of the input dimensions.

