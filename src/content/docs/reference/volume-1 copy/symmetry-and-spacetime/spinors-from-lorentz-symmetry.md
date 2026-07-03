---
title: "Spinors from Lorentz Symmetry"
description: "How two-component spinors arise from the double cover SL(2,C) of the connected Lorentz group: Hermitian matrices, dotted and undotted indices, epsilon tensors, sigma matrices, Weyl spinors, and Dirac spinors."
sidebar:
  label: "Spinors from Lorentz Symmetry"
  order: 3
---

## Summary

Spinors are not mysterious extra decorations added to relativistic physics. In four spacetime dimensions they are the most economical linear objects on which the double cover of the connected Lorentz group acts.

The key fact is that a real Minkowski vector can be packaged as a Hermitian $2\times2$ matrix:

$$
X(x)=x^0\mathbf 1+x^i\sigma_i.
$$

With qft.org's mostly-minus convention,

$$
\det X=(x^0)^2-\mathbf x^2=x^\mu x_\mu.
$$

If $M\in SL(2,\mathbb C)$, then

$$
\boxed{X\longmapsto X'=MXM^\dagger}
$$

preserves the determinant. Therefore it induces a Lorentz transformation on the vector $x^\mu$. The matrices $M$ and $-M$ induce the same Lorentz transformation, so

$$
\boxed{SL(2,\mathbb C)\longrightarrow SO^+(1,3)}
$$

is a double cover.

A two-component **undotted spinor** transforms linearly by $M$. Its Hermitian conjugate transforms in the conjugate, **dotted** representation. A product with one undotted and one dotted index transforms like a vector; products of two same-type spinors can be contracted with the antisymmetric tensor $\epsilon$ to make Lorentz scalars.

This page fills in the spinor machinery promised by [Lorentz Representations](/foundations/symmetry-and-spacetime/lorentz-representations/). It explains why the irreducible representations

$$
\left(\frac12,0\right),
\qquad
\left(0,\frac12\right)
$$

are the natural spin-one-half building blocks before quantization. Srednicki develops this notation using dotted and undotted indices, invariant $\epsilon$ tensors, and $\sigma^\mu_{\alpha\dot\alpha}$ symbols; Coleman gives a particularly physical construction of Lorentz vectors as bilinears of Weyl spinors; Weinberg derives spinor fields from the compatibility of Lorentz covariance, locality, and particle representations (Srednicki 2007, §§34–36; Coleman 2019, chs. 18–20; Weinberg 1995, Vol. I, ch. 5).

<figure class="doc-figure" style="--figure-width: 46rem;">

![Spinors, vectors, and the SL(2,C) double cover](/figures/foundations/spinor-lorentz-double-cover.svg)

<figcaption>

The double cover $SL(2,\mathbb C)$ acts linearly on two-component spinors. A Minkowski vector is equivalently a Hermitian matrix $X=x^0\mathbf 1+x^i\sigma_i$, and the transformation $X\mapsto MXM^\dagger$ preserves $\det X=x^2$. One undotted and one dotted spinor index form a vector representation; same-type spinor indices are contracted with $\epsilon$ tensors.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Normalizations](/foundations/conventions-and-normalizations/), [Poincaré Symmetry](/foundations/symmetry-and-spacetime/poincare-symmetry/), [Lorentz Representations](/foundations/symmetry-and-spacetime/lorentz-representations/), [Weyl and Majorana Fields](/foundations/free-fields/weyl-and-majorana-fields/), and [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/).

:::note[Conventions]
This page uses qft.org's default mostly-minus metric $\eta=\operatorname{diag}(+,-,-,-)$. We define

$$
\sigma^\mu_{\alpha\dot\alpha}=(\mathbf 1,\sigma^i),
\qquad
\bar\sigma^{\mu\dot\alpha\alpha}=(\mathbf 1,-\sigma^i),
$$

where $\sigma^i$ are the Pauli matrices. Some books use mostly-plus metric or different index placements; the formulas then move signs around. The invariant content is unchanged.
:::

## The double cover in one line

The connected Lorentz group $SO^+(1,3)$ acts on real four-vectors and preserves the Minkowski norm. The group $SL(2,\mathbb C)$ acts on complex two-component columns and has determinant one. The bridge between them is the Hermitian matrix

$$
X(x)=x^0\mathbf 1+x^1\sigma_1+x^2\sigma_2+x^3\sigma_3.
$$

Explicitly,

$$
X(x)=
\begin{pmatrix}
x^0+x^3 & x^1-i x^2\\
x^1+i x^2 & x^0-x^3
\end{pmatrix}.
$$

Its determinant is

$$
\det X=(x^0+x^3)(x^0-x^3)-(x^1-i x^2)(x^1+i x^2),
$$

so

$$
\boxed{
\det X=(x^0)^2-(x^1)^2-(x^2)^2-(x^3)^2=x^\mu x_\mu.
}
$$

Now take $M\in SL(2,\mathbb C)$ and define

$$
X'=MXM^\dagger.
$$

The matrix $X'$ is Hermitian, so it corresponds to another real vector $x'^\mu$. Also,

$$
\det X'=\det(M)\det(X)\det(M^\dagger)=\det X.
$$

Thus $x'^\mu$ has the same Minkowski norm as $x^\mu$. The map

$$
M\mapsto \Lambda(M)
$$

defined by

$$
X(x')=MX(x)M^\dagger
$$

is a homomorphism from $SL(2,\mathbb C)$ onto the connected Lorentz group. Its kernel is

$$
M=\pm\mathbf 1.
$$

That is why spinors can change sign under a $2\pi$ rotation while vectors return to themselves.

:::tip[Spinors are not vectors with fewer components]
A spinor is an object on which the double cover $SL(2,\mathbb C)$ acts linearly. Vectors can be built from spinor bilinears, but a single spinor is not a vector and does not transform like any tensor representation of $SO^+(1,3)$ itself.
:::

## Rotations and boosts

The same $SL(2,\mathbb C)$ matrix formula contains both ordinary spin rotations and Lorentz boosts.

For a rotation by angle $\theta$ around the unit vector $\hat n$, take

$$
M_R=\exp\left(-\frac{i}{2}\theta\,\hat n\cdot\boldsymbol\sigma\right).
$$

This is unitary. If $\theta=2\pi$, then

$$
M_R=-\mathbf 1.
$$

The induced vector transformation is the identity rotation, but a spinor changes sign. That is the spin-one-half behavior in its cleanest form.

For a boost of rapidity $\eta$ along $\hat n$, take

$$
M_B=\exp\left(+\frac{1}{2}\eta\,\hat n\cdot\boldsymbol\sigma\right).
$$

This is Hermitian rather than unitary. For a boost along the $z$ direction,

$$
M_B=\begin{pmatrix}e^{\eta/2}&0\\0&e^{-\eta/2}\end{pmatrix}.
$$

Acting on the rest vector $x^\mu=(1,0,0,0)$ gives

$$
X'=M_BM_B^\dagger
=\begin{pmatrix}e^\eta&0\\0&e^{-\eta}\end{pmatrix}
=\cosh\eta\,\mathbf 1+\sinh\eta\,\sigma_3.
$$

Therefore

$$
x'^0=\cosh\eta,
\qquad
x'^3=\sinh\eta,
$$

which is exactly a Lorentz boost.

The important conceptual point is that boosts act nonunitarily on finite-dimensional spinor components. This is not a problem. Local field components transform in finite-dimensional, generally nonunitary Lorentz representations; the Hilbert space of physical states carries a unitary representation of the Poincaré group.

## Dotted and undotted indices

An undotted spinor is written

$$
\chi_\alpha,
\qquad
\alpha=1,2.
$$

It transforms as

$$
\boxed{
\chi_\alpha\mapsto M_\alpha{}^\beta\chi_\beta.
}
$$

This is the representation usually called

$$
\left(\frac12,0\right).
$$

Its Hermitian conjugate is written with a dotted index:

$$
\chi^\dagger_{\dot\alpha},
\qquad
\dot\alpha=\dot 1,\dot 2.
$$

It transforms in the complex-conjugate representation,

$$
\boxed{
\chi^\dagger_{\dot\alpha}
\mapsto
M^*_{\dot\alpha}{}^{\dot\beta}\chi^\dagger_{\dot\beta}.
}
$$

This is the representation usually called

$$
\left(0,\frac12\right).
$$

The dot is not a decoration. It prevents illegal contractions. Undotted indices contract with undotted indices; dotted indices contract with dotted indices. One undotted plus one dotted index can be turned into a Lorentz vector using $\sigma^\mu$ or $\bar\sigma^\mu$.

There is a small linguistic trap here. In Lorentzian signature, the Hermitian conjugate of a left-handed Weyl field transforms as a right-handed object. But when doing complexified representation theory, one often treats left and right spinors as independent complex representations. Both viewpoints are useful; the context decides which one is meant.

## The ε tensor

The group $SL(2,\mathbb C)$ preserves the antisymmetric tensor

$$
\epsilon_{\alpha\beta}
=\begin{pmatrix}0&1\\-1&0\end{pmatrix}_{\alpha\beta}
$$

up to the convention for the sign of $\epsilon_{12}$. Since $\det M=1$,

$$
\boxed{
M^T\epsilon M=\epsilon.
}
$$

This tensor is used to raise and lower undotted spinor indices:

$$
\chi^\alpha=\epsilon^{\alpha\beta}\chi_\beta,
\qquad
\chi_\alpha=\epsilon_{\alpha\beta}\chi^\beta.
$$

There is an analogous tensor for dotted indices:

$$
\epsilon_{\dot\alpha\dot\beta},
\qquad
\epsilon^{\dot\alpha\dot\beta}.
$$

A Lorentz scalar can be made from two undotted spinors:

$$
\chi\psi\equiv\chi^\alpha\psi_\alpha.
$$

Another scalar can be made from two dotted spinors:

$$
\chi^\dagger\psi^\dagger
\equiv
\chi^\dagger_{\dot\alpha}\psi^{\dagger\dot\alpha}.
$$

For fermion fields, these contractions carry signs because the fields anticommute. A common compact convention is that

$$
\chi\psi=\psi\chi
$$

for anticommuting two-component fields, after the antisymmetry of $\epsilon$ and the minus sign from exchanging fermions are both included. If a sign looks surprising in two-component notation, first check both the $\epsilon$ convention and the Grassmann sign.

## Sigma matrices as the bridge

The sigma matrices are invariant symbols that convert spinor indices into vector indices. In our convention,

$$
\sigma^\mu_{\alpha\dot\alpha}=(\mathbf 1,\sigma^i),
\qquad
\bar\sigma^{\mu\dot\alpha\alpha}=(\mathbf 1,-\sigma^i).
$$

They obey

$$
\boxed{
\sigma^\mu\bar\sigma^\nu+
\sigma^\nu\bar\sigma^\mu
=2\eta^{\mu\nu}\mathbf 1,
}
$$

and

$$
\boxed{
\bar\sigma^\mu\sigma^\nu+
\bar\sigma^\nu\sigma^\mu
=2\eta^{\mu\nu}\mathbf 1.
}
$$

These are the two-component ancestors of the Dirac Clifford algebra.

A vector can be written as a bispinor:

$$
V_{\alpha\dot\alpha}
=V_\mu\sigma^\mu_{\alpha\dot\alpha}.
$$

Conversely,

$$
V^\mu
=\frac12\bar\sigma^{\mu\dot\alpha\alpha}V_{\alpha\dot\alpha},
$$

with the precise sign depending on whether the vector index is raised or lowered and on the metric convention. The invariant idea is simple: a Lorentz vector is equivalent to one undotted plus one dotted spinor index,

$$
\boxed{
\left(\frac12,0\right)\otimes
\left(0,\frac12\right)
=\left(\frac12,\frac12\right).
}
$$

This is the algebra behind expressions such as

$$
\chi^\dagger\bar\sigma^\mu\chi,
$$

which transform as Lorentz vectors.

Coleman makes this point very vividly: bilinears of a Weyl spinor and its conjugate transform like the components of a four-vector under boosts as well as rotations (Coleman 2019, ch. 19). Srednicki encodes the same fact in the invariance of $\sigma^\mu_{\alpha\dot\alpha}$ and the associated identities among $\sigma$, $\bar\sigma$, and $\epsilon$ (Srednicki 2007, §35).

## Lorentz generators for Weyl spinors

The spinor representation of the Lorentz algebra is generated by matrices built from $\sigma^\mu$ and $\bar\sigma^\mu$. Define

$$
(\sigma^{\mu\nu})_\alpha{}^\beta
=\frac{i}{4}
\left(
\sigma^\mu\bar\sigma^\nu-
\sigma^\nu\bar\sigma^\mu
\right)_\alpha{}^\beta,
$$

and

$$
(\bar\sigma^{\mu\nu})^{\dot\alpha}{}_{\dot\beta}
=\frac{i}{4}
\left(
\bar\sigma^\mu\sigma^\nu-
\bar\sigma^\nu\sigma^\mu
\right)^{\dot\alpha}{}_{\dot\beta}.
$$

The infinitesimal transformation of an undotted spinor can be written schematically as

$$
\chi_\alpha\mapsto
\left[
\delta_\alpha{}^\beta+\frac{i}{2}\omega_{\mu\nu}
(\sigma^{\mu\nu})_\alpha{}^\beta
\right]\chi_\beta.
$$

The dotted representation uses $\bar\sigma^{\mu\nu}$. Under rotations the two look equivalent, because both contain spin one half. Under boosts they differ by the sign appropriate to the two inequivalent Lorentz representations.

This is the operational meaning of

$$
\left(\frac12,0\right)
\quad\text{and}\quad
\left(0,\frac12\right).
$$

They are the two chiral spinor representations of the connected Lorentz group.

## Dirac spinors from left and right pieces

A Dirac spinor is not irreducible under the connected Lorentz group. It is the direct sum

$$
\boxed{
\Psi_D\in
\left(\frac12,0\right)
\oplus
\left(0,\frac12\right).
}
$$

In the chiral basis one may write

$$
\Psi_D=
\begin{pmatrix}
\chi_\alpha\\
\eta^{\dagger\dot\alpha}
\end{pmatrix},
$$

where $\chi$ and $\eta$ are two independent left-handed Weyl fields. In this basis,

$$
\gamma^\mu=
\begin{pmatrix}
0&\sigma^\mu\\
\bar\sigma^\mu&0
\end{pmatrix}
$$

up to the index-placement conventions of the page. The gamma-matrix Clifford algebra follows directly from the sigma-matrix identities.

A Dirac mass couples the two chiral representations:

$$
\mathcal L_m=-m(\eta\chi+\chi^\dagger\eta^\dagger).
$$

A Majorana mass instead contracts a Weyl spinor with itself:

$$
\mathcal L_m=-\frac12(m\chi\chi+m^*\chi^\dagger\chi^\dagger).
$$

The Majorana term is allowed only when the internal quantum numbers permit it. Lorentz symmetry alone permits the contraction; gauge symmetry or global charge assignments may forbid it. That is why spinor representation theory is necessary but not sufficient for writing a physical Lagrangian.

## Parity is not part of the connected group

The connected Lorentz group has two inequivalent Weyl representations:

$$
\left(\frac12,0\right),
\qquad
\left(0,\frac12\right).
$$

Parity exchanges them:

$$
P:
\left(\frac12,0\right)
\longleftrightarrow
\left(0,\frac12\right).
$$

Therefore a single isolated Weyl representation is not parity invariant by itself. A parity-invariant spinor theory must contain both chiralities and specify how parity acts between them.

This is one reason chiral theories are so important. The Standard Model does not assign the same electroweak gauge representation to all left- and right-handed fermions. Its chirality is not merely a notation choice; it is a statement about how Lorentz representations and internal gauge representations are combined.

## Index dictionary

Here is the minimum dictionary that keeps most two-component formulas sane.

| Object | Representation | Meaning |
|---|---:|---|
| $\chi_\alpha$ | $(\frac12,0)$ | left-handed Weyl spinor |
| $\chi^\dagger_{\dot\alpha}$ | $(0,\frac12)$ | conjugate/dotted spinor |
| $\epsilon_{\alpha\beta}$ | invariant | contracts two undotted indices |
| $\epsilon_{\dot\alpha\dot\beta}$ | invariant | contracts two dotted indices |
| $\sigma^\mu_{\alpha\dot\alpha}$ | bridge | turns a vector into a bispinor |
| $V_{\alpha\dot\alpha}$ | $(\frac12,\frac12)$ | Lorentz vector as one undotted plus one dotted index |
| $\chi\psi$ | $(0,0)$ | Lorentz scalar from two undotted spinors |
| $\chi^\dagger\bar\sigma^\mu\psi$ | $(\frac12,\frac12)$ | vector bilinear |

A useful rule of thumb:

```txt
same kind of spinor index + epsilon → scalar;
one undotted and one dotted + sigma → vector.
```

This rule is only a representation-theory rule. Fermion statistics, equations of motion, gauge charges, and reality conditions add further constraints.

## Common pitfalls

**Saying spinors are representations of the Lorentz group itself.** More precisely, spinors are representations of the double cover $SL(2,\mathbb C)$ of the connected Lorentz group. A $2\pi$ rotation is invisible to vectors but acts as $-1$ on spinors.

**Contracting dotted with undotted indices directly.** A dotted index and an undotted index are different representation types. To combine them into a vector, use $\sigma^\mu$ or $\bar\sigma^\mu$.

**Forgetting that boosts are nonunitary on field components.** This is expected. Finite-dimensional Lorentz representations are generally nonunitary because the Lorentz group is noncompact. The full quantum theory still acts unitarily on the Hilbert space.

**Confusing chirality with helicity.** Chirality is a Lorentz-representation label. Helicity is a particle-state label. They are tied together for massless particles, but they are not the same concept for massive particles.

**Treating a Majorana condition as always allowed.** Lorentz symmetry allows a Majorana contraction, but internal charges may forbid it. A charged fermion cannot generally be identified with its own antiparticle.

**Losing signs in two-component notation.** Signs depend on metric convention, epsilon convention, index placement, and whether the spinors are commuting test spinors or anticommuting quantum fields. Write indices when in doubt. Tiny signs are where gremlins do their postdocs.

## Relations to other pages

- [Lorentz Representations](/foundations/symmetry-and-spacetime/lorentz-representations/) classifies the finite-dimensional representations $(j_L,j_R)$; this page develops the most important spinor examples explicitly.
- [Weyl and Majorana Fields](/foundations/free-fields/weyl-and-majorana-fields/) uses this machinery to build free chiral and self-conjugate spinor fields.
- [Dirac Field](/foundations/free-fields/dirac-field/) packages the two chiral spinor representations into a four-component field and quantizes it.
- [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/) classifies Lorentz scalars, vectors, axial vectors, tensors, and pseudoscalars built from Dirac spinors.
- [Discrete Symmetries](/foundations/symmetry-and-spacetime/discrete-symmetries/) will explain how parity, charge conjugation, and time reversal act on these spinor structures.
- [Spin-Statistics](/foundations/symmetry-and-spacetime/spin-statistics/) will explain why spinor fields are quantized with anticommutation relations.

## Research status

- **Established:** The double-cover relation $SL(2,\mathbb C)\to SO^+(1,3)$, the two inequivalent Weyl representations, and the sigma-matrix dictionary are textbook-standard.
- **Convention-sensitive:** Signs in sigma-matrix identities, epsilon contractions, and four-component gamma matrices depend on metric and index conventions.
- **Beyond this page:** In curved spacetime, spinors require a spin structure and a local Lorentz frame. In amplitudes, massless spinor-helicity variables refine these same two-component spinors into on-shell square roots of null momenta.

## Exercises

### Exercise 1: Determinant of the vector matrix

Let

$$
X=x^0\mathbf 1+x^i\sigma_i.
$$

Show that $\det X=x^\mu x_\mu$ in mostly-minus signature.

<details>
<summary><strong>Solution</strong></summary>

Using the explicit Pauli matrices,

$$
X=
\begin{pmatrix}
x^0+x^3 & x^1-i x^2\\
x^1+i x^2 & x^0-x^3
\end{pmatrix}.
$$

Therefore

$$
\det X=(x^0+x^3)(x^0-x^3)-(x^1-i x^2)(x^1+i x^2).
$$

This gives

$$
\det X=(x^0)^2-(x^3)^2-(x^1)^2-(x^2)^2.
$$

Thus

$$
\boxed{\det X=x^\mu x_\mu.}
$$

</details>

### Exercise 2: Why determinant one matters

Suppose $X'=MXM^\dagger$. Show that $\det X'=\det X$ if $M\in SL(2,\mathbb C)$.

<details>
<summary><strong>Solution</strong></summary>

Use multiplicativity of the determinant:

$$
\det X'
=\det(MXM^\dagger)
=\det M\,\det X\,\det M^\dagger.
$$

For $M\in SL(2,\mathbb C)$,

$$
\det M=1,
\qquad
\det M^\dagger=(\det M)^*=1.
$$

Hence

$$
\boxed{\det X'=\det X.}
$$

Since $\det X$ is the Minkowski norm, the induced transformation preserves the Lorentz interval.

</details>

### Exercise 3: The kernel of the cover

Show that $M=\mathbf 1$ and $M=-\mathbf 1$ induce the same Lorentz transformation through $X\mapsto MXM^\dagger$.

<details>
<summary><strong>Solution</strong></summary>

For $M=\mathbf 1$,

$$
X'=\mathbf 1 X\mathbf 1=X.
$$

For $M=-\mathbf 1$,

$$
X'=(-\mathbf 1)X(-\mathbf 1)^\dagger.
$$

Since $(-\mathbf 1)^\dagger=-\mathbf 1$,

$$
X'=(-\mathbf 1)X(-\mathbf 1)=X.
$$

So both matrices induce the identity Lorentz transformation. This is the simplest manifestation of the double cover.

</details>

### Exercise 4: A boost from a spinor matrix

Let

$$
M=\exp\left(\frac{\eta}{2}\sigma_3\right)
=\begin{pmatrix}e^{\eta/2}&0\\0&e^{-\eta/2}\end{pmatrix}.
$$

Apply $X\mapsto MXM^\dagger$ to $X=\mathbf 1$. What vector does the result represent?

<details>
<summary><strong>Solution</strong></summary>

Since $M$ is Hermitian,

$$
X'=MM^\dagger=M^2
=\begin{pmatrix}e^\eta&0\\0&e^{-\eta}\end{pmatrix}.
$$

Rewrite this as

$$
X'=\cosh\eta\,\mathbf 1+
\sinh\eta\,\sigma_3.
$$

Therefore it represents the vector

$$
\boxed{x'^\mu=(\cosh\eta,0,0,\sinh\eta).}
$$

This is the Lorentz boost of the rest vector $(1,0,0,0)$ along the $z$ direction.

</details>

### Exercise 5: Scalar from two spinors

Let $\chi_\alpha$ and $\psi_\alpha$ transform as undotted spinors. Show that

$$
\chi\psi\equiv\chi^\alpha\psi_\alpha
$$

is Lorentz invariant.

<details>
<summary><strong>Solution</strong></summary>

Using $\chi^\alpha=\epsilon^{\alpha\beta}\chi_\beta$, the scalar is

$$
\chi\psi=\epsilon^{\alpha\beta}\chi_\beta\psi_\alpha.
$$

Under $M\in SL(2,\mathbb C)$, both spinors transform by $M$. The contraction transforms with

$$
\epsilon^{\alpha\beta}M_\beta{}^\gamma M_\alpha{}^\delta.
$$

The defining invariant property of $\epsilon$ is equivalent to

$$
M^T\epsilon M=\epsilon.
$$

Therefore the transformed contraction equals the original contraction. Hence

$$
\boxed{\chi\psi\ \,\text{is Lorentz invariant}.}
$$

</details>

### Exercise 6: Vector from one undotted and one dotted spinor

Let $\chi_\alpha$ transform by $M$ and $\chi^\dagger_{\dot\alpha}$ by $M^*$. Explain why

$$
V_{\alpha\dot\alpha}=\chi_\alpha\chi^\dagger_{\dot\alpha}
$$

transforms as a Lorentz vector.

<details>
<summary><strong>Solution</strong></summary>

The object $V_{\alpha\dot\alpha}$ transforms as

$$
V_{\alpha\dot\alpha}
\mapsto
M_\alpha{}^\beta
M^*_{\dot\alpha}{}^{\dot\beta}
V_{\beta\dot\beta}.
$$

This is exactly the transformation law of a Hermitian spinor matrix

$$
V=V_\mu\sigma^\mu.
$$

The same transformation can be written as

$$
V\mapsto MVM^\dagger.
$$

But $MVM^\dagger$ is the construction that induces a Lorentz transformation on the associated vector. Therefore

$$
\boxed{V_{\alpha\dot\alpha}\text{ transforms in }(\tfrac12,\tfrac12),\text{ the vector representation}.}
$$

</details>

## Sources and further reading

- É. Cartan, *The Theory of Spinors*, for the classical mathematical origin of spinors.
- H. Weyl, *The Classical Groups*, for the representation-theoretic setting of spinors.
- M. Srednicki, *Quantum Field Theory*, §§33–36, for Lorentz representations, two-component spinor indices, invariant $\epsilon$ and $\sigma$ symbols, and Weyl/Dirac Lagrangians.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 18–20, for Lorentz representations and the construction of vectors and Dirac fields from Weyl spinors.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§2.5 and 5.4–5.7, for particle representations, causal fields, and general Lorentz representations.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. II.1–II.3 and Appendix E, for a compact physical introduction to Dirac, Weyl, and Majorana spinors.

## Version history

- **2026-05-23:** Initial qft.org page on deriving two-component spinors from $SL(2,\mathbb C)$, the Hermitian-matrix representation of vectors, dotted and undotted indices, $\epsilon$ tensors, $\sigma^\mu$ bridges, Weyl generators, Dirac spinors, and parity exchange.
