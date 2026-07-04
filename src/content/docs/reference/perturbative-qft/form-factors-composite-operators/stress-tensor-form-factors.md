---
title: "Stress-Tensor Form Factors"
description: "How stress-tensor matrix elements are decomposed into gravitational form factors, constrained by translation Ward identities, and interpreted as momentum, spin, and mechanical response."
sidebar:
  label: "Stress-Tensor Form Factors"
  order: 5
level: Graduate
status: "Polished draft"
source: "Weinberg, Vols. I–II; Coleman current-algebra and LSZ lectures; Srednicki, scattering and conserved-current chapters; standard gravitational-form-factor literature."
topics:
  - stress tensor
  - form factors
  - Ward identities
  - gravitational form factors
  - composite operators
canonicalTopics:
  - stress-tensor-form-factors
  - gravitational-form-factors
  - stress-tensor-ward-identity
  - energy-momentum-matrix-elements
researchStatus:
  established:
    - "Lorentz decomposition, momentum normalization, and conservation constraints for stress-tensor matrix elements are standard consequences of Poincaré symmetry and local QFT."
  active:
    - "Nonperturbative stress-tensor form factors of hadrons, pressure and shear distributions, lattice extractions, trace-anomaly decompositions, and gravitational responses of strongly coupled systems remain active research areas."
---

## Summary

A **stress-tensor form factor** is a matrix element of the energy-momentum tensor between physical states. It is often called a gravitational form factor because a weak background metric couples to the stress tensor through

$$
\Delta S
=
\frac12\int d^4x\,h_{\mu\nu}(x)T^{\mu\nu}(x),
$$

so $T^{\mu\nu}$ is the local source for gravitational probes. The name does not require dynamical quantum gravity. It simply means that the stress tensor measures the response of a QFT to spacetime geometry.

For equal-mass spin-zero one-particle states, a symmetric conserved stress tensor has the standard decomposition

$$
\langle p'|T^{\mu\nu}(0)|p\rangle
=
2P^\mu P^\nu A(t)
+
\frac12\left(q^\mu q^\nu-\eta^{\mu\nu}q^2\right)D(t),
$$

where

$$
P=\frac{p'+p}{2},
\qquad
q=p'-p,
\qquad
t=q^2.
$$

The normalization of the total momentum fixes

$$
A(0)=1.
$$

The second form factor, often called the **D-term**, is not fixed by total momentum conservation. It encodes mechanical response information such as pressure and shear distributions in systems where such an interpretation is available.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 55rem;">

![A stress-tensor insertion between one-particle states is constrained by Lorentz covariance and the translation Ward identity into gravitational form factors](/figures/perturbative-qft/stress-tensor-form-factors.svg)

<figcaption>

A stress-tensor insertion between on-shell states is constrained by Lorentz covariance and the translation Ward identity. For spin zero, the conserved total stress tensor has two independent scalar form factors, commonly denoted $A(t)$ and $D(t)$. For spin $1/2$, a third form factor $B(t)$ appears and participates in the angular-momentum sum rule.

</figcaption>
</figure>

Stress-tensor form factors are the natural continuation of current form factors. A conserved vector current measures charge flow. The stress tensor measures energy, momentum, angular momentum, pressure, shear, trace response, and coupling to background geometry.

## Prerequisites

You should know [Composite Operator Insertions](/perturbative-qft/form-factors-composite-operators/composite-operator-insertions/), [Form Factors](/perturbative-qft/form-factors-composite-operators/form-factors/), [Current Matrix Elements](/perturbative-qft/form-factors-composite-operators/current-matrix-elements/), [Operator Renormalization Preview](/perturbative-qft/form-factors-composite-operators/operator-renormalization-preview/), [External Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), and [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/).

For later uses, it helps to know [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/), [Anomalous Dimensions Preview](/perturbative-qft/form-factors-composite-operators/anomalous-dimensions-preview/), and the stress-tensor pages in the Foundations, symmetry, and CFT volumes.

## Core idea

The stress tensor is the Noether current for spacetime translations. Its conserved charge is the four-momentum,

$$
P^\nu_{\rm op}
=
\int d^3\mathbf x\,T^{0\nu}(t,\mathbf x),
$$

where the subscript reminds us that this is an operator, not the average momentum $P=(p'+p)/2$ used in form-factor decompositions.

Because $T^{\mu\nu}$ is a local operator with two Lorentz indices, its matrix element is much richer than a scalar density or vector current matrix element. But it is not arbitrary. Poincaré symmetry, conservation, on-shell conditions, parity, time reversal, and the choice of spin of the external states reduce the matrix element to a finite set of scalar functions of $t=q^2$.

Those scalar functions are stress-tensor form factors. They are sometimes called **gravitational form factors** because a graviton, or more modestly a weak background metric perturbation, couples through $T^{\mu\nu}$. In perturbative QFT, this means that a stress-tensor insertion can be treated as a special two-index source vertex. In nonperturbative hadron physics, the same matrix elements encode momentum fractions, angular momentum fractions, and mechanical distributions.

A useful analogy is:

| Probe | Local operator | What the form factors measure |
|---|---|---|
| scalar source | scalar density $\mathcal O$ | response to mass or coupling deformation |
| vector source | current $J^\mu$ | charge, magnetic moment, current distribution |
| metric source | stress tensor $T^{\mu\nu}$ | energy, momentum, spin, pressure, shear, trace response |

The stress tensor is special because the total stress tensor is tied to exact spacetime symmetry. That exact symmetry fixes some form factors at zero momentum transfer.

## Setup and conventions

We use the site-wide perturbative QFT conventions and covariant one-particle normalization. The new notation on this page is

$$
P=\frac{p'+p}{2},
\qquad
q=p'-p,
\qquad
t=q^2.
$$

The external particles are taken on shell with equal mass unless stated otherwise:

$$
p^2=p'^2=m^2.
$$

Therefore

$$
P\cdot q=\frac{p'^2-p^2}{2}=0,
\qquad
P^2=m^2-\frac{t}{4}.
$$

The stress tensor used for form factors should be symmetric and conserved when it is the total physical stress tensor:

$$
\partial_\mu T^{\mu\nu}=0.
$$

The word “total” matters. In QCD, for example, one often splits the total stress tensor into quark and gluon pieces. Those pieces are useful, but they need not be separately conserved and their form-factor decompositions can include additional terms that vanish only in the sum.

## Which stress tensor?

There are several stress tensors in QFT, and they differ by improvement terms or by terms that vanish by the equations of motion. The most useful stress tensor for form factors is the one obtained by varying the action with respect to a background metric:

$$
T^{\mu\nu}(x)
=
\frac{2}{\sqrt{-g}}\frac{\delta S}{\delta g_{\mu\nu}(x)}\bigg|_{g=\eta},
$$

up to the sign convention chosen for varying $g_{\mu\nu}$ versus $g^{\mu\nu}$. The precise sign is convention-dependent; the physical coupling to $h_{\mu\nu}$ fixes the rule.

This metric stress tensor is naturally symmetric. It is the local operator coupled to a weak gravitational background. In a flat-space perturbative calculation, one can equivalently introduce $h_{\mu\nu}$ as a source and read off stress-tensor insertion vertices.

Improvement ambiguities remain. For a scalar theory, one may shift

$$
T^{\mu\nu}
\longmapsto
T^{\mu\nu}
+
\left(\eta^{\mu\nu}\Box-\partial^\mu\partial^\nu\right)B,
$$

where $B$ is a local scalar operator. The added term is identically conserved. It does not change the total four-momentum, but it can change off-forward stress-tensor form factors, especially the D-term and trace-related decompositions. This is not a paradox. A local density can be improved without changing its integrated conserved charge.

## Translation Ward identity

Translation invariance gives the conservation equation inside correlation functions, up to contact terms. In a matrix element between momentum eigenstates, conservation gives

$$
q_\mu\langle p'|T^{\mu\nu}(0)|p\rangle=0
$$

for the conserved total stress tensor and equal-mass on-shell states.

At zero momentum transfer, the integrated charge relation fixes the normalization. Since

$$
P^\nu_{\rm op}|p\rangle=p^\nu|p\rangle,
$$

we have

$$
\langle p'|P^\nu_{\rm op}|p\rangle
=
p^\nu\langle p'|p\rangle.
$$

Using translation invariance to integrate $T^{0\nu}$ over space gives the same statement as the forward matrix element of $T^{\mu\nu}$. In compact form, the forward total stress-tensor matrix element is normalized by

$$
\langle p|T^{\mu\nu}(0)|p\rangle
=
2p^\mu p^\nu
$$

with the usual covariant state-normalization delta functions suppressed. This fixes the leading momentum form factor $A(0)=1$ in the spin-zero decomposition.

The structure is the stress-tensor analogue of charge normalization for a conserved current:

$$
F_{\rm charge}(0)=Q,
\qquad
A_{\rm momentum}(0)=1.
$$

## Spin-zero decomposition

For equal-mass spin-zero states, the most general symmetric rank-two tensor built from $P^\mu$, $q^\mu$, and $\eta^{\mu\nu}$ can be reduced using $P\cdot q=0$ and conservation. A convenient conserved decomposition is

$$
\langle p'|T^{\mu\nu}(0)|p\rangle
=
2P^\mu P^\nu A(t)
+
\frac12\left(q^\mu q^\nu-\eta^{\mu\nu}q^2\right)D(t).
$$

The first term is the momentum-carrying structure. In the forward limit $q\to0$,

$$
\langle p|T^{\mu\nu}(0)|p\rangle
=
2p^\mu p^\nu A(0),
$$

so total momentum conservation requires $A(0)=1$.

The second structure is automatically conserved:

$$
q_\mu\left(q^\mu q^\nu-\eta^{\mu\nu}q^2\right)=0.
$$

It vanishes in the strict forward limit as a tensor structure, so $D(0)$ is not fixed by total momentum. In systems with a rest-frame spatial-density interpretation, $D(t)$ is related to internal stress distributions such as pressure and shear. That interpretation is subtle in a relativistic quantum theory, but the invariant form factor is well defined.

Different communities place different numerical factors in the definition of $D(t)$. Some absorb the factor $1/2$, use $C(t)$ instead of $D(t)$, or define a dimensionless D-term by dividing by a mass. The decomposition above is the convention used on this page; comparisons to hadron-structure literature require checking factors carefully.

## Spin-one-half decomposition

For a spin-$1/2$ particle, the stress-tensor matrix element contains spinor bilinears. A standard parity-even decomposition for the conserved total stress tensor is

$$
\begin{aligned}
\langle p',s'|T^{\mu\nu}(0)|p,s\rangle
=&\ \overline u(p',s')
\Bigg[
A(t)\gamma^{(\mu}P^{\nu)}
+B(t)\frac{P^{(\mu}i\sigma^{\nu)\rho}q_\rho}{2m}
\\
&\hspace{3.5em}
+D(t)\frac{q^\mu q^\nu-\eta^{\mu\nu}q^2}{4m}
\Bigg]
u(p,s),
\end{aligned}
$$

where

$$
X^{(\mu}Y^{\nu)}
\equiv
\frac12\left(X^\mu Y^\nu+X^\nu Y^\mu\right).
$$

The form factor $A(t)$ again controls the momentum normalization. The form factor $B(t)$ is sometimes called the gravitomagnetic form factor. The combination

$$
J=\frac12\left[A(0)+B(0)\right]
$$

is the total angular momentum carried by the constituents described by the chosen stress tensor. For the full one-particle state of spin $1/2$, $J=1/2$ and $A(0)=1$, so the total conserved stress tensor has

$$
B(0)=0.
$$

For separately defined quark and gluon contributions in QCD, $A_q(0)$ and $A_g(0)$ are momentum fractions, while $[A_q(0)+B_q(0)]/2$ and $[A_g(0)+B_g(0)]/2$ are angular-momentum contributions. Only the total sum is fixed by the total Poincaré generators.

A nonconserved partial stress tensor can also contain a term proportional to $m\eta^{\mu\nu}$, often written with a form factor $\overline C(t)$. Conservation of the total stress tensor removes this term in the sum over all sectors.

## Stress-tensor insertion vertices

Perturbatively, a stress-tensor form factor is computed like any other composite-operator form factor:

1. Couple the theory to a weak background metric or source $h_{\mu\nu}$.
2. Differentiate with respect to $h_{\mu\nu}$ to obtain a $T^{\mu\nu}$ insertion.
3. Compute the Green function with that insertion.
4. Renormalize the operator if needed.
5. Amputate external particle legs and take the LSZ on-shell limit.
6. Decompose the resulting matrix element into tensor structures.

For a real scalar field with minimal flat-space stress tensor,

$$
T^{\mu\nu}
=
\partial^\mu\phi\,\partial^\nu\phi
-
\eta^{\mu\nu}\left(
\frac12\partial_\rho\phi\,\partial^\rho\phi
-
\frac12m^2\phi^2
\right),
$$

the tree-level two-scalar insertion vertex follows from the derivatives in $T^{\mu\nu}$. It contains momenta because derivatives acting on external fields bring down momenta. If one adds the improvement term, the insertion vertex changes by a term proportional to

$$
q^\mu q^\nu-\eta^{\mu\nu}q^2.
$$

That is why improvement affects the D-type form factor but not the total momentum normalization.

## Trace, scale symmetry, and anomalies

The trace of the stress tensor is another important local operator:

$$
T^\mu_{\ \mu}.
$$

In a classically scale-invariant theory, one may be able to improve the stress tensor so that the classical trace vanishes. Quantum mechanically, renormalization can generate a trace anomaly. Schematically,

$$
T^\mu_{\ \mu}
\sim
\sum_i \beta_i\mathcal O_i
+
\text{mass terms}
+
\text{curvature terms in curved space}.
$$

This formula is intentionally schematic here. The detailed trace-anomaly story belongs to the symmetry, renormalization, CFT, and curved-spacetime volumes. The perturbative lesson is narrower: the trace is a composite operator, it can mix with other scalar operators, and its matrix elements are form factors.

For massive states, stress-tensor form factors interpolate between momentum normalization, trace response, and mechanical response. In QCD this is one route into the decomposition of hadron mass and the role of the trace anomaly. That subject is physical and nonperturbative; the perturbative page should only supply the operator and form-factor grammar.

## Mechanical interpretation and its limits

The D-term is often discussed as encoding pressure and shear forces inside an extended state. In a rest frame and under additional assumptions, one can Fourier transform spatial components of the stress tensor and write a static stress distribution of the schematic form

$$
T^{ij}(\mathbf r)
=
\left(\frac{r^ir^j}{r^2}-\frac13\delta^{ij}\right)s(r)
+
\delta^{ij}p(r),
$$

where $s(r)$ is a shear distribution and $p(r)$ is a pressure distribution.

This picture is useful, but it has caveats. Relativistic localization is subtle, boosts do not preserve naive spatial densities, and different definitions of spatial distributions can differ by relativistic corrections or improvement terms. The invariant object is the matrix element and its form factors. Spatial-density language is an interpretation layered on top of that invariant data.

A safe hierarchy is:

```txt
matrix element: fundamental QFT object;
form factors: invariant decomposition of that object;
spatial densities: useful representation with additional assumptions.
```

## Common pitfalls

**Confusing the total stress tensor with a partial stress tensor.** The total stress tensor is conserved and generates translations. Quark and gluon pieces, or matter and gauge pieces, can be useful but are usually scheme-dependent and not separately conserved.

**Forgetting improvement ambiguities.** An improvement term can change local densities and D-type form factors without changing total momentum. That is not a contradiction.

**Thinking “gravitational form factor” requires quantum gravity.** It does not. The phrase means matrix elements of $T^{\mu\nu}$, equivalently response to a background metric source.

**Treating pressure distributions as directly measured classical densities.** The invariant QFT object is the stress-tensor matrix element. Density interpretations depend on frame, localization prescription, and sometimes improvement choices.

**Dropping contact terms in Ward identities.** Translation Ward identities in correlation functions include contact terms when the stress tensor collides with other operators. Those terms are essential for normalization and operator transformations.

**Using a nonconserved decomposition for a conserved tensor.** If the total stress tensor is conserved between equal-mass on-shell states, terms proportional to $\eta^{\mu\nu}$ not arranged into conserved structures must vanish or combine appropriately.

## Relations to other pages

- [Composite Operator Insertions](/perturbative-qft/form-factors-composite-operators/composite-operator-insertions/) explains how $T^{\mu\nu}$ appears as a special local insertion vertex.
- [Form Factors](/perturbative-qft/form-factors-composite-operators/form-factors/) gives the general LSZ extraction logic for operator matrix elements.
- [Current Matrix Elements](/perturbative-qft/form-factors-composite-operators/current-matrix-elements/) is the vector-current analogue of this page.
- [Operator Renormalization Preview](/perturbative-qft/form-factors-composite-operators/operator-renormalization-preview/) explains why composite stress tensors and their sub-operators require renormalization.
- [Anomalous Dimensions Preview](/perturbative-qft/form-factors-composite-operators/anomalous-dimensions-preview/) explains scale dependence of operator matrix elements.
- [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/) gives a simpler current-conservation Ward identity before the two-index stress-tensor case.
- The CFT stress-tensor pages explain how $T^{\mu\nu}$ becomes the generator of conformal transformations and how its correlators encode central charges.

## Research status

- **Established:** Stress-tensor matrix elements, Lorentz decompositions, translation Ward identities, improvement terms, and zero-momentum normalization are textbook consequences of QFT and Poincaré symmetry.
- **Active:** Hadronic gravitational form factors, D-term extraction, pressure and shear distributions, trace-anomaly matrix elements, lattice stress-tensor renormalization, and stress-tensor form factors in strongly coupled systems remain active research areas.
- **Convention-dependent:** The names and numerical normalizations of $A(t)$, $B(t)$, $C(t)$, $D(t)$, and $\overline C(t)$ vary across communities. Always compare decompositions before comparing plots or quoted values.

## Exercises

### Exercise 1: Conservation of the spin-zero decomposition

Show that

$$
\langle p'|T^{\mu\nu}(0)|p\rangle
=
2P^\mu P^\nu A(t)
+
\frac12(q^\mu q^\nu-\eta^{\mu\nu}q^2)D(t)
$$

satisfies $q_\mu\langle p'|T^{\mu\nu}|p\rangle=0$ for equal-mass external states.

<details>
<summary><strong>Solution</strong></summary>

For equal masses,

$$
P\cdot q
=
\frac{p'+p}{2}\cdot(p'-p)
=
\frac{p'^2-p^2}{2}=0.
$$

Therefore

$$
q_\mu(2P^\mu P^\nu A)=2(P\cdot q)P^\nu A=0.
$$

The second structure is identically transverse:

$$
q_\mu(q^\mu q^\nu-\eta^{\mu\nu}q^2)
=
q^2q^\nu-q^\nu q^2=0.
$$

Thus the full decomposition is conserved.

</details>

### Exercise 2: Momentum normalization fixes A(0)

Use the forward matrix element of the total stress tensor to show that the spin-zero form factor obeys $A(0)=1$.

<details>
<summary><strong>Solution</strong></summary>

The four-momentum operator is

$$
P^\nu_{\rm op}
=
\int d^3\mathbf x\,T^{0\nu}(t,\mathbf x).
$$

On a one-particle state,

$$
P^\nu_{\rm op}|p\rangle=p^\nu|p\rangle.
$$

Thus the forward matrix element of the total stress tensor must be

$$
\langle p|T^{\mu\nu}(0)|p\rangle=2p^\mu p^\nu,
$$

with the common covariant-normalization delta functions suppressed. In the spin-zero decomposition, $q=0$ gives $P=p$ and removes the D-term structure:

$$
\langle p|T^{\mu\nu}(0)|p\rangle=2p^\mu p^\nu A(0).
$$

Comparison gives

$$
A(0)=1.
$$

</details>

### Exercise 3: Improvement shifts the D-type structure

Let

$$
\Delta T^{\mu\nu}
=
(\eta^{\mu\nu}\Box-\partial^\mu\partial^\nu)B
$$

for a scalar operator $B$. Show that its matrix element is proportional to $q^\mu q^\nu-\eta^{\mu\nu}q^2$.

<details>
<summary><strong>Solution</strong></summary>

Translation invariance gives

$$
\langle p'|B(x)|p\rangle
=
e^{iq\cdot x}\langle p'|B(0)|p\rangle,
\qquad q=p'-p.
$$

Each derivative acting on the matrix element produces a factor proportional to $iq^\mu$. Therefore

$$
\langle p'|\Delta T^{\mu\nu}(0)|p\rangle
\propto
q^\mu q^\nu-\eta^{\mu\nu}q^2,
$$

up to the scalar matrix element $\langle p'|B(0)|p\rangle$ and sign conventions from differentiating the phase. This is exactly the transverse D-type tensor structure, so the improvement shifts the D-term but not the forward momentum normalization.

</details>

### Exercise 4: Why a pure η term is forbidden for the conserved total tensor

Suppose one tried to add $\eta^{\mu\nu}F(t)$ to the equal-mass spin-zero decomposition of the conserved total stress tensor. Show that conservation forces $F(t)=0$ away from special kinematic points unless the term is combined with another structure.

<details>
<summary><strong>Solution</strong></summary>

Contract with $q_\mu$:

$$
q_\mu\eta^{\mu\nu}F(t)=q^\nu F(t).
$$

For a generic off-forward matrix element, $q^\nu$ is not zero. Therefore conservation requires

$$
F(t)=0.
$$

The allowed D-type term is not a pure $\eta^{\mu\nu}$ term. It appears in the transverse combination

$$
q^\mu q^\nu-\eta^{\mu\nu}q^2,
$$

whose contraction with $q_\mu$ vanishes identically.

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chapters on symmetries, conserved currents, scattering, and matrix elements; Vol. II for stress tensors, effective actions, and operator methods.
- S. Coleman, *Lectures on Quantum Field Theory*, chapters on symmetries, currents, current algebra, LSZ, and Green functions.
- M. Srednicki, *Quantum Field Theory*, chapters on continuous symmetries, conserved currents, LSZ, and form-factor-adjacent scattering tools.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on unitarity, currents, QCD, and energy-momentum tensor applications.
- M. V. Polyakov and P. Schweitzer, “Forces inside hadrons: pressure, surface tension, mechanical radius, and all that,” *International Journal of Modern Physics A* **33** (2018), for a hadron-physics review of stress-tensor form factors and the D-term.
- X. Ji, “Gauge-Invariant Decomposition of Nucleon Spin,” *Physical Review Letters* **78** (1997), for the connection between stress-tensor form factors and angular momentum in QCD.

## Version history

- **2026-06-13:** Initial polished draft. Added spin-zero and spin-$1/2$ decompositions, translation Ward-identity normalization, improvement-term caveats, mechanical-interpretation cautions, solved exercises, and a compact TikZ figure.
