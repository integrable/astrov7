---
title: "Conventions for Nonperturbative QFT"
description: "Conventions for Euclidean continuation, path integrals, gauge fields, topological sectors, Wilson loops, lattice notation, and large-N limits in the Nonperturbative QFT volume."
sidebar:
  label: "Conventions"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki; Coleman; Polyakov; Weinberg; Zinn-Justin; Mariño; Shifman; Gaiotto et al."
topics:
  - conventions
  - Euclidean path integrals
  - gauge fields
  - topological sectors
  - Wilson loops
  - large-N limits
canonicalTopics:
  - qft-conventions
  - nonperturbative-qft
  - euclidean-qft
  - gauge-theory-conventions
researchStatus:
  established:
    - "The sign, normalization, and Euclidean-continuation conventions fixed here are bookkeeping choices; physical statements are invariant under consistent translations."
  active:
    - "Some conventions for global forms of gauge groups, line operators, and generalized symmetries are refined in specialized pages."
---

## Summary

This page fixes the default conventions used in the Nonperturbative QFT volume. The general spacetime conventions are the standard conventions used across the site: mostly-minus Lorentzian metric, natural units, and plane waves $e^{-ip\cdot x}$. This page adds the conventions that become especially important beyond ordinary perturbation theory: Euclidean continuation, path-integral normalization, gauge-field normalization, topological charge, line operators, lattice notation, and large-N counting.

The basic Lorentzian-to-Euclidean translation is

$$
Z_M[J]=\int_{\mathcal C_M}\mathcal D\Phi\,e^{iS_M+i\int J\mathcal O}
\quad\longrightarrow\quad
Z_E[J_E]=\int_{\mathcal C_E}\mathcal D\Phi\,e^{-S_E+\int J_E\mathcal O_E}.
$$

The choice of integration cycle, boundary conditions, and topological sector is part of the definition of the Euclidean path integral. This is one of the main morals of nonperturbative QFT: the formula $\int\mathcal D\Phi\,e^{-S_E}$ is not a single object until the global data are specified.

:::note[Default convention]
Unless a page says otherwise, this volume uses

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),\qquad \hbar=c=1,
\qquad f(x)=\int\frac{d^dp}{(2\pi)^d}\,e^{-ip\cdot x}\widetilde f(p).
$$

Euclidean path integrals are weighted by $e^{-S_E}$, and Yang–Mills instantons of charge $Q=1$ carry the semiclassical weight $e^{-8\pi^2/g^2+i\theta}$ in four dimensions.
:::

## Prerequisites

You should be comfortable with Gaussian path integrals, Wick rotation, basic gauge theory, and the meaning of correlation functions. For the conceptual role of these conventions, see [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/).

## Core idea

Perturbative calculations often hide conventions because only a local expansion around one vacuum is being used. Nonperturbative calculations expose them. To ask a nonperturbative question, one usually has to say more than “expand the Lagrangian.” One must also specify the state or thermal ensemble, the spacetime manifold, the regulator, the boundary conditions, the global form of the gauge group, the allowed line operators, and the sum over topological sectors.

This page is therefore not a list of aesthetic preferences. It is a list of choices that later pages rely on when they discuss instantons, solitons, tunneling, Wilson loops, confinement, mass gaps, finite-volume spectra, large-N limits, and lattice continuum limits.

A useful slogan is

$$
\text{nonperturbative convention}
=\text{local formula}+\text{global definition data}.
$$

## Setup and conventions

### Spacetime dimension and notation

The symbol $d$ denotes spacetime dimension. In Lorentzian signature we often write $d=D+1$, where $D$ is the number of spatial dimensions. Thus four-dimensional relativistic QFT has $d=4$ and $D=3$.

Lorentzian coordinates are

$$
x^\mu=(t,\mathbf x),\qquad
p\cdot x=p^0t-\mathbf p\cdot\mathbf x,
$$

with mostly-minus metric

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,\ldots,-1).
$$

The Lorentzian d’Alembertian is

$$
\Box=\partial_\mu\partial^\mu=\partial_t^2-\nabla^2.
$$

Euclidean coordinates are denoted $x_E^\mu$, or simply $x^\mu$ when the signature is clear. Euclidean contractions use $\delta_{\mu\nu}$:

$$
p_E^2=\sum_{\mu=1}^d p_\mu p_\mu.
$$

### Fourier transforms

The default Fourier transform in $d$ Lorentzian spacetime dimensions is

$$
f(x)=\int_p e^{-ip\cdot x}\widetilde f(p),
\qquad
\widetilde f(p)=\int d^dx\,e^{ip\cdot x}f(x),
\qquad
\int_p\equiv\int\frac{d^dp}{(2\pi)^d}.
$$

For Euclidean correlators we use the same compact notation,

$$
f(x)=\int_p e^{ip\cdot x}\widetilde f(p),
\qquad
\int_p\equiv\int\frac{d^dp}{(2\pi)^d},
$$

where $p\cdot x$ now means the Euclidean dot product. The sign in the Euclidean exponential is a convention; correlation functions and propagators fix the practical meaning.

### Wick rotation and Euclidean weights

The default Wick rotation is

$$
t=-i\tau,
\qquad
p^0=i p_E^0,
$$

with Euclidean path-integral weight $e^{-S_E}$. For a scalar field with Lorentzian action

$$
S_M=\int d^dx\left(\frac12\partial_\mu\phi\,\partial^\mu\phi-V(\phi)\right),
$$

the corresponding Euclidean action is

$$
S_E=\int d^dx_E\left(\frac12(\partial_\mu\phi)^2+V(\phi)\right).
$$

For a positive Euclidean quadratic operator $K$, the Gaussian convention is

$$
\int \mathcal D\phi\,\exp\left[-\frac12\int d^dx\,\phi K\phi+\int d^dx\,J\phi\right]
\propto
\exp\left[\frac12\int d^dx\,d^dy\,J(x)K^{-1}(x,y)J(y)\right].
$$

The proportionality constant is usually absorbed into the normalization of $Z[0]$, unless the determinant itself is the observable under discussion.

### Correlation functions

Euclidean vacuum or thermal expectation values are normalized as

$$
\langle\mathcal O_1\cdots\mathcal O_n\rangle
=\frac{1}{Z}\int_{\mathcal C}\mathcal D\Phi\,
\mathcal O_1\cdots\mathcal O_n\,e^{-S_E[\Phi]},
\qquad
Z=\int_{\mathcal C}\mathcal D\Phi\,e^{-S_E[\Phi]}.
$$

The symbol $\mathcal C$ is deliberately included. It may encode boundary conditions, a choice of real or complex integration cycle, a sum over sectors, or a finite-volume Hilbert-space trace. In perturbation theory this symbol is often invisible; in nonperturbative QFT it is load-bearing.

Connected correlators are generated by

$$
W[J]=\log Z[J],
$$

and one-particle-irreducible correlators by the Legendre transform $\Gamma[\varphi]$. In nonperturbative discussions, $\Gamma$ means the full quantum effective action only when the existence and convexity assumptions are clear. A loop-expanded effective action around a metastable saddle is not automatically the same object as the exact convex effective action.

### Vacuum, volume, and temperature

At zero temperature, the Euclidean vacuum path integral is usually obtained as a large-time projection,

$$
\langle\mathcal O\rangle_0
=\lim_{T\to\infty}\frac{\operatorname{Tr}\left(e^{-T H}\mathcal O\right)}{\operatorname{Tr}\left(e^{-T H}\right)},
$$

with appropriate boundary conditions. At finite temperature,

$$
\beta=\frac{1}{T_{\mathrm{phys}}},
\qquad
Z(\beta)=\operatorname{Tr}e^{-\beta H},
$$

and the Euclidean time direction is a circle of circumference $\beta$. Bosons are periodic around this circle; fermions are antiperiodic unless a page is explicitly discussing a supersymmetric index, a twisted partition function, or a different spin structure.

Finite spatial volume is usually a torus of side length $L$. A mass gap $\Delta$ can be extracted from the large Euclidean-time decay of connected correlators or from the finite-volume Hamiltonian spectrum, but the order of limits matters:

$$
\text{infinite-volume QFT} = \lim_{L\to\infty}\lim_{a\to0}\text{regulated finite-volume theory},
$$

with the precise order stated when it affects the result.

## Gauge fields and topological sectors

### Lie algebra normalization

For compact simple gauge groups we use Hermitian generators $T^a$ satisfying

$$
[T^a,T^b]=i f^{abc}T^c,
\qquad
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}
$$

in the fundamental representation of $SU(N)$. The symbol $\operatorname{tr}$ denotes a matrix trace with the normalization just stated. When a different representation is used, we write $\operatorname{tr}_R$ or $\operatorname{Tr}_R$ and state the normalization if it matters.

### Connection normalization

For topological and semiclassical pages, the default gauge connection is coupling-independent and inherits the global sign convention $D_\mu=\partial_\mu+igB_\mu^aT^a$ after the rescaling $A_\mu=gB_\mu$:

$$
A_\mu=A_\mu^aT^a,
\qquad
D_\mu=\partial_\mu+iA_\mu.
$$

Thus

$$
[D_\mu,D_\nu]=iF_{\mu\nu},
\qquad
F_{\mu\nu}
=\partial_\mu A_\nu-\partial_\nu A_\mu+i[A_\mu,A_\nu].
$$

Equivalently, in components,

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-f^{abc}A_\mu^bA_\nu^c.
$$

With this geometric normalization, the Euclidean Yang–Mills action in four dimensions is

$$
S_{E,\mathrm{YM}}=\frac{1}{2g^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}-i\theta Q.
$$

The topological charge is

$$
Q=\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}
=\frac{1}{8\pi^2}\int \operatorname{tr}F\wedge F,
$$

where

$$
\widetilde F_{\mu\nu}=\frac12\epsilon_{\mu\nu\rho\sigma}F_{\rho\sigma},
\qquad
\epsilon_{1234}=+1
$$

in Euclidean signature. For smooth finite-action $SU(N)$ gauge fields on $\mathbb R^4$ with the usual boundary conditions, $Q\in\mathbb Z$.

A self-dual instanton obeys

$$
F_{\mu\nu}=\widetilde F_{\mu\nu},
$$

and an anti-instanton obeys $F_{\mu\nu}=-\widetilde F_{\mu\nu}$. The action satisfies the bound

$$
\frac{1}{2g^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}
\geq
\frac{8\pi^2}{g^2}|Q|.
$$

Thus a charge-one instanton contributes with the semiclassical weight

$$
e^{-S_E}=e^{-8\pi^2/g^2+i\theta}.
$$

Pages focused on perturbative Feynman rules may instead use a coupling-dependent field $A_\mu^{\mathrm{pert}}=A_\mu/g$. Such pages should state the rescaling explicitly.

### Theta angles and sector sums

When the configuration space decomposes into sectors labeled by a topological charge $Q$, the theta-dependent partition function is written

$$
Z(\theta)=\sum_Q e^{i\theta Q} Z_Q,
\qquad
Z_Q=\int_{\mathcal C_Q}\mathcal D\Phi\,e^{-S_{E,0}[\Phi]}.
$$

The same notation is used for sigma models, gauge theories, and quantum-mechanical examples, but the meaning of $Q$ depends on the target space, gauge bundle, spacetime dimension, and boundary conditions.

## Wilson, ’t Hooft, and Polyakov loops

For a closed curve $C$ and representation $R$, the Wilson loop is

$$
W_R(C)=\frac{1}{\dim R}\operatorname{tr}_R\,\mathcal P\exp\left(-i\oint_C A\right).
$$

The normalization $1/\dim R$ makes $W_R(C)=1$ for a trivial connection. A temporal Polyakov loop at temperature $T_{\mathrm{phys}}=1/\beta$ is

$$
P_R(\mathbf x)=\frac{1}{\dim R}\operatorname{tr}_R\,\mathcal P\exp\left(-i\int_0^\beta d\tau\,A_\tau(\tau,\mathbf x)\right).
$$

An ’t Hooft loop is a disorder line operator defined by a prescribed magnetic singularity or, equivalently, by imposing a specified gauge-bundle modification around the loop. The exact label of an ’t Hooft line depends on the global form of the gauge group. For example, $SU(N)$ and $PSU(N)=SU(N)/\mathbb Z_N$ have the same Lie algebra but different genuine line operators.

When line operators are discussed, the page should specify at least three things:

| Data | Why it matters |
|---|---|
| Local gauge algebra | Determines perturbative gluons and local currents. |
| Global form of the gauge group | Determines allowed electric line charges. |
| Genuine line operators | Determines one-form symmetries and confinement diagnostics. |

This is not optional polish. In modern language, confinement, screening, and generalized global symmetries cannot be stated cleanly without these data.

## Lattice conventions

A Euclidean hypercubic lattice has spacing $a$, sites $x$, and link variables

$$
U_\mu(x)\in G.
$$

The elementary plaquette is

$$
U_{\mu\nu}(x)=U_\mu(x)U_\nu(x+a\hat\mu)U_\mu(x+a\hat\nu)^{-1}U_\nu(x)^{-1}.
$$

For pure $SU(N)$ lattice gauge theory, the Wilson action is written

$$
S_W=\beta\sum_p\left(1-\frac{1}{N}\operatorname{Re}\operatorname{Tr}U_p\right),
\qquad
\beta=\frac{2N}{g_0^2},
$$

where $\operatorname{Tr}$ is the ordinary trace in the fundamental representation and $g_0$ is the bare lattice coupling. The continuum limit is not the formal limit $a\to0$ at fixed bare parameters. It is a limit toward a critical point in bare-parameter space while holding physical quantities fixed.

For scalar lattice theories, fields live on sites. For gauge theories, gauge fields live on links. This small distinction is the seed of much of lattice gauge theory.

## Large-N conventions

For $SU(N)$ gauge theories, the large-N limit means

$$
N\to\infty,
\qquad
\lambda=g^2N\quad\text{fixed},
$$

where $\lambda$ is the ’t Hooft coupling. Single-trace operators are normalized as

$$
\mathcal O(x)=\frac{1}{N}\operatorname{Tr}\left(\Phi_1(x)\cdots\Phi_k(x)\right)
$$

unless a page states another normalization. With this convention, large-N factorization takes the schematic form

$$
\langle\mathcal O_1\mathcal O_2\rangle
=
\langle\mathcal O_1\rangle\langle\mathcal O_2\rangle+O(N^{-2})
$$

for normalized single-trace bosonic operators in standard planar limits.

The symbol $O(N^{-1})$ or $O(N^{-2})$ is not universal across all large-N limits. Vector models, matrix models, tensor models, and gauge theories have different counting rules. The page should say which large-N limit is being used.

## Semiclassical and asymptotic conventions

A semiclassical expansion around a Euclidean saddle $\Phi_\star$ is written schematically as

$$
\langle\mathcal O\rangle_{\Phi_\star}
\sim
\exp\left[-S_E[\Phi_\star]\right]
\sum_{n\geq0} a_n g^n.
$$

After rescaling fields, many gauge-theory saddles have $S_E[\Phi_\star]\propto 1/g^2$, so their contributions are of order

$$
e^{-A/g^2}\sum_{n\geq0}a_n g^n.
$$

A perturbative expansion around the trivial saddle usually cannot see such terms at any finite order in $g$.

When the beta function is written as

$$
\mu\frac{dg}{d\mu}=-b_0g^3-b_1g^5+O(g^7),
\qquad b_0>0,
$$

an asymptotically free theory has a dynamically generated scale of the schematic form

$$
\Lambda
=\mu\,\exp\left[-\frac{1}{2b_0g^2(\mu)}\right]
\left(b_0g^2(\mu)\right)^{-b_1/(2b_0^2)}
\left[1+O(g^2)\right].
$$

The precise definition of $\Lambda$ is scheme-dependent, but dimensionless ratios of physical observables are not.

## Operator terminology

A local operator is supported at a point. An extended operator is supported on a positive-dimensional submanifold, such as a line, surface, or domain wall. A defect may be either a dynamical excitation or an inserted condition in the path integral; the page should say which meaning is intended.

A genuine operator is well-defined on its support without choosing an auxiliary surface or higher-dimensional attachment. A non-genuine operator requires such extra data. This distinction is essential for line operators, disorder operators, higher-form symmetries, and confinement diagnostics.

The phrase order parameter is used broadly for an observable that distinguishes phases in an appropriate limit. It need not be a local field expectation value. Wilson loops, Polyakov loops, disorder operators, topological ground-state degeneracy, and entanglement diagnostics can all serve as phase diagnostics in the right setting.

## Common pitfalls

| Pitfall | Repair |
|---|---|
| “Euclidean path integral” means only $e^{-S_E}$. | One must also specify the integration cycle, regulator, boundary conditions, and sector sum. |
| A theta term changes the classical Euclidean equations. | The $-i\theta Q$ term is topological in ordinary Yang–Mills theory; it changes quantum weights between sectors. |
| Instantons are just “small corrections.” | They can encode tunneling, anomalies, selection rules, vacuum structure, and large-order behavior. |
| Confinement means the coupling is numerically large. | Confinement is a statement about the spectrum and long-distance behavior of line operators. |
| A gauge algebra fixes the gauge theory. | The global form of the gauge group and the allowed line operators are also part of the theory. |
| The lattice is merely a numerical trick. | A lattice can be a nonperturbative regulator and a definition of the continuum theory when a continuum limit exists. |
| Large-N means the same thing in every model. | Vector, matrix, tensor, and gauge large-N limits have different normalizations and expansion parameters. |

## Relations to other pages

This page is the convention anchor for [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/). Later pages on Euclidean path integrals, instantons, Wilson loops, lattice regularization, confinement, and large-N methods should either use these conventions or state their translation explicitly.

This page does not replace the global site conventions. It records only the extra normalization choices that are unusually important in nonperturbative physics.

## Research status

**Established.** The Euclidean weighting, instanton action normalization, topological charge normalization, Wilson loop normalization, and large-N ’t Hooft scaling used here are standard choices. Other standard choices exist and are equivalent after translation.

**Convention-dependent.** The normalization of gauge fields, traces, theta angles, and line-operator charges varies across the literature. Any page comparing multiple sources should translate explicitly rather than mixing formulas.

**Active.** The clean organization of line operators, generalized global symmetries, non-invertible defects, and global forms of gauge groups is a modern language that continues to sharpen older discussions of confinement and phases.

## Exercises

### Exercise 1: Wick rotation for a scalar action

Start from

$$
S_M=\int dt\,d^{D}\mathbf x\left(\frac12(\partial_t\phi)^2-\frac12(\nabla\phi)^2-V(\phi)\right).
$$

Using $t=-i\tau$, show that the Euclidean action entering $e^{-S_E}$ is

$$
S_E=\int d\tau\,d^D\mathbf x\left(\frac12(\partial_\tau\phi)^2+\frac12(\nabla\phi)^2+V(\phi)\right).
$$

<details><summary><strong>Solution</strong></summary>

Under $t=-i\tau$, one has $dt=-i d\tau$ and $\partial_t=i\partial_\tau$. The Lorentzian path-integral phase is $iS_M$. Substituting gives

$$
iS_M
=i\int (-i d\tau)d^D\mathbf x\left(\frac12(i\partial_\tau\phi)^2-\frac12(\nabla\phi)^2-V(\phi)\right).
$$

Since $(i\partial_\tau\phi)^2=-(\partial_\tau\phi)^2$, this becomes

$$
iS_M
=\int d\tau d^D\mathbf x\left(-\frac12(\partial_\tau\phi)^2-\frac12(\nabla\phi)^2-V(\phi)\right)
=-S_E.
$$

Hence the Euclidean weight is $e^{-S_E}$ with the stated positive kinetic terms.

</details>

### Exercise 2: Instanton weight with a theta angle

Using

$$
S_E=\frac{1}{2g^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}-i\theta Q,
$$

show that a charge-$Q$ self-dual Yang–Mills saddle contributes

$$
e^{-8\pi^2 Q/g^2+i\theta Q}
$$

for $Q>0$.

<details><summary><strong>Solution</strong></summary>

For a self-dual field, $F=\widetilde F$, so

$$
Q=\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}.
$$

Therefore

$$
\frac{1}{2g^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}
=\frac{8\pi^2 Q}{g^2}.
$$

The theta term contributes $-i\theta Q$ to $S_E$, so the path-integral weight is

$$
e^{-S_E}=e^{-8\pi^2 Q/g^2+i\theta Q}.
$$

</details>

### Exercise 3: Large-N normalization

Let

$$
\mathcal O(x)=\frac1N\operatorname{Tr}\Phi^2(x)
$$

be a normalized single-trace operator in a matrix large-N limit. If connected two-point functions of normalized single-trace operators scale as $N^{-2}$, what is the leading scaling of

$$
\langle\mathcal O(x)\mathcal O(y)\rangle-\langle\mathcal O(x)\rangle\langle\mathcal O(y)\rangle?
$$

<details><summary><strong>Solution</strong></summary>

By assumption, the connected part of the normalized two-point function scales as

$$
\langle\mathcal O(x)\mathcal O(y)\rangle_c=O(N^{-2}).
$$

Thus large-N factorization says

$$
\langle\mathcal O(x)\mathcal O(y)\rangle
=\langle\mathcal O(x)\rangle\langle\mathcal O(y)\rangle+O(N^{-2}).
$$

The $1/N$ in the definition of $\mathcal O$ is what makes the disconnected term order one.

</details>

### Exercise 4: Continuum limit versus small lattice spacing

Why is the statement “take $a\to0$” incomplete as a definition of a continuum limit?

<details><summary><strong>Solution</strong></summary>

A lattice theory is defined by a spacing $a$ and by bare parameters, such as $g_0$, masses, and lattice couplings. Sending $a\to0$ without tuning the bare parameters does not specify which physical theory is approached. A continuum limit requires tuning toward a critical point where the correlation length in lattice units diverges,

$$
\frac{\xi_{\mathrm{phys}}}{a}\to\infty,
$$

while selected physical observables, such as a mass gap or string tension in physical units, are held fixed. The continuum limit is therefore a trajectory in bare-parameter space, not only a statement about a small lattice spacing.

</details>

## References

- M. Srednicki, *Quantum Field Theory*. Useful for path-integral, gauge-theory, Wilson-loop, lattice, soliton, and instanton conventions.
- S. Coleman, *Aspects of Symmetry*. Especially useful for solitons, instantons, false-vacuum decay, and large-N methods.
- A. M. Polyakov, *Gauge Fields and Strings*. Especially useful for strong-coupling expansions, compact gauge theory, confinement, instantons, and large-N ideas.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II. Useful for foundations, effective actions, gauge theory, and renormalization conventions.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Useful for Euclidean functional integrals, RG, instantons, large-order behavior, and critical phenomena.
- M. Mariño, *Instantons and Large N*. Useful for instantons, asymptotic expansions, Borel methods, and large-N expansions.
- M. Shifman, *Advanced Topics in Quantum Field Theory*. Useful for phases of gauge theories, solitons, instantons, anomalies, confinement, and higher-form symmetry conventions.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries.” Useful for modern terminology around higher-form symmetries and line operators.

## Version history

- **2026-06-25:** Initial polished draft.
