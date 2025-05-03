It is almost identical to [[Evenly Listed Elements from a Sequence]] the only difference being the rules for the homomorphism $odd$.

1. If $next(\sigma)=\perp$ then $odd(\sigma) = \langle \rangle$
2. If $next(\sigma) = (a, \sigma')$ and $next(\sigma')=\langle \rangle$ then $odd(\sigma)=\langle \rangle$
3. If $next(\sigma) = (a, \sigma')$ and $next(\sigma') = (b, \sigma'')$ then $odd(\sigma) = b \cdot odd(\sigma'')$

Then we have that the Coalgebra $f$ needs to respect

$f(\langle \rangle) = \perp$ 
$f(\sigma)=\perp$ if $\sigma = \langle a \rangle \forall a \in A$ 
$f(\sigma) = (a, \sigma'')$ if $\sigma=\langle b, a\rangle \cdot \sigma''$ 


#### version using evens $\circ$ tails

We can define $odd$ as the composite morphism $tail \circ even$ where $even$ was the unique homomorphism for a even picking Coalgebra defined here [[Evenly Listed Elements from a Sequence]].

Define $tail(\sigma) = \sigma'$ if $\sigma = \langle a \rangle \cdot \sigma'$ otherwise $tail(\langle \rangle)=\langle \rangle$

One needs to prove that using the $f$ defined above

1. $even \circ tail (\sigma) = odd(\sigma) = \perp$ when $f(\sigma) = \perp$
2. Let $f(\sigma)=(a, \sigma'')$ then one needs to prove that $even \circ tail (\sigma) = a \cdot (even \circ tail(\sigma'')) = a \cdot odd(\sigma'') = odd(\sigma)$

To prove 1(the first two axioms of the odd homomorphism):
$f(\sigma) = \perp$ iff $\sigma = \langle \rangle$ or $\sigma = \langle a \rangle$.
In the first case the empty list is a fix-point of tail and $even$ returns $\perp$ on empty list.
$Odd$ behaves like $even$ for empty lists.
In the second case, tail of the singleton list returns the empty list, while $odd$ of a singleton list returns $\perp$ by def.

To prove 2:
It is sufficient to prove that $even \circ tail$ satisfies the third rule for the $odd$ homomorphism.
Namely that:

If $next(\sigma) = (a, \sigma')$ and $next(\sigma') = (b, \sigma'')$ then $odd(\sigma) = b \cdot odd(\sigma'')=even \circ tail(\sigma)$  
By hypothesis $\sigma = \langle a, b \rangle \cdot \sigma''$ and tail of it is $\sigma'$. Thus $tail \circ even(\sigma) = \langle b \rangle \circ tail \circ even (\sigma'')$ which is exactly the third axiom of the $odd$ homomorphism.
Which completes the proof.