---
title: "Monopoles"
description: "Explains monopoles as codimension-three topological defects, from global hedgehogs to smooth ’t Hooft–Polyakov magnetic monopoles and their BPS limit."
sidebar:
  label: "Monopoles"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki, ch. 92; Shifman, ch. 4; Nakahara, chs. 1 and 4; Manton and Sutcliffe."
topics:
  - monopoles
  - magnetic charge
  - hedgehog ansatz
  - topological defects
  - ’t Hooft–Polyakov monopole
  - Bogomolnyi bound
  - dyons
canonicalTopics:
  - nonperturbative-qft
  - solitons
  - monopoles
  - topological-defects
researchStatus:
  established:
    - "The ’t Hooft–Polyakov monopole is a smooth finite-energy magnetic soliton in non-Abelian gauge theory broken to an Abelian subgroup, with magnetic charge classified by topology at spatial infinity."
  active:
    - "Monopole operators, monopole-instantons, confined monopoles, and monopoles in strongly coupled gauge theories remain central in modern studies of confinement, duality, and generalized symmetry."
---

## Summary

A **monopole** is a codimension-three defect. In three spatial dimensions it is particlelike. The boundary surrounding it is a two-sphere,

$$
S^2_\infty,
$$

so the basic topological datum is a map from the sphere at spatial infinity to the vacuum data of the theory.

The cleanest scalar example is the hedgehog map

$$
\hat\phi^a(\hat x)=\hat x^a,
$$

where $\hat x$ is a unit vector in physical space and $\hat\phi$ is a unit vector in an internal vacuum sphere. Its winding number is

$$
n
=
\frac{1}{4\pi}
\int d\theta\,d\varphi\,
\hat\phi\cdot(\partial_\theta\hat\phi\times\partial_\varphi\hat\phi)
\in\mathbb Z.
$$

A global monopole has this topology but a long-range gradient tail, so its energy diverges linearly with the system size. A **gauge monopole**, by contrast, can have finite energy. In the $SU(2)$ Georgi–Glashow model broken to $U(1)$, the smooth ’t Hooft–Polyakov monopole carries magnetic charge

$$
g_m
=
\int_{S^2_\infty}\mathcal B\cdot d\mathbf S
=
\frac{4\pi n}{g}
$$

in the standard adjoint-Higgs normalization.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A monopole as a hedgehog map from the spatial sphere at infinity to the vacuum sphere, and as a smooth gauge monopole with magnetic flux.](/figures/nonperturbative-qft/monopole-hedgehog-map.svg)

<figcaption>

A monopole is a codimension-three defect. The topological charge is the degree of the map $S^2_\infty\to\mathcal M_{\rm vac}$. In a broken non-Abelian gauge theory, the angular scalar gradient is cancelled by the gauge field and the soliton becomes a smooth finite-energy magnetic monopole.

</figcaption>
</figure>

Monopoles are one of the places where topology, gauge theory, and semiclassical physics visibly fuse. The topology is measured at infinity; the gauge field makes the energy finite; the smooth core removes the singularity of the Dirac monopole.

## Prerequisites

You should know [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/), [Vortices](/nonperturbative-qft/solitons-defects-extended-configurations/vortices/), [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/), [Moduli of Saddles](/nonperturbative-qft/semiclassical-methods/moduli-of-saddles/), and [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/).

You should also be comfortable with non-Abelian gauge fields at the level of Yang–Mills theory with an adjoint scalar. The page reviews the needed formulas, but not the full construction of gauge theory.

## Core idea

A monopole is the codimension-three analogue of a vortex. A vortex is detected by going around a circle $S^1$ surrounding its core. A monopole is detected by surrounding the core with a sphere $S^2$.

Finite energy forces the fields at large radius to approach vacuum data. If the vacuum data has a two-sphere worth of possibilities, then the asymptotic field defines a map

$$
\hat\phi_\infty:S^2_\infty\to S^2_{\rm vac}.
$$

Such maps have an integer degree,

$$
\pi_2(S^2)=\mathbb Z.
$$

The degree counts how many times the internal vacuum sphere is covered as one moves over the physical sphere at infinity. A nonzero degree cannot be removed by a smooth finite-energy deformation.

The first surprise is that topology alone does not guarantee finite energy. A global monopole has a linearly divergent energy. The second surprise is that a gauge field can repair this: the non-Abelian gauge field cancels the angular gradient at infinity and leaves a finite magnetic flux.

## Setup and conventions

Work in $3+1$ dimensions with three spatial coordinates $x^i$. For static configurations, the total energy is the relevant functional.

For a real scalar triplet with global $O(3)$ symmetry,

$$
\mathcal L
=
\frac12\partial_\mu\phi^a\partial^\mu\phi^a
-
\frac{\lambda}{4}(\phi^a\phi^a-v^2)^2,
\qquad a=1,2,3.
$$

The vacuum manifold is

$$
\phi^a\phi^a=v^2,
\qquad
\mathcal M_{\rm vac}\simeq S^2.
$$

For the non-Abelian gauge monopole, take the $SU(2)$ Yang–Mills–Higgs theory with an adjoint scalar:

$$
\mathcal L
=
-\frac14 F^a_{\mu\nu}F^{a\mu\nu}
+
\frac12(D_\mu\phi)^a(D^\mu\phi)^a
-
\frac{\lambda}{4}(\phi^a\phi^a-v^2)^2,
$$

where

$$
F^a_{\mu\nu}
=
\partial_\mu A^a_\nu-\partial_\nu A^a_\mu
+g\epsilon^{abc}A^b_\mu A^c_\nu,
$$

and

$$
(D_\mu\phi)^a
=
\partial_\mu\phi^a+g\epsilon^{abc}A^b_\mu\phi^c.
$$

The scalar expectation value breaks

$$
SU(2)\to U(1),
$$

and the vacuum manifold of scalar directions is

$$
SU(2)/U(1)\simeq S^2.
$$

The unbroken $U(1)$ is the long-distance electromagnetic gauge group selected by the Higgs direction.

## The global hedgehog

The standard global monopole ansatz is

$$
\phi^a(x)=v h(r)\hat x^a,
\qquad
\hat x^a=\frac{x^a}{r},
$$

with

$$
h(0)=0,
\qquad
h(\infty)=1.
$$

The field points radially in internal space, hence the name **hedgehog**. At infinity,

$$
\hat\phi^a=\frac{\phi^a}{|\phi|}\to\hat x^a,
$$

so the map $S^2_\infty\to S^2_{\rm vac}$ is the identity map and has degree $+1$.

The energy density contains angular gradients. At large $r$,

$$
\partial_i\hat x^a\partial_i\hat x^a
=
\frac{2}{r^2},
$$

so the gradient energy density behaves as

$$
\mathcal E_{\rm grad}
\sim
\frac{v^2}{r^2}.
$$

The total energy then grows as

$$
E(R)
\sim
4\pi v^2\int^R dr
\sim
4\pi v^2R.
$$

Thus the global monopole is not a finite-energy particle in infinite flat space. It is still important: it cleanly exhibits the topology of $\pi_2(S^2)$, appears in ordered media and cosmological models, and teaches why gauge fields matter.

:::note[Compare with the global vortex]
A global vortex has logarithmically divergent tension because its transverse integral is $\int r\,dr/r^2$. A global monopole has linearly divergent energy because the three-dimensional integral is $\int r^2dr/r^2$.
:::

## The ’t Hooft–Polyakov monopole

The smooth finite-energy monopole appears when the $O(3)$ internal symmetry is gauged as $SU(2)$. The hedgehog scalar is accompanied by a gauge field. A common spherically symmetric ansatz is

$$
\phi^a(x)=v H(r)\hat x^a,
$$

and

$$
A_i^a(x)
=
\frac{1-K(r)}{g r}\epsilon_{aij}\hat x^j,
\qquad
A_0^a=0.
$$

The profile functions obey

$$
H(0)=0,
\qquad
K(0)=1,
\qquad
H(\infty)=1,
\qquad
K(\infty)=0.
$$

Near the origin, these conditions make the fields smooth. At infinity, the scalar approaches the hedgehog direction and the gauge field cancels the angular covariant derivative:

$$
(D_i\phi)^a\to0.
$$

This is the monopole analogue of the gauge vortex. In the vortex, $A_\theta$ cancels the angular phase gradient. In the monopole, $A_i^a$ cancels the angular variation of the Higgs direction on $S^2_\infty$.

The physical magnetic field is the gauge-invariant electromagnetic field associated with the unbroken $U(1)$. Define

$$
\hat\phi^a=\frac{\phi^a}{|\phi|}.
$$

A gauge-invariant long-distance field strength is

$$
\mathcal F_{\mu\nu}
=
\hat\phi^a F^a_{\mu\nu}
-
\frac1g\epsilon^{abc}\hat\phi^a(D_\mu\hat\phi)^b(D_\nu\hat\phi)^c.
$$

At large radius, the corresponding magnetic field is radial,

$$
\mathcal B_i
\sim
\frac{n}{g}\frac{x_i}{r^3},
$$

and the magnetic charge is

$$
g_m
=
\int_{S^2_\infty}dS_i\,\mathcal B_i
=
\frac{4\pi n}{g}.
$$

The monopole is smooth at the origin but looks like a Dirac monopole at long distance. The singular Dirac string has been replaced by a non-Abelian core.

## Finite energy conditions

For the gauge monopole, finite energy requires

$$
|\phi|\to v,
\qquad
D_i\phi\to0,
\qquad
B_i^aB_i^a=O(r^{-4})
\qquad (r\to\infty).
$$

The condition $D_i\phi\to0$ means that the angular change of the Higgs direction is pure gauge at infinity. The residual gauge field is not trivial, however. It carries magnetic flux in the unbroken $U(1)$.

The finite-energy classification can be described by the vacuum manifold

$$
\mathcal M_{\rm vac}=SU(2)/U(1)\simeq S^2,
$$

so that

$$
\pi_2(SU(2)/U(1))=\mathbb Z.
$$

More generally, for symmetry breaking

$$
G\to H,
$$

monopoles are associated with

$$
\pi_2(G/H).
$$

When $G$ is simply connected, one has the useful relation

$$
\pi_2(G/H)\simeq\pi_1(H).
$$

This is why monopoles are tied to the topology of the unbroken gauge group. For $H=U(1)$,

$$
\pi_1(U(1))=\mathbb Z.
$$

## The BPS limit

The monopole has a particularly elegant limit. Let

$$
\lambda\to0
$$

with $v$ fixed. The scalar potential vanishes in the energy functional, but the boundary condition $|\phi|\to v$ remains. The static energy is

$$
E
=
\int d^3x
\left[
\frac12 B_i^aB_i^a
+
\frac12(D_i\phi)^a(D_i\phi)^a
\right].
$$

Complete the square:

$$
E
=
\frac12\int d^3x\,
\left(B_i^a\mp (D_i\phi)^a\right)^2
\pm
\int d^3x\,B_i^a(D_i\phi)^a.
$$

Using the Bianchi identity and integrating by parts, the second term becomes a surface integral:

$$
\int d^3x\,B_i^a(D_i\phi)^a
=
\int_{S^2_\infty}dS_i\,B_i^a\phi^a
=
\frac{4\pi v n}{g}.
$$

Thus

$$
E\ge\frac{4\pi v}{g}|n|.
$$

The bound is saturated by the Bogomolnyi equations

$$
B_i^a=\pm(D_i\phi)^a.
$$

A charge-one BPS monopole has mass

$$
M_{\rm BPS}=\frac{4\pi v}{g}.
$$

This formula is one of the cleanest semiclassical mass formulas in gauge theory. It is nonanalytic in the weak gauge coupling because $v/g$ is large when the massive gauge boson scale $m_W=gv$ is held fixed.

## Core scales and particles

The perturbative spectrum in the broken phase contains massive charged vector bosons with mass

$$
m_W=g v,
$$

and a scalar Higgs excitation with mass

$$
m_H=\sqrt{2\lambda}\,v.
$$

The monopole core has a gauge-field scale of order

$$
r_W\sim m_W^{-1},
$$

and, when $\lambda\ne0$, a scalar-core scale of order

$$
r_H\sim m_H^{-1}.
$$

The monopole mass is of order

$$
M\sim\frac{4\pi v}{g}\times\text{function of }\frac{\lambda}{g^2}.
$$

At weak coupling this is much heavier than the perturbative vector bosons. That is why monopoles are naturally semiclassical objects when the Higgs phase is weakly coupled.

## Dirac monopoles and smooth monopoles

A Dirac monopole in ordinary electrodynamics has magnetic field

$$
\mathbf B=\frac{g_m}{4\pi}\frac{\mathbf r}{r^3},
$$

which is singular at the origin. The vector potential cannot be globally smooth on $S^2$; one either introduces a Dirac string or uses different gauge patches on northern and southern hemispheres.

The ’t Hooft–Polyakov monopole has the same long-distance magnetic field, but no physical singularity at the origin. The non-Abelian fields and the Higgs field smooth out the core.

Dirac quantization says that electric and magnetic charges obey

$$
q_e g_m\in 2\pi\mathbb Z
$$

in units with $\hbar=1$. In the adjoint $SU(2)$ theory above, the massive $W$ bosons have charge $g$ under the unbroken $U(1)$, and the smooth monopole has

$$
g\,g_m=4\pi n.
$$

This factor of $2$ relative to the minimal Dirac unit reflects the global form of the gauge group and the allowed electric representations. If fundamental doublets are included, the minimal electric charge is smaller and the charge lattice must be stated accordingly. As usual with monopoles, the global form of the gauge group is not decorative fine print.

## Moduli and dyons

A single BPS monopole has collective coordinates. Three are its position in space:

$$
\mathbf X\in\mathbb R^3.
$$

There is also a compact internal phase associated with the unbroken $U(1)$ gauge rotation at infinity. For one monopole, the moduli space is locally

$$
\mathcal M_1\simeq\mathbb R^3\times S^1.
$$

Quantizing the $S^1$ coordinate gives electric charge. The resulting electrically and magnetically charged states are **dyons**.

For well-separated BPS monopoles, the low-energy dynamics is motion on a multi-monopole moduli space. For charge $n$ in the simplest $SU(2)$ theory, the dimension is

$$
\dim\mathcal M_n=4|n|.
$$

This is not just pretty geometry. It controls scattering, bound states, supersymmetric spectra, and duality tests.

## Monopoles in lower-dimensional and Euclidean problems

The same word “monopole” is used in a few related but distinct ways.

In $3+1$ Lorentzian dimensions, the ’t Hooft–Polyakov monopole is a particlelike soliton. In three Euclidean dimensions, a monopole configuration can be a finite-action instanton event. In compact $U(1)$ gauge theory in $2+1$ dimensions, monopole-instantons are central to Polyakov's confinement mechanism.

In a CFT or strongly coupled gauge theory, a **monopole operator** can mean a local operator defined by imposing magnetic flux through a small sphere surrounding the insertion. That is conceptually related to the boundary-condition logic here, but it belongs to the language of operator insertions and radial quantization, not classical finite-energy solitons alone.

## Common pitfalls

**Do not confuse global monopoles with finite-energy gauge monopoles.** Both use the same $S^2\to S^2$ topology, but the global monopole has linearly divergent energy in infinite volume. The gauge field is what makes the ’t Hooft–Polyakov monopole finite energy.

**Do not identify the monopole core with a singularity.** The Dirac monopole is singular as a classical electromagnetic field configuration. The ’t Hooft–Polyakov monopole is smooth; the core is where the non-Abelian and Higgs fields are essential.

**Do not ignore the global form of the gauge group.** Magnetic charge quantization depends on which electric representations exist and on whether the gauge group is $SU(2)$, $SO(3)$, or a quotient. The local Lie algebra is not the whole story.

**Do not treat $\pi_2(G/H)$ as the full quantum classification in every theory.** It classifies classical finite-energy sectors under specified boundary conditions. Quantum effects, matter content, screening, line operators, and global symmetries can refine or change the physically meaningful charge lattice.

**Do not assume BPS formulas away from the BPS limit.** The exact mass $4\pi v/g$ holds when the Bogomolnyi equations apply. Away from that limit, the monopole still exists but its mass receives model-dependent classical corrections.

## Relations to other pages

Monopoles complete the first codimension ladder in this chapter:

$$
\text{kinks/domain walls: }S^0,
\qquad
\text{vortices: }S^1,
\qquad
\text{monopoles: }S^2.
$$

They rely on [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/) and extend the gauge-screening logic introduced in [Vortices](/nonperturbative-qft/solitons-defects-extended-configurations/vortices/). Their BPS limit connects directly to [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/) and [Moduli of Saddles](/nonperturbative-qft/semiclassical-methods/moduli-of-saddles/).

They also foreshadow several later themes. Monopole-instantons will reappear in the instanton and confinement chapters. Magnetic disorder operators connect to ['t Hooft Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/thooft-loop-diagnostics/). Magnetic charge lattices and line operators connect to generalized global symmetries and the global form of gauge groups.

## Research status

The classical ’t Hooft–Polyakov monopole, its BPS limit, its magnetic charge, and its moduli-space dynamics are established.

The role of monopoles in strongly coupled gauge dynamics is broader and more subtle. Monopole condensation is a central image in dual-superconductor approaches to confinement. Monopole-instantons provide controlled confinement mechanisms in several lower-dimensional or compactified theories. Monopole operators are indispensable in many three-dimensional CFTs and dualities.

For four-dimensional pure Yang–Mills theory on $\mathbb R^4$, however, monopoles do not by themselves provide a complete elementary derivation of confinement. They are part of a powerful nonperturbative vocabulary whose precise implementation depends on the theory, compactification, matter content, and choice of line operators.

## Exercises

### Exercise 1: Degree of the hedgehog

Let

$$
\hat\phi:S^2\to S^2,
\qquad
\hat\phi(\theta,\varphi)=
(\sin\theta\cos\varphi,\sin\theta\sin\varphi,\cos\theta).
$$

Show that its degree is $+1$ using

$$
n
=
\frac{1}{4\pi}\int d\theta\,d\varphi\,
\hat\phi\cdot(\partial_\theta\hat\phi\times\partial_\varphi\hat\phi).
$$

<details><summary><strong>Solution</strong></summary>

For the identity map on the unit sphere,

$$
\partial_\theta\hat\phi\times\partial_\varphi\hat\phi
=
\sin\theta\,\hat\phi.
$$

Therefore

$$
\hat\phi\cdot(\partial_\theta\hat\phi\times\partial_\varphi\hat\phi)
=
\sin\theta.
$$

The degree is

$$
n
=
\frac{1}{4\pi}\int_0^\pi d\theta\int_0^{2\pi}d\varphi\,\sin\theta
=
\frac{1}{4\pi}(2)(2\pi)
=1.
$$

</details>

### Exercise 2: Linear divergence of the global monopole

For the global hedgehog $\phi^a=v\hat x^a$ outside a core, use

$$
\partial_i\hat x^a\partial_i\hat x^a=\frac{2}{r^2}
$$

to show that the energy diverges linearly with the radius $R$.

<details><summary><strong>Solution</strong></summary>

The gradient energy density is

$$
\mathcal E
=
\frac12\partial_i\phi^a\partial_i\phi^a
=
\frac12v^2\partial_i\hat x^a\partial_i\hat x^a
=
\frac{v^2}{r^2}.
$$

Thus

$$
E(R)
\simeq
\int_0^R4\pi r^2dr\,\frac{v^2}{r^2}
=
4\pi v^2R.
$$

The core changes only the finite additive part, not the linear infrared divergence.

</details>

### Exercise 3: The Bogomolnyi bound

In the BPS limit, show that

$$
E\ge\frac{4\pi v}{g}|n|.
$$

<details><summary><strong>Solution</strong></summary>

Start from

$$
E
=
\int d^3x
\left[
\frac12 B_i^aB_i^a
+
\frac12(D_i\phi)^a(D_i\phi)^a
\right].
$$

Complete the square:

$$
E
=
\frac12\int d^3x\,(B_i^a\mp D_i\phi^a)^2
\pm\int d^3x\,B_i^aD_i\phi^a.
$$

The square is nonnegative. The second term is topological:

$$
\int d^3x\,B_i^aD_i\phi^a
=
\int_{S^2_\infty}dS_i\,B_i^a\phi^a
=
\frac{4\pi v n}{g}.
$$

Choosing the sign so that the surface term is positive gives

$$
E\ge\frac{4\pi v}{g}|n|.
$$

The bound is saturated when

$$
B_i^a=\pm D_i\phi^a.
$$

</details>

### Exercise 4: Why a monopole is codimension three

A straight vortex in $3+1$ dimensions is extended along one spatial direction and is surrounded by a circle. A monopole is localized in all three spatial directions and is surrounded by a sphere. Explain this in terms of codimension.

<details><summary><strong>Solution</strong></summary>

In $d=3$ spatial dimensions, a defect with spatial dimension $p$ has codimension

$$
c=d-p.
$$

The boundary surrounding the defect is

$$
S^{c-1}.
$$

A straight vortex has $p=1$, so $c=2$ and the surrounding boundary is $S^1$. A monopole has $p=0$, so $c=3$ and the surrounding boundary is $S^2$. This is why vortices use $\pi_1$ while monopoles use $\pi_2$.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, ch. 92, for solitons, Nielsen–Olesen strings, and monopoles in a standard QFT course.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, ch. 4, for monopoles and Skyrmions, and ch. 9 for confinement-related applications.
- M. Nakahara, *Geometry, Topology and Physics*, chs. 1 and 4, for monopoles, homotopy groups, and defect classification.
- N. Manton and P. Sutcliffe, *Topological Solitons*, for monopole moduli spaces and soliton dynamics.
- E. Weinberg, *Classical Solutions in Quantum Field Theory*, for a modern treatment of classical solitons, monopoles, vortices, and instantons.

## Version history

- **2026-06-26:** Initial polished page.
