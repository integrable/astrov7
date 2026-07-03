---
title: "Semiclassical Expansion"
description: "Stationary phase, saddle points, fluctuation operators, one-loop determinants, zero modes, and the relation between semiclassical methods and loop counting in QFT."
sidebar:
  label: "Semiclassical Expansion"
  order: 8
---

## Summary

The semiclassical expansion is the systematic expansion of a path integral around classical solutions. Restore $\hbar$ temporarily and write a Lorentzian scalar functional integral in the form

$$
Z[J]=\int\mathcal D\phi\,
\exp\left\{\frac{i}{\hbar}\left(S[\phi]+\int d^dx\,J\phi\right)\right\}.
$$

When the phase oscillates rapidly, the dominant contributions come from configurations $\phi_{\rm cl}$ satisfying the stationary equation

$$
\boxed{
\left.\frac{\delta S}{\delta\phi(x)}\right|_{\phi_{\rm cl}}+J(x)=0.
}
$$

Expanding

$$
\phi=\phi_{\rm cl}+\eta
$$

gives

$$
S[\phi]+\int J\phi
=S[\phi_{\rm cl}]+\int J\phi_{\rm cl}
+\frac12\int d^dx\,d^dy\,\eta(x)K(x,y)\eta(y)
+S_{\rm int}[\eta],
$$

where

$$
\boxed{
K(x,y)=\left.\frac{\delta^2 S}{\delta\phi(x)\delta\phi(y)}\right|_{\phi_{\rm cl}}.
}
$$

The Gaussian integral over $\eta$ gives the one-loop determinant,

$$
\boxed{
Z[J]\sim
\exp\left\{\frac{i}{\hbar}\left(S[\phi_{\rm cl}]+\int J\phi_{\rm cl}\right)\right\}
\left[\det(K+i\epsilon)\right]^{-1/2}
\bigl(1+\text{higher loops}\bigr),
}
$$

up to normalization, phases, zero-mode factors, and regularization. In Euclidean signature the corresponding formula is cleaner:

$$
\boxed{
Z_E[J]\sim
\exp\left[-\frac1{\hbar}\left(S_E[\phi_{\rm cl}]-\int J\phi_{\rm cl}\right)\right]
\left[\det K_E\right]^{-1/2}
\bigl(1+\text{higher loops}\bigr).
}
$$

Tree level is classical physics. One loop is the Gaussian fluctuation determinant. Higher loops are perturbative interactions among the fluctuations. Coleman makes this link explicit by identifying the semiclassical expansion with loop counting: a connected diagram with $L$ loops carries one more power of $\hbar$ than a connected diagram with $L-1$ loops, once $Z$ is written as an exponential of connected diagrams (Coleman 2019, §§32.1–32.2). Zee gives the same physics in the quantum-mechanical path integral through the stationary-phase limit $\hbar\to0$ (Zee 2010, ch. I.2).

## Prerequisites

You should know [Finite-Dimensional Gaussians](/foundations/path-integral-formalism/finite-dimensional-gaussians/), [Quantum-Mechanical Path Integral](/foundations/path-integral-formalism/quantum-mechanical-path-integral/), [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/), [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/), [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/), and [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/).

## Core idea

A path integral is a sum over histories. In the semiclassical limit, most histories cancel by rapidly oscillating phases. The histories that survive are the stationary points of the action, and the first quantum correction is the Gaussian integral over small fluctuations around them.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Semiclassical expansion map from saddle point to one-loop determinant and higher loops](/figures/foundations/semiclassical-expansion-map.svg)

<figcaption>

The semiclassical expansion begins with a stationary configuration $\phi_{\rm cl}$, expands $\phi=\phi_{\rm cl}+\eta$, and organizes the result into the classical action, a Gaussian fluctuation determinant, and higher-loop interactions among $\eta$. Zero modes and negative modes require extra care.

</figcaption>
</figure>

For one variable, this is stationary phase. For infinitely many field variables, this is the loop expansion. The useful slogan is:

```txt
classical solution
  + quadratic fluctuations
  + interactions of fluctuations
  = tree + one loop + higher loops
```

The slogan is accurate only after three qualifications.

First, the quadratic operator must be regularized before its determinant is meaningful. Second, zero modes must be removed from the determinant and replaced by collective-coordinate integrals. Third, in gauge theories one must first remove gauge redundancy; otherwise the quadratic operator has gauge zero modes everywhere.

Those qualifications are not small print. They are where instantons, anomalies, ghosts, and moduli spaces eventually enter.

## Finite-dimensional stationary phase

Start with an ordinary oscillatory integral

$$
I(\hbar)=\int_{\mathbb R^N}d^Nx\;a(x)e^{if(x)/\hbar}.
$$

Suppose $x_s$ is an isolated nondegenerate stationary point:

$$
\partial_i f(x_s)=0,
\qquad
H_{ij}=\partial_i\partial_j f(x_s),
\qquad
\det H\ne0.
$$

Expand

$$
f(x_s+\xi)=f(x_s)+\frac12\xi^iH_{ij}\xi^j+O(\xi^3).
$$

The leading approximation is

$$
I(\hbar)
\sim
a(x_s)e^{if(x_s)/\hbar}
\int d^N\xi\,
\exp\left(\frac{i}{2\hbar}\xi^iH_{ij}\xi^j\right).
$$

After choosing a contour or an $i\epsilon$ prescription, the Gaussian contributes

$$
\boxed{
I(\hbar)
\sim
(2\pi\hbar)^{N/2}
\frac{a(x_s)e^{if(x_s)/\hbar}e^{i\pi\sigma/4}}
{|\det H|^{1/2}},
}
$$

where $\sigma$ is the number of positive eigenvalues minus the number of negative eigenvalues of $H$. In Euclidean steepest descent, where

$$
I_E(\hbar)=\int d^Nx\;a(x)e^{-f(x)/\hbar},
$$

and $x_s$ is a local minimum, the phase factor disappears:

$$
\boxed{
I_E(\hbar)
\sim
(2\pi\hbar)^{N/2}
\frac{a(x_s)e^{-f(x_s)/\hbar}}
{(\det H)^{1/2}}.
}
$$

The field-theory formula is the same statement with $x^i$ replaced by $\phi(x)$ and $H_{ij}$ replaced by a differential operator.

## Saddle points in field theory

For a scalar theory with source,

$$
S_J[\phi]=S[\phi]+\int d^dx\,J(x)\phi(x),
$$

the saddle equation is

$$
\boxed{
\frac{\delta S[\phi]}{\delta\phi(x)}+J(x)=0.
}
$$

When $J=0$, this is just the classical equation of motion. When $J\ne0$, the saddle is the classical solution in the presence of an external source.

For example, in a scalar theory

$$
S[\phi]=\int d^dx\left[\frac12\partial_\mu\phi\partial^\mu\phi-V(\phi)\right],
$$

the saddle equation is

$$
\boxed{
\Box\phi_{\rm cl}+V'(\phi_{\rm cl})=J
}
$$

with qft.org's mostly-minus convention. The sign comes from

$$
\delta S=\int d^dx\,[-\Box\phi-V'(\phi)]\delta\phi
$$

up to boundary terms, so the equation $\delta S+\int J\delta\phi=0$ gives $\Box\phi+V'(\phi)=J$.

Now write

$$
\phi=\phi_{\rm cl}+\eta.
$$

The linear term in $\eta$ vanishes by the saddle equation. The quadratic term is

$$
\frac12\int d^dx\,d^dy\,\eta(x)K(x,y)\eta(y),
$$

with

$$
K(x,y)=\left.\frac{\delta^2S_J}{\delta\phi(x)\delta\phi(y)}\right|_{\phi_{\rm cl}}
=\left.\frac{\delta^2S}{\delta\phi(x)\delta\phi(y)}\right|_{\phi_{\rm cl}}.
$$

The source does not contribute to $K$ because it is linear in $\phi$.

For the scalar example,

$$
\boxed{
K(x,y)=\left[-\Box-V''(\phi_{\rm cl}(x))\right]\delta^{(d)}(x-y)
}
$$

as a Lorentzian quadratic kernel. In Euclidean signature,

$$
\boxed{
K_E(x,y)=\left[-\partial_E^2+V''(\phi_{\rm cl}(x))\right]\delta^{(d)}(x-y).
}
$$

This Euclidean operator is the one whose spectrum is usually easiest to interpret.

## One-loop determinant

Ignore the higher powers of $\eta$ for the moment. The Gaussian fluctuation integral gives

$$
\int\mathcal D\eta\,
\exp\left[\frac{i}{2\hbar}\int\eta K\eta\right]
\propto
[\det(K+i\epsilon)]^{-1/2}.
$$

Equivalently,

$$
[\det K]^{-1/2}
=\exp\left[-\frac12\operatorname{Tr}\log K\right].
$$

This is why one-loop calculations so often contain traces of logarithms.

For an effective action, the common schematic result is

$$
\boxed{
\Gamma[\phi]
=S[\phi]+\frac{i\hbar}{2}\operatorname{Tr}\log S^{(2)}[\phi]+O(\hbar^2)
}
$$

in Lorentzian signature, and

$$
\boxed{
\Gamma_E[\phi]
=S_E[\phi]+\frac{\hbar}{2}\operatorname{Tr}\log S_E^{(2)}[\phi]+O(\hbar^2)
}
$$

in Euclidean signature. Here $S^{(2)}$ means the second functional derivative of the action around the background field. Constants independent of the background are usually dropped when computing correlation functions or effective potentials, but they matter for absolute partition functions and vacuum energies.

Fermions contribute with the opposite determinant structure. A quadratic Grassmann integral gives $\det D$ rather than $(\det K)^{-1/2}$, so fermion fluctuations contribute schematically

$$
\Gamma_E^{(1),\rm fermion}=-\hbar\operatorname{Tr}\log D
$$

to the Euclidean effective action, up to conventional factors and reality conditions. Majorana fields give Pfaffians or square roots of determinants.

## Loop counting and powers of ℏ

Restore $\hbar$ in the path integral:

$$
Z[J]=\int\mathcal D\phi\,e^{iS_J[\phi]/\hbar}.
$$

A propagator comes from inverting a quadratic term multiplied by $1/\hbar$, so each internal line contributes a factor of $\hbar$. A vertex comes from expanding $e^{iS_{\rm int}/\hbar}$, so each vertex contributes a factor of $1/\hbar$.

For a connected graph with $I$ internal lines and $V$ vertices,

$$
G_c\propto \hbar^{I-V}.
$$

The number of loops is

$$
\boxed{
L=I-V+1.
}
$$

Therefore

$$
G_c\propto \hbar^{L-1}.
$$

Since connected diagrams appear in the exponent, it is often more natural to define

$$
Z[J]=\exp\left(\frac{i}{\hbar}W[J]\right).
$$

Then

$$
\boxed{
W[J]=W_{\rm tree}[J]+\hbar W_{1\text{-loop}}[J]+\hbar^2W_{2\text{-loop}}[J]+\cdots.
}
$$

The same expansion holds for the effective action:

$$
\boxed{
\Gamma[\phi]=S[\phi]+\hbar\Gamma_1[\phi]+\hbar^2\Gamma_2[\phi]+\cdots.
}
$$

This is the precise sense in which the loop expansion is semiclassical. It is not an expansion in a tunable dimensionless constant called $\hbar$; after choosing units, $\hbar=1$. It is a bookkeeping device that becomes reliable when the action is large compared with $\hbar$ or when weak couplings suppress higher-loop graphs.

## Effective potential as a standard application

For a constant background field $\phi$, the Euclidean one-loop effective action reduces to a spacetime volume times an effective potential.

Consider

$$
S_E[\varphi]=\int d^dx\left[\frac12(\partial\varphi)^2+V(\varphi)\right].
$$

Expand around a constant background:

$$
\varphi(x)=\phi+\eta(x).
$$

The quadratic operator is

$$
K_E=-\partial_E^2+V''(\phi).
$$

Then the one-loop contribution to the Euclidean effective potential is formally

$$
\boxed{
V_{\rm eff}^{(1)}(\phi)
=\frac{\hbar}{2}\int\frac{d^dp_E}{(2\pi)^d}
\log\bigl[p_E^2+V''(\phi)\bigr]
}
$$

up to field-independent constants and counterterms.

This formula is not finite as written. It is a compact way of saying:

```txt
choose a regulator
compute the determinant
add allowed counterterms
state the renormalization convention
```

In the Foundations group, this formula is mainly a bridge. The full interpretation of the effective potential belongs to later pages on effective actions, spontaneous symmetry breaking, and renormalization.

## Zero modes and collective coordinates

The determinant formula assumes that $K$ has no zero eigenvalues. But classical solutions often come in continuous families. If

$$
\phi_{\rm cl}(x;a)
$$

depends on a collective coordinate $a$, then

$$
\eta_0(x)=\frac{\partial\phi_{\rm cl}(x;a)}{\partial a}
$$

is a zero mode of the quadratic operator:

$$
K\eta_0=0.
$$

The Gaussian determinant then vanishes or diverges, depending on how one writes it. The cure is not to integrate over that direction as a Gaussian fluctuation. Instead one removes the zero eigenvalue from the determinant and integrates over the collective coordinate:

$$
\boxed{
[\det K]^{-1/2}
\quad\longrightarrow\quad
J_a\,[\det{}'K]^{-1/2}\int da.
}
$$

The prime means that zero modes are omitted. The factor $J_a$ is a Jacobian relating the fluctuation coefficient along the zero-mode direction to the collective coordinate. This is the first place where the semiclassical expansion visibly depends on the path-integral measure.

Common examples include:

```txt
translation zero modes of solitons and instantons
rotation zero modes of internal-symmetry solitons
scale zero modes in classically scale-invariant systems
gauge zero modes before gauge fixing
```

Gauge zero modes are special: they are redundancies, not physical moduli. They are removed by gauge fixing and Faddeev–Popov determinants, not by integrating over new physical collective coordinates.

## Negative modes and instability

In Euclidean signature, a true local minimum has a positive fluctuation operator. If $K_E$ has a negative eigenvalue, the saddle is not an ordinary minimum. This is not automatically a disaster; it tells you what kind of saddle you are using.

A Euclidean bounce describing false-vacuum decay has one negative mode. That negative mode is responsible for the imaginary part of the false-vacuum energy and therefore for a decay rate. A configuration with many negative modes is usually not the leading tunneling saddle.

So the eigenvalue structure of $K_E$ carries physical information:

```txt
positive modes       → ordinary Gaussian fluctuations
zero modes           → collective coordinates or gauge redundancy
one negative mode    → tunneling/decay saddle
many negative modes  → usually not the relevant saddle
```

The determinant alone is never the full story; its spectrum must be interpreted.

## Semiclassical expansion in operator language

The path-integral saddle equation is the classical equation of motion, but this does not mean the path integral has abandoned quantum mechanics.

In operator language, the same approximation says:

```txt
states are concentrated near a classical trajectory or field configuration,
quadratic fluctuations give harmonic oscillators around that background,
higher interactions perturb those oscillators.
```

For a free field around the vacuum, the semiclassical fluctuation modes are precisely the oscillator modes quantized in canonical quantization. Around a nontrivial background, the same logic gives a new spectrum of small oscillations. That is why the page [Linearization and Normal Modes](/foundations/classical-field-theory/linearization-and-normal-modes/) belongs so early in Foundations: semiclassical QFT is just linearization plus quantum Gaussian integration, done carefully.

## What this page is not

This page fixes the architecture of the semiclassical expansion. It does not attempt to fully develop:

```txt
instantons and tunneling amplitudes
false-vacuum decay
soliton quantization
renormalized effective potentials
heat-kernel determinant technology
zeta-function regularization
semiclassical gravity
```

Those topics need their own pages. The foundational lesson here is smaller but deeper: whenever you see a one-loop determinant, a saddle-point equation, or a trace log, you are looking at the Gaussian approximation to a path integral around a classical configuration.

## Common pitfalls

### Thinking saddle means minimum

In Lorentzian signature the saddle is a stationary point of the phase, not a minimum. Euclidean signature turns many useful problems into steepest-descent problems, but even there tunneling saddles can have negative modes.

### Dropping zero modes into the determinant

Zero modes must be treated separately. A determinant with zero eigenvalues is not a small correction; it is a sign that the variables have been chosen incorrectly for the saddle.

### Forgetting the regulator

$\operatorname{Tr}\log K$ is usually divergent. A determinant formula without a regulator and a renormalization prescription is only formal.

### Confusing loop counting with numerical smallness

A one-loop approximation is not automatically accurate. It is controlled by small couplings, large actions, large quantum numbers, or other problem-specific parameters.

### Expanding around the wrong saddle

Perturbation theory around an unstable or physically inappropriate saddle can be mathematically consistent but physically misleading. The chosen saddle encodes the phase of the theory.

### Ignoring gauge redundancy

Gauge-equivalent fluctuations are not distinct physical fluctuations. Gauge theories require gauge fixing, ghosts, or an equivalent method before their determinants are meaningful.

## Relation to other topics

- [Finite-Dimensional Gaussians](/foundations/path-integral-formalism/finite-dimensional-gaussians/) gives the determinant identity used for the one-loop term.
- [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) explains why steepest descent is often cleaner after Wick rotation.
- [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) explains how $W[J]$ and $\Gamma[\phi]$ organize connected and 1PI diagrams.
- [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/) explains why exponentiating connected graphs is natural.
- [Path Integral Measure](/foundations/path-integral-formalism/path-integral-measure/) explains the Jacobians and zero-mode factors suppressed in the schematic determinant formula.
- Later pages on effective actions, instantons, gauge fixing, anomalies, and renormalization will reuse this machinery constantly.

## Research status

- **Established:** Stationary phase, Gaussian fluctuation determinants, loop counting, and one-loop effective actions are standard textbook QFT tools.
- **Active:** Semiclassical expansions with zero modes, gauge redundancies, fermion determinants, resurgence, renormalons, and real-time saddles remain technically active.
- **Speculative:** None at the level of the foundational formalism.

## Exercises

### Exercise 1: One-dimensional stationary phase

Let

$$
I(\hbar)=\int_{-\infty}^{\infty}dx\,a(x)e^{if(x)/\hbar},
$$

where $f'(x_0)=0$ and $f''(x_0)>0$. Keeping only the quadratic term in $f$ and the leading value of $a$, show that

$$
I(\hbar)\sim a(x_0)e^{if(x_0)/\hbar}e^{i\pi/4}
\sqrt{\frac{2\pi\hbar}{f''(x_0)}}.
$$

<details>
<summary><strong>Solution</strong></summary>

Expand

$$
f(x)=f(x_0)+\frac12 f''(x_0)(x-x_0)^2+\cdots,
\qquad
 a(x)=a(x_0)+\cdots.
$$

Then

$$
I(\hbar)\sim a(x_0)e^{if(x_0)/\hbar}
\int_{-\infty}^{\infty}d\xi\,
\exp\left[\frac{i}{2\hbar}f''(x_0)\xi^2\right].
$$

With the usual oscillatory Gaussian prescription,

$$
\int_{-\infty}^{\infty}d\xi\,e^{ia\xi^2/2}
=e^{i\pi/4}\sqrt{\frac{2\pi}{a}}
\qquad(a>0).
$$

Here $a=f''(x_0)/\hbar$, so

$$
I(\hbar)\sim a(x_0)e^{if(x_0)/\hbar}e^{i\pi/4}
\sqrt{\frac{2\pi\hbar}{f''(x_0)}}.
$$

</details>

### Exercise 2: Gaussian fluctuation determinant

Let $K$ be a positive-definite $N\times N$ matrix. Show that

$$
\int d^N\eta\,\exp\left[-\frac1{2\hbar}\eta^TK\eta\right]
=(2\pi\hbar)^{N/2}(\det K)^{-1/2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Diagonalize $K=O^T\Lambda O$, where $O$ is orthogonal and $\Lambda=\operatorname{diag}(\lambda_1,\dots,\lambda_N)$ with $\lambda_i>0$. The measure is unchanged by $\xi=O\eta$. Then

$$
\int d^N\eta\,e^{-\eta^TK\eta/(2\hbar)}
=\prod_{i=1}^N\int d\xi_i\,e^{-\lambda_i\xi_i^2/(2\hbar)}.
$$

Each one-dimensional integral is

$$
\sqrt{\frac{2\pi\hbar}{\lambda_i}}.
$$

Multiplying over $i$ gives

$$
(2\pi\hbar)^{N/2}\prod_i\lambda_i^{-1/2}
=(2\pi\hbar)^{N/2}(\det K)^{-1/2}.
$$

</details>

### Exercise 3: Loop counting

A connected Feynman graph has $I$ internal lines and $V$ vertices. Assume each propagator contributes $\hbar$ and each vertex contributes $1/\hbar$. Show that its overall power is $\hbar^{L-1}$, where $L$ is the number of loops.

<details>
<summary><strong>Solution</strong></summary>

The graph contributes

$$
\hbar^I\hbar^{-V}=\hbar^{I-V}.
$$

For a connected graph,

$$
L=I-V+1.
$$

Therefore

$$
I-V=L-1,
$$

so the graph scales as

$$
\boxed{\hbar^{L-1}.}
$$

If $Z=e^{iW/\hbar}$, this means $W$ itself has the expansion

$$
W=W_{\rm tree}+\hbar W_1+\hbar^2W_2+\cdots.
$$

</details>

### Exercise 4: One-loop effective potential kernel

For

$$
S_E[\varphi]=\int d^dx\left[\frac12(\partial\varphi)^2+V(\varphi)\right],
$$

expand around a constant field $\varphi=\phi+\eta$. Show that the quadratic fluctuation operator is

$$
K_E=-\partial_E^2+V''(\phi).
$$

<details>
<summary><strong>Solution</strong></summary>

Expand the potential:

$$
V(\phi+\eta)=V(\phi)+V'(\phi)\eta+\frac12V''(\phi)\eta^2+\cdots.
$$

Since $\phi$ is constant,

$$
\frac12(\partial(\phi+\eta))^2=\frac12(\partial\eta)^2.
$$

Integrating the kinetic term by parts gives

$$
\frac12\int d^dx\,(\partial\eta)^2
=\frac12\int d^dx\,\eta(-\partial_E^2)\eta
$$

assuming suitable boundary conditions. Thus the quadratic part is

$$
S_E^{(2)}=\frac12\int d^dx\,\eta[-\partial_E^2+V''(\phi)]\eta.
$$

So

$$
\boxed{K_E=-\partial_E^2+V''(\phi).}
$$

</details>

### Exercise 5: Removing a zero mode

Suppose a Euclidean fluctuation operator has normalized eigenfunctions $u_n$ with eigenvalues $\lambda_n$, and one eigenvalue is zero: $\lambda_0=0$. Explain why the determinant should be replaced by $\det{}'K=\prod_{n\ne0}\lambda_n$ before introducing a collective coordinate.

<details>
<summary><strong>Solution</strong></summary>

Expanding

$$
\eta=\sum_n c_nu_n,
$$

the quadratic action is

$$
\frac12\sum_n\lambda_nc_n^2.
$$

For $\lambda_0=0$, the coefficient $c_0$ does not appear in the Gaussian weight. Therefore

$$
\int dc_0\,e^{-\lambda_0c_0^2/2}
=\int dc_0
$$

is not a Gaussian integral. It represents motion along a family of equivalent or related saddles. The Gaussian determinant should include only nonzero modes:

$$
\det{}'K=\prod_{n\ne0}\lambda_n.
$$

The missing integration is then replaced by an integral over the corresponding collective coordinate, with an appropriate Jacobian.

</details>

### Exercise 6: Fermion determinant sign

A real bosonic Gaussian gives $(\det K)^{-1/2}$, while a Dirac Grassmann Gaussian gives $\det D$. Explain why bosonic and fermionic one-loop contributions enter $\Gamma_E$ with opposite signs.

<details>
<summary><strong>Solution</strong></summary>

For bosons,

$$
Z_{E,\rm boson}\propto(\det K)^{-1/2}
=\exp\left[-\frac12\operatorname{Tr}\log K\right].
$$

Since

$$
Z_E=e^{-\Gamma_E/\hbar},
$$

the exponent contribution $-\frac12\operatorname{Tr}\log K$ corresponds to

$$
\Gamma_E^{(1),\rm boson}=\frac{\hbar}{2}\operatorname{Tr}\log K.
$$

For Dirac fermions,

$$
Z_{E,\rm fermion}\propto\det D
=\exp[\operatorname{Tr}\log D].
$$

Therefore

$$
\Gamma_E^{(1),\rm fermion}=-\hbar\operatorname{Tr}\log D.
$$

The sign difference comes from Berezin integration: fermionic variables produce determinants in the numerator rather than inverse square roots in the denominator.

</details>

## Sources and further reading

### Primary references

- P. A. M. Dirac, “The Lagrangian in Quantum Mechanics,” for the action-phase viewpoint behind path integrals.
- R. P. Feynman, “Space-Time Approach to Non-Relativistic Quantum Mechanics,” for the path-integral formulation and stationary-phase classical limit.
- J. Schwinger, “On the Green's Functions of Quantized Fields,” for source methods and Green functions.
- R. Jackiw, “Functional Evaluation of the Effective Potential,” for a classic functional derivation of one-loop effective potentials.
- S. Coleman, “The Uses of Instantons,” for semiclassical methods, instantons, zero modes, and fluctuation determinants.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, §§32.1–32.2 and ch. 44, for loop counting, stationary phase, the effective action, and the effective potential.
- M. Srednicki, *Quantum Field Theory*, §§6–9, §13, and §53, for path integrals, exact propagators, and functional determinants.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§9–10 and Vol. II, §16, for path integrals, effective actions, and one-loop methods.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. I.2 and appendix A, for the stationary-phase classical limit and Gaussian identities.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§9–11, for generating functionals, effective actions, and loop expansions.

### For a first pass

- Zee, ch. I.2.
- Srednicki, §§6–9.
- Coleman, §§32.1–32.2.

### For mathematical precision

- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, for spectral theory behind determinants and fluctuation operators.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for rigorous functional-integral constructions.
- B. Simon, *Functional Integration and Quantum Physics*, for measure-theoretic aspects of Euclidean path integrals.

## Version history

- **2026-05-23:** Initial qft.org page on stationary phase, saddle points, one-loop determinants, loop counting, effective potentials, zero modes, and negative modes.
