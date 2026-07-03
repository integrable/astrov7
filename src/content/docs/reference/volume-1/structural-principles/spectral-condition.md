---
title: "Spectral Condition"
description: "Positive energy, the forward light cone in momentum space, vacuum stability, mass gaps, spectral support of correlators, and the Källén–Lehmann connection."
sidebar:
  label: "Spectral Condition"
  order: 3
---

## Summary

The **spectral condition** is the positive-energy axiom of relativistic QFT. It says that the joint spectrum of the translation generators lies in the closed forward light cone:

$$
\boxed{\operatorname{Spec}(P^\mu)\subset \overline V_+,
\qquad
\overline V_+=\{p^\mu: p^0\ge 0,\ p^2\ge 0\}.}
$$

With qft.org's mostly-minus metric,

$$
p^2=(p^0)^2-\mathbf p^2.
$$

So the spectral condition says two things at once:

$$
\boxed{p^0\ge 0}
\qquad\text{and}\qquad
\boxed{(p^0)^2\ge \mathbf p^2.}
$$

The first is **positive energy**. The second excludes physical states whose total four-momentum is spacelike. The vacuum is the bottom of the spectrum,

$$
P^\mu|0\rangle=0,
$$

after subtracting the flat-space vacuum energy from the Hamiltonian. One-particle states live on positive-energy mass shells $p^2=m^2$, and multiparticle states fill continua inside the same forward cone.

<figure class="doc-figure" style="--figure-width: 38rem;">

![The spectral condition as support in the forward light cone](/figures/foundations/spectral-condition-forward-cone.svg)

<figcaption>

The spectral condition places the joint spectrum of the translation generators inside the closed forward light cone $\overline V_+$. The vacuum sits at $P^\mu=0$; massive one-particle states lie on positive-energy mass shells; multiparticle states produce continua above thresholds.

</figcaption>
</figure>

This is one of the quiet structural assumptions behind almost everything else. It is what makes the vacuum stable, what gives Wightman functions their positive-frequency support, what makes the Källén–Lehmann spectral density live at nonnegative invariant mass, and what prevents a Lorentz-invariant quantum theory from having freely available tachyonic states. Weinberg's derivation of the Källén–Lehmann representation makes this concrete: inserting momentum eigenstates into a two-point function gives only intermediate states with $p^2\ge0$ and $p^0>0$, and quantum-mechanical positivity makes the scalar spectral function nonnegative (Weinberg 1995, Vol. I, §10.7). Coleman uses the same positive-energy spectral support in the Goldstone theorem proof, where the spectral representation contains a $\theta(k^0)$ factor and assumes positive energies and no tachyons (Coleman 2019, ch. 43). Srednicki's opening discussion of relativistic wave equations also shows why an unbounded negative-energy spectrum is disastrous: without a ground state, an interacting theory would allow a cascade to ever lower energy (Srednicki 2007, §1).

## Prerequisites

You should know [Poincaré Symmetry](/foundations/symmetry-and-spacetime/poincare-symmetry/), [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/), [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/), [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/), [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/), [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/), [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/), and [Unitarity](/foundations/structural-principles/unitarity/).

:::note[Conventions]
We use the mostly-minus metric,

$$
p^2=(p^0)^2-\mathbf p^2,
$$

and the translation generators are

$$
P^\mu=(H,\mathbf P).
$$

The closed forward light cone is

$$
\overline V_+=\{p: p^0\ge0,\ p^2\ge0\}.
$$

For a local operator $\mathcal O(x)$, we use

$$
\mathcal O(x)=e^{iP\cdot x}\mathcal O(0)e^{-iP\cdot x},
$$

so a vacuum two-point function has the schematic spectral expansion

$$
\langle0|\mathcal O(x)\mathcal O^\dagger(0)|0\rangle
=\sum_n e^{-ip_n\cdot x}|\langle n|\mathcal O^\dagger(0)|0\rangle|^2.
$$
:::

:::note[Assumptions]
The standard spectral condition assumes a flat-spacetime relativistic QFT with Poincaré translations, a positive-norm physical Hilbert space, and a stable vacuum. Gauge-fixed descriptions may introduce unphysical negative-norm or ghost states, so the condition should be imposed on the physical Hilbert space or, equivalently, on gauge-invariant observables. Thermal states, finite-density systems, curved spacetimes, and nonrelativistic theories require modified versions.
:::

## What the condition says

The translation generators commute:

$$
[P^\mu,P^\nu]=0.
$$

When they are represented as self-adjoint operators on a Hilbert space, one can ask for their **joint spectrum**. Informally, this is the set of four-momenta carried by all possible physical states. More precisely, if a simultaneous generalized eigenstate has

$$
P^\mu|\Psi\rangle=p^\mu|\Psi\rangle,
$$

then $p^\mu$ is part of the spectrum.

The spectral condition says that every such $p^\mu$ lies in $\overline V_+$:

$$
p^0\ge0,
\qquad
p^2\ge0.
$$

For one-particle states this reduces to the familiar positive-energy mass shell,

$$
p^0=E_{\mathbf p}=\sqrt{\mathbf p^2+m^2},
\qquad
p^2=m^2.
$$

For multiparticle states, $p^\mu$ is the sum of positive-energy momenta. The sum of future-directed timelike or null vectors is again future-directed timelike or null, so multiparticle states also stay inside $\overline V_+$.

The condition is often stated as an axiom because it is not a consequence of Lorentz covariance alone. Lorentz covariance tells us how spectra transform. It does not tell us which part of a Lorentz orbit the theory chooses. A theory with both positive- and negative-energy states can be formally Lorentz covariant but physically unstable.

## Why the forward cone is Lorentz invariant

The forward light cone is preserved by proper orthochronous Lorentz transformations. If $p\in\overline V_+$, then

$$
p^2\ge0,
\qquad p^0\ge0.
$$

The invariant $p^2$ is unchanged. The sign of $p^0$ is also preserved by transformations continuously connected to the identity. So if a theory has positive energy in one inertial frame, and if the spectrum is contained in $\overline V_+$, then all proper orthochronous inertial observers also see nonnegative energy.

This is why the second inequality matters. It is not enough to say $H\ge0$ in one frame. If a state had spacelike total momentum, $p^2<0$, then a Lorentz boost could make its energy component positive, zero, or negative. Such a state would not have observer-independent positive energy. The spectral condition packages stability and relativity into a single geometric statement.

## Vacuum stability

A stable vacuum is a state of lowest energy. In flat-space QFT we usually choose the zero of energy so that

$$
H|0\rangle=0.
$$

Translation invariance of the vacuum also gives

$$
\mathbf P|0\rangle=0.
$$

Together,

$$
P^\mu|0\rangle=0.
$$

This convention is harmless in nongravitational flat-space QFT: adding a constant to the Hamiltonian does not change energy differences, scattering amplitudes, or correlation functions after the usual normalization. It is not harmless once gravity is dynamical, because vacuum energy gravitates. The Foundations page treats the flat-space structural condition; the cosmological-constant and curved-spacetime issues belong in the spacetime/gravity sections.

The physical content is not that the vacuum energy density is numerically zero in nature. The physical content is that the vacuum is the state below which the theory cannot fall.

That is why negative-energy spectra are fatal. A Hamiltonian unbounded below would allow processes that lower the energy without limit. Srednicki illustrates this in the relativistic wave-equation problem: the Dirac equation has negative-energy solutions in a naive one-particle interpretation, and interactions would let positive-energy electrons radiate and cascade downward unless the interpretation is replaced by the field-theoretic particle-antiparticle picture (Srednicki 2007, §1). In QFT, the physical spectrum is rebuilt so that excitations above the vacuum have nonnegative energy.

## The mass operator

For a Poincaré-invariant theory, the invariant mass-squared operator is

$$
M^2=P_\mu P^\mu=H^2-\mathbf P^2.
$$

The spectral condition implies

$$
M^2\ge0
$$

on physical states. A one-particle state of mass $m$ has

$$
M^2|p,\sigma\rangle=m^2|p,\sigma\rangle.
$$

A massless one-particle state has $M^2=0$ and $p^0=|\mathbf p|$. A massive one-particle state has $M^2=m^2>0$ and $p^0>|\mathbf p|$.

For multiparticle states, $M^2$ is the invariant mass of the whole state, not the sum of individual mass-squared values. For two particles of masses $m_1,m_2$, the continuum begins at

$$
M^2\ge (m_1+m_2)^2
$$

when the particles are at rest in their center-of-momentum frame. This threshold structure is one reason the spectral condition is visible in analytic properties of propagators and scattering amplitudes.

## Mass gap versus spectral condition

The spectral condition is not the same as a **mass gap**.

A theory has a mass gap if the vacuum is isolated from all other physical states by a positive invariant mass scale. Schematically,

$$
\operatorname{Spec}(M^2)
\subset \{0\}\cup[m_{\rm gap}^2,\infty),
\qquad
m_{\rm gap}>0.
$$

A theory can satisfy the spectral condition without a mass gap. QED has massless photons. A theory with Goldstone bosons has massless excitations. A conformal field theory has no particle mass gap at all, but it may still have positive energy in the appropriate quantization.

So the hierarchy is:

$$
\text{mass gap}\quad\Longrightarrow\quad\text{positive excitation scale},
$$

but

$$
\text{spectral condition}\quad\not\Longrightarrow\quad\text{mass gap}.
$$

The spectral condition says where the spectrum can live. A mass gap says how far the non-vacuum spectrum begins from the vacuum.

Coleman's Goldstone-theorem proof makes this distinction explicit. He assumes positive energy, no tachyons, Lorentz invariance, and then considers the stronger condition that all non-vacuum states have invariant mass above a positive threshold. Under that stronger no-massless-particle assumption, a broken continuous symmetry is impossible; therefore spontaneous breaking requires a massless particle (Coleman 2019, ch. 43).

## Free scalar field example

For the free real scalar field, the Hamiltonian after normal ordering is

$$
H=\int\frac{d^3p}{(2\pi)^3}\,E_{\mathbf p}\,a^\dagger(\mathbf p)a(\mathbf p),
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The momentum operator is

$$
\mathbf P=\int\frac{d^3p}{(2\pi)^3}\,\mathbf p\,a^\dagger(\mathbf p)a(\mathbf p).
$$

A one-particle state $a^\dagger(\mathbf p)|0\rangle$ has

$$
P^\mu=(E_{\mathbf p},\mathbf p),
\qquad
P^2=m^2.
$$

An $n$-particle state has total four-momentum

$$
P^\mu=\sum_{a=1}^n(E_{\mathbf p_a},\mathbf p_a).
$$

Since each summand is future-directed timelike, the total is future-directed timelike or null. Therefore the free scalar Fock space obeys the spectral condition.

This calculation is almost too simple, and that is the point. The hard part is not checking the condition for a free field. The hard part is maintaining a positive-energy Hilbert space after interactions, constraints, gauge fixing, renormalization, and nonperturbative effects.

## Wightman functions and positive-frequency support

The spectral condition becomes especially concrete in vacuum correlators. Let $\mathcal O(x)$ be a local operator and consider the Wightman function

$$
W(x)=\langle0|\mathcal O(x)\mathcal O^\dagger(0)|0\rangle.
$$

Insert a complete set of momentum eigenstates:

$$
W(x)=\sum_n
\langle0|\mathcal O(x)|n\rangle
\langle n|\mathcal O^\dagger(0)|0\rangle.
$$

Using translation invariance,

$$
\langle0|\mathcal O(x)|n\rangle
=e^{-ip_n\cdot x}\langle0|\mathcal O(0)|n\rangle.
$$

So

$$
\boxed{
W(x)=\sum_n e^{-ip_n\cdot x}
|\langle n|\mathcal O^\dagger(0)|0\rangle|^2.
}
$$

Every term in the sum has $p_n\in\overline V_+$. Therefore the Fourier transform of $W(x)$ has support only in the forward cone:

$$
\boxed{\widetilde W(p)=0\quad\text{unless}\quad p\in\overline V_+.}
$$

This is the operator-language meaning of “positive frequency.” It is not merely a convention in a free-field mode expansion. It is a structural statement about the spectrum of translations.

For a scalar operator, Lorentz invariance and positivity let one write the support as

$$
\widetilde W(p)=2\pi\,\theta(p^0)\rho(p^2),
\qquad
\rho(\mu^2)\ge0,
$$

with support at nonnegative $\mu^2$. A stable one-particle state contributes a delta function to $\rho$, while multiparticle states contribute continua above thresholds.

## Connection to the Källén–Lehmann representation

The Källén–Lehmann representation is the spectral condition plus completeness plus positivity, written as a formula for two-point functions.

For a scalar operator with nonzero overlap with states of invariant mass $\mu$, the Wightman function can be decomposed as

$$
\langle0|\mathcal O(x)\mathcal O^\dagger(0)|0\rangle
=\int_0^\infty d\mu^2\,\rho(\mu^2)\Delta_+(x;\mu^2),
$$

where

$$
\Delta_+(x;\mu^2)=\int\frac{d^3p}{(2\pi)^3 2E_{\mathbf p}}
 e^{-ip\cdot x},
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+\mu^2}.
$$

The corresponding time-ordered two-point function is

$$
\langle0|T\mathcal O(x)\mathcal O^\dagger(0)|0\rangle
=\int_0^\infty d\mu^2\,\rho(\mu^2)\Delta_F(x;\mu^2),
$$

or in momentum space,

$$
\widetilde G_F(p)
=\int_0^\infty d\mu^2\,
\rho(\mu^2)\frac{i}{p^2-\mu^2+i\epsilon}.
$$

The lower limit $0$ is not decorative. It expresses the absence of tachyonic physical spectral weight. The factor $\theta(p^0)$ in the Wightman function expresses positive energy. The nonnegativity of $\rho$ expresses Hilbert-space positivity.

This is why the spectral representation is a bridge between “states and particles” and “analytic functions.” Poles and cuts in propagators are not arbitrary complex-analysis ornaments; they encode the positive-energy spectrum of physical intermediate states.

## Why tachyons are excluded

A tachyonic mass parameter in a Lagrangian is not automatically a physical tachyon. For example,

$$
V(\phi)=-\frac12\mu^2\phi^2+\frac\lambda4\phi^4
$$

has a negative quadratic term at $\phi=0$, but the correct perturbative vacuum lies near a minimum of $V$, not at the unstable point. Expanding around the stable minimum gives ordinary nonnegative mass-squared excitations, plus possible Goldstone modes if a continuous symmetry is broken.

A physical tachyon would mean a state with

$$
p^2<0.
$$

Then, because $p$ is spacelike, some Lorentz observers would assign that state negative energy. That is incompatible with the spectral condition. In practice, a tachyonic pole in a propagator usually means one of two things:

1. the theory has been expanded around the wrong vacuum, or
2. the proposed theory is unstable.

The spectral condition is imposed on the physical Hilbert space around the true vacuum.

## Energy conditions and Hamiltonian positivity

The spectral condition is a statement about the spectrum of the global translation generators, not a pointwise statement about the stress tensor.

It does **not** say

$$
T^{00}(x)\ge0
$$

as an operator at every point. In quantum field theory, local energy densities can have negative expectation values in some states, subject to additional constraints in specific settings. The spectral condition says instead that the total four-momentum of every physical state is future-directed:

$$
\langle\Psi|P^0|\Psi\rangle\ge0
$$

for normalized states, and more strongly that the joint spectrum of $P^\mu$ lies inside $\overline V_+$.

This distinction matters. A theory can have local fluctuations of energy density while still having a stable vacuum and nonnegative total energy spectrum.

## Gauge-theory caveat

Gauge fixing often enlarges the state space. Covariant gauges introduce longitudinal, timelike, and ghost degrees of freedom. Some of these states do not belong to the physical Hilbert space. Therefore it would be too naive to demand that every state in the gauge-fixed bookkeeping space obey the same positivity properties as physical states.

The structural condition is imposed on gauge-invariant observables and physical states. In BRST language, physical states are cohomology classes:

$$
Q_{\rm BRST}|\psi\rangle=0,
\qquad
|\psi\rangle\sim |\psi\rangle+Q_{\rm BRST}|\chi\rangle.
$$

The physical spectrum is the spectrum of translations acting on that cohomology. Ghosts and negative-norm modes are not physical asymptotic particles.

This is the same moral as in unitarity: gauge-fixed perturbation theory may look unhealthy term by term, but physical gauge-invariant quantities must have positive-norm states, positive-energy support, and unitary evolution.

## Thermal and finite-density states

At nonzero temperature, the theory is no longer organized around the vacuum state $|0\rangle$. Instead one studies a density matrix such as

$$
\rho_T=\frac{e^{-\beta H}}{\operatorname{Tr}e^{-\beta H}}.
$$

The Hamiltonian can still be bounded below, but vacuum Wightman support is replaced by thermal spectral relations. Thermal correlators contain both absorption and emission processes. In frequency space they have positive- and negative-frequency parts related by the KMS condition.

So the spectral condition remains a foundational property of the underlying Hilbert-space representation, but the simple vacuum statement

$$
\widetilde W(p)\quad\text{supported only in}\quad\overline V_+
$$

is no longer the correct description of thermal correlators. The medium has selected a rest frame and can exchange energy with excitations.

## Curved spacetime caveat

In a general curved spacetime there may be no global time-translation symmetry and hence no global Hamiltonian $H$ with a conserved spectrum. There may also be no preferred vacuum. The flat-space spectral condition is therefore not directly available.

The replacement in rigorous curved-spacetime QFT is a **microlocal spectrum condition**, a local statement about the allowed singular directions of correlation functions. That belongs to the Mathematical and Rigorous QFT and QFT in Curved Spacetime sections. For Foundations, the main lesson is simpler: the spectral condition is a flat-spacetime Poincaré statement, not a universal phrase that can be pasted unchanged onto every background.

## Relation to locality and unitarity

The spectral condition is independent from locality and unitarity, but the three are deeply entangled in healthy relativistic QFT.

Locality says spacelike separated observables commute. Unitarity says probabilities are positive and conserved. The spectral condition says the vacuum is stable and physical four-momentum is future-directed.

Together they power many structural theorems:

| Principle | Structural role |
|---|---|
| Locality | forbids superluminal operator influence |
| Unitarity | gives positive norms and probability conservation |
| Spectral condition | gives positive energy and stable vacuum |
| Poincaré symmetry | makes the forward cone and invariant mass meaningful |
| Stable vacuum | gives a reference state for particles and correlators |

Remove any one of these and familiar QFT arguments can fail. For example, the Källén–Lehmann representation uses positivity and the spectrum of momentum eigenstates. Spin-statistics and CPT arguments use locality, Lorentz invariance, positive energy, and Hilbert-space positivity. Analyticity arguments use both causality and spectral support.

## Common pitfalls

### Positive energy is not just choosing positive roots

For a free particle one may write

$$
E=+\sqrt{\mathbf p^2+m^2}.
$$

But in an interacting quantum theory, positive energy is a statement about the whole Hilbert-space representation of translations. It is not just a sign choice in a dispersion relation.

### Vacuum energy can be shifted only in flat nongravitational QFT

In ordinary flat-space QFT, the replacement

$$
H\to H-E_0
$$

sets the vacuum energy to zero. Once gravity is dynamical, the absolute vacuum energy affects curvature. Do not use flat-space convention-setting as an argument about the cosmological constant.

### A tachyonic Lagrangian mass may mean wrong vacuum

A negative quadratic term in a potential often signals instability of the expansion point, not a physical tachyon in the true spectrum. First find the vacuum; then ask whether the physical excitations obey the spectral condition.

### A massless theory can still obey the spectral condition

Massless particles lie on the boundary of the forward cone:

$$
p^2=0,
\qquad p^0>0.
$$

They violate a mass gap, not the spectral condition.

### Gauge ghosts are not physical spectral states

Covariant gauge fixing introduces fields that appear in propagators and loops but not in the physical asymptotic spectrum. Spectral positivity is a statement about physical states and gauge-invariant observables.

## Relation to other topics

- [Poincaré Symmetry](/foundations/symmetry-and-spacetime/poincare-symmetry/) explains the translation generators whose joint spectrum is constrained here.
- [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/) explains positive-energy mass shells and the little-group classification.
- [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/) show the positive-frequency support of vacuum correlators.
- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) develops the Källén–Lehmann formula using the same spectral support.
- [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/) gives the complementary spacetime-side causal condition.
- [Unitarity](/foundations/structural-principles/unitarity/) gives the complementary Hilbert-space positivity and probability-conservation condition.
- [Spin–Statistics Theorem](/foundations/symmetry-and-spacetime/spin-statistics/) and [CPT Theorem](/foundations/symmetry-and-spacetime/cpt-theorem/) rely on the same family of assumptions: locality, Lorentz invariance, positive energy, and a stable vacuum.
- [Reflection Positivity](/foundations/structural-principles/reflection-positivity/) will explain the Euclidean condition that helps reconstruct a positive-energy Lorentzian theory.
- [Cluster Decomposition](/foundations/structural-principles/cluster-decomposition/) will add the independence of distant experiments.

## Research status

- **Established:** The spectral condition is a standard structural assumption in relativistic QFT and one of the Wightman axioms.
- **Textbook-standard consequence:** Positive-energy support of Wightman functions and the Källén–Lehmann representation follow by inserting a complete set of physical momentum eigenstates.
- **Subtle:** Gauge theories, massless particles, infraparticles, confinement, finite temperature, finite density, boundaries, and curved spacetime all require care about what the physical state space and energy-momentum spectrum mean.
- **Out of scope here:** Haag–Ruelle scattering theory, full Wightman reconstruction, microlocal spectrum conditions, algebraic QFT, and nonperturbative mass-gap existence problems.

## Exercises

### Exercise 1: Forward cone under boosts

In 1+1 dimensions, let

$$
p^\mu=(E,p),
\qquad
E\ge |p|.
$$

A boost with velocity $v$ gives

$$
E'=\gamma(E-vp),
\qquad
p'=\gamma(p-vE),
\qquad
\gamma=(1-v^2)^{-1/2}.
$$

Show that $E'\ge0$ for $|v|<1$.

<details>
<summary><strong>Solution</strong></summary>

Since $E\ge |p|$, we have

$$
|vp|\le |v|\,|p|\le |v|E.
$$

Therefore

$$
E-vp\ge E-|vp|\ge E(1-|v|)\ge0.
$$

Since $\gamma>0$, this gives

$$
E'=\gamma(E-vp)\ge0.
$$

Thus a future-directed timelike or null vector remains future-directed under a proper orthochronous boost.

</details>

### Exercise 2: Free scalar Fock spectrum

For a free scalar field, take

$$
P^\mu=\int\frac{d^3p}{(2\pi)^3}\,p^\mu\,a^\dagger(\mathbf p)a(\mathbf p),
\qquad
p^\mu=(E_{\mathbf p},\mathbf p),
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

Show that every finite-particle state has total four-momentum in $\overline V_+$.

<details>
<summary><strong>Solution</strong></summary>

An $n$-particle momentum eigenstate has total four-momentum

$$
P^\mu_{\rm tot}=\sum_{a=1}^n p_a^\mu.
$$

Each $p_a^\mu$ is future-directed timelike for $m>0$, or future-directed null for $m=0$:

$$
p_a^0\ge0,
\qquad
p_a^2=m^2\ge0.
$$

The sum has

$$
P^0_{\rm tot}=\sum_a E_{\mathbf p_a}\ge0.
$$

Also,

$$
|\mathbf P_{\rm tot}|
=\left|\sum_a\mathbf p_a\right|
\le\sum_a|\mathbf p_a|
\le\sum_a E_{\mathbf p_a}=P^0_{\rm tot}.
$$

Therefore

$$
(P^0_{\rm tot})^2-\mathbf P_{\rm tot}^2\ge0,
$$

so $P^\mu_{\rm tot}\in\overline V_+$.

</details>

### Exercise 3: Wightman support

Let

$$
W(x)=\langle0|\mathcal O(x)\mathcal O^\dagger(0)|0\rangle.
$$

Assume a complete basis of momentum eigenstates $|n\rangle$ with $P^\mu|n\rangle=p_n^\mu|n\rangle$ and $p_n\in\overline V_+$. Show that the Fourier transform of $W(x)$ is supported only on $\overline V_+$.

<details>
<summary><strong>Solution</strong></summary>

Insert a complete set:

$$
W(x)=\sum_n\langle0|\mathcal O(x)|n\rangle
\langle n|\mathcal O^\dagger(0)|0\rangle.
$$

Translation invariance gives

$$
\langle0|\mathcal O(x)|n\rangle
=e^{-ip_n\cdot x}\langle0|\mathcal O(0)|n\rangle.
$$

Therefore

$$
W(x)=\sum_n e^{-ip_n\cdot x}
|\langle n|\mathcal O^\dagger(0)|0\rangle|^2.
$$

Fourier transforming with

$$
W(x)=\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot x}\widetilde W(p)
$$

gives, schematically,

$$
\widetilde W(p)=(2\pi)^4\sum_n
|\langle n|\mathcal O^\dagger(0)|0\rangle|^2
\delta^{(4)}(p-p_n).
$$

Since every $p_n$ lies in $\overline V_+$, $\widetilde W(p)$ has support only in $\overline V_+$.

</details>

### Exercise 4: Positivity of the spectral density

For a scalar operator, suppose

$$
\widetilde W(p)=2\pi\theta(p^0)\rho(p^2).
$$

Use the intermediate-state expansion to explain why $\rho(\mu^2)\ge0$.

<details>
<summary><strong>Solution</strong></summary>

From the previous exercise,

$$
\widetilde W(p)=(2\pi)^4\sum_n
|\langle n|\mathcal O^\dagger(0)|0\rangle|^2
\delta^{(4)}(p-p_n).
$$

Each coefficient is an absolute square:

$$
|\langle n|\mathcal O^\dagger(0)|0\rangle|^2\ge0.
$$

For a Lorentz scalar operator in a Lorentz-invariant vacuum, the distribution can be organized by invariant mass $\mu^2=p^2$. The weight at each invariant mass is a sum or integral of nonnegative absolute squares. Hence

$$
\rho(\mu^2)\ge0.
$$

This is Hilbert-space positivity showing up inside the analytic structure of a two-point function.

</details>

### Exercise 5: Spectral condition without a mass gap

Give two examples of theories or situations that can satisfy the spectral condition but do not have a mass gap.

<details>
<summary><strong>Solution</strong></summary>

Examples include:

- QED, because photons are massless and lie on $p^2=0$.
- A theory with spontaneously broken continuous global symmetry, because Goldstone bosons are massless.
- A conformal field theory in flat space, where there is no isolated particle mass gap.

In all cases, the absence of a mass gap means there are excitations arbitrarily close to the light cone or vacuum in the relevant sense. It does not mean that negative-energy or spacelike physical states are allowed.

</details>

### Exercise 6: Why spacelike momentum is dangerous

Let $p^\mu=(E,p)$ in 1+1 dimensions with $p^2=E^2-p^2<0$. Show that there is a boost for which $E'=0$, and boosts beyond it make $E'$ negative.

<details>
<summary><strong>Solution</strong></summary>

For a boost,

$$
E'=\gamma(E-vp).
$$

If $p^2<0$, then $|p|>|E|$. Therefore

$$
v=\frac{E}{p}
$$

has magnitude $|v|<1$, so it is an allowed boost velocity. For this boost,

$$
E'=\gamma(E-vp)=\gamma(E-E)=0.
$$

Changing $v$ slightly past $E/p$ makes $E-vp$ have the opposite sign, so $E'$ becomes negative. Thus a spacelike four-momentum cannot be assigned positive energy in a Lorentz-invariant way.

</details>

## Sources and further reading

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§2.4–2.5, chs. 4–5, and §10.7, for Poincaré generators, particle states, cluster decomposition, causal fields, and the Källén–Lehmann representation.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 1, 3, 15, and 43, for relativistic causality, scalar fields, spectral representations, and the positive-energy assumptions in Goldstone's theorem.
- M. Srednicki, *Quantum Field Theory*, §§1, 3, 4, and 13, for the failure of naive relativistic quantum mechanics, scalar-field quantization, spin-statistics, and the Lehmann–Källén representation.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.1–I.4 and III.8, for the physical motivation from relativity plus quantum mechanics and the relation between imaginary parts, probability, and analytic structure.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for the Wightman-axiom version of the spectrum condition.
- R. Haag, *Local Quantum Physics*, for the algebraic QFT formulation of positive energy and local observables.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, Vols. I–II, for spectral theory background.

## Version history

- **2026-05-23:** Initial qft.org page on the spectral condition, forward-cone support, vacuum stability, mass gaps, Wightman support, the Källén–Lehmann connection, tachyon caveats, gauge-theory subtleties, and exercises.
