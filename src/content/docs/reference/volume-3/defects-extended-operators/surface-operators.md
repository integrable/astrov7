---
title: "Surface Operators"
description: "Surface operators as two-dimensional extended insertions, codimension-two singular defects, one-form symmetry generators, Gukov–Witten defects, and bulk-coupled two-dimensional systems."
sidebar:
  label: "Surface Operators"
  order: 4
level: Advanced
status: "Polished draft"
source: "Gukov–Witten on surface operators; Gaiotto–Kapustin–Seiberg–Willett; Kapustin on line operators; standard gauge-theory, topology, and generalized-symmetry references."
topics:
  - surface operators
  - codimension-two defects
  - Gukov–Witten surface operators
  - one-form symmetry
  - disorder operators
  - topological surfaces
  - defect degrees of freedom
canonicalTopics:
  - surface-operator
  - codimension-two-defect
  - gukov-witten-surface-operator
  - one-form-symmetry-surface
  - defect-qft
researchStatus:
  established:
    - "Surface operators are standard extended insertions supported on two-dimensional submanifolds and may be defined by local couplings, singular boundary conditions, or intrinsic defect degrees of freedom."
    - "In four-dimensional gauge theory, codimension-two surface operators include holonomy defects and topological surfaces generating one-form symmetries."
  active:
    - "Surface defects remain active in supersymmetric duality, geometric Langlands, class-S theories, higher-form symmetry, noninvertible symmetry, and defect RG."
---

## Summary

A surface operator is an operator supported on a two-dimensional submanifold $\Sigma$. The phrase sounds simple, but it covers several genuinely different constructions:

- an ordinary exponential of a two-form operator integrated over $\Sigma$,
- a **codimension-two disorder defect** defined by a singularity around $\Sigma$,
- a topological surface generating a one-form symmetry,
- an intrinsic two-dimensional QFT coupled to the surrounding bulk fields,
- in lower-dimensional settings, a two-dimensional interface or boundary; in four-dimensional gauge theory, the main focus here is instead codimension-two monodromy data.

In four-dimensional gauge theory the most important surface operators are codimension-two defects. If $\varphi$ is the angular coordinate around a small circle linking the surface, a basic abelian singularity is

$$
A\sim \alpha\,d\varphi,
\qquad
\operatorname{Hol}_{S^1_{\rm link}}(A)=e^{2\pi i\alpha}.
$$

This is the surface-operator analog of the magnetic singularity that defines an ’t Hooft line. A surface can also be topological: for example, a center one-form symmetry surface links with Wilson lines and multiplies them by their center charge.

<figure class="doc-figure" style="--figure-width: 62rem;">

![Surface-operator diagram showing a two-dimensional defect surface, normal linking circle, holonomy parameter, one-form symmetry linking with Wilson lines, and possible intrinsic defect degrees of freedom.](/figures/symmetry-anomalies-topology/surface-operator-monodromy.svg)

<figcaption>

A surface operator is supported on a two-dimensional submanifold $\Sigma$. Codimension-two examples are controlled by data on a small linking circle; topological surface operators can generate one-form symmetries by linking with line operators.

</figcaption>
</figure>

## Prerequisites

Read [Local Versus Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/local-versus-extended-operators/), [Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/), and [’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/) first. You should also know the background-field viewpoint from [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/) and the finite-energy topology logic from [Topology of Field Configurations](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/topology-of-field-configurations/).

## Setup and conventions

Let $\Sigma\subset M_d$ be an oriented two-dimensional submanifold. Its codimension is

$$
\operatorname{codim}\Sigma=d-2.
$$

The most common gauge-theory setting is $d=4$, where $\Sigma$ has codimension two. A small transverse linking sphere is then a circle,

$$
S^1_{\rm link}.
$$

With the volume convention

$$
D=d-iA,
\qquad
F=dA-iA\wedge A,
$$

a codimension-two singularity is often described by prescribing the holonomy of $A$ around this small linking circle.

:::note[Convention-sensitive source note]
For codimension-two defects, local formulas such as $A\sim \alpha d\varphi$ depend on the normalization of $A$ and the periodicity of $\varphi$. The invariant datum is the conjugacy class of the linking holonomy $\exp(2\pi i\alpha)$, together with any additional defect couplings.
:::

## Four meanings of surface operator

The phrase "surface operator" is overloaded. A reliable page should separate the meanings.

### Integrated local operator

If $B$ is a two-form field or composite two-form operator, one can define

$$
\mathcal O_\lambda(\Sigma)=\exp\!\left(i\lambda\int_\Sigma B\right).
$$

This is an extended operator written directly in terms of local fields. It is an order-type surface operator.

### Disorder surface

A disorder surface specifies singular behavior of the bulk fields near $\Sigma$. For a gauge field in four dimensions, this often means fixing the conjugacy class of the holonomy around $S^1_{\rm link}$.

### Topological symmetry surface

A topological surface can be deformed freely as long as it does not cross charged operators. In four dimensions, the generator of a one-form symmetry is supported on a codimension-two surface, hence also on a two-dimensional surface.

### Defect QFT

One can place an honest two-dimensional theory on $\Sigma$ and couple it to the restriction of the bulk fields. This creates a surface defect whose dynamics need not be topological.

The same physical surface can combine several of these features: singular boundary conditions, local couplings, intrinsic degrees of freedom, and topological sectors. The taxonomy is useful precisely because real defects often mix these roles.

## Codimension-two singularity

In four-dimensional $U(1)$ gauge theory, a simple surface defect along $\Sigma$ is defined by

$$
A\sim \alpha\,d\varphi
$$

near $\Sigma$, where $\varphi\sim\varphi+2\pi$ is the angular coordinate in the normal plane. The linking holonomy is

$$
\exp\!\left(i\oint_{S^1_{\rm link}}A\right)=e^{2\pi i\alpha}.
$$

Therefore

$$
\alpha\sim \alpha+n,
\qquad n\in\mathbb Z,
$$

in a compact $U(1)$ theory. In distributional language one writes

$$
F=F_{\rm reg}+2\pi\alpha\,\delta_\Sigma,
$$

where $\delta_\Sigma$ is the Poincaré-dual two-form current supported on $\Sigma$. This equation should be read as a compact way of encoding the holonomy; it is not a license to multiply distributions without regularization.

For nonabelian $G$, choose $\alpha$ in a Cartan subalgebra and impose

$$
\operatorname{Hol}_{S^1_{\rm link}}(A)\in \text{conjugacy class of }\exp(2\pi i\alpha).
$$

The parameter is identified by the cocharacter lattice and the Weyl group. Equivalently,

$$
\alpha\in \mathfrak t/\Lambda_{\rm cochar},
\qquad
\alpha\sim w(\alpha),\quad w\in W_G.
$$

This is the codimension-two analog of the magnetic charge lattice for ’t Hooft lines.

## Electric surface couplings

A surface defect can also carry a two-dimensional theta-like coupling. In abelian language, one may insert

$$
U_\eta(\Sigma)=\exp\!\left(i\eta\int_\Sigma \frac{F}{2\pi}\right).
$$

If $F/2\pi$ has integral periods on closed two-cycles, then $\eta$ is periodic:

$$
\eta\sim\eta+2\pi.
$$

This is a surface analog of a Wilson phase. It weights gauge flux restricted to the surface rather than imposing holonomy around the surface.

For nonabelian defects the residual gauge group along $\Sigma$ can be reduced by the holonomy parameter $\alpha$. The precise theta-like parameters live in the character lattice of the unbroken subgroup. The slogan is again more useful than pretending the general formula is a one-liner:

$$
\text{codimension-two defects have magnetic holonomy data and electric two-dimensional theta data.}
$$

## Gukov–Witten surface operators

In four-dimensional $\mathcal N=4$ super Yang–Mills theory, a famous class of half-BPS surface operators is labeled, in a common semiclassical description, by parameters

$$
(\alpha,\beta,\gamma,\eta).
$$

Very roughly:

- $\alpha$ fixes the gauge-field holonomy around the linking circle,
- $\eta$ is a two-dimensional theta-like parameter on the surface,
- $\beta$ and $\gamma$ describe singular behavior of scalar fields normal to the surface in a supersymmetric construction.

For this volume, the important lesson is not the full supersymmetric construction. The lesson is that surface operators are legitimate extended defects with their own parameter spaces, duality transformations, and moduli. Under electric-magnetic duality, Wilson and ’t Hooft line labels are exchanged; similarly, surface-operator parameters can transform nontrivially under duality.

:::note[Scope note]
The full Gukov–Witten story belongs partly to supersymmetric gauge theory, geometric Langlands, and topological twists. This page only uses it as the canonical example showing that surface defects can have continuous parameters, singular boundary conditions, and duality actions.
:::

## One-form symmetry surfaces

The modern generalized-symmetry viewpoint makes surface operators unavoidable.

In $d$ dimensions, a $q$-form symmetry is generated by topological operators supported on codimension $q+1$ manifolds. For $q=1$ in $d=4$, the symmetry generator is supported on a two-dimensional surface $\Sigma$.

If $U_z(\Sigma)$ generates a finite center one-form symmetry and $W_R(C)$ is a Wilson line of center charge $q_R$, then

$$
U_z(\Sigma)W_R(C)
=
z^{q_R\operatorname{Link}(\Sigma,C)}W_R(C).
$$

Here $\operatorname{Link}(\Sigma,C)$ is the linking number of the surface and the line. Topological invariance means that $U_z(\Sigma)$ can be deformed without changing the correlator, unless it crosses $C$ or another charged defect.

This is the surface-operator version of a Ward identity. Instead of a conserved charge acting on a local operator, a topological surface links with an extended charged operator.

## Surface operators as charged objects

A surface can also be charged under a two-form symmetry. In that case the charged operator has dimension two, and the symmetry generator is supported on codimension three. In four spacetime dimensions that generator is a line.

So the same word "surface" can appear in two different generalized-symmetry roles:

| Role | Example in four dimensions | Symmetry relation |
| --- | --- | --- |
| Surface as generator | codimension-two topological surface | generates one-form symmetry |
| Surface as charged operator | two-dimensional charged object | charged under two-form symmetry |

The support dimension alone does not tell you whether a surface is a symmetry operator, a charged operator, or a non-topological defect. You must ask how it behaves under deformation and what it links with.

## Coupling intrinsic two-dimensional degrees of freedom

A surface defect can carry fields living only on $\Sigma$. For example, one can define

$$
Z[\Sigma]=\int \mathcal D\Phi_{\rm bulk}\,\mathcal D\chi_\Sigma\,
\exp\!\left(iS_{\rm bulk}[\Phi]+iS_\Sigma[\chi_\Sigma,\Phi|_\Sigma]\right),
$$

where $\chi_\Sigma$ are defect fields and $\Phi|_\Sigma$ denotes the pullback of bulk fields to the surface.

This construction is common in condensed matter, brane constructions, boundary CFT, supersymmetric defects, and anomaly inflow. The defect theory may have its own local operators, stress tensor, anomalies, RG flow, and topological sectors. It is not just a label attached to the bulk.

A defect with intrinsic degrees of freedom can screen or absorb the endpoints of line operators. This is one reason surface defects are central in line-operator algebra: a line may end on a surface if the defect supplies the missing charge.

## Fusion and endpoints

Surface operators can be fused by bringing two nearby surfaces together. If the surfaces are topological, fusion is often algebraic:

$$
U_a(\Sigma)U_b(\Sigma)=\sum_c N_{ab}^{\;c}U_c(\Sigma),
$$

with nonnegative integers $N_{ab}^{\;c}$ in favorable topological settings. For an ordinary finite one-form symmetry, fusion is group-like:

$$
U_a(\Sigma)U_b(\Sigma)=U_{ab}(\Sigma).
$$

For non-topological surface defects, fusion is an RG problem. Bringing defects together can generate local counterterms and flow to a new defect. The output need not be a simple product.

Surfaces can also have boundaries. If

$$
\partial\Sigma=C,
$$

then the boundary line $C$ must carry whatever charge or discontinuity is left by the surface. This is the extended-operator analog of saying that a branch cut must end on a disorder operator.

## Correlators and renormalization

Surface defects require renormalization. Even when the bulk theory is conformal, the defect can have its own defect beta functions. Local counterterms supported on $\Sigma$ include terms such as

$$
\int_\Sigma \sqrt{h},
\qquad
\int_\Sigma \sqrt{h}\,K^2,
\qquad
\int_\Sigma \Phi|_\Sigma,
$$

where $h$ is the induced metric and $K$ denotes extrinsic-curvature data. Which terms are allowed depends on dimension, symmetry, supersymmetry, and whether the surface is topological.

For topological surfaces, many metric-dependent counterterms are absent or $Q$-exact in a cohomological description, but framing or spin-structure subtleties can remain. For non-topological surfaces, expectation values often contain area-law divergences analogous to perimeter divergences for Wilson lines.

## Common pitfalls

### Confusing support dimension with codimension

A surface operator has two-dimensional support. In four dimensions it has codimension two, but in five dimensions it has codimension three. Generalized-symmetry roles depend on codimension as well as support dimension.

### Treating every surface as topological

Most surface operators are not topological. A surface defined by coupling a two-dimensional CFT to a four-dimensional bulk can depend on shape, metric, and defect RG scale.

### Forgetting the linking circle

Codimension-two disorder surfaces are controlled by holonomy around a small normal circle. If you forget this linking circle, the parameter $\alpha$ looks mysterious. It is just the angular holonomy seen by a tiny loop encircling the surface.

### Ignoring distributional subtleties

Writing $F=F_{\rm reg}+2\pi\alpha\delta_\Sigma$ is convenient. Products such as $F\wedge F$ in the presence of such singularities require a regularization or a more careful definition.

### Overgeneralizing Gukov–Witten parameters

The four-parameter label $(\alpha,\beta,\gamma,\eta)$ is not the universal definition of a surface operator. It is a special, extremely important supersymmetric class.

## Relations to nearby pages

- [’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/) gives the line-supported magnetic-disorder prototype.
- [Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/) gives the electric holonomy line prototype.
- [Disorder Operators](/symmetry-anomalies-topology/defects-extended-operators/disorder-operators/) will develop branch-cut and singular-boundary-condition definitions more generally.
- [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) explains why codimension-two topological surfaces generate one-form symmetries in four dimensions.
- [Symmetry TFT Idea](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/symmetry-tft-idea/) will repackage topological defects and their fusion in one-higher-dimensional language.

## Research status

Surface operators are standard objects in modern QFT, but the technology around them is still very alive. In supersymmetric theories they are tied to duality, localization, geometric Langlands, and class-S constructions. In generalized symmetry they are the basic topological operators of one-form symmetry in four dimensions. In condensed matter and topological phases they describe response sheets, domain walls, anyon-condensation interfaces, and defect degrees of freedom. In mathematical QFT they push one toward higher categories of defects. The small support dimension is deceptive: surface defects often carry enough structure to organize dualities, anomalies, and whole families of lower-dimensional theories.

## Exercises

### Exercise 1: Holonomy of an abelian surface operator

Let $A=\alpha d\varphi$ near a codimension-two surface in four dimensions, where $\varphi$ is the angular coordinate on the small linking circle. Compute the linking holonomy and show that $\alpha\sim\alpha+n$ for integer $n$ in compact $U(1)$ gauge theory.

<details><summary><strong>Solution</strong></summary>

The holonomy around the linking circle is

$$
\exp\!\left(i\oint A\right)
=
\exp\!\left(i\int_0^{2\pi}\alpha d\varphi\right)
=
e^{2\pi i\alpha}.
$$

If $\alpha$ is shifted by an integer $n$, then

$$
e^{2\pi i(\alpha+n)}=e^{2\pi i\alpha}.
$$

Thus $\alpha$ is periodic modulo integers. Geometrically, the shift is a large gauge transformation around the linking circle.

</details>

### Exercise 2: One-form symmetry linking

Suppose $U_z(\Sigma)$ is a topological surface generating a $\mathbb Z_N$ one-form symmetry, and $W_k(C)$ is a Wilson line of center charge $k\in\mathbb Z_N$. If $\operatorname{Link}(\Sigma,C)=1$, what is the Ward identity?

<details><summary><strong>Solution</strong></summary>

The topological surface acts by linking with the charged line:

$$
U_z(\Sigma)W_k(C)=z^k W_k(C).
$$

For $\mathbb Z_N$, one may take $z=e^{2\pi i/N}$, giving

$$
U_z(\Sigma)W_k(C)=e^{2\pi i k/N}W_k(C).
$$

If the linking number were $\ell$, the phase would be $e^{2\pi i k\ell/N}$.

</details>

### Exercise 3: Surface versus line disorder

Explain why an ’t Hooft line in four dimensions is controlled by flux through a linking $S^2$, while a codimension-two surface operator is controlled by holonomy around a linking $S^1$.

<details><summary><strong>Solution</strong></summary>

A line in four dimensions has codimension three. Removing the line leaves a transverse three-dimensional space, and a small sphere around the insertion is $S^2$. Magnetic charge is measured by integrating the two-form curvature over that $S^2$:

$$
\int_{S^2}F.
$$

A surface in four dimensions has codimension two. Its transverse space is two-dimensional, and a small loop around the insertion is $S^1$. The natural singular datum is the gauge holonomy around that loop:

$$
\exp\!\left(i\oint_{S^1}A\right).
$$

Both are linking data, but the linking manifold has different dimension because the defect codimension is different.

</details>

## References

- S. Gukov and E. Witten, "Gauge Theory, Ramification, and the Geometric Langlands Program," arXiv:hep-th/0612073.
- S. Gukov, "Surface Operators and Knot Homologies," arXiv:0706.2369.
- S. Gukov and E. Witten, "Rigid Surface Operators," arXiv:0804.1561.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, "Generalized Global Symmetries," arXiv:1412.5148.
- A. Kapustin, "Wilson–’t Hooft operators in four-dimensional gauge theories and S-duality," arXiv:hep-th/0501015.
- O. Aharony, N. Seiberg, and Y. Tachikawa, "Reading between the lines of four-dimensional gauge theories," arXiv:1305.0318.

## Version history

- 2026-06-19: First polished draft. Added surface-operator taxonomy, codimension-two holonomy defects, Gukov–Witten parameters, one-form symmetry surfaces, defect-QFT couplings, fusion, exercises, and figure.
