---
title: "Conformal Perturbation Theory"
description: "A guide to conformal perturbation theory: deforming a CFT by local operators, integrated OPE singularities, beta functions, anomalous dimensions, nearby fixed points, and scheme caveats."
sidebar:
  label: "Conformal Perturbation Theory"
  order: 50
level: Advanced
status: "Polished draft"
source: "Cardy; Zamolodchikov; Coleman 1985, Dilatations; Wilson and Kogut 1974; Rychkov; Simmons-Duffin; Zinn-Justin 2021."
topics:
  - conformal perturbation theory
  - CFT deformations
  - OPE coefficients
  - beta functions
  - anomalous dimensions
  - nearby fixed points
canonicalTopics:
  - conformal-perturbation-theory
  - cft-deformation
  - integrated-ope
  - nearby-fixed-point
researchStatus:
  established:
    - "Conformal perturbation theory expresses nearby RG flows and operator data in terms of CFT correlation functions and regulated integrated OPE singularities."
  active:
    - "Applications to conformal manifolds, defect CFTs, boundary CFTs, numerical bootstrap data, supersymmetric theories, and strongly coupled fixed points remain active."
---

## Summary

**Conformal perturbation theory** studies what happens when a CFT is deformed by local operators:

$$
S=S_{\mathrm{CFT}}
+\sum_i \mu^{d-\Delta_i}g^i\int d^d x\,\mathcal O_i(x).
$$

The input is not a weakly coupled Lagrangian. The input is CFT data: scaling dimensions $\Delta_i$, OPE coefficients $C_{ij}{}^k$, symmetry representations, and correlation functions. The perturbative expansion is an expansion in the deformation couplings $g^i$.

The central mechanism is short-distance collision of integrated operators. If

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\frac{C_{ij}{}^k}{|x|^{\Delta_i+\Delta_j-\Delta_k}}
\mathcal O_k(0)+\cdots,
$$

then integrating over $x$ can produce a logarithmic divergence. That divergence is local, so it is canceled by a counterterm for $\mathcal O_k$, and that counterterm contributes to $\beta^k$.

With the source convention on this page, the beta function begins schematically as

$$
\beta^k(g)
=
(\Delta_k-d)g^k
+\frac12S_{d-1}C_{ij}{}^k g^i g^j
+O(g^3),
$$

when the OPE channel is logarithmic and the perturbing action is written with the plus sign above. Here $S_{d-1}$ is the area of the unit $(d-1)$-sphere. The detailed coefficient depends on operator normalizations, sign conventions, and the subtraction scheme, but the mechanism is robust.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 56rem;">

![Conformal perturbation theory workflow from CFT data through integrated deformations, OPE collisions, counterterms, beta functions, anomalous dimensions, and nearby fixed points.](/figures/renormalization-rg-eft/conformal-perturbation-data-flow.svg)

<figcaption>

Conformal perturbation theory converts CFT data into nearby RG data. Integrated insertions collide, their OPEs produce local counterterms, and those counterterms determine beta functions, operator mixing, anomalous dimensions, and sometimes new fixed points.

</figcaption>
</figure>

This is the natural language for Wilson–Fisher fixed points, nearly marginal deformations, conformal manifolds, boundary RG flows, defect deformations, and two-dimensional CFT perturbations.

## Prerequisites

You should know [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Scale Invariance](/renormalization-rg-eft/fixed-points-critical-phenomena/scale-invariance/), [OPE and Short-Distance Expansion](/renormalization-rg-eft/local-operators-and-ope/ope-and-short-distance-expansion/), [Anomalous Dimensions of Operators](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimensions-of-operators/), [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/), and [Local Renormalization Group](/renormalization-rg-eft/advanced-rg-methods/local-renormalization-group/).

This page uses Euclidean CFT notation. It assumes that the undeformed CFT is sufficiently well defined that its operator spectrum and OPE coefficients can be used as data.

## Core idea

Ordinary perturbation theory expands around a Gaussian fixed point. Conformal perturbation theory expands around any CFT.

At first sight this sounds impossible: without a Lagrangian, what do we compute? The answer is that the undeformed CFT already supplies correlation functions. For an observable $X$, the deformed expectation value is formally

$$
\langle X\rangle_g
=
\frac{
\left\langle X\exp\left[-\sum_i g^i\mu^{d-\Delta_i}\int d^d x\,\mathcal O_i(x)\right]\right\rangle_{\mathrm{CFT}}
}{
\left\langle \exp\left[-\sum_i g^i\mu^{d-\Delta_i}\int d^d x\,\mathcal O_i(x)\right]\right\rangle_{\mathrm{CFT}}
}.
$$

Expanding in $g^i$ gives integrated CFT correlation functions. The ultraviolet singularities of these integrals are governed by OPEs. The local singularities determine counterterms, and the counterterms determine RG equations.

So the method is:

$$
\text{CFT data}
\longrightarrow
\text{integrated correlators}
\longrightarrow
\text{OPE collisions}
\longrightarrow
\text{counterterms}
\longrightarrow
\text{RG flow}.
$$

## Setup and RG convention

Let $\mathcal O_i$ be scalar primary operators of the CFT, with scaling dimensions $\Delta_i$. We write

$$
S_g=S_{\mathrm{CFT}}
+\sum_i \mu^{d-\Delta_i}g^i\int d^d x\,\mathcal O_i(x).
$$

The couplings $g^i$ are dimensionless. The RG convention in this volume is

$$
\beta^i(g)=
\left.\mu\frac{d g^i}{d\mu}\right|_{\text{bare data fixed}}.
$$

At linear order,

$$
\beta^i=(\Delta_i-d)g^i+O(g^2).
$$

Thus a relevant deformation, $\Delta_i<d$, has a negative coefficient in UV RG time. It grows toward the infrared because flowing to the IR means decreasing $\mu$.

:::note[IR length scale versus UV momentum scale]
Many statistical-mechanics texts write RG equations using a length scale $L$ that grows toward the infrared. Since $L\sim 1/\mu$, the linear term changes sign when translating to the $\mu$ convention used here.
:::

## Integrated OPEs and beta functions

At second order in the deformation, the expansion contains

$$
\frac12g^i g^j\mu^{2d-\Delta_i-\Delta_j}
\int d^d x\,d^d y\,
\mathcal O_i(x)\mathcal O_j(y).
$$

Introduce center and relative coordinates:

$$
X=\frac{x+y}{2},
\qquad
r=x-y.
$$

The OPE gives

$$
\mathcal O_i\left(X+\frac r2\right)
\mathcal O_j\left(X-\frac r2\right)
\supset
\frac{C_{ij}{}^k}{|r|^{\Delta_i+\Delta_j-\Delta_k}}
\mathcal O_k(X).
$$

The short-distance part of the relative integral is

$$
S_{d-1}\int_a dr\,r^{d-1-\Delta_i-\Delta_j+\Delta_k},
$$

where $a$ is a UV distance cutoff. The integral is logarithmic when

$$
\Delta_i+\Delta_j-\Delta_k=d.
$$

This logarithm is exactly the signal that the two perturbations generate a local counterterm for $\mathcal O_k$. In a minimal subtraction-like convention, this produces the schematic beta function

$$
\beta^k
=
(\Delta_k-d)g^k
+\frac12S_{d-1}C_{ij}{}^k g^i g^j
+\cdots.
$$

The ellipsis includes higher-order OPE collisions, scheme-dependent finite redefinitions, descendant contributions, spinful sources if allowed, and redundant operators.

The important lesson is that beta functions near a CFT are controlled by the OPE algebra of the CFT.

## Nearly marginal deformations

The cleanest application is a single nearly marginal operator

$$
\Delta=d-\epsilon,
\qquad
0<\epsilon\ll1.
$$

The beta function has the form

$$
\beta_g=-\epsilon g+A g^2+O(g^3),
$$

where $A$ is proportional to the relevant OPE coefficient in the chosen normalization. If $A>0$, the flow has a perturbative fixed point

$$
g_*=\frac{\epsilon}{A}+O(\epsilon^2).
$$

The Wilson–Fisher fixed point is the standard example. In $d=4-\epsilon$, the quartic scalar operator is slightly relevant at the Gaussian fixed point. The quadratic term in the beta function balances the engineering relevance and produces an interacting fixed point at $g_*\sim\epsilon$.

The linearized eigenvalue at the new fixed point is

$$
\left.\frac{d\beta_g}{dg}\right|_{g_*}
=
-\epsilon+2Ag_*
=
\epsilon+O(\epsilon^2).
$$

This sign is in UV RG time. The interpretation reverses if one uses IR coarse-graining time.

## Anomalous dimensions from operator collisions

Conformal perturbation theory also computes how operator dimensions shift. Insert a local operator $\mathcal O_a(0)$. At first order in $g^i$, the perturbation gives

$$
-g^i\mu^{d-\Delta_i}
\int d^d x\,
\langle \mathcal O_i(x)\mathcal O_a(0)\cdots\rangle_{\mathrm{CFT}}.
$$

The OPE

$$
\mathcal O_i(x)\mathcal O_a(0)
\sim
\sum_b
\frac{C_{ia}{}^b}{|x|^{\Delta_i+\Delta_a-\Delta_b}}
\mathcal O_b(0)+\cdots
$$

can produce logarithmic divergences. These divergences renormalize the operator insertion:

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R}.
$$

The anomalous-dimension matrix is then obtained from $Z$ in the usual way:

$$
\gamma_a{}^b=(Z^{-1})_a{}^c
\left.\mu\frac{d Z_c{}^b}{d\mu}\right|_{\text{bare data fixed}}.
$$

If multiple operators have the same quantum numbers and nearby dimensions, one must diagonalize the mixing matrix. The scaling operators of the deformed fixed point are not necessarily the original CFT operators.

## Exactly marginal operators and conformal manifolds

A marginal operator satisfies $\Delta=d$. But marginal does not mean exactly marginal. It means only that the engineering term in the beta function vanishes.

For marginal operators,

$$
\beta^i=O(g^2).
$$

The OPE coefficients decide whether the deformation remains conformal. If the physical beta functions vanish along a family of couplings, the family is a conformal manifold. If not, the operator is marginally relevant or marginally irrelevant.

The exact-marginality condition is subtle because the beta functions are defined modulo redundant directions and flavor rotations. In many theories, a marginal operator can collide with a conserved current descendant or with an operator related to a field redefinition. These effects must be quotiented out before declaring that a deformation is physical.

Local RG is the right language for this quotient. It treats marginal couplings as sources, includes background flavor fields, and separates physical beta functions from source-coordinate artifacts.

## Degenerate perturbation theory

When a CFT has several operators with the same spin, symmetry representation, and dimension, perturbing by $g^i$ can mix them. The correct first-order calculation is not a list of diagonal shifts; it is a matrix problem.

Suppose $\mathcal O_a$ and $\mathcal O_b$ are degenerate at the starting CFT. The deformation produces

$$
\gamma_a{}^b(g)
=
g^i M_{ia}{}^b+O(g^2),
$$

where $M_{ia}{}^b$ is determined by integrated three-point data. The new scaling dimensions are eigenvalues of the full matrix, and the new scaling operators are the eigenvectors.

This is the same logic as ordinary quantum-mechanical degenerate perturbation theory. The difference is that the Hamiltonian matrix is replaced by an anomalous-dimension matrix built from CFT OPE data.

## Descendants and redundant operators

OPEs contain descendants as well as primaries. Some descendants integrate to total derivatives and can be ignored on closed manifolds. Others become boundary terms, contact terms, or redundant deformations.

A redundant deformation is one that can be removed by a field redefinition. In Lagrangian language, a typical redundant operator has the form

$$
\mathcal O_{\mathrm{red}}
=
F[\phi]\frac{\delta S}{\delta\phi}.
$$

In CFT language, redundant directions are related to descendants, null states, current divergences, or source-coordinate transformations. They can appear in intermediate beta functions but should not be counted as independent physical directions in theory space.

This is why high-quality conformal perturbation theory always states the operator basis, the redundancy quotient, and the normalization convention.

## Boundary and defect versions

The same method works for boundary and defect CFTs. If a boundary has dimension $d-1$, a boundary perturbation has the form

$$
S=S_{\mathrm{BCFT}}
+\lambda^a\mu^{d-1-\widehat\Delta_a}
\int_{\partial M}d^{d-1}x\,\widehat{\mathcal O}_a(x).
$$

The linear beta function is

$$
\beta^a=(\widehat\Delta_a-(d-1))\lambda^a+\cdots.
$$

For a defect of dimension $p$, replace $d-1$ by $p$. Bulk operators can also approach a boundary or defect, producing bulk-to-boundary OPE singularities. Those singularities generate boundary or defect counterterms.

Thus boundary RG, interface RG, and defect perturbation theory are not separate miracles. They are conformal perturbation theory with a different integration region and a different OPE.

## Validity and limitations

Conformal perturbation theory is controlled when the deformed theory stays close to the starting CFT over the scales of interest. This usually requires small couplings and a good handle on the operator spectrum.

It is less reliable when:

- relevant couplings grow large before reaching the desired IR scale;
- many operators become important at the same order;
- the CFT data are unknown or poorly normalized;
- IR divergences are mixed with UV counterterms;
- redundant operators are not separated from physical ones;
- the calculation is truncated without a small parameter.

A relevant perturbation may accurately describe the beginning of an RG flow and still tell you little about the final phase. That is not a failure of the method. It is the method being honest.

## Common pitfalls

**Calling marginal operators exactly marginal.** Exact marginality is a statement about the full physical beta function, not just the engineering dimension.

**Ignoring OPE normalization.** OPE coefficients depend on operator normalization. So do the numerical coefficients in beta functions.

**Confusing UV and IR beta-function signs.** This page uses $\beta=\mu\,dg/d\mu$. Coarse-graining conventions often use the opposite sign.

**Dropping contact terms.** The RG data come from local singularities of integrated correlators. Contact terms are the point, not a nuisance.

**Forgetting operator mixing.** Degenerate operators mix. The scaling basis at the deformed fixed point is generally not the starting CFT basis.

**Counting redundant directions as physical.** Descendants, current divergences, and field-redefinition operators can appear in beta functions without representing independent physical deformations.

**Assuming perturbation theory knows the endpoint.** A relevant flow may leave the perturbative neighborhood. Conformal perturbation theory then describes the UV departure, not the full IR theory.

## Relations to other pages

This page is the advanced RG counterpart of [Conformal Perturbation Theory Preview](/renormalization-rg-eft/local-operators-and-ope/conformal-perturbation-theory-preview/). It relies on [OPE and Short-Distance Expansion](/renormalization-rg-eft/local-operators-and-ope/ope-and-short-distance-expansion/), [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/), and [Local Renormalization Group](/renormalization-rg-eft/advanced-rg-methods/local-renormalization-group/).

It connects to [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/), [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/), conformal manifolds in the CFT volume, and EFT operator running in [Renormalization Group Evolution](/renormalization-rg-eft/matching-running-decoupling/renormalization-group-evolution/).

## Research status

The perturbative logic of CFT deformations, integrated OPE singularities, and nearby fixed points is established. It is a standard tool in two-dimensional CFT, critical phenomena, supersymmetric CFTs, conformal manifolds, boundary RG, and bootstrap-adjacent work.

Active areas include higher-order conformal perturbation theory in strongly coupled CFTs, numerical extraction of OPE data for RG flows, perturbations of defects and boundaries, conformal manifolds with global-symmetry quotients, and the relation between local RG consistency and monotonicity constraints.

## Exercises

### Exercise 1: Engineering beta function

Let

$$
S=S_{\mathrm{CFT}}+g\mu^{d-\Delta}\int d^d x\,\mathcal O(x).
$$

Assume the dimensionful bare coefficient is fixed. Show that the engineering contribution to the UV beta function is

$$
\beta_g=(\Delta-d)g.
$$

<details><summary><strong>Solution</strong></summary>

The dimensionful coefficient is

$$
\lambda=g\mu^{d-\Delta}.
$$

Keeping $\lambda$ fixed gives

$$
g=\lambda\mu^{\Delta-d}.
$$

Therefore

$$
\mu\frac{dg}{d\mu}
=(\Delta-d)g.
$$

Thus a relevant operator with $\Delta<d$ has a negative UV beta-function coefficient and grows toward the infrared.

</details>

### Exercise 2: Logarithmic OPE collision

Show that

$$
\int_a dr\,r^{d-1-\Delta_i-\Delta_j+\Delta_k}
$$

has a logarithmic UV divergence exactly when

$$
\Delta_i+\Delta_j-\Delta_k=d.
$$

<details><summary><strong>Solution</strong></summary>

The integral has the form

$$
\int_a dr\,r^p,
\qquad
p=d-1-\Delta_i-\Delta_j+\Delta_k.
$$

A logarithm appears when $p=-1$. Setting $p=-1$ gives

$$
d-1-\Delta_i-\Delta_j+\Delta_k=-1,
$$

or

$$
\Delta_i+\Delta_j-\Delta_k=d.
$$

This is the resonance condition for an OPE collision to generate a logarithmic counterterm for $\mathcal O_k$.

</details>

### Exercise 3: Nearby fixed point

Suppose

$$
\beta_g=-\epsilon g+A g^2+O(g^3),
\qquad A>0,
\qquad 0<\epsilon\ll1.
$$

Find the perturbative fixed point and the linearized RG eigenvalue in the UV convention.

<details><summary><strong>Solution</strong></summary>

Set $\beta_g=0$:

$$
-\epsilon g+A g^2=0.
$$

The two roots are

$$
g=0,
\qquad
g_*=\frac{\epsilon}{A}+O(\epsilon^2).
$$

The linearized eigenvalue is

$$
\left.\frac{d\beta_g}{dg}\right|_{g_*}
=
-\epsilon+2A\frac{\epsilon}{A}+O(\epsilon^2)
=
\epsilon+O(\epsilon^2).
$$

This sign is for the UV RG time $\mu$. If one uses an IR length-scale time, the sign is reversed.

</details>

### Exercise 4: Symmetry selection rule

Suppose a CFT has a $\mathbb Z_2$ symmetry under which $\mathcal O$ is odd. Explain why the deformation by $g\int\mathcal O$ cannot generate a quadratic beta-function term proportional to $g^2\mathcal O$ if the symmetry is preserved.

<details><summary><strong>Solution</strong></summary>

The product $\mathcal O\times\mathcal O$ is even under the $\mathbb Z_2$ symmetry, because the product of two odd operators is even. The operator $\mathcal O$ itself is odd. Therefore the OPE coefficient $C_{\mathcal O\mathcal O}{}^{\mathcal O}$ must vanish in a symmetry-preserving scheme. Without that OPE channel, the short-distance collision of two perturbing insertions cannot generate the local counterterm $g^2\int\mathcal O$. Hence the quadratic self-term in the beta function is forbidden.

</details>

## References

- J. Cardy, *Scaling and Renormalization in Statistical Physics*, for conformal perturbation theory and critical phenomena.
- A. B. Zamolodchikov, classic work on two-dimensional conformal perturbation theory and RG flow.
- S. Coleman, *Aspects of Symmetry*, especially "Dilatations," for scaling, anomalous dimensions, and OPE-based RG reasoning.
- K. G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the connection between fixed points, operator data, and critical phenomena.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for fixed points, $\epsilon$ expansion, and statistical-field-theory applications.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D≥3 Dimensions*, for modern CFT data and perturbations.
- D. Simmons-Duffin, *TASI Lectures on the Conformal Bootstrap*, for CFT data, OPEs, and bootstrap context.

## Version history

- 2026-06-19: First polished draft. Developed conformal perturbation theory as integrated OPE perturbation theory around a fixed point, including beta functions, anomalous dimensions, nearby fixed points, conformal manifolds, and scheme caveats.
