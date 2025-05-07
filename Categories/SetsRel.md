
#### Definition
We can define the category **SetsRel** by having as objects sets and, as morphisms $f: A \rightarrow B$ between two sets $A$ and $B$, relations between them.
Relations then, relate $x\in A$ with $y \in B$ $\iff$ the relations has the couple $(x, y)$.
Identity morphism is then the identity relation $(x, x)$.

#### Dagger property

The inverse operation on the morphisms "$(-)^\dagger$" gives rise to a functor $\textbf{SetsRel}^\text{op} \rightarrow \textbf{SetsRel}$.

We need to prove functoriality:

- Preservation of identity: $F(id_X)=id_{F(X)}$. the inverse of the identity relation is the identity relation, thus $F(id_X) = id_X$, and the functor does not change the objects so $F(X) = X$.
- Preservation of composition: $F(g \circ f) = F(f) \circ F(g)$.
	- $F(g\circ f)$ is the inverse of $\{(z, y) | \exists x . (z, x) \in f \land (x, y) \in g\}$ which is $\{(y, z) | \exists x . (z, x) \in f \land (x, y) \in g\}$. 
	- $F(g)$ is $\{(a, b) | (b, a) \in g\}$ while $F(f)$ is $\{(c, d) | (d, c) \in f\}$, their composition is $\{(a, d)| \exists b. (b, a) \in g \land (d, b) \in f\}$ which for $\phi(a)=y, \phi(b)=x, \phi(d)=z$.

#category #dagger_category