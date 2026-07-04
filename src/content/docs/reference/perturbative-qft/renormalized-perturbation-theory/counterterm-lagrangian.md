---
title: "Counterterm Lagrangian"
description: "How local counterterms are organized in the Lagrangian, translated into Feynman rules, and fixed by renormalization conditions."
sidebar:
  label: "Counterterm Lagrangian"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§14–20 and 27–28; Coleman 2019, chs. 15–16 and 25; Weinberg 1995, Vol. I, ch. 12; Schwartz 2014, chs. 18–23; Zee 2010, ch. III.3; Zinn-Justin 2021, chs. 8–10"
topics:
  - counterterm lagrangian
  - local counterterms
  - renormalized perturbation theory
  - counterterm feynman rules
  - renormalization conditions
canonicalTopics:
  - counterterm-lagrangian
  - local-counterterm
  - counterterm-vertex
  - renormalized-lagrangian
  - scheme-dependence
researchStatus:
  established:
    - "Local counterterm Lagrangians are the standard perturbative implementation of renormalization: regulator-dependent local UV pieces are absorbed into local operators compatible with the theory's symmetries."
  active:
    - "Modern applications require systematic counterterm bases for gauge theories, EFTs, composite operators, evanescent operators, unstable-particle schemes, and automated multi-loop calculations."
---

## Summary

The **counterterm Lagrangian** is the local part of the Lagrangian that appears when a bare regulated theory is rewritten in terms of renormalized fields and parameters. It is not a separate physical interaction added by hand. It is the same bare theory expressed in coordinates adapted to finite calculations.

For real scalar $\phi^4$ theory in $d=4-2\epsilon$, the split is

$$
\mathcal L_0
=
\mathcal L_{\rm ren}+\mathcal L_{\rm ct}.
$$

With the conventions of [Bare and Renormalized Parameters](/perturbative-qft/renormalized-perturbation-theory/bare-and-renormalized-parameters/),

$$
\mathcal L_{\rm ren}
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4,
$$

and

$$
\mathcal L_{\rm ct}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2
-
\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4
-\delta\Lambda.
$$

The corresponding scalar counterterm vertices are

$$
\text{two-point counterterm: } i(p^2\delta Z-\delta m^2),
$$

and

$$
\text{quartic counterterm: } -i\mu^{2\epsilon}\delta\lambda.
$$

The coefficients $\delta Z$, $\delta m^2$, $\delta\lambda$, and $\delta\Lambda$ are fixed order by order by a renormalization scheme. Their job is to cancel local regulator dependence while leaving the finite, nonlocal, physical momentum dependence of loop diagrams intact.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![The bare Lagrangian splits into a renormalized Lagrangian and a counterterm Lagrangian, whose ordinary and counterterm rules combine into finite renormalized diagrams](/figures/perturbative-qft/counterterm-lagrangian-split.svg)

<figcaption>

The counterterm Lagrangian supplies local counterterm vertices. Ordinary diagrams and counterterm diagrams must be computed together at a fixed perturbative order. The final result is finite only after the chosen subtraction or physical renormalization conditions are imposed.

</figcaption>
</figure>

## Prerequisites

You should know [Bare and Renormalized Parameters](/perturbative-qft/renormalized-perturbation-theory/bare-and-renormalized-parameters/), [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [Superficial Degree of Divergence](/perturbative-qft/loop-expansion-regularization/superficial-degree-of-divergence/), [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/), [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/), and [Vacuum Bubbles](/perturbative-qft/loop-expansion-regularization/vacuum-bubbles/).

For later scattering applications, review [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/) and [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/).

## Core idea

Ultraviolet divergences in a local QFT are local. That sentence is the quiet engine behind counterterms.

A loop integral may diverge when the loop momentum becomes large. At large loop momentum, the diagram cannot resolve the detailed long-distance arrangement of external legs. Its divergent part is therefore a polynomial in external momenta and masses, compatible with the symmetries of the theory. A polynomial in momenta is exactly what a local operator produces.

So the counterterm Lagrangian has the form

$$
\mathcal L_{\rm ct}
=
\sum_i\delta c_i\mathcal O_i,
$$

where the $\mathcal O_i$ are local operators allowed by the symmetries and power counting. The coefficients $\delta c_i$ contain the regulator dependence and possible finite scheme-dependent pieces.

The counterterm Lagrangian does two things at once:

| Role | Meaning |
|---|---|
| Algebraic | It rewrites the bare Lagrangian in terms of renormalized parameters. |
| Diagrammatic | It supplies counterterm vertices that must be inserted in Feynman diagrams. |

This dual role is why counterterms are conceptually cleaner in the Lagrangian than as isolated subtraction symbols next to loop integrals.

## Setup and conventions

We use qft.org mostly-minus conventions and the Fourier phase $e^{-ip\cdot x}$. The scalar propagator from $\mathcal L_{\rm ren}$ is

$$
\frac{i}{p^2-m^2+i\epsilon}.
$$

Dimensional regularization is written with

$$
d=4-2\epsilon,
\qquad
\int_\ell
\equiv
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}.
$$

The scalar counterterms are expanded perturbatively:

$$
\delta Z=\delta Z^{(1)}+\delta Z^{(2)}+\cdots,
$$

$$
\delta m^2=\delta m^{2(1)}+\delta m^{2(2)}+\cdots,
\qquad
\delta\lambda=\delta\lambda^{(1)}+\delta\lambda^{(2)}+\cdots.
$$

A one-loop counterterm counts as a one-loop-order contribution even when the diagram containing it has no explicit loop integration. The loop order is stored in the coefficient.

## From the bare Lagrangian to counterterms

Start with

$$
\mathcal L_0
=
\frac12\partial_\mu\phi_0\,\partial^\mu\phi_0
-
\frac12m_0^2\phi_0^2
-
\frac{\lambda_0}{4!}\phi_0^4.
$$

Introduce the renormalized field and parameters by

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
Z_\phi=1+\delta Z,
$$

$$
Z_\phi m_0^2=m^2+\delta m^2,
\qquad
Z_\phi^2\lambda_0=\mu^{2\epsilon}(\lambda+\delta\lambda).
$$

Substitution gives

$$
\begin{aligned}
\mathcal L_0
&=
\frac12(1+\delta Z)\partial_\mu\phi\,\partial^\mu\phi
-
\frac12(m^2+\delta m^2)\phi^2
-
\frac{\mu^{2\epsilon}(\lambda+\delta\lambda)}{4!}\phi^4 \\
&=
\left[
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4
\right]
+
\left[
\frac12\delta Z\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2
-
\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4
\right].
\end{aligned}
$$

The first bracket is $\mathcal L_{\rm ren}$. The second bracket is $\mathcal L_{\rm ct}$, up to the optional but often necessary vacuum counterterm $-\delta\Lambda$.

The word “optional” here means optional for many ordinary flat-space scattering calculations. It is not optional if one tracks vacuum energy, the effective action at zero fields, gravity, or any calculation in which vacuum diagrams are part of the observable.

## Counterterm Feynman rules

Counterterm Feynman rules are derived by the same rule as ordinary Feynman rules: insert $i$ times the interaction term in the action and include the combinatoric normalization already built into the Lagrangian.

The quadratic counterterm is

$$
\mathcal L_{\rm ct}^{(2)}
=
\frac12\delta Z\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2.
$$

Fourier transforming it gives

$$
S_{\rm ct}^{(2)}
=
\frac12\int_p\phi(-p)
\left(p^2\delta Z-\delta m^2\right)
\phi(p).
$$

Therefore the two-point counterterm insertion is

$$
 i(p^2\delta Z-\delta m^2).
$$

The quartic counterterm is

$$
\mathcal L_{\rm ct}^{(4)}
=-\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4,
$$

so the four-point counterterm vertex is

$$
-i\mu^{2\epsilon}\delta\lambda.
$$

The vacuum counterterm is

$$
\mathcal L_{\rm ct}^{(0)}=-\delta\Lambda,
$$

so it contributes a local vacuum vertex proportional to

$$
-i\delta\Lambda\int d^dx.
$$

Different sign conventions for self-energies can move minus signs between the definition of $\Sigma(p^2)$ and the displayed counterterm insertion. The Lagrangian convention above fixes the rule used on this page.

## What counterterms are allowed?

The counterterm Lagrangian is constrained by the same principles that constrain the original theory.

| Principle | Counterterm consequence |
|---|---|
| Locality | Counterterms are local operators and derivatives. |
| Lorentz invariance | Counterterms are Lorentz scalars. |
| Internal symmetry | Counterterms must respect the symmetry unless it is explicitly broken or anomalous. |
| Gauge redundancy | Gauge-theory counterterms must respect Ward, Slavnov–Taylor, or BRST constraints. |
| Power counting | Renormalizable theories in four dimensions need finitely many dimension-four-or-less counterterms. |
| EFT logic | Effective theories include all symmetry-allowed operators up to the chosen order. |

For the $\mathbb Z_2$-symmetric scalar theory, with $\phi\mapsto-\phi$, the dimension-four-or-less local counterterms are

$$
1,
\qquad
\phi^2,
\qquad
\partial_\mu\phi\,\partial^\mu\phi,
\qquad
\phi^4.
$$

Odd operators such as $\phi$ and $\phi^3$ are local and relevant, but they are forbidden by the $\mathbb Z_2$ symmetry. If the theory lacks that symmetry, they generally must be included.

In an EFT, higher-dimension counterterms are not a failure. They are part of the point. Examples include

$$
\frac{c_6}{\Lambda^2}\phi^6,
\qquad
\frac{c_{\partial}}{\Lambda^2}\phi^2\partial_\mu\phi\,\partial^\mu\phi,
\qquad
\frac{c_{\Box}}{\Lambda^2}(\Box\phi)^2.
$$

They are suppressed by a high scale and ordered by power counting.

## Renormalization conditions

The counterterm Lagrangian tells us what can be adjusted. A renormalization condition tells us how it is adjusted.

For a stable scalar field, an on-shell scheme may require that the exact propagator has a pole at $p^2=m^2$ with unit residue. A coupling may be fixed by requiring that an amputated four-point function equals a specified value at a reference kinematic point.

MS and $\overline{\mathrm{MS}}$ use a different philosophy. They do not fix parameters directly by physical pole or scattering conditions. Instead, they subtract pole terms in dimensional regularization. In MS one subtracts powers of $1/\epsilon$; in $\overline{\mathrm{MS}}$ one subtracts the standard combination involving

$$
\frac{1}{\epsilon}-\gamma_E+\ln4\pi.
$$

The two approaches are both valid. They answer different practical questions:

| Scheme style | Best use |
|---|---|
| On-shell | Direct relation to stable-particle masses and residues. |
| Momentum subtraction | Clean off-shell normalization at chosen Euclidean momenta. |
| MS or $\overline{\mathrm{MS}}$ | Compact multi-loop calculations and renormalization group running. |

Changing finite counterterms changes the scheme. It changes the numerical values called $m$, $\lambda$, or $Z_\phi$, but not physical predictions after consistent parameter conversion.

## Order-by-order structure

Counterterms are determined recursively. At a fixed perturbative order, one includes ordinary loop diagrams and all lower-order counterterm insertions that contribute at that order.

At one-loop order, a two-point function receives

$$
\text{one-loop self-energy diagrams}
+
\text{tree diagrams with one-loop counterterms}.
$$

At two-loop order, it receives

$$
\text{two-loop self-energy diagrams}
+
\text{one-loop diagrams with one-loop counterterms}
+
\text{tree diagrams with two-loop counterterms}.
$$

This is why a counterterm diagram can look like a tree diagram while counting as a loop correction. The loop order lives in $\delta Z^{(n)}$, $\delta m^{2(n)}$, or $\delta\lambda^{(n)}$.

Subdivergences are handled the same way. A higher-loop graph may contain divergent subgraphs. Lower-order counterterm insertions subtract those subgraph divergences before the remaining overall divergence is removed by a higher-order counterterm.

## Local versus nonlocal terms

A local counterterm can cancel terms polynomial in external momenta and masses. For instance, a two-point counterterm can cancel a local expression of the form

$$
A+Bp^2+C m^2.
$$

It cannot cancel a branch cut or threshold logarithm such as

$$
\ln\frac{-p^2-i\epsilon}{\mu^2},
$$

because this is nonlocal analytic structure. Such nonlocal terms carry physical information about propagation, thresholds, and intermediate states.

This distinction is a useful diagnostic. Counterterms remove local regulator dependence. They do not erase the quantum dynamics. If a subtraction seems to remove a physical cut, the subtraction was not a local counterterm in the theory under discussion.

## Example: φ⁴ counterterms by target

In four-dimensional $\phi^4$ theory, the superficially divergent 1PI functions are the vacuum, two-point, and four-point functions. The counterterms match them as follows:

| Divergent object | Counterterm | Purpose |
|---|---|---|
| Vacuum diagrams | $-\delta\Lambda$ | Vacuum energy subtraction. |
| Two-point function at zero momentum | $-\frac12\delta m^2\phi^2$ | Mass-parameter subtraction. |
| Momentum-dependent two-point function | $\frac12\delta Z\partial_\mu\phi\partial^\mu\phi$ | Kinetic normalization subtraction. |
| Four-point 1PI function | $-\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4$ | Coupling subtraction. |

The finite parts of these counterterms are not fixed by finiteness alone. They are fixed by a scheme. That is why the same loop integral can produce different-looking finite renormalized answers in different books, while the same observable agrees after translation.

## Gauge-theory preview

In gauge theories, the idea is the same but the bookkeeping is stricter. Counterterms must respect gauge redundancy after gauge fixing. In QED, Ward identities relate charge and field renormalizations. In Yang–Mills theory, Slavnov–Taylor identities and BRST symmetry organize the allowed counterterms.

The scalar moral survives:

$$
\text{counterterms are local and symmetry-compatible.}
$$

The difference is that “symmetry-compatible” is more demanding in gauge theory. A naive local term may be forbidden because it violates gauge invariance or BRST consistency. That is why gauge-theory renormalization is treated in its own chapter.

## Common pitfalls

**Treating counterterms as new forces.** Counterterms are the same bare theory rewritten in renormalized variables. They are not additional phenomenological interactions unless an EFT deliberately includes new operator coefficients.

**Dropping counterterm diagrams because they have no loop.** A counterterm vertex may carry one-loop or two-loop order through its coefficient. Diagram topology alone does not determine perturbative order.

**Adding every local operator in a renormalizable calculation.** In a strictly renormalizable four-dimensional scalar theory, power counting and symmetry restrict the counterterms. In an EFT, the tower is larger but still ordered.

**Ignoring finite counterterms.** Divergent parts are fixed by finiteness; finite parts define the scheme. A finite counterterm can be as important as a divergent one when comparing schemes.

**Trying to subtract nonlocal physics.** Local counterterms cannot remove branch cuts, thresholds, or long-distance logarithms. Those structures are part of the prediction.

**Forgetting vacuum counterterms.** Vacuum diagrams cancel from many normalized correlators, but the vacuum-energy counterterm matters in the effective action and in any context where absolute vacuum energy is physical input.

## Relations to other pages

- [Bare and Renormalized Parameters](/perturbative-qft/renormalized-perturbation-theory/bare-and-renormalized-parameters/) defines the parameter split that produces $\mathcal L_{\rm ct}$.
- [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) explains the diagrammatic interpretation of the same local terms.
- [Superficial Degree of Divergence](/perturbative-qft/loop-expansion-regularization/superficial-degree-of-divergence/) predicts which local structures can be divergent by power counting.
- [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) motivates $\delta Z$ and $\delta m^2$.
- [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/) motivates $\delta\lambda$.
- [Vacuum Bubbles](/perturbative-qft/loop-expansion-regularization/vacuum-bubbles/) motivates $\delta\Lambda$.
- [Renormalization Conditions](/perturbative-qft/renormalized-perturbation-theory/renormalization-conditions/) will explain how counterterm coefficients are fixed.
- [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/) will specialize the counterterm choice to pole subtraction.

## Research status

The local counterterm Lagrangian is settled perturbative QFT technology. The scalar formulas here are textbook-standard once the convention for placing factors of $Z_\phi$ is fixed.

The active frontier is not the existence of counterterms, but their systematic use in difficult settings: multi-loop gauge theory, EFT operator bases, composite-operator mixing, evanescent operators in dimensional regularization, unstable particles, infrared subtraction, curved backgrounds, and automated renormalization pipelines.

## Exercises

### Exercise 1: Derive the scalar counterterm Lagrangian

Starting from

$$
\mathcal L_0
=
\frac12\partial_\mu\phi_0\partial^\mu\phi_0
-
\frac12m_0^2\phi_0^2
-
\frac{\lambda_0}{4!}\phi_0^4,
$$

and using

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
Z_\phi=1+\delta Z,
$$

$$
Z_\phi m_0^2=m^2+\delta m^2,
\qquad
Z_\phi^2\lambda_0=\mu^{2\epsilon}(\lambda+\delta\lambda),
$$

derive $\mathcal L_{\rm ren}$ and $\mathcal L_{\rm ct}$.

<details>
<summary><strong>Solution</strong></summary>

Substitution gives

$$
\mathcal L_0
=
\frac12Z_\phi\partial_\mu\phi\partial^\mu\phi
-
\frac12Z_\phi m_0^2\phi^2
-
\frac{Z_\phi^2\lambda_0}{4!}\phi^4.
$$

Using the definitions,

$$
\mathcal L_0
=
\frac12(1+\delta Z)\partial_\mu\phi\partial^\mu\phi
-
\frac12(m^2+\delta m^2)\phi^2
-
\frac{\mu^{2\epsilon}(\lambda+\delta\lambda)}{4!}\phi^4.
$$

The non-delta terms give

$$
\mathcal L_{\rm ren}
=
\frac12\partial_\mu\phi\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4,
$$

and the delta terms give

$$
\mathcal L_{\rm ct}
=
\frac12\delta Z\partial_\mu\phi\partial^\mu\phi
-
\frac12\delta m^2\phi^2
-
\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4.
$$

A constant term $-\delta\Lambda$ can be added to renormalize vacuum diagrams.

</details>

### Exercise 2: Two-point counterterm rule

Derive the two-point counterterm factor

$$
i(p^2\delta Z-\delta m^2)
$$

from

$$
\mathcal L_{\rm ct}^{(2)}
=
\frac12\delta Z\partial_\mu\phi\partial^\mu\phi
-
\frac12\delta m^2\phi^2.
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\phi(x)=\int_p e^{-ip\cdot x}\phi(p),
\qquad
\partial_\mu\phi(x)=\int_p(-ip_\mu)e^{-ip\cdot x}\phi(p).
$$

The quadratic counterterm action becomes

$$
S_{\rm ct}^{(2)}
=
\frac12\int_p\phi(-p)(p^2\delta Z-\delta m^2)\phi(p).
$$

In Lorentzian perturbation theory, an insertion from the action carries a factor of $i$, so the two-point counterterm is

$$
{i(p^2\delta Z-\delta m^2).}
$$

</details>

### Exercise 3: Symmetry forbids a φ³ counterterm

In the $\mathbb Z_2$-symmetric scalar theory with $\phi\mapsto-\phi$, explain why a counterterm proportional to $\phi^3$ is forbidden even though it is local.

<details>
<summary><strong>Solution</strong></summary>

The operator $\phi^3$ is odd under the symmetry:

$$
\phi^3\mapsto-\phi^3.
$$

A counterterm $\delta g_3\phi^3$ would therefore break the $\mathbb Z_2$ symmetry unless $\delta g_3=0$. If the regulator preserves the symmetry, loop divergences cannot require a symmetry-violating counterterm. Thus no $\phi^3$ counterterm is allowed in the $\mathbb Z_2$-symmetric theory.

</details>

### Exercise 4: Local counterterms cannot remove a branch cut

Can a local counterterm remove the term

$$
\ln\frac{-p^2-i\epsilon}{\mu^2}
$$

from a one-loop amplitude? Explain.

<details>
<summary><strong>Solution</strong></summary>

No. A local counterterm gives a polynomial in external momenta and masses, such as

$$
A+Bp^2+Cm^2+\frac{D}{\Lambda^2}p^4+\cdots.
$$

The logarithm is non-polynomial and has a branch cut. It represents nonlocal analytic structure associated with propagation and thresholds. A local counterterm can shift polynomial pieces, but it cannot remove a logarithmic branch cut.

</details>

### Exercise 5: EFT counterterms

In four dimensions, determine the mass dimension of

$$
(\Box\phi)^2.
$$

Why can it appear as an EFT counterterm but not as part of the dimension-four renormalizable scalar counterterm Lagrangian?

<details>
<summary><strong>Solution</strong></summary>

In four dimensions, $[\phi]=1$ and $[\Box]=2$, so

$$
[\Box\phi]=3.
$$

Therefore

$$
[(\Box\phi)^2]=6.
$$

The operator is local and even under $\phi\mapsto-\phi$, so it is allowed by the scalar symmetry. But it has dimension six, so its coefficient has mass dimension $-2$. It is not part of the dimension-four-or-less renormalizable counterterm Lagrangian. In an EFT, it can appear with a coefficient such as $c_{\Box}/\Lambda^2$ and is organized by the EFT power counting.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§14–20 and 27–28, for loop corrections, counterterms, schemes, and all-order perturbative structure.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 15–16 and 25, for counterterm determination and the logic of regularization and renormalization.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 18–23, for counterterms, renormalized perturbation theory, minimal subtraction, and RG.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 12, for the general structure of renormalization.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. III.3, for a physical discussion of counterterms and physical perturbation theory.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 8–10, for bare and renormalized QFT, minimal subtraction, and the RG perspective.

## Version history

- **2026-06-12:** Initial standardized page for the Renormalized Perturbation Theory chapter.
