---
title: "N=4 Super-Yang-Mills"
description: "The field-theory side of the canonical AdS5/CFT4 duality: field content, action, symmetries, parameters, operators, moduli space, and holographic role."
sidebar:
  order: 60
---

The canonical example of AdS/CFT begins with one very special four-dimensional quantum field theory:

$$
\mathcal N=4\; SU(N)\; \text{super-Yang–Mills theory}.
$$

It is the boundary theory in the duality

$$
\mathcal N=4\; SU(N)\; \text{SYM in } d=4
\quad
\longleftrightarrow
\quad
\text{type IIB string theory on } \mathrm{AdS}_5\times S^5 .
$$

This page explains what an AdS/CFT user needs to know about this theory. We will not develop supersymmetric gauge theory from scratch. Instead, we isolate the structural facts that make $\mathcal N=4$ SYM the cleanest laboratory for holography: it is conformal, it is a large-$N$ matrix theory, all fields are adjoint-valued, its symmetries match the geometry of $\mathrm{AdS}_5\times S^5$, and its two dimensionless parameters become bulk string-theory parameters.

The most important moral is this:

$$
\text{large } N \text{ controls bulk quantum effects},
\qquad
\text{large } \lambda=g_{\mathrm{YM}}^2N \text{ controls stringy curvature corrections}.
$$

So $\mathcal N=4$ SYM is not merely a historical example. It is the prototype from which much of the holographic dictionary is learned.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Field content, symmetries, and holographic role of N=4 super-Yang-Mills theory](/figures/course/n4-super-yang-mills.svg)

<figcaption>

The canonical AdS$_5$/CFT$_4$ example is organized by a tight matching of field-theory data and bulk data. The adjoint fields of $\mathcal N=4$ SYM generate gauge-invariant operators; the conformal and R-symmetry groups become the isometry groups of $\mathrm{AdS}_5$ and $S^5$; and the parameters $N$ and $\lambda$ become flux, curvature, and loop-expansion data in the bulk.

</figcaption>
</figure>

## Why this matters

The previous pages explained the field-theory ingredients needed for holography: conformal symmetry, radial quantization, large-$N$ counting, single-trace operators, and large-$N$ factorization. $\mathcal N=4$ SYM is where those ingredients come together in a real, fully defined quantum field theory.

It has three properties that are individually important and collectively extraordinary.

First, it is a **four-dimensional conformal field theory with a Lagrangian**. This gives us a familiar starting point: fields, an action, gauge symmetry, local operators, and a path integral.

Second, it is a **large-$N$ matrix theory**. All elementary fields transform in the adjoint representation of the gauge group, so gauge-invariant operators naturally organize into traces. This is exactly the structure needed for the single-trace/multi-trace dictionary.

Third, it is **maximally supersymmetric** without including gravity. Supersymmetry protects many quantities, forces the beta function to vanish, and gives enough analytic control that the theory can be compared sharply to string theory.

The result is a rare situation: a nontrivial interacting QFT that is exactly conformal, has a controllable large-$N$ limit, and has a known string-theory construction.

## Two different symbols called N

There is an annoying but unavoidable notation issue.

The symbol $N$ in $SU(N)$ is the number of colors. It controls the size of matrices and the number of degrees of freedom. This is the $N$ that appears in large-$N$ holography.

The symbol $\mathcal N$ in $\mathcal N=4$ counts supersymmetry in four-dimensional notation. It does **not** mean four colors. It means that the theory has four copies of the minimal four-dimensional supersymmetry algebra. Equivalently, it has

$$
16
$$

Poincaré supercharges. Because the theory is conformal, these are accompanied by another $16$ superconformal charges. Together with conformal symmetry and R-symmetry, they form the superconformal algebra

$$
\mathfrak{psu}(2,2|4).
$$

So the full phrase

$$
\mathcal N=4\; SU(N)\; \text{SYM}
$$

contains two different pieces of information: maximal supersymmetry and color rank $N$.

## Field content

The elementary fields form one adjoint vector multiplet. In four-dimensional language they are:

| Field | Number | Representation under $SU(N)$ | Simple meaning |
|---|---:|---|---|
| $A_\mu$ | $1$ gauge field | adjoint | Yang–Mills gauge field |
| $\Phi^I$, $I=1,\ldots,6$ | $6$ real scalars | adjoint | transverse D3-brane fluctuations |
| $\lambda^A_\alpha$, $A=1,\ldots,4$ | $4$ Weyl fermions | adjoint | superpartners |

More explicitly, the fields are matrices:

$$
A_\mu(x)=A_\mu^a(x)T^a,
\qquad
\Phi^I(x)=\Phi^{I,a}(x)T^a,
\qquad
\lambda^A_\alpha(x)=\lambda^{A,a}_\alpha(x)T^a,
$$

where $T^a$ are generators of $\mathfrak{su}(N)$ and

$$
a=1,\ldots,N^2-1.
$$

This adjoint matrix structure is the reason large-$N$ counting works so naturally. Every propagator carries two color lines, and gauge-invariant local operators are built by tracing matrix products.

The six scalars transform as the vector representation of

$$
SO(6)_R\simeq SU(4)_R,
$$

which is the R-symmetry of the theory. This symmetry will later become the isometry group of the $S^5$ in the bulk geometry.

## The action, at the level we need

Suppressing spinor indices and convention-dependent signs, the Euclidean action has the schematic form

$$
S_E
=
\frac{1}{g_{\mathrm{YM}}^2}
\int d^4x\, \operatorname{Tr}
\left[
\frac14 F_{\mu\nu}F_{\mu\nu}
+
\frac12 D_\mu\Phi^I D_\mu\Phi^I
+
\frac14\sum_{I,J}
[\Phi^I,\Phi^J]^\dagger[\Phi^I,\Phi^J]
+
\text{fermion kinetic terms}
+
\text{Yukawa terms}
\right]
+
i\frac{\theta}{8\pi^2}\int \operatorname{Tr} F\wedge F .
$$

The exact coefficients in the fermion and Yukawa terms are fixed by supersymmetry. The important structural points are:

1. all fields are adjoint-valued matrices;
2. all interactions are controlled by one gauge coupling $g_{\mathrm{YM}}$;
3. the scalar potential vanishes when the scalars commute;
4. the theory also has a topological theta angle $\theta$.

The field strength and covariant derivative are

$$
F_{\mu\nu}
=
\partial_\mu A_\nu-
\partial_\nu A_\mu+[A_\mu,A_\nu],
\qquad
D_\mu\Phi^I
=
\partial_\mu\Phi^I+[A_\mu,\Phi^I].
$$

For many holographic questions, one does not need the full component action. What matters is the symmetry, the matrix structure, the coupling dependence, and the operator content.

## Couplings and conformality

Four-dimensional Yang–Mills theory has a classically dimensionless coupling. In ordinary nonsupersymmetric Yang–Mills theory, quantum effects make the coupling run. In $\mathcal N=4$ SYM, the beta function vanishes exactly:

$$
\beta(g_{\mathrm{YM}})=0.
$$

Thus the theory is not merely scale invariant at tree level. It is an exact quantum conformal field theory.

The two parameters usually used in AdS/CFT are the complexified gauge coupling

$$
\tau_{\mathrm{YM}}
=
\frac{\theta}{2\pi}
+
\frac{4\pi i}{g_{\mathrm{YM}}^2},
$$

and the 't Hooft coupling

$$
\lambda=g_{\mathrm{YM}}^2N.
$$

The large-$N$ limit is taken with $\lambda$ held fixed:

$$
N\to\infty,
\qquad
\lambda=g_{\mathrm{YM}}^2N\;\text{fixed}.
$$

This is the limit in which planar diagrams dominate. In the canonical holographic example, the gravity description becomes weakly curved when

$$
\lambda\gg 1.
$$

This is one of the great inversions of AdS/CFT. Perturbative field theory is easy when $\lambda\ll 1$, but classical gravity is easy when $\lambda\gg 1$.

## The parameter map

For type IIB string theory on $\mathrm{AdS}_5\times S^5$, the standard relations are convention-dependent in factors of $2\pi$. A common convention gives

$$
g_{\mathrm{YM}}^2 = 4\pi g_s,
\qquad
L^4 = 4\pi g_s N\alpha'^2,
$$

and therefore

$$
\frac{L^4}{\alpha'^2}=\lambda.
$$

Here $L$ is the common radius of $\mathrm{AdS}_5$ and $S^5$, $g_s$ is the string coupling, and $\alpha'$ is the square of the string length.

The practical dictionary is:

$$
\lambda \gg 1
\quad\Longleftrightarrow\quad
L^2\gg \alpha'
\quad\Longleftrightarrow\quad
\text{small stringy curvature corrections},
$$

while

$$
N\gg 1
\quad\Longleftrightarrow\quad
\text{small bulk quantum corrections}.
$$

More precisely, the five-dimensional Newton constant satisfies

$$
\frac{L^3}{G_5}\sim N^2.
$$

This is the gravitational version of the fact that $\mathcal N=4$ SYM has order $N^2$ degrees of freedom.

## Symmetry matching

The symmetry matching is one of the cleanest pieces of evidence for the duality.

The conformal group of four-dimensional Minkowski space is

$$
SO(2,4),
$$

up to global and covering-group subtleties. The isometry group of $\mathrm{AdS}_5$ is also

$$
\operatorname{Isom}(\mathrm{AdS}_5)=SO(2,4).
$$

The R-symmetry group of $\mathcal N=4$ SYM is

$$
SO(6)_R\simeq SU(4)_R.
$$

The isometry group of the five-sphere is

$$
\operatorname{Isom}(S^5)=SO(6).
$$

Thus

$$
SO(2,4)\times SO(6)_R
$$

on the boundary matches

$$
\operatorname{Isom}(\mathrm{AdS}_5)\times \operatorname{Isom}(S^5)
$$

in the bulk.

Including supersymmetry, the full superconformal symmetry is

$$
PSU(2,2|4),
$$

which also appears as the symmetry supergroup of the maximally supersymmetric $\mathrm{AdS}_5\times S^5$ background.

This matching does not prove the duality, but it is too rigid to be accidental. It tells us that if a four-dimensional CFT is going to be dual to type IIB string theory on $\mathrm{AdS}_5\times S^5$, $\mathcal N=4$ SYM has exactly the right symmetry structure.

## Gauge group: $U(N)$ or $SU(N)$?

D3-branes naturally produce a $U(N)$ gauge theory. At low energies,

$$
U(N)\simeq \frac{SU(N)\times U(1)}{\mathbb Z_N}.
$$

The overall $U(1)$ describes the free center-of-mass motion of the stack of branes. It decouples from the interacting $SU(N)$ sector.

For the interacting AdS/CFT duality, one usually writes

$$
\mathcal N=4\; SU(N)\; \text{SYM}.
$$

At large $N$, the distinction between $U(N)$ and $SU(N)$ is often subleading for single-trace observables, but conceptually the distinction is useful. The $SU(N)$ theory is the interacting CFT of interest; the decoupled $U(1)$ is not responsible for the curved $\mathrm{AdS}_5\times S^5$ bulk.

## Gauge-invariant observables

The elementary fields $A_\mu$, $\Phi^I$, and $\lambda^A$ are not gauge-invariant local observables. Physical local operators must be gauge invariant.

The simplest local examples are traces:

$$
\operatorname{Tr}(\Phi^{I_1}\Phi^{I_2}\cdots \Phi^{I_J})(x),
$$

or operators containing fermions, field strengths, and covariant derivatives:

$$
\operatorname{Tr}\!\big(F_{\mu\nu}D_\rho\Phi^I\lambda^A\cdots\big)(x).
$$

In a conformal theory, one should choose linear combinations that diagonalize the dilatation operator. The cleanest AdS/CFT statement is therefore:

$$
\text{single-trace conformal primary operator}
\quad\longleftrightarrow\quad
\text{single-particle bulk state}.
$$

Some basic examples are:

| Boundary object | Bulk object |
|---|---|
| stress tensor $T_{\mu\nu}$ | graviton in $\mathrm{AdS}_5$ |
| R-current $J^\mu_{R}$ | gauge field from $S^5$ isometries |
| $\operatorname{Tr}F^2$ | dilaton-like mode |
| $\operatorname{Tr}F\widetilde F$ | axion-like mode |
| half-BPS scalar bilinears | Kaluza–Klein supergravity modes on $S^5$ |
| Wilson loop | fundamental string worldsheet ending on the boundary |

A particularly important family of protected scalar operators is the symmetric traceless combination

$$
\mathcal O^{IJ}(x)
=
\operatorname{Tr}\left(
\Phi^I\Phi^J-\frac{1}{6}\delta^{IJ}\Phi^K\Phi^K
\right)(x),
$$

which has protected dimension

$$
\Delta=2.
$$

These operators live in the $\mathbf{20'}$ representation of $SO(6)_R$ and belong to the stress-tensor multiplet. They are among the first nontrivial single-trace operators one meets in the canonical dictionary.

## Protected and unprotected operators

Supersymmetry does not make the theory trivial. It makes some quantities protected.

A **protected** operator has a scaling dimension or correlation-function coefficient constrained by supersymmetry. For example, many BPS operators have dimensions that do not depend on $\lambda$.

An **unprotected** operator can acquire a nontrivial anomalous dimension. A famous example is the Konishi operator, schematically

$$
\mathcal O_K = \operatorname{Tr}(\Phi^I\Phi^I).
$$

At weak coupling it is a simple scalar bilinear. At strong coupling its dimension grows, and it is associated not with a light supergravity field but with a massive stringy excitation.

This distinction is crucial. The low-energy supergravity limit does not keep every single-trace operator light. It keeps operators dual to light bulk fields. Generic stringy operators become heavy when $\lambda\gg 1$.

This is the field-theory meaning of the separation between the supergravity spectrum and the full string spectrum.

## Central charges and the number of degrees of freedom

In four-dimensional CFTs, the stress-tensor two-point function and the Weyl anomaly measure the number of degrees of freedom in a precise way. For $\mathcal N=4$ SYM with gauge algebra $\mathfrak{su}(N)$, the central charges are

$$
a=c=\frac{N^2-1}{4}
$$

in a standard normalization.

At large $N$,

$$
a\sim c\sim N^2.
$$

This is not a decorative fact. It is the boundary version of the bulk relation

$$
\frac{L^3}{G_5}\sim N^2.
$$

The larger $N$ is, the smaller the effective gravitational coupling is in AdS units. Large central charge on the boundary is the first sign that a semiclassical bulk description might exist.

But large central charge alone is not enough. A weakly curved local Einstein-gravity dual also requires a large gap to most higher-spin or stringy single-trace operators. In the canonical example, that large gap appears at strong 't Hooft coupling.

## The moduli space and the D3-brane picture

The scalar potential vanishes when the six scalar matrices commute:

$$
[\Phi^I,\Phi^J]=0.
$$

Commuting matrices can be diagonalized simultaneously. Their eigenvalues may be interpreted as positions of D3-branes in the six transverse directions:

$$
\Phi^I
\sim
\operatorname{diag}(x_1^I,x_2^I,\ldots,x_N^I).
$$

For the $U(N)$ theory, the classical moduli space is roughly

$$
\mathcal M_{U(N)}
=
\frac{(\mathbb R^6)^N}{S_N},
$$

where $S_N$ permutes identical branes. For $SU(N)$, the center-of-mass direction is removed:

$$
\sum_{a=1}^N x_a^I=0.
$$

The conformal vacuum dual to undeformed $\mathrm{AdS}_5\times S^5$ is the origin of this moduli space:

$$
x_1^I=x_2^I=\cdots=x_N^I=0.
$$

Moving onto the Coulomb branch separates the branes and changes the bulk geometry. That is a different state or vacuum of the same theory, not the maximally symmetric $\mathrm{AdS}_5\times S^5$ vacuum.

## Why the theory is called “maximally supersymmetric”

In four-dimensional interacting field theory with particles of spin at most one, $\mathcal N=4$ is the maximum amount of ordinary supersymmetry one can have without introducing gravity. More supersymmetry would force higher spins or gravity-like structures.

This maximal supersymmetry has several consequences:

- the field content is completely fixed once the gauge group is chosen;
- the interactions are fixed by the gauge coupling;
- the beta function vanishes;
- many operator dimensions and correlation functions are protected;
- the theory has a powerful superconformal symmetry.

For holography, maximal supersymmetry is both a blessing and a warning. It gives a beautifully controlled example, but it also makes the theory very different from QCD or condensed-matter systems. Many applications of holography deliberately break or reduce these symmetries.

## Why this theory is not QCD

$\mathcal N=4$ SYM is a gauge theory, but it is not a model of real-world strong interactions.

It is different from QCD in several obvious ways:

- it is conformal, so the coupling does not run;
- it has no confinement in its vacuum on $\mathbb R^{1,3}$;
- all elementary fields are adjoint-valued;
- it has six scalars and four Weyl fermions required by supersymmetry;
- it has exact supersymmetry;
- it has no fundamental quarks unless extra flavor sectors are added.

So why study it?

Because it is a controlled nonperturbative laboratory. It teaches us how gauge theories can encode gravity, how black holes can be described by ordinary quantum states, how geometry can emerge from matrix degrees of freedom, and how strong-coupling observables can sometimes be computed by classical gravitational methods.

The correct attitude is not “$\mathcal N=4$ SYM is QCD.” The correct attitude is “$\mathcal N=4$ SYM is the hydrogen atom of holography”: highly symmetric, not realistic, but structurally illuminating.

## The canonical dictionary for this page

The field-theory data of $\mathcal N=4$ SYM map to bulk data as follows:

| $\mathcal N=4$ SYM data | Type IIB on $\mathrm{AdS}_5\times S^5$ data |
|---|---|
| color rank $N$ | $N$ units of five-form flux through $S^5$ |
| $N^2$ degrees of freedom | $L^3/G_5\sim N^2$ |
| 't Hooft coupling $\lambda=g_{\mathrm{YM}}^2N$ | curvature radius in string units, $L^4/\alpha'^2\sim\lambda$ |
| complex coupling $\tau_{\mathrm{YM}}$ | type IIB axio-dilaton $C_0+ie^{-\phi}$ |
| conformal symmetry $SO(2,4)$ | isometry of $\mathrm{AdS}_5$ |
| R-symmetry $SO(6)_R$ | isometry of $S^5$ |
| single-trace primaries | single-particle bulk/string states |
| multi-trace operators | multiparticle bulk states |
| stress tensor $T_{\mu\nu}$ | graviton |
| R-current $J^\mu_R$ | gauge field from the compact space |

This table is the reason $\mathcal N=4$ SYM is the central example in a foundations course. Almost every later holographic dictionary entry is a generalization of one of these rows.

## Common confusions

### “$\mathcal N=4$ means $N=4$ colors.”

No. $\mathcal N=4$ counts supersymmetry. The color rank is the $N$ in $SU(N)$. The large-$N$ limit concerns the color rank, not the number of supersymmetries.

### “The elementary fields are the observables.”

Not as local gauge-invariant operators. The elementary fields are useful variables in the Lagrangian, but local physical operators must be gauge invariant, such as traces of products of fields.

### “Conformal means free.”

No. $\mathcal N=4$ SYM is conformal for every value of $g_{\mathrm{YM}}$, but it is generally interacting. Scaling dimensions of unprotected operators depend nontrivially on $\lambda$.

### “Supersymmetry means everything is protected.”

No. Supersymmetry protects special operators, especially BPS operators. Generic operators have anomalous dimensions.

### “The gravity limit is weak field-theory coupling.”

No. Classical weakly curved gravity corresponds to strong 't Hooft coupling:

$$
\lambda\gg 1.
$$

Weak field-theory perturbation theory corresponds to $\lambda\ll 1$, where the bulk string theory is highly curved in string units.

### “The $S^5$ is an extra arbitrary decoration.”

No. The $S^5$ is required by the R-symmetry and by the D3-brane construction. Its isometry group $SO(6)$ matches the $SO(6)_R$ symmetry rotating the six scalars.

### “The $U(1)$ from D3-branes should be part of the interacting dual.”

The overall $U(1)$ is free and describes center-of-mass motion of the brane stack. The interacting holographic CFT is usually the $SU(N)$ sector.

## Exercises

### Exercise 1: Count the adjoint degrees of freedom

For gauge group $SU(N)$, the adjoint representation has dimension $N^2-1$. Explain why the number of elementary field components in $\mathcal N=4$ SYM scales like $N^2$ at large $N$.

<details>
<summary><strong>Solution</strong></summary>

Each elementary field is adjoint-valued:

$$
X(x)=X^a(x)T^a,
\qquad
a=1,\ldots,N^2-1.
$$

Thus every species of field carries $N^2-1$ color components. Since the number of species is fixed as $N$ changes, the total number of elementary field components scales as

$$
N^2-1\sim N^2.
$$

This is the field-theory origin of the holographic scaling

$$
\frac{L^3}{G_5}\sim N^2.
$$

</details>

### Exercise 2: Why is $g_{\mathrm{YM}}$ dimensionless in four dimensions?

Use the Yang–Mills kinetic term

$$
\frac{1}{g_{\mathrm{YM}}^2}\int d^4x\, \operatorname{Tr}F_{\mu\nu}F^{\mu\nu}
$$

to determine the engineering dimension of $g_{\mathrm{YM}}$ in $d=4$.

<details>
<summary><strong>Solution</strong></summary>

In units with $\hbar=c=1$, the action is dimensionless and

$$
[d^4x]=-4.
$$

The gauge field has engineering dimension

$$
[A_\mu]=1,
$$

so the field strength has dimension

$$
[F_{\mu\nu}]=2.
$$

Therefore

$$
[F_{\mu\nu}F^{\mu\nu}]=4.
$$

The integral

$$
\int d^4x\, F_{\mu\nu}F^{\mu\nu}
$$

is dimensionless, so $g_{\mathrm{YM}}$ is also dimensionless in four dimensions.

This argument only shows classical scale invariance. In a generic four-dimensional gauge theory, quantum effects can still generate a beta function. The special fact about $\mathcal N=4$ SYM is that the beta function vanishes exactly.

</details>

### Exercise 3: Match $SO(6)_R$ to the bulk sphere

Why is the equality

$$
SO(6)_R \simeq \operatorname{Isom}(S^5)
$$

natural from the D3-brane viewpoint?

<details>
<summary><strong>Solution</strong></summary>

A D3-brane fills four spacetime directions and has six transverse directions in ten-dimensional flat space. The six scalar fields $\Phi^I$, $I=1,\ldots,6$, describe fluctuations of the brane in these transverse directions.

Rotations of the transverse $\mathbb R^6$ form the group $SO(6)$. In the worldvolume theory, this becomes the R-symmetry group rotating the six scalars:

$$
\Phi^I \to R^I{}_J \Phi^J,
\qquad
R\in SO(6).
$$

In the near-horizon geometry, the angular directions of the transverse $\mathbb R^6$ become an $S^5$. The isometry group of $S^5$ is also $SO(6)$. Thus the same transverse rotation symmetry appears as $SO(6)_R$ in the CFT and as $\operatorname{Isom}(S^5)$ in the bulk.

</details>

### Exercise 4: Identify the classical gravity regime

Suppose the canonical parameter map is written as

$$
\frac{L^4}{\alpha'^2}=\lambda,
\qquad
 g_s\sim \frac{\lambda}{N}.
$$

What conditions suppress stringy curvature corrections and string loop corrections?

<details>
<summary><strong>Solution</strong></summary>

Stringy curvature corrections are suppressed when the AdS radius is large compared with the string length:

$$
L^2\gg \alpha'.
$$

Using

$$
\frac{L^4}{\alpha'^2}=\lambda,
$$

this requires

$$
\lambda\gg 1.
$$

String loop corrections are suppressed when the string coupling is small. Since

$$
g_s\sim \frac{\lambda}{N},
$$

one sufficient condition is

$$
N\gg \lambda.
$$

In the usual holographic classical-gravity regime, one takes $N$ very large and $\lambda$ large, while keeping quantum-loop and $\alpha'$ corrections small. A common shorthand is

$$
N\gg 1,
\qquad
\lambda\gg 1,
$$

with the understanding that the precise suppression of string loops also depends on how $\lambda/N$ behaves.

</details>

### Exercise 5: Why are single traces natural?

Let $X$ be an adjoint scalar of $SU(N)$, so under a gauge transformation

$$
X\to UXU^{-1}.
$$

Show that $\operatorname{Tr}(X^J)$ is gauge invariant.

<details>
<summary><strong>Solution</strong></summary>

Under the gauge transformation,

$$
X^J\to (UXU^{-1})(UXU^{-1})\cdots(UXU^{-1})=UX^JU^{-1}.
$$

Taking the trace gives

$$
\operatorname{Tr}(X^J)\to \operatorname{Tr}(UX^JU^{-1}).
$$

Using cyclicity of the trace,

$$
\operatorname{Tr}(UX^JU^{-1})=\operatorname{Tr}(X^JU^{-1}U)=\operatorname{Tr}(X^J).
$$

Thus $\operatorname{Tr}(X^J)$ is gauge invariant. This is the basic reason single-trace operators are natural local operators in adjoint matrix gauge theories.

</details>

## Further reading

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- E. D'Hoker and D. Z. Freedman, [Supersymmetric Gauge Theories and the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0201253).
- S. Kovacs, [${\cal N}=4$ Supersymmetric Yang–Mills Theory and the AdS/SCFT Correspondence](https://arxiv.org/abs/hep-th/9908171).
- J. A. Minahan, [Review of AdS/CFT Integrability, Chapter I.1: Spin Chains in $\mathcal N=4$ Super Yang–Mills](https://arxiv.org/abs/1012.3983).
