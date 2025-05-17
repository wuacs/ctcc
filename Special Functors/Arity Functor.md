Let:
$I$ be a set
$\#: I \mapsto \mathbb{N}$
$F_{\#}(X)\coloneqq \amalg_{i\in I}{X^{\#(i)}}$ is a functor $\text{Sets} \rightarrow \text{Sets}$
where $X^{\#(i)}$ represents the power functor which sends $X$ to $1 \times X \times X ... \times X$($\#(i)$ + 1 times).

We can have $I$ to represent operations, for example, the algebraic sum has arity 2
thus its arity functor sends $X$ to $X \times X$
however, if we had another operation, say, complement, with arity 1 we would have $I= \{+, -\}$
with $\#(+) = 2$ and $\#(-)=1$
then we would send $X$ to $X \times X + X$

#### Single sort Arities

When the arity function is $I \mapsto \mathbb{N}$ we can only capture functors single sorted i.e. which go from $X \times X...$(n times) to $X$.

However, if we wanted to change the types we would need a set of types (or sets) $S$ and $\#: I \mapsto S^*$ where $S* = S \times S^+$.

#### Finite arity

A finite arity functor is an arity functor where $I$ is finite.
