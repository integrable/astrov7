---
title: "Locality and Microcausality"
description: "Explains local commutativity in Wightman QFT, including smeared fields, graded signs, spacelike separation, and common misconceptions about causality."
sidebar:
  label: "Locality and Microcausality"
  order: 5
level: Graduate
status: "Polished draft"
source: "Wightman; Streater–Wightman; Jost; Haag; Pauli–Jordan commutator; algebraic QFT locality."
topics:
  - locality
  - microcausality
  - local commutativity
  - graded commutators
  - Wightman functions
canonicalTopics:
  - wightman-axioms
  - locality
  - microcausality
researchStatus:
  established:
    - "In Wightman QFT, local commutativity requires smeared fields with spacelike separated supports to commute or graded-commute on the common invariant domain."
    - "For bosonic free scalar fields, the commutator is the Pauli–Jordan distribution and is supported on the causal cone, so it vanishes at spacelike separation."
  active:
    - "Gauge theories, charged fields, line operators, generalized symmetries, and nonlocal order parameters require more careful formulations of what the local observable algebra is."
---

## Summary

Locality in Wightman QFT is the axiom that spacelike separated fields cannot be used to influence one another. The rigorous field statement is not a slogan about point operators. It is a statement about smeared operators on the common domain:

$$
[\phi_i(f),\phi_j(g)]_\gamma\Psi=0,
\qquad
\Psi\in\mathcal D,
$$

whenever the supports of $f$ and $g$ are spacelike separated. The graded commutator is

$$
[A,B]_\gamma
=AB-(-1)^{|A||B|}BA.
$$

For two bosonic fields this is an ordinary commutator. For two fermionic fields it is an anticommutator. Physical bosonic observables localized in spacelike separated regions commute.

For a neutral scalar field, the locality axiom reads simply

$$
[\phi(f),\phi(g)]\Psi=0
\quad
\text{if }
\operatorname{supp}f\perp\operatorname{supp}g.
$$

Here $\operatorname{supp}f\perp\operatorname{supp}g$ means that every point in one support is spacelike separated from every point in the other. This page explains why this is the right mathematical form of microcausality, how it appears in Wightman functions, and what it does **not** say.

<figure class="doc-figure" style="--figure-width: 40rem;">

![Spacelike separated smearings and local commutativity](/figures/rigorous-qft/microcausality-spacelike-supports.svg)

<figcaption>

Locality is a statement about separated spacetime regions. If the supports of $f$ and $g$ are spacelike separated, the corresponding smeared fields commute or graded-commute on the Wightman domain. The light cone marks causal, not Euclidean, separation.

</figcaption>
</figure>

## Prerequisites

You should know why Wightman fields are smeared from [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/), how supports of test functions enter from [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/), and how domains are handled in [Domains of Unbounded Operators](/rigorous-qft/operator-valued-distributions/domains-of-unbounded-operators/).

Within this chapter, [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/), [Poincaré Covariance](/rigorous-qft/wightman-axiomatic-qft/poincare-covariance/), and [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/) give the surrounding axioms.

## Core idea

Special relativity distinguishes timelike, lightlike, and spacelike separation. Events that are spacelike separated have no invariant time ordering. A Lorentz transformation can reverse which one has the larger coordinate time. Therefore, a local relativistic quantum theory cannot allow an observable choice made in one spacelike region to change measurable outcomes in the other.

In Hilbert-space language, the clean expression is commutativity of independent local operations. For Wightman fields, because fields may be fermionic and because point fields are distributions, the axiom is expressed as graded commutativity of smeared fields:

$$
\phi_i(f)\phi_j(g)\Psi
=
(-1)^{|i||j|}\phi_j(g)\phi_i(f)\Psi,
\qquad
\Psi\in\mathcal D,
$$

when the supports are spacelike separated.

The condition is local because it refers to the spacetime supports of $f$ and $g$. It is causal because spacelike separation is the invariant condition for no signal to pass between the supports.

A useful slogan is:

$$
\text{microcausality}
=
\text{graded commutativity at spacelike separation}.
$$

## Setup and conventions

For two subsets $O_1,O_2\subset\mathbb R^d$, write

$$
O_1\perp O_2
$$

when

$$
(x-y)^2<0
\qquad
\text{for all }x\in O_1,
\ y\in O_2.
$$

For test functions, write

$$
\operatorname{supp}f\perp\operatorname{supp}g
$$

when their supports are spacelike separated in this sense. In practice one often uses compactly supported test functions for sharp localization statements. The Wightman framework also uses Schwartz test functions; for locality one phrases the condition for test functions whose supports are separated, or equivalently works with compactly supported smooth functions when discussing local support.

For fields with a $\mathbb Z_2$ grading, let

$$
|\phi_i|\in\{0,1\}
$$

denote bosonic or fermionic parity. The graded commutator is

$$
[\phi_i(f),\phi_j(g)]_\gamma
=
\phi_i(f)\phi_j(g)
-
(-1)^{|\phi_i||\phi_j|}
\phi_j(g)\phi_i(f).
$$

Thus

$$
[A,B]_\gamma=
\begin{cases}
AB-BA,&\text{if at least one of }A,B\text{ is even},\\
AB+BA,&\text{if }A\text{ and }B\text{ are odd}.
\end{cases}
$$

For a neutral scalar field, the grading is even and locality becomes ordinary commutativity.

## The Wightman locality axiom

Let $\mathcal D$ be the common invariant domain of the fields. The Wightman locality axiom states that

$$
[\phi_i(f),\phi_j(g)]_\gamma\Psi=0
$$

for all $\Psi\in\mathcal D$ whenever $\operatorname{supp}f\perp\operatorname{supp}g$.

This is a domain-level assertion. The operators $\phi_i(f)$ and $\phi_j(g)$ are generally unbounded, so the equation is first asserted on the common domain where both products make sense:

$$
\phi_i(f)\phi_j(g)\Psi,
\qquad
\phi_j(g)\phi_i(f)\Psi.
$$

Because $\mathcal D$ is invariant under each smeared field, both products lie in $\mathcal D$ and the equality is meaningful.

Point notation compresses this statement into

$$
[\phi_i(x),\phi_j(y)]_\gamma=0
\qquad
\text{for }(x-y)^2<0.
$$

This formula is useful but should be read as distributional shorthand. The true assertion is obtained after smearing in $x$ and $y$ with separated supports.

## Locality for Wightman functions

Locality has a correlation-function form. For scalar bosonic fields, if the adjacent variables $x_k$ and $x_{k+1}$ are spacelike separated, then the Wightman functions obey

$$
W_n(\ldots,x_k,x_{k+1},\ldots)
=
W_n(\ldots,x_{k+1},x_k,\ldots)
$$

as distributions in the spacelike-separated region. With graded fields, one includes the sign

$$
W_n(\ldots,x_k,x_{k+1},\ldots)
=
(-1)^{|\phi_k||\phi_{k+1}|}
W_n(\ldots,x_{k+1},x_k,\ldots).
$$

This does not mean that arbitrary time-ordered or Wightman functions vanish outside the light cone. It means that the **failure to commute** vanishes outside the light cone.

For the two-point scalar commutator distribution,

$$
C(x-y)
=
\langle\Omega,[\phi(x),\phi(y)]\Omega\rangle,
$$

locality says

$$
C(z)=0
\qquad
\text{for }z^2<0.
$$

The individual two-point function $W_2(z)$ is usually nonzero at spacelike $z$. Vacuum correlations and causal influence are different notions.

## Free scalar field as the model example

For the free real scalar field,

$$
[\phi(x),\phi(y)]=i\Delta(x-y)\,\mathbf 1,
$$

where the Pauli–Jordan distribution is

$$
\Delta(x)
=
\int\frac{d^dp}{(2\pi)^{d-1}}
\operatorname{sgn}(p^0)
\delta(p^2-m^2)e^{-ip\cdot x}.
$$

Equivalently,

$$
\Delta(x)=\Delta_+(x)-\Delta_+(-x).
$$

The key support property is

$$
\operatorname{supp}\Delta
\subset
\{x:x^2\ge0\}.
$$

Therefore $\Delta(x-y)=0$ when $x-y$ is spacelike. After smearing,

$$
[\phi(f),\phi(g)]
=i\Delta(f,g)\,\mathbf 1,
$$

where

$$
\Delta(f,g)
=
\int d^dx\,d^dy\,f(x)g(y)\Delta(x-y).
$$

If $\operatorname{supp}f\perp\operatorname{supp}g$, then $\Delta(x-y)=0$ throughout the integration region, so

$$
[\phi(f),\phi(g)]=0.
$$

This example is the prototype for local commutativity. Interacting theories need not have a c-number commutator, but the spacelike vanishing of the graded commutator remains the axiom.

## What locality does and does not say

Locality says that spacelike separated field operations commute or graded-commute. It does not say that spacelike correlations vanish.

For example, in the free massive scalar theory,

$$
W_2(x-y)=\langle\Omega,\phi(x)\phi(y)\Omega\rangle
$$

is nonzero for spacelike separation. This is compatible with locality because the reversed ordering gives the same value at spacelike separation:

$$
W_2(x-y)-W_2(y-x)
=\langle\Omega,[\phi(x),\phi(y)]\Omega\rangle
=0
$$

for $(x-y)^2<0$.

Locality also does not say that the equal-time canonical commutation relations are the same thing as microcausality. For a scalar field,

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(d-1)}(\mathbf x-\mathbf y)
$$

is an equal-time canonical relation. Microcausality is the spacetime statement

$$
[\phi(x),\phi(y)]=0
\qquad
\text{for }(x-y)^2<0.
$$

The two are related in free and canonical constructions, but they are not the same axiom.

## Grading and observables

Fermionic fields anticommute at spacelike separation:

$$
\{\psi_\alpha(f),\psi_\beta(g)\}=0
$$

for separated supports, with similar relations involving adjoints depending on the field multiplet and convention.

This does not mean that fermionic physics violates ordinary locality. Physical observables are even operators, such as currents and stress tensors. Even operators commute with even operators at spacelike separation:

$$
[A(f),B(g)]=0
\qquad
\text{for even local observables }A,B.
$$

The grading is bookkeeping for fields that create states with fermion parity. Observable locality remains ordinary commutativity.

The spin–statistics theorem explains, under Wightman-type hypotheses, why the correct grading is tied to Lorentz spin. In many presentations the grading is included in the field-locality axiom, and spin–statistics proves that the grading agrees with integer or half-integer spin in the expected way.

## Locality versus algebraic locality

Wightman theory phrases locality in terms of fields. Algebraic QFT phrases locality in terms of local observable algebras:

$$
[\mathcal A(O_1),\mathcal A(O_2)]=0
\qquad
\text{if }O_1\perp O_2.
$$

This formulation can be more intrinsic because different field coordinatizations may generate the same observable content. It is also better adapted to superselection sectors, gauge theories, and questions about localization of observables rather than localization of particular fields.

The two viewpoints are closely related when fields generate local algebras. If $\phi(f)$ is affiliated with the local algebra of a region containing $\operatorname{supp}f$, then Wightman locality implies algebraic locality for the observables generated from those fields. Conversely, algebraic locality may hold even when no preferred point field is chosen.

## Gauge theory caveats

Gauge theory is a major source of confusion about locality. Gauge-dependent fields such as $A_\mu$ in covariant gauges may live in auxiliary indefinite-metric or BRST complexes. They are useful for calculation but are not automatically Wightman fields on a positive physical Hilbert space.

Gauge-invariant local observables, such as suitable field-strength polynomials, are expected to be local. Wilson lines, ’t Hooft lines, disorder operators, and other extended or topological operators have their own localization regions and may obey more subtle commutation laws involving linking or braiding.

Thus the right locality question is always:

$$
\text{Which operators are genuine observables, and where are they localized?}
$$

The Wightman locality axiom gives the clean point-field version. Later algebraic, topological, and generalized-symmetry frameworks refine the answer for modern gauge-theoretic examples.

## Locality, spectrum, and analyticity

Locality is powerful because it combines with the spectral condition. The spectral condition gives analyticity of Wightman functions in tube domains. Locality says that certain boundary values agree when adjacent spacelike arguments are exchanged.

Together, these facts let one extend analytic functions beyond their original tube domains. This is the start of the Jost-point and edge-of-the-wedge machinery used in the proofs of structural theorems.

The rough chain is

$$
\text{spectrum}
\Rightarrow
\text{tube analyticity},
\qquad
\text{locality}
\Rightarrow
\text{exchange identities},
$$

and therefore

$$
\text{spectrum + locality + covariance}
\Rightarrow
\text{CPT, spin–statistics, analytic constraints}.
$$

The details are technical, but the conceptual message is simple: the sign of energy and the impossibility of spacelike signalling are not independent decorative axioms. Together they rigidify relativistic QFT.

## Common pitfalls

**Thinking locality means correlations vanish.** Vacuum correlations can be nonzero at spacelike separation. The commutator or graded commutator vanishes.

**Using point fields literally.** The expression $[\phi(x),\phi(y)]=0$ for spacelike separation is distributional shorthand. The rigorous statement uses test functions with separated supports.

**Confusing equal-time canonical relations with locality.** Equal-time commutators are canonical input in some constructions. Microcausality is a Lorentz-invariant spacetime condition.

**Forgetting the domain.** Since smeared fields are usually unbounded, locality is first an equality on the common invariant domain $\mathcal D$.

**Treating all gauge-dependent fields as physical local observables.** In gauge theory, the locality of the observable algebra is often cleaner than the locality of a particular gauge-fixed field variable.

**Omitting fermionic signs.** Fermionic fields anticommute, not commute, at spacelike separation. Even observables commute.

## Relations to other pages

[Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/) explains the positive-energy input that combines with locality to produce analytic consequences.

The future Wightman Functions page will state locality directly as permutation identities for vacuum distributions.

The future Spin–Statistics Theorem page will explain why spin and grading are linked under the Wightman hypotheses.

The future CPT Theorem page will use locality, covariance, positivity, and analyticity as structural inputs.

The later Local Nets of Algebras page will rephrase locality as commutativity of observable algebras assigned to spacetime regions.

## Research status

Local commutativity is established as a core axiom in Wightman QFT and as Einstein causality in algebraic QFT. For ordinary scalar, spinor, and vector examples after appropriate physical-state treatment, it is the standard mathematical formulation of relativistic locality.

The active frontier is not whether locality is important. It is how to formulate locality for gauge theories, charged sectors, topological operators, non-invertible defects, generalized symmetries, and theories where point fields are not the most natural starting objects. Algebraic QFT, factorization algebras, extended TQFT, and modern symmetry frameworks all refine the meaning of localization while preserving the central idea that spacelike separated observables should be independently measurable.

## Exercises

### Exercise 1: Spacelike supports imply a vanishing free commutator

Let $\phi$ be a free real scalar field with

$$
[\phi(f),\phi(g)]=i\Delta(f,g)\mathbf 1,
$$

and suppose $\operatorname{supp}\Delta\subset\{x:x^2\ge0\}$. Show that $[\phi(f),\phi(g)]=0$ if $\operatorname{supp}f\perp\operatorname{supp}g$.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
\Delta(f,g)=
\int d^dx\,d^dy\,f(x)g(y)\Delta(x-y).
$$

If $\operatorname{supp}f\perp\operatorname{supp}g$, then $(x-y)^2<0$ whenever $f(x)g(y)$ can be nonzero. But $\Delta(x-y)$ vanishes for spacelike $x-y$. Hence the integrand is zero everywhere, so $\Delta(f,g)=0$ and therefore

$$
[\phi(f),\phi(g)]=0.
$$

</details>

### Exercise 2: Correlation is not commutator

For a scalar field, suppose $W_2(z)$ is nonzero for a spacelike vector $z$, but $W_2(z)=W_2(-z)$ for spacelike $z$. Show that this is compatible with locality.

<details><summary><strong>Solution</strong></summary>

The vacuum expectation value of the commutator is

$$
\langle\Omega,[\phi(x),\phi(y)]\Omega\rangle
=
W_2(x-y)-W_2(y-x).
$$

Let $z=x-y$. If $z$ is spacelike and $W_2(z)=W_2(-z)$, then

$$
W_2(z)-W_2(-z)=0.
$$

Thus the commutator expectation value vanishes even though the individual correlation $W_2(z)$ may be nonzero. Locality constrains the commutator, not the correlation itself.

</details>

### Exercise 3: Even observables commute from graded locality

Let $\psi_1(f)$ and $\psi_2(g)$ be odd fields with spacelike separated supports, so they anticommute. Let $A$ be an even polynomial in odd fields localized in the first region and $B$ an even polynomial localized in the second. Explain why $A$ and $B$ commute.

<details><summary><strong>Solution</strong></summary>

Moving one odd field from the first region past one odd field from the second region produces a minus sign. If $A$ contains an even number of odd factors and $B$ contains an even number of odd factors, then moving all factors of $A$ past all factors of $B$ produces

$$
(-1)^{(\text{even})(\text{even})}=+1.
$$

Thus $AB=BA$ on the common domain, up to the usual qualifications about forming well-defined smeared composite operators. This is why observable locality is ordinary commutativity even when the underlying charged fields are fermionic.

</details>

## References

### Standard first pass

- A. S. Wightman, "Quantum Field Theory in Terms of Vacuum Expectation Values," *Physical Review* **101** (1956), 860–866. DOI: [10.1103/PhysRev.101.860](https://doi.org/10.1103/PhysRev.101.860).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- R. Jost, *The General Theory of Quantized Fields*, American Mathematical Society, 1965.

### Locality, algebras, and examples

- R. Haag, *Local Quantum Physics: Fields, Particles, Algebras*, Springer. DOI: [10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- H. Araki, *Mathematical Theory of Quantum Fields*, Oxford University Press.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics II: Fourier Analysis, Self-Adjointness*, Academic Press.

## Version history

- **2026-06-28:** Initial polished draft.
