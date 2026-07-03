---
title: "Gravitational Anomalies"
description: "Explains diffeomorphism, local Lorentz, and gravitational anomaly inflow, with the anomaly-polynomial viewpoint and the distinction from trace anomalies."
sidebar:
  label: "Gravitational Anomalies"
  order: 8
level: Advanced
status: "Polished draft"
source: "Alvarez-Gaumé and Witten; Witten global gravitational anomalies; Atiyah–Singer and Atiyah–Patodi–Singer; Srednicki §§75–77; Schwartz Ch. 30; Weinberg Vol. II; modern anomaly-polynomial and inflow viewpoints."
topics:
  - gravitational anomaly
  - diffeomorphism anomaly
  - local Lorentz anomaly
  - trace anomaly
  - anomaly polynomial
  - descent equations
  - anomaly inflow
  - chiral central charge
canonicalTopics:
  - gravitational-anomaly
  - diffeomorphism-anomaly
  - local-lorentz-anomaly
  - anomaly-polynomial
  - gravitational-inflow
researchStatus:
  established:
    - "Perturbative pure gravitational anomalies are local obstructions to diffeomorphism or local Lorentz invariance and occur only in spacetime dimensions 2 mod 4."
    - "The anomaly-polynomial and descent formalism gives a compact, convention-controlled way to compute local gravitational and mixed gauge-gravitational anomalies."
  active:
    - "Global gravitational anomalies and modern classifications of fermionic anomalies are naturally expressed using eta invariants, invertible field theories, and cobordism."
---

## Summary

A **gravitational anomaly** is an anomaly in a spacetime gauge redundancy: diffeomorphism invariance, local Lorentz invariance, or both. It says that the quantum theory cannot be consistently coupled to arbitrary background geometry while keeping the relevant spacetime redundancy exact.

In a background metric, the diagnostic is the stress tensor. A diffeomorphism anomaly appears as

$$
\nabla_\mu \langle T^\mu{}_{\nu}\rangle=\mathcal A^{\rm diff}_{\nu},
$$

rather than the expected covariant conservation law. In a vielbein formalism, a local Lorentz anomaly can also appear as an antisymmetric stress tensor,

$$
\langle T^{ab}-T^{ba}\rangle=\mathcal A^{ab}_{\rm Lorentz}.
$$

These are not ordinary failures of energy conservation. They are failures of the redundancy needed to remove unphysical metric or vielbein polarizations.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Flowchart from chiral QFT on a curved background to the gravitational anomaly polynomial, descent equations, anomalous Ward identity, and bulk inflow. A side branch warns not to confuse gravitational anomalies with Weyl or trace anomalies.](/figures/symmetry-anomalies-topology/gravitational-anomaly-descent.svg)

<figcaption>

Local gravitational anomalies are most cleanly organized by the anomaly polynomial and descent. The same descent data may be read either as an anomalous Ward identity on $M_d$ or as inflow from a bulk term on $X_{d+1}$ with $\partial X_{d+1}=M_d$.

</figcaption>
</figure>

The word “gravitational” is unfortunately used near another anomaly: the Weyl or trace anomaly. A trace anomaly means

$$
\langle T^\mu{}_{\mu}\rangle\ne0.
$$

That is a failure of Weyl invariance, not a failure of diffeomorphism invariance. Trace anomalies are extremely important, but they do not by themselves make coupling to a background metric inconsistent. A genuine diffeomorphism or local Lorentz anomaly does.

## Prerequisites

Read [What Is an Anomaly?](/symmetry-anomalies-topology/anomalies/what-is-an-anomaly/), [Chiral Anomaly](/symmetry-anomalies-topology/anomalies/chiral-anomaly/), [Fujikawa Method](/symmetry-anomalies-topology/anomalies/fujikawa-method/), [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), and [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/) first.

You should also know the idea of coupling a QFT to a background metric,

$$
\delta W[g]=\frac{1}{2}\int d^dx\sqrt{|g|}\,\langle T^{\mu\nu}\rangle\delta g_{\mu\nu},
$$

and the background-field principle: an anomaly is detected by asking whether the generating functional can be made invariant under background gauge transformations.

## Core idea

The stress tensor is the current for spacetime translations and, after coupling to a metric, the source response to $g_{\mu\nu}$. If the theory is invariant under infinitesimal diffeomorphisms, then the variation of the generating functional under

$$
\delta_\xi g_{\mu\nu}=\nabla_\mu\xi_\nu+\nabla_\nu\xi_\mu
$$

vanishes. Integrating by parts gives

$$
0=\delta_\xi W[g]
=-\int d^dx\sqrt{|g|}\,\xi_\nu\nabla_\mu\langle T^{\mu\nu}\rangle.
$$

Since $\xi_\nu$ is arbitrary, one obtains

$$
\nabla_\mu\langle T^{\mu\nu}\rangle=0.
$$

A gravitational anomaly says that no regulator and no allowed local counterterm can make this statement true for all background geometries. Instead,

$$
\delta_\xi W[g]
=\int_{M_d} \mathcal I^{(1)}_d(\xi,g),
$$

or equivalently

$$
\nabla_\mu\langle T^{\mu}{}_{\nu}\rangle=\mathcal A^{\rm diff}_{\nu}(g).
$$

For a dynamical gravitational theory, this is fatal unless it cancels. For a QFT placed on a fixed background metric, it means the theory is anomalous as a theory with spacetime symmetry; it can often be interpreted as living on the boundary of a higher-dimensional invertible theory.

## Setup and conventions

The default spacetime convention is mostly-minus in Lorentzian signature, with Wick rotation handled explicitly when needed. For anomaly polynomials it is usually cleaner to use Euclidean differential-form notation. We write $R^a{}_b$ for the curvature two-form of the spin connection,

$$
R^a{}_b=d\omega^a{}_b+\omega^a{}_c\wedge\omega^c{}_b.
$$

Pontryagin classes are built from traces of powers of $R$. A common convention is

$$
p_1(T)=-\frac{1}{8\pi^2}\operatorname{tr}R\wedge R,
$$

where $\operatorname{tr}$ is over tangent-space indices. Some books absorb signs or factors of $2\pi$ into $R$. The sign of formulas below can therefore flip when comparing references; the invariant statements are the anomaly class, cancellation condition, and exponentiated inflow phase.

For a chiral spin-$1/2$ fermion in $d=2n$ dimensions, the local anomaly is encoded by the degree-$(2n+2)$ part of

$$
I_{2n+2}=\left[\widehat A(T)\,\operatorname{ch}_{\mathcal R}(F)\right]_{2n+2},
$$

with a sign depending on chirality. Here $\widehat A(T)$ is the A-roof genus,

$$
\widehat A(T)=1-\frac{p_1(T)}{24}+\frac{7p_1(T)^2-4p_2(T)}{5760}+\cdots,
$$

and $\operatorname{ch}_{\mathcal R}(F)$ is the Chern character for any internal background gauge field. The purely gravitational part is obtained by setting $F=0$.

:::note[Convention-sensitive source note]
Many anomaly references use Euclidean signature, anti-Hermitian connections, and curvature forms normalized as $R/2\pi$. Others use Hermitian gauge fields and Lorentzian conventions. When comparing coefficients, first translate the definitions of $p_1(T)$, $\operatorname{tr}R^2$, chirality, and the phase $e^{iW}$ versus $e^{-W_E}$. Do not compare a bare coefficient in isolation.
:::

## Diffeomorphism, Lorentz, and Weyl anomalies

There are three closely related but distinct geometric variations.

| Transformation | Background variation | Possible anomaly | Ward identity |
|---|---|---|---|
| Diffeomorphism | $\delta_\xi g_{\mu\nu}=\nabla_\mu\xi_\nu+\nabla_\nu\xi_\mu$ | gravitational or Einstein anomaly | $\nabla_\mu T^\mu{}_{\nu}=\mathcal A^{\rm diff}_{\nu}$ |
| Local Lorentz | $\delta_\lambda e^a{}_{\mu}=\lambda^a{}_b e^b{}_{\mu}$ | Lorentz anomaly | $T^{[ab]}=\mathcal A^{ab}_{\rm Lorentz}$ |
| Weyl | $\delta_\sigma g_{\mu\nu}=2\sigma g_{\mu\nu}$ | trace anomaly | $T^\mu{}_{\mu}=\mathcal A_{\rm Weyl}$ |

The first two are gauge redundancies of the geometric description. In a vielbein formalism they can trade places: by adding local counterterms, one can often shift anomaly between diffeomorphism and local Lorentz Ward identities. What cannot be removed is the total cohomology class.

The Weyl anomaly is different. Diffeomorphism invariance may remain exact while Weyl invariance fails. For example, an ordinary two-dimensional nonchiral CFT with $c_L=c_R=c$ has no diffeomorphism gravitational anomaly, but it has a trace anomaly proportional to $cR$.

A nice slogan is:

$$
\text{gravitational anomaly} \ne \text{trace anomaly}.
$$

Both involve the stress tensor. Only the former obstructs background diffeomorphism or local Lorentz invariance.

## Why pure local gravitational anomalies occur in dimensions 2 mod 4

The anomaly polynomial for a $d$-dimensional theory is a $(d+2)$-form. A purely gravitational polynomial is built from Pontryagin classes,

$$
p_i(T)\in H^{4i}(M),
$$

so it has degree divisible by $4$. Therefore a purely gravitational local anomaly can exist only when

$$
d+2=4(k+1),
$$

or

$$
d=4k+2.
$$

Thus purely gravitational perturbative anomalies occur in

$$
d=2,6,10,\ldots.
$$

This is why two-dimensional chiral CFTs, six-dimensional chiral theories, and ten-dimensional chiral supergravity or string constructions are gravitational-anomaly hotspots.

Mixed gauge-gravitational anomalies obey different dimensional rules because the anomaly polynomial may contain both gauge Chern classes and gravitational Pontryagin classes. Four-dimensional $U(1)$-gravity-gravity anomalies are the canonical example and are treated on the next page.

## The descent formalism

Let $I_{d+2}$ be the anomaly polynomial. Locally, it can be written as an exterior derivative,

$$
I_{d+2}=dI_{d+1}^{(0)}.
$$

Under an infinitesimal gauge, Lorentz, or diffeomorphism transformation,

$$
\delta I_{d+1}^{(0)}=dI_d^{(1)}.
$$

Then the anomalous variation of the $d$-dimensional effective action is

$$
\delta W=2\pi i\int_{M_d} I_d^{(1)}.
$$

This is the Stora–Zumino descent story. It is powerful because it packages many Feynman-diagram Ward-identity failures into a single characteristic class.

For a gravitational anomaly, $I_{d+1}^{(0)}$ is a gravitational Chern–Simons form. Schematically,

$$
d\,\operatorname{CS}_{4k-1}(\omega)=\operatorname{tr}R^{2k}+\cdots.
$$

If the anomalous theory lives on $M_d=\partial X_{d+1}$, a bulk term

$$
S_{\rm inflow}=2\pi i\int_{X_{d+1}}I_{d+1}^{(0)}
$$

has a boundary variation that cancels the anomaly:

$$
\delta S_{\rm inflow}=-\delta W_{M_d}.
$$

This is gravitational anomaly inflow.

## Two-dimensional benchmark

In two dimensions, a chiral theory can have different left- and right-moving central charges. The diffeomorphism anomaly is controlled by the **chiral central charge**

$$
c_-\equiv c_R-c_L.
$$

With a common covariant normalization,

$$
\nabla_\mu\langle T^\mu{}_{\nu}\rangle
=\frac{c_R-c_L}{96\pi}\,\epsilon_{\nu\rho}\partial^\rho R.
$$

The same theory has a trace anomaly controlled by the total central charge,

$$
\langle T^\mu{}_{\mu}\rangle
=-\frac{c_L+c_R}{48\pi}R
$$

in one common Lorentzian convention. Some CFT references write the trace anomaly as $-cR/(24\pi)$ for a nonchiral theory with $c_L=c_R=c$; this is the same statement after translating the definition of $c$ and stress-tensor normalization.

The important separation is

$$
\begin{aligned}
\text{diffeomorphism anomaly} &\sim c_R-c_L,\\
\text{trace anomaly} &\sim c_R+c_L.
\end{aligned}
$$

A nonchiral CFT has $c_R=c_L$, so its diffeomorphism anomaly cancels even though the trace anomaly remains.

A single right-moving complex Weyl fermion has $c_R=1$ and $c_L=0$. It has a gravitational anomaly. A full nonchiral Dirac fermion has $c_R=c_L=1$, so its gravitational anomaly cancels.

:::note[Convention-sensitive source note]
The coefficient $1/(96\pi)$ is the covariant gravitational-anomaly coefficient in a common two-dimensional convention. Consistent anomalies, covariant anomalies, Euclidean conventions, and opposite definitions of $\epsilon^{\mu\nu}$ shift signs and factors of two. The physical invariant is the chiral central charge $c_R-c_L$.
:::

## Six-dimensional and ten-dimensional importance

The next pure gravitational anomaly dimensions are $d=6$ and $d=10$. These dimensions matter because many chiral theories live there.

In six dimensions, Weyl fermions, gravitinos, and self-dual or anti-self-dual tensor fields can all contribute. The anomaly polynomial is an eight-form involving

$$
p_1(T)^2,\qquad p_2(T),
$$

as well as possible gauge terms. Six-dimensional supersymmetric theories are therefore tightly constrained by anomaly cancellation and factorization.

In ten dimensions, anomaly cancellation is one of the central consistency conditions of chiral supergravity and superstring constructions. The relevant polynomial is a twelve-form. In favorable cases it factorizes in a way that allows Green–Schwarz inflow or Green–Schwarz cancellation.

The conceptual lesson is not dimension-specific: high-dimensional chiral theories often exist only because gauge, gravitational, and mixed terms conspire to cancel.

## Fermions, self-dual fields, and gravitinos

Spin-$1/2$ Weyl fermions are the easiest anomaly source, but not the only one.

A chiral spin-$3/2$ field, such as a gravitino, contributes a different gravitational anomaly polynomial. A self-dual tensor field in dimension $4k+2$ also contributes. These fields appear naturally in supersymmetric theories.

For a chiral spin-$1/2$ fermion, the gravitational polynomial is built from the A-roof genus $\widehat A(T)$. For a self-dual field, the polynomial is related instead to the Hirzebruch $L$-genus. For a gravitino, one combines spinor and vector bundle data.

The details belong to anomaly-polynomial tables, but the structural message belongs here:

$$
\text{total anomaly polynomial}=	ext{sum over all chiral species}.
$$

A consistent theory requires the dangerous gauge-redundancy part of this total class to vanish or be canceled by an allowed inflow mechanism.

## Gravitational anomalies and dynamical gravity

If the metric is merely a background source, a gravitational anomaly means the theory is anomalous as a theory with spacetime symmetry. It may still be meaningful as a boundary theory.

If the metric is dynamical, diffeomorphism invariance is a gauge redundancy. Then a gravitational anomaly usually destroys consistency. The reason is parallel to gauge anomalies:

- the redundant modes of the metric or vielbein fail to decouple;
- the gravitational constraints are anomalous;
- the physical Hilbert space cannot be defined in the usual way;
- unitarity or locality is endangered.

So the rule is severe:

$$
\text{dynamical gravity requires gravitational-anomaly cancellation.}
$$

This is one reason anomaly cancellation is so central in string theory and higher-dimensional supergravity.

## Global gravitational anomalies

This page focuses on local perturbative gravitational anomalies. There is also a global version.

A **global gravitational anomaly** appears under a large diffeomorphism or a nontrivial loop in the space of metrics and spin structures. The local anomaly polynomial may vanish, yet the fermion determinant line can have nontrivial holonomy.

The typical diagnostic is a mapping torus. Given a $d$-manifold $M_d$ and a large diffeomorphism $\varphi$, form

$$
M_{d+1}=M_d\times_\varphi S^1.
$$

The anomalous phase is expressed using an eta invariant or an index-theoretic quantity on $M_{d+1}$ or on a bounding manifold. This is the gravitational analogue of the global gauge anomalies discussed in [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/).

The modern view packages such anomalies as invertible field theories one dimension higher.

## Common pitfalls

**Calling the trace anomaly a gravitational anomaly.**  The trace anomaly involves background curvature and the stress tensor, but it is a Weyl anomaly. A gravitational anomaly, in the strict sense of this page, violates diffeomorphism or local Lorentz invariance.

**Expecting pure gravitational anomalies in four dimensions.**  Pure local gravitational anomalies require $d=4k+2$. Four-dimensional theories can have mixed gauge-gravitational anomalies, but not pure perturbative gravitational anomalies.

**Ignoring chirality.**  Vectorlike pairs cancel gravitational anomalies. Chiral matter is the danger.

**Comparing coefficients without translating conventions.**  Signs and factors of $2\pi$ depend on curvature normalization, chirality convention, and Euclidean versus Lorentzian phase convention.

**Assuming local cancellation implies global cancellation.**  Local anomaly polynomials detect perturbative anomalies. Global gravitational anomalies require separate topology-sensitive checks.

## Relations to other pages

- [Mixed Anomalies](/symmetry-anomalies-topology/anomalies/mixed-anomalies/) explains gauge-gravity and multi-symmetry anomalies.
- [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/) develops the characteristic-class formalism systematically.
- [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/) derives the descent chain used above.
- [Trace Anomaly](/symmetry-anomalies-topology/anomalies/trace-anomaly/) treats Weyl anomalies without confusing them with diffeomorphism anomalies.
- [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/) explains the boundary-of-a-bulk interpretation.
- [Spin Structures and Fermion Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/spin-structures-and-fermion-parity/) explains why fermionic anomalies depend on spin or Pin data.

## Research status

The local perturbative theory of gravitational anomalies is established. The anomaly-polynomial, index-theoretic, and descent descriptions are standard tools.

The active and more sophisticated frontier is global: how to classify all possible gravitational, fermionic, time-reversal, reflection, and higher-symmetry anomalies of QFTs with general tangential structures. The natural language uses invertible field theories, eta invariants, cobordism, and extended TQFT. For many practical QFT calculations, however, the local anomaly polynomial remains the workhorse.

## Exercises

### Exercise 1: Why no pure local gravitational anomaly in four dimensions?

Use degree counting of Pontryagin classes to explain why a pure local gravitational anomaly cannot occur in $d=4$.

<details><summary><strong>Solution</strong></summary>

A local anomaly in $d$ dimensions is encoded by a $(d+2)$-form polynomial. A pure gravitational polynomial is built from Pontryagin classes $p_i(T)$, each of degree $4i$. Therefore the total degree must be divisible by $4$.

For $d=4$, the anomaly polynomial would have degree $6$. There is no purely gravitational characteristic class of degree $6$ built from Pontryagin classes. Hence there is no pure perturbative gravitational anomaly in four dimensions.

This does not exclude mixed gauge-gravitational anomalies, because gauge Chern classes can have degree $2$.

</details>

### Exercise 2: Chiral central charge

A two-dimensional theory has $c_L=5$ and $c_R=2$. Does it have a diffeomorphism gravitational anomaly? Does it have a trace anomaly?

<details><summary><strong>Solution</strong></summary>

The diffeomorphism gravitational anomaly is controlled by

$$
c_R-c_L=2-5=-3.
$$

Since this is nonzero, the theory has a gravitational anomaly.

The trace anomaly is controlled by

$$
c_L+c_R=7,
$$

so the trace anomaly is also nonzero. These are different anomalies: the first is chiral and obstructs diffeomorphism invariance; the second is a Weyl anomaly.

</details>

### Exercise 3: Dirac versus Weyl in two dimensions

A right-moving complex Weyl fermion has $c_R=1$, $c_L=0$. A nonchiral Dirac fermion has one right-moving and one left-moving complex fermion. Which theory has a gravitational anomaly?

<details><summary><strong>Solution</strong></summary>

For the right-moving Weyl fermion,

$$
c_R-c_L=1,
$$

so it has a gravitational anomaly.

For the nonchiral Dirac fermion,

$$
c_R=c_L=1,
$$

so

$$
c_R-c_L=0.
$$

The gravitational anomaly cancels. The nonchiral Dirac theory can still have a trace anomaly if it is conformal and coupled to curved background geometry, but it has no diffeomorphism gravitational anomaly.

</details>

### Exercise 4: What counterterms can and cannot do

Suppose a theory written in vielbein variables has both a diffeomorphism Ward identity and a local Lorentz Ward identity. Explain why a local counterterm may move an anomaly between these two Ward identities without making the theory anomaly-free.

<details><summary><strong>Solution</strong></summary>

The diffeomorphism and local Lorentz transformations are different descriptions of redundancies of the same geometric coupling. Local counterterms change the definition of the effective action by a local functional of the background fields. Such a change modifies the representative of the anomaly in the descent complex.

Therefore it can change which Ward identity displays the anomaly. This is like changing from one representative of a cohomology class to another. But if the anomaly class itself is nonzero, no local counterterm removes it from all Ward identities simultaneously. The invariant data are the anomaly class and the exponentiated inflow phase, not the particular representative.

</details>

## References

- L. Alvarez-Gaumé and E. Witten, “Gravitational Anomalies,” *Nuclear Physics B* **234** (1984).
- E. Witten, “Global Gravitational Anomalies,” *Communications in Mathematical Physics* **100** (1985).
- M. Srednicki, *Quantum Field Theory*, sections on chiral anomalies and fermion path integrals.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Chapter 30.
- S. Weinberg, *The Quantum Theory of Fields*, Volume II, chapters on gauge theories and anomalies.
- R. A. Bertlmann, *Anomalies in Quantum Field Theory*.
- D. S. Freed, “Anomalies and Invertible Field Theories.”

## Version history

- 2026-06-18: First polished draft. Added anomaly-polynomial setup, two-dimensional benchmark, distinction from trace anomalies, inflow interpretation, and exercises.
