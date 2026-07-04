---
title: "Modular Invariance and the Cardy Formula"
description: "Torus partition functions, modular transformations, characters, Cardy growth, and the CFT side of black-hole entropy."
sidebar:
  order: 2
---

## Goal

The previous page explained minimal models as exact Virasoro CFTs with finitely many primary fields. This page moves from the plane to the **torus**. That move is much more than a change of background geometry. On the plane, conformal symmetry constrains local correlators. On the torus, the same theory must also be consistent under large diffeomorphisms of the surface. This extra consistency condition is **modular invariance**.

For AdS/CFT preparation, modular invariance matters for three reasons.

First, the torus partition function is a thermal trace. It encodes the spectrum of the CFT on a circle:

$$
Z(\tau,\bar\tau)
=
\operatorname{Tr}_{\mathcal H}
q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24}.
$$

Second, modular invariance relates low temperature to high temperature. In two-dimensional CFT, this turns the vacuum contribution at low temperature into universal high-energy information. That is the origin of the **Cardy formula**.

Third, in AdS$_3$/CFT$_2$, the Cardy formula is the CFT mechanism behind the entropy of BTZ black holes. On the gravity side, different bulk fillings of the same boundary torus are related by modular transformations. On the CFT side, the same modular transformations reorganize the thermal trace.

The main chain of ideas is therefore

$$
\text{torus geometry}
\quad\Longrightarrow\quad
SL(2,\mathbb Z)
\quad\Longrightarrow\quad
Z(\tau,\bar\tau)=Z\!\left(\frac{a\tau+b}{c\tau+d},\frac{a\bar\tau+b}{c\bar\tau+d}\right)
\quad\Longrightarrow\quad
\rho(E)\sim e^{S_{\rm Cardy}}.
$$

## The torus and its modular parameter

A complex torus is obtained by quotienting the complex plane by a lattice:

$$
\mathbb T^2_\tau
=
\mathbb C/(\mathbb Z+\tau\mathbb Z),
\qquad
\tau=\tau_1+i\tau_2,
\qquad
\tau_2>0.
$$

The coordinate $z\in\mathbb C$ is identified as

$$
z\sim z+1,
\qquad
z\sim z+\tau.
$$

The two lattice vectors $1$ and $\tau$ define two independent cycles. A choice of cycles is a choice of basis for the lattice, not an intrinsic physical datum. A different primitive basis of the same lattice is

$$
\begin{pmatrix}
1'\\ \tau'
\end{pmatrix}
=
\begin{pmatrix}
d & c\\ b & a
\end{pmatrix}
\begin{pmatrix}
1\\ \tau
\end{pmatrix},
\qquad
ad-bc=1,
\qquad
a,b,c,d\in\mathbb Z.
$$

After rescaling the new first basis vector to $1$, the same torus is described by

$$
\boxed{
\tau\mapsto \gamma\tau
=
\frac{a\tau+b}{c\tau+d},
\qquad
\gamma=\begin{pmatrix}a&b\\ c&d\end{pmatrix}\in SL(2,\mathbb Z).
}
$$

The two standard generators are

$$
T: \tau\mapsto \tau+1,
\qquad
S: \tau\mapsto -\frac{1}{\tau}.
$$

The $T$ transformation shifts one cycle by the other. The $S$ transformation exchanges the two cycles, up to orientation. In thermal language, $S$ exchanges the Euclidean time circle and the spatial circle. This is the deep reason that modular invariance knows about high-temperature physics.

<figure class="doc-figure" style="--figure-width: 34rem; --caption-width: 52rem;">

![The modular fundamental domain in the upper half-plane.](/figures/cft/modular-invariance-fundamental-domain.svg)

<figcaption>

The modular group $SL(2,\mathbb Z)$ acts on the upper half-plane by $\tau\mapsto (a\tau+b)/(c\tau+d)$. The shaded region $\mathcal F$ is a standard fundamental domain, bounded by $|\tau|=1$ and $|\tau_1|=1/2$. The generators $S$ and $T$ identify equivalent descriptions of the same torus.

</figcaption>
</figure>

A convenient fundamental domain is

$$
\mathcal F
=
\left\{
\tau\in\mathbb H:
|\tau|\geq 1,
\quad
-\frac12\leq \operatorname{Re}\tau\leq \frac12
\right\},
$$

with the usual boundary identifications. Integrating over tori in string theory means integrating over this fundamental domain, not over the whole upper half-plane. Otherwise one overcounts the same geometry infinitely many times.

## Torus partition function as a thermal trace

Quantize the CFT on a spatial circle of circumference $2\pi$. Let $\sigma\sim\sigma+2\pi$ be the spatial coordinate and $t_E$ Euclidean time. A rectangular thermal torus has

$$
t_E\sim t_E+\beta.
$$

More generally, one may include an angular potential $\theta$ so that the thermal identification is accompanied by a spatial translation:

$$
(\sigma,t_E)\sim(\sigma+\theta,t_E+\beta).
$$

The corresponding modular parameter is

$$
\boxed{
\tau=\frac{\theta+i\beta}{2\pi}.
}
$$

The cylinder Hamiltonian and momentum are

$$
H=L_0+\bar L_0-\frac{c+\bar c}{24},
\qquad
P=L_0-\bar L_0-\frac{c-\bar c}{24}.
$$

For a non-anomalous theory with $c=\bar c$, this reduces to

$$
H=L_0+\bar L_0-\frac{c}{12},
\qquad
P=L_0-\bar L_0.
$$

The torus partition function is therefore

$$
Z(\beta,\theta)
=
\operatorname{Tr}_{\mathcal H}
\exp(-\beta H+i\theta P).
$$

In terms of

$$
q=e^{2\pi i\tau},
\qquad
\bar q=e^{-2\pi i\bar\tau},
$$

this becomes

$$
\boxed{
Z(\tau,\bar\tau)
=
\operatorname{Tr}_{\mathcal H}
q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24}.
}
$$

The shifts by $c/24$ and $\bar c/24$ are not decoration. They are the Casimir-energy shifts caused by the conformal map from the plane to the cylinder. Equivalently, they are the vacuum energies on the circle:

$$
E_{\rm vac}
=-\frac{c+\bar c}{24}.
$$

For a CFT with $c=\bar c$ on a circle of circumference $2\pi$, this is

$$
E_{\rm vac}=-\frac{c}{12}.
$$

This vacuum energy is the seed of the Cardy formula. The high-energy density of states is controlled by the low-temperature vacuum because modular invariance exchanges the two regimes.

## What modular invariance says

For a bosonic, non-anomalous, compact CFT, the torus partition function is invariant under the modular group:

$$
\boxed{
Z(\tau,\bar\tau)
=
Z\!\left(\frac{a\tau+b}{c\tau+d},\frac{a\bar\tau+b}{c\bar\tau+d}\right),
\qquad
\begin{pmatrix}a&b\\ c&d\end{pmatrix}\in SL(2,\mathbb Z).
}
$$

Equivalently, it is enough to impose invariance under the two generators:

$$
Z(\tau+1,\bar\tau+1)=Z(\tau,\bar\tau),
$$

and

$$
Z\!\left(-\frac1\tau,-\frac1{\bar\tau}\right)=Z(\tau,\bar\tau).
$$

There are important refinements.

For fermionic theories, one must specify spin structures on the torus. Individual spin-structure partition functions usually transform into one another under $SL(2,\mathbb Z)$. A modular-invariant object is obtained only after choosing a consistent sum or projection.

For chiral theories, or theories with $c-\bar c\neq0$, the partition function can transform with phases. This is a gravitational anomaly. In such cases one should speak of modular covariance rather than ordinary modular invariance.

For noncompact CFTs, the spectrum may include continuous components and the partition function may require infrared regularization. Modular invariance remains meaningful, but the trace formula must be handled carefully.

For the rest of this page, unless stated otherwise, assume a compact non-anomalous CFT with a discrete spectrum and a unique vacuum.

## Characters and rational CFT

The torus trace organizes the Hilbert space by representations of the left and right chiral algebras. If the chiral algebra is just Virasoro, a representation is a Virasoro module. If the theory has an affine Lie algebra, a superconformal algebra, or a larger rational chiral algebra, one uses representations of that larger algebra.

For a chiral representation $\mathcal V_i$, define the character

$$
\chi_i(\tau)
=
\operatorname{Tr}_{\mathcal V_i}
q^{L_0-c/24}.
$$

If the theory is rational, only finitely many irreducible chiral representations occur. The Hilbert space decomposes as

$$
\mathcal H
=
\bigoplus_{i,j} M_{ij}\,\mathcal V_i\otimes \bar{\mathcal V}_j,
\qquad
M_{ij}\in\mathbb Z_{\geq0}.
$$

Then

$$
\boxed{
Z(\tau,\bar\tau)
=
\sum_{i,j}M_{ij}\,\chi_i(\tau)\bar\chi_j(\bar\tau).
}
$$

The characters form a finite-dimensional representation of the modular group:

$$
\chi_i\!\left(-\frac1\tau\right)
=
\sum_j S_{ij}\chi_j(\tau),
$$

and

$$
\chi_i(\tau+1)
=
\sum_j T_{ij}\chi_j(\tau).
$$

For many rational theories, $T$ is diagonal:

$$
T_{ij}
=
\delta_{ij}\exp\!\left[2\pi i\left(h_i-\frac{c}{24}\right)\right].
$$

Modular invariance of $Z$ becomes an arithmetic constraint on the nonnegative integer matrix $M$:

$$
\boxed{
S^\dagger M S=M,
\qquad
T^\dagger M T=M.
}
$$

This is an unexpectedly strong condition. It says that a CFT spectrum is not an arbitrary list of left and right representations. The left and right sectors must be paired so that the full torus path integral is invariant under large diffeomorphisms.

The simplest modular invariant is the diagonal invariant

$$
Z_{\rm diag}(\tau,\bar\tau)
=
\sum_i |\chi_i(\tau)|^2,
$$

when the representation labels can be paired with their conjugates in the obvious way. Minimal models, WZW models, and coset models provide many nontrivial examples in which the modular-invariant matrix $M$ is not simply the identity.

A famous bonus is the Verlinde formula. In rational CFT, the same modular $S$ matrix diagonalizes fusion:

$$
\boxed{
N_{ij}^{\;k}
=
\sum_m
\frac{S_{im}S_{jm}S^*_{km}}{S_{0m}}.
}
$$

Here $N_{ij}^{\;k}$ are the fusion coefficients in

$$
\phi_i\times\phi_j\sim\sum_k N_{ij}^{\;k}\phi_k.
$$

This is one of the cleanest places where geometry, representation theory, and operator algebra meet. Modular transformations of the torus know the fusion rules on the sphere.



## Example: the Ising modular invariant

The critical Ising CFT is the smallest useful example. It has

$$
c=\frac12,
$$

and three Virasoro primaries:

$$
\mathbf 1:\ h=0,
\qquad
\epsilon:\ h=\frac12,
\qquad
\sigma:\ h=\frac1{16}.
$$

The diagonal modular invariant is

$$
\boxed{
Z_{\rm Ising}
=
|\chi_{0}|^2+|\chi_{1/2}|^2+|\chi_{1/16}|^2.
}
$$

The modular $S$ matrix in the ordered basis $(\mathbf 1,\epsilon,\sigma)$ is

$$
S_{\rm Ising}
=
\frac12
\begin{pmatrix}
1&1&\sqrt2\\
1&1&-\sqrt2\\
\sqrt2&-\sqrt2&0
\end{pmatrix}.
$$

Because this matrix is real and unitary, the diagonal sum of absolute squares is invariant under $S$. The $T$ transformation is diagonal in the character basis, and the diagonal pairing of each left representation with the same right representation gives integer spin:

$$
h-\bar h=0.
$$

So the Ising torus partition function is modular invariant. This example is small enough that one can see the whole logic explicitly: the Kac table gives the allowed Virasoro representations, the characters package descendants, and modular invariance tells us how left and right sectors may be glued into a consistent local CFT.

## Modular $T$: spin integrality

The $T$ transformation is the easiest modular constraint to interpret. Under $\tau\mapsto\tau+1$,

$$
q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24}
\mapsto
\exp\!\left[2\pi i\left(L_0-\bar L_0-\frac{c-\bar c}{24}\right)\right]
q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24}.
$$

If $c=\bar c$, modular $T$ invariance requires

$$
L_0-\bar L_0\in\mathbb Z
$$

for all states appearing in the bosonic torus partition function. This is just integer spin. It is the torus version of locality: taking one operator around another should not produce an arbitrary phase in a purely bosonic local CFT.

If $c-\bar c\neq0$, there is an additional phase. A purely chiral CFT can still be mathematically consistent, but its partition function is not an ordinary modular-invariant scalar. In physical terms, it carries a gravitational anomaly.

## Modular $S$: low temperature becomes high temperature

The $S$ transformation is where the physics becomes dramatic. Consider the rectangular torus

$$
\tau=\frac{i\beta}{2\pi},
\qquad
\theta=0.
$$

Then

$$
S:\tau\mapsto -\frac1\tau
=\frac{2\pi i}{\beta}.
$$

The transformed torus is again rectangular, with inverse temperature

$$
\boxed{
\beta'=\frac{4\pi^2}{\beta}.
}
$$

Thus modular invariance implies

$$
\boxed{
Z(\beta)=Z\!\left(\frac{4\pi^2}{\beta}\right).
}
$$

This is high-temperature/low-temperature duality. If $\beta\to0$, then $\beta'=4\pi^2/\beta\to\infty$. The high-temperature partition function is determined by the low-temperature theory.

At low temperature, a compact unitary CFT with a unique vacuum is dominated by the vacuum state. The vacuum has

$$
L_0=0,
\qquad
\bar L_0=0,
$$

on the plane, and hence cylinder energy

$$
E_{\rm vac}
=-\frac{c+\bar c}{24}.
$$

Therefore, for large $\beta$,

$$
Z(\beta)
\sim
\exp\!\left[\frac{\beta(c+\bar c)}{24}\right].
$$

Using modular $S$, the small-$\beta$ behavior is

$$
Z(\beta)
=
Z\!\left(\frac{4\pi^2}{\beta}\right)
\sim
\exp\!\left[
\frac{\pi^2(c+\bar c)}{6\beta}
\right].
$$

For $c=\bar c$, this is

$$
\boxed{
\log Z(\beta)
\sim
\frac{\pi^2 c}{3\beta},
\qquad
\beta\to0.
}
$$

This is universal. It does not require a Lagrangian, weak coupling, free fields, or a large-$c$ limit. It only requires the assumptions stated above.

## Cardy formula: density of states

The partition function is a Laplace transform of the density of states. The high-temperature asymptotic form of $Z(\beta)$ therefore determines the asymptotic growth of the spectrum.

It is cleanest to keep left and right movers separate. Define shifted cylinder energies

$$
E_L=h-\frac{c}{24},
\qquad
E_R=\bar h-\frac{\bar c}{24}.
$$

The vacuum has

$$
E_{L,\rm vac}=-\frac{c}{24},
\qquad
E_{R,\rm vac}=-\frac{\bar c}{24}.
$$

Introduce left and right inverse temperatures $\beta_L$ and $\beta_R$ by writing

$$
Z(\beta_L,\beta_R)
=
\operatorname{Tr}
\exp(-\beta_L E_L-\beta_R E_R).
$$

At high temperature, modular invariance gives

$$
\log Z(\beta_L,\beta_R)
\sim
\frac{\pi^2 c}{6\beta_L}
+
\frac{\pi^2\bar c}{6\beta_R}.
$$

The inverse Laplace transform is controlled by a saddle point:

$$
\rho(E_L,E_R)
\sim
\int d\beta_L d\beta_R\,
\exp\!\left[
\beta_L E_L+\beta_R E_R
+
\frac{\pi^2 c}{6\beta_L}
+
\frac{\pi^2\bar c}{6\beta_R}
\right].
$$

The saddle equations are

$$
E_L=\frac{\pi^2 c}{6\beta_L^2},
\qquad
E_R=\frac{\pi^2\bar c}{6\beta_R^2}.
$$

Thus

$$
\beta_L^*=\pi\sqrt{\frac{c}{6E_L}},
\qquad
\beta_R^*=\pi\sqrt{\frac{\bar c}{6E_R}}.
$$

Substituting back gives the Cardy entropy

$$
\boxed{
S_{\rm Cardy}(E_L,E_R)
=
\log \rho(E_L,E_R)
\sim
2\pi\sqrt{\frac{cE_L}{6}}
+
2\pi\sqrt{\frac{\bar cE_R}{6}}.
}
$$

In terms of plane conformal weights, this is

$$
\boxed{
S_{\rm Cardy}(h,\bar h)
\sim
2\pi\sqrt{\frac{c}{6}\left(h-\frac{c}{24}\right)}
+
2\pi\sqrt{\frac{\bar c}{6}\left(\bar h-\frac{\bar c}{24}\right)}.
}
$$

Many books and papers write the formula as

$$
S\sim
2\pi\sqrt{\frac{ch}{6}}
+
2\pi\sqrt{\frac{\bar c\bar h}{6}}.
$$

That form uses a slightly different convention for the energy variable, or assumes $h,\bar h\gg c,\bar c$ so the $c/24$ shifts are negligible. For holography, it is safest to remember the cylinder-energy form: the Cardy formula counts states with large positive $E_L$ and $E_R$.

For fixed scaling dimension and spin,

$$
\Delta=h+\bar h,
\qquad
J=h-\bar h,
$$

and for $c=\bar c$, the formula becomes

$$
S_{\rm Cardy}(\Delta,J)
\sim
2\pi\sqrt{
\frac{c}{12}
\left(\Delta+J-\frac{c}{12}\right)
}
+
2\pi\sqrt{
\frac{c}{12}
\left(\Delta-J-\frac{c}{12}\right)
}.
$$

For spinless states, $J=0$, this reduces to

$$
S_{\rm Cardy}(\Delta)
\sim
4\pi\sqrt{
\frac{c}{12}
\left(\Delta-\frac{c}{12}\right)
}.
$$

Again, in the strict high-energy regime $\Delta\gg c$, this is often written as

$$
S_{\rm Cardy}(\Delta)
\sim
2\pi\sqrt{\frac{c\Delta}{3}}.
$$

## The Cardy regime and the holographic regime

The Cardy formula is universal in the asymptotic high-energy regime. The most conservative statement is

$$
E_L\gg c,
\qquad
E_R\gg \bar c.
$$

In that regime the saddle is reliable and subleading details of the spectrum are washed out.

Holographic CFTs introduce an additional question. In AdS$_3$/CFT$_2$, semiclassical gravity corresponds to large central charge,

$$
c\sim \frac{\ell_{\rm AdS}}{G_N}\gg1.
$$

BTZ black holes appear at energies of order $c$, not necessarily energies much larger than $c$. To use Cardy growth already at that scale, one needs stronger assumptions, usually stated as a **sparse light spectrum** condition. Roughly, the low-energy spectrum below the black-hole threshold must not grow too quickly. Under such conditions, modular invariance makes the vacuum dominate the appropriate transformed channel and the Cardy formula extends into the semiclassical black-hole regime.

This distinction is important:

$$
\text{ordinary Cardy universality}
\quad\neq\quad
\text{large-}c\text{ holographic universality at }E\sim c.
$$

The first is a theorem-like consequence of modular invariance in the asymptotic regime. The second is a stronger statement about a special class of CFTs with a gravitational dual.

## Modular invariance and AdS$_3$ black holes

The Euclidean boundary of thermal AdS$_3$ is a torus. A bulk saddle is not just a boundary torus; it is a choice of which boundary cycle becomes contractible in the bulk.

Thermal AdS and the Euclidean BTZ black hole have the same kind of boundary torus but different contractible cycles. The modular $S$ transformation exchanges the temporal and spatial cycles, so it naturally exchanges the two dominant descriptions:

$$
\text{thermal AdS}
\quad\overset{S}{\longleftrightarrow}\quad
\text{BTZ black hole}.
$$

On the CFT side, the same statement is

$$
\text{low-temperature vacuum dominance}
\quad\overset{S}{\longleftrightarrow}\quad
\text{high-temperature Cardy growth}.
$$

This is one of the cleanest examples of the general AdS/CFT philosophy. Geometry in the bulk becomes a statement about reorganizing the boundary Hilbert-space trace.

The Brown-Henneaux central charge of pure AdS$_3$ gravity is

$$
c=\bar c=\frac{3\ell}{2G_N}.
$$

Inserting this into the Cardy formula reproduces the Bekenstein-Hawking entropy of the BTZ black hole, after matching $E_L$ and $E_R$ to the left- and right-moving combinations of the black-hole mass and angular momentum. We will revisit this in the AdS$_3$/CFT$_2$ part of the course. For now, the lesson is simple: the black-hole entropy is already latent in modular invariance of the boundary CFT.

It is worth seeing the algebra once. For a BTZ black hole with outer and inner horizon radii $r_+$ and $r_-$,

$$
M=\frac{r_+^2+r_-^2}{8G_3\ell^2},
\qquad
J=\frac{r_+r_-}{4G_3\ell}.
$$

The left- and right-moving CFT energies are

$$
E_L=\frac{\ell M+J}{2},
\qquad
E_R=\frac{\ell M-J}{2}.
$$

Substituting the BTZ charges gives

$$
E_L=\frac{(r_++r_-)^2}{16G_3\ell},
\qquad
E_R=\frac{(r_+-r_-)^2}{16G_3\ell}.
$$

Since

$$
\frac{c}{6}=\frac{\ell}{4G_3},
$$

Cardy's formula gives

$$
S_{\rm Cardy}
=
2\pi\sqrt{\frac{cE_L}{6}}
+
2\pi\sqrt{\frac{cE_R}{6}}
=
2\pi\left(\frac{r_++r_-}{8G_3}+\frac{r_+-r_-}{8G_3}\right).
$$

The $r_-$ dependence cancels:

$$
\boxed{
S_{\rm Cardy}=\frac{2\pi r_+}{4G_3}.
}
$$

This is exactly the Bekenstein-Hawking entropy,

$$
S_{\rm BH}=\frac{\operatorname{Length}(\text{horizon})}{4G_3}
=\frac{2\pi r_+}{4G_3}.
$$

## A useful dictionary

| CFT object | Torus/modular meaning | AdS$_3$ meaning |
|---|---|---|
| $\tau$ | complex structure of the boundary torus | boundary thermal/angular potentials |
| $S:\tau\mapsto-1/\tau$ | exchange of cycles | exchange of thermal AdS and BTZ channels |
| $c/24$ | cylinder Casimir shift | global AdS vacuum energy |
| $Z(\tau,\bar\tau)$ | thermal trace over CFT states | gravitational path integral with torus boundary |
| Cardy growth | universal high-energy density of states | Bekenstein-Hawking entropy of BTZ black holes |
| sparse light spectrum | vacuum dominance after modular transform | semiclassical gravity regime |

## Common pitfalls

The first pitfall is forgetting the $c/24$ shift. The trace is not $\operatorname{Tr}q^{L_0}\bar q^{\bar L_0}$. The cylinder vacuum energy is essential.

The second pitfall is confusing local conformal transformations with modular transformations. Virasoro symmetry acts locally on the worldsheet. Modular transformations are large diffeomorphisms of the torus. Both are crucial in 2D CFT, but they are conceptually different.

The third pitfall is treating every modular-covariant object as modular invariant. Characters transform among themselves. Individual spin-structure partition functions transform among themselves. The full physical partition function is invariant only after the correct pairing or summation.

The fourth pitfall is applying the Cardy formula outside its regime. At fixed small $c$, it is an asymptotic high-energy statement. At large $c$, using it near the black-hole threshold requires additional spectral assumptions.

## Exercises

### Exercise 1: The rectangular torus and the $S$ transform

For a rectangular thermal torus with $\tau=i\beta/(2\pi)$, show that the modular transformation $S:\tau\mapsto-1/\tau$ sends $\beta$ to $4\pi^2/\beta$.

<details><summary><strong>Solution</strong></summary>

Start with

$$
\tau=\frac{i\beta}{2\pi}.
$$

Then

$$
-\frac1\tau
=
-\frac{1}{i\beta/(2\pi)}
=
\frac{2\pi i}{\beta}.
$$

If the transformed torus is written as

$$
\tau'=\frac{i\beta'}{2\pi},
$$

then

$$
\frac{i\beta'}{2\pi}
=
\frac{2\pi i}{\beta}.
$$

Thus

$$
\boxed{
\beta'=\frac{4\pi^2}{\beta}.
}
$$

</details>

### Exercise 2: Modular $T$ and spin integrality

Assume $c=\bar c$. Show that $T$ invariance of the bosonic torus partition function requires $h-\bar h\in\mathbb Z$ for every state appearing in the spectrum.

<details><summary><strong>Solution</strong></summary>

A state with weights $(h,\bar h)$ contributes

$$
q^{h-c/24}\bar q^{\bar h-c/24}.
$$

Under $T:\tau\mapsto\tau+1$,

$$
q\mapsto e^{2\pi i}q,
\qquad
\bar q\mapsto e^{-2\pi i}\bar q.
$$

Therefore the state contribution is multiplied by

$$
\exp\!\left[2\pi i(h-c/24)\right]
\exp\!\left[-2\pi i(\bar h-c/24)\right]
=
\exp\!\left[2\pi i(h-\bar h)\right].
$$

For the full bosonic partition function to be invariant term by term, or at least not to mix phases among states with unequal phases, we need

$$
\exp\!\left[2\pi i(h-\bar h)\right]=1.
$$

Thus

$$
\boxed{h-\bar h\in\mathbb Z.}
$$

This is integer spin.

</details>

### Exercise 3: High-temperature partition function

Assume a compact unitary CFT with a unique vacuum and $c=\bar c$. Use modular invariance to show that, as $\beta\to0$,

$$
\log Z(\beta)
\sim
\frac{\pi^2 c}{3\beta}.
$$

<details><summary><strong>Solution</strong></summary>

At low temperature, $\beta\to\infty$, the vacuum dominates. Since $c=\bar c$, the vacuum cylinder energy is

$$
E_{\rm vac}=-\frac{c}{12}.
$$

Thus

$$
Z(\beta)
\sim e^{-\beta E_{\rm vac}}
=e^{\beta c/12}.
$$

Modular invariance gives

$$
Z(\beta)=Z\!\left(\frac{4\pi^2}{\beta}\right).
$$

For $\beta\to0$, the transformed inverse temperature $4\pi^2/\beta$ is large, so the vacuum approximation applies:

$$
Z(\beta)
\sim
\exp\!\left[
\frac{4\pi^2}{\beta}\frac{c}{12}
\right]
=
\exp\!\left[
\frac{\pi^2 c}{3\beta}
\right].
$$

Therefore

$$
\boxed{
\log Z(\beta)
\sim
\frac{\pi^2 c}{3\beta}.
}
$$

</details>

### Exercise 4: Saddle derivation of the chiral Cardy formula

Let a chiral partition function behave at high temperature as

$$
Z_L(\beta)
\sim
\exp\!\left(\frac{\pi^2 c}{6\beta}\right).
$$

Assume

$$
Z_L(\beta)
=
\int dE\,\rho_L(E)e^{-\beta E},
$$

where $E=L_0-c/24$ is the chiral cylinder energy. Derive

$$
\log \rho_L(E)
\sim
2\pi\sqrt{\frac{cE}{6}}.
$$

<details><summary><strong>Solution</strong></summary>

The inverse Laplace transform is schematically

$$
\rho_L(E)
\sim
\int d\beta\,
\exp\!\left[
\beta E+\frac{\pi^2 c}{6\beta}
\right].
$$

At large $E$, evaluate by saddle point. The exponent is

$$
\Phi(\beta)=\beta E+\frac{\pi^2 c}{6\beta}.
$$

The saddle equation is

$$
0=\frac{d\Phi}{d\beta}
=E-\frac{\pi^2 c}{6\beta^2}.
$$

Thus

$$
\beta_*=\pi\sqrt{\frac{c}{6E}}.
$$

At the saddle,

$$
\Phi(\beta_*)
=\beta_*E+\frac{\pi^2 c}{6\beta_*}
=2\pi\sqrt{\frac{cE}{6}}.
$$

Therefore

$$
\boxed{
\log \rho_L(E)
\sim
2\pi\sqrt{\frac{cE}{6}}.
}
$$

The nonchiral formula is the sum of the left and right saddle entropies.

</details>

### Exercise 5: Why a diagonal RCFT partition function is modular invariant

Suppose the characters transform as

$$
\chi_i(-1/\tau)=\sum_j S_{ij}\chi_j(\tau),
$$

where $S$ is unitary. Show that

$$
Z_{\rm diag}=\sum_i |\chi_i|^2
$$

is invariant under $S$.

<details><summary><strong>Solution</strong></summary>

Under $S$,

$$
Z_{\rm diag}
\mapsto
\sum_i
\left|\sum_j S_{ij}\chi_j\right|^2.
$$

Expanding,

$$
\sum_i
\left(\sum_j S_{ij}\chi_j\right)
\left(\sum_k S_{ik}\chi_k\right)^*
=
\sum_{j,k}\chi_j\bar\chi_k
\sum_i S_{ij}S^*_{ik}.
$$

Since $S$ is unitary,

$$
\sum_i S_{ij}S^*_{ik}=\delta_{jk}.
$$

Therefore

$$
Z_{\rm diag}
\mapsto
\sum_j \chi_j\bar\chi_j
=Z_{\rm diag}.
$$

This proves $S$ invariance. Full modular invariance also requires invariance under $T$, which imposes compatible spin phases.

</details>

## Further reading

For the classic 2D CFT treatment, see Di Francesco, Mathieu, and Sénéchal, especially the chapters on the operator formalism, modular invariance, minimal models, and WZW models. For the original physical argument behind the asymptotic density of states, see Cardy's work on operator content and modular invariance. For the AdS$_3$ connection, the essential later references are Brown-Henneaux for the central charge and the BTZ/Cardy entropy matching.

The next page turns from Virasoro modular technology to current algebras and WZW models, where modular transformations, affine characters, fusion rules, and the Verlinde formula become fully concrete.
