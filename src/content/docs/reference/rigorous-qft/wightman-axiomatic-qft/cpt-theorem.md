---
title: "CPT Theorem"
description: "States the CPT theorem in the Wightman framework, explains its assumptions, and relates antiunitary spacetime reflection to analyticity and locality."
sidebar:
  label: "CPT Theorem"
  order: 10
level: Graduate
status: "Polished draft"
source: "Wightman; Jost; Streater–Wightman; Lüders–Zumino; Greenberg."
topics:
  - CPT theorem
  - PCT theorem
  - Wightman axioms
  - antiunitary symmetries
  - analyticity
canonicalTopics:
  - cpt-theorem
  - pct-theorem
  - axiomatic-quantum-field-theory
  - rigorous-quantum-field-theory
researchStatus:
  established:
    - "In ordinary local relativistic Wightman QFT on Minkowski spacetime, CPT invariance is a structural theorem rather than an optional model assumption."
  active:
    - "Gauge constraints, curved spacetime, nonlocal theories, Lorentz-violating effective theories, and nonstandard positivity assumptions require separate formulations of what a CPT statement should mean."
---

## Summary

The CPT theorem says that a local relativistic quantum field theory satisfying the Wightman hypotheses has an antiunitary symmetry combining charge conjugation, parity, and time reversal. In the axiomatic literature this is often called the **PCT theorem**. The letters are not important; the structural operation is spacetime inversion together with adjoint or charge conjugation:

$$
x\longmapsto -x,
\qquad
\phi(x)\longmapsto \phi^\dagger(-x)
$$

with representation matrices and signs inserted for spinor, tensor, charged, and graded fields.

For a neutral scalar field, the theorem can be summarized by the existence of an antiunitary operator $\Theta$ such that

$$
\Theta\Omega=\Omega,
\qquad
\Theta U(a,\Lambda)\Theta^{-1}=U(-a,\Lambda),
\qquad
\Theta\phi(f)\Theta^{-1}=\phi(f^\Theta),
$$

where

$$
f^\Theta(x)=\overline{f(-x)}.
$$

Equivalently, the vacuum correlation functions obey a reflected-and-reversed identity, schematically

$$
W_n(x_1,\ldots,x_n)
=
W_n(-x_n,\ldots,-x_1),
$$

again with the appropriate matrices, adjoints, and grading signs for general fields.

The theorem is not a statement that $C$, $P$, or $T$ must be separately conserved. Local relativistic QFT may violate $C$, $P$, $T$, $CP$, or $CT$ separately. The theorem says that, under the standard Wightman assumptions, the combined CPT operation is forced.

<figure class="doc-figure" style="--figure-width: 48rem;">

![The analytic logic of the CPT theorem in Wightman QFT](/figures/rigorous-qft/cpt-analyticity-logic.svg)

<figcaption>

The Wightman proof of CPT is an analyticity theorem. Positive energy gives tube analyticity, covariance enlarges the tube by complex Lorentz transformations, locality gives equality at Jost configurations, and reconstruction turns the resulting correlation-function identity into an antiunitary Hilbert-space symmetry $\Theta$.

</figcaption>
</figure>

## Prerequisites

You should know the [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/), especially [Poincaré Covariance](/rigorous-qft/wightman-axiomatic-qft/poincare-covariance/), [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/), [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/), [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/), and [Wightman Reconstruction Theorem](/rigorous-qft/wightman-axiomatic-qft/reconstruction-theorem/).

The [Spin–Statistics Theorem](/rigorous-qft/wightman-axiomatic-qft/spin-statistics-theorem/) is logically nearby but not identical: both use locality, positive energy, covariance, and analytic continuation, but they prove different structural constraints.

## Logical status

| Item | Status |
|---|---|
| Type | Theorem. |
| Framework | Wightman axiomatic QFT on Minkowski spacetime. |
| Input | Positive Hilbert space, invariant vacuum, finite-component covariant fields, spectral condition, locality or graded locality, and the standard adjoint structure. |
| Output | An antiunitary CPT operator on the vacuum-generated Hilbert space, implementing spacetime inversion and field adjunction or charge conjugation. |
| Correlation-function form | Reflected Wightman functions equal reversed Wightman functions, with spin matrices and grading signs. |
| Main proof engine | Tube analyticity, complex Lorentz covariance, Jost points, weak local commutativity, and reconstruction. |
| Main limitation | The theorem applies to the stated framework; it is not a blanket theorem for every object physicists call a QFT. |

## Core idea

The CPT theorem is surprising because none of its three individual letters is sacred. The weak interaction famously violates parity, and many QFTs distinguish particles from antiparticles under $C$ or $CP$. Nevertheless, the combination CPT survives in ordinary local relativistic QFT because it is tied to deeper structure than any one discrete transformation.

The deep ingredients are these:

1. **Positive energy** makes Wightman functions analytic in complexified spacetime tubes.
2. **Lorentz covariance** extends this analyticity through the complex Lorentz group.
3. **Locality** permits the order of spacelike separated fields to be interchanged.
4. **Hilbert-space positivity** turns correlation-function identities into operator identities.

The point $x\mapsto -x$ is not in the proper orthochronous real Lorentz group, but it is accessible through the complexified Lorentz group. This is the geometric reason a theorem about a discrete spacetime inversion can be proved from hypotheses involving only proper orthochronous covariance plus locality.

For scalar fields, the heart of the theorem is the identity

$$
\langle\Omega,\phi(x_1)\cdots\phi(x_n)\Omega\rangle
=
\langle\Omega,\phi(-x_n)\cdots\phi(-x_1)\Omega\rangle.
$$

For general fields this must be dressed by finite-dimensional Lorentz representation matrices, charge conjugation or adjunction, and the signs required by fermionic reordering. The scalar formula is a useful mental model, not the complete tensor-spinor statement.

## Setup and conventions

We work on $d=4$ Minkowski spacetime with the mostly-minus metric and Fourier convention fixed in [Conventions and Logical Status](/rigorous-qft/conventions/). The usual CPT theorem can be formulated in general spacetime dimension with suitable modifications, but the four-dimensional theorem is the standard case relevant to ordinary relativistic QFT.

A Wightman field multiplet is a collection of operator-valued distributions

$$
\phi_a(f):\mathcal D\to\mathcal D,
\qquad
f\in\mathcal S(\mathbb M^4),
$$

transforming under a finite-dimensional representation $S(\Lambda)$ of the proper Lorentz group or its spin cover. Covariance means, schematically,

$$
U(a,\Lambda)\phi_a(x)U(a,\Lambda)^{-1}
=
S_a{}^b(\Lambda^{-1})\phi_b(\Lambda x+a).
$$

The precise placement of indices depends on whether the field is scalar, spinor, vector, tensor, or a multiplet with internal labels. The CPT theorem is usually stated for a set of fields closed under adjoint, so that $\phi_a^\dagger$ is again a linear combination of fields in the theory.

We write the vacuum correlation distributions as

$$
W_{a_1\cdots a_n}(x_1,\ldots,x_n)
=
\langle\Omega,
\phi_{a_1}(x_1)\cdots\phi_{a_n}(x_n)
\Omega\rangle.
$$

This is kernel notation. The actual objects are tempered distributions smeared against Schwartz functions.

## Statement of the theorem

A standard Wightman-style statement is the following.

:::note[CPT theorem]
Let a finite set of Wightman fields on a positive Hilbert space satisfy the Wightman axioms: temperedness, a common invariant domain, proper orthochronous Poincaré covariance, the spectral condition, a Poincaré-invariant vacuum, cyclicity of the vacuum-generated field domain, and local graded commutativity at spacelike separation.

Assume also that the field system is closed under adjoints. Then there exists an antiunitary operator $\Theta$ on the vacuum-generated Hilbert space such that

$$
\Theta\Omega=\Omega,
\qquad
\Theta U(a,\Lambda)\Theta^{-1}=U(-a,\Lambda),
$$

and

$$
\Theta\phi_a(x)\Theta^{-1}
=
\sum_b \mathsf C_a{}^b\,\phi_b^\dagger(-x)
$$

as an identity of operator-valued distributions, with a fixed finite-dimensional matrix $\mathsf C$ determined by the Lorentz and internal representation conventions.

Equivalently, all vacuum Wightman functions satisfy the corresponding reflected, reversed, adjointed, and graded identity.
:::

The scalar neutral case hides most of the bookkeeping. For charged scalar fields, CPT exchanges the field with its adjoint. For spinor fields, it also converts spinor representation indices in the appropriate way. For several fermionic fields, reversing order produces the usual grading signs.

The theorem is often stated after the spin–statistics theorem, because then the allowed grading of each field is already fixed by its Lorentz representation. However, the analytic CPT statement can also be formulated using whatever graded locality structure is part of the field system.

## What CPT does to Wightman functions

For one neutral scalar Hermitian field, CPT covariance gives the clean identity

$$
W_n(x_1,\ldots,x_n)
=
W_n(-x_n,\ldots,-x_1).
$$

The order is reversed because an antiunitary adjoint-type operation reverses products. For a product of operators, the adjoint reverses order:

$$
(AB)^\dagger=B^\dagger A^\dagger.
$$

The field-theoretic CPT operator is not merely the Hilbert-space adjoint, but the same reversal is visible in the correlation-function identity.

For a multiplet, one should think instead of

$$
\begin{aligned}
&W_{a_1\cdots a_n}(x_1,\ldots,x_n) \\
&\quad =
\sum_{b_1,\ldots,b_n}
\mathsf C_{a_1}{}^{b_1}\cdots \mathsf C_{a_n}{}^{b_n}
\,\varepsilon(a_1,\ldots,a_n)\,
W_{b_n\cdots b_1}(-x_n,\ldots,-x_1),
\end{aligned}
$$

where $\varepsilon(a_1,\ldots,a_n)$ is the sign obtained from reversing odd fields. The exact matrix convention is not universal; the invariant content is the existence of an antiunitary operator implementing the reflected adjoint field system.

## Why analyticity enters

At first glance, CPT looks like a discrete symmetry theorem. Its proof is actually a theorem about analytic continuation.

Translation invariance lets one write Wightman functions in relative variables

$$
\xi_j=x_j-x_{j+1},
\qquad j=1,\ldots,n-1.
$$

The spectral condition says that the Fourier transform in these relative variables is supported in future cones:

$$
\operatorname{supp}\widetilde w_n
\subset
(\overline V_+)^{n-1}.
$$

With the Fourier convention $e^{-ip\cdot x}$, this support gives analyticity in the forward tube with negative imaginary parts,

$$
z_j=\xi_j-i\eta_j,
\qquad
\eta_j\in V_+.
$$

The tube is not yet enough to reach spacetime inversion. The next step is to use covariance under the complexified Lorentz group. Roughly,

$$
(z_1,\ldots,z_{n-1})
\longmapsto
(\Lambda z_1,\ldots,\Lambda z_{n-1}),
\qquad
\Lambda\in L_+(\mathbb C).
$$

The Bargmann–Hall–Wightman theorem gives the analytic continuation to the **extended tube**. This enlarged domain contains real configurations called Jost points. At those points, locality can be used as an equality of ordinary boundary values. Analytic uniqueness then transports the equality throughout the relevant domain.

This is the conceptual bridge:

$$
\text{spectral positivity}
\quad\Rightarrow\quad
\text{analyticity}
\quad\Rightarrow\quad
\text{complex spacetime reflection}
\quad\Rightarrow\quad
\text{CPT identity}.
$$

## Jost theorem and weak local commutativity

The sharp analytic statement behind CPT is often attributed to Jost. It says, roughly, that CPT invariance is equivalent to **weak local commutativity at Jost points**.

Weak local commutativity is not an operator statement. It is a statement about vacuum expectation values. For a scalar field it says that, at suitable spacelike real configurations,

$$
W_n(x_1,\ldots,x_n)
=
W_n(x_n,\ldots,x_1),
$$

with graded signs and field labels in the general case.

Full Wightman locality implies this weak equality. The converse is more subtle: weak local commutativity at Jost points is already enough, together with the other analytic and covariance hypotheses, to obtain CPT. This is why the later [Jost Points and Analyticity Preview](/rigorous-qft/wightman-axiomatic-qft/jost-points-and-analyticity-preview/) page is not a technical ornament. It is the geometric center of the theorem.

## Consequences and interpretation

The most familiar physical consequences are particle–antiparticle equality statements. In theories with a standard particle interpretation, CPT implies equality of masses and total lifetimes for particles and antiparticles, and relates scattering amplitudes of a process to the CPT-reflected process.

But the theorem itself is more primitive than scattering theory. It is a statement about local fields and their vacuum correlation functions. It does not require a mass gap, asymptotic completeness, or an $S$-matrix. This distinction matters in rigorous QFT, because scattering theory has additional hypotheses.

It is also important that CPT is not a new axiom in the Wightman framework. It is a theorem. If a proposed relativistic local positive-Hilbert-space field theory violates CPT, then at least one standard hypothesis must fail. The usual suspects are Lorentz covariance, locality, positivity, or the field-theoretic assumptions needed to define the Wightman system.

## What can fail if hypotheses are weakened?

| Modified setting | What changes |
|---|---|
| Lorentz-violating effective theories | The complex Lorentz argument no longer applies in its standard form. |
| Nonlocal fields | Locality cannot be used to reverse field order at Jost configurations. |
| Indefinite-metric gauge fixing | The auxiliary state space is not the physical positive Hilbert space assumed by the theorem. |
| BRST formalisms | One must formulate CPT on the BRST cohomology or gauge-invariant observable algebra. |
| Curved spacetime | Global Poincaré symmetry and global spacetime inversion may not exist. |
| Thermal states | The vacuum and spectrum assumptions are replaced by KMS-type structure. |
| Anyonic systems in two spatial dimensions | The topology of exchange and localization differs from ordinary four-dimensional point-field QFT. |
| Non-Hermitian or nonunitary theories | Antiunitary symmetry and positive Hilbert-space reconstruction require separate assumptions. |

The right conclusion is not that CPT is fragile. The right conclusion is that CPT is a precise theorem with precise hypotheses. When a framework changes, the theorem must be reformulated rather than quoted as a slogan.

## Relation to physics notation

In informal physics notation one often writes

$$
\mathrm{CPT}:\quad
\phi(t,\mathbf x)
\mapsto
\phi^\dagger(-t,-\mathbf x).
$$

This is a useful shorthand, but it suppresses several pieces of data:

- the operation is antiunitary, not just a substitution of coordinates;
- fermionic products acquire signs under reversal;
- spinor and tensor fields require representation matrices;
- charged fields are mapped to conjugate fields;
- gauge-fixed fields may be auxiliary rather than physical;
- the theorem is about smeared operator-valued distributions, not literal point operators.

For example, for a neutral scalar field the schematic rule is enough. For a Dirac field, the rule involves charge conjugation and spinor matrices. For gauge theory, the cleanest theorem-level statement may be on physical fields or local observables rather than on every gauge-fixed variable.

## Common pitfalls

**Treating CPT as an empirical accident.** The theorem explains why CPT is expected in ordinary local relativistic QFT. Experiments can test CPT, but the theoretical reason for expecting it is structural.

**Assuming separate C, P, or T invariance.** The theorem does not say that $C$, $P$, or $T$ is individually conserved.

**Ignoring antiunitarity.** Because time reversal is antiunitary, CPT is antiunitary. Complex conjugation of coefficients is part of the operation.

**Forgetting the reversal of order.** The reflected correlation function has fields in the reverse order, with grading signs when odd fields are present.

**Calling ghosts a counterexample.** Faddeev–Popov ghosts are auxiliary fields in gauge-fixed quantization. They are not physical Wightman fields on a positive Hilbert space.

**Quoting CPT in curved spacetime without checking geometry.** On a general curved spacetime there may be no global map $x\mapsto -x$, no Poincaré group, and no vacuum spectral condition.

**Using the theorem to avoid construction.** CPT is a theorem about theories satisfying the hypotheses. It does not prove that a given interacting model exists as a Wightman QFT.

## Relations to other pages

[Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/) defines the correlation distributions whose reflected identities express CPT. [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/) explains why positive energy implies tube analyticity. [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/) provides the field-ordering hypothesis used at spacelike configurations.

[Wightman Reconstruction Theorem](/rigorous-qft/wightman-axiomatic-qft/reconstruction-theorem/) explains why correlation-function identities become Hilbert-space operator identities. [Spin–Statistics Theorem](/rigorous-qft/wightman-axiomatic-qft/spin-statistics-theorem/) is the neighboring structural theorem. [Jost Points and Analyticity Preview](/rigorous-qft/wightman-axiomatic-qft/jost-points-and-analyticity-preview/) explains the analytic geometry behind both results.

## Research status

**Established theorem.** The CPT theorem is a standard theorem of axiomatic QFT in the Wightman framework. It is one of the classic successes of the field: a physically important prediction follows from a short list of structural assumptions.

**Modern refinements.** Algebraic QFT formulates related results in terms of local observable algebras and modular theory. Perturbative algebraic QFT and BV-BRST formalisms require care about gauge symmetry, ghosts, and physical observables.

**Frontier and phenomenology.** Searches for CPT violation are often simultaneously probes of Lorentz invariance, locality, quantum mechanics, or the assumptions underlying effective field theory. A reported violation would not merely toggle a discrete symmetry; it would identify a failure of some structural hypothesis.

## Exercises

### Exercise 1: Scalar CPT identity

Assume a neutral Hermitian scalar field satisfies

$$
\Theta\Omega=\Omega,
\qquad
\Theta\phi(x)\Theta^{-1}=\phi(-x),
$$

where $\Theta$ is antiunitary. Explain why the corresponding Wightman identity must reverse the order of fields.

<details><summary><strong>Solution</strong></summary>

The reversal is the same structural reversal that appears when taking adjoints of products:

$$
(\phi(x_1)\cdots\phi(x_n))^\dagger
=
\phi(x_n)\cdots\phi(x_1)
$$

for a Hermitian scalar field. An antiunitary symmetry relates matrix elements to matrix elements of transformed vectors and conjugates coefficients. Applying the transformed field rule to a vacuum expectation value therefore produces the product of reflected fields in the reverse order.

Thus the scalar CPT identity is schematically

$$
W_n(x_1,\ldots,x_n)
=
W_n(-x_n,\ldots,-x_1).
$$

For non-scalar or charged fields, this identity is modified by matrices, adjoints, and grading signs.

</details>

### Exercise 2: CPT and separate parity

Does the CPT theorem imply that a parity-violating theory is impossible? Explain.

<details><summary><strong>Solution</strong></summary>

No. The theorem concerns the combined antiunitary CPT operation, not the separate transformations $C$, $P$, and $T$. A theory may violate parity while still preserving CPT. Indeed, the weak interaction violates parity, but ordinary local relativistic QFT still predicts CPT invariance under the standard assumptions.

The logical implication is

$$
\text{Wightman hypotheses}
\Longrightarrow
\text{CPT invariance},
$$

not

$$
\text{Wightman hypotheses}
\Longrightarrow
C\text{, }P\text{, and }T\text{ separately}.
$$

</details>

### Exercise 3: Finding the failed hypothesis

A Lorentz scalar ghost field anticommutes at spacelike separation. Which assumption of the physical spin–statistics and CPT theorem framework should you inspect first?

<details><summary><strong>Solution</strong></summary>

Inspect Hilbert-space positivity and physicality. Gauge ghosts are auxiliary fields introduced in gauge fixing, usually inside an indefinite-metric or BRST complex. They are not physical scalar Wightman fields acting on a positive Hilbert space of observable states.

The physical theorem should be applied to the physical Hilbert space, BRST cohomology, or gauge-invariant observable algebra, depending on the formalism. A ghost field with unusual statistics is not by itself a counterexample to the theorem.

</details>

## References

### Standard first pass

- A. S. Wightman, "Quantum Field Theory in Terms of Vacuum Expectation Values," *Physical Review* **101** (1956), 860–866. DOI: [10.1103/PhysRev.101.860](https://doi.org/10.1103/PhysRev.101.860).
- G. Lüders, "Proof of the TCP Theorem," *Annals of Physics* **2** (1957), 1–15. DOI: [10.1016/0003-4916(57)90032-5](https://doi.org/10.1016/0003-4916(57)90032-5).
- W. Pauli, "Exclusion Principle, Lorentz Group and Reflection of Space-Time and Charge," in *Niels Bohr and the Development of Physics*, Pergamon Press, 1955.
- G. Lüders and B. Zumino, "Some Consequences of TCP-Invariance," *Physical Review* **106** (1957), 385–386. DOI: [10.1103/PhysRev.106.385](https://doi.org/10.1103/PhysRev.106.385).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- R. Jost, *The General Theory of Quantized Fields*, American Mathematical Society, 1965.

### Deeper references

- D. Hall and A. S. Wightman, "A Theorem on Invariant Analytic Functions with Applications to Relativistic Quantum Field Theory," *Matematisk-Fysiske Meddelelser* **31**, no. 5 (1957). Available from the Royal Danish Academy archive: [PDF](https://gymarkiv.sdu.dk/MFM/kdvs/mfm%2030-39/mfm-31-5.pdf).
- O. W. Greenberg, "CPT Violation Implies Violation of Lorentz Invariance," *Physical Review Letters* **89** (2002), 231602. DOI: [10.1103/PhysRevLett.89.231602](https://doi.org/10.1103/PhysRevLett.89.231602), arXiv: [hep-ph/0201258](https://arxiv.org/abs/hep-ph/0201258).
- R. Lehnert, "CPT Symmetry and Its Violation," *Symmetry* **8** (2016), 114. DOI: [10.3390/sym8110114](https://doi.org/10.3390/sym8110114), arXiv: [1611.01775](https://arxiv.org/abs/1611.01775).
- G. W. Mackey, *The Mathematical Foundations of Quantum Mechanics*, W. A. Benjamin, 1963. Useful background on antiunitary symmetries and Wigner's theorem.

## Version history

- **2026-06-28:** Initial polished draft.
