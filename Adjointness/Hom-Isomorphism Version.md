Two functors $F: D \mapsto C, G: C \mapsto D$ are said to be in an adjoint relationship $F \dashv G$ if there is a [[Natural Isomorphism]] between the functors $Hom(F(c), -)$ and $Hom(c, G(-))$ for any fixed $c \in D$ and functors $Hom(d, F(-))$ and $Hom(G(d), -)$ for any fixed $d \in C$... this is a correct def. but it is not the adjunction but something else...


### Mistake 1

I initially recalled something the def. to be:

there needs to be natural isomorphism between the functors $Hom(c, G(-))$ and $Hom(-, F(c))$ for any fixed $c \in X$ and functors $Hom(d, F(-))$ and $Hom(-, G(d))$ for any fixed $d \in Y$.

This definition came purely because it is type correct i.e. $Hom(c,G(-))$ is a functor from $Y$ to $Hom_X$ and $Hom(-, F(c))$ is a functor from $Y$ to $Hom_X$.
However, the first is a *controvariant functor* in $Y$ while the second is covariant, this is a hidden type problem.
Thus the only correct definition is the other "type correct" configuration:
$Hom(G(-), c) \cong Hom(-, F(c))$  
