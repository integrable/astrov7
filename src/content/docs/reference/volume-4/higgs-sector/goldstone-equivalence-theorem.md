---
title: "Goldstone Equivalence Theorem"
description: "Explains why high-energy longitudinal W and Z amplitudes are controlled by the would-be Goldstone fields in spontaneously broken gauge theories."
sidebar:
  label: "Goldstone Equivalence Theorem"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki §§84–87; Schwartz Chs. 28–29; Coleman, Aspects of Symmetry, Ch. 5; Weinberg Vol. II electroweak chapters."
topics:
  - Goldstone equivalence theorem
  - longitudinal gauge bosons
  - Higgs mechanism
  - electroweak symmetry breaking
  - perturbative unitarity
canonicalTopics:
  - goldstone-equivalence-theorem
  - longitudinal-gauge-bosons
  - would-be-goldstone-bosons
  - higgs-mechanism
researchStatus:
  established:
    - "At energies much larger than the vector-boson masses, amplitudes with external longitudinal massive gauge bosons equal the corresponding amplitudes with external would-be Goldstone fields, up to convention factors and corrections suppressed by mV/E."
  active:
    - "Loop-level precision versions require gauge choices, wave-function factors, renormalization schemes, and careful treatment of exceptional kinematics."
---

## Summary

In a Higgs phase, a massive gauge boson has three polarizations. At high energy, its longitudinal polarization behaves almost like its four-momentum divided by its mass:

$$
\epsilon_L^\mu(k)=\frac{k^\mu}{m_V}+O\left(\frac{m_V}{E}\right).
$$

Gauge invariance then turns the momentum-contracted vector amplitude into an amplitude with the would-be Goldstone field. Schematically,

$$
k_\mu\mathcal M^\mu(V^a)=m_a\mathcal M(G^a),
$$

so

$$
\mathcal M(V_L^{a_1}\cdots V_L^{a_n}\to X)
=
\mathcal M(G^{a_1}\cdots G^{a_n}\to X)
+
O\left(\frac{m_a}{E}\right)
$$

at tree level in a common phase convention. This is the **Goldstone equivalence theorem**.

The theorem is not saying that a longitudinal $W$ or $Z$ boson literally becomes a scalar particle. It says that the leading high-energy part of a physical amplitude can be computed using the simpler would-be Goldstone fields in a gauge-fixed description. That is why the theorem is both conceptually clarifying and brutally useful: it turns the high-energy behavior of longitudinal electroweak bosons into a problem in the scalar sector.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Goldstone equivalence theorem flow](/figures/gauge-theories-standard-model/goldstone-equivalence-theorem.svg)

<figcaption>

The equivalence theorem combines the high-energy form of a longitudinal polarization vector with the broken Ward identity relating $k_\mu\mathcal M^\mu(V^a)$ to $m_a\mathcal M(G^a)$. The useful tree-level rule is simple; loop-level statements include finite convention-dependent factors.

</figcaption>
</figure>

## Prerequisites

You should know [Non-Abelian Higgs Mechanism](/gauge-theories-standard-model/higgs-sector/non-abelian-higgs-mechanism/), [Gauge Boson Masses](/gauge-theories-standard-model/higgs-sector/gauge-boson-masses/), and [Higgs Boson Couplings](/gauge-theories-standard-model/higgs-sector/higgs-boson-couplings/). We use the same electroweak convention as before:

$$
Q=T^3+Y,
\qquad
D_\mu H=
\left(\partial_\mu+igW_\mu^a\frac{\sigma^a}{2}+ig'\frac12 B_\mu\right)H.
$$

In the Standard Model Higgs sector we write, before unitary gauge,

$$
H=
\begin{pmatrix}
G^+\\
\dfrac{v+h+iG^0}{\sqrt2}
\end{pmatrix}.
$$

The fields $G^\pm$ and $G^0$ are the would-be Goldstone fields. They are not physical asymptotic particles, but they are perfectly legitimate fields in covariant gauges and they remember the longitudinal components of $W^\pm$ and $Z$.

## The statement

Let $V^a_\mu$ be a massive gauge boson in a spontaneously broken gauge theory, with mass $m_a$, and let $G^a$ be the would-be Goldstone field associated with the same broken generator. For a process with external longitudinal massive vectors and any other external physical particles $X$, the theorem says

$$
\mathcal M(V_L^{a_1}(p_1)\cdots V_L^{a_n}(p_n)\to X)
=
\left(\prod_{i=1}^n C_{a_i}\right)
\mathcal M(G^{a_1}(p_1)\cdots G^{a_n}(p_n)\to X)
+
O\left(\frac{m_{a_i}}{E_i}\right).
$$

At tree level, with the usual normalization of fields and phases, one normally takes $C_a=1$ and remembers that some books absorb signs or factors of $i$ into the definition of the Goldstone fields. At loop level, the $C_a$ are finite factors determined by the renormalization prescription. The leading physics is independent of this bookkeeping.

The theorem is useful in the regime

$$
E_i\gg m_{a_i},
$$

with generic high-energy kinematics. It is not a license to ignore masses in every infrared-sensitive limit. Soft and collinear corners need separate care, as usual in gauge theory.

## Why longitudinal vectors know about Goldstones

A massive vector with momentum $k^\mu=(E,0,0,|\mathbf k|)$ has a longitudinal polarization vector

$$
\epsilon_L^\mu(k)=\frac{1}{m_V}\left(|\mathbf k|,0,0,E\right).
$$

Since $E^2-|\mathbf k|^2=m_V^2$, this can be written as

$$
\epsilon_L^\mu(k)=\frac{k^\mu}{m_V}+O\left(\frac{m_V}{E}\right).
$$

Therefore an amplitude with one external longitudinal vector has the form

$$
\mathcal M(V_L^a(k)\to X)
=
\epsilon_L^\mu(k)\mathcal M_\mu(V^a(k)\to X)
=
\frac{k^\mu}{m_a}\mathcal M_\mu(V^a(k)\to X)
+O\left(\frac{m_a}{E}\right).
$$

The first term looks dangerous: it has a factor $1/m_a$. Gauge invariance is what makes it meaningful. In a broken gauge theory, the gauge-fixed action still carries a BRST identity. For external on-shell physical states, this identity implies the broken Ward identity

$$
k^\mu\mathcal M_\mu(V^a(k)\to X)=m_a\mathcal M(G^a(k)\to X),
$$

up to convention-dependent signs and phases. Substituting this relation gives

$$
\mathcal M(V_L^a(k)\to X)
=
\mathcal M(G^a(k)\to X)+O\left(\frac{m_a}{E}\right).
$$

For several longitudinal vectors, apply the same argument to each external leg. The result is the multi-leg equivalence theorem.

## What the theorem is not saying

The theorem is often phrased as “replace longitudinal gauge bosons by Goldstone bosons.” That is fine as a mnemonic, but slightly treacherous.

The physical external state is still $W_L^\pm$ or $Z_L$, not $G^\pm$ or $G^0$. The Goldstone fields depend on the gauge-fixed description. In unitary gauge they are hidden; in $R_\xi$ gauges they appear explicitly and usually have gauge-dependent masses

$$
m_G^2=\xi m_V^2.
$$

The theorem says that the leading high-energy physical amplitude is equal to the corresponding Goldstone amplitude after the conventional normalization factors have been applied. The equality is an amplitude-level consequence of gauge symmetry, not an identity between fields.

## Example: longitudinal vector scattering

Consider the high-energy process

$$
W_L^+W_L^-\to Z_LZ_L.
$$

The equivalence theorem turns its leading behavior into

$$
\mathcal M(W_L^+W_L^-\to Z_LZ_L)
=
\mathcal M(G^+G^-\to G^0G^0)
+O\left(\frac{m_W}{E},\frac{m_Z}{E}\right).
$$

The Goldstone calculation lives in the scalar sector. Using

$$
V(H)=\lambda\left(H^\dagger H-\frac{v^2}{2}\right)^2,
\qquad
m_h^2=2\lambda v^2,
$$

the process $G^+G^-\to G^0G^0$ receives a contact interaction and an $s$-channel Higgs exchange. With the common convention in which $i\mathcal M$ is the sum of Feynman diagrams, one obtains

$$
\mathcal M(G^+G^-\to G^0G^0)
=
-\frac{m_h^2}{v^2}\frac{s}{s-m_h^2}
$$

up to the usual $i\epsilon$ prescription and overall sign conventions. Two limits are worth remembering:

$$
\mathcal M\simeq \frac{s}{v^2}
\qquad (s\ll m_h^2),
$$

and

$$
\mathcal M\simeq -\frac{m_h^2}{v^2}
\qquad (s\gg m_h^2).
$$

The first limit is the nonlinear sigma-model behavior: without the radial Higgs mode, longitudinal gauge-boson scattering grows with energy. The second shows the cancellation produced by the Higgs boson in the renormalizable Standard Model. This cancellation is one of the sharpest ways to see that Higgs interactions are not decorative. They are required for the high-energy consistency of the electroweak theory.

## Relation to perturbative unitarity

Before the Higgs boson was known experimentally, one of the central theoretical clues was the high-energy behavior of longitudinal weak-boson scattering. Massive vectors without a gauge-invariant Higgs completion tend to produce amplitudes that grow with energy. Growth itself is not automatically illegal, but partial-wave unitarity limits how long it can continue.

The equivalence theorem makes the issue transparent. The leading high-energy amplitude is controlled by the Goldstone sector. If the scalar sector is just the nonlinear Goldstone theory, amplitudes grow like $E^2/v^2$. If the Standard Model Higgs is included, its exchange cancels the dangerous high-energy growth. In this sense, the Higgs boson is not merely the particle that gives masses to $W$ and $Z$; it is also the field that repairs the high-energy behavior of their longitudinal polarizations.

## Why covariant gauges are better than unitary gauge here

In unitary gauge the Goldstone fields are absent from the Lagrangian, so the theorem looks mysterious. The vector propagator also has high-momentum behavior that obscures power counting. In an $R_\xi$ gauge, the fields $G^\pm$ and $G^0$ appear explicitly, and the gauge-fixing functions can be chosen to remove gauge–Goldstone mixing at quadratic order. For example, schematically,

$$
\mathcal F^a=\partial^\mu V^a_\mu-\xi m_aG^a.
$$

The corresponding gauge-fixing term is

$$
\mathcal L_{\rm gf}=-\frac{1}{2\xi}\mathcal F^a\mathcal F^a.
$$

This is the natural arena for proving the theorem: the Goldstone fields are visible, but BRST symmetry still knows that they are tied to longitudinal gauge modes rather than to independent physical particles.

## A reliable way to use the theorem

For tree-level high-energy estimates, use this workflow:

1. Identify each external $W_L^\pm$ or $Z_L$.
2. Replace it by $G^\pm$ or $G^0$ with the same momentum.
3. Compute the Goldstone amplitude using the scalar-sector interactions in a convenient gauge.
4. Drop terms suppressed by $m_V/E$.
5. Return to the physical interpretation: the result is the leading longitudinal-vector amplitude.

This is especially useful for seeing cancellations. Computing $W_LW_L$ scattering directly with polarization vectors, gauge vertices, and Higgs exchange is possible but algebraically noisy. The Goldstone calculation exposes the same leading physics in a few scalar diagrams.

## Common mistakes

**Confusing Goldstone fields with physical particles.** In a gauge theory, would-be Goldstone fields are gauge-dependent variables, not physical asymptotic states. They are a computational bridge to longitudinal vectors.

**Using the theorem outside its energy regime.** The correction is $O(m_V/E)$. Near threshold, or in soft kinematics, the theorem is not a precision approximation.

**Forgetting convention factors.** Some references include factors of $i$ or $-1$ for each external Goldstone. This is not a physics disagreement; it is a field-definition and $S$-matrix convention issue.

**Assuming unitary gauge is the cleanest gauge.** Unitary gauge makes the spectrum look physical but often hides the symmetry relations that make the theory well behaved.

**Thinking the Higgs only gives mass.** The same Higgs-sector structure that gives $m_W$ and $m_Z$ also controls the high-energy cancellation in longitudinal vector scattering.

## Exercises

### 1. Longitudinal polarization at high energy

For a massive vector moving in the $z$ direction, take

$$
k^\mu=(E,0,0,p),
\qquad
E^2=p^2+m^2,
$$

and

$$
\epsilon_L^\mu=\frac{1}{m}(p,0,0,E).
$$

Show that $\epsilon_L^2=-1$, $k\cdot\epsilon_L=0$, and

$$
\epsilon_L^\mu-\frac{k^\mu}{m}=O\left(\frac{m}{E}\right).
$$

<details><summary><strong>Solution</strong></summary>

Using the mostly-minus metric,

$$
\epsilon_L^2=\frac{p^2-E^2}{m^2}=-1,
$$

and

$$
k\cdot\epsilon_L=\frac{Ep-pE}{m}=0.
$$

The difference from $k^\mu/m$ is

$$
\epsilon_L^\mu-\frac{k^\mu}{m}
=
\frac{1}{m}(p-E,0,0,E-p).
$$

For $E\gg m$,

$$
E-p=\frac{E^2-p^2}{E+p}=\frac{m^2}{E+p}\simeq\frac{m^2}{2E},
$$

so each nonzero component of the difference is of order $m/E$.

</details>

### 2. From a broken Ward identity to the equivalence theorem

Assume that for one external massive vector

$$
k_\mu\mathcal M^\mu(V)=m_V\mathcal M(G),
$$

and that

$$
\epsilon_L^\mu(k)=\frac{k^\mu}{m_V}+\delta^\mu,
\qquad
\delta^\mu=O\left(\frac{m_V}{E}\right).
$$

Derive the leading high-energy relation between $\mathcal M(V_L)$ and $\mathcal M(G)$.

<details><summary><strong>Solution</strong></summary>

The longitudinal amplitude is

$$
\mathcal M(V_L)=\epsilon_L^\mu\mathcal M_\mu(V)
=\frac{k^\mu}{m_V}\mathcal M_\mu(V)+\delta^\mu\mathcal M_\mu(V).
$$

The Ward identity gives

$$
\frac{k^\mu}{m_V}\mathcal M_\mu(V)=\mathcal M(G).
$$

The remaining term is suppressed by $m_V/E$ relative to the characteristic hard scale of the amplitude. Therefore

$$
\mathcal M(V_L)=\mathcal M(G)+O\left(\frac{m_V}{E}\right).
$$

</details>

### 3. Goldstone scattering from the Higgs potential

Using

$$
H=
\begin{pmatrix}
G^+\\
\dfrac{v+h+iG^0}{\sqrt2}
\end{pmatrix},
\qquad
V(H)=\lambda\left(H^\dagger H-\frac{v^2}{2}\right)^2,
$$

identify the two types of tree diagrams contributing to $G^+G^-\to G^0G^0$.

<details><summary><strong>Solution</strong></summary>

Expanding the potential gives a four-Goldstone contact interaction involving $G^+G^-(G^0)^2$ and cubic interactions involving $hG^+G^-$ and $h(G^0)^2$. Therefore the tree-level Goldstone process receives:

1. a contact diagram from the quartic Goldstone term;
2. an $s$-channel Higgs-exchange diagram using the two cubic Higgs–Goldstone vertices.

The sum gives the leading high-energy behavior of $W_L^+W_L^-\to Z_LZ_L$ by the equivalence theorem.

</details>

## Where to go next

Continue to [Flavor and Neutrinos](/gauge-theories-standard-model/flavor-neutrinos/). The Higgs chapter has now explained how the vacuum reorganizes gauge and scalar degrees of freedom; the next chapter explains how the same Higgs field turns chiral Yukawa matrices into masses, CKM mixing, PMNS mixing, and CP-violating phases.

For the scattering side, return later to electroweak vector-boson scattering and SMEFT pages, where deviations in Higgs and gauge-boson couplings show up precisely in the high-energy amplitudes controlled by this theorem.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§84–87, for spontaneously broken gauge theories and the Standard Model gauge and Higgs sector.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 28–29, especially the Higgs mechanism, electroweak symmetry breaking, and gauge-boson scattering.
- Coleman, *Aspects of Symmetry*, Ch. 5, “Secret Symmetry,” for the conceptual origin of the Higgs phenomenon in Abelian and Yang–Mills theories.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the electroweak theory and spontaneously broken gauge theories.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*, for the standard perturbative treatment of longitudinal weak-boson scattering and the equivalence theorem.
- Cornwall, Levin, and Tiktopoulos, “Derivation of Gauge Invariance from High-Energy Unitarity Bounds on the S Matrix,” for a classic high-energy unitarity perspective.

## Version history

- **2026-06-18:** Initial page. Added the amplitude-level statement, derivation from longitudinal polarization and broken Ward identities, $W_LW_L$ scattering example, exercises, and figure.
