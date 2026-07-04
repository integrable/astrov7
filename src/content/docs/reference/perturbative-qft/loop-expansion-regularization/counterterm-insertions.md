---
title: "Counterterm Insertions"
description: "How local counterterms appear as Feynman-diagram vertices, cancel ultraviolet divergences, and organize renormalized perturbation theory."
sidebar:
  label: "Counterterm Insertions"
  order: 9
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§14–20 and 27; Coleman 2019, chs. 9–10, 15–16, and 25; Weinberg 1995, Vol. I, chs. 6 and 12; Schwartz 2014, chs. 15–21; Zinn-Justin 2021, chs. 8–10"
topics:
  - counterterm insertions
  - counterterm diagrams
  - renormalized perturbation theory
  - ultraviolet divergences
  - scalar field theory
canonicalTopics:
  - counterterm-insertion
  - counterterm-vertex
  - local-ultraviolet-divergence
  - renormalized-lagrangian
  - subtraction-scheme
researchStatus:
  established:
    - "Counterterm insertions are the standard diagrammatic implementation of renormalized perturbation theory: local counterterm vertices cancel the local regulator-dependent parts of loop diagrams order by order."
  active:
    - "Modern precision calculations require systematic multi-loop counterterm bookkeeping, gauge and BRST identities, infrared subtractions, unstable-particle schemes, and automated renormalization workflows beyond the scalar examples on this page."
---

## Summary

A **counterterm insertion** is a Feynman-diagram vertex coming from the counterterm part of the Lagrangian. Counterterms are not mysterious extra physics added after a loop integral misbehaves. They are the local interactions required to express a bare theory in terms of chosen renormalized parameters.

For scalar $\phi^4$ theory in qft.org conventions, a useful split is

$$
\mathcal L
=
\mathcal L_{\rm ren}+\mathcal L_{\rm ct},
$$

where

$$
\mathcal L_{\rm ren}
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\lambda}{4!}\phi^4,
$$

and

$$
\mathcal L_{\rm ct}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2
-
\frac{\delta\lambda}{4!}\phi^4
-\delta\Lambda.
$$

The scalar counterterm vertex factors are

$$
{\text{two-point counterterm: }i(p^2\delta Z-\delta m^2),}
$$

$$
{\text{four-point counterterm: }-i\delta\lambda,}
\qquad
{\text{vacuum counterterm: }-i\delta\Lambda.}
$$

A counterterm insertion cancels the **local** ultraviolet part of loop diagrams. It does not cancel the physical nonlocal dependence on momenta, masses, and thresholds. Those logarithms, branch cuts, and finite form factors are part of the prediction.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Counterterm insertions as local vertices paired with loop diagrams for two-point and four-point functions](/figures/perturbative-qft/counterterm-insertions.svg)

<figcaption>

Counterterm insertions are ordinary Feynman-rule vertices from $\mathcal L_{\rm ct}$. A two-point insertion cancels local pieces of self-energy diagrams; a four-point insertion cancels local pieces of vertex corrections. The finite nonlocal remainder is not removed by a local counterterm.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/), [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Superficial Degree of Divergence](/perturbative-qft/loop-expansion-regularization/superficial-degree-of-divergence/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/), [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/), and [Vacuum Bubbles](/perturbative-qft/loop-expansion-regularization/vacuum-bubbles/).

For the later renormalized-amplitude interpretation, review [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/) and [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/).

## Core idea

Perturbative loop diagrams often contain ultraviolet-sensitive pieces. Locality says something powerful about those pieces: at large loop momentum, the diagram cannot resolve the detailed long-distance arrangement of the external legs. Its divergent part is therefore a polynomial in external momenta and masses, compatible with the symmetries of the theory.

A polynomial in external momenta is exactly what a local operator produces. Counterterms are the local operators whose coefficients are chosen to cancel those local regulator-dependent pieces.

The central workflow is

$$
\text{bare theory}
\quad\longrightarrow\quad
\text{renormalized parameters}+\text{counterterms}
\quad\longrightarrow\quad
\text{finite predictions}.
$$

In diagrams this becomes

$$
\text{loop diagram}
+
\text{counterterm insertion}
=
\text{finite scheme-defined contribution}.
$$

The counterterm is local. The loop diagram need not be. The subtraction removes the local UV ambiguity and leaves the nonlocal dependence that amplitudes and correlation functions are supposed to have.

## Setup and conventions

We use qft.org mostly-minus conventions. The renormalized scalar propagator used in perturbative diagrams is

$$
\frac{i}{p^2-m^2+i\epsilon}.
$$

Dimensional regularization is written with

$$
d=4-2\epsilon,
\qquad
\int_\ell
\equiv
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d},
$$

and

$$
\frac{1}{\overline\epsilon}
\equiv
\frac{1}{\epsilon}-\gamma_E+\ln4\pi.
$$

The scalar counterterm Lagrangian used on this page is

$$
\mathcal L_{\rm ct}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2
-
\frac{\delta\lambda}{4!}\phi^4
-\delta\Lambda.
$$

The constants $\delta Z$, $\delta m^2$, $\delta\lambda$, and $\delta\Lambda$ are not fixed until a renormalization prescription is chosen. In minimal subtraction they remove only pole terms. In an on-shell scheme they are chosen so that pole masses, residues, and selected amplitudes obey specified physical normalization conditions.

The counterterms themselves are expanded perturbatively:

$$
\delta Z=\delta Z^{(1)}+\delta Z^{(2)}+\cdots,
\qquad
\delta m^2=\delta m^{2(1)}+\delta m^{2(2)}+\cdots,
$$

and similarly for $\delta\lambda$. A one-loop counterterm counts as order one loop in bookkeeping even though the diagram containing the counterterm may have no loop integral.

## From bare parameters to counterterm vertices

Start from a bare scalar Lagrangian,

$$
\mathcal L_0
=
\frac12\partial_\mu\phi_0\,\partial^\mu\phi_0
-\frac12m_0^2\phi_0^2
-\frac{\lambda_0}{4!}\phi_0^4.
$$

Introduce a renormalized field and renormalized parameters. One common notation is

$$
\phi_0=Z_\phi^{1/2}\phi.
$$

After re-expressing bare quantities in terms of renormalized quantities plus counterterms, the same bare theory is written as

$$
\mathcal L_0
=
\mathcal L_{\rm ren}+\mathcal L_{\rm ct}.
$$

For the scalar split above, the quadratic part of $\mathcal L_{\rm ct}$ contributes to the action as

$$
\frac12\int\frac{d^dp}{(2\pi)^d}\,
\phi(-p)\bigl(p^2\delta Z-\delta m^2\bigr)\phi(p).
$$

Multiplication by $i$ from $e^{iS}$ gives the two-point counterterm insertion

$$
\text{two-point counterterm factor}
=
i(p^2\delta Z-\delta m^2).
$$

For the quartic counterterm,

$$
-\frac{\delta\lambda}{4!}\phi^4,
$$

the $4!$ Wick contractions cancel the $1/4!$, giving the four-point counterterm vertex

$$
\text{four-point counterterm factor}=-i\delta\lambda.
$$

The exact graphic style is not physics. Some authors draw a crossed dot, some draw a small square, and some label the vertex explicitly. The algebraic factor is the rule.

:::note[Diagram notation]
A counterterm cross does not mean the diagram is deleted. It means “insert the local counterterm vertex here.” Tiny notation goblin, large consequences.
:::

## What counterterms can and cannot cancel

Counterterms are local, so they can cancel only local terms.

A local two-point counterterm has the form

$$
i(p^2\delta Z-\delta m^2).
$$

It can cancel divergent pieces proportional to $p^2$ and to a constant mass term. It cannot cancel a nonlocal finite term such as

$$
p^2\ln\frac{-p^2-i\epsilon}{\mu^2},
$$

because no local two-point operator produces a logarithm of momentum.

Similarly, a local four-point counterterm $-i\delta\lambda$ can cancel a momentum-independent divergent part of a four-point vertex in renormalizable $\phi^4$ theory. It cannot cancel finite functions such as

$$
\ln\frac{m^2-x(1-x)s-i\epsilon}{\mu^2}
$$

that arise from a bubble integral. Those logarithms know about thresholds and long-distance propagation. They are not artifacts of the regulator.

This distinction is the spine of renormalization:

| Loop contribution | Counterterm response |
|---|---|
| local UV pole | canceled by a local counterterm |
| scheme-dependent local finite part | fixed by a renormalization condition |
| nonlocal finite logarithm or branch cut | remains in the physical amplitude |
| symmetry-violating regulator artifact | canceled, or avoided, if the symmetry is non-anomalous |

## Two-point counterterm insertions

A scalar self-energy correction contributes an amputated two-point insertion. Write the loop part of the one-particle-irreducible two-point insertion as

$$
i\Pi_{\rm loop}(p^2).
$$

The counterterm contribution is

$$
i\Pi_{\rm ct}(p^2)=i(p^2\delta Z-\delta m^2).
$$

The renormalized insertion is

$$
 i\Pi_{\rm ren}(p^2)
 =
 i\Pi_{\rm loop}(p^2)+i(p^2\delta Z-\delta m^2).
$$

Suppose the divergent part of the loop insertion is local,

$$
\Pi_{\rm loop}^{\rm div}(p^2)=A+Bp^2.
$$

Then choosing

$$
\delta m^2=A,
\qquad
\delta Z=-B
$$

cancels the divergence, since

$$
\Pi_{\rm loop}^{\rm div}(p^2)+p^2\delta Z-\delta m^2
=
(A+Bp^2)-Bp^2-A=0.
$$

In a mass-independent subtraction scheme, the pole parts of $A$ and $B$ are subtracted. In an on-shell scheme, finite pieces are also chosen so that the renormalized propagator has its pole at the physical mass and residue one.

## Four-point counterterm insertions

In four-dimensional scalar $\phi^4$ theory, the one-loop four-point 1PI diagrams are the $s$-, $t$-, and $u$-channel bubbles. With the scalar bubble convention

$$
I(P^2)
=
-iB(P^2;m^2,m^2),
$$

the one-loop four-point vertex factor is

$$
 i\mathcal M_{4,\rm loop}^{(1)}
 =
 \frac{(-i\lambda)^2}{2}\left[I(s)+I(t)+I(u)\right].
$$

The counterterm contribution is

$$
 i\mathcal M_{4,\rm ct}^{(1)}=-i\delta\lambda.
$$

Using

$$
B(P^2;m^2,m^2)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}+\text{finite}(P^2)
\right],
$$

the divergent part of the three-channel loop contribution is

$$
 i\mathcal M_{4,\rm loop}^{(1),\rm div}
 =
 i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}.
$$

Minimal subtraction therefore chooses

$$
\delta\lambda_{\rm MS}^{(1)}
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}
$$

when $d=4-2\epsilon$. With this choice,

$$
 i\mathcal M_{4,\rm loop}^{(1),\rm div}+i\mathcal M_{4,\rm ct}^{(1)}=0.
$$

The finite logarithmic dependence on $s$, $t$, and $u$ remains.

:::caution[Conventions for ε]
Some books use $d=4-\epsilon$ instead of $d=4-2\epsilon$. Pole coefficients then look different by factors of two. Always check the definition of $\epsilon$ before comparing counterterms.
:::

## Vacuum counterterms

The counterterm

$$
-\delta\Lambda
$$

contributes a vacuum vertex with no external legs. In flat-space scattering calculations normalized by $Z[0]$, vacuum bubbles cancel and this term is usually invisible. In the vacuum functional itself,

$$
Z[0]=e^{iW[0]},
$$

it contributes to the vacuum energy density. In gravity or finite-temperature physics, this is not disposable bookkeeping. It is part of the cosmological-constant or free-energy sector.

Thus the same diagrammatic rule has two lives:

| Context | Vacuum counterterm role |
|---|---|
| normalized flat-space correlators | cancels from ratios with $Z[0]$ |
| effective potential | subtracts vacuum-energy divergences |
| finite-temperature partition function | contributes to free energy |
| gravity coupled to QFT | renormalizes the cosmological constant |

## Counterterm order counting

At a given perturbative order, include all diagrams whose total order matches the desired accuracy. A counterterm generated at one loop counts as one loop.

For example, a two-loop four-point calculation includes:

1. ordinary two-loop diagrams made only of renormalized vertices;
2. one-loop diagrams with one one-loop counterterm insertion;
3. tree diagrams with one two-loop counterterm insertion.

Symbolically,

$$
\mathcal A^{(2)}_{\rm ren}
=
\mathcal A^{(2)}_{\rm loops}
+
\mathcal A^{(1)}_{\rm loop\;with\;ct^{(1)}}
+
\mathcal A^{(0)}_{\rm ct^{(2)}}.
$$

This is how subdivergences are removed. A divergent subgraph inside a higher-loop diagram is canceled by a lower-order counterterm insertion. After all subdivergences are subtracted, any remaining overall local divergence is canceled by the counterterm of the current loop order.

This recursive structure is why renormalized perturbation theory works beyond one loop. It is also why counterterms must be organized systematically rather than sprinkled around after the fact like mathematical parmesan.

## Counterterms and schemes

Counterterms are not unique. Their divergent pieces are constrained by the need to cancel regulator dependence. Their finite local pieces define the renormalization scheme.

A few common choices are:

| Scheme | What the counterterms do |
|---|---|
| Minimal subtraction | subtract only $1/\epsilon$ poles |
| Modified minimal subtraction | subtract $1/\overline\epsilon$ poles |
| On-shell scheme | fix physical pole masses and residues |
| Momentum subtraction | fix Green functions at chosen external momenta |

Changing scheme changes the values assigned to renormalized parameters. It does not change physical predictions when the calculation is done consistently to the relevant order. At finite perturbative order, residual scheme dependence estimates uncomputed higher-order terms.

## Counterterms in gauge theories

Gauge theories add an important constraint: counterterms must respect the identities that express gauge redundancy after gauge fixing. In Abelian gauge theory this includes Ward–Takahashi identities. In non-Abelian gauge theory it includes Slavnov–Taylor or BRST identities.

The practical consequence is that counterterms cannot be chosen independently term by term. For example, in QED the relation between vertex and fermion wavefunction renormalization is controlled by the Ward identity. In Yang–Mills theory, the ghost, gauge-field, matter-field, and coupling counterterms are tied together by BRST symmetry.

This page uses scalar examples because they show the subtraction logic without gauge-theory machinery. Gauge-theory counterterms belong to the later chapters on gauge-theory perturbation theory and renormalized perturbation theory.

## Common pitfalls

**Treating counterterms as optional repairs.** Counterterms are part of the perturbative definition once renormalized parameters are chosen. Omitting them is not “doing the loop first”; it is doing an incomplete calculation.

**Canceling nonlocal physics.** A local counterterm can cancel a pole times $1$, $p^2$, $m^2$, or another local polynomial. It cannot cancel a branch cut or finite logarithm of external momentum.

**Mixing schemes.** A mass counterterm chosen on shell and a coupling counterterm chosen in minimal subtraction can be used together only if the hybrid scheme is stated and used consistently.

**Forgetting counterterm order.** A one-loop counterterm inserted in a one-loop graph contributes at two-loop order. Counting only visible loop integrals misses this.

**Double-counting bare and renormalized parameters.** Do not use both the bare coupling and the renormalized coupling plus counterterm as independent vertices. Choose one formulation.

**Ignoring symmetry constraints.** In gauge theories and theories with global symmetries, counterterms must respect the allowed operator basis. A regulator that breaks a symmetry may require symmetry-restoring counterterms when the symmetry is non-anomalous.

## Relations to other pages

- [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/) introduces the idea diagrammatically before loop integrals are developed.
- [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) explains the regulator and the meaning of $1/\overline\epsilon$.
- [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) uses two-point counterterms for mass and wavefunction renormalization.
- [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/) uses coupling counterterms for three- and four-point functions.
- [Vacuum Bubbles](/perturbative-qft/loop-expansion-regularization/vacuum-bubbles/) explains why vacuum counterterms can disappear from normalized correlators but not from vacuum energy.
- [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/) begins the next chapter by systematizing the denominator-combining step used in many one-loop examples.
- The later renormalized perturbation theory chapter systematizes bare parameters, renormalized parameters, and scheme choices.

## Research status

- **Established:** Counterterm insertions are textbook-standard perturbative tools. Their local form follows from locality, symmetry, and power counting, and their coefficients are fixed by a renormalization prescription.
- **Active:** Multi-loop counterterm organization remains a practical research challenge in precision gauge theory, EFT matching, unstable-particle calculations, curved spacetime, thermal QFT, and automated symbolic workflows.
- **Scheme-dependent:** The finite local parts of counterterms are not unique. They define the renormalization scheme.
- **Not physical by themselves:** Individual counterterms are not observables. Physical predictions come from renormalized, scheme-consistent amplitudes or correlation functions.

## Exercises

### Exercise 1: The two-point counterterm rule

Starting from

$$
\mathcal L_{\rm ct}^{(2)}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2,
$$

show that the momentum-space two-point counterterm insertion is

$$
i(p^2\delta Z-\delta m^2).
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\phi(x)=\int\frac{d^dp}{(2\pi)^d}\,e^{-ip\cdot x}\phi(p).
$$

Then

$$
\partial_\mu\phi(x)
=
\int\frac{d^dp}{(2\pi)^d}\,(-ip_\mu)e^{-ip\cdot x}\phi(p).
$$

After integrating over $x$, the quadratic counterterm action becomes

$$
S_{\rm ct}^{(2)}
=
\frac12\int\frac{d^dp}{(2\pi)^d}\,
\phi(-p)\bigl(p^2\delta Z-\delta m^2\bigr)\phi(p).
$$

A vertex insertion from $e^{iS}$ contributes $i$ times the quadratic kernel, so the two-point counterterm factor is

$$
{i(p^2\delta Z-\delta m^2).}
$$

</details>

### Exercise 2: Canceling a momentum-independent self-energy divergence

Suppose a one-loop two-point insertion has divergent part

$$
i\Pi_{\rm loop}^{\rm div}=iA,
$$

where $A$ is independent of $p^2$. Using the two-point counterterm insertion, find a minimal choice of $\delta m^2$ and $\delta Z$ that cancels it.

<details>
<summary><strong>Solution</strong></summary>

The divergent part of the renormalized insertion is

$$
iA+i(p^2\delta Z-\delta m^2).
$$

Since the divergence has no $p^2$ dependence, choose

$$
\delta Z=0,
\qquad
\delta m^2=A.
$$

Then

$$
iA-i\delta m^2=iA-iA=0.
$$

</details>

### Exercise 3: One-loop coupling counterterm in scalar φ⁴ theory

Using the bubble divergence

$$
B(P^2;m^2,m^2)^{\rm div}
=
\frac{1}{16\pi^2}\frac{1}{\overline\epsilon},
$$

and the one-loop four-point contribution

$$
 i\mathcal M_{4,\rm loop}^{(1)}
 =
 \frac{(-i\lambda)^2}{2}\left[I(s)+I(t)+I(u)\right],
\qquad
I(P^2)=-iB(P^2),
$$

find $\delta\lambda^{(1)}_{\rm MS}$ for $d=4-2\epsilon$.

<details>
<summary><strong>Solution</strong></summary>

The divergent part of each channel is

$$
\frac{(-i\lambda)^2}{2}[-iB^{\rm div}]
=
\frac{i\lambda^2}{2}B^{\rm div}.
$$

There are three channels, so

$$
 i\mathcal M_{4,\rm loop}^{(1),\rm div}
 =
 i\frac{3\lambda^2}{2}\frac{1}{16\pi^2}\frac{1}{\overline\epsilon}
 =
 i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}.
$$

The counterterm amplitude is

$$
 i\mathcal M_{4,\rm ct}^{(1)}=-i\delta\lambda.
$$

Cancellation requires

$$
\delta\lambda^{(1)}_{\rm MS}
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}.
$$

</details>

### Exercise 4: Why a logarithm cannot be a counterterm

Explain why a divergent term proportional to $p^2$ can be canceled by a counterterm, but a finite term proportional to $p^2\ln(-p^2/\mu^2)$ cannot be canceled by a local counterterm.

<details>
<summary><strong>Solution</strong></summary>

A local quadratic operator with two derivatives, such as

$$
\partial_\mu\phi\,\partial^\mu\phi,
$$

produces a polynomial factor proportional to $p^2$ in momentum space. More derivatives produce higher powers of $p^2$, but still polynomials.

The function

$$
p^2\ln\frac{-p^2}{\mu^2}
$$

is not a polynomial. It has a branch cut and nonlocal analytic structure. Canceling it would require a nonlocal operator such as a logarithm of the d'Alembertian. Ordinary local counterterms in a local QFT do not do this. The logarithm is therefore part of the finite nonlocal loop correction.

</details>

### Exercise 5: Counterterm order counting

A one-loop mass counterterm is inserted into a one-loop four-point diagram. What loop order does the resulting diagram contribute to, and why?

<details>
<summary><strong>Solution</strong></summary>

The diagram contains one explicit loop integral, but the counterterm coefficient is itself order one loop. Therefore the total perturbative order is two loops.

In general,

$$
\text{total order}
=
\text{explicit loop integrals}
+
\text{loop order of inserted counterterms}.
$$

Thus a one-loop diagram with one one-loop counterterm insertion contributes to the two-loop renormalized amplitude.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§14–20 and §27, for loop corrections, counterterms, and early renormalized perturbation theory in scalar theories.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 9–10, 15–16, and 25, for counterterms, mass renormalization, and the BPHZ perspective.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 6 and 12, for Feynman rules, power counting, and renormalization.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 15–21, for cutoff regularization, counterterms, mass renormalization, and renormalized perturbation theory.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 8–10, for power counting, regularization, renormalization, and dimensional regularization.

## Version history

- **2026-06-12:** Initial polished draft for the Perturbative QFT and Scattering volume. Figures use compact black/gray TikZ style and qft.org mostly-minus scattering conventions.
