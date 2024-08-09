---
tags:
  - ML
  - Supervised_Learning
aliases:
---

**Supervised learning** involves a human (or some process) labelling the target value $y^i$ for each input $x^i$ .


# Classification
A classification question is **binary** if $y^i$ is drawn from a set of two possible values; otherwise it's called multi-class.

# [[Regression]]

If $y^i \in R^k$ which $y^i=(y_{1},y_{2}\dots ,y_k)$ and each $y_j \in R$ , we call the mapping function $\Phi$ a form of **multivariate regression**. If $y^i$ is a scalar, $\Phi$ is a form of **univariate regression**. 

>Regression for $y^i$ is continuous , Classification for $y^i$ is drawn from finite label set.
>- Binary Classification: $y^i \in \{c_{1},c_{2}\}$
>- Multi-class Classification: $y^i \in \{c_{1},c_{2},\dots,c_{n}\}$
>- Univariate Regression: $y^i \in \mathbb{R}$
>- Multivariate Regression: $y^i \in \mathbb{R}^k$

