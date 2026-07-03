---
title: "Relativistic Normalization"
description: "The Lorentz-invariant on-shell measure, covariant one-particle normalization, delta functions, creation operators, and phase-space conventions used throughout qft.org."
sidebar:
  label: "Relativistic Normalization"
  order: 3
level: Graduate
status: "Polished draft"
topics:
  - relativistic normalization
  - invariant measure
  - delta functions
  - phase space
  - creation operators
canonicalTopics:
  - covariant-state-normalization
  - on-shell-measure
  - lorentz-invariant-phase-space
---

## Summary

Relativistic normalization is the art of putting the factor $2E_{\boldsymbol p}$ in the place where it does the most work.

The qft.org default one-particle normalization is

$$
\boxed{
\langle \boldsymbol p',a'\mid\boldsymbol p,a\rangle
=(2\pi)^3 2E_{\boldsymbol p}\,
\delta^{(3)}(\boldsymbol p-\boldsymbol p')\delta_{aa'}.
}
$$

The matching identity operator is

$$
\boxed{
\mathbf1_1
=\sum_a\int\frac{d^3\boldsymbol p}{(2\pi)^3 2E_{\boldsymbol p}}
\lvert\boldsymbol p,a\rangle\langle\boldsymbol p,a\rvert.
}
$$

The measure

$$
\boxed{
 d\Pi_p
=\frac{d^3\boldsymbol p}{(2\pi)^3 2E_{\boldsymbol p}}
=\frac{d^4p}{(2\pi)^3}\theta(p^0)\delta(p^2-m^2)
}
$$

is Lorentz invariant. This is why it appears in mode expansions, completeness relations, phase space, spectral representations, and LSZ formulas.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Deriving the Lorentz-invariant on-shell measure from the positive mass shell](/figures/foundations/on-shell-measure.svg)

<figcaption>

The invariant four-dimensional measure becomes the on-shell measure after restricting to $p^2=m^2$ and $p^0>0$. Integrating over $p^0$ produces the Jacobian $1/(2E_{\boldsymbol p})$.

</figcaption>
</figure>

## Prerequisites

You should have read [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/) and [Conventions and Normalizations](/foundations/conventions-and-normalizations/). You should be comfortable with Dirac delta functions and the mostly-minus convention

$$
p^2=(p^0)^2-\boldsymbol p^2,
\qquad
p^0=E_{\boldsymbol p}=\sqrt{\boldsymbol p^2+m^2}.
$$

## The invariant on-shell measure

Start with the Lorentz-invariant measure $d^4p$. To put a particle of mass $m$ on shell, insert

$$
\delta(p^2-m^2).
$$

To keep positive-energy states, insert $\theta(p^0)$. Then

$$
d^4p\,\theta(p^0)\delta(p^2-m^2)
$$

is an invariant measure on the positive-energy mass shell.

Now write

$$
p^2-m^2=(p^0)^2-E_{\boldsymbol p}^2,
\qquad
E_{\boldsymbol p}=\sqrt{\boldsymbol p^2+m^2}.
$$

Using

$$
\delta(f(x))=\sum_i\frac{\delta(x-x_i)}{|f'(x_i)|},
$$

we get

$$
\delta((p^0)^2-E_{\boldsymbol p}^2)
=\frac{1}{2E_{\boldsymbol p}}
\left[\delta(p^0-E_{\boldsymbol p})+
\delta(p^0+E_{\boldsymbol p})\right].
$$

The step function keeps only the first root. Therefore, for a test function $F$,

$$
\int d^4p\,\theta(p^0)\delta(p^2-m^2)F(p)
=
\int\frac{d^3\boldsymbol p}{2E_{\boldsymbol p}}F(E_{\boldsymbol p},\boldsymbol p).
$$

Including the qft.org Fourier convention gives

$$
\boxed{
 d\Pi_p
=\frac{d^3\boldsymbol p}{(2\pi)^3 2E_{\boldsymbol p}}.
}
$$

For a massless particle, $E_{\boldsymbol p}=|\boldsymbol p|$, so

$$
d\Pi_p=\frac{d^3\boldsymbol p}{(2\pi)^3 2|\boldsymbol p|}.
$$

## Covariant state normalization

The measure and the inner product must be paired. With

$$
d\Pi_p=\frac{d^3\boldsymbol p}{(2\pi)^3 2E_{\boldsymbol p}},
$$

the natural covariant normalization is

$$
\langle \boldsymbol p',a'\mid\boldsymbol p,a\rangle
=(2\pi)^3 2E_{\boldsymbol p}\delta^{(3)}(\boldsymbol p-\boldsymbol p')\delta_{aa'}.
$$

Then

$$
\mathbf1_1
=\sum_a\int d\Pi_p\,
\lvert\boldsymbol p,a\rangle\langle\boldsymbol p,a\rvert
$$

really acts as the identity:

$$
\mathbf1_1\lvert\boldsymbol q,b\rangle
=\lvert\boldsymbol q,b\rangle.
$$

The factor in the measure cancels the factor in the inner product.

:::tip[Memory aid]
If completeness has $1/(2E_{\boldsymbol p})$, the inner product has $2E_{\boldsymbol p}$. They are dual conventions, not two unrelated annoyances.
:::

## Delta functions on the mass shell

Define the on-shell delta distribution by

$$
\widetilde\delta_p(q)
=(2\pi)^3 2E_{\boldsymbol p}\delta^{(3)}(\boldsymbol p-\boldsymbol q).
$$

Its defining property is

$$
\int d\Pi_q\,\widetilde\delta_p(q)F(q)=F(p)
$$

for functions restricted to the positive-energy mass shell. The ordinary three-dimensional delta function is not invariant by itself. The combination paired with $d\Pi_p$ is.

## Relation to noncovariant normalization

Some sources use

$$
\langle \boldsymbol p'\mid\boldsymbol p\rangle_{\rm nc}
=(2\pi)^3\delta^{(3)}(\boldsymbol p-\boldsymbol p').
$$

Then the covariantly normalized state is

$$
\lvert\boldsymbol p\rangle_{\rm cov}
=\sqrt{2E_{\boldsymbol p}}\,\lvert\boldsymbol p\rangle_{\rm nc}.
$$

If a source instead uses

$$
\langle \boldsymbol p'\mid\boldsymbol p\rangle_\delta
=\delta^{(3)}(\boldsymbol p-\boldsymbol p'),
$$

then

$$
\lvert\boldsymbol p\rangle_{\rm cov}
=(2\pi)^{3/2}\sqrt{2E_{\boldsymbol p}}\,\lvert\boldsymbol p\rangle_\delta.
$$

All these choices describe the same physics. They differ only in where the normalization factors live.

## Creation and annihilation operators

With covariant normalization, a real scalar field is often written

$$
\phi(x)
=\int d\Pi_p\left[a(\boldsymbol p)e^{-ip\cdot x}+a^\dagger(\boldsymbol p)e^{ip\cdot x}\right],
\qquad
p^0=E_{\boldsymbol p}.
$$

The operators obey

$$
[a(\boldsymbol p),a^\dagger(\boldsymbol q)]
=(2\pi)^3 2E_{\boldsymbol p}\delta^{(3)}(\boldsymbol p-\boldsymbol q).
$$

Then

$$
\lvert\boldsymbol p\rangle=a^\dagger(\boldsymbol p)\lvert0\rangle
$$

has the covariant one-particle normalization.

Many books instead write

$$
\phi(x)=\int\frac{d^3\boldsymbol p}{(2\pi)^3}\frac{1}{\sqrt{2E_{\boldsymbol p}}}
\left[\alpha(\boldsymbol p)e^{-ip\cdot x}+\alpha^\dagger(\boldsymbol p)e^{ip\cdot x}\right],
$$

with

$$
[\alpha(\boldsymbol p),\alpha^\dagger(\boldsymbol q)]
=(2\pi)^3\delta^{(3)}(\boldsymbol p-\boldsymbol q).
$$

The relation is

$$
a(\boldsymbol p)=\sqrt{2E_{\boldsymbol p}}\,\alpha(\boldsymbol p).
$$

## Wave packets

A normalizable one-particle state is

$$
\lvert f\rangle
=\sum_a\int d\Pi_p\,f_a(\boldsymbol p)\lvert\boldsymbol p,a\rangle.
$$

Its norm is

$$
\langle f\mid f\rangle
=\sum_a\int d\Pi_p\,|f_a(\boldsymbol p)|^2.
$$

The components $f_a(\boldsymbol p)$ may transform with Wigner rotations or polarization matrices. The measure is invariant; the full state transforms consistently.

## Phase space

The same measure appears in final-state phase space. For $n$ on-shell final particles with total momentum $P$,

$$
\boxed{
 d\Phi_n(P;p_1,\ldots,p_n)
=(2\pi)^4\delta^{(4)}\!\left(P-\sum_{i=1}^n p_i\right)
\prod_{i=1}^n d\Pi_{p_i}.
}
$$

If some final particles are identical, cross-section and decay-rate formulas include symmetry factors to avoid overcounting final configurations. The state-space reason is explained in [Multiparticle States](/foundations/relativistic-particles-and-fields/multiparticle-states/).

## Common pitfalls

**Dropping $2E_{\boldsymbol p}$ inconsistently.** You may use a different convention, but the inner product, completeness relation, creation-operator algebra, and LSZ factors must change together.

**Thinking $d^3\boldsymbol p$ is invariant.** It is not. The invariant on-shell measure is $d^3\boldsymbol p/(2E_{\boldsymbol p})$.

**Confusing plane waves with normalizable states.** Momentum eigenstates are delta-normalized distributions. Physical one-particle states are wave packets.

**Mixing textbook conventions mid-calculation.** Most normalization mistakes come from importing one formula from one convention and another formula from a different convention.

## Relation to other topics

- [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/) defines the momentum eigenstates being normalized here.
- [Multiparticle States](/foundations/relativistic-particles-and-fields/multiparticle-states/) extends the normalization to identical-particle sectors.
- [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/) uses the matching creation and annihilation algebra.
- [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/) derives the scalar mode expansion in detail.
- The perturbative QFT scattering pages use $d\Phi_n$ for observables once the scattering section is filled in.

## Research status

- **Established:** The covariant normalization and invariant phase-space measure are standard textbook conventions.
- **Active:** Soft and collinear massless particles require additional care beyond the definition of $d\Pi_p$, especially in infrared-safe observables.

## References

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 1.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §2.5.
- M. Srednicki, *Quantum Field Theory*, §§1–3 and 11.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed., Part I.8.

## Version history

- **2026-06-08:** Revised for shorter reader flow, consistent chapter terminology, clearer convention translation, and reduced repeated warnings.
