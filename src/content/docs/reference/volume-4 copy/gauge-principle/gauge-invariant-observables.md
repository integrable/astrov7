---
title: "Gauge-Invariant Observables"
description: "Explains the criterion for physical observables in gauge theory, including local singlets, traces of field strengths, Wilson lines, Wilson loops, and dressed charged operators."
sidebar:
  label: "Gauge-Invariant Observables"
  order: 8
level: Graduate
status: "Polished draft"
source: "Srednicki §§54, 58, 69–75, and 82; Weinberg Vol. II Ch. 15; Schwartz Chs. 8, 25, and 30; Polyakov, Gauge Fields and Strings; Gaiotto–Kapustin–Seiberg–Willett 2015."
topics:
  - gauge-invariant observables
  - Wilson loops
  - Wilson lines
  - gauge redundancy
  - charged operators
canonicalTopics:
  - gauge-invariant-observables
  - wilson-loop
  - line-operators
  - gauss-law
researchStatus:
  established:
    - "Physical observables in a gauge theory must be invariant under proper gauge transformations, or more carefully must be well-defined on the gauge-equivalence classes allowed by the boundary conditions."
  active:
    - "The modern classification of extended operators, higher-form symmetries, boundary charges, and global forms of gauge groups is developed in later symmetry and nonperturbative chapters."
---

## Summary

Gauge theory uses redundant variables. Therefore the first test for a physical observable is not whether it is built from familiar fields, but whether it survives the redundancy. A quantity is a **gauge-invariant observable** if it gives the same answer on all representatives of the same physical configuration.

In the local classical language, this means that an observable $\mathcal O[A,\text{matter}]$ must satisfy

$$
\mathcal O[A^U,\text{matter}^U]=\mathcal O[A,\text{matter}]
$$

for every proper gauge transformation $U(x)$ that is treated as redundancy. Equivalently, $\mathcal O$ must descend from the configuration space $\mathcal C$ to the quotient by proper gauge transformations:

$$
\mathcal O:
\mathcal C/\mathcal G_0\longrightarrow \mathbb C.
$$

This criterion explains why $F_{\mu\nu}$ is an observable in Abelian theory, why $F_{\mu\nu}^a$ is not by itself an observable in non-Abelian theory, why $\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})$ is allowed, why Wilson loops are central, and why isolated charged fields require nonlocal dressing or boundary data.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![A map of common gauge-invariant observables: local singlets, closed Wilson loops, open Wilson lines with charged endpoints, and nonlocal charged dressings.](/figures/gauge-theories-standard-model/observable-classes-map.svg)

<figcaption>

Gauge-invariant observables are not limited to local polynomials. Local singlets, traces of covariant objects, closed Wilson loops, open Wilson lines ending on charged fields, and boundary-dressed charged operators are all examples of the same principle: the construction must be independent of the choice of gauge representative, up to any physical boundary symmetry that has intentionally been kept.

</figcaption>
</figure>

## Prerequisites

You should know [Gauge Redundancy Revisited](/gauge-theories-standard-model/gauge-principle/gauge-redundancy-revisited/), [Local Symmetry and Covariant Derivatives](/gauge-theories-standard-model/gauge-principle/local-symmetry-and-covariant-derivatives/), [Gauge Fields as Connections](/gauge-theories-standard-model/gauge-principle/gauge-fields-as-connections/), [Field Strength and Curvature](/gauge-theories-standard-model/gauge-principle/field-strength-and-curvature/), [Matter Representations](/gauge-theories-standard-model/gauge-principle/matter-representations/), and [Global versus Gauge Symmetry](/gauge-theories-standard-model/gauge-principle/global-versus-gauge-symmetry/).

The main technical input is the transformation law

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U,
$$

for the non-Abelian field strength, and the transformation law for a Wilson line derived below.

## Core idea

Gauge invariance is not a decorative constraint on formulas. It is the statement that the formula refers to physics rather than to coordinates on a redundant field space.

A useful analogy is ordinary polar coordinates. The angle $\theta$ is not defined at the origin, and the description $(r,\theta)$ has coordinate artifacts. A physical distance from the origin is $r$, not $\theta$. In gauge theory the redundancy is infinite-dimensional and more subtle, but the logic is the same: a physical statement cannot depend on how we label the same configuration.

The most compact criterion is:

$$
\boxed{\text{observable} = \text{well-defined function or operator on gauge orbits}.}
$$

That sentence is deliberately stronger than “made from $F_{\mu\nu}$.” In Abelian electrodynamics, many observables are built locally from $F_{\mu\nu}$. In non-Abelian gauge theory, important observables are often extended objects such as Wilson loops. In the Standard Model, experimentally meaningful quantities include scattering probabilities, inclusive rates, hadron masses, jet observables, and correlation functions of gauge-invariant operators. Gauge invariance is the first filter, not the end of the story.

## Setup and conventions

We use the volume convention

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a,
$$

with Hermitian generators satisfying

$$
[T^a,T^b]=if^{abc}T^c.
$$

Matter fields in a representation $R$ transform as

$$
\psi(x)\mapsto U_R^{-1}(x)\psi(x),
$$

and the gauge field transforms as

$$
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

The field strength is defined by

$$
[D_\mu,D_\nu]=igF_{\mu\nu},
$$

so

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

It transforms covariantly:

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U.
$$

For a $U(1)$ gauge theory, the same convention is

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

Then

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu
$$

is gauge invariant.

Throughout this page, “gauge invariant” means invariant under **proper gauge transformations**: transformations treated as redundancy after boundary conditions have been specified. Boundary transformations that act nontrivially on states can become global symmetries rather than redundancies. That caveat is not pedantry; it is exactly how electric charge appears in gauge theory.

## Local observables

A local observable is built from fields at one spacetime point, or from fields and finitely many derivatives at that point. In a gauge theory, locality alone is not enough. The expression must also contract gauge indices so that no unphysical orientation in internal space remains.

### Abelian examples

In Abelian gauge theory, $F_{\mu\nu}$ itself is gauge invariant. Therefore the familiar electric and magnetic fields,

$$
E_i=F_{i0},
\qquad
B_i=-\frac12\epsilon_{ijk}F_{jk},
$$

are gauge invariant in the usual electromagnetic theory. Local polynomials such as

$$
F_{\mu\nu}F^{\mu\nu},
\qquad
F_{\mu\nu}\widetilde F^{\mu\nu},
$$

are also gauge invariant. Here

$$
\widetilde F^{\mu\nu}=\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma}
$$

with the orientation convention fixed in the volume conventions page.

For charged matter, the field $\psi(x)$ is not gauge invariant:

$$
\psi(x)\mapsto e^{-iq\alpha(x)}\psi(x).
$$

But local neutral composites such as

$$
\psi^\dagger\psi,
\qquad
\bar\psi\psi,
\qquad
\phi^\dagger\phi,
\qquad
(D_\mu\phi)^\dagger D^\mu\phi
$$

are gauge invariant. The phase from the field cancels against the phase from the conjugate field.

### Non-Abelian examples

In a non-Abelian gauge theory, $F_{\mu\nu}$ transforms by conjugation, not by remaining fixed. Thus the matrix $F_{\mu\nu}$ is covariant, while its components $F_{\mu\nu}^a$ are basis-dependent internal components.

The trace removes the conjugation:

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
\mapsto
\operatorname{tr}(U^{-1}F_{\mu\nu}UU^{-1}F^{\mu\nu}U)
=
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

Similarly,

$$
\operatorname{tr}(F_{\mu\nu}\widetilde F^{\mu\nu})
$$

is gauge invariant and later becomes the density coupled to a theta angle.

Matter fields work the same way. If $\psi$ is in a unitary representation $R$, then

$$
\bar\psi\psi
\mapsto
\bar\psi U_R U_R^{-1}\psi
=\bar\psi\psi,
$$

while $\psi^i$ alone is not gauge invariant. Gauge-invariant local operators are built by contracting all representation indices with invariant tensors: Kronecker deltas, epsilon tensors, Clebsch–Gordan maps, traces, and their generalizations.

For example, in an $SU(N)$ theory with a fundamental scalar $\phi^i$,

$$
\phi^\dagger_i\phi^i
$$

is a singlet. In an $SU(3)$ color theory, a schematic baryon-like color singlet uses the invariant tensor

$$
\epsilon_{ijk}\,q^i q^j q^k.
$$

The detailed spin, flavor, and statistics structure matters in QCD, but the color lesson is already visible: gauge-invariant local operators must have all gauge indices saturated.

## Wilson lines and Wilson loops

The connection viewpoint says that $A_\mu$ tells us how to compare internal vectors at nearby spacetime points. The finite version of this comparison along a path $C$ from $x_i$ to $x_f$ is the Wilson line

$$
W_R(C;x_f,x_i)
=
P\exp\left[-ig\int_C dx^\mu\,A_\mu^a(x)T_R^a\right],
$$

where $P$ denotes path ordering. Path ordering is needed because non-Abelian generators at different points need not commute.

With the conventions of this volume, the Wilson line transforms as

$$
W_R(C;x_f,x_i)
\mapsto
U_R^{-1}(x_f)W_R(C;x_f,x_i)U_R(x_i).
$$

This formula is the master key. It says that an open Wilson line is not gauge invariant by itself: it has an uncanceled gauge rotation at each endpoint.

### Closed Wilson loops

If the path is closed, $x_f=x_i$, the endpoint rotations cancel inside a trace:

$$
W_R(C)
\equiv
\operatorname{tr}_R P\exp\left[-ig\oint_C dx^\mu\,A_\mu^aT_R^a\right].
$$

Under a gauge transformation,

$$
W_R(C)
\mapsto
\operatorname{tr}_R\left(U_R^{-1}(x_0)W_R(C)U_R(x_0)\right)
=W_R(C).
$$

A Wilson loop is therefore a gauge-invariant extended observable.

This is one of the deepest objects in gauge theory. In weakly coupled perturbation theory it encodes phase factors and gauge-boson exchange. In nonperturbative gauge theory it diagnoses confinement, screening, and center symmetry. In modern language it is a line operator, and its allowed representations depend on the global form of the gauge group and on the matter content.

### Open Wilson lines with charged endpoints

An open Wilson line can become gauge invariant if its endpoint transformations are canceled by charged fields. Suppose $\phi$ is in representation $R$. Then

$$
\phi^\dagger(x_f)W_R(C;x_f,x_i)\phi(x_i)
$$

is gauge invariant. Indeed,

$$
\phi^\dagger(x_f)\mapsto \phi^\dagger(x_f)U_R(x_f),
$$

while

$$
W_R(C;x_f,x_i)
\mapsto U_R^{-1}(x_f)W_R(C;x_f,x_i)U_R(x_i),
$$

and

$$
\phi(x_i)\mapsto U_R^{-1}(x_i)\phi(x_i).
$$

All endpoint rotations cancel.

This construction has a simple physical meaning. The Wilson line transports the gauge index from one point to another so that the two charged insertions can be compared and contracted. Without that transporter, the product $\phi^\dagger(x_f)\phi(x_i)$ would compare vectors in different internal frames without specifying how to identify those frames.

## Charged operators and Gauss law

A local charged field is not a gauge-invariant operator. This statement sounds strange at first because particle physicists constantly talk about electron fields, quark fields, and charged creation operators. The point is that the elementary field variable is not itself the same thing as a physical, gauge-invariant observable.

For QED,

$$
\psi(x)\mapsto e^{-iq\alpha(x)}\psi(x).
$$

No local expression equal to “just one charged field plus local photon fields at the same point” can make this transformation disappear for arbitrary compactly supported $\alpha(x)$. The reason is Gauss law. A charged excitation is accompanied by electric flux. The flux cannot be compressed into a strictly local gauge-invariant operator at one point.

There are three common ways this issue appears.

First, neutral local composites are gauge invariant. Examples include positronium-like bilinears, meson-like operators, and local currents such as

$$
j^\mu=q\bar\psi\gamma^\mu\psi.
$$

Second, separated charged fields can be connected by a Wilson line, producing a gauge-invariant but path-dependent extended operator. In Abelian notation, a schematic gauge-invariant pair is

$$
\bar\psi(y)\exp\left[-iq\int_x^y dz^\mu A_\mu(z)\right]\psi(x).
$$

Third, a single charged operator can be dressed by a nonlocal electromagnetic cloud extending to infinity or to a boundary. Such dressings create states in charged sectors. They are invariant under proper gauge transformations that vanish at the boundary, but they can transform under global asymptotic symmetries. That transformation is physical: it is the electric charge.

So the better statement is not “charged particles are impossible.” The better statement is:

$$
\text{charge is not created by a strictly local gauge-invariant operator in an isolated gauge theory.}
$$

Charged sectors exist, but their operators know about long-range fields, boundaries, or endpoints.

## Gauge-invariant actions versus observables

A Lagrangian density should be gauge invariant up to total derivatives, but a gauge-invariant term in the action is not automatically a directly measurable observable. These are related but distinct questions.

For example,

$$
\mathcal L_{\mathrm{YM}}
=-\frac12\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
$$

is gauge invariant and defines the classical Yang–Mills dynamics. The local density $\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})$ is also a gauge-invariant local operator. By contrast, a gauge-fixing term such as

$$
-\frac{1}{2\xi}(\partial_\mu A^\mu)^2
$$

is useful in quantization but is not a physical observable. It deliberately depends on a choice of gauge coordinate.

Similarly, a gauge-dependent propagator can be a useful computational object. The photon propagator in covariant gauge contains a gauge parameter $\xi$. Individual Green functions of $A_\mu$ can depend on $\xi$, while physical S-matrix elements, gauge-invariant correlation functions, and properly inclusive observables do not.

The rule is not “never use gauge-dependent quantities.” That would make calculations miserable. The rule is: gauge-dependent quantities may appear inside a calculation, but the final physical question must be gauge invariant.

## Boundary symmetries and large transformations

The quotient $\mathcal C/\mathcal G_0$ depends on what is included in $\mathcal G_0$. Usually $\mathcal G_0$ means gauge transformations that are continuously connected to the identity and vanish sufficiently fast at the boundary or act trivially on boundary data. These are redundancies.

Transformations that do not vanish at the boundary can act on physical states. In electrodynamics, the constant transformation at spatial infinity is associated with electric charge. In non-Abelian gauge theory, boundary transformations, center transformations, and large gauge transformations can carry physical information depending on spacetime, boundary conditions, and global form of the gauge group.

This gives a useful refinement:

| Transformation type | Usually treated as | Observable response |
|---|---|---|
| Proper gauge transformation | Redundancy | Physical observables invariant. |
| Boundary global transformation | Physical symmetry | Charged operators or states may transform. |
| Large gauge transformation | Context-dependent | May label sectors, impose quantization, or act as a symmetry. |

The local pages in this chapter mostly use the first row. Later chapters return to the other rows because they are essential for theta angles, anomalies, Wilson and ’t Hooft lines, center symmetry, and confinement.

## How to check gauge invariance

Here is a practical checklist.

Start by identifying the transformation laws of every factor. For local matter fields, write the representation matrices explicitly. For field strengths, remember that non-Abelian $F_{\mu\nu}$ transforms by conjugation.

Then check whether every gauge rotation cancels. For local products, all representation indices must be contracted with invariant tensors. For Wilson lines, endpoint rotations must either be traced, canceled by charged endpoint fields, or left at a boundary where they represent a physical charge.

Finally, ask whether the expression depends on a gauge choice. If the object contains a gauge-fixing function, a polarization vector chosen by a gauge condition, or an undressed gauge potential, it may still be a useful intermediate quantity, but it is not yet a physical observable.

A compact version is:

$$
\begin{array}{ccl}
\text{local charged field} &:& \text{not gauge invariant},\\
\text{local singlet composite} &:& \text{gauge invariant},\\
\text{non-Abelian }F_{\mu\nu}^a &:& \text{covariant component, not invariant},\\
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}) &:& \text{gauge invariant},\\
\text{open Wilson line} &:& \text{not invariant unless endpoints are handled},\\
\text{closed traced Wilson loop} &:& \text{gauge invariant}.
\end{array}
$$

## Common pitfalls

**Pitfall 1: treating gauge-dependent fields as directly observable.** The potential $A_\mu$ is indispensable, but it is not itself gauge invariant. In Abelian theory $F_{\mu\nu}$ is invariant; in non-Abelian theory traces or complete contractions are needed.

**Pitfall 2: saying “Elitzur’s theorem means gauge symmetry cannot break, so the Higgs mechanism is impossible.”** The correct lesson is that a local gauge redundancy is not a physical symmetry that breaks in the same way as a global symmetry. Gauge-invariant diagnostics of the Higgs regime exist, but the naive expectation value of a charged field is gauge dependent.

**Pitfall 3: forgetting endpoints of Wilson lines.** An open Wilson line transforms at both endpoints. It is not gauge invariant until those endpoint transformations are traced, canceled by charged fields, or interpreted as boundary charges.

**Pitfall 4: assuming every gauge-invariant object is local.** Wilson loops, ’t Hooft loops, surface operators, and dressed charged operators are extended. Gauge theory forces us to take extended observables seriously.

**Pitfall 5: ignoring boundary conditions.** Whether a transformation is redundancy or physical symmetry depends on boundary conditions. This is why the same local gauge theory can have different charge sectors and different line-operator spectra.

## Relations to other pages

This page completes the first pass through the Gauge Principle chapter. [Gauge Redundancy Revisited](/gauge-theories-standard-model/gauge-principle/gauge-redundancy-revisited/) explains why observables must live on gauge orbits. [Gauge Fields as Connections](/gauge-theories-standard-model/gauge-principle/gauge-fields-as-connections/) and [Field Strength and Curvature](/gauge-theories-standard-model/gauge-principle/field-strength-and-curvature/) explain the local objects whose traces appear here. [Matter Representations](/gauge-theories-standard-model/gauge-principle/matter-representations/) explains how to contract gauge indices.

The QED chapter uses these ideas in the simplest dynamical gauge theory. The Yang–Mills chapter uses them in the non-Abelian theory where Wilson loops, color traces, and gauge-boson self-interactions become unavoidable. The Wilson Loops and Confinement chapter returns to line operators as diagnostics of phases. The Symmetry, Anomalies, and Topology volume develops the modern language of generalized symmetries and extended operators.

## Research status

The basic criterion for proper gauge invariance is settled textbook material. What remains subtle and active is not the local algebraic statement, but the global organization of observables.

Important refinements include the global form of the gauge group, the spectrum of allowed Wilson and ’t Hooft lines, higher-form symmetries, boundary charges, asymptotic symmetries, non-invertible defects, and the relation between gauge theory and extended topological operators. In modern gauge theory, “what are the genuine observables?” is often part of the definition of the theory, not a detail added afterward.

## Exercises

### Exercise 1: Non-Abelian field strength is covariant, not invariant

Let $F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U$. Show that $\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})$ is gauge invariant, but that the components $F_{\mu\nu}^a$ are not gauge invariant in general.

<details><summary><strong>Solution</strong></summary>

Using cyclicity of the trace,

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
\mapsto
\operatorname{tr}(U^{-1}F_{\mu\nu}UU^{-1}F^{\mu\nu}U)
=
\operatorname{tr}(U^{-1}F_{\mu\nu}F^{\mu\nu}U)
=
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

The components $F_{\mu\nu}^a$ are defined only after choosing a basis $T^a$ for the Lie algebra. Under conjugation, $U^{-1}F_{\mu\nu}U$ generally rotates this basis. Infinitesimally, for $U=e^{i\theta^aT^a}$,

$$
\delta F_{\mu\nu}^a=-f^{abc}\theta^bF_{\mu\nu}^c
$$

up to the convention for the infinitesimal parameter. Thus the components transform in the adjoint representation; they are covariant data, not invariant observables.

</details>

### Exercise 2: Transformation of a Wilson line

Given

$$
W_R(C;y,x)=P\exp\left[-ig\int_x^y dz^\mu A_\mu^a(z)T_R^a\right],
$$

show that under a gauge transformation it transforms as

$$
W_R(C;y,x)\mapsto U_R^{-1}(y)W_R(C;y,x)U_R(x).
$$

<details><summary><strong>Solution</strong></summary>

Parametrize the curve by $z^\mu(s)$ with $s\in[0,1]$, $z(0)=x$, and $z(1)=y$. The Wilson line is the solution to

$$
\frac{d}{ds}W(s,0)=-ig\dot z^\mu(s)A_\mu(z(s))W(s,0),
\qquad
W(0,0)=\mathbf 1.
$$

Define

$$
W^U(s,0)=U^{-1}(z(s))W(s,0)U(z(0)).
$$

Differentiate this expression. Using

$$
A_\mu^U=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U,
$$

one finds

$$
\frac{d}{ds}W^U(s,0)=-ig\dot z^\mu(s)A_\mu^U(z(s))W^U(s,0),
$$

with $W^U(0,0)=\mathbf 1$. By uniqueness of the solution to this first-order equation,

$$
W_R^U(C;y,x)=U_R^{-1}(y)W_R(C;y,x)U_R(x).
$$

</details>

### Exercise 3: Gauge invariance of an open-line composite

Let $\phi$ transform as $\phi\mapsto U_R^{-1}\phi$. Show that

$$
\phi^\dagger(y)W_R(C;y,x)\phi(x)
$$

is gauge invariant.

<details><summary><strong>Solution</strong></summary>

The conjugate field transforms as

$$
\phi^\dagger(y)\mapsto \phi^\dagger(y)U_R(y).
$$

The Wilson line transforms as

$$
W_R(C;y,x)\mapsto U_R^{-1}(y)W_R(C;y,x)U_R(x),
$$

and the field at $x$ transforms as

$$
\phi(x)\mapsto U_R^{-1}(x)\phi(x).
$$

Multiplying the three transformed factors gives

$$
\phi^\dagger(y)U_R(y)
U_R^{-1}(y)W_R(C;y,x)U_R(x)
U_R^{-1}(x)\phi(x)
=
\phi^\dagger(y)W_R(C;y,x)\phi(x).
$$

</details>

### Exercise 4: Why a single charged field is not local and gauge invariant

In Abelian gauge theory, suppose $\psi(x)\mapsto e^{-iq\alpha(x)}\psi(x)$. Explain why $\psi(x)$ is not gauge invariant, and why multiplying it by a local polynomial in $F_{\mu\nu}(x)$ cannot make it gauge invariant.

<details><summary><strong>Solution</strong></summary>

The field transforms with a local phase:

$$
\psi(x)\mapsto e^{-iq\alpha(x)}\psi(x).
$$

The field strength $F_{\mu\nu}$ is already gauge invariant in Abelian theory, so any local polynomial $P(F,\partial F,\ldots)$ is also invariant. Therefore

$$
P(F,\partial F,\ldots)(x)\psi(x)
\mapsto
 e^{-iq\alpha(x)}P(F,\partial F,\ldots)(x)\psi(x).
$$

The phase remains. To cancel it, one needs either another oppositely charged local field, an open Wilson line ending on another charged field, or a nonlocal dressing that extends to a boundary or infinity.

</details>

## References

- Srednicki, *Quantum Field Theory*, especially the chapters on Maxwell theory, spinor electrodynamics, non-Abelian gauge theory, BRST symmetry, anomalies, and Wilson loops.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 8 and 25, for gauge invariance, Wilson lines, Yang–Mills theory, and the connection to observable quantities.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Ch. 15, for a systematic treatment of non-Abelian gauge invariance, constraints, and quantization.
- Polyakov, *Gauge Fields and Strings*, for the nonperturbative importance of Wilson loops and gauge-theory observables.
- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for the modern viewpoint on extended operators and higher-form global symmetries.

## Version history

- **2026-06-17:** Initial polished draft. Added local observables, Wilson lines, Wilson loops, charged dressings, boundary caveats, and exercises.
