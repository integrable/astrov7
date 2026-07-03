---
title: "Renormalization Is Not Only Infinities"
description: "Why the modern meaning of renormalization is scale dependence, locality, and effective description—not merely the cancellation of divergent integrals."
sidebar:
  label: "Not Only Infinities"
  order: 7
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Coleman, Dilatations and Renormalization and Symmetry; Srednicki §§27–29; Weinberg Vol. I ch. 12 and Vol. II ch. 18; Schwartz chs. 21–23; Zinn-Justin, RG and critical phenomena chapters; Burgess 2020 chs. 1–3."
topics:
  - renormalization concept
  - scale dependence
  - Wilsonian renormalization
  - effective field theory
  - universality
  - fixed points
canonicalTopics:
  - renormalization
  - renormalization-group
  - wilsonian-rg
  - effective-field-theory
  - universality
researchStatus:
  established:
    - "The Wilsonian and EFT interpretation of renormalization as scale-dependent local description is standard modern QFT."
  active:
    - "The same viewpoint continues to evolve in nonperturbative RG, generalized symmetries, conformal bootstrap, lattice chiral gauge theories, quantum gravity EFT, and the classification of QFTs by fixed points and deformations."
---

## Summary

Renormalization is often introduced as the trick that makes divergent loop integrals finite. That is historically honest but conceptually too small. Divergences are one entrance to the subject, not the subject itself.

The modern view is:

$$
\text{renormalization}
=\text{the organization of physics across scales by locality, symmetry, and change of description}.
$$

In perturbation theory this organization appears as regulators, counterterms, renormalization conditions, beta functions, and anomalous dimensions. In Wilson's formulation it appears as the flow of an action when high-momentum or short-distance degrees of freedom are integrated out. In effective field theory it appears as the statement that short-distance ignorance is encoded in local operators ordered by relevance. In critical phenomena it appears as fixed points, scaling, and universality.

The cancellation of infinities is therefore not the miracle. The miracle is that the short-distance details that matter at long distances can be organized into a finite hierarchy of local data.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Conceptual map of renormalization beyond infinity cancellation: counterterms, running parameters, Wilsonian flow, EFT power counting, fixed points, and universality](/figures/renormalization-rg-eft/renormalization-beyond-infinities-map.svg)

<figcaption>

Renormalization is broader than infinity cancellation. Local counterterms, running parameters, Wilsonian flow, EFT power counting, and fixed points are complementary ways of organizing the same scale-dependent local data.

</figcaption>
</figure>

:::note[The slogan to retire]
"Renormalization removes infinities" is not false, but it is too narrow. A better slogan is: renormalization tells us how the description of a system changes when the scale of resolution changes.
:::

## Prerequisites

You should have read the earlier pages in this chapter: [Short-Distance Singularities](/renormalization-rg-eft/why-renormalization/short-distance-singularities/), [Loops and Locality](/renormalization-rg-eft/why-renormalization/loops-and-locality/), [Divergences as Local Operators](/renormalization-rg-eft/why-renormalization/divergences-as-local-operators/), [Bare versus Renormalized](/renormalization-rg-eft/why-renormalization/bare-versus-renormalized/), [Physical Parameters](/renormalization-rg-eft/why-renormalization/physical-parameters/), and [Regulator Dependence](/renormalization-rg-eft/why-renormalization/regulator-dependence/).

You do not need to know the full Callan–Symanzik equation, Wilsonian exact RG, or EFT matching machinery yet. This page explains why those later technologies are different faces of the same scale problem.

## Core idea

A local QFT lets us ask questions at arbitrarily short distances. Sometimes that produces divergent integrals. But even when no literal divergence is present, changing the resolution at which we describe a system changes the parameters and operators that are useful.

The deeper chain is

$$
\text{short-distance modes}
\longrightarrow
\text{local effects at long distance}
\longrightarrow
\text{scale-dependent parameters}
\longrightarrow
\text{RG flow and EFT organization}.
$$

A UV divergence is one extreme version of this chain. It says that the short-distance modes have not merely affected a parameter; they have affected it without bound as the regulator is removed. Renormalization then supplies the physical definition of the parameter. But the same logic applies when the correction is large and finite, small and finite, or deliberately kept as a finite threshold correction.

This is why renormalization belongs in statistical physics, condensed matter, nuclear physics, gravity, and hydrodynamics, not only in high-energy loop calculations. Whenever we separate scales and ask which details survive at long distances, we are doing renormalization.

## Setup and conventions

We use $Q$ for a physical external scale, $M$ for a heavy threshold, $\Lambda$ for a cutoff or Wilsonian resolution scale, and $\mu$ for a renormalization scale. The distinction matters:

$$
Q\quad\text{is measured by the process},
\qquad
M\quad\text{is a physical threshold},
$$

$$
\Lambda\quad\text{limits the active modes in a regulated or Wilsonian description},
\qquad
\mu\quad\text{labels the convention for renormalized parameters}.
$$

For a dimensionless renormalized coupling $g(\mu)$, this volume uses

$$
\beta_g(g)\equiv \left.\mu\frac{dg}{d\mu}\right|_{\text{bare parameters fixed}}.
$$

For Wilsonian flow it is often convenient to use

$$
\ell=\log\frac{\Lambda_0}{\Lambda},
$$

which increases toward the infrared as the cutoff is lowered.

The same physics can therefore be described using complementary languages:

| Language | What changes? | What stays invariant? |
|---|---|---|
| renormalized perturbation theory | $g_i(\mu)$, $Z$ factors, counterterms, scheme conventions | physical observables |
| Wilsonian RG | $S_\Lambda$, active fields, Wilsonian couplings $g_i(\Lambda)$ | long-distance physics below the cutoff |
| effective field theory | Wilson coefficients $C_i(\mu)$ and operator basis | matched low-energy observables to a stated accuracy |
| critical phenomena | coarse-grained Hamiltonian and relevant perturbations | universal scaling data within a universality class |

The languages are not enemies. They answer slightly different versions of the same scale question.

## The old problem: divergent loop integrals

The traditional entrance to renormalization is a divergent loop integral. In a scalar theory one might meet

$$
I(m^2)=\int\frac{d^4 k_E}{(2\pi)^4}\frac{1}{k_E^2+m^2},
$$

which diverges at large Euclidean momentum. With a cutoff,

$$
I_\Lambda(m^2)
=\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\log\frac{\Lambda^2}{m^2}+\cdots
\right].
$$

In a self-energy diagram this expression multiplies the local operator $\phi^2$. The counterterm for the mass absorbs the cutoff dependence. The renormalized mass is then fixed by a physical condition, such as the pole of the propagator or a value of a two-point function at a reference momentum.

This is real renormalization, but it is not all of renormalization. It is the case where scale sensitivity becomes infinite as the UV cutoff is removed.

The moral is local:

$$
\text{UV divergence} \quad\Rightarrow\quad \text{missing local short-distance datum}.
$$

The deeper moral is about scale:

$$
\text{changing the UV description} \quad\Rightarrow\quad \text{changing local coefficients}.
$$

## Finite shell integration is already renormalization

Consider a Wilsonian step. Split a scalar field into slow and fast modes,

$$
\phi=\phi_<+\phi_>,
$$

where $\phi_>$ contains momenta in a finite shell

$$
\frac{\Lambda}{b}<|k|<\Lambda,
\qquad b>1.
$$

Integrating out this shell produces a new action for $\phi_<$:

$$
e^{-S_{\Lambda/b}[\phi_<]}
=\int_{\Lambda/b<|k|<\Lambda}\mathcal D\phi_>\,e^{-S_\Lambda[\phi_<+\phi_>]}.
$$

For finite $b$ and finite $\Lambda$, this integral need not contain any infinity. Nevertheless the couplings change. For example, in a schematic $\phi^4$ theory, shell modes correct the mass term by a finite amount of the form

$$
\delta m^2\sim \frac{\lambda}{2}
\int_{\Lambda/b<|k|<\Lambda}
\frac{d^d k}{(2\pi)^d}\frac{1}{k^2+m^2}.
$$

They also correct the quartic interaction by a finite amount of the form

$$
\delta\lambda\sim -3\lambda^2
\int_{\Lambda/b<|k|<\Lambda}
\frac{d^d k}{(2\pi)^d}\frac{1}{(k^2+m^2)^2},
$$

up to convention-dependent signs and factors. The precise coefficients depend on the normalization of the action and the cutoff scheme; the lesson does not.

After the shell is integrated out, one rescales momenta and fields to compare the new action to the old one. The result is an RG transformation:

$$
S_\Lambda\longrightarrow S_{\Lambda/b}\longrightarrow \text{rescaled action}.
$$

No infinity was required. Renormalization has occurred because the description changed with scale.

## Locality survives coarse graining

Why does a Wilsonian step produce local operators rather than arbitrary nonlocal mess?

Because the modes being removed have wavelengths of order $1/\Lambda$, while the remaining fields vary slowly on that scale. At external momenta $p\ll \Lambda$, the influence of a high-momentum shell can be expanded in powers of $p/\Lambda$:

$$
\frac{1}{(k+p)^2+m^2}
=\frac{1}{k^2+m^2}
-\frac{2k\cdot p+p^2}{(k^2+m^2)^2}
+\cdots.
$$

Each term in this expansion is polynomial in external momenta. In position space, polynomial momentum dependence corresponds to local operators with more derivatives:

$$
\phi^2,
\qquad
\partial_\mu\phi\partial^\mu\phi,
\qquad
\phi^4,
\qquad
(\partial\phi)^2\phi^2,
\qquad
\phi^6,
\qquad\ldots
$$

This is the Wilsonian reason the EFT expansion exists. The details of the high-momentum shell are not thrown away. They are compressed into local coefficients.

Nonlocality can appear when the modes being integrated out are not heavy relative to the process, or when massless particles propagate over long distances. That is not a failure of locality. It is a warning that those degrees of freedom should remain explicit in the low-energy description.

## Running couplings are coordinates, not new forces of nature

In renormalized perturbation theory, we introduce a scale $\mu$ and define parameters such as $g(\mu)$ or $m(\mu)$. These parameters run:

$$
\mu\frac{dg}{d\mu}=\beta_g(g).
$$

This does not mean the experiment changes when we rename $\mu$. It means the coordinate used for the local interaction changes when we choose a different subtraction scale.

A physical observable $\mathcal O(Q)$ can be written schematically as

$$
\mathcal O(Q)=g(\mu)+b g^2(\mu)\log\frac{Q}{\mu}+O(g^3).
$$

The explicit logarithm changes when $\mu$ changes. The coupling $g(\mu)$ changes in just the compensating way, so that the exact observable is independent of $\mu$:

$$
\mu\frac{d}{d\mu}\mathcal O(Q)=0.
$$

At finite perturbative order, residual $\mu$ dependence remains because higher-order terms have been omitted. That residual dependence is not physical scale dependence; it is an error estimate and a diagnostic of missing orders.

Running is therefore not mystical. It is the bookkeeping needed when local parameters are defined at one scale and used at another.

## Effective field theory remembers heavy physics locally

Suppose a theory contains a heavy particle of mass $M$, but we study processes with

$$
Q\ll M.
$$

At low energy, the heavy particle cannot go on shell. Its propagator can be expanded:

$$
\frac{1}{M^2-Q^2}
=\frac{1}{M^2}\left(1+\frac{Q^2}{M^2}+\frac{Q^4}{M^4}+\cdots\right).
$$

In position space this becomes a series of local operators:

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\text{light}}
+\frac{C_1}{M^2}\mathcal O_1
+\frac{C_2}{M^4}\mathcal O_2
+\cdots.
$$

This is renormalization without an infinity in sight. The heavy particle has been removed as an explicit degree of freedom, but its effects remain in Wilson coefficients. Matching determines those coefficients. Running evolves them between scales. Power counting tells us which terms matter at a desired accuracy.

The EFT lesson is sharp:

$$
\text{low-energy ignorance is not ignorance without structure}.
$$

It is organized by locality, symmetries, and powers of $Q/M$.

## Universality is renormalization as explanation

Renormalization also explains why very different microscopic systems can have the same long-distance behavior.

Near a fixed point, a theory is described by small perturbations

$$
S=S_*+\sum_i g_i\int d^d x\,\mathcal O_i(x).
$$

If $\mathcal O_i$ has scaling dimension $\Delta_i$, the dimensionless coupling obeys, to leading order,

$$
\frac{d\tilde g_i}{d\ell}=(d-\Delta_i)\tilde g_i+\text{nonlinear terms}.
$$

Only relevant perturbations, with $\Delta_i<d$, grow toward the infrared. Irrelevant perturbations fade away. Marginal perturbations require a closer look.

This explains universality. Many microscopic Hamiltonians differ by enormous numbers of irrelevant details. Under RG flow those details become less important, and the long-distance physics is governed by a small number of relevant parameters and the fixed point they approach.

No divergent Feynman integral is needed to state this. The renormalization group is doing something more powerful: it is explaining why macroscopic behavior can be simpler than microscopic construction.

## Scale dependence versus scale invariance

Renormalization is also the language in which scale invariance is lost, recovered, or refined.

Classically, a theory may appear scale invariant because its couplings have no dimensions. Quantum mechanically, the renormalization scale can enter through logarithms and beta functions. Scale invariance is broken when

$$
\beta^i(g)\ne 0.
$$

At a fixed point,

$$
\beta^i(g_*)=0,
$$

and scale invariance may reappear as a quantum statement. In many unitary relativistic examples, scale invariance is enhanced to conformal invariance, though the assumptions behind that enhancement matter and are studied elsewhere.

This is another reason the infinity-only picture is too small. Renormalization does not merely repair calculations. It classifies possible scale behavior:

| RG behavior | Physical meaning |
|---|---|
| flow away from a fixed point | a relevant deformation sets a scale |
| flow toward a fixed point | long-distance universality or emergent scale invariance |
| marginally relevant flow | logarithmically slow departure from scale invariance |
| marginally irrelevant flow | logarithmically slow approach to a fixed point |
| dimensional transmutation | a dimensionless coupling generates a physical scale |

A theory of scale has to say all of this. A theory of infinity cancellation does not.

## Renormalization as a change of coordinates on theory space

The phrase **theory space** means the space of all local actions compatible with chosen fields and symmetries:

$$
S=\sum_i g_i\int d^d x\,\mathcal O_i(x).
$$

Renormalization moves us through this space or changes coordinates on it. A scheme change is a coordinate change,

$$
g^i\longrightarrow g^{\prime i}(g),
$$

and the beta functions transform as a vector field:

$$
\beta^{\prime i}(g')=\frac{\partial g^{\prime i}}{\partial g^j}\beta^j(g).
$$

The individual components of $\beta^i$ depend on coordinates. The existence of a fixed point, the scaling dimensions of perturbations around it, and physical observables are invariant when treated exactly.

This geometric viewpoint clarifies a lot of otherwise annoying facts. It explains why finite counterterms can change beta-function coefficients beyond universal orders. It explains why redundant operators and field redefinitions do not change the $S$-matrix. It explains why EFT operator bases can differ while physical predictions agree.

Good renormalization practice is therefore not about worshiping a particular scheme. It is about keeping track of which statements are coordinate choices and which statements are physical.

## Why this viewpoint changes how one learns QFT

If renormalization is taught only as divergence subtraction, students naturally ask:

$$
\text{Why not avoid divergent theories?}
$$

The modern answer is that divergences are not the defining issue. Scale separation is.

A good low-energy theory is rarely a final microscopic theory. It is a controlled description valid in a domain. Its job is to identify the degrees of freedom and local operators that matter at the scale being studied. Once this is understood, several slogans change meaning.

| Narrow slogan | Better modern statement |
|---|---|
| renormalization removes infinities | renormalization organizes scale dependence |
| counterterms cancel bad terms | counterterms encode local short-distance data |
| nonrenormalizable theories are sick | higher-dimension operators are EFT corrections |
| the cutoff is unphysical | sometimes it is a regulator; sometimes it is the EFT boundary |
| running couplings are measured at different energies | running couplings are scheme-dependent coordinates related to scale-dependent observables |
| microscopic details determine everything | relevant data and fixed points determine long-distance universality |

The second column is not softer. It is more precise.

## What remains predictive?

A common worry is that the Wilsonian or EFT viewpoint sounds like giving up. If all possible local operators are allowed, do we lose predictivity?

No, because predictivity comes from ordering. Local operators are organized by symmetries and scaling. At energies $Q\ll M$, an operator of dimension $\Delta>d$ contributes with a suppression roughly like

$$
\left(\frac{Q}{M}\right)^{\Delta-d}.
$$

To compute to fixed accuracy, only finitely many operators are needed. The rest are smaller than the error tolerance.

In a renormalizable theory near a Gaussian fixed point, only relevant and marginal operators are needed for predictions that survive the continuum limit. In an EFT, irrelevant operators are kept systematically because they encode controlled corrections. In a critical system, only a small number of relevant perturbations must be tuned to reach a universality class.

The predictive principle is therefore:

$$
\text{infinitely many allowed terms, but only finitely many matter at fixed accuracy and scale}.
$$

That sentence is one of the real gifts of renormalization.

## Common pitfalls

**Treating infinities as the definition of renormalization.** Divergences are one manifestation of short-distance sensitivity. Wilsonian coarse graining, EFT matching, and critical phenomena show that renormalization is broader.

**Thinking finite means unrenormalized.** A finite threshold correction, a finite shell integration, or a finite scheme change can still be renormalization. The issue is scale-dependent description, not only divergent arithmetic.

**Thinking Wilsonian RG and MS beta functions must look identical.** They use different cutoffs, different coordinates, and sometimes different flow parameters. They agree on physical scaling data when their domains overlap.

**Thinking an EFT is arbitrary because it has infinitely many operators.** Power counting and symmetries make the expansion predictive at fixed accuracy.

**Thinking irrelevant means unimportant forever.** Irrelevant means suppressed near a fixed point or at low energies. Irrelevant operators can still control corrections to scaling, encode finite-size effects, or become important when the scale hierarchy disappears.

**Thinking scale dependence is always a quantum effect.** Quantum loops are a central source of RG flow in relativistic QFT, but coarse graining and universality also appear in classical statistical systems.

## Relations to other pages

This page closes the conceptual chapter Why Renormalization?. The earlier pages explained the route from short-distance singularities to local counterterms, from bare parameters to physical parameters, and from regulator dependence to regulator-independent predictions.

The next chapter, [Regularization and Counterterms](/renormalization-rg-eft/regularization-counterterms/), turns the conceptual language into tools: cutoffs, dimensional regularization, Pauli–Villars fields, lattice previews, counterterm actions, power counting, and renormalized correlation functions.

Later chapters expand the four main faces of this page. Renormalized Perturbation Theory develops $Z$ factors and renormalization conditions. Renormalization Group Equations develops beta functions and anomalous dimensions. Wilsonian Renormalization develops $S_\Lambda$ and theory space. Effective Field Theory develops matching, running, decoupling, field redefinitions, and Wilson coefficients.

## Research status

The modern scale-based interpretation of renormalization is established. It is central to perturbative QFT, critical phenomena, lattice field theory, condensed matter field theory, and effective field theory.

The active frontier is not whether renormalization is broader than infinity cancellation; that is settled. The active questions concern how this structure behaves in harder settings: nonperturbative continuum limits, chiral gauge theories, theories without Lagrangians, generalized symmetries and defects under RG flow, conformal manifolds, quantum gravity, real-time finite-density systems, and automated high-order EFT matching.

## Exercises

### Exercise 1: A finite shell still changes couplings

Let

$$
J(p)=\int_{\Lambda/b<|k|<\Lambda}\frac{d^d k}{(2\pi)^d}
\frac{1}{(k^2+m^2)((k+p)^2+m^2)},
$$

with $p\ll \Lambda$. Show that the low-momentum effect of this finite shell can be expanded in local powers of $p$.

<details><summary><strong>Solution</strong></summary>

For shell momenta $k$ of order $\Lambda$ and external momentum $p\ll \Lambda$, expand

$$
\frac{1}{(k+p)^2+m^2}
=\frac{1}{k^2+m^2}
-\frac{2k\cdot p+p^2}{(k^2+m^2)^2}
+\frac{(2k\cdot p+p^2)^2}{(k^2+m^2)^3}
+\cdots.
$$

Substituting into $J(p)$ gives

$$
J(p)=A_0+A_2p^2+A_4p^4+\cdots,
$$

where odd terms vanish after angular integration in a rotationally invariant shell. Each coefficient is a finite integral over the shell. Polynomial dependence on $p$ corresponds to local derivative operators in position space. Thus finite shell integration already produces local renormalization of couplings.

</details>

### Exercise 2: Running cancels an explicit logarithm

Suppose an observable has the perturbative form

$$
\mathcal O(Q)=g(\mu)+b g^2(\mu)\log\frac{Q}{\mu}+O(g^3).
$$

Assuming $\mu d\mathcal O/d\mu=0$, find the beta function through order $g^2$.

<details><summary><strong>Solution</strong></summary>

Differentiate at fixed $Q$:

$$
0=\mu\frac{d\mathcal O}{d\mu}
=\beta_g+b\left(2g\beta_g\log\frac{Q}{\mu}-g^2\right)+O(g^3).
$$

If $\beta_g$ begins at order $g^2$, then the term $2b g\beta_g\log(Q/\mu)$ is order $g^3$ and can be dropped at this accuracy. Therefore

$$
0=\beta_g-b g^2+O(g^3),
$$

so

$$
\beta_g=b g^2+O(g^3).
$$

The explicit logarithm of $Q/\mu$ is compensated by the running of $g(\mu)$.

</details>

### Exercise 3: Local EFT memory of a heavy particle

A tree-level full-theory amplitude contains the factor

$$
\frac{g^2}{M^2-s},
$$

where $s\ll M^2$. Expand it through order $s/M^4$ and identify the EFT interpretation.

<details><summary><strong>Solution</strong></summary>

For $s\ll M^2$,

$$
\frac{g^2}{M^2-s}
=\frac{g^2}{M^2}\frac{1}{1-s/M^2}
=\frac{g^2}{M^2}
\left(1+\frac{s}{M^2}+O\left(\frac{s^2}{M^4}\right)\right).
$$

The leading term corresponds to a local operator with coefficient proportional to $g^2/M^2$. The next term corresponds to a higher-derivative local operator suppressed by $g^2/M^4$. The heavy particle is not present as an explicit low-energy degree of freedom, but its effects are remembered by Wilson coefficients.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," "Renormalization and Symmetry," and "Asymptotic Freedom."
- Mark Srednicki, *Quantum Field Theory*, especially the sections on renormalization schemes, the renormalization group, and effective field theory.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, and Vol. II, chapter 18.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 21–23.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on renormalization, RG, composite operators, and critical phenomena.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially chapters 1–3.
- Joseph Polchinski, "Renormalization and Effective Lagrangians," *Nuclear Physics B* **231** (1984) 269–295.

## Version history

- 2026-06-17: First polished draft. Added the capstone conceptual page explaining renormalization as scale dependence, Wilsonian coarse graining, EFT organization, fixed points, and universality rather than only cancellation of divergent integrals.
