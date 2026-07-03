---
title: "Counterterm Schemes"
description: "How MS, modified MS, momentum subtraction, on-shell schemes, and finite renormalizations organize the same bare theory with different renormalized coordinates."
sidebar:
  label: "Counterterm Schemes"
  order: 3
level: Graduate
status: "Polished draft"
source: "Coleman, renormalization lectures; Srednicki §§27–29; Schwartz chs. 18–23; Weinberg Vol. I ch. 12 and Vol. II ch. 18; Zinn-Justin, renormalization chapters."
topics:
  - counterterm schemes
  - minimal subtraction
  - modified minimal subtraction
  - momentum subtraction
  - on-shell renormalization
  - scheme dependence
canonicalTopics:
  - counterterm-schemes
  - minimal-subtraction
  - msbar-scheme
  - momentum-subtraction
  - scheme-dependence
researchStatus:
  established:
    - "Different counterterm schemes are different coordinate choices on the same renormalized physics, provided observables are computed and converted consistently."
  active:
    - "Scheme design and conversion remain important in precision gauge theory, EFT matching, lattice matching, multi-loop computations, unstable-particle definitions, and nonperturbative running-coupling schemes."
---

## Summary

A **counterterm scheme** is a systematic rule for choosing the divergent and finite parts of counterterms. It tells us how to pass from a regulated bare theory to renormalized parameters such as $m(\mu)$, $g(\mu)$, $\lambda(\mu)$, or Wilson coefficients $C_i(\mu)$.

The same regulated bare theory may be described by many renormalized coordinate systems:

$$
\text{bare theory}
\longrightarrow
\begin{cases}
\text{MS coordinates},\\
\overline{\mathrm{MS}}\text{ coordinates},\\
\text{momentum-subtraction coordinates},\\
\text{on-shell coordinates},\\
\text{Wilsonian or EFT coordinates}.
\end{cases}
$$

The physical predictions agree when the parameters are converted consistently and the perturbative expansion is carried to the same accuracy. The intermediate numbers need not agree. That is not a bug; it is what a change of coordinates looks like.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![A bare regulated theory is mapped by different counterterm schemes to different renormalized coordinate systems, which all predict the same observables after finite conversion](/figures/renormalization-rg-eft/counterterm-scheme-coordinate-map.svg)

<figcaption>

A counterterm scheme is a coordinate choice. MS, $\overline{\mathrm{MS}}$, momentum subtraction, and on-shell schemes assign different finite meanings to masses, couplings, and fields, but consistent conversion leaves observables unchanged.

</figcaption>
</figure>

The practical question is not "which scheme is true?" The practical question is "which scheme makes this problem transparent, stable, symmetry-compatible, and easy to compare with data or with another calculation?"

:::note[Regulator versus scheme]
A regulator makes divergent expressions finite. A scheme chooses how finite renormalized parameters are defined after the regulator is introduced. Dimensional regularization is a regulator; MS and $\overline{\mathrm{MS}}$ are schemes.
:::

## Prerequisites

You should know [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/) and [Renormalization Conditions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalization-conditions/). For the local-counterterm logic, review [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/) and [Divergences as Local Operators](/renormalization-rg-eft/why-renormalization/divergences-as-local-operators/).

We use the conventions of [Conventions and Notation](/renormalization-rg-eft/conventions/). In dimensional regularization near four dimensions,

$$
d=4-2\epsilon,
\qquad
\frac{1}{\bar\epsilon}\equiv \frac{1}{\epsilon}-\gamma_E+\log(4\pi).
$$

## Core idea

Counterterms are local. Their divergent parts cancel regulator dependence. Their finite parts define a scheme.

For a dimensionless coupling $g$, a typical bare-to-renormalized relation has the form

$$
g_0=\mu^{\kappa\epsilon}Z_g(g,\epsilon)g,
$$

where $\kappa$ is fixed by dimensional analysis. Expanding perturbatively,

$$
Z_g(g,\epsilon)
=1+\frac{a_1(g)}{\epsilon}
+\frac{a_2(g)}{\epsilon^2}
+\cdots
+f(g).
$$

The pole terms are needed to cancel ultraviolet divergences. The finite function $f(g)$ is a scheme choice. In minimal subtraction, $f(g)$ is set to zero by definition. In a momentum-subtraction scheme, $f(g)$ is chosen so that a specified Green function has a specified value at a specified momentum. In an on-shell scheme, $f(g)$ is chosen so that selected pole masses, residues, and low-energy amplitudes have physical meanings.

Different choices of $f(g)$ define different renormalized couplings. They describe the same physics if the bare theory is held fixed.

The mental model is:

$$
\text{scheme choice}
=\text{finite local redefinition of parameters and fields}.
$$

## Setup and conventions

Let a bare Lagrangian be rewritten as

$$
\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}}.
$$

A counterterm scheme gives rules for the coefficients in $\mathcal L_{\text{ct}}$. For a scalar theory,

$$
\mathcal L_{\text{ct}}
=\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4+\cdots.
$$

A scheme decides the coefficients

$$
\delta Z,\qquad \delta m^2,\qquad \delta\lambda,
$$

order by order in perturbation theory.

It is useful to split a counterterm into three conceptual pieces:

$$
\delta g=\delta g_{\text{div}}+\delta g_{\text{finite}}+\delta g_{\text{convention}}.
$$

This formula is schematic. The point is that "the counterterm" includes both forced cancellations and voluntary coordinate choices. In $\overline{\mathrm{MS}}$, the voluntary finite choice is extremely sparse. In on-shell or momentum-subtraction schemes, the finite choice is chosen to satisfy physically or kinematically motivated conditions.

The scheme is part of the definition of the quoted renormalized parameter. A symbol like $\lambda$ is not complete by itself. A complete statement is something like

$$
\lambda_{\overline{\mathrm{MS}}}(\mu=1\,\mathrm{TeV})=0.126,
$$

or

$$
m_{\text{pole}}=173\,\mathrm{GeV},
$$

or

$$
g_{\text{MOM}}(\mu)=\text{value defined by a specified vertex at a specified Euclidean point}.
$$

## Minimal subtraction

**Minimal subtraction**, or MS, is defined in dimensional regularization by subtracting only the pole part in $\epsilon$.

For a generic renormalization factor,

$$
Z_g^{\mathrm{MS}}
=1+\sum_{L\ge 1}\sum_{k=1}^{L}\frac{Z_{g,Lk}}{\epsilon^k}.
$$

There are no finite terms. This is a precise convention, not a claim that finite terms are unimportant.

MS is powerful because the counterterms are algebraically simple. In a mass-independent scheme such as MS, the beta functions for dimensionless couplings depend only on the dimensionless couplings, not on ratios such as $m^2/\mu^2$. This makes MS especially useful for RG equations, high-order perturbation theory, and EFT operator mixing.

The cost is interpretive. An MS mass or coupling is not directly a measured mass or coupling. It is a running coordinate. To compare with experiment, one must express observables in terms of MS parameters or convert MS parameters to more physical definitions.

## Modified minimal subtraction

The modified minimal-subtraction scheme, $\overline{\mathrm{MS}}$, subtracts not just $1/\epsilon$ but the common dimensional-regularization combination

$$
\frac{1}{\bar\epsilon}
=\frac{1}{\epsilon}-\gamma_E+\log(4\pi).
$$

Equivalently, many formulas can be written using a modified scale $\bar\mu$ related to $\mu$ by

$$
\bar\mu^2=4\pi e^{-\gamma_E}\mu^2.
$$

The exact placement of the factors $4\pi$ and $e^{-\gamma_E}$ is convention. The purpose is practical: $\overline{\mathrm{MS}}$ removes clutter that otherwise appears in nearly every loop integral.

For example, a typical logarithmic Euclidean one-loop integral has the expansion

$$
\mu^{2\epsilon}
\int\frac{d^d k_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta)^2}
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\bar\epsilon}
-\log\frac{\Delta}{\mu^2}
+O(\epsilon)
\right].
$$

In $\overline{\mathrm{MS}}$, the subtraction removes the $1/\bar\epsilon$ piece. The finite logarithm remains and drives scale dependence.

In modern particle physics and EFT, $\overline{\mathrm{MS}}$ is the default scheme for many high-order calculations. It is not default because it is more physical. It is default because it is efficient, portable, and RG-friendly.

## Momentum subtraction

A **momentum-subtraction scheme** defines renormalized parameters by imposing conditions on Green functions at a chosen momentum point. In Euclidean language, one might define a scalar quartic coupling by

$$
\Gamma^{(4)}_{E,R}\big|_{\text{sym},\mu}=\lambda_{\text{MOM}}(\mu),
$$

and the field normalization by

$$
\left.\frac{d\Gamma^{(2)}_{E,R}}{dp_E^2}\right|_{p_E^2=\mu^2}=1.
$$

Momentum subtraction is conceptually direct: the renormalized parameter is literally the value of a chosen Green function or derivative at a chosen point.

It is often useful when one wants to compare perturbation theory with Euclidean nonperturbative calculations. It is also helpful pedagogically because it makes the subtraction scale visible as a momentum scale.

The disadvantages are also clear. Momentum-subtraction counterterms contain finite pieces depending on the subtraction point. In massive theories, beta functions generally depend on ratios such as $m/\mu$. In gauge theories, Green functions used for MOM definitions can be gauge-dependent unless one defines the scheme using gauge-invariant quantities or carefully fixes a gauge.

A MOM coupling is therefore not automatically a physical observable. It is a well-defined coordinate if the subtraction prescription is fully specified.

## On-shell schemes

An **on-shell scheme** defines masses, residues, and selected couplings using physical pole data and low-energy processes.

For a stable scalar particle, the propagator condition is

$$
G_R(p)\underset{p^2\to m_{\text{pole}}^2}{=}
\frac{i}{p^2-m_{\text{pole}}^2+i\epsilon}+\text{regular}.
$$

This makes the renormalized mass equal to the pole mass and fixes the field normalization so that the pole residue is one. In QED, the electron mass and charge can be defined through the electron pole and the low-energy electromagnetic interaction.

On-shell schemes are intuitive and closely tied to measured quantities. They are often useful in precision calculations involving stable asymptotic particles.

But on-shell schemes are not always the best choice. They are awkward for confined fields, massless particles with infrared singularities, and unstable particles. They can also produce large logarithms when the physical process takes place at energies far above the on-shell mass. In such cases, one often uses an $\overline{\mathrm{MS}}$ or EFT scheme and converts to physical inputs at the end.

## Mass-independent and mass-dependent schemes

A scheme is **mass-independent** if its renormalization constants for dimensionless couplings do not depend on masses or ratios such as $m/\mu$. MS and $\overline{\mathrm{MS}}$ are the standard examples.

In a mass-independent scheme, the beta function has the form

$$
\beta_g=\mu\frac{dg}{d\mu}=\beta_g(g)
$$

for a single dimensionless coupling, with no explicit $m/\mu$ dependence. This makes RG equations simple.

A scheme is **mass-dependent** if the subtraction conditions introduce mass ratios into the renormalization constants. Momentum-subtraction and on-shell schemes are usually mass-dependent. Their beta functions may have the form

$$
\beta_g=\beta_g(g,m^2/\mu^2).
$$

Mass-dependent schemes can describe threshold decoupling more smoothly. Mass-independent schemes usually require explicit matching when heavy particles are integrated out.

Neither behavior is inherently better. They answer different bookkeeping needs.

## Finite renormalizations

Two schemes are related by finite renormalizations. For a single dimensionless coupling,

$$
g'=g+a g^3+b g^5+O(g^7).
$$

For a mass parameter,

$$
m'^2=m^2\left[1+c g^2+O(g^4)\right].
$$

For a field,

$$
\phi'=Z_{\text{fin}}^{1/2}\phi,
\qquad
Z_{\text{fin}}=1+z_1g^2+O(g^4).
$$

These transformations change the numerical values of renormalized parameters and the coefficients appearing in perturbative formulas. They do not change the physical predictions when everything is converted consistently.

This is why it is misleading to ask whether $g_{\overline{\mathrm{MS}}}$ or $g_{\text{MOM}}$ is "the real coupling." They are different coordinates. A coordinate can be more convenient, more stable, or more transparent. It is not more real.

## Beta functions under scheme changes

For a coupling redefinition

$$
g'=f(g),
$$

the beta function transforms by the chain rule:

$$
\beta_{g'}(g')=\frac{df(g)}{dg}\,\beta_g(g).
$$

This simple equation is one of the cleanest ways to see that a beta function is a vector field on coupling space. Its coordinate components depend on the coordinates.

Suppose

$$
\beta_g=b_1g^3+b_2g^5+O(g^7),
$$

and

$$
g'=g+a g^3+O(g^5).
$$

Then the first coefficient $b_1$ is invariant under this analytic finite redefinition. Higher coefficients can change. In many common four-dimensional gauge-theory conventions, the first two beta-function coefficients are universal within mass-independent schemes, but the assumptions behind that statement should always be checked.

Fixed-point existence and critical exponents are physical when properly defined, but perturbative truncations can make scheme dependence look larger or smaller than it really is. A fixed point that appears at strong coupling in one low-order scheme calculation deserves skepticism until scheme-stable evidence is available.

## A physical observable in two schemes

Consider a dimensionless observable with perturbative expansion

$$
\mathcal O(Q)=g^2(\mu)
+\left[A\log\frac{Q^2}{\mu^2}+B\right]g^4(\mu)
+O(g^6).
$$

Now change scheme by

$$
g'=g+a g^3+O(g^5).
$$

Inverting,

$$
g=g'-a g'^3+O(g'^5).
$$

Then

$$
\mathcal O(Q)=g'^2(\mu)
+\left[A\log\frac{Q^2}{\mu^2}+B-2a\right]g'^4(\mu)
+O(g'^6).
$$

The finite constant in the perturbative coefficient changed. The observable did not. The change in the definition of the coupling is exactly compensated by the change in the finite coefficient.

This is the basic anatomy of scheme dependence. Coefficients move around. Predictions do not, when computed consistently.

## Decoupling and thresholds

Mass-independent schemes such as $\overline{\mathrm{MS}}$ do not automatically remove heavy fields from beta functions at scales below their masses. If a theory contains a heavy particle of mass $M$, the $\overline{\mathrm{MS}}$ beta function above and below $M$ is usually handled by matching two EFTs at a scale $\mu\sim M$.

The workflow is:

$$
\text{full theory above }M
\longrightarrow
\text{match at }\mu\simeq M
\longrightarrow
\text{EFT below }M
\longrightarrow
\text{run to lower scales}.
$$

A mass-dependent scheme can display smooth threshold behavior directly, but often at the cost of more complicated beta functions. EFT matching in $\overline{\mathrm{MS}}$ is usually cleaner for high-order calculations.

This is one of the first places where the difference between a convenient scheme and a physical scale becomes impossible to ignore. The matching scale $\mu$ is arbitrary within a reasonable range. The heavy mass $M$ is physical. The residual $\mu$ dependence after truncation estimates missing higher-order terms.

## BPHZ and subtraction operators

The Bogoliubov–Parasiuk–Hepp–Zimmermann approach organizes renormalization by subtracting Taylor expansions of integrands or amplitudes according to the forest structure of divergent subgraphs. In this language, a scheme is encoded by a subtraction operator.

For a logarithmically divergent amplitude $F(p)$, a simple subtraction at a point $p=p_*$ has the schematic form

$$
F_R(p)=F(p)-F(p_*).
$$

For a superficially linear divergence, one subtracts more Taylor terms:

$$
F_R(p)=F(p)-F(p_*)-(p-p_*)^\mu
\left.\frac{\partial F}{\partial p^\mu}\right|_{p=p_*}.
$$

The full BPHZ forest formula handles overlapping divergences systematically. The point for this page is conceptual: subtracting local Taylor polynomials is another way to implement counterterm schemes. It makes locality of counterterms explicit.

## Choosing a scheme

A good scheme is adapted to the job.

| Task | Usually helpful scheme style |
|---|---|
| high-order RG and anomalous dimensions | MS or $\overline{\mathrm{MS}}$ |
| precision calculations with stable particles | on-shell or mixed on-shell/$\overline{\mathrm{MS}}$ |
| Euclidean nonperturbative comparisons | MOM-like schemes |
| EFT thresholds | $\overline{\mathrm{MS}}$ plus matching, or a threshold scheme |
| lattice-continuum conversion | lattice bare scheme matched to $\overline{\mathrm{MS}}$ or a nonperturbative intermediate scheme |
| conceptual pedagogy | cutoff or MOM first, then MS/$\overline{\mathrm{MS}}$ |
| gauge-invariant physical running | scheme defined by gauge-invariant observables |

Real calculations often use mixed schemes. For example, one may use on-shell masses for some particles, $\overline{\mathrm{MS}}$ couplings for RG evolution, and EFT Wilson coefficients matched at thresholds. This is not inconsistent if every definition is stated and every conversion is performed.

## Scheme dependence and truncation error

Exact observables are scheme independent. Truncated perturbative predictions are not. If

$$
\mathcal O=\mathcal O_0+\mathcal O_1+\mathcal O_2+\cdots,
$$

and the series is stopped at order $N$, then a scheme change generally shifts terms at order $N+1$ and higher into lower-looking finite pieces. The remaining scheme dependence is therefore a useful diagnostic of missing higher-order corrections.

This does not mean one can estimate uncertainty by wildly changing schemes without discipline. A sensible scheme variation should compare schemes that are natural for the same physical problem and do not introduce artificial large logarithms or bad convergence.

Scale variation and scheme variation are related but not identical. Changing $\mu$ within a scheme probes uncalculated logarithmic terms. Changing finite counterterm conventions probes a broader coordinate dependence. Both must be interpreted with care.

## Common pitfalls

**Calling dimensional regularization a scheme.** Dimensional regularization is a regulator. MS and $\overline{\mathrm{MS}}$ are schemes built naturally on it.

**Thinking $\overline{\mathrm{MS}}$ parameters are observables.** They are not. They are extremely useful running coordinates.

**Thinking on-shell schemes are always more physical.** They are close to physical pole definitions when stable asymptotic particles exist. They are not automatically better for high-energy, massless, confined, or unstable-particle problems.

**Forgetting heavy-particle matching.** In mass-independent schemes, heavy particles do not decouple from running by themselves. EFT matching does the decoupling work.

**Comparing numbers across schemes.** The statements $m_{\text{pole}}=m_{\overline{\mathrm{MS}}}(\mu)$ or $g_{\text{MOM}}=g_{\overline{\mathrm{MS}}}$ are generally false unless a conversion relation and scale are specified.

**Interpreting beta-function coefficients without assumptions.** Some coefficients are universal under restricted scheme changes. Others are not. Always ask what coupling definition and scheme class are being used.

## Relations to other pages

[Renormalization Conditions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalization-conditions/) explains how finite counterterms are fixed by conditions on Green functions, amplitudes, poles, or subtraction rules. This page compares the major families of such choices.

[Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/) gives the split $\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}}$. [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/) explains where the $1/\epsilon$ poles and $\mu$ scale enter. [Regulator Dependence](/renormalization-rg-eft/why-renormalization/regulator-dependence/) explains why regulator dependence must disappear from physical predictions.

Later pages on minimal subtraction, the on-shell scheme, wavefunction renormalization, mass and coupling renormalization, scheme dependence, matching, and RG equations will use this page as the scheme dictionary.

## Research status

The equivalence of schemes under finite renormalization is settled perturbative QFT. Scheme choice is a convention, not a new physical principle.

The research-level work is practical and subtle. Precision calculations require carefully designed input schemes. Gauge theories require symmetry-compatible definitions. EFTs require threshold matching and operator-basis conventions. Lattice calculations often pass through intermediate schemes before converting to $\overline{\mathrm{MS}}$. Multi-loop calculations require robust scheme-conversion algebra. Unstable particles and resonances require definitions that respect analyticity and gauge invariance.

In frontier contexts, scheme dependence can become diagnostic. If a claimed fixed point, anomalous dimension, or naturalness statement changes dramatically under reasonable scheme transformations, the calculation may be outside its trustworthy domain.

## Exercises

### Exercise 1: Transforming a beta function

Let

$$
\beta_g=b_1g^3+b_2g^5+O(g^7),
$$

and define a new coupling

$$
g'=g+a g^3+O(g^5).
$$

Show that the coefficient of $g'^3$ in $\beta_{g'}$ is still $b_1$.

<details><summary><strong>Solution</strong></summary>

Use

$$
\beta_{g'}=\frac{dg'}{dg}\beta_g.
$$

Since

$$
\frac{dg'}{dg}=1+3a g^2+O(g^4),
$$

we get

$$
\beta_{g'}=(1+3a g^2)(b_1g^3+b_2g^5+\cdots)
=b_1g^3+O(g^5).
$$

Also $g=g'+O(g'^3)$, so $g^3=g'^3+O(g'^5)$. Therefore

$$
\beta_{g'}=b_1g'^3+O(g'^5).
$$

The leading coefficient is invariant under this finite analytic redefinition.

</details>

### Exercise 2: Finite redefinition in an observable

An observable is

$$
\mathcal O=g^2+(L+B)g^4+O(g^6),
$$

where $L$ is a logarithmic term and $B$ is a finite constant. Let

$$
g'=g+a g^3+O(g^5).
$$

Find the coefficient multiplying $g'^4$.

<details><summary><strong>Solution</strong></summary>

Invert the coupling relation:

$$
g=g'-a g'^3+O(g'^5).
$$

Then

$$
g^2=g'^2-2a g'^4+O(g'^6),
\qquad
g^4=g'^4+O(g'^6).
$$

Therefore

$$
\mathcal O=g'^2+(L+B-2a)g'^4+O(g'^6).
$$

The finite coefficient shifts by $-2a$. The observable remains the same after the coupling is re-expressed.

</details>

### Exercise 3: MS versus modified MS

Explain why subtracting $1/\bar\epsilon$ instead of $1/\epsilon$ is a finite scheme change.

<details><summary><strong>Solution</strong></summary>

The difference is

$$
\frac{1}{\bar\epsilon}-\frac{1}{\epsilon}
=-\gamma_E+\log(4\pi).
$$

This is finite as $\epsilon\to0$. Therefore, subtracting $1/\bar\epsilon$ instead of $1/\epsilon$ removes the same pole plus a specific finite constant. That finite constant changes the definition of the renormalized parameter. Hence $\overline{\mathrm{MS}}$ differs from MS by a finite scheme change.

</details>

### Exercise 4: Why heavy fields need matching in mass-independent schemes

In one sentence, why does a mass-independent scheme usually require explicit EFT matching at a heavy threshold?

<details><summary><strong>Solution</strong></summary>

Because the renormalization constants and beta functions in a mass-independent scheme do not know by themselves that $\mu$ has crossed below a heavy mass $M$, so the heavy field must be removed by matching to an EFT with different degrees of freedom.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on counterterms and renormalization.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," "Renormalization and Symmetry," and "Asymptotic Freedom."
- Mark Srednicki, *Quantum Field Theory*, especially sections on other renormalization schemes, the renormalization group, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters on renormalized perturbation theory, renormalizability, and the renormalization group.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, and Vol. II, chapter 18.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on renormalization, RG equations, and critical behavior.

## Version history

- 2026-06-17: First polished draft. Compared MS, $\overline{\mathrm{MS}}$, momentum subtraction, on-shell schemes, finite renormalizations, beta-function transformations, threshold matching, and scheme-dependence diagnostics.
