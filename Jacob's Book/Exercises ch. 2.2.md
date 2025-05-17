#### Exercise 2.2.1

Without the identity functor we cannot refer to $X$ in $F(X)$ thus every set is mapped to some algebraic combination of $+, \times, \mathcal{P}, (-)^A$ for fixed sets $A, B$. This implies every objects becomes the same and every morphism thus becomes the identity morphism making this functor isomorphic to the constant functor.

#### Exercise 2.2.2

1. For $S \mapsto A + (A \times S)$ skewed trees.
2. For $S \mapsto A + (A \times S) + (A\times S \times S)$ possibly unbalanced binary trees

#### Exercise 2.2.3

$$
\boxed{X \mapsto P(1+(A\times X)) \cong P(1) \times P(A \times X) \cong 2 \times P(A \times X) \cong 2 \times P(X)^A}$$

The first congruence was proven in [[Exercises ch. 2.1#Exercise 2.1.10]], the second one is clear from the definition of powerset of a set of 1 element(empty-set and the singleton), the third one implies $P(A \times X) \cong P(X)^A$ which has been proven on page 58 for non-finite powerset functor $P$.
#### Exercise 2.2.4

We need to provide the arity functor equivalent to the functor:

$\boxed{X \mapsto B + (X \times A \times X)}$.

Let $I = \{b_i | \forall b_i \in B\} \cup \{x_1\cdot a\cdot x_2\}$.

Then $\#(b_i)=0 \forall b_i, \#(a_i) = 2 \forall a_i$
it becomes $F^{\#}_I= \amalg_{i\in B}(1) + \amalg_{i\in A}X \times X$

$\boxed{X \mapsto A_0 \times X^{A_1} \times (X \times X)^{A_2}}$

for finite sets $A_1, A_2$

say $|A_1| = n$ and $|A_2| = m$ then say $\#(a_1) = n$ and $\#(a_2) = 2m$

then let us have the set of symbols $a_i \forall a_i \in A_0$ where $\#(a_i)=0\forall i$

we know $X^{A_1}\cong = X\times X...$(n times) so $F^{\#}_{\{a_1\}} \cong X^{A_1}$

and $(X \times X)^{A_2}\cong X\times X..$(2m times) so $F^{\#}_{\{a_2\}}\cong (X\times X)^{A_2}$

thus we need to sum those arities obtaining the set $I = \{a_{1,2,i} \forall a_i|  \#(a_{1,2,i})=n+m\}$

we obtain $F^{\#}_{I} = \amalg_{a_i}(X^{n+m})$.

#### Exercise 2.2.5

We can exploit the already written proof for bijection in the general case written at page 51.

We need to check the cases where we use coproducts of arbitrary size, in the case of the constant functor we had the mapping to $\amalg_{a\in A}X^{\#a}$ but since $A$ is finite the number of arities symbols are finite too.

For the product between two arity functors with number of arities symbols $n, m$ we have the new arity functor with $n\times m$ arity symbols which is still finite.

For the coproduct case, using the inductive hypothesis on the sub-functors we have that the new number of arities is simply their sum, which is still indeed finite.

#### Exercise 2.2.6

Note here the definition of [[Dependent Polynomial Functor]]
##### Part 1 

Identity:

$F(Id_X)(i, g) = (i, h)$ such that $h(a) = Id_X(g(a)) = g(a)$ i.e. 
$F(Id_X)(i, g) = (i, g)$.

Composition:

$F(f \circ z)(i, g) = (i, h)$ such that $h(a) = (f \circ z)(g(a)) = f(z(g(a))$
i.e. $(i, h)=F(f)(i, z \circ g) = F(f)\circ F(z) (i, g)$.


##### Part 2

So we work inductively on the structure of the simple polynomial functor:

1. The identity functor $F(X) = X$ we set $I=\{1\}$ then every object become the morphic points of every objects and it is well known that they are isomorphic.
2. The constant functor $F(X) =A$ we set $I = \emptyset$ then our category is made of only the empty-set.
3. Let G + H and by induction say we have the dependent version of G and H then let $A=A_G\cup A_H$ clearly since we can behave like G or H because the coproduct is maintained we can simulate $G + H$
4. For $G \times H$ we need $A = \{A_i + A_j \forall A_i \in A_G, A_j \in A_H\}$: you can see this congruence from $\amalg_{i, j \in A}X^{A_i + A_j} \cong \amalg_{i, j \in A}X^{A_i} \times X^{A_j}\cong \amalg_i( X^{A_i} \times \amalg_j X^{A_j})$ which by inductive hypothesis is $\cong \amalg_i(X^{A_i}\times H)\cong H \times (\amalg_i(X^{A_i}))\cong H \times G$
