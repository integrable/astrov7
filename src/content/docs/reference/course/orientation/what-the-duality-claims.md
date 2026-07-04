---
title: "What the Duality Claims"
description: "A precise first statement of AdS/CFT as an equivalence between a boundary quantum field theory and a bulk quantum gravity or string theory, including sources, states, limits, and common misreadings."
sidebar:
  order: 20
---

The previous page, [Why Holography?](../why-holography/), motivated holography from black-hole entropy, large-$N$ gauge theory, strong coupling, and Anti-de Sitter geometry. Motivation is useful, but AdS/CFT is not a metaphor. It is a claim of equivalence between two quantum theories.

This page states that claim carefully. The central lesson is that there are several layers of the statement:

$$
\text{exact quantum duality}
\quad \Longrightarrow \quad
\text{large-}N\text{ string/gravity expansion}
\quad \Longrightarrow \quad
\text{classical on-shell gravity recipe}.
$$

Many confusions come from replacing the first statement by the last one. The classical on-shell action is a powerful approximation. It is not the full duality.

## The canonical statement

The best-known example is

$$
\mathcal N=4\; SU(N)\;\text{super-Yang–Mills theory in four dimensions}
\quad
\longleftrightarrow
\quad
\text{type IIB string theory on } \mathrm{AdS}_5\times S^5 .
$$

The field theory has no dynamical gravity. The string theory has gravity. The claim is not that one theory approximately resembles the other in a certain calculation. The claim is that they are two descriptions of the same quantum system.

A compact way to write the conjecture is

$$
Z_{\mathrm{CFT}}[\text{sources on }\partial\mathrm{AdS}]
=
Z_{\mathrm{string}}[\text{asymptotic boundary data}].
$$

In the canonical example, the integer $N$ is the rank of the gauge group on the CFT side and the quantized five-form flux through the $S^5$ on the string side. The Yang–Mills coupling and theta angle combine into the complex coupling of the CFT, which is mapped to the axio-dilaton data of type IIB string theory.

This statement is strongest when read as an exact equivalence of complete quantum theories. The CFT supplies a nonperturbative definition. The bulk description becomes geometrical only in appropriate limits.

## The same theory, not two interacting theories

A first trap is to imagine a bulk theory and a boundary theory coupled across a wall. That is not the AdS/CFT claim.

AdS/CFT says that the two sides are two languages for one system. They should not be added together. One should not write

$$
S_{\mathrm{total}}
=
S_{\mathrm{bulk}}+S_{\mathrm{boundary}}
$$

as though the CFT were an extra material layer placed at the edge of AdS. Instead, the CFT is the non-gravitational description of the same physics that the bulk describes gravitationally.

The analogy is closer to electric-magnetic duality than to a boundary condition in ordinary field theory. In electric-magnetic duality, the same physics may be described using electric variables or magnetic variables. In AdS/CFT, the two descriptions are far more different: one has a dynamical spacetime and one does not.

## The data that must be specified

A precise holographic question begins by specifying the boundary data.

For a CFT, one specifies a spacetime manifold $M_d$, a conformal class of metrics $[g_{(0)}]$, a state or ensemble, and sources $J_a(x)$ coupled to operators $\mathcal O_a(x)$. A Euclidean generating functional can be written schematically as

$$
Z_{\mathrm{CFT}}[g_{(0)},J_a]
=
\int \mathcal D\Psi\,
\exp\!\left[
-S_{\mathrm{CFT}}[\Psi;g_{(0)}]
+
\sum_a\int_{M_d} d^d x\sqrt{g_{(0)}}\,J_a(x)\mathcal O_a(x)
\right].
$$

On the bulk side, one sums over fields, strings, branes, and geometries that approach the chosen boundary data near infinity. For an asymptotically locally AdS metric, one often writes near $z=0$

$$
ds^2
\sim
\frac{L^2}{z^2}\left(dz^2+g_{(0)\mu\nu}(x)dx^\mu dx^\nu+\cdots\right).
$$

For a scalar field dual to an operator of dimension $\Delta$, the corresponding asymptotic behavior is schematically

$$
\phi(z,x)
\sim
z^{d-\Delta}J(x)+\cdots .
$$

The source $J(x)$ is therefore not a random boundary decoration. It is the leading asymptotic datum of the bulk field. More generally, every boundary source fixes an allowed asymptotic behavior for a bulk field.

## The partition-function equality

With the previous data understood, the Euclidean version of the dictionary takes the form

$$
Z_{\mathrm{CFT}}[g_{(0)},J_a]
=
Z_{\mathrm{bulk}}\!\big[g\to g_{(0)},\;\phi_a\to J_a\big].
$$

The right-hand side is a quantum-gravity path integral with prescribed asymptotic behavior. In a full string-theory statement, this includes all stringy and quantum effects. In a semiclassical limit, it is approximated by a sum over saddle points:

$$
Z_{\mathrm{bulk}}[J_a]
\approx
\sum_{\text{saddles }s}
\exp\!\left[-S_{\mathrm{ren}}^{(s)}[J_a]\right].
$$

If a single classical saddle dominates, then

$$
W_{\mathrm{CFT}}[J_a]
\equiv
\log Z_{\mathrm{CFT}}[J_a]
\approx
-S_{\text{ren,on-shell}}[J_a].
$$

This is the form most often used for computations. It gives connected CFT correlators by functional differentiation:

$$
\langle \mathcal O_a(x)\rangle_J
=
\frac{1}{\sqrt{g_{(0)}(x)}}
\frac{\delta W_{\mathrm{CFT}}[J]}{\delta J_a(x)},
$$

and

$$
\langle \mathcal O_a(x)\mathcal O_b(y)\rangle_{c,J}
=
\frac{1}{\sqrt{g_{(0)}(x)}\sqrt{g_{(0)}(y)}}
\frac{\delta^2 W_{\mathrm{CFT}}[J]}
{\delta J_a(x)\delta J_b(y)}.
$$

In the classical gravity approximation, these derivatives are derivatives of $-S_{\text{ren,on-shell}}$. That is the seed of the GKP/Witten prescription.

## Three layers of the claim

<figure class="doc-figure" style="--figure-width: 52rem;">

![A layered diagram of AdS/CFT statements: exact quantum equivalence at the top, controlled large-N and large-coupling expansion in the middle, and the practical classical on-shell action recipe at the bottom.](/figures/course/duality-claims-map.svg)

<figcaption>

Three layers of the AdS/CFT claim. The exact duality is an equivalence of quantum theories with matched boundary data. The classical on-shell action formula is a controlled approximation in a special regime, not the definition of the full correspondence.

</figcaption>
</figure>

### Layer 1: exact quantum equivalence

At the deepest level, the duality identifies complete quantum theories. The spectra, correlation functions, partition functions, symmetries, and allowed states should agree after translating variables.

In a Hamiltonian language, for global AdS one expects an equivalence of Hilbert spaces of the schematic form

$$
\mathcal H_{\mathrm{bulk}}^{\mathrm{AdS}}
\simeq
\mathcal H_{\mathrm{CFT}}(S^{d-1}).
$$

This formula should be read carefully. The exact Hilbert space is most sharply defined on the CFT side. The phrase $\mathcal H_{\mathrm{bulk}}^{\mathrm{AdS}}$ refers to the quantum-gravity Hilbert space that, when a geometric bulk description is available, contains states interpreted as gravitons, strings, branes, black holes, and other bulk objects.

### Layer 2: large-$N$ and strong-coupling expansion

In the large-$N$ expansion, connected correlators of normalized single-trace operators are suppressed by powers of $1/N$. This is the boundary origin of weak bulk interactions.

In the canonical D3-brane example, the useful qualitative relations are

$$
\frac{L^4}{\alpha'^2}\sim \lambda,
\qquad
\frac{L^3}{G_5}\sim N^2,
$$

where $L$ is the AdS radius, $\alpha'$ is the string length squared, $G_5$ is the five-dimensional Newton constant after compactifying on $S^5$, and $\lambda=g_{\mathrm{YM}}^2N$ is the 't Hooft coupling.

Thus:

| Boundary limit | Bulk consequence |
|---|---|
| $N\to\infty$ | suppresses bulk quantum loops |
| $\lambda\to\infty$ | suppresses string-scale curvature corrections |
| finite $N$ | includes quantum-gravity corrections |
| finite $\lambda$ | includes stringy $\alpha'$ corrections |

The statement “AdS/CFT computes strongly coupled field theory using classical gravity” refers to the special corner where $N$ and $\lambda$ are both large.

### Layer 3: classical saddle-point dictionary

When a single smooth classical geometry dominates the bulk path integral, the dictionary becomes a boundary-value problem. Solve the classical bulk equations with prescribed asymptotic data, plug the solution into the renormalized action, and differentiate with respect to sources.

Schematically:

$$
J(x)
\quad\longrightarrow\quad
\phi_{\mathrm{cl}}(z,x;J)
\quad\longrightarrow\quad
S_{\text{ren,on-shell}}[J]
\quad\longrightarrow\quad
\langle \mathcal O\cdots\mathcal O\rangle_c.
$$

This is the practical form used in many computations, but it comes with assumptions: classical gravity must be valid, the variational problem must be well posed, counterterms must be added, and the relevant saddle or sum of saddles must be identified.

## What exactly is matched?

The duality matches more than partition functions. It matches structures.

### Symmetries

The isometry group of $\mathrm{AdS}_{d+1}$ is $SO(2,d)$, the conformal group of a $d$-dimensional CFT. For the canonical example,

$$
\mathrm{AdS}_5\times S^5
$$

also has an $SO(6)$ symmetry from the sphere, matching the $SO(6)_R\simeq SU(4)_R$ symmetry of $\mathcal N=4$ SYM.

Bulk gauge symmetries are redundancies, but gauge fields in AdS encode global currents in the boundary theory. The boundary value of a bulk gauge field is a source for a conserved current:

$$
A_{(0)\mu}
\quad\longleftrightarrow\quad
J^\mu_{\mathrm{CFT}}.
$$

Similarly, the boundary metric is the source for the CFT stress tensor:

$$
g_{(0)\mu\nu}
\quad\longleftrightarrow\quad
T^{\mu\nu}.
$$

### Spectra

States in the CFT on the cylinder $\mathbb R\times S^{d-1}$ are matched with states in global AdS. For a local primary operator of dimension $\Delta$, radial quantization gives a state whose cylinder energy is

$$
E_{\mathrm{cyl}}=\frac{\Delta}{L}.
$$

On the bulk side, this is interpreted as the global AdS energy of the corresponding excitation. For a scalar field, the more detailed relation is

$$
m^2L^2=\Delta(\Delta-d),
$$

which will be derived later.

### Operators and fields

A local single-trace operator is mapped, in a large-$N$ regime with a local bulk description, to a single-particle bulk field:

$$
\mathcal O_a
\quad\longleftrightarrow\quad
\phi_a.
$$

Multi-trace operators correspond to multiparticle states or composite bulk excitations. This statement becomes sharp only in the large-$N$ expansion, where the distinction between single-particle and multiparticle states is meaningful.

### States and geometries

The CFT vacuum on $\mathbb R\times S^{d-1}$ maps to global AdS. Thermal states map to AdS black holes or black branes. Excited coherent states may map to classical geometries. Generic high-energy states may not have a simple smooth geometric description, even though they are still valid CFT states.

This distinction is important:

$$
\text{every CFT state has a bulk interpretation}
\quad\not\Rightarrow\quad
\text{every CFT state has a smooth classical geometry}.
$$

## Boundary conditions, sources, and states

A second common trap is to confuse a source with a state.

For a scalar field in standard quantization,

$$
\phi(z,x)
\sim
z^{d-\Delta}J(x)+z^\Delta A(x)+\cdots .
$$

The coefficient $J(x)$ is fixed as part of the definition of the boundary problem. It is the source for $\mathcal O$. The coefficient $A(x)$ is determined after solving the bulk equations with appropriate regularity or state conditions, and it is related to $\langle \mathcal O(x)\rangle$ after renormalization.

Thus:

| Quantity | Role |
|---|---|
| $J(x)$ | source, fixed boundary datum |
| $A(x)$ | response, related to a one-point function |
| regularity condition | helps choose the state in Euclidean problems |
| incoming-wave condition | selects retarded response in black-hole backgrounds |
| normalizable excitation | often corresponds to changing the state rather than turning on a source |

The phrase “turn on a bulk field” is therefore ambiguous. Turning on the leading boundary coefficient is turning on a source. Exciting a normalizable mode is usually changing the state.

## Euclidean versus Lorentzian statements

The Euclidean version is the cleanest first statement because partition functions and saddle points are comparatively straightforward:

$$
Z_{\mathrm{CFT}}[J]
\approx
\exp[-S_{\text{ren,on-shell}}[J]].
$$

Lorentzian holography requires more care. One must specify the state, the time contour, and boundary conditions in the interior. In black-hole geometries, retarded Green's functions are obtained by imposing incoming-wave boundary conditions at the horizon. Other real-time correlators require other contours or prescriptions.

So the safe rule is:

$$
\text{Euclidean formulas do not automatically become Lorentzian formulas by replacing }t_E\text{ with }it.
$$

The Lorentzian dictionary is powerful, but it is not a one-line analytic continuation in all circumstances.

## Saddles, phases, and sums over geometries

In the classical approximation, it is tempting to say “the bulk geometry dual to the CFT state.” Sometimes that is correct. Sometimes it hides an important sum.

The bulk partition function with fixed boundary data may receive contributions from multiple saddles:

$$
Z_{\mathrm{bulk}}
\approx
\sum_s e^{-S_s}.
$$

A familiar example is a thermal CFT on $S^{d-1}$, whose Euclidean boundary is $S^1_\beta\times S^{d-1}$. The bulk may have different smooth fillings with the same boundary. At low temperature, thermal AdS can dominate. At high temperature, an AdS black hole can dominate. The exchange of dominance is the Hawking–Page transition.

From the boundary point of view, this is a phase transition in the large-$N$ thermal theory. From the bulk point of view, it is a change in the dominant saddle.

Thus the duality does not say that every boundary condition picks a unique classical geometry. The exact statement is the equality of partition functions. A unique geometry is an approximation when one saddle dominates.

## What the duality does not claim

### It does not claim that every CFT has a simple gravity dual

A weakly curved, local Einstein-like bulk requires special properties: large $N$, strong coupling in an appropriate sense, and a sparse spectrum of low-dimension single-trace operators. A generic CFT may have no useful classical geometric dual.

### It does not claim that the boundary theory is located inside the bulk

The CFT lives on the conformal boundary. It is not a brane sitting at finite radial position. Cutoff surfaces inside AdS can be useful regulators, but they are not the fundamental location of the exact CFT.

### It does not claim that bulk locality is exact

Local bulk fields are emergent effective variables. At finite $N$, exact local bulk observables are obstructed by quantum gravity and diffeomorphism invariance. Boundary correlators are the sharp observables; bulk locality is recovered approximately in the right regime.

### It does not claim that classical gravity is always enough

Classical gravity captures the leading large-$N$, large-$\lambda$ behavior in favorable examples. Quantum loops, stringy corrections, branes, topology change, and other nonclassical effects are part of the full duality.

### It does not claim that the two sides are usually weakly coupled at the same time

The usefulness of the correspondence often comes from strong/weak behavior. When the boundary gauge theory is strongly coupled and large $N$, the bulk may be weakly curved and classical. When the boundary theory is weakly coupled, the bulk is typically highly stringy.

## A minimal working dictionary

For the rest of the course, the following first-pass dictionary will be used repeatedly.

| Boundary concept | Bulk concept |
|---|---|
| CFT spacetime $M_d$ | conformal boundary of asymptotically AdS spacetime |
| boundary metric $g_{(0)\mu\nu}$ | asymptotic metric data |
| source $J_a$ | leading boundary coefficient of bulk field $\phi_a$ |
| operator $\mathcal O_a$ | bulk field $\phi_a$ |
| generating functional $W[J]$ | renormalized on-shell action in classical limit |
| scaling dimension $\Delta$ | bulk mass and spin data |
| CFT state on $S^{d-1}$ | bulk state in global AdS |
| thermal density matrix | black hole or black brane ensemble |
| global symmetry current | bulk gauge field |
| stress tensor | bulk metric fluctuation |
| large $N$ | small bulk Newton coupling |
| large gap / strong coupling | local weakly curved bulk effective theory |

Every entry in this table will be refined later. The table is a map, not a proof.

## A first example of the logic

Suppose a scalar operator $\mathcal O$ is coupled to a source $J$:

$$
Z_{\mathrm{CFT}}[J]
=
\left\langle
\exp\!\left(\int d^dx\sqrt{g_{(0)}}\,J(x)\mathcal O(x)\right)
\right\rangle .
$$

The dual bulk problem is to solve for a scalar field $\phi$ whose leading near-boundary behavior is fixed by $J$:

$$
\phi(z,x)\sim z^{d-\Delta}J(x)+\cdots .
$$

In the classical limit,

$$
Z_{\mathrm{CFT}}[J]
\approx
\exp[-S_{\text{ren,on-shell}}[J]].
$$

Therefore,

$$
\langle \mathcal O(x)\rangle_J
=
-\frac{1}{\sqrt{g_{(0)}(x)}}
\frac{\delta S_{\text{ren,on-shell}}[J]}{\delta J(x)}.
$$

The minus sign here follows from the Euclidean convention $W=\log Z\approx -S_{\text{ren,on-shell}}$. Other sign conventions are common, especially in Lorentzian signature, so one should always track the convention used in a given paper.

This simple chain is the prototype for many holographic calculations:

$$
\text{choose source}
\quad\to\quad
\text{solve bulk equations}
\quad\to\quad
\text{renormalize on-shell action}
\quad\to\quad
\text{differentiate}.
$$

## Dictionary checkpoint

The precise first claim of AdS/CFT is not “gravity lives in one more dimension.” It is:

$$
\boxed{
Z_{\mathrm{CFT}}[g_{(0)},J_a]
=
Z_{\mathrm{bulk}}[g\to g_{(0)},\phi_a\to J_a]
}
$$

with the understanding that the right-hand side is the full quantum string/gravity partition function, not merely the classical Einstein action.

The classical working approximation is:

$$
\boxed{
W_{\mathrm{CFT}}[J_a]
\approx
-S_{\text{ren,on-shell}}[J_a]
}
$$

when a single classical saddle dominates.

The conceptual translation is:

$$
\boxed{
\text{boundary sources define bulk asymptotics; boundary correlators are bulk responses.}
}
$$

This is the operational heart of the course.

## Common confusions

### “The bulk partition function is just the exponential of the Einstein action.”

Only in a restricted classical limit. The full bulk partition function includes quantum fluctuations, strings, branes, and possibly sums over topologies. Einstein gravity is the leading effective description in a special regime.

### “A bulk field value at a point is a CFT operator.”

A local bulk field is an emergent effective operator. The elementary CFT-side object is a boundary operator. Reconstructing local bulk fields from CFT data is subtle and approximate in the semiclassical regime.

### “The source is the same thing as the expectation value.”

No. The source is fixed as boundary data. The expectation value is the response. They are related dynamically, not identified.

### “The CFT only describes the boundary region of the bulk.”

No. The CFT describes the entire quantum-gravity system with the specified asymptotic boundary conditions, including the interior of AdS and black-hole regions when the corresponding bulk interpretation exists.

### “The duality is proven because many quantities match.”

There is overwhelming evidence in highly supersymmetric examples and many precise checks, but the statement is still usually called a conjecture. In practice, AdS/CFT is used both as a conjectural equivalence and as a definition of quantum gravity in asymptotically AdS settings via the better-defined CFT.


## How this page connects to the next one

This page stated what AdS/CFT claims. The next page, [Regimes of Validity](../regimes-of-validity/), asks when the useful approximations are justified. That is where the hierarchy

$$
\text{full string theory}
\supset
\text{classical string theory}
\supset
\text{classical supergravity}
\supset
\text{Einstein gravity}
$$

becomes a quantitative guide rather than a slogan.

## Exercises

### Exercise 1: The one-point function from the generating functional

Let

$$
Z[J]
=
\left\langle
\exp\!\left(\int d^dx\sqrt g\,J(x)\mathcal O(x)\right)
\right\rangle,
\qquad
W[J]=\log Z[J].
$$

Show that

$$
\langle \mathcal O(x)\rangle_J
=
\frac{1}{\sqrt{g(x)}}\frac{\delta W[J]}{\delta J(x)}.
$$

<details>
<summary><strong>Solution</strong></summary>

Vary $Z[J]$ with respect to $J(x)$:

$$
\frac{\delta Z[J]}{\delta J(x)}
=
\sqrt{g(x)}
\left\langle
\mathcal O(x)
\exp\!\left(\int d^dy\sqrt g\,J(y)\mathcal O(y)\right)
\right\rangle .
$$

Dividing by $Z[J]$ gives the expectation value in the presence of the source:

$$
\frac{\delta W[J]}{\delta J(x)}
=
\frac{1}{Z[J]}\frac{\delta Z[J]}{\delta J(x)}
=
\sqrt{g(x)}\,\langle \mathcal O(x)\rangle_J.
$$

Therefore,

$$
\langle \mathcal O(x)\rangle_J
=
\frac{1}{\sqrt{g(x)}}\frac{\delta W[J]}{\delta J(x)}.
$$

</details>

### Exercise 2: Why equality of actions is not the duality

A student says: “AdS/CFT means $S_{\mathrm{CFT}}=S_{\mathrm{gravity}}$.” Explain why this is not the right statement.

<details>
<summary><strong>Solution</strong></summary>

The two theories use different variables. The CFT action is a functional of boundary quantum fields, while the gravitational action is a functional of bulk metrics, fields, strings, and other degrees of freedom. The duality equates partition functions, correlation functions, spectra, and states after translating variables; it does not identify the two Lagrangians term by term.

In a classical gravity limit, one often writes

$$
W_{\mathrm{CFT}}[J]
\approx
-S_{\text{ren,on-shell}}[J],
$$

but this relates the CFT generating functional to the on-shell bulk action as a function of boundary sources. It is not an equality between the microscopic CFT action and the off-shell bulk action.

</details>

### Exercise 3: Source or state?

For a scalar field in standard quantization,

$$
\phi(z,x)\sim z^{d-\Delta}J(x)+z^\Delta A(x)+\cdots .
$$

Which coefficient is fixed as the source? Which coefficient is related to the response? What additional information is needed to determine $A(x)$ from $J(x)$?

<details>
<summary><strong>Solution</strong></summary>

The coefficient $J(x)$ is the source. It is fixed as part of the boundary condition for the bulk field. The coefficient $A(x)$ is related to the response, namely the expectation value $\langle \mathcal O(x)\rangle$, after holographic renormalization.

To determine $A(x)$ from $J(x)$, one must solve the bulk equations of motion and impose conditions that select the state or correlator. In Euclidean signature this often means regularity in the interior. In a Lorentzian black-hole background, retarded correlators require incoming-wave boundary conditions at the horizon.

</details>

### Exercise 4: Why multiple saddles matter

Suppose the same Euclidean boundary data admit two classical bulk saddles with renormalized actions $S_1$ and $S_2$. In the saddle approximation,

$$
Z\approx e^{-S_1}+e^{-S_2}.
$$

If $S_1<S_2$, which saddle dominates? What happens when the two actions cross as a function of temperature?

<details>
<summary><strong>Solution</strong></summary>

If $S_1<S_2$, then $e^{-S_1}$ is larger than $e^{-S_2}$, so saddle $1$ dominates. If the two actions cross as a function of temperature, the dominant saddle changes. In the large-$N$ limit, where actions are often of order $N^2$, this change can become a sharp phase transition.

The Hawking–Page transition is the standard example: thermal AdS and an AdS black hole are different bulk fillings of the same thermal boundary, and the dominant saddle changes at a critical temperature.

</details>

## Further reading

The following references are the main historical and technical anchors for the claims stated here.

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
