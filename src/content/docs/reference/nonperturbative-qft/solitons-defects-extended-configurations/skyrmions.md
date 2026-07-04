---
title: "Skyrmions"
description: "Skyrmions are topological solitons in nonlinear sigma models, classified by maps from compactified space into a target manifold."
sidebar:
  label: "Skyrmions"
  order: 6
level: Graduate
status: "Polished draft"
source: "Skyrme; Witten; Shifman, ch. 4; Manton and Sutcliffe; Nakahara."
topics:
  - skyrmions
  - nonlinear sigma models
  - topological charge
  - baryon number
  - chiral lagrangians
  - Derrick theorem
  - semiclassical quantization
canonicalTopics:
  - nonperturbative-qft
  - skyrmions
  - solitons
  - topological-defects
  - nonlinear-sigma-models
researchStatus:
  established:
    - "Skyrmions are textbook topological solitons in nonlinear sigma models; in the chiral model, their integer winding number is naturally identified with baryon number."
  active:
    - "Quantitative use of Skyrmions for nuclear physics, dense matter, holographic models, and magnetic materials is model-dependent and remains an active research area."
---

## Summary

A **Skyrmion** is a finite-energy soliton whose charge comes from a map from compactified space into a nonlinear sigma-model target. In the four-dimensional chiral model, the field is a unitary matrix

$$
U(t,\mathbf x)\in SU(N_f),
$$

and a static finite-energy configuration obeys

$$
U(\mathbf x)\longrightarrow U_\infty
\qquad (|\mathbf x|\to\infty).
$$

After fixing $U_\infty=1$, ordinary space compactifies to a three-sphere,

$$
\mathbb R^3\cup\{\infty\}\simeq S^3,
$$

so the field is a map

$$
U:S^3\to SU(N_f).
$$

For $N_f\geq 2$,

$$
\pi_3(SU(N_f))=\mathbb Z,
$$

and the integer winding number labels topological sectors. In the chiral effective theory of QCD, this integer is identified with baryon number.

<figure class="doc-figure" style="--figure-width: 56rem;">

![A Skyrmion as a degree map from compactified space to the SU(2) target, together with the Derrick scaling stabilization by the Skyrme term.](/figures/nonperturbative-qft/skyrmion-winding-stabilization.svg)

<figcaption>

A Skyrmion is a topological map $S^3\to SU(2)\simeq S^3$. The two-derivative sigma-model energy alone scales as $E_2\sim R$ and favors collapse. The four-derivative Skyrme term scales as $E_4\sim R^{-1}$ and can stabilize a finite size $R_\star\sim (eF_\pi)^{-1}$.

</figcaption>
</figure>

Skyrmions are different from kinks, vortices, and monopoles in an important way. They need not be singular at a core and need not be localized by boundary winding around a transverse sphere. They are often **textures**: the whole compactified spatial slice wraps the target manifold.

## Prerequisites

You should know [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/), [Kinks](/nonperturbative-qft/solitons-defects-extended-configurations/kinks/), [Vortices](/nonperturbative-qft/solitons-defects-extended-configurations/vortices/), [Monopoles](/nonperturbative-qft/solitons-defects-extended-configurations/monopoles/), and [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/).

It also helps to know that $SU(2)$ is topologically a three-sphere. The page uses homotopy groups only as classification labels; the relevant maps are written explicitly.

## Core idea

A kink is classified by what the field does at the two ends of a line. A vortex is classified by what the field does around a large circle. A monopole is classified by what the field does on a large sphere. A Skyrmion in three spatial dimensions is classified by what the field does on all of compactified space.

For a static finite-energy sigma-model field,

$$
U(\mathbf x)\to 1
\qquad (|\mathbf x|\to\infty).
$$

All points at infinity are therefore identified. Topologically, this turns $\mathbb R^3$ into $S^3$. The soliton charge asks how many times this spatial $S^3$ wraps the target $SU(2)\simeq S^3$.

This is why a Skyrmion is not a small perturbative pion cloud. A perturbative pion field is a small fluctuation near $U=1$. A Skyrmion must explore the global topology of the target. In fact, its integer charge vanishes order by order in a small pion expansion around $U=1$.

## Setup and conventions

We use the mostly-minus metric. Let

$$
L_\mu=U^\dagger\partial_\mu U,
\qquad U\in SU(N_f).
$$

The leading chiral Lagrangian is

$$
\mathcal L_2
=
\frac{F_\pi^2}{4}\operatorname{tr}\left(\partial_\mu U^\dagger\partial^\mu U\right).
$$

For static fields, this gives the energy

$$
E_2[U]
=
\frac{F_\pi^2}{4}\int d^3x\,\operatorname{tr}\left(\partial_iU^\dagger\partial_iU\right).
$$

The two-derivative theory has the right topology but the wrong scaling for stable finite-size solitons in three spatial dimensions. The usual Skyrme model adds a four-derivative term,

$$
\mathcal L_4
=
\frac{1}{32e^2}\operatorname{tr}\left([L_\mu,L_\nu][L^\mu,L^\nu]\right),
$$

with the corresponding positive static contribution conventionally written as

$$
E_4[U]
=
\frac{1}{32e^2}\int d^3x\,
\operatorname{tr}\left([L_i,L_j]^\dagger[L_i,L_j]\right).
$$

The constant $F_\pi$ has dimensions of mass, while $e$ is dimensionless. The scale of the classical soliton is set parametrically by

$$
R_\star\sim \frac{1}{eF_\pi}.
$$

Different authors move signs between $L_\mu$, the metric, and the trace convention. The safe invariant statement is that the static energy is a positive sum of two-derivative and four-derivative terms.

## Topological charge

For $U:S^3\to SU(N_f)$, the winding number can be written as the spatial integral

$$
B
=
-
\frac{1}{24\pi^2}
\int d^3x\,\epsilon^{ijk}
\operatorname{tr}\left(
U^\dagger\partial_iU\,
U^\dagger\partial_jU\,
U^\dagger\partial_kU
\right).
$$

The associated spacetime current is

$$
J_B^\mu
=
-
\frac{1}{24\pi^2}
\epsilon^{\mu\nu\alpha\beta}
\operatorname{tr}\left(
U^\dagger\partial_\nu U\,
U^\dagger\partial_\alpha U\,
U^\dagger\partial_\beta U
\right),
$$

so that

$$
B=\int d^3x\,J_B^0.
$$

The conservation law

$$
\partial_\mu J_B^\mu=0
$$

is topological. It does not rely on the Euler–Lagrange equations. It follows from the Maurer–Cartan identity for $L_\mu=U^\dagger\partial_\mu U$ and the antisymmetry of $\epsilon^{\mu\nu\alpha\beta}$.

This is not an ordinary Noether current of a continuous transformation acting on $U$ pointwise. Its charge counts the degree of a map. In the chiral theory of QCD, the striking statement is that this topological degree is the effective-field-theory avatar of baryon number.

## Derrick scaling and the Skyrme term

Topology says that sectors exist. Dynamics decides whether a smooth finite-size minimum exists in a sector.

Consider a fixed configuration $U(\mathbf x)$ and rescale it by

$$
U_R(\mathbf x)=U(\mathbf x/R).
$$

Then the volume element scales as $d^3x\sim R^3$, while each spatial derivative scales as $\partial_i\sim R^{-1}$. Therefore

$$
E_2[U_R]\sim R,
\qquad
E_4[U_R]\sim \frac{1}{R}.
$$

The two-derivative term alone decreases when $R\to0$. A Skyrmion would shrink to a singular zero-size configuration. The four-derivative term resists this collapse. The sum

$$
E(R)\sim aR+\frac{b}{R},
\qquad a,b>0,
$$

has a minimum at finite $R$.

This is the Skyrmion version of a recurring lesson: topology protects a sector from being continuously unwound, but it does not automatically provide a smooth classical soliton of finite size. The energy functional must also support one.

:::note[Derrick theorem]
Derrick’s theorem is the scaling obstruction behind the statement above. In more than one spatial dimension, a scalar theory with only ordinary two-derivative gradient energy and nonnegative potential typically cannot support stable static finite-size lumps without extra ingredients: higher-derivative terms, gauge fields, time-dependent charge, gravity, or boundary conditions.
:::

## The hedgehog ansatz

For $SU(2)$, a convenient charge-one ansatz is

$$
U(\mathbf x)
=
\cos F(r)+i\,\hat{\mathbf x}\cdot\boldsymbol\tau\,\sin F(r),
\qquad r=|\mathbf x|,
$$

where $\boldsymbol\tau$ are the Pauli matrices. The boundary conditions for a unit Skyrmion are

$$
F(0)=\pi,
\qquad
F(\infty)=0.
$$

At spatial infinity,

$$
U(\infty)=1.
$$

At the origin,

$$
U(0)=-1,
$$

and the angular direction $\hat{\mathbf x}$ disappears because $\sin F(0)=0$. This is what makes the ansatz smooth at $r=0$.

For the hedgehog, the winding number reduces to a one-dimensional boundary expression. Up to the orientation convention above,

$$
B
=
\frac{1}{\pi}\left[F(0)-F(\infty)\right]
-
\frac{1}{2\pi}\left[\sin 2F(0)-\sin 2F(\infty)\right].
$$

With $F(0)=\pi$ and $F(\infty)=0$, this gives

$$
B=1.
$$

The hedgehog ansatz is not the definition of a Skyrmion. It is a symmetric representative of the unit-charge sector.

## Baryons from Skyrmions

In large-N QCD, meson interactions are suppressed, while baryon masses grow like $N$. This is exactly the scaling pattern expected for semiclassical solitons of an effective meson theory. The Skyrme picture therefore gives a beautiful bridge:

$$
\text{baryon}
\quad\longleftrightarrow\quad
\text{topological soliton of the chiral field}.
$$

In the simplest $SU(2)$ model, collective-coordinate quantization rotates the hedgehog in flavor space:

$$
U(\mathbf x,t)=A(t)U_0(\mathbf x)A^\dagger(t),
\qquad A(t)\in SU(2).
$$

The rotational Hamiltonian has the schematic form

$$
H_{\rm rot}=\frac{\mathbf J^2}{2I_{\rm sk}},
$$

where $I_{\rm sk}$ is the Skyrmion moment of inertia. The hedgehog locks spatial and isospin rotations, so quantized states obey the characteristic relation between spin and isospin. In QCD applications, the Wess–Zumino–Witten term is essential for getting the correct quantum numbers and statistics in theories with three or more light flavors.

The interpretation is powerful but not exact. The Skyrme model is an effective low-energy model. It does not derive all baryon properties from first-principles QCD, and its numerical accuracy depends on the truncation of the chiral Lagrangian and on how parameters are fitted.

## Magnetic Skyrmions and terminology

The word “Skyrmion” is used in more than one community. In particle physics, the canonical Skyrmion is a three-dimensional soliton of the chiral field, classified by $\pi_3(SU(N_f))$. In condensed matter physics, “magnetic Skyrmion” often refers to a two-dimensional spin texture

$$
\mathbf n(x,y):\mathbb R^2\to S^2,
\qquad \mathbf n^2=1,
$$

with finite-energy boundary condition $\mathbf n(\infty)=\mathbf n_0$. Compactifying the plane gives $S^2$, so the charge is classified by

$$
\pi_2(S^2)=\mathbb Z.
$$

These are not identical field theories, but they share the same conceptual DNA: a smooth field texture is stable because a compactified space wraps a target manifold nontrivially.

## Common pitfalls

**Topology does not replace dynamics.** The integer $B$ labels sectors, but a stable smooth soliton needs an energy functional with a finite-size minimum. The two-derivative sigma model in three spatial dimensions fails this test by Derrick scaling.

**A Skyrmion is not just a monopole with another name.** A monopole is usually classified by a sphere at spatial infinity surrounding a localized core, often in a gauge-Higgs system. A Skyrmion is typically a texture in which compactified space itself maps nontrivially into the target.

**The baryon current is not an ordinary pion Noether current.** It is a topological current built from $U^{-1}dU$. It vanishes in ordinary perturbation theory around $U=1$ with small pion fields and nontrivial boundary conditions absent.

**The Skyrme model is not QCD.** It is an effective chiral theory. Its baryon interpretation is especially natural at large $N$, but quantitative predictions require care.

**The Wess–Zumino–Witten term is not optional in three-flavor QCD.** It affects allowed processes, anomalies, and Skyrmion quantum numbers. Omitting it changes the physics.

## Relations to other pages

Skyrmions use the same finite-energy logic as [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/), but with compactified space rather than a transverse sphere as the main actor.

They connect backward to [Monopoles](/nonperturbative-qft/solitons-defects-extended-configurations/monopoles/) through homotopy classification and forward to Q-Balls through the contrast between topological and nontopological stabilization. They also connect to [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/) because quantizing spin, isospin, translations, and rotations is part of the physical Skyrmion story.

Later pages on large-N methods, chiral symmetry breaking, and strongly coupled gauge theories will revisit the baryon interpretation.

## Research status

**Established.** The topological classification of Skyrmions in sigma models, the baryon-number current, Derrick scaling, and semiclassical collective-coordinate quantization are standard material.

**Model-dependent.** The use of the minimal Skyrme model as a quantitative model of real baryons and nuclei is approximate. Higher-derivative terms, vector mesons, pion masses, Wess–Zumino–Witten terms, and holographic completions can materially change predictions.

**Active.** Skyrmions remain active in nuclear effective theory, dense matter, holographic QCD, chiral magnets, spintronics, and topological textures in quantum materials.

## Exercises

### Exercise 1: Derrick scaling

Let $U_R(\mathbf x)=U(\mathbf x/R)$ in three spatial dimensions. Show that a two-derivative energy scales as $E_2[U_R]=R E_2[U]$, while a four-derivative Skyrme energy scales as $E_4[U_R]=R^{-1}E_4[U]$.

<details>
<summary><strong>Solution</strong></summary>

For the two-derivative term,

$$
E_2[U_R]
\sim
\int d^3x\,\operatorname{tr}(\partial_iU_R^\dagger\partial_iU_R).
$$

Set $\mathbf y=\mathbf x/R$. Then $d^3x=R^3d^3y$ and $\partial_iU_R=R^{-1}\partial_{y_i}U$. Therefore

$$
E_2[U_R]\sim R^3R^{-2}E_2[U]=R E_2[U].
$$

For a four-derivative term, each derivative contributes $R^{-1}$, so

$$
E_4[U_R]\sim R^3R^{-4}E_4[U]=R^{-1}E_4[U].
$$

Thus $E_2$ favors shrinking and $E_4$ favors expansion. Their sum can have a finite-size minimum.

</details>

### Exercise 2: Hedgehog boundary conditions

For

$$
U(\mathbf x)=\cos F(r)+i\hat{\mathbf x}\cdot\boldsymbol\tau\sin F(r),
$$

explain why smoothness at the origin requires $\sin F(0)=0$, and why the unit Skyrmion usually uses $F(0)=\pi$ and $F(\infty)=0$.

<details>
<summary><strong>Solution</strong></summary>

The unit vector $\hat{\mathbf x}$ is not defined at $r=0$. Therefore the coefficient multiplying $\hat{\mathbf x}\cdot\boldsymbol\tau$ must vanish at the origin. This requires

$$
\sin F(0)=0,
$$

so $F(0)$ is an integer multiple of $\pi$. The choice $F(\infty)=0$ makes

$$
U(\infty)=1,
$$

which is the standard finite-energy boundary condition. The choice $F(0)=\pi$ gives

$$
U(0)=-1
$$

and produces a map that wraps $SU(2)\simeq S^3$ once as compactified space is swept once. With the orientation convention of this page, this is $B=1$.

</details>

### Exercise 3: Why the charge is invisible perturbatively

Explain why an ordinary small-field pion expansion around $U=1$ cannot produce a nonzero Skyrmion number if the pion fields vanish at infinity.

<details>
<summary><strong>Solution</strong></summary>

Write $U=e^{i\pi^a\tau^a/F_\pi}$ with $|\pi|$ small everywhere and $\pi(\infty)=0$. Such a configuration lies in a small coordinate patch around the identity of $SU(2)$. A small patch is contractible, so the map from compactified space into that patch can be continuously deformed to the constant map $U=1$.

The winding number is invariant under continuous deformations that preserve the boundary condition. Since the constant map has $B=0$, every globally small configuration has $B=0$. Nonzero Skyrmion number requires leaving the perturbative coordinate patch.

</details>

## References

- T. H. R. Skyrme, “A Non-Linear Field Theory,” *Proceedings of the Royal Society A* **260** (1961) 127.
- E. Witten, “Baryons in the $1/N$ Expansion,” *Nuclear Physics B* **160** (1979) 57.
- G. S. Adkins, C. R. Nappi, and E. Witten, “Static Properties of Nucleons in the Skyrme Model,” *Nuclear Physics B* **228** (1983) 552.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapter 4.
- N. Manton and P. Sutcliffe, *Topological Solitons*.
- M. Nakahara, *Geometry, Topology and Physics*, for homotopy and topological classification.

## Version history

- **2026-06-26:** Initial polished page, added with Q-Balls.
