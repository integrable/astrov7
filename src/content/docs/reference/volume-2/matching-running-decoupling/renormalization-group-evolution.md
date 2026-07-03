---
title: "Renormalization Group Evolution"
description: "How Wilson coefficients and operator bases are evolved between matching scales and low-energy scales using anomalous-dimension matrices."
sidebar:
  label: "RG Evolution"
  order: 8
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. II, renormalization group methods; Srednicki 2007, RG and EFT chapters; Schwartz 2014, RG and nonrenormalizable theories; Burgess 2020, matching and power counting."
topics:
  - renormalization group evolution
  - Wilson coefficients
  - anomalous dimension matrix
  - operator mixing
  - large logarithms
  - EFT running
canonicalTopics:
  - renormalization-group-evolution
  - wilson-coefficient-running
  - anomalous-dimension-evolution
researchStatus:
  established:
    - "Renormalization group evolution of Wilson coefficients is a standard method for resumming logarithms between separated physical scales."
  active:
    - "High-order anomalous dimensions, multi-threshold EFT evolution, evanescent operators, automated operator bases, and precision resummation remain active technical areas."
---

## Summary

**Renormalization group evolution** is the step between matching and prediction. Matching fixes Wilson coefficients near a heavy scale $M$. Matrix elements are often evaluated near a lower scale $Q$. If $M\gg Q$, fixed-order perturbation theory contains large logarithms such as

$$
\alpha\log\frac{M}{Q},
\qquad
\alpha^2\log^2\frac{M}{Q},
\qquad
\ldots
$$

RG evolution reorganizes these logarithms by running the EFT coefficients from $\mu_M\sim M$ to $\mu_Q\sim Q$:

$$
C_i(\mu_Q)=U_i{}^j(\mu_Q,
\mu_M)C_j(\mu_M).
$$

Here $U$ is the evolution matrix determined by anomalous dimensions and running couplings. In an EFT with many operators, RG evolution is usually a **matrix problem**. Operators mix, coefficients rotate, and the coefficient of one low-energy operator may receive contributions from several high-scale operators.

The physical picture is simple:

$$
\text{match where heavy physics is simple, run where logarithms are simple, evaluate where matrix elements are simple.}
$$

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 54rem;">

![Renormalization group evolution map showing matching at M, coefficient vector evolution by U, operator mixing, thresholds, and low-energy matrix elements](/figures/renormalization-rg-eft/rge-evolution-operator-mixing.svg)

<figcaption>

RG evolution transports Wilson coefficients from a matching scale $\mu_M$ to a low-energy scale $\mu_Q$. The evolution matrix $U(\mu_Q,\mu_M)$ resums logarithms and accounts for operator mixing; additional threshold matchings are inserted when the degrees of freedom change.

</figcaption>
</figure>

## Prerequisites

You should know [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), and [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/).

For the matching side, review [Tree-Level Matching](/renormalization-rg-eft/matching-running-decoupling/tree-level-matching/), [One-Loop Matching](/renormalization-rg-eft/matching-running-decoupling/one-loop-matching/), [Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/), and [Matching with Background Fields](/renormalization-rg-eft/matching-running-decoupling/matching-with-background-fields/).

## Core idea

An EFT prediction often has the schematic form

$$
\mathcal A(Q)=\sum_i C_i(\mu)\langle \mathcal O_i(\mu)\rangle_Q.
$$

The scale $\mu$ is arbitrary. The Wilson coefficients and renormalized operators separately depend on $\mu$, but the physical amplitude does not:

$$
\mu\frac{d}{d\mu}\mathcal A(Q)=0.
$$

This condition determines how $C_i(\mu)$ must run once the operator anomalous dimensions are known. If the renormalized operators obey

$$
\left.\mu\frac{d}{d\mu}\mathcal O_i(\mu)\right|_{\text{bare}}
=-\gamma_i{}^j(\mu)\mathcal O_j(\mu),
$$

then the coefficient row vector obeys

$$
\mu\frac{d}{d\mu}C_i(\mu)=C_j(\mu)\gamma_j{}^i(\mu).
$$

Equivalently, for a column vector $C$, one writes

$$
\mu\frac{d}{d\mu}C(\mu)=\gamma^T(\mu)C(\mu).
$$

This transpose is not deep physics. It is bookkeeping. Operators and coefficients transform dually so that $C_i\mathcal O_i$ is invariant.

## Setup and conventions

This page uses the anomalous-dimension convention stated in [Conventions and Notation](/renormalization-rg-eft/conventions/):

$$
\mathcal O_{i,0}=Z_i{}^j\mathcal O_{j,R},
\qquad
\gamma_i{}^j=(Z^{-1})_i{}^k\left.\mu\frac{dZ_k{}^j}{d\mu}\right|_{\text{bare}}.
$$

Therefore

$$
\left.\mu\frac{d}{d\mu}\mathcal O_{i,R}\right|_{\text{bare}}
=-\gamma_i{}^j\mathcal O_{j,R}.
$$

For the EFT Lagrangian we write

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\text{light}}
+\sum_i C_i(\mu)\mathcal O_i(\mu).
$$

The Wilson coefficients satisfy

$$
\mu\frac{d}{d\mu}C_i=C_j\gamma_j{}^i,
$$

or, in column-vector notation,

$$
\frac{dC}{d\log\mu}=\gamma^T C.
$$

Many EFT papers define the anomalous-dimension matrix with the opposite sign or put the transpose into the definition of $\gamma$. Always check the convention before comparing formulas. The physics is the invariance of $C_i\mathcal O_i$, not the typography of the matrix.

## Why RG evolution is needed

Suppose a heavy particle of mass $M$ is integrated out and a low-energy observable is measured at $Q\ll M$. Matching at $\mu=M$ avoids large logarithms in the coefficient:

$$
C(M)=C^{(0)}+\frac{\alpha(M)}{4\pi}C^{(1)}+\cdots.
$$

But evaluating matrix elements at $Q$ may generate terms such as

$$
\frac{\alpha}{4\pi}C^{(0)}\log\frac{M}{Q}.
$$

If the logarithm is large, the nominal loop expansion becomes poorly organized. RG evolution resums the tower of logarithms by solving differential equations:

$$
C(Q)=U(Q,M)C(M).
$$

At leading-logarithmic accuracy, $U$ resums terms of the schematic form

$$
\left(\alpha\log\frac{M}{Q}\right)^n.
$$

At next-to-leading and higher accuracy, it resums additional towers involving more powers of $\alpha$ and fewer logarithms. The precise counting depends on the observable and the EFT.

The workflow is therefore:

$$
\text{high-scale matching}
\longrightarrow
\text{RG evolution}
\longrightarrow
\text{low-scale matrix elements}.
$$

## The evolution matrix

The formal solution of

$$
\frac{dC}{d\log\mu}=\gamma^T(g(\mu),\mu)C
$$

is

$$
C(\mu_2)=U(\mu_2,\mu_1)C(\mu_1),
$$

where

$$
U(\mu_2,\mu_1)
=
P\exp\left[
\int_{\log\mu_1}^{\log\mu_2}dt\,\gamma^T(g(t),t)
\right].
$$

The symbol $P$ means path ordering. It is needed when anomalous-dimension matrices at different scales do not commute:

$$
[\gamma(t_1),\gamma(t_2)]\neq0.
$$

The evolution matrix satisfies

$$
U(\mu_3,\mu_1)=U(\mu_3,\mu_2)U(\mu_2,\mu_1),
\qquad
U(\mu_1,\mu_1)=\mathbf 1.
$$

This composition law is one of the best sanity checks on an RG calculation. Evolution from $M$ to $Q$ should not depend on the arbitrary intermediate scale used to split the calculation.

## Constant anomalous dimension

If $\gamma$ is approximately constant over the range of scales, then

$$
C(\mu_2)
=\exp\left[\gamma^T\log\frac{\mu_2}{\mu_1}\right]C(\mu_1).
$$

For a single coefficient this reduces to

$$
C(\mu_2)
=C(\mu_1)\left(\frac{\mu_2}{\mu_1}\right)^\gamma.
$$

For several coefficients, diagonalizing $\gamma^T$ gives eigenoperators and eigencoefficients. If

$$
\gamma^T v_a=\lambda_a v_a,
$$

then the component of $C$ along $v_a$ scales as

$$
\left(\frac{\mu_2}{\mu_1}\right)^{\lambda_a}.
$$

This is the finite-scale version of the fixed-point statement that scaling operators diagonalize the linearized RG flow.

## Running couplings inside anomalous dimensions

Usually $\gamma$ depends on running couplings. Consider a single running coupling $g$ with

$$
\frac{dg}{d\log\mu}=\beta(g),
\qquad
\frac{dC}{d\log\mu}=\gamma_C(g)C.
$$

Then

$$
\frac{d\log C}{dg}=\frac{\gamma_C(g)}{\beta(g)}.
$$

Therefore

$$
C(\mu_2)
=C(\mu_1)
\exp\left[
\int_{g(\mu_1)}^{g(\mu_2)}dg\,\frac{\gamma_C(g)}{\beta(g)}
\right].
$$

If

$$
\beta(g)=b g^3+O(g^5),
\qquad
\gamma_C(g)=a g^2+O(g^4),
$$

then at leading order

$$
C(\mu_2)
=C(\mu_1)
\left[\frac{g(\mu_2)}{g(\mu_1)}\right]^{a/b}.
$$

This compact formula is often the safest way to remember the sign: derive it from your own beta-function and anomalous-dimension conventions.

## Leading-logarithmic expansion

If the coupling is treated as approximately constant and the anomalous dimension begins as

$$
\gamma^T=\frac{\alpha}{4\pi}\gamma_0^T+O(\alpha^2),
$$

then

$$
C(\mu_Q)
=
\left[
1+\frac{\alpha}{4\pi}\gamma_0^T\log\frac{\mu_Q}{\mu_M}
+\frac{1}{2}\left(\frac{\alpha}{4\pi}\right)^2(\gamma_0^T)^2\log^2\frac{\mu_Q}{\mu_M}
+\cdots
\right]C(\mu_M).
$$

This displays the resummation of repeated logarithms. If $\mu_Q<Q$ is chosen poorly or $\mu_M$ is far from $M$, extra logarithms appear in matching or matrix elements. The art is to put each calculation at the scale where it is boring.

Good scale choices are typically

$$
\mu_M\sim M,
\qquad
\mu_Q\sim Q.
$$

Boring is a compliment here. Boring perturbative coefficients are what you get when the RG has done its job.

## Operator mixing

In an EFT, operators with the same quantum numbers and compatible dimensions can mix. A simple two-operator example is

$$
\frac{d}{d\log\mu}
\begin{pmatrix}
C_1\\
C_2
\end{pmatrix}
=
\begin{pmatrix}
\gamma_{11} & \gamma_{21}\\
\gamma_{12} & \gamma_{22}
\end{pmatrix}
\begin{pmatrix}
C_1\\
C_2
\end{pmatrix},
$$

where the placement of indices follows the column-vector convention. Even if $C_2(\mu_M)=0$, it may be generated by running if the off-diagonal entry is nonzero:

$$
C_2(\mu_Q)\neq0.
$$

This is not a small bookkeeping detail. Many low-energy observables are dominated by coefficients generated through mixing rather than by coefficients present at tree-level matching.

Mixing is constrained by:

| Constraint | Consequence |
|---|---|
| Lorentz symmetry | only same tensor type can mix |
| gauge symmetry | only same gauge representation and charge sector can mix |
| global symmetries | preserve flavor, baryon number, parity, or their breaking spurions |
| dimension in mass-independent schemes | lower-dimension operators generally do not receive contributions from higher-dimension operators without mass insertions |
| equations of motion | redundant sectors can mix with physical sectors unless the basis is handled carefully |
| evanescent operators | operators vanishing in four dimensions can affect finite physical anomalous dimensions |

A published anomalous-dimension matrix is therefore inseparable from its basis and scheme.

## Thresholds and piecewise evolution

If the energy interval contains several heavy thresholds, evolution is piecewise. Suppose

$$
M_1>M_2>Q.
$$

Then the coefficient vector evolves as

$$
C(Q)
=U_{\text{EFT}_2}(Q,M_2)
R(M_2)
U_{\text{EFT}_1}(M_2,M_1)
C(M_1),
$$

where $R(M_2)$ is a threshold matching matrix relating the coefficient basis above and below $M_2$.

The steps are:

1. match at $M_1$;
2. run in the EFT valid below $M_1$ but above $M_2$;
3. match across $M_2$;
4. run in the lower EFT;
5. evaluate matrix elements near $Q$.

The number of active degrees of freedom changes at thresholds. So do beta functions, anomalous dimensions, and sometimes the operator basis.

## Scheme and basis dependence

Let the operator basis change by an invertible matrix $R(\mu)$:

$$
\mathcal O'=R\mathcal O.
$$

Since

$$
C^T\mathcal O=C^{\prime T}\mathcal O',
$$

we must have

$$
C'=R^{-T}C.
$$

The anomalous-dimension matrix changes accordingly. If $R$ depends on $\mu$, the transformed matrix includes an inhomogeneous term:

$$
\gamma'
=R\gamma R^{-1}-\frac{dR}{d\log\mu}R^{-1},
$$

up to the same row-versus-column convention used above.

This is the operator version of scheme dependence. The coefficient vector and anomalous-dimension matrix are coordinates. The amplitude

$$
\mathcal A=C_i\langle\mathcal O_i\rangle
$$

is the invariant object.

## Matching-scale independence

A consistent EFT prediction should not depend on the arbitrary matching scale, up to higher-order truncation errors. Suppose matching gives $C(\mu_M)$ and evolution gives $U(\mu_Q,\mu_M)$. Then

$$
C(\mu_Q)=U(\mu_Q,\mu_M)C(\mu_M).
$$

Changing $\mu_M$ changes both $C(\mu_M)$ and $U(\mu_Q,\mu_M)$. The changes cancel when matching and running are computed to compatible orders.

This provides a practical error estimate. Residual dependence on $\mu_M$ or $\mu_Q$ after truncation is often used as a diagnostic for missing higher-order terms. It is not a theorem that scale variation is a perfect uncertainty estimate, but it is a useful stress test.

## Example: one operator with one anomalous dimension

Consider

$$
\mathcal L_{\text{EFT}}\supset C(\mu)\mathcal O(\mu)
$$

with

$$
\frac{dC}{d\log\mu}=\gamma C,
$$

where $\gamma$ is approximately constant. Then

$$
C(Q)=C(M)\left(\frac{Q}{M}\right)^\gamma.
$$

Expanding for small $\gamma$ gives

$$
C(Q)=C(M)\left[1+\gamma\log\frac{Q}{M}+O(\gamma^2\log^2)\right].
$$

If the fixed-order calculation contains $\gamma\log(Q/M)$, the RG solution supplies the higher powers implied by repeated scale evolution.

The sign of $\gamma$ determines whether the coefficient grows or shrinks toward the infrared. But remember: the operator matrix element has the compensating scale dependence.

## Example: two-operator triangular mixing

Suppose

$$
\frac{d}{d\log\mu}
\begin{pmatrix}
C_1\\
C_2
\end{pmatrix}
=
\begin{pmatrix}
\gamma_1 & 0\\
\eta & \gamma_2
\end{pmatrix}
\begin{pmatrix}
C_1\\
C_2
\end{pmatrix},
$$

with constant entries. If $C_2(M)=0$, then

$$
C_1(\mu)=C_1(M)\left(\frac{\mu}{M}\right)^{\gamma_1},
$$

and

$$
C_2(\mu)
=\eta C_1(M)
\left(\frac{\mu}{M}\right)^{\gamma_2}
\int_{\log M}^{\log\mu}dt\,
\exp\left[(\gamma_1-\gamma_2)(t-\log M)\right].
$$

If $\gamma_1\neq\gamma_2$, this gives

$$
C_2(\mu)
=\frac{\eta}{\gamma_1-\gamma_2}C_1(M)
\left[
\left(\frac{\mu}{M}\right)^{\gamma_1}
-
\left(\frac{\mu}{M}\right)^{\gamma_2}
\right].
$$

Thus an operator absent at matching can appear at low energy. This is one of the main reasons EFT calculations are matrix calculations rather than coefficient-by-coefficient folklore.

## RG invariance of amplitudes

Let

$$
\mathcal A=C_i(\mu)\langle\mathcal O_i(\mu)\rangle.
$$

Using

$$
\frac{dC_i}{d\log\mu}=C_j\gamma_j{}^i,
\qquad
\frac{d\mathcal O_i}{d\log\mu}=-\gamma_i{}^j\mathcal O_j,
$$

we find

$$
\frac{d\mathcal A}{d\log\mu}
=
C_j\gamma_j{}^i\langle\mathcal O_i\rangle
-C_i\gamma_i{}^j\langle\mathcal O_j\rangle
=0,
$$

after relabeling dummy indices. This cancellation is the heart of RG evolution. Coefficients run because operators run in the opposite dual way.

When matrix elements are computed perturbatively, they may contain explicit logarithms of $\mu/Q$. Choosing $\mu\sim Q$ keeps those logarithms small. The coefficient evolution has already carried the logarithms of $M/Q$ from the high scale.

## Logarithmic accuracy

RG-improved EFT calculations are often labeled by logarithmic accuracy:

| Accuracy | Typical ingredients |
|---|---|
| leading log | tree-level matching, one-loop anomalous dimensions, one-loop beta functions |
| next-to-leading log | one-loop matching, two-loop anomalous dimensions or beta functions where needed |
| next-to-next-to-leading log | higher matching and higher anomalous dimensions |

The exact requirements depend on the observable. For example, if a coefficient first appears at one loop, the counting shifts. If the leading anomalous dimension vanishes, higher-order terms become leading. If several couplings run, the bookkeeping becomes more intricate.

A careful page or paper should say what accuracy is being claimed and which ingredients are included. "RG improved" by itself is not a precision statement.

## Evolution with multiple couplings

If several couplings run, then

$$
\frac{dC}{d\log\mu}
=\gamma^T(g_1(\mu),g_2(\mu),\ldots)C,
$$

with

$$
\frac{dg_a}{d\log\mu}=\beta_a(g_1,g_2,\ldots).
$$

The solution still has the path-ordered form

$$
U=P\exp\int d\log\mu\,\gamma^T(g_a(\mu)).
$$

In practice one may solve the coupled equations numerically, diagonalize approximate blocks, or expand perturbatively in small couplings. The conceptual issue is unchanged: the Wilson coefficient vector is transported along an RG trajectory in the coupling space of the EFT.

Multiple couplings matter in realistic applications. Gauge couplings, Yukawa couplings, scalar couplings, and lower-dimension parameters can all enter anomalous dimensions. Operator sectors may mix only after certain symmetry-breaking spurions are included.

## Evanescent operators

In dimensional regularization, some operators vanish algebraically in exactly four dimensions but not in $d=4-2\epsilon$. These are **evanescent operators**. They can mix into physical operators through poles times $O(\epsilon)$ differences, producing finite effects.

The typical pattern is

$$
\frac{1}{\epsilon}\times \epsilon = \text{finite}.
$$

Therefore one cannot always discard evanescent operators before renormalization. Their effects are scheme dependent, but physical predictions are not when the scheme is handled consistently.

This issue is especially common in four-fermion operator bases, gamma-matrix identities, Fierz transformations, and chiral theories. It is a good way for otherwise dignified calculations to step on a rake.

## RG evolution versus running couplings

Running Wilson coefficients are not the same thing as running fundamental couplings, but the equations are structurally similar.

A renormalizable gauge coupling satisfies

$$
\mu\frac{dg}{d\mu}=\beta_g(g).
$$

An EFT coefficient satisfies

$$
\mu\frac{dC_i}{d\mu}=C_j\gamma_j{}^i(g).
$$

The beta function describes flow of couplings in the EFT Lagrangian. The anomalous-dimension matrix describes how local operators and their coefficients are renormalized by loops. In practice these are coupled: $\gamma$ depends on $g(\mu)$, and some Wilson coefficients can feed into beta functions at higher order or in nonlinear EFT truncations.

The phrase "running" therefore has several meanings. Always ask: which parameter is running, in which EFT, and with which degrees of freedom active?

## RG evolution and physical interpretation

RG evolution is sometimes described as "integrating out shells" between $M$ and $Q$. That intuition is Wilsonian and useful. In renormalized perturbation theory, however, $\mu$ is a subtraction scale, not a physical cutoff. The evolution equation follows from independence of bare quantities and physical predictions from $\mu$.

Both descriptions lead to the same practical message. Physics at widely separated scales should not be computed with a single fixed-order expression containing large logarithms. One should factorize the calculation into pieces adapted to their natural scales.

For EFT, the pieces are:

$$
\text{short-distance matching coefficients},
\qquad
\text{RG evolution},
\qquad
\text{low-energy matrix elements}.
$$

Each piece can be computed with small logarithms and then combined.

## Common pitfalls

**Forgetting the transpose.** Operator anomalous dimensions and coefficient anomalous dimensions are dual. If your equation differs by a transpose from another paper, first check row-versus-column conventions before panicking.

**Running in the wrong EFT.** The beta functions and anomalous dimensions depend on the active degrees of freedom. If a heavy field has been integrated out, it should not keep contributing below its threshold except through Wilson coefficients.

**Mixing without a basis.** A matrix is meaningless until the operator basis, normalization, scheme, and evanescent-operator conventions are specified.

**Matching at one scale and evaluating at another without running.** This leaves large logarithms in the prediction and can spoil perturbative convergence.

**Double counting threshold logarithms.** Logs assigned to matching should not also be generated by running over the same scale interval.

**Treating residual scale dependence as a theorem-level error bar.** Scale variation is a diagnostic, not a rigorous uncertainty estimate.

**Discarding evanescent operators too early.** Operators that vanish in four dimensions can still affect finite anomalous dimensions in dimensional regularization.

## Relations to other pages

[Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/) introduces the physical motivation for coefficient running. This page gives the chapter-level matching-and-running workflow, with emphasis on evolution matrices, thresholds, and operator mixing.

[Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/) explains how to cross a mass threshold. [Matching with Background Fields](/renormalization-rg-eft/matching-running-decoupling/matching-with-background-fields/) explains how high-scale coefficients can be extracted before evolution begins. [Operator Basis Choice](/renormalization-rg-eft/matching-running-decoupling/operator-basis-choice/) will explain how basis choices affect the matrices used here.

For the underlying RG equations, see [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), and [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/). For operator mixing, see [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/) and [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/).

## Research status

RG evolution of Wilson coefficients is established and central in EFT. It is used throughout weak decays, QCD factorization, SMEFT, chiral EFT, heavy-quark EFT, SCET, condensed-matter EFT, and gravitational EFT.

Active technical work includes higher-loop anomalous-dimension matrices, automated basis transformations, evanescent-operator schemes, nonlinear EFTs, resummation beyond leading power, EFTs with many thresholds, and consistent uncertainty estimates for precision phenomenology.

The conceptual status is stable: RG evolution is the statement that physical predictions are independent of the arbitrary renormalization scale. The implementation can be highly nontrivial, but the principle is not optional.

## Exercises

### Exercise 1: Coefficients run oppositely to operators

Assume

$$
\frac{d\mathcal O_i}{d\log\mu}=-\gamma_i{}^j\mathcal O_j.
$$

Derive the coefficient RGE required by RG invariance of $\mathcal L\supset C_i\mathcal O_i$.

<details><summary><strong>Solution</strong></summary>

Demand

$$
0=\frac{d}{d\log\mu}(C_i\mathcal O_i)
=\frac{dC_i}{d\log\mu}\mathcal O_i
-C_i\gamma_i{}^j\mathcal O_j.
$$

Relabel the dummy index in the second term so that it multiplies $\mathcal O_i$:

$$
-C_j\gamma_j{}^i\mathcal O_i.
$$

Therefore

$$
\frac{dC_i}{d\log\mu}=C_j\gamma_j{}^i,
$$

up to the index-placement convention. In column-vector notation this is $dC/d\log\mu=\gamma^T C$.

</details>

### Exercise 2: One-coefficient evolution with running coupling

Let

$$
\frac{dg}{d\log\mu}=b g^3,
\qquad
\frac{dC}{d\log\mu}=a g^2 C.
$$

Solve for $C(\mu_2)$ in terms of $C(\mu_1)$ and the running coupling values.

<details><summary><strong>Solution</strong></summary>

Divide the two RG equations:

$$
\frac{d\log C}{dg}
=\frac{a g^2}{b g^3}
=\frac{a}{b}\frac1g.
$$

Integrating from $g(\mu_1)$ to $g(\mu_2)$ gives

$$
\log\frac{C(\mu_2)}{C(\mu_1)}
=\frac{a}{b}\log\frac{g(\mu_2)}{g(\mu_1)}.
$$

Thus

$$
C(\mu_2)=C(\mu_1)
\left[\frac{g(\mu_2)}{g(\mu_1)}\right]^{a/b}.
$$

</details>

### Exercise 3: Triangular mixing at first order

Suppose

$$
\frac{dC_1}{dt}=0,
\qquad
\frac{dC_2}{dt}=\eta C_1,
\qquad
t=\log\mu,
$$

with $C_2(M)=0$. Find $C_2(Q)$.

<details><summary><strong>Solution</strong></summary>

Since $dC_1/dt=0$, $C_1$ is constant:

$$
C_1(t)=C_1(M).
$$

Integrating the second equation from $t_M=\log M$ to $t_Q=\log Q$ gives

$$
C_2(Q)-C_2(M)=\eta C_1(M)(t_Q-t_M).
$$

Using $C_2(M)=0$,

$$
C_2(Q)=\eta C_1(M)\log\frac{Q}{M}.
$$

This is the leading-logarithmic generation of $C_2$ from $C_1$.

</details>

### Exercise 4: Matching-scale cancellation

Let a coefficient matched at $\mu_M$ have

$$
C(\mu_M)=C_0\left[1+a\alpha\log\frac{\mu_M}{M}\right]
$$

and run according to

$$
\frac{dC}{d\log\mu}=a\alpha C
$$

with constant $\alpha$ to this order. Show that $C(\mu_Q)$ is independent of the arbitrary intermediate scale $\mu_M$ through $O(\alpha)$.

<details><summary><strong>Solution</strong></summary>

Running from $\mu_M$ to $\mu_Q$ gives

$$
C(\mu_Q)=C(\mu_M)\left[1+a\alpha\log\frac{\mu_Q}{\mu_M}\right]+O(\alpha^2).
$$

Substitute the matching result:

$$
C(\mu_Q)=C_0\left[1+a\alpha\log\frac{\mu_M}{M}
+a\alpha\log\frac{\mu_Q}{\mu_M}\right]+O(\alpha^2).
$$

The two logarithms combine to

$$
\log\frac{\mu_M}{M}+\log\frac{\mu_Q}{\mu_M}
=\log\frac{\mu_Q}{M}.
$$

Therefore

$$
C(\mu_Q)=C_0\left[1+a\alpha\log\frac{\mu_Q}{M}\right]+O(\alpha^2),
$$

which is independent of $\mu_M$ through the order being kept.

</details>

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the chapter on renormalization group methods, large logarithms, mass effects, and critical phenomena.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on the renormalization group and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on renormalization, running couplings, nonrenormalizable theories, EFT, HQET, and SCET.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on power counting, matching, dimensional regularization, and exact RG logic.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for anomalous dimensions, operator mixing, RG equations, and critical applications.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations" and "Secret Symmetry" for the physical use of RG equations and scaling.

## Version history

- 2026-06-18: First polished draft. Added coefficient/operator duality, evolution matrices, leading-log solutions, operator mixing, threshold composition, scheme and basis transformations, evanescent-operator caveats, exercises, and figure.
