---
title: "Global Form of Symmetry Groups"
description: "Explains why the global form of a symmetry group, not only its Lie algebra, controls charged operators, background bundles, flux quantization, and gauging."
sidebar:
  label: "Global Form of Symmetry Groups"
  order: 4
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. I §2.7 and Vol. II Chs. 15–16 on representations, symmetries, and external fields; Gaiotto–Kapustin–Seiberg–Willett on background fields and gauging; Aharony–Seiberg–Tachikawa on global aspects of gauge theories."
topics:
  - global form
  - Lie groups
  - symmetry bundles
  - background fields
  - charge quantization
  - gauging
  - line operators
canonicalTopics:
  - global-form-of-symmetry-group
  - faithful-global-symmetry
  - principal-bundle-background
  - charge-lattice
  - flux-quantization
  - obstruction-to-gauging
researchStatus:
  established:
    - "Local Ward identities see the Lie algebra of a continuous symmetry, while background fields, charged spectra, bundle topology, and gauging depend on the full global form of the symmetry group."
  active:
    - "Modern work extends this global-form bookkeeping to higher-form symmetries, higher groups, disconnected symmetries, non-invertible defects, and symmetry TFT."
---

## Summary

A continuous symmetry is not specified completely by its Lie algebra. The Lie algebra tells us the infinitesimal generators and local Ward identities, but the **global form** of the group tells us which transformations are actually identified, which representations are allowed, and which background bundles can be turned on.

A useful slogan is

$$
\text{Lie algebra} \quad + \quad \text{global form} \quad = \quad \text{honest symmetry group}.
$$

For example, the groups $SU(2)$ and $SO(3)$ have the same Lie algebra,

$$
\mathfrak{su}(2)\simeq \mathfrak{so}(3),
$$

so their infinitesimal current algebra is locally the same. They are not the same symmetry group. A theory with genuine spin-$1/2$ operators can have an $SU(2)$ symmetry; a theory in which only integer-spin representations are genuine local operators may have only $SO(3)=SU(2)/\mathbb Z_2$ as its faithful symmetry.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A diagram showing that a Lie algebra must be supplemented by a global form to determine representations, background bundles, flux quantization, and gauging choices.](/figures/symmetry-anomalies-topology/global-form-symmetry-bundles.svg)

<figcaption>

The Lie algebra controls infinitesimal Ward identities. The global form of the group controls representation theory, background bundles, flux quantization, and the possible operation of gauging. Two theories can agree locally and differ globally.

</figcaption>
</figure>

This page explains the global-form layer for ordinary zero-form symmetries. The punchline is simple and easy to forget:

$$
\text{The current algebra is not enough data to gauge a symmetry.}
$$

To gauge, or even to couple to arbitrary backgrounds, one must know the actual group $G$, not merely its Lie algebra $\mathfrak g$.

## Prerequisites

Read [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/) and [Background Fields versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/) first. You should also know the representation-theoretic language in [Symmetry Groups and Representations](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-groups-and-representations/) and the charge-sector viewpoint in [Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/).

The only topology assumed here is the idea that a gauge field can be a connection on a possibly nontrivial principal bundle. The mathematical details belong in the Mathematical Toolkit; here we focus on the QFT consequences.

## Core idea

For a connected Lie group $G$, the Lie algebra $\mathfrak g$ describes small transformations near the identity. A Noether current $j_a^\mu$ and charge $Q_a$ usually satisfy commutation relations of the form

$$
[Q_a,Q_b]=i f_{ab}{}^c Q_c,
$$

and the Ward identities derived from localizing a symmetry parameter depend on the same structure constants. This is local data.

But a quantum field theory also knows global data:

- which finite transformations are equal to the identity,
- which charge representations occur in the spectrum,
- which local operators are genuine,
- which extended operators are genuine,
- which background gauge fields are allowed,
- which fluxes and holonomies are quantized,
- which topological sectors appear when the symmetry is gauged.

This data is encoded in the global form of $G$.

The standard connected case is

$$
G=\widetilde G/\Gamma,
$$

where $\widetilde G$ is the simply connected Lie group with Lie algebra $\mathfrak g$ and $\Gamma$ is a subgroup of its center $Z(\widetilde G)$. Different choices of $\Gamma$ give groups with the same Lie algebra and different global physics.

Examples include

$$
SO(3)=SU(2)/\mathbb Z_2,
$$

and, more generally,

$$
PSU(N)=SU(N)/\mathbb Z_N.
$$

The difference is invisible to an infinitesimal Ward identity around flat space, but visible to spinor representations, center charge, line operators, and bundles with nontrivial topology.

:::note[Source note]
Different communities use slightly different words here. In particle-physics textbooks, “the symmetry group” often means the group acting on the elementary fields in a chosen Lagrangian. In modern QFT, especially when dualities or non-Lagrangian theories are involved, the more invariant object is the group acting faithfully on genuine operators and admitting background fields. This page uses the latter meaning.
:::

## Setup and conventions

We use the conventions of this volume. Continuous internal symmetries are generated by Hermitian charges $Q_a$ with unitary transformations

$$
U(\alpha)=e^{i\alpha^a Q_a}.
$$

A field or operator $\mathcal O$ transforms in a representation $R$ as

$$
U(g)\,\mathcal O_i\,U(g)^{-1}=R(g)_i{}^j\mathcal O_j.
$$

For a compact connected group $G$, a background field is a connection on a principal $G$-bundle $P\to M$, not merely a globally defined one-form $A=A_\mu^aT_a dx^\mu$. On a good cover $\{U_i\}$ of spacetime $M$, it is described by local one-forms $A_i$ and transition functions $g_{ij}:U_i\cap U_j\to G$ satisfying

$$
A_i=g_{ij}A_jg_{ij}^{-1}-i(dg_{ij})g_{ij}^{-1},
$$

with the cocycle condition

$$
g_{ij}g_{jk}g_{ki}=1
$$

on triple overlaps. If the actual group is $G=\widetilde G/\Gamma$, then the transition functions take values in $G$, not necessarily in $\widetilde G$.

That last sentence is where much of the physics hides.

## Faithful symmetry versus presentation

A group action on a theory may have a kernel: a subgroup that acts trivially on all genuine operators. If $K\subset G$ acts trivially, then the faithful symmetry is

$$
G_{\text{faithful}}=G/K.
$$

This is not pedantry. The group that acts faithfully is the one whose background bundles are naturally classified as symmetry backgrounds.

Suppose a theory is presented with a $U(1)$ transformation

$$
\phi(x)\mapsto e^{iq\alpha}\phi(x),
$$

but all genuine local operators have charges divisible by $n$ in some chosen normalization. Then the element $e^{2\pi i/n}$ acts trivially on the local operator algebra. One can still use the covering $U(1)$ as a convenient presentation, but the faithful group is a quotient. Because $U(1)/\mathbb Z_n$ is abstractly isomorphic to $U(1)$, this example is mostly about **charge normalization** and flux quantization rather than about a new Lie group. The lesson is still important: the minimal electric charge is global data.

For nonabelian groups, the distinction is sharper. A theory with only adjoint $SU(2)$ fields has no local operator in a half-integer isospin representation. The center element $-1\in SU(2)$ acts trivially on all adjoint fields, so the faithful action on those fields is $SO(3)$. If the full QFT has no genuine spin-$1/2$ local operators, its ordinary zero-form symmetry may be $SO(3)$ rather than $SU(2)$.

The word “presentation” matters. A Lagrangian may use redundant variables or fields that are not themselves genuine local operators. Conversely, a non-Lagrangian theory may have a symmetry visible only through its operator spectrum, defects, and background coupling. The symmetry group of the QFT is not always the group one first writes in a convenient UV description.

## Local Ward identities see only the Lie algebra

The ordinary derivation of a current Ward identity uses an infinitesimal transformation

$$
\delta_\alpha \phi=i\alpha^a(x)T_a\phi,
$$

and extracts the coefficient of $\partial_\mu\alpha^a$. This determines a current $j_a^\mu$ and, when the symmetry is unbroken and anomaly-free,

$$
\partial_\mu j_a^\mu=0
$$

inside correlators, up to contact terms.

Nothing in this local derivation distinguishes $SU(2)$ from $SO(3)$. Both have the same generators $T_a$ and the same structure constants.

This is why one sometimes hears statements like “the symmetry is $SU(2)$” when the derivation has only shown “the Lie algebra is $\mathfrak{su}(2)$.” For perturbative calculations around a trivial background, that shortcut may be harmless. For global questions it is not.

The global form appears when one asks questions such as:

$$
\text{Can I put the theory on every }G\text{-bundle?}
$$

$$
\text{Which holonomies are allowed?}
$$

$$
\text{Which flux sectors are summed over after gauging?}
$$

$$
\text{Which charged operators are genuine?}
$$

The answers require the group, not just the algebra.

## Background bundles are the diagnostic

A background gauge field for a global symmetry is the most efficient test of the global form. For a continuous group $G$, it is not just a Lie-algebra-valued one-form. It is a connection on a principal $G$-bundle.

If spacetime is topologically simple and the background is globally trivial, one may write a single connection one-form $A$ everywhere. Then the global form is easy to miss. But on a general spacetime, or with nontrivial holonomies, one must specify transition functions valued in the actual group.

For $G=SU(2)$, every principal bundle has transition functions that lift to $SU(2)$ by definition. For $G=SO(3)$, there can be $SO(3)$ bundles that do not lift to $SU(2)$. The obstruction is measured by a characteristic class usually denoted

$$
w_2(P)\in H^2(M,\mathbb Z_2).
$$

A spin-$1/2$ representation is not a representation of $SO(3)$, so an $SO(3)$ background with $w_2(P)\neq0$ cannot be used to define a doublet field globally. This is not a small correction. It is the difference between a well-defined path integral and nonsense.

Thus the same local connection $A_\mu^aT_a$ can represent different global situations depending on the bundle to which it belongs.

:::note[Convention-sensitive source note]
Mathematical treatments often define a gauge field directly as a connection on a principal bundle. Many physics derivations first write a globally defined $A_\mu^a$. The latter is a local trivialization of the former. This page uses the bundle language only where it changes QFT answers: allowed backgrounds, flux quantization, and gauging sectors.
:::

## Charge lattices and allowed representations

For compact connected groups, the allowed representations are another way to see the global form.

For $SU(2)$, irreducible representations are labelled by

$$
j=0,\frac12,1,\frac32,\ldots.
$$

For $SO(3)$, only integer-spin representations descend to honest representations:

$$
j=0,1,2,\ldots.
$$

The Lie algebra action is the same. The difference is the action of the center of $SU(2)$.

More generally, let $\widetilde G$ be simply connected and let

$$
G=\widetilde G/\Gamma.
$$

A representation of $\widetilde G$ descends to a representation of $G$ precisely when every element of $\Gamma$ acts trivially. Equivalently, the representation has zero charge under the quotient subgroup $\Gamma$ of the center.

In gauge-theory language, this is often called a restriction on center charge or $N$-ality. In flavor-symmetry language, it is a restriction on which multiplets are genuine local operators.

This distinction is also visible in selection rules. If a putative local operator carries a representation that does not descend to the faithful group, it is not a genuine local operator of the theory. It might still exist as the end of a topological line or surface, or as a nonlocal defect. That distinction becomes essential in later pages on defects and higher-form symmetries.

## U(1) normalization and flux quantization

The abelian case looks deceptively familiar. A $U(1)$ background is locally a one-form $A$, and a charge-$q$ field couples by

$$
D_\mu\phi=(\partial_\mu-iqA_\mu)\phi.
$$

The global information is the charge lattice. If the minimal genuine charge is normalized to $1$, then the flux obeys

$$
\frac{1}{2\pi}\int_\Sigma F\in\mathbb Z
$$

for any closed two-cycle $\Sigma$, assuming ordinary bosonic $U(1)$ bundles and no additional spin-charge refinement.

If one instead writes the same theory using charges that are all multiples of $n$, then the apparent normalization of $A$ has changed. One can absorb the factor into the definition of the gauge field, but not for free: holonomies and flux quantization transform accordingly.

The invariant statement is this:

$$
\exp\left(iq\oint_\gamma A\right)
$$

must be well-defined for every genuine charge $q$ and closed loop $\gamma$. The allowed backgrounds are those compatible with the genuine charge lattice.

This is why one should be cautious with phrases like “the $U(1)$ charge is $1/3$.” Fractional relative to what? In QFT, charge normalization is fixed only after specifying which line operators, local operators, and background bundles are regarded as genuine.

## SU(2) versus SO(3)

The cleanest nonabelian example is the pair

$$
SU(2)\quad\text{and}\quad SO(3)=SU(2)/\mathbb Z_2.
$$

They have the same Lie algebra. They do not have the same global data.

| Question | $SU(2)$ symmetry | $SO(3)$ symmetry |
|---|---|---|
| Lie algebra | $\mathfrak{su}(2)$ | $\mathfrak{su}(2)$ |
| Allowed local reps | integer and half-integer $j$ | integer $j$ only |
| Center action | nontrivial on half-integer reps | already quotiented |
| Background bundles | $SU(2)$ bundles | $SO(3)$ bundles, including possibly non-liftable ones |
| Diagnostic class | second Chern class data | $w_2(P)$ can obstruct lift to $SU(2)$ |

If a theory contains a genuine doublet local operator $\psi_i$, then the center of $SU(2)$ acts as $\psi_i\mapsto-\psi_i$, and the symmetry cannot be faithfully reduced to $SO(3)$.

If all genuine local operators are integer-spin multiplets, then the center acts trivially on local operators. One must still ask about extended operators and background couplings before declaring the full symmetry, but from the local-operator viewpoint $SO(3)$ is the natural faithful group.

The distinction controls gauging. Gauging $SU(2)$ and gauging $SO(3)$ do not generally produce the same theory: they sum over different bundles and have different allowed line operators and topological terms.

## The Standard Model quotient as a warning

A physically important warning sign is the Standard Model gauge group. Its Lie algebra is often written as

$$
\mathfrak{su}(3)\oplus\mathfrak{su}(2)\oplus\mathfrak u(1).
$$

But the possible global gauge group is not determined by this Lie algebra alone. One familiar choice is

$$
G_{\mathrm{SM}}=\frac{SU(3)\times SU(2)\times U(1)_Y}{\mathbb Z_6},
$$

with related quotient choices also discussed depending on the spectrum and allowed bundles.

Why does this matter here, in a volume about global symmetries? Because the same logic applies before gauging. A set of local charges may be compatible not with a direct product group, but with a quotient by elements that act trivially on all genuine fields and operators.

The moral is not that every page must obsess over $\mathbb Z_6$. The moral is that writing the Lie algebra and the particle charges is not always the full statement of the symmetry structure.

## Global form and anomalies

An anomaly can depend on the global form of the symmetry.

Perturbative anomalies are often detected by infinitesimal background gauge transformations and are naturally expressed in terms of Lie-algebra data. Global anomalies, discrete anomalies, and mixed anomalies with higher-form symmetries can be invisible to purely local Lie-algebra tests.

A theory might have no perturbative anomaly for $\mathfrak g$, yet fail to be consistently coupled to all $G$-bundles for a particular global form $G$. Conversely, a theory may be anomaly-free for one quotient but not for another.

The background-field test says:

$$
\text{A symmetry with group }G\text{ is anomaly-free only if }Z[P,A]\text{ is well-defined for all allowed }G\text{-backgrounds.}
$$

Here $P$ is the principal $G$-bundle and $A$ is a connection on it. A local calculation around the trivial bundle checks only part of this condition.

This is one reason modern anomaly discussions are written in terms of background fields, characteristic classes, and inflow actions. The anomaly is not merely a bad divergence in a triangle graph. It is an obstruction to making the partition function a gauge-invariant function of background symmetry data.

## Global form and line operators

Even in a page about ordinary zero-form symmetries, line operators are hard to avoid. They are often the most sensitive probes of global form.

In a gauge theory, the choice of gauge group affects which Wilson lines are genuine. A Wilson line in representation $R$ is well-defined only if $R$ is a representation of the gauge group. For $SU(2)$ gauge theory, a fundamental Wilson line is allowed. For $SO(3)$ gauge theory, it is not a genuine Wilson line unless extra surface data are attached.

For global symmetries, the analogous statement is that local and extended charged operators must transform in honest representations of the symmetry group, or else come with additional topological attachments. The latter possibility is a preview of higher-form symmetry and defects.

This is the beginning of a recurring theme:

$$
\text{global form} \quad \longleftrightarrow \quad \text{which operators are genuine}.
$$

If a purported operator needs an attached topological surface to be well-defined, then it is not a standalone local or line operator. That attachment is not decorative; it is part of the symmetry structure.

## Gauging depends on the global form

To gauge a global symmetry, one sums or integrates over its background fields. Therefore the global form determines the configuration space being summed over.

For a continuous group $G$, the schematic gauged path integral is

$$
Z_{\text{gauged}}
=\sum_{[P\to M]}
\int_{\mathcal A(P)/\mathcal G(P)}\mathcal D A\;
Z_{\text{matter}}[P,A]\,e^{iS_{\text{gauge}}[P,A]+iS_{\text{top}}[P,A]}.
$$

The sum over $[P\to M]$ is a sum over topological types of principal $G$-bundles. Change $G$, and this sum changes.

For a finite group $G$, gauging is even more visibly global:

$$
Z_{\text{gauged}}(M)
=\sum_{[P\to M]}
\frac{1}{|\operatorname{Aut}(P)|}\,
Z[M;P]\,e^{iS_{\text{top}}[P]}.
$$

There is no Lie algebra at all. The whole operation is global.

The next page develops gauging in detail. The lesson needed here is this: there is no well-defined operation “gauge the Lie algebra $\mathfrak g$.” One gauges a symmetry group, with a specified global form, background-field space, anomaly status, and choice of gauge/topological action.

## Common pitfalls

**Pitfall 1: Treating the Lie algebra as the symmetry group.**

The Lie algebra controls infinitesimal transformations. It does not determine representations, center action, background bundles, or flux quantization.

**Pitfall 2: Assuming the group acting on Lagrangian fields is automatically the faithful symmetry.**

A Lagrangian can contain redundant variables or fields whose transformation has a kernel. The faithful group is the group acting nontrivially on genuine operators.

**Pitfall 3: Ignoring background bundles because flat-space perturbation theory does not need them.**

Many global-form distinctions vanish on $M=\mathbb R^d$ with trivial background. They reappear on nontrivial manifolds, in finite-volume partition functions, with defects, and after gauging.

**Pitfall 4: Saying that $U(1)$ charges are fractional without specifying normalization.**

The physically meaningful data are the charge lattice, genuine operators, and allowed fluxes. A different normalization of $A$ changes what counts as an integral charge.

**Pitfall 5: Forgetting that anomalies can be global.**

A perturbative anomaly polynomial checks important local data. It does not automatically settle every question about finite transformations, disconnected components, torsion backgrounds, or quotient groups.

## Relations to other pages

This page sits between background fields and gauging. The next page, [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/), uses the global form to define the space of fields being summed over.

Later pages on **Higher-Form Symmetries** and **Center Symmetry** will revisit the same issue from the perspective of extended charged operators. The Gauge Redundancy and BRST chapter will explain the corresponding statement for dynamical gauge fields.

The Anomalies chapter will use the background-bundle viewpoint to formulate perturbative, global, mixed, and gravitational anomalies. The Topological Terms chapter will explain how different choices of bundle sum can be weighted by theta terms, Chern–Simons terms, Dijkgraaf–Witten terms, or discrete theta angles.

## Research status

The core distinction between Lie algebra and global group is established mathematics and standard QFT practice. What has changed in modern QFT is how central this distinction has become.

In older perturbative contexts, one often fixed a Lagrangian on flat spacetime and did not need to discuss nontrivial backgrounds. In modern work on anomalies, duality, generalized symmetry, topological phases, and symmetry TFT, the global form is often part of the primary data of the theory.

Active research directions include disconnected zero-form symmetries, higher-group symmetries, generalized global structures involving ordinary and higher-form symmetries, non-invertible symmetry defects, and systematic classification of anomalies by invertible field theories.

## Exercises

### Exercise 1: Same Lie algebra, different representations

Show that every integer-spin representation of $SU(2)$ descends to a representation of $SO(3)=SU(2)/\mathbb Z_2$, while a spin-$1/2$ representation does not.

<details><summary><strong>Solution</strong></summary>

The center of $SU(2)$ is $\mathbb Z_2=\{1,-1\}$. In the spin-$j$ representation, the central element $-1$ acts as

$$
(-1)^{2j}.
$$

If $j$ is an integer, then $2j$ is even and $-1$ acts trivially. Therefore the representation is really a representation of the quotient $SU(2)/\mathbb Z_2=SO(3)$.

If $j$ is half-integer, then $2j$ is odd and $-1$ acts as minus the identity. The quotient identifies $-1$ with $1$, so this action is not well-defined on the quotient. Hence spin-$1/2$ and all half-integer representations do not descend to $SO(3)$.

</details>

### Exercise 2: Why Ward identities miss the quotient

Consider two theories whose continuous symmetry has Lie algebra $\mathfrak{su}(2)$, but whose faithful groups are respectively $SU(2)$ and $SO(3)$. Explain why the local current conservation equation has the same form in both theories.

<details><summary><strong>Solution</strong></summary>

The local Ward identity is obtained by making an infinitesimal transformation

$$
\delta\phi=i\alpha^a(x)T_a\phi
$$

and extracting the coefficient of $\partial_\mu\alpha^a$. This calculation uses the generators $T_a$ and their Lie brackets

$$
[T_a,T_b]=if_{ab}{}^cT_c.
$$

The Lie algebras of $SU(2)$ and $SO(3)$ are the same, so the same local current algebra and the same conservation equation

$$
\partial_\mu j_a^\mu=0
$$

appear, up to contact terms and anomalies. The quotient by $\mathbb Z_2$ affects finite transformations, allowed representations, and background bundles, not the infinitesimal conservation equation around a trivial background.

</details>

### Exercise 3: Faithful quotient

Suppose a group $G$ acts on every genuine local operator, but a normal subgroup $K\triangleleft G$ acts trivially on all of them. Show that the action factors through $G/K$.

<details><summary><strong>Solution</strong></summary>

Let $R$ denote the action of $G$ on the operator algebra. If $K$ acts trivially, then $R(k)=1$ for every $k\in K$. If two group elements differ by an element of $K$, say $g'=gk$, then

$$
R(g')=R(gk)=R(g)R(k)=R(g).
$$

Therefore the action depends only on the coset $gK\in G/K$. This defines a faithful action of the quotient group after removing any remaining kernel.

</details>

### Exercise 4: Why gauging needs the global form

Explain why the expression

$$
\sum_{[P\to M]}\int_{\mathcal A(P)/\mathcal G(P)}\mathcal D A\;Z[P,A]
$$

is incomplete unless the group $G$ has been specified, not just the Lie algebra $\mathfrak g$.

<details><summary><strong>Solution</strong></summary>

The symbol $[P\to M]$ means topological isomorphism classes of principal $G$-bundles. Different global forms of the same Lie algebra can have different classes of principal bundles over the same spacetime. For example, $SO(3)$ bundles may fail to lift to $SU(2)$ bundles.

The quotient $\mathcal A(P)/\mathcal G(P)$ also depends on the structure group of $P$, and allowed matter fields or line operators depend on which representations are honest representations of $G$. Thus the path integral cannot be defined from $\mathfrak g$ alone.

</details>

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, §2.7. Projective representations, covering groups, and global aspects of symmetry representations.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters 15–16. Gauge theory, external fields, and symmetry constraints.
- Mark Srednicki, *Quantum Field Theory*, especially §§22, 24, 69–76. Continuous and nonabelian symmetries, gauge theory, and anomalies.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters 25, 30, and 34. Yang–Mills theory, anomalies, and background fields.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” 2015. Modern background-field and gauging language, including the role of genuine operators.
- Ofer Aharony, Nathan Seiberg, and Yuji Tachikawa, “Reading between the Lines of Four-Dimensional Gauge Theories,” 2013. A standard reference for global form, line operators, and discrete theta angles in gauge theory.
- Clay Córdova, Thomas T. Dumitrescu, and Kenneth Intriligator, “Exploring 2-Group Global Symmetries,” 2018. Global structures involving ordinary and higher-form symmetries.

## Version history

- **2026-06-17:** Initial polished page on global form, faithful symmetry groups, background bundles, and gauging data.
