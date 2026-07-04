---
title: "N=4 SYM Fields and Symmetries"
description: "Field content, action, couplings, R-symmetry, superconformal algebra, local operators, and the AdS5 x S5 symmetry dictionary."
sidebar:
  order: 1
---

## Goal

The previous module explained why a large-$N$ CFT can behave like a weakly coupled theory of particles in AdS. We now turn to the central example:

$$
\boxed{
4d\ \mathcal N=4\ \mathrm{super\ Yang\text{-}Mills}
\quad\longleftrightarrow\quad
\mathrm{type\ IIB\ string\ theory\ on}\ \mathrm{AdS}_5\times S^5.
}
$$

This page introduces the CFT side of this correspondence. The aim is not to teach every detail of the $\mathcal N=4$ Lagrangian, but to organize the facts that are essential for AdS/CFT:

$$
\text{fields}
\quad\longrightarrow\quad
\text{couplings}
\quad\longrightarrow\quad
\text{symmetries}
\quad\longrightarrow\quad
\text{operators}
\quad\longrightarrow\quad
\text{bulk interpretation}.
$$

The slogan is simple but powerful:

$$
\mathcal N=4\ \mathrm{SYM}
\text{ is the maximally supersymmetric four-dimensional CFT.}
$$

It is interacting for general coupling, yet exactly conformal. It has enough symmetry to be sharply constrained, but enough dynamics to contain quantum gravity, strings, black holes, integrability, thermal physics, entanglement, and strong-coupling phenomena. That combination is why it became the canonical laboratory for AdS/CFT.

<figure class="doc-figure" style="--figure-width: 42rem; --caption-width: 55rem;">

![Field content, symmetries, and holographic data of N=4 SYM](/figures/cft/n4-sym-field-symmetry-map.svg)

<figcaption>

The basic structure of $4d$ $\mathcal N=4$ SYM. The fields $A_\mu$, $\Phi_I$, and $\lambda^A_\alpha$ are all in the adjoint of $SU(N)$. The global symmetry is the superconformal group $PSU(2,2|4)$, whose bosonic part matches the isometries of $\mathrm{AdS}_5\times S^5$. The parameters $N$ and $\lambda=g_{\rm YM}^2N$ control the bulk genus and stringy corrections.

</figcaption>
</figure>

## Field content

Take gauge group $G=SU(N)$. One may also start with $U(N)$, as in the D3-brane construction, but the overall $U(1)$ sector is a decoupled free multiplet. The interacting holographic theory is the $SU(N)$ part.

All elementary fields are valued in the adjoint representation of $SU(N)$. In four-dimensional notation, the fields are:

| field | notation | Lorentz representation | $SU(4)_R\simeq SO(6)_R$ representation | engineering dimension |
|---|---|---|---|---|
| gauge field | $A_\mu$ | vector | singlet $\mathbf 1$ | $1$ |
| real scalars | $\Phi_I$, $I=1,\ldots,6$ | scalar | vector $\mathbf 6$ of $SO(6)_R$ | $1$ |
| Weyl fermions | $\lambda^A_\alpha$, $A=1,\ldots,4$ | left Weyl spinor | fundamental $\mathbf 4$ of $SU(4)_R$ | $3/2$ |
| conjugate fermions | $\bar\lambda_{A\dot\alpha}$ | right Weyl spinor | $\bar{\mathbf 4}$ of $SU(4)_R$ | $3/2$ |

The six scalars are one of the first hints of the string-theory geometry. In the D3-brane picture, a stack of branes fills four spacetime directions. The six real scalars describe transverse fluctuations of the branes in the remaining six directions. The rotation group of those transverse directions is

$$
SO(6)_R\simeq SU(4)_R,
$$

which becomes the $R$-symmetry of the four-dimensional theory. In the bulk dual, the same $SO(6)$ is the isometry group of $S^5$.

A compact way to remember the field content is to begin from ten-dimensional $\mathcal N=1$ super Yang-Mills and dimensionally reduce to four dimensions. The ten-dimensional gauge field decomposes as

$$
A_M
\quad\longrightarrow\quad
A_\mu\oplus \Phi_I,
\qquad
M=0,\ldots,9,
\quad
\mu=0,\ldots,3,
\quad
I=1,\ldots,6.
$$

The ten-dimensional Majorana-Weyl fermion becomes four Weyl fermions in four dimensions. This is the quickest way to see why the field content is so rigid: maximal supersymmetry leaves essentially no room to change it.

## The action

Let $F_{\mu\nu}$ and $D_\mu$ be

$$
F_{\mu\nu}
=
\partial_\mu A_\nu-
\partial_\nu A_\mu-i[A_\mu,A_\nu],
$$

and

$$
D_\mu X=\partial_\mu X-i[A_\mu,X]
$$

for an adjoint field $X$. Suppressing the detailed spinor index contractions, the Lorentzian action has the schematic form

$$
S_{\mathcal N=4}
=
\frac{1}{g_{\rm YM}^2}
\int d^4x\,\operatorname{Tr}\left[
-\frac14 F_{\mu\nu}F^{\mu\nu}
-\frac12 D_\mu\Phi_I D^\mu\Phi_I
+\frac14[\Phi_I,\Phi_J]^2
+\text{fermion kinetic terms}
+\text{Yukawa terms}
\right]
+S_\theta.
$$

Here

$$
S_\theta
=
\frac{\theta}{8\pi^2}\int \operatorname{Tr}(F\wedge F)
=
\frac{\theta}{32\pi^2}\int d^4x\,
\epsilon^{\mu\nu\rho\sigma}\operatorname{Tr}(F_{\mu\nu}F_{\rho\sigma}).
$$

Different books use slightly different sign conventions for Hermitian versus anti-Hermitian generators and for Lorentzian signature. The structural facts do not depend on those choices:

1. the gauge field has the usual Yang-Mills kinetic term;
2. there are six adjoint scalars with covariant kinetic terms;
3. the scalar potential is fixed by commutators $[\Phi_I,\Phi_J]$;
4. the fermions have Yukawa couplings fixed by supersymmetry;
5. the same coupling $g_{\rm YM}$ multiplies all interaction terms.

The scalar potential vanishes precisely when the scalars commute:

$$
[\Phi_I,\Phi_J]=0.
$$

This condition describes the Coulomb branch of vacua. In the conformal vacuum usually used for AdS/CFT, we sit at the origin of this branch,

$$
\langle \Phi_I\rangle=0,
$$

so the full $SU(N)$ gauge symmetry and $SO(6)_R$ symmetry remain unbroken.

## Couplings and the conformal manifold

The gauge coupling is dimensionless in four dimensions:

$$
[g_{\rm YM}]=0.
$$

The theta angle combines with it into the complexified coupling

$$
\tau
=
\frac{\theta}{2\pi}
+
\frac{4\pi i}{g_{\rm YM}^2}.
$$

The parameter most useful in the large-$N$ limit is the 't Hooft coupling

$$
\lambda=g_{\rm YM}^2N.
$$

The AdS/CFT limits are organized as follows:

| CFT limit | bulk interpretation |
|---|---|
| $N\to\infty$ with $\lambda$ fixed | planar limit, string loops suppressed |
| $N\to\infty$, $\lambda\gg 1$ | classical type IIB supergravity regime |
| finite large $\lambda$ | stringy $\alpha'$ corrections |
| finite large $N$ | quantum gravity/string loop corrections |

With the common convention $g_{\rm YM}^2=4\pi g_s$, the string-frame radius relation is

$$
\frac{R^4}{\alpha'^2}=\lambda,
$$

so large $\lambda$ means

$$
R\gg \sqrt{\alpha'}.
$$

That is the condition that the AdS curvature radius is large compared with the string length. In that regime, the stringy tower is heavy and the low-energy bulk description becomes supergravity.

The central large-$N$ relation is

$$
\frac{R^3}{G_5}\sim N^2.
$$

This is the gravitational version of the statement that the CFT has order $N^2$ matrix degrees of freedom.

## Why the beta function vanishes

The theory is conformal for every value of $\tau$. At one loop, the cancellation is already visible. For a four-dimensional gauge theory with $n_f$ Weyl fermions and $n_s$ real scalars in the adjoint representation, the one-loop beta-function coefficient is proportional to

$$
\frac{11}{3}C_2(G)
-
\frac{2}{3}n_f C_2(G)
-
\frac{1}{6}n_s C_2(G).
$$

For $\mathcal N=4$ SYM,

$$
n_f=4,
\qquad
n_s=6.
$$

Therefore

$$
\frac{11}{3}-\frac{2}{3}\cdot 4-\frac{1}{6}\cdot 6
=
\frac{11}{3}-\frac{8}{3}-1
=0.
$$

Maximal supersymmetry strengthens this one-loop cancellation to exact conformality. The coupling $\tau$ is exactly marginal. Thus $\mathcal N=4$ SYM is not one CFT, but a family of CFTs connected by an exactly marginal deformation.

This point is crucial. The theory is not free except at $g_{\rm YM}=0$. As $\lambda$ changes, unprotected scaling dimensions and OPE coefficients change. The stress tensor, currents, and BPS data are constrained by symmetry, but the full theory remains dynamical.

## Global symmetry

The bosonic global symmetry of flat-space $\mathcal N=4$ SYM is

$$
SO(4,2)\times SO(6)_R,
$$

or equivalently

$$
SO(4,2)\times SU(4)_R.
$$

The first factor is the four-dimensional conformal group. The second factor is the $R$-symmetry rotating the six scalars and the four supercharges.

The full superconformal group is

$$
PSU(2,2|4).
$$

Its bosonic subalgebra is

$$
\mathfrak{so}(4,2)\oplus \mathfrak{su}(4)_R.
$$

The fermionic generators are the Poincare supercharges and conformal supercharges:

$$
Q^A_\alpha,
\qquad
\bar Q_{A\dot\alpha},
\qquad
S_{A}^{\alpha},
\qquad
\bar S^{A\dot\alpha}.
$$

There are $16$ Poincare supercharges and $16$ conformal supercharges. Their schematic anticommutators are

$$
\{Q,\bar Q\}\sim P,
\qquad
\{S,\bar S\}\sim K,
\qquad
\{Q,S\}\sim D+M+R.
$$

This is exactly the symmetry expected from type IIB string theory on $\mathrm{AdS}_5\times S^5$:

$$
\operatorname{Isom}(\mathrm{AdS}_5)=SO(4,2),
\qquad
\operatorname{Isom}(S^5)=SO(6),
$$

and the supersymmetric completion is $PSU(2,2|4)$.

This symmetry match is not a decorative feature. It is the first sharp test of the duality. The CFT conformal group becomes the AdS isometry group; the CFT $R$-symmetry becomes the sphere isometry group; the CFT supercharges become the Killing spinor symmetries of the background.

## Representations of $SU(4)_R$

Because

$$
SO(6)\simeq SU(4),
$$

one may label $R$-symmetry representations either by $SO(6)$ language or by $SU(4)$ Dynkin labels $[a,b,c]$.

The most important identifications are

$$
\mathbf 6_{SO(6)}
\quad\leftrightarrow\quad
[0,1,0]_{SU(4)},
$$

and

$$
\mathbf 4_{SU(4)}=[1,0,0],
\qquad
\bar{\mathbf 4}_{SU(4)}=[0,0,1].
$$

The scalars may be packaged as antisymmetric tensors

$$
\phi^{AB}=-\phi^{BA},
\qquad
A,B=1,\ldots,4,
$$

with a reality condition relating $\phi^{AB}$ to $\bar\phi_{AB}$. This antisymmetric representation has dimension $6$, matching the six real scalars $\Phi_I$.

For later AdS/CFT applications, the half-BPS scalar operators are especially important:

$$
\mathcal O_k
\sim
\operatorname{Tr}\left(\Phi_{(I_1}\Phi_{I_2}\cdots \Phi_{I_k)}\right)-\text{traces}.
$$

They transform in the $SU(4)_R$ representation

$$
[0,k,0]
$$

and have protected scaling dimension

$$
\Delta=k.
$$

The $k=2$ case is the bottom component of the stress-tensor multiplet. It is one of the central operators in precision tests of AdS/CFT.

## Local operators

The elementary fields $A_\mu$, $\Phi_I$, and $\lambda^A_\alpha$ are not themselves physical gauge-invariant local operators. The local operators of the CFT are gauge-invariant composites, such as single traces:

$$
\operatorname{Tr}(\Phi_I\Phi_J),
\qquad
\operatorname{Tr}(F_{\mu\nu}F^{\mu\nu}),
\qquad
\operatorname{Tr}(\lambda^A\lambda^B),
\qquad
\operatorname{Tr}(\Phi_I D_\mu\Phi_J\cdots).
$$

At large $N$, single-trace operators are the CFT analogues of single-particle bulk fields. Multi-trace operators are the analogues of multi-particle states.

Important examples include:

| CFT operator | role |
|---|---|
| $T_{\mu\nu}$ | stress tensor; dual to the graviton in $\mathrm{AdS}_5$ |
| $J_\mu{}^A{}_B$ | $SU(4)_R$ current; dual to gauge fields from $S^5$ isometries |
| $\operatorname{Tr}F^2$ | exactly marginal operator paired with the dilaton source |
| $\operatorname{Tr}F\tilde F$ | paired with the axion source |
| $\mathcal O_k\in[0,k,0]$ | half-BPS chiral primary; dual to Kaluza-Klein modes on $S^5$ |
| $\mathcal K=\operatorname{Tr}(\Phi_I\Phi_I)$ | Konishi operator; unprotected long multiplet |

The contrast between BPS operators and long-multiplet operators is one of the main lessons of the theory. BPS dimensions are fixed by representation theory. Long-multiplet dimensions are dynamical functions of $\lambda$.

For example, the Konishi operator has classical dimension $2$, but its exact dimension is not protected:

$$
\Delta_{\mathcal K}(\lambda)
=
2+\gamma_{\mathcal K}(\lambda).
$$

At weak coupling, $\gamma_{\mathcal K}$ can be computed perturbatively. At strong coupling, the Konishi operator is associated with a genuinely stringy excitation, not a light supergravity field.

## Central charges and large $N$

For $SU(N)$ $\mathcal N=4$ SYM, the conformal anomaly coefficients are

$$
a=c=\frac{N^2-1}{4}.
$$

The equality $a=c$ is a strong supersymmetric constraint. The scaling

$$
a\sim c\sim N^2
$$

is what matters most for holography. It says that the number of effective degrees of freedom is of order the number of matrix components in the adjoint representation.

In the bulk, the same scaling appears as

$$
\frac{R^3}{G_5}\sim N^2.
$$

Thus the classical gravity limit is a large-central-charge limit. This is the same idea developed in the large-$N$ module, now realized in a concrete CFT.

## The $\mathcal N=4$ SYM dictionary preview

The basic AdS/CFT dictionary for this theory is:

$$
\boxed{
\begin{array}{ccl}
\text{CFT symmetry }SO(4,2) &\leftrightarrow& \text{AdS}_5\text{ isometry},\\[2pt]
\text{CFT }R\text{-symmetry }SO(6)_R &\leftrightarrow& S^5\text{ isometry},\\[2pt]
T_{\mu\nu} &\leftrightarrow& g_{MN}\text{ graviton},\\[2pt]
J_\mu{}^A{}_B &\leftrightarrow& \text{bulk gauge fields},\\[2pt]
\mathcal O_k\in[0,k,0] &\leftrightarrow& S^5\text{ Kaluza-Klein modes},\\[2pt]
\operatorname{Tr}F^2,\ \operatorname{Tr}F\tilde F &\leftrightarrow& \text{dilaton-axion},\\[2pt]
\text{single trace} &\leftrightarrow& \text{single particle/string state},\\[2pt]
\text{multi trace} &\leftrightarrow& \text{multi-particle state}.
\end{array}
}
$$

The parameter dictionary is:

$$
\boxed{
\begin{array}{ccl}
N\to\infty &\leftrightarrow& \text{classical bulk limit},\\[2pt]
1/N^2 &\leftrightarrow& \text{bulk loop expansion},\\[2pt]
\lambda\gg 1 &\leftrightarrow& \text{small stringy curvature corrections},\\[2pt]
1/\sqrt\lambda &\leftrightarrow& \alpha'\text{ expansion}.
\end{array}
}
$$

These relations are the reason $\mathcal N=4$ SYM is not merely an example of a CFT. It is a controlled nonperturbative definition of a quantum gravity theory in asymptotically $\mathrm{AdS}_5\times S^5$ spacetime.

## Common pitfalls

First, $\mathcal N=4$ SYM is conformal but not generally free. The free point $g_{\rm YM}=0$ is only one point on the conformal manifold. At strong coupling, the theory is deeply interacting.

Second, the fields in the Lagrangian are not the same thing as CFT observables. Gauge-invariant local operators are traces and products of traces. The bulk dictionary is written in terms of such operators, not bare gauge-dependent fields.

Third, $SU(4)_R$ is not a flavor symmetry in the ordinary sense. It rotates supercharges and sits inside the superconformal algebra. In the bulk it becomes an isometry of the internal space $S^5$.

Fourth, the large-$N$ and large-$\lambda$ limits are logically distinct. Large $N$ suppresses quantum gravity loops. Large $\lambda$ suppresses stringy curvature corrections. Classical Einstein gravity needs both.

## AdS/CFT checkpoint

After this page, the key facts to remember are:

$$
\mathcal N=4\ \mathrm{SYM}
\text{ is a }4d\text{ CFT with symmetry }PSU(2,2|4).
$$

Its bosonic symmetry matches the geometry

$$
SO(4,2)\times SO(6)
=
\operatorname{Isom}(\mathrm{AdS}_5)\times \operatorname{Isom}(S^5).
$$

Its large-$N$ single-trace operators behave like bulk single-particle states. Its BPS operators give a protected window into the supergravity spectrum. Its unprotected long operators encode the genuinely stringy, strongly coupled dynamics.

That is exactly the CFT structure needed for the AdS/CFT correspondence.

## Exercises

### Exercise 1: One-loop beta-function cancellation

Use the one-loop coefficient

$$
b_0
=
\left(\frac{11}{3}-\frac{2}{3}n_f-\frac{1}{6}n_s\right)C_2(G)
$$

for a gauge theory with $n_f$ adjoint Weyl fermions and $n_s$ adjoint real scalars. Show that $b_0=0$ for $\mathcal N=4$ SYM.

<details><summary><strong>Solution</strong></summary>

For $\mathcal N=4$ SYM,

$$
n_f=4,
\qquad
n_s=6.
$$

Therefore

$$
\frac{11}{3}-\frac{2}{3}n_f-\frac{1}{6}n_s
=
\frac{11}{3}-\frac{8}{3}-1
=0.
$$

Thus $b_0=0$. This is only the one-loop check; maximal supersymmetry implies exact conformality.

</details>

### Exercise 2: Counting on-shell degrees of freedom

Show that the elementary fields of $\mathcal N=4$ SYM have equal bosonic and fermionic on-shell degrees of freedom in each adjoint color component.

<details><summary><strong>Solution</strong></summary>

A massless gauge field in four dimensions has $2$ physical polarizations. The six real scalars contribute $6$ bosonic degrees of freedom. Thus the bosonic count is

$$
2+6=8.
$$

A massless Weyl fermion has $2$ on-shell real degrees of freedom. There are four Weyl fermions, so the fermionic count is

$$
4\times 2=8.
$$

Thus the multiplet has $8$ bosonic and $8$ fermionic on-shell degrees of freedom per adjoint generator.

</details>

### Exercise 3: Why large $N$ is not the same as strong coupling

Explain the different bulk meanings of $N\to\infty$ and $\lambda\to\infty$.

<details><summary><strong>Solution</strong></summary>

Large $N$ controls the bulk loop expansion. Since

$$
\frac{R^3}{G_5}\sim N^2,
$$

the limit $N\to\infty$ makes Newton's constant small in AdS units and suppresses quantum gravity loops.

Large $\lambda$ controls stringy curvature corrections. Since

$$
\frac{R^4}{\alpha'^2}=\lambda,
$$

the limit $\lambda\to\infty$ makes the AdS radius large compared with the string length. This suppresses $\alpha'$ corrections and allows a low-energy supergravity description.

Classical Einstein gravity requires both limits: $N\gg 1$ and $\lambda\gg 1$.

</details>

### Exercise 4: Protected and unprotected dimensions

Why can a half-BPS operator have a coupling-independent dimension while the Konishi operator does not?

<details><summary><strong>Solution</strong></summary>

A half-BPS operator belongs to a shortened representation of the superconformal algebra. Shortening imposes an algebraic relation between its scaling dimension and its $R$-symmetry quantum numbers. For the operators

$$
\mathcal O_k\in[0,k,0],
$$

this gives

$$
\Delta=k.
$$

The Konishi operator is in a long multiplet. Long multiplets have no shortening condition fixing $\Delta$. Therefore their dimensions can receive anomalous corrections:

$$
\Delta_{\mathcal K}=2+\gamma_{\mathcal K}(\lambda).
$$

In the bulk, protected operators can remain light supergravity modes, while long unprotected operators can become heavy string states at strong coupling.

</details>

### Exercise 5: Symmetry matching

Match each CFT symmetry factor to its geometric origin in the dual background.

<details><summary><strong>Solution</strong></summary>

The CFT conformal group is

$$
SO(4,2),
$$

which is the isometry group of $\mathrm{AdS}_5$. The $R$-symmetry group is

$$
SO(6)_R\simeq SU(4)_R,
$$

which is the isometry group of $S^5$. Together, these give the bosonic symmetry

$$
SO(4,2)\times SO(6).
$$

Including the $16$ Poincare and $16$ conformal supercharges gives the full superconformal group

$$
PSU(2,2|4),
$$

matching the supersymmetry of type IIB string theory on $\mathrm{AdS}_5\times S^5$.

</details>

## Further reading

For the original AdS/CFT construction, read Maldacena's paper on the large-$N$ limit of superconformal field theories and supergravity. For the GKPW prescription, read Gubser-Klebanov-Polyakov and Witten. For field-theory details of $\mathcal N=4$ SYM, useful sources include standard supersymmetry textbooks, reviews of $\mathcal N=4$ SYM, and integrability-focused introductions.

The next page studies the protected half-BPS operators more carefully and explains why their $SU(4)_R$ representation theory is the first precise bridge to the Kaluza-Klein spectrum on $S^5$.
