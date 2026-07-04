---
title: "Scalar Tree Amplitudes"
description: "A worked calculation of the first scalar two-to-two tree amplitudes from contact and exchange diagrams, including signs, factors of i, Mandelstam variables, and identical-particle caveats."
sidebar:
  label: "Scalar Tree Amplitudes"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§9–11; Coleman 2019, chs. 8, 10–12; Weinberg 1995, Vol. I, ch. 6; Schwartz 2014, ch. 7; Zee 2010, ch. I.7 and appendix C"
topics:
  - scalar field theory
  - tree amplitudes
  - Feynman rules
  - Mandelstam variables
  - two-to-two scattering
canonicalTopics:
  - scalar-tree-amplitudes
  - phi-four-scattering
  - phi-three-exchange
  - contact-and-exchange-diagrams
researchStatus:
  established:
    - "Tree-level scalar amplitudes from local contact vertices and exchange propagators are standard textbook applications of LSZ-reduced Feynman rules."
  active:
    - "The physical interpretation of tree amplitudes becomes subtler for massless fields, unstable particles, bound states, infrared-safe observables, and nonperturbative completions; those issues belong to later pages."
---

## Summary

This page computes the first tree-level $2\to2$ amplitudes in scalar field theory. In qft.org conventions,

$$
\langle f|iT|i\rangle
=
i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi},
$$

so a diagram calculation produces $i\mathcal M$.

For real scalar $\phi^4$ theory with

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

the tree-level four-point amplitude is simply

$$
{\mathcal M_{\phi^4,\rm tree}=-\lambda.}
$$

For a cubic scalar interaction

$$
\mathcal L_{\rm int}=-\frac{g}{3!}\phi^3,
$$

the connected tree-level $2\to2$ amplitude for identical external scalars is

$$
\mathcal M_{\phi^3,\rm tree}
=-g^2\left(
\frac{1}{s-m^2+i\epsilon}
+\frac{1}{t-m^2+i\epsilon}
+\frac{1}{u-m^2+i\epsilon}
\right).
$$

If both interactions are present around the chosen perturbative vacuum, the corresponding tree amplitude is the sum of the contact and exchange contributions.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![Contact and exchange diagrams for scalar two-to-two tree amplitudes](/figures/perturbative-qft/scalar-tree-amplitudes.svg)

<figcaption>

The basic scalar $2\to2$ tree diagrams are a local quartic contact diagram and three cubic-exchange diagrams. The internal momentum squared is $s$, $t$, or $u$ depending on the channel, so the exchange terms produce poles at $s=m^2$, $t=m^2$, or $u=m^2$ for an exchanged scalar of mass $m$.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/), and [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/).

## Core idea

Tree amplitudes are the first place where Feynman rules become physical scattering predictions. A connected tree diagram has no independent loop momentum. Once the external momenta are fixed, every internal momentum is fixed by momentum conservation, and the result is an algebraic function of the external invariants.

For scalar theories, this means:

| Diagram ingredient | Contribution to $i\mathcal M$ |
|---|---:|
| local quartic vertex | $-i\lambda$ |
| cubic vertex | $-ig$ |
| internal scalar line carrying $k$ | $\displaystyle \frac{i}{k^2-m^2+i\epsilon}$ |
| overall delta function | stripped into $i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M$ |

The $i$ bookkeeping matters. With the amplitude convention above, the contact diagram $-i\lambda$ means $\mathcal M=-\lambda$, not $\mathcal M=-i\lambda$.

## Setup and conventions

Consider a real scalar field with free Lagrangian

$$
\mathcal L_0
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2.
$$

External particles are on shell,

$$
p_i^2=m^2,
\qquad
p_i^0>0,
$$

and the physical process is

$$
\phi(p_1)+\phi(p_2)\to\phi(p_3)+\phi(p_4).
$$

We use

$$
s=(p_1+p_2)^2,
\qquad
 t=(p_1-p_3)^2,
\qquad
 u=(p_1-p_4)^2,
$$

with

$$
s+t+u=4m^2
$$

for identical external masses.

For an interaction term written as

$$
\mathcal L_{\rm int}\supset-\frac{g_n}{n!}\phi^n,
$$

the scalar $n$-point vertex is

$$
-i g_n.
$$

The factorial in the Lagrangian is part of the convention. It cancels the permutations of identical fields attached to the vertex. Do not add another $n!$ when using the Feynman rule.

:::note[About the cubic toy model]
A lone real $\phi^3$ potential is not globally stable as a classical potential. It is still an excellent local perturbative example for learning exchange diagrams, and the same formulas appear in stable multi-field theories with scalar mediators. The tree-level bookkeeping is the point here, not the global completion of the toy potential.
:::

## What tree level means

For a connected graph, the number of independent loop momenta is

$$
L=I-V+1,
$$

where $I$ is the number of internal lines and $V$ is the number of vertices. A tree diagram has

$$
L=0.
$$

Tree level does **not** mean “one vertex only.” A cubic exchange diagram has two vertices and one internal line, so

$$
L=1-2+1=0.
$$

It is still tree level. The absence of loop integrals is what matters.

## Quartic contact amplitude

Take

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4.
$$

The momentum-space quartic vertex is

$$
-i\lambda.
$$

There is one connected tree diagram for four external scalar particles: the contact diagram. Since the overall momentum-conservation delta function is stripped into the definition of $\mathcal M$, we have

$$
i\mathcal M_{\,\rm contact}=-i\lambda.
$$

Therefore

$$
{\mathcal M_{\,\rm contact}=-\lambda.}
$$

There is no additional factor of $4!$ in the amplitude. The $1/4!$ in the Lagrangian and the $4!$ Wick contractions that attach four labeled external fields to the four fields at the vertex have already combined into the vertex rule $-i\lambda$.

For identical final particles, there will later be a factor $1/2!$ in the phase-space integral for total rates or cross sections. That factor is **not** part of $\mathcal M$.

## Cubic exchange amplitude

Now take

$$
\mathcal L_{\rm int}=-\frac{g}{3!}\phi^3.
$$

The cubic vertex is

$$
-ig.
$$

At order $g^2$, the connected four-point tree diagrams have two cubic vertices joined by one internal scalar line. For identical external scalars, there are three channels.

### The s channel

In the $s$ channel, the internal momentum is

$$
k_s=p_1+p_2=p_3+p_4,
$$

so

$$
k_s^2=s.
$$

The diagram gives

$$
i\mathcal M_s
=(-ig)^2\frac{i}{s-m^2+i\epsilon}.
$$

Since $(-ig)^2=-g^2$, this is

$$
i\mathcal M_s
=-\frac{ig^2}{s-m^2+i\epsilon},
$$

and therefore

$$
{\mathcal M_s=-\frac{g^2}{s-m^2+i\epsilon}.}
$$

### The t and u channels

The $t$-channel internal momentum may be taken as

$$
k_t=p_1-p_3,
$$

so

$$
k_t^2=t.
$$

Similarly, the $u$-channel internal momentum may be taken as

$$
k_u=p_1-p_4,
$$

so

$$
k_u^2=u.
$$

The two contributions are

$$
{\mathcal M_t=-\frac{g^2}{t-m^2+i\epsilon},
\qquad
\mathcal M_u=-\frac{g^2}{u-m^2+i\epsilon}.}
$$

Adding the three tree diagrams gives

$$
\mathcal M_{\phi^3,\rm tree}
=-g^2\left(
\frac{1}{s-m^2+i\epsilon}
+\frac{1}{t-m^2+i\epsilon}
+\frac{1}{u-m^2+i\epsilon}
\right).
$$

For real physical kinematics away from poles, the infinitesimal $i\epsilon$ often stays implicit. It should not be forgotten when analytic continuation, unitarity, or pole prescriptions matter.

## Contact plus exchange

If the interaction contains both terms,

$$
\mathcal L_{\rm int}
=-\frac{g}{3!}\phi^3-\frac{\lambda}{4!}\phi^4,
$$

then, at tree level through order $\lambda$ and $g^2$,

$$
\mathcal M_{\rm tree}
=-\lambda
-g^2\left(
\frac{1}{s-m^2+i\epsilon}
+\frac{1}{t-m^2+i\epsilon}
+\frac{1}{u-m^2+i\epsilon}
\right).
$$

This formula illustrates the two basic analytic structures of tree amplitudes:

| Term | Analytic structure | Physical interpretation |
|---|---|---|
| $-\lambda$ | polynomial contact term | local interaction at one spacetime point |
| $-g^2/(s-m^2)$ | pole in $s$ | exchanged scalar in the $s$ channel |
| $-g^2/(t-m^2)$ | pole in $t$ | exchanged scalar in the $t$ channel |
| $-g^2/(u-m^2)$ | pole in $u$ | exchanged scalar in the $u$ channel |

At loop level, amplitudes develop logarithms, branch cuts, ultraviolet divergences, and imaginary parts. Tree amplitudes are the rational starting point.

## Distinguishable scalars and allowed channels

Identical scalar scattering often has all three exchange channels because any external leg can attach to any cubic vertex. With different species, the interaction terms decide which diagrams exist.

For example, let $\phi$ and $\chi$ be stable real scalars coupled to a mediator $\sigma$ of mass $M$ by

$$
\mathcal L_{\rm int}
=-\frac{g_\phi}{2}\sigma\phi^2
-\frac{g_\chi}{2}\sigma\chi^2.
$$

The process

$$
\phi\phi\to\chi\chi
$$

has an $s$-channel mediator exchange:

$$
i\mathcal M_s
=(-ig_\phi)(-ig_\chi)\frac{i}{s-M^2+i\epsilon},
$$

so

$$
\mathcal M(\phi\phi\to\chi\chi)
=-\frac{g_\phi g_\chi}{s-M^2+i\epsilon}.
$$

The process

$$
\phi\chi\to\phi\chi
$$

instead has a $t$-channel mediator exchange:

$$
\mathcal M(\phi\chi\to\phi\chi)
=-\frac{g_\phi g_\chi}{t-M^2+i\epsilon}.
$$

This is the cleanest way to remember channel denominators: first draw the allowed species flow, then square the internal momentum.

## Angular form for identical scalars

For equal-mass elastic scattering in the center-of-mass frame,

$$
t=-\frac{s-4m^2}{2}(1-\cos\theta),
\qquad
u=-\frac{s-4m^2}{2}(1+\cos\theta).
$$

Therefore the cubic-exchange amplitude can be written as

$$
\mathcal M_{\phi^3,\rm tree}(s,\theta)
=-g^2\left[
\frac{1}{s-m^2+i\epsilon}
+\frac{1}{-\frac{s-4m^2}{2}(1-\cos\theta)-m^2+i\epsilon}
+\frac{1}{-\frac{s-4m^2}{2}(1+\cos\theta)-m^2+i\epsilon}
\right].
$$

This form is useful for plotting angular dependence or inserting the amplitude into a differential cross-section formula. The amplitude itself is still most compactly written as $\mathcal M(s,t,u)$.

## Checks on the result

### Mass dimensions

In four spacetime dimensions,

$$
[\phi]=1.
$$

Thus

$$
[\lambda]=0,
\qquad
[g]=1.
$$

The quartic amplitude $-\lambda$ is dimensionless. The cubic exchange term $g^2/(s-m^2)$ is also dimensionless. This matches the fact that a four-dimensional $2\to2$ invariant amplitude is dimensionless in the standard normalization.

### Crossing and identical-particle symmetry

For identical real scalars, the amplitude must be symmetric under permutations of the external particles. In $2\to2$ language, exchanging the two outgoing particles sends

$$
p_3\leftrightarrow p_4,
\qquad
 t\leftrightarrow u.
$$

The contact amplitude is trivially symmetric. The cubic exchange amplitude is symmetric because it contains the sum of $s$, $t$, and $u$ exchange terms.

### Pole structure

Near an $s$-channel pole,

$$
s\to m^2,
$$

the cubic amplitude behaves as

$$
\mathcal M_{\phi^3,\rm tree}
\sim
-\frac{g^2}{s-m^2+i\epsilon}
+\text{terms regular in }s.
$$

This pole is the tree-level signature of a one-particle intermediate state. In a more general theory, the residue is the product of the lower-point couplings on the two sides of the pole. This factorization idea becomes central in unitarity methods and modern on-shell amplitudes.

## From amplitudes to observables

The invariant amplitude is not yet a cross section. For a two-body scattering process, the amplitude will later be inserted into the Lorentz-invariant phase-space formula. In the center-of-mass frame, the standard unpolarized $2\to2$ differential cross section has the schematic form

$$
\frac{d\sigma}{d\Omega}
=\frac{1}{64\pi^2s}\frac{|\mathbf p_f|}{|\mathbf p_i|}\,\overline{|\mathcal M|^2},
$$

with possible identical-final-state factors in integrated rates. This page focuses on $\mathcal M$; phase-space normalization and flux factors are treated in the phase-space chapter.

## Common pitfalls

**Reporting $i\mathcal M$ as $\mathcal M$.** The diagram gives $i\mathcal M$. With $\mathcal L_{\rm int}=-\lambda\phi^4/4!$, the contact diagram is $-i\lambda$, so $\mathcal M=-\lambda$.

**Adding an extra factorial to the vertex.** If the Lagrangian contains $-g_n\phi^n/n!$, the vertex is $-ig_n$. The factorial has already done its job.

**Omitting crossed diagrams for identical particles.** In real scalar $\phi^3$ theory, identical external scalars give $s$, $t$, and $u$ exchange diagrams. Keeping only the $s$ channel breaks the identical-particle symmetry of the amplitude.

**Putting final-state symmetry factors into the amplitude.** Identical-particle factors such as $1/2!$ belong in phase-space sums for rates or cross sections, not in the invariant amplitude itself.

**Treating internal momenta as on shell.** The internal line in a tree diagram carries momentum fixed by external kinematics, but it is generally off shell. The propagator denominator keeps track of how far it is from its pole.

**Forgetting species restrictions.** A channel exists only if the vertices are allowed by the Lagrangian. Mandelstam variables name possible kinematic channels; they do not override field content.

**Ignoring instability caveats for toy potentials.** A real cubic potential is useful perturbatively but not a stable standalone scalar potential. For physical models, use a stable completion or interpret the cubic term as an expansion around a chosen background.

## Relations to other pages

- [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) defines the $s,t,u$ variables used throughout this page.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) explains the diagram-to-integrand rules used here.
- [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/) explains why the factorials in scalar interaction terms lead to simple vertex rules.
- [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/) explains why amputated connected diagrams compute S-matrix elements.
- [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/) explains why the same four-point amplitude can be viewed in different physical channels.
- [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/) previews how tree amplitudes and loop imaginary parts fit into probability conservation.

## Research status

- **Established:** The scalar contact and exchange amplitudes on this page are textbook tree-level consequences of local interaction terms and LSZ-reduced Feynman rules.
- **Convention-dependent:** The signs and factors of $i$ follow qft.org's amplitude and Lagrangian conventions. Other books may define $\mathcal A=i\mathcal M$ or absorb signs differently.
- **More delicate:** Massless limits, unstable exchanged particles, threshold singularities, infrared-safe inclusive observables, and renormalized higher-order corrections require later tools.

## Exercises

### Exercise 1: Contact sign

For

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

use the vertex rule to compute $\mathcal M(\phi\phi\to\phi\phi)$ at tree level.

<details>
<summary><strong>Solution</strong></summary>

The quartic vertex is

$$
-i\lambda.
$$

There is one connected contact diagram, so

$$
i\mathcal M=-i\lambda.
$$

Therefore

$$
\mathcal M=-\lambda.
$$

The result contains no extra $4!$ because the interaction was written with $1/4!$.

</details>

### Exercise 2: Cubic exchange channels

For

$$
\mathcal L_{\rm int}=-\frac{g}{3!}\phi^3,
$$

compute the three tree-level exchange contributions to identical-scalar $2\to2$ scattering.

<details>
<summary><strong>Solution</strong></summary>

Each cubic vertex gives $-ig$, and each internal scalar line gives

$$
\frac{i}{k^2-m^2+i\epsilon}.
$$

The internal momentum squared is $s$, $t$, or $u$ in the three channels. Hence

$$
i\mathcal M_s=(-ig)^2\frac{i}{s-m^2+i\epsilon},
$$

$$
i\mathcal M_t=(-ig)^2\frac{i}{t-m^2+i\epsilon},
$$

$$
i\mathcal M_u=(-ig)^2\frac{i}{u-m^2+i\epsilon}.
$$

Since $(-ig)^2=-g^2$,

$$
\mathcal M_s=-\frac{g^2}{s-m^2+i\epsilon},
\qquad
\mathcal M_t=-\frac{g^2}{t-m^2+i\epsilon},
\qquad
\mathcal M_u=-\frac{g^2}{u-m^2+i\epsilon}.
$$

Adding the diagrams gives

$$
\mathcal M_{\rm tree}
=-g^2\left(
\frac{1}{s-m^2+i\epsilon}
+\frac{1}{t-m^2+i\epsilon}
+\frac{1}{u-m^2+i\epsilon}
\right).
$$

</details>

### Exercise 3: Equal-mass angular amplitude

Using

$$
t=-\frac{s-4m^2}{2}(1-\cos\theta),
\qquad
u=-\frac{s-4m^2}{2}(1+\cos\theta),
$$

write the $\phi^4+\phi^3$ tree amplitude as a function of $s$ and $\theta$.

<details>
<summary><strong>Solution</strong></summary>

The invariant amplitude is

$$
\mathcal M_{\rm tree}
=-\lambda
-g^2\left(
\frac{1}{s-m^2+i\epsilon}
+\frac{1}{t-m^2+i\epsilon}
+\frac{1}{u-m^2+i\epsilon}
\right).
$$

Substituting the equal-mass center-of-mass formulas gives

$$
\mathcal M_{\rm tree}(s,\theta)
=-\lambda
-g^2\left[
\frac{1}{s-m^2+i\epsilon}
+\frac{1}{-\frac{s-4m^2}{2}(1-\cos\theta)-m^2+i\epsilon}
+\frac{1}{-\frac{s-4m^2}{2}(1+\cos\theta)-m^2+i\epsilon}
\right].
$$

</details>

### Exercise 4: Mediator exchange

Let

$$
\mathcal L_{\rm int}
=-\frac{g_\phi}{2}\sigma\phi^2
-\frac{g_\chi}{2}\sigma\chi^2,
$$

where $\sigma$ has mass $M$. Compute the tree amplitude for $\phi\phi\to\chi\chi$.

<details>
<summary><strong>Solution</strong></summary>

The process proceeds through an $s$-channel $\sigma$ propagator. The two vertices are $-ig_\phi$ and $-ig_\chi$, and the propagator is

$$
\frac{i}{s-M^2+i\epsilon}.
$$

Thus

$$
i\mathcal M=(-ig_\phi)(-ig_\chi)\frac{i}{s-M^2+i\epsilon}
=-\frac{i g_\phi g_\chi}{s-M^2+i\epsilon}.
$$

Therefore

$$
\mathcal M(\phi\phi\to\chi\chi)
=-\frac{g_\phi g_\chi}{s-M^2+i\epsilon}.
$$

</details>

### Exercise 5: Dimension check

In four spacetime dimensions, show that both the $\phi^4$ contact amplitude and the $\phi^3$ exchange amplitude are dimensionless.

<details>
<summary><strong>Solution</strong></summary>

The scalar field has mass dimension

$$
[\phi]=1.
$$

Since the Lagrangian density has dimension $4$,

$$
\left[\frac{\lambda}{4!}\phi^4\right]=4
\quad\Longrightarrow\quad
[\lambda]=0,
$$

and

$$
\left[\frac{g}{3!}\phi^3\right]=4
\quad\Longrightarrow\quad
[g]=1.
$$

The contact amplitude is $-\lambda$, so it has dimension $0$. The exchange amplitude has terms of the form

$$
\frac{g^2}{s-m^2}.
$$

The numerator has dimension $2$ and the denominator has dimension $2$, so the ratio has dimension $0$.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§9–11, for interacting scalar field theory, scattering amplitudes, Feynman rules, and cross-section normalization.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 8, 10–12, for Wick diagrams, Feynman diagrams, scalar scattering, Mandelstam variables, and phase space.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 6, for the general derivation of Feynman rules and momentum-space amplitudes.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 7, for momentum-space Feynman rules and tree-level examples.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. I.7 and appendix C, for a compact diagrammatic introduction.

## Version history

- **2026-06-12:** Initial polished draft for the Tree-Level Scattering chapter. The page computes scalar contact and exchange amplitudes using the qft.org amplitude convention and the Mandelstam-variable page created in the same batch.
