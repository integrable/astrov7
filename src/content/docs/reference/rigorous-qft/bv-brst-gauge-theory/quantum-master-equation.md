---
title: "Quantum Master Equation"
description: "Explains the BV quantum master equation, the role of the BV Laplacian, and how anomalies appear as cohomological obstructions in perturbative gauge theory."
sidebar:
  label: "Quantum Master Equation"
  order: 5
level: Advanced
status: "Polished draft"
source: "Batalin–Vilkovisky; Schwarz; Gomis–París–Samuel; Barnich–Brandt–Henneaux; Fredenhagen–Rejzner; Costello"
topics:
  - quantum master equation
  - BV Laplacian
  - anomalies
  - perturbative quantization
  - gauge fixing
canonicalTopics:
  - quantum-master-equation
  - bv-laplacian
  - anomalies
  - perturbative-gauge-theory
  - brst-cohomology
researchStatus:
  established:
    - "In finite-dimensional BV theory, the quantum master equation is the condition that makes BV integration independent of deformations of the gauge-fixing Lagrangian submanifold."
  active:
    - "In local quantum field theory the BV Laplacian is singular and must be replaced by renormalized or regularized constructions; the remaining obstruction is measured by local BRST/BV cohomology."
---

## Summary

The **quantum master equation** is the BV condition that replaces classical gauge invariance after quantization. The classical master equation says that the BV action $S_0$ generates a nilpotent classical differential:

$$
(S_0,S_0)=0,
\qquad
s_0F=(S_0,F),
\qquad
s_0^2=0.
$$

The quantum master equation adds the effect of the integration measure. In the simplest finite-dimensional convention used on this page,

$$
\frac12(S_\hbar,S_\hbar)-i\hbar\Delta S_\hbar=0,
$$

or equivalently

$$
\Delta\exp\!\left(\frac{i}{\hbar}S_\hbar\right)=0.
$$

Here $\Delta$ is the BV Laplacian associated with a choice of compatible density, and $S_\hbar=S_0+\hbar S_1+\hbar^2S_2+\cdots$ is a quantum BV action. The equation says that the exponential weight used in BV integration is $\Delta$-closed.

This page explains the finite-dimensional meaning of the equation, the order-by-order obstruction theory, why the formula is singular in local QFT, and how the failure of the quantum master equation is related to anomalies.

:::caution[Status]
The displayed finite-dimensional formula is a model for the structure. In local field theory, $\Delta$ contains second functional derivatives at coincident points and is not a literal operator on local functionals without regularization or renormalization. In rigorous perturbative settings one replaces this naive expression by renormalized BV operators, master Ward identities, or effective-scale versions.
:::

## Prerequisites

Read [BV Formalism](/rigorous-qft/bv-brst-gauge-theory/bv-formalism/) and [Classical Master Equation](/rigorous-qft/bv-brst-gauge-theory/classical-master-equation/) first. The pages on [Extension of Distributions](/rigorous-qft/perturbative-algebraic-qft/extension-of-distributions/), [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/), and [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/) explain why renormalization is unavoidable once products of local fields are used.

## Core idea

The classical BV formalism makes gauge invariance into the equation

$$
(S_0,S_0)=0.
$$

This is not yet the whole quantum story. A quantum path integral has two ingredients:

$$
\text{integrand}
= \text{measure}\times\exp\!\left(\frac{i}{\hbar}S\right).
$$

A symmetry of the classical action can fail to be a symmetry of the measure. In elementary language, this is the origin of many anomalies. BV packages the action and measure into one object by introducing a second-order operator $\Delta$. The quantum master equation is the compact condition that the full BV integrand is compatible with the odd symplectic structure.

<figure class="doc-figure" style="--figure-width: 52rem;">

![The quantum master equation as the quantum refinement of the classical master equation](/figures/rigorous-qft/quantum-master-equation-obstruction.svg)

<figcaption>

The classical master equation gives the classical BV differential. Quantization adds a measure term, represented in finite dimension by $\Delta$. In local QFT this term is singular and must be renormalized; failure to solve the resulting equation is an anomaly class.

</figcaption>
</figure>

The slogan is:

$$
\text{classical master equation}
+\text{measure compatibility}
=\text{quantum master equation}.
$$

That slogan is accurate only if “measure compatibility” is treated carefully. In finite dimension it is a theorem about BV integration. In QFT it becomes a renormalization problem.

## Setup and conventions

Let $\mathcal F$ be a finite-dimensional graded manifold equipped with an odd symplectic form. In Darboux coordinates $\Phi^A,\Phi_A^*$, the BV antibracket is written schematically as

$$
(F,G)
 =\sum_A\left(
    \frac{\partial_r F}{\partial \Phi^A}
    \frac{\partial_l G}{\partial \Phi_A^*}
    -
    \frac{\partial_r F}{\partial \Phi_A^*}
    \frac{\partial_l G}{\partial \Phi^A}
  \right),
$$

with the usual graded signs suppressed in this schematic display. The bracket has ghost number $+1$:

$$
\operatorname{gh}(F,G)
 =\operatorname{gh}(F)+\operatorname{gh}(G)+1.
$$

A compatible density $\rho$ defines a BV Laplacian $\Delta_\rho$. In Darboux coordinates with constant density, the model formula is

$$
\Delta F
  =\sum_A (-1)^{|\Phi^A|}
    \frac{\partial_l}{\partial \Phi^A}
    \frac{\partial_l F}{\partial \Phi_A^*}.
$$

The important properties are not the coordinate signs, but the structural identities:

$$
\Delta^2=0,
\qquad
\Delta(FG)
 = (\Delta F)G
 +(-1)^{|F|}F\Delta G
 +(-1)^{|F|}(F,G).
$$

Thus $\Delta$ is not a derivation. Its failure to be a derivation is precisely the BV antibracket.

The sign convention for the quantum master equation varies across the literature. With Lorentzian weight $e^{iS/\hbar}$ we write

$$
\frac12(S_\hbar,S_\hbar)-i\hbar\Delta S_\hbar=0.
$$

With Euclidean or formal weights, the factor of $i$ is often absent or moved into the definition of $S_\hbar$. The cohomological content is independent of this bookkeeping.

## Finite-dimensional BV integration

In finite dimension, the geometric reason for the quantum master equation is clean. Suppose $\mathcal L\subset \mathcal F$ is a Lagrangian submanifold, interpreted as a gauge-fixing condition. For an observable $\mathcal O$, BV integration has the schematic form

$$
\langle\mathcal O\rangle_{\mathcal L}
  =\int_{\mathcal L}
       \mathcal O\,
       \exp\!\left(\frac{i}{\hbar}S_\hbar\right).
$$

The quantum master equation says that the integrand is closed under the BV divergence operator. A BV version of Stokes's theorem then implies that the integral is unchanged under suitable deformations of $\mathcal L$, provided the observable is also quantum-closed:

$$
\Delta\left(
\mathcal O e^{iS_\hbar/\hbar}
\right)=0.
$$

Equivalently, one defines the quantum BV differential

$$
\widehat sF
  =(S_\hbar,F)-i\hbar\Delta F.
$$

Then the quantum master equation is the condition that $\widehat s$ squares to zero on the appropriate algebra. Observables are quantum cohomology classes:

$$
\widehat s\mathcal O=0,
\qquad
\mathcal O\sim\mathcal O+\widehat sK.
$$

This is the precise BV version of the informal statement “physical answers should not depend on the gauge-fixing condition.”

## Expanding the equation in ℏ

Write

$$
S_\hbar=S_0+\hbar S_1+\hbar^2S_2+\cdots.
$$

Substitute this into

$$
\frac12(S_\hbar,S_\hbar)-i\hbar\Delta S_\hbar=0.
$$

At order $\hbar^0$ one recovers the classical master equation:

$$
\frac12(S_0,S_0)=0.
$$

At order $\hbar^1$ one obtains

$$
(S_0,S_1)-i\Delta S_0=0.
$$

Using $s_0F=(S_0,F)$, this is

$$
s_0S_1=i\Delta S_0.
$$

Thus the first quantum correction $S_1$ exists only if $\Delta S_0$ is $s_0$-exact. Since

$$
s_0(\Delta S_0)=0
$$

under the usual compatibility hypotheses, $\Delta S_0$ defines a cohomology class. If that class is nonzero, the quantum master equation cannot be solved without changing the theory or adding extra degrees of freedom.

At order $\hbar^2$ one gets

$$
s_0S_2
= i\Delta S_1-\frac12(S_1,S_1),
$$

and similarly at higher orders. The quantum master equation is therefore an obstruction problem in BV cohomology.

The physically important version of this statement is:

$$
\text{anomaly candidates live in ghost number }1.
$$

Counterterms live in ghost number $0$. Anomalies live one ghost degree higher because they measure the failure of a quantum symmetry identity.

## Why the BV Laplacian is singular in QFT

The finite-dimensional operator $\Delta$ differentiates once with respect to a field and once with respect to its antifield. In field theory this becomes a functional expression of the schematic form

$$
\Delta F
  \sim
  \sum_A\int_M d^dx\,
  \frac{\delta^2 F}
       {\delta\Phi^A(x)\,\delta\Phi_A^*(x)}.
$$

For local functionals, this asks one to multiply distributions at the same spacetime point. That is exactly the kind of singular operation that renormalization was invented to control.

For example, if a functional contains a local density built from fields and derivatives at $x$, two functional derivatives can produce delta functions supported at coincident points. Evaluating the expression at the same point produces symbols such as

$$
\delta(0),
$$

which are not distributions. The correct lesson is not “BV fails.” The lesson is that the naive finite-dimensional $\Delta$ is not a literal operator on local QFT functionals.

This is one reason the quantum master equation is conceptually more subtle than the classical master equation. The classical bracket is already formal but can often be interpreted on local functionals. The quantum Laplacian requires a renormalization prescription, a regulator, or a different perturbative algebraic replacement.

## Renormalized quantum master equations

There are several rigorous or semi-rigorous ways to retain the content of the quantum master equation in field theory.

**Regularized BV.** Introduce a cutoff, replace $\Delta$ by a regulated operator $\Delta_\Lambda$, and solve an effective-scale quantum master equation. The resulting effective action depends on the scale. One then studies whether the equation can be maintained as the cutoff is removed or the scale is changed.

**Perturbative algebraic BV.** Work with formal power series and renormalized time-ordered products. In this approach, the ill-defined BV Laplacian is replaced by a renormalized operator or anomaly term in a master Ward identity. The equation is not written as a naive functional integral identity; it is written inside the algebra of perturbative observables.

**Algebraic renormalization.** Express the possible failure of the Slavnov–Taylor or BV identity as a local integrated functional $\mathcal A$ satisfying a consistency condition

$$
s_0\mathcal A=0.
$$

If

$$
\mathcal A=s_0B,
$$

then a finite counterterm $B$ can remove the anomaly. If the cohomology class of $\mathcal A$ is nonzero, the anomaly is genuine.

All three viewpoints agree on the main structural point: the failure of quantum gauge invariance is not arbitrary. It is local, constrained, and cohomological.

## Anomalies as obstruction classes

Suppose a renormalized construction produces a breaking term $\mathcal A$ in the quantum master equation. Its ghost number is $1$. The nilpotence or consistency of the classical BV differential implies the Wess–Zumino consistency condition

$$
s_0\mathcal A=0.
$$

Changing the renormalization prescription or adding a finite local counterterm changes $\mathcal A$ by an exact term:

$$
\mathcal A\longmapsto \mathcal A+s_0B.
$$

Therefore the invariant obstruction is the cohomology class

$$
[\mathcal A]\in H^1(s_0).
$$

For local field theory, the sharper statement uses local functionals modulo total derivatives. If $a$ is a local $d$-form representing the anomaly density, then

$$
s_0 a+d b=0,
$$

and the anomaly class belongs to

$$
H^{1,d}(s_0\mid d).
$$

Here the first superscript is ghost number and the second is form degree. The notation $s_0\mid d$ means that two local densities differing by a total derivative define the same integrated functional.

This is the bridge from the BV quantum master equation to the anomaly pages later in the chapter.

## Example: the finite-dimensional toy model

Let $(x^i,\xi_i)$ be even-odd Darboux coordinates with

$$
(x^i,\xi_j)=\delta^i_j,
\qquad
\Delta=\sum_i\frac{\partial^2}{\partial x^i\partial\xi_i}.
$$

Let $S$ be even. The condition

$$
\Delta e^{iS/\hbar}=0
$$

is equivalent to

$$
\frac12(S,S)-i\hbar\Delta S=0.
$$

Indeed, the second-order nature of $\Delta$ gives

$$
\Delta e^{iS/\hbar}
=\left(
\frac{i}{\hbar}\Delta S
-\frac{1}{2\hbar^2}(S,S)
\right)e^{iS/\hbar}.
$$

Multiplying by $-\hbar^2$ gives the displayed equation. This computation is the algebraic heart of the quantum master equation.

In field theory the same formal calculation is morally correct, but the operator $\Delta$ is ill-defined on the local action. The obstruction appears precisely at the step where two functional derivatives collide.

## Common pitfalls

**Thinking the quantum master equation is just the classical master equation with hats.** The new term $\Delta S$ encodes the measure or renormalized time-ordering effect. It is not present classically.

**Treating the BV Laplacian as harmless in local QFT.** The expression contains coincident functional derivatives. Without regularization or renormalization, it is usually meaningless on local functionals.

**Calling every breaking term an anomaly.** A breaking term that is BRST/BV exact can be removed by a counterterm. The anomaly is the cohomology class that remains after this freedom is used.

**Forgetting convention dependence.** Lorentzian and Euclidean conventions place factors of $i$ differently. The obstruction class and nilpotence statement are the invariant content.

**Assuming QME implies nonperturbative existence.** A solved perturbative quantum master equation gives order-by-order consistency of gauge symmetry. It does not automatically construct a nonperturbative continuum measure.

## Relations to other pages

The [Classical Master Equation](/rigorous-qft/bv-brst-gauge-theory/classical-master-equation/) is the $\hbar^0$ part of the story. [Ghosts, Antifields, and Cohomology](/rigorous-qft/bv-brst-gauge-theory/ghosts-antifields-and-cohomology/) explains the cohomology groups in which counterterms and anomalies live. `anomalies-as-obstructions.md` will make the obstruction language concrete.

For renormalized perturbation theory, connect this page to [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/) and [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/). For mathematical perturbative QFT, the Factorization Algebras chapter later gives another natural home for scale-dependent BV quantization.

## Research status

**Established.** The finite-dimensional BV quantum master equation is a precise geometric statement about odd symplectic manifolds, compatible densities, BV Laplacians, and gauge-fixing independence. In perturbative gauge theory, the same structure governs Slavnov–Taylor identities, anomaly consistency conditions, and the classification of local counterterms.

**Technically delicate.** The naive BV Laplacian is not defined on local QFT actions. Any serious field-theoretic use of the quantum master equation must specify regularization, renormalized time-ordered products, effective actions, or another precise replacement.

**Active.** Boundary theories, extended operators, global gauge quotient geometry, nonperturbative quantization, and derived-geometric formulations of BV theory remain active research areas. The local cohomological structure is powerful, but it is not the whole story of gauge theory.

## Exercises

### Exercise 1: derive the finite-dimensional quantum master equation

Let $\Delta$ be an odd second-order operator satisfying

$$
\Delta(FG)
 = (\Delta F)G
 +(-1)^{|F|}F\Delta G
 +(-1)^{|F|}(F,G).
$$

Assume $S$ is even. Show that

$$
\Delta e^{iS/\hbar}=0
$$

is equivalent to

$$
\frac12(S,S)-i\hbar\Delta S=0.
$$

<details><summary><strong>Solution</strong></summary>

Use the second-order identity repeatedly, or expand the exponential as a formal power series. For an even $S$,

$$
\Delta e^{iS/\hbar}
=\left(
\frac{i}{\hbar}\Delta S
-\frac{1}{2\hbar^2}(S,S)
\right)e^{iS/\hbar}.
$$

The exponential is invertible as a formal series. Thus the vanishing of $\Delta e^{iS/\hbar}$ is equivalent to

$$
\frac{i}{\hbar}\Delta S
-\frac{1}{2\hbar^2}(S,S)=0.
$$

Multiplying by $-\hbar^2$ gives

$$
\frac12(S,S)-i\hbar\Delta S=0.
$$

</details>

### Exercise 2: find the first obstruction

Let $S_\hbar=S_0+\hbar S_1+O(\hbar^2)$ and suppose

$$
\frac12(S_\hbar,S_\hbar)-i\hbar\Delta S_\hbar=0.
$$

Find the equations at order $\hbar^0$ and $\hbar^1$.

<details><summary><strong>Solution</strong></summary>

At order $\hbar^0$:

$$
\frac12(S_0,S_0)=0.
$$

At order $\hbar^1$:

$$
(S_0,S_1)-i\Delta S_0=0.
$$

With $s_0F=(S_0,F)$, this becomes

$$
s_0S_1=i\Delta S_0.
$$

Therefore the first quantum correction exists only if $\Delta S_0$ is $s_0$-exact.

</details>

### Exercise 3: why the anomaly has ghost number one

Assume $S_0$ has ghost number $0$, the BV bracket has ghost number $+1$, and $\Delta$ has ghost number $+1$. What is the ghost number of the breaking term in the quantum master equation?

<details><summary><strong>Solution</strong></summary>

Both terms

$$
(S_\hbar,S_\hbar)
\qquad\text{and}\qquad
\Delta S_\hbar
$$

have ghost number $1$, because $S_\hbar$ has ghost number $0$, the bracket raises ghost number by $1$, and $\Delta$ also raises ghost number by $1$. Thus a possible failure of the quantum master equation is a ghost-number-one functional. This is why local anomaly classes live in ghost number $1$.

</details>

## References

### Standard references

- I. A. Batalin and G. A. Vilkovisky, “Gauge Algebra and Quantization,” *Physics Letters B* **102** (1981), 27–31. [doi:10.1016/0370-2693(81)90205-7](https://doi.org/10.1016/0370-2693(81)90205-7).
- I. A. Batalin and G. A. Vilkovisky, “Quantization of Gauge Theories with Linearly Dependent Generators,” *Physical Review D* **28** (1983), 2567–2582. [doi:10.1103/PhysRevD.28.2567](https://doi.org/10.1103/PhysRevD.28.2567).
- A. Schwarz, “Geometry of Batalin–Vilkovisky Quantization,” *Communications in Mathematical Physics* **155** (1993), 249–260. [arXiv:hep-th/9205088](https://arxiv.org/abs/hep-th/9205088), [doi:10.1007/BF02097392](https://doi.org/10.1007/BF02097392).
- J. Gomis, J. París, and S. Samuel, “Antibracket, Antifields and Gauge-Theory Quantization,” *Physics Reports* **259** (1995), 1–145. [arXiv:hep-th/9412228](https://arxiv.org/abs/hep-th/9412228), [doi:10.1016/0370-1573(94)00112-G](https://doi.org/10.1016/0370-1573(94)00112-G).

### Perturbative and cohomological references

- G. Barnich, F. Brandt, and M. Henneaux, “Local BRST Cohomology in Gauge Theories,” *Physics Reports* **338** (2000), 439–569. [arXiv:hep-th/0002245](https://arxiv.org/abs/hep-th/0002245), [doi:10.1016/S0370-1573(00)00049-1](https://doi.org/10.1016/S0370-1573(00)00049-1).
- K. Fredenhagen and K. Rejzner, “Batalin–Vilkovisky Formalism in Perturbative Algebraic Quantum Field Theory,” *Communications in Mathematical Physics* **317** (2013), 697–725. [arXiv:1110.5232](https://arxiv.org/abs/1110.5232), [doi:10.1007/s00220-012-1601-1](https://doi.org/10.1007/s00220-012-1601-1).
- K. Costello, *Renormalization and Effective Field Theory*, Mathematical Surveys and Monographs **170**, American Mathematical Society, 2011. [doi:10.1090/surv/170](https://doi.org/10.1090/surv/170).
- O. Piguet and S. P. Sorella, *Algebraic Renormalization: Perturbative Renormalization, Symmetries and Anomalies*, Springer, 1995. [doi:10.1007/978-3-540-49192-7](https://doi.org/10.1007/978-3-540-49192-7).

## Version history

- **2026-07-01:** Initial polished draft.
