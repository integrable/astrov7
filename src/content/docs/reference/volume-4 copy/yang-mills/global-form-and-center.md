---
title: "Global Form and Center"
description: "Explains the distinction between the local Lie algebra and the global gauge group, with emphasis on the center of SU(N), N-ality, line operators, and center one-form symmetry."
sidebar:
  label: "Global Form and Center"
  order: 7
level: Advanced
status: "Polished draft"
source: "Srednicki §§69–70, 82; Schwartz Ch. 25; Weinberg Vol. II Ch. 15; Gaiotto, Kapustin, Seiberg, Willett 2015; Polyakov, Gauge Fields and Strings."
topics:
  - global form of gauge group
  - center symmetry
  - one-form symmetry
  - line operators
  - SU(N) gauge theory
canonicalTopics:
  - global-form-of-gauge-group
  - center-of-gauge-group
  - n-ality
  - one-form-center-symmetry
  - line-operator-spectrum
researchStatus:
  established:
    - "The distinction between Lie algebra, global gauge group, center, representations, and line-operator spectra is a standard part of the nonperturbative definition of gauge theory."
  active:
    - "The modern language of generalized symmetries, relative QFTs, anomaly inflow, and global-form choices continues to sharpen how gauge theories are classified and compared."
---

## Summary

The local formulas of Yang–Mills theory know the Lie algebra. They do not, by themselves, know the full global form of the gauge group.

For example,

$$
SU(N)
\qquad\text{and}\qquad
PSU(N)\equiv SU(N)/\mathbb Z_N
$$

have the same Lie algebra $\mathfrak{su}(N)$. Therefore they share the same infinitesimal gauge field $A_\mu=A_\mu^aT^a$, the same structure constants $f^{abc}$, and the same local Yang–Mills kinetic term. But they are not the same gauge theory once one asks global questions: which representations are genuine, which Wilson lines exist, which 't Hooft lines are allowed, and which higher-form symmetries act on line operators.

The center of $SU(N)$ is

$$
Z(SU(N))
=
\left\{
\exp\!\left(\frac{2\pi ik}{N}\right)\mathbf 1_N
\,\middle|\,
k=0,1,\ldots,N-1
\right\}
\cong \mathbb Z_N.
$$

A representation $R$ has center charge, or $N$-ality, $k_R\in\mathbb Z_N$, if the center acts as

$$
z\mathbf 1_N\mapsto z^{k_R}\mathbf 1_R.
$$

The fundamental has $N$-ality $1$, the antifundamental has $N$-ality $-1$, and the adjoint has $N$-ality $0$. This single integer already tells you which Wilson lines are charged under the electric center one-form symmetry of pure $SU(N)$ Yang–Mills theory.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Diagram showing how the same local su(N) algebra can lead to different global gauge groups, representation spectra, line operators, and center one-form symmetries.](/figures/gauge-theories-standard-model/global-form-center-map.svg)

<figcaption>

The local algebra $\mathfrak{su}(N)$ fixes infinitesimal Yang–Mills formulas. The global form of the gauge group fixes additional nonlocal data: which representations descend to the group, which line operators are genuine, and which center one-form symmetries exist.

</figcaption>
</figure>

## Prerequisites

You should know the local Yang–Mills construction through [Color and Representations](/gauge-theories-standard-model/yang-mills/color-and-representations/). The key local facts are

$$
[T^a,T^b]=if^{abc}T^c,
\qquad
D_\mu=\partial_\mu+igA_\mu^aT_R^a,
\qquad
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U.
$$

You should also know what Wilson lines are at the level of the gauge-principle chapter: parallel transporters built from the connection. This page uses them as probes of global gauge structure, not yet as confinement diagnostics in detail.

## Core idea

The slogan is:

$$
\text{Lie algebra fixes local gauge theory; global form fixes nonlocal gauge theory}.
$$

A Lagrangian written using $F_{\mu\nu}^aF^{a\mu\nu}$ can look identical for two different global forms of the gauge group. The difference appears when you ask questions such as:

- Is the fundamental representation a genuine representation of the gauge group?
- Can a fundamental Wilson line be inserted by itself?
- Which line operators are mutually local?
- Are there topological sectors not visible in small gauge transformations?
- Does the theory have an electric or magnetic one-form symmetry?

These are not fussy mathematical footnotes. They affect confinement diagnostics, finite-temperature order parameters, anomaly constraints, boundary conditions, dualities, and the global form of the Standard Model gauge group.

## Local algebra versus global group

A Lie algebra describes infinitesimal transformations. A Lie group describes finite transformations, including global topology.

The Lie algebra of $SU(N)$ is

$$
\mathfrak{su}(N)
=
\{X\in \operatorname{Mat}_{N\times N}(\mathbb C)\mid X^\dagger=X,\ \operatorname{tr}X=0\}
$$

in the Hermitian-generator convention used in this volume. The local gauge connection is

$$
A_\mu=A_\mu^aT^a.
$$

Any quotient

$$
SU(N)/\Gamma,
\qquad
\Gamma\subseteq Z(SU(N)),
$$

has the same Lie algebra. Therefore the local curvature formula

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c
$$

is unchanged by replacing $SU(N)$ with $SU(N)/\Gamma$.

But finite transformations are not the same. In $SU(N)/\Gamma$, elements of $\Gamma$ are identified with the identity. A representation of $SU(N)$ is a genuine representation of $SU(N)/\Gamma$ only if every element of $\Gamma$ acts trivially.

That is the first place where local Lie-algebra notation under-describes the theory.

## The center of SU(N)

The center of a group consists of elements that commute with every group element. For $SU(N)$,

$$
Z(SU(N))
=
\{z_k\mathbf 1_N\mid z_k^N=1\}
\cong\mathbb Z_N,
$$

where

$$
z_k=\exp\!\left(\frac{2\pi ik}{N}\right).
$$

Because these elements are scalar matrices, they commute with all of $SU(N)$. They also have determinant one:

$$
\det(z_k\mathbf 1_N)=z_k^N=1.
$$

The center acts on irreducible representations by a phase. For $SU(N)$, this phase is measured by $N$-ality.

If a representation is built from $n$ fundamental indices and $\bar n$ antifundamental indices, then its $N$-ality is

$$
k_R=n-\bar n\pmod N.
$$

Examples:

| Representation | Symbol | $N$-ality |
|---|---:|---:|
| singlet | $\mathbf 1$ | $0$ |
| fundamental | $\mathbf N$ | $1$ |
| antifundamental | $\bar{\mathbf N}$ | $-1$ |
| adjoint | $\mathbf{Adj}$ | $0$ |
| two-index antisymmetric | $\wedge^2\mathbf N$ | $2$ |
| baryon-like product of $N$ fundamentals | $\epsilon_{i_1\cdots i_N}q^{i_1}\cdots q^{i_N}$ | $0$ |

For QCD with $N=3$,

$$
\mathbf 3: k=1,
\qquad
\bar{\mathbf 3}: k=-1\equiv 2,
\qquad
\mathbf 8: k=0.
$$

This is why adjoint fields are neutral under the center while quark fields are not.

## Representations that descend to a quotient

Consider

$$
PSU(N)=SU(N)/\mathbb Z_N.
$$

A representation of $SU(N)$ descends to a representation of $PSU(N)$ only if the entire center acts trivially. Equivalently, only representations with

$$
k_R=0\pmod N
$$

descend to $PSU(N)$.

The adjoint representation descends because the center acts trivially by conjugation:

$$
z\mathbf 1_N\, X\, (z\mathbf 1_N)^{-1}=X.
$$

The fundamental representation does not descend, because

$$
z\mathbf 1_N\mapsto z\mathbf 1_N
$$

is not the identity unless $z=1$. In the quotient group $PSU(N)$, the center element is supposed to be the same as the identity. A genuine representation must assign the same matrix to both. The fundamental fails this test.

This distinction can be invisible in perturbative Feynman rules around trivial backgrounds. It becomes visible in nonperturbative sectors, line operators, bundles on topologically nontrivial manifolds, and the spectrum of genuine charged objects.

## Wilson lines and center charge

A Wilson line in representation $R$ along a curve $C$ is schematically

$$
W_R(C)
=
\operatorname{tr}_R\,\mathcal P
\exp\!\left(-ig\int_C A_\mu^aT_R^a dx^\mu\right),
$$

where the sign in the exponential is chosen to match the parallel transport convention used with $D_\mu=\partial_\mu+igA_\mu$. Different sources may place the inverse transporter here; the center-charge statements are unchanged.

Under the center of $SU(N)$, a Wilson line in representation $R$ carries charge $k_R$. In pure $SU(N)$ Yang–Mills theory, the Wilson line in the fundamental representation is charged under an electric $\mathbb Z_N$ one-form symmetry.

This is different from an ordinary zero-form global symmetry:

- an ordinary symmetry acts on local operators;
- a one-form symmetry acts on line operators;
- the charged objects are extended, not pointlike.

For pure $SU(N)$ Yang–Mills theory, local gauge-invariant operators such as

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
$$

are neutral under the electric center one-form symmetry. Wilson loops can be charged.

## Center symmetry and matter screening

The center one-form symmetry exists only when no dynamical field can screen the corresponding center charge.

In pure Yang–Mills theory, all dynamical fields are adjoint-valued. The adjoint has $N$-ality zero, so adjoint fields cannot screen a fundamental Wilson line. The electric center one-form symmetry survives.

If dynamical fundamental matter is added, a fundamental Wilson line can end on a dynamical fundamental particle. Then the electric center one-form symmetry is explicitly broken. The Wilson loop is no longer a sharp order parameter for confinement in the same symmetry sense.

This explains a common statement in a more precise language:

$$
\text{pure } SU(N)\text{ Yang–Mills has a center one-form symmetry,}
$$

but

$$
SU(N)\text{ gauge theory with fundamental matter does not.}
$$

In QCD with dynamical quarks, the $SU(3)_c$ center is not an exact one-form symmetry. This is why confinement in real QCD is subtler than a simple unbroken-center-symmetry statement.

## Area law and perimeter law

A large Wilson loop can behave schematically as

$$
\langle W_R(C)\rangle
\sim
\exp[-\sigma_R\operatorname{Area}(C)]
$$

or

$$
\langle W_R(C)\rangle
\sim
\exp[-\mu_R\operatorname{Perimeter}(C)].
$$

The area law indicates that separating external probes with nonzero center charge costs energy proportional to their separation. In pure Yang–Mills theory, this is a confinement diagnostic.

In the modern generalized-symmetry language, the area law for center-charged Wilson loops is associated with an unbroken electric center one-form symmetry. A perimeter law indicates that the corresponding one-form symmetry is broken or screened in that channel.

This page is only setting up the language. A later chapter on Wilson loops, phases, and confinement develops the physics carefully, including Polyakov loops, thermal center symmetry, screening, and the limitations of Wilson-loop diagnostics.

## SU(N) versus PSU(N)

The difference between $SU(N)$ and $PSU(N)$ gauge theory can be summarized like this:

| Feature | $SU(N)$ gauge theory | $PSU(N)=SU(N)/\mathbb Z_N$ gauge theory |
|---|---|---|
| Local Lie algebra | $\mathfrak{su}(N)$ | $\mathfrak{su}(N)$ |
| Local $F_{\mu\nu}^aF^{a\mu\nu}$ term | same | same |
| Fundamental representation as genuine matter | allowed | not allowed |
| Adjoint representation | allowed | allowed |
| Fundamental Wilson line | genuine in suitable theories | not a genuine standalone Wilson line |
| Magnetic line sectors | depend on global choice | differ from $SU(N)$ |
| One-form symmetries | electric center in adjoint-only theories | magnetic center-type symmetries may appear |

The table is schematic because a full quantum gauge theory also requires choices of discrete theta angles and mutually local line-operator spectra. The important point for now is that the local Lagrangian is not the whole definition.

## The Standard Model preview

The local Standard Model Lie algebra is

$$
\mathfrak{su}(3)\oplus\mathfrak{su}(2)\oplus\mathfrak u(1).
$$

But the global gauge group is not determined by this line alone. Depending on which representations and line operators are allowed, one may consider global forms such as

$$
SU(3)\times SU(2)\times U(1)
$$

or quotients by finite subgroups. A particularly important possibility is

$$
\frac{SU(3)\times SU(2)\times U(1)}{\mathbb Z_6},
$$

which is compatible with the observed Standard Model matter representations.

The full story belongs to the later Standard Model Architecture chapter. The lesson here is already enough: once a theory has several gauge factors and matter representations, global identifications can become part of the physical definition.

## Common pitfalls

**Thinking the Lie algebra uniquely determines the gauge group.** It does not. $SU(N)$ and $SU(N)/\mathbb Z_N$ have the same Lie algebra but different global data.

**Calling center symmetry an ordinary symmetry of quark fields.** In a gauge theory, the center one-form symmetry is not an ordinary global symmetry acting on local quark operators. It acts on line operators and exists only when compatible with the dynamical matter content.

**Forgetting that fundamental matter breaks the electric center one-form symmetry.** If a Wilson line can end on a dynamical particle, it is not charged under an exact one-form symmetry.

**Assuming perturbation theory sees everything.** Around flat spacetime and trivial bundles, $SU(N)$ and $PSU(N)$ perturbative Feynman rules can look identical. Nonperturbative sectors and line operators can still distinguish the theories.

**Treating quotient groups as notation only.** A quotient by the center changes which representations are genuine. It is not merely a relabeling of the same theory.

**Confusing center charge with ordinary electric charge.** $N$-ality labels how a representation transforms under the center of $SU(N)$. It is not the electromagnetic charge and not a flavor quantum number.

## Relations to other pages

This page closes the first Yang–Mills chapter by explaining what local formulas do not determine. It builds on [Color and Representations](/gauge-theories-standard-model/yang-mills/color-and-representations/) and prepares the later chapters on Wilson loops, confinement, QCD, and Standard Model global structure.

The Gauge Quantization chapter will mostly return to local perturbative questions: gauge fixing, Faddeev–Popov ghosts, BRST symmetry, and Slavnov–Taylor identities. The global-form issues here will reappear when line operators, theta angles, center symmetry, confinement diagnostics, anomalies, and generalized symmetries become central.

## Research status

The distinction between local Lie algebra and global gauge group is established. So are the center of $SU(N)$, $N$-ality of representations, and the fact that quotient groups restrict genuine representations.

The modern organization of these facts using generalized global symmetries is now a standard research language, especially for line operators, confinement, anomaly matching, boundary conditions, and dualities. The frontier is not whether these structures exist; it is how they classify QFTs, interact with anomalies and defects, and constrain nonperturbative dynamics in theories without a simple Lagrangian description.

## Exercises

### Exercise 1: Center of SU(N)

Show that

$$
Z(SU(N))
=
\{e^{2\pi ik/N}\mathbf 1_N\mid k=0,1,\ldots,N-1\}.
$$

<details><summary><strong>Solution</strong></summary>

Any scalar matrix $z\mathbf 1_N$ commutes with every $N\times N$ matrix. To belong to $SU(N)$ it must be unitary and have determinant one. Unitarity gives $|z|=1$, and the determinant condition gives

$$
\det(z\mathbf 1_N)=z^N=1.
$$

Thus

$$
z=e^{2\pi ik/N},
\qquad k=0,1,\ldots,N-1.
$$

Conversely, every such scalar matrix lies in $SU(N)$ and commutes with every element. These $N$ elements form a group isomorphic to $\mathbb Z_N$.

</details>

### Exercise 2: N-ality of QCD singlets

For $SU(3)$, assign $N$-ality to $q$, $\bar q$, $\bar q q$, and $qqq$.

<details><summary><strong>Solution</strong></summary>

For $SU(3)$, $N$-ality is defined modulo $3$.

A quark in the fundamental has

$$
k(q)=1.
$$

An antiquark in the antifundamental has

$$
k(\bar q)=-1\equiv 2\pmod 3.
$$

A meson-like color contraction has

$$
k(\bar q q)=-1+1=0\pmod 3.
$$

A baryon-like color contraction has

$$
k(qqq)=1+1+1=3\equiv0\pmod 3.
$$

So both meson and baryon color contractions are neutral under the center, as required for $SU(3)$ color singlets.

</details>

### Exercise 3: Why the fundamental does not descend to PSU(N)

Explain why the fundamental representation of $SU(N)$ is not a representation of $PSU(N)=SU(N)/\mathbb Z_N$.

<details><summary><strong>Solution</strong></summary>

In $PSU(N)$, all elements of the center $\mathbb Z_N$ are identified with the identity. Therefore a representation of $PSU(N)$, pulled back to $SU(N)$, must assign the identity matrix to every center element.

In the fundamental representation of $SU(N)$,

$$
z\mathbf 1_N\mapsto z\mathbf 1_N.
$$

For nontrivial $z=e^{2\pi ik/N}$, this is not the identity matrix. Hence the fundamental representation does not assign the same matrix to the identity and to the center element identified with it in the quotient. It therefore does not descend to a genuine representation of $PSU(N)$.

The adjoint representation does descend because center elements act trivially by conjugation.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§69–70, for non-Abelian gauge theory and group-representation data; §82 for Wilson loops, lattice theory, and confinement.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 25, especially gauge invariance and Wilson lines, for a physically direct entry point.
- Polyakov, *Gauge Fields and Strings*, Chs. 1, 3, and 7, for gauge systems, strong-coupling expansion, non-Abelian phase factors, and loop dynamics.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, Ch. 15, for non-Abelian gauge theory and the constraints of gauge invariance.
- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for the modern one-form symmetry interpretation of center symmetries and line operators.
- Aharony, Seiberg, and Tachikawa, “Reading between the lines of four-dimensional gauge theories,” for the detailed classification of line operators and global forms in four-dimensional gauge theory.

## Version history

- **2026-06-17:** Initial polished draft.
