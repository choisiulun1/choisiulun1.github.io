# Group

### Definition
Consider a set $G$ and an operation $\otimes : G \times G \to G$ defined on $G$. Then $G := (G, \otimes)$ is called a group if the following hold:


1. **Closure of $G$ under $\otimes$**: $\forall x, y \in G : x \otimes y \in G$
2. **Associativity**: $\forall x, y, z \in G : (x \otimes y) \otimes z = x \otimes (y \otimes z)$
3. **Neutral element**: $\exists e \in G$ such that $\forall x \in G : x \otimes e = x$ and $e \otimes x = x$
4. **Inverse element**: $\forall x \in G \exists y \in G : x \otimes y = e$ and $y \otimes x = e$, where $e$ is the neutral element. We often write $x^{-1}$ to denote the inverse element of $x$.


>[!example] 
>$U = \{ (x,y) \mid x,y \in \mathbb{R}, \, x + y = 1 \}$
>
>Closure under addition: If you take two vectors $(1,0)$ and $(0,1)$ from this set, their sum is
>
>$$(1,0) + (0,1) = (1,1)$$
>
>which does not satisfy $x + y = 1$. Therefore, the set is not closed under addition.



---
# Abelian Group
The diff between Abelian Group and Group is only Group doesn't have *Commutativity*, where $$ a\ast b = b \ast a$$
### General Linear Group
The set of regular (invertible) matrices $A \in \mathbb{R}^{n \times n}$ is a group with respect to matrix multiplication as defined in (2.13) and is called the general linear group $\text{GL}(n, \mathbb{R})$. However, since matrix multiplication is not ***commutative***, the group is not Abelian.
- $e = I$ which $x*e=x \space | \space e*x=x$ (***Neutral Element***)
- $y=x^{-1}$ which $x*y=e \space | \space y*x=I$