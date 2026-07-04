---
title: "Other AdS Backgrounds"
description: "A survey of important AdS/CFT examples beyond AdS5 x S5, including AdS4, AdS7, AdS3, conifold, orbifold, and wrapped-brane constructions."
sidebar:
  order: 20
---

The canonical duality

$$
\mathcal N=4\; SU(N)\; \text{SYM}_4
\quad \longleftrightarrow \quad
\text{type IIB string theory on } \mathrm{AdS}_5\times S^5
$$
is not the only AdS/CFT correspondence. It is the cleanest classroom example because it has maximal supersymmetry, a simple compact space, and a transparent D3-brane origin. But the logic of holography is much broader.

This page is a map of other AdS backgrounds. The aim is not to classify all known solutions. The aim is to teach you how to read a top-down holographic background:

$$
\text{string/M theory on } \mathrm{AdS}_{d+1}\times M
\quad \longleftrightarrow \quad
\text{a }d\text{-dimensional CFT}.
$$
The AdS factor fixes the spacetime conformal symmetry. The compact internal space $M$ encodes global symmetries, R-symmetries, Kaluza–Klein towers, flux quantization, and the microscopic brane construction.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A map of common top-down AdS backgrounds.](/figures/course/other-ads-backgrounds.svg)

<figcaption>

A non-exhaustive map of major top-down AdS/CFT families. The noncompact factor $\mathrm{AdS}_{d+1}$ fixes the boundary spacetime dimension $d$, while the internal space and flux data determine supersymmetry, global symmetries, operator spectra, and the scaling of degrees of freedom.

</figcaption>
</figure>

## How to read an AdS background

A top-down AdS solution usually has the schematic form

$$
\mathrm{AdS}_{d+1} \times M_{D-d-1},
$$
where $D=10$ for type II string theory and $D=11$ for M-theory. The dual field theory lives in $d$ spacetime dimensions.

The first pass through any background should ask the following questions.

### 1. What is the AdS factor?

The AdS factor determines the conformal group:

$$
\mathrm{Isom}(\mathrm{AdS}_{d+1})=SO(2,d),
$$
matching the global conformal group of a Lorentzian CFT$_d$.

So:

| Bulk factor | Boundary theory |
|---|---|
| $\mathrm{AdS}_3$ | CFT$_2$ |
| $\mathrm{AdS}_4$ | CFT$_3$ |
| $\mathrm{AdS}_5$ | CFT$_4$ |
| $\mathrm{AdS}_7$ | CFT$_6$ |

There is no known ordinary AdS$_6$/CFT$_5$ example with a simple weakly coupled Lagrangian as canonical as $\mathcal N=4$ SYM, but string theory does contain important AdS$_6$ solutions dual to five-dimensional SCFTs. The lesson is that the boundary CFT need not have a conventional Lagrangian description.

### 2. What is the internal space?

The compact factor $M$ is not decoration. Its isometries become global symmetries of the CFT. Its Kaluza–Klein modes become towers of CFT operators. Its cycles support wrapped branes, baryon-like operators, defects, and fluxes.

For example,

$$
S^5 \quad \Longrightarrow \quad SO(6)_R \simeq SU(4)_R
$$
in $\mathcal N=4$ SYM. Replacing $S^5$ by a different compact Einstein or Sasaki–Einstein space changes the internal symmetry and the dual field theory.

### 3. What flux supports the geometry?

AdS backgrounds are usually supported by form-field flux. Flux quantization supplies the integer data that become ranks, levels, or charges in the CFT.

For D3-branes,

$$
\int_{S^5} F_5 = N,
$$
and $N$ becomes the rank of the gauge group. For M2- and M5-brane backgrounds, flux through $S^7$ or $S^4$ determines the number of branes and the scaling of degrees of freedom.

### 4. What is the separation of scales?

A background may be a perfectly valid string or M-theory solution but not have a simple Einstein gravity regime. To use low-energy supergravity, one needs the curvature radius to be large in microscopic units and the effective Newton constant to be small.

The universal question is:

$$
\frac{L^{d-1}}{G_{d+1}} \gg 1,
\qquad
\Delta_{\rm gap}\gg1.
$$
The first condition suppresses quantum loops. The second suppresses stringy or Kaluza–Klein/string-scale corrections to the desired lower-dimensional EFT.

## A compact table of examples

| Branes / construction | Bulk background | Boundary theory | Characteristic scaling |
|---|---|---|---|
| D3-branes | type IIB on $\mathrm{AdS}_5\times S^5$ | $\mathcal N=4$ SYM$_4$ | $c_T\sim N^2$ |
| D3-branes at conifold | type IIB on $\mathrm{AdS}_5\times T^{1,1}$ | $\mathcal N=1$ quiver SCFT$_4$ | $c_T\sim N^2$ |
| M2-branes | M-theory on $\mathrm{AdS}_4\times S^7$ | CFT$_3$ on M2-branes | $F\sim N^{3/2}$ |
| ABJM | M-theory on $\mathrm{AdS}_4\times S^7/\mathbb Z_k$ or IIA on $\mathrm{AdS}_4\times \mathbb{CP}^3$ | $\mathcal N=6$ Chern–Simons matter | $F\sim N^{3/2}\sqrt{k}$ in the M-theory regime |
| M5-branes | M-theory on $\mathrm{AdS}_7\times S^4$ | 6d $(2,0)$ theory | degrees of freedom $\sim N^3$ |
| D1-D5 system | type IIB on $\mathrm{AdS}_3\times S^3\times M_4$ | 2d CFT | $c\sim N_1N_5$ |
| wrapped branes | warped $\mathrm{AdS}_{d+1}\times M$ | lower-dimensional SCFTs | depends on flux and topology |

This table is only a guide. The correct dictionary of any particular background depends on supersymmetry, fluxes, cycles, brane charges, and boundary conditions.

## AdS$_4$/CFT$_3$: M2-branes and ABJM

The near-horizon geometry of many coincident M2-branes is

$$
\mathrm{AdS}_4\times S^7.
$$
The dual theory is a three-dimensional superconformal field theory living on the M2-brane worldvolume. Unlike D3-branes, M2-branes do not lead to an ordinary Yang–Mills theory in the UV with a dimensionless coupling. The interacting fixed point is intrinsically three-dimensional and strongly coupled.

A major breakthrough was ABJM theory: a three-dimensional Chern–Simons matter theory with gauge group

$$
U(N)_k \times U(N)_{-k},
$$
where $k$ is the Chern–Simons level. Its holographic dual depends on the regime:

$$
\text{M-theory on } \mathrm{AdS}_4\times S^7/\mathbb Z_k
$$
for fixed $k$ and large $N$, while a type IIA description on

$$
\mathrm{AdS}_4\times \mathbb{CP}^3
$$
emerges in an appropriate 't Hooft limit with

$$
\lambda = \frac{N}{k}
$$
large but with $k$ also large enough to reduce the M-theory circle.

The most striking scaling is the number of degrees of freedom. Instead of $N^2$, M2-brane theories exhibit

$$
F_{S^3} \sim N^{3/2}
$$
at large $N$, matching the gravitational scaling of the AdS$_4$ background.

## AdS$_7$/CFT$_6$: M5-branes and the $(2,0)$ theory

The near-horizon geometry of $N$ coincident M5-branes is

$$
\mathrm{AdS}_7\times S^4.
$$
The dual is the six-dimensional $(2,0)$ superconformal field theory. This theory is one of the most mysterious and important examples in quantum field theory. It has no known standard Lagrangian description in six dimensions, yet it is a well-defined object in string/M-theory and is central to many constructions in lower-dimensional supersymmetric field theory.

The characteristic large-$N$ scaling is

$$
\text{degrees of freedom} \sim N^3.
$$
This scaling is not what one would expect from a simple matrix gauge theory. Holography makes the scaling visible through the seven-dimensional Newton constant:

$$
\frac{L^5}{G_7} \sim N^3.
$$
The AdS$_7$/CFT$_6$ example teaches a crucial lesson: holographic CFTs need not have elementary field variables that resemble a conventional gauge theory.

## AdS$_5$/CFT$_4$ beyond $S^5$: conifolds and Sasaki–Einstein spaces

The simplest AdS$_5$/CFT$_4$ example uses $S^5$, but type IIB string theory has many AdS$_5$ solutions of the form

$$
\mathrm{AdS}_5\times X_5,
$$
where $X_5$ is a suitable compact five-dimensional space. Supersymmetric examples often involve Sasaki–Einstein manifolds.

The classic example is the conifold:

$$
X_5 = T^{1,1}
= \frac{SU(2)\times SU(2)}{U(1)}.
$$
The dual is the Klebanov–Witten $\mathcal N=1$ superconformal quiver gauge theory with gauge group

$$
SU(N)\times SU(N),
$$
bifundamental matter fields, and a superpotential constrained by global symmetry. The internal isometry

$$
SU(2)\times SU(2)\times U(1)_R
$$
matches global symmetries of the boundary SCFT.

This example is important because it shows how reducing supersymmetry and changing the internal space produce less symmetric but still controlled AdS/CFT duals.

## Orbifolds and quiver gauge theories

Orbifolding is another way to generate new AdS backgrounds. Starting with

$$
\mathrm{AdS}_5\times S^5,
$$
one can quotient the internal sphere by a discrete group $\Gamma$:

$$
S^5 \to S^5/\Gamma.
$$
On the field-theory side, this often produces quiver gauge theories. Nodes correspond to gauge-group factors, arrows correspond to matter fields, and the amount of preserved supersymmetry depends on how $\Gamma$ acts on the internal space.

The lesson is structural:

$$
\text{geometry of } M
\quad \Longleftrightarrow \quad
\text{matter content and global symmetries of the CFT}.
$$
Quiver diagrams are often the field-theory shadow of branes probing singular geometry.

## AdS$_3$/CFT$_2$ from D1-D5

The AdS$_3$/CFT$_2$ unit emphasized pure three-dimensional gravity and Brown–Henneaux symmetry. String theory also gives top-down AdS$_3$ examples. The most famous is the D1-D5 system, whose near-horizon geometry is roughly

$$
\mathrm{AdS}_3\times S^3\times M_4,
\qquad
M_4=T^4\text{ or }K3.
$$
The dual is a two-dimensional CFT associated with the D1-D5 brane system. Its central charge scales as

$$
c \sim 6N_1N_5,
$$
up to conventions and precise charge definitions. This family is especially important for black-hole microstate counting, stringy AdS$_3$ physics, symmetric-product CFTs, and the study of tensionless-string regimes.

The D1-D5 system is a reminder that not every AdS$_3$/CFT$_2$ example is pure Einstein gravity. A full top-down model includes an internal space, fluxes, Kaluza–Klein modes, branes, and stringy sectors.

## Wrapped branes and lower supersymmetry

Many AdS backgrounds arise by wrapping branes on curved internal cycles. The field theory then appears as the infrared fixed point of a higher-dimensional brane theory compactified with a topological twist.

Schematically,

$$
\text{brane theory on } \mathbb R^{1,d-1}\times \Sigma
\quad \longrightarrow \quad
\text{CFT}_d
$$
in the infrared. The bulk dual is often a warped product rather than a direct product:

$$
ds^2
=
e^{2A(y)} ds^2_{\mathrm{AdS}_{d+1}}
+
ds^2_M(y).
$$
The warp factor and internal fluxes encode the compactification data. These examples are more complicated than $\mathrm{AdS}_5\times S^5$, but they are essential for understanding the range of top-down holography.

## Consistent truncations

A common simplification is to reduce the higher-dimensional theory on the internal space and keep only a finite set of lower-dimensional fields. A truncation is called *consistent* if every solution of the lower-dimensional equations uplifts to a solution of the full ten- or eleven-dimensional equations.

For example, many calculations in AdS$_5$/CFT$_4$ use a five-dimensional action of the form

$$
S_5
=
\frac{1}{16\pi G_5}
\int d^5x\sqrt{-g}
\left(
R+\frac{12}{L^2}+\cdots
\right).
$$
This does not mean the internal $S^5$ disappeared. It means one is focusing on a consistent subsector, usually the modes invariant under some symmetry or organized by a supergravity multiplet.

A consistent truncation is powerful, but it can also hide important physics. Kaluza–Klein modes, wrapped branes, baryon vertices, and stringy excitations may be invisible in the truncated action.

## Top-down versus bottom-up

A top-down AdS background comes from a known solution of string or M-theory. It carries a microscopic dictionary: flux integers, branes, compact cycles, global symmetries, supersymmetry, and operator spectra.

A bottom-up model begins with a lower-dimensional gravitational action chosen to model desired field-theory features. It may not be known whether the model embeds into string theory.

Both approaches are useful:

| Approach | Strength | Main risk |
|---|---|---|
| top-down | UV complete, constrained, microscopic dictionary | often technically complicated |
| bottom-up | flexible, efficient, phenomenologically targeted | may violate hidden quantum-gravity consistency conditions |

A mature holographic argument usually knows which kind of model it is using.

## A warning about internal spaces and gaps

Suppose the bulk is

$$
\mathrm{AdS}_{d+1}\times M.
$$
The Kaluza–Klein masses on $M$ are often of order

$$
m_{\rm KK} \sim \frac{1}{L_M},
$$
where $L_M$ is the size of the internal space. In many maximally supersymmetric examples, $L_M\sim L$, so the Kaluza–Klein scale is not much heavier than the AdS scale.

This means pure $(d+1)$-dimensional Einstein gravity is often not the full low-energy theory. It may be a consistent truncation, but the full tower of protected KK modes can have dimensions of order one.

The large gap needed for locality below the AdS scale usually refers to stringy and higher-spin states, not necessarily all KK modes. One must distinguish:

$$
\text{KK scale},
\qquad
\text{string scale},
\qquad
\text{Planck scale}.
$$
Conflating these scales is a common source of bad holographic reasoning.

## How backgrounds encode observables

Given an AdS background, many CFT observables can be read from geometric data.

### Central charge or stress-tensor normalization

The effective Newton constant determines the stress-tensor normalization:

$$
c_T \sim \frac{L^{d-1}}{G_{d+1}}.
$$
The lower-dimensional Newton constant comes from reducing over the internal space:

$$
\frac{1}{G_{d+1}}
\sim
\frac{\operatorname{Vol}(M)}{G_D}
$$
up to warp factors and convention-dependent constants.

### Global symmetries

Isometries of $M$ give global symmetries of the CFT. Gauge fields in AdS arise from metric components with one leg along AdS and one leg along an internal Killing direction.

### Operator dimensions

Kaluza–Klein modes on $M$ produce bulk masses. These masses determine operator dimensions through relations such as

$$
m^2L^2=\Delta(\Delta-d)
$$
for scalar operators.

### Extended operators

Wrapped branes on cycles in $M$ produce extended or heavy operators: baryon vertices, Wilson surfaces, domain walls, defects, and line operators. The topology of $M$ matters directly for the operator spectrum.

## Dictionary checkpoint

The basic translation for other AdS backgrounds is:

| Bulk datum | Boundary meaning |
|---|---|
| $\mathrm{AdS}_{d+1}$ | conformal symmetry $SO(2,d)$ of CFT$_d$ |
| internal isometry of $M$ | global or R-symmetry |
| flux integer | rank, charge, or level data |
| $L^{d-1}/G_{d+1}$ | stress-tensor normalization / degrees of freedom |
| KK modes on $M$ | towers of single-trace operators |
| cycles in $M$ | wrapped-brane operators and defects |
| singularities/orbifolds | quiver structure and reduced supersymmetry |
| warping | nontrivial compactification and RG data |

The slogan is: the AdS factor tells you the CFT dimension, but the internal space tells you which CFT.

## Common confusions

### “AdS$_5$ means the bulk is five-dimensional.”

Not in string theory. The noncompact part may be five-dimensional, but the full background is usually ten-dimensional, such as $\mathrm{AdS}_5\times S^5$. The five-dimensional description is often a truncation.

### “Changing the internal space is a small detail.”

It is a huge detail. It changes supersymmetry, global symmetries, KK spectra, wrapped-brane sectors, and the microscopic CFT.

### “A lower-dimensional CFT must be simpler.”

No. CFT$_3$ and CFT$_6$ examples can be more mysterious than $\mathcal N=4$ SYM. The 6d $(2,0)$ theory is a prime example: it is central to modern quantum field theory but has no ordinary six-dimensional Lagrangian.

### “Top-down backgrounds are only examples; bottom-up models are the real physics.”

That is too glib. Top-down examples teach consistency conditions that bottom-up models can easily miss. Bottom-up models are powerful precisely when used with awareness of those constraints.

### “All internal modes should be ignored in a low-energy AdS calculation.”

Not always. If the internal radius is comparable to the AdS radius, KK modes can have dimensions of order one. A lower-dimensional truncation may still be consistent, but it does not represent the entire operator spectrum.

## Exercises

### Exercise 1: Boundary dimension

What is the boundary dimension of a CFT dual to $\mathrm{AdS}_7\times S^4$?

<details>
<summary><strong>Solution</strong></summary>

The CFT dimension is one less than the AdS dimension. Thus $\mathrm{AdS}_7$ is dual to a six-dimensional CFT. In the canonical M-theory example, this is the 6d $(2,0)$ theory on M5-branes.

</details>

### Exercise 2: Internal symmetries

Why does the $S^5$ in $\mathrm{AdS}_5\times S^5$ lead to an $SO(6)$ global symmetry in the boundary theory?

<details>
<summary><strong>Solution</strong></summary>

The isometry group of $S^5$ is $SO(6)$. In Kaluza–Klein reduction, isometries of the internal space give gauge fields in AdS. Bulk gauge fields are dual to conserved currents in the boundary CFT, so the internal $SO(6)$ isometry becomes an $SO(6)$ global symmetry. In $\mathcal N=4$ SYM this is the R-symmetry group, often written as $SO(6)_R\simeq SU(4)_R$.

</details>

### Exercise 3: Central-charge scaling

Suppose a top-down AdS$_{d+1}$ background gives

$$
\frac{L^{d-1}}{G_{d+1}} \sim N^p.
$$
What should be the large-$N$ scaling of thermal entropy density at temperature $T$ in the planar black-brane regime?

<details>
<summary><strong>Solution</strong></summary>

For a CFT$_d$ with a classical Einstein black-brane dual,

$$
s \sim \frac{L^{d-1}}{G_{d+1}} T^{d-1}.
$$
Therefore

$$
s \sim N^p T^{d-1}.
$$
The same power $N^p$ controls the stress-tensor normalization and the leading classical gravitational action.

</details>

### Exercise 4: KK modes and operator dimensions

A scalar KK mode on an internal space has effective AdS mass $m$. What determines the dimension of the dual scalar operator?

<details>
<summary><strong>Solution</strong></summary>

For a scalar in $\mathrm{AdS}_{d+1}$, the dimension obeys

$$
m^2L^2=\Delta(\Delta-d).
$$
Thus solving the KK spectrum on the internal space gives effective AdS masses, and these masses determine the scaling dimensions of the corresponding single-trace operators.

</details>

## Further reading

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- O. Aharony, O. Bergman, D. L. Jafferis, and J. Maldacena, [$\mathcal N=6$ Superconformal Chern–Simons-Matter Theories, M2-Branes and Their Gravity Duals](https://arxiv.org/abs/0806.1218).
- I. R. Klebanov and E. Witten, [Superconformal Field Theory on Threebranes at a Calabi–Yau Singularity](https://arxiv.org/abs/hep-th/9807080).
- N. Seiberg and E. Witten, [The D1/D5 System and Singular CFT](https://arxiv.org/abs/hep-th/9903224).
- D. Gaiotto and J. Maldacena, [The Gravity Duals of $\mathcal N=2$ Superconformal Field Theories](https://arxiv.org/abs/0904.4466).
