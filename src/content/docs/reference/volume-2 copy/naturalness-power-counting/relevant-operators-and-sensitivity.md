---
title: "Relevant Operators and Sensitivity"
description: "A Wilsonian explanation of why relevant operators amplify short-distance data, why they control tuning to criticality, and when their sensitivity becomes a naturalness problem."
sidebar:
  label: "Relevant Operators and Sensitivity"
  order: 7
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Coleman 1985, dilatations and renormalization lectures; Weinberg Vol. II, RG methods and critical phenomena; Srednicki 2007, §§28–29; Schwartz 2014, chs. 21–23; Zinn-Justin 2021, RG and critical-phenomena chapters; Burgess 2020, chs. 2–3."
topics:
  - relevant operators
  - sensitivity
  - naturalness
  - critical surfaces
  - Wilsonian RG
canonicalTopics:
  - relevant-operator
  - rg-sensitivity
  - naturalness
researchStatus:
  established:
    - "Relevant perturbations are the RG directions that grow under coarse graining; they control departures from fixed points, correlation lengths, and many naturalness questions."
  active:
    - "Which relevant parameters in fundamental physics require dynamical explanations, environmental explanations, or no explanation remains an active interpretive question."
---

## Summary

A **relevant operator** is a local perturbation that grows as the theory flows away from a fixed point toward longer distances. If an operator $\mathcal O_i$ has scaling dimension $\Delta_i<d$ at a $d$-dimensional fixed point, then its coupling has positive RG eigenvalue

$$
y_i=d-\Delta_i>0.
$$

Using Wilsonian IR time

$$
\ell=\log\frac{\Lambda_0}{\Lambda},
$$

the linearized flow is

$$
\frac{d\widetilde g_i}{d\ell}=y_i\widetilde g_i+\cdots,
\qquad y_i>0,
$$

so small departures from the critical surface are amplified:

$$
\widetilde g_i(\ell)\approx e^{y_i\ell}\widetilde g_i(0).
$$

This amplification is why relevant operators are powerful. They decide which phase a system enters, which mass gap is generated, which correlation length is obtained, and which low-energy scales are sensitive to short-distance input.

It is also why relevant operators are dangerous. If a relevant operator is allowed by all exact symmetries, heavy physics can feed it with positive powers of the heavy scale. Then obtaining a much smaller low-energy scale may require tuning or a protective mechanism.

:::note[The practical slogan]
Relevant operators are the knobs that must be adjusted to stay near a fixed point. Naturalness problems arise when the required adjustment is extremely precise and no symmetry or dynamics explains it.
:::

## Prerequisites

You should know [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/), [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/), [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [Radiative Stability](/renormalization-rg-eft/naturalness-power-counting/radiative-stability/), and [Fine-Tuning](/renormalization-rg-eft/naturalness-power-counting/fine-tuning/).

Readers mainly interested in particle physics can read this page as the Wilsonian explanation of why scalar mass terms are special. Readers mainly interested in statistical physics can read it as the explanation of why tuning the temperature near $T_c$ produces a long correlation length.

## Core idea

The relevance of an operator is a statement about scaling near a fixed point. It is not merely dimensional analysis, although dimensional analysis gives the first approximation near a Gaussian fixed point.

Let a theory near a fixed point be perturbed by local operators:

$$
S=S_*+\sum_i g_i\int d^d x\,\mathcal O_i(x).
$$

Define dimensionless couplings by

$$
\widetilde g_i(\Lambda)=\Lambda^{\Delta_i-d}g_i(\Lambda).
$$

Near the fixed point, the linearized Wilsonian flow can be diagonalized into scaling directions:

$$
\frac{d\widetilde g_i}{d\ell}=y_i\widetilde g_i+\cdots,
\qquad
\ell=\log\frac{\Lambda_0}{\Lambda},
\qquad
y_i=d-\Delta_i.
$$

Thus:

| Direction | RG eigenvalue | IR behavior | Meaning |
|---|---:|---|---|
| relevant | $y_i>0$ | grows | pushes the theory away from the fixed point |
| marginal | $y_i=0$ | decided by nonlinear terms | can generate logarithmic flow |
| irrelevant | $y_i<0$ | shrinks | becomes unimportant at long distances |

A relevant coupling is therefore a microscope for UV initial conditions. A tiny change in $\widetilde g_i(\Lambda_0)$ can become an order-one change in the long-distance theory after enough RG time.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 55rem;">

![RG geometry showing a critical surface, a fixed point, relevant perturbations growing under coarse graining, and the narrow initial band required for a long scaling window](/figures/renormalization-rg-eft/relevant-operator-sensitivity-map.svg)

<figcaption>

Relevant operators are transverse coordinates to the critical surface. Under IR coarse graining, irrelevant coordinates are washed out, while a relevant coordinate grows as $u(\ell)=e^{y\ell}u_0$. To see scaling over a long range $\xi/a$, the initial relevant perturbation must satisfy $|u_0|\lesssim(a/\xi)^y$.

</figcaption>
</figure>

## Setup and conventions

This page uses the conventions of [Conventions and Notation](/renormalization-rg-eft/conventions/). In particular:

| Symbol | Meaning |
|---|---|
| $d$ | spacetime dimension for relativistic QFT, or Euclidean dimension in statistical field theory |
| $\Lambda$ | Wilsonian cutoff or coarse-graining scale |
| $\Lambda_0$ | microscopic or UV cutoff scale |
| $\ell$ | IR RG time, $\ell=\log(\Lambda_0/\Lambda)$ |
| $Q$ | physical low-energy scale |
| $a$ | microscopic length scale, often $a\sim\Lambda_0^{-1}$ |
| $\xi$ | correlation length |
| $\Delta_i$ | scaling dimension of $\mathcal O_i$ at a fixed point |
| $y_i$ | RG eigenvalue $d-\Delta_i$ |

The sign convention is important. In the Wilsonian convention used here, $\ell$ increases toward the infrared. Therefore a relevant coupling grows for $y_i>0$. In renormalized perturbation theory one often uses $t=\log\mu$, which increases toward the ultraviolet, so the same linearized statement may appear with the opposite sign.

## Relevant directions and the critical surface

A fixed point is not usually isolated as a physically visible phase by itself. It is approached by tuning relevant perturbations to zero. The set of points that flow into the fixed point under coarse graining is the **critical surface**. Its codimension is the number of relevant directions.

If there is one relevant direction $u$, then near the fixed point

$$
u(\ell)=e^{y\ell}u_0.
$$

The flow stays close to the fixed point until $u(\ell)$ becomes order one. Define $\ell_*$ by

$$
e^{y\ell_*}|u_0|\sim 1.
$$

Then

$$
\ell_*\approx \frac{1}{y}\log\frac{1}{|u_0|}.
$$

Since length scales grow like $e^\ell$, the associated correlation length is

$$
\xi\sim a e^{\ell_*}\sim a |u_0|^{-1/y}.
$$

This is the RG origin of power-law sensitivity near a critical point. To obtain $\xi\gg a$, the relevant coordinate $u_0$ must be close to the critical surface:

$$
|u_0|\sim \left(\frac{a}{\xi}\right)^y.
$$

This is not a pathology. It is why critical phenomena are experimentally possible: a laboratory knob, such as the temperature, tunes the system close to the critical surface.

## Why relevant operators create sensitivity

Suppose the low-energy scale $Q_*$ is generated when a dimensionless relevant coupling becomes order one:

$$
\widetilde g(Q_*)\sim 1.
$$

If

$$
\widetilde g(Q)=\left(\frac{\Lambda_0}{Q}\right)^y\widetilde g(\Lambda_0),
$$

then

$$
Q_*\sim \Lambda_0 |\widetilde g(\Lambda_0)|^{1/y}.
$$

Thus a hierarchy

$$
Q_*\ll \Lambda_0
$$

requires

$$
|\widetilde g(\Lambda_0)|\ll 1.
$$

The required smallness is more severe for larger $y$. A mass-squared perturbation at a Gaussian fixed point in four dimensions has $y=2$, so producing a hierarchy of masses $m\ll\Lambda_0$ corresponds to tuning a dimensionless mass-squared coordinate of order

$$
\widetilde m^2(\Lambda_0)\sim \left(\frac{m}{\Lambda_0}\right)^2.
$$

This square is the little villain in many hierarchy discussions.

## Relevant does not mean unnatural

A common mistake is to equate relevant with unnatural. Relevance means that the perturbation grows under RG flow. Naturalness asks whether the small UV coordinate required for a hierarchy is stable and explained.

Here are four different cases:

| Relevant parameter | Why it is relevant | Why it may or may not be natural |
|---|---|---|
| Temperature deviation $t=(T-T_c)/T_c$ | controls departure from a critical point | can be tuned by an external experimental knob |
| Dirac fermion mass $m\bar\psi\psi$ | $m$ has positive mass dimension | small $m$ can be protected by chiral symmetry |
| Generic scalar mass $m^2\phi^2/2$ | $m^2$ has dimension two | unprotected heavy thresholds can generate additive $M^2$ corrections |
| Cosmological constant term | vacuum-energy density has dimension $d$ | all sectors contribute additively; protection is highly nontrivial |

The lesson is:

$$
\text{relevance tells you where sensitivity can enter; protection tells you whether it does.}
$$

## Scalar masses as the canonical example

At the four-dimensional Gaussian fixed point, a real scalar has engineering dimension

$$
[\phi]=1.
$$

The mass operator $\phi^2$ has engineering dimension

$$
[\phi^2]=2,
$$

so its coupling $m^2$ has dimension two:

$$
[m^2]=2.
$$

The corresponding dimensionless coupling is

$$
\widetilde m^2(\Lambda)=\frac{m^2(\Lambda)}{\Lambda^2}.
$$

Ignoring anomalous dimensions near weak coupling,

$$
\frac{d\widetilde m^2}{d\ell}=2\widetilde m^2+\cdots.
$$

If a physical light scalar mass is $m_{\text{phys}}\ll M$, then the dimensionless relevant coordinate near the heavy scale must be roughly

$$
\widetilde m^2(M)\sim \frac{m_{\text{phys}}^2}{M^2}.
$$

But if the scalar couples to heavy physics at mass $M$, locality and symmetry generally allow a threshold correction

$$
\Delta m^2\sim \frac{c}{16\pi^2}M^2.
$$

The problem is not that some regularization produced a quadratic divergence. The problem is that a physical heavy threshold can contribute to the coefficient of a relevant local operator with the size allowed by dimensions and symmetries.

## Fermion masses are different

A Dirac fermion mass is also relevant. In four dimensions,

$$
[\bar\psi\psi]=3,
\qquad [m]=1.
$$

So why is a small fermion mass not the same kind of hierarchy problem?

Because the massless limit has an enhanced chiral symmetry. If the interactions respect this symmetry, a fermion mass cannot be generated unless the symmetry is broken. The mass beta function has the multiplicative form

$$
\mu\frac{dm}{d\mu}=\gamma_m(g)m.
$$

Equivalently, in a Wilsonian language, the surface $m=0$ is invariant under the RG flow when chiral symmetry is exact. The relevant direction exists, but the symmetry can keep the theory on the surface.

This is the prototype of technical naturalness:

$$
\text{a relevant parameter can be small naturally if }p=0\text{ is symmetry-enhanced.}
$$

## Critical phenomena and tuning

In statistical mechanics, relevant operators explain why critical points are special. The Ising universality class has two familiar relevant perturbations:

| Perturbation | Physical meaning | Effect |
|---|---|---|
| temperature-like direction | deviation from $T_c$ | controls correlation length |
| magnetic-field direction | explicit breaking of spin-flip symmetry | selects magnetization |

To observe universal critical behavior, one tunes relevant perturbations small. Irrelevant microscopic details such as lattice shape, many short-distance interactions, and weak higher-order terms flow away. This is why many different systems share the same critical exponents.

The tuning near a critical point is not mysterious because the control parameter is part of the experimental setup. The system is not being asked to sit near criticality without a reason; the experimentalist moves it there.

Particle-physics naturalness questions arise when a relevant parameter appears to be tiny compared with a heavy scale but there is no adjustable environmental knob, symmetry, or dynamics known to explain why.

## Relevant operators and EFT truncation

In an EFT below a heavy scale $M$, the operator expansion is often written

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\text{relevant/marginal}}
+\sum_{\Delta_i>d}\frac{C_i}{M^{\Delta_i-d}}\mathcal O_i.
$$

The irrelevant operators are predictive because their effects are suppressed by powers of $Q/M$:

$$
\delta \mathcal A_i \sim C_i\left(\frac{Q}{M}\right)^{\Delta_i-d}.
$$

Relevant operators are not suppressed in this way. They must be included in the leading EFT, and their coefficients must be specified as input data. This is why EFT predictivity and naturalness are related but distinct:

- EFT can remain predictive even with relevant parameters, as long as they are measured.
- Naturalness asks why those relevant parameters have the measured sizes.

The electron mass, pion mass, Higgs mass parameter, cosmological constant, and relevant deformations of CFTs are all relevant inputs. EFT tells us how to use them. Naturalness asks whether their sizes are stable or surprising.

## Sensitivity to UV boundary conditions

Let $p_{\text{IR}}$ be a low-energy parameter controlled by a UV relevant coordinate $p_{\text{UV}}$. A simple power-law map is

$$
p_{\text{IR}}\sim \left(\frac{\Lambda_0}{Q}\right)^y p_{\text{UV}}.
$$

The logarithmic sensitivity is then

$$
\frac{\partial \log p_{\text{IR}}}{\partial \log p_{\text{UV}}}=1,
$$

which may look harmless. But the absolute allowed range of $p_{\text{UV}}$ needed to obtain a small $p_{\text{IR}}$ is tiny:

$$
|p_{\text{UV}}|\sim \left(\frac{Q}{\Lambda_0}\right)^y |p_{\text{IR}}|.
$$

This illustrates a limitation of simple sensitivity measures. Fine-tuning can appear as a small allowed volume in parameter space, not only as a large logarithmic derivative.

For additive threshold sensitivity,

$$
p_{\text{IR}}=p_{\text{UV}}+\Delta p_{\text{threshold}},
$$

where $|\Delta p_{\text{threshold}}|\gg |p_{\text{IR}}|$. Then small changes in either input can ruin the cancellation. This is the more familiar tuning pattern.

## Power sensitivity versus logarithmic sensitivity

Marginal couplings often run logarithmically:

$$
\mu\frac{dg}{d\mu}=b g^3+\cdots.
$$

Solving at one loop gives behavior involving $\log(\mu/\mu_0)$. Logarithmic sensitivity can generate large hierarchies by dimensional transmutation, but it is structurally different from relevant-operator sensitivity.

For example, asymptotically free gauge theory generates a scale

$$
\Lambda=\mu e^{-1/(2b_0g^2(\mu))}
$$

from a dimensionless coupling. This hierarchy can be exponentially small without tuning a relevant operator. The sensitivity is real, but it is a different mechanism: the scale is generated dynamically by marginal running.

Relevant operators instead carry positive mass dimension and can receive power-sized local contributions from heavy thresholds. This is why scalar masses and vacuum energy are sharper naturalness problems than ordinary logarithmic running couplings.

## Sensitivity and accidental small numbers

Sometimes a relevant parameter is simply small. The question is whether the theory contains an explanation.

A useful diagnostic checklist is:

| Question | If yes | If no |
|---|---|---|
| Does $p=0$ enhance symmetry? | small $p$ may be technically natural | additive corrections may be allowed |
| Is $p$ controlled by a spurion? | corrections carry spurion factors | loops can generate unsuppressed terms |
| Is $p$ an experimentally tunable control variable? | critical tuning can be ordinary | unexplained hierarchy may remain |
| Is $p$ generated by dimensional transmutation? | hierarchy may be dynamical | power sensitivity may still appear elsewhere |
| Are UV parameters correlated by dynamics? | cancellation may be explained | cancellation looks tuned |
| Is the protecting symmetry anomalous or broken by thresholds? | protection may fail | no protection |

This checklist does not prove a model beautiful or ugly. It makes the assumption visible.

## Common pitfalls

**Relevant does not mean bad.** Relevant operators are essential. They label phases, masses, and physical deformations. The problem is not relevance itself; it is unexplained smallness of allowed relevant coefficients.

**Irrelevant does not mean unimportant.** Irrelevant operators can encode leading new-physics effects, dangerously irrelevant variables, symmetry-breaking corrections, or precision observables. They are suppressed at low energy, not worthless.

**A cutoff divergence is not the whole hierarchy problem.** Cutoff regularization makes power sensitivity visible, but physical heavy thresholds can produce the same kind of local relevant-operator sensitivity.

**A small relevant coupling may be protected.** Fermion masses and pseudo-Goldstone masses are relevant but can be stable because $p=0$ is symmetry-enhanced.

**Critical tuning is not automatically mysterious.** In the laboratory, one can tune temperature or pressure. In particle physics, the analogue of the experimental knob may be absent or unknown.

**Do not compare relevance across unrelated fixed points carelessly.** The classification depends on the fixed point and the operator dimensions there. An operator that is relevant near one fixed point may not have the same status near another.

## Relations to other pages

This page translates [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/) into the language of naturalness. [Radiative Stability](/renormalization-rg-eft/naturalness-power-counting/radiative-stability/) explains how loops and thresholds test whether a small relevant parameter stays small. [Fine-Tuning](/renormalization-rg-eft/naturalness-power-counting/fine-tuning/) describes the parameter-space diagnosis when it does not.

[Hierarchy Problem](/renormalization-rg-eft/naturalness-power-counting/hierarchy-problem/) is the main physical application for scalar mass operators. [Symmetry Protection](/renormalization-rg-eft/naturalness-power-counting/symmetry-protection/) explains how exact or approximate symmetries can make relevant directions invariant or spurion-suppressed. [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/) explains a different way to generate low scales without tuning relevant operators.

## Research status

The RG classification of relevant, marginal, and irrelevant directions is established. Its use in critical phenomena, Wilsonian EFT, and renormalized perturbation theory is standard.

The interpretive role of relevant-operator sensitivity remains active in particle physics and cosmology. The Higgs mass parameter, the cosmological constant, axion quality, inflationary scalar potentials, and some dark-sector hierarchies are all discussed using variants of this logic. The formulas on this page are not controversial; the controversy is what kind of explanation nature owes us.

## Exercises

### Exercise 1: Correlation length from a relevant coupling

Suppose a single relevant coupling obeys

$$
\frac{du}{d\ell}=yu,
\qquad y>0.
$$

If the microscopic length is $a$ and the flow leaves the linear regime when $u(\ell_*)\sim 1$, show that

$$
\xi\sim a |u_0|^{-1/y}.
$$

<details><summary><strong>Solution</strong></summary>

The solution is

$$
u(\ell)=e^{y\ell}u_0.
$$

The linear regime ends when

$$
e^{y\ell_*}|u_0|\sim 1,
$$

so

$$
\ell_*\sim \frac{1}{y}\log\frac{1}{|u_0|}.
$$

The physical length scale grows as $a e^\ell$, so

$$
\xi\sim a e^{\ell_*}\sim a |u_0|^{-1/y}.
$$

</details>

### Exercise 2: Required tuning for a scalar hierarchy

A scalar mass-squared parameter has $y=2$ near a Gaussian fixed point. Estimate the required dimensionless UV coordinate $\widetilde m^2(M)$ if the physical scalar mass is $m$ and the heavy scale is $M$.

<details><summary><strong>Solution</strong></summary>

The dimensionless coordinate is

$$
\widetilde m^2(M)=\frac{m^2}{M^2}.
$$

Equivalently, since $y=2$, the hierarchy $m/M$ corresponds to the relevant-coordinate smallness

$$
\widetilde m^2(M)\sim \left(\frac{m}{M}\right)^2.
$$

For example, $m/M=10^{-10}$ requires $\widetilde m^2(M)\sim 10^{-20}$ before considering any additional threshold corrections.

</details>

### Exercise 3: Relevant but protected

Explain why a Dirac fermion mass can be both relevant and technically natural.

<details><summary><strong>Solution</strong></summary>

In four dimensions the operator $\bar\psi\psi$ has engineering dimension three, so its coupling $m$ has dimension one and is relevant. However, the limit $m=0$ has an enhanced chiral symmetry, assuming other interactions respect it. This symmetry forbids an additive mass term. Therefore quantum corrections have the multiplicative form

$$
\mu\frac{dm}{d\mu}=\gamma_m m,
$$

rather than $dm/d\log\mu\sim M$. The mass is relevant, but its smallness can be stable because $m=0$ is an invariant symmetry-enhanced surface.

</details>

### Exercise 4: Critical tuning versus naturalness tuning

Why is tuning a magnet to its critical temperature not usually regarded as a naturalness problem, even though the temperature direction is relevant?

<details><summary><strong>Solution</strong></summary>

The temperature-like perturbation is relevant because it grows under coarse graining and controls the correlation length. Observing a long correlation length therefore requires tuning $T$ close to $T_c$.

This is not mysterious because $T$ is an external control parameter. The experimental setup includes a knob that deliberately moves the system close to the critical surface. A naturalness problem arises when a small relevant parameter appears in a fundamental or low-energy theory without an analogous knob, symmetry, or dynamical explanation.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," "Renormalization and Symmetry," and "Secret Symmetry."
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the chapters on renormalization group methods and critical phenomena.
- Mark Srednicki, *Quantum Field Theory*, especially sections on the renormalization group and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters on renormalizability, nonrenormalizable theories, and the renormalization group.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on RG, fixed points, and critical behavior.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially chapters on scaling, Wilson actions, power counting, and naturalness.

## Version history

- 2026-06-18: First polished draft. Added Wilsonian explanation of relevant-operator sensitivity, critical-surface tuning, scalar threshold sensitivity, and the distinction between relevance and naturalness.
