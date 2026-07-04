---
title: "Perturbative Yang–Mills: Rigorous View"
description: "Explains what is rigorous in perturbative Yang–Mills theory: formal power series, BV-BRST cohomology, renormalized products, Ward identities, and the limits of the result."
sidebar:
  label: "Perturbative Yang–Mills"
  order: 10
level: Advanced
status: "Polished draft"
source: "Faddeev–Popov; BRST; Batalin–Vilkovisky; Hollands; Fredenhagen–Rejzner; perturbative algebraic QFT"
topics:
  - Yang-Mills theory
  - perturbative algebraic QFT
  - BRST cohomology
  - BV formalism
  - renormalized observables
canonicalTopics:
  - perturbative-yang-mills
  - yang-mills-bv
  - brst-cohomology
  - perturbative-algebraic-qft
  - gauge-theory-renormalization
researchStatus:
  established:
    - "Perturbative Yang–Mills theory can be formulated rigorously as a renormalized formal power series theory with auxiliary ghosts, antifields, Ward identities, and physical observables given by BRST cohomology under suitable hypotheses."
  active:
    - "This perturbative construction does not solve nonperturbative Yang–Mills existence, the mass gap, confinement, asymptotic completeness, or construction of a continuum probability measure for four-dimensional non-Abelian gauge theory."
---

## Summary

Perturbative Yang–Mills theory is one of the best-understood interacting gauge theories in QFT, but “understood” has a precise meaning here. In a rigorous perturbative approach, one constructs renormalized observables, products, and Ward identities **order by order** in a formal coupling parameter. The output is not a convergent path integral measure. It is an algebraic and microlocal construction of interacting fields as formal power series.

For a compact Lie group $G$ with Lie algebra $\mathfrak g$, the classical Yang–Mills action in QFT.org mostly-minus conventions is

$$
S_{\mathrm{YM}}[A]
=-\frac14\int_M d^dx\,
F^a_{\mu\nu}F_a^{\mu\nu},
$$

where

$$
F_{\mu\nu}
=\partial_\mu A_\nu-\partial_\nu A_\mu+[A_\mu,A_\nu].
$$

Gauge symmetry makes the quadratic operator non-invertible. A rigorous perturbative construction therefore does not quantize $A_\mu$ alone. It first passes through the BRST-BV auxiliary system of fields, ghosts, antighosts, auxiliary fields, and antifields. Physical observables are recovered as cohomology.

A compact slogan is

$$
\text{perturbative Yang--Mills}
=
H^0\!\left(
\text{renormalized auxiliary BRST-BV algebra}[[g]],
Q_{\mathrm{int}}
\right).
$$

The theorem-level object is an algebra of formal power series satisfying locality, covariance, causal factorization, microlocal spectral conditions, and renormalized Ward identities. It does not by itself prove that four-dimensional pure Yang–Mills theory exists nonperturbatively with a mass gap.

:::caution[Status]
This page is about **rigorous perturbation theory**. It is not the Clay Yang–Mills existence and mass gap problem, not lattice continuum-limit construction, and not a proof of confinement.
:::

## Prerequisites

Read [Gauge Symmetry as Redundancy](/rigorous-qft/bv-brst-gauge-theory/gauge-symmetry-as-redundancy-rigorous-view/), [BRST Complex](/rigorous-qft/bv-brst-gauge-theory/brst-complex/), [BV Formalism](/rigorous-qft/bv-brst-gauge-theory/bv-formalism/), [Gauge Fixing as a Lagrangian Submanifold](/rigorous-qft/bv-brst-gauge-theory/gauge-fixing-as-lagrangian-submanifold/), and [Anomalies as Obstructions](/rigorous-qft/bv-brst-gauge-theory/anomalies-as-obstructions/) first. The pAQFT background is in [Perturbative QFT as Formal Power Series](/rigorous-qft/perturbative-algebraic-qft/perturbative-qft-as-formal-power-series/), [Causal Perturbation Theory](/rigorous-qft/perturbative-algebraic-qft/causal-perturbation-theory/), and [Interacting Fields as Formal Series](/rigorous-qft/perturbative-algebraic-qft/interacting-fields-as-formal-series/).

## Core idea

The ordinary physics story says: write the Yang–Mills action, fix a gauge, add ghosts, derive Feynman rules, renormalize, and impose Slavnov–Taylor identities. The rigorous perturbative story says the same thing with every informal step replaced by a controlled object.

The construction has four layers.

1. **Classical gauge theory.** Yang–Mills fields form a gauge-redundant system. The equations, symmetries, Noether identities, and observables are encoded by BV data.
2. **Auxiliary free theory.** Gauge fixing gives a normally hyperbolic or otherwise well-controlled free operator on an enlarged field space. This makes propagators and the free algebra precise.
3. **Renormalized perturbation theory.** Time-ordered products and interacting fields are constructed as formal power series using causal factorization and local extension of distributions.
4. **BRST cohomology.** Physical observables are the cohomology of a renormalized interacting BRST charge or BV differential.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Rigorous perturbative Yang–Mills construction through the BV-BRST auxiliary theory](/figures/rigorous-qft/perturbative-yang-mills-bv-pipeline.svg)

<figcaption>

A rigorous perturbative Yang–Mills construction starts from classical gauge data, passes through the BV auxiliary system and gauge fixing, constructs renormalized time-ordered products, imposes Ward or master identities, and takes BRST cohomology. The output is a formal power series algebra, not a nonperturbative continuum measure.

</figcaption>
</figure>

## Classical Yang–Mills data

Let $P\to M$ be a principal $G$-bundle and let $A$ be a connection. In a local trivialization, $A=A_\mu dx^\mu$ is a $\mathfrak g$-valued one-form and

$$
F=dA+\frac12[A,A].
$$

In components,

$$
F^a_{\mu\nu}
=\partial_\mu A^a_\nu-
\partial_\nu A^a_\mu
+f^a{}_{bc}A^b_\mu A^c_\nu.
$$

An infinitesimal gauge transformation with parameter $\epsilon$ acts by

$$
\delta_\epsilon A_\mu=D_\mu\epsilon,
\qquad
D_\mu\epsilon=\partial_\mu\epsilon+[A_\mu,\epsilon].
$$

The classical action is invariant under this transformation. In BRST language one replaces $\epsilon$ by an odd ghost $c$ and writes

$$
sA_\mu=D_\mu c,
\qquad
sc=-\frac12[c,c].
$$

Nilpotency follows from the Jacobi identity and the covariance of the curvature:

$$
s^2A_\mu=0,
\qquad
s^2c=0.
$$

In the BV formalism one adds antifields $A^{*\mu}$ and $c^*$ and begins with the minimal master action

$$
\begin{aligned}
S_{\mathrm{BV,min}}
&=S_{\mathrm{YM}}[A]
 +\int_M d^dx\,
 A^{*\mu}_a(D_\mu c)^a \\
&\quad
 -\frac12\int_M d^dx\,
 c^*_a f^a{}_{bc}c^b c^c .
\end{aligned}
$$

This compactly records the action, the gauge transformation, and the gauge algebra.

## Why gauge fixing is unavoidable perturbatively

The second variation of the Yang–Mills action around a background has gauge zero directions. This means there is no ordinary inverse propagator on the space of all gauge potentials.

For perturbation theory one chooses a gauge-fixing fermion or a gauge condition. In a Lorenz-type gauge for a trivial bundle over flat spacetime, the familiar nonminimal fields are

$$
\bar c^a,
\qquad b^a,
$$

with

$$
s\bar c^a=b^a,
\qquad
sb^a=0.
$$

A common gauge-fixing fermion is

$$
\Psi
=\int_M d^dx\,
\bar c_a\left(
\partial^\mu A^a_\mu+\frac\xi2 b^a
\right).
$$

Eliminating antifields by

$$
\Phi_A^*=\frac{\delta\Psi}{\delta\Phi^A}
$$

gives the usual gauge-fixed Lagrangian containing

$$
-\frac{1}{2\xi}(\partial^\mu A^a_\mu)^2
\quad\text{and}\quad
-\bar c_a\partial^\mu D_\mu c^a,
$$

up to convention-dependent signs and integration by parts.

The ghosts appear because the gauge-fixed free operator is defined on an auxiliary complex, not because they are extra physical polarizations. Physical quantities are recovered only after imposing BRST cohomology.

## The perturbative algebraic construction

In perturbative algebraic QFT, one first constructs a free algebra $\mathfrak A_0$ of fields and Wick polynomials. The free product is determined by a two-point distribution satisfying the microlocal spectrum condition. Interactions are introduced through a local interaction functional $V$ and the relative $S$-matrix or Bogoliubov map.

Schematically, the interacting field associated with a local functional $F$ is

$$
R_V(F)
=
\left.\frac{d}{d\lambda}\right|_{\lambda=0}
S(V)^{-1}\star S(V+\lambda F),
$$

where $S(V)$ is a formal time-ordered exponential and $\star$ is the free quantum product. This expression is formal but precise once the time-ordered products are constructed.

For Yang–Mills theory, the algebra is initially an **auxiliary** algebra containing gauge fields, ghosts, antighosts, $b$-fields, and antifields. Physical interacting observables are then selected by BRST cohomology:

$$
\mathfrak A_{\mathrm{phys}}
=H^0(Q_{\mathrm{int}},\mathfrak A_{\mathrm{aux}}).
$$

The operator $Q_{\mathrm{int}}$ is the interacting BRST charge or the corresponding BV differential. Constructing it requires renormalized Ward identities ensuring conservation and nilpotency.

## Renormalization and Ward identities

Renormalization in perturbative Yang–Mills theory is not only the subtraction of divergent integrals. It is the construction of time-ordered products satisfying a list of compatibility conditions:

$$
T_n(F_1,\ldots,F_n),
\qquad n\ge 1.
$$

For ordinary scalar theories, the main conditions include locality, covariance, causal factorization, unitarity, microlocal spectral bounds, and scaling behavior. For gauge theories, one must also impose the gauge identities.

In BRST language, these are Slavnov–Taylor or master Ward identities. Schematic examples are

$$
Q_{\mathrm{int}}^2=0
$$

and

$$
[Q_{\mathrm{int}},R_V(F)]
=R_V(sF)
$$

for suitable representatives and modulo the usual qualifications about local functionals, equations of motion, and anomalies.

The obstruction to imposing these identities is precisely the anomaly class discussed in [Anomalies as Obstructions](/rigorous-qft/bv-brst-gauge-theory/anomalies-as-obstructions/). If the relevant anomaly class vanishes, finite renormalizations can be chosen to restore the identities order by order.

## What is rigorous here?

The rigorous perturbative result has a specific form.

**Formal power series.** Observables are elements of algebras such as

$$
\mathfrak A[[g]]
$$

where $g$ is a formal coupling. No convergence in $g$ is asserted.

**Local construction.** The theory is built from local functionals, local time-ordered products, causal factorization, and extension of distributions to diagonals.

**Microlocal control.** Products of distributions are controlled by wavefront-set conditions. This is essential on curved spacetimes and useful even in flat spacetime.

**Gauge control by cohomology.** The auxiliary gauge-fixed algebra is not the physical algebra. Physical observables are BRST-BV cohomology classes.

**Renormalization ambiguities.** Different allowed choices of time-ordered products are related by local finite renormalizations. Gauge identities restrict these ambiguities.

**Curved-spacetime compatibility.** In locally covariant settings, the construction is required to behave naturally under embeddings of globally hyperbolic spacetimes.

This is already substantial. It gives a mathematically controlled version of the perturbative Yang–Mills fields used in formal calculations.

## What is not proved here?

The perturbative theorem should not be mistaken for a nonperturbative theorem.

It does **not** prove that the formal series converges.

It does **not** construct a positive Hilbert space of interacting non-Abelian Yang–Mills theory in four dimensions.

It does **not** prove a mass gap.

It does **not** prove confinement.

It does **not** prove asymptotic completeness.

It does **not** define a continuum Euclidean Yang–Mills measure in four dimensions.

It does **not** solve the problem of Gribov copies in a nonperturbative gauge-fixed path integral.

This boundary is not a weakness of the perturbative framework. It is what makes the theorem honest. Perturbative Yang–Mills and nonperturbative Yang–Mills are related but mathematically different problems.

## Flat spacetime versus curved spacetime

On Minkowski spacetime, physicists often use momentum-space Feynman diagrams and dimensional regularization. These are efficient and canonical for many calculations, but they hide some locality and covariance properties.

On curved spacetime, global momentum space is absent. The perturbative algebraic construction instead uses local covariance, Hadamard two-point functions, causal propagators, and microlocal extension of distributions. This makes the framework well suited for a theorem-level formulation.

The curved-spacetime viewpoint has a useful side effect: it forces the construction to distinguish physical principles from flat-space computational conveniences. Propagators, time-ordered products, Ward identities, and observables must be formulated without relying on translation invariance.

## Relation to ordinary Feynman rules

The ordinary Feynman rules are not discarded. They reappear as a coordinate representation of the same formal expansion in special situations.

For a gauge-fixed Yang–Mills theory in flat spacetime, the free propagators and interaction vertices produce diagrams with:

- gauge-boson propagators,
- ghost propagators,
- three- and four-gauge-boson vertices,
- ghost-gauge vertices,
- matter vertices if matter is included,
- counterterm vertices required by renormalization.

The rigorous formulation changes the logical status of these diagrams. A diagram is not the definition of the theory; it is a contribution to a renormalized time-ordered product or interacting field in a formal power series.

## Matter fields and chiral gauge theories

Adding scalar or Dirac matter is straightforward perturbatively once the free field content and interaction terms are specified. Chiral matter is more delicate because gauge anomalies may appear.

For an anomaly-free chiral gauge theory, one must show that the required Ward identities can be imposed by suitable finite renormalizations. The local BRST cohomology analysis gives the obstruction theory: if the relevant anomaly class cancels, the perturbative construction can proceed within the chosen framework.

This is the rigorous version of the familiar physics statement that chiral gauge theories require anomaly cancellation.

## The role of antifields

Antifields have two complementary roles in perturbative Yang–Mills theory.

First, they encode the BRST transformations and gauge algebra in the master action. For example, the term

$$
\int_M d^dx\,A^{*\mu}_a(D_\mu c)^a
$$

says that $sA_\mu=D_\mu c$.

Second, they act as sources for composite BRST variations in renormalized perturbation theory. This is essential because expressions such as $D_\mu c$ and $[c,c]$ are composite fields. Renormalizing the identities involving them requires treating them as insertions with their own source variables.

This is why antifields are not optional decoration in a rigorous treatment. They are part of the bookkeeping that makes the Ward identities meaningful after renormalization.

## Common pitfalls

**Saying “Yang–Mills is rigorously constructed” without the word perturbative.** The perturbative construction gives a formal power series algebra. It is not the nonperturbative four-dimensional theory with mass gap.

**Thinking gauge fixing defines the physical theory.** Gauge fixing defines an auxiliary theory. The physical algebra is recovered through BRST cohomology and Ward identities.

**Ignoring anomalies.** A gauge-fixed Lagrangian with ghosts is not enough. One must also check that the quantum identities can be maintained.

**Confusing formal power series with asymptotic expansions.** Formal power series are algebraic objects. Whether they are asymptotic to functions, Borel summable, or non-Borel summable is a different question.

**Treating ghosts as physical states.** Ghosts appear in the auxiliary complex. Physical states or observables must be selected by cohomology.

**Assuming flat-space diagrams are the only rigorous method.** Epstein–Glaser and pAQFT constructions define perturbation theory locally, including on curved spacetime where momentum-space diagrams are not available.

**Forgetting background dependence.** Perturbation theory is often around a background connection or metric. The construction may depend on this background, while local covariance controls how that dependence transforms.

## Relations to other pages

This page completes the first BV-BRST route through gauge redundancy. The cohomological input is developed in [BRST Complex](/rigorous-qft/bv-brst-gauge-theory/brst-complex/), [BV Formalism](/rigorous-qft/bv-brst-gauge-theory/bv-formalism/), and [Observables as Cohomology](/rigorous-qft/bv-brst-gauge-theory/observables-as-cohomology/). The obstruction theory is in [Anomalies as Obstructions](/rigorous-qft/bv-brst-gauge-theory/anomalies-as-obstructions/).

The perturbative machinery is shared with [Causal Perturbation Theory](/rigorous-qft/perturbative-algebraic-qft/causal-perturbation-theory/), [Epstein–Glaser Renormalization](/rigorous-qft/perturbative-algebraic-qft/epstein-glaser-renormalization/), [Extension of Distributions](/rigorous-qft/perturbative-algebraic-qft/extension-of-distributions/), and [Interacting Fields as Formal Series](/rigorous-qft/perturbative-algebraic-qft/interacting-fields-as-formal-series/).

For the curved-spacetime side, see [QFT in Curved Spacetime: Rigorous View](/rigorous-qft/locally-covariant-qft/qft-in-curved-spacetime-rigorous-view/), [Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/), and [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/).

For nonperturbative questions, continue later to constructive QFT, lattice-to-continuum constructions, and the open-problems chapter.

## Research status

**Established.** Perturbative Yang–Mills theory can be treated as a renormalized formal power series theory using BRST-BV methods, causal perturbation theory, and local cohomological identities.

**Established.** In anomaly-free cases, Ward or master identities can be imposed order by order under suitable hypotheses, and physical observables can be described as BRST cohomology classes of an auxiliary algebra.

**Subtle.** The exact theorem statement depends on the framework: flat-space renormalized perturbation theory, Epstein–Glaser theory, pAQFT, locally covariant QFT, or BV factorization algebra. The common core is local perturbative control, not a single universal construction theorem covering every desired analytic property.

**Open.** Nonperturbative four-dimensional Yang–Mills existence, mass gap, confinement, and asymptotic particle interpretation remain separate problems.

## Exercises

### Exercise 1: Nilpotency of the Yang–Mills BRST differential

Let

$$
sA_\mu=D_\mu c,
\qquad
sc=-\frac12[c,c].
$$

Show formally that $s^2A_\mu=0$.

<details><summary><strong>Solution</strong></summary>

Use the graded derivation property of $s$ and the covariance of the derivative. First,

$$
s^2A_\mu=s(D_\mu c).
$$

Since $D_\mu c=\partial_\mu c+[A_\mu,c]$,

$$
s(D_\mu c)
=D_\mu(sc)+[sA_\mu,c].
$$

Substitute $sc=-\frac12[c,c]$ and $sA_\mu=D_\mu c$:

$$
s^2A_\mu
=-\frac12D_\mu[c,c]+[D_\mu c,c].
$$

The covariant derivative obeys

$$
D_\mu[c,c]=2[D_\mu c,c]
$$

with the appropriate graded signs for the odd ghost. Therefore $s^2A_\mu=0$.

</details>

### Exercise 2: Why a gauge propagator needs gauge fixing

Consider the Abelian quadratic action

$$
S_2[A]=-\frac14\int d^dx\,
F_{\mu\nu}F^{\mu\nu}.
$$

Explain why the quadratic operator cannot be inverted before gauge fixing.

<details><summary><strong>Solution</strong></summary>

The Abelian action is invariant under

$$
A_\mu\mapsto A_\mu+\partial_\mu\epsilon.
$$

Thus pure-gradient directions are zero directions of the quadratic form. In momentum space, the kinetic operator is proportional to

$$
K_{\mu\nu}(p)=p^2\eta_{\mu\nu}-p_\mu p_\nu.
$$

It has

$$
K_{\mu\nu}(p)p^\nu=0.
$$

Therefore it has no inverse on the full vector space. Gauge fixing modifies the operator so that an inverse propagator can be defined on the auxiliary gauge-fixed system.

</details>

### Exercise 3: Formal series versus convergence

Let an interacting field be written as

$$
R_V(F)=\sum_{n\ge0}g^n R_n(F).
$$

What does it mean to construct this as a formal power series, and what does it not mean?

<details><summary><strong>Solution</strong></summary>

A formal power series construction defines each coefficient $R_n(F)$ and gives algebraic rules for addition, multiplication, commutators, adjoints, and identities order by order in $g$. It does not require the series to converge for any numerical value of $g$.

Thus a perturbative construction can be rigorous as an element of $\mathfrak A[[g]]$ even if the numerical series is divergent, asymptotic, or non-Borel summable. Analytic summability is an additional nonperturbative question.

</details>

## References

### Gauge fixing, BRST, and BV

- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* **25** (1967), 29–30. [doi:10.1016/0370-2693(67)90067-6](https://doi.org/10.1016/0370-2693(67)90067-6).
- C. Becchi, A. Rouet, and R. Stora, “Renormalization of Gauge Theories,” *Annals of Physics* **98** (1976), 287–321. [doi:10.1016/0003-4916(76)90156-1](https://doi.org/10.1016/0003-4916(76)90156-1).
- I. V. Tyutin, “Gauge Invariance in Field Theory and Statistical Physics in Operator Formalism,” Lebedev preprint (1975). [arXiv:0812.0580](https://arxiv.org/abs/0812.0580).
- I. A. Batalin and G. A. Vilkovisky, “Gauge Algebra and Quantization,” *Physics Letters B* **102** (1981), 27–31. [doi:10.1016/0370-2693(81)90205-7](https://doi.org/10.1016/0370-2693(81)90205-7).
- I. A. Batalin and G. A. Vilkovisky, “Quantization of Gauge Theories with Linearly Dependent Generators,” *Physical Review D* **28** (1983), 2567–2582. [doi:10.1103/PhysRevD.28.2567](https://doi.org/10.1103/PhysRevD.28.2567).

### Rigorous perturbative Yang–Mills and pAQFT

- S. Hollands, “Renormalized Quantum Yang–Mills Fields in Curved Spacetime,” *Reviews in Mathematical Physics* **20** (2008), 1033–1172. [arXiv:0705.3340](https://arxiv.org/abs/0705.3340), [doi:10.1142/S0129055X08003420](https://doi.org/10.1142/S0129055X08003420).
- K. Fredenhagen and K. Rejzner, “Batalin–Vilkovisky Formalism in Perturbative Algebraic Quantum Field Theory,” *Communications in Mathematical Physics* **317** (2013), 697–725. [arXiv:1110.5232](https://arxiv.org/abs/1110.5232), [doi:10.1007/s00220-012-1601-1](https://doi.org/10.1007/s00220-012-1601-1).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory: An Introduction for Mathematicians*, Mathematical Physics Studies, Springer, 2016. [doi:10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).
- K. Costello, *Renormalization and Effective Field Theory*, Mathematical Surveys and Monographs **170**, American Mathematical Society, 2011. [doi:10.1090/surv/170](https://doi.org/10.1090/surv/170).

### Cohomology and anomalies

- G. Barnich, F. Brandt, and M. Henneaux, “Local BRST Cohomology in Gauge Theories,” *Physics Reports* **338** (2000), 439–569. [arXiv:hep-th/0002245](https://arxiv.org/abs/hep-th/0002245), [doi:10.1016/S0370-1573(00)00049-1](https://doi.org/10.1016/S0370-1573(00)00049-1).
- O. Piguet and S. P. Sorella, *Algebraic Renormalization: Perturbative Renormalization, Symmetries and Anomalies*, Springer, 1995. [doi:10.1007/978-3-540-49192-7](https://doi.org/10.1007/978-3-540-49192-7).
- M. Dütsch and K. Fredenhagen, “Causal Perturbation Theory in Terms of Retarded Products, and a Proof of the Action Ward Identity,” *Reviews in Mathematical Physics* **16** (2004), 1291–1348. [arXiv:hep-th/0403213](https://arxiv.org/abs/hep-th/0403213), [doi:10.1142/S0129055X04002216](https://doi.org/10.1142/S0129055X04002216).

## Version history

- **2026-07-01:** Initial polished draft.
