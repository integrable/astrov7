---
title: "Crossing and the Conformal Bootstrap"
description: "OPE associativity, crossing equations, positivity, linear functionals, numerical bootstrap logic, and the holographic meaning of consistency."
sidebar:
  order: 3
---

The OPE lets us compute a four-point function by expanding pairs of nearby operators. But a four-point function has more than one OPE channel. We can expand $12\to34$, or $14\to23$, or $13\to24$. These are not different physical observables. They are different ways of computing the same correlator.

The equality of these different expansions is called **crossing symmetry**. In a local CFT, crossing is the analytic expression of OPE associativity:

$$
(\mathcal O_1\mathcal O_2)\mathcal O_3
=
\mathcal O_1(\mathcal O_2\mathcal O_3),
$$

where the equation is not meant as a naive pointwise product of singular operators, but as an equality inside correlation functions after using the convergent OPE in appropriate radial quantization domains.

The modern conformal bootstrap is the program of solving, or constraining, CFT data from this requirement:

$$
\boxed{
\text{conformal symmetry}
+
\text{OPE convergence}
+
\text{crossing}
+
\text{unitarity}
\quad\Longrightarrow\quad
\text{constraints on }\{\Delta,\ell,\lambda\}.
}
$$

For AdS/CFT, this page is a big milestone. Crossing is the CFT form of bulk consistency. In large-$N$ theories it forces the appearance of multi-trace operators, controls anomalous dimensions, and makes it possible to test whether a proposed spectrum can come from a local theory of fields and gravity in AdS.

## OPE associativity as a four-point equation

Consider four scalar primary operators. Conformal symmetry fixes their four-point function up to a function of the cross-ratios $u,v$. For identical scalars $\phi$ of dimension $\Delta_\phi$, we use the convention

$$
\langle
\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)
\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}\mathcal G(u,v),
$$

where

$$
u=
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=
\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The variable $u$ is small in the $12\to34$ OPE channel. The variable $v$ is small in the $14\to23$ OPE channel. For identical operators, permuting the insertion points cannot change the correlator. Exchanging $x_1$ and $x_3$ sends

$$
u\leftrightarrow v.
$$

while changing the kinematic prefactor. Equating the two representations gives

$$
\boxed{
\mathcal G(u,v)
=
\left(\frac{u}{v}\right)^{\Delta_\phi}
\mathcal G(v,u).
}
$$

Equivalently,

$$
\boxed{
v^{\Delta_\phi}\mathcal G(u,v)
=
u^{\Delta_\phi}\mathcal G(v,u).
}
$$

This is the simplest crossing equation. It compares the $12\to34$ channel with the crossed $14\to23$ channel.

## Inserting conformal blocks

The $12\to34$ OPE channel gives the conformal block expansion

$$
\mathcal G(u,v)
=
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(u,v).
$$

The sum runs over primary operators in the OPE $\phi\times\phi$. For a unitary CFT with unit-normalized operators,

$$
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

For a single real identical scalar without extra internal symmetry, Bose symmetry allows only even spins in the singlet OPE channel:

$$
\ell=0,2,4,\ldots.
$$

The identity operator appears with

$$
\Delta=0,
\qquad
\ell=0,
\qquad
G_{0,0}(u,v)=1.
$$

Substitute the conformal block expansion into crossing. Define the crossing vector

$$
F_{\Delta,\ell}(u,v)
=
v^{\Delta_\phi}G_{\Delta,\ell}(u,v)
-u^{\Delta_\phi}G_{\Delta,\ell}(v,u).
$$

Then crossing becomes the infinite-dimensional sum rule

$$
\boxed{
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
F_{\Delta,\ell}(u,v)=0.
}
$$

Separating the identity contribution gives

$$
\boxed{
F_{\mathbf 1}(u,v)
+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2
F_{\Delta,\ell}(u,v)=0,
}
$$

where

$$
F_{\mathbf 1}(u,v)=v^{\Delta_\phi}-u^{\Delta_\phi}.
$$

This equation is the workhorse of the numerical conformal bootstrap. The functions $F_{\Delta,\ell}$ are known once conformal blocks are known. The unknowns are the allowed spectrum and the nonnegative coefficients $\lambda_{\phi\phi\mathcal O}^2$.

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 55rem;">

![Crossing as equality between two OPE channel decompositions.](/figures/cft/crossing-bootstrap-equation.svg)

<figcaption>

Crossing equates different OPE decompositions of the same four-point function. For identical scalars, the equality between the $12\to34$ and $14\to23$ channels gives an infinite sum rule built from crossing vectors $F_{\Delta,\ell}(u,v)$. In a unitary identical-scalar problem the coefficients are nonnegative: $\lambda_{\phi\phi\mathcal O}^2\ge0$.

</figcaption>
</figure>

## What is actually being bootstrapped?

The CFT data relevant to this four-point function are

$$
\left\{
(\Delta,\ell),
\lambda_{\phi\phi\mathcal O}
\right\}_{\mathcal O\in\phi\times\phi}.
$$

Crossing asks whether these data can satisfy

$$
F_{\mathbf 1}
+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2F_{\Delta,\ell}
=0.
$$

Unitarity supplies two crucial ingredients. First, the coefficients are nonnegative. Second, the exchanged dimensions satisfy unitarity bounds. For scalar and symmetric traceless tensor primaries in $d\ge3$,

$$
\Delta\ge \frac{d-2}{2}
\qquad
(\ell=0),
$$

and

$$
\Delta\ge \ell+d-2
\qquad
(\ell\ge1),
$$

with conserved currents and the stress tensor sitting at shortening values:

$$
\Delta_J=d-1,
\qquad
\Delta_T=d.
$$

Thus a bootstrap problem is usually stated as follows. Choose some assumptions, such as external dimension $\Delta_\phi$, spacetime dimension $d$, global symmetry, gaps in certain sectors, or existence of a stress tensor. Then ask:

$$
\boxed{
\text{Does there exist a spectrum and nonnegative OPE data satisfying crossing?}
}
$$

If the answer is no, the assumptions are inconsistent. If the answer is yes, the assumptions may describe one or more CFTs, though crossing of a single correlator alone rarely proves existence or uniqueness.

## The crossing-symmetric point

It is useful to introduce complex variables $z,\bar z$ by

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

The crossing-symmetric Euclidean point is

$$
z=\bar z=\frac12,
\qquad
u=v=\frac14.
$$

At this point, the two OPE channels are as balanced as possible. Numerical bootstrap algorithms often act on crossing equations by taking derivatives at or near this point. A typical linear functional has the form

$$
\alpha[f]
=
\sum_{m+n\le\Lambda}
 a_{mn}
\left.
\partial_z^m\partial_{\bar z}^n f(z,\bar z)
\right|_{z=\bar z=1/2}.
$$

The cutoff $\Lambda$ is the derivative order. Larger $\Lambda$ means a stronger search space for constraints, but also a larger numerical problem.

The reason this works is that crossing is an equality of functions. If two analytic functions are equal, then all of their derivatives at a point agree. Taking finitely many derivatives gives a finite-dimensional projection of the full problem. Increasing $\Lambda$ recovers more and more of the functional equality.

## Linear functionals and exclusions

Write the crossing equation schematically as

$$
F_{\mathbf 1}
+
\sum_i p_iF_i=0,
\qquad
p_i\ge0.
$$

Here $i$ labels allowed exchanged primaries, and $p_i=\lambda_i^2$. Suppose we can find a linear functional $\alpha$ such that

$$
\alpha(F_{\mathbf 1})>0,
$$

and

$$
\alpha(F_i)
\ge0
$$

for every operator allowed by the assumptions. Acting with $\alpha$ on crossing gives

$$
0
=
\alpha(F_{\mathbf 1})
+
\sum_i p_i\alpha(F_i).
$$

But the right-hand side is strictly positive. Contradiction.

Therefore, the assumed spectrum is impossible.

This is the conceptual heart of numerical bootstrap bounds. To exclude a hypothesized gap, one searches for a functional that is positive on all blocks compatible with that gap. If such a functional exists, no unitary CFT with that gap and external dimension can exist.

Geometrically, the vectors $F_i$ generate a positive cone. Crossing says that $-F_{\mathbf 1}$ must lie inside this cone. A separating linear functional proves that it does not.

## A basic scalar gap bound

A common bootstrap question is: given a scalar $\phi$ of dimension $\Delta_\phi$, how large can the lowest non-identity scalar dimension in $\phi\times\phi$ be?

Let the lowest such scalar be called $\epsilon$, with dimension $\Delta_\epsilon$. To test a proposed lower bound

$$
\Delta_\epsilon\ge\Delta_*,
$$

we allow only operators satisfying

$$
\begin{aligned}
&\ell=0:
&&\Delta\ge\Delta_*,
\\
&\ell\ge2\text{ even}:
&&\Delta\ge \ell+d-2.
\end{aligned}
$$

If a positive functional exists for these assumptions, then the gap $\Delta_*$ is too large. The maximal allowed $\Delta_*$ gives an upper bound on $\Delta_\epsilon$ as a function of $\Delta_\phi$.

This is the origin of the famous bootstrap bound plots. At special values of $\Delta_\phi$, kinks or islands may appear. A kink is not a theorem by itself, but it is often a sign that a real CFT is sitting at an extremal point of the allowed space.

## Mixed correlators and islands

A single correlator can produce strong constraints, but many interesting CFTs are isolated more cleanly using **mixed correlators**.

Suppose a theory has several low-lying scalar primaries, for example $\sigma$ and $\epsilon$ in a $\mathbb Z_2$-symmetric theory. One studies the correlators

$$
\langle\sigma\sigma\sigma\sigma\rangle,
\qquad
\langle\sigma\sigma\epsilon\epsilon\rangle,
\qquad
\langle\epsilon\epsilon\epsilon\epsilon\rangle,
$$

and imposes crossing on all of them simultaneously.

The schematic crossing equation becomes vector-valued:

$$
\sum_{\mathcal O}
\vec V_{\Delta,\ell}
\,p_{\mathcal O}=0.
$$

For mixed correlators, the coefficients $p_{\mathcal O}$ are often positive semidefinite matrices rather than single nonnegative numbers, because the same exchanged operator can couple to several external pairs. This is why semidefinite programming naturally appears.

Mixed correlators allow one to impose more structure: global symmetry sectors, parity sectors, gaps in different channels, and equality of OPE coefficients required by symmetry. The result can be a small allowed region, an **island**, in the space of low-lying scaling dimensions.

## Global symmetries

If the CFT has a global symmetry group $G$, operators are organized into representations of $G$. The OPE decomposes into symmetry channels:

$$
\phi_i\times\phi_j
=
\sum_R
(\phi_i\times\phi_j)_R.
$$

Crossing then becomes a vector equation coupling different representation sectors. For example, in an $O(N)$ model, the product of two fundamental scalars decomposes into singlet, symmetric traceless, and antisymmetric representations. Each sector has its own spectrum and positivity conditions.

This is important for AdS/CFT because global symmetries of the boundary CFT become gauge symmetries in the bulk. Flavor current sectors, charged operator sectors, and symmetry selection rules are all visible in crossing equations.

## What crossing does and does not assume

Crossing does not assume a Lagrangian. It does not assume weak coupling. It does not assume quasiparticles. It does not assume large $N$. This is why it is so powerful.

What it does assume is more basic: locality, a Hilbert space with positive norm in unitary problems, conformal symmetry, and the validity of the OPE. In Euclidean CFT, radial quantization gives a clean way to understand OPE convergence. In Lorentzian signature, the same crossing equations have further analytic consequences tied to causality and lightcone singularities.

Crossing also does not usually determine a CFT from one equation. A full CFT must satisfy crossing for all correlators, with all global symmetry and spin structures, together with Ward identities, anomalies, and other consistency conditions. Numerical bootstrap studies finite but increasingly powerful projections of this infinite system.

## Large-$N$ meaning: why double-trace operators are forced

In a large-$N$ CFT, single-trace operators behave like single-particle states in AdS. Multi-trace operators behave like multi-particle states. For a scalar single-trace operator $\mathcal O$ of dimension $\Delta$, large-$N$ factorization gives the leading generalized-free four-point function

$$
\mathcal G^{(0)}(u,v)
=
1
+u^{\Delta}
+
\left(\frac{u}{v}\right)^{\Delta}.
$$

This already satisfies crossing:

$$
\mathcal G^{(0)}(u,v)
=
\left(\frac{u}{v}\right)^\Delta
\mathcal G^{(0)}(v,u).
$$

But its conformal block expansion contains an infinite tower of double-trace operators of schematic form

$$
[\mathcal O\mathcal O]_{n,\ell}
\sim
\mathcal O\,\partial^{2n}\partial_{\mu_1}\cdots\partial_{\mu_\ell}\mathcal O
-
\text{traces},
$$

with leading dimensions

$$
\Delta_{n,\ell}^{(0)}
=
2\Delta+2n+
\ell.
$$

Thus crossing plus large-$N$ factorization already predicts the CFT avatar of two-particle states in AdS.

At the next order in $1/N$, single-trace exchanges and contact interactions correct the four-point function. Crossing then requires shifts in double-trace data:

$$
\Delta_{n,\ell}
=
2\Delta+2n+
\ell
+
\frac{1}{N^2}\gamma_{n,\ell}
+\cdots,
$$

and corrections to OPE coefficients. In the bulk, these are interaction energy shifts and changes in overlap between two-particle states and boundary operator products.

So one of the deepest lessons of crossing for AdS/CFT is:

$$
\boxed{
\text{bulk interactions are encoded in the crossing-consistent deformation of double-trace data.}
}
$$

## Single blocks are not enough

A single conformal block in one channel is almost never crossing-symmetric by itself. This matters holographically.

If a bulk field is exchanged in AdS, the corresponding boundary single-trace block appears in one OPE channel. But a full Witten exchange diagram decomposes into that single-trace block plus an infinite set of double-trace blocks. Those extra blocks are not optional decoration. They are required by crossing and by the OPE.

This is why the statement

$$
\text{conformal block} = \text{exchange Witten diagram}
$$

is generally false. A conformal block isolates one irreducible conformal representation. A Witten diagram gives a full contribution to a correlator, and a full correlator must obey crossing.

A more refined statement is that special objects, such as geodesic Witten diagrams, compute individual conformal blocks. Ordinary exchange diagrams are larger crossing-compatible objects.

## Analytic bootstrap viewpoint

Numerical bootstrap often starts from positivity and linear functionals. Analytic bootstrap starts from special kinematic limits.

The most important one is the lightcone limit. In one channel, take

$$
u\to0.
$$

while keeping the other cross-ratio fixed. The identity operator, conserved currents, or low-twist operators dominate one channel. Crossing then implies the existence of large-spin operators in the crossed channel.

For identical scalars, one finds families of double-twist operators

$$
[\phi\phi]_{n,\ell},
$$

with dimensions approaching

$$
\Delta_{n,\ell}
\to
2\Delta_\phi+2n+
\ell
\qquad
(\ell\to\infty),
$$

plus anomalous corrections controlled by low-twist exchanges in the crossed channel.

This is the analytic ancestor of many holographic results. In large-$N$ CFTs, the same logic becomes the systematic large-spin expansion of two-particle states in AdS.

## AdS/CFT checkpoint

Crossing is the boundary consistency condition that makes bulk physics possible.

At leading large $N$, crossing gives generalized free fields and double-trace towers: the boundary description of free multi-particle states in AdS. At subleading order, crossing ties single-trace exchange, double-trace anomalous dimensions, and contact interactions into one consistent structure. In Lorentzian kinematics, crossing and analyticity lead to causality constraints that become bulk causality, positivity, and chaos bounds.

A useful slogan is

$$
\boxed{
\text{CFT crossing is the nonperturbative shadow of AdS locality.}
}
$$

One must not overread the slogan: crossing alone does not automatically produce a weakly coupled local bulk. But every consistent AdS dual must pass the crossing test, and the detailed way it passes the test is precisely where bulk dynamics is encoded.

## Common pitfalls

Crossing is not merely permutation symmetry of a prefactor. The prefactor changes under permutations, and the reduced correlator transforms nontrivially.

The coefficients in the identical-scalar unitary bootstrap are nonnegative only after choosing positive two-point normalization and an appropriate basis of exchanged operators. With multiple tensor structures or mixed correlators, positivity becomes matrix positivity.

A kink in a numerical bound is evidence, not a proof by itself. It becomes compelling when combined with mixed correlators, global symmetry, spectrum extraction, and stability under increasing numerical precision.

A single channel expansion is not a complete correlator. A complete correlator must admit all OPE expansions and satisfy crossing between them.

## What to remember

For an identical scalar $\phi$, the crossing equation is

$$
v^{\Delta_\phi}\mathcal G(u,v)
=
u^{\Delta_\phi}\mathcal G(v,u).
$$

Using conformal blocks, this becomes

$$
F_{\mathbf 1}(u,v)
+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2
F_{\Delta,\ell}(u,v)=0,
$$

where

$$
F_{\Delta,\ell}(u,v)
=
v^{\Delta_\phi}G_{\Delta,\ell}(u,v)
-u^{\Delta_\phi}G_{\Delta,\ell}(v,u).
$$

Unitarity turns the unknown coefficients into nonnegative numbers. Linear functionals can then prove that proposed spectra are impossible. In large-$N$ CFTs, the same equations organize the emergence of multi-particle AdS states and constrain their interactions.

## Exercises

### Exercise 1: Derive identical-scalar crossing

Starting from

$$
\langle
\phi_1\phi_2\phi_3\phi_4
\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}\mathcal G(u,v),
$$

show that invariance under exchanging $x_1$ and $x_3$ implies

$$
\mathcal G(u,v)
=
\left(\frac{u}{v}\right)^{\Delta_\phi}
\mathcal G(v,u).
$$

<details>
<summary><strong>Solution</strong></summary>

Under $x_1\leftrightarrow x_3$, the cross-ratios are exchanged:

$$
u\leftrightarrow v.
$$

The same four-point function can therefore be written as

$$
\langle
\phi_1\phi_2\phi_3\phi_4
\rangle
=
\frac{1}{(x_{23}^2x_{14}^2)^{\Delta_\phi}}
\mathcal G(v,u).
$$

Equating this with the original representation gives

$$
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}
\mathcal G(u,v)
=
\frac{1}{(x_{23}^2x_{14}^2)^{\Delta_\phi}}
\mathcal G(v,u).
$$

Now use

$$
\frac{x_{12}^2x_{34}^2}{x_{23}^2x_{14}^2}
=
\frac{u}{v}.
$$

Thus

$$
\mathcal G(u,v)
=
\left(\frac{u}{v}\right)^{\Delta_\phi}
\mathcal G(v,u).
$$

</details>

### Exercise 2: Identity crossing vector

Use $G_{0,0}(u,v)=1$ to show that the identity contribution to the crossing equation is

$$
F_{\mathbf 1}(u,v)=v^{\Delta_\phi}-u^{\Delta_\phi}.
$$

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
F_{\Delta,\ell}(u,v)
=
v^{\Delta_\phi}G_{\Delta,\ell}(u,v)
-u^{\Delta_\phi}G_{\Delta,\ell}(v,u).
$$

For the identity,

$$
G_{0,0}(u,v)=G_{0,0}(v,u)=1.
$$

Therefore

$$
F_{\mathbf 1}(u,v)
=
v^{\Delta_\phi}-u^{\Delta_\phi}.
$$

</details>

### Exercise 3: Generalized free field crossing

The leading large-$N$ four-point function of a generalized free scalar of dimension $\Delta$ has reduced correlator

$$
\mathcal G^{(0)}(u,v)
=
1+u^\Delta+\left(\frac{u}{v}\right)^\Delta.
$$

Show that it obeys identical-scalar crossing.

<details>
<summary><strong>Solution</strong></summary>

Compute the crossed expression:

$$
\left(\frac{u}{v}\right)^\Delta
\mathcal G^{(0)}(v,u)
=
\left(\frac{u}{v}\right)^\Delta
\left[
1+v^\Delta+\left(\frac{v}{u}\right)^\Delta
\right].
$$

Distribute the prefactor:

$$
\left(\frac{u}{v}\right)^\Delta
+u^\Delta+1.
$$

This is exactly

$$
1+u^\Delta+\left(\frac{u}{v}\right)^\Delta
=
\mathcal G^{(0)}(u,v).
$$

Thus generalized free field theory satisfies crossing at leading large $N$.

</details>

### Exercise 4: Linear functional exclusion

Assume crossing has the form

$$
F_{\mathbf 1}+\sum_i p_iF_i=0,
\qquad p_i\ge0.
$$

Show that if there exists a linear functional $\alpha$ satisfying

$$
\alpha(F_{\mathbf 1})>0,
\qquad
\alpha(F_i)\ge0
$$

for all allowed $i$, then the assumed spectrum is impossible.

<details>
<summary><strong>Solution</strong></summary>

Apply $\alpha$ to crossing:

$$
0
=
\alpha(F_{\mathbf 1})
+
\sum_i p_i\alpha(F_i).
$$

By assumption,

$$
\alpha(F_{\mathbf 1})>0.
$$

Also, for every allowed operator,

$$
p_i\alpha(F_i)
\ge0
$$

because $p_i\ge0$ and $\alpha(F_i)\ge0$. Therefore the right-hand side is strictly positive, which contradicts the equality to zero. Hence no CFT spectrum satisfying the assumptions can obey crossing.

</details>

### Exercise 5: Why a single block is not crossing-symmetric

Explain why a single nontrivial conformal block $G_{\Delta,\ell}(u,v)$ in one OPE channel cannot usually be a complete four-point function.

<details>
<summary><strong>Solution</strong></summary>

A single block represents one conformal family in one OPE channel. Crossing requires the complete correlator to admit equivalent decompositions in other OPE channels. A single block has the correct OPE behavior in its chosen channel, for example

$$
G_{\Delta,\ell}(u,v)
\sim
u^{\Delta/2}
$$

as the $12$ OPE limit is approached, but it does not generally transform into itself under $u\leftrightarrow v$ with the required external prefactor.

Therefore a crossing-symmetric correlator must combine many blocks with carefully related coefficients. In holographic CFTs, a bulk exchange diagram similarly contains not only the single-trace block of the exchanged field but also double-trace blocks required by crossing.

</details>

## Further reading

For the two-dimensional origin of conformal blocks and crossing, see Di Francesco, Mathieu, and Sénéchal, especially the operator formalism and conformal bootstrap sections. For modern higher-dimensional bootstrap methods, see Rychkov’s *EPFL Lectures on Conformal Field Theory in $D\ge3$* and Simmons-Duffin’s *TASI Lectures on the Conformal Bootstrap*. For the AdS/CFT perspective, compare large-$N$ conformal block expansions with Witten diagrams, double-trace anomalous dimensions, and the lightcone bootstrap.
