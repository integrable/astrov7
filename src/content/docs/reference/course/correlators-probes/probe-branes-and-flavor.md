---
title: "Probe Branes and Flavor"
description: "How holographic theories add fundamental matter, flavor symmetries, mesons, and defects using probe D-branes."
sidebar:
  order: 60
---

## Why this matters

The canonical AdS$_5$/CFT$_4$ example is built from open strings on $N_c$ coincident D3-branes. Its elementary fields transform in the adjoint representation of the color gauge group. This is perfect for a clean large-$N_c$ gauge theory, but it is not very QCD-like: QCD has quarks in the fundamental representation.

Probe branes are the standard top-down way to add fundamental matter to a holographic gauge theory. The idea is simple:

$$
\text{color branes create the geometry},
\qquad
\text{flavor branes add open-string matter}.
$$

In the large-$N_c$ limit with a small number $N_f$ of flavor branes, the flavor sector does not significantly backreact on the bulk geometry. The branes are probes moving in a fixed background.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Probe branes add flavor degrees of freedom in AdS/CFT](/figures/course/probe-branes-flavor.svg)

<figcaption>

Color D3-branes produce the $\mathrm{AdS}_5\times S^5$ background. Adding $N_f\ll N_c$ D7-branes introduces fundamental hypermultiplets from 3–7 strings. The D7-brane embedding encodes the quark mass and condensate, while D7 worldvolume fluctuations encode mesons and flavor-current correlators.

</figcaption>
</figure>

This page explains the basic probe-brane logic, with the D3/D7 system as the main example. The goal is not to build a realistic holographic QCD model yet. The goal is to understand what a flavor brane computes and what approximations are being made.

## Adjoint versus fundamental matter

The fields of $\mathcal N=4$ SYM are adjoint-valued matrices. Schematically,

$$
X^i{}_j,
\qquad
i,j=1,\ldots,N_c.
$$

The number of adjoint degrees of freedom scales like

$$
N_c^2.
$$

A fundamental field has one color index:

$$
q^i,
\qquad
\tilde q_i,
$$

so $N_f$ flavors contribute roughly

$$
N_c N_f
$$

degrees of freedom.

This scaling is the reason the probe limit exists. If

$$
N_f \ll N_c,
$$

then

$$
\frac{N_cN_f}{N_c^2}
=
\frac{N_f}{N_c}
\ll 1.
$$

The flavor sector is visible to probes, but its stress tensor is small compared with the stress tensor that created the background. In bulk language, the flavor branes can be treated as embedded surfaces in a fixed closed-string geometry.

This is the holographic version of the quenched approximation: include flavor matter as probes, but neglect flavor loops that would modify the gluonic vacuum.

## The D3/D7 example

The most important introductory example is the D3/D7 system. Start with $N_c$ D3-branes along directions

$$
0,1,2,3.
$$

They generate the near-horizon geometry

$$
\mathrm{AdS}_5\times S^5.
$$

Now add $N_f$ D7-branes along

$$
0,1,2,3,4,5,6,7.
$$

The D3-branes and D7-branes share the four gauge-theory directions $0,1,2,3$. Open strings stretching between D3 and D7 branes have one endpoint carrying color and the other endpoint carrying flavor. Their light modes become fundamental matter fields in the D3-brane gauge theory.

In the supersymmetric D3/D7 construction, this adds $N_f$ hypermultiplets to $\mathcal N=4$ SYM, reducing the supersymmetry to $\mathcal N=2$ in four-dimensional language. The matter transforms schematically as

$$
q^a_i,
\qquad
\tilde q^i_a,
$$

where $i$ is a color index and $a=1,\ldots,N_f$ is a flavor index.

The flavor symmetry is the gauge symmetry on the D7-branes, viewed from the boundary as a global symmetry:

$$
U(N_f)_{\rm D7\;gauge}
\quad
\longrightarrow
\quad
U(N_f)_{\rm flavor}.
$$

This is a standard holographic principle: bulk gauge symmetries whose gauge fields reach the boundary source global currents in the boundary theory.

## Brane separation and quark mass

If the D3-branes and D7-branes are separated in the two directions transverse to both branes, say $8,9$, then the 3–7 strings have a minimum length. A stretched string has mass

$$
m_q
=
\frac{w}{2\pi\alpha'},
$$

where $w$ is the asymptotic D3–D7 separation.

In the near-horizon geometry it is useful to split the six transverse directions of the D3-branes into

$$
r^2 = \rho^2 + w^2,
$$

where $\rho$ is radial along the four D7 directions inside the transverse $\mathbb R^6$, and $w$ denotes the two directions transverse to the D7. A simple supersymmetric embedding has constant $w$.

As $\rho\to\infty$, the D7 embedding has an expansion of the schematic form

$$
w(\rho)
=
m
+
\frac{c}{\rho^2}
+\cdots .
$$

The leading coefficient is the source, proportional to the quark mass. The subleading coefficient is related, after holographic renormalization, to a condensate such as

$$
\langle \tilde q q\rangle.
$$

As always in holography, the precise normalization depends on conventions and counterterms. The robust lesson is the source-response structure:

$$
\boxed{
\text{brane embedding}
\quad
\longleftrightarrow
\quad
\text{mass deformation and flavor condensate}.
}
$$

## The probe-brane action

The low-energy action of a D$p$-brane is the Dirac–Born–Infeld plus Wess–Zumino action:

$$
S_{\rm Dp}
=
-T_p\int d^{p+1}\xi\,
e^{-\Phi}
\sqrt{
-\det\left(
P[G+B]_{ab}
+
2\pi\alpha' F_{ab}
\right)
}
+
S_{\rm WZ}.
$$

Here:

| Symbol | Meaning |
|---|---|
| $T_p$ | D$p$-brane tension |
| $\xi^a$ | worldvolume coordinates |
| $P[G+B]$ | pullback of the bulk metric and $B$-field |
| $F_{ab}$ | worldvolume gauge-field strength |
| $\Phi$ | dilaton |
| $S_{\rm WZ}$ | couplings to Ramond–Ramond fields |

For small fluctuations, the DBI action reduces to an ordinary action for fields living on the brane: gauge fields, scalar embedding fluctuations, and fermions. These brane fields are dual to flavor-sector operators.

The D7 worldvolume gauge field $A_a$ is especially important. Its boundary value sources the flavor current:

$$
A_i^{(0)}(x)
\quad
\longleftrightarrow
\quad
J^i_{\rm flavor}(x).
$$

A nonzero boundary value of $A_t$ is a flavor chemical potential:

$$
A_t^{(0)} = \mu.
$$

This is one of the cleanest routes from top-down probe branes to finite-density holography.

## Induced AdS and mesons

For massless D7-branes in AdS$_5\times S^5$, the D7-brane wraps

$$
\mathrm{AdS}_5\times S^3
\subset
\mathrm{AdS}_5\times S^5.
$$

This is why the D7 worldvolume fields have their own AdS/CFT dictionary: fluctuations on AdS$_5$ are dual to four-dimensional flavor-sector operators.

For massive embeddings, the D7-brane caps off smoothly before reaching the deepest part of the geometry. Normal modes of brane fluctuations become mesons. In the simplest zero-temperature supersymmetric D3/D7 setup, these mesons are stable at leading large $N_c$ because the flavor sector is quenched and the background has no horizon.

Schematically,

$$
\text{D7 fluctuation normal mode}
\quad
\longleftrightarrow
\quad
\text{mesonic bound state}.
$$

A vector fluctuation of the D7 gauge field gives a vector meson tower. Scalar fluctuations of the embedding give scalar mesons. Open strings attached to the D7-brane provide the microscopic origin of these mesonic excitations.

The important distinction is:

| Object | Bulk description |
|---|---|
| external infinitely heavy quark | endpoint of a fundamental string at the boundary |
| dynamical fundamental matter | open strings on flavor branes |
| meson operator $\tilde q q$ | fluctuation of a flavor brane or open string mode |
| flavor current $J^i_{\rm flavor}$ | D-brane worldvolume gauge field |

This table prevents a common mistake: Wilson-loop strings and flavor branes are related, but they are not the same ingredient.

## Large-$N_c$ counting and the probe limit

The gravitational background created by the color sector has action of order

$$
S_{\rm closed}\sim N_c^2.
$$

The action of $N_f$ probe flavor branes scales as

$$
S_{\rm flavor}\sim N_cN_f.
$$

Therefore

$$
\frac{S_{\rm flavor}}{S_{\rm closed}}
\sim
\frac{N_f}{N_c}.
$$

The probe approximation is the limit

$$
N_c\to\infty,
\qquad
N_f\;\text{fixed},
\qquad
\lambda\;\text{large}.
$$

In this limit, the branes affect flavor observables but do not change the closed-string background at leading order.

If $N_f/N_c$ is not small, the flavor branes backreact. The bulk solution then changes. This is called unquenched flavor. It is physically important but technically much harder.

## Holographic renormalization for probe branes

Probe-brane actions also diverge near the AdS boundary. This should not surprise us: the brane fills an asymptotically AdS region, so its volume is infinite. The renormalized probe action has the same general structure as before:

$$
S_{\rm Dp,ren}
=
\lim_{\epsilon\to0}
\left(
S_{\rm Dp}^{\rho\le \rho_\epsilon}
+
S_{\rm ct}^{\rho=\rho_\epsilon}
\right).
$$

After renormalization, variations of the on-shell brane action compute flavor-sector one-point functions:

$$
\langle J^i_{\rm flavor}\rangle
=
\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta S_{\rm Dp,ren}}{\delta A_i^{(0)}},
$$

and similarly for scalar operators sourced by embedding data.

This is a useful place to recall a theme from holographic renormalization: the coefficient that looks like a vev in an asymptotic expansion is usually not the full renormalized one-point function until local counterterm contributions are included.

## Finite temperature: Minkowski and black-hole embeddings

In a black-brane background, flavor branes can behave in two qualitatively different ways.

A massive flavor brane may cap off smoothly above the horizon. This is called a Minkowski embedding. In such an embedding, meson-like normal modes can remain relatively sharp, because the brane does not enter the horizon.

Alternatively, the brane may fall through the horizon. This is called a black-hole embedding. Then brane fluctuations can dissipate into the horizon, and flavor excitations become quasinormal modes rather than stable normal modes.

This gives a geometric picture of meson melting:

$$
\text{Minkowski embedding}
\quad
\longrightarrow
\quad
\text{stable mesons},
$$

while

$$
\text{black-hole embedding}
\quad
\longrightarrow
\quad
\text{dissipative flavor excitations}.
$$

This topic belongs naturally to finite-temperature and finite-density holography, but the probe-brane language is the seed.

## Defects and interfaces

Not every probe brane adds flavor throughout the whole boundary spacetime. Some probe branes intersect the color branes along fewer dimensions. Then the dual degrees of freedom live on a defect or interface.

For example, a D3/D5 intersection can produce matter localized on a three-dimensional defect inside a four-dimensional ambient CFT. In such cases, the probe brane often contains an AdS$_m$ factor whose boundary is the defect spacetime.

The rough dictionary is

$$
\text{probe brane wrapping AdS}_m
\quad
\longleftrightarrow
\quad
\text{defect CFT in }m-1\text{ dimensions}.
$$

Defect branes are not the main topic of this page, but they use the same logic: a brane embedded in the bulk adds an open-string sector localized on the corresponding boundary submanifold.

## What flavor branes compute

Probe branes give access to many flavor-sector observables:

| Boundary observable | Probe-brane computation |
|---|---|
| quark mass | asymptotic brane separation |
| condensate | normalizable embedding coefficient |
| flavor current correlator | D-brane gauge-field fluctuations |
| meson spectrum | normal modes of brane fluctuations |
| flavor charge density | electric displacement on the brane |
| conductivity | linear response of brane gauge fields |
| baryon-like objects | wrapped branes or instantons on flavor branes |
| meson melting | change from normal modes to quasinormal modes |

This is a powerful toolbox. But it comes with the same warning as all bottom-up-looking holographic computations: know the approximations. A probe-brane result is not automatically a statement about full QCD.

## Common confusions

### “Flavor branes are the same as Wilson-loop strings.”

No. A fundamental Wilson loop is represented by a fundamental string ending on the boundary. A flavor brane introduces dynamical fundamental matter through open strings attached to the brane. Wilson-loop strings are external probes; flavor branes add a new sector of fields.

### “The D7 gauge symmetry is a gauge symmetry of the boundary theory.”

The D7 worldvolume gauge field is a bulk gauge field. Its boundary value sources a global flavor current in the boundary theory. The boundary flavor symmetry is global unless one explicitly gauges it by adding additional boundary dynamics.

### “Probe means physically negligible.”

Probe means negligible backreaction on the background at leading order in $N_f/N_c$. It does not mean flavor observables are trivial. The flavor free energy, current correlators, and meson spectra are precisely the leading probe effects.

### “Adding D7-branes gives QCD.”

It gives a controlled top-down theory with fundamental matter, often supersymmetric and with adjoint fields inherited from the parent theory. It is QCD-like in some observables, but it is not QCD. The right attitude is to use it as a laboratory for strongly coupled flavor dynamics.

### “The condensate is just the subleading coefficient.”

Only after holographic renormalization and convention choices. In supersymmetric D3/D7 examples, finite counterterms and supersymmetric schemes can matter. Always distinguish the raw expansion coefficient from the renormalized one-point function.

## Dictionary checkpoint

| Boundary statement | Bulk statement |
|---|---|
| color degrees of freedom | closed-string background from $N_c$ color branes |
| fundamental flavor matter | open strings involving flavor branes |
| $N_f\ll N_c$ | probe-brane approximation |
| flavor symmetry $U(N_f)$ | D-brane worldvolume gauge symmetry |
| flavor current $J^i_{\rm flavor}$ | D-brane gauge field $A_i$ |
| quark mass | asymptotic brane separation/embedding source |
| condensate | normalizable embedding response |
| mesons | normal modes of brane fluctuations |
| finite flavor density | electric displacement on the brane |
| meson melting | brane reaches a black-hole horizon |

The conceptual lesson is that the holographic dictionary includes more than closed-string supergravity fields. Open-string sectors in the bulk encode matter sectors that transform in fundamental or defect representations in the boundary theory.

## Exercises

### Exercise 1: Probe-limit counting

Adjoint degrees of freedom scale as $N_c^2$, while $N_f$ fundamental flavors scale as $N_cN_f$. Show that the flavor contribution is suppressed in the Veneziano-quenched limit $N_c\to\infty$ with $N_f$ fixed.

<details>
<summary><strong>Solution</strong></summary>

The ratio of flavor to adjoint degrees of freedom is

$$
\frac{N_cN_f}{N_c^2}
=
\frac{N_f}{N_c}.
$$

If $N_f$ is fixed while $N_c\to\infty$, this ratio goes to zero. The flavor sector can still have nontrivial observables of order $N_cN_f$, but it does not backreact on the leading order $N_c^2$ background. This is the field-theory origin of the probe-brane approximation.

</details>

### Exercise 2: Quark mass from string stretching

A 3–7 string has minimum length $w$ in flat space. Use the fundamental string tension

$$
T_{\rm F1}=\frac{1}{2\pi\alpha'}
$$

to find the mass of the corresponding fundamental matter field.

<details>
<summary><strong>Solution</strong></summary>

A string of length $w$ has energy equal to tension times length:

$$
m_q = T_{\rm F1} w
=
\frac{w}{2\pi\alpha'}.
$$

In the D3/D7 system this energy is interpreted as the bare quark mass. In the near-boundary brane embedding, the same information appears as the leading source coefficient.

</details>

### Exercise 3: Why is a D7 gauge field dual to a global current?

Explain why a bulk D7 worldvolume gauge field $A_i$ sources a boundary flavor current rather than a dynamical boundary photon.

<details>
<summary><strong>Solution</strong></summary>

In AdS/CFT, the boundary value of a bulk gauge field is a source for a conserved global current:

$$
A_i^{(0)}J^i.
$$

The bulk gauge redundancy enforces current conservation, but the boundary value $A_i^{(0)}$ is treated as a nondynamical source in the usual dictionary. Therefore the corresponding boundary symmetry is global. To make it a dynamical boundary gauge symmetry, one would need to add an additional boundary kinetic term and integrate over the boundary gauge field, which is not part of the standard probe-brane setup.

</details>

### Exercise 4: Normal modes versus quasinormal modes

Why do brane fluctuations on a Minkowski embedding tend to give stable meson spectra, while fluctuations on a black-hole embedding give dissipative modes?

<details>
<summary><strong>Solution</strong></summary>

For a Minkowski embedding, the brane caps off smoothly outside the horizon. Fluctuations satisfy regularity at the cap and normalizability at the boundary, producing a discrete normal-mode spectrum. These modes have real frequencies at leading large $N_c$ and correspond to stable mesons.

For a black-hole embedding, the brane intersects the horizon. Fluctuations must satisfy ingoing boundary conditions at the horizon. Energy can flow down the brane into the horizon, so the boundary poles move into the complex frequency plane. These are quasinormal modes and represent dissipative flavor excitations.

</details>

## Further reading

- A. Karch and E. Katz, [Adding Flavor to AdS/CFT](https://arxiv.org/abs/hep-th/0205236).
- M. Kruczenski, D. Mateos, R. C. Myers, and D. J. Winters, [Meson Spectroscopy in AdS/CFT with Flavour](https://arxiv.org/abs/hep-th/0304032).
- A. Karch, A. O'Bannon, and K. Skenderis, [Holographic Renormalization of Probe D-Branes in AdS/CFT](https://arxiv.org/abs/hep-th/0512125).
- J. Erdmenger, N. Evans, I. Kirsch, and E. Threlfall, [Mesons in Gauge/Gravity Duals: A Review](https://arxiv.org/abs/0711.4467).
