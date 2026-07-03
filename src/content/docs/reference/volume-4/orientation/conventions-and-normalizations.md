---
title: "Conventions and Normalizations"
description: "Gauge-field, charge, generator, electroweak, and Standard Model sign conventions used throughout the Gauge Theories and the Standard Model volume."
sidebar:
  label: "Conventions"
  order: 1
level: Graduate
status: "Polished draft"
source: "Site-wide conventions; Srednicki §§54, 58, 69–75, 87–91; Weinberg Vol. II Chs. 15, 17, 19–21; Schwartz Chs. 8, 25, 29–30."
topics:
  - gauge-field conventions
  - covariant derivatives
  - Standard Model charges
  - electroweak mixing
canonicalTopics:
  - gauge-conventions
  - covariant-derivative
  - standard-model-hypercharge
researchStatus:
  established:
    - "The conventions on this page are standard textbook conventions, with one explicit sign choice for the non-Abelian covariant derivative."
  active:
    - "Global forms of gauge groups, boundary symmetries, and generalized symmetries require more structure than local Lie-algebra conventions and are treated on later pages."
---

## Summary

This page fixes the gauge-theory conventions used in this volume. The convention-sensitive choices are the sign in the covariant derivative, the normalization of generators, the definition of the field strength, and the normalization of Standard Model hypercharge.

The default Abelian convention is

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\psi(x)\mapsto e^{-iq\alpha(x)}\psi(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x),
$$

so the electron has $q=-e$ with $e>0$. The default non-Abelian convention is

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
$$

with Hermitian generators. With this sign choice,

$$
[D_\mu,D_\nu]=igF_{\mu\nu}^aT^a,
$$

where

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

For the electroweak theory we use

$$
Q=T^3+Y,
$$

not $Q=T^3+Y/2$. This is the convention in which the Standard Model Higgs doublet has $Y_H=+1/2$.

:::caution[Convention check]
Many books use $D_\mu=\partial_\mu-igA_\mu^aT^a$. That convention flips the sign of the non-Abelian term in $F_{\mu\nu}^a$. Nothing physical changes, but Feynman rules and intermediate formulas must be translated consistently.
:::

## Prerequisites

You should know the site-wide [Conventions and Normalizations](/foundations/conventions-and-normalizations/), especially the mostly-minus metric, Fourier phase, propagator, gamma-matrix, and path-integral conventions. You should also be comfortable with Lie-algebra generators, complex scalar and Dirac fields, and the basic distinction between a global symmetry and a gauge redundancy.

## Core idea

Gauge theory has a small number of sign choices that propagate everywhere. Once the convention for $D_\mu$ is fixed, the transformation law for $A_\mu$, the definition of $F_{\mu\nu}$, the sign of the gauge-boson self-interactions, and the signs of matter vertices are no longer independent.

The fastest way to avoid convention drift is to remember this chain:

| Choice | Consequence |
|---|---|
| Matter derivative $D_\mu=\partial_\mu+igA_\mu^aT^a$ | Matter fields transform as $\psi\mapsto U^{-1}\psi$. |
| Commutator $[D_\mu,D_\nu]=igF_{\mu\nu}$ | $F_{\mu\nu}^a$ contains $-gf^{abc}A_\mu^bA_\nu^c$. |
| Hermitian generators | The structure constants $f^{abc}$ are real and totally antisymmetric for compact simple factors in an orthonormal basis. |
| Hypercharge $Q=T^3+Y$ | The Higgs doublet has $Y=+1/2$, and $e=gs_W=g'c_W$. |

The formulas below are not meant to replace the later derivations. They are the convention anchor for the whole volume.

## Setup and conventions

Unless a page says otherwise, we work in four-dimensional Minkowski spacetime with mostly-minus metric

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
$$

natural units $\hbar=c=1$, and Lorentzian path-integral weight $e^{iS}$. Repeated Lorentz indices are contracted with $\eta_{\mu\nu}$, and repeated adjoint indices are summed.

Gauge fields are written as Lie-algebra-valued matrices

$$
A_\mu=A_\mu^aT^a,
$$

where $T^a$ denotes the generator in the representation acting on the field under discussion. For compact gauge groups we use Hermitian generators. In a representation $R$,

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab},
\qquad
T_R^aT_R^a=C_2(R)\mathbf 1_R.
$$

For $SU(N)$ in the fundamental representation, the default normalization is

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
\qquad
C_F=\frac{N^2-1}{2N},
\qquad
C_A=N.
$$

For $SU(2)$ doublets we use $T^I=\tau^I/2$, where $\tau^I$ are the Pauli matrices. For $SU(3)$ fundamental color triplets we use $T^A=\lambda^A/2$, where $\lambda^A$ are the Gell-Mann matrices.

## Abelian gauge fields

For a field of Abelian charge $q$,

$$
D_\mu\psi=(\partial_\mu+iqA_\mu)\psi.
$$

The local gauge transformation is

$$
\psi(x)\mapsto e^{-iq\alpha(x)}\psi(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x).
$$

Then the covariant derivative transforms covariantly:

$$
D_\mu\psi\mapsto e^{-iq\alpha(x)}D_\mu\psi.
$$

The Abelian field strength is

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
\qquad
[D_\mu,D_\nu]=iqF_{\mu\nu}.
$$

The gauge-field Lagrangian is

$$
\mathcal L_{\mathrm{gauge}}=-\frac14F_{\mu\nu}F^{\mu\nu}.
$$

With the mostly-minus metric,

$$
F_{\mu\nu}F^{\mu\nu}=2(\mathbf B^2-\mathbf E^2),
$$

so the Maxwell Lagrangian is

$$
\mathcal L_{\mathrm{Maxwell}}=\frac12(\mathbf E^2-\mathbf B^2).
$$

For the electron, $q=-e$ with $e>0$, so

$$
D_\mu\psi_e=(\partial_\mu-ieA_\mu)\psi_e.
$$

Equivalently, a particle of electric charge $Qe$ has

$$
D_\mu=\partial_\mu+i e Q A_\mu,
$$

where $Q$ is the charge in proton-charge units. Thus $Q=-1$ for the electron, $Q=+2/3$ for the up quark, and $Q=-1/3$ for the down quark.

## Non-Abelian gauge fields

Let $G$ be a compact gauge group with Hermitian generators $T^a$ in a representation $R$. The matter covariant derivative is

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a.
$$

For a local transformation

$$
U(x)=\exp\{ig\alpha^a(x)T^a\},
$$

the matter field transforms as

$$
\psi(x)\mapsto U^{-1}(x)\psi(x).
$$

The gauge field transforms as

$$
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

With these definitions,

$$
D_\mu\psi\mapsto U^{-1}D_\mu\psi.
$$

The field strength is the curvature of the covariant derivative:

$$
[D_\mu,D_\nu]=igF_{\mu\nu},
\qquad
F_{\mu\nu}=F_{\mu\nu}^aT^a,
$$

with

$$
F_{\mu\nu}
=\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu].
$$

In components this is

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

Under a gauge transformation,

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U.
$$

The Yang–Mills kinetic term is

$$
\mathcal L_{\mathrm{YM}}
=-\frac12\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
=-\frac14F_{\mu\nu}^aF^{a\mu\nu}
$$

when the generators obey $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$.

An adjoint-valued field $X=X^aT^a$ transforms as

$$
X\mapsto U^{-1}XU.
$$

Its covariant derivative is

$$
D_\mu X=\partial_\mu X+ig[A_\mu,X],
$$

or in components

$$
(D_\mu X)^a=\partial_\mu X^a-gf^{abc}A_\mu^bX^c.
$$

This component sign is a common source of mistakes because it follows from the same $D_\mu=\partial_\mu+igA_\mu$ convention as the matter derivative.

## Matter Lagrangians

For a Dirac fermion in representation $R$,

$$
\mathcal L_\psi=\bar\psi(i\gamma^\mu D_\mu-m)\psi.
$$

Since $\psi\mapsto U^{-1}\psi$ and $U$ acts only on internal indices,

$$
\bar\psi\mapsto \bar\psi U,
$$

so $\bar\psi i\gamma^\mu D_\mu\psi$ is gauge invariant.

For a complex scalar in representation $R$,

$$
\mathcal L_\phi=(D_\mu\phi)^\dagger D^\mu\phi-V(\phi),
$$

where $V(\phi)$ must be built from gauge-invariant contractions. In the Standard Model, the Higgs potential is built from $H^\dagger H$.

For a field in a product representation, the full covariant derivative is the sum of the contributions from each gauge factor. For example, a field carrying color, weak isospin, and hypercharge has one term for each factor of the Standard Model gauge algebra.

## Standard Model gauge conventions

The local Standard Model gauge algebra is

$$
\mathfrak{su}(3)_c\oplus\mathfrak{su}(2)_L\oplus\mathfrak{u}(1)_Y.
$$

The covariant derivative on a field of hypercharge $Y$ is

$$
D_\mu
=\partial_\mu
+ig_sG_\mu^A T_c^A
+igW_\mu^I T_L^I
+ig'YB_\mu.
$$

Here $T_c^A$ is an $SU(3)_c$ generator in the field's color representation, $T_L^I$ is an $SU(2)_L$ generator in the field's weak representation, and $Y$ is a number.

We use

$$
Q=T^3+Y.
$$

With this choice, the Standard Model representations for one generation are

| Field | $SU(3)_c$ | $SU(2)_L$ | $Y$ | Electric charges |
|---|---:|---:|---:|---:|
| $Q_L=(u_L,d_L)^T$ | $\mathbf 3$ | $\mathbf 2$ | $+1/6$ | $+2/3,-1/3$ |
| $u_R$ | $\mathbf 3$ | $\mathbf 1$ | $+2/3$ | $+2/3$ |
| $d_R$ | $\mathbf 3$ | $\mathbf 1$ | $-1/3$ | $-1/3$ |
| $L_L=(\nu_L,e_L)^T$ | $\mathbf 1$ | $\mathbf 2$ | $-1/2$ | $0,-1$ |
| $e_R$ | $\mathbf 1$ | $\mathbf 1$ | $-1$ | $-1$ |
| $H=(H^+,H^0)^T$ | $\mathbf 1$ | $\mathbf 2$ | $+1/2$ | $+1,0$ |

This table uses the physical right-handed fermion fields. Later anomaly calculations often rewrite the theory entirely in terms of left-handed Weyl fields, replacing $u_R,d_R,e_R$ by their left-handed conjugates. That rewrite changes the representation labels and hypercharges of those conjugate fields; it does not change the convention $Q=T^3+Y$.

## Electroweak mixing

After electroweak symmetry breaking, define

$$
A_\mu=s_W W_\mu^3+c_W B_\mu,
\qquad
Z_\mu=c_W W_\mu^3-s_W B_\mu,
$$

with

$$
s_W=\sin\theta_W,
\qquad
c_W=\cos\theta_W,
\qquad
 e=gs_W=g'c_W.
$$

Equivalently,

$$
W_\mu^3=s_WA_\mu+c_WZ_\mu,
\qquad
B_\mu=c_WA_\mu-s_WZ_\mu.
$$

The part of the covariant derivative involving the neutral electroweak gauge bosons becomes

$$
igT^3W_\mu^3+ig'YB_\mu
=ieQA_\mu+i\frac{g}{c_W}(T^3-s_W^2Q)Z_\mu.
$$

The photon therefore couples to electric charge $Q$ exactly as in the Abelian convention:

$$
D_\mu\supset ieQA_\mu.
$$

This is the quickest check that the signs in the electroweak mixing convention are consistent.

## Gauge fixing and propagators

Gauge fixing is not part of the definition of a classical gauge theory, but perturbative calculations require a convention. For an Abelian or Yang–Mills gauge field in a covariant gauge, we use

$$
\mathcal L_{\mathrm{gf}}=-\frac{1}{2\xi}(\partial_\mu A^{a\mu})^2.
$$

The free gauge-boson propagator is then

$$
D_{\mu\nu}^{ab}(p)
=\frac{-i\delta^{ab}}{p^2+i\epsilon}
\left(\eta_{\mu\nu}-(1-\xi)\frac{p_\mu p_\nu}{p^2+i\epsilon}\right).
$$

For QED the adjoint index is absent. Feynman gauge is $\xi=1$, and Landau gauge is $\xi=0$. Non-Abelian covariant gauges require Faddeev–Popov ghosts; their normalization is fixed later in the quantization chapter.

Gauge-dependent propagators are not observables. They are coordinate-dependent tools on the redundant configuration space. Physical matrix elements and gauge-invariant correlators must not depend on $\xi$.

## Fast convention checks

A few checks catch most sign errors.

First, the Abelian electron derivative must be

$$
D_\mu\psi_e=(\partial_\mu-ieA_\mu)\psi_e.
$$

Second, the non-Abelian field strength must satisfy

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U.
$$

If a proposed sign convention does not make this true, either the transformation law or the covariant derivative has been mixed with another convention.

Third, the electroweak photon must couple as

$$
D_\mu\supset ieQA_\mu.
$$

If the photon couples to $T^3-Y$, the sign of the $B_\mu$ contribution or the definition of $A_\mu$ has been flipped.

Fourth, with mostly-minus metric the gauge kinetic term is

$$
-\frac14F_{\mu\nu}^aF^{a\mu\nu},
$$

not $+\frac14F^2$.

## Common pitfalls

**Mixing the two non-Abelian sign conventions.** The sign in $D_\mu$ and the sign of the $gf^{abc}A_\mu^bA_\nu^c$ term in $F_{\mu\nu}^a$ are linked. It is fine to use the opposite convention, but not halfway through a calculation.

**Using $Q=T^3+Y/2$ with the $Y$ table above.** The table on this page uses $Q=T^3+Y$. If a source uses $Q=T^3+Y/2$, every hypercharge in the table is twice as large.

**Forgetting the representation.** The symbol $T^a$ means the generator in the representation carried by the field. The same gauge boson couples through different matrices to fundamental, adjoint, singlet, doublet, and conjugate representations.

**Calling gauge-dependent quantities physical.** A propagator in a fixed gauge is useful, but it is not itself an observable. Gauge-parameter dependence must cancel from properly defined physical quantities.

**Confusing right-handed fields with left-handed conjugates.** Standard Model anomaly calculations are usually done with left-handed Weyl fields only. The conjugate of a right-handed field has the conjugate gauge representation and the opposite Abelian charge.

## Relations to other pages

- [Gauge Redundancy Revisited](/gauge-theories-standard-model/gauge-principle/gauge-redundancy-revisited/) explains why these transformation laws identify equivalent descriptions rather than ordinary physical symmetries.
- [Conventions and Normalizations](/foundations/conventions-and-normalizations/) fixes the site-wide metric, Fourier, spinor, propagator, and path-integral conventions used here.

## Research status

The sign, charge, and normalization choices on this page are conventional, not experimental claims. The physics is invariant under consistent translations between conventions.

The local Lie-algebra conventions are textbook-standard. More subtle global questions — the global form of the Standard Model gauge group, large gauge transformations, boundary charges, one-form symmetries, and line-operator spectra — are not fixed by the local formulas alone and are treated later in the volume.

## Exercises

### Exercise 1: Abelian covariance

Using

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
$$

show that $D_\mu\psi\mapsto e^{-iq\alpha}D_\mu\psi$.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
D_\mu'\psi'
=(\partial_\mu+iqA_\mu+iq\partial_\mu\alpha)(e^{-iq\alpha}\psi).
$$

The derivative of the phase gives $-iq(\partial_\mu\alpha)e^{-iq\alpha}\psi$, which cancels the $+iq(\partial_\mu\alpha)$ from the transformed gauge field. The remaining terms are

$$
D_\mu'\psi'=e^{-iq\alpha}(\partial_\mu+iqA_\mu)\psi
=e^{-iq\alpha}D_\mu\psi.
$$

</details>

### Exercise 2: Recover the non-Abelian field strength

Starting from

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
$$

compute $[D_\mu,D_\nu]$ and read off $F_{\mu\nu}^a$.

<details>
<summary><strong>Solution</strong></summary>

Acting on a matter field,

$$
[D_\mu,D_\nu]
=ig(\partial_\mu A_\nu^a-\partial_\nu A_\mu^a)T^a
+(ig)^2A_\mu^aA_\nu^b[T^a,T^b].
$$

Using $(ig)^2=-g^2$ and $[T^a,T^b]=if^{abc}T^c$, the commutator term is

$$
-ig^2f^{abc}A_\mu^aA_\nu^bT^c.
$$

Relabeling dummy indices gives

$$
[D_\mu,D_\nu]
=ig\left(\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c\right)T^a.
$$

Therefore

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

</details>

### Exercise 3: Check the photon coupling after electroweak mixing

Use

$$
W_\mu^3=s_WA_\mu+c_WZ_\mu,
\qquad
B_\mu=c_WA_\mu-s_WZ_\mu,
\qquad
 e=gs_W=g'c_W,
$$

to show that the coefficient of $A_\mu$ in $igT^3W_\mu^3+ig'YB_\mu$ is $ieQ$.

<details>
<summary><strong>Solution</strong></summary>

The photon term is

$$
i(g s_WT^3+g'c_WY)A_\mu.
$$

Using $e=gs_W=g'c_W$, this becomes

$$
ie(T^3+Y)A_\mu=ieQA_\mu.
$$

This is why the convention $Q=T^3+Y$ pairs naturally with the hypercharge table on this page.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, sections on Maxwell theory, spinor electrodynamics, non-Abelian gauge theory, BRST symmetry, anomalies, and the Standard Model.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on gauge invariance, Yang–Mills theory, weak interactions, anomalies, and Standard Model conventions.
- A. Zee, *Quantum Field Theory in a Nutshell*, chapters on gauge invariance, non-Abelian gauge theory, the Anderson–Higgs mechanism, electroweak unification, and QCD.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters on non-Abelian gauge theories, renormalization of gauge theories, and the Standard Model.
- S. Coleman, *Aspects of Symmetry*, especially the Erice lectures on secret symmetry, gauge fields, Faddeev–Popov quantization, and asymptotic freedom.

## Version history

- **2026-06-17:** Initial polished draft for the Gauge Theories and the Standard Model volume.
