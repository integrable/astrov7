---
title: "Generalized Free Fields"
description: "How generalized free fields give crossing-symmetric mean-field CFT correlators with arbitrary scaling dimension, double-trace spectra, and large-N interpretation."
sidebar:
  label: "Generalized Free Fields"
  order: 7
level: Graduate
status: "Polished draft"
source: "Rychkov lectures; Simmons-Duffin TASI lectures; Poland, Rychkov, and Vichi 2019; large-N and conformal bootstrap literature."
topics:
  - generalized free fields
  - mean-field theory
  - large-N CFT
  - double-trace operators
  - conformal bootstrap
canonicalTopics:
  - generalized-free-fields
  - mean-field-cft
  - double-trace-spectrum
researchStatus:
  established:
    - "Generalized free fields provide exact crossing-symmetric correlators whose OPE contains double-trace-like primaries with dimensions 2 Delta plus spin and radial excitation number."
  active:
    - "Generalized free fields remain central as starting points for large-N perturbation theory, holographic CFT, analytic bootstrap, and studies of approximate locality in AdS."
---

## Summary

A **generalized free field** is a scalar primary $\phi$ whose correlation functions obey Wick-like factorization but whose scaling dimension $\Delta_\phi$ is not forced to be the free scalar value. Its two-point function is

$$
\langle\phi(x)\phi(0)\rangle=\frac{1}{(x^2)^{\Delta_\phi}}.
$$

Its four-point function is the disconnected Wick sum:

$$
\langle\phi_1\phi_2\phi_3\phi_4\rangle
=\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}
\left[1+u^{\Delta_\phi}+\left(\frac{u}{v}\right)^{\Delta_\phi}\right],
$$

where

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The result is exactly crossing-symmetric. Its OPE contains the identity and an infinite tower of double-trace-like primary operators

$$
[\phi\phi]_{n,\ell},
\qquad
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell,
\qquad
n=0,1,2,\ldots .
$$

For identical scalar $\phi$, only even spin $\ell$ appears in $\phi\times\phi$.

Generalized free fields are not ordinary free fields unless $\Delta_\phi=(d-2)/2$ and the correct equation of motion and stress tensor are present. They are best understood as mean-field CFT data, large-$N$ leading approximations, or consistent sectors whose stress tensor has decoupled in the $C_T\to\infty$ limit.

## Prerequisites

Read [Conformal Symmetry in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/conformal-symmetry-in-higher-dimensions/), [Unitarity Bounds in d Dimensions](/cft-bootstrap/higher-dimensional-cft/unitarity-bounds-in-d-dimensions/), [Operator Product Expansion](/cft-bootstrap/operator-product-expansion/), and [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) first.

You should know the scalar cross-ratios $u,v$ and the idea that a four-point function can be decomposed into conformal blocks labeled by exchanged primary dimensions and spins.

## Core idea

A genuine free scalar field has Wick factorization because it is Gaussian. A generalized free field keeps the Wick-like correlation functions but lets the scaling dimension be arbitrary, subject to unitarity:

$$
\Delta_\phi\ge\frac{d-2}{2}.
$$

This produces a huge simplification. Every even-point function is a sum over pairings:

$$
\langle\phi(x_1)\cdots\phi(x_{2m})\rangle
=\sum_{\text{pairings}}\prod_{(ij)}\frac{1}{(x_{ij}^2)^{\Delta_\phi}},
$$

and odd-point functions vanish:

$$
\langle\phi(x_1)\cdots\phi(x_{2m+1})\rangle=0.
$$

Despite this simplicity, the OPE is not trivial. The four-point function decomposes into an infinite tower of primary operators with dimensions

$$
2\Delta_\phi+2n+\ell.
$$

The slogan is

$$
\text{Wick-like correlators with arbitrary }\Delta
\quad\Longrightarrow\quad
\text{crossing-symmetric double-trace spectrum}.
$$

Generalized free fields are the mean-field-theory solution of CFT crossing.

## Setup and conventions

We consider a scalar primary $\phi$ in a Euclidean CFT in $d>2$. The two-point function is normalized as

$$
\langle\phi(x)\phi(0)\rangle=\frac{1}{(x^2)^{\Delta_\phi}}.
$$

For four points, use

$$
\langle\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}\mathcal G(u,v),
$$

with

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The generalized free field four-point function is

$$
\mathcal G_{\rm GFF}(u,v)
=1+u^{\Delta_\phi}+\left(\frac{u}{v}\right)^{\Delta_\phi}.
$$

The three terms correspond to the three pairings:

$$
(12)(34),
\qquad
(13)(24),
\qquad
(14)(23).
$$

When $\phi$ is identical and bosonic, the correlator is invariant under all permutations of the four points.

## Crossing symmetry

For identical scalars, crossing symmetry can be written as

$$
\mathcal G(u,v)=\left(\frac{u}{v}\right)^{\Delta_\phi}\mathcal G(v,u).
$$

For the generalized free field,

$$
\mathcal G(u,v)=1+u^{\Delta_\phi}+\left(\frac{u}{v}\right)^{\Delta_\phi}.
$$

Now compute the crossed expression:

$$
\left(\frac{u}{v}\right)^{\Delta_\phi}\mathcal G(v,u)
=\left(\frac{u}{v}\right)^{\Delta_\phi}\left[1+v^{\Delta_\phi}+\left(\frac{v}{u}\right)^{\Delta_\phi}\right].
$$

This equals

$$
\left(\frac{u}{v}\right)^{\Delta_\phi}+u^{\Delta_\phi}+1,
$$

which is the same function. Thus generalized free fields solve crossing exactly.

This is why they are so useful in bootstrap. They give a simple exact point in the space of crossing-symmetric CFT data.

## OPE interpretation

The $s$-channel OPE limit is

$$
x_1\to x_2,
\qquad
u\to0.
$$

The term $1$ in $\mathcal G(u,v)$ is the identity exchange. The other terms must be reproduced by an infinite tower of nontrivial primaries in the $\phi\times\phi$ OPE.

These primaries are schematically

$$
[\phi\phi]_{n,\ell}\sim
\phi\,\partial_{\mu_1}\cdots\partial_{\mu_\ell}(\partial^2)^n\phi
-\text{traces and descendants}.
$$

Their dimensions are

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell.
$$

Here $n$ is a radial excitation number and $\ell$ is spin. For identical scalars, Bose symmetry keeps only even $\ell$.

The word “double-trace” comes from large-$N$ gauge theory, where $\phi$ is often a single-trace operator and $[\phi\phi]$ is a double-trace composite. But the same kinematic spectrum appears for generalized free fields even without referring to matrices or traces.

## Why the dimensions are additive

The dimensions

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell
$$

have a simple interpretation. A composite made from two primaries has leading dimension $2\Delta_\phi$. Adding $\ell$ derivatives to make spin $\ell$ raises the dimension by $\ell$. Adding $n$ powers of a two-derivative scalar structure raises the dimension by $2n$.

Thus the tower resembles two-particle states on the cylinder. In radial quantization, a primary of dimension $\Delta_\phi$ creates a state of energy $\Delta_\phi$ on $S^{d-1}$. Two noninteracting particles have energy approximately

$$
2\Delta_\phi+\text{integer excitation energy}.
$$

Generalized free fields are therefore the CFT analogue of noninteracting multiparticle kinematics.

This interpretation becomes literal in large-$N$ CFTs and holography. Double-trace operators correspond to two-particle states in AdS, and anomalous dimensions measure interactions between them.

## Generalized free versus free

The name “generalized free field” is slightly dangerous. A generalized free field is usually not a local free field satisfying a differential equation.

Compare:

| Feature | Ordinary free scalar | Generalized free scalar |
|---|---|---|
| Dimension | $\Delta=(d-2)/2$ | arbitrary $\Delta\ge(d-2)/2$ in unitary cases |
| Equation of motion | $\partial^2\phi=0$ | no local equation in general |
| Correlators | Wick factorization | Wick-like factorization |
| Stress tensor | local stress tensor present | generally absent from the GFF sector |
| OPE spectrum | constrained by the free equation | double-trace tower with arbitrary input $\Delta$ |

If $\Delta_\phi=(d-2)/2$, the scalar saturates the unitarity bound and the descendant

$$
\partial^2\phi
$$

is null. This is the ordinary free scalar case. For generic $\Delta_\phi$, no such equation exists.

The absence of a local stress tensor is the most important caveat. A standalone local CFT should have a stress tensor. The generalized free field alone normally does not provide one. It is best viewed as a consistent set of correlators, or as a sector in a theory where the stress tensor is parametrically weakly coupled.

## Large-N interpretation

In large-$N$ CFTs, normalized single-trace operators often factorize:

$$
\langle\mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=\langle\mathcal O_1\mathcal O_2\rangle\langle\mathcal O_3\mathcal O_4\rangle
+\text{pairings}+O\left(\frac{1}{N^2}\right).
$$

At leading order in $1/N$, a single-trace scalar behaves like a generalized free field. Corrections generate connected four-point functions:

$$
\mathcal G(u,v)=\mathcal G_{\rm GFF}(u,v)+\frac{1}{N^2}\mathcal G^{(1)}(u,v)+\cdots .
$$

These corrections do two things:

1. They shift double-trace dimensions:

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell+rac{1}{N^2}\gamma_{n,\ell}+\cdots .
$$

2. They correct OPE coefficients:

$$
\lambda_{n,\ell}^2=\lambda_{n,\ell}^{2,(0)}+rac{1}{N^2}\lambda_{n,\ell}^{2,(1)}+\cdots .
$$

Thus GFF data are the zeroth-order point around which large-$N$ perturbation theory is organized.

## Holographic interpretation

In AdS/CFT, a generalized free field on the boundary corresponds to a free field propagating in AdS with interactions turned off. The boundary dimension $\Delta$ is related to the bulk mass by

$$
m^2R_{\rm AdS}^2=\Delta(\Delta-d).
$$

The double-trace tower corresponds to two-particle states in global AdS. The integer $n$ counts radial excitation, and $\ell$ is angular momentum on $S^{d-1}$.

Bulk interactions produce connected boundary correlators. In CFT language, these interactions generate anomalous dimensions and OPE coefficient corrections for double-trace operators.

The dictionary is:

| Boundary GFF object | Bulk AdS interpretation |
|---|---|
| single-trace-like primary $\phi$ | one-particle field in AdS |
| GFF four-point function | disconnected propagation of two particles |
| $[\phi\phi]_{n,\ell}$ | two-particle state in global AdS |
| anomalous dimension $\gamma_{n,\ell}$ | interaction energy of the two-particle state |
| connected $1/N$ correction | Witten diagrams or bulk interactions |

This is why generalized free fields are everywhere in holographic bootstrap.

## Mean-field theory CFT

Generalized free fields are also called mean-field theory CFT data. The phrase does not mean Landau mean-field theory in every microscopic detail. It means that the four-point function is disconnected and factorized, like a Gaussian theory.

The associated conformal block decomposition is nontrivial. In the $s$ channel,

$$
\mathcal G_{\rm GFF}(u,v)=1+\sum_{n,\ell}a_{n,\ell}^{(0)}G_{2\Delta_\phi+2n+\ell,\ell}(u,v),
$$

with positive coefficients

$$
a_{n,\ell}^{(0)}\ge0
$$

in a unitary normalization. The explicit formula for $a_{n,\ell}^{(0)}$ depends on conformal-block conventions, but the spectrum and positivity are convention-independent.

The next page, [Mean-Field Theory CFT](/cft-bootstrap/higher-dimensional-cft/mean-field-theory-cft/), can develop the block decomposition and coefficients in more detail.

## Stress tensor and locality caveat

A local CFT in flat space should have a stress tensor $T_{\mu\nu}$. The generalized free field sector by itself usually does not contain a stress tensor with the right Ward identity.

One way to see this is from the OPE. The stress tensor would have spin two and dimension

$$
\Delta_T=d.
$$

The GFF double-trace spectrum contains spin-two operators with dimensions

$$
2\Delta_\phi+2n+2.
$$

For generic $\Delta_\phi$, none of these equals $d$ with the correct Ward identity. Even if a dimension accidentally matches, the Ward identity is not automatic.

In large-$N$ theories, the stress tensor exists but its coupling to a normalized single-trace scalar can be suppressed by powers of $1/N$. In the strict $N\to\infty$ limit, the sector generated by $\phi$ can look generalized free while the stress tensor effectively decouples.

Therefore:

$$
\text{GFF correlators are crossing-symmetric}
\ne
\text{complete standalone local CFT in the usual sense}.
$$

This distinction is subtle and important.

## Generalized free fermions and spinning fields

The same idea applies to spinful primaries. A generalized free fermion has a conformally covariant two-point function with arbitrary allowed dimension, and higher-point functions are built by Wick contractions with fermionic signs.

Similarly, one can define generalized free vector or tensor primaries, subject to the appropriate unitarity bounds and tensor structures.

The scalar case is the cleanest and most widely used because it underlies the identical-scalar bootstrap and large-$N$ scalar correlators. Spinning generalized free fields are useful in fermion bootstrap, conserved-current bootstrap, and holographic theories with bulk spin.

A key warning persists: generalized free spinful fields do not automatically come with gauge invariance, conservation, or a stress tensor. Those are extra shortening or Ward-identity conditions, not consequences of Wick-like factorization alone.

## Common pitfalls

**Do not confuse generalized free with ordinary free.** Ordinary free fields satisfy local equations of motion and have canonical dimensions. Generalized free fields usually do not.

**Do not forget the stress-tensor caveat.** A GFF sector by itself generally lacks a local stress tensor with the correct Ward identity.

**Do not think disconnected means OPE-trivial.** The GFF four-point function has a nontrivial conformal block decomposition with infinitely many double-trace primaries.

**Do not include odd spins for identical scalar GFFs.** Bose symmetry allows only even symmetric traceless spin in $\phi\times\phi$.

**Do not assume all double-trace dimensions remain additive in an interacting theory.** Interactions generate anomalous dimensions.

**Do not apply GFF intuition to nonunitary dimensions without checking positivity.** In a unitary CFT, $\Delta_\phi$ must obey the scalar unitarity bound.

**Do not confuse mean-field theory with a microscopic Landau theory.** Here “mean-field” refers to factorized CFT correlators and their conformal block decomposition.

## Relations to other pages

This page follows [Unitarity Bounds in d Dimensions](/cft-bootstrap/higher-dimensional-cft/unitarity-bounds-in-d-dimensions/) and prepares [Mean-Field Theory CFT](/cft-bootstrap/higher-dimensional-cft/mean-field-theory-cft/) and [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/).

It connects to [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/), and [Identical Scalar Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/identical-scalar-bootstrap/), because GFF is the simplest exact crossing-symmetric scalar four-point solution.

For holographic applications, see [Holographic CFT](/cft-bootstrap/holographic-cft/) and the later pages on AdS contact diagrams and large-spin perturbation theory.

## Research status

Generalized free fields are established and standard in conformal bootstrap, large-$N$ CFT, and holography. Their correlators, double-trace spectra, and role as mean-field data are basic tools.

Active research uses GFF data as the starting point for analytic bootstrap, large-spin perturbation theory, AdS effective field theory, constraints on bulk locality, large-$N$ anomalous dimensions, and numerical bootstrap studies near mean-field-like solutions.

## Exercises

### Exercise 1

Verify crossing symmetry of the generalized free scalar four-point function

$$
\mathcal G(u,v)=1+u^{\Delta}+\left(\frac{u}{v}\right)^\Delta.
$$

<details><summary><strong>Solution</strong></summary>

For identical scalars, crossing under $x_1\leftrightarrow x_3$ can be written as

$$
\mathcal G(u,v)=\left(\frac{u}{v}\right)^\Delta\mathcal G(v,u).
$$

Compute

$$
\left(\frac{u}{v}\right)^\Delta\mathcal G(v,u)
=\left(\frac{u}{v}\right)^\Delta
\left[1+v^\Delta+\left(\frac{v}{u}\right)^\Delta\right].
$$

This is

$$
\left(\frac{u}{v}\right)^\Delta+u^\Delta+1,
$$

which equals

$$
1+u^\Delta+\left(\frac{u}{v}\right)^\Delta.
$$

Thus the GFF four-point function is crossing-symmetric.

</details>

### Exercise 2

Why do only even spins appear in the OPE of two identical scalar generalized free fields?

<details><summary><strong>Solution</strong></summary>

The OPE $\phi\times\phi$ of two identical bosonic scalars must be symmetric under exchanging the two scalars. A symmetric traceless spin-$\ell$ operator contributes to the scalar-scalar-spin-$\ell$ three-point function with a factor that changes sign as $(-1)^\ell$ under exchanging the two scalar positions.

Exchange symmetry therefore requires

$$
(-1)^\ell=1,
$$

so

$$
\ell\text{ is even}.
$$

</details>

### Exercise 3

Explain the dimension formula

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell.
$$

<details><summary><strong>Solution</strong></summary>

The schematic double-trace operator is made from two fields and derivatives:

$$
[\phi\phi]_{n,\ell}\sim
\phi\,\partial_{\mu_1}\cdots\partial_{\mu_\ell}(\partial^2)^n\phi-	ext{traces and descendants}.
$$

The two fields contribute

$$
2\Delta_\phi.
$$

The $\ell$ spin-carrying derivatives contribute $\ell$, and the $n$ powers of $\partial^2$ contribute $2n$. Therefore

$$
\Delta_{n,\ell}=2\Delta_\phi+\ell+2n.
$$

</details>

### Exercise 4

Why is a generalized free field not usually a complete local CFT by itself?

<details><summary><strong>Solution</strong></summary>

A complete local CFT should contain a stress tensor $T_{\mu\nu}$ with dimension $d$, spin two, conservation, and the correct Ward identity for translations and conformal transformations.

A generalized free field sector has Wick-like correlators and a double-trace spectrum, but it generally does not contain a spin-two dimension-$d$ operator with the correct stress-tensor Ward identity. Therefore it is usually best viewed as a consistent crossing-symmetric sector or as the leading large-$N$ limit of a sector in a full CFT, not as a complete standalone local CFT.

</details>

### Exercise 5

What happens to double-trace dimensions when interactions are turned on at large $N$?

<details><summary><strong>Solution</strong></summary>

At leading large $N$, the dimensions are additive:

$$
\Delta_{n,\ell}^{(0)}=2\Delta_\phi+2n+\ell.
$$

Interactions produce anomalous dimensions suppressed by powers of $1/N$:

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell+rac{1}{N^2}\gamma_{n,\ell}+\cdots,
$$

for a standard large-$N$ counting. The anomalous dimension measures the interaction energy of the two-particle state, or equivalently the departure from generalized free behavior.

</details>

## References

- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2016.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, “Holography from conformal field theory,” *Journal of High Energy Physics* **2009**.
- A. L. Fitzpatrick, J. Kaplan, D. Poland, and D. Simmons-Duffin, “The analytic bootstrap and AdS superhorizon locality,” *Journal of High Energy Physics* **2013**.
- L. F. Alday, “Large spin perturbation theory for conformal field theories,” *Physical Review Letters* **119** (2017).

## Version history

- 2026-06-30: First polished draft. Added GFF definition, crossing check, double-trace spectrum, free-field distinction, large-$N$ and holographic interpretations, stress-tensor caveat, exercises, and references.
