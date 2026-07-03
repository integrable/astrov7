---
title: "Electroweak Symmetry Breaking"
description: "Derives how the Higgs doublet vacuum leaves electromagnetic U(1) unbroken, gives masses to W± and Z, and keeps the photon massless."
sidebar:
  label: "Electroweak Symmetry Breaking"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §§84–87; Schwartz Chs. 28–29; Weinberg Vol. II electroweak chapters; Coleman, Aspects of Symmetry, Ch. 5."
topics:
  - electroweak symmetry breaking
  - Higgs doublet
  - weak mixing
  - gauge-boson masses
  - Standard Model
canonicalTopics:
  - electroweak-symmetry-breaking
  - higgs-mechanism
  - photon-z-mixing
  - gauge-boson-mass-matrix
  - unbroken-electromagnetism
researchStatus:
  established:
    - "In the minimal Standard Model, a complex Higgs doublet with hypercharge 1/2 leaves U(1)em unbroken and gives tree-level masses to W± and Z while the photon remains massless."
  active:
    - "The microscopic origin of the Higgs potential, electroweak naturalness, finite-temperature electroweak symmetry breaking, and precision tests of Higgs and electroweak couplings remain active research interfaces."
---

## Summary

Electroweak symmetry breaking is the step that turns the gauge-basis fields of $SU(2)_L\times U(1)_Y$ into the physical photon, $W^\pm$, and $Z$ bosons. The input is the Higgs doublet

$$
H(x)=\binom{H^+(x)}{H^0(x)},
\qquad
H\sim (\mathbf 1,\mathbf 2)_{1/2},
$$

where the subscript is hypercharge in the convention

$$
Q=T^3+Y.
$$

The Higgs potential has a continuum of classical minima with nonzero $H^\dagger H$. A convenient gauge choice points the vacuum in the lower component,

$$
\langle H\rangle
=\frac{1}{\sqrt2}\binom{0}{v}.
$$

This vacuum is electrically neutral because

$$
Q\langle H\rangle=0.
$$

Therefore the generator $Q=T^3+Y$ remains unbroken, and the corresponding gauge boson is the massless photon. The three remaining gauge directions are Higgsed: they become the massive fields $W^+$, $W^-$, and $Z$.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Electroweak symmetry breaking flow](/figures/gauge-theories-standard-model/electroweak-symmetry-breaking-flow.svg)

<figcaption>

Electroweak symmetry breaking in the minimal Standard Model. The Higgs doublet vacuum preserves $Q=T^3+Y$, produces the mass terms $\frac{g^2v^2}{4}W_\mu^+W^{-\mu}+\frac{v^2}{8}(gW_\mu^3-g'B_\mu)^2$, and reorganizes the gauge fields into massive $W^\pm,Z$ bosons and a massless photon.

</figcaption>
</figure>

The phrase “spontaneous breaking of gauge symmetry” is useful but treacherous. Gauge redundancy is not a physical symmetry that disappears. What changes is the best perturbative description of the gauge-invariant spectrum: three gauge bosons acquire longitudinal polarizations, the radial Higgs excitation remains as a scalar particle, and one gauge boson stays massless because electromagnetism is unbroken.

## Prerequisites

You should know [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/) and [Electroweak Covariant Derivative](/gauge-theories-standard-model/electroweak/electroweak-covariant-derivative/). The core convention is

$$
D_\mu
=
\partial_\mu+igW_\mu^aT^a+ig'YB_\mu,
\qquad
Q=T^3+Y.
$$

You should also know the distinction between gauge redundancy and physical global symmetry from [Gauge Redundancy Revisited](/gauge-theories-standard-model/gauge-principle/gauge-redundancy-revisited/) and [Global Versus Gauge Symmetry](/gauge-theories-standard-model/gauge-principle/global-versus-gauge-symmetry/). For comparison with a simpler model, the Higgs Sector chapter later treats the Abelian Higgs model before returning to the full Standard Model Higgs doublet.

## Core idea

The electroweak gauge theory begins with four gauge fields:

$$
W_\mu^1,
\quad
W_\mu^2,
\quad
W_\mu^3,
\quad
B_\mu.
$$

Before symmetry breaking, none of these is the photon. The fields $W_\mu^a$ gauge weak isospin, and $B_\mu$ gauges hypercharge. The photon appears only after the Higgs vacuum chooses a direction in weak-isospin space.

The vacuum direction must preserve electric charge. The Higgs doublet has

$$
T^3=\frac12
\begin{pmatrix}
1&0\\
0&-1
\end{pmatrix},
\qquad
Y=\frac12.
$$

Thus its components have charges

$$
Q(H^+)=\frac12+\frac12=1,
\qquad
Q(H^0)=-\frac12+\frac12=0.
$$

The lower component is neutral. A nonzero vacuum expectation value in that component leaves $U(1)_{\rm em}$ intact.

This is the entire trick. The Standard Model does not add electromagnetism after the fact. It starts with weak isospin and hypercharge, then the Higgs vacuum identifies the unbroken electromagnetic generator.

## Setup and conventions

The electroweak Higgs Lagrangian is

$$
\mathcal L_H
=(D_\mu H)^\dagger(D^\mu H)-V(H),
$$

with

$$
D_\mu H
=
\left(\partial_\mu+igW_\mu^a\frac{\sigma^a}{2}+ig'\frac12 B_\mu\right)H.
$$

For the minimal renormalizable Higgs potential, use

$$
V(H)=-\mu^2H^\dagger H+\lambda(H^\dagger H)^2,
\qquad
\mu^2>0,
\qquad
\lambda>0.
$$

The extrema satisfy

$$
\frac{\partial V}{\partial(H^\dagger H)}
=-\mu^2+2\lambda H^\dagger H=0,
$$

so the classical minima obey

$$
H^\dagger H=\frac{v^2}{2},
\qquad
v^2=\frac{\mu^2}{\lambda}.
$$

The minimum is not a single point in field space. Any field related to a given minimum by an electroweak gauge transformation is an equivalent representative. A convenient representative is

$$
\langle H\rangle
=\frac{1}{\sqrt2}\binom{0}{v}.
$$

In perturbation theory one often writes, in unitary gauge,

$$
H(x)=\frac{1}{\sqrt2}\binom{0}{v+h(x)},
$$

where $h(x)$ is the physical Higgs fluctuation. In gauges that keep the would-be Goldstone fields explicit, a useful local parametrization is schematically

$$
H(x)=
\exp\!\left(\frac{i\pi^a(x)\sigma^a}{v}\right)
\frac{1}{\sqrt2}\binom{0}{v+h(x)}.
$$

The three fields $\pi^a$ are not physical massless Goldstone bosons in the gauge theory. They are gauge-dependent variables that become the longitudinal modes of $W^\pm$ and $Z$ in the Higgs phase.

## The unbroken generator

A generator is unbroken by the chosen vacuum if it annihilates the vacuum direction. Consider an infinitesimal electroweak generator

$$
\alpha^aT^a+\beta Y.
$$

The generators $T^1$ and $T^2$ move the lower component of the doublet into the upper component, so they do not preserve the vacuum direction. The diagonal part acts as

$$
(\alpha^3T^3+\beta Y)
\binom{0}{v}
=
\frac{v}{2}\binom{0}{-\alpha^3+\beta}.
$$

This vanishes when

$$
\beta=\alpha^3.
$$

Therefore the unbroken generator is proportional to

$$
T^3+Y=Q.
$$

The breaking pattern is

$$
SU(2)_L\times U(1)_Y
\longrightarrow
U(1)_{\rm em}.
$$

Counting dimensions,

$$
\dim(SU(2)_L\times U(1)_Y)-\dim(U(1)_{\rm em})=4-1=3.
$$

There are three broken gauge directions. Correspondingly, three gauge bosons become massive. The unbroken direction gives one massless gauge boson, the photon.

## Gauge-boson mass terms

The gauge-boson masses come from the Higgs kinetic term, not from explicit mass terms inserted by hand. Set $H$ equal to its vacuum value and evaluate

$$
(D_\mu\langle H\rangle)^\dagger(D^\mu\langle H\rangle).
$$

Using

$$
T^1\binom{0}{v}
=\frac{v}{2}\binom{1}{0},
\qquad
T^2\binom{0}{v}
=-\frac{iv}{2}\binom{1}{0},
\qquad
T^3\binom{0}{v}
=-\frac{v}{2}\binom{0}{1},
$$

and

$$
Y\binom{0}{v}=\frac{v}{2}\binom{0}{1},
$$

one finds

$$
D_\mu\langle H\rangle
=\frac{iv}{2\sqrt2}
\binom{
 g(W_\mu^1-iW_\mu^2)
}{
 -gW_\mu^3+g'B_\mu
}.
$$

Therefore

$$
(D_\mu\langle H\rangle)^\dagger(D^\mu\langle H\rangle)
=
\frac{g^2v^2}{8}
\left(W_\mu^1W^{1\mu}+W_\mu^2W^{2\mu}\right)
+\frac{v^2}{8}(gW_\mu^3-g'B_\mu)^2.
$$

Define the charged fields

$$
W_\mu^\pm
=\frac{1}{\sqrt2}(W_\mu^1\mp iW_\mu^2).
$$

Then

$$
W_\mu^+W^{-\mu}
=\frac12
\left(W_\mu^1W^{1\mu}+W_\mu^2W^{2\mu}\right),
$$

so the charged mass term is

$$
\frac{g^2v^2}{4}W_\mu^+W^{-\mu}.
$$

Thus

$$
m_W=\frac{gv}{2}.
$$

The neutral mass term is

$$
\frac{v^2}{8}(gW_\mu^3-g'B_\mu)^2.
$$

It has one massive linear combination and one massless linear combination. Introduce

$$
s_W=\sin\theta_W,
\qquad
c_W=\cos\theta_W,
\qquad
\tan\theta_W=\frac{g'}{g}.
$$

Equivalently,

$$
s_W=\frac{g'}{\sqrt{g^2+g'^2}},
\qquad
c_W=\frac{g}{\sqrt{g^2+g'^2}}.
$$

The mass eigenstate fields are

$$
A_\mu=s_WW_\mu^3+c_WB_\mu,
\qquad
Z_\mu=c_WW_\mu^3-s_WB_\mu.
$$

The inverse relations are

$$
W_\mu^3=s_WA_\mu+c_WZ_\mu,
\qquad
B_\mu=c_WA_\mu-s_WZ_\mu.
$$

Substituting into the mass term gives

$$
gW_\mu^3-g'B_\mu
=
\sqrt{g^2+g'^2}\,Z_\mu,
$$

and hence

$$
\frac{v^2}{8}(gW_\mu^3-g'B_\mu)^2
=
\frac12 m_Z^2 Z_\mu Z^\mu,
\qquad
m_Z=\frac{v}{2}\sqrt{g^2+g'^2}.
$$

The photon remains massless:

$$
m_A=0.
$$

The tree-level relation between $W$ and $Z$ masses is

$$
m_W=m_Zc_W.
$$

Equivalently,

$$
\rho_{\rm tree}
\equiv
\frac{m_W^2}{m_Z^2c_W^2}
=1.
$$

This relation is special to the minimal Higgs representation and its custodial-symmetry structure. Precision electroweak physics is partly the art of measuring and organizing deviations from these simple tree-level relations.

## Electromagnetic coupling

The neutral part of the covariant derivative is

$$
igW_\mu^3T^3+ig'YB_\mu.
$$

Using

$$
W_\mu^3=s_WA_\mu+c_WZ_\mu,
\qquad
B_\mu=c_WA_\mu-s_WZ_\mu,
$$

we get

$$
igW_\mu^3T^3+ig'YB_\mu
=
i(gs_WT^3+g'c_WY)A_\mu
+i(gc_WT^3-g's_WY)Z_\mu.
$$

Define the electric charge coupling

$$
e=gs_W=g'c_W.
$$

Then the photon coupling becomes

$$
ie(T^3+Y)A_\mu=ieQA_\mu.
$$

This is a strong consistency check. The massless gauge field couples exactly to the unbroken generator. The same derivation gives the neutral weak coupling

$$
igc_WT^3Z_\mu-ig's_WYZ_\mu
=
i\frac{g}{c_W}(T^3-s_W^2Q)Z_\mu.
$$

So after symmetry breaking,

$$
D_\mu
\supset
ieQA_\mu
+i\frac{g}{c_W}(T^3-s_W^2Q)Z_\mu
+\frac{ig}{\sqrt2}(W_\mu^+T^+ + W_\mu^-T^-).
$$

The photon coupling is universal because all fields couple to the same unbroken generator $Q$. The $Z$ coupling is not simply proportional to electric charge; it remembers weak isospin.

## Goldstone modes and gauge choices

A complex Higgs doublet contains four real field components. Around the Higgs vacuum they reorganize as

$$
4\text{ real Higgs components}
=
1\text{ radial Higgs mode}+3\text{ would-be Goldstone modes}.
$$

The three would-be Goldstone modes match the three broken gauge directions. In a global symmetry theory, Goldstone's theorem would give three physical massless scalar particles. In a gauge theory, those scalar variables are absorbed into the longitudinal polarizations of the massive vector bosons.

The polarization count is useful:

$$
\begin{aligned}
\text{before:}&\quad 4\text{ massless gauge bosons}\times 2\text{ polarizations}+4\text{ real scalars}=12,\\
\text{after:}&\quad 3\text{ massive gauge bosons}\times 3\text{ polarizations}+1\text{ massless photon}\times 2+1\text{ Higgs}=12.
\end{aligned}
$$

No degree of freedom disappears. The variables are rearranged.

Different gauges display this rearrangement differently.

| Gauge language | What it shows well | What to remember |
|---|---|---|
| Unitary gauge | Only physical-looking fields $h,W^\pm,Z,A$ appear. | Power counting and renormalization are less transparent. |
| $R_\xi$ gauges | Goldstones and ghosts remain explicit. | Intermediate Goldstone and ghost masses depend on $\xi$. |
| Landau gauge | Often useful for symmetry arguments and loop calculations. | The vacuum direction is still a gauge-fixed statement. |
| Gauge-invariant language | Avoids pretending that gauge redundancy is a physical symmetry. | Perturbative particle intuition is less immediate. |

The most common working compromise is to use gauge-fixed perturbation theory, compute gauge-invariant observables, and remember that the final physics cannot depend on the gauge parameter.

## What is actually observable?

The textbook statement

$$
\langle H\rangle=\frac1{\sqrt2}\binom{0}{v}
$$

is a gauge-fixed description. The field $H$ is not itself gauge invariant, so its one-point function is not an observable in the same way that a global order parameter is. A gauge-invariant statement can instead refer to the nonzero scale set by $H^\dagger H$, to particle masses, to scattering amplitudes, and to pole structures in gauge-invariant correlators.

In perturbation theory this distinction is usually hidden because gauge fixing chooses a representative vacuum and the resulting field variables are extremely efficient. But conceptually it matters. Local gauge redundancy is not literally broken as a physical symmetry. The Higgs phase is a phase in which the spectrum and long-distance force law are organized as if some gauge bosons have acquired mass, while the unbroken electromagnetic gauge field remains long-range.

A good practical rule is:

$$
\text{Use the gauge-fixed Higgs vacuum for calculations; interpret only gauge-invariant outputs as physics.}
$$

This rule also prevents a common mistake: treating the Higgs mechanism as an explicit Proca mass term added to a gauge theory. A Proca mass for $W$ and $Z$ alone would obscure the gauge identities that control high-energy behavior. The Higgs mechanism gives vector boson masses in a way compatible with the underlying gauge redundancy and the renormalized quantum theory.

## Common pitfalls

**Forgetting the Higgs hypercharge.** In the convention $Q=T^3+Y$, the Standard Model Higgs doublet has $Y=1/2$. This makes its lower component neutral. If you use the older convention $Q=T^3+Y_{\rm old}/2$, then the same Higgs doublet has $Y_{\rm old}=1$.

**Calling $B_\mu$ the photon.** Before symmetry breaking, $B_\mu$ is the hypercharge gauge field. The photon is the massless combination $A_\mu=s_WW_\mu^3+c_WB_\mu$.

**Losing the factor of $1/\sqrt2$ in the vacuum.** The standard convention $\langle H\rangle=(0,v/\sqrt2)^T$ is what gives $m_W=gv/2$. Moving the $\sqrt2$ changes the definition of $v$.

**Thinking the Higgs mechanism destroys gauge invariance.** Gauge redundancy remains. Gauge fixing may hide it, but BRST identities and gauge-parameter independence still organize the quantum theory.

**Confusing the broken generators with the massive vector fields.** Broken gauge directions are directions in the Lie algebra. Massive vector fields are linear combinations of gauge fields after the Higgs kinetic term is diagonalized. Couplings $g$ and $g'$ matter in the neutral mass eigenstates.

**Treating the tree-level mass relation as exact without qualification.** The formula $m_W=m_Zc_W$ is a tree-level relation in the minimal Higgs sector. Loop corrections and the precise definition of $\theta_W$ depend on the renormalization scheme and on the observables used to extract parameters.

## Relations to other pages

[Electroweak Covariant Derivative](/gauge-theories-standard-model/electroweak/electroweak-covariant-derivative/) gives the representation-dependent derivative from which the mass terms and current couplings are derived. The next page, [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/), focuses on the physical boson basis and the current interactions.

The Higgs Sector chapter later returns to this material more slowly, beginning with the Abelian Higgs model and then deriving Higgs couplings, gauge-boson masses, and the Goldstone equivalence theorem. The Standard Model Architecture chapter later assembles the Higgs, gauge, fermion, and Yukawa pieces into the full Lagrangian.

The Gauge Quantization chapter explains why gauge fixing and ghosts are still needed after symmetry breaking. The Standard Model anomalies chapter explains why the chiral fermion representation content is consistent as a quantum gauge theory.

## Research status

The mechanism described on this page is established as the minimal Standard Model account of electroweak symmetry breaking. The observed weak bosons, the photon, and the Higgs boson are described with this structure to high precision.

Several surrounding questions remain active. The Standard Model does not explain why the Higgs potential has the parameters it has, why the electroweak scale is so small compared with very high ultraviolet scales, whether the electroweak phase transition in the early universe was merely a crossover or modified by new physics, or whether precision Higgs and electroweak measurements will reveal higher-dimensional operators or additional fields.

## Exercises

### Exercise 1: Find the unbroken generator

Let

$$
\langle H\rangle=\frac1{\sqrt2}\binom{0}{v},
\qquad
T^3=\frac12\begin{pmatrix}1&0\\0&-1\end{pmatrix},
\qquad
Y=\frac12.
$$

Show that $Q=T^3+Y$ annihilates the vacuum, while $T^3$ and $Y$ separately do not.

<details><summary><strong>Solution</strong></summary>

Acting on the vacuum direction,

$$
T^3\binom{0}{v}
=\binom{0}{-v/2},
\qquad
Y\binom{0}{v}
=\binom{0}{v/2}.
$$

Therefore

$$
(T^3+Y)\binom{0}{v}=0.
$$

But neither $T^3$ nor $Y$ individually gives zero. The unbroken generator is the combination $Q=T^3+Y$, not either original neutral generator alone.

</details>

### Exercise 2: Derive the neutral mass matrix

Starting from

$$
\frac{v^2}{8}(gW_\mu^3-g'B_\mu)^2,
$$

write the neutral gauge-boson mass term in matrix form and find its eigenvalues.

<details><summary><strong>Solution</strong></summary>

The mass term is

$$
\frac{v^2}{8}
\begin{pmatrix}W_\mu^3&B_\mu\end{pmatrix}
\begin{pmatrix}
g^2&-gg'\\
-gg'&g'^2
\end{pmatrix}
\binom{W^{3\mu}}{B^\mu}.
$$

For real vector fields, the canonical mass form is

$$
\frac12
\begin{pmatrix}W_\mu^3&B_\mu\end{pmatrix}
M^2
\binom{W^{3\mu}}{B^\mu},
$$

so

$$
M^2=\frac{v^2}{4}
\begin{pmatrix}
g^2&-gg'\\
-gg'&g'^2
\end{pmatrix}.
$$

The determinant of the $2\times2$ matrix is zero, so one eigenvalue is zero. The trace is $g^2+g'^2$, so the other eigenvalue is

$$
\frac{v^2}{4}(g^2+g'^2).
$$

Thus

$$
m_A^2=0,
\qquad
m_Z^2=\frac{v^2}{4}(g^2+g'^2).
$$

</details>

### Exercise 3: Check the photon coupling

Using

$$
A_\mu=s_WW_\mu^3+c_WB_\mu,
\qquad
Z_\mu=c_WW_\mu^3-s_WB_\mu,
$$

and $e=gs_W=g'c_W$, show that the coefficient of $A_\mu$ in the neutral covariant derivative is $ieQ$.

<details><summary><strong>Solution</strong></summary>

Invert the rotation:

$$
W_\mu^3=s_WA_\mu+c_WZ_\mu,
\qquad
B_\mu=c_WA_\mu-s_WZ_\mu.
$$

Then

$$
igW_\mu^3T^3+ig'B_\mu Y
=
i(gs_WT^3+g'c_WY)A_\mu
+
\text{$Z$ terms}.
$$

Since

$$
e=gs_W=g'c_W,
$$

the photon term is

$$
ie(T^3+Y)A_\mu=ieQA_\mu.
$$

</details>

## References

- Srednicki, *Quantum Field Theory*, §§84–87, for spontaneous breaking of gauge symmetries, the Abelian and non-Abelian Higgs mechanisms, and the Standard Model gauge and Higgs sector.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 28–29, for spontaneous symmetry breaking, the Higgs mechanism, weak interactions, and the gauge-boson mass relations.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the electroweak theory and the treatment of spontaneously broken gauge symmetries.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for the conceptual structure of spontaneous symmetry breaking and the Higgs phenomenon in gauge theory.

## Version history

- **2026-06-18:** Initial polished draft. Derived the Higgs vacuum, unbroken electromagnetic generator, gauge-boson mass terms, and weak mixing relations using the volume convention $D_\mu=\partial_\mu+igA_\mu^aT^a$.
