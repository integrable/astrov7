---
title: "Anomalies as Obstructions"
description: "Explains anomalies in BRST-BV gauge theory as cohomological obstructions to preserving gauge symmetry after quantization."
sidebar:
  label: "Anomalies as Obstructions"
  order: 9
level: Advanced
status: "Polished draft"
source: "Adler–Bell–Jackiw; Wess–Zumino; Barnich–Brandt–Henneaux; algebraic renormalization; pAQFT BV literature"
topics:
  - anomalies
  - BRST cohomology
  - BV formalism
  - Wess-Zumino consistency
  - quantum master equation
canonicalTopics:
  - anomalies-as-obstructions
  - brst-anomalies
  - wess-zumino-consistency
  - local-brst-cohomology
  - quantum-master-equation
researchStatus:
  established:
    - "In local perturbative gauge theory, anomaly candidates are represented by ghost-number-one local BRST cohomology classes, and trivial classes can be removed by local counterterms."
  active:
    - "Global anomalies, boundary anomalies, higher-form anomalies, and nonperturbative gauge-sector obstructions require additional tools beyond local BRST-BV cohomology."
---

## Summary

An anomaly is a symmetry that exists at the classical level but cannot be preserved by the chosen quantum construction. In a gauge theory this is not merely a broken conservation law: if the symmetry is genuine gauge redundancy, a nontrivial gauge anomaly is an obstruction to defining the quantum theory with the intended physical state space.

In BRST-BV language, the obstruction is cohomological. Let $s$ be the classical BRST-BV differential. A one-loop breaking of the quantum master equation or Slavnov–Taylor identity has the schematic form

$$
\mathcal S(\Gamma)
=
\hbar\mathcal A+O(\hbar^2),
$$

where $\Gamma$ is a renormalized effective action or interacting functional. Consistency of the identity implies

$$
s\mathcal A=0.
$$

Changing the renormalization prescription or adding a local counterterm $B$ changes

$$
\mathcal A\longmapsto \mathcal A+sB.
$$

Thus the anomaly is not the particular formula $\mathcal A$ but the class

$$
[\mathcal A]\in H^1(s)
$$

or, for local $d$-form densities modulo total derivatives,

$$
[\mathcal A]\in H^{1,d}(s\mid d).
$$

If this class vanishes, the anomaly is removable. If it does not vanish, the classical gauge redundancy cannot be maintained by local counterterms inside the given perturbative theory.

:::note[Gauge versus global]
A gauge anomaly is usually fatal because gauge transformations are redundancies. A global-symmetry anomaly is often valuable physical data: it constrains renormalization group flows, boundary theories, and possible couplings to background fields. This page focuses on local BRST-BV gauge anomalies.
:::

## Prerequisites

Read [Quantum Master Equation](/rigorous-qft/bv-brst-gauge-theory/quantum-master-equation/), [Ghosts, Antifields, and Cohomology](/rigorous-qft/bv-brst-gauge-theory/ghosts-antifields-and-cohomology/), [Observables as Cohomology](/rigorous-qft/bv-brst-gauge-theory/observables-as-cohomology/), and [Gauge Fixing as a Lagrangian Submanifold](/rigorous-qft/bv-brst-gauge-theory/gauge-fixing-as-lagrangian-submanifold/) first. For the renormalized perturbative setting, use [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/) and [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/).

## Core idea

Classically, a gauge theory has a BRST-BV differential $s$ satisfying

$$
s^2=0.
$$

Equivalently, in BV language the classical master action satisfies

$$
(S_0,S_0)=0,
\qquad
sF=(S_0,F).
$$

Quantization asks for a renormalized construction in which the quantum version of this identity still holds. In finite-dimensional BV theory, the clean formal equation is

$$
\frac12(S,S)-i\hbar\Delta S=0.
$$

In local QFT, $\Delta S$ is not literally a well-defined local functional. The field-theoretic statement is instead formulated through renormalized Ward identities, Slavnov–Taylor identities, master Ward identities, or a renormalized BV operator replacing the naive Laplacian.

The obstruction appears when the desired identity fails by a local term:

$$
\mathcal S(\Gamma)=\hbar^n\mathcal A_n+O(\hbar^{n+1}).
$$

Here $\mathcal S$ denotes the relevant Slavnov or master operator. The identity $\mathcal S^2=0$, linearized at lower orders, forces

$$
s\mathcal A_n=0.
$$

If there exists a local counterterm $B_n$ such that

$$
\mathcal A_n=sB_n,
$$

then replacing $\Gamma$ by $\Gamma-\hbar^n B_n$ removes the breaking at that order. If not, the class $[\mathcal A_n]$ is a genuine anomaly.

<figure class="doc-figure" style="--figure-width: 52rem;">

![An anomaly as a cohomological obstruction in BRST-BV theory](/figures/rigorous-qft/anomaly-obstruction-descent.svg)

<figcaption>

In local perturbative gauge theory, a breaking term $\mathcal A$ must satisfy a consistency condition. Counterterms shift $\mathcal A$ by an exact term. The cohomology class $[\mathcal A]\in H^{1,d}(s\mid d)$ is the obstruction; only a nonzero class is a genuine local anomaly.

</figcaption>
</figure>

## Setup and conventions

Let $M$ be an oriented $d$-dimensional spacetime, and let $s$ denote the classical BRST-BV differential. We write local densities as horizontal forms on spacetime. A local anomaly density has ghost number $1$ and form degree $d$.

The local condition is

$$
sa_d^1+db_{d-1}^2=0,
$$

where the subscript is form degree and the superscript is ghost number. The equivalence relation is

$$
a_d^1\sim a_d^1+sm_d^0+dn_{d-1}^1.
$$

Thus local anomaly candidates live in

$$
H^{1,d}(s\mid d).
$$

This notation is compact but important. The $d$ in $H^{1,d}(s\mid d)$ means we are classifying local Lagrangian densities or integrated local functionals. The vertical bar means that equality is taken modulo total derivatives, because integrated actions and Ward identity breakings are insensitive to boundary-free exact forms.

We use the word **local** in the standard perturbative sense: the density depends on finitely many jets of fields, ghosts, antifields, background structures, and sources at the same spacetime point.

## Wess–Zumino consistency

The Wess–Zumino consistency condition is the anomaly version of the statement that two infinitesimal symmetry transformations have a prescribed commutator. In BRST language it is simply the closure condition

$$
s\mathcal A=0.
$$

For a gauge parameter $\epsilon$ and an anomalous variation $\mathcal A(\epsilon)$, the same idea can be written schematically as

$$
\delta_{\epsilon_1}\mathcal A(\epsilon_2)
-
\delta_{\epsilon_2}\mathcal A(\epsilon_1)
=
\mathcal A([\epsilon_1,\epsilon_2]).
$$

The BRST version is better for local QFT because the ghost $c$ packages the gauge parameter and the Lie algebra bracket into a single nilpotent differential.

The consistency condition does not say that the anomaly vanishes. It says that any possible breaking must be compatible with the gauge algebra. This is why anomaly classification is a cohomology problem rather than a direct computation of one diagram.

## Trivial anomalies and counterterms

A breaking term is **trivial** when it is BRST-exact modulo a total derivative:

$$
a_d^1=sm_d^0+dn_{d-1}^1.
$$

Then the integrated breaking can be removed by adding the counterterm

$$
-\hbar^n\int_M m_d^0
$$

to the renormalized action or effective action at the same perturbative order. In this case the apparent anomaly was an artifact of the renormalization scheme.

A breaking term is **nontrivial** when its class in $H^{1,d}(s\mid d)$ is nonzero. Then no local counterterm can restore the identity while keeping the same field content, symmetries, locality assumptions, and perturbative expansion.

This is the precise sense in which an anomaly is an obstruction: it obstructs a simultaneous choice of locality, renormalization, and gauge symmetry.

## Descent equations

Many familiar local anomalies arise from descent. Suppose $P(F)$ is an invariant polynomial in the curvature $F$ of total degree $d+2$ in an even-dimensional gauge theory. Locally one can write

$$
P(F)=dQ_{d+1}^0(A).
$$

BRST variation gives a sequence

$$
\begin{aligned}
sQ_{d+1}^0+dQ_d^1&=0,\\
sQ_d^1+dQ_{d-1}^2&=0,\\
sQ_{d-1}^2+dQ_{d-2}^3&=0,
\end{aligned}
$$

and so on. The term $Q_d^1$ is a candidate anomaly density. It satisfies

$$
sQ_d^1+dQ_{d-1}^2=0,
$$

so it defines a class in $H^{1,d}(s\mid d)$.

For example, the four-dimensional chiral gauge anomaly is controlled by a six-form invariant polynomial. In differential-form notation one often writes the relevant polynomial as

$$
P_6(F)=\operatorname{tr}(F^3),
$$

with representation-dependent traces and normalization. The descent term $Q_4^1$ encodes the consistent gauge anomaly. The exact numerical coefficient depends on conventions for generators, traces, chirality, and fermion normalization.

:::caution[Consistent versus covariant]
The anomaly produced by the descent equations is the **consistent** anomaly: it satisfies Wess–Zumino consistency. A **covariant** anomaly transforms covariantly under gauge transformations but generally does not arise as the variation of a local effective action without adding a Bardeen–Zumino polynomial. Mixing these two is a common source of wrong signs and wrong conclusions.
:::

## The Adler–Bell–Jackiw example

The axial anomaly in four-dimensional Dirac theory is the standard first example. Classically, the axial current of a massless Dirac fermion is conserved. Quantum mechanically, in the presence of a background gauge field, the divergence receives a local curvature term.

With a common normalization for a charge-$q$ Dirac fermion, one writes schematically

$$
\partial_\mu j_5^\mu
=
2im\bar\psi\gamma^5\psi
+\frac{q^2}{16\pi^2}
\epsilon^{\mu\nu\rho\sigma}F_{\mu\nu}F_{\rho\sigma},
$$

up to convention-dependent signs. This is an anomaly in a global axial symmetry, not a gauge anomaly of electromagnetism. The gauge symmetry is kept; the axial current conservation law is not.

The lesson for gauge theory is subtler. If a chiral fermion representation produces a nonzero gauge anomaly, gauge invariance itself fails. In a consistent gauge theory, the gauge-anomaly contributions of all fermions must cancel in the relevant local cohomology class.

## Local anomaly cancellation

For ordinary four-dimensional chiral Yang–Mills theory, the perturbative gauge anomaly is controlled by symmetric invariant traces of the gauge representation. Very schematically, the dangerous cubic invariant is

$$
\operatorname{tr}_R\!
\left(T^a\{T^b,T^c\}\right),
$$

summed over left-handed fermion representations with signs for chirality. If the total invariant vanishes, the local perturbative gauge anomaly cancels.

This statement is not a replacement for the full BRST-BV classification. It is the common representation-theoretic shadow of that classification in four-dimensional semisimple Yang–Mills theory coupled to chiral fermions.

There are several caveats.

- Abelian factors have additional anomaly structures, such as mixed Abelian-non-Abelian and gravitational anomalies.
- Local anomaly cancellation does not automatically exclude global anomalies.
- Boundary conditions can turn bulk variations into boundary anomalies.
- Background fields for global symmetries turn global anomalies into precise obstruction data, but not usually into inconsistencies.

## Gauge anomalies versus 't Hooft anomalies

A pure gauge transformation is redundancy. A gauge anomaly means the redundancy cannot be imposed consistently on the quantum theory. The attempted quotient by gauge transformations fails.

A global symmetry is different. It acts on physical states or operators. A global, or 't Hooft, anomaly means the symmetry cannot be gauged as an ordinary background symmetry in the same dimension. Such an anomaly is not an inconsistency of the original theory. It is physical data that must be matched along renormalization group flows.

BRST-BV local cohomology can describe local background-field anomalies for global symmetries. But the interpretation changes: nonzero cohomology for a gauge redundancy is an obstruction to the theory, while nonzero cohomology for a global symmetry is often a diagnostic of the theory.

## What local BRST cohomology does not classify

Local BRST cohomology is powerful but not omniscient. It does not by itself classify every anomaly-like phenomenon in QFT.

**Global anomalies.** Some anomalies are invisible in infinitesimal local cohomology. They appear under large gauge transformations or from topology of determinant line bundles. The four-dimensional $SU(2)$ anomaly discovered by Witten is the standard example.

**Boundary and edge anomalies.** A bulk gauge variation can be a total derivative. On a closed spacetime this may vanish after integration; with a boundary it becomes a boundary anomaly requiring boundary degrees of freedom, boundary conditions, or anomaly inflow.

**Higher-form and generalized symmetry anomalies.** These are naturally phrased using background higher-form fields, topological terms, and extended operators. Local BRST methods are useful but not the whole language.

**Nonperturbative obstructions.** Local perturbative anomaly cancellation is necessary for many gauge theories, but it is not a nonperturbative construction of the continuum theory.

## How to use the criterion

A practical anomaly analysis usually follows this workflow.

1. Identify the intended gauge redundancy and its BRST-BV differential $s$.
2. Specify the class of local functionals and background structures allowed by locality, covariance, power counting, and symmetries.
3. Compute or classify $H^{1,d}(s\mid d)$ in that class.
4. Calculate the breaking term produced by the chosen regularization or renormalization scheme.
5. Project the breaking term to cohomology.
6. If the class vanishes, choose counterterms to restore the Ward identity.
7. If the class does not vanish, change the field content, representation content, boundary theory, or target theory.

The key point is step 5. A raw nonzero breaking term is not yet a genuine anomaly. Only its nonzero cohomology class is.

## Common pitfalls

**Calling every anomalous divergence a gauge anomaly.** The axial Adler–Bell–Jackiw anomaly is usually an anomaly of a global axial current, while gauge invariance is preserved. A gauge anomaly is a failure of redundancy and has a different status.

**Forgetting the word local.** The group $H^{1,d}(s\mid d)$ classifies local perturbative anomaly candidates. Global anomalies and boundary anomalies need more data.

**Confusing consistent and covariant anomalies.** The consistent anomaly satisfies Wess–Zumino consistency and is obtained from variation of an effective action. The covariant anomaly has cleaner covariance properties but differs by a local Bardeen–Zumino term.

**Treating a regulator artifact as a true anomaly.** A regulator can break a symmetry temporarily. The question is whether a local counterterm can restore the identity.

**Ignoring antifields.** In irreducible Yang–Mills examples one can sometimes state results without antifields. In general gauge theories the antifield dependence is essential for the correct cohomological problem.

**Assuming anomaly cancellation proves the theory exists nonperturbatively.** It removes one obstruction to a gauge theory. It does not prove existence, mass gap, confinement, or asymptotic completeness.

## Relations to other pages

This page is the obstruction-theoretic continuation of [Quantum Master Equation](/rigorous-qft/bv-brst-gauge-theory/quantum-master-equation/). It uses the local cohomology setup from [Ghosts, Antifields, and Cohomology](/rigorous-qft/bv-brst-gauge-theory/ghosts-antifields-and-cohomology/) and the observable interpretation from [Observables as Cohomology](/rigorous-qft/bv-brst-gauge-theory/observables-as-cohomology/).

The renormalized Ward-identity side is developed in [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/) and [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/). The next page, [Perturbative Yang–Mills: Rigorous View](/rigorous-qft/bv-brst-gauge-theory/perturbative-yang-mills-rigorous-view/), explains how anomaly-free Yang–Mills theory fits into a rigorous perturbative construction.

For anomalies as physical data rather than gauge-theory obstructions, use the Symmetry, Anomalies, and Topology volume.

## Research status

**Established.** Local perturbative gauge anomalies are classified by ghost-number-one BRST cohomology modulo total derivatives. Wess–Zumino consistency is the cohomological closure condition, and local counterterms shift the representative by exact terms.

**Established.** In many standard Yang–Mills theories, the local gauge-anomaly cancellation problem reduces to representation-theoretic trace constraints on chiral fermion content, together with Abelian and mixed-anomaly checks.

**Subtle.** The distinction between local anomalies, global anomalies, boundary anomalies, and background-field anomalies is essential. They are related but not identical mathematical problems.

**Open-ended.** Anomaly cancellation is not a nonperturbative construction theorem for four-dimensional gauge theory. It is a consistency condition within perturbative and local frameworks.

## Exercises

### Exercise 1: Consistency from nilpotency

Suppose a Ward operator $\mathcal S$ satisfies $\mathcal S^2=0$ at the classical level, and at the first anomalous order

$$
\mathcal S(\Gamma)=\hbar^n\mathcal A+O(\hbar^{n+1}).
$$

Show that the leading anomaly satisfies a closure condition.

<details><summary><strong>Solution</strong></summary>

Apply $\mathcal S$ to both sides. The left side gives

$$
\mathcal S^2(\Gamma)=0
$$

up to terms controlled by lower-order identities. At order $\hbar^n$, this implies

$$
s\mathcal A=0,
$$

where $s$ is the linearized classical Slavnov or BRST operator. In the local density setting this becomes

$$
sa_d^1+db_{d-1}^2=0.
$$

This is the Wess–Zumino consistency condition in cohomological form.

</details>

### Exercise 2: Counterterm shift

Let the anomalous breaking at order $\hbar^n$ be $\mathcal A=sB$. Show that adding a local counterterm proportional to $B$ removes it at that order.

<details><summary><strong>Solution</strong></summary>

Replace

$$
\Gamma\longmapsto \Gamma'=
\Gamma-\hbar^n B.
$$

Then, to order $\hbar^n$,

$$
\mathcal S(\Gamma')
=
\mathcal S(\Gamma)-\hbar^n sB+O(\hbar^{n+1}).
$$

Since $\mathcal S(\Gamma)=\hbar^n\mathcal A+O(\hbar^{n+1})$ and $\mathcal A=sB$, the order-$\hbar^n$ breaking cancels. This is why exact anomaly representatives are called trivial.

</details>

### Exercise 3: Why modulo total derivatives?

Let $a_d$ and $a_d+dn_{d-1}$ be two local $d$-form densities on a closed spacetime $M$. Explain why they define the same integrated local functional.

<details><summary><strong>Solution</strong></summary>

By Stokes' theorem,

$$
\int_M dn_{d-1}=\int_{\partial M}n_{d-1}.
$$

If $M$ has no boundary, or if boundary conditions make the boundary term vanish, then

$$
\int_M(a_d+dn_{d-1})=\int_M a_d.
$$

This is why local Lagrangian densities, anomaly densities, and counterterm densities are classified modulo total derivatives. With boundaries, the same formula shows why boundary anomalies require extra care.

</details>

## References

### Foundational anomaly references

- S. L. Adler, “Axial-Vector Vertex in Spinor Electrodynamics,” *Physical Review* **177** (1969), 2426–2438. [doi:10.1103/PhysRev.177.2426](https://doi.org/10.1103/PhysRev.177.2426).
- J. S. Bell and R. Jackiw, “A PCAC Puzzle: $\pi^0\to\gamma\gamma$ in the $\sigma$-Model,” *Il Nuovo Cimento A* **60** (1969), 47–61. [doi:10.1007/BF02823296](https://doi.org/10.1007/BF02823296).
- J. Wess and B. Zumino, “Consequences of Anomalous Ward Identities,” *Physics Letters B* **37** (1971), 95–97. [doi:10.1016/0370-2693(71)90582-X](https://doi.org/10.1016/0370-2693(71)90582-X).
- W. A. Bardeen, “Anomalous Ward Identities in Spinor Field Theories,” *Physical Review* **184** (1969), 1848–1857. [doi:10.1103/PhysRev.184.1848](https://doi.org/10.1103/PhysRev.184.1848).

### BRST-BV and cohomological references

- G. Barnich, F. Brandt, and M. Henneaux, “Local BRST Cohomology in Gauge Theories,” *Physics Reports* **338** (2000), 439–569. [arXiv:hep-th/0002245](https://arxiv.org/abs/hep-th/0002245), [doi:10.1016/S0370-1573(00)00049-1](https://doi.org/10.1016/S0370-1573(00)00049-1).
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*, Princeton University Press, 1992. [doi:10.1515/9780691213866](https://doi.org/10.1515/9780691213866).
- O. Piguet and S. P. Sorella, *Algebraic Renormalization: Perturbative Renormalization, Symmetries and Anomalies*, Springer, 1995. [doi:10.1007/978-3-540-49192-7](https://doi.org/10.1007/978-3-540-49192-7).
- J. Gomis, J. París, and S. Samuel, “Antibracket, Antifields and Gauge-Theory Quantization,” *Physics Reports* **259** (1995), 1–145. [arXiv:hep-th/9412228](https://arxiv.org/abs/hep-th/9412228), [doi:10.1016/0370-1573(94)00112-G](https://doi.org/10.1016/0370-1573(94)00112-G).

### Perturbative algebraic references

- K. Fredenhagen and K. Rejzner, “Batalin–Vilkovisky Formalism in Perturbative Algebraic Quantum Field Theory,” *Communications in Mathematical Physics* **317** (2013), 697–725. [arXiv:1110.5232](https://arxiv.org/abs/1110.5232), [doi:10.1007/s00220-012-1601-1](https://doi.org/10.1007/s00220-012-1601-1).
- R. Brunetti, M. Dütsch, and K. Fredenhagen, “Perturbative Algebraic Quantum Field Theory and the Renormalization Groups,” *Advances in Theoretical and Mathematical Physics* **13** (2009), 1541–1599. [arXiv:0901.2038](https://arxiv.org/abs/0901.2038).

## Version history

- **2026-07-01:** Initial polished draft.
