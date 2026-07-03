---
title: "Regulator and Measure Viewpoints"
description: "Explains how quantum anomalies arise from regulator choices and path-integral measures, and how this viewpoint matches Ward identities and background-field variations."
sidebar:
  label: "Regulator and Measure"
  order: 2
level: Graduate
status: "Polished draft"
source: "Adler–Bell–Jackiw; Fujikawa; Bardeen; Pauli–Villars regularization; Srednicki §§75–77; Schwartz Ch. 30; Weinberg Vol. II Ch. 22."
topics:
  - quantum anomaly
  - regulator
  - path integral measure
  - Fujikawa method
  - Pauli–Villars regularization
  - chiral anomaly
  - counterterms
  - Ward identity
canonicalTopics:
  - regulator-viewpoint-of-anomalies
  - path-integral-measure-anomaly
  - fujikawa-jacobian
  - counterterm-ambiguity
researchStatus:
  established:
    - "Perturbative anomalies can be diagnosed by the impossibility of choosing a regulator and local counterterms that preserve all desired classical symmetries."
    - "For chiral fermions, the path-integral measure viewpoint and the triangle-diagram viewpoint give the same anomaly after the current normalization and regulator convention are matched."
  active:
    - "Modern anomaly theory generalizes this regulator-and-measure logic to fermionic, higher-form, non-invertible, and topological background fields where the 'measure' may be better phrased as the phase of a one-higher-dimensional invertible theory."
---

## Summary

The regulator and measure viewpoints answer a deceptively simple question:

> When a classical symmetry is used as a change of variables in the quantum path integral, what exactly is being held fixed?

A formal Ward-identity derivation starts from

$$
0=\int D\Phi\,\delta\left(e^{iS[\Phi]}\mathcal X[\Phi]\right).
$$

This expression hides two assumptions. The measure $\mathcal D\Phi$ must be invariant, and the regulator that defines the integral must preserve the symmetry. An **anomaly** appears when those assumptions cannot be made true simultaneously with locality, the required gauge redundancies, and the chosen background-field structure.

For a continuous transformation with local parameter $\alpha(x)$, the measure may transform as

$$
D\Phi\longrightarrow J_\alpha[A]D\Phi,
\qquad
J_\alpha[A]=\exp\left(i\int_{M_d}\alpha^a\mathcal A_a[A]\right).
$$

Then the Ward identity acquires the local term $\mathcal A_a[A]$. In the background-field convention of this volume,

$$
\delta_\lambda W[A]=\int_{M_d}\lambda^a\mathcal A_a[A],
\qquad
D_\mu\langle j_a^\mu\rangle_A=-\mathcal A_a[A].
$$

<figure class="doc-figure" style="--figure-width: 55rem;">

![Regulator and measure map for anomalies. A formal classical symmetry enters the quantum path integral only after a regulator and a measure are chosen; the nonremovable part of the Jacobian or regulator variation is the anomaly class.](/figures/symmetry-anomalies-topology/regulator-measure-anomaly-map.svg)

<figcaption>

The regulator and measure diagnostics. A formal classical symmetry becomes a quantum symmetry only if the regulator, measure, and counterterm scheme can be chosen compatibly. A removable breaking is a scheme artifact; a nonremovable breaking is an anomaly.

</figcaption>
</figure>

The lesson is not “the regulator breaks the symmetry, therefore the anomaly is a mistake.” The lesson is sharper:

$$
\text{anomaly} = \text{the part of regulator or measure variation that no allowed local counterterm removes}.
$$

That is why different calculations can look very different while giving the same anomaly. Pauli–Villars makes the anomaly come from heavy regulator fields. Fujikawa’s method makes it come from a regularized Jacobian. Triangle diagrams make it come from a momentum-routing obstruction in a divergent loop integral. Background-field language makes it the non-invariance of $W[A]$.

## Prerequisites

Read [What Is an Anomaly?](/symmetry-anomalies-topology/anomalies/what-is-an-anomaly/), [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/), [Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/), and [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/) first.

You should also know the basic distinction between a background field and a dynamical gauge field from [Background Fields Versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/). The page uses Dirac fermions as the main example, but the logic applies more broadly.

## Core idea

A classical symmetry is a statement about a classical action. A quantum symmetry is a statement about a **regulated quantum definition**.

For fields $\Phi$ and transformation $\Phi\mapsto\Phi+\delta_\alpha\Phi$, the classical action may satisfy

$$
\delta_\alpha S[\Phi;A]=0.
$$

The path integral asks for more:

$$
Z[A]=\int D\Phi\,e^{iS[\Phi;A]}.
$$

The symbol $D\Phi$ is not an innocent product of ordinary Lebesgue measures. In field theory it is an infinite-dimensional object defined by a cutoff, a basis of modes, a lattice, a heat kernel, Pauli–Villars fields, dimensional continuation, point splitting, or another regulator. A transformation that looks like a symmetry of $S$ can change this regulated measure.

For a nonanomalous symmetry, one can choose the quantum definition so that

$$
D\Phi\,e^{iS[\Phi;A]}
$$

is invariant, up to ordinary contact terms and allowed local counterterms. For an anomalous symmetry, every acceptable definition leaves a nontrivial local remainder.

The word **acceptable** matters. A regulator that violates locality, breaks a dynamical gauge redundancy, or changes the theory is not an allowed cure. An anomaly is the obstruction after those constraints are imposed.

## Setup and conventions

We use the volume conventions

$$
Z[A]=e^{iW[A]},
\qquad
D=d-iA,
\qquad
F=dA-iA\wedge A.
$$

For a background gauge transformation with infinitesimal parameter $\lambda$,

$$
\delta_\lambda A=D\lambda.
$$

The current coupled to $A$ is

$$
\langle j_a^\mu(x)\rangle_A=\frac{\delta W[A]}{\delta A^a_\mu(x)}.
$$

If the symmetry is anomalous, we write

$$
\delta_\lambda W[A]=\int_{M_d}\lambda^a\mathcal A_a[A],
$$

so the one-point Ward identity on a closed spacetime is

$$
D_\mu\langle j_a^\mu\rangle_A=-\mathcal A_a[A].
$$

For the Dirac example below, the site-wide gamma-matrix conventions are

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu},
\qquad
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3,
\qquad
\epsilon^{0123}=+1.
$$

We define

$$
\widetilde F^{\mu\nu}=\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma}.
$$

:::note[Convention-sensitive source note]
The coefficient of the chiral anomaly depends on the normalization of the axial current. In this page, when a Dirac fermion has charge $q$, the axial current normalized as the Noether current for $\delta\psi=i\alpha\gamma^5\psi/2$ is

$$
j_A^\mu=\frac12\bar\psi\gamma^\mu\gamma^5\psi.
$$

With this normalization,

$$
\partial_\mu j_A^\mu
=im\bar\psi\gamma^5\psi+\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

If instead one defines $j_5^\mu=\bar\psi\gamma^\mu\gamma^5\psi$, the right-hand side is doubled. Many textbooks use the latter current.
:::

## Finite-dimensional changes of variables

Start with an ordinary integral

$$
I=\int_{\mathbb R^n}d^nx\,e^{iS(x)}.
$$

Under an invertible change of variables $x\mapsto x'=f(x)$,

$$
d^nx'=\left|\det\frac{\partial x'}{\partial x}\right|d^nx.
$$

If $S(f(x))=S(x)$ and the Jacobian is $1$, the integral is invariant. If the Jacobian is not $1$, the measure changes. In finite dimensions this is just calculus, not a paradox.

For Grassmann variables the Jacobian is inverted. If

$$
\psi_i'=M_{ij}\psi_j,
$$

then

$$
\prod_i d\psi_i'=\det(M)^{-1}\prod_i d\psi_i.
$$

For a paired transformation of $\psi$ and $\bar\psi$, the two Jacobians multiply.

The anomaly story is the field-theory version of this elementary fact, but with a twist: the determinant is now an infinite product and must be regulated. The regulated determinant can remember ultraviolet information even when the classical transformation is local and smooth.

## Why infinite measures are not neutral

A field can be expanded in modes,

$$
\psi(x)=\sum_n a_n\varphi_n(x),
\qquad
\bar\psi(x)=\sum_n \bar b_n\varphi_n^\dagger(x),
$$

and the formal measure is written

$$
D\psi D\bar\psi=\prod_n da_n\,d\bar b_n.
$$

A chiral rotation of a massless Dirac fermion,

$$
\psi\longrightarrow e^{i\alpha(x)\gamma^5/2}\psi,
\qquad
\bar\psi\longrightarrow\bar\psi e^{i\alpha(x)\gamma^5/2},
$$

mixes the modes. Formally, the logarithm of the Jacobian contains a trace like

$$
\operatorname{Tr}\left(\alpha\gamma^5\right).
$$

This trace is meaningless until it is regularized. The regulator cannot be chosen arbitrarily; if the fermion is coupled to a background or dynamical gauge field, the regulator should respect the corresponding gauge covariance.

The Fujikawa choice is to regulate the trace by a gauge-covariant operator, usually the square of the Dirac operator in Euclidean signature:

$$
\operatorname{Tr}\left(\alpha\gamma^5\right)
\quad\leadsto\quad
\lim_{M\to\infty}\operatorname{Tr}\left(\alpha\gamma^5 e^{-\mathcal D^2/M^2}\right).
$$

The high-energy modes do not cancel completely. Their regulated trace leaves a finite local density: the anomaly.

## The Fujikawa calculation in compressed form

Consider a Dirac fermion coupled to a background $U(1)$ field,

$$
S=\int d^4x\,\bar\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu-iqA_\mu.
$$

For $m=0$, the classical axial rotation

$$
\delta\psi=\frac{i\alpha(x)}{2}\gamma^5\psi,
\qquad
\delta\bar\psi=\bar\psi\frac{i\alpha(x)}{2}\gamma^5
$$

is a symmetry up to the derivative of the local parameter. The classical Ward identity would be

$$
\partial_\mu j_A^\mu=0.
$$

The regulated path-integral measure instead gives

$$
D\psi D\bar\psi\longrightarrow
\exp\left(i\int d^4x\,\alpha(x)\mathcal A(x)\right)D\psi D\bar\psi.
$$

Fujikawa’s formula computes

$$
\mathcal A(x)=\lim_{M\to\infty}\operatorname{tr}\left[\frac12\gamma^5 e^{-(i\gamma^\mu D_\mu)^2/M^2}\right]_{x,x},
$$

where $\operatorname{tr}$ is over spinor and internal indices, while $[\cdots]_{x,x}$ denotes the coincident heat kernel.

The key algebraic input is that

$$
(i\gamma^\mu D_\mu)^2
= -D^2+\frac{q}{2}\sigma^{\mu\nu}F_{\mu\nu}
$$

up to the Lorentzian/Euclidean continuation convention used to make the heat kernel convergent, with

$$
\sigma^{\mu\nu}=\frac{i}{2}[\gamma^\mu,\gamma^\nu].
$$

Only the term quadratic in $F$ survives the spinor trace with $\gamma^5$. The result is

$$
\mathcal A(x)=\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

Thus

$$
\partial_\mu j_A^\mu
=im\bar\psi\gamma^5\psi
+\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

The mass term is explicit breaking. The $F\widetilde F$ term is the anomaly.

:::caution[Do not overread the formal trace]
The unregulated trace $\operatorname{Tr}\gamma^5$ is not the anomaly. The anomaly is the finite remainder of a **gauge-covariantly regulated** trace. Dropping the regulator too early is the fastest route to nonsense.
:::

## Pauli–Villars: the anomaly from heavy fields

The same anomaly can be seen with Pauli–Villars regularization. Introduce heavy regulator fermions with mass $M$ and coefficients chosen to cancel ultraviolet divergences. The regulator fields are not physical; they are a controlled way to define the determinant.

For the vector gauge symmetry, one can choose regulator couplings that preserve gauge invariance. But a regulator mass term has the same axial transformation problem as an ordinary fermion mass:

$$
M\bar\chi\chi
\quad\text{is not invariant under}\quad
\chi\mapsto e^{i\alpha\gamma^5/2}\chi.
$$

Taking $M\to\infty$ removes the regulator particles from the spectrum, but not from the anomalous Ward identity. Their ultraviolet contribution leaves the finite $F\widetilde F$ term.

This is a useful sanity check. The anomaly is not tied to light regulator artifacts. It is the residue of trying to impose mutually incompatible requirements:

$$
\text{locality} + \text{gauge invariance} + \text{axial symmetry} + \text{UV regularization}.
$$

For the ordinary axial anomaly in QED, one preserves vector gauge invariance and sacrifices axial current conservation. For a would-be gauge anomaly in a chiral gauge theory, sacrificing gauge invariance is not allowed; the fermion content must make the gauge anomaly cancel.

## A regulator dictionary

Different regulators expose different aspects of the same obstruction.

| Regulator or definition | What it makes transparent | What to watch |
|---|---|---|
| Heat-kernel or Fujikawa regulator | Measure Jacobian and local index-density structure | Requires careful Euclidean continuation and current normalization. |
| Pauli–Villars | Heavy regulator fields carry the anomaly | Regulator masses often choose which symmetry is preserved. |
| Dimensional regularization | Gauge invariance and perturbative loop technology | $\gamma^5$ and Levi-Civita tensors are subtle away from four dimensions. |
| Point splitting | Current definition and short-distance singularity | Gauge links are needed to preserve gauge covariance. |
| Lattice regularization | Nonperturbative definition and exact gauge invariance | Chiral symmetry, locality, and species doubling require care. |
| Background-field regularization | Covariant organization of current correlators | Local counterterms can shift contact terms and consistent versus covariant forms. |

No single regulator is morally superior in all contexts. A regulator is a tool for making the quantum definition precise. A genuine anomaly is the part that survives comparison among all acceptable tools.

## Counterterms and moving the anomaly

Suppose the background effective action has anomalous variation

$$
\delta_\lambda W[A]=\int_{M_d}\lambda^a\mathcal A_a[A].
$$

Adding a local counterterm changes

$$
W[A]\longrightarrow W[A]+S_{\mathrm{ct}}[A].
$$

Therefore

$$
\mathcal A_a[A]
\longrightarrow
\mathcal A_a[A]+\frac{\delta_\lambda S_{\mathrm{ct}}[A]}{\lambda^a}
$$

schematically. More invariantly, the anomaly is not a single density but an equivalence class

$$
\mathcal A\sim \mathcal A+\delta S_{\mathrm{ct}}.
$$

This is why a local term in a Ward identity is not automatically an anomaly. It might be removable.

A famous example is the AVV triangle diagram with one axial current and two vector currents. A local counterterm can move the anomalous term between the axial Ward identity and the vector Ward identities. If the vector symmetry is electromagnetic gauge invariance, the vector Ward identities must be preserved. The anomaly is then placed in the axial current:

$$
\partial_\mu j_A^\mu
=im\bar\psi\gamma^5\psi
+\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

This does not mean the anomaly is arbitrary. The counterterm changes its representative, not the underlying obstruction.

:::note[Consistent versus covariant source note]
In non-Abelian chiral theories, the anomaly obtained by varying a regularized effective action is the **consistent anomaly** and obeys Wess–Zumino consistency. One can add a Bardeen–Zumino local polynomial to define a covariant current with a covariant-looking divergence. The covariant anomaly is often prettier, but the consistent anomaly is the one that directly integrates to a variation of $W[A]$.
:::

## Wess–Zumino consistency from the measure viewpoint

Background gauge transformations form an algebra. Therefore their anomalous variations must also form the same algebra when acting on the effective action:

$$
[\delta_{\lambda_1},\delta_{\lambda_2}]W[A]
=\delta_{[\lambda_1,\lambda_2]}W[A].
$$

If

$$
\delta_\lambda W[A]=\mathcal A_\lambda[A],
$$

then

$$
\delta_{\lambda_1}\mathcal A_{\lambda_2}
-\delta_{\lambda_2}\mathcal A_{\lambda_1}
=\mathcal A_{[\lambda_1,\lambda_2]}.
$$

This is the **Wess–Zumino consistency condition**. It says that anomalies are not arbitrary symmetry-breaking terms. They must be compatible with the symmetry algebra. Later pages repackage this condition using descent equations and anomaly polynomials.

The measure viewpoint makes the reason intuitive. A Jacobian for two successive changes of variables must compose associatively. The anomalous phase can be nontrivial, but it cannot violate the group law.

## Gauge anomaly versus global anomaly

The regulator viewpoint is especially good at separating two cases.

A **gauge anomaly** is an anomaly in a redundancy used to define the theory. Then the path integral over gauge fields is not consistently defined. Gauge-dependent states fail to decouple, BRST symmetry is spoiled, or the background-field effective action cannot be promoted to a dynamical gauge theory. Such an anomaly must cancel.

A **global anomaly** or **’t Hooft anomaly** is an anomaly of a genuine global symmetry. The theory can still exist, but the symmetry cannot be gauged as an ordinary stand-alone operation. The anomaly becomes physical data. It constrains RG flow, boundary conditions, symmetry breaking, and possible trivially gapped phases.

In both cases the local computation may look similar. The difference is which symmetry is allowed to fail.

## How to recognize a fake anomaly

Not every failure of a Ward identity is a quantum anomaly. Common impostors include:

| Phenomenon | Diagnostic |
|---|---|
| Explicit breaking | The action changes already classically, such as a fermion mass breaking axial symmetry. |
| Contact term | The current is acting on nearby operator insertions; the Ward identity is distributional. |
| Current improvement | The current changed by a total derivative or equation-of-motion term. |
| Bad regulator artifact | A different allowed regulator or local counterterm restores the symmetry. |
| Boundary flux | Charge leaks through a boundary or defect; the bulk symmetry may be intact. |
| Gauge choice artifact | A non-gauge-invariant object was used as if it were physical. |

A genuine anomaly survives these tests. It cannot be removed without changing the theory or abandoning a required structural principle.

## Worked example: axial rotation of one Dirac fermion

For a massive Dirac fermion,

$$
\mathcal L=\bar\psi(i\gamma^\mu D_\mu-m)\psi.
$$

Under

$$
\delta\psi=\frac{i\alpha}{2}\gamma^5\psi,
\qquad
\delta\bar\psi=\bar\psi\frac{i\alpha}{2}\gamma^5,
$$

the classical variation gives

$$
\delta\mathcal L=-(\partial_\mu\alpha)j_A^\mu+i\alpha m\bar\psi\gamma^5\psi,
$$

where

$$
j_A^\mu=\frac12\bar\psi\gamma^\mu\gamma^5\psi.
$$

If the measure were invariant, the Ward identity would be

$$
\partial_\mu j_A^\mu=im\bar\psi\gamma^5\psi.
$$

The regulated measure adds the Jacobian contribution, so the quantum identity is

$$
\partial_\mu j_A^\mu
=im\bar\psi\gamma^5\psi
+\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

This equation separates the two kinds of breaking:

$$
\text{mass term} = \text{explicit breaking},
\qquad
F\widetilde F = \text{anomaly}.
$$

When $m=0$, the classical axial symmetry still fails quantum mechanically in gauge-field backgrounds with nonzero $F\widetilde F$.

## Common pitfalls

**Pitfall 1: Saying the anomaly is caused by a bad regulator.**  
A bad regulator can create fake breaking. A real anomaly is the statement that no acceptable regulator and counterterm scheme preserves all the desired structures.

**Pitfall 2: Dropping the regulator in Fujikawa’s trace.**  
The formal expression $\operatorname{Tr}\gamma^5$ is not meaningful by itself. The anomaly is a regulated ultraviolet trace.

**Pitfall 3: Treating counterterm dependence as unphysical in all senses.**  
The representative of an anomaly can change under local counterterms, but the anomaly class is physical. Which representative is most useful depends on whether one wants consistent currents, covariant currents, or a specific preserved subgroup.

**Pitfall 4: Confusing explicit breaking with anomalous breaking.**  
The fermion mass term in the axial Ward identity is explicit breaking. The $F\widetilde F$ term remains even when the classical massless symmetry exists.

**Pitfall 5: Forgetting dynamical gauge redundancies.**  
A global symmetry anomaly is allowed and meaningful. A dynamical gauge anomaly is an inconsistency unless canceled.

## Relations to other pages

The regulator viewpoint is the conceptual bridge to [Triangle Anomaly](/symmetry-anomalies-topology/anomalies/triangle-anomaly/), where the same obstruction appears as a one-loop momentum-routing problem.

It prepares [Fujikawa Method](/symmetry-anomalies-topology/anomalies/fujikawa-method/), which computes the Jacobian carefully, and [Chiral Anomaly](/symmetry-anomalies-topology/anomalies/chiral-anomaly/), which studies the axial-current equation and its physical consequences.

It also prepares [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), [Consistent Versus Covariant Anomalies](/symmetry-anomalies-topology/anomalies/consistent-versus-covariant-anomalies/), [Wess–Zumino Consistency Condition](/symmetry-anomalies-topology/anomalies/wess-zumino-consistency-condition/), [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/), and [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/).

For the broader physical meaning, see [’t Hooft Anomalies](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/thooft-anomalies/) and [Anomalies as RG Invariants](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-as-rg-invariants/).

## Research status

The regulator and measure viewpoints for perturbative fermion anomalies are established textbook material. They are not merely heuristic; they match diagrammatic calculations, index-theoretic formulas, and background-field descent.

The frontier is not whether this mechanism exists. The frontier is how broadly the same logic should be formulated. In modern symmetry theory, anomalies may involve finite groups, higher-form symmetries, fermion parity, reflection or time reversal, non-invertible defects, and higher-categorical background data. In those cases the phrase “path-integral measure” may be too narrow, but the core lesson survives: the quantum theory may fail to be invariant under a background-field redundancy by a well-defined, nonremovable phase.

## Exercises

### Exercise 1: Grassmann Jacobian

Let $\psi_i'=M_{ij}\psi_j$ for $n$ Grassmann variables. Show that

$$
\prod_i d\psi_i'=\det(M)^{-1}\prod_i d\psi_i.
$$

Then explain why a fermion measure can acquire a determinant under a field redefinition.

<details><summary><strong>Solution</strong></summary>

For one Grassmann variable, if $\psi'=a\psi$, then $d\psi'=a^{-1}d\psi$ because the integral must satisfy

$$
1=\int d\psi'\,\psi'=\int a^{-1}d\psi\,a\psi.
$$

For $n$ variables, diagonalize or triangularize the linear transformation, or use the defining property of Berezin integration. Each eigenvalue contributes inversely, so

$$
\prod_i d\psi_i'=\det(M)^{-1}\prod_i d\psi_i.
$$

A fermion field is an infinite collection of Grassmann coefficients after mode expansion. A field redefinition therefore produces an infinite determinant. In QFT that determinant must be regulated, and the regulated determinant can leave a finite anomaly.

</details>

### Exercise 2: Why the regulator matters

Consider the formal trace $\operatorname{Tr}\gamma^5$ in a Dirac theory. Explain why setting it to zero by pairing left- and right-handed modes is not a valid anomaly calculation in a background gauge field.

<details><summary><strong>Solution</strong></summary>

The expression $\operatorname{Tr}\gamma^5$ is infinite-dimensional and not defined without a regulator. In a background gauge field, the regulator must preserve the required gauge covariance. The gauge-covariant regulated trace is not the same as the naive algebraic trace over a finite-dimensional spinor space.

Fujikawa’s method replaces the formal trace by

$$
\lim_{M\to\infty}\operatorname{Tr}\left(\alpha\gamma^5e^{-\mathcal D^2/M^2}\right).
$$

The heat kernel weights the high-energy modes in a gauge-covariant way. Its coincident-point expansion contains a finite $F\widetilde F$ term. Thus the anomaly is not the trace of $\gamma^5$ alone; it is the regulated ultraviolet trace in a background field.

</details>

### Exercise 3: Explicit versus anomalous axial breaking

For a charge-$q$ Dirac fermion with

$$
j_A^\mu=\frac12\bar\psi\gamma^\mu\gamma^5\psi,
$$

the quantum Ward identity is

$$
\partial_\mu j_A^\mu
=im\bar\psi\gamma^5\psi
+\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

Which term is explicit breaking and which term is anomalous? What happens when $m=0$?

<details><summary><strong>Solution</strong></summary>

The term

$$
im\bar\psi\gamma^5\psi
$$

is explicit breaking because the mass term is not invariant under the axial rotation already at the classical level. The term

$$
\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}
$$

is anomalous breaking because it remains even when the classical massless action has the axial symmetry.

When $m=0$, the explicit breaking vanishes, but the anomaly remains in gauge-field backgrounds with nonzero $F\widetilde F$.

</details>

### Exercise 4: Counterterm shift

Suppose an anomaly representative changes by

$$
\mathcal A_\lambda[A]\longrightarrow \mathcal A_\lambda[A]+\delta_\lambda S_{\mathrm{ct}}[A].
$$

Explain why this does not mean the anomaly is unphysical.

<details><summary><strong>Solution</strong></summary>

A local counterterm changes the representative of the anomaly. It can move terms among Ward identities or change the contact-term scheme. But if no allowed counterterm makes the anomaly vanish completely, the equivalence class is nontrivial.

The physical anomaly is therefore not a preferred local density by itself. It is the obstruction class modulo local counterterm variations. This is similar to saying that a gauge potential can change by a gauge transformation while the field strength or holonomy data remain physical.

</details>

## References

- S. L. Adler, “Axial-Vector Vertex in Spinor Electrodynamics,” *Physical Review* **177** (1969).
- J. S. Bell and R. Jackiw, “A PCAC Puzzle: $\pi^0\to\gamma\gamma$ in the $\sigma$-Model,” *Nuovo Cimento A* **60** (1969).
- K. Fujikawa, “Path-Integral Measure for Gauge-Invariant Fermion Theories,” *Physical Review Letters* **42** (1979).
- W. A. Bardeen, “Anomalous Ward Identities in Spinor Field Theories,” *Physical Review* **184** (1969).
- R. A. Bertlmann, *Anomalies in Quantum Field Theory*, Oxford University Press.
- M. Srednicki, *Quantum Field Theory*, §§75–77.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 30.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, Ch. 22.
- K. Fujikawa and H. Suzuki, *Path Integrals and Quantum Anomalies*.

## Version history

- 2026-06-18: First polished draft. Added regulator dictionary, Fujikawa summary, Pauli–Villars interpretation, counterterm equivalence, and exercises.
