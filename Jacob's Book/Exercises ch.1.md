From Intro to Coalgebra: Towards Mathematics of States and Observations

#### Exercise 1.1.1

**Part 1**

1. Suppose $s_1(x) = x' \in S$ 
	1. Suppose $s_1; s_2 (x)\neq \perp$ 
		1. $s_1;(s_2;s_3) (x) = s_2;s_3 (x') = s_3(x'')$ where $x''=s_2(x')$ and $(s_1; s_2); s_3 (x) = s_3(x'')$
	2. Suppose instead $s_1; s_2(x) = \perp$ then:
		1. $s_1;(s_2;s_3)(x) = s_2; s_3(x') = \perp$ because $s_2(x') = \perp$, and by same reasoning, $(s_1;s_2);s_3(x) = \perp$. 
2. Suppose $s_1(x) = \perp$ then:
	1. $s_1; (s_2; s_3) (x) = \perp$ and $(s_1; s_2)(x) = \perp$ which implies $(s_1;s_2);s_3(x)= \perp$

**Part 2**

$\verb|skip(x) = x|$ for both Coalgebras

#### Exercise 1.1.2

We define the composition as follows: if $s_1: S \mapsto \mathcal{P}(S)$ and $s_2: S \mapsto \mathcal{P}(S)$ then $s_1; s_2(x) = \cup\{s_2(y) | y \in s_1(x)\}$.

The **skip** statement is just the map $x \mapsto \{x\}$.

We need to prove the unit property:
$s_1;\verb|skip|(x) = \cup\{\verb|skip|(y)| y \in s_1(x)\}= \cup\{y | y \in s_1(x)\} = s_1(x)$.
$\verb|skip|;s_1(x) = \cup\{s_1(y) | y \in \verb|skip|(x)\} = \cup\{s_1(y) | y = x\} = s_1(x)$.


Proving that $beh_c(x)$ is an unique homomorphism.

1. If $c(x) = \perp$ then $beh_c(x) = \langle \rangle$ thus $next\circ beh_c(x) = \perp$.
2. If $c(x) \neq \perp$ we might have $beh_c(x)$ mapped to a finite sequence or an infinite sequence.
	1. In the case of finite sequences $\langle a_0, ..., a_{m-1}\rangle$:
		1. Let $c(x_0) = (a_0, x_1)$. Assume it holds for the shorter suffixes $\langle a_i, ..., a_{m-1}\rangle, i \gt 0$  that $beh_c(x_i) = \langle a_i ,..., a_{m-1}\rangle$, which allows us to prove $next \circ beh_c(x_0) = (a_0, beh_c(x_1))$ because by definition $next(\langle a_0, ..., x_{m-1}\rangle) = (a_0, \langle a_1, ..., a_{m-1} \rangle)$ and by inductive hypothesis we have $beh_c(x_1) = \langle a_1, ..., a_{m-1} \rangle$.
	2. Similarly for infinite sequence.

To prove uniqueness proceed as follows: let $g, beh_c$ be two distinct homomorphisms. Then if $c(x) = \perp$ we need $g(x) = beh_c(x) = \perp$ for commuting.

Say $c(x) = (a, x')$ and $g(x) = \langle a, ..., a_{m} \rangle$ and $beh_c(x) = \langle a,...,a'_m\rangle$ by induction on the sequences length we discover that $a_i = a'_i \forall i \in[1..m]$.

For infinite sequences $beh_c(x) = \langle a'_1, ...\rangle$ and $g(x) = \langle a_1,...\rangle$we get that by noting that if we want to prove $a_i = a'_i$ we can just prove by induction that they behave the same on $j \in i$ first elements. By simply noting that they need to agree always on the head because of *next*.

#### Exercise 1.2.2

See [[Oddly Listed Elements from a Sequence]]

#### Exercise 1.2.3

I guess we need to define a Coalgebra and let the behavior of its homomorphism to next need to describe the empty sequence.

So ... $m: \{\perp\} \mapsto \perp + \{A \times \{\perp\}\}=\perp$...?

For the constant sequence just 

do $m(\perp) \mapsto (a, \perp)$

#### Exercise 1.2.5


*Prove that merge is not associative*

If you pick $\sigma=\langle a \rangle$, $\tau = \langle b \rangle$, $\rho=\langle c\rangle$;

you have the left associative:
$merge(\sigma, merge(\tau, \rho))$
$\rightarrow^a merge(merge(\tau, \rho), \sigma')$
$\rightarrow^b merge(\sigma', merge(\rho, \tau')$

and the right associative:
$merge(merge(\sigma, \tau), \rho)$
$\rightarrow^a merge(\rho, merge(\tau, \sigma'))$
$\rightarrow^c merge(merge(\tau, \sigma'), \rho')$

*Is there a neutral element for merge?*

Yes, it is the empty list.

#### Exercise 1.2.6

*Show how to define an alternative merge function which alternatingly takes two elements from its arguments sequences*

$merge^2: A^{\infty}\times A^{\infty}\mapsto A^{\infty}$ is just $merge^2(\sigma, \tau) = merge(merge(even(\sigma), even(\tau)), merge(odd(\sigma), odd(\tau))$

#### Exercise 1.2.8

comp is the behavior of the following Coalgebra:

$$m(\sigma, \tau) = \begin{cases}
\perp & \text{if } \sigma \nrightarrow \land \tau \nrightarrow,\\
(a, (\sigma', \tau))  & \text{if } \tau \nrightarrow \land \sigma \rightarrow^a \sigma',\\
(a, (\sigma, \tau'))  & \text{if } \sigma \nrightarrow \land \tau \rightarrow^a \tau'.
\end{cases}$$
To show $comp(\langle \rangle, \sigma) = \sigma$

we need to show that $comp$ is the identity homomorphism.

To do this simply we show that if $\sigma \rightarrow^a \sigma'$ then $comp(\langle \rangle, \sigma) \rightarrow^a (\langle \rangle, \sigma'')$.
I think it is enough to show $m$ definition above.

#### Exercise 1.2.9

By the use of finality we show a Coalgebra which induces the behavior of applying $f$ element-wise.

$$m^f(\sigma) = \begin{cases}
\perp & \text{if } \sigma \nrightarrow\\
(f(a)
, \sigma')  & \text{if } \sigma \rightarrow^a \sigma'
\end{cases}$$

Proof of $(g \circ f)^{\infty} = g^{\infty}\circ f^{\infty}$. 

We need to show that, $head((g\circ f)^{\infty}\sigma) = head(g^{\infty} \circ f^{\infty} (\sigma))$, if $\sigma = \langle a \rangle \cdot \sigma'$
i.e.: $head((g\circ f)^{\infty}\sigma)=g\circ f(a) = g(head(f^{\infty}(\sigma))) = head(g^{\infty}\circ f^{\infty} (\sigma))$

And that tails correspond (using co-induction):

$tail((g \circ f)^{\infty} \sigma) = (g\circ f)^{\infty}(\sigma') = \text{coinductive hypothesis } = g^{\infty}\circ f^{\infty}\sigma' = tail((g^{\infty}\circ f^{\infty}) \sigma)$.

Since the Coalgebra is the same, the homomorphism, being unique, must be the same.

#### Exercise 1.2.10

To do this we just need to define a Coalgebra $st^b: A^{\infty} \times B \mapsto (A \times B) \times (A^{\infty} \times B)$: 

$$
st^b(\sigma) = ((a, b), \sigma') \text{ if } \sigma = \langle a\rangle \cdot \sigma'
$$
by finality an homomorphism exists which exhibits the desired behavior