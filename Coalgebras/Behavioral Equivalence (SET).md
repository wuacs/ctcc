Here the definition of Bisimulation is the [[Lifting-Span Bis Aczel-Mendler|Aczel Mendler one]] where of course we don't use spans for relations but instead subsets of $\mathcal{P}(A \times B)$ because we work in **Set**.

Let $F: Set \mapsto Set$ be a functor such that its induced Coalgebra has a final object ($\Omega, w$).
Let $(X, f)$ and $(Y, g)$ be two F-Coalgebras.
We say $x\in X$ and $y \in Y$ are F-behaviorally equivalent ($\sim_{F}$) if and only if their unique homomorphisms to $(\Omega, w)$ map x and y to the same element in $\Omega$.

#### Condition on being behaviorally equivalent
$x_1 \sim_F x_2$ if and only if there exists an F-Coalgebra $(Y, g)$ and an homomorphism $h: (X, f)\mapsto (Y,g)$ such that $h(x_1) = h(x_2)$.

Proof:
$\implies$ choose as the F-Coalgebra the final Coalgebra.
$\impliedby$ Consider [this](https://tikzcd.yichuanshen.de/#N4Igdg9gJgpgziAXAbVABwnAlgFyxMJZABgBpiBdUkANwEMAbAVxiRAA0QBfU9TXfIRRkATFVqMWbAGKcefbHgJER5cfWatEIADo6A8gFsYAczrdeIDIsErSY6hqnbpeo6fPyr-JUOQAWNUdJLRAATQsFAWUUQIcJTRkIrnEYKBN4IlAAMwAnCEMkMhAcCCQARi88gqRVErLEAGYq-MLEcupSpGbLarbirsQ6hiwwUKgIJgAjBlZqAAsYOigkMCYGBk66LAY2SDHIkD6kQPra6hGD7QmcHDTD48QAVk6GnpzWk9ekJ5aaxAGDVOUxgYBWTWKl3GEFu9wWS3B4AIrBSXCAA) the dashed composite morphism which starts from X goes to Y and ends in $\Omega$ must be equal to the doubled morphism as the homomorphism to a final Coalgebra is unique.

#### Bisimulation implies Behavioral Equivalence

Let $R \subseteq A \times B$ be an F-Bisimulation for Coalgebras; if $(a, b) \in R$ then $a \sim_F b$.

The proof is trivial, we only need to note that for the final Coalgebra any homomorphism must be unique, thus the relation is a sort of intermediary between the two homomorphisms which guarantees that they are mapped to the same element in the final Coalgebra.

#### Behavioral Equivalence implies Bisimulation for Weak Pullback preserving Functors

If F is a weak pullback preserving functor, $x \in A \land y \in B$ and $x \sim_F y$ then there exists a F-Bisimulation $R\subseteq A \times B$ where $(x, y) \in R$.

Proof:

First note that if we define the relation $R$ as the set of all *behaviorally equivalent* elements then R forms a weak pullback on the object 4-tuple ($R, A, B, \Omega$) and morphisms $\pi_A; h$, $\pi_b; k$ where $h, k$ are the unique homomorphisms from Coalgebras (A, $\gamma$), (B, $\rho$) to the final Coalgebra ($\Omega, \tau$).

It is like that because any other object B which makes the cone commute will necessarily map some element to X and to Y. To make the cone commute it means those elements are mapped to the same element in $\Omega$, i.e. they are behaviorally equivalent.

Then, since R is a weak pullback, by hypothesis, F preserves pull-backs.

Observe the diagram: [Here](https://tikzcd.yichuanshen.de/#N4Igdg9gJgpgziAXAbVABwnAlgFyxMJZARgBoAGAXVJADcBDAGwFcYkQAxACgCUBKEAF9S6TLnyEUZYtTpNW7HkJEgM2PASLlSAJlkMWbRCACCy0eolEdu-fKMgAQudViNkkrZoGFxgDp+APIAtjAA5vQuauKaUqQAzHaG7NwBIeH0AsIWMR7aid72KVwmWSrR7tYJSb6cXI5ZsjBQYfBEoABmAE4QwUhkIDgQSDYgjPQARjCMAApuVsZYYNiwIIXJ-n5oWAD6Ztkg3b1IACw0Q0gArAdHfYijF4gAbOu1ARHBwZE041Oz87EQEsVmwbj07vFzsNEAB2V4OAJdAAWwx+k2mc0sgOBWFWYOOzyhVx+SwcUAgOBwzTWcg2dSRAjRf0xuXYOLxKluIyJiDOY1J7HJlOp8PYSJpvwxAMkQOWuLYNDgSKwHRwSHI+IhPL5kv+WJl7IVtNqAGsJQLjEKqVAXFzYTzLiSwGSKdaaT4HNwTYyxui9azFnKOZ1wf0eZDjQitrtnEypfq2UHQZzQ4gBo9tPznYKIMwJowjUiYPQbYgwMxGIxzvQsIx2JBs4rlar1aLjEbdSzKoGQbbU5nHi8QFMwKWALQwoed6WJ3ttuoBbZ7MohgkD6Fw4cwUdIGEADnnqWjOwaEr9XYWst7gkogiAA)

The arrow from $R$ to $F(R)$ which makes $e; F(\pi_A); F(h)=\pi_A; \gamma; F(h)$ commute exists because of the preservation of the pullback by F.
And same thing for $e;F(\pi_B);F(k)=\pi_B;\rho;F(k)$.

#bisimulation




