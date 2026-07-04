---
title: "Level and Normalization"
description: "How to compare current-algebra levels, trace conventions, invariant forms, Dynkin indices, subgroup embeddings, and Sugawara normalizations across WZW and affine CFT references."
sidebar:
  label: "Level and Normalization"
  order: 3
level: Graduate
status: "Polished draft"
source: "Di Francesco, Mathieu, and Senechal ch. 14; Kac; Ginsparg lectures; Witten 1984; standard WZW normalization conventions."
topics:
  - level
  - current normalization
  - Dynkin index
  - Sugawara construction
  - WZW models
canonicalTopics:
  - affine-level-normalization
  - current-two-point-normalization
  - dynkin-index
researchStatus:
  established:
    - "The level of an affine current algebra is the coefficient of its central term, but its numerical value must be read together with a specified invariant bilinear form and generator normalization."
  active:
    - "Normalization issues remain important in embeddings, anomalies, boundary CFT, condensed-matter applications, and comparisons between WZW, Chern–Simons, and lattice conventions."
---

## Summary

The **level** $k$ of an affine current algebra is the coefficient of the current-current central term. In the convention used in this chapter,

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w}.
$$

Equivalently,

$$
[J^a_m,J^b_n]
=i f^{ab}{}_cJ^c_{m+n}
+k m\kappa^{ab}\delta_{m+n,0}.
$$

This looks simple, but it hides a convention trap: the number called $k$ is meaningful only after fixing the invariant form $\kappa^{ab}$ and the normalization of the finite Lie-algebra generators. Rescaling the generators can move factors between $k$, $\kappa^{ab}$, and the structure constants.

This page fixes the normalization dictionary used in the Current Algebras and WZW Models chapter. It explains the current two-point function, trace conventions, Dynkin index, embedding index, abelian levels, integrable-representation condition, and the Sugawara central charge.

## Prerequisites

Read [Affine Lie Algebras](/cft-bootstrap/current-algebras-wzw/affine-lie-algebras/) and [Currents and Kac–Moody OPEs](/cft-bootstrap/current-algebras-wzw/currents-and-kac-moody-opes/) first.

You should know the finite Lie-algebra notation

$$
[T^a,T^b]=i f^{ab}{}_cT^c,
$$

and the idea that an invariant bilinear form can be written as a trace in a chosen representation:

$$
\operatorname{Tr}_R(T^aT^b)=I_R\kappa^{ab}.
$$

## Core idea

The same physical current algebra can be written in several normalization systems. A source might normalize generators by

$$
\operatorname{Tr}_{\rm fund}(T^aT^b)=\frac12\delta^{ab},
$$

another might use

$$
\operatorname{Tr}_{\rm fund}(T^aT^b)=\delta^{ab},
$$

and a third might use anti-Hermitian generators with no explicit $i$ in the commutator. If you compare only the symbol $k$, you can be off by a factor of two or by a group-theoretic index.

The robust statement is:

$$
\text{level} = \text{coefficient of the double pole once the current metric is fixed}.
$$

Everything else is translation.

## Setup and conventions

For a simple compact Lie algebra $\mathfrak g$, we choose a positive invariant form $\kappa^{ab}$ and Hermitian generators satisfying

$$
[T^a,T^b]=i f^{ab}{}_cT^c.
$$

The current OPE is

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w}.
$$

When we use root and weight formulas, we use the standard long-root convention

$$
(\theta,\theta)=2,
$$

where $\theta$ is the highest root. In that convention the dual Coxeter number is $h^\vee$, and the Sugawara central charge for a compact simple WZW model is

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee}.
$$

The current-primary OPE for a primary in representation $R$ is

$$
J^a(z)\Phi_R(w,\bar w)
\sim
\frac{T_R^a\Phi_R(w,\bar w)}{z-w}.
$$

This fixes the relative normalization between the current and the representation matrices.

## Current two-point normalization

The level appears directly in the current two-point function:

$$
\langle J^a(z)J^b(0)\rangle
=\frac{k\kappa^{ab}}{z^2}.
$$

Thus, if a source writes

$$
\langle J^a(z)J^b(0)\rangle
=\frac{K^{ab}}{z^2},
$$

then the level matrix is $K^{ab}$. For a simple algebra, invariance forces

$$
K^{ab}=k\kappa^{ab}.
$$

For a product algebra, each simple factor has its own level:

$$
\widehat{\mathfrak g}_{1,k_1}\oplus\widehat{\mathfrak g}_{2,k_2}\oplus\cdots .
$$

For abelian currents, the level can be a matrix:

$$
J^I(z)J^J(w)\sim\frac{K^{IJ}}{(z-w)^2}.
$$

In compact unitary theories, this matrix is positive definite on physical currents and is often tied to an integral charge lattice.

## Rescaling generators

Suppose one rescales finite generators by a constant:

$$
T^a\mapsto \alpha T^a.
$$

Then the structure constants and invariant form change unless one simultaneously changes the basis labels. This is why the level should not be compared without specifying the generator metric.

A safer method is to compare basis-independent quantities:

| Quantity | Safer comparison |
|---|---|
| Current two-point function | Compare $k\kappa^{ab}$ as a bilinear form. |
| Sugawara central charge | Compare $c=k\dim\mathfrak g/(k+h^\vee)$ after fixing long roots. |
| Integrable weights | Compare $(\lambda,\theta)\le k$ in long-root normalization. |
| Subalgebra levels | Compare embedding indices. |
| Free-fermion levels | Compare Dynkin indices of the fermion representation. |

In a simple compact WZW model, the long-root convention removes most ambiguity. In general current-algebra applications, especially in condensed matter or anomaly matching, one must still track the current normalization explicitly.

## Trace conventions and Dynkin index

Let $R$ be a representation of $\mathfrak g$. Define the Dynkin index $I_R$ by

$$
\operatorname{Tr}_R(T^aT^b)=I_R\kappa^{ab}.
$$

The value of $I_R$ depends on the normalization of $\kappa^{ab}$. In the common $SU(N)$ convention with Hermitian generators in the fundamental representation normalized by

$$
\operatorname{Tr}_{\rm fund}(T^aT^b)=\frac12\delta^{ab},
$$

one has

$$
I_{\rm fund}=\frac12,
\qquad
I_{\rm adj}=h^\vee=N.
$$

Some CFT conventions instead normalize the fundamental index to one. Then all quoted levels and indices are twice the values in the $1/2$ convention. Neither convention is wrong; the mistake is mixing them.

For a set of free chiral fermions transforming in representation $R$, the current

$$
J^a(z)=:\psi^\dagger T_R^a\psi:(z)
$$

has current two-point coefficient proportional to $I_R$. Thus free fermions generate an affine current algebra with level set by the Dynkin index of the representation, in the chosen convention.

## Subalgebras and embedding index

Suppose a simple algebra $\mathfrak h$ is embedded in a simple algebra $\mathfrak g$:

$$
\mathfrak h\subset\mathfrak g.
$$

A current algebra $\widehat{\mathfrak g}_k$ induces a current algebra for $\mathfrak h$, but the level is not always the same. It is multiplied by the embedding index $x_e$:

$$
k_{\mathfrak h}=x_e k_{\mathfrak g}.
$$

The embedding index compares the invariant form inherited from $\mathfrak g$ with the standard invariant form on $\mathfrak h$.

This matters in cosets. The GKO coset

$$
\frac{\widehat{\mathfrak g}_k}{\widehat{\mathfrak h}_{k_{\mathfrak h}}}
$$

has central charge

$$
c_{\rm coset}=c(\mathfrak g,k)-c(\mathfrak h,k_{\mathfrak h}).
$$

Using $k_{\mathfrak h}=k$ when the embedding index is not one gives the wrong answer.

## Integrable highest weights

For a compact simple WZW model at positive integer level $k$, the allowed affine primary representations are the integrable highest-weight representations. In long-root normalization, the condition is

$$
(\lambda,\theta)\le k,
$$

where $\lambda$ is the finite highest weight and $\theta$ is the highest root.

For $SU(2)_k$, this becomes

$$
2j\le k,
$$

so the allowed spins are

$$
j=0,\frac12,1,\ldots,\frac{k}{2}.
$$

For $SU(N)_k$, a highest weight with Dynkin labels

$$
(\lambda_1,\ldots,\lambda_{N-1})
$$

is integrable when

$$
\sum_{i=1}^{N-1}\lambda_i\le k.
$$

This finite list is what makes compact WZW models rational CFTs.

## Sugawara normalization

For a simple compact algebra in the standard long-root convention, the Sugawara stress tensor is

$$
T(z)=\frac{1}{2(k+h^\vee)}\kappa_{ab}:J^aJ^b:(z).
$$

It gives

$$
T(z)J^a(w)
\sim
\frac{J^a(w)}{(z-w)^2}
+\frac{\partial J^a(w)}{z-w},
$$

so the currents have weight one.

The central charge is

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee}.
$$

An affine primary of finite highest weight $\lambda$ has conformal weight

$$
h_\lambda=\frac{C_2(\lambda)}{2(k+h^\vee)},
$$

if $C_2(\lambda)$ is defined by

$$
T^aT^b\kappa_{ab}=C_2(\lambda)\mathbf 1.
$$

With the common long-root convention, the same formula is often written as

$$
h_\lambda=\frac{(\lambda,\lambda+2\rho)}{2(k+h^\vee)},
$$

where $\rho$ is the Weyl vector.

For $SU(2)_k$, this gives

$$
h_j=\frac{j(j+1)}{k+2}.
$$

## WZW action normalization

For a compact group $G$, the WZW action is often written schematically as

$$
S_{\rm WZW}[g]
=\frac{k}{8\pi}\int_\Sigma \operatorname{Tr}(g^{-1}\partial_\mu g\,g^{-1}\partial^\mu g)
+\frac{k}{12\pi}\int_B \operatorname{Tr}(g^{-1}dg)^3,
$$

with $\partial B=\Sigma$. The displayed coefficients depend on the trace convention, but the quantization statement is invariant: the path-integral phase must be independent of the choice of extension $B$.

For compact simply connected simple $G$, this implies

$$
k\in\mathbb Z.
$$

In the quantum CFT, unitarity requires

$$
k\in\mathbb Z_{\ge0}.
$$

The same integer is the affine level in the current OPE when the action and current are normalized consistently.

## Free-fermion example

Consider left-moving complex fermions $\psi^i(z)$ with

$$
\psi^i(z)\psi_j^\dagger(w)\sim\frac{\delta^i{}_j}{z-w}.
$$

The currents

$$
J^a(z)=:\psi^\dagger_i(T^a)^i{}_j\psi^j:(z)
$$

have OPE

$$
J^a(z)J^b(w)
\sim
\frac{\operatorname{Tr}_R(T^aT^b)}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w}.
$$

Thus the level is the Dynkin index of the fermion representation in the chosen normalization.

For $N$ complex fermions in the fundamental of $SU(N)$, the standard physics convention

$$
\operatorname{Tr}_{\rm fund}(T^aT^b)=\frac12\delta^{ab}
$$

gives a double-pole coefficient $\delta^{ab}/2$. If one wants the affine algebra called $SU(N)_1$, one usually chooses the current metric so that this coefficient is $k\kappa^{ab}$ with $k=1$. Equivalently, one chooses $\kappa^{ab}=\operatorname{Tr}_{\rm fund}(T^aT^b)$ for the defining representation.

This is the kind of convention translation that causes many apparent factor-of-two disagreements.

## Abelian levels and charge normalization

For a $U(1)$ current,

$$
J(z)J(w)\sim\frac{k}{(z-w)^2}.
$$

If a charged field has

$$
J(z)\Phi_q(w)\sim\frac{q\Phi_q(w)}{z-w},
$$

then rescaling the current

$$
J\mapsto \alpha J
$$

changes both

$$
k\mapsto\alpha^2k,
\qquad
q\mapsto\alpha q.
$$

The invariant information is the charge lattice together with the current two-point form. In compact boson CFTs, this information is encoded in the momentum-winding lattice. In anomaly language, the abelian level is the coefficient of the current two-point function or, equivalently, the two-dimensional anomaly coefficient for the chiral symmetry.

Therefore, for abelian currents, always state the charge normalization. Saying “$U(1)$ level $k$” without saying what charge is called $1$ is incomplete.

## Common reference conventions

Here is a practical translation table.

| Convention choice | Effect |
|---|---|
| Hermitian generators | Commutator has $i f^{ab}{}_c$; current OPE often has $i f^{ab}{}_cJ^c/(z-w)$. |
| Anti-Hermitian generators | The $i$ is absorbed into the structure constants or generators. |
| $\operatorname{Tr}_{\rm fund}(T^aT^b)=\frac12\delta^{ab}$ | Common particle-physics convention for $SU(N)$. |
| $\operatorname{Tr}_{\rm fund}(T^aT^b)=\delta^{ab}$ | Doubles many Dynkin indices relative to the previous convention. |
| Long roots have length squared $2$ | Standard for affine representation theory and WZW formulas. |
| Current metric chosen as fundamental trace | Often makes free fundamental fermions realize level one. |

The safest workflow is:

1. Identify the finite-generator normalization.
2. Identify the current two-point coefficient.
3. Express the coefficient as $k\kappa^{ab}$.
4. Use the same $\kappa^{ab}$ in Sugawara and representation formulas.

## Common pitfalls

**Do not compare bare symbols $k$ across books.** Compare the current two-point function and generator metric.

**Do not confuse Dynkin index with quadratic Casimir.** The index $I_R$ is defined by a trace over $R$; the Casimir $C_2(R)$ is the eigenvalue of $T^aT^b\kappa_{ab}$ on $R$.

**Do not forget subgroup embedding indices.** A subalgebra current inherited from $\widehat{\mathfrak g}_k$ can have level $x_e k$, not $k$.

**Do not use the Sugawara formula with mismatched conventions.** The formula $c=k\dim\mathfrak g/(k+h^\vee)$ assumes the standard long-root normalization.

**Do not call every positive real number a compact WZW level.** Compact simply connected WZW models require quantized integer level.

**Do not specify an abelian level without charge normalization.** For $U(1)$, rescaling the current rescales both charges and the double-pole coefficient.

## Relations to other pages

This page supports every formula-heavy page in the Current Algebras and WZW Models chapter. [Currents and Kac–Moody OPEs](/cft-bootstrap/current-algebras-wzw/currents-and-kac-moody-opes/) defines the current OPE whose double pole is called the level. [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/) uses the same normalization to compute $T(z)$, $c$, and $h_\lambda$.

[Integrable Highest Weights](/cft-bootstrap/current-algebras-wzw/integrable-highest-weights/) uses the condition $(\lambda,\theta)\le k$. [Cosets and GKO Construction](/cft-bootstrap/current-algebras-wzw/cosets-gko-construction/) uses embedding indices to subtract the correct denominator central charge. [WZW Fusion Rules](/cft-bootstrap/current-algebras-wzw/wzw-fusion-rules/) uses the same level to truncate fusion.

The page also connects to [Compact Boson](/cft-bootstrap/two-dimensional-cft/compact-boson/) for abelian current lattices and to [Modular Invariance](/cft-bootstrap/minimal-models-rational-cft/modular-invariance/) for the modular meaning of rational WZW spectra.

## Research status

The normalization and level dictionary for affine Lie algebras and compact WZW models is established. Most errors in this topic are not research-level uncertainties; they are convention mismatches.

Active applications make the bookkeeping more important rather than less: subgroup embeddings in cosets, boundary current algebra, anomaly matching, non-invertible symmetries, condensed-matter edge theories, Chern–Simons/WZW relations, and nonsemisimple current algebras all require careful normalization.

## Exercises

### Exercise 1

Suppose a current is rescaled as $J^a\mapsto\alpha J^a$ while the OPE is written in the abelian form

$$
J(z)J(w)\sim\frac{k}{(z-w)^2}.
$$

How does $k$ change?

<details><summary><strong>Solution</strong></summary>

The rescaled current has

$$
J'(z)J'(w)=\alpha^2J(z)J(w)
\sim\frac{\alpha^2 k}{(z-w)^2}.
$$

Therefore

$$
k'=\alpha^2k.
$$

This is why abelian levels must be quoted together with charge normalization.

</details>

### Exercise 2

For $SU(2)_k$, list the allowed integrable spins at $k=3$.

<details><summary><strong>Solution</strong></summary>

The integrability condition is

$$
2j\le k.
$$

At $k=3$,

$$
j=0,\frac12,1,\frac32.
$$

</details>

### Exercise 3

Use the Sugawara formula to compute the central charge of $SU(2)_3$.

<details><summary><strong>Solution</strong></summary>

For $SU(2)$,

$$
\dim\mathfrak{su}(2)=3,
\qquad
h^\vee=2.
$$

Thus

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee}
=\frac{3\cdot3}{3+2}
=\frac95.
$$

</details>

### Exercise 4

Explain why the level of a subalgebra can differ from the level of the larger algebra.

<details><summary><strong>Solution</strong></summary>

The level measures the current two-point function relative to a chosen invariant form. When $\mathfrak h\subset\mathfrak g$, the invariant form on $\mathfrak g$ restricts to an invariant form on $\mathfrak h$, but it need not equal the standard form used to normalize $\mathfrak h$.

The ratio is the embedding index $x_e$. Therefore a $\widehat{\mathfrak g}_k$ current algebra induces

$$
k_{\mathfrak h}=x_e k_{\mathfrak g}.
$$

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- V. Kac, *Infinite-Dimensional Lie Algebras*, Cambridge University Press.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- E. Witten, “Non-Abelian bosonization in two dimensions,” *Communications in Mathematical Physics* **92** (1984).
- P. Goddard, A. Kent, and D. Olive, “Virasoro algebras and coset space models,” *Physics Letters B* **152** (1985).

## Version history

- 2026-06-30: First polished draft. Added current two-point normalization, trace and Dynkin-index dictionary, embedding index, integrability condition, Sugawara conventions, abelian levels, exercises, and references.
