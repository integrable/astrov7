---
title: "Sources and Generating Functionals"
description: "Background sources, connected correlators, contact terms, and the precise CFT side of the AdS/CFT source-response dictionary."
sidebar:
  order: 3
---

The previous page introduced the stress tensor and conserved currents as responses to background fields. This page turns that idea into a systematic tool.

A local operator is not just something we insert into a correlation function. It is something we can **source**. If $\mathcal O_i(x)$ is a local operator, then a background function $\lambda^i(x)$ coupled to $\mathcal O_i(x)$ lets us define a generating functional. Differentiating this generating functional with respect to $\lambda^i(x)$ creates insertions of $\mathcal O_i(x)$.

That sounds like a formal trick. In AdS/CFT it becomes physical:

$$
\boxed{
\text{CFT source}
\quad\longleftrightarrow\quad
\text{boundary value of a bulk field}.
}
$$

The source formalism is therefore not optional background technology. It is the CFT half of the holographic dictionary.

## The source convention used in this course

We work mostly in Euclidean signature. Let $\Phi$ denote all microscopic fields of the theory. For scalar operator sources $\lambda^i(x)$, background gauge fields $A_\mu^a(x)$, and a background metric $g_{\mu\nu}(x)$, define

$$
\mathcal Z[g,A,\lambda]
=
\int [D\Phi]_{g,A,\lambda}\,e^{-S[g,A,\lambda]},
$$

with

$$
S[g,A,\lambda]
=
S_{\mathrm{CFT}}[\Phi;g]
+
\int d^d x\sqrt g\,\lambda^i(x)\mathcal O_i(x)
+
\int d^d x\sqrt g\,A_\mu^a(x)J^\mu_a(x)
+
\cdots.
$$

The dots include possible higher-spin sources, fermionic sources in supersymmetric theories, and local counterterms needed to define the theory. The source $A_\mu^a$ is a **background** gauge field for a global symmetry; it is not integrated over in the CFT path integral.

We define the Euclidean connected generating functional by

$$
W[g,A,\lambda]
=
-\log \mathcal Z[g,A,\lambda].
$$

This is the convention already used in the previous page. Many QFT texts instead define $\mathcal W=\log\mathcal Z$. That convention is also fine, but every sign in the derivative formulas below changes. Here we use $W=-\log\mathcal Z$ because it is the convention naturally matched to a Euclidean on-shell bulk action:

$$
\mathcal Z_{\mathrm{bulk}}[\text{boundary data}]
\simeq
\exp\left[-S^{\mathrm{os}}_{\mathrm{ren}}\right]
\quad\Rightarrow\quad
W_{\mathrm{CFT}}\simeq S^{\mathrm{os}}_{\mathrm{ren}}.
$$

The vacuum normalization is often irrelevant. One may use

$$
W_{\mathrm{norm}}[g,A,\lambda]
=
W[g,A,\lambda]-W[g,A,0]
$$

when only connected correlators with operator insertions are desired.

## One-point functions as responses

The defining property of $W$ is that its first variation gives one-point functions in the presence of sources:

$$
\delta W
=
\frac12\int d^d x\sqrt g\,\langle T^{\mu\nu}\rangle\delta g_{\mu\nu}
+
\int d^d x\sqrt g\,\langle J^\mu_a\rangle\delta A_\mu^a
+
\int d^d x\sqrt g\,\langle\mathcal O_i\rangle\delta\lambda^i.
$$

Equivalently,

$$
\langle T^{\mu\nu}(x)\rangle
=
\frac{2}{\sqrt g}\frac{\delta W}{\delta g_{\mu\nu}(x)},
$$

$$
\langle J^\mu_a(x)\rangle
=
\frac{1}{\sqrt g}\frac{\delta W}{\delta A_\mu^a(x)},
\qquad
\langle\mathcal O_i(x)\rangle
=
\frac{1}{\sqrt g}\frac{\delta W}{\delta\lambda^i(x)}.
$$

These expectation values are evaluated in the theory with the sources turned on. This matters. The symbol

$$
\langle\mathcal O_i(x)\rangle_{g,A,\lambda}
$$

means the one-point function in the deformed background, not necessarily the vacuum one-point function of the original flat-space CFT.

For most flat-space CFTs on $\mathbb R^d$, one-point functions of non-identity primary operators vanish when all sources are set to zero:

$$
\langle\mathcal O_i(x)\rangle_{\lambda=0}=0.
$$

But they need not vanish in a nontrivial state, on curved space, at finite temperature, in the presence of defects, or when sources are nonzero.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Sources, generating functional, responses, connected correlators, and the holographic on-shell action](/figures/cft/sources-generating-functional-hierarchy.svg)

<figcaption>

Background sources define the Euclidean functional $\mathcal Z=e^{-W}$. First derivatives of $W$ give one-point responses such as $\langle T\rangle$, $\langle J\rangle$, and $\langle\mathcal O\rangle$. Higher derivatives give connected correlators, up to the sign $(-1)^{n-1}$ in the convention $W=-\log\mathcal Z$. In AdS/CFT, sources are boundary values of bulk fields and $W_{\mathrm{CFT}}$ is computed by the renormalized on-shell bulk action in the classical limit.

</figcaption>
</figure>

## Full correlators versus connected correlators

The partition function $\mathcal Z$ generates ordinary, not necessarily connected, correlation functions. The functional $W=-\log\mathcal Z$ generates connected correlation functions.

To see the sign carefully, consider a single scalar source $\lambda(x)$ coupled as

$$
S[\lambda]
=
S_0+
\int d^d x\sqrt g\,\lambda(x)\mathcal O(x).
$$

Then

$$
\frac{1}{\sqrt g}\frac{\delta W}{\delta\lambda(x)}
=
\langle\mathcal O(x)\rangle_\lambda.
$$

The second derivative gives the linear response:

$$
\frac{1}{\sqrt{g(x)}\sqrt{g(y)}}
\frac{\delta^2 W}{\delta\lambda(x)\delta\lambda(y)}
=
-\langle\mathcal O(x)\mathcal O(y)\rangle_{c,\lambda}
+\text{contact terms}.
$$

At separated points, and when the operator itself has no explicit source dependence,

$$
\boxed{
\langle\mathcal O(x)\mathcal O(y)\rangle_c
=
-
\frac{1}{\sqrt{g(x)}\sqrt{g(y)}}
\frac{\delta^2 W}{\delta\lambda(x)\delta\lambda(y)}
\bigg|_{\lambda=0}.
}
$$

More generally,

$$
\boxed{
\langle\mathcal O(x_1)\cdots\mathcal O(x_n)\rangle_c
=
(-1)^{n-1}
\frac{1}{\sqrt{g_1}\cdots\sqrt{g_n}}
\frac{\delta^n W}{\delta\lambda(x_1)\cdots\delta\lambda(x_n)}
\bigg|_{\lambda=0}
}
$$

at separated points. Here $g_i=g(x_i)$.

Equivalently, the expansion of $W$ around zero source is

$$
W[\lambda]
=
W[0]
+
\sum_{n=1}^{\infty}
\frac{(-1)^{n+1}}{n!}
\int d^d x_1\sqrt{g_1}\cdots d^d x_n\sqrt{g_n}\,
\lambda(x_1)\cdots\lambda(x_n)
\langle\mathcal O(x_1)\cdots\mathcal O(x_n)\rangle_c.
$$

The alternating sign is not physics. It is a bookkeeping consequence of the Euclidean convention $S[\lambda]=S_0+\int\lambda\mathcal O$ and $W=-\log\mathcal Z$.

## What sources know about dimensions

If $\mathcal O_i$ is a scalar primary of scaling dimension $\Delta_i$, then the source $\lambda^i$ has engineering dimension

$$
[\lambda^i]=d-\Delta_i.
$$

This follows from the requirement that the deformation

$$
\int d^d x\,\lambda^i\mathcal O_i
$$

be dimensionless. A constant source is therefore:

| Operator dimension | Source type | Interpretation |
|---|---|---|
| $\Delta_i<d$ | relevant | drives the CFT away from the fixed point in the IR |
| $\Delta_i=d$ | marginal | may preserve conformality if the beta function vanishes |
| $\Delta_i>d$ | irrelevant | grows toward the UV and usually requires extra UV data |

The source $\lambda^i$ can also be position-dependent. A position-dependent source is not simply a coupling constant; it is a background field. If the source is varied in space, translation invariance is explicitly broken, and the stress tensor Ward identity notices this.

For example, with scalar sources turned on, the diffeomorphism Ward identity has the schematic form

$$
\nabla_\mu\langle T^\mu{}_{\nu}\rangle
=
F^a_{\nu\mu}\langle J^\mu_a\rangle
+
\langle\mathcal O_i\rangle\nabla_\nu\lambda^i
+
\text{anomaly terms}.
$$

This equation says exactly what it should say. A background gauge field can exert a force on the CFT, and a spatially varying scalar source can inject momentum.

## Source transformations and Ward identities

The cleanest derivation of Ward identities is not to insert currents manually. It is to demand that $W[g,A,\lambda]$ be invariant under transformations of the background sources.

### Background gauge transformations

Suppose the CFT has a global symmetry group $G$. We couple its current to a background gauge field $A_\mu^a$. If the scalar sources $\lambda^i$ transform in some representation of $G$, then under an infinitesimal background gauge transformation,

$$
\delta_\alpha A_\mu^a=D_\mu\alpha^a,
$$

$$
\delta_\alpha\lambda^i
=-\alpha^a(t_a)^i{}_j\lambda^j,
$$

where the sign is a convention for the representation matrices $t_a$. Gauge invariance of $W$ gives

$$
0=\delta_\alpha W
=
\int d^d x\sqrt g\,
\left(
\langle J^\mu_a\rangle D_\mu\alpha^a
-
\langle\mathcal O_i\rangle\alpha^a(t_a)^i{}_j\lambda^j
\right)
$$

when there is no anomaly. Integrating by parts gives

$$
D_\mu\langle J^\mu_a\rangle
=
-
\langle\mathcal O_i\rangle(t_a)^i{}_j\lambda^j.
$$

If the scalar sources vanish, this reduces to current conservation:

$$
D_\mu\langle J^\mu_a\rangle=0.
$$

If there is an anomaly, the right-hand side receives an additional local functional of the background fields:

$$
D_\mu\langle J^\mu_a\rangle
=
-
\langle\mathcal O_i\rangle(t_a)^i{}_j\lambda^j
+
\mathcal A_a[A,g,\lambda].
$$

An anomaly is not a failure of the method. It is exactly what the source formalism is designed to expose.

### Weyl transformations

A CFT should also know how to respond to a Weyl rescaling of the background metric. Let

$$
\delta_\sigma g_{\mu\nu}=2\sigma g_{\mu\nu}.
$$

If $\mathcal O_i$ is a primary operator of dimension $\Delta_i$, its source transforms as a spurion of dimension $d-\Delta_i$:

$$
\delta_\sigma\lambda^i
=-(d-\Delta_i)\sigma\lambda^i.
$$

Then the Weyl variation of $W$ gives

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma
\left[
\langle T^\mu{}_{\mu}\rangle
-
\sum_i(d-\Delta_i)\lambda^i\langle\mathcal O_i\rangle
\right].
$$

At a conformal fixed point with all scalar sources turned off, the right-hand side is zero in odd dimensions on a topologically trivial flat background, and equals the Weyl anomaly in even dimensions on curved backgrounds:

$$
\langle T^\mu{}_{\mu}\rangle
=
\mathcal A[g,A].
$$

In flat space with no anomaly and no sources,

$$
\langle T^\mu{}_{\mu}\rangle=0.
$$

This is the source-functional version of the stress-tensor tracelessness condition.

## Contact terms are part of the theory

A common mistake is to think that contact terms are ignorable technicalities. They are not. Contact terms are exactly where background-field definitions, anomalies, and Ward identities live.

For example, the separated-point two-point function of scalar primaries is fixed by conformal symmetry:

$$
\langle\mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{G_{ij}}{|x|^{2\Delta_i}}
\qquad
\text{if }\Delta_i=\Delta_j.
$$

But the full distribution may also contain terms supported at $x=0$, such as derivatives of delta functions. These are contact terms. In the generating functional, they arise from local terms in $W$:

$$
W_{\mathrm{ct}}[\lambda]
=
\int d^d x\sqrt g\,
\left(
C_{ij}\lambda^i\lambda^j R
+
D_{ij}\nabla_\mu\lambda^i\nabla^\mu\lambda^j
+
\cdots
\right).
$$

Differentiating $W_{\mathrm{ct}}$ gives contributions only when insertion points collide. Such terms are usually scheme-dependent, because one may add finite local counterterms. But not all contact terms are arbitrary. Anomalous contact terms can be protected and physically meaningful.

In AdS/CFT this distinction is mirrored by holographic renormalization. Divergent local terms must be subtracted by boundary counterterms. Finite local counterterms change scheme-dependent contact terms. The nonlocal part of the renormalized on-shell action gives separated-point CFT correlators.

## Sources, states, and boundary conditions

A source is not the same thing as a state.

A source changes the action or background:

$$
S\to S+\int\lambda\mathcal O.
$$

A state specifies which expectation values are taken. In Lorentzian QFT, states are selected by initial conditions, density matrices, or operator insertions. In Euclidean QFT, states can be prepared by path integrals with specified boundary conditions or insertions.

This distinction becomes essential in holography. Near the AdS boundary, a scalar bulk field dual to an operator of dimension $\Delta$ behaves schematically as

$$
\phi(z,x)
\sim
z^{d-\Delta}\lambda(x)
+
z^{\Delta}A(x)
+
\cdots,
\qquad z\to0.
$$

The coefficient $\lambda(x)$ is the source. The coefficient $A(x)$ is related to the expectation value $\langle\mathcal O(x)\rangle$, after holographic renormalization. The precise normalization depends on conventions, counterterms, and possible logarithmic terms, but the conceptual split is robust:

$$
\boxed{
\text{non-normalizable mode}
\leftrightarrow
\text{source},
\qquad
\text{normalizable mode}
\leftrightarrow
\text{response/state data}.
}
$$

This is the standard quantization statement. In the Breitenlohner-Freedman window where alternate quantization is allowed, the two independent asymptotic coefficients can exchange roles after an appropriate Legendre transform. We will return to that refinement later.

This is one of the reasons generating functionals are the natural language of AdS/CFT.

## Legendre transforms and effective actions

Although the connected generating functional $W$ is the main object for AdS/CFT, it is useful to know the related effective action. Define the source-dependent one-point function

$$
\varphi_i(x)
=
\frac{1}{\sqrt g}\frac{\delta W}{\delta\lambda^i(x)}
=
\langle\mathcal O_i(x)\rangle_\lambda.
$$

A Legendre transform exchanges the source $\lambda^i$ for the response $\varphi_i$. With our sign convention, a natural definition is

$$
\Gamma[\varphi]
=
W[\lambda]
-
\int d^d x\sqrt g\,\lambda^i\varphi_i,
$$

where $\lambda$ is eliminated in favor of $\varphi$. Then

$$
\frac{1}{\sqrt g}\frac{\delta\Gamma}{\delta\varphi_i(x)}
=
-\lambda^i(x).
$$

This object is useful when discussing spontaneous symmetry breaking, effective potentials, double-trace deformations, and alternative quantization in AdS. But for the basic holographic dictionary, $W[\lambda]$ is primary: the boundary value of the bulk field is the source, and differentiating $W$ gives the response.

## Double-trace deformations as a preview

The source formalism also makes multi-trace deformations almost automatic. Suppose a large-$N$ CFT contains a single-trace scalar operator $\mathcal O$. A double-trace deformation has the form

$$
S_f
=
S_{\mathrm{CFT}}
+
\frac{f}{2}\int d^d x\,\mathcal O(x)^2.
$$

This is not a linear source, but it can be studied by introducing an auxiliary field $\sigma(x)$:

$$
\exp\left[-\frac{f}{2}\int\mathcal O^2\right]
\propto
\int[D\sigma]\,
\exp\left[
-\int\left(
\frac{1}{2f}\sigma^2+i\sigma\mathcal O
\right)
\right],
$$

up to contour and sign conventions. The double-trace deformation is thereby converted into a source problem for $\mathcal O$. In AdS/CFT, double-trace deformations correspond to mixed boundary conditions for the dual bulk field. This will become important later, especially in large-$N$ CFT.

## Holographic checkpoint

The source formalism is the sharpest way to state the AdS/CFT dictionary:

$$
\boxed{
\mathcal Z_{\mathrm{CFT}}[g_{\mu\nu},A_\mu^a,\lambda^i]
=
\mathcal Z_{\mathrm{bulk}}[G_{MN}\to g_{\mu\nu},\,\mathcal A_M^a\to A_\mu^a,\,\phi^i\to\lambda^i].
}
$$

In the classical bulk limit,

$$
W_{\mathrm{CFT}}[g,A,\lambda]
=
-\log\mathcal Z_{\mathrm{CFT}}
\simeq
S^{\mathrm{os}}_{\mathrm{ren}}[g,A,\lambda].
$$

Therefore,

$$
\langle\mathcal O_i(x)\rangle
=
\frac{1}{\sqrt g}\frac{\delta S^{\mathrm{os}}_{\mathrm{ren}}}{\delta\lambda^i(x)},
$$

$$
\langle J^\mu_a(x)\rangle
=
\frac{1}{\sqrt g}\frac{\delta S^{\mathrm{os}}_{\mathrm{ren}}}{\delta A_\mu^a(x)},
$$

$$
\langle T^{\mu\nu}(x)\rangle
=
\frac{2}{\sqrt g}\frac{\delta S^{\mathrm{os}}_{\mathrm{ren}}}{\delta g_{\mu\nu}(x)},
$$

in the convention of this course. Higher functional derivatives of $S^{\mathrm{os}}_{\mathrm{ren}}$ give connected CFT correlators at leading order in the bulk saddle expansion.

This is why so much of practical AdS/CFT consists of the following steps:

1. Choose boundary sources.
2. Solve bulk equations with those boundary conditions.
3. Renormalize the on-shell action.
4. Differentiate with respect to the sources.

All four steps are just the source-response logic of QFT written geometrically.

## Common pitfalls

### Pitfall 1: confusing $\mathcal Z$ and $W$

The partition function $\mathcal Z$ generates full correlators. The functional $W=-\log\mathcal Z$ generates connected correlators, with the sign $(-1)^{n-1}$ in the convention used here.

### Pitfall 2: forgetting the sign convention

If one defines $\mathcal W=\log\mathcal Z$ and couples sources as $e^{+\int J\mathcal O}$, connected correlators are derivatives of $\mathcal W$ without the alternating signs above. Both conventions are common. Mixing them is the real danger.

### Pitfall 3: treating all contact terms as meaningless

Many contact terms are scheme-dependent. Some are anomaly-related and physical. The source functional is the right place to tell the difference.

### Pitfall 4: mistaking a source for a dynamical field

In the CFT, $g_{\mu\nu}$, $A_\mu^a$, and $\lambda^i$ are background sources. They are not integrated over. In the bulk dual, the fields whose boundary values equal these sources are dynamical in the interior, but their boundary values are fixed when computing $\mathcal Z_{\mathrm{bulk}}$.

### Pitfall 5: thinking the source is the vev

The source is boundary data. The vev is the response. In AdS language, the source and response are usually the two independent asymptotic coefficients of a bulk field.

## Summary

Sources turn local operators into functional derivatives:

$$
\langle\mathcal O_i(x)\rangle
=
\frac{1}{\sqrt g}\frac{\delta W}{\delta\lambda^i(x)}.
$$

The connected generating functional in this course is

$$
W=-\log\mathcal Z.
$$

Therefore separated-point connected correlators obey

$$
\langle\mathcal O(x_1)\cdots\mathcal O(x_n)\rangle_c
=
(-1)^{n-1}
\frac{1}{\sqrt{g_1}\cdots\sqrt{g_n}}
\frac{\delta^n W}{\delta\lambda(x_1)\cdots\delta\lambda(x_n)}
\bigg|_{\lambda=0}.
$$

Background gauge invariance, diffeomorphism invariance, and Weyl covariance of $W$ generate the current, stress-tensor, and trace Ward identities. Contact terms are controlled by local terms in $W$.

In AdS/CFT,

$$
W_{\mathrm{CFT}}[\text{sources}]
\simeq
S_{\mathrm{ren}}^{\mathrm{os}}[\text{bulk fields with fixed boundary values}],
$$

so the QFT source-response formalism becomes the practical prescription for computing holographic one-point functions and correlators.

## Exercises

### Exercise 1 — The sign of the connected two-point function

Let

$$
\mathcal Z[\lambda]
=
\int[D\Phi]e^{-S_0-\int d^d x\,\lambda(x)\mathcal O(x)},
\qquad
W[\lambda]=-\log\mathcal Z[\lambda].
$$

Assume $\mathcal O$ has no explicit dependence on $\lambda$. Show that

$$
\frac{\delta^2 W}{\delta\lambda(x)\delta\lambda(y)}
=
-\langle\mathcal O(x)\mathcal O(y)\rangle_c.
$$

<details><summary><strong>Solution</strong></summary>

First,

$$
\frac{\delta W}{\delta\lambda(x)}
=
-\frac{1}{\mathcal Z}\frac{\delta\mathcal Z}{\delta\lambda(x)}.
$$

Since

$$
\frac{\delta\mathcal Z}{\delta\lambda(x)}
=
-\mathcal Z\langle\mathcal O(x)\rangle,
$$

we get

$$
\frac{\delta W}{\delta\lambda(x)}
=
\langle\mathcal O(x)\rangle.
$$

Now differentiate once more:

$$
\frac{\delta}{\delta\lambda(y)}\langle\mathcal O(x)\rangle
=
\frac{\delta}{\delta\lambda(y)}
\left(
\frac{1}{\mathcal Z}\int[D\Phi]\,\mathcal O(x)e^{-S_0-\int\lambda\mathcal O}
\right).
$$

The derivative of the numerator gives

$$
-\langle\mathcal O(x)\mathcal O(y)\rangle.
$$

The derivative of $1/\mathcal Z$ gives

$$
+\langle\mathcal O(x)\rangle\langle\mathcal O(y)\rangle.
$$

Therefore

$$
\frac{\delta^2 W}{\delta\lambda(x)\delta\lambda(y)}
=
-\langle\mathcal O(x)\mathcal O(y)\rangle
+
\langle\mathcal O(x)\rangle\langle\mathcal O(y)\rangle
=
-\langle\mathcal O(x)\mathcal O(y)\rangle_c.
$$

</details>

### Exercise 2 — Source dimension

Let $\mathcal O$ be a scalar primary of dimension $\Delta$ in a $d$-dimensional CFT. Show that the source $\lambda$ in

$$
\int d^d x\,\lambda\mathcal O
$$

has dimension $d-\Delta$. Then classify the deformation as relevant, marginal, or irrelevant.

<details><summary><strong>Solution</strong></summary>

The action is dimensionless. Since

$$
[d^d x]=-d,
\qquad
[\mathcal O]=\Delta,
$$

we need

$$
[d^d x]+[\lambda]+[\mathcal O]=0.
$$

Thus

$$
-d+[\lambda]+\Delta=0,
$$

so

$$
[\lambda]=d-\Delta.
$$

If $\Delta<d$, then $[\lambda]>0$ and the deformation is relevant. If $\Delta=d$, it is marginal. If $\Delta>d$, it is irrelevant.

</details>

### Exercise 3 — Gauge Ward identity with charged sources

Assume

$$
\delta W
=
\int d^d x\sqrt g\,
\left(
\langle J^\mu_a\rangle\delta A_\mu^a
+
\langle\mathcal O_i\rangle\delta\lambda^i
\right).
$$

Under a background gauge transformation,

$$
\delta_\alpha A_\mu^a=D_\mu\alpha^a,
\qquad
\delta_\alpha\lambda^i=-\alpha^a(t_a)^i{}_j\lambda^j.
$$

Derive the Ward identity for $D_\mu\langle J^\mu_a\rangle$ assuming no anomaly.

<details><summary><strong>Solution</strong></summary>

Gauge invariance says $\delta_\alpha W=0$. Therefore

$$
0=
\int d^d x\sqrt g\,
\left(
\langle J^\mu_a\rangle D_\mu\alpha^a
-
\langle\mathcal O_i\rangle\alpha^a(t_a)^i{}_j\lambda^j
\right).
$$

Integrate the first term by parts:

$$
\int d^d x\sqrt g\,\langle J^\mu_a\rangle D_\mu\alpha^a
=
-
\int d^d x\sqrt g\,\alpha^aD_\mu\langle J^\mu_a\rangle,
$$

assuming the boundary term vanishes. Then

$$
0=
-\int d^d x\sqrt g\,\alpha^a
\left(
D_\mu\langle J^\mu_a\rangle
+
\langle\mathcal O_i\rangle(t_a)^i{}_j\lambda^j
\right).
$$

Since $\alpha^a(x)$ is arbitrary,

$$
D_\mu\langle J^\mu_a\rangle
=
-
\langle\mathcal O_i\rangle(t_a)^i{}_j\lambda^j.
$$

When $\lambda^i=0$, this reduces to current conservation.

</details>

### Exercise 4 — Weyl Ward identity with scalar sources

Assume

$$
\delta W
=
\frac12\int d^d x\sqrt g\,\langle T^{\mu\nu}\rangle\delta g_{\mu\nu}
+
\int d^d x\sqrt g\,\langle\mathcal O_i\rangle\delta\lambda^i.
$$

Under a Weyl transformation,

$$
\delta_\sigma g_{\mu\nu}=2\sigma g_{\mu\nu},
\qquad
\delta_\sigma\lambda^i=-(d-\Delta_i)\sigma\lambda^i.
$$

Show that the Weyl variation of $W$ is

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma
\left[
\langle T^\mu{}_{\mu}\rangle
-
\sum_i(d-\Delta_i)\lambda^i\langle\mathcal O_i\rangle
\right].
$$

<details><summary><strong>Solution</strong></summary>

Insert the Weyl variations into the first-variation formula. The metric term gives

$$
\frac12\int d^d x\sqrt g\,\langle T^{\mu\nu}\rangle(2\sigma g_{\mu\nu})
=
\int d^d x\sqrt g\,\sigma\langle T^\mu{}_{\mu}\rangle.
$$

The scalar-source term gives

$$
\int d^d x\sqrt g\,\langle\mathcal O_i\rangle
\left[-(d-\Delta_i)\sigma\lambda^i\right]
=
-
\int d^d x\sqrt g\,\sigma
\sum_i(d-\Delta_i)\lambda^i\langle\mathcal O_i\rangle.
$$

Adding both terms yields

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma
\left[
\langle T^\mu{}_{\mu}\rangle
-
\sum_i(d-\Delta_i)\lambda^i\langle\mathcal O_i\rangle
\right].
$$

If the theory is Weyl invariant and has no anomaly, the bracket must vanish.

</details>

### Exercise 5 — Holographic one-point function from an on-shell action

Suppose the renormalized Euclidean bulk on-shell action for a scalar source has the quadratic form

$$
S_{\mathrm{ren}}^{\mathrm{os}}[\lambda]
=
\frac12\int d^d x\,d^d y\,\lambda(x)K(x,y)\lambda(y),
$$

with $K(x,y)=K(y,x)$. In the convention $W_{\mathrm{CFT}}\simeq S_{\mathrm{ren}}^{\mathrm{os}}$, compute $\langle\mathcal O(x)\rangle_\lambda$ and the connected two-point function.

<details><summary><strong>Solution</strong></summary>

The one-point function is the first functional derivative:

$$
\langle\mathcal O(x)\rangle_\lambda
=
\frac{\delta W}{\delta\lambda(x)}
=
\frac{\delta S_{\mathrm{ren}}^{\mathrm{os}}}{\delta\lambda(x)}.
$$

Using the symmetry of $K$,

$$
\frac{\delta S_{\mathrm{ren}}^{\mathrm{os}}}{\delta\lambda(x)}
=
\int d^d y\,K(x,y)\lambda(y).
$$

Thus

$$
\langle\mathcal O(x)\rangle_\lambda
=
\int d^d y\,K(x,y)\lambda(y).
$$

The second derivative of $W$ is

$$
\frac{\delta^2 W}{\delta\lambda(x)\delta\lambda(y)}=K(x,y).
$$

But with the convention $W=-\log\mathcal Z$ and $S=S_0+\int\lambda\mathcal O$, the connected two-point function is minus the second derivative of $W$:

$$
\langle\mathcal O(x)\mathcal O(y)\rangle_c
=
- K(x,y).
$$

In other sign conventions, the final sign may be absorbed into the definition of the source coupling or of the generating functional. The invariant statement is that the kernel of the quadratic on-shell action determines the two-point function.

</details>
