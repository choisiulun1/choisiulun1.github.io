# Linear Combination
## Definition 

Consider a vector space $V$ and a finite number of vectors $x_1, \ldots, x_k \in V$. Then, every $v \in V$ of the form

$v = \lambda_1 x_1 + \cdots + \lambda_k x_k = \sum_{i=1}^{k} \lambda_i x_i \in V$

with $\lambda_1, \ldots, \lambda_k \in \mathbb{R}$ is a linear combination of the vectors $x_1, \ldots, x_k$.

The 0-vector can always be written as the linear combination of $k$ vectors $x_1, \ldots, x_k$ because $0 = \sum_{i=1}^{k} 0 \cdot x_i$ is always true. 


# Linear Independence
## Definition 
Let us consider a vector space $V$ with $k \in \mathbb{N}$ and $x_1, \ldots, x_k \in V$. If there is a non-trivial linear combination, such that $0 = \sum_{i=1}^{k} \lambda_i x_i$ with at least one $\lambda_i \neq 0$, the vectors $x_1, \ldots, x_k$ are linearly dependent. If only the trivial solution exists, i.e., $\lambda_1 = \cdots = \lambda_k = 0$, the vectors $x_1, \ldots, x_k$ are linearly independent.
