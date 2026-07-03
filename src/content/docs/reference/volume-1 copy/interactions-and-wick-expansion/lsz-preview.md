---
title: "LSZ Preview"
description: "A first explanation of how time-ordered correlation functions become scattering amplitudes: one-particle poles, field-strength residues, amputation, and on-shell limits."
sidebar:
  label: "LSZ Preview"
  order: 8
---

## Summary

Correlation functions are vacuum expectation values of fields. Scattering amplitudes are matrix elements between asymptotic particle states. The LSZ reduction formula explains how these two languages meet.

For a scalar field whose exact two-point function has a stable one-particle pole,

$$
G_2(p)\underset{p^2\to m^2}{\sim}\frac{iZ}{p^2-m^2+i\epsilon}+\text{regular},
$$

the residue $Z$ measures the overlap between the field and the physical one-particle state:

$$
\langle0|\phi(0)|p\rangle=\sqrt Z.
$$

The LSZ prescription says: take the connected time-ordered Green function, isolate each external one-particle pole, remove the external propagators, and put the external momenta on shell. In an all-incoming momentum convention,

$$
\boxed{
 i\mathcal M_n
=\left[\prod_{j=1}^n Z^{-1/2}
\lim_{p_j^2\to m^2}\frac{p_j^2-m^2}{i}\right]
\widetilde G^{\rm c}_{n,\,\text{stripped}}(p_1,\ldots,p_n).
}
$$

Here $\widetilde G^{\rm c}_{n,\,\text{stripped}}$ is the connected momentum-space correlator with the overall $(2\pi)^4\delta^{(4)}(\sum_jp_j)$ removed. Outgoing particles are represented by incoming momenta with the opposite sign.

This is only a preview. A full scattering section will later discuss wave packets, asymptotic completeness, cross sections, phase space, spin, gauge fields, infrared subtleties, and the optical theorem. But this page fixes the conceptual bridge: **the poles of correlators know about particles**. Srednicki presents the scalar LSZ formula as the basic relation between interacting-field correlators and scattering amplitudes, with field-normalization conditions; Coleman derives the LSZ formalism after constructing Green functions and in/out states; Weinberg embeds reduction formulas in the general S-matrix framework (Srednicki 2007, §5; Coleman 2019, chs. 13–14; Weinberg 1995, Vol. I, §§3.1–3.5 and §10.3).

## Prerequisites

You should know [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/), [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/), [Connected Diagrams](/foundations/interactions-and-wick-expansion/connected-diagrams/), and [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/).

## Core idea

A local field is not itself a particle state. But if it has a nonzero overlap with a stable one-particle state, its two-point function has a pole at the physical mass. Higher connected correlators have corresponding poles when external momenta approach the mass shell. LSZ extracts the residue of those poles.

<figure class="doc-figure" style="--figure-width: 42rem;">

![LSZ amputation map from connected correlators to scattering amplitudes](/figures/foundations/lsz-amputation-map.svg)

<figcaption>

The connected Green function includes external propagators. LSZ isolates the single-particle poles, multiplies by the inverse pole factors, includes one factor of $Z^{-1/2}$ per external leg, and then takes the on-shell limit $p_j^2\to m^2$.

</figcaption>
</figure>

In pictures, Feynman diagrams for correlators have external propagator tails. Feynman diagrams for amplitudes have those external tails removed. That removal is called **amputation**.

:::note[Assumptions]
This page treats a single stable scalar particle with a mass gap and nonzero field overlap. The clean LSZ formula assumes well-defined asymptotic one-particle states. Massless particles, gauge fields, confined fields, unstable particles, infraparticles, and bound states require extra care.
:::

## Correlators are off-shell objects

The connected $n$-point function is

$$
G_n^{\rm c}(x_1,\ldots,x_n)
=\langle0|T\{\phi(x_1)\cdots\phi(x_n)\}|0\rangle_{\rm connected}.
$$

Using qft.org's Fourier convention,

$$
\widetilde G_n^{\rm c}(p_1,\ldots,p_n)
=\int\prod_{j=1}^n d^4x_j\,
\exp\left(i\sum_{j=1}^n p_j\cdot x_j\right)
G_n^{\rm c}(x_1,\ldots,x_n).
$$

Translation invariance gives

$$
\widetilde G_n^{\rm c}(p_1,\ldots,p_n)
=(2\pi)^4\delta^{(4)}\left(\sum_{j=1}^n p_j\right)
\widetilde G^{\rm c}_{n,\,\text{stripped}}(p_1,\ldots,p_n).
$$

The variables $p_j$ in the Green function are not required to satisfy $p_j^2=m^2$. They are off-shell Fourier variables. Scattering amplitudes, by contrast, are defined for external particles on the physical mass shell.

That is the first conceptual gap LSZ closes.

## The one-particle pole

The exact scalar two-point function has a Källén–Lehmann spectral representation. If the theory contains a stable one-particle state of mass $m$ created by $\phi$, then near the pole

$$
\boxed{
G_2(p)
\underset{p^2\to m^2}{\sim}
\frac{iZ}{p^2-m^2+i\epsilon}+\text{regular}.
}
$$

The constant $Z$ is the field-strength residue. It is fixed by

$$
\boxed{
\langle0|\phi(0)|p\rangle=\sqrt Z.
}
$$

For the canonically normalized free scalar field used earlier in Foundations,

$$
Z=1.
$$

In an interacting theory, the field appearing in the Lagrangian need not create the physical one-particle state with unit overlap. The LSZ factors $Z^{-1/2}$ correct for this.

A field may also have no overlap with a given particle. Then it cannot be used directly as the external interpolating field for that particle. This is not a paradox; it just means the field has the wrong quantum numbers or the wrong normalization.

## External poles in higher correlators

The same pole appears on every external leg of a connected Green function. Near the simultaneous one-particle poles,

$$
\boxed{
\widetilde G^{\rm c}_{n,\,\text{stripped}}(p_1,\ldots,p_n)
\sim
\left[\prod_{j=1}^n
\frac{i\sqrt Z}{p_j^2-m^2+i\epsilon}
\right]
i\mathcal M_n(p_1,\ldots,p_n).
}
$$

This formula uses the all-incoming convention. For a physical process

$$
p_1+p_2\to q_1+q_2,
$$

one may set

$$
(p_1,p_2,p_3,p_4)=(p_1,p_2,-q_1,-q_2)
$$

inside the all-incoming correlator.

Solving the pole formula for the amplitude gives the LSZ prescription:

$$
\boxed{
 i\mathcal M_n
=
\left[\prod_{j=1}^n Z^{-1/2}
\lim_{p_j^2\to m^2}\frac{p_j^2-m^2}{i}\right]
\widetilde G^{\rm c}_{n,\,\text{stripped}}(p_1,\ldots,p_n).
}
$$

The factor $(p_j^2-m^2)/i$ removes the scalar Feynman propagator $i/(p_j^2-m^2+i\epsilon)$. The factor $Z^{-1/2}$ removes the field-state overlap. What remains is the amputated on-shell scattering amplitude.

## Coordinate-space interpretation

In coordinate space, amputation is the operation of applying the inverse free wave operator to each external point and then Fourier transforming. For the scalar propagator,

$$
(\Box_x+m^2)D_F(x-y)=-i\delta^{(4)}(x-y).
$$

Therefore applying $\Box+m^2$ to an external leg collapses the external propagator. This is the coordinate-space version of multiplying by $p^2-m^2$ in momentum space.

Schematic coordinate-space LSZ looks like

$$
\text{amplitude}
\sim
\prod_{j=1}^n
\left[Z^{-1/2}\int d^4x_j\,e^{ip_j\cdot x_j}(\Box_{x_j}+m^2)\right]
G_n^{\rm c}(x_1,\ldots,x_n),
$$

with signs and momentum directions fixed by the incoming/outgoing convention. The momentum-space formula above is the cleaner convention for this page.

## Example: tree-level quartic scalar scattering

In $\lambda\phi^4$ theory, with

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

the first connected four-point function at tree level has the stripped form

$$
\widetilde G^{\rm c}_{4,\,\text{stripped}}
=
\left[\prod_{j=1}^4\frac{i}{p_j^2-m^2+i\epsilon}\right](-i\lambda).
$$

At this order $Z=1$. Applying LSZ gives

$$
 i\mathcal M_4
=\left[\prod_{j=1}^4\lim_{p_j^2\to m^2}\frac{p_j^2-m^2}{i}\right]
\left[\prod_{j=1}^4\frac{i}{p_j^2-m^2+i\epsilon}\right](-i\lambda).
$$

Each external pole factor cancels, so

$$
\boxed{i\mathcal M_4=-i\lambda,}
\qquad
\boxed{\mathcal M_4=-\lambda.}
$$

This is the same tree-level contact amplitude found diagrammatically. LSZ explains why one should not include external propagators in the final amplitude: they belong to the correlator, not to the S-matrix element.

## Example: cubic exchange

In $g\phi^3$ theory, the connected four-point correlator contains tree exchange diagrams. In the $s$ channel, the stripped correlator contains

$$
\left[\prod_{j=1}^4\frac{i}{p_j^2-m^2+i\epsilon}\right]
(-ig)^2\frac{i}{s-m^2+i\epsilon},
$$

where

$$
s=(p_1+p_2)^2.
$$

LSZ removes only the four external propagators. It does not remove the internal exchange propagator. Thus the $s$-channel amplitude contribution is

$$
 i\mathcal M_s=(-ig)^2\frac{i}{s-m^2+i\epsilon}.
$$

The internal pole is physical information about an intermediate propagation channel. External poles are removed because they only represent the interpolation between fields and asymptotic states.

## Why connected correlators are enough

Disconnected correlator pieces describe independent processes occurring side by side. For scattering, the interesting transition amplitude is the connected part after removing identity/no-scattering contributions. That is why LSZ is normally applied to connected Green functions when extracting connected amplitudes.

The full S-matrix contains an identity piece:

$$
S=1+iT.
$$

The identity contribution says that particles can pass through without interacting. Connected amputated Green functions extract the nontrivial part $iT$.

## Relation to field normalization

A common shortcut is to choose a renormalized field such that

$$
\langle0|\phi_R(0)|p\rangle=1.
$$

Then $Z_R=1$ for that field, and the LSZ residue factors disappear. This is a normalization convention, not a new physical principle.

If one instead uses a bare or differently normalized field, the external $Z^{-1/2}$ factors must be included. The amplitude should not depend on the arbitrary normalization of the interpolating field.

This is one of the quiet morals of LSZ: local fields are not directly observables. Properly normalized S-matrix elements are.

## When the simple formula needs care

### Massless particles

Massless particles can create infrared divergences. In QED, for example, amplitudes with a fixed number of photons are not always infrared-safe observables. Inclusive rates and dressed states enter later.

### Gauge fields

For photons and gluons, gauge fixing, polarization vectors, ghosts, and Ward identities all matter. The external physical states are transverse polarizations or gauge-invariant asymptotic states, not arbitrary components of $A_\mu$.

### Unstable particles

An unstable particle does not correspond to a stable asymptotic one-particle state. Its propagator may have a resonance pole away from the real axis, but it should not be treated as an ordinary external LSZ particle.

### Confined particles

Quark and gluon fields do not create isolated asymptotic particle states in confining QCD. LSZ applies to physical asymptotic states such as hadrons, not to colored elementary fields as external particles.

### Composite operators

If a particle is created by a composite operator, the same pole-residue logic applies, but the operator usually requires renormalization and mixing with other operators of the same quantum numbers.

## Common pitfalls

### Leaving external propagators in amplitudes

External propagators belong to Green functions. Scattering amplitudes are amputated. If external propagators remain, one is usually still computing a correlator, not an S-matrix element.

### Putting momenta on shell too early

The operation is: compute the off-shell correlator, isolate the pole factors, multiply by inverse pole factors, and then take the on-shell limit. Setting $p^2=m^2$ before amputation can turn useful pole information into undefined infinities.

### Forgetting the residue

In an interacting theory, the two-point pole residue need not be one. The LSZ factor $Z^{-1/2}$ per external leg is what makes the answer independent of field normalization.

### Treating virtual lines as external particles

LSZ applies to external asymptotic states. Internal lines in a Feynman diagram are not put on shell by LSZ and are not removed by external amputation.

## Relations to nearby pages

- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) explains why stable particles show up as poles in exact two-point functions.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) gives the external propagator factors that LSZ removes.
- [Connected Diagrams](/foundations/interactions-and-wick-expansion/connected-diagrams/) explains why connected correlators isolate non-factorized processes.
- [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/) generates amputated 1PI vertices, which are building blocks for amplitudes.
- [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/) gives the tree-level scalar examples used above.
- [Scattering Theory](/perturbative-qft/scattering-theory/) will develop the full S-matrix, cross sections, decay rates, and phase space.

## Research status

LSZ reduction is textbook-standard for relativistic QFTs with stable asymptotic particle states and a mass gap. Its assumptions become nontrivial in gauge theories, massless theories, confined theories, finite-volume systems, curved spacetime, and theories without an ordinary particle S-matrix. Those cases do not invalidate LSZ; they clarify how much structure is hidden in the innocent phrase “asymptotic particle state.”

## Exercises

### Exercise 1: Amputate a free external scalar propagator

Show that multiplying

$$
\frac{i}{p^2-m^2+i\epsilon}
$$

by $(p^2-m^2)/i$ and then taking $p^2\to m^2$ gives one.

<details>
<summary><strong>Solution</strong></summary>

We compute

$$
\lim_{p^2\to m^2}\frac{p^2-m^2}{i}\frac{i}{p^2-m^2+i\epsilon}.
$$

The factor of $i$ cancels. After the pole has been isolated, the limiting operation gives

$$
\lim_{p^2\to m^2}\frac{p^2-m^2}{p^2-m^2+i\epsilon}=1.
$$

The $i\epsilon$ specifies how the pole is approached as a distribution; LSZ extracts the residue.

</details>

### Exercise 2: Field-strength residue

If

$$
G_2(p)\sim\frac{iZ}{p^2-m^2+i\epsilon},
$$

what factor should be associated with each external leg in LSZ?

<details>
<summary><strong>Solution</strong></summary>

Each external leg contributes a pole factor

$$
\frac{i\sqrt Z}{p^2-m^2+i\epsilon}
$$

inside a higher connected correlator. LSZ removes this by multiplying by

$$
\frac{p^2-m^2}{i\sqrt Z}=Z^{-1/2}\frac{p^2-m^2}{i}.
$$

Thus each external leg carries a factor $Z^{-1/2}$ in addition to the inverse pole factor.

</details>

### Exercise 3: Quartic scalar tree amplitude

Use LSZ to extract the tree-level $\lambda\phi^4$ four-point amplitude from

$$
\widetilde G^{\rm c}_{4,\,\text{stripped}}
=
\left[\prod_{j=1}^4\frac{i}{p_j^2-m^2+i\epsilon}\right](-i\lambda).
$$

<details>
<summary><strong>Solution</strong></summary>

At tree level $Z=1$. Apply one inverse pole factor to each external leg:

$$
 i\mathcal M_4
=\left[\prod_{j=1}^4\frac{p_j^2-m^2}{i}\right]
\left[\prod_{j=1}^4\frac{i}{p_j^2-m^2+i\epsilon}\right](-i\lambda).
$$

The four external factors cancel, leaving

$$
i\mathcal M_4=-i\lambda.
$$

Therefore

$$
\mathcal M_4=-\lambda.
$$

</details>

### Exercise 4: Why internal propagators remain

In the cubic scalar exchange diagram, why does LSZ remove the external propagators but not the internal exchange propagator?

<details>
<summary><strong>Solution</strong></summary>

LSZ is applied once for each external asymptotic particle. It extracts the pole associated with the field creating or annihilating that external particle. Internal propagators are integrated over or fixed by momentum conservation inside the diagram; they represent intermediate propagation, not external field-state interpolation. Therefore the internal factor, such as $i/(s-m^2+i\epsilon)$, remains in the amplitude.

</details>

### Exercise 5: Outgoing momentum in all-incoming convention

A physical process has incoming momenta $p_1,p_2$ and outgoing momenta $q_1,q_2$. What momenta appear in the all-incoming four-point correlator?

<details>
<summary><strong>Solution</strong></summary>

The all-incoming convention represents outgoing particles by incoming momenta with the opposite sign. Thus the four momenta are

$$
(p_1,p_2,-q_1,-q_2).
$$

Momentum conservation in the correlator is

$$
p_1+p_2-q_1-q_2=0,
$$

which is the usual physical conservation law.

</details>

### Exercise 6: State an assumption of LSZ

Name one physical assumption needed for the simple scalar LSZ formula on this page.

<details>
<summary><strong>Solution</strong></summary>

One assumption is the existence of a stable one-particle asymptotic state of mass $m$ with nonzero overlap with the field $\phi$:

$$
\langle0|\phi(0)|p\rangle\ne0.
$$

Equivalently, the two-point function must contain a one-particle pole with nonzero residue. Other assumptions include a suitable vacuum, a mass gap for the cleanest version, and well-defined in/out states.

</details>

## Sources and further reading

- H. Lehmann, K. Symanzik, and W. Zimmermann, “Zur Formulierung quantisierter Feldtheorien,” *Nuovo Cimento* **1** (1955), 205–225, for the original LSZ framework.
- Mark Srednicki, *Quantum Field Theory*, §5, for a concise scalar LSZ derivation and field-normalization conditions; §56 for the photon version.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 13–14, for Green functions, in/out states, and the LSZ formalism.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, §§3.1–3.5 and §10.3, for scattering theory, asymptotic states, and reduction formulas.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*, §7.2, for the LSZ formula and its role in extracting S-matrix elements.

## Version history

- **2026-05-23:** Initial qft.org preview of LSZ reduction: one-particle poles, field-strength residues, amputation, on-shell limits, scalar examples, and assumptions.
