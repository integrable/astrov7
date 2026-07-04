---
title: "Examples of CFTs"
description: "Surveys the main families of conformal field theories, from free fields and two-dimensional minimal models to Wilson–Fisher fixed points, gauge-theory CFTs, generalized free fields, supersymmetric CFTs, and holographic large-N theories."
sidebar:
  label: "Examples of CFTs"
  order: 7
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Zinn-Justin 2021; Rychkov 2017; Poland–Rychkov–Vichi 2019; Rychkov–Su 2024"
topics:
  - examples of CFTs
  - free CFTs
  - Wilson-Fisher fixed points
  - Ising CFT
  - O(N) models
  - minimal models
  - WZW models
  - generalized free fields
  - supersymmetric CFTs
  - holographic CFTs
canonicalTopics:
  - examples-of-cfts
  - free-conformal-field-theories
  - interacting-conformal-field-theories
  - statistical-cfts
  - gauge-theory-cfts
  - holographic-cfts
researchStatus:
  established:
    - "Free fields, two-dimensional minimal models, WZW models, Wilson–Fisher-type critical points, and many supersymmetric fixed points provide standard benchmark examples of CFTs."
    - "The conformal bootstrap treats all these examples through their CFT data rather than through a preferred microscopic Lagrangian."
  active:
    - "Many candidate CFTs in three-dimensional gauge theory, deconfined criticality, nonsupersymmetric conformal windows, and holographic large-N dynamics remain active research targets."
---

## Summary

CFTs are not one species of theory. They form a large ecosystem. Some are free. Some are interacting. Some come from statistical mechanics. Some arise as gauge-theory fixed points. Some are exactly solved in two dimensions. Some are known only through protected data, dualities, numerics, or consistency constraints.

A useful first map is:

| Family | Typical example | Main lesson |
|---|---|---|
| Free CFTs | Massless scalar, fermion, Maxwell field in special dimensions | Symmetry and operator organization can be seen explicitly. |
| Statistical CFTs | Ising, $O(N)$, Potts, percolation | CFTs describe critical points and universality classes. |
| Two-dimensional exact CFTs | Minimal models, compact boson, WZW models | Infinite-dimensional symmetry can solve theories exactly. |
| Gauge-theory CFTs | Banks–Zaks fixed points, QED$_3$ candidates, supersymmetric gauge theories | A CFT need not be built from gauge-invariant elementary fields. |
| Generalized free fields | A scalar with Wick-like correlators and arbitrary $\Delta$ | Crossing can be easy while locality and stress tensors are subtle. |
| Holographic large-N CFTs | Large-N strongly coupled CFTs with AdS duals | Sparse spectra and factorization can produce emergent gravity. |

The right question is not “which Lagrangian defines the CFT?” The more intrinsic question is:

$$
\text{What is the spectrum of local operators and what are their OPE coefficients?}
$$

That is why [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/) comes before the model zoo. Examples are not just illustrations. They are calibration points for the whole subject.

:::note[How to use this page]
Read this page as a field guide. The goal is not to master every example immediately. The goal is to recognize the major families, know what each one teaches, and know which caveats travel with it.
:::

## Prerequisites

You should know [CFTs as RG Fixed Points](/cft-bootstrap/what-is-a-cft/cfts-as-rg-fixed-points/), [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/), [Local Operators as Observables](/cft-bootstrap/what-is-a-cft/local-operators-as-observables/), and [Euclidean and Lorentzian CFT](/cft-bootstrap/what-is-a-cft/euclidean-and-lorentzian-cft/).

For the examples from statistical mechanics, it helps to know the Wilsonian picture of fixed points and relevant perturbations. For two-dimensional examples, complex coordinates and the stress tensor will be developed later in [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/).

## Core idea

A CFT example is useful when it teaches at least one of the following lessons:

| Lesson | Example family |
|---|---|
| How conformal symmetry acts on explicit fields | Free scalar and free fermion CFTs. |
| How universality works at a critical point | Ising and $O(N)$ Wilson–Fisher CFTs. |
| How a CFT can be solved without a Lagrangian | Two-dimensional minimal models. |
| How extended symmetry changes the game | WZW models, supersymmetric CFTs, rational CFTs. |
| How gauge redundancy disappears from physical data | Gauge-theory CFTs. |
| How large-N factorization reorganizes dynamics | Vector models, matrix large-N CFTs, holographic CFTs. |
| How crossing can be satisfied in a controlled toy model | Generalized free fields. |

A Lagrangian can be a convenient UV description, an IR effective description, or no description at all. The CFT itself is the fixed-point theory: the operator algebra, its correlation functions, and the consistency conditions they obey.

## Setup and conventions

Unless stated otherwise, dimensions and correlators use the conventions of [Conventions and Notation](/cft-bootstrap/conventions/). In $d$ CFT dimensions, scalar-primary two-point functions are normalized as

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{\delta_{ij}}{|x|^{2\Delta_i}}
$$

in Euclidean signature after choosing an orthonormal basis of scalar primaries.

For two-dimensional CFTs, we use complex coordinates

$$
z=x^1+ix^2,
\qquad
\bar z=x^1-ix^2,
$$

and write scaling dimension and spin as

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

Some examples below are unitary CFTs. Some are nonunitary but still extremely useful. Some are candidate CFTs whose existence or detailed data depend on assumptions, dimension, matter content, or limits. The point of this page is to sort the examples by what they teach, not to pretend they all have the same status.

## Free scalar CFT

The massless real scalar field in $d>2$ is the simplest local CFT with a scalar primary. Its Euclidean action is

$$
S=\frac12\int d^d x\,\partial_\mu\phi\,\partial^\mu\phi,
$$

where in Euclidean signature indices are contracted with $\delta_{\mu\nu}$. The equation of motion is

$$
\partial^2\phi=0.
$$

The scalar has scaling dimension

$$
\Delta_\phi=\frac{d-2}{2},
$$

and its two-point function is proportional to

$$
\langle\phi(x)\phi(0)\rangle
\propto
\frac{1}{|x|^{d-2}}.
$$

The free scalar is important because it shows the basic conformal multiplet structure explicitly. The field $\phi$ saturates the scalar unitarity bound in $d>2$:

$$
\Delta_\phi=\frac{d-2}{2}.
$$

The null descendant is the equation of motion,

$$
\partial^2\phi=0.
$$

Composite operators such as

$$
\phi^2,
\qquad
\phi\partial_\mu\phi,
\qquad
\phi\partial_{(\mu_1}\cdots\partial_{\mu_\ell)}\phi-\text{traces}
$$

organize into primary operators and descendants. Wick's theorem computes all correlation functions.

### The stress-tensor caveat

The canonical stress tensor of the free scalar is not automatically traceless. One uses the improved stress tensor

$$
T_{\mu\nu}
=
\partial_\mu\phi\partial_\nu\phi
-\frac12\delta_{\mu\nu}(\partial\phi)^2
+\xi\left(\delta_{\mu\nu}\partial^2-\partial_\mu\partial_\nu\right)\phi^2,
$$

with

$$
\xi=\frac{d-2}{4(d-1)}.
$$

On the equation of motion, this stress tensor is traceless. This is one of the cleanest examples of improvement.

### The two-dimensional caveat

In $d=2$, the uncompactified free scalar field itself has a logarithmic two-point function rather than an ordinary power-law two-point function:

$$
\langle\phi(z,\bar z)\phi(0)\rangle\sim -\log |z|^2.
$$

The local primary operators are better taken to be derivatives such as $\partial\phi$ and vertex operators such as

$$
V_\alpha(z,\bar z)=e^{i\alpha\phi(z,\bar z)},
$$

with details depending on compactification and normalization. This is a good reminder that “free scalar CFT” means slightly different things in $d=2$ and $d>2$.

## Free fermion CFT

A massless free fermion is another basic CFT. In $d$ dimensions, a free Dirac fermion has scaling dimension

$$
\Delta_\psi=\frac{d-1}{2}.
$$

Its two-point function has the schematic form

$$
\langle\psi(x)\bar\psi(0)\rangle
\propto
\frac{\gamma_\mu x^\mu}{|x|^d}
$$

in Euclidean conventions.

Free fermions teach three lessons.

First, CFT operators can carry spinor indices. Their conformal transformations include both the local scale factor and the spin representation of the local rotation.

Second, unitarity bounds for spinning operators are not cosmetic. The free Dirac equation shortens the fermion multiplet, just as the free scalar equation shortens the scalar multiplet.

Third, fermion bilinears generate important bosonic operators:

$$
\bar\psi\psi,
\qquad
\bar\psi\gamma_\mu\psi,
\qquad
T_{\mu\nu}.
$$

These operators are the bridge from free fermion theory to Gross–Neveu, Gross–Neveu–Yukawa, QED$_3$, and many condensed-matter CFTs.

## Maxwell theory and free gauge fields

Maxwell theory is conformal in four spacetime dimensions. The action is

$$
S=\frac14\int d^4x\,F_{\mu\nu}F^{\mu\nu},
$$

in Euclidean signature, with the obvious Lorentzian sign changes. In $d=4$, the gauge-invariant field strength has dimension

$$
\Delta_F=2.
$$

The stress tensor can be chosen traceless:

$$
T^\mu_{\ \mu}=0.
$$

The dimension $d=4$ is special. In general $d$, the Maxwell action is scale invariant only when the coupling has the appropriate dimension, and the theory is conformal as an ordinary local gauge theory in the familiar Maxwell sense only in four dimensions.

This example is pedagogically useful because it separates **fields** from **observables**. The gauge potential $A_\mu$ is not gauge-invariant. The gauge-invariant local operators are built from $F_{\mu\nu}$ and its derivatives, while line operators such as Wilson lines are extended observables.

In other dimensions, conformal free gauge systems exist for suitable $p$-form gauge fields. A free $p$-form field strength can be conformal in dimension

$$
d=2(p+1),
$$

which includes the ordinary Maxwell field with $p=1$ in $d=4$.

## Generalized free fields

A generalized free scalar field is a formal scalar operator $\phi$ with dimension $\Delta_\phi$ and two-point function

$$
\langle\phi(x)\phi(0)\rangle
=
\frac{1}{|x|^{2\Delta_\phi}},
$$

whose higher-point functions are defined by Wick-like factorization. For example,

$$
\begin{aligned}
\langle\phi_1\phi_2\phi_3\phi_4\rangle
={}&
\langle\phi_1\phi_2\rangle\langle\phi_3\phi_4\rangle
+\langle\phi_1\phi_3\rangle\langle\phi_2\phi_4\rangle\\
&+\langle\phi_1\phi_4\rangle\langle\phi_2\phi_3\rangle.
\end{aligned}
$$

This satisfies crossing symmetry almost by construction. The exchanged operators include double-trace-like primaries with approximate dimensions

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell,
\qquad
n=0,1,2,\ldots.
$$

Generalized free fields are indispensable in bootstrap and holography because they model the leading large-N behavior of single-trace operators. But they come with a warning: a generalized free field by itself is usually not a complete local CFT with a normal stress tensor. It is a consistent sector-like structure, not automatically a full theory of local quantum fields.

That makes it the perfect toy model: friendly enough to compute, dangerous enough to teach humility.

## Wilson–Fisher and Ising-type CFTs

The Wilson–Fisher fixed point is the prototype of an interacting CFT reached from a relevant deformation of a Gaussian theory. For a single real scalar with $\mathbb Z_2$ symmetry, one begins with the Landau–Ginzburg action

$$
S=\int d^d x\left[
\frac12(\partial\phi)^2+\frac12 r\phi^2+\frac{\lambda}{4!}\phi^4
\right].
$$

At criticality, the correlation length diverges. In $d=4-\epsilon$, the quartic interaction is weakly relevant and flows to an interacting fixed point. In $d=3$, the same universality class describes the critical three-dimensional Ising model.

The 3D Ising CFT has two especially important low-dimension scalar primaries:

$$
\sigma
\qquad\text{and}\qquad
\epsilon.
$$

They correspond roughly to the spin/order-parameter operator and the energy operator. Modern bootstrap computations determine their dimensions with spectacular precision. A recent stress-tensor bootstrap gives approximately

$$
\Delta_\sigma=0.518148806,
\qquad
\Delta_\epsilon=1.41262528.
$$

The exact decimals are less important here than the lesson: an interacting non-supersymmetric CFT can be solved numerically from symmetry, crossing, and unitarity to precision that competes with or surpasses traditional methods.

### The O(N) vector models

The $O(N)$ Wilson–Fisher CFTs generalize the Ising model. Their order parameter is an $N$-component vector

$$
\phi_i,
\qquad i=1,\ldots,N,
$$

with symmetry

$$
O(N).
$$

Important cases include:

| Model | Physical interpretation |
|---|---|
| $N=1$ | Ising universality class. |
| $N=2$ | XY universality class, superfluid transition, easy-plane magnets. |
| $N=3$ | Heisenberg universality class. |
| Large $N$ | Controlled $1/N$ expansion and analytic checks. |

The $O(N)$ models teach how global symmetry organizes CFT data. Four-point functions decompose into singlet, traceless-symmetric, and antisymmetric sectors. This is the first place many readers meet mixed representation crossing equations.

## Two-dimensional minimal models

Two-dimensional CFT is special because local conformal transformations are infinite-dimensional. The stress tensor generates the Virasoro algebra,

$$
[L_m,L_n]
=(m-n)L_{m+n}+\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

Minimal models are rational CFTs with finitely many Virasoro primary operators. The unitary minimal models have central charges

$$
c=1-\frac{6}{m(m+1)},
\qquad
m=3,4,5,\ldots.
$$

The first few are famous:

| Model | $m$ | Central charge | Comments |
|---|---:|---:|---|
| Ising | $3$ | $1/2$ | Primaries $\mathbf 1$, $\sigma$, $\epsilon$. |
| Tricritical Ising | $4$ | $7/10$ | Critical point with an additional relevant tuning. |
| Three-state Potts | related rational theory | $4/5$ | Requires extended symmetry and non-diagonal modular invariant in the usual presentation. |

The critical Ising minimal model has primaries

$$
\mathbf 1,
\qquad
\sigma,
\qquad
\epsilon,
$$

with

$$
(h,\bar h)_\sigma=\left(\frac{1}{16},\frac{1}{16}\right),
\qquad
(h,\bar h)_\epsilon=\left(\frac12,\frac12\right).
$$

Thus

$$
\Delta_\sigma=\frac18,
\qquad
\Delta_\epsilon=1.
$$

Minimal models teach the idealized bootstrap dream: under the right conditions, symmetry, null states, modular constraints, and crossing determine a theory exactly.

## Compact bosons and torus CFTs

The compact free boson is a two-dimensional CFT in which

$$
\phi\sim\phi+2\pi R.
$$

It has central charge

$$
c=1.
$$

Its local operators include momentum and winding vertex operators. Their dimensions depend on the radius $R$. Changing $R$ moves along a continuous family of CFTs: a **conformal manifold**.

This example teaches several lessons that do not appear in the simplest minimal models:

- CFTs can come in continuous families.
- Exactly marginal operators can move one along a conformal manifold.
- Dualities can identify apparently different parameter values.
- Momentum and winding are natural in compact target spaces.
- Modular invariance strongly constrains the spectrum.

The compact boson is also the doorway to bosonization, Luttinger liquids, string worldsheet theory, and many condensed-matter applications.

## WZW models and current algebra CFTs

Wess–Zumino–Witten models are two-dimensional CFTs with affine Lie algebra symmetry. For a compact simple group $G$ and level $k$, the holomorphic currents obey an OPE of the schematic form

$$
J^a(z)J^b(0)
\sim
\frac{k\delta^{ab}}{z^2}
+
\frac{if^{abc}J^c(0)}{z}.
$$

The central charge is

$$
c=\frac{k\,\dim G}{k+h^\vee},
$$

where $h^\vee$ is the dual Coxeter number.

WZW models are essential because they show how internal symmetry can be promoted to an infinite-dimensional chiral algebra. They appear in nonabelian bosonization, spin chains, string theory, rational CFT, boundary CFT, and topological field theory.

They also provide clean examples where the word “operator algebra” is not metaphorical. Fusion rules, modular transformations, characters, and current algebra representations become explicit calculational tools.

## Liouville theory

Liouville theory is a two-dimensional CFT with a continuous spectrum. Its action is often written schematically as

$$
S_L=\frac{1}{4\pi}\int d^2x\sqrt g\left[
(\partial\phi)^2+Q R\phi+4\pi\mu e^{2b\phi}
\right].
$$

Its central charge is

$$
c=1+6Q^2,
\qquad
Q=b+b^{-1}.
$$

Liouville theory is important because it is exactly solvable but not rational. It appears in two-dimensional quantum gravity, noncritical string theory, and the modern theory of Virasoro conformal blocks.

Minimal models teach finite spectra. Liouville theory teaches continuous spectra. Both are exact, and they illuminate different parts of the CFT landscape.

## Gauge-theory CFTs

Many CFTs are not naturally described in terms of gauge-invariant elementary fields. A gauge theory can flow to a conformal fixed point, but the physical local operators are gauge-invariant composites, monopole operators, line defects, or protected operators.

### Banks–Zaks fixed points

In four-dimensional nonabelian gauge theory with a suitable number of fermion flavors, the beta function can have a weakly coupled infrared fixed point. This is the Banks–Zaks mechanism. The fixed point is perturbative when the one-loop coefficient is small and the two-loop term balances it.

This family is important because it provides controllable interacting CFTs in four dimensions without supersymmetry, at least in a regime where perturbation theory is reliable.

### Three-dimensional gauge-theory candidates

In three dimensions, examples and candidates include QED$_3$, QCD$_3$, Chern–Simons–matter theories, and gauge theories proposed to describe deconfined critical points. Their status can depend delicately on the number of matter fields, global symmetries, monopole operators, and possible symmetry enhancement.

These theories are especially active because they connect CFT, duality, condensed matter, topology, and numerical bootstrap.

### Gauge-invariant operator lesson

In a gauge-theory CFT, the basic data are not dimensions of gauge-dependent fields. They are dimensions and OPE coefficients of physical operators such as

$$
\bar\psi\psi,
\qquad
F_{\mu\nu}F^{\mu\nu},
\qquad
\operatorname{tr}\phi^k,
\qquad
\text{monopole operators},
\qquad
T_{\mu\nu}.
$$

This is one of the reasons the bootstrap language is so natural: it never needed a gauge-dependent field basis in the first place.

## Supersymmetric CFTs

Supersymmetric CFTs have superconformal symmetry. They are often more tractable than nonsupersymmetric CFTs because protected sectors, indices, localization, chiral rings, and dualities can compute exact data.

Important examples include:

| Dimension | Examples | Why they matter |
|---|---|---|
| 2D | $\mathcal N=(2,2)$ minimal models, sigma-model fixed points | Chiral rings, mirror symmetry, elliptic genera. |
| 3D | $\mathcal N=2$ and extended supersymmetric Chern–Simons–matter theories | Localization, $F$-maximization, dualities. |
| 4D | $\mathcal N=1$ SCFTs, $\mathcal N=2$ SCFTs, $\mathcal N=4$ super Yang–Mills | Protected operator data, conformal manifolds, AdS/CFT. |
| 6D | $\mathcal N=(2,0)$ theories | Strongly interacting theories without ordinary Lagrangians. |

The most famous example is four-dimensional $\mathcal N=4$ super Yang–Mills theory. It has an exactly marginal gauge coupling, a large amount of supersymmetry, integrability in special limits, and a holographic dual at large $N$ and strong coupling.

Supersymmetric examples teach a crucial lesson: some CFTs are not merely hard to describe by a Lagrangian; some may have no conventional Lagrangian description at all, while still having sharply defined operator data.

## Large-N vector models

The $O(N)$ vector model at large $N$ is a controlled interacting CFT. One studies fields

$$
\phi_i,
\qquad i=1,\ldots,N,
$$

and expands in powers of

$$
\frac1N.
$$

At leading large $N$, many quantities simplify. The singlet sector develops approximate factorization, and anomalous dimensions can be computed systematically.

Large-N vector models are important for three reasons.

First, they provide analytic control over interacting CFTs.

Second, they interpolate between statistical CFTs and higher-spin holography.

Third, they give benchmark data for numerical and analytic bootstrap methods.

## Holographic large-N CFTs

A holographic CFT is a CFT whose dynamics can be equivalently described, in a suitable limit, by a gravitational theory in anti-de Sitter space. The slogan is

$$
\text{CFT in }d\text{ dimensions}
\quad\longleftrightarrow\quad
\text{gravity-like theory in AdS}_{d+1}.
$$

Not every large-N CFT is holographic in the Einstein-gravity sense. A CFT with a weakly curved local gravitational dual should have special features, including:

- large-N factorization,
- a sparse spectrum of low-dimension single-trace higher-spin operators,
- a stress tensor with large central charge,
- approximate locality in AdS,
- OPE data organized like bulk interactions.

Generalized free fields describe the leading disconnected correlators of single-trace operators. Corrections in $1/N$ encode bulk interactions.

Holographic CFTs are not first examples for beginners, but they are conceptually central. They turn CFT data into a nonperturbative definition of quantum gravity in asymptotically AdS spacetime.

## Nonunitary and logarithmic examples

Not all important CFTs are unitary.

Examples include:

| Example | Where it appears | Caveat |
|---|---|---|
| Yang–Lee edge singularity | Critical phenomena with imaginary magnetic field | Nonunitary minimal model in 2D; nonunitary CFTs in higher dimensions. |
| Percolation CFTs | Statistical cluster models | Often logarithmic; $c=0$ behavior in 2D. |
| Self-avoiding walk limit | $O(N)$ model as $N\to0$ | Analytic continuation in $N$, not an ordinary positive-norm Hilbert space. |
| Logarithmic CFTs | Disordered systems, polymers, percolation | Dilatation operator may have Jordan blocks. |

These examples should not be dismissed as pathological. They are physically and mathematically important. But one must not apply unitary bootstrap positivity to them without modification.

## Defect and boundary CFTs

A boundary CFT or defect CFT is not an ordinary CFT on all of flat space. It is a conformal theory with a boundary or defect preserving a subgroup of the full conformal group.

Examples include:

$$
\text{CFT on a half-space},
\qquad
\text{line defects},
\qquad
\text{surface defects},
\qquad
\text{interfaces between CFTs}.
$$

These systems have their own operator data: bulk operators, defect operators, bulk-to-defect OPE coefficients, and defect OPE coefficients. They are not the main examples in this opening chapter, but they become important later because real systems often have boundaries, impurities, interfaces, or extended probes.

## A comparison table

Here is a compact comparison of common examples.

| CFT | Dimension | Unitary? | Solvability | Main data |
|---|---:|---|---|---|
| Free scalar | $d>2$ | Yes | Exact by Wick theorem | $\Delta_\phi=(d-2)/2$ and composite spectrum. |
| Free fermion | general $d$ with spinors | Yes | Exact by Wick theorem | $\Delta_\psi=(d-1)/2$ and bilinear currents. |
| Maxwell | $d=4$ | Yes after gauge quantization care | Exact | Gauge-invariant operators built from $F_{\mu\nu}$. |
| 2D Ising minimal model | $d=2$ | Yes | Exact | $c=1/2$, three Virasoro primaries. |
| 3D Ising | $d=3$ | Yes | Numerical, perturbative, Monte Carlo | $\Delta_\sigma$, $\Delta_\epsilon$, OPE data. |
| $O(N)$ Wilson–Fisher | $d=3$ or $4-\epsilon$ | Yes for integer $N\ge1$ | Numerical, $\epsilon$ expansion, large $N$ | Operator sectors by $O(N)$ representation. |
| Compact boson | $d=2$ | Yes | Exact | Radius-dependent dimensions and $c=1$. |
| WZW model | $d=2$ | Often yes for compact $G$ and positive integer $k$ | Exact rational data | Affine Lie algebra representations and fusion. |
| Generalized free field | formal any $d$ | Reflection-positive if bounds hold | Exact correlators | Double-trace-like spectrum, no automatic stress tensor. |
| Banks–Zaks | $d=4$ | Yes in perturbative window | Perturbative | Gauge-invariant composite operators. |
| Supersymmetric CFTs | various | Often yes | Protected sectors exact | Chiral rings, indices, central charges. |
| Holographic CFTs | various | Yes in standard examples | Large-N expansion | Single-trace spectrum and $1/N$ OPE data. |
| Yang–Lee | various | No | Exact in 2D, perturbative/numerical otherwise | Nonunitary operator data. |

## How examples support the bootstrap

The conformal bootstrap needs examples for several reasons.

First, examples calibrate normalization. Free fields tell us how two-point functions, OPE coefficients, conserved currents, and stress tensors should behave.

Second, examples provide targets. The 3D Ising and $O(N)$ CFTs produce islands, kinks, and allowed regions that bootstrap methods can test.

Third, examples show what assumptions do. If one imposes unitarity and a $\mathbb Z_2$ symmetry, the 3D Ising CFT sits in one landscape. If one removes unitarity, Yang–Lee-type theories become visible. If one adds supersymmetry, protected relations reshape the constraints.

Fourth, examples expose danger. Generalized free fields satisfy crossing but may not be complete local CFTs. Gauge theories have no gauge-invariant elementary matter fields. Logarithmic CFTs can violate diagonalizability. Holographic CFTs demand sparse spectra, not just large central charge.

The bootstrap is powerful because it does not require all examples to be formulated in the same microscopic language. It asks the same questions of all of them:

$$
\text{What operators exist?}
\qquad
\text{What are their dimensions and spins?}
\qquad
\text{What OPE coefficients are allowed?}
\qquad
\text{Do the correlators cross consistently?}
$$

## Common pitfalls

**Pitfall 1: Thinking “CFT” means “free massless theory.”** Free theories are CFTs, but most interesting CFTs are interacting fixed points.

**Pitfall 2: Thinking every CFT must have a Lagrangian.** Many CFTs are known intrinsically through operator data, symmetry, duality, or consistency. A Lagrangian is useful, not mandatory.

**Pitfall 3: Treating gauge-dependent fields as CFT operators.** In gauge-theory CFTs, physical local operators must be gauge-invariant or properly defined disorder operators.

**Pitfall 4: Applying unitary bounds to nonunitary examples.** Yang–Lee, percolation, polymers, and logarithmic CFTs require modified assumptions.

**Pitfall 5: Forgetting dimension-specific conformality.** Maxwell theory is conformal in $d=4$, not as an ordinary Maxwell CFT in every dimension. Free scalar subtleties also differ between $d=2$ and $d>2$.

**Pitfall 6: Treating generalized free fields as complete CFTs.** They are crossing-symmetric and often reflection-positive, but a full local CFT also needs a stress tensor and a complete operator algebra with locality properties.

**Pitfall 7: Confusing a universality class with a microscopic model.** The 3D Ising CFT is not the lattice Ising Hamiltonian. It is the universal long-distance fixed point reached by many microscopic systems with the same relevant symmetry data.

## Relations to other pages

- [CFTs as RG Fixed Points](/cft-bootstrap/what-is-a-cft/cfts-as-rg-fixed-points/) explains why statistical examples flow to CFTs at criticality.
- [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/) explains the intrinsic data used to compare all examples.
- [Scale Invariance versus Conformal Invariance](/cft-bootstrap/what-is-a-cft/scale-invariance-versus-conformal-invariance/) explains why Maxwell theory and other examples require dimension-sensitive care.
- [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) develops the free boson, free fermion, and complex-coordinate formalism.
- [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/) develops the stress-tensor algebra behind minimal models.
- [Minimal Models and Rational CFT](/cft-bootstrap/minimal-models-rational-cft/) develops the Ising, tricritical Ising, Potts, and rational examples.
- [Current Algebras and WZW Models](/cft-bootstrap/current-algebras-wzw/) develops affine Lie algebra examples.
- [Higher-Dimensional CFT](/cft-bootstrap/higher-dimensional-cft/) develops free fields, generalized free fields, Wilson–Fisher theories, and large-N CFTs beyond two dimensions.
- [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) explains how examples such as the 3D Ising CFT become precision targets.
- [Holographic CFT](/cft-bootstrap/holographic-cft/) explains large-N sparse-spectrum CFTs and their AdS interpretation.

## Research status

The basic examples on this page are well established: free CFTs, 2D minimal models, WZW models, Wilson–Fisher fixed points, and many supersymmetric CFTs are standard parts of the subject.

The active frontier lies in sharpening the map. Current work asks which nonsupersymmetric gauge theories are conformal, which candidate deconfined critical points are genuine CFTs, how to classify nonunitary and logarithmic CFTs, how to characterize holographic CFTs intrinsically, and how to extract more CFT data from numerical and analytic bootstrap methods.

There is also a practical frontier: producing benchmark data accurate enough that different methods can be compared. The 3D Ising CFT is the flagship example, but $O(N)$ models, Gross–Neveu–Yukawa models, QED$_3$, boundary CFTs, and supersymmetric CFTs are increasingly part of the same precision ecosystem.

## Exercises

### Exercise 1: Dimension of the free scalar

In $d>2$, use dimensional analysis of

$$
S=\frac12\int d^d x\,(\partial\phi)^2
$$

to derive the scaling dimension of $\phi$.

<details>
<summary><strong>Solution</strong></summary>

The action is dimensionless in natural units. Since

$$
[d^d x]=-d,
\qquad
[\partial]=1,
$$

the kinetic term has dimension

$$
2+2[\phi].
$$

The Lagrangian density must have dimension $d$, so

$$
2+2[\phi]=d.
$$

Therefore

$$
\Delta_\phi=[\phi]=\frac{d-2}{2}.
$$

This matches the scalar unitarity bound in $d>2$, and the shortening condition is the free equation of motion $\partial^2\phi=0$.

</details>

### Exercise 2: Why Maxwell theory is special in four dimensions

Use dimensional analysis to show why the Maxwell action

$$
S=\frac14\int d^d x\,F_{\mu\nu}F^{\mu\nu}
$$

is naturally conformal for the ordinary one-form gauge field in $d=4$.

<details>
<summary><strong>Solution</strong></summary>

For an ordinary gauge potential $A_\mu$, the field strength is

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

The Maxwell kinetic term fixes

$$
[A_\mu]=\frac{d-2}{2},
\qquad
[F_{\mu\nu}]=\frac d2.
$$

For the gauge-invariant field strength to behave like the familiar conformal primary of dimension $2$, one needs

$$
\frac d2=2,
$$

so

$$
d=4.
$$

Equivalently, the stress tensor of the ordinary Maxwell theory is traceless only in four dimensions. This is why Maxwell theory is the standard free gauge-field CFT in $d=4$.

</details>

### Exercise 3: Relevance of the quartic interaction

For a free scalar in $d$ dimensions, compute the engineering dimension of the coupling $\lambda$ in

$$
\int d^d x\,\lambda\phi^4.
$$

What happens near $d=4$?

<details>
<summary><strong>Solution</strong></summary>

The free scalar has

$$
[\phi]=\frac{d-2}{2}.
$$

Therefore

$$
[\phi^4]=2(d-2).
$$

The Lagrangian density must have dimension $d$, so

$$
[\lambda]+2(d-2)=d.
$$

Thus

$$
[\lambda]=4-d.
$$

Near

$$
d=4-\epsilon,
$$

we have

$$
[\lambda]=\epsilon.
$$

The quartic interaction is weakly relevant for small positive $\epsilon$, leading to the Wilson–Fisher fixed point.

</details>

### Exercise 4: Generalized free double-trace dimensions

A generalized free scalar $\phi$ has dimension $\Delta_\phi$. Explain why the schematic composite operators

$$
\phi\partial_{\mu_1}\cdots\partial_{\mu_\ell}(\partial^2)^n\phi
$$

suggest dimensions

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell.
$$

<details>
<summary><strong>Solution</strong></summary>

Each factor of $\phi$ contributes dimension $\Delta_\phi$, so two fields contribute

$$
2\Delta_\phi.
$$

Each ordinary derivative contributes one unit of scaling dimension. The spin-$\ell$ traceless derivative structure contributes $\ell$, while each $\partial^2$ contributes two. Therefore the schematic dimension is

$$
\Delta_{n,\ell}=2\Delta_\phi+\ell+2n.
$$

In generalized free theory these are the dimensions of double-trace-like primary operators after subtracting descendants and traces appropriately.

</details>

### Exercise 5: Identify the kind of CFT

For each description, name a likely CFT family.

1. A theory with $c=1/2$ and three Virasoro primaries.
2. A $d=3$ critical point with a $\mathbb Z_2$-odd scalar $\sigma$ and a $\mathbb Z_2$-even scalar $\epsilon$.
3. A theory whose four-point functions factorize into pairings but whose scalar dimension is arbitrary.
4. A two-dimensional theory with affine Lie algebra currents $J^a(z)$.
5. A large-N theory with sparse low-spin single-trace data and an AdS dual.

<details>
<summary><strong>Solution</strong></summary>

1. The two-dimensional Ising minimal model.
2. The three-dimensional Ising CFT.
3. A generalized free field.
4. A WZW model or current-algebra CFT.
5. A holographic large-N CFT.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. Standard reference for two-dimensional CFT, minimal models, free bosons, free fermions, WZW models, modular invariance, and rational CFT.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, 5th ed., Oxford University Press, 2021. Detailed treatment of RG fixed points, Wilson–Fisher theory, critical phenomena, and the bridge between QFT and statistical mechanics.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, Springer, 2017. Pedagogical higher-dimensional CFT reference, including free fields, unitarity, conformal data, and bootstrap basics.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982. Useful source for generalized free fields, conformal blocks, and bootstrap examples.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405. Broad review of CFT examples and numerical bootstrap applications, especially 3D Ising and $O(N)$ models.
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” arXiv:2311.15844. Review of recent numerical-bootstrap methods and applications.
- A. B. Zamolodchikov and A. B. Zamolodchikov, “Structure Constants and Conformal Bootstrap in Liouville Field Theory,” *Nuclear Physics B* **477** (1996). Classic reference for exact Liouville structure constants.
- J. L. Cardy, *Scaling and Renormalization in Statistical Physics*, Cambridge University Press, 1996. Compact reference for critical phenomena, scaling, and statistical CFT examples.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, 2nd ed., Cambridge University Press, 2013. Useful source for condensed-matter examples including spin chains, bosonization, WZW models, criticality, and entanglement.

## Version history

- **2026-06-27:** Initial polished draft surveying free CFTs, generalized free fields, Wilson–Fisher and Ising-type theories, two-dimensional minimal models, compact bosons, WZW models, gauge-theory CFTs, supersymmetric CFTs, holographic CFTs, nonunitary/logarithmic examples, boundary and defect examples, bootstrap uses, pitfalls, and exercises.
