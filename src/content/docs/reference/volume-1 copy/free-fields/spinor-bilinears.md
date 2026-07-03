---
title: "Spinor Bilinears"
description: "The Dirac bilinear dictionary: scalar, pseudoscalar, vector, axial-vector, and tensor bilinears; Lorentz transformation, parity, charge conjugation, chirality, Majorana constraints, and common interaction terms."
sidebar:
  label: "Spinor Bilinears"
  order: 4
---

## Summary

Spinor bilinears are the basic Lorentz-covariant objects built from a spinor and its Dirac adjoint. For a Dirac field $\psi$, the standard basis is

$$
\boxed{
\overline\psi\psi,
\qquad
 i\overline\psi\gamma^5\psi,
\qquad
\overline\psi\gamma^\mu\psi,
\qquad
\overline\psi\gamma^\mu\gamma^5\psi,
\qquad
\overline\psi\sigma^{\mu\nu}\psi,
}
$$

where

$$
\overline\psi=\psi^\dagger\gamma^0,
\qquad
\sigma^{\mu\nu}=\frac{i}{2}[\gamma^\mu,\gamma^\nu].
$$

These five types contain

$$
1+1+4+4+6=16
$$

independent matrices, a basis for all complex $4\times4$ matrices. They are classified as scalar, pseudoscalar, vector, axial vector, and antisymmetric tensor:

| Type | Bilinear | Components | Parity behavior | Charge conjugation |
| --- | --- | ---: | --- | --- |
| Scalar | $\overline\psi\psi$ | 1 | even | even |
| Pseudoscalar | $i\overline\psi\gamma^5\psi$ | 1 | odd | even |
| Vector | $\overline\psi\gamma^\mu\psi$ | 4 | $(V^0,\mathbf V)\mapsto(V^0,-\mathbf V)$ | odd |
| Axial vector | $\overline\psi\gamma^\mu\gamma^5\psi$ | 4 | $(A^0,\mathbf A)\mapsto(-A^0,\mathbf A)$ | even |
| Tensor | $\overline\psi\sigma^{\mu\nu}\psi$ | 6 | $T^{0i}$ odd, $T^{ij}$ even | odd |

The signs in the last two columns are for a single Dirac field and omit possible intrinsic phases or flavor matrices. Weinberg gives this scalar/vector/tensor/axial/pseudoscalar classification and the corresponding charge-conjugation signs; Coleman presents the same sixteen bilinears as the basis from which spinor interactions are built (Weinberg 1995, Vol. I, §5.5; Coleman 2019, ch. 20 and ch. 22).

## Prerequisites

You should know [Dirac Field](/foundations/free-fields/dirac-field/), [Weyl and Majorana Fields](/foundations/free-fields/weyl-and-majorana-fields/), [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/), and [Conventions and Normalizations](/foundations/conventions-and-normalizations/). We use qft.org's mostly-minus gamma-matrix convention.

## Core idea

Spinors themselves are not Lorentz scalars, so individual spinor components are rarely observables or Lagrangian terms. Bilinears are the simplest covariant packages. They tell you which fermion interactions can be scalars, which currents couple to vector fields, which terms violate parity, and which operators are allowed by charge conjugation or chirality.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Basis of Dirac spinor bilinears and their parity and charge-conjugation signs](/figures/foundations/spinor-bilinear-basis.svg)

<figcaption>

The five standard Dirac bilinear types form a basis of sixteen matrices. The parity entries show ordinary component behavior: vectors have even time and odd space components, axial vectors have odd time and even space components, and tensors split into electric-like $T^{0i}$ and magnetic-like $T^{ij}$ pieces.

</figcaption>
</figure>

The point is not to memorize a table for its own sake. The point is to read interactions. For example, $A_\mu\overline\psi\gamma^\mu\psi$ couples a vector field to a vector current, while $\phi\overline\psi\psi$ is a scalar Yukawa coupling.

:::note[Assumptions]
The table assumes flat four-dimensional Minkowski spacetime, a single Dirac field, and standard charge-conjugation phase choices. With multiple flavors, gauge generators, or nontrivial intrinsic phases, the symmetry of the full operator includes the spinor bilinear and the flavor/gauge matrix.
:::

## The sixteen-matrix basis

The Dirac gamma matrices generate the full algebra of $4\times4$ complex matrices. A convenient basis is

$$
\boxed{
\mathbf 1,
\qquad
\gamma^5,
\qquad
\gamma^\mu,
\qquad
\gamma^\mu\gamma^5,
\qquad
\sigma^{\mu\nu}.
}
$$

Counting components gives

$$
1+1+4+4+6=16.
$$

The six tensor components come from antisymmetry:

$$
\sigma^{\mu\nu}=-\sigma^{\nu\mu}.
$$

A general spinor bilinear has the form

$$
\overline\psi\Gamma\psi,
$$

where $\Gamma$ is a linear combination of the sixteen basis matrices.

The factor $i$ in

$$
i\overline\psi\gamma^5\psi
$$

is a convention chosen so that the pseudoscalar bilinear is Hermitian for the usual gamma-matrix Hermiticity conventions. Some books instead define the pseudoscalar without the $i$ and compensate elsewhere. Always check the convention before comparing signs.

## Lorentz classification

Under a proper Lorentz transformation,

$$
\psi(x)\mapsto S(\Lambda)\psi(\Lambda^{-1}x),
$$

and

$$
\overline\psi(x)\mapsto \overline\psi(\Lambda^{-1}x)S(\Lambda)^{-1}.
$$

The gamma matrices satisfy

$$
S(\Lambda)^{-1}\gamma^\mu S(\Lambda)
=\Lambda^\mu_{\ \nu}\gamma^\nu.
$$

Therefore

$$
\overline\psi\psi
$$

is a Lorentz scalar, while

$$
V^\mu=\overline\psi\gamma^\mu\psi
$$

is a Lorentz vector. Similarly,

$$
A^\mu=\overline\psi\gamma^\mu\gamma^5\psi
$$

is an axial vector, and

$$
T^{\mu\nu}=\overline\psi\sigma^{\mu\nu}\psi
$$

is an antisymmetric tensor.

The word **axial** means that the object transforms like a vector under proper Lorentz transformations but picks up the opposite parity behavior under spatial reflection. The word **pseudo** in pseudoscalar means the same thing for a scalar-like object: it is invariant under proper Lorentz transformations, but changes sign under parity.

## Parity behavior

Let parity act as

$$
(t,\mathbf x)\mapsto(t,-\mathbf x).
$$

Ignoring intrinsic phases, the Dirac field transforms as

$$
\psi(t,\mathbf x)\mapsto\gamma^0\psi(t,-\mathbf x).
$$

Then the scalar is even:

$$
\overline\psi\psi(t,\mathbf x)
\mapsto
\overline\psi\psi(t,-\mathbf x).
$$

The pseudoscalar is odd:

$$
i\overline\psi\gamma^5\psi(t,\mathbf x)
\mapsto
-i\overline\psi\gamma^5\psi(t,-\mathbf x).
$$

The vector transforms as an ordinary vector:

$$
V^0(t,\mathbf x)\mapsto V^0(t,-\mathbf x),
\qquad
V^i(t,\mathbf x)\mapsto -V^i(t,-\mathbf x).
$$

The axial vector transforms oppositely:

$$
A^0(t,\mathbf x)\mapsto -A^0(t,-\mathbf x),
\qquad
A^i(t,\mathbf x)\mapsto A^i(t,-\mathbf x).
$$

For the tensor,

$$
T^{0i}\mapsto -T^{0i},
\qquad
T^{ij}\mapsto T^{ij},
$$

with the arguments evaluated at $(t,-\mathbf x)$. This is the same split as electric-like and magnetic-like components of an antisymmetric tensor.

## Charge conjugation behavior

For one Dirac field and standard phases, the charge-conjugation signs are

$$
C^{-1}(\overline\psi\psi)C=+\overline\psi\psi,
$$

$$
C^{-1}(i\overline\psi\gamma^5\psi)C=+i\overline\psi\gamma^5\psi,
$$

$$
C^{-1}(\overline\psi\gamma^\mu\psi)C=-\overline\psi\gamma^\mu\psi,
$$

$$
C^{-1}(\overline\psi\gamma^\mu\gamma^5\psi)C=+\overline\psi\gamma^\mu\gamma^5\psi,
$$

and

$$
C^{-1}(\overline\psi\sigma^{\mu\nu}\psi)C=-\overline\psi\sigma^{\mu\nu}\psi.
$$

These signs explain common couplings. The electromagnetic current

$$
j^\mu=q\overline\psi\gamma^\mu\psi
$$

is charge-conjugation odd, matching the fact that charge changes sign under $C$. A neutral pseudoscalar can couple to

$$
\overline\psi i\gamma^5\psi
$$

without being charge-conjugation odd.

With several fermion species, the full operator may be

$$
\overline\psi_i\Gamma M_{ij}\psi_j,
$$

and the transformation also acts on the flavor or gauge matrix $M$. The simple table gives the spinor part, not the whole model.

## Chirality structure

The chiral projectors are

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2}.
$$

Define

$$
\psi_L=P_L\psi,
\qquad
\psi_R=P_R\psi.
$$

Because the Dirac adjoint flips the projector,

$$
\overline\psi_L=\overline\psi P_R,
\qquad
\overline\psi_R=\overline\psi P_L.
$$

The scalar bilinear couples left and right chiralities:

$$
\overline\psi\psi
=\overline\psi_L\psi_R+\overline\psi_R\psi_L.
$$

The pseudoscalar also couples left and right:

$$
i\overline\psi\gamma^5\psi
=i(\overline\psi_L\psi_R-\overline\psi_R\psi_L).
$$

The vector and axial-vector bilinears preserve chirality:

$$
\overline\psi\gamma^\mu\psi
=\overline\psi_L\gamma^\mu\psi_L
+\overline\psi_R\gamma^\mu\psi_R,
$$

and

$$
\overline\psi\gamma^\mu\gamma^5\psi
=-\overline\psi_L\gamma^\mu\psi_L
+\overline\psi_R\gamma^\mu\psi_R.
$$

The tensor bilinear flips chirality:

$$
\overline\psi\sigma^{\mu\nu}\psi
=\overline\psi_L\sigma^{\mu\nu}\psi_R
+\overline\psi_R\sigma^{\mu\nu}\psi_L.
$$

This is often the fastest way to see which interactions are compatible with chiral symmetries. Scalar mass terms and tensor dipole terms mix left and right; vector gauge interactions preserve chirality before symmetry breaking.

## Two-component forms

For a left-handed Weyl field $\chi$, the basic Lorentz vector is

$$
\chi^\dagger\bar\sigma^\mu\chi.
$$

For two left-handed Weyl fields $\chi$ and $\xi$, the Lorentz scalar is

$$
\xi\chi=\xi^\alpha\chi_\alpha.
$$

A Dirac mass term is exactly this scalar plus its Hermitian conjugate:

$$
-m(\xi\chi+\chi^\dagger\xi^\dagger).
$$

A Majorana mass term uses the same invariant contraction with the same Weyl field:

$$
-\frac12(m\chi\chi+m^*\chi^\dagger\chi^\dagger).
$$

This is why two-component notation is often cleaner in chiral theories. The Lorentz contractions and gauge-representation constraints are visible immediately.

## Majorana bilinears

For a single Majorana field $\Psi_M=\Psi_M^c$, some Dirac bilinears vanish identically. With standard conventions and equal fields,

$$
\overline\Psi_M\gamma^\mu\Psi_M=0,
$$

and

$$
\overline\Psi_M\sigma^{\mu\nu}\Psi_M=0.
$$

The scalar, pseudoscalar, and axial-vector bilinears can be nonzero:

$$
\overline\Psi_M\Psi_M,
\qquad
 i\overline\Psi_M\gamma^5\Psi_M,
\qquad
\overline\Psi_M\gamma^\mu\gamma^5\Psi_M.
$$

The intuitive reason is charge conjugation: a Majorana field is self-conjugate, so a bilinear that is odd under charge conjugation cannot survive when built from one identical Majorana field. There are sign subtleties for anticommuting fields, and with two different Majorana species the corresponding mixed bilinears need not vanish.

## Currents and interactions

### Scalar Yukawa coupling

A real scalar $\phi$ can couple through

$$
\mathcal L_\text{Yukawa}=-y\phi\overline\psi\psi.
$$

If $\phi$ is parity even and $y$ is real, this term is parity even.

### Pseudoscalar Yukawa coupling

A pseudoscalar $a$ can couple through

$$
\mathcal L=-ig a\overline\psi\gamma^5\psi.
$$

Equivalently, using the Hermitian pseudoscalar bilinear,

$$
\mathcal L=-g a\,i\overline\psi\gamma^5\psi.
$$

This form is common for pion-like or axion-like fields.

### Vector gauge coupling

A vector gauge field couples to the vector current:

$$
\mathcal L_\text{int}=-qA_\mu\overline\psi\gamma^\mu\psi.
$$

The current

$$
j^\mu=q\overline\psi\gamma^\mu\psi
$$

is conserved for a free Dirac field with global U(1) symmetry.

### Axial current

The axial current is

$$
j_5^\mu=\overline\psi\gamma^\mu\gamma^5\psi.
$$

Classically, for a massless Dirac field, this current is conserved. With a mass,

$$
\partial_\mu j_5^\mu=2im\overline\psi\gamma^5\psi
$$

at the classical level. Quantum mechanically, gauge interactions can add anomaly terms. That belongs in the symmetry and anomalies sections, but the bilinear itself is defined here.

### Tensor and dipole terms

Tensor bilinears appear in dipole operators such as

$$
\overline\psi\sigma^{\mu\nu}\psi F_{\mu\nu}
$$

or, with chirality made explicit,

$$
\overline\psi_L\sigma^{\mu\nu}\psi_R F_{\mu\nu}+\text{h.c.}
$$

Such terms flip chirality and typically arise as higher-dimension effective operators rather than minimal gauge couplings.

## Traces and projections

The bilinear basis is useful because it is orthogonal under traces. For example,

$$
\operatorname{tr}(\gamma^\mu\gamma^\nu)=4\eta^{\mu\nu},
$$

and

$$
\operatorname{tr}(\gamma^5)=0,
\qquad
\operatorname{tr}(\gamma^\mu)=0.
$$

A general matrix $M$ can be expanded as

$$
M=a\mathbf 1+b\gamma^5+c_\mu\gamma^\mu+d_\mu\gamma^\mu\gamma^5
+\frac12 e_{\mu\nu}\sigma^{\mu\nu},
$$

with coefficients extracted by traces. This is the algebraic reason Fierz identities exist: different pairings of spinor indices correspond to different decompositions in the same complete matrix basis.

:::caution[Fierz identities]
Fierz rearrangements are powerful but sign-sensitive. The signs depend on the ordering of fermion fields, metric signature, gamma-matrix conventions, and whether the spinors are commuting test spinors or anticommuting quantum fields. Use a checked convention sheet before doing serious Fierz algebra.
:::

## Examples

### Dirac mass

The mass term

$$
-m\overline\psi\psi
$$

is scalar and parity even. In chiral language it is

$$
-m(\overline\psi_L\psi_R+\overline\psi_R\psi_L),
$$

so it mixes left and right chiralities.

### Electromagnetic current

The QED coupling

$$
-qA_\mu\overline\psi\gamma^\mu\psi
$$

is Lorentz scalar because it contracts two vectors. Since $A_\mu$ and $\overline\psi\gamma^\mu\psi$ are both charge-conjugation odd, their product is charge-conjugation even.

### Axial coupling

A coupling of the form

$$
B_\mu\overline\psi\gamma^\mu\gamma^5\psi
$$

uses an axial-vector current. Such currents are central in weak interactions, chiral symmetries, and anomaly discussions.

## Common pitfalls

**Forgetting the factor of i in the pseudoscalar.** In the conventions used here, $i\overline\psi\gamma^5\psi$ is the Hermitian pseudoscalar.

**Calling the axial current an ordinary vector.** It transforms like a vector under proper Lorentz transformations, but differently under parity.

**Ignoring chirality.** Scalar and tensor bilinears flip chirality; vector and axial-vector bilinears preserve it. This often matters more than the table of names.

**Using Majorana bilinears as if all Dirac bilinears survive.** For a single Majorana field, the vector and tensor bilinears vanish.

**Forgetting flavor matrices.** With multiple fermions, the symmetry of $\overline\psi_i\Gamma M_{ij}\psi_j$ depends on both $\Gamma$ and $M$.

**Trusting Fierz signs from memory.** Fierz identities are convention traps. Derive them or cite the convention being used.

## Relation to other topics

- [Weyl and Majorana Fields](/foundations/free-fields/weyl-and-majorana-fields/) explains the chiral building blocks and Majorana reality condition.
- [Dirac Field](/foundations/free-fields/dirac-field/) derives the Dirac equation, spin sums, and propagator that use the same gamma-matrix algebra.
- [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/) explains why spinor fields anticommute.
- [Noether Theorem](/foundations/classical-field-theory/noether-theorem/) gives the current logic behind vector and axial currents.
- [Discrete Symmetries](/foundations/symmetry-and-spacetime/discrete-symmetries/) will treat $C$, $P$, and $T$ systematically.
- [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) will use vector and axial currents in correlation functions.
- [Yukawa Theory](/foundations/foundational-models/yukawa-theory/) will use scalar and pseudoscalar bilinears as interaction terms.
- [QED Preview](/foundations/foundational-models/qed-preview/) will use the vector current $\overline\psi\gamma^\mu\psi$.

## Research status

- **Established:** The Dirac bilinear classification, parity properties, charge-conjugation signs, and chirality structure are textbook-standard.
- **Subtle:** Fierz identities, Majorana bilinear signs, dimensional regularization with $\gamma^5$, Euclidean continuation, and anomaly calculations require extra convention care.
- **Out of scope here:** Full Fierz algebra, spinor-helicity brackets, evanescent operators, anomaly derivations, and Standard Model operator bases.

## Exercises

### Exercise 1: Count the bilinear basis

Explain why the standard bilinear basis contains sixteen independent matrices.

<details>
<summary><strong>Solution</strong></summary>

The basis contains

$$
\mathbf 1 \quad (1),
\qquad
\gamma^5 \quad (1),
$$

$$
\gamma^\mu \quad (4),
\qquad
\gamma^\mu\gamma^5 \quad (4),
$$

and

$$
\sigma^{\mu\nu}=-\sigma^{\nu\mu} \quad (6).
$$

The tensor count is

$$
\binom42=6.
$$

Thus the total count is

$$
1+1+4+4+6=16.
$$

A complex $4\times4$ matrix also has sixteen complex components, so this is the right size for a basis.

</details>

### Exercise 2: Parity of the pseudoscalar

Using $\psi(t,\mathbf x)\mapsto\gamma^0\psi(t,-\mathbf x)$, show that $i\overline\psi\gamma^5\psi$ is parity odd.

<details>
<summary><strong>Solution</strong></summary>

Under parity,

$$
\overline\psi(t,\mathbf x)\mapsto\overline\psi(t,-\mathbf x)\gamma^0.
$$

Therefore

$$
i\overline\psi\gamma^5\psi
\mapsto
i\overline\psi(t,-\mathbf x)\gamma^0\gamma^5\gamma^0\psi(t,-\mathbf x).
$$

Since $\{\gamma^5,\gamma^0\}=0$ and $(\gamma^0)^2=1$,

$$
\gamma^0\gamma^5\gamma^0=-\gamma^5.
$$

Thus

$$
i\overline\psi\gamma^5\psi(t,\mathbf x)
\mapsto
-i\overline\psi\gamma^5\psi(t,-\mathbf x),
$$

so the pseudoscalar is parity odd.

</details>

### Exercise 3: Chirality of the vector current

Show that

$$
\overline\psi\gamma^\mu\psi
=\overline\psi_L\gamma^\mu\psi_L
+\overline\psi_R\gamma^\mu\psi_R.
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\psi=\psi_L+\psi_R,
\qquad
\overline\psi=\overline\psi_L+\overline\psi_R.
$$

The cross terms are

$$
\overline\psi_L\gamma^\mu\psi_R
=\overline\psi P_R\gamma^\mu P_R\psi,
$$

and

$$
\overline\psi_R\gamma^\mu\psi_L
=\overline\psi P_L\gamma^\mu P_L\psi.
$$

Since $\{\gamma^5,\gamma^\mu\}=0$,

$$
P_R\gamma^\mu=\gamma^\mu P_L,
\qquad
P_L\gamma^\mu=\gamma^\mu P_R.
$$

Therefore

$$
P_R\gamma^\mu P_R=\gamma^\mu P_LP_R=0,
$$

and similarly

$$
P_L\gamma^\mu P_L=0.
$$

The surviving terms are

$$
\overline\psi_L\gamma^\mu\psi_L
+\overline\psi_R\gamma^\mu\psi_R.
$$

</details>

### Exercise 4: Chirality of the scalar mass term

Show that

$$
\overline\psi\psi
=\overline\psi_L\psi_R+\overline\psi_R\psi_L.
$$

<details>
<summary><strong>Solution</strong></summary>

Write

$$
\overline\psi\psi
=(\overline\psi_L+\overline\psi_R)(\psi_L+\psi_R).
$$

Since

$$
\overline\psi_L=\overline\psi P_R,
\qquad
\overline\psi_R=\overline\psi P_L,
$$

the same-chirality terms are

$$
\overline\psi_L\psi_L=\overline\psi P_RP_L\psi=0,
$$

and

$$
\overline\psi_R\psi_R=\overline\psi P_LP_R\psi=0.
$$

Thus

$$
\overline\psi\psi
=\overline\psi_L\psi_R+\overline\psi_R\psi_L.
$$

</details>

### Exercise 5: Classical divergence of the axial current

Using the free Dirac equation, show that classically

$$
\partial_\mu(\overline\psi\gamma^\mu\gamma^5\psi)=2im\overline\psi\gamma^5\psi.
$$

<details>
<summary><strong>Solution</strong></summary>

The axial current is

$$
j_5^\mu=\overline\psi\gamma^\mu\gamma^5\psi.
$$

Its divergence is

$$
\partial_\mu j_5^\mu
=(\partial_\mu\overline\psi)\gamma^\mu\gamma^5\psi
+\overline\psi\gamma^\mu\gamma^5\partial_\mu\psi.
$$

The adjoint equation gives

$$
i(\partial_\mu\overline\psi)\gamma^\mu=-m\overline\psi,
$$

so

$$
(\partial_\mu\overline\psi)\gamma^\mu\gamma^5\psi
=im\overline\psi\gamma^5\psi.
$$

The Dirac equation gives

$$
i\gamma^\mu\partial_\mu\psi=m\psi.
$$

Using $\gamma^\mu\gamma^5=-\gamma^5\gamma^\mu$,

$$
\overline\psi\gamma^\mu\gamma^5\partial_\mu\psi
=-\overline\psi\gamma^5\gamma^\mu\partial_\mu\psi
=-\overline\psi\gamma^5(-im\psi)
=im\overline\psi\gamma^5\psi.
$$

Adding the two terms gives

$$
\partial_\mu j_5^\mu=2im\overline\psi\gamma^5\psi.
$$

For $m=0$, the classical axial current is conserved. Quantum anomalies are a separate effect.

</details>

### Exercise 6: Majorana vector current

Use charge conjugation to explain why the vector current of a single Majorana field vanishes.

<details>
<summary><strong>Solution</strong></summary>

For a single Dirac field, the vector bilinear is charge-conjugation odd:

$$
C^{-1}(\overline\psi\gamma^\mu\psi)C
=-\overline\psi\gamma^\mu\psi.
$$

A Majorana field satisfies $\Psi_M^c=\Psi_M$, so charge conjugation maps the field back to itself, up to a conventional phase. Therefore a bilinear made from one identical Majorana field must be equal to its charge-conjugated version. But the vector bilinear is also equal to minus itself. Hence

$$
\overline\Psi_M\gamma^\mu\Psi_M=0.
$$

A fully explicit proof requires careful handling of anticommuting fields, but the charge-conjugation argument captures the invariant reason.

</details>

## References

### Primary references

- P. A. M. Dirac, “The Quantum Theory of the Electron,” *Proceedings of the Royal Society A* **117** (1928), for the Dirac spinor framework.
- E. Majorana, “Teoria simmetrica dell'elettrone e del positrone,” *Il Nuovo Cimento* **14** (1937), for Majorana spinors.
- T. D. Lee and C. N. Yang, “Question of Parity Conservation in Weak Interactions,” *Physical Review* **104** (1956), for the historical role of scalar, vector, tensor, axial, and pseudoscalar structures in weak interactions.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 20 for bilinear spinor products and ch. 22 for charge conjugation and Fermi fields.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §5.5, for Lorentz and discrete-symmetry classification of spinor bilinears.
- M. Srednicki, *Quantum Field Theory*, §§35–40 and §47, for spinor indices, Lagrangians, discrete symmetries, and gamma-matrix technology.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, chs. 3–4, for spinor bilinears in scattering and chiral language.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. II.1–II.4, for a compact physical treatment of Dirac spinors and bilinears.

### For a first pass

- Coleman, ch. 20.
- Peskin and Schroeder, §§3.1–3.4.
- Zee, chs. II.1–II.2.

### For mathematical precision

- Weinberg, Vol. I, §§5.4–5.7, for Lorentz-representation foundations.
- P. Deligne et al., *Quantum Fields and Strings: A Course for Mathematicians*, Vol. I, for Clifford algebras and spinor bilinears.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for structural results involving spinors, locality, and discrete symmetries.

## Version history

- **2026-05-22:** Initial qft.org bilinear dictionary page, including the sixteen-matrix basis, Lorentz classification, parity and charge conjugation, chirality structure, Majorana bilinear constraints, interaction examples, pitfalls, exercises, and a TikZ-generated summary figure.
