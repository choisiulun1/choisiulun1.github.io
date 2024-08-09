---
tags:
  - ML
aliases:
---
# Definition
Machine learning is a subfield of artificial intelligence (AI) that focuses on the development of algorithms and statistical models that enable computers to perform tasks without explicit instructions.

Machine learning's goal overlapped with different other fields such as economics and psychology which is to find the causal process and find a model to fit them. The essence of ML is the problem of induction. We have to take some assumption to promise the universality of the laws allowing us to predict from the past observations.

In the context of learning from data, especially in fields like machine learning and statistics, we operationalize the problem of induction by making certain assumptions to facilitate practical solutions.

# Assumption

## IID Assumption (Independent and Identically Distributed Data)

- **Independent**: Each data point is generated independently of the others. This means that the occurrence of one data point does not affect the probability of occurrence of another data point.
- **Identically Distributed**: All data points are drawn from the same probability distribution. This implies that the statistical properties of the data do not change over time or across different samples.

## Same Distribution for Training and Queries

- This assumption means that the data used for training a model and the data the model will encounter in the future (queries) come from the same underlying distribution. This is crucial because if the training data and future data come from different distributions, the model's predictions may not be reliable.

## Known Set of Possible Answers

- This assumption implies that the potential outcomes or categories are known in advance. In other words, the problem space is well-defined, and the model's task is to identify which of the known possible answers is correct for a given query.


- [[Supervised Learning]]
- [[Unsupervised Learning]]