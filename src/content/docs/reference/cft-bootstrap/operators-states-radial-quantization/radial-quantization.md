---
title: "Radial Quantization"
description: "Explains radial quantization in conformal field theory, the map from flat space to the cylinder, radial ordering, conjugation by inversion, and why scaling dimensions become cylinder energies."
sidebar:
  label: "Radial Quantization"
  order: 4
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2017; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019; Pappadopulo et al. 2012"
topics:
  - radial quantization
  - state-operator correspondence
  - cylinder quantization
  - dilatation operator
  - radial ordering
  - inversion positivity
  - OPE convergence
canonicalTopics:
  - radial-quantization
  - cylinder-map
  - state-operator-map
  - radial-ordering
  - inversion-conjugation
researchStatus:
  established:
    - 'Radial quantization maps flat-space CFT on punctured $\mathbb R^d$ to quantization on $\mathbb R\times S^{d-1}$, with the dilatation generator $D$ as the cylinder Hamiltonian.'
    - 'The adjoint relation $P_\mu^\dagger=K_\mu$ and positivity of radial-quantization norms underlie unitarity bounds and the Hilbert-space interpretation of CFT data.'
  active:
    - "The basic construction is standard; active applications include radial-coordinate conformal blocks, Lorentzian inversion formulas, defect radial quantization, numerical bootstrap algorithms, and rigorous OPE convergence."
---

## Summary

Radial quantization is the operator formalism adapted to a conformal field theory. Instead of choosing a Cartesian coordinate as Euclidean time, one chooses the logarithm of radius:

$$
\tau=\log r,
\qquad
r=|x|.
$$

Equal-time slices are spheres $S^{d-1}$ centered at the origin. The flat metric on punctured Euclidean space becomes

$$
ds^2=dr^2+r^2d\Omega_{d-1}^2
=e^{2\tau}\left(d\tau^2+d\Omega_{d-1}^2\right).
$$

A CFT is insensitive to the Weyl factor in this local construction, up to anomaly subtleties discussed below. Thus flat space with the origin removed is conformally equivalent to the cylinder

$$
\mathbb R_\tau\times S^{d-1}.
$$

The Hamiltonian that translates $\tau$ is the dilatation generator:

$$
H_{\rm cyl}=D.
$$

Therefore a local operator of scaling dimension $\Delta$ creates a cylinder state of energy $\Delta$.

<figure class="doc-figure" style="--figure-width: 43rem;">

![Radial quantization maps concentric spheres in flat space to constant-time slices on the cylinder.](/figures/cft-bootstrap/radial-quantization-cylinder.svg)

<figcaption>

Radial quantization replaces planar time slices by spheres around the origin. The coordinate $\tau=\log r$ maps concentric spheres in $\mathbb R^d$ to constant-time slices of the cylinder $\mathbb R_\tau\times S^{d-1}$. Dilatations become cylinder time translations.

</figcaption>
</figure>

This construction is the reason the state-operator correspondence is so natural, why descendants have dimensions $\Delta+n$, why $P_\mu^\dagger=K_\mu$ in unitary CFTs, and why the OPE is a convergent expansion rather than only an asymptotic one.

## Prerequisites

You should know the CFT-specific [Conventions and Notation](/cft-bootstrap/conventions/), the conformal generators from [Conformal Generators](/cft-bootstrap/conformal-symmetry/conformal-generators/), and the representation language of [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/) and [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/). The page [Scaling Dimensions and Spin](/cft-bootstrap/operators-states-radial-quantization/scaling-dimensions-and-spin/) explains the quantum numbers that radial quantization turns into cylinder energies and angular momenta.

This page uses Euclidean signature. Lorentzian CFT requires additional care with causal ordering, Hilbert-space time evolution, and analytic continuation, but radial quantization remains one of the cleanest ways to define CFT data.

## Core idea

Ordinary canonical quantization chooses equal-time planes. Radial quantization chooses equal-radius spheres.

In Euclidean QFT, no coordinate has to be time. A choice of “time” is a choice of how to slice the path integral into states. In radial quantization, the path integral over the ball $|x|<R$ prepares a state on the sphere $|x|=R$. Inserting a local operator at the origin changes that state.

The origin is the infinite past:

$$
r\to0
\quad\Longleftrightarrow\quad
\tau\to-\infty.
$$

Infinity is the infinite future:

$$
r\to\infty
\quad\Longleftrightarrow\quad
\tau\to+\infty.
$$

Dilatations $x\mapsto \lambda x$ shift radial time:

$$
\tau\mapsto \tau+\log\lambda.
$$

This is the whole trick. Scale transformations become time translations. Scaling dimensions become energies.

## Setup and conventions

Write a nonzero point in $\mathbb R^d$ as

$$
x^\mu=r n^\mu,
\qquad
r>0,
\qquad
n^\mu n_\mu=1.
$$

The flat metric is

$$
ds^2=dx^\mu dx_\mu=dr^2+r^2d\Omega_{d-1}^2.
$$

With

$$
r=e^\tau,
\qquad
dr=e^\tau d\tau,
$$

this becomes

$$
ds^2=e^{2\tau}\left(d\tau^2+d\Omega_{d-1}^2\right).
$$

After removing the Weyl factor $e^{2\tau}$, the geometry is the cylinder

$$
ds_{\rm cyl}^2=d\tau^2+d\Omega_{d-1}^2.
$$

A CFT can be transported between these two geometries because conformal transformations include Weyl rescalings. Correlation functions of primary operators transform with the appropriate powers of the Weyl factor. In even dimensions, Weyl anomalies can affect quantities such as the stress tensor and the partition function on curved backgrounds; they do not invalidate the local radial-quantization construction on flat space.

## The cylinder Hamiltonian

The operator that translates $\tau$ is $D$. Indeed,

$$
\tau\mapsto \tau+a
$$

means

$$
r\mapsto e^a r,
\qquad
x^\mu\mapsto e^a x^\mu,
$$

which is precisely a dilatation. Therefore

$$
H_{\rm cyl}=D.
$$

If a state has dimension $\Delta$,

$$
D|\Psi\rangle=\Delta|\Psi\rangle,
$$

then its cylinder time evolution is

$$
e^{-\tau H_{\rm cyl}}|\Psi\rangle=e^{-\tau\Delta}|\Psi\rangle.
$$

This is why CFT spectra are energy spectra on the cylinder.

The rotation generators $M_{\mu\nu}$ act within each sphere $S^{d-1}$. Thus the spin of a local operator is the angular momentum representation of the state it creates on the cylinder.

## States from local operators

The path integral over the ball with a local insertion at the origin prepares a state. For a local operator $\mathcal O(0)$,

$$
|\mathcal O\rangle=\mathcal O(0)|0\rangle.
$$

If $\mathcal O$ is a primary with dimension $\Delta$ and spin representation $\rho$, then

$$
D|\mathcal O\rangle=\Delta|\mathcal O\rangle,
$$

and $M_{\mu\nu}$ acts on $|\mathcal O\rangle$ in the representation $\rho$.

Descendant states are generated by translations:

$$
P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle.
$$

Because $[D,P_\mu]=P_\mu$, these states have cylinder energies $\Delta+n$.

This is the state-operator correspondence in its first form. The dedicated page [State-Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/) develops the inverse statement: under good conditions, every normalizable state on $S^{d-1}$ corresponds to a local operator at the origin.

## Bras, infinity, and inversion

In radial quantization, the bra dual to a ket created at the origin is represented by an insertion at infinity. The map that exchanges the origin and infinity is inversion:

$$
x^\mu\mapsto x'^{\mu}=\frac{x^\mu}{x^2}.
$$

For a scalar primary, radial Hermitian conjugation is encoded by

$$
\mathcal O(x)^\dagger
=|x|^{-2\Delta}\mathcal O\left(\frac{x}{x^2}\right),
$$

up to the ordinary internal Hermitian conjugation of the operator. For spinning primaries, one also includes the appropriate inversion tensor or spin representation matrix.

The bra associated with a scalar primary may be written as

$$
\langle\mathcal O|
=\lim_{r\to\infty} r^{2\Delta}\langle0|\mathcal O(r n),
$$

with the angular and spin indices treated appropriately. The factor $r^{2\Delta}$ precisely cancels the falloff of the two-point function.

For a scalar normalized by

$$
\langle\mathcal O(x)\mathcal O(0)\rangle
=\frac{C_{\mathcal O}}{|x|^{2\Delta}},
$$

one obtains

$$
\langle\mathcal O|\mathcal O\rangle=C_{\mathcal O}.
$$

In a unitary CFT, this norm must be positive for nonzero states.

## Radial ordering

Radial ordering replaces Euclidean time ordering. For two bosonic operators,

$$
R\{\mathcal O_1(x_1)\mathcal O_2(x_2)\}
=
\begin{cases}
\mathcal O_1(x_1)\mathcal O_2(x_2), & |x_1|>|x_2|,\\
\mathcal O_2(x_2)\mathcal O_1(x_1), & |x_2|>|x_1|.
\end{cases}
$$

For fermionic operators, the second line carries the usual sign. The operator at smaller radius acts earlier in radial time, closer to the ket in the far past.

This is not just a notational choice. Many familiar CFT formulas are operator statements only after radial ordering. In two-dimensional CFT, contour integrals around insertions are interpreted using radial ordering: deforming a contour past an operator computes a commutator.

## Adjoint relations for generators

In radial quantization, inversion conjugation gives the important adjoint relations

$$
D^\dagger=D,
\qquad
M_{\mu\nu}^\dagger=M_{\mu\nu},
\qquad
P_\mu^\dagger=K_\mu.
$$

The last relation is especially powerful. Translations raise dimension, special conformal transformations lower dimension, and the two are adjoints.

For a primary state,

$$
K_\mu|\mathcal O\rangle=0.
$$

Descendant norms can therefore be computed algebraically. For example, if $\mathcal O$ is a scalar primary,

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=\langle\mathcal O|K_\mu P_\nu|\mathcal O\rangle
=2\delta_{\mu\nu}\Delta\langle\mathcal O|\mathcal O\rangle.
$$

At higher levels, positivity of descendant norms produces the unitarity bounds. Saturation of a bound means that a descendant has zero norm and is removed from the physical Hilbert space. Conservation equations and free equations of motion are the most familiar examples.

## Reflection and inversion positivity

Euclidean unitarity is usually expressed as reflection positivity. Radial quantization gives a conformally adapted version called inversion positivity.

A ket is prepared by inserting operators inside the unit sphere. The corresponding bra is prepared by inserting conjugate operators at the inverted points outside the unit sphere:

$$
x_i\mapsto \frac{x_i}{x_i^2}.
$$

The norm of the state is then a correlation function in an inversion-symmetric configuration. Positivity of this norm is the Hilbert-space positivity condition written in radial language.

This is why radial quantization is not merely a pretty coordinate system. It is the bridge between Euclidean correlation functions and a positive Hilbert space.

## OPE convergence

The operator product expansion becomes a Hilbert-space spectral expansion in radial quantization. Suppose two operators are inserted inside a sphere and all other operators in the correlation function are outside that sphere. Then the product of the inside operators creates a state on the sphere. Expanding that state in cylinder energy eigenstates gives the OPE.

Schematically,

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k \lambda_{ijk}\,C_{ij}{}^k(x,\partial)\mathcal O_k(0).
$$

Radial quantization explains the region of convergence: the expansion converges when the sphere enclosing the two operators does not enclose any other insertion. This is much stronger than saying the OPE is only an asymptotic short-distance expansion.

This perspective also explains why conformal blocks are organized by dimensions and spin. In a four-point function, inserting a complete set of cylinder states between pairs of operators gives a sum over conformal multiplets. The powers in the radial expansion are controlled by the cylinder energies $\Delta+n$.

## Two-dimensional version

In two dimensions, write

$$
z=re^{i\sigma}=e^{\tau+i\sigma}.
$$

Equivalently, the cylinder coordinate is

$$
w=\tau+i\sigma,
\qquad
z=e^w.
$$

The generators are related to Virasoro modes by

$$
D=L_0+\bar L_0,
\qquad
M=L_0-\bar L_0.
$$

A primary with weights $(h,\bar h)$ creates a state with

$$
D|h,\bar h\rangle=(h+\bar h)|h,\bar h\rangle,
$$

and spin

$$
M|h,\bar h\rangle=(h-\bar h)|h,\bar h\rangle.
$$

In a unitary two-dimensional CFT,

$$
L_n^\dagger=L_{-n},
\qquad
\bar L_n^\dagger=\bar L_{-n}.
$$

There is also an important stress-tensor subtlety: mapping the plane to the cylinder can shift the physical cylinder energy by a Casimir term because the stress tensor has a Schwarzian transformation law. The algebraic state-operator label $\Delta=h+\bar h$ is still the eigenvalue of $L_0+\bar L_0$ on the plane; finite-size Hamiltonians often involve the shifted combination $L_0+\bar L_0-c/12$.

## What radial quantization gives you

Radial quantization packages many CFT facts into one picture.

| Fact | Radial-quantization explanation |
|---|---|
| Scaling dimensions are energies | $D$ translates $\tau=\log r$. |
| Spin is angular momentum | Rotations act on $S^{d-1}$ slices. |
| Operators create states | Insertions inside a sphere prepare states on the sphere. |
| Bras live at infinity | Inversion maps the origin to infinity. |
| $P_\mu^\dagger=K_\mu$ | Translation and special conformal generators are conjugate under inversion. |
| Unitarity bounds exist | Descendant norms must be nonnegative. |
| OPE converges | The OPE is a spectral expansion on the cylinder. |
| Conformal blocks have radial expansions | Blocks sum the states in one conformal multiplet. |

This is why radial quantization appears everywhere in modern CFT, even when a calculation begins in ordinary flat coordinates.

## Common pitfalls

**Do not confuse radial time with physical Lorentzian time.** Radial time is a Euclidean quantization coordinate. It becomes a true Hilbert-space time for the cylinder theory, but it is not the original Lorentzian time coordinate.

**Do not forget the Weyl factor.** Flat punctured space and the cylinder differ by a Weyl factor. Primary operators transform simply, but stress tensors, anomalies, and partition functions can carry extra terms.

**Do not place the bra at ordinary finite radius.** The natural conjugate of an operator at the origin is an insertion at infinity, defined through inversion and a compensating power of radius.

**Do not omit radial ordering in operator equations.** OPEs and contour manipulations are operator statements only after the appropriate radial ordering is understood.

**Do not think descendants are arbitrary excitations.** Descendants are the cylinder states obtained by acting with $P_\mu$ on primaries. Their energies and many matrix elements are fixed by symmetry.

**Do not identify a zero-norm descendant with a small correction.** In a unitary CFT, a null descendant is quotiented out. Its vanishing is an exact shortening condition, such as conservation or an equation of motion.

## Relations to other pages

[Scaling Dimensions and Spin](/cft-bootstrap/operators-states-radial-quantization/scaling-dimensions-and-spin/) explains the quantum numbers that become cylinder energy and angular momentum.

[State-Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/) develops the one-to-one map between local operators and normalizable states.

[Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/) treats inversion, adjoints, and positivity more systematically.

[Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/) derives the bounds from descendant norms.

[OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/) uses radial quantization to explain the convergence domain of the operator product expansion.

[Radial Coordinates](/cft-bootstrap/conformal-blocks/radial-coordinates/) develops the $\rho$ coordinate and the radial expansion of conformal blocks.

## Research status

Radial quantization is a settled part of CFT. It is standard in two-dimensional operator formalism, higher-dimensional bootstrap, state-operator correspondence, unitarity bounds, and conformal-block theory.

Current research uses the same construction in more refined ways. Radial coordinates improve numerical convergence of conformal blocks. Defect CFTs use radial quantization around a defect. Lorentzian inversion formulas combine radial and causal ideas. Rigorous bootstrap work uses Hilbert-space positivity and OPE convergence. The construction is old; the ways we exploit it keep getting sharper.

## Exercises

### Exercise 1: Derive the cylinder metric

Starting from

$$
ds^2=dr^2+r^2d\Omega_{d-1}^2,
$$

set $r=e^\tau$. Show that the metric is Weyl-equivalent to the cylinder.

<details><summary><strong>Solution</strong></summary>

Since $r=e^\tau$,

$$
dr=e^\tau d\tau.
$$

Therefore

$$
dr^2=e^{2\tau}d\tau^2,
\qquad
r^2d\Omega_{d-1}^2=e^{2\tau}d\Omega_{d-1}^2.
$$

Thus

$$
ds^2=e^{2\tau}\left(d\tau^2+d\Omega_{d-1}^2\right).
$$

Removing the Weyl factor gives the cylinder metric

$$
ds_{\rm cyl}^2=d\tau^2+d\Omega_{d-1}^2.
$$

</details>

### Exercise 2: Dilatations are time translations

Show that a scale transformation $x\mapsto \lambda x$ shifts $\tau=\log r$ by $\log\lambda$.

<details><summary><strong>Solution</strong></summary>

Under $x\mapsto \lambda x$,

$$
r=|x|\mapsto r'=|\lambda x|=\lambda r
$$

for $\lambda>0$. Therefore

$$
\tau'=\log r'=\log(\lambda r)=\log\lambda+\log r
=\tau+
\log\lambda.
$$

So dilatations act as translations in radial time.

</details>

### Exercise 3: Norm from a scalar two-point function

Let

$$
\langle\mathcal O(x)\mathcal O(0)\rangle=\frac{C_{\mathcal O}}{|x|^{2\Delta}}.
$$

Using

$$
\langle\mathcal O|=
\lim_{r\to\infty}r^{2\Delta}\langle0|\mathcal O(r n),
$$

compute $\langle\mathcal O|\mathcal O\rangle$.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
\langle\mathcal O|\mathcal O\rangle
=\lim_{r\to\infty}r^{2\Delta}
\langle\mathcal O(r n)\mathcal O(0)\rangle.
$$

Substitute the two-point function:

$$
\langle\mathcal O|\mathcal O\rangle
=\lim_{r\to\infty}r^{2\Delta}\frac{C_{\mathcal O}}{r^{2\Delta}}
=C_{\mathcal O}.
$$

In a unitary CFT, a nonzero state must have $C_{\mathcal O}>0$ after choosing a Hermitian operator basis.

</details>

### Exercise 4: First descendant norm of a scalar

Let $|\mathcal O\rangle$ be a scalar primary with dimension $\Delta$. Use

$$
P_\mu^\dagger=K_\mu,
\qquad
[K_\mu,P_\nu]=2\delta_{\mu\nu}D-2M_{\mu\nu},
$$

to compute $\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle$.

<details><summary><strong>Solution</strong></summary>

Since $|\mathcal O\rangle$ is primary,

$$
K_\mu|\mathcal O\rangle=0.
$$

Thus

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=\langle\mathcal O|K_\mu P_\nu|\mathcal O\rangle
=\langle\mathcal O|[K_\mu,P_\nu]|\mathcal O\rangle.
$$

For a scalar primary,

$$
M_{\mu\nu}|\mathcal O\rangle=0,
$$

so

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=2\delta_{\mu\nu}\Delta\langle\mathcal O|\mathcal O\rangle.
$$

Positivity at this level implies $\Delta\ge0$ for a nonzero scalar state. The sharper scalar unitarity bound in $d>2$ comes from higher-level descendants.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. See the operator formalism chapter for radial quantization, radial ordering, Hermitian conjugation by inversion, and the cylinder-plane map.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, Springer, 2017. Higher-dimensional treatment of radial quantization, state-operator correspondence, and unitarity.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982. Modern bootstrap-oriented discussion of radial quantization, reflection positivity, and conformal blocks.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405. Review of radial quantization, inversion positivity, unitarity bounds, and radial conformal-block expansions.
- D. Pappadopulo, S. Rychkov, J. Espin, and R. Rattazzi, “OPE Convergence in Conformal Field Theory,” *Physical Review D* **86** (2012), arXiv:1208.6449. Foundational modern reference for OPE convergence from radial quantization.

## Version history

- 2026-06-27: First polished draft. Explains the flat-space-to-cylinder map, cylinder Hamiltonian, state creation by local operators, inversion conjugation, radial ordering, unitarity positivity, OPE convergence, and the two-dimensional cylinder-plane notation.
