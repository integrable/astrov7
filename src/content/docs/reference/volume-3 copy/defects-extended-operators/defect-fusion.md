---
title: "Defect Fusion"
description: "Explains how extended operators and defects are brought together, when fusion is topological, and why fusion is the doorway from defects to generalized and categorical symmetry."
sidebar:
  label: "Defect Fusion"
  order: 9
level: Advanced
status: "Polished draft"
source: "Wilson; Polyakov Ch. 7; Gaiotto–Kapustin–Seiberg–Willett; standard TQFT and defect-CFT references."
topics:
  - defect fusion
  - topological defects
  - extended operators
  - non-invertible symmetry
  - categorical symmetry
canonicalTopics:
  - defect-fusion
  - topological-defect
  - non-invertible-fusion
  - categorical-symmetry
researchStatus:
  established:
    - "Fusion of topological line, surface, wall, and interface operators is standard in TQFT, CFT, lattice/statistical models, and generalized-symmetry language."
    - "Group-like symmetry defects fuse by group multiplication; more general topological defects can fuse into sums or categories of defects."
  active:
    - "Fusion in higher-dimensional, fermionic, non-invertible, anomalous, and symmetry-TFT settings is an active research area where conventions and mathematical language vary."
---

## Summary

**Defect fusion** is the operation of bringing two compatible defects close together and replacing them by an effective defect. If the defects are topological, this operation is often exact and independent of the distance between them. If the defects are not topological, fusion is usually an operator product expansion with singular coefficients, renormalization, and possible defect-local operators.

For two parallel or coincident topological defects $\mathcal D_a$ and $\mathcal D_b$, the schematic fusion rule is

$$
\mathcal D_a\times \mathcal D_b
\simeq
\sum_c N_{ab}{}^c\,\mathcal D_c.
$$

The simplest case is an ordinary invertible symmetry. If $U_g$ and $U_h$ are topological symmetry defects for group elements $g,h\in G$, then

$$
U_g\times U_h=U_{gh}.
$$

The modern surprise is that topological defects need not be invertible. They can fuse into a sum rather than a single defect. That is the first glimpse of categorical symmetry.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Two nearby topological defects are moved together and replaced by a sum of effective defects, illustrating defect fusion.](/figures/symmetry-anomalies-topology/defect-fusion-schematic.svg)

<figcaption>

Fusion means shrinking the separation between compatible defects. For topological defects the result depends only on the topological class of the configuration, not on the microscopic distance used during the limiting process.

</figcaption>
</figure>

The key lesson is:

$$
\text{defect fusion is the operator product expansion for extended operators}.
$$

For ordinary symmetries it recovers group multiplication. For Wilson lines it recovers representation-theoretic tensor products in suitable limits. For non-invertible symmetries it becomes the algebraic structure that replaces a group.

## Prerequisites

You should know [Local Versus Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/local-versus-extended-operators/), [Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/), [’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/), [Surface Operators](/symmetry-anomalies-topology/defects-extended-operators/surface-operators/), and [Twist Operators](/symmetry-anomalies-topology/defects-extended-operators/twist-operators/).

It also helps to know the topological-operator viewpoint on ordinary symmetry: a symmetry operator can be deformed freely until it crosses a charged insertion. Higher-form and non-invertible chapters will generalize this idea; here we explain the fusion operation itself.

## Core idea

Suppose $\mathcal D_1(M_p)$ and $\mathcal D_2(M_p)$ are two $p$-dimensional defects supported on nearby submanifolds in a $d$-dimensional spacetime. Choose a small normal separation $\epsilon$. Fusion asks whether the composite insertion

$$
\mathcal D_1(M_p+\epsilon n)\,\mathcal D_2(M_p)
$$

has a controlled limit as $\epsilon\to0$.

For ordinary local operators, this limiting question gives the local OPE:

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ij}{}^k(x)\mathcal O_k(0).
$$

For extended operators, the same idea gives a **defect OPE** or **defect fusion rule**:

$$
\mathcal D_a(M+\epsilon n)\mathcal D_b(M)
\sim
\sum_c C_{ab}{}^c(\epsilon)\,\mathcal D_c(M)
+\text{defect-local descendants}.
$$

If the defects are topological and no relevant defect-local data are generated, the coefficient becomes a topological number or finite-dimensional vector-space data rather than a function of distance. In that case one writes a clean fusion rule

$$
\mathcal D_a\times\mathcal D_b=\sum_c N_{ab}{}^c\,\mathcal D_c.
$$

The coefficients $N_{ab}{}^c$ are often nonnegative integers in semisimple bosonic examples, but this innocent-looking statement hides assumptions. Fermionic defects, nonsemisimple categories, boundary conditions, noncompact theories, and anomalous systems require more careful language.

## Setup and conventions

A defect supported on a submanifold $M_p$ is denoted $\mathcal D(M_p)$. Its codimension is

$$
r=d-p.
$$

Fusion usually requires the defects to have compatible support dimension and compatible normal framing. A **framing** is a choice of how the defect is thickened or displaced in the normal directions. Framing can be invisible in elementary examples and crucial in Chern–Simons theory, fermionic theories, and self-linking computations.

The product symbol $\times$ denotes fusion, not necessarily ordinary multiplication of numbers. If defects are linearly combined, the sum means that correlation functions with the fused insertion equal the corresponding sum of correlation functions:

$$
\left\langle
\left(\sum_c N_{ab}{}^c\mathcal D_c\right)\cdots
\right\rangle
=
\sum_c N_{ab}{}^c
\left\langle
\mathcal D_c\cdots
\right\rangle.
$$

Orientation matters. Reversing the orientation of a defect may produce an inverse, a dual defect, a conjugate representation, or something more subtle depending on the theory.

:::note[Source note]
The notation $\mathcal D_a\times\mathcal D_b=\sum_cN_{ab}{}^c\mathcal D_c$ is deliberately schematic. It is perfect for first-pass intuition, but advanced treatments replace it by a statement about categories, functors, junction spaces, or state spaces assigned to small spheres linking the fused configuration.
:::

## Group-like symmetry defects

For an ordinary finite or compact internal symmetry group $G$, the topological symmetry defect $U_g$ implements $g\in G$. Fusion is just group multiplication:

$$
U_g\times U_h=U_{gh}.
$$

The identity defect is

$$
U_e=1,
$$

and the inverse is

$$
U_g^{-1}=U_{g^{-1}}.
$$

This is the cleanest possible fusion law. If a defect $U_g$ crosses a charged local operator $\mathcal O$, it transforms it:

$$
U_g\text{ crossing }\mathcal O
\quad\leadsto\quad
g\cdot\mathcal O.
$$

Fusing $U_g$ and $U_h$ before crossing $\mathcal O$ gives the same result as crossing first with $U_h$ and then with $U_g$, up to the convention for ordering. The fusion rule is therefore the geometric version of the representation property of the symmetry action.

For a continuous symmetry, one often writes infinitesimal symmetry defects as exponentials of charge integrals. For an ordinary zero-form symmetry on a spatial slice,

$$
U(\alpha)=e^{-i\alpha^aQ_a}.
$$

The fusion of nearby constant-$\alpha$ and constant-$\beta$ defects gives the finite group product, while local variations of the parameter lead to current conservation and Ward identities.

## Non-invertible fusion

A defect is **invertible** if there is another defect $\mathcal D^{-1}$ such that

$$
\mathcal D\times\mathcal D^{-1}=1.
$$

A defect is **non-invertible** if no such inverse exists. Non-invertibility is not failure. It is extra structure.

A typical non-invertible fusion rule is

$$
\mathcal N_a\times\mathcal N_b
=
\sum_c N_{ab}{}^c\,\mathcal N_c.
$$

The right-hand side is a sum of possible defects rather than a single group element. This is the algebraic doorway to non-invertible symmetry. Instead of a group, one has a fusion category or a higher-categorical analogue, depending on dimension and defect codimension.

A famous two-dimensional example is the Kramers–Wannier duality defect of the critical Ising model. Its fusion with itself does not give only the identity defect; it produces a sum involving the identity and the spin-flip symmetry defect. The exact normalization and notation depend on the chosen convention, but the structural point is robust:

$$
\text{duality defect}\times\text{duality defect}
\quad\text{can be a sum of defects}.
$$

This is why non-invertible symmetry is not just a fancy name for an ordinary group.

## Fusion versus OPE

Fusion is often exact only for topological defects. For general defects, one should expect a defect OPE.

Imagine two line operators separated by a small transverse distance $\epsilon$. Their product may behave as

$$
L_a(C+\epsilon n)L_b(C)
\sim
\sum_c C_{ab}{}^c(\epsilon,\mu)\,L_c(C)
+\sum_{c,\hat{\mathcal O}} C_{ab}{}^{c,\hat{\mathcal O}}(\epsilon,\mu)
\int_C \hat{\mathcal O}_c\,L_c(C)+\cdots.
$$

Here $\hat{\mathcal O}_c$ denotes a defect-local operator living on the fused line. The coefficients can depend on the distance $\epsilon$, the renormalization scale $\mu$, and geometric data such as angles or curvature. Singular terms are common.

Topological fusion is the special case where these metric-dependent details drop out, or are controlled well enough that the result is a topological operation.

:::caution[Do not topologize too early]
Many useful Wilson loops, boundary conditions, interfaces, and disorder defects are not topological. They can still have fusion limits, but those limits may include divergences, RG flow, scheme dependence, and defect-local counterterms.
:::

## Wilson-line fusion and representation products

Wilson lines give a useful example where fusion is close to representation theory but not automatically topological.

For a gauge connection $A$, a Wilson line in representation $R$ is schematically

$$
W_R(C)=\operatorname{tr}_R\,P\exp\left(i\int_C A\right).
$$

If two Wilson lines run along the same curve, the product of holonomies naturally involves the tensor product of representations:

$$
\operatorname{tr}_{R_1}U(C)\,\operatorname{tr}_{R_2}U(C)
=
\operatorname{tr}_{R_1\otimes R_2}U(C).
$$

If

$$
R_1\otimes R_2=\bigoplus_R N_{R_1R_2}{}^R\,R,
$$

then formally

$$
W_{R_1}(C)W_{R_2}(C)
=
\sum_R N_{R_1R_2}{}^R\,W_R(C).
$$

In a genuine dynamical gauge theory, coincident line operators may require renormalization and regularization. In a topological gauge theory, such as Chern–Simons theory, this representation-theoretic statement becomes part of a richer topological line algebra, modified by quantum group effects, framing, and level-dependent truncation.

The moral is that fusion often starts as an intuitive tensor-product rule and becomes precise only after specifying the QFT, regulator, and defect class.

## Fusion of interfaces and boundaries

Interfaces can also fuse. Let $\mathcal I_{12}$ be an interface between theory $\mathcal T_1$ and theory $\mathcal T_2$, and let $\mathcal I_{23}$ be an interface between $\mathcal T_2$ and $\mathcal T_3$. Placing them close together gives an effective interface between $\mathcal T_1$ and $\mathcal T_3$:

$$
\mathcal I_{12}\times\mathcal I_{23}
\sim
\mathcal I_{13}^{\rm eff}.
$$

If the interfaces are topological, the result can be independent of separation. If they are not topological, the intermediate strip of theory $\mathcal T_2$ can have its own degrees of freedom, RG flow, and defect-local operators.

Boundaries are interfaces with the trivial theory on one side. Fusion of a boundary with an interface produces a new boundary condition. This point is central in boundary CFT, symmetry TFT, and duality-wall constructions.

The **folding trick** often helps: an interface between $\mathcal T_1$ and $\mathcal T_2$ can be viewed as a boundary condition for $\mathcal T_1\otimes\overline{\mathcal T}_2$. Fusion then becomes a boundary or interface operation in the folded theory.

## Junctions and associativity

Fusion is not only a multiplication table. Defects can meet at junctions. If three topological lines $a,b,c$ meet, the space of allowed junction operators may be a vector space

$$
V_{ab}{}^c.
$$

In simple semisimple examples,

$$
\dim V_{ab}{}^c=N_{ab}{}^c.
$$

Associativity of fusion is the statement that fusing three defects in different orders gives equivalent results:

$$
(\mathcal D_a\times\mathcal D_b)\times\mathcal D_c
\simeq
\mathcal D_a\times(\mathcal D_b\times\mathcal D_c).
$$

The equivalence between these two ways of fusing is not always trivial. It is encoded by associators, often called $F$-symbols in two-dimensional topological and conformal examples. Consistency of different fusion and junction moves leads to pentagon identities and, when braiding is present, additional hexagon-like constraints.

That is the point where defect fusion becomes categorical symmetry. This page only opens the door; the Non-Invertible and Categorical Symmetries chapter develops the language.

## Anomalies and obstruction to fusion

Fusion can fail to be strictly associative or strictly gauge invariant because of anomalies. For example, symmetry defects may be able to end only on certain boundary degrees of freedom, or may acquire phases under moves that would be trivial in an anomaly-free theory.

A ’t Hooft anomaly can be detected by trying to make symmetry defects fully topological and consistently fuseable in all backgrounds. If the rules require a one-higher-dimensional bulk term to be consistent, the anomaly is being expressed as inflow.

In practice, anomaly-sensitive fusion requires tracking:

- orientations;
- spin or Pin structures;
- background bundles;
- local counterterms;
- framing;
- junction phases;
- possible bulk terms.

This is one reason symmetry TFT is so useful: it packages defect fusion and anomaly inflow into a single topological bulk-boundary framework.

## Common pitfalls

**“Fusion always means multiplying two numbers.”** Defects are operators, boundary conditions, functors, or extended insertions. Fusion is an operation on those objects, not usually multiplication of scalar values.

**“Every fusion rule has integer coefficients.”** Many familiar semisimple topological examples do, but fermionic, nonsemisimple, noncompact, anomalous, and non-topological settings can require more refined data.

**“Fusion is always topological.”** Non-topological defects have OPE-like fusion with distance dependence, divergences, and defect-local operators.

**“Invertible defects are the only symmetries.”** That is true only for ordinary group-like symmetry. Modern QFT uses topological defects to define broader symmetry structures.

**“Wilson-line fusion is always just tensor products.”** Tensor products are the first guide. Dynamics, framing, screening, line endpoints, global form of the gauge group, and topological level can modify the precise operator algebra.

**“Associativity is automatic and trivial.”** Associativity is a consistency structure. In categorical settings it is implemented by specified isomorphisms satisfying identities, not by equality of strings on a page.

## Relations to other pages

[Symmetry Defects and Topological Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-defects-and-topological-operators/) explains the ordinary global-symmetry case where fusion is group multiplication. [Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/) and [’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/) provide the main gauge-theory examples.

[Defect Correlation Functions](/symmetry-anomalies-topology/defects-extended-operators/defect-correlation-functions/) explains how fused defects appear inside correlators, how defect-local operators enter, and why framing matters.

[Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) uses extended charged operators and topological symmetry operators. [Non-Invertible and Categorical Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/) turns fusion rules, junctions, and associators into the main language. [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) explains how anomalous fusion can be made consistent by a one-higher-dimensional bulk.

## Research status

The basic idea of fusing topological defects is established. It appears in TQFT, rational CFT, boundary and interface CFT, lattice/statistical models, gauge theory, and modern generalized symmetry.

The active frontier is the systematic use of defect fusion as the definition of symmetry beyond groups. This includes non-invertible symmetries in dimensions higher than two, fermionic and antiunitary refinements, nonsemisimple categories, higher categories of extended operators, symmetry TFT, and anomaly-sensitive fusion in QFTs with nontrivial background structures.

## Exercises

### Exercise 1: Group-like fusion

Let $U_g$ and $U_h$ be topological symmetry defects for an ordinary internal group $G$. Show that crossing a local operator $\mathcal O$ with the fused defect $U_g\times U_h$ gives the same result as acting by the product group element.

<details><summary><strong>Solution</strong></summary>

Crossing $\mathcal O$ with $U_h$ gives $h\cdot\mathcal O$. Crossing the result with $U_g$ gives

$$
g\cdot(h\cdot\mathcal O)=(gh)\cdot\mathcal O,
$$

with the ordering determined by the convention for which defect crosses first. The fused defect must therefore act as $U_{gh}$ on all charged operators. Since topological symmetry defects are determined by their action on the operator algebra, the fusion rule is

$$
U_g\times U_h=U_{gh}.
$$

</details>

### Exercise 2: Wilson-line tensor product

Suppose two Wilson lines in representations $R_1$ and $R_2$ run along the same curve $C$, and ignore regularization subtleties. Show that their product is naturally associated with $R_1\otimes R_2$.

<details><summary><strong>Solution</strong></summary>

Let $U(C)$ be the holonomy along $C$. The Wilson lines are

$$
W_{R_i}(C)=\operatorname{tr}_{R_i}U(C).
$$

The product is

$$
\operatorname{tr}_{R_1}U(C)\operatorname{tr}_{R_2}U(C)
=
\operatorname{tr}_{R_1\otimes R_2}(U(C)\otimes U(C)).
$$

This is the Wilson operator associated with the tensor-product representation. If

$$
R_1\otimes R_2=\bigoplus_R N_{R_1R_2}{}^R R,
$$

then the product decomposes into the corresponding sum of Wilson lines, up to the dynamical and regularization qualifications discussed in the page.

</details>

### Exercise 3: Non-invertibility test

A topological defect $\mathcal N$ obeys

$$
\mathcal N\times\mathcal N=1+\eta,
$$

where $\eta$ is a nontrivial invertible symmetry defect. Explain why $\mathcal N$ is not invertible.

<details><summary><strong>Solution</strong></summary>

If $\mathcal N$ were invertible, then fusing it with another defect $\mathcal N^{-1}$ would give the identity and fusion by $\mathcal N$ would permute simple defects rather than producing a sum. But the displayed fusion rule says that $\mathcal N\times\mathcal N$ is a direct sum of two distinct defects, $1$ and $\eta$. Therefore $\mathcal N$ cannot have an inverse defect under fusion. It is non-invertible.

</details>

### Exercise 4: Why framing can matter

Give a reason why fusing a line defect with itself may require a framing choice.

<details><summary><strong>Solution</strong></summary>

To define the product of two line defects along the same curve, one often separates one copy slightly in a normal direction and then takes a limit. The choice of normal displacement is a framing. In theories where self-linking, spin structure, or Chern–Simons-like phases are present, different framings can change the value of the correlator or the phase assigned to the line. Thus the fused operator is not fully specified by the curve alone; it also needs framing data or a convention for removing framing dependence.

</details>

## References

- K. G. Wilson, “Confinement of Quarks,” for the Wilson-loop viewpoint on gauge theory.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on non-Abelian phase factors, loop dynamics, and topology of gauge fields.
- M. Srednicki, *Quantum Field Theory*, §82, for Wilson loops and confinement orientation.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for extended charged operators and topological symmetry operators.
- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality,” for line operators, global form, and higher-form symmetry.
- O. Aharony, N. Seiberg, and Y. Tachikawa, “Reading Between the Lines of Four-Dimensional Gauge Theories,” for line-operator lattices and global forms.
- P. Etingof, S. Gelaki, D. Nikshych, and V. Ostrik, *Tensor Categories*, for the mathematical language behind semisimple fusion categories.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, for two-dimensional defects, fusion, and rational CFT examples.

## Version history

- **2026-06-20:** Initial polished draft. Added topological and non-topological fusion, Wilson-line tensor-product examples, interface fusion, junctions, associativity, anomaly caveats, and exercises.
