---
title: "Cutoff Regularization"
description: "A practical guide to regulating ultraviolet loop integrals with hard or smooth momentum cutoffs, extracting divergent terms, and interpreting cutoff dependence before renormalization."
sidebar:
  label: "Cutoff Regularization"
  order: 3
level: Graduate
status: "Polished draft"
source: "Coleman 2019, chs. 15–16 and 25; Srednicki 2007, §§14–20 and 27; Schwartz 2014, chs. 15 and 21; Zee 2010, chs. III.1–III.3; Zinn-Justin 2021, chs. 8–9"
topics:
  - cutoff regularization
  - ultraviolet divergences
  - momentum cutoff
  - counterterms
  - naturalness
canonicalTopics:
  - cutoff-regularization
  - hard-momentum-cutoff
  - smooth-cutoff
  - ultraviolet-regulator
  - cutoff-dependence
researchStatus:
  established:
    - "Momentum cutoffs are standard ultraviolet regulators that make short-distance sensitivity explicit and are especially useful for power counting, Wilsonian intuition, and naturalness estimates."
  active:
    - "In gauge theories, chiral theories, real-time calculations, and precision computations, cutoff regulators must be chosen carefully or replaced by symmetry-preserving schemes such as dimensional regularization, lattice regularization, Pauli–Villars variants, or gauge-invariant higher-derivative methods."
---

## Summary

A **cutoff regulator** makes a loop integral finite by suppressing momenta above a large scale $\Lambda$. In Euclidean momentum space, the simplest version replaces

$$
\int\frac{d^4k_E}{(2\pi)^4}
\qquad\text{by}\qquad
\int_{|k_E|<\Lambda}\frac{d^4k_E}{(2\pi)^4}.
$$

The cutoff is not a new physical prediction by itself. It is a temporary device that exposes how a calculation depends on short-distance modes. A typical divergent integral becomes

$$
\int_{|k_E|<\Lambda}\frac{d^4k_E}{(2\pi)^4}\frac{1}{k_E^2+m^2}
=
\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\ln\!\left(1+\frac{\Lambda^2}{m^2}\right)
\right].
$$

For large $\Lambda$,

$$
\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\ln\frac{\Lambda^2}{m^2}+O(\Lambda^{-2})
\right]
$$

shows both quadratic and logarithmic cutoff dependence. In a renormalized calculation, local counterterms absorb the cutoff-dependent local pieces, and physical predictions are expressed in terms of measured parameters.

Cutoffs are conceptually transparent, but they are blunt instruments. A hard momentum cutoff can obscure Lorentz invariance, gauge invariance, and momentum-routing invariance if used carelessly. That is why cutoff regularization is excellent for learning and Wilsonian reasoning, while dimensional regularization is often the default for precision perturbative calculations.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Cutoff regularization flow from Lorentzian loop integral to Euclidean cutoff, divergent local pieces, counterterms, and finite physical predictions](/figures/perturbative-qft/cutoff-regularization-flow.svg)

<figcaption>

Cutoff regularization is a workflow, not just the symbol $\Lambda$. One first defines a finite regulated integral, then isolates the large-$\Lambda$ behavior, absorbs local cutoff dependence into counterterms, and finally expresses predictions in terms of renormalized parameters. The danger is that a naive hard cutoff may interfere with symmetries or momentum shifts before the renormalized answer is assembled.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Superficial Degree of Divergence](/perturbative-qft/loop-expansion-regularization/superficial-degree-of-divergence/), and [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/). For the Euclidean continuation used below, review [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/).

## Core idea

A cutoff implements the sentence “do not trust the theory at arbitrarily short distances.” In momentum space, short distance means large momentum. Cutting off momenta above $\Lambda$ says: compute only with modes that the effective description is meant to describe.

There are two closely related uses.

| Use | Meaning |
|---|---|
| Regulator | A temporary device used to make divergent loop integrals finite before renormalization. |
| Physical cutoff | A real scale where new degrees of freedom, new dynamics, or a more microscopic description replaces the low-energy theory. |

The algebra can look identical in the two uses, but the interpretation is different. If $\Lambda$ is merely a regulator, physical predictions should not depend on it after counterterms and renormalization conditions are included. If $\Lambda$ is a physical threshold, the remaining low-energy sensitivity to $\Lambda$ is information about matching to the theory above that threshold.

The practical slogan is

$$
\text{a cutoff exposes short-distance sensitivity; counterterms decide how it is parameterized.}
$$

## Setup and conventions

We use qft.org mostly-minus Lorentzian conventions, but the explicit cutoff integrals on this page are Euclidean. A scalar propagator loop integral of the form

$$
\int\frac{d^4\ell}{(2\pi)^4}\frac{i}{\ell^2-m^2+i\epsilon}
$$

Wick rotates to

$$
\int\frac{d^4\ell_E}{(2\pi)^4}\frac{1}{\ell_E^2+m^2},
$$

when no singularity crosses the contour. A hard Euclidean cutoff then means

$$
\int_k^{\Lambda} f(k)
\equiv
\int_{|k|<\Lambda}\frac{d^d k}{(2\pi)^d}f(k),
$$

where $k$ is Euclidean and $d$ is usually $4$ on this page. The angular volume of the unit sphere in $d$ Euclidean dimensions is

$$
\Omega_{d-1}=\frac{2\pi^{d/2}}{\Gamma(d/2)}.
$$

For $d=4$,

$$
\Omega_3=2\pi^2,
\qquad
\int_{|k|<\Lambda}d^4k\,f(k^2)
=2\pi^2\int_0^\Lambda dk\,k^3 f(k^2).
$$

The cutoff formulas below are regulator formulas. They do not by themselves define a renormalization scheme until one also states which counterterms are used and which renormalization conditions fix their finite parts.

## Hard momentum cutoff

The sharpest cutoff is the hard ball

$$
|k_E|<\Lambda.
$$

It is easy to visualize and easy to compute with in rotationally invariant Euclidean scalar integrals. For example,

$$
I_1^\Lambda(m^2)
\equiv
\int_{|k|<\Lambda}\frac{d^4k}{(2\pi)^4}\frac{1}{k^2+m^2}.
$$

Using four-dimensional spherical coordinates,

$$
I_1^\Lambda(m^2)
=
\frac{2\pi^2}{(2\pi)^4}
\int_0^\Lambda dk\,\frac{k^3}{k^2+m^2}
=
\frac{1}{8\pi^2}
\int_0^\Lambda dk\,\frac{k^3}{k^2+m^2}.
$$

Write

$$
\frac{k^3}{k^2+m^2}=k-\frac{m^2k}{k^2+m^2}.
$$

Then

$$
I_1^\Lambda(m^2)
=
\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\ln\!\left(1+\frac{\Lambda^2}{m^2}\right)
\right].
$$

The large-cutoff expansion is

$$
I_1^\Lambda(m^2)
=
\frac{\Lambda^2}{16\pi^2}
-
\frac{m^2}{16\pi^2}\ln\frac{\Lambda^2}{m^2}
+O(\Lambda^{-2}).
$$

This integral is the basic scalar tadpole. In $\lambda\phi^4$ theory, the one-loop two-point 1PI tadpole is proportional to $\lambda I_1^\Lambda/2$, up to the sign convention used for the self-energy. The important structural point is independent of that sign: the divergent part is local and has the same form as a mass counterterm.

## The cutoff bubble integral

The next elementary integral is

$$
I_2^\Lambda(m^2)
\equiv
\int_{|k|<\Lambda}\frac{d^4k}{(2\pi)^4}\frac{1}{(k^2+m^2)^2}.
$$

A direct radial calculation gives

$$
I_2^\Lambda(m^2)
=
\frac{1}{8\pi^2}
\int_0^\Lambda dk\,\frac{k^3}{(k^2+m^2)^2}.
$$

With $u=k^2$, this becomes

$$
I_2^\Lambda(m^2)
=
\frac{1}{16\pi^2}
\int_0^{\Lambda^2}du\,\frac{u}{(u+m^2)^2}.
$$

Since

$$
\frac{u}{(u+m^2)^2}
=
\frac{1}{u+m^2}-\frac{m^2}{(u+m^2)^2},
$$

we get

$$
I_2^\Lambda(m^2)
=
\frac{1}{16\pi^2}
\left[
\ln\!\left(1+\frac{\Lambda^2}{m^2}\right)
-
\frac{\Lambda^2}{\Lambda^2+m^2}
\right].
$$

At large $\Lambda$,

$$
I_2^\Lambda(m^2)
=
\frac{1}{16\pi^2}
\left[
\ln\frac{\Lambda^2}{m^2}-1+O(\Lambda^{-2})
\right].
$$

This is the prototype logarithmically divergent integral. It appears after Feynman parameterization in one-loop two-propagator diagrams and after differentiating the tadpole integral:

$$
I_2^\Lambda(m^2)=-\frac{\partial I_1^\Lambda(m^2)}{\partial m^2}.
$$

That derivative check is one of the fastest ways to catch a missing sign or factor of two.

## Smooth cutoffs

A hard cutoff abruptly changes the integration domain. A smooth cutoff instead inserts a damping function,

$$
\int\frac{d^d k}{(2\pi)^d}f(k)
\quad\longrightarrow\quad
\int\frac{d^d k}{(2\pi)^d}R\!\left(\frac{k^2}{\Lambda^2}\right)f(k),
$$

where

$$
R(0)=1,
\qquad
R(x)\to0\quad(x\to\infty).
$$

Examples include

$$
R(x)=e^{-x},
\qquad
R(x)=\frac{1}{(1+x)^N},
\qquad
R(x)=\theta(1-x).
$$

The last example is the hard cutoff. Smooth cutoffs are often better for Wilsonian calculations because they make shell integration and differentiating with respect to $\Lambda$ cleaner. They also avoid sharp boundary artifacts. However, unless carefully designed, a smooth momentum cutoff can still break gauge invariance or other symmetries.

The universal lesson is not the exact shape of $R$. Different cutoff functions change finite scheme-dependent constants and power-divergent coefficients, but they agree on the local structures allowed by symmetry and on physical predictions after matching and renormalization.

## What cutoff dependence means

A large-$\Lambda$ expansion separates a regulated loop integral into pieces with different interpretations.

For the tadpole integral,

$$
I_1^\Lambda(m^2)
=
\frac{\Lambda^2}{16\pi^2}
-
\frac{m^2}{16\pi^2}\ln\frac{\Lambda^2}{m^2}
+\text{finite or suppressed terms}.
$$

The $\Lambda^2$ term has mass dimension two and is local. In a scalar two-point function, it has the form of a mass correction. The $m^2\ln\Lambda^2$ term is also local in the external fields and contributes to mass renormalization. In diagrams with external momentum, terms polynomial in external momentum correspond to local operators such as

$$
\phi^2,
\qquad
\partial_\mu\phi\partial^\mu\phi,
\qquad
\phi^4,
\qquad
\phi^6,
\qquad
\ldots
$$

The nonlocal finite parts, such as threshold logarithms and branch cuts in external momenta, cannot be removed by local counterterms. Those are physical analytic structures of amplitudes.

:::note[Locality is the reason counterterms work]
Ultraviolet divergences come from loop momenta much larger than external momenta and masses. Expanding in small external quantities gives polynomials, hence local operators in position space. This is the deep reason local counterterms can absorb UV divergences.
:::

## Cutoff regularization and counterterms

Consider a bare Lagrangian written schematically as

$$
\mathcal L_B
=
\frac12 Z_\phi\partial_\mu\phi\partial^\mu\phi
-
\frac12 Z_m m^2\phi^2
-
\frac{Z_\lambda\lambda}{4!}\phi^4.
$$

Equivalently, split it into a renormalized part plus counterterms:

$$
\mathcal L_B=\mathcal L_R+\mathcal L_{\rm ct},
$$

with

$$
\mathcal L_{\rm ct}
=
\frac12\delta Z\,\partial_\mu\phi\partial^\mu\phi
-
\frac12\delta m^2\phi^2
-
\frac{\delta\lambda}{4!}\phi^4+\cdots.
$$

The counterterms depend on $\Lambda$ and on the chosen renormalization conditions. For example, a two-point renormalization condition may demand that the pole of the renormalized propagator occurs at the measured mass. Then $\delta m^2$ is chosen to cancel the cutoff-dependent shift in the pole location.

The important conceptual separation is

$$
\text{bare parameters depend on the regulator; measured predictions do not.}
$$

This statement is not magic. It is achieved order by order by including every local counterterm allowed by the symmetries and by fixing a finite number of renormalized parameters in a renormalizable theory, or an organized tower of parameters in an effective field theory.

## Momentum routing and symmetry issues

A hard cutoff restricts the integration domain. Therefore a shift of loop momentum can change the domain:

$$
\int_{|k|<\Lambda} d^d k\,f(k+a)
\neq
\int_{|k|<\Lambda} d^d k\,f(k)
$$

for finite $\Lambda$. For convergent integrals this difference vanishes as $\Lambda\to\infty$. For divergent integrals it can leave surface terms. This is why momentum routing in cutoff-regulated loop diagrams requires care.

The same issue appears in tensor integrals. With a rotationally invariant Euclidean cutoff one may use

$$
\int_{|k|<\Lambda}d^d k\,k_\mu k_\nu F(k^2)
=
\frac{\delta_{\mu\nu}}{d}
\int_{|k|<\Lambda}d^d k\,k^2F(k^2),
$$

but only because the regulator preserves Euclidean rotations. A regulator that preserves one symmetry may break another. In gauge theories, naive cutoff manipulations can violate Ward or Slavnov–Taylor identities unless the regulator and counterterms are chosen with the symmetry in mind.

This does not mean cutoffs are wrong. It means they are physical enough to expose the UV scale, but not automatically elegant enough to preserve every formal identity.

## Cutoffs versus dimensional regularization

Cutoff regularization and dimensional regularization are different regulators, not different physics.

| Feature | Cutoff regularization | Dimensional regularization |
|---|---|---|
| UV scale | explicit $\Lambda$ | pole at $\epsilon=0$ and scale $\mu$ |
| Power divergences | visible, such as $\Lambda^2$ | absent for scaleless integrals in minimal subtraction |
| Symmetry handling | can break Lorentz or gauge symmetry if naive | usually preserves Lorentz and gauge symmetry, with chiral subtleties |
| Wilsonian intuition | very transparent | less direct |
| Precision loop algebra | often clunky | very efficient |

A logarithmic divergence often appears in cutoff language as

$$
\ln\frac{\Lambda^2}{m^2},
$$

and in dimensional regularization as

$$
\frac{1}{\epsilon}-\ln\frac{m^2}{\mu^2}
$$

up to scheme-dependent constants. Both encode the same need to define a renormalized parameter and its scale dependence.

Power divergences are more subtle. Their presence in cutoff regularization is important for Wilsonian naturalness estimates. Their absence from minimal-subtraction dimensional regularization does not mean that heavy thresholds cannot affect scalar masses. It means that this particular subtraction scheme does not display power sensitivity as an explicit divergent integral.

## Common pitfalls

**Treating the cutoff as an observable.** If $\Lambda$ is a regulator, predictions should not depend on it after renormalization. If $\Lambda$ is a physical threshold, the low-energy theory must be matched to whatever lives above it.

**Using a hard cutoff in Minkowski space casually.** The condition $|\ell|<\Lambda$ is not Lorentz invariant in Lorentzian signature. The usual elementary cutoff formulas are Euclidean formulas after a Wick rotation.

**Shifting divergent integrals without checking the regulator.** A hard cutoff changes the integration domain, so shifts of loop momentum can leave surface terms. Momentum-routing invariance is automatic only for regulators that preserve it, or after a consistent renormalized calculation.

**Assuming power divergences are scheme-independent numbers.** The coefficient of a power divergence depends strongly on the regulator. The need for local counterterms and the sensitivity to heavy thresholds are physical statements; the exact coefficient of a regulator artifact is not.

**Breaking gauge symmetry by accident.** A naive momentum cutoff may violate Ward identities. Gauge theories require symmetry-preserving regulators or counterterm prescriptions that restore the identities.

## Relations to other pages

- [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/) explains why loop integrals appear and how loop number is counted.
- [Superficial Degree of Divergence](/perturbative-qft/loop-expansion-regularization/superficial-degree-of-divergence/) predicts which cutoff powers can appear before cancellations are used.
- [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/) explains how local counterterms enter diagrammatic perturbation theory.
- [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) gives the symmetry-friendly analytic continuation regulator that is most common in modern loop calculations.
- [Conventions and Notation](/perturbative-qft/conventions/) fixes the scattering and loop-measure conventions used here.

## Research status

Cutoff regularization is textbook-standard. Its role as a regulator, its relation to local counterterms, and its Wilsonian interpretation are settled parts of QFT.

The subtleties are practical and conceptual rather than unresolved. Different cutoff implementations preserve different symmetries, and a careless cutoff can produce intermediate expressions that violate identities restored only after counterterms or a better regulator are used. In modern research, cutoffs remain central in Wilsonian RG, lattice field theory, effective field theory, naturalness arguments, and numerical methods, while dimensional regularization dominates many analytic perturbative calculations.

## Exercises

### Exercise 1: Evaluate the cutoff tadpole

Derive

$$
I_1^\Lambda(m^2)
=
\int_{|k|<\Lambda}\frac{d^4k}{(2\pi)^4}\frac{1}{k^2+m^2}
=
\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\ln\!\left(1+\frac{\Lambda^2}{m^2}\right)
\right].
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\int_{|k|<\Lambda}d^4k\,f(k^2)
=2\pi^2\int_0^\Lambda dk\,k^3 f(k^2).
$$

Then

$$
I_1^\Lambda
=
\frac{1}{8\pi^2}\int_0^\Lambda dk\,\frac{k^3}{k^2+m^2}.
$$

Rewrite

$$
\frac{k^3}{k^2+m^2}=k-\frac{m^2k}{k^2+m^2}.
$$

Therefore

$$
I_1^\Lambda
=
\frac{1}{8\pi^2}
\left[
\frac{\Lambda^2}{2}
-
\frac{m^2}{2}\ln(k^2+m^2)\bigg|_0^\Lambda
\right],
$$

which gives

$$
I_1^\Lambda
=
\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\ln\frac{\Lambda^2+m^2}{m^2}
\right].
$$

</details>

### Exercise 2: Derivative check for the bubble integral

Show that

$$
I_2^\Lambda(m^2)
=
-\frac{\partial I_1^\Lambda(m^2)}{\partial m^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

At the integrand level,

$$
-\frac{\partial}{\partial m^2}\frac{1}{k^2+m^2}
=
\frac{1}{(k^2+m^2)^2}.
$$

The cutoff domain does not depend on $m^2$, so the derivative passes through the integral:

$$
-\frac{\partial I_1^\Lambda}{\partial m^2}
=
\int_{|k|<\Lambda}\frac{d^4k}{(2\pi)^4}\frac{1}{(k^2+m^2)^2}
=
I_2^\Lambda.
$$

Differentiating the closed form of $I_1^\Lambda$ gives

$$
I_2^\Lambda
=
\frac{1}{16\pi^2}
\left[
\ln\!\left(1+\frac{\Lambda^2}{m^2}\right)
-\frac{\Lambda^2}{\Lambda^2+m^2}
\right].
$$

</details>

### Exercise 3: Identify local counterterms

In four-dimensional $\lambda\phi^4$ theory, the one-loop tadpole contribution to the two-point function is proportional to $\lambda I_1^\Lambda(m^2)$. Which counterterm can absorb its divergent part?

<details>
<summary><strong>Solution</strong></summary>

The divergent part of $I_1^\Lambda$ is independent of external momentum:

$$
I_1^\Lambda(m^2)
=
\frac{\Lambda^2}{16\pi^2}
-
\frac{m^2}{16\pi^2}\ln\frac{\Lambda^2}{m^2}
+\cdots.
$$

Since it is momentum-independent, it has the same two-point structure as a mass term. It is absorbed by a local counterterm

$$
-\frac12\delta m^2\phi^2,
$$

with $\delta m^2$ chosen according to the chosen renormalization condition. A momentum-dependent divergence proportional to $p^2$ would instead require a wavefunction counterterm proportional to $\partial_\mu\phi\partial^\mu\phi$.

</details>

### Exercise 4: Large-cutoff expansion of the bubble

Expand

$$
I_2^\Lambda(m^2)
=
\frac{1}{16\pi^2}
\left[
\ln\!\left(1+\frac{\Lambda^2}{m^2}\right)
-
\frac{\Lambda^2}{\Lambda^2+m^2}
\right]
$$

for $\Lambda\gg m$.

<details>
<summary><strong>Solution</strong></summary>

For $\Lambda\gg m$,

$$
\ln\!\left(1+\frac{\Lambda^2}{m^2}\right)
=
\ln\frac{\Lambda^2}{m^2}+O(\Lambda^{-2}),
$$

and

$$
\frac{\Lambda^2}{\Lambda^2+m^2}=1+O(\Lambda^{-2}).
$$

Therefore

$$
I_2^\Lambda(m^2)
=
\frac{1}{16\pi^2}
\left[
\ln\frac{\Lambda^2}{m^2}-1+O(\Lambda^{-2})
\right].
$$

The divergence is logarithmic.

</details>

### Exercise 5: Why shifts are dangerous

Explain why the equality

$$
\int_{|k|<\Lambda}d^d k\,f(k+a)
=
\int_{|k|<\Lambda}d^d k\,f(k)
$$

is not automatic for a hard cutoff.

<details>
<summary><strong>Solution</strong></summary>

Changing variables $q=k+a$ changes the integration domain:

$$
|k|<\Lambda
\qquad\longrightarrow\qquad
|q-a|<\Lambda.
$$

That shifted ball is not the same as $|q|<\Lambda$. For convergent integrals, the boundary difference vanishes as $\Lambda\to\infty$. For divergent integrals, the difference can leave a finite or divergent surface term. Therefore momentum shifts in hard-cutoff-regulated divergent integrals require care.

</details>

## References

### Standard first pass

- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 15–16 and 25, for counterterm logic, regularization, and the conceptual role of infinities.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 15 and 21, for cutoff examples, regulator dependence, and renormalizability.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. III.1–III.3, for the physical meaning of cutting off short-distance ignorance and introducing counterterms.

### Deeper references

- Mark Srednicki, *Quantum Field Theory*, §§14–20 and 27, for scalar loop corrections, all-orders perturbation theory, and comparison of renormalization schemes.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 12, for the structural role of power counting and renormalization.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 8–9, for cutoff regularization, ultraviolet divergences, effective QFT, and renormalization.

## Version history

- **2026-06-12:** Initial polished draft for the Perturbative QFT and Scattering volume.
