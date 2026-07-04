---
title: "Confinement and Hard-Wall Models"
description: "How an infrared cutoff in AdS produces a mass gap, discrete spectra, area-law Wilson loops, and a toy holographic model of confinement."
sidebar:
  order: 40
---

A conformal field theory has no mass gap, no intrinsic confinement scale, and no discrete hadron spectrum on flat space. Holography can move beyond this by modifying the infrared region of the bulk. The simplest modification is brutally direct: take AdS and cut it off at a finite radial position.

This is the *hard-wall model*.

It is not a top-down string construction of QCD. It is a phenomenological laboratory. Its value is that it makes several confinement-like mechanisms visible with almost no machinery:

$$
\text{IR scale in field theory}
\quad \longleftrightarrow \quad
\text{end of space at } z=z_{\rm IR}.
$$

A finite radial box produces a discrete spectrum. A string worldsheet can rest on the wall and generate an area law. A Hawking–Page-like competition can model deconfinement. These are crude but illuminating lessons.

<figure class="doc-figure" style="--figure-width: 56rem;">

![The hard-wall model as a slice of AdS with an infrared cutoff.](/figures/course/confinement-hard-wall.svg)

<figcaption>

The hard-wall model replaces full AdS by a finite radial interval $0<z<z_{\rm IR}$. The UV boundary remains at $z=0$, while the artificial wall introduces an infrared scale $\Lambda_{\rm IR}\sim 1/z_{\rm IR}$. Bulk normal modes become discrete, and a long string worldsheet can lie near the wall, giving a linear quark–antiquark potential.

</figcaption>
</figure>

## Why this page belongs in the foundations course

A foundations course should not pretend that the hard-wall model is as fundamental as $\text{AdS}_5\times S^5$. But it should explain it carefully because the model teaches three durable ideas.

First, confinement is about infrared geometry. If the radial direction has an endpoint, a cap, or a scale at which the geometry changes, boundary observables can acquire a mass gap.

Second, a discrete hadron-like spectrum arises naturally from radial normal-mode quantization. This is the same basic mathematics as a particle in a box, but dressed in AdS geometry.

Third, bottom-up models must be interpreted honestly. The hard wall captures some qualitative features of large-$N$ confining gauge theories, but the wall itself is not a solution of Einstein's equations with sensible matter. It is a boundary condition inserted by hand.

The model is therefore both useful and dangerous. Useful, because it gives intuition. Dangerous, because it can make an arbitrary cutoff look like a derivation.

## What confinement means on the boundary

In a large-$N$ gauge theory, confinement is associated with several related but distinct diagnostics:

1. **Mass gap:** the spectrum above the vacuum has a lowest nonzero energy scale.
2. **Discrete color-singlet spectrum:** at large $N$, stable glueballs and mesons appear as narrow states.
3. **Area law for large Wilson loops:** a heavy quark–antiquark pair has potential

   $$
   V_{q\bar q}(R)\sim \sigma R
   $$

   at large separation $R$.
4. **Low-temperature entropy of order $N^0$:** confined phases have few active color degrees of freedom compared with deconfined plasmas.
5. **Deconfinement transition:** at large $N$, thermal physics may jump to an entropy of order $N^2$.

No single diagnostic is perfect in every theory. For example, theories with fundamental dynamical quarks can break strings by pair creation, softening the Wilson-loop criterion. But for large-$N$ pure-glue-like holographic models, the above list is a useful target.

## The hard-wall geometry

The model begins with Poincaré AdS$_{d+1}$:

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu\right),
\qquad
0<z<\infty.
$$

The hard wall replaces the infinite radial range by

$$
0<z<z_{\rm IR}.
$$

The UV boundary remains at $z=0$. The wall at $z=z_{\rm IR}$ introduces the infrared scale

$$
\Lambda_{\rm IR}\sim \frac{1}{z_{\rm IR}}.
$$

A more careful model may add five-dimensional gauge fields, scalars, and boundary terms at the wall. But the essential move is already visible in the metric: the bulk has become a finite radial box.

This is the main difference from a genuine smooth confining geometry. In a top-down geometry, the interior typically caps off because a spatial circle shrinks smoothly, fluxes change, or branes backreact. In the hard-wall model, the endpoint is imposed.

## The radial box gives a discrete spectrum

Consider a scalar field in the hard-wall background:

$$
S_\phi
=-\frac12\int d^{d+1}x\sqrt{-g}
\left[(\partial\phi)^2+m_5^2\phi^2\right].
$$

Use the mode expansion

$$
\phi(z,x)=f_n(z)e^{ik\cdot x},
\qquad
k^2=-m_n^2.
$$

In pure Poincaré AdS without a wall, normalizable modes form a continuum because the radial direction extends indefinitely. With a wall, boundary conditions at $z=z_{\rm IR}$ quantize the allowed values of $m_n$.

For a scalar dual to an operator of dimension $\Delta$, define

$$
\nu=\Delta-\frac d2.
$$

Normalizable solutions behave as

$$
f_n(z)\propto z^{d/2}J_\nu(m_n z)
$$

up to choices of normalization and boundary condition. A Dirichlet wall condition gives

$$
J_\nu(m_n z_{\rm IR})=0,
$$

so

$$
m_n=\frac{j_{\nu,n}}{z_{\rm IR}},
$$

where $j_{\nu,n}$ is the $n$-th zero of $J_\nu$.

The details depend on the field and IR boundary condition. The robust lesson does not: the wall turns the radial Sturm–Liouville problem into a discrete spectrum.

## Vector mesons in hard-wall AdS/QCD

A common bottom-up AdS/QCD model introduces five-dimensional gauge fields for the chiral symmetry

$$
SU(N_f)_L\times SU(N_f)_R.
$$

One writes a five-dimensional action on the AdS slice and includes a scalar $X$ dual to the quark bilinear $\bar q q$:

$$
X
\quad \longleftrightarrow \quad
\bar q q.
$$

The near-boundary behavior is schematically

$$
X(z)
\sim
m_q z+\sigma z^3
\qquad (d=4),
$$

where $m_q$ is the quark mass and $\sigma$ is related to the chiral condensate. The five-dimensional gauge fields encode vector and axial-vector currents:

$$
V_M
\quad \longleftrightarrow \quad
J^\mu_V,
\qquad
A_M
\quad \longleftrightarrow \quad
J^\mu_A.
$$

Solving their radial equations with UV and IR boundary conditions produces meson masses and decay constants. This is one reason the hard-wall model became popular: with a few parameters, it captures several qualitative features of low-energy hadron physics.

But the model is not derived from QCD. It borrows the holographic dictionary and engineers a five-dimensional effective description with QCD-like symmetries.

## Wilson loops and the area law

The Wilson-loop diagnostic is especially transparent.

A heavy external quark–antiquark pair separated by distance $R$ is described by a fundamental string worldsheet ending on the boundary at the two endpoints. In pure AdS, the string dips into the bulk and gives a Coulombic potential at strong coupling:

$$
V(R)\sim -\frac{\sqrt\lambda}{R}.
$$

In the hard-wall geometry, a long string cannot go past $z=z_{\rm IR}$. At large separation, the minimal worldsheet consists approximately of:

1. two vertical segments from the boundary down to the wall;
2. one long horizontal segment lying near $z=z_{\rm IR}$.

The long horizontal segment gives

$$
V(R)\sim \sigma_{\rm HW} R+\text{constant},
$$

with effective string tension

$$
\sigma_{\rm HW}
=
\frac{1}{2\pi\alpha'}
\sqrt{-g_{tt}g_{xx}}\bigg|_{z=z_{\rm IR}}.
$$

For the AdS metric,

$$
\sqrt{-g_{tt}g_{xx}}
=\frac{L^2}{z^2},
$$

so

$$
\sigma_{\rm HW}
=
\frac{L^2}{2\pi\alpha' z_{\rm IR}^2}.
$$

In the canonical AdS$_5$/CFT$_4$ normalization, $L^2/\alpha'=\sqrt\lambda$, giving

$$
\sigma_{\rm HW}
=\frac{\sqrt\lambda}{2\pi z_{\rm IR}^2}.
$$

In bottom-up QCD-like models, $\sqrt\lambda$ should be regarded as an effective parameter rather than the literal 't Hooft coupling of QCD.

## A warning about the hard-wall Wilson loop

The hard wall produces a linear potential because the string is forced to lie at a finite minimum warp factor. This is a useful cartoon of confinement, but it is not the same as a smooth string-theory derivation.

In a smooth confining background, the string tension usually comes from a geometry where

$$
\sqrt{-g_{tt}g_{xx}}
$$

has a positive minimum at a smooth interior endpoint. In the hard-wall model, the minimum occurs because the space has simply been cut off.

That distinction matters. The hard wall correctly teaches the geometric mechanism behind an area law, but it does not explain dynamically why the wall exists.

## Thermal physics and deconfinement

At finite temperature, the hard-wall model compares two Euclidean saddles:

1. thermal AdS with the IR wall;
2. an AdS black brane, possibly with the wall hidden behind the horizon.

The black brane metric is

$$
ds^2
=
\frac{L^2}{z^2}
\left[
 f(z)d\tau^2+d\mathbf x^2+\frac{dz^2}{f(z)}
\right],
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d.
$$

The temperature is

$$
T=\frac{d}{4\pi z_h}.
$$

For the common $d=4$ hard-wall model, comparing the renormalized Euclidean actions gives a first-order Hawking–Page-like transition with critical temperature

$$
T_c=\frac{2^{1/4}}{\pi z_{\rm IR}}
$$

in the simplest setup.

The interpretation is large-$N$ confinement/deconfinement:

$$
\text{thermal AdS slice}
\quad \longleftrightarrow \quad
\text{confined phase},
$$

$$
\text{AdS black brane}
\quad \longleftrightarrow \quad
\text{deconfined phase}.
$$

Below $T_c$, the free energy is of order $N^0$ after subtracting the vacuum contribution. Above $T_c$, the black brane has entropy of order $N^2$.

## Hard wall versus soft wall

The hard wall imposes an abrupt cutoff. A soft-wall model instead introduces a smooth background field, often a dilaton profile such as

$$
\Phi(z)\sim \Lambda^2 z^2,
$$

which modifies the bulk equations and produces confinement-like spectra without a sharp endpoint.

A common motivation is Regge behavior. The hard wall gives masses roughly scaling as

$$
m_n\sim \frac{n}{z_{\rm IR}}
$$

at large excitation number for simple Bessel-mode spectra, whereas soft-wall models can give

$$
m_n^2\sim n.
$$

This page focuses on the hard wall because it is conceptually simpler. But serious phenomenological AdS/QCD often uses soft-wall or improved holographic QCD models to obtain more realistic spectra and thermodynamics.

## Relation to top-down confining geometries

A top-down confining dual is not usually a hard-wall slice of AdS. It is a smooth solution of string theory or supergravity. Examples include:

- geometries where a spatial circle smoothly caps off, as in Witten's model of confinement;
- cascading gauge-theory geometries such as the Klebanov–Strassler throat;
- wrapped-brane constructions with fluxes and shrinking cycles.

These models are harder to analyze but conceptually stronger. The IR scale arises dynamically from geometry and fluxes rather than from an imposed cutoff.

The hard wall is best viewed as a controlled toy model for some *consequences* of an IR endpoint, not as an explanation of the endpoint.

## Boundary conditions at the wall

Because the wall is artificial, one must specify IR boundary conditions. Common choices are:

$$
f_n(z_{\rm IR})=0
\qquad\text{Dirichlet},
$$

or

$$
\partial_z f_n(z_{\rm IR})=0
\qquad\text{Neumann},
$$

possibly modified by boundary-localized terms.

Different choices change the spectrum and correlators. This is not a minor technicality. Since the wall stands in for unknown IR dynamics, the boundary condition is part of the model.

A good hard-wall calculation should therefore state:

1. the bulk field content;
2. UV boundary conditions;
3. IR wall boundary conditions;
4. counterterms and normalization conventions;
5. which observables are robust under reasonable IR changes.

## Two-point functions in a hard-wall model

The hard wall converts branch cuts into poles. In a conformal theory on flat space, a two-point function often has a continuum structure in momentum space. In a confining large-$N$ theory, one expects a sum over narrow resonances:

$$
\Pi(q^2)
=
\sum_n \frac{F_n^2}{q^2+m_n^2}
+
\text{contact terms}.
$$

Holographically, this happens because solving the radial wave equation with an IR wall produces normal modes at discrete values of $m_n$.

A bulk-to-boundary propagator $K(q,z)$ must satisfy:

$$
K(q,z\to0)=1,
$$

and an IR condition at $z=z_{\rm IR}$. The on-shell action gives the boundary two-point function. Poles appear when the homogeneous normalizable problem has a nontrivial solution satisfying both UV normalizability and IR wall boundary conditions.

Thus the analytic structure of correlators knows about the finite radial interval.

## What the hard wall captures well

The hard-wall model captures several robust qualitative ideas:

- an IR length scale creates a mass gap;
- radial normal modes give discrete large-$N$ resonances;
- strings stopped at a finite radial position give a linear potential;
- thermal AdS versus black brane competition mimics confinement/deconfinement;
- chiral symmetry can be modeled using five-dimensional gauge fields and scalar profiles.

These are valuable lessons for students. They make the geometry/field-theory dictionary tangible.

## What the hard wall does not capture

The hard-wall model has serious limitations:

- the wall is not generated dynamically;
- the geometry is not a complete solution of a known string compactification;
- IR boundary conditions are model choices;
- high-energy behavior may be contaminated by artificial IR assumptions;
- Regge trajectories are not naturally reproduced in the simplest version;
- QCD is neither conformal in the UV nor generically strongly coupled at all scales;
- large-$N$ holographic models describe narrow resonances, whereas real QCD has finite-$N_c$ widths.

The right conclusion is not that the model is useless. The right conclusion is that it is a simple effective model, not a derivation of QCD.

## A clean derivation of the mass gap

Take a massless scalar in AdS$_5$ with the hard wall at $z=z_{\rm IR}$. Here $d=4$ and $\Delta=4$, so

$$
\nu=\Delta-\frac d2=2.
$$

The normalizable radial solutions are

$$
f_n(z)=z^2J_2(m_n z).
$$

If we impose a Dirichlet condition at the wall,

$$
f_n(z_{\rm IR})=0,
$$

then

$$
J_2(m_n z_{\rm IR})=0.
$$

Therefore

$$
m_n=\frac{j_{2,n}}{z_{\rm IR}}.
$$

The lightest mode has

$$
m_1=\frac{j_{2,1}}{z_{\rm IR}}.
$$

Since $j_{2,1}$ is order one, the gap is

$$
m_{\rm gap}\sim \frac{1}{z_{\rm IR}}.
$$

That is the whole mechanism in one line: the IR cutoff discretizes radial momenta.

## Relation to the Wilsonian picture

The hard wall can be understood as a drastic IR modification of the holographic RG flow.

In the UV, the model keeps the AdS geometry, so short-distance correlators retain approximately conformal behavior. In the IR, the wall says that the RG flow stops at a scale

$$
\Lambda_{\rm IR}\sim \frac{1}{z_{\rm IR}}.
$$

This is not a Wilsonian UV cutoff. It is an IR cutoff in the radial direction. The UV boundary is still at $z=0$, so the model still requires holographic renormalization near the boundary.

Do not confuse the two cutoffs:

$$
z=\epsilon
\quad \text{UV regulator},
$$

$$
z=z_{\rm IR}
\quad \text{IR wall}.
$$

The UV regulator is removed after adding counterterms. The IR wall remains as part of the physical model.

## Dictionary checkpoint

| Boundary feature | Hard-wall bulk feature |
|---|---|
| confinement scale $\Lambda_{\rm IR}$ | wall position $z_{\rm IR}\sim 1/\Lambda_{\rm IR}$ |
| mass gap | lowest radial normal mode |
| discrete glueball/meson spectrum | Sturm–Liouville spectrum on $0<z<z_{\rm IR}$ |
| Wilson-loop area law | string worldsheet rests near the wall |
| string tension $\sigma$ | $\frac{1}{2\pi\alpha'}\sqrt{-g_{tt}g_{xx}}\big|_{z_{\rm IR}}$ |
| confined phase | thermal AdS with wall |
| deconfined phase | AdS black brane |
| phenomenological uncertainty | IR boundary condition at the wall |

## Common confusions

### “The hard wall is a gravity solution.”

Not by itself. It is AdS with an imposed endpoint. Unless one specifies additional branes, matter, junction conditions, or a top-down completion, the wall is a modeling assumption rather than a derived solution.

### “A discrete spectrum automatically means confinement.”

A discrete spectrum is one confinement-like feature, but confinement also involves Wilson-loop behavior, thermodynamics, center symmetry in pure gauge theory, and color-singlet physics. The hard wall gives a useful package of these features, but each diagnostic has its own assumptions.

### “The IR wall is the UV cutoff.”

No. The UV cutoff is near $z=0$ and is removed by holographic renormalization. The IR wall is at finite $z=z_{\rm IR}$ and remains as a physical scale in the model.

### “Hard-wall AdS/QCD is QCD.”

No. It is a five-dimensional phenomenological model motivated by AdS/CFT. It can fit or organize some hadronic data, but it is not known to be exactly dual to QCD.

### “The wall position is determined by first principles.”

In the hard-wall model, $z_{\rm IR}$ is a parameter. It is usually fixed by matching one observed scale, such as a vector-meson mass or a confinement scale.

## Exercises

### Exercise 1: Discrete scalar spectrum

For a scalar in hard-wall AdS, suppose the normalizable radial modes are

$$
f_n(z)=z^{d/2}J_\nu(m_n z).
$$

Impose Dirichlet boundary conditions at $z=z_{\rm IR}$. Show that the spectrum is discrete.

<details>
<summary><strong>Solution</strong></summary>

The Dirichlet condition is

$$
f_n(z_{\rm IR})=0.
$$

Since $z_{\rm IR}^{d/2}\neq0$, this requires

$$
J_\nu(m_n z_{\rm IR})=0.
$$

Let $j_{\nu,n}$ be the $n$-th zero of $J_\nu$. Then

$$
m_n z_{\rm IR}=j_{\nu,n},
$$

so

$$
m_n=\frac{j_{\nu,n}}{z_{\rm IR}}.
$$

The zeros are discrete, so the spectrum is discrete.

</details>

### Exercise 2: Hard-wall string tension

Using

$$
ds^2=\frac{L^2}{z^2}\left(-dt^2+d\mathbf x^2+dz^2\right),
$$

compute

$$
\sigma_{\rm HW}=\frac{1}{2\pi\alpha'}\sqrt{-g_{tt}g_{xx}}\bigg|_{z=z_{\rm IR}}.
$$

<details>
<summary><strong>Solution</strong></summary>

The metric components are

$$
g_{tt}=-\frac{L^2}{z^2},
\qquad
g_{xx}=\frac{L^2}{z^2}.
$$

Therefore

$$
\sqrt{-g_{tt}g_{xx}}
=
\sqrt{\frac{L^4}{z^4}}
=
\frac{L^2}{z^2}.
$$

At the wall,

$$
\sigma_{\rm HW}
=
\frac{1}{2\pi\alpha'}\frac{L^2}{z_{\rm IR}^2}.
$$

If $L^2/\alpha'=\sqrt\lambda$, this becomes

$$
\sigma_{\rm HW}
=
\frac{\sqrt\lambda}{2\pi z_{\rm IR}^2}.
$$

</details>

### Exercise 3: Dimensional estimate of the gap

Assume that $z_{\rm IR}$ is the only IR length scale in a hard-wall model. What is the expected scaling of the lightest mass?

<details>
<summary><strong>Solution</strong></summary>

A mass has dimension inverse length. Since the only available IR length is $z_{\rm IR}$, the lightest mass must scale as

$$
m_{\rm gap}\sim \frac{1}{z_{\rm IR}}.
$$

The exact coefficient depends on the field, the bulk mass, and the IR boundary condition. In Bessel-function examples, it is a zero of a Bessel function.

</details>

### Exercise 4: Why low-temperature entropy is order $N^0$

Explain why thermal AdS with a hard wall represents a confined phase with entropy of order $N^0$, while the black-brane phase has entropy of order $N^2$.

<details>
<summary><strong>Solution</strong></summary>

In the classical gravity approximation, the leading on-shell action scales as

$$
\frac{L^{d-1}}{G_{d+1}}\sim N^2.
$$

A black brane has a horizon area, so its entropy is

$$
S_{\rm BH}=\frac{\mathrm{Area}}{4G_{d+1}}\sim N^2.
$$

Thermal AdS has no horizon. After subtracting the vacuum contribution, the leading thermal entropy comes from a gas of color-singlet bulk excitations, which is order $N^0$ in the large-$N$ limit. This matches the distinction between deconfined and confined phases.

</details>

## Further reading

- E. Witten, [Anti de Sitter Space, Thermal Phase Transition, and Confinement in Gauge Theories](https://arxiv.org/abs/hep-th/9803131).
- J. Polchinski and M. J. Strassler, [Hard Scattering and Gauge/String Duality](https://arxiv.org/abs/hep-th/0109174).
- J. Erlich, E. Katz, D. T. Son, and M. A. Stephanov, [QCD and a Holographic Model of Hadrons](https://arxiv.org/abs/hep-ph/0501128).
- L. Da Rold and A. Pomarol, [Chiral Symmetry Breaking from Five Dimensional Spaces](https://arxiv.org/abs/hep-ph/0501218).
- C. P. Herzog, [A Holographic Prediction of the Deconfinement Temperature](https://arxiv.org/abs/hep-th/0608151).
- A. Karch, E. Katz, D. T. Son, and M. A. Stephanov, [Linear Confinement and AdS/QCD](https://arxiv.org/abs/hep-ph/0602229).
