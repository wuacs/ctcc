#### Definition 1
It is a fun way to say that Functors are related, I say F can be naturally transformed into G if for every object $x$ I can find an arrow (i call it portal) $F(x)\rightarrow G(x)$ which 

1. If i jump through the portal for x and take the arrow I end up the same as If i first take the arrow and then jump through the portal. I.e. the arrows F(f) and G(f) are related by those fixed portals.
2. A natural isomorphism is when the portal, other than being unique for each element, is also bidirectional.
#### Definition 2
$\alpha: F\mapsto G$, with Functors: $F,G: C\mapsto D$ is a natural transformation if we can give an assignment to every arrow $m: x \mapsto y$ in $C$ an arrow $\alpha_m: F(x) \mapsto G(y)$ such that for every $m_1,m_2, s.t. m_2\circ m_1: G(m_2) \circ \alpha_{m1} = \alpha_{m1} \circ F(m_2)$

[[naturaltransformation__seconddefinition.png]]

### Examples

#### List and Head

Imagine the Functors *List* and *Head*. The first maps a type A to the type $List\langle A\rangle$ while the second maps a type A to the type $Maybe\langle A\rangle$.

There is a natural transformation

List[A] -- η_A --> Maybe[A]
  |                   |
List(f)             Maybe(f)
  |                   |
  v                   v
List[B] -- η_B --> Maybe[B]

Where $\eta$ is the complete version of the *head* function i.e. extracts the head and returns it if it is non empty, otherwise returns Nothing.

**Remember**: an instance of a list is actually a (unique) type, so it makes sense to apply *head* to it.



