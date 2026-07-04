---
title: "Radial Ordering"
description: "Defines radial ordering in Euclidean CFT, explains its cylinder interpretation, and shows how it underlies radial quantization and the OPE."
sidebar:
  label: "Radial Ordering"
  order: 5
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019"
topics:
  - radial ordering
  - radial quantization
  - operator product expansion
  - Euclidean CFT
  - cylinder quantization
  - two-dimensional CFT
canonicalTopics:
  - radial-ordering
  - radial-quantization
  - operator-product-expansion
  - euclidean-cft
  - state-operator-correspondence
researchStatus:
  established:
    - "Radial ordering is Euclidean time ordering after mapping flat space to the cylinder by radial quantization."
    - "The OPE is naturally an expansion of radially ordered products in domains ordered by nested spheres or annuli."
  active:
    - "Lorentzian continuations, light-ray operators, Regge ordering, defect radial quantization, and contact-term prescriptions require more refined ordering choices."
---

## Summary

**Radial ordering** orders Euclidean operator insertions by their distance from a chosen origin. In radial quantization, the radius

$$
r=|x|
$$

is Euclidean time in disguise:

$$
\tau=\log r.
$$

Thus radial ordering is ordinary Euclidean time ordering on the cylinder $\mathbb R_\tau\times S^{d-1}$.

For two bosonic local operators,

$$
\mathcal R\{\mathcal O_1(x_1)\mathcal O_2(x_2)\}
=
\begin{cases}
\mathcal O_1(x_1)\mathcal O_2(x_2), & |x_1|>|x_2|,\\
\mathcal O_2(x_2)\mathcal O_1(x_1), & |x_2|>|x_1|.
\end{cases}
$$

For fermionic operators, exchanging the order includes the usual graded sign. Equal radii require a prescription, just as equal times require a prescription in ordinary time ordering.

Radial ordering is the quiet piece of technology behind the state–operator correspondence, OPE convergence, two-dimensional contour manipulations, Virasoro modes, and conformal-block expansions. It is less glamorous than crossing symmetry, but it is the clock that makes the operator formalism tick.

## Prerequisites

You should know [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/), [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/), [Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/), and [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/).

For the two-dimensional remarks, it helps to know the preview material in [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) and [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/), though no detailed Virasoro technology is required here.

## Core idea

Choose an origin. Spheres centered at that origin are equal-time slices. An operator farther from the origin is later in radial time and is placed to the left in a radially ordered product.

<figure class="doc-figure" style="--figure-width: 40rem;">

![Radial ordering arranges operators by nested spheres around the origin.](/figures/cft-bootstrap/radial-ordering-annuli.svg)

<figcaption>

Radial ordering places larger radius insertions to the left. In the configuration shown, $|x_3|>|x_2|>|x_1|$, so the radially ordered product is $\mathcal O_3(x_3)\mathcal O_2(x_2)\mathcal O_1(x_1)$, up to graded signs for fermionic exchanges.

</figcaption>
</figure>

The OPE is adapted to this ordering. If $\mathcal O_1(x_1)$ and $\mathcal O_2(x_2)$ lie inside a sphere that excludes every other insertion, their product can be replaced by a sum of local operators at a point inside that sphere. The replacement is an expansion of a state on the surrounding sphere.

## Setup and conventions

We work in Euclidean flat space. Write

$$
x=r n,
\qquad
r>0,
\qquad
n\in S^{d-1}.
$$

The cylinder coordinate is

$$
\tau=\log r.
$$

A scalar primary of dimension $\Delta$ is mapped to a cylinder operator by

$$
\mathcal O_{\mathrm{cyl}}(\tau,n)
=
e^{\Delta\tau}\mathcal O_{\mathbb R^d}(e^\tau n).
$$

This factor removes the Weyl scaling between flat space and the cylinder. Spinful operators require a choice of frame on the sphere; the scalar formula is the clean template.

The radial-ordering symbol $\mathcal R$ orders operators by radius, placing larger $r$ (later radial time) to the left:

$$
|x_{\sigma(1)}|>|x_{\sigma(2)}|>\cdots>|x_{\sigma(n)}|
\quad\Longrightarrow\quad
\mathcal R\{\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\}
=
\epsilon_\sigma
\mathcal O_{\sigma(1)}(x_{\sigma(1)})\cdots
\mathcal O_{\sigma(n)}(x_{\sigma(n)}),
$$

where $\epsilon_\sigma$ is the graded sign from permuting fermionic operators. For purely bosonic scalar operators, $\epsilon_\sigma=1$.

## Why radial ordering appears

In ordinary quantum mechanics, a Euclidean correlator such as

$$
\langle 0|T\{A(t_1)B(t_2)\}|0\rangle
$$

is defined by time ordering. Operators at later Euclidean time are placed to the left.

Radial quantization uses the same logic, but the time coordinate is $\tau=\log r$. A flat-space correlator becomes a cylinder correlator,

$$
\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle_{\mathbb R^d}
=
\prod_i r_i^{-\Delta_i}
\langle \mathcal R\{\mathcal O_{1,\mathrm{cyl}}(\tau_i,n_i)\cdots\mathcal O_{n,\mathrm{cyl}}(\tau_i,n_i)\}\rangle_{\mathrm{cyl}}
$$

for scalar primaries away from contact singularities. The powers $r_i^{-\Delta_i}$ are the Weyl factors returning to flat-space normalization.

This formula explains why radial ordering is not an arbitrary notation. It is the operator-ordering prescription inherited from quantizing on concentric spheres.

## Relation to states and bras

An insertion near the origin creates a ket:

$$
|\mathcal O\rangle
=
\lim_{r\to0}\mathcal O(rn)|0\rangle
$$

for a scalar primary. More generally, descendants and spin polarizations are obtained by derivatives and angular dependence.

An insertion sent to infinity creates the corresponding bra. For a Hermitian scalar primary,

$$
\langle \mathcal O|
=
\lim_{r\to\infty}r^{2\Delta}\langle 0|\mathcal O(rn).
$$

The two-point function becomes the Hilbert-space inner product. With the normalization

$$
\langle \mathcal O(x)\mathcal O(0)\rangle=\frac{1}{|x|^{2\Delta}},
$$

one gets

$$
\langle \mathcal O|\mathcal O\rangle=1.
$$

Radial ordering is what makes this expression an inner product rather than an unordered Euclidean product.

## Relation to the OPE

Suppose

$$
|x_1|>|x_2|.
$$

Then the radially ordered product is

$$
\mathcal R\{\mathcal O_i(x_1)\mathcal O_j(x_2)\}
=
\mathcal O_i(x_1)\mathcal O_j(x_2)
$$

for bosonic operators. If $|x_2|>|x_1|$, the order is reversed.

The OPE is usually written for a product in a chosen radial domain. In two-dimensional notation, for example,

$$
A(z)B(w)=\sum_k C_{AB}{}^k(z-w)\mathcal O_k(w)
\qquad
\text{for } |z|>|w|
$$

when the origin is used for radial quantization. The same analytic expression may be continued elsewhere, but the operator interpretation as a product on the Hilbert space depends on the radial ordering.

In higher dimensions, the domain is better stated with spheres: the operators being fused must lie inside a sphere that separates them from the other insertions. Radial ordering is the special case where those spheres are centered at the chosen origin.

## Annuli and convergence

Radial ordering naturally produces annuli. If all insertions in one cluster lie at radii smaller than all insertions in another cluster, then there is an annulus between them:

$$
r_{\mathrm{inside}}<r<r_{\mathrm{outside}}.
$$

Inserting a complete set of states on a sphere in the annulus gives

$$
\mathbf 1=\sum_\alpha |\alpha\rangle\langle \alpha|,
$$

and radial time evolution gives suppression factors

$$
e^{-(\tau_{\mathrm{outside}}-\tau_{\mathrm{inside}})\Delta_\alpha}
=
\left(\frac{r_{\mathrm{inside}}}{r_{\mathrm{outside}}}\right)^{\Delta_\alpha}.
$$

This is the same mechanism behind [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/). The annulus is the Euclidean breathing room that lets the intermediate-state expansion converge.

## Two-dimensional notation

In two dimensions, radial ordering is usually described on the complex plane. Write

$$
z=re^{i\theta}.
$$

Then radial time is

$$
\tau=\log |z|.
$$

For bosonic chiral fields,

$$
\mathcal R\{A(z)B(w)\}
=
\begin{cases}
A(z)B(w), & |z|>|w|,\\
B(w)A(z), & |w|>|z|.
\end{cases}
$$

This convention is the backbone of contour manipulations. Modes are defined by contours around the origin, for example

$$
A_n=\oint_0\frac{dz}{2\pi i}\,z^{n+h-1}A(z)
$$

for a holomorphic field of weight $h$. Commutators are computed by moving contours through radially ordered products and collecting OPE singularities. This is how the Virasoro algebra is extracted from the stress-tensor OPE.

The two-dimensional technology is more elaborate because holomorphic factorization and chiral algebras provide extra structure. The radial-ordering idea itself is the same one used in any dimension.

## Radial ordering versus ordinary time ordering

Radial ordering is not Lorentzian time ordering. It is Euclidean time ordering for the cylinder time $\tau$.

A Lorentzian time-ordered correlator orders insertions by physical time $t$. A radial-ordered Euclidean correlator orders insertions by $|x|$. The two are related by analytic continuation only after specifying the desired Lorentzian ordering and the associated $i\epsilon$ prescription.

This distinction matters in Lorentzian CFT. Wightman functions, time-ordered correlators, retarded correlators, out-of-time-order correlators, lightcone OPEs, and Regge limits are different analytic continuations or orderings of Euclidean data. Radial ordering is the Euclidean starting point, not the whole Lorentzian story.

## Equal radii and contact terms

Radial ordering is unambiguous when all radii are distinct. If two operators lie on the same sphere,

$$
|x_i|=|x_j|,
$$

then the ordering needs a prescription. One may separate the radii slightly, average, or define an angular-ordering convention in two-dimensional chiral settings. Which prescription is natural depends on the problem.

Coincident points are a separate issue. When $x_i\to x_j$, operator products have singularities and contact terms. The OPE describes those singularities, while Ward identities track the contact terms associated with currents and the stress tensor.

A safe rule is: do radial-ordering manipulations with separated insertions first, then take limits only after the singular terms are controlled.

## Common pitfalls

**Pitfall 1: thinking radial ordering is coordinate-free.** It depends on a chosen origin. Different origins give different radial-time slicings. Physical correlators are independent of this choice, but a particular operator-channel expansion is not.

**Pitfall 2: confusing radial order with Euclidean permutation symmetry.** Euclidean scalar correlators at separated points are symmetric under exchange, but the operator product on the radial-quantization Hilbert space still has an order.

**Pitfall 3: ignoring equal-radius prescriptions.** Equal radial time is like equal ordinary time: contact terms and commutators may sit exactly where the naive formula is ambiguous.

**Pitfall 4: using radial ordering as Lorentzian time ordering.** Lorentzian observables require analytic continuation and an $i\epsilon$ prescription. Radial ordering alone does not specify a retarded or time-ordered Lorentzian correlator.

**Pitfall 5: forgetting the Weyl factor on the cylinder.** A primary operator on the cylinder differs from the flat-space operator by a factor $e^{\Delta\tau}$ for scalars.

## Relations to other pages

[Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/) develops the Hilbert-space picture on spheres. [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/) uses radial ordering to identify local insertions with states. [Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/) explains how radial inversion turns kets into bras.

Within this chapter, [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/) explains why annuli give convergent expansions, and [Associativity of the OPE](/cft-bootstrap/operator-product-expansion/associativity-of-ope/) explains how different radial-ordering channels lead to crossing symmetry.

## Research status

Radial ordering in ordinary Euclidean CFT is standard. It is one of the basic definitions behind radial quantization and the operator formalism.

Active research often asks for more refined orderings: Lorentzian light-ray operators, Regge limits, modular-flow ordering, defect radial quantization, celestial correlators, and nontrivial operator algebras with extended objects. These refinements do not replace radial ordering; they extend the same operator-ordering discipline to more delicate settings.

## Exercises

### Exercise 1: cylinder two-point function

Let $\mathcal O$ be a scalar primary with

$$
\langle \mathcal O(x)\mathcal O(y)\rangle
=\frac{1}{|x-y|^{2\Delta}}.
$$

Using $x=e^\tau n$ and $y=n'$ with $n,n'\in S^{d-1}$, show that

$$
\langle \mathcal O_{\mathrm{cyl}}(\tau,n)\mathcal O_{\mathrm{cyl}}(0,n')\rangle
=
\frac{1}{\left[2(\cosh\tau-n\cdot n')\right]^\Delta}.
$$

<details><summary><strong>Solution</strong></summary>

The flat-space distance is

$$
|e^\tau n-n'|^2
=e^{2\tau}+1-2e^\tau n\cdot n'
=2e^\tau(\cosh\tau-n\cdot n').
$$

The cylinder operator is

$$
\mathcal O_{\mathrm{cyl}}(\tau,n)=e^{\Delta\tau}\mathcal O(e^\tau n),
$$

while $\mathcal O_{\mathrm{cyl}}(0,n')=\mathcal O(n')$. Therefore

$$
\langle \mathcal O_{\mathrm{cyl}}(\tau,n)\mathcal O_{\mathrm{cyl}}(0,n')\rangle
=
\frac{e^{\Delta\tau}}{
\left[2e^\tau(\cosh\tau-n\cdot n')\right]^\Delta}
=
\frac{1}{\left[2(\cosh\tau-n\cdot n')\right]^\Delta}.
$$

</details>

### Exercise 2: radial ordering of three operators

For bosonic operators with radii

$$
|x_2|>|x_3|>|x_1|,
$$

write the radially ordered product $\mathcal R\{\mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\}$.

<details><summary><strong>Solution</strong></summary>

The largest radius is placed leftmost. Therefore

$$
\mathcal R\{\mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\}
=
\mathcal O_2(x_2)\mathcal O_3(x_3)\mathcal O_1(x_1).
$$

For fermionic operators, one would also include the graded sign from the permutation needed to reach this order.

</details>

### Exercise 3: radial suppression

Suppose an intermediate state has scaling dimension $\Delta_\alpha$. Show that evolving it from radius $r$ to radius $R>r$ gives a factor $(r/R)^{\Delta_\alpha}$.

<details><summary><strong>Solution</strong></summary>

Radial time is $\tau=\log r$. The time difference is

$$
\Delta\tau=\log R-\log r=\log\frac{R}{r}.
$$

The cylinder Hamiltonian is the dilatation generator $D$. Acting on a state with $D|\alpha\rangle=\Delta_\alpha|\alpha\rangle$, Euclidean time evolution gives

$$
e^{-\Delta\tau D}|\alpha\rangle
=e^{-\Delta\tau\Delta_\alpha}|\alpha\rangle
=\left(\frac{r}{R}\right)^{\Delta_\alpha}|\alpha\rangle.
$$

This is the basic suppression factor behind Euclidean OPE convergence.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, 1997.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, 2016.
- D. Simmons-Duffin, “The Conformal Bootstrap,” 2017.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” 2019.

## Version history

- **2026-06-27:** First polished draft. Defines radial ordering, relates it to cylinder time ordering, explains its role in the OPE and two-dimensional contour manipulations, and records common Lorentzian and equal-radius caveats.
