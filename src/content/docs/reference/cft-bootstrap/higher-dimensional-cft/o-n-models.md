---
title: "O(N) Models"
description: "The Wilson–Fisher conformal field theories with O(N) global symmetry, including operator sectors, critical exponents, large-N limits, and bootstrap structure."
sidebar:
  label: "O(N) Models"
  order: 11
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Zinn-Justin; Rychkov lectures; Poland, Rychkov, and Vichi 2019; large-N and O(N) bootstrap literature."
topics:
  - O(N) models
  - Wilson-Fisher fixed points
  - vector models
  - critical phenomena
  - conformal bootstrap
canonicalTopics:
  - o-n-models
  - vector-model-cfts
  - wilson-fisher-fixed-points
researchStatus:
  established:
    - "The critical O(N) models in three dimensions are unitary CFTs describing vector order-parameter universality classes, with N=1 giving the Ising class, N=2 the XY class, and N=3 the Heisenberg class."
  active:
    - "Precision CFT data, symmetry enhancement, boundary criticality, large-N higher-spin breaking, cubic anisotropy, gauge-theory cousins, and noninteger N remain active research topics."
---

## Summary

The **$O(N)$ models** are conformal field theories describing critical points with an $N$-component real order parameter

$$
\phi_i(x),
\qquad i=1,\ldots,N,
$$

transforming in the vector representation of $O(N)$. Their Landau–Ginzburg description is

$$
S=\int d^d x\left[\frac12(\partial\phi_i)^2+\frac12 r\phi_i\phi_i+\frac{g}{4!}(\phi_i\phi_i)^2\right].
$$

At the Wilson–Fisher fixed point, this theory becomes an interacting CFT. Important special cases are:

| $N$ | Universality class | Typical physical language |
|---:|---|---|
| $0$ | self-avoiding walk | polymers, via analytic continuation |
| $1$ | Ising | scalar order parameter, $\mathbb Z_2$ symmetry |
| $2$ | XY | superfluid transition, planar magnets |
| $3$ | Heisenberg | isotropic magnets |
| $\infty$ | large-$N$ vector model | solvable saddle and approximate higher-spin symmetry |

The $O(N)$ models are central examples of higher-dimensional CFT because they connect almost every major method: renormalization group, $\varepsilon$ expansion, large-$N$ expansion, Monte Carlo simulation, conformal bootstrap, and experiments on critical systems.

Their CFT data are organized by $O(N)$ representation sectors. The vector primary $\phi_i$, singlet scalar $s$, traceless symmetric tensor $t_{ij}$, antisymmetric conserved current $J_\mu^{ij}$, and stress tensor $T_{\mu\nu}$ are the first landmarks.

## Prerequisites

Read [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/), [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/), [Conserved Currents](/cft-bootstrap/higher-dimensional-cft/conserved-currents/), [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/), and [Unitarity Bounds in d Dimensions](/cft-bootstrap/higher-dimensional-cft/unitarity-bounds-in-d-dimensions/) first.

You should also know the basics of global symmetry representations and the idea that an OPE decomposes into irreducible representations of the global symmetry group.

## Core idea

The Ising CFT has one real order parameter. The $O(N)$ models replace it by an $N$-component vector order parameter. The microscopic spin may be a vector

$$
\mathbf s_i\in \mathbb R^N,
$$

and the continuum order parameter becomes a primary operator

$$
\phi_i(x).
$$

At criticality, the long-distance theory is a CFT with global $O(N)$ symmetry. The continuum slogan is

$$
\text{critical vector spin system}
\quad\longrightarrow\quad
\text{unitary }O(N)\text{-symmetric CFT}.
$$

The symmetry organizes the operator algebra. The product of two vector operators decomposes as

$$
\mathbf N\otimes\mathbf N
=\mathbf S\oplus\mathbf T\oplus\mathbf A,
$$

where $\mathbf S$ is the singlet, $\mathbf T$ is the traceless symmetric representation, and $\mathbf A$ is the antisymmetric representation. In indices,

$$
\phi_i\times\phi_j
\sim
\delta_{ij}(\text{singlets})
+\left(\text{traceless symmetric}\right)_{ij}
+\left(\text{antisymmetric}\right)_{ij}.
$$

This sector decomposition is the backbone of the $O(N)$ bootstrap.

## Setup and conventions

The Euclidean Landau–Ginzburg action is

$$
S=\int d^d x\left[\frac12\partial_\mu\phi_i\partial^\mu\phi_i+\frac12 r\phi_i\phi_i+\frac{g}{4!}(\phi_i\phi_i)^2\right].
$$

Repeated $O(N)$ indices are summed. The global symmetry acts as

$$
\phi_i\mapsto R_i{}^j\phi_j,
\qquad
R\in O(N).
$$

The Wilson–Fisher fixed point is reached by tuning $r$ to criticality. In $d=4-\varepsilon$, the fixed-point coupling is perturbative:

$$
g_*\sim O(\varepsilon).
$$

In $d=3$, the fixed point is strongly interacting for small $N$, but it can be studied nonperturbatively using the bootstrap and numerically using lattice methods.

The CFT normalization convention for scalar two-point functions is

$$
\langle \phi_i(x)\phi_j(0)\rangle
=\frac{\delta_{ij}}{|x|^{2\Delta_\phi}}.
$$

Other operators are similarly normalized when quoting OPE coefficients.

## Special values of N

The $O(N)$ family contains several famous universality classes.

### N equals 1

For $N=1$,

$$
O(1)=\mathbb Z_2,
$$

and the model is the Ising universality class. The vector operator $\phi_i$ becomes the Ising spin operator $\sigma$, and the leading singlet scalar becomes the energy operator $\epsilon$.

### N equals 2

For $N=2$, the model has $O(2)$ symmetry. Its connected part is $SO(2)\simeq U(1)$, and it describes the XY universality class. Physical realizations include planar magnets and the superfluid transition of helium-4, up to the usual caveats about microscopic details and experimental corrections.

The $O(2)$ model is also important because vortices and topological defects are natural in its ordered phase. In two dimensions, related physics leads to the Berezinskii–Kosterlitz–Thouless transition, but the three-dimensional $O(2)$ Wilson–Fisher CFT is a different fixed point.

### N equals 3

For $N=3$, the model describes the Heisenberg universality class of isotropic magnets. The order parameter is a three-component vector. The global symmetry is $O(3)$, with conserved currents

$$
J_\mu^{ij}=-J_\mu^{ji}.
$$

### N equals 0

The formal $N\to0$ continuation describes self-avoiding walks and polymers. This is not a theory with a literal negative or zero number of spin components. It is an analytic continuation of the $O(N)$ loop expansion.

### Large N

At $N=\infty$, the vector model becomes solvable by saddle-point methods. It has an infinite tower of approximately conserved higher-spin currents at large but finite $N$, making it a bridge to higher-spin holography.

## Operator sectors

The most important $O(N)$ sectors in the $\phi_i\times\phi_j$ OPE are:

| Sector | Representation | Typical leading operator | Spin/parity information |
|---|---|---|---|
| Singlet $S$ | invariant under $O(N)$ | $s\sim \phi_i\phi_i$ | scalar relevant thermal operator |
| Traceless symmetric $T$ | symmetric tensor with trace removed | $t_{ij}\sim\phi_i\phi_j-\delta_{ij}\phi^2/N$ | scalar or higher-spin operators |
| Antisymmetric $A$ | antisymmetric tensor | $J_\mu^{ij}$ | conserved current, spin one |

The OPE can be written schematically as

$$
\phi_i\times\phi_j
=\delta_{ij}\,S+T_{(ij)}+A_{[ij]}.
$$

More explicitly, the singlet part contains

$$
\mathbf 1,\quad s,\quad T_{\mu\nu},\quad s',\ldots,
$$

the traceless symmetric part contains

$$
t_{ij},\quad \text{higher-spin traceless tensors},\ldots,
$$

and the antisymmetric part contains

$$
J_\mu^{ij},\quad \text{other antisymmetric operators},\ldots .
$$

This decomposition is essential in mixed-correlator bootstrap, where each representation sector has its own crossing equation and positivity condition.

## Leading CFT data

The leading vector scalar is $\phi_i$, with dimension

$$
\Delta_\phi=\frac{d-2+\eta}{2}.
$$

The leading singlet scalar $s$ is the thermal operator. Its dimension determines the correlation-length exponent:

$$
\nu=\frac1{d-\Delta_s}.
$$

The conserved current has fixed dimension

$$
\Delta_J=d-1,
$$

and belongs to the antisymmetric representation. The stress tensor has fixed dimension

$$
\Delta_T=d.
$$

The leading irrelevant singlet $s'$ gives the correction-to-scaling exponent

$$
\omega=\Delta_{s'}-d.
$$

For $N=1$, these formulas reduce to the Ising notation:

$$
\phi\to\sigma,
\qquad
s\to\epsilon.
$$

For $N\ge2$, the conserved currents are new protected operators that are absent in the $N=1$ Ising model as continuous currents.

## Critical exponents

Many critical exponents are CFT scaling dimensions in disguise. The two basic RG eigenvalues are

$$
y_t=d-\Delta_s,
\qquad
 y_h=d-\Delta_\phi.
$$

Then

$$
\nu=\frac1{y_t},
$$

and

$$
\eta=2\Delta_\phi-(d-2).
$$

The magnetization exponent is

$$
\beta=\nu\Delta_\phi,
$$

and the susceptibility exponent is

$$
\gamma=\nu(2-\eta).
$$

The critical-isotherm exponent is

$$
\delta=\frac{d-\Delta_\phi}{\Delta_\phi}.
$$

These formulas apply to the usual vector order parameter. More complicated observables, such as tensor anisotropies, crossover perturbations, or monopole-like operators in related gauge theories, require additional operator dimensions.

## Large-N solution

The large-$N$ limit is obtained by introducing an auxiliary singlet field $\sigma$ or $\lambda$ enforcing the constraint on $\phi_i\phi_i$. A common Hubbard–Stratonovich rewriting is schematically

$$
\frac{g}{4!}(\phi_i\phi_i)^2
\quad\longrightarrow\quad
\lambda\phi_i\phi_i-\frac{1}{g}\lambda^2.
$$

Integrating out the $N$ vector components produces an effective action proportional to $N$:

$$
S_{\rm eff}[\lambda]\sim N\,\operatorname{Tr}\log(-\partial^2+\lambda)+\cdots .
$$

At $N=\infty$, the saddle point becomes exact. The leading vector dimension is close to its free value,

$$
\Delta_\phi=\frac{d-2}{2}+O\left(\frac1N\right),
$$

while the leading singlet scalar has

$$
\Delta_s=2+O\left(\frac1N\right)
$$

in $2<d<4$.

The theory also has an infinite tower of higher-spin currents with dimensions

$$
\Delta_\ell=\ell+d-2+O\left(\frac1N\right).
$$

At $N=\infty$, these currents are conserved. At finite $N$, they acquire anomalous dimensions. This is the CFT signature of weakly broken higher-spin symmetry.

## Epsilon expansion

Near four dimensions, the quartic coupling is weakly relevant. In

$$
d=4-\varepsilon,
$$

the beta function has a Wilson–Fisher fixed point at

$$
g_*\sim \frac{\varepsilon}{N+8}
$$

up to convention-dependent normalization. Critical exponents can be expanded in powers of $\varepsilon$.

For example, at leading order,

$$
\eta=O(\varepsilon^2),
$$

while

$$
\nu=\frac12+\frac{N+2}{4(N+8)}\varepsilon+O(\varepsilon^2).
$$

Setting $\varepsilon=1$ gives estimates in $d=3$. High-order resummation improves the numerical predictions.

The epsilon expansion and the large-$N$ expansion are complementary:

$$
\varepsilon\text{ expansion: controlled near }d=4,
$$

$$
1/N\text{ expansion: controlled at large }N.
$$

The three-dimensional bootstrap works directly in $d=3$ and is especially powerful at small $N$.

## Bootstrap equations

The basic four-point function is

$$
\langle \phi_i\phi_j\phi_k\phi_l\rangle.
$$

Crossing decomposes this correlator into singlet, traceless symmetric, and antisymmetric sectors. Schematically,

$$
\sum_{\mathcal O\in S} \lambda_{S,\mathcal O}^2 G_{\Delta,\ell}^{S}
+\sum_{\mathcal O\in T} \lambda_{T,\mathcal O}^2 G_{\Delta,\ell}^{T}
+\sum_{\mathcal O\in A} \lambda_{A,\mathcal O}^2 G_{\Delta,\ell}^{A}=0,
$$

where the actual crossing equation is vector-valued because the tensor structures from $O(N)$ index contractions are linearly independent.

Important exact inputs include:

$$
\Delta_J=d-1,
\qquad
\Delta_T=d,
$$

and the representation sectors in which $J$ and $T$ appear. The current $J_\mu^{ij}$ is in the antisymmetric sector, while $T_{\mu\nu}$ is a singlet.

Mixed-correlator bootstrap adds correlators involving $s$ or $t_{ij}$, such as

$$
\langle \phi\phi ss\rangle,
\qquad
\langle ssss\rangle,
\qquad
\langle \phi\phi tt\rangle.
$$

These systems can isolate islands for small values of $N$.

## Cubic anisotropy and stability

The $O(N)$ fixed point can be perturbed by anisotropies that reduce the symmetry. A common example is cubic anisotropy, which preserves the hypercubic symmetry of an $N$-component lattice spin but not full $O(N)$:

$$
\sum_i \phi_i^4.
$$

Whether such an anisotropy is relevant or irrelevant at the $O(N)$ fixed point determines whether the $O(N)$ critical behavior is stable in microscopic systems with only cubic symmetry.

In CFT language, the question is whether a scalar operator in the appropriate spin-four representation of $O(N)$ has

$$
\Delta<d
$$

or

$$
\Delta>d.
$$

This is an example of how a practical universality question becomes a question about the CFT spectrum.

For $N=3$, the cubic-anisotropy stability problem is subtle and has been studied by RG, Monte Carlo, and bootstrap methods. It is a good warning that global symmetry assumptions in a bootstrap setup are physical assumptions, not harmless decoration.

## Relation to experiments and simulations

The $O(N)$ models describe many critical systems:

| Model | Typical systems | Main order parameter |
|---|---|---|
| $O(1)$ | liquid-gas, uniaxial magnets | scalar |
| $O(2)$ | superfluids, XY magnets | planar vector |
| $O(3)$ | isotropic magnets | three-vector |
| $O(0)$ | polymers | formal loop/SAW observable |

Universality means that critical exponents and CFT dimensions are shared across systems with the same dimension, symmetry, locality, and relevant perturbation structure. It does not mean that every amplitude or microscopic observable is universal.

A lattice vector spin $s_i^a$ has an infrared expansion

$$
s_i^a\sim A_\phi\phi^a(x)+A_{\phi'}\phi'^a(x)+\cdots,
$$

with nonuniversal coefficients. Lattice energy-like operators similarly overlap with the leading singlet scalar $s$ and subleading singlets.

This operator-mixing viewpoint is essential when extracting CFT data from Monte Carlo or experiments.

## Beyond the basic O(N) fixed point

The phrase “$O(N)$ model” can refer to several related but distinct theories:

| Theory | Meaning |
|---|---|
| critical $O(N)$ vector model | Wilson–Fisher CFT with vector order parameter |
| free $O(N)$ vector model | $N$ free scalars, with exact higher-spin currents |
| nonlinear sigma model | constrained field $n_i n_i=1$, useful in ordered phases and near two dimensions |
| cubic model | $O(N)$ broken to a discrete subgroup by anisotropy |
| Gross–Neveu–Yukawa cousins | fermions coupled to order parameters, different universality classes |
| gauge-theory cousins | CP models, QED-like critical points, deconfined criticality candidates |

This page is about the ordinary critical $O(N)$ vector CFT unless stated otherwise.

## Common pitfalls

**Do not treat $N$ as only an integer.** Many computations analytically continue in $N$, and $N=0$ describes self-avoiding walks. Physical spin systems usually have integer $N$, but the equations often make sense more broadly.

**Do not confuse $O(2)$ Wilson–Fisher criticality with the 2D BKT transition.** They are different fixed points in different dimensions with different mechanisms.

**Do not forget representation sectors.** The $\phi_i\times\phi_j$ OPE is not a single scalar equation; it decomposes into singlet, traceless symmetric, and antisymmetric sectors.

**Do not call the conserved current a scalar.** The $O(N)$ current is a spin-one operator in the antisymmetric representation with $\Delta=d-1$.

**Do not assume all microscopic anisotropies are irrelevant.** Stability of the $O(N)$ fixed point depends on the dimensions of anisotropy operators.

**Do not confuse the large-$N$ vector model with matrix large-$N$ gauge theory.** Their counting, spectra, and holographic interpretations differ.

**Do not use one set of exponents for every $N$.** $N=1$, $N=2$, $N=3$, and large $N$ describe different CFTs with different CFT data.

## Relations to other pages

This page follows [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/) and places it inside the broader $O(N)$ family. It also relies on [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/) for factorization and higher-spin comments.

It prepares [Gauge-Theory CFTs](/cft-bootstrap/higher-dimensional-cft/gauge-theory-cfts/) because many modern critical points are compared to or distinguished from ordinary $O(N)$ vector models. It also prepares later pages in [CFT in Statistical Physics and Matter](/cft-bootstrap/cft-in-statistical-physics-matter/) and [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/).

For RG background, see the Renormalization, RG, and EFT volume. For higher-spin and holographic directions, see [Holographic CFT](/cft-bootstrap/holographic-cft/) and [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/).

## Research status

The Wilson–Fisher $O(N)$ fixed points are established central examples of higher-dimensional CFTs. Their leading critical exponents and many low-lying operator dimensions are known from a combination of perturbative RG, large-$N$ methods, Monte Carlo, experiments, and conformal bootstrap.

Active research includes precision islands for various $N$, current and stress-tensor data, cubic anisotropy and stability, boundary critical phenomena, extraordinary transitions, large-$N$ higher-spin breaking, noninteger $N$, conformal defects, and relations to gauge-theory and deconfined critical points.

## Exercises

### Exercise 1

Decompose the product of two $O(N)$ vectors into irreducible representations.

<details><summary><strong>Solution</strong></summary>

The product $\phi_i\phi_j$ decomposes into trace, symmetric traceless, and antisymmetric parts:

$$
\phi_i\phi_j
=\frac{\delta_{ij}}{N}(\phi_k\phi_k)
+\left(\phi_i\phi_j-\frac{\delta_{ij}}{N}\phi_k\phi_k\right)
+\frac12(\phi_i\phi_j-\phi_j\phi_i).
$$

For commuting scalar fields at the same point the last schematic expression needs regularization and operator definitions, but representation-theoretically the tensor product is

$$
\mathbf N\otimes\mathbf N=\mathbf S\oplus\mathbf T\oplus\mathbf A.
$$

The singlet is the trace, $\mathbf T$ is symmetric traceless, and $\mathbf A$ is antisymmetric.

</details>

### Exercise 2

Show that the $O(N)$ current has dimension $d-1$.

<details><summary><strong>Solution</strong></summary>

The $O(N)$ current is a conserved spin-one primary:

$$
\partial^\mu J_\mu^{ij}=0.
$$

In a unitary CFT, a spin-one primary obeys the unitarity bound

$$
\Delta\ge d-1.
$$

Conservation occurs at saturation, so

$$
\Delta_J=d-1.
$$

The antisymmetric indices $ij$ reflect the adjoint representation of $O(N)$.

</details>

### Exercise 3

For $N=1$, explain how the $O(N)$ notation reduces to Ising notation.

<details><summary><strong>Solution</strong></summary>

For $N=1$,

$$
O(1)=\mathbb Z_2.
$$

The vector operator $\phi_i$ has only one component and becomes the odd Ising spin operator:

$$
\phi\to\sigma.
$$

The leading singlet scalar $s\sim\phi_i\phi_i$ becomes the even Ising energy operator:

$$
s\to\epsilon.
$$

There is no continuous $O(1)$ current because $O(1)$ is discrete. Thus the antisymmetric current sector disappears.

</details>

### Exercise 4

Use the dimension of the leading singlet scalar $s$ to write the correlation-length exponent.

<details><summary><strong>Solution</strong></summary>

The coupling to the leading singlet scalar is the thermal perturbation:

$$
S\to S+t\int d^dx\,s(x).
$$

The RG eigenvalue of $t$ is

$$
y_t=d-\Delta_s.
$$

The correlation-length exponent is the inverse of this eigenvalue:

$$
\nu=\frac1{d-\Delta_s}.
$$

</details>

### Exercise 5

Why is the large-$N$ vector model not the same as a matrix large-$N$ gauge theory?

<details><summary><strong>Solution</strong></summary>

In the vector model, fields carry one index:

$$
\phi_i,\qquad i=1,\ldots,N.
$$

The number of degrees of freedom scales like $N$, and typically

$$
C_T\sim N.
$$

In a matrix gauge theory, fields can carry two indices, and the number of degrees of freedom often scales like $N^2$:

$$
C_T\sim N^2.
$$

The diagrammatics, operator organization, and holographic interpretations differ. Vector models are naturally connected to higher-spin theories, while sparse matrix large-$N$ CFTs can have Einstein-like gravity duals.

</details>

## References

- K. G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” *Physics Reports* **12** (1974).
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, fifth edition, Oxford University Press, 2021.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2016.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- S. El-Showk, M. F. Paulos, D. Poland, S. Rychkov, D. Simmons-Duffin, and A. Vichi, “Solving the 3D Ising Model with the Conformal Bootstrap II,” *Journal of Statistical Physics* **157** (2014), for the $N=1$ benchmark.
- A. M. Polyakov, *Gauge Fields and Strings*, Harwood, 1987.
- I. R. Klebanov and A. M. Polyakov, “AdS Dual of the Critical O(N) Vector Model,” *Physics Letters B* **550** (2002).

## Version history

- 2026-07-01: First polished draft. Added $O(N)$ Wilson–Fisher setup, special values of $N$, representation-sector decomposition, critical exponent dictionary, large-$N$ and epsilon-expansion summaries, bootstrap structure, anisotropy discussion, exercises, and references.
