---
title: "Gauge-Invariant Regularization"
description: "A guide to regulators for gauge theories, why naive cutoffs can violate gauge symmetry, and how Ward, Slavnov–Taylor, and BRST identities constrain allowed counterterms."
sidebar:
  label: "Gauge-Invariant Regularization"
  order: 5
level: Graduate
status: "Polished draft"
source: "Coleman lectures on renormalization and QED; Srednicki 2007, gauge-theory beta functions and background field gauge; Weinberg Vol. II, gauge-theory renormalization; Schwartz 2014, regularization and Yang–Mills renormalization; Zinn-Justin 2021, renormalization with symmetries."
topics:
  - gauge-invariant regularization
  - Ward identities
  - Slavnov–Taylor identities
  - BRST symmetry
  - dimensional regularization
  - lattice gauge theory
canonicalTopics:
  - gauge-invariant-regularization
  - regularization-of-gauge-theories
  - brst-preserving-renormalization
researchStatus:
  established:
    - "Regulators for gauge theories must preserve gauge/BRST identities or allow their restoration by local counterterms in anomaly-free theories."
  active:
    - "Regulating chiral gauge theories, maintaining supersymmetry together with gauge symmetry, handling evanescent operators, and constructing nonperturbative chiral lattice gauge theories remain technically subtle."
---

## Summary

A regulator is **gauge-invariant** only if it respects the quantum identities that express gauge redundancy. In a perturbative gauge-fixed calculation this usually means Ward identities in QED and Slavnov–Taylor or BRST identities in nonabelian gauge theory. In a nonperturbative lattice definition it means exact invariance under lattice gauge transformations, usually implemented through link variables.

This page explains why gauge theory is less forgiving than scalar theory. In scalar theory, a clumsy regulator may be ugly but still harmless after suitable local counterterms. In gauge theory, a clumsy regulator can generate terms that look like a photon mass, spoil transversality of vacuum polarization, or destroy the relations among vertex and wavefunction counterterms. If the breaking is local and the gauge symmetry is anomaly-free, the identities can often be restored by counterterms. If the breaking is a true gauge anomaly, no choice of local counterterms repairs the theory.

The useful slogan is

$$
\text{gauge-invariant regularization}
\quad\text{means}\quad
\text{regularization compatible with gauge redundancy, not merely a nice cutoff}.
$$

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Map of gauge-invariant regularization: a regulated bare theory either preserves BRST or Ward identities, so divergences obey restricted counterterm forms, or breaks the identities and requires local restoring counterterms if the gauge symmetry is anomaly-free; otherwise there is an obstruction.](/figures/renormalization-rg-eft/gauge-invariant-regularization-map.svg)

<figcaption>

A regulator that preserves the gauge or BRST identities restricts divergent terms automatically. A regulator that breaks them may still be usable in an anomaly-free theory, but only if the breaking is local and can be canceled by counterterms. A genuine gauge anomaly is not a scheme choice.

</figcaption>
</figure>

## Prerequisites

You should know [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/), [QED Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/qed-beta-function/), [Yang–Mills Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/yang-mills-beta-function/), and the basic role of gauge fixing in perturbation theory. The next page, [Ward Identities and Renormalization](/renormalization-rg-eft/gauge-theories-and-rg/ward-identities-and-renormalization/), explains the main identities in more detail.

## Core idea

Gauge symmetry is not an ordinary symmetry of states. It is a redundancy in the description. This makes regularization unusually delicate.

A regulator should make divergent expressions finite while preserving the structural identities that say unphysical polarizations, gauge choices, and ghost degrees of freedom do not contaminate physical observables. In QED these identities are Ward–Takahashi identities. In nonabelian gauge theory they are Slavnov–Taylor identities, most cleanly organized by BRST symmetry.

For example, the QED vacuum polarization tensor must be transverse:

$$
q_\mu\Pi^{\mu\nu}(q)=0.
$$

This forbids a photon mass counterterm, because a local mass term

$$
\frac12 m_\gamma^2 A_\mu A^\mu
$$

would contribute a term proportional to $\eta^{\mu\nu}$ that is not transverse. A regulator that produces such a term is not respecting gauge redundancy. One can sometimes subtract it by hand, but then the calculation must prove that all such gauge-breaking local terms have been identified and removed consistently.

The point is not aesthetic. Gauge identities are what make gauge theory predictive and unitary. They relate counterterms, remove unphysical modes from the $S$-matrix, forbid some operators, and make the renormalized theory live on the same physical configuration space as the original gauge theory.

## Setup and conventions

We use the mostly-minus convention

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
$$

and define the covariant derivative in a representation $R$ by

$$
D_\mu=\partial_\mu-ig A_\mu^a T_R^a.
$$

For a nonabelian gauge field,

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
+g f^{abc}A_\mu^b A_\nu^c,
$$

and the Yang–Mills action is

$$
S_{\mathrm{YM}}
=-\frac14\int d^4x\,F_{\mu\nu}^aF^{a\mu\nu}.
$$

Perturbation theory requires gauge fixing. In a covariant gauge one adds schematically

$$
\mathcal L_{\mathrm{gf}}
=-\frac{1}{2\xi}(\partial_\mu A^{a\mu})^2,
$$

and in nonabelian theory also the Faddeev–Popov ghost term. After gauge fixing, the original gauge invariance is no longer manifest as a naive invariance of the gauge-fixed Lagrangian. It is replaced by BRST invariance. A regulator that preserves the BRST symmetry is usually the perturbative version of a gauge-invariant regulator.

When this page says that a regulator "preserves gauge invariance," read it in the appropriate context:

| Context | Meaning of gauge-invariant regularization |
|---|---|
| Classical or Wilsonian action | local terms are built from gauge-covariant objects such as $F_{\mu\nu}$ and $D_\mu$ |
| Gauge-fixed perturbation theory | Ward or Slavnov–Taylor identities are preserved, usually through BRST symmetry |
| Lattice gauge theory | lattice action and measure are exactly invariant under lattice gauge transformations |
| Chiral gauge theory | the regulator preserves the gauge symmetry if and only if the gauge anomaly cancels and the construction realizes this cancellation |

## Why naive cutoffs can fail

A hard momentum cutoff looks simple:

$$
\int d^4\ell
\quad\longrightarrow\quad
\int_{|\ell|<\Lambda} d^4\ell.
$$

In a scalar loop this often gives a useful physical picture of short-distance sensitivity. In a gauge loop it can break the algebraic manipulations behind Ward identities. The reason is that Ward identities frequently use shifts of loop momentum, integration by parts in momentum space, and tensor decompositions with no boundary term. A hard cutoff introduces a boundary in momentum space, so a shift like

$$
\ell\longrightarrow \ell+q
$$

changes the integration region. What was supposed to vanish as a change of variables can leave a surface term.

This is not a mere technical footnote. In QED, transversality of the vacuum polarization follows from charge conservation and the Ward identity. A regulator that violates the identity can produce an expression of the schematic form

$$
\Pi^{\mu\nu}_{\Lambda}(q)
=A\Lambda^2\eta^{\mu\nu}
+B(q^2\eta^{\mu\nu}-q^\mu q^\nu)\log\Lambda
+\cdots.
$$

The second tensor structure is transverse. The first is not. It behaves like a photon mass term, which gauge invariance forbids.

A careful cutoff calculation can still be useful if one subtracts the noninvariant local term and imposes the Ward identity as a renormalization condition. But then the phrase "cutoff regularization" hides extra work: one is not merely cutting off momenta; one is also restoring the gauge symmetry by a specific choice of counterterms.

:::note[Hard cutoffs are not evil]
A hard cutoff is often the clearest way to see power sensitivity and Wilsonian scale separation. The warning is narrower: a naive momentum cutoff is usually not a gauge-invariant regulator for continuum gauge-theory perturbation theory.
:::

## Dimensional regularization

Dimensional regularization is the standard perturbative regulator for gauge theories because it preserves the algebraic properties needed for many Ward and Slavnov–Taylor identities. Loop integrals are analytically continued to

$$
d=4-2\epsilon,
$$

and the measure has no hard boundary in momentum space. Shifts of integration variables remain legitimate inside the analytically continued integrals, and tensor integrals remain Lorentz-covariant in $d$ dimensions.

For vectorlike QED and ordinary Yang–Mills theory, dimensional regularization combined with minimal subtraction or $\overline{\mathrm{MS}}$ is usually the cleanest way to compute beta functions and anomalous dimensions. It keeps gauge invariance sufficiently manifest that the allowed counterterms are exactly the gauge-invariant ones, plus gauge-fixing and ghost terms constrained by BRST symmetry.

The advantages are:

| Feature | Why it matters in gauge theory |
|---|---|
| no momentum-space boundary | loop-momentum shifts do not generate cutoff-surface artifacts |
| Lorentz covariance in $d$ dimensions | tensor decompositions remain covariant |
| compatibility with gauge fixing and ghosts | Slavnov–Taylor identities are manageable |
| logarithmic divergences become $1/\epsilon$ poles | beta functions are extracted cleanly |
| scaleless integrals vanish | many massless gauge-theory calculations simplify |

But dimensional regularization is not magic. It has important caveats.

First, it hides power divergences. A quadratic cutoff sensitivity may appear as scheme-dependent threshold sensitivity rather than as a visible $\Lambda^2$ term. This is why dimensional regularization is excellent for beta functions but not always the best pedagogical regulator for naturalness.

Second, objects intrinsically tied to four dimensions need care. The most famous example is $\gamma^5$. Chiral gauge theories require a prescription that preserves gauge consistency. One cannot assume that all four-dimensional spinor identities continue harmlessly to $d=4-2\epsilon$.

Third, evanescent operators can appear. These are operators that vanish in the physical dimension but affect intermediate renormalization in $d$ dimensions. They become important in higher-loop EFT calculations, chiral theories, and operator mixing.

## Pauli–Villars and massive regulator fields

Pauli–Villars regularization cancels high-momentum behavior by adding fictitious heavy fields with wrong-sign contributions. In a simple QED fermion loop, one may replace a divergent expression schematically by

$$
I(m)-I(M),
\qquad M\gg m,
$$

where the heavy regulator field has the same gauge coupling. Because the regulator field couples gauge-covariantly, Pauli–Villars can preserve the QED Ward identity in simple vectorlike cases.

The method becomes less pleasant in nonabelian gauge theory. Gauge boson loops, ghost loops, nonlinear gauge symmetry, and chiral matter make it hard to introduce massive regulator fields without breaking the very symmetry one wants to preserve. Modern perturbative nonabelian calculations therefore usually prefer dimensional regularization or more elaborate covariant higher-derivative regulators.

The moral is:

$$
\text{Pauli–Villars is not automatically gauge-invariant; the regulator fields must transform correctly.}
$$

For chiral gauge theories, Pauli–Villars also exposes the anomaly issue sharply. If the gauge symmetry is anomalous, there is no regulator that preserves it. If the anomaly cancels, a consistent regulator must implement the cancellation across the full fermion content, not field by field in isolation.

## Lattice gauge regularization

Lattice gauge theory is the cleanest example of an exact gauge-invariant regulator. The basic variables are not continuum gauge fields $A_\mu(x)$ but link variables

$$
U_\mu(n)\in G,
$$

living on links from lattice site $n$ to $n+\hat\mu$. Under a lattice gauge transformation $\Omega(n)\in G$,

$$
U_\mu(n)\longrightarrow
\Omega(n)U_\mu(n)\Omega(n+\hat\mu)^{-1}.
$$

The elementary plaquette variable is

$$
U_{\mu\nu}(n)
=U_\mu(n)U_\nu(n+\hat\mu)
U_\mu(n+\hat\nu)^{-1}U_\nu(n)^{-1}.
$$

It transforms by conjugation at the base point,

$$
U_{\mu\nu}(n)
\longrightarrow
\Omega(n)U_{\mu\nu}(n)\Omega(n)^{-1},
$$

so $\operatorname{Re}\operatorname{tr}(1-U_{\mu\nu})$ is gauge invariant. The Wilson plaquette action is therefore exactly gauge invariant at nonzero lattice spacing $a$.

This is a stronger statement than perturbative gauge invariance. The lattice path integral is a finite-dimensional integral over compact group variables for finite volume and nonzero $a$. Gauge invariance is built into the variables themselves.

The price is that other symmetries become less manifest. Continuous Euclidean rotation symmetry is reduced to the lattice rotation group and must be recovered in the continuum limit. Chiral symmetry is subtle because of fermion doubling and the Nielsen–Ninomiya obstruction. Chiral lattice gauge theories require special constructions, such as domain-wall or overlap ideas, and careful anomaly cancellation.

## Higher covariant derivative regulators

Another gauge-covariant strategy is to improve high-momentum behavior by adding higher-derivative terms built from covariant derivatives. For example, one may schematically modify a gauge kinetic term by

$$
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
\quad\longrightarrow\quad
-\frac14F_{\mu\nu}^a
\left[1+\frac{D^2}{\Lambda^2}+\cdots\right]
F^{a\mu\nu}.
$$

Because $D_\mu$ is gauge covariant, the new terms can be written in a gauge-invariant way before gauge fixing. This improves ultraviolet behavior while keeping gauge covariance more visible than a naive momentum cutoff.

However, higher covariant derivatives do not always regularize every divergence by themselves. Residual one-loop divergences may remain and require additional regulators. The method is conceptually important because it is Wilsonian and gauge-covariant, but it is usually more cumbersome than dimensional regularization for standard perturbative calculations.

## Gauge fixing, ghosts, and BRST symmetry

Gauge fixing is not optional in continuum perturbation theory. The gauge-field kinetic operator has zero modes along gauge orbits, so one cannot invert it to get a propagator until a gauge condition has been imposed.

The gauge-fixed nonabelian path integral contains ghosts because the Faddeev–Popov determinant depends on the gauge field. The gauge-fixed action is no longer invariant under the original gauge transformation, but it is invariant under BRST transformations. In schematic form,

$$
s A_\mu^a=D_\mu c^a,
\qquad
s c^a=-\frac12 g f^{abc}c^b c^c,
\qquad
s\bar c^a=B^a,
\qquad
sB^a=0,
$$

where $s$ is a nilpotent Grassmann-odd operation, $c^a$ is the ghost, $\bar c^a$ the antighost, and $B^a$ an auxiliary field.

BRST symmetry is the bookkeeping device that remembers gauge redundancy after gauge fixing. The regulator should preserve this symmetry, or else the violation must be tracked and canceled. The corresponding identities are the Slavnov–Taylor identities.

The practical implication is severe: one cannot renormalize every vertex independently. The ghost-gluon vertex, three-gluon vertex, four-gluon vertex, gauge-field wavefunction, ghost wavefunction, gauge coupling, and gauge-fixing parameter are tied together by BRST symmetry.

## What if the regulator breaks gauge symmetry?

Suppose a regulator breaks gauge symmetry. Is the calculation doomed? Not necessarily.

The key test is whether the breaking is local and removable. If the regulated effective action violates a Ward or Slavnov–Taylor identity by local terms, and if the gauge theory is anomaly-free, then one can often add local counterterms to restore the identity order by order. This is the algebraic-renormalization viewpoint.

Schematically, let $\mathcal S(\Gamma)$ denote the Slavnov–Taylor functional identity for the renormalized effective action $\Gamma$. A regulator might produce

$$
\mathcal S(\Gamma_\Lambda)=\Delta_\Lambda.
$$

If $\Delta_\Lambda$ is a local BRST-exact breaking, one may cancel it by adding a local counterterm. If $\Delta_\Lambda$ contains a nontrivial BRST cohomology class, it is an anomaly. Then no local counterterm restores the symmetry.

This distinction is the difference between an inconvenient regulator and an inconsistent gauge theory.

## Gauge anomalies as regulator obstructions

A gauge anomaly is not a regulator artifact. It is the statement that no regulator and counterterm prescription can preserve the gauge symmetry of the quantum theory.

For a chiral gauge theory, triangle diagrams can produce a gauge variation proportional to a group-theoretic anomaly coefficient. If the fermion representation content satisfies the anomaly-cancellation conditions, the obstruction cancels among fields. If it does not, the gauge theory is not a consistent quantum theory with that gauge group and matter content.

The contrast with global anomalies is important. A global symmetry may be anomalous; that means it cannot be gauged but can still be a meaningful anomalous global symmetry. A gauge symmetry is redundancy. If a gauge redundancy is anomalous, the theory has too many unphysical degrees of freedom and no consistent gauge-invariant Hilbert space.

## Scheme dependence versus symmetry breaking

A scheme change is a finite redefinition of parameters and fields. It changes coordinates on the space of renormalized descriptions. A violation of a gauge identity is not automatically a harmless scheme change.

For example, changing from MS to $\overline{\mathrm{MS}}$ changes finite constants in counterterms. It does not permit a photon mass. A photon mass in QED changes the physical content by introducing a third photon polarization. That is not a coordinate redefinition of massless QED.

A useful diagnostic is:

| Change | Usually a scheme choice? | Why |
|---|---:|---|
| finite redefinition of $g(\mu)$ | yes | same local operator, different coordinate |
| different subtraction point | yes | same theory described at different scale |
| adding a gauge-invariant higher-dimension operator | EFT basis or matching choice | changes truncation data, not gauge redundancy |
| adding $m_\gamma^2 A_\mu A^\mu$ to QED | no | violates gauge redundancy and changes states |
| violating a Slavnov–Taylor identity | no, unless restored | unphysical modes may fail to decouple |
| anomaly in a gauge symmetry | no | obstruction to the quantum theory |

## Practical hierarchy of regulators

For most graduate-level calculations, use the following hierarchy.

For perturbative QED, Yang–Mills, and QCD in ordinary vectorlike theories, dimensional regularization with MS or $\overline{\mathrm{MS}}$ is the default. It is efficient, symmetry-compatible, and directly produces beta functions and anomalous dimensions.

For Wilsonian intuition, naturalness, and EFT threshold sensitivity, use a cutoff picture, but do not pretend a naive momentum cutoff is automatically gauge-invariant. Interpret the cutoff as a physical scale or use gauge-covariant cutoff constructions when gauge identities matter.

For nonperturbative gauge theory, lattice gauge theory is the canonical regulator. It preserves gauge invariance exactly through link variables, although chiral symmetry and continuum spacetime symmetry require care.

For formal proofs of renormalization with symmetries, use BRST identities and algebraic renormalization. The regulator may be a tool, but the real result is that all allowed counterterms can be classified by locality, ghost number, dimension, and BRST cohomology.

## Common pitfalls

**Saying "gauge-invariant regulator" when only Lorentz invariance is preserved.** Lorentz covariance is not enough. The regulator must preserve the gauge or BRST identities, or the calculation must restore them.

**Trusting a hard cutoff inside a Ward identity.** Momentum shifts that are harmless in dimensional regularization can generate boundary terms with a hard cutoff.

**Confusing gauge fixing with gauge breaking.** Gauge fixing deliberately removes redundant integration volume. Done correctly, it preserves BRST symmetry and does not break physical gauge consistency.

**Treating a gauge anomaly as a bad counterterm choice.** A genuine gauge anomaly is an obstruction. It is not fixed by choosing MS instead of on-shell renormalization.

**Thinking lattice gauge theory is "less gauge invariant" because it has a cutoff.** It is often more exactly gauge invariant than continuum perturbation theory. The cutoff is geometric: link variables transform exactly under lattice gauge transformations.

**Forgetting chiral subtleties.** Dimensional regularization, Pauli–Villars, and lattice regulators all need special care for chiral fermions. Vectorlike intuition can mislead.

## Relations to other pages

This page explains the regulator side of the story. [Ward Identities and Renormalization](/renormalization-rg-eft/gauge-theories-and-rg/ward-identities-and-renormalization/) explains how the identities constrain counterterms and renormalization constants.

The pages [QED Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/qed-beta-function/) and [Yang–Mills Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/yang-mills-beta-function/) show what the identities protect in one-loop running. [Background Field Method](/renormalization-rg-eft/gauge-theories-and-rg/background-field-method/) gives a method in which gauge covariance of the effective action is especially visible. The more general role of counterterms is developed in [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), while anomaly obstructions belong to the Symmetry, Anomalies, and Topology volume.

## Research status

The basic message of this page is settled: gauge theories require regulators and counterterms compatible with gauge or BRST identities, and genuine gauge anomalies are obstructions to gauging.

The subtle cases remain active in practice. Chiral gauge theories, lattice chiral fermions, supersymmetric regulators, dimensional regularization with $\gamma^5$, evanescent operators, gauge-invariant Wilsonian exact RG formulations, and multi-loop EFT operator mixing all require careful convention-specific treatments. In these topics the slogan "use a gauge-invariant regulator" is not enough; one must say exactly which identities are preserved and how.

## Exercises

### Exercise 1: Transversality forbids a photon mass

Assume the QED two-point effective action contains a quadratic term

$$
\Gamma^{(2)}[A]
=\frac12\int\frac{d^4q}{(2\pi)^4}
A_\mu(-q)\Pi^{\mu\nu}(q)A_\nu(q).
$$

Show that gauge invariance under $A_\mu(q)\to A_\mu(q)+iq_\mu\alpha(q)$ implies $q_\mu\Pi^{\mu\nu}(q)=0$. Explain why a term $m_\gamma^2\eta^{\mu\nu}$ is forbidden.

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta\Gamma^{(2)}
=\int\frac{d^4q}{(2\pi)^4}
(iq_\mu\alpha(-q))\Pi^{\mu\nu}(q)A_\nu(q),
$$

up to relabeling of momenta and using symmetry of the quadratic kernel. For this to vanish for arbitrary $\alpha$ and $A_\nu$, we need

$$
q_\mu\Pi^{\mu\nu}(q)=0.
$$

A mass term contributes

$$
\Pi^{\mu\nu}_{\mathrm{mass}}=m_\gamma^2\eta^{\mu\nu},
$$

so

$$
q_\mu\Pi^{\mu\nu}_{\mathrm{mass}}=m_\gamma^2q^\nu,
$$

which is not zero unless $m_\gamma^2=0$. Therefore gauge invariance forbids a photon mass term.

</details>

### Exercise 2: Gauge invariance of the plaquette trace

Let a lattice link variable transform as

$$
U_\mu(n)\to \Omega(n)U_\mu(n)\Omega(n+\hat\mu)^{-1}.
$$

Show that the plaquette product

$$
U_{\mu\nu}(n)
=U_\mu(n)U_\nu(n+\hat\mu)
U_\mu(n+\hat\nu)^{-1}U_\nu(n)^{-1}
$$

transforms by conjugation at $n$. Conclude that $\operatorname{tr}U_{\mu\nu}(n)$ is gauge invariant.

<details><summary><strong>Solution</strong></summary>

Under a gauge transformation each link gets an $\Omega$ at its initial site and an $\Omega^{-1}$ at its final site. In the plaquette product, all transformations at intermediate sites cancel pairwise. The result is

$$
U_{\mu\nu}(n)\to
\Omega(n)U_{\mu\nu}(n)\Omega(n)^{-1}.
$$

Taking the trace gives

$$
\operatorname{tr}\bigl(\Omega(n)U_{\mu\nu}(n)\Omega(n)^{-1}\bigr)
=\operatorname{tr}U_{\mu\nu}(n),
$$

by cyclicity of the trace. Therefore the plaquette trace is exactly gauge invariant at nonzero lattice spacing.

</details>

### Exercise 3: Why a shift of loop momentum can fail with a cutoff

Let

$$
I_\Lambda(q)=\int_{|\ell|<\Lambda}d^4\ell\,f(\ell+q).
$$

Why is $I_\Lambda(q)$ not generally equal to $I_\Lambda(0)$ after the change of variables $k=\ell+q$?

<details><summary><strong>Solution</strong></summary>

With $k=\ell+q$, the domain changes:

$$
|\ell|<\Lambda
\quad\Longrightarrow\quad
|k-q|<\Lambda.
$$

Therefore

$$
I_\Lambda(q)=\int_{|k-q|<\Lambda}d^4k\,f(k),
$$

not

$$
\int_{|k|<\Lambda}d^4k\,f(k).
$$

The two domains differ by a thin shell near the cutoff boundary. In convergent integrals the difference may vanish as $\Lambda\to\infty$, but in divergent integrals it can leave finite or divergent surface terms. Ward identities often assume that such shifts produce no boundary contribution, so a naive hard cutoff can spoil them.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on QED renormalization, Ward identities, and regularization.
- Mark Srednicki, *Quantum Field Theory*, especially the chapters on beta functions in QED, nonabelian gauge theory, and background field gauge.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters on nonabelian gauge theories and renormalization of gauge theories.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on regularization, QED renormalization, Yang–Mills theory, and the background field method.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the treatment of renormalization with symmetries and gauge theories.
- Kenneth G. Wilson, lattice gauge theory and Wilsonian RG papers, for the nonperturbative gauge-invariant cutoff viewpoint.
- L. D. Faddeev and V. N. Popov, original work on gauge fixing and ghosts.
- A. A. Slavnov and J. C. Taylor, original work on nonabelian gauge-theory identities.

## Version history

- 2026-06-18: First polished draft. Added the regulator taxonomy, BRST-restoration logic, anomaly caveat, lattice gauge regularization discussion, and the gauge-invariant regularization map.
