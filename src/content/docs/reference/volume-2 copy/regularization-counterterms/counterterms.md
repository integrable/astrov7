---
title: "Counterterms"
description: "How counterterms encode local short-distance sensitivity, cancel regulator dependence, impose renormalization conditions, and enter Feynman rules."
sidebar:
  label: "Counterterms"
  order: 5
level: Graduate
status: "Polished draft"
source: "Coleman, renormalization lectures; Srednicki §§18–29; Schwartz ch. 19 and app. B; Weinberg Vol. I ch. 12; Zee ch. III.3; Zinn-Justin, renormalization chapters."
topics:
  - counterterms
  - local operators
  - renormalized perturbation theory
  - renormalization conditions
  - scheme dependence
canonicalTopics:
  - counterterms
  - renormalized-lagrangian
  - local-renormalization
  - renormalization-conditions
researchStatus:
  established:
    - "Counterterms are standard local terms in the regulated action that absorb regulator dependence and define renormalized parameters order by order in perturbation theory."
  active:
    - "The same logic becomes subtler in gauge theories, theories with anomalies, curved spacetime, operator mixing, nonperturbative definitions, and EFTs with large operator bases."
---

## Summary

**Counterterms** are local terms added to a regulated Lagrangian so that renormalized correlation functions, amplitudes, and observables have a finite and scheme-defined limit when the regulator is removed or changed.

The basic decomposition is

$$
\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}},
$$

where $\mathcal L_0$ is the bare regulated Lagrangian, $\mathcal L_{\text{ren}}$ is written in terms of renormalized parameters, and $\mathcal L_{\text{ct}}$ contains counterterms. In a real scalar theory with $\mathbb Z_2$ symmetry in four dimensions, for example,

$$
\mathcal L_{\text{ren}}
=\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4,
$$

and

$$
\mathcal L_{\text{ct}}
=\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\delta\lambda}{4!}\phi^4
-\delta\rho.
$$

Here $\delta Z$, $\delta m^2$, $\delta\lambda$, and $\delta\rho$ are chosen according to a renormalization scheme. Their divergent parts cancel regulator dependence. Their finite parts encode a convention for what the symbols $m$ and $\lambda$ mean.

Counterterms are not a trick for hiding infinities under the rug. They are the bookkeeping form of a physical statement: short-distance effects that cannot be resolved at long distances appear as **local operators**. A loop that is hard compared with external momenta cannot remember the detailed shape of the long-distance experiment; it can only contribute a polynomial in external momenta, which is exactly what a local term in the Lagrangian produces.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![A loop graph has an epsilon pole and a finite part, a counterterm vertex cancels the pole and adds a finite scheme choice, and the renormalized result is finite](/figures/renormalization-rg-eft/counterterm-cancellation-flow.svg)

<figcaption>

A counterterm cancels the local divergent part of a loop graph and may also include a finite part that defines the scheme. Pole cancellation is forced by finiteness; the finite remainder is a convention until it is tied to a renormalization condition or a measured input.

</figcaption>
</figure>

## Prerequisites

You should know [Divergences as Local Operators](/renormalization-rg-eft/why-renormalization/divergences-as-local-operators/), [Bare versus Renormalized](/renormalization-rg-eft/why-renormalization/bare-versus-renormalized/), [Regulator Dependence](/renormalization-rg-eft/why-renormalization/regulator-dependence/), and the regulator examples in this chapter. The main formulas use the conventions fixed in [Conventions and Notation](/renormalization-rg-eft/conventions/): mostly-minus metric, $d=4-2\epsilon$ in dimensional regularization, and

$$
\frac{1}{\bar\epsilon}=\frac{1}{\epsilon}-\gamma_E+\log 4\pi.
$$

## Core idea

A UV-divergent loop integral is not mysterious because it is large. It is mysterious because it asks the theory for information about arbitrarily short distances. The long-distance theory may not know that information. Counterterms say exactly which short-distance information must be supplied.

The crucial fact is locality. Suppose a one-loop contribution to a two-point function has large loop momentum $k$ compared with external momentum $p$. The integrand can be expanded as

$$
F(k,p)=F_0(k)+p_\mu F_1^\mu(k)+p_\mu p_\nu F_2^{\mu\nu}(k)+\cdots.
$$

After symmetric integration, Lorentz invariance and internal symmetries leave only allowed polynomial structures such as

$$
A+Bp^2+Cm^2+\cdots.
$$

In position space, a polynomial in momentum is a contact term with derivatives:

$$
A+Bp^2+\cdots
\quad\longleftrightarrow\quad
A\delta^{(d)}(x)+B\Box\delta^{(d)}(x)+\cdots.
$$

Those are local. Therefore the counterterms that cancel UV sensitivity are local operators. If a proposed subtraction is nonlocal, it is usually not a legitimate UV counterterm; it is probably trying to remove physical long-distance information.

The short slogan is

$$
\text{UV counterterms are local because short-distance ignorance is local at long distances.}
$$

## Setup and conventions

A bare scalar Lagrangian may be written as

$$
\mathcal L_0
=\frac12 Z_\phi\partial_\mu\phi\,\partial^\mu\phi
-\frac12 Z_{m^2}m^2\phi^2
-\frac{\mu^{2\epsilon}Z_\lambda\lambda}{4!}\phi^4
-\rho_0,
$$

where the field $\phi$, mass $m$, and coupling $\lambda$ on the right are renormalized quantities. Equivalently,

$$
Z_\phi=1+\delta Z,
\qquad
Z_{m^2}m^2=m^2+\delta m^2,
\qquad
\mu^{2\epsilon}Z_\lambda\lambda=\mu^{2\epsilon}\lambda+\delta\lambda.
$$

Then

$$
\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}}.
$$

The counterterm Lagrangian is treated perturbatively. Its terms give Feynman rules just as ordinary interactions do. For the scalar example above, the counterterm insertions are:

| Counterterm | Momentum-space effect |
|---|---|
| $\frac12\delta Z\partial_\mu\phi\partial^\mu\phi$ | two-point insertion proportional to $p^2\delta Z$ |
| $-\frac12\delta m^2\phi^2$ | two-point insertion proportional to $-\delta m^2$ |
| $-\frac{\delta\lambda}{4!}\phi^4$ | four-point insertion proportional to $-\delta\lambda$ |
| $-\delta\rho$ | vacuum-energy insertion |

The precise factors of $i$ depend on whether one is writing the action, the Feynman rule, the amputated 1PI function, or the invariant amplitude. Pages that perform diagrammatic calculations state the convention at the calculation site. The conceptual rule is simpler: a counterterm vertex contributes the same local momentum polynomial as the term in $\mathcal L_{\text{ct}}$.

## What counterterms accomplish

Counterterms do four related jobs.

First, they cancel regulator dependence in intermediate expressions. For example, a regulated two-point function may contain

$$
\Gamma^{(2)}_{\text{loop}}(p^2)
=A_\Lambda+B_\Lambda p^2+\Gamma^{(2)}_{\text{finite}}(p^2),
$$

where $A_\Lambda$ and $B_\Lambda$ diverge with the regulator. The counterterms $\delta m^2$ and $\delta Z$ are chosen so that the renormalized two-point function is finite.

Second, they define renormalization conditions. After the divergent part is removed, one may still choose finite pieces. For instance, in an on-shell scheme one may demand that the exact propagator have a pole at $p^2=m_{\text{phys}}^2$ with residue one. In a minimal-subtraction scheme one subtracts only pole parts and leaves finite constants to be handled by the relation between the scheme parameter and measured quantities.

Third, they preserve the form of the theory under quantum corrections. If the original Lagrangian contains every local operator allowed by the symmetries up to the required order in power counting, then loop-generated local terms can be reabsorbed into the coefficients of those operators.

Fourth, they expose when a symmetry cannot be kept. If no choice of local counterterms can preserve all desired Ward identities simultaneously, the failure is not bookkeeping; it is an anomaly. Counterterms can move an anomalous variation from one current to another, but they cannot make a genuine anomaly disappear.

## Counterterms are local, not arbitrary

It is tempting to imagine that any divergent expression can be canceled by inventing a compensating expression with the opposite divergence. That is not renormalization. The allowed counterterms are restricted by locality, symmetries, field content, and power counting.

A local counterterm has the form

$$
\int d^d x\,c_i\mathcal O_i(x),
$$

where $\mathcal O_i(x)$ is a local operator built from fields and finitely many derivatives at the same point. In momentum space, such a term gives a polynomial in external momenta. For example,

$$
\int d^d x\,\phi\Box\phi
\quad\longrightarrow\quad
-p^2\widetilde\phi(p)\widetilde\phi(-p),
$$

up to integration-by-parts and sign conventions. By contrast, a term such as

$$
\int d^d x\,d^d y\,\phi(x)K(x-y)\phi(y)
$$

is nonlocal unless $K(x-y)$ is supported at coincident points or has a derivative expansion valid in a specified low-energy regime. Nonlocal dependence such as $\log(-p^2/m^2)$ or $\sqrt{-p^2}$ usually carries physical information about propagation, thresholds, or long-distance modes. It should not be subtracted away by UV counterterms.

:::tip[The counterterm smell test]
A legitimate UV counterterm should look like something that could have been written in the local action before doing the loop integral. If the proposed subtraction knows about thresholds, branch cuts, or distant points in spacetime, it is probably not a UV counterterm.
:::

## A scalar one-loop template

Consider real $\phi^4$ theory in four dimensions with $\mathbb Z_2$ symmetry. The renormalized interaction is

$$
\mathcal L_{\text{int}}=-\frac{\lambda}{4!}\phi^4.
$$

At one loop, the two-point function receives a tadpole correction. Its divergent part is momentum-independent, so it requires a mass counterterm but no wavefunction counterterm at this order:

$$
\delta m^2\neq0,
\qquad
\delta Z=0
\quad\text{at one loop in }\phi^4\text{ theory}.
$$

The four-point function receives bubble corrections in the $s$, $t$, and $u$ channels. The divergent part is independent of the external momenta at leading order in the UV expansion, so it is canceled by the quartic counterterm $\delta\lambda$.

In a common $\overline{\mathrm{MS}}$ convention, the pole parts have the schematic form

$$
\delta m^2\propto \frac{\lambda m^2}{16\pi^2\bar\epsilon},
\qquad
\delta\lambda\propto \frac{3\lambda^2}{16\pi^2\bar\epsilon},
\qquad
\delta Z=0\quad\text{at one loop}.
$$

The proportionality sign is intentional here: the exact sign and placement of $\mu^{2\epsilon}$ depend on the convention used for $\mathcal L_{\text{ct}}$, for the 1PI function, and for MS versus $\overline{\mathrm{MS}}$. What is invariant is the structure: the two-point divergence is local and mass-like; the four-point divergence is local and quartic; wavefunction renormalization begins later in this theory.

The same logic is more important than the example. A self-energy divergence polynomial in $p^2$ produces field-strength and mass counterterms. A vertex divergence polynomial in external momenta produces local interaction counterterms. Vacuum bubbles produce a vacuum-energy counterterm. In gauge theories, Ward or Slavnov–Taylor identities tie different counterterms together.

## Counterterms and renormalization conditions

A counterterm is not fully specified by saying "cancel the infinity." There is also a finite part, and that finite part is a convention until it is tied to a measurement.

Suppose a renormalized two-point 1PI function has the form

$$
\Gamma_R^{(2)}(p^2)=p^2-m^2-\Pi_R(p^2).
$$

An on-shell scheme may impose

$$
\Pi_R(m_{\text{phys}}^2)=0,
\qquad
\left.\frac{d\Pi_R}{dp^2}\right|_{p^2=m_{\text{phys}}^2}=0.
$$

These conditions say that $m_{\text{phys}}$ is the pole location and that the residue is normalized in a chosen way. A minimal-subtraction scheme instead removes the pole part in $\epsilon$ and defines $m(\mu)$ by the resulting convention. The same physical pole mass is then obtained only after relating $m(\mu)$ to a measured quantity.

The moral is

$$
\text{counterterms define coordinates on theory space; observables define physics.}
$$

Two schemes can use different counterterms and still describe the same physics if the renormalized parameters are translated consistently.

## Counterterms as Feynman-rule vertices

In renormalized perturbation theory, counterterms are inserted as vertices. This avoids a common conceptual trap. We do not first compute with bare quantities, discover infinities, panic, and then repair the answer. Instead, the perturbative expansion is organized from the start as

$$
\text{renormalized diagrams}
+\text{counterterm diagrams}.
$$

For a two-point function, one writes schematically

$$
\Gamma_R^{(2)}(p^2)
=\bigl[\Gamma_{\text{tree}}^{(2)}(p^2)
+\Gamma_{\text{loop}}^{(2)}(p^2)\bigr]
+\Gamma_{\text{ct}}^{(2)}(p^2).
$$

For a four-point function,

$$
\Gamma_R^{(4)}
=\bigl[\Gamma_{\text{tree}}^{(4)}
+\Gamma_{\text{loop}}^{(4)}\bigr]
+\Gamma_{\text{ct}}^{(4)}.
$$

At higher orders, counterterm insertions appear inside loop graphs. That is not double counting. It is what makes the subtraction recursive: subdivergences are canceled by lower-order counterterms, while the remaining overall divergence is canceled by a counterterm at the current order.

This recursive structure is the perturbative content of renormalizability. One must be able to cancel all UV subdivergences and overall divergences using local counterterms consistent with the symmetries.

## Symmetry constraints

If the regulator preserves a symmetry, the counterterms can usually be chosen to preserve it as well. For example, a $\mathbb Z_2$ symmetry $\phi\to-\phi$ forbids odd counterterms such as $\phi$ and $\phi^3$. Lorentz invariance forbids a single-derivative scalar counterterm in an ordinary relativistic scalar theory. Gauge invariance relates field-strength and vertex counterterms through Ward or Slavnov–Taylor identities.

If a regulator breaks a symmetry, one may have to add finite symmetry-restoring counterterms. This is common in practical calculations. A hard cutoff may break gauge invariance if applied carelessly; a lattice regulator may break continuum rotation symmetry down to a discrete subgroup; dimensional regularization has subtleties with $\gamma^5$ and Levi-Civita tensors. The test is whether a symmetry-preserving renormalized theory can be recovered after adding allowed local counterterms.

If it cannot, the symmetry is anomalous. The difference between a regulator artifact and an anomaly is sharp:

| Situation | Meaning |
|---|---|
| Symmetry-breaking terms can be removed by local counterterms | regulator artifact or bad scheme choice |
| No local counterterm restores all desired identities | genuine anomaly |

This distinction matters enormously in gauge theory. A global anomaly can be a physical feature. A gauge anomaly is an inconsistency unless canceled by the field content.

## Finite counterterms and scheme changes

A finite counterterm changes the renormalization scheme. For a coupling $g$, a finite redefinition might be

$$
g'=g+a g^3+O(g^5).
$$

This changes the beta function coefficients beyond the universal part and changes the finite expression assigned to intermediate Green functions. It does not change physical observables if all quantities are transformed consistently.

In this language, a scheme is a rule for choosing the finite parts of counterterms. Common choices include:

| Scheme | Counterterm philosophy |
|---|---|
| On-shell | choose counterterms so masses and residues match physical poles |
| MOM | choose Green functions at a subtraction momentum $p^2=-\mu^2$ |
| MS | subtract only $1/\epsilon$ poles |
| $\overline{\mathrm{MS}}$ | subtract $1/\bar\epsilon$ poles |
| Wilsonian cutoff | choose local couplings at cutoff $\Lambda$ |

No scheme is universally best in all problems. On-shell schemes are directly physical but can be awkward with massless particles or unstable states. Minimal subtraction is elegant for beta functions and high-energy calculations but defines parameters indirectly. Wilsonian schemes are conceptually transparent for EFT and locality, but calculations can be regulator-dependent in appearance.

## Counterterms in EFT

In a renormalizable theory, the required counterterms have the same form as a finite set of operators already present in the Lagrangian. In an EFT, the Lagrangian contains an infinite tower:

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\le d}
+\sum_i\frac{C_i}{M^{\Delta_i-d}}\mathcal O_i.
$$

Loops generate counterterms for higher-dimension operators. This is not a failure. It is the mechanism that makes EFT predictive: at any fixed order in $Q/M$, only finitely many operators contribute.

For example, a dimension-six operator inserted in a loop may require a dimension-six counterterm and perhaps, depending on the theory, counterterms for other operators of the same or lower order allowed by symmetry. Operator mixing is the systematic study of this effect.

The old slogan "nonrenormalizable theories need infinitely many counterterms" is true but incomplete. The modern EFT statement is sharper:

$$
\text{infinitely many counterterms are allowed, but only finitely many are needed at any fixed accuracy.}
$$

## Common pitfalls

**Thinking counterterms are fake.** Counterterms are not fake interactions. They are local terms in the action. What is unphysical is the split between a renormalized term and its counterterm before a scheme and parameter definition are specified.

**Subtracting nonlocal physics.** UV counterterms are local. Nonanalytic dependence such as logarithms with branch cuts, thresholds, and imaginary parts usually carries physical long-distance information.

**Forgetting finite parts.** Canceling infinities does not uniquely define a renormalized theory. Finite parts specify the renormalization scheme and must be tied to physical input.

**Violating symmetries accidentally.** Counterterms must respect exact symmetries unless the point is to study explicit breaking or anomalies. If the regulator breaks a symmetry, the restoration must be checked.

**Treating counterterms as afterthoughts.** In renormalized perturbation theory, counterterm diagrams are part of the calculation. Leaving them until the end is a reliable way to create bookkeeping errors.

## Relations to other pages

This page explains the local terms that implement the lessons of [Divergences as Local Operators](/renormalization-rg-eft/why-renormalization/divergences-as-local-operators/) and [Regulator Dependence](/renormalization-rg-eft/why-renormalization/regulator-dependence/). The next page, [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/), explains when the list of required counterterms is finite by engineering dimension. Later, [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/) uses counterterms as a calculation framework, while [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/) develops the matrix version for composite operators and EFT bases.

## Research status

The basic perturbative counterterm framework is settled. The BPHZ, Callan–Symanzik, Wilsonian, dimensional-regularization, algebraic-renormalization, and EFT languages package the same locality principle in different ways.

Active and subtle areas include counterterms in chiral gauge theories, evanescent operators in dimensional regularization, field redefinitions in EFT bases, curved-spacetime counterterms, boundary and defect counterterms, nonperturbative definitions, and the algebraic treatment of gauge symmetry and BRST cohomology. These are not failures of the basic idea; they are places where locality, symmetry, and scheme dependence must be handled with particular care.

## Exercises

### Exercise 1: Deriving a scalar counterterm Lagrangian

Let

$$
\mathcal L_0
=\frac12 Z_\phi\partial_\mu\phi\partial^\mu\phi
-\frac12 Z_m m^2\phi^2
-\frac{Z_\lambda\lambda}{4!}\phi^4,
$$

with

$$
Z_\phi=1+\delta Z,
\qquad
Z_m=1+\delta_m,
\qquad
Z_\lambda=1+\delta_\lambda.
$$

Split $\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}}$.

<details><summary><strong>Solution</strong></summary>

The renormalized part is

$$
\mathcal L_{\text{ren}}
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4.
$$

The counterterm part is the remainder:

$$
\mathcal L_{\text{ct}}
=\frac12\delta Z\partial_\mu\phi\partial^\mu\phi
-\frac12\delta_m m^2\phi^2
-\frac{\delta_\lambda\lambda}{4!}\phi^4.
$$

If desired, one can rename $\delta m^2=\delta_m m^2$ and $\delta\lambda=\delta_\lambda\lambda$.

</details>

### Exercise 2: Why a logarithm is not a local counterterm

A loop correction contains a term proportional to

$$
p^2\log\frac{-p^2-i\epsilon}{\mu^2}.
$$

Can this term be canceled by a local two-point counterterm?

<details><summary><strong>Solution</strong></summary>

No. A local two-point counterterm gives a polynomial in $p^2$, such as $A+Bp^2+C(p^2)^2+\cdots$. The logarithm is nonanalytic: it has a branch cut and therefore encodes physical long-distance or threshold information. A counterterm can subtract a local polynomial part, such as a divergent coefficient multiplying $p^2$, but it cannot subtract the nonlocal logarithmic dependence without changing the physical theory.

</details>

### Exercise 3: Counterterms and symmetry

In a real scalar theory with exact $\mathbb Z_2$ symmetry $\phi\to-\phi$, which of the following counterterms are allowed?

$$
\phi,
\qquad
\phi^2,
\qquad
\phi^3,
\qquad
\phi^4,
\qquad
\partial_\mu\phi\partial^\mu\phi.
$$

<details><summary><strong>Solution</strong></summary>

The $\mathbb Z_2$-even operators are allowed:

$$
\phi^2,
\qquad
\phi^4,
\qquad
\partial_\mu\phi\partial^\mu\phi.
$$

The odd operators $\phi$ and $\phi^3$ are forbidden if the symmetry is exact. They may appear only if the symmetry is explicitly broken, spontaneously expanded around a non-symmetric field coordinate, or violated by the regulator and then restored by appropriate finite counterterms.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially "Renormalization and Symmetry" and the renormalization parts of "Secret Symmetry."
- Sidney Coleman, *Lectures on Quantum Field Theory*, especially the chapters on divergences, counterterms, renormalization, and QED renormalization.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on higher-order corrections, renormalizability, renormalization schemes, the renormalization group, and EFT.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 18–23 and appendix B.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, and Vol. II, chapters 17–18.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on renormalization, BPHZ subtraction, and critical phenomena.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially chapters 2–4.

## Version history

- 2026-06-17: First polished draft. Introduced counterterms as local terms, explained their role in renormalized perturbation theory, symmetry constraints, finite scheme dependence, and EFT operator towers.
