---
title: "Principal Values"
description: "A QFT-oriented derivation of Cauchy principal-value distributions, boundary-value identities, Hilbert transforms, and pole prescriptions such as 1/(x ± i0)."
sidebar:
  label: "Principal Values"
  order: 6
level: Graduate
status: "Polished draft"
source: "Standard distribution theory and complex analysis, with QFT applications to pole prescriptions, spectral densities, Green functions, response functions, and dispersion relations."
topics:
  - principal values
  - distributions
  - pole prescriptions
  - Hilbert transforms
  - propagators
canonicalTopics:
  - principal-value-distributions
  - boundary-value-distributions
  - qft-pole-prescriptions
researchStatus:
  established:
    - "Cauchy principal values and boundary values of meromorphic functions are standard distributional tools in Fourier analysis, complex analysis, and perturbative QFT."
  active:
    - "In advanced QFT, products and restrictions of singular boundary-value distributions are controlled using microlocal analysis, renormalization, or carefully specified regulator schemes."
---

## Summary

A principal value is not a license to ignore a pole. It is a precise distribution obtained by testing a singular kernel against a smooth function and removing the singular point in a symmetric way.

The prototype is

$$
\left\langle \operatorname{PV}\frac1x,\varphi\right\rangle
=\lim_{\epsilon\to0^+}\int_{|x|>\epsilon}dx\,\frac{\varphi(x)}{x}.
$$

The limit exists even though $1/x$ is not locally integrable in the ordinary absolute sense near $x=0$. The cancellation is not magic; it is the cancellation of the odd singular part after the test function is expanded near the origin.

Principal values matter in QFT because real-time denominators almost never mean ordinary functions. The basic identity

$$
\frac{1}{x\pm i0}=\operatorname{PV}\frac1x\mp i\pi\delta(x)
$$

is the local model for Feynman, retarded, and advanced prescriptions. The principal-value part carries the dispersive, off-shell, real part; the delta-function part carries the on-shell discontinuity.

<figure class="doc-figure" style="--figure-width: 41rem;">

![Principal-value boundary values and delta-function jump](/figures/math-toolkit/principal-value-boundary.svg)

<figcaption>

The principal value removes a symmetric interval around the singular point before taking the limit. Boundary values from $x\to x\pm i0$ add the delta-function term that records which side of the pole was chosen.

</figcaption>
</figure>

:::note[The slogan]
A principal value is the distributional shadow of a singular integral whose odd part cancels. An $i0$ prescription is a boundary value from complex analysis, not just a small imaginary number.
:::

## Prerequisites

You should know the [Mathematical Conventions](/math-toolkit/conventions/), especially the distribution and Fourier conventions. The pages on [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/), [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/), [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/), and [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/) provide the immediate background.

You do not need a full course in complex analysis, but you should be comfortable with residues and contour deformation. The most important habit is to keep the pole prescription until the end of a calculation.

## Core idea

The bad expression $1/x$ fails as an ordinary locally integrable function near $x=0$ because

$$
\int_{-a}^{a}\frac{dx}{|x|}=\infty.
$$

But the singularity is odd. If a smooth test function is nearly constant near zero, then the constant part cancels in a symmetric exclusion:

$$
\int_{-a}^{-\epsilon}\frac{\varphi(0)}{x}\,dx
+\int_{\epsilon}^{a}\frac{\varphi(0)}{x}\,dx=0.
$$

The remaining part is

$$
\frac{\varphi(x)-\varphi(0)}{x},
$$

which is regular near $x=0$ because $\varphi(x)-\varphi(0)=x\varphi'(0)+O(x^2)$. This is why the principal value exists as a distribution.

The guiding replacement is therefore

$$
\text{singular odd kernel}
\quad\leadsto\quad
\text{linear functional on test functions}.
$$

The phrase “principal value” is sometimes used informally in physics to mean “take the real part” or “average above and below the pole.” Those statements are often morally right, but the distributional definition is the safe one.

## Setup and conventions

Throughout this page, $\varphi$ is a smooth test function on $\mathbb R$. For local definitions, $\varphi\in C_c^\infty(\mathbb R)$ is enough. For Fourier transforms, $\varphi$ may be taken in the Schwartz space $\mathcal S(\mathbb R)$.

The distribution pairing is written

$$
\langle T,\varphi\rangle.
$$

The one-dimensional delta distribution is normalized by

$$
\langle \delta,
\varphi\rangle=\varphi(0).
$$

For Euclidean or spatial Fourier transforms, we use

$$
\widehat f(k)=\int_{-\infty}^{\infty}dx\,e^{-ikx}f(x),
\qquad
f(x)=\int\frac{dk}{2\pi}\,e^{ikx}\widehat f(k).
$$

For Lorentzian spacetime Fourier transforms, the site convention is

$$
f(x)=\int_p e^{-ip\cdot x}\widetilde f(p),
\qquad
\widetilde f(p)=\int d^4x\,e^{ip\cdot x}f(x).
$$

The symbol $0$ in $x\pm i0$ means the distributional limit $\epsilon\to0^+$ of $x\pm i\epsilon$. It is not a number to be set to zero prematurely.

## The one-dimensional principal value

The Cauchy principal-value distribution $\operatorname{PV}(1/x)$ is defined by

$$
\left\langle \operatorname{PV}\frac1x,\varphi\right\rangle
=\lim_{\epsilon\to0^+}\int_{|x|>\epsilon}dx\,\frac{\varphi(x)}{x}
$$

whenever the integral is over the real line and $\varphi$ has compact support or rapid decay.

To see that the limit exists, choose $a>0$ small enough that the singular part is isolated. Split

$$
\int_{\epsilon<|x|<a}\frac{\varphi(x)}{x}\,dx
=\int_{\epsilon<|x|<a}\frac{\varphi(0)}{x}\,dx
+\int_{\epsilon<|x|<a}\frac{\varphi(x)-\varphi(0)}{x}\,dx.
$$

The first term vanishes by oddness. The second has a finite limit because the numerator vanishes linearly at zero. The part $|x|>a$ is an ordinary integral.

Thus the principal value remembers the pole, but it records it by a distributional rule rather than by assigning a finite pointwise value to $1/0$.

### Basic properties

The principal value is odd:

$$
\left\langle \operatorname{PV}\frac1x,\varphi(-x)\right\rangle
=-\left\langle \operatorname{PV}\frac1x,\varphi(x)\right\rangle.
$$

It satisfies

$$
x\operatorname{PV}\frac1x=1
$$

as distributions. Indeed,

$$
\left\langle x\operatorname{PV}\frac1x,\varphi\right\rangle
=\left\langle \operatorname{PV}\frac1x,x\varphi\right\rangle
=\lim_{\epsilon\to0^+}\int_{|x|>\epsilon}dx\,\varphi(x)
=\int dx\,\varphi(x).
$$

This equation is often more useful than the definition. It tells you that $\operatorname{PV}(1/x)$ is one particular distributional inverse of multiplication by $x$.

It is not the only inverse in a naive algebraic sense: because $x\delta(x)=0$, the distributions

$$
\operatorname{PV}\frac1x+c\delta(x)
$$

also satisfy $xT=1$ for any constant $c$. Boundary values $1/(x\pm i0)$ choose the special constants $c=\mp i\pi$.

### Differentiating principal values

The derivative of a distribution is defined by integration by parts. Therefore

$$
\left\langle \frac{d}{dx}\operatorname{PV}\frac1x,\varphi\right\rangle
=-\left\langle \operatorname{PV}\frac1x,\varphi'\right\rangle.
$$

This derivative is more singular than $1/x$. It is usually written as a finite-part distribution:

$$
\frac{d}{dx}\operatorname{PV}\frac1x
=-\operatorname{Fp}\frac1{x^2},
$$

where

$$
\left\langle \operatorname{Fp}\frac1{x^2},\varphi\right\rangle
=\lim_{\epsilon\to0^+}
\left[
\int_{|x|>\epsilon}dx\,\frac{\varphi(x)}{x^2}
-\frac{2\varphi(0)}{\epsilon}
\right].
$$

The subtraction is not arbitrary. It removes the divergent part that is forced by the Taylor expansion of $\varphi$ at the singular point.

More generally, higher powers $1/x^n$ require finite-part prescriptions. In QFT, these higher finite parts appear when differentiating singular kernels, expanding short-distance singularities, or defining composite operators.

## Boundary values and the Sokhotski–Plemelj identity

The distributions $1/(x+i0)$ and $1/(x-i0)$ are defined by limits

$$
\left\langle \frac{1}{x\pm i0},\varphi\right\rangle
=\lim_{\epsilon\to0^+}\int_{-\infty}^{\infty}dx\,\frac{\varphi(x)}{x\pm i\epsilon}.
$$

The central identity is

$$
\boxed{
\frac{1}{x\pm i0}=\operatorname{PV}\frac1x\mp i\pi\delta(x)
}
$$

as distributions. This is the Sokhotski–Plemelj formula in its simplest form.

A quick derivation goes as follows. Write

$$
\frac{1}{x\pm i\epsilon}
=\frac{x}{x^2+\epsilon^2}\mp i\frac{\epsilon}{x^2+\epsilon^2}.
$$

The real part converges to $\operatorname{PV}(1/x)$ when tested against a smooth function. The imaginary part uses the standard delta sequence

$$
\frac{1}{\pi}\frac{\epsilon}{x^2+\epsilon^2}\longrightarrow \delta(x),
$$

so

$$
\mp i\frac{\epsilon}{x^2+\epsilon^2}\longrightarrow \mp i\pi\delta(x).
$$

That is the whole $i0$ prescription in one line: the infinitesimal imaginary part tells you which delta-function contribution sits on the pole.

### Average and discontinuity

The principal value is the average of the two boundary values:

$$
\operatorname{PV}\frac1x
=\frac12\left(\frac{1}{x+i0}+\frac{1}{x-i0}\right).
$$

The delta function is their discontinuity:

$$
\frac{1}{x+i0}-\frac{1}{x-i0}=-2\pi i\delta(x).
$$

Equivalently,

$$
\operatorname{Im}\frac{1}{x+i0}=-\pi\delta(x),
\qquad
\operatorname{Re}\frac{1}{x+i0}=\operatorname{PV}\frac1x.
$$

This average/discontinuity split is the seed of spectral representations, optical theorems, dispersion relations, and cutting rules.

## Fourier transforms

With the Euclidean/spatial convention

$$
\widehat f(k)=\int dx\,e^{-ikx}f(x),
$$

the principal-value kernel has Fourier transform

$$
\mathcal F\left[\operatorname{PV}\frac1x\right](k)
=-i\pi\operatorname{sgn}(k)
$$

as a tempered distribution.

One way to derive this is to use the boundary-value identities and contour integration. Since

$$
\frac{1}{x+i0}=\operatorname{PV}\frac1x-i\pi\delta(x),
$$

we get

$$
\mathcal F\left[\frac{1}{x+i0}\right](k)
=-i\pi\operatorname{sgn}(k)-i\pi
=-2\pi i\theta(k),
$$

where the value of $\theta(0)$ is irrelevant distributionally. Similarly,

$$
\mathcal F\left[\frac{1}{x-i0}\right](k)
=2\pi i\theta(-k).
$$

These formulas encode contour closing. The pole below the real axis contributes for one sign of $k$; the pole above contributes for the other.

### Hilbert transform

The Hilbert transform is convolution with the principal-value kernel

$$
Hf(x)=\frac1\pi\operatorname{PV}\int_{-\infty}^{\infty}dy\,\frac{f(y)}{x-y}.
$$

Equivalently,

$$
Hf=\left(\operatorname{PV}\frac{1}{\pi x}\right)*f.
$$

Its Fourier multiplier is

$$
\widehat{Hf}(k)=-i\operatorname{sgn}(k)\widehat f(k).
$$

This is the analytic heart of many Kramers–Kronig and dispersion-relation formulas: boundary values of analytic functions relate real and imaginary parts by Hilbert transforms.

## Singular hypersurfaces

The one-dimensional identity generalizes locally. Suppose $g$ is a real smooth function and $dg\neq0$ on the hypersurface $g=0$. Then

$$
\frac{1}{g\pm i0}=\operatorname{PV}\frac1g\mp i\pi\delta(g)
$$

as distributions, with

$$
\int d^dx\,F(x)\delta(g(x))
=\int_{g=0}\frac{d\Sigma}{|\nabla g|}\,F(x)
$$

in Euclidean coordinates.

This formula is local because one may use $g$ itself as one coordinate near a regular point of the hypersurface. The one-dimensional pole then sits in the normal direction to $g=0$.

The regularity assumption matters. If $dg=0$ somewhere on $g=0$, the singularity is worse and the naive formula can fail or require refinement. QFT denominators can have precisely such subtle points at thresholds, pinches, and Landau singularities.

## Propagator prescriptions

The scalar Feynman denominator is the distribution

$$
\frac{1}{p^2-m^2+i0}.
$$

By the boundary-value identity,

$$
\frac{1}{p^2-m^2+i0}
=\operatorname{PV}\frac{1}{p^2-m^2}-i\pi\delta(p^2-m^2)
$$

as a distribution in momentum space.

Multiplying by the conventional factor of $i$, the scalar Feynman propagator in momentum space is

$$
\frac{i}{p^2-m^2+i0}
=i\operatorname{PV}\frac{1}{p^2-m^2}+\pi\delta(p^2-m^2).
$$

The principal-value part is off-shell and dispersive. The delta part is on-shell. This split is useful, but it should not be confused with the full causal prescription. The full object is the boundary value, and the boundary value knows how the poles are passed when $p^0$ is integrated.

### Feynman versus retarded and advanced

For fixed spatial momentum, write

$$
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The Feynman prescription places the positive-energy pole below and the negative-energy pole above the $p^0$ contour:

$$
\frac{1}{(p^0)^2-E_{\mathbf p}^2+i0}.
$$

The retarded prescription places both poles below the contour:

$$
\frac{1}{(p^0+i0)^2-E_{\mathbf p}^2}
=\operatorname{PV}\frac{1}{(p^0)^2-E_{\mathbf p}^2}
-i\pi\operatorname{sgn}(p^0)\delta((p^0)^2-E_{\mathbf p}^2).
$$

The advanced prescription places both poles above:

$$
\frac{1}{(p^0-i0)^2-E_{\mathbf p}^2}
=\operatorname{PV}\frac{1}{(p^0)^2-E_{\mathbf p}^2}
+i\pi\operatorname{sgn}(p^0)\delta((p^0)^2-E_{\mathbf p}^2).
$$

These formulas show why the symbol $i0$ is not decorative. The sign and the location of the infinitesimal imaginary part determine causality.

## Dispersion relations

Suppose $F(z)$ is analytic away from the real axis and has boundary values

$$
F_+(x)=\lim_{\epsilon\to0^+}F(x+i\epsilon),
\qquad
F_-(x)=\lim_{\epsilon\to0^+}F(x-i\epsilon).
$$

The discontinuity across the real axis is

$$
\operatorname{Disc}F(x)=F_+(x)-F_-(x).
$$

When $F$ decreases sufficiently at infinity, Cauchy's theorem gives a representation of $F(z)$ in terms of its discontinuity:

$$
F(z)=\frac{1}{2\pi i}\int_{-\infty}^{\infty}dx\,\frac{\operatorname{Disc}F(x)}{x-z}.
$$

Taking $z$ to the real axis gives principal-value integrals. Schematically,

$$
\operatorname{Re}F_+(s)
=\frac{1}{\pi}\operatorname{PV}\int dx\,\frac{\operatorname{Im}F_+(x)}{x-s}
$$

up to subtraction terms. In QFT those subtraction terms are not bookkeeping fluff: they are local polynomial ambiguities, counterterms, or input constants fixed by renormalization conditions.

This is why principal values show up in response theory and scattering. Analyticity turns imaginary parts and discontinuities into real parts through principal-value kernels.

## Principal values in loop calculations

A loop integral with a Feynman denominator is not usually defined as a principal-value integral. It is defined by the full $i0$ prescription:

$$
\int_p \frac{N(p)}{p^2-m^2+i0}.
$$

Only after using the distributional identity may one split it into a principal-value part and an on-shell delta part. This split can be useful for unitarity, spectral representations, finite-temperature formulas, and real-time response, but it must be done with care.

Three warnings are worth keeping close.

First, a principal value in one variable may not define a principal value in another variable after a singular change of coordinates. The prescription belongs to the distribution, not to a visual picture of a pole.

Second, products such as

$$
\left(\operatorname{PV}\frac1x\right)^2
$$

are not automatically defined. They require a regulator, a finite-part prescription, or a renormalization rule.

Third, the imaginary part of a Feynman integral is often simpler than the real part because the imaginary part is supported on on-shell delta functions. The real part is commonly reconstructed from dispersion relations and principal values, but only after the necessary subtractions are specified.

## A practical checklist

When you see a principal value or $i0$ prescription, ask these questions.

| Question | Why it matters |
|---|---|
| What is the test space? | Compactly supported and Schwartz test functions lead to different global assumptions. |
| Which variable carries the pole? | $1/(x+i0)$ and $1/(f(x)+i0)$ require different local interpretations. |
| Is the zero set regular? | If $df=0$ on $f=0$, thresholds and pinch singularities may appear. |
| Is the expression a boundary value or an average? | $1/(x+i0)$ contains both principal-value and delta pieces. |
| Are distributions being multiplied? | Products of singular distributions require extra data. |
| Are subtraction terms needed? | Dispersion relations and finite parts often have local polynomial ambiguities. |
| Has the Fourier convention changed? | Signs in $\mathcal F[\operatorname{PV}(1/x)]$ depend on the phase convention. |

This checklist sounds fussy because it is. It is also the difference between a correct causal Green function and a ghost sign error that haunts a calculation for six pages.

## Common pitfalls

**Treating principal value as “just ignore the pole.”** The definition is not deletion; it is a symmetric limiting operation after pairing with a test function. Deleting a point from an ordinary integral does nothing. Principal values work because the singularity is handled distributionally.

**Forgetting the delta term in an $i0$ denominator.** The identity $1/(x+i0)=\operatorname{PV}(1/x)-i\pi\delta(x)$ is not optional. Dropping the delta term changes spectral densities, unitarity, and causal response.

**Confusing Feynman, retarded, and advanced prescriptions.** They can share the same algebraic denominator while having different pole locations. The prescription, not the polynomial alone, defines the distribution.

**Changing variables casually.** Principal values depend on how the singular surface is approached. Smooth changes of variables with nonzero Jacobian are fine; singular changes or threshold coordinates require fresh analysis.

**Multiplying singular distributions without a regulator.** The expression $\delta(x)\operatorname{PV}(1/x)$ is not canonically defined. A particular regularization may assign a value, but that value is part of the prescription.

**Thinking the real part is always physical and the imaginary part is artificial.** In QFT the imaginary part often carries the on-shell spectral content. The principal-value part and delta part are both physical when the full object is physical.

## Relations to other pages

The [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) page explains the general pairing language used here. [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/) derives the normalization and change-of-variables rules for $\delta(g)$. [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/) explains why principal values are tempered distributions. [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/) fixes the signs in the Fourier formulas. [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/) explains the Hilbert transform as a singular convolution kernel.

The next page, [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/), uses principal values and boundary values to organize propagators, commutators, spectral densities, contact terms, and time-ordered products.

## Research status

The one-dimensional principal value, the Sokhotski–Plemelj identity, Hilbert transforms, and standard pole prescriptions are established mathematical tools. In perturbative QFT they are part of the everyday distributional meaning of propagators and response functions.

The subtle frontier is not the basic identity. It is the controlled manipulation of several singular distributions at once: products at coincident points, overlapping singular supports, boundary values of multivariable integrals, Landau singularities, and renormalized extensions to diagonals. Those issues are handled in advanced perturbative QFT, microlocal analysis, algebraic QFT, and modern amplitude theory.

## Exercises

### Exercise 1: Existence of the principal value

Let $\varphi\in C_c^\infty(\mathbb R)$. Prove that

$$
\lim_{\epsilon\to0^+}\int_{|x|>\epsilon}dx\,\frac{\varphi(x)}{x}
$$

exists.

<details><summary><strong>Solution</strong></summary>

Choose $a>0$ and split the integral into $|x|<a$ and $|x|>a$. The second part is ordinary because $1/x$ is smooth away from zero.

For the near-zero part,

$$
\int_{\epsilon<|x|<a}\frac{\varphi(x)}{x}\,dx
=\int_{\epsilon<|x|<a}\frac{\varphi(0)}{x}\,dx
+\int_{\epsilon<|x|<a}\frac{\varphi(x)-\varphi(0)}{x}\,dx.
$$

The first term vanishes because the interval is symmetric and $1/x$ is odd. The second has a finite limit because

$$
\frac{\varphi(x)-\varphi(0)}{x}
$$

extends smoothly to $x=0$ with value $\varphi'(0)$. Hence the principal-value limit exists.

</details>

### Exercise 2: Multiplication by the coordinate

Show that

$$
x\operatorname{PV}\frac1x=1
$$

as distributions.

<details><summary><strong>Solution</strong></summary>

Test both sides on $\varphi$:

$$
\left\langle x\operatorname{PV}\frac1x,\varphi\right\rangle
=\left\langle \operatorname{PV}\frac1x,x\varphi\right\rangle.
$$

By definition,

$$
\left\langle \operatorname{PV}\frac1x,x\varphi\right\rangle
=\lim_{\epsilon\to0^+}\int_{|x|>\epsilon}dx\,\frac{x\varphi(x)}{x}
=\int dx\,\varphi(x).
$$

This is exactly $\langle 1,\varphi\rangle$.

</details>

### Exercise 3: Boundary-value identity

Using

$$
\frac{1}{x+i\epsilon}=\frac{x}{x^2+\epsilon^2}-i\frac{\epsilon}{x^2+\epsilon^2},
$$

prove

$$
\frac{1}{x+i0}=\operatorname{PV}\frac1x-i\pi\delta(x).
$$

<details><summary><strong>Solution</strong></summary>

Pair with a test function $\varphi$. The real part gives

$$
\lim_{\epsilon\to0^+}\int dx\,\frac{x\varphi(x)}{x^2+\epsilon^2}
=\left\langle \operatorname{PV}\frac1x,\varphi\right\rangle.
$$

The imaginary part uses the normalized delta sequence

$$
\frac{1}{\pi}\frac{\epsilon}{x^2+\epsilon^2}\to\delta(x).
$$

Therefore

$$
-i\lim_{\epsilon\to0^+}\int dx\,\frac{\epsilon\varphi(x)}{x^2+\epsilon^2}
=-i\pi\varphi(0).
$$

Combining the two parts gives the identity.

</details>

### Exercise 4: Fourier transform of the principal value

Using the site Euclidean Fourier convention, show that

$$
\mathcal F\left[\operatorname{PV}\frac1x\right](k)
=-i\pi\operatorname{sgn}(k).
$$

<details><summary><strong>Solution</strong></summary>

From the boundary-value identity,

$$
\frac{1}{x+i0}=\operatorname{PV}\frac1x-i\pi\delta(x).
$$

For $k>0$, close the contour for

$$
\int dx\,\frac{e^{-ikx}}{x+i0}
$$

in the lower half-plane. The contour is clockwise and encloses the pole at $x=-i0$, giving $-2\pi i$. For $k<0$, close in the upper half-plane and enclose no pole, giving $0$. Thus

$$
\mathcal F\left[\frac{1}{x+i0}\right](k)=-2\pi i\theta(k).
$$

Since $\mathcal F[\delta]=1$,

$$
\mathcal F\left[\operatorname{PV}\frac1x\right](k)-i\pi=-2\pi i\theta(k).
$$

Therefore

$$
\mathcal F\left[\operatorname{PV}\frac1x\right](k)
=i\pi-2\pi i\theta(k)
=-i\pi\operatorname{sgn}(k).
$$

The value at $k=0$ is irrelevant as a distribution.

</details>

### Exercise 5: Feynman denominator split

Show that

$$
\frac{i}{p^2-m^2+i0}
=i\operatorname{PV}\frac{1}{p^2-m^2}+\pi\delta(p^2-m^2).
$$

What part is supported on shell?

<details><summary><strong>Solution</strong></summary>

Apply the one-dimensional identity to the real variable

$$
x=p^2-m^2.
$$

Then

$$
\frac{1}{p^2-m^2+i0}
=\operatorname{PV}\frac{1}{p^2-m^2}-i\pi\delta(p^2-m^2).
$$

Multiplying by $i$ gives

$$
\frac{i}{p^2-m^2+i0}
=i\operatorname{PV}\frac{1}{p^2-m^2}+\pi\delta(p^2-m^2).
$$

The delta-function term is supported on shell, namely on the mass hyperboloid $p^2=m^2$. The principal-value part is not concentrated on shell.

</details>

### Exercise 6: Why the square is not automatic

Explain why the expression

$$
\left(\operatorname{PV}\frac1x\right)^2
$$

is not automatically a well-defined distribution.

<details><summary><strong>Solution</strong></summary>

A distribution is a linear functional on test functions. Multiplication by a smooth function is defined by moving the smooth factor onto the test function:

$$
\langle fT,\varphi\rangle=\langle T,f\varphi\rangle.
$$

But $\operatorname{PV}(1/x)$ is not a smooth function, so this rule does not define

$$
\left(\operatorname{PV}\frac1x\right)\varphi
$$

as a test function. In fact, different regularizations of $1/x$ can produce different finite local terms when squared. A prescription or renormalization rule is needed.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, for $i\epsilon$ prescriptions, propagators, and distributional identities in perturbative QFT.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for propagator prescriptions, unitarity, and analytic structure in practical QFT calculations.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for scattering theory, propagators, analyticity, and spectral representations.

### Mathematical references

- L. Schwartz, *Théorie des distributions*, for the original distribution-theoretic framework.
- I. M. Gel'fand and G. E. Shilov, *Generalized Functions*, Vol. I, for generalized functions, principal values, and boundary values.
- F. G. Friedlander and M. Joshi, *Introduction to the Theory of Distributions*, for a readable mathematical introduction.
- L. Hörmander, *The Analysis of Linear Partial Differential Operators*, Vol. I, for distributions, boundary values, and microlocal refinements.

## Version history

- **2026-06-24:** Initial polished draft. Defined principal-value distributions, derived $1/(x\pm i0)$, fixed Fourier signs in the site convention, and connected the formalism to QFT pole prescriptions and spectral discontinuities.
