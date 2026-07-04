---
title: "Scalar Two-Point Functions"
description: "A detailed first computation of a CFT two-point function from a massive scalar field in Euclidean AdS using the GKP/Witten prescription."
sidebar:
  order: 30
---

The previous page gave the GKP/Witten prescription:

$$
W_{\text{CFT}}[\phi_{(0)}]
\approx
-S_{\text{ren,on-shell}}[\phi_{(0)}].
$$

Now we use it for the first time.

The goal is to compute the two-point function of a scalar primary operator $\mathcal O$ in a $d$-dimensional CFT from a free massive scalar field $\phi$ in Euclidean AdS$_{d+1}$. The result must have the conformal form

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\frac{C_{\mathcal O}}{|x|^{2\Delta}},
$$

where $\Delta$ is the scaling dimension of $\mathcal O$. The holographic calculation will explain both pieces: the power $2\Delta$ comes from the near-boundary behavior of the bulk field, and the normalization $C_{\mathcal O}$ comes from the normalization of the bulk action.

This page is deliberately detailed. It is the first calculation in the course where the phrase “compute a CFT correlator from gravity” becomes literal.

<figure class="doc-figure" style="--figure-width: 58rem;">

![The scalar two-point function calculation: source, regular bulk solution, near-boundary response, renormalized on-shell action, and CFT two-point function.](/figures/course/scalar-two-point-functions.svg)

<figcaption>

The scalar two-point function calculation. A boundary source $\phi_{(0)}(k)$ fixes the leading falloff of a regular Euclidean bulk solution. The subleading coefficient is proportional to $k^{2\nu}\phi_{(0)}(k)$, where $\nu=\Delta-d/2$. The renormalized on-shell action is quadratic in $\phi_{(0)}$, and two functional derivatives give $\langle \mathcal O\mathcal O\rangle$.

</figcaption>
</figure>

## Setup

Use Euclidean Poincaré AdS$_{d+1}$,

$$
ds^2
=
\frac{L^2}{z^2}
\left(
dz^2+d x^i d x^i
\right),
\qquad
z>0,
$$

where $i=1,\ldots,d$, and the conformal boundary is at $z=0$.

Consider a real scalar field with action

$$
S
=
\frac{\mathcal N_\phi}{2}
\int d^{d+1}X\sqrt{g}
\left(
g^{MN}\partial_M\phi\partial_N\phi
+
m^2\phi^2
\right).
$$

The constant $\mathcal N_\phi$ is an overall normalization. In a full supergravity compactification it is determined by the ten-dimensional action and by the normalization of the Kaluza–Klein mode. In this page we keep it explicit.

The equation of motion is

$$
(\nabla^2-m^2)\phi=0.
$$

In Poincaré coordinates,

$$
\sqrt{g}=\left(\frac{L}{z}\right)^{d+1},
\qquad
g^{zz}=g^{ij}\delta_{ij}=\frac{z^2}{L^2}.
$$

The scalar equation becomes

$$
z^{d+1}\partial_z\!\left(z^{1-d}\partial_z\phi\right)
+
z^2\partial_i\partial_i\phi
-
m^2L^2\phi
=
0.
$$

## Near-boundary behavior and the dimension

Near $z=0$, derivatives along the boundary are subleading compared with radial powers. Try

$$
\phi(z,x)\sim z^\alpha f(x).
$$

The leading radial equation gives

$$
\alpha(\alpha-d)-m^2L^2=0.
$$

Thus

$$
\alpha=\Delta
\qquad
\text{or}
\qquad
\alpha=d-\Delta,
$$

where

$$
m^2L^2=\Delta(\Delta-d).
$$

It is useful to define

$$
\nu
=
\sqrt{\frac{d^2}{4}+m^2L^2},
\qquad
\Delta
=
\frac d2+\nu.
$$

Then the two asymptotic powers are

$$
d-\Delta=\frac d2-\nu,
\qquad
\Delta=\frac d2+\nu.
$$

In standard quantization,

$$
\phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)
+
z^\Delta A(x)
+
\cdots .
$$

The source is $\phi_{(0)}(x)$, and the response coefficient $A(x)$ is related to the expectation value. The two-point function is the linear response of $A$ to $\phi_{(0)}$.

## Fourier transform

Because Euclidean Poincaré AdS is translation invariant along the boundary, Fourier transform along the $x^i$ directions:

$$
\phi(z,x)
=
\int\frac{d^d k}{(2\pi)^d}
e^{ik\cdot x}
\phi_k(z),
\qquad
k=\sqrt{k_i k_i}.
$$

The equation of motion becomes

$$
z^{d+1}\partial_z\!\left(z^{1-d}\partial_z\phi_k\right)
-
z^2 k^2 \phi_k
-
m^2L^2\phi_k
=
0.
$$

Equivalently,

$$
z^2\phi_k''-(d-1)z\phi_k'
-
(k^2z^2+m^2L^2)\phi_k
=
0.
$$

Write

$$
\phi_k(z)=z^{d/2}f_k(z).
$$

Then $f_k$ obeys the modified Bessel equation

$$
z^2 f_k''
+
z f_k'
-
(k^2z^2+\nu^2)f_k
=
0.
$$

The two independent solutions are

$$
I_\nu(kz),
\qquad
K_\nu(kz).
$$

In Euclidean AdS, regularity in the interior $z\to\infty$ selects $K_\nu(kz)$, because $I_\nu(kz)$ grows exponentially while $K_\nu(kz)$ decays exponentially.

## The normalized bulk solution

For noninteger $\nu$, the small-argument expansion is

$$
K_\nu(u)
=
2^{\nu-1}\Gamma(\nu)u^{-\nu}
+
2^{-\nu-1}\Gamma(-\nu)u^\nu
+
\cdots .
$$

The regular solution whose leading boundary coefficient is $\phi_{(0)}(k)$ is

$$
\phi_k(z)
=
\phi_{(0)}(k)\,
\mathcal K_\nu(k,z),
$$

with

$$
\mathcal K_\nu(k,z)
=
\frac{2^{1-\nu}}{\Gamma(\nu)}
k^\nu z^{d/2}K_\nu(kz).
$$

Indeed, as $z\to0$,

$$
\mathcal K_\nu(k,z)
=
z^{d/2-\nu}
+
\frac{\Gamma(-\nu)}{\Gamma(\nu)}
2^{-2\nu}
k^{2\nu}
z^{d/2+\nu}
+
\cdots
+
\text{local terms}.
$$

Since

$$
d/2-\nu=d-\Delta,
\qquad
d/2+\nu=\Delta,
$$

we identify

$$
A(k)
=
\frac{\Gamma(-\nu)}{\Gamma(\nu)}
2^{-2\nu}
k^{2\nu}
\phi_{(0)}(k)
+
\text{local terms}.
$$

The phrase “local terms” matters. The expansion also contains powers such as $k^2z^{d-\Delta+2}$, $k^4z^{d-\Delta+4}$, and so on. These are determined locally by the source. After holographic renormalization, they contribute contact terms to the CFT correlator.

The nonlocal part is the $k^{2\nu}$ term. It is the part that becomes the separated-point power law $|x|^{-2\Delta}$.

## On-shell action

On shell, the scalar action reduces to a boundary term. With a cutoff surface $z=\epsilon$ and outward normal pointing toward smaller $z$, one finds

$$
S_{\epsilon,\text{on-shell}}
=
-\frac{\mathcal N_\phi}{2}
\int_{z=\epsilon} d^d x
\sqrt{\gamma}\,
\phi\, n^z\partial_z\phi
$$

or, equivalently,

$$
S_{\epsilon,\text{on-shell}}
=
-\frac{\mathcal N_\phi L^{d-1}}{2}
\int d^d x\,
\epsilon^{1-d}\phi(\epsilon,x)\partial_z\phi(\epsilon,x),
$$

up to the sign convention for the outward normal. What matters for the CFT correlator is the renormalized finite part after counterterms are added.

Holographic renormalization gives the standard result

$$
\langle \mathcal O(k)\rangle_{\phi_{(0)}}
=
\mathcal N_\phi L^{d-1}
(2\Delta-d)\,
A(k)
+
\text{local terms}.
$$

Using $2\Delta-d=2\nu$, the nonlocal momentum-space two-point function is

$$
\langle \mathcal O(k)\mathcal O(-k)\rangle_{\text{nonlocal}}
=
\mathcal N_\phi L^{d-1}
(2\nu)
\frac{\Gamma(-\nu)}{\Gamma(\nu)}
2^{-2\nu}
k^{2\nu}.
$$

This expression is best understood modulo local terms. If $\nu$ is an integer, the formula is obtained by analytic continuation and contains a logarithm after subtracting poles:

$$
k^{2\nu}
\quad
\longrightarrow
\quad
k^{2\nu}\log\frac{k^2}{\mu^2}
\qquad
(\nu\in\mathbb Z_{\ge0}),
$$

again up to polynomial contact terms. The scale $\mu$ is the renormalization scale.

## Position-space answer

For noninteger $\nu$, the Fourier transform identity is

$$
\int\frac{d^d k}{(2\pi)^d}
e^{ik\cdot x}
(k^2)^\nu
=
\frac{2^{2\nu}\Gamma(d/2+\nu)}
{\pi^{d/2}\Gamma(-\nu)}
\frac{1}{|x|^{d+2\nu}},
$$

understood by analytic continuation as a distribution.

Since

$$
d+2\nu=2\Delta,
$$

the separated-point two-point function is

$$
\boxed{
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\mathcal N_\phi L^{d-1}
\frac{(2\Delta-d)\Gamma(\Delta)}
{\pi^{d/2}\Gamma(\Delta-d/2)}
\frac{1}{|x|^{2\Delta}}
}
$$

up to the normalization convention for $\mathcal O$ and up to contact terms.

This is exactly the form required by conformal invariance. The holographic calculation does more than recover the form: it relates the coefficient to the normalization of the bulk kinetic term.

## Position-space bulk-to-boundary propagator

The same result can be obtained directly in position space. The Euclidean bulk-to-boundary propagator is

$$
K_\Delta(z,x;x')
=
C_\Delta
\left(
\frac{z}{z^2+|x-x'|^2}
\right)^\Delta,
$$

with

$$
C_\Delta
=
\frac{\Gamma(\Delta)}
{\pi^{d/2}\Gamma(\Delta-d/2)}.
$$

It is normalized so that

$$
\lim_{z\to0}
z^{\Delta-d}
K_\Delta(z,x;x')
=
\delta^{(d)}(x-x').
$$

The classical solution is

$$
\phi(z,x)
=
\int d^d x'\,
K_\Delta(z,x;x')\phi_{(0)}(x').
$$

The renormalized quadratic on-shell action can be written as

$$
S_{\text{ren}}^{(2)}
=
-\frac{\mathcal N_\phi L^{d-1}}{2}
(2\Delta-d)
C_\Delta
\int d^d x\,d^d y\,
\frac{\phi_{(0)}(x)\phi_{(0)}(y)}
{|x-y|^{2\Delta}},
$$

again up to contact terms. Differentiating twice and using $W=-S_{\text{ren}}$ gives the two-point function above.

This position-space expression is often the cleanest way to see conformal invariance. The momentum-space expression is often the cleanest way to do the calculation.

## Where the power law comes from

The result

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
\propto
\frac{1}{|x|^{2\Delta}}
$$

has two complementary explanations.

From the CFT point of view, conformal symmetry fixes the two-point function of scalar primaries:

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\frac{C_{\mathcal O}}{|x|^{2\Delta}}.
$$

From the bulk point of view, the exponent comes from the indicial equation near the AdS boundary:

$$
\alpha(\alpha-d)=m^2L^2.
$$

The normalizable response is separated from the source by $2\nu=2\Delta-d$ radial powers. In momentum space that separation appears as $k^{2\nu}$. Fourier transforming $k^{2\nu}$ gives $|x|^{-d-2\nu}=|x|^{-2\Delta}$.

This is the first concrete example of the rule:

$$
\boxed{
\text{near-boundary radial scaling}
\quad
\longleftrightarrow
\quad
\text{boundary conformal scaling}.
}
$$

## Normalization and operator conventions

The coefficient $C_{\mathcal O}$ is not universal by itself. If we rescale the boundary operator,

$$
\mathcal O\to a\mathcal O,
$$

then the source must rescale as

$$
\phi_{(0)}\to a^{-1}\phi_{(0)}
$$

to keep $\int\phi_{(0)}\mathcal O$ fixed. The two-point coefficient then changes as

$$
C_{\mathcal O}\to a^2 C_{\mathcal O}.
$$

In a top-down string compactification, the normalization of $\mathcal O$ is fixed by matching the bulk field normalization to the microscopic CFT convention. In a bottom-up model, $\mathcal N_\phi$ is often a phenomenological input.

This is why the power law is usually more robust than the absolute coefficient unless one has carefully normalized both sides.

## What happens when $\nu$ is an integer?

Many important examples have integer $\nu$. For instance, a massless scalar in AdS$_5$ has $d=4$, $m^2=0$, and hence $\Delta=4$, $\nu=2$.

The formula with $\Gamma(-\nu)$ has a pole at integer $\nu$. This does not mean the correlator is infinite. It means that the naive noninteger formula must be renormalized. After subtracting local divergences, the momentum-space correlator contains

$$
k^{2\nu}\log\frac{k^2}{\mu^2}.
$$

The logarithm is precisely what one expects when Fourier transforming a separated-point correlator of the form $1/|x|^{2\Delta}$ in cases where the transform is singular as an ordinary function. The logarithm also encodes scale dependence of contact terms.

The lesson is:

$$
\Gamma(-\nu)\text{ pole}
\quad
\longleftrightarrow
\quad
\text{local divergence plus logarithmic renormalized correlator}.
$$

Separated-point correlators remain conformal.

## Standard versus alternate quantization

For

$$
-\frac{d^2}{4}
<
m^2L^2
<
-\frac{d^2}{4}+1,
$$

both radial falloffs are normalizable. In this window, there are two possible CFT quantizations:

$$
\Delta_+
=
\frac d2+\nu,
\qquad
\Delta_-
=
\frac d2-\nu.
$$

The standard quantization treats the coefficient of $z^{d-\Delta_+}$ as the source and gives an operator of dimension $\Delta_+$. The alternate quantization treats the other falloff as the source and gives an operator of dimension $\Delta_-$.

This page uses standard quantization. The alternate case requires a Legendre transform of the generating functional and will be discussed later with the Breitenlohner–Freedman bound.

## A clean example: $d=3$, $m^2L^2=-2$

Take AdS$_4$ with a scalar mass

$$
m^2L^2=-2.
$$

Then

$$
\nu
=
\sqrt{\frac{9}{4}-2}
=
\frac12.
$$

The standard dimension is

$$
\Delta
=
\frac32+\frac12=2.
$$

The separated-point correlator is

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\mathcal N_\phi L^2
\frac{(2\Delta-d)\Gamma(\Delta)}
{\pi^{d/2}\Gamma(\Delta-d/2)}
\frac{1}{|x|^{2\Delta}}.
$$

Since $d=3$ and $\Delta=2$,

$$
2\Delta-d=1,
\qquad
\Gamma(\Delta)=\Gamma(2)=1,
\qquad
\Gamma(\Delta-d/2)=\Gamma(1/2)=\sqrt{\pi}.
$$

Thus

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\frac{\mathcal N_\phi L^2}{\pi^2}
\frac{1}{|x|^4}.
$$

This is a useful check because no logarithmic subtlety appears: $\nu=1/2$ is noninteger.

## What has been computed?

We computed the vacuum Euclidean two-point function of a scalar primary in a CFT on flat Euclidean space. More precisely, we computed the leading large-$N$, strong-coupling, classical-bulk answer for the operator dual to a free bulk scalar field.

We did not compute:

- a Lorentzian retarded correlator;
- a finite-temperature correlator;
- a correlator in an excited state;
- loop corrections in the bulk;
- stringy corrections;
- contact terms fixed by a specific renormalization scheme;
- the normalization of a specific $\mathcal N=4$ SYM operator.

Each of those requires additional data. But the structure of the calculation will recur throughout the course.

## Dictionary checkpoint

The scalar two-point calculation extracts the following dictionary entries:

| Bulk statement | Boundary statement |
|---|---|
| scalar mass $m^2L^2$ | operator dimension $\Delta(\Delta-d)$ |
| leading falloff $z^{d-\Delta}\phi_{(0)}$ | source for $\mathcal O$ |
| regular Euclidean interior solution | vacuum Euclidean correlator |
| response coefficient $A(k)\propto k^{2\nu}\phi_{(0)}(k)$ | linear response of $\langle\mathcal O(k)\rangle$ |
| renormalized quadratic on-shell action | connected two-point function |
| local counterterms | contact terms and scheme dependence |
| radial scaling gap $2\nu$ | momentum-space scaling $k^{2\nu}$ |

The key conceptual bridge is

$$
\text{solve a bulk boundary-value problem}
\quad
\longrightarrow
\quad
\text{read off a CFT correlator}.
$$

## Common confusions

### “The divergent terms are mistakes.”

They are not mistakes. The divergent terms are the bulk version of UV divergences in the boundary theory. Holographic renormalization removes them by local counterterms. The nonlocal part of the answer is the physical separated-point correlator.

### “The coefficient of $z^\Delta$ is automatically the vev.”

It is proportional to the vev in simple standard cases, but the precise one-point function is the variation of the renormalized action. Local terms, logarithms, curvature couplings, and alternate quantization can modify the naive identification.

### “The $K_\nu$ solution is chosen because it is normalizable near the boundary.”

No. Near the boundary, $K_\nu$ contains both source and response falloffs. It is chosen in Euclidean AdS because it is regular in the interior. Boundary normalizability and interior regularity are different conditions.

### “The two-point coefficient is a universal prediction.”

The power law is fixed by conformal symmetry and the mass-dimension relation. The coefficient depends on the normalization of the bulk field and the boundary operator. In top-down examples it can be fixed precisely; in bottom-up models it is a convention or phenomenological parameter.

### “Momentum-space polynomials can be ignored everywhere.”

Polynomial terms in $k^2$ are contact terms. They do not affect separated points, but they matter for Ward identities, anomalies, scheme dependence, and finite counterterms. Ignore them only when the observable really is insensitive to contact terms.

## Exercises

### Exercise 1: Derive the mass-dimension relation

Starting from the near-boundary ansatz

$$
\phi(z,x)\sim z^\alpha f(x),
$$

derive

$$
m^2L^2=\Delta(\Delta-d).
$$

<details>
<summary><strong>Solution</strong></summary>

Near the boundary, ignore boundary derivatives. The scalar equation reduces to

$$
z^{d+1}\partial_z\!\left(z^{1-d}\partial_z z^\alpha\right)
-
m^2L^2z^\alpha
=
0.
$$

Compute

$$
\partial_z z^\alpha=\alpha z^{\alpha-1},
$$

so

$$
z^{1-d}\partial_z z^\alpha
=
\alpha z^{\alpha-d}.
$$

Then

$$
\partial_z\left(\alpha z^{\alpha-d}\right)
=
\alpha(\alpha-d)z^{\alpha-d-1}.
$$

Multiplying by $z^{d+1}$ gives

$$
\alpha(\alpha-d)z^\alpha.
$$

Therefore

$$
\alpha(\alpha-d)-m^2L^2=0.
$$

The two roots are $\alpha=\Delta$ and $\alpha=d-\Delta$, so

$$
m^2L^2=\Delta(\Delta-d).
$$

</details>

### Exercise 2: Check the regular solution

Show that

$$
\mathcal K_\nu(k,z)
=
\frac{2^{1-\nu}}{\Gamma(\nu)}
k^\nu z^{d/2}K_\nu(kz)
$$

has leading behavior $z^{d-\Delta}$ as $z\to0$.

<details>
<summary><strong>Solution</strong></summary>

For small $u$ and noninteger $\nu$,

$$
K_\nu(u)
=
2^{\nu-1}\Gamma(\nu)u^{-\nu}
+\cdots .
$$

Thus

$$
\mathcal K_\nu(k,z)
\sim
\frac{2^{1-\nu}}{\Gamma(\nu)}
k^\nu z^{d/2}
\left[
2^{\nu-1}\Gamma(\nu)(kz)^{-\nu}
\right].
$$

The constants and powers of $k$ cancel, leaving

$$
\mathcal K_\nu(k,z)
\sim
z^{d/2-\nu}.
$$

Since $\Delta=d/2+\nu$,

$$
d/2-\nu=d-\Delta.
$$

Therefore the leading behavior is $z^{d-\Delta}$.

</details>

### Exercise 3: Compute the response coefficient

Using the second term in the small-$u$ expansion

$$
K_\nu(u)
=
2^{\nu-1}\Gamma(\nu)u^{-\nu}
+
2^{-\nu-1}\Gamma(-\nu)u^\nu
+
\cdots,
$$

show that

$$
A(k)
=
2^{-2\nu}
\frac{\Gamma(-\nu)}{\Gamma(\nu)}
k^{2\nu}
\phi_{(0)}(k)
$$

for noninteger $\nu$, up to local terms.

<details>
<summary><strong>Solution</strong></summary>

Insert the second term into the normalized solution:

$$
\mathcal K_\nu(k,z)
=
\frac{2^{1-\nu}}{\Gamma(\nu)}
k^\nu z^{d/2}K_\nu(kz).
$$

The second term gives

$$
\frac{2^{1-\nu}}{\Gamma(\nu)}
k^\nu z^{d/2}
\left[
2^{-\nu-1}\Gamma(-\nu)(kz)^\nu
\right].
$$

The numerical factor is

$$
2^{1-\nu}2^{-\nu-1}=2^{-2\nu}.
$$

The powers are

$$
k^\nu k^\nu=k^{2\nu},
\qquad
z^{d/2}z^\nu=z^{d/2+\nu}=z^\Delta.
$$

Thus the coefficient of $z^\Delta$ is

$$
A(k)
=
2^{-2\nu}
\frac{\Gamma(-\nu)}{\Gamma(\nu)}
k^{2\nu}
\phi_{(0)}(k),
$$

up to local terms from the analytic part of the expansion.

</details>

### Exercise 4: The AdS$_4$ example

For $d=3$ and $m^2L^2=-2$, compute $\Delta_+$ and the separated-point two-point function coefficient in terms of $\mathcal N_\phi$ and $L$.

<details>
<summary><strong>Solution</strong></summary>

First,

$$
\nu
=
\sqrt{\frac{d^2}{4}+m^2L^2}
=
\sqrt{\frac94-2}
=
\frac12.
$$

Therefore

$$
\Delta_+
=
\frac d2+\nu
=
\frac32+\frac12
=
2.
$$

The coefficient formula gives

$$
C_{\mathcal O}
=
\mathcal N_\phi L^{d-1}
\frac{(2\Delta-d)\Gamma(\Delta)}
{\pi^{d/2}\Gamma(\Delta-d/2)}.
$$

Substitute $d=3$ and $\Delta=2$:

$$
2\Delta-d=1,
\qquad
\Gamma(2)=1,
\qquad
\Gamma(1/2)=\sqrt{\pi}.
$$

Therefore

$$
C_{\mathcal O}
=
\mathcal N_\phi L^2
\frac{1}{\pi^{3/2}\sqrt{\pi}}
=
\frac{\mathcal N_\phi L^2}{\pi^2}.
$$

So

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\frac{\mathcal N_\phi L^2}{\pi^2}
\frac{1}{|x|^4}.
$$

</details>

## Further reading

- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- D. Z. Freedman, S. D. Mathur, A. Matusis, and L. Rastelli, [Correlation Functions in the CFT(d)/AdS(d+1) Correspondence](https://arxiv.org/abs/hep-th/9804058).
- E. D'Hoker and D. Z. Freedman, [Supersymmetric Gauge Theories and the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0201253).
- S. de Haro, K. Skenderis, and S. N. Solodukhin, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
