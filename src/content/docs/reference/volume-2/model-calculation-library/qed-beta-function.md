---
title: "QED Beta Function"
description: "Derive the one-loop QED beta function from vacuum polarization and the Ward identity, then interpret charge screening, running alpha, thresholds, and the Landau pole."
sidebar:
  label: "QED Beta Function"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §66; Schwartz 2014, chs. 16, 23, and 26; Weinberg 1995, Vol. I ch. 12; Coleman 1985, Dilatations; Coleman 2019, Ward identities and renormalization lectures."
topics:
  - QED beta function
  - vacuum polarization
  - running electric charge
  - Ward identity
  - charge screening
  - Landau pole
canonicalTopics:
  - qed-beta-function
  - qed-running-coupling
  - vacuum-polarization-running
researchStatus:
  established:
    - "The one-loop QED beta function is a standard consequence of vacuum polarization and the Ward identity."
  active:
    - "Precision running of the electromagnetic coupling requires threshold matching, hadronic vacuum polarization, electroweak embedding, and scheme-specific definitions beyond this one-loop benchmark."
---

## Summary

The one-loop QED beta function is positive. With one Dirac fermion of unit charge and the convention

$$
\beta_e\equiv \left.\mu\frac{de}{d\mu}\right|_{e_0},
$$

the result is

$$
\boxed{
\beta_e=\frac{e^3}{12\pi^2}+O(e^5)
}
$$

or, in terms of

$$
\alpha=\frac{e^2}{4\pi},
$$

$$
\boxed{
\beta_\alpha\equiv\mu\frac{d\alpha}{d\mu}
=
\frac{2}{3\pi}\alpha^2+O(\alpha^3).
}
$$

For several Dirac fermions of charges $Q_f e$,

$$
\beta_e=\frac{e^3}{12\pi^2}\sum_f Q_f^2+O(e^5),
\qquad
\beta_\alpha=\frac{2\alpha^2}{3\pi}\sum_f Q_f^2+O(\alpha^3).
$$

The sign has a physical interpretation: charged particle-antiparticle fluctuations screen electric charge at long distances. As one probes shorter distances, less screening is included inside the probe scale, so the effective electric charge increases. In perturbative one-loop running this eventually produces a Landau pole, which should be read as a warning about the limited domain of pure QED rather than as a measured ultraviolet catastrophe.

:::note[The whole derivation in one sentence]
Vacuum polarization gives a pole in $Z_A$, the Ward identity gives $Z_e=Z_A^{-1/2}$, and fixed bare charge $e_0$ turns the pole coefficient into $\beta_e=e^3/(12\pi^2)$.
:::

## Prerequisites

You should know [QED One-Loop Renormalization](/renormalization-rg-eft/model-calculation-library/qed-one-loop-renormalization/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/), [Landau Poles](/renormalization-rg-eft/renormalization-group-equations/landau-poles/), and [Ward Identities and Renormalization](/renormalization-rg-eft/gauge-theories-and-rg/ward-identities-and-renormalization/).

We use

$$
d=4-2\epsilon,
\qquad
\frac{1}{\bar\epsilon}=\frac{1}{\epsilon}-\gamma_E+\log4\pi,
$$

and the volume convention that increasing $\mu$ means moving toward the ultraviolet in renormalized perturbation theory.

## The input from one-loop renormalization

The one-loop photon vacuum polarization gives

$$
Z_A
=
1-\frac{e^2}{12\pi^2}\frac{1}{\bar\epsilon}+O(e^4)
$$

for one Dirac fermion of unit charge. The Ward identity gives

$$
Z_1=Z_\psi,
$$

so the charge renormalization constant is

$$
Z_e=Z_1Z_\psi^{-1}Z_A^{-1/2}=Z_A^{-1/2}.
$$

Expanding to order $e^2$,

$$
Z_e
=
1+\frac{e^2}{24\pi^2}\frac{1}{\bar\epsilon}+O(e^4).
$$

Therefore the bare charge is

$$
e_0
=
\mu^\epsilon e
\left[
1+\frac{e^2}{24\pi^2}\frac{1}{\bar\epsilon}+O(e^4)
\right].
$$

For the beta function, the finite $-\gamma_E+\log4\pi$ part of $1/\bar\epsilon$ is not essential. The pole coefficient is the same if we write

$$
e_0
=
\mu^\epsilon\left[e+c\frac{e^3}{\epsilon}+O(e^5)\right],
\qquad
c=\frac{1}{24\pi^2}.
$$

## Derivation from fixed bare charge

The bare charge $e_0$ is independent of the arbitrary renormalization scale $\mu$. Differentiate at fixed $e_0$:

$$
0=
\mu\frac{d e_0}{d\mu}.
$$

Using

$$
e_0=\mu^\epsilon\left(e+c\frac{e^3}{\epsilon}\right)+O(e^5),
$$

we obtain

$$
0=
\epsilon\mu^\epsilon\left(e+c\frac{e^3}{\epsilon}\right)
+
\mu^\epsilon\beta_e\left(1+3c\frac{e^2}{\epsilon}\right)
+O(e^5).
$$

Now write

$$
\beta_e=-\epsilon e+b e^3+O(e^5).
$$

The term $-\epsilon e$ is the engineering-dimension part: in $d=4-2\epsilon$, the gauge coupling has mass dimension $\epsilon$. Substituting the ansatz gives

$$
0=
\epsilon e+c e^3
+
(-\epsilon e+b e^3)\left(1+3c\frac{e^2}{\epsilon}\right)
+O(e^5).
$$

The product

$$
(-\epsilon e)\left(3c\frac{e^2}{\epsilon}\right)
$$

is finite and must be kept. Thus

$$
0=
\epsilon e+c e^3-\epsilon e+b e^3-3c e^3+O(e^5)
=
(b-2c)e^3+O(e^5).
$$

Therefore

$$
b=2c=\frac{1}{12\pi^2},
$$

so

$$
\beta_e=-\epsilon e+\frac{e^3}{12\pi^2}+O(e^5).
$$

In four dimensions,

$$
\beta_e=\frac{e^3}{12\pi^2}+O(e^5).
$$

:::tip[Do not drop the engineering term too soon]
The finite one-loop beta function comes partly from multiplying the tree-level term $-\epsilon e$ by the $1/\epsilon$ pole in the renormalization constant. Setting $\epsilon=0$ before differentiating loses the beta function.
:::

## Running alpha

Since

$$
\alpha=\frac{e^2}{4\pi},
$$

we have

$$
\beta_\alpha
=
\mu\frac{d}{d\mu}\left(\frac{e^2}{4\pi}\right)
=
\frac{e}{2\pi}\beta_e.
$$

Using the one-loop beta function,

$$
\beta_\alpha
=
\frac{e^4}{24\pi^3}+O(e^6)
=
\frac{2}{3\pi}\alpha^2+O(\alpha^3).
$$

The one-loop RG equation is

$$
\frac{d\alpha}{d\log\mu}
=
\frac{2}{3\pi}\alpha^2.
$$

Separating variables gives

$$
\frac{1}{\alpha(\mu)}
=
\frac{1}{\alpha(\mu_0)}
-
\frac{2}{3\pi}\log\frac{\mu}{\mu_0}.
$$

Equivalently,

$$
\alpha(\mu)
=
\frac{\alpha(\mu_0)}{
1-\frac{2\alpha(\mu_0)}{3\pi}\log(\mu/\mu_0)
}
$$

at one loop for a single active Dirac fermion of unit charge.

For multiple active fermions,

$$
\frac{1}{\alpha(\mu)}
=
\frac{1}{\alpha(\mu_0)}
-
\frac{2}{3\pi}\left(\sum_f Q_f^2\right)\log\frac{\mu}{\mu_0}.
$$

## Screening interpretation

The positive beta function is often summarized by saying that QED screens electric charge. The idea is:

$$
\text{bare source}
\quad\longrightarrow\quad
\text{polarized virtual pairs}
\quad\longrightarrow\quad
\text{smaller long-distance effective charge}.
$$

At large distances, the probe sees the bare source plus the surrounding polarization cloud. At shorter distances, the probe penetrates more of the cloud and sees a larger effective charge. In RG language, $e(\mu)$ increases with $\mu$.

This interpretation is useful but should not be over-literal. The renormalized coupling $e(\mu)$ is scheme-dependent, and different physical definitions of the electromagnetic coupling differ by finite terms. The sign of the leading running, however, is robust.

## Landau pole

The one-loop running formula has a pole when the denominator vanishes:

$$
1-\frac{2\alpha(\mu_0)}{3\pi}\log\frac{\mu_L}{\mu_0}=0.
$$

Thus

$$
\mu_L
=
\mu_0\exp\left(\frac{3\pi}{2\alpha(\mu_0)}\right)
$$

for one active unit-charge Dirac fermion. More generally,

$$
\mu_L
=
\mu_0\exp\left[
\frac{3\pi}{2\alpha(\mu_0)\sum_f Q_f^2}
\right].
$$

This is the perturbative Landau pole. It says that pure QED cannot be extrapolated to arbitrarily high energy while remaining weakly coupled under this one-loop flow.

It does not mean that an experiment literally reaches an infinite charge. Long before that formal scale is relevant, ordinary QED is no longer the complete theory of nature: electroweak physics, charged matter thresholds, and whatever ultraviolet completion is appropriate must be included. The Landau pole is a consistency warning for a theory considered in isolation.

## Thresholds and active charges

In a mass-independent scheme such as $\overline{\mathrm{MS}}$, a heavy charged fermion contributes to the beta function even for $\mu$ far below its mass unless one explicitly matches to an EFT in which that fermion has been integrated out. The physical low-energy description uses active charged fields appropriate to the scale.

A practical running prescription is:

1. run with the beta function of the theory valid above a charged threshold;
2. match the coupling near the mass $M$ of the charged particle;
3. run below $M$ with the particle removed from the active spectrum.

Symbolically,

$$
\alpha_{\text{high}}(\mu=M)
\quad\longleftrightarrow\quad
\alpha_{\text{low}}(\mu=M)+\text{threshold correction}.
$$

At one loop, choosing $\mu$ near $M$ avoids large logarithms. Higher-order precision requires keeping finite matching terms and using the appropriate physical definition of the electromagnetic coupling.

## Relation to vacuum polarization in momentum space

A physical charge can be defined from the coefficient of the photon propagator at momentum transfer $q^2$. At one loop, the renormalized vacuum polarization contains a logarithm of the form

$$
\Pi_R(q^2)\sim \frac{e^2}{12\pi^2}\log\frac{-q^2}{\mu^2}+\text{scheme-dependent constant}
$$

for spacelike $q^2$ large compared with the fermion mass. The logarithm is the finite remnant of the same UV pole that produced $Z_A$.

Choosing $\mu^2\sim -q^2$ moves the large logarithm into the running coupling. This is the practical meaning of RG improvement in QED:

$$
\text{fixed-order logs in }\Pi_R(q^2)
\quad\longleftrightarrow\quad
\text{running }\alpha(\mu).
$$

## Comparison with phi-four theory

At one loop, real scalar $\phi^4$ theory and QED both have positive beta functions in four dimensions:

$$
\beta_\lambda=\frac{3\lambda^2}{16\pi^2}+O(\lambda^3),
\qquad
\beta_e=\frac{e^3}{12\pi^2}+O(e^5).
$$

The mechanisms are different. In $\phi^4$ theory, the four-point bubble directly renormalizes the quartic coupling. In QED, the Ward identity removes the independent vertex contribution from charge renormalization, leaving vacuum polarization as the source of running. The positive sign in QED has a screening interpretation; the positive sign in scalar theory is better understood as the flow of a local contact interaction.

The contrast with Yang–Mills theory is even sharper. Nonabelian gauge bosons carry the gauge charge, and their loops produce antiscreening. That is why QCD can have

$$
\beta_g<0
$$

at weak coupling, while QED has

$$
\beta_e>0.
$$

## Common pitfalls

**Deriving the beta function from $Z_1$ alone.** In QED, the Ward identity gives $Z_1=Z_\psi$. The charge renormalization is controlled by $Z_A$, not by the vertex factor by itself.

**Calling $\mu$ a physical momentum cutoff.** The scale $\mu$ is a renormalization scale. A physical momentum transfer $Q$ enters observables; setting $\mu\sim Q$ is a choice that improves perturbative convergence.

**Ignoring thresholds.** A formula with $\sum_f Q_f^2$ assumes a specified active spectrum. Charged particles heavier than the process scale should be integrated out and matched.

**Overinterpreting the Landau pole.** The one-loop Landau pole is a signal that pure perturbative QED is not an autonomous UV-complete weakly coupled theory. It is not a direct experimental prediction of an infinite charge.

**Forgetting scheme dependence.** The one-loop coefficient is universal in ordinary definitions, but finite definitions of the running electromagnetic coupling differ. Higher-order statements require a scheme.

**Confusing QED running with QCD running.** QED matter screens; nonabelian gauge fields antiscreen. The sign difference is one of the most important lessons in gauge-theory RG.

## Relations to other pages

This page follows [QED One-Loop Renormalization](/renormalization-rg-eft/model-calculation-library/qed-one-loop-renormalization/). It is the abelian companion to [Yang–Mills One-Loop Beta Function](/renormalization-rg-eft/model-calculation-library/yang-mills-one-loop-beta-function/) when that page is available. For conceptual background, see [QED Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/qed-beta-function/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Landau Poles](/renormalization-rg-eft/renormalization-group-equations/landau-poles/), and [Gauge Theories and RG](/renormalization-rg-eft/gauge-theories-and-rg/).

For EFT threshold logic, see [Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/) and [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/).

## Research status

The one-loop QED beta function is established. Precision electromagnetic running is much richer: low-energy definitions involve Thomson-limit charge, high-energy definitions often use $\alpha(q^2)$, hadronic vacuum polarization cannot be computed purely perturbatively at low energies, and electroweak unification changes the degrees of freedom at high scales. This page is the clean one-loop benchmark, not a precision-data review.

## Exercises

### Exercise 1: Derive beta e from the pole coefficient

Let

$$
e_0=\mu^\epsilon\left(e+c\frac{e^3}{\epsilon}\right)+O(e^5).
$$

Show that

$$
\beta_e=-\epsilon e+2c e^3+O(e^5).
$$

<details><summary><strong>Solution</strong></summary>

Differentiate at fixed $e_0$:

$$
0=\epsilon\left(e+c\frac{e^3}{\epsilon}\right)
+\beta_e\left(1+3c\frac{e^2}{\epsilon}\right)+O(e^5).
$$

Use the ansatz

$$
\beta_e=-\epsilon e+b e^3+O(e^5).
$$

Then

$$
0=\epsilon e+c e^3-\epsilon e+b e^3-3c e^3+O(e^5)
=(b-2c)e^3+O(e^5).
$$

Therefore $b=2c$, so

$$
\beta_e=-\epsilon e+2c e^3+O(e^5).
$$

</details>

### Exercise 2: Convert beta e to beta alpha

Starting from

$$
\beta_e=\frac{e^3}{12\pi^2},
\qquad
\alpha=\frac{e^2}{4\pi},
$$

show that

$$
\beta_\alpha=\frac{2}{3\pi}\alpha^2.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate $\alpha=e^2/(4\pi)$:

$$
\beta_\alpha
=\mu\frac{d}{d\mu}\frac{e^2}{4\pi}
=\frac{e}{2\pi}\beta_e.
$$

Substitute the one-loop result:

$$
\beta_\alpha
=\frac{e}{2\pi}\frac{e^3}{12\pi^2}
=\frac{e^4}{24\pi^3}.
$$

Since $e^4=(4\pi\alpha)^2=16\pi^2\alpha^2$,

$$
\beta_\alpha
=\frac{16\pi^2\alpha^2}{24\pi^3}
=\frac{2}{3\pi}\alpha^2.
$$

</details>

### Exercise 3: Integrate the running coupling

Solve

$$
\frac{d\alpha}{d\log\mu}=b\alpha^2
$$

with initial condition $\alpha(\mu_0)=\alpha_0$.

<details><summary><strong>Solution</strong></summary>

Separate variables:

$$
\frac{d\alpha}{\alpha^2}=b\,d\log\mu.
$$

Integrating from $\mu_0$ to $\mu$ gives

$$
-\frac{1}{\alpha(\mu)}+\frac{1}{\alpha_0}=b\log\frac{\mu}{\mu_0}.
$$

Therefore

$$
\frac{1}{\alpha(\mu)}=\frac{1}{\alpha_0}-b\log\frac{\mu}{\mu_0},
$$

or

$$
\alpha(\mu)=\frac{\alpha_0}{1-b\alpha_0\log(\mu/\mu_0)}.
$$

For one-flavor QED, $b=2/(3\pi)$.

</details>

### Exercise 4: Charges and multiplicities

A theory contains an electron of charge $-e$, a muon of charge $-e$, and a Dirac fermion of charge $2e$, all active at the scale of interest. What is the one-loop coefficient in $\beta_\alpha$?

<details><summary><strong>Solution</strong></summary>

The coefficient is weighted by $\sum_f Q_f^2$. The three charges in units of $e$ are

$$
Q_f=-1,-1,2.
$$

Thus

$$
\sum_f Q_f^2=1+1+4=6.
$$

Therefore

$$
\beta_\alpha
=\frac{2}{3\pi}(6)\alpha^2+O(\alpha^3)
=\frac{4}{\pi}\alpha^2+O(\alpha^3).
$$

</details>

### Exercise 5: Estimate the one-loop Landau pole

For one active unit-charge fermion, show that the one-loop Landau pole is

$$
\mu_L=\mu_0\exp\left(\frac{3\pi}{2\alpha(\mu_0)}\right).
$$

<details><summary><strong>Solution</strong></summary>

The one-loop solution is

$$
\alpha(\mu)=\frac{\alpha(\mu_0)}{1-\frac{2\alpha(\mu_0)}{3\pi}\log(\mu/\mu_0)}.
$$

The pole occurs when the denominator vanishes:

$$
1-\frac{2\alpha(\mu_0)}{3\pi}\log\frac{\mu_L}{\mu_0}=0.
$$

Solving gives

$$
\log\frac{\mu_L}{\mu_0}=\frac{3\pi}{2\alpha(\mu_0)},
$$

hence

$$
\mu_L=\mu_0\exp\left(\frac{3\pi}{2\alpha(\mu_0)}\right).
$$

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially the chapter on beta functions in quantum electrodynamics.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on vacuum polarization, renormalization-group equations, and Yang–Mills running for comparison.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, for the general relation between renormalization constants and beta functions.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," for the physical role of running couplings and the Callan–Symanzik viewpoint.

## Version history

- 2026-06-19: First polished draft. Derived the one-loop QED beta function from $Z_A$ and the Ward identity, added running-$\alpha$ solution, threshold caveats, Landau-pole interpretation, and exercises.
