---
title: "Four-Point Functions and Bulk Locality"
description: "How CFT four-point functions encode contact interactions, exchange diagrams, double-trace data, crossing symmetry, and the emergence of local bulk effective field theory."
sidebar:
  order: 30
---

## Why this matters

Two- and three-point functions teach us the spectrum and cubic couplings of a holographic CFT. Four-point functions are where the first genuinely dynamical consistency questions appear.

A scalar three-point function has its position dependence fixed by conformal symmetry. A scalar four-point function does not. After kinematics are removed, it depends on two conformally invariant cross-ratios. That remaining function contains information about bulk contact interactions, exchange of bulk fields, double-trace anomalous dimensions, crossing symmetry, and the degree to which the bulk theory behaves locally.

This is why four-point functions are a major turning point in AdS/CFT. They are not merely “one more correlator.” They are the first place where the following slogan becomes mathematically visible:

$$
\text{local bulk dynamics}
\quad\longleftrightarrow\quad
\text{special analytic structure of CFT four-point data}.
$$

<figure class="doc-figure" style="--figure-width: 56rem;">

![Four-point functions, Witten diagrams, and bulk locality](/figures/course/four-point-functions-bulk-locality.svg)

<figcaption>

Four-point functions see both contact interactions and exchange diagrams. In the CFT, these contributions appear through single-trace exchange, double-trace data, crossing symmetry, and the large-$N$ expansion. Bulk locality is a sharp constraint on this structure, not just a picture of vertices drawn in AdS.

</figcaption>
</figure>

The goal of this page is not to compute a complicated supergravity four-point function. The goal is to explain what four-point functions know, how Witten diagrams organize that knowledge, and why the large-$N$ plus large-gap structure of a CFT is the boundary signal of local bulk effective field theory.

## Kinematics of scalar four-point functions

Consider scalar primary operators $\mathcal O_i$ of dimensions $\Delta_i$ in a $d$-dimensional CFT. Conformal symmetry fixes the four-point function up to a function of two cross-ratios. For identical scalar operators $\mathcal O$ of dimension $\Delta$, it is convenient to write

$$
\langle
\mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\mathcal O(x_4)
\rangle
=
\frac{1}{|x_{12}|^{2\Delta}|x_{34}|^{2\Delta}}
\mathcal G(u,v),
$$

where $x_{ij}=x_i-x_j$ and

$$
u = \frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v = \frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

In Euclidean signature, $x_{ij}^2=|x_i-x_j|^2$. The two numbers $u$ and $v$ are invariant under translations, rotations, dilatations, and special conformal transformations.

For non-identical scalar operators, one can factor out a different kinematic prefactor. The essential point is unchanged: conformal symmetry reduces the problem to a function of $u$ and $v$.

## Crossing symmetry

For identical scalars, the same four-point function must be invariant under permutations of the operator insertions. The exchange $x_1\leftrightarrow x_3$ gives the crossing equation

$$
\mathcal G(u,v)
=
\left(\frac{u}{v}\right)^\Delta \mathcal G(v,u).
$$

This innocent-looking equation is one of the strongest constraints in conformal field theory. In a holographic CFT it says that the same bulk process must be decomposable in different OPE channels.

The $s$-channel OPE groups $(12)(34)$:

$$
\mathcal O(x_1)\mathcal O(x_2)
\sim
\sum_p C_{\mathcal O\mathcal O p}\,
\mathcal C_p(x_{12},\partial_{x_2})\mathcal O_p(x_2).
$$

The same correlator can also be expanded in the $t$-channel $(14)(23)$ or the $u$-channel $(13)(24)$. Crossing says that all these decompositions agree. In the bulk, this is the boundary expression of the consistency of a single AdS effective theory.

## The large-$N$ expansion

For a single-trace scalar primary $\mathcal O$ normalized so that

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
\sim
\frac{1}{|x|^{2\Delta}},
$$

large-$N$ factorization gives

$$
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle
=
\langle \mathcal O\mathcal O\rangle\langle \mathcal O\mathcal O\rangle
+\text{two more pairings}
+
\frac{1}{N^2}
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle_{\rm conn}^{(1)}
+\cdots .
$$

Equivalently,

$$
\mathcal G(u,v)
=
\mathcal G^{(0)}(u,v)
+\frac{1}{N^2}\mathcal G^{(1)}(u,v)
+\cdots .
$$

For identical generalized-free fields,

$$
\mathcal G^{(0)}(u,v)
=
1+u^\Delta+\left(\frac{u}{v}\right)^\Delta .
$$

This leading term is not empty. Its OPE contains an infinite tower of double-trace operators,

$$
[\mathcal O\mathcal O]_{n,\ell},
$$

with leading dimensions

$$
\Delta_{n,\ell}^{(0)}
=
2\Delta+2n+\ell,
\qquad
n=0,1,2,\ldots ,
$$

and spin $\ell$. At order $1/N^2$, interactions shift these dimensions:

$$
\Delta_{n,\ell}
=
2\Delta+2n+\ell
+
\frac{1}{N^2}\gamma_{n,\ell}
+\cdots ,
$$

and also correct the OPE coefficients. Thus the connected four-point function measures not only single-trace exchange, but also the binding energies and interaction strengths of two-particle states in AdS.

This is a key conceptual point:

$$
\text{double-trace anomalous dimensions}
\quad
\longleftrightarrow
\quad
\text{two-particle interactions in the bulk}.
$$

## Contact Witten diagrams

A local quartic bulk interaction gives the simplest connected four-point Witten diagram. For a scalar interaction

$$
S_{\rm int}
=
g_4
\int_{\mathrm{AdS}} d^{d+1}X\sqrt g\,
\phi_1\phi_2\phi_3\phi_4,
$$

the connected correlator contains

$$
\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)
\mathcal O_3(x_3)\mathcal O_4(x_4)
\rangle_{\rm contact}
=
-g_4
\int_{\mathrm{AdS}}dX\sqrt g\,
K_{\Delta_1}(X;x_1)
K_{\Delta_2}(X;x_2)
K_{\Delta_3}(X;x_3)
K_{\Delta_4}(X;x_4),
$$

up to normalization conventions. This integral is often expressed in terms of a $D$-function or reduced $\bar D$-function.

A contact diagram contributes in all OPE channels. It does not select one obvious exchanged single-trace primary. Instead, it shifts the double-trace data in a way consistent with crossing. In a bulk effective theory, adding higher-derivative contact interactions changes the detailed spin and dimension dependence of those double-trace corrections.

For example,

$$
\int\sqrt g\,\phi^4,
\qquad
\int\sqrt g\,(\nabla\phi)^2\phi^2,
\qquad
\int\sqrt g\,(\nabla_M\phi\nabla^M\phi)^2
$$

all give different four-point contact contributions. From the CFT point of view, these differences are encoded in the large-spin and large-twist behavior of OPE data.

## Exchange Witten diagrams

A cubic interaction can produce a four-point exchange diagram. Suppose a field $\chi$ couples as

$$
S_{\rm int}
=
g_{12\chi}\int dX\sqrt g\,\phi_1\phi_2\chi
+
g_{34\chi}\int dX\sqrt g\,\phi_3\phi_4\chi.
$$

The corresponding $s$-channel exchange diagram is

$$
\begin{aligned}
\mathcal A_s(x_i)
&=
g_{12\chi}g_{34\chi}
\int dX\sqrt g\int dY\sqrt g\,
K_{\Delta_1}(X;x_1)K_{\Delta_2}(X;x_2) \\
&\hspace{4.2rem}\times
G_{\Delta_\chi}(X,Y)
K_{\Delta_3}(Y;x_3)K_{\Delta_4}(Y;x_4),
\end{aligned}
$$

where $G_{\Delta_\chi}(X,Y)$ is the bulk-to-bulk propagator for $\chi$. In the $s$-channel OPE, this diagram contains the single-trace primary $\mathcal O_\chi$ and its conformal descendants. It also contains double-trace contributions that are required by the full AdS integral and by crossing.

This is one of the places where diagrams can mislead if read too literally. The line $G_{\Delta_\chi}$ is naturally associated with a single-trace exchange, but the full boundary four-point function is not just “the conformal block of $\mathcal O_\chi$.” It includes additional pieces, and the final answer must be crossing-compatible after all relevant diagrams and channels are included.

## Conformal blocks and geodesic Witten diagrams

The CFT OPE organizes the four-point function into conformal blocks. Schematically,

$$
\mathcal G(u,v)
=
\sum_p
C_{\mathcal O\mathcal O p}^2\,
G_{\Delta_p,\ell_p}(u,v).
$$

The block $G_{\Delta_p,\ell_p}$ packages a primary operator and all of its descendants. A full exchange Witten diagram is not usually equal to a single conformal block. It decomposes into the single-trace block associated with the exchanged field plus an infinite set of double-trace blocks.

There is, however, a beautiful geometric object called a geodesic Witten diagram that computes a conformal block directly. Instead of integrating cubic vertices over all of AdS, one integrates them over geodesics connecting the paired boundary points. This construction is not the same as the heavy-particle geodesic approximation discussed on the next page, but the names are related: both use special curves in AdS to isolate pieces of a boundary correlator.

For this course, the main takeaway is:

$$
\text{ordinary exchange Witten diagram}
=
\text{single-trace block}
+
\text{double-trace data}.
$$

The double-trace terms are not nuisance terms. They are required for a consistent bulk theory.

## Mellin space: why locality becomes simple

Position-space four-point functions can be complicated. Mellin space often makes the analogy with scattering amplitudes clearer. Very schematically, one writes

$$
\mathcal G(u,v)
=
\int \frac{ds\,dt}{(2\pi i)^2}\,
u^{s/2}v^{-(s+t)/2}
M(s,t)
\times
\Gamma\text{-factors}.
$$

The precise gamma-function measure is convention-dependent, so this page will not use it for computations. What matters is the structural lesson:

- contact interactions give polynomial Mellin amplitudes;
- exchange diagrams give poles in Mellin variables;
- the residues of those poles are determined by lower-point data;
- higher-derivative bulk interactions correspond to higher-degree polynomials.

For a scalar exchange, the Mellin amplitude has poles schematically at

$$
s
=
\Delta_\chi-\ell_\chi+2m,
\qquad
m=0,1,2,\ldots ,
$$

with residues determined by cubic couplings and descendant structure. This is the AdS version of the idea that scattering amplitudes factorize when an intermediate particle goes on shell.

Mellin space is especially useful for seeing the connection between bulk locality and CFT analyticity. In a local bulk EFT, interactions with finitely many derivatives produce Mellin amplitudes with controlled polynomial growth. If the CFT produces wild high-energy behavior in Mellin space, it is unlikely to admit a simple local bulk dual.

## Large gap and local bulk EFT

Large $N$ alone does not guarantee local Einstein-like bulk physics. It gives a perturbative expansion, but that expansion might describe string theory at the string scale, higher-spin theory, or something not well approximated by a local low-energy action.

A sharper condition is that the CFT have a parametrically large gap in the spectrum of single-trace operators of spin greater than two:

$$
\Delta_{\rm gap}\gg 1.
$$

The physical meaning is simple. Heavy single-trace operators correspond to heavy single-particle bulk states. If all higher-spin and stringy states are very heavy in AdS units, then at energies well below the gap they can be integrated out. The result is a local bulk effective action organized by derivatives:

$$
S_{\rm eff}
=
\frac{1}{16\pi G_N}
\int d^{d+1}x\sqrt g
\left[
R+\frac{d(d-1)}{L^2}
+
\alpha_1 L^2 R^2
+
\alpha_2 L^4 R^3
+\cdots
\right]
+
\text{matter}.
$$

The coefficients of higher-derivative terms are suppressed by powers of the gap. Boundary four-point functions know about those terms through the detailed behavior of anomalous dimensions and OPE coefficients.

Thus one of the most important modern lessons of AdS/CFT is:

$$
\text{large }N
+
\text{large sparse gap}
\quad
\Rightarrow
\quad
\text{local bulk EFT below the gap}.
$$

The converse is also physically clear: if a local bulk EFT exists, its spectrum should show large-$N$ factorization and a separation between light fields and heavy stringy or higher-spin states.

## A simple dictionary of four-point data

The following table summarizes the first-pass dictionary.

| CFT four-point feature | Bulk interpretation |
|---|---|
| disconnected generalized-free term | free propagation of multiparticle states |
| connected order $1/N^2$ term | tree-level bulk interaction |
| single-trace conformal block | exchange of one bulk field |
| double-trace operators | multiparticle bulk states |
| double-trace anomalous dimensions | binding energies/interactions |
| crossing symmetry | consistency of all OPE channels |
| large spin behavior | causality and locality constraints |
| Mellin poles | particle exchange in AdS |
| Mellin polynomials | local contact interactions |
| large single-trace gap | local bulk EFT below the gap |

This table is approximate but useful. The exact dictionary depends on operator normalizations, mixing, spin, supersymmetry, and whether one is working in Euclidean or Lorentzian signature.

## A worked example: generalized-free plus interaction

At leading large $N$, a normalized scalar single-trace operator behaves like a generalized-free field:

$$
\mathcal G^{(0)}(u,v)
=
1+u^\Delta+\left(\frac{u}{v}\right)^\Delta.
$$

The first term is the contraction $(12)(34)$, the second is $(13)(24)$, and the third is $(14)(23)$. The OPE in the $(12)$ channel includes the identity and double-trace operators $[\mathcal O\mathcal O]_{n,\ell}$.

Now add a weak bulk quartic interaction,

$$
\delta S
=
g_4\int_{\mathrm{AdS}}dX\sqrt g\,\phi^4.
$$

At order $g_4$, the connected four-point function is a contact Witten diagram. In the CFT, this modifies the dimensions and OPE coefficients of the double-trace operators:

$$
\gamma_{n,\ell}\neq 0,
\qquad
a_{n,\ell}=a_{n,\ell}^{(0)}+\frac{1}{N^2}a_{n,\ell}^{(1)}+\cdots .
$$

The correction must still satisfy crossing. This is a nontrivial constraint: one cannot choose arbitrary anomalous dimensions and call the result a local bulk interaction. Locality is encoded in very special patterns of OPE data.

## What four-point functions do not automatically prove

It is tempting to say that because a four-point function can be drawn as a Witten diagram, the bulk is local. That is too fast.

A CFT four-point function can often be represented using formal AdS integrals. Local bulk physics requires more:

1. a controlled $1/N$ expansion;
2. a parametrically sparse single-trace spectrum;
3. crossing-compatible OPE data;
4. causal and unitary Lorentzian behavior;
5. an effective derivative expansion below the gap.

In other words, the existence of AdS-like variables is not the same as the existence of a local semiclassical spacetime. The four-point function is where this distinction starts to matter.

## Dictionary checkpoint

After this page, you should associate:

$$
\mathcal G^{(1)}(u,v)
\quad
\longleftrightarrow
\quad
\text{tree-level bulk interactions},
$$

$$
[\mathcal O\mathcal O]_{n,\ell}
\quad
\longleftrightarrow
\quad
\text{two-particle bulk states},
$$

$$
\gamma_{n,\ell}
\quad
\longleftrightarrow
\quad
\text{bulk binding energies and phase shifts},
$$

and

$$
\text{crossing + large }N\text{ + large gap}
\quad
\longleftrightarrow
\quad
\text{local bulk EFT below the gap}.
$$

The conceptual leap is that a local vertex in AdS is not merely drawn in a diagram. It is encoded in the way infinitely many CFT OPE coefficients and anomalous dimensions conspire to satisfy crossing.

## Common confusions

### “An exchange Witten diagram is just one conformal block.”

Not quite. The single-trace field exchanged in the bulk is associated with a single-trace conformal block in the relevant OPE channel, but the full exchange Witten diagram also contains double-trace contributions. These double-trace pieces are part of the AdS integral and are essential for consistency.

### “Large $N$ automatically means local gravity.”

Large $N$ gives a perturbative expansion. It does not by itself give local Einstein gravity. A vector model, a matrix model with no large gap, and a stringy theory at small AdS radius can all have large-$N$ structure without being well described by local Einstein gravity.

### “Contact diagrams are less physical than exchange diagrams.”

Contact diagrams are just as physical. They represent local interactions in the bulk effective action. In a low-energy EFT, contact terms encode the effects of heavy fields that have been integrated out.

### “Crossing is a boundary detail.”

Crossing is one of the main boundary expressions of bulk consistency. If a set of bulk diagrams did not produce crossing-compatible CFT data, it would not define a consistent holographic theory.

### “Mellin space is required to understand four-point functions.”

No. One can study four-point functions entirely in position space or conformal-block language. Mellin space is useful because it makes analogies with scattering amplitudes and locality especially transparent.

## Exercises

### Exercise 1: Check crossing for generalized-free fields

For identical scalar generalized-free fields,

$$
\mathcal G^{(0)}(u,v)
=
1+u^\Delta+\left(\frac{u}{v}\right)^\Delta.
$$

Show that

$$
\mathcal G^{(0)}(u,v)
=
\left(\frac{u}{v}\right)^\Delta
\mathcal G^{(0)}(v,u).
$$

<details>
<summary><strong>Solution</strong></summary>

Compute the right-hand side:

$$
\left(\frac{u}{v}\right)^\Delta
\mathcal G^{(0)}(v,u)
=
\left(\frac{u}{v}\right)^\Delta
\left[
1+v^\Delta+\left(\frac{v}{u}\right)^\Delta
\right].
$$

Multiplying term by term gives

$$
\left(\frac{u}{v}\right)^\Delta
+
u^\Delta
+
1.
$$

Reordering the terms,

$$
1+u^\Delta+\left(\frac{u}{v}\right)^\Delta
=
\mathcal G^{(0)}(u,v).
$$

So the generalized-free four-point function satisfies crossing.

</details>

### Exercise 2: Why do double-trace anomalous dimensions appear at order $1/N^2$?

Suppose normalized single-trace three-point coefficients scale as

$$
C_{\mathcal O\mathcal O\mathcal X}\sim \frac{1}{N}.
$$

Why should the anomalous dimensions of double-trace operators $[\mathcal O\mathcal O]_{n,\ell}$ induced by single-trace exchange scale as $1/N^2$?

<details>
<summary><strong>Solution</strong></summary>

Single-trace exchange in a four-point function uses two cubic couplings: one coupling connects $\mathcal O\mathcal O$ to the exchanged single-trace operator $\mathcal X$, and the other connects $\mathcal X$ back to $\mathcal O\mathcal O$.

If each normalized three-point coefficient scales as

$$
C_{\mathcal O\mathcal O\mathcal X}\sim \frac{1}{N},
$$

then the exchange contribution scales as

$$
C_{\mathcal O\mathcal O\mathcal X}^2
\sim
\frac{1}{N^2}.
$$

The same order controls the connected four-point function and hence the leading corrections to double-trace dimensions and OPE coefficients. Therefore

$$
\gamma_{n,\ell}\sim \frac{1}{N^2}.
$$

</details>

### Exercise 3: Contact interaction and Mellin degree

A non-derivative quartic interaction $\phi^4$ gives a constant Mellin amplitude, while an interaction with four derivatives gives a higher-degree polynomial in Mellin variables. Why is this natural from the bulk EFT point of view?

<details>
<summary><strong>Solution</strong></summary>

In flat-space scattering, derivatives in an interaction vertex produce powers of momenta. A non-derivative contact interaction gives a momentum-independent amplitude, while a four-derivative interaction gives an amplitude with four powers of momenta.

Mellin variables in AdS/CFT play a role analogous to kinematic invariants in scattering. Therefore a local contact vertex with more derivatives produces a Mellin amplitude of higher polynomial degree. This is why polynomial boundedness in Mellin space is a useful diagnostic of local bulk EFT.

</details>

### Exercise 4: Why is a large gap needed?

Explain why a CFT with large $N$ but no large single-trace gap should not be expected to have a simple local Einstein gravity dual.

<details>
<summary><strong>Solution</strong></summary>

Large $N$ suppresses interactions between normalized single-trace operators and gives a perturbative expansion. But local Einstein gravity also requires that most non-gravitational single-particle bulk states be heavy in AdS units. Otherwise, the bulk low-energy theory contains many light fields, possibly including higher-spin fields or stringy modes.

A large single-trace gap means that, below some high scale, only a small set of low-spin bulk fields remains light. The heavy states can be integrated out, producing a local derivative expansion. Without such a gap, there is no reason for the bulk to be approximated by a local Einstein-like effective action.

</details>

## Further reading

- E. D'Hoker and D. Z. Freedman, [General Scalar Exchange in AdS$_{d+1}$](https://arxiv.org/abs/hep-th/9811257).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151).
- J. Penedones, [Writing CFT Correlation Functions as AdS Scattering Amplitudes](https://arxiv.org/abs/1011.1485).
- A. L. Fitzpatrick, J. Kaplan, J. Penedones, S. Raju, and B. C. van Rees, [A Natural Language for AdS/CFT Correlators](https://arxiv.org/abs/1107.1499).
- E. Hijano, P. Kraus, E. Perlmutter, and R. Snively, [Witten Diagrams Revisited: The AdS Geometry of Conformal Blocks](https://arxiv.org/abs/1508.00501).
- J. Penedones, [TASI Lectures on AdS/CFT](https://arxiv.org/abs/1608.04948).
