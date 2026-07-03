---
title: "Landau Poles"
description: "Explains finite-scale blowups of running couplings, their one-loop origin, their relation to triviality and EFT cutoffs, and what they do and do not prove."
sidebar:
  label: "Landau Poles"
  order: 9
level: Graduate
status: "Polished draft"
source: "Landau, Abrikosov, and Khalatnikov; Coleman, Dilatations and Asymptotic Freedom; Srednicki §§27–29; Schwartz chs. 21–23; Weinberg Vol. II ch. 18; Zinn-Justin 2021."
topics:
  - Landau poles
  - running couplings
  - triviality
  - ultraviolet completion
  - effective field theory
  - perturbative breakdown
canonicalTopics:
  - landau-pole
  - triviality
  - running-coupling-singularity
  - uv-completion
researchStatus:
  established:
    - "A Landau pole is the finite-RG-time divergence of a running coupling within a chosen beta-function description; in perturbation theory it signals loss of validity before or at the pole."
  active:
    - "The nonperturbative interpretation of apparent Landau poles, triviality bounds, and possible ultraviolet completions is theory dependent and remains important in scalar theories, Abelian gauge theories, Higgs-sector EFTs, and beyond-Standard-Model model building."
---

## Summary

A **Landau pole** is a finite-scale singularity in the solution of an RG equation. In its simplest one-coupling form,

$$
\frac{dg}{d\log\mu}=b g^3,
\qquad b>0,
$$

the solution is

$$
g^2(\mu)=
\frac{g^2(\mu_0)}{1-2b g^2(\mu_0)\log(\mu/\mu_0)}.
$$

It diverges at

$$
\mu_L
=
\mu_0\exp\left[\frac{1}{2b g^2(\mu_0)}\right].
$$

This scale is the **Landau pole** of the one-loop running coupling. It means that the running-coupling description cannot be continued past $\mu_L$ within that approximation.

A Landau pole is not automatically a directly observable explosion. It may be far above the regime where the EFT is meant to apply. It may be removed by new degrees of freedom, a UV fixed point, compositeness, quantum gravity, or another ultraviolet completion. It may also indicate that no interacting continuum limit exists in the assumed class of theories. The right interpretation depends on the theory and on the question being asked.

The practical lesson is:

$$
\text{a Landau pole is a warning about extrapolating an RG description beyond its domain.}
$$

## Prerequisites

You should know [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/), and [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/).

It is also useful to know the distinction between [Physical Parameters](/renormalization-rg-eft/why-renormalization/physical-parameters/) and scheme-defined running parameters, and the EFT viewpoint from [Nonrenormalizable Does Not Mean Useless](/renormalization-rg-eft/effective-field-theory/nonrenormalizable-does-not-mean-useless/) when that page is available.

## Core idea

An RG equation is a differential equation on coupling space. A coupling may reach infinity at finite RG time, just as a solution of an ordinary differential equation may blow up at finite time. The variable

$$
t=\log\mu
$$

is the usual RG time in renormalized perturbation theory. A Landau pole occurs when the solution cannot be continued to arbitrarily large or small $t$ because a coupling diverges.

The simplest case is a positive cubic beta function:

$$
\beta(g)=b g^3+O(g^5),
\qquad b>0.
$$

Then weak coupling in the infrared grows toward the ultraviolet. If nothing changes, perturbation theory predicts a divergence at a finite UV scale.

That phrase contains two traps. First, “if nothing changes” is doing real work. New physics can enter before the pole. Second, “perturbation theory predicts” means the calculation has usually stopped being trustworthy before the formal divergence. A one-loop expression that says $g\to\infty$ cannot also be used as a reliable calculation at $g\to\infty$.

:::note[The pole is a feature of the running coordinate]
A Landau pole is a singularity of a running coupling in a chosen description. It is not, by itself, a proof that an observable diverges. To make a physical claim, one must say which observable is being computed and whether the theory is being treated as a cutoff EFT or as a proposed continuum QFT.
:::

## Setup and conventions

This volume defines

$$
\beta_g(g)=\left.\mu\frac{dg}{d\mu}\right|_{\text{bare parameters fixed}}
=\frac{dg}{d\log\mu}.
$$

Let $t=\log\mu$. Near weak coupling, suppose

$$
\beta_g=b g^3+O(g^5),
\qquad b>0.
$$

Keeping only the leading term,

$$
\frac{dg}{dt}=b g^3.
$$

Equivalently,

$$
\frac{d}{dt}\left(\frac{1}{g^2}\right)
=-2b.
$$

Integrating between $\mu_0$ and $\mu$ gives

$$
\frac{1}{g^2(\mu)}
=
\frac{1}{g^2(\mu_0)}-2b\log\frac{\mu}{\mu_0}.
$$

When the denominator reaches zero, the one-loop solution has a pole:

$$
\log\frac{\mu_L}{\mu_0}
=
\frac{1}{2b g^2(\mu_0)}.
$$

The exponential dependence is important. A small coupling at one scale can push the formal Landau pole astronomically far away.

## A one-loop ultraviolet Landau pole

The one-loop solution can be written as

$$
g^2(\mu)=
\frac{g_0^2}{1-2b g_0^2\log(\mu/\mu_0)},
\qquad g_0\equiv g(\mu_0).
$$

For $\mu>\mu_0$, the denominator decreases. If $b>0$, the coupling grows as the renormalization scale is raised. The pole occurs at finite $\mu_L$.

The same formula shows why the pole is invisible in ordinary low-energy perturbation theory when $g_0$ is small. Expanding the denominator gives

$$
g^2(\mu)
=
g_0^2\left[1+2b g_0^2\log\frac{\mu}{\mu_0}+O(g_0^4\log^2(\mu/\mu_0))\right].
$$

For moderate logarithms the correction is small. The Landau pole appears only after the logarithm becomes order $1/g_0^2$. That is exactly the regime where ordinary fixed-order perturbation theory has failed and RG improvement was needed in the first place.

## QED as the classic example

For QED with one Dirac fermion, this volume uses

$$
\beta_e=\frac{e^3}{12\pi^2}+O(e^5).
$$

In terms of

$$
\alpha=\frac{e^2}{4\pi},
$$

this gives

$$
\frac{d\alpha}{d\log\mu}
=
\frac{2}{3\pi}\alpha^2+O(\alpha^3).
$$

The one-loop solution is

$$
\alpha(\mu)=
\frac{\alpha(\mu_0)}{1-\frac{2\alpha(\mu_0)}{3\pi}\log(\mu/\mu_0)}.
$$

The corresponding Landau scale is

$$
\mu_L
=
\mu_0\exp\left[\frac{3\pi}{2\alpha(\mu_0)}\right].
$$

Using the low-energy value $\alpha\simeq 1/137$ makes this scale fantastically large compared with ordinary particle-physics scales. Long before treating that pole literally, one encounters electroweak unification, charged-particle thresholds, possible new physics, gravity, and the limitations of extrapolating QED by itself.

So the QED Landau pole is not a practical prediction that a laboratory will see a divergence. It is a conceptual statement: pure continuum QED, taken as a standalone theory to arbitrarily high energies with fixed nonzero low-energy charge, does not look UV complete in perturbation theory.

## Scalar φ⁴ theory and triviality

In four-dimensional scalar $\phi^4$ theory with

$$
\mathcal L\supset -\frac{\lambda}{4!}\phi^4,
$$

the one-loop beta function is

$$
\beta_\lambda=\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

For positive $\lambda$, the solution is

$$
\lambda(\mu)
=
\frac{\lambda(\mu_0)}{1-\frac{3\lambda(\mu_0)}{16\pi^2}\log(\mu/\mu_0)}.
$$

Again there is a UV Landau pole in the one-loop running coupling.

The related continuum-limit issue is called **triviality**. Suppose a theory is defined with cutoff $\Lambda_{\text{cut}}$ and one insists on sending $\Lambda_{\text{cut}}\to\infty$ while keeping the low-energy coupling finite and positive. If the Landau-pole behavior persists nonperturbatively, the only way to avoid a pole below the cutoff is to let the low-energy renormalized coupling go to zero. The interacting theory then becomes free in the continuum limit.

This is why the statement “four-dimensional $\phi^4$ theory is trivial” is not merely the statement that a one-loop beta function is positive. It is a statement about the possible continuum limit. Perturbation theory motivates it; nonperturbative arguments and lattice evidence determine how seriously to take it in a given setting.

## Landau pole versus strong-coupling scale

Asymptotically free theories also produce a formal one-loop divergence, but it occurs in the opposite direction. If

$$
\beta(g)=-b_0g^3,
\qquad b_0>0,
$$

then

$$
g^2(\mu)=\frac{1}{2b_0\log(\mu/\Lambda)}.
$$

This expression diverges as $\mu\to\Lambda^+$. It is sometimes loosely called an infrared Landau pole, but this language is dangerous. In QCD-like theories, the divergence of the perturbative coupling near $\Lambda$ is not a UV inconsistency. It is a sign that weak-coupling perturbation theory has reached the edge of its domain and that infrared physics is nonperturbative.

The contrast is worth keeping sharp:

| Case | One-loop sign | Direction of formal pole | Usual interpretation |
|---|---:|---|---|
| QED-like screening | $\beta(g)>0$ | ultraviolet | possible obstruction to a standalone continuum UV completion |
| $\phi^4_4$ with $\lambda>0$ | $\beta_\lambda>0$ | ultraviolet | triviality or need for a cutoff/UV completion |
| asymptotically free gauge theory | $\beta(g)<0$ | infrared | perturbative breakdown and dimensional transmutation |

A finite-scale pole is therefore not a complete diagnosis. One must ask: which direction is the pole in, and what is the theory claiming to describe?

## What a Landau pole does and does not prove

A Landau pole **does** show that a running-coupling description cannot be extrapolated indefinitely within its current beta-function approximation.

It **does** often imply that an EFT has an upper limit of validity unless new physics enters first.

It **does** motivate triviality questions for theories whose renormalized coupling grows toward the ultraviolet.

It **does not** prove that a low-energy EFT is bad. EFTs are not required to survive to infinite energy.

It **does not** automatically prove that all physical observables diverge at the pole.

It **does not** rule out a UV completion. A new fixed point, new fields, compositeness, dual variables, or another short-distance description may take over.

It **does not** prove that a perturbative truncation is reliable near the pole. In fact, the opposite is usually true.

:::tip[Use Landau poles as domain markers]
The safest practical use of a Landau pole is as a domain marker. If an EFT predicts a pole at $\mu_L$, then calculations near or above $\mu_L$ cannot be trusted without additional information. Calculations far below $\mu_L$ may be perfectly useful.
:::

## Scheme dependence and invariant content

The exact location of a Landau pole in a truncated perturbative beta function is scheme dependent. A finite coupling redefinition changes the coordinate $g$ and therefore changes the detailed higher-order beta function.

However, the existence of a problem can be robust when the following statements hold together:

- the weak-coupling beta function has a positive leading coefficient;
- no UV fixed point appears before strong coupling;
- attempts to remove the cutoff while holding a nonzero low-energy interaction fixed fail;
- physical predictions become sensitive to the cutoff or to new short-distance input.

The invariant statement is not “the pole occurs at this exact number.” The invariant statement is that a given low-energy description cannot be used as a complete ultraviolet theory without further structure.

## Landau poles in EFT language

From the EFT viewpoint, a UV Landau pole is not embarrassing by itself. An EFT always has a domain of validity. If the pole lies above the cutoff where the EFT is replaced by new physics, then the pole is outside the EFT's job description.

For example, a low-energy scalar EFT may have a quartic coupling that would hit a Landau pole if extrapolated. That only tells us that the scalar EFT cannot be the final theory to arbitrarily high energies. It does not stop the EFT from organizing low-energy scattering, symmetry breaking, or phase-transition physics below its cutoff.

The EFT attitude is:

$$
\text{do not demand immortality from an effective description.}
$$

Demand instead that it is predictive within its regime, that all operators allowed by symmetries are organized by power counting, and that uncertainty from omitted short-distance physics is estimated honestly.

## Common pitfalls

**Treating the pole as an observable explosion.** The pole is a singularity of a running coupling in a description. Observables require their own analysis.

**Trusting perturbation theory at the pole.** The formula that finds the pole has normally become unreliable before the pole is reached.

**Confusing an ultraviolet Landau pole with the QCD scale.** A UV Landau pole suggests a short-distance problem. The QCD strong scale marks infrared strong coupling in an asymptotically free theory.

**Declaring an EFT inconsistent because it has a Landau pole above its cutoff.** EFTs are allowed to have limited domains. That is their entire brand.

**Ignoring thresholds.** Real running couplings change when new charged particles, heavy fields, or new interactions become active.

**Comparing pole locations across schemes too literally.** The precise numerical location is not invariant under finite redefinitions of the coupling.

## Relations to other pages

[Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/) gives the general RG flow picture. [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/) explains why the coordinate location of a pole is not by itself an observable. [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/) explains the scale generated by asymptotically free running. [Asymptotic Freedom](/renormalization-rg-eft/renormalization-group-equations/asymptotic-freedom/) explains the opposite UV behavior.

Later, [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/) reframes Landau poles as part of the general lesson that low-energy theories need not be valid at all scales. [Naturalness and Power Counting](/renormalization-rg-eft/naturalness-power-counting/) uses related logic when discussing cutoff sensitivity, triviality bounds, and UV completion.

## Research status

The perturbative definition of a Landau pole is settled. The deeper question is what an apparent Landau pole means in a particular theory.

For QED, the pole lies so far above ordinary scales that pure-QED extrapolation is not physically isolated from electroweak and gravitational physics. For four-dimensional scalar theories, triviality questions are connected to lattice continuum limits and Higgs-sector EFT bounds. For model building, Landau poles often act as practical constraints: a proposed theory may become strongly coupled below the scale where it was meant to remain predictive.

More speculative possibilities include asymptotic safety, compositeness, dual descriptions, or emergent gauge fields that replace the naive coupling before a pole is reached. Those possibilities must be demonstrated in the theory at hand; they are not automatic loopholes.

## Exercises

### Exercise 1: Solve the one-loop Landau equation

Let

$$
\frac{dg}{d\log\mu}=b g^3,
\qquad b>0.
$$

Solve for $g(\mu)$ in terms of $g(\mu_0)$ and find the Landau pole.

<details><summary><strong>Solution</strong></summary>

Write

$$
\frac{dg}{g^3}=b\,d\log\mu.
$$

Integrating,

$$
-\frac{1}{2g^2(\mu)}+\frac{1}{2g^2(\mu_0)}=b\log\frac{\mu}{\mu_0}.
$$

Thus

$$
\frac{1}{g^2(\mu)}=\frac{1}{g^2(\mu_0)}-2b\log\frac{\mu}{\mu_0},
$$

and

$$
g^2(\mu)=
\frac{g^2(\mu_0)}{1-2b g^2(\mu_0)\log(\mu/\mu_0)}.
$$

The pole occurs when the denominator vanishes:

$$
\mu_L=\mu_0\exp\left[\frac{1}{2b g^2(\mu_0)}\right].
$$

</details>

### Exercise 2: QED pole scale at one loop

For one-flavor QED,

$$
\frac{d\alpha}{d\log\mu}=\frac{2}{3\pi}\alpha^2.
$$

Find $\mu_L/\mu_0$ in terms of $\alpha(\mu_0)$.

<details><summary><strong>Solution</strong></summary>

The equation has the same form as

$$
\frac{d\alpha}{dt}=c\alpha^2,
\qquad c=\frac{2}{3\pi}.
$$

Therefore

$$
\frac{1}{\alpha(\mu)}=\frac{1}{\alpha(\mu_0)}-\frac{2}{3\pi}\log\frac{\mu}{\mu_0}.
$$

The pole is at

$$
\log\frac{\mu_L}{\mu_0}=\frac{3\pi}{2\alpha(\mu_0)},
$$

so

$$
\frac{\mu_L}{\mu_0}=\exp\left[\frac{3\pi}{2\alpha(\mu_0)}\right].
$$

For $\alpha(\mu_0)\simeq 1/137$, the exponent is about $645$, so the formal pole is unimaginably far above $\mu_0$.

</details>

### Exercise 3: A triviality-style bound

Suppose four-dimensional $\phi^4$ theory has one-loop running

$$
\frac{d\lambda}{d\log\mu}=\frac{3\lambda^2}{16\pi^2}.
$$

If the EFT is required to have no Landau pole below a cutoff $\Lambda_{\text{cut}}$, show that

$$
\lambda(\mu_0)<\frac{16\pi^2}{3\log(\Lambda_{\text{cut}}/\mu_0)}.
$$

<details><summary><strong>Solution</strong></summary>

The pole condition is

$$
\log\frac{\mu_L}{\mu_0}=\frac{16\pi^2}{3\lambda(\mu_0)}.
$$

Requiring $\mu_L>\Lambda_{\text{cut}}$ gives

$$
\frac{16\pi^2}{3\lambda(\mu_0)}>
\log\frac{\Lambda_{\text{cut}}}{\mu_0}.
$$

Solving for $\lambda(\mu_0)$ gives

$$
\lambda(\mu_0)<
\frac{16\pi^2}{3\log(\Lambda_{\text{cut}}/\mu_0)}.
$$

As $\Lambda_{\text{cut}}\to\infty$, the allowed fixed low-energy coupling tends to zero in this one-loop argument.

</details>

### Exercise 4: The infrared pole of an asymptotically free coupling

For

$$
\frac{dg}{d\log\mu}=-b_0g^3,
\qquad b_0>0,
$$

show that the formal pole occurs in the infrared rather than the ultraviolet.

<details><summary><strong>Solution</strong></summary>

Integrating gives

$$
\frac{1}{g^2(\mu)}=\frac{1}{g^2(\mu_0)}+2b_0\log\frac{\mu}{\mu_0}.
$$

The right-hand side grows as $\mu$ is increased, so $g(\mu)$ decreases toward the ultraviolet. It vanishes only logarithmically as $\mu\to\infty$.

The denominator vanishes when

$$
\log\frac{\mu}{\mu_0}=-\frac{1}{2b_0g^2(\mu_0)},
$$

so

$$
\mu=\mu_0\exp\left[-\frac{1}{2b_0g^2(\mu_0)}\right],
$$

which lies below $\mu_0$. The pole is therefore an infrared strong-coupling scale in the one-loop formula.

</details>

## References

- L. D. Landau, A. A. Abrikosov, and I. M. Khalatnikov, early work on charge renormalization and the zero-charge problem.
- Sidney Coleman, *Aspects of Symmetry*, especially “Dilatations” and “Asymptotic Freedom.”
- Mark Srednicki, *Quantum Field Theory*, especially the sections on renormalization schemes, the renormalization group, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters on renormalizability, nonrenormalizable theories, and the renormalization group.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the relation between Landau poles, triviality, continuum limits, and critical behavior.
- Kenneth G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974) 75–200.

## Version history

- 2026-06-17: First polished draft. Added one-loop derivations, QED and $\phi^4$ examples, triviality interpretation, EFT reading, and distinctions from asymptotically free infrared strong-coupling scales.
