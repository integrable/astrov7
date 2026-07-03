---
title: "Momentum-Shell RG"
description: "Derives the Wilsonian momentum-shell renormalization step: integrate a thin shell of high momenta, rescale momenta and fields, and read off coupling flows."
sidebar:
  label: "Momentum-Shell RG"
  order: 3
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Kadanoff blocking; Zinn-Justin 2021; Weinberg Vol. II ch. 18; Schwartz ch. 23; Altland and Simons ch. 6; Burgess ch. 3."
topics:
  - momentum-shell RG
  - Wilsonian RG
  - fixed points
  - relevant operators
  - phi-four theory
  - Wilson–Fisher fixed point
canonicalTopics:
  - momentum-shell-rg
  - wilsonian-rg-step
  - shell-integration
  - rescaling
  - wilson-fisher-preview
researchStatus:
  established:
    - "Momentum-shell RG is the standard perturbative Wilsonian calculation that integrates out a thin band of high momenta and rescales to obtain flow equations."
  active:
    - "Beyond simple scalar and statistical systems, shell RG requires care with gauge symmetry, Fermi surfaces, disorder, real time, constraints, and nonperturbative truncations."
---

## Summary

**Momentum-shell RG** is the infinitesimal Wilsonian operation:

$$
\text{integrate a thin shell near }\Lambda
\quad\longrightarrow\quad
\text{rescale momenta and fields}
\quad\longrightarrow\quad
\text{read off new couplings}.
$$

For a scalar field with cutoff $\Lambda$, choose $d\ell>0$ and split momenta into

$$
|p|<\Lambda e^{-d\ell}
\qquad\text{and}\qquad
\Lambda e^{-d\ell}<|p|<\Lambda.
$$

Integrate over the shell, then rescale momenta so that the cutoff is again $\Lambda$. Repeating the step produces a flow of couplings.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Momentum-shell RG cycle: start with cutoff Lambda, integrate a thin shell, rescale momenta and fields, and obtain new couplings at the restored cutoff](/figures/renormalization-rg-eft/momentum-shell-rg-cycle.svg)

<figcaption>

A momentum-shell RG step lowers the cutoff by integrating over a thin shell, then rescales momenta and fields to restore the original cutoff. The theory returns to the same form only at a fixed point; otherwise the couplings move through theory space.

</figcaption>
</figure>

For scalar $\phi^4$ theory, a common sharp-cutoff normalization gives schematic one-loop flows

$$
\frac{d\tilde r}{d\ell}
=2\tilde r+\frac{\tilde u}{2(1+\tilde r)}+\cdots,
\qquad
\frac{d\tilde u}{d\ell}
=(4-d)\tilde u-\frac{3\tilde u^2}{2(1+\tilde r)^2}+\cdots.
$$

The coordinates and coefficients depend on regulator and coupling normalization. The invariant lessons are the existence of fixed points, relevant and irrelevant directions, and universal critical exponents.

## Prerequisites

You should know [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/) and [Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/). This page also uses the operator-dimension ideas from [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/) and the sign conventions from [Conventions and Notation](/renormalization-rg-eft/conventions/).

For comparison with perturbative RG equations, it helps to know [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), and [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/).

## Core idea

Momentum-shell RG makes Wilsonian renormalization differential. Instead of integrating all modes between $\Lambda_0$ and a much lower scale at once, one lowers the cutoff by an infinitesimal factor,

$$
\Lambda\longrightarrow \Lambda'=\Lambda e^{-d\ell}.
$$

There are three steps.

| Step | Operation | Purpose |
|---|---|---|
| 1 | Split fields into slow modes and shell modes | Isolate the variables to remove. |
| 2 | Integrate over the shell | Compute how high modes change the slow-mode action. |
| 3 | Rescale coordinates, momenta, and fields | Restore the cutoff and compare actions in the same theory space. |

The rescaling step is essential. Without it, one merely has an action with a smaller cutoff. With it, one obtains a flow on a fixed space of couplings.

A useful slogan is

$$
\text{shell integration gives quantum corrections; rescaling gives RG meaning.}
$$

## Setup and conventions

Use Euclidean scalar theory with cutoff $\Lambda$:

$$
S_\Lambda[\phi]
=\int d^d x\left[
\frac12(\partial\phi)^2+\frac12 r\phi^2+\frac{u}{4!}\phi^4+\cdots
\right].
$$

Here $r$ has engineering dimension $2$, and $u$ has engineering dimension $4-d$. The dots stand for all higher operators allowed by the symmetries.

Define the IR Wilsonian RG time by

$$
d\ell=-d\log\Lambda>0.
$$

Increasing $\ell$ means flowing toward the infrared. This is the opposite orientation from the common perturbative convention $t=\log\mu$, where increasing $t$ means moving toward the ultraviolet.

The field split is

$$
\phi(p)=\phi_s(p)+\phi_f(p),
$$

where

$$
\phi_s(p): |p|<\Lambda e^{-d\ell},
\qquad
\phi_f(p): \Lambda e^{-d\ell}<|p|<\Lambda.
$$

The subscripts $s$ and $f$ stand for slow and fast. The fast modes are integrated out.

For shell integrals, define

$$
K_d\equiv \frac{S_{d-1}}{(2\pi)^d},
$$

where $S_{d-1}$ is the area of the unit $(d-1)$-sphere. To first order in $d\ell$,

$$
\int_{\mathrm{shell}}\frac{d^d q}{(2\pi)^d}\frac{1}{(q^2+r)^n}
=
K_d\frac{\Lambda^d d\ell}{(\Lambda^2+r)^n}+O(d\ell^2).
$$

## The shell step

Write

$$
S[\phi_s+\phi_f]
=S_s[\phi_s]+S_f[\phi_f]+S_{\mathrm{int}}[\phi_s,\phi_f].
$$

The shell-integrated action is

$$
e^{-S'[\phi_s]}
=e^{-S_s[\phi_s]}
\left\langle e^{-S_{\mathrm{int}}[\phi_s,\phi_f]}\right\rangle_f.
$$

Thus

$$
S'[\phi_s]=S_s[\phi_s]+\Delta S[\phi_s].
$$

The cumulant expansion gives

$$
\Delta S
=\left\langle S_{\mathrm{int}}\right\rangle_f
-\frac12\left(
\left\langle S_{\mathrm{int}}^2\right\rangle_f
-\left\langle S_{\mathrm{int}}\right\rangle_f^2
\right)+\cdots.
$$

The first term gives one-vertex contractions such as tadpoles. The second gives connected two-vertex contractions such as bubbles. The internal lines are restricted to the shell.

## The rescaling step

After shell integration, the remaining modes satisfy

$$
|p|<\Lambda e^{-d\ell}.
$$

To compare the new action to the original one, rescale momenta by

$$
p'=e^{d\ell}p.
$$

Equivalently,

$$
x'=e^{-d\ell}x.
$$

The cutoff in $p'$ is again $\Lambda$.

Now rescale the field so that the kinetic term remains canonically normalized. Near the Gaussian fixed point,

$$
\phi'(x')=e^{(d-2)d\ell/2}\phi_s(x).
$$

A local operator $\mathcal O_i$ with scaling dimension $\Delta_i$ then transforms at tree level as

$$
g_i\int d^d x\,\mathcal O_i(x)
\longrightarrow
g_i e^{(d-\Delta_i)d\ell}\int d^d x'\,\mathcal O_i'(x').
$$

Thus

$$
\frac{dg_i}{d\ell}=(d-\Delta_i)g_i+\cdots,
$$

where the dots denote loop corrections and nonlinear terms.

## One-loop scalar example

Consider the $\mathbb Z_2$-symmetric scalar action

$$
S_\Lambda[\phi]
=\int d^d x\left[
\frac12(\partial\phi)^2+\frac12 r\phi^2+\frac{u}{4!}\phi^4
\right].
$$

The shell tadpole corrects $r$:

$$
\Delta r
=\frac{u}{2}\int_{\mathrm{shell}}\frac{d^d q}{(2\pi)^d}\frac{1}{q^2+r}.
$$

Using the shell integral,

$$
\Delta r
=\frac{u}{2}K_d\frac{\Lambda^d d\ell}{\Lambda^2+r}.
$$

The shell bubble corrects $u$:

$$
\Delta u
=-\frac{3u^2}{2}\int_{\mathrm{shell}}\frac{d^d q}{(2\pi)^d}\frac{1}{(q^2+r)^2},
$$

so

$$
\Delta u
=-\frac{3u^2}{2}K_d\frac{\Lambda^d d\ell}{(\Lambda^2+r)^2}.
$$

These are the quantum corrections from shell integration. Rescaling then supplies the engineering terms.

Define dimensionless couplings

$$
\tilde r\equiv \frac{r}{\Lambda^2},
\qquad
\tilde u\equiv K_d u\Lambda^{d-4}.
$$

To this order, the Wilsonian IR-time flow is

$$
\frac{d\tilde r}{d\ell}
=2\tilde r+\frac{\tilde u}{2(1+\tilde r)}+\cdots,
$$

and

$$
\frac{d\tilde u}{d\ell}
=(4-d)\tilde u-\frac{3\tilde u^2}{2(1+\tilde r)^2}+\cdots.
$$

The dots include higher operators, higher-loop terms, derivative interactions, anomalous field rescaling, and cutoff-scheme details.

## What the scalar example teaches

First, the mass term is relevant. The $2\tilde r$ term says that a small mass perturbation grows toward the infrared near the Gaussian fixed point.

Second, the quartic coupling has engineering flow $(4-d)\tilde u$. It is marginal in four dimensions, relevant below four dimensions, and irrelevant above four dimensions at tree level.

Third, loops bend the flow. The $-3\tilde u^2/2$ term competes with the engineering growth of $\tilde u$ when $d<4$.

Fourth, fixed points arise when scaling and loops balance. For $d=4-\epsilon$ and small $\epsilon$,

$$
\frac{d\tilde u}{d\ell}
=\epsilon\tilde u-\frac32\tilde u^2+\cdots
$$

has the nonzero fixed point

$$
\tilde u_*=\frac{2\epsilon}{3}+O(\epsilon^2).
$$

The coordinate of the fixed point is not universal. Critical exponents extracted from the linearized flow are the physical data.

## Relation to beta functions

Momentum-shell equations are beta functions, but the sign convention depends on the flow parameter.

Here

$$
\ell=\log\frac{\Lambda_{\mathrm{old}}}{\Lambda_{\mathrm{new}}}
$$

increases toward the infrared. In renormalized perturbation theory, one often defines

$$
\beta_g=\mu\frac{dg}{d\mu},
$$

where $\mu$ increases toward the ultraviolet. If $\mu$ is identified roughly with a running cutoff, then

$$
\frac{d}{d\ell}\sim -\mu\frac{d}{d\mu}.
$$

This is why signs can appear reversed between Wilsonian IR-time flows and Callan–Symanzik beta functions.

There is also scheme dependence. A sharp cutoff, a smooth cutoff, and minimal subtraction produce different coordinates on theory space. Universal quantities are not raw recursion coefficients; they are invariant data such as critical exponents, fixed-point anomalous dimensions, and physical observables.

## Relevant, irrelevant, and marginal directions

Near a fixed point, write

$$
\tilde g^i=\tilde g_*^i+\delta \tilde g^i.
$$

Linearizing the IR flow gives

$$
\frac{d}{d\ell}\delta\tilde g^i
=M^i{}_j\delta\tilde g^j+\cdots.
$$

Eigenvectors of $M$ define scaling directions.

| Direction | Eigenvalue $y$ | Behavior toward the IR |
|---|---:|---|
| relevant | $y>0$ | grows |
| irrelevant | $y<0$ | shrinks |
| marginal | $y=0$ at linear order | decided by nonlinear terms |

At the Gaussian fixed point this reproduces engineering dimensions. At an interacting fixed point, anomalous dimensions change the eigenvalues.

## Why rescaling is not optional

If one integrates out a shell but does not rescale, the cutoff changes from $\Lambda$ to $\Lambda e^{-d\ell}$. The action now lives on a smaller momentum domain and cannot be compared term by term with the original action.

Rescaling restores the cutoff and asks a sharper question:

$$
\text{after coarse graining, does the action return to itself?}
$$

If yes, the theory is at a fixed point. If not, the couplings have moved through theory space.

A fixed point is therefore not simply an action unchanged by integration. It is an action unchanged by integration plus rescaling.

## When momentum-shell RG is trustworthy

Momentum-shell RG is most transparent for Euclidean scalar theories, statistical field theories, and systems where modes can be cleanly separated by momentum magnitude. It becomes subtler in important cases.

| System | Subtlety |
|---|---|
| Gauge theories | a naive momentum cutoff can violate gauge invariance. |
| Fermions near a Fermi surface | low energy means distance from the Fermi surface, not small $|p|$. |
| Disordered systems | replicas, supersymmetry, or Keldysh methods may be needed. |
| Real-time systems | integrating out modes can generate dissipation and noise. |
| Gravity | momentum cutoffs are hard to define covariantly. |
| Strong coupling | no small shell expansion may exist. |

The lesson is not that shell RG is obsolete. It is the cleanest classroom model of Wilsonian reasoning. More sophisticated methods preserve the same structure while adapting the cutoff and variables to harder problems.

## Common pitfalls

**Forgetting the rescaling step.** Shell integration alone gives threshold corrections. RG flow in a fixed theory space requires rescaling.

**Comparing IR-time and UV-time beta functions without flipping signs.** Wilsonian $\ell$ usually increases toward the infrared. The convention $\mu dg/d\mu$ increases toward the ultraviolet.

**Taking cutoff-dependent coordinates too literally.** Fixed-point coordinates in a sharp cutoff scheme are not universal numbers.

**Discarding generated operators too early.** Shell integration generates every operator allowed by symmetry. Truncations must be justified by relevance, power counting, or another controlled approximation.

**Calling an operator irrelevant without naming the fixed point.** Relevance is a local property near a fixed point.

**Using scalar shell RG as a gauge-theory regulator without care.** Gauge theories require regulators and truncations compatible with Ward, Slavnov–Taylor, or BRST structure.

## Relations to other pages

This page follows [Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/) and prepares [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/) and [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/).

The scalar example previews [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/), and [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/).

The comparison with $\mu$-dependent beta functions connects back to [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/), and [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/).

## Research status

Momentum-shell RG is established as a conceptual and calculational method. It remains one of the clearest ways to derive relevance, universality, and the Wilson–Fisher fixed point.

Modern research often uses descendants or refinements: exact RG equations, functional RG, lattice blocking, tensor-network coarse graining, holographic RG, and RG adapted to Fermi surfaces, disorder, nonequilibrium systems, or gauge constraints. These methods differ in implementation but inherit the same central structure: reduce resolution, compensate with an effective description, and study the resulting flow.

## Exercises

### Exercise 1: Tree-level scaling of a coupling

Let

$$
S\supset g\int d^d x\,\mathcal O(x),
$$

where $\mathcal O$ has scaling dimension $\Delta$ at a fixed point. Show that with IR time $\ell$,

$$
\frac{dg}{d\ell}=(d-\Delta)g.
$$

<details><summary><strong>Solution</strong></summary>

Under $x=e^{d\ell}x'$, the measure gives

$$
d^d x=e^{d d\ell}d^d x'.
$$

The operator transforms as

$$
\mathcal O(x)=e^{-\Delta d\ell}\mathcal O'(x').
$$

Therefore

$$
g\int d^d x\,\mathcal O(x)
=g e^{(d-\Delta)d\ell}\int d^d x'\,\mathcal O'(x').
$$

Thus $g(\ell+d\ell)=g(\ell)e^{(d-\Delta)d\ell}$, so

$$
\frac{dg}{d\ell}=(d-\Delta)g.
$$

</details>

### Exercise 2: Thin-shell integral

Show that

$$
\int_{\Lambda e^{-d\ell}<|q|<\Lambda}\frac{d^d q}{(2\pi)^d}\frac{1}{q^2+r}
=K_d\frac{\Lambda^d d\ell}{\Lambda^2+r}+O(d\ell^2).
$$

<details><summary><strong>Solution</strong></summary>

Use spherical coordinates:

$$
\int_{\mathrm{shell}}\frac{d^d q}{(2\pi)^d}\frac{1}{q^2+r}
=K_d\int_{\Lambda e^{-d\ell}}^{\Lambda}dq\,\frac{q^{d-1}}{q^2+r}.
$$

For an infinitesimal shell, evaluate the integrand at $q=\Lambda$. The shell thickness is

$$
\Lambda-\Lambda e^{-d\ell}=\Lambda d\ell+O(d\ell^2).
$$

Therefore

$$
K_d\int_{\Lambda e^{-d\ell}}^{\Lambda}dq\,\frac{q^{d-1}}{q^2+r}
=K_d\frac{\Lambda^{d-1}}{\Lambda^2+r}\Lambda d\ell+O(d\ell^2),
$$

which is the desired result.

</details>

### Exercise 3: Relevance of the quartic coupling

At the Gaussian fixed point, $[\phi]=(d-2)/2$. Find the engineering dimension of $\phi^4$ and the tree-level flow of $u$.

<details><summary><strong>Solution</strong></summary>

The operator dimension is

$$
\Delta_{\phi^4}=4\frac{d-2}{2}=2d-4.
$$

The coupling dimension is

$$
d-\Delta_{\phi^4}=d-(2d-4)=4-d.
$$

Therefore

$$
\frac{du}{d\ell}=(4-d)u+\cdots.
$$

The quartic coupling is relevant for $d<4$, marginal at $d=4$, and irrelevant for $d>4$ at tree level.

</details>

### Exercise 4: Wilson–Fisher fixed point in the simplified flow

Using

$$
\frac{d\tilde u}{d\ell}=\epsilon\tilde u-\frac32\tilde u^2,
$$

find the nonzero fixed point to leading order in $\epsilon$.

<details><summary><strong>Solution</strong></summary>

Set the beta function to zero:

$$
0=\epsilon\tilde u-\frac32\tilde u^2
=\tilde u\left(\epsilon-\frac32\tilde u\right).
$$

Thus

$$
\tilde u_*=0,
\qquad
\tilde u_*=\frac{2\epsilon}{3}.
$$

The nonzero fixed point is the leading Wilson–Fisher fixed point in this normalization.

</details>

### Exercise 5: Sign of RG time

Let $\ell=\log(\Lambda_0/\Lambda)$ and $t=\log\mu$. If $\mu$ is identified with $\Lambda$, show that $d/d\ell=-d/dt$.

<details><summary><strong>Solution</strong></summary>

If $\mu$ is identified with $\Lambda$, then $t=\log\Lambda+\text{constant}$. Meanwhile

$$
\ell=\log\Lambda_0-\log\Lambda.
$$

Therefore $d\ell=-d\log\Lambda=-dt$, so

$$
\frac{d}{d\ell}=-\frac{d}{dt}.
$$

This is the sign flip between IR Wilsonian time and UV-oriented Callan–Symanzik time.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the classic momentum-shell and critical-phenomena viewpoint.
- Leo Kadanoff's block-spin picture, for the real-space coarse-graining intuition underlying Wilsonian RG.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for systematic shell and field-theoretic RG treatments.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for renormalization group methods and critical phenomena.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter 23, for a modern QFT derivation of Wilsonian RG flows.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, chapter 6, for RG in condensed-matter and statistical-field-theory settings.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapter 3, for power counting, matching, and Wilsonian EFT logic.

## Version history

- 2026-06-17: First polished draft. Derived shell integration, rescaling, one-loop scalar flow, relevance classification, and the Wilson–Fisher preview with IR-time conventions.
