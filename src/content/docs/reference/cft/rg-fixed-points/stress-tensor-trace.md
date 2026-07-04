---
title: "The Stress-Tensor Trace"
description: "The trace of the stress tensor as the local diagnostic of scale dependence, beta functions, improvement terms, Weyl anomalies, and the bridge from RG fixed points to CFTs."
sidebar:
  order: 2
---

## Goal

The previous page described renormalization group flow as a motion in theory space. This page explains the same idea locally, through the stress tensor.

The stress tensor $T_{\mu\nu}$ is the operator coupled to the spacetime metric. Its trace $T^\mu{}_{\mu}$ measures the failure of a theory to be invariant under local changes of scale. At a fixed point, beta functions vanish. If the stress tensor can be improved appropriately, the flat-space trace vanishes:

$$
T^\mu{}_{\mu}=0.
$$

That equation is one of the central meanings of conformal invariance.

The main lesson is:

$$
\boxed{
\text{RG flow is measured by }T^\mu{}_{\mu}.
}
$$

More precisely, in a renormalized QFT one should expect a trace identity of the schematic form

$$
\boxed{
T^\mu{}_{\mu}
=
\sum_i \beta^i\mathcal O_i
+\partial_\mu V^\mu
+\mathcal A
+\text{contact terms}.
}
$$

Here $\beta^i$ are beta functions, $\partial_\mu V^\mu$ is a possible virial or improvement term, and $\mathcal A$ is a Weyl anomaly on curved backgrounds. At separated points in flat space, a genuine CFT has a representative of the stress tensor for which

$$
T^\mu{}_{\mu}=0.
$$

This is why the stress tensor is not just another operator. It is the operator that tells us whether the theory is sitting at a conformal fixed point.

## Conventions

There are two common RG conventions. The previous page used an IR-oriented Wilsonian scale factor $b>1$, where increasing $b$ means coarse graining toward longer distances. In this page, when writing beta functions in trace identities, we use the high-energy convention

$$
\beta^i(\lambda)=\mu\frac{d\lambda^i}{d\mu}.
$$

Thus moving to the IR corresponds to decreasing $\mu$. If $\beta^i_{\rm IR}$ denotes the beta function with respect to $\log b$, then

$$
\beta^i_{\rm IR}=-\beta^i.
$$

The sign of a trace formula can look different from book to book because of this convention, and also because of Euclidean versus Lorentzian choices. The invariant statement is not the sign convention; it is that the trace is controlled by how couplings respond to changes of scale.

Throughout this page, we work mostly in flat Euclidean space unless explicitly stated otherwise.

## Stress tensor from translations

In a classical field theory with fields $\phi^A$, the stress tensor first appears as the Noether current for translations. If the action is invariant under

$$
x^\mu\mapsto x^\mu+a^\mu,
$$

then there is a conserved current $T^\mu{}_{\nu}$ satisfying

$$
\partial_\mu T^\mu{}_{\nu}=0
$$

on the equations of motion. The conserved charges are the momenta

$$
P_\nu=\int d^{d-1}x\,T^0{}_{\nu}.
$$

In a relativistic theory, one can usually choose a symmetric stress tensor,

$$
T_{\mu\nu}=T_{\nu\mu},
$$

by adding improvement terms that do not change the conserved momentum. Once $T_{\mu\nu}$ is symmetric, it is the natural object that couples to the metric and generates spacetime transformations.

This is important: the stress tensor is not unique as a local operator. We can shift it by certain identically conserved local terms without changing the global charges. The trace, however, is sensitive to these improvements, and this sensitivity is exactly what matters when deciding whether scale invariance enhances to conformal invariance.

## Stress tensor from metric variation

The cleanest definition of $T_{\mu\nu}$ is obtained by putting the theory on a background metric $g_{\mu\nu}$.

Let

$$
W[g_{\mu\nu},\lambda^i]
=
-\log Z[g_{\mu\nu},\lambda^i]
$$

be the Euclidean generating functional, where $\lambda^i(x)$ are background sources for local operators $\mathcal O_i$. We use the convention

$$
\delta W
=
\frac12\int d^d x\sqrt g\,\langle T^{\mu\nu}\rangle\,\delta g_{\mu\nu}
+
\int d^d x\sqrt g\,\langle \mathcal O_i\rangle\,\delta\lambda^i.
$$

Equivalently,

$$
\langle T^{\mu\nu}(x)\rangle
=
\frac{2}{\sqrt g}\frac{\delta W}{\delta g_{\mu\nu}(x)},
\qquad
\langle\mathcal O_i(x)\rangle
=
\frac{1}{\sqrt g}\frac{\delta W}{\delta\lambda^i(x)}.
$$

This definition is more than aesthetic. It immediately tells us what the trace means.

A local Weyl transformation is

$$
\delta_\sigma g_{\mu\nu}=2\sigma(x)g_{\mu\nu}.
$$

Using the metric variation formula,

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma(x)\langle T^\mu{}_{\mu}(x)\rangle
$$

if the sources $\lambda^i$ are held fixed. Therefore:

$$
\boxed{
T^\mu{}_{\mu}
\text{ is the response of the theory to a local change of scale.}
}
$$

This is the local version of the statement that the dilatation generator measures scaling.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 55rem;">

![Trace Ward identity as the local Weyl response of a QFT](/figures/cft/stress-tensor-trace-ward-identity.svg)

<figcaption>

The trace $T^\mu{}_{\mu}$ is the local response of the generating functional $W[g_{\mu\nu},\lambda^i]$ to a Weyl transformation. In flat space, a properly improved fixed point has $T^\mu{}_{\mu}=0$. Away from a fixed point, beta functions appear. On curved space, a CFT can have a Weyl anomaly $\mathcal A[g]$.

</figcaption>
</figure>

## Scale transformations and the trace

In flat space, a global scale transformation is

$$
x^\mu\mapsto e^\alpha x^\mu.
$$

If the symmetric stress tensor is conserved, then the naive dilatation current is

$$
D^\mu=x_\nu T^{\mu\nu}.
$$

Its divergence is

$$
\partial_\mu D^\mu
=
T^\mu{}_{\mu}
+x_\nu\partial_\mu T^{\mu\nu}
=
T^\mu{}_{\mu}.
$$

Thus, if

$$
T^\mu{}_{\mu}=0,
$$

then $D^\mu$ is conserved and the theory is scale invariant.

The converse is subtler. A theory can be scale invariant even if the trace is not zero, provided the trace is a total derivative:

$$
T^\mu{}_{\mu}=\partial_\mu V^\mu.
$$

Then the improved dilatation current

$$
D^\mu=x_\nu T^{\mu\nu}-V^\mu
$$

is conserved:

$$
\partial_\mu D^\mu
=
T^\mu{}_{\mu}-\partial_\mu V^\mu
=0.
$$

The vector $V^\mu$ is called a virial current. The crucial question is whether $V^\mu$ can be removed by improving the stress tensor. If it can, then the scale-invariant theory is actually conformally invariant.

## Improvement terms

The stress tensor is not unique. In flat space, if $L(x)$ is a local scalar operator, then

$$
\Delta T_{\mu\nu}
=
\frac{1}{d-1}
\left(\partial_\mu\partial_\nu-\eta_{\mu\nu}\partial^2\right)L
$$

is identically conserved:

$$
\partial^\mu\Delta T_{\mu\nu}=0.
$$

Its trace is

$$
\Delta T^\mu{}_{\mu}
=
-\partial^2 L.
$$

Therefore, if the original stress tensor obeys

$$
T^\mu{}_{\mu}=\partial^2 L,
$$

then

$$
T'_{\mu\nu}=T_{\mu\nu}+\Delta T_{\mu\nu}
$$

has

$$
T'^\mu{}_{\mu}=0.
$$

This is the simplest and most common improvement mechanism.

### Example: the free massless scalar

Consider the free massless scalar in $d$ dimensions,

$$
S=\frac12\int d^d x\,\partial_\mu\phi\,\partial^\mu\phi.
$$

The canonical symmetric stress tensor is

$$
T^{\rm can}_{\mu\nu}
=
\partial_\mu\phi\partial_\nu\phi
-\frac12\eta_{\mu\nu}(\partial\phi)^2.
$$

On the equation of motion $\partial^2\phi=0$, its trace is

$$
T^{{\rm can}\,\mu}{}_{\mu}
=
\left(1-\frac d2\right)(\partial\phi)^2.
$$

Using

$$
\partial^2\phi^2=2(\partial\phi)^2
$$

on shell, this becomes

$$
T^{{\rm can}\,\mu}{}_{\mu}
=-\frac{d-2}{4}\partial^2\phi^2.
$$

Thus the trace is an improvement term. The improved stress tensor is

$$
T^{\rm conf}_{\mu\nu}
=
T^{\rm can}_{\mu\nu}
+
\xi\left(\eta_{\mu\nu}\partial^2-\partial_\mu\partial_\nu\right)\phi^2,
\qquad
\xi=\frac{d-2}{4(d-1)}.
$$

It is conserved, symmetric, and traceless on shell:

$$
T^{{\rm conf}\,\mu}{}_{\mu}=0.
$$

This example is a perfect warning: if one uses the wrong stress tensor, the free massless scalar looks merely scale invariant. With the correct improved stress tensor, it is conformal for $d>2$. In $d=2$, the elementary scalar field itself has special infrared subtleties, but its derivative theory and vertex-operator CFTs are central examples of two-dimensional CFT.

## Why conformal invariance needs more than scale invariance

If $T_{\mu\nu}$ is symmetric and conserved, the current for special conformal transformations is

$$
K^\mu{}_{\rho}
=
\left(2x_\rho x_\nu-x^2\eta_{\rho\nu}\right)T^{\mu\nu}.
$$

Its divergence is

$$
\partial_\mu K^\mu{}_{\rho}
=
2x_\rho T^\mu{}_{\mu}
$$

when $T_{\mu\nu}$ is conserved and symmetric. Therefore, if

$$
T^\mu{}_{\mu}=0,
$$

then the special conformal currents are conserved.

This is the structural reason conformal invariance is stronger than scale invariance. Scale invariance asks for a conserved dilatation current. Conformal invariance asks for conserved special conformal currents as well. A traceless stress tensor gives both.

For the unitary, local, Poincare-invariant theories that dominate this course, RG fixed points are expected to be CFTs under suitable assumptions. But the assumptions matter. The stress tensor is where the assumptions live.

## Quantum trace identity

Now consider a renormalized theory described by dimensionless couplings $\lambda^i$ and sources for operators $\mathcal O_i$. The local RG equation has the schematic form

$$
\left(
2g_{\mu\nu}\frac{\delta}{\delta g_{\mu\nu}}
-
\beta^i\frac{\delta}{\delta\lambda^i}
\right)W
=
\int d^d x\sqrt g\,\mathcal A.
$$

Here $\mathcal A$ is a local anomaly functional. Using the definitions of $T_{\mu\nu}$ and $\mathcal O_i$, this becomes

$$
\boxed{
\langle T^\mu{}_{\mu}\rangle
-
\beta^i\langle\mathcal O_i\rangle
=
\mathcal A.
}
$$

Equivalently, at the operator level and away from coincident operator insertions,

$$
\boxed{
T^\mu{}_{\mu}
=
\beta^i\mathcal O_i
+\mathcal A
}
$$

with the understanding that improvement terms, virial currents, operator mixing, and contact terms may have to be included in a careful treatment.

This equation is the local form of the Callan-Symanzik equation. It says:

$$
\boxed{
\text{nonzero beta functions create a nonzero trace.}
}
$$

At a fixed point,

$$
\beta^i=0.
$$

In flat space, where curvature-dependent anomalies vanish, a properly improved CFT has

$$
T^\mu{}_{\mu}=0.
$$

## Relevant deformations and the trace

Let $\mathcal O$ be a scalar primary of dimension $\Delta$ in a CFT. Deform the theory by

$$
S=S_{\rm CFT}+\lambda\mu^{d-\Delta}\int d^d x\,\mathcal O(x),
$$

where $\lambda$ is dimensionless. Near the fixed point, the beta function begins as

$$
\beta_\lambda
=
\mu\frac{d\lambda}{d\mu}
=(\Delta-d)\lambda+O(\lambda^2).
$$

Thus, to leading order,

$$
T^\mu{}_{\mu}
=
(\Delta-d)\lambda\mu^{d-\Delta}\mathcal O+O(\lambda^2)
$$

in the convention used here.

If $\Delta<d$, the deformation is relevant. In the high-energy convention, $\beta_\lambda$ is negative at small positive $\lambda$, reflecting that $\lambda$ grows as one runs toward the IR. In the IR Wilsonian convention of the previous page, the eigenvalue is

$$
y=d-\Delta>0.
$$

Same physics, opposite flow parameter.

This is the first bridge between the operator dimension $\Delta$ and the trace. The operator dimension tells us how a coupling runs. The coupling's running tells us the trace.

## Marginal couplings and conformal manifolds

If $\Delta=d$, then the deformation is classically marginal:

$$
S=S_{\rm CFT}+\lambda\int d^d x\,\mathcal O(x).
$$

At linear order,

$$
\beta_\lambda=0.
$$

But quantum corrections can give

$$
\beta_\lambda=b_2\lambda^2+b_3\lambda^3+\cdots.
$$

There are three qualitatively different possibilities:

| Type | Trace consequence | Physical meaning |
|---|---|---|
| Marginally relevant | $\beta_\lambda$ drives the theory away from the fixed point | The coupling grows toward the IR. |
| Marginally irrelevant | $\beta_\lambda$ drives the theory back to the fixed point | The coupling dies logarithmically. |
| Exactly marginal | $\beta_\lambda=0$ to all orders | There is a continuous family of CFTs. |

Exactly marginal couplings are crucial in supersymmetric AdS/CFT examples. In four-dimensional $\mathcal N=4$ super Yang-Mills, the complexified gauge coupling is exactly marginal, and the theory remains conformal along a conformal manifold. The trace remains zero in flat space even though the value of the coupling changes.

## Anomalies: why CFTs can have a trace on curved space

A flat-space CFT has

$$
T^\mu{}_{\mu}=0
$$

at separated points after improvement. But this does not mean the trace vanishes on every background. In even spacetime dimensions, the generating functional can have a Weyl anomaly.

In two dimensions, the standard form is

$$
\langle T^\mu{}_{\mu}\rangle
=
-\frac{c}{24\pi}R,
$$

up to sign conventions for $W$ and $T_{\mu\nu}$. The number $c$ is the central charge.

In four dimensions, the trace anomaly has the schematic form

$$
\langle T^\mu{}_{\mu}\rangle
=
\frac{c}{16\pi^2}W_{\mu\nu\rho\sigma}W^{\mu\nu\rho\sigma}
-
\frac{a}{16\pi^2}E_4
+\text{flavor anomalies}
+\text{scheme-dependent }\nabla^2R.
$$

Here $W_{\mu\nu\rho\sigma}$ is the Weyl tensor and $E_4$ is the Euler density. The coefficient of $\nabla^2R$ is scheme-dependent because it can be shifted by local counterterms. The coefficients $a$ and $c$ are intrinsic CFT data.

This is not a contradiction. The anomaly is a statement about coupling the theory to a background geometry. In flat space, the curvature terms vanish.

## Contact terms and separated points

Trace identities should be read carefully. As operator equations, they are most robust inside correlation functions at separated points. If $X=\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)$, then a CFT has

$$
\langle T^\mu{}_{\mu}(x)X\rangle=0
\qquad
\text{for }x\neq x_i
$$

in flat space. But when $x$ collides with one of the $x_i$, there are contact terms. These contact terms encode the transformation laws of the operators under scale and conformal transformations.

For example, the integrated scale Ward identity for scalar primaries says

$$
\left(\sum_{i=1}^n x_i^\mu\frac{\partial}{\partial x_i^\mu}
+\sum_{i=1}^n\Delta_i\right)
\langle\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle=0
$$

at a fixed point. Locally, the $\Delta_i$ terms come from contact terms in the trace Ward identity.

So one should not say, too casually, that the trace operator is zero in every possible sense. The precise statement is:

$$
\boxed{
T^\mu{}_{\mu}=0
\text{ at separated points in flat-space CFT correlators,}
}
$$

with contact terms enforcing Ward identities.

## Examples

### Massive deformation of a free scalar

Start with the conformally improved massless scalar and add

$$
\delta S=\frac12m^2\int d^d x\,\phi^2.
$$

At the Gaussian fixed point,

$$
\Delta_{\phi^2}=d-2.
$$

Thus the mass-squared coupling has RG exponent

$$
y=d-\Delta_{\phi^2}=2.
$$

The mass term is relevant. Correspondingly, the trace becomes proportional to the mass deformation:

$$
T^\mu{}_{\mu}\propto m^2\phi^2
$$

with a sign depending on Euclidean/Lorentzian and beta-function conventions. The important point is that $m$ introduces a length scale,

$$
\xi\sim m^{-1},
$$

so the theory is no longer scale invariant.

### Gauge theory in four dimensions

For a four-dimensional gauge theory written schematically as

$$
\mathcal L=\frac{1}{4g^2}\operatorname{tr}F_{\mu\nu}F^{\mu\nu}+\cdots,
$$

quantum running of $g$ produces a trace proportional to the beta function:

$$
T^\mu{}_{\mu}
\sim
\frac{\beta(g)}{g^3}\operatorname{tr}F_{\mu\nu}F^{\mu\nu}
+\cdots.
$$

If $\beta(g)=0$ and all other beta functions vanish, the flat-space trace vanishes after improvement. This is the stress-tensor way to say that the theory is conformal.

This will matter later for $\mathcal N=4$ super Yang-Mills, where the gauge beta function vanishes and the theory is the canonical four-dimensional CFT in AdS/CFT.

### Two-dimensional CFT

In two dimensions, the flat-space trace condition becomes

$$
T_{z\bar z}=0.
$$

Conservation of the stress tensor then implies

$$
\partial_{\bar z}T_{zz}=0,
\qquad
\partial_z T_{\bar z\bar z}=0.
$$

Thus the stress tensor splits into a holomorphic and antiholomorphic part:

$$
T(z)=T_{zz}(z),
\qquad
\bar T(\bar z)=T_{\bar z\bar z}(\bar z).
$$

This is the beginning of the Virasoro story. The entire infinite-dimensional structure of two-dimensional CFT grows out of the same local equation:

$$
T^\mu{}_{\mu}=0.
$$

## Holographic checkpoint

The stress-tensor trace is one of the most important CFT quantities in AdS/CFT.

First, the stress tensor is dual to the bulk metric:

$$
T_{\mu\nu}
\quad\longleftrightarrow\quad
\text{asymptotic metric fluctuation }g_{\mu\nu}^{\rm bulk}.
$$

Second, the CFT trace Ward identity is encoded by the radial constraints of gravity. In Fefferman-Graham language, the near-boundary radial direction plays the role of scale. Radial evolution of the bulk fields corresponds to RG evolution of boundary sources.

Third, the Weyl anomaly of the CFT is reproduced by logarithmic divergences in the regulated bulk on-shell action. In even boundary dimensions, holographic renormalization gives precisely the structure

$$
\langle T^\mu{}_{\mu}\rangle=\mathcal A.
$$

Fourth, relevant deformations of the CFT correspond to turning on non-normalizable modes of bulk fields. If

$$
\phi(z,x)\sim z^{d-\Delta}J(x)+z^\Delta A(x),
$$

then $J(x)$ is the source for an operator $\mathcal O$ of dimension $\Delta$. The deformation contributes to the trace because $J$ carries scale dimension $d-\Delta$.

Thus the trace equation is the boundary shadow of bulk radial dynamics:

$$
\boxed{
T^\mu{}_{\mu}
\leftrightarrow
\text{radial scale response of the bulk theory}.
}
$$

## Common pitfalls

### Pitfall 1: confusing conserved with traceless

Translation invariance gives

$$
\partial^\mu T_{\mu\nu}=0.
$$

Conformal invariance requires, after improvement,

$$
T^\mu{}_{\mu}=0.
$$

These are different statements.

### Pitfall 2: using the canonical stress tensor too literally

The canonical stress tensor is often not the conformal stress tensor. Improvement terms are not cosmetic; they can change the trace and reveal conformal invariance.

### Pitfall 3: thinking anomalies mean the theory is not a CFT

A CFT can have a Weyl anomaly on curved space. In even dimensions, this anomaly is part of the CFT data. Flat-space conformal invariance is not spoiled by curvature terms that vanish on flat backgrounds.

### Pitfall 4: ignoring contact terms

The equation $T^\mu{}_{\mu}=0$ in a CFT is a separated-point statement. Contact terms are needed to reproduce the scaling of operators inside correlation functions.

## Summary

The stress-tensor trace is the local diagnostic of scale dependence. Classically, a traceless stress tensor implies conserved dilatation and special conformal currents. If the trace is a removable improvement term, scale invariance enhances to conformal invariance.

Quantum mechanically, the trace identity is controlled by beta functions and anomalies:

$$
\boxed{
T^\mu{}_{\mu}
=
\beta^i\mathcal O_i
+\partial_\mu V^\mu
+\mathcal A
+\text{contact terms}.
}
$$

At a flat-space CFT fixed point, after choosing the correct improved stress tensor,

$$
\boxed{
T^\mu{}_{\mu}=0.
}
$$

This equation is one of the cleanest ways to recognize a conformal field theory, and it is one of the main boundary equations that holography geometrizes.

## Exercises

### Exercise 1 — Weyl variation and the trace

Assume

$$
\delta W
=
\frac12\int d^d x\sqrt g\,\langle T^{\mu\nu}\rangle\delta g_{\mu\nu}.
$$

For a Weyl variation

$$
\delta_\sigma g_{\mu\nu}=2\sigma g_{\mu\nu},
$$

show that

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma\langle T^\mu{}_{\mu}\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Substitute the Weyl variation into the metric variation formula:

$$
\delta_\sigma W
=
\frac12\int d^d x\sqrt g\,\langle T^{\mu\nu}\rangle\,2\sigma g_{\mu\nu}.
$$

Thus

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma\,g_{\mu\nu}\langle T^{\mu\nu}\rangle.
$$

Since

$$
g_{\mu\nu}T^{\mu\nu}=T^\mu{}_{\mu},
$$

we obtain

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma\langle T^\mu{}_{\mu}\rangle.
$$

</details>

### Exercise 2 — Improvement of a scalar stress tensor

For the free massless scalar,

$$
T^{\rm can}_{\mu\nu}
=\partial_\mu\phi\partial_\nu\phi
-\frac12\eta_{\mu\nu}(\partial\phi)^2.
$$

Using the equation of motion $\partial^2\phi=0$, show that

$$
T^{{\rm can}\,\mu}{}_{\mu}
=-\frac{d-2}{4}\partial^2\phi^2.
$$

Then verify that

$$
T^{\rm conf}_{\mu\nu}
=
T^{\rm can}_{\mu\nu}
+
\frac{d-2}{4(d-1)}
\left(\eta_{\mu\nu}\partial^2-\partial_\mu\partial_\nu\right)\phi^2
$$

is traceless on shell.

<details><summary><strong>Solution</strong></summary>

The trace of the canonical tensor is

$$
T^{{\rm can}\,\mu}{}_{\mu}
=(\partial\phi)^2-\frac d2(\partial\phi)^2
=\left(1-\frac d2\right)(\partial\phi)^2.
$$

Using $\partial^2\phi=0$,

$$
\partial^2\phi^2
=2\phi\partial^2\phi+2(\partial\phi)^2
=2(\partial\phi)^2.
$$

Therefore

$$
T^{{\rm can}\,\mu}{}_{\mu}
=\left(1-\frac d2\right)\frac12\partial^2\phi^2
=-\frac{d-2}{4}\partial^2\phi^2.
$$

The improvement term has trace

$$
\frac{d-2}{4(d-1)}
\left(d\partial^2-\partial^2\right)\phi^2
=
\frac{d-2}{4}\partial^2\phi^2.
$$

Adding this to the canonical trace gives

$$
T^{{\rm conf}\,\mu}{}_{\mu}=0
$$

on shell.

</details>

### Exercise 3 — Trace of a relevant deformation

Let a CFT be deformed by

$$
S=S_{\rm CFT}+\lambda\mu^{d-\Delta}\int d^d x\,\mathcal O(x),
$$

where $\mathcal O$ has scaling dimension $\Delta$ and $\lambda$ is dimensionless. Show that the leading beta function is

$$
\beta_\lambda=(\Delta-d)\lambda+O(\lambda^2).
$$

Explain why $\Delta<d$ is relevant even though $\beta_\lambda$ is negative for positive $\lambda$ in this convention.

<details><summary><strong>Solution</strong></summary>

The dimensionful source is

$$
g=\lambda\mu^{d-\Delta}.
$$

Holding the physical source $g$ fixed while changing $\mu$ gives

$$
0=\mu\frac{d}{d\mu}\left(\lambda\mu^{d-\Delta}\right)
=\mu^{d-\Delta}\left(\beta_\lambda+(d-\Delta)\lambda\right).
$$

Therefore

$$
\beta_\lambda=(\Delta-d)\lambda
$$

at leading order.

If $\Delta<d$, then $\beta_\lambda<0$ for positive $\lambda$ in the high-energy convention $\beta=\mu d\lambda/d\mu$. This means $\lambda$ decreases as $\mu$ increases toward the UV, or equivalently grows as $\mu$ decreases toward the IR.

In the IR Wilsonian convention with $b\sim 1/\mu$, the exponent is

$$
y=d-\Delta>0,
$$

so the deformation is relevant.

</details>

### Exercise 4 — Integrated two-dimensional anomaly

For a two-dimensional CFT on a compact Euclidean surface without boundary, suppose

$$
\langle T^\mu{}_{\mu}\rangle
=-\frac{c}{24\pi}R.
$$

Use the Gauss-Bonnet theorem

$$
\int d^2x\sqrt g\,R=4\pi\chi
$$

to compute

$$
\int d^2x\sqrt g\,\langle T^\mu{}_{\mu}\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Substitute the anomaly into the integral:

$$
\int d^2x\sqrt g\,\langle T^\mu{}_{\mu}\rangle
=
-\frac{c}{24\pi}
\int d^2x\sqrt g\,R.
$$

Using Gauss-Bonnet,

$$
\int d^2x\sqrt g\,R=4\pi\chi.
$$

Therefore

$$
\int d^2x\sqrt g\,\langle T^\mu{}_{\mu}\rangle
=
-\frac{c}{24\pi}(4\pi\chi)
=-\frac{c}{6}\chi.
$$

This shows that the central charge controls the global Weyl response of the two-dimensional CFT.

</details>

### Exercise 5 — Special conformal current

Let $T_{\mu\nu}$ be symmetric, conserved, and traceless in flat space. Define

$$
K^\mu{}_{\rho}
=
\left(2x_\rho x_\nu-x^2\eta_{\rho\nu}\right)T^{\mu\nu}.
$$

Show that

$$
\partial_\mu K^\mu{}_{\rho}=0.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate:

$$
\partial_\mu K^\mu{}_{\rho}
=
\partial_\mu\left(2x_\rho x_\nu-x^2\eta_{\rho\nu}\right)T^{\mu\nu}
+
\left(2x_\rho x_\nu-x^2\eta_{\rho\nu}\right)\partial_\mu T^{\mu\nu}.
$$

The second term vanishes by conservation:

$$
\partial_\mu T^{\mu\nu}=0.
$$

For the first term,

$$
\partial_\mu\left(2x_\rho x_\nu-x^2\eta_{\rho\nu}\right)
=
2\eta_{\mu\rho}x_\nu+2x_\rho\eta_{\mu\nu}-2x_\mu\eta_{\rho\nu}.
$$

Contracting with symmetric $T^{\mu\nu}$ gives

$$
2x_\nu T_\rho{}^\nu
+2x_\rho T^\mu{}_{\mu}
-2x_\mu T^\mu{}_{\rho}.
$$

The first and third terms cancel because $T_{\mu\nu}$ is symmetric. The remaining term is

$$
2x_\rho T^\mu{}_{\mu},
$$

which vanishes because the stress tensor is traceless. Hence

$$
\partial_\mu K^\mu{}_{\rho}=0.
$$

</details>
