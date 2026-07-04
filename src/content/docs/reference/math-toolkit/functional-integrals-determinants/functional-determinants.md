---
title: "Functional Determinants"
description: "A QFT-oriented guide to determinants of differential operators, one-loop fluctuation determinants, zero modes, determinant ratios, heat-kernel and zeta regularization, phases, and domain dependence."
sidebar:
  label: "Functional Determinants"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki, functional determinants; Coleman, instantons and false-vacuum decay; Schwartz, path integrals and effective actions; Zinn-Justin, functional methods; Weinberg, external field methods and gauge fixing."
topics:
  - functional determinants
  - one-loop effective action
  - heat kernels
  - zeta regularization
  - zero modes
canonicalTopics:
  - functional-determinants
  - one-loop-determinants
  - spectral-regularization
  - determinant-ratios
researchStatus:
  established:
    - "Finite-dimensional determinant identities and regulated determinant ratios of suitable elliptic operators are standard tools in semiclassical and one-loop QFT."
  active:
    - "The phase, sign, multiplicative properties, zero-mode treatment, and continuum definition of functional determinants can depend on regulator, boundary conditions, spectral asymmetry, gauge fixing, and global topology."
---

## Summary

A functional determinant is the field-theory descendant of the finite-dimensional determinant in a Gaussian integral. In finite dimension,

$$
\int d^n x\,
\exp\left(-\frac12 x^T A x\right)
\propto (\det A)^{-1/2}.
$$

For a free scalar field with quadratic Euclidean action

$$
S_E[\phi]=\frac12\int d^d x\,\phi K\phi,
$$

the formal analogue is

$$
\int D\phi\,e^{-S_E[\phi]}
\propto (\det K)^{-1/2}.
$$

The word “formal” is doing real work. If $K$ is a differential operator, its determinant wants to be an infinite product of eigenvalues,

$$
\det K\stackrel{\text{formal}}{=}\prod_n\lambda_n.
$$

This product almost never converges without interpretation. A functional determinant is therefore not just an infinite determinant; it is a **regulated spectral object**, together with choices of operator, domain, boundary conditions, zero-mode treatment, phase convention, and renormalization scheme.

<figure class="doc-figure" style="--figure-width: 49rem;">

![Functional determinant workflow from an operator and boundary data to a regulated one-loop contribution.](/figures/math-toolkit/functional-determinant-spectrum.svg)

<figcaption>

A functional determinant is built from more than a differential expression. One must specify the operator, domain, boundary conditions, spectrum, regulator, zero-mode prescription, and renormalization scheme before the symbol $\det K$ has a stable meaning.

</figcaption>
</figure>

The safe practical rule is:

$$
\boxed{\text{never ask for }\det K\text{ before saying what regulates the spectrum.}}
$$

## Prerequisites

You should know [Finite-Dimensional Gaussians](/math-toolkit/functional-integrals-determinants/finite-dimensional-gaussians/), [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/), [Grassmann Algebra](/math-toolkit/functional-integrals-determinants/grassmann-algebra/), [Berezin Integration](/math-toolkit/functional-integrals-determinants/berezin-integration/), and [Pfaffians](/math-toolkit/functional-integrals-determinants/pfaffians/).

You should also be comfortable with distributions and Fourier modes from [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/) and with the idea that differential operators require domains, as previewed in [Sobolev Spaces Preview](/math-toolkit/analysis-distributions-fourier/sobolev-spaces-preview/).

## Core idea

A determinant is easiest to define when an operator has a discrete spectrum. Suppose $K$ acts on a finite-dimensional vector space and has eigenvalues $\lambda_1,\ldots,\lambda_N$. Then

$$
\det K=\prod_{n=1}^N\lambda_n,
\qquad
\log\det K=\sum_{n=1}^N\log\lambda_n=\operatorname{Tr}\log K.
$$

In QFT, a quadratic fluctuation operator often has infinitely many eigenvalues. For example, on a compact Euclidean domain, the scalar operator

$$
K=-\partial^2+m^2
$$

has eigenvalues schematically

$$
\lambda_n=p_n^2+m^2.
$$

The formal determinant is

$$
\det(-\partial^2+m^2)=\prod_n(p_n^2+m^2),
$$

and the formal logarithm is

$$
\operatorname{Tr}\log(-\partial^2+m^2)=\sum_n\log(p_n^2+m^2).
$$

Both expressions diverge in the ultraviolet because there are too many large eigenvalues. In infinite volume there is also a continuum of modes, and the sum becomes a divergent momentum integral.

A regularization scheme gives meaning to the expression by replacing the divergent sum with a controlled object. A renormalization scheme then decides which local divergent pieces are subtracted or absorbed into couplings.

## Setup and conventions

Unless otherwise stated, this page discusses Euclidean quadratic operators. The cleanest basic case is a positive self-adjoint operator $K$ with discrete positive spectrum

$$
0<\lambda_1\le\lambda_2\le\cdots.
$$

The assumptions matter. If $K$ has zero modes, one must define a primed determinant

$$
\det{}'K=\prod_{\lambda_n\ne0}\lambda_n
$$

and treat the zero modes separately. If $K$ has negative modes, the Gaussian is not a convergent positive Euclidean Gaussian; the determinant carries a phase or signals an instability. If $K$ is not self-adjoint, the determinant may require spectral cuts, complex phases, or a different formulation.

A differential expression such as

$$
-\frac{d^2}{dx^2}+m^2
$$

is not yet an operator. The operator also includes its domain and boundary conditions. Dirichlet, Neumann, periodic, antiperiodic, and mixed boundary conditions give different spectra and therefore different determinants.

Lorentzian determinants require additional data: $i\epsilon$ prescriptions, integration contours, causal boundary conditions, or analytic continuation from Euclidean signature. The algebraic determinant identities are the same, but the analytic meaning is more delicate.

## Determinants from one-loop fluctuations

Let $\phi_{\mathrm{cl}}$ be a classical saddle of a Euclidean action. Expand

$$
\phi=\phi_{\mathrm{cl}}+\eta.
$$

If the first variation vanishes and the second variation is governed by a fluctuation operator $K$, then

$$
S_E[\phi]
=S_E[\phi_{\mathrm{cl}}]
+\frac12\langle \eta,K\eta\rangle
+O(\eta^3).
$$

The quadratic approximation gives

$$
Z\approx e^{-S_E[\phi_{\mathrm{cl}}]}
\int D\eta\,
\exp\left(-\frac12\langle \eta,K\eta\rangle\right).
$$

Formally,

$$
Z\approx e^{-S_E[\phi_{\mathrm{cl}}]}(\det K)^{-1/2}.
$$

The one-loop contribution to the effective action is therefore

$$
\Gamma^{(1)}_{\mathrm{boson}}
=\frac12\operatorname{Tr}\log K.
$$

For a complex bosonic field with action $\phi^\dagger K\phi$, the Gaussian gives

$$
Z\propto (\det K)^{-1},
\qquad
\Gamma^{(1)}=\operatorname{Tr}\log K.
$$

For complex Grassmann variables,

$$
\int D\bar\psi D\psi\,e^{-\bar\psi D\psi}=\det D,
$$

so a Dirac fermion contributes

$$
\Gamma^{(1)}_{\mathrm{Dirac}}
=-\operatorname{Tr}\log D.
$$

For real Grassmann variables, or Majorana fermions, the answer is a Pfaffian:

$$
Z_{\mathrm{Majorana}}\propto \operatorname{Pf}(B),
\qquad
\Gamma^{(1)}_{\mathrm{Majorana}}=-\log\operatorname{Pf}(B).
$$

When $B$ is antisymmetric and invertible,

$$
\log\operatorname{Pf}(B)=\frac12\operatorname{Tr}\log B
$$

up to the sign or phase data discussed in [Pfaffians](/math-toolkit/functional-integrals-determinants/pfaffians/).

A useful one-loop sign table is:

| Field type | Quadratic action | Gaussian factor in $Z$ | Contribution to $\Gamma=-\log Z$ |
|---|---|---|---|
| real boson | $\frac12\phi K\phi$ | $(\det K)^{-1/2}$ | $+\frac12\operatorname{Tr}\log K$ |
| complex boson | $\phi^\dagger K\phi$ | $(\det K)^{-1}$ | $+\operatorname{Tr}\log K$ |
| Dirac fermion | $\bar\psi D\psi$ | $\det D$ | $-\operatorname{Tr}\log D$ |
| Majorana fermion | $\frac12\psi^T B\psi$ | $\operatorname{Pf}(B)$ | $-\log\operatorname{Pf}(B)$ |
| Faddeev–Popov ghost | $\bar c M c$ | $\det M$ | $-\operatorname{Tr}\log M$ |

The table is finite-dimensional algebra plus field-theory interpretation. The hard part is defining the traces and determinants.

## The variation identity

The most reliable formula for determinants is often not the determinant itself, but its variation. In finite dimension,

$$
\delta\log\det K
=\operatorname{Tr}(K^{-1}\delta K).
$$

This remains one of the safest formal identities in QFT when both sides are regulated consistently. It says that the variation of a one-loop determinant is controlled by the Green function of the fluctuation operator.

For a scalar operator

$$
K=-\partial^2+m^2+V(x),
$$

a variation $\delta V(x)$ gives

$$
\delta\log\det K
=\operatorname{Tr}(K^{-1}\delta V)
=\int d^d x\,G(x,x)\delta V(x),
$$

where

$$
K G(x,y)=\delta^{(d)}(x-y).
$$

The expression $G(x,x)$ is usually ultraviolet divergent. This is not a failure of the identity. It is the local short-distance singularity that renormalization must handle.

A useful special case is the mass derivative:

$$
\frac{\partial}{\partial m^2}\log\det(-\partial^2+m^2)
=\operatorname{Tr}\frac{1}{-\partial^2+m^2}.
$$

In infinite volume this becomes

$$
\frac{\partial}{\partial m^2}\frac{1}{V}\log\det(-\partial^2+m^2)
=\int\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+m^2},
$$

which makes the ultraviolet behavior transparent.

## Determinant ratios

Absolute determinants often contain arbitrary normalization constants. Ratios are usually more meaningful:

$$
\frac{\det K}{\det K_0},
\qquad
\log\frac{\det K}{\det K_0}
=\operatorname{Tr}\log K-\operatorname{Tr}\log K_0.
$$

If $K$ and $K_0$ have the same high-frequency behavior, the ratio can cancel many ultraviolet divergences. This is why fluctuation determinants around solitons, instantons, bounces, and background fields are often written as

$$
\left(\frac{\det{}' K}{\det K_0}\right)^{-1/2}.
$$

The prime means that zero modes have been removed from the determinant. Those modes are then replaced by collective-coordinate integrals or by explicit insertions, depending on whether the zero modes are bosonic or fermionic.

Ratios do not remove every issue. There can still be divergences requiring counterterms, phases from negative modes, infrared subtleties, or scheme-dependent finite local terms. But ratios are usually the right starting point.

## Cutoff regularization

The simplest idea is to cut off the spectrum. If $K$ has positive eigenvalues $\lambda_n$, define

$$
\log\det_{\Lambda}K
=\sum_{\lambda_n\le\Lambda^2}\log\lambda_n.
$$

For a field theory in a box, this is similar to imposing a maximum momentum. In infinite volume, one writes schematically

$$
\operatorname{Tr}\log(-\partial^2+m^2)
\sim V\int^{\Lambda}\frac{d^d p}{(2\pi)^d}\log(p^2+m^2).
$$

Cutoffs are physically intuitive and close to Wilsonian thinking, but they may break symmetries if implemented carelessly. A hard momentum cutoff can break gauge invariance or spacetime symmetries. A lattice cutoff preserves locality and can preserve gauge invariance, but it changes rotation symmetry at short distances. A regulator is not just a calculator. It is part of the definition of what is being approximated.

The divergent pieces of cutoff determinants are usually local. They renormalize vacuum energy, masses, couplings, wavefunction normalizations, curvature couplings, or boundary counterterms.

## Heat-kernel regularization

For a positive operator $K$, the logarithm can be represented by a proper-time integral:

$$
\log\lambda=-\int_0^\infty\frac{dt}{t}e^{-t\lambda}+\text{constant}.
$$

Thus

$$
\operatorname{Tr}\log K
=-\int_0^\infty\frac{dt}{t}\operatorname{Tr}(e^{-tK})+\text{constant}.
$$

The heat kernel is

$$
H(t)=\operatorname{Tr}(e^{-tK}).
$$

The ultraviolet region is $t\to0^+$. A regulated version is

$$
\operatorname{Tr}\log K\big|_{\epsilon}
=-\int_{\epsilon}^{\infty}\frac{dt}{t}\operatorname{Tr}(e^{-tK}).
$$

For a Laplace-type operator on a smooth compact $d$-dimensional space, the small-$t$ expansion has the form

$$
\operatorname{Tr}(e^{-tK})
\sim
\frac{1}{(4\pi t)^{d/2}}
\sum_{r\ge0}a_r(K)t^r,
\qquad t\to0^+.
$$

The coefficients $a_r(K)$ are local geometric quantities built from the background fields, curvature, bundle connection, potential terms, and boundary data. They are the heat-kernel way of seeing why one-loop ultraviolet divergences are local.

This method is especially useful in curved spacetime, background-field calculations, anomalies, Casimir problems, and one-loop effective actions.

## Zeta regularization

If $K$ has positive discrete eigenvalues, define the spectral zeta function

$$
\zeta_{K/\mu^2}(s)=\sum_n\left(\frac{\lambda_n}{\mu^2}\right)^{-s},
$$

where $\mu$ is a reference scale inserted to make the eigenvalue ratio dimensionless. The sum converges for sufficiently large $\operatorname{Re}(s)$ and is then analytically continued to $s=0$ when possible. The zeta-regularized determinant is

$$
\log\det_{\zeta}\left(\frac{K}{\mu^2}\right)
=-\zeta'_{K/\mu^2}(0).
$$

This definition is elegant and often powerful. It packages the subtraction of divergent spectral sums into analytic continuation. It is also not magic. The result depends on the scale $\mu$, boundary conditions, spectral cuts when eigenvalues are not positive, and the analytic structure of $\zeta_K(s)$.

Zeta regularization is best viewed as one precise scheme, not as the unique meaning of a functional determinant.

## Boundary conditions and domains

A functional determinant is a determinant of an operator, not merely of a differential expression. Consider

$$
K=-\frac{d^2}{dx^2}+m^2
$$

on an interval. With Dirichlet boundary conditions,

$$
f(0)=f(L)=0,
$$

the eigenfunctions are sine modes and

$$
\lambda_n=\left(\frac{n\pi}{L}\right)^2+m^2,
\qquad n=1,2,\ldots.
$$

With periodic boundary conditions,

$$
f(x+L)=f(x),
$$

the eigenvalues are

$$
\lambda_n=\left(\frac{2\pi n}{L}\right)^2+m^2,
\qquad n\in\mathbb Z.
$$

These are different determinants. The same local differential expression has different spectral data because the domain is different.

This distinction is crucial in finite-temperature QFT, where bosons are periodic and fermions are antiperiodic around the Euclidean thermal circle; in Casimir problems, where boundary conditions are the physics; and in gauge theory, where boundary conditions affect edge modes, zero modes, and residual gauge transformations.

## Zero modes, negative modes, and primes

If $K$ has zero modes, then

$$
\det K=0.
$$

For a bosonic Gaussian, zero modes produce divergent integrals because the action does not suppress motion along flat directions. These flat directions are often symmetries or moduli. The correct procedure is to separate them:

$$
\eta=\sum_{a=1}^r q^a\eta_a^{(0)}+\eta_\perp,
$$

where $\eta_a^{(0)}$ are zero modes and $\eta_\perp$ lies in the nonzero subspace. The nonzero modes give

$$
(\det{}'K)^{-1/2},
$$

while the zero modes are integrated as collective coordinates, with their own Jacobian.

For fermionic zero modes, the situation is opposite. A missing quadratic term means the Berezin integral over that variable vanishes unless insertions saturate it. This is the selection-rule mechanism described in [Pfaffians](/math-toolkit/functional-integrals-determinants/pfaffians/).

Negative modes also require special care. A single negative mode in a Euclidean saddle means the saddle is not a local minimum. In false-vacuum decay, such a negative mode is not a mistake; it is the source of the imaginary part that encodes an instability. In stationary phase, negative modes contribute phases determined by the choice of contour.

The notation $\det{}'K$ means “the determinant after removing specified zero modes.” It does not by itself specify how the removed modes are normalized. That normalization is part of the calculation.

## Phases and spectral asymmetry

For positive self-adjoint $K$, the determinant can be chosen real and positive after regularization. For fermions and first-order operators, life is less polite.

A Dirac operator may have positive and negative eigenvalues, complex eigenvalues after continuation, or spectral asymmetry. Formally writing

$$
\det D=\prod_n\lambda_n
$$

requires a choice of how to define the product and its phase. One often replaces $D$ by a positive operator such as $D^\dagger D$ to compute magnitudes:

$$
\log|\det D|=\frac12\operatorname{Tr}\log(D^\dagger D).
$$

But this loses the phase. The phase can encode parity anomalies, chiral anomalies, eta invariants, or global sign information. Majorana Pfaffians are even more sensitive because the sign of the Pfaffian is the oriented square root of a determinant.

A practical rule:

$$
\text{using }D^\dagger D\text{ computes a magnitude, not necessarily the full quantum answer.}
$$

Whenever a determinant phase can affect symmetry, topology, or unitarity, it must be tracked explicitly.

## Multiplicative caveat

In finite dimension,

$$
\det(AB)=\det A\det B.
$$

For regulated functional determinants, the analogous statement can fail if the regulator does not preserve multiplicativity. In zeta regularization, for suitable operators $A$ and $B$, one can encounter a multiplicative anomaly:

$$
\log\det_{\zeta}(AB)
\ne
\log\det_{\zeta}A+
\log\det_{\zeta}B.
$$

In many physics calculations this difference is a local term that can be absorbed into a scheme choice, but it is still a warning: finite-dimensional determinant algebra should not be moved into infinite dimension without checking the regulator.

The safer identity is the regulated variation formula. If two determinant expressions have the same variations and the same normalization condition, then they agree in that scheme.

## Functional determinants in QFT examples

Functional determinants appear whenever a quadratic field is integrated out or fluctuations around a saddle are quantized.

**Free scalar partition functions.** A real scalar field gives

$$
Z_0\propto\left[\det(-\partial^2+m^2)\right]^{-1/2}.
$$

The determinant contains the vacuum energy and all oscillator-mode normalization factors.

**One-loop effective potentials.** Expanding around a constant background field gives a field-dependent fluctuation operator. The one-loop potential contains integrals of the form

$$
\frac12\int\frac{d^d p}{(2\pi)^d}\log(p^2+M^2(\phi)).
$$

**Fermion determinants.** Integrating out a Dirac fermion gives

$$
\det(\gamma^\mu D_\mu+m),
$$

or its Euclidean counterpart. Its magnitude and phase can affect effective actions, anomalies, and topological terms.

**Ghost determinants.** Gauge fixing introduces a determinant of the variation of the gauge-fixing condition along the gauge orbit. This determinant is represented by Grassmann ghost fields.

**Instanton and soliton fluctuations.** Semiclassical expansions around nontrivial saddles give determinant ratios such as

$$
\left(\frac{\det{}'K_{\mathrm{saddle}}}{\det K_{\mathrm{vac}}}\right)^{-1/2}
$$

together with zero-mode collective coordinates.

**Casimir energies.** Differences between determinants with different boundary conditions encode changes in vacuum energy.

**Localization.** Supersymmetric localization often reduces functional integrals to finite-dimensional integrals multiplied by one-loop determinants of fluctuation complexes.

The same algebra keeps reappearing. The physics lies in choosing the correct operator, boundary data, regulator, and subtraction.

## Common pitfalls

**“$\det K$ means $\prod_n\lambda_n$.”** That is only the unregulated mnemonic. The product needs a regulator, and different regulators can differ by local counterterms or phases.

**“The differential operator determines the determinant.”** Not without a domain. Boundary conditions, zero-mode restrictions, gauge conditions, and function spaces are part of the operator.

**“Zero modes can be included in the determinant.”** Not in the ordinary way. Bosonic zero modes make the Gaussian integral diverge; fermionic zero modes make it vanish unless insertions saturate them.

**“A determinant ratio is automatically finite.”** Ratios improve the ultraviolet behavior only when the high-frequency asymptotics match sufficiently. Counterterms may still be required.

**“$D^\dagger D$ contains the whole fermion determinant.”** It gives the magnitude, not necessarily the phase or sign. Anomalies and eta-invariant effects can live in what $D^\dagger D$ forgets.

**“Heat-kernel regularization removes physics.”** It separates local ultraviolet pieces from finite nonlocal data. The subtraction scheme must be specified; the local pieces are where counterterms and anomalies are organized.

**“Zeta regularization is regulator independent.”** Zeta regularization is a scheme. It is often elegant, but it still involves scale choices, analytic continuation, spectral assumptions, and sometimes multiplicative anomalies.

**“The one-loop determinant is just a normalization.”** Around a trivial free vacuum it may look like a normalization. In background fields, curved spaces, finite temperature, nontrivial topology, and gauge theory, it can contain real observable information.

## Relations to other pages

This page completes the first pass through the determinant backbone of the chapter. [Finite-Dimensional Gaussians](/math-toolkit/functional-integrals-determinants/finite-dimensional-gaussians/) and [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/) explain why bosons produce determinant denominators. [Berezin Integration](/math-toolkit/functional-integrals-determinants/berezin-integration/) explains why fermions produce determinant numerators. [Pfaffians](/math-toolkit/functional-integrals-determinants/pfaffians/) explains the real-fermion square root with sign data.

The next determinant pages should develop Zeta Regularization and the Heat-Kernel Expansion. Those pages should turn the schematic formulas in this page into reusable computational methods.

For analysis background, this page connects to Fourier methods, Sobolev spaces, spectral theory, Green functions, and boundary-value problems. For physics applications, it connects to one-loop effective actions, anomalies, instantons, gauge fixing, Casimir energies, finite-temperature determinants, and supersymmetric localization.

## Research status

The finite-dimensional determinant identities are elementary and exact. For suitable elliptic operators on compact spaces, heat-kernel and zeta-function methods provide precise determinant schemes, and determinant ratios are standard in one-loop QFT.

The subtleties are not cosmetic. In continuum field theory, determinants are tied to regularization, renormalization, phase choices, determinant/Pfaffian line bundles, zero modes, boundary conditions, noncompact spectra, gauge redundancy, and infrared behavior. These issues are active in anomaly theory, lattice fermions, curved-spacetime QFT, localization, spectral geometry, and nonperturbative path integrals.

## Exercises

### Exercise 1: Finite-dimensional origin

Let $A$ be a positive diagonal $N\times N$ matrix with entries $a_1,\ldots,a_N$. Compute

$$
\int_{\mathbb R^N}d^Nx\,
\exp\left(-\frac12x^TAx\right)
$$

and identify the determinant factor.

<details><summary><strong>Solution</strong></summary>

Since $A$ is diagonal,

$$
x^TAx=\sum_{i=1}^N a_i x_i^2.
$$

The integral factorizes:

$$
\int_{\mathbb R^N}d^Nx\,e^{-\frac12x^TAx}
=\prod_{i=1}^N\int_{-\infty}^{\infty}dx_i\,e^{-\frac12a_ix_i^2}.
$$

Each one-dimensional integral is

$$
\int_{-\infty}^{\infty}dx_i\,e^{-\frac12a_ix_i^2}
=\left(\frac{2\pi}{a_i}\right)^{1/2}.
$$

Therefore

$$
\int_{\mathbb R^N}d^Nx\,e^{-\frac12x^TAx}
=(2\pi)^{N/2}\prod_{i=1}^N a_i^{-1/2}
=(2\pi)^{N/2}(\det A)^{-1/2}.
$$

The functional determinant formula is the regulated infinite-dimensional analogue of this identity.

</details>

### Exercise 2: Variation of a determinant

Assume $K$ is an invertible finite-dimensional matrix. Show that

$$
\delta\log\det K=\operatorname{Tr}(K^{-1}\delta K).
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
\det(K+\delta K)=\det K\,\det(1+K^{-1}\delta K).
$$

Taking the logarithm gives

$$
\log\det(K+\delta K)
=\log\det K+\operatorname{Tr}\log(1+K^{-1}\delta K).
$$

To first order,

$$
\operatorname{Tr}\log(1+K^{-1}\delta K)
=\operatorname{Tr}(K^{-1}\delta K)+O((\delta K)^2).
$$

Thus

$$
\delta\log\det K=\operatorname{Tr}(K^{-1}\delta K).
$$

</details>

### Exercise 3: Mass derivative

For the formal operator

$$
K_m=-\partial^2+m^2
$$

on a translation-invariant Euclidean volume $V$, show that

$$
\frac{\partial}{\partial m^2}\frac{1}{V}\operatorname{Tr}\log K_m
=\int\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+m^2}.
$$

<details><summary><strong>Solution</strong></summary>

In momentum space,

$$
K_m(p)=p^2+m^2.
$$

The trace per unit volume becomes the momentum integral

$$
\frac{1}{V}\operatorname{Tr}\log K_m
=\int\frac{d^d p}{(2\pi)^d}\log(p^2+m^2),
$$

formally. Differentiating with respect to $m^2$ gives

$$
\frac{\partial}{\partial m^2}\frac{1}{V}\operatorname{Tr}\log K_m
=\int\frac{d^d p}{(2\pi)^d}\frac{\partial}{\partial m^2}\log(p^2+m^2)
=\int\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+m^2}.
$$

This integral is the coincident Green function $G(x,x)$ in momentum representation and is ultraviolet divergent for sufficiently large $d$.

</details>

### Exercise 4: Periodic zero mode

Consider

$$
K=-\frac{d^2}{dx^2}
$$

on a circle of circumference $L$, acting on periodic functions. Show that $K$ has a zero mode and explain why $\det{}'K$ is needed.

<details><summary><strong>Solution</strong></summary>

The periodic eigenfunctions are

$$
f_n(x)=e^{2\pi i n x/L},
\qquad n\in\mathbb Z.
$$

Acting with $K$ gives

$$
Kf_n=\left(\frac{2\pi n}{L}\right)^2 f_n.
$$

For $n=0$, $f_0(x)=1$ and

$$
Kf_0=0.
$$

Thus $K$ has a zero mode: the constant function. The determinant would include a factor $\lambda_0=0$, so $\det K=0$. In a bosonic Gaussian integral, this zero mode corresponds to an unsuppressed flat direction. One removes it from the determinant and writes $\det{}'K$, then treats the constant mode separately.

</details>

### Exercise 5: Heat-kernel divergence counting

Suppose a four-dimensional Laplace-type operator has

$$
\operatorname{Tr}(e^{-tK})
\sim
\frac{1}{(4\pi t)^2}(a_0+a_1t+a_2t^2+\cdots)
$$

as $t\to0^+$. Which terms can produce ultraviolet divergences in

$$
-\int_{\epsilon}^{\infty}\frac{dt}{t}\operatorname{Tr}(e^{-tK})
$$

as $\epsilon\to0^+$?

<details><summary><strong>Solution</strong></summary>

Insert the expansion:

$$
-\int_{\epsilon}^{\infty}\frac{dt}{t}\operatorname{Tr}(e^{-tK})
\sim
-\frac{1}{(4\pi)^2}
\int_{\epsilon}\frac{dt}{t}
\left(a_0t^{-2}+a_1t^{-1}+a_2+a_3t+\cdots\right).
$$

The terms behave near $t=0$ as

$$
a_0t^{-3},
\qquad
 a_1t^{-2},
\qquad
 a_2t^{-1},
\qquad
 a_3t^0,
\ldots.
$$

The $a_0$ term gives a power divergence proportional to $\epsilon^{-2}$, the $a_1$ term gives a power divergence proportional to $\epsilon^{-1}$, and the $a_2$ term gives a logarithmic divergence. Terms $a_3$ and higher are finite as $\epsilon\to0^+$.

Thus in four dimensions the divergent heat-kernel coefficients are $a_0$, $a_1$, and $a_2$, with $a_2$ controlling the logarithmic divergence.

</details>

## References

- M. Srednicki, *Quantum Field Theory*. Functional determinants, fermion determinants, one-loop effective actions, and Gaussian path integrals.
- S. Coleman, *Aspects of Symmetry*. Functional integration, instanton determinants, false-vacuum decay, and determinant ratios.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*. Functional integration, generating functionals, ghost determinants, and one-loop reasoning.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Path integrals, effective actions, one-loop determinants, Schwinger proper time, and background fields.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II. External field methods, effective action, gauge fixing, ghosts, and determinant methods.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Functional methods, saddle points, determinant regularization, and renormalization.
- A. Zee, *Quantum Field Theory in a Nutshell*. Physical intuition for Gaussian path integrals, determinants, anomalies, and effective actions.
- V. Pestun et al., *Localization Techniques in Quantum Field Theories*. One-loop determinants in supersymmetric localization and related spectral/geometric tools.

## Version history

- 2026-06-24: First polished draft. Introduced functional determinants as regulated spectral objects, derived one-loop determinant factors, explained variation identities, determinant ratios, cutoff, heat-kernel and zeta schemes, zero modes, phases, domains, multiplicative caveats, and common QFT applications.
