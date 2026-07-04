---
title: "Replica Method Preview"
description: "A careful QFT-oriented preview of the replica method for quenched disorder, entanglement entropy, twist constructions, and analytic continuation in replica number."
sidebar:
  label: "Replica Method Preview"
  order: 8
level: Advanced
status: "Polished draft"
source: "Standard uses of replicas in disordered systems, statistical field theory, Euclidean QFT, and entanglement entropy calculations."
topics:
  - replica method
  - quenched disorder
  - annealed averages
  - entanglement entropy
  - Rényi entropy
  - twist defects
  - analytic continuation
canonicalTopics:
  - replica-trick
  - quenched-disorder
  - renyi-entropy
  - entanglement-replica-method
  - disorder-averaged-qft
researchStatus:
  established:
    - "Replica formulas for quenched free energies and Rényi entropies are standard tools in statistical field theory, disordered systems, random matrices, and entanglement calculations."
    - "For integer replica number, replicated theories often have a direct path-integral or statistical-mechanical construction."
  active:
    - "Analytic continuation in replica number, replica-symmetry breaking, nonperturbative saddles, gravitational replicas, and rigorous control of replica limits remain subtle and research-active."
---

## Summary

The replica method is a way to compute something hard by first computing an integer family of easier problems and then analytically continuing in the integer parameter. The two most common QFT formulas are

$$
\overline{\log Z}
=\lim_{n\to 0}\frac{\overline{Z^n}-1}{n},
$$

for quenched disorder, and

$$
S_A=-\operatorname{Tr}\rho_A\log\rho_A
=\lim_{n\to 1}\frac{1}{1-n}\log\operatorname{Tr}\rho_A^n,
$$

for entanglement entropy.

The method is powerful because $Z^n$ or $\operatorname{Tr}\rho_A^n$ has an honest meaning when $n$ is a positive integer. One can introduce $n$ copies of the system, do a disorder average or glue path integrals cyclically, and obtain a new integer-$n$ theory. The danger is that the desired answer lives at $n\to0$ or $n\to1$, where there may be no unique continuation from integer values. The replica method is therefore a method with a built-in warning label.

The slogan is:

$$
\text{replicas turn logarithms and entropy into partition functions, at the price of analytic continuation.}
$$

<figure class="doc-figure" style="--figure-width: 46rem;">

![Flowchart showing replica calculations from integer replicas to analytic continuation.](/figures/math-toolkit/replica-method-analytic-continuation.svg)

<figcaption>

Replica calculations have two logically separate steps. The integer-$n$ construction is usually concrete: copy the theory, average the disorder, or glue sheets. The continuation away from integer $n$ is the delicate step, and must be justified by physics, analyticity, saddle control, or independent checks.

</figcaption>
</figure>

## Prerequisites

You should know probability expectations, cumulants, Gaussian measures, connected correlators, and large-deviation or saddle-point language. You should also know the basic path-integral idea that a partition function is a sum over configurations weighted by $e^{-S_E}$.

This page is a preview, not a complete treatment of spin glasses, disorder field theory, quantum information, random matrices, or gravitational entropy. The goal is to make replica formulas legible before they appear elsewhere.

## Two different replica tricks

There are two related but distinct uses of replicas.

### Quenched disorder

A theory with random couplings has a partition function $Z[J]$ depending on a disorder realization $J$. The quenched free energy is

$$
F_q=-\beta^{-1}\overline{\log Z[J]},
$$

where the overline denotes averaging over disorder.

The logarithm is hard because the disorder average is outside it. The replica identity

$$
\log Z=\lim_{n\to0}\frac{Z^n-1}{n}
$$

suggests

$$
\overline{\log Z}
=\lim_{n\to0}\frac{\overline{Z^n}-1}{n}.
$$

For positive integer $n$, $Z^n$ is the partition function of $n$ independent copies. After averaging over the same disorder source, the copies become coupled.

### Entanglement entropy

For a density matrix $\rho_A$ reduced to a spatial region $A$, the von Neumann entropy is

$$
S_A=-\operatorname{Tr}\rho_A\log\rho_A.
$$

The Rényi entropies are

$$
S_n(A)=\frac{1}{1-n}\log\operatorname{Tr}\rho_A^n.
$$

For positive integer $n$, $\operatorname{Tr}\rho_A^n$ can often be computed by gluing $n$ Euclidean path integrals cyclically along the region $A$. The entanglement entropy is obtained from

$$
S_A=\lim_{n\to1}S_n(A)
= -\left.\partial_n\log\operatorname{Tr}\rho_A^n\right|_{n=1},
$$

assuming $\operatorname{Tr}\rho_A=1$.

The two replica tricks share the same architecture, but the limits are different:

| Problem | Integer construction | Desired limit |
|---|---:|---:|
| quenched disorder | $n$ copies sharing the same disorder | $n\to0$ |
| entanglement entropy | $n$ sheets glued cyclically | $n\to1$ |

Conflating these is an excellent way to produce confident nonsense. A classic move, admittedly. Still nonsense.

## Annealed versus quenched averages

Suppose $Z[J]$ is the partition function for a fixed disorder realization $J$. There are two natural averages.

The **annealed** free energy is

$$
F_a=-\beta^{-1}\log\overline{Z[J]}.
$$

The **quenched** free energy is

$$
F_q=-\beta^{-1}\overline{\log Z[J]}.
$$

The names come from whether the disorder equilibrates with the microscopic degrees of freedom. Annealed disorder is averaged inside the partition function. Quenched disorder is frozen; one computes the free energy for each realization and then averages.

By Jensen’s inequality, since $\log$ is concave,

$$
\overline{\log Z}\le \log\overline Z.
$$

Therefore

$$
F_q\ge F_a
$$

at positive temperature. The quenched problem is harder because the logarithm prevents immediate averaging.

## The basic quenched replica construction

Let $\phi$ be a field and $h(x)$ a random source coupled to an operator $\mathcal O(x)$:

$$
S_h[\phi]=S_0[\phi]-\int d^dx\,h(x)\mathcal O(x).
$$

Assume $h$ is Gaussian with

$$
\overline{h(x)}=0,
\qquad
\overline{h(x)h(y)}=\Delta\delta^{(d)}(x-y).
$$

For one realization,

$$
Z[h]=\int\mathcal D\phi\,
\exp\!\left[-S_0[\phi]+\int d^dx\,h(x)\mathcal O(x)\right].
$$

For integer $n$,

$$
Z[h]^n
=\int\prod_{a=1}^n\mathcal D\phi_a\,
\exp\!\left[-\sum_{a=1}^nS_0[\phi_a]
+\int d^dx\,h(x)\sum_{a=1}^n\mathcal O_a(x)\right].
$$

Now average over $h$. The Gaussian identity

$$
\overline{e^{\int hJ}}
=\exp\!\left[\frac{\Delta}{2}\int d^dx\,J(x)^2\right]
$$

gives

$$
\overline{Z^n}
=\int\prod_{a=1}^n\mathcal D\phi_a\,
\exp\!\left[-S_{\mathrm{rep}}[\phi_1,\ldots,\phi_n]\right],
$$

where

$$
S_{\mathrm{rep}}
=\sum_{a=1}^nS_0[\phi_a]
-\frac{\Delta}{2}\sum_{a,b=1}^n\int d^dx\,\mathcal O_a(x)\mathcal O_b(x).
$$

The disorder average has created interactions between replicas. The replicated theory has a permutation symmetry $S_n$ exchanging copies, unless the saddle or vacuum breaks it.

## The n to zero limit

The expression

$$
\overline{\log Z}
=\lim_{n\to0}\frac{\overline{Z^n}-1}{n}
$$

is often rewritten as

$$
\overline{\log Z}
=\lim_{n\to0}\frac{\partial}{\partial n}\overline{Z^n},
$$

if the normalization is such that $\overline{Z^0}=1$ and the continuation is differentiable. More commonly, one computes

$$
\overline{Z^n}=e^{-\beta F(n)}
$$

for integer $n$ and extracts the term linear in $n$ as $n\to0$.

Replica combinatorics has a useful rule of thumb: a sum over one free replica index gives a factor of $n$, while a sum over two independent replica indices gives $n^2$. In the $n\to0$ limit, only terms with the right power of $n$ survive after dividing by $n$.

This is why replica diagrams often look like an exercise in counting loops of replica indices. They are. But the counting only means something after the analytic continuation has been chosen.

## Replica symmetry and its breaking

The replicated action often has an $S_n$ symmetry,

$$
\phi_a\mapsto \phi_{\sigma(a)}.
$$

A replica-symmetric saddle treats all copies equally. In some disordered systems, especially spin glasses, the dominant saddle breaks replica symmetry. The order parameter may be an overlap matrix

$$
Q_{ab}\sim \langle \phi_a\phi_b\rangle,
$$

with a nontrivial structure in replica space.

Replica-symmetry breaking is not a minor technicality. It changes the phase structure. In QFT applications, one should not assume replica symmetry simply because the replicated Lagrangian has it. Symmetries of the action can be broken by the saddle or by the state.

## Entanglement replicas and branched geometries

Now consider a QFT state with density matrix $\rho$ and a spatial region $A$. The reduced density matrix is

$$
\rho_A=\operatorname{Tr}_{\bar A}\rho.
$$

In a Euclidean path-integral representation, matrix elements of $\rho_A$ are obtained by cutting spacetime open along $A$ at a time slice. To compute $\operatorname{Tr}\rho_A^n$, one glues $n$ copies cyclically along that cut.

The result is a partition function on an $n$-sheeted geometry:

$$
\operatorname{Tr}\rho_A^n
=\frac{Z_n(A)}{Z_1^n}.
$$

Then

$$
S_n(A)=\frac{1}{1-n}\log\frac{Z_n(A)}{Z_1^n},
$$

and

$$
S_A=\left.(1-n\partial_n)\log Z_n(A)\right|_{n=1}
$$

if $Z_1$ is included in the same normalization. Equivalent formulas differ by whether one starts with normalized $\rho_A$ or unnormalized path integrals.

The singular locus where sheets meet is the **entangling surface** $\partial A$. In two-dimensional CFT, the branch points can be represented by twist operators. In higher dimensions, the analog is a codimension-two twist defect.

## Twist operators and defects

For integer $n$, the replicated theory has fields

$$
\phi_1,\phi_2,\ldots,\phi_n.
$$

A twist operator or twist defect implements the cyclic permutation

$$
\phi_a\mapsto \phi_{a+1},
\qquad
\phi_n\mapsto \phi_1,
$$

when a field is taken around the defect. In two dimensions, for an interval $A=[u,v]$, one often writes

$$
\operatorname{Tr}\rho_A^n
\propto
\langle \mathcal T_n(u)\widetilde{\mathcal T}_n(v)\rangle.
$$

In a two-dimensional CFT, the twist operator has scaling dimension

$$
\Delta_n=\frac{c}{12}\left(n-\frac1n\right)
$$

for a single interval in the vacuum of a unitary theory with central charge $c$, in standard conventions. Then

$$
\operatorname{Tr}\rho_A^n
\propto
\left(\frac{\epsilon}{L}\right)^{\frac{c}{6}(n-1/n)},
$$

and the von Neumann entropy becomes

$$
S_A=\frac{c}{3}\log\frac{L}{\epsilon}+\text{constant}.
$$

This formula is one of the cleanest wins of the replica method: geometry, analyticity, and conformal symmetry cooperate beautifully.

## Replica limits are not innocent

The integer sequence $Z_n$ does not automatically determine a unique analytic function of $n$. Many functions agree on all positive integers but differ elsewhere. In practice, replica calculations rely on extra input: analyticity assumptions, growth bounds, symmetry, saddle selection, comparison to limiting regimes, or independent derivations.

The most common problems are:

| Problem | What can go wrong |
|---|---|
| multiple saddles | the dominant saddle may change as $n$ moves away from integers |
| replica symmetry breaking | the integer-$n$ symmetric ansatz may miss the correct continuation |
| nonperturbative effects | exponentially small terms in one regime can control another |
| gravitational replicas | new replica-nondiagonal saddles can appear |
| logarithmic CFT or nonunitarity | analytic structure may differ from the semisimple case |

The replica method is not “wrong” because of these issues. It is powerful precisely because it converts impossible quantities into tractable families. But it is not a substitute for thinking.

## Disorder, RG, and effective interactions

After disorder averaging, a random coupling usually becomes an interaction in the replicated theory. For example, random-field disorder coupled to $\mathcal O$ gives

$$
-\frac{\Delta}{2}\sum_{a,b}\int d^dx\,\mathcal O_a\mathcal O_b
$$

in the replicated action.

The scaling dimension of this operator determines whether the disorder is relevant. If $\mathcal O$ has dimension $\Delta_{\mathcal O}$ in the clean theory, then the disorder variance coupling has engineering RG eigenvalue

$$
y_\Delta=d-2\Delta_{\mathcal O}
$$

in a simple short-range Gaussian disorder model. Thus disorder is relevant when

$$
2\Delta_{\mathcal O}<d.
$$

This is the field-theory version of the Harris-style logic: randomness becomes important when fluctuations of local couplings grow under coarse-graining.

## Replicas and supersymmetry for disorder

There is another method for quenched disorder that introduces commuting and anticommuting variables so that determinants cancel. This is often called the supersymmetric method for disorder. Its schematic advantage is that it can compute ratios such as

$$
\frac{Z[J]}{Z[J]}
$$

without taking $n\to0$. Its disadvantage is that the resulting theory has graded symmetry and its own subtleties.

Replica and supersymmetric methods are often complementary. In random-matrix and disordered-electron problems, comparing them is a useful consistency check.

## Common pitfalls

### Treating n as real before constructing the integer theory

The clean construction is usually at positive integer $n$. Analytic continuation comes later. Write down the integer-$n$ replicated theory first.

### Forgetting the normalization in entanglement replicas

For entanglement,

$$
\operatorname{Tr}\rho_A^n=\frac{Z_n(A)}{Z_1^n}
$$

when $Z_n$ is built from unnormalized path integrals. Dropping the denominator creates spurious volume terms.

### Confusing quenched and annealed disorder

The quenched average is $\overline{\log Z}$, not $\log\overline Z$. The difference is physical.

### Assuming replica symmetry

The replicated action may be symmetric under permuting copies, but the saddle need not be. Replica-symmetry breaking is not optional in systems where it is required.

### Trusting analytic continuation without checks

The continuation is the soul of the method and also the crack in the floorboards. Whenever possible, check against exact limits, numerics, supersymmetric methods, Ward identities, or known inequalities.

## Exercises

### Exercise 1: The logarithm identity

Show that for $Z>0$,

$$
\log Z=\lim_{n\to0}\frac{Z^n-1}{n}.
$$

<details><summary><strong>Solution</strong></summary>

Write

$$
Z^n=e^{n\log Z}.
$$

Expanding near $n=0$ gives

$$
Z^n=1+n\log Z+O(n^2).
$$

Therefore

$$
\frac{Z^n-1}{n}=\log Z+O(n),
$$

and the limit is $\log Z$.

</details>

### Exercise 2: Gaussian disorder average

Let $h$ be a single Gaussian random variable with mean zero and variance $\Delta$. Show that

$$
\overline{e^{hJ}}=e^{\Delta J^2/2}.
$$

<details><summary><strong>Solution</strong></summary>

The average is

$$
\overline{e^{hJ}}
=\frac{1}{\sqrt{2\pi\Delta}}\int_{-\infty}^{\infty}dh\,
\exp\!\left[-\frac{h^2}{2\Delta}+hJ\right].
$$

Complete the square:

$$
-\frac{h^2}{2\Delta}+hJ
=-\frac{1}{2\Delta}(h-\Delta J)^2+\frac{\Delta J^2}{2}.
$$

The shifted normalized Gaussian integrates to $1$, so

$$
\overline{e^{hJ}}=e^{\Delta J^2/2}.
$$

</details>

### Exercise 3: Replica coupling from a random source

Using the previous exercise, derive the replicated interaction generated by a random source $h(x)$ coupled to $\mathcal O_a(x)$ with variance $\Delta\delta^{(d)}(x-y)$.

<details><summary><strong>Solution</strong></summary>

For integer $n$, the $h$-dependent part of $Z[h]^n$ is

$$
\exp\!\left[\int d^dx\,h(x)\sum_{a=1}^n\mathcal O_a(x)\right].
$$

The Gaussian functional identity gives

$$
\overline{\exp\!\left[\int hJ\right]}
=\exp\!\left[\frac{\Delta}{2}\int d^dx\,J(x)^2\right],
$$

with

$$
J(x)=\sum_a\mathcal O_a(x).
$$

Therefore

$$
\frac{\Delta}{2}\int d^dx\,J(x)^2
=
\frac{\Delta}{2}\sum_{a,b}\int d^dx\,\mathcal O_a(x)\mathcal O_b(x).
$$

Since the path-integral weight is $e^{-S}$, this corresponds to the replicated action term

$$
S_{\mathrm{int,rep}}
=-\frac{\Delta}{2}\sum_{a,b}\int d^dx\,\mathcal O_a\mathcal O_b.
$$

</details>

### Exercise 4: Entanglement from Rényi entropies

Assume $f(n)=\operatorname{Tr}\rho_A^n$ is differentiable near $n=1$ and $f(1)=1$. Show that

$$
\lim_{n\to1}\frac{1}{1-n}\log f(n)
=-f'(1).
$$

<details><summary><strong>Solution</strong></summary>

Since $f(1)=1$,

$$
\log f(1)=0.
$$

Using L’Hôpital’s rule,

$$
\lim_{n\to1}\frac{\log f(n)}{1-n}
=\frac{f'(1)/f(1)}{-1}
=-f'(1).
$$

For $f(n)=\operatorname{Tr}\rho_A^n$,

$$
f'(1)=\operatorname{Tr}\rho_A\log\rho_A,
$$

so the limit is

$$
-\operatorname{Tr}\rho_A\log\rho_A.
$$

</details>

## References

- Edwards and Anderson, “Theory of spin glasses.”
- Mézard, Parisi, and Virasoro, *Spin Glass Theory and Beyond*.
- Cardy, *Scaling and Renormalization in Statistical Physics*.
- Dotsenko, *Introduction to the Replica Theory of Disordered Statistical Systems*.
- Altland and Simons, *Condensed Matter Field Theory*.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- Calabrese and Cardy, “Entanglement entropy and quantum field theory.”
- Casini and Huerta, “Entanglement entropy in free quantum field theory.”
- Lewkowycz and Maldacena, “Generalized gravitational entropy.”

## Version history

- **2026-06-27:** First polished draft. Introduces quenched and annealed disorder, replicated disorder actions, the $n\to0$ limit, entanglement replicas, twist defects, analytic-continuation caveats, and worked exercises.
