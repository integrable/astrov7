---
title: "Regimes of Validity"
description: "When AdS/CFT is an exact quantum duality, when it becomes classical string theory, and when classical Einstein gravity is a reliable approximation."
sidebar:
  order: 30
---

The previous page, [What the Duality Claims](../what-the-duality-claims/), emphasized that AdS/CFT has several layers:

$$
\text{exact quantum duality}
\quad \Longrightarrow \quad
\text{large-}N\text{ string/gravity expansion}
\quad \Longrightarrow \quad
\text{classical on-shell gravity recipe}.
$$

This page is the warning label for the rest of the course. Many beautiful holographic calculations are simple because they are performed in a special corner of parameter space. That corner is not the whole duality. It is the corner where the bulk has a weakly curved, weakly quantum, classical gravitational description.

For the canonical example,

$$
\mathcal N=4\; SU(N)\;\text{super-Yang–Mills}
\quad
\longleftrightarrow
\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5,
$$

the two most important knobs are

$$
N
\qquad\text{and}\qquad
\lambda = g_{\mathrm{YM}}^2 N.
$$

The integer $N$ counts colors in the gauge theory and five-form flux in the bulk. The 't Hooft coupling $\lambda$ measures the strength of interactions in the planar gauge theory and also controls the curvature of the string background in string units.

The punchline is:

$$
\boxed{
\begin{aligned}
N \gg 1 &\quad \Rightarrow \quad \text{bulk quantum loops are suppressed},\\
\lambda \gg 1 &\quad \Rightarrow \quad \text{stringy curvature corrections are suppressed}.
\end{aligned}}
$$

Classical two-derivative gravity requires both.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A parameter-regime map for AdS/CFT, showing that large N suppresses bulk loops while large 't Hooft coupling suppresses stringy alpha-prime corrections.](/figures/course/regimes-of-validity-map.svg)

<figcaption>

The two main expansion parameters of the canonical AdS$_5$/CFT$_4$ example. Moving upward increases $N$ and suppresses bulk quantum loops. Moving rightward increases $\lambda$ and suppresses stringy $\alpha'$ corrections. Classical Einstein gravity lives in the upper-right corner, while the exact duality is expected to exist beyond this controlled corner.

</figcaption>
</figure>

## The canonical parameter map

In a common convention for the D3-brane system,

$$
g_{\mathrm{YM}}^2 = 4\pi g_s,
\qquad
\lambda = g_{\mathrm{YM}}^2N = 4\pi g_s N,
$$

and the AdS radius satisfies

$$
L^4 = 4\pi g_s N\alpha'^2.
$$

Equivalently,

$$
\frac{L^4}{\alpha'^2} = \lambda,
\qquad
\frac{L^2}{\alpha'} = \sqrt{\lambda},
\qquad
\frac{L}{\ell_s} = \lambda^{1/4},
$$

where $\ell_s^2=\alpha'$. Thus large $\lambda$ means that the curvature radius is large compared with the string length.

The string coupling is

$$
g_s = \frac{\lambda}{4\pi N}.
$$

So if $N$ is large at fixed or moderately growing $\lambda$, string loops are suppressed. In practice, the classical supergravity limit is taken with

$$
N \to \infty,
\qquad
\lambda \to \infty,
\qquad
\frac{\lambda}{N} \to 0
$$

or, less pedantically, with $N$ and $\lambda$ both parametrically large while $g_s$ remains small.

There is one more useful relation. The ten-dimensional Newton constant scales as

$$
G_{10} \sim g_s^2\alpha'^4.
$$

For $\mathrm{AdS}_5\times S^5$, dimensional reduction gives

$$
G_5 \sim \frac{G_{10}}{L^5},
$$

and therefore

$$
\frac{L^3}{G_5} \sim N^2.
$$

This is why classical gravitational actions scale like $N^2$, matching the number of gluonic degrees of freedom in a four-dimensional adjoint gauge theory.

With conventional normalizations, the central charges of large-$N$ $\mathcal N=4$ SYM satisfy

$$
a=c=\frac{N^2-1}{4}
\approx
\frac{N^2}{4},
$$

while the gravity formula gives

$$
a=c=\frac{\pi L^3}{8G_5}.
$$

The equality of these scalings is not a detail. It is the reason a saddle-point gravitational action can reproduce a large-$N$ CFT generating functional.

## Three distinct approximations

It is helpful to separate three approximations that are often bundled together.

### 1. The large-$N$ or genus expansion

In a gauge theory with adjoint fields, diagrams can be drawn in double-line notation. Their topology determines their power of $N$:

$$
\mathcal A
=
\sum_{g=0}^{\infty} N^{2-2g}F_g(\lambda),
$$

where $g$ is the genus of the associated ribbon graph. Planar diagrams dominate at $N=\infty$, and nonplanar diagrams are suppressed by powers of $1/N^2$.

This looks like the closed-string perturbation series,

$$
\mathcal A_{\mathrm{string}}
=
\sum_{g=0}^{\infty} g_s^{2g-2}\mathcal F_g.
$$

The comparison suggests that the bulk string loop expansion is the boundary $1/N$ expansion. More precisely, after translating conventions, bulk loop corrections are controlled by powers of

$$
\frac{G_N}{L^{d-1}} \sim \frac{1}{N^2}.
$$

Thus $N\gg 1$ is the condition for a weakly quantum bulk.

### 2. The large-$\lambda$ or low-string-scale expansion

The bulk theory is a string theory, not just a gravity theory. Even at zero string coupling, a string propagating in a curved background receives corrections controlled by the ratio of the string length to the curvature radius.

For the canonical example,

$$
\frac{\ell_s}{L} = \lambda^{-1/4}.
$$

So large $\lambda$ suppresses stringy corrections. The first higher-derivative correction in type IIB string theory on $\mathrm{AdS}_5\times S^5$ begins schematically with an $R^4$ interaction and gives corrections to many observables that scale as a power of $\lambda^{-3/2}$.

The important lesson is that large $N$ by itself is not enough for Einstein gravity. It gives a classical string theory, but the strings may still be propagating in a highly curved background.

### 3. The low-energy bulk effective field theory expansion

Even when strings are weakly coupled and curvature is small in string units, the bulk contains many fields. Type IIB supergravity on $\mathrm{AdS}_5\times S^5$ includes the metric, form fields, the dilaton, the axion, fermions, and an infinite tower of Kaluza–Klein modes after compactification on $S^5$.

A still simpler model, such as five-dimensional Einstein gravity coupled to a few matter fields, is another approximation. It may be justified in a consistent truncation or as a low-energy effective description of a restricted sector, but it is not automatically equivalent to the full string dual.

So there is a hierarchy:

$$
\text{full quantum string theory}
\supset
\text{classical string theory}
\supset
\text{classical supergravity}
\supset
\text{simple Einstein-matter truncation}.
$$

Each arrow throws away physics.

## Regime table

The following table is a useful first map. It is schematic, because precise control also depends on the observable, the state, the amount of supersymmetry, and the spectrum of the CFT.

| Boundary regime | Bulk description | What is controlled? | What is hard? |
|---|---|---|---|
| finite $N$, finite $\lambda$ | full quantum string theory on AdS | exact CFT definition, in principle | bulk spacetime may be highly quantum and stringy |
| $N\gg 1$, fixed $\lambda$ | classical string theory on AdS | string loops suppressed | worldsheet theory may be strongly curved |
| $N\gg 1$, $\lambda\ll 1$ | weakly coupled planar gauge theory | boundary perturbation theory | no simple Einstein gravity |
| $N\gg 1$, $\lambda\gg 1$ | classical supergravity | tree-level bulk geometry | stringy corrections are small but not zero |
| $N\gg 1$, $\lambda\gg 1$, large gap/truncation | classical Einstein-matter gravity | simple geometric calculations | model-dependence of truncation |
| large $\lambda$, finite $N$ | weakly curved but quantum gravity | geometric intuition may survive | bulk loops and nonperturbative effects matter |

A common mistake is to identify the fourth or fifth row with AdS/CFT itself. Those rows are controlled approximations to the duality, not the duality.

## What survives outside classical gravity?

Classical geometry is a special language. The exact boundary theory can exist even when that language becomes awkward.

At finite $N$, bulk quantum effects are not negligible. Black-hole entropy is no longer just a classical area in a smooth saddle; it receives quantum and possibly nonperturbative corrections. Bulk locality becomes approximate and state-dependent. The gravitational path integral is not simply dominated by one geometry.

At finite or small $\lambda$, the bulk is stringy. The AdS radius is not large compared with the string length, so massive string modes cannot be ignored. A local two-derivative gravitational action is then the wrong tool. The CFT may nevertheless be perfectly well defined.

At weak coupling $\lambda\ll 1$, the boundary theory may be accessible by ordinary perturbation theory. The corresponding bulk is highly curved in string units, which is why it is difficult to see classical geometry from weakly coupled Feynman diagrams. This is not a contradiction. A duality can map a simple description on one side to a complicated description on the other.

## Strong/weak does not mean source/response

The phrase “strong/weak duality” can be misleading here. It is true that the useful supergravity limit corresponds to strong 't Hooft coupling on the boundary. But the full duality is not merely a relation between a strongly coupled theory and a weakly coupled one.

For example, at large $N$ and small $\lambda$, the CFT is weakly coupled and the bulk is highly stringy. At large $N$ and large $\lambda$, the CFT is strongly coupled and the bulk is weakly curved. Both are regions of the same conjectured equivalence.

The inversion is between different expansion parameters:

$$
\lambda \gg 1
\quad
\Longleftrightarrow
\quad
\frac{\ell_s}{L}\ll 1,
$$

and

$$
N \gg 1
\quad
\Longleftrightarrow
\quad
\frac{G_N}{L^{d-1}}\ll 1.
$$

Boundary perturbation theory expands in small $\lambda$. Bulk low-energy gravity expands in small $\ell_s/L$ and small $G_N/L^{d-1}$. These are not the same expansion.

## Why $N^2$ is the size of the classical action

One of the cleanest checks of the regime map is the scaling of the action.

A gravitational action in $d+1$ dimensions has the schematic form

$$
S_{\mathrm{grav}}
\sim
\frac{1}{G_{d+1}}\int d^{d+1}x\sqrt{g}\,R.
$$

For a spacetime whose curvature radius is $L$, the dimensionless size of the action is roughly

$$
S_{\mathrm{grav}}
\sim
\frac{L^{d-1}}{G_{d+1}}.
$$

In AdS$_5$/CFT$_4$,

$$
\frac{L^3}{G_5}\sim N^2.
$$

Therefore the classical on-shell action scales as $N^2$:

$$
S_{\text{on-shell}} \sim N^2.
$$

This is exactly what one expects for a large-$N$ gauge theory with adjoint degrees of freedom. The free energy, entropy density, and connected correlators of single-trace operators all have characteristic large-$N$ scalings.

The saddle-point approximation is therefore a large-$N$ approximation:

$$
Z_{\mathrm{bulk}}
\approx
\exp\!\left(-S_{\mathrm{cl}}\right)
$$

is reliable when the dimensionless action is large. The reason the gravitational saddle is sharp is not mystical; it is the same reason a path integral with a large prefactor is dominated by stationary points.

## What “classical supergravity” really means

In many holography papers one reads: “We work in the classical gravity limit.” Usually this means more than one thing.

It means $N$ is large enough that bulk loops are negligible:

$$
\frac{G_N}{L^{d-1}} \ll 1.
$$

It means $\lambda$ is large enough that higher-derivative string corrections are negligible:

$$
\frac{\alpha'}{L^2} \ll 1.
$$

It often means one is using a low-energy truncation that keeps only a small set of bulk fields. For example, many bottom-up calculations use an action like

$$
S
=
\frac{1}{16\pi G_{d+1}}
\int d^{d+1}x\sqrt{-g}
\left(
R + \frac{d(d-1)}{L^2}
-\frac{1}{4}F^2
- |D\Phi|^2
- V(|\Phi|)
\right).
$$

This can be an excellent effective model. But it is not the same as deriving a complete string compactification. A responsible holographic calculation should say which level of approximation it is using.

## The CFT meaning of a weakly local bulk

Large $N$ alone gives factorization, but local Einstein gravity requires more. A generic large-$N$ CFT need not have a simple local bulk dual. For a weakly curved low-energy gravitational description, the CFT should also have a sparse spectrum of low-dimension single-trace operators, or equivalently a large gap to higher-spin/stringy single-trace states.

The rough field-theory condition is

$$
\Delta_{\mathrm{gap}} \gg 1,
$$

where $\Delta_{\mathrm{gap}}$ is the dimension of the lightest single-trace operator not included in the low-energy bulk effective theory. In the canonical AdS$_5\times S^5$ example, increasing $\lambda$ raises the dimensions of many stringy states in AdS units, producing a gap between supergravity modes and massive string modes.

This is the boundary translation of the geometric condition

$$
\ell_s \ll L.
$$

So the slogan “large $N$ gives gravity” needs refinement:

$$
\text{large }N
+
\text{large gap}
\quad
\Rightarrow
\quad
\text{weakly coupled local bulk effective theory}.
$$

Without the gap, the bulk may still exist as a stringy or higher-spin theory, but not as ordinary Einstein gravity with a small number of light fields.

## Finite temperature and black holes

Thermal states provide a useful diagnostic of the same regimes. In a deconfined large-$N$ CFT, the entropy density often scales as

$$
s \sim N^2 T^{d-1}.
$$

On the bulk side this comes from a black-brane horizon:

$$
S_{\mathrm{BH}}
=
\frac{A_{\mathrm{hor}}}{4G_N}.
$$

Since $1/G_N\sim N^2$, the horizon entropy has the correct large-$N$ scaling. This is why black holes are not rare decorations in AdS/CFT; they are the natural bulk description of thermal states with order $N^2$ degrees of freedom excited.

But the same caveats remain. The area law is the leading classical answer. Quantum bulk fields add subleading corrections. Higher-derivative terms add finite-$\lambda$ corrections. At finite $N$, the exact CFT partition function is still meaningful, but the simple horizon-area formula is no longer the full answer.

## Which regime will this course usually use?

The foundations course will move between three levels.

First, it will state formal dictionary entries that are meant to be exact, such as the equality of partition functions with specified boundary data.

Second, it will develop the semiclassical approximation in which

$$
Z_{\mathrm{bulk}}[J]
\approx
\exp\!\left(-S_{\text{ren,on-shell}}[J]\right).
$$

This is the level at which one computes many correlation functions, thermodynamic quantities, and transport coefficients.

Third, it will point out where the classical approximation must be corrected: holographic renormalization, alternate quantization, higher-derivative corrections, quantum extremal surfaces, bulk loops, and finite-$N$ effects.

The default computational regime of the course is therefore:

$$
N\gg 1,
\qquad
\lambda\gg 1,
\qquad
\text{large enough gap for a local bulk EFT}.
$$

Whenever a result needs stronger or weaker assumptions, the relevant page will say so.

## Dictionary checkpoint

The following translations are the main takeaways.

| Boundary statement | Bulk statement |
|---|---|
| $N\gg 1$ | bulk quantum loops are suppressed |
| $1/N^2$ expansion | closed-string genus / bulk loop expansion |
| $\lambda\gg 1$ | $L\gg \ell_s$, so stringy curvature corrections are suppressed |
| finite $\lambda$ | $\alpha'$ corrections or full string dynamics matter |
| $L^{d-1}/G_N\gg 1$ | classical saddle-point approximation is sharp |
| large gap in single-trace spectrum | local bulk EFT with few light fields |
| finite $N$ | genuinely quantum gravity effects are important |
| classical Einstein gravity | a controlled corner, not the full duality |

The safest mental model is this:

$$
\text{AdS/CFT is exact; classical gravity is an approximation.}
$$

## Common confusions

### “Large $N$ automatically means Einstein gravity.”

No. Large $N$ suppresses bulk loops, but it does not by itself suppress stringy corrections. A large-$N$ CFT with no large gap may have a dual that is stringy, higher-spin-like, or otherwise not well described by local Einstein gravity.

### “Large $\lambda$ means the gauge theory is easier.”

Usually the opposite. Large $\lambda$ means the boundary gauge theory is strongly coupled. It is easier only after translating to the bulk, where large $\lambda$ means weak curvature in string units.

### “Finite $N$ breaks the duality.”

Finite $N$ breaks the classical-gravity approximation, not the duality. The exact CFT still exists at finite $N$. What may disappear is a simple semiclassical spacetime description.

### “Supergravity means pure gravity.”

No. Supergravity contains many fields besides the metric. In AdS$_5\times S^5$, the full ten-dimensional supergravity theory includes the compact $S^5$, fluxes, scalars, fermions, and Kaluza–Klein modes. Pure Einstein gravity is a further truncation.

### “The $1/N$ expansion and the $1/\lambda$ expansion are the same.”

They are different. The $1/N$ expansion controls quantum loops in the bulk. The large-$\lambda$ expansion controls stringy corrections. A calculation can be classical but stringy, or weakly curved but quantum, depending on how the limits are taken.

## Exercises

### Exercise 1: Estimate the bulk expansion parameters

Assume the common convention

$$
g_s = \frac{\lambda}{4\pi N},
\qquad
\frac{L}{\ell_s}=\lambda^{1/4}.
$$

For $N=10^6$ and $\lambda=100$, estimate $g_s$ and $L/\ell_s$. Is the bulk weakly coupled? Is it very weakly curved?

<details>
<summary><strong>Solution</strong></summary>

We find

$$
g_s
=
\frac{100}{4\pi\times 10^6}
\approx
8\times 10^{-6}.
$$

So string loops are extremely suppressed. Also

$$
\frac{L}{\ell_s}
=
100^{1/4}
=\sqrt{10}
\approx 3.16.
$$

The curvature radius is a few string lengths. This is larger than the string scale, but not enormously larger. The bulk is very weakly coupled, but stringy corrections may still be worth tracking unless one only wants a qualitative leading approximation. Parametrically, the clean supergravity limit requires $\lambda\to\infty$, not merely $\lambda=100$.

</details>

### Exercise 2: Show that the gravitational action scales like $N^2$

Use

$$
L^4 \sim g_sN\alpha'^2,
\qquad
G_{10}\sim g_s^2\alpha'^4.
$$

Show that

$$
\frac{L^8}{G_{10}}\sim N^2.
$$

Why is this the right scaling for a large-$N$ gauge theory with adjoint fields?

<details>
<summary><strong>Solution</strong></summary>

From

$$
L^4 \sim g_sN\alpha'^2,
$$

we get

$$
L^8 \sim g_s^2N^2\alpha'^4.
$$

Dividing by

$$
G_{10}\sim g_s^2\alpha'^4
$$

gives

$$
\frac{L^8}{G_{10}}
\sim
\frac{g_s^2N^2\alpha'^4}{g_s^2\alpha'^4}
\sim
N^2.
$$

After compactifying on $S^5$, this becomes $L^3/G_5\sim N^2$. A four-dimensional gauge theory with adjoint fields has order $N^2$ matrix degrees of freedom, so its free energy and stress-tensor two-point normalization also scale as $N^2$. The scaling of the classical gravitational action matches the scaling of the boundary degrees of freedom.

</details>

### Exercise 3: Large $N$ but small $\lambda$

Suppose $N\to\infty$ while $\lambda\ll 1$ is fixed. Which side is perturbative, and why is classical Einstein gravity not reliable?

<details>
<summary><strong>Solution</strong></summary>

At small $\lambda$, the boundary gauge theory is weakly coupled, so ordinary perturbation theory may be useful. Since $N\to\infty$, nonplanar corrections are suppressed and one obtains a planar gauge theory.

On the bulk side, however,

$$
\frac{L}{\ell_s}=\lambda^{1/4}\ll 1
$$

if $\lambda\ll 1$. The curvature radius is smaller than the string length, so the background is highly curved in string units. This invalidates the two-derivative Einstein gravity approximation. The appropriate dual description would be a classical but strongly stringy theory, not classical supergravity.

</details>

### Exercise 4: Why a large gap matters

Explain why a CFT with large $N$ but many light single-trace higher-spin operators should not be expected to have a simple Einstein gravity dual.

<details>
<summary><strong>Solution</strong></summary>

Single-trace operators correspond to single-particle bulk fields. If many single-trace operators have low dimensions, then many bulk fields have masses of order the AdS scale or below. A low-energy bulk observer cannot consistently ignore them. A simple Einstein-matter theory with only the metric and a few light fields is then not a complete low-energy description.

A large gap means that most stringy or higher-spin single-particle states are heavy in AdS units. Then a local effective field theory with a small number of light fields can be valid below the gap. This is the CFT-side meaning of having a weakly curved local bulk description.

</details>

## Further reading

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200). The original AdS/CFT proposal and the D3-brane origin of the canonical parameter map.
- G. 't Hooft, [Large N](https://arxiv.org/abs/hep-th/0204069). A concise discussion of the large-$N$ expansion and its relation to planar diagrams.
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111). The standard review, especially useful for understanding large $N$, large $\lambda$, and the supergravity regime.
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151). A modern CFT-first perspective on why large $N$ plus a large gap leads to local bulk effective field theory.
