---
title: "Retarded Green Functions"
description: "How to compute holographic retarded two-point functions from infalling bulk solutions, renormalized canonical momenta, and linear response."
sidebar:
  order: 50
---

## Why this matters

The previous page explained the real-time prescription at the level of principle: retarded correlators are computed by Lorentzian bulk fields that fall through the future horizon. This page turns that principle into a calculation.

The central boundary object is

$$
G_R(t,\mathbf{x})
=
-i\theta(t)
\langle[\mathcal O(t,\mathbf{x}),\mathcal O(0,\mathbf{0})]\rangle .
$$

It is the kernel that relates a small source to a causal response:

$$
\delta\langle\mathcal O(\omega,\mathbf{k})\rangle
=
G_R(\omega,\mathbf{k})J(\omega,\mathbf{k}) .
$$

In holography, this response is not guessed. It is extracted from the renormalized radial canonical momentum of a bulk field whose boundary value is $J$.

The short practical formula is

$$
\boxed{
G_R(\omega,\mathbf{k})
=
\frac{\delta \Pi_{\rm ren}(\omega,\mathbf{k})}
{\delta \phi_{(0)}(\omega,\mathbf{k})}
\bigg|_{\rm infalling}
}
$$

where $\phi_{(0)}$ is the boundary source and $\Pi_{\rm ren}$ is the finite response after adding counterterms.

## Linear response on the boundary

Couple a source $J$ to an operator $\mathcal O$:

$$
\delta S_{\rm QFT}
=
\int d^dx\,J(x)\mathcal O(x) .
$$

To first order in $J$,

$$
\delta\langle\mathcal O(x)\rangle
=
\int d^dy\,G_R(x-y)J(y) .
$$

The step function in $G_R$ is not decorative: it enforces causality. A source at time $y^0$ cannot affect an expectation value at an earlier time $x^0<y^0$.

With Fourier convention

$$
J(t,\mathbf{x})
=
\int\frac{d\omega\,d^{d-1}k}{(2\pi)^d}
 e^{-i\omega t+i\mathbf{k}\cdot\mathbf{x}}J(\omega,\mathbf{k}),
$$

linear response becomes multiplication:

$$
\delta\langle\mathcal O(\omega,\mathbf{k})\rangle
=
G_R(\omega,\mathbf{k})J(\omega,\mathbf{k}) .
$$

The spectral density is

$$
\rho(\omega,\mathbf{k})
=
-2\operatorname{Im}G_R(\omega,\mathbf{k}) .
$$

For a stable thermal state and a Hermitian operator, $\rho$ measures physical spectral weight. In holography, its imaginary part is tied to absorption by the black-brane horizon.

## Bulk setup

Use the planar AdS black-brane metric

$$
ds^2
=
\frac{L^2}{z^2}
\left[-f(z)dt^2+d\mathbf{x}^{2}+\frac{dz^2}{f(z)}\right],
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d,
$$

with

$$
T=\frac{d}{4\pi z_h} .
$$

For a scalar field dual to $\mathcal O$, take

$$
S_L[\phi]
=
-\frac{\mathcal N_\phi}{2}
\int d^{d+1}x\sqrt{-g}\,
\left(g^{MN}\partial_M\phi\partial_N\phi+m^2\phi^2\right) .
$$

The overall normalization $\mathcal N_\phi$ depends on the ten-dimensional reduction, the five-dimensional Newton constant, and the convention used to normalize $\mathcal O$. For the logic of the prescription, it can be kept explicit.

For a Fourier mode

$$
\phi(t,z,\mathbf{x})
=
e^{-i\omega t+i\mathbf{k}\cdot\mathbf{x}}\phi_{\omega,\mathbf{k}}(z),
$$

the wave equation is

$$
\frac{1}{\sqrt{-g}}\partial_z
\left(\sqrt{-g}g^{zz}\partial_z\phi\right)
+
\left(g^{tt}\omega^2+g^{ij}k_i k_j-m^2\right)\phi=0 .
$$

The calculation has two ends:

$$
\text{AdS boundary: source and response},
\qquad
\text{horizon: causal interior condition}.
$$

<figure class="doc-figure" style="--figure-width: 56rem;">

![Retarded Green function workflow](/figures/course/retarded-green-functions.svg)

<figcaption>

A holographic retarded two-point function is a linear-response computation. Specify the boundary source $\phi_{(0)}$, solve the bulk equation with infalling behavior at the future horizon, extract the renormalized response $\Pi_{\rm ren}$, and differentiate. Poles occur when the source coefficient can vanish while the infalling response remains nonzero.

</figcaption>
</figure>

## Boundary expansion and the response coefficient

Near the boundary, the scalar behaves as

$$
\phi(z;k)
=
z^{d-\Delta}\left[\phi_{(0)}(k)+\cdots\right]
+
z^\Delta\left[A(k)+\cdots\right],
\qquad
k=(\omega,\mathbf{k}),
$$

where

$$
m^2L^2=\Delta(\Delta-d) .
$$

In standard quantization, $\phi_{(0)}$ is the source. The coefficient $A(k)$ is the nonlocal response data. After holographic renormalization,

$$
\langle\mathcal O(k)\rangle
=
\mathcal N_\phi(2\Delta-d)A(k)
+
\text{local terms in }\phi_{(0)}(k),
$$

for a scalar with no special logarithmic subtleties. The local terms are contact terms or scheme-dependent analytic pieces. They can change polynomial pieces of $G_R$, but not its nonlocal singularities.

Thus the nonlocal part of the retarded correlator is schematically

$$
G_R(k)
=
\mathcal N_\phi(2\Delta-d)
\frac{A(k)}{\phi_{(0)}(k)}
+
\text{contact terms},
$$

where $A/\phi_{(0)}$ is computed using the infalling bulk solution.

## Canonical momentum form

The more invariant way to write the prescription uses radial canonical momentum. Varying the scalar action gives a boundary term

$$
\delta S_L\big|_{\text{on-shell}}
=
\int_{z=\epsilon}\frac{d^dk}{(2\pi)^d}\,
\Pi(\epsilon;-k)\delta\phi(\epsilon;k),
$$

with

$$
\Pi(z;k)
=
-\mathcal N_\phi\sqrt{-g}\,g^{zz}\partial_z\phi(z;k),
$$

up to the sign chosen for the outward normal. The renormalized momentum is

$$
\Pi_{\rm ren}(k)
=
\lim_{\epsilon\to0}
\left[
\epsilon^{\Delta-d}\Pi(\epsilon;k)+\Pi_{\rm ct}(\epsilon;k)
\right],
$$

where the power of $\epsilon$ shown here is the schematic conversion to the source normalization. A careful calculation uses the precise Fefferman–Graham expansion and the variation of $S_{\rm ren}$.

At linear order,

$$
\Pi_{\rm ren}(k)=G_R(k)\phi_{(0)}(k).
$$

Therefore

$$
\boxed{
G_R(k)
=
\frac{\Pi_{\rm ren}(k)}{\phi_{(0)}(k)}
\bigg|_{\rm linear,\ infalling}
}
$$

when the solution has been normalized to the desired boundary source. For multiple fields, this equation becomes a matrix relation.

## The infalling solution

Near the horizon,

$$
f(z)\simeq 4\pi T(z_h-z).
$$

The radial equation has two independent behaviors:

$$
\phi(z;k)
\sim
\left(1-\frac{z}{z_h}\right)^{-i\omega/(4\pi T)},
\qquad
\phi(z;k)
\sim
\left(1-\frac{z}{z_h}\right)^{+i\omega/(4\pi T)} .
$$

The retarded function uses the first behavior. In ingoing Eddington–Finkelstein time

$$
v=t-z_*,
\qquad
z_*\sim-\frac{1}{4\pi T}\log\!\left(1-\frac{z}{z_h}\right),
$$

an infalling mode is regular:

$$
e^{-i\omega v}
=
e^{-i\omega t}
\left(1-\frac{z}{z_h}\right)^{-i\omega/(4\pi T)} .
$$

This condition says that the boundary perturbation may be absorbed by the future horizon. It does not allow independent radiation to emerge from behind the future horizon.

## A step-by-step recipe

For a scalar two-point function in a thermal state:

1. Choose the bulk field dual to $\mathcal O$ and write its quadratic action.
2. Fourier transform along the boundary directions.
3. Solve the radial equation with infalling behavior at $z=z_h$.
4. Normalize the solution near $z=0$ so that the source coefficient is $\phi_{(0)}(k)$.
5. Compute the on-shell boundary term or radial canonical momentum.
6. Add counterterms and take $z\to0$.
7. Read off

   $$
   \delta\langle\mathcal O(k)\rangle
   =
   G_R(k)\phi_{(0)}(k).
   $$

For numerical work, a common trick is to write

$$
\phi(z;k)
=
\left(1-\frac{z}{z_h}\right)^{-i\omega/(4\pi T)}F(z;k),
$$

where $F$ is regular at the horizon. One integrates from the horizon to the boundary, then extracts the source and response coefficients.

## Coupled fields and response matrices

Many important correlators are not single-field problems. Metric and gauge perturbations can mix. For example, at finite density, $a_x$ and $h_{tx}$ often couple. For stress-tensor correlators, diffeomorphism constraints mix metric components.

Suppose the independent sources are $J_a$ and the renormalized responses are $R_a$. Linear response gives

$$
R_a(k)=G_{R,ab}(k)J_b(k).
$$

In the bulk, one constructs a basis of infalling solutions labelled by boundary source data. In matrix notation,

$$
G_R(k)=R(k)J(k)^{-1},
$$

after adding counterterms and projecting onto gauge-invariant source and response variables.

This is why gauge invariance matters. A pole of a gauge-dependent component is not necessarily a physical pole. The clean objects are gauge-invariant master fields or the full renormalized response matrix.

## Flux and spectral weight

For real $\omega$, the scalar equation has a conserved radial flux

$$
\mathcal F_z
=
\frac{i\mathcal N_\phi}{2}
\sqrt{-g}g^{zz}
\left(
\phi^*\partial_z\phi-\phi\partial_z\phi^*
\right).
$$

This flux is independent of $z$ when the coefficients of the radial equation are real. Evaluated near the boundary, it is related to the imaginary part of $G_R$. Evaluated at the horizon, the infalling condition turns it into an absorption flux.

This gives the geometric meaning of dissipation:

$$
\operatorname{Im}G_R
\quad
\longleftrightarrow
\quad
\text{absorption by the horizon}.
$$

The horizon is therefore not just a place where the bulk calculation ends. It is the bulk mechanism by which the thermal CFT loses memory of perturbations.

## Hydrodynamic preview

Retarded functions encode transport. A conserved density with diffusion has a retarded correlator of the schematic form

$$
G_R^{nn}(\omega,\mathbf{k})
=
\frac{\chi D\mathbf{k}^2}{-i\omega+D\mathbf{k}^2}
+
\text{contact terms},
$$

where $\chi$ is the susceptibility and $D$ is the diffusion constant. The pole

$$
\omega=-iD\mathbf{k}^2
$$

is a hydrodynamic relaxation mode.

Similarly, shear viscosity is extracted from a stress-tensor retarded function by a Kubo formula,

$$
\eta
=
-
\lim_{\omega\to0}
\frac{1}{\omega}
\operatorname{Im}G_R^{T^{xy}T^{xy}}(\omega,\mathbf{0}) .
$$

The next pages develop the pole interpretation and the hydrodynamic limit more systematically.

## Analytic structure

A retarded correlator is analytic in the upper half of the complex $\omega$ plane for a stable causal thermal state. Poles lie in the lower half plane:

$$
\operatorname{Im}\omega_n<0 .
$$

In time domain, a pole at

$$
\omega_n=\Omega_n-i\Gamma_n,
\qquad
\Gamma_n>0,
$$

contributes a late-time behavior

$$
e^{-i\omega_n t}=e^{-i\Omega_n t}e^{-\Gamma_n t},
\qquad t>0 .
$$

In holography, these poles are quasinormal modes of the black brane.

## Dictionary checkpoint

| Boundary quantity | Bulk computation |
|---|---|
| source $J=\phi_{(0)}$ | non-normalizable boundary coefficient |
| response $\delta\langle\mathcal O\rangle$ | renormalized radial canonical momentum |
| $G_R=\delta\langle\mathcal O\rangle/\delta J$ | infalling linear solution differentiated at the boundary |
| spectral density $\rho=-2\operatorname{Im}G_R$ | absorption flux into the horizon |
| transport coefficient | small-$\omega$, small-$k$ limit of $G_R$ |
| relaxation pole | infalling, source-free bulk mode |
| coupled correlator matrix | matrix of renormalized responses to independent sources |

The retarded prescription is a boundary-value problem with a causal horizon condition.

## Common confusions

### “The retarded correlator is just the ratio $A/\phi_{(0)}$.”

That is only a useful shorthand. The correct object is the renormalized variation of the on-shell action. For simple scalars, the nonlocal part is often proportional to $A/\phi_{(0)}$, but counterterms, logarithms, operator normalization, alternate quantization, and mixing can modify the precise formula.

### “The imaginary part comes from the boundary.”

The boundary expansion can display $\operatorname{Im}G_R$, but its physical origin at finite temperature is horizon absorption. The conserved radial flux lets one evaluate the same imaginary part at the horizon.

### “Every pole is hydrodynamic.”

Hydrodynamic poles approach $\omega=0$ as $\mathbf{k}\to0$ because they are tied to conserved quantities. Generic quasinormal poles remain at complex frequencies of order $T$ and describe nonhydrodynamic relaxation.

### “Gauge fields and metric perturbations can be treated component by component.”

Not safely. Gauge and diffeomorphism constraints can mix components. Use gauge-invariant variables or the full source-response matrix.

### “The infalling condition is optional.”

For the retarded correlator in a thermal state, it is the defining Lorentzian interior condition. Choosing outgoing behavior computes a different causal object.

## Exercises

### Exercise 1: Retarded analyticity and late-time decay

Suppose a retarded Green function has a simple pole at

$$
\omega_* = \Omega-i\Gamma,
\qquad
\Gamma>0.
$$

Show that this pole gives a decaying contribution to the response for $t>0$.

<details>
<summary><strong>Solution</strong></summary>

For $t>0$, the inverse Fourier transform contains

$$
\int\frac{d\omega}{2\pi}\,e^{-i\omega t}G_R(\omega).
$$

Closing the contour in the lower half plane picks up poles with $\operatorname{Im}\omega<0$. A simple pole at $\omega_*$ gives

$$
e^{-i\omega_*t}
=
e^{-i\Omega t}e^{-\Gamma t} .
$$

Thus the imaginary part $-\Gamma$ gives decay. A pole in the upper half plane would grow exponentially and signal an instability or an acausal prescription.

</details>

### Exercise 2: Source and response from a normalized solution

Let an infalling scalar solution near the boundary behave as

$$
\phi(z;k)=J(k)z^{d-\Delta}+A(k)z^\Delta+\cdots .
$$

Assume standard quantization and no logarithmic subtleties. What is the nonlocal part of $G_R(k)$?

<details>
<summary><strong>Solution</strong></summary>

The source is $J(k)$. The nonlocal response is proportional to $A(k)$. For a scalar with normalization $\mathcal N_\phi$,

$$
\langle\mathcal O(k)\rangle
=
\mathcal N_\phi(2\Delta-d)A(k)+\text{local terms}.
$$

Therefore the nonlocal part of the retarded two-point function is

$$
G_R(k)
=
\mathcal N_\phi(2\Delta-d)\frac{A(k)}{J(k)}
+
\text{contact terms}.
$$

The infalling condition is what makes this the retarded correlator rather than another Green function.

</details>

### Exercise 3: Why coupled fields require a matrix

Suppose two bulk fields have boundary expansions with sources $J_1,J_2$ and responses $R_1,R_2$. Explain why computing only $R_1/J_1$ with $J_2$ accidentally nonzero does not give $G_{11}$.

<details>
<summary><strong>Solution</strong></summary>

Linear response has the matrix form

$$
\begin{pmatrix}R_1\\ R_2\end{pmatrix}
=
\begin{pmatrix}G_{11}&G_{12}\\G_{21}&G_{22}\end{pmatrix}
\begin{pmatrix}J_1\\ J_2\end{pmatrix} .
$$

If $J_2\ne0$, then

$$
R_1=G_{11}J_1+G_{12}J_2.
$$

The ratio $R_1/J_1$ is not $G_{11}$ unless $J_2=0$ or $G_{12}J_2$ is known and subtracted. In practice one constructs independent infalling solutions, forms the source matrix $J$, forms the response matrix $R$, and computes

$$
G=RJ^{-1}.
$$

</details>

## Further reading

- D. T. Son and A. O. Starinets, [Minkowski-space correlators in AdS/CFT correspondence: recipe and applications](https://arxiv.org/abs/hep-th/0205051).
- G. Policastro, D. T. Son, and A. O. Starinets, [Shear viscosity of strongly coupled $\mathcal N=4$ supersymmetric Yang–Mills plasma](https://arxiv.org/abs/hep-th/0104066).
- C. P. Herzog and D. T. Son, [Schwinger-Keldysh propagators from AdS/CFT correspondence](https://arxiv.org/abs/hep-th/0212072).
- K. Skenderis and B. C. van Rees, [Real-time gauge/gravity duality](https://arxiv.org/abs/0812.2909).
- D. T. Son, [Viscosity, Black Holes, and Quantum Field Theory](https://arxiv.org/abs/0704.0240).
