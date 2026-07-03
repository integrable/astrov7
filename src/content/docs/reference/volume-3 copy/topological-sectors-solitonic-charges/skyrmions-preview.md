---
title: "Skyrmions: Preview"
description: "Introduces Skyrmions as topological solitons of chiral fields, including compactified-space degree maps, baryon number, the Skyrme term, hedgehog ansatz, WZW term, and QCD interpretation."
sidebar:
  label: "Skyrmions: Preview"
  order: 7
level: Advanced
status: "Polished draft"
source: "Skyrme; Witten on large-N baryons and current algebra; Coleman on solitons and symmetry; Manton–Sutcliffe; Rajaraman; Nakahara Ch. 4; Altland–Simons Ch. 8; Tong TASI soliton notes."
topics:
  - Skyrmions
  - baryon number
  - chiral Lagrangian
  - topological solitons
  - winding number
  - nonlinear sigma models
  - Wess–Zumino–Witten term
  - large N QCD
canonicalTopics:
  - skyrmion
  - skyrme-model
  - baryon-number
  - chiral-soliton
  - topological-degree
  - wess-zumino-witten-term
researchStatus:
  established:
    - "The classical Skyrme model has finite-energy sectors labeled by the degree of the chiral field, and this degree is naturally interpreted as baryon number in the chiral effective theory of QCD."
    - "The Skyrme term stabilizes the soliton against collapse in three spatial dimensions, evading Derrick’s theorem for the pure two-derivative sigma model."
  active:
    - "Quantitative nuclear Skyrmion physics, dense Skyrmion matter, holographic Skyrmions, magnetic Skyrmions, and generalized topological solitons remain active research areas with model-dependent assumptions."
---

## Summary

A Skyrmion is a topological soliton in a nonlinear sigma model whose field takes values in a group or vacuum manifold with nontrivial third homotopy group. In the two-flavor chiral theory of QCD, the field is

$$
U(x)\in SU(2),
$$

and finite energy requires

$$
U(\mathbf x)\to \mathbf 1
\qquad
|\mathbf x|\to\infty.
$$

This compactifies physical space:

$$
\mathbb R^3\cup\{\infty\}\simeq S^3.
$$

Since

$$
SU(2)\simeq S^3,
$$

static configurations are maps

$$
U:S^3_{\rm space}\to S^3_{\rm target},
$$

classified by

$$
\pi_3(SU(2))=\mathbb Z.
$$

The integer is the Skyrmion number. In the QCD chiral Lagrangian it is interpreted as baryon number.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing compactified space S3 mapping to SU(2) approximately S3, with baryon number as degree and a hedgehog profile.](/figures/symmetry-anomalies-topology/skyrmion-degree-baryon-map.svg)

<figcaption>

A Skyrmion is a degree-$B$ map from compactified space to the chiral target. For two light flavors, $SU(2)\simeq S^3$, so the conserved topological charge is $B\in\pi_3(S^3)=\mathbb Z$.

</figcaption>
</figure>

This page is a preview because a full Skyrmion treatment belongs at the intersection of chiral effective theory, soliton quantization, nuclear physics, large-$N$ QCD, and topology. Here we develop the QFT-facing essentials: charge, stability, the Skyrme term, the hedgehog ansatz, and the Wess–Zumino–Witten bridge.

## Prerequisites

You should know [Winding Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/winding-number/), [Homotopy Classification](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/homotopy-classification/), [Nonlinear Sigma Models: Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/nonlinear-sigma-models-preview/), [Wess–Zumino Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-terms/), and [Wess–Zumino–Witten Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-witten-terms/).

It also helps to have seen [Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/) and [Examples of Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/examples-of-anomaly-matching/), because the QCD interpretation of Skyrmions is tied to chiral symmetry and anomaly matching.

## Core idea

A Skyrmion is a spatial winding configuration. It is not a vortex, because vortices are detected by circles. It is not a monopole, because monopoles are detected by spheres surrounding a point. It is a texture-like soliton in three dimensions, detected by compactifying all of space to a three-sphere.

For two light flavors, the chiral symmetry breaking pattern is

$$
SU(2)_L\times SU(2)_R\to SU(2)_V.
$$

The Goldstone field can be packaged as

$$
U(x)\in SU(2),
$$

with transformation law

$$
U\to g_L U g_R^{-1}.
$$

The finite-energy condition chooses a vacuum at spatial infinity. Once all directions at infinity are identified, a static field is a map

$$
S^3\to SU(2).
$$

The topological sectors are therefore

$$
[S^3,SU(2)]\simeq\pi_3(SU(2))\simeq\mathbb Z.
$$

The integer is the degree of the map. In the Skyrme model, that integer is called $B$.

## Baryon number as a topological current

Define

$$
L_\mu=U^{-1}\partial_\mu U.
$$

With $\epsilon^{0123}=+1$, a common convention for the topological current is

$$
B^\mu=-{1\over24\pi^2}\epsilon^{\mu\nu\rho\sigma}
\operatorname{tr}(L_\nu L_\rho L_\sigma).
$$

The conserved charge is

$$
B=\int d^3x\,B^0.
$$

For smooth finite-energy configurations,

$$
B\in\mathbb Z.
$$

This conservation is topological. It does not come from varying the action with respect to an ordinary continuous parameter. Instead, the current is identically conserved:

$$
\partial_\mu B^\mu=0,
$$

provided $U$ is smooth. In differential-form language, the charge integrates the pullback of the normalized volume form on $SU(2)\simeq S^3$.

:::note[Convention-sensitive source note]
Some authors define $R_\mu=(\partial_\mu U)U^{-1}$ instead of $L_\mu=U^{-1}\partial_\mu U$, or choose the opposite orientation on space or target. These choices can flip the sign of $B$. This page uses the minus sign above so that the standard hedgehog with profile $F(0)=\pi$ and $F(\infty)=0$ has $B=+1$.
:::

## The chiral Lagrangian and Derrick’s theorem

The leading chiral Lagrangian contains two derivatives:

$$
\mathcal L_2={f_\pi^2\over4}\operatorname{tr}(\partial_\mu U^\dagger\partial^\mu U).
$$

For static fields in three spatial dimensions, this term alone cannot stabilize a finite-size soliton. Derrick’s scaling argument says that if one rescales

$$
U(\mathbf x)\to U(\lambda\mathbf x),
$$

the two-derivative energy scales in a way that allows the configuration to shrink rather than sit at a stable size.

Skyrme’s key move was to add a four-derivative term,

$$
\mathcal L_4={1\over32e^2}\operatorname{tr}\left([U^\dagger\partial_\mu U,U^\dagger\partial_\nu U]^2\right),
$$

with the sign in the static energy chosen positive. The two-derivative and four-derivative terms scale oppositely under changes of size, allowing a stable classical soliton.

A common Skyrme-model action is therefore

$$
S=\int d^4x\left[
{f_\pi^2\over4}\operatorname{tr}(\partial_\mu U^\dagger\partial^\mu U)
+{1\over32e^2}\operatorname{tr}\left([U^\dagger\partial_\mu U,U^\dagger\partial_\nu U]^2\right)
+\cdots
\right].
$$

The ellipsis can include pion-mass terms, Wess–Zumino–Witten terms, vector mesons, higher-derivative corrections, and model-dependent terms.

## The hedgehog ansatz

The simplest $B=1$ Skyrmion in the $SU(2)$ model is described by the hedgehog ansatz

$$
U(\mathbf x)=\cos F(r)+i\,\hat x\cdot\boldsymbol\tau\,\sin F(r),
$$

where $\boldsymbol\tau$ are Pauli matrices and

$$
r=|\mathbf x|,
\qquad
\hat x={\mathbf x\over r}.
$$

Finite energy and smoothness impose

$$
F(\infty)=0,
\qquad
F(0)=\pi
$$

for the unit Skyrmion. The profile function moves from the antipodal group element at the origin to the identity at infinity. As space wraps once around its compactified $S^3$, the field wraps once around $SU(2)\simeq S^3$.

For this ansatz, the baryon number reduces to

$$
B=-{2\over\pi}\int_0^\infty dr\,\sin^2F(r)F'(r).
$$

With $F(0)=\pi$ and $F(\infty)=0$,

$$
B=1.
$$

The shape of $F(r)$ is determined dynamically by minimizing the static energy. The integer $B$ is determined topologically and cannot change under smooth finite-energy deformations.

## Why baryons appear

In low-energy QCD, pions are Goldstone bosons of chiral symmetry breaking. The chiral Lagrangian describes them by a field $U(x)$. Skyrme’s proposal is that baryons appear as topological solitons of this pion field.

The proposal becomes especially natural in the large-$N$ limit of QCD. Baryon masses scale like

$$
M_B\sim N_c,
$$

while meson interactions are weak in a way compatible with a classical soliton picture. Witten sharpened the idea: in large-$N_c$ QCD, baryons can be identified with Skyrmions of the chiral effective theory, and the Wess–Zumino–Witten term is essential for getting quantum numbers and anomalies right.

The minimal message is this:

$$
\text{Skyrmion number} = \text{baryon number}
$$

inside the chiral EFT description.

This does not mean a proton is literally a rigid little pion knot in microscopic QCD. It means that in a low-energy effective description, baryon number is represented by the topology of the chiral field.

## The Wess–Zumino–Witten term

For $N_f\ge3$, the chiral field takes values in $SU(N_f)$ and the Wess–Zumino–Witten term is built from a five-dimensional extension. Its coefficient is quantized and proportional to the number of colors:

$$
k_{\rm WZW}=N_c.
$$

This term encodes the chiral anomaly of QCD in the low-energy theory. It also affects the quantization of Skyrmion collective coordinates and helps fix baryon quantum numbers.

For $N_f=2$, the local five-form story is more degenerate because

$$
\pi_5(SU(2))=\mathbb Z_2
$$

rather than the $\mathbb Z$ structure familiar for $SU(N_f\ge3)$. Nevertheless, the two-flavor Skyrmion still carries the $\pi_3(SU(2))$ topological baryon number. The global, spin, and quantization subtleties should be handled carefully rather than swept into a slogan.

:::note[Source note]
The phrase “the WZW term makes the Skyrmion a fermion” is a useful memory hook but not a complete statement. The precise spin/statistics and representation quantization depend on $N_c$, flavor number, global structure, and collective-coordinate quantization.
:::

## Multi-Skyrmions and nuclei

A configuration with

$$
B>1
$$

is a multi-Skyrmion. In the nuclear interpretation, $B$ is the baryon number, so $B=2$ corresponds to deuteron-like topology, $B=4$ to alpha-particle-like topology, and so on.

Classical multi-Skyrmion solutions are not usually spherical. They often have rich discrete symmetries. Quantizing their rotational and isorotational collective coordinates is part of the model’s attempt to describe nuclear spectra.

This is fascinating physics, but it is beyond the job of this page. The present volume needs the structural lesson: topological sectors in a low-energy field can represent conserved quantum numbers of microscopic matter.

## Relation to instantons

Skyrmions and instantons both use $\pi_3$, but in different ways.

For Yang–Mills instantons on $\mathbb R^4$, finite action gives a pure gauge map at infinity:

$$
S^3_\infty\to G.
$$

For Skyrmions in three spatial dimensions, finite energy compactifies space itself:

$$
S^3_{\rm space}\to SU(2).
$$

The first is a Euclidean spacetime saddle. The second is a spatial soliton. Their formulas look like cousins because the topology is the same; their physical roles are different.

There is also a beautiful bridge: the Atiyah–Manton construction approximates Skyrmions by holonomies of Yang–Mills instantons along Euclidean time. That idea is optional here but worth knowing exists. The topology is not just rhyming; sometimes it is literally talking across dimensions.

## Magnetic Skyrmions and broader usage

In condensed matter physics, “Skyrmion” is also used for topological spin textures, often in two spatial dimensions. Those are usually classified by a map

$$
S^2\to S^2
$$

rather than the QCD chiral map $S^3\to SU(2)$. They are close relatives, not identical objects.

This page focuses on the three-dimensional chiral Skyrmion relevant to QFT, baryon number, WZW terms, and large-$N$ QCD. The broader family of Skyrmion-like textures belongs also to matter, statistical physics, and topological phases.

## Common pitfalls

### Thinking the Skyrmion is stable in the pure two-derivative sigma model

The winding number protects the configuration from being smoothly unwound, but it does not by itself fix a finite size. The Skyrme term or other dynamics is needed to prevent collapse in the classical three-dimensional model.

### Confusing baryon number with an ordinary Noether charge of pions

The topological current is identically conserved. It is not the Noether current of a continuous symmetry acting on $U$ in the usual way. In the QCD interpretation, it represents microscopic baryon number in the low-energy chiral theory.

### Ignoring the WZW term

The two-derivative and Skyrme terms can produce a stable classical lump, but anomaly matching and quantum numbers require the Wess–Zumino–Witten structure in the full chiral EFT story.

### Treating the model as exact QCD

The Skyrme model is an effective model. It captures robust topological and symmetry information, but quantitative predictions depend on parameters, higher-derivative terms, vector mesons, quantization choices, and the regime of validity of chiral EFT.

## Relations to nearby pages

[Winding Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/winding-number/) gives the degree formulas behind the baryon-number integral.

[Wess–Zumino–Witten Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-witten-terms/) explains the anomaly-matching term that appears in chiral Lagrangians.

[Instanton Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/instanton-number/) explains the Euclidean $\pi_3$ cousin of the Skyrmion number.

[Examples of Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/examples-of-anomaly-matching/) places the chiral Lagrangian and WZW term inside the anomaly-matching story.

## Research status

The topological classification and the existence of Skyrmion solitons in the Skyrme model are established. The interpretation of Skyrmions as baryons in large-$N_c$ QCD is a standard, powerful viewpoint.

Quantitative Skyrmion phenomenology is model-dependent. Modern research includes multi-Skyrmion nuclear structure, dense Skyrmion matter, holographic baryons, instanton-derived Skyrmions, chiral soliton lattices, magnetic Skyrmions, and generalized topological textures. The conceptual core is stable; the best effective description depends on the physical system.

## Exercises

### Exercise 1: Compactifying space

Show that the boundary condition

$$
U(\mathbf x)\to \mathbf 1
\qquad |\mathbf x|\to\infty
$$

allows static fields on $\mathbb R^3$ to be treated as maps $S^3\to SU(2)$.

<details><summary><strong>Solution</strong></summary>

The boundary condition says that all directions at spatial infinity approach the same field value $\mathbf 1\in SU(2)$. Therefore all points at infinity can be identified as a single point. The one-point compactification of $\mathbb R^3$ is $S^3$:

$$
\mathbb R^3\cup\{\infty\}\simeq S^3.
$$

Thus a finite-energy static configuration defines a continuous map

$$
U:S^3\to SU(2).
$$

Since $SU(2)\simeq S^3$, these maps have an integer degree.

</details>

### Exercise 2: Hedgehog baryon number

Using

$$
B=-{2\over\pi}\int_0^\infty dr\,\sin^2F(r)F'(r),
$$

show that $F(0)=\pi$ and $F(\infty)=0$ gives $B=1$.

<details><summary><strong>Solution</strong></summary>

Change variables from $r$ to $F$:

$$
B=-{2\over\pi}\int_{F(0)}^{F(\infty)}dF\,\sin^2F.
$$

With $F(0)=\pi$ and $F(\infty)=0$,

$$
B=-{2\over\pi}\int_\pi^0 dF\,\sin^2F
={2\over\pi}\int_0^\pi dF\,\sin^2F.
$$

Since

$$
\int_0^\pi\sin^2F\,dF={\pi\over2},
$$

we get

$$
B={2\over\pi}{\pi\over2}=1.
$$

</details>

### Exercise 3: Why the Skyrme term stabilizes size

Suppose the two-derivative static energy scales like $E_2(\lambda)=\lambda^{-1}E_2$ under $U(\mathbf x)\to U(\lambda\mathbf x)$, while the four-derivative term scales like $E_4(\lambda)=\lambda E_4$. Show that

$$
E(\lambda)=\lambda^{-1}E_2+\lambda E_4
$$

has a finite-size minimum.

<details><summary><strong>Solution</strong></summary>

Differentiate:

$$
{dE\over d\lambda}=-\lambda^{-2}E_2+E_4.
$$

Setting this to zero gives

$$
\lambda^2={E_2\over E_4}.
$$

For positive $E_2$ and $E_4$, this has a finite positive solution

$$
\lambda_*=\sqrt{E_2/E_4}.
$$

The second derivative is

$$
{d^2E\over d\lambda^2}=2\lambda^{-3}E_2>0,
$$

so the stationary point is a minimum. The two- and four-derivative terms balance to give a stable size.

</details>

### Exercise 4: Skyrmion number versus instanton number

Both Skyrmion number and Yang–Mills instanton number involve $\pi_3$. Explain the difference in physical interpretation.

<details><summary><strong>Solution</strong></summary>

For a Skyrmion, finite energy in three spatial dimensions compactifies space:

$$
\mathbb R^3\cup\{\infty\}\simeq S^3.
$$

The field is a map

$$
S^3_{\rm space}\to SU(2),
$$

and the integer degree labels a spatial soliton sector. It is interpreted as baryon number in the chiral EFT.

For a Yang–Mills instanton, finite Euclidean action in four dimensions makes the gauge field pure gauge at spacetime infinity:

$$
S^3_\infty\to G.
$$

The integer labels a Euclidean spacetime saddle and contributes to tunneling amplitudes and theta dependence. It is not the charge of a static particle-like configuration in ordinary space.

</details>

## References

- T. H. R. Skyrme, “A nonlinear field theory,” *Proceedings of the Royal Society A* **260** (1961) 127–138.
- E. Witten, “Baryons in the $1/N$ expansion,” *Nuclear Physics B* **160** (1979) 57–115.
- E. Witten, “Global aspects of current algebra,” *Nuclear Physics B* **223** (1983) 422–432.
- E. Witten, “Current algebra, baryons, and quark confinement,” *Nuclear Physics B* **223** (1983) 433–444.
- G. Adkins, C. Nappi, and E. Witten, “Static properties of nucleons in the Skyrme model,” *Nuclear Physics B* **228** (1983) 552–566.
- N. Manton and P. Sutcliffe, *Topological Solitons*. Detailed treatment of Skyrmions and multi-Skyrmions.
- R. Rajaraman, *Solitons and Instantons*. Classic semiclassical introduction.
- M. Nakahara, *Geometry, Topology and Physics*, Ch. 4. Homotopy groups and topological defects.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, Ch. 8. Topological terms, Wess–Zumino terms, and Chern–Simons terms.
- M. Atiyah and N. Manton, “Skyrmions from instantons,” *Physics Letters B* **222** (1989) 438–442.
- D. Tong, *TASI Lectures on Solitons*, arXiv:hep-th/0509216. Pedagogical discussion of soliton topology and related moduli spaces.

## Version history

- 2026-06-18: First polished draft. Added Skyrmion degree, baryon current, hedgehog ansatz, Skyrme-term stability, WZW/anomaly bridge, instanton relation, broader Skyrmion usage, exercises, and references.
