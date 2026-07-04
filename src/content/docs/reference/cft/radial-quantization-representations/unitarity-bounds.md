---
title: "Unitarity Bounds"
description: "How positivity in radial quantization constrains scaling dimensions, produces conserved currents, and prepares the AdS/CFT dictionary."
sidebar:
  order: 3
---

A conformal field theory is not just a representation of the conformal algebra. It is, in a unitary theory, a representation on a Hilbert space with a positive inner product. That positivity is surprisingly powerful. It says that many apparently legal conformal multiplets are forbidden. The resulting constraints are called **unitarity bounds**.

The most important bounds for this course are, for $d \geq 3$,

| operator type | bound | what happens at saturation |
|---|---:|---|
| identity $\mathbf 1$ | $\Delta=0$ | isolated vacuum representation |
| scalar primary, non-identity | $\Delta \geq \dfrac{d-2}{2}$ | free equation $\partial^2\mathcal O=0$ |
| spinor primary | $\Delta \geq \dfrac{d-1}{2}$ | free Dirac equation $\gamma^\mu\partial_\mu\psi=0$ |
| symmetric traceless spin-$\ell$ primary, $\ell\geq 1$ | $\Delta \geq \ell+d-2$ | conservation $\partial^{\mu_1}\mathcal O_{\mu_1\cdots\mu_\ell}=0$ |
| conserved current $J_\mu$ | $\Delta=d-1$ | global symmetry current |
| stress tensor $T_{\mu\nu}$ | $\Delta=d$ | spacetime symmetry current |

These are not optional details. They are part of what makes CFT a rigid subject. In the bootstrap, they define the allowed spectrum. In AdS/CFT, they decide which boundary operators can correspond to physical bulk particles, which bulk fields must be gauge fields, and which proposed spectra are impossible.

## The radial-quantization setup

We work in Euclidean signature and use radial quantization. A local primary operator $\mathcal O(0)$ creates a state

$$
|\mathcal O\rangle = \mathcal O(0)|0\rangle .
$$

The dilatation generator $D$ is the Hamiltonian on the cylinder $S^{d-1}\times \mathbb R_\tau$, so

$$
D|\mathcal O\rangle = \Delta |\mathcal O\rangle .
$$

A primary state is annihilated by special conformal generators:

$$
K_\mu|\mathcal O\rangle=0.
$$

Descendants are obtained by acting with momenta:

$$
P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle .
$$

Since $[D,P_\mu]=P_\mu$, a level-$n$ descendant has cylinder energy $\Delta+n$. Radial conjugation gives

$$
P_\mu^\dagger=K_\mu,
\qquad
D^\dagger=D,
$$

so descendant norms can be computed algebraically from the conformal commutators. For norm computations it is convenient to use the convention

$$
[D,P_\mu]=P_\mu,
\qquad
[D,K_\mu]=-K_\mu,
\qquad
[K_\mu,P_\nu]=2\delta_{\mu\nu}D+2M_{\mu\nu}.
$$

This is the same conformal algebra as before, with the factors of $i$ absorbed into the Hermitian radial-quantization convention.

The central principle is simple:

$$
\text{every state in a unitary CFT must have nonnegative norm.}
$$

The hard work is that every conformal primary generates infinitely many descendants. The norm matrix at each level must be positive semidefinite. The first few levels already give the familiar unitarity bounds.

## Reflection positivity and the meaning of norm

For a scalar primary with two-point function

$$
\langle \mathcal O(x)\mathcal O(0)\rangle = \frac{C_{\mathcal O}}{|x|^{2\Delta}},
$$

radial quantization defines

$$
\langle \mathcal O|\mathcal O\rangle
=\lim_{|x|\to\infty}|x|^{2\Delta}\langle \mathcal O(x)\mathcal O(0)\rangle
=C_{\mathcal O}.
$$

Unitarity requires $C_{\mathcal O}>0$ for a nonzero operator. This fixes the sign convention of the two-point function. But positivity of the primary norm is only the beginning. Positivity must also hold for

$$
P_\mu|\mathcal O\rangle,
\qquad
P_\mu P_\nu|\mathcal O\rangle,
\qquad
P_\mu P_\nu P_\rho|\mathcal O\rangle,
\qquad \ldots
$$

A proposed primary can have a positive two-point function and still be illegal because one of its descendants has negative norm.

This is the clean representation-theoretic origin of the bounds.

## Scalar primary: why $\Delta\geq (d-2)/2$

Let $\mathcal O$ be a scalar primary normalized by

$$
\langle \mathcal O|\mathcal O\rangle=1.
$$

At level one,

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=\langle \mathcal O|K_\mu P_\nu|\mathcal O\rangle.
$$

Because $K_\mu|\mathcal O\rangle=0$ and $\mathcal O$ is a scalar, this becomes

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=2\Delta\delta_{\mu\nu}.
$$

Therefore level-one positivity only gives

$$
\Delta\geq 0.
$$

This is weaker than the true scalar bound. The stronger condition appears at level two. The dangerous scalar descendant is

$$
P^2|\mathcal O\rangle
\equiv P_\mu P_\mu|\mathcal O\rangle .
$$

A short commutator calculation gives

$$
K_\mu P^2|\mathcal O\rangle
=4\left(\Delta-\frac d2+1\right)P_\mu|\mathcal O\rangle.
$$

Then

$$
\begin{aligned}
\|P^2|\mathcal O\rangle\|^2
&=\langle \mathcal O|K^2P^2|\mathcal O\rangle \\
&=8d\Delta\left(\Delta-\frac d2+1\right).
\end{aligned}
$$

For a non-identity scalar primary, $\Delta>0$, so positivity requires

$$
\boxed{\Delta\geq \frac{d-2}{2}.}
$$

When the bound is saturated, the descendant $P^2|\mathcal O\rangle$ is null:

$$
P^2|\mathcal O\rangle=0.
$$

In position space this says

$$
\partial^2\mathcal O(x)=0.
$$

Thus the scalar saturating the bound behaves like a free massless scalar field. This is an important lesson: in CFT, an equation of motion is not merely a Lagrangian statement. It is also a representation-theoretic shortening condition.

The identity operator is a special isolated case. It has $\Delta=0$, but it does not violate unitarity because

$$
P_\mu|\mathbf 1\rangle=0.
$$

The identity creates the vacuum, not an ordinary scalar conformal multiplet.

## Spin-$\ell$ symmetric traceless primary

Now take a primary in the symmetric traceless representation of $SO(d)$:

$$
\mathcal O_{\mu_1\cdots\mu_\ell}(x),
\qquad
\mathcal O_{\mu_1\cdots\mu_\ell}=\mathcal O_{(\mu_1\cdots\mu_\ell)},
\qquad
\delta^{\mu_1\mu_2}\mathcal O_{\mu_1\cdots\mu_\ell}=0.
$$

It is useful to package the indices with a null polarization vector $z^\mu$ satisfying $z^2=0$:

$$
\mathcal O(x,z)=\mathcal O_{\mu_1\cdots\mu_\ell}(x)z^{\mu_1}\cdots z^{\mu_\ell}.
$$

At level one, the descendant $P_\nu|\mathcal O_{\mu_1\cdots\mu_\ell}\rangle$ decomposes into irreducible $SO(d)$ representations. Schematically,

$$
[\ell]\otimes [1]
=[\ell+1]\oplus[\ell-1]\oplus\text{mixed-symmetry part}.
$$

The most important component is the divergence descendant,

$$
P^{\mu_1}|\mathcal O_{\mu_1\cdots\mu_\ell}\rangle.
$$

Its norm is proportional to

$$
(\Delta+\ell-1)(\Delta-\ell-d+2).
$$

The first factor is positive in any physically relevant conformal multiplet. Hence the sign is controlled by the second factor, and unitarity gives

$$
\boxed{\Delta\geq \ell+d-2,\qquad \ell\geq 1.}
$$

At saturation,

$$
P^{\mu_1}|\mathcal O_{\mu_1\cdots\mu_\ell}\rangle=0,
$$

or in position space,

$$
\boxed{\partial^{\mu_1}\mathcal O_{\mu_1\cdots\mu_\ell}(x)=0.}
$$

So a spin-$\ell$ primary saturating the unitarity bound is a conserved current.

For $\ell=1$, the bound is

$$
\Delta\geq d-1.
$$

Saturation gives

$$
\partial^\mu J_\mu=0,
$$

so $J_\mu$ is a conserved global-symmetry current.

For $\ell=2$, the bound is

$$
\Delta\geq d.
$$

Saturation gives

$$
\partial^\mu T_{\mu\nu}=0,
$$

so $T_{\mu\nu}$ is the stress tensor.

This is why in any unitary CFT in $d\geq 3$ the stress tensor has exactly

$$
\Delta_T=d,
\qquad
\ell_T=2.
$$

This value is not a perturbative accident. It is forced by conservation and unitarity.

## Spinor bound

For a spinor primary $\psi_\alpha$, the dangerous level-one descendant is the gamma-trace

$$
\gamma^\mu P_\mu|\psi\rangle.
$$

Its norm is proportional to

$$
\Delta-\frac{d-1}{2}.
$$

Therefore

$$
\boxed{\Delta_\psi\geq \frac{d-1}{2}.}
$$

At saturation,

$$
\gamma^\mu P_\mu|\psi\rangle=0,
$$

or in position space,

$$
\gamma^\mu\partial_\mu\psi(x)=0.
$$

Again, saturation gives a free field equation.

## Shortening, null descendants, and equations of motion

The phrase **short multiplet** means that some descendant has zero norm and must be quotiented out of the Hilbert space. In a unitary theory, a zero-norm state is orthogonal to all physical states, so it should be removed. This produces a smaller irreducible representation.

There are three basic possibilities:

| value of $\Delta$ | representation type | physical interpretation |
|---:|---|---|
| above the bound | long multiplet | generic interacting operator |
| exactly at the bound | shortened multiplet | null descendant, conservation law, or free equation |
| below the bound | nonunitary | negative-norm descendant |

For a scalar,

$$
\Delta=\frac{d-2}{2}
\quad\Longrightarrow\quad
\partial^2\mathcal O=0.
$$

For a spin-$\ell$ symmetric traceless tensor with $\ell\geq 1$,

$$
\Delta=\ell+d-2
\quad\Longrightarrow\quad
\partial^{\mu_1}\mathcal O_{\mu_1\cdots\mu_\ell}=0.
$$

The first is a free equation. The second is a conservation equation.

This distinction matters. A conserved current can exist in a strongly interacting CFT. A scalar saturating the unitarity bound is much more restrictive: it is a free scalar operator. In an interacting CFT, scalar primaries are usually strictly above the scalar bound.

## Why conserved currents have protected dimensions

The dimension of a conserved current can also be understood without the full representation theory. Suppose $J_\mu$ is a conserved current. The charge

$$
Q=\int_{S^{d-1}} d\Sigma^\mu J_\mu
$$

is dimensionless. The measure on a sphere has dimension $d-1$, so $J_\mu$ must have scaling dimension

$$
\Delta_J=d-1.
$$

Similarly, the stress tensor appears in the conserved momentum and conformal charges. Equivalently, it couples to the metric through

$$
\delta S=\frac12\int d^dx\,\sqrt g\,T^{\mu\nu}\delta g_{\mu\nu}.
$$

Since the action is dimensionless and the metric is dimensionless, the stress tensor has

$$
\Delta_T=d.
$$

These dimensions are protected because conservation is protected. A current cannot continuously acquire an anomalous dimension unless conservation is lost.

This is a sharp diagnostic in CFT data. If a spin-one operator has $\Delta=d-1$, it is a conserved current and signals a global symmetry. If a spin-two operator has $\Delta=d$, it is a stress tensor. If there is more than one independent spin-two conserved current in a local unitary CFT, the theory typically factorizes into decoupled sectors.

## The two-dimensional caveat

The table above is designed for $d\geq 3$. Two dimensions are special.

In $d=2$, the global conformal algebra is enhanced to two copies of the Virasoro algebra. Local operators are labeled by left and right conformal weights,

$$
(h,\bar h),
\qquad
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

Global conformal unitarity implies, roughly,

$$
h\geq 0,
\qquad
\bar h\geq 0,
$$

for non-vacuum unitary representations. Virasoro unitarity imposes further conditions involving the central charge $c$ and the highest weights. Those constraints are much stronger than the finite-dimensional $SO(d)$ bounds and are the reason minimal models are exactly classifiable.

For this course, the practical rule is:

$$
\text{use the bounds in this page for } d\geq 3;
\quad
\text{use Virasoro representation theory in } d=2.
$$

The physical idea is the same in both cases: positivity of descendant norms restricts the spectrum.

## Interpretation for the conformal bootstrap

The conformal bootstrap treats CFT data as an algebraic object:

$$
\left\{\Delta_i,\ell_i,\lambda_{ijk}\right\}
$$

subject to crossing symmetry and unitarity. Unitarity enters in two ways.

First, the spectrum must obey the unitarity bounds. For example, in a unitary $d=3$ CFT, a scalar primary must satisfy

$$
\Delta\geq\frac12,
$$

unless it is the identity. A spin-one primary must satisfy

$$
\Delta\geq2,
$$

with equality only for a conserved current. A spin-two primary must satisfy

$$
\Delta\geq3,
$$

with equality only for the stress tensor.

Second, squared OPE coefficients in identical-scalar four-point functions must be nonnegative:

$$
\lambda_{\phi\phi\mathcal O}^2\geq0.
$$

The bounds tell the bootstrap algorithm where conformal blocks are allowed to appear. Conservation laws tell it when a conformal block must be replaced by a shortened block.

## AdS/CFT checkpoint

In global AdS, the isometry group is $SO(d,2)$, the same group as the conformal group of the boundary CFT. A CFT primary corresponds to a lowest-energy AdS state, and the scaling dimension is the global AdS energy:

$$
E_0=\Delta.
$$

Descendants correspond to acting with AdS raising operators. A CFT unitarity bound is therefore also a constraint on the allowed lowest-weight representations of the AdS isometry group.

For scalar operators, the bulk mass and boundary scaling dimension are related by

$$
m^2R^2=\Delta(\Delta-d).
$$

The CFT scalar unitarity bound

$$
\Delta\geq\frac{d-2}{2}
$$

is crucial for understanding the allowed quantizations of scalars near the Breitenlohner-Freedman window. In particular, for

$$
\Delta_- = \frac d2-\nu,
\qquad
\nu=\sqrt{\frac{d^2}{4}+m^2R^2},
$$

alternative quantization is unitary only if

$$
\Delta_-\geq\frac{d-2}{2},
$$

which means

$$
0\leq \nu\leq1.
$$

For spinning operators, the interpretation is even more vivid:

$$
\begin{array}{ccl}
J_\mu,\ \Delta=d-1 &\longleftrightarrow& \text{massless gauge field in AdS},\\[2mm]
T_{\mu\nu},\ \Delta=d &\longleftrightarrow& \text{graviton in AdS},\\[2mm]
\mathcal O_{\mu_1\cdots\mu_\ell},\ \Delta=\ell+d-2 &\longleftrightarrow& \text{massless spin-}\ell\text{ gauge field}.
\end{array}
$$

Above the bound, the bulk field is massive. At the bound, a null descendant appears on the CFT side, and a gauge redundancy appears on the AdS side.

This is one of the cleanest examples of the AdS/CFT dictionary already being visible inside CFT representation theory.

## Examples

### Free scalar

A free massless scalar in $d$ dimensions has

$$
\Delta_\phi=\frac{d-2}{2}.
$$

It saturates the scalar unitarity bound. The null descendant is

$$
\partial^2\phi=0.
$$

The existence of this null descendant is what removes negative-norm states that would otherwise appear at level two.

### Conserved current

A global symmetry current has

$$
\Delta_J=d-1,
\qquad
\partial^\mu J_\mu=0.
$$

In AdS/CFT, this is the boundary signal of a bulk gauge field. A CFT global symmetry becomes a gauge symmetry in the bulk.

### Stress tensor

The stress tensor has

$$
\Delta_T=d,
\qquad
\partial^\mu T_{\mu\nu}=0,
\qquad
T^\mu{}_{\mu}=0
$$

in a CFT, up to anomalies and contact terms on curved backgrounds. In AdS/CFT, this is the boundary signal of dynamical gravity in the bulk.

### Higher-spin currents

A symmetric traceless current with spin $\ell>2$ and dimension

$$
\Delta=\ell+d-2
$$

is a conserved higher-spin current. In an interacting unitary CFT with a unique stress tensor and $d\geq3$, exact higher-spin currents are extremely restrictive; in familiar cases they signal free or highly constrained theories. In AdS language, they correspond to massless higher-spin gauge fields.

## Common pitfalls

### Pitfall 1: confusing engineering dimension with scaling dimension

The unitarity bounds constrain the exact CFT scaling dimension $\Delta$, not the engineering dimension assigned in a classical Lagrangian. At an interacting fixed point,

$$
\Delta=\Delta_{\rm classical}+\gamma,
$$

where $\gamma$ is an anomalous dimension. The bound applies to the full $\Delta$.

### Pitfall 2: treating null descendants as ordinary zeroes

A null descendant is not just a state whose norm accidentally vanishes. In a unitary representation, it must be removed from the physical Hilbert space. In position space, this removal appears as a differential equation or conservation law.

### Pitfall 3: forgetting the identity exception

The scalar bound

$$
\Delta\geq\frac{d-2}{2}
$$

is for nontrivial scalar primaries. The identity operator has $\Delta=0$ and is allowed because it creates the vacuum representation, not an ordinary scalar multiplet.

### Pitfall 4: applying the $d\geq3$ table directly to 2D Virasoro CFT

Two-dimensional CFT has extra local conformal symmetry. The right language there is Virasoro representation theory, with weights $(h,\bar h)$ and central charge $c$.

## Exercises

### Exercise 1: level-one scalar descendant

Let $\mathcal O$ be a scalar primary with $\langle\mathcal O|\mathcal O\rangle=1$. Use

$$
K_\mu|\mathcal O\rangle=0,
\qquad
[K_\mu,P_\nu]=2\delta_{\mu\nu}D+2M_{\mu\nu},
\qquad
M_{\mu\nu}|\mathcal O\rangle=0,
$$

to compute $\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle$.

<details><summary><strong>Solution</strong></summary>

By radial conjugation, $P_\mu^\dagger=K_\mu$, so

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=\langle\mathcal O|K_\mu P_\nu|\mathcal O\rangle.
$$

Since $K_\mu|\mathcal O\rangle=0$,

$$
K_\mu P_\nu|\mathcal O\rangle
=[K_\mu,P_\nu]|\mathcal O\rangle.
$$

Using the commutator,

$$
[K_\mu,P_\nu]|\mathcal O\rangle
=2\delta_{\mu\nu}D|\mathcal O\rangle+2M_{\mu\nu}|\mathcal O\rangle.
$$

The primary is a scalar, so $M_{\mu\nu}|\mathcal O\rangle=0$, and $D|\mathcal O\rangle=\Delta|\mathcal O\rangle$. Therefore

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=2\Delta\delta_{\mu\nu}.
$$

Level-one positivity gives $\Delta\geq0$.

</details>

### Exercise 2: scalar unitarity bound from the level-two descendant

Assume the commutator identity

$$
K_\mu P^2|\mathcal O\rangle
=4\left(\Delta-\frac d2+1\right)P_\mu|\mathcal O\rangle
$$

for a scalar primary. Use Exercise 1 to show that positivity of $P^2|\mathcal O\rangle$ gives the scalar unitarity bound for non-identity scalar primaries.

<details><summary><strong>Solution</strong></summary>

We compute

$$
\|P^2|\mathcal O\rangle\|^2
=\langle \mathcal O|K^2P^2|\mathcal O\rangle.
$$

Using the given identity,

$$
K_\mu P^2|\mathcal O\rangle
=4\left(\Delta-\frac d2+1\right)P_\mu|\mathcal O\rangle.
$$

Therefore

$$
\begin{aligned}
\|P^2|\mathcal O\rangle\|^2
&=4\left(\Delta-\frac d2+1\right)
\langle \mathcal O|K_\mu P_\mu|\mathcal O\rangle \\
&=4\left(\Delta-\frac d2+1\right)
(2d\Delta) \\
&=8d\Delta\left(\Delta-\frac d2+1\right).
\end{aligned}
$$

For a non-identity scalar primary, $\Delta>0$. Positivity requires

$$
\Delta-\frac d2+1\geq0,
$$

or

$$
\Delta\geq\frac{d-2}{2}.
$$

At equality, $P^2|\mathcal O\rangle$ is null, which gives $\partial^2\mathcal O=0$.

</details>

### Exercise 3: dimension of a conserved current

Use dimensional analysis of the charge

$$
Q=\int_{S^{d-1}}d\Sigma^\mu J_\mu
$$

to show that a conserved current has $\Delta_J=d-1$.

<details><summary><strong>Solution</strong></summary>

The charge $Q$ is dimensionless: it generates an internal symmetry and does not scale under dilatations. The surface element on $S^{d-1}$ has scaling dimension $-(d-1)$ in position-space units, while $J_\mu$ has scaling dimension $\Delta_J$. The total scaling dimension of the integrand is therefore

$$
\Delta_J-(d-1).
$$

For $Q$ to be dimensionless, this must vanish:

$$
\Delta_J-(d-1)=0.
$$

Thus

$$
\Delta_J=d-1.
$$

This agrees with the spin-one unitarity bound at saturation.

</details>

### Exercise 4: stress tensor and the spin-two bound

The stress tensor is a symmetric traceless spin-two primary in a CFT. Use the spin-$\ell$ unitarity bound to determine its dimension. What does saturation mean?

<details><summary><strong>Solution</strong></summary>

For a symmetric traceless spin-$\ell$ primary with $\ell\geq1$,

$$
\Delta\geq \ell+d-2.
$$

For the stress tensor, $\ell=2$, so

$$
\Delta_T\geq d.
$$

The stress tensor is conserved,

$$
\partial^\mu T_{\mu\nu}=0,
$$

so it saturates the bound:

$$
\Delta_T=d.
$$

Saturation means that the divergence descendant $P^\mu|T_{\mu\nu}\rangle$ is null and is quotiented out of the physical Hilbert space.

</details>

### Exercise 5: scalar bulk mass and the CFT unitarity bound

For a scalar field in $AdS_{d+1}$,

$$
m^2R^2=\Delta(\Delta-d).
$$

Let

$$
\Delta_-=\frac d2-\nu,
\qquad
\nu=\sqrt{\frac{d^2}{4}+m^2R^2}.
$$

Show that the CFT scalar unitarity bound for $\Delta_-$ gives $0\leq\nu\leq1$.

<details><summary><strong>Solution</strong></summary>

The scalar unitarity bound is

$$
\Delta\geq\frac{d-2}{2}.
$$

For the alternative root,

$$
\Delta_- = \frac d2-\nu.
$$

Requiring $\Delta_-$ to obey the CFT bound gives

$$
\frac d2-\nu\geq\frac{d-2}{2}.
$$

Subtracting $(d-2)/2$ from both sides gives

$$
1-\nu\geq0,
$$

so

$$
\nu\leq1.
$$

Reality of $\nu$ gives $\nu\geq0$, equivalent to the Breitenlohner-Freedman condition. Thus alternative quantization is compatible with scalar unitarity only in the window

$$
0\leq\nu\leq1.
$$

</details>

## Takeaway

Unitarity bounds are positivity constraints on conformal multiplets. They say:

$$
\begin{array}{rcl}
\text{scalar} &:& \Delta\geq \dfrac{d-2}{2},\\[2mm]
\text{spinor} &:& \Delta\geq \dfrac{d-1}{2},\\[2mm]
\text{symmetric traceless spin }\ell\geq1 &:& \Delta\geq \ell+d-2.
\end{array}
$$

Saturating a bound is not generic. It means the multiplet shortens. The null descendant becomes a field equation or conservation law. In AdS/CFT language, this is the boundary shadow of masslessness, gauge invariance, and the distinction between physical and unphysical bulk polarizations.
