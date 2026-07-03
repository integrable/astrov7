---
title: "Quantization of Couplings"
description: "Explains why coefficients of topological terms are often quantized or periodic, with examples from theta terms, Wess–Zumino terms, Chern–Simons terms, BF terms, and topological response."
sidebar:
  label: "Quantization of Couplings"
  order: 8
level: Advanced
status: "Polished draft"
source: "Topological terms and anomaly references; Witten on Chern–Simons and anomalies; Coleman on instantons; Srednicki §§93–94; Altland–Simons Ch. 8; Polyakov Chs. 4, 6, 7."
topics:
  - topological terms
  - coupling quantization
  - theta angles
  - Chern–Simons levels
  - Wess–Zumino terms
  - BF theory
  - large gauge transformations
canonicalTopics:
  - quantization-of-couplings
  - topological-coupling-lattice
  - theta-angle-periodicity
  - chern-simons-level-quantization
  - wess-zumino-level-quantization
researchStatus:
  established:
    - "Topological couplings are constrained by the requirement that the exponentiated path integral be globally well defined under large gauge transformations, changes of extension, and changes of patching data."
    - "The allowed coefficient lattice depends on the global form of the symmetry or gauge group, charge lattice, spin or Pin structure, boundaries, and background-field normalization."
  active:
    - "Modern refinements phrase topological couplings in differential cohomology, cobordism, invertible field theory, and generalized-symmetry language, especially for torsion, fermionic, crystalline, and non-invertible settings."
---

## Summary

Topological terms are special because their coefficients are not always ordinary continuous couplings. A quartic scalar coupling can be any small real number. A Yang–Mills gauge coupling can run continuously. By contrast, the coefficient of a Wess–Zumino term, a Chern–Simons term, or a compact BF term is often forced onto an integer lattice, while the coefficient of a theta term is often an angular variable.

The reason is not mysterious, but it is global. The path integral uses the exponentiated action,

$$
\exp(iS),
$$

not the action as an isolated real-valued functional. If a local formula for $S$ changes by $2\pi$ times an integer when we change gauge patches, choose a different extension, or apply a large gauge transformation, the quantum theory is unchanged. If it changes by anything else, the expression $e^{iS}$ is not well defined.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing compact fields and integral periods leading to theta angles, Chern–Simons levels, Wess–Zumino levels, BF levels, and spin or torsion refinements.](/figures/symmetry-anomalies-topology/topological-coupling-quantization.svg)

<figcaption>

Topological couplings are fixed by global consistency of $e^{iS}$, not by local equations of motion. Integral periods give periodic angles; secondary characteristic classes and extension ambiguities give integer levels; spin, boundary, torsion, and global-form data refine the allowed lattice.

</figcaption>
</figure>

The slogan is

$$
\text{quantization of topological couplings}
=
\text{single-valuedness of the quantum phase}.
$$

This page explains the mechanism once, because it reappears everywhere: theta angles, Wess–Zumino terms, Wess–Zumino–Witten levels, Chern–Simons levels, BF levels, topological response coefficients, anomaly counterterms, and symmetry protected phases.

## Prerequisites

Read [Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/), [Wess–Zumino Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-terms/), [Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/), [BF Theory Terms](/symmetry-anomalies-topology/topological-terms/bf-theory-terms/), and [Topological Response](/symmetry-anomalies-topology/topological-terms/topological-response/) first.

The background-field viewpoint from [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/) and the large-gauge discussion in [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/) are also useful.

## Core idea

A topological action often has a local-looking expression such as

$$
S_{\mathrm{top}}=\lambda\int_{M_d}\omega_d.
$$

The local expression hides a global question: what values can the integral take? If the normalized integral is an integer,

$$
\int_{M_d}\omega_d\in \mathbb Z,
$$

then the path-integral weight is

$$
\exp\!\left(i\lambda\int_{M_d}\omega_d\right).
$$

The shift

$$
\lambda\longmapsto \lambda+2\pi
$$

leaves the weight unchanged. In this case $\lambda$ is not quantized as an integer; it is periodic. This is the basic theta-angle situation.

Other topological terms are secondary. A Chern–Simons action, for example, is locally defined by a form whose exterior derivative is an integral characteristic class:

$$
d\omega_{2n-1}=\operatorname{tr}(F^n).
$$

Under a large gauge transformation, the Chern–Simons functional itself can shift by an integer multiple of $2\pi$. If the action is $k$ times this functional, then

$$
e^{iS}\text{ is well defined}
\quad\Longrightarrow\quad
k\in\mathbb Z
$$

up to refinements from spin structure, global form, and charge lattice.

Thus there are two common outcomes:

$$
\begin{array}{c|c|c}
\text{kind of topological datum} & \text{typical coefficient} & \text{example} \\
\hline
\text{integer-valued topological charge} & \text{periodic angle} & \theta\int F\wedge F \\
\text{secondary or extension-dependent action} & \text{integer level} & k\,S_{\mathrm{CS}},\ k\,S_{\mathrm{WZ}} \\
\text{compact higher-form pairing} & \text{integer level} & \frac{k}{2\pi}\int B\wedge dA
\end{array}
$$

A useful mental picture is that topological actions are functions not only on local fields, but on global field configurations. The coefficient is allowed precisely when that function lands in $U(1)$ in a consistent way.

## Setup and conventions

We write Lorentzian path-integral weights as

$$
Z=\int \mathcal D\Phi\, e^{iS[\Phi]}.
$$

A shift

$$
S\longmapsto S+2\pi N,
\qquad N\in\mathbb Z,
$$

does not change $e^{iS}$. In Euclidean signature, the same data are often written as phases inside $e^{-S_E}$, so factors of $i$ may move between the action and the exponent.

For compact $U(1)$ gauge fields we use the standard period normalization

$$
\frac{1}{2\pi}\int_\Sigma F\in\mathbb Z
$$

on every closed two-cycle $\Sigma$. For nonabelian gauge fields we use Hermitian generators and

$$
D=d-iA,
\qquad
F=dA-iA\wedge A.
$$

With $G=SU(N)$ and trace in the fundamental representation normalized by

$$
\operatorname{tr}(T_aT_b)=\frac{1}{2}\delta_{ab},
$$

the second Chern number is

$$
Q=\frac{1}{8\pi^2}\int_{M_4}\operatorname{tr}(F\wedge F)
\in\mathbb Z
$$

for an $SU(N)$ bundle on a closed four-manifold. Other global forms, such as $PSU(N)=SU(N)/\mathbb Z_N$, allow additional bundles and can modify the possible values of $Q$. That is not a small-print issue; it changes the allowed counterterms and periodicities.

:::note[Convention-sensitive source note]
Many books use anti-Hermitian gauge fields, mostly-plus metric, or Euclidean actions. The integer statement is invariant, but the local formula can differ by signs and factors of $i$. The safe comparison method is to identify the normalized topological charge first, then read off the coefficient multiplying it in $e^{iS}$.
:::

## Quantization versus periodicity

The most common trap is to mix up two statements:

$$
\theta\sim \theta+2\pi,
\qquad
k\in\mathbb Z.
$$

They look similar because both involve integers, but they mean different things.

A theta term has the form

$$
S_\theta=\theta Q,
\qquad Q\in\mathbb Z.
$$

Then

$$
e^{iS_\theta}=e^{i\theta Q}
$$

is unchanged under $\theta\mapsto\theta+2\pi$. The coefficient is an angle:

$$
\theta\in\mathbb R/2\pi\mathbb Z.
$$

By contrast, a Chern–Simons term is not usually a globally invariant real number before exponentiation. Under a large gauge transformation $g$ with winding number $\nu(g)$,

$$
S_{\mathrm{CS}}[A^g]-S_{\mathrm{CS}}[A]
=2\pi k\,\nu(g).
$$

For $e^{iS_{\mathrm{CS}}}$ to be gauge invariant for every allowed $g$, we need

$$
k\in\mathbb Z.
$$

So theta terms usually give periodic parameters; Chern–Simons and Wess–Zumino terms usually give quantized levels. Both facts come from the same rule: $e^{iS}$ must be unambiguous.

## The normalization test

To decide whether a topological coefficient is allowed, use this five-step test.

First, identify the compact fields and their allowed global configurations. A one-form $A$ is not just a local differential form if it is a compact $U(1)$ connection; it also has flux sectors, holonomies, and transition functions.

Second, normalize the topological density so that it integrates to integers on closed manifolds. For example,

$$
\frac{1}{8\pi^2}\int\operatorname{tr}(F\wedge F)\in\mathbb Z
$$

for an $SU(N)$ bundle in the above trace convention.

Third, check whether the action is a primary topological charge or a secondary expression. Primary charges are globally defined integers. Secondary expressions, such as Chern–Simons forms, can shift under changes of gauge or extension.

Fourth, demand that the exponentiated action be independent of all unphysical choices:

$$
\text{patches},\quad \text{extensions},\quad \text{trivializations},\quad \text{large gauge transformations}.
$$

Fifth, state the background structure. The coefficient lattice can depend on whether the theory is bosonic or fermionic, whether the manifold is oriented, spin, or Pin, whether the field is a background or dynamical gauge field, and whether boundaries are allowed.

A one-line formula without these choices is often not a complete definition of a topological term.

## Theta terms

A theta term multiplies an integer-valued topological charge. In four-dimensional Yang–Mills theory with gauge group $SU(N)$,

$$
S_\theta
=\theta Q,
\qquad
Q=\frac{1}{8\pi^2}\int_{M_4}\operatorname{tr}(F\wedge F)\in\mathbb Z.
$$

The partition function decomposes schematically as

$$
Z(\theta)=\sum_{Q\in\mathbb Z} e^{i\theta Q}Z_Q.
$$

Therefore

$$
Z(\theta+2\pi)=Z(\theta).
$$

The same structure appears in the two-dimensional $O(3)$ nonlinear sigma model. A field $\mathbf n:M_2\to S^2$ has winding number

$$
Q=\frac{1}{4\pi}\int_{M_2}\mathbf n\cdot
(\partial_1\mathbf n\times \partial_2\mathbf n)\,d^2x
\in\mathbb Z,
$$

and the theta term $S_\theta=\theta Q$ has $\theta\sim\theta+2\pi$.

The word “integer” here is doing a lot. If the allowed field configurations are enlarged, the topological charge may become fractional. That happens, for example, when one changes the global form of the gauge group or turns on certain background fields. Then the apparent $2\pi$ periodicity may be modified or restored only after shifting an additional discrete counterterm.

## Wess–Zumino terms

A Wess–Zumino term is often defined by extending a field from spacetime $M_d$ to a bounding manifold $B_{d+1}$:

$$
\partial B_{d+1}=M_d.
$$

Let $\phi:M_d\to X$ be the physical field and let $\widetilde\phi:B_{d+1}\to X$ be an extension. Given a closed $(d+1)$-form $H$ on $X$, define

$$
S_{\mathrm{WZ}}
=\kappa\int_{B_{d+1}}\widetilde\phi^*H.
$$

This formula is useful only if the result does not depend on the arbitrary extension. Two different extensions glue to a closed $(d+1)$-manifold $Y_{d+1}$. The ambiguity is

$$
\Delta S_{\mathrm{WZ}}
=\kappa\int_{Y_{d+1}}\Phi^*H.
$$

If $H$ is normalized so that

$$
\frac{1}{2\pi}\int_{Y_{d+1}}\Phi^*H\in\mathbb Z,
$$

then $e^{iS_{\mathrm{WZ}}}$ is independent of the extension when

$$
\kappa\in\mathbb Z.
$$

This is the same logic as Chern–Simons level quantization, but the unphysical choice is now an extension rather than a gauge trivialization.

A useful baby example is a spin $s$ particle whose path traces a curve $\mathbf n(t)$ on $S^2$. The Berry/Wess–Zumino term is proportional to the area swept out on the sphere. Since the full sphere has area $4\pi$, the ambiguity in the phase requires

$$
2s\in\mathbb Z.
$$

Thus the quantization of spin is another face of the same global consistency rule.

## Wess–Zumino–Witten levels

For a two-dimensional Wess–Zumino–Witten model with field $g:M_2\to G$, the WZ term is commonly written

$$
S_{\mathrm{WZ}}
=\frac{k}{12\pi}\int_{B_3}\operatorname{tr}\!\left(g^{-1}dg\right)^3,
\qquad
\partial B_3=M_2.
$$

With the trace normalized so that the integral over a generator of $\pi_3(G)$ gives $2\pi$ times an integer, extension independence requires

$$
k\in\mathbb Z.
$$

This integer is the WZW level. It controls the affine current algebra, the allowed representations in rational examples, and the anomaly matched by the WZW term.

This is a good example of why normalization matters. If a reference rescales the trace, it also rescales the symbol called $k$. The physical statement is not that a particular printed coefficient is holy. The physical statement is that the coefficient multiplying the generator of the integral cohomology class is integral.

## Chern–Simons levels

For a compact gauge group $G$ in three dimensions, the nonabelian Chern–Simons action in the Hermitian convention used in this volume is

$$
S_{\mathrm{CS}}[A]
=\frac{k}{4\pi}\int_{M_3}
\operatorname{tr}\!\left(A\wedge dA-\frac{2i}{3}A\wedge A\wedge A\right).
$$

The exterior derivative of the Chern–Simons form is

$$
d\omega_3(A)=\operatorname{tr}(F\wedge F).
$$

Under a large gauge transformation,

$$
A\longmapsto A^g=gAg^{-1}+i\,g\,dg^{-1},
$$

the action shifts by

$$
S_{\mathrm{CS}}[A^g]-S_{\mathrm{CS}}[A]
=2\pi k\,\nu(g),
\qquad
\nu(g)\in\mathbb Z.
$$

Hence the quantum theory requires

$$
k\in\mathbb Z.
$$

For abelian Chern–Simons theories, a common multicomponent local expression is

$$
S_K=\frac{1}{4\pi}\int K_{IJ}A^I\wedge dA^J.
$$

The matrix $K$ must be integral in a compact theory. Additional parity conditions can appear depending on whether the theory is a bosonic theory on oriented manifolds, a spin theory, or a response theory built from spin or spin$_c$ backgrounds. In condensed-matter language, these refinements distinguish bosonic, fermionic, and spin-dependent topological responses.

:::note[Convention-sensitive source note]
Some references state the abelian Chern–Simons quantization rule directly for the $K$-matrix. Others state it as a condition on the quadratic refinement of a charge lattice. These are the same issue in different language: the exponentiated action must be well defined on all allowed bundles and manifolds.
:::

## BF levels

For compact higher-form gauge fields $A_p$ and $B_{d-p-1}$, the BF action is

$$
S_{\mathrm{BF}}
=\frac{k}{2\pi}\int_{M_d}B\wedge dA.
$$

With the compact normalization

$$
\frac{1}{2\pi}\int dA\in\mathbb Z,
\qquad
\frac{1}{2\pi}\int dB\in\mathbb Z,
$$

large higher-form gauge transformations require

$$
k\in\mathbb Z.
$$

A quick two-dimensional version makes the logic vivid. Let $\phi$ be a compact scalar with

$$
\phi\sim \phi+2\pi
$$

and let $A$ be a compact $U(1)$ gauge field on a closed two-manifold. The term

$$
S=\frac{k}{2\pi}\int_{M_2}\phi F
$$

changes under $\phi\to\phi+2\pi$ by

$$
\Delta S=k\int_{M_2}F=2\pi k n,
\qquad n\in\mathbb Z.
$$

So $e^{iS}$ is invariant for all flux sectors only if $k\in\mathbb Z$. The same calculation is the seed of the higher-form BF quantization rule.

## Topological response coefficients

Topological response terms are topological actions for background fields. Because the fields are backgrounds, one might be tempted to ignore coefficient quantization. That temptation is dangerous.

A background field is not integrated over, but the generating functional

$$
Z[A]
$$

must still be a well-defined functional of the allowed background. If the background is a compact gauge field, one must allow nontrivial bundles and large gauge transformations. Therefore counterterms and response coefficients are still constrained.

For example, in three dimensions an electromagnetic Hall response is written

$$
W_{\mathrm{Hall}}[A]
=\frac{\nu}{4\pi}\int A\wedge dA.
$$

The allowed values of $\nu$ depend on what kind of microscopic system and background are being described. An integer quantum Hall state of fermions, a bosonic integer quantum Hall state, and a fractional Hall state with emergent dynamical gauge fields do not have identical coefficient rules. The local expression $A\wedge dA$ is the start of the analysis, not the end.

Similarly, in four-dimensional time-reversal-invariant electronic topological insulators one writes an electromagnetic theta response

$$
W_\theta[A]
=\frac{\theta}{8\pi^2}\int F\wedge F.
$$

The familiar values $\theta=0$ and $\theta=\pi$ rely on time reversal and on the spin or spin$_c$ structure appropriate for electrons. Without saying what backgrounds are allowed, the statement is incomplete.

## Torsion, spin, and global-form refinements

Differential-form formulas see the de Rham part of topology. They can miss torsion. A finite symmetry background, a flat discrete gauge field, or a torsion characteristic class can support topological terms whose local differential-form representative is zero. Such terms are still physical.

This is why modern treatments often formulate topological actions as elements of groups such as

$$
H^{d+1}(BG,U(1)),
$$

for finite bosonic symmetry protected phases, or in cobordism and differential cohomology for fermionic, gravitational, and continuous-symmetry systems. The point is not to replace all physics pages by algebraic topology. The point is to know when a local formula is only a chart on a more global object.

Spin structure can also refine the coefficient lattice. Some terms are well defined on every oriented manifold. Others are defined only after choosing a spin, Pin, or spin$_c$ structure. This is why parity anomalies, fermionic topological phases, gravitational Chern–Simons terms, and eta-invariant refinements need special care.

The global form of a group matters too. The Lie algebras of $SU(N)$ and $PSU(N)$ are the same, but their bundles are not. A topological charge that is integral for $SU(N)$ bundles can be fractional for $PSU(N)$ bundles. Consequently, the periodicity of theta angles and the allowed discrete theta terms can differ.

## Boundaries and anomaly inflow

On a manifold with boundary, even a properly quantized bulk topological term can fail to be gauge invariant by itself. The variation may be a boundary term:

$$
\delta S_{\mathrm{bulk}}= -\delta S_{\partial M}.
$$

Then there are two consistent possibilities.

One can impose boundary conditions that remove the offending variation. Or one can add boundary degrees of freedom whose anomaly cancels it. This is anomaly inflow.

Chern–Simons theory is the classic example: on a closed three-manifold, integer level makes $e^{iS_{\mathrm{CS}}}$ gauge invariant. On a three-manifold with boundary, gauge variation produces a boundary term. A chiral WZW model or another suitable boundary theory can carry the compensating anomaly.

This distinction is crucial: coefficient quantization handles large-gauge consistency in the bulk, while boundary gauge variation diagnoses anomaly inflow and edge physics.

## A compact dictionary

The following table is a practical lookup, not a substitute for checking global hypotheses.

$$
\begin{array}{c|c|c|c}
\text{term} & \text{typical normalized datum} & \text{coefficient} & \text{main caveat} \\
\hline
\theta\text{ term} & Q\in\mathbb Z & \theta\sim\theta+2\pi & \text{global form can fractionalize }Q \\
\text{WZ term} & \frac{1}{2\pi}\int H\in\mathbb Z & k\in\mathbb Z & \text{extension and target normalization} \\
\text{WZW term} & \pi_3(G)\simeq\mathbb Z & k\in\mathbb Z & \text{trace convention and global }G \\
\text{Chern--Simons} & \nu(g)\in\mathbb Z & k\in\mathbb Z & \text{spin, framing, charge lattice} \\
\text{BF term} & \frac{1}{2\pi}\int F\in\mathbb Z & k\in\mathbb Z & \text{compactness and higher-form periods} \\
\text{finite response} & \text{group cocycle} & U(1)\text{-valued class} & \text{torsion invisible to forms}
\end{array}
$$

The table also explains why topological terms are a convention minefield. A different normalization of $Q$, $H$, or $\operatorname{tr}$ changes the printed coefficient, but not the underlying integrality rule.

## Common pitfalls

**“It is a total derivative, so its coefficient is arbitrary.”** Locally exact terms can still detect global sectors, boundaries, and patching data. Total derivative does not mean physically irrelevant.

**“Quantized coupling means every topological coefficient is an integer.”** Theta angles are periodic real parameters, not integer parameters. Levels such as $k$ in Chern–Simons, BF, and WZW terms are typically integer-valued.

**“Large gauge transformations matter only for dynamical gauge fields.”** Background generating functionals must also be well defined under allowed background gauge transformations. Otherwise the theory has an anomaly or requires an inflow bulk.

**“The local differential form tells the whole story.”** Torsion terms, finite-symmetry responses, spin refinements, and global-form effects can be invisible in de Rham notation.

**“The coefficient lattice is universal.”** It depends on the global form of the group, charge lattice, allowed manifolds, spin or Pin structure, boundary conditions, and whether the term is a standalone action or a response action.

## Relations to other pages

This page is the global-consistency companion to [Total Derivatives That Matter](/symmetry-anomalies-topology/topological-terms/total-derivatives-that-matter/). The next page, [Periodicity and Large Gauge Transformations](/symmetry-anomalies-topology/topological-terms/periodicity-and-large-gauge-transformations/), focuses on the transformations that generate many of these identifications.

For the main examples, see [Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/), [Wess–Zumino Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-terms/), [Wess–Zumino–Witten Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-witten-terms/), [Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/), and [BF Theory Terms](/symmetry-anomalies-topology/topological-terms/bf-theory-terms/).

For anomaly applications, see [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/) and [Anomalies and Symmetry-Protected Phases](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-and-symmetry-protected-phases/).

## Research status

The basic mechanism of coefficient quantization is established. It is one of the most reliable pieces of global QFT reasoning.

The active frontier is classification and refinement. Modern work asks how to classify all allowed topological response terms for a given symmetry, spacetime structure, charge lattice, defect category, and anomaly. Differential cohomology controls continuous gauge fields with integral periods; group cohomology captures many finite bosonic responses; spin and Pin cobordism capture many fermionic and reflection/time-reversal refinements; symmetry TFT and higher-categorical language organize generalized-symmetry versions.

For most physics calculations, the practical rule remains simple: normalize the topological charge, then demand that $e^{iS}$ survive every unphysical choice.

## Exercises

### Exercise 1: Theta periodicity

Suppose a theory has topological sectors labeled by $Q\in\mathbb Z$ and partition function

$$
Z(\theta)=\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q.
$$

Show that $Z(\theta+2\pi)=Z(\theta)$.

<details><summary><strong>Solution</strong></summary>

Use $Q\in\mathbb Z$:

$$
e^{i(\theta+2\pi)Q}=e^{i\theta Q}e^{2\pi iQ}=e^{i\theta Q}.
$$

Therefore every term in the sector sum is unchanged, so

$$
Z(\theta+2\pi)=Z(\theta).
$$

</details>

### Exercise 2: Compact scalar BF quantization in two dimensions

Let $\phi\sim\phi+2\pi$ and let $A$ be a compact $U(1)$ gauge field on a closed two-manifold, with

$$
\frac{1}{2\pi}\int F=n\in\mathbb Z.
$$

Consider

$$
S=\frac{k}{2\pi}\int \phi F.
$$

Show that invariance under $\phi\to\phi+2\pi$ requires $k\in\mathbb Z$.

<details><summary><strong>Solution</strong></summary>

The shift gives

$$
\Delta S=\frac{k}{2\pi}\int 2\pi F=k\int F=2\pi k n.
$$

The phase $e^{iS}$ is invariant for every integer flux $n$ iff

$$
e^{2\pi i k n}=1
$$

for all $n\in\mathbb Z$. Taking $n=1$ gives $k\in\mathbb Z$.

</details>

### Exercise 3: Wess–Zumino extension ambiguity

Let $H$ be normalized so that

$$
\frac{1}{2\pi}\int_Y \Phi^*H\in\mathbb Z
$$

for every closed $(d+1)$-manifold $Y$ and map $\Phi:Y\to X$. Show that

$$
S_{\mathrm{WZ}}=k\int_B\widetilde\phi^*H
$$

is independent of the choice of extension in the exponentiated path integral if $k\in\mathbb Z$.

<details><summary><strong>Solution</strong></summary>

Two extensions glue to a closed manifold $Y$. Their actions differ by

$$
\Delta S=k\int_Y\Phi^*H.
$$

By normalization, $\int_Y\Phi^*H=2\pi m$ with $m\in\mathbb Z$. Hence

$$
\Delta S=2\pi km.
$$

If $k\in\mathbb Z$, then $e^{i\Delta S}=1$, so $e^{iS_{\mathrm{WZ}}}$ does not depend on the extension.

</details>

### Exercise 4: Counterterms and anomaly classes

Suppose two background effective actions differ by a local topological counterterm whose coefficient is allowed by the quantization rules. Explain why this can change the displayed anomaly representative but not remove a nontrivial anomaly class.

<details><summary><strong>Solution</strong></summary>

Adding a local counterterm changes the definition of the generating functional by a well-defined local phase. Its variation can move anomaly terms between different currents or different background-field components. This changes the representative of the anomaly.

However, if the anomaly class is nontrivial, no allowed local counterterm has exactly the variation needed to cancel it globally. Otherwise the anomalous generating functional would become gauge invariant and the class would have been trivial. Thus counterterms change representatives, not the cohomology class.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially “The Uses of Instantons,” for theta vacua and global topological sectors.
- Mark Srednicki, *Quantum Field Theory*, §§93–94, for instantons, theta vacua, and quark-theta physics.
- A. M. Polyakov, *Gauge Fields and Strings*, Chs. 4, 6, and 7, for compact gauge fields, instantons, topology of gauge fields, and loop dynamics.
- Edward Witten, “Quantum Field Theory and the Jones Polynomial,” *Communications in Mathematical Physics* **121** (1989), for Chern–Simons level quantization and the TQFT viewpoint.
- Edward Witten, “Global Aspects of Current Algebra,” *Nuclear Physics B* **223** (1983), for Wess–Zumino terms, WZW levels, and global consistency.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, Ch. 8, for theta, Wess–Zumino, and Chern–Simons terms in matter-oriented field theory.
- Daniel S. Freed, “Classical Chern–Simons Theory,” for a mathematical treatment of global Chern–Simons actions.
- Edward Witten, “Fermion Path Integrals and Topological Phases,” *Reviews of Modern Physics* **88** (2016), for spin, eta-invariant, and fermionic refinements.

## Version history

- 2026-06-18: Initial polished draft for the improved Symmetry, Anomalies, and Topology plan.
