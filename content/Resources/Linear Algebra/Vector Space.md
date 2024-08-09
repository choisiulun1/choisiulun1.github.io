## Definition
When we discussed groups, we looked at sets $G$ and inner operations on
$G$, i.e., mappings $G \times G \rightarrow G$ that only operate on elements in $G$. In the following, we will consider sets that in addition to an inner operation $+$ also contain an outer operation , the multiplication of a vector $x \in G$ by a scalar $\lambda \in \mathbb{R}$. We can think of the inner operation as a form of addition, and the outer operation as a form of scaling. Note that the inner/outer operations have nothing to do with inner/outer products.
1. $(V, +)$ is an [[Group#Abelian Group | Abelian Group]]
3. Distributivity:
	- $\forall \lambda \in \mathbb{R}, x, y \in V : \lambda \cdot (x + y) = \lambda \cdot x + \lambda \cdot y$
	- $\forall \lambda, \psi \in \mathbb{R}, x \in V : (\lambda + \psi) \cdot x = \lambda \cdot x + \psi \cdot x$
4. Associativity (outer operation): $\forall \lambda, \psi \in \mathbb{R}, x \in V : \lambda \cdot (\psi \cdot x) = (\lambda \psi) \cdot x$
5. Neutral element with respect to the outer operation: $\forall x \in V : 1 \cdot x = x$

> There is no meaningful definition of the inverse element for scalar operation


>[!info] 
>Exists a Set $V$ with inner operation $+$ and outer operation  , which $(V,+)$ is a [[Group#Abelian Group | Abelian Group]] supporting *Associativity* , *Distributivity* , *Identity Element* , *Inverse Element* $(-v)$ , *Communtativity* (for $+$).

Also define *Distributivity* , *Associativity* and *Neutral Element* for scalar



---
# Vector Subspace
## Definition
Let $V = (V, +, \cdot)$ be a vector space and $U \subseteq V, U \neq \emptyset$. Then $U = (U, +, \cdot)$ is called a *vector subspace* of $V$ (or linear subspace) if $U$ is a vector space with the vector space operations $+$ and  restricted to $U \times U$ and $\mathbb{R} \times U$. We write $U \subseteq V$ to denote a subspace $U$ of $V$.

If $U \subseteq V$ and $V$ is a vector space, then $U$ naturally inherits many properties directly from $V$ because they hold for all $x \in V$, and in particular for all $x \in U \subseteq V$. This includes the Abelian group properties, the distributivity, the associativity, and the neutral element. To determine whether $U = (U, +, \cdot)$ is a subspace of $V$ we still do need to show:

1. $U \neq \emptyset$, in particular: $0 \in U$
2. Closure of $U$:
	- With respect to the outer operation: $\forall \lambda \in \mathbb{R} \, \forall x \in U : \lambda x \in U$
	- With respect to the inner operation: $\forall x, y \in U : x + y \in U$

>[!notes]
>The solution set of a homogeneous system of linear equations : $A \mathbf{x} = 0$ with $n$ unknowns $\mathbf{x} = [x_1, \ldots, x_n]^\top$ is a subspace of $\mathbb{R}^n$

**Contains the Zero Vector:**

The zero vector $\mathbf{0}$ in $\mathbb{R}^n$ is a solution to $A \mathbf{0} = 0$. Hence, the zero vector is in the solution set.

**Closed under Addition:**

If $\mathbf{x}$ and $\mathbf{y}$ are both solutions to the system, then:
$A \mathbf{x} = 0 \quad \text{and} \quad A \mathbf{y} = 0$
We need to show that $\mathbf{x} + \mathbf{y}$ is also a solution. Consider:
$A (\mathbf{x} + \mathbf{y}) = A \mathbf{x} + A \mathbf{y} = 0 + 0 = 0$
Hence, $\mathbf{x} + \mathbf{y}$ is in the solution set, proving closure under addition.

**Closed under Scalar Multiplication:**

If $\mathbf{x}$ is a solution and $\lambda$ is a scalar, then:
$A \mathbf{x} = 0$
We need to show that $\lambda \mathbf{x}$ is also a solution. Consider:
$A (\lambda \mathbf{x}) = \lambda A \mathbf{x} = \lambda 0 = 0$
Hence, $\lambda \mathbf{x}$ is in the solution set, proving closure under scalar multiplication.

