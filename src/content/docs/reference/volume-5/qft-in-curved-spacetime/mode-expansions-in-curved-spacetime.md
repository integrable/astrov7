---
title: "Mode Expansions in Curved Spacetime"
description: "A careful guide to expanding free fields in curved-spacetime modes, normalizing them with the Klein–Gordon inner product, and understanding when a particle interpretation exists."
sidebar:
  label: "Mode Expansions in Curved Spacetime"
  order: 40
level: Graduate
status: "Polished draft"
source: "Birrell and Davies 1982, chs. 3–4; Wald 1994, chs. 2–4; Fulling 1989; Parker and Toms 2009; Carroll 2004, chs. 3–4"
topics:
  - mode expansions
  - curved spacetime
  - Klein–Gordon inner product
  - positive frequency
  - Fock space
canonicalTopics:
  - curved-spacetime-mode-expansion
  - positive-frequency-modes
  - klein-gordon-inner-product
  - fock-space-curved-spacetime
  - stationary-spacetime-quantization
researchStatus:
  established:
    - "For free fields on globally hyperbolic spacetimes, mode expansions are a convenient representation of the field algebra once a complete positive-frequency subspace has been chosen."
  active:
    - "The mode expansion is not itself a state-selection principle; in nonstationary spacetimes and near horizons, physically preferred states require additional input."
---

## Summary

A **mode expansion** writes a free quantum field as a sum over classical solutions of the field equation multiplied by creation and annihilation operators. For a real scalar field on a curved background, one chooses complex solutions $u_i(x)$ of

$$
(\Box_g+m^2+\xi R)u_i=0
$$

that are orthonormal with respect to the Klein–Gordon inner product,

$$
(u_i,u_j)_{\mathrm{KG}}=\delta_{ij},
\qquad
(u_i^*,u_j^*)_{\mathrm{KG}}=-\delta_{ij},
\qquad
(u_i,u_j^*)_{\mathrm{KG}}=0.
$$

Then the field is expanded as

$$
\widehat\phi(x)
=\sum_i\left(a_i u_i(x)+a_i^\dagger u_i^*(x)\right),
\qquad
[a_i,a_j^\dagger]=\delta_{ij}.
$$

For continuous labels, the sum becomes an integral and the Kronecker delta becomes a Dirac delta.

This looks like flat-space quantization, but one word has become dangerous: **positive frequency**. In Minkowski spacetime, Poincare symmetry chooses the positive-frequency modes. In a general curved spacetime, there may be no preferred time translation, and hence no unique split into creation and annihilation operators. The local field algebra remains meaningful; the particle interpretation becomes dependent on the state, observer, boundary conditions, and asymptotic structure.

## Prerequisites

Read [Scalar Fields in Curved Spacetime](/spacetime-gravity-holography/qft-in-curved-spacetime/scalar-fields-in-curved-spacetime/), [Killing Vectors and Conserved Quantities](/spacetime-gravity-holography/spacetime-gravity-toolkit/killing-vectors-and-conserved-quantities/), and [Causal Structure](/spacetime-gravity-holography/spacetime-gravity-toolkit/causal-structure/).

You should know the flat-space mode expansion of the real scalar field and the idea that canonical commutators can be encoded by a complete set of positive- and negative-frequency solutions.

## Core idea

A classical free field equation has a vector space of solutions. Quantization turns a suitable half of that solution space into annihilation operators and the complex conjugate half into creation operators.

In flat spacetime, the half is chosen by the sign of energy:

$$
e^{-iE_{\mathbf p}t+i\mathbf p\cdot\mathbf x}
\quad\text{has positive frequency.}
$$

In curved spacetime, the field equation still has a solution space, but a preferred positive-frequency half may not exist. A mode expansion therefore has two layers:

| Layer | Geometric or physical input |
|---|---|
| Solution basis | The differential operator, boundary conditions, and global hyperbolicity. |
| Positive-frequency split | A timelike symmetry, asymptotic region, adiabatic prescription, regularity condition, or chosen state. |

The first layer is mostly kinematics. The second layer is where particle creation, Unruh radiation, Hawking radiation, and cosmological vacua enter.

## Setup and conventions

We use the mostly-minus conventions of this volume. The real scalar field obeys

$$
P\phi=0,
\qquad
P=\Box_g+m^2+\xi R.
$$

Let $\Sigma$ be a spacelike Cauchy surface with future-directed unit normal $n^\mu$. For two complex solutions $u$ and $v$, define

$$
(u,v)_{\mathrm{KG}}
=i\int_\Sigma d\Sigma\,n_\mu
\left(u^*\nabla^\mu v-v\nabla^\mu u^*\right).
$$

If $Pu=Pv=0$, then the current inside the integral is conserved, so the inner product is independent of the choice of $\Sigma$ when there is no boundary flux.

The inner product is anti-linear in the first slot and linear in the second:

$$
(\alpha u,\beta v)_{\mathrm{KG}}
=\alpha^*\beta (u,v)_{\mathrm{KG}}.
$$

It satisfies

$$
(u^*,v^*)_{\mathrm{KG}}=-(v,u)_{\mathrm{KG}}.
$$

This minus sign is why negative-frequency modes have negative Klein–Gordon norm.

## Positive-frequency subspaces

A **positive-frequency subspace** is a complex subspace $\mathcal S_+$ of the complex solution space such that every real solution can be decomposed uniquely as

$$
\phi=f+f^*,
\qquad
f\in\mathcal S_+,
$$

and the Klein–Gordon inner product is positive on $\mathcal S_+$:

$$
(f,f)_{\mathrm{KG}}>0
\qquad
\text{for }f\neq0.
$$

Choosing $\mathcal S_+$ is equivalent to choosing what will be called annihilation modes. It is also equivalent, for a free theory, to choosing a complex structure on the real solution space compatible with the symplectic form.

In a stationary spacetime with timelike Killing vector $\xi^\mu$, modes can be chosen to satisfy

$$
\mathcal L_\xi u_i=-i\omega_i u_i.
$$

If $\xi^\mu$ is timelike in the relevant region and boundary conditions are compatible with the symmetry, one usually calls $\omega_i>0$ positive frequency. This is the cleanest curved-spacetime analogue of flat-space quantization.

In a time-dependent spacetime, there may be no such $\xi^\mu$. Then a positive-frequency split can be natural only in an asymptotic region, in an adiabatic approximation, or by a state-selection rule such as regularity at a horizon.

## Orthonormal modes and completeness

Let $\{u_i\}$ be a positive-frequency mode basis. The orthonormality conditions are

$$
(u_i,u_j)_{\mathrm{KG}}=\delta_{ij},
\qquad
(u_i^*,u_j^*)_{\mathrm{KG}}=-\delta_{ij},
\qquad
(u_i,u_j^*)_{\mathrm{KG}}=0.
$$

For a continuous basis labeled by $\lambda$,

$$
(u_\lambda,u_{\lambda'})_{\mathrm{KG}}
=\delta(\lambda-\lambda'),
\qquad
(u_\lambda,u_{\lambda'}^*)_{\mathrm{KG}}=0.
$$

Completeness means that every sufficiently regular real solution can be expanded as

$$
\phi(x)=\sum_i\left(c_i u_i(x)+c_i^*u_i^*(x)\right),
$$

or, for continuous labels,

$$
\phi(x)=\int d\lambda\,
\left(c_\lambda u_\lambda(x)+c_\lambda^*u_\lambda^*(x)\right).
$$

The coefficients are recovered from the inner product:

$$
c_i=(u_i,\phi)_{\mathrm{KG}}.
$$

The existence of a convenient complete basis is a spectral problem. It depends on the geometry, boundary conditions, and domain of the differential operator.

## Quantization from the mode basis

Given a positive-frequency mode basis, the quantum field is

$$
\widehat\phi(x)
=\sum_i\left(a_i u_i(x)+a_i^\dagger u_i^*(x)\right).
$$

The canonical commutation relations are encoded by

$$
[a_i,a_j^\dagger]=\delta_{ij},
\qquad
[a_i,a_j]=0,
\qquad
[a_i^\dagger,a_j^\dagger]=0.
$$

The vacuum associated with this basis is

$$
a_i|0_u\rangle=0
\qquad
\text{for all }i.
$$

The notation $|0_u\rangle$ is deliberate. It is not “the” vacuum unless the geometry supplies a reason that this basis is preferred.

The commutator of fields is independent of the chosen basis:

$$
[\widehat\phi(x),\widehat\phi(x')]=i\Delta(x,x'),
$$

where $\Delta=G_R-G_A$ is the causal propagator. By contrast, the Wightman function

$$
G^+(x,x')=\langle0_u|\widehat\phi(x)\widehat\phi(x')|0_u\rangle
=\sum_i u_i(x)u_i^*(x')
$$

does depend on the chosen positive-frequency subspace.

## Flat-spacetime check

In Minkowski spacetime,

$$
ds^2=dt^2-d\mathbf x^2,
$$

positive-frequency modes are

$$
u_{\mathbf p}(x)
=\frac{e^{-iE_{\mathbf p}t+i\mathbf p\cdot\mathbf x}}
{\sqrt{2E_{\mathbf p}(2\pi)^{D-1}}},
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

They obey

$$
(u_{\mathbf p},u_{\mathbf q})_{\mathrm{KG}}
=\delta^{(D-1)}(\mathbf p-\mathbf q),
\qquad
(u_{\mathbf p},u_{\mathbf q}^*)_{\mathrm{KG}}=0.
$$

The field expansion becomes

$$
\widehat\phi(x)
=\int d^{D-1}\mathbf p\,
\left(a_{\mathbf p}u_{\mathbf p}(x)
+a_{\mathbf p}^\dagger u_{\mathbf p}^*(x)
\right),
$$

with

$$
[a_{\mathbf p},a_{\mathbf q}^\dagger]
=\delta^{(D-1)}(\mathbf p-\mathbf q).
$$

This normalization is equivalent to the more common form using $d^{D-1}\mathbf p/[(2\pi)^{D-1}2E_{\mathbf p}]$ after absorbing measure factors into the modes and operators.

## Static spacetimes

A static spacetime can often be written as

$$
ds^2=N(\mathbf x)^2dt^2-h_{ij}(\mathbf x)dx^i dx^j.
$$

Modes may be separated as

$$
u_\alpha(t,\mathbf x)=e^{-i\omega_\alpha t}f_\alpha(\mathbf x),
\qquad
\omega_\alpha>0.
$$

The spatial functions solve an eigenvalue problem determined by the operator $P$ and the boundary conditions. The natural vacuum is the one annihilated by the corresponding $a_\alpha$ operators.

This construction is robust when $\partial_t$ is everywhere timelike in the region and the boundary conditions are time-translation invariant. It becomes subtler in black-hole exteriors, rotating spacetimes, and spacetimes with horizons, because the Killing field can become null or spacelike.

## Cosmological mode functions

For a spatially flat Robertson–Walker metric in conformal time,

$$
ds^2=a(\eta)^2(d\eta^2-d\mathbf x^2),
$$

a scalar field can be expanded as

$$
\widehat\phi(\eta,\mathbf x)
=\int\frac{d^{D-1}\mathbf k}{(2\pi)^{D-1}}
\left(
 a_{\mathbf k}u_k(\eta)e^{i\mathbf k\cdot\mathbf x}
+a_{\mathbf k}^\dagger u_k^*(\eta)e^{-i\mathbf k\cdot\mathbf x}
\right).
$$

In $D=4$, it is often useful to define $\chi_k=a\,u_k$. For minimal notation, take $m$ and $\xi$ arbitrary. The mode equation has the schematic form

$$
\chi_k''+\Omega_k(\eta)^2\chi_k=0,
$$

with

$$
\Omega_k(\eta)^2
=k^2+a(\eta)^2m^2+
(\xi-1/6)a(\eta)^2R.
$$

Primes denote derivatives with respect to conformal time. The Wronskian condition from the Klein–Gordon inner product is

$$
\chi_k\chi_k^{*\prime}-\chi_k^*\chi_k'=i.
$$

If $a(\eta)$ changes with time, a mode that behaves like positive frequency in the far past need not remain positive frequency in the far future. That is the mode-expansion origin of cosmological particle creation.

## Boundary conditions and spectra

Mode expansions are incomplete until the domain of the wave operator is specified. The issue is invisible in the simplest flat-space examples because one usually assumes plane waves on all of $\mathbb R^{D-1}$ or periodic boundary conditions in a box.

On a general background, possible boundary conditions include:

| Boundary condition | Typical setting |
|---|---|
| Regularity | Origin of polar coordinates, Euclidean smoothness, nonsingular horizons. |
| Dirichlet or Neumann | Timelike walls, boxes, AdS-like boundaries. |
| Robin | Boundary EFTs and self-adjoint extensions. |
| Ingoing or outgoing | Horizons, scattering, quasinormal-mode problems. |
| Normalizability | Bound states, AdS modes, Sturm–Liouville problems. |

The boundary condition affects the spectrum, the normalization, the vacuum, and the allowed propagators. In AdS, for example, boundary conditions are part of the definition of the dual QFT source/vev problem.

## Common pitfalls

**Calling any complete solution basis a particle basis.** A particle basis requires a positive-frequency split, not just completeness.

**Assuming the vacuum is unique.** The local field equation does not choose a vacuum. Symmetry, asymptotic behavior, regularity, or physical preparation must do that job.

**Ignoring negative Klein–Gordon norms.** Complex conjugate modes carry the opposite Klein–Gordon norm. This is what makes creation operators appear with $u_i^*$.

**Forgetting boundary conditions.** A differential operator without a domain is not a complete spectral problem.

**Confusing the field commutator with the Wightman function.** The commutator is fixed by causal propagation. The Wightman and Feynman functions depend on the state.

**Trusting particles more than local observables.** Particle number can be observer- or time-dependent. Local field commutators and stress-tensor expectation values are more invariantly formulated, although the latter require renormalization.

## Relations to other pages

This page follows [Scalar Fields in Curved Spacetime](/spacetime-gravity-holography/qft-in-curved-spacetime/scalar-fields-in-curved-spacetime/) and prepares [Bogoliubov Transformations](/spacetime-gravity-holography/qft-in-curved-spacetime/bogoliubov-transformations/). It also supplies the language used in particle creation, the Unruh effect, Hawking radiation, and de Sitter QFT.

The [Killing Vectors and Conserved Quantities](/spacetime-gravity-holography/spacetime-gravity-toolkit/killing-vectors-and-conserved-quantities/) page explains when a timelike symmetry can define energy and positive frequency. The [Causal Structure](/spacetime-gravity-holography/spacetime-gravity-toolkit/causal-structure/) page explains why the commutator is controlled by retarded and advanced propagation rather than by the particle basis.

## Research status

Mode expansions for free fields on fixed backgrounds are standard. They remain one of the most useful computational tools in QFT in curved spacetime.

The subtlety is interpretive, not algebraic. In nonstationary spacetimes, the same field algebra can support many inequivalent Fock representations in the infinite-volume limit. Modern algebraic approaches therefore treat the local algebra and physically admissible states as more primitive than any one mode expansion. Mode language remains indispensable for calculations, but it should not be mistaken for the invariant definition of the theory.

## Exercises

### Exercise 1: Flat-space Klein–Gordon normalization

Show that the modes

$$
u_{\mathbf p}(x)
=\frac{e^{-iE_{\mathbf p}t+i\mathbf p\cdot\mathbf x}}
{\sqrt{2E_{\mathbf p}(2\pi)^{D-1}}}
$$

satisfy

$$
(u_{\mathbf p},u_{\mathbf q})_{\mathrm{KG}}
=\delta^{(D-1)}(\mathbf p-\mathbf q).
$$

<details><summary><strong>Solution</strong></summary>

On a constant-$t$ slice, $n^\mu=(1,\mathbf0)$ and $d\Sigma=d^{D-1}\mathbf x$. Thus

$$
(u_{\mathbf p},u_{\mathbf q})_{\mathrm{KG}}
=i\int d^{D-1}\mathbf x\,
\left(u_{\mathbf p}^*\partial_tu_{\mathbf q}
-u_{\mathbf q}\partial_tu_{\mathbf p}^*\right).
$$

Using $\partial_tu_{\mathbf q}=-iE_{\mathbf q}u_{\mathbf q}$ and $\partial_tu_{\mathbf p}^*=iE_{\mathbf p}u_{\mathbf p}^*$, the integrand gives a factor $E_{\mathbf p}+E_{\mathbf q}$. The spatial integral gives

$$
\int d^{D-1}\mathbf x\,
 e^{i(\mathbf q-\mathbf p)\cdot\mathbf x}
=(2\pi)^{D-1}\delta^{(D-1)}(\mathbf p-\mathbf q).
$$

The delta function sets $E_{\mathbf p}=E_{\mathbf q}$, so the normalization factor gives one. Hence

$$
(u_{\mathbf p},u_{\mathbf q})_{\mathrm{KG}}
=\delta^{(D-1)}(\mathbf p-\mathbf q).
$$

</details>

### Exercise 2: Negative norm of conjugate modes

Using the definition of the Klein–Gordon inner product, show that

$$
(u^*,u^*)_{\mathrm{KG}}=-(u,u)_{\mathrm{KG}}.
$$

<details><summary><strong>Solution</strong></summary>

By definition,

$$
(u^*,u^*)_{\mathrm{KG}}
=i\int_\Sigma d\Sigma\,n_\mu
\left(u\nabla^\mu u^*-u^*\nabla^\mu u\right).
$$

This is minus

$$
i\int_\Sigma d\Sigma\,n_\mu
\left(u^*\nabla^\mu u-u\nabla^\mu u^*\right),
$$

which is $-(u,u)_{\mathrm{KG}}$.

</details>

### Exercise 3: Surface independence of the inner product

Let $u$ and $v$ solve $Pu=Pv=0$. Show that $(u,v)_{\mathrm{KG}}$ is independent of the Cauchy surface if no boundary flux is present.

<details><summary><strong>Solution</strong></summary>

Define

$$
j^\mu=i\left(u^*\nabla^\mu v-v\nabla^\mu u^*\right).
$$

A direct calculation gives

$$
\nabla_\mu j^\mu
=i\left(u^*\Box_gv-v\Box_gu^*\right).
$$

Since $Pu=Pv=0$ and $m^2+\xi R$ is real,

$$
\Box_gv=-(m^2+\xi R)v,
\qquad
\Box_gu^*=-(m^2+\xi R)u^*.
$$

Therefore $\nabla_\mu j^\mu=0$. Integrating this conservation law over the spacetime region between two Cauchy surfaces and using Gauss's theorem gives equality of the two surface integrals when the side-boundary flux vanishes.

</details>

### Exercise 4: Wronskian condition in cosmology

For the four-dimensional conformal-time expansion with $\chi_k=a u_k$, show that canonical normalization gives

$$
\chi_k\chi_k^{*\prime}-\chi_k^*\chi_k'=i.
$$

<details><summary><strong>Solution</strong></summary>

In the metric $ds^2=a(\eta)^2(d\eta^2-d\mathbf x^2)$, a constant-$\eta$ slice has the Klein–Gordon product

$$
(u_k,u_k)_{\mathrm{KG}}
=i a^2\left(u_k^*u_k'-u_ku_k^{*\prime}\right)
$$

per momentum delta-function normalization. Setting $u_k=\chi_k/a$ gives

$$
a^2(u_k^*u_k'-u_ku_k^{*\prime})
=\chi_k^*\chi_k'-\chi_k\chi_k^{*\prime}.
$$

The convention $(u_k,u_k)_{\mathrm{KG}}=1$ is therefore equivalent to

$$
\chi_k\chi_k^{*\prime}-\chi_k^*\chi_k'=i,
$$

after rearranging the sign. Different Fourier conventions may move the sign into the definition of positive-frequency modes.

</details>

## References

- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, Cambridge University Press, 1982.
- R. M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994.
- S. A. Fulling, *Aspects of Quantum Field Theory in Curved Spacetime*, Cambridge University Press, 1989.
- L. Parker and D. Toms, *Quantum Field Theory in Curved Spacetime*, Cambridge University Press, 2009.
- B. S. DeWitt, *The Global Approach to Quantum Field Theory*, Oxford University Press, 2003.
- S. M. Carroll, *Spacetime and Geometry*, Addison-Wesley, 2004.

## Version history

- 2026-07-01: Added a polished page on mode expansions and positive-frequency choices in curved spacetime.
