- [[Powerset Functor]]

### Preservation Properties

### An algebraic characterization

$\boxed{\textbf{Theorem: }\text{The collections of simple polynomial functors and arity functors are isomorphic}}$

(See also [[Arity Functor]], [[Simple Polynomial Functor]])

$\boxed{\textbf{Proof:}}$

The proof goes by induction on the length of the functor.

1. Identity functor $Id$: to have this functor represented by an arity functor we need a singleton set $I =\{1\}$ where $\#(1) = 1$ and we get $F^{\#}(X) = X^1=X$
2. Constant functor $A$: the category result of applying the constant functor collapses each set into one only with only one morphism: the identity. If we choose $I=\{0\}$ where $\#(0)=0$ we have $F^{\#}(X)=1$
3. The Sum functor $G + H$: we suppose to have $I$ such that $F^{\#}_I\cong G$ and $F^{\#}_{I'} \cong H$ then we can make $I''= I \sqcup I'$ and prove that this is isomorphic to G+H:
	1. $$ G + H \cong F^{\#}_{I} + F^{\#}_{I'} = F^{\#}_{I\sqcup I'}$$
4. The product functor $G \times H$: we suppose to have $I$ such that  $F^{\#}_I\cong G$ and $F^{\#}_{I'} \cong H$ then let $I''= I \times I'$ i.e. $\forall x \in I, y \in I', xy\in I''$ and $\#(xy) = \#x+\#y$ 
	1. Then $\amalg_{(i, i')\in I\times I'}(X^{\#i+\#i'})\cong \amalg_{(i, i')\in I\times I'}(X^{\#i}\times X^{\#i'})\cong\text{Sets is distributive} \cong \amalg_{i\in I}(X^{\#i}\times \amalg_{i'\in I'} X^{\#i'})$$\cong \amalg_{i\in I}(X^{\#i})\times \amalg_{i' \in I'}( X^{\#i'})\cong \text{ inductive hypothesis} \cong G \times H$ 
	


#list