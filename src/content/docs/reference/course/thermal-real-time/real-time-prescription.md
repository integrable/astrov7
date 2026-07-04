---
title: "Real-Time Prescription"
description: "How Lorentzian AdS/CFT computes retarded, advanced, time-ordered, Wightman, and Schwinger-Keldysh correlators from horizon boundary conditions and renormalized canonical momenta."
sidebar:
  order: 40
---

## Why this matters

Euclidean gravity computes equilibrium thermodynamics and Euclidean correlators. But many physical questions are real-time questions:

$$
\text{How does a plasma respond to a perturbation?}
$$

$$
\text{What are its transport coefficients?}
$$

$$
\text{How do perturbations fall into a horizon?}
$$

$$
\text{Where are the poles of }G_R(\omega,\vec k)?
$$

These questions require Lorentzian holography. The central object is the retarded Green's function

$$
G_R(t,\vec x)
=
-i\theta(t)\langle [\mathcal O(t,\vec x),\mathcal O(0,\vec 0)]\rangle.
$$

In thermal holography, the practical rule is:

$$
\boxed{
\text{retarded correlator}
\quad\longleftrightarrow\quad
\text{solve the Lorentzian bulk equation with infalling horizon boundary conditions.}
}
$$

This page explains why that prescription is needed, what it computes, and how it fits into the more general real-time gauge/gravity dictionary.

## Why Euclidean continuation is not enough

A Euclidean thermal two-point function is defined at Matsubara frequencies:

$$
\omega_n=
\begin{cases}
2\pi n T, & \text{bosons},\\
(2n+1)\pi T, & \text{fermions}.
\end{cases}
$$

For bosonic operators, one often writes the analytic-continuation relation

$$
G_R(\omega,\vec k)
=
G_E(i\omega_n\to \omega+i0^+,\vec k),
$$

when the continuation is well defined. This formula is useful, but it hides the main bulk issue. In Lorentzian signature, a second-order bulk wave equation needs both:

1. the boundary source at the AdS boundary;
2. an interior condition at the horizon or in the deep interior.

The interior condition chooses the real-time Green's function. Ingoing gives retarded. Outgoing gives advanced. More general choices produce other correlators or states.

## Boundary real-time correlators

For a Hermitian operator $\mathcal O$, the basic thermal real-time correlators are

$$
G_R(t)
=
-i\theta(t)\langle[\mathcal O(t),\mathcal O(0)]\rangle,
$$

$$
G_A(t)
=
i\theta(-t)\langle[\mathcal O(t),\mathcal O(0)]\rangle,
$$

$$
G^>(t)
=
\langle\mathcal O(t)\mathcal O(0)\rangle,
\qquad
G^<(t)
=
\langle\mathcal O(0)\mathcal O(t)\rangle.
$$

The spectral density is

$$
\rho(\omega,\vec k)
=
-2\,\operatorname{Im}G_R(\omega,\vec k).
$$

For transport, retarded functions are especially important because linear response says

$$
\delta\langle \mathcal O\rangle(\omega,\vec k)
=
G_R(\omega,\vec k)\,J(\omega,\vec k)
$$

for a source $J$ switched on causally.

## Lorentzian saddle-point dictionary

In Lorentzian signature, the generating functional has the schematic saddle form

$$
Z_{\rm CFT}[J]
\approx
\exp\!\left(iS_{{\rm ren},L}[\phi_{\rm cl};J]\right).
$$

For a scalar field with boundary source $J=\phi_{(0)}$, solve the Lorentzian bulk equation

$$
(\Box-m^2)\phi=0
$$

subject to

$$
\phi(z,x)\sim z^{d-\Delta}\phi_{(0)}(x)+\cdots
\quad\text{as }z\to 0,
$$

and an interior condition appropriate to the state and correlator.

The renormalized one-point function is extracted from the renormalized canonical momentum:

$$
\langle\mathcal O\rangle_J
=
\frac{\delta S_{{\rm ren},L}}{\delta \phi_{(0)}}.
$$

The retarded two-point function is the linear response kernel:

$$
G_R(x,y)
=
\frac{\delta \langle\mathcal O(x)\rangle}{\delta \phi_{(0)}(y)}\bigg|_{\phi_{(0)}=0},
$$

where the bulk solution obeys retarded interior boundary conditions.

<figure class="doc-figure" style="--figure-width: 55rem;">

![Real-time holographic prescription](/figures/course/real-time-retarded-prescription.svg)

<figcaption>

For a thermal retarded correlator, prescribe a boundary source, solve the Lorentzian bulk wave equation with infalling behavior at the horizon, renormalize the boundary canonical momentum, and differentiate the response with respect to the source. Changing the horizon condition changes the real-time correlator.

</figcaption>
</figure>

## The infalling condition near a horizon

Use the planar black-brane metric

$$
ds^2
=
\frac{L^2}{z^2}
\left[-f(z)dt^2+d\vec x^{\,2}+\frac{dz^2}{f(z)}\right],
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d.
$$

The horizon is at $z=z_h$, and

$$
T=\frac{d}{4\pi z_h}.
$$

Near the horizon,

$$
f(z)\approx 4\pi T(z_h-z).
$$

For a Fourier mode

$$
\phi(t,z,\vec x)=e^{-i\omega t+i\vec k\cdot\vec x}\phi_\omega(z),
$$

the radial equation near the horizon has two independent behaviors:

$$
\phi_\omega(z)
\sim
\left(1-\frac{z}{z_h}\right)^{-i\omega/(4\pi T)},
\qquad
\phi_\omega(z)
\sim
\left(1-\frac{z}{z_h}\right)^{+i\omega/(4\pi T)}.
$$

The first is infalling; the second is outgoing.

To see this, introduce the tortoise coordinate

$$
z_* = \int_0^z \frac{dz'}{f(z')}
\sim
-\frac{1}{4\pi T}\log\!\left(1-\frac{z}{z_h}\right),
$$

and the ingoing Eddington–Finkelstein coordinate

$$
v=t-z_*.
$$

A mode regular in $v$ behaves as

$$
e^{-i\omega v}
=
e^{-i\omega t}
\left(1-\frac{z}{z_h}\right)^{-i\omega/(4\pi T)}.
$$

Thus infalling behavior is regular at the future horizon. This is the gravitational encoding of causal dissipation in the boundary theory.

## The Son–Starinets recipe

For a scalar perturbation, normalize the radial solution by

$$
\phi(z;k)=\phi_{(0)}(k)\,F(z;k),
\qquad
F(z;k)\to z^{d-\Delta}
\quad\text{near the boundary},
$$

or, after stripping the leading source power, by $F(0;k)=1$. Impose infalling behavior at the future horizon.

The renormalized on-shell action has the quadratic form

$$
S_{{\rm ren},L}^{(2)}
=
\frac{1}{2}\int \frac{d^dk}{(2\pi)^d}\,
\phi_{(0)}(-k)\,\mathcal F_{\rm ren}(k)\,\phi_{(0)}(k).
$$

Then, up to the sign convention used for the Lorentzian action and Fourier transform,

$$
G_R(k)=\mathcal F_{\rm ren}(k).
$$

Equivalently, in canonical-momentum language,

$$
G_R(k)
=
\lim_{z\to 0}
\frac{\Pi_{\rm ren}(z;k)}{\phi(z;k)}
\bigg|_{\rm infalling},
$$

where

$$
\Pi(z;k)
=
\frac{\delta S_L}{\delta(\partial_z\phi(-k,z))}
$$

is the radial canonical momentum. Counterterms must be included before the limit is taken.

This is the practical prescription used throughout holographic transport.

## A useful scalar equation

For a scalar in the planar black brane, the radial equation can be written schematically as

$$
\frac{1}{\sqrt{-g}}\partial_z\!\left(\sqrt{-g}g^{zz}\partial_z\phi\right)
+g^{tt}\omega^2\phi
+g^{ij}k_i k_j\phi
-m^2\phi=0.
$$

Near the boundary, this equation determines the source and response expansion:

$$
\phi(z;k)
=
z^{d-\Delta}\phi_{(0)}(k)+\cdots+z^\Delta A(k)+\cdots.
$$

Near the horizon, it determines the infalling/outgoing exponents. A retarded correlator is obtained by connecting these two asymptotic regions through the unique infalling solution.

This “connect boundary source to horizon infalling condition” logic is the Lorentzian analogue of regularity in Euclidean AdS. The difference is that Lorentzian regularity alone is not enough; one must specify which horizon is being used and which causal Green's function is desired.

## Poles and quasinormal modes

The retarded Green's function has poles when there is a nontrivial solution satisfying:

$$
\text{normalizable at the boundary},
\qquad
\text{infalling at the horizon}.
$$

These are precisely the quasinormal modes of the black brane. Therefore

$$
\boxed{
\text{poles of }G_R(\omega,\vec k)
\quad\longleftrightarrow\quad
\text{bulk quasinormal frequencies}.
}
$$

This is why black-brane perturbations encode the relaxation spectrum of the dual thermal state. Hydrodynamic poles, diffusion, sound, and shear modes all appear this way.

## Relation to Euclidean regularity

For thermal equilibrium correlators, the retarded prescription is closely related to Euclidean regularity. A Euclidean solution regular at the smooth cigar tip can be analytically continued from Matsubara frequency to

$$
i\omega_n\to \omega+i0^+.
$$

After this continuation, regularity at the Euclidean cap selects the infalling Lorentzian solution. This is a useful shortcut for two-point functions in equilibrium.

But this shortcut is not the whole real-time dictionary. For time-dependent sources, non-equilibrium states, time-ordered correlators, Wightman correlators, or higher-point functions, one needs a genuine Lorentzian contour prescription.

## Schwinger–Keldysh viewpoint

Real-time QFT is naturally formulated on a contour in complex time. For thermal correlators, a typical contour has:

- a forward Lorentzian segment;
- a backward Lorentzian segment;
- an imaginary Euclidean segment of length $\beta$.

The generating functional is a Schwinger–Keldysh path integral, and sources may be placed independently on different contour segments.

The holographic version fills each segment with an appropriate bulk geometry:

$$
\text{Lorentzian boundary segment}
\quad\longrightarrow\quad
\text{Lorentzian bulk segment},
$$

$$
\text{Euclidean boundary segment}
\quad\longrightarrow\quad
\text{Riemannian bulk segment}.
$$

The segments are glued with matching conditions at the corners of the contour. This prescription keeps track of the initial state or density matrix and gives a systematic way to compute retarded, advanced, Feynman, Wightman, and higher real-time correlators.

For the simplest retarded thermal two-point function, the Schwinger–Keldysh machinery collapses to the familiar infalling-horizon rule.

## Advanced, Feynman, and Wightman correlators

Changing the prescription changes the Green's function:

| Boundary correlator | Bulk condition |
|---|---|
| retarded $G_R$ | infalling at future horizon |
| advanced $G_A$ | outgoing at future horizon |
| Euclidean $G_E$ | regular at Euclidean cap |
| Feynman $G_F$ | contour-dependent prescription |
| Wightman $G^>,G^<$ | Schwinger–Keldysh / thermal contour data |

For a thermal state, these correlators are related by KMS identities, but they are not all the same analytic function on the same sheet. The bulk knows this through the choice of contour and horizon data.

## Real-time holographic renormalization

The near-boundary divergences are local and do not disappear in Lorentzian signature. The same counterterm logic applies:

$$
S_{{\rm ren},L}
=
\lim_{\epsilon\to 0}
\left(
S_L^{z\ge \epsilon}+S_{{\rm ct},L}^{z=\epsilon}
\right).
$$

The finite response is extracted from the renormalized canonical momentum:

$$
\Pi_{\rm ren}
=
\Pi+\Pi_{\rm ct}.
$$

For a scalar in standard quantization,

$$
\langle\mathcal O(k)\rangle
=
\Pi_{\rm ren}(k),
$$

up to the normalization convention chosen for the scalar action. Differentiating with respect to the boundary source gives the retarded correlator if the bulk solution obeyed the retarded interior condition.

The imaginary part of $G_R$ is especially important. It measures dissipation, absorption by the horizon, and spectral weight in the boundary theory.

## Dictionary checkpoint

| Boundary real-time concept | Bulk Lorentzian object |
|---|---|
| source $J(\omega,\vec k)$ | non-normalizable boundary value of a bulk field |
| response $\delta\langle\mathcal O\rangle$ | renormalized canonical momentum |
| retarded correlator $G_R$ | infalling horizon boundary condition |
| advanced correlator $G_A$ | outgoing horizon boundary condition |
| spectral density $\rho=-2\operatorname{Im}G_R$ | horizon absorption / radial flux |
| relaxation pole | quasinormal mode |
| thermal density matrix | Euclidean segment of real-time contour |
| Schwinger–Keldysh sources | sources on different boundary contour segments |

The horizon is not a nuisance. It is the mechanism by which the classical bulk encodes causal response and dissipation.

## Common confusions

### “Lorentzian AdS/CFT is just the Euclidean answer with $\tau=it$.”

Sometimes analytic continuation is enough, especially for equilibrium two-point functions. But Lorentzian problems require interior boundary conditions. The continuation must know which Green's function is being selected.

### “Regularity at the horizon uniquely fixes the answer.”

In Euclidean signature, smoothness at the cap is the natural condition. In Lorentzian signature, both infalling and outgoing modes can be locally finite in appropriate coordinates. Retarded response selects infalling behavior at the future horizon.

### “The infalling condition is an arbitrary absorption assumption.”

It is the bulk representation of causal boundary response. A perturbation sourced at the boundary can fall through the future horizon; a retarded Green's function should not contain radiation emerging from a past horizon as an independent source.

### “Quasinormal modes are normal modes.”

Normal modes in global AdS without a horizon have real frequencies. Quasinormal modes in black-brane backgrounds usually have complex frequencies, reflecting decay in the boundary thermal state.

### “Counterterms are a Euclidean-only issue.”

No. UV divergences are near-boundary divergences. They are present in Euclidean and Lorentzian signature and are removed by the same local counterterm structure, with appropriate factors of $i$ in the path integral.

## Exercises

### Exercise 1: Near-horizon exponents

Using

$$
f(z)\approx 4\pi T(z_h-z),
$$

show that a massless scalar mode near the horizon behaves as

$$
\phi_\omega(z)
\sim
\left(1-\frac{z}{z_h}\right)^{\pm i\omega/(4\pi T)}.
$$

<details>
<summary><strong>Solution</strong></summary>

Near the horizon, the dominant part of the radial wave equation comes from the $(t,z)$ part of the metric. Introduce the tortoise coordinate

$$
z_* = \int^z \frac{dz'}{f(z')}.
$$

Since

$$
f(z)\approx 4\pi T(z_h-z),
$$

we have

$$
z_*
\sim
-\frac{1}{4\pi T}\log\!\left(1-\frac{z}{z_h}\right).
$$

Near the horizon, the wave equation reduces to a flat two-dimensional wave equation in $t$ and $z_*$, so the solutions are

$$
e^{-i\omega t}e^{\pm i\omega z_*}.
$$

Using the logarithmic behavior of $z_*$ gives

$$
e^{-i\omega t}
\left(1-\frac{z}{z_h}\right)^{\mp i\omega/(4\pi T)}.
$$

The sign convention depends on how one defines $z_*$ and the ingoing coordinate. With the convention used in this page, infalling behavior is

$$
\left(1-\frac{z}{z_h}\right)^{-i\omega/(4\pi T)}.
$$

</details>

### Exercise 2: Why outgoing gives the advanced correlator

Explain why replacing infalling by outgoing boundary conditions should compute an advanced rather than retarded correlator.

<details>
<summary><strong>Solution</strong></summary>

The retarded correlator describes causal response: the response at time $t$ depends only on sources at earlier times. In the bulk, this is implemented by allowing disturbances to enter the future horizon. No independent signal is allowed to emerge from the future horizon.

The outgoing condition reverses this causal choice. It corresponds to radiation emerging from the horizon rather than being absorbed by it. This is the time-reversed condition and therefore gives the advanced response, whose support is appropriate to response before the source rather than after it.

In frequency space, retarded and advanced correlators are related by opposite $i0^+$ prescriptions and have poles in opposite half-planes.

</details>

### Exercise 3: Quasinormal poles

Why does a source-free, normalizable, infalling bulk solution imply a pole in $G_R$?

<details>
<summary><strong>Solution</strong></summary>

For a linear bulk equation, write the near-boundary solution schematically as

$$
\phi(z;k)
\sim z^{d-\Delta}\phi_{(0)}(k)+z^\Delta A(k).
$$

The retarded Green's function is the response divided by the source,

$$
G_R(k)\sim \frac{A(k)}{\phi_{(0)}(k)},
$$

after holographic renormalization.

A quasinormal mode is a nonzero solution that is infalling at the horizon and normalizable at the boundary. Normalizable means

$$
\phi_{(0)}(k)=0
$$

while $A(k)$ is not zero. This means the ratio $A(k)/\phi_{(0)}(k)$ is singular. Hence the corresponding frequency is a pole of $G_R$.

</details>

## Further reading

- D. T. Son and A. O. Starinets, [Minkowski-space Correlators in AdS/CFT Correspondence: Recipe and Applications](https://arxiv.org/abs/hep-th/0205051).
- G. Policastro, D. T. Son, and A. O. Starinets, [From AdS/CFT Correspondence to Hydrodynamics](https://arxiv.org/abs/hep-th/0205052).
- K. Skenderis and B. C. van Rees, [Real-time Gauge/Gravity Duality](https://arxiv.org/abs/0805.0150).
- K. Skenderis and B. C. van Rees, [Real-time Gauge/Gravity Duality: Prescription, Renormalization and Examples](https://arxiv.org/abs/0812.2909).
- P. K. Kovtun and A. O. Starinets, [Quasinormal Modes and Holography](https://arxiv.org/abs/hep-th/0506184).
