---
title: "Sobolev Spaces Preview"
description: "A QFT-oriented preview of Sobolev spaces as spaces of weakly differentiable functions and distributions, with applications to finite energy, Green functions, elliptic regularity, boundaries, and the roughness of quantum fields."
sidebar:
  label: "Sobolev Preview"
  order: 8
level: Graduate
status: "Polished draft"
source: "Standard Sobolev-space and elliptic-operator theory, with QFT applications to finite-energy fields, propagators, Gaussian free fields, boundary data, and functional integration."
topics:
  - Sobolev spaces
  - weak derivatives
  - elliptic operators
  - Green functions
  - Gaussian fields
  - QFT regularity
canonicalTopics:
  - sobolev-spaces
  - weak-derivatives
  - elliptic-regularity
  - qft-functional-analysis
researchStatus:
  established:
    - "Sobolev spaces are the standard analytic language for weak derivatives, finite-energy fields, elliptic operators, boundary traces, and distributional regularity."
  active:
    - "In interacting QFT, stochastic PDEs, constructive field theory, and gauge theory, Sobolev-type regularity must be combined with renormalization, nonlinear estimates, gauge fixing, and microlocal control."
---

## Summary

Sobolev spaces are a way to measure how many derivatives an object has when ordinary pointwise differentiability is the wrong standard. They sit between classical functions and distributions. In QFT, that is exactly the terrain we live on.

The basic idea is this:

$$
\text{regularity is measured by weak derivatives, not by pointwise smoothness.}
$$

For an integer $m\geq 0$, the Sobolev space $H^m(\mathbb R^d)$ consists, roughly, of functions whose derivatives up to order $m$ are square-integrable. More generally, for real $s$, the Fourier-space definition is

$$
H^s(\mathbb R^d)
=\left\{u\in\mathcal S'(\mathbb R^d):
(1+|k|^2)^{s/2}\widehat u(k)\in L^2(\mathbb R^d)\right\}.
$$

The norm is

$$
\|u\|_{H^s}^2
=\int\frac{d^dk}{(2\pi)^d}\,(1+|k|^2)^s|\widehat u(k)|^2.
$$

Large positive $s$ means many square-integrable derivatives. $s=0$ gives $L^2$. Negative $s$ allows distributions.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Sobolev regularity scale with negative spaces, L2, weak derivatives, and embedding thresholds.](/figures/math-toolkit/sobolev-regularity-scale.svg)

<figcaption>

Sobolev spaces organize regularity on a scale. Negative spaces contain distributions and sources; sufficiently positive spaces have pointwise control. In a massive Euclidean problem, the Green operator $(-\Delta+m^2)^{-1}$ gains two derivatives when the inverse is well defined.

</figcaption>
</figure>

Sobolev spaces appear whenever we ask any of the following questions.

- Which classical field configurations have finite energy?
- What is the domain of a differential operator?
- How singular is a Green function?
- Which boundary values make sense?
- How rough is a typical Gaussian free field configuration?
- When can two distributions be multiplied?
- Why do propagators improve regularity by two derivatives, but not make singularities disappear?

This page is a preview, not a full course in PDE or functional analysis. It gives the Sobolev facts most often needed by QFT readers and explains how they fit into the analytic infrastructure of distributions, Fourier transforms, Green functions, and functional integrals.

## Prerequisites

You should know the distributional pairing from [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), the role of test functions from [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/), and the Fourier conventions from [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/).

It is also useful to have seen [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/) and [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/), because Sobolev spaces explain why Green functions and quantum fields are usually rougher than smooth functions.

## Core idea

Classical analysis often starts with functions that are differentiable pointwise. QFT does not grant us that luxury. Delta functions, propagators, equal-time commutators, and quantum fields are distributional. Even when a field configuration is an honest function, it may be too rough to differentiate pointwise.

Sobolev spaces solve this by defining derivatives weakly. A function $u$ has weak derivative $v_i$ in the $x^i$ direction if

$$
\int_{\mathbb R^d} d^dx\,v_i(x)\varphi(x)
=-\int_{\mathbb R^d}d^dx\,u(x)\partial_i\varphi(x)
$$

for every compactly supported smooth test function $\varphi$. Equivalently,

$$
v_i=\partial_i u
$$

as a distribution.

The derivative is moved onto the test function, where it is harmless. That is the same integration-by-parts logic that defines distributional derivatives, but Sobolev spaces add a quantitative condition: the weak derivatives must belong to $L^p$, usually $L^2$.

For example, $u(x)=|x|$ on $\mathbb R$ is not differentiable at $x=0$ in the classical sense, but it has weak derivative

$$
u'(x)=\operatorname{sgn}(x)
$$

as a locally integrable function. The kink is allowed. A jump discontinuity is rougher: the weak derivative of the step function contains a delta function.

That is the point. Sobolev spaces do not ask whether derivatives exist as pointwise limits. They ask whether distributional derivatives are controlled by integrability.

## Setup and conventions

This page mostly works on Euclidean $\mathbb R^d$. We write

$$
\int_k\equiv\int\frac{d^dk}{(2\pi)^d},
$$

and use the Fourier transform

$$
\widehat f(k)=\int d^dx\,e^{-ik\cdot x}f(x),
\qquad
f(x)=\int_k e^{ik\cdot x}\widehat f(k).
$$

For a multi-index $\alpha=(\alpha_1,\ldots,\alpha_d)$, define

$$
|\alpha|=\alpha_1+\cdots+\alpha_d,
\qquad
\partial^\alpha=\partial_1^{\alpha_1}\cdots\partial_d^{\alpha_d}.
$$

The Sobolev space $W^{m,p}(\mathbb R^d)$ consists of functions $u\in L^p(\mathbb R^d)$ whose weak derivatives $\partial^\alpha u$ lie in $L^p(\mathbb R^d)$ for all $|\alpha|\leq m$:

$$
W^{m,p}(\mathbb R^d)
=\left\{u\in L^p: \partial^\alpha u\in L^p\text{ for all }|\alpha|\leq m\right\}.
$$

The norm is

$$
\|u\|_{W^{m,p}}
=\left(\sum_{|\alpha|\leq m}\|\partial^\alpha u\|_{L^p}^p\right)^{1/p},
$$

with the usual modification for $p=\infty$.

The Hilbert-space Sobolev spaces are

$$
H^m(\mathbb R^d)=W^{m,2}(\mathbb R^d).
$$

For real $s$, define $H^s$ by Fourier transform:

$$
H^s(\mathbb R^d)
=\left\{u\in\mathcal S'(\mathbb R^d):
(1+|k|^2)^{s/2}\widehat u(k)\in L^2\right\}.
$$

This definition includes noninteger and negative regularity. The factor $1+|k|^2$ is conventional; replacing it by any comparable positive elliptic symbol gives an equivalent norm.

:::note[Why the plus one?]
The weight $(1+|k|^2)^s$ controls both low and high momentum. At large $|k|$, it behaves like $|k|^{2s}$ and measures derivatives. Near $k=0$, it avoids artificial infrared singularities in the definition of the norm.
:::

## Weak derivatives

The weak derivative definition is a direct extension of integration by parts. Suppose $u$ is smooth and decays well. Then

$$
\int d^dx\,(\partial_i u)\varphi
=-\int d^dx\,u\partial_i\varphi.
$$

The right-hand side still makes sense if $u$ is merely locally integrable. So we define $\partial_i u$ to be whatever distribution has that action.

More generally,

$$
\langle \partial^\alpha u,\varphi\rangle
=(-1)^{|\alpha|}\langle u,\partial^\alpha\varphi\rangle.
$$

If this distribution is represented by an $L^p$ function for every $|\alpha|\leq m$, then $u\in W^{m,p}$.

This definition is local. It does not care about a few bad points as long as the distributional derivative remains integrable. That is why Sobolev spaces are the natural spaces for finite-energy classical solutions, weak PDE solutions, and variational methods.

### Example: kinks and jumps

On $\mathbb R$, let

$$
u(x)=|x|.
$$

For $x\neq0$, $u'(x)=\operatorname{sgn}(x)$. Distributionally, the same is true:

$$
u'=\operatorname{sgn}(x).
$$

There is no delta function in $u'$ because $|x|$ is continuous.

But the second weak derivative is

$$
u''=2\delta(x).
$$

So $|x|$ has one locally integrable weak derivative, but its second derivative is distributional.

By contrast, the Heaviside function $\Theta(x)$ has

$$
\Theta'(x)=\delta(x).
$$

A jump discontinuity costs one derivative immediately.

This distinction matters in field theory. Domain walls, shocks, boundaries, and defects often produce weak derivatives or distributional sources. Sobolev language lets us say precisely which singularities are allowed by an action or equation of motion.

## The Hilbert-space case

The space $H^s$ is especially important because it is a Hilbert space. The inner product is

$$
(u,v)_{H^s}
=\int_k (1+|k|^2)^s\widehat u(k)^*\widehat v(k).
$$

For $s=0$,

$$
H^0=L^2.
$$

For integer $m\geq0$, the Fourier definition is equivalent to the weak-derivative definition:

$$
\|u\|_{H^m}^2
\simeq
\sum_{|\alpha|\leq m}\|\partial^\alpha u\|_{L^2}^2.
$$

Here $\simeq$ means equivalence of norms: each side is bounded by a constant times the other. The constants depend on $m$ and $d$, not on $u$.

The inclusions go downward in regularity:

$$
s_1>s_2
\quad\Longrightarrow\quad
H^{s_1}(\mathbb R^d)\subset H^{s_2}(\mathbb R^d).
$$

Positive $s$ means regularity. Negative $s$ means distributional roughness.

A useful duality statement is

$$
(H^s)'\simeq H^{-s},
$$

with the pairing extending the $L^2$ inner product. In QFT language, this is one way to formalize the idea that a source can be rougher than the field it probes.

## Fourier interpretation

The Fourier definition says that $H^s$ controls high-momentum behavior. If $\widehat u(k)$ decays rapidly at large $|k|$, then $u$ is smooth. If $\widehat u(k)$ decays slowly, then $u$ is rough. If it grows polynomially, $u$ may still be a tempered distribution.

The Sobolev norm weights modes by

$$
(1+|k|^2)^s.
$$

Thus high positive $s$ penalizes ultraviolet modes. Negative $s$ tolerates ultraviolet growth.

This is why Sobolev spaces are useful in QFT. The ultraviolet behavior of fields, propagators, loop integrals, and regulators is naturally described by weighted momentum norms.

For example, the delta distribution has Fourier transform

$$
\widehat{\delta}(k)=1.
$$

Its Sobolev norm would be

$$
\|\delta\|_{H^{-s}}^2
=\int_k (1+|k|^2)^{-s}.
$$

This integral converges at large $|k|$ exactly when

$$
s>\frac d2.
$$

So

$$
\delta\in H^{-s}(\mathbb R^d)
\quad\text{for every }s>\frac d2,
$$

but not at the endpoint $s=d/2$.

This single calculation is a good mental anchor: a point source is slightly worse than $H^{-d/2}$.

## Sobolev embedding

Sobolev spaces measure derivatives in an integral sense. Embedding theorems tell us when that integral control implies pointwise control.

A basic form is:

$$
H^s(\mathbb R^d)\subset C^0(\mathbb R^d)
\qquad\text{if}\qquad
s>\frac d2.
$$

More generally,

$$
H^s(\mathbb R^d)\subset C^k(\mathbb R^d)
\qquad\text{if}\qquad
s>k+\frac d2.
$$

This is one reason the dimension $d$ matters so much. In higher dimension, it takes more derivatives in $L^2$ to force continuity.

There is also an important algebra statement:

$$
H^s(\mathbb R^d)\text{ is closed under multiplication if }s>\frac d2.
$$

In other words, sufficiently regular Sobolev functions can be multiplied without leaving the space.

QFT often lives below this threshold. That is why products such as $\phi(x)^2$, $\phi(x)^4$, or $T\{\phi(x)\phi(y)\}$ at coincident points require normal ordering, regularization, or renormalization. The problem is not philosophical. It is an analytic regularity problem.

## Finite energy and classical fields

Consider a real scalar field on Euclidean $\mathbb R^d$ with classical energy functional

$$
E[\phi]
=\frac12\int d^dx\,\left(|\nabla\phi|^2+m^2\phi^2\right).
$$

If $m>0$, finite energy implies

$$
\phi\in H^1(\mathbb R^d).
$$

Indeed,

$$
E[\phi]
=\frac12\int_k (|k|^2+m^2)|\widehat\phi(k)|^2,
$$

which is equivalent to the $H^1$ norm when $m>0$.

This explains a common phrase:

$$
\text{finite energy fields are }H^1\text{ fields.}
$$

But this statement is about classical finite-action configurations. It is not the same as saying that quantum fields sampled from the path integral are usually $H^1$ functions. They are generally much rougher.

## Elliptic operators and Green functions

Let

$$
L=-\Delta+m^2,
\qquad m>0.
$$

In Fourier space,

$$
\widehat{Lu}(k)=(|k|^2+m^2)\widehat u(k).
$$

The operator $L$ lowers Sobolev regularity by two derivatives:

$$
L:H^{s+2}(\mathbb R^d)\to H^s(\mathbb R^d).
$$

Its inverse raises regularity by two derivatives:

$$
L^{-1}:H^s(\mathbb R^d)\to H^{s+2}(\mathbb R^d).
$$

This is the Sobolev-space meaning of a Green function. If

$$
LG=\delta,
$$

then $G=L^{-1}\delta$. Since $\delta\in H^{-s}$ for every $s>d/2$, we get

$$
G\in H^{2-s}\quad\text{for every }s>\frac d2.
$$

For example, in $d=4$ the Green function belongs locally to spaces a little below $H^0$, but its point singularity prevents it from being smooth. The inverse operator improves regularity away from the source, but it cannot erase the source singularity itself.

This is the analytic origin of a familiar physical fact: propagators solve equations with delta-function sources, so they are singular at coincident points.

## Elliptic regularity

Elliptic regularity is the principle that elliptic equations improve regularity.

For the model equation

$$
(-\Delta+m^2)u=f,
$$

one expects

$$
f\in H^s
\quad\Longrightarrow\quad
u\in H^{s+2},
$$

up to boundary conditions, zero modes, and global issues.

The phrase “up to boundary conditions” is doing real work. On a domain with boundary, elliptic regularity depends on the smoothness of the boundary and on the boundary condition. On a compact manifold, zero modes may prevent invertibility unless one projects them out.

In QFT, elliptic regularity is behind many standard tools:

| QFT object | Sobolev interpretation |
|---|---|
| Euclidean kinetic operator | elliptic differential operator |
| propagator | inverse operator, often gaining two derivatives |
| source $J$ | element of a dual Sobolev space |
| Green function singularity | inverse applied to a delta distribution |
| zero mode | obstruction to invertibility |
| gauge redundancy | non-elliptic directions before gauge fixing |
| heat kernel | smoothing operator for positive time |

For gauge fields, the kinetic operator is typically not elliptic before gauge fixing because gauge transformations create degenerate directions. Gauge fixing turns the relevant part of the operator into an elliptic complex or elliptic operator, modulo residual symmetries and zero modes.

## Boundary traces

Sobolev spaces also explain when boundary values are meaningful.

A generic $L^2$ function does not have a well-defined value on a codimension-one boundary. The boundary has measure zero, so changing a representative on the boundary does not change the $L^2$ function.

Sobolev regularity repairs this. Roughly,

$$
H^s(\Omega)\to H^{s-1/2}(\partial\Omega)
$$

is a well-defined trace map when

$$
s>\frac12.
$$

In particular, an $H^1$ field on a region $\Omega$ has a boundary trace in

$$
H^{1/2}(\partial\Omega).
$$

This matters for classical variational principles and for path integrals with boundary conditions. Dirichlet data, Neumann data, gluing formulas, edge modes, and boundary counterterms all depend on which boundary values are analytically meaningful.

A common notation is $H_0^1(\Omega)$: the closure of compactly supported smooth functions in the $H^1$ norm. Informally, these are $H^1$ functions with zero boundary trace. That is the natural domain for many Dirichlet problems.

## Compactness and spectral theory

On a bounded domain or compact manifold, Sobolev embeddings can become compact. A key example is the Rellich compactness theorem:

$$
H^1(\Omega)\hookrightarrow L^2(\Omega)
$$

compactly under suitable assumptions on $\Omega$.

Compactness is not just technical decoration. It implies that many elliptic operators on compact spaces have discrete spectra. For example, the Laplacian on a compact Riemannian manifold has eigenvalues

$$
0\leq \lambda_0\leq\lambda_1\leq\lambda_2\leq\cdots,
\qquad
\lambda_n\to\infty,
$$

with eigenfunctions forming an orthonormal basis of $L^2$.

This is the analytic backbone of mode expansions, finite-volume determinants, zeta regularization, heat-kernel traces, and one-loop partition functions.

When the space is noncompact, the spectrum usually has continuous parts, and infrared behavior becomes more delicate.

## Gaussian free fields are rough

A Euclidean Gaussian free field has covariance

$$
C=(-\Delta+m^2)^{-1}.
$$

In momentum space,

$$
\langle \widehat\phi(k)\widehat\phi(k')\rangle
=(2\pi)^d\delta^{(d)}(k+k')\frac1{k^2+m^2}.
$$

A tempting but wrong slogan is:

$$
\text{the action contains }\int |\nabla\phi|^2,
\text{ so typical fields are }H^1.
$$

The correct statement is subtler. The action is finite on classical $H^1$ configurations, but the Gaussian measure is supported on rougher objects. Mode by mode,

$$
\mathbb E\,\|\phi\|_{H^s}^2
\sim
\int_k \frac{(1+|k|^2)^s}{k^2+m^2}.
$$

At large $|k|$, the integrand behaves like

$$
|k|^{2s-2}.
$$

Including the $d$-dimensional measure, the ultraviolet convergence condition is

$$
s<1-\frac d2.
$$

So in $d=2$, a massive free scalar is roughly in $H^s$ for $s<0$, not in $L^2$ at the endpoint. In $d=4$, it is roughly in $H^s$ only for $s<-1$.

This is one of the cleanest ways to see why local products of quantum fields are singular. A typical quantum field is much rougher than a finite-action classical field.

:::caution[Action domain versus measure support]
The classical action suggests which configurations have finite action. The quantum Gaussian measure is usually supported on distributions rougher than the finite-action space. Treating the path integral as if it were an ordinary integral over finite-action smooth fields is a useful saddle-point heuristic, not a literal description of the measure.
:::

## Products and renormalization

Sobolev spaces clarify why multiplication is easy for smooth functions and hard for quantum fields.

If $s>d/2$, then $H^s$ is an algebra:

$$
u,v\in H^s
\quad\Longrightarrow\quad
uv\in H^s.
$$

Below that threshold, multiplication may still be possible under more refined conditions, but it is no longer automatic. If both factors are distributions with overlapping singularities, the product may not be defined.

This is the analytic shadow of renormalization. Expressions like

$$
\phi^2(x),
\qquad
\phi^4(x),
\qquad
T_{\mu\nu}(x),
\qquad
J_\mu(x)J_\nu(y)\big|_{x=y}
$$

are not automatically meaningful just because the symbols are familiar. They may require normal ordering, point splitting, operator mixing, counterterms, or a definition as composite operators.

Sobolev spaces do not replace renormalization. They explain why renormalization is necessary: the fields are too rough for naive nonlinear operations.

## Local and global Sobolev spaces

The notation $H^s_{\mathrm{loc}}(\Omega)$ means that the object is Sobolev of order $s$ after multiplying by any compactly supported smooth cutoff inside $\Omega$:

$$
u\in H^s_{\mathrm{loc}}(\Omega)
\quad\Longleftrightarrow\quad
\chi u\in H^s(\mathbb R^d)
\text{ for all }\chi\in C_c^\infty(\Omega).
$$

Local regularity ignores behavior at infinity. This is essential in field theory because ultraviolet and infrared questions are different.

A distribution can be locally regular but globally fail to be in a Sobolev space because it does not decay. Conversely, it can decay well at infinity but have a local singularity.

For example, plane waves are smooth locally but not in $L^2(\mathbb R^d)$. Green functions may decay at infinity but be singular at the source. Scattering states and finite-volume states require different global function spaces.

## Sobolev spaces on manifolds

On a smooth compact manifold, Sobolev spaces can be defined using charts and a partition of unity, or more invariantly using an elliptic positive operator such as the Laplacian.

For a compact Riemannian manifold $M$, one may define

$$
\|u\|_{H^s(M)}^2
=\|(1+\Delta)^{s/2}u\|_{L^2(M)}^2,
$$

where $\Delta$ is the nonnegative Laplacian. If

$$
\Delta e_n=\lambda_n e_n,
$$

and

$$
u=\sum_n u_n e_n,
$$

then

$$
\|u\|_{H^s(M)}^2
=\sum_n (1+\lambda_n)^s|u_n|^2.
$$

For vector bundles, one uses a connection and an elliptic operator acting on sections. Gauge theory then adds a further layer: the relevant Sobolev spaces must be chosen compatibly with gauge transformations, gauge fixing, and quotient spaces.

This page does not develop that machinery. The important takeaway is that the Sobolev scale is not tied to flat space. It is a general way to measure regularity using elliptic operators.

## A QFT dictionary

| Mathematical phrase | QFT translation |
|---|---|
| $L^2$ field | square-integrable configuration |
| $H^1$ field | finite kinetic energy, in many scalar examples |
| weak derivative | derivative defined by integration by parts |
| $H^{-s}$ | distributional source or rough field |
| elliptic operator | Euclidean kinetic operator after fixing degeneracies |
| Green operator | inverse kinetic operator, propagator in Euclidean signature |
| trace map | boundary value of a field |
| compact embedding | discrete mode spectrum on compact spaces |
| Sobolev embedding | when finite derivative control implies pointwise regularity |
| multiplication theorem | when nonlinear composite expressions make analytic sense |
| failure of multiplication | reason local composite operators need renormalization |
| measure support below action domain | reason typical path-integral fields are rough |

The dictionary should be used with judgment. Lorentzian hyperbolic equations, gauge constraints, fermions, finite-temperature systems, and noncompact spaces all require additional structure. But the Sobolev viewpoint remains the same: regularity is a scale, and differential operators move objects along it.

## Common pitfalls

**Pitfall 1: Thinking Sobolev functions are necessarily continuous.**

They are not. In $d$ dimensions, $H^s$ embeds into continuous functions only when $s>d/2$. An $H^1$ function in one dimension is much more pointwise controlled than an $H^1$ function in four dimensions.

**Pitfall 2: Confusing finite-action configurations with typical quantum fields.**

The classical scalar action suggests $H^1$, but the Gaussian free field is typically much rougher. The path integral is not literally an integral over smooth finite-action fields.

**Pitfall 3: Treating the delta function as barely singular but harmless.**

The delta distribution is in $H^{-s}$ only for $s>d/2$. A point source gets more singular as the dimension increases.

**Pitfall 4: Assuming propagators always make things smooth.**

An elliptic inverse improves regularity away from sources, but the Green function still carries the singularity of the delta source. Propagators improve; they do not magically sanitize all singularities.

**Pitfall 5: Multiplying distributions because the formula looks familiar.**

Sobolev multiplication theorems have thresholds. QFT products at coincident points often sit below those thresholds, which is why composite operators need definitions.

**Pitfall 6: Ignoring boundary regularity.**

Boundary values are not automatic. Trace theorems say exactly how much regularity is needed for a boundary condition to make sense.

## Relations to other pages

This page extends [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) by adding quantitative regularity. Distributions ask whether an object can be tested. Sobolev spaces ask how many weak derivatives it has, in an integral sense.

It refines [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/) by turning high-momentum behavior into a norm. It also explains why the Green kernels introduced in [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/) and [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/) have controlled but nontrivial singularities.

The next chapter, [Functional Integrals and Determinants](/math-toolkit/functional-integrals-determinants/), uses the same regularity logic when explaining Gaussian measures, determinants, heat kernels, zeta regularization, saddle points, and Jacobians.

## Research status

The basic theory of Sobolev spaces, weak derivatives, trace maps, Sobolev embeddings, and elliptic regularity is established mathematical infrastructure.

The active QFT frontier is not whether Sobolev spaces exist. It is how to combine Sobolev regularity with nonlinear and quantum effects: renormalized products of distributions, singular stochastic PDEs, constructive field theory, gauge-field quotient spaces, moduli spaces of connections, low-regularity Lorentzian evolution, and nonperturbative functional measures.

For most graduate QFT work, Sobolev spaces are best treated as a precision tool. They prevent us from saying “function” when the correct object is a distribution and from saying “smooth” when the correct statement is an $H^s$ estimate.

## Exercises

### Exercise 1: The weak derivative of an absolute value

Show that $u(x)=|x|$ has weak derivative $\operatorname{sgn}(x)$ on $\mathbb R$. Then compute the weak derivative of $\operatorname{sgn}(x)$.

<details><summary><strong>Solution</strong></summary>

For a test function $\varphi\in C_c^\infty(\mathbb R)$,

$$
\int_{\mathbb R} dx\,\operatorname{sgn}(x)\varphi(x)
=\int_0^\infty dx\,\varphi(x)-\int_{-\infty}^0 dx\,\varphi(x).
$$

Integrating by parts separately on the two half-lines gives

$$
-\int_{\mathbb R}dx\,|x|\varphi'(x)
= -\int_0^\infty dx\,x\varphi'(x)+\int_{-\infty}^0 dx\,x\varphi'(x).
$$

The boundary terms at infinity vanish because $\varphi$ is compactly supported. The boundary terms at $0$ vanish because $x=0$. The result is

$$
-\int |x|\varphi'=
\int_0^\infty \varphi-
\int_{-\infty}^0\varphi
=\int \operatorname{sgn}(x)\varphi(x)dx.
$$

Thus

$$
\frac{d}{dx}|x|=\operatorname{sgn}(x)
$$

weakly.

Now compute the derivative of $\operatorname{sgn}(x)$. Since

$$
\operatorname{sgn}(x)=2\Theta(x)-1,
$$

and $\Theta'(x)=\delta(x)$, we get

$$
\frac{d}{dx}\operatorname{sgn}(x)=2\delta(x).
$$

</details>

### Exercise 2: Delta functions and negative Sobolev order

Using the Fourier definition of $H^s(\mathbb R^d)$, show that

$$
\delta\in H^{-s}(\mathbb R^d)
$$

when $s>d/2$.

<details><summary><strong>Solution</strong></summary>

The Fourier transform of the delta distribution is

$$
\widehat\delta(k)=1.
$$

Therefore

$$
\|\delta\|_{H^{-s}}^2
=\int\frac{d^dk}{(2\pi)^d}\,(1+|k|^2)^{-s}.
$$

At small $|k|$, the integrand is finite. At large $|k|$, the radial integral behaves like

$$
\int^\infty dk\,k^{d-1}k^{-2s}
=\int^\infty dk\,k^{d-1-2s}.
$$

This converges if

$$
d-1-2s<-1,
$$

or equivalently

$$
s>\frac d2.
$$

Thus $\delta\in H^{-s}$ for every $s>d/2$.

</details>

### Exercise 3: Regularity gain from a massive propagator

Let $L=-\Delta+m^2$ with $m>0$. Show from Fourier space that

$$
L^{-1}:H^s(\mathbb R^d)\to H^{s+2}(\mathbb R^d)
$$

is bounded.

<details><summary><strong>Solution</strong></summary>

If $u=L^{-1}f$, then

$$
\widehat u(k)=\frac{\widehat f(k)}{|k|^2+m^2}.
$$

The $H^{s+2}$ norm of $u$ is

$$
\|u\|_{H^{s+2}}^2
=\int_k (1+|k|^2)^{s+2}\frac{|\widehat f(k)|^2}{(|k|^2+m^2)^2}.
$$

Since $m>0$, the ratio

$$
\frac{(1+|k|^2)^2}{(|k|^2+m^2)^2}
$$

is bounded uniformly in $k$. Hence

$$
\|u\|_{H^{s+2}}^2
\leq C\int_k(1+|k|^2)^s|\widehat f(k)|^2
=C\|f\|_{H^s}^2.
$$

So $L^{-1}$ maps $H^s$ boundedly into $H^{s+2}$.

</details>

### Exercise 4: Roughness of a free scalar field

A massive Euclidean free scalar in $d$ dimensions has covariance

$$
\langle \widehat\phi(k)\widehat\phi(k')\rangle
=(2\pi)^d\delta^{(d)}(k+k')\frac1{k^2+m^2}.
$$

Use the mode-sum estimate

$$
\mathbb E\|\phi\|_{H^s}^2
\sim\int_k\frac{(1+|k|^2)^s}{k^2+m^2}
$$

to find the ultraviolet convergence condition.

<details><summary><strong>Solution</strong></summary>

At large $|k|$,

$$
\frac{(1+|k|^2)^s}{k^2+m^2}
\sim |k|^{2s-2}.
$$

The $d$-dimensional radial measure contributes $k^{d-1}dk$, so the ultraviolet integral behaves like

$$
\int^\infty dk\,k^{d-1+2s-2}
=\int^\infty dk\,k^{d+2s-3}.
$$

This converges if

$$
d+2s-3<-1,
$$

or

$$
s<1-\frac d2.
$$

Thus the Gaussian free field is much rougher than a classical finite-action $H^1$ field. For instance, in $d=4$ this estimate requires $s<-1$.

</details>

### Exercise 5: Why boundary values require regularity

Explain why an arbitrary $L^2(\Omega)$ function does not have a canonical boundary value on $\partial\Omega$, while an $H^1(\Omega)$ function has a boundary trace in $H^{1/2}(\partial\Omega)$ under standard smoothness assumptions on $\Omega$.

<details><summary><strong>Solution</strong></summary>

An $L^2$ function is defined only up to changes on sets of measure zero. Since $\partial\Omega$ has measure zero inside $\Omega$, changing the representative of an $L^2$ equivalence class on the boundary does not change the $L^2$ element. Therefore there is no canonical boundary value.

Sobolev regularity supplies enough control near the boundary to define a continuous trace map. The trace theorem gives, for smooth enough domains,

$$
\operatorname{Tr}:H^s(\Omega)\to H^{s-1/2}(\partial\Omega)
$$

when $s>1/2$. In particular,

$$
\operatorname{Tr}:H^1(\Omega)\to H^{1/2}(\partial\Omega).
$$

Thus $H^1$ functions have well-defined boundary traces, even though they need not be classically continuous everywhere.

</details>

## References

- R. A. Adams and J. J. F. Fournier, *Sobolev Spaces*, 2nd ed.
- L. C. Evans, *Partial Differential Equations*, especially the chapters on weak derivatives and Sobolev spaces.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, Vol. II, for functional analysis and elliptic-operator background.
- M. E. Taylor, *Partial Differential Equations I: Basic Theory*, for Sobolev spaces, distributions, and elliptic regularity.
- B. Simon, *The $P(\phi)_2$ Euclidean Quantum Field Theory*, for the relationship between Gaussian measures, Sobolev regularity, and constructive QFT.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for functional-integral regularity and constructive-field-theory context.

## Version history

- 2026-06-24: First polished draft. Added weak derivatives, Fourier definition of $H^s$, embeddings, Green functions, boundary traces, Gaussian free-field roughness, and QFT-oriented exercises.
