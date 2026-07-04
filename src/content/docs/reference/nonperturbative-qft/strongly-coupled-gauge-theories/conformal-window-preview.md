---
title: "Conformal Window Preview"
description: "Explains how asymptotically free gauge theories with enough massless matter can flow to infrared conformal fixed points instead of confining."
sidebar:
  label: "Conformal Window Preview"
  order: 6
level: Advanced
status: "Polished draft"
source: "Caswell; Banks–Zaks; Shifman; Schwartz; Poland–Rychkov–Vichi; lattice conformal-window reviews."
topics:
  - conformal window
  - Banks–Zaks fixed point
  - infrared fixed points
  - asymptotic freedom
  - strongly coupled gauge theories
  - anomalous dimensions
  - lattice gauge theory
  - conformal bootstrap
canonicalTopics:
  - nonperturbative-qft
  - strongly-coupled-gauge-theories
  - conformal-window
  - banks-zaks-fixed-point
  - infrared-fixed-points
  - gauge-theory-phases
researchStatus:
  established:
    - "Asymptotically free non-Abelian gauge theories with sufficiently many massless fermions can have perturbatively controlled infrared fixed points near the upper edge of asymptotic freedom."
  active:
    - "The lower edge of the nonsupersymmetric conformal window, especially for strongly coupled theories relevant to lattice studies and model building, is an active research problem."
---

## Summary

The **conformal window** is the range of matter content for which a non-Abelian gauge theory is asymptotically free in the ultraviolet but flows in the infrared to an interacting conformal field theory rather than to a confining, chirally broken, gapped theory. It is one of the cleanest ways to see that strong gauge dynamics is not synonymous with confinement.

For a vectorlike gauge theory with gauge group $G$ and $N_f$ massless Dirac fermions in a representation $R$, the perturbative beta function begins

$$
\mu\frac{dg}{d\mu}
=-\frac{b_0}{16\pi^2}g^3
-\frac{b_1}{(16\pi^2)^2}g^5+
O(g^7),
$$

where

$$
b_0=\frac{11}{3}C_A-\frac{4}{3}T_R N_f.
$$

Asymptotic freedom requires $b_0>0$. Just below the value where $b_0$ changes sign, $b_0$ is small and the two-loop beta function can have a weakly coupled infrared zero. This is the **Caswell–Banks–Zaks fixed point**. Deeper in the window, the fixed point may become strongly coupled. Below the lower edge of the window, the theory is expected to confine and often to break chiral symmetry instead of remaining conformal.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A schematic conformal-window map as the number of flavors is increased: confining and chirally broken dynamics at small flavor number, walking near the lower edge, an infrared conformal window, a weak Banks–Zaks region near the upper edge, and loss of asymptotic freedom above it.](/figures/nonperturbative-qft/conformal-window-rg-map.svg)

<figcaption>

A schematic conformal window for an asymptotically free gauge theory with variable matter content. Near the upper edge the fixed point is weak and perturbative. Near the lower edge it is strongly coupled or disappears, so lattice, bootstrap, anomaly, and effective-field-theory diagnostics become essential.

</figcaption>
</figure>

This page is a preview because the full theory of conformal field theory belongs in the CFT and Bootstrap volume. The purpose here is narrower: explain how conformal behavior appears as an infrared phase of gauge theory and how it differs from ordinary QCD-like confinement.

## Prerequisites

Read [QCD as a Strongly Coupled QFT](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-as-strongly-coupled-qft/), [Chiral Symmetry Breaking](/nonperturbative-qft/strongly-coupled-gauge-theories/chiral-symmetry-breaking/), [Hadron Spectrum](/nonperturbative-qft/strongly-coupled-gauge-theories/hadron-spectrum/), [What Is Confinement?](/nonperturbative-qft/confinement-screening-mass-gap/what-is-confinement/), [Mass Gap in Gauge Theory](/nonperturbative-qft/confinement-screening-mass-gap/mass-gap/), and [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) before this page.

For methods, it helps to know [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/), [Spectral Density](/nonperturbative-qft/order-parameters-diagnostics/spectral-density/), [Condensates](/nonperturbative-qft/order-parameters-diagnostics/condensates/), and the Wilsonian picture of RG flows. This page uses standard beta-function notation and assumes familiarity with anomalous dimensions.

## Core idea

A gauge theory can be asymptotically free and still not become QCD-like in the infrared. The UV coupling may start small, grow as the energy decreases, and then approach a finite fixed value:

$$
\lim_{\mu\to0}g(\mu)=g_*.
$$

If the fixed point is genuine, the long-distance theory is scale invariant, and in ordinary relativistic unitary examples one expects conformal invariance. There is no confinement scale, no isolated massive hadron spectrum in the massless theory, and no chiral condensate of the QCD type. Instead, the infrared data are CFT data: operator dimensions, OPE coefficients, conserved currents, anomalies, and correlation functions with power-law behavior.

This is a sharp contrast with QCD with a small number of light flavors. There the coupling grows until the theory generates a scale $\Lambda_{\rm QCD}$, confines color, breaks approximate chiral symmetry, and produces massive color-singlet states plus pseudo-Goldstone bosons. In an infrared-conformal gauge theory, the massless limit has no such scale. A scale appears only if one deforms the CFT, for example by adding fermion masses or putting the theory in a finite box.

The phrase “window” emphasizes that the phenomenon depends on matter content. Increasing $N_f$ screens gauge interactions. With too few fermions, confinement and chiral symmetry breaking win. With too many fermions, asymptotic freedom is lost. In between there may be a range where the UV is asymptotically free and the IR is conformal.

## Setup and conventions

Consider a four-dimensional vectorlike gauge theory with compact simple gauge group $G$ and $N_f$ massless Dirac fermions in representation $R$. The group-theory factors are defined by

$$
\operatorname{tr}_R(T^aT^b)=T_R\delta^{ab},
\qquad
T^aT^a=C_R\mathbf 1,
\qquad
f^{acd}f^{bcd}=C_A\delta^{ab}.
$$

For $SU(N_c)$ with fermions in the fundamental representation,

$$
C_A=N_c,
\qquad
T_F=\frac12,
\qquad
C_F=\frac{N_c^2-1}{2N_c}.
$$

In that case asymptotic freedom requires

$$
N_f<\frac{11}{2}N_c.
$$

For $SU(3)$ fundamentals this upper bound is $N_f<16.5$, so integer $N_f\le16$ can be asymptotically free. This upper bound is perturbative and exact at one loop. The lower edge of the conformal window is not known from perturbation theory alone.

This page uses the beta-function convention

$$
\beta(g)\equiv \mu\frac{dg}{d\mu}.
$$

With $b_0>0$, the negative sign in $\beta(g)$ means the coupling decreases toward the ultraviolet and increases toward the infrared until other terms or nonperturbative effects intervene.

## The upper edge and the Banks–Zaks fixed point

The two-loop coefficient for $N_f$ Dirac fermions in representation $R$ is

$$
b_1=\frac{34}{3}C_A^2
-\frac{20}{3}C_A T_RN_f
-4C_R T_RN_f.
$$

Near the loss of asymptotic freedom, $b_0$ is positive but small. If $b_1<0$, the two-loop beta function has a zero at

$$
g_*^2=-16\pi^2\frac{b_0}{b_1}+O(b_0^2).
$$

Because $b_0$ is small near the upper edge, $g_*$ is small. This is the controlled Banks–Zaks regime. The fixed point is perturbative, and one can compute anomalous dimensions and critical exponents as series in the small distance from the upper edge.

For example, a gauge-invariant fermion bilinear

$$
\Phi^i{}_{\bar j}\sim \bar\psi_{L\bar j}\psi_R^i
$$

has scaling dimension

$$
\Delta_\Phi=3-\gamma_m(g_*),
$$

where $\gamma_m$ is the mass anomalous dimension in the convention in which the mass deformation has RG eigenvalue $1+\gamma_m$. Near the upper edge, $\gamma_m$ is small. Farther down the window, $\gamma_m$ can be sizable, but then perturbation theory is no longer enough.

The fixed point value of a coupling depends on the definition of the coupling. The existence of a fixed point, the scaling dimensions of gauge-invariant operators, and critical exponents are physical. This distinction matters: drawing a beta function is useful, but the CFT data are the invariant information.

## The lower edge

The lower edge is the hard part. As $N_f$ is decreased, the would-be fixed point moves to stronger coupling. Eventually one of several things can happen:

| Possibility | Physical description | Consequence |
|---|---|---|
| Fixed point persists | The infrared remains a CFT. | The theory stays inside the conformal window. |
| Chiral symmetry breaks first | A condensate forms before the flow reaches the fixed point. | The infrared is QCD-like rather than conformal. |
| Fixed points annihilate | An IR and UV fixed point merge and disappear. | The nearby confining theory may walk. |
| Relevant deformation appears | An operator becomes relevant and destabilizes the fixed point. | Additional tuning is required to reach the CFT. |

The actual mechanism is theory-dependent. In nonsupersymmetric four-dimensional gauge theories, the lower edge is not known exactly in general. It is studied using lattice simulations, perturbative expansions where available, large-$N_f$ expansions, Schwinger–Dyson estimates, conformal bootstrap constraints, anomaly arguments, and effective field theory.

It is useful to separate two questions:

1. **Does an infrared fixed point exist?** This is a statement about the massless continuum theory.
2. **Can a particular regulator or lattice discretization reach it without extra tuning?** This depends on which symmetries the regulator preserves and which symmetry-breaking operators it allows.

A fixed point can be present in theory space but difficult to see numerically if the lattice action breaks part of the symmetry and introduces relevant or dangerously irrelevant deformations.

## What the infrared CFT looks like

Inside the conformal window, the massless theory has no isolated massive particles. Correlators of local gauge-invariant operators decay as powers:

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
\sim \frac{1}{|x|^{2\Delta_{\mathcal O}}}.
$$

The stress tensor is conserved and has dimension $d=4$. Global flavor currents are conserved and have dimension $3$. Gauge-invariant scalar operators have dimensions constrained by unitarity and dynamics. The fermion fields themselves are not gauge-invariant observables, so the CFT data of primary interest are gauge-invariant composites, line operators, currents, and defect operators.

For an $SU(N_c)$ theory with $N_f$ massless Dirac fundamentals, the classical flavor symmetry before anomalies is roughly

$$
SU(N_f)_L\times SU(N_f)_R\times U(1)_V,
$$

with the axial $U(1)_A$ broken by the anomaly. If the theory flows to an IR CFT in the conformal window, the non-anomalous chiral flavor symmetry is not spontaneously broken. Operators must organize into representations of the unbroken flavor symmetry. This is one of the places where conformal bootstrap constraints can enter: crossing, unitarity, and global symmetry restrict the allowed operator spectrum.

## Mass deformation and hyperscaling

The massless conformal theory has no mass gap. A common way to probe it is to add a small fermion mass

$$
\delta\mathcal L=m\bar\psi\psi.
$$

At the fixed point, the mass parameter has RG exponent

$$
y_m=1+\gamma_*,
$$

where $\gamma_*$ is the mass anomalous dimension at the IR fixed point. The induced mass scale behaves as

$$
M\sim m^{1/(1+\gamma_*)}.
$$

Consequently, many spectral quantities in a mass-deformed conformal theory obey hyperscaling:

$$
M_H\propto m^{1/(1+\gamma_*)},
\qquad
F_H\propto m^{1/(1+\gamma_*)},
$$

up to finite-volume effects, subleading corrections, and channel-dependent amplitudes. This is very different from ordinary chirally broken QCD, where pseudo-Goldstone masses obey

$$
m_\pi^2\propto m_q
$$

at leading order while many other hadron masses remain finite in the chiral limit.

Hyperscaling is a diagnostic, not a magic verdict. A finite box, a finite lattice spacing, a not-small-enough fermion mass, or a walking but ultimately confining theory can mimic parts of conformal scaling over a limited range.

## Diagnostics for the conformal window

No single observable settles the conformal-window question in a difficult strongly coupled theory. Useful diagnostics include:

| Diagnostic | Conformal expectation | QCD-like expectation |
|---|---|---|
| Running coupling | Approaches a finite IR fixed point. | Grows until confinement or chiral breaking cuts off the flow. |
| Gauge-invariant correlators | Power-law decay in the massless infinite-volume limit. | Exponential decay with a mass gap, plus Goldstone behavior if chiral symmetry breaks. |
| Chiral condensate | No spontaneous chiral condensate in the massless CFT. | Nonzero chiral condensate in the chiral limit. |
| Spectrum with fermion mass | Hyperscaling with $m^{1/(1+\gamma_*)}$. | Pions and non-Goldstone hadrons scale differently. |
| Finite-size scaling | Controlled by CFT dimensions. | Controlled by massive finite-volume effects and chiral dynamics. |
| Operator dimensions | Constrained CFT data. | Not the natural language of the massive IR theory. |

The hard cases are near the lower edge. The beta function may be small over a wide range, the mass anomalous dimension may be large, finite-volume effects may be severe, and distinguishing true conformality from walking can require a heroic continuum, infinite-volume, and chiral analysis. The lab coat gets sweaty here.

## Relation to walking

A theory just below the lower edge of the conformal window may have a beta function that is small over a long range of scales. The coupling runs slowly, the dynamics looks approximately scale invariant for a while, and only at much longer distances does confinement or chiral symmetry breaking set in. This is called **walking**.

A useful cartoon is:

$$
\text{inside window:}\quad g(\mu)\to g_*,
$$

while

$$
\text{just below window:}\quad g(\mu)\text{ lingers near }g_*\text{ but eventually exits.}
$$

The walking page explains this distinction in detail. The conformal window is about exact infrared fixed points. Walking is about approximate scale invariance over a large but finite range.

## Common pitfalls

**Equating strong coupling with confinement.** Inside the conformal window, the IR fixed point can be strongly coupled but not confining.

**Treating the two-loop fixed point as the whole conformal window.** The two-loop Banks–Zaks fixed point controls only the upper edge. The lower edge is nonperturbative in many theories.

**Confusing a fixed point coupling with physical data.** The value $g_*$ is scheme-dependent. Operator dimensions, anomaly coefficients, and critical exponents are physical.

**Forgetting masslessness.** The conformal window is a statement about the massless theory. Adding fermion masses creates a scale and a gapped spectrum.

**Overinterpreting finite lattice data.** A finite box and nonzero fermion mass can make conformal, walking, and confining theories look deceptively similar over limited ranges.

**Assuming QCD lies close to the conformal window.** Real-world QCD with a few light flavors is strongly coupled, confining, and chirally broken. Near-conformal QCD-like theories are obtained by changing matter content, not by staring harder at ordinary low-energy QCD.

## Research status

The upper edge of the conformal window is textbook-standard: near the loss of asymptotic freedom, perturbation theory gives a controlled Banks–Zaks fixed point. The existence of infrared conformality in many gauge theories is also established in supersymmetric examples by stronger exact methods, though those belong mainly in the supersymmetry and duality parts of the site.

The lower edge of the nonsupersymmetric conformal window is active research. Lattice studies, conformal bootstrap bounds, large-$N_f$ methods, perturbative resummations, anomaly constraints, and effective theories all contribute partial information. The most trustworthy attitude is pluralistic: identify the observable, state the regulator and limits, and avoid turning a schematic phase diagram into a theorem.

## Exercises

### Exercise 1: Upper edge of asymptotic freedom

For $SU(N_c)$ gauge theory with $N_f$ Dirac fermions in the fundamental representation, use

$$
b_0=\frac{11}{3}N_c-\frac{2}{3}N_f
$$

to find the condition for asymptotic freedom.

<details><summary><strong>Solution</strong></summary>

Asymptotic freedom requires $b_0>0$, so

$$
\frac{11}{3}N_c-\frac{2}{3}N_f>0.
$$

Multiplying by $3$ gives

$$
11N_c-2N_f>0,
$$

or

$$
N_f<\frac{11}{2}N_c.
$$

For $SU(3)$ this is $N_f<16.5$, so integer $N_f\le16$ is allowed by one-loop asymptotic freedom.

</details>

### Exercise 2: Two-loop fixed point

With

$$
\beta(g)=-\frac{b_0}{16\pi^2}g^3
-\frac{b_1}{(16\pi^2)^2}g^5,
$$

show that if $b_0>0$ and $b_1<0$, there is a nonzero fixed point at

$$
g_*^2=-16\pi^2\frac{b_0}{b_1}.
$$

<details><summary><strong>Solution</strong></summary>

Set $\beta(g)=0$. Besides the Gaussian fixed point $g=0$, the nonzero solution satisfies

$$
\frac{b_0}{16\pi^2}+\frac{b_1}{(16\pi^2)^2}g^2=0.
$$

Multiplying by $(16\pi^2)^2$ gives

$$
16\pi^2 b_0+b_1g^2=0,
$$

so

$$
g_*^2=-16\pi^2\frac{b_0}{b_1}.
$$

For this to be positive with $b_0>0$, one needs $b_1<0$.

</details>

### Exercise 3: Hyperscaling from an anomalous mass dimension

Suppose the only relevant deformation of an IR CFT is a fermion mass $m$ with RG exponent $y_m=1+\gamma_*$. Show that the induced mass scale obeys

$$
M\sim m^{1/y_m}.
$$

<details><summary><strong>Solution</strong></summary>

Under an RG rescaling by a factor $s$, the mass parameter transforms as

$$
m(s)=s^{y_m}m.
$$

The RG flow leaves the vicinity of the fixed point when the dimensionless mass becomes order one. If the UV reference scale is set to one, this occurs when

$$
s^{y_m}m\sim1,
$$

so

$$
s\sim m^{-1/y_m}.
$$

The physical infrared mass scale is the inverse length scale, hence

$$
M\sim s^{-1}\sim m^{1/y_m}=m^{1/(1+\gamma_*)}.
$$

</details>

## Relations to other pages

This page follows [QCD String Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-string-preview/) because it shows how strong gauge dynamics can depart from the confining-string picture. Continue to [Walking Gauge Theories Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/walking-gauge-theories-preview/) for the near-conformal but ultimately nonconformal case just below the lower edge.

For the confining side of the phase diagram, see [What Is Confinement?](/nonperturbative-qft/confinement-screening-mass-gap/what-is-confinement/), [Chiral Symmetry Breaking](/nonperturbative-qft/strongly-coupled-gauge-theories/chiral-symmetry-breaking/), and [Mass Gap in Gauge Theory](/nonperturbative-qft/confinement-screening-mass-gap/mass-gap/). For CFT methods, continue later to the CFT and Bootstrap volume. For lattice diagnostics, continue later to Lattice Field Theory.

## References

### Standard first pass

- T. Banks and A. Zaks, “On the Phase Structure of Vector-Like Gauge Theories with Massless Fermions,” *Nuclear Physics B* **196** (1982).
- W. E. Caswell, “Asymptotic Behavior of Non-Abelian Gauge Theories to Two-Loop Order,” *Physical Review Letters* **33** (1974).
- M. Schwartz, *Quantum Field Theory and the Standard Model*, especially the discussion of Banks–Zaks behavior and Wilsonian RG.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapters on phases of gauge theories, anomalies, confinement, and lower-dimensional models.

### Deeper references

- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), especially the discussion of constraints on the QCD conformal window.
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” for recent bootstrap developments involving critical gauge theories.
- A. Hasenfratz, T. DeGrand, A. Patella, B. Svetitsky, A. Nogradi, and collaborators, for lattice studies and reviews of near-conformal gauge theories.
- T. A. Ryttov, R. Shrock, F. Sannino, and collaborators, for perturbative, all-orders-beta-function, and phase-diagram approaches to conformal windows.
- M. A. Luty, T. Okui, L. Vecchi, and related work, for conformal technicolor and phenomenological applications of strongly coupled CFTs.

## Version history

- **2026-06-27:** Linked the new Strongly Coupled Chiral Gauge Theories page.
- **2026-06-27:** Initial polished draft, added after QCD String Preview in the Strongly Coupled Gauge Theories chapter.
