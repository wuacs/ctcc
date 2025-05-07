#### Categorical Formulation

*==Every surjection==* $f: X\twoheadrightarrow Y$ has a *section*(or *splitting*) i.e. a function $s: Y \rightarrow X$ in the reverse direction such that $f\circ  s= id$ this $s$ has to choose an element in the non-empty set $f^{-1}(y) = \{x | f(x) = y\}$.

*==Every injection==* $g: X \rightarrowtail Y$ (with $X \neq \emptyset$) then there is a function $h: Y \rightarrow X$ such that $h \circ g = Id$.
This function is defined as follows $h(y) = x'$ if there is one unique element $x'$ with $g(x') = y$ or $h(y) = x_0$ otherwise where $x_0$ is any element in $X$ which exists because $X$ is non-empty(the axiom of choice stays in finding this $x_0$)
#### properties
- $s: Y\rightarrow X$ is an injection by the properties of maps.
- $h: Y \rightarrow X$ is a surjection.