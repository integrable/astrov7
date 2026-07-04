---
title: "Hydrodynamics from Gravity"
description: "How long-wavelength black-brane perturbations become relativistic hydrodynamics in the dual thermal field theory."
sidebar:
  order: 70
---

## Why this matters

The previous pages explained real-time correlators and quasinormal modes. Hydrodynamics is the universal low-frequency corner of that story.

A thermal quantum field theory has infinitely many microscopic degrees of freedom, but at sufficiently long wavelengths almost all of them are irrelevant. The only slow variables are the densities of conserved quantities: energy, momentum, and any conserved charges. Their dynamics is constrained by conservation laws and organized by a derivative expansion. This is hydrodynamics.

Holographically, the same statement becomes geometric:

$$
\boxed{
\text{long-wavelength black-brane perturbations}
\quad\longleftrightarrow\quad
\text{relativistic fluid dynamics of the boundary theory}
}
$$

This is one of the cleanest examples of emergence in AdS/CFT. Einstein's equations in one higher dimension reduce, in a controlled long-wavelength limit, to the Navier–Stokes equations of the boundary plasma.

The lesson is not that gravity is “like” hydrodynamics. The sharper statement is that the constraint equations and regularity conditions of the bulk gravitational problem determine the hydrodynamic equations and transport coefficients of the boundary state.

## The boundary hydrodynamic setup

Let the boundary theory live on a background metric $g_{(0)\mu\nu}$ in $d$ spacetime dimensions. A relativistic fluid is described locally by a temperature field $T(x)$ and a velocity field $u^\mu(x)$ satisfying

$$
u^\mu u_\mu=-1 .
$$

The projector transverse to the velocity is

$$
\Delta^{\mu\nu}
=
g_{(0)}^{\mu\nu}+u^\mu u^\nu .
$$

At zero chemical potential, the hydrodynamic stress tensor is expanded in derivatives:

$$
T^{\mu\nu}
=
\epsilon u^\mu u^\nu
+
p\Delta^{\mu\nu}
-
\eta\sigma^{\mu\nu}
-
\zeta\Delta^{\mu\nu}\nabla_\rho u^\rho
+
\cdots .
$$

Here $\epsilon$ is the energy density, $p$ is the pressure, $\eta$ is the shear viscosity, and $\zeta$ is the bulk viscosity. The shear tensor is

$$
\sigma^{\mu\nu}
=
\Delta^{\mu\alpha}\Delta^{\nu\beta}
\left(
\nabla_\alpha u_\beta
+
\nabla_\beta u_\alpha
-
\frac{2}{d-1}g_{(0)\alpha\beta}\nabla_\rho u^\rho
\right).
$$

For a conformal field theory,

$$
T^\mu_{\ \mu}=0,
\qquad
\epsilon=(d-1)p,
\qquad
\zeta=0.
$$

The equations of motion are not extra assumptions. They are the Ward identities for translation invariance:

$$
\boxed{
\nabla_\mu T^{\mu\nu}=0 .
}
$$

Hydrodynamics is the statement that this equation closes after writing $T^{\mu\nu}$ as a derivative expansion in $T(x)$ and $u^\mu(x)$.

## Why hydrodynamics is a derivative expansion

The expansion parameter is not the amplitude of the perturbation. It is the ratio

$$
\frac{\ell_{\rm microscopic}}{\ell_{\rm variation}} .
$$

For a thermal CFT with no other scale, the microscopic length is of order $1/T$. Therefore hydrodynamics requires

$$
\omega\ll T,
\qquad
|\mathbf{k}|\ll T.
$$

The fluid can have large velocity variations in amplitude, as long as those variations are slow in space and time. This is important in holography because the fluid/gravity construction can treat nonlinear fluid motion perturbatively in derivatives.

For a conformal plasma, the ideal stress tensor is

$$
T^{\mu\nu}_{\rm ideal}
=
\epsilon u^\mu u^\nu+p\Delta^{\mu\nu}
=
p\,g_{(0)}^{\mu\nu}+d p\,u^\mu u^\nu .
$$

The first derivative correction is dissipative:

$$
T^{\mu\nu}_{(1)}=-\eta\sigma^{\mu\nu} .
$$

The minus sign encodes entropy production. Gradients in velocity are damped rather than amplified.

## The black brane as an equilibrium fluid element

Use ingoing Eddington–Finkelstein coordinates for the planar AdS$_{d+1}$ black brane, and set $L=1$ for compactness. A convenient boosted form is

$$
ds^2
=
-2u_\mu dx^\mu dr
-r^2 f(br)u_\mu u_\nu dx^\mu dx^\nu
+r^2 P_{\mu\nu}dx^\mu dx^\nu,
$$

where

$$
f(br)=1-\frac{1}{(br)^d},
\qquad
P_{\mu\nu}=\eta_{\mu\nu}+u_\mu u_\nu,
\qquad
u^\mu u_\mu=-1.
$$

The parameter $b$ is related to the temperature by

$$
T=\frac{d}{4\pi b}.
$$

For constant $u^\mu$ and constant $b$, this is just a uniform black brane viewed in a boosted frame. Its boundary stress tensor is the ideal conformal-fluid stress tensor,

$$
T^{\mu\nu}_{\rm ideal}
=
p\eta^{\mu\nu}+d p\,u^\mu u^\nu,
$$

with

$$
p=\frac{1}{16\pi G_{d+1}}\frac{1}{b^d},
\qquad
\epsilon=(d-1)p,
\qquad
s=\frac{1}{4G_{d+1}}\frac{1}{b^{d-1}} .
$$

These formulae assume the flat-boundary, planar-brane normalization with $L=1$. Restoring $L$ only changes the overall power of $L$ multiplying extensive quantities.

The important point is structural: the parameters of a black brane are exactly the parameters of a local equilibrium fluid element.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Hydrodynamics from gravity](/figures/course/hydrodynamics-from-gravity.svg)

<figcaption>

The fluid/gravity idea. A uniform boosted black brane is dual to a global thermal equilibrium state. Promoting the temperature and velocity to slowly varying fields $T(x)$ and $u^\mu(x)$ produces a derivative expansion. The radial constraint equations impose $\nabla_\mu T^{\mu\nu}=0$, while regularity of the future horizon fixes the transport coefficients.

</figcaption>
</figure>

## The fluid/gravity move

The key move is to promote the constant parameters of the boosted black brane to slowly varying functions:

$$
b\to b(x),
\qquad
u^\mu\to u^\mu(x).
$$

The metric obtained by this substitution is not an exact solution. Derivatives of $b(x)$ and $u^\mu(x)$ generate errors in Einstein's equations. The remedy is to solve order by order:

$$
g_{MN}
=
g^{(0)}_{MN}[b(x),u(x)]
+
g^{(1)}_{MN}
+
g^{(2)}_{MN}
+
\cdots,
$$

where $g^{(n)}_{MN}$ contains $n$ boundary derivatives.

The bulk equations are

$$
E_{MN}
\equiv
R_{MN}-\frac12 Rg_{MN}+\Lambda g_{MN}=0.
$$

At each derivative order they split into two types of equations:

| Bulk equation type | Boundary meaning |
|---|---|
| radial constraint equations | hydrodynamic conservation laws |
| radial dynamical equations | determine metric corrections and transport data |

The constraint equations are the important conceptual bridge:

$$
\boxed{
E_{r\mu}=0
\quad\Longleftrightarrow\quad
\nabla_\nu T^\nu_{\ \mu}=0
}
$$

order by order in the derivative expansion.

This equivalence is not mysterious. In the Hamiltonian view of gravity, radial constraints generate boundary diffeomorphism Ward identities. Holographic renormalization translates those constraints into conservation of the boundary stress tensor.

## What regularity fixes

Conservation alone does not determine transport coefficients. It only says that the stress tensor must obey

$$
\nabla_\mu T^{\mu\nu}=0.
$$

The numerical values of $\eta$, relaxation times, and higher-order transport coefficients come from solving the radial equations with physical boundary conditions.

The standard choices are:

1. the boundary metric is fixed;
2. the solution is asymptotically AdS;
3. the future horizon is regular in ingoing coordinates;
4. the hydrodynamic frame is fixed, commonly the Landau frame.

The Landau frame condition is

$$
u_\mu T^{\mu\nu}_{\rm dissipative}=0 .
$$

For two-derivative Einstein gravity duals of conformal plasmas, the first-order answer is

$$
T^{\mu\nu}
=
\epsilon u^\mu u^\nu
+
p\Delta^{\mu\nu}
-
\eta\sigma^{\mu\nu}
+
O(\partial^2),
$$

with

$$
\boxed{
\frac{\eta}{s}=\frac{1}{4\pi}
}
$$

in units $\hbar=k_B=1$.

The next page derives this ratio directly from the transverse graviton calculation. Here the point is broader: gravitational regularity chooses the dissipative branch of the effective boundary dynamics.

## Linearized hydrodynamic modes

The quasinormal-mode page explained that poles of retarded Green functions encode relaxation. Hydrodynamic poles are the special quasinormal modes whose frequencies approach zero as $|\mathbf{k}|\to0$.

### Shear diffusion

Consider a small transverse velocity perturbation in flat space:

$$
u^y(t,x)=\delta u_y(t,x),
\qquad
\text{all other perturbations zero at linear order.}
$$

The relevant components of the stress tensor are

$$
T^{ty}=(\epsilon+p)\delta u_y,
\qquad
T^{xy}=-\eta\partial_x\delta u_y .
$$

Conservation $\partial_\mu T^{\mu y}=0$ gives

$$
(\epsilon+p)\partial_t\delta u_y
-
\eta\partial_x^2\delta u_y=0 .
$$

For a Fourier mode $e^{-i\omega t+ikx}$,

$$
\boxed{
\omega_{\rm shear}(k)
=
-iD_\eta k^2+
O(k^4),
\qquad
D_\eta=\frac{\eta}{\epsilon+p}.
}
$$

At zero chemical potential, thermodynamics gives

$$
\epsilon+p=sT,
$$

so an Einstein-gravity plasma has

$$
D_\eta=\frac{1}{4\pi T}.
$$

This hydrodynamic pole is visible as the lowest shear-channel quasinormal mode of the black brane.

### Sound

Sound couples energy density and longitudinal momentum. For a conformal fluid,

$$
\epsilon=(d-1)p,
\qquad
c_s^2=\frac{\partial p}{\partial\epsilon}=\frac{1}{d-1}.
$$

The sound dispersion relation is

$$
\boxed{
\omega_{\rm sound}(k)
=
\pm c_s k
-
i\frac{d-2}{d-1}\frac{\eta}{\epsilon+p}k^2
+
O(k^3)
}
$$

for a conformal fluid with $\zeta=0$.

Using $\eta/s=1/(4\pi)$ gives

$$
\omega_{\rm sound}(k)
=
\pm \frac{k}{\sqrt{d-1}}
-
i\frac{d-2}{d-1}\frac{k^2}{4\pi T}
+
O(k^3).
$$

For $d=4$, this becomes

$$
\omega_{\rm sound}(k)
=
\pm \frac{k}{\sqrt3}
-
i\frac{k^2}{6\pi T}
+
O(k^3),
$$

which is the familiar strongly coupled $\mathcal N=4$ SYM result.

## How this appears in gravitational perturbations

Black-brane perturbations organize into channels according to their transformation under rotations transverse to the momentum $\mathbf{k}$.

For momentum along $x$, the usual channels are:

| Channel | Boundary variables | Hydrodynamic pole |
|---|---|---|
| shear | $T^{ty}$, $T^{xy}$ | $\omega=-iD_\eta k^2+\\cdots$ |
| sound | $T^{tt}$, $T^{tx}$, $T^{xx}$ | $\omega=\pm c_s k-i\Gamma k^2+\cdots$ |
| scalar/tensor | transverse traceless stress | no conserved hydrodynamic pole |

In the gravity calculation, each channel is represented by a gauge-invariant combination of metric perturbations. Solving the corresponding radial equation with infalling horizon behavior and source-free boundary behavior gives quasinormal frequencies.

Hydrodynamics predicts the small-$k$ form of the lowest poles. The bulk equations compute the coefficients.

This is a powerful consistency check: the same coefficients can be extracted either from Kubo formulae or from the dispersion of hydrodynamic quasinormal modes.

## The horizon as the place where dissipation enters

A classical black brane is a dissipative object because its future horizon absorbs perturbations. In the boundary theory, this absorption becomes entropy production and relaxation.

The retarded prescription imposes infalling behavior at the future horizon. That condition is what selects the causal, dissipative Green function rather than the advanced or time-symmetric one.

For hydrodynamics, this means:

$$
\text{regular future horizon}
\quad\Longrightarrow\quad
\text{positive dissipative transport}
$$

under the usual stability and unitarity assumptions.

This is also why the membrane paradigm is so effective. In the low-frequency limit, many transport coefficients can be expressed in terms of horizon data, even though the full correlator depends on radial evolution from the horizon to the boundary.

## What is universal and what is not

The hydrodynamic form of the stress tensor is universal. The values of transport coefficients are theory-dependent.

For conformal plasmas with two-derivative Einstein gravity duals, the first-order coefficients are highly constrained:

$$
\zeta=0,
\qquad
\frac{\eta}{s}=\frac{1}{4\pi}.
$$

But this does not mean all holographic theories have identical hydrodynamics. Transport can change when one includes:

- higher-derivative bulk terms;
- finite-coupling stringy corrections;
- finite-$N$ quantum corrections;
- chemical potentials and charge diffusion;
- broken translations and momentum relaxation;
- anisotropy;
- nonconformal RG flows.

The robust lesson is the method: hydrodynamic effective theory emerges from the near-equilibrium, long-wavelength sector of black-brane dynamics.

## Dictionary checkpoint

| Boundary hydrodynamics | Bulk gravity |
|---|---|
| local temperature $T(x)$ | slowly varying horizon radius |
| fluid velocity $u^\mu(x)$ | locally boosted black brane |
| $\nabla_\mu T^{\mu\nu}=0$ | radial constraint equations |
| transport coefficients | regular radial solutions with horizon boundary conditions |
| shear diffusion pole | shear-channel black-brane quasinormal mode |
| sound pole | sound-channel black-brane quasinormal mode |
| entropy current | horizon area current |

A useful one-line summary is:

$$
\boxed{
\text{Einstein equations near a regular black-brane horizon}
\quad\Rightarrow\quad
\text{boundary relativistic hydrodynamics}
}
$$

## Common confusions

### “Hydrodynamics assumes quasiparticles.”

No. Hydrodynamics assumes local equilibrium, conservation laws, and a derivative expansion. It does not require quasiparticles. This is why it is ideal for strongly coupled holographic plasmas.

### “The fluid lives on the horizon.”

The boundary fluid lives in the boundary QFT. The horizon provides a geometric way of computing transport and entropy. The membrane paradigm is an efficient gravitational description, not a replacement for the boundary theory.

### “Hydrodynamics is linear response.”

Linearized hydrodynamics is only the small-amplitude limit. The full hydrodynamic equations can be nonlinear in the velocity and temperature fields while still being perturbative in derivatives.

### “All quasinormal modes are hydrodynamic.”

No. Hydrodynamic quasinormal modes are the special modes whose frequencies vanish as $|\mathbf{k}|\to0$. Most quasinormal modes remain at frequencies of order $T$ and describe nonhydrodynamic relaxation.

### “The value $\eta/s=1/(4\pi)$ follows from conformal symmetry alone.”

No. Conformal symmetry implies $\zeta=0$ and fixes the equation of state up to an overall constant. The ratio $\eta/s=1/(4\pi)$ follows from two-derivative Einstein gravity and horizon regularity. Other conformal theories can have different values.

## Exercises

### Exercise 1: Derive the shear diffusion pole

Starting from

$$
T^{ty}=(\epsilon+p)\delta u_y,
\qquad
T^{xy}=-\eta\partial_x\delta u_y,
$$

use $\partial_\mu T^{\mu y}=0$ to derive the shear dispersion relation.

<details>
<summary><strong>Solution</strong></summary>

The conservation equation is

$$
\partial_t T^{ty}+\partial_x T^{xy}=0.
$$

Substituting the linearized stress tensor gives

$$
(\epsilon+p)\partial_t\delta u_y
-
\eta\partial_x^2\delta u_y=0.
$$

For $\delta u_y\sim e^{-i\omega t+ikx}$,

$$
-i\omega(\epsilon+p)+\eta k^2=0.
$$

Therefore

$$
\omega=-i\frac{\eta}{\epsilon+p}k^2.
$$

The diffusion constant is

$$
D_\eta=\frac{\eta}{\epsilon+p}.
$$

</details>

### Exercise 2: Sound speed in a conformal fluid

Use the tracelessness condition $T^\mu_{\ \mu}=0$ to show that a conformal fluid in $d$ spacetime dimensions has

$$
c_s^2=\frac{1}{d-1}.
$$

<details>
<summary><strong>Solution</strong></summary>

For an ideal fluid in $d$ spacetime dimensions,

$$
T^\mu_{\ \mu}=-\epsilon+(d-1)p.
$$

Conformal invariance requires $T^\mu_{\ \mu}=0$, so

$$
\epsilon=(d-1)p.
$$

The sound speed is

$$
c_s^2=\frac{\partial p}{\partial\epsilon}.
$$

Since $p=\epsilon/(d-1)$,

$$
c_s^2=\frac{1}{d-1}.
$$

</details>

### Exercise 3: Relate shear diffusion to the temperature

Assume zero chemical potential and an Einstein-gravity dual with

$$
\frac{\eta}{s}=\frac{1}{4\pi}.
$$

Show that

$$
D_\eta=\frac{1}{4\pi T}.
$$

<details>
<summary><strong>Solution</strong></summary>

At zero chemical potential, the thermodynamic identity is

$$
\epsilon+p=sT.
$$

The shear diffusion constant is

$$
D_\eta=\frac{\eta}{\epsilon+p}.
$$

Substituting $\epsilon+p=sT$ gives

$$
D_\eta=\frac{\eta}{sT}
=
\frac{1}{T}\frac{\eta}{s}.
$$

Using $\eta/s=1/(4\pi)$,

$$
D_\eta=\frac{1}{4\pi T}.
$$

</details>

### Exercise 4: Why are radial constraints hydrodynamic equations?

Explain in words why $E_{r\mu}=0$ in the bulk becomes $\nabla_\nu T^\nu_{\ \mu}=0$ on the boundary.

<details>
<summary><strong>Solution</strong></summary>

In a radial Hamiltonian decomposition of gravity, equations with one radial index are constraints rather than independent radial evolution equations. They generate boundary diffeomorphisms. In holographic renormalization, invariance of the renormalized on-shell action under boundary diffeomorphisms gives the stress-tensor Ward identity

$$
\nabla_\nu T^\nu_{\ \mu}=0
$$

when no external sources exchange momentum with the fluid. Therefore the bulk radial constraints are the gravitational form of boundary stress-tensor conservation. In the fluid/gravity expansion, this conservation law becomes the relativistic hydrodynamic equation for $T(x)$ and $u^\mu(x)$.

</details>

## Further reading

- G. Policastro, D. T. Son, and A. O. Starinets, [From Black Holes to Hydrodynamics](https://arxiv.org/abs/hep-th/0205052).
- D. T. Son and A. O. Starinets, [Minkowski-Space Correlators in AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0205051).
- S. Bhattacharyya, V. E. Hubeny, S. Minwalla, and M. Rangamani, [Nonlinear Fluid Dynamics from Gravity](https://arxiv.org/abs/0712.2456).
- M. Rangamani, [Gravity and Hydrodynamics: Lectures on the Fluid-Gravity Correspondence](https://arxiv.org/abs/0905.4352).
- N. Iqbal and H. Liu, [Universality of the Hydrodynamic Limit in AdS/CFT and the Membrane Paradigm](https://arxiv.org/abs/0809.3808).
