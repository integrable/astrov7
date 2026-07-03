---
title: "Symmetry Groups and Representations"
description: "Explains how global symmetry groups act through representations on states, fields, local operators, tensor products, and correlation functions in QFT."
sidebar:
  label: "Groups and Representations"
  order: 4
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. I, Coleman lectures, Srednicki §§22–24, Zee; Gaiotto–Kapustin–Seiberg–Willett for the operator-first viewpoint."
topics:
  - symmetry groups
  - representations
  - irreducible multiplets
  - tensor products
  - selection rules
  - global form
canonicalTopics:
  - symmetry-group
  - representation-of-symmetry
  - operator-multiplet
  - global-form-of-symmetry
researchStatus:
  established:
    - "The representation-theoretic organization of states, fields, and local operators under ordinary global symmetries is standard QFT material."
  active:
    - "The same organizing idea extends to higher-form, non-invertible, categorical, and symmetry-TFT structures, where ordinary group representations are replaced by richer representation-like data."
---

## Summary

A symmetry group is abstract composition data. A representation is how that data acts on something physical.

An ordinary internal global symmetry group $G$ acts on the Hilbert space by operators $U(g)$ and on local operators by conjugation. In the convention used in this volume,

$$
U(g)^\dagger\mathcal O_i(x)U(g)=R(g)_i{}^j\mathcal O_j(x),
$$

where $R(g)$ is a matrix representation on the operator multiplet. For a continuous symmetry,

$$
U(\alpha)=e^{-i\alpha^aQ_a},
$$

and near the identity, define the infinitesimal operator-action matrices $\rho_a$ by

$$
R(\alpha)=1+i\alpha^a\rho_a+O(\alpha^2),
\qquad
[Q_a,\mathcal O_i]=(\rho_a)_i{}^j\mathcal O_j.
$$

The matrices $\rho_a$ are the ones that appear in the operator pullback convention used here. They may differ by a sign from the Hermitian generators used in a column-vector field convention. The finite transformation law is the safest object to compare across sources.

This is the representation-theoretic version of the slogan “symmetry determines quantum numbers.” Fields, local operators, currents, order parameters, particle states, boundary conditions, and line operators can all carry representations. A single QFT usually contains many representations of the same group.

The practical rule is:

$$
\text{a }G\text{-invariant object must be a singlet under }G.
$$

For $U(1)$, this becomes charge conservation. For a finite group, it becomes a finite-group selection rule. For a nonabelian group, it becomes the statement that the tensor product of the relevant representations must contain the trivial representation.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A diagram showing a symmetry group represented on fields, operators, states, and defects, with tensor products producing invariant tensors and selection rules.](/figures/symmetry-anomalies-topology/symmetry-representation-map.svg)

<figcaption>

The group $G$ becomes QFT data through representations on fields, operators, states, and defects. Tensor products then decide whether couplings, correlators, or OPE coefficients contain a singlet and hence can be symmetry-invariant.

</figcaption>
</figure>


## Prerequisites

You should know [What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/), [Internal versus Spacetime Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/internal-versus-spacetime-symmetries/), and [Continuous and Discrete Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/continuous-and-discrete-symmetries/).

We use

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

You only need basic group theory: representations, tensor products, direct sums, irreducible representations, and invariant tensors. Detailed Lie theory belongs to the Mathematical Toolkit.

## Core idea

A group names the symmetry. A representation says what transforms. A tensor product says what can couple.

For example, saying that a theory has $SU(2)$ symmetry is incomplete until we know whether a field, operator, or state transforms as a singlet, doublet, triplet, or some higher-spin representation. Saying that a theory has $U(1)$ symmetry is incomplete until we know the charge assignments. Saying that a spin model has a $\mathbb Z_2$ symmetry is incomplete until we know which operators are even and which are odd.

The same group can act on several different spaces:

| Object | Typical action | What the representation controls |
|---|---|---|
| Hilbert-space states | $|\psi_i\rangle\mapsto U(g)|\psi_i\rangle$ | degeneracies, superselection sectors, quantum numbers |
| elementary fields | $\Phi^I\mapsto D(g)^I{}_J\Phi^J$ | Lagrangian construction and perturbation theory |
| local operators | $\mathcal O_i\mapsto R(g)_i{}^j\mathcal O_j$ | correlators, OPEs, deformations, order parameters |
| sources | $J^i\mapsto J^jR(g^{-1})_j{}^i$ | generating functionals and spurions |
| products | $R\otimes S$ | selection rules and allowed couplings |
| extended probes | lines, surfaces, boundaries | generalized charges and defect sectors |

The conceptual upgrade is that field transformations are presentation-dependent, while the action on physical operators and states is intrinsic.

## Setup and conventions

Throughout this page, $G$ is an ordinary internal global symmetry. It is implemented on the Hilbert space by unitary operators $U(g)$ satisfying

$$
[H,U(g)]=0.
$$

Thus the symmetry maps energy eigenstates to energy eigenstates of the same energy.

A multiplet of local operators $\mathcal O_i$ transforms as

$$
U(g)^\dagger\mathcal O_i(x)U(g)=R(g)_i{}^j\mathcal O_j(x).
$$

For a continuous group, choose Hermitian charges $Q_a$ satisfying

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c.
$$

For an operator multiplet, define the matrices $\rho_a$ by

$$
[Q_a,\mathcal O_i]=(\rho_a)_i{}^j\mathcal O_j.
$$

Then

$$
U(\alpha)^{\dagger}\mathcal O_iU(\alpha)
=\mathcal O_i+i\alpha^a(\rho_a)_i{}^j\mathcal O_j+O(\alpha^2).
$$

:::note[Convention-sensitive formula]
The signs follow from $U(\alpha)=e^{-i\alpha^aQ_a}$ and the operator pullback convention $U^{\dagger}\mathcal O U$. If a source writes $U\mathcal O U^{-1}$ or uses anti-Hermitian generators, the matrices assigned to the same multiplet may differ by signs or inverses. The finite action $U(g)^{\dagger}\mathcal O U(g)=R(g)\mathcal O$ is the convention-independent datum once the side of conjugation is fixed.
:::

For antiunitary symmetries and spacetime symmetries, $U(g)$ may complex-conjugate coefficients or move the point $x$. Those cases are treated later.

## Representations on states

If $|E,i\rangle$ is a basis for a degenerate energy eigenspace, then symmetry acts within that eigenspace:

$$
U(g)|E,i\rangle=|E,j\rangle D_E(g)^j{}_i.
$$

The matrices $D_E(g)$ form a representation of $G$ on the degeneracy space. If this representation is irreducible, the states form one symmetry multiplet.

For an abelian $U(1)$ symmetry,

$$
Q|q\rangle=q|q\rangle,
\qquad
U(\alpha)|q\rangle=e^{-i\alpha q}|q\rangle.
$$

The charge $q$ is the representation label. For a nonabelian group, one usually cannot diagonalize all generators at once. Instead, states are grouped into multiplets. For $SU(2)$, one labels states by $j,m$, and the ladder generators move within the same spin-$j$ representation.

Schematic decompositions such as

$$
\mathcal H\simeq\bigoplus_R \mathcal K_R\otimes V_R
$$

are common. Here $V_R$ is an irreducible representation of $G$, while $\mathcal K_R$ contains the remaining labels: momentum, spin, energy, particle number, radial-quantization level, or degeneracy data. Infinite-volume QFTs, continuous spectra, constraints, and spontaneous breaking can complicate the direct-sum notation, but the representation idea remains the organizing principle.

## Representations on local operators

Local operators also form representations. This is often the cleanest language, especially in Euclidean QFT, conformal field theory, statistical field theory, and anomaly discussions.

Examples:

| Operator | Symmetry | Representation |
|---|---|---|
| complex scalar $\phi$ | $U(1)$ | charge $+1$ |
| $\phi^\dagger$ | $U(1)$ | charge $-1$ |
| real scalar multiplet $\phi^a$ | $O(N)$ | vector |
| $\phi^a\phi^a$ | $O(N)$ | singlet |
| $\phi^a\phi^b-\delta^{ab}\phi^2/N$ | $O(N)$ | symmetric traceless tensor |
| nonabelian current $j_a^\mu$ | $G$ | adjoint |

The operator representation is more durable than the field representation. A dual theory may not contain the same elementary fields, but it must reproduce the same symmetry action on the operator algebra.

## Tensor products and singlets

Selection rules are tensor-product statements.

Suppose the vacuum is invariant:

$$
U(g)|\Omega\rangle=|\Omega\rangle.
$$

Let $\mathcal O_1,\dots,\mathcal O_n$ transform in representations $R_1,\dots,R_n$. Then the correlator

$$
\langle\Omega|\mathcal O_1\cdots\mathcal O_n|\Omega\rangle
$$

is an invariant tensor in

$$
R_1\otimes\cdots\otimes R_n.
$$

Therefore it can be nonzero only if this tensor product contains the trivial representation.

For $U(1)$,

$$
\langle\mathcal O_{q_1}(x_1)\cdots\mathcal O_{q_n}(x_n)\rangle\ne0
\quad\Longrightarrow\quad
\sum_i q_i=0.
$$

For $\mathbb Z_N$,

$$
\sum_i q_i=0\mod N.
$$

For nonabelian groups, the statement is not “add all charges and get zero.” The statement is that the product representation must contain a singlet, and the correlator must be built from invariant tensors such as $\delta_{ij}$, $\epsilon_{ij}$, $f_{abc}$, $d_{abc}$, or Clebsch–Gordan coefficients.

As a tiny example,

$$
\mathbf 2\otimes \mathbf 2=\mathbf 1\oplus\mathbf 3
$$

for $SU(2)$. The singlet of two doublets $\psi^i$ and $\chi^j$ is

$$
\epsilon_{ij}\psi^i\chi^j.
$$

The invariant tensor $\epsilon_{ij}$ is what makes the expression a singlet.

## The Lie algebra is not the whole group

A continuous connected Lie group has a Lie algebra, but the Lie algebra does not determine the full global form of the symmetry.

The standard example is

$$
\mathfrak{su}(2)\simeq\mathfrak{so}(3),
\qquad
SO(3)=SU(2)/\mathbb Z_2.
$$

The spin-$1/2$ representation is an honest representation of $SU(2)$, but not of $SO(3)$. Thus two theories can have the same infinitesimal algebra and different allowed operator multiplets.

The global form affects:

- which representations are allowed;
- which charges are quantized;
- which background bundles may be turned on;
- which line operators are genuine;
- which quotient can be gauged;
- which anomalies are possible.

For $U(1)$, the parameter is periodic:

$$
\alpha\sim\alpha+2\pi.
$$

A one-dimensional representation $e^{iq\alpha}$ is single-valued only when $q\in\mathbb Z$ in the chosen normalization. The Lie algebra alone would not know this; the global group does.

:::note[Source note]
Textbook Noether calculations often emphasize Lie algebra generators because currents are infinitesimal. Background fields, topological terms, quotient groups, line operators, and anomalies require the actual group, not only its algebra.
:::

## Faithful actions and kernels

A representation can be unfaithful. Its kernel is

$$
\ker R=\{g\in G\mid R(g)=1\}.
$$

If a subgroup $K\subset G$ acts trivially on a set of operators, then the faithful group acting on that set is a quotient:

$$
G/K.
$$

In QFT this statement needs care. A central subgroup may act trivially on all local operators but nontrivially on extended operators, boundary conditions, or sectors defined on nontrivial manifolds. This is one reason modern symmetry discussions ask exactly which objects are included in the operator spectrum.

The safe formulation is:

$$
\text{specify the group and specify the objects on which it acts faithfully.}
$$

## Real, complex, and pseudoreal representations

Representations also have reality type.

A representation is **real** if it is equivalent to its complex conjugate by a symmetric invariant bilinear form. The vector representation of $SO(N)$ is the usual example.

A representation is **complex** if it is not equivalent to its conjugate. The fundamental representation of $SU(N)$ for $N\ge3$ is complex.

A representation is **pseudoreal** if it is equivalent to its conjugate by an antisymmetric invariant form. The fundamental of $SU(2)$ is the standard example.

This matters for constructing invariant terms. For example, a mass term, bilinear condensate, or Yukawa coupling exists only if the relevant tensor product contains a singlet with the right symmetry under exchange of identical fields. For fermions, Lorentz contraction and Fermi statistics add further signs. Representation reality is therefore not decorative; it decides which operators can exist.

## Projective representations as a preview

Quantum symmetries act on rays. Therefore the Hilbert-space operators may obey a projective group law:

$$
U(g_1)U(g_2)=e^{i\omega(g_1,g_2)}U(g_1g_2).
$$

Sometimes the phase can be removed by redefining $U(g)$. Sometimes it cannot. Spin-$1/2$ under spatial rotations is the most familiar example: one may view it as a projective representation of $SO(3)$ or an honest representation of its double cover $SU(2)$.

This chapter has a later page on projective representations. For now, the lesson is that the representation data of a quantum symmetry can include global phases not visible in a classical field transformation.

## Common pitfalls

**Confusing a group with one representation.** A theory can contain many representations of the same group. The field representation, operator representation, and state representation need not be the same.

**Stopping at the Lie algebra.** The Lie algebra misses global form, quotient data, finite centers, disconnected components, charge quantization, and allowed background bundles.

**Treating nonabelian symmetry as several independent charges.** Nonabelian generators do not commute. States form multiplets rather than simultaneous eigenstates of all generators.

**Forgetting invariant tensors.** A nonabelian singlet requires a specific invariant contraction. “The charges add up” is not a sufficient nonabelian rule.

**Confusing gauge representation with global representation.** Gauge-charged fields are not physical local observables in the same sense as gauge-invariant local operators.

**Ignoring operator mixing.** Composite operators with the same quantum numbers can mix under renormalization. Symmetry block-diagonalizes the problem; it does not make every classical monomial an eigenoperator.

## Relations to other pages

[Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/) applies this representation language to elementary fields, composite operators, sources, OPEs, and renormalized operator mixing.

[Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/) develops the state-side action. [Selection Rules](/symmetry-anomalies-topology/ordinary-global-symmetries/selection-rules/) turns the singlet condition into practical constraints. [Symmetry Algebras](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-algebras/) focuses on infinitesimal generators and Lie brackets.

The [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/) chapter returns to the global form of $G$, because coupling to background fields depends on the actual group. The anomaly chapters explain what can go wrong when the symmetry action cannot be made compatible with quantization or gauging.

## Research status

The representation theory used for ordinary global symmetries is established. Its use in QFT is standard.

The active frontier is the generalization of the idea. Higher-form symmetries act on extended operators. Non-invertible symmetries are implemented by topological defects that fuse by algebraic rules rather than group multiplication. Symmetry TFT packages symmetry and anomaly data in an auxiliary topological theory. All of these developments keep the basic instinct of this page: symmetries organize objects by how they transform.

## Exercises

### Exercise 1: U(1) neutrality

Let $\mathcal O_q$ transform as

$$
U(\alpha)^\dagger\mathcal O_qU(\alpha)=e^{iq\alpha}\mathcal O_q.
$$

Assume the vacuum is invariant. Show that

$$
\langle\mathcal O_{q_1}(x_1)\cdots\mathcal O_{q_n}(x_n)\rangle
$$

can be nonzero only if $\sum_i q_i=0$.

<details><summary><strong>Solution</strong></summary>

Insert $1=U(\alpha)U(\alpha)^\dagger$ and use vacuum invariance:

$$
\begin{aligned}
\langle\mathcal O_{q_1}\cdots\mathcal O_{q_n}\rangle
&=\langle U(\alpha)^\dagger\mathcal O_{q_1}\cdots\mathcal O_{q_n}U(\alpha)\rangle \\
&=e^{i\alpha(q_1+\cdots+q_n)}
\langle\mathcal O_{q_1}\cdots\mathcal O_{q_n}\rangle.
\end{aligned}
$$

If the correlator is nonzero, the phase must equal one for every $\alpha$, so $q_1+\cdots+q_n=0$.

</details>

### Exercise 2: Singlet from two SU(2) doublets

Let $\psi^i$ and $\chi^i$ transform as doublets of $SU(2)$. Show that $\epsilon_{ij}\psi^i\chi^j$ is invariant.

<details><summary><strong>Solution</strong></summary>

Under $R\in SU(2)$,

$$
\psi^i\mapsto R^i{}_k\psi^k,
\qquad
\chi^j\mapsto R^j{}_\ell\chi^\ell.
$$

Then

$$
\epsilon_{ij}\psi^i\chi^j
\mapsto
\epsilon_{ij}R^i{}_kR^j{}_\ell\psi^k\chi^\ell.
$$

The invariant tensor obeys

$$
\epsilon_{ij}R^i{}_kR^j{}_\ell=\epsilon_{k\ell}\det R=\epsilon_{k\ell},
$$

because $\det R=1$. Hence the bilinear is invariant.

</details>

### Exercise 3: Kernel and quotient

Suppose every element of a normal subgroup $K\subset G$ acts trivially on all local operators. Show that the local operator algebra carries an action of $G/K$.

<details><summary><strong>Solution</strong></summary>

If $k\in K$, then $R(gk)=R(g)R(k)=R(g)$. Thus the action depends only on the equivalence class $[g]\in G/K$. Define

$$
\widetilde R([g])=R(g).
$$

This is well-defined and obeys

$$
\widetilde R([g_1][g_2])=R(g_1g_2)=R(g_1)R(g_2).
$$

So $G/K$ acts on the local operator algebra. The physical caveat is that $K$ might still act on extended operators or boundary sectors.

</details>

### Exercise 4: Infinitesimal action

Use

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
U(\alpha)^\dagger\mathcal O_iU(\alpha)
=\left(1+i\alpha^a\rho_a+O(\alpha^2)\right)_i{}^j\mathcal O_j
$$

to derive

$$
[Q_a,\mathcal O_i]=(\rho_a)_i{}^j\mathcal O_j.
$$

<details><summary><strong>Solution</strong></summary>

Expand the left-hand side:

$$
U(\alpha)^\dagger\mathcal O_iU(\alpha)
=(1+i\alpha^aQ_a)\mathcal O_i(1-i\alpha^aQ_a)+O(\alpha^2).
$$

Therefore

$$
U(\alpha)^\dagger\mathcal O_iU(\alpha)
=\mathcal O_i+i\alpha^a[Q_a,\mathcal O_i]+O(\alpha^2).
$$

Comparing with the representation expansion gives

$$
[Q_a,\mathcal O_i]=(\rho_a)_i{}^j\mathcal O_j.
$$

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially the lectures on unitary symmetry, soft pions, scale symmetry, and spontaneous symmetry breaking.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on spacetime and internal symmetries.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapters on symmetries, one-particle states, and projective representations.
- Mark Srednicki, *Quantum Field Theory*, sections 22–24 on continuous, discrete, and nonabelian symmetries.
- A. Zee, *Quantum Field Theory in a Nutshell*, chapters on symmetry and group theory.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” *JHEP* 02 (2015) 172.

## Version history

- **2026-06-17:** First polished draft for the Ordinary Global Symmetries chapter.
