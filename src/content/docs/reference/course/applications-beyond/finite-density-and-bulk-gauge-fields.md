---
title: "Finite Density and Bulk Gauge Fields"
description: "How chemical potential, charge density, and conserved currents are encoded by bulk gauge fields in holography."
sidebar:
  order: 50
---

Finite density is the first place where holography begins to look less like a formal dictionary and more like a tool for many-body physics. Instead of asking only for vacuum correlators or thermal correlators, we ask for a state with a nonzero density of a conserved charge.

On the field-theory side, the basic object is a conserved current $J^\mu$ and a charge

$$
Q=\int_{\Sigma} d^{d-1}x \, J^t .
$$

A thermal state at chemical potential $\mu$ is described by

$$
\rho_{\beta,\mu}
=
\frac{1}{Z(\beta,\mu)}
\exp[-\beta(H-\mu Q)] .
$$

On the gravity side, the current $J^\mu$ is dual to a bulk gauge field $A_M$. The chemical potential is the boundary value of its time component, and the charge density is the radial electric flux.

This is the basic finite-density dictionary:

$$
\boxed{
A_t^{(0)} = \mu,
\qquad
\langle J^t\rangle = \rho
\quad
\leftrightarrow
\quad
\text{radial electric flux in AdS}.
}
$$

The point of this page is to make this statement precise and to explain what it does, and does not, mean.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A bulk gauge field encodes chemical potential and charge density through its boundary value and radial electric flux.](/figures/course/finite-density-bulk-gauge-fields.svg)

<figcaption>

A conserved boundary current $J^\mu$ is sourced by the boundary value $A_\mu^{(0)}$ of a bulk gauge field. For a homogeneous finite-density state, $A_t^{(0)}=\mu$ and the radial electric flux is proportional to the charge density $\rho=\langle J^t\rangle$.

</figcaption>
</figure>

## Why this matters

Finite density introduces three new pieces of physics.

First, it gives us a controlled holographic way to study strongly coupled compressible systems. The boundary theory has a conserved charge and a nonzero density of that charge. In ordinary weakly coupled language one might expect quasiparticles, a Fermi surface, or a condensate. Holography does not require any of those assumptions.

Second, finite density forces us to distinguish carefully between global and gauge symmetries. A bulk gauge symmetry is dual to a global symmetry of the boundary CFT. Unless we explicitly choose boundary conditions that make the boundary gauge field dynamical, $A_\mu^{(0)}$ is an external source, not a dynamical photon.

Third, finite density produces new black-hole geometries. Turning on charge in the boundary theory usually means turning on electric flux in the bulk. If that flux backreacts, the neutral AdS black brane becomes a charged Reissner–Nordström-AdS black brane. That is the next page.

## Boundary setup: a current and its source

Let the boundary theory have a conserved current $J^\mu$ satisfying

$$
\partial_\mu J^\mu = 0
$$

in flat space, or

$$
\nabla_\mu J^\mu = 0
$$

on a curved background, up to anomalies that we ignore for now.

The current is sourced by a background gauge field $A_\mu^{(0)}$. A common Lorentzian convention is

$$
S_{\mathrm{QFT}}
\to
S_{\mathrm{QFT}}
+
\int d^d x \, A_\mu^{(0)} J^\mu .
$$

Then the generating functional obeys

$$
\langle J^\mu(x)\rangle
=
\frac{1}{\sqrt{-g_{(0)}}}
\frac{\delta W[A^{(0)}]}{\delta A_\mu^{(0)}(x)} .
$$

A chemical potential for the charge $Q$ is introduced by setting

$$
A_t^{(0)} = \mu
$$

for a homogeneous static state. In Euclidean signature, this statement is often phrased as a background holonomy around the thermal circle.

A more invariant statement is that the chemical potential is the gauge-invariant difference between the boundary value of $A_t$ and the value at the horizon:

$$
\mu = A_t(z=0)-A_t(z_h) .
$$

For a smooth Euclidean black-hole saddle, one usually chooses a gauge in which

$$
A_t(z_h)=0,
\qquad
A_t(0)=\mu .
$$

This is not just a cosmetic convention. At the Euclidean horizon the thermal circle shrinks, so the one-form $A=A_t d\tau$ must be regular there. The horizon value of $A_t$ is therefore fixed by regularity in the usual grand-canonical black-hole saddle.

## Bulk setup: Maxwell field in AdS

The minimal bulk action for a conserved $U(1)$ current is a Maxwell action in an asymptotically AdS spacetime:

$$
S_A
=
-\frac{1}{4g_{d+1}^2}
\int d^{d+1}x\,\sqrt{-g}\,F_{MN}F^{MN}
+S_{\mathrm{bdy}},
\qquad
F=dA .
$$

Here $g_{d+1}$ is the bulk gauge coupling. Its precise normalization depends on the top-down model or bottom-up convention. In a top-down compactification, $g_{d+1}$ is determined by the internal space and flux data. In a bottom-up model, it is a phenomenological parameter fixed by the normalization of the current two-point function.

The Maxwell equation is

$$
\nabla_M F^{MN}=0,
$$

or equivalently

$$
\partial_M\left(\sqrt{-g}F^{MN}\right)=0
$$

when no charged bulk matter is present.

Near the AdS boundary, the gauge field has an expansion of the form

$$
A_i(z,x)
=
A_i^{(0)}(x)
+
\cdots
+
z^{d-2}A_i^{(d-2)}(x)
+
\cdots,
\qquad d>2 .
$$

The leading term is the source. The subleading coefficient is related to the expectation value of the current. In particular, for a homogeneous electric potential in pure asymptotic AdS,

$$
A_t(z)
=
\mu
-
\frac{g_{d+1}^2\rho}{(d-2)L^{d-3}}
z^{d-2}
+
\cdots,
\qquad d>2,
$$

with the sign chosen so that $\rho=\langle J^t\rangle$ in the convention used here.

The more invariant definition is through the renormalized canonical momentum:

$$
\langle J^i\rangle
=
\lim_{\epsilon\to0}
\frac{1}{\sqrt{-g_{(0)}}}
\frac{\delta S_{\mathrm{ren}}}{\delta A_i^{(0)}}
=
\lim_{\epsilon\to0}
\Pi^i_{\mathrm{ren}} .
$$

For the Maxwell field, before adding possible finite counterterms,

$$
\Pi^i
=
-\frac{1}{g_{d+1}^2}
\sqrt{-\gamma}\,n_M F^{Mi},
$$

where $n_M$ is the outward unit normal to the cutoff surface and $\gamma_{ij}$ is the induced metric. Different sign conventions for the outward normal shift an overall sign, so the safest rule is always to define the current by varying $S_{\mathrm{ren}}$.

## Chemical potential as boundary data

In the grand-canonical ensemble, we fix $\mu$. In holography this means Dirichlet boundary conditions for $A_t$:

$$
A_t(z\to0)=\mu .
$$

The boundary generating functional is then

$$
Z_{\mathrm{CFT}}[A^{(0)}]
=
\left\langle
\exp\left(
\int d^d x\, A_\mu^{(0)}J^\mu
\right)
\right\rangle .
$$

The Euclidean thermal partition function at chemical potential is

$$
Z(\beta,\mu)
=
\mathrm{Tr}\, e^{-\beta(H-\mu Q)} .
$$

The grand potential is

$$
\Omega(T,\mu)
=
-T\log Z(\beta,\mu),
$$

and the charge density is

$$
\rho
=
-\frac{1}{V}
\left(\frac{\partial \Omega}{\partial \mu}\right)_T .
$$

In the classical gravity limit,

$$
\Omega(T,\mu)
=
T I_{E,\mathrm{ren}}[A_t^{(0)}=\mu]
$$

for the dominant Euclidean saddle.

## Charge density as radial electric flux

Now assume a static homogeneous ansatz

$$
A=A_t(z)dt .
$$

The $N=t$ Maxwell equation gives

$$
\partial_z\left(\sqrt{-g}F^{zt}\right)=0 .
$$

Thus the radial electric flux is independent of $z$:

$$
\sqrt{-g}F^{zt}=\text{constant} .
$$

This is the bulk form of charge conservation. The same constant can be evaluated near the boundary, where it is proportional to $\rho$, or deeper in the bulk, where it may be carried by a charged horizon, charged matter fields, or charged branes.

This simple observation is surprisingly powerful. It tells us that a finite-density holographic state is not just a black hole with a parameter named $\mu$. It is a bulk configuration carrying electric flux.

## Grand canonical versus canonical ensemble

There are two natural finite-density ensembles.

In the grand-canonical ensemble, the chemical potential is fixed:

$$
\delta A_t^{(0)}=0 .
$$

The on-shell action computes $\Omega(T,\mu)$.

In the canonical ensemble, the charge density is fixed. This corresponds to fixing the radial electric flux rather than the boundary value of $A_t$. At the level of the variational principle, one performs a Legendre transform of the action. Schematically,

$$
S_{\mathrm{canonical}}
=
S_{\mathrm{grand}}
-
\int_{\partial M} d^d x\, A_t^{(0)}\rho .
$$

Then the free energy is

$$
F(T,\rho)
=
\Omega(T,\mu)+\mu Q .
$$

This distinction matters for charged black holes, where stability and phase structure can differ between ensembles.

## Gauge invariance and the meaning of $\mu$

A constant shift of $A_t$ looks like a gauge transformation, so why is $A_t^{(0)}=\mu$ physical?

The answer is that chemical potential is not the absolute value of $A_t$ at one point. It is a boundary condition relative to the regularity condition in the interior. For a black-hole saddle,

$$
\mu
=
A_t(0)-A_t(z_h)
=
\int_{z_h}^{0} dz\,\partial_z A_t .
$$

Equivalently, in Euclidean signature it is tied to the holonomy of the gauge field around the thermal circle, with regularity imposed where the circle contracts.

This is why the common gauge choice

$$
A_t(z_h)=0,
\qquad
A_t(0)=\mu
$$

is physically meaningful even though $A_t$ itself is gauge-dependent.

## Boundary global symmetry, not boundary electromagnetism

A frequent confusion is to say that the bulk gauge field is dual to electromagnetism in the boundary theory. That is usually not correct.

In the standard Dirichlet quantization, $A_\mu^{(0)}$ is a nondynamical source for a global current $J^\mu$. The boundary theory has a global $U(1)$ symmetry. The bulk field is gauge redundant because the dual current is conserved.

The source $A_\mu^{(0)}$ can be interpreted as an externally imposed electromagnetic field, but it is not a fluctuating boundary photon unless we change the boundary conditions and add boundary gauge dynamics.

So the usual dictionary is

$$
\boxed{
\text{bulk gauge symmetry}
\quad\leftrightarrow\quad
\text{boundary global symmetry}.
}
$$

This point is essential in AdS/CMT. Holography often studies strongly coupled charged matter in a background electromagnetic field, not a full theory of dynamical electromagnetism.

## Probe gauge field versus backreacted finite density

There are two levels of finite-density holography.

### Probe limit

One may study a Maxwell field on a fixed neutral geometry. This is useful for current correlators and conductivities at small density or in approximations where the stress tensor contribution of the gauge field is neglected.

The Maxwell field then solves

$$
\nabla_M F^{MN}=0
$$

on a fixed background such as pure AdS or AdS-Schwarzschild.

### Backreacted limit

At finite charge density of order the large-$N$ degrees of freedom, the electric field carries stress-energy. Then the metric and gauge field must solve Einstein–Maxwell equations. The simplest homogeneous solution is the Reissner–Nordström-AdS black brane.

This is the natural gravitational dual of a thermal CFT state at nonzero chemical potential and charge density.

## Finite density and scale invariance

A CFT at nonzero $T$ and $\mu$ has scales. Conformal invariance is not absent, but it is realized through scaling relations.

For a homogeneous CFT in $d$ spacetime dimensions,

$$
p(T,\mu)=T^d f\!\left(\frac{\mu}{T}\right),
$$

or equivalently

$$
p(T,\mu)=\mu^d \tilde f\!\left(\frac{T}{\mu}\right)
$$

when $\mu\neq0$. The stress tensor remains traceless in flat space, so

$$
\epsilon=(d-1)p
$$

for an isotropic homogeneous state, up to anomalies or explicit deformations.

The thermodynamic identities are

$$
dp=s\,dT+\rho\,d\mu,
$$

and

$$
\epsilon+p=Ts+\mu\rho .
$$

These relations are useful checks on any charged black-brane computation.

## What carries the charge in the bulk?

The radial flux equation tells us that charge exists in the bulk, but not what carries it.

There are several possibilities:

1. The flux can end on a charged horizon. This is the simplest Reissner–Nordström-AdS picture.
2. The flux can be carried by charged bulk matter outside the horizon.
3. The flux can be carried by charged branes or stringy degrees of freedom.
4. The flux can be partly behind the horizon and partly in visible bulk matter.

This distinction matters physically. Charge hidden behind the horizon is sometimes called fractionalized charge in the holographic condensed-matter literature. Charge carried by bulk matter outside the horizon is more directly associated with gauge-invariant charged operators or condensates in the boundary theory.

This course does not need that terminology yet, but it is useful to know that the simple dictionary $A_t^{(0)}=\mu$ is only the start. The distribution of electric flux in the radial direction contains physical information about the state.

## Linear response at finite density

Current-current correlators at finite density are computed by perturbing the bulk gauge field:

$$
A_i(z,x)=A_i^{\mathrm{background}}(z)+a_i(z,x) .
$$

The retarded correlator is obtained from the response/source ratio:

$$
G^R_{J^iJ^j}(\omega,\mathbf k)
=
\frac{\delta\langle J^i\rangle}{\delta A_j^{(0)}} .
$$

At finite density, current perturbations often mix with metric perturbations because the background electric field couples gauge and gravitational fluctuations. This is not a technical annoyance; it is the bulk reflection of the fact that charge transport, momentum transport, and energy transport are coupled in a charged fluid.

For example, in a translationally invariant finite-density theory, the electrical conductivity contains a delta function at zero frequency because momentum cannot relax. Holographically, that delta function is tied to coupled gauge-metric perturbations.

## Dictionary checkpoint

The finite-density dictionary is:

| Boundary quantity | Bulk quantity |
|---|---|
| conserved current $J^\mu$ | bulk gauge field $A_M$ |
| source for $J^\mu$ | boundary value $A_\mu^{(0)}$ |
| chemical potential $\mu$ | $A_t(0)-A_t(z_h)$ |
| charge density $\rho=\langle J^t\rangle$ | radial electric flux |
| grand-canonical ensemble | Dirichlet boundary condition for $A_t$ |
| canonical ensemble | fixed electric flux / Legendre-transformed action |
| current correlators | gauge-field fluctuations |
| finite-density backreaction | charged black brane or charged bulk matter |

The shortest useful slogan is:

$$
\boxed{
\mu \text{ is boundary electric potential; }
\rho \text{ is radial electric flux.}
}
$$

## Common confusions

### “The bulk gauge field is the boundary photon.”

Usually no. In standard AdS/CFT boundary conditions, the bulk gauge field is dual to a global current in the boundary theory. Its boundary value is an external source. A dynamical boundary photon requires changing the boundary conditions and adding boundary gauge dynamics.

### “A constant $A_t$ is pure gauge, so chemical potential is meaningless.”

The physical chemical potential is the difference between the boundary value and the regular interior value. For a black hole, smoothness fixes $A_t(z_h)=0$ in the Euclidean gauge, so $A_t(0)=\mu$ is meaningful.

### “Finite charge density always means a charged black hole.”

Not always. A charged black hole is the simplest homogeneous backreacted saddle. But charge can also be carried by charged scalar fields, fermion fluids, branes, or other bulk degrees of freedom.

### “The coefficient of $z^{d-2}$ is always exactly the charge density.”

It is proportional to the charge density, but the proportionality depends on the Maxwell normalization, counterterms, and conventions. The invariant prescription is variation of $S_{\mathrm{ren}}$ with respect to $A_t^{(0)}$.

### “Finite density breaks conformal invariance explicitly.”

A chemical potential introduces a scale in the state or ensemble, but the underlying theory can still be conformal. Thermodynamic functions then obey scaling relations such as $p(T,\mu)=T^d f(\mu/T)$.

## Exercises

### Exercise 1: Solve the near-boundary Maxwell equation

In pure Poincare AdS$_{d+1}$,

$$
ds^2=\frac{L^2}{z^2}
\left(dz^2-dt^2+d\mathbf x^2\right),
$$

consider a static homogeneous potential $A=A_t(z)dt$. Show that the Maxwell equation gives

$$
A_t(z)=\mu-C z^{d-2}
$$

for $d>2$.

<details>
<summary><strong>Solution</strong></summary>

The Maxwell equation is

$$
\partial_z(\sqrt{-g}F^{zt})=0 .
$$

For the AdS metric,

$$
\sqrt{-g}=\frac{L^{d+1}}{z^{d+1}},
\qquad
F^{zt}=g^{zz}g^{tt}F_{zt}
=-\frac{z^4}{L^4}\partial_z A_t .
$$

Thus

$$
\sqrt{-g}F^{zt}
=-L^{d-3}z^{3-d}\partial_z A_t
=
\text{constant} .
$$

Therefore

$$
\partial_z A_t \propto z^{d-3} .
$$

Integrating gives

$$
A_t(z)=\mu-Cz^{d-2}
$$

for $d>2$. The constant $\mu$ is the source, and $C$ is proportional to the charge density.

</details>

### Exercise 2: Why must $A_t$ vanish at a smooth Euclidean horizon?

Near a nonextremal Euclidean horizon, the metric takes the schematic form

$$
ds^2 \simeq dR^2 + R^2 d\theta^2 + \cdots .
$$

Explain why the one-form $A=A_\theta d\theta$ is regular at $R=0$ only if $A_\theta$ vanishes there in a smooth gauge.

<details>
<summary><strong>Solution</strong></summary>

At $R=0$, the angular coordinate $\theta$ degenerates. The one-form $d\theta$ is not regular at the origin of polar coordinates. In Cartesian coordinates,

$$
d\theta=\frac{x\,dy-y\,dx}{x^2+y^2},
$$

which is singular at $x=y=0$. Therefore a one-form proportional to $d\theta$ is regular at the origin only if its coefficient vanishes sufficiently fast. For a smooth static black-hole gauge field, this means choosing

$$
A_\theta(R=0)=0,
$$

or in Lorentzian notation after Wick rotation,

$$
A_t(z_h)=0.
$$

The chemical potential is then the boundary value relative to this regular horizon value.

</details>

### Exercise 3: Thermodynamic conjugates

Starting from the grand potential $\Omega(T,\mu)$, show that

$$
\rho=-\frac{1}{V}
\left(\frac{\partial\Omega}{\partial\mu}\right)_T .
$$

<details>
<summary><strong>Solution</strong></summary>

The grand partition function is

$$
Z=\mathrm{Tr}\,e^{-\beta(H-\mu Q)},
\qquad
\Omega=-T\log Z .
$$

Then

$$
\frac{\partial\log Z}{\partial\mu}
=
\beta\langle Q\rangle .
$$

Thus

$$
\frac{\partial\Omega}{\partial\mu}
=
-T\frac{\partial\log Z}{\partial\mu}
=-\langle Q\rangle .
$$

Dividing by the spatial volume $V$ gives

$$
\rho=\frac{\langle Q\rangle}{V}
=-\frac{1}{V}
\left(\frac{\partial\Omega}{\partial\mu}\right)_T .
$$

</details>

### Exercise 4: Boundary global symmetry

Why is it natural that a bulk gauge field is dual to a conserved boundary current rather than to an arbitrary vector operator?

<details>
<summary><strong>Solution</strong></summary>

A bulk gauge transformation is a redundancy:

$$
A_M\to A_M+\partial_M\Lambda .
$$

In the boundary generating functional, the corresponding source changes as

$$
A_i^{(0)}\to A_i^{(0)}+\partial_i\Lambda^{(0)} .
$$

Gauge invariance of the generating functional implies

$$
0=\delta W
=\int d^d x\,\sqrt{-g_{(0)}}\,
\langle J^i\rangle\partial_i\Lambda^{(0)}
=-\int d^d x\,\sqrt{-g_{(0)}}\,
\Lambda^{(0)}\nabla_i\langle J^i\rangle .
$$

Since $\Lambda^{(0)}$ is arbitrary, this gives

$$
\nabla_i\langle J^i\rangle=0 .
$$

Thus bulk gauge redundancy is precisely what enforces conservation of the dual current.

</details>

## Further reading

- S. A. Hartnoll, [Lectures on holographic methods for condensed matter physics](https://arxiv.org/abs/0903.3246).
- J. McGreevy, [Holographic duality with a view toward many-body physics](https://arxiv.org/abs/0909.0518).
- A. Chamblin, R. Emparan, C. V. Johnson, and R. C. Myers, [Holography, Thermodynamics and Fluctuations of Charged AdS Black Holes](https://arxiv.org/abs/hep-th/9904197).
- N. Iqbal and H. Liu, [Universality of the hydrodynamic limit in AdS/CFT and the membrane paradigm](https://arxiv.org/abs/0809.3808).
