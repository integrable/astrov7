---
title: "Momentum-Space Feynman Rules"
description: "How position-space Wick contractions become momentum-space propagators, vertex factors, conservation delta functions, loop integrals, and amputated scalar amplitudes."
sidebar:
  label: "Momentum-Space Rules"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§9–10 and §19; Coleman 2019, chs. 8 and 10; Weinberg 1995, Vol. I, §§6.1–6.3; Schwartz 2014, ch. 7; Zee 2010, app. C"
topics:
  - momentum-space Feynman rules
  - scalar field theory
  - propagators
  - vertex factors
  - momentum conservation
  - loop integrals
  - amputated amplitudes
canonicalTopics:
  - momentum-space-feynman-rules
  - scalar-feynman-rules
  - loop-momentum-routing
researchStatus:
  established:
    - "Momentum-space Feynman rules for perturbative scalar QFT, including propagators, vertex factors, momentum conservation, loop integration, and external-leg amputation, are textbook-standard."
  active:
    - "Advanced loop reduction, infrared subtraction, gauge-theory automation, and multi-loop amplitude computation are active computational and phenomenological subjects treated later in the volume."
---

## Summary

Momentum-space Feynman rules turn a diagram into an algebraic expression. For real scalar $\phi^4$ theory,

$$
\mathcal L
=
\frac12\partial_\mu\phi\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\lambda}{4!}\phi^4,
$$

the basic stripped rules are

| Diagrammatic object | Momentum-space factor |
|---|---|
| Internal scalar line carrying momentum $q$ | $\displaystyle \frac{i}{q^2-m^2+i\epsilon}$ |
| Quartic scalar vertex | $-i\lambda$ |
| Independent loop momentum $\ell$ | $\displaystyle \int\frac{d^4\ell}{(2\pi)^4}$ |
| Whole connected diagram | overall $(2\pi)^4\delta^{(4)}(\sum p_{\mathrm{ext}})$ |

The word **stripped** means that the overall momentum-conserving delta function has been removed from the object being reported. With qft.org scattering conventions, diagrams for an amputated scalar scattering process compute $i\mathcal M$ after stripping the overall delta function:

$$
\langle f|iT|i\rangle
=
i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

This page derives the rules from Fourier transforming position-space diagrams, explains momentum routing and loop counting, and separates Green-function rules from amputated-amplitude rules. That separation prevents many later mistakes with signs, external legs, and factors of $2\pi$.

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Perturbative Expansion](/perturbative-qft/diagrammatics-feynman-rules/perturbative-expansion/), and [Wick Theorem Recap](/perturbative-qft/diagrammatics-feynman-rules/wick-theorem-recap/). The Foundations page [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) explains the diagrammatic grammar, while [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) fixes the propagator convention used below.

## Core idea

A position-space diagram is an integral over vertex positions with one propagator for each line. Momentum-space rules come from inserting the Fourier representation of every propagator. Each vertex-position integral then produces a delta function enforcing four-momentum conservation at that vertex.

The algorithm is:

1. assign a momentum to each line;
2. assign a propagator to each internal line;
3. assign a vertex factor and a momentum-conservation delta function to each vertex;
4. use delta functions to eliminate internal line momenta;
5. strip the single remaining overall delta function if reporting an amplitude;
6. integrate over each independent loop momentum.

The only physics input is local translation invariance. The rest is bookkeeping.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 54rem;">

![Scalar momentum-space Feynman-rule ingredients: propagator, quartic vertex, and loop measure](/figures/perturbative-qft/momentum-space-scalar-rules.svg)

<figcaption>

The scalar momentum-space rules are the Fourier image of Wick contractions and local interaction vertices. A propagator carries a momentum, a quartic vertex conserves the incoming four-momenta, and each unfixed cycle momentum is integrated with $d^4\ell/(2\pi)^4$.

</figcaption>
</figure>

## Setup and conventions

We use the qft.org mostly-minus metric and Fourier transform

$$
f(x)=\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot x}\widetilde f(p),
\qquad
\widetilde f(p)=\int d^4x\,e^{ip\cdot x}f(x).
$$

The scalar propagator is

$$
D_F(x-y)
=
\int\frac{d^4q}{(2\pi)^4}
\frac{i\,e^{-iq\cdot(x-y)}}{q^2-m^2+i\epsilon}.
$$

External momenta in correlation functions are taken incoming by default. For an $n$-point connected momentum-space Green function, define the reduced correlator by

$$
\int \prod_{a=1}^n d^4x_a\,
 e^{i\sum_a p_a\cdot x_a}
G_{n,\mathrm{conn}}(x_1,\ldots,x_n)
=
(2\pi)^4\delta^{(4)}\!\left(\sum_{a=1}^n p_a\right)
\widetilde G_{n,\mathrm{conn}}(p_1,\ldots,p_n).
$$

The delta function is required by translation invariance. The reduced correlator $\widetilde G_{n,\mathrm{conn}}$ still includes external propagators unless we explicitly amputate them.

## From position space to momentum space

Consider the first-order connected four-point function in $\phi^4$ theory:

$$
G_{4,\mathrm{conn}}^{(1)}(x_1,x_2,x_3,x_4)
=
(-i\lambda)\int d^4z\,
\prod_{a=1}^4 D_F(x_a-z).
$$

Insert the Fourier representation of each propagator:

$$
D_F(x_a-z)
=
\int\frac{d^4q_a}{(2\pi)^4}
\frac{i\,e^{-iq_a\cdot(x_a-z)}}{q_a^2-m^2+i\epsilon}.
$$

The Fourier transform over the external points gives

$$
\int d^4x_a\,e^{ip_a\cdot x_a}e^{-iq_a\cdot x_a}
=(2\pi)^4\delta^{(4)}(p_a-q_a),
$$

so each external momentum fixes the line momentum attached to that insertion. The remaining vertex-position integral gives

$$
\int d^4z\,e^{iz\cdot(q_1+q_2+q_3+q_4)}
=(2\pi)^4\delta^{(4)}(q_1+q_2+q_3+q_4).
$$

Therefore

$$
\widetilde G_{4,\mathrm{conn}}^{(1)}(p_1,p_2,p_3,p_4)
=
(-i\lambda)
\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon}
$$

with the overall $(2\pi)^4\delta^{(4)}(p_1+p_2+p_3+p_4)$ stripped off.

The amputated four-point object removes the four external propagators. At tree level,

$$
i\mathcal A_4^{\mathrm{tree}}=-i\lambda.
$$

For scalar scattering with unit tree-level residue, this is the same diagrammatic factor that enters $i\mathcal M$.

## Unstripped and stripped rules

There are two equivalent ways to write momentum-space rules.

| Rule style | What each vertex carries | What the final answer carries | Best use |
|---|---|---|---|
| Unstripped | $-i\lambda(2\pi)^4\delta^{(4)}(\sum p_v)$ | all delta functions appear explicitly | deriving rules and checking $2\pi$ factors |
| Stripped | $-i\lambda$ | one overall $(2\pi)^4\delta^{(4)}(\sum p_{\mathrm{ext}})$ is understood or removed | practical amplitudes and loop integrals |

In the unstripped version, every internal line momentum is integrated over and every vertex has a delta function. In a connected diagram, all but one of the vertex delta functions are used to eliminate internal momenta. The remaining one enforces total momentum conservation.

The stripped version starts after this elimination. It is the version most often used for amplitudes: draw the diagram, multiply propagators and vertex factors, integrate over independent loop momenta, include symmetry factors and signs, and remember that the full matrix element contains the overall delta function.

:::caution[Delta-function convention]
When comparing two books, check whether their quoted diagram equals the full matrix element, the reduced Green function, $i\mathcal M$, or $\mathcal M$. Many apparent sign or $2\pi$ disagreements are just different choices about what has been stripped.
:::

## Practical scalar rules

For a connected scalar $\phi^4$ diagram in the stripped convention:

1. draw all topologically distinct diagrams with the required external legs and order in $\lambda$;
2. assign momenta to internal lines, with arbitrary but fixed orientations;
3. put $i/(q^2-m^2+i\epsilon)$ on each internal scalar line;
4. put $-i\lambda$ on each quartic vertex;
5. impose momentum conservation at vertices;
6. integrate each independent loop momentum with $\int d^4\ell/(2\pi)^4$;
7. multiply by the graph's symmetry factor and any signs from statistics;
8. include external propagators for Green functions, but not for amputated amplitudes.

For a scalar connected Green function, external insertions have propagators attached. For an amputated object, those external propagators are removed. For an S-matrix element, LSZ reduction additionally puts external momenta on shell and includes the appropriate one-particle residues and normalization conventions.

A useful scalar relation near tree level is

$$
\widetilde G_{n,\mathrm{conn}}(p_1,\ldots,p_n)
=
\left[\prod_{a=1}^n\frac{i}{p_a^2-m^2+i\epsilon}\right]
i\mathcal A_n(p_1,\ldots,p_n)
$$

with the overall delta function stripped. Beyond tree level, external propagators and residues are corrected, and LSZ tells us how to extract the physical amplitude.

## Worked example: cubic exchange

For a scalar theory with

$$
\mathcal L_{\mathrm{int}}=-\frac{g}{3!}\phi^3,
$$

the cubic vertex is $-ig$. The tree-level $s$-channel contribution to $2\to2$ scattering has two cubic vertices and one internal propagator. If $P=p_1+p_2$ is the momentum through the internal line, then

$$
 i\mathcal M_s
=
(-ig)^2\frac{i}{P^2-m^2+i\epsilon}.
$$

There are analogous $t$- and $u$-channel contributions when the external particles are identical and the corresponding diagrams are allowed. This example is a good reminder that the propagator denominator knows about the channel invariant carried by the internal line.

## Worked example: one-loop fish in scalar theory

In $\phi^4$ theory, the one-loop four-point fish diagram has two quartic vertices and two internal lines. In the $s$ channel, with $P=p_1+p_2$, the stripped contribution has the form

$$
 i\mathcal M_s^{\mathrm{1-loop}}
=
\frac12(-i\lambda)^2
\int\frac{d^4\ell}{(2\pi)^4}
\frac{i}{\ell^2-m^2+i\epsilon}
\frac{i}{(\ell+P)^2-m^2+i\epsilon}.
$$

The factor $1/2$ is the symmetry factor of this diagram. The integral is ultraviolet divergent in four-dimensional $\phi^4$ theory and requires a regulator. The rule still tells us the integrand; renormalization tells us how to interpret the divergent result.

## Momentum routing and loop counting

For a connected graph with $I$ internal lines and $V$ vertices, the number of independent loop momenta is

$$
{L=I-V+1.}
$$

Reason: assign one momentum to each internal line. Vertex momentum conservation gives $V$ delta functions, but one of them is the overall conservation law and does not eliminate an internal momentum. Thus there are $V-1$ independent constraints on $I$ internal momenta, leaving

$$
I-(V-1)=I-V+1.
$$

Momentum routing is not unique. Different choices of loop variables describe the same integral when the regulator respects momentum shifts, as in dimensional regularization. With a hard cutoff, shifts of divergent loop momenta can change intermediate expressions, so one must define the regulator and routing consistently.

## Derivative interactions, spin, and gauge fields

The scalar rules above are the cleanest laboratory. The generalization is conceptually simple but notationally heavier.

| Feature | Momentum-space effect |
|---|---|
| Derivative interaction | each derivative acting on a Fourier mode gives a momentum factor |
| Dirac field | propagators and external legs carry spinor indices; signs track fermion permutations |
| Vector field | propagators and vertices carry Lorentz indices and gauge-fixing dependence |
| Non-Abelian gauge field | vertices carry Lorentz and color tensors; ghosts appear after gauge fixing |
| Composite operator insertion | the insertion is treated as an extra marked vertex with its own momentum flow |

Later pages develop these cases separately. The safest habit is to derive the rule once from the Lagrangian and Fourier convention, then use the compact diagrammatic version only after the signs and index placements are fixed.

## Common pitfalls

**Forgetting what has been stripped.** A full matrix element includes an overall momentum-conserving delta function. A reduced amplitude or reduced Green function usually has that factor removed.

**Mixing Green-function and S-matrix rules.** External legs in a time-ordered Green function are propagators. External legs in an amputated amplitude have been removed, and external legs in an S-matrix element are on-shell states extracted by LSZ.

**Changing Fourier conventions mid-calculation.** The sign in $e^{-ip\cdot x}$ fixes the sign of momentum factors from derivatives and the form of vertex delta functions. A convention swap without a full translation is a reliable way to create fake sign errors.

**Treating momentum arrows as physical motion.** Internal line momentum orientation is a bookkeeping choice. Reversing a scalar line momentum changes labels, not physics.

**Shifting divergent loop momenta casually.** In convergent integrals, momentum shifts are harmless. In divergent integrals, the regulator decides which shifts are legitimate at intermediate stages.

**Dropping symmetry factors at loops.** Momentum-space rules do not automatically remove every graph automorphism. If multiple Wick contractions give the same unlabeled loop graph, a symmetry factor may remain.

## Relations to other pages

- [Wick Theorem Recap](/perturbative-qft/diagrammatics-feynman-rules/wick-theorem-recap/) explains the contraction counting behind propagators and symmetry factors.
- [Perturbative Expansion](/perturbative-qft/diagrammatics-feynman-rules/perturbative-expansion/) explains why interaction vertices arise from expanding the action or Dyson operator.
- [Conventions and Notation](/perturbative-qft/conventions/) fixes the amplitude normalization and Fourier conventions used here.
- [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/) gives the first bridge from correlators with external propagators to amputated scattering amplitudes.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) derives the line factor whose Fourier transform is used throughout this page.

## Research status

The scalar momentum-space rules on this page are settled textbook perturbative QFT. Their use in loop calculations requires a regulator and renormalization prescription, and their gauge-theory generalizations require gauge fixing, ghosts, Ward identities or Slavnov–Taylor identities, and careful distinction between gauge-dependent intermediate quantities and physical observables. Modern amplitude methods often reorganize or bypass ordinary Feynman diagrams, but they must reproduce the same perturbative S-matrix where both descriptions apply.

## Exercises

### Exercise 1: Fourier transform the contact graph

Starting from

$$
G_{4,\mathrm{conn}}^{(1)}(x_1,x_2,x_3,x_4)
=
(-i\lambda)\int d^4z\,\prod_{a=1}^4D_F(x_a-z),
$$

show that the reduced momentum-space correlator is

$$
\widetilde G_{4,\mathrm{conn}}^{(1)}(p_1,p_2,p_3,p_4)
=
(-i\lambda)\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon}.
$$

<details>
<summary><strong>Solution</strong></summary>

Insert

$$
D_F(x_a-z)=\int\frac{d^4q_a}{(2\pi)^4}\frac{i e^{-iq_a\cdot(x_a-z)}}{q_a^2-m^2+i\epsilon}.
$$

The external Fourier transforms give

$$
\int d^4x_a\,e^{ip_a\cdot x_a}e^{-iq_a\cdot x_a}
=(2\pi)^4\delta^{(4)}(p_a-q_a),
$$

so $q_a=p_a$. The $z$ integral gives

$$
(2\pi)^4\delta^{(4)}(p_1+p_2+p_3+p_4).
$$

After stripping this overall delta function, the remaining factor is

$$
(-i\lambda)\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon}.
$$

</details>

### Exercise 2: Amputate the contact graph

Using the result of Exercise 1, compute the tree-level amputated four-point factor in $\phi^4$ theory.

<details>
<summary><strong>Solution</strong></summary>

The connected Green function factorizes as

$$
\widetilde G_{4,\mathrm{conn}}^{(1)}
=
\left[\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon}\right]i\mathcal A_4.
$$

Comparing with Exercise 1 gives

$$
i\mathcal A_4=-i\lambda.
$$

Thus, at tree level with unit scalar residue, the corresponding diagram contributes $i\mathcal M=-i\lambda$ to the scattering amplitude.

</details>

### Exercise 3: Loop counting for the fish diagram

The $\phi^4$ fish diagram has two quartic vertices connected by two internal lines. Use $L=I-V+1$ to find the number of loop integrals.

<details>
<summary><strong>Solution</strong></summary>

For the fish diagram,

$$
I=2,
\qquad
V=2.
$$

Therefore

$$
L=I-V+1=2-2+1=1.
$$

The diagram has one independent loop momentum and therefore one measure

$$
\int\frac{d^4\ell}{(2\pi)^4}.
$$

</details>

### Exercise 4: Cubic exchange channels

For $\mathcal L_{\mathrm{int}}=-g\phi^3/3!$, write the three tree-level exchange contributions to identical scalar $2\to2$ scattering using Mandelstam variables $s$, $t$, and $u$.

<details>
<summary><strong>Solution</strong></summary>

Each cubic vertex contributes $-ig$, and each internal scalar line contributes $i/(Q^2-m^2+i\epsilon)$. Therefore

$$
i\mathcal M_s=(-ig)^2\frac{i}{s-m^2+i\epsilon},
$$

$$
i\mathcal M_t=(-ig)^2\frac{i}{t-m^2+i\epsilon},
$$

and

$$
i\mathcal M_u=(-ig)^2\frac{i}{u-m^2+i\epsilon}.
$$

For identical external scalars, the tree amplitude is the sum of the allowed $s$-, $t$-, and $u$-channel diagrams.

</details>

### Exercise 5: Check dimensions in four-dimensional scalar theory

In four spacetime dimensions, use $[\phi]=1$ to find $[\lambda]$ in $\lambda\phi^4/4!$ and $[g]$ in $g\phi^3/3!$. Then check the mass dimension of the tree-level $\phi^4$ amplitude.

<details>
<summary><strong>Solution</strong></summary>

The Lagrangian density has mass dimension $4$. Since $[\phi]=1$,

$$
[\lambda]+4[\phi]=4
\quad\Rightarrow\quad
[\lambda]=0.
$$

For the cubic coupling,

$$
[g]+3[\phi]=4
\quad\Rightarrow\quad
[g]=1.
$$

The tree-level $\phi^4$ amplitude has

$$
i\mathcal M=-i\lambda,
$$

so $\mathcal M$ is dimensionless in four dimensions, as expected for a renormalizable quartic scalar coupling.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§9–10 and §19, for scalar Feynman rules and perturbation theory to all orders.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 8 and 10, for Wick diagrams, Feynman diagrams, and scalar scattering examples.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 7, for momentum-space Feynman rules and examples.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§6.1–6.3, for a general derivation of coordinate- and momentum-space Feynman rules.
- A. Zee, *Quantum Field Theory in a Nutshell*, app. C, for compact Feynman-rule summaries.
- R. P. Feynman, “Space-Time Approach to Quantum Electrodynamics,” *Physical Review* **76** (1949), 769–789, for the original diagrammatic viewpoint in QED.

## Version history

- **2026-06-11:** Initial standardized page.
