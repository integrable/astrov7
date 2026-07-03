---
title: "Electroweak Gauge-Boson Masses"
description: "Derives the W and Z boson masses, photon masslessness, weak mixing angle, electric charge relation, and tree-level rho parameter from the Standard Model Higgs kinetic term."
sidebar:
  label: "Electroweak Gauge-Boson Masses"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki §87; Schwartz §29.1; Weinberg Vol. II electroweak material; Coleman, Secret Symmetry."
topics:
  - electroweak symmetry breaking
  - Higgs doublet
  - W boson mass
  - Z boson mass
  - photon
  - weak mixing angle
  - rho parameter
canonicalTopics:
  - electroweak-gauge-boson-masses
  - weak-mixing-angle
  - photon-z-mixing
  - rho-parameter
researchStatus:
  established:
    - "At tree level in the Standard Model with one Higgs doublet, the Higgs kinetic term gives m_W = gv/2, m_Z = v sqrt(g^2+g'^2)/2, and a massless photon."
  active:
    - "Loop corrections, precision electroweak observables, oblique parameters, SMEFT corrections, and custodial-symmetry tests refine these tree-level relations."
---

## Summary

This page derives the electroweak gauge-boson masses from the Standard Model Higgs kinetic term

$$
(D_\mu H)^\dagger D^\mu H.
$$

We use the convention

$$
Q=T^3+Y,
$$

so the Higgs doublet has hypercharge

$$
Y_H=\frac12,
\qquad
H=\begin{pmatrix}H^+\\H^0\end{pmatrix}.
$$

The electroweak covariant derivative is

$$
D_\mu
=
\partial_\mu
+ig\frac{\tau^a}{2}W^a_\mu
+ig'YB_\mu.
$$

In unitary gauge,

$$
H(x)=\frac1{\sqrt2}\begin{pmatrix}0\\v+h(x)\end{pmatrix}.
$$

The quadratic terms in $|D_\mu H|^2$ give

$$
m_W=\frac{gv}{2},
\qquad
m_Z=\frac{v}{2}\sqrt{g^2+g'^2},
\qquad
m_\gamma=0.
$$

The neutral gauge bosons are related by

$$
\begin{pmatrix}Z_\mu\\A_\mu\end{pmatrix}
=
\begin{pmatrix}
\cos\theta_W&-\sin\theta_W\\
\sin\theta_W&\cos\theta_W
\end{pmatrix}
\begin{pmatrix}W^3_\mu\\B_\mu\end{pmatrix},
$$

with

$$
\sin\theta_W=\frac{g'}{\sqrt{g^2+g'^2}},
\qquad
\cos\theta_W=\frac{g}{\sqrt{g^2+g'^2}},
\qquad
e=g\sin\theta_W=g'\cos\theta_W.
$$

<figure class="doc-figure" style="--figure-width: 44rem;">

![Electroweak gauge-boson mass derivation](/figures/gauge-theories-standard-model/electroweak-gauge-boson-mass-flow.svg)

<figcaption>

The Higgs doublet vacuum separates the electroweak gauge fields into a charged sector with massive $W^\pm$ bosons and a neutral sector where one combination becomes the massive $Z$ boson and the orthogonal combination remains the photon.

</figcaption>
</figure>

This is the Standard Model version of the Higgs mechanism. The calculation is short, but it encodes a large amount of physics: the unbroken electromagnetic gauge group, the weak mixing angle, the relation between $m_W$ and $m_Z$, and the reason the photon is massless.

## Setup

The gauge group before symmetry breaking is locally

$$
SU(2)_L\times U(1)_Y.
$$

The gauge fields are

$$
W^a_\mu,
\qquad a=1,2,3,
$$

for $SU(2)_L$, and

$$
B_\mu
$$

for hypercharge. The Higgs field is a complex $SU(2)_L$ doublet with $Y=1/2$:

$$
H=\begin{pmatrix}H^+\\H^0\end{pmatrix},
\qquad
T^a=\frac{\tau^a}{2},
\qquad
Y_H=\frac12.
$$

The electric charge is

$$
Q=T^3+Y.
$$

Indeed,

$$
QH^+=\left(\frac12+\frac12\right)H^+=H^+,
\qquad
QH^0=\left(-\frac12+\frac12\right)H^0=0.
$$

This is why the neutral Higgs component can acquire a vacuum expectation value without breaking electromagnetism.

In unitary gauge, write

$$
H(x)=\frac1{\sqrt2}\begin{pmatrix}0\\v+h(x)\end{pmatrix}.
$$

For mass terms, set $h=0$ and compute

$$
(D_\mu\langle H\rangle)^\dagger D^\mu\langle H\rangle,
\qquad
\langle H\rangle=\frac1{\sqrt2}\begin{pmatrix}0\\v\end{pmatrix}.
$$

## Acting on the Higgs vacuum

Because the vacuum is constant, the derivative term vanishes:

$$
D_\mu\langle H\rangle
=
\left(ig\frac{\tau^a}{2}W^a_\mu+ig'\frac12B_\mu\right)
\frac1{\sqrt2}\begin{pmatrix}0\\v\end{pmatrix}.
$$

Use

$$
\frac{\tau^1}{2}\begin{pmatrix}0\\1\end{pmatrix}
=
\frac12\begin{pmatrix}1\\0\end{pmatrix},
\qquad
\frac{\tau^2}{2}\begin{pmatrix}0\\1\end{pmatrix}
=
\frac12\begin{pmatrix}-i\\0\end{pmatrix},
\qquad
\frac{\tau^3}{2}\begin{pmatrix}0\\1\end{pmatrix}
=
\frac12\begin{pmatrix}0\\-1\end{pmatrix}.
$$

The hypercharge generator acts as

$$
Y\begin{pmatrix}0\\1\end{pmatrix}
=
\frac12\begin{pmatrix}0\\1\end{pmatrix}.
$$

Therefore

$$
D_\mu\langle H\rangle
=
\frac{iv}{2\sqrt2}
\begin{pmatrix}
g(W^1_\mu-iW^2_\mu)\\
-gW^3_\mu+g'B_\mu
\end{pmatrix}.
$$

Taking the norm gives

$$
(D_\mu\langle H\rangle)^\dagger D^\mu\langle H\rangle
=
\frac{v^2}{8}
\left[
 g^2\big((W^1_\mu)^2+(W^2_\mu)^2\big)
+
(gW^3_\mu-g'B_\mu)^2
\right].
$$

This is the full gauge-boson mass term.

## Charged sector

Define

$$
W^\pm_\mu
=
\frac{1}{\sqrt2}(W^1_\mu\mp iW^2_\mu).
$$

Then

$$
(W^1_\mu)^2+(W^2_\mu)^2=2W^+_\mu W^{-\mu}.
$$

The charged part of the mass Lagrangian is

$$
\frac{v^2}{8}g^2\left((W^1)^2+(W^2)^2\right)
=
\frac{g^2v^2}{4}W^+_\mu W^{-\mu}.
$$

For a complex charged vector field, the mass term is

$$
m_W^2W^+_\mu W^{-\mu}.
$$

Thus

$$
m_W^2=\frac{g^2v^2}{4},
\qquad
m_W=\frac{gv}{2}.
$$

The two charged gauge bosons $W^+$ and $W^-$ are massive and carry electric charges $+1$ and $-1$.

## Neutral sector

The neutral mass term is

$$
\mathcal L_{\rm mass}^{\rm neutral}
=
\frac{v^2}{8}(gW^3_\mu-g'B_\mu)^2.
$$

Equivalently,

$$
\mathcal L_{\rm mass}^{\rm neutral}
=
\frac12
\begin{pmatrix}W^3_\mu&B_\mu\end{pmatrix}
\frac{v^2}{4}
\begin{pmatrix}
g^2&-gg'\\
-gg'&g'^2
\end{pmatrix}
\begin{pmatrix}W^{3\mu}\\B^\mu\end{pmatrix}.
$$

The matrix

$$
M_0^2
=
\frac{v^2}{4}
\begin{pmatrix}
g^2&-gg'\\
-gg'&g'^2
\end{pmatrix}
$$

has determinant zero:

$$
\det M_0^2
=
\frac{v^4}{16}(g^2g'^2-g^2g'^2)=0.
$$

So one neutral gauge boson remains massless.

The massive eigenvector is proportional to

$$
\begin{pmatrix}g\\-g'\end{pmatrix},
$$

and the massless eigenvector is proportional to

$$
\begin{pmatrix}g'\\g\end{pmatrix}.
$$

Define

$$
\cos\theta_W=\frac{g}{\sqrt{g^2+g'^2}},
\qquad
\sin\theta_W=\frac{g'}{\sqrt{g^2+g'^2}}.
$$

Then

$$
Z_\mu=\cos\theta_W W^3_\mu-\sin\theta_W B_\mu,
$$

and

$$
A_\mu=\sin\theta_W W^3_\mu+\cos\theta_W B_\mu.
$$

The neutral mass term becomes

$$
\mathcal L_{\rm mass}^{\rm neutral}
=
\frac{v^2}{8}(g^2+g'^2)Z_\mu Z^\mu.
$$

For a real vector field, the mass term is $\frac12m_Z^2Z_\mu Z^\mu$. Therefore

$$
m_Z^2=\frac{v^2}{4}(g^2+g'^2),
\qquad
m_Z=\frac{v}{2}\sqrt{g^2+g'^2}.
$$

The orthogonal field $A_\mu$ has

$$
m_A=0.
$$

It is the photon.

## Electric charge

Before symmetry breaking, the neutral gauge interaction for a field with weak isospin $T^3$ and hypercharge $Y$ is

$$
igT^3W^3_\mu+ig'YB_\mu.
$$

Invert the mixing equations:

$$
W^3_\mu=\cos\theta_W Z_\mu+\sin\theta_W A_\mu,
\qquad
B_\mu=-\sin\theta_W Z_\mu+\cos\theta_W A_\mu.
$$

The coefficient of $A_\mu$ is

$$
i(g\sin\theta_W T^3+g'\cos\theta_WY)A_\mu.
$$

For this to be the electromagnetic coupling

$$
ieQA_\mu=ie(T^3+Y)A_\mu,
$$

we need

$$
e=g\sin\theta_W=g'\cos\theta_W.
$$

This follows automatically from the definitions of $\sin\theta_W$ and $\cos\theta_W$:

$$
g\sin\theta_W
=
\frac{gg'}{\sqrt{g^2+g'^2}}
=
g'\cos\theta_W.
$$

The massless gauge field is the one associated with the unbroken generator $Q=T^3+Y$.

## Tree-level rho parameter

The mass formulas imply

$$
m_W^2=\frac{g^2v^2}{4},
\qquad
m_Z^2=\frac{(g^2+g'^2)v^2}{4},
\qquad
\cos^2\theta_W=\frac{g^2}{g^2+g'^2}.
$$

Therefore

$$
\rho
\equiv
\frac{m_W^2}{m_Z^2\cos^2\theta_W}
=
1.
$$

This tree-level relation is a consequence of the Higgs representation and the custodial symmetry structure of the minimal Higgs sector. It is not an arbitrary numerical coincidence. Precision electroweak physics is, in part, the art of measuring how quantum corrections and possible new physics deform relations like this.

## Where the Goldstone modes went

The Higgs doublet has four real scalar degrees of freedom. After electroweak symmetry breaking,

$$
SU(2)_L\times U(1)_Y\longrightarrow U(1)_{\rm em}.
$$

There are three broken generators, so three would-be Goldstone modes are absorbed into the longitudinal polarizations of

$$
W^+,
\qquad
W^-,
\qquad
Z.
$$

One real scalar remains: the physical Higgs boson $h$.

Degree-of-freedom counting before and after symmetry breaking is

| before | physical degrees of freedom | after | physical degrees of freedom |
|---|---:|---|---:|
| four massless electroweak gauge bosons | $4\times2=8$ | photon | $2$ |
| Higgs doublet | $4$ | $W^\pm$ and $Z$ | $3\times3=9$ |
|  |  | Higgs boson | $1$ |
| total | $12$ | total | $12$ |

The counting is a useful sanity check: the Higgs mechanism reorganizes fields; it does not create or destroy physical degrees of freedom.

## Checks

### Unbroken generator check

The Higgs vacuum is neutral under

$$
Q=T^3+Y.
$$

Indeed,

$$
Q\begin{pmatrix}0\\v/\sqrt2\end{pmatrix}
=
\left(-\frac12+\frac12\right)
\begin{pmatrix}0\\v/\sqrt2\end{pmatrix}
=0.
$$

That is why electromagnetism survives.

### Zero determinant check

The neutral mass matrix has zero determinant. This guarantees a massless photon at tree level:

$$
\det
\begin{pmatrix}
g^2&-gg'\\
-gg'&g'^2
\end{pmatrix}
=0.
$$

### Hypercharge normalization check

This page uses $Q=T^3+Y$. In the alternative convention $Q=T^3+Y_{\rm alt}/2$, the Higgs has $Y_{\rm alt}=1$, and the coupling to the Abelian field is often written with $g'Y_{\rm alt}/2$. The physics is the same, but mixing formulas look wrong if the two conventions are mixed.

## Common mistakes

**Mistake 1: Missing the factor of $1/2$ in $T^a=\tau^a/2$.** This is the classic way to get $m_W=gv$ instead of $m_W=gv/2$.

**Mistake 2: Treating the neutral mass term as a diagonal mass term for $W^3$ and $B$.** The expression $(gW^3-g'B)^2$ has an off-diagonal mixing term. The mass eigenstates are $Z$ and $A$, not $W^3$ and $B$.

**Mistake 3: Forgetting that a real vector mass term has $\frac12m^2Z_\mu Z^\mu$.** The charged $W^+W^-$ mass term and the real $ZZ$ mass term have different visible factors.

**Mistake 4: Calling $B_\mu$ the photon.** The hypercharge gauge field $B_\mu$ is not the photon. The photon is $A_\mu=s_WW^3_\mu+c_WB_\mu$ after electroweak symmetry breaking.

**Mistake 5: Mixing hypercharge conventions.** With $Q=T^3+Y$, the Higgs hypercharge is $Y=1/2$. With $Q=T^3+Y/2$, it is $Y=1$. Pick one and stick to it.

## Exercises

### Exercise 1: Derive the neutral mass matrix

Starting from

$$
\frac{v^2}{8}(gW^3_\mu-g'B_\mu)^2,
$$

write the expression as

$$
\frac12
\begin{pmatrix}W^3_\mu&B_\mu\end{pmatrix}
M_0^2
\begin{pmatrix}W^{3\mu}\\B^\mu\end{pmatrix}.
$$

<details><summary><strong>Solution</strong></summary>

Expand the square:

$$
\frac{v^2}{8}
\left[g^2W^3_\mu W^{3\mu}-2gg'W^3_\mu B^\mu+g'^2B_\mu B^\mu\right].
$$

Comparing with

$$
\frac12
\begin{pmatrix}W^3&B\end{pmatrix}
M_0^2
\begin{pmatrix}W^3\\B\end{pmatrix},
$$

we get

$$
M_0^2
=
\frac{v^2}{4}
\begin{pmatrix}
g^2&-gg'\\
-gg'&g'^2
\end{pmatrix}.
$$

</details>

### Exercise 2: Find the massless eigenstate

Show that the vector

$$
\begin{pmatrix}g'\\g\end{pmatrix}
$$

is a zero eigenvector of the neutral mass matrix.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\begin{pmatrix}
g^2&-gg'\\
-gg'&g'^2
\end{pmatrix}
\begin{pmatrix}g'\\g\end{pmatrix}
=
\begin{pmatrix}g^2g'-gg'g\\-gg'g'+g'^2g\end{pmatrix}
=
\begin{pmatrix}0\\0\end{pmatrix}.
$$

Therefore the massless field is proportional to

$$
g'W^3_\mu+gB_\mu.
$$

After normalization this is

$$
A_\mu=s_WW^3_\mu+c_WB_\mu.
$$

</details>

### Exercise 3: Verify the rho parameter

Using

$$
m_W=\frac{gv}{2},
\qquad
m_Z=\frac{v}{2}\sqrt{g^2+g'^2},
\qquad
c_W=\frac{g}{\sqrt{g^2+g'^2}},
$$

show that $\rho=1$ at tree level.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
\rho=\frac{m_W^2}{m_Z^2c_W^2}.
$$

Substitute:

$$
m_W^2=\frac{g^2v^2}{4},
\qquad
m_Z^2c_W^2=\frac{(g^2+g'^2)v^2}{4}\frac{g^2}{g^2+g'^2}
=\frac{g^2v^2}{4}.
$$

Therefore

$$
\rho=1.
$$

</details>

## Related pages

- [Electroweak Symmetry Breaking](/gauge-theories-standard-model/electroweak/electroweak-symmetry-breaking/) gives the conceptual account of the breaking pattern.
- [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/) explains the physical mass eigenstates.
- [Gauge Boson Masses](/gauge-theories-standard-model/higgs-sector/gauge-boson-masses/) derives the same result in the Higgs Sector chapter.
- [Abelian Higgs Mechanism](/gauge-theories-standard-model/calculation-library/abelian-higgs-mechanism/) gives the simpler one-gauge-field version of the calculation.
- [Fermi Theory from W Exchange](/gauge-theories-standard-model/calculation-library/fermi-theory-from-w-exchange/) will use $m_W$ to match the low-energy weak interaction.

## References

- Srednicki, *Quantum Field Theory*, §87.
- Schwartz, *Quantum Field Theory and the Standard Model*, §29.1.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, electroweak theory chapters.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry.”

## Version history

- **2026-06-19:** Initial polished draft. Derived the charged and neutral electroweak gauge-boson mass terms, photon–$Z$ mixing, electric charge relation, and tree-level $\rho=1$ relation.
