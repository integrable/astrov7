---
title: "Large-N Vector Models"
description: "Derive the large-N saddle-point method for O(N) vector models and explain gap equations, collective fields, and 1/N corrections."
sidebar:
  label: "Large-N Vector Models"
  order: 1
level: Advanced
status: "Polished draft"
source: "Zinn-Justin, ch. 18; Mariño, ch. 6; Shifman, ch. 9."
topics:
  - large-N expansion
  - O(N) vector models
  - saddle point
  - Hubbard-Stratonovich transformation
  - gap equation
  - nonlinear sigma model
  - critical phenomena
canonicalTopics:
  - nonperturbative-qft
  - large-n-methods
  - vector-models
  - o-n-model
  - saddle-point-method
researchStatus:
  established:
    - "The leading large-N solution of O(N) vector models is a standard controlled saddle-point calculation, and 1/N corrections are systematically computable."
  active:
    - "Precision comparisons among large-N, epsilon expansion, bootstrap, lattice, and finite-N data remain model-dependent, especially near small N and near marginal dimensions."
---

## Summary

A **large-N vector model** is a QFT whose elementary field has $N$ components, for example

$$
\phi^i(x),\qquad i=1,\ldots,N,
$$

with an $O(N)$ symmetry. The large-N limit keeps suitable $O(N)$-invariant combinations finite, such as

$$
\rho(x)=\frac{1}{N}\phi^i(x)\phi^i(x),
$$

and scales the interactions so that the Euclidean action is of order $N$. Then the path integral can often be rewritten as

$$
Z=\int D\rho\,D\sigma\,e^{-N S_{\rm eff}[\rho,\sigma]},
$$

so that the leading large-N answer is found by solving saddle-point equations.

The remarkable feature is that this is not just mean-field handwaving. In many vector models the original $N$ fields can be integrated out exactly once auxiliary singlet fields are introduced. The large parameter $N$ then genuinely plays the role of $1/\hbar$ for the collective-field path integral.

This page derives the basic mechanism for $O(N)$ scalar models, explains the gap equation, interprets the leading two-point function, and shows how the $1/N$ expansion arises from fluctuations of the collective fields.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A schematic pipeline for the large-N vector model: N-component fields, collective singlet rho, Lagrange multiplier sigma, integration over the vector fields, saddle equation, and 1/N corrections.](/figures/nonperturbative-qft/large-n-vector-model-saddle.svg)

<figcaption>

In a vector model, the large index is carried by $\phi^i$. The singlet $\rho=\phi^2/N$ and its multiplier $\sigma$ expose the $N S_{\rm eff}$ structure. The leading answer is a saddle; fluctuations of $\rho$ and $\sigma$ generate the $1/N$ expansion.

</figcaption>
</figure>

The model is a laboratory for a big nonperturbative lesson: **a theory that looks like many interacting fields can become a saddle-point problem for a few collective variables.**

## Prerequisites

Read [Large-N Methods](/nonperturbative-qft/large-n-methods/), [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/), [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/), and [Correlation Length](/nonperturbative-qft/order-parameters-diagnostics/correlation-length/) before this page.

It is also helpful to know [Chiral Symmetry Breaking](/nonperturbative-qft/strongly-coupled-gauge-theories/chiral-symmetry-breaking/) and [Mass Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/), because vector models show how symmetry realization and mass generation can change in nonperturbative limits.

## Core idea

The central trick is to separate two kinds of variables:

| Variable | Role |
|---|---|
| $\phi^i$ | The $N$ microscopic vector components. |
| $\rho=\phi^2/N$ | The $O(N)$-invariant collective field. |
| $\sigma$ | A Lagrange multiplier or Hubbard–Stratonovich field enforcing the relation between $\rho$ and $\phi^2/N$. |

The $O(N)$ symmetry implies that many observables of interest are singlets. At large $N$, singlet quantities self-average: their connected fluctuations are suppressed by powers of $1/N$. This makes the collective field nearly classical in the large-N limit.

There are two common versions.

First, in the **linear $O(N)$ model**, the action contains a potential $N U(\phi^2/N)$. The field $\rho$ is introduced to rewrite the interaction as a collective-field problem.

Second, in the **nonlinear sigma model**, one imposes a constraint such as $\phi^2=N/g$ or $\sigma^a\sigma^a=1$. A Lagrange multiplier enforces the constraint, and the saddle-point value of the multiplier can generate a mass.

Both versions teach the same structural lesson:

$$
\text{many vector components}
\quad\longrightarrow\quad
\text{few singlet collective fields}
\quad\longrightarrow\quad
\text{saddle plus }1/N\text{ corrections}.
$$

## Setup and conventions

We work in Euclidean signature with an ultraviolet cutoff $\Lambda$. Consider an $O(N)$-invariant scalar field $\phi^i(x)$ in $d$ Euclidean dimensions with action

$$
S[\phi]
=
\int d^d x\left[
\frac12\partial_\mu\phi^i\partial_\mu\phi^i
+N U\!\left(\frac{\phi^i\phi^i}{N}\right)
\right].
$$

The factor of $N$ in front of $U$ is essential. For example,

$$
U(\rho)=\frac{r}{2}\rho+\frac{u}{4!}\rho^2
$$

gives

$$
S[\phi]
=
\int d^d x\left[
\frac12(\partial\phi^i)^2
+\frac{r}{2}\phi^i\phi^i
+\frac{u}{4!N}(\phi^i\phi^i)^2
\right].
$$

The quartic interaction is scaled as $1/N$ so that the total interaction energy remains of order $N$ when $\phi^i\phi^i$ is of order $N$.

We define the collective field

$$
\rho(x)=\frac{\phi^i(x)\phi^i(x)}{N}
$$

and introduce a multiplier field $\sigma(x)$ enforcing this relation. A convenient formal representation is

$$
1=\int D\rho\,D\sigma\,
\exp\left[-\frac12\int d^d x\,\sigma(x)\left(\phi^i\phi^i-N\rho\right)\right],
$$

with an appropriate contour for $\sigma$. The contour detail matters for rigor and convergence, but the saddle equations below are the practical working formulas.

After inserting this identity, the action becomes quadratic in $\phi^i$:

$$
S[\phi,\rho,\sigma]
=
\int d^d x\left[
\frac12\phi^i(-\partial^2+\sigma)\phi^i
+N U(\rho)-\frac{N}{2}\sigma\rho
\right].
$$

Integrating out the $N$ real scalar fields gives

$$
Z=\int D\rho\,D\sigma\,e^{-N S_{\rm eff}[\rho,\sigma]},
$$

where

$$
S_{\rm eff}[\rho,\sigma]
=
\int d^d x\left[U(\rho)-\frac12\sigma\rho\right]
+\frac12\operatorname{Tr}\log(-\partial^2+\sigma).
$$

The trace is over spacetime modes, not over $O(N)$ indices; the $O(N)$ trace has already produced the overall factor $N$.

## Saddle-point equations

The leading large-N answer comes from stationary points of $S_{\rm eff}$. Translation-invariant phases are described by constant saddle values

$$
\rho(x)=\rho_0,
\qquad
\sigma(x)=m^2.
$$

The saddle equations are

$$
\frac{\delta S_{\rm eff}}{\delta \rho}=0,
\qquad
\frac{\delta S_{\rm eff}}{\delta \sigma}=0.
$$

They give

$$
U'(\rho_0)=\frac12 m^2,
$$

and

$$
\rho_0
=
\int^{\Lambda}\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+m^2}.
$$

Equivalently, for the quartic potential above,

$$
m^2=r+\frac{u}{6}\rho_0,
$$

so the gap equation is

$$
m^2
=
r+\frac{u}{6}\int^{\Lambda}\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+m^2}.
$$

This is the large-N analogue of a self-consistent mass equation. The bare parameter $r$ must be tuned against the cutoff dependence to reach a critical point. The physical mass $m$ is the inverse correlation length in the symmetric phase:

$$
\xi=\frac{1}{m}.
$$

At the critical point, the renormalized mass vanishes. Away from criticality, the gap equation relates the physical scale $m$ to microscopic parameters.

## Leading correlation functions

At leading order in $1/N$, the vector field propagator is the propagator of a scalar with the self-consistent mass:

$$
\langle \phi^i(p)\phi^j(-p)\rangle
=
\frac{\delta^{ij}}{p^2+m^2}+O\!\left(\frac1N\right).
$$

This formula looks free, but the mass $m$ is not an arbitrary input. It is determined by the saddle equation. That is why the result can contain nonperturbative information even though the leading propagator is Gaussian.

The singlet operator $\phi^2$ is more interesting. It is represented by fluctuations of the collective fields $\rho$ and $\sigma$. To study it, expand

$$
\rho=\rho_0+\frac{1}{\sqrt N}\eta,
\qquad
\sigma=m^2+\frac{1}{\sqrt N}s.
$$

Then

$$
N S_{\rm eff}[\rho,\sigma]
=
N S_{\rm eff}[\rho_0,m^2]
+\frac12\int \eta K_{\eta\eta}\eta
+\frac12\int s K_{ss}s
+\int \eta K_{\eta s}s
+O(N^{-1/2}),
$$

where the kernels are determined by derivatives of $U$ and by one-loop bubble integrals of the massive $\phi^i$ fields. The schematic bubble integral is

$$
\Pi(p)=\int\frac{d^d q}{(2\pi)^d}
\frac{1}{(q^2+m^2)((q+p)^2+m^2)}.
$$

Thus the $1/N$ expansion of singlet correlators is an expansion in collective-field propagators and vertices. The leading vector propagator is simple; the singlet sector stores the interactions.

## What becomes classical at large N?

The large-N vector model has two related classical limits.

First, $S_{\rm eff}$ is multiplied by $N$, so the collective-field path integral is controlled by stationary phase. This is a literal saddle-point limit.

Second, normalized singlet observables factorize. For an $O(N)$ singlet observable $\mathcal O$, connected fluctuations are often suppressed:

$$
\langle \mathcal O_1\mathcal O_2\rangle_c
=O\!\left(\frac1N\right)
$$

when the normalization is chosen so that each one-point function is $O(1)$. This is the sense in which the singlet sector becomes classical.

This does not mean that every original component $\phi^i$ becomes classical. The fields $\phi^i$ are still quantum fields. What becomes sharply determined is the collective singlet saddle.

## Relation to critical phenomena

The $O(N)$ vector model is one of the main examples in the theory of critical phenomena. In $2<d<4$, the quartic theory has an interacting Wilson–Fisher fixed point. The large-N expansion gives access to critical exponents and operator dimensions directly in dimension $d$, rather than only through the epsilon expansion.

At leading order, the anomalous dimension of the vector field is small:

$$
\eta=O\!\left(\frac1N\right).
$$

The correlation-length exponent has a nontrivial large-N value. In the usual $O(N)$ universality class for $2<d<4$,

$$
\nu=\frac{1}{d-2}+O\!\left(\frac1N\right).
$$

This formula is already beyond ordinary mean-field theory. For example, in $d=3$ it gives $\nu=1+O(1/N)$, not the mean-field value $1/2$.

The point is subtle but important: large $N$ is not the same approximation as mean-field theory. Mean-field theory suppresses fluctuations by assumption. Large $N$ suppresses certain fluctuations because the singlet effective action carries a large coefficient.

## Nonlinear sigma model and mass generation

The nonlinear $O(N)$ sigma model in two dimensions is an especially instructive large-N laboratory. Its fields can be described as maps into a sphere, or equivalently as $N$ real fields constrained by

$$
\sigma^a\sigma^a=1.
$$

After rescaling, one often writes an action of the form

$$
S=\frac12\int d^2x\left[
\partial_\mu\sigma^a\partial_\mu\sigma^a
-i\alpha\left(\sigma^a\sigma^a-\frac{N}{t_0}\right)
\right],
$$

where $t_0$ is held fixed as $N\to\infty$. Integrating out the $N$ fields produces

$$
S_{\rm eff}[\alpha]
=\frac{N}{2}\operatorname{Tr}\log(-\partial^2-i\alpha)
+\frac{iN}{2t_0}\int d^2x\,\alpha.
$$

A translation-invariant saddle has

$$
i\alpha=m^2.
$$

The gap equation becomes schematically

$$
\frac{1}{t_0}
=
\int^\Lambda\frac{d^2p}{(2\pi)^2}\frac{1}{p^2+m^2}
=
\frac{1}{4\pi}\log\frac{\Lambda^2}{m^2}+\cdots.
$$

Therefore

$$
m
\sim
\Lambda\,e^{-2\pi/t_0}
$$

up to convention-dependent constants. This mass is invisible to any finite-order expansion in $t_0$ around $t_0=0$. The large-N solution therefore exhibits dimensional transmutation and a mass gap in a controlled setting.

This is one of the best examples of why “nonperturbative” does not mean “incalculable.” The mass is nonanalytic in the coupling, but the large-N saddle computes it.

## No Goldstone bosons in two dimensions

The two-dimensional nonlinear sigma model also illustrates a conceptual trap. Perturbatively, solving the constraint near a chosen point on the sphere seems to produce $N-1$ massless Goldstone-like fields. That picture suggests spontaneous breaking of $O(N)$.

But continuous global symmetries cannot be spontaneously broken in two-dimensional relativistic QFT under the usual assumptions. The large-N solution respects this: all $N$ fields acquire the same mass $m$, and the full $O(N)$ symmetry is restored in the quantum theory.

Thus the large-N answer corrects the perturbative expansion in a qualitative way. Perturbation theory around a chosen point on the target sphere misses the true infrared physics.

## The 1/N expansion as diagrams

After the saddle is found, the $1/N$ expansion is generated by expanding the collective-field action. There are two equivalent viewpoints.

In the original $\phi^i$ variables, the leading large-N diagrams are chains of bubbles. Each closed $\phi$ loop gives a factor of $N$, while each quartic vertex gives a factor of $1/N$. The leading diagrams maximize the number of index loops for a given number of vertices.

In the collective-field variables, the leading saddle gives the self-consistent mass, and fluctuations of $\sigma$ or $\rho$ mediate interactions. Vertices among collective fields carry explicit powers of $1/\sqrt N$.

The second viewpoint is often cleaner, because it makes the saddle structure explicit. The first viewpoint is useful for seeing why the same expansion appears in ordinary Feynman diagrams.

A schematic scaling rule is

$$
\text{connected singlet }k\text{-point function}
\sim
N^{1-k}
$$

when singlet operators are normalized by $1/N$. For unnormalized singlets, the powers shift accordingly.

## Vector models versus gauge large N

Vector large $N$ is not the same as the large-$N_c$ limit of Yang–Mills theory.

| Feature | Vector models | Matrix and gauge theories |
|---|---|---|
| Basic index | One index $i=1,\ldots,N$ | Two indices, e.g. $M^i{}_j$ or color flow. |
| Typical invariant | $\phi^i\phi^i$ | $\operatorname{tr}M^k$, Wilson loops, single-trace operators. |
| Leading diagrams | Bubble chains and cactus diagrams. | Planar diagrams. |
| Geometry of expansion | Collective-field saddle. | Surfaces organized by genus. |
| Common control variable | $1/N$. | $1/N^2$ for many pure single-trace observables, with $1/N$ effects from boundaries, quarks, or baryons. |
| String interpretation | Limited and model-dependent. | Much more direct through planar surfaces and flux tubes. |

This is why the chapter starts here but does not stop here. Vector models teach the saddle mechanism; gauge theories add topology.

## Common pitfalls

**Forgetting the coupling scaling.** If the quartic coupling is not scaled as $1/N$, the large-N limit is not the model described here. The saddle equations and diagram counting change.

**Calling the leading answer “free.”** The leading vector propagator is Gaussian, but its mass and critical behavior are determined self-consistently. The singlet sector remains interacting through collective fluctuations.

**Confusing $\phi^i$ with $\rho$.** The vector field transforms nontrivially under $O(N)$. The collective field $\rho=\phi^2/N$ is a singlet. Their correlators have different large-N scalings.

**Ignoring the cutoff and renormalization.** The gap equation contains divergent integrals. Physical statements require tuning, renormalization, or comparison of cutoff-independent quantities.

**Trusting the $N=\infty$ answer too literally at small $N$.** The large-N expansion may be qualitatively powerful at $N=3$, $N=2$, or $N=1$, but this is not automatic. It must be checked against other methods or data.

**Assuming all nonperturbative effects are captured by the leading saddle.** Some effects can be exponentially small in $N$, invisible in the $1/N$ expansion. Large $N$ can create its own nonperturbative sectors.

## Relations to other pages

This page is the technical entry point for [Large-N Methods](/nonperturbative-qft/large-n-methods/). It supplies the saddle and gap-equation logic that later pages reuse for large-N sigma models, the $CP^{N-1}$ model, matrix models, and large-N QCD.

It is closely related to [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/) and [Saddle Points at Large N](/nonperturbative-qft/large-n-methods/saddle-points-at-large-n/). The large parameter is $N$ rather than $1/g^2$ or $1/\hbar$. It also relates to [Mass Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/) because the saddle mass controls exponential decay of correlators.

Continue next to [Large-N Sigma Models](/nonperturbative-qft/large-n-methods/large-n-sigma-models/), where the auxiliary-field saddle is adapted to constrained target spaces and dynamical mass generation. Then read [Matrix Large-N Limits](/nonperturbative-qft/large-n-methods/matrix-large-n-limits/), where the large-N saddle variable becomes an eigenvalue density rather than a singlet field.

For gauge-theory motivation, compare [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) and [QCD as a Strongly Coupled QFT](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-as-strongly-coupled-qft/). For critical phenomena and bootstrap comparisons, this page will later connect to the CFT and Bootstrap volume.

[Large-N Factorization](/nonperturbative-qft/large-n-methods/large-n-factorization/) compares this vector-model self-averaging with the $1/N^2$ factorization of normalized single-trace operators in matrix and gauge theories.

## Research status

Established:

- The leading large-N solution of $O(N)$ vector models is a standard saddle-point calculation.
- The $1/N$ expansion is a systematic expansion around the collective-field saddle.
- In $2<d<4$, large-N methods give controlled critical exponents and correlators for the $O(N)$ universality class.
- In two-dimensional nonlinear sigma models, the large-N saddle gives a mass gap and restores the global symmetry, illustrating nonperturbative mass generation.

Active or delicate:

- Quantitative extrapolation to small $N$ requires comparison with epsilon expansion, conformal bootstrap, lattice simulations, exact solutions, or experiment.
- The convergence or asymptotic nature of the $1/N$ expansion is model-dependent.
- Nonperturbative effects of order $e^{-cN}$ are not visible in any finite order of the $1/N$ expansion.
- Large-N vector models have modern roles in higher-spin duality, critical CFTs, and finite-temperature dynamics, but those developments belong to later specialized pages.

## Exercises

1. **Derive the saddle equations.** Starting from

   $$
   S_{\rm eff}[\rho,\sigma]
   =
   \int d^d x\left[U(\rho)-\frac12\sigma\rho\right]
   +\frac12\operatorname{Tr}\log(-\partial^2+\sigma),
   $$

   assume constant $\rho$ and $\sigma=m^2$. Show that

   $$
   U'(\rho_0)=\frac12m^2,
   \qquad
   \rho_0=\int^\Lambda\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+m^2}.
   $$

   <details><summary><strong>Solution</strong></summary>

   Varying with respect to $\rho$ gives

   $$
   \delta_\rho S_{\rm eff}
   =\int d^d x\left[U'(\rho)-\frac12\sigma\right]\delta\rho,
   $$

   hence $U'(\rho_0)=\sigma/2=m^2/2$. Varying with respect to $\sigma$ gives two terms:

   $$
   \delta_\sigma S_{\rm eff}
   =-\frac12\int d^d x\,\rho\,\delta\sigma
   +\frac12\operatorname{Tr}\left[(-\partial^2+\sigma)^{-1}\delta\sigma\right].
   $$

   For constant $\sigma=m^2$, the diagonal Green function is

   $$
   \langle x|(-\partial^2+m^2)^{-1}|x\rangle
   =\int^\Lambda\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+m^2}.
   $$

   Setting the variation to zero gives the stated equation.

   </details>

2. **Find the quartic gap equation.** For

   $$
   U(\rho)=\frac{r}{2}\rho+\frac{u}{4!}\rho^2,
   $$

   derive

   $$
   m^2=r+\frac{u}{6}\int^\Lambda\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+m^2}.
   $$

   <details><summary><strong>Solution</strong></summary>

   The derivative of the potential is

   $$
   U'(\rho)=\frac{r}{2}+\frac{u}{12}\rho.
   $$

   The first saddle equation gives

   $$
   \frac{m^2}{2}=\frac{r}{2}+\frac{u}{12}\rho_0,
   $$

   hence

   $$
   m^2=r+\frac{u}{6}\rho_0.
   $$

   Substituting the second saddle equation for $\rho_0$ gives the result.

   </details>

3. **Evaluate the two-dimensional logarithm.** Show that for $m\ll \Lambda$,

   $$
   \int^{\Lambda}\frac{d^2p}{(2\pi)^2}\frac{1}{p^2+m^2}
   =\frac{1}{4\pi}\log\frac{\Lambda^2}{m^2}+O(1).
   $$

   <details><summary><strong>Solution</strong></summary>

   Using polar coordinates with a circular cutoff,

   $$
   \int^\Lambda\frac{d^2p}{(2\pi)^2}\frac{1}{p^2+m^2}
   =\frac{1}{2\pi}\int_0^\Lambda dp\,\frac{p}{p^2+m^2}.
   $$

   The integral is

   $$
   \frac{1}{4\pi}\log\frac{\Lambda^2+m^2}{m^2}
   =
   \frac{1}{4\pi}\log\frac{\Lambda^2}{m^2}+O\!\left(\frac{m^2}{\Lambda^2}\right).
   $$

   Cutoff shape changes the additive constant, not the leading logarithm.

   </details>

4. **Explain the nonperturbative scale.** If

   $$
   \frac{1}{t_0}=\frac{1}{4\pi}\log\frac{\Lambda^2}{m^2},
   $$

   solve for $m$ and explain why no finite Taylor series in $t_0$ can produce this dependence.

   <details><summary><strong>Solution</strong></summary>

   Rearranging gives

   $$
   \log\frac{\Lambda^2}{m^2}=\frac{4\pi}{t_0},
   $$

   so

   $$
   m=\Lambda e^{-2\pi/t_0}.
   $$

   The function $e^{-2\pi/t_0}$ has an essential singularity at $t_0=0$. Its formal Taylor expansion around $t_0=0$ has all coefficients equal to zero, so it cannot be generated at any finite order in perturbation theory.

   </details>

## References

- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 16 and 18, especially the treatment of $O(N)$ vector models for large $N$.
- M. Mariño, *Instantons and Large N*, ch. 6, for the $O(N)$ and $CP^{N-1}$ sigma models at large $N$.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, ch. 9, especially the appendix solving the $O(N)$ model at large $N$.
- A. M. Polyakov, *Gauge Fields and Strings*, ch. 8, for large-N sigma-model and gauge-theory intuition.
- S. Coleman, *Aspects of Symmetry*, for classic physical discussion of large-N ideas and symmetry realization.

## Version history

- **2026-06-27:** Added handoff links to the saddle-points-at-large-N and CP N-minus-one pages.
- **2026-06-27:** Added handoff link to large-N factorization.
- **2026-06-27:** Added handoff links to large-N sigma models and matrix large-N limits.
- **2026-06-27:** Initial polished page deriving the large-N vector-model saddle, gap equation, mass generation example, and $1/N$ expansion structure.
