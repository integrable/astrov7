---
title: "Spectral Density"
description: "Explains spectral density as the density of a spectral measure, density of states, resolvent discontinuity, and QFT spectral function, with emphasis on continuum limits and Källén–Lehmann representations."
sidebar:
  label: "Spectral Density"
  order: 8
level: Graduate
status: "Polished draft"
source: "Standard spectral-theory and QFT references, including Reed–Simon, Teschl, Moretti, Weinberg, Srednicki, Schwartz, Zinn-Justin, and treatments of Källén–Lehmann representations, density of states, and spectral functions."
topics:
  - spectral density
  - spectral measure
  - density of states
  - resolvent
  - Källén–Lehmann representation
  - spectral function
  - continuum spectrum
  - thresholds
  - sum rules
  - finite-volume limits
canonicalTopics:
  - spectral-density
  - spectral-measure
  - density-of-states
  - resolvent
  - kallen-lehmann-representation
  - spectral-function
  - continuous-spectrum
  - threshold
  - sum-rule
  - finite-volume-limit
researchStatus:
  established:
    - "Spectral density is the Radon–Nikodym density of a spectral measure when the absolutely continuous part of the spectrum is resolved with respect to a reference measure."
  active:
    - "Extracting real-time spectral densities from Euclidean or lattice data is an ill-conditioned inverse problem and depends on priors, regulators, resolution, and analytic continuation methods."
---

## Summary

A spectral density is what a list of eigenvalues becomes when the spectrum is continuous, or when a finite-volume spectrum is viewed at coarse resolution. In finite volume one may write a delta-comb density

$$
\rho_L(\lambda)=\sum_n\delta(\lambda-\lambda_n).
$$

In an infinite-volume or continuum limit, this often approaches a smoother object:

$$
d\mu(\lambda)=\rho(\lambda)\,d\lambda.
$$

The density $\rho(\lambda)$ is not an extra postulate. It is the density of a spectral measure with respect to a chosen reference measure, usually Lebesgue measure. The spectral theorem gives the measure; absolute continuity gives the density.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Diagram showing finite-volume spectral delta functions becoming a continuum spectral density, which can be recovered as a boundary value of the resolvent and used in QFT spectral representations.](/figures/math-toolkit/spectral-density-continuum-limit.svg)

<figcaption>

Finite-volume spectra often appear as sums of delta functions. In a continuum or thermodynamic limit, a spectral measure may acquire an absolutely continuous part with density $\rho(\lambda)$. The same density is encoded in the imaginary part or discontinuity of a resolvent, and in QFT it appears as the pole-plus-continuum data of two-point functions.

</figcaption>
</figure>

There are several related uses of the phrase “spectral density” in QFT:

$$
\text{spectral density of an operator},
\qquad
\text{density of states},
\qquad
\text{spectral function of a correlator}.
$$

They are not identical, but they share a common structure: a positive or signed measure becomes a density after choosing a variable and a normalization.

## Prerequisites

You should know the spectral theorem, compact operators, distributions, delta functions, and principal values from [Spectral Theorem](/math-toolkit/functional-analysis-spectral-theory/spectral-theorem/), [Compact Operators](/math-toolkit/functional-analysis-spectral-theory/compact-operators/), [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/), and [Principal Values](/math-toolkit/analysis-distributions-fourier/principal-values/). The resolvent formulas use [Trace-Class and Hilbert–Schmidt Operators](/math-toolkit/functional-analysis-spectral-theory/trace-class-and-hilbert-schmidt-operators/) for traceability issues. QFT examples connect to [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/) and [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/).

## Core idea

Let $A$ be a self-adjoint operator with spectral measure $E_A$. For a vector $\psi\in\mathcal H$, the scalar spectral measure is

$$
\mu_\psi(\Delta)=\langle\psi,E_A(\Delta)\psi\rangle,
$$

where $\Delta\subseteq\mathbb R$ is a Borel set. If $\|\psi\|=1$, then $\mu_\psi$ is a probability measure. It tells us how the state $\psi$ is distributed over the spectral values of $A$.

If this measure is absolutely continuous with respect to $d\lambda$ on some region, then there is a function $\rho_\psi(\lambda)$ such that

$$
d\mu_\psi(\lambda)=\rho_\psi(\lambda)\,d\lambda.
$$

This $\rho_\psi$ is a spectral density for the pair $(A,\psi)$.

For a pair of vectors $\psi,\phi$, one similarly has a complex measure

$$
\mu_{\psi,\phi}(\Delta)=\langle\psi,E_A(\Delta)\phi\rangle,
$$

and, when it is absolutely continuous,

$$
d\mu_{\psi,\phi}(\lambda)=\rho_{\psi,\phi}(\lambda)\,d\lambda.
$$

Matrix elements of functions of $A$ become ordinary integrals:

$$
\langle\psi,f(A)\phi\rangle
=\int f(\lambda)\,d\mu_{\psi,\phi}(\lambda)
=\int f(\lambda)\rho_{\psi,\phi}(\lambda)\,d\lambda.
$$

This is the clean version of “insert a complete set of states” when the spectrum is continuous. The complete set is not a literal basis of normalizable eigenvectors. It is a spectral measure, and the spectral density is the derivative of its continuous part.

## Discrete, continuous, and mixed spectra

For a finite-dimensional Hermitian matrix with normalized eigenvectors $e_n$ and eigenvalues $\lambda_n$, the spectral measure of a normalized vector $\psi$ is

$$
\mu_\psi=\sum_n |\langle e_n,\psi\rangle|^2\delta_{\lambda_n}.
$$

In density notation,

$$
\rho_\psi(\lambda)=\sum_n |\langle e_n,\psi\rangle|^2\delta(\lambda-\lambda_n).
$$

This is not a smooth function. It is a distribution: a weighted sum of delta functions.

For a purely absolutely continuous spectrum, the same measure may be represented by an honest density. The free momentum operator on $L^2(\mathbb R)$ is the standard example. In the momentum representation,

$$
(P\widehat\psi)(p)=p\widehat\psi(p),
$$

and the spectral measure is

$$
\mu_\psi(\Delta)=\int_\Delta |\widehat\psi(p)|^2\,dp.
$$

So the spectral density is

$$
\rho_\psi(p)=|\widehat\psi(p)|^2.
$$

A general spectral measure can have several pieces:

$$
d\mu=d\mu_{\mathrm{pp}}+d\mu_{\mathrm{ac}}+d\mu_{\mathrm{sc}}.
$$

Here $\mathrm{pp}$ denotes pure point spectrum, $\mathrm{ac}$ denotes absolutely continuous spectrum, and $\mathrm{sc}$ denotes singular continuous spectrum. Most elementary QFT uses point and absolutely continuous parts. Singular continuous spectrum is rare in textbook QFT but appears in spectral theory, quasiperiodic systems, and some fractal-like models.

## Density of states

The density of states counts spectral values rather than the spectral content of a particular vector. In finite volume, if an operator $A_L$ has eigenvalues $\lambda_n(L)$, one writes

$$
\rho_L(\lambda)=\sum_n\delta(\lambda-\lambda_n(L)).
$$

The integrated density of states is

$$
N_L(\Lambda)=\#\{n:\lambda_n(L)\le\Lambda\}
=\int_{-\infty}^{\Lambda}\rho_L(\lambda)\,d\lambda.
$$

In a box of volume $V_L$, one often wants the density per unit volume:

$$
\rho(\lambda)=\lim_{L\to\infty}\frac1{V_L}\rho_L(\lambda),
$$

understood weakly, meaning after integrating against smooth test functions.

This weak viewpoint matters. The finite-volume object is a forest of delta functions. It rarely converges pointwise to a smooth curve. It converges only after smoothing, binning, testing, or taking an integrated limit.

For the free Laplacian on $\mathbb R^d$, the density of states per unit volume for

$$
A=-\Delta
$$

is obtained from momentum space:

$$
\frac{N(\Lambda)}{V}=\int_{p^2\le\Lambda}\frac{d^dp}{(2\pi)^d}.
$$

Therefore

$$
\frac{N(\Lambda)}{V}
=\frac{\Omega_d}{(2\pi)^d}\Lambda^{d/2},
$$

where

$$
\Omega_d=\frac{\pi^{d/2}}{\Gamma(d/2+1)}
$$

is the volume of the unit ball in $\mathbb R^d$. Differentiating gives

$$
\rho(\lambda)
=\frac{S_{d-1}}{2(2\pi)^d}\lambda^{d/2-1},
\qquad
\lambda>0,
$$

where $S_{d-1}=d\,\Omega_d=2\pi^{d/2}/\Gamma(d/2)$ is the area of the unit sphere.

## Spectral density from the resolvent

The resolvent of a self-adjoint operator $A$ is

$$
R_A(z)=(A-z)^{-1},
\qquad
z\notin\sigma(A).
$$

For a vector $\psi$,

$$
\langle\psi,R_A(z)\psi\rangle
=\int_\mathbb R\frac{d\mu_\psi(\lambda')}{\lambda'-z}.
$$

This is a Stieltjes transform of the spectral measure. The measure can be recovered from boundary values of the transform. With the convention above,

$$
\rho_\psi(\lambda)
=\frac1\pi\lim_{\epsilon\downarrow0}
\operatorname{Im}\,
\langle\psi,(A-\lambda-i\epsilon)^{-1}\psi\rangle
$$

at points where the absolutely continuous density exists.

The sign comes from the distribution identity

$$
\frac1{x-i0}=\operatorname{PV}\frac1x+i\pi\delta(x).
$$

Equivalently, the density is a discontinuity across the cut:

$$
\rho_\psi(\lambda)
=\frac{1}{2\pi i}
\lim_{\epsilon\downarrow0}
\left[
\langle\psi,(A-\lambda-i\epsilon)^{-1}\psi\rangle
-
\langle\psi,(A-\lambda+i\epsilon)^{-1}\psi\rangle
\right].
$$

This formula is the analytic ancestor of many physics slogans:

$$
\text{density of states} = \text{imaginary part of a Green function}.
$$

One must still choose the exact Green function and sign convention. Some authors define the resolvent as $(z-A)^{-1}$ instead of $(A-z)^{-1}$, which flips the sign in the imaginary-part formula.

## Trace densities and volume normalization

For a finite-dimensional operator,

$$
\operatorname{Tr}\delta(\lambda-A)=\sum_n\delta(\lambda-\lambda_n).
$$

In infinite dimensions, this trace is usually divergent. In finite volume it may be meaningful as a distribution, while in infinite volume one often divides by volume:

$$
\rho(\lambda)=\lim_{V\to\infty}\frac1V\operatorname{Tr}\delta(\lambda-A_V).
$$

The same caution applies to resolvents:

$$
\rho(\lambda)
=\frac1\pi\lim_{\epsilon\downarrow0}\frac1V
\operatorname{Im}\operatorname{Tr}(A_V-\lambda-i\epsilon)^{-1}.
$$

The trace may not exist without a finite box, smearing, heat-kernel damping, or trace-class difference. The density of states is often a trace density, not an ordinary trace. That single word “density” is carrying a lot of analytic furniture.

For local differential operators, one often studies the diagonal heat kernel

$$
K(s;x,x)
$$

and its spatial integral. In homogeneous infinite volume, the global heat trace diverges like the volume, but the heat trace per volume can be finite:

$$
\frac1V\operatorname{Tr}e^{-sA}
=\int e^{-s\lambda}\rho(\lambda)\,d\lambda.
$$

This is a Laplace transform of the spectral density.

## Spectral functions in QFT

In QFT, “spectral density” often means the spectral function appearing in a two-point function. Let $O(x)$ be a scalar local operator. A Wightman two-point function has an insertion of energy-momentum eigenstates:

$$
\langle0|O(x)O(0)|0\rangle.
$$

Translation invariance and positivity imply a spectral representation supported on future-directed momenta. For a Lorentz-invariant scalar operator in the vacuum, the invariant spectral data can be written as a nonnegative measure in $\mu^2$:

$$
\langle0|O(x)O(0)|0\rangle
=\int_0^\infty d\mu^2\,\rho_O(\mu^2)\,\Delta_+(x;\mu^2),
$$

up to conventional normalizations. Here $\Delta_+(x;\mu^2)$ is the free positive-frequency two-point function of mass $\mu$.

For the time-ordered two-point function, the corresponding momentum-space representation is

$$
G_F(p)=\int_0^\infty d\mu^2\,
\frac{i\rho_O(\mu^2)}{p^2-\mu^2+i\epsilon}
+\text{contact terms or subtractions},
$$

using the mostly-minus metric convention.

For an elementary scalar field with a stable one-particle state, the spectral density has the schematic form

$$
\rho_\phi(\mu^2)
=Z\delta(\mu^2-m^2)+\rho_{\mathrm{cont}}(\mu^2).
$$

The delta function is the stable particle pole. The continuum begins at multiparticle thresholds, such as

$$
\mu^2\ge (2m)^2
$$

for a two-particle threshold of identical mass-$m$ particles.

This is the Källén–Lehmann lesson: a propagator is not merely a pole. In an interacting theory it contains a positive spectral distribution describing the overlap of the local operator with all states carrying the same quantum numbers.

## Spectral density versus propagator

A propagator is usually a Green function. A spectral density is its discontinuity or imaginary part across a physical cut. In a simple scalar representation,

$$
G_F(p)=\int_0^\infty d\mu^2\,
\frac{i\rho(\mu^2)}{p^2-\mu^2+i\epsilon}.
$$

The pole or cut structure of $G_F$ encodes $\rho$. For $s=p^2$, the discontinuity across the real axis is schematically

$$
\operatorname{Disc}G_F(s)
=G_F(s+i0)-G_F(s-i0)
=2\pi\rho(s)
$$

up to the $i$ conventions used in defining $G_F$.

A retarded Green function is often cleaner for real-time response. If

$$
G_R(t)=-i\theta(t)\langle[O(t),O(0)]\rangle,
$$

then the real-time spectral function is commonly normalized as

$$
\rho(\omega)=-2\operatorname{Im}G_R(\omega)
$$

or with the opposite sign depending on Fourier conventions. The physical content is the same: the spectral function measures dissipative response and the distribution of excitation energies.

The safe habit is to state the convention:

$$
\rho=\text{specified imaginary part or specified discontinuity}.
$$

Never quote a sign for $\rho$ without knowing whether the source uses $e^{-i\omega t}$ or $e^{+i\omega t}$, mostly-minus or mostly-plus metric, and $G_R=-i\theta(t)[\cdot,\cdot]$ or $+i\theta(t)[\cdot,\cdot]$.

## Positivity and sum rules

For a Hermitian operator $O$, the vacuum spectral density in a unitary theory is nonnegative in the physical channel:

$$
\rho_O(\mu^2)\ge0.
$$

This positivity follows from inserting a complete set of states. Schematically,

$$
\rho_O\sim\sum_n|
\langle0|O|n\rangle|^2\delta(\text{invariant mass of }n-\mu).
$$

This is one of the most powerful facts about spectral representations. It constrains propagators, proves inequalities, and helps connect analyticity with unitarity.

Sum rules arise when asymptotic behavior, commutators, Ward identities, or operator-product expansions fix moments of the spectral density. A typical moment has the form

$$
\int d\lambda\,\lambda^k\rho(\lambda),
$$

possibly after subtractions. In QFT, such moments are often divergent unless regulated or combined in a convergent difference. The meaningful sum rule includes its convergence and subtraction assumptions.

## Finite-volume spectra and the continuum limit

A finite box converts momenta into discrete values. For a scalar particle in a periodic box of side $L$,

$$
\mathbf p=\frac{2\pi}{L}\mathbf n,
\qquad
\mathbf n\in\mathbb Z^d.
$$

Sums become integrals as

$$
\frac1{L^d}\sum_{\mathbf p}
\longrightarrow
\int\frac{d^dp}{(2\pi)^d}.
$$

Equivalently, the finite-volume density of momentum states per unit volume approaches

$$
\frac{d^dp}{(2\pi)^d}.
$$

For multiparticle states, the continuum limit is more intricate. Energies depend on several momenta, interactions shift levels, and thresholds appear. Still, the conceptual structure is the same: finite-volume delta functions condense into continuum spectral weight.

This is why finite-volume spectroscopy is useful in lattice field theory. Discrete energy levels are not the final infinite-volume spectral density, but they encode it. Extracting scattering amplitudes or spectral functions from finite-volume data requires additional analytic machinery.

## Euclidean correlators and inverse problems

Euclidean correlation functions are often integral transforms of real-time spectral densities. A zero-temperature schematic form is

$$
G_E(\tau)=\int_0^\infty d\omega\,\rho(\omega)e^{-\omega\tau},
\qquad
\tau>0.
$$

At finite temperature, the kernel changes. For bosonic correlators one commonly encounters

$$
G_E(\tau)=\int_0^\infty d\omega\,\rho(\omega)
\frac{\cosh\big(\omega(\tau-\beta/2)\big)}{\sinh(\beta\omega/2)}.
$$

The forward map

$$
\rho(\omega)\mapsto G_E(\tau)
$$

smooths information. The inverse map is ill-conditioned. Many different fine-grained spectral densities can produce nearly indistinguishable Euclidean data at finite precision. This is why spectral reconstruction from Euclidean or lattice correlators is difficult and depends on priors, resolution, Bayesian choices, analytic ansätze, or other constraints.

This is not a failure of QFT. It is the mathematical character of analytic continuation and inverse Laplace transforms wearing a lab coat.

## Thresholds and branch cuts

A discrete stable particle gives a delta function in the spectral density and a pole in the propagator. A continuum of multiparticle states gives a branch cut.

For example, suppose an operator can create two particles of masses $m_1$ and $m_2$. The invariant mass threshold is

$$
\mu_{\mathrm{thr}}=m_1+m_2.
$$

The spectral density can have support for

$$
\mu^2\ge (m_1+m_2)^2.
$$

Near threshold, phase space controls the leading behavior, modified by angular momentum, interactions, and bound-state effects. In perturbation theory, the same threshold appears as a branch point of loop integrals.

This is one reason spectral density is a bridge between analysis and physics. The analytic structure of a Green function knows about the state space: poles for stable states, cuts for continua, and discontinuities governed by phase space and matrix elements.

## Common pitfalls

**Treating a spectral density as automatically smooth.** A spectral density may contain delta functions, step functions, singular distributions, or a smooth absolutely continuous part. Say which part you mean.

**Confusing density of states with a correlator spectral function.** Density of states counts levels. A correlator spectral function weights states by matrix elements of an operator.

**Forgetting volume normalization.** In infinite volume, global traces usually diverge. The useful object is often a density per unit volume.

**Ignoring the measure variable.** A density in $\lambda$ is not the same as a density in $\omega$ or $\mu^2$. Jacobians matter:

$$
\rho_\omega(\omega)d\omega=\rho_\lambda(\lambda)d\lambda.
$$

**Losing signs in imaginary-part formulas.** The sign depends on whether the resolvent is $(A-z)^{-1}$ or $(z-A)^{-1}$ and on Fourier conventions.

**Assuming Euclidean data determines a sharp spectral function.** Analytic continuation from noisy or finite Euclidean data is ill-conditioned. Positivity and sum rules help, but they do not make the inverse problem magically unique.

**Dropping contact terms.** Momentum-space correlators can contain polynomial contact terms that do not contribute to the discontinuity but do affect local expressions and subtractions.

## Worked examples

### A finite diagonal operator

Let $A$ have eigenvalues $\lambda_1,\dots,\lambda_N$ and orthonormal eigenvectors $e_n$. For a normalized state

$$
\psi=\sum_nc_ne_n,
$$

one has

$$
\rho_\psi(\lambda)=\sum_{n=1}^N|c_n|^2\delta(\lambda-\lambda_n).
$$

For a test function $f$,

$$
\int f(\lambda)\rho_\psi(\lambda)\,d\lambda
=\sum_n|c_n|^2f(\lambda_n)
=\langle\psi,f(A)\psi\rangle.
$$

The delta functions are not decorative. They are exactly what makes the functional calculus work in density notation.

### Free-particle density of states

For $A=-\Delta$ on $\mathbb R^d$, the spectral parameter is

$$
\lambda=p^2.
$$

Per unit volume,

$$
\rho(\lambda)=\int\frac{d^dp}{(2\pi)^d}\delta(\lambda-p^2).
$$

Using spherical coordinates,

$$
\rho(\lambda)
=\frac{S_{d-1}}{(2\pi)^d}
\int_0^\infty p^{d-1}\delta(\lambda-p^2)\,dp.
$$

Since

$$
\delta(\lambda-p^2)=\frac{1}{2\sqrt\lambda}\delta(p-\sqrt\lambda)
$$

for $p\ge0$ and $\lambda>0$, one gets

$$
\rho(\lambda)
=\frac{S_{d-1}}{2(2\pi)^d}\lambda^{d/2-1}.
$$

This formula is the continuum replacement for counting discrete momentum modes in a box.

### A one-particle pole plus continuum

Suppose a scalar operator overlaps with a stable one-particle state of mass $m$ and also with multiparticle states. Then

$$
\rho(\mu^2)=Z\delta(\mu^2-m^2)+\rho_{\mathrm{cont}}(\mu^2).
$$

The time-ordered propagator contains

$$
G_F(p)=\frac{iZ}{p^2-m^2+i\epsilon}
+
\int_{\mu^2_{\mathrm{thr}}}^{\infty}d\mu^2\,
\frac{i\rho_{\mathrm{cont}}(\mu^2)}{p^2-\mu^2+i\epsilon}
+\text{subtractions}.
$$

The pole is the stable particle. The continuum integral is the branch cut from multiparticle states.

## Exercises

### Exercise 1: Recover a finite spectral measure

Let $A$ be a Hermitian matrix with eigenvalues $\lambda_n$ and orthonormal eigenvectors $e_n$. Show that

$$
\rho_\psi(\lambda)=\sum_n|\langle e_n,\psi\rangle|^2\delta(\lambda-\lambda_n)
$$

satisfies

$$
\langle\psi,f(A)\psi\rangle
=\int f(\lambda)\rho_\psi(\lambda)\,d\lambda.
$$

<details><summary><strong>Solution</strong></summary>

By the finite-dimensional spectral theorem,

$$
f(A)=\sum_nf(\lambda_n)|e_n\rangle\langle e_n|.
$$

Therefore

$$
\langle\psi,f(A)\psi\rangle
=\sum_nf(\lambda_n)|\langle e_n,\psi\rangle|^2.
$$

On the other hand,

$$
\int f(\lambda)\rho_\psi(\lambda)\,d\lambda
=\sum_n|\langle e_n,\psi\rangle|^2
\int f(\lambda)\delta(\lambda-\lambda_n)\,d\lambda,
$$

which equals the same sum.

</details>

### Exercise 2: Imaginary part of the resolvent

For a finite diagonal operator with eigenvalues $\lambda_n$, show that

$$
\frac1\pi\lim_{\epsilon\downarrow0}\operatorname{Im}\sum_n\frac{w_n}{\lambda_n-\lambda-i\epsilon}
=\sum_nw_n\delta(\lambda-\lambda_n)
$$

for nonnegative weights $w_n$.

<details><summary><strong>Solution</strong></summary>

Use

$$
\frac1{x-i0}=\operatorname{PV}\frac1x+i\pi\delta(x).
$$

With $x=\lambda_n-\lambda$, one has

$$
\operatorname{Im}\frac1{\lambda_n-\lambda-i0}
=\pi\delta(\lambda_n-\lambda).
$$

Since $\delta(\lambda_n-\lambda)=\delta(\lambda-\lambda_n)$,

$$
\frac1\pi\operatorname{Im}\sum_n\frac{w_n}{\lambda_n-\lambda-i0}
=\sum_nw_n\delta(\lambda-\lambda_n).
$$

</details>

### Exercise 3: Free density of states in three dimensions

Use

$$
\rho(\lambda)=\int\frac{d^3p}{(2\pi)^3}\delta(\lambda-p^2)
$$

to compute the density of states per unit volume for $-
abla^2$ on $\mathbb R^3$.

<details><summary><strong>Solution</strong></summary>

In spherical coordinates,

$$
\rho(\lambda)
=\frac{4\pi}{(2\pi)^3}\int_0^\infty p^2\delta(\lambda-p^2)\,dp.
$$

For $\lambda>0$,

$$
\delta(\lambda-p^2)=\frac1{2\sqrt\lambda}\delta(p-\sqrt\lambda).
$$

Thus

$$
\int_0^\infty p^2\delta(\lambda-p^2)\,dp
=\frac{\lambda}{2\sqrt\lambda}
=\frac{\sqrt\lambda}{2}.
$$

Therefore

$$
\rho(\lambda)
=\frac{4\pi}{(2\pi)^3}\frac{\sqrt\lambda}{2}
=\frac{\sqrt\lambda}{4\pi^2}.
$$

</details>

### Exercise 4: Jacobian for changing spectral variables

Suppose a spectral density is given in the energy variable $\omega>0$ by $\rho_\omega(\omega)$. Let $s=\omega^2$. Find the density $\rho_s(s)$ such that

$$
\rho_\omega(\omega)d\omega=\rho_s(s)ds.
$$

<details><summary><strong>Solution</strong></summary>

Since

$$
s=\omega^2,
\qquad
 ds=2\omega\,d\omega,
$$

one has

$$
d\omega=\frac{ds}{2\sqrt s}.
$$

Therefore

$$
\rho_s(s)=\frac{\rho_\omega(\sqrt s)}{2\sqrt s}.
$$

Densities depend on the variable. Forgetting this Jacobian is a classic source of wrong factors near thresholds.

</details>

### Exercise 5: Pole contribution to the propagator

If

$$
\rho(\mu^2)=Z\delta(\mu^2-m^2),
$$

show that the spectral representation gives the Feynman pole

$$
G_F(p)=\frac{iZ}{p^2-m^2+i\epsilon}.
$$

<details><summary><strong>Solution</strong></summary>

Insert the spectral density into

$$
G_F(p)=\int_0^\infty d\mu^2\,
\frac{i\rho(\mu^2)}{p^2-\mu^2+i\epsilon}.
$$

Then

$$
G_F(p)=\int_0^\infty d\mu^2\,
\frac{iZ\delta(\mu^2-m^2)}{p^2-\mu^2+i\epsilon}
=\frac{iZ}{p^2-m^2+i\epsilon}.
$$

</details>

## References

- M. Reed and B. Simon, *Methods of Modern Mathematical Physics I: Functional Analysis* and *III: Scattering Theory*. Standard references for spectral measures, resolvents, and absolutely continuous spectrum.
- G. Teschl, *Mathematical Methods in Quantum Mechanics*. Useful for spectral measures, resolvents, and density of states.
- V. Moretti, *Spectral Theory and Quantum Mechanics*. Physics-friendly account of spectral decompositions and Green functions.
- S. Weinberg, *The Quantum Theory of Fields, Volume I*. Standard source for spectral representations and particle-state decompositions.
- M. Srednicki, *Quantum Field Theory*. Useful for the Lehmann–Källén form of the exact propagator and related QFT spectral ideas.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for spectral decomposition, unitarity, analytic structure, and propagators.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Useful for Euclidean field theory, correlation functions, and spectral/renormalization viewpoints.
- A. Altland and B. Simons, *Condensed Matter Field Theory*. Useful for response functions and analytic structure of correlators.

## Version history

- 2026-06-25: Initial polished draft.
