---
title: "Charge Conjugation"
description: "Defines charge conjugation in QFT, explains particle–antiparticle exchange, conjugate representations, scalar and spinor transformation rules, gauge-background signs, Majorana subtleties, and charge-conjugation violation."
sidebar:
  label: "Charge Conjugation"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §§23, 40; Weinberg Vol. I Chs. 2, 5; Coleman, Lectures on QFT ch. 22; Schwartz ch. 11; standard treatments of charge conjugation, Majorana fields, and discrete symmetries."
topics:
  - charge conjugation
  - particle-antiparticle exchange
  - conjugate representations
  - Dirac fields
  - Majorana fields
  - gauge backgrounds
  - CP symmetry
canonicalTopics:
  - charge-conjugation
  - conjugate-representation
  - charge-conjugate-spinor
  - majorana-field
  - particle-antiparticle
  - c-symmetry
researchStatus:
  established:
    - "Charge conjugation exchanges charges and conjugate representations; its standard action on scalar, Dirac, Majorana, gauge, and current operators is textbook QFT material once phases are fixed."
    - "Charge conjugation is a possible unitary internal transformation, not an automatic property of every theory; chiral and representation-asymmetric theories need not possess it."
  active:
    - "Charge conjugation remains important in modern anomaly, CP, real/pseudoreal representation, orientifold, lattice, and topological-phase contexts, especially when combined with spacetime reflections or higher-form backgrounds."
---

## Summary

Charge conjugation is the operation that exchanges particles with antiparticles. It reverses internal charges and maps representations to conjugate representations:

$$
q\mapsto -q,
\qquad
R\mapsto R^*.
$$

Unlike time reversal, charge conjugation is usually represented by a **unitary** operator on the Hilbert space. We denote it by $\mathcal C$. For a charge operator $Q$,

$$
\mathcal C^\dagger Q\mathcal C=-Q.
$$

For a complex scalar field of charge $q$,

$$
\mathcal C^\dagger\phi(x)\mathcal C
=\eta_C\phi^\dagger(x),
$$

where $\eta_C$ is a convention-dependent phase. For a Dirac field,

$$
\mathcal C^\dagger\psi(x)\mathcal C
=\eta_C\psi^c(x),
\qquad
\psi^c\equiv C_D\bar\psi^T.
$$

Here $C_D$ is the charge-conjugation matrix acting on spinor indices. Do not confuse it with the Hilbert-space operator $\mathcal C$.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A charge-conjugation dictionary. A charged operator with charge q in representation R maps to an operator with charge minus q in the conjugate representation. A scalar maps to its dagger, a Dirac field maps to its charge-conjugate spinor, and an Abelian gauge background maps to minus itself.](/figures/symmetry-anomalies-topology/charge-conjugation-dictionary.svg)

<figcaption>

Charge conjugation reverses internal charges and sends representations to conjugate representations. For Abelian gauge backgrounds this gives $A_\mu\mapsto -A_\mu$. For non-Abelian groups, the transformation is encoded by complex conjugation of the representation, and may require an automorphism of the gauge algebra.

</figcaption>
</figure>

The most important warning is:

$$
\text{charge conjugation}\neq\text{complex conjugation of every formula}.
$$

Charge conjugation is an operator acting on the QFT Hilbert space and operator algebra. It may involve complex conjugate representations, but it is not the antiunitary operation of ordinary complex conjugation. That antiunitary role belongs to time reversal or related antiunitary symmetries.

## Prerequisites

Read [Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/parity/) and [Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/time-reversal/) first. They separate spacetime reflection, antiunitarity, and background-field transformation.

You should also know [Symmetry Groups and Representations](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-groups-and-representations/), [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/), and [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/).

We use

$$
\bar\psi=\psi^\dagger\gamma^0,
\qquad
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu},
\qquad
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1).
$$

The covariant derivative convention for a field in representation $R$ is

$$
D_\mu=\partial_\mu-iA_\mu^aT_R^a.
$$

## Core idea

Charge conjugation asks whether the theory of charges is equivalent to the theory of opposite charges.

In QED this sounds natural: an electron and a positron have opposite electric charges, and the electromagnetic field changes sign under charge conjugation. But this is not automatic in all QFTs. A theory may contain a field in representation $R$ without containing a matching field in $R^*$. A chiral interaction may treat particles and antiparticles differently. A background chemical potential may select one charge sign over the other.

The transformation has three layers:

| Layer | Charge conjugation does this |
|---|---|
| Charge labels | Sends $q\mapsto -q$. |
| Representations | Sends $R\mapsto R^*$. |
| Fields and operators | Maps charged fields to conjugate fields, and charged operators to oppositely charged operators. |
| Backgrounds | Sends a background field coupled to a C-odd current to the corresponding conjugate background. |

The transformation rule exists as a useful dictionary even when $\mathcal C$ is not a symmetry of the theory. The theory is charge-conjugation invariant only when the action, measure, state, and backgrounds are invariant under the full operation.

## Setup and conventions

We write the Hilbert-space charge-conjugation operator as $\mathcal C$. Since it is unitary,

$$
\mathcal C^\dagger\mathcal C=1,
$$

and numerical coefficients are not automatically complex-conjugated:

$$
\mathcal C^\dagger(a\mathcal O+b\mathcal P)\mathcal C
=a\mathcal C^\dagger\mathcal O\mathcal C+b\mathcal C^\dagger\mathcal P\mathcal C.
$$

This is different from time reversal.

For an Abelian charge $Q$,

$$
\mathcal C^\dagger Q\mathcal C=-Q.
$$

For a non-Abelian symmetry or gauge group, the corresponding statement is not that every generator simply gets a minus sign in a basis-independent way. The invariant statement is that the representation is conjugated:

$$
R\mapsto R^*.
$$

If $T_R^a$ are Hermitian generators in $R$, then a convenient set of generators in the conjugate representation is

$$
T_{R^*}^a=-(T_R^a)^T.
$$

The minus sign appears because the infinitesimal transformation of the conjugate field is the complex conjugate of the inverse transformation.

:::note[Convention-sensitive source note]
The phase of $\mathcal C$ on a field and the phase of the spinor matrix $C_D$ are conventional. Physical statements are phase-invariant: whether a term is allowed, whether a current is C-even or C-odd, and whether a representation is mapped to an available conjugate representation.
:::

## Charges, antiparticles, and representations

A charged particle state may transform as

$$
\mathcal C|\mathbf p,s,q,a\rangle
=\sum_b U_{ba}|\mathbf p,s,-q,b\rangle,
$$

where $a,b$ label degeneracies. Charge conjugation does not reverse the spatial momentum or spin by itself. Those are parity and time-reversal issues.

If the field transforms in a representation $R$ of a group $G$, the charge-conjugate field transforms in $R^*$. For real representations,

$$
R\simeq R^*,
$$

so charge conjugation may act within the same representation after a change of basis. For pseudoreal representations, such as the fundamental of $SU(2)$, there is also an invariant antisymmetric tensor identifying $R$ with $R^*$. For genuinely complex representations, such as the fundamental of $SU(N)$ with $N\ge3$, $R$ and $R^*$ are inequivalent.

This is why charge conjugation is sensitive to representation content. A theory with matter in $R$ but no corresponding matter in $R^*$ generally cannot have ordinary charge-conjugation symmetry.

## Complex scalar fields

For a complex scalar field with charge $q$ under a $U(1)$ symmetry,

$$
\phi(x)\mapsto e^{iq\alpha}\phi(x).
$$

The conjugate field transforms as

$$
\phi^\dagger(x)\mapsto e^{-iq\alpha}\phi^\dagger(x).
$$

Therefore charge conjugation acts as

$$
\mathcal C^\dagger\phi(x)\mathcal C=\eta_C\phi^\dagger(x),
\qquad
\mathcal C^\dagger\phi^\dagger(x)\mathcal C=\eta_C^*\phi(x),
$$

where consistency with $\mathcal C^\dagger\mathcal C=1$ fixes the second phase once the first is chosen.

The conserved current of the free complex scalar may be written, with our covariant-derivative conventions at zero background, as

$$
j^\mu=i\phi^\dagger\overleftrightarrow{\partial^\mu}\phi
=i\phi^\dagger\partial^\mu\phi-i(\partial^\mu\phi^\dagger)\phi.
$$

Under charge conjugation,

$$
\mathcal C^\dagger j^\mu\mathcal C=-j^\mu.
$$

Thus the charge

$$
Q=\int d^3\mathbf x\,j^0
$$

is C-odd, as it must be.

A real scalar is neutral and may have a charge-conjugation parity

$$
\mathcal C^\dagger\varphi\mathcal C=\eta_C\varphi,
\qquad
\eta_C=\pm1,
$$

if the theory has such a discrete internal symmetry. In particle physics this label is often called a C-parity for neutral states.

## Abelian gauge fields

The QED coupling is

$$
\mathcal L_{\text{int}}=-A_\mu j^\mu
$$

up to the convention for where the electric charge is included. Since the electric current is C-odd,

$$
j^\mu\mapsto -j^\mu,
$$

charge conjugation requires the electromagnetic gauge potential to be C-odd:

$$
A_\mu\mapsto -A_\mu.
$$

Therefore

$$
F_{\mu\nu}\mapsto -F_{\mu\nu},
\qquad
\mathbf E\mapsto -\mathbf E,
\qquad
\mathbf B\mapsto -\mathbf B.
$$

The Maxwell kinetic term is C-even:

$$
F_{\mu\nu}F^{\mu\nu}\mapsto F_{\mu\nu}F^{\mu\nu}.
$$

The theta density is also C-even:

$$
F_{\mu\nu}\widetilde F^{\mu\nu}
\mapsto
F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

This differs from parity and time reversal, both of which make $F\widetilde F$ odd.

If $A_\mu$ is a nondynamical background field for a global $U(1)$ symmetry, the same logic applies: to test charge conjugation, one must transform the background as $A\mapsto -A$. Holding a chemical potential or background charge density fixed often breaks charge conjugation.

## Dirac fields and charge-conjugate spinors

For a Dirac field, define the charge-conjugate spinor

$$
\psi^c\equiv C_D\bar\psi^T,
$$

where the spinor charge-conjugation matrix $C_D$ satisfies

$$
C_D^{-1}\gamma^\mu C_D=-(\gamma^\mu)^T.
$$

A common Dirac-basis choice is

$$
C_D=i\gamma^2\gamma^0,
$$

up to an overall phase.

Charge conjugation acts on the field as

$$
\mathcal C^\dagger\psi(x)\mathcal C
=\eta_C\psi^c(x),
$$

and on the conjugate field as

$$
\mathcal C^\dagger\bar\psi(x)\mathcal C
=\eta_C^*\overline{\psi^c}(x).
$$

The free Dirac Lagrangian

$$
\mathcal L=\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
$$

is invariant under charge conjugation. The QED Lagrangian is also invariant when both the matter field and the electromagnetic field transform:

$$
\psi\mapsto\psi^c,
\qquad
A_\mu\mapsto -A_\mu.
$$

A useful way to remember this is that the covariant derivative acting on a charge-$q$ field,

$$
D_\mu=\partial_\mu-iqA_\mu,
$$

is mapped to the corresponding derivative acting on a charge-$-q$ field.

## Dirac bilinears

Charge conjugation gives a clean sign table for standard Dirac bilinears. With the usual Hermitian convention for the pseudoscalar,

| Bilinear | C parity |
|---|---:|
| $\bar\psi\psi$ | even |
| $i\bar\psi\gamma^5\psi$ | even |
| $\bar\psi\gamma^\mu\psi$ | odd |
| $\bar\psi\gamma^\mu\gamma^5\psi$ | even |
| $\bar\psi\sigma^{\mu\nu}\psi$ | odd |
| $\bar\psi\sigma^{\mu\nu}\gamma^5\psi$ | odd |

The vector current is C-odd because it measures charge flow. The axial current is C-even because it measures a spin/chirality imbalance rather than electric charge.

For example, the QED interaction

$$
A_\mu\bar\psi\gamma^\mu\psi
$$

is C-even because both factors are C-odd:

$$
A_\mu\mapsto -A_\mu,
\qquad
\bar\psi\gamma^\mu\psi\mapsto -\bar\psi\gamma^\mu\psi.
$$

A coupling of a neutral scalar $\varphi$ to $\bar\psi\psi$ is C-even if $\varphi$ is C-even. A coupling of a neutral field to the vector current requires that the neutral field itself be C-odd if the term is to preserve charge conjugation.

:::note[Derivation note]
The bilinear table follows from $C_D^{-1}\gamma^\mu C_D=-(\gamma^\mu)^T$ and the anticommutation of fermion fields. One must include the sign from exchanging Grassmann-odd fields; otherwise the vector and axial signs are easy to get wrong.
:::

## Majorana fields

A Majorana field obeys

$$
\chi^c=\chi.
$$

It is its own antiparticle. This does not mean charge conjugation is trivial on every operator built from $\chi$. It means that the charge-conjugate spinor is not an independent field.

A Majorana mass term is

$$
\mathcal L_m=-\frac12m\bar\chi\chi.
$$

The factor $1/2$ avoids double-counting degrees of freedom. A Majorana field cannot carry an ordinary conserved $U(1)$ charge, because charge conjugation would reverse that charge while the field is identified with its own conjugate.

For a single Majorana field, some bilinears vanish identically. In particular,

$$
\bar\chi\gamma^\mu\chi=0
$$

for the ordinary vector current, while the axial current

$$
\bar\chi\gamma^\mu\gamma^5\chi
$$

need not vanish. This is consistent with the C-parity table: the vector current is C-odd and cannot be built as a nonzero current of a self-conjugate field without another label.

Majorana conditions are only available for suitable Lorentz and internal representations. In four-dimensional Lorentzian QFT, a gauge-charged Majorana fermion requires a real representation, or a more careful construction using multiple fields and invariant tensors.

## Chiral fermions and representation asymmetry

Charge conjugation is especially delicate in chiral theories.

A left-handed Weyl field in a complex representation $R$ has a charge-conjugate field in the conjugate representation $R^*$ with opposite chirality in four-component notation. In two-component notation one can rewrite the charge-conjugate degree of freedom as another left-handed Weyl field in $R^*$, but it is still a different representation.

Thus a theory containing only

$$
\psi_L\in R
$$

and no corresponding field in $R^*$ generally has no ordinary charge-conjugation symmetry. This is one reason chiral gauge theories are intrinsically asymmetric between particles and antiparticles in a way that vectorlike theories are not.

The Standard Model weak interaction famously violates charge conjugation. A purely left-handed charged current is not mapped by $\mathcal C$ to the same left-handed current structure. The combined operation $CP$ is closer to a symmetry, but it too is violated by physical flavor phases.

The lesson is not “charge conjugation is impossible in chiral theories.” The lesson is that the field content and representation data must support it.

## Charge conjugation versus complex conjugation

It is tempting to say that charge conjugation just complex-conjugates the fields. That is not correct.

Charge conjugation is unitary. It does not complex-conjugate arbitrary numbers multiplying operators. For example,

$$
\mathcal C^\dagger(i\mathcal O)\mathcal C
=i\mathcal C^\dagger\mathcal O\mathcal C.
$$

Time reversal would instead send $i$ to $-i$.

Charge conjugation can map a field to a Hermitian conjugate field or a conjugate representation. That is a transformation of the operator algebra, not the same as applying ordinary complex conjugation to an equation.

A useful comparison is:

| Operation | Unitary or antiunitary? | Main action |
|---|---|---|
| Parity | usually unitary | reverses spatial orientation |
| Time reversal | antiunitary | reverses motion and sends $i\mapsto -i$ |
| Charge conjugation | usually unitary | reverses internal charges and representations |

This is why $C$, $P$, $T$, $CP$, and $CPT$ have distinct logical roles.

## Charge conjugation in non-Abelian gauge theory

For non-Abelian gauge theory, charge conjugation is best written in matrix notation. Let

$$
A_\mu=A_\mu^aT_R^a
$$

act on matter in representation $R$. The conjugate representation uses

$$
T_{R^*}^a=-(T_R^a)^T.
$$

A charge-conjugated covariant derivative should act on fields in $R^*$:

$$
D_\mu\phi=(\partial_\mu-iA_\mu^aT_R^a)\phi
\quad\longrightarrow\quad
D_\mu^*\phi^c=(\partial_\mu-iA_\mu^{c,a}T_{R^*}^a)\phi^c.
$$

In a convenient matrix notation this is often summarized as

$$
A_\mu\mapsto -A_\mu^T,
$$

with the transpose acting on representation matrices. For $SU(N)$ Yang–Mills this is related to the complex-conjugation automorphism of the group. For $SU(N)$ with $N\ge3$, this is an outer automorphism; for groups with only real representations the story can collapse to an inner transformation or become trivial in a suitable basis.

The pure Yang–Mills kinetic term is invariant under this operation because it is built from traces such as

$$
\operatorname{tr}F_{\mu\nu}F^{\mu\nu}.
$$

Matter couplings are invariant only if the matter content and interactions are mapped back to themselves.

This global-form and representation dependence becomes important in modern discussions of line operators, one-form symmetries, and discrete gauging.

## C, CP, and backgrounds

A theory may violate $C$ but preserve $CP$, or vice versa, depending on its interactions and backgrounds.

For electromagnetism, the field signs are:

| Field | C | P | T |
|---|---:|---:|---:|
| $\mathbf E$ | $-$ | $-$ | $+$ |
| $\mathbf B$ | $-$ | $+$ | $-$ |
| $\mathbf E\cdot\mathbf B$ | $+$ | $-$ | $-$ |

Thus a theta term is C-even but P-odd and T-odd. It is also CP-odd, because C leaves $\mathbf E\cdot\mathbf B$ even while P flips it.

A chemical potential illustrates a different point. If

$$
H_\mu=H-\mu Q,
$$

and $Q$ is C-odd, then charge conjugation maps

$$
H_\mu\mapsto H+\mu Q.
$$

The system at fixed $\mu$ is generally not C-invariant unless one also sends

$$
\mu\mapsto -\mu.
$$

That is not a contradiction. Background sources transform under symmetries. Holding a C-odd background fixed explicitly breaks $C$.

## Neutral states and C parity

For a neutral particle or operator, charge conjugation may be represented by an eigenvalue:

$$
\mathcal C^\dagger\mathcal O\mathcal C=\eta_C\mathcal O,
\qquad
\eta_C=\pm1.
$$

This is called C parity. It is useful for neutral mesons, photon-number states, and selection rules in theories where charge conjugation is a good symmetry.

For photons,

$$
\mathcal C^\dagger A_\mu\mathcal C=-A_\mu.
$$

Thus a one-photon state has C parity $-1$, while an $n$-photon state has C parity

$$
(-1)^n,
$$

up to orbital and polarization details irrelevant to this simple counting. This kind of rule underlies selection rules for decays of neutral states into photons when charge conjugation is conserved.

The same logic does not apply if the state is charged. A charged state is not an eigenstate of $\mathcal C$ because $\mathcal C$ maps it to a different charge sector.

## Common pitfalls

**Pitfall 1: Calling charge conjugation antiunitary.**

Charge conjugation is usually unitary. Time reversal is antiunitary. The word “conjugation” in charge conjugation refers to charges and representations, not to complex conjugating all coefficients.

**Pitfall 2: Forgetting to transform gauge fields.**

The QED interaction is C-invariant only because both $j^\mu$ and $A_\mu$ are C-odd.

**Pitfall 3: Assuming every neutral field is C-even.**

A neutral field can be C-even or C-odd. The assignment is part of the symmetry action.

**Pitfall 4: Treating $R$ and $R^*$ as automatically identical.**

Some representations are real or pseudoreal, but many are genuinely complex. Charge conjugation can fail simply because the conjugate representation is absent.

**Pitfall 5: Confusing Majorana with “no transformation.”**

A Majorana field is self-conjugate, but operators built from it still have C-parity properties, and some bilinears vanish because of fermion statistics.

**Pitfall 6: Testing C at fixed C-odd background.**

A chemical potential, background charge density, or Abelian background gauge field can explicitly break C if it is held fixed rather than transformed.

## Relations to other pages

[Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/parity/) and [Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/time-reversal/) explain the spacetime and antiunitary partners of charge conjugation.

[Symmetry Groups and Representations](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-groups-and-representations/) explains representations and conjugate representations in the ordinary symmetry language.

[Global Form of Symmetry Groups](/symmetry-anomalies-topology/background-fields-and-gauging/global-form-of-symmetry-groups/) explains why representation data and charge lattices matter beyond the Lie algebra.

[Background Fields versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/) explains why sources must transform and why gauging changes the operator algebra.

Later pages on CPT, spin structures, and anomalies of discrete symmetries refine the global and fermionic aspects of charge conjugation.

## Research status

The local transformation rules of charge conjugation are established textbook material. The representation-theoretic and global refinements remain important in modern QFT.

Active uses include charge conjugation as an outer automorphism of non-Abelian groups, its role in CP and time-reversal anomaly discussions, the classification of fermionic phases, lattice implementations of real and pseudoreal representations, and the interplay between charge conjugation and higher-form or non-invertible symmetries.

The practical research lesson is that $C$ is not a decorative label. It is a precise automorphism of the operator algebra, and it may or may not exist for a given theory.

## Exercises

### Exercise 1: Complex scalar current

Let

$$
j^\mu=i\phi^\dagger\overleftrightarrow{\partial^\mu}\phi.
$$

Using $\mathcal C^\dagger\phi\mathcal C=\phi^\dagger$, show that $j^\mu$ is C-odd.

<details><summary><strong>Solution</strong></summary>

Under charge conjugation,

$$
\phi\mapsto\phi^\dagger,
\qquad
\phi^\dagger\mapsto\phi.
$$

Therefore

$$
j^\mu
=i\phi^\dagger\partial^\mu\phi-i(\partial^\mu\phi^\dagger)\phi
$$

maps to

$$
i\phi\partial^\mu\phi^\dagger-i(\partial^\mu\phi)\phi^\dagger.
$$

For bosonic fields at equal points inside the local composite, this is

$$
-\left[i\phi^\dagger\partial^\mu\phi-i(\partial^\mu\phi^\dagger)\phi\right]
=-j^\mu,
$$

up to the usual local-operator renormalization conventions. Thus the scalar charge current is C-odd.

</details>

### Exercise 2: QED interaction

Assume

$$
A_\mu\mapsto -A_\mu,
\qquad
j^\mu=\bar\psi\gamma^\mu\psi\mapsto -j^\mu.
$$

Show that the interaction $A_\mu j^\mu$ is C-even.

<details><summary><strong>Solution</strong></summary>

The product transforms as

$$
A_\mu j^\mu
\mapsto
(-A_\mu)(-j^\mu)
=A_\mu j^\mu.
$$

Thus the interaction is invariant. This is the basic reason QED can preserve charge conjugation even though the electromagnetic field itself is C-odd.

</details>

### Exercise 3: Photon C parity

Using $\mathcal C^\dagger A_\mu\mathcal C=-A_\mu$, argue that an $n$-photon state has C parity $(-1)^n$ when charge conjugation is a good symmetry.

<details><summary><strong>Solution</strong></summary>

The field $A_\mu$ creates or annihilates one photon and is C-odd. Thus the photon creation operator transforms with a minus sign, schematically

$$
a^\dagger\mapsto -a^\dagger.
$$

An $n$-photon state is produced by applying $n$ such creation operators to the vacuum. If the vacuum is C-even,

$$
\mathcal C(a_1^\dagger\cdots a_n^\dagger|0\rangle)
=(-1)^n a_1^\dagger\cdots a_n^\dagger|0\rangle.
$$

So the C parity is $(-1)^n$, modulo the usual details of angular momentum and polarization needed for a fully specified state.

</details>

### Exercise 4: Why a lone complex representation can break C

Consider a theory with a left-handed Weyl fermion in a complex representation $R$ of a group $G$, but no field in $R^*$. Explain why ordinary charge conjugation is generally not a symmetry.

<details><summary><strong>Solution</strong></summary>

Charge conjugation sends representation $R$ to the conjugate representation $R^*$. If the theory has no corresponding field in $R^*$, then the transformed field is not an operator in the same theory. Therefore $\mathcal C$ cannot act as an automorphism of the operator algebra.

There may be special exceptions if $R\simeq R^*$, if charge conjugation is combined with a nontrivial automorphism, or if the theory maps to a distinct conjugate theory. But an ordinary C symmetry of one theory requires the field content and interactions to be closed under $R\mapsto R^*$.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §§23 and 40. Discrete symmetries for scalar and spinor fields.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, especially Chs. 2 and 5. Symmetry representations, charge conjugation, and free-field transformation laws.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 22. CPT and Fermi fields.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 11. Charge conjugation, parity, time reversal, and spinor conventions.
- Claude Itzykson and Jean-Bernard Zuber, *Quantum Field Theory*, sections on charge conjugation and bilinear covariants.
- Michael E. Peskin and Daniel V. Schroeder, *An Introduction to Quantum Field Theory*, sections on discrete symmetries and spinor fields.
- Howard Georgi, *Lie Algebras in Particle Physics*, for representation conjugation, real and pseudoreal representations, and group-theory conventions.
- Standard reviews on CP violation, Majorana fermions, and discrete symmetries in gauge theory.

## Version history

- 2026-06-17: Initial polished page. Added scalar, spinor, Majorana, Abelian and non-Abelian gauge-field transformation rules, bilinear C-parity table, representation-content caveats, C versus complex conjugation, background-source warnings, neutral-state C parity, and exercises with solutions.
