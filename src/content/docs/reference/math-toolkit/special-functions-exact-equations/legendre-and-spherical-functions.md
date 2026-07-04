---
title: "Legendre and Spherical Functions"
description: "Explains Legendre polynomials, associated Legendre functions, spherical harmonics, spherical Bessel functions, partial waves, addition theorems, and higher-dimensional spherical functions for QFT." 
sidebar:
  label: "Legendre and Spherical Functions"
  order: 3
level: Graduate
status: "Polished draft"
source: "Standard references on Legendre functions, spherical harmonics, angular momentum, partial waves, Sturm–Liouville theory, special functions, and QFT applications, including Whittaker–Watson, Hobson, Watson, Abramowitz–Stegun, NIST DLMF, Olver, Vilenkin–Klimyk, Edmonds, Varshalovich et al., Morse–Feshbach, Messiah, Sakurai, Weinberg, Srednicki, Schwartz, Zee, Di Francesco–Mathieu–Sénéchal, and mathematical physics references on harmonic analysis on spheres."
topics:
  - Legendre polynomials
  - associated Legendre functions
  - spherical harmonics
  - spherical Bessel functions
  - partial waves
  - angular momentum
  - addition theorem
  - Gegenbauer polynomials
  - hyperspherical harmonics
  - central potentials
canonicalTopics:
  - legendre-polynomial
  - associated-legendre-function
  - spherical-harmonic
  - spherical-bessel-function
  - partial-wave
  - angular-momentum
  - addition-theorem
  - gegenbauer-polynomial
  - hyperspherical-harmonic
  - central-potential
researchStatus:
  established:
    - "Legendre polynomials, associated Legendre functions, spherical harmonics, and hyperspherical harmonics are standard eigenfunctions of angular Laplacians and are foundational in partial-wave analysis, angular momentum, and rotationally invariant QFT problems."
    - "Orthogonality, completeness, addition theorems, recurrence relations, and normalization conventions are classical and widely used."
  active:
    - "Modern applications include conformal partial waves, harmonic analysis on homogeneous spaces, celestial amplitudes, compactification spectra, finite-volume spectra, and numerical bootstrap decompositions with spin."
---

## Summary

Legendre and spherical functions are the angular side of separation of variables. Bessel functions solve the radial equation; Legendre polynomials and spherical harmonics solve the angular equation.

The Legendre equation is

$$
(1-x^2)y''-2xy'+\ell(\ell+1)y=0.
$$

Its regular polynomial solution is $P_\ell(x)$, with $\ell=0,1,2,\dots$. The associated Legendre equation is

$$
(1-x^2)y''-2xy'
+\left[\ell(\ell+1)-\frac{m^2}{1-x^2}\right]y=0.
$$

Its regular solutions build the spherical harmonics

$$
Y_{\ell m}(\theta,\phi)
=
\sqrt{\frac{2\ell+1}{4\pi}\frac{(\ell-m)!}{(\ell+m)!}}
P_\ell^m(\cos\theta)e^{im\phi}.
$$

This page uses the Condon–Shortley phase $(-1)^m$ in the definition of $P_\ell^m$, so it is already included in $Y_{\ell m}$. Many physics texts use the same convention, but not all references do. Tiny phase convention, enormous annoyance potential.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing angular separation on the sphere leading to Legendre functions, spherical harmonics, addition theorem, and partial waves.](/figures/math-toolkit/spherical-harmonic-partial-wave-flow.svg)

<figcaption>

Rotational symmetry separates a field into angular and radial factors. The angular Laplacian gives $Y_{\ell m}$ and $P_\ell(\cos\theta)$; the radial equation gives spherical Bessel functions. The addition theorem and partial-wave expansion turn rotational invariance into diagonal sums over angular momentum.

</figcaption>
</figure>

## Prerequisites

You should know [Sturm–Liouville Theory](/math-toolkit/differential-equations-green-functions/sturm-liouville-theory/), [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/), [Schrödinger Operators](/math-toolkit/differential-equations-green-functions/schrodinger-operators/), [Bessel Functions](/math-toolkit/special-functions-exact-equations/bessel-functions/), [SU(2) and Angular Momentum](/math-toolkit/groups-representations/su2-and-angular-momentum/), [Compact Lie Groups](/math-toolkit/groups-representations/compact-lie-groups/), and [Characters](/math-toolkit/groups-representations/characters/).

The default sphere measure is

$$
d\Omega=\sin\theta\,d\theta\,d\phi
$$

on $S^2$, and spherical harmonics are normalized to

$$
\int_{S^2}d\Omega\,Y_{\ell m}^*(\Omega)Y_{\ell' m'}(\Omega)
=\delta_{\ell\ell'}\delta_{mm'}.
$$

## Angular separation on the sphere

The Laplacian in three Euclidean dimensions is

$$
\nabla^2
=\frac1{r^2}\frac{\partial}{\partial r}\left(r^2\frac{\partial}{\partial r}\right)
+\frac1{r^2}\Delta_{S^2},
$$

where

$$
\Delta_{S^2}
=\frac1{\sin\theta}\frac{\partial}{\partial\theta}
\left(\sin\theta\frac{\partial}{\partial\theta}\right)
+\frac1{\sin^2\theta}\frac{\partial^2}{\partial\phi^2}.
$$

The spherical harmonics are eigenfunctions of $\Delta_{S^2}$:

$$
\Delta_{S^2}Y_{\ell m}(\theta,\phi)
=-\ell(\ell+1)Y_{\ell m}(\theta,\phi),
$$

with

$$
\ell=0,1,2,\dots,
\qquad
m=-\ell,-\ell+1,\dots,\ell.
$$

Set

$$
Y(\theta,\phi)=\Theta(\theta)e^{im\phi}.
$$

Then $x=\cos\theta$ converts the angular equation into the associated Legendre equation,

$$
(1-x^2)\Theta''-2x\Theta'
+\left[\ell(\ell+1)-\frac{m^2}{1-x^2}\right]\Theta=0.
$$

Regularity at the poles $x=\pm1$ forces $\ell$ and $m$ to be integers with $|m|\le\ell$. The quantization of angular momentum is already in the boundary condition on the sphere.

## Legendre polynomials

The Legendre polynomial $P_\ell(x)$ is the regular solution of

$$
(1-x^2)y''-2xy'+\ell(\ell+1)y=0
$$

normalized by

$$
P_\ell(1)=1.
$$

The first few are

$$
P_0(x)=1,
$$

$$
P_1(x)=x,
$$

$$
P_2(x)=\frac12(3x^2-1),
$$

and

$$
P_3(x)=\frac12(5x^3-3x).
$$

Rodrigues' formula is

$$
P_\ell(x)=\frac1{2^\ell\ell!}\frac{d^\ell}{dx^\ell}(x^2-1)^\ell.
$$

The generating function is

$$
\frac1{\sqrt{1-2xt+t^2}}
=\sum_{\ell=0}^{\infty}P_\ell(x)t^\ell,
\qquad |t|<1.
$$

The orthogonality relation is

$$
\int_{-1}^{1}dx\,P_\ell(x)P_{\ell'}(x)
=\frac{2}{2\ell+1}\delta_{\ell\ell'}.
$$

This is a Sturm–Liouville orthogonality relation with unit weight on $[-1,1]$.

## Associated Legendre functions

With the Condon–Shortley convention,

$$
P_\ell^m(x)
=(-1)^m(1-x^2)^{m/2}\frac{d^m}{dx^m}P_\ell(x),
\qquad m\ge0.
$$

Negative $m$ is defined by

$$
P_\ell^{-m}(x)
=(-1)^m\frac{(\ell-m)!}{(\ell+m)!}P_\ell^m(x).
$$

The spherical harmonics are then

$$
Y_{\ell m}(\theta,\phi)
=(-1)^m
\sqrt{\frac{2\ell+1}{4\pi}\frac{(\ell-m)!}{(\ell+m)!}}
P_\ell^m(\cos\theta)e^{im\phi},
$$

if $P_\ell^m$ is defined without the Condon–Shortley phase. Since this page includes the phase in $P_\ell^m$ itself, the equivalent compact convention is

$$
Y_{\ell m}(\theta,\phi)
=
\sqrt{\frac{2\ell+1}{4\pi}\frac{(\ell-m)!}{(\ell+m)!}}
P_\ell^m(\cos\theta)e^{im\phi}.
$$

To avoid ambiguity: throughout the rest of this page, $P_\ell^m$ includes the $(-1)^m$ above, and $Y_{\ell m}$ is normalized by the second formula.

With this convention,

$$
Y_{\ell,-m}=(-1)^mY_{\ell m}^*.
$$

## Completeness and the addition theorem

The spherical harmonics form a complete orthonormal basis for square-integrable functions on $S^2$:

$$
f(\Omega)=\sum_{\ell=0}^{\infty}\sum_{m=-\ell}^{\ell}
f_{\ell m}Y_{\ell m}(\Omega),
$$

where

$$
f_{\ell m}=\int_{S^2}d\Omega\,Y_{\ell m}^*(\Omega)f(\Omega).
$$

Distributionally,

$$
\sum_{\ell=0}^{\infty}\sum_{m=-\ell}^{\ell}
Y_{\ell m}(\Omega)Y_{\ell m}^*(\Omega')
=\delta_{S^2}(\Omega,\Omega'),
$$

where

$$
\int_{S^2}d\Omega'\,\delta_{S^2}(\Omega,\Omega')f(\Omega')=f(\Omega).
$$

The addition theorem says

$$
\sum_{m=-\ell}^{\ell}
Y_{\ell m}(\Omega)Y_{\ell m}^*(\Omega')
=\frac{2\ell+1}{4\pi}P_\ell(\cos\gamma),
$$

where $\gamma$ is the angle between the unit vectors $\hat n(\Omega)$ and $\hat n(\Omega')$:

$$
\cos\gamma=\hat n(\Omega)\cdot \hat n(\Omega').
$$

This theorem is the workhorse behind partial-wave expansions. It packages the $m$ degeneracy into a rotationally invariant function of the angle between two directions.

## Plane waves and partial waves

The three-dimensional plane wave has the expansion

$$
e^{i\mathbf k\cdot\mathbf r}
=4\pi\sum_{\ell=0}^{\infty}\sum_{m=-\ell}^{\ell}
i^\ell j_\ell(kr)
Y_{\ell m}(\hat r)Y_{\ell m}^*(\hat k),
$$

where

$$
j_\ell(z)=\sqrt{\frac{\pi}{2z}}J_{\ell+1/2}(z)
$$

is a spherical Bessel function.

If $\hat k$ is chosen as the polar axis, this reduces to

$$
e^{ikr\cos\theta}
=\sum_{\ell=0}^{\infty}(2\ell+1)i^\ell j_\ell(kr)P_\ell(\cos\theta).
$$

This formula explains the division of labor:

$$
\text{angular dependence} \longleftrightarrow P_\ell(\cos\theta),
\qquad
\text{radial dependence} \longleftrightarrow j_\ell(kr).
$$

Partial waves diagonalize rotationally invariant scattering. For a central potential in three dimensions, the scattering amplitude is often written

$$
f(\theta)=\frac1{2ik}\sum_{\ell=0}^{\infty}(2\ell+1)
\left(S_\ell-1\right)P_\ell(\cos\theta),
$$

where

$$
S_\ell=e^{2i\delta_\ell}
$$

for elastic scattering. Equivalently,

$$
f(\theta)=\frac1{k}\sum_{\ell=0}^{\infty}(2\ell+1)
e^{i\delta_\ell}\sin\delta_\ell\,P_\ell(\cos\theta).
$$

In QFT, partial waves are also a language for unitarity, resonances, crossing problems, conformal blocks, and spin decompositions.

## Legendre functions of the second kind

The Legendre equation has a second solution, conventionally called $Q_\ell(x)$. For example,

$$
Q_0(x)=\frac12\log\frac{x+1}{x-1}.
$$

For integer $\ell$, $Q_\ell$ has logarithmic branch points at $x=\pm1$. This is not an obscure special-function footnote. In physics, $Q_\ell$ appears when angular Green functions or partial-wave projected propagators are analytically continued through their cuts.

A common pattern is that $P_\ell$ is selected by regularity on $[-1,1]$, while $Q_\ell$ carries branch-cut behavior in the complex $x$-plane. If $x$ is a kinematic variable, those branch cuts often become physical cuts.

## Recurrence relations

Legendre polynomials obey

$$
(\ell+1)P_{\ell+1}(x)
=(2\ell+1)xP_\ell(x)-\ell P_{\ell-1}(x),
$$

and

$$
(1-x^2)P_\ell'(x)
=\ell\left(P_{\ell-1}(x)-xP_\ell(x)\right).
$$

The first relation is numerically useful, but not always stable in every direction or region of the complex plane. The second is useful when angular derivatives act on partial-wave expansions.

For spherical harmonics, angular momentum operators act as

$$
L_zY_{\ell m}=mY_{\ell m},
$$

and

$$
L^2Y_{\ell m}=\ell(\ell+1)Y_{\ell m}.
$$

With $\hbar=1$,

$$
L_\pm Y_{\ell m}
=\sqrt{\ell(\ell+1)-m(m\pm1)}\,Y_{\ell,m\pm1}.
$$

This is the bridge between special functions and representation theory: the fixed-$\ell$ harmonics form the spin-$\ell$ irreducible representation of $SO(3)$, or equivalently of $SU(2)$ with integer spin.

## Higher-dimensional spherical functions

In $d$ Euclidean dimensions, angular functions live on $S^{d-1}$. Hyperspherical harmonics satisfy

$$
\Delta_{S^{d-1}}Y_{\ell a}(\Omega)
=-\ell(\ell+d-2)Y_{\ell a}(\Omega),
$$

where $a$ labels the degeneracy. The degeneracy is

$$
g_\ell^{(d)}
=\frac{(2\ell+d-2)(\ell+d-3)!}{\ell!(d-2)!}.
$$

The analogue of the addition theorem uses Gegenbauer polynomials. Let

$$
\lambda=\frac{d-2}{2}.
$$

Then

$$
\sum_{a=1}^{g_\ell^{(d)}}Y_{\ell a}(\Omega)Y_{\ell a}^*(\Omega')
=\frac{g_\ell^{(d)}}{\operatorname{Vol}(S^{d-1})}
\frac{C_\ell^{\lambda}(\cos\gamma)}{C_\ell^{\lambda}(1)}.
$$

For $d=3$, $\lambda=1/2$ and

$$
C_\ell^{1/2}(x)=P_\ell(x),
$$

so this reduces to the familiar $S^2$ addition theorem.

This higher-dimensional version appears in conformal field theory, dimensional regularization, Euclidean partial waves, and harmonic analysis on spheres.

## Common QFT uses

**Central potentials and partial-wave unitarity.** Rotational symmetry decomposes scattering into independent angular momentum channels. The $S$-matrix is diagonal in $\ell,m$ for a central potential.

**Free-field mode expansions.** In spherical coordinates, field modes use $Y_{\ell m}(\Omega)$ times radial Bessel functions. This is useful near spherical boundaries, defects, entangling surfaces, and radial quantization setups.

**Multipole expansions.** The Coulomb kernel admits the expansion

$$
\frac1{|\mathbf r-\mathbf r'|}
=\sum_{\ell=0}^{\infty}\frac{r_<^\ell}{r_>^{\ell+1}}P_\ell(\cos\gamma),
$$

where $r_<=\min(r,r')$ and $r_>=\max(r,r')$. This is the classical ancestor of many angular Green-function decompositions.

**Spin and tensor decompositions.** Scalar spherical harmonics are only the beginning. Vector, tensor, and spin-weighted harmonics organize gauge fields, gravitons, CMB polarization, celestial amplitudes, and fields on curved backgrounds.

**Conformal partial waves.** Higher-dimensional conformal blocks generalize the idea of diagonalizing symmetry. Gegenbauer polynomials and spherical harmonics appear in radial coordinates and spin decompositions.

## Common pitfalls

**Dropping the sphere measure.** Orthogonality on $S^2$ uses $d\Omega=\sin\theta\,d\theta\,d\phi$. Forgetting the $\sin\theta$ turns a correct formula into mathematical confetti.

**Mixing phase conventions.** Some references put the Condon–Shortley phase in $P_\ell^m$; others put it in $Y_{\ell m}$; some omit it. Always check the convention before comparing Clebsch–Gordan coefficients or conjugation identities.

**Confusing $m$ with mass.** In $Y_{\ell m}$, $m$ is the magnetic quantum number. In QFT, $m$ is also often mass. Context saves lives.

**Using $P_\ell$ outside its domain without analytic continuation.** $P_\ell(x)$ is a polynomial for integer $\ell$, but Legendre functions with noninteger degree or second-kind solutions have branch choices. Kinematic analytic continuation can expose these choices.

**Thinking partial waves are only nonrelativistic.** The elementary expansion is familiar from quantum mechanics, but the same angular-momentum decomposition underlies relativistic scattering, unitarity bounds, conformal blocks, and finite-volume spectra.

**Forgetting degeneracy.** A fixed $\ell$ on $S^2$ has $2\ell+1$ values of $m$. In $d$ dimensions the degeneracy is $g_\ell^{(d)}$, not $2\ell+1$.

## Exercises

### Exercise 1: derive the Legendre equation

Starting from the $m=0$ angular eigenvalue equation

$$
\frac1{\sin\theta}\frac{d}{d\theta}
\left(\sin\theta\frac{d\Theta}{d\theta}\right)
=-\ell(\ell+1)\Theta,
$$

set $x=\cos\theta$ and show that $\Theta(x)$ obeys

$$
(1-x^2)\Theta''-2x\Theta'+\ell(\ell+1)\Theta=0.
$$

<details><summary><strong>Solution</strong></summary>

Since $x=\cos\theta$,

$$
\frac{d}{d\theta}=-\sin\theta\frac{d}{dx}.
$$

Therefore

$$
\sin\theta\frac{d\Theta}{d\theta}
=-\sin^2\theta\frac{d\Theta}{dx}
=-(1-x^2)\Theta'(x).
$$

Act once more with $d/d\theta=-\sin\theta\,d/dx$:

$$
\frac{d}{d\theta}\left(\sin\theta\frac{d\Theta}{d\theta}\right)
=\sin\theta\frac{d}{dx}\left[(1-x^2)\Theta'\right].
$$

Dividing by $\sin\theta$ gives

$$
\frac{d}{dx}\left[(1-x^2)\Theta'\right]
=-\ell(\ell+1)\Theta.
$$

Expanding the derivative,

$$
(1-x^2)\Theta''-2x\Theta'+\ell(\ell+1)\Theta=0.
$$

</details>

### Exercise 2: normalize the addition theorem

Assume rotational invariance implies

$$
\sum_{m=-\ell}^{\ell}Y_{\ell m}(\Omega)Y_{\ell m}^*(\Omega')
=A_\ell P_\ell(\cos\gamma).
$$

Set $\Omega=\Omega'$ and integrate over $\Omega$ to show that

$$
A_\ell=\frac{2\ell+1}{4\pi}.
$$

<details><summary><strong>Solution</strong></summary>

At $\Omega=\Omega'$, $\gamma=0$ and $P_\ell(1)=1$, so

$$
\sum_{m=-\ell}^{\ell}|Y_{\ell m}(\Omega)|^2=A_\ell.
$$

Integrate over $S^2$:

$$
\int d\Omega\sum_{m=-\ell}^{\ell}|Y_{\ell m}(\Omega)|^2
=\sum_{m=-\ell}^{\ell}1=2\ell+1,
$$

using orthonormality. The right-hand side gives

$$
\int d\Omega\,A_\ell=4\pi A_\ell.
$$

Thus

$$
A_\ell=\frac{2\ell+1}{4\pi}.
$$

</details>

### Exercise 3: recover the first terms of the plane-wave expansion

Use

$$
e^{iz\cos\theta}
=\sum_{\ell=0}^{\infty}(2\ell+1)i^\ell j_\ell(z)P_\ell(\cos\theta)
$$

and the small-$z$ behavior $j_0(z)=1+O(z^2)$, $j_1(z)=z/3+O(z^3)$ to reproduce

$$
e^{iz\cos\theta}=1+iz\cos\theta+O(z^2).
$$

<details><summary><strong>Solution</strong></summary>

Keep only $\ell=0$ and $\ell=1$ terms. Since $P_0=1$ and $P_1(\cos\theta)=\cos\theta$,

$$
\ell=0:\qquad (1)i^0j_0(z)P_0=1+O(z^2).
$$

For $\ell=1$,

$$
(3)i j_1(z)P_1(\cos\theta)
=3i\left(\frac z3+O(z^3)\right)\cos\theta
=iz\cos\theta+O(z^3).
$$

Therefore

$$
e^{iz\cos\theta}=1+iz\cos\theta+O(z^2),
$$

as expected.

</details>

### Exercise 4: degeneracy check in three dimensions

Use

$$
g_\ell^{(d)}
=\frac{(2\ell+d-2)(\ell+d-3)!}{\ell!(d-2)!}
$$

to show that $g_\ell^{(3)}=2\ell+1$.

<details><summary><strong>Solution</strong></summary>

Set $d=3$. Then

$$
g_\ell^{(3)}
=\frac{(2\ell+1)(\ell)!}{\ell!\,1!}
=2\ell+1.
$$

This is the familiar number of magnetic quantum numbers $m=-\ell,\dots,\ell$.

</details>

## References

- E. W. Hobson, *The Theory of Spherical and Ellipsoidal Harmonics*. Classic reference on spherical harmonics and Legendre functions.
- E. T. Whittaker and G. N. Watson, *A Course of Modern Analysis*. Classical reference for special functions.
- M. Abramowitz and I. A. Stegun, *Handbook of Mathematical Functions*. Useful for Legendre identities and normalization checks.
- NIST Digital Library of Mathematical Functions, chapters on Legendre, Gegenbauer, and related functions. Reliable formula reference.
- F. W. J. Olver et al., *NIST Handbook of Mathematical Functions*. Modern handbook version of the DLMF.
- A. R. Edmonds, *Angular Momentum in Quantum Mechanics*. Compact standard reference for angular momentum conventions.
- D. A. Varshalovich, A. N. Moskalev, and V. K. Khersonskii, *Quantum Theory of Angular Momentum*. Comprehensive reference for angular-momentum technology.
- P. M. Morse and H. Feshbach, *Methods of Theoretical Physics*. Useful for separation of variables, Green functions, and boundary-value problems.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Useful for partial waves and representation-theoretic foundations.
- M. Srednicki, *Quantum Field Theory*. Useful for QFT scattering and angular-momentum conventions.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for scattering, spin, and Standard Model applications.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*. Useful for conformal partial-wave and CFT applications.

## Version history

- 2026-06-26: Initial polished draft.
