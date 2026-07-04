---
title: "Modular Forms"
description: "Explains modular forms for QFT: the upper half-plane, the modular group, torus moduli, weights, multipliers, q-expansions, eta and theta functions, Eisenstein series, characters, partition functions, modular invariance, anomalies, and duality."
sidebar:
  label: "Modular Forms"
  order: 8
level: Advanced
status: "Polished draft"
source: "Standard references on modular forms, theta functions, Dedekind eta functions, elliptic curves, torus partition functions, conformal field theory, string perturbation theory, and duality, including Serre, Apostol, Koblitz, Diamond–Shurman, Zagier, Mumford, Whittaker–Watson, NIST DLMF, Polchinski, Di Francesco–Mathieu–Sénéchal, Ginsparg, Kac, Frenkel–Ben-Zvi, Maloney–Witten, Witten, and modern literature on vector-valued modular forms, modular bootstrap, elliptic genera, and S-duality."
topics:
  - modular form
  - modular group
  - upper half-plane
  - torus partition function
  - q-expansion
  - Dedekind eta function
  - theta function
  - Eisenstein series
  - modular invariant
  - CFT character
  - elliptic genus
  - S-duality
canonicalTopics:
  - modular-form
  - modular-group
  - upper-half-plane
  - torus-partition-function
  - q-expansion
  - dedekind-eta-function
  - theta-function
  - eisenstein-series
  - modular-invariant
  - cft-character
  - elliptic-genus
  - s-duality
researchStatus:
  established:
    - "Modular forms are holomorphic functions on the upper half-plane with controlled transformation law under a subgroup of SL(2,Z), together with suitable behavior at cusps."
    - "Eta functions, theta functions, Eisenstein series, modular discriminants, and modular functions such as j(tau) are standard building blocks for torus partition functions, lattice sums, characters, and elliptic genera."
  active:
    - "Vector-valued modular forms, modular differential equations, modular bootstrap constraints, mock and quantum modular forms, moonshine, elliptic genera, S-duality, and modular properties of QFT partition functions remain active research interfaces between QFT, CFT, string theory, number theory, and geometry."
---

## Summary

Modular forms are functions whose argument is the complex structure of a torus and whose transformation law knows that the same torus can be described by many different bases of cycles. A complex torus can be written as

$$
E_\tau=\mathbb C/(\mathbb Z+\tau\mathbb Z),
\qquad \operatorname{Im}\tau>0.
$$

The parameter $\tau$ lives in the upper half-plane

$$
\mathcal H=\{\tau\in\mathbb C:\operatorname{Im}\tau>0\}.
$$

Changing the $A$- and $B$-cycle basis acts by

$$
\tau\longmapsto \gamma\tau={a\tau+b\over c\tau+d},
\qquad
\gamma=\begin{pmatrix}a&b\\ c&d\end{pmatrix}\in SL(2,\mathbb Z).
$$

A modular form of weight $k$ transforms, roughly, as

$$
f(\gamma\tau)=(c\tau+d)^k f(\tau).
$$

The word "roughly" is doing honest work: one may need a subgroup, a multiplier system, vector-valued transformation laws, or controlled meromorphic behavior. In QFT, these refinements are not decoration. They are how anomalies, spin structures, chiral partition functions, and characters show up.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing torus geometry, modular transformations, weight-k modular laws, q-expansions, and QFT uses such as characters and partition functions.](/figures/math-toolkit/modular-forms-torus-flow.svg)

<figcaption>

Modular forms turn torus geometry into controlled analytic data. A torus is described by $\tau$, but changing the cycle basis acts by $SL(2,\mathbb Z)$. Modular forms transform with a weight, have $q$-expansions at the cusp, and supply the standard ingredients for torus partition functions, CFT characters, eta and theta functions, elliptic genera, anomalies, and dualities.

</figcaption>
</figure>

A useful QFT slogan is:

$$
\text{torus path integral} \quad\Longrightarrow\quad
\text{modular covariance or modular invariance}.
$$

For a two-dimensional CFT, the torus partition function is usually written

$$
Z(\tau,\bar\tau)=\operatorname{Tr}_{\mathcal H}
\left(q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24}\right),
\qquad
q=e^{2\pi i\tau}.
$$

Modular invariance says that $Z$ is unchanged when one cuts the same torus along a different pair of cycles. Modular covariance says that the object transforms by a known factor or matrix. Confusing those two ideas is a small sign error’s cooler, more dangerous cousin.

## Prerequisites and conventions

You should know [Analytic Functions](/math-toolkit/complex-analysis/analytic-functions/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), [Riemann Surfaces](/math-toolkit/complex-analysis/riemann-surfaces/), [Elliptic Functions and Integrals](/math-toolkit/special-functions-exact-equations/elliptic-functions-and-integrals/), [Characters](/math-toolkit/groups-representations/characters/), and [Compact Lie Groups](/math-toolkit/groups-representations/compact-lie-groups/). For determinants and oscillator products, it helps to know [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) and [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/).

This page uses

$$
q=e^{2\pi i\tau},
\qquad \operatorname{Im}\tau>0.
$$

Many mathematics references use the same convention. Some references on theta functions use $q_\theta=e^{\pi i\tau}$ instead. This is harmless, but it changes factors of $2$ in theta-function exponents. When using theta functions, always check whether the author’s $q$ is $e^{\pi i\tau}$ or $e^{2\pi i\tau}$. The notation gremlin lives there rent-free.

## The modular group

The group $SL(2,\mathbb Z)$ consists of integer matrices

$$
\gamma=\begin{pmatrix}a&b\\c&d\end{pmatrix},
\qquad ad-bc=1.
$$

It acts on the upper half-plane by fractional linear transformations:

$$
\gamma\tau={a\tau+b\over c\tau+d}.
$$

The imaginary part transforms as

$$
\operatorname{Im}(\gamma\tau)
={\operatorname{Im}\tau\over |c\tau+d|^2},
$$

so the action preserves $\mathcal H$. The two standard generators are

$$
T:\tau\mapsto\tau+1,
\qquad
S:\tau\mapsto-{1\over\tau}.
$$

Geometrically, $T$ changes one cycle by adding the other, while $S$ exchanges the two cycles up to orientation. Since $-I$ acts trivially on $\tau$, the effective group acting faithfully on $\mathcal H$ is

$$
PSL(2,\mathbb Z)=SL(2,\mathbb Z)/\{\pm I\}.
$$

A standard fundamental domain is

$$
\mathcal F=\left\{\tau\in\mathcal H:
|\tau|\ge1,
\quad -{1\over2}\le \operatorname{Re}\tau\le {1\over2}\right\},
$$

with boundary identifications. A modular-invariant function on $\mathcal H$ is really a function on the quotient moduli space

$$
\mathcal H/SL(2,\mathbb Z),
$$

up to the usual orbifold subtleties at special tori.

## Modular forms

Let $\Gamma\subset SL(2,\mathbb Z)$ be a subgroup. A holomorphic modular form of weight $k$ for $\Gamma$ is a holomorphic function $f:\mathcal H\to\mathbb C$ satisfying

$$
f(\gamma\tau)=(c\tau+d)^k f(\tau),
\qquad
\gamma=\begin{pmatrix}a&b\\c&d\end{pmatrix}\in\Gamma,
$$

and a regularity condition at the cusps. For $SL(2,\mathbb Z)$, the cusp at infinity is analyzed by

$$
q=e^{2\pi i\tau},
\qquad
\operatorname{Im}\tau\to\infty
\quad\Longleftrightarrow\quad
q\to0.
$$

If $f$ is holomorphic at the cusp, it has an expansion

$$
f(\tau)=\sum_{n=0}^{\infty}a_n q^n.
$$

A cusp form vanishes at the cusp:

$$
a_0=0.
$$

A modular function is a weight-zero modular object, usually allowed to be meromorphic:

$$
f(\gamma\tau)=f(\tau).
$$

The distinction matters. Modular forms transform with a factor. Modular functions are invariant. Partition functions are often modular invariant, while chiral building blocks are often modular covariant or vector-valued.

### Multipliers and half-integral weights

The simplest transformation law is not general enough for QFT. The Dedekind eta function has weight $1/2$ with a multiplier:

$$
\eta(\tau+1)=e^{\pi i/12}\eta(\tau),
$$

$$
\eta(-1/\tau)=(-i\tau)^{1/2}\eta(\tau),
$$

with a choice of square-root branch. This is not a nuisance; it is a signal. Half-integral weights and multipliers are the analytic shadow of spin structures, determinant lines, and quantum anomalies.

More generally, one may have

$$
f(\gamma\tau)=v(\gamma)(c\tau+d)^k f(\tau),
$$

where $v(\gamma)$ is a multiplier system. In a rational CFT, characters often transform as a vector:

$$
\chi_i(\gamma\tau)=\sum_j \rho(\gamma)_{ij}\chi_j(\tau),
$$

where $\rho$ is a finite-dimensional representation of the modular group or a related quotient.

## Standard examples

### Dedekind eta function

The Dedekind eta function is

$$
\eta(\tau)=q^{1/24}\prod_{n=1}^{\infty}(1-q^n).
$$

The factor $q^{1/24}$ is not random. It is the zeta-regularized zero-point energy of a chiral oscillator tower:

$$
-{1\over24}={1\over2}\zeta(-1).
$$

Thus the holomorphic oscillator partition function of a free chiral boson is essentially

$$
{1\over\eta(\tau)}
=q^{-1/24}\prod_{n=1}^{\infty}{1\over1-q^n}.
$$

This is the cleanest place to see how modular forms, determinants, and Casimir energies become the same calculation in different clothes.

### Theta functions

With $q=e^{2\pi i\tau}$, one common theta convention is

$$
\vartheta_3(\tau)=\sum_{n\in\mathbb Z} q^{n^2/2}
=\sum_{n\in\mathbb Z} e^{\pi i\tau n^2}.
$$

More generally, theta functions are lattice sums. For an even lattice $\Lambda$ with bilinear form $(\cdot,\cdot)$,

$$
\Theta_\Lambda(\tau)=\sum_{\lambda\in\Lambda}q^{(\lambda,\lambda)/2}.
$$

These appear in compact bosons, toroidal compactifications, current algebras, theta angles, spin structures, and finite-temperature sums. The modular behavior of a theta function knows the arithmetic and duality properties of the lattice.

### Eisenstein series

For even $k\ge4$, the normalized Eisenstein series for $SL(2,\mathbb Z)$ is

$$
E_k(\tau)=1-{2k\over B_k}\sum_{n=1}^{\infty}\sigma_{k-1}(n)q^n,
$$

where $B_k$ is a Bernoulli number and

$$
\sigma_{p}(n)=\sum_{d\mid n}d^p.
$$

The most common cases are

$$
E_4(\tau)=1+240\sum_{n=1}^{\infty}\sigma_3(n)q^n,
$$

$$
E_6(\tau)=1-504\sum_{n=1}^{\infty}\sigma_5(n)q^n.
$$

The graded ring of holomorphic modular forms for $SL(2,\mathbb Z)$ is generated by $E_4$ and $E_6$:

$$
M_*(SL(2,\mathbb Z))=\mathbb C[E_4,E_6].
$$

This compact algebraic fact is why many torus answers collapse into combinations of $E_4$, $E_6$, $\eta$, and theta functions.

### Discriminant and j-function

The modular discriminant is the weight-12 cusp form

$$
\Delta(\tau)=\eta(\tau)^{24}
=q\prod_{n=1}^{\infty}(1-q^n)^{24}.
$$

With this normalization,

$$
\Delta(\tau)={E_4(\tau)^3-E_6(\tau)^2\over1728}.
$$

The modular $j$-function is the basic meromorphic modular function

$$
j(\tau)={E_4(\tau)^3\over\Delta(\tau)}
=q^{-1}+744+196884q+21493760q^2+\cdots.
$$

It classifies elliptic curves over $\mathbb C$ up to isomorphism. In physics, $j$ and related modular functions appear in torus moduli, threshold corrections, moonshine, and special holomorphic CFTs.

## Modular invariance in two-dimensional CFT

For a two-dimensional CFT on a torus, the Euclidean path integral can be evaluated as a trace over the Hilbert space on a spatial circle:

$$
Z(\tau,\bar\tau)=\operatorname{Tr}_{\mathcal H}
\left(q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24}\right).
$$

The shift by $c/24$ is the Casimir energy on the cylinder. The modular transformation $S:\tau\mapsto-1/\tau$ exchanges the two cycles of the torus, so it relates a low-temperature expansion to a high-temperature one.

In a rational CFT, the Hilbert space decomposes into finitely many chiral sectors, and one writes

$$
Z(\tau,\bar\tau)=\sum_{i,j}M_{ij}\chi_i(\tau)\overline{\chi_j(\tau)}.
$$

The characters transform by matrices $S$ and $T$:

$$
\chi_i(-1/\tau)=\sum_j S_{ij}\chi_j(\tau),
$$

$$
\chi_i(\tau+1)=\sum_j T_{ij}\chi_j(\tau).
$$

Modular invariance requires

$$
S^\dagger M S=M,
\qquad
T^\dagger M T=M,
$$

or equivalently, depending on index conventions,

$$
MS=SM,
\qquad
MT=TM.
$$

This is not just a technical consistency condition. It constrains the spectrum and operator content. Combined with positivity and crossing, modular invariance is one of the sharpest nonperturbative constraints in two-dimensional CFT.

## Modular covariance, anomalies, and determinant lines

A full nonchiral partition function may be modular invariant, but chiral pieces often are not. A chiral determinant, character, or current-algebra block may transform by a phase, a power of $c\tau+d$, or a matrix. That transformation is modular covariance.

Physically, this is the same theme as anomalies. A symmetry can act on the background geometry while the quantum functional integral transforms by a nontrivial line-bundle factor. In two-dimensional CFT, the chiral partition function should often be viewed as a section of a determinant line bundle over moduli space, not as an honest scalar function.

For example, $\eta(\tau)$ transforms with weight $1/2$ and a multiplier. Therefore $1/\eta(\tau)$ is not modular invariant by itself. Modular invariance usually emerges only after adding zero modes, antiholomorphic pieces, lattice sums, ghost contributions, or a suitable sum over spin structures.

## Modular forms beyond torus CFT

Modular forms enter QFT in several recurring ways.

### Finite temperature and compactification

A Euclidean thermal path integral has an imaginary-time circle. In two dimensions, the thermal cylinder can be sewn into a torus, so modular transformations relate different channel decompositions. Even in higher-dimensional QFTs, compactification on tori introduces modular groups acting on shape parameters and background holonomies.

### Lattice sums and theta functions

Compact bosons and gauge fields with flux sectors produce theta functions. Poisson resummation is the elementary mechanism behind many modular transformations:

$$
\sum_{n\in\mathbb Z}e^{-\pi a n^2}
={1\over\sqrt a}\sum_{m\in\mathbb Z}e^{-\pi m^2/a}.
$$

This identity is the one-dimensional ancestor of the modular $S$ transformation for theta functions.

### Elliptic genera

In supersymmetric theories, the elliptic genus is a protected torus partition function with signs and flavor fugacities. It is often a weak Jacobi form rather than an ordinary modular form. Schematically,

$$
\mathcal Z(\tau,z)=\operatorname{Tr}_{\mathcal H}
\left((-1)^F q^{L_0-c/24}y^J\right),
\qquad y=e^{2\pi i z}.
$$

The extra variable $z$ tracks flavor or R-symmetry charge. Its transformation law contains both modular and elliptic shifts, and the index of the Jacobi form encodes anomaly data.

### Duality and couplings

In four-dimensional gauge theory, a complexified coupling may be written

$$
\tau_{\mathrm{YM}}={\theta\over2\pi}+{4\pi i\over g^2}.
$$

An $SL(2,\mathbb Z)$-type duality can act on $\tau_{\mathrm{YM}}$ by fractional linear transformations. When this is an exact or protected statement, observables often transform as modular or quasi-modular objects. The physics is not the same as torus moduli, but the mathematics is the same group action.

### Quasi-modular forms

The Eisenstein series $E_2$ is not a modular form. It transforms with an extra inhomogeneous term:

$$
E_2\left({a\tau+b\over c\tau+d}\right)
=(c\tau+d)^2E_2(\tau)-{6i\over\pi}c(c\tau+d).
$$

Such quasi-modular behavior appears naturally when differentiating modular forms, computing gravitational or holomorphic anomalies, or working with almost-holomorphic completions. In physics, quasi-modularity is often the polite mathematical version of "the derivative did not stay inside the space I wanted."

## Modular differential equations

Characters of rational CFTs are often constrained by modular differential equations. The simplest idea is that a finite vector of characters

$$
\chi(\tau)=\begin{pmatrix}\chi_1(\tau)\\ \vdots\\ \chi_N(\tau)\end{pmatrix}
$$

transforms in a finite-dimensional modular representation. One can then build modular-covariant differential operators that preserve the transformation law.

The ordinary derivative does not map modular forms to modular forms. A useful covariant derivative is the Serre derivative:

$$
D_k f={1\over2\pi i}{d f\over d\tau}-{k\over12}E_2 f.
$$

If $f$ has weight $k$, then $D_k f$ has weight $k+2$. Modular differential equations built from $D_k$ provide a compact way to encode characters and spectra. This viewpoint is especially useful in rational CFT and modular bootstrap problems.

## Common pitfalls

### Treating modular covariance as invariance

A chiral character $\chi_i(\tau)$ is usually not invariant. It transforms into a linear combination of characters. A full partition function may be invariant after pairing holomorphic and antiholomorphic sectors.

### Forgetting the cusp condition

A holomorphic function satisfying a transformation law on $\mathcal H$ is not automatically a modular form. Its behavior at cusps matters. The $q$-expansion is not a computational afterthought; it is part of the definition.

### Mixing q conventions

If $q=e^{2\pi i\tau}$, then $e^{\pi i\tau}=q^{1/2}$. Many theta identities look wrong by a factor of $2$ if you silently switch conventions.

### Assuming every modular-looking object has integer weight

Eta functions, theta functions, fermion determinants, and spin-structure sums often involve half-integral weights, multipliers, or vector-valued modular transformations.

### Reading the S transformation as a small perturbation

The map $S:\tau\mapsto-1/\tau$ is often a strong–weak or high–low transformation. A $q$-expansion at $\tau\to i\infty$ need not converge usefully after applying $S$ unless transformed properly.

## Exercises

### Exercise 1: The upper half-plane is preserved

Let

$$
\gamma=\begin{pmatrix}a&b\\c&d\end{pmatrix}\in SL(2,\mathbb R),
\qquad
\gamma\tau={a\tau+b\over c\tau+d}.
$$

Show that

$$
\operatorname{Im}(\gamma\tau)
={\operatorname{Im}\tau\over |c\tau+d|^2}.
$$

<details><summary><strong>Solution</strong></summary>

Write $\tau=x+iy$ with $y>0$. Then

$$
\gamma\tau-\overline{\gamma\tau}
={a\tau+b\over c\tau+d}-{a\bar\tau+b\over c\bar\tau+d}.
$$

Putting over a common denominator gives

$$
\gamma\tau-\overline{\gamma\tau}
={ (a\tau+b)(c\bar\tau+d)-(a\bar\tau+b)(c\tau+d)
\over |c\tau+d|^2 }.
$$

The numerator is

$$
(ac\tau\bar\tau+ad\tau+bc\bar\tau+bd)
-(ac\tau\bar\tau+ad\bar\tau+bc\tau+bd)
=(ad-bc)(\tau-\bar\tau).
$$

Since $ad-bc=1$,

$$
\gamma\tau-\overline{\gamma\tau}
={\tau-\bar\tau\over |c\tau+d|^2}.
$$

Dividing by $2i$ gives

$$
\operatorname{Im}(\gamma\tau)
={\operatorname{Im}\tau\over |c\tau+d|^2}.
$$

</details>

### Exercise 2: Eta as an oscillator partition function

A chiral bosonic oscillator tower has one oscillator at each positive integer level. Its oscillator trace is

$$
Z_{\mathrm{osc}}(q)=q^{-1/24}\prod_{n=1}^{\infty}{1\over1-q^n}.
$$

Show that

$$
Z_{\mathrm{osc}}(q)={1\over\eta(\tau)}.
$$

<details><summary><strong>Solution</strong></summary>

By definition,

$$
\eta(\tau)=q^{1/24}\prod_{n=1}^{\infty}(1-q^n).
$$

Taking the reciprocal gives

$$
{1\over\eta(\tau)}=q^{-1/24}\prod_{n=1}^{\infty}{1\over1-q^n},
$$

which is exactly $Z_{\mathrm{osc}}(q)$. The factor $q^{-1/24}$ is the regularized zero-point energy contribution.

</details>

### Exercise 3: Modular invariance of a character pairing

Suppose the vector of characters transforms as

$$
\chi(\gamma\tau)=\rho(\gamma)\chi(\tau),
$$

and define

$$
Z(\tau,\bar\tau)=\chi(\tau)^\dagger M\chi(\tau).
$$

Show that $Z$ is invariant under $\gamma$ if

$$
\rho(\gamma)^\dagger M\rho(\gamma)=M.
$$

<details><summary><strong>Solution</strong></summary>

Under $\gamma$,

$$
Z(\gamma\tau,\overline{\gamma\tau})
=\chi(\gamma\tau)^\dagger M\chi(\gamma\tau).
$$

Using $\chi(\gamma\tau)=\rho(\gamma)\chi(\tau)$,

$$
Z(\gamma\tau,\overline{\gamma\tau})
=\chi(\tau)^\dagger \rho(\gamma)^\dagger M\rho(\gamma)\chi(\tau).
$$

If

$$
\rho(\gamma)^\dagger M\rho(\gamma)=M,
$$

then

$$
Z(\gamma\tau,\overline{\gamma\tau})=\chi(\tau)^\dagger M\chi(\tau)=Z(\tau,\bar\tau).
$$

</details>

### Exercise 4: Why the Serre derivative is needed

Let $f$ be a modular form of weight $k$. Explain why the ordinary derivative $d f/d\tau$ does not transform as a modular form of weight $k+2$, and why the appearance of $E_2$ in

$$
D_k f={1\over2\pi i}{d f\over d\tau}-{k\over12}E_2 f
$$

is natural.

<details><summary><strong>Solution</strong></summary>

The transformation law is

$$
f(\gamma\tau)=(c\tau+d)^k f(\tau).
$$

Differentiating both sides produces two terms: one from differentiating $f(\tau)$ and another from differentiating the factor $(c\tau+d)^k$. That extra term prevents $df/d\tau$ from transforming homogeneously with weight $k+2$.

The Eisenstein series $E_2$ transforms with its own inhomogeneous term. The inhomogeneous term in $E_2 f$ is precisely arranged to cancel the inhomogeneous term from differentiating $(c\tau+d)^k$. Therefore $D_k f$ transforms as a modular form of weight $k+2$.

</details>

## Related pages

For the torus and branch-cut geometry behind modular functions, see [Riemann Surfaces](/math-toolkit/complex-analysis/riemann-surfaces/) and [Elliptic Functions and Integrals](/math-toolkit/special-functions-exact-equations/elliptic-functions-and-integrals/). For representation-theoretic characters, see [Characters](/math-toolkit/groups-representations/characters/), [Roots, Weights, and Dynkin Diagrams](/math-toolkit/groups-representations/roots-weights-and-dynkin-diagrams/), and [Compact Lie Groups](/math-toolkit/groups-representations/compact-lie-groups/). For the determinant side of eta functions, see [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) and [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/). For nonlinear monodromy problems that extend beyond classical modular functions, see [Painlevé Equations](/math-toolkit/special-functions-exact-equations/painleve-equations/).

## References and further reading

For mathematical foundations, see Serre's *A Course in Arithmetic*, Apostol's *Modular Functions and Dirichlet Series in Number Theory*, Koblitz's *Introduction to Elliptic Curves and Modular Forms*, Diamond and Shurman's *A First Course in Modular Forms*, Zagier's expository articles, Mumford's *Tata Lectures on Theta*, and the NIST Digital Library of Mathematical Functions. For theta functions and elliptic functions, see Whittaker–Watson and modern references on elliptic curves and complex tori. For CFT applications, see Di Francesco–Mathieu–Sénéchal, Ginsparg's lectures, Kac, Frenkel–Ben-Zvi, and the modular-invariance literature on rational CFT, WZW models, vertex operator algebras, and modular tensor categories. For string theory, elliptic genera, and duality applications, see standard texts and reviews by Polchinski, Witten, Harvey, Moore, and later literature on modular bootstrap, mock modularity, and S-duality.

## Version history

- **2026-06-26:** Initial polished draft. Added modular group, torus interpretation, modular forms and functions, cusp expansions, eta and theta functions, Eisenstein series, discriminant and $j$-function, torus CFT partition functions, modular covariance, anomalies, modular differential equations, QFT applications, common pitfalls, exercises with solutions, and TikZ/SVG figure.
