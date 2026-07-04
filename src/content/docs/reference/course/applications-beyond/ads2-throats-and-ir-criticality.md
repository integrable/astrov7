---
title: "AdS2 Throats and IR Criticality"
description: "How extremal charged AdS black branes develop AdS2 x R^{d-1} near-horizon regions and why these throats control low-energy finite-density physics."
sidebar:
  label: "AdS2 Throats and IR Criticality"
  order: 70
---

At finite charge density, the simplest homogeneous holographic saddle is a charged AdS black brane. At nonzero temperature it has a regular horizon and ordinary thermal entropy. At zero temperature, however, the horizon does not disappear. In the minimal Einstein–Maxwell model, its near-horizon region becomes

$$
\mathrm{AdS}_2\times\mathbb R^{d-1}.
$$

This geometry is the basic infrared laboratory of finite-density holography. It says that the low-energy boundary dynamics is governed by an emergent scale invariance in time, while the spatial directions remain spectators. The resulting behavior is often called **local quantum criticality** or **semi-local criticality**.

The word “local” is easy to misread. The bulk theory is still local in spacetime. The point is that the IR scaling acts as

$$
t\to \lambda t,
\qquad
\vec x\to \vec x,
$$

so frequency scales but momentum does not.

<figure class="doc-figure" style="--figure-width: 52rem;">

![The near-horizon region of an extremal charged AdS black brane is an AdS2 throat times flat spatial directions.](/figures/course/ads2-throats-ir-criticality.svg)

<figcaption>

An extremal charged black brane interpolates between a UV $\mathrm{AdS}_{d+1}$ region and an IR throat $\mathrm{AdS}_2\times\mathbb R^{d-1}$. The radial direction is an RG scale, while the near-horizon electric field remembers the finite charge density.

</figcaption>
</figure>

## Why this matters

Finite-density quantum field theory is hard because the ground state can reorganize itself. Weakly coupled Fermi liquids have quasiparticles. Strongly coupled finite-density systems may not. Holography gives a different diagnostic:

> Look at the deep interior of the charged black brane.

For the minimal charged black brane, the deep interior is an AdS$_2$ throat. This has three major consequences.

First, low-frequency response functions inherit power laws from AdS$_2$. Second, spatial momentum labels different IR operators rather than scaling in the usual relativistic way. Third, extremal RN-AdS has a finite entropy density at $T=0$, which is powerful but suspicious: it often indicates that the simplest saddle is not the final microscopic ground state.

So AdS$_2$ is both a tool and a warning. It gives universal IR control in a simple finite-density phase, but it also points toward instabilities and more refined phases.

## Setup: the extremal charged black brane

Use the planar metric convention

$$
ds^2
=
\frac{L^2}{z^2}
\left[
-f(z)dt^2+d\vec x_{d-1}^{\,2}+\frac{dz^2}{f(z)}
\right],
\qquad
A=A_t(z)dt.
$$

The boundary is at $z=0$. The horizon is at $z=z_h$. For a non-extremal black brane, $f(z)$ has a simple zero at the horizon:

$$
f(z)\sim z_h-z.
$$

At extremality, the temperature vanishes and the zero becomes double:

$$
f(z)
=
\frac{d(d-1)}{z_*^2}(z_*-z)^2+\cdots,
$$

where $z_*$ is the extremal horizon position. This double zero is the geometric origin of the AdS$_2$ throat.

## Deriving the AdS$_2$ throat

Near the extremal horizon define

$$
\rho=z_*-z,
\qquad
\rho\ll z_*.
$$

Then

$$
ds^2
\approx
\frac{L^2}{z_*^2}
\left[
-d(d-1)\frac{\rho^2}{z_*^2}dt^2
+d\vec x_{d-1}^{\,2}
+
\frac{z_*^2}{d(d-1)}\frac{d\rho^2}{\rho^2}
\right].
$$

The $(t,\rho)$ part is AdS$_2$. Introducing a coordinate $\zeta$ proportional to $1/\rho$, the metric becomes

$$
ds^2
\approx
\frac{L_2^2}{\zeta^2}
\left(-dt^2+d\zeta^2\right)
+
\frac{L^2}{z_*^2}d\vec x_{d-1}^{\,2},
$$

with

$$
L_2^2=\frac{L^2}{d(d-1)}.
$$

Therefore

$$
\boxed{
\text{extremal RN-AdS}_{d+1}
\quad\longrightarrow\quad
\mathrm{AdS}_2\times\mathbb R^{d-1}
\quad\text{near the horizon}.
}
$$

The spatial $\mathbb R^{d-1}$ factor is not an accident. It is the horizon plane of the black brane.

## The near-horizon electric field

The gauge potential can be chosen to vanish at the horizon,

$$
A_t(z_*)=0,
$$

which is the regular gauge in Euclidean signature. But the electric field does not vanish:

$$
F_{\zeta t}\neq 0
$$

in the AdS$_2$ region. This matters because charged fields in AdS$_2$ feel the background electric field. Their effective IR scaling dimensions are shifted by their charge.

Boundary interpretation:

$$
\text{electric flux through the horizon}
\quad\longleftrightarrow\quad
\text{charge density carried by strongly coupled IR degrees of freedom}.
$$

If charge is instead carried by explicit bulk matter outside the horizon, the IR geometry and transport can change. This is one reason why RN-AdS is not the only possible finite-density ground state.

## The IR scaling symmetry

The AdS$_2$ metric

$$
ds_2^2=\frac{L_2^2}{\zeta^2}(-dt^2+d\zeta^2)
$$

is invariant under

$$
t\to\lambda t,
\qquad
\zeta\to\lambda\zeta.
$$

In the full throat geometry,

$$
ds^2=ds_{\mathrm{AdS}_2}^2+\ell_x^2d\vec x^{\,2},
\qquad
\ell_x=\frac{L}{z_*},
$$

the spatial coordinates do not scale. Momentum is therefore not assigned an ordinary scaling dimension. Instead, each value of $\vec k$ labels a different operator in the emergent IR CFT$_1$.

This is the semi-local scaling structure:

$$
\omega\to\lambda^{-1}\omega,
\qquad
\vec k\to\vec k.
$$

## Momentum-dependent IR dimensions

Consider a neutral scalar field of mass $m$ and Fourier mode

$$
\phi(t,\zeta,\vec x)
=
e^{-i\omega t+i\vec k\cdot\vec x}\phi_{\omega,k}(\zeta).
$$

In the AdS$_2$ region, spatial momentum contributes to an effective AdS$_2$ mass:

$$
m_{\mathrm{eff}}^2(k)
=
m^2+
\frac{k^2}{\ell_x^2}+\cdots.
$$

The dots can include spin-dependent terms, curvature couplings, or mixing with other fields. The AdS$_2$ scaling exponent is

$$
\nu_k
=
\sqrt{\frac14+m_{\mathrm{eff}}^2(k)L_2^2}.
$$

The two possible IR dimensions are

$$
\delta_k^{\pm}=\frac12\pm\nu_k.
$$

For a charged field, the background electric field shifts this expression schematically to

$$
\nu_k
=
\sqrt{\frac14+m_{\mathrm{eff}}^2(k)L_2^2-q_{\mathrm{eff}}^2}.
$$

This formula is the small hinge on which much of holographic finite-density physics turns. The exponent depends on $k$, even though $k$ itself does not scale.

## IR Green functions

A CFT$_1$ operator of dimension

$$
\delta_k=\frac12+\nu_k
$$

has a zero-temperature retarded Green function with power-law behavior

$$
\mathcal G_k^R(\omega)
\propto
\omega^{2\nu_k},
$$

up to a complex coefficient fixed by the infalling AdS$_2$ boundary condition.

At low but nonzero temperature, the throat becomes an AdS$_2$ black hole. The scaling form is

$$
\mathcal G_k^R(\omega,T)
=
T^{2\nu_k}
F_k\!\left(\frac{\omega}{T}\right),
$$

where the function $F_k$ is determined by the AdS$_2$ wave equation.

The full boundary Green function is obtained by matching this IR solution to the outer AdS$_{d+1}$ region. A common schematic form is

$$
G_R(\omega,k)
=
\frac{b_+(k)+b_-(k)\mathcal G_k^R(\omega)}
{a_+(k)+a_-(k)\mathcal G_k^R(\omega)}.
$$

The functions $a_\pm(k)$ and $b_\pm(k)$ are UV matching data. The nonanalytic frequency dependence comes from the AdS$_2$ throat.

## Semi-local versus ordinary criticality

At an ordinary relativistic fixed point,

$$
t\to\lambda t,
\qquad
\vec x\to\lambda\vec x,
$$

and correlators scale in terms of combinations involving both $\omega$ and $k$.

In an AdS$_2\times\mathbb R^{d-1}$ throat,

$$
t\to\lambda t,
\qquad
\vec x\to\vec x.
$$

Therefore the IR exponent can depend continuously on momentum:

$$
\mathcal G_k^R(\omega)\sim\omega^{2\nu_k}.
$$

This is not a standard CFT$_d$ scaling form. It is an emergent CFT$_1$ scaling form for a continuum of momentum-labeled sectors.

## Fermions and non-Fermi-liquid behavior

A famous application involves a charged bulk spinor. After matching the AdS$_2$ throat to the UV region, the boundary fermion Green function can take the schematic form

$$
G_R(\omega,k)
\simeq
\frac{h_1}
{k-k_F-v_F^{-1}\omega-h_2\omega^{2\nu_{k_F}}}.
$$

The Fermi momentum $k_F$ is determined by the UV problem. The exponent $\nu_{k_F}$ is determined by the IR AdS$_2$ throat. Depending on its value, the excitation can resemble a Fermi liquid quasiparticle, a non-Fermi liquid, or a marginal Fermi liquid.

The lesson for this course is the mechanism:

$$
\text{UV Fermi momentum}
+
\text{IR AdS}_2\text{ scaling}
\quad\Rightarrow\quad
\text{nontrivial spectral functions}.
$$

## The zero-temperature entropy puzzle

Extremal RN-AdS has finite horizon area at zero temperature. Hence

$$
s_0
=
\frac{1}{4G_{d+1}}
\frac{L^{d-1}}{z_*^{d-1}}
$$

is nonzero. For an ordinary isolated quantum system, a finite ground-state entropy density is unusual. In holography it is often treated as a clue that the minimal Einstein–Maxwell saddle is incomplete in the deep IR.

Possible resolutions include:

- charged scalar condensation, leading to holographic superconductors;
- charged fermion fluids, leading to electron-star-like geometries;
- lattice or translation-breaking effects;
- hyperscaling-violating or Lifshitz IR geometries;
- stringy or finite-$N$ corrections that lift the degeneracy.

RN-AdS is therefore best read as a controlled, universal starting point, not as a universal endpoint.

## Dictionary checkpoint

| Bulk statement | Boundary statement |
|---|---|
| extremal charged horizon | zero-temperature finite-density state |
| $\mathrm{AdS}_2\times\mathbb R^{d-1}$ throat | emergent IR CFT$_1$ sectors |
| radial coordinate in AdS$_2$ | low-energy scale |
| near-horizon electric field | finite charge density |
| exponent $\nu_k$ | momentum-dependent IR critical exponent |
| infalling AdS$_2$ condition | retarded IR response |
| finite extremal area | finite $T=0$ entropy density, often signaling degeneracy or instability |

## Common confusions

### “AdS$_2$ means the boundary theory literally becomes one-dimensional.”

No. The UV theory still lives in $d$ spacetime dimensions. The statement is that the low-frequency dynamics is controlled by an emergent CFT$_1$-like sector, with momentum acting as a label.

### “Momentum disappears in the IR.”

No. Momentum enters the effective AdS$_2$ mass and therefore the exponent $\nu_k$. What disappears is ordinary spatial scaling.

### “Extremal RN-AdS is automatically the true ground state.”

No. It is the simplest homogeneous saddle of Einstein–Maxwell theory. Many models become unstable at low temperature or flow to a different IR geometry.

### “The finite entropy is harmless.”

It may be a useful large-$N$ saddle artifact, but it is also a warning. In many microscopic theories one expects additional effects to resolve or replace the extremal horizon degeneracy.

## Exercises

### Exercise 1: The double zero and AdS$_2$

Suppose near an extremal horizon $z=z_*$,

$$
f(z)=c(z_*-z)^2+\cdots,
\qquad
c>0.
$$

Show that the $(t,z)$ part of

$$
ds^2=\frac{L^2}{z^2}\left[-f(z)dt^2+\frac{dz^2}{f(z)}\right]
$$

is locally AdS$_2$ near the horizon.

<details>
<summary><strong>Solution</strong></summary>

Set $\rho=z_*-z$. To leading order,

$$
ds_2^2
\approx
\frac{L^2}{z_*^2}
\left[-c\rho^2dt^2+\frac{d\rho^2}{c\rho^2}\right].
$$

Define $\tilde t=ct$ and $\zeta=1/(c\rho)$. Then

$$
ds_2^2
=
\frac{L^2}{c z_*^2}\frac{-d\tilde t^2+d\zeta^2}{\zeta^2},
$$

which is AdS$_2$. For extremal planar RN-AdS, $c=d(d-1)/z_*^2$, so $L_2=L/\sqrt{d(d-1)}$.

</details>

### Exercise 2: Momentum as an IR mass

For

$$
ds^2=ds_{\mathrm{AdS}_2}^2+\ell_x^2d\vec x^{\,2},
$$

show that a scalar Fourier mode with spatial momentum $k$ behaves in AdS$_2$ like a scalar of mass

$$
m_{\mathrm{eff}}^2(k)=m^2+\frac{k^2}{\ell_x^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

The scalar wave equation contains the term $g^{ij}k_i k_j\phi$. Since $g^{ij}=\ell_x^{-2}\delta^{ij}$, this contribution is $k^2/\ell_x^2$. Therefore the AdS$_2$ radial equation contains the effective mass

$$
m_{\mathrm{eff}}^2(k)=m^2+\frac{k^2}{\ell_x^2}.
$$

The IR scaling exponent is then

$$
\nu_k=\sqrt{\frac14+m_{\mathrm{eff}}^2(k)L_2^2}.
$$

</details>

### Exercise 3: Semi-local scaling

Why is

$$
\mathcal G_k^R(\omega)\propto\omega^{2\nu_k}
$$

not the usual scaling form of a relativistic CFT$_d$?

<details>
<summary><strong>Solution</strong></summary>

In a relativistic CFT$_d$, time and space scale together, so correlators scale in combinations involving both $\omega$ and $k$. In the AdS$_2\times\mathbb R^{d-1}$ throat only time and the AdS$_2$ radial coordinate scale. Momentum remains a label, and the exponent itself may depend on $k$. This is the semi-local feature.

</details>

## Further reading

- T. Faulkner, H. Liu, J. McGreevy, and D. Vegh, [Emergent quantum criticality, Fermi surfaces, and AdS$_2$](https://arxiv.org/abs/0907.2694).
- S. A. Hartnoll, [Lectures on holographic methods for condensed matter physics](https://arxiv.org/abs/0903.3246).
- S. A. Hartnoll, J. Polchinski, E. Silverstein, and D. Tong, [Towards strange metallic holography](https://arxiv.org/abs/0912.1061).
- N. Iqbal, H. Liu, and M. Mezei, [Semi-local quantum liquids](https://arxiv.org/abs/1105.4621).
- J. McGreevy, [Holographic duality with a view toward many-body physics](https://arxiv.org/abs/0909.0518).
