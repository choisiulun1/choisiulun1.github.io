---
tags:
  - ML
  - Supervised_Learning
aliases:
---
# Loss Function Selection for Regression

## RMSE (Root Mean Square Error)
$$
RMSE(X,h)=\sqrt{\frac{1}{m}\sum_{i=1}^{m}(h(x^i)-y^i)^2 }
$$


>[!info]
>RMSE usually gives higher weight for large errors.


# MAE
If the dataset has many outlier districts, we simply use mean to alleviate the noise distraction.

$$
MAE(X,h)=\frac{1}{m}\sum^m_{i=1}|h(x^i)-y^i|
$$


