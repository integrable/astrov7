---
title: "Global AdS and the Cylinder"
description: "How global AdS compactifies to a boundary cylinder, why global time is CFT cylinder time, and how operator dimensions become energies."
sidebar:
  order: 40
---

Global AdS is the gravitational description of the CFT vacuum on a spatial sphere. This is the first place where the boundary theory should be thought of not merely as a collection of local operators on flat space, but as a quantum system with a Hilbert space:

$$
\mathcal H_{\mathrm{CFT}}(S^{d-1}),
\qquad
H_{\mathrm{cyl}}\text{ generating time translations on }\mathbb R_t\times S^{d-1}.
$$

The point of this page is to make that sentence precise. In global coordinates, pure $\mathrm{AdS}_{d+1}$ is a solid cylinder. Its conformal boundary is the cylinder $\mathbb R_t\times S^{d-1}$. The CFT Hamiltonian on that cylinder is the dilatation operator of flat-space radial quantization, up to the radius used to measure energy:

$$
H_{\mathrm{cyl}} = \frac{D}{L},
\qquad
E_{\mathrm{primary}} = \frac{\Delta}{L}.
$$

This relation is one of the cleanest bridges between CFT representation theory and bulk physics. A local primary operator of dimension $\Delta$ creates a lowest-energy state on the boundary cylinder; the dual bulk field has a lowest dimensionless normal-mode frequency $\Omega=\Delta$.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Global AdS compactifies to a boundary cylinder, and quantization on that cylinder turns CFT dimensions into energy levels.](/figures/course/global-ads-cylinder.svg)

<figcaption>

Global AdS is naturally adapted to the CFT Hilbert space on $\mathbb R_t\times S^{d-1}$. After conformal compactification, the boundary cylinder supplies the spacetime on which the CFT is quantized. The spectrum of $H_{\rm cyl}$ is the spectrum of the dilatation operator in radial quantization, so primary dimensions and descendant levels appear as global-AdS energies.

</figcaption>
</figure>

## Why this matters

Poincaré coordinates are often the first coordinates used in practical AdS/CFT computations because they make the flat boundary $\mathbb R^{1,d-1}$ manifest. Global coordinates are equally fundamental, and in some ways more conceptual. They describe the full AdS spacetime, not just a patch, and their boundary is the natural home of radial quantization.

The dictionary we want is

$$
\text{global AdS vacuum}
\quad\longleftrightarrow\quad
\text{CFT vacuum on }\mathbb R_t\times S^{d-1}.
$$

A normalizable excitation of a bulk field in global AdS is a state in the CFT Hilbert space. A non-normalizable deformation of the boundary behavior is a source in the CFT Lagrangian or Hamiltonian. This distinction between states and sources is already present here, before we do holographic renormalization in detail.

Global AdS is also the right setting for several later topics:

| Question | Why global AdS is natural |
|---|---|
| What is the CFT spectrum? | Global energies are cylinder energies. |
| What state is dual to empty AdS? | The CFT vacuum on $S^{d-1}$. |
| What is a bulk one-particle state? | A normalizable global mode. |
| What is the Hawking–Page transition? | A competition between thermal AdS and global AdS black holes. |
| How do operator dimensions become bulk masses? | The lowest global frequency is fixed by $\Delta$. |

The point is not that global coordinates are always computationally easiest. The point is that they expose the Hilbert-space meaning of the duality.

## Global coordinates

Recall the embedding-space definition of $\mathrm{AdS}_{d+1}$ as the hyperboloid

$$
-X_{-1}^2-X_0^2+X_1^2+\cdots+X_d^2=-L^2
$$

inside $\mathbb R^{2,d}$ with metric

$$
ds_{\mathbb R^{2,d}}^2
=
-dX_{-1}^2-dX_0^2+dX_1^2+\cdots+dX_d^2.
$$

A convenient global parametrization is

$$
X_{-1}=L\cosh\rho\cos\tau,
\qquad
X_0=L\cosh\rho\sin\tau,
$$

$$
X_i=L\sinh\rho\, n_i,
\qquad
\sum_{i=1}^d n_i^2=1,
$$

where $n_i$ are coordinates on a unit $S^{d-1}$. The induced metric is

$$
ds^2
=
L^2\left(
-\cosh^2\rho\,d\tau^2+d\rho^2+
\sinh^2\rho\,d\Omega_{d-1}^2
\right),
$$

with

$$
0\leq \rho<\infty,
\qquad
\tau\in\mathbb R
$$

on the universal cover.

The word “universal cover” matters. The hyperboloid itself has $\tau$ periodic with period $2\pi$, which would produce closed timelike curves. The physical spacetime called global AdS is the universal covering spacetime, where $\tau$ is unwrapped:

$$
\tau\sim \tau+2\pi
\quad\text{is not imposed.}
$$

The dimensionful global time is usually written

$$
t=L\tau.
$$

With this convention, the same metric becomes

$$
ds^2
=
-
\cosh^2\rho\,dt^2
+
L^2d\rho^2
+
L^2\sinh^2\rho\,d\Omega_{d-1}^2.
$$

Equivalently, if we define

$$
r=L\sinh\rho,
$$

then

$$
ds^2
=
-
\left(1+\frac{r^2}{L^2}\right)dt^2
+
\frac{dr^2}{1+r^2/L^2}
+
r^2d\Omega_{d-1}^2.
$$

This is the most common Schwarzschild-like form of global AdS.

## Compactifying the radial coordinate

The conformal boundary sits at $\rho\to\infty$, or equivalently $r\to\infty$. To see its shape, introduce a compact radial coordinate $\chi$ by

$$
\tan\chi=\sinh\rho,
\qquad
0\leq \chi<\frac{\pi}{2}.
$$

Then

$$
\cosh\rho=\sec\chi,
\qquad
d\rho=\sec\chi\,d\chi,
\qquad
\sinh\rho=\tan\chi.
$$

Substituting into the metric gives

$$
ds^2
=
\frac{L^2}{\cos^2\chi}
\left(
-d\tau^2+d\chi^2+
\sin^2\chi\,d\Omega_{d-1}^2
\right).
$$

Now the boundary is at finite coordinate position

$$
\chi=\frac{\pi}{2}.
$$

The physical metric $g$ diverges there, but the compactified metric

$$
\bar g = \frac{\cos^2\chi}{L^2}g
$$

is finite:

$$
d\bar s^2
=
-d\tau^2+d\chi^2+
\sin^2\chi\,d\Omega_{d-1}^2.
$$

Restricting to the boundary $\chi=\pi/2$ gives

$$
d\bar s^2_{\partial}
=
-d\tau^2+d\Omega_{d-1}^2.
$$

In dimensionful time $t=L\tau$, this is equivalently

$$
ds^2_{\partial}
\sim
-dt^2+L^2d\Omega_{d-1}^2.
$$

The symbol $\sim$ is deliberate: this is a representative of the boundary conformal class, not an intrinsically preferred metric. Choosing this representative is called choosing the **global conformal frame**.

So the boundary of global AdS is

$$
\partial \mathrm{AdS}_{d+1}
\cong
\mathbb R_t\times S^{d-1}.
$$

This is the CFT cylinder.

## The CFT cylinder from radial quantization

On the CFT side, the same cylinder appears from radial quantization. In Euclidean flat space, write

$$
x^\mu=r n^\mu,
\qquad
n^\mu n_\mu=1,
\qquad
r=e^\tau.
$$

Then

$$
ds^2_{\mathbb R^d}
=
dr^2+r^2d\Omega_{d-1}^2
=
e^{2\tau}\left(d\tau^2+d\Omega_{d-1}^2\right).
$$

A CFT is insensitive, up to anomaly subtleties, to Weyl rescaling of the background metric. Therefore Euclidean flat space with the origin removed is conformally equivalent to a cylinder:

$$
\mathbb R^d\setminus\{0\}
\simeq
\mathbb R_\tau\times S^{d-1}.
$$

The Euclidean radial coordinate $\tau=\log r$ becomes Euclidean cylinder time. After analytic continuation to Lorentzian time, the CFT is quantized on spatial spheres $S^{d-1}$.

The generator of translations in $\tau$ is the dilatation operator $D$. If the sphere has radius $L$, the dimensionful Hamiltonian is

$$
H_{\mathrm{cyl}}=\frac{D}{L}.
$$

A primary operator $\mathcal O$ of scaling dimension $\Delta$ creates a state

$$
|\mathcal O\rangle=\mathcal O(0)|0\rangle
$$

with cylinder energy

$$
H_{\mathrm{cyl}}|\mathcal O\rangle
=
\frac{\Delta}{L}|\mathcal O\rangle.
$$

Descendants are produced by acting with momentum generators $P_\mu$:

$$
P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle,
$$

and have energies shifted upward by integers:

$$
E L = \Delta+n.
$$

This is why global AdS is the natural bulk description of the CFT Hilbert space. In global time, energy is dimensionless when measured in units of $1/L$, and that dimensionless energy is the CFT scaling dimension plus descendant level.

## The basic Hilbert-space dictionary

The global AdS/cylinder dictionary begins as follows.

| Bulk global AdS | Boundary CFT on the cylinder |
|---|---|
| global time $t$ | cylinder time $t$ |
| time translations | Hamiltonian $H_{\mathrm{cyl}}=D/L$ |
| pure global AdS | CFT vacuum on $S^{d-1}$ |
| normalizable bulk mode | CFT state |
| lowest normal mode | primary state |
| higher normal modes | descendants and multiparticle states |
| angular momentum on $S^{d-1}$ | $SO(d)$ spin/representation |
| non-normalizable boundary behavior | source deformation |
| global AdS black hole | thermal state on $S^{d-1}$ |

The entry “pure global AdS equals the CFT vacuum” is more subtle than it first appears. The vacuum energy on the cylinder may be nonzero because a CFT on a compact spatial sphere can have Casimir energy. In the bulk, this is captured by the renormalized gravitational stress tensor and by the convention used for the zero of energy. What is invariant is the state identification: pure global AdS represents the vacuum state in the global conformal frame.

## Scalar modes in global AdS

The cleanest calculation showing how cylinder energies appear is the normal-mode spectrum of a free scalar field in global AdS.

Consider a scalar of mass $m$ satisfying

$$
(\nabla^2-m^2)\phi=0.
$$

Using compact global coordinates,

$$
ds^2
=
\frac{L^2}{\cos^2\chi}
\left(
-d\tau^2+d\chi^2+
\sin^2\chi\,d\Omega_{d-1}^2
\right),
$$

separate variables as

$$
\phi(\tau,\chi,\Omega)
=
e^{-i\Omega\tau}Y_{\ell m}(\Omega)f_{\Omega\ell}(\chi),
$$

where

$$
\nabla^2_{S^{d-1}}Y_{\ell m}
=
-
\ell(\ell+d-2)Y_{\ell m}.
$$

The radial equation is

$$
\frac{1}{\tan^{d-1}\chi}
\partial_\chi
\left(
\tan^{d-1}\chi\,\partial_\chi f
\right)
+
\left[
\Omega^2
-
\frac{\ell(\ell+d-2)}{\sin^2\chi}
-
\frac{m^2L^2}{\cos^2\chi}
\right]f=0.
$$

There are two physical requirements.

First, the solution should be regular at the center $\chi=0$. Since the sphere shrinks smoothly there, regularity requires

$$
f(\chi)\sim \chi^\ell
\qquad
\text{as }\chi\to 0.
$$

Second, for a state rather than a source deformation, the solution should be normalizable at the boundary. Near $\chi=\pi/2$, the scalar behaves as

$$
f(\chi)
\sim
(\cos\chi)^{\Delta_-}A
+
(\cos\chi)^{\Delta_+}B,
$$

where

$$
\Delta_\pm
=
\frac d2\pm\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

In standard quantization,

$$
\Delta=\Delta_+,
$$

and the normalizable behavior is

$$
f(\chi)\sim (\cos\chi)^\Delta.
$$

Solving the radial equation with regularity at the center and normalizability at the boundary quantizes the frequency:

$$
\Omega_{n\ell}
=
\Delta+2n+\ell,
\qquad
n=0,1,2,\ldots,
\qquad
\ell=0,1,2,\ldots.
$$

Restoring dimensionful time $t=L\tau$, the physical energy is

$$
E_{n\ell}=\frac{\Omega_{n\ell}}{L}
=
\frac{\Delta+2n+\ell}{L}.
$$

This formula is one of the most concrete versions of the state-operator map in AdS/CFT:

$$
\boxed{
\text{bulk normal mode energy}
\quad\longleftrightarrow\quad
\text{CFT cylinder energy}
}
$$

or

$$
\boxed{
E L
\quad\longleftrightarrow\quad
\Delta+\text{descendant level}.
}
$$

The lowest scalar mode has

$$
n=0,
\qquad
\ell=0,
\qquad
\Omega=\Delta,
\qquad
E L=\Delta.
$$

It is dual to the primary state $|\mathcal O\rangle$. The higher modes are dual to descendants of $\mathcal O$, organized by angular momentum on the sphere and additional radial excitation number.

## Why the spectrum is discrete

A common surprise is that global AdS has discrete normal modes, while Poincaré AdS often leads to continuous momentum labels.

The reason is simple. The CFT on $\mathbb R_t\times S^{d-1}$ lives in finite spatial volume. Its energy spectrum is discrete in any unitary theory with a well-defined Hilbert space and compact spatial slices. The bulk knows this because global AdS behaves like a gravitational box. A light ray sent from the center reaches the conformal boundary and returns in finite global time, once reflecting boundary conditions are imposed.

This “box” property does not mean that the boundary is a material wall. It means that asymptotically AdS boundary conditions are part of the definition of the gravitational problem. In the dual CFT, those boundary conditions specify the sources and the state in the cylinder frame.

## Relation to the Poincaré patch

Poincaré AdS is not a different spacetime. It is a patch of global AdS. Its boundary is a conformal patch of the global cylinder.

The boundary cylinder metric can be written as

$$
ds^2_{\mathrm{cyl}}
=
-d\tau^2+d\theta^2+
\sin^2\theta\,d\Omega_{d-2}^2.
$$

Flat Minkowski space in polar coordinates,

$$
ds^2_{\mathrm{Mink}}
=
-dt_M^2+dr_M^2+r_M^2d\Omega_{d-2}^2,
$$

is conformal to a patch of the cylinder through

$$
t_M
=
\frac{\sin\tau}{\cos\tau+\cos\theta},
\qquad
r_M
=
\frac{\sin\theta}{\cos\tau+\cos\theta}.
$$

One finds

$$
ds^2_{\mathrm{Mink}}
=
\frac{1}{(\cos\tau+\cos\theta)^2}
\left(
-d\tau^2+d\theta^2+
\sin^2\theta\,d\Omega_{d-2}^2
\right).
$$

Thus the flat-space CFT and the cylinder CFT are related by a conformal transformation, but the global questions they make manifest are different. Poincaré coordinates are adapted to momenta on $\mathbb R^{1,d-1}$. Global coordinates are adapted to the spectrum on $S^{d-1}$.

This distinction matters in holography. The Poincaré vacuum is usually the same local conformal vacuum, viewed in a different conformal frame, but the Poincaré patch does not cover the entire global bulk. A bulk point outside the Poincaré patch is not absent from the theory; it is absent from that coordinate description.

## States versus sources in global language

Global AdS gives a useful way to separate two roles played by bulk fields.

A **normalizable mode** has no source turned on at the boundary. It changes the state. For a scalar in standard quantization, the leading source coefficient vanishes and the subleading response coefficient is nonzero.

A **non-normalizable mode** changes the boundary condition. It corresponds to adding a source term to the CFT:

$$
\delta S_{\mathrm{CFT}}
=
\int_{\mathbb R_t\times S^{d-1}} d^dx\sqrt{-g_{(0)}}\,J(x)\mathcal O(x).
$$

This distinction is the global version of the same source-response structure used in Poincaré coordinates. The details become precise only after holographic renormalization, but the conceptual separation is already visible:

$$
\text{normalizable data}
\quad\longleftrightarrow\quad
\text{state},
$$

$$
\text{non-normalizable data}
\quad\longleftrightarrow\quad
\text{source}.
$$

## The vacuum and Casimir energy

The vacuum of a CFT on $\mathbb R_t\times S^{d-1}$ is not identical in presentation to the vacuum on flat Minkowski space. A conformal transformation relates the two local descriptions, but the cylinder has a compact spatial sphere and a Hamiltonian with a discrete spectrum.

For many CFTs, the cylinder vacuum has a Casimir energy. In holography, pure global AdS can reproduce this vacuum energy after one defines the renormalized Brown–York stress tensor with the appropriate counterterms. The exact numerical value depends on the theory, the dimension, and the normalization conventions. The important foundational point for this page is the state identification:

$$
|0\rangle_{\mathrm{cyl}}
\quad\longleftrightarrow\quad
\text{global AdS}.
$$

Later, when we study thermal AdS and the Hawking–Page transition, we will see how this same cylinder frame makes finite-volume thermodynamics geometrically transparent.

## Dictionary checkpoint

Global AdS teaches the first Hilbert-space version of the holographic dictionary:

$$
\boxed{
\text{CFT on }\mathbb R_t\times S^{d-1}
\quad\longleftrightarrow\quad
\text{bulk theory in global AdS}
}
$$

with

$$
\boxed{
H_{\mathrm{cyl}}=\frac{D}{L}
}
$$

and

$$
\boxed{
E_{\mathrm{bulk}}L=E_{\mathrm{cyl}}L=\Delta+\text{integer descendant level}.
}
$$

For a scalar field of mass $m$,

$$
\boxed{
\Delta(\Delta-d)=m^2L^2
}
$$

and its global normal frequencies are

$$
\boxed{
E_{n\ell}L=\Omega_{n\ell}=\Delta+2n+\ell.
}
$$

The lowest mode is the primary. The rest of the tower is the bulk reflection of descendants and spherical harmonics in the boundary Hilbert space.

## Common confusions

### “The global AdS boundary is an ordinary cylinder at finite distance.”

It is a conformal boundary, not a material cylinder at finite physical distance. The compactified metric places it at finite coordinate location, but the physical AdS metric has infinite proper distance to the boundary along spatial slices.

### “The original AdS hyperboloid already has a good global time.”

The embedded hyperboloid has periodic global time and therefore closed timelike curves. The physical spacetime used in AdS/CFT is the universal cover, where global time is unwrapped.

### “Poincaré AdS and global AdS are different dualities.”

They are different coordinate/conformal-frame descriptions of the same local AdS/CFT structure. Poincaré coordinates cover only part of global AdS and make the flat boundary frame manifest. Global coordinates cover the whole spacetime and make the cylinder Hilbert space manifest.

### “The boundary sphere radius is a new physical coupling.”

For a CFT, changing the overall radius of $S^{d-1}$ is a Weyl rescaling, apart from anomaly and scheme subtleties. The radius $L$ sets the units in which cylinder energies are measured. The dimensionless combination is $EL$.

### “Every global-AdS mode is a primary.”

No. The lowest mode associated with a bulk field corresponds to a primary operator. Higher normal modes correspond to descendants and, in interacting theories, to more complicated mixtures with multiparticle states. The primary/descendant organization is exact in the CFT; the bulk mode language is simplest in the large-$N$ weakly coupled bulk limit.

### “The radial coordinate in global AdS is just the flat-space radius of radial quantization.”

No. The CFT radial coordinate $r=e^\tau$ becomes Euclidean cylinder time. The bulk radial coordinate $\rho$ is a separate emergent geometric coordinate. Both are related to scale in different ways, but they should not be identified literally.

## Exercises

### Exercise 1: Derive the boundary cylinder

Starting from

$$
ds^2
=
\frac{L^2}{\cos^2\chi}
\left(
-d\tau^2+d\chi^2+\sin^2\chi\,d\Omega_{d-1}^2
\right),
$$

show that the conformal boundary metric in the global frame is

$$
d\bar s^2_{\partial}=-d\tau^2+d\Omega_{d-1}^2.
$$

<details>
<summary><strong>Solution</strong></summary>

The metric diverges as $\chi\to \pi/2$ because of the factor $L^2/\cos^2\chi$. Multiply by the defining function

$$
\Omega^2=\frac{\cos^2\chi}{L^2}.
$$

The compactified metric is

$$
d\bar s^2
=
-d\tau^2+d\chi^2+\sin^2\chi\,d\Omega_{d-1}^2.
$$

Restricting this metric to the boundary means setting $\chi=\pi/2$ and dropping the normal direction $d\chi$. Since $\sin(\pi/2)=1$,

$$
d\bar s^2_{\partial}
=
-d\tau^2+d\Omega_{d-1}^2.
$$

This is the metric on $\mathbb R_\tau\times S^{d-1}$ with a unit-radius sphere.

</details>

### Exercise 2: Energy from scaling dimension

A primary operator $\mathcal O$ has scaling dimension $\Delta$. If the CFT is placed on a sphere of radius $L$, what is the energy of the corresponding primary state on the cylinder?

<details>
<summary><strong>Solution</strong></summary>

Radial quantization identifies the cylinder Hamiltonian with the dilatation operator measured in units of the sphere radius:

$$
H_{\mathrm{cyl}}=\frac{D}{L}.
$$

For a primary state,

$$
D|\mathcal O\rangle=\Delta|\mathcal O\rangle.
$$

Therefore

$$
H_{\mathrm{cyl}}|\mathcal O\rangle
=
\frac{\Delta}{L}|\mathcal O\rangle.
$$

The cylinder energy is

$$
E=\frac{\Delta}{L},
\qquad
EL=\Delta.
$$

</details>

### Exercise 3: Massless scalar in global $\mathrm{AdS}_5$

For a massless scalar in $\mathrm{AdS}_5$, take $d=4$ and $m^2=0$. In standard quantization, what is $\Delta$? What is the lowest global frequency?

<details>
<summary><strong>Solution</strong></summary>

The mass-dimension relation is

$$
m^2L^2=\Delta(\Delta-d).
$$

For $d=4$ and $m^2=0$,

$$
0=\Delta(\Delta-4),
$$

so

$$
\Delta=0
\quad\text{or}\quad
\Delta=4.
$$

In standard quantization we choose the larger root,

$$
\Delta=4.
$$

The normal-mode spectrum is

$$
E_{n\ell}L=\Omega_{n\ell}=\Delta+2n+\ell.
$$

The lowest mode has $n=0$ and $\ell=0$, hence

$$
E L=4.
$$

In dimensionful units,

$$
E=\frac{4}{L}.
$$

</details>

### Exercise 4: Descendant levels from global modes

A scalar primary has dimension $\Delta$. A global scalar mode has quantum numbers $n$ and $\ell$, with

$$
E_{n\ell}L=\Omega_{n\ell}=\Delta+2n+\ell.
$$

What descendant level does this mode correspond to?

<details>
<summary><strong>Solution</strong></summary>

In radial quantization, each action of a momentum generator $P_\mu$ raises the cylinder energy by one unit. A descendant at level $k$ has

$$
EL=\Delta+k.
$$

The global mode has

$$
EL=E_{n\ell}L=\Omega_{n\ell}=\Delta+2n+\ell.
$$

Therefore it lies at descendant level

$$
k=2n+\ell.
$$

The angular momentum $\ell$ records how the descendant transforms under rotations on $S^{d-1}$, while the radial quantum number $n$ counts additional excitation compatible with that angular momentum.

</details>

### Exercise 5: Why is the spectrum discrete?

Give both the boundary and bulk explanations for the discreteness of the global-AdS normal-mode spectrum.

<details>
<summary><strong>Solution</strong></summary>

On the boundary, the CFT is quantized on $S^{d-1}$, a compact spatial manifold. The Hamiltonian spectrum on a compact space is discrete under ordinary assumptions about a well-defined unitary QFT.

In the bulk, global AdS behaves like a box. Spatial slices are effectively finite after conformal compactification, and asymptotically AdS boundary conditions reflect excitations. Regularity at the center and normalizability at the boundary turn the radial wave equation into an eigenvalue problem with discrete frequencies.

These are two descriptions of the same fact:

$$
\text{discrete CFT cylinder spectrum}
\quad\longleftrightarrow\quad
\text{discrete global-AdS normal modes}.
$$

</details>

## Further reading

- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150). The foundational boundary-value formulation of AdS/CFT observables.
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111). The standard review, including the global and thermal viewpoints.
- V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de-Sitter Gravity](https://arxiv.org/abs/hep-th/9902121). Useful for understanding the renormalized boundary stress tensor and the vacuum energy of global AdS.
- S. Rychkov, [EPFL Lectures on Conformal Field Theory in $D\geq 3$ Dimensions](https://arxiv.org/abs/1601.05000). A clear introduction to radial quantization and the state-operator correspondence.
- D. Simmons-Duffin, [TASI Lectures on the Conformal Bootstrap](https://arxiv.org/abs/1602.07982). A modern CFT reference with a careful treatment of radial quantization, primaries, descendants, and conformal multiplets.
