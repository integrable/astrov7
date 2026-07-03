---
title: "Global Anomalies"
description: "Explains anomalies under large gauge or symmetry transformations, determinant-line holonomy, the Witten SU(2) anomaly, and the difference between local and global anomaly tests."
sidebar:
  label: "Global Anomalies"
  order: 7
level: Advanced
status: "Polished draft"
source: "Witten SU(2) anomaly; Atiyah–Patodi–Singer; Alvarez-Gaumé and Witten; Srednicki §§75–77; Schwartz §30.5; Weinberg Vol. II; modern determinant-line and inflow viewpoints."
topics:
  - global anomaly
  - Witten anomaly
  - large gauge transformation
  - determinant line
  - eta invariant
  - mod-two index
  - anomaly inflow
  - SU(2) anomaly
canonicalTopics:
  - global-anomaly
  - witten-su2-anomaly
  - determinant-line-holonomy
  - large-gauge-anomaly
  - mod-two-index
researchStatus:
  established:
    - "Global anomalies are genuine quantum obstructions invisible to infinitesimal perturbative anomaly tests."
    - "The four-dimensional SU(2) anomaly with an odd number of Weyl doublets is the canonical example of a global gauge anomaly."
  active:
    - "The modern classification of global anomalies is naturally formulated using eta invariants, invertible field theories, cobordism, and anomaly inflow."
---

## Summary

A **global anomaly** is an anomaly that appears only when one performs a transformation that is not continuously connected to the identity, or when one moves around a nontrivial loop in the space of background fields. It is “global” in field space or topology, not global in the sense of “global symmetry.”

This terminology is treacherous, so keep the two uses separate:

| Phrase | Meaning |
|---|---|
| global symmetry anomaly | an anomaly of an ordinary physical global symmetry |
| global anomaly | an anomaly under a large transformation or around a nontrivial loop in background-field space |

A global anomaly can affect either a gauge redundancy or a physical global symmetry. If it affects a gauge redundancy, the theory is inconsistent unless the anomaly cancels. If it affects a physical global symmetry, it is a ’t Hooft anomaly: the theory exists, but the symmetry cannot be gauged in the naive way.

The classic example is Witten’s four-dimensional $SU(2)$ anomaly. A single left-handed Weyl fermion in the $SU(2)$ doublet representation has no perturbative $SU(2)^3$ gauge anomaly, because $SU(2)$ has no cubic invariant tensor. Nevertheless, the fermion path integral changes sign under a large $SU(2)$ gauge transformation:

$$
Z[A^g]=-Z[A].
$$

Since $A$ and $A^g$ are supposed to describe the same gauge field, this sign makes the gauge theory inconsistent. An even number of doublets is safe.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Global anomaly as a loop in field space. A background or gauge field A is related to A transformed by a large gauge transformation g. The loop defines a mapping torus M4 times_g S1. The fermion determinant line can have nontrivial holonomy around the loop, producing Z[A^g] different from Z[A].](/figures/symmetry-anomalies-topology/global-anomaly-large-transformation.svg)

<figcaption>

A global anomaly is detected by transporting the fermion determinant around a nontrivial loop in field space. For Witten’s $SU(2)$ anomaly, the relevant loop is built from the nontrivial element of $\pi_4(SU(2))\cong\mathbb Z_2$.

</figcaption>
</figure>

The moral is sharp: **local anomaly cancellation is necessary, but not sufficient.** Perturbative gauge anomalies test infinitesimal transformations. Global anomalies test the topology of the full background-field and gauge-transformation space.

## Prerequisites

Read [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/) first. You should also know [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/), [Spin Structures and Fermion Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/spin-structures-and-fermion-parity/), and [Anomalies of Discrete Symmetries: Preview](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/anomalies-of-discrete-symmetries-preview/).

The page uses a small amount of topology: connected components, homotopy groups, mapping tori, and the idea that a fermion determinant may define a line rather than an ordinary function.

## Core idea

A perturbative anomaly asks whether the quantum theory is invariant under infinitesimal transformations. A global anomaly asks a more subtle question:

> If we move around a closed loop of physically equivalent background fields, does the quantum partition function come back to itself?

For a bosonic classical action, the answer often looks trivially yes. For fermions, the path integral includes a determinant or Pfaffian. A determinant is not merely a number assigned independently to each background. As the background changes, the determinants form a **line bundle** over background-field space. The partition function is a section of this line bundle.

A local perturbative anomaly is the curvature of this line bundle. A global anomaly can remain even when the curvature vanishes: the line bundle may be flat but have nontrivial holonomy.

In symbols, for a loop $\gamma$ in background-field space,

$$
Z\mapsto \operatorname{Hol}_\gamma(Z).
$$

If

$$
\operatorname{Hol}_\gamma\ne1,
$$

there is a global anomaly. For a gauge redundancy, such a holonomy is unacceptable because the loop identifies physically equivalent configurations.

## Setup and conventions

Let $M_4$ be a four-dimensional spacetime manifold, and let $A$ be a gauge field. A gauge transformation $g$ acts by

$$
A\mapsto A^g.
$$

If $g$ is connected to the identity, an anomaly under $g$ is detected infinitesimally and belongs to the perturbative anomaly story.

If $g$ is not connected to the identity in the relevant configuration space, then $A$ and $A^g$ may still be gauge equivalent, but the path from $A$ to $A^g$ closes only after quotienting by gauge transformations. This closed loop can support a nontrivial fermion-determinant holonomy.

A useful geometric construction is the **mapping torus**

$$
M_5=M_4\times_g S^1.
$$

Start with $M_4\times[0,1]$ and identify

$$
(x,1)\sim(gx,0),
$$

or, for an internal gauge transformation, identify the gauge bundle at the two ends using $g$. Fermions on this five-dimensional mapping torus define an index or eta invariant that measures the anomalous phase.

For many fermionic global anomalies, the phase has the form

$$
\exp\!\left(2\pi i\,\Phi(M_5,A)\right),
$$

where $\Phi$ is an eta-invariant or mod-two index quantity. In the simplest $SU(2)$ example, the phase is just $\pm1$.

:::note[Convention-sensitive source note]
The global-anomaly phase is often written using an eta invariant, a mod-two index, or a five-dimensional invertible field theory. Different authors normalize these objects differently, especially in Euclidean signature and for real or pseudoreal fermion representations. The invariant statement is whether the exponentiated phase equals $1$ for every allowed large transformation and every allowed spacetime topology.
:::

## Witten’s SU(2) anomaly

The simplest global gauge anomaly occurs in four-dimensional $SU(2)$ gauge theory with a single left-handed Weyl fermion in the doublet representation.

There is no perturbative $SU(2)^3$ gauge anomaly. The reason is group-theoretic: $SU(2)$ has no nonzero symmetric invariant tensor $d^{abc}$, and the doublet is pseudoreal. The local triangle test says nothing is wrong.

But the fourth homotopy group of $SU(2)$ is

$$
\pi_4(SU(2))\cong\mathbb Z_2.
$$

Thus there is a nontrivial class of large gauge transformations on a four-dimensional spacetime such as $S^4$. Under the nontrivial transformation $g$, the Weyl fermion Pfaffian changes sign:

$$
\operatorname{Pf}(D_{A^g})=-\operatorname{Pf}(D_A).
$$

Consequently

$$
Z[A^g]=-Z[A].
$$

For a gauge theory this is impossible: $A$ and $A^g$ are the same gauge configuration. The theory cannot be defined with one Weyl doublet.

With two doublets, both Pfaffians change sign, so the total sign is

$$
(-1)^2=+1.
$$

The cancellation rule for ordinary doublets is therefore

$$
N_{\text{doublets}}\equiv0\pmod 2.
$$

This is the four-dimensional $SU(2)$ global anomaly.

## Standard Model check

One Standard Model generation contains the following $SU(2)_L$ doublets:

- three quark doublets, one for each color;
- one lepton doublet.

So per generation,

$$
N_{SU(2)\text{ doublets}}=3+1=4.
$$

This is even, so Witten’s $SU(2)$ global anomaly cancels. With three generations, the number is $12$, still even.

This is logically separate from the perturbative anomaly cancellation checks on the previous page. The Standard Model passes both the local triangle-anomaly tests and the global $SU(2)$ test.

## More general SU(2) representations

The doublet is the most common example, but the $SU(2)$ global anomaly has a more general representation-theoretic form.

Let a Weyl fermion transform in isospin $j$, so the representation has dimension $2j+1$. Its contribution to the mod-two anomaly is controlled by

$$
2T(j)=\frac{2}{3}j(j+1)(2j+1),
$$

where $T(j)$ is the quadratic index normalized so that the doublet has $T(1/2)=1/2$.

The representation contributes nontrivially when

$$
2T(j)\equiv1\pmod2.
$$

Thus $j=1/2$ contributes, $j=3/2$ does not, $j=5/2$ contributes, and so on. For most particle-physics applications, counting doublets is enough, but the index formula is the correct general principle.

## Determinant lines and holonomy

The determinant-line viewpoint is the clean conceptual home of global anomalies.

For each background field $A$, the fermion path integral formally gives

$$
Z_\mathrm{fermion}[A]=\det D_A
$$

or, for a Weyl or Majorana-type fermion,

$$
Z_\mathrm{fermion}[A]=\operatorname{Pf}(D_A).
$$

But $\det D_A$ is not always a globally defined complex-valued function on background-field space. Instead, as $A$ varies, these determinants form a line bundle

$$
\mathcal L\to\mathcal B,
$$

where $\mathcal B$ is the space of background fields modulo gauge transformations.

A local anomaly means the determinant line has nonzero curvature. A global anomaly means that even if the curvature is zero, parallel transport around a closed loop can produce a nontrivial phase:

$$
\operatorname{Hol}_\gamma(\mathcal L)\ne1.
$$

For Witten’s $SU(2)$ anomaly, the holonomy is $-1$ around the nontrivial loop. This is why no local counterterm can fix it: a local counterterm can change local connection data, but it cannot erase a topologically nontrivial holonomy unless the relevant anomaly class is trivial.

## Relation to anomaly inflow

Modern anomaly language often phrases both perturbative and global anomalies through **anomaly inflow**.

A $d$-dimensional anomalous theory can be viewed as the boundary of an invertible $(d+1)$-dimensional theory. Under a background transformation, the boundary partition function changes by a phase. The bulk partition function changes by the inverse phase. The combined bulk–boundary system is invariant:

$$
Z_{\partial}(A^g)Z_{\mathrm{bulk}}(A^g)
=Z_{\partial}(A)Z_{\mathrm{bulk}}(A).
$$

For perturbative anomalies, the bulk action is often written using Chern–Simons forms and descent from an anomaly polynomial. For global anomalies, the bulk action may be expressed using eta invariants, mod-two indices, or cobordism invariants.

This inflow viewpoint is powerful because it treats continuous, discrete, perturbative, global, bosonic, and fermionic anomalies in one conceptual language.

## Parity anomaly as a large-gauge example

A closely related phenomenon occurs in three-dimensional gauge theories with fermions. A massive Dirac fermion in three dimensions induces a Chern–Simons term at half-integer level. But gauge invariance under large gauge transformations requires the total Chern–Simons level to be properly quantized.

This creates the **parity anomaly**: one cannot simultaneously preserve time-reversal or parity and large-gauge invariance for an odd number of suitable three-dimensional fermions.

The parity anomaly is often introduced in condensed matter, Chern–Simons theory, and boundary-state physics. It is not identical to Witten’s four-dimensional $SU(2)$ anomaly, but it teaches the same lesson: large gauge transformations can impose quantum consistency conditions that are invisible in a naive local Lagrangian.

## Global gravitational anomalies

Gauge fields are not the only backgrounds that can have global anomalies. The metric, spin structure, and Pin structure can also produce global anomaly phases.

For example, chiral fermions or self-dual fields in certain dimensions can have gravitational anomalies. Some are perturbative and detected by local curvature polynomials. Others are global and detected by eta invariants on mapping tori.

The general question is:

> Does the partition function return to itself under large diffeomorphisms or changes of geometric structure that should be regarded as redundancies?

If not, the theory has a global gravitational anomaly. For a theory coupled to dynamical gravity, this is a consistency obstruction. For an ordinary QFT on a fixed spacetime, it is an anomaly in the corresponding spacetime symmetry background.

## Local versus global anomaly tests

The distinction can be summarized as follows.

| Feature | Perturbative anomaly | Global anomaly |
|---|---|---|
| Transformation tested | Infinitesimal | Large or topologically nontrivial |
| Typical detector | Triangle diagram, descent | Mapping torus, eta invariant, mod-two index |
| Local expression | Yes | Not necessarily |
| Counterterm question | Local counterterms | Topological phases and holonomy |
| Example | $U(1)^3$ anomaly | Witten $SU(2)$ anomaly |

A theory must pass both tests before a symmetry can be gauged. For a dynamical gauge group, both tests are consistency conditions.

## Common pitfalls

**Pitfall 1: Thinking “global anomaly” means anomaly of a global symmetry.**  It does not. A global anomaly is an anomaly visible only through global topology of transformations or background-field space. It may involve a gauge redundancy.

**Pitfall 2: Assuming zero triangle anomaly is enough.**  Witten’s $SU(2)$ example is precisely a theory with zero perturbative gauge anomaly and a nonzero global gauge anomaly.

**Pitfall 3: Looking for a local anomalous divergence.**  A global anomaly may not appear as a local equation like $D_\mu J^\mu=F\widetilde F$. It can appear only as a sign or phase after moving around a large loop.

**Pitfall 4: Ignoring spin and Pin data.**  Fermionic global anomalies often depend on spin or Pin structures. A statement that is true on oriented spin manifolds may change once reflections, time reversal, or unorientable manifolds are allowed.

**Pitfall 5: Treating the anomaly phase before exponentiation.**  The physical partition function sees an exponentiated phase. Different formulas for eta invariants or Chern–Simons actions may differ by integers but define the same phase.

## Relations to other pages

[Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/) gives the local anomaly tests that must be checked first. [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/) explains the large transformations that make global anomalies possible.

[Spin Structures and Fermion Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/spin-structures-and-fermion-parity/) explains why fermionic theories require geometric data beyond the metric. [Anomalies of Discrete Symmetries: Preview](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/anomalies-of-discrete-symmetries-preview/) introduces closely related finite and antiunitary anomaly phenomena.

[Anomaly Inflow](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/) and [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) will place global anomalies in the modern bulk-boundary language.

## Research status

The classic examples of global anomalies, including the four-dimensional $SU(2)$ anomaly and many gravitational anomalies, are established. Their modern formulation has become much more systematic. Instead of treating each anomaly as an isolated surprise, one can study anomaly theories as invertible field theories in one higher dimension.

The active frontier lies in classification and application: fermionic anomalies, crystalline and reflection anomalies, higher-form and non-invertible symmetry anomalies, anomalies on non-spin manifolds, and the precise relation between anomaly inflow, cobordism, and symmetry TFT.

## Exercises

### Exercise 1: Standard Model SU(2) global anomaly

Count the number of $SU(2)_L$ Weyl doublets in one Standard Model generation and check Witten’s anomaly condition.

<details><summary><strong>Solution</strong></summary>

Each quark doublet $Q=(u_L,d_L)$ is an $SU(2)_L$ doublet, and there are three color copies. This gives $3$ doublets. The lepton doublet $L=(\nu_L,e_L)$ gives one more. Therefore

$$
N_{\text{doublets}}=3+1=4.
$$

Since

$$
4\equiv0\pmod2,
$$

Witten’s $SU(2)$ global anomaly cancels in one generation.

</details>

### Exercise 2: Why the triangle test misses the SU(2) anomaly

Explain why the perturbative anomaly tensor does not detect the four-dimensional $SU(2)$ anomaly.

<details><summary><strong>Solution</strong></summary>

The perturbative anomaly tensor is

$$
\mathcal A^{abc}=\sum_i\operatorname{tr}_{R_i}(T^a\{T^b,T^c\}).
$$

It detects local anomalies under infinitesimal gauge transformations. For $SU(2)$, there is no nonzero symmetric invariant tensor $d^{abc}$, and the doublet is pseudoreal, so this local cubic tensor vanishes.

Witten’s anomaly is instead associated with

$$
\pi_4(SU(2))\cong\mathbb Z_2.
$$

It is a sign under a large gauge transformation, not a local anomalous divergence. Therefore the triangle test misses it.

</details>

### Exercise 3: Two doublets

Suppose a four-dimensional $SU(2)$ gauge theory contains two left-handed Weyl doublets. What happens under the nontrivial large gauge transformation?

<details><summary><strong>Solution</strong></summary>

Each doublet contributes a sign

$$
Z_i[A^g]=-Z_i[A]
$$

under the nontrivial transformation. For two doublets, the total fermion factor transforms as

$$
Z_1[A^g]Z_2[A^g]
=(-Z_1[A])(-Z_2[A])
=Z_1[A]Z_2[A].
$$

The signs cancel. Thus two doublets have no Witten $SU(2)$ global anomaly.

</details>

### Exercise 4: Curvature versus holonomy

Use the analogy of a flat $U(1)$ connection on a circle to explain how a global anomaly can remain even when the perturbative anomaly vanishes.

<details><summary><strong>Solution</strong></summary>

A connection on a line bundle can have zero curvature but nontrivial holonomy around a noncontractible loop. For example, a flat $U(1)$ connection on a circle may have holonomy

$$
\exp(i\theta)
$$

around the circle even though its curvature is zero.

Similarly, a perturbative anomaly is like curvature of the determinant line over background-field space. If the perturbative anomaly vanishes, the curvature can be zero. But the determinant line can still have nontrivial holonomy around a noncontractible loop. That holonomy is a global anomaly.

</details>

## References

- E. Witten, “An $SU(2)$ Anomaly,” *Physics Letters B* **117** (1982).
- M. F. Atiyah, V. K. Patodi, and I. M. Singer, “Spectral Asymmetry and Riemannian Geometry,” *Mathematical Proceedings of the Cambridge Philosophical Society* **77–79** (1975–1976).
- L. Alvarez-Gaumé and E. Witten, “Gravitational Anomalies,” *Nuclear Physics B* **234** (1984).
- L. Alvarez-Gaumé and P. Ginsparg, “The Structure of Gauge and Gravitational Anomalies,” *Annals of Physics* **161** (1985).
- D. S. Freed, “Determinants, Torsion, and Strings,” *Communications in Mathematical Physics* **107** (1986).
- M. Srednicki, *Quantum Field Theory*, §§75–77.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, §30.5.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, anomaly and gauge-theory chapters.

## Version history

- 2026-06-18: First polished draft. Covers global anomaly definition, determinant-line holonomy, mapping tori, Witten’s $SU(2)$ anomaly, Standard Model check, relation to inflow, parity anomaly orientation, and exercises.
