---
title: "Large N Gauge Theory"
description: "How the large N limit reorganizes gauge theory by topology, why planar diagrams dominate, and why this is the field-theory origin of weakly coupled bulk strings and gravity."
sidebar:
  order: 40
---

Large-$N$ gauge theory is the first place where AdS/CFT starts to look less like magic. A gauge theory with gauge group $SU(N)$ or $U(N)$ contains fields with color indices. When those fields are in the adjoint representation, they are $N\times N$ matrices. Feynman diagrams then carry not only spacetime and momentum information, but also **color topology**.

The large-$N$ limit turns this topology into an organizing principle. Instead of expanding only in a small coupling constant, we reorganize diagrams by the genus of a two-dimensional surface. Planar diagrams dominate, nonplanar handles are suppressed by powers of $1/N^2$, and the resulting expansion has the same form as a closed-string perturbation series.

This is the field-theory reason why holography does not merely relate a gauge theory to a classical spacetime. At large $N$, gauge theory begins to behave like a weakly coupled string theory. In favorable cases, such as strongly coupled $\mathcal N=4$ super-Yang–Mills theory, that string theory has a low-energy limit described by classical gravity in AdS.

## Why this matters

AdS/CFT has two separate semiclassical limits:

$$
\text{large } N
\quad\Longrightarrow\quad
\text{weak bulk quantum loops},
$$

and

$$
\text{large 't Hooft coupling } \lambda
\quad\Longrightarrow\quad
\text{weak stringy curvature corrections}.
$$

This page explains the first arrow. The next pages will refine the operator dictionary, but the basic slogan is already visible:

$$
\frac{1}{N}
\quad\text{acts like a bulk interaction strength}.
$$

More precisely, for canonically normalized single-trace operators,

$$
\langle \mathcal O_1 \mathcal O_2 \rangle_c \sim N^0,
\qquad
\langle \mathcal O_1 \mathcal O_2 \mathcal O_3 \rangle_c \sim \frac{1}{N},
\qquad
\langle \mathcal O_1\cdots \mathcal O_n\rangle_c \sim N^{2-n}.
$$

This is exactly the pattern one expects from weakly interacting single-particle fields in a bulk theory: two-point functions normalize the particles, three-point functions measure cubic interactions, and higher connected amplitudes become increasingly suppressed.

## The 't Hooft limit

Consider a gauge theory with gauge group $SU(N)$ or $U(N)$. The Yang–Mills coupling $g_{\mathrm{YM}}$ is not the best variable to keep fixed as $N$ becomes large. The useful coupling is the **'t Hooft coupling**

$$
\lambda = g_{\mathrm{YM}}^2 N.
$$

The 't Hooft large-$N$ limit is

$$
N\to \infty,
\qquad
\lambda = g_{\mathrm{YM}}^2 N \;\text{fixed}.
$$

Equivalently,

$$
g_{\mathrm{YM}}^2 \sim \frac{\lambda}{N}.
$$

This scaling is not cosmetic. It is what keeps the leading diagrams finite and nontrivial. If $g_{\mathrm{YM}}$ were held fixed instead, the number of color degrees of freedom would grow while the interaction strength stayed too large. If $g_{\mathrm{YM}}$ were sent to zero too quickly, the large-$N$ theory would become trivial.

The 't Hooft limit holds fixed the effective coupling felt by a typical color loop.

## Adjoint fields are matrices

An adjoint field may be written as

$$
X(x) = X^a(x) T^a,
$$

or, more explicitly, as a matrix

$$
X^i{}_{j}(x),
\qquad
 i,j=1,\ldots,N.
$$

The two color indices are the key. A fundamental field $q^i$ carries one color line. An adjoint field $X^i{}_{j}$ carries two color lines, one for the upper index and one for the lower index. This turns ordinary Feynman diagrams into **ribbon graphs**.

The adjoint propagator schematically carries color structure

$$
\langle X^i{}_{j}(x) X^k{}_{l}(y) \rangle
\propto
\delta^i_l\delta^k_j
\times
\text{spacetime propagator}.
$$

The important point is not the detailed spacetime factor. The important point is the pair of Kronecker deltas. They show how color flows through the diagram.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Large N ribbon graph topology](/figures/course/large-n-topology.svg)

<figcaption>

Large-$N$ perturbation theory is organized by the topology of double-line color graphs. A connected diagram with genus $g$ and $b$ boundaries scales as $N^{2-2g-b}$, up to a function of the 't Hooft coupling $\lambda=g_{\mathrm{YM}}^2N$.

</figcaption>
</figure>

## Double-line notation

In ordinary Feynman diagrams, a propagator is drawn as a single line. For an adjoint field, it is more informative to draw the propagator as two oppositely oriented color lines:

$$
X^i{}_{j}
\quad\leadsto\quad
\text{one line for } i,\;\text{one line for } j.
$$

When diagrams are drawn this way, each closed color loop contributes a factor of $N$ because it represents a sum over a free color index:

$$
\sum_{i=1}^{N} \delta^i_i = N.
$$

Thus the power of $N$ associated with a diagram can be read combinatorially:

- each closed color face contributes $N$;
- each propagator contributes a factor proportional to $g_{\mathrm{YM}}^2 \sim \lambda/N$;
- each interaction vertex contributes compensating factors determined by the action;
- at fixed $\lambda$, the remaining $N$-dependence depends only on topology.

For a connected vacuum ribbon graph, the result is

$$
\mathcal A \sim N^{F-E+V} f(\lambda),
$$

where $F$ is the number of faces, $E$ is the number of edges, and $V$ is the number of vertices of the ribbon graph. But

$$
F-E+V = \chi,
$$

where $\chi$ is the Euler characteristic of the two-dimensional surface on which the ribbon graph can be drawn without crossings. For a closed oriented surface of genus $g$,

$$
\chi = 2-2g.
$$

Therefore

$$
\mathcal A_g \sim N^{2-2g} f_g(\lambda).
$$

Planar diagrams have $g=0$ and scale as $N^2$. Diagrams with one handle have $g=1$ and scale as $N^0$. Diagrams with two handles scale as $N^{-2}$, and so on.

The expansion of the connected vacuum functional takes the form

$$
\log Z
=
\sum_{g=0}^{\infty} N^{2-2g} F_g(\lambda).
$$

This is the large-$N$ topological expansion.

## Why planar diagrams dominate

At large $N$ with fixed $\lambda$,

$$
N^2 \gg N^0 \gg N^{-2} \gg \cdots.
$$

So the leading contribution comes from genus-zero diagrams. These are called **planar diagrams**, because they can be drawn on the plane or sphere without crossing double-line color strands.

The name “planar” is topological, not geometric in spacetime. A planar diagram may involve complicated momentum integrals and many vertices. What matters is that its color ribbon graph can be placed on a sphere without handles.

The large-$N$ expansion is therefore not the same as weak-coupling perturbation theory. Even when $\lambda$ is not small, one may still hope that the theory has an expansion in powers of $1/N$:

$$
\text{large }N\text{ expansion}
\neq
\text{small }\lambda\text{ expansion}.
$$

This distinction is essential in AdS/CFT. Classical gravity is expected when $N$ is large and $\lambda$ is large. Perturbative gauge-theory Feynman diagrams are useful when $\lambda$ is small. The most interesting holographic regime is precisely where ordinary perturbation theory fails, but the $1/N$ expansion remains meaningful.

## Boundaries and operator insertions

So far we discussed vacuum diagrams. Correlation functions of single-trace operators introduce marked boundaries on the ribbon surface.

A typical single-trace operator is

$$
\operatorname{Tr}(X_1 X_2\cdots X_J)
=
X_1{}^{i_1}{}_{i_2}
X_2{}^{i_2}{}_{i_3}
\cdots
X_J{}^{i_J}{}_{i_1}.
$$

The trace ties color indices into a loop. In the ribbon graph, that loop behaves like a boundary component. For connected correlators of canonically normalized single-trace operators, the large-$N$ scaling is

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_c
=
\sum_{g=0}^{\infty}
N^{2-2g-n}
G_{g,n}(\lambda).
$$

At leading genus,

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_c
\sim
N^{2-n}.
$$

Thus

$$
\langle \mathcal O_1\mathcal O_2\rangle_c \sim N^0,
\qquad
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle_c \sim \frac{1}{N},
\qquad
\langle \mathcal O_1\cdots\mathcal O_4\rangle_c \sim \frac{1}{N^2}.
$$

This is the standard normalization used when one wants single-trace operators to create single-particle bulk states with order-one two-point functions.

A warning about normalization is useful here. Some authors use unnormalized operators such as $\operatorname{Tr}X^J$, while others insert powers of $N$ or $\sqrt N$ so that two-point functions are order one. The physics is not changed by this convention, but the explicit powers of $N$ in correlators move around. Whenever comparing formulas, first check how the operators and sources are normalized.

## Large-$N$ factorization

The most important consequence of the previous scaling is **factorization**. Suppose $A$ and $B$ are gauge-invariant single-trace or multi-trace operators normalized so that their expectation values are order one. Then connected correlations are suppressed:

$$
\langle A B\rangle
=
\langle A\rangle\langle B\rangle
+O\!\left(\frac{1}{N^2}\right),
$$

for bosonic gauge-invariant observables of the usual single-trace type.

This resembles a classical limit. In ordinary quantum mechanics, connected fluctuations are suppressed when $\hbar\to 0$. In large-$N$ gauge theory, connected fluctuations of suitable gauge-invariant observables are suppressed when $1/N\to 0$.

This is one reason the bulk dual can become classical. The boundary theory remains a quantum field theory, but its gauge-invariant collective variables behave more and more classically as $N$ grows.

The next page will examine this point more carefully because it is the bridge from large-$N$ field theory to bulk Fock space.

## The string-theory interpretation

The genus expansion of large-$N$ gauge theory looks like the perturbative expansion of a closed string theory. A closed-string partition function has the schematic form

$$
Z_{\mathrm{string}}
=
\sum_{g=0}^{\infty}
 g_s^{2g-2} Z_g,
$$

where $g_s$ is the string coupling and $g$ is the genus of the string worldsheet.

The gauge-theory expansion has the form

$$
\log Z_{\mathrm{gauge}}
=
\sum_{g=0}^{\infty}
N^{2-2g}F_g(\lambda).
$$

Comparing the powers gives the rough identification

$$
g_s \sim \frac{1}{N}.
$$

In the canonical AdS$_5$/CFT$_4$ example, the more precise parametric relation is

$$
g_s \sim \frac{\lambda}{N},
$$

up to conventional numerical factors. At fixed large $\lambda$, large $N$ still means weak string coupling.

This does not mean every large-$N$ gauge theory has a simple classical gravity dual. The large-$N$ expansion suggests a string description, but classical Einstein gravity requires more. Roughly, the string theory must have a regime in which massive string modes are much heavier than the AdS curvature scale. In the boundary language, that corresponds to a large gap in the spectrum of higher-spin single-trace operators.

So the hierarchy is:

$$
\text{large }N
\quad\Rightarrow\quad
\text{weakly coupled string expansion},
$$

but

$$
\text{large }N + \text{large gap/strong coupling}
\quad\Rightarrow\quad
\text{local classical gravity}.
$$

## Why $N^2$ degrees of freedom?

An adjoint matrix has approximately $N^2$ components. This simple fact has many holographic consequences.

For example, the free energy density of a deconfined large-$N$ adjoint plasma typically scales as

$$
F \sim N^2.
$$

The central charge or stress-tensor two-point coefficient of a holographic CFT also scales as

$$
C_T \sim N^2.
$$

On the gravity side, the coefficient controlling classical gravitational dynamics is the inverse Newton constant in AdS units:

$$
\frac{L^{d-1}}{G_N} \sim N^2.
$$

This relation is one of the most important normalization facts in the entire course. It says that the bulk classical action is large:

$$
S_{\mathrm{bulk}} \sim \frac{L^{d-1}}{G_N} \sim N^2.
$$

A large action suppresses quantum fluctuations around a saddle point. Thus the same $N^2$ that counts adjoint degrees of freedom in the gauge theory becomes the semiclassical parameter of the bulk gravitational path integral.

## A useful toy model of the counting

To see the counting without the complications of gauge fixing and vector indices, consider a matrix field $X^i{}_{j}$ with an action schematically normalized as

$$
S[X]
=
\frac{N}{\lambda}
\int d^d x\;
\operatorname{Tr}
\left[
\frac12 (\partial X)^2 + \frac12 X^2 + \frac{1}{3}X^3 + \cdots
\right].
$$

This normalization makes the $N$-counting transparent. The propagator carries a factor

$$
\frac{\lambda}{N},
$$

while an interaction vertex carries a factor

$$
\frac{N}{\lambda}.
$$

A graph with $E$ propagators, $V$ vertices, and $F$ closed color faces gives

$$
N^F
\left(\frac{\lambda}{N}\right)^E
\left(\frac{N}{\lambda}\right)^V
=
N^{F-E+V}\lambda^{E-V}.
$$

At fixed $\lambda$, the power of $N$ is

$$
N^{F-E+V}=N^\chi.
$$

The detailed power of $\lambda$ depends on the graph and the interaction vertices. The power of $N$ knows only the topology.

This is the core of the 't Hooft expansion.

## Relation to confinement and mesons

Large-$N$ ideas were originally developed as a way to understand strong interactions. In QCD-like theories with fundamental quarks, quark loops add boundaries to the ribbon surface. A diagram with genus $g$ and $b$ quark boundaries scales like

$$
\mathcal A_{g,b}
\sim
N^{2-2g-b}.
$$

Thus each additional quark loop costs a factor of $1/N$. In the strict large-$N$ limit, mesons become stable narrow resonances, and interactions among color-singlet hadrons are suppressed.

This historical connection is useful but should not be confused with the AdS/CFT examples studied later. The canonical AdS$_5$/CFT$_4$ theory is not QCD. It is conformal, supersymmetric, and contains only adjoint fields in its simplest form. The common lesson is the topological organization of gauge dynamics.

## What large $N$ does and does not do

Large $N$ does something profound: it creates a controlled expansion parameter even in strongly coupled gauge theories. But it does not automatically solve the theory.

At fixed $\lambda$, the planar contribution $F_0(\lambda)$ may still be a complicated function. If $\lambda$ is small, ordinary perturbation theory can approximate it. If $\lambda$ is large, perturbation theory in $\lambda$ fails. AdS/CFT becomes powerful precisely because it can sometimes compute $F_0(\lambda)$ at large $\lambda$ using classical gravity.

So there are two expansions:

$$
\text{topological expansion:}
\qquad
\frac{1}{N},
$$

and

$$
\text{coupling expansion:}
\qquad
\lambda\;\text{or}\;\frac{1}{\lambda}.
$$

In the classical gravity regime of AdS$_5$/CFT$_4$,

$$
N\gg 1,
\qquad
\lambda\gg 1.
$$

The first condition suppresses bulk loops. The second suppresses string-scale corrections.

## Dictionary checkpoint

The large-$N$ dictionary is:

| Gauge-theory statement | Bulk interpretation |
|---|---|
| adjoint fields are matrices | color flow becomes ribbon topology |
| $\lambda=g_{\mathrm{YM}}^2N$ fixed | smooth 't Hooft large-$N$ limit |
| planar diagrams dominate | genus-zero string worldsheets dominate |
| each handle costs $1/N^2$ | closed-string loops are suppressed |
| $1/N$ suppresses connected interactions | bulk fields interact weakly |
| $C_T\sim N^2$ | $L^{d-1}/G_N\sim N^2$ |
| large $N$ factorization | classical bulk saddle behavior |

The single most important sentence is this:

$$
\boxed{\text{Large }N\text{ is the boundary origin of the bulk semiclassical expansion.}}
$$

## Common confusions

### “Large $N$ means the gauge theory is weakly coupled.”

No. The 't Hooft coupling $\lambda=g_{\mathrm{YM}}^2N$ may be small or large. Large $N$ controls the topology of color diagrams. It does not by itself make the planar theory easy.

### “Planar diagrams are just diagrams that look planar on the page.”

No. Planarity refers to the double-line color graph. A diagram is planar if its ribbon graph can be drawn on a sphere without crossing color lines.

### “The string coupling is exactly $1/N$.”

Parametrically, large $N$ suppresses string loops. In the canonical AdS$_5$/CFT$_4$ normalization, $g_s$ is proportional to $\lambda/N$, up to numerical conventions. What is robust is that the closed-string genus expansion is controlled by powers of $1/N^2$ at fixed appropriate coupling.

### “Every large-$N$ gauge theory has an Einstein gravity dual.”

No. Large $N$ suggests a string-like expansion, not necessarily a weakly curved gravitational description. A simple Einstein gravity dual requires additional dynamical conditions, such as strong coupling and a sparse spectrum of low-dimension single-trace higher-spin operators.

### “$SU(N)$ and $U(N)$ make no difference.”

At leading large $N$, the distinction is often subleading for adjoint-sector observables. But it can matter for global issues, decoupled $U(1)$ factors, line operators, and precise dictionary questions. This course will usually ignore the distinction until it matters.

## Exercises

### Exercise 1: Euler counting

A connected vacuum ribbon graph has $V$ vertices, $E$ propagators, and $F$ closed color faces. Assume the action is normalized so that propagators contribute $\lambda/N$ and vertices contribute $N/\lambda$. Show that the graph scales as

$$
N^{F-E+V}
$$

at fixed $\lambda$, and identify this exponent with the Euler characteristic.

<details>
<summary><strong>Solution</strong></summary>

The color faces give a factor $N^F$. The propagators give $(\lambda/N)^E$. The vertices give $(N/\lambda)^V$. Multiplying these factors gives

$$
N^F
\left(\frac{\lambda}{N}\right)^E
\left(\frac{N}{\lambda}\right)^V
=
N^{F-E+V}\lambda^{E-V}.
$$

At fixed $\lambda$, the power of $N$ is $F-E+V$. For a ribbon graph drawn on a closed oriented surface, this is the Euler characteristic

$$
\chi = F-E+V.
$$

For genus $g$,

$$
\chi = 2-2g,
$$

so the graph scales as $N^{2-2g}$ times a function of $\lambda$.

</details>

### Exercise 2: Cost of a handle

Compare a planar connected vacuum diagram with a genus-one connected vacuum diagram. By what power of $N$ is the genus-one diagram suppressed?

<details>
<summary><strong>Solution</strong></summary>

A planar connected vacuum diagram has $g=0$, so it scales as

$$
N^{2-2g}=N^2.
$$

A genus-one connected vacuum diagram has $g=1$, so it scales as

$$
N^{2-2g}=N^0.
$$

The ratio is

$$
\frac{N^0}{N^2}=\frac{1}{N^2}.
$$

Thus one handle costs $1/N^2$.

</details>

### Exercise 3: Three-point interactions

Assume canonically normalized single-trace operators obey

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_c
\sim
N^{2-n}
$$

at leading planar order. What is the scaling of a connected three-point function? What does this suggest for the corresponding cubic bulk coupling?

<details>
<summary><strong>Solution</strong></summary>

For $n=3$,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle_c
\sim
N^{-1}.
$$

If the operators create canonically normalized single-particle bulk states, then the connected three-point function measures a cubic interaction among those bulk fields. The scaling suggests that the cubic bulk coupling is of order $1/N$.

</details>

### Exercise 4: Why large $N$ is not enough for classical gravity

Explain why the existence of a $1/N$ expansion does not by itself imply a weakly curved Einstein gravity dual.

<details>
<summary><strong>Solution</strong></summary>

The $1/N$ expansion organizes the theory by topology and suggests a weakly coupled string expansion. However, a string theory can still be highly stringy: many massive string modes may have masses comparable to the curvature scale, and higher-derivative corrections may be important. A weakly curved Einstein gravity dual requires not only weak string coupling, controlled by large $N$, but also suppression of string-scale corrections. In the canonical example this is achieved at large 't Hooft coupling $\lambda$, where $L^2/\alpha'$ is large.

</details>

## Further reading

- G. 't Hooft, [A Planar Diagram Theory for Strong Interactions](https://webspace.science.uu.nl/~hooft101/gthpub/planar_diagram_theory.pdf). The original source of the topological large-$N$ expansion.
- G. 't Hooft, [Large N](https://arxiv.org/abs/hep-th/0204069). A concise retrospective lecture on large-$N$ ideas.
- E. Witten, [Baryons in the 1/N Expansion](https://doi.org/10.1016/0550-3213(79)90232-3). A classic analysis of how hadronic physics simplifies at large $N$.
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large N Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111). The standard broad review connecting large-$N$ field theory to AdS/CFT.
