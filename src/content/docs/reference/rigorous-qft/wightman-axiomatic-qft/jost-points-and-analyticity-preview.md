---
title: "Jost Points and Analyticity Preview"
description: "Explains the tube-domain analyticity of Wightman functions, the definition of Jost points, and why these real extended-tube configurations power the CPT and spin–statistics theorems."
sidebar:
  label: "Jost Points and Analyticity"
  order: 11
level: Advanced
status: "Polished draft"
source: "Wightman; Bargmann–Hall–Wightman; Jost; Streater–Wightman; Bros–Epstein–Glaser; Tomozawa."
topics:
  - Jost points
  - tube domains
  - Wightman functions
  - analyticity
  - edge-of-the-wedge theorem
  - CPT theorem
canonicalTopics:
  - jost-points
  - wightman-analyticity
  - axiomatic-quantum-field-theory
researchStatus:
  established:
    - "The spectral condition implies tube-domain analyticity of Wightman functions, and locality at Jost points is a standard route to CPT, spin–statistics, and related structural theorems."
  active:
    - "The detailed extension of analyticity to scattering amplitudes, massless theories, gauge theories, curved spacetime, and non-Wightman frameworks requires extra hypotheses and more specialized tools."
---

## Summary

Jost points are special real configurations of spacetime points that lie in the real section of the extended analytic domains of Wightman functions. They are the places where locality, Lorentz covariance, and positive energy meet.

For an $n$-point Wightman function, use the relative variables

$$
\xi_j=x_j-x_{j+1},
\qquad
j=1,\ldots,n-1.
$$

A real tuple $(\xi_1,\ldots,\xi_{n-1})$ is a Jost point if every nonzero positive linear combination is spacelike:

$$
\left(\sum_{j=1}^{n-1}\lambda_j\xi_j\right)^2<0
\qquad
\text{for all }\lambda_j\ge0
\text{ not all zero}.
$$

For $n=2$, this is just spacelike separation. For $n\ge3$, it is stronger than saying that adjacent or pairwise separations are spacelike. This stronger condition is exactly what makes the tuple sit in the real part of the extended tube.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Tube analyticity, extended tubes, and Jost points for Wightman functions](/figures/rigorous-qft/jost-points-analyticity.svg)

<figcaption>

Positive energy gives analyticity in the primitive tube selected by the forward cone. Complex Lorentz covariance enlarges it to the extended tube, whose real section contains Jost points. Locality supplies equality on this real edge, and edge-of-the-wedge arguments propagate those equalities through analytic continuation.

</figcaption>
</figure>

## Prerequisites

You should know [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/), [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/), [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/), [CPT Theorem](/rigorous-qft/wightman-axiomatic-qft/cpt-theorem/), and [Spin–Statistics Theorem](/rigorous-qft/wightman-axiomatic-qft/spin-statistics-theorem/).

This page uses only the minimal language of several complex variables. The goal is orientation: to explain what the analytic domains are doing in the Wightman proofs, not to replace a mathematical treatment of tube domains, envelopes of holomorphy, or the edge-of-the-wedge theorem.

## Logical status

| Item | Status |
|---|---|
| Type | Concept and theorem-preview page. |
| Framework | Wightman functions on Minkowski spacetime. |
| Main input | Translation invariance, spectral support in $\overline V_+$, Lorentz covariance, and locality. |
| Main output | Analytic continuations of Wightman functions and real Jost configurations where locality becomes an analytic real-edge identity. |
| Used for | CPT theorem, spin–statistics theorem, analytic continuation, and scattering analyticity previews. |
| Main caveat | This page suppresses many technical hypotheses on domains, distributions, and boundary values. |

## Core idea

Wightman functions are distributions on real Minkowski spacetime, but the spectral condition secretly makes them boundary values of holomorphic functions. This is the analytic engine behind much of axiomatic QFT.

The simplest example is a two-point function. If

$$
W_2(x)=\int_{\overline V_+} e^{-ip\cdot x}\,d\mu(p),
$$

then define

$$
z=x-iy,
\qquad
 y\in V_+.
$$

The analytic continuation is

$$
W_2(z)=\int_{\overline V_+}e^{-ip\cdot z}\,d\mu(p)
=
\int_{\overline V_+}e^{-ip\cdot x}e^{-p\cdot y}\,d\mu(p).
$$

Since $p\in\overline V_+$ and $y\in V_+$ imply $p\cdot y\ge0$, the exponential has damping rather than growth. This is the reason the forward light cone appears in complex spacetime.

The many-point case is the same idea applied to the relative variables $\xi_j=x_j-x_{j+1}$. The function is holomorphic when each relative variable is shifted by a negative imaginary future-timelike vector.

## Tube domains

Let $V_+$ be the open future light cone in the mostly-minus convention:

$$
V_+=\{y\in\mathbb R^d:y^0>0,\ y^2>0\}.
$$

For an $n$-point Wightman function, use relative variables

$$
\xi=(\xi_1,\ldots,\xi_{n-1}),
\qquad
\xi_j=x_j-x_{j+1}.
$$

The **primitive forward tube** is

$$
\mathcal T_{n-1}
=
\{\zeta_j=\xi_j-i\eta_j:
\xi_j\in\mathbb R^d,
\eta_j\in V_+\}.
$$

The spectral condition implies that the Wightman distribution is the boundary value of a holomorphic function

$$
F_n(\zeta_1,
\ldots,
\zeta_{n-1})
$$

on $\mathcal T_{n-1}$.

The primitive tube itself has no real points: all its points have imaginary parts in future cones. To get useful real configurations, one combines tube analyticity with Lorentz covariance. The complex proper Lorentz group acts on complexified Minkowski space, and the **extended tube** is the orbit

$$
\mathcal T'_{n-1}
=
L_+(\mathbb C)\,\mathcal T_{n-1}.
$$

The extended tube is larger than the primitive tube and can contain real points. Those real points are the Jost points.

## Definition of Jost points

A real tuple

$$
\xi=(\xi_1,\ldots,\xi_{n-1})
$$

is a Jost point if

$$
\left(\sum_{j=1}^{n-1}\lambda_j\xi_j\right)^2<0
$$

for every choice of real coefficients satisfying

$$
\lambda_j\ge0,
\qquad
(\lambda_1,
\ldots,\lambda_{n-1})\neq0.
$$

In words: the whole open convex cone generated by the successive differences must consist of spacelike vectors.

For $n=2$, there is one relative variable, and the condition becomes

$$
(x_1-x_2)^2<0.
$$

For $n=3$, the condition says that

$$
\xi_1^2<0,
\qquad
\xi_2^2<0,
\qquad
(\lambda_1\xi_1+
\lambda_2\xi_2)^2<0
$$

for all $\lambda_1,\lambda_2\ge0$ not both zero. The last condition is the important one.

## Pairwise spacelike is not enough

It is tempting to identify Jost points with configurations where all fields are pairwise spacelike separated. That is safe for two fields and unsafe in general.

In $1+1$ dimensions with mostly-minus metric, take two successive differences

$$
\xi_1=(0,1),
\qquad
\xi_2=(2,-4).
$$

The two adjacent separations and the total separation are all spacelike:

$$
\xi_1^2=-1,
\qquad
\xi_2^2=4-16=-12,
\qquad
(\xi_1+\xi_2)^2=4-9=-5.
$$

Thus the three points are pairwise spacelike separated. But a different positive linear combination is timelike:

$$
\xi_1+\frac14\xi_2
=
\left(\frac12,0\right),
\qquad
\left(\xi_1+\frac14\xi_2\right)^2
=
\frac14>0.
$$

Therefore the tuple is not a Jost point. The obstruction is not only the finite list of pairwise separations; it is the whole positive cone generated by the ordered successive differences.

This distinction matters because the analytic theorem is not merely about pairwise causality. It is about whether the ordered real configuration belongs to the real section of the extended tube.

## Weak local commutativity

Locality is an operator statement: fields commute or graded-commute at spacelike separation. Jost's theorem uses a weaker-looking correlation-function statement called **weak local commutativity**.

For scalar fields, weak local commutativity at Jost points says schematically that

$$
W_n(x_1,
\ldots,x_n)
=
W_n(x_n,
\ldots,x_1)
$$

whenever $(x_1-x_2,\ldots,x_{n-1}-x_n)$ is a Jost configuration. For fields with fermionic parity, the right-hand side includes the corresponding graded sign. For spinning or charged fields, it also includes the appropriate component and conjugation matrices.

Why is this enough? Because Wightman functions determine the vacuum-generated Hilbert-space sector. If two field-polynomial expressions have the same vacuum matrix elements against a dense set of field-polynomial states, cyclicity and positivity turn the identity into an operator statement on the common domain.

Weak local commutativity is therefore weaker in appearance but not weak in consequence once the Wightman framework is in place.

## Edge-of-the-wedge logic

The edge-of-the-wedge theorem is a several-complex-variable continuation theorem. In the present setting, the moral version is:

> If two holomorphic functions live in adjacent tube-like domains and have the same distributional boundary value on a sufficiently large real edge, then they are restrictions of one holomorphic function on a larger domain.

In Wightman QFT, different orderings of fields give different Wightman functions and hence different primitive tubes. Locality tells us that, on real spacelike configurations, their boundary values agree up to graded signs. The edge-of-the-wedge theorem then glues the corresponding analytic functions.

This is the mechanism by which a local equality at real spacelike points becomes a global analytic relation among Wightman functions.

The proof is subtle because Wightman functions are distributions, not ordinary functions on real spacetime. The boundary equality is therefore a statement about distributional boundary values of holomorphic functions.

## Why Jost points power CPT

The CPT theorem can be formulated in terms of Wightman functions. For a neutral scalar theory, the relevant identity is roughly

$$
W_n(x_1,\ldots,x_n)
=
W_n(-x_n,\ldots,-x_1)
$$

with complex conjugation in the smeared antiunitary formulation.

Jost points enter because the complex Lorentz group can connect the analytic continuation of one ordering to the analytic continuation of the reversed ordering through the extended tube. Locality supplies the needed equality at Jost points, and the Wightman reconstruction theorem turns the correlation-function symmetry into the antiunitary CPT operator.

A concise version of the logic is

$$
\begin{gathered}
\operatorname{Spec}(P)\subset\overline V_+
\Rightarrow
\text{tube analyticity},\\
\text{Lorentz covariance}
\Rightarrow
\text{extended tube},\\
\text{locality at Jost points}
\Rightarrow
\text{CPT correlation identity},\\
\text{reconstruction}
\Rightarrow
\text{antiunitary CPT operator}.
\end{gathered}
$$

This is why the CPT theorem is not a diagrammatic accident. It is encoded in the analytic geometry forced by positive energy and locality.

## Why Jost points power spin–statistics

The spin–statistics theorem uses the same analytic machinery, but the comparison is slightly different. At spacelike configurations, locality says that exchanging fields changes a Wightman function by the field's graded exchange sign. Complex Lorentz covariance also supplies a sign from the central element of the spin representation.

For a field transforming in an irreducible Lorentz representation $(j,k)$, the central sign is

$$
D_{(j,k)}(-1)=(-1)^{2(j+k)}.
$$

Analytic continuation compares this Lorentz sign with the locality sign. Hilbert positivity and cyclicity then rule out the mismatch for a nonzero field. The result is

$$
\text{integer spin}\Rightarrow\text{Bose locality},
\qquad
\text{half-integer spin}\Rightarrow\text{Fermi locality}.
$$

Thus CPT and spin–statistics are neighboring theorems: both live at the intersection of tube analyticity, Lorentz covariance, locality, and positivity.

## Relation to scattering analyticity

The Wightman analytic structure is also one origin of analyticity statements for scattering amplitudes. But there is an important boundary: an analytic statement about Wightman functions is not automatically a complete analytic statement about the physical $S$-matrix.

To pass from Wightman functions to scattering amplitudes one typically needs additional ingredients, such as a mass gap, Haag–Ruelle scattering theory, LSZ-type limits, control of singularities, and assumptions excluding severe infrared pathologies. The classic rigorous analyticity program for scattering amplitudes is therefore more specialized than the tube-domain story on this page.

A safe hierarchy is

$$
\text{Wightman axioms}
\Rightarrow
\text{correlator analyticity}
\Rightarrow
\text{some structural theorems},
$$

but

$$
\text{full scattering analyticity}
$$

requires more than the one-line slogan "correlators are analytic."

## Common pitfalls

**Thinking Jost points are just pairwise spacelike points.** For $n\ge3$, the positive cone condition is stronger.

**Thinking the primitive tube contains real points.** It does not contain real points. Real Jost points appear after the complex Lorentz extension.

**Forgetting that Wightman functions are distributions.** The holomorphic functions have distributional boundary values on real spacetime.

**Replacing locality by vanishing correlations.** Spacelike correlations need not vanish. Locality concerns commutators or graded commutators.

**Treating analytic continuation as Wick rotation only.** Wick rotation to Euclidean space is one use of analytic continuation. Jost-point analyticity is a more Lorentzian and several-variable structure.

**Assuming the scattering amplitude has every desired analytic property.** Correlator analyticity is foundational, but scattering analyticity needs extra hypotheses.

## Relations to other pages

This page is the analytic bridge between [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/), [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/), [CPT Theorem](/rigorous-qft/wightman-axiomatic-qft/cpt-theorem/), and [Spin–Statistics Theorem](/rigorous-qft/wightman-axiomatic-qft/spin-statistics-theorem/).

The distributional boundary-value viewpoint connects to [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/), which gives a modern language for singular directions. Later pages on Osterwalder–Schrader reconstruction will explain a different analytic route: Euclidean Schwinger functions plus reflection positivity reconstruct Lorentzian Wightman functions.

## Research status

The tube analyticity of Wightman functions and the role of Jost points in Wightman structural theorems are established results. They are part of the standard axiomatic QFT toolkit.

Active and delicate directions include:

| Direction | Status issue |
|---|---|
| Gauge theories | Physical gauge-invariant fields may fit Wightman ideas, while gauge-fixed variables often live in auxiliary indefinite spaces. |
| Massless particles | Infrared behavior complicates scattering limits and particle interpretations. |
| Scattering analyticity | Requires extra assumptions beyond the basic correlator analytic domains. |
| Curved spacetime | No global translation spectrum or global Lorentz group is available in general. |
| Constructive models | One must prove the Wightman properties for the constructed correlation functions. |
| Microlocal reformulations | Wavefront-set methods provide local control of singularities, especially in curved spacetime and perturbative algebraic QFT. |

The most important lesson is that analyticity is not decoration. In rigorous relativistic QFT, analyticity is the mathematical form of positive energy plus locality.

## Exercises

### Exercise 1: Two-point Jost points

Show that for $n=2$ the Jost-point condition is exactly spacelike separation.

<details><summary><strong>Solution</strong></summary>

There is one relative variable,

$$
\xi_1=x_1-x_2.
$$

The Jost condition says that for all $\lambda_1>0$,

$$
(\lambda_1\xi_1)^2<0.
$$

Since

$$
(\lambda_1\xi_1)^2=\lambda_1^2\xi_1^2,
$$

and $\lambda_1^2>0$, this is equivalent to

$$
\xi_1^2<0.
$$

That is precisely spacelike separation.

</details>

### Exercise 2: Pairwise spacelike is insufficient

In $1+1$ dimensions with mostly-minus metric, verify that

$$
\xi_1=(0,1),
\qquad
\xi_2=(2,-4)
$$

have pairwise spacelike adjacent and total separations, but the pair is not a Jost tuple.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\xi_1^2=-1,
\qquad
\xi_2^2=2^2-(-4)^2=-12,
\qquad
(\xi_1+\xi_2)^2=2^2-(-3)^2=-5.
$$

Equivalently, $(\xi_1+\xi_2)=(2,-3)$, so its square is $4-9=-5$. Thus the adjacent separations and the total separation are spacelike.

However, with $\lambda_1=1$ and $\lambda_2=1/4$,

$$
\xi_1+
\frac14\xi_2
=
\left(\frac12,0\right),
$$

and hence

$$
\left(\xi_1+\frac14\xi_2\right)^2
=
\frac14>0.
$$

A positive linear combination is timelike, so the tuple is not a Jost point.

</details>

### Exercise 3: Why the sign of the imaginary shift matters

Let

$$
W_2(x)=\int_{\overline V_+}e^{-ip\cdot x}\,d\mu(p).
$$

Explain why $z=x-iy$ with $y\in V_+$ gives damping, while $z=x+iy$ gives growth.

<details><summary><strong>Solution</strong></summary>

For $z=x-iy$,

$$
e^{-ip\cdot z}
=e^{-ip\cdot x}e^{-p\cdot y}.
$$

Since $p\in\overline V_+$ and $y\in V_+$ imply $p\cdot y\ge0$, the factor $e^{-p\cdot y}$ is damping.

For $z=x+iy$,

$$
e^{-ip\cdot z}
=e^{-ip\cdot x}e^{+p\cdot y},
$$

which grows in the forward cone. The spectral condition therefore selects the forward tube with the sign $x-iy$ for this Fourier convention.

</details>

## References

### Standard first pass

- A. S. Wightman, "Quantum Field Theory in Terms of Vacuum Expectation Values," *Physical Review* **101** (1956), 860–866. DOI: [10.1103/PhysRev.101.860](https://doi.org/10.1103/PhysRev.101.860).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- R. Jost, *The General Theory of Quantized Fields*, American Mathematical Society, 1965.
- D. Hall and A. S. Wightman, "A Theorem on Invariant Analytic Functions with Applications to Relativistic Quantum Field Theory," *Kongelige Danske Videnskabernes Selskab Matematisk-Fysiske Meddelelser* **31**, no. 5 (1957), 1–41. Record: [Royal Danish Academy](https://publ.royalacademy.dk/books/74/417).
- R. Jost, "Eine Bemerkung zum CTP Theorem," *Helvetica Physica Acta* **30** (1957), 409–416. Record: [E-Periodica](https://www.e-periodica.ch/digbib/view?pid=hpa-001%3A1957%3A30%3A%3A413).

### Deeper references

- Y. Tomozawa, "Local Commutativity and the Analytic Continuation of the Wightman Function," *Journal of Mathematical Physics* **4** (1963), 1240–1252. DOI: [10.1063/1.1703896](https://doi.org/10.1063/1.1703896).
- J. Bros, H. Epstein, and V. Glaser, "Some Rigorous Analyticity Properties of the Four-Point Function in Momentum Space," *Il Nuovo Cimento* **31** (1964), 1265–1302. DOI: [10.1007/BF02733596](https://doi.org/10.1007/BF02733596).
- J. Bros, "On the Connection Between Analyticity and Lorentz Covariance of Wightman Functions," *Communications in Mathematical Physics* **6** (1967), 77–100. DOI: [10.1007/BF01654126](https://doi.org/10.1007/BF01654126).
- H. J. Borchers and J. Yngvason, "On the PCT-Theorem in the Theory of Local Observables," arXiv: [math-ph/0012020](https://arxiv.org/abs/math-ph/0012020).
- N. N. Bogoliubov, A. A. Logunov, A. I. Oksak, and I. T. Todorov, *General Principles of Quantum Field Theory*, Kluwer. DOI: [10.1007/978-94-009-0491-0](https://doi.org/10.1007/978-94-009-0491-0).

## Version history

- **2026-06-28:** Initial polished draft.
