---
title: "What Counts as a Holographic CFT?"
description: "Criteria for when a conformal field theory has a useful AdS dual, from exact quantum gravity to weakly curved local bulk effective field theory."
sidebar:
  order: 10
---

The previous units treated AdS/CFT mostly through controlled examples: D3-branes, $\mathrm{AdS}_5\times S^5$, large-$N$ gauge theory, the GKPW prescription, black branes, Witten diagrams, and holographic entanglement. It is now time to ask a sharper question.

When should a CFT be called *holographic*?

There is a dangerous answer and a useful answer. The dangerous answer is: “a holographic CFT is any CFT with a gravity dual.” That sentence sounds clean, but it hides almost all of the physics. A generic CFT, even if it admits some formal AdS description, need not have a weakly curved spacetime, local bulk fields, an Einstein action, or a small number of light particles. The useful answer is layered:

1. A CFT may define a full quantum theory with asymptotically AdS boundary conditions.
2. A stronger class of CFTs has a large-$N$ or large-central-charge expansion, so the bulk has weak quantum loops.
3. An even stronger class has a sparse single-trace spectrum, so the bulk is local below the AdS scale.
4. The strongest and most commonly used class has a large gap to stringy and higher-spin states, so the low-energy bulk is approximately Einstein gravity plus a finite number of matter fields.

This page explains these layers. The goal is not to give a mathematically complete classification of holographic CFTs; no such classification is known. The goal is to give a reliable diagnostic checklist for students reading holography papers.

<figure class="doc-figure" style="--figure-width: 56rem;">

![A layered diagnostic map for holographic CFTs.](/figures/course/holographic-cft-criteria.svg)

<figcaption>

A practical hierarchy. A local unitary CFT with a stress tensor is not automatically Einstein-like. Large $c_T$ gives a small bulk Newton constant; large-$N$ factorization gives weak bulk interactions; a large single-trace gap $\Delta_{\rm gap}$ gives local bulk effective field theory; an Einstein-like regime additionally has no light higher-spin/stringy tower below the cutoff.

</figcaption>
</figure>

## The word “holographic” has several meanings

In this course, we will use three levels of precision.

### Level 1: exact AdS/CFT

At the strongest conceptual level, AdS/CFT is an equality of quantum theories:

$$
Z_{\rm CFT}[\text{sources}]
=
Z_{\rm bulk}[\text{boundary conditions}] .
$$
The bulk side is not necessarily classical gravity. It may be full string theory or M-theory in an asymptotically AdS spacetime. At this level, “holographic” means that the CFT is a non-gravitational definition of a quantum gravitational theory with AdS boundary conditions.

This level is the most ambitious and the least algorithmic. Given a random CFT, we usually do not know how to write its exact bulk dual. Even when a bulk dual exists, it may be as complicated as the original CFT.

### Level 2: semiclassical AdS gravity

A more useful working definition is:

> A CFT is semiclassically holographic if its observables admit a large parameter expansion that maps to weak bulk quantum loops.

The parameter is often $N$, but in abstract CFT language it is better to use the stress-tensor two-point normalization $c_T$. In a holographic CFT,

$$
c_T \sim \frac{L^{d-1}}{G_{d+1}},
$$
where $L$ is the AdS radius and $G_{d+1}$ is the bulk Newton constant. Thus

$$
c_T \gg 1
\quad \Longleftrightarrow \quad
G_{d+1} \ll L^{d-1}.
$$
Large $c_T$ means the AdS radius is large in Planck units. That is the bulk meaning of weak gravitational loop effects.

### Level 3: local bulk effective field theory

Semiclassicality is not enough. A bulk can have weak quantum loops but still fail to look like local Einstein gravity below the AdS scale. Local bulk effective field theory also requires a large gap in the spectrum of single-trace operators.

Let $\Delta_{\rm gap}$ denote the dimension of the lightest single-trace operator whose spin or internal quantum numbers indicate stringy, higher-spin, or otherwise non-Einstein degrees of freedom. A local bulk EFT requires

$$
\Delta_{\rm gap} \gg 1.
$$
The reason is the mass-dimension relation. For a heavy bulk field in $\mathrm{AdS}_{d+1}$,

$$
\Delta \sim mL .
$$
So a large operator dimension means a heavy bulk particle in AdS units. If all unwanted higher-spin or stringy states satisfy $mL\gg1$, then they can be integrated out when studying physics at energies $E\ll m$. The remaining light fields are governed by a local derivative expansion.

### Level 4: Einstein-like gravity

The most restrictive and most familiar class is the one used in simple black-brane, hydrodynamic, and entanglement calculations. Such a CFT has a bulk description of the form

$$
S_{\rm bulk}
=
\frac{1}{16\pi G_{d+1}}
\int d^{d+1}x\sqrt{-g}
\left(
R + \frac{d(d-1)}{L^2}
\right)
+
S_{\rm matter}
+
S_{\rm higher\;derivative} .
$$
The higher-derivative terms are suppressed by powers of the gap:

$$
S_{\rm higher\;derivative}
\sim
\sum_k
\frac{L^{2k}}{\Delta_{\rm gap}^{2k}}
\int \sqrt{-g}\, \mathcal R^{k+1}
+
\cdots .
$$
In this regime, black holes, minimal surfaces, hydrodynamic modes, and Witten diagrams behave like ordinary low-energy gravity phenomena.

## The CFT data behind the bulk

A CFT is specified by its spectrum of primary operators and their OPE coefficients. Schematically, the data are

$$
\left\{ \Delta_a, \ell_a, C_{abc} \right\}.
$$
Here $\Delta_a$ is the scaling dimension, $\ell_a$ is spin, and $C_{abc}$ are three-point coefficients. Four- and higher-point functions are then constrained by crossing symmetry and the operator product expansion.

In a holographic CFT, this same data is reinterpreted as bulk physics:

| CFT data | Bulk interpretation |
|---|---|
| primary operator $\mathcal O_a$ | single-particle field $\phi_a$ if single-trace |
| dimension $\Delta_a$ | AdS mass $m_a$ |
| spin $\ell_a$ | bulk spin |
| OPE coefficient $C_{abc}$ | cubic coupling among bulk fields |
| connected four-point data | exchange diagrams and contact interactions |
| large $c_T$ | weak bulk quantum gravity |
| large gap $\Delta_{\rm gap}$ | local bulk EFT below the gap |

The word “single-trace” is borrowed from large-$N$ gauge theory, but the abstract meaning is broader: single-trace operators are the primitive operators whose correlators behave like single-particle states in the bulk. Multi-trace operators correspond to multiparticle states.

## Criterion 1: a stress tensor and conformal symmetry

A CFT dual to gravity must have a conserved stress tensor $T_{ij}$. The source for $T_{ij}$ is the boundary metric $g_{(0)ij}$, and the bulk dual of $T_{ij}$ is the graviton.

The stress-tensor two-point function has a normalization conventionally written as

$$
\langle T_{ij}(x) T_{kl}(0)\rangle
=
\frac{c_T}{x^{2d}}
\mathcal I_{ij,kl}(x),
$$
where $\mathcal I_{ij,kl}(x)$ is fixed by conformal symmetry. The coefficient $c_T$ counts degrees of freedom in a way that is meaningful for any CFT dimension $d$.

In a classical bulk limit,

$$
c_T \propto \frac{L^{d-1}}{G_{d+1}}.
$$
This statement is the gravitational version of the fact that stress-tensor fluctuations become small when the number of degrees of freedom is large.

A CFT with small $c_T$ may still be perfectly consistent. It simply should not be expected to have a weakly coupled semiclassical bulk metric.

## Criterion 2: large-$N$ factorization

The next property is factorization. For normalized single-trace operators with two-point functions of order one, a holographic large-$N$ CFT has

$$
\langle \mathcal O_1 \mathcal O_2\rangle_c \sim N^0,
$$
$$
\langle \mathcal O_1 \mathcal O_2 \mathcal O_3\rangle_c \sim \frac{1}{N},
$$
and more generally

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_c
\sim
N^{2-n}.
$$
Equivalently, since $c_T\sim N^2$ in many gauge-theory examples,

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_c
\sim
c_T^{1-n/2}.
$$
This is the CFT version of weak bulk interactions. A connected $n$-point function is a process where $n$ single-particle bulk excitations interact. If the connected correlator is suppressed, the bulk particles are weakly coupled.

Factorization also explains why multi-trace operators have approximately additive dimensions. If $\mathcal O_a$ and $\mathcal O_b$ are single-trace primaries, then at leading order one expects double-trace operators of schematic form

$$
[\mathcal O_a \mathcal O_b]_{n,\ell}
\sim
\mathcal O_a \, \partial^{2n}\partial_{\{i_1}\cdots \partial_{i_\ell\}} \, \mathcal O_b
+
\cdots,
$$
with dimensions

$$
\Delta_{ab,n,\ell}
=
\Delta_a+
\Delta_b+2n+\ell+\gamma_{ab,n,\ell},
$$
where

$$
\gamma_{ab,n,\ell}=O(1/N^2).
$$
The anomalous dimensions $\gamma_{ab,n,\ell}$ are caused by weak bulk interactions.

## Criterion 3: sparse single-trace spectrum

Large $N$ by itself does not imply Einstein gravity. The CFT must also have a sparse spectrum of light single-trace operators.

Why? Because every light single-trace operator corresponds to a light bulk field. If there are infinitely many light single-trace operators with spins and dimensions of order one, the bulk is not described by a finite collection of low-energy fields. It may instead be stringy, higher-spin, or nonlocal on the AdS scale.

A sparse holographic CFT has only finitely many single-trace operators below some large gap:

$$
\Delta_{\rm light} = O(1),
\qquad
\Delta_{\rm gap} \gg 1.
$$
This gap controls the bulk derivative expansion. Integrating out heavy fields produces local higher-derivative terms suppressed by powers of $1/\Delta_{\rm gap}$.

A good mental model is:

$$
\frac{\ell_{\rm string}}{L}
\sim
\frac{1}{\Delta_{\rm gap}}.
$$
In the canonical $\mathcal N=4$ SYM example at large 't Hooft coupling,

$$
\Delta_{\rm stringy} \sim \lambda^{1/4},
$$
so the string tower becomes heavy in AdS units when $\lambda\gg1$.

## Criterion 4: no light higher-spin currents

A conserved spin-$s$ current has dimension

$$
\Delta = d-2+s.
$$
For $s=1$ this is an ordinary global symmetry current, and for $s=2$ it is the stress tensor. But conserved currents with spin $s>2$ are extremely constraining. In holography they correspond to massless higher-spin gauge fields in AdS.

This does not mean the CFT is inconsistent. It means the bulk is not ordinary Einstein gravity. Large-$N$ vector models, for example, are naturally associated with higher-spin gravitational theories rather than weakly curved Einstein gravity with a finite number of light fields.

An Einstein-like holographic CFT should not have an infinite tower of light higher-spin conserved or nearly conserved currents. If such a tower is present, the bulk derivative expansion is not the one used in the simplest AdS/CFT calculations.

## Criterion 5: crossing symmetry and causality consistency

A candidate holographic CFT must still be a consistent CFT. Its correlators must obey crossing symmetry, unitarity, reflection positivity in Euclidean signature, and Lorentzian causality.

This is not a decorative condition. It is what protects the bulk from acausal interactions. For example, a bulk theory with arbitrary higher-derivative graviton couplings can produce boundary correlators that violate causality or energy-positivity constraints. The CFT does not allow arbitrary low-energy gravitational actions.

The modern lesson is:

$$
\text{bulk EFT consistency}
\quad \Longleftrightarrow \quad
\text{CFT crossing, unitarity, positivity, and causality}.
$$
This is why holography is not just a convenient calculator. It is a bridge between quantum consistency of CFT data and consistency of quantum gravity.

## A diagnostic checklist

When you encounter a proposed holographic CFT, ask the following questions.

### 1. What is the large parameter?

Is there a rank $N$, a central charge $c$, a stress-tensor coefficient $c_T$, or another quantity that can be taken large?

A classical bulk limit requires something like

$$
c_T \gg 1.
$$
Without this, bulk quantum loops are not suppressed.

### 2. What are the single-trace operators?

In a gauge theory, single-trace operators often have the form

$$
\operatorname{Tr}(X_1X_2\cdots X_k).
$$
In a more abstract CFT, “single-trace” means “single-particle-like” in the large-$N$ expansion. Identify the primitive sector before interpreting the spectrum geometrically.

### 3. Is there a large gap?

Check whether the CFT has a parametrically large gap to higher-spin or stringy single-trace operators:

$$
\Delta_{\rm gap} \gg 1.
$$
No large gap means no simple local Einstein-like bulk below the AdS scale.

### 4. Are correlators sparse and factorized?

Do connected $n$-point functions scale like powers of $1/N$ or $1/c_T$? If not, the bulk is not weakly coupled.

### 5. Are there light higher-spin currents?

If yes, expect a higher-spin theory or a stringy/tensionless regime, not ordinary Einstein gravity.

### 6. Is the theory top-down or bottom-up?

A top-down model comes from a controlled string/M-theory construction. A bottom-up model is a useful gravitational EFT motivated by desired CFT features. Both can be valuable, but their evidentiary status is different.

## Examples and non-examples

### Strongly coupled $\mathcal N=4$ SYM at large $N$
This is the canonical Einstein-like example. At large $N$ and large $\lambda$,

$$
\frac{L^3}{G_5} \sim N^2,
\qquad
\Delta_{\rm stringy} \sim \lambda^{1/4} \gg 1.
$$
The bulk is type IIB string theory on $\mathrm{AdS}_5\times S^5$, whose low-energy limit is classical supergravity.

### Weakly coupled $\mathcal N=4$ SYM at large $N$
This theory still has a large-$N$ expansion, but the string scale is not separated from the AdS scale. The bulk is highly stringy. It is not well described by classical Einstein gravity.

### Large-$N$ vector models

Vector models can have a large-$N$ expansion, but they typically contain an infinite tower of nearly conserved higher-spin currents. Their natural bulk duals, when available, are higher-spin theories rather than ordinary Einstein gravity.

### A generic CFT with large central charge

Large $c_T$ alone is not enough. Without factorization and a sparse spectrum, a large central charge does not guarantee a local semiclassical bulk.

### ABJM theory in an appropriate regime

Three-dimensional ABJM theory provides a major holographic example beyond $\mathrm{AdS}_5/\mathrm{CFT}_4$. Depending on the scaling of $N$ and the Chern–Simons level $k$, the bulk is M-theory on $\mathrm{AdS}_4\times S^7/\mathbb Z_k$ or type IIA string theory on $\mathrm{AdS}_4\times \mathbb{CP}^3$.

This is an important reminder: holographic CFTs need not be four-dimensional gauge theories.

## Large gap versus strong coupling

In $\mathcal N=4$ SYM, the large gap is controlled by strong 't Hooft coupling. This sometimes leads to a misleading slogan:

> Strong coupling means gravity.

A better statement is:

> A large gap in the single-trace spectrum is what makes bulk effective field theory local below the AdS scale.

Strong coupling may produce such a gap in some theories, but it is not a universal diagnostic. The CFT spectrum is the real invariant object.

## What bottom-up models assume

Many holographic applications start from an action such as

$$
S=
\frac{1}{16\pi G_{d+1}}
\int d^{d+1}x\sqrt{-g}
\left(
R - \frac12(\partial\phi)^2 - V(\phi)
- \frac14 Z(\phi)F^2
\right).
$$
This is a bottom-up model. It assumes that there exists a CFT or quantum field theory whose low-energy bulk description is captured by this action.

That assumption can be very useful. It lets one study robust mechanisms: horizons, transport, scaling geometries, symmetry breaking, entanglement wedges, and RG flows. But a bottom-up model is not automatically a complete UV-consistent quantum gravity theory. It must still satisfy consistency constraints such as causality, stability, charge quantization, and the absence of forbidden global symmetries.

## Dictionary checkpoint

A practical holographic CFT has the following bulk translations:

| Boundary criterion | Bulk consequence |
|---|---|
| $c_T\gg1$ | $G_{d+1}/L^{d-1}\ll1$; weak gravitational loops |
| large-$N$ factorization | weakly interacting single-particle bulk states |
| sparse single-trace spectrum | finite set of light bulk fields |
| $\Delta_{\rm gap}\gg1$ | local bulk EFT below the AdS scale |
| no light higher-spin tower | Einstein-like rather than higher-spin gravity |
| crossing and causality | constraints on bulk interactions |
| stress tensor $T_{ij}$ | bulk metric $g_{\mu\nu}$ |

The important negative lesson is just as valuable: large $N$ does not automatically mean Einstein gravity.

## Common confusions

### “Every large-$N$ theory has an Einstein dual.”

No. Large $N$ suppresses loops, but it does not guarantee locality or a finite light spectrum. Vector models are the standard counterexample: they are large-$N$ theories, but their bulk description is higher-spin-like rather than Einstein-like.

### “A holographic CFT must be supersymmetric.”

No. Supersymmetry is a powerful tool for constructing and controlling examples, but the logic of the dictionary does not require supersymmetry. What is hard is constructing nonsupersymmetric examples that are fully stable and under quantitative control.

### “A bottom-up model is fake because it is not top-down.”

Also no. Bottom-up models are useful effective theories. The problem is not that they are fake; the problem is that their domain of validity must be stated honestly. They model sectors of possible holographic theories rather than automatically defining complete quantum gravity backgrounds.

### “Large central charge alone is enough.”

No. Large $c_T$ gives a small Newton constant, but it does not guarantee a large string scale, a sparse single-trace spectrum, or local bulk interactions.

### “The gap is only a technical detail.”

The gap is the difference between a local bulk field theory and a stringy/higher-spin mess on the AdS scale. It is one of the central diagnostics of semiclassical holography.

## Exercises

### Exercise 1: Newton's constant from $c_T$
Suppose a family of CFTs has $c_T\sim N^2$. What is the scaling of the bulk Newton constant in AdS units?

<details>
<summary><strong>Solution</strong></summary>

The holographic relation is

$$
c_T \sim \frac{L^{d-1}}{G_{d+1}}.
$$
If $c_T\sim N^2$, then

$$
\frac{G_{d+1}}{L^{d-1}} \sim \frac{1}{N^2}.
$$
Thus bulk quantum loops are suppressed by powers of $1/N^2$. This is the gravitational version of the planar expansion.

</details>

### Exercise 2: Why does a higher-spin current obstruct Einstein gravity?

A conserved spin-$s$ current in a $d$-dimensional CFT has dimension

$$
\Delta=d-2+s.
$$
For $s>2$, explain why this suggests a massless higher-spin field in the bulk.

<details>
<summary><strong>Solution</strong></summary>

Conserved currents sit in short conformal multiplets. Under the AdS/CFT dictionary, conserved spin-$s$ currents are dual to gauge fields of spin $s$ in AdS. For $s=1$ this gives a bulk gauge field; for $s=2$ this gives the graviton. For $s>2$, one gets massless higher-spin gauge fields.

Ordinary Einstein gravity contains a massless spin-2 graviton but not an infinite set of massless higher-spin gauge fields. Therefore a CFT with light conserved higher-spin currents should not be expected to have a simple Einstein-gravity dual.

</details>

### Exercise 3: Large $N$ but no gap

Consider a large-$N$ CFT whose connected correlators factorize, but whose single-trace spectrum contains infinitely many operators with dimensions of order one. What is the expected bulk interpretation?

<details>
<summary><strong>Solution</strong></summary>

Factorization suggests weak bulk interactions, but the absence of a gap means there are infinitely many light single-particle bulk fields in AdS units. This is not a finite local EFT of Einstein gravity plus a small number of matter fields. The bulk may be higher-spin-like, tensionless-string-like, or otherwise nonlocal at the AdS scale.

</details>

### Exercise 4: The gap and the derivative expansion

Assume a heavy bulk field has mass $M$ with $ML\sim \Delta_{\rm gap}$. Show why integrating it out produces interactions suppressed by powers of $1/\Delta_{\rm gap}$.

<details>
<summary><strong>Solution</strong></summary>

A heavy field of mass $M$ produces local operators suppressed by powers of $1/M$. In AdS units, derivatives are measured in units of $1/L$, so the expansion parameter is

$$
\frac{1/L}{M} = \frac{1}{ML} \sim \frac{1}{\Delta_{\rm gap}}.
$$
Thus each additional pair of derivatives is suppressed by powers of $1/\Delta_{\rm gap}^2$. This is why a large single-trace gap is the CFT condition for a local bulk derivative expansion.

</details>

## Further reading

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151).
- X. O. Camanho, J. D. Edelstein, J. Maldacena, and A. Zhiboedov, [Causality Constraints on Corrections to the Graviton Three-Point Coupling](https://arxiv.org/abs/1407.5597).
- D. Simmons-Duffin, [The Conformal Bootstrap](https://arxiv.org/abs/1602.07982).
