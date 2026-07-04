---
title: "Cylinder and Finite-Size Scaling"
description: "Weyl maps from the plane to the cylinder, cylinder correlators, Casimir energy, and finite-size spectra of CFTs."
sidebar:
  order: 1
---

## Why the cylinder is not just a change of coordinates

The cylinder is one of the most important backgrounds in CFT. On the plane, local operators are inserted at points. On the cylinder, the same operators become states, and their scaling dimensions become energy levels. This is the cleanest way to see why a CFT spectrum is physical data rather than a bookkeeping device.

For AdS/CFT, the cylinder is unavoidable. The conformal boundary of global AdS$_{d+1}$ is

$$
S^{d-1}\times \mathbb R_t .
$$

Thus a CFT placed on $S^{d-1}\times\mathbb R$ is not an optional finite-volume version of the theory; it is the Hamiltonian frame naturally used by global AdS. The dictionary

$$
\Delta_{\mathcal O}
\quad\longleftrightarrow\quad
E_{\rm global\ AdS}
$$

is really the statement that radial quantization turns dilatations on flat space into time translations on the cylinder.

The goal of this page is to make this statement precise, first in any dimension and then in the especially powerful two-dimensional case.

---

## The plane-cylinder Weyl map in any dimension

Start with Euclidean flat space in polar coordinates,

$$
ds^2_{\mathbb R^d}=dr^2+r^2d\Omega_{d-1}^2.
$$

Introduce the logarithmic radial coordinate

$$
r=R e^{\tau/R},
\qquad
\tau=R\log\frac rR.
$$

Then

$$
ds^2_{\mathbb R^d}
=e^{2\tau/R}\left(d\tau^2+R^2d\Omega_{d-1}^2\right).
$$

So punctured flat space is Weyl-equivalent to the cylinder

$$
\mathbb R^d\setminus\{0\}
\simeq
S^{d-1}_R\times\mathbb R_\tau,
$$

up to the Weyl factor $e^{2\tau/R}$. A CFT is designed precisely to survive such Weyl transformations, modulo anomalies that will be discussed later.

The dilatation operator $D$ on flat space becomes the cylinder Hamiltonian. If $R$ is the radius of the spatial sphere, then a scalar primary operator $\mathcal O$ of dimension $\Delta$ creates a cylinder state whose excitation energy is

$$
E_{\mathcal O}-E_0=\frac{\Delta}{R}.
$$

In two dimensions, the spatial cylinder is usually written with circumference $L=2\pi R$, so this becomes

$$
E_{\mathcal O}-E_0=\frac{2\pi}{L}\Delta_{\mathcal O}.
$$

This is the simplest quantitative form of the state-operator correspondence.

<figure class="doc-figure" style="--figure-width: 44rem; --caption-width: 55rem;">

![The exponential map from the plane to the Euclidean cylinder.](/figures/cft/cylinder-finite-size-map.svg)

<figcaption>

The exponential map $z=e^{2\pi w/L}$ turns radial evolution on the plane into Euclidean time evolution on the cylinder $w=\tau+i\sigma$, with $\sigma\sim\sigma+L$. In two dimensions, primary dimensions become cylinder excitation energies via $E_{\mathcal O}-E_0=2\pi\Delta_{\mathcal O}/L$, while the vacuum carries the universal Casimir energy $E_0=-\pi c/(6L)$.

</figcaption>
</figure>

---

## The cylinder operator

The Weyl factor in the metric tells us how to relate local operators on the plane and on the cylinder. For a scalar primary of dimension $\Delta$, a convenient convention is

$$
\mathcal O_{\rm cyl}(\tau,n)
=
e^{\Delta\tau/R}\,
\mathcal O_{\mathbb R^d}\!\left(R e^{\tau/R}n\right),
\qquad
n\in S^{d-1}.
$$

This is not an arbitrary normalization. It is exactly the factor needed to remove the local Weyl rescaling of distances. In even dimensions, the Weyl anomaly affects the partition function and stress-tensor expectation values on curved backgrounds, but separated primary correlators transform by the local Weyl factors. Contact terms require more care; ordinary separated-point correlators do not.

The cylinder state associated with a local operator is

$$
|\mathcal O\rangle=\mathcal O_{\mathbb R^d}(0)|0\rangle .
$$

Because the cylinder Hamiltonian is $H_{\rm cyl}=D/R$, and because

$$
D|\mathcal O\rangle=\Delta_{\mathcal O}|\mathcal O\rangle,
$$

we get

$$
H_{\rm cyl}|\mathcal O\rangle
=
\frac{\Delta_{\mathcal O}}{R}|\mathcal O\rangle.
$$

Descendants are obtained by acting with translations $P_\mu$. Since

$$
[D,P_\mu]=P_\mu,
$$

a descendant at level $N$ has excitation energy

$$
E_{\mathcal O,N}-E_0
=
\frac{\Delta_{\mathcal O}+N}{R}.
$$

The descendants are not merely extra states. They are the Hamiltonian tower that sits above a primary on the cylinder. In AdS language, they are the global-mode excitations of the same bulk representation.

---

## Cylinder two-point functions in any dimension

Let a scalar primary have flat-space two-point function

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\rangle_{\mathbb R^d}
=
\frac{C_{\mathcal O}}{|x_{12}|^{2\Delta}}.
$$

Set

$$
x_i=R e^{\tau_i/R}n_i,
\qquad
n_i^2=1.
$$

Then

$$
|x_{12}|^2
=
2R^2e^{(\tau_1+\tau_2)/R}
\left(
\cosh\frac{\tau_{12}}{R}-n_1\cdot n_2
\right),
$$

where $\tau_{12}=\tau_1-\tau_2$. Multiplying by the Weyl factors from the two cylinder operators gives

$$
\boxed{
\langle \mathcal O(\tau_1,n_1)\mathcal O(\tau_2,n_2)\rangle_{\rm cyl}
=
\frac{C_{\mathcal O}}{
\left[
2R^2\left(\cosh\frac{\tau_{12}}{R}-n_1\cdot n_2\right)
\right]^\Delta
}.
}
$$

For large Euclidean time separation,

$$
|\tau_{12}|\gg R,
$$

the correlator decays as

$$
\langle \mathcal O(\tau_1,n_1)\mathcal O(\tau_2,n_2)\rangle_{\rm cyl}
\sim
\exp\left(-\frac{\Delta}{R}|\tau_{12}|\right).
$$

This is the spectral decomposition in disguise. The power law on $\mathbb R^d$ has become exponential decay on the cylinder because the cylinder has a Hamiltonian with discrete energy levels.

This is one of the most useful mental translations in CFT:

$$
\text{power law on the plane}
\quad\Longleftrightarrow\quad
\text{energy gap on the cylinder}.
$$

The word "gap" here must be understood carefully. The gap is a finite-size gap caused by compactifying space to $S^{d-1}$. It vanishes as $R\to\infty$. It is not a flat-space mass gap.

---

## Perturbing away from the fixed point

Finite-size scaling is most powerful when the CFT is slightly deformed. Suppose the fixed point is perturbed by a relevant scalar operator,

$$
S=S_{\rm CFT}+\tilde g\int d^d x\, \mathcal O_g(x),
\qquad
\Delta_g<d.
$$

The coupling has mass dimension

$$
[\tilde g]=d-\Delta_g.
$$

On a sphere of radius $R$, the only dimensionless coupling that can appear in universal quantities is therefore

$$
g_R=\tilde g R^{d-\Delta_g}.
$$

This implies the scaling form

$$
E_n(R,\tilde g)-E_0(R,\tilde g)
=
\frac{1}{R}\,F_n(g_R),
$$

where $F_n$ is universal once the operator normalization and the coupling convention are fixed. At the conformal point,

$$
F_n(0)=\Delta_n.
$$

In infinite volume, the same deformation generates a correlation length

$$
\xi\sim |\tilde g|^{-1/(d-\Delta_g)}.
$$

Thus finite-size scaling can be phrased in either of two equivalent ways:

$$
g_R=\tilde g R^{d-\Delta_g}
\qquad\Longleftrightarrow\qquad
\frac{R}{\xi}.
$$

The CFT regime is $R\ll \xi$, the massive or gapped regime is $R\gg \xi$, and the crossover between them is encoded by universal scaling functions. This is the continuum version of the finite-size scaling window used in numerical studies of critical systems.

---

## The two-dimensional cylinder

In two-dimensional Euclidean CFT, use complex plane coordinate $z$ and cylinder coordinate

$$
w=\tau+i\sigma,
\qquad
\bar w=\tau-i\sigma,
\qquad
\sigma\sim\sigma+L.
$$

The exponential map is

$$
z=e^{2\pi w/L},
\qquad
\bar z=e^{2\pi \bar w/L}.
$$

The real part of $w$ is logarithmic radial time; the imaginary part of $w$ is the angular coordinate. Circles around the origin in the $z$-plane become constant-$\tau$ spatial circles on the cylinder.

A primary operator of weights $(h,\bar h)$ transforms as

$$
\mathcal O_{\rm cyl}(w,\bar w)
=
\left(\frac{dz}{dw}\right)^h
\left(\frac{d\bar z}{d\bar w}\right)^{\bar h}
\mathcal O_{\rm plane}(z,\bar z).
$$

Since

$$
\frac{dz}{dw}=\frac{2\pi}{L}z,
\qquad
\frac{d\bar z}{d\bar w}=\frac{2\pi}{L}\bar z,
$$

we have

$$
\mathcal O_{\rm cyl}(w,\bar w)
=
\left(\frac{2\pi}{L}\right)^{h+\bar h}
z^h\bar z^{\bar h}\mathcal O_{\rm plane}(z,\bar z).
$$

This formula is worth absorbing. It says that the same local operator has different coordinate representatives on the plane and on the cylinder, because the Weyl factor rescales local lengths.

---

## Two-dimensional cylinder correlators

On the plane, normalize a primary by

$$
\langle \mathcal O(z_1,\bar z_1)\mathcal O(z_2,\bar z_2)\rangle_{\mathbb C}
=
\frac{1}{z_{12}^{2h}\bar z_{12}^{2\bar h}}.
$$

Using $z=e^{2\pi w/L}$, one obtains the cylinder correlator

$$
\boxed{
\langle \mathcal O(w_1,\bar w_1)\mathcal O(w_2,\bar w_2)\rangle_{\rm cyl}
=
\left[\frac{\pi/L}{\sinh\left(\frac{\pi w_{12}}{L}\right)}\right]^{2h}
\left[\frac{\pi/L}{\sinh\left(\frac{\pi \bar w_{12}}{L}\right)}\right]^{2\bar h}
}
$$

where

$$
w_{12}=w_1-w_2,
\qquad
\bar w_{12}=\bar w_1-\bar w_2.
$$

For equal Euclidean time, $\tau_1=\tau_2$, and for a scalar operator with $h=\bar h=\Delta/2$, this becomes

$$
\langle \mathcal O(0,\sigma)\mathcal O(0,0)\rangle_{\rm cyl}
=
\left[\frac{\pi/L}{\left|\sin(\pi\sigma/L)\right|}\right]^{2\Delta}.
$$

The power law on the plane has turned into a periodic power law on the circle. At separations much smaller than $L$, this reduces to the flat-space answer,

$$
\left[\frac{\pi/L}{\sin(\pi\sigma/L)}\right]^{2\Delta}
\sim
\frac{1}{|\sigma|^{2\Delta}}
\qquad
|\sigma|\ll L.
$$

At large Euclidean time separation, take $\tau_{12}\gg L$ with fixed $\sigma_{12}$. Then

$$
\langle \mathcal O(\tau,\sigma)\mathcal O(0,0)\rangle_{\rm cyl}
\sim
\exp\left(-\frac{2\pi\Delta}{L}\tau\right).
$$

The exponential decay directly reads off the excitation energy

$$
E_{\mathcal O}-E_0=\frac{2\pi\Delta}{L}.
$$

So the cylinder correlator is not merely a useful formula; it is the bridge between local CFT data and Hamiltonian spectroscopy.

---

## Stress tensor, Schwarzian derivative, and Casimir energy

The stress tensor is not an ordinary primary field. In two dimensions, under a holomorphic coordinate transformation $z=z(w)$, it transforms as

$$
T_{\rm cyl}(w)
=
\left(\frac{dz}{dw}\right)^2T_{\rm plane}(z)
+
\frac{c}{12}\{z,w\},
$$

where the Schwarzian derivative is

$$
\{z,w\}
=
\frac{z'''(w)}{z'(w)}
-
\frac32\left(\frac{z''(w)}{z'(w)}\right)^2.
$$

For

$$
z=e^{aw},
\qquad
a=\frac{2\pi}{L},
$$

we have

$$
\frac{z'''}{z'}=a^2,
\qquad
\frac{z''}{z'}=a,
\qquad
\{z,w\}=-\frac12a^2.
$$

Therefore

$$
T_{\rm cyl}(w)
=
\left(\frac{2\pi}{L}\right)^2
\left(z^2T_{\rm plane}(z)-\frac{c}{24}\right).
$$

Since the plane vacuum has $\langle T_{\rm plane}\rangle=0$, the cylinder vacuum has a nonzero stress-tensor expectation value,

$$
\langle T_{\rm cyl}\rangle
=
-\frac{c}{24}\left(\frac{2\pi}{L}\right)^2,
\qquad
\langle \bar T_{\rm cyl}\rangle
=
-\frac{c}{24}\left(\frac{2\pi}{L}\right)^2.
$$

In Virasoro language, the cylinder Hamiltonian and momentum are

$$
H_{\rm cyl}
=
\frac{2\pi}{L}\left(L_0+\bar L_0-\frac{c}{12}\right),
$$

$$
P_{\rm cyl}
=
\frac{2\pi}{L}\left(L_0-\bar L_0\right).
$$

Thus a state associated with a primary of weights $(h,\bar h)$ and descendant levels $(N,\bar N)$ has

$$
E_{h,\bar h;N,\bar N}
=
\frac{2\pi}{L}
\left(
h+\bar h+N+\bar N-\frac{c}{12}
\right),
$$

$$
P_{h,\bar h;N,\bar N}
=
\frac{2\pi}{L}
\left(
h-\bar h+N-\bar N
\right).
$$

The vacuum energy is

$$
\boxed{
E_0=-\frac{\pi c}{6L}
}
$$

for a unitary CFT on a spatial circle of circumference $L$ in relativistic units. This is the universal Casimir energy.

The word "universal" needs one caution. In a lattice model, the total ground-state energy also contains a nonuniversal extensive contribution,

$$
E_0^{\rm lattice}(L)
=
\epsilon_\infty L
-\frac{\pi c v}{6L}
+o(L^{-1}),
$$

where $v$ is the emergent low-energy velocity. The coefficient of $1/L$ is universal; the bulk energy density $\epsilon_\infty$ is not.

---

## Finite-size scaling as RG in a box

At a critical point, the infinite system has no intrinsic length scale. If the system is placed in a finite spatial box of size $L$, then $L$ becomes the only infrared scale. This is the logic of finite-size scaling.

Suppose a quantity $Q$ has scaling dimension $q$. Near a CFT fixed point deformed by couplings $g_i$ to operators of dimensions $\Delta_i$, define the RG exponents

$$
y_i=d-\Delta_i.
$$

Then finite-size scaling says

$$
Q(L,\{g_i\})
=
L^{-q}\Phi_Q\left(g_1L^{y_1},g_2L^{y_2},\ldots\right),
$$

up to corrections from irrelevant operators. At the fixed point, all $g_i=0$, so

$$
Q(L)\propto L^{-q}.
$$

For energy levels in a relativistic CFT,

$$
E_n(L)-E_0(L)\propto \frac1L.
$$

The proportionality constants are not arbitrary: in two dimensions, they are the scaling dimensions.

For a critical quantum chain with velocity $v$, the universal CFT predictions are

$$
\boxed{
E_n(L)-E_0(L)
=
\frac{2\pi v}{L}\Delta_n+o(L^{-1})
}
$$

and

$$
\boxed{
P_n(L)-P_0(L)
=
\frac{2\pi}{L}s_n+o(L^{-1})
}
$$

where

$$
\Delta_n=h_n+\bar h_n,
\qquad
s_n=h_n-\bar h_n.
$$

The ground-state energy behaves as

$$
\boxed{
E_0(L)=\epsilon_\infty L-\frac{\pi c v}{6L}+o(L^{-1})
}
$$

for periodic boundary conditions. These three formulas are among the most useful practical bridges between numerical many-body physics and CFT. They allow one to extract the central charge, operator dimensions, and spins from finite-size spectra.

---

## Cylinder versus thermal cylinder

There are two common cylinders in CFT, and they mean different things.

| Geometry | Periodic direction | Physical meaning |
|---|---:|---|
| $S^{d-1}\times\mathbb R_\tau$ | space | Hamiltonian quantization on a compact spatial slice |
| $\mathbb R^{d-1}\times S^1_\beta$ | Euclidean time | thermal ensemble at temperature $T=1/\beta$ |

In two-dimensional CFT, exchanging space and Euclidean time often looks like a simple modular transformation. In higher-dimensional CFT, the distinction is sharper: the spatial sphere $S^{d-1}$ is the natural boundary of global AdS, while the thermal circle is the natural setting for black branes, black holes, and real-time response.

The present page is about the first cylinder. Thermal CFT comes later.

---

## AdS/CFT checkpoint

The global AdS metric may be written schematically as

$$
ds^2_{\rm AdS}
=
R_{\rm AdS}^2
\left[
-\cosh^2\rho\,dt^2+d\rho^2+\sinh^2\rho\,d\Omega_{d-1}^2
\right].
$$

At large $\rho$, the conformal boundary is

$$
S^{d-1}\times\mathbb R_t.
$$

This is the Lorentzian cylinder. The CFT Hamiltonian on the cylinder is therefore the natural boundary dual of global AdS time translation. The state created by a primary operator $\mathcal O$ corresponds to a one-particle bulk state whose global AdS energy is

$$
E_{\rm bulk}R_{\rm AdS}=\Delta_{\mathcal O}.
$$

Descendants correspond to acting with boundary momentum generators; in global AdS language, they are higher oscillator modes of the same bulk representation.

For large-$N$ holographic CFTs, the cylinder spectrum organizes itself as follows:

$$
\begin{array}{ccl}
\text{single-trace primary} &\longleftrightarrow& \text{single-particle bulk field},\\
\text{multi-trace primary} &\longleftrightarrow& \text{multi-particle bulk state},\\
T_{\mu\nu} &\longleftrightarrow& \text{graviton},\\
J_\mu &\longleftrightarrow& \text{bulk gauge field}.
\end{array}
$$

The cylinder is where this dictionary becomes Hamiltonian physics.

---

## Common pitfalls

The first pitfall is to confuse a finite-size gap with a mass gap. A massive theory has a correlation length $\xi$ that remains finite as $L\to\infty$. A CFT on a finite circle has a gap proportional to $1/L$, which vanishes in the infinite-volume limit. The finite gap is caused by the box, not by a mass.

The second pitfall is to forget the Casimir shift. On the plane, the vacuum has zero scaling dimension. On the cylinder, the vacuum energy is shifted by the Schwarzian term. In two dimensions this shift is fixed by $c$.

The third pitfall is to use finite-size formulas without the velocity $v$ in lattice systems. A continuum relativistic CFT sets $v=1$. A critical spin chain or condensed-matter realization generally has a nonuniversal velocity that must be measured or fixed separately.

---

## Exercises

### Exercise 1 — Derive the Weyl map

Starting from

$$
ds^2_{\mathbb R^d}=dr^2+r^2d\Omega_{d-1}^2,
\qquad
r=R e^{\tau/R},
$$

show that

$$
ds^2_{\mathbb R^d}
=e^{2\tau/R}\left(d\tau^2+R^2d\Omega_{d-1}^2\right).
$$

<details>
<summary><strong>Solution</strong></summary>

From $r=R e^{\tau/R}$, we get

$$
dr=e^{\tau/R}d\tau.
$$

Therefore

$$
dr^2=e^{2\tau/R}d\tau^2,
\qquad
r^2d\Omega_{d-1}^2=R^2e^{2\tau/R}d\Omega_{d-1}^2.
$$

Adding the two terms gives

$$
ds^2_{\mathbb R^d}
=e^{2\tau/R}\left(d\tau^2+R^2d\Omega_{d-1}^2\right).
$$

Thus flat space minus the origin is Weyl-equivalent to the cylinder.

</details>

### Exercise 2 — Derive the cylinder two-point function in any dimension

Use

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\rangle
=
\frac{C_{\mathcal O}}{|x_{12}|^{2\Delta}},
\qquad
x_i=R e^{\tau_i/R}n_i,
$$

to derive the cylinder correlator

$$
\langle \mathcal O(\tau_1,n_1)\mathcal O(\tau_2,n_2)\rangle_{\rm cyl}
=
\frac{C_{\mathcal O}}{
\left[
2R^2\left(\cosh\frac{\tau_{12}}{R}-n_1\cdot n_2\right)
\right]^\Delta
}.
$$

<details>
<summary><strong>Solution</strong></summary>

We compute

$$
|x_{12}|^2
=
R^2e^{2\tau_1/R}+R^2e^{2\tau_2/R}
-2R^2e^{(\tau_1+\tau_2)/R}n_1\cdot n_2.
$$

Factor out $R^2e^{(\tau_1+\tau_2)/R}$:

$$
|x_{12}|^2
=
R^2e^{(\tau_1+\tau_2)/R}
\left(
e^{\tau_{12}/R}+e^{-\tau_{12}/R}-2n_1\cdot n_2
\right).
$$

Using $e^a+e^{-a}=2\cosh a$,

$$
|x_{12}|^2
=
2R^2e^{(\tau_1+\tau_2)/R}
\left(
\cosh\frac{\tau_{12}}{R}-n_1\cdot n_2
\right).
$$

A scalar primary satisfies

$$
\mathcal O_{\rm cyl}(\tau,n)
=
e^{\Delta\tau/R}\mathcal O_{\mathbb R^d}(R e^{\tau/R}n).
$$

Multiplying the plane correlator by $e^{\Delta(\tau_1+\tau_2)/R}$ cancels the exponential factor in $|x_{12}|^{2\Delta}$ and gives the desired expression.

</details>

### Exercise 3 — Derive the two-dimensional cylinder two-point function

Starting from

$$
\langle \mathcal O(z_1,\bar z_1)\mathcal O(z_2,\bar z_2)\rangle
=
\frac{1}{z_{12}^{2h}\bar z_{12}^{2\bar h}},
$$

and using

$$
z=e^{2\pi w/L},
$$

derive the two-dimensional cylinder two-point function.

<details>
<summary><strong>Solution</strong></summary>

A primary transforms as

$$
\mathcal O_{\rm cyl}(w,\bar w)
=
\left(\frac{dz}{dw}\right)^h
\left(\frac{d\bar z}{d\bar w}\right)^{\bar h}
\mathcal O_{\rm plane}(z,\bar z).
$$

For $z=e^{2\pi w/L}$,

$$
\frac{dz}{dw}=\frac{2\pi}{L}z.
$$

Also,

$$
z_1-z_2
=
e^{\pi(w_1+w_2)/L}
\left(e^{\pi w_{12}/L}-e^{-\pi w_{12}/L}\right)
=
2e^{\pi(w_1+w_2)/L}
\sinh\left(\frac{\pi w_{12}}{L}\right).
$$

Therefore

$$
\frac{\left(\frac{dz_1}{dw_1}\frac{dz_2}{dw_2}\right)^h}{(z_1-z_2)^{2h}}
=
\left[
\frac{\pi/L}{\sinh\left(\frac{\pi w_{12}}{L}\right)}
\right]^{2h}.
$$

The antiholomorphic part is identical, so

$$
\langle \mathcal O(w_1,\bar w_1)\mathcal O(w_2,\bar w_2)\rangle_{\rm cyl}
=
\left[
\frac{\pi/L}{\sinh\left(\frac{\pi w_{12}}{L}\right)}
\right]^{2h}
\left[
\frac{\pi/L}{\sinh\left(\frac{\pi \bar w_{12}}{L}\right)}
\right]^{2\bar h}.
$$

</details>

### Exercise 4 — Compute the Schwarzian shift

For

$$
z=e^{aw},
$$

compute $\{z,w\}$ and use it to show that the plane vacuum has nonzero cylinder energy.

<details>
<summary><strong>Solution</strong></summary>

We have

$$
z'=az,
\qquad
z''=a^2z,
\qquad
z'''=a^3z.
$$

Thus

$$
\frac{z'''}{z'}=a^2,
\qquad
\frac{z''}{z'}=a,
$$

and

$$
\{z,w\}
=
a^2-\frac32a^2
=
-\frac12a^2.
$$

The stress tensor transforms as

$$
T_{\rm cyl}(w)
=
\left(\frac{dz}{dw}\right)^2T_{\rm plane}(z)
+
\frac{c}{12}\{z,w\}.
$$

Since $\langle T_{\rm plane}\rangle=0$ in the plane vacuum,

$$
\langle T_{\rm cyl}\rangle
=
-\frac{c}{24}a^2.
$$

With $a=2\pi/L$, this gives the chiral vacuum shift. Combining the holomorphic and antiholomorphic sectors gives

$$
H_{\rm cyl}
=
\frac{2\pi}{L}\left(L_0+\bar L_0-\frac{c}{12}\right),
$$

so the vacuum energy is

$$
E_0=-\frac{\pi c}{6L}.
$$

</details>

### Exercise 5 — Extract CFT data from finite-size energies

A critical periodic spin chain has low-energy spectrum

$$
E_n(L)-E_0(L)=\frac{2\pi v}{L}\Delta_n+o(L^{-1}),
$$

and ground-state energy

$$
E_0(L)=\epsilon_\infty L-\frac{\pi c v}{6L}+o(L^{-1}).
$$

Assume $v$ is known. Explain how to extract $\Delta_n$ and $c$ from numerical data at several large values of $L$.

<details>
<summary><strong>Solution</strong></summary>

For each excited level,

$$
\Delta_n(L)
=
\frac{L}{2\pi v}\left[E_n(L)-E_0(L)\right].
$$

As $L\to\infty$, this approaches the scaling dimension $\Delta_n$. In practice one fits

$$
\Delta_n(L)=\Delta_n+aL^{-\omega}+\cdots,
$$

where $\omega>0$ is controlled by irrelevant operators.

For the central charge, first fit the extensive part $\epsilon_\infty L$. Then compute

$$
c(L)
=
-\frac{6L}{\pi v}\left[E_0(L)-\epsilon_\infty L\right].
$$

As $L\to\infty$, $c(L)$ approaches $c$. In real numerical work, $\epsilon_\infty$, $c$, and correction terms are often fit simultaneously.

</details>

### Exercise 6 — Why the finite cylinder is not massive

A scalar two-point function on the cylinder decays at large Euclidean time as

$$
\langle \mathcal O(\tau)\mathcal O(0)\rangle_{\rm cyl}
\sim
\exp\left(-\frac{2\pi\Delta}{L}\tau\right).
$$

Explain why this exponential decay does not mean that the CFT has developed a mass gap.

<details>
<summary><strong>Solution</strong></summary>

The decay exponent is

$$
E_{\mathcal O}-E_0=\frac{2\pi\Delta}{L}.
$$

This gap is caused by compactifying space to a circle of circumference $L$. It vanishes as $L\to\infty$:

$$
\lim_{L\to\infty}\frac{2\pi\Delta}{L}=0.
$$

A genuine mass gap would remain finite in the infinite-volume limit. Therefore the finite cylinder has a discrete spectrum, but the underlying infinite-volume CFT remains gapless.

</details>

---

## Takeaway

The cylinder turns scale into time:

$$
D_{\rm plane}
\quad\longrightarrow\quad
H_{\rm cyl}.
$$

In two dimensions this gives exact and extremely useful formulas:

$$
E_n-E_0=\frac{2\pi}{L}\Delta_n,
\qquad
P_n-P_0=\frac{2\pi}{L}s_n,
\qquad
E_0=-\frac{\pi c}{6L}.
$$

For AdS/CFT, this is the first Hamiltonian form of the dictionary: CFT scaling dimensions are global AdS energies.

## Further reading

For the 2D cylinder, finite-size scaling, and the central charge, see Di Francesco, Mathieu, and Sénéchal on radial quantization, modular invariance, and finite-size scaling. For the higher-dimensional cylinder, the most useful companions are modern conformal bootstrap lecture notes, where the cylinder is treated as the natural Hilbert-space quantization of a CFT. The next pages will use this cylinder picture to discuss Weyl anomalies, thermal CFT, and entanglement.
