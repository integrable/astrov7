---
title: "Large-N OPE and Perturbation Theory"
description: "Mean-field OPE data, anomalous dimensions, crossing at order 1/N², Witten diagrams, Mellin amplitudes, and double-trace deformations."
sidebar:
  order: 4
---

## Goal

The previous three pages explained the large-$N$ architecture of a holographic CFT:

$$
\text{generalized free fields}
\quad\Longrightarrow\quad
\text{single-trace and multi-trace operators}
\quad\Longrightarrow\quad
\text{planar expansion}.
$$

This page puts those ideas into the language most useful for AdS/CFT calculations: **perturbation theory in CFT data**.

The central object is a four-point function. At $N=\infty$, it is fixed by generalized-free-field factorization. At order $1/N^2$, interactions appear. But the CFT does not say “a particle scattered in AdS.” It says something sharper:

$$
\boxed{
\text{bulk interactions}
\quad\Longleftrightarrow\quad
\text{corrections to OPE data}.
}
$$

For double-trace operators, this means

$$
\Delta_{n,\ell}
=
2\Delta+2n+\ell
+
\frac{1}{N^2}\gamma_{n,\ell}^{(1)}
+\cdots,
$$

and

$$
a_{n,\ell}
=
a_{n,\ell}^{(0)}
+
\frac{1}{N^2}a_{n,\ell}^{(1)}
+\cdots.
$$

The anomalous dimensions $\gamma_{n,\ell}^{(1)}$ are the CFT version of **two-particle binding energies in AdS**. The OPE-coefficient shifts $a_{n,\ell}^{(1)}$ encode how the wavefunctions and interaction vertices are corrected.

This is the point where CFT becomes holographic perturbation theory.

## The four-point function as the laboratory

Consider an identical scalar single-trace primary $\mathcal O$ with dimension $\Delta$, normalized by

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\frac{1}{x^{2\Delta}}.
$$

Write the four-point function as

$$
\langle
\mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\mathcal O(x_4)
\rangle
=
\frac{1}{x_{12}^{2\Delta}x_{34}^{2\Delta}}
\mathcal G(u,v),
$$

where

$$
u
=
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v
=
\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

For identical scalars, crossing symmetry under $1\leftrightarrow 3$ gives

$$
\boxed{
v^\Delta \mathcal G(u,v)
=
u^\Delta \mathcal G(v,u).
}
$$

In a matrix large-$N$ CFT, the connected four-point function of normalized single-trace operators is order $1/N^2$. Therefore

$$
\boxed{
\mathcal G(u,v)
=
\mathcal G^{(0)}(u,v)
+
\frac{1}{N^2}\mathcal G^{(1)}(u,v)
+
\frac{1}{N^4}\mathcal G^{(2)}(u,v)
+\cdots.
}
$$

The leading piece is the generalized-free or mean-field answer:

$$
\boxed{
\mathcal G^{(0)}(u,v)
=
1+u^\Delta+\left(\frac{u}{v}\right)^\Delta.
}
$$

The first term is the identity contribution in the $12\to 34$ channel. The other two terms are the disconnected Wick pairings in crossed channels. Even though the correlator factorizes, the $\mathcal O\times\mathcal O$ OPE is not trivial: the crossed disconnected terms decompose into an infinite tower of double-trace conformal families.

## Mean-field OPE data

The $\mathcal O\times\mathcal O$ OPE at $N=\infty$ contains the identity and double-trace primaries

$$
[\mathcal O\mathcal O]_{n,\ell}.
$$

Schematic representatives are

$$
[\mathcal O\mathcal O]_{n,\ell}
\sim
\mathcal O\,
\partial_{\{\mu_1}\cdots\partial_{\mu_\ell\}}
(\partial^2)^n
\mathcal O
+\cdots,
$$

where the omitted terms subtract traces and descendants so that the result is a conformal primary. The quantum numbers are

$$
n=0,1,2,\ldots,
\qquad
\ell=0,1,2,\ldots.
$$

For identical bosonic scalars in the $\mathcal O\times\mathcal O$ OPE, only even $\ell$ appear.

At leading large $N$, their dimensions are additive:

$$
\boxed{
\Delta_{n,\ell}^{(0)}
=
2\Delta+2n+\ell.
}
$$

This formula is one of the most important formulas in holographic CFT. Under the state-operator map, $\Delta$ is the energy of a one-particle state on $S^{d-1}$. Thus

$$
2\Delta+2n+\ell
$$

is the energy of two noninteracting particles in global AdS, with radial excitation number $n$ and angular momentum $\ell$.

The leading OPE coefficients

$$
a_{n,\ell}^{(0)}
\equiv
\left(C_{\mathcal O\mathcal O[\mathcal O\mathcal O]_{n,\ell}}^{(0)}\right)^2
$$

are fixed by the conformal block decomposition of $\mathcal G^{(0)}(u,v)$. Their closed form depends on normalization conventions for conformal blocks, so the formula itself is less important than the principle:

$$
\boxed{
\text{mean-field theory fixes all leading double-trace OPE data.}
}
$$

The first nontrivial dynamical question is how these data are corrected.

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 55rem;">

![Large-N OPE perturbation theory](/figures/cft/large-n-ope-perturbation.svg)

<figcaption>

Large-$N$ perturbation theory is perturbation theory of the operator algebra. At $N=\infty$, the four-point function is mean-field theory and the OPE contains double-trace towers $[\mathcal O\mathcal O]_{n,\ell}$. At order $1/N^2$, single-trace exchange and contact interactions generate anomalous dimensions $\gamma_{n,\ell}^{(1)}$ and OPE-coefficient shifts $a_{n,\ell}^{(1)}$. In AdS, these are tree-level Witten diagrams.

</figcaption>
</figure>

## Perturbing the OPE data

Decompose the reduced correlator into conformal blocks in the $12\to 34$ channel:

$$
\mathcal G(u,v)
=
\sum_{\mathcal X}
a_{\mathcal X}
G_{\Delta_{\mathcal X},\ell_{\mathcal X}}(u,v),
$$

where

$$
a_{\mathcal X}=C_{\mathcal O\mathcal O\mathcal X}^2
$$

for identical external scalars, up to the chosen block normalization.

At $N=\infty$, the sum contains the identity and the double-trace towers. At order $1/N^2$, three things can happen.

First, double-trace dimensions shift:

$$
\Delta_{n,\ell}
=
\Delta_{n,\ell}^{(0)}
+
\frac{1}{N^2}\gamma_{n,\ell}^{(1)}
+
O(N^{-4}).
$$

Second, double-trace OPE coefficients shift:

$$
a_{n,\ell}
=
a_{n,\ell}^{(0)}
+
\frac{1}{N^2}a_{n,\ell}^{(1)}
+
O(N^{-4}).
$$

Third, single-trace operators $\mathcal X$ can be exchanged if the three-point coefficient

$$
C_{\mathcal O\mathcal O\mathcal X}
$$

is nonzero. For a normalized single-trace operator $\mathcal X$,

$$
C_{\mathcal O\mathcal O\mathcal X}
\sim
\frac{1}{N},
$$

so its conformal block contributes to $\mathcal G^{(1)}$:

$$
a_{\mathcal X}=C_{\mathcal O\mathcal O\mathcal X}^2
\sim
\frac{1}{N^2}.
$$

Putting these ingredients together gives the order-$1/N^2$ block expansion:

$$
\boxed{
\begin{aligned}
\mathcal G^{(1)}(u,v)
=&
\sum_{n,\ell}
\left[
 a_{n,\ell}^{(1)}
 G_{\Delta_{n,\ell}^{(0)},\ell}(u,v)
+
 a_{n,\ell}^{(0)}
 \gamma_{n,\ell}^{(1)}
 \left.\partial_\Delta
 G_{\Delta,\ell}(u,v)
 \right|_{\Delta=\Delta_{n,\ell}^{(0)}}
\right]
\\
&+
\sum_{\mathcal X\,\text{single trace}}
\left(c_{\mathcal O\mathcal O\mathcal X}^{(0)}\right)^2
G_{\Delta_{\mathcal X},\ell_{\mathcal X}}(u,v).
\end{aligned}
}
$$

Here $c_{\mathcal O\mathcal O\mathcal X}^{(0)}$ denotes the order-one coefficient in

$$
C_{\mathcal O\mathcal O\mathcal X}
=
\frac{1}{N}c_{\mathcal O\mathcal O\mathcal X}^{(0)}
+
O(N^{-3}).
$$

This equation is the CFT version of tree-level perturbation theory in AdS.

## Why anomalous dimensions produce logarithms

The derivative with respect to $\Delta$ in the previous formula is not cosmetic. It is how anomalous dimensions show up in position-space correlators.

Near the $12$ OPE limit,

$$
u\to 0,
\qquad
v\quad\text{fixed},
$$

a conformal block behaves schematically as

$$
G_{\Delta_{n,\ell},\ell}(u,v)
\sim
u^{\Delta_{n,\ell}/2}
\times
\text{angular function}.
$$

Now substitute

$$
\Delta_{n,\ell}
=
\Delta_{n,\ell}^{(0)}
+
\frac{1}{N^2}\gamma_{n,\ell}^{(1)}
+\cdots.
$$

Then

$$
u^{\Delta_{n,\ell}/2}
=
u^{\Delta_{n,\ell}^{(0)}/2}
\left[
1+
\frac{1}{2N^2}\gamma_{n,\ell}^{(1)}\log u
+
O(N^{-4})
\right].
$$

Thus:

$$
\boxed{
\log u\text{ terms in }\mathcal G^{(1)}
\quad\Longleftrightarrow\quad
\text{double-trace anomalous dimensions}.
}
$$

This is one of the most useful practical facts in holographic CFT. Given a tree-level AdS correlator, one extracts the $\log u$ coefficient in an OPE channel to read off $\gamma_{n,\ell}^{(1)}$. The non-logarithmic part contains OPE-coefficient shifts, contact-term ambiguities, and possible scheme-dependent choices of basis.

## Contact interactions versus exchange interactions

At tree level in AdS, there are two basic types of Witten diagrams for a four-point function.

A **contact diagram** comes from a local quartic bulk vertex, schematically

$$
\int_{\mathrm{AdS}} d^{d+1}X\sqrt g\,\phi^4
$$

or with derivatives,

$$
\int_{\mathrm{AdS}} d^{d+1}X\sqrt g\,
(\nabla\phi)^4,
\qquad
\int_{\mathrm{AdS}} d^{d+1}X\sqrt g\,
\phi^2(\nabla^2)^k\phi^2,
\quad\ldots
$$

In the CFT, such a contact diagram has no new single-trace block in the $\mathcal O\times\mathcal O$ OPE. Instead, it directly modifies double-trace data:

$$
\phi^4\text{ contact interaction}
\quad\Longrightarrow\quad
\gamma_{n,\ell}^{(1)},\ a_{n,\ell}^{(1)}.
$$

A simple non-derivative $\phi^4$ interaction affects low-spin double-trace data in a particularly simple way. Derivative contact interactions generate more rapidly growing anomalous dimensions at large $n$, reflecting the higher-energy behavior of the bulk interaction.

An **exchange diagram** comes from cubic couplings such as

$$
\int_{\mathrm{AdS}} d^{d+1}X\sqrt g\,
\phi\phi\chi.
$$

The exchanged bulk field $\chi$ is dual to a single-trace CFT operator $\mathcal X$. In the CFT block decomposition, this appears as a single-trace conformal block contribution:

$$
\mathcal X\text{ exchange}
\quad\Longrightarrow\quad
C_{\mathcal O\mathcal O\mathcal X}^2
G_{\Delta_{\mathcal X},\ell_{\mathcal X}}(u,v)
$$

plus the accompanying double-trace corrections required by crossing.

This last phrase matters. A single block in one channel is not crossing symmetric by itself. The full Witten exchange diagram includes an infinite tower of double-trace contributions in the same channel. These double-trace terms are not optional; they are required for the correlator to be a well-defined CFT four-point function.

## The order-$1/N^2$ crossing equation

The exact crossing equation is

$$
v^\Delta \mathcal G(u,v)
=
u^\Delta \mathcal G(v,u).
$$

Substitute the expansion

$$
\mathcal G
=
\mathcal G^{(0)}
+
\frac{1}{N^2}\mathcal G^{(1)}
+
\cdots.
$$

Since mean-field theory is already crossing symmetric,

$$
v^\Delta \mathcal G^{(0)}(u,v)
=
u^\Delta \mathcal G^{(0)}(v,u),
$$

the first correction obeys the linearized crossing equation

$$
\boxed{
v^\Delta \mathcal G^{(1)}(u,v)
=
u^\Delta \mathcal G^{(1)}(v,u).
}
$$

This equation is linear in the order-$1/N^2$ data:

$$
\left\{
\gamma_{n,\ell}^{(1)},
\ a_{n,\ell}^{(1)},
\ c_{\mathcal O\mathcal O\mathcal X}^{(0)}
\right\}.
$$

The large-$N$ bootstrap is the systematic solution of this linearized crossing equation, subject to unitarity, global symmetries, and assumptions about the single-trace spectrum.

This is a good place to appreciate how the modern bootstrap and AdS effective field theory meet. Bulk locality is not an extra mystical principle pasted onto CFT. It is reflected in the allowed solutions to crossing with a sparse single-trace spectrum and controlled high-energy behavior.

## Degeneracy and operator mixing

The notation $[\mathcal O\mathcal O]_{n,\ell}$ can be misleading because it makes each double-trace primary look unique. In realistic holographic CFTs, there are often many double-trace operators with the same spin, dimension at $N=\infty$, and global quantum numbers.

For example, if there are several single-trace operators $\mathcal O_A$, one has double-trace families

$$
[\mathcal O_A\mathcal O_B]_{n,\ell}.
$$

At $N=\infty$, two different families can have the same dimension:

$$
\Delta_A+
\Delta_B+2n+
\ell
=
\Delta_C+
\Delta_D+2n'+
\ell.
$$

At order $1/N^2$, interactions mix all operators with the same exact quantum numbers. Instead of one anomalous dimension $\gamma_{n,\ell}^{(1)}$, there is a matrix

$$
\Gamma_{IJ}^{(n,\ell)}.
$$

The physical anomalous dimensions are its eigenvalues, and the physical double-trace primaries are the corresponding eigenvectors.

This is exactly the same as degenerate perturbation theory in quantum mechanics. On the cylinder,

$$
D=D^{(0)}+\frac{1}{N^2}D^{(1)}+\cdots,
$$

and one diagonalizes $D^{(1)}$ inside a degenerate $D^{(0)}$ eigenspace.

This mixing issue is not a technical annoyance. It is essential in superconformal examples, where many operators carry the same spin and $R$-symmetry representation. It is also crucial when extracting bulk interaction data from CFT correlators: a correlator may only reveal weighted averages of anomalous dimensions unless enough external operators are included to diagonalize the mixing problem.

## Mellin space in one page

Position-space Witten diagrams can be complicated. Mellin space provides a representation in which AdS correlators look more like scattering amplitudes.

For identical scalars, a schematic Mellin representation is

$$
\mathcal G(u,v)
=
\int\frac{ds\,dt}{(2\pi i)^2}
M(s,t)u^{s/2}v^{-(s+t)/2}
\times
\Gamma\text{-factors}.
$$

The exact Gamma factors are fixed by conformal kinematics and by the external dimensions. The important object is the Mellin amplitude $M(s,t)$.

The dictionary is:

| Mellin feature | AdS interpretation | CFT interpretation |
|---|---|---|
| polynomial in $s,t$ | contact interaction | local double-trace data |
| pole in $s$ or $t$ | exchange of a bulk field | single-trace conformal family |
| degree of polynomial | number of derivatives | high-energy growth of anomalous dimensions |
| crossing of $M(s,t)$ | Bose symmetry of amplitude | CFT crossing symmetry |

A non-derivative $\phi^4$ contact interaction gives a constant Mellin amplitude. A higher-derivative interaction gives a polynomial Mellin amplitude. An exchange diagram has poles whose positions are determined by the dimension and spin of the exchanged single-trace operator.

This is why Mellin space is so useful for holographic CFT: it separates the two basic kinds of order-$1/N^2$ physics, contact and exchange, in a way that resembles ordinary scattering theory.

## Large spin and long-distance forces

The lightcone bootstrap gives a universal handle on large-spin double-trace anomalous dimensions. Suppose a single-trace operator $\mathcal X$ of twist

$$
\tau_{\mathcal X}
=
\Delta_{\mathcal X}
-
\ell_{\mathcal X}
$$

appears in the crossed channel. Then at large spin,

$$
\boxed{
\gamma_{n,\ell}^{(1)}
\sim
\frac{1}{\ell^{\tau_{\mathcal X}}}
\qquad
(\ell\to\infty)
}
$$

up to an $n$-dependent coefficient and possible sums over exchanged operators.

This formula has a clean AdS meaning. Large spin corresponds to two particles orbiting far apart in global AdS. The binding energy is controlled by the longest-range force between them. The lowest-twist exchanged operator gives the slowest falloff with distance and therefore dominates the large-$\ell$ anomalous dimension.

Important examples include:

| Exchanged CFT operator | Bulk force |
|---|---|
| stress tensor $T_{\mu\nu}$ | gravity |
| conserved current $J_\mu$ | gauge force |
| light scalar $\mathcal X$ | scalar-mediated force |

This is one of the most beautiful points in holographic CFT: the asymptotic behavior of OPE data at large spin knows about long-range forces in AdS.

## Double-trace deformations

A different but closely related large-$N$ operation is a double-trace deformation of the CFT action:

$$
S
\longrightarrow
S_f
=
S+
\frac{f}{2}
\int d^d x\,\mathcal O^2(x).
$$

This is not the same thing as inserting a double-trace operator in an OPE. It is a deformation of the theory by such an operator.

At large $N$, double-trace deformations are unusually tractable because factorization makes bubble diagrams resum. In momentum space, the two-point function has the schematic form

$$
\boxed{
G_f(p)
=
\frac{G_0(p)}{1+fG_0(p)}
}
$$

up to sign conventions for the deformation and source. This is the same algebra as a geometric series.

In AdS, double-trace deformations change the boundary condition of the bulk field dual to $\mathcal O$. For a scalar with

$$
m^2R^2=\Delta(\Delta-d),
$$

both $\Delta$ and $d-\Delta$ quantizations are allowed in the window

$$
-\frac{d^2}{4}
<
m^2R^2
<
-\frac{d^2}{4}+1.
$$

In that window, double-trace RG flows interpolate between alternate and standard quantization. This is one of the cleanest examples of an RG flow that is almost entirely visible from large-$N$ CFT data.

## Effective bulk locality from CFT data

A large-$N$ CFT is not automatically dual to weakly curved Einstein gravity. It is automatically suggestive of a weakly coupled bulk theory, but the bulk may still be stringy or highly nonlocal at the AdS scale.

For a local AdS effective field theory, one wants more structure:

| CFT property | Bulk meaning |
|---|---|
| large $C_T\sim N^2$ | small bulk Newton constant |
| factorization | weak bulk interactions |
| sparse light single-trace spectrum | few light bulk fields |
| large gap $\Delta_{\rm gap}$ to higher-spin/stringy states | local effective field theory below the gap |
| controlled Mellin growth | bounded high-energy behavior |
| crossing and unitarity | consistent bulk causality/unitarity constraints |

The large gap is especially important. If infinitely many higher-spin single-trace operators remain light, the bulk is not ordinary Einstein gravity. It may instead be a Vasiliev-like higher-spin theory or a tensionless string regime.

In AdS/CFT, locality is therefore encoded in the CFT as a statement about the spectrum and asymptotic behavior of OPE data.

## AdS/CFT checkpoint

This page gives the operational bridge from CFT to perturbative AdS physics:

$$
\boxed{
\mathcal G^{(0)}
\quad\Longleftrightarrow\quad
\text{free fields in AdS},
}
$$

$$
\boxed{
\mathcal G^{(1)}
\quad\Longleftrightarrow\quad
\text{tree-level AdS interactions},
}
$$

$$
\boxed{
\gamma_{n,\ell}^{(1)}
\quad\Longleftrightarrow\quad
\text{two-particle binding energies},
}
$$

$$
\boxed{
a_{n,\ell}^{(1)}
\quad\Longleftrightarrow\quad
\text{interaction-corrected OPE wavefunction data},
}
$$

and

$$
\boxed{
\mathcal G^{(2)}
\quad\Longleftrightarrow\quad
\text{one-loop AdS effects}.
}
$$

This is why modern holography is so operator-algebraic. The bulk does not first appear as a spacetime geometry. It first appears as a pattern in CFT data:

$$
\left\{
\Delta_i,
\ C_{ijk}
\right\}
=
\text{mean field data}
+
\frac{1}{N^2}\text{interactions}
+\cdots.
$$

The rest of AdS/CFT is the art of recognizing when this pattern is produced by a local gravitational theory.

## Common pitfalls

**Pitfall 1: “Planar” means “free.”**  
No. Planar correlators can be highly interacting functions of the 't Hooft coupling $\lambda$. Generalized-free behavior refers to connected correlator suppression at $N=\infty$, not necessarily to weak microscopic coupling.

**Pitfall 2: Double-trace operators are unimportant because they are composite.**  
No. Double-trace operators are the multi-particle spectrum of AdS. They are essential.

**Pitfall 3: A single-trace exchange block is crossing symmetric by itself.**  
No. A single conformal block in one channel is not a full correlator. Crossing requires the accompanying infinite double-trace response.

**Pitfall 4: Anomalous dimensions are just technical corrections.**  
No. In the AdS interpretation, they are binding energies. Their sign and asymptotics contain physical information about forces.

**Pitfall 5: Large $N$ alone gives Einstein gravity.**  
No. Large $N$ suppresses quantum loops. A sparse spectrum and a large gap are needed for a local weakly curved gravitational effective theory.

## Exercises

### Exercise 1: Logarithms from anomalous dimensions

Suppose a double-trace conformal block contributes near the OPE limit as

$$
a_{n,\ell}u^{\Delta_{n,\ell}/2}f_{n,\ell}(v),
$$

where

$$
\Delta_{n,\ell}
=
\Delta_{n,\ell}^{(0)}
+
\frac{1}{N^2}\gamma_{n,\ell}^{(1)}
+
O(N^{-4})
$$

and

$$
a_{n,\ell}
=
a_{n,\ell}^{(0)}
+
\frac{1}{N^2}a_{n,\ell}^{(1)}
+
O(N^{-4}).
$$

Show that the coefficient of $\log u$ at order $1/N^2$ is proportional to $a_{n,\ell}^{(0)}\gamma_{n,\ell}^{(1)}$.

<details><summary><strong>Solution</strong></summary>

Expand the power of $u$:

$$
u^{\Delta_{n,\ell}/2}
=
u^{\Delta_{n,\ell}^{(0)}/2}
\exp\left[
\frac{1}{2N^2}\gamma_{n,\ell}^{(1)}\log u+O(N^{-4})
\right].
$$

Therefore

$$
u^{\Delta_{n,\ell}/2}
=
u^{\Delta_{n,\ell}^{(0)}/2}
\left[
1+
\frac{1}{2N^2}\gamma_{n,\ell}^{(1)}\log u
+
O(N^{-4})
\right].
$$

Multiplying by the OPE coefficient gives

$$
\left(a_{n,\ell}^{(0)}+
\frac{1}{N^2}a_{n,\ell}^{(1)}
+\cdots\right)
u^{\Delta_{n,\ell}^{(0)}/2}
\left[
1+
\frac{1}{2N^2}\gamma_{n,\ell}^{(1)}\log u
+\cdots
\right]
f_{n,\ell}(v).
$$

The order-$1/N^2$ logarithmic term is

$$
\frac{1}{N^2}
\left[
\frac12 a_{n,\ell}^{(0)}\gamma_{n,\ell}^{(1)}
\right]
u^{\Delta_{n,\ell}^{(0)}/2}
\log u\,f_{n,\ell}(v).
$$

Thus the $\log u$ coefficient determines $a_{n,\ell}^{(0)}\gamma_{n,\ell}^{(1)}$ in the chosen block normalization.

</details>

### Exercise 2: Scaling of single-trace exchange

Let $\mathcal O$ and $\mathcal X$ be normalized single-trace primaries in a matrix large-$N$ CFT. Use

$$
\langle \mathcal O_1\cdots\mathcal O_k\rangle_{\rm conn}
\sim
N^{2-k}
$$

to show that single-trace exchange in $\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle$ contributes at order $1/N^2$.

<details><summary><strong>Solution</strong></summary>

The three-point function of normalized single-trace operators scales as

$$
\langle \mathcal O\mathcal O\mathcal X\rangle
\sim
N^{2-3}
=
\frac{1}{N}.
$$

Thus

$$
C_{\mathcal O\mathcal O\mathcal X}
\sim
\frac{1}{N}.
$$

In a conformal block decomposition, the contribution of $\mathcal X$ appears with coefficient

$$
a_{\mathcal X}
=
C_{\mathcal O\mathcal O\mathcal X}^2
\sim
\frac{1}{N^2}.
$$

Therefore a normalized single-trace exchange block contributes to the connected four-point function at order $1/N^2$, matching tree-level AdS exchange.

</details>

### Exercise 3: Double-trace dimensions from the cylinder

Use the state-operator map to explain why the mean-field double-trace dimension is

$$
\Delta_{n,\ell}^{(0)}=2\Delta+2n+\ell.
$$

<details><summary><strong>Solution</strong></summary>

In radial quantization, a primary of dimension $\Delta$ creates a state on $S^{d-1}$ with energy $\Delta$. At $N=\infty$, two particles do not interact, so their leading energy is additive.

The lowest two-particle state made from two identical particles has energy

$$
2\Delta.
$$

Angular momentum $\ell$ on $S^{d-1}$ raises the energy by $\ell$. Radial excitations come in pairs of derivatives and raise the energy by $2n$. Thus the two-particle energy is

$$
2\Delta+\ell+2n.
$$

By the state-operator map, this energy is the scaling dimension of the corresponding double-trace primary:

$$
\Delta_{n,\ell}^{(0)}=2\Delta+2n+\ell.
$$

</details>

### Exercise 4: Linearized crossing

Given

$$
\mathcal G(u,v)
=
\mathcal G^{(0)}(u,v)
+
\frac{1}{N^2}\mathcal G^{(1)}(u,v)
+
O(N^{-4}),
$$

show that if the full correlator obeys

$$
v^\Delta\mathcal G(u,v)
=
u^\Delta\mathcal G(v,u),
$$

then $\mathcal G^{(0)}$ and $\mathcal G^{(1)}$ separately obey the same crossing equation order by order.

<details><summary><strong>Solution</strong></summary>

Substitute the large-$N$ expansion into the crossing equation:

$$
v^\Delta
\left[
\mathcal G^{(0)}(u,v)
+
\frac{1}{N^2}\mathcal G^{(1)}(u,v)
+
O(N^{-4})
\right]
=
u^\Delta
\left[
\mathcal G^{(0)}(v,u)
+
\frac{1}{N^2}\mathcal G^{(1)}(v,u)
+
O(N^{-4})
\right].
$$

Equating powers of $1/N$ gives at order $N^0$:

$$
v^\Delta\mathcal G^{(0)}(u,v)
=
u^\Delta\mathcal G^{(0)}(v,u).
$$

At order $1/N^2$ one gets

$$
v^\Delta\mathcal G^{(1)}(u,v)
=
u^\Delta\mathcal G^{(1)}(v,u).
$$

Thus the first correction obeys a linearized crossing equation.

</details>

### Exercise 5: Double-trace deformation as a geometric series

At large $N$, suppose the undeformed connected two-point function of $\mathcal O$ in momentum space is $G_0(p)$. A double-trace deformation adds

$$
\frac{f}{2}\int d^d x\,\mathcal O^2.
$$

Show schematically why the deformed two-point function has the form

$$
G_f(p)=\frac{G_0(p)}{1+fG_0(p)}
$$

up to sign conventions.

<details><summary><strong>Solution</strong></summary>

At large $N$, connected higher-point functions of $\mathcal O$ are suppressed, so the dominant correction to the two-point function is a chain of repeated double-trace insertions. In momentum space, this gives a geometric series:

$$
G_f(p)
=
G_0(p)-fG_0(p)^2+f^2G_0(p)^3-\cdots.
$$

Summing the series gives

$$
G_f(p)
=
G_0(p)
\left[
1-fG_0(p)+f^2G_0(p)^2-\cdots
\right]
=
\frac{G_0(p)}{1+fG_0(p)}.
$$

The sign depends on whether the deformation is written with $+f\mathcal O^2/2$ or $-f\mathcal O^2/2$, and on Euclidean source conventions. The important point is the large-$N$ factorization that turns the effect into a geometric resummation.

</details>

## Further reading

For large-$N$ CFT and holographic perturbation theory, the natural next references are the original large-$N$ expansion, modern large-$N$ bootstrap papers, Mellin-space treatments of AdS correlators, and reviews of holographic CFT. Useful entry points are 't Hooft on the planar expansion, Witten diagrams in early AdS/CFT, Heemskerk-Polchinski-Penedones-Sully on the CFT origin of bulk locality, Penedones on Mellin amplitudes, and modern analytic bootstrap treatments of large-spin perturbation theory.
