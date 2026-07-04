---
title: "Shear Viscosity"
description: "The holographic derivation of the universal Einstein-gravity result eta over s equals one over four pi."
sidebar:
  order: 80
---

## Why this matters

Shear viscosity is the cleanest transport coefficient in AdS/CFT. It measures how efficiently transverse momentum gradients are damped. In a strongly coupled plasma with an Einstein-gravity dual, it is computed by a transverse graviton falling into the black-brane horizon.

The famous result is

$$
\boxed{
\frac{\eta}{s}=\frac{1}{4\pi}
}
$$

in units $\hbar=k_B=1$.

This page derives the result in the form most useful for AdS/CFT calculations. The derivation also explains why the number is universal in two-derivative Einstein gravity and why it is not a theorem about all quantum field theories.

The logic is:

$$
\text{metric source }h^{(0)}_{xy}
\quad\longrightarrow\quad
G_R^{T^{xy}T^{xy}}
\quad\longrightarrow\quad
\eta
\quad\longrightarrow\quad
\frac{\eta}{s}=\frac{1}{4\pi}.
$$

## Boundary definition: the Kubo formula

In a relativistic QFT, the stress tensor responds to a small metric perturbation. Turn on an off-diagonal boundary metric source

$$
g_{(0)xy}(t)=h^{(0)}_{xy}(t).
$$

The corresponding operator is $T^{xy}$. Linear response gives

$$
\delta\langle T^{xy}(\omega)\rangle
=
-\frac12 G_R^{xy,xy}(\omega,\mathbf{0})h^{(0)}_{xy}(\omega),
$$

up to sign conventions for how the source is inserted. The retarded correlator is

$$
G_R^{xy,xy}(t,\mathbf{x})
=
-i\theta(t)\langle[T^{xy}(t,\mathbf{x}),T^{xy}(0,\mathbf{0})]\rangle .
$$

For an isotropic fluid, the shear viscosity is determined by the low-frequency spectral weight:

$$
\boxed{
\eta
=
-\lim_{\omega\to0}
\frac{1}{\omega}
\operatorname{Im}G_R^{xy,xy}(\omega,\mathbf{0}) .
}
$$

This is the shear Kubo formula. The real part of $G_R$ contains contact and scheme-dependent terms. The transport coefficient is obtained from the dissipative imaginary part.

## Gravity setup

Use the planar AdS$_{d+1}$ black brane

$$
ds^2
=
\frac{L^2}{z^2}
\left[
-f(z)dt^2+d\mathbf{x}^2+\frac{dz^2}{f(z)}
\right],
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d,
$$

with

$$
T=\frac{d}{4\pi z_h}.
$$

Consider a transverse traceless metric perturbation at zero spatial momentum:

$$
g_{xy}\to g_{xy}+\delta g_{xy},
\qquad
\delta g^x_{\ y}(t,z)=\phi(z)e^{-i\omega t}.
$$

The boundary value $\phi_{(0)}$ sources $T^{xy}$:

$$
\phi(z\to0)=\phi_{(0)}+\cdots .
$$

For two-derivative Einstein gravity, this transverse graviton obeys the same radial equation as a minimally coupled massless scalar:

$$
\frac{1}{\sqrt{-g}}\partial_z
\left(\sqrt{-g}g^{zz}\partial_z\phi\right)
+
g^{tt}\omega^2\phi=0 .
$$

This simplification is the heart of the universality argument.

<figure class="doc-figure" style="--figure-width: 55rem;">

![Shear viscosity from the transverse graviton](/figures/course/shear-viscosity-kubo.svg)

<figcaption>

The shear viscosity computation. The boundary metric source $h^{(0)}_{xy}$ launches a transverse graviton $\phi=h^x_{\ y}$ into the black-brane geometry. Infalling horizon behavior selects the retarded correlator. In the low-frequency limit, the dissipative flux is fixed by the horizon area density, giving $\eta=s/(4\pi)$ for two-derivative Einstein gravity.

</figcaption>
</figure>

## The quadratic action and canonical momentum

Expand the Einstein-Hilbert action to quadratic order in the transverse graviton. For the shear mode, the relevant part can be written as

$$
S^{(2)}
=
-\frac{1}{32\pi G_{d+1}}
\int d^{d+1}x\sqrt{-g}\,
 g^{MN}\partial_M\phi\partial_N\phi
+
\text{boundary terms}.
$$

The radial canonical momentum is therefore

$$
\Pi(z,\omega)
=
-\frac{1}{16\pi G_{d+1}}
\sqrt{-g}\,g^{zz}\partial_z\phi(z,\omega),
$$

where the precise factor follows from varying the quadratic action and using the standard normalization of $h^x_{\ y}$. After adding counterterms, the retarded correlator is schematically

$$
G_R^{xy,xy}(\omega,\mathbf{0})
=
\lim_{z\to0}\frac{\Pi_{\rm ren}(z,\omega)}{\phi(z,
\omega)} .
$$

For the viscosity, only the term linear in $i\omega$ matters. Local counterterms are analytic and real at this order for the zero-momentum shear channel, so they do not change $\eta$.

## Horizon boundary condition

Near the horizon,

$$
f(z)\simeq 4\pi T(z_h-z),
$$

and the scalar equation has two local behaviors:

$$
\phi(z)
\sim
\left(1-\frac{z}{z_h}\right)^{-i\omega/(4\pi T)}
\quad\text{or}\quad
\left(1-\frac{z}{z_h}\right)^{+i\omega/(4\pi T)}.
$$

The retarded Green function uses the infalling branch:

$$
\phi_{\rm in}(z)
\sim
\left(1-\frac{z}{z_h}\right)^{-i\omega/(4\pi T)}.
$$

Expanding at small $\omega$,

$$
\partial_z\phi_{\rm in}
\simeq
\frac{i\omega}{4\pi T}\frac{1}{z_h-z}\phi_{\rm in}.
$$

Because $g^{zz}\propto f(z)$ vanishes linearly at the horizon, the product $g^{zz}\partial_z\phi$ has a finite limit. This is the cancellation that makes the horizon calculation simple.

## Evaluating the low-frequency response at the horizon

At low frequency and zero spatial momentum, the ratio

$$
\frac{\Pi(z,\omega)}{i\omega\phi(z,\omega)}
$$

is radially conserved at leading order in $\omega$. Therefore it may be evaluated at the horizon instead of at the boundary.

Using the infalling solution, one finds

$$
\Pi(z_h,\omega)
=
-i\omega\frac{1}{16\pi G_{d+1}}
\left(\frac{L}{z_h}\right)^{d-1}
\phi(z_h,
\omega)
+
O(\omega^2).
$$

Since the zero-frequency solution is constant in $z$,

$$
\phi(z_h,\omega)=\phi_{(0)}(\omega)+O(\omega).
$$

Thus

$$
G_R^{xy,xy}(\omega,\mathbf{0})
=
-i\omega
\frac{1}{16\pi G_{d+1}}
\left(\frac{L}{z_h}\right)^{d-1}
+
O(\omega^2)
+
\text{real contact terms}.
$$

The Kubo formula gives

$$
\boxed{
\eta
=
\frac{1}{16\pi G_{d+1}}
\left(\frac{L}{z_h}\right)^{d-1}.
}
$$

## Entropy density and the ratio

The Bekenstein–Hawking entropy density of the planar horizon is

$$
s
=
\frac{1}{4G_{d+1}}
\left(\frac{L}{z_h}\right)^{d-1}.
$$

Comparing this with the viscosity gives

$$
\eta
=
\frac{s}{4\pi}.
$$

Therefore

$$
\boxed{
\frac{\eta}{s}=\frac{1}{4\pi}.}
$$

This is independent of $z_h$, $T$, and the number of degrees of freedom. Those quantities appear in both $\eta$ and $s$ and cancel in the ratio.

For $\mathcal N=4$ SYM at large $N$ and large $\lambda$,

$$
s=\frac{\pi^2}{2}N^2T^3,
\qquad
\eta=\frac{\pi}{8}N^2T^3,
$$

so again

$$
\frac{\eta}{s}=\frac{1}{4\pi}.
$$

## Relation to shear diffusion

The previous page derived the shear diffusion pole

$$
\omega=-iD_\eta k^2+
O(k^4),
\qquad
D_\eta=\frac{\eta}{\epsilon+p}.
$$

At zero chemical potential,

$$
\epsilon+p=sT.
$$

Using $\eta/s=1/(4\pi)$ gives

$$
\boxed{
D_\eta=\frac{1}{4\pi T}.
}
$$

The same number can be obtained from the lowest shear-channel quasinormal mode. Thus the Kubo computation and the hydrodynamic-pole computation agree.

## Why the result is universal in Einstein gravity

The universality follows from three ingredients.

First, $h^x_{\ y}$ is a transverse graviton mode. In an isotropic two-derivative Einstein background, it behaves like a minimally coupled scalar at zero momentum.

Second, the low-frequency response is controlled by the future horizon. The horizon is where dissipation enters.

Third, both $\eta$ and $s$ are determined by the same horizon area density:

$$
\eta
\sim
\frac{\text{horizon area density}}{16\pi G_{d+1}},
\qquad
s
=
\frac{\text{horizon area density}}{4G_{d+1}}.
$$

The ratio is therefore fixed:

$$
\frac{\eta}{s}=\frac{1}{4\pi}.
$$

This is sometimes called the membrane-paradigm explanation of the result.

## What can change the answer

The value $1/(4\pi)$ is not an exact law of nature. It is a robust result for a class of holographic theories whose low-energy bulk dynamics is governed by two-derivative Einstein gravity.

Corrections can come from several sources.

### Stringy corrections

In AdS$_5$/CFT$_4$, finite 't Hooft coupling produces higher-derivative terms in the type IIB effective action. The leading correction behaves schematically as

$$
\frac{\eta}{s}
=
\frac{1}{4\pi}
\left[
1+O(\lambda^{-3/2})
\right].
$$

For maximally supersymmetric Yang–Mills theory, the leading correction is positive in the standard normalization.

### Quantum gravity corrections

Finite $N$ produces bulk loop corrections. These are suppressed by powers of $1/N$ in theories with a weakly coupled bulk dual.

### Higher-derivative gravity

If the bulk action contains curvature-squared or higher-curvature terms not removable by field redefinitions, the transverse graviton can acquire an effective coupling different from the Einstein value. Then

$$
\eta
\neq
\frac{\text{area density}}{16\pi G_{d+1}},
$$

and $\eta/s$ can differ from $1/(4\pi)$.

In Gauss–Bonnet gravity, for example, one obtains a shifted value of the schematic form

$$
\frac{\eta}{s}
=
\frac{1}{4\pi}(1-4\lambda_{\rm GB})
$$

with conventions in which $\lambda_{\rm GB}$ is the Gauss–Bonnet coupling. Consistency constraints such as causality and positivity restrict the allowed range of such couplings, but the original universal value is no longer automatic.

### Broken translations and anisotropy

If translations are broken, momentum is no longer conserved and the shear channel need not contain an ordinary diffusion pole. If rotational symmetry is broken, different shear components can have different viscosities.

The lesson is: $\eta/s=1/(4\pi)$ is universal for a clean universality class, not for every holographic model one can write down.

## Physical interpretation

A small shear perturbation changes the boundary geometry by stretching one spatial direction into another. In the bulk, this is a transverse graviton.

The imaginary part of the retarded correlator measures absorption. At small frequency, the absorption of the transverse graviton by the horizon is governed by the horizon area. Since the same area computes entropy, viscosity and entropy are locked together.

This is why the result is so elegant:

$$
\text{dissipation}
\quad\leftrightarrow\quad
\text{horizon absorption},
$$

and

$$
\text{entropy}
\quad\leftrightarrow\quad
\text{horizon area}.
$$

In Einstein gravity, both are controlled by the same geometric object.

## Dictionary checkpoint

| Boundary quantity | Bulk computation |
|---|---|
| metric source $h^{(0)}_{xy}$ | boundary value of transverse graviton $h^x_{\ y}$ |
| $G_R^{xy,xy}$ | response/source ratio for infalling graviton |
| shear viscosity $\eta$ | low-frequency absorptive part of graviton correlator |
| entropy density $s$ | horizon area density divided by $4G_{d+1}$ |
| $\eta/s=1/(4\pi)$ | universality of two-derivative Einstein graviton coupling |
| corrections to $\eta/s$ | higher-derivative, stringy, quantum, anisotropic, or translation-breaking effects |

## Common confusions

### “Small viscosity means no interactions.”

No. In weakly coupled kinetic theory, viscosity is often large because quasiparticles travel far before exchanging momentum. Strongly coupled holographic plasmas have no long-lived quasiparticles and can have very small $\eta/s$.

### “The Kubo formula uses Euclidean correlators.”

The viscosity is defined by a retarded correlator. Euclidean correlators can sometimes be analytically continued, but the holographic calculation must impose the Lorentzian infalling condition to obtain the retarded answer.

### “The ratio $1/(4\pi)$ is a proven lower bound.”

It was historically conjectured as a bound for a broad class of systems, but higher-derivative holographic models show that the value can be modified. A safer statement is that $1/(4\pi)$ is the universal answer for isotropic two-derivative Einstein gravity duals.

### “The calculation only works for $\mathcal N=4$ SYM.”

The original explicit computation was done in the canonical D3-brane example, but the universality argument applies much more broadly to theories whose relevant bulk shear mode is governed by two-derivative Einstein gravity.

### “Counterterms change the viscosity.”

Local counterterms can change analytic real contact terms in $G_R$. The shear viscosity depends on the coefficient of $-i\omega$ in the retarded correlator at zero momentum, which is fixed by horizon absorption in the Einstein-gravity calculation.

## Exercises

### Exercise 1: Extract $\eta$ from a retarded correlator

Suppose the small-frequency retarded correlator in the shear channel is

$$
G_R^{xy,xy}(\omega,\mathbf{0})
=
P-i\omega A+O(\omega^2),
$$

where $P$ and $A$ are real constants. Use the Kubo formula to find $\eta$.

<details>
<summary><strong>Solution</strong></summary>

The Kubo formula is

$$
\eta
=
-\lim_{\omega\to0}\frac{1}{\omega}\operatorname{Im}G_R^{xy,xy}(\omega,\mathbf{0}).
$$

The imaginary part is

$$
\operatorname{Im}G_R^{xy,xy}=-\omega A+O(\omega^2).
$$

Therefore

$$
\eta
=
-\lim_{\omega\to0}\frac{-\omega A}{\omega}=A.
$$

The real contact term $P$ does not affect the viscosity.

</details>

### Exercise 2: Derive $\eta/s$ from horizon area density

Assume that a two-derivative Einstein-gravity black brane gives

$$
\eta=\frac{a_h}{16\pi G_{d+1}},
\qquad
s=\frac{a_h}{4G_{d+1}},
$$

where $a_h$ is the horizon area density. Show that $\eta/s=1/(4\pi)$.

<details>
<summary><strong>Solution</strong></summary>

Divide the two expressions:

$$
\frac{\eta}{s}
=
\frac{a_h/(16\pi G_{d+1})}{a_h/(4G_{d+1})}.
$$

The area density and Newton constant cancel:

$$
\frac{\eta}{s}
=
\frac{4}{16\pi}
=
\frac{1}{4\pi}.
$$

</details>

### Exercise 3: Check the $\mathcal N=4$ SYM numbers

Using

$$
s=\frac{\pi^2}{2}N^2T^3,
\qquad
\frac{\eta}{s}=\frac{1}{4\pi},
$$

compute $\eta$.

<details>
<summary><strong>Solution</strong></summary>

Multiply the entropy density by $1/(4\pi)$:

$$
\eta
=
\frac{s}{4\pi}
=
\frac{1}{4\pi}\frac{\pi^2}{2}N^2T^3.
$$

Therefore

$$
\eta
=
\frac{\pi}{8}N^2T^3.
$$

</details>

### Exercise 4: Shear viscosity and diffusion

Show that the shear diffusion constant of a zero-density holographic conformal plasma is

$$
D_\eta=\frac{1}{4\pi T}
$$

if $\eta/s=1/(4\pi)$.

<details>
<summary><strong>Solution</strong></summary>

The shear diffusion constant is

$$
D_\eta=\frac{\eta}{\epsilon+p}.
$$

At zero chemical potential,

$$
\epsilon+p=sT.
$$

Thus

$$
D_\eta=\frac{\eta}{sT}
=\frac{1}{T}\frac{\eta}{s}
=\frac{1}{4\pi T}.
$$

</details>

### Exercise 5: Why can higher-derivative terms change $\eta/s$?

Explain qualitatively why a higher-curvature term in the bulk action can modify the shear-viscosity ratio.

<details>
<summary><strong>Solution</strong></summary>

In two-derivative Einstein gravity, the transverse graviton has a universal kinetic coupling fixed by Newton's constant. The same Newton constant controls the Bekenstein–Hawking entropy, so $\eta$ and $s$ are tied to the same horizon area density.

Higher-curvature terms can change the effective kinetic coupling of the transverse graviton. They can also change the entropy formula from the simple area law to the Wald entropy. Since the two quantities need not be modified in the same way, the ratio $\eta/s$ can differ from $1/(4\pi)$.

</details>

## Further reading

- G. Policastro, D. T. Son, and A. O. Starinets, [Shear Viscosity of Strongly Coupled $\mathcal N=4$ Supersymmetric Yang–Mills Plasma](https://arxiv.org/abs/hep-th/0104066).
- P. Kovtun, D. T. Son, and A. O. Starinets, [Viscosity in Strongly Interacting Quantum Field Theories from Black Hole Physics](https://arxiv.org/abs/hep-th/0405231).
- D. T. Son and A. O. Starinets, [Minkowski-Space Correlators in AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0205051).
- N. Iqbal and H. Liu, [Universality of the Hydrodynamic Limit in AdS/CFT and the Membrane Paradigm](https://arxiv.org/abs/0809.3808).
- M. Brigante, H. Liu, R. C. Myers, S. Shenker, and S. Yaida, [Viscosity Bound Violation in Higher Derivative Gravity](https://arxiv.org/abs/0712.0805).
