---
title: "Lie Algebras for CFT"
description: "A compact reference for Lie algebras, roots, weights, Dynkin labels, Casimirs, affine current algebras, and the representation theory used throughout CFT and AdS/CFT."
sidebar:
  order: 2
---

Lie algebras appear in CFT in three different ways, and it is useful not to mix them up.

First, there is the **spacetime symmetry algebra**. In a $d$-dimensional Euclidean CFT this is $\mathfrak{so}(d+1,1)$; in Lorentzian signature it is $\mathfrak{so}(d,2)$. Its representations classify local operators by scaling dimension and spin.

Second, there are **internal global symmetries**. These include ordinary flavor symmetries, $R$-symmetries in supersymmetric theories, and discrete symmetries when present. Their Lie algebras label multiplets of local operators. In AdS/CFT, these global symmetries become gauge symmetries in the bulk.

Third, in two-dimensional CFT there are **current algebras**. A conserved holomorphic current $J^a(z)$ does not merely generate a finite-dimensional Lie algebra $\mathfrak g$; its modes generate the affine algebra $\widehat{\mathfrak g}_k$. This is the algebraic engine behind WZW models, Sugawara stress tensors, KZ equations, rational CFT, and many worldsheet descriptions of strings.

This appendix is a working reference. It is not a full course on Lie theory. Its goal is to make the representation labels, normalizations, and formulas used in CFT and AdS/CFT immediately readable.

## Basic conventions

A finite-dimensional Lie algebra $\mathfrak g$ is a vector space with a bilinear antisymmetric bracket

$$
[X,Y]=-[Y,X]
$$

obeying the Jacobi identity

$$
[X,[Y,Z]]+[Y,[Z,X]]+[Z,[X,Y]]=0.
$$

Choose a basis $T^a$ of $\mathfrak g$. In a physics convention for compact Lie algebras, the bracket is often written

$$
[T^a,T^b]=i f^{ab}{}_c T^c,
$$

where $f^{ab}{}_c$ are the structure constants. Some mathematics references use anti-Hermitian generators and omit the factor of $i$. The physics convention is natural when $T^a$ are Hermitian matrices acting on a Hilbert space.

A representation $R$ is a map

$$
T^a \mapsto T^a_R
$$

such that

$$
[T^a_R,T^b_R]=i f^{ab}{}_c T^c_R.
$$

In CFT, a local operator $\mathcal O_i$ transforming in representation $R_i$ has infinitesimal transformation

$$
\delta_\epsilon \mathcal O_i
=
i\epsilon_a (T^a_{R_i})_i{}^j \mathcal O_j,
$$

up to the sign convention chosen for charges. The important invariant fact is that operators organize into multiplets of $\mathfrak g$.

## Three recurring examples

The following table is the mental map for this course.

| Algebra | Where it appears | What it labels |
|---|---|---|
| $\mathfrak{so}(d+1,1)$ or $\mathfrak{so}(d,2)$ | Conformal symmetry | $\Delta$, spin, conformal multiplets |
| $\mathfrak{su}(2)$ | Spin chains, 2D current algebra, angular momentum | spin $j$, Dynkin label $n=2j$ |
| $\mathfrak{su}(4)_R\simeq\mathfrak{so}(6)_R$ | $4d$ $\mathcal N=4$ SYM | $R$-symmetry labels $[a,b,c]$ |
| $\widehat{\mathfrak g}_k$ | 2D WZW and current algebra | affine highest weights, level $k$ |
| $\mathfrak{psu}(2,2\vert4)$ | $\mathcal N=4$ superconformal symmetry | supermultiplets, BPS shortening |

The same representation-theoretic words occur in all rows: weights, highest weights, Casimirs, tensor products, singlets, and selection rules. The details differ, but the logic is remarkably stable.

## Cartan subalgebra, roots, and weights

Let $\mathfrak g$ be a complex semisimple Lie algebra of rank $r$. A Cartan subalgebra $\mathfrak h$ is a maximal commuting subalgebra. Choose a basis $H_i$, $i=1,\ldots,r$, for $\mathfrak h$.

In the Cartan-Weyl basis, the algebra is decomposed into

$$
\mathfrak g
=
\mathfrak h
\oplus
\bigoplus_{\alpha\in\Phi}\mathfrak g_\alpha,
$$

where $\Phi$ is the root system. A root $\alpha$ is a linear functional on $\mathfrak h$, characterized by

$$
[H_i,E_\alpha]=\alpha_i E_\alpha.
$$

For every root $\alpha$, there is a root vector $E_\alpha$. Roots describe the charges of the algebra generators under the Cartan subalgebra.

A representation $R$ decomposes into weight spaces. A vector $\vert\lambda\rangle$ has weight $\lambda$ if

$$
H_i\vert\lambda\rangle=\lambda_i\vert\lambda\rangle.
$$

The generators $E_\alpha$ shift weights:

$$
E_\alpha:\quad \lambda\mapsto \lambda+\alpha.
$$

This is the simplest way to picture finite-dimensional representations: a representation is a finite set of weights, and the roots tell you how the algebra moves between them.

<figure class="doc-figure" style="--figure-width: 30rem; --caption-width: 46rem;">

![The $A_2$ root system and fundamental weights.](/figures/cft/lie-algebras-a2-roots-weights.svg)

<figcaption>

The $A_2\simeq\mathfrak{su}(3)$ root system. The roots $\alpha_1$, $\alpha_2$, and $\alpha_1+\alpha_2$ generate the positive-root directions. The fundamental weights $\omega_i$ are dual to the simple coroots through $(\omega_i,\alpha_j^\vee)=\delta_{ij}$. The overall scale of the drawing is conventional.

</figcaption>
</figure>

A choice of positive roots $\Phi_+$ defines simple roots

$$
\alpha_1,\ldots,\alpha_r.
$$

Every positive root is a nonnegative integer combination of simple roots:

$$
\alpha\in\Phi_+
\quad\Longrightarrow\quad
\alpha=\sum_{i=1}^r n_i\alpha_i,
\qquad n_i\in\mathbb Z_{\ge0}.
$$

The coroot associated with $\alpha$ is

$$
\alpha^\vee=\frac{2\alpha}{(\alpha,\alpha)}.
$$

The fundamental weights $\omega_i$ are defined by

$$
(\omega_i,\alpha_j^\vee)=\delta_{ij}.
$$

A highest weight is usually written in Dynkin-label form as

$$
\lambda=\sum_{i=1}^r n_i\omega_i,
\qquad
[n_1,n_2,\ldots,n_r].
$$

For compact groups, finite-dimensional irreducible representations are classified by dominant integral highest weights:

$$
n_i\in\mathbb Z_{\ge0}.
$$

This is why Dynkin labels are so useful. They are the nonnegative integers that specify the representation.

## Highest-weight representations

A highest-weight representation is generated from a highest-weight vector $\vert\lambda\rangle$ obeying

$$
H_i\vert\lambda\rangle=\lambda_i\vert\lambda\rangle,
\qquad
E_{\alpha}\vert\lambda\rangle=0
\quad
\text{for all }\alpha\in\Phi_+.
$$

The rest of the representation is obtained by applying lowering operators $E_{-\alpha}$.

This logic appears repeatedly in CFT:

- For finite internal symmetries, highest weights label ordinary global-symmetry multiplets.
- For conformal symmetry, a primary state is annihilated by $K_\mu$, and descendants are obtained using $P_\mu$.
- For Virasoro symmetry, a highest-weight state is annihilated by $L_{n>0}$, and descendants are obtained using $L_{-n}$.
- For affine current algebra, an affine primary is annihilated by positive current modes $J^a_{n>0}$ and transforms in a finite-dimensional representation of $\mathfrak g$ under $J_0^a$.

The same diagram keeps reappearing: a highest state sits at the top, lowering operators generate a module, and null states or shortening conditions can remove part of the module.

## Weyl vector, dimensions, and Casimirs

The Weyl vector is

$$
\rho=\frac12\sum_{\alpha\in\Phi_+}\alpha
=
\sum_{i=1}^r \omega_i.
$$

The Weyl dimension formula gives the dimension of the finite-dimensional irreducible representation $R_\lambda$:

$$
\dim R_\lambda
=
\prod_{\alpha\in\Phi_+}
\frac{(\lambda+\rho,\alpha^\vee)}{(\rho,\alpha^\vee)}.
$$

The quadratic Casimir in the representation of highest weight $\lambda$ is

$$
C_2(\lambda)
=
\frac12(\lambda,\,\lambda+2\rho),
$$

when long roots have length squared $2$ and generators are normalized in the standard physics convention. The Casimir is defined by

$$
T^a_R T^a_R=C_2(R)\,\mathbf 1_R.
$$

The Dynkin index $T_R$ is defined by

$$
\operatorname{tr}_R(T^a_R T^b_R)=T_R\delta^{ab}.
$$

The relation between $C_2(R)$ and $T_R$ is

$$
T_R\dim \mathfrak g=C_2(R)\dim R.
$$

For $SU(N)$ with fundamental generators normalized by

$$
\operatorname{tr}_{\mathbf N}(T^aT^b)=\frac12\delta^{ab},
$$

one has

$$
T_{\mathbf N}=\frac12,
\qquad
C_F=\frac{N^2-1}{2N},
\qquad
C_A=N.
$$

These constants appear in beta functions, current two-point functions, anomalies, and large-$N$ counting.

## $SU(N)$ representations and Young diagrams

For $SU(N)$, irreducible representations may be labeled either by Dynkin labels

$$
[a_1,a_2,\ldots,a_{N-1}]
$$

or by Young diagrams. The connection is simple. If the Young diagram has row lengths

$$
r_1\ge r_2\ge\cdots\ge r_{N-1}\ge0,
$$

then the Dynkin labels are

$$
a_i=r_i-r_{i+1}.
$$

Conversely,

$$
r_i=a_i+a_{i+1}+\cdots+a_{N-1}.
$$

Useful examples are:

| Group | Representation | Dynkin label | Dimension |
|---|---:|---:|---:|
| $SU(2)$ | spin $j$ | $[2j]$ | $2j+1$ |
| $SU(3)$ | fundamental | $[1,0]$ | $3$ |
| $SU(3)$ | antifundamental | $[0,1]$ | $\bar 3$ |
| $SU(3)$ | adjoint | $[1,1]$ | $8$ |
| $SU(4)$ | fundamental | $[1,0,0]$ | $4$ |
| $SU(4)$ | antifundamental | $[0,0,1]$ | $\bar 4$ |
| $SU(4)$ | vector of $SO(6)$ | $[0,1,0]$ | $6$ |
| $SU(4)$ | adjoint | $[1,0,1]$ | $15$ |
| $SU(4)$ | $20'$ | $[0,2,0]$ | $20$ |

For $\mathcal N=4$ SYM, the most important sequence is

$$
[0,p,0],
\qquad p=2,3,4,\ldots.
$$

These are the half-BPS chiral-primary representations. Their protected scaling dimensions are

$$
\Delta=p.
$$

In the $\mathrm{AdS}_5\times S^5$ dictionary, they match scalar Kaluza-Klein harmonics on $S^5$ with angular momentum $p$.

## Selection rules and invariant tensors

A correlation function must be invariant under all global symmetries. If operators transform in representations $R_1,\ldots,R_n$ of a compact global symmetry group $G$, then the correlator can be nonzero only if

$$
R_1\otimes\cdots\otimes R_n
$$

contains the singlet representation.

This is the representation-theoretic origin of many CFT selection rules. For example, a three-point coefficient

$$
C_{ijk}
$$

can be nonzero only if

$$
R_i\otimes R_j\otimes R_k
$$

contains a $G$-invariant tensor. If the singlet appears more than once, there are multiple independent tensor structures in internal-symmetry space.

For adjoint currents, the two most common invariant tensors are

$$
\delta^{ab},
\qquad
f^{abc}.
$$

For $SU(N)$ with $N\ge3$, there is also a symmetric invariant

$$
d^{abc}=2\operatorname{tr}\bigl(T^{(a}T^bT^{c)}\bigr).
$$

In CFT language, these invariant tensors multiply spacetime tensor structures. Symmetry fixes the tensor structures; dynamics fixes their coefficients.

## The conformal algebra as a Lie algebra

The conformal algebra in $d$ dimensions is generated by

$$
P_\mu,
\qquad
M_{\mu\nu},
\qquad
D,
\qquad
K_\mu.
$$

In the convention used in this course,

$$
[D,P_\mu]=P_\mu,
\qquad
[D,K_\mu]=-K_\mu,
$$

and

$$
[K_\mu,P_\nu]
=2\delta_{\mu\nu}D-2M_{\mu\nu}
$$

in Euclidean signature. This algebra is isomorphic to

$$
\mathfrak{so}(d+1,1).
$$

In Lorentzian signature it is

$$
\mathfrak{so}(d,2).
$$

A primary state is a highest-weight state for the conformal algebra:

$$
K_\mu\vert\mathcal O\rangle=0,
\qquad
D\vert\mathcal O\rangle=\Delta\vert\mathcal O\rangle.
$$

Descendants are obtained by acting with $P_\mu$:

$$
P_{\mu_1}\cdots P_{\mu_n}\vert\mathcal O\rangle.
$$

Thus CFT representation theory is also highest-weight representation theory, but with respect to the noncompact conformal algebra. This is why unitarity bounds are subtler than for compact Lie groups: noncompact generators do not act like ordinary compact rotations.

## The $SL(2)$ subalgebra

Many CFT calculations reduce to an $SL(2)$ problem. In two dimensions, the global holomorphic conformal algebra is generated by

$$
L_{-1},\quad L_0,\quad L_1,
$$

with

$$
[L_m,L_n]=(m-n)L_{m+n},
\qquad m,n=-1,0,1.
$$

For a primary state,

$$
L_1\vert h\rangle=0,
\qquad
L_0\vert h\rangle=h\vert h\rangle,
$$

and descendants are produced by $L_{-1}$. In higher-dimensional lightcone bootstrap, an analogous collinear $SL(2)$ controls towers of large-spin operators. This is why $SL(2)$ representation theory keeps returning in apparently different CFT problems.

## Affine Lie algebras and current algebras

In two-dimensional CFT, a holomorphic conserved current has the OPE

$$
J^a(z)J^b(0)
\sim
\frac{k\kappa^{ab}}{z^2}
+
\frac{i f^{ab}{}_c J^c(0)}{z}.
$$

Here $k$ is the level and $\kappa^{ab}$ is the invariant metric on $\mathfrak g$. Expanding

$$
J^a(z)=\sum_{n\in\mathbb Z}J_n^a z^{-n-1},
$$

one obtains the affine algebra

$$
[J_m^a,J_n^b]
=
i f^{ab}{}_c J_{m+n}^c
+
k m\kappa^{ab}\delta_{m+n,0}.
$$

The zero modes $J_0^a$ generate the original finite-dimensional algebra $\mathfrak g$. The nonzero modes are the new two-dimensional ingredient.

For a WZW model based on a simple Lie algebra $\mathfrak g$ at level $k$, the Sugawara stress tensor gives

$$
T(z)=\frac{1}{2(k+h^\vee)}\kappa_{ab}:J^aJ^b:(z),
$$

where $h^\vee$ is the dual Coxeter number. The central charge is

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee}.
$$

An affine primary labeled by a finite-dimensional highest weight $\lambda$ has conformal weight

$$
h_\lambda=\frac{C_2(\lambda)}{k+h^\vee}.
$$

For integrable highest-weight representations at level $k$, the finite highest weight must obey

$$
(\lambda,\theta)\le k,
$$

where $\theta$ is the highest root. For $SU(N)_k$, this becomes

$$
a_1+a_2+\cdots+a_{N-1}\le k
$$

for Dynkin labels $[a_1,\ldots,a_{N-1}]$.

For $SU(2)_k$, the allowed representations are

$$
j=0,\frac12,1,\ldots,\frac{k}{2}.
$$

Their conformal weights are

$$
h_j=\frac{j(j+1)}{k+2},
$$

and the central charge is

$$
c=\frac{3k}{k+2}.
$$

## Cosets

A coset CFT is built from a pair of current algebras $\widehat{\mathfrak g}_k$ and $\widehat{\mathfrak h}_{k'}$ with $\mathfrak h\subset\mathfrak g$. The symbolic notation is

$$
\frac{G_k}{H_{k'}}.
$$

The stress tensor is the difference

$$
T_{G/H}=T_G-T_H,
$$

so the central charge is

$$
c_{G/H}=c_G-c_H.
$$

Cosets are useful because they produce new CFTs from current-algebra data. Minimal models, parafermions, and many rational CFTs can be described this way. In string theory, cosets also provide exact worldsheet descriptions of curved target-space backgrounds.

## The $SU(4)_R\simeq SO(6)_R$ dictionary

The $R$-symmetry of $4d$ $\mathcal N=4$ SYM is

$$
SU(4)_R\simeq SO(6)_R.
$$

The six real scalars transform as the vector of $SO(6)_R$, which is the $SU(4)$ representation

$$
[0,1,0].
$$

The four Weyl fermions transform as

$$
[1,0,0]=\mathbf 4,
$$

and their conjugates transform as

$$
[0,0,1]=\bar{\mathbf 4}.
$$

The $R$-symmetry currents transform in the adjoint

$$
[1,0,1]=\mathbf{15}.
$$

The stress-tensor multiplet has a scalar superconformal primary in

$$
[0,2,0]=\mathbf{20'}.
$$

The half-BPS single-trace chiral primaries are schematically

$$
\mathcal O_p
=
\operatorname{tr}\bigl(\Phi^{(I_1}\cdots\Phi^{I_p)}\bigr)_{\text{traceless}},
$$

and transform in

$$
[0,p,0],
\qquad
\Delta=p.
$$

These are the cleanest example of representation theory becoming a holographic spectrum: $SO(6)_R$ is the isometry algebra of $S^5$, and $[0,p,0]$ labels spherical harmonics on $S^5$.

## Lie algebra data frequently used in CFT

| $\mathfrak g$ | Rank | $\dim\mathfrak g$ | $h^\vee$ | Common use |
|---|---:|---:|---:|---|
| $\mathfrak{su}(N)$ | $N-1$ | $N^2-1$ | $N$ | gauge theory, WZW models, spin chains |
| $\mathfrak{so}(N)$ | $\lfloor N/2\rfloor$ | $N(N-1)/2$ | $N-2$ | rotations, $R$-symmetry, vector models |
| $\mathfrak{sp}(N)$ | $N$ | $N(2N+1)$ | $N+1$ | supersymmetry, flavor symmetry conventions |
| $\mathfrak{e}_6$ | $6$ | $78$ | $12$ | exceptional symmetry, SCFTs |
| $\mathfrak{e}_7$ | $7$ | $133$ | $18$ | exceptional symmetry, SCFTs |
| $\mathfrak{e}_8$ | $8$ | $248$ | $30$ | exceptional symmetry, heterotic strings |

For $\mathfrak{sp}(N)$, this table uses the convention in which the fundamental representation has dimension $2N$. Some physics papers instead write $Sp(2N)$ for the same group. Always check the convention.

## AdS/CFT checkpoints

Lie algebras become physical data in holography in several ways.

A global symmetry current in the CFT,

$$
J_\mu^a,
$$

is dual to a bulk gauge field,

$$
A_M^a.
$$

The Lie algebra $\mathfrak g$ controls the non-Abelian bulk gauge interactions through $f^{ab}{}_c$.

The stress tensor is the current for conformal symmetry. It is dual to the bulk metric:

$$
T_{\mu\nu}
\longleftrightarrow
 g_{MN}.
$$

The conformal algebra $\mathfrak{so}(d,2)$ is the isometry algebra of $\mathrm{AdS}_{d+1}$ in Lorentzian signature. This is the first exact match in the AdS/CFT dictionary.

For $\mathcal N=4$ SYM,

$$
\mathfrak{su}(4)_R\simeq\mathfrak{so}(6)_R
$$

is the isometry algebra of $S^5$. Thus $R$-symmetry representation theory becomes harmonic analysis on the internal sphere.

In two-dimensional worldsheet CFT, affine Lie algebras determine exact string backgrounds. The level $k$ often controls the curvature radius in string units. Large $k$ is a semiclassical limit; small $k$ is intrinsically stringy.

## Common pitfalls

**Do not confuse a group with its algebra.** The algebra captures infinitesimal transformations. The global form of the group matters for charge quantization, line operators, global anomalies, and allowed representations.

**Do not confuse tensor products with fusion products.** For ordinary finite-dimensional Lie algebras, tensor products decompose as usual. In rational 2D CFT and WZW models, fusion rules are level-truncated versions of tensor-product rules.

**Do not confuse spin with $R$-symmetry.** Spacetime spin is part of the Lorentz or rotation representation. $R$-symmetry is an internal symmetry that acts nontrivially on supercharges.

**Do not assume every representation is unitary.** Compact internal symmetries have finite-dimensional unitary representations. Noncompact conformal algebras require separate unitarity bounds, and infinite-dimensional Virasoro or affine modules have their own positivity conditions.

**Do not ignore normalization.** A factor of $2$ in the definition of roots or generators changes formulas for $C_2$, $T_R$, and $k$. Fix the convention before comparing formulas across references.

## Exercises

### Exercise 1: $SU(2)$ Casimir from the highest weight

For $SU(2)$, the simple root has length squared $2$, and the fundamental weight is $\omega=\alpha/2$. A spin-$j$ representation has highest weight

$$
\lambda=2j\omega.
$$

Use

$$
C_2(\lambda)=\frac12(\lambda,\lambda+2\rho)
$$

with $\rho=\omega$ to show that

$$
C_2(j)=j(j+1).
$$

<details><summary><strong>Solution</strong></summary>

Since $\omega=\alpha/2$ and $(\alpha,\alpha)=2$, we have

$$
(\omega,\omega)=\frac12.
$$

The highest weight is $\lambda=2j\omega$, and $\rho=\omega$. Therefore

$$
(\lambda,\lambda+2\rho)
=
(2j\omega,2(j+1)\omega)
=
4j(j+1)(\omega,\omega)
=
2j(j+1).
$$

Thus

$$
C_2(j)=\frac12(\lambda,\lambda+2\rho)=j(j+1).
$$

</details>

### Exercise 2: allowed primaries of $SU(2)_k$

Show that the integrability condition for $SU(2)_k$ gives

$$
j=0,\frac12,1,\ldots,\frac{k}{2}.
$$

Then compute the conformal weights for $k=1$.

<details><summary><strong>Solution</strong></summary>

For $SU(2)$, a highest weight is labeled by the Dynkin label

$$
n=2j.
$$

The highest root is the simple root, so the integrability condition is

$$
n\le k.
$$

Therefore

$$
2j\le k,
\qquad
j=0,\frac12,1,\ldots,\frac{k}{2}.
$$

For $SU(2)_1$, the allowed spins are $j=0$ and $j=1/2$. The conformal weights are

$$
h_j=\frac{j(j+1)}{k+2}.
$$

Thus

$$
h_0=0,
\qquad
h_{1/2}=\frac{(1/2)(3/2)}{3}=\frac14.
$$

</details>

### Exercise 3: the $\mathcal N=4$ half-BPS mass formula

A half-BPS scalar primary in $\mathcal N=4$ SYM has

$$
\Delta=p,
\qquad
SU(4)_R\text{ label }[0,p,0].
$$

Use the scalar AdS/CFT mass-dimension relation in $d=4$,

$$
m^2L^2=\Delta(\Delta-4),
$$

to find the bulk mass for $p=2$, $p=3$, and $p=4$.

<details><summary><strong>Solution</strong></summary>

Substitute $\Delta=p$:

$$
m^2L^2=p(p-4).
$$

For $p=2$,

$$
m^2L^2=2(2-4)=-4.
$$

For $p=3$,

$$
m^2L^2=3(3-4)=-3.
$$

For $p=4$,

$$
m^2L^2=4(4-4)=0.
$$

The $p=2$ scalar saturates the $\mathrm{AdS}_5$ Breitenlohner-Freedman bound $m^2L^2\ge -4$.

</details>

### Exercise 4: singlet selection rule

Suppose three scalar primaries transform in representations $R_1$, $R_2$, and $R_3$ of a compact internal symmetry group $G$. Explain why a nonzero three-point function requires

$$
R_1\otimes R_2\otimes R_3
$$

to contain the singlet.

<details><summary><strong>Solution</strong></summary>

A three-point function with internal indices has the schematic form

$$
\langle \mathcal O_{1,a}(x_1)\mathcal O_{2,b}(x_2)\mathcal O_{3,c}(x_3)\rangle
=
\mathcal I_{abc}\,F(x_1,x_2,x_3),
$$

where $\mathcal I_{abc}$ is an invariant tensor in

$$
R_1^*\otimes R_2^*\otimes R_3^*.
$$

Equivalently, the tensor product $R_1\otimes R_2\otimes R_3$ must contain the trivial representation. If no singlet exists, there is no invariant tensor to contract the internal indices, so the correlator must vanish.

</details>

## Further reading

For finite-dimensional simple Lie algebras, highest weights, characters, tensor products, affine Lie algebras, WZW models, fusion rules, modular invariants, and cosets, the most directly relevant reference is Di Francesco--Mathieu--Sénéchal, Chapters 13--18.

For the conformal algebra and representation theory used in the modern bootstrap, read this appendix together with the earlier pages on primaries, radial quantization, unitarity bounds, Casimirs, and conformal blocks.

For $\mathcal N=4$ SYM and AdS/CFT, the indispensable finite-dimensional algebra is

$$
\mathfrak{su}(4)_R\simeq\mathfrak{so}(6)_R,
$$

and the indispensable superalgebra is

$$
\mathfrak{psu}(2,2\vert4).
$$
