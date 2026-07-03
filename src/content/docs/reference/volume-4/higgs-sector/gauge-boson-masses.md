---
title: "Gauge Boson Masses"
description: "Derives the tree-level W, Z, and photon masses from the Standard Model Higgs kinetic term and the neutral electroweak mass matrix."
sidebar:
  label: "Gauge Boson Masses"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§84–87; Schwartz Chs. 28–29; Coleman, Aspects of Symmetry, Ch. 5; Weinberg Vol. II electroweak chapters."
topics:
  - gauge boson masses
  - electroweak symmetry breaking
  - Weinberg angle
  - photon
  - W and Z bosons
canonicalTopics:
  - w-boson-mass
  - z-boson-mass
  - photon-masslessness
  - electroweak-mass-matrix
  - weak-mixing-angle
researchStatus:
  established:
    - "At tree level in the minimal Standard Model, the Higgs kinetic term gives mW = gv/2, mZ = sqrt(g^2 + g'^2) v/2, and mA = 0."
  active:
    - "Precision tests of the tree-level relations require loop corrections, electroweak input schemes, and possible higher-dimensional operators."
---

## Summary

The $W$ and $Z$ masses do not come from explicit Proca mass terms. They come from the gauge-invariant Higgs kinetic term

$$
(D_\mu H)^\dagger(D^\mu H)
$$

after the Higgs doublet has a neutral vacuum expectation value,

$$
\langle H\rangle
=
\frac{1}{\sqrt2}
\begin{pmatrix}
0\\ v
\end{pmatrix}.
$$

Using

$$
D_\mu H=
\left(
\partial_\mu
+igW_\mu^a\frac{\sigma^a}{2}
+ig'\frac12B_\mu
\right)H,
$$

the vacuum contribution is

$$
(D_\mu\langle H\rangle)^\dagger(D^\mu\langle H\rangle)
=
\frac{g^2v^2}{4}W_\mu^+W^{-\mu}
+
\frac{v^2}{8}(gW_\mu^3-g'B_\mu)(gW^{3\mu}-g'B^\mu).
$$

Therefore

$$
m_W=\frac{gv}{2},
\qquad
m_Z=\frac{v}{2}\sqrt{g^2+g'^2},
\qquad
m_A=0.
$$

The massless field is the photon,

$$
A_\mu=\sin\theta_W W_\mu^3+\cos\theta_W B_\mu,
$$

while the massive neutral field is

$$
Z_\mu=\cos\theta_W W_\mu^3-\sin\theta_W B_\mu,
$$

with

$$
\tan\theta_W=\frac{g'}{g},
\qquad
\cos\theta_W=\frac{g}{\sqrt{g^2+g'^2}},
\qquad
\sin\theta_W=\frac{g'}{\sqrt{g^2+g'^2}}.
$$

<figure class="doc-figure" style="--figure-width: 52rem;">

![Gauge-boson masses from the Higgs kinetic term](/figures/gauge-theories-standard-model/higgs-gauge-boson-masses.svg)

<figcaption>

The Higgs kinetic term evaluated on the neutral vacuum splits the electroweak gauge fields into a charged massive pair $W^\pm$, one neutral massive field $Z$, and one neutral massless field $A$. The massless direction is the unbroken generator $Q=T^3+Y$.

</figcaption>
</figure>

## Prerequisites

You should know [Standard Model Higgs Doublet](/gauge-theories-standard-model/higgs-sector/standard-model-higgs-doublet/) and [Higgs Potential](/gauge-theories-standard-model/higgs-sector/higgs-potential/). The essential inputs are

$$
H\sim(\mathbf 1,\mathbf 2)_{1/2},
\qquad
Q=T^3+Y,
\qquad
\langle H\rangle=\frac{1}{\sqrt2}\begin{pmatrix}0\\v\end{pmatrix}.
$$

You should also know [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/) from the Electroweak Theory chapter. That page introduces the same field rotation from the gauge-boson side; here we derive the masses from the Higgs kinetic term.

This page is tree-level and uses the minimal one-doublet Standard Model. Loop-corrected pole masses, electroweak input schemes, and precision observables are not treated here.

## Core idea

A gauge-boson mass term by itself would look like

$$
\frac12m^2A_\mu A^\mu
$$

for a real vector field. Such a term is not gauge invariant for a Yang–Mills gauge field. The Higgs mechanism avoids this problem because the gauge-invariant kinetic term

$$
(D_\mu H)^\dagger(D^\mu H)
$$

contains two kinds of terms after expanding around the vacuum:

$$
\text{derivatives of fluctuations}
\quad+\quad
\text{quadratic terms in gauge fields}.
$$

The quadratic gauge-field terms are mass terms. Gauge redundancy is still present; the spectrum has reorganized. The would-be Goldstone modes supply the longitudinal polarizations of the massive vector bosons.

The one-line version is:

$$
\text{mass matrix for gauge bosons}
=
\text{norm of gauge generators acting on the Higgs vacuum}.
$$

If a generator annihilates the vacuum, its gauge boson remains massless. If it moves the vacuum, its gauge boson becomes massive.

## Setup and conventions

The Higgs-sector kinetic term is

$$
\mathcal L_{\rm kin,H}=(D_\mu H)^\dagger(D^\mu H),
$$

where

$$
D_\mu H=
\left(
\partial_\mu+igW_\mu^aT^a+ig'YB_\mu
\right)H,
\qquad
T^a=\frac{\sigma^a}{2},
\qquad
Y_H=\frac12.
$$

We use the Higgs vacuum representative

$$
H_0\equiv\langle H\rangle
=
\frac{1}{\sqrt2}\begin{pmatrix}0\\v\end{pmatrix}.
$$

Because $H_0$ is constant,

$$
D_\mu H_0=i\left(gW_\mu^aT^a+g'\frac12B_\mu\right)H_0.
$$

The needed actions of the $SU(2)$ generators are

$$
T^1H_0=\frac{v}{2\sqrt2}\begin{pmatrix}1\\0\end{pmatrix},
\qquad
T^2H_0=\frac{v}{2\sqrt2}\begin{pmatrix}-i\\0\end{pmatrix},
\qquad
T^3H_0=-\frac{v}{2\sqrt2}\begin{pmatrix}0\\1\end{pmatrix}.
$$

The hypercharge action is

$$
YH_0=\frac12H_0
=\frac{v}{2\sqrt2}\begin{pmatrix}0\\1\end{pmatrix}.
$$

Thus the charged gauge fields act on the upper component, while the neutral fields act on the lower component.

## Charged gauge bosons

The charged part of the covariant derivative on the vacuum is

$$
i g(W_\mu^1T^1+W_\mu^2T^2)H_0
=
\frac{igv}{2\sqrt2}
\begin{pmatrix}
W_\mu^1-iW_\mu^2\\0
\end{pmatrix}.
$$

Define

$$
W_\mu^\pm=\frac{1}{\sqrt2}(W_\mu^1\mp iW_\mu^2).
$$

Then

$$
W_\mu^1-iW_\mu^2=\sqrt2W_\mu^+.
$$

The charged contribution to the kinetic term is

$$
\frac{g^2v^2}{8}\left(W_\mu^1W^{1\mu}+W_\mu^2W^{2\mu}\right)
=
\frac{g^2v^2}{4}W_\mu^+W^{-\mu}.
$$

A complex charged vector has mass term

$$
m_W^2W_\mu^+W^{-\mu},
$$

so

$$
m_W^2=\frac{g^2v^2}{4},
\qquad
m_W=\frac{gv}{2}.
$$

This is the first place where the Higgs vacuum scale becomes directly measurable: the weak charged-current range is set by $m_W^{-1}$.

## Neutral gauge bosons

The neutral part is

$$
i(gW_\mu^3T^3+g'YB_\mu)H_0
=
\frac{iv}{2\sqrt2}(-gW_\mu^3+g'B_\mu)
\begin{pmatrix}0\\1\end{pmatrix}.
$$

Therefore

$$
\mathcal L_{\rm neutral\ mass}
=
\frac{v^2}{8}(gW_\mu^3-g'B_\mu)(gW^{3\mu}-g'B^\mu).
$$

In matrix form,

$$
\mathcal L_{\rm neutral\ mass}
=
\frac12
\begin{pmatrix}W_\mu^3&B_\mu\end{pmatrix}
M_0^2
\begin{pmatrix}W^{3\mu}\\B^\mu\end{pmatrix},
$$

where

$$
M_0^2=\frac{v^2}{4}
\begin{pmatrix}
g^2&-gg'\\
-gg'&g'^2
\end{pmatrix}.
$$

This matrix has determinant zero,

$$
\det M_0^2=0,
$$

so one neutral gauge boson remains massless. Its eigenvalues are

$$
0,
\qquad
\frac{v^2}{4}(g^2+g'^2).
$$

The massive eigenvector is proportional to

$$
gW_\mu^3-g'B_\mu,
$$

and the massless eigenvector is proportional to

$$
g'W_\mu^3+gB_\mu.
$$

Define the weak mixing angle by

$$
\cos\theta_W=\frac{g}{\sqrt{g^2+g'^2}},
\qquad
\sin\theta_W=\frac{g'}{\sqrt{g^2+g'^2}}.
$$

Then

$$
Z_\mu=\cos\theta_W W_\mu^3-\sin\theta_W B_\mu,
$$

and

$$
A_\mu=\sin\theta_W W_\mu^3+\cos\theta_W B_\mu.
$$

The neutral mass term becomes

$$
\mathcal L_{\rm neutral\ mass}
=
\frac12m_Z^2Z_\mu Z^\mu,
$$

with

$$
m_Z^2=\frac{v^2}{4}(g^2+g'^2),
\qquad
m_Z=\frac{v}{2}\sqrt{g^2+g'^2}.
$$

The photon has

$$
m_A=0.
$$

## Why the photon is massless

The massless field is not an accident of diagonalizing a $2\times2$ matrix. It is the gauge boson of the unbroken generator.

For the neutral Higgs vacuum,

$$
T^3H_0=-\frac12H_0,
\qquad
YH_0=+\frac12H_0.
$$

Therefore

$$
QH_0=(T^3+Y)H_0=0.
$$

The generator $Q=T^3+Y$ preserves the vacuum. Its gauge field is the photon. The orthogonal neutral generator moves the vacuum, so its gauge boson becomes massive.

This gives a useful diagnostic:

$$
\text{unbroken gauge generator}
\quad\Longleftrightarrow\quad
\text{zero mode of the gauge-boson mass matrix}.
$$

The electromagnetic coupling is

$$
e=g\sin\theta_W=g'\cos\theta_W
=
\frac{gg'}{\sqrt{g^2+g'^2}}.
$$

This relation is often the cleanest way to remember the normalization of the photon direction.

## The tree-level mass relation

The mass formulas imply

$$
m_W=m_Z\cos\theta_W.
$$

Equivalently, the tree-level rho parameter is

$$
\rho\equiv\frac{m_W^2}{m_Z^2\cos^2\theta_W}=1.
$$

This equality is a special feature of the minimal Higgs doublet representation at tree level. It is often described as a consequence of an approximate custodial symmetry. Precision electroweak physics studies controlled deviations from this simple relation due to loops, input-scheme choices, and possible new physics.

The point for this page is more basic: the representation and vacuum direction of one Higgs doublet are restrictive enough to determine the ratio of $W$ and $Z$ masses in terms of the weak mixing angle.

## Relation to the Fermi constant

At momenta much smaller than $m_W$, charged-current weak interactions are described by the Fermi theory. Tree-level $W$ exchange gives

$$
\frac{G_F}{\sqrt2}=\frac{g^2}{8m_W^2}.
$$

Using

$$
m_W^2=\frac{g^2v^2}{4},
$$

we get

$$
\frac{G_F}{\sqrt2}=\frac{1}{2v^2},
$$

or

$$
G_F=\frac{1}{\sqrt2v^2}.
$$

Thus the same vacuum scale $v$ that appears in the Higgs potential also controls the strength of low-energy weak interactions. This is a tree-level relation; precision work uses radiative corrections and a specified electroweak input scheme.

## Gauge choices and Goldstone modes

The derivation above used only the vacuum contribution to $|D_\mu H|^2$. It did not require unitary gauge, although unitary gauge makes the final spectrum visually simple.

In a general parametrization,

$$
H(x)=\exp\left(\frac{iG^a(x)\sigma^a}{v}\right)
\frac{1}{\sqrt2}\begin{pmatrix}0\\v+h(x)\end{pmatrix}
$$

schematically displays the radial field $h$ and the three angular would-be Goldstone modes. In unitary gauge, the angular fields are removed from $H$ and appear as longitudinal polarizations of $W^\pm$ and $Z$. In covariant $R_\xi$ gauges, the Goldstone fields remain explicit and have gauge-dependent masses, while the physical vector masses remain the values derived above.

This is why the Higgs mechanism should not be thought of as “breaking gauge symmetry.” The gauge redundancy remains. The physical spectrum changes.

## Common pitfalls

**Writing explicit mass terms before symmetry breaking.** Terms such as $m^2W_\mu^aW^{a\mu}$ are not electroweak-gauge invariant. The mass terms above arise from the gauge-invariant operator $(D_\mu H)^\dagger(D^\mu H)$ evaluated around a nonzero vacuum.

**Forgetting the factor of one half for neutral real fields.** A real vector mass term is $\frac12m^2Z_\mu Z^\mu$, while a charged complex vector mass term is $m^2W_\mu^+W^{-\mu}$. This is a classic factor-of-two trap.

**Confusing $B_\mu$ with the photon.** Before electroweak symmetry breaking, $B_\mu$ is the hypercharge gauge field. The photon is the massless mixture $A_\mu=\sin\theta_WW_\mu^3+\cos\theta_WB_\mu$.

**Thinking the photon is massless because $g'$ is small.** The photon is massless because $Q=T^3+Y$ annihilates the Higgs vacuum. The zero eigenvalue is exact at tree level in the minimal Standard Model and is protected by unbroken electromagnetic gauge invariance.

**Using $Q=T^3+Y/2$ without translating hypercharge.** This volume uses $Q=T^3+Y$. In the alternative convention $Q=T^3+Y_{\rm alt}/2$, the Higgs doublet has $Y_{\rm alt}=1$ instead of $Y=1/2$.

**Treating $m_W=m_Z\cos\theta_W$ as an all-purpose exact identity.** It is a tree-level minimal-Standard-Model relation. Precision observables require loop corrections and an input scheme.

## Relations to other pages

- [Standard Model Higgs Doublet](/gauge-theories-standard-model/higgs-sector/standard-model-higgs-doublet/) defines the Higgs representation and the electrically neutral vacuum used here.
- [Higgs Potential](/gauge-theories-standard-model/higgs-sector/higgs-potential/) explains how $v$ and $m_h$ arise from the scalar potential.
- [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/) introduces the same field basis from the electroweak gauge-sector viewpoint.
- [Fermi Theory Limit](/gauge-theories-standard-model/electroweak/fermi-theory-limit/) derives the low-energy weak interaction that fixes $v$ at tree level through $G_F$.
- [Higgs Boson Couplings](/gauge-theories-standard-model/higgs-sector/higgs-boson-couplings/) expands the same mass terms with $v\mapsto v+h$ to obtain $hWW$, $hZZ$, $hhWW$, and $hhZZ$ interactions.

## Research status

The tree-level mass derivation is textbook-standard. Its main assumptions are:

- one elementary Higgs doublet with $Y=1/2$;
- a neutral vacuum preserving $U(1)_{\rm em}$;
- the renormalizable Standard Model gauge kinetic and Higgs kinetic terms;
- tree-level matching between Lagrangian parameters and masses.

Research-level refinements start immediately beyond this page. Precision electroweak theory defines $m_W$, $m_Z$, $\sin^2\theta_W$, $\alpha$, and $G_F$ in specific schemes and includes loop corrections. SMEFT adds higher-dimensional operators such as $(H^\dagger D_\mu H)^\ast(H^\dagger D^\mu H)$, which can shift the simple tree-level relations. Extended Higgs sectors can also change the rho parameter at tree level unless their representations are arranged carefully.

## Exercises

### Exercise 1: Charged mass term

Starting from

$$
T^1H_0=\frac{v}{2\sqrt2}\begin{pmatrix}1\\0\end{pmatrix},
\qquad
T^2H_0=\frac{v}{2\sqrt2}\begin{pmatrix}-i\\0\end{pmatrix},
$$

show that the charged part of $(D_\mu H_0)^\dagger(D^\mu H_0)$ is

$$
\frac{g^2v^2}{4}W_\mu^+W^{-\mu}.
$$

<details>
<summary><strong>Solution</strong></summary>

The charged contribution is

$$
i g(W_\mu^1T^1+W_\mu^2T^2)H_0
=
\frac{igv}{2\sqrt2}
\begin{pmatrix}W_\mu^1-iW_\mu^2\\0\end{pmatrix}.
$$

Taking the norm gives

$$
\frac{g^2v^2}{8}(W_\mu^1+iW_\mu^2)(W^{1\mu}-iW^{2\mu}).
$$

With

$$
W_\mu^+=\frac{W_\mu^1-iW_\mu^2}{\sqrt2},
\qquad
W_\mu^-=\frac{W_\mu^1+iW_\mu^2}{\sqrt2},
$$

this becomes

$$
\frac{g^2v^2}{4}W_\mu^-W^{+\mu}
=
\frac{g^2v^2}{4}W_\mu^+W^{-\mu}.
$$

Therefore $m_W^2=g^2v^2/4$.

</details>

### Exercise 2: Diagonalize the neutral mass matrix

Diagonalize

$$
M_0^2=\frac{v^2}{4}
\begin{pmatrix}
g^2&-gg'\\
-gg'&g'^2
\end{pmatrix}.
$$

<details>
<summary><strong>Solution</strong></summary>

The determinant is zero:

$$
\det M_0^2=\frac{v^4}{16}(g^2g'^2-g^2g'^2)=0.
$$

The trace is

$$
\operatorname{tr}M_0^2=\frac{v^2}{4}(g^2+g'^2).
$$

Thus the eigenvalues are

$$
0,
\qquad
\frac{v^2}{4}(g^2+g'^2).
$$

For the zero eigenvalue, solve

$$
g^2x-gg'y=0,
$$

so $x/y=g'/g$. The massless eigenvector is proportional to $(g',g)$, giving

$$
A_\mu=\frac{g'W_\mu^3+gB_\mu}{\sqrt{g^2+g'^2}}.
$$

The massive orthogonal combination is

$$
Z_\mu=\frac{gW_\mu^3-g'B_\mu}{\sqrt{g^2+g'^2}}.
$$

</details>

### Exercise 3: Show that electromagnetism is unbroken

Show that $QH_0=0$ for $Q=T^3+Y$ and $Y_H=1/2$.

<details>
<summary><strong>Solution</strong></summary>

For

$$
H_0=\frac{1}{\sqrt2}\begin{pmatrix}0\\v\end{pmatrix},
$$

we have

$$
T^3H_0=
\frac{\sigma^3}{2}H_0
=
-\frac12H_0,
$$

and

$$
YH_0=\frac12H_0.
$$

Therefore

$$
QH_0=(T^3+Y)H_0=0.
$$

The gauge boson of this unbroken generator is the photon.

</details>

### Exercise 4: Derive the tree-level rho parameter

Using

$$
m_W=\frac{gv}{2},
\qquad
m_Z=\frac{v}{2}\sqrt{g^2+g'^2},
\qquad
\cos\theta_W=\frac{g}{\sqrt{g^2+g'^2}},
$$

show that

$$
\rho=\frac{m_W^2}{m_Z^2\cos^2\theta_W}=1.
$$

<details>
<summary><strong>Solution</strong></summary>

Compute the denominator:

$$
m_Z^2\cos^2\theta_W
=
\frac{v^2}{4}(g^2+g'^2)\frac{g^2}{g^2+g'^2}
=
\frac{g^2v^2}{4}.
$$

This equals $m_W^2$, so

$$
\rho=1.
$$

</details>

### Exercise 5: Relate the weak scale to the Fermi constant

Given

$$
\frac{G_F}{\sqrt2}=\frac{g^2}{8m_W^2},
\qquad
m_W^2=\frac{g^2v^2}{4},
$$

derive $G_F=1/(\sqrt2v^2)$.

<details>
<summary><strong>Solution</strong></summary>

Substitute the mass formula into the matching relation:

$$
\frac{G_F}{\sqrt2}
=
\frac{g^2}{8(g^2v^2/4)}
=
\frac{1}{2v^2}.
$$

Multiplying by $\sqrt2$ gives

$$
G_F=\frac{1}{\sqrt2v^2}.
$$

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§84–87, for spontaneous breaking of gauge symmetries and the Standard Model gauge and Higgs sector.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 28–29, for the Higgs mechanism, electroweak symmetry breaking, weak currents, and the Standard Model mass relations.
- Coleman, *Aspects of Symmetry*, Ch. 5, “Secret Symmetry,” for the conceptual distinction between ordinary spontaneous symmetry breaking and the Higgs phenomenon.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak theory and spontaneously broken gauge theories.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*, for a standard perturbative treatment of the electroweak gauge-boson masses.
- Burgess, *Introduction to Effective Field Theory*, Chs. 7 and 9, for the Fermi-theory matching and the Standard Model as an effective field theory.

## Version history

- **2026-06-18:** Initial standardized page.
