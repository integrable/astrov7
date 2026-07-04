---
title: "Locally Covariant Fields"
description: "Defines locally covariant quantum fields as natural transformations compatible with spacetime embeddings."
sidebar:
  label: "Locally Covariant Fields"
  order: 6
level: Advanced
status: "Polished draft"
source: "Brunetti–Fredenhagen–Verch local covariance; Hollands–Wald local covariant fields."
topics:
  - locally covariant fields
  - natural transformations
  - curved spacetime QFT
  - algebraic QFT
canonicalTopics:
  - locally-covariant-fields
  - locally-covariant-quantum-field-theory
  - qft-on-curved-spacetimes
researchStatus:
  established:
    - "In locally covariant QFT, fields can be formulated as natural transformations from test-function functors to the observable-algebra functor."
  active:
    - "Composite fields, gauge fields, boundaries, and renormalized stress tensors require additional choices and sometimes enriched target categories."
---

## Summary

A locally covariant field is a field assignment that is compatible with every admissible spacetime embedding. In the functorial framework, a theory is a covariant functor

$$
\mathcal A:\mathsf{Loc}\longrightarrow \mathsf{Alg},
$$

and a scalar field is not just a family of maps $\Phi_M:C_c^\infty(M)\to \mathcal A(M)$. It is a family satisfying the naturality condition

$$
\mathcal A(\psi)\bigl(\Phi_M(f)\bigr)
=
\Phi_N(\psi_*f)
$$

for every admissible embedding $\psi:M\to N$ and every test function $f\in C_c^\infty(M)$. Equivalently, the following square commutes:

$$
\begin{array}{ccc}
\mathcal D(M)&\xrightarrow{\ \Phi_M\ }&\mathcal A(M)\\
\mathcal D(\psi)\downarrow&&\downarrow\mathcal A(\psi)\\
\mathcal D(N)&\xrightarrow{\ \Phi_N\ }&\mathcal A(N).
\end{array}
$$

Here $\mathcal D$ is a test-object functor, usually sending $M$ to compactly supported test functions, densities, or test sections of a bundle. For tensor fields, spinor fields, currents, and stress tensors, $\mathcal D(M)$ is replaced by the appropriate compactly supported test sections.

The slogan is:

$$
\text{field}=
\text{natural transformation from test data to observables}.
$$

This page explains the definition, the free scalar example, and why local covariance is stronger than merely writing tensor indices correctly.

## Prerequisites

You should know [QFT as a Functor on Spacetimes](/rigorous-qft/locally-covariant-qft/qft-as-functor-on-spacetimes/), [Globally Hyperbolic Spacetimes](/rigorous-qft/locally-covariant-qft/globally-hyperbolic-spacetimes/), and [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/). For the distributional side of the definition, review [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) and [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/).

## Core idea

A quantum field on one spacetime is already subtle: it is usually an operator-valued distribution, not an operator at a point. In curved-spacetime QFT there is an additional subtlety. The symbol $\Phi$ should not mean a different, unrelated field on each spacetime. It should mean one field construction that behaves consistently when one spacetime is embedded into another.

Suppose $M$ is a globally hyperbolic spacetime sitting as a causally convex subspacetime of $N$. A compactly supported test function $f$ on $M$ can be pushed forward to a compactly supported test function $\psi_*f$ on $N$, extended by zero outside the image of $M$. The field smeared with $f$ in the small spacetime should agree with the field smeared with $\psi_*f$ in the large spacetime after the observable algebra of $M$ is embedded into that of $N$.

This is not a slogan about general covariance. It is a commuting diagram.

<figure class="doc-figure" style="--figure-width: 45rem;">

![Naturality square defining a locally covariant field](/figures/rigorous-qft/locally-covariant-field-natural-transformation.svg)

<figcaption>

A locally covariant scalar field is a natural transformation $\Phi:\mathcal D\Rightarrow\mathcal A$. Pushing the test function forward and then applying the field gives the same observable as first applying the field and then embedding the observable algebra.

</figcaption>
</figure>

## Setup and conventions

Let $\mathsf{Loc}$ be the category whose objects are oriented and time-oriented globally hyperbolic Lorentzian spacetimes and whose morphisms are admissible causal isometric embeddings. Let

$$
\mathcal A:\mathsf{Loc}\to\mathsf{Alg}
$$

be a locally covariant QFT satisfying the usual covariance and causality assumptions.

For a scalar field, define a test-function functor

$$
\mathcal D:\mathsf{Loc}\to\mathsf{Vec}
$$

by

$$
\mathcal D(M)=C_c^\infty(M).
$$

For an embedding $\psi:M\to N$, the pushforward is

$$
(\psi_*f)(y)=
\begin{cases}
 f(\psi^{-1}(y)),&y\in\psi(M),\\
 0,&y\notin\psi(M).
\end{cases}
$$

The compact support of $f$ and the causal convexity of $\psi(M)$ are important. They ensure that the pushed-forward test function is a legitimate smearing function on $N$ and that causal propagation behaves as expected.

A locally covariant scalar field is a natural transformation

$$
\Phi:\mathcal D\Rightarrow\mathcal A,
$$

meaning a family of maps

$$
\Phi_M:C_c^\infty(M)\to\mathcal A(M)
$$

such that for every morphism $\psi:M\to N$,

$$
\mathcal A(\psi)\circ \Phi_M
=
\Phi_N\circ \psi_*.
$$

In element notation,

$$
\mathcal A(\psi)(\Phi_M(f))
=
\Phi_N(\psi_*f).
$$

For a linear scalar field, each $\Phi_M$ is linear in $f$. For Wick powers or nonlinear composite fields, the map from test functions to algebra elements may still be linear in the smearing function but nonlinear in the underlying basic field. For tensor fields one replaces $C_c^\infty(M)$ by compactly supported test tensor densities or compactly supported sections of a dual bundle.

## The naturality condition

The naturality condition is the whole definition in one line:

$$
\boxed{
\mathcal A(\psi)(\Phi_M(f))=\Phi_N(\psi_*f).
}
$$

It says that the two procedures below give the same observable in $\mathcal A(N)$.

| Procedure | Result |
|---|---|
| First make the observable in $M$, then embed the algebra. | $\mathcal A(\psi)(\Phi_M(f))$ |
| First push the smearing function into $N$, then make the observable there. | $\Phi_N(\psi_*f)$ |

This is the curved-spacetime replacement for a familiar flat-spacetime covariance law. In Minkowski space, a Poincaré transformation $g$ acts by

$$
U(g)\Phi(f)U(g)^{-1}=\Phi(g_*f),
$$

where $U(g)$ is a unitary implementing the symmetry. In locally covariant QFT, one does not assume a symmetry group acting on one spacetime. Instead, each admissible embedding $\psi:M\to N$ induces an algebra map $\mathcal A(\psi)$, and the field must be compatible with all such maps.

## Free scalar example

The free scalar field is the template. Let

$$
P_M=\Box_g+m^2+\xi R
$$

be the Klein–Gordon operator on $M$ in the mostly-minus convention used in this volume. On a globally hyperbolic spacetime, $P_M$ has advanced and retarded Green operators under the standard hypotheses for normally hyperbolic operators. Their difference is the causal propagator

$$
E_M=E_M^{\mathrm{ret}}-E_M^{\mathrm{adv}}.
$$

The field algebra $\mathcal A(M)$ is generated by symbols $\Phi_M(f)$, $f\in C_c^\infty(M)$, subject to the relations

$$
\Phi_M(af+bg)=a\Phi_M(f)+b\Phi_M(g),
$$

$$
\Phi_M(P_M f)=0,
$$

$$
\Phi_M(f)^*=\Phi_M(\overline f),
$$

and

$$
[\Phi_M(f),\Phi_M(g)]
=iE_M(f,g)\mathbf 1.
$$

Here

$$
E_M(f,g)=\int_M f\,(E_Mg)\,d\operatorname{vol}_g,
$$

up to the harmless convention of whether test functions are treated as functions or densities.

If $\psi:M\to N$ is an admissible embedding, define the algebra map on generators by

$$
\mathcal A(\psi)(\Phi_M(f))=\Phi_N(\psi_*f).
$$

For this to be well-defined, the defining relations in $M$ must be preserved in $N$. The key analytic facts are that admissible embeddings preserve the differential operator on the image and preserve the causal propagator on causally convex subspacetimes:

$$
P_N\psi_*f=\psi_*P_Mf,
$$

and

$$
E_N(\psi_*f,\psi_*g)=E_M(f,g).
$$

These identities are why global hyperbolicity and causal convexity are not decorative assumptions. They make the local algebraic construction independent of the ambient spacetime.

## Tensor, spinor, and composite fields

The scalar example hides an important point: the test object should match the geometric type of the field.

A vector current $J^\mu$ is naturally smeared with a compactly supported one-form or vector density, depending on conventions. A stress tensor $T^{\mu\nu}$ is naturally smeared with a compactly supported symmetric covariant tensor $h_{\mu\nu}$,

$$
T_M(h)=\int_M T_M^{\mu\nu}h_{\mu\nu}\,d\operatorname{vol}_g.
$$

A spinor field requires a spin-spacetime category: the objects include spin structures and the morphisms preserve the spin data. The corresponding test functor uses compactly supported sections of the dual spinor bundle. The naturality condition is the same idea, but the pushforward includes the bundle map covering the spacetime embedding.

Composite fields are subtler. The Wick square $:\!\Phi^2\!:_M$, Wick powers, time-ordered products, and the stress tensor are not obtained by multiplying fields at a point. They require renormalization. Local covariance imposes strong restrictions on the allowed finite renormalization freedoms, but it does not remove them all. In four dimensions, for example, the Wick square of a massive scalar field has finite curvature-dependent ambiguities of the schematic form

$$
:\!\Phi^2\!:_M
\longmapsto
:\!\Phi^2\!:_M
+
(c_1m^2+c_2R_M)\mathbf 1.
$$

The important point is not the exact list on this page. The important point is structural: admissible renormalization ambiguities must themselves be local and covariant.

## Locality versus local covariance

Locality and local covariance are different requirements.

Locality says that observables associated with causally disjoint regions commute. For a scalar field this appears as

$$
[\Phi_M(f),\Phi_M(g)]=0
\quad\text{if}\quad
\operatorname{supp}f\perp\operatorname{supp}g.
$$

Local covariance says that the field assignment is compatible with embeddings between spacetimes:

$$
\mathcal A(\psi)(\Phi_M(f))=\Phi_N(\psi_*f).
$$

Both are needed. A family of fields could be local on each spacetime but chosen in a way that is not natural across embeddings. Conversely, a natural assignment might fail to have causal commutation relations if the underlying theory does not satisfy Einstein causality.

## Relation to relative Cauchy evolution

Locally covariant fields also interact with metric response. If the theory has relative Cauchy evolution, then a field should respond to a compact metric perturbation in a way compatible with the same naturality principles.

For a stress tensor, this relation becomes especially sharp. The previous page defined the infinitesimal metric response by

$$
\delta_M[h](A)
=
\left.\frac{d}{ds}\right|_{s=0}\operatorname{rce}_M[sh](A).
$$

When a locally covariant stress tensor exists, it implements this response by

$$
\delta_M[h](A)=\frac{i}{2}[T_M(h),A].
$$

Thus the stress tensor is not only a tensor field in the index sense. It is a locally covariant field whose definition is tied to the functorial behavior of the whole theory under changes of background geometry.

## Checks

A proposed locally covariant field should pass the following tests.

| Check | Question | Failure mode |
|---|---|---|
| Naturality | Does $\mathcal A(\psi)(\Phi_M(f))=\Phi_N(\psi_*f)$ hold for every admissible $\psi$? | The field is defined separately on each spacetime but is not one global construction. |
| Support | Is $\Phi_M(f)$ localized in the causal hull of $\operatorname{supp}f$? | The field assignment is nonlocal. |
| Field equation | For a free field, does $\Phi_M(P_Mf)=0$ hold? | The smearing does not descend to solutions modulo equations of motion. |
| Commutator | Is the commutator controlled by the causal propagator? | The field violates Einstein causality or the CCR. |
| Renormalization | Are finite ambiguities themselves local and covariant? | Counterterms depend on arbitrary coordinates or nonlocal data. |

The most common useful check is the free scalar field. If a formula fails for the free scalar, it is almost certainly not the right locally covariant definition.

## Common pitfalls

**Thinking naturality is just tensor transformation.** Tensor indices tell you how components change under coordinate changes. Naturality tells you how fields on different spacetimes are related by algebra maps and pushforwards of test data.

**Forgetting smearing.** The map is not $x\mapsto\Phi_M(x)$ as an operator-valued function. It is a map from compactly supported test data to algebra elements.

**Using arbitrary embeddings.** The standard spacetime morphisms are not arbitrary smooth maps. They preserve the Lorentzian metric, orientations, time orientations, and causal convexity conditions needed for local physics.

**Assuming a preferred Hilbert space.** The locally covariant field is defined at the algebraic level. Hilbert spaces appear after choosing states and representations.

**Expecting renormalization to be unique.** Local covariance restricts finite counterterms, but it does not eliminate all finite renormalization freedom. Curvature-dependent terms are often allowed.

**Ignoring gauge structure.** Gauge potentials, ghosts, BRST fields, and charged fields may require enriched frameworks. The observable net alone may not contain every field used in a Lagrangian presentation.

## Relations to other pages

[QFT as a Functor on Spacetimes](/rigorous-qft/locally-covariant-qft/qft-as-functor-on-spacetimes/) defines the theory functor $\mathcal A$. This page defines fields as natural transformations associated with that functor.

[Relative Cauchy Evolution](/rigorous-qft/locally-covariant-qft/relative-cauchy-evolution/) and [Stress Tensor from Local Covariance](/rigorous-qft/locally-covariant-qft/stress-tensor-from-local-covariance/) explain how metric response becomes an algebraic automorphism and how the stress tensor can generate its infinitesimal form.

[Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) explains why fields must be smeared. [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) gives the technical language used later to control products and Hadamard singularities.

[QFT in Curved Spacetime: Rigorous View](/rigorous-qft/locally-covariant-qft/qft-in-curved-spacetime-rigorous-view/) places locally covariant fields inside the larger physical and mathematical framework of quantum fields on classical curved backgrounds.

## Research status

The natural-transformation formulation of locally covariant fields is established and is one of the cleanest conceptual achievements of locally covariant QFT. It gives a coordinate-free, representation-independent way to say that a symbol such as $\Phi$, $J^\mu$, or $T^{\mu\nu}$ denotes the same field construction on all admissible spacetimes.

The deeper research issues concern enrichment. Composite fields require renormalization and curvature counterterms. Gauge theories require BRST/BV or related structures. State spaces cannot generally be chosen by a single locally covariant preferred vacuum. Quantum gravity and fluctuating causal structure are outside the basic framework, though perturbative locally covariant approaches exist.

## Exercises

1. **Naturality for a subspacetime.** Let $\psi:M\to N$ be an admissible embedding and let $f\in C_c^\infty(M)$. Explain why the formula $\mathcal A(\psi)(\Phi_M(f))=\Phi_N(\psi_*f)$ says more than coordinate covariance.

<details><summary><strong>Solution</strong></summary>

Coordinate covariance compares descriptions of the same object in different coordinate charts. Naturality compares the field assignment on two possibly different spacetimes connected by an admissible embedding. The equality says that the algebra element obtained from $f$ in $M$ becomes exactly the algebra element obtained from the pushed-forward test function in $N$. It is a compatibility condition between the test-function functor and the observable-algebra functor.

</details>

2. **CCR preservation.** Suppose the free scalar field satisfies $E_N(\psi_*f,\psi_*g)=E_M(f,g)$. Show that the map $\mathcal A(\psi)(\Phi_M(f))=\Phi_N(\psi_*f)$ preserves the canonical commutation relation.

<details><summary><strong>Solution</strong></summary>

In $M$ the relation is

$$
[\Phi_M(f),\Phi_M(g)]=iE_M(f,g)\mathbf 1.
$$

Applying $\mathcal A(\psi)$ gives

$$
[\mathcal A(\psi)\Phi_M(f),\mathcal A(\psi)\Phi_M(g)]
=iE_M(f,g)\mathbf 1.
$$

Using the proposed definition of $\mathcal A(\psi)$, the left side is

$$
[\Phi_N(\psi_*f),\Phi_N(\psi_*g)].
$$

The CCR in $N$ gives this as $iE_N(\psi_*f,\psi_*g)\mathbf 1$, which equals $iE_M(f,g)\mathbf 1$ by assumption. Thus the commutation relation is preserved.

</details>

3. **Curvature ambiguity.** Why is a finite ambiguity proportional to $R_M\mathbf 1$ in a Wick square more compatible with local covariance than an ambiguity proportional to an arbitrarily chosen function $u_M(x)\mathbf 1$?

<details><summary><strong>Solution</strong></summary>

The scalar curvature $R_M$ is constructed locally and covariantly from the metric. Under an admissible embedding, it pulls forward consistently with the embedded geometry. An arbitrary function $u_M$ chosen separately on each spacetime has no reason to satisfy such compatibility. It would make the field depend on non-geometric auxiliary choices rather than on the locally covariant spacetime data.

</details>

## References

- Romeo Brunetti, Klaus Fredenhagen, and Rainer Verch, "The Generally Covariant Locality Principle – A New Paradigm for Local Quantum Physics," *Communications in Mathematical Physics* **237** (2003), 31–68. DOI: [10.1007/s00220-003-0815-7](https://doi.org/10.1007/s00220-003-0815-7), arXiv: [math-ph/0112041](https://arxiv.org/abs/math-ph/0112041).
- Stefan Hollands and Robert M. Wald, "Local Wick Polynomials and Time Ordered Products of Quantum Fields in Curved Spacetime," *Communications in Mathematical Physics* **223** (2001), 289–326. DOI: [10.1007/s002200100540](https://doi.org/10.1007/s002200100540), arXiv: [gr-qc/0103074](https://arxiv.org/abs/gr-qc/0103074).
- Stefan Hollands and Robert M. Wald, "Existence of Local Covariant Time Ordered Products of Quantum Fields in Curved Spacetime," *Communications in Mathematical Physics* **231** (2002), 309–345. DOI: [10.1007/s00220-002-0719-y](https://doi.org/10.1007/s00220-002-0719-y), arXiv: [gr-qc/0111108](https://arxiv.org/abs/gr-qc/0111108).
- Christopher J. Fewster and Rainer Verch, "Algebraic Quantum Field Theory in Curved Spacetimes," in *Advances in Algebraic Quantum Field Theory*, Springer, 2015. DOI: [10.1007/978-3-319-21353-8_4](https://doi.org/10.1007/978-3-319-21353-8_4), arXiv: [1504.00586](https://arxiv.org/abs/1504.00586).
- Stefan Hollands and Robert M. Wald, "Quantum Fields in Curved Spacetime," *Physics Reports* **574** (2015), 1–35. arXiv: [1401.2026](https://arxiv.org/abs/1401.2026).

## Version history

- **2026-06-29:** Initial polished draft.
