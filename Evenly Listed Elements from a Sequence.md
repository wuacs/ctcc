Let $A$ be an alphabet and consider the functor $\perp + (A \times -)$, we want to define a Coalgebra which tells us the *next even element from a sequence of elements*.

To define the Coalgebra we can proceed coinductively, that is, we define the unique homomorphism to the final Coalgebra which will set what is the "behavior" of the Coalgebra(i.e. to display only the even positions of any sequence).

Thus, the Coalgebra will be something of type: $f: A^{\infty} \mapsto \perp + (A \times A^{\infty})$.

The unique homomorphism $h: (A^{\infty}, f) \mapsto (A^{\infty}, next)$ needs to behave like this: 

1. If $next(\sigma)=\perp$ then $h(\sigma) = \langle \rangle$
2. If $next(\sigma) = (a, \sigma')$ and $next(\sigma')=\langle \rangle$ then $h(\sigma)=a \cdot \sigma'$
3. If $next(\sigma) = (a, \sigma')$ and $next(\sigma') = (b, \sigma'')$ then $h(\sigma) = a \cdot h(\sigma'')$

And clearly $h(\sigma)$ needs to return $\langle \rangle$ when $f(\sigma)=\perp$.
Also to respect the previous rules $f(\sigma) = (a, \sigma')$ then $h(\sigma) = a \cdot h(\sigma')$

Which implies 
$f(\sigma) = \perp$ if $\sigma = \langle \rangle$
$f(\sigma) = (a, \sigma')$ if $\sigma = \langle a \rangle \cdot \sigma' \land \sigma' = \langle \rangle$ (complicated way of saying $\sigma = \langle a \rangle$)
$f(\sigma) = (a, \sigma'')$ if $\sigma = \langle a, a' \rangle \cdot \sigma''$

