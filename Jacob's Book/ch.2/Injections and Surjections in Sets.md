#### Lemma 1  - Functors

Let $F: \textbf{Sets} \rightarrow \textbf{Sets}$ be a functor, then:

1. If $f: X \rightarrow Y$ is surjective then so is $F(f)$
2. If $f: X\rightarrow Y$ is injective, and $X$ is non-empty then so is $F(f)$

Proofs:

1. By the [[Categorical Axiom Of Choice]] we have a splitting which we can apply the functor $F(f \circ s) = F(id_Y) = id_{F(Y)}$ i.e. $F(f)$ has a right inverse i..e it is surjective.
2. By again the use of the axiom of choice, we have $h$ which returns $x_0$ in case of no mapping. Then $F(h) \circ F(f) = F(h \circ f) = F(Id_{X})= Id_{F(X)}$