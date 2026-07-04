---
title: "Superficial Degree of Divergence"
description: "A derivation and practical guide to power counting ultraviolet divergences in Feynman diagrams before cancellations and subtractions are applied."
sidebar:
  label: "Superficial Degree"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§12 and 18–19; Weinberg 1995, Vol. I, ch. 12; Coleman 2019, chs. 15–16 and 25; Schwartz 2014, chs. 15 and 21; Zinn-Justin 2021, chs. 8–9"
topics:
  - superficial degree of divergence
  - power counting
  - ultraviolet divergences
  - renormalizability
  - counterterms
canonicalTopics:
  - superficial-degree-of-divergence
  - ultraviolet-power-counting
  - renormalizability-by-power-counting
  - divergent-subgraph
  - local-counterterm
researchStatus:
  established:
    - "Superficial degree of divergence is the standard first diagnostic for ultraviolet behavior of Feynman integrals and for the local counterterms suggested by power counting."
  active:
    - "In realistic gauge theories and precision calculations, naive power counting must be combined with symmetries, regulator choices, subdivergence subtraction, infrared analysis, effective field theory, and computational reduction methods."
---

## Summary

The **superficial degree of divergence** of a Feynman graph is the power of loop momentum left over when all loop momenta are scaled uniformly large. It answers the first ultraviolet question:

$$
\text{How badly could this graph diverge at large loop momentum before cancellations are used?}
$$

For a scalar graph in $d$ spacetime dimensions, with $L$ loop integrations, $I$ internal scalar propagators, and $N_\partial(v)$ derivatives at vertex $v$, the superficial degree of divergence is

$$
D=dL-2I+\sum_v N_\partial(v).
$$

For a graph with boson propagators scaling as $1/\ell^2$, fermion propagators scaling as $1/\ell$, and derivative numerators from vertices, a common four-dimensional estimate is

$$
D=dL+\sum_v N_\partial(v)-2I_B-I_F.
$$

If $D<0$, the graph is superficially convergent. If $D=0$, it is superficially logarithmically divergent. If $D>0$, cutoff power counting suggests a power divergence. This is only the first test: symmetries can improve the behavior, dimensional regularization treats power divergences differently from cutoff regularization, and subdivergences can appear even when the whole graph is superficially convergent.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Superficial degree of divergence adds loop-measure powers and derivative powers, then subtracts propagator powers](/figures/perturbative-qft/superficial-degree-map.svg)

<figcaption>

Power counting estimates the large-momentum behavior of a graph. Loop measures add powers of momentum, propagators subtract powers, and derivative vertices or numerator algebra add powers. In four-dimensional scalar $\phi^4$ theory this reduces to $D=4-E$, so only two-point and four-point graphs are superficially divergent, although higher-point graphs may contain divergent subgraphs.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/), and [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/).

For the interpretation of local counterterms, review [Vertices and Propagators](/perturbative-qft/diagrammatics-feynman-rules/vertices-and-propagators/) and [Generating Functional Diagrams](/perturbative-qft/diagrammatics-feynman-rules/generating-functional-diagrams/).

## Core idea

A loop integral can diverge when loop momenta become large. To estimate this, scale all independent loop momenta together,

$$
\ell_r\mapsto \Lambda \ell_r,
\qquad
\Lambda\to\infty.
$$

Then count powers of $\Lambda$. In $d$ dimensions, each loop measure contributes

$$
\int d^d\ell_r \sim \Lambda^d.
$$

A scalar or gauge-boson propagator behaves like

$$
\frac{1}{\ell^2-m^2+i\epsilon}\sim \Lambda^{-2},
$$

while a fermion propagator behaves like

$$
\frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon}\sim \Lambda^{-1},
$$

because the numerator contributes one power of momentum. Derivative interactions and momentum-dependent vertices add powers of $\Lambda$.

The superficial degree $D$ is the net exponent. Schematically,

$$
\int^{\Lambda_{\rm UV}} d\ell\,\ell^{D-1}
\sim
\begin{cases}
\Lambda_{\rm UV}^{D}, & D>0,\\
\log\Lambda_{\rm UV}, & D=0,\\
\text{finite at large momentum}, & D<0.
\end{cases}
$$

The word “superficial” matters. This estimate does not know about cancellations, Ward identities, antisymmetry, equations of motion, scaleless integrals, or subdivergences. It is a first diagnostic, not a final verdict.

## Setup and conventions

We work with qft.org mostly-minus conventions and write loop integrals in $d$ spacetime dimensions. A scalar propagator scales at large momentum as

$$
D_F(\ell)=\frac{i}{\ell^2-m^2+i\epsilon}
\sim \ell^{-2}.
$$

A Dirac propagator scales as

$$
S_F(\ell)=\frac{i(\ell\!\!\!/+m)}{\ell^2-m^2+i\epsilon}
\sim \ell^{-1}.
$$

A vertex with $N_\partial$ derivatives contributes $N_\partial$ powers of momentum. Non-derivative scalar and Yukawa vertices have $N_\partial=0$. Gauge-theory vertices may carry momenta in their numerators, but gauge symmetry often forces cancellations that are not visible in the naive count.

Throughout this page, $D$ means ultraviolet superficial degree of divergence. It is not an infrared diagnostic.

## General power-counting formula

Suppose a graph has

| Symbol | Meaning |
|---|---|
| $L$ | number of independent loop momenta |
| $I_B$ | number of internal boson propagators scaling as $\ell^{-2}$ |
| $I_F$ | number of internal fermion propagators scaling as $\ell^{-1}$ |
| $N_\partial(v)$ | number of derivatives or explicit powers of momentum at vertex $v$ |

Then the naive large-momentum estimate is

$$
D=dL+\sum_v N_\partial(v)-2I_B-I_F.
$$

More generally, if propagator type $a$ scales as $\ell^{-\sigma_a}$ and there are $I_a$ internal lines of that type, then

$$
D=dL+\sum_v N_\partial(v)-\sum_a \sigma_a I_a.
$$

This formula is the ultraviolet version of dimensional bookkeeping. It does not compute the coefficient of the divergence. It only estimates the largest possible power of loop momentum.

## Scalar theory without derivative interactions

For a scalar theory with no derivative interactions, every internal propagator contributes $\ell^{-2}$ and vertices contribute no powers of loop momentum. Therefore

$$
D=dL-2I.
$$

For a connected graph,

$$
L=I-V+1,
$$

so

$$
D=d(I-V+1)-2I
=d+(d-2)I-dV.
$$

If the graph contains vertices of valence $n$ with multiplicity $V_n$, and has $E$ external scalar lines, then

$$
\sum_n nV_n=2I+E.
$$

Eliminating $I$ gives

$$
D=d-\frac{d-2}{2}E
+\sum_n V_n\left[\frac{d-2}{2}n-d\right].
$$

The mass dimension of the coupling $g_n$ multiplying $\phi^n/n!$ is

$$
[g_n]=d-\frac{d-2}{2}n.
$$

Therefore the previous formula can be written as

$$
D=d-\frac{d-2}{2}E-\sum_n V_n[g_n].
$$

This is the cleanest connection between power counting and renormalizability. Interactions with nonnegative coupling dimension do not make $D$ worse as the number of vertices grows. Interactions with negative coupling dimension generate worse and worse divergences at higher orders, requiring an infinite tower of counterterms in a general effective field theory.

## Example: φ⁴ theory in four dimensions

In $d=4$, the real scalar field has dimension

$$
[\phi]=1.
$$

For $\lambda\phi^4/4!$,

$$
[\lambda]=0.
$$

The scalar formula becomes

$$
D=4-E.
$$

Thus the superficial behavior depends only on the number of external legs:

| External legs $E$ | $D=4-E$ | Interpretation |
|---:|---:|---|
| $0$ | $4$ | vacuum energy divergences |
| $2$ | $2$ | mass and wavefunction counterterms can appear |
| $4$ | $0$ | coupling counterterm can appear |
| $6$ | $-2$ | superficially convergent as a whole |
| $E>6$ | $< -2$ | increasingly convergent as a whole |

The $E=2$ entry says that two-point functions can contain local divergences proportional to

$$
1,
\qquad
p^2,
$$

which correspond to mass and field-strength counterterms:

$$
\delta m^2\phi^2,
\qquad
\delta Z\,\partial_\mu\phi\partial^\mu\phi.
$$

The $E=4$ entry says that four-point functions can contain logarithmic local divergences proportional to

$$
\phi^4,
$$

which correspond to coupling renormalization.

The $E\ge6$ entries do not mean every six-point graph is finite without care. A six-point graph may contain a divergent two-point or four-point subgraph. They mean the overall graph is superficially convergent after its subdivergences are subtracted.

## Example: φ³ theory in six dimensions

In $d=6$, a scalar has dimension

$$
[\phi]=\frac{d-2}{2}=2.
$$

For $g\phi^3/3!$,

$$
[g]=6-3\cdot2=0.
$$

The scalar formula gives

$$
D=6-2E.
$$

Thus

| External legs $E$ | $D=6-2E$ | Interpretation |
|---:|---:|---|
| $2$ | $2$ | two-point divergences |
| $3$ | $0$ | cubic coupling divergences |
| $4$ | $-2$ | superficially convergent overall |

This is why $\phi^3$ theory in six dimensions is a useful pedagogical model of a perturbatively renormalizable scalar theory. It has a dimensionless coupling and nontrivial one-loop self-energy and vertex corrections, but the diagrammatics are simpler than in gauge theory.

## Derivative interactions and effective field theory

Derivative interactions add powers of loop momentum. For example, an operator schematically of the form

$$
\mathcal O_{n,k}\sim (\partial)^k\phi^n
$$

has coupling dimension

$$
[g_{n,k}]=d-k-\frac{d-2}{2}n.
$$

The scalar power-counting formula becomes

$$
D=d-\frac{d-2}{2}E-\sum_{n,k}V_{n,k}[g_{n,k}].
$$

If $[g_{n,k}]<0$, each insertion of this operator increases the superficial degree of divergence. That is not a disaster. It is the normal logic of effective field theory: higher-dimension operators are suppressed by a heavy scale, and loop calculations generate additional local operators compatible with the symmetries.

The distinction is conceptual:

| Theory type | Power-counting behavior |
|---|---|
| super-renormalizable | positive-dimension couplings; fewer divergent structures at high order |
| renormalizable | nonnegative-dimension couplings; finite list of counterterm structures |
| nonrenormalizable EFT | negative-dimension couplings; infinite tower organized by power counting |

“Nonrenormalizable” does not mean useless. It means the theory must be organized as an expansion in powers of energy over a cutoff or matching scale.

## Gauge theories and naive counting

Power counting in gauge theories starts the same way but ends with more structure. In QED in four dimensions, using photon propagators scaling as $\ell^{-2}$, fermion propagators scaling as $\ell^{-1}$, and no derivative at the electron-photon vertex, one finds

$$
D=4-E_A-\frac{3}{2}E_\psi,
$$

where $E_A$ is the number of external photons and $E_\psi$ is the number of external fermion lines.

This formula suggests the possible local structures, but gauge invariance and Ward identities improve and restrict the answer. For example, the photon two-point function is not allowed to generate a photon mass term in gauge-invariant QED. Its local divergence must have the transverse structure associated with

$$
F_{\mu\nu}F^{\mu\nu},
$$

not a general $A_\mu A^\mu$ term.

The moral is:

$$
\text{power counting tells us what could diverge; symmetry tells us what may actually appear.}
$$

## Subdivergences versus overall divergences

A graph can be superficially convergent as a whole and still contain divergent subgraphs. This is one of the first places where the word “superficial” earns its salary.

Suppose a two-loop six-point graph in four-dimensional $\phi^4$ theory has $E=6$. Its overall degree is

$$
D=4-6=-2,
$$

so the whole graph is superficially convergent. But it may contain a four-point one-loop subgraph. That subgraph has

$$
D_{\rm sub}=4-4=0,
$$

and is logarithmically divergent. The graph becomes finite only after the subdivergence is subtracted by the lower-order coupling counterterm.

Therefore the correct renormalization question is not just

$$
D(\Gamma)\ge0?
$$

but also

$$
D(\gamma)\ge0
\quad\text{for any subgraph }\gamma\subset\Gamma?
$$

Systematic renormalization algorithms subtract divergent subgraphs before interpreting the remaining overall divergence.

## What the degree does and does not say

The superficial degree of divergence is useful because ultraviolet divergences in local QFT are local in external momenta. If a graph has $D\ge0$, its divergent part is expected to be a polynomial in external momenta of degree at most $D$, subject to symmetries. That polynomial corresponds to a local counterterm.

For a scalar two-point graph in four dimensions with $D=2$, the local divergent part can have the form

$$
A\Lambda_{\rm UV}^2+Bp^2\log\Lambda_{\rm UV}+Cm^2\log\Lambda_{\rm UV}+\cdots,
$$

in a cutoff-like scheme. The local structures are

$$
\phi^2,
\qquad
\partial_\mu\phi\partial^\mu\phi.
$$

However, $D$ does not tell us:

| It does not determine | Why not |
|---|---|
| the coefficient of the divergence | requires doing the integral and numerator algebra |
| whether symmetry cancels the divergence | Ward identities, antisymmetry, and equations of motion can improve behavior |
| infrared behavior | large-momentum counting ignores soft and collinear regions |
| subdivergences | a graph with $D<0$ can contain divergent subgraphs |
| scheme dependence | cutoff and dimensional regularization represent power divergences differently |
| finite parts | finite terms are beyond superficial counting |

Use $D$ as a triage tool, not as a substitute for calculation.

## Common pitfalls

**Confusing superficial convergence with complete finiteness.** A graph with $D<0$ can contain divergent subgraphs. Subdivergence subtraction is a separate step.

**Forgetting numerator powers.** Derivative interactions, gauge vertices, spinor numerators, and tensor reductions can add powers of loop momentum.

**Ignoring symmetry improvements.** Gauge invariance, Lorentz invariance, chiral symmetry, supersymmetry, and discrete symmetries can forbid counterterms suggested by naive counting.

**Using ultraviolet counting for infrared problems.** Superficial degree of divergence concerns large loop momentum. Soft and collinear divergences require separate infrared analysis.

**Thinking dimensional regularization erases power counting.** Scaleless power-divergent integrals may vanish in dimensional regularization, but the allowed local counterterms and sensitivity to relevant operators remain part of the physics.

**Calling nonrenormalizable theories bad.** Negative-dimension couplings mean that infinitely many operators are needed for arbitrary precision at arbitrary energy. As EFTs with a cutoff and power counting, such theories are often the correct low-energy description.

## Relations to other pages

- [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/) defines loop number and loop momentum integrations.
- [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/) explains how local counterterms enter diagrams.
- [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/) identifies the graph classes most directly associated with self-energies and vertex functions.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) gives the momentum integrals whose large-momentum behavior is counted here.
- [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) is the natural complement on the infrared side, where soft and collinear singularities require physical observable definitions.
- The regularization pages following this one explain how cutoff and dimensional regularization make divergent loop integrals temporarily well defined.
- The Renormalization, RG, and EFT volume gives the conceptual home of renormalizability, Wilsonian power counting, and effective field theory.

## Research status

- **Established:** Superficial degree of divergence and power-counting renormalizability are standard textbook tools.
- **Active:** In modern calculations, power counting is refined by gauge symmetry, EFT operator bases, helicity methods, soft and collinear factorization, asymptotic expansions, and automated integral reduction.
- **Approximate:** Superficial counting estimates possible ultraviolet behavior. Actual divergences can be absent or improved by cancellations.
- **Scheme-dependent:** The distinction between logarithmic and power divergences is regulator-sensitive, although the need for local counterterms and the classification of operators by dimension are robust.

## Exercises

### Exercise 1: Scalar power counting

For a scalar theory with no derivative interactions, derive

$$
D=dL-2I.
$$

Then use $L=I-V+1$ and $\sum_n nV_n=2I+E$ to show

$$
D=d-\frac{d-2}{2}E-\sum_n V_n[g_n],
$$

where

$$
[g_n]=d-\frac{d-2}{2}n.
$$

<details>
<summary><strong>Solution</strong></summary>

Each loop measure contributes $d$ powers of momentum, and each scalar propagator contributes $-2$ powers. With no derivative interactions,

$$
D=dL-2I.
$$

For a connected graph,

$$
L=I-V+1,
\qquad
V=\sum_n V_n.
$$

Therefore

$$
D=d(I-V+1)-2I=d+(d-2)I-dV.
$$

The half-edge identity is

$$
\sum_n nV_n=2I+E,
$$

so

$$
I=\frac12\left(\sum_n nV_n-E\right).
$$

Substituting gives

$$
D=d-\frac{d-2}{2}E
+\sum_n V_n\left[\frac{d-2}{2}n-d\right].
$$

Since

$$
[g_n]=d-\frac{d-2}{2}n,
$$

we get

$$
D=d-\frac{d-2}{2}E-\sum_n V_n[g_n].
$$

</details>

### Exercise 2: φ⁴ theory in four dimensions

Use power counting to determine which connected $E$-point functions in four-dimensional $\phi^4$ theory are superficially divergent.

<details>
<summary><strong>Solution</strong></summary>

For $d=4$ and $\phi^4$ theory,

$$
[\lambda]=4-4\cdot\frac{4-2}{2}=0.
$$

The scalar power-counting formula becomes

$$
D=4-\frac{2}{2}E=4-E.
$$

Thus:

$$
E=0:\ D=4,
\qquad
E=2:\ D=2,
\qquad
E=4:\ D=0,
\qquad
E\ge6:\ D<0.
$$

So vacuum, two-point, and four-point graphs are superficially divergent. Higher-point graphs are superficially convergent as whole graphs, although they may contain divergent subgraphs.

</details>

### Exercise 3: φ³ theory in six dimensions

For scalar $\phi^3$ theory in $d=6$, show that

$$
D=6-2E.
$$

Which amplitudes are superficially divergent?

<details>
<summary><strong>Solution</strong></summary>

In $d=6$,

$$
[\phi]=\frac{6-2}{2}=2.
$$

The cubic coupling has dimension

$$
[g]=6-3\cdot2=0.
$$

Therefore the scalar formula gives

$$
D=6-\frac{6-2}{2}E=6-2E.
$$

The superficially divergent cases satisfy $D\ge0$:

$$
E=0:\ D=6,
\qquad
E=1:\ D=4,
\qquad
E=2:\ D=2,
\qquad
E=3:\ D=0.
$$

In a theory with a $\phi\mapsto-\phi$ symmetry this model would be absent, but ordinary $\phi^3$ theory allows odd-point functions. The physically important entries for renormalization of the standard cubic theory are the two-point and three-point structures, along with vacuum and tadpole-type terms depending on how the vacuum is defined.

</details>

### Exercise 4: QED power counting

In four-dimensional QED, let $E_A$ be the number of external photon lines and $E_\psi$ the number of external fermion lines. Use

$$
D=4L-2I_A-I_\psi,
$$

with

$$
2I_\psi+E_\psi=2V,
\qquad
2I_A+E_A=V,
\qquad
L=I_A+I_\psi-V+1,
$$

to show that

$$
D=4-E_A-\frac32E_\psi.
$$

<details>
<summary><strong>Solution</strong></summary>

Start with

$$
D=4L-2I_A-I_\psi.
$$

Using

$$
L=I_A+I_\psi-V+1,
$$

we get

$$
D=4(I_A+I_\psi-V+1)-2I_A-I_\psi
=2I_A+3I_\psi-4V+4.
$$

The vertex identities give

$$
I_\psi=V-\frac{E_\psi}{2},
\qquad
I_A=\frac{V-E_A}{2}.
$$

Substituting,

$$
D=2\left(\frac{V-E_A}{2}\right)
+3\left(V-\frac{E_\psi}{2}\right)-4V+4.
$$

The $V$ terms cancel, leaving

$$
D=4-E_A-\frac32E_\psi.
$$

This is the naive power-counting result. Ward identities and gauge invariance further restrict the actual local counterterms.

</details>

### Exercise 5: A derivative interaction

In four dimensions, consider a scalar operator

$$
\mathcal O=(\partial_\mu\phi\partial^\mu\phi)\phi^4.
$$

What is the mass dimension of its coupling, and what does that imply for power counting?

<details>
<summary><strong>Solution</strong></summary>

In four dimensions, $[\phi]=1$ and $[\partial_\mu]=1$. The operator contains six scalar fields and two derivatives, so

$$
[\mathcal O]=6\cdot1+2=8.
$$

The Lagrangian density has dimension four, so the coupling $c$ in $c\mathcal O$ has dimension

$$
[c]=4-8=-4.
$$

This is a negative-dimension coupling. Each insertion worsens the superficial degree of divergence by four powers compared with a dimensionless interaction. Such an operator is nonrenormalizable by power counting, but it is perfectly natural in an effective field theory as a term suppressed by a heavy scale, for example

$$
\frac{c_8}{\Lambda^4}(\partial_\mu\phi\partial^\mu\phi)\phi^4.
$$

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §§12 and 18–19, for dimensional analysis, higher-order corrections, and renormalizability.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 12, for power counting and renormalization structure.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 15–16 and 25, for counterterms, regularization, and renormalization logic.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 15 and 21, for regularization examples and renormalizability.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 8–9, for power counting, ultraviolet divergences, and renormalization.

## Version history

- **2026-06-12:** Initial polished draft for the Perturbative QFT and Scattering volume.
