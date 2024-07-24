---
tags: [machine learning, overfitting, noise, data, model complexity, curse of dimensionality, feature selection, training data, accuracy, parameter selection,-A]
aliases: []
---

Overfitting happens when the model is too complex relative to the amount and noisiness of the training data.

>For instance, if a machine learning model is given <mark style="background: #FFF3A3A6;">a small amount of noisy data</mark> and <mark style="background: #FFF3A3A6;">the model has too many parameters,</mark> it may try to fit as many of the data points as possible, even the outliers that are not representative of the underlying pattern. This results in a model that is too specialized to the training data and performs poorly on new data that has not been seen before.

- Small amount
	- small amount of data can't have enough information for the algorithm to learn the pattern
- Noisy
	- Noise distrubs the machine to learn from the pattern in the data
	- such as outliner , especially in small amount data , will cause significant change to the algorithm to fit into the noise

## Why do too many parameters cause the overfitting?

>Having too many features can negatively affect the accuracy of a model due to a phenomenon called the curse of dimensionality. When the number of features is large, the amount of training data needed to learn the relationships between these features and the target variable increases exponentially. This means that the model may struggle to find <mark style="background: #FFF3A3A6;">meaningful relationships</mark> between the features and the target variable

- Meaningful relationships
	- When there are too many parameters, there can be several patterns in them. But not all is meaningful.

>For example, say you feed your life satisfaction model many more attributes, including uninformative ones such as the country’s name. In that case, a complex model may detect patterns like the fact that all coun‐ tries in the training data with a w in their name have a life satisfaction greater than 7: New Zealand (7.3), Norway (7.4), Sweden (7.2), and Switzerland (7.5). How confident are you that the W-satisfaction rule generalizes to Rwanda or Zimbabwe? Obviously this pattern occurred in the training data by pure chance, but the model has no way to tell whether a pattern is real or simply the result of noise in the data.

To solve this , we can:
- To simplify the model by selecting one with fewer parameters (e.g., a linear model rather than a high-degree polynomial model), by reducing the number of attributes in the training data or by constraining the model
	- to manually create the hyper-parameters to make the machine concetrate on the desired pattern (since different parameter can have different potential pattern )
	- to gather more training data -> reduce the effect caused by noisy data 
	- directly reduce the noisde


