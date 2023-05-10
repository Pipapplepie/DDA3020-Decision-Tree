# K_Means

https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html

# Gaussian Mixture Model (GMM)

## Mixture Model

$p(x) = \sum_z p(x, z) = \sum_z p(x|z)p(z)$

where x denoting a feature variable, z denoting the class label variable.

## Gaussian MM

$p(x) = {\sum_{k=1}}^K \ \pi_k N(x|\mu_k, \Sigma_k)$ with $\pi_k$ mixing coefficients, where $\sum^K \pi_k = 1$ and $\pi_k \geq 0, \ \forall k$

<img src='https://github.com/Pipapplepie/DDA3020-Machine-Learning/assets/107236740/171387cd-9f9f-4f5e-9660-68f8dba4da81' width=700>

<img src='https://github.com/Pipapplepie/DDA3020-Machine-Learning/assets/107236740/a31abbc6-924d-42c6-8751-1478b808f490' width=700>

see https://the-learning-machine.com/article/ml/gaussian-mixture-model

log likelihood: $log L(\Theta) = log(p(x)) = log({\sum_{k=1}}^K \ \pi_k N(x|\mu_k, \Sigma_k))$

## Understand through Latent Variables

Latent (Hidden) Variable Model (LVM)

_Def._ A latent variable model is a statistical model that relates a set of **observable variables** to a set of latent variables.

$p(x) = \sum^K_{k=1} p(x, z=k) = \sum^K p(x|z=k)p(z=k)$

z ~ Categorical($\pi$), i.e., p(z=k| $\pi$) = $\pi_k$

# EM

## Jensen's Inequality

Recall convexity of functions:

Latent variables
