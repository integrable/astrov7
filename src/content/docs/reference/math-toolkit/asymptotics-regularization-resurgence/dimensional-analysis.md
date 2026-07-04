---
title: "Dimensional Analysis"
description: "Explains mass dimension, field dimensions, operator dimensions, coupling dimensions, power counting, relevance, naturalness, dimensional transmutation, and QFT uses of dimensional analysis."
sidebar:
  label: "Dimensional Analysis"
  order: 2
level: Graduate
status: "Polished draft"
source: "Standard references on QFT, EFT, renormalization, and dimensional analysis, including Wilson–Kogut, Weinberg, Srednicki, Schwartz, Zee, Zinn-Justin, Burgess, Coleman, Peskin–Schroeder, and Georgi."
topics:
  - dimensional analysis
  - mass dimension
  - power counting
  - operator dimension
  - coupling dimension
  - relevance
  - marginal operator
  - effective field theory
  - naturalness
  - dimensional transmutation
canonicalTopics:
  - dimensional-analysis
  - mass-dimension
  - power-counting
  - operator-dimension
  - coupling-dimension
  - relevant-operator
  - marginal-operator
  - effective-field-theory
  - naturalness
  - dimensional-transmutation
researchStatus:
  established:
    - "Canonical mass dimensions, tree-level power counting, and the classification of couplings as relevant, marginal, or irrelevant are standard mathematical tools in QFT and EFT."
    - "Dimensional analysis is exact for units and engineering dimensions; anomalous dimensions and logarithmic running require dynamics."
  active:
    - "The best power-counting scheme for a given EFT, especially with multiple scales, strong coupling, boundaries, defects, gravity, or nonrelativistic modes, can be subtle and remains an active practical problem."
---

## Summary

Dimensional analysis is the first draft of renormalization. It tells you which terms can appear in an action, how their coefficients scale with energy, which interactions dominate at long distances, and which counterterms are allowed by locality and symmetry. It will not compute a beta function for you — rude, but fair — but it tells you where the beta function is allowed to live.

In units $c=\hbar=1$, every dimension is measured as a power of mass. In $d$ spacetime dimensions,

$$
[x]=-1,
\qquad
[\partial]=1,
\qquad
[d^d x]=-d,
\qquad
[S]=0,
\qquad
[\mathcal L]=d.
$$

If a local operator $\mathcal O_i$ has dimension $\Delta_i$, then a term

$$
S\supset \int d^d x\, g_i\mathcal O_i
$$

requires

$$
[g_i]=d-\Delta_i.
$$

That one line is the backbone of power counting. It distinguishes relevant, marginal, and irrelevant interactions; it explains why masses are dangerous, why logarithms are special, why higher-derivative operators are suppressed in effective field theory, and why QFT pages keep talking about scales even after setting $\hbar=c=1$.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Flow diagram from mass units to action dimension, field dimensions, operator dimensions, coupling dimensions, and relevance classification.](/figures/math-toolkit/dimensional-analysis-scaling-flow.svg)

<figcaption>

Dimensional analysis proceeds from units to the action, from the action to field dimensions, from fields to local operators, and from operators to coupling dimensions. The final classification is tree-level: loop corrections and anomalous dimensions deform it, but they do not erase the basic map.

</figcaption>
</figure>

This page explains mass dimensions, canonical field dimensions, operator dimensions, coupling dimensions, superficial divergence estimates, EFT power counting, naturalness, and the difference between dimensional analysis as a theorem about units and scaling analysis as a statement about dynamics.

## Prerequisites and conventions

You should be comfortable with Lagrangians, Fourier transforms, Gaussian integrals, and basic perturbative QFT notation. Useful nearby pages are [Conventions](/math-toolkit/conventions/), [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/), [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/), [Asymptotic Series](/math-toolkit/asymptotics-regularization-resurgence/asymptotic-series/), and [Determinants, Traces, and Jacobians](/math-toolkit/linear-algebra-tensors/determinants-traces-and-jacobians/).

Unless stated otherwise, dimensions are **mass dimensions**. Thus

$$
[\text{mass}]=[\text{energy}]=[\text{momentum}]=1,
\qquad
[\text{length}]=[\text{time}]=-1.
$$

The spacetime dimension is denoted by $d$. In particle-physics applications $d=4$ unless a page says otherwise. In statistical-mechanics or Euclidean applications, one often writes $D$ for the number of Euclidean dimensions. This page uses $d$ because the formulas are the same after continuation.

:::note[Dimension versus scaling]
Mass dimension is a statement about units. Scaling dimension at a fixed point is a dynamical statement. They agree for free fields in many familiar normalizations, but interacting fixed points can add anomalous dimensions.
:::

## The action fixes the bookkeeping

In the path integral, the phase is $e^{iS}$ in Lorentzian signature or $e^{-S_E}$ in Euclidean signature. Because the exponent must be dimensionless,

$$
[S]=0.
$$

For a local action

$$
S=\int d^d x\,\mathcal L,
$$

we therefore need

$$
[d^d x]+[\mathcal L]=0.
$$

Since each coordinate has dimension $[x]=-1$,

$$
[d^d x]=-d,
$$

and hence

$$
[\mathcal L]=d.
$$

That is the whole game. Every term in a Lagrangian density must have total mass dimension $d$.

For example, in four dimensions, $\mathcal L$ has dimension $4$. A mass term $m^2\phi^2$ has dimension $4$ only if $m^2$ has dimension $2$ and $\phi$ has dimension $1$. A term $\lambda\phi^4$ has dimension $4$ only if $\lambda$ is dimensionless. A term $c_6\phi^6$ has dimension $4$ only if $c_6$ has dimension $-2$, so one expects

$$
c_6\sim \frac{1}{\Lambda_*^2}
$$

when it comes from physics at a heavy scale $\Lambda_*$.

This does not prove the coefficient is numerically $1/\Lambda_*^2$. It proves that any coefficient multiplying $\phi^6$ in four dimensions must carry two inverse powers of mass. The dimensionless number multiplying those powers is dynamics.

## Canonical field dimensions

Field dimensions follow from kinetic terms. The word **canonical** means that we are using the free quadratic kinetic term to assign dimensions. Interactions can modify scaling dimensions at a fixed point, but canonical dimensions are the starting point for perturbation theory and EFT.

### Scalar fields

For a real scalar field with kinetic term

$$
\mathcal L_{\text{kin}}={1\over2}\partial_\mu\phi\,\partial^\mu\phi,
$$

we require

$$
[\partial_\mu\phi\,\partial^\mu\phi]=d.
$$

Since $[\partial]=1$,

$$
2+2[\phi]=d,
$$

so

$$
[\phi]=\frac{d-2}{2}.
$$

In $d=4$,

$$
[\phi]=1.
$$

In $d=2$, a free scalar has canonical dimension zero. This innocuous fact is the seed of many two-dimensional delights and nightmares: logarithmic propagators, vertex operators, compact bosons, and marginal-looking exponentials.

### Fermion fields

For a Dirac fermion,

$$
\mathcal L_{\text{kin}}=\bar\psi\,i\gamma^\mu\partial_\mu\psi.
$$

The gamma matrices are dimensionless, so

$$
[\bar\psi]+1+[\psi]=d.
$$

Since $\bar\psi$ and $\psi$ have the same mass dimension,

$$
[\psi]=[\bar\psi]=\frac{d-1}{2}.
$$

In $d=4$,

$$
[\psi]=\frac32.
$$

This explains why a Yukawa interaction $y\phi\bar\psi\psi$ is dimension four in four dimensions:

$$
[\phi\bar\psi\psi]=1+{3\over2}+{3\over2}=4,
$$

so $[y]=0$.

### Gauge fields

There are two common normalizations for gauge fields. In the particle-physics normalization,

$$
D_\mu=\partial_\mu+i g A_\mu,
$$

and the gauge kinetic term is written with canonically normalized $A_\mu$. Then the free term schematically looks like

$$
\mathcal L_{\text{kin}}\sim -{1\over4}F_{\mu\nu}F^{\mu\nu},
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu+\cdots,
$$

so

$$
[A_\mu]=\frac{d-2}{2}.
$$

The covariant derivative requires $[gA_\mu]=1$, hence

$$
[g]=1-[A_\mu]=\frac{4-d}{2}.
$$

In four dimensions, $[A_\mu]=1$ and $[g]=0$.

In a geometric normalization, one often regards $A=A_\mu dx^\mu$ as a connection and writes $D=d+iA$. Then $A_\mu$ has dimension $1$, while the coupling appears in front of the kinetic term:

$$
S\sim -{1\over 4g^2}\int d^d x\,\operatorname{tr}F_{\mu\nu}F^{\mu\nu}.
$$

The physical dimension of $g$ is the same. The difference is where the factor is placed. This is why comparing gauge-theory formulas across books is occasionally a tiny convention dungeon.

## Operators and couplings

Let $\mathcal O_i(x)$ be a local operator with mass dimension $\Delta_i$. A local interaction in the action has the form

$$
S_i=\int d^d x\,g_i\mathcal O_i(x).
$$

Since $S_i$ is dimensionless,

$$
[g_i]+\Delta_i-d=0,
$$

so

$$
[g_i]=d-\Delta_i.
$$

This formula gives the tree-level classification:

| Operator dimension | Coupling dimension | Name | Tree-level behavior |
|---|---:|---|---|
| $\Delta_i<d$ | $[g_i]>0$ | relevant | grows at long distances |
| $\Delta_i=d$ | $[g_i]=0$ | marginal | needs loop/anomalous-dimension test |
| $\Delta_i>d$ | $[g_i]<0$ | irrelevant | suppressed at long distances |

The names come from Wilsonian renormalization. To make a dimensionless coupling at a scale $\mu$, define

$$
\tilde g_i(\mu)=g_i\mu^{\Delta_i-d}.
$$

At tree level,

$$
\mu{d\tilde g_i\over d\mu}=(\Delta_i-d)\tilde g_i.
$$

If $\Delta_i<d$, then $\Delta_i-d<0$, so $\tilde g_i$ grows as $\mu$ is lowered. Relevant couplings dominate the infrared. If $\Delta_i>d$, then $\tilde g_i$ shrinks as $\mu$ is lowered. Irrelevant couplings are suppressed in the infrared, though they can still encode measurable corrections.

For marginal couplings, dimensional analysis says only that tree-level scaling is neutral. Quantum corrections decide whether the coupling is marginally relevant, marginally irrelevant, or exactly marginal.

:::caution[Marginal does not mean harmless]
A dimensionless coupling is not automatically constant. In four-dimensional Yang–Mills theory, the gauge coupling is dimensionless by engineering dimension, but it runs logarithmically. Marginality is an invitation to compute the beta function.
:::

## The four-dimensional cheat sheet

In $d=4$, the canonical dimensions of common objects are

| Object | Dimension |
|---|---:|
| $x^\mu$ | $-1$ |
| $\partial_\mu$, $p_\mu$, $m$, $\mu$, $\Lambda$ | $1$ |
| $d^4x$ | $-4$ |
| $\mathcal L$ | $4$ |
| scalar $\phi$ | $1$ |
| gauge field $A_\mu$ in canonical normalization | $1$ |
| field strength $F_{\mu\nu}$ | $2$ |
| Dirac fermion $\psi$ | $3/2$ |
| current $j^\mu=\bar\psi\gamma^\mu\psi$ | $3$ |
| stress tensor $T^{\mu\nu}$ | $4$ |

Some common four-dimensional interactions are

| Term in $\mathcal L$ | Operator dimension | Coupling dimension | Classification |
|---|---:|---:|---|
| $m^2\phi^2/2$ | $2$ | $2$ | relevant |
| $m\bar\psi\psi$ | $3$ | $1$ | relevant |
| $\lambda\phi^4/4!$ | $4$ | $0$ | marginal at tree level |
| $y\phi\bar\psi\psi$ | $4$ | $0$ | marginal at tree level |
| $F_{\mu\nu}F^{\mu\nu}$ | $4$ | $0$ | marginal at tree level |
| $c_6\phi^6$ | $6$ | $-2$ | irrelevant |
| $c_F(\bar\psi\gamma_\mu\psi)^2$ | $6$ | $-2$ | irrelevant |
| $c_{\partial}(\partial_\mu\phi\partial^\mu\phi)^2$ | $8$ | $-4$ | irrelevant |

A four-fermion operator has dimension $6$ in four dimensions, so its coefficient must have dimension $-2$. This is why Fermi's weak interaction can be written schematically as

$$
\mathcal L_{\text{Fermi}}\sim G_F(\bar\psi\gamma_\mu\psi)(\bar\psi\gamma^\mu\psi),
\qquad
[G_F]=-2.
$$

At energies $E\ll M_W$, this is suppressed by a heavy scale:

$$
G_F\sim {1\over M_W^2}
$$

up to dimensionless constants. Dimensional analysis predicts the scale dependence; matching computes the constants.

## Why powers of momentum matter

Dimensional analysis can be done in position space or momentum space. Since $[p]=1$, each derivative in a local operator usually becomes a power of momentum in an amplitude. This is the core of low-energy EFT.

Suppose an interaction has the form

$$
\mathcal L\supset {c_i\over \Lambda_*^{\Delta_i-d}}\mathcal O_i,
\qquad
\Delta_i>d,
$$

where $\Lambda_*$ is a heavy scale and $c_i$ is dimensionless. In a process with characteristic energy $E\ll\Lambda_*$, that operator contributes schematically as

$$
c_i\left({E\over\Lambda_*}\right)^{\Delta_i-d},
$$

relative to an operator of dimension $d$, up to spin, symmetry, phase-space, and loop factors. The positive power of $E/\Lambda_*$ is why low-energy theories can be predictive even when infinitely many higher-dimension operators are allowed. At any desired accuracy, only finitely many operators matter.

This is a power-counting theorem in spirit, but not yet a full theorem in every theory. Multiple low scales, massless particles, near-threshold modes, nonrelativistic power counting, strong coupling, and collinear limits can all modify the useful counting. The basic dimensional estimate is the first layer, not the whole cake.

## Superficial degree of divergence

Dimensional analysis also estimates ultraviolet divergences. Consider a Euclidean loop integral that behaves at large momentum like

$$
I\sim\int^{\Lambda}d^d k\,{k^N\over (k^2)^P}.
$$

The measure contributes $d$, the numerator contributes $N$, and the denominator contributes $2P$, so the **superficial degree of divergence** is

$$
\omega=d+N-2P.
$$

If $\omega>0$, the integral has a power divergence of order $\Lambda^\omega$. If $\omega=0$, it has a logarithmic divergence. If $\omega<0$, this estimate says the integral is superficially convergent in the ultraviolet.

For example, in $d=4$,

$$
\int^{\Lambda}{d^4k\over (2\pi)^4}{1\over k^2+m^2}
$$

has $N=0$ and $P=1$, so

$$
\omega=4-2=2.
$$

Indeed, it has a quadratic divergence with a hard cutoff. Meanwhile,

$$
\int^{\Lambda}{d^4k\over (2\pi)^4}{1\over (k^2+m^2)^2}
$$

has

$$
\omega=4-4=0,
$$

so it diverges logarithmically.

Superficial counting is not the final answer. Symmetries, tensor numerators, gauge cancellations, subtractions, external momenta, and infrared regions can all change what appears in a physical observable. Still, superficial power counting is the fastest way to see which counterterms can be needed.

## Dimensional analysis of correlators

In a scale-invariant theory, the scaling dimension of an operator controls its correlators. If a scalar primary operator $\mathcal O$ has scaling dimension $\Delta$, then in flat Euclidean space,

$$
\langle \mathcal O(x)\mathcal O(0)\rangle\propto {1\over |x|^{2\Delta}}.
$$

Fourier transforming gives, up to contact terms and scheme-dependent normalization,

$$
\langle \mathcal O(p)\mathcal O(-p)\rangle\propto (p^2)^{\Delta-d/2}.
$$

This is dimensionally inevitable: the position-space expression has dimension $2\Delta$, and the Fourier transform contributes $-d$ from $d^d x$.

When $2\Delta-d$ is an even nonnegative integer, logarithms and contact terms often appear. For example, in four dimensions a dimension-four operator has a momentum-space two-point function with the schematic form

$$
p^4\log {p^2\over\mu^2}
$$

plus local polynomial terms. The power $p^4$ is dimensional analysis; the logarithm knows about renormalization.

## Logs are where dimensions hide

A logarithm cannot take a dimensionful argument. Expressions such as

$$
\log p^2
$$

are shorthand for something like

$$
\log {p^2\over\mu^2},
$$

where $\mu$ is a reference scale. The need for $\mu$ is not typography; it is physics. It means that a classically scale-neutral quantity has acquired scale dependence through regularization and renormalization.

For a dimensionless coupling $g(\mu)$, the beta function has the form

$$
\mu{dg\over d\mu}=\beta(g).
$$

For a dimensionful coupling $g_i$ with $[g_i]=d-\Delta_i$, the associated dimensionless coupling

$$
\tilde g_i(\mu)=g_i\mu^{\Delta_i-d}
$$

has beta function

$$
\mu{d\tilde g_i\over d\mu}=(\Delta_i-d)\tilde g_i+\text{quantum corrections}.
$$

The first term is dimensional analysis. The rest is dynamics.

## Dimensional transmutation

Sometimes a dimensionless coupling is traded for a dimensionful scale. This is **dimensional transmutation**. Suppose a marginal coupling has one-loop running

$$
\mu{dg\over d\mu}=-b_0g^3+O(g^5),
\qquad b_0>0.
$$

Then

$$
{d\over d\log\mu}{1\over g^2}=2b_0+O(g^0),
$$

so to leading order,

$$
{1\over g^2(\mu)}=2b_0\log {\mu\over\Lambda}.
$$

The integration constant $\Lambda$ has dimension one:

$$
\Lambda=\mu\exp\left[-{1\over 2b_0g^2(\mu)}\right]
$$

at this order. The classical theory started with a dimensionless coupling. The quantum theory contains a scale. This is one of the cleanest places where dimensional analysis says, “I see no mass scale,” and renormalization replies, “Give me a minute.”

The formula is also a preview of asymptotics and nonperturbative scales. The factor

$$
\exp\left[-{\text{const}\over g^2}\right]
$$

is invisible in an ordinary perturbative expansion around $g=0$.

## Naturalness and sensitivity to scales

Dimensional analysis is often used to express **naturalness**. The rough principle is: if a parameter is allowed by symmetries, and if heavy physics at scale $\Lambda_*$ couples to it, then its coefficient is expected to receive contributions of the size allowed by dimensions and symmetries.

For example, in four dimensions a scalar mass term has coefficient $m^2$ with dimension two:

$$
\mathcal L\supset -{1\over2}m^2\phi^2.
$$

If no symmetry protects $m^2$, dimensional analysis permits corrections of order

$$
\delta m^2\sim \Lambda_*^2
$$

in a cutoff description. By contrast, a fermion mass term

$$
m\bar\psi\psi
$$

can be protected by chiral symmetry: when $m=0$, the symmetry can be enhanced, so corrections are proportional to $m$ itself in suitable settings. Gauge boson masses are similarly constrained by gauge symmetry.

Naturalness is not a theorem that nature must obey. It is a diagnostic of sensitivity. It tells you which small numbers require symmetry, dynamics, boundary conditions, environmental selection, tuning, or some other explanation if you want them to remain small against heavy scales.

## Naive dimensional analysis

In EFT, one often writes an operator expansion as

$$
\mathcal L_{\text{eff}}=\sum_i c_i\Lambda_*^{d-\Delta_i}\mathcal O_i.
$$

The coefficients $c_i$ are dimensionless. A minimal power-counting estimate says $c_i$ should be order one unless symmetries, loops, weak couplings, selection rules, or strong dynamics say otherwise.

This is sometimes called **naive dimensional analysis**. The word “naive” is not an insult; it means that only dimensions and symmetry have been used. In strongly coupled four-dimensional theories, additional $4\pi$ factors are often inserted to estimate loop sizes. In weakly coupled EFTs, powers of small couplings and loop factors such as

$$
{1\over 16\pi^2}
$$

must be counted separately.

The useful habit is to write coefficients as

$$
\text{coefficient}=(\text{dimensionless number})\times(\text{required power of scale}).
$$

Then the physics question becomes: why is the dimensionless number large, small, zero, universal, or scheme-dependent?

## Multiple scales

Real QFT problems rarely have a single scale. A scattering amplitude might depend on

$$
E,
\quad m,
\quad \mu,
\quad \Lambda_*,
\quad T,
\quad L^{-1},
\quad |\mathbf p|,
$$

where $E$ is a process energy, $m$ a mass, $\mu$ a renormalization scale, $\Lambda_*$ a heavy threshold, $T$ a temperature, and $L$ a box size. Dimensional analysis says an observable $\mathcal A$ with dimension $\alpha$ can be written as

$$
\mathcal A=E^\alpha F\left({m\over E},{\mu\over E},{E\over\Lambda_*},{T\over E},{1\over EL},\ldots\right),
$$

provided $E$ is nonzero and appropriate for the kinematic region. The function $F$ is dimensionless, but it may contain logs, thresholds, branch cuts, anomalous powers, and nonanalyticities.

Dimensional analysis reduces the number of independent variables. It does not tell you the function $F$.

## Common pitfalls

**Treating dimensionless as scale independent.** A dimensionless coupling can run. Marginal operators are precisely the ones for which logarithms and beta functions matter most.

**Confusing canonical and anomalous dimensions.** Canonical dimensions come from kinetic terms. Scaling dimensions at an interacting fixed point include anomalous contributions. The difference is the difference between bookkeeping and dynamics.

**Taking cutoff powers too literally.** A hard cutoff may show $\Lambda^2$ or $\Lambda^4$ terms that are regulator-dependent. Their existence diagnoses sensitivity to local counterterms, not automatically an observable power-law divergence.

**Forgetting the measure.** In $d$ dimensions, $d^d x$ has dimension $-d$ and $d^d p$ has dimension $d$. Many factor-of-scale mistakes are measure mistakes wearing a fake mustache.

**Writing logarithms of dimensionful quantities.** Always ask what scale is hiding inside the logarithm: $\log(p^2/\mu^2)$, $\log(m^2/\mu^2)$, $\log(\Lambda^2/m^2)$, or something equivalent.

**Using one power-counting scheme everywhere.** Relativistic EFT, nonrelativistic EFT, chiral perturbation theory, heavy-particle EFT, soft-collinear effective theory, thermal EFT, and finite-density EFT count scales differently. Dimensions are universal; useful power counting is contextual.

**Assuming irrelevant means irrelevant to experiments.** Irrelevant operators are suppressed at low energies, but precision experiments are often searches for precisely those suppressed effects.

## Exercises

### Exercise 1: Scalar dimensions in arbitrary dimension

For a real scalar field with kinetic term $\frac12\partial_\mu\phi\partial^\mu\phi$ in $d$ spacetime dimensions, find $[\phi]$, $[m^2]$, and the dimension of the coupling $\lambda_n$ in

$$
\mathcal L\supset {\lambda_n\over n!}\phi^n.
$$

<details><summary><strong>Solution</strong></summary>

The kinetic term has dimension $d$:

$$
[\partial_\mu\phi\partial^\mu\phi]=2+2[\phi]=d.
$$

Thus

$$
[\phi]=\frac{d-2}{2}.
$$

The mass term $m^2\phi^2$ must have dimension $d$, so

$$
[m^2]+2[\phi]=d.
$$

Using $2[\phi]=d-2$ gives

$$
[m^2]=2.
$$

For $\lambda_n\phi^n$, we need

$$
[\lambda_n]+n[\phi]=d,
$$

so

$$
[\lambda_n]=d-n\frac{d-2}{2}.
$$

</details>

### Exercise 2: The upper critical dimension of phi to the n

For the interaction $\phi^n$ in a scalar theory, find the spacetime dimension $d_c$ where $\lambda_n$ is classically marginal.

<details><summary><strong>Solution</strong></summary>

Marginality means

$$
[\lambda_n]=0.
$$

From Exercise 1,

$$
0=d-n\frac{d-2}{2}.
$$

Solving,

$$
2d=n(d-2),
$$

so

$$
(n-2)d=2n,
$$

and therefore

$$
d_c={2n\over n-2}.
$$

For $n=4$, $d_c=4$. For $n=6$, $d_c=3$.

</details>

### Exercise 3: Four-fermion operators

In $d=4$, show that a four-fermion operator has coefficient dimension $-2$.

<details><summary><strong>Solution</strong></summary>

In four dimensions,

$$
[\psi]=\frac32.
$$

A four-fermion operator has dimension

$$
4[\psi]=4\cdot\frac32=6.
$$

Since the Lagrangian density has dimension $4$, the coefficient $G$ in

$$
\mathcal L\supset G(\bar\psi\Gamma\psi)(\bar\psi\Gamma\psi)
$$

has dimension

$$
[G]=4-6=-2.
$$

Thus $G$ is naturally written as $G\sim c/\Lambda_*^2$.

</details>

### Exercise 4: Superficial divergence

Estimate the UV degree of divergence of

$$
I_N=\int^\Lambda {d^4k\over(2\pi)^4}{k^{2N}\over(k^2+m^2)^3}.
$$

For which $N$ is the integral superficially convergent?

<details><summary><strong>Solution</strong></summary>

At large $k$,

$$
{ k^{2N}\over(k^2+m^2)^3}\sim k^{2N-6}.
$$

The measure $d^4k$ contributes $k^4$ in dimension counting, so the superficial degree of divergence is

$$
\omega=4+2N-6=2N-2.
$$

The integral is superficially convergent when

$$
\omega<0,
$$

so

$$
2N-2<0
\quad\Longrightarrow\quad
N<1.
$$

For nonnegative integer $N$, only $N=0$ is superficially convergent. For $N=1$, the integral is logarithmically divergent; for $N>1$, it has a power divergence.

</details>

### Exercise 5: Dimensionless ratios

Let an observable $\mathcal A(E,m,\Lambda_*)$ have mass dimension $2$. Suppose $E$ is the only external energy scale and $m,\Lambda_*$ are nonzero mass scales. Write the most general dimensional form using $E$ as the reference scale.

<details><summary><strong>Solution</strong></summary>

Since $\mathcal A$ has dimension $2$, factor out $E^2$. The remaining function must be dimensionless and can depend only on dimensionless ratios:

$$
\mathcal A(E,m,\Lambda_*)=E^2F\left({m\over E},{E\over\Lambda_*}\right).
$$

One could also use $m/\Lambda_*$ instead of one of these ratios, since only two independent ratios exist among three scales. The choice of reference scale is a convenience, not physics.

</details>

## References and further reading

For dimensional analysis and power counting in QFT, see Mark Srednicki, *Quantum Field Theory*; Steven Weinberg, *The Quantum Theory of Fields*, Vols. I and II; Matthew Schwartz, *Quantum Field Theory and the Standard Model*; A. Zee, *Quantum Field Theory in a Nutshell*; and Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.

For EFT power counting, naturalness, Wilsonian scaling, redundant operators, and matching, see C. P. Burgess, *Introduction to Effective Field Theory*; Howard Georgi's EFT lectures; and Weinberg's EFT discussions. For the renormalization-group viewpoint, see Wilson and Kogut, "The Renormalization Group and the $\epsilon$ Expansion," and modern QFT texts.

For dimensional analysis in geometry-heavy or condensed-matter settings, see Altland and Simons, *Condensed Matter Field Theory*; Fradkin, *Field Theories of Condensed Matter Physics*; and relevant EFT treatments adapted to nonrelativistic scaling.

## Version history

- 2026-06-26: First polished draft. Added mass-dimension conventions, canonical field dimensions, operator and coupling dimensions, relevance classification, four-dimensional tables, loop power counting, correlator scaling, logarithms, dimensional transmutation, naturalness, EFT estimates, common pitfalls, exercises with solutions, and scaling-flow figure.
