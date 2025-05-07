#### Exercise 2.1.2

By universal property of products, if there is $k \le c, d$ then we have a morphism to $c \times d$ element which symbolizes the $\le$ relation 
Same thing for the coproducts,  where now the morphism comes into the Coproduct while the two inclusion morphisms represent that $c, d$ any other $c, d \le k$ must have a morphism pointing to $c + d$.

#### Exercise 2.1.4

- For $X \mapsto A \times X$: 
	- $F(f): F(X) \mapsto F(Y)$ = $F(f)((a, x)) = (a, f(x))$ 
	- $F(Id_X)((a, x)) = (a, x) = F(X)$
	- $F(f \circ g)(a, x) = (a, f \circ g(x)) = F(f)(a, g(x))=F(f)\circ F(g)(a, x)$
- For $X \mapsto A + X$:
	- $F(f): F(X) \mapsto F(Y) = F(f)(y, 1)=(y, 1)$ and $F(f)(y, 2)=(f(y), 2)$
	- $F(Id_X)((y, 1))=(y,1)$ and $F(Id_X)=((y,2))=(Id_X(y), 2)=(y, 2)$
	- $F(f \circ g)((y,1)) = (y,1)$ and $F(f \circ g)(y,2)=(f\circ g(y), 2)=F(f)(g(y), 2)) = F(f) \circ F(g) (y,2)$
- For $X \mapsto X^A$
	- $F(f): F(X) \mapsto F(Y) = F(f)(k) = f \circ k$
	- $F(Id_{X})(k)=Id_{X}\circ k = k$
	- $F(f \circ g)(k) = f \circ g \circ k = f \circ (g \circ k) = F(f)(g \circ k) = F(f) (F(g)(k)) = (F(f) \circ F(g))(k)$

#### Exercise 2.1.5

From page 59. we need to show the existence of finite products, exponents and finite coproducts.

For the product:

1. Define $A\times B$ has the set of $(a,b)$ and define the poset as $(a,b) \le (a', b')$ iff $a \le a'$ or $b\le b'$
2. Let $Z$ be an object and two morphisms $f: Z \mapsto A, g: Z \mapsto B$.
3. Define the morphism $\langle f, g\rangle: Z \mapsto A \times B = \lambda (a,b). (f(a), f(b))$
4. Uniqueness is proved because any other morphism $t: Z \mapsto A\times B$ s.t. $t(x) = (\pi_A \circ t(x), \pi_B \circ t(x)) = (f(x), g(x))=\langle f, g \rangle(x)$
5. Finite product is defined by induction: $(A_1 \times A_2 ... \times A_n) \times A_{n+1}$

For the exponential:

1. Define $A^B$ as the object which has the following relation between $f: B \rightarrow A$, $f': B \rightarrow A$ is defined as $f' \le f$ if and only if $\forall x f'(x)\le f(x)$.
2. Let the evaluation map $ev: (Y^X \times X)\mapsto Y$ which we need to prove to be monotone. $ev((f, x)) =f(x) \le f(x') \le f'(x') = ev((f', x'))$ 
3. Let the abstraction map $\Delta(f)(z) = \{g | \exists f: C \times B \rightarrow A, g(x) = f(z, x)\}$ which has type $\Delta(f) : Z \mapsto A^{B}$
4. We need to prove, for any monotone map $f: Z \times X\rightarrow Y$, $ev \circ (\Delta(f) \times Id_X) (z, x) = ev(\Delta(f)(z), x) = ev(\Delta(f)(z), x)=\Delta(f)(z)(x)=f(z, x)$  
5. Say $g$ is another morphism which makes $ev \circ g = f$. Then $ev \circ g (z, c) = ev (\pi_1(g(z, c)), \pi_2(g(z,c))) = \pi_1(g(z, c))(\pi_2(g(z,c))) = f(z, c) = (\Delta(f)(z))(c)$
	1. Thus $\pi_1(g(z, c))=(\Delta(f)(z)$ and $\pi_2(g(z,c))=c= Id_X(c)$

For the Coproduct:

1. Define $A+B$ as usual set with objects tagged where the partial orders do not interact. I.e. $(a, 1) \in (A+B) \forall a \in A$ and $(a, 1) \le_{A+B} (a', 1) \iff a \le_A a'$ and $(b, 2)\in (A+B) \forall b \in B$ and $(b, 1) \le_{A+B} (b', 1)$
2. Let $k_A$ be the inclusion $A \rightarrow A + B$ such that $f(a) = (a, 1)$ which is clearly a monotone map because it is basically the identity map.
3. Let $Z$ be an object and $f: A \rightarrow Z$ and $g: B \rightarrow Z$ be two monotone maps, then let $[f,g]$ be the monotone map defined as $[f,g](x) =f(a))\text{ if } x=(a,1)$, and $=f(b) \text{ if } x=(b,2)$. this is clearly monotone because f and g are monotone. And it is unique because say another $g: A+B \rightarrow Z$ existed then $g((a, 1)) = f(a) = [f,g](a,1)$ and $g((b,2))=g(b)=[f,g](b,2)$

#### Exercise 2.1.6

1. It is clearly final, it is enough to map every object to the the singleton. For it to be initial we find the map which simply maps the identity element(i.e. the singleton) to the identity element in the in-going monad.
2. Let $Z$ be any other *Monoid* and let $f: Z \mapsto M_1, g: Z \mapsto M_2$ be a pair of *Monoid Homomorphism* then we define the homomorphism $\langle f, g\rangle: Z \mapsto M_1 \times M_2$ to be $\langle f, g\rangle (z) = (f(z), g(z))$
	1. We need to prove that this is a Monoid Homomorphism, i.e. that :
		1. It preserves composition: $\forall x, y \in Z, \langle f, g \rangle (x \otimes_Z y) = \langle f, g \rangle (x) \otimes_{M_1 \times M_2} \langle f, g \rangle (y)$ which comes from $\langle f, g \rangle (x) \otimes_{M_1 \times M_2} \langle f, g \rangle (y) =^\text{by def.} (f(x)+_{M_1}f(y), g(x) +_{M_2} g(y))=^\text{Assuming f, g to be hom.}(f(x \otimes_Z y), g(x \otimes_Z y))=\langle f, g\rangle(x \otimes_{Z} y)$
		2. It preserves identity: $\langle f, g\rangle (0_Z)=(f(0_Z), g(0_Z))=^\text{assuming f,g to preserve}=(0_1, 0_2)=0_{M_1\times M_2}$
3. $M_1 \times M_2$ also satisfies the coproduct universal property. Let $f: M_1\rightarrow Z$ and $g: M_2 \rightarrow Z$ be any two *Monoid Homomorphisms* then define $[f,g]: M_1\times M_2 \rightarrow Z$ to be $f(x)$ if $x \in M_1$ or else $g$.
#### Exercise 2.1.7

Let's prove that $0 \mapsto X \times 0$ is an isomorphism.
$0$ in $\textbf{Sets}$ is the empty set, thus the product $X \times 0$ is in fact the empty set, thus this morphism is the identity morphism for $0$ making it an isomorphism.

Let's prove that $(X\times Y)+(X \times Z) \rightarrow(Id_X \times k_1, id_X\times k_2)\rightarrow X\times(Y + Z)$ is an ISO.
Assume $X, Y, Z$ non-empty.
Create the function $f: X \times (Y+Z)$ s.t. $f(a, c)=k_{X\times Y}(a,k^{-1}_1(c))$ if $c \in Y$ and $f(a, c) = k_{X \times Z}(a, k^{-1}_2(c))$ if $c \in Z$. $k^{-1}_{1}$ and $k^{-1}_2$ can be defined to be the reverse of the injective map $k_1, k_2$ for elements from Y(or Z) and map elements from Z(Y) to any element(which exists since we assumed the sets to be non-empty).   
Now, $[Id_X \times k_1, Id_X \times k_2](a,c)$ if $(a,c) \in (X \times Y)$ is $Id_X \times k_1(a,c)=(a, k_1(c))$ and $f(a, k_1(c))=(a, c)$.

#### Exercise 2.1.8

##### Part 1

Let $C$ be a category with finite products ($\times$, 1), prove that the following are isomorphisms:

- $X\times Y \cong Y \times X$:
	- Consider this [diagram](https://tikzcd.yichuanshen.de/#N4Igdg9gJgpgziAXAbVABwnAlgFyxMJZARgBoAGAXVJADcBDAGwFcYkQANAAgB0e8AtvC4BNEAF9S6TLnyEU5UsWp0mrdhwlSQGbHgJEyAJhUMWbRCBG9+WIXC6bJ0vXKJGlptRasSVMKABzeCJQADMAJwgBJEUQHAgkMlVzdj40LAB9AA8QGkZ6ACMYRgAFGX15ECwwbFgtcKiYxA94xMRks3VLdKzc-KKS8tcDSxq6tmcQSOikVoSkAGYaLp9ezIBPPJAC4rKKtzHarHqpmea4hcRllO6Qda2BveHZUerj0+1z2Jor1sYaj4oBAcDgAttVmkeAUwIFGDAuGFSIE+BF6LD4dtdkMDm9xidJpRxEA) the morphism $\langle f, g \rangle$ exists by universal property of products and is defined as $\langle f, g\rangle(x, y) = (y, x)$. The arrow in the other direction is instead $\langle f,g\rangle^{-1}(y, x) = (x, y)$ their composition $\langle f,g\rangle \circ \langle f, g \rangle^{-1}(y, x)$ is the identity morphism on $Y \times X$
- $(X\times Y)\times Z \cong X \times (Y \times Z)$
	- Let $f: (X\times Y)\times Z \rightarrow X \times (Y \times Z)$ be defined as $f(x, y) = (\pi_x(x), (\pi_y(x), y)$
	- And $f': X \times (Y \times Z) \rightarrow (X\times Y)\times Z$ be defined as $f'(x, y) =((x, \pi_y(y)), \pi_z(y))$
	- Then $f \circ f'(x, y) = f((x, \pi_y(y)), \pi_z(y)) = (\pi_x(x, \pi_y(y)), (\pi_y(x, \pi_y(y)), \pi_z(y))=(x, (\pi_y(y), \pi_z(y))=(x, y)$
	- And similarly can be shown that $f' \circ f(x, y) =(x, y)$
- $1\times X\cong X$
	- Consider this [diagram](https://tikzcd.yichuanshen.de/#N4Igdg9gJgpgziAXAbVABwnAlgFyxMJZARgBoAGAXVJADcBDAGwFcYkRiACAHW7wFt4nABogAvqXSZc+QinKkATNTpNW7YuMkgM2PASKKlKhizaIQoiVL2yiZACwm15y+JUwoAc3hFQAMwAnCH4kBRAcCCQyVTN2AEIQGkZ6ACMYRgAFaX05ECwwbFgtAODQxHDIpCNY9QteNCwAfVFktIzs2wMLAqK2axAgkKQAZhoqippTOpBeFLAvRhh4ltIASSgWgEokkBT0rJy7HsKsYoGh8rGIqMQa6dcNlt39jqPu-NPz7UvR8duYg8Es82gdOjIPr0zv0fmUwv8-iB0mAoKNwq9Dl08lDilMXOw5vQFktOCthKQeNxGi1eIEiYsYJSAMZYQJMynU1ogOAACyw-hw0TElDEQA) it is evident that $\langle !_X, Id_X\rangle; ((\langle !_X, Id_X\rangle) \pi_X) (x)=\pi_X\langle !_X(x), Id_X(x)\rangle=x$ and that $(\pi_X); \langle !_X, Id_X\rangle(*, x)=\langle !_X, Id_X\rangle x=(!_X(x), x)=(*, x)$
	 The last part, i.e.  $*=!_X(x)$ comes from the fact that the composite morphism $\pi_x; !_X: 1\times X \mapsto 1$ must be equal to $\pi_1 = Id_{1}: 1\times X \mapsto 1$ by uniqueness of the morphisms from any object to the final object.

##### Part 2
#todo

#### Part 3
- $Z^{X+Y}\cong Z^X\times Z^Y$: 
	- Define $\Psi: Z^{X+Y} \mapsto Z^X \times Z^Y$
		- By universal property of products define $\Psi(f) = \langle f \circ \iota_x, f \circ \iota_y\rangle$
	- Define $\Phi: Z^X \times Z^Y\mapsto Z^{X+Y}$
		- This is the hard part.
		- We don't define directly $\Phi$ but we define it starting from *how* it behaves, i.e. we define $\Phi': Z^X\times Z^Y \times (X + Y)$
		- To do it consider the [following diagram](https://tikzcd.yichuanshen.de/#N4Igdg9gJgpgziAXAbVABwnAlgFyxMJZARgBoAGAXVJADcBDAGwFcYkQAdDuAWyceAAtAHoANLnh7wABCICa0iVilxpAClEBqOQEoAviD2l0mXPkIpypYtTpNW7Lr37A1I8R0kz5OxZ+UyogZGJth4BEQATNa2DCxsiCBuYn5eqj6pAapyhsYgGGHmRGSRsfYJIIKGtjBQAObwRKAAZgBOEDxIZCA4EEhWIIz0AEYwjAAKpuEWIFhg2LAgNHEOiWoAklCkfvg49AD6ojq5Le2diNE9fYgDQ6MTU0WJcwtsy+XsG1s7EHv7uicQG0Ol0aL0kABmGh3MaTQoRZ7zLCLd7xRwcNAACywhwAvDBaPtgEEuABjLCtUnqLhoHHEJQqaSbQ7HEJAs5IS7gxBQuxoxI07H-XHSAn-MkU0lqGk4yKZRnMgHQkawx4IwYwZo4QHA84Dbm8lYVZCCnEAD22pv2AE9KEtBiqHvCZi9kWw9JQ9EA) which commutes by coproduct universal property. Basically since our category is a [[Bicartesian Closed Category]] by assumption, it is a [[distributive category]].
		- Let $\phi'=[\phi_X, \phi_Y]$
		- By the [[exponential adjunction]] which is valid in any [[Cartesian Closed Category]] $Hom(A \times B, C)\cong Hom(A, B^C)$ if we consider $A=Z^X \times Z^Y$ and $B=(X+Y)$ we have that there must exist $\phi^*$ s.t. $ev_{X+Y}\circ (\phi^* \times Id_{X+Y})=\Phi'$.
		- Take $\Phi=\phi^*$.
	 	- Then we need to prove that $\Psi \circ \Phi=Id_{Z^X \times Z^Y}$
