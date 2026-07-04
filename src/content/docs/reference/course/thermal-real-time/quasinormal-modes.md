---
title: "Quasinormal Modes"
description: "Why black-brane quasinormal frequencies are poles of retarded Green functions and how they encode relaxation in the dual thermal field theory."
sidebar:
  order: 60
---

## Why this matters

A thermal state forgets perturbations. In a weakly coupled gas, relaxation can be described by kinetic theory and quasiparticle collisions. In a strongly coupled holographic plasma, relaxation is encoded geometrically by perturbations falling into a black-brane horizon.

The frequencies that control this relaxation are quasinormal modes. In holography,

$$
\boxed{
\text{quasinormal frequencies of the black brane}
\quad\longleftrightarrow\quad
\text{poles of }G_R(\omega,\mathbf{k})
}
$$

for the dual operator or response channel.

This page explains the statement carefully. The key point is simple: retarded correlators are ratios of response coefficients to source coefficients. A pole occurs when the source coefficient vanishes while a nonzero infalling response remains. That is precisely the quasinormal-mode boundary-value problem.

## Definition

Consider a linearized bulk perturbation $\Phi(z)$ with Fourier dependence

$$
\Phi(t,z,\mathbf{x})
=
e^{-i\omega t+i\mathbf{k}\cdot\mathbf{x}}\Phi(z).
$$

In a black-brane background, a quasinormal mode is a nontrivial solution satisfying:

$$
\text{infalling at the future horizon},
$$

and

$$
\text{source-free at the AdS boundary}.
$$

For a scalar in standard quantization, the near-boundary expansion is

$$
\Phi(z;k)
=
z^{d-\Delta}J(k)+z^\Delta A(k)+\cdots .
$$

The source-free condition is

$$
J(k)=0,
$$

while the mode is nonzero because $A(k)\ne0$.

The allowed frequencies are discrete at fixed $\mathbf{k}$ for a standard AdS black brane:

$$
\omega=\omega_n(\mathbf{k}) .
$$

For a stable equilibrium black brane, they lie in the lower half plane:

$$
\operatorname{Im}\omega_n(\mathbf{k})<0 .
$$

## How the pole appears

Normalize an infalling solution in the interior and read its boundary expansion:

$$
\Phi_{\rm in}(z;k)
=
z^{d-\Delta}J(k)+z^\Delta A(k)+\cdots .
$$

For a generic frequency, $J(k)\ne0$. To compute a retarded correlator with unit source, divide by $J(k)$:

$$
\Phi_{J=1}(z;k)
=
\frac{\Phi_{\rm in}(z;k)}{J(k)} .
$$

Then the response coefficient is $A(k)/J(k)$, so

$$
G_R(k)
\sim
\frac{A(k)}{J(k)}
+
\text{contact terms}.
$$

A pole occurs when

$$
J(k)=0,
\qquad
A(k)\ne0 .
$$

But this is exactly the quasinormal-mode condition: an infalling solution with no source at the boundary. Thus quasinormal frequencies are poles of the retarded Green function.

<figure class="doc-figure" style="--figure-width: 55rem;">

![Quasinormal modes as retarded poles](/figures/course/quasinormal-modes-poles.svg)

<figcaption>

A quasinormal mode is an infalling, source-free bulk perturbation. In the boundary Green function, this appears as a pole of $G_R(\omega,\mathbf{k})$. Stable thermal states have poles in the lower half of the complex $\omega$ plane; hydrodynamic poles approach the origin as $|\mathbf{k}|\to0$.

</figcaption>
</figure>

## Normal modes versus quasinormal modes

It is useful to compare three cases.

| Bulk geometry | Boundary condition in the interior | Frequency spectrum | Boundary interpretation |
|---|---|---|---|
| global AdS without horizon | regular at the center | real normal modes | stable states on the cylinder |
| AdS black brane | infalling at horizon | complex quasinormal modes | relaxation in a thermal state |
| asymptotically flat black hole | outgoing at infinity, infalling at horizon | complex quasinormal modes | ringdown with energy leakage |

In global AdS, there is no horizon to absorb energy. Normal modes do not decay. In an AdS black brane, the horizon absorbs perturbations, and the dual thermal state dissipates.

The word “quasinormal” signals two facts:

$$
\text{not normalizable as a Hermitian eigenvalue problem},
\qquad
\text{not generally real-valued frequencies}.
$$

The radial problem is non-Hermitian because the horizon boundary condition is dissipative.

## Horizon boundary condition

Near a nonextremal horizon,

$$
\Phi(z)
\sim
\left(1-\frac{z}{z_h}\right)^{-i\omega/(4\pi T)}
\quad\text{or}\quad
\left(1-\frac{z}{z_h}\right)^{+i\omega/(4\pi T)} .
$$

The retarded quasinormal-mode condition uses the infalling branch:

$$
\Phi(z)
\sim
\left(1-\frac{z}{z_h}\right)^{-i\omega/(4\pi T)} .
$$

In ingoing Eddington–Finkelstein coordinates, this is the branch regular at the future horizon. This is the same interior condition used for retarded Green functions.

For complex $\omega$, one should define the condition by analytic continuation from real $\omega$ or by working directly in regular ingoing coordinates. The phrase “infalling” is then a shorthand for future-horizon regularity in the retarded prescription.

## Boundary condition at infinity

The boundary condition depends on the field and quantization. For a scalar in standard quantization,

$$
\Phi(z;k)
=
z^{d-\Delta}J(k)+z^\Delta A(k)+\cdots,
$$

and the quasinormal boundary condition is

$$
J(k)=0 .
$$

For a bulk gauge field,

$$
A_i(z;k)=a_i(k)+z^{d-2}b_i(k)+\cdots,
$$

and the source-free condition is $a_i=0$, modulo gauge issues.

For metric perturbations,

$$
h_{ij}(z;k)=h_{(0)ij}(k)+z^d h_{(d)ij}(k)+\cdots,
$$

and the source-free condition is $h_{(0)ij}=0$, again imposed on gauge-invariant combinations or with a complete gauge-fixed source-response analysis.

## Coupled systems and determinant conditions

In coupled channels, the quasinormal-mode condition is not simply “one coefficient vanishes.” Suppose there are $n$ independent sources $J_a$ and $n$ responses $R_a$. Construct $n$ independent infalling bulk solutions. Their source coefficients form an $n\times n$ matrix $J_{ab}(\omega,\mathbf{k})$.

A source-free nontrivial linear combination exists when

$$
\det J(\omega,\mathbf{k})=0 .
$$

The retarded correlator matrix is schematically

$$
G_R(\omega,\mathbf{k})=R(\omega,\mathbf{k})J(\omega,\mathbf{k})^{-1},
$$

so zeros of $\det J$ become poles of the matrix, unless they are cancelled by zeros in the response matrix. Such cancellations can occur in special variables or gauge-dependent quantities, which is another reason to use gauge-invariant channels.

## Hydrodynamic quasinormal modes

Hydrodynamic poles are quasinormal modes controlled by conserved quantities. They approach the origin as $\mathbf{k}\to0$.

A diffusion pole has

$$
\omega(\mathbf{k})
=
-iD\mathbf{k}^2+O(\mathbf{k}^4).
$$

A sound channel in a relativistic conformal plasma has

$$
\omega_\pm(\mathbf{k})
=
\pm c_s |\mathbf{k}|-i\Gamma_s\mathbf{k}^2+O(|\mathbf{k}|^3),
$$

where conformality gives

$$
c_s^2=\frac{1}{d-1}
$$

for a $d$-dimensional boundary CFT.

For a neutral holographic plasma with two-derivative Einstein gravity, the shear diffusion constant is

$$
D_\eta=\frac{\eta}{\epsilon+p}
=
\frac{1}{4\pi T},
$$

using $\eta/s=1/(4\pi)$ and $\epsilon+p=sT$ at zero chemical potential.

Hydrodynamic quasinormal modes are special because their frequencies vanish at small momentum. Nonhydrodynamic modes usually remain at

$$
\omega\sim T
$$

in both real and imaginary parts.

## Nonhydrodynamic modes

A black brane has an infinite tower of nonhydrodynamic quasinormal modes. These modes encode relaxation not captured by hydrodynamics.

At late times, the pole closest to the real axis dominates the nonhydrodynamic part of the response:

$$
\delta\langle\mathcal O(t)\rangle
\sim
\sum_n c_n e^{-i\omega_n t}
=
\sum_n c_n e^{-i\operatorname{Re}\omega_n t}e^{\operatorname{Im}\omega_n t} .
$$

For stable modes, $\operatorname{Im}\omega_n<0$, so the contribution decays.

In many holographic plasmas, the distance from the origin to the nearest nonhydrodynamic pole sets a microscopic equilibration scale of order $1/T$. This statement is qualitative: the precise spectrum depends on the channel, theory, background, and finite-coupling corrections.

## Example: the pole logic in one equation

For a scalar in a black brane, define the infalling solution by its near-horizon behavior. Near the boundary write

$$
\Phi_{\rm in}(z;\omega,k)
=
J(\omega,k)z^{d-\Delta}
+
A(\omega,k)z^\Delta+\cdots .
$$

The retarded correlator has the schematic form

$$
G_R(\omega,k)
=
\mathcal C\frac{A(\omega,k)}{J(\omega,k)}
+
\text{contact terms} .
$$

Therefore

$$
J(\omega_n,k)=0
\quad\Rightarrow\quad
G_R(\omega,k)\text{ has a pole at }\omega=\omega_n,
$$

provided $A(\omega_n,k)\ne0$ and the pole is not removed by mixing or contact-term conventions.

This is the basic quasinormal-mode dictionary.

## Numerical methods

Most quasinormal spectra are found numerically. Common methods include:

- **shooting:** impose infalling behavior at the horizon and integrate to the boundary, then search for vanishing source;
- **Frobenius expansion:** expand around the horizon and solve recursively, matching to the boundary;
- **spectral collocation:** represent the radial profile by Chebyshev polynomials and turn the problem into a generalized eigenvalue problem;
- **determinant method:** for coupled fields, build the source matrix from independent infalling solutions and solve $\det J=0$.

For gravitational perturbations, it is usually best to decompose the problem into helicity or gauge-invariant channels: tensor, vector/shear, and scalar/sound channels for planar black branes.

## Stability, instabilities, and phase transitions

In a stable thermal state, all retarded poles lie below the real axis. If a mode crosses into the upper half plane,

$$
\operatorname{Im}\omega>0,
$$

then the perturbation grows exponentially. This signals an instability of the background or of the ensemble.

Examples include:

- charged black-brane instabilities leading to holographic superconductors;
- Gregory–Laflamme-type instabilities in certain extended geometries;
- scalar condensation when an effective mass violates an infrared stability bound.

A static onset mode has

$$
\omega=0,
$$

at a critical value of a parameter such as temperature, chemical potential, or magnetic field. It often marks the beginning of a new branch of solutions.

## Branch cuts and extremal horizons

At nonzero temperature and finite volume regularity conditions often lead to isolated poles. In infinite-volume thermal field theory, one still discusses poles at fixed momentum, but cuts can also appear in certain limits.

At zero temperature or near extremality, AdS$_2$ throats can produce branch cuts or densely spaced poles. In the boundary theory, this reflects infrared critical behavior rather than simple exponential relaxation by isolated modes.

So the slogan “QNMs are poles” is most straightforward for nonextremal black holes and black branes. More exotic infrared geometries require more care.

## Dictionary checkpoint

| Boundary thermal response | Bulk perturbation theory |
|---|---|
| pole of $G_R(\omega,\mathbf{k})$ | quasinormal frequency $\omega_n(\mathbf{k})$ |
| causal response | infalling/future-horizon condition |
| no external source | normalizable/source-free boundary condition |
| hydrodynamic pole | long-wavelength QNM tied to conservation law |
| nonhydrodynamic pole | microscopic black-brane relaxation mode |
| instability | QNM with $\operatorname{Im}\omega>0$ |
| transport coefficient | small-$\omega$, small-$k$ pole or Kubo limit |

Quasinormal modes are the spectral fingerprints of the black brane as seen by the boundary thermal state.

## Common confusions

### “Quasinormal modes are poles of Euclidean correlators.”

Euclidean correlators are defined at Matsubara frequencies. Quasinormal modes are poles of real-time retarded correlators in the complex frequency plane. Euclidean data may determine the analytic continuation in favorable cases, but the physical pole statement is Lorentzian.

### “The boundary condition is normalizable at both ends.”

At the AdS boundary, one imposes a source-free or normalizable condition. At the horizon, one imposes infalling behavior. The horizon condition is not normalizability; it is a causal dissipative condition.

### “All QNMs have nonzero real part.”

No. Diffusion modes are purely imaginary at small momentum. Instability onsets can occur at $\omega=0$. Sound modes have real parts at nonzero momentum. The spectrum depends on the channel.

### “Every zero of a source coefficient is a physical mode.”

Only after gauge constraints and coupled-field structure are handled correctly. Gauge-dependent variables can contain spurious singularities or miss physical ones.

### “A pole close to the origin always means hydrodynamics.”

Hydrodynamic poles are tied to conservation laws and have controlled small-$k$ dispersion. A nonhydrodynamic pole can move close to the origin near a critical point or instability, but that does not automatically make it hydrodynamic.

## Exercises

### Exercise 1: Pole from a source coefficient

Suppose an infalling scalar solution has boundary coefficients $J(\omega)$ and $A(\omega)$, and

$$
G_R(\omega)=\mathcal C\frac{A(\omega)}{J(\omega)} .
$$

If $J(\omega_*)=0$, $J'(\omega_*)\ne0$, and $A(\omega_*)\ne0$, show that $G_R$ has a simple pole at $\omega_*$.

<details>
<summary><strong>Solution</strong></summary>

Near $\omega_*$,

$$
J(\omega)=J'(\omega_*)(\omega-\omega_*)+O((\omega-\omega_*)^2),
$$

while

$$
A(\omega)=A(\omega_*)+O(\omega-\omega_*).
$$

Thus

$$
G_R(\omega)
=
\mathcal C\frac{A(\omega_*)}{J'(\omega_*)}
\frac{1}{\omega-\omega_*}
+
\text{regular terms}.
$$

This is a simple pole. The condition $J(\omega_*)=0$ is the source-free boundary condition, while infalling behavior was already built into the solution.

</details>

### Exercise 2: Diffusion pole in time

A diffusive retarded correlator has a pole at

$$
\omega=-iDk^2,
\qquad D>0.
$$

What time dependence does this pole imply for fixed spatial momentum $k$?

<details>
<summary><strong>Solution</strong></summary>

The pole contributes

$$
e^{-i\omega t}
=
e^{-i(-iDk^2)t}
=
e^{-Dk^2t}
$$

for $t>0$. This is diffusion: long-wavelength perturbations decay slowly, with a decay time

$$
\tau_k=\frac{1}{Dk^2} .
$$

As $k\to0$, the mode becomes arbitrarily slow because it is tied to a conserved density.

</details>

### Exercise 3: Why pure global AdS has real normal modes

Why do scalar normal modes in pure global AdS have real frequencies, while black-brane quasinormal modes are generally complex?

<details>
<summary><strong>Solution</strong></summary>

Pure global AdS has no horizon. With regularity at the center and normalizable behavior at the boundary, the scalar wave equation forms a self-adjoint eigenvalue problem under the appropriate inner product. Its frequencies are real, and the corresponding CFT states on the cylinder do not decay.

A black brane has a horizon. The infalling boundary condition lets energy flow into the horizon and makes the radial eigenvalue problem non-Hermitian. The frequencies are therefore generally complex. Their negative imaginary parts encode decay of perturbations in the boundary thermal state.

</details>

## Further reading

- D. T. Son and A. O. Starinets, [Minkowski-space correlators in AdS/CFT correspondence: recipe and applications](https://arxiv.org/abs/hep-th/0205051).
- G. T. Horowitz and V. E. Hubeny, [Quasinormal modes of AdS black holes and the approach to thermal equilibrium](https://arxiv.org/abs/hep-th/9909056).
- D. Birmingham, I. Sachs, and S. N. Solodukhin, [Conformal field theory interpretation of black hole quasinormal modes](https://arxiv.org/abs/hep-th/0112055).
- E. Berti, V. Cardoso, and A. O. Starinets, [Quasinormal modes of black holes and black branes](https://arxiv.org/abs/0905.2975).
- P. K. Kovtun and A. O. Starinets, [Quasinormal modes and holography](https://arxiv.org/abs/hep-th/0506184).
