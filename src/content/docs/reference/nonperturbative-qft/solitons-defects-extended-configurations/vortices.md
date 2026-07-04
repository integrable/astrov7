---
title: "Vortices"
description: "Explains vortices as codimension-two winding defects, comparing global vortices with gauge vortices and deriving flux quantization in the Abelian Higgs model."
sidebar:
  label: "Vortices"
  order: 4
level: Graduate
status: "Polished draft"
source: "Rajaraman; Manton and Sutcliffe; Shifman, ch. 3; Srednicki, ch. 92; Nakahara, ch. 4."
topics:
  - vortices
  - strings
  - flux tubes
  - Abelian Higgs model
  - Nielsen–Olesen vortex
  - winding number
  - flux quantization
canonicalTopics:
  - nonperturbative-qft
  - solitons
  - vortices
  - topological-defects
researchStatus:
  established:
    - "Global vortices and Abelian Higgs vortices are standard codimension-two defects classified by winding at infinity; gauge vortices carry quantized magnetic flux and finite tension."
  active:
    - "Non-Abelian vortices, semilocal strings, vortex worldsheet theories, and the role of vortex condensation in confinement remain active bridges between semiclassics, supersymmetry, and strongly coupled gauge theory."
---

## Summary

A **vortex** is a codimension-two defect whose fields wind as one goes around the defect. In two spatial dimensions it is particlelike; in three spatial dimensions it is a stringlike object. The transverse boundary is a circle,

$$
S^1_\infty,
$$

so the basic topological datum is a map from a large circle around the vortex into the vacuum data of the theory.

For a complex scalar with spontaneously broken global $U(1)$ symmetry,

$$
\phi(r,\theta)\to v e^{i n\theta}
\qquad (r\to\infty),
$$

and the winding number is

$$
n
=
\frac{1}{2\pi}\oint_{S^1_\infty} d\theta\,\partial_\theta \arg\phi
\in\mathbb Z.
$$

The same winding becomes a finite-tension **gauge vortex** in the Abelian Higgs model. The gauge field cancels the long-distance phase gradient and leaves quantized magnetic flux,

$$
\Phi_B
=
\int d^2x\,B
=
\oint_{S^1_\infty} A
=
\frac{2\pi n}{e}.
$$

<figure class="doc-figure" style="--figure-width: 56rem;">

![A comparison of a global vortex with logarithmically divergent tension and a gauge vortex with quantized magnetic flux.](/figures/nonperturbative-qft/vortex-winding-flux.svg)

<figcaption>

A global vortex has winding at infinity and an unscreened Goldstone gradient, giving logarithmically divergent tension in infinite volume. A gauge vortex has the same phase winding, but the gauge field cancels the asymptotic covariant gradient. The remaining gauge-invariant datum is quantized flux $\Phi_B=2\pi n/e$.

</figcaption>
</figure>

The physical lesson is sharp: topology says winding cannot be removed without changing the boundary data or passing through the core where $\phi=0$; dynamics says whether the energy is finite, logarithmically divergent, or unstable to splitting.

## Prerequisites

You should know [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/), [Kinks](/nonperturbative-qft/solitons-defects-extended-configurations/kinks/), [Domain Walls](/nonperturbative-qft/solitons-defects-extended-configurations/domain-walls/), and [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/).

It also helps to know that $\pi_1(S^1)=\mathbb Z$: loops into a circle are classified by an integer winding number. We will use this fact explicitly rather than assuming more topology.

## Core idea

A vortex is what happens when the field cannot choose a single vacuum phase consistently around a loop.

Take a broken $U(1)$ scalar with vacuum manifold

$$
\mathcal M_{\rm vac}\simeq S^1.
$$

In the plane transverse to a putative vortex, remove the core and surround it by a large circle. Finite energy density far from the core wants $|\phi|\to v$, so on the circle we may write

$$
\phi_\infty(\theta)=v e^{i\alpha(\theta)}.
$$

Single-valuedness of $\phi$ requires

$$
\alpha(2\pi)-\alpha(0)=2\pi n,
\qquad n\in\mathbb Z.
$$

If $n\ne0$, the phase winds. The winding cannot be removed by a smooth deformation that keeps $|\phi|=v$ on the boundary. Somewhere inside the loop the field must leave the vacuum manifold, usually by passing through $\phi=0$. That region is the vortex core.

This is the codimension-two analogue of a kink. A kink has two ends of space and interpolates between two vacua. A vortex has a circle at transverse infinity and winds around a vacuum circle.

## Setup and conventions

Use polar coordinates in the transverse plane,

$$
x^1=r\cos\theta,
\qquad
x^2=r\sin\theta,
$$

and let the vortex, when embedded in $3+1$ dimensions, extend along the $z$ direction. The quantity analogous to the kink mass is then the **tension** $T$, the energy per unit length along the string.

For a complex scalar with global $U(1)$ symmetry, take

$$
\mathcal L
=
\partial_\mu\phi^*\partial^\mu\phi
-
V(|\phi|),
\qquad
V(|\phi|)=\frac{\lambda}{2}\left(|\phi|^2-v^2\right)^2.
$$

The vacuum manifold is

$$
|\phi|=v,
\qquad
\mathcal M_{\rm vac}\simeq U(1).
$$

For the Abelian Higgs model, take

$$
\mathcal L
=
-\frac14 F_{\mu\nu}F^{\mu\nu}
+
(D_\mu\phi)^*D^\mu\phi
-
\frac{\lambda}{2}\left(|\phi|^2-v^2\right)^2,
$$

with

$$
D_\mu=\partial_\mu-i e A_\mu,
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

For static configurations independent of $z$,

$$
T
=
\int d^2x
\left[
\frac12 B^2+|D_i\phi|^2+\frac{\lambda}{2}\left(|\phi|^2-v^2\right)^2
\right],
$$

where

$$
B=F_{12}.
$$

For a global vortex, set $A_i=0$ and drop the magnetic term.

## Global vortices

The simplest winding ansatz is

$$
\phi(r,\theta)=v f(r)e^{i n\theta},
\qquad n\in\mathbb Z,
$$

with boundary conditions

$$
f(0)=0,
\qquad
f(\infty)=1.
$$

The condition $f(0)=0$ makes the field single-valued and nonsingular at the origin. If $f(0)$ were nonzero, $e^{in\theta}$ would be ill-defined at $r=0$ for $n\ne0$.

For a global vortex, the tension is

$$
T_{\rm global}
=
2\pi\int_0^R r\,dr
\left[
 v^2(f')^2+
\frac{n^2v^2 f^2}{r^2}
+
\frac{\lambda v^4}{2}(f^2-1)^2
\right],
$$

where $R$ is an infrared cutoff. At large $r$, $f(r)\to1$, so the angular gradient term behaves as

$$
\mathcal E_{\rm angular}
\sim
\frac{n^2v^2}{r^2}.
$$

Therefore

$$
T_{\rm global}(R)
\sim
2\pi n^2v^2\int_\xi^R \frac{dr}{r}
=
2\pi n^2v^2\log\frac{R}{\xi},
$$

where $\xi$ is a core-size cutoff of order the inverse radial-mode mass. Thus a global vortex has logarithmically divergent tension in infinite volume.

This divergence is not a failure of topology. It is a dynamical fact about the massless Goldstone field. The phase gradient cannot be screened, so the vortex has a long-range tail.

:::note[Finite energy versus finite-size physics]
A global vortex is not a finite-tension string in infinite flat space. It can still be physically meaningful in finite volume, in condensed-matter systems, in cosmology with an infrared scale, or as part of a vortex–antivortex configuration whose far-field gradients cancel.
:::

The interaction between well-separated global vortices follows from the same Goldstone tail. In two spatial dimensions, vortices behave roughly like logarithmically interacting charges. This is the seed of the Berezinskii–Kosterlitz–Thouless story in statistical systems, although that full finite-temperature phase transition belongs elsewhere.

## Gauge vortices

Now gauge the $U(1)$. The finite-tension condition no longer requires the ordinary gradient $\partial_i\phi$ to vanish at infinity. It requires the covariant gradient to vanish:

$$
D_i\phi\to0
\qquad (r\to\infty).
$$

For a vortex of winding $n$, use the Nielsen–Olesen ansatz

$$
\phi(r,\theta)=v f(r)e^{i n\theta},
\qquad
A=A_\theta(r)\,d\theta,
\qquad
A_\theta(r)=\frac{n}{e}a(r),
$$

with

$$
f(0)=0,
\qquad
a(0)=0,
\qquad
f(\infty)=1,
\qquad
a(\infty)=1.
$$

Here $A=A_\theta d\theta$ is written as a one-form. The magnetic field in the transverse plane is

$$
B
=
\frac{1}{r}\frac{dA_\theta}{dr}
=
\frac{n}{e r}\frac{da}{dr}.
$$

At large $r$,

$$
D_\theta\phi
=
\left(\partial_\theta-i e A_\theta\right)\phi
\to
\left(i n-i e\frac{n}{e}\right)\phi
=0.
$$

The gauge field cancels the phase gradient. The tension is now finite because the long-distance angular energy is screened.

The total magnetic flux is topological:

$$
\Phi_B
=
\int d^2x\,B
=
\oint_{S^1_\infty} A
=
\int_0^{2\pi}d\theta\,A_\theta(\infty)
=
\frac{2\pi n}{e}.
$$

This formula is often the most robust way to remember the gauge vortex. The scalar winds, the gauge field compensates the winding, and the compensation leaves quantized flux.

## Why the gauge vortex is finite

The energy density of a global vortex falls as $1/r^2$, which is too slow in two transverse dimensions:

$$
\int r\,dr\,\frac1{r^2}
\sim
\log R.
$$

The gauge vortex replaces the ordinary phase gradient by a covariant one. Away from the core,

$$
\phi\simeq v e^{in\theta},
\qquad
A\simeq \frac{n}{e}d\theta,
\qquad
D\phi\simeq0.
$$

The one-form $d\theta$ is closed away from the origin but not globally exact on the punctured plane. This is the geometric reason the flux can be nonzero even though the field strength is localized near the core.

The core has two characteristic lengths:

$$
m_A=\sqrt{2}\,e v,
\qquad
m_H=\sqrt{2\lambda}\,v
$$

for the normalization used here. The gauge field decays on the scale $m_A^{-1}$, while the radial Higgs field decays on the scale $m_H^{-1}$. Different normalizations of $V$ move factors of $\sqrt2$ around; the meaningful statement is that the gauge and Higgs masses determine the magnetic and scalar core sizes.

## The Bogomolnyi point

At the special coupling

$$
\lambda=e^2,
$$

the static tension can be rearranged into squares plus a topological term. Using

$$
|D_1\phi\pm iD_2\phi|^2
=
|D_i\phi|^2
\pm eB|\phi|^2
\pm \text{total derivative},
$$

one obtains, for suitable boundary conditions,

$$
T
=
\int d^2x
\left[
|D_1\phi\pm iD_2\phi|^2
+
\frac12\left(B\mp e(v^2-|\phi|^2)\right)^2
\right]
\pm e v^2\int d^2x\,B.
$$

Therefore

$$
T\ge 2\pi v^2|n|.
$$

The bound is saturated by the first-order vortex equations

$$
(D_1\pm iD_2)\phi=0,
\qquad
B=\pm e(v^2-|\phi|^2),
$$

with the sign chosen according to the sign of $n$.

At this point, vortices exert no static force on one another in the BPS approximation. Away from it, vortices can attract or repel depending on the ratio of scalar and gauge masses. In superconductivity language, this is the distinction between type I and type II behavior.

:::caution[Normalization alert]
The precise BPS condition is convention-dependent because authors normalize the scalar potential and covariant derivative differently. In these conventions, with $V=\lambda(|\phi|^2-v^2)^2/2$ and $D=\partial-i eA$, the BPS point is $\lambda=e^2$.
:::

## Stability and splitting

The integer $n$ labels the total winding or flux. But a vortex with $|n|>1$ is not automatically a stable elementary object. It may prefer to split into $|n|$ unit vortices, remain marginally bound, or form a bound state, depending on the dynamics.

The topology says only that total winding is conserved under smooth deformations that preserve the boundary conditions:

$$
n_{\rm total}=n_1+n_2+\cdots.
$$

It does not say that the cheapest configuration with $n=2$ is a single axially symmetric vortex. In many theories the energetically preferred configuration is two separated $n=1$ vortices.

## Vortices as strings and flux tubes

In $2+1$ dimensions, a vortex is localized in space and behaves as a particle. In $3+1$ dimensions, the same transverse profile extended along a line is a string. Its low-energy motion contains at least two translational zero modes, describing displacement of the string in the transverse directions.

The worldsheet of a straight vortex is spanned by

$$
(t,z),
$$

and slow transverse fluctuations are described by fields

$$
X^1(t,z),\qquad X^2(t,z).
$$

At long wavelengths, the leading worldsheet action is the Nambu–Goto action expanded around a straight string,

$$
S_{\rm ws}
\simeq
- T\int dt\,dz
+
\frac{T}{2}\int dt\,dz\,\partial_\alpha X^i\partial^\alpha X^i
+\cdots.
$$

More elaborate vortices can carry internal orientational moduli, fermion zero modes, or lower-dimensional gauge fields on the string. Those features are model-dependent, but the pattern is universal: a soliton with moduli gives a low-energy effective theory on its worldvolume.

## Global, gauge, and non-Abelian vortices

It is useful to separate three levels of structure.

| Type | Boundary datum | Long-distance behavior | Typical object |
|---|---|---|---|
| Global vortex | Winding in a global $U(1)$ vacuum circle | Goldstone tail; logarithmic tension in infinite volume | Superfluid vortex, axion string idealization |
| Abelian gauge vortex | Winding plus gauge holonomy | Finite tension; quantized magnetic flux | Nielsen–Olesen string, Abrikosov flux tube |
| Non-Abelian vortex | Flux plus internal orientation or color-flavor data | Finite tension in Higgs phases; worldsheet moduli | Supersymmetric and color-flavor locked flux tubes |

The Abelian Higgs vortex is the canonical page-level example because it displays the essential nonperturbative lesson without requiring a large group-theory setup. Non-Abelian vortices add important physics, but they are not conceptually needed to understand winding, flux quantization, and finite tension.

## Common pitfalls

**Do not call every rotating configuration a vortex.** In field theory, a vortex is usually a codimension-two configuration with winding or flux. Hydrodynamic rotation without a topological winding sector is a different thing.

**Do not confuse global and gauge vortices.** The global vortex has an unscreened massless tail and logarithmically divergent tension. The gauge vortex has finite tension because the gauge field cancels the asymptotic phase gradient.

**Do not say the gauge vortex is classified simply by the gauge-orbit vacuum manifold.** A local gauge symmetry is redundancy, not a physical global symmetry. The flux quantization is better understood from finite-energy boundary conditions, large gauge transformations, and the holonomy $\oint A$.

**Do not infer stability of a multi-vortex from winding alone.** Winding fixes a sector; it does not determine whether the minimum in that sector is one multiply wound vortex or many unit vortices.

**Do not forget the core.** The phase-only description fails at the origin. A smooth vortex requires the radial field to leave the vacuum manifold, typically with $|\phi|\to0$ at the center.

## Relations to other pages

Vortices sit between several themes in this volume.

They extend [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/) from $S^0$ boundary data to $S^1$ boundary data. They are the codimension-two analogues of [Domain Walls](/nonperturbative-qft/solitons-defects-extended-configurations/domain-walls/), and they prepare the codimension-three logic of [Monopoles](/nonperturbative-qft/solitons-defects-extended-configurations/monopoles/).

They also connect to [Wilson Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/wilson-loop-diagnostics/) and ['t Hooft Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/thooft-loop-diagnostics/) because magnetic flux tubes and electric confinement are naturally diagnosed by line operators. Later pages on confinement will revisit vortices through dual superconductivity and flux-tube formation.

For semiclassical calculations, vortices use [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/), [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/), and [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/).

## Research status

The Abelian Higgs vortex is established textbook physics. Its classical solutions, flux quantization, BPS limit, zero modes, and long-distance effective string description are standard.

Non-Abelian vortices are also well developed in many supersymmetric and Higgs-phase gauge theories. Their worldsheet theories can encode strong-coupling dynamics, dualities, confined monopoles, and two-dimensional sigma models. The details, however, are model-dependent.

Vortex condensation as a mechanism for confinement is a powerful organizing idea, especially in dual-superconductor pictures and in lower-dimensional models. In four-dimensional non-Abelian Yang–Mills theory, no single semiclassical vortex story by itself constitutes a complete derivation of confinement in the continuum theory. That distinction matters: vortices are a crucial language for confinement, not a magic proof button.

## Exercises

### Exercise 1: Winding number of the standard vortex

For

$$
\phi(r,\theta)=v f(r)e^{in\theta},
$$

compute

$$
N=\frac{1}{2\pi}\oint d\theta\,\partial_\theta\arg\phi.
$$

<details><summary><strong>Solution</strong></summary>

For $r$ large enough that $f(r)>0$, the phase is

$$
\arg\phi=n\theta
$$

up to a constant. Therefore

$$
N
=
\frac{1}{2\pi}\int_0^{2\pi}d\theta\,n
=n.
$$

The integer is unchanged by any smooth deformation that keeps $\phi$ nonzero on the boundary circle.

</details>

### Exercise 2: Logarithmic tension of a global vortex

Assume $f(r)\to1$ outside a core of radius $\xi$. Show that the leading infrared contribution to the global vortex tension is

$$
T(R)\sim 2\pi n^2v^2\log\frac{R}{\xi}.
$$

<details><summary><strong>Solution</strong></summary>

For $r\gg\xi$,

$$
\phi\simeq v e^{in\theta}.
$$

The angular gradient is

$$
|\nabla\phi|^2
=
\frac{1}{r^2}|\partial_\theta\phi|^2
=
\frac{n^2v^2}{r^2}.
$$

Thus the large-distance contribution is

$$
T(R)
\simeq
\int_\xi^R r\,dr\int_0^{2\pi}d\theta\,\frac{n^2v^2}{r^2}
=
2\pi n^2v^2\log\frac{R}{\xi}.
$$

</details>

### Exercise 3: Flux quantization from finite tension

In the Abelian Higgs model, suppose that at large $r$

$$
\phi\to v e^{in\theta},
\qquad
D_\theta\phi\to0.
$$

Show that

$$
\oint A=\frac{2\pi n}{e}.
$$

<details><summary><strong>Solution</strong></summary>

Using $D_\theta=\partial_\theta-i eA_\theta$ and $\phi\to v e^{in\theta}$,

$$
D_\theta\phi
\to
(i n-i eA_\theta)\phi.
$$

The condition $D_\theta\phi\to0$ gives

$$
A_\theta\to\frac{n}{e}.
$$

Therefore, treating $A=A_\theta d\theta$ as a one-form,

$$
\oint A
=
\int_0^{2\pi}d\theta\,A_\theta
=
\frac{2\pi n}{e}.
$$

By Stokes' theorem this equals the magnetic flux through the transverse plane.

</details>

### Exercise 4: The BPS tension

At the Bogomolnyi point, use the square-completed energy to show that a vortex with winding $n$ has

$$
T=2\pi v^2|n|
$$

when it satisfies the first-order equations.

<details><summary><strong>Solution</strong></summary>

At the BPS point,

$$
T
=
\int d^2x
\left[
|D_1\phi\pm iD_2\phi|^2
+
\frac12\left(B\mp e(v^2-|\phi|^2)\right)^2
\right]
\pm e v^2\int d^2x\,B.
$$

The first-order equations set the two squares to zero. Hence

$$
T
=
\left|e v^2\Phi_B\right|.
$$

Using flux quantization,

$$
\Phi_B=\frac{2\pi n}{e},
$$

we get

$$
T=2\pi v^2|n|.
$$

</details>

## References

- R. Rajaraman, *Solitons and Instantons*, for classic vortex and soliton technology.
- N. Manton and P. Sutcliffe, *Topological Solitons*, for topological classification, vortex dynamics, and moduli-space methods.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, ch. 3, for vortices, strings, non-Abelian vortices, and worldsheet dynamics.
- M. Srednicki, *Quantum Field Theory*, ch. 92, for solitons, Nielsen–Olesen strings, and monopoles in an introductory QFT sequence.
- M. Nakahara, *Geometry, Topology and Physics*, ch. 4, for the homotopy classification of line defects and vortices.

## Version history

- **2026-06-26:** Initial polished page.
