---
title: "Green Functions Cheatsheet"
description: "A compact reference for Euclidean, retarded, advanced, Feynman, Wightman, spectral, and thermal Green functions used throughout AdS/CFT."
sidebar:
  order: 50
---

Green functions are where the AdS/CFT dictionary becomes useful as a machine for physics. They encode sources and responses, transport coefficients, spectral weight, screening, quasinormal modes, thermal fluctuations, and the difference between Euclidean and Lorentzian questions.

They are also where small convention changes create large confusion. One paper defines the spectral function as $-2\operatorname{Im}G_R$, another as $+2\operatorname{Im}G_R$; one source is inserted as $+\int J\mathcal O$, another as $-\int J\mathcal O$; one author calls a function $G$ while another calls $iG$ the Green function. This appendix fixes the conventions used in this course and gives a translation guide.

We mostly discuss a bosonic Hermitian scalar operator $\mathcal O$. Currents, stress tensors, and fermionic operators are summarized later.

## Fourier convention

The Lorentzian Fourier convention is

$$
f(t,\mathbf x)
=
\int \frac{d\omega}{2\pi}
\frac{d^{d-1}\mathbf k}{(2\pi)^{d-1}}
 e^{-i\omega t+i\mathbf k\cdot \mathbf x}
 f(\omega,\mathbf k),
$$

with inverse

$$
f(\omega,\mathbf k)
=
\int dt\,d^{d-1}\mathbf x\,
 e^{i\omega t-i\mathbf k\cdot \mathbf x}
 f(t,\mathbf x).
$$

A damped mode behaves as

$$
e^{-i\omega_*t},
\qquad
\operatorname{Im}\omega_*<0.
$$

So stable retarded poles lie in the lower half of the complex $\omega$ plane.

## Thermal expectation values

At finite temperature,

$$
\langle X\rangle_\beta
=
\frac{\operatorname{Tr}(e^{-\beta H}X)}
{\operatorname{Tr}(e^{-\beta H})}.
$$

At zero temperature, replace $\langle\cdots\rangle_\beta$ by the vacuum expectation value. In most formulas below the subscript $\beta$ is suppressed.

For finite chemical potential associated with a charge $Q$,

$$
\rho_{\rm th}
=
\frac{e^{-\beta(H-\mu Q)}}
{\operatorname{Tr}e^{-\beta(H-\mu Q)}}.
$$

The KMS relation is then modified by charge-dependent factors for charged operators. For neutral bosonic operators, the formulas below are unchanged.

## Linear response and the retarded function

Perturb the Hamiltonian by a weak source,

$$
H(t)=H_0-\int d^{d-1}\mathbf x\,J(t,\mathbf x)\mathcal O(t,\mathbf x).
$$

The first-order response is

$$
\delta\langle \mathcal O(t,\mathbf x)\rangle
=
\int dt'\,d^{d-1}\mathbf y\,
G_R(t-t',\mathbf x-\mathbf y)J(t',\mathbf y),
$$

where

$$
G_R(t,\mathbf x)
=
-i\theta(t)\langle[\mathcal O(t,\mathbf x),\mathcal O(0,\mathbf 0)]\rangle.
$$

In momentum space,

$$
\delta\langle \mathcal O(\omega,\mathbf k)\rangle
=
G_R(\omega,\mathbf k)J(\omega,\mathbf k).
$$

This is the real-time correlator computed by the infalling prescription in black-hole backgrounds.

For several operators $\mathcal O_a$ and sources $J^a$,

$$
\delta\langle \mathcal O_a(\omega,\mathbf k)\rangle
=
G^R_{ab}(\omega,\mathbf k)J^b(\omega,\mathbf k),
$$

with

$$
G^R_{ab}(t,\mathbf x)
=
-i\theta(t)\langle[\mathcal O_a(t,\mathbf x),\mathcal O_b(0,\mathbf 0)]\rangle.
$$

The word “retarded” means causal: the expectation value at time $t$ depends only on the source at earlier times.

## The main real-time correlators

| Name | Definition | What it is good for |
|---|---|---|
| Greater/Wightman | $G^>(x)=\langle \mathcal O(x)\mathcal O(0)\rangle$ | unordered fluctuations, emission |
| Lesser/Wightman | $G^<(x)=\langle \mathcal O(0)\mathcal O(x)\rangle$ | unordered fluctuations, absorption |
| Spectral kernel | $\rho(x)=\langle[\mathcal O(x),\mathcal O(0)]\rangle$ | causal commutator, spectral density |
| Retarded | $G_R(x)=-i\theta(t)\rho(x)$ | linear response |
| Advanced | $G_A(x)=+i\theta(-t)\rho(x)$ | advanced response, analytic partner of $G_R$ |
| Feynman/time ordered | $G_F(x)=-i\langle T\mathcal O(x)\mathcal O(0)\rangle$ | vacuum perturbation theory, scattering conventions |
| Symmetrized | $G_{\rm sym}(x)=\frac12\langle\{\mathcal O(x),\mathcal O(0)\}\rangle$ | noise and equilibrium fluctuations |

The factor $-i$ in $G_F$ and $G_R$ is a Lorentzian QFT convention. Holographic papers sometimes define correlators directly as second variations of the on-shell action; then the same physical response may be called $iG$, $-G$, or $G$ depending on source conventions. The reliable object is the linear-response equation.

## Spectral function

Define the spectral function by the Fourier transform of the commutator:

$$
\rho(\omega,\mathbf k)
=
\int dt\,d^{d-1}\mathbf x\,
e^{i\omega t-i\mathbf k\cdot\mathbf x}
\langle[\mathcal O(t,\mathbf x),\mathcal O(0,\mathbf 0)]\rangle.
$$

With the retarded convention above,

$$
\rho(\omega,\mathbf k)
=
-2\operatorname{Im}G_R(\omega,\mathbf k)
$$

for real $\omega$, modulo contact terms that are real polynomials in $\omega$ and $\mathbf k$.

For a Hermitian bosonic operator,

$$
\rho(-\omega,-\mathbf k)=-\rho(\omega,\mathbf k).
$$

If the state is parity invariant, $\rho(\omega,-\mathbf k)=\rho(\omega,\mathbf k)$, and $\rho$ is odd in $\omega$.

Some communities define the plotted spectral weight as $+2\operatorname{Im}G_R$ instead. Do not compare signs between papers until the definition of $G_R$ and $\rho$ is checked.

## Analytic structure

Causality gives

$$
G_R(t,\mathbf x)=0
\qquad
(t<0).
$$

Therefore, under standard boundedness assumptions, $G_R(\omega,\mathbf k)$ is analytic in the upper half-plane,

$$
\operatorname{Im}\omega>0.
$$

The advanced correlator is analytic in the lower half-plane. For equilibrium states and Hermitian operators,

$$
G_A(\omega,\mathbf k)=G_R(\omega,\mathbf k)^*
$$

on the real $\omega$ axis, up to convention-dependent contact terms.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Green functions and analytic continuation](/figures/course/green-functions-cheatsheet.svg)

<figcaption>

One physical two-point function has many useful boundary values and real-time orderings. Euclidean data live at Matsubara frequencies, the retarded function computes causal response, $\rho=-2\operatorname{Im}G_R$ measures spectral weight in the convention of this page, and poles of $G_R$ are relaxation modes. In holography these poles are quasinormal modes.

</figcaption>
</figure>

For holographic black holes, stable quasinormal modes have $\operatorname{Im}\omega<0$ and become poles of $G_R$. A pole in the upper half-plane would signal an instability of the thermal state.

## Euclidean correlators

The Euclidean thermal correlator is

$$
G_E(\tau,\mathbf x)
=
\langle T_\tau \mathcal O(\tau,\mathbf x)\mathcal O(0,\mathbf 0)\rangle,
\qquad
0\leq \tau<\beta.
$$

For bosons,

$$
G_E(\tau+\beta,\mathbf x)=G_E(\tau,\mathbf x),
$$

and the Matsubara frequencies are

$$
\omega_n=2\pi nT.
$$

For fermions,

$$
\omega_n=(2n+1)\pi T,
$$

with anti-periodic thermal boundary conditions.

For bosons,

$$
G_E(i\omega_n,\mathbf k)
=
\int_0^\beta d\tau\int d^{d-1}\mathbf x\,
e^{i\omega_n \tau-i\mathbf k\cdot\mathbf x}
G_E(\tau,\mathbf x).
$$

Euclidean correlators are not retarded correlators. To obtain a retarded function from an equilibrium Euclidean correlator, analytically continue with a retarded prescription:

$$
i\omega_n\to \omega+i0^+.
$$

Equivalently, if the Euclidean frequency is written as a real variable $\omega_E$, the retarded continuation is schematically

$$
\omega_E\to -i(\omega+i0^+).
$$

The analytic continuation is the invariant part. The overall sign can change with the source convention. In a holographic computation, the safest retarded prescription is not to guess from Euclidean formulas, but to solve the Lorentzian bulk problem with infalling horizon boundary conditions and then vary the renormalized response with respect to the source.

## Spectral representation

For $\operatorname{Im}z>0$, the retarded function has the spectral representation

$$
G_R(z,\mathbf k)
=
\int_{-\infty}^{\infty}\frac{d\omega'}{2\pi}
\frac{\rho(\omega',\mathbf k)}{z-\omega'}
+
\text{contact terms}.
$$

Taking $z=\omega+i0^+$ gives

$$
G_R(\omega,\mathbf k)
=
\operatorname{P}\!\int_{-\infty}^{\infty}\frac{d\omega'}{2\pi}
\frac{\rho(\omega',\mathbf k)}{\omega-\omega'}
-
\frac{i}{2}\rho(\omega,\mathbf k)
+
\text{contact terms}.
$$

Thus

$$
\rho(\omega,\mathbf k)=-2\operatorname{Im}G_R(\omega,\mathbf k).
$$

This is the real-time version of the Kramers–Kronig relation: causality ties the real and imaginary parts of a response function.

## KMS and fluctuation-dissipation

Thermal equilibrium implies the Kubo–Martin–Schwinger relation. For a neutral bosonic operator,

$$
G^>(t,\mathbf x)=G^<(t+i\beta,\mathbf x),
$$

or in frequency space,

$$
G^>(\omega,\mathbf k)=e^{\beta\omega}G^<(\omega,\mathbf k).
$$

Since

$$
\rho(\omega,\mathbf k)=G^>(\omega,\mathbf k)-G^<(\omega,\mathbf k),
$$

we obtain

$$
G^<(\omega,\mathbf k)=n_B(\omega)\rho(\omega,\mathbf k),
$$

and

$$
G^>(\omega,\mathbf k)=\bigl(1+n_B(\omega)\bigr)\rho(\omega,\mathbf k),
$$

where

$$
n_B(\omega)=\frac{1}{e^{\beta\omega}-1}.
$$

The symmetrized correlator is

$$
G_{\rm sym}(\omega,\mathbf k)
=
\frac12\bigl(G^>(\omega,\mathbf k)+G^<(\omega,\mathbf k)\bigr)
=
\frac12\coth\!\left(\frac{\beta\omega}{2}\right)\rho(\omega,\mathbf k).
$$

This is the fluctuation-dissipation theorem. Dissipation is governed by $\operatorname{Im}G_R$; equilibrium fluctuations are fixed by the same spectral density multiplied by a thermal occupation factor.

For fermionic operators, replace the Bose factor by the Fermi factor and use the anti-periodic KMS relation. Retarded fermion correlators use anticommutators rather than commutators.

## Static, Euclidean, and retarded limits

Three related limits are easy to confuse.

The static Euclidean correlator is evaluated at zero Matsubara frequency:

$$
G_E(i\omega_n=0,\mathbf k).
$$

The retarded zero-frequency correlator is

$$
G_R(\omega=0,\mathbf k).
$$

Hydrodynamic limits may depend on the order in which $\omega$ and $\mathbf k$ go to zero:

$$
\lim_{\omega\to0}\lim_{\mathbf k\to0}G_R(\omega,\mathbf k)
\neq
\lim_{\mathbf k\to0}\lim_{\omega\to0}G_R(\omega,\mathbf k).
$$

This distinction matters for conductivities, susceptibilities, screening masses, sound modes, and diffusion poles.

For a conserved charge density $n=J^t$, the susceptibility is the thermodynamic derivative

$$
\chi=\frac{\partial n}{\partial \mu}.
$$

It is extracted from a static density-density correlator, with signs fixed by the chosen source convention for $A_t$ and $\mu$.

## Kubo formulas

Transport coefficients are low-frequency limits of retarded correlators.

For an isotropic electrical conductivity,

$$
\sigma(\omega)
=
-\frac{i}{\omega}G_R^{J_xJ_x}(\omega,\mathbf 0),
$$

up to diamagnetic or contact terms. The dissipative part is

$$
\operatorname{Re}\sigma(\omega)
=
-\frac{1}{\omega}\operatorname{Im}G_R^{J_xJ_x}(\omega,\mathbf 0).
$$

For shear viscosity,

$$
\eta
=
-\lim_{\omega\to0}\frac{1}{\omega}
\operatorname{Im}G_R^{T_{xy}T_{xy}}(\omega,\mathbf 0).
$$

For diffusion of a conserved density,

$$
\omega_*=-iD\mathbf k^2+O(\mathbf k^4)
$$

is the hydrodynamic pole. A common density-density structure is

$$
G_R^{nn}(\omega,\mathbf k)
=
\chi \frac{D\mathbf k^2}{-i\omega+D\mathbf k^2}
+
\text{contact terms}.
$$

Here $D$ is the diffusion constant and $\chi$ is the susceptibility.

## Holographic retarded correlators

Let a bulk fluctuation $\Phi$ be dual to $\mathcal O$. Near the AdS boundary,

$$
\Phi(z;\omega,\mathbf k)
\sim
z^{d-\Delta}\Phi_{(0)}(\omega,\mathbf k)
+
z^\Delta \Phi_{(\Delta)}(\omega,\mathbf k)
+
\cdots.
$$

The source is $\Phi_{(0)}$, and the renormalized response is obtained from the renormalized canonical momentum:

$$
\langle \mathcal O(\omega,\mathbf k)\rangle
=
\Pi_{\rm ren}(\omega,\mathbf k).
$$

Then

$$
G_R(\omega,\mathbf k)
=
\frac{\delta \Pi_{\rm ren}(\omega,\mathbf k)}
{\delta \Phi_{(0)}(\omega,\mathbf k)}.
$$

For a single decoupled scalar this often reduces schematically to

$$
G_R(\omega,\mathbf k)
\sim
\frac{\Phi_{(\Delta)}(\omega,\mathbf k)}
{\Phi_{(0)}(\omega,\mathbf k)}
+
\text{local counterterm contributions}.
$$

The interior condition selects the Green function:

| Bulk condition | Boundary correlator |
|---|---|
| regular Euclidean solution | Euclidean correlator $G_E$ |
| infalling at the future horizon | retarded correlator $G_R$ |
| outgoing at the future horizon | advanced correlator $G_A$ |
| full Schwinger–Keldysh contour with gluing conditions | contour-ordered real-time correlators |

Near a black-brane horizon, using a tortoise coordinate $r_*$,

$$
\Phi \sim e^{-i\omega(t+r_*)}
\quad \text{infalling},
\qquad
\Phi \sim e^{-i\omega(t-r_*)}
\quad \text{outgoing}.
$$

The retarded prescription chooses the infalling solution.

## Poles and quasinormal modes

For a decoupled fluctuation satisfying infalling horizon boundary conditions, write the near-boundary behavior as

$$
\Phi(z;\omega,\mathbf k)
=
J(\omega,\mathbf k)\Phi_{\rm source}(z;\omega,\mathbf k)
+
A(\omega,\mathbf k)\Phi_{\rm vev}(z;\omega,\mathbf k).
$$

The retarded correlator behaves schematically as

$$
G_R(\omega,\mathbf k)\sim \frac{A(\omega,\mathbf k)}{J(\omega,\mathbf k)}.
$$

A pole occurs when the source coefficient vanishes:

$$
J(\omega_*,\mathbf k)=0.
$$

Thus the bulk solution is nonzero, infalling at the horizon, and source-free at the boundary. This is precisely the quasinormal-mode boundary-value problem.

For coupled fields, the source-response relation is matrix-valued. Poles occur when the source matrix is non-invertible,

$$
\det J_{ab}(\omega_*,\mathbf k)=0.
$$

Hydrodynamic poles approach the origin as $\mathbf k\to0$. Nonhydrodynamic quasinormal poles remain at frequencies of order $T$ or another microscopic scale.

## Contact terms and scheme dependence

Holographic counterterms can shift correlators by local terms. In momentum space,

$$
G_R(\omega,\mathbf k)
\to
G_R(\omega,\mathbf k)+a+b\omega^2+c\mathbf k^2+\cdots.
$$

Such terms can affect:

- the real part of a correlator;
- static susceptibilities;
- Ward identities;
- comparison between renormalization schemes.

They do not move nonlocal poles, branch cuts, or dissipative spectral weight at nonzero frequency. This is why pole locations and $\operatorname{Im}G_R$ are often more robust than the raw real part of $G_R$.

## Conserved-current correlators

For a conserved current,

$$
\partial_\mu J^\mu=0.
$$

In momentum space, current conservation implies Ward identities such as

$$
k_\mu G_R^{\mu\nu}(\omega,\mathbf k)=0,
$$

up to contact terms and possible anomalies.

For a bulk Maxwell field,

$$
A_i^{(0)}
\quad\longleftrightarrow\quad
\text{source for }J^i,
$$

and the renormalized radial electric flux gives

$$
\langle J^i\rangle=\Pi_{\rm ren}^i.
$$

Therefore

$$
G_R^{ij}(\omega,\mathbf k)
=
\frac{\delta \Pi_{\rm ren}^i}{\delta A_j^{(0)}}.
$$

Gauge redundancy means that one should either fix gauge carefully or use gauge-invariant combinations, such as longitudinal electric fields.

## Stress-tensor correlators

The retarded stress-tensor correlator is

$$
G_R^{\mu\nu,\rho\sigma}(x)
=
-i\theta(t)\langle[T^{\mu\nu}(x),T^{\rho\sigma}(0)]\rangle.
$$

The metric source is the boundary metric $g_{(0)\mu\nu}$. With

$$
\delta W
=
\frac12\int d^d x\sqrt{-g_{(0)}}
\langle T^{\mu\nu}\rangle \delta g_{(0)\mu\nu},
$$

linear response gives schematically

$$
\delta\langle T^{\mu\nu}\rangle
=-\frac12
G_R^{\mu\nu,\rho\sigma}\delta g_{(0)\rho\sigma}
+
\text{contact terms},
$$

where the sign depends on whether one varies $g_{\mu\nu}$ or $g^{\mu\nu}$.

In holography, $G_R^{TT}$ comes from linearized metric perturbations with infalling horizon boundary conditions. The shear perturbation $h_{xy}$ is often the simplest channel because it decouples and behaves like a minimally coupled scalar in two-derivative Einstein gravity.

## Fermionic correlators

For a fermionic operator $\Psi$, the retarded function uses an anticommutator:

$$
G_R^\Psi(t,\mathbf x)
=
-i\theta(t)\langle\{\Psi(t,\mathbf x),\bar\Psi(0,\mathbf 0)\}\rangle.
$$

A common spectral diagnostic is

$$
A(\omega,\mathbf k)
=
-2\operatorname{Im}\operatorname{Tr}G_R^\Psi(\omega,\mathbf k).
$$

In holography, fermionic retarded functions come from solving the bulk Dirac equation with infalling boundary conditions and reading off the ratio of normalizable to non-normalizable spinor components. Details depend on gamma-matrix and boundary-spinor conventions, so raw signs in fermion Green functions are especially convention-sensitive.

## Quick dictionary

| Field-theory object | Holographic computation |
|---|---|
| $G_E$ | Euclidean regular bulk solution with fixed boundary source |
| $G_R$ | Lorentzian infalling solution at the future horizon |
| $G_A$ | outgoing solution, or complex conjugate in equilibrium |
| spectral density $\rho$ | discontinuity / absorption / imaginary part of $G_R$ |
| transport coefficient | low-frequency limit of $G_R$ |
| hydrodynamic pole | low-lying quasinormal mode |
| Euclidean Matsubara data | correlator at imaginary frequencies |
| contact term | local counterterm ambiguity |
| Ward identity | radial constraint or gauge constraint |
| coupled response | matrix of sources and radial canonical momenta |

## Common confusions

### “The Euclidean correlator is automatically the retarded correlator.”

No. Equilibrium Euclidean data and real-time response are related by analytic continuation, but the retarded function is a specific boundary value with a specific $i\epsilon$ prescription. In holography, the retarded function is computed directly by imposing infalling horizon boundary conditions.

### “The spectral function is always $2\operatorname{Im}G_R$.”

With the convention used here,

$$
G_R=-i\theta(t)\langle[\mathcal O(t),\mathcal O(0)]\rangle,
$$

so

$$
\rho=-2\operatorname{Im}G_R.
$$

Other sign conventions are common.

### “Every pole is a quasinormal mode.”

The clean holographic statement is that poles of the retarded Green function correspond to infalling, source-free bulk solutions. Other real-time correlators have different $i\epsilon$ prescriptions and different analytic structures.

### “Contact terms are unphysical.”

Some are scheme artifacts, but contact terms matter for Ward identities, anomalies, susceptibilities, and precise one-point-function normalization. They usually do not affect dissipative spectral weight or pole locations.

### “The zero-frequency, zero-momentum limit is unique.”

Hydrodynamic correlators often have noncommuting limits. Static susceptibility, DC conductivity, screening, and hydrodynamic relaxation can probe different limits of the same function.

## Exercises

### Exercise 1: Causality and analyticity

Assume $G_R(t)=0$ for $t<0$ and that $G_R(t)$ is sufficiently bounded for $t>0$. Show why $G_R(\omega)$ is analytic for $\operatorname{Im}\omega>0$.

<details>
<summary><strong>Solution</strong></summary>

The Fourier transform is

$$
G_R(\omega)=\int_{-\infty}^{\infty}dt\,e^{i\omega t}G_R(t)
=\int_0^\infty dt\,e^{i\omega t}G_R(t).
$$

Write $\omega=\omega_R+i\omega_I$. Then

$$
e^{i\omega t}=e^{i\omega_R t}e^{-\omega_I t}.
$$

For $\omega_I>0$, the exponential damps the integral at large positive time. Under the usual assumptions that justify differentiating under the integral sign, the result is analytic in the upper half-plane.

</details>

### Exercise 2: KMS to fluctuation-dissipation

Use

$$
G^>(\omega)=e^{\beta\omega}G^<(\omega)
$$

and

$$
\rho(\omega)=G^>(\omega)-G^<(\omega)
$$

to derive $G^<$ and $G^>$ in terms of $\rho$ and $n_B$.

<details>
<summary><strong>Solution</strong></summary>

From KMS,

$$
\rho=(e^{\beta\omega}-1)G^<.
$$

Therefore

$$
G^<(\omega)=\frac{1}{e^{\beta\omega}-1}\rho(\omega)
=n_B(\omega)\rho(\omega).
$$

Then

$$
G^>(\omega)=e^{\beta\omega}G^<(\omega)
=\bigl(1+n_B(\omega)\bigr)\rho(\omega).
$$

</details>

### Exercise 3: Diffusion pole

Consider

$$
G_R^{nn}(\omega,\mathbf k)
=\chi\frac{D\mathbf k^2}{-i\omega+D\mathbf k^2}.
$$

Where is the pole, and is it stable?

<details>
<summary><strong>Solution</strong></summary>

The pole is determined by

$$
-i\omega+D\mathbf k^2=0,
$$

so

$$
\omega_*=-iD\mathbf k^2.
$$

For $D>0$, $\operatorname{Im}\omega_*<0$. The time dependence is

$$
e^{-i\omega_*t}=e^{-D\mathbf k^2t},
$$

which decays. This is the correct half-plane for a stable retarded correlator.

</details>

### Exercise 4: Holographic pole condition

Suppose an infalling bulk solution behaves near the boundary as

$$
\Phi(z)=J(\omega)z^{d-\Delta}+A(\omega)z^\Delta+\cdots,
$$

and

$$
G_R(\omega)\sim \frac{A(\omega)}{J(\omega)}.
$$

Why does $J(\omega_*)=0$ define a quasinormal-mode pole?

<details>
<summary><strong>Solution</strong></summary>

The coefficient $J$ is the source. If $J(\omega_*)=0$ while the solution remains nonzero, the bulk field is source-free at the boundary and infalling at the horizon. That is precisely the quasinormal-mode boundary-value problem.

At the same frequency,

$$
G_R(\omega)\sim \frac{A(\omega)}{J(\omega)}
$$

has a pole unless the numerator vanishes in a canceling way. Therefore quasinormal frequencies are poles of the retarded boundary Green function.

</details>

## Further reading

- L. P. Kadanoff and P. C. Martin, [Hydrodynamic Equations and Correlation Functions](https://doi.org/10.1016/0003-4916(63)90046-7).
- D. T. Son and A. O. Starinets, [Minkowski-Space Correlators in AdS/CFT Correspondence: Recipe and Applications](https://arxiv.org/abs/hep-th/0205051).
- K. Skenderis and B. C. van Rees, [Real-Time Gauge/Gravity Duality](https://arxiv.org/abs/0805.0150).
- K. Skenderis and B. C. van Rees, [Real-Time Gauge/Gravity Duality: Prescription, Renormalization and Examples](https://arxiv.org/abs/0812.2909).
- M. Laine and A. Vuorinen, [Basics of Thermal Field Theory](https://arxiv.org/abs/1701.01554).
- S. A. Hartnoll, [Lectures on Holographic Methods for Condensed Matter Physics](https://arxiv.org/abs/0903.3246).
