---
title: "Bogoliubov Transformations"
description: "A derivation-focused guide to Bogoliubov transformations between curved-spacetime mode bases, including particle creation, normalization identities, squeezed vacua, and physical interpretation."
sidebar:
  label: "Bogoliubov Transformations"
  order: 50
level: Graduate
status: "Polished draft"
source: "Birrell and Davies 1982, chs. 3–4; Wald 1994, chs. 2–4; Fulling 1989; Parker and Toms 2009; Mukhanov and Winitzki 2007"
topics:
  - Bogoliubov transformations
  - particle creation
  - curved spacetime
  - mode mixing
  - squeezed states
canonicalTopics:
  - bogoliubov-transformation
  - particle-creation
  - beta-coefficient
  - squeezed-vacuum
  - inequivalent-fock-representations
researchStatus:
  established:
    - "Bogoliubov transformations are the standard linear-algebraic mechanism by which different positive-frequency choices in free QFT lead to different particle notions."
  active:
    - "In infinite volume and in dynamical or horizon spacetimes, the physical interpretation of particle number must be supplemented by state selection, detector response, and renormalized local observables."
---

## Summary

A **Bogoliubov transformation** relates two different choices of positive-frequency modes for the same free quantum field. Let $\{u_i\}$ and $\{v_j\}$ be two complete positive-frequency bases for a real scalar field. Since both are bases of the same complexified solution space, each $v_j$ can be expanded as

$$
v_j=\sum_i\left(\alpha_{ji}u_i+\beta_{ji}u_i^*\right).
$$

The coefficients $\alpha_{ji}$ and $\beta_{ji}$ are the Bogoliubov coefficients. The crucial coefficient is $\beta$. If $\beta=0$, the two bases agree on what counts as positive frequency. If $\beta\neq0$, the annihilation operators for one basis mix creation and annihilation operators for the other:

$$
b_j=\sum_i\left(\alpha_{ji}^*a_i-\beta_{ji}^*a_i^\dagger\right).
$$

Therefore the $u$-vacuum generally contains $v$-particles:

$$
\langle0_u|b_j^\dagger b_j|0_u\rangle
=\sum_i |\beta_{ji}|^2.
$$

This is the algebraic heart of cosmological particle creation, the Unruh effect, Hawking radiation, and many squeezed-state phenomena. The physics is not that particles are secretly absolute. The physics is that different observers or asymptotic regions can decompose the same local field into positive and negative frequency in inequivalent ways.

## Prerequisites

Read [Mode Expansions in Curved Spacetime](/spacetime-gravity-holography/qft-in-curved-spacetime/mode-expansions-in-curved-spacetime/) and [Scalar Fields in Curved Spacetime](/spacetime-gravity-holography/qft-in-curved-spacetime/scalar-fields-in-curved-spacetime/) first. You should be comfortable with the Klein–Gordon inner product, mode normalization, and the idea that a positive-frequency split defines annihilation operators.

The examples also use [Killing Vectors and Conserved Quantities](/spacetime-gravity-holography/spacetime-gravity-toolkit/killing-vectors-and-conserved-quantities/) and [Horizons](/spacetime-gravity-holography/spacetime-gravity-toolkit/horizons/) conceptually, but no black-hole calculation is required yet.

## Core idea

A free field has one local equation of motion, but many possible decompositions into creation and annihilation operators. A Bogoliubov transformation compares two such decompositions.

The transformation has two parts:

| Coefficient | Meaning |
|---|---|
| $\alpha$ | Positive-frequency modes in one basis overlapping positive-frequency modes in the other. |
| $\beta$ | Positive-frequency modes in one basis overlapping negative-frequency modes in the other. |

The $\beta$ coefficient is the interesting one. It measures the failure of the two bases to agree on the positive-frequency split. Nonzero $\beta$ means the vacuum for one basis is an excited, usually squeezed, state for the other.

The slogan is

$$
\text{particle creation} = \text{mixing of positive and negative frequency}.
$$

## Setup and conventions

We work with a real scalar field satisfying

$$
P\phi=0,
\qquad
P=\Box_g+m^2+\xi R,
$$

and use the Klein–Gordon inner product

$$
(f,g)_{\mathrm{KG}}
=i\int_\Sigma d\Sigma\,n_\mu
\left(f^*\nabla^\mu g-g\nabla^\mu f^*\right).
$$

Let $\{u_i\}$ and $\{v_j\}$ be two complete positive-frequency bases satisfying

$$
(u_i,u_j)_{\mathrm{KG}}=\delta_{ij},
\qquad
(u_i^*,u_j^*)_{\mathrm{KG}}=-\delta_{ij},
\qquad
(u_i,u_j^*)_{\mathrm{KG}}=0,
$$

and the same relations for the $v$ modes.

The field can be expanded in either basis:

$$
\widehat\phi
=\sum_i\left(a_i u_i+a_i^\dagger u_i^*\right)
=\sum_j\left(b_j v_j+b_j^\dagger v_j^*\right).
$$

The two vacua are defined by

$$
a_i|0_u\rangle=0,
\qquad
b_j|0_v\rangle=0.
$$

The point of the page is to compare these two definitions.

## Bogoliubov coefficients from inner products

Because $\{u_i,u_i^*\}$ is complete, write

$$
v_j=\sum_i\left(\alpha_{ji}u_i+\beta_{ji}u_i^*\right).
$$

Taking Klein–Gordon inner products gives

$$
\alpha_{ji}=(u_i,v_j)_{\mathrm{KG}},
\qquad
\beta_{ji}=-(u_i^*,v_j)_{\mathrm{KG}}.
$$

The minus sign in the second formula comes from the negative Klein–Gordon norm of complex-conjugate modes.

The inverse expansion has the same structure:

$$
u_i=\sum_j\left(\alpha_{ji}^*v_j-\beta_{ji}v_j^*\right),
$$

with index placement determined by the convention above. In matrix notation, the transformation acts on the doubled vector of modes as

$$
\begin{pmatrix} v \\ v^* \end{pmatrix}
=
\begin{pmatrix}
\alpha & \beta \\
\beta^* & \alpha^*
\end{pmatrix}
\begin{pmatrix} u \\ u^* \end{pmatrix}.
$$

This matrix is not unitary in the ordinary positive-definite sense. It preserves the indefinite Klein–Gordon form.

## Operator transformation

Using

$$
a_i=(u_i,\widehat\phi)_{\mathrm{KG}},
\qquad
b_j=(v_j,\widehat\phi)_{\mathrm{KG}},
$$

and the expansion of $v_j$ in terms of $u_i$, one finds

$$
b_j=\sum_i\left(\alpha_{ji}^*a_i-\beta_{ji}^*a_i^\dagger\right).
$$

Similarly,

$$
a_i=\sum_j\left(\alpha_{ji}b_j+\beta_{ji}^*b_j^\dagger\right).
$$

This is the central algebraic result. The annihilation operator $b_j$ is not purely an annihilation operator with respect to the $u$-basis if $\beta\neq0$.

The transformation preserves the canonical commutators if and only if the Bogoliubov coefficients obey the normalization identities below.

## Normalization identities

The $v$ modes must have the same Klein–Gordon normalization as the $u$ modes. From $(v_j,v_k)_{\mathrm{KG}}=\delta_{jk}$, one obtains

$$
\sum_i\left(
\alpha_{ji}\alpha_{ki}^*
-\beta_{ji}\beta_{ki}^*
\right)=\delta_{jk}.
$$

From $(v_j,v_k^*)_{\mathrm{KG}}=0$, one obtains

$$
\sum_i\left(
\alpha_{ji}\beta_{ki}
-\beta_{ji}\alpha_{ki}
\right)=0.
$$

These are the bosonic Bogoliubov identities. They are the infinite-dimensional analogue of the statement that the transformation preserves the canonical symplectic form.

For a single oscillator mode, these reduce to

$$
|\alpha|^2-|\beta|^2=1.
$$

A convenient parametrization is

$$
\alpha=e^{i\theta_\alpha}\cosh r,
\qquad
\beta=e^{i\theta_\beta}\sinh r,
$$

where $r$ is the squeeze parameter.

## Particle number

The number operator for $v$-particles is

$$
N_j^{(v)}=b_j^\dagger b_j.
$$

In the $u$-vacuum,

$$
\langle0_u|N_j^{(v)}|0_u\rangle
=\sum_i |\beta_{ji}|^2.
$$

The derivation is short. Insert

$$
b_j=\sum_i\left(\alpha_{ji}^*a_i-\beta_{ji}^*a_i^\dagger\right)
$$

and use

$$
a_i|0_u\rangle=0,
\qquad
\langle0_u|a_i a_k^\dagger|0_u\rangle=\delta_{ik}.
$$

Only the $a_i a_k^\dagger$ contraction survives, giving the sum of $|\beta|^2$.

For continuous labels, the same formula contains delta functions and often gives a density rather than a finite number. One must divide by spacetime volume factors or form wave packets before assigning a finite particle count.

## Squeezed-vacuum interpretation

If $\beta\neq0$, the $v$-vacuum is not the $u$-vacuum. In finite-dimensional notation, the condition

$$
b_j|0_v\rangle=0
$$

becomes

$$
\sum_i\left(\alpha_{ji}^*a_i-\beta_{ji}^*a_i^\dagger\right)|0_v\rangle=0.
$$

When $\alpha$ is invertible, the solution has the schematic squeezed form

$$
|0_v\rangle
=\mathcal N
\exp\left(\frac12\sum_{ik}\Gamma_{ik}a_i^\dagger a_k^\dagger\right)
|0_u\rangle,
$$

where

$$
\Gamma=\alpha^{-1}\beta
$$

up to index-convention transposes and complex conjugations. The important point is conceptual: the new vacuum is a coherent superposition of pairs of old particles.

Pair structure is forced for a real scalar field because the field is Hermitian and the Bogoliubov transformation mixes $u$ with $u^*$. In translationally invariant cosmology, particles are commonly produced in opposite-momentum pairs $\mathbf k$ and $-\mathbf k$.

## Example: one harmonic oscillator

A single quantum oscillator can be written in terms of two annihilation operators related by

$$
b=\alpha^*a-\beta^*a^\dagger,
\qquad
|\alpha|^2-|\beta|^2=1.
$$

The $a$-vacuum contains

$$
\langle0_a|b^\dagger b|0_a\rangle=|\beta|^2
$$

$b$-quanta.

This is not yet curved-spacetime physics. It is the algebraic core. Curved spacetime supplies natural reasons why the oscillator basis at early time, late time, near a horizon, or for an accelerated observer might be related by precisely this kind of transformation.

## Example: time-dependent frequency

Consider a mode equation of the form

$$
\chi_k''+\Omega_k(\eta)^2\chi_k=0.
$$

If $\Omega_k(\eta)$ approaches constants in the far past and far future, there are natural in and out modes:

$$
\chi_k^{\mathrm{in}}\sim\frac{e^{-i\omega_{\mathrm{in}}\eta}}
{\sqrt{2\omega_{\mathrm{in}}}}
\quad\text{as }\eta\to-\infty,
$$

and

$$
\chi_k^{\mathrm{out}}\sim\frac{e^{-i\omega_{\mathrm{out}}\eta}}
{\sqrt{2\omega_{\mathrm{out}}}}
\quad\text{as }\eta\to+\infty.
$$

The same exact solution that begins as a positive-frequency in-mode generally ends as a mixture:

$$
\chi_k^{\mathrm{in}}
=\alpha_k\chi_k^{\mathrm{out}}
+\beta_k\chi_k^{\mathrm{out}*}.
$$

The produced out-particle number in the in-vacuum is

$$
\langle0_{\mathrm{in}}|N_k^{\mathrm{out}}|0_{\mathrm{in}}\rangle
=|\beta_k|^2.
$$

This is the prototype for cosmological particle creation. A time-dependent background behaves like a parametric amplifier for field modes.

## Example: Rindler versus Minkowski

The right Rindler wedge of Minkowski spacetime has its own natural time coordinate, generated by Lorentz boosts. Positive frequency with respect to Rindler time is not the same as positive frequency with respect to Minkowski time.

Therefore the Minkowski and Rindler mode bases are related by a Bogoliubov transformation. The Minkowski vacuum is not empty for Rindler observers. When restricted to one wedge, it behaves thermally with respect to the Rindler Hamiltonian.

The result is the Unruh effect:

$$
T_U=\frac{a}{2\pi},
$$

where $a$ is the proper acceleration of the observer. The detailed derivation requires the Rindler modes and analytic continuation across the horizon, but the algebraic reason is already visible here: Rindler annihilation operators mix Minkowski annihilation and creation operators.

## Example: black-hole horizons

Near a smooth nonextremal horizon, the metric is locally Rindler-like. This is why the same Bogoliubov logic reappears in Hawking radiation.

In a gravitational collapse spacetime, one compares modes that are positive frequency near past null infinity with modes that are positive frequency near future null infinity. The horizon produces an exponential relation between null coordinates near the horizon, and that relation mixes positive and negative frequencies.

The result is a thermal spectrum at temperature

$$
T_H=\frac{\kappa}{2\pi},
$$

where $\kappa$ is the surface gravity. The full Hawking calculation adds greybody factors, state choices, and backreaction issues, but the central conversion from vacuum to particles is a Bogoliubov transformation.

## Infinite volume and inequivalent Fock spaces

For finitely many oscillators, every Bogoliubov transformation satisfying the canonical identities is implemented by a unitary operator on the same Hilbert space. In field theory, there are infinitely many oscillators, and this statement can fail.

A sufficient condition for unitary equivalence of the two Fock representations is that $\beta$ be Hilbert–Schmidt:

$$
\sum_{ij}|\beta_{ij}|^2<\infty.
$$

When this fails, the total number of $u$-particles in the $v$-vacuum is infinite, and the two Fock representations are unitarily inequivalent.

This is not a pathology. It is one reason the algebraic approach to QFT in curved spacetime treats local observables and states as more basic than any single global particle Hilbert space.

## Common pitfalls

**Saying nonzero beta means the background literally creates invariant particles.** It means two particle definitions disagree. The operational meaning depends on detectors, asymptotic regions, and the state.

**Forgetting normalization identities.** Arbitrary $\alpha$ and $\beta$ do not define a canonical transformation. They must preserve the Klein–Gordon inner product.

**Ignoring continuum delta functions.** In infinite volume, $|\beta_k|^2$ often describes a density. Wave packets or finite-volume normalization avoid fake infinities.

**Equating particle number with local energy density.** Particle number is basis-dependent. Renormalized stress tensors are local but require subtraction and curvature counterterms.

**Assuming the in-vacuum and out-vacuum live in the same Fock space.** For infinitely many modes, unitary equivalence can fail.

**Dropping complex conjugations in the operator map.** The difference between $v_j=\alpha u+\beta u^*$ and $b_j=\alpha^*a-\beta^*a^\dagger$ is a common source of sign and conjugation errors.

## Relations to other pages

This page follows [Mode Expansions in Curved Spacetime](/spacetime-gravity-holography/qft-in-curved-spacetime/mode-expansions-in-curved-spacetime/). It prepares particle creation, the Unruh effect, Hawking radiation, de Sitter QFT, and black-hole evaporation.

Later pages will compute specific $\alpha$ and $\beta$ coefficients in model geometries. The [Horizons](/spacetime-gravity-holography/spacetime-gravity-toolkit/horizons/) page explains why Rindler and black-hole horizons supply natural but observer-dependent frequency splittings.

## Research status

Bogoliubov transformations are standard and settled for free fields. They are one of the cleanest bridges between classical background geometry and quantum particle interpretation.

The active issues arise when this clean free-field language is embedded in more physical settings: interacting fields, dynamical gravity, backreaction, infrared effects, detector models, and the relation between particle production and local renormalized observables. The transformation itself is linear algebra; the interpretation can be subtle.

## Exercises

### Exercise 1: Derive the beta coefficient formula

Starting from

$$
v_j=\sum_i(\alpha_{ji}u_i+\beta_{ji}u_i^*),
$$

show that

$$
\alpha_{ji}=(u_i,v_j)_{\mathrm{KG}},
\qquad
\beta_{ji}=-(u_i^*,v_j)_{\mathrm{KG}}.
$$

<details><summary><strong>Solution</strong></summary>

Take the inner product with $u_i$:

$$
(u_i,v_j)_{\mathrm{KG}}
=\sum_k\left(\alpha_{jk}(u_i,u_k)_{\mathrm{KG}}
+\beta_{jk}(u_i,u_k^*)_{\mathrm{KG}}\right).
$$

Using orthonormality, this gives $\alpha_{ji}$. Taking the inner product with $u_i^*$ gives

$$
(u_i^*,v_j)_{\mathrm{KG}}
=\sum_k\beta_{jk}(u_i^*,u_k^*)_{\mathrm{KG}}
=-\beta_{ji},
$$

so $\beta_{ji}=-(u_i^*,v_j)_{\mathrm{KG}}$.

</details>

### Exercise 2: Particle number from beta

Use

$$
b_j=\sum_i(\alpha_{ji}^*a_i-\beta_{ji}^*a_i^\dagger)
$$

to show that

$$
\langle0_u|b_j^\dagger b_j|0_u\rangle
=\sum_i|\beta_{ji}|^2.
$$

<details><summary><strong>Solution</strong></summary>

The adjoint is

$$
b_j^\dagger=\sum_i(\alpha_{ji}a_i^\dagger-\beta_{ji}a_i).
$$

In the product $b_j^\dagger b_j$, the only term with nonzero $u$-vacuum expectation value is

$$
\sum_{ik}\beta_{ji}\beta_{jk}^*\langle0_u|a_i a_k^\dagger|0_u\rangle.
$$

Using $\langle0_u|a_i a_k^\dagger|0_u\rangle=\delta_{ik}$, we get

$$
\langle0_u|b_j^\dagger b_j|0_u\rangle
=\sum_i|\beta_{ji}|^2.
$$

</details>

### Exercise 3: Single-mode normalization

For one bosonic mode, suppose

$$
b=\alpha^*a-\beta^*a^\dagger.
$$

Show that $[b,b^\dagger]=1$ implies $|\alpha|^2-|\beta|^2=1$.

<details><summary><strong>Solution</strong></summary>

The adjoint is

$$
b^\dagger=\alpha a^\dagger-\beta a.
$$

Using $[a,a^\dagger]=1$,

$$
[b,b^\dagger]
=|\alpha|^2[a,a^\dagger]+|\beta|^2[a^\dagger,a]
=|\alpha|^2-|\beta|^2.
$$

Requiring $[b,b^\dagger]=1$ gives

$$
|\alpha|^2-|\beta|^2=1.
$$

</details>

### Exercise 4: No particle creation when beta vanishes

Suppose $v_j=\sum_i\alpha_{ji}u_i$ with no $u_i^*$ contribution. Show that $|0_u\rangle$ is also annihilated by all $b_j$.

<details><summary><strong>Solution</strong></summary>

If $\beta_{ji}=0$, then

$$
b_j=\sum_i\alpha_{ji}^*a_i.
$$

Acting on the $u$-vacuum gives

$$
b_j|0_u\rangle
=\sum_i\alpha_{ji}^*a_i|0_u\rangle=0.
$$

Thus the two bases define the same vacuum up to possible unitary rotations among annihilation operators.

</details>

## References

- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, Cambridge University Press, 1982.
- R. M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994.
- S. A. Fulling, *Aspects of Quantum Field Theory in Curved Spacetime*, Cambridge University Press, 1989.
- L. Parker and D. Toms, *Quantum Field Theory in Curved Spacetime*, Cambridge University Press, 2009.
- V. Mukhanov and S. Winitzki, *Introduction to Quantum Effects in Gravity*, Cambridge University Press, 2007.
- B. S. DeWitt, *The Global Approach to Quantum Field Theory*, Oxford University Press, 2003.

## Version history

- 2026-07-01: Added a polished page on Bogoliubov transformations, particle creation, and squeezed vacua.
