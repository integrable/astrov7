---
title: "Single-Trace and Multi-Trace Operators"
description: "Gauge-invariant operator bases, large-N counting, multi-particle states, operator mixing, and the AdS interpretation."
sidebar:
  order: 2
---

## Goal

The previous page introduced generalized free fields: the universal leading behavior of normalized single-particle operators in a large-$N$ CFT. This page explains where those operators come from in matrix large-$N$ theories and how their products become the multi-particle Hilbert space of AdS.

The slogan is

$$
\boxed{
\text{trace number in the CFT}
\quad\longleftrightarrow\quad
\text{particle number in AdS}
\qquad (N=\infty).
}
$$

This slogan is powerful, but it must be handled carefully. “Single trace” is a microscopic label in gauge theories. “Single particle” is the more invariant holographic idea. At large $N$, the two notions usually coincide in familiar matrix theories such as $\mathcal N=4$ super-Yang-Mills, but the exact statement is about the organization of the CFT Hilbert space and OPE data.

By the end of this page, the following dictionary should feel natural:

$$
\mathcal O_A
\quad\longleftrightarrow\quad
\text{one-particle bulk state},
$$

$$
[\mathcal O_A\mathcal O_B]_{n,\ell}
\quad\longleftrightarrow\quad
\text{two-particle bulk state},
$$

$$
[\mathcal O_{A_1}\cdots\mathcal O_{A_p}]
\quad\longleftrightarrow\quad
\text{$p$-particle bulk state}.
$$

Finite-$N$ corrections are equally important. They make particles interact, generate anomalous dimensions, and mix operators with the same quantum numbers.

## The basic matrix-theory picture

In a large-$N$ gauge theory, the elementary fields are matrices in color space. For example, an adjoint scalar of an $SU(N)$ gauge theory can be written as

$$
\Phi(x)=\Phi^a(x)T^a,
$$

or, in explicit color indices, as

$$
\Phi^i{}_j(x),
\qquad
i,j=1,\ldots,N.
$$

Gauge-invariant local operators are built by contracting color indices. The simplest contractions are traces:

$$
\operatorname{Tr}\Phi^2,
\qquad
\operatorname{Tr}\Phi^3,
\qquad
\operatorname{Tr}\left(F_{\mu\nu}F^{\mu\nu}\right),
\qquad
\operatorname{Tr}\left(\Phi D_\mu\Phi D_\nu\Phi\right).
$$

A **single-trace operator** has one color trace. A **double-trace operator** is a product of two traces at the same spacetime point, after renormalization and projection onto a conformal primary. A **multi-trace operator** is a product of several traces.

Schematic examples are

$$
\mathcal O_A(x)
\sim
\operatorname{Tr}\left(\Phi^{L_A}\right)(x),
$$

$$
\mathcal O_A(x)\mathcal O_B(x)
\sim
\operatorname{Tr}\left(\Phi^{L_A}\right)(x)
\operatorname{Tr}\left(\Phi^{L_B}\right)(x),
$$

and

$$
\mathcal O_A(x)\mathcal O_B(x)\mathcal O_C(x)
\sim
\operatorname{Tr}\left(\Phi^{L_A}\right)
\operatorname{Tr}\left(\Phi^{L_B}\right)
\operatorname{Tr}\left(\Phi^{L_C}\right)(x).
$$

The word “schematic” matters. Operators with derivatives, spin, flavor indices, $R$-symmetry indices, and fermions require projections onto irreducible Lorentz and internal-symmetry representations. In a CFT, one ultimately wants conformal primaries, not merely arbitrary products of fields.

## Normalization convention

There are several conventions in the literature. In this course, unless stated otherwise, a single-trace primary $\mathcal O_A$ is normalized so that

$$
\langle \mathcal O_A(x)\mathcal O_B(0)\rangle
=
\frac{\delta_{AB}}{x^{2\Delta_A}}.
$$

With this normalization, connected correlators of single-trace primaries scale as

$$
\boxed{
\langle \mathcal O_{A_1}\cdots\mathcal O_{A_k}\rangle_{\rm conn}
\sim
N^{2-k}.
}
$$

Equivalently, since holographic matrix theories have $C_T\sim N^2$,

$$
\langle \mathcal O_{A_1}\cdots\mathcal O_{A_k}\rangle_{\rm conn}
\sim
C_T^{1-k/2}.
$$

Thus

$$
\langle \mathcal O_A\mathcal O_B\rangle\sim N^0,
\qquad
\langle \mathcal O_A\mathcal O_B\mathcal O_C\rangle\sim \frac{1}{N},
$$

and

$$
\langle \mathcal O_A\mathcal O_B\mathcal O_C\mathcal O_D\rangle_{\rm conn}
\sim
\frac{1}{N^2}.
$$

This is the normalization in which single-trace operators behave as generalized free fields at $N=\infty$.

If one uses unnormalized traces, powers of $N$ move into the definition of the operator. That is harmless, but it often obscures the holographic dictionary. The invariant statement is the scaling of normalized correlators.

## Where the counting comes from

The origin of the scaling is the double-line expansion. In a matrix theory, propagators carry two color lines. A Feynman graph can be drawn as a two-dimensional surface. The power of $N$ is determined by the topology of that surface.

A connected genus-$g$ contribution with $k$ normalized single-trace insertions scales as

$$
N^{2-2g-k}.
$$

The leading contribution is planar, $g=0$, so

$$
\langle \mathcal O_{A_1}\cdots\mathcal O_{A_k}\rangle_{\rm conn, planar}
\sim
N^{2-k}.
$$

This is the CFT side of the string perturbation expansion:

$$
\frac{1}{N}
\quad\leftrightarrow\quad
\text{string coupling},
$$

and, in a theory with a classical gravity limit,

$$
\frac{1}{N^2}
\quad\leftrightarrow\quad
G_N.
$$

More precisely, in AdS units,

$$
G_N\sim \frac{R_{\rm AdS}^{d-1}}{C_T}.
$$

So the same parameter that suppresses connected correlators suppresses bulk quantum gravity effects.

## Single trace means one-particle, not necessarily supergravity

A single-trace operator creates one object in the bulk. That object may be a light supergravity particle, a Kaluza-Klein mode, a massive string excitation, or something heavier. The word “particle” here means one bulk quantum, not necessarily a low-energy graviton-like excitation.

For example, in $\mathcal N=4$ SYM, half-BPS single traces have the schematic form

$$
\mathcal O_p^{I}(x)
\sim
C^I_{i_1\cdots i_p}\operatorname{Tr}
\left(\Phi^{i_1}\cdots\Phi^{i_p}\right)(x),
$$

where $C^I$ projects onto a symmetric traceless representation of $SO(6)_R$. These operators are dual to Kaluza-Klein modes on $S^5$.

Other single traces, such as operators with many derivatives or large spin-chain excitation number, can be dual to stringy states rather than supergravity fields. At strong 't Hooft coupling, many such stringy single-trace operators become heavy. A sparse low-dimension single-trace spectrum is one of the signals that the bulk effective theory is local and gravitational at low energies.

Thus the refined dictionary is:

| CFT object | Bulk object |
|---|---|
| light single-trace primary | light one-particle field in AdS |
| heavy single-trace primary | massive stringy one-particle state |
| stress tensor $T_{\mu\nu}$ | graviton |
| conserved current $J_\mu$ | gauge field |
| double-trace primary | two-particle state |
| $p$-trace primary | $p$-particle state |

The stress tensor is special because of Ward identities, but holographically it is still a single-particle operator: it creates the graviton.

<figure class="doc-figure" style="--figure-width: 45rem; --caption-width: 55rem;">

![Single-trace and multi-trace dictionary](/figures/cft/single-trace-multi-trace-dictionary.svg)

<figcaption>

At $N=\infty$, normalized single-trace primaries behave as one-particle creators, while multi-trace primaries behave as multi-particle states. Finite-$N$ effects weakly mix sectors with the same global quantum numbers and generate anomalous dimensions.

</figcaption>
</figure>

## Multi-trace operators are not naive products

A product such as $\mathcal O_A(x)\mathcal O_B(x)$ is singular. To define a local operator, one must renormalize the coincident-point product. In a CFT, one also wants a conformal primary. The resulting double-trace primary is denoted

$$
[\mathcal O_A\mathcal O_B]_{n,\ell}.
$$

For scalar single-trace primaries, its schematic form is

$$
[\mathcal O_A\mathcal O_B]_{n,\ell}
\sim
\mathcal O_A\,\partial_{\{\mu_1}\cdots\partial_{\mu_\ell\}}
(\partial^2)^n\mathcal O_B
+
\cdots.
$$

The braces denote symmetric traceless projection on the spin-$\ell$ indices. The ellipsis contains terms with derivatives distributed differently between the two operators, plus trace subtractions and descendant subtractions. These terms are fixed by the requirement that the result be a primary:

$$
K_\mu [\mathcal O_A\mathcal O_B]_{n,\ell}(0)=0.
$$

At leading large $N$, the dimension is additive:

$$
\boxed{
\Delta_{AB;n,\ell}^{(0)}
=
\Delta_A+\Delta_B+2n+\ell.
}
$$

For identical bosonic scalars, Bose symmetry allows only even $\ell$ in the OPE $\mathcal O_A\times\mathcal O_A$. If the two operators are distinct, both even and odd spins can appear, subject to the full set of global-symmetry selection rules.

Higher multi-trace primaries are built similarly:

$$
[\mathcal O_{A_1}\cdots\mathcal O_{A_p}]_{\rm primary}.
$$

At $N=\infty$, their leading dimensions are sums of one-particle dimensions plus nonnegative integer excitation energies. In radial quantization, this is just the statement that a free Fock space has additive energies.

## Normal ordering and orthogonality

It is useful to think of multi-trace operators as normal-ordered products. For two distinct normalized scalar primaries, write schematically

$$
:\mathcal O_A\mathcal O_B:(x)
=
\lim_{y\to x}
\left[
\mathcal O_A(x)\mathcal O_B(y)
-
\text{singular subtractions}
\right].
$$

The subtractions remove identity pieces, lower-trace pieces, and descendant contamination. In an exact generalized-free sector, this is directly analogous to normal ordering in an ordinary free theory.

For example, suppose $\mathcal O_A$ and $\mathcal O_B$ are distinct generalized free scalar primaries with diagonal two-point functions. Then the leading two-point function of the simple scalar double trace is

$$
\left\langle :\mathcal O_A\mathcal O_B:(x)\,:\mathcal O_A\mathcal O_B:(0)\right\rangle
=
\frac{1}{x^{2(\Delta_A+\Delta_B)}}.
$$

If $A=B$, the Wick contraction gives an extra factor of $2$, so the unit-normalized scalar double trace is

$$
\frac{1}{\sqrt{2}}:\mathcal O_A^2:.
$$

This is exactly the same combinatorics as the normalization of identical two-particle states.

At strict $N=\infty$, operators with different particle number are orthogonal after proper normal ordering:

$$
\langle \text{one-particle}\,|\,\text{two-particle}\rangle=0,
$$

$$
\langle \text{$p$-particle}\,|\,\text{$q$-particle}\rangle=0
\qquad
(p\neq q).
$$

At finite $N$, this orthogonality is corrected by powers of $1/N$.

## The OPE knows about both single and multi-trace sectors

Consider the OPE of two normalized single-trace scalar primaries. Schematically,

$$
\mathcal O_A\times\mathcal O_B
\sim
\delta_{AB}\mathbf 1
+
\frac{1}{N}\sum_C \lambda_{ABC}\mathcal O_C
+
\sum_{n,\ell}\lambda^{(0)}_{AB;n,\ell}
[\mathcal O_A\mathcal O_B]_{n,\ell}
+
\cdots.
$$

The important point is the different $N$-scaling:

| OPE contribution | Scaling in $\mathcal O_A\times\mathcal O_B$ | Bulk meaning |
|---|---:|---|
| identity | $O(1)$ | disconnected propagation |
| double-trace tower | $O(1)$ | two-particle states |
| single-trace exchange | $O(1/N)$ | cubic bulk coupling |
| anomalous double-trace data in four-point functions | $O(1/N^2)$ | tree-level interaction |

This is why the generalized-free four-point function has a nontrivial conformal-block expansion even though its connected part vanishes. The leading $O(1)$ OPE data in the $\mathcal O_A\times\mathcal O_B$ channel are mostly multi-trace data. The genuinely interacting single-particle exchange data enter one order later.

For identical scalar $\mathcal O$, the leading large-$N$ OPE takes the form

$$
\mathcal O\times\mathcal O
\sim
\mathbf 1
+
\sum_{n=0}^{\infty}\sum_{\ell=0,2,4,\ldots}
\lambda^{(0)}_{n,\ell}
[\mathcal O\mathcal O]_{n,\ell}
+
O\left(\frac{1}{N}\right).
$$

At finite $N$,

$$
\Delta_{n,\ell}
=
2\Delta+2n+\ell
+
\frac{1}{N^2}\gamma_{n,\ell}^{(1)}
+
\cdots
$$

in matrix theories where connected four-point functions scale as $1/N^2$. The anomalous dimensions $\gamma_{n,\ell}^{(1)}$ are the CFT imprint of bulk interactions.

## Operator mixing

At $N=\infty$, trace number is a good organizing principle. At finite $N$, it is not an exact quantum number. Operators with the same Lorentz spin, scaling dimension range, and global-symmetry quantum numbers can mix.

Suppose there is a single-trace primary $\mathcal S$ and a double-trace primary $\mathcal D$ with the same quantum numbers. Their dilatation operator may take the schematic form

$$
\Gamma
=
\begin{pmatrix}
\Delta_{\mathcal S}^{(0)}+\delta_{\mathcal S} & \mu/N \\
\mu/N & \Delta_{\mathcal D}^{(0)}+\delta_{\mathcal D}
\end{pmatrix},
$$

where $\delta_{\mathcal S}$ and $\delta_{\mathcal D}$ contain diagonal anomalous-dimension corrections. If the two leading dimensions are separated by an order-one gap,

$$
\Delta_{\mathcal S}^{(0)}-\Delta_{\mathcal D}^{(0)}=O(1),
$$

then the mixing angle is small:

$$
\theta
\sim
\frac{\mu/N}{\Delta_{\mathcal S}^{(0)}-\Delta_{\mathcal D}^{(0)}}.
$$

If the two levels are nearly degenerate, however, the mixing can be order one even though the off-diagonal matrix element is $1/N$-suppressed. This is ordinary degenerate perturbation theory, but in AdS/CFT it has a clear physical meaning: a one-particle state can mix strongly with a two-particle state when their energies are close.

This is how resonances and multi-particle thresholds appear in CFT language.

## Single-particle versus single-trace in an abstract CFT

In a general CFT, one may not have a Lagrangian or color traces. For holography, the more invariant concept is a **single-particle primary**.

A practical large-$N$ definition is this: a primary $\mathcal O_A$ is single-particle if it belongs to a chosen basis of normalized primaries whose connected correlators obey

$$
\langle \mathcal O_{A_1}\cdots\mathcal O_{A_k}\rangle_{\rm conn}
\sim
C_T^{1-k/2},
$$

and if it cannot be written, at leading order, as a normal-ordered product of lower-particle primaries.

This definition is recursive. Once the single-particle primaries are identified, multi-particle primaries are built from their products and primary projections.

For matrix gauge theories, this abstract definition agrees with the usual single-trace/multi-trace language for low-dimension operators at large $N$. For vector models, the terminology changes: the natural single-particle operators are often bilinears rather than traces, and the bulk dual, when it exists, is usually a higher-spin theory rather than ordinary Einstein gravity. The large-$N$ logic of factorization and multi-particle composites is still present.

## Finite-$N$ trace relations

At finite $N$, traces are not all independent. This is a basic algebraic fact: finite-size matrices obey polynomial identities. For one matrix, the Cayley-Hamilton theorem implies that sufficiently long traces can be expressed in terms of lower traces. For several noncommuting matrices, the relations are more complicated, but finite-$N$ constraints still exist.

In the large-$N$ limit, these relations disappear for operators of fixed dimension. That is why it is consistent to discuss an infinite tower of multi-trace states at $N=\infty$.

But if the operator dimension grows with $N$, finite-$N$ constraints become physically important. In AdS/CFT, this is related to stringy exclusion effects, giant gravitons, and the fact that a finite-$N$ CFT has fewer independent states than the naive infinite-$N$ Fock space.

The safe rule for this course is

$$
\text{fixed operator dimension first, then }N\to\infty.
$$

In that regime, single-trace and multi-trace language is reliable.

## Multi-trace deformations versus multi-trace operators

A multi-trace operator is a local operator in the CFT spectrum. A multi-trace deformation is a change of the action by such an operator. For example,

$$
S_{\rm CFT}
\longrightarrow
S_{\rm CFT}
+
f\int d^d x\,\mathcal O^2(x).
$$

These are related but not identical concepts. The operator $\mathcal O^2$ belongs to the spectrum whether or not we deform by it. Adding it to the action changes the theory.

In AdS/CFT, double-trace deformations are especially important because they modify boundary conditions for the dual bulk field. We will return to this idea later. On this page, the main point is spectral: multi-trace operators are the CFT names of multi-particle states.

## The large-$N$ Hilbert space as a Fock space

Radial quantization gives the cleanest picture. A primary $\mathcal O_A$ creates a state

$$
|A\rangle=\mathcal O_A(0)|0\rangle
$$

with cylinder energy

$$
E_A=\Delta_A.
$$

A double-trace primary creates a two-particle state:

$$
[\mathcal O_A\mathcal O_B]_{n,\ell}(0)|0\rangle
\quad\longleftrightarrow\quad
|A,B;n,\ell\rangle.
$$

At $N=\infty$,

$$
E_{AB;n,\ell}^{(0)}
=
\Delta_A+\Delta_B+2n+\ell.
$$

At finite $N$,

$$
E_{AB;n,\ell}
=
E_{AB;n,\ell}^{(0)}
+
\frac{1}{N^2}\gamma_{AB;n,\ell}^{(1)}
+
\cdots.
$$

This is precisely the structure of perturbation theory for weakly interacting particles in global AdS. The CFT dilatation operator is the global-AdS Hamiltonian.

Thus the large-$N$ Hilbert space is approximately

$$
\mathcal H_{\rm CFT}
\simeq
\mathcal F\left(\mathcal H_{\rm single\ particle}\right),
\qquad
N=\infty,
$$

where $\mathcal F$ denotes a Fock-space construction. The approximation breaks down when finite-$N$ constraints, strong mixing, black-hole states, or very high energies become important.

## The OPE as a particle-number expansion

The operator product expansion can be reorganized by particle number. For two single-particle operators,

$$
\mathcal O_A\times\mathcal O_B
=
\text{identity}
+
\text{two-particle primaries}
+
\frac{1}{N}\text{one-particle primaries}
+
\cdots.
$$

This ordering may look surprising: why do two-particle operators appear at order one, while single-particle exchange is suppressed? The answer is that two generalized-free particles are already present in the disconnected theory. A single-particle exchange between two external particles requires an interaction vertex, and interaction vertices are $1/N$-suppressed.

For a four-point function of single-trace scalars, the expansion is

$$
\mathcal G(u,v)
=
\mathcal G_{\rm MFT}(u,v)
+
\frac{1}{N^2}\mathcal G^{(1)}(u,v)
+
\cdots.
$$

The leading term contains the identity and double-trace blocks. The correction $\mathcal G^{(1)}$ contains single-trace exchange and corrections to double-trace data.

This is the conceptual bridge to Witten diagrams:

| CFT expansion | AdS perturbation theory |
|---|---|
| identity block | disconnected propagation |
| leading double-trace blocks | free two-particle states |
| single-trace exchange at $1/N^2$ in four-point functions | tree-level exchange Witten diagram |
| anomalous dimensions of double traces | binding energies and phase shifts |
| $1/N^4$ corrections | loop Witten diagrams |

The precise power of $1/N$ depends on whether one discusses OPE coefficients or full connected correlators. For normalized single traces, cubic OPE coefficients scale as $1/N$, while their contribution to a four-point function scales as $1/N^2$.

## AdS/CFT checkpoint

The core holographic dictionary is

$$
\boxed{
\mathcal O_A
\leftrightarrow
\phi_A
}
$$

for a single-particle bulk field or string state, and

$$
\boxed{
[\mathcal O_A\mathcal O_B]_{n,\ell}
\leftrightarrow
\text{two-particle state of }\phi_A\text{ and }\phi_B.
}
$$

The large-$N$ expansion controls how sharply this particle-number interpretation holds. At $N=\infty$, trace number is conserved and the Hilbert space is Fock-like. At finite $N$, trace number can change, reflecting bulk interactions:

$$
\text{one particle}
\leftrightarrow
\text{two particles}
$$

through processes whose amplitudes are suppressed by powers of $1/N$.

This is why large-$N$ CFT is the right language for quantum gravity in AdS. It gives a nonperturbative operator algebra, but at large $N$ that algebra reorganizes itself into the perturbative Hilbert space of particles, strings, and interactions.

## Summary

Single-trace operators are the basic gauge-invariant operators of matrix large-$N$ theories. With order-one two-point normalization, their connected correlators scale as

$$
\langle \mathcal O_{A_1}\cdots \mathcal O_{A_k}\rangle_{\rm conn}
\sim
N^{2-k}
\sim
C_T^{1-k/2}.
$$

At $N=\infty$, they create one-particle states. Multi-trace primaries create multi-particle states. For scalar double traces,

$$
[ \mathcal O_A\mathcal O_B ]_{n,\ell}
\quad\text{has}\quad
\Delta_{AB;n,\ell}^{(0)}
=
\Delta_A+\Delta_B+2n+\ell.
$$

Finite-$N$ effects mix operators with the same quantum numbers and shift multi-trace dimensions:

$$
\Delta_{AB;n,\ell}
=
\Delta_A+\Delta_B+2n+\ell
+
\frac{1}{N^2}\gamma_{AB;n,\ell}^{(1)}
+
\cdots.
$$

These anomalous dimensions are the CFT form of bulk binding energies and scattering data. The whole point of large-$N$ holography is that a complicated CFT operator algebra becomes, to leading order, a Fock-space problem in AdS.

## Exercises

### Exercise 1. Connected scaling and factorization

Assume normalized single-trace operators obey

$$
\langle \mathcal O_1\cdots\mathcal O_k\rangle_{\rm conn}
\sim
N^{2-k}.
$$

Show that the four-point function factorizes at leading order, while its connected part is suppressed by $1/N^2$.

<details><summary><strong>Solution</strong></summary>

For $k=2$,

$$
\langle \mathcal O_i\mathcal O_j\rangle_{\rm conn}
\sim
N^0.
$$

For $k=4$,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle_{\rm conn}
\sim
N^{-2}.
$$

The full four-point function decomposes into connected and disconnected pieces:

$$
\begin{aligned}
\langle 1234\rangle
&=
\langle 12\rangle\langle 34\rangle
+
\langle 13\rangle\langle 24\rangle
+
\langle 14\rangle\langle 23\rangle
+
\langle 1234\rangle_{\rm conn}.
\end{aligned}
$$

The disconnected products are order $N^0$, while the connected term is order $N^{-2}$. Thus

$$
\langle 1234\rangle
=
\langle 12\rangle\langle 34\rangle
+
\langle 13\rangle\langle 24\rangle
+
\langle 14\rangle\langle 23\rangle
+
O(N^{-2}).
$$

This is large-$N$ factorization.

</details>

### Exercise 2. Unit normalization of an identical double trace

Let $\mathcal O$ be a generalized free scalar with

$$
\langle \mathcal O(x)\mathcal O(0)\rangle=\frac{1}{x^{2\Delta}}.
$$

Show that the scalar double-trace operator

$$
\mathcal D(x)=\frac{1}{\sqrt{2}}:\mathcal O^2:(x)
$$

has unit-normalized two-point function at leading order:

$$
\langle \mathcal D(x)\mathcal D(0)\rangle
=
\frac{1}{x^{4\Delta}}.
$$

<details><summary><strong>Solution</strong></summary>

Using Wick factorization and normal ordering, contractions inside the same normal-ordered product are removed. The only leading contractions pair the two fields at $x$ with the two fields at $0$:

$$
\left\langle :\mathcal O^2:(x):\mathcal O^2:(0)\right\rangle
=
2\left(\frac{1}{x^{2\Delta}}\right)^2
=
\frac{2}{x^{4\Delta}}.
$$

Therefore

$$
\langle \mathcal D(x)\mathcal D(0)\rangle
=
\frac{1}{2}\frac{2}{x^{4\Delta}}
=
\frac{1}{x^{4\Delta}}.
$$

The factor $1/\sqrt{2}$ is the same Bose-symmetry normalization as for two identical particles.

</details>

### Exercise 3. Additive dimensions from the cylinder

Let $\mathcal O_A$ and $\mathcal O_B$ be scalar primaries of dimensions $\Delta_A$ and $\Delta_B$. Use radial quantization to explain why

$$
\Delta_{AB;n,\ell}^{(0)}
=
\Delta_A+\Delta_B+2n+\ell.
$$

<details><summary><strong>Solution</strong></summary>

Radial quantization maps a primary operator to a state on $S^{d-1}$:

$$
\mathcal O_A(0)|0\rangle=|A\rangle,
\qquad
E_A=\Delta_A.
$$

At $N=\infty$, two-particle energies add. A two-particle state built from $A$ and $B$ has base energy

$$
\Delta_A+\Delta_B.
$$

Orbital angular momentum $\ell$ adds $\ell$ units of energy, and the radial excitation number $n$ adds $2n$ units. Therefore

$$
E_{AB;n,\ell}^{(0)}
=
\Delta_A+\Delta_B+2n+\ell.
$$

By the state-operator correspondence, cylinder energy equals scaling dimension, so

$$
\Delta_{AB;n,\ell}^{(0)}=E_{AB;n,\ell}^{(0)}.
$$

</details>

### Exercise 4. Small mixing angle

Consider two operators with the same quantum numbers and dilatation matrix

$$
\Gamma
=
\begin{pmatrix}
\Delta_S & \mu/N \\
\mu/N & \Delta_D
\end{pmatrix},
$$

where $\Delta_S-\Delta_D=O(1)$. Compute the leading mixing angle.

<details><summary><strong>Solution</strong></summary>

For a real symmetric $2\times2$ matrix, the mixing angle satisfies

$$
\tan 2\theta
=
\frac{2\mu/N}{\Delta_S-\Delta_D}.
$$

If the off-diagonal term is small compared to the level splitting, then

$$
\theta
\simeq
\frac{\mu/N}{\Delta_S-\Delta_D}.
$$

Thus the mixing is suppressed by $1/N$ when the two levels are not nearly degenerate. If $\Delta_S-\Delta_D$ becomes of order $1/N$, this perturbative estimate fails and the mixing can become order one.

</details>

### Exercise 5. Single-trace exchange in a four-point function

Suppose the OPE coefficient of three normalized single-trace operators scales as

$$
\lambda_{ABC}\sim \frac{1}{N}.
$$

Explain why exchange of a single-trace primary $\mathcal O_C$ in a four-point function of normalized single traces contributes at order $1/N^2$.

<details><summary><strong>Solution</strong></summary>

A conformal-block contribution from exchanging $\mathcal O_C$ in the $\mathcal O_A\mathcal O_B$ and $\mathcal O_D\mathcal O_E$ channels is proportional to a product of two OPE coefficients:

$$
\lambda_{ABC}\lambda_{DEC}\,G_{\Delta_C,\ell_C}(u,v).
$$

Each cubic single-trace OPE coefficient scales as $1/N$, so

$$
\lambda_{ABC}\lambda_{DEC}
\sim
\frac{1}{N^2}.
$$

Thus single-trace exchange appears at order $1/N^2$ in the connected four-point function. This matches the bulk statement that a tree-level exchange Witten diagram is suppressed by one power of the gravitational coupling $G_N\sim 1/N^2$.

</details>
