#### Definition
A weak pullback in a category $C$ is associated to three objects $X, Y, Z$, and two morphisms $f: X \mapsto Z, g: Y \mapsto Z$: 

- it consists of an object $Wk_{xy}$ and two morphisms $w_x$ and $w_y$ such that $f \circ w_x = g \circ w_y$
- for every object $K$ and pair of morphisms $k_1: K \mapsto X, k_2: K \mapsto Y$ there exists a morphism $h: K \mapsto Wk_{xy}$ such that $k_1 = w_x \circ h$ and $k_2 = w_y \circ h$ 

#### Functor Preserving Weak Pullbacks

A functor is said to *preserve weak pullbacks*, if and only if, given the objects $X, Y, Z$ and the morphisms $f: X \mapsto Z, g: Y \mapsto Z$ if this is a weak pullback, then objects $F(X), F(Y), F(Z)$ and morphisms $F(f), F(g)$ represent also a weak pullback.

##### Kripke Polynomial Functors preserve weak pullbacks

Let $F: \textbf{Set} \mapsto \textbf{Set}$ be a Kripke polynomial functor, then $F$ preserves weak pullbacks.
Proof:
1. **Id** it is clear
2. **Q**: it is the constant functor thus it is trivially satisfied.
3. **A+B**: by structural recursion on A, and B:
	1. Note that $A+B(w_x \circ \pi_x) = A+B(w_x) \circ A+B(\pi_x) =A(w_x) + B(w_x) \circ A(\pi_x) + B(\pi_x)$ Note that $A+B(w_y \circ \pi_y) = A+B(w_y) \circ A+B(\pi_y) =A(w_y) + B(w_y) \circ A(\pi_y) + B(\pi_y)$
	2. Now, for $x \in A(Wk)$, $A+B(w_x \circ \pi_x) (x) = A(w_x) \circ A(\pi_x)$ and $A+B(w_y \circ \pi_y) (y) = A(w_y) \circ A(\pi_y)$ by induction hypothesis those two commute.
	3. Similarly we do for $x \in B(Wk)$.
	4. Then we can conclude the property holds for $A+B(Wk)$.
	5. Now we need to prove the existence of the morphism from any set $K$ and functions $k_1$ 
4. **A x B**: very similar to the above.
5. $\mathcal{P}^{fin}(A)$: very briefly: the commutativity holds by simply noting that the morphism $A(w_x\circ \pi_x)=\rho$ commutes with $A(w_y \circ \pi_y)=\tau$ for the structural hypothesis and that $\mathcal{P(\rho)}$ is simply $\rho$ but applied on a subset of $Wk$ which commutes with $\tau$ applied on the same subset. For the witness part of the definition of weak pullback simply consider that $h(x) = \mathcal{P}(h'(x))$ where $h'$ is the morphisms associated with morphism $k_1': B \mapsto A(X)$ which exists by structural hypothesis. Same thing done for $k_2$.
6. **Exponential**, $F^A$: again by structural hypothesis is easy to see why the commutativity holds. Idea for the witness part: simply map to functions which for a given input behave in the same way they would behave on the underlying functor $F$.
