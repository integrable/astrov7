---
title: "Euclidean and Lorentzian CFT"
description: "Explains the relation between Euclidean and Lorentzian conformal field theory, Wick rotation, reflection positivity, radial quantization, cylinder evolution, and Lorentzian correlator prescriptions."
sidebar:
  label: "Euclidean and Lorentzian CFT"
  order: 6
level: Graduate
status: "Polished draft"
source: "Osterwalder–Schrader 1973; Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2017; Simmons-Duffin 2016; Hartman 2015; Poland–Rychkov–Vichi 2019"
topics:
  - Euclidean CFT
  - Lorentzian CFT
  - Wick rotation
  - reflection positivity
  - radial quantization
  - cylinder picture
  - Wightman functions
  - time ordering
  - causality
  - conformal bootstrap
canonicalTopics:
  - euclidean-and-lorentzian-cft
  - wick-rotation
  - euclidean-reconstruction
  - lorentzian-correlators
  - radial-quantization-cylinder
researchStatus:
  established:
    - "Euclidean CFT and Lorentzian CFT are two related but not identical presentations of a quantum field theory; reflection positivity and analytic continuation are the bridge between them."
    - "Most conformal bootstrap equations are written in Euclidean signature, while causal, thermal, Regge, and collider questions require Lorentzian continuation and careful operator ordering."
  active:
    - "Lorentzian CFT techniques, including lightcone limits, inversion formulae, energy conditions, Regge limits, and modular-flow methods, remain central in current bootstrap, holography, and quantum-information applications."
---

## Summary

A conformal field theory can be studied in **Euclidean signature**, where correlation functions behave like statistical-mechanics observables, or in **Lorentzian signature**, where the same theory has real time, causal order, commutators, and a Hilbert-space interpretation.

In Euclidean flat space the metric is positive definite,

$$
ds_E^2=d\tau^2+d\mathbf x^2,
$$

and scalar primary two-point functions have the simple separated-point form

$$
\langle \mathcal O(x)\mathcal O(0)\rangle_E
=
\frac{C_\mathcal O}{(x_E^2)^\Delta},
\qquad
x_E^2=\tau^2+\mathbf x^2.
$$

In Lorentzian flat space, using the mostly-minus convention of the site,

$$
ds_L^2=dt^2-d\mathbf x^2,
\qquad
x_L^2=t^2-\mathbf x^2,
$$

operator order matters. A Wightman two-point function is obtained from the Euclidean expression only after specifying an $i\epsilon$ prescription, for example

$$
\langle 0|\mathcal O(t,\mathbf x)\mathcal O(0)|0\rangle
=
\frac{C_\mathcal O}{\left(\mathbf x^2-(t-i\epsilon)^2\right)^\Delta}
$$

for a scalar primary in the standard vacuum ordering. Other orderings have different prescriptions.

The slogan is:

$$
\text{Euclidean CFT gives the clean algebraic data; Lorentzian CFT tells you how it propagates and commutes.}
$$

A Euclidean collection of functions is not automatically a unitary Lorentzian quantum theory. To reconstruct a Hilbert space with positive norm and causal evolution, the Euclidean correlators must satisfy reflection positivity and the rest of the Euclidean reconstruction conditions. This is why [Unitarity and Reflection Positivity](/cft-bootstrap/what-is-a-cft/unitarity-and-reflection-positivity/) is not a decorative axiom. It is the bridge.

## Prerequisites

You should know the basic definitions of [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/), [Local Operators as Observables](/cft-bootstrap/what-is-a-cft/local-operators-as-observables/), and [Unitarity and Reflection Positivity](/cft-bootstrap/what-is-a-cft/unitarity-and-reflection-positivity/). You should also know the site-wide [Conventions and Normalizations](/foundations/conventions-and-normalizations/) and the CFT-specific [Conventions and Notation](/cft-bootstrap/conventions/).

This page does not assume detailed knowledge of radial quantization. It previews the ideas that are developed later in [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/), [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/), and [Cylinder Picture](/cft-bootstrap/operators-states-radial-quantization/cylinder-picture/).

## Core idea

The words “Euclidean” and “Lorentzian” are sometimes used too casually. They do not merely describe two sign conventions for the metric. They describe two different ways of organizing the same physics.

Euclidean CFT is the natural language for:

| Euclidean question | Typical object |
|---|---|
| Critical phenomena | Schwinger functions and scaling limits |
| Bootstrap equations | Euclidean four-point functions and crossing |
| Radial quantization | Operator insertions ordered by radius |
| Statistical mechanics | Partition functions and Euclidean path integrals |
| Reflection positivity | Euclidean version of Hilbert-space positivity |

Lorentzian CFT is the natural language for:

| Lorentzian question | Typical object |
|---|---|
| Causality | Commutators and lightcones |
| Real-time response | Retarded and advanced correlators |
| Scattering-like limits | Regge and lightcone limits |
| Thermalization and chaos | Out-of-time-order correlators |
| Holography | Bulk causal propagation and boundary correlators |
| Collider physics | Energy flux and averaged null energy |

The same CFT data often controls both sides. The dimensions, spins, symmetry representations, and OPE coefficients that appear in Euclidean correlation functions also organize Lorentzian observables. But the continuation is not the same as replacing $\tau$ by $it$ everywhere and closing your eyes. Singularities, branch cuts, and operator orderings matter.

## Setup and conventions

Unless stated otherwise, Euclidean coordinates are written

$$
x_E=(\tau,\mathbf x),
\qquad
x_E^2=\tau^2+\mathbf x^2.
$$

Lorentzian coordinates are written

$$
x_L=(t,\mathbf x),
\qquad
x_L^2=t^2-\mathbf x^2.
$$

The Euclidean rotation convention used on this page is

$$
\tau=it+\epsilon
$$

for the Wightman function in which the operator at $(t,\mathbf x)$ is placed to the left of the operator at the origin. Equivalently, the denominator becomes

$$
x_E^2
\longrightarrow
\mathbf x^2-(t-i\epsilon)^2.
$$

Different conventions for Wick rotation move signs between $t$, $\epsilon$, and the definition of Fourier transforms. What is invariant is the analytic prescription: the small imaginary part specifies how the Lorentzian points avoid the singularities of the Euclidean correlator.

:::caution[Do not drop the prescription]
The formal replacement $\tau=it$ is not a complete Lorentzian correlator. It misses the operator ordering. The $i\epsilon$ prescription is part of the definition of the Lorentzian distribution.
:::

For scalar primaries, this page uses the Euclidean normalization

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle_E
=
\frac{\delta_{ij}}{(x_E^2)^{\Delta_i}}
$$

when an orthonormal basis is chosen. Non-scalar operators require tensor structures and spin-dependent reflection rules.

## Euclidean CFT

Euclidean CFT is often the cleanest starting point because the conformal group acts on a positive-definite space. In $d$ Euclidean dimensions, the local conformal transformations are generated by translations, rotations, dilatations, and special conformal transformations. For $d>2$ the connected conformal group is locally $SO(d+1,1)$.

The basic observables are Euclidean correlation functions,

$$
G_n(x_1,\ldots,x_n)
=
\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle_E.
$$

At separated points, conformal symmetry strongly constrains these functions. For scalar primaries, two- and three-point functions take the form

$$
\langle \mathcal O_i(x_1)\mathcal O_j(x_2)\rangle_E
=
\frac{\delta_{ij}}{(x_{12}^2)^{\Delta_i}},
$$

and

$$
\langle \mathcal O_i(x_1)\mathcal O_j(x_2)\mathcal O_k(x_3)\rangle_E
=
\frac{\lambda_{ijk}}
{(x_{12}^2)^{(\Delta_i+\Delta_j-\Delta_k)/2}
 (x_{23}^2)^{(\Delta_j+\Delta_k-\Delta_i)/2}
 (x_{13}^2)^{(\Delta_i+\Delta_k-\Delta_j)/2}}.
$$

The freedom begins at four points. For four identical scalar primaries $\phi$,

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle_E
=
\frac{g(u,v)}{(x_{12}^2x_{34}^2)^{\Delta_\phi}},
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

Here $u$ and $v$ are Euclidean cross-ratios. The conformal bootstrap usually begins by expanding $g(u,v)$ in the OPE channel and demanding that different expansions agree. The Euclidean theory is therefore the home of the cleanest version of crossing symmetry.

## Lorentzian CFT

Lorentzian CFT has real time. Operator order matters. For two local operators, one can consider Wightman functions,

$$
\langle 0|\mathcal O_1(x_1)\mathcal O_2(x_2)|0\rangle,
$$

time-ordered functions,

$$
\langle 0|T\{\mathcal O_1(x_1)\mathcal O_2(x_2)\}|0\rangle,
$$

retarded functions,

$$
G_R(x)
=
i\theta(t)\langle 0|[\mathcal O(t,\mathbf x),\mathcal O(0)]|0\rangle,
$$

and out-of-time-order functions. These are not the same distribution.

In Lorentzian signature, the connected conformal group is locally $SO(d,2)$, and causal structure becomes part of the story. Points can be spacelike, timelike, or null separated:

$$
x_L^2<0,
\qquad
x_L^2>0,
\qquad
x_L^2=0.
$$

A local Lorentzian QFT obeys microcausality: bosonic local operators commute at spacelike separation,

$$
[\mathcal O_1(x),\mathcal O_2(0)]=0,
\qquad
x_L^2<0,
$$

with the obvious graded modification for fermionic operators. This statement has no literal Euclidean version because Euclidean space has no lightcone. It is recovered from the analytic structure and the reconstruction of the Lorentzian theory.

## Wick rotation and reconstruction

For many path-integral computations, Euclidean correlators are obtained by the formal rotation

$$
t=-i\tau.
$$

This is immensely useful, but it is not an axiom saying that every Euclidean formula is automatically a Lorentzian quantum field theory. The safe logic is:

$$
\text{Lorentzian unitary QFT}
\longrightarrow
\text{Euclidean reflection-positive Schwinger functions}
\longrightarrow
\text{Lorentzian reconstruction}.
$$

The reverse arrow requires conditions. In broad terms, Euclidean correlators must obey:

| Condition | Physical role |
|---|---|
| Euclidean invariance | Rotations and translations before continuation. |
| Symmetry and locality properties | Permutation behavior of spacelike-separated insertions. |
| Reflection positivity | Positive-norm Hilbert space after reconstruction. |
| Regularity and growth conditions | Existence of distributions and Hamiltonian evolution. |
| Clustering | A unique vacuum rather than unrelated distant sectors. |

For CFT practice, the most visible condition is reflection positivity. If it fails, Euclidean crossing equations may still make sense, but the Lorentzian theory is not a standard unitary CFT. This is why nonunitary minimal models, logarithmic theories, ghosts, and gauge-fixed correlators must be handled with care.

## Radial quantization and the cylinder

Euclidean CFT has a special quantization adapted to scale symmetry: **radial quantization**. Write

$$
r=|x|,
\qquad
\tau_{\mathrm{cyl}}=\log r,
\qquad
x=r n,
\qquad
n\in S^{d-1}.
$$

Then flat Euclidean space minus the origin is conformal to the cylinder:

$$
ds_E^2=dr^2+r^2d\Omega_{d-1}^2
=r^2\left(d\tau_{\mathrm{cyl}}^2+d\Omega_{d-1}^2\right).
$$

Because a CFT is insensitive to Weyl rescalings up to anomalies and operator factors, this identifies radial evolution on $\mathbb R^d$ with time evolution on

$$
\mathbb R_{\tau_{\mathrm{cyl}}}\times S^{d-1}.
$$

The generator of translations in $\tau_{\mathrm{cyl}}$ is the dilatation operator $D$. A primary operator at the origin creates a state on the sphere,

$$
|\mathcal O\rangle=\mathcal O(0)|0\rangle,
$$

and the cylinder energy is its scaling dimension:

$$
H_{\mathrm{cyl}}|\mathcal O\rangle=\Delta_\mathcal O|\mathcal O\rangle.
$$

Descendants have energies shifted by integers because derivatives raise the dimension:

$$
P_\mu|\mathcal O\rangle
\quad\text{has}\quad
\Delta_\mathcal O+1.
$$

This is one of the reasons CFT feels more spectral than ordinary QFT. The operator spectrum becomes a discrete energy spectrum on the cylinder when the theory is compact and unitary.

## Lorentzian cylinder and causal diamonds

The Lorentzian version of the cylinder is

$$
\mathbb R_t\times S^{d-1},
\qquad
ds^2=dt^2-d\Omega_{d-1}^2.
$$

It is related to the conformal compactification of Minkowski space. In this picture, the cylinder time generator is again tied to dilatations and conformal transformations in flat space, but the interpretation is now causal. Light rays move at $45^\circ$ on the cylinder, and finite regions of Minkowski space map to causal diamonds.

This cylinder viewpoint is especially useful for:

| Topic | Why the cylinder helps |
|---|---|
| State–operator correspondence | Local operators become states on $S^{d-1}$. |
| Thermal CFT | Thermal states live naturally on $S^{d-1}\times S^1$ or $S^{d-1}\times\mathbb R$. |
| Holography | Global AdS has boundary $\mathbb R\times S^{d-1}$. |
| Causality constraints | Commutators and energy flux have clean geometric meaning. |
| Finite-volume spectra | Scaling dimensions become measurable energies. |

The Euclidean cylinder is excellent for constructing the Hilbert space. The Lorentzian cylinder is excellent for interpreting its dynamics.

## Correlators and operator ordering

The simplest place where ordering matters is the scalar two-point function. Start from

$$
G_E(\tau,\mathbf x)
=
\frac{C}{(\tau^2+\mathbf x^2)^\Delta}.
$$

The Wightman function with the first operator infinitesimally earlier in Euclidean time is

$$
G^+(t,\mathbf x)
=
\frac{C}{\left(\mathbf x^2-(t-i\epsilon)^2\right)^\Delta}.
$$

The reversed Wightman function is

$$
G^-(t,\mathbf x)
=
\frac{C}{\left(\mathbf x^2-(t+i\epsilon)^2\right)^\Delta}.
$$

The time-ordered correlator is assembled from them:

$$
G_T(t,\mathbf x)
=
\theta(t)G^+(t,\mathbf x)+\theta(-t)G^-(t,\mathbf x).
$$

For spacelike separation, the two Wightman functions agree after analytic continuation because the operators commute. For timelike separation, they can differ by phases or discontinuities across branch cuts. Those discontinuities are not errors; they are the Lorentzian physics.

:::note[Euclidean equality can hide Lorentzian choices]
A Euclidean four-point function is a single-valued function in a Euclidean domain. Its Lorentzian continuations can land on different sheets depending on how the insertion times are ordered. This is why Lorentzian bootstrap arguments often discuss analytic continuation around branch points.
:::

## What the bootstrap usually uses

The standard numerical bootstrap is usually formulated in Euclidean signature. For identical scalars, one expands the Euclidean four-point function using the OPE and conformal blocks:

$$
g(u,v)
=
\sum_{\mathcal O}\lambda_{\phi\phi\mathcal O}^2G_{\Delta,\ell}(u,v).
$$

Crossing symmetry compares this to the expansion with $x_1$ and $x_3$ exchanged. In a unitary theory the coefficients satisfy

$$
\lambda_{\phi\phi\mathcal O}^2\ge0,
$$

which turns crossing into a positivity problem.

This Euclidean formulation is powerful, but it is not the whole CFT. Lorentzian ideas enter in several important ways:

| Lorentzian input | Bootstrap consequence |
|---|---|
| Causality | Analyticity and commutator constraints. |
| Lightcone OPE | Large-spin expansions and double-twist operators. |
| Reflection positivity | Positive conformal-block coefficients. |
| Energy conditions | Bounds involving the stress tensor and spinning operators. |
| Regge behavior | Constraints on chaos, high-energy behavior, and holographic CFTs. |
| Thermal causality | Constraints on finite-temperature correlators. |

A healthy working attitude is therefore:

$$
\text{Use Euclidean crossing for clean constraints; use Lorentzian continuation for causal meaning.}
$$

## Compact, noncompact, and gauge-theory caveats

Not every scale-invariant-looking theory gives a compact unitary CFT with a discrete spectrum on the cylinder.

A **compact** CFT has a discrete spectrum of local operators with finite degeneracies below any fixed dimension. This is the natural setting for many bootstrap arguments and for ordinary statistical critical points.

A **noncompact** CFT can have continuous spectra or non-normalizable sectors. Free noncompact bosons in two dimensions are the classic warning sign: derivatives of the scalar are well-behaved local operators, while the scalar itself has infrared subtleties.

Gauge theories add another layer. Gauge-dependent fields are not physical local operators. Gauge-invariant local operators, Wilson lines, disorder operators, and charged sectors may have different Euclidean and Lorentzian interpretations. A gauge-fixed Euclidean path integral can contain fields with indefinite metric; reflection positivity is expected only after the physical Hilbert space is correctly identified.

## Common pitfalls

**Pitfall 1: Thinking Euclidean time is physical time.** Euclidean time is a computational and structural coordinate. Physical causality lives in Lorentzian signature.

**Pitfall 2: Dropping $i\epsilon$.** The $i\epsilon$ prescription specifies the Lorentzian operator ordering. Without it, a correlator near the lightcone is undefined or ambiguous.

**Pitfall 3: Treating crossing as the same thing as causality.** Crossing is OPE associativity. Causality is a Lorentzian commutator statement. They are related through analyticity, but they are not identical.

**Pitfall 4: Assuming every Euclidean solution is unitary.** Crossing equations can have nonunitary solutions. Reflection positivity is the extra condition that gives positive norm.

**Pitfall 5: Forgetting branch cuts.** Lorentzian four-point functions live on analytic continuations of Euclidean functions. Moving operators around in time can move the correlator to another sheet.

**Pitfall 6: Confusing the Euclidean cylinder with a thermal circle.** Radial quantization maps $\mathbb R^d\setminus\{0\}$ to $\mathbb R\times S^{d-1}$. Thermal physics compactifies Euclidean time and imposes periodic or antiperiodic conditions. The geometries look similar but answer different questions.

## Relations to other pages

This page is the bridge between the first conceptual chapter and the technical core of the volume.

- [Unitarity and Reflection Positivity](/cft-bootstrap/what-is-a-cft/unitarity-and-reflection-positivity/) explains the positivity condition that makes Euclidean correlators reconstruct a positive Hilbert space.
- [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/) develops radial time, radial ordering, and operator-state maps.
- [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/) explains why primary operators create energy eigenstates on the cylinder.
- [Correlation Functions](/cft-bootstrap/correlation-functions/) develops the Euclidean constraints on two-, three-, and four-point functions.
- [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) uses Euclidean OPE associativity as the basis for bootstrap equations.
- [Thermal and Lorentzian CFT](/cft-bootstrap/thermal-lorentzian-cft/) studies real-time response, lightcone limits, chaos, thermal states, and Lorentzian analytic structure in more detail.

## Research status

The Euclidean–Lorentzian relation is conceptually settled in the axiomatic and constructive framework under appropriate assumptions. For ordinary unitary CFT practice, the working toolkit is standard: Euclidean correlators, reflection positivity, radial quantization, analytic continuation, and Lorentzian $i\epsilon$ prescriptions.

What remains active is not the basic bridge but what can be extracted from it. Modern Lorentzian CFT methods use causality, analyticity, Regge limits, lightcone limits, modular flow, energy correlators, and inversion formulae to derive constraints that are difficult to see from Euclidean crossing alone. Holographic CFTs make this especially vivid: the same boundary correlator knows both Euclidean OPE data and bulk causal propagation.

A fair status summary is:

$$
\text{Euclidean CFT is the stable grammar; Lorentzian CFT is where many of the sharpest modern arguments live.}
$$

## Exercises

### Exercise 1: Wick-rotate the scalar two-point function

Start with the Euclidean scalar two-point function

$$
G_E(\tau,\mathbf x)=\frac{1}{(\tau^2+\mathbf x^2)^\Delta}.
$$

Using $\tau=it+\epsilon$, derive the Wightman prescription for $G^+(t,\mathbf x)$.

<details>
<summary><strong>Solution</strong></summary>

Substitute

$$
\tau=it+\epsilon=i(t-i\epsilon).
$$

Then

$$
\tau^2+
\mathbf x^2
=
-(t-i\epsilon)^2+\mathbf x^2.
$$

Therefore

$$
G^+(t,\mathbf x)
=
\frac{1}{\left(\mathbf x^2-(t-i\epsilon)^2\right)^\Delta}.
$$

The small imaginary part is not optional. It tells us which side of the lightcone singularity the distribution occupies.

</details>

### Exercise 2: Cylinder energy from scaling dimension

Let $\mathcal O$ be a scalar primary of dimension $\Delta$. Under $x\mapsto \lambda x$, it obeys

$$
\mathcal O(0)|0\rangle\mapsto \lambda^{-\Delta}\mathcal O(0)|0\rangle
$$

in the corresponding state representation. Explain why the cylinder energy of $|\mathcal O\rangle$ is $\Delta$.

<details>
<summary><strong>Solution</strong></summary>

Radial quantization uses

$$
\tau_{\mathrm{cyl}}=\log r.
$$

A scale transformation $r\mapsto \lambda r$ is therefore a translation

$$
\tau_{\mathrm{cyl}}\mapsto \tau_{\mathrm{cyl}}+\log\lambda.
$$

The generator of translations in $\tau_{\mathrm{cyl}}$ is the cylinder Hamiltonian $H_{\mathrm{cyl}}$, which is identified with the dilatation generator. If $\mathcal O$ has scaling dimension $\Delta$, then the state created by $\mathcal O$ is an eigenstate of this generator with eigenvalue $\Delta$:

$$
H_{\mathrm{cyl}}|\mathcal O\rangle=\Delta|\mathcal O\rangle.
$$

</details>

### Exercise 3: Why crossing is not the same as causality

Explain in one paragraph why Euclidean crossing symmetry does not by itself state that operators commute at spacelike separation.

<details>
<summary><strong>Solution</strong></summary>

Euclidean crossing symmetry says that different Euclidean OPE decompositions of the same correlation function agree in overlapping domains. It is a statement about associativity of the local operator algebra. Causality is a Lorentzian statement about commutators vanishing outside the lightcone:

$$
[\mathcal O_1(x),\mathcal O_2(0)]=0,
\qquad
x_L^2<0.
$$

The two are related because a reflection-positive Euclidean CFT can be analytically continued to Lorentzian signature, where locality and analyticity imply commutator properties. But crossing alone, especially without positivity and reconstruction assumptions, is not literally the spacelike commutator equation.

</details>

### Exercise 4: Euclidean radius and radial ordering

Consider two Euclidean insertions $\mathcal O_1(x_1)$ and $\mathcal O_2(x_2)$ with $|x_1|>|x_2|$. Which one is later in radial time, and what does radial ordering do?

<details>
<summary><strong>Solution</strong></summary>

Radial time is

$$
\tau_{\mathrm{cyl}}=\log r.
$$

Therefore $|x_1|>|x_2|$ implies

$$
\tau_{{\rm cyl},1}>\tau_{{\rm cyl},2}.
$$

The insertion at $x_1$ is later in radial time. Radial ordering places operators with larger radius to the left, just as ordinary time ordering places later-time operators to the left.

</details>

### Exercise 5: Reflection positivity and Lorentzian positivity

Why is reflection positivity the Euclidean condition relevant for a positive Lorentzian Hilbert space?

<details>
<summary><strong>Solution</strong></summary>

In Euclidean signature, states can be prepared by inserting operators on one side of a reflection plane, say $\tau>0$. The bra is obtained by reflecting those insertions to $\tau<0$ and applying the appropriate anti-linear operation. Reflection positivity says that the resulting Euclidean correlator is nonnegative:

$$
\langle \Theta F\,F\rangle_E\ge0.
$$

This is the Euclidean version of

$$
\langle \Psi|\Psi\rangle\ge0.
$$

Without it, analytic continuation may produce a vector space with an indefinite inner product rather than a physical Hilbert space.

</details>

## References

- K. Osterwalder and R. Schrader, “Axioms for Euclidean Green's Functions,” *Communications in Mathematical Physics* **31** (1973). Foundational reference for reflection positivity and Euclidean reconstruction.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. Standard reference for two-dimensional Euclidean CFT, radial quantization, cylinder maps, and operator formalism.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, Springer, 2017. Pedagogical modern treatment of Euclidean CFT, unitarity, radial quantization, OPE, and bootstrap.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982. Clear account of Euclidean CFT, reflection positivity, radial quantization, OPE, conformal blocks, and numerical bootstrap.
- T. Hartman, *Lectures on Quantum Gravity and Black Holes*, 2015. Useful for Lorentzian cylinder intuition, conformal compactification, and holographic correlators.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405. Review of Euclidean crossing, conformal blocks, and numerical bootstrap.
- D. M. Hofman and J. Maldacena, “Conformal Collider Physics: Energy and Charge Correlations,” *Journal of High Energy Physics* **05** (2008), arXiv:0803.1467. Classic Lorentzian CFT application to energy flux and positivity.
- S. Caron-Huot, “Analyticity in Spin in Conformal Theories,” *Journal of High Energy Physics* **09** (2017), arXiv:1703.00278. Landmark Lorentzian inversion formula paper.

## Version history

- **2026-06-27:** Initial polished draft explaining Euclidean versus Lorentzian CFT, Wick rotation, reflection positivity, radial quantization, cylinder evolution, Wightman and time-ordered prescriptions, bootstrap usage, caveats, pitfalls, and exercises.
