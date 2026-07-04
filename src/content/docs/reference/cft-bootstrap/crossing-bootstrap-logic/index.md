---
title: "Crossing Symmetry and Bootstrap Logic"
description: "Chapter overview for crossing symmetry, bootstrap equations, positivity, assumptions, islands, and the logical structure of the conformal bootstrap."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Polyakov 1974; Belavin–Polyakov–Zamolodchikov 1984; Rattazzi–Rychkov–Tonni–Vichi 2008; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019; Rychkov–Su 2024"
topics:
  - crossing symmetry
  - conformal bootstrap
  - bootstrap equations
  - unitarity
  - positivity
  - numerical bootstrap
canonicalTopics:
  - crossing-symmetry-and-bootstrap-logic
  - conformal-bootstrap
  - bootstrap-equations
  - positivity-and-unitarity
  - bootstrap-islands
researchStatus:
  established:
    - "Crossing symmetry expresses associativity of the OPE and gives nonperturbative consistency equations for CFT data."
    - "In unitary CFTs, reflection positivity turns many four-point bootstrap equations into positivity problems for squared OPE coefficients or positive semidefinite OPE matrices."
  active:
    - "Which assumptions isolate a given CFT, how to certify islands, how to extract spectra robustly, and how to combine analytic, numerical, modular, defect, and Lorentzian constraints remain active research directions."
---

Crossing Symmetry and Bootstrap Logic is the chapter in the CFT and Bootstrap volume where the previous machinery becomes a nonperturbative method. Conformal symmetry fixes the kinematic form of correlators. The OPE expands products of local operators. Conformal blocks package the descendants of one exchanged primary. Crossing symmetry demands that all these ways of expanding the same correlator agree.

The chapter is not just about one pretty equation. It is about the logic that turns CFT data into a constrained mathematical object:

$$
\text{spectrum} + \text{OPE coefficients}
\quad\xrightarrow{\text{blocks}}\quad
\text{correlators}
\quad\xrightarrow{\text{crossing}}\quad
\text{consistency constraints}.
$$

For a unitary CFT, these constraints become much sharper because OPE coefficients often enter as squares or positive semidefinite matrices. That positivity is the hinge on which the numerical conformal bootstrap turns.

Read this chapter when you want to understand why CFT data are not arbitrary, how crossing equations are built, what assumptions enter a bootstrap problem, why allowed islands can appear, and what the bootstrap can honestly prove.

## Prerequisites

You should know [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/), [Unitarity and Reflection Positivity](/cft-bootstrap/what-is-a-cft/unitarity-and-reflection-positivity/), [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/), [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/), [Associativity of OPE](/cft-bootstrap/operator-product-expansion/associativity-of-ope/), and the [Conformal Blocks](/cft-bootstrap/conformal-blocks/) chapter.

For a first pass, you do not need semidefinite programming, mixed-correlator technology, extremal functionals, or the modern navigator and skydive algorithms. Those belong later in [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/). This chapter teaches what the equations mean before teaching how large computations solve them.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) | The equality of different OPE expansions of the same correlator. |
| 2 | [Bootstrap Equations](/cft-bootstrap/crossing-bootstrap-logic/bootstrap-equations/) | How crossing becomes equations for dimensions, spins, and OPE coefficients. |
| 3 | [Four-Point Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/four-point-bootstrap/) | The standard scalar four-point setup and its block decomposition. |
| 4 | [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/) | Why unitary CFTs give positive OPE weights and positive semidefinite matrices. |
| 5 | [Identical Scalar Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/identical-scalar-bootstrap/) | The cleanest single-correlator bootstrap problem and the origin of exclusion bounds. |
| 6 | [Mixed-Correlator Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/mixed-correlator-bootstrap/) | How multiple external operators and symmetry sectors create matrix bootstrap equations. |
| 7 | [Gaps and Assumptions](/cft-bootstrap/crossing-bootstrap-logic/gaps-and-assumptions/) | Which extra hypotheses define a bootstrap problem and how assumptions change conclusions. |
| 8 | [Islands in Parameter Space](/cft-bootstrap/crossing-bootstrap-logic/islands-in-parameter-space/) | Why isolated allowed regions can identify candidate CFTs such as the 3D Ising CFT. |
| 9 | [Extremal Functional Method](/cft-bootstrap/crossing-bootstrap-logic/extremal-functional-method/) | How boundary points of allowed regions can reveal approximate spectra and OPE data. |
| 10 | [What Bootstrap Can and Cannot Prove](/cft-bootstrap/crossing-bootstrap-logic/what-bootstrap-can-and-cannot-prove/) | The honest scope of bootstrap constraints, assumptions, numerics, and interpretation. |

After this path, you should be able to write the scalar four-point crossing equation, identify where positivity enters, explain what an exclusion bound means, and state which assumptions were used in a bootstrap claim.

## Landmarks

The first landmark is **crossing as OPE associativity**. In a four-point function, one may fuse $1$ with $2$, or $1$ with $4$, or $1$ with $3$. These choices are different expansions of one object, not different observables.

For identical scalar primaries $\phi$ of dimension $\Delta_\phi$, write

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}
\mathcal G(U,V),
$$

where

$$
U=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
V=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The crossing equation under $1\leftrightarrow3$ is

$$
V^{\Delta_\phi}\mathcal G(U,V)
=
U^{\Delta_\phi}\mathcal G(V,U).
$$

The second landmark is the **block expansion**:

$$
\mathcal G(U,V)
=
\sum_{\mathcal O\in \phi\times \phi}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(U,V).
$$

The exchanged operator data $(\Delta,\ell)$ enter through conformal blocks. The dynamical coefficients enter as $\lambda_{\phi\phi\mathcal O}^2$.

The third landmark is the **bootstrap vector equation**. Define a crossing vector

$$
F_{\Delta,\ell}(U,V)
=
V^{\Delta_\phi}G_{\Delta,\ell}(U,V)
-
U^{\Delta_\phi}G_{\Delta,\ell}(V,U).
$$

Then crossing becomes schematically

$$
\sum_{\mathcal O}
\lambda_{\phi\phi\mathcal O}^2
F_{\Delta,\ell}(U,V)=0.
$$

The fourth landmark is **positivity**. In a unitary identical-scalar bootstrap problem,

$$
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

This turns crossing into a convex-geometric problem: can zero lie in the positive cone generated by allowed crossing vectors?

<figure class="doc-figure" style="--figure-width: 46rem;">

![Bootstrap logic flow](/figures/cft-bootstrap/bootstrap-logic-flow.svg)

<figcaption>

The bootstrap loop begins with candidate CFT data and assumptions, translates OPE associativity into crossing equations, tests positivity with functionals, and returns excluded regions, bounds, or islands.

</figcaption>
</figure>

The fifth landmark is **exclusion by linear functionals**. If a linear functional $\alpha$ satisfies

$$
\alpha(F_{\Delta,\ell})\ge0
$$

for every operator allowed by the assumptions, but

$$
\alpha(F_{\mathbf 1})>0
$$

or the corresponding identity-normalized contradiction holds, then that assumed spectrum is impossible. This is the conceptual engine behind numerical bootstrap bounds.

The sixth landmark is **interpretation**. A bootstrap plot is not a measurement. It is a theorem-like conditional statement inside a chosen setup:

```txt
If a unitary CFT has these symmetries, dimensions, gaps, and external operators,
then its CFT data must lie in this allowed region.
```

Changing the assumptions changes the theorem.

## Common confusions

| Confusion | Better statement |
|---|---|
| Crossing symmetry is an extra symmetry of a special CFT. | Crossing is a consistency condition on local operator products in any CFT. |
| Bootstrap equations determine everything automatically. | They constrain CFT data; uniqueness requires enough equations, assumptions, and sometimes numerical or analytic input. |
| A numerical exclusion plot is a direct experimental plot. | It is a conditional allowed/excluded region in theory space. |
| Positivity comes from conformal symmetry alone. | Positivity comes from unitarity or reflection positivity plus a suitable choice of correlator basis. |
| A kink is automatically a known CFT. | A kink is evidence of a change in the optimal solution; identifying it requires more checks. |
| An island proves a theory exists. | An island shows that data satisfying the assumptions must lie there if such a CFT exists; existence and uniqueness can require additional arguments. |
| Mixed correlators are just more equations. | Mixed correlators add matrix positivity, symmetry-sector structure, and much stronger constraints. |
| More assumptions always make a result better. | Stronger assumptions may isolate a theory, but they also narrow the scope of the conclusion. |

## Boundaries

This chapter is the conceptual home of crossing equations and bootstrap logic. It stops before the heavy machinery of large numerical implementations.

| Topic | Main home |
|---|---|
| Definition of primaries, descendants, and multiplets | [Operators, States, and Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/) |
| OPE convergence and OPE coefficients | [Operator Product Expansion](/cft-bootstrap/operator-product-expansion/) |
| Conformal blocks and block computation | [Conformal Blocks](/cft-bootstrap/conformal-blocks/) |
| Semidefinite programming, derivative bases, SDPB, islands in large systems | [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) |
| Lightcone limits, inversion formula, and large-spin expansions | [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/) |
| Modular invariance and torus partition-function constraints | [Modular Bootstrap](/cft-bootstrap/modular-bootstrap/) |
| Boundary, defect, and interface crossing equations | [Boundary, Defect, and Interface CFT](/cft-bootstrap/boundary-defect-interface-cft/) |
| Holographic crossing, Witten diagrams, and AdS locality | [Holographic CFT](/cft-bootstrap/holographic-cft/) |

The chapter also avoids claiming that the bootstrap is a single algorithm. “Bootstrap” names a family of consistency methods. Some are analytic, some numerical, some modular, some Lorentzian, some holographic. Their shared DNA is the demand that CFT data assemble into well-defined correlators.

## Where to go next

After this chapter, most readers should go to [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) to learn how linear and semidefinite programming produce bounds, allowed regions, and spectra. Readers who care more about analytic structure should go to [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/), where lightcone limits and large-spin perturbation theory turn crossing into asymptotic formulas for operator data.

For two-dimensional readers, the natural next route is [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/), [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/), and [Minimal Models and Rational CFT](/cft-bootstrap/minimal-models-rational-cft/). For readers motivated by statistical physics, continue later to [CFT in Statistical Physics and Matter](/cft-bootstrap/cft-in-statistical-physics-matter/). For readers motivated by quantum gravity, continue later to [Holographic CFT](/cft-bootstrap/holographic-cft/).

## References

- A. M. Polyakov, “Non-Hamiltonian approach to conformal quantum field theory,” 1974.
- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” 1984.
- R. Rattazzi, V. S. Rychkov, E. Tonni, and A. Vichi, “Bounding scalar operator dimensions in 4D CFT,” 2008.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, 2016.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures, 2017.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” 2019.
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.

## Version history

- 2026-06-27: First polished draft. Replaced scaffold overview with a reader-facing chapter doorway for crossing symmetry, bootstrap equations, positivity, assumptions, islands, and scope.
