---
title: "QFT Data and Generating Functionals"
description: "Sources, generating functionals, connected correlators, Ward identities, and the field-theory language behind the GKPW prescription in AdS/CFT."
sidebar:
  order: 10
---

AdS/CFT begins with an equality of quantum theories, but the first formula one actually uses is an equality of **generating functionals**. Before we talk about bulk fields, boundary values, or on-shell gravitational actions, we need the field-theory side of that statement.

The basic idea is simple. Couple a source $J(x)$ to a local operator $\mathcal O(x)$, compute the partition functional $Z[J]$, and then differentiate with respect to $J$. The derivatives give correlation functions of $\mathcal O$. The logarithm $W[J]=\log Z[J]$ gives connected correlation functions.

This is the language in which the GKP/Witten prescription is written:

$$
Z_{\mathrm{CFT}}[J]
=
Z_{\mathrm{bulk}}[\phi \to J].
$$

The equation says that the same object can be computed in two radically different ways. The CFT computes it as a quantum field theory with sources. The bulk computes it as a gravitational or string-theoretic partition function with prescribed boundary data.

This page develops the field-theory half of that statement.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Sources generate QFT correlation functions](/figures/course/qft-generating-functional.svg)

<figcaption>

A source $J_i(x)$ couples to an operator $\mathcal O_i(x)$. The partition functional $Z_{\rm QFT}[J]$ generates full correlators, while $W[J]=\log Z[J]$ generates connected correlators. This is the field-theory structure that the bulk on-shell action reproduces in AdS/CFT.

</figcaption>
</figure>

## Why this matters for holography

The gravitational side of AdS/CFT does not usually hand us boundary correlators directly. It hands us a bulk variational problem.

For a scalar field $\phi$ in AdS, one solves the bulk equation of motion subject to a near-boundary condition. The boundary coefficient is interpreted as a source $\phi_{(0)}(x)$ for a CFT operator $\mathcal O(x)$. The renormalized on-shell bulk action is then a functional of that source:

$$
S_{\text{ren,on-shell}}[\phi_{(0)}].
$$

In Euclidean signature and in the classical gravity approximation, the bulk partition function has the schematic saddle-point form

$$
Z_{\mathrm{bulk}}[\phi_{(0)}]
\approx
\exp\!\left(-S_{\text{ren,on-shell}}[\phi_{(0)}]\right).
$$

Thus the CFT generating functional is related to the on-shell action by

$$
W_{\mathrm{CFT}}[\phi_{(0)}]
=
\log Z_{\mathrm{CFT}}[\phi_{(0)}]
\approx
-S_{\text{ren,on-shell}}[\phi_{(0)}].
$$

All later computations of holographic one-point functions, two-point functions, Ward identities, transport coefficients, and response functions are refinements of this sentence.

The important point for now is not the bulk formula. The important point is what $W[J]$ means in an ordinary QFT.

## QFT data as a response problem

A quantum field theory is not just a Lagrangian. A Lagrangian is one way of presenting the theory. The physical data include:

- the Hilbert space and its states;
- local operators and their correlation functions;
- conserved currents and stress tensors;
- the response to external fields;
- the behavior under changes of scale;
- the partition function on different spacetime manifolds and backgrounds.

In a conformal field theory, especially in flat space, much of the local data can be organized into the spectrum of local operators and their operator product coefficients. For holography, however, the most useful package is the generating functional with sources.

Think of $Z[J]$ as a response machine. We perturb the theory by external fields $J_i(x)$, and the derivatives of $Z[J]$ tell us how the theory responds.

The source $J_i(x)$ can be a purely formal book-keeping device, introduced only so that we can differentiate and then set it to zero. But it can also be a real physical coupling. For example:

$$
S \to S - \int d^d x\, J(x)\mathcal O(x)
$$

is a deformation of the theory by the operator $\mathcal O$. If $J$ is constant, it is an ordinary coupling. If $J(x)$ varies in spacetime, it is a local external field.

This dual role is essential in AdS/CFT. The same boundary datum can be used either to compute correlators around an undeformed CFT or to define a genuinely deformed theory.

## Euclidean generating functional

Let $M$ be a Euclidean $d$-dimensional spacetime with metric $g_{\mu\nu}$. Let $\Phi$ denote all dynamical fields of the QFT, and let $\mathcal O_i$ be a set of local operators. We couple sources $J_i$ to these operators by defining

$$
Z[J]
=
\int \mathcal D\Phi\,
\exp\!\left(
-S[\Phi]
+
\sum_i \int_M d^d x\sqrt g\, J_i(x)\mathcal O_i(x)
\right).
$$

Throughout this course, when no confusion is likely, we abbreviate the source coupling as

$$
\int J_i\mathcal O_i
\equiv
\sum_i \int_M d^d x\sqrt g\, J_i(x)\mathcal O_i(x).
$$

The expectation value in the presence of sources is

$$
\langle X\rangle_J
=
\frac{1}{Z[J]}
\int \mathcal D\Phi\, X[\Phi]\,
\exp\!\left(
-S[\Phi]+
\int J_i\mathcal O_i
\right).
$$

The connected generating functional is

$$
W[J]=\log Z[J].
$$

Some authors define $W_E[J]=-\log Z[J]$ in Euclidean signature. This course uses $W[J]=\log Z[J]$ unless stated otherwise. With this convention, the classical Euclidean gravity saddle gives $W\approx -S_{\text{ren,on-shell}}$.

:::note
If you use the source convention $S\to S+\int J\mathcal O$ rather than $S\to S-\int J\mathcal O$, several signs below flip. Nothing physical depends on this choice, but one must be consistent.
:::

## Functional derivatives

The defining operation is differentiation with respect to the source. We use the covariant convention

$$
\delta W[J]
=
\sum_i \int_M d^d x\sqrt g\,\delta J_i(x)\,
\frac{1}{\sqrt g}\frac{\delta W[J]}{\delta J_i(x)}.
$$

Then

$$
\frac{1}{\sqrt g}\frac{\delta W[J]}{\delta J_i(x)}
=
\langle \mathcal O_i(x)\rangle_J.
$$

In flat space, where $\sqrt g=1$, this reduces to the familiar expression

$$
\frac{\delta W[J]}{\delta J_i(x)}
=
\langle \mathcal O_i(x)\rangle_J.
$$

The second derivative gives the connected two-point function in the presence of sources:

$$
\frac{1}{\sqrt{g_x}\sqrt{g_y}}
\frac{\delta^2 W[J]}{\delta J_i(x)\delta J_j(y)}
=
\langle \mathcal O_i(x)\mathcal O_j(y)\rangle_J
-
\langle \mathcal O_i(x)\rangle_J
\langle \mathcal O_j(y)\rangle_J,
$$

provided the operators themselves do not have explicit source dependence. More generally, source-dependent definitions of composite operators can generate contact terms. Such terms are not mistakes; they are part of the local scheme dependence of QFT.

At zero source, the connected two-point function is therefore

$$
\langle \mathcal O_i(x)\mathcal O_j(y)\rangle_c
=
\left.
\frac{1}{\sqrt{g_x}\sqrt{g_y}}
\frac{\delta^2 W[J]}{\delta J_i(x)\delta J_j(y)}
\right|_{J=0}.
$$

The general connected $n$-point function is

$$
\langle
\mathcal O_{i_1}(x_1)\cdots \mathcal O_{i_n}(x_n)
\rangle_c
=
\left.
\frac{1}{\sqrt{g_{x_1}}\cdots\sqrt{g_{x_n}}}
\frac{\delta^n W[J]}
{\delta J_{i_1}(x_1)\cdots \delta J_{i_n}(x_n)}
\right|_{J=0}.
$$

This formula is the field-theory ancestor of the holographic rule “differentiate the on-shell action with respect to boundary data.”

## Why $\log Z$ gives connected correlators

It is useful to see explicitly why $W[J]=\log Z[J]$ generates connected correlators.

For one operator $\mathcal O$, define

$$
Z[J]
=
\left\langle
\exp\!\left(\int J\mathcal O\right)
\right\rangle_{0} Z[0],
$$

where $\langle\cdots\rangle_0$ denotes expectation values in the theory without sources. Expanding the exponential gives full correlators:

$$
\frac{Z[J]}{Z[0]}
=
1
+
\int J(x)\langle \mathcal O(x)\rangle_0
+
\frac{1}{2}\int J(x)J(y)
\langle \mathcal O(x)\mathcal O(y)\rangle_0
+
\cdots .
$$

Taking the logarithm reorganizes this expansion into cumulants:

$$
W[J]-W[0]
=
\int J(x)\langle \mathcal O(x)\rangle_0
+
\frac{1}{2}\int J(x)J(y)
\langle \mathcal O(x)\mathcal O(y)\rangle_c
+
\cdots .
$$

The logarithm removes disconnected pieces because disconnected vacuum diagrams exponentiate. This is why tree-level bulk Witten diagrams compute connected CFT correlators, while disconnected pieces are generated by exponentiating the connected functional.

## Normalized and unnormalized functionals

One often removes the vacuum normalization by defining

$$
\mathcal Z[J]
=
\frac{Z[J]}{Z[0]},
\qquad
\mathcal W[J]
=
\log \mathcal Z[J]
=
W[J]-W[0].
$$

This normalization ensures

$$
\mathcal Z[0]=1,
\qquad
\mathcal W[0]=0.
$$

It does not change connected correlators with at least one source derivative. It only removes source-independent vacuum terms.

In holography, source-independent constants in the on-shell action often correspond to vacuum energies, Casimir terms, or scheme-dependent local counterterms. They can matter for thermodynamics, but they do not affect ordinary connected correlators at separated points.

## Sources, couplings, and dimensions

If $\mathcal O_i$ has scaling dimension $\Delta_i$ in a $d$-dimensional CFT, the source has engineering dimension

$$
[J_i]=d-\Delta_i,
$$

because the source deformation

$$
\int d^d x\, J_i(x)\mathcal O_i(x)
$$

must be dimensionless.

This simple relation is one of the first pieces of the holographic dictionary. Later we will see that for a scalar field in $\mathrm{AdS}_{d+1}$,

$$
m^2L^2=\Delta(\Delta-d).
$$

Thus the bulk mass determines the scaling dimension of the boundary operator, and the boundary behavior of the bulk field determines the source.

The sign of $d-\Delta$ gives the usual classification of deformations:

| Operator dimension | Source dimension | Deformation |
|---|---:|---|
| $\Delta<d$ | $[J]>0$ | relevant |
| $\Delta=d$ | $[J]=0$ | classically marginal |
| $\Delta>d$ | $[J]<0$ | irrelevant |

Relevant deformations grow in the infrared. Irrelevant deformations require UV care. Marginal deformations can remain marginal, become marginally relevant, or become marginally irrelevant depending on quantum effects.

In the bulk, these distinctions are reflected in the near-boundary falloffs of fields and in the difficulty of defining boundary conditions for the corresponding modes.

## The source is not the expectation value

One repeated confusion in AdS/CFT is to identify the source with the expectation value. They are different pieces of the response problem.

The source is what we control. It appears in the definition of the theory:

$$
Z[J]
=
\int \mathcal D\Phi\,e^{-S+\int J\mathcal O}.
$$

The expectation value is what the theory returns:

$$
\langle \mathcal O(x)\rangle_J
=
\frac{1}{\sqrt g}\frac{\delta W[J]}{\delta J(x)}.
$$

The relation between them is dynamical. In a linear response regime,

$$
\delta \langle \mathcal O(x)\rangle
=
\int d^d y\sqrt{g_y}\,
G_c(x,y)\,\delta J(y),
$$

where

$$
G_c(x,y)=\langle \mathcal O(x)\mathcal O(y)\rangle_c.
$$

In holography, the same distinction appears as the difference between the leading boundary coefficient of a bulk field and the subleading response coefficient. The precise identification requires holographic renormalization.

## Several sources at once

Real theories have many operators. A compact way to write the sourced generating functional is

$$
Z[J_1,J_2,\ldots]
=
\left\langle
\exp\!\left(
\sum_i\int J_i\mathcal O_i
\right)
\right\rangle Z[0].
$$

Mixed derivatives generate mixed correlators:

$$
\left.
\frac{\delta^2 W}{\delta J_i(x)\delta J_j(y)}
\right|_{J=0}
=
\langle \mathcal O_i(x)\mathcal O_j(y)\rangle_c.
$$

If the operators carry indices, the sources carry the corresponding dual indices. For example:

$$
\int d^d x\sqrt g\, A_\mu J^\mu
$$

couples a background gauge field $A_\mu$ to a conserved current $J^\mu$, while the metric couples to the stress tensor.

The sources should be viewed as coordinates on a space of theories or backgrounds. A local QFT is probed by turning on these coordinates and asking how the generating functional changes.

## Background fields and Ward identities

The most important sources in holography are not always scalar. A conserved current and the stress tensor have special sources.

A global symmetry current $J^\mu$ couples to a background gauge field $A_\mu$:

$$
Z[A]
=
\int \mathcal D\Phi\,
\exp\!\left(-S[\Phi]+\int d^d x\sqrt g\, A_\mu J^\mu\right).
$$

The one-point function is

$$
\langle J^\mu(x)\rangle_A
=
\frac{1}{\sqrt g}\frac{\delta W[A]}{\delta A_\mu(x)}.
$$

If the symmetry is non-anomalous and no charged sources are turned on, background gauge invariance implies

$$
W[A+d\alpha]=W[A].
$$

Varying this relation gives

$$
0
=
\int d^d x\sqrt g\,
\langle J^\mu\rangle_A\nabla_\mu\alpha
=
-\int d^d x\sqrt g\,\alpha\nabla_\mu\langle J^\mu\rangle_A,
$$

so

$$
\nabla_\mu\langle J^\mu\rangle_A=0.
$$

This is a Ward identity. In AdS/CFT, the corresponding bulk statement is gauge invariance of the bulk gauge field.

The stress tensor is similar but even more important. It is sourced by the background metric:

$$
Z[g_{\mu\nu}]
=
\int \mathcal D\Phi\,e^{-S[\Phi;g]}.
$$

With the Euclidean convention used here,

$$
\delta W[g]
=
\frac{1}{2}\int d^d x\sqrt g\,
\langle T^{\mu\nu}\rangle_g\,\delta g_{\mu\nu},
$$

or equivalently

$$
\langle T^{\mu\nu}(x)\rangle_g
=
\frac{2}{\sqrt g}\frac{\delta W[g]}{\delta g_{\mu\nu}(x)}.
$$

Diffeomorphism invariance implies stress-tensor conservation. In the absence of additional sources and anomalies,

$$
\nabla_\mu\langle T^{\mu\nu}\rangle_g=0.
$$

For a CFT in flat space, scale invariance further implies the trace relation

$$
\langle T^\mu{}_{\mu}\rangle=0,
$$

up to conformal anomalies in even dimensions and contact terms. With scalar sources present, the trace Ward identity is modified schematically to

$$
\langle T^\mu{}_{\mu}\rangle_J
=
\sum_i (d-\Delta_i)J_i\langle \mathcal O_i\rangle_J
+
\text{anomalies and beta-function terms}.
$$

This equation will reappear in holographic renormalization, where Ward identities follow from bulk constraints near the AdS boundary.

## Euclidean, Lorentzian, and real-time correlators

The Euclidean generating functional computes Euclidean correlation functions. In a Lorentzian QFT one often writes a formal source functional

$$
Z_L[J]
=
\int \mathcal D\Phi\,
\exp\!\left(
iS[\Phi]+i\int J\mathcal O
\right).
$$

This object naturally generates time-ordered correlators, with convention-dependent factors of $i$.

Retarded correlators are different. They describe causal response:

$$
G_R(t,\mathbf x)
=
-i\theta(t)\langle[\mathcal O(t,\mathbf x),\mathcal O(0)]\rangle.
$$

At finite temperature or in real-time nonequilibrium problems, the clean formulation uses a Schwinger–Keldysh contour. In holography, retarded functions are computed by imposing incoming-wave boundary conditions at black-hole horizons. That subject belongs to the real-time unit of the course.

For now, the lesson is simply this: do not blindly convert Euclidean formulas into retarded Lorentzian formulas. The words “generating functional” are used in both settings, but the boundary conditions and analytic continuation matter.

## Effective action and one-particle-irreducible data

The connected functional $W[J]$ is not the only useful functional. Define the classical expectation value

$$
\varphi_i(x)
=
\frac{1}{\sqrt g}\frac{\delta W[J]}{\delta J_i(x)}
=
\langle \mathcal O_i(x)\rangle_J.
$$

When the relation between $J_i$ and $\varphi_i$ can be inverted, the Legendre transform defines the effective action

$$
\Gamma[\varphi]
=
\sum_i\int d^d x\sqrt g\,J_i(x)\varphi_i(x)-W[J].
$$

Then

$$
\frac{1}{\sqrt g}\frac{\delta \Gamma}{\delta \varphi_i(x)}
=
J_i(x).
$$

The effective action generates one-particle-irreducible correlators. It is central in ordinary QFT, spontaneous symmetry breaking, and Wilsonian effective field theory.

In standard AdS/CFT computations, however, the first object is usually $W[J]$, because the bulk partition function naturally computes the source-dependent generating functional. Legendre transforms become important for alternate quantization, mixed boundary conditions, and multi-trace deformations.

## Contact terms and scheme dependence

Correlation functions at separated points are usually the cleanest observables. At coincident points, local ambiguities appear.

For example, adding a local counterterm depending on the source,

$$
W[J]\to W[J]+\int d^d x\sqrt g\, c\,J(x)^2,
$$

changes the two-point function by

$$
\langle \mathcal O(x)\mathcal O(y)\rangle_c
\to
\langle \mathcal O(x)\mathcal O(y)\rangle_c
+
2c\,\frac{\delta^{(d)}(x-y)}{\sqrt g}.
$$

This is a contact term. It affects coincident-point correlators and momentum-space polynomials, but not separated-point singularities or nonlocal response.

Holographic renormalization is full of such terms. Counterterms are necessary to remove divergences, but finite local counterterms remain a choice of renormalization scheme. A trustworthy holographic computation must distinguish universal nonlocal data from scheme-dependent local data.

## Large-$N$ preview

In holographic CFTs, the generating functional typically has a large-$N$ expansion. For a gauge theory with matrix degrees of freedom, the number of degrees of freedom scales like $N^2$, and one often finds

$$
W[J]
=
N^2 w_0[J]+w_1[J]+\frac{1}{N^2}w_2[J]+\cdots .
$$

The leading term is classical from the bulk viewpoint. The subleading terms are bulk quantum corrections. This is the field-theory origin of the statement that large $N$ suppresses bulk loops.

Operator normalization matters. Depending on whether a single-trace operator is written as $\mathrm{Tr}(\cdots)$, $\frac{1}{N}\mathrm{Tr}(\cdots)$, or with a convention that gives an order-one two-point function, powers of $N$ move between the operator and the source. The invariant statement is not a particular normalization, but the hierarchy of connected correlators and the existence of a controlled $1/N$ expansion.

The next pages develop this point carefully.

## The holographic translation

At this stage, the basic field-theory structure is:

$$
J_i(x)
\quad\longrightarrow\quad
Z_{\mathrm{QFT}}[J]
\quad\longrightarrow\quad
W[J]=\log Z[J]
\quad\longrightarrow\quad
\langle \mathcal O_{i_1}\cdots\mathcal O_{i_n}\rangle_c.
$$

The holographic claim is that for special large-$N$ QFTs, the same functional can be computed from a higher-dimensional bulk theory:

$$
Z_{\mathrm{QFT}}[J]
=
Z_{\mathrm{bulk}}[\phi_i\to J_i].
$$

In the classical limit,

$$
W_{\mathrm{QFT}}[J]
\approx
-S_{\text{ren,on-shell}}[J].
$$

So the field-theory operation

$$
\frac{\delta}{\delta J_i(x)}
$$

becomes the bulk operation “vary the renormalized on-shell action with respect to the boundary value of the dual field.”

This is the technical bridge from QFT to gravity.

## Dictionary checkpoint

The lesson of this page can be compressed into the following dictionary.

| QFT concept | Later bulk interpretation |
|---|---|
| source $J_i(x)$ | boundary value of a bulk field $\phi_i$ |
| operator $\mathcal O_i(x)$ | bulk field species $\phi_i$ |
| $Z_{\mathrm{QFT}}[J]$ | bulk partition function with boundary data |
| $W[J]=\log Z[J]$ | minus the renormalized on-shell action at leading classical order |
| $\delta W/\delta J_i$ | one-point function / response coefficient |
| $\delta^n W/\delta J^n$ | connected $n$-point function |
| background gauge field $A_\mu$ | boundary value of a bulk gauge field |
| background metric $g_{\mu\nu}$ | boundary value of the bulk metric |
| Ward identities | bulk gauge and diffeomorphism constraints |
| local counterterms | holographic counterterms and scheme dependence |

The table is only a preview. Each line becomes precise only after we specify the AdS asymptotics, boundary conditions, and renormalization prescription.

## Common confusions

### “$Z[J]$ and $W[J]$ generate the same correlators.”

$Z[J]$ generates full correlators. $W[J]=\log Z[J]$ generates connected correlators. The distinction matters because classical bulk diagrams compute connected correlators, and disconnected correlators arise by exponentiating them.

### “The source is the same thing as the expectation value.”

No. The source is what we choose. The expectation value is the response of the theory. In holography, these become different coefficients in the near-boundary expansion of a bulk field.

### “Contact terms are errors.”

Contact terms are often physical or scheme-dependent local contributions. They are especially important in Ward identities, anomalies, and stress-tensor correlators. They should be tracked, not automatically discarded.

### “A source must be infinitesimal.”

A source can be infinitesimal if we are computing linear response, but the generating functional is defined for finite sources when the theory is well-defined. Finite sources correspond to deformations or nontrivial background fields.

### “Euclidean correlators are automatically retarded correlators.”

No. Euclidean correlators, time-ordered Lorentzian correlators, and retarded correlators are related but distinct. Analytic continuation and boundary conditions matter, especially at finite temperature.

## Exercises

### Exercise 1: Derive the connected two-point function

Starting from

$$
W[J]=\log Z[J],
$$

show that

$$
\frac{\delta^2 W}{\delta J(x)\delta J(y)}
=
\langle\mathcal O(x)\mathcal O(y)\rangle_J
-
\langle\mathcal O(x)\rangle_J\langle\mathcal O(y)\rangle_J
$$

in flat space, assuming $\mathcal O$ has no explicit source dependence.

<details>
<summary><strong>Solution</strong></summary>

First,

$$
\frac{\delta W}{\delta J(x)}
=
\frac{1}{Z[J]}\frac{\delta Z[J]}{\delta J(x)}.
$$

Since differentiating the source term brings down $\mathcal O(x)$,

$$
\frac{\delta Z[J]}{\delta J(x)}
=Z[J]\langle \mathcal O(x)\rangle_J.
$$

Therefore

$$
\frac{\delta W}{\delta J(x)}
=\langle \mathcal O(x)\rangle_J.
$$

Differentiate again:

$$
\frac{\delta^2 W}{\delta J(x)\delta J(y)}
=
\frac{\delta}{\delta J(y)}\left(\frac{1}{Z}\int \mathcal D\Phi\,\mathcal O(x)e^{-S+\int J\mathcal O}\right).
$$

The derivative acts both on the numerator and on $1/Z$. The numerator gives

$$
\langle\mathcal O(x)\mathcal O(y)\rangle_J,
$$

while the derivative of $1/Z$ gives

$$
-\langle\mathcal O(x)\rangle_J\langle\mathcal O(y)\rangle_J.
$$

Thus

$$
\frac{\delta^2 W}{\delta J(x)\delta J(y)}
=
\langle\mathcal O(x)\mathcal O(y)\rangle_J
-
\langle\mathcal O(x)\rangle_J\langle\mathcal O(y)\rangle_J.
$$

This is the connected two-point function.

</details>

### Exercise 2: Gaussian generating functional

Consider a Euclidean Gaussian theory with action

$$
S[\phi]
=
\frac{1}{2}\int d^d x\,d^d y\,\phi(x)K(x,y)\phi(y),
$$

and source coupling $\int d^d x\,J(x)\phi(x)$. Let $G=K^{-1}$. Show that

$$
\frac{Z[J]}{Z[0]}
=
\exp\!\left(\frac{1}{2}\int d^d x\,d^d y\,J(x)G(x,y)J(y)\right),
$$

and compute the connected two-point function.

<details>
<summary><strong>Solution</strong></summary>

Write the exponent as

$$
-\frac{1}{2}\phi K\phi+J\phi.
$$

Complete the square:

$$
-\frac{1}{2}\phi K\phi+J\phi
=
-\frac{1}{2}(\phi-GJ)K(\phi-GJ)
+
\frac{1}{2}JGJ,
$$

where condensed notation is used:

$$
JGJ
=
\int d^d x\,d^d y\,J(x)G(x,y)J(y).
$$

The shift $\phi\to \phi-GJ$ leaves the Gaussian measure formally unchanged, so

$$
Z[J]
=Z[0]\exp\!\left(\frac{1}{2}JGJ\right).
$$

Therefore

$$
W[J]-W[0]
=\frac{1}{2}JGJ.
$$

Taking two derivatives gives

$$
\left.\frac{\delta^2 W}{\delta J(x)\delta J(y)}\right|_{J=0}
=G(x,y).
$$

Thus the connected two-point function of the free field is the Green function $K^{-1}$.

</details>

### Exercise 3: Source dimensions

In a $d$-dimensional CFT, an operator $\mathcal O$ has scaling dimension $\Delta$. The theory is deformed by

$$
\delta S=-\int d^d x\,J(x)\mathcal O(x).
$$

Find the dimension of $J$. Classify the deformation for $\Delta<d$, $\Delta=d$, and $\Delta>d$.

<details>
<summary><strong>Solution</strong></summary>

The action is dimensionless in units where $\hbar=1$. Since $d^d x$ has dimension $-d$ and $\mathcal O$ has dimension $\Delta$, the source must have dimension

$$
[J]=d-\Delta.
$$

If $\Delta<d$, then $[J]>0$, and the deformation is relevant. If $\Delta=d$, then $[J]=0$, and the deformation is classically marginal. If $\Delta>d$, then $[J]<0$, and the deformation is irrelevant.

In holography, this classification is reflected in the near-boundary behavior of the bulk field dual to $\mathcal O$.

</details>

### Exercise 4: Ward identity from a background gauge field

Let $W[A]$ be invariant under the background gauge transformation

$$
A_\mu\to A_\mu+\nabla_\mu\alpha.
$$

Assume

$$
\delta W[A]
=
\int d^d x\sqrt g\,\langle J^\mu\rangle_A\delta A_\mu.
$$

Show that

$$
\nabla_\mu\langle J^\mu\rangle_A=0
$$

when there are no anomalies and no charged sources.

<details>
<summary><strong>Solution</strong></summary>

Gauge invariance gives

$$
0=\delta_\alpha W[A]
=\int d^d x\sqrt g\,\langle J^\mu\rangle_A\nabla_\mu\alpha.
$$

Integrating by parts and ignoring boundary terms,

$$
0
=-\int d^d x\sqrt g\,\alpha\nabla_\mu\langle J^\mu\rangle_A.
$$

Because $\alpha(x)$ is arbitrary,

$$
\nabla_\mu\langle J^\mu\rangle_A=0.
$$

This is the current-conservation Ward identity. In holography, the corresponding statement comes from gauge invariance and the radial constraint equations of the bulk gauge field.

</details>

### Exercise 5: The sign of the holographic one-point function

Suppose the Euclidean CFT convention is

$$
Z_{\mathrm{CFT}}[J]
=
\left\langle e^{\int J\mathcal O}\right\rangle,
\qquad
W[J]=\log Z[J].
$$

Suppose also that the classical bulk saddle gives

$$
Z_{\mathrm{CFT}}[J]\approx e^{-S_{\text{ren,on-shell}}[J]}.
$$

What is $\langle\mathcal O(x)\rangle_J$ in terms of $S_{\text{ren,on-shell}}$?

<details>
<summary><strong>Solution</strong></summary>

From the CFT convention,

$$
\langle\mathcal O(x)\rangle_J
=
\frac{1}{\sqrt g}\frac{\delta W[J]}{\delta J(x)}.
$$

The saddle approximation gives

$$
W[J]\approx -S_{\text{ren,on-shell}}[J].
$$

Therefore

$$
\langle\mathcal O(x)\rangle_J
\approx
-\frac{1}{\sqrt g}\frac{\delta S_{\text{ren,on-shell}}[J]}{\delta J(x)}.
$$

Some references absorb this minus sign by using a different source convention or by defining the Euclidean generating functional as $W_E=-\log Z$. The physics is unchanged, but the convention must be tracked.

</details>

## Further reading

For the generating-functional language in ordinary QFT, see standard QFT texts such as Peskin and Schroeder, Weinberg, Zinn-Justin, and Coleman. For its role in AdS/CFT, the essential starting points are:

- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
