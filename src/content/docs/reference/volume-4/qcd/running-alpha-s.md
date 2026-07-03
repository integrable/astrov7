---
title: "Running Alpha s"
description: "Explains how the strong coupling alpha s runs with scale, how Lambda QCD and active-flavor thresholds enter, and how to use the coupling consistently in perturbative QCD."
sidebar:
  label: "Running Alpha s"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§73 and 81–82; Schwartz Chs. 26 and 32; Weinberg Vol. II Ch. 18; Wilson and Kogut; Coleman, Aspects of Symmetry, Ch. 5."
topics:
  - running alpha s
  - strong coupling
  - Lambda QCD
  - threshold matching
  - perturbative QCD
  - dimensional transmutation
canonicalTopics:
  - running-alpha-s
  - qcd-scale
  - strong-coupling-running
  - threshold-matching
  - perturbative-qcd
researchStatus:
  established:
    - "The perturbative running of alpha s at high scales, including heavy-quark threshold matching, is a standard part of QCD phenomenology."
  active:
    - "Precision determinations of alpha s, low-scale effective-charge definitions, lattice extractions, and infrared-safe observables remain active precision-QCD topics."
---

## Summary

The strong coupling is conventionally written

$$
\alpha_s(\mu)=\frac{g_s^2(\mu)}{4\pi}.
$$

It is not a constant in the classical sense. It is a scale-dependent renormalized coupling. At weak coupling,

$$
\mu\frac{d\alpha_s}{d\mu}
=
-
\frac{b_0}{2\pi}\alpha_s^2
-
\frac{b_1}{8\pi^2}\alpha_s^3
+O(\alpha_s^4),
$$

with

$$
b_0=11-\frac23n_f,
\qquad
b_1=102-\frac{38}{3}n_f
$$

for $SU(3)_c$ with $n_f$ active Dirac quark flavors. Since $b_0>0$ for real-world QCD, $\alpha_s(\mu)$ decreases at high scales and grows toward low scales.

At one loop,

$$
\alpha_s(\mu)
=
\frac{4\pi}{b_0\ln(\mu^2/\Lambda^2)}.
$$

The scale $\Lambda$ is the RG integration constant in a chosen scheme and with a chosen number of active flavors. In common notation it becomes $\Lambda_{\rm QCD}$ or, more precisely, $\Lambda_{\overline{\rm MS}}^{(n_f)}$.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Schematic running of alpha_s: strong coupling in the infrared, heavy-quark threshold matching, and asymptotic freedom in the ultraviolet.](/figures/gauge-theories-standard-model/qcd-running-alpha-s.svg)

<figcaption>

Qualitative running of the strong coupling. The curve is not a data plot: it summarizes the perturbative fact that $\alpha_s$ decreases logarithmically at high scales and the practical fact that heavy-quark thresholds change the active theory used to describe the same physics.

</figcaption>
</figure>

## Prerequisites

You should first read [QCD Beta Function](/gauge-theories-standard-model/qcd/qcd-beta-function/). That page explains the coefficients $b_0$ and $b_1$ and the origin of their signs.

You should also know [QCD Lagrangian](/gauge-theories-standard-model/qcd/qcd-lagrangian/), [Quarks and Gluons](/gauge-theories-standard-model/qcd/quarks-and-gluons/), [Asymptotic Freedom](/gauge-theories-standard-model/gauge-renormalization/asymptotic-freedom/), and [Dimensional Transmutation in Gauge Theory](/gauge-theories-standard-model/gauge-renormalization/dimensional-transmutation-in-gauge-theory/).

This page assumes a mass-independent renormalization scheme such as $\overline{\rm MS}$ unless stated otherwise. The qualitative ultraviolet running is scheme-independent, but numerical values of $\alpha_s(\mu)$ and $\Lambda$ are scheme-dependent.

## Core idea

The running coupling is a bookkeeping device with physical bite. It summarizes the logarithmic dependence on a momentum scale that appears in short-distance QCD calculations.

A typical perturbative prediction contains logarithms such as

$$
\ln\frac{Q}{\mu},
$$

where $Q$ is a physical hard scale and $\mu$ is the renormalization scale. Choosing $\mu$ near $Q$ keeps explicit logarithms small. The remaining scale dependence is then mostly carried by the running coupling $\alpha_s(Q)$.

This gives the working intuition

$$
Q\text{ large}
\quad\Longrightarrow\quad
\alpha_s(Q)\text{ small}
\quad\Longrightarrow\quad
\text{perturbative quarks and gluons are useful}.
$$

As $Q$ decreases toward hadronic scales, the coupling grows and perturbation theory loses control. The low-energy theory is still QCD, but the useful observables are color-singlet hadrons, currents, Wilson loops, finite-volume spectra, and effective degrees of freedom—not isolated quarks, gluons, and a small expansion parameter.

## Setup and conventions

We define

$$
\alpha_s=\frac{g_s^2}{4\pi}.
$$

The perturbative beta function is

$$
\mu\frac{d\alpha_s}{d\mu}
=
-\frac{b_0}{2\pi}\alpha_s^2
-\frac{b_1}{8\pi^2}\alpha_s^3
+O(\alpha_s^4).
$$

For $SU(3)_c$ with $n_f$ active fundamental Dirac quarks,

$$
b_0=11-\frac23n_f,
\qquad
b_1=102-\frac{38}{3}n_f.
$$

The phrase “active flavor” means that the quark is included as a dynamical degree of freedom in the effective theory at that scale. For a scale below a heavy-quark mass, it is usually better to integrate that heavy quark out and use a theory with one fewer active flavor. Near the threshold, one matches the two descriptions.

## One-loop running

At one loop,

$$
\mu\frac{d\alpha_s}{d\mu}
=
-\frac{b_0}{2\pi}\alpha_s^2.
$$

Separate variables:

$$
\frac{d\alpha_s}{\alpha_s^2}
=
-\frac{b_0}{2\pi}d\ln\mu.
$$

Integrating between $\mu_0$ and $\mu$ gives

$$
\frac{1}{\alpha_s(\mu)}
=
\frac{1}{\alpha_s(\mu_0)}
+
\frac{b_0}{2\pi}\ln\frac{\mu}{\mu_0}.
$$

This formula already contains the physics:

- increasing $\mu$ increases $1/\alpha_s$;
- therefore increasing $\mu$ decreases $\alpha_s$;
- the decrease is only logarithmic, so it is slow.

Introducing an integration constant $\Lambda$ gives the more compact form

$$
\alpha_s(\mu)
=
\frac{2\pi}{b_0\ln(\mu/\Lambda)}
=
\frac{4\pi}{b_0\ln(\mu^2/\Lambda^2)}.
$$

The two versions are identical. The second is common because scattering calculations often use $Q^2$ as the argument.

## Lambda QCD

Solving the one-loop formula for $\Lambda$ gives

$$
\Lambda
=
\mu\exp\left[-\frac{2\pi}{b_0\alpha_s(\mu)}\right].
$$

This is dimensional transmutation in QCD. The coupling $\alpha_s(\mu)$ and the arbitrary scale $\mu$ are traded for a scale $\Lambda$. In a specified scheme and with a specified $n_f$, this scale is an RG-invariant way of labeling the theory.

Three warnings are essential.

First, $\Lambda$ is not a hadron mass by itself. It sets the rough strong scale, but physical hadron masses, decay constants, condensates, and string tensions are nonperturbative quantities.

Second, $\Lambda$ is scheme-dependent. The symbol $\Lambda_{\overline{\rm MS}}^{(5)}$, for example, means the $\overline{\rm MS}$ definition with five active flavors. A different scheme gives a different numerical Lambda even when it describes the same physics.

Third, the apparent one-loop singularity at $\mu=\Lambda$ is not a trustworthy physical singularity. It is the point where the weak-coupling formula announces its own retirement. Sensible fellow, that formula.

## Two-loop running

At two loops,

$$
\mu\frac{d\alpha_s}{d\mu}
=
-\frac{b_0}{2\pi}\alpha_s^2
-\frac{b_1}{8\pi^2}\alpha_s^3.
$$

For $\mu\gg\Lambda$, it is useful to write

$$
L\equiv\ln\frac{\mu^2}{\Lambda^2}.
$$

Then the large-$L$ expansion is

$$
\alpha_s(\mu)
=
\frac{4\pi}{b_0L}
\left[
1
-
\frac{b_1}{b_0^2}\frac{\ln L}{L}
+O\left(\frac{1}{L^2}\right)
\right].
$$

This formula is not meant for the deep infrared. It is an ultraviolet expansion improved by the renormalization group.

For precision work, one does not usually stop at this displayed expression. One specifies a scheme, includes higher-loop beta-function coefficients, includes threshold matching, chooses an appropriate scale, and estimates residual perturbative uncertainty.

## Heavy-quark thresholds

QCD contains quarks with very different masses. A calculation at a scale far below a heavy-quark mass should not treat that heavy quark as an ordinary light dynamical parton. The standard logic is effective field theory:

$$
\text{above }m_Q:
\quad n_f+1\text{ active flavors},
$$

$$
\text{below }m_Q:
\quad n_f\text{ active flavors}.
$$

At a matching scale $\mu_Q$ of order $m_Q$, the couplings in the two effective theories are related:

$$
\alpha_s^{(n_f+1)}(\mu_Q)
\quad\longleftrightarrow\quad
\alpha_s^{(n_f)}(\mu_Q).
$$

At one-loop order, one often treats the coupling as continuous across the threshold if the matching scale is chosen near the heavy-quark mass. At higher orders, finite matching corrections appear. The final answer for a physical observable should not depend on the arbitrary matching scale when all orders are included. At finite order, residual matching-scale dependence is another estimate of missing higher-order terms.

The same idea explains why the superscript in $\Lambda_{\overline{\rm MS}}^{(n_f)}$ matters. The beta-function coefficient changes when $n_f$ changes, so the integration constant in the running solution changes as well.

## Choosing the renormalization scale

The scale $\mu$ is not a new physical knob on nature. It is a scale introduced by the renormalization procedure. A physical observable $\mathcal O$ is independent of $\mu$ when computed exactly:

$$
\mu\frac{d}{d\mu}\mathcal O=0.
$$

At finite order in perturbation theory, however, the cancellation is incomplete. A practical calculation must choose $\mu$. The basic rule is:

$$
\mu\sim Q,
$$

where $Q$ is the hard physical scale of the process. This avoids large logarithms in the fixed-order coefficients. If a problem has several separated scales, one often needs factorization and RG evolution between scales rather than a single magic choice of $\mu$.

A conventional uncertainty estimate varies $\mu$ by a moderate factor around the central scale. This is not a theorem about errors. It is a diagnostic for missing higher-order logarithms and coefficients.

## Alpha s is not an observable by itself

A common trap is to talk as if $\alpha_s(\mu)$ were directly measured in isolation. What experiments measure are physical quantities: event shapes, jet rates, hadronic tau decays, deep-inelastic scattering, lattice observables, quarkonium splittings, and many others. A value of $\alpha_s$ is extracted by comparing such observables with QCD calculations in a specified scheme.

This matters because there are many possible definitions of a strong effective charge:

| Definition type | Typical use | Caveat |
|---|---|---|
| $\overline{\rm MS}$ coupling | Standard perturbative QCD and global comparisons | Not tied directly to one physical potential or cross section. |
| Momentum-subtraction couplings | Gauge-fixed Green-function studies | Often gauge and scheme dependent. |
| Potential-scheme couplings | Heavy-quark static potential | Natural for static sources, not universal bookkeeping. |
| Lattice or gradient-flow couplings | Nonperturbative scale setting and step scaling | Definition depends on finite-volume or flow setup. |
| Effective charges from observables | Direct physical interpretation for one observable | Different observables define different charges beyond leading universal behavior. |

The first two beta-function coefficients agree under ordinary scheme changes. The detailed low-scale behavior of a chosen coupling need not be universal.

## Relation to partons and factorization

The running of $\alpha_s$ is one piece of perturbative QCD. It is not the whole story.

In high-energy hadronic processes, one also encounters parton distribution functions, fragmentation functions, jet functions, soft functions, and factorization scales. These objects also obey RG equations. The running coupling enters their evolution, but it does not replace them.

For example, deep-inelastic scattering involves a hard scale $Q$ and parton distributions that depend on a factorization scale. The QCD prediction separates short-distance coefficients, which are perturbative, from long-distance matrix elements, which are nonperturbative but universal across classes of processes. The running of $\alpha_s$ controls part of the scale dependence of the short-distance coefficients and parton evolution.

This is why the parton model works better at high momentum transfer: not because confinement disappears, but because short-distance sub-processes become weakly coupled and factorization organizes the long-distance physics.

## Infrared interpretation

At low scales, the one-loop formula suggests that $\alpha_s$ becomes large. One should not overinterpret the literal curve. Perturbation theory is an expansion in small $\alpha_s$; once $\alpha_s$ is large, the expansion is no longer self-justifying.

Infrared QCD must be described by other tools:

- lattice QCD for Euclidean nonperturbative observables;
- chiral perturbation theory for pions and other low-energy hadronic processes;
- heavy-quark effective theory for systems with a heavy quark;
- operator product expansions for controlled short-distance expansions inside long-distance observables;
- sum rules, models, and phenomenological descriptions where appropriate.

The running coupling points toward the strong scale. It does not, by itself, calculate the hadron spectrum.

## Common pitfalls

**Using a fixed number of flavors across every scale.** The active-flavor number changes across heavy-quark thresholds. The couplings in adjacent effective theories must be matched.

**Treating $\Lambda_{\rm QCD}$ as a directly measured particle mass.** It is a scheme-dependent RG parameter. It sets the order of strong-interaction scales, but physical masses are separately defined observables.

**Taking the one-loop infrared pole literally.** The pole says perturbation theory has failed. It is not a reliable prediction of a physical singularity.

**Choosing $\mu$ far from the hard scale and then blaming QCD for large logs.** Fixed-order perturbation theory works best when $\mu$ is chosen near the characteristic hard scale. Multiple scales require factorization and RG evolution.

**Forgetting scheme dependence.** A quoted number for $\alpha_s(\mu)$ should come with a scheme, usually $\overline{\rm MS}$, and an active-flavor convention.

**Thinking small $\alpha_s$ means no confinement.** High-energy partons are perturbative over short distances. They still hadronize into color-singlet states at long distances.

## Relations to other pages

This page follows [QCD Beta Function](/gauge-theories-standard-model/qcd/qcd-beta-function/) and applies its coefficients. It connects directly to [Dimensional Transmutation in Gauge Theory](/gauge-theories-standard-model/gauge-renormalization/dimensional-transmutation-in-gauge-theory/), where the general mechanism is explained without specializing to QCD.

It prepares the later QCD pages on chiral symmetry and confinement. The growth of $\alpha_s$ toward low scales motivates those topics but does not solve them. It also prepares the Perturbative QFT and Scattering volume’s pages on factorization, jets, infrared safety, and RG-improved perturbation theory.

## Research status

The perturbative running of $\alpha_s$ at high scales is established and central to precision QCD. High-loop beta functions, threshold matching, and scheme translations are known in standard frameworks and used in modern phenomenology.

Precision extraction of $\alpha_s$ remains active because different observables carry different experimental systematics, nonperturbative corrections, and perturbative uncertainties. Low-scale definitions of effective charges, lattice step-scaling methods, and infrared-safe event-shape extractions are still important areas of work.

## Exercises

### One-loop solution

Starting from

$$
\mu\frac{d\alpha_s}{d\mu}
=-\frac{b_0}{2\pi}\alpha_s^2,
$$

derive

$$
\alpha_s(\mu)=\frac{4\pi}{b_0\ln(\mu^2/\Lambda^2)}.
$$

<details><summary><strong>Solution</strong></summary>

Write $d\ln\mu=d\mu/\mu$. Then

$$
\frac{d\alpha_s}{\alpha_s^2}
=-\frac{b_0}{2\pi}d\ln\mu.
$$

Integrating gives

$$
-\frac{1}{\alpha_s(\mu)}
=-\frac{b_0}{2\pi}\ln\mu + \text{constant}.
$$

Equivalently,

$$
\frac{1}{\alpha_s(\mu)}
=\frac{b_0}{2\pi}\ln\frac{\mu}{\Lambda}.
$$

Invert:

$$
\alpha_s(\mu)
=\frac{2\pi}{b_0\ln(\mu/\Lambda)}.
$$

Since $\ln(\mu^2/\Lambda^2)=2\ln(\mu/\Lambda)$, this is

$$
\alpha_s(\mu)=\frac{4\pi}{b_0\ln(\mu^2/\Lambda^2)}.
$$

</details>

### Changing the scale

Assume $b_0>0$. If $\mu_2>\mu_1$ and both are in the same active-flavor theory, show from the one-loop solution that $\alpha_s(\mu_2)<\alpha_s(\mu_1)$.

<details><summary><strong>Solution</strong></summary>

The one-loop relation between the two scales is

$$
\frac{1}{\alpha_s(\mu_2)}
=
\frac{1}{\alpha_s(\mu_1)}
+
\frac{b_0}{2\pi}\ln\frac{\mu_2}{\mu_1}.
$$

If $\mu_2>\mu_1$, then $\ln(\mu_2/\mu_1)>0$. Since $b_0>0$, the second term is positive. Therefore

$$
\frac{1}{\alpha_s(\mu_2)}>\frac{1}{\alpha_s(\mu_1)}.
$$

For positive coupling this implies

$$
\alpha_s(\mu_2)<\alpha_s(\mu_1).
$$

</details>

### Threshold matching at one loop

Suppose a heavy quark of mass $m_Q$ is integrated out at $\mu_Q=m_Q$, and suppose the one-loop coupling is matched continuously:

$$
\alpha_s^{(n_f+1)}(m_Q)=\alpha_s^{(n_f)}(m_Q).
$$

Explain why the corresponding $\Lambda^{(n_f+1)}$ and $\Lambda^{(n_f)}$ are generally different.

<details><summary><strong>Solution</strong></summary>

At one loop,

$$
\alpha_s^{(n_f)}(\mu)
=
\frac{4\pi}{b_0^{(n_f)}\ln(\mu^2/[\Lambda^{(n_f)}]^2)}.
$$

The coefficient

$$
b_0^{(n_f)}=11-\frac23n_f
$$

changes when the number of active flavors changes. Continuity at $\mu=m_Q$ requires the two formulae to give the same value of $\alpha_s$, but because their $b_0$ values differ, their integration constants must generally differ as well. Thus $\Lambda^{(n_f)}$ is not a universal number independent of the effective theory; it is labeled by the active-flavor convention.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§73 and 81–82, for non-Abelian running and QCD applications.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 26 and 32, for the running coupling, defining the charge, and the QCD parton model.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Ch. 18, for RG methods and running couplings.
- Wilson and Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” for the modern scale-dependence viewpoint behind RG thinking.
- Coleman, *Aspects of Symmetry*, lecture 5, for the classic physical explanation of asymptotic freedom.
- Particle Data Group reviews on QCD and $\alpha_s$ for current numerical world averages and precision determinations.

## Version history

- **2026-06-18:** Initial page. Added one-loop and two-loop running, $\Lambda_{\rm QCD}$ interpretation, heavy-quark thresholds, practical scale choice, exercises, and a qualitative running-coupling figure.
