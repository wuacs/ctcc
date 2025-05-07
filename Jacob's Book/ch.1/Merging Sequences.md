Let us create the homomorphism which will capture the behavior $merge(\sigma, \tau)$ which will alternate by taking once an element from $\sigma$ and once from $\tau$.

Then:

let:
1. $merge(\sigma, \tau)=\langle \rangle$ if $\tau = \langle \rangle \land \sigma = \langle \rangle$
2. $merge(\sigma, \tau) = \langle a \rangle \cdot merge(\tau, \sigma')$ if $\sigma = \langle a \rangle \cdot \sigma'$ 
3. $merge(\sigma, \tau) = \langle a \rangle \cdot merge(\sigma, \tau')$ if $\tau = \langle a \rangle \cdot \tau'$ and $\sigma = \langle \rangle$

Then we defined coinductively merge by creating the appropriate ($A^{\infty} \times A^{\infty}, \rho$) Coalgebra defined over the functor $\perp + (A \times (-))$.

$\rho(\sigma, \tau) = \perp$ if $\sigma = \tau = \langle \rangle$
$\rho(\sigma, \tau) = (a, (\tau, \sigma'))$ if $\sigma = a \cdot \sigma'$
$\rho(\sigma, \tau) = (a, (\sigma', \tau ))$ if $\sigma = a \cdot \sigma' \land \tau = \langle \rangle$

#### Lemma

For each sequence $\sigma \in A^{\infty}$

$$
merge(even(\sigma), odd(\sigma)) = \sigma
$$

Proof (Brutal):

If $\sigma = \langle \rangle$ then merge $merge(\langle \rangle, \langle \rangle) = \langle \rangle$ by definition.

If $\sigma = \langle a \rangle$ then $merge(even(\langle a \rangle), odd(\langle a \rangle))=a \cdot merge(\langle \rangle, \langle \rangle)$ by def. of even and odd. $=\langle a \rangle$.

If $\sigma = \langle a,b  \rangle$ then $merge(even(\langle a, b \rangle), odd(\langle a, b \rangle))=\langle a \rangle \cdot merge(odd(\langle a, b\rangle), even(\langle \rangle))$ by def. of even and now by def. of odd $=\langle a, b \rangle \cdot merge(even(\langle \rangle), odd(\langle \rangle)) =\langle a, b \rangle \cdot merge(\langle \rangle, \langle \rangle) =\langle a, b \rangle$.

Then you can conclude by induction by chopping the first two elements of the sequences.

Proof (More elegant):

One can prove that the function $f: A^{\infty} \mapsto A^{\infty}$ s.t. $f(\sigma) = merge(even(\sigma), odd(\sigma))$ is the identity function. 
To prove this we simply need to show that this is a valid behavioral homomorphism for the Coalgebra NEXT, since we know the identity homomorphism $f(\sigma) = \sigma$ exists and there is only one homomorphism to the next Coalgebra.

If $\sigma=\langle \rangle$ then it is clear that they both correspond.

We need to prove that if $\sigma = \langle a , a' \rangle \cdot \sigma''$. Let's call $\sigma' = \langle a' \rangle \cdot \sigma''$.

then if
$\sigma' \mapsto^{a'} \sigma''$ we have $even(\sigma) \mapsto^a even(\sigma'')$ which means 
$f(\sigma)$
=
$merge(even(\sigma), odd(\sigma))$
$\mapsto^a$ 
$merge(odd(\sigma), even(\sigma''))$
=
$merge(even(tail(\sigma)), even(tail(\sigma')))$
=
$merge(even(\sigma'),odd(\sigma'))$
=
$f(\sigma')$


