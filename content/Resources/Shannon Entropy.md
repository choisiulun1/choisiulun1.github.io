---
tags:
  - ML
aliases:
---

## Information
The amount of information can be understood as ***the degree of surprise*** at the occurrence of an event. If an event has a high probability of occurring, then we are not surprised when it occurs and such an event carries less information; conversely, if an event has a low probability of occurring, then we are surprised when it occurs and such an event carries more information.

### Definition
$$
I(x) = -\log_{2}P(x)
$$

>[!example]
>- Completely uncertain event: If the probability of an event occurring is 0.5 (such as the result of a coin toss being heads or tails), its information content is $-\log_2{0.5} = 1$ bit.
>- Completely certain event: If the probability of an event occurring is 1 (such as an event that is guaranteed to happen), its information content is $-\log_2{1}$ = 0 bits.


## Shannon Entropy
Shannon entropy is the ***expected value of the amount of information*** about a set of possible events and is a weighted average of the amount of information. It measures the average uncertainty or amount of information in a message system.

### Definition
$$
H(X) = -\sum_{i=1}^{n} P(x_{i})\log(P(x_{i})) 
$$

>[!info]
>If you receive a message that is completely unexpected, such as the winning lottery numbers, it contains high information content because it greatly reduces your uncertainty. On the contrast, If you receive a piece of news that was already expected, such as that there will be sunrise tomorrow, such a piece of news contains low information content because it does not reduce your uncertainty.

