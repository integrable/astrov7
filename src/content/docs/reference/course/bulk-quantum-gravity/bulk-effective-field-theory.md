---
title: "Bulk Effective Field Theory"
description: "How large N, a sparse spectrum, and a large gap make an approximately local effective field theory emerge in AdS."
sidebar:
  order: 10
---

The previous units taught us how to compute boundary observables from classical bulk fields. We now turn the logic around. Suppose we are handed a conformal field theory and asked whether it contains an approximately local gravitational world in one higher dimension. What CFT data would let us say, with controlled approximations, that there is a bulk effective field theory?

This question is one of the deepest lessons of AdS/CFT. The bulk is not put in by hand. In favorable large-$N$ CFTs, the bulk low-energy theory is an efficient reorganization of the CFT spectrum and correlation functions.

The slogan for this page is:

$$
\text{large }N + \text{sparse low-energy single-trace spectrum} + \text{large gap}
\quad\Longrightarrow\quad
\text{local bulk EFT in AdS}.
$$

The arrow should be read carefully. It is not a theorem for every CFT in every dimension and every regime. It is a controlled organizing principle, sharpened by crossing symmetry, large-$N$ factorization, and the success of Witten-diagram perturbation theory.

<figure class="doc-figure" style="--figure-width: 52rem;">

![CFT data reorganized into a local bulk effective field theory.](/figures/course/bulk-effective-field-theory.svg)

<figcaption>

A semiclassical bulk effective field theory is not an extra assumption glued onto the CFT. It is the low-energy reorganization of large-$N$ CFT data: light single-trace primaries become bulk fields, OPE coefficients become local couplings, and anomalous dimensions of multi-trace operators encode bulk interactions.

</figcaption>
</figure>

## Why this matters

AdS/CFT is often first learned in the classical gravity corner. But the most conceptual question is not merely how to solve Einstein's equations in AdS. It is why a CFT can ever look like a spacetime with local fields.

A local bulk effective field theory is the statement that, below a cutoff scale, the bulk dynamics can be described by a finite or controlled set of fields with local interactions:

$$
S_{\mathrm{EFT}}
=
\int d^{d+1}x\sqrt{-g}\,
\left[
\frac{1}{16\pi G_N}
\left(R-2\Lambda\right)
-
\frac12 (\nabla\phi)^2
-
\frac12 m^2\phi^2
-
\frac{g_3}{3!}\phi^3
-
\frac{g_4}{4!}\phi^4
+
\cdots
\right].
$$

The dots contain two different kinds of corrections:

1. **More fields**, corresponding to more single-trace CFT operators.
2. **More derivatives and loops**, suppressed by the bulk cutoff and by $G_N$.

A healthy bulk EFT answers several questions at once:

- Why do low-energy bulk particles have approximately local interactions?
- Why are Witten diagrams a good perturbation theory?
- Why do single-trace operators behave like elementary bulk fields?
- Why do multi-trace operators behave like multiparticle states?
- Why does classical gravity know only a small part of the full CFT?

The answer is a hierarchy of scales.

## The hierarchy of scales

A bulk EFT is useful only between two limits. It should be insensitive to very short-distance quantum-gravity/stringy physics, but it should still resolve distances much smaller than the AdS radius.

A schematic hierarchy is

$$
\ell_{\mathrm{P}}
\ll
\ell_{\mathrm{gap}}
\ll
L,
$$

where $L$ is the AdS radius, $\ell_{\mathrm P}$ is the Planck length, and $\ell_{\mathrm{gap}}$ is the length scale associated with the first heavy states not included in the low-energy EFT. Equivalently,

$$
\frac{L^{d-1}}{G_N} \gg 1,
\qquad
M_{\mathrm{gap}}L \gg 1.
$$

The first condition means gravity is weakly quantum. The second means there is a parametrically high mass gap above the light fields, so derivative corrections are suppressed.

In AdS/CFT language,

$$
\frac{L^{d-1}}{G_N}
\sim
c_T
\sim
N^2
$$

in matrix-like large-$N$ theories, up to convention-dependent constants. The bulk cutoff is measured by a CFT gap:

$$
M_{\mathrm{gap}}L
\sim
\Delta_{\mathrm{gap}}.
$$

For the canonical AdS$_5\times S^5$/CFT$_4$ example, the stringy gap scales as

$$
\Delta_{\mathrm{stringy}}
\sim
\lambda^{1/4},
$$

because massive string states have $m_s^2\sim 1/\alpha'$ and

$$
\frac{L^2}{\alpha'}=\sqrt{\lambda}.
$$

Thus the two suppressions are different:

$$
\text{bulk loops}
\sim
\frac{G_N}{L^{d-1}}
\sim
\frac{1}{N^2},
\qquad
\text{stringy/derivative corrections}
\sim
\frac{1}{\Delta_{\mathrm{gap}}^p}.
$$

Large $N$ suppresses quantum loops. A large gap suppresses short-distance nonlocality and higher-derivative corrections.

## What counts as a low-energy bulk field?

A bulk field is dual to a single-trace primary operator, or more generally a single-particle operator, in the CFT.

For a scalar primary $\mathcal O$ of dimension $\Delta$, the dual scalar has mass

$$
m^2L^2=\Delta(\Delta-d).
$$

For a conserved current $J^i$, the dual field is a bulk gauge field $A_M$. For the stress tensor $T^{ij}$, the dual field is the metric $g_{MN}$. Schematically,

$$
\begin{array}{ccl}
\text{single-trace scalar }\mathcal O &\longleftrightarrow& \text{bulk scalar }\phi,\\[2mm]
\text{current }J^i &\longleftrightarrow& \text{bulk gauge field }A_M,\\[2mm]
\text{stress tensor }T^{ij} &\longleftrightarrow& \text{bulk graviton }g_{MN}.
\end{array}
$$

The low-energy bulk EFT keeps only operators with dimensions below a chosen cutoff:

$$
\Delta \lesssim \Delta_{\mathrm{cut}}.
$$

This cutoff must be safely below the gap:

$$
1\ll \Delta_{\mathrm{cut}} \ll \Delta_{\mathrm{gap}}.
$$

The dual bulk statement is that we keep fields with masses $mL\lesssim \Delta_{\mathrm{cut}}$ and integrate out heavier fields. Integrating out heavy fields produces local higher-derivative interactions among the light fields.

## Locality from a sparse spectrum

A large-$N$ expansion alone does not guarantee an Einstein-like local bulk. A generalized free field theory has factorized correlators, but it need not have a good interacting local gravitational dual. A vector model at large $N$ can have a higher-spin dual rather than Einstein gravity. The missing ingredient is a sparse low-energy spectrum with a large gap to higher-spin and stringy states.

A useful CFT criterion is:

$$
\Delta_{\mathrm{gap}}
\equiv
\min_{\text{heavy single-trace}}
\Delta
\gg 1.
$$

The precise definition of the gap depends on the problem. For Einstein gravity in particular, one wants no light single-trace operators of spin $s>2$ beyond the stress tensor and any intentionally included matter fields. Light higher-spin particles would impose strong constraints on interactions and typically signal a stringy or higher-spin regime rather than an ordinary low-energy Einstein regime.

The logic is:

$$
\text{sparse low spectrum}
\quad\Longrightarrow\quad
\text{few light bulk fields},
$$

and

$$
\text{large gap}
\quad\Longrightarrow\quad
\text{derivative expansion in }\frac{\nabla}{M_{\mathrm{gap}}}.
$$

For example, a four-derivative correction to the Einstein action is suppressed schematically by

$$
S_{\mathrm{EFT}}
\supset
\frac{1}{16\pi G_N}
\int d^{d+1}x\sqrt{-g}\,
\frac{1}{M_{\mathrm{gap}}^2}R^2.
$$

In AdS units, its relative effect on low-curvature observables is of order

$$
\frac{1}{(M_{\mathrm{gap}}L)^2}
\sim
\frac{1}{\Delta_{\mathrm{gap}}^2}.
$$

For AdS$_5\times S^5$, $M_{\mathrm{gap}}$ is the string scale, so such corrections are controlled by powers of $1/\sqrt\lambda$ or $1/\lambda$ depending on the operator.

## How CFT data become bulk EFT data

A CFT is specified by its spectrum and OPE coefficients. A bulk EFT is specified by fields, masses, and couplings. The AdS/CFT dictionary relates these two descriptions.

### Spectrum $\to$ fields and masses

Each light single-trace primary $\mathcal O_a$ gives a bulk field $\phi_a$. Its dimension determines the mass or representation data. For scalars,

$$
m_a^2L^2=\Delta_a(\Delta_a-d).
$$

For spinning operators, $\Delta$ and spin determine the corresponding AdS representation.

### Two-point functions $\to$ kinetic normalization

The normalization of

$$
\langle \mathcal O_a(x)\mathcal O_b(0)\rangle
$$

fixes the normalization of the kinetic terms of the corresponding bulk fields. We often choose CFT operators so that two-point functions are unit-normalized. Then bulk fields are canonically normalized, and powers of $1/N$ appear in interactions.

### Three-point functions $\to$ cubic couplings

A cubic bulk coupling

$$
S_{\mathrm{int}}
\supset
\int d^{d+1}x\sqrt{g}\,g_{abc}\phi_a\phi_b\phi_c
$$

computes a CFT three-point coefficient

$$
C_{abc}.
$$

Thus, after fixing two-point normalizations,

$$
C_{abc}
\quad\longleftrightarrow\quad
\text{cubic bulk coupling}.
$$

### Four-point functions $\to$ exchange and contact interactions

Four-point functions contain more information. They know about:

- exchange of light bulk fields;
- local quartic contact interactions;
- higher-derivative corrections;
- anomalous dimensions of double-trace operators;
- crossing symmetry and causality constraints.

In a large-gap theory, low-energy four-point data can be organized by an AdS derivative expansion. Contact interactions with more derivatives contribute increasingly suppressed terms.

A schematic local quartic EFT takes the form

$$
S_{\mathrm{int}}^{(4)}
=
\int d^{d+1}x\sqrt{g}\,
\left[
\lambda_0\phi^4
+
\frac{\lambda_2}{M_{\mathrm{gap}}^2}(\nabla\phi)^2\phi^2
+
\frac{\lambda_4}{M_{\mathrm{gap}}^4}(\nabla\phi)^4
+
\cdots
\right].
$$

The CFT sees this as a structured expansion of double-trace anomalous dimensions and OPE coefficients.

## The large-$N$ expansion and bulk loops

Let $\mathcal O$ be a normalized single-trace operator, chosen so that

$$
\langle \mathcal O(x)\mathcal O(0)\rangle \sim N^0.
$$

In a matrix large-$N$ theory, connected correlators scale as

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_c
\sim
N^{2-n}.
$$

This has a direct bulk interpretation. A canonically normalized bulk action can be written schematically as

$$
S
=
\int d^{d+1}x\sqrt{-g}\,
\left[
\frac12(\nabla\phi)^2+\frac12m^2\phi^2
+
\frac{1}{N}\phi^3
+
\frac{1}{N^2}\phi^4
+
\cdots
\right],
$$

with gravitational interactions following the same pattern after expanding the metric around a background. Tree-level Witten diagrams reproduce the leading connected correlators. Bulk loops carry extra powers of

$$
\frac{G_N}{L^{d-1}}
\sim
\frac{1}{N^2}.
$$

This is why the classical bulk saddle is the leading large-$N$ approximation, while one-loop determinants and quantum corrections appear at subleading orders.

## Locality is approximate, not exact

Bulk locality is one of the miracles of the duality, but it is not exact in the same sense as microscopic CFT locality.

At leading order in $1/N$ and below the gap, bulk fields can obey local equations of motion. But several effects limit exact locality:

- **gravitational dressing:** gauge-invariant bulk observables are never perfectly local in a theory with gravity;
- **finite $N$:** the number of independent bulk degrees of freedom in a region is finite and constrained by holographic entropy;
- **stringy physics:** at distances comparable to $\ell_s$ or $1/M_{\mathrm{gap}}$, point-particle locality breaks down;
- **black holes:** high-energy states are not well described as a small number of bulk particles;
- **operator mixing:** the CFT basis of single-trace and multi-trace operators is not unique away from the strict large-$N$ limit.

Thus a better statement is:

$$
\text{bulk locality is an emergent low-energy, large-}N\text{ approximation.}
$$

This is exactly what one expects from effective field theory.

## A useful reliability ladder

It helps to distinguish several levels of bulk description.

| CFT regime | Bulk description |
|---|---|
| exact finite-$N$ CFT | full quantum gravity/string theory, generally not local EFT |
| large $N$, finite gap | weakly quantum but possibly stringy or higher-spin bulk |
| large $N$, large gap | local bulk EFT in AdS |
| large $N$, large gap, low curvatures | classical local bulk EFT |
| large $N$, large gap, only metric light | classical Einstein gravity plus controlled corrections |

The last line is the regime most often used in simple holographic calculations. But it is only the narrowest and most classical corner of the full correspondence.

## Example: the scalar EFT behind a CFT four-point function

Suppose a CFT has a light scalar single-trace primary $\mathcal O$ of dimension $\Delta$, and all other single-trace primaries except the stress tensor are heavy. The bulk EFT contains a scalar field $\phi$:

$$
S
=
\int d^{d+1}x\sqrt{g}\,
\left[
\frac12(\nabla\phi)^2+\frac12m^2\phi^2
+\frac{\lambda_4}{N^2}\phi^4
+\frac{\lambda_{4,2}}{N^2M_{\mathrm{gap}}^2}(\nabla\phi)^2\phi^2
+\cdots
\right].
$$

The two-point function fixes $m^2L^2=\Delta(\Delta-d)$. The connected four-point function begins at order $1/N^2$:

$$
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle_c
\sim
\frac{1}{N^2}.
$$

At low energies, the first term $\phi^4$ gives the leading contact contribution. The derivative term is suppressed by

$$
\frac{1}{(M_{\mathrm{gap}}L)^2}
\sim
\frac{1}{\Delta_{\mathrm{gap}}^2}.
$$

In the CFT, the same expansion appears as a hierarchy of corrections to double-trace operator dimensions and OPE coefficients.

## Dictionary checkpoint

The main translation of this page is:

$$
\boxed{
\begin{array}{ccl}
\text{light single-trace primaries} &\longleftrightarrow& \text{light bulk fields},\\[1mm]
\text{large }N &\longleftrightarrow& G_N/L^{d-1}\ll 1,\\[1mm]
\text{large single-trace gap} &\longleftrightarrow& M_{\mathrm{gap}}L\gg 1,\\[1mm]
\text{OPE coefficients} &\longleftrightarrow& \text{bulk couplings},\\[1mm]
\text{double-trace anomalous dimensions} &\longleftrightarrow& \text{bulk binding/scattering data}.
\end{array}}
$$

Bulk EFT is the low-energy expansion of this dictionary.

## Common confusions

### “Large $N$ automatically means Einstein gravity.”

No. Large $N$ suppresses connected correlators and bulk loops, but it does not guarantee a sparse spectrum or a large gap. Vector models at large $N$ are the standard warning: they can be dual to higher-spin theories rather than Einstein gravity.

### “A bottom-up action is automatically a CFT dual.”

No. A bottom-up model is a useful effective model only if it respects the consistency constraints expected of a UV-complete holographic theory: unitarity, causality, Ward identities, correct boundary conditions, and controlled scales.

### “Bulk locality is exact.”

No. Bulk locality is approximate and regime-dependent. The exact CFT is local on the boundary. Bulk locality emerges after taking a large-$N$, low-energy, large-gap limit.

### “The gap must remove all extra fields.”

Not necessarily. In AdS$_5\times S^5$, the $S^5$ Kaluza–Klein modes have masses of order $1/L$, so they are not separated from AdS physics. The correct local EFT is ten-dimensional type IIB supergravity, not merely five-dimensional pure Einstein gravity, unless one consistently truncates to a smaller sector.

### “Higher-derivative corrections are always small at large $N$.”

No. Higher-derivative corrections are controlled by the gap, not by $N$ alone. Bulk loops are controlled by $1/N^2$; stringy or higher-spin corrections are controlled by $1/\Delta_{\mathrm{gap}}$ or $1/\lambda$ in the canonical example.

## Exercises

### Exercise 1

In AdS$_5\times S^5$/CFT$_4$, the string scale satisfies

$$
\frac{L^2}{\alpha'}=\sqrt\lambda.
$$

Estimate the dimension of a typical massive string excitation in AdS units.

<details>
<summary><strong>Solution</strong></summary>

A massive string state has approximately

$$
m_s^2\sim \frac{1}{\alpha'}.
$$

Thus

$$
(m_sL)^2\sim \frac{L^2}{\alpha'}=\sqrt\lambda,
$$

so

$$
m_sL\sim \lambda^{1/4}.
$$

For a heavy AdS particle, the CFT dimension is approximately $\Delta\sim mL$, so

$$
\Delta_{\mathrm{stringy}}\sim \lambda^{1/4}.
$$

This is the stringy gap of the canonical example.

</details>

### Exercise 2

Assume normalized single-trace operators satisfy

$$
\langle \mathcal O_1\cdots\mathcal O_n\rangle_c\sim N^{2-n}.
$$

What is the $N$-scaling of a connected four-point function? What bulk effect does it represent?

<details>
<summary><strong>Solution</strong></summary>

For $n=4$,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle_c
\sim
N^{-2}.
$$

In the bulk, this is the scaling of a tree-level four-point Witten diagram built either from a quartic contact interaction or from two cubic vertices connected by an exchange propagator. Bulk loop corrections are further suppressed by additional powers of $1/N^2$.

</details>

### Exercise 3

A bulk EFT contains a correction

$$
\Delta S
=
\frac{1}{16\pi G_N}
\int d^{d+1}x\sqrt{-g}\,
\frac{1}{M_{\mathrm{gap}}^2}R^2.
$$

Estimate its size relative to the Einstein-Hilbert term in an AdS background of radius $L$.

<details>
<summary><strong>Solution</strong></summary>

In AdS,

$$
R\sim \frac{1}{L^2}.
$$

The Einstein-Hilbert term scales like $R\sim 1/L^2$, while the correction scales like

$$
\frac{R^2}{M_{\mathrm{gap}}^2}
\sim
\frac{1}{M_{\mathrm{gap}}^2L^4}.
$$

The relative size is therefore

$$
\frac{1/(M_{\mathrm{gap}}^2L^4)}{1/L^2}
=
\frac{1}{(M_{\mathrm{gap}}L)^2}
\sim
\frac{1}{\Delta_{\mathrm{gap}}^2}.
$$

A large CFT gap is precisely what makes this correction small.

</details>

## Further reading

- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151).
- A. L. Fitzpatrick and J. Kaplan, [Effective Conformal Theory and the Flat-Space Limit of AdS](https://arxiv.org/abs/1007.2412).
- A. Hamilton, D. Kabat, G. Lifschytz, and D. A. Lowe, [Local Bulk Operators in AdS/CFT](https://arxiv.org/abs/hep-th/0506118).
- D. Kabat, G. Lifschytz, and D. A. Lowe, [Constructing Local Bulk Observables in Interacting AdS/CFT](https://arxiv.org/abs/1102.2910).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
