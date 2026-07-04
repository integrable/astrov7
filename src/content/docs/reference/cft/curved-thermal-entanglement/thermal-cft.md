---
title: "Thermal CFT"
description: "Thermal circle, KMS condition, retarded correlators, equation of state, and the black-brane preparation for AdS/CFT."
sidebar:
  order: 3
---

A CFT at nonzero temperature is no longer conformally invariant in the same sense as the vacuum. The temperature introduces a scale,

$$
T=\beta^{-1},
$$

and the thermal density matrix chooses a rest frame. Nevertheless, thermal CFT is still enormously constrained. There is no intrinsic mass scale, so every extensive thermodynamic quantity is fixed up to a dimensionless constant. Correlators obey KMS periodicity. The stress tensor has a universal ideal-fluid form. Real-time correlators have analyticity and positivity properties that become, in holography, causality and regularity at black-hole horizons.

This page is the bridge between CFT kinematics and black holes. The slogan is:

$$
\boxed{
\text{thermal CFT state}
\quad\longleftrightarrow\quad
\text{AdS black hole or black brane}
}
$$

More precisely, a CFT on $S^{d-1}$ at finite temperature prepares states dual to global AdS black holes, while a CFT on $\mathbb R^{d-1}$ at finite temperature prepares the planar black-brane geometry.

## Thermal density matrix

Let the CFT be quantized on spatial manifold $\Sigma$. In this course the two most important cases are

$$
\Sigma=\mathbb R^{d-1},
\qquad
\Sigma=S^{d-1}.
$$

A thermal state is defined by the density matrix

$$
\rho_\beta={e^{-\beta H}\over Z(\beta)},
\qquad
Z(\beta)=\operatorname{Tr}_{\mathcal H_\Sigma}e^{-\beta H},
$$

and thermal expectation values are

$$
\langle \mathcal A\rangle_\beta
=\operatorname{Tr}\left(\rho_\beta \mathcal A\right).
$$

The trace is over the Hilbert space obtained by quantizing the CFT on $\Sigma$. On $S^{d-1}$ the spectrum is discrete, and by the state-operator map the Hamiltonian is essentially the dilatation operator:

$$
H_{S^{d-1}}={1\over R}D,
$$

up to vacuum/Casimir terms. On $\mathbb R^{d-1}$ the spectrum is continuous and the thermodynamic limit is more natural.

The partition function is related to the free energy by

$$
F(T)=-T\log Z(\beta),
$$

and, for a homogeneous system of spatial volume $V$, one defines

$$
f={F\over V},
\qquad
p=-f,
\qquad
s=-{\partial f\over \partial T},
\qquad
\epsilon={E\over V}=f+Ts.
$$

Here $p$ is pressure, $s$ is entropy density, and $\epsilon$ is energy density.

## Euclidean thermal circle

The Euclidean path-integral representation of $Z(\beta)$ is obtained by compactifying Euclidean time:

$$
\tau\sim \tau+\beta.
$$

Thus a thermal CFT on $\mathbb R^{d-1}$ is formulated on

$$
S^1_\beta\times \mathbb R^{d-1}.
$$

Bosonic fields are periodic around the thermal circle. Fermionic fields are antiperiodic:

$$
\Phi(\tau+\beta,\vec x)=\Phi(\tau,\vec x),
\qquad
\Psi(\tau+\beta,\vec x)=-\Psi(\tau,\vec x).
$$

This is not merely a convention. The antiperiodic fermion boundary condition follows from the trace defining the thermal ensemble and is responsible for fermionic Matsubara frequencies.

The allowed Euclidean frequencies are

$$
\omega_n=
\begin{cases}
{2\pi n\over \beta}, & \text{bosons},\\[4pt]
{(2n+1)\pi\over \beta}, & \text{fermions},
\end{cases}
\qquad n\in\mathbb Z.
$$

<figure class="doc-figure" style="--figure-width: 44rem; --caption-width: 55rem;">

![Thermal CFT from the Euclidean circle to the black brane](/figures/cft/thermal-cft-circle-kms-black-brane.svg)

<figcaption>

A thermal CFT is naturally defined on $S^1_\beta\times\mathbb R^{d-1}$. Analytic continuation gives Lorentzian real-time correlators constrained by the KMS condition. In holographic CFTs, the planar thermal state is dual to an AdS black brane with horizon $z=z_h$ and temperature $T=d/(4\pi z_h)$.

</figcaption>
</figure>

The Euclidean path integral on the thermal circle computes thermal correlators ordered along Euclidean time:

$$
G_E(\tau_1,\vec x_1;\ldots;\tau_n,\vec x_n)
=
\langle \mathcal T_\tau\,
\mathcal O_1(\tau_1,\vec x_1)\cdots
\mathcal O_n(\tau_n,\vec x_n)\rangle_\beta.
$$

Because the thermal circle has finite circumference, Euclidean time translation remains a symmetry, but scale invariance is broken by the circumference $\beta$.

The important conceptual point is subtle but simple: the theory is still a CFT, but the state is not the vacuum. Thermal expectation values are constrained by the CFT operator algebra and by the remaining symmetries of the thermal state.

## KMS condition

The Kubo-Martin-Schwinger condition is the defining analytic property of thermal equilibrium.

For two bosonic operators $A$ and $B$, define Lorentzian Wightman functions

$$
G^>_{AB}(t)=\langle A(t)B(0)\rangle_\beta,
\qquad
G^<_{AB}(t)=\langle B(0)A(t)\rangle_\beta.
$$

Using $A(t)=e^{iHt}A(0)e^{-iHt}$ and the cyclicity of the trace, one obtains

$$
\boxed{
G^>_{AB}(t-i\beta)=G^<_{AB}(t)
}
$$

for bosonic operators. For fermionic operators there is an extra minus sign when one moves a fermion around the thermal trace.

The KMS condition has several equivalent forms. In Euclidean time, bosonic correlators are periodic:

$$
G_E(\tau+\beta)=G_E(\tau),
$$

while fermionic correlators are antiperiodic:

$$
G_E(\tau+\beta)=-G_E(\tau).
$$

In frequency space, KMS relates the two Wightman functions to the spectral density. For a bosonic operator, define

$$
\rho_{AB}(\omega,\vec k)
=G^>_{AB}(\omega,\vec k)-G^<_{AB}(\omega,\vec k).
$$

Then

$$
G^>_{AB}(\omega,\vec k)
={\rho_{AB}(\omega,\vec k)\over 1-e^{-\beta\omega}},
\qquad
G^<_{AB}(\omega,\vec k)
={e^{-\beta\omega}\rho_{AB}(\omega,\vec k)\over 1-e^{-\beta\omega}}.
$$

Equivalently,

$$
G^>_{AB}(\omega,\vec k)=e^{\beta\omega}G^<_{AB}(\omega,\vec k).
$$

This is the finite-temperature generalization of the spectral representation of vacuum correlators.

## Real-time thermal correlators

For AdS/CFT, the Euclidean thermal path integral is not enough. Black holes are Lorentzian objects, and the most physical observables are real-time response functions.

The retarded Green function of a bosonic operator $\mathcal O$ is

$$
G_R(t,\vec x)
=-i\theta(t)\langle [\mathcal O(t,\vec x),\mathcal O(0,\vec 0)]\rangle_\beta.
$$

Its Fourier transform is analytic in the upper half complex $\omega$-plane. The spectral density is

$$
\rho(\omega,\vec k)
=-2\operatorname{Im}G_R(\omega,\vec k),
$$

up to the sign convention used in defining $G_R$. The convention above is common in high-energy theory; some condensed-matter references use the opposite sign.

Euclidean correlators are evaluated at Matsubara frequencies. For bosons,

$$
G_E(\omega_n,\vec k),
\qquad
\omega_n=2\pi nT.
$$

The retarded correlator is obtained by analytic continuation

$$
\boxed{
G_R(\omega,\vec k)=G_E(\omega_n,\vec k)\big|_{i\omega_n\to \omega+i0^+}
}
$$

provided the analytic continuation is made to the function with the correct analyticity domain.

This last caveat is not pedantic. At finite temperature, there are several inequivalent Lorentzian correlators: time-ordered, retarded, advanced, Wightman, and Schwinger-Keldysh correlators. The Euclidean correlator knows them only through analytic continuation and KMS.

## What symmetries remain at finite temperature?

The thermal state on flat space preserves spatial translations, spatial rotations, and time translations. It does not preserve Lorentz boosts. In Lorentzian signature the thermal state has a preferred velocity vector $u^\mu$, normalized by

$$
u^\mu u_\mu=-1.
$$

In the rest frame,

$$
u^\mu=(1,\vec 0).
$$

It is often useful to write finite-temperature expectation values in a covariant-looking form using $u^\mu$ and the metric $\eta_{\mu\nu}$.

For example, a scalar primary has thermal one-point function

$$
\langle \mathcal O\rangle_\beta=a_{\mathcal O}T^\Delta,
$$

provided it is allowed by internal symmetries. If $\mathcal O$ is charged under an unbroken global symmetry, then $\langle \mathcal O\rangle_\beta=0$.

For a symmetric traceless spin-$\ell$ primary, the thermal one-point function takes the schematic form

$$
\langle \mathcal O_{\mu_1\cdots\mu_\ell}\rangle_\beta
=b_{\mathcal O}T^\Delta
\left[u_{\mu_1}\cdots u_{\mu_\ell}-\text{traces}\right],
$$

again assuming no symmetry forbids it. The coefficients $a_{\mathcal O}$ and $b_{\mathcal O}$ are dynamical CFT data in the thermal state. They are not determined by conformal symmetry alone.

## Stress tensor one-point function

The most important thermal one-point function is that of the stress tensor. In a homogeneous and isotropic thermal state,

$$
\langle T^{\mu\nu}\rangle_\beta
=(\epsilon+p)u^\mu u^\nu+p\eta^{\mu\nu}.
$$

In the rest frame this is

$$
\langle T^{\mu}{}_{\nu}\rangle_\beta
=\operatorname{diag}(-\epsilon,p,p,\ldots,p).
$$

For a CFT on flat spacetime without a trace anomaly, the stress tensor is traceless:

$$
\langle T^\mu{}_{\mu}\rangle_\beta=0.
$$

Therefore

$$
-\epsilon+(d-1)p=0,
$$

or

$$
\boxed{
\epsilon=(d-1)p.
}
$$

This is the conformal equation of state. Since there is no other scale on $\mathbb R^{d-1}$, dimensional analysis gives

$$
p(T)=a_T T^d,
$$

where $a_T$ is a dimensionless constant characterizing the CFT. Hence

$$
\epsilon(T)=(d-1)a_T T^d,
$$

and

$$
s(T)={\partial p\over \partial T}=d a_T T^{d-1}.
$$

The speed of sound is universal:

$$
c_s^2={\partial p\over \partial \epsilon}={1\over d-1}.
$$

This result is one of the first hydrodynamic fingerprints of conformality.

On curved spaces, such as $S^{d-1}\times S^1_\beta$, there can be additional dependence on $RT$, where $R$ is the sphere radius. In that case the free energy has the form

$$
F(T,R)=R^{-1}\,\mathcal F(RT),
$$

up to powers of $R$ appropriate to the total free energy. At high temperature, $RT\gg 1$, the leading extensive part approaches the flat-space answer.

## Thermal correlators in 2D CFT

In two dimensions, finite-temperature correlators of primary fields can often be obtained by a conformal map. Consider a primary field with weights $(h,\bar h)$ on the plane. Let

$$
w=x+i\tau,
\qquad
\tau\sim \tau+\beta,
$$

and map the thermal cylinder to the plane by

$$
z=e^{2\pi w/\beta}.
$$

Using the primary transformation law, the two-point function on the cylinder is

$$
\boxed{
\langle \mathcal O(w,\bar w)\mathcal O(0,0)\rangle_\beta
=
\left({\pi/\beta\over \sinh(\pi w/\beta)}\right)^{2h}
\left({\pi/\beta\over \sinh(\pi \bar w/\beta)}\right)^{2\bar h}
}
$$

for a noncompact spatial direction. This formula shows how exponential thermal decay emerges from a vacuum power law. At large spatial separation $x\gg \beta$,

$$
\langle \mathcal O(x)\mathcal O(0)\rangle_\beta
\sim e^{-2\pi\Delta x/\beta},
\qquad
\Delta=h+\bar h.
$$

So the thermal state has a finite correlation length

$$
\xi_\beta={\beta\over 2\pi\Delta}
$$

for this operator. This does not mean the CFT itself has become massive. Rather, the thermal state introduces a scale and causes spatial correlations to decay exponentially.

For a CFT on a spatial circle, the story is richer because the Euclidean spacetime is a torus. Then modular invariance becomes a powerful constraint, and the high-temperature density of states is controlled by the Cardy formula. This is the CFT$_2$ precursor of BTZ black-hole entropy.

## Thermal OPE versus zero-temperature OPE

The local OPE is a statement about short distances and remains valid inside a thermal state:

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ijk}\,\mathcal D_{ij}^{k}(x,\partial)\mathcal O_k(0).
$$

Taking a thermal expectation value gives

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle_\beta
\sim
\sum_k C_{ijk}\,\mathcal D_{ij}^{k}(x,\partial)\langle \mathcal O_k\rangle_\beta.
$$

This is called the thermal OPE expansion. It is useful when

$$
|x|\ll \beta.
$$

The data entering this expansion are of two types:

1. ordinary vacuum CFT data, such as $\Delta_k$, spins, and $C_{ijk}$;
2. thermal one-point coefficients, such as $a_{\mathcal O_k}$.

This separation is conceptually important. The operator algebra is the same CFT operator algebra as at zero temperature. The state-dependent information appears through one-point functions.

For AdS/CFT, this is the boundary counterpart of the statement that short-distance physics near the AdS boundary is governed by the same local bulk fields and interactions, while the thermal state changes the bulk background from pure AdS to a black-hole geometry.

## Hydrodynamic limit

At long wavelengths and late times, any interacting thermal QFT is described by hydrodynamics if it has conserved densities. A CFT has at least the conserved stress tensor, and possibly conserved global currents.

Hydrodynamics is an expansion in

$$
\omega\ll T,
\qquad
|\vec k|\ll T.
$$

For a CFT with no conserved charge, the stress tensor retarded correlator contains shear and sound modes. The shear mode has dispersion

$$
\omega=-iD_\eta k^2+\cdots,
$$

where

$$
D_\eta={\eta\over \epsilon+p}
$$

is the momentum diffusion constant and $\eta$ is the shear viscosity.

The sound modes have dispersion

$$
\omega=\pm c_s k-i\Gamma_s k^2+\cdots,
$$

with

$$
c_s^2={1\over d-1}.
$$

For a conformal fluid, the bulk viscosity vanishes:

$$
\zeta=0.
$$

The shear viscosity $\eta$ is dynamical. In holographic CFTs with a classical Einstein gravity dual, one famously finds

$$
{\eta\over s}={1\over 4\pi},
$$

but this is not a universal property of all CFTs. It is a property of a special large-$N$, strongly coupled regime with a two-derivative Einstein gravity description.

## Thermalization and operator probes

Thermal CFT correlators probe how disturbances relax. A local operator insertion creates an excitation above the thermal state. The late-time behavior of the retarded correlator is controlled by singularities of $G_R(\omega,\vec k)$ in the lower half complex $\omega$-plane.

In a generic interacting thermal system, one expects poles and branch cuts associated with relaxation. In holographic large-$N$ CFTs, many real-time correlators have poles corresponding to black-brane quasinormal modes:

$$
\omega=\omega_n(\vec k),
\qquad
\operatorname{Im}\omega_n<0.
$$

These poles encode decay of perturbations into the black-hole horizon. The CFT statement is that the thermal state absorbs and scrambles perturbations.

The hierarchy is:

$$
\boxed{
\text{hydrodynamic poles}
\subset
\text{thermal poles of }G_R
\leftrightarrow
\text{black-brane quasinormal modes}.
}
$$

Hydrodynamic poles are universal consequences of conservation laws. Nonhydrodynamic poles are more microscopic and depend on the CFT.

## Holographic thermal states

For a holographic CFT on $\mathbb R^{d-1}$, the high-temperature homogeneous state is dual to the planar AdS$_{d+1}$ black brane:

$$
ds^2={L^2\over z^2}
\left[-f(z)dt^2+d\vec x^{\,2}+{dz^2\over f(z)}\right],
\qquad
f(z)=1-\left({z\over z_h}\right)^d.
$$

The AdS boundary is at $z=0$, and the horizon is at $z=z_h$. Regularity of the Euclidean geometry fixes the temperature:

$$
T={d\over 4\pi z_h}.
$$

The Bekenstein-Hawking entropy density is

$$
s={1\over 4G_{d+1}}\left({L\over z_h}\right)^{d-1}.
$$

Using $z_h=d/(4\pi T)$, this gives

$$
s\propto T^{d-1},
$$

exactly as required by CFT thermodynamics.

Likewise, the black-brane energy density and pressure obey

$$
\epsilon=(d-1)p,
$$

matching the tracelessness of the boundary stress tensor.

This is one of the cleanest early checks of AdS/CFT: the geometry knows the CFT equation of state because the horizon area scales with the only available thermal scale.

## Global AdS, Hawking-Page physics, and finite volume

On $S^{d-1}$, the thermal CFT partition function is not purely extensive because the sphere radius $R$ is another scale. The dimensionless control parameter is

$$
RT.
$$

In large-$N$ holographic CFTs, the thermal ensemble on $S^{d-1}$ has two important bulk saddles:

$$
\text{thermal AdS},
\qquad
\text{AdS-Schwarzschild black hole}.
$$

At low temperature, thermal AdS dominates. At high temperature, a large AdS black hole dominates. The transition between these saddles is the Hawking-Page transition. In the boundary gauge theory, it is interpreted as a confinement/deconfinement-like transition in the large-$N$ limit.

This is not a universal feature of every CFT. It is a feature of large-$N$ holographic CFTs on compact space. On flat space $\mathbb R^{d-1}$, the planar black brane is the natural homogeneous thermal saddle.

## AdS/CFT checkpoint

Thermal CFT is where several pieces of the holographic dictionary first become concrete:

$$
\begin{array}{ccl}
\text{CFT thermal circle } S^1_\beta
&\longleftrightarrow&
\text{Euclidean black-hole regularity},\\[4pt]
\text{temperature } T
&\longleftrightarrow&
\text{surface gravity / horizon radius},\\[4pt]
\langle T_{\mu\nu}\rangle_\beta
&\longleftrightarrow&
\text{asymptotic metric coefficient},\\[4pt]
\text{entropy density }s
&\longleftrightarrow&
\text{horizon area density}/4G_N,\\[4pt]
G_R(\omega,k)
&\longleftrightarrow&
\text{infalling bulk wave problem},\\[4pt]
\text{hydrodynamic poles}
&\longleftrightarrow&
\text{long-wavelength black-brane perturbations}.
\end{array}
$$

The practical lesson is that one should understand thermal CFT before studying AdS black holes. The black hole is not an extra object added to the CFT; it is the gravitational representation of the CFT thermal state.

## Common pitfalls

A thermal CFT is not scale invariant as a state. The underlying theory has no scale, but the state has the scale $T$. Therefore correlators can and usually do depend on dimensionless combinations such as $Tx$, $\omega/T$, and $k/T$.

The Euclidean thermal correlator is not automatically the retarded correlator. One must analytically continue with the correct $i0^+$ prescription. This distinction is the boundary version of imposing infalling rather than outgoing boundary conditions at a black-hole horizon.

Thermal exponential decay does not imply a mass gap in the theory. It reflects finite temperature and the compact Euclidean time circle. The zero-temperature CFT can remain exactly gapless.

The relation $\eta/s=1/(4\pi)$ is not a theorem of conformal symmetry. It is a result for a special class of holographic CFTs with classical two-derivative Einstein gravity duals.

## Exercises

### Exercise 1 — Conformal equation of state

Consider a homogeneous thermal CFT on $\mathbb R^{d-1}$. Assume the stress tensor has ideal-fluid form

$$
\langle T^{\mu\nu}\rangle=(\epsilon+p)u^\mu u^\nu+p\eta^{\mu\nu}.
$$

Use tracelessness to derive $\epsilon=(d-1)p$. Then use dimensional analysis to determine the temperature dependence of $p$, $\epsilon$, and $s$.

<details><summary><strong>Solution</strong></summary>

In the rest frame,

$$
\langle T^\mu{}_{\nu}\rangle=\operatorname{diag}(-\epsilon,p,\ldots,p).
$$

Tracelessness gives

$$
0=\langle T^\mu{}_{\mu}\rangle=-\epsilon+(d-1)p.
$$

Therefore

$$
\epsilon=(d-1)p.
$$

On flat space, the only scale is $T$, and pressure has mass dimension $d$. Hence

$$
p=a_TT^d.
$$

Then

$$
\epsilon=(d-1)a_TT^d,
$$

and

$$
s={\partial p\over\partial T}=d a_TT^{d-1}.
$$

</details>

### Exercise 2 — Derive the KMS condition

Let

$$
G^>_{AB}(t)=Z^{-1}\operatorname{Tr}\left(e^{-\beta H}A(t)B(0)\right),
$$

where $A(t)=e^{iHt}A(0)e^{-iHt}$. Show that

$$
G^>_{AB}(t-i\beta)=G^<_{AB}(t),
$$

where

$$
G^<_{AB}(t)=\langle B(0)A(t)\rangle_\beta.
$$

Assume $A$ and $B$ are bosonic.

<details><summary><strong>Solution</strong></summary>

First continue $t$ to $t-i\beta$:

$$
A(t-i\beta)=e^{iH(t-i\beta)}A(0)e^{-iH(t-i\beta)}
=e^{iHt}e^{\beta H}A(0)e^{-\beta H}e^{-iHt}.
$$

Then

$$
\begin{aligned}
G^>_{AB}(t-i\beta)
&=Z^{-1}\operatorname{Tr}\left(e^{-\beta H}A(t-i\beta)B(0)\right)\\
&=Z^{-1}\operatorname{Tr}\left(A(t)e^{-\beta H}B(0)\right).
\end{aligned}
$$

Using cyclicity of the trace,

$$
G^>_{AB}(t-i\beta)
=Z^{-1}\operatorname{Tr}\left(e^{-\beta H}B(0)A(t)\right)
=G^<_{AB}(t).
$$

For fermionic operators, cyclically moving a fermionic operator around the thermal trace gives an additional sign.

</details>

### Exercise 3 — Thermal two-point function in 2D

A primary field $\mathcal O$ with weights $(h,\bar h)$ has plane two-point function

$$
\langle \mathcal O(z,\bar z)\mathcal O(0,0)\rangle
={1\over z^{2h}\bar z^{2\bar h}}.
$$

Use the map

$$
z=e^{2\pi w/\beta}
$$

from the cylinder coordinate $w=x+i\tau$ to the plane to derive

$$
\langle \mathcal O(w,\bar w)\mathcal O(0,0)\rangle_\beta
=
\left({\pi/\beta\over \sinh(\pi w/\beta)}\right)^{2h}
\left({\pi/\beta\over \sinh(\pi \bar w/\beta)}\right)^{2\bar h}.
$$

<details><summary><strong>Solution</strong></summary>

Under $z=e^{2\pi w/\beta}$,

$$
{dz\over dw}={2\pi\over\beta}z.
$$

A primary transforms as

$$
\mathcal O(w,\bar w)
=\left({dz\over dw}\right)^h
\left({d\bar z\over d\bar w}\right)^{\bar h}
\mathcal O(z,\bar z).
$$

Place one operator at $w$ and the other at $0$. Then $z_1=e^{2\pi w/\beta}$ and $z_2=1$. The holomorphic part is

$$
\left({2\pi\over\beta}\right)^{2h}
{z_1^h z_2^h\over (z_1-z_2)^{2h}}.
$$

Since

$$
z_1-z_2=e^{\pi w/\beta}\left(e^{\pi w/\beta}-e^{-\pi w/\beta}\right)
=2e^{\pi w/\beta}\sinh(\pi w/\beta),
$$

and $z_1^h=e^{2\pi h w/\beta}$, the exponential factors cancel, leaving

$$
\left({\pi/\beta\over \sinh(\pi w/\beta)}\right)^{2h}.
$$

The antiholomorphic part is identical with $w\to\bar w$ and $h\to\bar h$.

</details>

### Exercise 4 — Black-brane entropy scaling

For the planar AdS$_{d+1}$ black brane,

$$
ds^2={L^2\over z^2}\left[-f(z)dt^2+d\vec x^{\,2}+{dz^2\over f(z)}\right],
\qquad
f(z)=1-\left({z\over z_h}\right)^d,
$$

show that the Bekenstein-Hawking entropy density scales as $T^{d-1}$.

<details><summary><strong>Solution</strong></summary>

At the horizon $z=z_h$, the induced metric along the spatial boundary directions is

$$
ds^2_{\text{horizon}}={L^2\over z_h^2}d\vec x^{\,2}.
$$

Therefore the horizon area per unit boundary volume is

$$
{A\over V}=\left({L\over z_h}\right)^{d-1}.
$$

The entropy density is

$$
s={1\over 4G_{d+1}}\left({L\over z_h}\right)^{d-1}.
$$

The Euclidean regularity condition gives

$$
T={d\over 4\pi z_h},
$$

so $z_h\propto T^{-1}$. Hence

$$
s\propto z_h^{-(d-1)}\propto T^{d-1}.
$$

This matches the thermal scaling required by conformal invariance.

</details>

## Further reading

For thermal QFT and finite-temperature correlators, useful references are Kapusta and Gale, *Finite-Temperature Field Theory*, Laine and Vuorinen, *Basics of Thermal Field Theory*, and Le Bellac, *Thermal Field Theory*. For the CFT side of modular thermal physics in two dimensions, see Di Francesco, Mathieu, and Sénéchal, especially the chapters on modular invariance and finite-size scaling. For the holographic black-brane dictionary, the natural continuation is the finite-temperature chapters of standard AdS/CFT lecture notes and reviews.
