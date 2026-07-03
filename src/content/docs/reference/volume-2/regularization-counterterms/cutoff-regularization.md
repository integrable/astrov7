---
title: "Cutoff Regularization"
description: "How hard cutoffs make ultraviolet sensitivity explicit, why cutoff-dependent terms are local, and how counterterms absorb them."
sidebar:
  label: "Cutoff Regularization"
  order: 1
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Coleman, renormalization lectures; Srednicki §§14–20 and §§27–29; Schwartz chs. 15, 18–23; Weinberg Vol. I ch. 12; Zinn-Justin, renormalization chapters; Burgess 2020 chs. 2–3."
topics:
  - cutoff regularization
  - ultraviolet divergences
  - counterterms
  - locality
  - Wilsonian cutoff
canonicalTopics:
  - cutoff-regularization
  - ultraviolet-cutoff
  - counterterm
  - locality-of-divergences
  - wilsonian-cutoff
researchStatus:
  established:
    - "Cutoff regularization is a standard way to expose ultraviolet sensitivity; locality and symmetry determine which cutoff-dependent terms can affect low-energy physics."
  active:
    - "Cutoff implementations remain subtle in gauge theories, chiral fermion theories, lattice constructions, exact RG schemes, and nonperturbative continuum limits."
---

## Summary

A **cutoff regulator** makes a quantum field theory well defined by removing, suppressing, or discretizing modes above a short-distance scale. In momentum-space examples this often means replacing a divergent loop integral by

$$
\int \frac{d^d k_E}{(2\pi)^d}
\quad\longrightarrow\quad
\int_{|k_E|<\Lambda}\frac{d^d k_E}{(2\pi)^d},
$$

where $k_E$ is Euclidean momentum and $\Lambda$ is a large momentum scale.

Cutoffs are conceptually valuable because they show what the theory is sensitive to. Power divergences appear as powers of $\Lambda$. Logarithmic divergences appear as logarithms such as $\log(\Lambda^2/m^2)$. The central lesson is not that these symbols are physical infinities. The central lesson is this:

$$
\text{large loop momentum produces local dependence on external fields and momenta.}
$$

That local dependence is precisely what counterterms absorb.

A cutoff may be used in two different ways. It can be a **temporary regulator** that is removed after renormalization, or it can be a **Wilsonian cutoff** that defines an effective action with only modes below $\Lambda$ kept explicitly. The formulas can look similar, but the interpretation is different. A temporary cutoff is scaffolding. A Wilsonian cutoff is part of the scale-dependent description.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Two regulator languages for the same ultraviolet-sensitive local data: a hard cutoff produces powers and logarithms of Lambda, dimensional regularization produces epsilon poles and logarithms of mu, and both feed local counterterms and renormalized parameters](/figures/renormalization-rg-eft/regulator-languages-local-terms.svg)

<figcaption>

Cutoff regularization and dimensional regularization are different languages for exposing ultraviolet-sensitive local data. A hard cutoff displays powers and logarithms of $\Lambda$; dimensional regularization displays poles in $\epsilon$ and logarithms of $\mu$. The regulator-dependent local pieces are absorbed into counterterms or Wilson coefficients, while properly defined observables are regulator independent.

</figcaption>
</figure>

:::note[What a cutoff teaches]
A cutoff is not merely a brute-force way to stop an integral from diverging. It is a microscope dial. By watching how the answer depends on $\Lambda$, one learns which local terms the low-energy description cannot predict without input.
:::

## Prerequisites

You should know the volume [Conventions and Notation](/renormalization-rg-eft/conventions/) and the chapter overview [Regularization and Counterterms](/renormalization-rg-eft/regularization-counterterms/). The most important conceptual prerequisites are [Loops and Locality](/renormalization-rg-eft/why-renormalization/loops-and-locality/), [Divergences as Local Operators](/renormalization-rg-eft/why-renormalization/divergences-as-local-operators/), and [Regulator Dependence](/renormalization-rg-eft/why-renormalization/regulator-dependence/).

This page uses Euclidean loop integrals after Wick rotation. The underlying Lorentzian convention remains mostly-minus, with scalar propagator $i/(p^2-m^2+i\epsilon)$. The Euclidean formulas are used because a spherical cutoff $|k_E|<\Lambda$ is simple and unambiguous.

## Core idea

Loop integrals sum over virtual momenta not fixed by external kinematics. A typical one-loop integral has the schematic form

$$
I(p,m)=\int\frac{d^d k}{(2\pi)^d}F(k,p,m),
$$

where $p$ denotes external momenta and $m$ denotes masses. The ultraviolet question is what happens when $|k|\gg |p|,m$.

A cutoff replaces the question by a finite one:

$$
I_\Lambda(p,m)=\int_{|k_E|<\Lambda}\frac{d^d k_E}{(2\pi)^d}F_E(k_E,p_E,m).
$$

For finite $\Lambda$, this is an ordinary number or function. The dependence on $\Lambda$ has two roles:

1. It diagnoses which local structures are sensitive to short-distance physics.
2. It tells us which counterterms or Wilson coefficients must be specified.

The large-$\Lambda$ expansion usually separates into two qualitatively different pieces:

$$
I_\Lambda(p,m)
=\text{local terms depending on }\Lambda
+\text{finite nonlocal terms}
+O(1/\Lambda).
$$

The local terms are polynomials in external momenta and masses, possibly multiplied by powers or logarithms of $\Lambda$. They are the terms that counterterms can absorb. The nonlocal terms contain physical long-distance information such as thresholds, branch cuts, and logarithms of ratios of physical scales.

## Setup and conventions

We write Euclidean loop integrals as

$$
\int_k^\Lambda f(k)
\equiv
\int_{|k|<\Lambda}\frac{d^4 k}{(2\pi)^4}f(k),
$$

unless another dimension is stated. The $O(4)$-invariant volume element is

$$
\int_{|k|<\Lambda}d^4k\,f(k^2)
=2\pi^2\int_0^\Lambda dk\,k^3 f(k^2).
$$

Therefore

$$
\int_k^\Lambda f(k^2)
=\frac{1}{8\pi^2}\int_0^\Lambda dk\,k^3 f(k^2).
$$

This spherical Euclidean cutoff is useful pedagogically. It preserves Euclidean rotations but should not be confused with the only possible cutoff. Other common choices include smooth cutoff functions,

$$
\int\frac{d^4k}{(2\pi)^4}f(k)
\quad\longrightarrow\quad
\int\frac{d^4k}{(2\pi)^4}R(k^2/\Lambda^2)f(k),
$$

with $R(x)\to 1$ for $x\ll1$ and $R(x)\to0$ for $x\gg1$, lattice regulators with spacing $a$, and Pauli–Villars regulators using heavy auxiliary fields.

Different cutoffs differ in the detailed coefficients of local terms. They must agree on physical observables after renormalization, provided the regulator respects the needed symmetries or the required symmetry-restoring counterterms are included.

## The basic tadpole integral

The simplest cutoff integral in four Euclidean dimensions is

$$
I_1^\Lambda(m^2)
\equiv
\int_k^\Lambda\frac{1}{k^2+m^2}.
$$

Using the radial measure,

$$
I_1^\Lambda(m^2)
=\frac{1}{8\pi^2}\int_0^\Lambda dk\,\frac{k^3}{k^2+m^2}.
$$

Since

$$
\frac{k^3}{k^2+m^2}=k-\frac{m^2 k}{k^2+m^2},
$$

the integral is elementary:

$$
I_1^\Lambda(m^2)
=\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\log\left(1+\frac{\Lambda^2}{m^2}\right)
\right].
$$

For $\Lambda\gg m$,

$$
I_1^\Lambda(m^2)
=\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\log\frac{\Lambda^2}{m^2}
+O(m^4/\Lambda^2)
\right].
$$

This expression displays two common kinds of cutoff sensitivity:

$$
\Lambda^2
\qquad\text{and}\qquad
m^2\log\Lambda^2.
$$

In $\phi^4$ theory, this integral appears in the one-loop correction to the scalar two-point function. With interaction convention

$$
\mathcal L_{\text{int}}=-\frac{\lambda}{4!}\phi^4,
$$

the one-loop mass correction is schematically

$$
\delta m^2_{\text{loop}}\sim \frac{\lambda}{2}I_1^\Lambda(m^2),
$$

up to the precise sign convention used for self-energies. The important point is structural: the divergence multiplies the local operator $\phi^2$. It is absorbed by a mass counterterm.

## The basic logarithmic integral

The next integral is

$$
I_2^\Lambda(m^2)
\equiv
\int_k^\Lambda\frac{1}{(k^2+m^2)^2}.
$$

Again using the radial measure,

$$
I_2^\Lambda(m^2)
=\frac{1}{8\pi^2}\int_0^\Lambda dk\,\frac{k^3}{(k^2+m^2)^2}.
$$

The result is

$$
I_2^\Lambda(m^2)
=\frac{1}{16\pi^2}
\left[
\log\left(1+\frac{\Lambda^2}{m^2}\right)
-\frac{\Lambda^2}{\Lambda^2+m^2}
\right].
$$

For $\Lambda\gg m$,

$$
I_2^\Lambda(m^2)
=\frac{1}{16\pi^2}
\left[
\log\frac{\Lambda^2}{m^2}-1+O(m^2/\Lambda^2)
\right].
$$

This logarithm is the cutoff-language precursor of the $1/\epsilon$ pole in dimensional regularization. In four-dimensional $\phi^4$ theory, logarithmically divergent four-point diagrams require a local $\phi^4$ counterterm. The finite remainder depends on the subtraction convention, and this scheme dependence becomes the running of the renormalized coupling.

## Large-momentum expansion and locality

The reason cutoff divergences are local is visible before evaluating the integral. Consider a loop denominator with external momentum $p$:

$$
\frac{1}{(k+p)^2+m^2}.
$$

For $|k|\gg |p|,m$, expand:

$$
\frac{1}{(k+p)^2+m^2}
=\frac{1}{k^2+m^2}
\left[
1-\frac{2k\cdot p+p^2}{k^2+m^2}
+\frac{(2k\cdot p+p^2)^2}{(k^2+m^2)^2}
-\cdots
\right].
$$

After angular integration, odd powers of $k\cdot p$ vanish for a rotationally invariant cutoff. The remaining divergent terms are polynomials in $p^2$ and $m^2$:

$$
A(\Lambda)+B(\Lambda)m^2+C(\Lambda)p^2+\cdots.
$$

In position space, polynomials in momentum correspond to local operators:

$$
1\leftrightarrow \phi^2,
\qquad
p^2\leftrightarrow \partial_\mu\phi\partial^\mu\phi,
\qquad
m^2\leftrightarrow m^2\phi^2.
$$

This is the practical version of a central theorem-like lesson:

$$
\text{UV divergences in local QFT are canceled by local counterterms.}
$$

The nonlocal parts of amplitudes do not come from arbitrarily large momentum alone. They know about physical scales, thresholds, massless propagation, and branch cuts. A local counterterm cannot remove a physical branch cut, and it should not try.

## Power divergences, logarithms, and dimensions

Cutoff power counting begins with the large-$k$ behavior of the integrand. In $d$ Euclidean dimensions,

$$
\int^{\Lambda} d^d k\,k^r
\sim
\Lambda^{d+r}
\qquad(d+r\ne0),
$$

while

$$
\int^{\Lambda}\frac{dk}{k}\sim \log\Lambda.
$$

Thus a loop integral has:

| Large-momentum behavior | Cutoff dependence | Meaning |
|---|---|---|
| $d^d k/k^2$ in four dimensions | $\Lambda^2$ | quadratic sensitivity to a local mass-like operator |
| $d^d k/k^4$ in four dimensions | $\log\Lambda$ | logarithmic sensitivity to a marginal local operator |
| $d^d k/k^6$ in four dimensions | finite as $\Lambda\to\infty$ | UV-convergent contribution |

Power divergences are scheme-dependent as numerical objects. A smooth cutoff, a sharp cutoff, and a lattice regulator can assign different coefficients to $\Lambda^2$. But the need for a symmetry-allowed relevant operator is physical in the Wilsonian sense. If no symmetry forbids $\phi^2$, then short-distance physics can affect its coefficient strongly.

Logarithmic divergences are special because they produce scale dependence that survives as running couplings. This is why beta functions are often extracted most cleanly from logarithmic divergences or $1/\epsilon$ poles.

## A scalar example: which counterterms are suggested?

Consider four-dimensional scalar theory

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4.
$$

The local operators with dimension at most four and $\phi\to-\phi$ symmetry are

$$
1,
\qquad
\phi^2,
\qquad
\partial_\mu\phi\partial^\mu\phi,
\qquad
\phi^4.
$$

Therefore the counterterm Lagrangian has the form

$$
\mathcal L_{\text{ct}}
=-\delta\rho
+\frac12\delta Z\,\partial_\mu\phi\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\delta\lambda}{4!}\phi^4.
$$

The one-loop tadpole suggests $\delta m^2$. The one-loop four-point diagrams suggest $\delta\lambda$. At higher loop order, momentum-dependent two-point divergences require $\delta Z$. Vacuum bubbles require the vacuum-energy counterterm $\delta\rho$.

The cutoff is doing a diagnostic job. It tells us what local information the low-energy Lagrangian must contain. Once all allowed counterterms are included and fixed by conditions, physical predictions do not depend on the arbitrary details of the cutoff.

## Temporary cutoff versus Wilsonian cutoff

The same symbol $\Lambda$ is used in two related but distinct ways.

A **temporary cutoff** is a regulator introduced to make intermediate expressions finite. The workflow is:

$$
\text{regulate with }\Lambda
\quad\longrightarrow\quad
\text{add counterterms}
\quad\longrightarrow\quad
\text{fix renormalized parameters}
\quad\longrightarrow\quad
\Lambda\to\infty\text{ if possible}.
$$

Here $\Lambda$ is not a physical maximum energy. It should disappear from final observables.

A **Wilsonian cutoff** labels an effective action in which modes above $\Lambda$ have been integrated out or not included explicitly:

$$
e^{iS_\Lambda[\phi_<]}
=\int \mathcal D\phi_>\,e^{iS[\phi_<+\phi_>]}.
$$

Here $S_\Lambda$ changes when $\Lambda$ changes. The point is not to take $\Lambda\to\infty$ immediately. The point is to choose a scale appropriate to the physics and use the effective action at that scale.

The conceptual difference is sharp:

| Use of $\Lambda$ | What changes when $\Lambda$ changes? | Desired final dependence on $\Lambda$ |
|---|---|---|
| temporary regulator | intermediate expressions and counterterms | cancels from observables |
| Wilsonian cutoff | the effective action and explicit degrees of freedom | physical predictions remain invariant after couplings flow |

Many confusions come from mixing these two languages in one sentence.

## Cutoffs and symmetries

A regulator is not innocent if it violates a symmetry that the theory is supposed to have. A sharp Euclidean momentum cutoff preserves translations and rotations in Euclidean momentum space, but it can obscure Lorentzian covariance and can violate gauge invariance in naive gauge-theory calculations.

The issue is especially visible in momentum routing. With an unrestricted integral, shifting the loop variable is harmless:

$$
\int d^4k\,f(k)=\int d^4k\,f(k+p).
$$

With a sharp cutoff, the integration domain changes under $k\to k+p$:

$$
|k|<\Lambda
\quad\not\Longleftrightarrow\quad
|k+p|<\Lambda.
$$

The difference comes from the boundary of the cutoff region. It is local in external momenta, but in gauge theories such local terms can violate Ward identities unless treated carefully. The cure is not to ignore the problem. The cure is to use a symmetry-preserving regulator when possible, or to include all symmetry-restoring local counterterms allowed by the true quantum symmetries.

Dimensional regularization is popular partly because it preserves momentum-shift invariance and is highly compatible with gauge symmetry. Lattice gauge theory preserves gauge invariance nonperturbatively by putting group variables on links. Pauli–Villars can preserve some symmetries but must be designed with care.

## What cutoff dependence means in EFT

In an EFT with breakdown scale $M$, a finite cutoff can be physically reasonable. The EFT Lagrangian has the form

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\le d}
+\sum_i\frac{C_i}{M^{\Delta_i-d}}\mathcal O_i.
$$

If calculations are regulated at a cutoff $\Lambda\lesssim M$, the coefficients $C_i$ absorb dependence on physics above the EFT resolution. Predictions are organized in powers of $Q/M$ or $Q/\Lambda$, depending on the setup.

The EFT logic is:

$$
\text{include every local operator allowed by symmetries, then truncate by power counting.}
$$

A cutoff makes this logic visible. Integrating out short-distance modes generates local operators whether or not they were present in a bare-looking starting Lagrangian. Excluding them without a symmetry reason is not a simplification; it is an unstable assumption.

## Common pitfalls

**Treating $\Lambda$ as automatically physical.** A cutoff can be physical, Wilsonian, or temporary. State which one you mean.

**Believing the coefficient of $\Lambda^2$ is universal.** The precise coefficient of a power divergence depends on the cutoff scheme. The existence of sensitivity to a relevant operator is meaningful; the raw coefficient is not by itself an observable.

**Ignoring symmetry violation by the regulator.** If the regulator breaks a symmetry, intermediate expressions may violate the corresponding identities. The final renormalized theory must restore the desired symmetry if that symmetry is genuine and non-anomalous.

**Thinking a cutoff makes counterterms unnecessary.** A finite cutoff makes integrals finite, but predictions still depend on local short-distance parameters. Counterterms or Wilson coefficients are how that dependence is organized.

**Expanding outside the regime of validity.** The large-$k$ expansion explains UV-local terms. It does not reproduce threshold cuts or long-distance nonanalyticities.

**Confusing Wilsonian flow with renormalized running.** Wilsonian couplings change because degrees of freedom are integrated out. Renormalized couplings change because the subtraction scale changes at fixed bare data. The two are related but not identical statements.

## Relations to other pages

This page is the first regulator page in the Regularization and Counterterms chapter. It should be read before [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/) because dimensional regularization is much easier to interpret once cutoff power counting and local UV sensitivity are visible.

The next pages compare cutoff regularization with Pauli–Villars, lattice regularization, and dimensional regularization. The [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/) page then explains how the local terms found here enter the Lagrangian and Feynman rules. [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/) turns the large-momentum estimates into a systematic classification.

Later, [Wilsonian Renormalization](/renormalization-rg-eft/wilsonian-renormalization/) treats $\Lambda$ as a sliding scale defining an effective action. [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/) uses finite-cutoff intuition to explain why higher-dimension operators are predictive rather than embarrassing.

## Research status

The basic use of cutoff regularization in perturbative QFT is standard. The structural facts on this page — UV-locality, counterterms, power counting, and scheme dependence — are established graduate-level material.

The subtle parts are not historical dust. Cutoff regulators remain central in lattice field theory, Wilsonian exact RG, functional RG, Hamiltonian truncation, tensor-network approaches, and EFTs with finite breakdown scales. In chiral gauge theories, gauge theories with anomalies, gravity, and theories with fermion-doubling constraints, choosing a cutoff that preserves the right structures can be a deep part of the problem.

## Exercises

### Exercise 1: The four-dimensional tadpole

Derive

$$
\int_{|k|<\Lambda}\frac{d^4k}{(2\pi)^4}\frac{1}{k^2+m^2}
=\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\log\left(1+\frac{\Lambda^2}{m^2}\right)
\right].
$$

<details><summary><strong>Solution</strong></summary>

Use the four-dimensional spherical measure $d^4k=2\pi^2 k^3dk$:

$$
I=\frac{2\pi^2}{(2\pi)^4}\int_0^\Lambda dk\,\frac{k^3}{k^2+m^2}
=\frac{1}{8\pi^2}\int_0^\Lambda dk\,\frac{k^3}{k^2+m^2}.
$$

Rewrite

$$
\frac{k^3}{k^2+m^2}=k-\frac{m^2k}{k^2+m^2}.
$$

Then

$$
I=\frac{1}{8\pi^2}
\left[
\frac{\Lambda^2}{2}
-\frac{m^2}{2}\log\frac{\Lambda^2+m^2}{m^2}
\right],
$$

which gives the stated result.

</details>

### Exercise 2: The logarithmic integral by differentiation

Use the identity

$$
\frac{\partial}{\partial m^2}\frac{1}{k^2+m^2}
=-\frac{1}{(k^2+m^2)^2}
$$

to derive $I_2^\Lambda(m^2)$ from $I_1^\Lambda(m^2)$.

<details><summary><strong>Solution</strong></summary>

Since

$$
I_2^\Lambda(m^2)=-\frac{\partial I_1^\Lambda(m^2)}{\partial m^2},
$$

and

$$
I_1^\Lambda(m^2)=\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\log\left(1+\frac{\Lambda^2}{m^2}\right)
\right],
$$

we differentiate the second term:

$$
\frac{\partial}{\partial m^2}
\left[m^2\log\left(1+\frac{\Lambda^2}{m^2}\right)\right]
=
\log\left(1+\frac{\Lambda^2}{m^2}\right)
-\frac{\Lambda^2}{\Lambda^2+m^2}.
$$

Therefore

$$
I_2^\Lambda(m^2)=\frac{1}{16\pi^2}
\left[
\log\left(1+\frac{\Lambda^2}{m^2}\right)
-\frac{\Lambda^2}{\Lambda^2+m^2}
\right].
$$

</details>

### Exercise 3: Locality from expansion

For $|k|\gg |p|,m$, expand

$$
\frac{1}{(k^2+m^2)((k+p)^2+m^2)}
$$

through terms quadratic in $p$. Explain why the divergent terms after angular integration are polynomial in $p$.

<details><summary><strong>Solution</strong></summary>

Write

$$
\frac{1}{(k+p)^2+m^2}
=\frac{1}{k^2+m^2}
\left[
1-\frac{2k\cdot p+p^2}{k^2+m^2}
+\frac{(2k\cdot p+p^2)^2}{(k^2+m^2)^2}
+O(p^3)
\right].
$$

Multiplying by the first propagator gives

$$
\frac{1}{(k^2+m^2)^2}
-\frac{2k\cdot p+p^2}{(k^2+m^2)^3}
+\frac{(2k\cdot p)^2}{(k^2+m^2)^4}
+O(p^3).
$$

For a rotationally invariant cutoff, angular integration kills the term linear in $k\cdot p$ and replaces

$$
(k\cdot p)^2\longrightarrow \frac{k^2p^2}{4}
$$

in four Euclidean dimensions. The divergent part is therefore a sum of terms proportional to $1$, $p^2$, $m^2$, and higher polynomials. Polynomials in external momenta are local terms in position space.

</details>

### Exercise 4: Temporary or Wilsonian?

A calculation uses $\Lambda$ and then sends $\Lambda\to\infty$ after adding counterterms. Another calculation lowers $\Lambda$ from $10\,\mathrm{TeV}$ to $1\,\mathrm{GeV}$ and changes the action accordingly. Which use is temporary cutoff regularization, and which is Wilsonian?

<details><summary><strong>Solution</strong></summary>

The first is temporary cutoff regularization. The cutoff is scaffolding: it makes intermediate expressions finite and is removed from final observables after counterterms and renormalization conditions are included.

The second is Wilsonian. The cutoff labels which degrees of freedom remain explicit, and the action changes as modes are integrated out between $10\,\mathrm{TeV}$ and $1\,\mathrm{GeV}$.

</details>

## References

- K. G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on divergences, counterterms, and renormalization.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on loop corrections, renormalizability, other renormalization schemes, the RG, and EFT.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 15 and 18–23.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on regularization, renormalization, and critical behavior.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially chapters 2–3.

## Version history

- 2026-06-17: First polished draft. Introduced hard Euclidean cutoffs, basic cutoff integrals, locality of divergent terms, symmetry caveats, and the distinction between temporary and Wilsonian cutoffs.
