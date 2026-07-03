---
title: "Selection Rules"
description: "Derives selection rules from global symmetry: charge neutrality, singlet conditions, matrix-element constraints, and the ways these rules change with breaking, anomalies, boundaries, and backgrounds."
sidebar:
  label: "Selection Rules"
  order: 8
level: Graduate
status: "Polished draft"
source: "Coleman lectures on currents and symmetry; Weinberg Vol. I on symmetry representations; Srednicki §§22–24; standard Ward-identity arguments."
topics:
  - selection rules
  - charge conservation
  - invariant tensors
  - Ward identities
  - matrix elements
  - symmetry defects
canonicalTopics:
  - selection-rule
  - charge-neutrality
  - invariant-correlator
  - ward-identity
researchStatus:
  established:
    - "Selection rules from exact global symmetries are direct consequences of the symmetry action on states, operators, and the vacuum."
  active:
    - "In modern QFT, selection rules are refined by anomalies, boundaries, generalized symmetries, non-invertible defects, and global-form choices."
---

## Summary

A **selection rule** says that a quantity must vanish unless its quantum numbers are compatible with the symmetries of the theory.

For an exact $U(1)$ symmetry and an invariant vacuum,

$$
\langle \mathcal O_{q_1}(x_1)\cdots \mathcal O_{q_n}(x_n)\rangle\ne0
\quad\Longrightarrow\quad
\sum_{i=1}^n q_i=0.
$$

For a finite symmetry such as $\mathbb Z_N$,

$$
\sum_i q_i=0\quad \mathrm{mod}\,N.
$$

For a compact nonabelian symmetry group $G$, the corresponding statement is not “the charges add to zero” but

$$
\mathbf 1\subset R_1\otimes R_2\otimes\cdots\otimes R_n,
$$

where $R_i$ is the representation carried by $\mathcal O_i$. The correlator is an invariant tensor. If the tensor product contains no singlet, the correlator vanishes.

For a matrix element,

$$
\langle f|\mathcal O_{q_1}\cdots\mathcal O_{q_n}|i\rangle\ne0
\quad\Longrightarrow\quad
Q_f=Q_i+\sum_i q_i,
$$

with the sign convention used in this volume. Selection rules are therefore not extra assumptions. They are the zero-mode part of Ward identities, or equivalently the statement that a topological symmetry defect can be slid away from a correlator.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A symmetry wall surrounding local insertions gives an abelian charge-neutrality rule, while a nonabelian correlator is nonzero only when the tensor product contains an invariant singlet.](/figures/symmetry-anomalies-topology/selection-rule-singlet-test.svg)

<figcaption>

Selection rules are symmetry-invariance tests. For an abelian symmetry the test is charge neutrality, $\sum_i q_i=0$. For a nonabelian symmetry the test is the existence of an invariant tensor, equivalently a singlet in $R_1\otimes\cdots\otimes R_n$.

</figcaption>
</figure>

## Prerequisites

You should know [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/), [Symmetry Defects and Topological Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-defects-and-topological-operators/), and [Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/).

The only group theory needed here is the idea that states and operators transform in representations, and that a physical scalar correlator in an invariant vacuum must be a singlet.

## Core idea

A symmetry gives two kinds of information.

First, it tells us how states and operators transform. Second, it tells us that the vacuum, action, Hamiltonian, path-integral measure, and boundary conditions are invariant, unless the symmetry is broken or anomalous.

Putting these together gives selection rules. If a correlator transforms nontrivially under a symmetry but the same correlator is supposed to be invariant, the only consistent value is zero.

The smallest example is a $U(1)$ symmetry. If

$$
U(\alpha)^\dagger\mathcal O_qU(\alpha)=e^{i\alpha q}\mathcal O_q,
$$

then the product $\mathcal O_{q_1}\cdots\mathcal O_{q_n}$ has charge $\sum_iq_i$. If the vacuum is invariant, the correlator must equal itself times $e^{i\alpha\sum_iq_i}$ for every $\alpha$. Unless the phase is always one, the correlator vanishes.

That is the whole idea. The rest of the page is about making the statement precise in the cases that actually appear in QFT.

## Setup and conventions

For a continuous internal symmetry, we use

$$
U(\alpha)=e^{-i\alpha^aQ_a},
$$

with Hermitian charges $Q_a$. Operators transform by pullback,

$$
U(\alpha)^\dagger\mathcal O_iU(\alpha)
=\mathcal O_i+i\alpha^a[Q_a,\mathcal O_i]+O(\alpha^2).
$$

For a $U(1)$ charge eigenoperator,

$$
[Q,\mathcal O_q]=q\mathcal O_q,
$$

so

$$
U(\alpha)^\dagger\mathcal O_qU(\alpha)=e^{i\alpha q}\mathcal O_q.
$$

A charge eigenstate obeys

$$
Q|Q_i,r\rangle=Q_i|Q_i,r\rangle,
\qquad
U(\alpha)|Q_i,r\rangle=e^{-i\alpha Q_i}|Q_i,r\rangle.
$$

:::note[Convention-sensitive source note]
With the convention above, a charge-$q$ operator raises the charge of a state: $\mathcal O_q:\mathcal H_Q\to\mathcal H_{Q+q}$. If a source uses $U(\alpha)=e^{+i\alpha Q}$ or transforms operators as $U\mathcal O U^{-1}$, the displayed phases move around. The invariant statement is the same: a nonzero matrix element must balance the charges of the states and insertions.
:::

## Abelian charge neutrality

Let the vacuum be invariant:

$$
U(\alpha)|\Omega\rangle=|\Omega\rangle.
$$

Consider a product of charge eigenoperators,

$$
\mathcal X=\mathcal O_{q_1}(x_1)\cdots\mathcal O_{q_n}(x_n).
$$

Using symmetry invariance,

$$
\langle\Omega|\mathcal X|\Omega\rangle
=
\langle\Omega|U(\alpha)^\dagger\mathcal XU(\alpha)|\Omega\rangle.
$$

Since each factor contributes its charge phase,

$$
U(\alpha)^\dagger\mathcal XU(\alpha)
=e^{i\alpha(q_1+\cdots+q_n)}\mathcal X.
$$

Therefore

$$
\langle\mathcal X\rangle
=e^{i\alpha\sum_iq_i}\langle\mathcal X\rangle.
$$

If this holds for all $\alpha$, then

$$
\langle\mathcal X\rangle\ne0
\quad\Longrightarrow\quad
\sum_iq_i=0.
$$

This is the charge-neutrality selection rule.

For example, if $\phi$ has charge $+1$ and $\phi^\dagger$ has charge $-1$, then

$$
\langle \phi(x)\phi(y)\rangle=0,
\qquad
\langle \phi(x)\phi^\dagger(y)\rangle
$$

is allowed by the $U(1)$ symmetry. “Allowed” does not mean “nonzero”; it only means the symmetry does not force it to vanish.

## Matrix-element charge balance

Selection rules also constrain matrix elements between charged states. Let

$$
\mathcal X=\mathcal O_{q_1}\cdots\mathcal O_{q_n}
$$

have total charge

$$
q_\mathcal X=\sum_iq_i.
$$

Let

$$
Q|i\rangle=Q_i|i\rangle,
\qquad
Q|f\rangle=Q_f|f\rangle.
$$

Insert $1=UU^\dagger$ around $\mathcal X$:

$$
\langle f|\mathcal X|i\rangle
=
\langle f|U(\alpha)\,U(\alpha)^\dagger\mathcal XU(\alpha)\,U(\alpha)^\dagger|i\rangle.
$$

Using the phases of $|i\rangle$, $|f\rangle$, and $\mathcal X$ gives

$$
\langle f|\mathcal X|i\rangle
=
e^{i\alpha(q_\mathcal X+Q_i-Q_f)}\langle f|\mathcal X|i\rangle.
$$

Thus

$$
\langle f|\mathcal X|i\rangle\ne0
\quad\Longrightarrow\quad
Q_f=Q_i+q_\mathcal X.
$$

This is the Hilbert-space version of charge conservation. It says that the operator insertions carry exactly the charge difference between the final and initial states.

## Finite and discrete symmetries

A finite symmetry has no infinitesimal charge operator in the Noether sense, but it still has selection rules.

For a $\mathbb Z_N$ symmetry, let $r$ be the generator and let an operator have charge $k\in\mathbb Z_N$:

$$
U_r^\dagger\mathcal O_kU_r=e^{2\pi i k/N}\mathcal O_k.
$$

For an invariant vacuum,

$$
\langle\mathcal O_{k_1}\cdots\mathcal O_{k_n}\rangle\ne0
\quad\Longrightarrow\quad
k_1+\cdots+k_n=0\quad\mathrm{mod}\,N.
$$

For a matrix element,

$$
Q_f=Q_i+\sum_i k_i\quad\mathrm{mod}\,N.
$$

The same logic works for any finite abelian group by replacing charges with characters. For a general finite nonabelian group, the rule is the same as for compact nonabelian Lie groups: the relevant tensor product must contain the trivial representation.

A useful example is a $\mathbb Z_2$ spin-flip symmetry. If $\sigma$ is odd and $\varepsilon$ is even, then in a spin-flip invariant vacuum,

$$
\langle \sigma(x)\rangle=0,
\qquad
\langle \sigma(x)\varepsilon(y)\rangle=0,
\qquad
\langle \sigma(x)\sigma(y)\rangle
$$

is allowed.

## Nonabelian singlet rules

For a compact nonabelian group $G$, the clean statement is representation-theoretic.

Let local operators transform in representations $R_i$. A vacuum correlator can be nonzero only if the product of representations admits a $G$-invariant tensor:

$$
\operatorname{Hom}_G(\mathbf 1,R_1\otimes\cdots\otimes R_n)\ne0.
$$

Equivalently,

$$
\mathbf 1\subset R_1\otimes\cdots\otimes R_n.
$$

For $SU(2)$, this says that the spins in a correlator must be able to couple to total spin zero. For two operators,

$$
j_1\otimes j_2
$$

contains spin zero only if $j_1=j_2$. For three operators, the familiar triangle inequalities and integrality condition must hold:

$$
|j_1-j_2|\le j_3\le j_1+j_2,
\qquad
j_1+j_2+j_3\in\mathbb Z.
$$

For $SU(N)$, an invariant tensor can be built from Kronecker deltas, epsilon tensors, and their representation-theoretic descendants. For example, a fundamental and an antifundamental can form a singlet:

$$
\mathbf N\otimes\overline{\mathbf N}\supset\mathbf 1,
$$

while a single fundamental cannot have a nonzero one-point function in an invariant vacuum.

For matrix elements, if the initial state transforms in $R_i$, the final state in $R_f$, and the operator product in $R_\mathcal X$, then

$$
\langle f|\mathcal X|i\rangle\ne0
$$

requires an invariant map

$$
R_i\otimes R_\mathcal X\to R_f,
$$

or equivalently

$$
R_f\subset R_\mathcal X\otimes R_i.
$$

This is the QFT version of the Wigner–Eckart selection rule from quantum mechanics.

## Ward-identity derivation

Selection rules are the integrated, zero-momentum part of Ward identities.

For an infinitesimal continuous symmetry,

$$
\delta_a\mathcal O_i=i[Q_a,\mathcal O_i].
$$

If the vacuum and measure are invariant, then

$$
0=\delta_a\langle\mathcal O_1\cdots\mathcal O_n\rangle.
$$

Therefore

$$
0=
\sum_{k=1}^n
\langle\mathcal O_1\cdots(\delta_a\mathcal O_k)\cdots\mathcal O_n\rangle.
$$

If the operators are $U(1)$ charge eigenoperators, this becomes

$$
0=i\left(\sum_kq_k\right)
\langle\mathcal O_{q_1}\cdots\mathcal O_{q_n}\rangle,
$$

which is the charge-neutrality rule.

The local Ward identity refines this statement. For a conserved current $j^\mu$,

$$
\partial_\mu\langle j^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=
-i\sum_k\delta^{(d)}(x-x_k)
\langle\mathcal O_1\cdots(\delta\mathcal O_k)\cdots\mathcal O_n\rangle,
$$

up to convention-dependent signs. Integrating over a region whose boundary encloses all insertions gives the selection rule.

:::note[Convention-sensitive source note]
The sign in the local Ward identity depends on whether one defines $\delta\mathcal O=i[Q,\mathcal O]$ or $\delta\mathcal O=-i[Q,\mathcal O]$, and on whether the current insertion is written in Lorentzian or Euclidean signature. The selection rule itself is insensitive to these choices.
:::

## Defect derivation

The topological-defect derivation is often the most robust one.

Insert a closed symmetry defect $U_g(\Sigma)$ around a collection of local operators. Because the defect is topological, it can be slid outward. If there is no obstruction at infinity and the vacuum is invariant, the defect disappears. But sliding the defect across the operators acts on them.

For a $U(1)$ symmetry, this gives

$$
\langle\mathcal O_{q_1}\cdots\mathcal O_{q_n}\rangle
=
e^{i\alpha\sum_iq_i}
\langle\mathcal O_{q_1}\cdots\mathcal O_{q_n}\rangle.
$$

For nonabelian $G$, it says that the correlator is an invariant tensor. For higher-form symmetries, the same idea applies with topological operators linking extended operators rather than enclosing local operators. This is why selection rules survive well beyond ordinary Noether-current language.

## Spacetime selection rules

Internal symmetries are not the only source of selection rules.

Translation invariance gives momentum conservation. In a translationally invariant vacuum,

$$
\langle\mathcal O_1(p_1)\cdots\mathcal O_n(p_n)\rangle
\propto
(2\pi)^d\delta^{(d)}(p_1+\cdots+p_n).
$$

Time-translation invariance gives energy conservation in transition amplitudes. Rotational invariance gives angular-momentum selection rules. Lorentz invariance restricts tensor structures in correlation functions and scattering amplitudes. Parity, time reversal, and charge conjugation impose additional rules when they are exact.

The logic is the same: if a quantity transforms in a nontrivial representation while the state and background are invariant, that quantity must vanish or have a constrained tensor structure.

Spacetime symmetry has extra caveats. It can be broken by boundaries, finite temperature, finite density, curved backgrounds, defects, or a chosen scattering setup. For example, a thermal state preserves spatial translations and rotations but not Lorentz boosts.

## Selection rules in perturbation theory

In perturbation theory, selection rules show up as diagrammatic absences.

If every interaction vertex preserves a $U(1)$ charge, then no Feynman diagram can violate total charge. Charge flows through propagators and vertices like a conserved label. If a diagram appears to violate the symmetry, something has been mislabeled: either the field charge is wrong, a conjugate field was omitted, or the interaction term explicitly breaks the symmetry.

For a complex scalar with Lagrangian interactions built from $\phi^\dagger\phi$, every vertex has equal numbers of $\phi$ and $\phi^\dagger$. Therefore external legs must carry net zero $U(1)$ charge for a vacuum correlator to be nonzero.

For nonabelian symmetries, diagrammatic selection rules are encoded in invariant tensors at vertices. A vertex exists only if the tensor product of the attached representations contains a singlet. This is why group-theory factors are not decorative multipliers: they are the selection-rule machinery of perturbation theory.

## When selection rules change

Selection rules are powerful, but they are conditional. Always ask: *which symmetry, which state, which operators, which boundary conditions?*

### Explicit breaking

If the Hamiltonian or action is not invariant, the selection rule is not exact. For example, a small term

$$
\epsilon\,\phi+\epsilon^*\phi^\dagger
$$

breaks a $U(1)$ symmetry and allows correlators that were previously forbidden, typically with amplitudes proportional to powers of $\epsilon$.

### Spontaneous breaking

If the theory has a symmetry but the chosen vacuum does not, the full symmetry no longer gives vacuum selection rules. Only the unbroken subgroup does.

In a $\mathbb Z_2$-broken phase, one may have

$$
\langle\sigma\rangle\ne0
$$

in a chosen infinite-volume vacuum, even though $\sigma$ is odd under the microscopic $\mathbb Z_2$. The symmetry relates different vacua rather than annihilating the chosen vacuum.

In finite volume, tunneling may restore a symmetric ground state. This is one reason selection rules can look different before and after the infinite-volume limit.

### Anomalies

An anomaly can modify the Ward identity. A classically conserved current may satisfy a quantum equation of the form

$$
\partial_\mu j^\mu=\mathcal A,
$$

where $\mathcal A$ is a local anomaly density. Then the naive selection rule is replaced by an anomalous relation.

For an ordinary global symmetry, the anomaly may mean that the symmetry cannot be consistently gauged, rather than that all global selection rules disappear. The anomaly chapters separate these cases carefully.

### Boundaries and charged backgrounds

Boundaries can absorb charge. If a region has a boundary,

$$
\frac{dQ}{dt}=-\int_{\partial\text{space}}dS_i\,j^i.
$$

A bulk selection rule can be violated by boundary degrees of freedom carrying the missing charge. Likewise, background sources or defects can carry charge, so the correct selection rule includes them:

$$
Q_\mathrm{operators}+Q_\mathrm{background}+Q_\mathrm{boundary}=0.
$$

### Gauge redundancy

Gauge invariance is not an ordinary global symmetry selection rule. Physical local operators must be gauge-invariant. Gauge-charged fields may be useful variables inside a gauge-fixed calculation, but a nonzero expectation value of a gauge-variant local field is not a gauge-invariant observable.

In gauge theory, the closest physical analogues of charge selection rules involve Gauss’s law, boundary fluxes, line operators, and global parts of the gauge group. Those belong to the gauge-redundancy and higher-form-symmetry chapters.

## Common pitfalls

**Thinking “allowed” means “nonzero.”** A selection rule only says when symmetry forces a quantity to vanish. Dynamics may still make an allowed quantity zero.

**Using abelian charge addition for nonabelian groups.** Nonabelian selection rules are singlet or tensor-product rules, not simultaneous conservation of every generator eigenvalue.

**Forgetting the state.** Vacuum correlators require vacuum invariance. Matrix elements require charge balance between initial and final states.

**Applying a broken symmetry as if the vacuum were invariant.** In a spontaneously broken phase, only the unbroken subgroup imposes ordinary vacuum selection rules.

**Ignoring boundaries and backgrounds.** The missing charge may be sitting on a boundary, defect, source, or at infinity.

**Confusing global and gauge selection rules.** Gauge redundancy removes unphysical quantities; it is not a physical global symmetry acting on observables in the same way.

## Relations to other pages

[Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/) gives the operator proof that charged insertions shift charge sectors. [Symmetry Defects and Topological Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-defects-and-topological-operators/) gives the sliding-defect proof of the same selection rules.

[Symmetry Algebras](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-algebras/) explains how continuous charges close under commutators and how representation theory organizes nonabelian selection rules.

The [Noether Currents and Ward Identities](/symmetry-anomalies-topology/noether-currents-ward-identities/) chapter derives the local Ward identities behind selection rules. [Spontaneous Symmetry Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/) explains how selection rules change when the vacuum is not invariant. [Anomalies](/symmetry-anomalies-topology/anomalies/) explains anomalous modifications of Ward identities.

## Research status

Selection rules from exact ordinary symmetries are established textbook material.

The modern research frontier is not whether selection rules exist, but what the correct symmetry object is. In theories with higher-form symmetries, the charged objects are extended. In theories with non-invertible symmetries, selection rules can be projection rules associated with defect fusion rather than ordinary charge conservation. In anomalous theories, the selection rule may be realized by anomaly inflow or by a higher-dimensional bulk. In theories with boundaries, edge modes can carry the missing quantum numbers.

## Exercises

### Exercise 1: Charge-neutral two-point functions

Let $\mathcal O_q$ have $U(1)$ charge $q$. In an invariant vacuum, show that

$$
\langle \mathcal O_q(x)\mathcal O_q(y)\rangle=0
$$

unless $q=0$, while

$$
\langle \mathcal O_q(x)\mathcal O_q^\dagger(y)\rangle
$$

is allowed.

<details><summary><strong>Solution</strong></summary>

The first correlator has total charge $2q$. Charge neutrality requires $2q=0$. For an ordinary $U(1)$ with real charge lattice, this implies $q=0$.

The second correlator has charges $q$ and $-q$, so the total charge is zero. The symmetry does not force it to vanish.

</details>

### Exercise 2: Matrix-element balance

Suppose $Q|i\rangle=3|i\rangle$ and $Q|f\rangle=1|f\rangle$. A product of operators $\mathcal X$ has total $U(1)$ charge $q_\mathcal X$. What value of $q_\mathcal X$ is required for $\langle f|\mathcal X|i\rangle$ to be nonzero?

<details><summary><strong>Solution</strong></summary>

The selection rule is

$$
Q_f=Q_i+q_\mathcal X.
$$

Here $Q_i=3$ and $Q_f=1$, so

$$
1=3+q_\mathcal X.
$$

Therefore

$$
q_\mathcal X=-2.
$$

</details>

### Exercise 3: A finite symmetry rule

In a $\mathbb Z_4$-invariant theory, operators $A$, $B$, and $C$ have charges $1$, $2$, and $3$ modulo $4$. Is $\langle ABC\rangle$ allowed by the symmetry?

<details><summary><strong>Solution</strong></summary>

The total charge is

$$
1+2+3=6=2\quad\mathrm{mod}\,4.
$$

Since this is not zero modulo $4$, the correlator is forbidden in a $\mathbb Z_4$-invariant vacuum.

</details>

### Exercise 4: An SU(2) singlet test

For $SU(2)$, decide whether a vacuum three-point function of operators with spins $j_1=1/2$, $j_2=1/2$, and $j_3=1$ is allowed by symmetry.

<details><summary><strong>Solution</strong></summary>

First combine the two spin-$1/2$ representations:

$$
\frac12\otimes\frac12=0\oplus1.
$$

Then tensor with spin $1$:

$$
(0\oplus1)\otimes1=1\oplus(0\oplus1\oplus2).
$$

This contains spin $0$, so an invariant tensor exists. The correlator is allowed by $SU(2)$ symmetry.

</details>

### Exercise 5: Broken symmetry caveat

A theory has a $\mathbb Z_2$ symmetry $\sigma\mapsto-\sigma$. In a chosen infinite-volume broken vacuum, $\langle\sigma\rangle\ne0$. Does this contradict the $\mathbb Z_2$ selection rule?

<details><summary><strong>Solution</strong></summary>

No. The ordinary selection rule $\langle\sigma\rangle=0$ assumes that the vacuum is invariant under the $\mathbb Z_2$. In a spontaneously broken phase, the theory has the symmetry but the chosen infinite-volume vacuum does not. The symmetry maps one broken vacuum to another.

Only the unbroken subgroup imposes ordinary vacuum selection rules in a chosen broken vacuum.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on internal symmetries, currents, and Ward identities.
- Sidney Coleman, *Aspects of Symmetry*, especially lectures on unitary symmetry, soft pions, current algebra, and spontaneous symmetry breakdown.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, sections on symmetries, representations, and superselection.
- Mark Srednicki, *Quantum Field Theory*, sections 22–24 on continuous, discrete, and nonabelian symmetries.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, sections on Noether’s theorem, Ward–Takahashi identities, and Standard Model symmetry constraints.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” for the topological-operator generalization of selection rules.

## Version history

- **2026-06-17:** First polished draft for the Ordinary Global Symmetries chapter.
