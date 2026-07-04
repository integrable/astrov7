---
title: "Reissner–Nordström-AdS Black Branes"
sidebar:
  label: "Reissner–Nordström-AdS"
  order: 60
description: "Charged AdS black holes and black branes as holographic duals of finite-density thermal states."
---

The Reissner–Nordström-AdS black brane is the simplest backreacted holographic state at nonzero temperature and nonzero charge density. It is to finite-density holography what the neutral AdS black brane is to finite-temperature holography.

On the boundary side, the state is described by

$$
\rho_{\beta,\mu}
=
\frac{1}{Z(\beta,\mu)}
\exp[-\beta(H-\mu Q)] .
$$

On the bulk side, the geometry contains a horizon and radial electric flux:

$$
\boxed{
\text{thermal CFT at }(T,\mu)
\quad\leftrightarrow\quad
\text{charged AdS black brane}.
}
$$

This page develops the basic solution, its thermodynamics, and the near-extremal limit. The goal is not to cover every charged AdS black hole in every supergravity theory. The goal is to understand the canonical Einstein–Maxwell model that underlies much of finite-density holography.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A Reissner–Nordström-AdS black brane carries radial electric flux from the boundary to a charged horizon.](/figures/course/reissner-nordstrom-ads.svg)

<figcaption>

The planar Reissner–Nordström-AdS saddle is a charged black brane. The boundary value of $A_t$ is the chemical potential $\mu$, the radial electric flux gives the charge density $\rho$, and the horizon encodes temperature and entropy.

</figcaption>
</figure>

## Einstein–Maxwell-AdS theory

A minimal bottom-up action is

$$
S
=
\frac{1}{16\pi G_{d+1}}
\int d^{d+1}x\sqrt{-g}
\left(
R+\frac{d(d-1)}{L^2}
\right)
-
\frac{1}{4g_{d+1}^2}
\int d^{d+1}x\sqrt{-g}\,F_{MN}F^{MN}
+S_{\mathrm{bdy}} .
$$

Here $L$ is the AdS radius, $G_{d+1}$ controls gravitational interactions, and $g_{d+1}$ fixes the normalization of the boundary current two-point function.

The equations of motion are

$$
\nabla_M F^{MN}=0,
$$

and

$$
R_{MN}-\frac12 R g_{MN}
-\frac{d(d-1)}{2L^2}g_{MN}
=
8\pi G_{d+1}\,T_{MN}^{(A)},
$$

where

$$
T_{MN}^{(A)}
=
\frac{1}{g_{d+1}^2}
\left(
F_{MP}F_N{}^P
-
\frac14 g_{MN}F_{PQ}F^{PQ}
\right).
$$

In top-down examples, the Maxwell field may arise from an isometry of an internal space, an R-symmetry gauge field, a flavor brane gauge field, or a consistent truncation of supergravity. The simple Einstein–Maxwell model captures the universal-looking structure but not every stringy detail.

## Planar charged black brane

A convenient planar ansatz is

$$
ds^2
=
\frac{L^2}{z^2}
\left[
-f(z)dt^2
+d\mathbf x_{d-1}^2
+\frac{dz^2}{f(z)}
\right],
$$

with boundary at $z=0$ and horizon at $z=z_h$. A standard dimensionless parametrization is

$$
f(z)
=
1-(1+Q^2)\left(\frac{z}{z_h}\right)^d
+Q^2\left(\frac{z}{z_h}\right)^{2d-2},
$$

and

$$
A_t(z)
=
\mu\left[
1-\left(\frac{z}{z_h}\right)^{d-2}
\right].
$$

The dimensionless charge parameter $Q$ is proportional to $\mu z_h$, with a proportionality constant depending on the normalization of the Maxwell term. Since this course uses several possible normalizations across examples, we will keep that proportionality implicit unless a specific top-down model is being discussed.

The important normalization-independent facts are:

1. $A_t(0)=\mu$ is the chemical potential.
2. $A_t(z_h)=0$ is the smooth Euclidean horizon gauge.
3. The subleading term of $A_t$ determines the charge density.
4. The $Q^2$ term in $f(z)$ is the gravitational backreaction of the electric field.

For $Q=0$, this reduces to the neutral planar AdS-Schwarzschild black brane:

$$
f(z)=1-\left(\frac{z}{z_h}\right)^d .
$$

## Temperature

The Hawking temperature follows from horizon smoothness or surface gravity:

$$
T=\frac{|f'(z_h)|}{4\pi} .
$$

For the above parametrization,

$$
\boxed{
T
=
\frac{1}{4\pi z_h}
\left[d-(d-2)Q^2\right] .
}
$$

This formula already shows something new. Increasing the charge at fixed horizon radius lowers the temperature.

The extremal limit is reached when

$$
T=0,
\qquad
Q^2=\frac{d}{d-2} .
$$

At extremality, the black brane has a horizon but zero temperature.

## Entropy density

The entropy density is given by the Bekenstein–Hawking area law:

$$
s
=
\frac{1}{4G_{d+1}}
\frac{L^{d-1}}{z_h^{d-1}} .
$$

This is the same area formula as for the neutral black brane, but now $z_h$ is related to both $T$ and $\mu$.

In the simple two-derivative Einstein–Maxwell model, the extremal limit has finite entropy density because $z_h$ remains finite as $T\to0$. This feature is both useful and suspicious. It gives a controlled near-horizon geometry, but it also suggests an enormous ground-state degeneracy. In many more complete models, low-temperature instabilities or additional degrees of freedom modify the extremal Reissner–Nordström-AdS solution.

## Charge density

Near the boundary,

$$
A_t(z)
=
\mu
-
\mu\frac{z^{d-2}}{z_h^{d-2}}
+
\cdots .
$$

Comparing with the general expansion

$$
A_t(z)
=
\mu
-
\frac{g_{d+1}^2\rho}{(d-2)L^{d-3}}z^{d-2}
+
\cdots,
$$

one obtains, in this simple normalization of the Maxwell field,

$$
\rho
=
\frac{(d-2)L^{d-3}}{g_{d+1}^2}
\frac{\mu}{z_h^{d-2}} .
$$

In a fully backreacted solution, the Einstein equation relates this same charge density to the parameter $Q$. Different papers often absorb factors of $G_{d+1}$, $g_{d+1}$, and $L$ into the definition of $Q$. This is why the most robust dictionary statement is not a memorized coefficient but the variational one:

$$
\rho
=
\langle J^t\rangle
=
\frac{1}{\sqrt{-g_{(0)}}}
\frac{\delta S_{\mathrm{ren}}}{\delta A_t^{(0)}} .
$$

## Thermodynamics

The grand potential is obtained from the renormalized Euclidean on-shell action:

$$
\Omega(T,\mu)=T I_{E,\mathrm{ren}} .
$$

For a homogeneous planar state,

$$
\Omega=-pV .
$$

Conformal invariance in flat space implies

$$
\epsilon=(d-1)p .
$$

The first law and Gibbs–Duhem relation are

$$
d\epsilon=Tds+\mu d\rho,
$$

and

$$
dp=s\,dT+\rho\,d\mu .
$$

The Euler relation is

$$
\epsilon+p=Ts+\mu\rho .
$$

These equations are excellent checks on holographic computations. If a charged black-brane calculation violates them, one should suspect a missing boundary term, an inconsistent normalization, or an ensemble mismatch.

## Extremality and the AdS$_2$ throat

The extremal limit is especially important. At

$$
Q^2=\frac{d}{d-2},
$$

the blackening factor has a double zero at the horizon. Expanding around $u=z/z_h=1$,

$$
f(u)
\simeq
d(d-1)(1-u)^2 .
$$

The near-horizon geometry becomes

$$
\mathrm{AdS}_2\times \mathbb R^{d-1},
$$

with AdS$_2$ radius

$$
L_2=\frac{L}{\sqrt{d(d-1)}} .
$$

This emergent AdS$_2$ region controls many low-frequency and low-temperature properties of the charged black brane. It is the geometric origin of the “IR criticality” discussed later in the course.

The phrase “emergent AdS$_2$” should be read carefully. The full UV theory is still a $d$-dimensional CFT. The AdS$_2$ throat describes an infrared sector associated with the near-horizon region of the extremal geometry.

## Why finite entropy at zero temperature is a warning

The extremal Reissner–Nordström-AdS black brane has

$$
T=0,
\qquad
s\neq0 .
$$

This is not automatically inconsistent, but it is unusual from the viewpoint of ordinary many-body ground states. It can mean that the two-derivative gravitational solution is an approximation hiding important low-temperature physics.

Possible resolutions include:

- charged scalar condensation, leading to holographic superconductors;
- charged fermion fluid or electron-star-like phases;
- lattice, disorder, or momentum relaxation effects;
- higher-derivative or stringy corrections;
- instabilities of the AdS$_2$ throat.

Therefore, RN-AdS is best understood as a universal finite-density saddle in a simple effective theory, not as the final answer to every finite-density problem.

## Spherical charged AdS black holes

The planar black brane is dual to the CFT on flat space $\mathbb R^{d-1}$. There are also charged AdS black holes with spherical horizons, dual to the CFT on $S^{d-1}$.

Spherical charged AdS black holes have richer phase structure. Depending on the ensemble and dimension, they can exhibit behavior analogous to liquid-gas transitions and critical points. These thermodynamic phenomena were among the early finite-density applications of AdS/CFT.

For the foundations course, the planar brane is the cleaner starting point because it isolates the finite-density state without the finite-volume scale of the sphere.

## Relation to the neutral black brane

The neutral black brane taught us the thermal dictionary:

$$
T_{\mathrm{CFT}}=T_{\mathrm{Hawking}},
\qquad
s_{\mathrm{CFT}}=\frac{\mathrm{Area}}{4G_{d+1}V} .
$$

The charged black brane adds the finite-density dictionary:

$$
\mu=A_t(0)-A_t(z_h),
\qquad
\rho=\text{radial electric flux} .
$$

Thus RN-AdS is not a completely new holographic idea. It is the same black-brane dictionary with one extra field turned on and allowed to backreact.

## Linear response around RN-AdS

To study transport, one perturbs the charged black brane:

$$
g_{MN}\to g_{MN}+h_{MN},
\qquad
A_M\to A_M+a_M .
$$

At nonzero density, gauge-field perturbations and metric perturbations generally mix. This is the bulk reason why charge, momentum, and energy transport are coupled in hydrodynamics.

For example, an electric field accelerates charge. If translations are exact, the charge current overlaps with conserved momentum, producing an infinite DC conductivity. In holography, this shows up as a coupled gauge-graviton fluctuation and a zero-frequency pole in the conductivity.

This is why finite-density holography quickly leads to topics such as momentum relaxation, holographic lattices, massive gravity models, and memory-matrix-like physics. Those topics are beyond this introductory page, but the source of the complication is already visible in the RN-AdS background.

## Dictionary checkpoint

| Boundary finite-density quantity | RN-AdS bulk quantity |
|---|---|
| temperature $T$ | horizon temperature |
| entropy density $s$ | horizon area density divided by $4G_{d+1}$ |
| chemical potential $\mu$ | $A_t(0)-A_t(z_h)$ |
| charge density $\rho$ | radial electric flux |
| grand potential $\Omega$ | renormalized Euclidean on-shell action |
| charged thermal state | charged black brane |
| zero-temperature finite-density IR | extremal near-horizon AdS$_2\times\mathbb R^{d-1}$ |
| current correlators | gauge and metric perturbations around RN-AdS |

The essential formula package is

$$
ds^2
=
\frac{L^2}{z^2}
\left[-f(z)dt^2+d\mathbf x_{d-1}^2+\frac{dz^2}{f(z)}\right],
$$

$$
f(z)
=
1-(1+Q^2)\left(\frac{z}{z_h}\right)^d
+Q^2\left(\frac{z}{z_h}\right)^{2d-2},
$$

$$
T
=
\frac{d-(d-2)Q^2}{4\pi z_h},
\qquad
s
=
\frac{L^{d-1}}{4G_{d+1}z_h^{d-1}} .
$$

## Common confusions

### “RN-AdS is always the correct finite-density ground state.”

No. It is the simplest homogeneous saddle of Einstein–Maxwell-AdS theory. Other fields or stringy corrections can make it unstable, especially near extremality.

### “The extremal entropy proves that the boundary theory has a huge exact ground-state degeneracy.”

It suggests a large degeneracy in the two-derivative saddle, but one must be careful. The extremal entropy may be lifted or reorganized by quantum, stringy, or matter-sector effects.

### “The parameter $Q$ is the boundary charge density.”

$Q$ is a dimensionless bulk charge parameter. It is proportional to the physical charge density only after choosing a precise normalization of the Maxwell action and holographic current.

### “Finite density only changes the gauge field.”

At small density or in a probe approximation, one may neglect backreaction. But a charge density of order the large-$N$ degrees of freedom backreacts on the metric and changes the horizon geometry.

### “AdS$_2$ means the whole theory becomes one-dimensional.”

No. The AdS$_2$ throat describes an infrared sector of the finite-density state. The UV boundary theory remains a $d$-dimensional CFT.

## Exercises

### Exercise 1: Derive the temperature

For

$$
f(u)=1-(1+Q^2)u^d+Q^2u^{2d-2},
\qquad
u=\frac{z}{z_h},
$$

show that

$$
T=\frac{d-(d-2)Q^2}{4\pi z_h} .
$$

<details>
<summary><strong>Solution</strong></summary>

First compute

$$
\frac{df}{du}
=-d(1+Q^2)u^{d-1}
+(2d-2)Q^2u^{2d-3} .
$$

At the horizon $u=1$,

$$
f'(1)
=-d(1+Q^2)+(2d-2)Q^2
=-d+(d-2)Q^2 .
$$

Since $u=z/z_h$,

$$
\frac{df}{dz}\bigg|_{z=z_h}
=
\frac{1}{z_h}[-d+(d-2)Q^2] .
$$

The Hawking temperature is

$$
T=\frac{|f'(z_h)|}{4\pi}
=
\frac{d-(d-2)Q^2}{4\pi z_h}
$$

for the nonextremal range $d-(d-2)Q^2>0$.

</details>

### Exercise 2: Find the extremal charge

Use the temperature formula to find the value of $Q^2$ at extremality.

<details>
<summary><strong>Solution</strong></summary>

Extremality means $T=0$, so

$$
d-(d-2)Q^2=0 .
$$

Therefore

$$
Q^2=\frac{d}{d-2} .
$$

</details>

### Exercise 3: Show that the extremal horizon is double zero

At extremality, show that

$$
f(u)\simeq d(d-1)(1-u)^2
$$

near $u=1$.

<details>
<summary><strong>Solution</strong></summary>

At extremality,

$$
Q^2=\frac{d}{d-2} .
$$

We already know $f(1)=0$ and $f'(1)=0$. Now compute

$$
f''(u)
=-d(d-1)(1+Q^2)u^{d-2}
+(2d-2)(2d-3)Q^2u^{2d-4} .
$$

At $u=1$ and $Q^2=d/(d-2)$,

$$
f''(1)=2d(d-1) .
$$

Thus

$$
f(u)
\simeq
\frac12 f''(1)(u-1)^2
=d(d-1)(1-u)^2 .
$$

</details>

### Exercise 4: Conformal thermodynamic identity

For a homogeneous isotropic CFT in flat space, the stress tensor has

$$
T^\mu{}_{\mu}=0 .
$$

Show that this implies $\epsilon=(d-1)p$.

<details>
<summary><strong>Solution</strong></summary>

For a homogeneous isotropic state,

$$
T^\mu{}_{\nu}
=\mathrm{diag}(-\epsilon,p,p,\ldots,p)
$$

in $d$ spacetime dimensions. The trace is

$$
T^\mu{}_{\mu}
=-\epsilon+(d-1)p .
$$

If the trace vanishes, then

$$
-\epsilon+(d-1)p=0,
$$

so

$$
\epsilon=(d-1)p .
$$

</details>

## Further reading

- A. Chamblin, R. Emparan, C. V. Johnson, and R. C. Myers, [Charged AdS Black Holes and Catastrophic Holography](https://arxiv.org/abs/hep-th/9902170).
- A. Chamblin, R. Emparan, C. V. Johnson, and R. C. Myers, [Holography, Thermodynamics and Fluctuations of Charged AdS Black Holes](https://arxiv.org/abs/hep-th/9904197).
- S. A. Hartnoll, [Lectures on holographic methods for condensed matter physics](https://arxiv.org/abs/0903.3246).
- J. McGreevy, [Holographic duality with a view toward many-body physics](https://arxiv.org/abs/0909.0518).
- T. Faulkner, H. Liu, J. McGreevy, and D. Vegh, [Emergent quantum criticality, Fermi surfaces, and AdS$_2$](https://arxiv.org/abs/0907.2694).
