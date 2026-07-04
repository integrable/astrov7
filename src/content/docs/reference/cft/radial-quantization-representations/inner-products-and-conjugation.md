---
title: "Inner Products and Conjugation"
description: "Reflection positivity, radial Hermitian conjugation, BPZ conjugation, and adjoints of conformal generators."
sidebar:
  order: 2
---

## Goal

The previous page explained how radial quantization turns a local operator into a state on $S^{d-1}$:

$$
\mathcal O(0)
\quad\longleftrightarrow\quad
|\mathcal O\rangle.
$$

That statement is only half of the Hilbert-space story. A Hilbert space also needs an inner product. In an ordinary Hamiltonian quantization, the inner product is usually given to us from canonical quantization. In Euclidean CFT, the inner product is more subtle: it is reconstructed from Euclidean correlation functions by a reflection operation.

The key point is this:

$$
\boxed{
\text{Hermitian conjugation in radial quantization is radial reflection, not ordinary complex conjugation at fixed Euclidean time.}
}
$$

On flat Euclidean space, radial reflection is inversion through the unit sphere,

$$
R:x^\mu\mapsto \frac{x^\mu}{x^2}.
$$

On the cylinder, where $r=e^\tau$, the same operation is simply

$$
\tau\mapsto -\tau.
$$

This page develops the inner product, the adjoint operation on local operators, the adjoints of conformal generators, and the first consequences of positivity. This is the foundation for the unitarity bounds on the next page.

## Conventions for this page

There are two common ways to write the conformal algebra. One uses Hermitian spacetime generators and therefore many explicit factors of $i$. The other, common in conformal bootstrap and Euclidean radial quantization, absorbs those factors and writes the representation-theory algebra as

$$
[D,P_\mu]=P_\mu,
\qquad
[D,K_\mu]=-K_\mu,
$$

$$
[M_{\mu\nu},P_\rho]
=
\delta_{\nu\rho}P_\mu-\delta_{\mu\rho}P_\nu,
$$

$$
[M_{\mu\nu},K_\rho]
=
\delta_{\nu\rho}K_\mu-\delta_{\mu\rho}K_\nu,
$$

$$
[K_\mu,P_\nu]
=
2\delta_{\mu\nu}D-2M_{\mu\nu}.
$$

This page uses this second convention. In it, $D$ is Hermitian, $P_\mu$ and $K_\mu$ are adjoints, and the $SO(d)$ generators $M_{\mu\nu}$ are anti-Hermitian:

$$
D^\dagger=D,
\qquad
P_\mu^\dagger=K_\mu,
\qquad
M_{\mu\nu}^\dagger=-M_{\mu\nu}.
$$

If one instead defines Hermitian angular momentum generators

$$
J_{\mu\nu}=iM_{\mu\nu},
$$

then

$$
J_{\mu\nu}^\dagger=J_{\mu\nu}.
$$

Nothing physical depends on this convention. What matters is the invariant statement:

$$
\boxed{\text{translations and special conformal transformations are adjoint to each other in radial quantization.}}
$$

## The cylinder picture

Radial quantization maps punctured Euclidean space to the cylinder:

$$
\mathbb R^d\setminus\{0\}
\simeq
S^{d-1}\times\mathbb R_\tau,
\qquad
\tau=\log r.
$$

The ket state is prepared by a path integral over the region of earlier radial time. If the quantization sphere is the unit sphere $r=1$, then the ket lives inside the unit ball:

$$
r<1
\qquad\Longleftrightarrow\qquad
\tau<0.
$$

The bra state must be prepared by the reflected configuration at later radial time:

$$
r>1
\qquad\Longleftrightarrow\qquad
\tau>0.
$$

The reflection that exchanges these two regions is

$$
\tau\mapsto -\tau.
$$

Since $r=e^\tau$, this is

$$
r\mapsto \frac{1}{r}.
$$

In vector notation this is inversion through the unit sphere:

$$
R x^\mu=\frac{x^\mu}{x^2}.
$$

<figure class="doc-figure" style="--figure-width: 44rem; --caption-width: 55rem;">

![Radial Hermitian conjugation by inversion](/figures/cft/radial-conjugation-inversion.svg)

<figcaption>

Radial conjugation. On $\mathbb R^d$, the reflection that turns a ket insertion into a bra insertion is inversion $R x=x/x^2$, mapping $r$ to $1/r$. On the cylinder it is simply $\tau\mapsto -\tau$. For a scalar primary, radial conjugation sends $\mathcal O(x)$ to $|x|^{-2\Delta}\mathcal O^\dagger(Rx)$.

</figcaption>
</figure>

This is the Euclidean version of the familiar Hamiltonian statement that bras are obtained from kets by time reflection plus complex conjugation. The only novelty is that the Euclidean time coordinate is radial time.

## States from insertions inside the unit sphere

Let $\mathcal A$ be a collection of local operator insertions inside the unit ball. For example,

$$
\mathcal A
=
\mathcal O_1(x_1)\mathcal O_2(x_2)\cdots \mathcal O_n(x_n),
\qquad
|x_i|<1.
$$

Radial quantization interprets this collection as a state on the unit sphere:

$$
|\Psi_{\mathcal A}\rangle
=
\mathcal A|0\rangle.
$$

If a Lagrangian description exists, this state is represented by the path integral over the unit ball with the insertions $\mathcal A$ included. If no Lagrangian description is available, the same state is characterized abstractly by its correlation functions with all operators outside the sphere.

The inner product of two such states should be computed by gluing a reflected bra configuration outside the unit sphere to a ket configuration inside the unit sphere. Thus, for two insertion collections $\mathcal A$ and $\mathcal B$,

$$
\langle \Psi_{\mathcal A}|\Psi_{\mathcal B}\rangle
=
\langle \Theta \mathcal A\,\mathcal B\rangle_{\mathbb R^d}.
$$

Here $\Theta$ is an anti-linear operation: it complex-conjugates coefficients and reflects each operator insertion by inversion.

This equation is the basic definition of the radial inner product.

## Radial reflection positivity

The condition that the Euclidean theory describes a unitary Lorentzian theory is not just conformal invariance. It is also **reflection positivity**.

In radial quantization, reflection positivity says that for every collection $\mathcal A$ of insertions inside the unit ball,

$$
\boxed{
\langle \Theta\mathcal A\,\mathcal A\rangle\geq 0.
}
$$

Equivalently,

$$
\|\Psi_{\mathcal A}\|^2\geq 0.
$$

This is the Euclidean origin of Hilbert-space positivity.

The positivity condition is powerful because $\mathcal A$ can be any finite linear combination of local operator insertions. For example,

$$
\mathcal A
=
\sum_i c_i\mathcal O_i(x_i),
\qquad
|x_i|<1.
$$

Then reflection positivity implies

$$
\sum_{i,j}\overline{c_i}c_j
\langle \Theta\mathcal O_i(x_i)\,\mathcal O_j(x_j)\rangle
\geq 0.
$$

Thus the matrix

$$
G_{ij}
=
\langle \Theta\mathcal O_i(x_i)\,\mathcal O_j(x_j)\rangle
$$

must be positive semidefinite. This simple statement becomes, after expanding in conformal families, the positivity input used in the conformal bootstrap.

A Euclidean CFT can obey all conformal Ward identities and crossing equations but fail reflection positivity. Such a theory is nonunitary. The Yang-Lee edge singularity is a famous two-dimensional example of a useful nonunitary CFT. For AdS/CFT preparation, however, the unitary case is the main one: a positive CFT Hilbert space is the boundary avatar of a ghost-free bulk quantum theory.

## Conjugating scalar primaries

Let $\mathcal O$ be a scalar primary of dimension $\Delta$. Under inversion,

$$
R:x^\mu\mapsto \frac{x^\mu}{x^2},
$$

the Weyl factor is

$$
\Omega(x)=\frac{1}{x^2}.
$$

A scalar primary transforms with one factor of $\Omega^\Delta$. Therefore the radial Hermitian conjugate of a scalar primary is

$$
\boxed{
\mathcal O(x)^\dagger_{\rm rad}
=
|x|^{-2\Delta}\mathcal O^\dagger\left(\frac{x}{x^2}\right).
}
$$

When $\mathcal O$ is Hermitian as an internal operator, $\mathcal O^\dagger=\mathcal O$, this becomes

$$
\mathcal O(x)^\dagger_{\rm rad}
=
|x|^{-2\Delta}\mathcal O\left(\frac{x}{x^2}\right).
$$

The subscript “rad” is often omitted, but it is conceptually important. The operation is not merely ordinary complex conjugation. It includes inversion.

The formula is easy to remember from the special case $x=0$. The ket is

$$
|\mathcal O\rangle
=
\mathcal O(0)|0\rangle.
$$

The bra must be an insertion at infinity:

$$
\boxed{
\langle \mathcal O|
=
\lim_{|x|\to\infty}|x|^{2\Delta}\langle 0|\mathcal O^\dagger(x).
}
$$

This is exactly the formula already anticipated on the previous page.

## Inner products from two-point functions

Suppose $\mathcal O_i$ and $\mathcal O_j$ are scalar primaries with dimensions $\Delta_i$ and $\Delta_j$. Their flat-space two-point function has the form

$$
\langle \mathcal O_i^\dagger(x)\mathcal O_j(0)\rangle
=
\frac{C_{ij}\,\delta_{\Delta_i,\Delta_j}}{|x|^{2\Delta_i}},
$$

where $C_{ij}$ is a Hermitian matrix within the subspace of operators having the same quantum numbers and the same dimension. The radial inner product is

$$
\langle \mathcal O_i|\mathcal O_j\rangle
=
\lim_{|x|\to\infty}|x|^{2\Delta_i}
\langle \mathcal O_i^\dagger(x)\mathcal O_j(0)\rangle.
$$

Therefore

$$
\boxed{
\langle \mathcal O_i|\mathcal O_j\rangle
=
C_{ij}\,\delta_{\Delta_i,\Delta_j}.
}
$$

In a unitary CFT, $C_{ij}$ is positive semidefinite. After quotienting out possible null states, one can choose an orthonormal basis of primaries:

$$
\langle \mathcal O_i|\mathcal O_j\rangle
=
\delta_{ij}.
$$

In this basis, the scalar two-point function is usually normalized as

$$
\langle \mathcal O_i^\dagger(x)\mathcal O_j(0)\rangle
=
\frac{\delta_{ij}}{|x|^{2\Delta_i}}.
$$

This normalization is not just cosmetic. It is the normalization in which OPE coefficients become physical structure constants, and in which positivity of conformal block expansions becomes transparent.

## Conjugating spinning primaries

For spinning primaries, inversion also rotates tensor indices. The relevant matrix is the inversion tensor

$$
I^\mu{}_{\nu}(x)
=
\delta^\mu{}_{\nu}-2\frac{x^\mu x_\nu}{x^2}.
$$

It satisfies

$$
I^\mu{}_{\rho}(x)I^\rho{}_{\nu}(x)=\delta^\mu{}_{\nu}.
$$

For a symmetric traceless spin-$\ell$ primary $\mathcal O_{\mu_1\cdots\mu_\ell}$ of dimension $\Delta$, radial conjugation gives schematically

$$
\boxed{
\mathcal O_{\mu_1\cdots\mu_\ell}(x)^\dagger_{\rm rad}
=
|x|^{-2\Delta}
I_{\mu_1}{}^{\nu_1}(x)\cdots I_{\mu_\ell}{}^{\nu_\ell}(x)
\mathcal O^\dagger_{\nu_1\cdots\nu_\ell}\left(\frac{x}{x^2}\right).
}
$$

This is the higher-dimensional version of the familiar two-dimensional rule that a primary field with weights $(h,\bar h)$ acquires powers of the conformal Jacobian under radial conjugation.

A convenient way to package spinning operators is to contract them with a null polarization vector $z^\mu$:

$$
\mathcal O(x,z)
=
\mathcal O_{\mu_1\cdots\mu_\ell}(x)z^{\mu_1}\cdots z^{\mu_\ell},
\qquad
z^2=0.
$$

Then the conjugation rule can be written by reflecting the polarization as well:

$$
z^\mu\mapsto I^\mu{}_{\nu}(x)z^\nu.
$$

This is why the inversion tensor appeared earlier in the page on spinning correlators. It is not a random tensor structure; it is the tensorial part of conformal inversion, and therefore it is built into the radial inner product for spinning states.

## Adjoint of the conformal generators

The radial inner product determines the adjoint operation on the conformal algebra. Since $D$ generates translations in cylinder time $\tau$, it is the cylinder Hamiltonian:

$$
H_{\rm cyl}=D.
$$

A unitary theory must have

$$
D^\dagger=D.
$$

Rotations act within each sphere $S^{d-1}$, so they are unitary symmetries of the spatial slice. In the no-explicit-$i$ convention used here,

$$
M_{\mu\nu}^\dagger=-M_{\mu\nu}.
$$

Equivalently, the Hermitian angular momenta are $J_{\mu\nu}=iM_{\mu\nu}$.

The most important relation is

$$
\boxed{
P_\mu^\dagger=K_\mu.
}
$$

There are several ways to see this.

First, $P_\mu$ raises the cylinder energy because

$$
[D,P_\mu]=P_\mu,
$$

while $K_\mu$ lowers it because

$$
[D,K_\mu]=-K_\mu.
$$

In a Hilbert space with a Hermitian Hamiltonian, energy-raising and energy-lowering operators should be adjoints.

Second, inversion exchanges translations and special conformal transformations. A special conformal transformation is precisely

$$
\text{inversion}\circ\text{translation}\circ\text{inversion}.
$$

Since radial Hermitian conjugation includes inversion, it maps $P_\mu$ to $K_\mu$.

Third, on the cylinder, radial reflection sends

$$
\tau\mapsto -\tau.
$$

A generator with $D$-weight $+1$ is reflected into a generator with $D$-weight $-1$. Thus $P_\mu$ and $K_\mu$ are exchanged.

This adjoint relation is the algebraic engine behind unitarity bounds. Norms of descendants are computed by moving every $P_\mu$ from the ket to a $K_\mu$ acting on the bra, and then using the conformal algebra.

## Primary states and descendants revisited

A primary state obeys

$$
K_\mu|\mathcal O\rangle=0,
$$

and

$$
D|\mathcal O\rangle=\Delta|\mathcal O\rangle.
$$

Descendants are obtained by acting with $P_\mu$:

$$
P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle.
$$

Their norms are not arbitrary. They are fixed by the algebra and the norm of the primary.

For a scalar primary, the first descendant has norm

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=
\langle \mathcal O|K_\mu P_\nu|\mathcal O\rangle.
$$

Since

$$
K_\mu|\mathcal O\rangle=0,
$$

we may replace $K_\mu P_\nu$ by the commutator:

$$
\langle \mathcal O|K_\mu P_\nu|\mathcal O\rangle
=
\langle \mathcal O|[K_\mu,P_\nu]|\mathcal O\rangle.
$$

For a scalar primary, $M_{\mu\nu}|\mathcal O\rangle=0$. Therefore

$$
[K_\mu,P_\nu]|\mathcal O\rangle
=
2\delta_{\mu\nu}D|\mathcal O\rangle
=
2\Delta\delta_{\mu\nu}|\mathcal O\rangle.
$$

So

$$
\boxed{
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=
2\Delta\delta_{\mu\nu}\langle \mathcal O|\mathcal O\rangle.
}
$$

If the primary has positive norm, positivity of the first descendants implies

$$
\Delta\geq 0.
$$

This is only the first, weakest scalar constraint. The stronger scalar unitarity bound

$$
\Delta\geq \frac{d-2}{2}
$$

for nontrivial scalar primaries comes from analyzing level-two descendants. That is the subject of the next page. The important lesson here is already visible: unitarity bounds are not mysterious dynamical inequalities. They are positivity of Gram matrices in radial quantization.

## Gram matrices and null states

At each descendant level, one can form a Gram matrix of inner products. For example, at level one above a scalar primary, the descendant basis is

$$
P_\mu|\mathcal O\rangle,
\qquad
\mu=1,\ldots,d.
$$

The Gram matrix is

$$
G_{\mu\nu}^{(1)}
=
\langle \mathcal O|K_\mu P_\nu|\mathcal O\rangle
=
2\Delta\delta_{\mu\nu}\langle\mathcal O|\mathcal O\rangle.
$$

At level two, the natural descendants are

$$
P_\mu P_\nu|\mathcal O\rangle.
$$

They decompose under rotations into symmetric traceless, vector, and scalar pieces, depending on the spin of the primary. Positivity of all these pieces gives sharper bounds.

A **null state** is a nonzero-looking descendant whose norm is zero. In a unitary theory, null states are orthogonal to all states and must be quotiented out. Physically, null states usually signal a shortening condition:

$$
\text{conservation law},
\qquad
\text{equation of motion},
\qquad
\text{gauge redundancy},
\qquad
\text{BPS shortening}.
$$

For example, a conserved current satisfies

$$
\partial^\mu J_\mu=0.
$$

In radial quantization, this means that a particular descendant of $J_\mu$ is null. The stress tensor similarly satisfies

$$
\partial^\mu T_{\mu\nu}=0,
$$

which is a shortening condition for the stress-tensor multiplet.

In AdS/CFT, these shortening conditions are boundary shadows of bulk gauge invariances. A conserved current is dual to a bulk gauge field, and the stress tensor is dual to the graviton.

## BPZ conjugation in two-dimensional CFT

In two-dimensional CFT, radial conjugation is often called **BPZ conjugation**, after Belavin, Polyakov, and Zamolodchikov. On the plane, radial reflection maps

$$
z\mapsto \frac{1}{\bar z},
\qquad
\bar z\mapsto \frac{1}{z}.
$$

For a primary field of weights $(h,\bar h)$, the conjugation rule has the schematic form

$$
\phi(z,\bar z)^\dagger_{\rm rad}
=
\bar z^{-2h}z^{-2\bar h}
\phi^\dagger\left(\frac{1}{\bar z},\frac{1}{z}\right),
$$

with convention-dependent phases for fields with spin. For scalar fields, where $h=\bar h=\Delta/2$, this reduces to

$$
\phi(z,\bar z)^\dagger_{\rm rad}
=
|z|^{-2\Delta}
\phi^\dagger\left(\frac{1}{\bar z},\frac{1}{z}\right).
$$

The Virasoro modes obey

$$
L_n^\dagger=L_{-n},
\qquad
\bar L_n^\dagger=\bar L_{-n}.
$$

This is the two-dimensional version of

$$
P_\mu^\dagger=K_\mu.
$$

Indeed, in two dimensions the global conformal generators are embedded in the Virasoro algebra as

$$
L_{-1},L_0,L_1,
\qquad
\bar L_{-1},\bar L_0,\bar L_1.
$$

The translation generator is represented by $L_{-1}$, and the special conformal generator by $L_1$. The BPZ adjoint relation

$$
L_{-1}^\dagger=L_1
$$

is exactly the same idea.

## Positivity of OPE coefficients

Reflection positivity also explains why unitary conformal block expansions have positive coefficients.

Take a Hermitian scalar primary $\phi$ with two-point function normalized as

$$
\langle \phi(x)\phi(0)\rangle=\frac{1}{|x|^{2\Delta_\phi}}.
$$

Consider the OPE

$$
\phi(x)\phi(0)
\sim
\sum_{\mathcal O}\lambda_{\phi\phi\mathcal O}
|x|^{\Delta_\mathcal O-2\Delta_\phi}
\left(\mathcal O(0)+\text{descendants}\right).
$$

If the exchanged primary basis is orthonormal, then the contribution of each conformal family to the four-point function is proportional to

$$
\lambda_{\phi\phi\mathcal O}^2.
$$

For identical Hermitian scalars in a unitary CFT, these coefficients are nonnegative:

$$
\lambda_{\phi\phi\mathcal O}^2\geq 0.
$$

This positivity is not a decorative detail. It is the reason the numerical conformal bootstrap can turn crossing symmetry into rigorous inequalities. Crossing symmetry alone says that different OPE decompositions agree. Reflection positivity says the coefficients in the decomposition have definite signs.

## Euclidean versus Lorentzian unitarity

Reflection positivity is a Euclidean condition. Lorentzian unitarity is the statement that the Hilbert space has positive norm and that time evolution is unitary.

The bridge between them is analytic continuation. Roughly speaking:

$$
\text{Euclidean reflection positivity}
\quad\Longrightarrow\quad
\text{positive Lorentzian Hilbert space}.
$$

In ordinary Euclidean QFT this is part of the Osterwalder-Schrader reconstruction logic. In CFT, radial quantization gives a particularly geometric realization: the reflection surface is $S^{d-1}$, the Euclidean time is $\tau=\log r$, and the Hamiltonian is $D$.

This is why dimensions of local operators in a unitary CFT are real. They are eigenvalues of a Hermitian operator:

$$
D|\mathcal O\rangle=\Delta|\mathcal O\rangle.
$$

If the theory is unitary, then $D$ has a real spectrum. If the vacuum is the lowest-energy state on the cylinder, then nontrivial operators have nonnegative dimensions, and more detailed descendant positivity gives the familiar unitarity bounds.

## Contact terms and coincident points

The inner product formulas above are cleanest when operator insertions are separated. Coincident points require regularization and contact terms. This is not a failure of the formalism; it is the usual local nature of QFT.

For example, the stress tensor has contact terms in Ward identities. Conserved currents have contact terms when their Ward identity surface crosses charged operators. Composite operators may mix with other operators of the same quantum numbers and dimension.

The radial Hilbert-space prescription avoids most confusion by keeping the reflection surface away from all insertions. One first defines states by insertions strictly inside the unit sphere and bras by reflected insertions strictly outside. Only after the correlator is well-defined should one take limits such as $x\to0$ or $|x|\to\infty$.

This is also good practice in AdS/CFT. Boundary correlators often have contact-term ambiguities, but separated-point correlators and their conformal data are unambiguous.

## AdS/CFT checkpoint

The radial inner product is the CFT-side origin of bulk unitarity.

In global AdS/CFT, the CFT Hilbert space on $S^{d-1}$ is identified with the Hilbert space of quantum gravity in global $\mathrm{AdS}_{d+1}$. The CFT dilatation operator is the global AdS Hamiltonian:

$$
D
\quad\longleftrightarrow\quad
H_{\rm global\ AdS}.
$$

Therefore:

$$
D^\dagger=D
\quad\Longleftrightarrow\quad
\text{real bulk energies},
$$

$$
\langle \Psi|\Psi\rangle_{\rm CFT}\geq0
\quad\Longleftrightarrow\quad
\text{no negative-norm bulk states},
$$

$$
P_\mu^\dagger=K_\mu
\quad\Longleftrightarrow\quad
\text{raising/lowering structure of }SO(d,2)\text{ representations}.
$$

Short multiplets are especially important holographically. A conserved current multiplet has a null descendant and is dual to a bulk gauge field. The stress tensor multiplet is dual to the graviton. In supersymmetric examples, BPS shortening produces protected operator dimensions, which become protected masses or charges in the bulk.

Thus reflection positivity is not a minor Euclidean axiom. It is the boundary consistency condition behind a healthy bulk Hilbert space.

## Summary

Radial quantization defines the CFT Hilbert space on $S^{d-1}$. The inner product is obtained by reflecting ket insertions through the unit sphere and evaluating the resulting Euclidean correlator:

$$
\langle \Psi_{\mathcal A}|\Psi_{\mathcal B}\rangle
=
\langle \Theta\mathcal A\,\mathcal B\rangle.
$$

For scalar primaries,

$$
\Theta\mathcal O(x)
=
|x|^{-2\Delta}\mathcal O^\dagger\left(\frac{x}{x^2}\right).
$$

For spinning primaries, inversion tensors act on the indices. The conformal generators obey

$$
D^\dagger=D,
\qquad
P_\mu^\dagger=K_\mu,
\qquad
M_{\mu\nu}^\dagger=-M_{\mu\nu}
$$

in the no-explicit-$i$ convention. Reflection positivity implies positive Gram matrices of states and descendants. These positivity constraints lead directly to unitarity bounds and to positive conformal block coefficients.

For AdS/CFT, this structure is indispensable: it is how the CFT knows about a positive-norm bulk Hilbert space and real global AdS energies.

## Exercises

### Exercise 1 — Radial conjugation of a scalar primary

Let $\mathcal O$ be a Hermitian scalar primary of dimension $\Delta$. Show that the radial conjugate of $\mathcal O(x)$ is

$$
\Theta\mathcal O(x)
=
|x|^{-2\Delta}\mathcal O\left(\frac{x}{x^2}\right).
$$

Explain why the factor $|x|^{-2\Delta}$ is needed.

<details><summary><strong>Solution</strong></summary>

Radial reflection sends

$$
R x^\mu=\frac{x^\mu}{x^2}.
$$

This is a conformal transformation. Its local scale factor is

$$
ds'^2=\frac{ds^2}{|x|^4}.
$$

Thus the Weyl factor is

$$
\Omega(x)=\frac{1}{|x|^2}.
$$

A scalar primary of dimension $\Delta$ transforms with a factor $\Omega(x)^\Delta$, so inversion gives

$$
\mathcal O(x)
\mapsto
|x|^{-2\Delta}\mathcal O(Rx).
$$

Hermitian conjugation also complex-conjugates the operator. If $\mathcal O$ is Hermitian, then $\mathcal O^\dagger=\mathcal O$, and therefore

$$
\Theta\mathcal O(x)
=
|x|^{-2\Delta}\mathcal O\left(\frac{x}{x^2}\right).
$$

The factor $|x|^{-2\Delta}$ is required because inversion is not an isometry of flat space. It is a conformal transformation with a position-dependent scale factor.

</details>

### Exercise 2 — Bra state from an insertion at infinity

Starting from

$$
|\mathcal O\rangle=\mathcal O(0)|0\rangle,
$$

show that the conjugate bra is

$$
\langle \mathcal O|
=
\lim_{|x|\to\infty}|x|^{2\Delta}\langle 0|\mathcal O^\dagger(x).
$$

Then compute $\langle\mathcal O|\mathcal O\rangle$ if

$$
\langle \mathcal O^\dagger(x)\mathcal O(0)\rangle
=
\frac{C_{\mathcal O}}{|x|^{2\Delta}}.
$$

<details><summary><strong>Solution</strong></summary>

The ket insertion at the origin is reflected to infinity by radial conjugation. For a scalar primary, the correct finite bra is obtained by multiplying the large-$|x|$ insertion by $|x|^{2\Delta}$:

$$
\langle \mathcal O|
=
\lim_{|x|\to\infty}|x|^{2\Delta}\langle 0|\mathcal O^\dagger(x).
$$

Now compute the norm:

$$
\langle\mathcal O|\mathcal O\rangle
=
\lim_{|x|\to\infty}|x|^{2\Delta}
\langle \mathcal O^\dagger(x)\mathcal O(0)\rangle.
$$

Using the two-point function,

$$
\langle\mathcal O|\mathcal O\rangle
=
\lim_{|x|\to\infty}|x|^{2\Delta}
\frac{C_{\mathcal O}}{|x|^{2\Delta}}
=
C_{\mathcal O}.
$$

Thus choosing $C_{\mathcal O}=1$ gives a unit-normalized primary state.

</details>

### Exercise 3 — Why $P_\mu^\dagger=K_\mu$

Use the radial reflection $\tau\mapsto-\tau$ and the commutators

$$
[D,P_\mu]=P_\mu,
\qquad
[D,K_\mu]=-K_\mu
$$

to explain why $P_\mu$ and $K_\mu$ must be adjoints in radial quantization.

<details><summary><strong>Solution</strong></summary>

The operator $D$ is the cylinder Hamiltonian:

$$
H_{\rm cyl}=D.
$$

The commutator

$$
[D,P_\mu]=P_\mu
$$

means that $P_\mu$ raises the cylinder energy by one unit. If

$$
D|\psi\rangle=E|\psi\rangle,
$$

then

$$
D(P_\mu|\psi\rangle)=(E+1)P_\mu|\psi\rangle.
$$

Similarly,

$$
[D,K_\mu]=-K_\mu
$$

means that $K_\mu$ lowers the cylinder energy by one unit.

Hermitian conjugation in Euclidean time reverses time. In radial quantization, Euclidean time reversal is

$$
\tau\mapsto-\tau.
$$

Therefore an energy-raising operator is reflected into an energy-lowering operator. Since $P_\mu$ raises and $K_\mu$ lowers, radial Hermitian conjugation identifies them:

$$
P_\mu^\dagger=K_\mu.
$$

</details>

### Exercise 4 — Level-one norm of a scalar descendant

Let $|\mathcal O\rangle$ be a scalar primary with

$$
D|\mathcal O\rangle=\Delta|\mathcal O\rangle,
\qquad
K_\mu|\mathcal O\rangle=0,
\qquad
M_{\mu\nu}|\mathcal O\rangle=0.
$$

Using

$$
[K_\mu,P_\nu]=2\delta_{\mu\nu}D-2M_{\mu\nu},
$$

show that

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=
2\Delta\delta_{\mu\nu}\langle\mathcal O|\mathcal O\rangle.
$$

<details><summary><strong>Solution</strong></summary>

By radial conjugation,

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=
\langle \mathcal O|K_\mu P_\nu|\mathcal O\rangle.
$$

Because $K_\mu|\mathcal O\rangle=0$, we can write

$$
K_\mu P_\nu|\mathcal O\rangle
=
[K_\mu,P_\nu]|\mathcal O\rangle.
$$

Use the commutator:

$$
[K_\mu,P_\nu]|\mathcal O\rangle
=
(2\delta_{\mu\nu}D-2M_{\mu\nu})|\mathcal O\rangle.
$$

For a scalar primary,

$$
M_{\mu\nu}|\mathcal O\rangle=0,
$$

and

$$
D|\mathcal O\rangle=\Delta|\mathcal O\rangle.
$$

Therefore

$$
[K_\mu,P_\nu]|\mathcal O\rangle
=
2\Delta\delta_{\mu\nu}|\mathcal O\rangle.
$$

Substituting back,

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=
2\Delta\delta_{\mu\nu}\langle\mathcal O|\mathcal O\rangle.
$$

</details>

### Exercise 5 — Positivity of a two-operator Gram matrix

Let $\mathcal O_1$ and $\mathcal O_2$ be scalar primaries with the same dimension and the same global quantum numbers. Suppose their two-point functions are

$$
\langle \mathcal O_i^\dagger(x)\mathcal O_j(0)\rangle
=
\frac{C_{ij}}{|x|^{2\Delta}}.
$$

Use reflection positivity to show that the matrix $C_{ij}$ must be positive semidefinite.

<details><summary><strong>Solution</strong></summary>

Consider the state

$$
|\Psi\rangle
=
(c_1\mathcal O_1(0)+c_2\mathcal O_2(0))|0\rangle.
$$

Its norm is

$$
\langle\Psi|\Psi\rangle
=
\sum_{i,j}\overline{c_i}c_j\langle\mathcal O_i|\mathcal O_j\rangle.
$$

The radial inner product gives

$$
\langle\mathcal O_i|\mathcal O_j\rangle=C_{ij}.
$$

Therefore

$$
\langle\Psi|\Psi\rangle
=
\sum_{i,j}\overline{c_i}C_{ij}c_j.
$$

Reflection positivity says that this must be nonnegative for all complex coefficients $c_i$:

$$
\sum_{i,j}\overline{c_i}C_{ij}c_j\geq0.
$$

That is exactly the statement that $C_{ij}$ is positive semidefinite.

</details>

## Further reading

For two-dimensional BPZ conjugation and radial quantization, see Di Francesco, Mathieu, and Sénéchal, Chapter 6. For higher-dimensional radial quantization, reflection positivity, and unitarity bounds, see Rychkov’s CFT lectures and Simmons-Duffin’s TASI lectures. For AdS/CFT, the essential point to retain is $D^\dagger=D$ and $P_\mu^\dagger=K_\mu$: these are the boundary representation-theory statements behind positive bulk energy and the raising/lowering structure of global AdS states.
