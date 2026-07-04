---
title: "Thermal States and Density Matrices"
description: "A field-theory introduction to thermal density matrices, Euclidean thermal circles, KMS relations, Matsubara modes, chemical potentials, and the finite-temperature data used in AdS/CFT."
sidebar:
  order: 70
---

The previous pages built the zero-temperature field-theory spine of AdS/CFT: sources and generating functionals, conformal symmetry, radial quantization, large-$N$ counting, single-trace operators, and the canonical example $\mathcal N=4$ super-Yang–Mills theory. We now add one more piece of field-theory technology before entering the geometry side: **thermal states**.

This is not a detour. Finite temperature is one of the places where holography becomes immediately physical. A thermal CFT state is described in the bulk not by empty AdS, but by an AdS black hole or black brane. Entropy becomes horizon area, relaxation becomes quasinormal decay, and transport coefficients become horizon response coefficients.

But before black holes appear, the boundary statement is ordinary quantum statistical mechanics:

$$
\rho_\beta
=
\frac{e^{-\beta H}}{Z(\beta)},
\qquad
Z(\beta)=\operatorname{Tr} e^{-\beta H},
\qquad
\beta=\frac{1}{T}.
$$

Throughout this page we use the course conventions $k_B=\hbar=c=1$, so temperature has dimensions of energy and $\beta$ has dimensions of inverse energy.

The thermal expectation value of an operator is

$$
\langle \mathcal O\rangle_\beta
=
\operatorname{Tr}\!\left(\rho_\beta\mathcal O\right).
$$

The whole page is about taking these familiar formulas seriously in a relativistic QFT, and about identifying which pieces will later become geometric in AdS.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Thermal field theory data organized by density matrices, Euclidean circles, correlators, and holographic saddles](/figures/course/thermal-states-density-matrices.svg)

<figcaption>

A thermal QFT state can be described by a density matrix $\rho_\beta$, by a Euclidean path integral on $S^1_\beta\times\Sigma$, or by real-time thermal correlators. In holography, the same data are encoded in asymptotically AdS saddles: thermal AdS, black holes, or black branes, depending on the ensemble and regime.

</figcaption>
</figure>

## Why this matters

Many of the most important applications of AdS/CFT involve states rather than just theories.

At zero temperature, the cleanest object is the vacuum generating functional. At finite temperature, the central object is instead the partition function of a statistical ensemble and the correlators evaluated inside that ensemble. The source language remains, but now the expectation value means

$$
\langle \cdots \rangle_\beta
=
\operatorname{Tr}\!\left(\rho_\beta\cdots\right),
$$

not a vacuum expectation value.

This distinction matters because a thermal state has features that the vacuum does not:

- it chooses a preferred rest frame;
- it has nonzero energy density and entropy density;
- it has dissipative real-time response;
- it has characteristic correlation lengths and relaxation times;
- it can undergo phase transitions as the temperature or chemical potentials are varied.

In holography, these features are not added by hand. They are encoded in the bulk saddle. A horizon in the bulk is the geometric avatar of thermal entropy and dissipation in the boundary theory.

The purpose of this page is to make the boundary side precise enough that later statements such as

$$
T_{\mathrm{CFT}}=T_{\mathrm{Hawking}},
\qquad
S_{\mathrm{CFT}}=\frac{\mathrm{Area}_{\mathrm{horizon}}}{4G_N}
$$

feel natural rather than miraculous.

## Density matrices: states beyond pure states

A pure state is specified by a vector $|\psi\rangle$ in Hilbert space, up to phase. The expectation value of an operator is

$$
\langle \mathcal O\rangle_\psi
=
\langle \psi|\mathcal O|\psi\rangle.
$$

A mixed state is specified by a density matrix $\rho$ satisfying

$$
\rho^\dagger=\rho,
\qquad
\rho\ge 0,
\qquad
\operatorname{Tr}\rho=1.
$$

Expectation values are

$$
\langle \mathcal O\rangle_\rho
=
\operatorname{Tr}(\rho\mathcal O).
$$

A pure state is the special case

$$
\rho=|\psi\rangle\langle\psi|,
\qquad
\rho^2=\rho.
$$

A thermal state is usually mixed:

$$
\rho_\beta
=
\frac{e^{-\beta H}}{\operatorname{Tr}e^{-\beta H}}.
$$

If the Hamiltonian eigenstates are

$$
H|n\rangle=E_n|n\rangle,
$$

then

$$
\rho_\beta
=
\frac{1}{Z(\beta)}
\sum_n e^{-\beta E_n}|n\rangle\langle n|.
$$

So the thermal state weights energy eigenstates by Boltzmann factors. Low-energy states dominate at low temperature. Many high-energy states contribute at high temperature.

This last sentence is the doorway to black holes. In a holographic theory, sufficiently high-energy thermal states can be dominated by bulk black-hole geometries.

## The canonical ensemble

The canonical partition function is

$$
Z(\beta)=\operatorname{Tr} e^{-\beta H}.
$$

The free energy is

$$
F(T)=-T\log Z(\beta),
$$

or equivalently

$$
\log Z(\beta)=-\beta F.
$$

The thermal energy is

$$
E
=
\langle H\rangle_\beta
=
-\frac{\partial}{\partial \beta}\log Z(\beta).
$$

The entropy is

$$
S
=-\operatorname{Tr}(\rho_\beta\log\rho_\beta).
$$

For the canonical ensemble this becomes

$$
S
=
\beta(E-F)
=
\left(1-\beta\frac{\partial}{\partial\beta}\right)\log Z.
$$

The heat capacity is

$$
C
=\frac{\partial E}{\partial T}.
$$

A stable canonical ensemble has positive heat capacity. This point becomes important for AdS black holes: some black holes are stable in a canonical ensemble, while others are not.

## The grand canonical ensemble

If the QFT has a conserved charge $Q$, then one can introduce a chemical potential $\mu$ and use the grand canonical density matrix

$$
\rho_{\beta,\mu}
=
\frac{e^{-\beta(H-\mu Q)}}{Z(\beta,\mu)},
\qquad
Z(\beta,\mu)
=
\operatorname{Tr} e^{-\beta(H-\mu Q)}.
$$

The grand potential is

$$
\Omega(T,\mu)
=-T\log Z(\beta,\mu).
$$

With this convention,

$$
\langle Q\rangle
=
\frac{1}{\beta}\frac{\partial}{\partial\mu}\log Z(\beta,\mu)
=
-\frac{\partial \Omega}{\partial\mu}.
$$

In field-theory language, $\mu$ is a source for the charge density $J^t$. If $J^\mu$ is a conserved current, then the source is a background gauge field $A_\mu^{(0)}$, and a chemical potential is essentially the boundary value of the temporal component:

$$
A_t^{(0)}=\mu.
$$

There are Euclidean factors of $i$ that depend on Wick-rotation conventions, so the safest statement is: a chemical potential is a background temporal gauge-field source for a conserved charge.

This is exactly the statement that later becomes holographic:

$$
\text{boundary chemical potential}
\quad
\longleftrightarrow
\quad
\text{boundary value of a bulk gauge field}.
$$

Finite density holography begins here, not in the bulk.

## Thermal QFT as a Euclidean path integral

The trace in

$$
Z(\beta)=\operatorname{Tr} e^{-\beta H}
$$

has a path-integral representation. In ordinary quantum mechanics, the operator $e^{-\beta H}$ evolves the system by Euclidean time $\beta$. Taking the trace identifies the final state with the initial state. Therefore Euclidean time is periodic:

$$
\tau\sim \tau+\beta.
$$

For a QFT on a spatial manifold $\Sigma$, the thermal partition function is a Euclidean path integral on

$$
S^1_\beta\times \Sigma.
$$

Schematically,

$$
Z(\beta)
=
\int_{\text{thermal b.c.}} \mathcal D\Phi\; e^{-S_E[\Phi]}.
$$

The boundary conditions are

$$
\Phi_B(\tau+\beta,\mathbf x)=\Phi_B(\tau,\mathbf x)
$$

for bosonic fields, and

$$
\Phi_F(\tau+\beta,\mathbf x)=-\Phi_F(\tau,
\mathbf x)
$$

for fermionic fields.

The minus sign for fermions is not optional. It is the path-integral form of the trace over fermionic states. It is also why a thermal state of a supersymmetric theory usually breaks supersymmetry: bosons and fermions obey different thermal boundary conditions around the Euclidean time circle.

For a CFT, this Euclidean viewpoint is especially useful because a finite temperature is equivalent to putting the theory on a circle in imaginary time. The geometry

$$
S^1_\beta\times \mathbb R^{d-1}
$$

sets the thermal scale $T=1/\beta$.

## Thermal states of a CFT

A conformal field theory has no intrinsic mass scale. A thermal state introduces one:

$$
T.
$$

This does not mean the theory has stopped being conformal. It means the **state** is not invariant under the full conformal group. The density matrix

$$
\rho_\beta=e^{-\beta H}/Z
$$

selects a rest frame and a length scale $\beta$.

For a homogeneous CFT on flat spacetime, dimensional analysis strongly constrains the thermodynamics. Let the boundary spacetime dimension be $d$, so the spatial volume is $V_{d-1}$. The pressure has dimension $d$, so in an infinite-volume thermal state

$$
p(T)=a_T T^d,
$$

where $a_T$ is a dimensionless number measuring the effective number of degrees of freedom. The free-energy density is

$$
f(T)=\frac{F}{V_{d-1}}=-p(T)=-a_T T^d.
$$

The entropy density is

$$
s(T)=-\frac{\partial f}{\partial T}
=d\,a_T T^{d-1}.
$$

The energy density is

$$
\epsilon(T)=f+Ts=(d-1)a_TT^d.
$$

Thus

$$
\epsilon=(d-1)p.
$$

This is the thermodynamic version of stress-tensor tracelessness:

$$
\langle T^\mu_{\ \mu}\rangle_eta
=-\epsilon+(d-1)p=0,
$$

up to possible anomalies, background curvature effects, explicit deformations, or finite-size effects.

For holographic CFTs with classical gravity duals, $a_T$ is typically proportional to the large number of degrees of freedom. In the canonical four-dimensional example,

$$
a_T\sim N^2.
$$

That scaling foreshadows why black-brane entropy densities scale like $1/G_N$ in the bulk.

## CFT on the cylinder

The canonical Hilbert-space definition of the thermal partition function depends on the spatial manifold. In radial quantization, a CFT on flat space is related to a CFT on the cylinder

$$
\mathbb R_\tau\times S^{d-1}.
$$

A thermal state on the cylinder is described by

$$
Z(\beta,R)
=
\operatorname{Tr}_{S^{d-1}} e^{-\beta H_{\mathrm{cyl}}},
$$

where $R$ is the radius of the sphere. The dimensionless parameter is

$$
\frac{\beta}{R}.
$$

This distinction between the plane and the cylinder matters in global AdS. The boundary of global AdS is

$$
\mathbb R\times S^{d-1},
$$

so thermal states of the CFT on the sphere are naturally compared with thermal geometries in global AdS. The Hawking–Page transition is the bulk version of a finite-volume thermal phase transition on this cylinder.

For black branes, by contrast, the boundary spatial geometry is usually

$$
\mathbb R^{d-1},
$$

and one studies thermodynamic densities rather than total thermodynamic quantities.

## Matsubara frequencies

Because Euclidean time is a circle of circumference $\beta$, fields can be expanded in Fourier modes around that circle.

For a bosonic operator or source,

$$
\phi(\tau,\mathbf x)
=
T\sum_{n\in\mathbb Z}e^{-i\omega_n\tau}\phi_n(\mathbf x),
\qquad
\omega_n=2\pi nT.
$$

For a fermionic field,

$$
\psi(\tau,\mathbf x)
=
T\sum_{n\in\mathbb Z}e^{-i\omega_n\tau}\psi_n(\mathbf x),
\qquad
\omega_n=(2n+1)\pi T.
$$

These are the Matsubara frequencies. They are not arbitrary. They are forced by the periodic or antiperiodic thermal boundary conditions.

Euclidean thermal correlators are therefore naturally computed at discrete imaginary frequencies:

$$
G_E(i\omega_n,\mathbf k).
$$

Real-time physics requires analytic continuation to continuous real frequency. This step is powerful but subtle. In particular, the retarded correlator is not obtained by merely replacing $i\omega_n$ by $\omega$ in a careless way. One must specify the correct analytic continuation and boundary conditions.

This subtlety is exactly why real-time holography has its own prescription.

## The KMS condition

Thermal equilibrium imposes a powerful relation on real-time correlation functions: the Kubo–Martin–Schwinger condition, usually called the KMS condition.

Let

$$
G^>_{AB}(t)
=
\operatorname{Tr}\!\left(\rho_\beta A(t)B(0)\right),
$$

and

$$
G^<_{AB}(t)
=
\operatorname{Tr}\!\left(\rho_\beta B(0)A(t)\right).
$$

For bosonic operators, the KMS condition is

$$
G^>_{AB}(t-i\beta)=G^<_{AB}(t).
$$

This follows from two facts: thermal time evolution is generated by $H$, and the trace is cyclic. The relation says that thermal correlators are analytic in a strip of complex time and relate shifted operator orderings.

In frequency space, for bosonic operators, KMS implies the detailed-balance relation

$$
G^>_{AB}(\omega)
=e^{\beta\omega}G^<_{AB}(\omega),
$$

with convention-dependent signs and transpositions when $A$ and $B$ are different operators or carry fermionic parity.

The Euclidean periodicity of bosonic correlators is a close cousin of KMS. In imaginary time, bosonic thermal correlators are periodic with period $\beta$, while fermionic correlators are antiperiodic.

The KMS condition is one of the cleanest ways to say what thermal equilibrium means in quantum field theory.

## Real-time response

Equilibrium thermodynamics is not enough for holography. Many of the most useful observables are dynamical: conductivities, viscosities, diffusion constants, relaxation rates, and spectral functions.

Suppose a source $J(t,\mathbf x)$ couples to an operator $\mathcal O$ by perturbing the Hamiltonian as

$$
\delta H(t)=-\int d^{d-1}x\,J(t,\mathbf x)\mathcal O(t,\mathbf x).
$$

To first order in the source, the response is controlled by the retarded Green's function:

$$
\delta\langle \mathcal O(t,\mathbf x)\rangle
=
\int dt' d^{d-1}x'\,
G_R(t-t',\mathbf x-\mathbf x')J(t',\mathbf x')
$$

up to sign conventions tied to the definition of the source coupling.

For a bosonic operator,

$$
G_R(t,\mathbf x)
=
-i\theta(t)\langle[\mathcal O(t,\mathbf x),\mathcal O(0,\mathbf 0)]\rangle_\beta.
$$

The step function $\theta(t)$ enforces causality. The retarded correlator answers the question: how does the system respond after it is perturbed?

The spectral density is commonly defined by

$$
\rho_{\mathcal O}(\omega,\mathbf k)
=-2\operatorname{Im}G_R(\omega,\mathbf k),
$$

though some communities use the opposite sign. The spectral density measures the available excitations created by $\mathcal O$ at frequency $\omega$ and momentum $\mathbf k$.

Transport coefficients are low-frequency, long-wavelength limits of retarded correlators. For example, shear viscosity is extracted from a stress-tensor correlator of the schematic form

$$
\eta
=
-\lim_{\omega\to 0}\frac{1}{\omega}
\operatorname{Im}G_R^{T_{xy}T_{xy}}(\omega,\mathbf k=0),
$$

with the sign depending on the Fourier convention.

This is why black-brane perturbations matter. In holography, retarded correlators are computed by solving classical wave equations in a black-hole background with infalling boundary conditions at the horizon.

## Euclidean versus Lorentzian thermal correlators

It is useful to separate three related but distinct objects.

First, the Euclidean thermal correlator:

$$
G_E(\tau,\mathbf x)
=
\langle \mathcal T_\tau\mathcal O(\tau,\mathbf x)\mathcal O(0,\mathbf 0)\rangle_\beta,
$$

where $\mathcal T_\tau$ denotes Euclidean time ordering.

Second, the Wightman functions:

$$
G^>(t,\mathbf x)
=
\langle \mathcal O(t,\mathbf x)\mathcal O(0,\mathbf 0)\rangle_\beta,
$$

and

$$
G^<(t,\mathbf x)
=
\langle \mathcal O(0,\mathbf 0)\mathcal O(t,\mathbf x)\rangle_\beta.
$$

Third, the retarded function:

$$
G_R(t,\mathbf x)
=-i\theta(t)\left(G^>(t,\mathbf x)-G^<(t,\mathbf x)\right)
$$

for bosonic operators.

The Euclidean correlator is often easier to compute because the path integral has weight $e^{-S_E}$. The retarded correlator is often more physical because it governs causal response. Analytic continuation relates them only after their analytic structure has been specified.

In holography, this difference appears geometrically. Euclidean black holes require smoothness at the origin of the Euclidean cigar. Lorentzian retarded correlators require infalling behavior at the horizon. These are related, but they are not the same sentence.

## Thermal generating functionals

The source formalism from the previous pages extends directly to finite temperature. For a source $J$ coupled to an operator $\mathcal O$, define

$$
Z_\beta[J]
=
\operatorname{Tr}\,\mathcal T
\exp\!\left[-\beta H+\int J\mathcal O\right],
$$

schematically. In Euclidean field theory, this becomes

$$
Z_\beta[J]
=
\int_{S^1_\beta\times\Sigma}\mathcal D\Phi\,
\exp\!\left[-S_E[\Phi]+\int_{S^1_\beta\times\Sigma}J\mathcal O\right],
$$

with the appropriate thermal boundary conditions.

The connected generating functional is

$$
W_\beta[J]=\log Z_\beta[J].
$$

Thermal connected correlators are obtained by functional differentiation:

$$
\langle \mathcal O(x_1)\cdots \mathcal O(x_n)\rangle_{\beta,c}
=
\left.
\frac{\delta^n W_\beta[J]}
{\delta J(x_1)\cdots\delta J(x_n)}
\right|_{J=0}.
$$

This is the finite-temperature version of the source machinery used in the GKP/Witten prescription.

At large $N$, one often studies the thermal free energy through

$$
W_\beta[0]=\log Z(\beta)=-\beta F.
$$

In a holographic theory, this is matched to the renormalized Euclidean on-shell action of the dominant bulk saddle:

$$
\log Z_{\mathrm{CFT}}(\beta)
\approx
-S_{E,\text{ren,on-shell}}.
$$

This formula is the thermal version of the classical gravity approximation to the holographic dictionary.

## Thermal one-point functions

A thermal state can have nonzero one-point functions even when the vacuum expectation value vanishes. The most universal example is the stress tensor.

For a homogeneous isotropic thermal state on flat spacetime,

$$
\langle T^{\mu}_{\ \nu}\rangle_\beta
=
\operatorname{diag}(-\epsilon,p,p,\ldots,p),
$$

in mostly-plus Lorentzian signature.

For a CFT in flat space,

$$
-\epsilon+(d-1)p=0,
$$

so

$$
\epsilon=(d-1)p.
$$

If a conserved charge density is present, then

$$
\langle J^t\rangle_{\beta,\mu}=\rho_Q,
$$

where $\rho_Q$ is the charge density. In the bulk, these thermal one-point functions are read from the asymptotic behavior of the metric and gauge field after holographic renormalization.

This gives the first glimpse of the finite-temperature dictionary:

$$
\langle T_{\mu\nu}\rangle_\beta
\quad
\longleftrightarrow
\quad
\text{asymptotic coefficients of a black-brane metric},
$$

and

$$
\langle J^t\rangle_{\beta,\mu}
\quad
\longleftrightarrow
\quad
\text{asymptotic electric flux of a bulk gauge field}.
$$

## Purifying the thermal state

Although $\rho_\beta$ is mixed, it can be represented as a pure state in a doubled Hilbert space. Choose energy eigenstates $|n\rangle$ and define

$$
|\mathrm{TFD}\rangle
=
\frac{1}{\sqrt{Z(\beta)}}
\sum_n e^{-\beta E_n/2}|n\rangle_L|n\rangle_R.
$$

This is the thermofield double state. Tracing out the left Hilbert space gives the thermal density matrix on the right:

$$
\operatorname{Tr}_L |\mathrm{TFD}\rangle\langle \mathrm{TFD}|
=
\rho_{\beta,R}.
$$

In holography, the thermofield double state is related to the eternal two-sided AdS black hole. That is not needed for the calculations on this page, but it is a useful warning: thermal physics, entanglement, and black-hole geometry are deeply entangled subjects.

## Holographic preview

Here is the finite-temperature dictionary in its most elementary form.

A CFT thermal partition function on

$$
S^1_\beta\times \Sigma
$$

is computed holographically by a gravitational path integral over asymptotically AdS Euclidean geometries whose conformal boundary is

$$
S^1_\beta\times \Sigma.
$$

Schematically,

$$
Z_{\mathrm{CFT}}[S^1_\beta\times\Sigma]
=
Z_{\mathrm{grav}}[\partial M=S^1_\beta\times\Sigma].
$$

In the classical limit,

$$
Z_{\mathrm{grav}}
\approx
\sum_{\text{saddles}} e^{-S_{E,\mathrm{ren}}[g_\ast]}.
$$

The dominant saddle is the one with smallest renormalized Euclidean action. Depending on the spatial geometry and temperature, it may be thermal AdS, an AdS black hole, or a planar black brane.

For a black brane, the boundary theory is usually a thermal CFT on flat space. The horizon temperature is the CFT temperature:

$$
T_{\mathrm{CFT}}=T_{\mathrm{Hawking}}.
$$

The entropy density is horizon area per unit boundary volume:

$$
s=\frac{1}{4G_N}\frac{\mathrm{Area}_{\mathrm{horizon}}}{V_{d-1}}.
$$

Real-time response requires Lorentzian black-brane perturbations. The boundary condition at the horizon is infalling, reflecting causal absorption by the black hole. The resulting quasinormal mode spectrum gives poles of retarded thermal Green's functions.

All of this begins with the humble density matrix.

## Dictionary checkpoint

| Boundary thermal QFT | Bulk holographic description |
|---|---|
| inverse temperature $\beta$ | length of Euclidean boundary time circle |
| thermal partition function $Z(\beta)$ | gravitational path integral with boundary $S^1_\beta\times\Sigma$ |
| free energy $F=-T\log Z$ | renormalized Euclidean on-shell action |
| thermal entropy $S$ | horizon area in black-hole saddle |
| stress-tensor one-point function $\langle T_{\mu\nu}\rangle_\beta$ | asymptotic metric coefficients |
| chemical potential $\mu$ | boundary value of a bulk gauge field |
| charge density $\rho_Q$ | asymptotic electric flux |
| retarded correlator $G_R$ | Lorentzian bulk fluctuation with infalling horizon condition |
| relaxation pole | black-hole quasinormal mode |

The table is intentionally schematic. Each entry will be made precise later, with boundary conditions, counterterms, and ensemble choices included.

## Common confusions

### “A thermal state means the theory is no longer conformal.”

The theory can still be conformal. The state is not invariant under the full conformal group because $T$ introduces a scale and a rest frame. In flat space, stress-tensor tracelessness still implies

$$
\epsilon=(d-1)p
$$

for a homogeneous CFT thermal state, up to anomalies or deformations.

### “Euclidean periodicity is the same thing as real-time dynamics.”

No. Euclidean periodicity encodes equilibrium thermal data and Matsubara correlators. Real-time response is governed by retarded correlators. Analytic continuation connects them only after the analytic structure and boundary conditions are specified.

### “Finite temperature always means a black hole.”

Not quite. A finite-temperature boundary condition means the Euclidean boundary contains a thermal circle. The dominant bulk saddle may be thermal AdS, an AdS black hole, or another geometry. In planar high-temperature applications, black branes are often the relevant saddles, but this is not a logical necessity.

### “The thermal circle is physical time.”

The Euclidean thermal circle is imaginary time. It is a bookkeeping device with enormous power, but it is not the same as Lorentzian time evolution. Lorentzian finite-temperature physics uses the density matrix together with real-time evolution.

### “The chemical potential is the charge density.”

No. The chemical potential $\mu$ is a source conjugate to the charge $Q$. The charge density is an expectation value. In holography, this distinction becomes the difference between the leading boundary value of a bulk gauge field and the subleading response coefficient.

### “A mixed thermal state cannot be described by a pure state.”

It can be purified by enlarging the Hilbert space. The thermofield double state is the standard purification of a thermal density matrix. The original one-sided thermal state is recovered by tracing out the auxiliary copy.

## Exercises

### Exercise 1: Energy from the partition function

Starting from

$$
Z(\beta)=\operatorname{Tr}e^{-\beta H},
$$

show that

$$
E=\langle H\rangle_\beta=-\frac{\partial}{\partial\beta}\log Z.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate the partition function:

$$
\frac{\partial Z}{\partial\beta}
=
\operatorname{Tr}\left(-H e^{-\beta H}\right).
$$

Therefore

$$
\frac{\partial}{\partial\beta}\log Z
=
\frac{1}{Z}\frac{\partial Z}{\partial\beta}
=-\frac{1}{Z}\operatorname{Tr}\left(H e^{-\beta H}\right).
$$

Using

$$
\rho_\beta=\frac{e^{-\beta H}}{Z},
$$

we get

$$
\frac{\partial}{\partial\beta}\log Z
=-\operatorname{Tr}(\rho_\beta H)
=-\langle H\rangle_\beta.
$$

Thus

$$
E=-\frac{\partial}{\partial\beta}\log Z.
$$

</details>

### Exercise 2: Entropy in the canonical ensemble

Use

$$
\rho_\beta=\frac{e^{-\beta H}}{Z}
$$

to show that

$$
S=-\operatorname{Tr}(\rho_\beta\log\rho_\beta)=\beta(E-F).
$$

<details>
<summary><strong>Solution</strong></summary>

Take the logarithm of the density matrix:

$$
\log\rho_\beta=-\beta H-\log Z.
$$

Then

$$
S
=-\operatorname{Tr}(\rho_\beta\log\rho_\beta)
=\operatorname{Tr}\left[\rho_\beta(\beta H+\log Z)\right].
$$

Since $\operatorname{Tr}\rho_\beta=1$,

$$
S=\beta\langle H\rangle_\beta+\log Z.
$$

Using $E=\langle H\rangle_\beta$ and $F=-T\log Z=-\beta^{-1}\log Z$,

$$
\log Z=-\beta F.
$$

Therefore

$$
S=\beta E-\beta F=\beta(E-F).
$$

</details>

### Exercise 3: Thermodynamics of a flat-space CFT

Assume a homogeneous CFT in $d$ spacetime dimensions has pressure

$$
p(T)=a_TT^d.
$$

Show that

$$
s=d a_TT^{d-1},
\qquad
\epsilon=(d-1)a_TT^d,
\qquad
\epsilon=(d-1)p.
$$

<details>
<summary><strong>Solution</strong></summary>

The free-energy density is

$$
f=-p=-a_TT^d.
$$

The entropy density is

$$
s=-\frac{\partial f}{\partial T}
=d a_TT^{d-1}.
$$

The energy density is

$$
\epsilon=f+Ts.
$$

Substituting the expressions above gives

$$
\epsilon=-a_TT^d+T(d a_TT^{d-1})=(d-1)a_TT^d.
$$

Since $p=a_TT^d$,

$$
\epsilon=(d-1)p.
$$

This is the equation of state implied by tracelessness of the stress tensor in flat space.

</details>

### Exercise 4: Matsubara frequencies

Show that a periodic bosonic field on the Euclidean thermal circle has frequencies

$$
\omega_n=2\pi nT,
\qquad n\in\mathbb Z,
$$

while an antiperiodic fermionic field has frequencies

$$
\omega_n=(2n+1)\pi T.
$$

<details>
<summary><strong>Solution</strong></summary>

A mode around the Euclidean thermal circle has the form

$$
e^{-i\omega\tau}.
$$

For a bosonic field, periodicity requires

$$
e^{-i\omega(\tau+\beta)}=e^{-i\omega\tau}.
$$

Thus

$$
e^{-i\omega\beta}=1,
$$

so

$$
\omega\beta=2\pi n,
\qquad n\in\mathbb Z.
$$

Since $T=1/\beta$,

$$
\omega_n=2\pi nT.
$$

For a fermionic field, antiperiodicity requires

$$
e^{-i\omega(\tau+\beta)}=-e^{-i\omega\tau}.
$$

Thus

$$
e^{-i\omega\beta}=-1=e^{-i\pi(2n+1)},
$$

which gives

$$
\omega_n=(2n+1)\pi T.
$$

</details>

### Exercise 5: The KMS relation

For bosonic operators, use cyclicity of the trace to show that

$$
G^>_{AB}(t-i\beta)=G^<_{AB}(t).
$$

<details>
<summary><strong>Solution</strong></summary>

Start with

$$
G^>_{AB}(t-i\beta)
=\frac{1}{Z}\operatorname{Tr}\left(e^{-\beta H}A(t-i\beta)B(0)\right).
$$

Using

$$
A(t-i\beta)=e^{\beta H}A(t)e^{-\beta H},
$$

we find

$$
G^>_{AB}(t-i\beta)
=\frac{1}{Z}\operatorname{Tr}\left(e^{-\beta H}e^{\beta H}A(t)e^{-\beta H}B(0)\right).
$$

So

$$
G^>_{AB}(t-i\beta)
=\frac{1}{Z}\operatorname{Tr}\left(A(t)e^{-\beta H}B(0)\right).
$$

Cyclicity of the trace gives

$$
\operatorname{Tr}\left(A(t)e^{-\beta H}B(0)\right)
=\operatorname{Tr}\left(e^{-\beta H}B(0)A(t)\right).
$$

Therefore

$$
G^>_{AB}(t-i\beta)
=\frac{1}{Z}\operatorname{Tr}\left(e^{-\beta H}B(0)A(t)\right)
=G^<_{AB}(t).
$$

This is the KMS condition for bosonic operators.

</details>

### Exercise 6: Charge from the grand canonical partition function

Given

$$
Z(\beta,\mu)=\operatorname{Tr}e^{-\beta(H-\mu Q)},
$$

show that

$$
\langle Q\rangle
=\frac{1}{\beta}\frac{\partial}{\partial\mu}\log Z(\beta,\mu).
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate $Z$ with respect to $\mu$:

$$
\frac{\partial Z}{\partial\mu}
=\operatorname{Tr}\left(\beta Q e^{-\beta(H-\mu Q)}\right),
$$

assuming $Q$ commutes with $H$, as it does for a conserved charge. Therefore

$$
\frac{\partial}{\partial\mu}\log Z
=\frac{1}{Z}\frac{\partial Z}{\partial\mu}
=\beta\frac{1}{Z}\operatorname{Tr}\left(Q e^{-\beta(H-\mu Q)}\right).
$$

The density matrix is

$$
\rho_{\beta,\mu}=\frac{e^{-\beta(H-\mu Q)}}{Z},
$$

so

$$
\frac{\partial}{\partial\mu}\log Z
=\beta\operatorname{Tr}(\rho_{\beta,\mu}Q)
=\beta\langle Q\rangle.
$$

Hence

$$
\langle Q\rangle
=\frac{1}{\beta}\frac{\partial}{\partial\mu}\log Z.
$$

</details>

## Further reading

- M. Laine and A. Vuorinen, [Basics of Thermal Field Theory](https://arxiv.org/abs/1701.01554).
- J. I. Kapusta and C. Gale, *Finite-Temperature Field Theory: Principles and Applications*.
- M. Le Bellac, *Thermal Field Theory*.
- A. Das, *Finite Temperature Field Theory*.
- D. T. Son and A. O. Starinets, [Minkowski-Space Correlators in AdS/CFT Correspondence: Recipe and Applications](https://arxiv.org/abs/hep-th/0205051).
- E. Witten, [Anti-de Sitter Space, Thermal Phase Transition, and Confinement in Gauge Theories](https://arxiv.org/abs/hep-th/9803131).

## What comes next

This page completed the field-theory-side preparation. The next unit begins the bulk side with [AdS as a Spacetime](../../ads-geometry/ads-as-a-spacetime/). There we will define Anti-de Sitter space geometrically, study its boundary, and explain why its isometry group is the conformal group of the boundary theory.
