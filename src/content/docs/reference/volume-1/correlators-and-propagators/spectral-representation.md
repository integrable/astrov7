---
title: "Spectral Representation"
description: "The Källén–Lehmann representation of exact two-point functions, including spectral density, positivity, one-particle poles, branch cuts, and mass spectrum."
sidebar:
  label: "Spectral Representation"
  order: 8
---

## Summary

The Källén–Lehmann representation says that an exact two-point function is a positive superposition of free two-point functions with different masses. For a Hermitian scalar operator $\mathcal O(x)$ in the vacuum,

$$
\boxed{
\langle0|\mathcal O(x)\mathcal O(0)|0\rangle
=\int_0^\infty ds\,\rho_{\mathcal O}(s)\,\Delta^+(x;s),
\qquad
\rho_{\mathcal O}(s)\ge0.
}
$$

The corresponding time-ordered two-point function is

$$
\boxed{
D_F^{\mathcal O}(p)
=\int_0^\infty ds\,\rho_{\mathcal O}(s)
\frac{i}{p^2-s+i0}.
}
$$

A stable one-particle state appears as a delta-function pole in the spectral density. Multiparticle states appear as a continuum:

$$
\boxed{
\rho_{\mathcal O}(s)=Z\delta(s-m^2)+\theta(s-s_{\rm th})\rho_{\rm cont}(s).
}
$$

This formula is one of the cleanest places where QFT's Hilbert-space structure becomes visible inside a propagator. Coleman derives the Källén–Lehmann representation by inserting a complete set of states into an exact two-point function; Weinberg uses the same representation to connect positivity, spectral support, asymptotic behavior, and the analytic structure of propagators; Srednicki introduces it as the Lehmann–Källén form of the exact propagator before using it to discuss loop corrections (Coleman 2019, ch. 15; Weinberg 1995, Vol. I, §10.7; Srednicki 2007, §13).

## Prerequisites

You should know [States, Operators, and the Vacuum](/foundations/correlators-and-propagators/states-operators-vacuum/), [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [iε Prescription](/foundations/correlators-and-propagators/i-epsilon-prescription/), and [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/).

## Core idea

A free scalar propagator has a single mass:

$$
D_F(p)=\frac{i}{p^2-m^2+i0}.
$$

An interacting field does not generally create only a single one-particle state. Acting on the vacuum, a local operator can create any state with the same quantum numbers:

$$
\mathcal O(0)|0\rangle
=\text{one-particle component}
+\text{multiparticle components}
+\cdots.
$$

The exact two-point function sums over all those states. Lorentz invariance groups the states by invariant mass

$$
s=p^2.
$$

The result is a superposition of free propagators with mass squared $s$, weighted by a nonnegative spectral density.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Källén–Lehmann spectral density with a one-particle pole and multiparticle continuum](/figures/foundations/kallen-lehmann-spectral-density.svg)

<figcaption>

The spectral density records which invariant masses can be created from the vacuum by the operator. A stable particle gives an isolated delta function at $s=m^2$; multiparticle states give a continuum above the threshold $s_{\rm th}$. The exact propagator is the corresponding weighted integral of free Feynman propagators.

</figcaption>
</figure>

:::note[Assumptions]
The clean positivity statement assumes a positive-norm Hilbert space and a Hermitian scalar operator. Gauge-fixed gauge fields, ghosts, and other unphysical variables may not have positive spectral densities. For operators with nonzero vacuum expectation value, subtract the vacuum expectation value before discussing the connected spectral density.
:::

## From complete states

Let

$$
W(x)=\langle0|\mathcal O(x)\mathcal O(0)|0\rangle,
$$

with $\mathcal O$ Hermitian. Translation invariance gives

$$
\mathcal O(x)=e^{iP\cdot x}\mathcal O(0)e^{-iP\cdot x}.
$$

Insert a complete set of energy-momentum eigenstates:

$$
\mathbf 1=\sum_n |n\rangle\langle n|.
$$

Then

$$
\begin{aligned}
W(x)
&=\sum_n \langle0|\mathcal O(x)|n\rangle\langle n|\mathcal O(0)|0\rangle \\
&=\sum_n e^{-ip_n\cdot x}\left|\langle n|\mathcal O(0)|0\rangle\right|^2.
\end{aligned}
$$

The spectral condition says $p_n^0\ge0$. Lorentz invariance says that, for scalar operators, the density of states depends on the invariant mass $s=p_n^2$ rather than on a preferred frame. Therefore the sum can be organized as

$$
\boxed{
W(x)=\int_0^\infty ds\,\rho_{\mathcal O}(s)\Delta^+(x;s).
}
$$

Here

$$
\Delta^+(x;s)=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p,s}}e^{-ip\cdot x},
\qquad
E_{\mathbf p,s}=\sqrt{\mathbf p^2+s}.
$$

The function $\rho_{\mathcal O}(s)$ is the spectral density of the operator $\mathcal O$.

## Positivity

The positivity of the spectral density is not a perturbative statement. It is Hilbert-space positivity.

For a Hermitian operator,

$$
\rho_{\mathcal O}(s)
$$

is built from sums of squared matrix elements such as

$$
\left|\langle n|\mathcal O(0)|0\rangle\right|^2.
$$

Hence

$$
\boxed{
\rho_{\mathcal O}(s)\ge0.
}
$$

Equivalently, for any test function $f(x)$,

$$
|\Psi_f\rangle=\int d^4x\,f(x)\mathcal O(x)|0\rangle
$$

has nonnegative norm:

$$
\langle\Psi_f|\Psi_f\rangle\ge0.
$$

That norm is exactly a smeared two-point function. The Källén–Lehmann representation is the momentum-space expression of this positivity.

## Time-ordered representation

Time ordering gives

$$
D_F^{\mathcal O}(x)
=\langle0|T\{\mathcal O(x)\mathcal O(0)\}|0\rangle.
$$

Since each fixed-$s$ component behaves like a free scalar two-point function of mass $\sqrt{s}$,

$$
D_F^{\mathcal O}(x)
=\int_0^\infty ds\,\rho_{\mathcal O}(s)D_F(x;s).
$$

Fourier transforming gives

$$
\boxed{
D_F^{\mathcal O}(p)
=\int_0^\infty ds\,\rho_{\mathcal O}(s)
\frac{i}{p^2-s+i0}.
}
$$

This equation is the Källén–Lehmann spectral representation of the exact Feynman two-point function.

For a free scalar field,

$$
\rho(s)=\delta(s-m^2),
$$

so the representation collapses to

$$
D_F(p)=\frac{i}{p^2-m^2+i0}.
$$

For an interacting field, the isolated delta function is only part of the story.

## One-particle pole and continuum

Suppose the theory has a stable scalar particle of physical mass $m$, and suppose $\mathcal O$ has nonzero overlap with that particle:

$$
\langle p|\mathcal O(0)|0\rangle\neq0.
$$

Then the spectral density contains an isolated one-particle term:

$$
\rho_{\mathcal O}(s)\supset Z_{\mathcal O}\delta(s-m^2),
\qquad
Z_{\mathcal O}\ge0.
$$

The exact propagator contains the corresponding pole:

$$
D_F^{\mathcal O}(p)
=\frac{iZ_{\mathcal O}}{p^2-m^2+i0}
+
\text{less singular terms near }p^2=m^2.
$$

Multiparticle states produce a continuum. If the lightest multiparticle state with the same quantum numbers has invariant-mass threshold $s_{\rm th}$, then

$$
\rho_{\mathcal O}(s)=Z_{\mathcal O}\delta(s-m^2)
+\theta(s-s_{\rm th})\rho_{\rm cont}(s).
$$

The value of $s_{\rm th}$ depends on the theory and on the quantum numbers of $\mathcal O$. For example, a scalar operator with vacuum quantum numbers may couple to two-particle states; an operator odd under a $\mathbb Z_2$ symmetry may first couple to one-particle and then three-particle states.

## Branch cuts and discontinuities

An isolated delta function in $\rho(s)$ produces an isolated pole in $D_F(p)$. A continuum in $\rho(s)$ produces a branch cut in $D_F(p)$ along the physical timelike region.

Let

$$
q=p^2.
$$

Across the cut, the discontinuity of the exact propagator is proportional to the spectral density:

$$
\boxed{
\operatorname{Disc}D_F(q)
\equiv D_F(q+i0)-D_F(q-i0)
=2\pi\rho(q)
}
$$

for $q$ in the support of the spectral density, with qft.org's convention that the propagator includes the numerator factor $i$.

This is the seed of many later ideas: dispersion relations, unitarity cuts, optical theorems, resonance line shapes, and the analytic structure of scattering amplitudes. Foundations only needs the first lesson: the exact propagator knows the mass spectrum.

## Field strength and residue

For an elementary-looking scalar field, textbooks often write the spectral density as

$$
\rho(s)=Z\delta(s-m_{\rm phys}^2)+\rho_{\rm cont}(s).
$$

The number $Z$ is the pole residue of that field's two-point function. It measures the overlap of the field with the one-particle state. In LSZ scattering theory, one often chooses a renormalized interpolating field whose pole residue is normalized to one. In that convention,

$$
D_F^{\phi_R}(p)\sim\frac{i}{p^2-m_{\rm phys}^2+i0}
$$

near the physical pole.

For a bare canonical field in a regulated theory, the equal-time commutation relation implies a sum rule of the schematic form

$$
\int_0^\infty ds\,\rho(s)=1,
$$

so

$$
0\le Z\le1.
$$

This statement is regulator- and normalization-sensitive. It is best understood as a statement about a conventionally normalized canonical field before taking continuum renormalization limits too casually. The robust physical statement is the pole-residue interpretation: a local operator may have some overlap, all overlap, or no overlap with a given one-particle state.

## Vacuum subtraction

If $\mathcal O$ has a nonzero vacuum expectation value,

$$
\langle0|\mathcal O|0\rangle\neq0,
$$

then the complete-state insertion includes the vacuum state. This gives a zero-momentum disconnected contribution.

For spectral information about excitations, use the connected operator

$$
\mathcal O_c(x)=\mathcal O(x)-\langle0|\mathcal O|0\rangle.
$$

Then

$$
\langle0|\mathcal O_c(x)\mathcal O_c(0)|0\rangle
$$

has no vacuum contribution, and its spectral density starts at the lightest non-vacuum state with the same quantum numbers as $\mathcal O$.

## Euclidean interpretation

After Wick rotation, the Euclidean two-point function has the representation

$$
G_E(p_E)=\int_0^\infty ds\,\rho(s)\frac{1}{p_E^2+s}.
$$

This is a Stieltjes transform of a positive measure. Positivity imposes strong constraints: not every function of $p_E^2$ can be a physical two-point function of a positive-norm QFT.

At large Euclidean separations, the lightest state that couples to $\mathcal O$ dominates. Schematically,

$$
G_E(r)\sim e^{-m_{\rm lightest}r}
$$

up to powers of $r$, if there is a mass gap and a lightest isolated state. This is why lattice QFT can extract masses from exponential decay of Euclidean correlators.

## Why this matters

The spectral representation is a rare formula that is both conceptual and practical.

It tells you:

1. **Mass spectrum:** poles and thresholds in the propagator correspond to physical states.
2. **Positivity:** the spectral density is nonnegative for physical operators in a positive Hilbert space.
3. **Renormalization meaning:** field-strength residues are overlaps with physical one-particle states.
4. **Analytic structure:** multiparticle continua produce branch cuts.
5. **Euclidean constraints:** physical Euclidean correlators are not arbitrary functions.

It also explains why a propagator that falls faster than $1/p^2$ at large momentum is suspicious if one insists on a standard positive spectral representation. Extra higher-derivative poles often signal negative-norm states unless the theory is interpreted as an effective theory with a cutoff or with additional structure.

## Common pitfalls

### Thinking every field has a one-particle pole

A local operator has a pole only if it overlaps with a stable one-particle state. Composite operators, gauge-dependent fields, or operators in a confining theory may have very different spectral structure.

### Confusing bare mass with physical mass

The pole location is the physical mass. Parameters in a Lagrangian are not automatically pole masses once interactions are included.

### Forgetting the continuum

An interacting propagator is usually not just a shifted free pole. Multiparticle states contribute a continuum and therefore branch cuts.

### Applying positivity to unphysical fields

Gauge-fixed vector fields and ghosts may live in an indefinite or constrained state space. Positivity is guaranteed for gauge-invariant physical operators, not for every variable used in a gauge-fixed calculation.

### Treating the spectral density as a perturbative gadget

The representation follows from general principles: translation invariance, Lorentz invariance, the spectral condition, and Hilbert-space positivity. Perturbation theory may compute approximations to it, but it does not create the representation.

## Relation to other topics

- [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/) introduce non-time-ordered correlators and positive-energy support.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) is recovered when the spectral density is a single delta function.
- [iε Prescription](/foundations/correlators-and-propagators/i-epsilon-prescription/) explains the pole prescription inside every free propagator in the spectral integral.
- [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/) will separate vacuum pieces from connected spectral information.
- [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/) will use pole residues to relate correlation functions to scattering amplitudes.
- [Unitarity](/foundations/structural-principles/unitarity/) will connect positivity and discontinuities to probability conservation.
- [Reflection Positivity](/foundations/structural-principles/reflection-positivity/) will give the Euclidean counterpart of Hilbert-space positivity.

## Research status

- **Established:** The Källén–Lehmann representation for scalar two-point functions is a textbook-standard consequence of the spectral condition and Hilbert-space positivity.
- **Subtle:** Gauge theories, massless particles, infraparticles, unstable resonances, confinement, and finite-temperature systems modify the naive pole-plus-continuum picture.
- **Out of scope here:** Detailed dispersion relations, anomalous thresholds, nonperturbative spectral reconstruction, positivity bounds, and numerical inverse problems in lattice QFT.

## Exercises

### Exercise 1: Free-field spectral density

Show that a free scalar field has

$$
\rho(s)=\delta(s-m^2)
$$

in the Källén–Lehmann representation.

<details>
<summary><strong>Solution</strong></summary>

The free scalar Wightman function is

$$
\Delta^+(x;m^2)=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}e^{-ip\cdot x}.
$$

The spectral representation says

$$
\Delta^+(x)=\int_0^\infty ds\,\rho(s)\Delta^+(x;s).
$$

For a free field of mass $m$, the only invariant mass that appears is $s=m^2$. Therefore

$$
\rho(s)=\delta(s-m^2),
$$

which gives

$$
\int_0^\infty ds\,\delta(s-m^2)\Delta^+(x;s)=\Delta^+(x;m^2).
$$

</details>

### Exercise 2: Positivity from a smeared state

Let

$$
|\Psi_f\rangle=\int d^4x\,f(x)\mathcal O(x)|0\rangle.
$$

Show that the two-point function defines a positive quadratic form.

<details>
<summary><strong>Solution</strong></summary>

Compute the norm:

$$
\begin{aligned}
\langle\Psi_f|\Psi_f\rangle
&=\int d^4x\,d^4y\,f^*(x)f(y)
\langle0|\mathcal O(x)\mathcal O(y)|0\rangle.
\end{aligned}
$$

Since this is a Hilbert-space norm,

$$
\langle\Psi_f|\Psi_f\rangle\ge0.
$$

Thus the two-point function is a positive distribution. In the spectral representation this positivity appears as

$$
\rho_{\mathcal O}(s)\ge0.
$$

</details>

### Exercise 3: Stable particle pole

Suppose

$$
\rho(s)=Z\delta(s-m^2)+\theta(s-s_{\rm th})\rho_{\rm cont}(s),
$$

with $s_{\rm th}>m^2$. Show that the propagator has an isolated pole at $p^2=m^2$ with residue $iZ$.

<details>
<summary><strong>Solution</strong></summary>

Insert the spectral density into

$$
D_F(p)=\int_0^\infty ds\,\rho(s)\frac{i}{p^2-s+i0}.
$$

The delta-function term gives

$$
\int_0^\infty ds\,Z\delta(s-m^2)\frac{i}{p^2-s+i0}
=\frac{iZ}{p^2-m^2+i0}.
$$

The continuum integral starts at $s_{\rm th}>m^2$, so it is less singular near $p^2=m^2$. Therefore the isolated pole has residue $iZ$.

</details>

### Exercise 4: Discontinuity across the cut

Using

$$
D_F(q)=\int_0^\infty ds\,\rho(s)\frac{i}{q-s+i0},
$$

show that

$$
\operatorname{Disc}D_F(q)=2\pi\rho(q)
$$

where $q$ lies in the support of $\rho$.

<details>
<summary><strong>Solution</strong></summary>

The discontinuity is

$$
D_F(q+i0)-D_F(q-i0)
=i\int_0^\infty ds\,\rho(s)
\left[\frac1{q-s+i0}-\frac1{q-s-i0}\right].
$$

Using

$$
\frac1{x+i0}-\frac1{x-i0}=-2\pi i\delta(x),
$$

we get

$$
\operatorname{Disc}D_F(q)
=i\int_0^\infty ds\,\rho(s)(-2\pi i)\delta(q-s)
=2\pi\rho(q).
$$

</details>

### Exercise 5: Vacuum subtraction

Let $\langle0|\mathcal O|0\rangle=v\neq0$. Show that the disconnected part of the two-point function is removed by

$$
\mathcal O_c=\mathcal O-v.
$$

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
\begin{aligned}
\langle0|\mathcal O_c(x)\mathcal O_c(0)|0\rangle
&=\langle0|[\mathcal O(x)-v][\mathcal O(0)-v]|0\rangle \\
&=\langle0|\mathcal O(x)\mathcal O(0)|0\rangle-v^2-v^2+v^2.
\end{aligned}
$$

Since $v$ is constant,

$$
\langle0|\mathcal O_c(x)\mathcal O_c(0)|0\rangle
=\langle0|\mathcal O(x)\mathcal O(0)|0\rangle-v^2.
$$

Thus the vacuum intermediate-state contribution is removed.

</details>

### Exercise 6: Euclidean large-distance behavior

Assume the Euclidean spectral representation

$$
G_E(r)=\int_0^\infty ds\,\rho(s)G_E(r;s),
$$

and suppose the lightest state that couples to $\mathcal O$ is an isolated particle of mass $m$. Explain why $G_E(r)$ decays as $e^{-mr}$ up to powers of $r$ at large $r$.

<details>
<summary><strong>Solution</strong></summary>

For fixed mass $\sqrt{s}$, the Euclidean massive propagator decays at large distance as

$$
G_E(r;s)\sim e^{-\sqrt{s}\,r}
$$

up to powers of $r$. The spectral integral is a positive superposition of such terms. At large $r$, the smallest value of $\sqrt{s}$ with nonzero spectral weight decays slowest and dominates.

If the lightest contribution is an isolated pole at $s=m^2$, then

$$
G_E(r)\sim Z e^{-mr}
$$

up to powers of $r$. Heavier states and continua are exponentially suppressed relative to it.

</details>

## Sources and further reading

### Primary references

- G. Källén, “On the Definition of the Renormalization Constants in Quantum Electrodynamics,” *Helvetica Physica Acta* **25** (1952), for one of the original spectral-representation analyses.
- H. Lehmann, “Über Eigenschaften von Ausbreitungsfunktionen und Renormierungskonstanten quantisierter Felder,” *Nuovo Cimento* **11** (1954), for the classic Lehmann representation of propagators.
- A. S. Wightman, “Quantum Field Theory in Terms of Vacuum Expectation Values,” *Physical Review* **101** (1956), for the vacuum-expectation-value framework behind spectral representations.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 15, for the Källén–Lehmann representation of exact scalar propagators and its use in renormalization.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §10.7, for the nonperturbative derivation, positivity, and propagator consequences.
- M. Srednicki, *Quantum Field Theory*, §13, for the Lehmann–Källén form of the exact propagator.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §7.1, for the spectral representation and field-strength renormalization.
- R. Haag, *Local Quantum Physics*, for the spectral condition and operator-algebraic viewpoint.

### For a first pass

- Srednicki, §13.
- Peskin and Schroeder, §7.1.
- Coleman, §15.2.

### For mathematical precision

- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for Wightman functions, spectral support, locality, and reconstruction.
- R. Jost, *The General Theory of Quantized Fields*, for analytic and axiomatic aspects of spectral representations.
- N. N. Bogoliubov and D. V. Shirkov, *Introduction to the Theory of Quantized Fields*, for dispersion-theoretic and causal-distribution treatments.

## Version history

- **2026-05-23:** Initial qft.org page on the Källén–Lehmann representation, spectral density, positivity, one-particle poles, continua, branch cuts, field-strength residues, and Euclidean large-distance behavior.
