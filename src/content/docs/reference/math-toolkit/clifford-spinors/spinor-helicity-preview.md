---
title: "Spinor-Helicity Preview"
description: "Introduces spinor-helicity variables for massless four-dimensional kinematics, including null-momentum factorization, spinor brackets, little-group scaling, polarization vectors, and the main convention traps."
sidebar:
  label: "Spinor-Helicity Preview"
  order: 8
level: Advanced
status: "Polished draft"
source: "Standard QFT and amplitudes references, including Srednicki, Schwartz, Weinberg, Elvang–Huang, Dixon, and common two-component spinor conventions."
topics:
  - spinor helicity
  - massless kinematics
  - little group
  - helicity amplitudes
  - polarization vectors
  - spinor brackets
canonicalTopics:
  - spinor-helicity
  - massless-spinors
  - little-group-scaling
  - helicity-amplitudes
  - polarization-vectors
  - schouten-identity
researchStatus:
  established:
    - "Spinor-helicity variables are the standard four-dimensional language for massless on-shell kinematics and helicity amplitudes."
  active:
    - "Modern amplitude research extends the basic formalism to massive spinor helicity, higher dimensions, twistor variables, on-shell recursion, positive geometry, celestial amplitudes, and automated amplitude computation."
---

## Summary

Spinor-helicity notation rewrites a null four-momentum as a product of two two-component spinors. In four-dimensional mostly-minus conventions, define

$$
p_{\alpha\dot\alpha}=p_\mu\sigma^\mu_{\alpha\dot\alpha}.
$$

If $p^2=0$, then $p_{\alpha\dot\alpha}$ has determinant zero and can be factorized as

$$
p_{\alpha\dot\alpha}=\lambda_\alpha\widetilde\lambda_{\dot\alpha}.
$$

This page introduces the notation

$$
\lambda_{i\alpha}=|i\rangle_\alpha,
\qquad
\widetilde\lambda_{i\dot\alpha}=|i]_{\dot\alpha},
$$

and the invariant brackets

$$
\langle ij\rangle,
\qquad
[ij],
\qquad
2p_i\cdot p_j=\langle ij\rangle[ji].
$$

The payoff is huge: complicated massless amplitudes become homogeneous functions of angle brackets and square brackets. Lorentz covariance is built in, and helicity is enforced by a simple little-group scaling rule.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Flow diagram from null momentum to bispinor factorization, little-group scaling, spinor brackets, and homogeneous helicity amplitudes.](/figures/math-toolkit/spinor-helicity-kinematics.svg)

<figcaption>

Spinor-helicity variables trade a null vector for a pair of spinors. The price is a little-group redundancy; the reward is that helicity amplitudes become compact homogeneous functions of $\langle ij\rangle$ and $[ij]$.

</figcaption>
</figure>

This is a preview page, not a full amplitudes course. It explains the mathematical dictionary needed before the scattering and amplitudes pages use expressions such as the Parke–Taylor formula, on-shell recursion, or spinor-helicity Feynman rules. The mantra is:

$$
\text{massless four-vector}
\quad\longleftrightarrow\quad
\text{rank-one bispinor}
\quad\longleftrightarrow\quad
\text{spinor pair modulo little group}.
$$

## Prerequisites

Read [Pauli Matrices](/math-toolkit/clifford-spinors/pauli-matrices/), [SL2C and the Lorentz Group](/math-toolkit/groups-representations/sl2c-and-lorentz-group/), [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/), and [Weyl, Dirac, and Majorana Spinors](/math-toolkit/clifford-spinors/weyl-dirac-majorana-spinors/) first.

This page also uses the mostly-minus metric fixed in [Mathematical Conventions](/math-toolkit/conventions/):

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1).
$$

You do not need to know scattering amplitudes yet, but the notation is motivated by massless external states in perturbative QFT.

## Core idea

A generic four-vector is encoded by a $2\times2$ matrix. A null four-vector is special because that matrix has rank one, so it factorizes into a column spinor times a row spinor. That is the entire geometric source of spinor helicity.

The construction has three steps:

1. Turn $p^\mu$ into a bispinor $p_{\alpha\dot\alpha}$.
2. Use $p^2=0$ to factor it as $\lambda_\alpha\widetilde\lambda_{\dot\alpha}$.
3. Use the one-dimensional rescaling freedom of this factorization to encode helicity.

The rescaling freedom is

$$
\lambda_\alpha\mapsto t\lambda_\alpha,
\qquad
\widetilde\lambda_{\dot\alpha}\mapsto t^{-1}\widetilde\lambda_{\dot\alpha},
\qquad
p_{\alpha\dot\alpha}\mapsto p_{\alpha\dot\alpha}.
$$

This is not a gauge symmetry of the underlying theory. It is the massless little group acting on the spinor representatives of a fixed null momentum. For an external particle of helicity $h_i$, an $n$-point amplitude must scale as

$$
\mathcal A_n(\ldots,t_i\lambda_i,t_i^{-1}\widetilde\lambda_i,\ldots)
=t_i^{-2h_i}\mathcal A_n(\ldots,\lambda_i,\widetilde\lambda_i,\ldots).
$$

That single homogeneity condition is one reason spinor-helicity expressions are so rigid.

## Setup and conventions

We work in four-dimensional Minkowski space with mostly-minus metric. The sigma matrices are

$$
\sigma^\mu_{\alpha\dot\alpha}=(\mathbf 1,\sigma^1,\sigma^2,\sigma^3)_{\alpha\dot\alpha},
\qquad
\bar\sigma^{\mu\dot\alpha\alpha}=(\mathbf 1,-\sigma^1,-\sigma^2,-\sigma^3)^{\dot\alpha\alpha}.
$$

The bispinor associated to a four-vector is

$$
p_{\alpha\dot\alpha}=p_\mu\sigma^\mu_{\alpha\dot\alpha}
=p^0\mathbf 1-\mathbf p\cdot\boldsymbol\sigma.
$$

With this choice,

$$
\det(p_{\alpha\dot\alpha})=p^2.
$$

Spinor indices are raised and lowered with antisymmetric tensors. We choose signs for angle and square brackets so that

$$
\langle ij\rangle=-\langle ji\rangle,
\qquad
[ij]=-[ji],
$$

and

$$
2p_i\cdot p_j=\langle ij\rangle[ji].
$$

Different amplitudes references sometimes place the sign in the definition of square brackets instead. This is harmless if it is done globally, but catastrophic if one mixes formulas source-by-source without translating.

All external momenta are taken outgoing when amplitude examples are mentioned. Real Lorentzian momenta impose a complex-conjugation relation between $\lambda$ and $\widetilde\lambda$ for positive energy, but most spinor-helicity manipulations analytically continue momenta to complex values. In complex kinematics, $\lambda$ and $\widetilde\lambda$ are independent variables.

## Null momenta as bispinors

A four-vector $p^\mu$ becomes a $2\times2$ matrix

$$
p_{\alpha\dot\alpha}=p_\mu\sigma^\mu_{\alpha\dot\alpha}.
$$

For a massive momentum, this matrix has nonzero determinant:

$$
\det p_{\alpha\dot\alpha}=p^2=m^2.
$$

For a massless momentum,

$$
p^2=0,
$$

so

$$
\det p_{\alpha\dot\alpha}=0.
$$

A nonzero $2\times2$ matrix with determinant zero has rank one. Hence it can be written as an outer product:

$$
p_{\alpha\dot\alpha}=\lambda_\alpha\widetilde\lambda_{\dot\alpha}.
$$

This factorization is unique only up to multiplication by a nonzero complex number:

$$
\lambda_\alpha\to t\lambda_\alpha,
\qquad
\widetilde\lambda_{\dot\alpha}\to t^{-1}\widetilde\lambda_{\dot\alpha}.
$$

The four-vector is invariant because the two factors cancel.

A useful way to remember the construction is that $p_{\alpha\dot\alpha}$ maps dotted spinors to undotted spinors. If $p$ is null, that map has a one-dimensional image and a one-dimensional kernel. The spinors $\lambda$ and $\widetilde\lambda$ are representatives of those one-dimensional structures.

The factorization immediately solves the massless Weyl equations. For example,

$$
p_{\alpha\dot\alpha}\widetilde\lambda^{\dot\alpha}
=\lambda_\alpha\widetilde\lambda_{\dot\alpha}\widetilde\lambda^{\dot\alpha}=0,
$$

because the antisymmetric contraction of a commuting spinor with itself vanishes. Similarly,

$$
p^{\dot\alpha\alpha}\lambda_\alpha=0.
$$

So the same spinors that encode the momentum also serve as massless external wavefunctions.

## Spinor brackets and invariants

For two massless momenta $p_i$ and $p_j$, define angle and square brackets by antisymmetric contractions of their spinors:

$$
\langle ij\rangle=\lambda_i^\alpha\lambda_{j\alpha},
\qquad
[ij]=\widetilde\lambda_{i\dot\alpha}\widetilde\lambda_j^{\dot\alpha}.
$$

They obey

$$
\langle ii\rangle=0,
\qquad
[ii]=0,
$$

and

$$
\langle ij\rangle=-\langle ji\rangle,
\qquad
[ij]=-[ji].
$$

The basic Lorentz invariant is

$$
s_{ij}=(p_i+p_j)^2=2p_i\cdot p_j.
$$

For massless $p_i$ and $p_j$, our bracket convention gives

$$
s_{ij}=\langle ij\rangle[ji].
$$

This is the first serious benefit of the notation: scalar products factor into holomorphic and antiholomorphic spinor contractions.

The second benefit is the Schouten identity. Since the undotted spinor space is two-dimensional, any three undotted spinors are linearly dependent. In bracket form,

$$
\langle ij\rangle\lambda_k^\alpha
+\langle jk\rangle\lambda_i^\alpha
+\langle ki\rangle\lambda_j^\alpha=0.
$$

Contracting with a fourth spinor gives

$$
\langle ij\rangle\langle k\ell\rangle
+\langle jk\rangle\langle i\ell\rangle
+\langle ki\rangle\langle j\ell\rangle=0.
$$

There is an identical square-bracket version. In amplitude calculations, many miraculous-looking cancellations are just Schouten identity wearing sunglasses.

Momentum conservation also becomes a spinor identity. If

$$
\sum_i p_i^{\alpha\dot\alpha}=0,
$$

then for any external spinors $a$ and $b$,

$$
\sum_i \langle a i\rangle[i b]=0.
$$

This compact identity is often the fastest way to simplify four-point and five-point expressions.

## Little group scaling

The factorization

$$
p_{\alpha\dot\alpha}=\lambda_\alpha\widetilde\lambda_{\dot\alpha}
$$

has the redundancy

$$
(\lambda,\widetilde\lambda)\sim(t\lambda,t^{-1}\widetilde\lambda).
$$

For real momenta, $t$ is related to the $U(1)$ massless little group. For complexified momenta, $t\in\mathbb C^\times$ is the complexified little group.

A one-particle state of helicity $h$ transforms as

$$
|p,h\rangle\mapsto t^{-2h}|p,h\rangle
$$

in the spinor variables. Therefore an amplitude containing external particle $i$ with helicity $h_i$ must obey

$$
\mathcal A_n(\ldots,t_i\lambda_i,t_i^{-1}\widetilde\lambda_i,\ldots)
=t_i^{-2h_i}\mathcal A_n(\ldots,\lambda_i,\widetilde\lambda_i,\ldots).
$$

For a positive-helicity gluon, $h=+1$, so the amplitude scales as $t^{-2}$. For a negative-helicity gluon, $h=-1$, so it scales as $t^{2}$. For a positive-helicity graviton, $h=+2$, so it scales as $t^{-4}$.

This scaling is so constraining that many three-point amplitudes are fixed, up to a coupling constant, by little-group covariance and dimensional analysis alone.

## Polarization vectors

Spinor helicity also gives compact polarization vectors for massless spin one. Introduce a reference null momentum $q$ with spinors $|q\rangle$ and $|q]$. A convenient convention is

$$
\varepsilon_+^\mu(p;q)
=\frac{\langle q|\bar\sigma^\mu|p]}{\sqrt2\,\langle q p\rangle},
$$

and

$$
\varepsilon_-^\mu(p;q)
=\frac{\langle p|\bar\sigma^\mu|q]}{\sqrt2\,[p q]}.
$$

Here

$$
\langle q|\bar\sigma^\mu|p]
=\lambda_q^\alpha\bar\sigma^{\mu}{}_{\alpha\dot\alpha}\widetilde\lambda_p^{\dot\alpha},
$$

with the obvious analogous expression for $\langle p|\bar\sigma^\mu|q]$. Overall signs and phases vary across references; physical amplitudes are unchanged after consistent translation.

These polarization vectors satisfy

$$
p_\mu\varepsilon_\pm^\mu(p;q)=0,
\qquad
q_\mu\varepsilon_\pm^\mu(p;q)=0.
$$

The reference momentum $q$ is a gauge choice. Changing $q$ changes $\varepsilon_\pm^\mu$ by a term proportional to $p^\mu$. Since gauge-invariant amplitudes vanish when an external polarization is replaced by the external momentum, the final amplitude is independent of $q$.

This is why spinor-helicity calculations often look too good to be legal. You can choose different reference spinors for different external gauge bosons to kill many terms, as long as the final gauge-invariant answer does not depend on those choices.

## Three-point kinematics

Real massless three-point kinematics in Lorentzian signature is degenerate: momentum conservation and on-shellness force all pairwise invariants to vanish. Complex momenta make three-point amplitudes meaningful.

For three massless outgoing momenta,

$$
p_1+p_2+p_3=0,
\qquad
p_i^2=0,
$$

we have

$$
0=(p_i+p_j)^2=\langle ij\rangle[ji].
$$

For complex momenta this can be solved in two branches:

$$
[12]=[23]=[31]=0
\quad\text{with nonzero angle brackets},
$$

or

$$
\langle12\rangle=\langle23\rangle=\langle31\rangle=0
\quad\text{with nonzero square brackets}.
$$

Little-group scaling then fixes the possible three-point structures. On the angle branch,

$$
\mathcal A_3
\propto
\langle12\rangle^{h_3-h_1-h_2}
\langle23\rangle^{h_1-h_2-h_3}
\langle31\rangle^{h_2-h_3-h_1}.
$$

On the square branch,

$$
\mathcal A_3
\propto
[12]^{-h_3+h_1+h_2}
[23]^{-h_1+h_2+h_3}
[31]^{-h_2+h_3+h_1}.
$$

The proportionality constant contains the coupling and any internal-index structure. The point is not that all dynamics has disappeared. The point is that Lorentz covariance and little-group covariance have already done most of the kinematic work.

## A first amplitude-shaped example

A famous color-ordered tree-level Yang–Mills amplitude is the maximally helicity-violating amplitude

$$
A_n^{\mathrm{tree}}(1^-,2^-,3^+,\ldots,n^+)
=i\,g^{n-2}
\frac{\langle12\rangle^4}
{\langle12\rangle\langle23\rangle\cdots\langle n1\rangle},
$$

up to convention-dependent overall factors and color-ordering normalization.

This formula is not derived here. It is included because it shows the point of the notation. In ordinary polarization-vector notation, gluon scattering rapidly becomes algebraic soup. In spinor-helicity notation, the full tree-level answer for an infinite family of amplitudes fits on one line.

Check the little-group scaling. Leg $1$ appears with four powers from the numerator and two powers from the denominator, giving $t_1^2$, which matches helicity $h_1=-1$. A positive-helicity leg $k\ge3$ appears with two denominator powers and no numerator powers, giving $t_k^{-2}$, which matches $h_k=+1$.

That simple check is one of the best ways to catch a wrong spinor-helicity formula.

## Relation to Dirac notation

Spinor helicity is usually presented in two-component Weyl notation, but it also has a four-component Dirac version. One packages massless spinors as chiral Dirac spinors and writes contractions such as

$$
\langle i|\gamma^\mu|j]
$$

or strings such as

$$
\langle i|p\!\!/_a p\!\!/_b|j\rangle.
$$

Here $p\!\!/=\gamma^\mu p_\mu$ in the site convention. The Dirac notation is compact for long spinor strings, while the Weyl notation is cleaner for signs, dotted indices, and the origin of the bracket identities.

The safest approach is to learn both dictionaries:

| Object | Weyl language | Dirac-language role |
|---|---|---|
| $p_{\alpha\dot\alpha}$ | rank-one bispinor | chiral block of $p\!\!/$ |
| $\lambda_\alpha$ | undotted spinor | one massless chiral wavefunction |
| $\widetilde\lambda_{\dot\alpha}$ | dotted spinor | the opposite chiral wavefunction |
| $\langle ij\rangle$ | undotted contraction | chiral spinor product |
| $[ij]$ | dotted contraction | opposite chiral spinor product |

When in doubt, return to the two-component index contraction. It is less glamorous, but it tells the truth.

## Common pitfalls

**Forgetting the little group.** An expression can have the right mass dimension and still be wrong because it has the wrong $t_i$ scaling on one leg.

**Mixing square-bracket conventions.** Some sources define $[ij]$ where others effectively use $[ji]$. Always test the formula against $2p_i\cdot p_j$.

**Treating three-point amplitudes as real Lorentzian amplitudes.** Nonzero massless three-point amplitudes live naturally in complex kinematics. They are still essential because they seed recursion relations and factorization limits.

**Confusing helicity and chirality.** For massless particles the two are tightly related, but chirality is a representation property while helicity is spin projected along momentum. Massive particles do not let you identify them.

**Thinking the reference spinor is physical.** The $q$ in $\varepsilon_\pm^\mu(p;q)$ is a gauge choice. If a gauge-invariant answer depends on $q$, something has gone wrong.

**Using four-dimensional spinor helicity inside dimensional regularization without care.** Many loop calculations use momenta in $d=4-2\epsilon$ dimensions while keeping external helicities four-dimensional. There are several schemes, and chiral objects can be especially delicate.

## Relations to other pages

This page is the on-shell continuation of the spinor technology developed in [Weyl, Dirac, and Majorana Spinors](/math-toolkit/clifford-spinors/weyl-dirac-majorana-spinors/). The two-component sigma-matrix conventions come from [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/), while the Lorentz-group origin of dotted and undotted spinors belongs to [SL2C and the Lorentz Group](/math-toolkit/groups-representations/sl2c-and-lorentz-group/).

It is also related to [Fierz Identities](/math-toolkit/clifford-spinors/fierz-identities/), because Schouten identities and gamma-matrix completeness are both consequences of low-dimensional spinor linear algebra. Later scattering pages use this notation for helicity amplitudes, gauge-boson polarization vectors, soft limits, factorization, and on-shell recursion.

## Research status

The basic four-dimensional massless formalism is established and used routinely in perturbative gauge theory, gravity, collider calculations, and amplitude research. The convention choices on this page are not unique, but the geometry is: null momenta factor into spinors, and helicity is little-group weight.

Active developments include massive spinor-helicity variables, supersymmetric on-shell variables, momentum twistors, celestial amplitudes, positive geometries, finite-field reconstruction of amplitudes, all-multiplicity formulae, and higher-loop integrand technology. Those topics are not prerequisites for this page, but they all rely on the same basic lesson: encode kinematics in variables that make the symmetry unavoidable.

## Exercises

### Exercise 1: Null factorization

Let

$$
p_{\alpha\dot\alpha}=\lambda_\alpha\widetilde\lambda_{\dot\alpha}.
$$

Show that $p^2=0$.

<details><summary><strong>Solution</strong></summary>

The matrix $p_{\alpha\dot\alpha}$ is an outer product of a column vector and a row vector. Therefore it has rank at most one. Any $2\times2$ matrix of rank less than two has determinant zero:

$$
\det(p_{\alpha\dot\alpha})=0.
$$

In our sigma-matrix convention,

$$
\det(p_{\alpha\dot\alpha})=p^2.
$$

Therefore $p^2=0$.

</details>

### Exercise 2: Little-group scaling of brackets

Under

$$
\lambda_i\to t_i\lambda_i,
\qquad
\widetilde\lambda_i\to t_i^{-1}\widetilde\lambda_i,
$$

how do $\langle ij\rangle$ and $[ij]$ scale?

<details><summary><strong>Solution</strong></summary>

Since $\langle ij\rangle$ is linear in $\lambda_i$ and linear in $\lambda_j$,

$$
\langle ij\rangle\to t_i t_j\langle ij\rangle.
$$

Since $[ij]$ is linear in $\widetilde\lambda_i$ and linear in $\widetilde\lambda_j$,

$$
[ij]\to t_i^{-1}t_j^{-1}[ij].
$$

Therefore the product $\langle ij\rangle[ji]$ is invariant under both little-group scalings, as it must be because it equals $2p_i\cdot p_j$.

</details>

### Exercise 3: Schouten identity

Prove

$$
\langle ij\rangle\langle k\ell\rangle
+\langle jk\rangle\langle i\ell\rangle
+\langle ki\rangle\langle j\ell\rangle=0.
$$

<details><summary><strong>Solution</strong></summary>

In a two-dimensional spinor space, the completely antisymmetric tensor with three spinor indices vanishes. Equivalently,

$$
\lambda_i^\alpha\lambda_j^\beta\lambda_k^\gamma
$$

cannot have a nonzero fully antisymmetric part in $\alpha,\beta,\gamma$. This gives the vector identity

$$
\langle ij\rangle\lambda_k^\alpha
+\langle jk\rangle\lambda_i^\alpha
+\langle ki\rangle\lambda_j^\alpha=0.
$$

Contracting with $\lambda_{\ell\alpha}$ yields

$$
\langle ij\rangle\langle k\ell\rangle
+\langle jk\rangle\langle i\ell\rangle
+\langle ki\rangle\langle j\ell\rangle=0.
$$

</details>

### Exercise 4: Little-group check of the MHV formula

Check the little-group scaling of

$$
A_n(1^-,2^-,3^+,\ldots,n^+)
\propto
\frac{\langle12\rangle^4}
{\langle12\rangle\langle23\rangle\cdots\langle n1\rangle}.
$$

<details><summary><strong>Solution</strong></summary>

For leg $1$, the numerator contributes $t_1^4$. The denominator contains $\langle12\rangle$ and $\langle n1\rangle$, contributing $t_1^2$. Therefore the total scaling is

$$
t_1^{4-2}=t_1^2.
$$

This matches $t_1^{-2h_1}$ for $h_1=-1$. The same argument applies to leg $2$.

For a positive-helicity leg $k\ge3$, the numerator contributes no $t_k$. The denominator contains $\langle k-1,k\rangle$ and $\langle k,k+1\rangle$, contributing $t_k^2$ downstairs. Therefore the total scaling is

$$
t_k^{-2},
$$

which matches $t_k^{-2h_k}$ for $h_k=+1$.

</details>

### Exercise 5: Reference spinor dependence

Explain why changing the reference spinor $q$ in a polarization vector should not change a gauge-invariant amplitude.

<details><summary><strong>Solution</strong></summary>

The reference spinor $q$ parametrizes a representative of the polarization vector. Changing $q$ changes the polarization by a term proportional to the external momentum:

$$
\varepsilon^\mu(p;q')-\varepsilon^\mu(p;q)=c(p,q,q')p^\mu
$$

for some scalar $c$. Gauge invariance implies the Ward identity: replacing an external polarization vector by the external momentum gives zero in a physical amplitude. Therefore

$$
\mathcal A(\varepsilon(p;q'))-\mathcal A(\varepsilon(p;q))
=c\,\mathcal A(p)=0.
$$

So the amplitude is independent of the reference spinor, provided all external states and interactions are treated consistently.

</details>

## References

- M. Srednicki, *Quantum Field Theory*. See the chapters on representations of the Lorentz group, spinor technology, gamma-matrix technology, and massless spinor helicity.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. See the chapters on spinors, QED, and gluon scattering with the spinor-helicity formalism.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Useful for the representation-theoretic origin of massless helicity states.
- H. Elvang and Y.-t. Huang, *Scattering Amplitudes in Gauge Theory and Gravity*. A systematic amplitudes reference.
- L. J. Dixon, “Calculating scattering amplitudes efficiently.” A classic review of spinor-helicity and perturbative amplitude technology.
- H. K. Dreiner, H. E. Haber, and S. P. Martin, “Two-component spinor techniques and Feynman rules for quantum field theory and supersymmetry.” Useful for two-component conventions and translations.

## Version history

- **2026-06-24:** Initial polished draft. Introduced massless bispinor factorization, bracket conventions, little-group weights, polarization vectors, three-point kinematics, Schouten identities, and the MHV scaling check.
