---
title: "Winding Number"
description: "Defines winding number as the degree of a map or characteristic-class integral, with examples for vortices, sigma-model lumps, Skyrmions, Chern–Simons winding, and instanton number."
sidebar:
  label: "Winding Number"
  order: 3
level: Advanced
status: "Polished draft"
source: "Srednicki §§92–94; Polyakov Ch. 6; Nakahara on degree, monopoles, and instantons; Frankel on forms and degree; Coleman on solitons; Altland–Simons Ch. 8."
topics:
  - winding number
  - degree of a map
  - topological charge
  - pullback form
  - vortex winding
  - sigma-model lump
  - Skyrmion number
  - instanton number
canonicalTopics:
  - winding-number
  - degree-of-map
  - topological-charge-density
  - topological-current
  - instanton-number
researchStatus:
  established:
    - "Winding numbers are integer-valued homotopy invariants computed by normalized integrals of pullback volume forms, Chern classes, or related characteristic forms."
    - "In QFT, the same integer may appear as a soliton charge, magnetic flux, instanton number, baryon number in a Skyrme model, or a large-gauge-transformation winding."
  active:
    - "Quantum theories refine winding-number conservation through boundaries, defects, anomalies, dynamical charged objects, global-form choices, and higher-form symmetry backgrounds."
---

## Summary

A winding number is an integer that counts how many times one space wraps around another. In QFT it is the most concrete form of topological charge.

For a smooth map between compact oriented $n$-manifolds of the same dimension,

$$
f:M_n\to N_n,
$$

the winding number is the **degree** of the map. If $\omega_N$ is a normalized volume form on $N$ with

$$
\int_N \omega_N=1,
$$

then

$$
\deg(f)=\int_M f^*\omega_N.
$$

For the standard examples, this abstract formula becomes the formulas one actually uses:

$$
\begin{array}{c|c|c}
\text{map} & \text{topological charge} & \text{physics} \\
\hline
S^1\to S^1 & \displaystyle \frac{1}{2\pi}\oint d\varphi & \text{vortex winding} \\
S^2\to S^2 & \displaystyle \frac{1}{4\pi}\int \mathbf n\cdot(\partial_1\mathbf n\times\partial_2\mathbf n)\,d^2x & \text{sigma-model lump or monopole map} \\
S^3\to SU(N) & \displaystyle \frac{1}{24\pi^2}\int \operatorname{tr}(g^{-1}dg)^3 & \text{large gauge transformation or Skyrmion-type winding}.
\end{array}
$$

<figure class="doc-figure" style="--figure-width: 56rem;">

![Diagram showing a map from a source sphere to a target sphere, the degree integral using a normalized pullback form, and the standard S1, S2, S3, and gauge-bundle winding formulas.](/figures/symmetry-anomalies-topology/winding-number-degree-map.svg)

<figcaption>

For $S^1\to S^1$, winding is the integral of $g^{-1}dg$ around the domain circle. The higher-dimensional version is degree: choose a normalized generator $\omega$ of top cohomology on the target, pull it back, and integrate. In gauge theory, the same idea appears through Chern classes and Chern–Simons winding forms.

</figcaption>
</figure>

Winding numbers are robust because they cannot vary continuously. A smooth one-parameter deformation changes the integral continuously, but the result is integer-valued, so it stays fixed unless the map becomes singular, the boundary condition changes, or the configuration leaves the allowed field space.

## Prerequisites

You should know [Topology of Field Configurations](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/topology-of-field-configurations/) and [Homotopy Classification](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/homotopy-classification/). You should also know the orientation and differential-form conventions in [Conventions and Notation](/symmetry-anomalies-topology/conventions/) and the role of topological action terms from [Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/).

Mathematically, you need the pullback of a differential form, Stokes’ theorem, and the idea that $H^n(N,\mathbb Z)$ has integral generators when $N$ is compact and oriented. The page uses this language operationally: a normalized form gives an integer when pulled back by a map representing an integral homology or homotopy class.

## Degree of a map

Let $M$ and $N$ be compact, connected, oriented $n$-manifolds. The degree of a smooth map

$$
f:M\to N
$$

is the integer $\deg(f)$ defined by

$$
\int_M f^*\omega = \deg(f)\int_N\omega
$$

for every top form $\omega$ on $N$. Choosing $\int_N\omega=1$ gives the compact formula

$$
\deg(f)=\int_M f^*\omega.
$$

Geometrically, if $y\in N$ is a regular value, then

$$
\deg(f)=\sum_{x\in f^{-1}(y)} \operatorname{sign}\det(df_x).
$$

A preimage where the map preserves orientation contributes $+1$; one where it reverses orientation contributes $-1$. This gives the literal counting interpretation: how many times does $M$ cover $N$, with orientation signs?

The degree is invariant under homotopy. If $f_s:M\to N$ is smooth in $s$, then $\deg(f_s)$ cannot change because it is integer-valued and varies continuously. More explicitly, the $s$-variation of the pullback top form is exact, and the integral of an exact form on a closed manifold vanishes by Stokes’ theorem.

:::note[Source note]
Differential-geometry texts usually define degree for maps between compact oriented manifolds. In QFT, the source is often $\mathbb R^d$ compactified by a finite-energy boundary condition. That compactification is part of the physics. Without it, a winding integral may not be an integer.
:::

## The circle example: vortex winding

The simplest winding number is a map from a circle to a circle. Write a $U(1)$-valued field as

$$
U(\theta)=e^{i\alpha(\theta)}.
$$

Single-valuedness means

$$
U(\theta+2\pi)=U(\theta),
$$

so the phase can shift by an integer multiple of $2\pi$:

$$
\alpha(2\pi)-\alpha(0)=2\pi n,
\qquad n\in\mathbb Z.
$$

The winding number is

$$
n=\frac{1}{2\pi}\int_0^{2\pi}d\theta\,\frac{d\alpha}{d\theta}
=\frac{1}{2\pi}\oint d\alpha.
$$

This is exactly the vortex winding for a broken global $U(1)$ order parameter. Around a vortex core,

$$
\phi(r,\theta)\simeq v e^{i n\theta}
$$

at large radius, so a loop linking the vortex maps to the vacuum circle with degree $n$.

For a gauged $U(1)$ Higgs theory, the scalar phase is gauge-dependent. The gauge-invariant winding is usually seen as flux. If the Higgs field has charge $q$ and finite energy requires $D\phi\to0$ at infinity, then

$$
q\oint A = 2\pi n
$$

in the common convention $D=d-iqA$. Thus

$$
\Phi=\oint A=\frac{2\pi n}{q}.
$$

The same integer appears, but the physical observable is magnetic flux rather than a gauge-dependent phase.

## The sphere example: lumps and hedgehogs

Let

$$
\mathbf n(x)=(n^1,n^2,n^3),
\qquad
\mathbf n\cdot\mathbf n=1,
$$

so the target is $S^2$. A map from compactified two-dimensional space to $S^2$ has integer degree

$$
Q=\frac{1}{4\pi}\int d^2x\,
\mathbf n\cdot
(\partial_1\mathbf n\times\partial_2\mathbf n).
$$

In differential-form language, this is

$$
Q=\frac{1}{8\pi}\int_{\Sigma_2}
\epsilon_{abc}\,n^a\,dn^b\wedge dn^c.
$$

The normalization is chosen so that the identity map $S^2\to S^2$ has $Q=1$.

The same formula classifies the hedgehog map at infinity for monopoles. For the unit hedgehog,

$$
\mathbf n(\theta,\phi)=
(\sin\theta\cos\phi,\sin\theta\sin\phi,\cos\theta),
$$

the pullback of the target area form is

$$
\frac{1}{4\pi}\sin\theta\,d\theta\wedge d\phi,
$$

and integration over $S^2$ gives $Q=1$.

## The three-sphere example: group-valued winding

For maps

$$
g:S^3\to SU(N),
$$

the integer winding number is

$$
\nu(g)=\frac{1}{24\pi^2}\int_{S^3}
\operatorname{tr}(g^{-1}dg\wedge g^{-1}dg\wedge g^{-1}dg).
$$

For $SU(2)\simeq S^3$, this is the ordinary degree of a map from $S^3$ to $S^3$. For $SU(N)$ with $N\ge2$, it represents the generator of $H^3(SU(N),\mathbb Z)$ and the homotopy group

$$
\pi_3(SU(N))\simeq\mathbb Z.
$$

This formula appears in three connected places.

First, it gives the winding of a Skyrme field $U(\mathbf x):S^3\to SU(2)$. With a sign depending on whether one uses $U^{-1}dU$ or $dU\,U^{-1}$, the Skyrmion baryon number is

$$
B=\frac{1}{24\pi^2}\int_{S^3}
\operatorname{tr}(U^{-1}dU)^3.
$$

Second, it gives the winding number of a large gauge transformation in three spatial dimensions.

Third, it appears in the change of the Chern–Simons functional under a large gauge transformation:

$$
CS(A^g)-CS(A)=\nu(g)
$$

up to the chosen normalization of $CS(A)$. This is why Chern–Simons levels are quantized.

:::note[Convention-sensitive sign]
Some references define the Skyrmion current with a minus sign, often so that a chosen hedgehog ansatz has baryon number $+1$. The sign depends on orientation, the trace convention, and whether the left-invariant form $U^{-1}dU$ or right-invariant form $dU\,U^{-1}$ is used. The invariant statement is integrality and homotopy invariance.
:::

## Instanton number as a winding number

Yang–Mills instanton number is a winding number in two equivalent disguises.

On $\mathbb R^4_E$, finite action requires

$$
F\to0
\qquad |x|\to\infty.
$$

Therefore $A$ approaches a pure gauge at infinity, which defines a map

$$
g:S^3_\infty\to G.
$$

The winding of $g$ labels the instanton sector. In the bulk, the same integer is

$$
k=\frac{1}{8\pi^2}\int_{M_4}\operatorname{tr}(F\wedge F)
$$

for $G=SU(N)$ with the trace convention $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$ and the standard orientation. With the volume convention $F=dA-iA\wedge A$, this is the convention used throughout the Topological Terms chapter unless a page states otherwise.

The equality between boundary winding and bulk integral is the statement that the four-form $\operatorname{tr}(F\wedge F)$ is locally exact:

$$
\operatorname{tr}(F\wedge F)=d\omega_3(A),
$$

where $\omega_3(A)$ is the Chern–Simons three-form. On a nontrivial bundle, the local representatives on patches must be glued, and the integral remains a global characteristic class.

This is the cleanest example of a recurring theme: a winding number may be computed either from boundary data or from a bulk density.

## Winding density and topological currents

A topological charge is often written as an integral of a density:

$$
Q=\int_\Sigma j^0_{\rm top}.
$$

The current is called topological when its conservation is an identity, not an Euler–Lagrange equation. For the $O(3)$ sigma model in $2+1$ dimensions, define

$$
j^\mu_{\rm top}
=\frac{1}{8\pi}\epsilon^{\mu\nu\rho}\epsilon_{abc}
 n^a\partial_\nu n^b\partial_\rho n^c.
$$

Then

$$
\partial_\mu j^\mu_{\rm top}=0
$$

follows from antisymmetry and $n^a n^a=1$, not from the equations of motion. The charge

$$
Q=\int d^2x\,j^0_{\rm top}
$$

is the degree $S^2\to S^2$.

In $3+1$ dimensions, the Skyrme model has the baryon current

$$
B^\mu=\frac{1}{24\pi^2}\epsilon^{\mu\nu\rho\sigma}
\operatorname{tr}
(U^{-1}\partial_\nu U\,U^{-1}\partial_\rho U\,U^{-1}\partial_\sigma U),
$$

again up to the sign convention described above. Its conservation is a topological identity as long as $U$ remains smooth and well-defined.

The phrase “as long as” is important. Topological currents can fail to give conserved charges when fields are singular, when boundaries leak charge, when defects end, or when quantum tunneling connects sectors.

## Why the integer cannot change smoothly

There are two useful ways to see homotopy invariance.

The first is discreteness. If $Q(s)$ is an integer-valued quantity depending continuously on a deformation parameter $s$, then $Q(s)$ is constant on connected intervals. Smooth deformations cannot change an integer unless continuity fails.

The second is Stokes’ theorem. Suppose

$$
Q=\int_M f^*\omega
$$

and $f_s$ is a deformation. The variation of the pullback of a closed top form is exact:

$$
\frac{d}{ds}f_s^*\omega=d(\cdots).
$$

If $M$ is closed, then

$$
\frac{dQ}{ds}=\int_M d(\cdots)=0.
$$

If $M$ has a boundary, the last equality becomes a boundary term. That is exactly why winding number can change through boundaries, punctures, singular cores, or operator insertions.

## When winding number is not conserved

A winding number is conserved under the deformations used to define it. Change the allowed deformations and the conservation law can change.

Common failure modes include:

| Failure mode | What happens |
|---|---|
| Boundary leakage | The exact-form variation becomes a boundary term. |
| Singular field event | The map to the target is not defined at a point or along a defect. |
| Defect endpoint | A string can end on a monopole, so string winding is not separately conserved. |
| Dynamical charged object | A probe defect can break when an endpoint object is in the spectrum. |
| Gauge quotient | A winding written in a gauge-dependent variable is not a physical charge. |
| Tunneling | Euclidean instantons can change Chern–Simons number between Lorentzian vacua. |
| Anomaly | A current that looks conserved classically may have anomalous divergence. |

This is not a list of exceptions to topology. It is a list of changes in the topology of the allowed configuration space.

## Relation to characteristic classes

Not every integer in QFT is best viewed as the degree of a map between spheres. Gauge fields often require bundles and characteristic classes.

The Dirac monopole charge is the first Chern number of a $U(1)$ bundle over $S^2$:

$$
q_m=\frac{1}{2\pi}\int_{S^2} F
\in\mathbb Z
$$

with the normalization in which minimally charged matter has unit electric charge.

Yang–Mills instanton number is the second Chern number:

$$
k=\frac{1}{8\pi^2}\int_{M_4}\operatorname{tr}(F\wedge F).
$$

These are winding numbers in a broader sense: integers obtained by integrating normalized characteristic forms. They may also be represented by transition functions on overlaps or maps at infinity. The differential-form expression is usually the most compact way to compute them.

## Common pitfalls

**Forgetting normalization.** The difference between $1/(2\pi)$, $1/(4\pi)$, $1/(8\pi^2)$, and $1/(24\pi^2)$ is not cosmetic. These factors are chosen so the basic generator has charge one.

**Forgetting orientation.** Reversing the orientation of the source or target flips the sign of the degree.

**Using a local coordinate formula outside its patch.** A winding number may require multiple patches or a globally defined pullback form. Coordinate singularities are not necessarily physical singularities.

**Calling every integral an integer.** The integral is quantized only when the form represents an integral cohomology class and the boundary conditions make the source compact or properly relative.

**Confusing gauge-dependent winding with gauge-invariant charge.** In gauge theories, translate phase winding into flux, holonomy, bundle class, or Chern number.

**Ignoring boundaries and defects.** Stokes’ theorem is the watchdog. If the source has a boundary, a winding number can flow out.

## Relation to nearby pages

[Homotopy Classification](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/homotopy-classification/) explains when the relevant sphere and target are $S^1$, $S^2$, $S^3$, $G/H$, or a gauge group.

[Vortices](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/vortices/) specializes the $S^1\to S^1$ formula to superfluids and Abelian Higgs vortices.

[Monopoles](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/monopoles/) develops the $S^2\to S^2$ map, magnetic flux, and bundle interpretation.

[Instanton Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/instanton-number/) develops the $\int\operatorname{tr}(F\wedge F)$ formula and its relation to Euclidean tunneling.

[Quantization of Couplings](/symmetry-anomalies-topology/topological-terms/quantization-of-couplings/) and [Periodicity and Large Gauge Transformations](/symmetry-anomalies-topology/topological-terms/periodicity-and-large-gauge-transformations/) explain how these integers force theta periodicities, Wess–Zumino quantization, and Chern–Simons level quantization.

## Research status

The mathematical and classical-field-theory foundations of winding number are settled. What remains subtle in modern QFT is not whether the degree formula is integer-valued, but which integer is actually conserved, which operator measures it, and whether quantum effects allow it to change.

In modern language, winding number often becomes the charge of a higher-form symmetry, the flux measured by a topological defect, or the obstruction encoded by an anomaly inflow theory. In gauge theories, global form and line-operator spectrum can change the allowed charge lattice. In systems with boundaries, a winding number in the bulk can become an anomalous charge on the boundary. The old integer remains, but its job title changes.

## Exercises

### Exercise 1: Degree of the identity map

Use the normalized area form

$$
\omega=\frac{1}{4\pi}\sin\theta\,d\theta\wedge d\phi
$$

on $S^2$ to compute the degree of the identity map $S^2\to S^2$.

<details><summary><strong>Solution</strong></summary>

For the identity map, the pullback of $\omega$ is $\omega$ itself. Therefore

$$
\deg(\operatorname{id})=
\int_{S^2}\omega
=\frac{1}{4\pi}\int_0^{2\pi}d\phi\int_0^\pi d\theta\,\sin\theta
=\frac{1}{4\pi}(2\pi)(2)=1.
$$

</details>

### Exercise 2: Winding of a phase map

Let

$$
U(\theta)=e^{i(3\theta+\alpha_0)}.
$$

Compute its winding number as a map $S^1\to S^1$.

<details><summary><strong>Solution</strong></summary>

The phase is $\alpha(\theta)=3\theta+\alpha_0$. Hence

$$
n=\frac{1}{2\pi}\int_0^{2\pi}d\theta\,\frac{d\alpha}{d\theta}
=\frac{1}{2\pi}\int_0^{2\pi}3\,d\theta
=3.
$$

The constant offset $\alpha_0$ does not affect the winding.

</details>

### Exercise 3: Why the vortex core is necessary

A complex scalar has asymptotic behavior $\phi\sim v e^{i\theta}$ around a loop. Explain why $\phi$ must vanish somewhere inside the loop if it is a smooth field on the disk.

<details><summary><strong>Solution</strong></summary>

If $\phi$ were nonzero everywhere on the disk, its phase would define a continuous map from the entire disk $D^2$ to $S^1$ extending the boundary map $e^{i\theta}$. But the boundary map has winding number one and is not null-homotopic. It cannot extend to the disk as an $S^1$-valued map. Therefore the assumption that $\phi$ is nonzero everywhere is false. The field must leave the vacuum circle, and for a complex scalar that means $\phi=0$ somewhere in the core.

</details>

### Exercise 4: Boundary leakage

Suppose $Q=\int_M f^*\omega$ with $d\omega=0$, but $M$ has boundary. Show schematically why $Q$ can change under a homotopy.

<details><summary><strong>Solution</strong></summary>

For a homotopy $f_s$, the variation of the pullback of a closed form has the form

$$
\frac{d}{ds}f_s^*\omega=d\eta_s
$$

for some form $\eta_s$ built from the deformation vector and $\omega$. Therefore

$$
\frac{dQ}{ds}=\int_M d\eta_s=\int_{\partial M}\eta_s.
$$

If $\partial M$ is empty or the boundary term vanishes by boundary conditions, $Q$ is conserved. Otherwise winding can flow through the boundary.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§92–94. Solitons, monopoles, instantons, and theta vacua.
- A. M. Polyakov, *Gauge Fields and Strings*, Ch. 6. Topology of gauge fields and instanton winding.
- S. Coleman, *Aspects of Symmetry*. Solitons, instantons, and symmetry-breaking lectures.
- M. Nakahara, *Geometry, Topology and Physics*. Degree, homotopy groups, monopoles, Chern classes, and instantons.
- T. Frankel, *The Geometry of Physics*. Differential forms, degree, winding, bundles, and gauge-field topology.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, Ch. 8. Homotopy, theta terms, Wess–Zumino terms, and Chern–Simons terms in matter examples.
- N. Manton and P. Sutcliffe, *Topological Solitons*. Detailed soliton and topological-charge examples.
- D. Tong, *TASI Lectures on Solitons*, arXiv:hep-th/0509216. Efficient physics introduction to winding charges.

## Version history

- **2026-06-18:** Initial polished draft.
