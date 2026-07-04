---
title: "Gauge-Theory CFTs"
description: "How conformal field theories with gauge fields are described through gauge-invariant operators, global symmetries, line defects, monopoles, conformal windows, and bootstrap data."
sidebar:
  label: "Gauge-Theory CFTs"
  order: 12
level: Graduate
status: "Polished draft"
source: "Poland, Rychkov, and Vichi 2019; Rychkov and Su 2024; standard conformal window, QED3, Chern–Simons–matter, and gauge-theory bootstrap literature."
topics:
  - gauge-theory CFTs
  - conformal windows
  - QED3
  - Chern-Simons matter
  - monopole operators
canonicalTopics:
  - gauge-theory-cfts
  - conformal-window
  - gauge-invariant-operators
researchStatus:
  established:
    - "Gauge theories can flow to conformal fixed points whose local CFT data are built from gauge-invariant operators, conserved global currents, and the stress tensor."
  active:
    - "Many proposed gauge-theory CFTs, especially in three dimensions and near the edge of conformal windows, remain active targets for bootstrap, lattice, large-N, supersymmetric, and duality-based tests."
---

## Summary

A **gauge-theory CFT** is a conformal fixed point whose useful microscopic description contains gauge fields. The gauge field is not itself a local observable. The CFT data are built from gauge-invariant local operators, line or surface defects, conserved global currents, the stress tensor, and sometimes disorder operators such as monopoles.

Examples include Banks–Zaks fixed points in four dimensions, three-dimensional QED-like theories, Chern–Simons–matter theories, supersymmetric gauge-theory fixed points, and large-$N$ gauge CFTs with holographic duals.

The central conceptual warning is

$$
\text{gauge symmetry is redundancy, not a global symmetry}.
$$

The physical symmetries of a gauge-theory CFT are global symmetries acting on gauge-invariant operators and extended objects. The gauge redundancy is a description used to compute or organize the theory.

Gauge-theory CFTs are difficult because their simplest fields are often not physical operators. They are also important because they provide many of the most interesting strongly coupled CFTs in dimensions greater than two: conformal windows, deconfined criticality candidates, quantum critical gauge theories, supersymmetric fixed points, and holographic large-$N$ theories.

## Prerequisites

Read [Higher-Dimensional CFT](/cft-bootstrap/higher-dimensional-cft/), [Conserved Currents](/cft-bootstrap/higher-dimensional-cft/conserved-currents/), [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/), [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/), and [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/) first.

You should also know the basic QFT distinction between gauge redundancy and global symmetry. The gauge-theory foundations live in the gauge-theory volumes; this page focuses on how gauge theories appear as CFTs and bootstrap targets.

## Core idea

A Lagrangian gauge theory may have fields such as

$$
A_\mu,
\qquad
\psi,
\qquad
\phi,
$$

but a local CFT is organized by gauge-invariant operators. A schematic example is

$$
\operatorname{Tr}F_{\mu\nu}F^{\mu\nu},
\qquad
\bar\psi\psi,
\qquad
\phi^\dagger\phi,
\qquad
\bar\psi\gamma_\mu\psi,
$$

when these expressions are gauge invariant and well defined at the fixed point.

At a conformal fixed point, one does not ask for the elementary gauge-field propagator as the fundamental observable. One asks for CFT data:

$$
\{\Delta_i,\ell_i,\text{global representations},\lambda_{ijk}\}
$$

of gauge-invariant primaries and defects.

The slogan is

$$
\text{gauge theory description}
\quad\longrightarrow\quad
\text{gauge-invariant CFT data}.
$$

This is especially important in strongly coupled theories, where the gauge variables may be a useful UV language but the IR CFT may have emergent symmetries, dual descriptions, or no weakly coupled Lagrangian at all.

## Setup and conventions

A gauge theory has a gauge group $G_{\rm gauge}$ and usually a global symmetry group $G_{\rm global}$. The two play very different roles.

| Structure | Meaning | Acts on |
|---|---|---|
| gauge group $G_{\rm gauge}$ | redundancy of description | non-gauge-invariant variables |
| global symmetry $G_{\rm global}$ | physical symmetry | gauge-invariant local and extended operators |
| one-form symmetry | generalized global symmetry | line operators |
| topological symmetry in 3D | current built from flux | monopole sectors and magnetic charge |

The stress tensor is gauge invariant and has fixed dimension

$$
\Delta_T=d.
$$

Ordinary conserved global currents have fixed dimension

$$
\Delta_J=d-1.
$$

Gauge-invariant scalar operators can be relevant, marginal, or irrelevant. Their dimensions determine which deformations preserve or destroy the fixed point.

This page uses Euclidean CFT language. Lorentzian gauge theories have additional questions about real-time dynamics, confinement, transport, and charged states; those belong to later chapters.

## What makes a gauge theory conformal?

A gauge theory is conformal when its renormalization group flow reaches a fixed point. In perturbation theory, this often means that beta functions vanish:

$$
\beta_g(g_*)=0,
$$

and similarly for Yukawa, scalar, or Chern–Simons-matter couplings.

At such a fixed point, correlation functions of gauge-invariant operators have power-law behavior. For a scalar primary $\mathcal O$,

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=\frac{1}{|x|^{2\Delta_\mathcal O}}
$$

in a unit-normalized basis.

There are several routes to gauge-theory CFTs:

| Route | Typical control parameter | Example |
|---|---|---|
| weakly coupled perturbative fixed point | small beta-function coefficient | Banks–Zaks fixed points |
| large flavor number | $1/N_f$ | QED3 and QCD3-like theories |
| large rank | $1/N$ | planar gauge CFTs, holographic CFTs |
| supersymmetry | protected data and dualities | superconformal gauge theories |
| Chern–Simons level | large $k$ or fixed 't Hooft ratio | Chern–Simons–matter CFTs |
| numerical bootstrap | crossing and unitarity | QED3, deconfined-criticality candidates |

The fixed-point description may be weakly coupled, strongly coupled, or only indirectly defined by consistency conditions.

## Gauge invariance and local operators

Local operators in a gauge theory must be gauge invariant, or more precisely must be genuine operators in the theory under consideration. Examples include traces, bilinears, baryon-like operators, and topological disorder operators.

For a nonabelian gauge field, common gauge-invariant local operators include

$$
\operatorname{Tr}F_{\mu\nu}F^{\mu\nu},
\qquad
\operatorname{Tr}F_{\mu\nu}\widetilde F^{\mu\nu}
$$

in four dimensions, and matter composites such as

$$
\bar\psi_i\psi^j,
\qquad
\phi_i^\dagger\phi^j,
$$

with gauge indices contracted.

Some gauge theories also have baryon-like operators. In an $SU(N_c)$ gauge theory with fundamental fields, a schematic baryon operator is

$$
\epsilon_{a_1\cdots a_{N_c}}\psi^{a_1}\cdots\psi^{a_{N_c}},
$$

with spin, flavor, and statistics treated carefully.

The identity of local operators can depend on the global form of the gauge group. An $SU(N)$ theory and a $PSU(N)=SU(N)/\mathbb Z_N$ theory can share a Lie algebra but differ in their genuine line operators and sometimes in allowed local disorder sectors.

## Monopole and disorder operators

In three-dimensional gauge theories, monopole operators are especially important. A monopole operator is defined by specifying magnetic flux through a small sphere surrounding the insertion:

$$
\int_{S^2} F = 2\pi q
$$

in an abelian normalization. The insertion creates a state on $S^2$ with magnetic flux under the state-operator correspondence.

Monopole operators are local disorder operators. They are not polynomial expressions in the elementary fields, but they are genuine local operators when allowed by the theory. Their scaling dimensions are important CFT data.

In QED3-like theories with $N_f$ charged fermions or bosons, monopole dimensions can be estimated at large $N_f$, constrained by bootstrap, and compared across dual descriptions. They often carry nontrivial quantum numbers under global symmetries because charged matter has zero modes in the monopole background.

The lesson is

$$
\text{local operator} \ne \text{polynomial in Lagrangian fields}.
$$

Gauge-theory CFTs force this lesson early and often.

## Line operators and one-form symmetries

Gauge theories also contain extended operators. The most familiar are Wilson lines,

$$
W_R(C)=\operatorname{Tr}_R\,\mathcal P\exp\left(i\oint_C A\right),
$$

and 't Hooft lines, which impose magnetic singularities along a curve $C$.

In a conformal gauge theory, straight or circular line operators can define conformal defects. Their data include defect operator spectra, displacement operators, and defect OPE coefficients.

Gauge theories may also have higher-form global symmetries. For example, a pure gauge theory can have a center one-form symmetry acting on Wilson lines. The charged objects are lines rather than local operators.

In CFT language, this means that the full theory is not specified only by local operator data. Extended operators and generalized global symmetries are part of the modern description, especially when comparing dual theories.

## Four-dimensional conformal windows

A **conformal window** is a range of matter content for which a gauge theory flows to an interacting conformal fixed point.

For asymptotically free nonabelian gauge theories with sufficiently many massless fermions, the two-loop beta function may have a weakly coupled infrared fixed point. This is the Banks–Zaks mechanism. Schematically,

$$
\beta(g)=-b_0g^3-b_1g^5+\cdots,
$$

and if

$$
b_0>0,
\qquad
b_1<0,
$$

with $b_0$ small, then

$$
g_*^2\sim -\frac{b_0}{b_1}
$$

can be perturbative.

As the number of flavors is lowered, the fixed point becomes more strongly coupled. At some lower edge of the conformal window, the theory may confine, break chiral symmetry, merge with another fixed point, or otherwise leave the conformal regime. Determining this edge is a hard nonperturbative problem.

Conformal windows are important because they connect perturbation theory, lattice gauge theory, Schwinger–Dyson estimates, bootstrap constraints, and phenomenological model building.

## Three-dimensional gauge CFTs

Three-dimensional gauge theories are especially rich. The gauge coupling has positive mass dimension, so the UV and IR logic differs from four dimensions. Chern–Simons terms can be added:

$$
S_{\rm CS}=\frac{k}{4\pi}\int \operatorname{Tr}\left(A\wedge dA+\frac23 A\wedge A\wedge A\right),
$$

with quantized level $k$ in appropriate normalizations.

Important examples include:

| Theory type | Typical features |
|---|---|
| QED3 with fermions | global flavor symmetry, monopole operators, large-$N_f$ expansion |
| scalar QED3 | Wilson–Fisher-like matter coupled to a gauge field, duality web connections |
| Chern–Simons–matter | parity violation, anyonic statistics, large-$N$ vector limits |
| QCD3-like theories | nonabelian gauge group, flavor symmetry, possible symmetry breaking or CFT behavior |
| deconfined criticality candidates | emergent gauge fields, monopoles, possible symmetry enhancement |

Many three-dimensional gauge CFTs have dual descriptions. A theory written with fermions may be dual to a theory written with bosons and Chern–Simons gauge fields. Bootstrap constraints are valuable because they do not require choosing a weakly coupled side.

## Supersymmetric gauge CFTs

Supersymmetry can make gauge-theory CFTs much more tractable. Superconformal symmetry relates operator dimensions, R-charges, and protected quantities. In some dimensions, exact results can be obtained using localization, holomorphy, or duality.

Examples include:

$$
\mathcal N=4\text{ super-Yang--Mills in }d=4,
$$

which is conformal for all values of the exactly marginal gauge coupling, and three-dimensional supersymmetric Chern–Simons–matter theories with holographic duals.

Supersymmetric examples are important even in a nonsupersymmetric CFT chapter because they teach general lessons:

1. Gauge fields can belong to exact CFTs.
2. A CFT may have a conformal manifold of fixed points.
3. Dual gauge descriptions can describe the same operator algebra.
4. Protected sectors can be solved even when the full theory is strongly coupled.

The full technology of superconformal representation theory belongs to the Supersymmetric CFT chapter.

## Gauge-theory CFTs and the bootstrap

Bootstrap methods study gauge-theory CFTs through gauge-invariant operators. For example, in QED3 with flavor symmetry, one may bootstrap four-point functions of fermion bilinears, scalar bilinears, conserved currents, or monopole operators.

The basic workflow is the same as in scalar bootstrap:

$$
\text{choose external gauge-invariant operators}
\quad\longrightarrow\quad
\text{write crossing equations}
\quad\longrightarrow\quad
\text{impose unitarity, symmetry, and gaps}.
$$

The complications are specific to gauge theories:

- the simplest gauge variables may not be observables;
- global symmetry representations can be large;
- monopoles and baryons may be essential;
- multiple dual descriptions can suggest different external operators;
- relevant singlet scalars determine whether the fixed point is stable;
- current and stress-tensor normalizations distinguish candidate theories.

Bootstrap does not prove that every Lagrangian flows to the assumed CFT. It constrains possible CFT data consistent with the assumed symmetry and spectrum.

## Example: QED3-like theories

A common example is QED3 with $N_f$ two-component or four-component fermions, depending on convention. The schematic action is

$$
S=\int d^3x\left[\bar\psi_i\gamma^\mu(\partial_\mu-iA_\mu)\psi^i+\frac{1}{4e^2}F_{\mu\nu}F^{\mu\nu}\right].
$$

At large $N_f$, the theory is believed to flow to an interacting CFT. The $1/N_f$ expansion estimates dimensions of bilinears, monopoles, currents, and higher-spin operators.

At small $N_f$, the situation can be subtle. The theory may remain conformal, break symmetry, or have dual descriptions depending on matter content and global structure. This is why QED3-like theories are central in modern bootstrap and condensed-matter applications.

Common gauge-invariant operators include:

$$
\bar\psi_i\psi^j,
\qquad
F_{\mu\nu}\text{-related topological currents},
\qquad
\text{monopole operators}.
$$

The monopoles are often the most diagnostic operators because they see the compactness and global structure of the gauge field.

## Example: Chern–Simons–matter CFTs

Chern–Simons–matter theories in three dimensions can be conformal because the Chern–Simons coupling is topological and the level $k$ is quantized. With matter, one can tune interactions to fixed points or use supersymmetry to preserve conformality.

A schematic action is

$$
S=S_{\rm matter}+\frac{k}{4\pi}\int \operatorname{Tr}\left(A\wedge dA+\frac23A\wedge A\wedge A\right)+S_{\rm interactions}.
$$

These theories can violate parity. Their current and stress-tensor three-point functions can contain parity-odd structures. In large-$N$ vector-like Chern–Simons–matter theories, the ratio

$$
\lambda=\frac{N}{k}
$$

plays the role of a 't Hooft coupling.

Chern–Simons–matter CFTs are important in duality webs, anyon physics, vector-model holography, and supersymmetric localization. They are also a reminder that conformal gauge theories need not look like ordinary Yang–Mills theories.

## Deformations and stability

To understand a gauge-theory CFT, one must know its relevant scalar singlets. A relevant singlet deformation can destabilize the fixed point unless it is tuned away.

If $\mathcal O$ is a scalar singlet with

$$
\Delta_\mathcal O<d,
$$

then the deformation

$$
S\to S+g\int d^dx\,\mathcal O(x)
$$

is relevant. The number of relevant singlets determines how many parameters must be tuned to reach the CFT.

For proposed deconfined critical points or gauge-theory descriptions of statistical transitions, stability is crucial. A beautiful candidate fixed point is not a generic critical point if extra relevant singlets are allowed by microscopic symmetries.

In bootstrap language, one often imposes or tests gaps in singlet scalar sectors to distinguish stable from multicritical fixed points.

## Common pitfalls

**Do not treat gauge symmetry as a physical global symmetry.** Gauge symmetry is redundancy. Physical global symmetries act on gauge-invariant operators and defects.

**Do not use gauge-variant fields as CFT local operators.** The elementary gauge field $A_\mu$ and charged matter fields are not local gauge-invariant operators unless dressed or considered in a different context.

**Do not forget monopole and disorder operators.** In three-dimensional gauge CFTs, monopoles can be among the most important local primaries.

**Do not assume every gauge theory flows to a CFT.** Gauge theories may confine, break symmetry, flow to a gapped topological phase, or become conformal depending on matter content and dimension.

**Do not identify the Lie algebra of the gauge group with the full theory.** Global form, line operators, one-form symmetries, and discrete theta-like choices matter.

**Do not assume large $N$ means Einstein gravity.** A large-$N$ vector gauge theory may be closer to higher-spin holography than to Einstein gravity.

**Do not apply weak-coupling intuition at the lower edge of a conformal window.** The fixed point can be strongly coupled or disappear by mechanisms invisible in low-order perturbation theory.

## Relations to other pages

This page completes the [Higher-Dimensional CFT](/cft-bootstrap/higher-dimensional-cft/) chapter's first pass through benchmark examples. It follows [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/), [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/), and [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/).

It prepares [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) because many modern bootstrap targets are gauge-theory CFTs. It also connects to [Conserved Currents](/cft-bootstrap/higher-dimensional-cft/conserved-currents/) and [Conformal Collider Bounds](/cft-bootstrap/higher-dimensional-cft/conformal-collider-bounds/) through current and stress-tensor data.

For gauge-theory foundations, see the gauge-theory volumes. For generalized symmetry, line operators, and anomalies, see the later symmetry and nonperturbative QFT chapters. For supersymmetric examples, see [Supersymmetric CFT](/cft-bootstrap/supersymmetric-cft/).

## Research status

Gauge-theory CFTs are established in many controlled settings: perturbative conformal windows near weak coupling, supersymmetric examples with protected data, large-$N$ limits, and several well-tested three-dimensional fixed points.

Active research is broad. Major questions include the lower edge of conformal windows, the fate of QED3 and QCD3-like theories at small flavor number, the operator spectra of Chern–Simons–matter theories, the consistency of deconfined-criticality scenarios, emergent symmetry, monopole dimensions, line-defect data, and the precise bootstrap signatures of gauge dynamics.

## Exercises

### Exercise 1

Explain why $A_\mu$ is not itself a gauge-invariant local operator in an ordinary gauge theory.

<details><summary><strong>Solution</strong></summary>

Under a gauge transformation, the gauge field changes by a derivative term and a commutator term. In an abelian theory,

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

Therefore $A_\mu(x)$ depends on the choice of gauge and is not a gauge-invariant local observable. Gauge-invariant local operators must be built from objects such as field strengths, covariant composites with gauge indices contracted, or disorder definitions such as monopole insertions.

</details>

### Exercise 2

In a three-dimensional abelian gauge theory, define the topological current

$$
j^\mu_{\rm top}=\frac{1}{2\pi}\epsilon^{\mu\nu\rho}F_{\nu\rho}.
$$

Show that it is conserved by the Bianchi identity.

<details><summary><strong>Solution</strong></summary>

Taking the divergence gives

$$
\partial_\mu j^\mu_{\rm top}
=\frac{1}{2\pi}\epsilon^{\mu\nu\rho}\partial_\mu F_{\nu\rho}.
$$

The Bianchi identity is

$$
\partial_{[\mu}F_{\nu\rho]}=0.
$$

Contracting this identity with $\epsilon^{\mu\nu\rho}$ gives

$$
\epsilon^{\mu\nu\rho}\partial_\mu F_{\nu\rho}=0.
$$

Thus

$$
\partial_\mu j^\mu_{\rm top}=0.
$$

</details>

### Exercise 3

Why is the lower edge of a conformal window a nonperturbative question?

<details><summary><strong>Solution</strong></summary>

Near the upper edge of a conformal window, the fixed point may be weakly coupled, so perturbation theory can locate it. Moving toward the lower edge usually makes the fixed-point coupling larger. Low-order perturbation theory then becomes unreliable.

At strong coupling, several things can happen: the fixed point may persist, merge with another fixed point, become complex, confine, or trigger symmetry breaking. Distinguishing these possibilities requires nonperturbative tools such as lattice simulations, bootstrap, dualities, large-$N$ expansions, or supersymmetric control.

</details>

### Exercise 4

Why can a monopole operator be a local operator even though it is not a polynomial in fields?

<details><summary><strong>Solution</strong></summary>

A local operator in QFT is defined by the boundary condition or insertion it creates in correlation functions, not only by a polynomial expression in microscopic fields. In a three-dimensional gauge theory, a monopole operator is inserted by requiring magnetic flux through a small sphere surrounding the insertion:

$$
\int_{S^2}F=2\pi q.
$$

This condition is localized at the insertion point. Under the state-operator map, it creates a state on $S^2$ with magnetic flux. Therefore it can define a genuine local disorder operator when allowed by the theory.

</details>

### Exercise 5

In a gauge-theory CFT, why are relevant scalar singlets important for stability?

<details><summary><strong>Solution</strong></summary>

A scalar singlet $\mathcal O$ with

$$
\Delta_\mathcal O<d
$$

can be added to the action as

$$
S\to S+g\int d^dx\,\mathcal O(x).
$$

Because the coupling $g$ is relevant, it grows under RG flow and drives the theory away from the fixed point unless tuned to zero. Therefore each relevant scalar singlet allowed by the microscopic symmetries is a tuning parameter. A stable critical point has only the relevant singlets expected from the physical tuning problem.

</details>

## References

- T. Banks and A. Zaks, “On the phase structure of vector-like gauge theories with massless fermions,” *Nuclear Physics B* **196** (1982).
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- S. Giombi and X. Yin, “The higher spin/vector model duality,” *Journal of Physics A* **46** (2013).
- O. Aharony, “Baryons, monopoles and dualities in Chern–Simons-matter theories,” *Journal of High Energy Physics* **2016**.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” *Journal of High Energy Physics* **2015**.
- M. A. Metlitski and A. Vishwanath, “Particle-vortex duality of two-dimensional Dirac fermion from electric-magnetic duality of three-dimensional topological insulators,” *Physical Review B* **93** (2016).
- N. Seiberg, T. Senthil, C. Wang, and E. Witten, “A duality web in 2+1 dimensions and condensed matter physics,” *Annals of Physics* **374** (2016).

## Version history

- 2026-07-01: First polished draft. Added gauge-invariant operator viewpoint, conformal windows, monopoles, line operators, one-form symmetries, 3D gauge CFT examples, bootstrap role, deformations, exercises, and references.
