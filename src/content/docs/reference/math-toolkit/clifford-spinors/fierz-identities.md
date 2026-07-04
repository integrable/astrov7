---
title: "Fierz Identities"
description: "Derives and explains four-dimensional Fierz identities as gamma-matrix completeness relations, including scalar, vector, tensor, chiral, and Grassmann-sign conventions."
sidebar:
  label: "Fierz Identities"
  order: 7
level: Graduate
status: "Polished draft"
source: "Standard spinor and QFT references, including Weinberg, Srednicki, Schwartz, Zee, Coleman, and common two-component spinor conventions."
topics:
  - Fierz identities
  - gamma matrix completeness
  - four fermion operators
  - chiral projectors
  - Grassmann signs
  - operator bases
canonicalTopics:
  - fierz-identities
  - gamma-matrix-completeness
  - four-fermion-operators
  - chiral-fierz-identities
  - grassmann-signs
  - fermion-operator-bases
researchStatus:
  established:
    - "Four-dimensional Fierz identities are algebraic consequences of the completeness of the gamma-matrix basis, with signs fixed by the chosen spinor ordering and Grassmann convention."
  active:
    - "Fierz rearrangements remain important in EFT operator bases, automated symbolic manipulation, supersymmetry, lattice operator matching, Majorana systems, and dimensionally regulated chiral calculations."
---

## Summary

Fierz identities are rearrangement formulas for products of spinor bilinears. A typical product has one pairing of spinors,

$$
(\bar\psi_1\Gamma\psi_2)(\bar\psi_3\Delta\psi_4),
$$

and a Fierz identity rewrites it in another pairing,

$$
(\bar\psi_1\Gamma'\psi_4)(\bar\psi_3\Delta'\psi_2).
$$

The physics motivation is everywhere: four-fermion effective operators, weak interactions, current-current amplitudes, Majorana simplifications, supersymmetry closures, color and spin rearrangements, and lattice matching calculations all require deciding whether two apparently different fermion operators are actually independent.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Flow diagram showing a product of bilinears paired as (12)(34), insertion of the gamma-matrix completeness relation, rearrangement to the pairing (14)(32), and the Grassmann-sign warning.](/figures/math-toolkit/fierz-rearrangement-flow.svg)

<figcaption>

A Fierz identity is not magic. It is a completeness relation for the $16$ Dirac matrices inserted between four spinor slots. The only drama is bookkeeping: which spinors are paired, whether the spinors are commuting wavefunctions or anticommuting fields, and which gamma-matrix convention is being used.

</figcaption>
</figure>

The core four-dimensional completeness identity is

$$
\delta_{ij}\delta_{kl}
=
\frac14\delta_{il}\delta_{kj}
+\frac14(\gamma^5)_{il}(\gamma^5)_{kj}
+\frac14(\gamma^\mu)_{il}(\gamma_\mu)_{kj}
-\frac14(\gamma^\mu\gamma^5)_{il}(\gamma_\mu\gamma^5)_{kj}
+\frac18(\sigma^{\mu\nu})_{il}(\sigma_{\mu\nu})_{kj}.
$$

This one line is the scalar Fierz identity in matrix form. The signs and factors follow from trace orthogonality of the gamma-matrix basis.

## Prerequisites

Read [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/) and [Spinor Bilinears](/math-toolkit/clifford-spinors/spinor-bilinears/) first. This page uses the mostly-minus four-dimensional conventions

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}\mathbf 1,
\qquad
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
$$

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3,
\qquad
\sigma^{\mu\nu}=\frac{i}{2}[\gamma^\mu,\gamma^\nu].
$$

The Fierz tables below use the algebraic pseudoscalar insertion $\gamma^5$. If you want Hermitian pseudoscalar operators in the conventions of the previous page, replace $\bar\psi\gamma^5\psi$ by $-i\bar\psi i\gamma^5\psi$ at the end. The table is a gamma-algebra table first, and a Hermitian-operator table second.

## Core idea

The Dirac matrices form a complete basis for $4\times4$ matrices:

$$
\mathbf 1,
\qquad
\gamma^5,
\qquad
\gamma^\mu,
\qquad
\gamma^\mu\gamma^5,
\qquad
\sigma^{\mu\nu}.
$$

Because this basis is complete, any matrix with one pair of spinor indices can be expanded in it. A Fierz identity applies this completeness not to one matrix, but to the identity map on a tensor product of two spinor spaces.

A product such as

$$
(\bar\psi_1\psi_2)(\bar\psi_3\psi_4)
$$

has spinor-index structure

$$
(\bar\psi_1)_i(\psi_2)_j(\bar\psi_3)_k(\psi_4)_l\,\delta_{ij}\delta_{kl}.
$$

The identity $\delta_{ij}\delta_{kl}$ contracts $(1,2)$ and $(3,4)$. The Fierz completeness relation rewrites that contraction in terms of $\delta_{il}\delta_{kj}$ and gamma-matrix analogues, which contract $(1,4)$ and $(3,2)$.

That is all a Fierz identity does:

$$
(12)(34)\quad\longrightarrow\quad(14)(32).
$$

The danger is that this arrow is an algebraic arrow, not a vibes arrow. The coefficients are fixed, and anticommuting spinor fields may add an overall minus sign when you move fields past one another.

## Matrix completeness

A convenient trace-orthogonal basis is

$$
\Gamma_A\in
\left\{
\mathbf 1,\gamma^5,\gamma^\mu,\gamma^\mu\gamma^5,\sigma^{\mu\nu}
\right\}.
$$

The trace inner products are schematic but memorable:

$$
\operatorname{tr}(\mathbf 1\mathbf 1)=4,
\qquad
\operatorname{tr}(\gamma^5\gamma^5)=4,
$$

$$
\operatorname{tr}(\gamma^\mu\gamma^\nu)=4\eta^{\mu\nu},
$$

$$
\operatorname{tr}(\gamma^\mu\gamma^5\gamma^\nu\gamma^5)=-4\eta^{\mu\nu},
$$

and

$$
\operatorname{tr}(\sigma^{\mu\nu}\sigma^{\rho\sigma})
=4(\eta^{\mu\rho}\eta^{\nu\sigma}-\eta^{\mu\sigma}\eta^{\nu\rho}).
$$

The axial minus sign and tensor normalization are why the completeness relation is

$$
\delta_{ij}\delta_{kl}
=
\frac14\delta_{il}\delta_{kj}
+\frac14(\gamma^5)_{il}(\gamma^5)_{kj}
+\frac14(\gamma^\mu)_{il}(\gamma_\mu)_{kj}
-\frac14(\gamma^\mu\gamma^5)_{il}(\gamma_\mu\gamma^5)_{kj}
+\frac18(\sigma^{\mu\nu})_{il}(\sigma_{\mu\nu})_{kj}.
$$

A useful consistency check is to count components. The scalar and pseudoscalar pieces contribute $1+1$, the vector and axial pieces contribute $4+4$, and the tensor piece contributes $6$. Altogether,

$$
1+1+4+4+6=16,
$$

as required for all $4\times4$ matrices.

## Scalar Fierz identity

For commuting spinors, the completeness relation gives

$$
(\bar\psi_1\psi_2)(\bar\psi_3\psi_4)
=
\frac14(\bar\psi_1\psi_4)(\bar\psi_3\psi_2)
+\frac14(\bar\psi_1\gamma^5\psi_4)(\bar\psi_3\gamma^5\psi_2)
$$

$$
+\frac14(\bar\psi_1\gamma^\mu\psi_4)(\bar\psi_3\gamma_\mu\psi_2)
-\frac14(\bar\psi_1\gamma^\mu\gamma^5\psi_4)(\bar\psi_3\gamma_\mu\gamma^5\psi_2)
$$

$$
+\frac18(\bar\psi_1\sigma^{\mu\nu}\psi_4)(\bar\psi_3\sigma_{\mu\nu}\psi_2).
$$

For anticommuting spinor fields, the same rearrangement of the field order carries an overall minus sign:

$$
(\bar\psi_1\psi_2)(\bar\psi_3\psi_4)
=
-\frac14(\bar\psi_1\psi_4)(\bar\psi_3\psi_2)
-\frac14(\bar\psi_1\gamma^5\psi_4)(\bar\psi_3\gamma^5\psi_2)
$$

$$
-\frac14(\bar\psi_1\gamma^\mu\psi_4)(\bar\psi_3\gamma_\mu\psi_2)
+\frac14(\bar\psi_1\gamma^\mu\gamma^5\psi_4)(\bar\psi_3\gamma_\mu\gamma^5\psi_2)
$$

$$
-\frac18(\bar\psi_1\sigma^{\mu\nu}\psi_4)(\bar\psi_3\sigma_{\mu\nu}\psi_2).
$$

This sign is the thing most likely to ambush a correct-looking calculation. A matrix identity has no Grassmann sign. A field identity does, if obtaining the new pairing requires moving odd fields through one another.

A practical rule:

- Use the plus-sign matrix table for commuting external spinor wavefunctions.
- Use an extra overall minus sign when rearranging anticommuting fields from $(12)(34)$ to $(14)(32)$.
- If a source has normal-ordered bilinears or a different spinor ordering convention, compare the ordering before comparing the coefficients.

Yes, this is annoying. It is also cheaper than discovering the error after a four-fermion basis has been published.

## The five-channel Fierz table

Define the five contracted bilinear products

$$
B_S=(\bar\psi_1\psi_2)(\bar\psi_3\psi_4),
$$

$$
B_P=(\bar\psi_1\gamma^5\psi_2)(\bar\psi_3\gamma^5\psi_4),
$$

$$
B_V=(\bar\psi_1\gamma^\mu\psi_2)(\bar\psi_3\gamma_\mu\psi_4),
$$

$$
B_A=(\bar\psi_1\gamma^\mu\gamma^5\psi_2)(\bar\psi_3\gamma_\mu\gamma^5\psi_4),
$$

and

$$
B_T=(\bar\psi_1\sigma^{\mu\nu}\psi_2)(\bar\psi_3\sigma_{\mu\nu}\psi_4).
$$

Let $\widetilde B_S,\widetilde B_P,\widetilde B_V,\widetilde B_A,\widetilde B_T$ denote the same expressions with the pairing changed from $(12)(34)$ to $(14)(32)$:

$$
\widetilde B_S=(\bar\psi_1\psi_4)(\bar\psi_3\psi_2),
$$

and similarly for the other gamma insertions.

For commuting spinors, the Fierz table in the conventions of this page is

$$
\begin{pmatrix}
B_S\\
B_P\\
B_V\\
B_A\\
B_T
\end{pmatrix}
=
\begin{pmatrix}
\frac14&\frac14&\frac14&-\frac14&\frac18\\
\frac14&\frac14&-\frac14&\frac14&\frac18\\
1&-1&-\frac12&-\frac12&0\\
-1&1&-\frac12&-\frac12&0\\
3&3&0&0&-\frac12
\end{pmatrix}
\begin{pmatrix}
\widetilde B_S\\
\widetilde B_P\\
\widetilde B_V\\
\widetilde B_A\\
\widetilde B_T
\end{pmatrix}.
$$

For anticommuting fields with the same rearrangement of field order, multiply the right-hand side by $-1$.

This table is often the fastest way to rearrange a four-fermion operator. It is also the fastest way to make a sign error. Before using it, check three things:

1. Is the pseudoscalar basis $\gamma^5$ or $i\gamma^5$?
2. Is $\sigma^{\mu\nu}$ defined as $\frac{i}{2}[\gamma^\mu,\gamma^\nu]$?
3. Are the spinors commuting external wavefunctions or anticommuting fields?

The table above assumes $\gamma^5$, $\sigma^{\mu\nu}=\frac{i}{2}[\gamma^\mu,\gamma^\nu]$, and commuting spinors before the optional Grassmann sign.

## Chiral Fierz identities

Chiral projectors simplify many identities. With

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2},
$$

one useful matrix identity is

$$
(P_L)_{ij}(P_R)_{kl}
=
\frac12(\gamma^\mu P_R)_{il}(\gamma_\mu P_L)_{kj}.
$$

For anticommuting fields this gives

$$
(\bar\psi_1P_L\psi_2)(\bar\psi_3P_R\psi_4)
=
-\frac12(\bar\psi_1\gamma^\mu P_R\psi_4)(\bar\psi_3\gamma_\mu P_L\psi_2),
$$

where the minus sign comes from rearranging the fields.

Another useful matrix identity is

$$
(\gamma^\mu P_L)_{ij}(\gamma_\mu P_L)_{kl}
=
-(\gamma^\mu P_L)_{il}(\gamma_\mu P_L)_{kj}.
$$

For anticommuting fields the extra Grassmann sign cancels this matrix minus, giving the clean current-current rearrangement

$$
(\bar\psi_1\gamma^\mu P_L\psi_2)(\bar\psi_3\gamma_\mu P_L\psi_4)
=
(\bar\psi_1\gamma^\mu P_L\psi_4)(\bar\psi_3\gamma_\mu P_L\psi_2).
$$

The same identity holds with $L$ replaced by $R$.

These chiral formulas are particularly useful for weak-interaction operators, Standard Model effective field theory, and two-component spinor calculations. They are also a good reminder that the full five-channel table is sometimes overkill. If all spinors are chiral, most channels are absent before you begin.

## Two-component viewpoint

In two-component notation the same content appears as completeness identities for the sigma matrices. With

$$
\sigma^\mu=(\mathbf 1,\sigma^i),
\qquad
\bar\sigma^\mu=(\mathbf 1,-\sigma^i),
$$

one has

$$
\sigma^\mu_{\alpha\dot\alpha}\bar\sigma_{\mu}^{\dot\beta\beta}
=2\delta_\alpha{}^\beta\delta_{\dot\alpha}{}^{\dot\beta}.
$$

There is also the antisymmetric identity

$$
\sigma^\mu_{\alpha\dot\alpha}\sigma_{\mu\beta\dot\beta}
=2\epsilon_{\alpha\beta}\epsilon_{\dot\alpha\dot\beta},
$$

with index placement following the conventions of the two-component spinor page.

The most basic two-component Fierz move is really the Schouten identity. For two-component spinor indices,

$$
\epsilon_{\alpha\beta}\epsilon_{\gamma\delta}
+\epsilon_{\alpha\gamma}\epsilon_{\delta\beta}
+\epsilon_{\alpha\delta}\epsilon_{\beta\gamma}=0.
$$

This is why products of Weyl spinor contractions often have only two independent pairings rather than three. In supersymmetry and spinor-helicity calculations, many “Fierz identities” are Schouten identities wearing a trench coat.

## Fierz identities and operator bases

In an effective field theory, one often writes several four-fermion operators that look independent:

$$
(\bar\psi\psi)(\bar\chi\chi),
\qquad
(\bar\psi\gamma^\mu\psi)(\bar\chi\gamma_\mu\chi),
\qquad
(\bar\psi\sigma^{\mu\nu}\chi)(\bar\chi\sigma_{\mu\nu}\psi),
$$

and so on. Fierz identities can relate some of them after flavor, color, gauge, and Lorentz contractions are included.

The phrase “after flavor, color, gauge, and Lorentz contractions are included” is crucial. A spinor Fierz identity only rearranges spinor indices. It does not automatically rearrange color indices or gauge representations. For non-Abelian gauge theories, a complete operator-basis reduction often combines spinor Fierz identities with group identities such as

$$
(T^a)_{ij}(T^a)_{kl}
=\frac12\left(\delta_{il}\delta_{kj}-\frac1N\delta_{ij}\delta_{kl}\right)
$$

for fundamental generators of $SU(N)$ with the common normalization $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$.

The sober workflow is:

1. Write all spinor, gauge, and flavor indices.
2. Decide which spinor pairing you want.
3. Apply the spinor Fierz identity.
4. Apply group-theory completeness if needed.
5. Use field statistics and flavor labels to simplify.
6. Only then declare operators redundant.

Skipping step 1 is a personality test. The algebra usually wins.

## Majorana fields and identical fermions

Majorana fields add two extra layers of bookkeeping.

First, diagonal Majorana vector and tensor bilinears vanish in four-dimensional Lorentzian signature:

$$
\bar\lambda\gamma^\mu\lambda=0,
\qquad
\bar\lambda\sigma^{\mu\nu}\lambda=0.
$$

Second, when the same field appears multiple times, exchanging two identical fermion operators creates signs. A Fierz identity may then imply that an operator is zero or that two channels are related by a numerical factor.

For example, if $\lambda$ is a single Majorana field, then any expression that Fierzes into a diagonal vector current

$$
\bar\lambda\gamma^\mu\lambda
$$

drops out. But if there are flavor labels $\lambda_a,\lambda_b$, mixed vector bilinears need not vanish. The identity knows about the spinor algebra; you still have to know whether the fields are identical.

A safe rule for Majorana work: do not set species labels equal until after the Fierz rearrangement and charge-conjugation symmetry properties have been applied.

## Dimensional regularization warning

The Fierz identities on this page are four-dimensional identities. They use the $16$-element gamma-matrix basis and the four-dimensional $\gamma^5$.

In dimensional regularization, especially in chiral theories, this becomes delicate. In $d=4-2\epsilon$, the gamma matrix algebra does not have the same finite $16$-element basis. Operators that vanish by a four-dimensional Fierz identity can become evanescent operators: they vanish as $\epsilon\to0$ but affect loop-level matching and anomalous dimensions.

So the operational rule is:

- For tree-level four-dimensional algebra, use the identities freely.
- For loop-level EFT matching in dimensional regularization, track evanescent operators and the chosen $\gamma^5$ scheme.
- For chiral gauge theories and anomalies, do not assume four-dimensional Fierz manipulations commute with regularization.

This is not a philosophical warning. It changes anomalous-dimension matrices.

## Common pitfalls

**Using the scalar Fierz identity without the tensor term.** The tensor term has coefficient $1/8$ in the scalar identity. Dropping it is only valid after an extra projection, not in the full Dirac algebra.

**Mixing $\gamma^5$ and $i\gamma^5$ bases.** The Fierz table above uses $\gamma^5$. Hermitian pseudoscalar operators use $i\gamma^5$ in the site conventions. Convert deliberately.

**Forgetting the overall Grassmann sign.** Matrix identities are sign-free. Reordering anticommuting fields is not.

**Applying spinor Fierz identities to color indices.** Spinor completeness does not know about color. Use group completeness separately.

**Using four-dimensional Fierz identities inside dimensional regularization without evanescent operators.** This is a classic EFT trap.

**Setting Majorana fields equal too early.** Keep species labels until after the rearrangement.

## Exercises

### Exercise 1: Derive the scalar Fierz identity from completeness

Start from

$$
(\bar\psi_1\psi_2)(\bar\psi_3\psi_4)
=
(\bar\psi_1)_i(\psi_2)_j(\bar\psi_3)_k(\psi_4)_l\delta_{ij}\delta_{kl}.
$$

Use the completeness relation for $\delta_{ij}\delta_{kl}$ to derive the commuting-spinor scalar Fierz identity.

<details><summary><strong>Solution</strong></summary>

Insert

$$
\delta_{ij}\delta_{kl}
=
\frac14\delta_{il}\delta_{kj}
+\frac14(\gamma^5)_{il}(\gamma^5)_{kj}
+\frac14(\gamma^\mu)_{il}(\gamma_\mu)_{kj}
-\frac14(\gamma^\mu\gamma^5)_{il}(\gamma_\mu\gamma^5)_{kj}
+\frac18(\sigma^{\mu\nu})_{il}(\sigma_{\mu\nu})_{kj}.
$$

For commuting spinors, the first term gives

$$
\frac14(\bar\psi_1)_i(\psi_4)_l\delta_{il}
(\bar\psi_3)_k(\psi_2)_j\delta_{kj}
=
\frac14(\bar\psi_1\psi_4)(\bar\psi_3\psi_2).
$$

The other terms are identical with the corresponding gamma insertions. Therefore

$$
(\bar\psi_1\psi_2)(\bar\psi_3\psi_4)
=
\frac14(\bar\psi_1\psi_4)(\bar\psi_3\psi_2)
+\frac14(\bar\psi_1\gamma^5\psi_4)(\bar\psi_3\gamma^5\psi_2)
$$

$$
+\frac14(\bar\psi_1\gamma^\mu\psi_4)(\bar\psi_3\gamma_\mu\psi_2)
-\frac14(\bar\psi_1\gamma^\mu\gamma^5\psi_4)(\bar\psi_3\gamma_\mu\gamma^5\psi_2)
$$

$$
+\frac18(\bar\psi_1\sigma^{\mu\nu}\psi_4)(\bar\psi_3\sigma_{\mu\nu}\psi_2).
$$

For anticommuting fields, this same rearrangement gets an extra overall minus sign from moving odd fields.

</details>

### Exercise 2: Read the vector row of the Fierz table

Using the five-channel table, write the commuting-spinor rearrangement of

$$
B_V=(\bar\psi_1\gamma^\mu\psi_2)(\bar\psi_3\gamma_\mu\psi_4).
$$

<details><summary><strong>Solution</strong></summary>

The vector row of the table is

$$
(1,\,-1,\,-\frac12,\,-\frac12,\,0).
$$

Therefore

$$
(\bar\psi_1\gamma^\mu\psi_2)(\bar\psi_3\gamma_\mu\psi_4)
=
(\bar\psi_1\psi_4)(\bar\psi_3\psi_2)
-(\bar\psi_1\gamma^5\psi_4)(\bar\psi_3\gamma^5\psi_2)
$$

$$
-\frac12(\bar\psi_1\gamma^\mu\psi_4)(\bar\psi_3\gamma_\mu\psi_2)
-\frac12(\bar\psi_1\gamma^\mu\gamma^5\psi_4)(\bar\psi_3\gamma_\mu\gamma^5\psi_2).
$$

There is no tensor term in this row.

</details>

### Exercise 3: Explain the Grassmann sign

Why does the anticommuting-field version of the scalar Fierz identity differ by an overall minus sign from the commuting-spinor version?

<details><summary><strong>Solution</strong></summary>

The matrix identity rewrites the index contraction from $(12)(34)$ to $(14)(32)$. In components, the original field order is schematically

$$
\bar\psi_1\,\psi_2\,\bar\psi_3\,\psi_4.
$$

The rearranged bilinears have order

$$
\bar\psi_1\,\psi_4\,\bar\psi_3\,\psi_2.
$$

For anticommuting spinor fields, moving $\psi_2$ and $\psi_4$ into this order requires an odd number of swaps of Grassmann-odd objects. Hence an overall minus sign appears. For commuting external wavefunctions, there is no such sign.

</details>

### Exercise 4: Chiral current-current rearrangement

Use

$$
(\gamma^\mu P_L)_{ij}(\gamma_\mu P_L)_{kl}
=
-(\gamma^\mu P_L)_{il}(\gamma_\mu P_L)_{kj}
$$

to show that for anticommuting fields

$$
(\bar\psi_1\gamma^\mu P_L\psi_2)(\bar\psi_3\gamma_\mu P_L\psi_4)
=
(\bar\psi_1\gamma^\mu P_L\psi_4)(\bar\psi_3\gamma_\mu P_L\psi_2).
$$

<details><summary><strong>Solution</strong></summary>

The matrix identity gives a minus sign when the spinor indices are rearranged. Passing from the matrix identity to anticommuting fields gives another minus sign from moving the odd fields into the new bilinear order. The two signs cancel:

$$
(-1)_{\text{matrix}}\times(-1)_{\text{Grassmann}}=+1.
$$

Therefore

$$
(\bar\psi_1\gamma^\mu P_L\psi_2)(\bar\psi_3\gamma_\mu P_L\psi_4)
=
(\bar\psi_1\gamma^\mu P_L\psi_4)(\bar\psi_3\gamma_\mu P_L\psi_2).
$$

The same argument works with $P_R$.

</details>

### Exercise 5: Why the tensor coefficient is one eighth

In the scalar completeness relation, why does the tensor term have coefficient $1/8$ rather than $1/4$?

<details><summary><strong>Solution</strong></summary>

The tensor insertion $\sigma^{\mu\nu}$ is antisymmetric. If the sum is written over all $\mu,\nu$, then each independent antisymmetric pair is counted twice: once as $(\mu,\nu)$ and once as $(\nu,\mu)$.

Equivalently, the trace inner product is

$$
\operatorname{tr}(\sigma^{\mu\nu}\sigma^{\rho\sigma})
=
4(\eta^{\mu\rho}\eta^{\nu\sigma}-\eta^{\mu\sigma}\eta^{\nu\rho}),
$$

and the projector onto antisymmetric two-index structures carries an extra factor of $1/2$. The scalar completeness coefficient is therefore

$$
\frac14\times\frac12=\frac18.
$$

If one sums only over $\mu<\nu$ with a separately normalized tensor basis, the coefficient convention changes. The full expression must be read together with the summation convention.

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. See the discussion of spinor representations and fermion bilinears.
- M. Srednicki, *Quantum Field Theory*. See the chapters on manipulating spinor indices, spinor technology, gamma-matrix technology, and four-fermion rearrangements.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. See the spinor, QED, and gamma-matrix identity discussions.
- A. Zee, *Quantum Field Theory in a Nutshell*. Useful for physical uses of spinor rearrangements and four-fermion interactions.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory* and *Aspects of Symmetry*. Useful for symmetry, current algebra, and fermion-operator reasoning.
- H. K. Dreiner, H. E. Haber, and S. P. Martin, “Two-component spinor techniques and Feynman rules for quantum field theory and supersymmetry.” Useful for two-component Fierz and Schouten identities.

## Version history

- **2026-06-24:** Initial polished draft. Derived Fierz identities from gamma-matrix completeness, fixed the five-channel table in the site conventions, separated commuting and anticommuting signs, and added chiral, two-component, Majorana, and evanescent-operator caveats.
