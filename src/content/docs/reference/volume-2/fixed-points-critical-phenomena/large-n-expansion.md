---
title: "Large-N Expansion"
description: "Explains the large-N expansion for O(N) vector models and its use as a controlled fixed-dimension method for critical phenomena."
sidebar:
  label: "Large-N Expansion"
  order: 9
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Coleman 1985, 1/N; Moshe and Zinn-Justin 2003; Zinn-Justin 2021; Polyakov 1987; Cardy 1996; Sachdev 2011."
topics:
  - large-N expansion
  - O(N) vector model
  - saddle point
  - Hubbard–Stratonovich field
  - critical exponents
  - vector models
canonicalTopics:
  - large-n-expansion
  - o-n-model
  - critical-phenomena
  - saddle-point-methods
researchStatus:
  established:
    - "The large-N expansion is a standard controlled expansion for vector models, with the N to infinity limit governed by a saddle point and corrections organized in powers of 1/N."
  active:
    - "Large-N vector models remain active in conformal bootstrap, higher-spin duality, deconfined and fractionalized criticality, finite-temperature dynamics, and mixed large-N/epsilon expansions."
---

## Summary

The **large-$N$ expansion** is a controlled approximation in which the number of field components is taken large. For the $O(N)$ vector model, one studies

$$
\phi^a(x),
\qquad a=1,\ldots,N,
$$

and expands universal quantities in powers of $1/N$:

$$
\Delta_i(N)=\Delta_i^{(\infty)}+
\frac{\Delta_i^{(1)}}{N}+
\frac{\Delta_i^{(2)}}{N^2}+\cdots.
$$

Unlike the epsilon expansion, the large-$N$ expansion can be performed directly in fixed dimension, especially in $2<d<4$. At $N=\infty$, the $O(N)$ model becomes a saddle-point problem for a collective auxiliary field. Fluctuations around that saddle are suppressed by powers of $1/N$.

For the critical $O(N)$ model in $2<d<4$, the $N=\infty$ exponents include

$$
\eta=0,
\qquad
\nu=\frac{1}{d-2}.
$$

In three dimensions this gives $\nu=1$ at $N=\infty$, with corrections such as

$$
\eta=\frac{8}{3\pi^2N}+O\left(\frac{1}{N^2}\right),
\qquad
\nu=1-\frac{32}{3\pi^2N}+O\left(\frac{1}{N^2}\right).
$$

These formulas are not magic numerology. They come from a systematic saddle-point expansion of a many-field path integral.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 55rem;">

![Large-N vector model map from N components to auxiliary field, saddle point, 1 over N fluctuations, and critical data](/figures/renormalization-rg-eft/large-n-vector-model-saddle.svg)

<figcaption>

In the $O(N)$ vector model, the $N$ field components can be traded for a collective auxiliary field. After the vector fields are integrated out, the effective action is proportional to $N$, so the $N\to\infty$ limit is a saddle point and fluctuations are organized by powers of $1/N$.

</figcaption>
</figure>

:::note[One sentence to remember]
The large-$N$ expansion turns the critical $O(N)$ model into a saddle-point problem for collective fields, then computes corrections as loops weighted by $1/N$.
:::

## Prerequisites

You should know [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/), and [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/).

It is also helpful to know Gaussian functional integrals, one-loop determinants, and the saddle-point method. The main new idea is not a hard integral; it is the bookkeeping that makes $1/N$ the small parameter.

## Core idea

A theory with many field components can simplify when the number of components is large. The $O(N)$ model has $N$ scalar fields, and every closed loop of $\phi^a$ indices can produce a factor of $N$. If the interaction is scaled appropriately, the path integral takes the schematic form

$$
Z=\int \mathcal D\sigma\,\exp\left[-N\Gamma[\sigma]\right].
$$

When $N$ is large, the integral is dominated by a saddle point:

$$
\frac{\delta\Gamma}{\delta\sigma}=0.
$$

Corrections come from fluctuations around the saddle. A Gaussian fluctuation determinant contributes $O(N^0)$ to $\log Z$, cubic and higher vertices generate further powers, and connected corrections are organized by powers of $1/N$.

This is the same general reason that thermodynamic systems simplify when the number of degrees of freedom is large: collective fluctuations become relatively small. The difference is that here the large parameter is the number of internal field components rather than the physical volume.

## Setup and conventions

We use the Euclidean $O(N)$ vector model

$$
S=\int d^d x\left[
\frac12\partial_\mu\phi^a\partial^\mu\phi^a
+\frac12 r\,\phi^a\phi^a
+\frac{\lambda}{4N}(\phi^a\phi^a)^2
\right],
\qquad a=1,\ldots,N.
$$

The factor $1/N$ in the quartic coupling is not cosmetic. It keeps the interaction energy extensive in $N$ when typical configurations satisfy $\phi^a\phi^a=O(N)$.

The symmetry is

$$
\phi^a\mapsto R^a{}_b\phi^b,
\qquad R\in O(N).
$$

We will focus on the critical theory in

$$
2<d<4.
$$

In this range the interacting $O(N)$ fixed point is nontrivial, and the large-$N$ expansion gives a controlled fixed-dimension method complementary to the epsilon expansion.

## Auxiliary field representation

The key move is to replace the quartic interaction by an auxiliary field. Schematically, with the integration contour chosen to reproduce the stable Euclidean quartic interaction, one may write

$$
S[\phi,\sigma]
=\int d^d x\left[
\frac12\partial_\mu\phi^a\partial^\mu\phi^a
+\frac12(r+\sigma)\phi^a\phi^a
-\frac{N}{4\lambda}\sigma^2
\right].
$$

The sign and contour of $\sigma$ are bookkeeping details of the Euclidean Hubbard–Stratonovich transformation. What matters physically is that eliminating $\sigma$ reproduces the original quartic interaction, while keeping $\sigma$ makes the $N$ counting transparent.

Because the $\phi^a$ fields appear quadratically, they can be integrated out:

$$
Z=\int \mathcal D\sigma\,
\exp\left[-S_{\mathrm{eff}}[\sigma]\right],
$$

with

$$
S_{\mathrm{eff}}[\sigma]
=N\left[
-\int d^d x\,\frac{\sigma^2}{4\lambda}
+\frac12\operatorname{Tr}\log(-\partial^2+r+\sigma)
\right].
$$

The whole effective action is proportional to $N$. Therefore

$$
N\to\infty
\quad\Longrightarrow\quad
\text{saddle point for }\sigma.
$$

This is the heart of the large-$N$ method.

## The saddle point and gap equation

Assume a translation-invariant saddle

$$
\sigma(x)=\sigma_*.
$$

Define

$$
m^2\equiv r+\sigma_*.
$$

The saddle equation takes the schematic form

$$
\frac{\sigma_*}{\lambda}
=\int\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+m^2},
$$

with regulator-dependent terms understood. Equivalently, after subtracting the critical value $r_c$, one obtains a finite relation between the distance from criticality and the physical mass scale $m$.

For $2<d<4$, the nonanalytic small-$m$ part of the momentum integral behaves as

$$
\int\frac{d^d p}{(2\pi)^d}
\left(\frac{1}{p^2+m^2}-\frac{1}{p^2}\right)
\propto m^{d-2}.
$$

Therefore, near the critical point,

$$
t\equiv r-r_c \propto m^{d-2},
$$

where $t$ is the temperature-like scaling variable. Since the correlation length is

$$
\xi\sim m^{-1},
$$

we find

$$
\xi\sim t^{-1/(d-2)}.
$$

Thus at $N=\infty$,

$$
\nu_\infty=\frac{1}{d-2}.
$$

This derivation is one of the cleanest examples of how a critical exponent emerges from a saddle-point equation.

## Scaling dimensions at N equals infinity

At the critical saddle, the fundamental field is effectively Gaussian at leading order in $1/N$. Its two-point function behaves as

$$
\langle \phi^a(x)\phi^b(0)\rangle
\propto \frac{\delta^{ab}}{|x|^{d-2}}.
$$

Therefore

$$
\Delta_\phi^{(\infty)}=\frac{d-2}{2},
\qquad
\eta_\infty=0.
$$

The singlet operator $\phi^a\phi^a$ is subtler. At the interacting critical point, the operator that tunes the temperature is represented by the collective field $\sigma$, not by the naive Gaussian composite alone. At $N=\infty$ its scaling dimension is

$$
\Delta_{\phi^2}^{(\infty)}=2.
$$

The corresponding thermal RG eigenvalue is

$$
y_t=d-\Delta_{\phi^2}^{(\infty)}=d-2,
$$

again giving

$$
\nu_\infty=\frac{1}{y_t}=\frac{1}{d-2}.
$$

In $d=3$ this gives

$$
\Delta_\phi^{(\infty)}=\frac12,
\qquad
\Delta_{\phi^2}^{(\infty)}=2,
\qquad
\nu_\infty=1.
$$

These values are not mean-field values in the usual $d=3$ sense. They are the $N=\infty$ values of the interacting vector-model fixed point.

## Fluctuations and 1 over N counting

Write

$$
\sigma(x)=\sigma_*+\frac{1}{\sqrt N}s(x).
$$

Expanding the effective action gives

$$
S_{\mathrm{eff}}[\sigma]
=N\Gamma[\sigma_*]
+\frac12\int sK s
+\frac{1}{\sqrt N}\int V_3 s^3
+\frac{1}{N}\int V_4 s^4+\cdots.
$$

The saddle term is $O(N)$. The Gaussian fluctuation action is $O(1)$. Interaction vertices of the $s$ field are suppressed by powers of $1/\sqrt N$.

This produces the expansion

$$
\mathcal O(N)=\mathcal O_\infty+
\frac{\mathcal O_1}{N}+
\frac{\mathcal O_2}{N^2}+\cdots.
$$

For example, in three dimensions,

$$
\eta=\frac{8}{3\pi^2N}+O\left(\frac{1}{N^2}\right),
$$

and

$$
\nu=1-\frac{32}{3\pi^2N}+O\left(\frac{1}{N^2}\right).
$$

The precise derivation of these coefficients requires computing the propagator of the $s$ field and its contribution to the $\phi$ self-energy and singlet scaling dimension. The important structural lesson is already visible: the expansion parameter is not the quartic coupling but the inverse number of components.

## Vector large-N versus matrix large-N

The large-$N$ expansion in the $O(N)$ vector model is not the same as the large-$N$ expansion of $SU(N)$ gauge theory.

| Feature | Vector model | Matrix or gauge large-$N$ |
|---|---|---|
| basic field | $\phi^a$ with one index | matrices or adjoint fields with two indices |
| dominant diagrams | bubble and saddle diagrams | planar diagrams |
| expansion parameter | $1/N$ | often $1/N^2$ for closed orientable surfaces |
| collective variables | singlets such as $\phi^a\phi^a$ | traces, Wilson loops, master fields |
| common use | critical phenomena, vector CFTs | QCD-like theories, string expansions, holography |

Both methods exploit many internal degrees of freedom, but their combinatorics and physical interpretations differ. In vector models, the large-$N$ limit is often close to a self-consistent mean-field theory for a singlet collective field. In matrix models and gauge theories, the leading expansion is organized by topology of ribbon diagrams.

## Relation to the epsilon expansion

The epsilon expansion and large-$N$ expansion are complementary.

| Method | Small parameter | Strength | Weakness |
|---|---|---|---|
| epsilon expansion | $\varepsilon=4-d$ | controlled near the upper critical dimension | extrapolation needed for $d=3$ |
| large-$N$ expansion | $1/N$ | works directly in fixed $d$ | extrapolation needed for small $N$ |

For the $O(N)$ model, both methods describe the same Wilson–Fisher universality classes in their overlapping domain. They can be combined in a double expansion where both $\varepsilon$ and $1/N$ are small. Agreement in overlapping limits is a powerful consistency check.

The large-$N$ expansion also gives intuition unavailable from low-order epsilon expansion. It emphasizes collective fields, self-consistent masses, gap equations, and singlet operator dynamics. These ideas reappear in many-body physics, gauge theory, holography, and statistical field theory.

## How the method is used in practice

A typical large-$N$ calculation follows this pattern:

| Step | Operation | Output |
|---:|---|---|
| 1 | Scale couplings with $N$ | action extensive in $N$ |
| 2 | Introduce an auxiliary or collective field | quartic terms become quadratic in vectors |
| 3 | Integrate out the $N$ vector components | effective action $N\Gamma[\sigma]$ |
| 4 | Solve the saddle equation | leading gap equation and phase structure |
| 5 | Expand around the saddle | propagators and vertices for collective fluctuations |
| 6 | Compute $1/N$ diagrams | anomalous dimensions and exponent corrections |

This method is especially useful for distinguishing universal from nonuniversal information. Regulator-dependent pieces of the gap equation set the critical value $r_c$, while nonanalytic long-distance pieces determine universal scaling.

## Why the N equals infinity theory is still interacting

At first glance, $\eta_\infty=0$ may suggest that the $N=\infty$ critical theory is just Gaussian. That is misleading.

The fundamental field two-point function has Gaussian scaling, but singlet observables and constraints are nontrivial. The critical theory is not simply $N$ independent free scalars with arbitrary mass. The mass is fixed self-consistently by the saddle equation, and the singlet sector contains the collective $\sigma$ field with nontrivial scaling.

A sharp way to say it is:

$$
\text{the vector two-point function looks free at }N=\infty,
\quad
\text{but the singlet critical theory is not trivial.}
$$

At finite but large $N$, the collective field mediates interactions and produces anomalous dimensions.

## Common pitfalls

**Forgetting the coupling scaling.** If the quartic coupling is not scaled as $1/N$, the large-$N$ limit is not finite in the desired way.

**Confusing vector and matrix large-$N$.** The $O(N)$ vector model is dominated by singlet collective-field saddles, not by planar ribbon diagrams.

**Assuming $N=\infty$ means ordinary mean-field theory.** In $2<d<4$, the $N=\infty$ critical exponents differ from Landau mean-field exponents. For example, $\nu_\infty=1/(d-2)$, not $1/2$.

**Using large-$N$ formulas blindly at $N=1$.** The expansion parameter is $1/N$. For small $N$, large-$N$ estimates may be qualitatively useful but are not parametrically controlled.

**Ignoring singlet operators.** The most important physics of the vector model often lives in the singlet sector, especially the operator related to $\phi^a\phi^a$ and the auxiliary field $\sigma$.

**Treating the auxiliary field as fake.** The auxiliary field begins as a calculational device, but at the critical point it encodes genuine collective scaling behavior.

## Relations to other pages

This page complements [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/). The epsilon expansion is controlled by proximity to the upper critical dimension; the large-$N$ expansion is controlled by many field components.

It builds on [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), and [Universality Classes](/renormalization-rg-eft/fixed-points-critical-phenomena/universality-classes/). It also prepares for later pages on the [Operator Product Expansion](/renormalization-rg-eft/local-operators-and-ope/ope-and-short-distance-expansion/), effective actions, and model calculations in scalar field theory.

The conceptual toolkit overlaps with [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/) and [Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/), because the large-$N$ method is a clean example of replacing microscopic fields by collective effective variables.

## Research status

The large-$N$ expansion of vector models is established. It is a standard analytic method for critical phenomena and a benchmark for other approaches.

The active research life of large $N$ is broad. Vector models at large $N$ are central in modern conformal field theory, higher-spin holography, finite-temperature and finite-density dynamics, tensor and matrix generalizations, and critical phenomena with gauge fields or constraints. Large-$N$ methods are also used as controlled laboratories for questions that are otherwise hard: operator mixing, thermalization, emergent gauge structure, nonperturbative saddle points, and the relation between perturbative expansions and exact constraints.

The status to keep in mind is balanced: large $N$ is a controlled expansion when $N$ is parametrically large, a useful organizing principle for moderate $N$, and only a heuristic guide for very small $N$ unless supported by other methods.

## Exercises

### Exercise 1: Why the quartic coupling scales as 1 over N

Assume a typical configuration has

$$
\phi^a\phi^a=O(N).
$$

Show that the interaction

$$
\frac{\lambda}{4N}(\phi^a\phi^a)^2
$$

is $O(N)$, while $\lambda(\phi^a\phi^a)^2/4$ would be $O(N^2)$.

<details><summary><strong>Solution</strong></summary>

If $\phi^a\phi^a=O(N)$, then

$$
(\phi^a\phi^a)^2=O(N^2).
$$

Therefore

$$
\frac{\lambda}{4N}(\phi^a\phi^a)^2=O(N),
$$

whereas

$$
\frac{\lambda}{4}(\phi^a\phi^a)^2=O(N^2).
$$

The kinetic and mass terms are sums over $N$ components and are also $O(N)$. The $1/N$ scaling of the quartic term therefore keeps all pieces of the action comparable in the large-$N$ limit.

</details>

### Exercise 2: Saddle equation from the effective action

Starting from

$$
S_{\mathrm{eff}}[\sigma]
=N\left[
-\int d^d x\,\frac{\sigma^2}{4\lambda}
+\frac12\operatorname{Tr}\log(-\partial^2+r+\sigma)
\right],
$$

assume $\sigma(x)=\sigma_*$ is constant. Show that the saddle equation has the form

$$
\frac{\sigma_*}{\lambda}
=\int\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+r+\sigma_*}.
$$

<details><summary><strong>Solution</strong></summary>

For constant $\sigma_*$, vary the effective action with respect to $\sigma_*$. The first term gives

$$
\frac{\delta}{\delta\sigma_*}\left(-\frac{\sigma_*^2}{4\lambda}\right)
=-\frac{\sigma_*}{2\lambda}.
$$

The derivative of the trace log uses

$$
\delta\operatorname{Tr}\log A=\operatorname{Tr}(A^{-1}\delta A).
$$

Here $A=-\partial^2+r+\sigma_*$ and $\delta A=\delta\sigma_*$. Per unit volume, this gives

$$
\frac12\int\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+r+\sigma_*}.
$$

Setting the variation to zero gives

$$
-\frac{\sigma_*}{2\lambda}
+\frac12\int\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+r+\sigma_*}=0,
$$

or

$$
\frac{\sigma_*}{\lambda}
=\int\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+r+\sigma_*}.
$$

</details>

### Exercise 3: Correlation length exponent at N equals infinity

Assume that after subtracting the critical value, the saddle equation gives

$$
t\equiv r-r_c\propto m^{d-2},
$$

where $m$ is the inverse correlation length. Derive $\nu_\infty=1/(d-2)$.

<details><summary><strong>Solution</strong></summary>

The correlation length is

$$
\xi\sim m^{-1}.
$$

The saddle equation says

$$
t\propto m^{d-2},
$$

so

$$
m\propto t^{1/(d-2)}.
$$

Therefore

$$
\xi\sim m^{-1}\propto t^{-1/(d-2)}.
$$

By definition,

$$
\xi\sim t^{-\nu},
$$

so

$$
\nu_\infty=\frac{1}{d-2}.
$$

</details>

### Exercise 4: Large-N control versus small-N extrapolation

Explain why a result of the form

$$
\eta=\frac{8}{3\pi^2N}+O\left(\frac{1}{N^2}\right)
$$

is controlled for $N\gg1$ but not automatically precise for $N=1$.

<details><summary><strong>Solution</strong></summary>

The expansion parameter is $1/N$. When $N\gg1$, each successive term is parametrically smaller than the previous one, assuming the coefficients are not anomalously large. Then truncating the series has a controlled error of the next order.

For $N=1$, the expansion parameter is not small. The omitted terms of order $1/N^2$, $1/N^3$, and so on are not parametrically suppressed. The leading term may still give useful intuition, but it is not a precision prediction without additional evidence, resummation, or comparison with other methods.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\varepsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Sidney Coleman, *Aspects of Symmetry*, especially the lectures on $1/N$ and related nonperturbative methods.
- Moshe Moshe and Jean Zinn-Justin, "Quantum Field Theory in the Large $N$ Limit: A Review," *Physics Reports* **385** (2003) 69–228.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on large-$N$ methods and critical exponents.
- Alexander M. Polyakov, *Gauge Fields and Strings*, especially the large-$N$ and sigma-model chapters.
- John Cardy, *Scaling and Renormalization in Statistical Physics*.
- Subir Sachdev, *Quantum Phase Transitions*, for large-$N$ methods in quantum critical systems.

## Version history

- 2026-06-17: First polished draft. Introduced the large-$N$ expansion for $O(N)$ vector models, including auxiliary-field formulation, saddle equation, $N=\infty$ exponents, $1/N$ corrections, and comparison with the epsilon expansion.
