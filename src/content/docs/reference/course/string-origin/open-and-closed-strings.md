---
title: "Open and Closed Strings"
description: "A minimal string-theory primer for AdS/CFT: open strings, closed strings, D-branes, Chan–Paton factors, and why gauge theory and gravity appear in one framework."
sidebar:
  order: 10
---

The previous units built two sides of the AdS/CFT story separately. On the boundary side, we found large-$N$ gauge theories, single-trace operators, and factorization. On the bulk side, we found Anti-de Sitter geometry, fields in AdS, and black holes. The next task is to explain why these two languages meet in the first place.

The answer in the canonical example is string theory.

This page is not a string theory course. It is a carefully chosen minimum: enough open strings, closed strings, and D-branes to understand why the D3-brane argument produces

$$
\mathcal N=4\;\text{super-Yang–Mills}
\quad\longleftrightarrow\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5 .
$$

The essential slogan is:

$$
\text{open strings give gauge theories},
\qquad
\text{closed strings give gravity},
$$

and D-branes are the objects that make both statements true at once.

## Why this matters

AdS/CFT did not arise by guessing that a random gauge theory should equal a random gravitational theory. It arose from a physical system with two complementary low-energy descriptions.

For a stack of D3-branes:

- the open strings ending on the branes give a four-dimensional gauge theory;
- the same branes also source a ten-dimensional closed-string gravitational field;
- in a suitable low-energy limit, the gauge-theory description and the near-horizon gravitational description describe the same degrees of freedom.

This is the historical and structural origin of the canonical correspondence. Later, the dictionary can be formulated abstractly, and many holographic lessons do not require constantly mentioning strings. But the string origin explains several facts that otherwise look mysterious:

- why the boundary theory is a gauge theory;
- why the bulk contains gravity;
- why the number of colors $N$ controls bulk quantum effects;
- why the 't Hooft coupling controls the bulk curvature in string units;
- why the strongest form of the duality is a string-theoretic statement, not merely an Einstein-gravity statement.

The figure summarizes the logic of this page.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Open strings on D-branes and closed strings in the bulk](/figures/course/open-closed-strings-branes.svg)

<figcaption>

Open strings have endpoints and can end on D-branes. Their massless modes give gauge fields and adjoint matter on the brane worldvolume. Closed strings have no endpoints and propagate through the bulk; their massless modes include the graviton and other supergravity fields. D-branes are the bridge: they support open-string gauge theories and also source closed-string gravitational fields.

</figcaption>
</figure>

## The string scale

A relativistic point particle traces out a worldline. A string traces out a two-dimensional worldsheet. The simplest classical string action is proportional to the area swept out by the string:

$$
S_{\rm string}
=
-T_s \int d^2\sigma\, \sqrt{-\det h_{\alpha\beta}},
$$

where $h_{\alpha\beta}$ is the induced metric on the worldsheet and $T_s$ is the string tension. The conventional normalization is

$$
T_s = \frac{1}{2\pi \alpha'},
\qquad
\ell_s = \sqrt{\alpha'}.
$$

Here $\ell_s$ is the string length. At energies much smaller than $1/\ell_s$, massive string excitations are hard to produce, and the theory can often be approximated by an ordinary field theory of the massless modes. At energies comparable to $1/\ell_s$, the extended nature of the string becomes visible.

This is the first appearance of a distinction that will recur throughout AdS/CFT:

$$
\text{low energy compared with }\ell_s^{-1}
\quad\Rightarrow\quad
\text{field theory or supergravity approximation},
$$

while

$$
\text{curvature radius comparable to }\ell_s
\quad\Rightarrow\quad
\text{stringy corrections are important}.
$$

In AdS/CFT, the ratio $L/\ell_s$ is controlled by the boundary 't Hooft coupling. Large $L/\ell_s$ means that the bulk curvature is small in string units, so the extended-string corrections are suppressed.

## Open strings and closed strings

There are two basic topologies for a single string.

An **open string** has two endpoints. Its worldsheet has boundaries. A convenient worldsheet coordinate choice is

$$
0 \leq \sigma \leq \pi,
\qquad
\tau \in \mathbb R,
$$

so the endpoints lie at $\sigma=0$ and $\sigma=\pi$.

A **closed string** has no endpoints. Its spatial worldsheet coordinate is periodic:

$$
\sigma \sim \sigma + 2\pi.
$$

This topological difference is not cosmetic. It determines the types of massless particles that appear after quantization.

Very schematically:

$$
\begin{aligned}
\text{open string massless modes}
&\longrightarrow
\text{gauge fields and matter on branes},
\\
\text{closed string massless modes}
&\longrightarrow
\text{graviton and other bulk fields}.
\end{aligned}
$$

In the AdS/CFT construction, both sectors are present in one theory. The open-string sector becomes the gauge theory on D-branes. The closed-string sector becomes the gravitational theory in the bulk.

## Closed strings contain gravity

The quickest way to see why string theory contains gravity is to look at the massless spectrum of a closed string. Closed-string excitations combine a left-moving oscillator and a right-moving oscillator. The first massless tensor excitation has the schematic form

$$
\alpha^M_{-1}\,\tilde\alpha^N_{-1}|0;k\rangle.
$$

The spacetime tensor product decomposes into symmetric, antisymmetric, and trace parts:

$$
\alpha^M_{-1}\tilde\alpha^N_{-1}|0;k\rangle
\quad\longrightarrow\quad
G_{MN},\quad B_{MN},\quad \Phi.
$$

Here:

- $G_{MN}$ is the spacetime metric fluctuation, whose quantum is the graviton;
- $B_{MN}$ is an antisymmetric two-form field;
- $\Phi$ is the dilaton, whose expectation value controls the string coupling.

In superstring theory there are also Ramond–Ramond fields, fermions, and supersymmetric partners. For the canonical AdS$_5$/CFT$_4$ example, we need type IIB string theory, whose massless closed-string fields include the metric, dilaton, two-forms, and a self-dual five-form field strength.

At energies low compared with $1/\ell_s$, the closed-string massless modes are described by a supergravity action. The schematic ten-dimensional scaling is

$$
S_{\rm closed,low\ energy}
\sim
\frac{1}{G_{10}}
\int d^{10}x\,\sqrt{-G}\,
\left(
R + \cdots
\right),
$$

with

$$
G_{10} \sim g_s^2 \ell_s^8
= g_s^2 \alpha'^4.
$$

The exact numerical convention often used in type II string theory is

$$
2\kappa_{10}^2 = (2\pi)^7 g_s^2 \alpha'^4,
\qquad
16\pi G_{10}=2\kappa_{10}^2.
$$

The important lesson is the scaling:

$$
G_{10} \propto g_s^2.
$$

Thus the string coupling $g_s$ controls closed-string quantum loops. Weak string coupling means weak quantum gravity in the bulk.

## The dilaton and the string coupling

The string coupling is not just a number inserted by hand. It is determined by the expectation value of the dilaton:

$$
g_s = e^{\Phi_0}.
$$

A spacetime-dependent dilaton corresponds to a spacetime-dependent effective string coupling. In the simplest AdS$_5\times S^5$ background, the dilaton is constant, so $g_s$ is constant.

This matters for the parameter map. In the canonical D3-brane duality, one finds schematically

$$
g_{\rm YM}^2 \sim g_s,
\qquad
\lambda = g_{\rm YM}^2 N \sim g_s N.
$$

The precise factor depends on conventions for normalizing the Yang–Mills action and generators. In the common AdS/CFT convention used later in this course,

$$
g_{\rm YM}^2 = 4\pi g_s,
\qquad
\lambda = 4\pi g_s N.
$$

That is why the combination $g_s N$, not just $g_s$, appears in the curvature radius of the D3-brane geometry.

## Open strings need endpoint conditions

Open strings have endpoints, so their variation requires boundary conditions. Split the ten-dimensional spacetime coordinates as

$$
X^M = (X^a, X^i),
$$

where $a=0,1,\ldots,p$ are directions along a D$p$-brane and $i=p+1,\ldots,9$ are directions transverse to it.

For an open string ending on the D$p$-brane, the endpoint is free to move along the brane but fixed in the transverse directions. The corresponding boundary conditions are

$$
\partial_\sigma X^a\big|_{\partial\Sigma}=0,
\qquad
\delta X^i\big|_{\partial\Sigma}=0.
$$

The first condition is a Neumann boundary condition. The second is a Dirichlet boundary condition. This is the origin of the name **D-brane**: a D-brane is a hypersurface defined by Dirichlet boundary conditions for open strings.

The brane has $p$ spatial dimensions and one time dimension, so its worldvolume has dimension $p+1$. A D3-brane has a $3+1$ dimensional worldvolume, which is exactly why D3-branes are the natural branes behind a four-dimensional gauge theory.

## Open strings give gauge fields

Quantizing an open string produces a tower of excitations. The massless open-string modes include a vector field along the brane,

$$
A_a(x),
\qquad
 a=0,\ldots,p,
$$

and scalar fields describing transverse fluctuations of the brane,

$$
X^i(x),
\qquad
 i=p+1,\ldots,9.
$$

In a supersymmetric theory there are also fermionic partners. At low energies, these massless modes are described by a gauge theory on the D-brane worldvolume.

For a single D$p$-brane, the gauge group is $U(1)$. For $N$ coincident D$p$-branes, the endpoints of an open string can begin on brane $i$ and end on brane $j$. These endpoint labels are called **Chan–Paton indices**:

$$
|\text{open string}\rangle
\quad\longrightarrow\quad
|\text{oscillators}; i,j\rangle,
\qquad
 i,j=1,\ldots,N.
$$

The massless fields therefore become $N\times N$ matrices:

$$
A_a(x)^i{}_j,
\qquad
X^i(x)^m{}_n.
$$

This is the open-string origin of non-Abelian gauge theory. The gauge group for $N$ coincident branes is typically $U(N)$, with fields in the adjoint representation.

In AdS/CFT one often focuses on the $SU(N)$ part. The overall $U(1)$ corresponds to the center-of-mass motion of the brane stack and decouples in the usual low-energy limit of the canonical example.

## Why coincident branes matter

If the $N$ branes are separated in transverse space, an open string stretching from brane $i$ to brane $j$ has a minimum length. Its energy is roughly

$$
E_{ij} \sim T_s |\Delta x_{ij}|
= \frac{|\Delta x_{ij}|}{2\pi\alpha'}.
$$

These stretched strings become massive. In the worldvolume gauge theory, this corresponds to moving onto the Coulomb branch, where the gauge group is broken:

$$
U(N) \longrightarrow U(1)^N
$$

for a generic separation.

When the branes coincide, the stretched strings can become massless. The non-Abelian gauge symmetry is restored. This is why coincident branes are the natural string-theoretic origin of matrix-valued gauge fields.

For D3-branes in type IIB string theory, the low-energy theory on $N$ coincident branes is four-dimensional $\mathcal N=4$ super-Yang–Mills theory. The six scalar fields of $\mathcal N=4$ SYM are precisely the six transverse fluctuations of the D3-branes inside ten-dimensional spacetime.

## D-branes are not just places where strings end

It is tempting to picture a D-brane as a fixed surface. That picture is useful, but incomplete.

D-branes are dynamical objects in string theory. They have:

- a worldvolume gauge theory from open strings ending on them;
- transverse scalar fields describing their motion;
- tension, so they carry energy and gravitate;
- Ramond–Ramond charge, so they source RR gauge potentials.

The D$p$-brane tension scales as

$$
T_p \sim \frac{1}{g_s\,\ell_s^{p+1}}.
$$

With the common type II normalization,

$$
T_p
=
\frac{1}{(2\pi)^p g_s \alpha'^{(p+1)/2}}.
$$

The factor $1/g_s$ is important. At weak string coupling, D-branes are heavy objects. They can be treated as classical sources for closed-string fields when the total charge or energy is large enough.

For a stack of many branes, the gravitational backreaction depends on a combination like

$$
g_s N.
$$

This is the first sign of the same combination that will become the 't Hooft coupling in the boundary gauge theory.

## Open–closed consistency

Open and closed strings are not two unrelated theories glued together by hand. In a consistent string theory with open strings, closed strings are generally unavoidable.

One way to see this is through the annulus diagram. Viewed in one direction, it is a one-loop open-string diagram. Viewed after a modular transformation of the worldsheet, the same surface is a tree-level closed-string exchange between two boundaries:

$$
\text{open-string one-loop annulus}
\quad = \quad
\text{closed-string tree exchange}.
$$

Schematically,

$$
Z_{\rm annulus}
=
\int_0^\infty \frac{dt}{2t}\,
{\rm Tr}_{\rm open}\,e^{-2\pi t(L_0-a)}
=
\int_0^\infty \frac{d\ell}{2\ell}\,
\langle B|e^{-2\pi \ell(L_0+\widetilde L_0-2a)}|B\rangle.
$$

Here $|B\rangle$ is a boundary state representing the D-brane as a source for closed strings. The exact constants are not important for us. The conceptual point is essential:

$$
\text{a D-brane is visible both to open strings and to closed strings}.
$$

This is the physical seed of the two-description argument behind AdS/CFT.

## Worldsheet topology and the coupling expansion

String perturbation theory is organized by worldsheet topology. For an oriented worldsheet with genus $h$ and $b$ boundaries, the Euler characteristic is

$$
\chi = 2 - 2h - b.
$$

The corresponding vacuum worldsheet weight scales as

$$
g_s^{-\chi}
=
g_s^{2h+b-2}.
$$

For closed strings without boundaries, $b=0$. Then a genus-$h$ worldsheet contributes with weight

$$
g_s^{2h-2}.
$$

Thus the closed-string loop expansion is controlled by powers of $g_s^2$:

$$
\text{sphere} \sim g_s^{-2},
\qquad
\text{torus} \sim g_s^0,
\qquad
\text{higher genus} \sim g_s^{2h-2}.
$$

After canonical normalization of external fields, the same expansion says that closed-string interactions are controlled by $g_s$ and closed-string loops by powers of $g_s^2$.

With D-branes, worldsheets can have boundaries. Each boundary can carry a Chan–Paton trace. For a stack of $N$ branes, this produces factors of $N$. This is why the combination

$$
g_s N
$$

naturally appears in the open-string description. On D3-branes, it becomes the gauge-theory 't Hooft coupling up to conventional numerical factors:

$$
\lambda = g_{\rm YM}^2 N \sim g_s N.
$$

So the field-theory large-$N$ expansion and the string worldsheet expansion are two faces of the same organizing principle.

## Low-energy limits

String theory contains infinitely many massive excitations. For AdS/CFT foundations, we usually begin by taking a low-energy limit.

The open-string low-energy limit gives a gauge theory on the brane:

$$
E\ell_s \ll 1
\quad\Rightarrow\quad
\text{massive open strings decouple},
$$

leaving the massless worldvolume fields. For D3-branes, this becomes four-dimensional $\mathcal N=4$ SYM.

The closed-string low-energy limit gives supergravity in the ambient spacetime:

$$
E\ell_s \ll 1
\quad\Rightarrow\quad
\text{massive closed strings decouple},
$$

leaving the metric, dilaton, form fields, and their superpartners.

These two limits are not independent when branes are present. Open strings on the brane can emit and absorb closed strings. Closed strings can feel the brane as a gravitational and RR source. The D-brane system contains both sectors.

The AdS/CFT decoupling argument will exploit this structure very carefully. It will take a low-energy limit in which the brane gauge theory decouples from ordinary asymptotically flat bulk gravity, while a near-horizon closed-string region remains. The claim of the duality is that those two surviving descriptions are equivalent.

## The two descriptions waiting behind the curtain

For $N$ coincident D3-branes in type IIB string theory, there are two useful weak-coupling descriptions before taking the full AdS/CFT limit.

First, if $g_s N$ is small, the branes do not strongly curve spacetime. The open-string description is natural. The low-energy theory on the branes is

$$
\mathcal N=4\; U(N)\;\text{super-Yang–Mills in }3+1\text{ dimensions},
$$

plus closed strings propagating in the surrounding ten-dimensional nearly flat spacetime.

Second, if $g_s N$ is large while $g_s$ itself remains small, the collective backreaction of the branes is strong even though string loops are suppressed. The closed-string gravitational description is natural. The branes are replaced by a classical D3-brane supergravity geometry.

The profound point is that these are two descriptions of the same underlying brane system. The near-horizon limit will turn the second description into

$$
\mathrm{AdS}_5\times S^5.
$$

The next few pages unpack this slowly:

$$
\text{D3-branes}
\quad\Rightarrow\quad
\begin{cases}
\text{open strings} & \Rightarrow \mathcal N=4\;\text{SYM},\\
\text{closed strings} & \Rightarrow \text{D3-brane geometry},
\end{cases}
$$

and then the decoupling limit identifies the two surviving low-energy descriptions.

## A useful hierarchy of approximations

It is helpful to separate four layers.

### Full string theory

The most complete statement involves all string modes, all loops, and all allowed backgrounds:

$$
\text{full open/closed string theory with D-branes}.
$$

This is the layer at which the D-brane construction truly lives.

### Low-energy open-string theory

At energies below the string scale, the open-string sector on D-branes reduces to a worldvolume field theory. For D3-branes, this is $\mathcal N=4$ SYM.

### Low-energy closed-string theory

At energies below the string scale, the closed-string sector reduces to supergravity. This approximation is reliable when curvatures are small in string units:

$$
\ell_s^2 |R| \ll 1.
$$

For AdS backgrounds, this means

$$
\frac{\ell_s^2}{L^2} \ll 1.
$$

### Classical gravity

Supergravity becomes classical when quantum loops are suppressed. In AdS units this is controlled by $G_N/L^{d-1}$, or equivalently by large $N$ in the boundary theory.

For the canonical example, the two conditions for classical two-derivative gravity are roughly

$$
N \gg 1,
\qquad
\lambda \gg 1.
$$

Large $N$ suppresses quantum loops. Large $\lambda$ suppresses stringy $\alpha'$ corrections.

## What survives into the AdS/CFT dictionary

Even when we stop explicitly talking about strings, three lessons survive.

First, **single-trace operators are single-string or single-particle states** in the bulk. In the supergravity limit, they are represented by bulk fields.

Second, **large $N$ is a bulk perturbation parameter**. Boundary factorization becomes weak bulk interactions.

Third, **large 't Hooft coupling is a curvature condition**. It makes the AdS radius large compared with the string length, suppressing the tower of massive string modes.

This is why the classical gravity approximation is powerful but limited. It captures the low-energy closed-string sector in a special limit. It does not erase the string-theoretic origin of the duality.

## Dictionary checkpoint

| String-theory concept | AdS/CFT role |
|---|---|
| string length $\ell_s=\sqrt{\alpha'}$ | scale of stringy corrections |
| string coupling $g_s$ | controls closed-string loops |
| closed string | bulk gravitational excitation |
| massless closed-string modes | metric, dilaton, form fields, supergravity multiplet |
| open string endpoint | degree of freedom living on a D-brane |
| Chan–Paton labels | matrix indices of gauge-theory fields |
| $N$ coincident D-branes | $U(N)$ or $SU(N)$ gauge theory |
| D3-brane worldvolume | four-dimensional spacetime of $\mathcal N=4$ SYM |
| D-brane tension and RR charge | source for closed-string supergravity fields |
| $g_sN$ | precursor of the 't Hooft coupling $\lambda$ |

The next page turns this checkpoint into a concrete object: the D-brane as seen by a field theorist.

## Common confusions

### “If closed strings give gravity, why do we need D-branes?”

Closed strings give the gravitational sector, but AdS/CFT needs a non-gravitational quantum theory with gauge degrees of freedom. D-branes supply that theory through their open-string sector. They also source the closed-string geometry. Without D-branes, the canonical derivation of AdS$_5$/CFT$_4$ would be missing the bridge between gauge theory and gravity.

### “Are open and closed strings independent particles?”

They are different string sectors, but they interact. Open strings can join and split. Open-string loop diagrams can be reinterpreted as closed-string exchange. In a consistent theory with D-branes, open and closed sectors are tightly linked.

### “Is a D-brane just a boundary condition?”

At weak coupling, it is often useful to define a D-brane by the boundary conditions it imposes on open strings. But a D-brane is also a dynamical object with tension, charge, worldvolume fields, and gravitational backreaction. Both viewpoints are needed for AdS/CFT.

### “Does the boundary CFT literally consist of open strings?”

In the D3-brane derivation, the gauge theory arises as the low-energy limit of open strings on the branes. Once the decoupled CFT is identified, one can study it as an ordinary quantum field theory. The open-string origin explains why it has the right fields and parameters, but the CFT does not require us to draw open strings in every calculation.

### “Is classical gravity the same as the closed-string sector?”

No. Classical gravity is a low-energy, weakly curved, weakly quantum approximation to the closed-string sector. The full closed-string sector includes massive string modes and quantum loops. In AdS/CFT language, these correspond to finite-$\lambda$ and finite-$N$ corrections.

### “Why do D3-branes give a four-dimensional theory?”

A D$p$-brane has $p$ spatial directions plus time, so its worldvolume dimension is $p+1$. A D3-brane has a $3+1$ dimensional worldvolume. The gauge fields living on it are therefore four-dimensional fields.

## Exercises

### Exercise 1: The dimension of $\alpha'$

The string tension is

$$
T_s = \frac{1}{2\pi\alpha'}.
$$

In units with $\hbar=c=1$, tension has dimensions of energy per length. What are the dimensions of $\alpha'$ and $\ell_s=\sqrt{\alpha'}$?

<details>
<summary><strong>Solution</strong></summary>

In natural units, energy has dimension inverse length. Tension is energy per length, so

$$
[T_s] = L^{-2}.
$$

Since

$$
T_s = \frac{1}{2\pi\alpha'},
$$

we have

$$
[\alpha'] = L^2.
$$

Therefore

$$
\ell_s = \sqrt{\alpha'}
$$

has dimensions of length. This is why $\ell_s$ is called the string length.

</details>

### Exercise 2: Boundary conditions for a D3-brane

A D3-brane in ten-dimensional flat spacetime extends along directions

$$
X^0,X^1,X^2,X^3.
$$

Write the Neumann and Dirichlet boundary conditions for an open string ending on the brane.

<details>
<summary><strong>Solution</strong></summary>

The endpoint is free to move along the brane directions, so

$$
\partial_\sigma X^a\big|_{\partial\Sigma}=0,
\qquad
 a=0,1,2,3.
$$

The endpoint is fixed in the transverse directions, so

$$
\delta X^i\big|_{\partial\Sigma}=0,
\qquad
 i=4,5,6,7,8,9.
$$

The six transverse directions later become the six scalar fields of $\mathcal N=4$ SYM, interpreted as fluctuations of the D3-brane stack.

</details>

### Exercise 3: Chan–Paton factors and matrix fields

For $N$ coincident D-branes, an oriented open string can start on brane $i$ and end on brane $j$. Explain why the corresponding massless fields are naturally $N\times N$ matrices.

<details>
<summary><strong>Solution</strong></summary>

The two endpoint labels are discrete indices:

$$
i,j=1,\ldots,N.
$$

A massless open-string field therefore carries two such labels:

$$
A_a(x)^i{}_j.
$$

This is exactly the index structure of an $N\times N$ matrix. The massless fields transform in the adjoint representation of the gauge group, usually $U(N)$ for $N$ coincident branes. This is the string-theoretic origin of matrix-valued gauge fields on a brane stack.

</details>

### Exercise 4: Why does separating branes make some strings massive?

Suppose two D-branes are separated by distance $r$ in a transverse direction. Estimate the energy of the lightest string stretched between them.

<details>
<summary><strong>Solution</strong></summary>

A string stretched between separated branes has minimum length approximately $r$. Its classical energy is tension times length:

$$
E \sim T_s r
= \frac{r}{2\pi\alpha'}.
$$

Thus strings connecting separated branes become massive. When the branes coincide, $r\to 0$, these stretched strings can become massless, enhancing the gauge symmetry.

</details>

### Exercise 5: Open-string annulus versus closed-string exchange

Explain in words why the annulus diagram suggests that D-branes source closed strings.

<details>
<summary><strong>Solution</strong></summary>

The same annulus worldsheet has two interpretations. If time runs around the loop of the annulus, it is a one-loop diagram of open strings. If time runs between the two boundary components, it is a tree-level closed string propagating between two boundary states.

The second interpretation says that each boundary behaves as a source or sink for closed strings. Since those boundaries represent D-branes, D-branes must couple to closed-string fields. In particular, they gravitate and source other supergravity fields.

</details>

### Exercise 6: The two ingredients of classical gravity

Use the schematic AdS/CFT relations

$$
\lambda \sim g_s N,
\qquad
G_{10}\sim g_s^2\ell_s^8.
$$

Explain why large $N$ and large $\lambda$ have different physical meanings in the bulk.

<details>
<summary><strong>Solution</strong></summary>

Large $\lambda$ means large $g_sN$. For D3-branes this controls the curvature radius in string units:

$$
\frac{L^4}{\ell_s^4} \sim \lambda.
$$

Thus large $\lambda$ makes the curvature small compared with the string scale and suppresses $\alpha'$ corrections.

Large $N$ suppresses bulk quantum effects. Since $g_s\sim \lambda/N$, taking $N$ large at fixed large $\lambda$ can make $g_s$ small. More invariantly, large $N$ makes the AdS radius large in Planck units, so gravitational loop corrections are suppressed.

Therefore large $\lambda$ gives a weakly curved string background, while large $N$ gives a weakly quantum bulk. Classical Einstein gravity needs both.

</details>

## Further reading

- J. Polchinski, [TASI Lectures on D-Branes](https://arxiv.org/abs/hep-th/9611050).
- J. Polchinski, [Dirichlet-Branes and Ramond–Ramond Charges](https://arxiv.org/abs/hep-th/9510017).
- J. M. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- C. V. Johnson, [D-Brane Primer](https://arxiv.org/abs/hep-th/0007170).
