---
title: "Running Masses"
description: "Explains running masses as scale-dependent relevant couplings, distinguishing them from pole masses, physical thresholds, additive scalar sensitivity, and mass gaps."
sidebar:
  label: "Running Masses"
  order: 5
level: Graduate
status: "Polished draft"
source: "Coleman, Dilatations; Srednicki §§27–29 and 51–52; Schwartz chs. 18, 23, and 26; Weinberg Vol. II ch. 18; Zinn-Justin, RG and critical-phenomena chapters; Burgess 2020, chs. 2–3."
topics:
  - running masses
  - mass anomalous dimensions
  - relevant couplings
  - scalar mass renormalization
  - pole masses
  - thresholds
  - critical phenomena
canonicalTopics:
  - running-mass
  - mass-anomalous-dimension
  - relevant-deformation
  - pole-mass
  - threshold-matching
  - scalar-naturalness
researchStatus:
  established:
    - "Running masses are standard renormalized parameters governed by mass beta functions or mass anomalous dimensions."
  active:
    - "Precision mass schemes, threshold matching, nonperturbative mass definitions, unstable-particle masses, quark masses in QCD, and scalar naturalness remain active technical and conceptual topics."
---

## Summary

A **running mass** is a mass parameter whose numerical value depends on the renormalization scale. It is not automatically the same thing as a physical particle mass.

For a multiplicatively renormalized fermion mass one often writes

$$
\mu\frac{d m}{d\mu}=-\gamma_m(g)m.
$$

The function $\gamma_m(g)$ is the **mass anomalous dimension**. With this sign convention, a positive $\gamma_m$ makes the mass decrease toward the ultraviolet when the coupling is asymptotically free.

For a scalar squared mass it is usually safer to write a beta function directly,

$$
\beta_{m^2}\equiv \mu\frac{d m^2}{d\mu}.
$$

If the flow is multiplicative, then

$$
\beta_{m^2}=\eta_{m^2}(g)m^2.
$$

But scalar masses can also have additive sensitivity to heavy scales or cutoffs when no symmetry protects them. This is why running masses are not a side comment in the RG story. They are where relevance, decoupling, thresholds, pole definitions, criticality, and naturalness first collide.

:::note[The word mass hides several objects]
In QFT, the same symbol $m$ may refer to a bare mass $m_0$, a running mass $m(\mu)$, a pole mass $m_{\text{pole}}$, a threshold mass, a screening mass, a mass gap, or the inverse correlation length. A good calculation says which one is meant before using the symbol.
:::

## Prerequisites

You should know [Conventions and Notation](/renormalization-rg-eft/conventions/), [Callan–Symanzik Equation](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), and [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/).

It is also useful to have read [Mass and Coupling Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/mass-and-coupling-renormalization/) and [Regulator Dependence](/renormalization-rg-eft/why-renormalization/regulator-dependence/). Those pages explain why the mass appearing in the renormalized Lagrangian is not automatically the mass measured by an experiment.

## Core idea

A mass is a coupling multiplying a relevant local operator. For a scalar field,

$$
\mathcal L\supset -\frac12m^2\phi^2.
$$

For a Dirac fermion,

$$
\mathcal L\supset -m\bar\psi\psi.
$$

These terms are special for two reasons.

First, they carry positive mass dimension. In four spacetime dimensions, $m^2$ has dimension two and $m$ has dimension one. Even without loops, the dimensionless ratios $m^2/\mu^2$ and $m/\mu$ change as the reference scale changes.

Second, the operators $\phi^2$ and $\bar\psi\psi$ are composite operators. Their short-distance singularities induce additional scale dependence. The running mass is the coefficient that compensates the running of the operator so that the bare theory or the physical prediction remains unchanged.

The core slogan is

$$
\text{mass running}=\text{canonical relevance}+\text{operator renormalization}+\text{scheme choice}.
$$

This is why mass running appears in different languages. In particle physics it helps define quark masses and improve perturbation theory. In statistical field theory it describes the temperature-like deformation away from a critical point. In EFT it controls threshold matching and decoupling. In naturalness discussions it reveals how sensitive relevant operators can be to short-distance physics.

## Setup and conventions

This volume defines beta functions by differentiating renormalized parameters at fixed bare parameters:

$$
\beta^i(g)=\left.\mu\frac{d g^i}{d\mu}\right|_{\text{bare}}.
$$

For a mass parameter we use the same language:

$$
\beta_m\equiv \left.\mu\frac{d m}{d\mu}\right|_{\text{bare}},
\qquad
\beta_{m^2}\equiv \left.\mu\frac{d m^2}{d\mu}\right|_{\text{bare}}.
$$

For fermion masses, many particle-physics references define

$$
\mu\frac{d m}{d\mu}=-\gamma_m(g)m.
$$

The minus sign is part of this convention. In QCD, $\gamma_m>0$ at weak coupling, so quark masses decrease toward the ultraviolet.

For scalar squared masses, we will often keep the beta function explicit:

$$
\mu\frac{d m^2}{d\mu}=\beta_{m^2}(m^2,g).
$$

If the flow is multiplicative,

$$
\beta_{m^2}=\eta_{m^2}(g)m^2.
$$

If additive sensitivity to a heavy scale $M$ is present, the schematic form may be

$$
\beta_{m^2}=\eta_{m^2}(g)m^2+A(g)M^2+\cdots.
$$

The appearance or absence of such additive terms depends on the regulator, scheme, symmetries, and degrees of freedom retained in the theory. The physical issue they diagnose is real even when a particular scheme hides it.

## Dimensionless masses and relevance

The dimensionful parameter $m$ is not the best object for seeing relevance. Define

$$
\tilde m(\mu)=\frac{m(\mu)}{\mu},
\qquad
\tilde m^2(\mu)=\frac{m^2(\mu)}{\mu^2}.
$$

If

$$
\mu\frac{dm}{d\mu}=-\gamma_m(g)m,
$$

then

$$
\mu\frac{d\tilde m}{d\mu}=-(1+\gamma_m)\tilde m.
$$

For a multiplicatively renormalized scalar mass squared,

$$
\mu\frac{dm^2}{d\mu}=\eta_{m^2}(g)m^2,
$$

we get

$$
\mu\frac{d\tilde m^2}{d\mu}=(-2+\eta_{m^2})\tilde m^2.
$$

The negative signs use $\mu$ as a UV scale: increasing $\mu$ moves upward in energy. Going toward the infrared reverses the intuition. If $\tilde m^2$ satisfies

$$
\mu\frac{d\tilde m^2}{d\mu}\simeq -2\tilde m^2,
$$

then lowering $\mu$ makes $\tilde m^2$ grow. This is the statement that a mass term is relevant.

Near an interacting fixed point, the same statement is written in terms of an RG eigenvalue. If $r$ is the coefficient of a relevant scalar operator with scaling dimension $\Delta_r$ in $d$ spacetime dimensions, then its dimensionless coupling obeys

$$
\mu\frac{d\tilde r}{d\mu}=(\Delta_r-d)\tilde r+\cdots.
$$

Equivalently, using an infrared flow time $\ell=\log(\Lambda_0/\Lambda)$,

$$
\frac{d\tilde r}{d\ell}=y_r\tilde r+\cdots,
\qquad
 y_r=d-\Delta_r.
$$

In critical phenomena, the temperature-like mass deformation has eigenvalue $y_t=1/\nu$, where $\nu$ is the correlation-length critical exponent.

## Multiplicative mass renormalization

A mass renormalizes multiplicatively when the theory has a symmetry or scheme structure preventing additive shifts. Fermion masses often behave this way because a massless fermion theory can have chiral symmetry.

Suppose

$$
\mu\frac{d m}{d\mu}=-\gamma_m(g)m.
$$

The formal solution is

$$
m(\mu)=m(\mu_0)
\exp\left[-\int_{\mu_0}^{\mu}d\log\mu'\,\gamma_m(g(\mu'))\right].
$$

Using the running coupling as the variable,

$$
m(\mu)=m(\mu_0)
\exp\left[-\int_{g(\mu_0)}^{g(\mu)}dg\,\frac{\gamma_m(g)}{\beta(g)}\right].
$$

This formula is one of the main reasons running masses are useful. If a calculation contains logarithms associated with mass renormalization, the RG evolution of $m(\mu)$ resums them.

For an asymptotically free theory with

$$
\beta(g)=-\beta_0\frac{g^3}{16\pi^2}+O(g^5),
\qquad
\gamma_m(g)=\gamma_0\frac{g^2}{16\pi^2}+O(g^4),
$$

the leading solution is

$$
\frac{m(\mu)}{m(\mu_0)}
=
\left[\frac{g(\mu)}{g(\mu_0)}\right]^{\gamma_0/\beta_0}
=
\left[\frac{g^2(\mu)}{g^2(\mu_0)}\right]^{\gamma_0/(2\beta_0)}.
$$

For QCD with quarks in the fundamental representation,

$$
\gamma_0=6C_F,
\qquad
C_F=\frac{N_c^2-1}{2N_c},
$$

in the $g^2/(16\pi^2)$ convention. Since $g(\mu)$ decreases in the ultraviolet, the short-distance quark mass decreases as well.

## Additive scalar mass sensitivity

Scalar masses are qualitatively more delicate. In a hard-cutoff language, a scalar self-energy may generate terms schematically of the form

$$
\delta m^2\sim c_1\lambda\Lambda^2+c_2\lambda m^2\log\frac{\Lambda^2}{\mu^2}+\cdots.
$$

The logarithmic term is the kind of scale dependence most directly captured by beta functions. The power-sensitive term says something else: the scalar mass is sensitive to short-distance physics unless a symmetry or dynamical mechanism protects it.

Dimensional regularization with minimal subtraction often hides power divergences. In that language the scalar mass may satisfy a clean multiplicative equation such as

$$
\mu\frac{d m^2}{d\mu}=\eta_{m^2}(\lambda)m^2.
$$

That does not erase threshold sensitivity. If a heavy particle of mass $M$ couples to the scalar, integrating it out can generate a finite matching correction of the schematic form

$$
\Delta m^2\sim \frac{\lambda_{\text{mix}}}{16\pi^2}M^2.
$$

This statement is independent of whether one chooses a regulator that displays quadratic divergences. The Wilsonian issue is the sensitivity of a relevant coupling to heavy physics.

## Pole masses and running masses

A pole mass is defined by the location of a pole of an exact propagator. For a scalar field with renormalized self-energy $\Pi_R$, write schematically

$$
G(p)=\frac{i}{p^2-m^2(\mu)-\Pi_R(p^2,\mu)+i\epsilon}.
$$

The pole mass satisfies

$$
m_{\text{pole}}^2-m^2(\mu)-\Pi_R(m_{\text{pole}}^2,\mu)=0,
$$

assuming an isolated stable particle pole exists.

Because the full propagator is independent of the arbitrary scale $\mu$, the pole position is scale independent in the exact theory. At finite order, residual $\mu$ dependence remains and becomes one diagnostic of missing higher orders.

A running mass $m(\mu)$ is usually more convenient for short-distance calculations because it avoids large logarithms. A pole mass is closer to a direct particle interpretation when the particle is stable and isolated. In confining theories, quark pole masses are not physical observables, and short-distance mass definitions are used instead.

| Object | Meaning | Typical use |
|---|---|---|
| $m_0$ | bare mass in a regulated theory | defines the regulated starting point |
| $m(\mu)$ | running renormalized mass | organizes perturbation theory and RG evolution |
| $m_{\text{pole}}$ | pole position of an exact propagator | physical particle mass when a clean pole exists |
| $M$ | heavy threshold or matching scale | separates EFT descriptions |
| $\xi^{-1}$ | inverse correlation length | statistical and critical systems |

## Mass-independent and mass-dependent schemes

In a mass-independent scheme, such as MS or $\overline{\mathrm{MS}}$, renormalization constants are defined by subtracting poles in dimensional regularization and do not depend explicitly on mass ratios. This makes beta functions simple and universal-looking, but it also means heavy particles do not automatically disappear from beta functions just because $\mu$ drops below their mass.

In a mass-dependent scheme, the subtraction conditions can depend on physical momenta and masses. Decoupling can be more automatic, but formulas are often less compact.

Neither style is morally superior. A mass-independent scheme is excellent for high-order calculations and EFT matching. A mass-dependent scheme can make physical thresholds more visible. The final observable is independent of this bookkeeping when matching and running are done consistently.

## Running masses in the Callan–Symanzik equation

For a renormalized Green function, masses enter the Callan–Symanzik equation as running parameters. A schematic scalar form is

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+\beta_{m^2}\frac{\partial}{\partial m^2}
+n\gamma_\phi
\right)G_R^{(n)}=0.
$$

For a fermion mass with $\beta_m=-\gamma_m m$,

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
-\gamma_m m\frac{\partial}{\partial m}
+n\gamma_\phi
\right)G_R^{(n)}=0.
$$

The equation expresses a simple fact: explicit logarithms of $\mu$ in the Green function are compensated by the implicit $\mu$ dependence of couplings, masses, and field normalizations.

## Critical phenomena interpretation

In statistical field theory, a mass parameter often measures the distance from a critical point. For the Euclidean Landau–Ginzburg action

$$
S_E=\int d^d x\left[\frac12(\nabla\phi)^2+\frac12 r\phi^2+\frac{u}{4!}\phi^4\right],
$$

the parameter $r$ is a mass squared. The critical point occurs at a tuned value $r=r_c$, not necessarily at the naive microscopic value $r=0$.

Near criticality, the correlation length behaves as

$$
\xi\sim |t|^{-\nu},
$$

where $t$ is a reduced temperature-like variable. The RG eigenvalue $y_t$ of the relevant direction is

$$
y_t=\frac{1}{\nu}.
$$

This is the statistical-physics version of mass running. The mass-like deformation grows in the IR and eventually cuts off scale-invariant behavior at the correlation length.

## Thresholds and decoupling

A mass can also mark a threshold where the degrees of freedom change. Suppose a heavy field has mass $M$. At energies $Q\ll M$, it is usually better to integrate it out and use an EFT with only light fields.

The logic is

$$
\text{full theory above }M
\quad\longrightarrow\quad
\text{match near }\mu\sim M
\quad\longrightarrow\quad
\text{run in the EFT below }M.
$$

The running mass of the heavy field and the matching scale are related but distinct. Choosing $\mu\sim M$ avoids large logarithms in the matching calculation. The EFT below $M$ no longer contains the heavy particle as a dynamical field, though its effects remain in Wilson coefficients.

In mass-independent schemes, this matching step is not optional bookkeeping. It is how the theory knows which particles are active at which scale.

## RG-invariant masses

Sometimes it is useful to define an RG-invariant mass parameter. For a multiplicatively running mass,

$$
\mu\frac{dm}{d\mu}=-\gamma_m(g)m,
\qquad
\mu\frac{dg}{d\mu}=\beta(g),
$$

define

$$
\widehat m
=m(\mu)
\exp\left[\int^{g(\mu)}dg\,\frac{\gamma_m(g)}{\beta(g)}\right].
$$

Then $\widehat m$ is independent of $\mu$, up to the convention used for the lower limit and normalization of the integral. Such invariant combinations are useful because they separate the arbitrary running coordinate from a scale-independent label of the RG trajectory.

One should not confuse an RG-invariant mass parameter with a pole mass. It is invariant under RG flow, but it remains a scheme-defined object unless tied to a physical observable.

## Common pitfalls

**Thinking that a running mass is directly measured at every scale.** A running mass is inferred by matching calculations to observables. It is not itself an observable.

**Confusing $m(\mu)$ with $m_{\text{pole}}$.** The running mass changes with $\mu$. A pole mass, when well defined, is a scale-independent property of the exact propagator.

**Forgetting additive scalar mass sensitivity.** Multiplicative MS running does not erase physical sensitivity to heavy thresholds.

**Decoupling heavy particles just by lowering $\mu$.** In mass-independent schemes, decoupling is implemented through matching.

**Comparing masses across schemes without conversion.** $\overline{\mathrm{MS}}$ masses, on-shell masses, threshold masses, lattice masses, and EFT parameters are different coordinates.

## Relations to other pages

[Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/) explains the operator-side scaling data that control mass running. [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/) treats dimensionless couplings; this page treats relevant mass parameters. [RG-Improved Perturbation Theory](/renormalization-rg-eft/renormalization-group-equations/rg-improved-perturbation-theory/) shows how running masses are inserted into improved calculations.

[Mass and Coupling Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/mass-and-coupling-renormalization/) explains how mass counterterms arise in renormalized perturbation theory. [Regulator Dependence](/renormalization-rg-eft/why-renormalization/regulator-dependence/) explains why a displayed cutoff dependence is not the same thing as a physical infinity. The EFT threshold logic is developed later in matching, running, and decoupling pages.

## Research status

The distinction among bare, running, and physical masses is settled. One-loop and higher-loop mass anomalous dimensions are standard tools in perturbative QFT, QCD, EFT, and critical phenomena.

What remains technically active is precision and interpretation in difficult regimes: quark-mass schemes, threshold masses, unstable-particle masses, lattice-to-continuum conversion, nonperturbative mass renormalization, finite-volume mass gaps, and naturalness of scalar relevant operators.

## Exercises

### Exercise 1: Solve a one-loop running mass

Let

$$
\mu\frac{dg}{d\mu}=-\beta_0\frac{g^3}{16\pi^2},
\qquad
\mu\frac{dm}{d\mu}=-\gamma_0\frac{g^2}{16\pi^2}m,
$$

with $\beta_0>0$. Derive $m(\mu)/m(\mu_0)$ in terms of $g(\mu)/g(\mu_0)$.

<details><summary><strong>Solution</strong></summary>

Divide the two equations:

$$
\frac{d\log m}{dg}
=
\frac{-\gamma_0 g^2/(16\pi^2)}{-\beta_0 g^3/(16\pi^2)}
=\frac{\gamma_0}{\beta_0}\frac{1}{g}.
$$

Integrating gives

$$
\log\frac{m(\mu)}{m(\mu_0)}
=\frac{\gamma_0}{\beta_0}
\log\frac{g(\mu)}{g(\mu_0)}.
$$

Therefore

$$
\frac{m(\mu)}{m(\mu_0)}
=
\left[\frac{g(\mu)}{g(\mu_0)}\right]^{\gamma_0/\beta_0}.
$$

</details>

### Exercise 2: Dimensionless relevance

Assume $\mu dm/d\mu=-\gamma_m m$. Show that $\tilde m=m/\mu$ obeys $\mu d\tilde m/d\mu=-(1+\gamma_m)\tilde m$.

<details><summary><strong>Solution</strong></summary>

Differentiate $\tilde m=m\mu^{-1}$:

$$
\mu\frac{d\tilde m}{d\mu}
=
\mu\frac{d}{d\mu}(m\mu^{-1})
=\mu^{-1}\mu\frac{dm}{d\mu}-m\mu^{-1}.
$$

Using $\mu dm/d\mu=-\gamma_m m$ gives

$$
\mu\frac{d\tilde m}{d\mu}
=-\gamma_m\tilde m-\tilde m
=-(1+\gamma_m)\tilde m.
$$

</details>

### Exercise 3: Why pole masses do not run

Suppose the exact scalar propagator has a pole at $p^2=m_{\text{pole}}^2$. Explain why $m_{\text{pole}}$ is independent of $\mu$, while $m(\mu)$ is not.

<details><summary><strong>Solution</strong></summary>

The pole position is a property of the exact Green function and cannot depend on an arbitrary subtraction scale. The running mass $m(\mu)$ is a scheme-defined coordinate chosen to parametrize the same exact Green function at scale $\mu$. Changing $\mu$ changes this coordinate, and the explicit $\mu$ dependence in loop corrections changes in the opposite way. In the exact result the pole position is unchanged.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations" and "Renormalization and Symmetry."
- Mark Srednicki, *Quantum Field Theory*, especially sections on renormalization schemes, the renormalization group, effective field theory, and beta functions in Yukawa and gauge theories.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters on mass renormalization, renormalized perturbation theory, the renormalization group, and QCD running.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for RG methods, masses, and scheme issues.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for relevant perturbations, mass renormalization, and critical exponents.
- C. P. Burgess, *Introduction to Effective Field Theory*, for decoupling, matching, and scale hierarchies.

## Version history

- 2026-06-17: First polished draft. Introduced running masses as relevant couplings, fixed sign conventions for $\gamma_m$, distinguished running and pole masses, and connected scalar mass sensitivity to thresholds and naturalness.
