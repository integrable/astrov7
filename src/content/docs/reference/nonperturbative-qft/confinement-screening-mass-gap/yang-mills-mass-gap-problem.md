---
title: "Yang–Mills Mass Gap Problem"
description: "States the Yang–Mills existence and mass gap problem, explains what a proof must construct, and separates physics evidence from mathematical theorem."
sidebar:
  label: "Yang–Mills Mass Gap Problem"
  order: 14
level: Research
status: "Polished draft"
source: "Jaffe–Witten; Clay Mathematics Institute; Osterwalder–Schrader; Srednicki ch. 82; Shifman ch. 9."
topics:
  - Yang–Mills theory
  - mass gap
  - Millennium problem
  - constructive QFT
  - confinement
  - glueballs
  - reflection positivity
  - lattice gauge theory
canonicalTopics:
  - nonperturbative-qft
  - yang-mills-theory
  - mass-gap
  - constructive-qft
  - confinement
researchStatus:
  established:
    - "The problem asks for a rigorous construction of four-dimensional quantum Yang–Mills theory for compact simple gauge group and a proof of a positive mass gap."
  active:
    - "The problem remains unsolved; experiment and computer simulations strongly support a gap, but no proof of the mass-gap property is known."
---

## Summary

The **Yang–Mills mass gap problem** asks for much more than a good argument that glueballs are massive. In its standard Millennium-problem form, it asks one to construct four-dimensional quantum Yang–Mills theory for every compact simple gauge group $G$ and prove that the resulting theory has a positive mass gap.

The spectral part of the statement is

$$
\Delta
=\inf\bigl(\operatorname{spec}H\setminus\{0\}\bigr)>0,
$$

where $H$ is the Hamiltonian acting on the physical Hilbert space and the vacuum energy has been normalized to zero. Equivalently, gauge-invariant connected Euclidean correlators should have exponential long-distance decay controlled by a nonzero lowest physical mass.

<figure class="doc-figure" style="--figure-width: 60rem;">

![A flowchart showing that the Yang–Mills mass gap problem requires a regulated theory, a continuum limit, axioms or reconstruction, a physical Hilbert space, and a positive spectral gap.](/figures/nonperturbative-qft/yang-mills-mass-gap-problem-map.svg)

<figcaption>

The Yang–Mills problem has two inseparable parts: construct the continuum quantum field theory and prove a positive gap in its physical spectrum. Lattice simulations, large-$N$ arguments, strong-coupling expansions, lower-dimensional models, and phenomenology are crucial evidence, but they do not replace the construction plus theorem.

</figcaption>
</figure>

The physics expectation is very strong. Pure four-dimensional Yang–Mills theory is asymptotically free, generates a scale by dimensional transmutation, has a lattice-regulated nonperturbative definition at finite cutoff, and numerically exhibits a glueball spectrum with a nonzero lowest mass. The open problem is to turn this physics into a mathematically complete continuum construction and proof.

## Prerequisites

Read [Mass Gap in Gauge Theory](/nonperturbative-qft/confinement-screening-mass-gap/mass-gap/) before this page. You should also know [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/), [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/), [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/), [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/), and [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/).

This page is a frontier/open-problem page. It assumes more mathematical maturity than the diagnostic pages earlier in the chapter.

## Core idea

There are two tasks, and both are hard.

The **existence** task is to define the continuum quantum theory with enough mathematical control that its correlation functions, Hilbert space, locality, positivity, and symmetries are not merely formal. A lattice regulator is a natural starting point, but the problem is not solved at finite lattice spacing. One must control the continuum limit.

The **mass-gap** task is to prove that the constructed theory has no arbitrarily low-energy physical excitations above the vacuum. In Euclidean language, the connected correlation functions of gauge-invariant operators must decay exponentially at large separation.

The two tasks cannot be cleanly separated. A mass gap must be a theorem about the actual continuum theory, not about a regulator, a truncation, a toy model, or a formal perturbative expansion.

## Setup and conventions

The classical Euclidean Yang–Mills action is

$$
S_E[A]
=\frac{1}{2g_0^2}\int_{\mathbb R^4}d^4x\,
\operatorname{tr}F_{\mu\nu}F_{\mu\nu},
$$

with

$$
F=dA+A\wedge A
$$

in differential-form language, or

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu+[A_\mu,A_\nu]
$$

in components. The gauge group $G$ is compact and simple.

A typical regulated approach introduces a lattice spacing $a$ and link variables

$$
U_\ell\in G.
$$

At finite volume and nonzero lattice spacing, the lattice theory is a well-defined finite-dimensional integral. The hard question is whether one can take

$$
a\to0,
\qquad
L\to\infty,
$$

with the bare coupling tuned appropriately, so that gauge-invariant correlation functions converge to those of a nontrivial continuum QFT on $\mathbb R^4$.

The expected continuum scale is generated by dimensional transmutation:

$$
\Lambda_{\mathrm{YM}}
=\mu\exp\left[-\int^{g(\mu)}\frac{dg}{\beta(g)}\right].
$$

The mass gap, if present, should be of order

$$
\Delta\sim c\,\Lambda_{\mathrm{YM}},
$$

with a dimensionless constant $c$ depending on the gauge group and normalization scheme for $\Lambda_{\mathrm{YM}}$.

## Problem statement

A clean physics version is:

> Construct pure quantum Yang–Mills theory on four-dimensional spacetime for compact simple gauge group $G$, and prove that the physical spectrum above the vacuum has a positive lower bound.

A Euclidean constructive version asks for gauge-invariant Schwinger functions satisfying conditions strong enough to reconstruct a Lorentzian QFT. These include Euclidean invariance, reflection positivity, locality or an appropriate field/operator structure, clustering, and regularity conditions. The exact formal framework can vary, but it must be strong enough to define a genuine quantum field theory, not only a collection of formal integrals.

The gap condition can be expressed spectrally as

$$
\operatorname{spec}H\cap(0,\Delta)=\varnothing
$$

for some $\Delta>0$. In Euclidean correlator language, if $O$ is a gauge-invariant operator with its vacuum expectation value subtracted, one expects

$$
\langle O(x)O(0)\rangle_c
\sim e^{-m_O|x|}
$$

in massive channels, with the lightest such mass bounded below by $\Delta$.

## What existence means

Existence is not the statement that physicists can write the formal integral

$$
Z=\int \mathcal D A\,e^{-S_E[A]}.
$$

Nor is it the statement that perturbation theory is renormalizable. Perturbative renormalizability says that short-distance divergences can be absorbed order by order in a small-coupling expansion. The Yang–Mills existence problem asks for the nonperturbative continuum object.

A lattice construction suggests the right shape of the problem. At finite lattice spacing and finite volume,

$$
Z_{a,L}
=\int \prod_\ell dU_\ell\,e^{-S_{\mathrm{lat}}[U]}
$$

is a well-defined integral over compact group variables. The continuum theory would arise from a limit of gauge-invariant correlators as $a\to0$ and $L\to\infty$.

To prove existence, one must show that this limiting object is nontrivial and satisfies the needed axioms. In particular, one must control ultraviolet singularities, infinite-volume limits, gauge invariance, positivity, and the reconstruction of a physical Hilbert space.

This is where asymptotic freedom helps and hurts. It helps because the bare coupling goes to zero at short distances, suggesting ultraviolet control. It hurts because the infrared theory is strongly coupled, and the mass gap is precisely an infrared phenomenon.

## What the mass gap means

The mass gap is a statement about the **physical** Hilbert space. Gauge-fixed gluons, ghosts, and gauge potentials are not by themselves physical particles. The relevant excitations are created by gauge-invariant operators: glueball operators, extended operators, and their multiparticle states.

A typical scalar glueball interpolating operator is

$$
O_S(x)=\operatorname{tr}F_{\mu\nu}F_{\mu\nu}(x).
$$

If the theory has a scalar glueball of mass $m_{0^{++}}$, then a zero-momentum Euclidean correlator behaves at large Euclidean time as

$$
C_S(\tau)
=\int d^3\mathbf x\,
\langle O_S(\tau,\mathbf x)O_S(0,\mathbf0)\rangle_c
\sim A e^{-m_{0^{++}}\tau}.
$$

The gap $\Delta$ is the smallest positive mass or threshold energy over all physical non-vacuum channels. In pure Yang–Mills theory the expected lightest states are glueballs, but the theorem should not depend on guessing a particular interpolating operator.

## Why perturbation theory cannot solve it

Perturbation theory around $A_\mu=0$ describes massless gauge bosons at every finite order. The mass gap is expected to scale like

$$
\Delta\sim \Lambda_{\mathrm{YM}}
\sim \mu\,e^{-\mathrm{const}/g^2(\mu)}
$$

at weak coupling. This behavior is invisible to any Taylor series in $g^2$ around $g=0$.

This is one of the most basic lessons of nonperturbative QFT: the mass gap is not a high-loop correction to a gluon propagator. It is a reorganization of the physical spectrum.

Perturbation theory remains essential for asymptotic freedom and ultraviolet control. It cannot, by itself, produce the theorem.

## Evidence versus proof

The evidence for a mass gap in pure four-dimensional Yang–Mills theory is substantial.

| Evidence | What it supports | Why it is not the full proof |
|---|---|---|
| Lattice simulations | Nonzero glueball masses and string tension after continuum extrapolation. | Numerical evidence is not a constructive proof of existence and gap. |
| Strong-coupling expansion | Wilson-loop area law at finite lattice spacing in a controlled regime. | The strong-coupling regime is not automatically connected to the continuum limit. |
| Asymptotic freedom | Ultraviolet control and dimensional transmutation. | It does not alone control the strongly coupled infrared. |
| Large-$N$ expansion | Narrow glueballs, string-like flux tubes, and factorization if confinement holds. | It organizes a confining theory but does not prove confinement. |
| Compact QED in three dimensions | A controlled monopole mechanism for mass gap and confinement. | It is a different lower-dimensional abelian theory. |
| Supersymmetric gauge theory | Exact results and mass gaps in special protected settings. | Adding supersymmetry changes the theory. |

A good proof may use insights from any of these sources. But it must eventually establish a theorem about the target four-dimensional pure Yang–Mills theory.

## Relation to confinement

The mass-gap problem and the confinement problem are close relatives, not identical twins.

A mass gap says there are no arbitrarily light physical excitations. Confinement concerns the fate of gauge charges, line operators, flux tubes, and the absence of colored asymptotic states. A gapped scalar theory has a mass gap but no confinement. Conversely, a theory might have subtle confinement-like behavior in some sectors without making the mass-gap theorem easy.

For pure Yang–Mills theory, the expected physics includes both:

$$
\text{mass gap}
\quad\text{and}\quad
\text{confinement of nonzero center charge}.
$$

The Wilson-loop area law would be a strong confinement diagnostic, while exponential decay of local gauge-invariant correlators is the direct mass-gap diagnostic. A complete nonperturbative understanding of pure Yang–Mills should explain both, but the official Millennium problem is usually framed as existence plus mass gap.

## What a proof would have to control

A convincing proof must control several layers at once.

**Continuum limit.** Starting from a regulator, one must show that a nontrivial continuum limit exists. The limit should be independent of regulator details in the appropriate universality sense.

**Gauge invariance and physical observables.** The construction must identify gauge-invariant observables or an equivalent physical algebra. Gauge fixing cannot introduce unphysical states into the final Hilbert space.

**Positivity and reconstruction.** Euclidean correlation functions must satisfy positivity conditions strong enough to reconstruct a Hilbert space with a positive Hamiltonian.

**Locality and symmetry.** The theory must have the expected Euclidean or Poincaré invariance, locality, and gauge-invariant operator structure.

**Infrared decay.** The connected gauge-invariant correlators must decay exponentially, or equivalently the Hamiltonian spectrum must have a positive gap above the vacuum.

**Nontriviality.** The limit must not collapse to a trivial theory. Pure Yang–Mills should retain nonzero physical scales and nontrivial correlation functions.

This list is why the problem is not merely “show the lightest glueball has mass.” The glueball statement only makes sense after the continuum theory and its physical Hilbert space exist.

## Common pitfalls

**Confusing finite-volume gaps with a mass gap.** Any finite box has discrete levels. The Yang–Mills problem asks for a positive gap after the infinite-volume continuum theory has been constructed.

**Calling lattice evidence a proof.** Lattice gauge theory is the best nonperturbative regulator and a powerful numerical laboratory. The Millennium problem asks for a rigorous continuum theorem.

**Proving a property of a toy model and declaring victory.** Compact QED in three dimensions, two-dimensional QCD, sigma models, and supersymmetric theories are invaluable guides. They are not the four-dimensional pure Yang–Mills theory of the problem.

**Using gauge-fixed propagators as physical spectra.** A scale in a gauge-fixed gluon propagator is not automatically a physical particle mass. The gap belongs to the gauge-invariant Hilbert space.

**Treating confinement and mass gap as synonyms.** They are related in pure Yang–Mills, but they are logically distinct. The theorem must state precisely which property is being proved.

## Relations to other pages

- [Mass Gap in Gauge Theory](/nonperturbative-qft/confinement-screening-mass-gap/mass-gap/) gives the physical and spectral definition used here.
- [What Is Confinement?](/nonperturbative-qft/confinement-screening-mass-gap/what-is-confinement/) separates confinement, screening, and mass gap before the rigorous problem is stated.
- [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/) explains the standard confinement diagnostic that is closely related to, but not identical with, the mass-gap theorem.
- [Strong-Coupling Expansion](/nonperturbative-qft/confinement-screening-mass-gap/strong-coupling-expansion/) gives a controlled finite-cutoff area-law calculation and explains why it is not automatically a continuum proof.
- [Compact QED in Three Dimensions](/nonperturbative-qft/confinement-screening-mass-gap/compact-qed-three-dimensions/) gives a lower-dimensional model where a mass gap and confinement mechanism are analytically controlled.
- [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) explains a major organizing limit that sharpens the expected glueball and string picture.

## Research status

The problem remains open. Experiment and computer simulations strongly support a mass gap in quantum Yang–Mills theory, and the Clay Mathematics Institute lists the problem as unsolved with no proof of the mass-gap property known. The official problem description by Jaffe and Witten also emphasizes that QCD’s successful strong-interaction physics requires a mass gap, quark confinement, and chiral symmetry breaking, while a complete theoretical derivation in QCD is not known.

The strongest current evidence comes from lattice gauge theory, asymptotic freedom, continuum extrapolation of glueball spectra, the success of QCD, strong-coupling and semiclassical mechanisms in related models, and large-$N$ consistency. The missing ingredient is a rigorous continuum construction with a proof of spectral positivity and a positive gap.

## Exercises

### Exercise 1: Why finite volume is not enough

A theory in a finite box of side length $L$ has a lowest nonzero momentum $2\pi/L$. Explain why a nonzero finite-volume energy spacing does not prove an infinite-volume mass gap.

<details>
<summary><strong>Solution</strong></summary>

The mass gap is an infinite-volume property. Even a free massless particle in a finite box has a lowest nonzero momentum

$$
|\mathbf p|=\frac{2\pi}{L},
$$

so the finite-volume energy spacing is nonzero. But as $L\to\infty$,

$$
\frac{2\pi}{L}\to0.
$$

Therefore finite-volume discreteness is not a mass gap. One must control the infinite-volume limit.

</details>

### Exercise 2: Correlator decay and the gap

Assume a zero-momentum connected Euclidean correlator has spectral representation

$$
C(\tau)=\sum_{n\ne0}a_n e^{-E_n\tau},
\qquad a_n\ge0.
$$

If $E_n\ge\Delta>0$ for all $n\ne0$, show that $C(\tau)$ is bounded by an exponentially decaying function when $\sum a_n$ is finite.

<details>
<summary><strong>Solution</strong></summary>

Since $E_n\ge\Delta$,

$$
e^{-E_n\tau}\le e^{-\Delta\tau}.
$$

Therefore

$$
C(\tau)
=\sum_{n\ne0}a_n e^{-E_n\tau}
\le e^{-\Delta\tau}\sum_{n\ne0}a_n.
$$

If $\sum a_n$ is finite, then

$$
C(\tau)\le C(0)e^{-\Delta\tau}.
$$

This is the basic spectral reason why a gap implies exponential Euclidean decay.

</details>

### Exercise 3: Why perturbation theory misses the scale

Suppose a physical mass scale behaves at weak coupling as

$$
M(g)=\mu e^{-A/g^2}
$$

with $A>0$. Show that all derivatives of $M(g)$ at $g=0^+$ vanish formally, so no ordinary Taylor series in $g$ can see this scale.

<details>
<summary><strong>Solution</strong></summary>

The function $e^{-A/g^2}$ goes to zero faster than any power of $g$ as $g\to0^+$. For every integer $k$,

$$
\lim_{g\to0^+}g^{-k}e^{-A/g^2}=0.
$$

Derivatives of $e^{-A/g^2}$ produce powers of $1/g$ multiplying the same exponential, but the exponential still wins. Thus all Taylor coefficients at $g=0$ vanish. A nonzero scale of this form is nonperturbative in $g^2$.

</details>

## References

### Standard first pass

- A. Jaffe and E. Witten, “Quantum Yang–Mills Theory,” for the official problem description and the physics–mathematics framing.
- Clay Mathematics Institute, “Yang–Mills and Mass Gap,” for the official Millennium-problem status.
- M. Srednicki, *Quantum Field Theory*, especially chapter 82, for Wilson loops, lattice theory, and confinement diagnostics.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapters 1 and 9, for phases of gauge theories, confinement, and mass-gap context.

### Deeper references

- M. R. Douglas, “Report on the Status of the Yang–Mills Millennium Prize Problem,” for a concise mathematical-physics status overview.
- K. Wilson and J. Kogut, and the lattice gauge theory literature, for the regulator and continuum-limit perspective.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, and constructive-QFT literature for the rigorous Euclidean-measure viewpoint.
- J. Greensite, *An Introduction to the Confinement Problem*, for the physics evidence and confinement diagnostics surrounding the mass-gap question.

## Version history

- **2026-06-27:** Initial polished page. Added problem statement, existence versus mass-gap distinction, Euclidean and Hamiltonian formulations, evidence-versus-proof table, confinement relation, proof requirements, status language, and exercises.
