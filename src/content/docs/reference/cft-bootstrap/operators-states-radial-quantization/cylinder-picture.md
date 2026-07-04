---
title: "Cylinder Picture"
description: "Explains the conformal map from flat space to the cylinder, the identification of cylinder energy with scaling dimension, and the use of cylinder correlators in CFT."
sidebar:
  label: "Cylinder Picture"
  order: 6
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2017; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019; Cardy 1996"
topics:
  - cylinder picture
  - radial quantization
  - state-operator correspondence
  - scaling dimensions
  - conformal map
  - cylinder correlators
  - finite-size spectrum
canonicalTopics:
  - cylinder-picture
  - plane-cylinder-map
  - cylinder-hamiltonian
  - radial-time-evolution
  - finite-size-spectrum
researchStatus:
  established:
    - 'Punctured flat Euclidean space is conformally equivalent to the cylinder $\\mathbb R\\times S^{d-1}$, and the generator of cylinder time translations is the dilatation generator $D$.'
    - 'For local operator states in radial quantization, scaling dimensions are cylinder energies and spin is angular momentum on $S^{d-1}$.'
  active:
    - "The basic map is standard; current applications include thermal CFT, modular bootstrap, Lorentzian cylinder kinematics, defect cylinders, finite-size spectra, and stress-tensor anomaly effects."
---

## Summary

The cylinder picture is the geometric form of radial quantization. Write a point in Euclidean flat space as

$$
x=r n,
\qquad
n\in S^{d-1},
\qquad
r=e^\tau.
$$

Then

$$
ds_{\mathbb R^d}^2=dr^2+r^2d\Omega_{d-1}^2
=e^{2\tau}\left(d\tau^2+d\Omega_{d-1}^2\right).
$$

After removing the Weyl factor, punctured flat space is mapped to the cylinder

$$
\mathbb R^d\setminus\{0\}
\quad\longrightarrow\quad
\mathbb R_\tau\times S^{d-1}.
$$

Dilatations $r\mapsto\lambda r$ become translations in cylinder time $\tau\mapsto\tau+\log\lambda$. Therefore

$$
H_{\rm cyl}=D.
$$

A local operator of dimension $\Delta$ creates a cylinder state of energy $\Delta$:

$$
\mathcal O(0)|0\rangle
\quad\longleftrightarrow\quad
E_{\rm cyl}=\Delta.
$$

<figure class="doc-figure" style="--figure-width: 43rem;">

![The logarithmic radial coordinate maps concentric spheres in flat space to time slices on the cylinder.](/figures/cft-bootstrap/flat-space-to-cylinder-map.svg)

<figcaption>

The coordinate $\tau=\log r$ maps concentric spheres in $\mathbb R^d$ to constant-time slices on $\mathbb R_\tau\times S^{d-1}$. Dilatations become translations along the cylinder, and the spectrum of $D$ becomes the cylinder energy spectrum.

</figcaption>
</figure>

This picture is why CFT spectra look like energy spectra, why finite-size spectra determine scaling dimensions in statistical systems, and why the bootstrap organizes four-point functions by propagation of conformal multiplets on the cylinder.

:::note[The slogan]
Flat-space scaling becomes cylinder time evolution. The local-operator spectrum becomes the energy spectrum on $S^{d-1}$.
:::

## Prerequisites

You should know [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/) and [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/). The pages [Scaling Dimensions and Spin](/cft-bootstrap/operators-states-radial-quantization/scaling-dimensions-and-spin/) and [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/) explain the operator labels that become cylinder quantum numbers.

You should also know the basic action of conformal generators from [Conformal Generators](/cft-bootstrap/conformal-symmetry/conformal-generators/). No two-dimensional CFT is required, although the two-dimensional version of the cylinder picture has special central-charge effects discussed below.

## Core idea

A CFT has no intrinsic length scale. This makes the following maneuver natural: instead of treating radius $r$ as a distance, treat

$$
\tau=\log r
$$

as Euclidean time. Equal-time slices are spheres. Moving forward in time means expanding the sphere.

The map

$$
x=e^\tau n
$$

separates scale from direction. The direction $n$ is a point on $S^{d-1}$; the scale is cylinder time $\tau$.

The flat metric is conformal to the cylinder metric:

$$
ds_{\rm flat}^2=e^{2\tau}ds_{\rm cyl}^2,
\qquad
ds_{\rm cyl}^2=d\tau^2+d\Omega_{d-1}^2.
$$

Because a CFT is invariant under Weyl rescalings up to known anomaly terms, local flat-space correlation functions can be translated into cylinder correlation functions. The origin of flat space becomes the far past of the cylinder, and infinity becomes the far future:

$$
r\to0 \quad\Longleftrightarrow\quad \tau\to-\infty,
\qquad
r\to\infty \quad\Longleftrightarrow\quad \tau\to+\infty.
$$

Thus an operator at the origin creates an incoming cylinder state, while an operator at infinity creates the corresponding outgoing bra.

## Setup and conventions

Unless stated otherwise, the cylinder radius is set to one:

$$
ds_{\rm cyl}^2=d\tau^2+d\Omega_{d-1}^2.
$$

If the sphere has radius $R$, the cylinder metric is

$$
ds_{\rm cyl}^2=dt^2+R^2d\Omega_{d-1}^2,
$$

and local-operator energies scale as

$$
E_{\rm cyl}=\frac{\Delta}{R}
$$

up to possible vacuum-energy shifts.

For a scalar primary of dimension $\Delta$, the operator on the cylinder is related to the flat-space operator by the Weyl factor

$$
\mathcal O_{\rm cyl}(\tau,n)
=e^{\Delta\tau}\mathcal O_{\rm flat}(e^\tau n).
$$

Equivalently,

$$
\mathcal O_{\rm flat}(x)=r^{-\Delta}\mathcal O_{\rm cyl}(\tau,n).
$$

For spinning operators, one also transforms the local frame or tensor indices. For the stress tensor, extra anomaly terms can appear; this is one reason stress-tensor transformations are more delicate than primary scalar transformations.

## Cylinder Hamiltonian and angular momentum

Dilatations act on flat space as

$$
x\mapsto e^a x.
$$

In cylinder variables this is

$$
\tau\mapsto\tau+a.
$$

Therefore the generator of cylinder time translations is the dilatation generator:

$$
H_{\rm cyl}=D.
$$

Rotations of the sphere are generated by the ordinary rotation generators $M_{\mu\nu}$. Thus the quantum numbers of a local operator become cylinder quantum numbers:

| Flat-space operator label | Cylinder interpretation |
|---|---|
| scaling dimension $\Delta$ | energy on $S^{d-1}$ |
| $SO(d)$ spin | angular momentum on $S^{d-1}$ |
| primary | lowest-energy state in a conformal multiplet |
| descendant | excitation produced by $P_\mu$ |
| conserved current | shortened multiplet with a null descendant |

For a primary state,

$$
D|\mathcal O\rangle=\Delta|\mathcal O\rangle,
\qquad
K_\mu|\mathcal O\rangle=0.
$$

Acting with $P_\mu$ raises energy because

$$
[D,P_\mu]=P_\mu.
$$

Thus descendants lie at integer-spaced levels above the primary,

$$
E=\Delta,\quad \Delta+1,\quad \Delta+2,\quad\ldots,
$$

before quotienting null states.

## Radial evolution as Euclidean time evolution

Cylinder time evolution is generated by $D$. If a state has dimension $\Delta$, then Euclidean evolution by a time interval $T$ gives

$$
e^{-T H_{\rm cyl}}|\mathcal O\rangle
=
e^{-T\Delta}|\mathcal O\rangle.
$$

In flat-space radial variables, a radial ratio is a time interval:

$$
T=\log\frac{r_{\rm out}}{r_{\rm in}}.
$$

Therefore propagation of a state of dimension $\Delta$ across an annulus gives

$$
e^{-\Delta T}
=
\left(\frac{r_{\rm in}}{r_{\rm out}}\right)^\Delta.
$$

This simple factor is the seed of radial OPE convergence, conformal-block expansions, and spectral decompositions of CFT correlators.

## Cylinder two-point function

Take a scalar primary normalized in flat space by

$$
\langle\mathcal O(x_1)\mathcal O(x_2)\rangle_{\rm flat}
=
\frac{1}{|x_{12}|^{2\Delta}}.
$$

Write $x_i=e^{\tau_i}n_i$ with $n_i^2=1$. Then

$$
|x_{12}|^2
=
e^{\tau_1+\tau_2}
\left(2\cosh\tau_{12}-2n_1\cdot n_2\right),
\qquad
\tau_{12}=\tau_1-\tau_2.
$$

Using

$$
\mathcal O_{\rm cyl}(\tau,n)
=
e^{\Delta\tau}\mathcal O_{\rm flat}(e^\tau n),
$$

the cylinder correlator becomes

$$
\langle\mathcal O(\tau_1,n_1)\mathcal O(\tau_2,n_2)\rangle_{\rm cyl}
=
\frac{1}{\left(2\cosh\tau_{12}-2n_1\cdot n_2\right)^\Delta}.
$$

At fixed angular position $n_1=n_2$ and large $|\tau_{12}|$,

$$
\langle\mathcal O(\tau_1,n)\mathcal O(\tau_2,n)\rangle_{\rm cyl}
\sim e^{-\Delta|\tau_{12}|}.
$$

The power-law decay in flat space has become exponential decay in cylinder time.

## Four-point functions and conformal blocks

The cylinder picture is especially useful for four-point functions. Put two operators in the far past and two operators in the far future. Insert a complete set of cylinder states between them. The result is a spectral decomposition:

$$
\sum_{\text{states }\alpha}
\langle \Psi_{\rm out}|\alpha\rangle
e^{-E_\alpha T}
\langle\alpha|\Psi_{\rm in}\rangle.
$$

Grouping states into conformal multiplets gives conformal blocks. The primary chooses the multiplet; descendants fill out the block. Crossing symmetry says that different ways of slicing the same four-point function must agree.

This is the cylinder Hilbert-space version of the bootstrap equation. The equation is not just an identity among special functions; it is equality between different spectral decompositions of the same correlator.

## Two-dimensional cylinder formulas

In two dimensions, write

$$
z=e^w,
\qquad
w=\tau+i\sigma,
\qquad
\sigma\sim\sigma+2\pi.
$$

A primary with weights $(h,\bar h)$ has

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

On the radial cylinder, the representation-theoretic Hamiltonian and momentum are

$$
H_{\rm rad}=L_0+\bar L_0,
\qquad
P_{\rm cyl}=L_0-\bar L_0.
$$

For a physical CFT on a cylinder of circumference $L$, the stress-tensor transformation includes the Schwarzian derivative. The finite-size Hamiltonian is commonly written

$$
H_{\rm phys}
=
\frac{2\pi}{L}
\left(L_0+\bar L_0-\frac{c}{12}\right),
$$

and the momentum is

$$
P_{\rm phys}
=
\frac{2\pi}{L}
\left(L_0-\bar L_0\right).
$$

The $-c/12$ term is the total Casimir shift from the two chiral sectors. It is not a contradiction with $E=\Delta$; it reflects the difference between measuring energies relative to the radial-quantization vacuum and including the physical vacuum energy on a curved finite cylinder.

## Vacuum energy and anomalies

The statement $H_{\rm cyl}=D$ is the representation-theoretic statement used in radial quantization. It assigns the identity state energy zero and a local operator state energy $\Delta$.

However, when the CFT is placed as a physical theory on a curved cylinder, the vacuum energy need not vanish. In even dimensions, Weyl anomalies can also affect stress-tensor expectation values and partition functions. The clean rule is:

| Context | What to remember |
|---|---|
| local operator spectrum | energies are $E=\Delta/R$ on a radius-$R$ sphere |
| radial quantization | vacuum energy is set so that the identity has energy zero |
| physical finite-size cylinder | a Casimir energy may shift all energies by a constant |
| stress-tensor correlators | Weyl anomaly and improvement terms require care |
| scalar primary correlators | transform by the simple Weyl factor shown above |

Most bootstrap formulas use the first two rows. Modular bootstrap and thermal CFT often require the finite-size vacuum energy carefully.

## Relation to statistical physics

In a lattice statistical system near a critical point, the transfer matrix on a cylinder has energy levels. In the continuum limit, those levels are organized by the CFT on the cylinder. Scaling dimensions can therefore be extracted from finite-size gaps:

$$
E_n-E_0=\frac{\Delta_n}{R}
$$

up to the conventional normalization of the cylinder radius and velocity. In two-dimensional lattice systems with spatial circumference $L$, this often appears as

$$
E_n-E_0=\frac{2\pi}{L}\Delta_n.
$$

This is one of the most concrete ways the cylinder picture enters numerical and statistical physics: the spectrum of a finite system remembers the scaling dimensions of the critical theory.

## Common pitfalls

**Forgetting the Weyl factor.** The coordinate change $r=e^\tau$ alone gives the flat metric with an overall factor. CFT lets us remove that factor, but primary fields transform with Weyl weight.

**Confusing radial energy with physical Casimir-shifted energy.** In radial quantization, the identity has energy zero and $E=\Delta$. On a physical cylinder, the vacuum energy can be shifted, most famously by $-c/12$ in two-dimensional CFT.

**Thinking the cylinder is optional decoration.** The cylinder is the Hilbert-space home of the local operator spectrum. It is not merely a picture for the same formulas.

**Forgetting angular momentum.** The sphere is not a point. Spin labels become angular momentum labels on $S^{d-1}$.

**Using the same formula for stress tensors and scalar primaries.** Scalar primaries transform simply. The stress tensor has anomalous terms under Weyl transformations, especially in even dimensions and in two-dimensional CFT.

**Equating thermal time with radial time too quickly.** A thermal partition function on $S^{d-1}$ is a trace over $e^{-\beta H_{\rm cyl}}$. Radial quantization uses Euclidean time on the cylinder, but a local flat-space correlator is not automatically a thermal observable.

## Relations to other pages

[Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/) constructs the slicing by spheres. [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/) identifies cylinder states with local operators. [Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/) explains why the far future of the cylinder corresponds to insertion at infinity.

[Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/) uses positivity of cylinder states. [Conformal Blocks](/cft-bootstrap/conformal-blocks/) packages propagation of one conformal multiplet on the cylinder. [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) and [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/) develop the special two-dimensional cylinder formulas.

[Thermal and Lorentzian CFT](/cft-bootstrap/thermal-lorentzian-cft/) returns to the cylinder as a physical spacetime for finite-temperature and real-time questions.

## Research status

The cylinder picture is established and universal in CFT. It is one of the main reasons CFT is tractable without a Lagrangian: scale transformations become Hamiltonian evolution, and local operator data become spectral data.

Active uses include high-precision finite-size spectra, modular bootstrap, thermal one-point functions, Lorentzian inversion formulas, defect cylinders, entanglement mappings, and numerical bootstrap methods based on radial coordinates. The conceptual map is old; the computational leverage keeps getting better.

## Exercises

### Exercise 1: derive the cylinder metric

Starting from

$$
ds^2=dr^2+r^2d\Omega_{d-1}^2
$$

and $r=e^\tau$, show that flat space is conformal to the cylinder.

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

The expression in parentheses is the metric on $\mathbb R_\tau\times S^{d-1}$, so flat punctured space is Weyl equivalent to the cylinder.

</details>

### Exercise 2: energy from a scale transformation

Let $|\mathcal O\rangle$ be a state created by a scaling operator of dimension $\Delta$. Show that Euclidean cylinder evolution by $T$ multiplies the state by $e^{-T\Delta}$.

<details><summary><strong>Solution</strong></summary>

Cylinder time translations are generated by

$$
H_{\rm cyl}=D.
$$

If

$$
D|\mathcal O\rangle=\Delta|\mathcal O\rangle,
$$

then Euclidean evolution gives

$$
e^{-T H_{\rm cyl}}|\mathcal O\rangle
=
e^{-T D}|\mathcal O\rangle
=
e^{-T\Delta}|\mathcal O\rangle.
$$

Thus the cylinder energy is $E=\Delta$ for a unit-radius cylinder.

</details>

### Exercise 3: cylinder two-point function

Use the Weyl transformation of a scalar primary to derive

$$
\langle\mathcal O(\tau_1,n_1)\mathcal O(\tau_2,n_2)\rangle_{\rm cyl}
=
\frac{1}{\left(2\cosh\tau_{12}-2n_1\cdot n_2\right)^\Delta}.
$$

<details><summary><strong>Solution</strong></summary>

Start from the flat-space two-point function

$$
\langle\mathcal O(x_1)\mathcal O(x_2)\rangle_{\rm flat}
=
\frac{1}{|x_{12}|^{2\Delta}}.
$$

Write $x_i=e^{\tau_i}n_i$. Then

$$
|x_{12}|^2
=
e^{2\tau_1}+e^{2\tau_2}-2e^{\tau_1+\tau_2}n_1\cdot n_2
=
e^{\tau_1+\tau_2}
\left(2\cosh\tau_{12}-2n_1\cdot n_2\right).
$$

The cylinder operator is

$$
\mathcal O_{\rm cyl}(\tau,n)=e^{\Delta\tau}\mathcal O_{\rm flat}(e^\tau n).
$$

Therefore

$$
\langle\mathcal O_1\mathcal O_2\rangle_{\rm cyl}
=
e^{\Delta(\tau_1+\tau_2)}
\frac{1}{
\left[
e^{\tau_1+\tau_2}
\left(2\cosh\tau_{12}-2n_1\cdot n_2\right)
\right]^\Delta},
$$

which simplifies to the claimed expression.

</details>

### Exercise 4: large-time decay

Set $n_1=n_2$ in the cylinder two-point function and show that it decays like $e^{-\Delta |\tau_{12}|}$ at large time separation.

<details><summary><strong>Solution</strong></summary>

For $n_1=n_2$, we have $n_1\cdot n_2=1$, so

$$
2\cosh\tau_{12}-2
=
4\sinh^2\frac{\tau_{12}}{2}.
$$

At large $|\tau_{12}|$,

$$
\sinh^2\frac{\tau_{12}}{2}
\sim
\frac14 e^{|\tau_{12}|}.
$$

Thus

$$
2\cosh\tau_{12}-2
\sim
e^{|\tau_{12}|},
$$

and the correlator behaves as

$$
\langle\mathcal O(\tau_1,n)\mathcal O(\tau_2,n)\rangle_{\rm cyl}
\sim
e^{-\Delta |\tau_{12}|}.
$$

This is Euclidean propagation of a state of cylinder energy $\Delta$.

</details>

### Exercise 5: two-dimensional Casimir shift

In a two-dimensional CFT on a circle of circumference $L$, explain why

$$
H_{\rm phys}
=
\frac{2\pi}{L}
\left(L_0+\bar L_0-\frac{c}{12}\right)
$$

is compatible with the radial-quantization statement $H_{\rm rad}=L_0+\bar L_0$.

<details><summary><strong>Solution</strong></summary>

The radial-quantization Hamiltonian is the generator of dilatations on the plane. It assigns the identity state energy zero:

$$
H_{\rm rad}|0\rangle=0.
$$

When the CFT is placed on a physical cylinder, the stress tensor transforms anomalously under the plane-cylinder map. The Schwarzian derivative produces a Casimir energy shift. For circumference $L$, the total shift from the holomorphic and antiholomorphic sectors is

$$
-\frac{2\pi}{L}\frac{c}{12}.
$$

Therefore $H_{\rm phys}$ is the physical finite-size Hamiltonian including vacuum energy, while $H_{\rm rad}$ is the representation-theoretic dilatation generator. Energy differences are controlled by scaling dimensions in either convention.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. See the operator formalism, the map from cylinder to plane, radial quantization, and finite-size formulas in two-dimensional CFT.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2017. Higher-dimensional treatment of radial quantization and the cylinder interpretation of scaling dimensions.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982. Bootstrap-oriented account of radial quantization, reflection positivity, and cylinder-state decompositions.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91**, 015002 (2019), arXiv:1805.04405. Modern review connecting CFT data, conformal blocks, radial coordinates, and crossing.
- J. Cardy, *Scaling and Renormalization in Statistical Physics*, Cambridge University Press, 1996. Useful for finite-size scaling and the statistical-physics interpretation of cylinder spectra.

## Version history

- 2026-06-27: First polished draft.
