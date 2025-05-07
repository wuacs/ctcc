A *Monoidal Category* $\textbf{C}$ is a category which has a *unit object* with respect to a *product functor* (often called tensor product, and noted $\otimes$), i.e. a functor $\otimes : \textbf{C} \times \textbf{C} \rightarrow \textbf{C}$.

It is called *monoidal* because the functor has some nice properties:

- There is a natural isomorphism between the functors $((-) \otimes (-)) \otimes (-)$ and $(-) \otimes ((-) \otimes (-))$ which represents associativity property of monoids.
- There is a natural isomorphism between functors $1 \otimes (-)$ and $Id_C$ 
- There is also a natural isomorphism between functors $(-) \otimes 1$ and $Id_C$


A special class of monoidal categories is that of [[Closed Monoidal Category]]
