---
title: "CFT Data: Spectrum and OPE Coefficients"
description: "The intrinsic data of a conformal field theory: primary spectrum, OPE coefficients, Ward identities, crossing, unitarity, and the AdS/CFT interpretation."
sidebar:
  order: 4
---

## Goal

The previous pages explained how CFTs arise as fixed points of RG flow. We now describe what a CFT is **once we have arrived at the fixed point**.

A generic quantum field theory is often introduced by a Lagrangian. A CFT is more cleanly described by its **operator algebra**. The central claim of this page is:

$$
\boxed{
\text{A CFT is specified by its local operator spectrum and OPE coefficients, subject to consistency.}
}
$$

This is the language of the conformal bootstrap. It is also the language that AdS/CFT uses most directly. Bulk fields, particle masses, cubic couplings, Newton's constant, gauge couplings, and locality diagnostics are encoded in boundary CFT data.

The goal of this page is to make the phrase “CFT data” precise enough that, when the holographic dictionary appears later, it will feel like a translation rather than a magic trick.

## The operator-algebra viewpoint

Let $\mathcal O_i(x)$ denote local operators in a $d$-dimensional CFT. A first-pass description of the data is

$$
\mathcal D_{\rm CFT}
=
\left\{
\mathcal O_i,
\Delta_i,
\ell_i,
\mathcal R_i,
\lambda_{ijk},
\text{Ward/anomaly data}
\right\}.
$$

Here $\Delta_i$ is the scaling dimension of $\mathcal O_i$, $\ell_i$ denotes its spin or Lorentz representation, $\mathcal R_i$ denotes its representation under global symmetries, and $\lambda_{ijk}$ are OPE coefficients. For spinning operators, $\lambda_{ijk}$ usually means a finite list of coefficients multiplying the allowed tensor structures.

In a fixed normalization convention, much of the Ward data can be viewed as special OPE data involving conserved currents and the stress tensor. We nevertheless list it separately because $T_{\mu\nu}$ and $J_\mu$ are not generic operators: they generate spacetime and global symmetries.

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 55rem;">

![The CFT data package](/figures/cft/cft-data-package.svg)

<figcaption>

The basic CFT data consists of the primary spectrum $\mathcal O_i:(\Delta_i,\ell_i,\mathcal R_i)$, OPE coefficients $\lambda_{ijk}$, and symmetry data such as $T_{\mu\nu}$, conserved currents, and normalization constants $C_T,C_J$. This data reconstructs separated-point correlators and relevant deformations, and it becomes the input for the AdS dictionary. Not every formal choice of numbers is allowed: unitarity, locality, Ward identities, and crossing symmetry impose strong consistency conditions.

</figcaption>
</figure>

The figure is not a definition by itself, but it captures the workflow of modern CFT. The theory is not primarily a list of fields in a Lagrangian. It is a consistent algebra of local observables.

## Local operators and conformal primaries

A CFT has infinitely many local operators. Even a free scalar theory contains

$$
\phi,
\qquad
\partial_\mu\phi,
\qquad
\phi^2,
\qquad
\phi\partial_\mu\phi,
\qquad
(\partial\phi)^2,
\qquad
\ldots
$$

The conformal symmetry organizes these operators into families. Each family starts from a **primary operator**. Descendants are obtained by acting with translations, equivalently derivatives:

$$
\mathcal O_i,
\qquad
\partial_\mu\mathcal O_i,
\qquad
\partial_\mu\partial_\nu\mathcal O_i,
\qquad
\ldots
$$

The primary is the irreducible seed. Descendants are not independent CFT data: their correlation functions are fixed by conformal symmetry once the primary data are known.

Thus the spectrum means the list

$$
\boxed{
\text{spectrum}
=
\left\{
\mathcal O_i\ \text{primary}:
\Delta_i,
\ell_i,
\mathcal R_i
\right\}.
}
$$

There are always some special entries:

$$
\mathbf 1,
\qquad
T_{\mu\nu},
\qquad
J_\mu^a\quad\text{if the CFT has a continuous global symmetry}.
$$

The identity operator has

$$
\Delta_{\mathbf 1}=0.
$$

The stress tensor has

$$
\Delta_T=d,
\qquad
\ell_T=2,
$$

and a conserved current has

$$
\Delta_J=d-1,
\qquad
\ell_J=1.
$$

These dimensions are exact because conservation equations shorten the conformal multiplets:

$$
\partial^\mu T_{\mu\nu}=0,
\qquad
\partial^\mu J_\mu^a=0.
$$

Shortening is one of the cleanest ways symmetry protects operator dimensions.

## Scaling dimensions are physical observables

At an RG fixed point, a scalar local operator has a definite response to scale transformations:

$$
\mathcal O_i(\lambda x)
=
\lambda^{-\Delta_i}\mathcal O_i(x)
$$

up to possible mixing among degenerate operators. The number $\Delta_i$ controls power laws. With the common scalar normalization

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{\delta_{ij}}{|x|^{2\Delta_i}},
$$

we can read $\Delta_i$ directly from the falloff of the two-point function.

This is why anomalous dimensions are not a secondary detail in modern CFT. The full scaling dimension is the observable:

$$
\Delta_i
=
\Delta_i^{\rm classical}+\gamma_i.
$$

At an interacting fixed point, $\gamma_i$ is generally part of the nonperturbative data of the theory.

## Deformations are encoded by CFT data

The RG relevance of a deformation is determined by the dimension of the operator being added to the CFT action:

$$
S
\mapsto
S+g_i\int d^d x\,\mathcal O_i(x).
$$

Since the action is dimensionless, the coupling has dimension

$$
[g_i]=d-\Delta_i.
$$

Therefore:

$$
\boxed{
\begin{array}{ccl}
\Delta_i<d &\Longleftrightarrow& \mathcal O_i\ \text{is relevant},\\
\Delta_i=d &\Longleftrightarrow& \mathcal O_i\ \text{is classically marginal},\\
\Delta_i>d &\Longleftrightarrow& \mathcal O_i\ \text{is irrelevant}.
\end{array}
}
$$

At the Ising fixed point, the continuum description near criticality has the schematic form

$$
S
=
S_{\rm Ising\ CFT}
+t\int d^d x\,\epsilon(x)
+h\int d^d x\,\sigma(x)
+\cdots.
$$

The operators $\epsilon$ and $\sigma$ are relevant if

$$
\Delta_\epsilon<d,
\qquad
\Delta_\sigma<d.
$$

The correlation-length exponent $\nu$ is related to $\Delta_\epsilon$ by

$$
\boxed{
\Delta_\epsilon=d-\frac{1}{\nu}.
}
$$

The reason is that the temperature-like coupling $t$ has RG eigenvalue $y_t=1/\nu$, while a coupling to an operator of dimension $\Delta$ has RG eigenvalue

$$
y=d-\Delta.
$$

Similarly, the critical exponent $\eta$ is related to the spin-field dimension by

$$
\boxed{
\Delta_\sigma=\frac{d-2+\eta}{2}.
}
$$

This is a good example of the CFT viewpoint replacing critical exponents by operator dimensions.

## Two-point functions and normalization

For scalar primaries in a unitary CFT, one often chooses an orthonormal basis such that

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{\delta_{ij}}{|x|^{2\Delta_i}}.
$$

This convention is useful, but it is not mandatory. If we rescale an operator by

$$
\mathcal O_i\mapsto a_i\mathcal O_i,
$$

then its two-point function and OPE coefficients change. The raw numerical value of $\lambda_{ijk}$ is meaningful only after normalization conventions are fixed.

For spinning operators, the two-point function also contains tensor structures. A conserved current has the schematic form

$$
\langle J_\mu^a(x)J_\nu^b(0)\rangle
=
\frac{C_J\delta^{ab}}{|x|^{2(d-1)}}
\left(
\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}
\right),
$$

up to convention-dependent overall factors.

The stress-tensor two-point function is similarly fixed up to one number, usually called $C_T$:

$$
\langle T_{\mu\nu}(x)T_{\rho\sigma}(0)\rangle
=
\frac{C_T}{|x|^{2d}}
\mathcal I_{\mu\nu,\rho\sigma}(x),
$$

where $\mathcal I_{\mu\nu,\rho\sigma}(x)$ is fixed by conformal symmetry, conservation, and tracelessness.

The coefficient $C_T$ is an important measure of degrees of freedom. In holographic CFTs with an Einstein-like gravity dual, it scales as

$$
C_T\sim \frac{R_{\rm AdS}^{d-1}}{G_N},
$$

up to a convention-dependent numerical factor.

## Three-point functions and OPE coefficients

For scalar primaries, conformal symmetry fixes the position dependence of the three-point function:

$$
\langle
\mathcal O_i(x_1)
\mathcal O_j(x_2)
\mathcal O_k(x_3)
\rangle
=
\frac{\lambda_{ijk}}
{|x_{12}|^{\Delta_i+\Delta_j-\Delta_k}
 |x_{23}|^{\Delta_j+\Delta_k-\Delta_i}
 |x_{13}|^{\Delta_i+\Delta_k-\Delta_j}},
$$

where

$$
x_{ij}=x_i-x_j.
$$

The number $\lambda_{ijk}$ is genuine dynamical data. Symmetry fixes the shape; dynamics fixes the coefficient.

For spinning operators, there can be several independent tensor structures. Then one writes schematically

$$
\langle \mathcal O_i\mathcal O_j\mathcal O_k\rangle
=
\sum_a \lambda_{ijk}^{(a)}\,\mathcal T_{ijk}^{(a)}(x_1,x_2,x_3),
$$

where the allowed structures $\mathcal T_{ijk}^{(a)}$ are fixed by conformal symmetry, spin, parity, and global symmetry, while the coefficients $\lambda_{ijk}^{(a)}$ are CFT data.

## The OPE as a multiplication table

The operator product expansion says that when two local operators approach each other, their product can be expanded in local operators at one point:

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k
\lambda_{ij}^{\ \ k}\,
\frac{1}{|x|^{\Delta_i+\Delta_j-\Delta_k}}
\left(\mathcal O_k(0)+\text{descendants}\right).
$$

This formula is schematic. The precise expression includes spin-dependent tensor structures and differential operators acting on descendants. The crucial point is that the descendant terms are fixed by conformal symmetry once the primary operator $\mathcal O_k$ and coefficient $\lambda_{ij}^{\ \ k}$ are known.

Thus the primary OPE coefficients are the multiplication constants of the CFT operator algebra:

$$
\boxed{
\mathcal O_i\times \mathcal O_j
=\sum_k \lambda_{ij}^{\ \ k}\mathcal O_k.
}
$$

The identity contribution is especially important. In an orthonormal scalar basis,

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\frac{\delta_{ij}}{|x|^{2\Delta_i}}\mathbf 1+\cdots.
$$

Taking the vacuum expectation value reproduces the two-point function.

The OPE is not merely a vague asymptotic expansion. In Euclidean CFT, radial quantization gives a powerful reason for its convergence inside correlation functions whenever one operator insertion is closer to another than to the rest. This convergence property is what makes the bootstrap precise.

## All correlators from CFT data

Suppose we know the full spectrum and all OPE coefficients. Then, in principle, we can compute any local correlation function by repeatedly applying the OPE.

For a four-point function,

$$
\langle
\mathcal O_1(x_1)
\mathcal O_2(x_2)
\mathcal O_3(x_3)
\mathcal O_4(x_4)
\rangle,
$$

we can first fuse $\mathcal O_1\mathcal O_2$:

$$
\mathcal O_1\times\mathcal O_2
\sim
\sum_k \lambda_{12k}\mathcal O_k.
$$

The four-point function becomes a sum over conformal families:

$$
\langle 1234\rangle
=
\sum_k \lambda_{12k}\lambda_{34k}\,G_k^{(12)(34)}(x_i),
$$

where $G_k^{(12)(34)}$ is a conformal block. The block is fixed by symmetry. The coefficients and exchanged dimensions are the dynamical data.

But we could also fuse $\mathcal O_1\mathcal O_4$ or $\mathcal O_1\mathcal O_3$. Equality of the different decompositions is crossing symmetry. Schematically,

$$
\sum_k \lambda_{12k}\lambda_{34k}\,G_k^{(12)(34)}
=
\sum_k \lambda_{14k}\lambda_{23k}\,G_k^{(14)(23)}.
$$

This is the bootstrap equation. It says that the OPE must be associative.

## Consistency conditions

Not every formal list of dimensions and OPE coefficients defines a CFT. The data must satisfy strong consistency conditions.

The most important are:

1. **Conformal symmetry.** Correlators must transform correctly under the conformal group.
2. **OPE associativity.** Different OPE channels of the same correlator must agree.
3. **Unitarity or reflection positivity.** In Euclidean signature, inner products obtained by reflection must be positive.
4. **Locality.** Operator products must have the correct permutation and monodromy properties.
5. **Ward identities.** Correlators involving $T_{\mu\nu}$ and $J_\mu$ must implement spacetime and global symmetries.
6. **Anomaly matching.** If the theory has 't Hooft anomalies or Weyl anomalies, they must be consistently represented in correlation functions and background-source dependence.

The conformal bootstrap takes this seriously: it studies the space of all possible CFT data obeying these constraints.

## Special role of the stress tensor

The stress tensor is both an operator and a generator of symmetry. Its correlation functions encode universal information.

The Ward identity for translations schematically says

$$
\partial^\mu T_{\mu\nu}=0
$$

away from operator insertions, with contact terms at insertions. Those contact terms tell us that $T_{\mu\nu}$ generates translations of local operators.

Likewise, the trace condition

$$
T^\mu{}_{\mu}=0
$$

is the flat-space statement of conformal invariance, up to anomalies and contact terms.

The stress-tensor OPE with a scalar primary has the schematic form

$$
T_{\mu\nu}(x)\mathcal O(0)
\sim
\text{singular terms fixed by }\Delta_{\mathcal O}\text{ and spin}.
$$

The detailed tensor expression will come later. For now the key lesson is this: once $T_{\mu\nu}$ is part of the CFT data, its Ward identities know the dimensions and spins of all local operators.

## Global symmetries and charged operators

If the CFT has a global symmetry group $G$, local operators fall into representations of $G$:

$$
\mathcal O_i\in \mathcal R_i.
$$

The OPE must respect symmetry selection rules. If

$$
\mathcal O_i\in\mathcal R_i,
\qquad
\mathcal O_j\in\mathcal R_j,
$$

then only operators in representations contained in the tensor product may appear:

$$
\mathcal R_k\subset \mathcal R_i\otimes\mathcal R_j.
$$

For example, if a theory has a $\mathbb Z_2$ symmetry and $\sigma$ is odd while $\epsilon$ is even, then

$$
\sigma\times\sigma
\sim
\mathbf 1+\epsilon+\text{even operators},
$$

while

$$
\sigma\times\epsilon
\sim
\sigma+\text{odd operators}.
$$

This is how symmetry reduces the space of possible OPEs.

Continuous global symmetries come with conserved currents $J_\mu^a$. Their Ward identities determine how charged operators transform. Their two-point coefficient $C_J$ is a CFT observable and, in holography, is related to the bulk gauge coupling.

## Large-$N$ CFT data

For AdS/CFT, an especially important class of CFTs has a large parameter $N$ and a sparse low-dimension spectrum. The basic pattern is

$$
\langle \mathcal O_1\mathcal O_2\rangle=O(1),
$$

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle_{\rm conn}=O(N^{-1})
$$

for suitably normalized single-trace operators in a gauge-theory-like large-$N$ limit. Connected $n$-point functions are suppressed by powers of $1/N$.

This factorization makes the boundary theory look like a weakly coupled bulk theory. A single-trace primary corresponds to a single-particle bulk field. Multi-trace operators correspond to multi-particle states.

The CFT data then have a bulk interpretation:

$$
\boxed{
\begin{array}{ccl}
\text{primary operator }\mathcal O_i &\longleftrightarrow& \text{bulk field }\phi_i,\\
\Delta_i &\longleftrightarrow& \text{bulk mass},\\
\ell_i &\longleftrightarrow& \text{bulk spin},\\
\lambda_{ijk} &\longleftrightarrow& \text{bulk cubic coupling},\\
C_T &\longleftrightarrow& R_{\rm AdS}^{d-1}/G_N.
\end{array}
}
$$

For a scalar field in AdS$_{d+1}$, the mass-dimension relation is

$$
\boxed{
 m^2R_{\rm AdS}^2=\Delta(\Delta-d).
}
$$

This is the first hard dictionary entry. The boundary scaling dimension is the bulk mass in AdS units.

## CFT data in two dimensions

Two-dimensional CFT has extra structure because local conformal transformations form two copies of the Virasoro algebra. The spectrum is often organized by left and right conformal weights:

$$
(h,\bar h),
\qquad
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

The stress tensor splits into holomorphic and antiholomorphic components:

$$
T(z),
\qquad
\bar T(\bar z),
$$

with central charges

$$
c,
\qquad
\bar c.
$$

In rational CFT, the number of primary fields under an extended chiral algebra can be finite. Then additional data such as fusion rules, modular $S$ and $T$ matrices, and torus partition functions become central.

For this AdS/CFT-oriented course, two-dimensional CFT is important for three reasons. It gives exact examples where the operator-algebra philosophy can be solved completely. It is the worldsheet language of perturbative string theory. And it is the boundary language of AdS$_3$/CFT$_2$, where Virasoro symmetry and modular invariance are exceptionally powerful.

But the general idea remains the same: the theory is specified by spectra, operator products, symmetries, and consistency.

## Examples

The two-dimensional Ising CFT has three Virasoro primaries:

$$
\mathbf 1,
\qquad
\sigma,
\qquad
\epsilon,
$$

with

$$
\Delta_{\mathbf 1}=0,
\qquad
\Delta_\sigma=\frac18,
\qquad
\Delta_\epsilon=1,
$$

and central charge

$$
c=\frac12.
$$

The fusion rules are

$$
\sigma\times\sigma=\mathbf 1+\epsilon,
$$

$$
\sigma\times\epsilon=\sigma,
$$

$$
\epsilon\times\epsilon=\mathbf 1.
$$

Together with OPE coefficients and Virasoro symmetry, this data determines the local correlators of the model.

The canonical AdS/CFT example is four-dimensional $\mathcal N=4$ super-Yang-Mills theory. Its CFT data depend on $N$ and the exactly marginal 't Hooft coupling

$$
\lambda=g_{\rm YM}^2N.
$$

Protected BPS operators have dimensions fixed by representation theory. Unprotected operators have dimensions that depend on $\lambda$. At large $N$ and large $\lambda$, the data organize into weakly curved type IIB string theory on

$$
AdS_5\times S^5.
$$

## What is not independent data?

It is useful to separate independent data from derived data.

Descendants are not independent once primary data are known. Their dimensions are fixed:

$$
\Delta_{\partial^n\mathcal O}=\Delta_{\mathcal O}+n.
$$

Their OPE contributions are fixed by conformal symmetry in terms of primary OPE coefficients.

Two- and three-point coordinate dependence is not independent. Conformal symmetry fixes it, up to finite sets of constants and tensor structures.

Many Ward-identity coefficients are not independent. The stress tensor generates translations and conformal transformations, so its coupling to operators is constrained by their dimensions and spins.

The microscopic regulator is not CFT data. Two different lattice models may have the same continuum CFT data. Conversely, the same CFT may admit several different UV descriptions.

The Lagrangian is not fundamental CFT data either. It may be a beautiful and useful way of defining the theory, but the CFT itself is the equivalence class of local correlation functions satisfying the conformal axioms and consistency conditions.

## AdS/CFT checkpoint

The CFT data are the boundary form of the bulk theory:

$$
\boxed{
\begin{array}{ccl}
\mathcal O_i &\longleftrightarrow& \phi_i,\\
\Delta_i &\longleftrightarrow& m_i^2R_{\rm AdS}^2,\\
\ell_i &\longleftrightarrow& \text{bulk spin},\\
\lambda_{ijk} &\longleftrightarrow& \text{bulk interaction},\\
T_{\mu\nu} &\longleftrightarrow& g_{MN},\\
J_\mu^a &\longleftrightarrow& A_M^a.
\end{array}
}
$$

This is the conceptual transition from RG fixed points to holography: the boundary CFT data are the nonperturbative definition of the AdS quantum gravity theory.

## Common pitfalls

**Pitfall 1: thinking the spectrum alone defines the CFT.** The spectrum is not enough. Two theories can have the same operator dimensions but different OPE coefficients. Dynamics lives in the OPE.

**Pitfall 2: forgetting normalization conventions.** Numbers like $\lambda_{ijk}$ depend on the normalization of operators. Before comparing OPE coefficients, fix the two-point functions.

**Pitfall 3: treating descendants as independent.** Descendants are part of conformal multiplets. Once a primary and its OPE coefficient are known, conformal symmetry fixes the descendant contributions to conformal blocks.

**Pitfall 4: assuming all marginal operators are exactly marginal.** An operator with $\Delta=d$ is marginal at the fixed point. It may be marginally relevant or marginally irrelevant once conformal perturbation theory is included. Exactly marginal operators are special and generate conformal manifolds.

**Pitfall 5: confusing boundary global symmetry with bulk global symmetry.** In AdS/CFT, a global symmetry of the boundary CFT corresponds to a gauge symmetry in the bulk. The CFT current $J_\mu$ is dual to a bulk gauge field.

## Summary

A CFT is most efficiently specified by its operator algebra. The basic data are

$$
\boxed{
\text{spectrum of primaries }(\Delta_i,\ell_i,\mathcal R_i)
\quad\text{and}\quad
\text{OPE coefficients }\lambda_{ijk}^{(a)}.
}
$$

Two-point functions define the operator metric. Three-point coefficients define the OPE. Higher-point functions are reconstructed by repeated OPEs and decomposed into conformal blocks:

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\sum_{\mathcal O}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}G_{\mathcal O}(u,v).
$$

Different OPE channels must agree. This is crossing symmetry, or associativity of the operator algebra.

For AdS/CFT, the same data are bulk physics:

$$
\Delta\leftrightarrow m^2R_{\rm AdS}^2,
\qquad
\lambda_{ijk}\leftrightarrow \text{bulk couplings},
\qquad
C_T\leftrightarrow \frac{R_{\rm AdS}^{d-1}}{G_N}.
$$

The next module begins the systematic study of conformal symmetry in $d$ dimensions. We will derive the conformal group, its generators, and its relationship to the isometry group of AdS.

## Exercises

### Exercise 1: Dimension of a coupling

Let $\mathcal O$ be a scalar primary of dimension $\Delta$, and deform the CFT by

$$
\delta S=\lambda\int d^d x\,\mathcal O(x).
$$

Find the engineering dimension of $\lambda$ and classify the deformation as relevant, marginal, or irrelevant.

<details><summary><strong>Solution</strong></summary>

The action is dimensionless. Since

$$
[d^d x]=-d,
\qquad
[\mathcal O]=\Delta,
$$

the coupling must have dimension

$$
[\lambda]=d-\Delta.
$$

Therefore $\Delta<d$ is relevant, $\Delta=d$ is marginal, and $\Delta>d$ is irrelevant.

</details>

### Exercise 2: Identity term in the OPE

Suppose a scalar primary is normalized by

$$
\langle \mathcal O(x)\mathcal O(0)\rangle=\frac1{|x|^{2\Delta}}.
$$

Show that the identity contribution in the OPE must be

$$
\mathcal O(x)\mathcal O(0)\sim \frac1{|x|^{2\Delta}}\mathbf 1+\cdots.
$$

<details><summary><strong>Solution</strong></summary>

Take the vacuum expectation value of the OPE. Since $\langle \mathbf 1\rangle=1$, and one-point functions of non-identity primaries vanish in flat space when not allowed by symmetries, the leading identity term must reproduce the two-point function:

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
\sim
\frac1{|x|^{2\Delta}}\langle \mathbf 1\rangle
=
\frac1{|x|^{2\Delta}}.
$$

Thus the identity coefficient is fixed by the two-point normalization.

</details>

### Exercise 3: OPE coefficient from a three-point function

Assume scalar primaries are orthonormal:

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{\delta_{ij}}{|x|^{2\Delta_i}}.
$$

Use the OPE

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\lambda_{ij}^{\ \ k}|x|^{\Delta_k-\Delta_i-\Delta_j}\mathcal O_k(0)+\cdots
$$

to recover the leading $x\to0$ behavior of

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\mathcal O_k(y)\rangle,
\qquad
|x|\ll |y|.
$$

<details><summary><strong>Solution</strong></summary>

Insert the OPE into the three-point function:

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\mathcal O_k(y)\rangle
\sim
\sum_\ell \lambda_{ij}^{\ \ \ell}|x|^{\Delta_\ell-\Delta_i-\Delta_j}
\langle \mathcal O_\ell(0)\mathcal O_k(y)\rangle.
$$

Using orthonormality,

$$
\langle \mathcal O_\ell(0)\mathcal O_k(y)\rangle
=
\frac{\delta_{\ell k}}{|y|^{2\Delta_k}}.
$$

Thus

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\mathcal O_k(y)\rangle
\sim
\lambda_{ij}^{\ \ k}
\frac{|x|^{\Delta_k-\Delta_i-\Delta_j}}{|y|^{2\Delta_k}}.
$$

This matches the short-distance limit of the conformal three-point function.

</details>

### Exercise 4: Crossing for identical scalars

For identical scalar primaries $\phi$ of dimension $\Delta_\phi$, define

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{|x_{12}|^{2\Delta_\phi}|x_{34}|^{2\Delta_\phi}}\mathcal G(u,v).
$$

Show that exchanging $x_1\leftrightarrow x_3$ implies

$$
v^{\Delta_\phi}\mathcal G(u,v)
=
u^{\Delta_\phi}\mathcal G(v,u).
$$

<details><summary><strong>Solution</strong></summary>

Under $x_1\leftrightarrow x_3$, the cross-ratios exchange:

$$
u\mapsto v,
\qquad
v\mapsto u.
$$

The same four-point function can be written as

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{|x_{23}|^{2\Delta_\phi}|x_{14}|^{2\Delta_\phi}}\mathcal G(v,u).
$$

Equating this with the original expression gives

$$
\mathcal G(u,v)=\left(\frac{u}{v}\right)^{\Delta_\phi}\mathcal G(v,u),
$$

or equivalently

$$
v^{\Delta_\phi}\mathcal G(u,v)
=
u^{\Delta_\phi}\mathcal G(v,u).
$$

</details>

### Exercise 5: Scalar mass in AdS

A scalar primary in a $d$-dimensional CFT is dual to a scalar field in AdS$_{d+1}$ with

$$
 m^2R^2=\Delta(\Delta-d).
$$

For which range of $\Delta$ is $m^2<0$? Does a negative $m^2$ automatically mean an instability?

<details><summary><strong>Solution</strong></summary>

The product $\Delta(\Delta-d)$ is negative when

$$
0<\Delta<d.
$$

So scalar operators with dimensions in this range correspond to bulk scalars with negative mass squared.

A negative $m^2$ in AdS does not automatically imply an instability. AdS has the Breitenlohner-Freedman stability bound

$$
 m^2R^2\ge -\frac{d^2}{4}.
$$

Using

$$
 m^2R^2=\Delta(\Delta-d)
=\left(\Delta-\frac d2\right)^2-\frac{d^2}{4},
$$

we see that any real $\Delta$ automatically satisfies the bound. The minimum occurs at $\Delta=d/2$.

</details>
