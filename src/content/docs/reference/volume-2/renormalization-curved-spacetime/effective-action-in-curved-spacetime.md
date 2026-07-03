---
title: "Effective Action in Curved Spacetime"
description: "How background metrics, sources, one-loop determinants, local counterterms, nonlocal terms, stress tensors, anomalies, and state dependence fit together in the curved-spacetime effective action."
sidebar:
  label: "Effective Action in Curved Spacetime"
  order: 40
level: Advanced
status: "Polished draft"
source: "Birrell and Davies; Parker and Toms; Wald; Fulling; DeWitt; Christensen; Donoghue; Burgess 2020; Weinberg 1995; Schwartz 2014; Zinn-Justin 2021."
topics:
  - effective action
  - curved spacetime
  - background fields
  - stress tensor
  - one-loop determinants
  - nonlocal effective action
canonicalTopics:
  - effective-action-in-curved-spacetime
  - curved-spacetime-effective-action
  - background-field-effective-action
  - stress-tensor-generating-functional
researchStatus:
  established:
    - "The curved-spacetime effective action is the generating functional whose metric variations produce stress-tensor expectation values and correlators; its ultraviolet divergences are local diffeomorphism-invariant curvature terms."
  active:
    - "Lorentzian state dependence, in-in effective actions, boundaries, horizons, gauge constraints, nonlocal terms, and dynamical gravity remain technically and conceptually rich in modern research."
---

## Summary

The effective action in curved spacetime is the functional that records what remains after quantum fields have been integrated out in a background metric. If the metric is treated as a source, then the renormalized generating functional

$$
W[g,J]
$$

contains stress-tensor expectation values, stress-tensor correlators, curvature counterterms, trace anomalies, and finite nonlocal quantum response. If the metric is dynamical, the same object becomes part of the low-energy gravitational effective action.

For a matter field $\Phi$ in a background metric, the Lorentzian source functional is schematically

$$
Z[g,J]
=\int \mathcal D\Phi\,
\exp\left\{iS[\Phi,g]+i\int d^d x\sqrt{-g}\,J\Phi\right\},
\qquad
Z[g,J]=e^{iW[g,J]}.
$$

The metric variation of $W$ defines the renormalized stress tensor:

$$
\langle T_{\mu\nu}(x)\rangle
=-\frac{2}{\sqrt{-g(x)}}\frac{\delta W[g]}{\delta g^{\mu\nu}(x)},
$$

with the sign convention fixed by

$$
\delta S
=-\frac12\int d^d x\sqrt{-g}\,T_{\mu\nu}\delta g^{\mu\nu}.
$$

The one-loop Euclidean effective action of a real scalar with quadratic operator $\Delta$ is

$$
\Gamma_E^{(1)}[g]
=\frac12\operatorname{Tr}\log\Delta.
$$

After regularization and renormalization, the full answer has the schematic form

$$
\Gamma[g]
=\Gamma_{\text{local}}[g;\mu]
+\Gamma_{\text{nonlocal}}[g;\mu]
+\Gamma_{\text{state/contour}}[g].
$$

The local part contains curvature counterterms and EFT coefficients. The nonlocal part contains finite long-distance information, such as logarithms of differential operators. The state or contour part matters in Lorentzian problems where one asks for expectation values rather than in-out matrix elements.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 58rem;">

![Curved-spacetime effective action pipeline from quantum fields and metric sources to determinants, counterterms, nonlocal terms, stress tensor, trace anomaly, and observables](/figures/renormalization-rg-eft/effective-action-curved-spacetime-map.svg)

<figcaption>

The curved-spacetime effective action packages several roles at once. It is a source functional for stress-tensor correlators, a bookkeeping device for local curvature counterterms, a container for finite nonlocal terms, and — when gravity is dynamical — the low-energy gravitational EFT action.

</figcaption>
</figure>

## Prerequisites

You should know [Stress-Tensor Renormalization](/renormalization-rg-eft/renormalization-curved-spacetime/stress-tensor-renormalization/), [Trace Anomaly Preview](/renormalization-rg-eft/renormalization-curved-spacetime/trace-anomaly-preview/), [Curvature Counterterms](/renormalization-rg-eft/renormalization-curved-spacetime/curvature-counterterms/), [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/), [Background Field Method](/renormalization-rg-eft/gauge-theories-and-rg/background-field-method/), and [Gravitational Effective Field Theory](/renormalization-rg-eft/major-efts/gravitational-effective-field-theory/).

You should also be comfortable with functional derivatives, Gaussian path integrals, covariant derivatives, curvature tensors, and the distinction between Lorentzian and Euclidean path integrals. This page uses mostly-minus Lorentzian conventions by default, but determinant formulas are written in Euclidean signature where the heat-kernel expansion is most direct.

## Core idea

In flat-space QFT, sources are often introduced as temporary devices for generating correlation functions. In curved spacetime, the metric is itself a source. It couples to the stress tensor, so renormalizing QFT in curved spacetime means renormalizing the metric-dependent functional $W[g]$.

This is stronger than renormalizing ordinary flat-space amplitudes. A term such as

$$
\int d^4x\sqrt{-g}\,R^2
$$

vanishes in flat spacetime, but its metric variations around flat spacetime contribute to stress-tensor correlators. A theory that is finite for ordinary scattering amplitudes may still require curvature counterterms once the stress tensor is treated as an operator coupled to a source.

The curved-spacetime effective action is therefore the natural home for three ideas:

| Ingredient | In the effective action | Physical role |
|---|---|---|
| UV locality | local curvature terms | counterterms and EFT coefficients |
| Quantum propagation | nonlocal kernels | finite response, thresholds, particle creation |
| Source dependence | metric variations | stress tensor and its correlators |
| Weyl response | scale variation | trace anomaly and running couplings |

The main discipline is to keep these roles separate. A local counterterm is not the same thing as a nonlocal physical effect. A Euclidean determinant is not automatically a causal real-time expectation value. A finite local term may be a scheme choice in a nondynamical background, but a measurable EFT coefficient when gravity is dynamical.

## Connected and 1PI functionals

There are several related functionals, and authors do not always use the same notation.

The connected generating functional is defined by

$$
Z[g,J]=e^{iW[g,J]}
$$

in Lorentzian signature, or

$$
Z_E[g,J]=e^{-W_E[g,J]}
$$

in Euclidean signature. It generates connected correlation functions of operators coupled to sources.

The one-particle-irreducible effective action is the Legendre transform with respect to the source $J$:

$$
\bar\Phi(x)=\frac{1}{\sqrt{-g(x)}}\frac{\delta W[g,J]}{\delta J(x)},
$$

and

$$
\Gamma[g,\bar\Phi]
=W[g,J]-\int d^d x\sqrt{-g}\,J\bar\Phi,
$$

up to the usual Lorentzian sign convention. It obeys

$$
\frac{1}{\sqrt{-g}}\frac{\delta\Gamma[g,\bar\Phi]}{\delta\bar\Phi(x)}=-J(x).
$$

If all matter fields are integrated out and no expectation value is kept as an argument, one may write simply $\Gamma[g]$ or $W[g]$. On this site, $W[g]$ usually means the connected metric source functional, while $\Gamma[g,\bar\Phi]$ means the 1PI functional. When only the metric remains, the page should state which object is meant.

:::note[Ask what is being varied]
The phrase effective action is not enough. Ask which variables remain as arguments: background metric, background gauge field, classical matter expectation value, doubled Schwinger–Keldysh fields, or dynamical metric. The variational meaning changes with the answer.
:::

## The one-loop determinant

Consider a real scalar field in Euclidean signature,

$$
S_E[\phi,g]
=\frac12\int d^d x\sqrt g\,\phi\Delta\phi,
$$

where, after integration by parts,

$$
\Delta=-\nabla^2+m^2+\xi R.
$$

The Gaussian path integral gives

$$
Z_E[g]\propto(\det\Delta)^{-1/2}.
$$

Therefore the one-loop effective action is

$$
\Gamma_E^{(1)}[g]
=\frac12\operatorname{Tr}\log\Delta.
$$

For Grassmann fields the determinant appears in the numerator, so fermion loops carry the familiar minus sign. For gauge theories, gauge fixing and ghosts must be included. For operators with zero modes, the zero modes must be removed from the determinant and integrated over separately.

The determinant is formal until regularized. Schwinger proper time gives

$$
\operatorname{Tr}\log\Delta
=-\int_0^\infty\frac{ds}{s}\operatorname{Tr}\,e^{-s\Delta},
$$

up to a field-independent normalization. The region $s\to0$ probes high eigenvalues of $\Delta$, so it encodes UV divergences. This is the bridge to heat-kernel methods.

## Local and nonlocal terms

The divergent part of the effective action is local. The full effective action is not.

In four dimensions, the local gravitational part has the derivative expansion

$$
\Gamma_{\text{local}}[g]
=\int d^4x\sqrt{-g}\left(
\Lambda_{\text{vac}}
-\frac{M_{\text{Pl}}^2}{2}R
+aR^2+bR_{\mu\nu}R^{\mu\nu}
+cR_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
+\cdots
\right),
$$

with Lorentzian signs depending on the convention for the gravitational action. These coefficients include divergent counterterms, finite scheme choices, and physical EFT parameters if gravity is dynamical.

The nonlocal part contains terms such as

$$
\int d^4x\sqrt g\,
C_{\mu\nu\rho\sigma}
\log\left(\frac{-\nabla^2}{\mu^2}\right)
C^{\mu\nu\rho\sigma},
$$

where $C_{\mu\nu\rho\sigma}$ is the Weyl tensor. This term cannot be reproduced by finitely many local curvature invariants. It records finite long-distance information from massless propagation.

A useful classification is:

| Part | Example | Interpretation |
|---|---|---|
| local divergent | $\frac{1}{\epsilon}\int\sqrt g\,R^2$ | required counterterm |
| local finite | $a(\mu)\int\sqrt g\,R^2$ | scheme choice or EFT coefficient |
| nonlocal logarithmic | $\int C\log(-\nabla^2/\mu^2)C$ | finite massless-loop memory |
| nonlocal threshold | $\int R F(-\nabla^2/m^2)R$ | finite massive-loop response |
| state dependent | in-in kernels | causal real-time expectation values |

Renormalization removes regulator dependence by adjusting local terms. It does not erase genuine nonlocal physics.

## Metric variation and Ward identities

If the regulator, counterterms, and state preserve diffeomorphism invariance, the renormalized source functional obeys the diffeomorphism Ward identity. With no other sources, this gives

$$
\nabla^\mu\langle T_{\mu\nu}\rangle=0.
$$

With background scalar sources $J^a(x)$ coupled to operators $\mathcal O_a$, the identity is modified schematically to

$$
\nabla^\mu\langle T_{\mu\nu}\rangle
=\langle\mathcal O_a\rangle\nabla_\nu J^a
+\cdots,
$$

where the ellipsis includes background gauge-field contributions if present. This is the curved-spacetime version of the statement that translation invariance is broken by spacetime-dependent sources.

A Weyl variation gives the trace. Under

$$
g_{\mu\nu}\to e^{2\sigma(x)}g_{\mu\nu},
$$

one has

$$
\delta_\sigma g^{\mu\nu}=-2\sigma g^{\mu\nu}.
$$

Therefore, in the Lorentzian convention above,

$$
\delta_\sigma W[g]
=\int d^d x\sqrt{-g}\,\sigma(x)\langle T^\mu{}_{\mu}(x)\rangle.
$$

If the renormalized functional fails to be Weyl invariant even though the classical theory is Weyl invariant, the failure is the trace anomaly.

## In-out versus in-in effective actions

Euclidean determinants are excellent for UV divergences, local counterterms, equilibrium free energies, and anomalies. They are not always the right object for real-time expectation values.

The ordinary Lorentzian effective action built from vacuum-to-vacuum amplitudes is an in-out effective action. Its variation gives matrix elements between out and in vacua. In curved spacetime, where the background can create particles and no unique vacuum may exist, that is not the same as a causal expectation value in a specified state.

For expectation values such as

$$
\langle \Psi|T_{\mu\nu}(x)|\Psi\rangle,
$$

one should use a Schwinger–Keldysh, or in-in, effective action. It doubles the metric sources,

$$
g_{\mu\nu}\longrightarrow(g^+_{\mu\nu},g^-_{\mu\nu}),
$$

and takes variations before setting

$$
g^+_{\mu\nu}=g^-_{\mu\nu}=g_{\mu\nu}.
$$

This is the natural formalism for semiclassical Einstein equations with causal response,

$$
G_{\mu\nu}+\Lambda g_{\mu\nu}+\text{higher-curvature terms}
=8\pi G\,\langle T_{\mu\nu}\rangle_{\text{ren}}.
$$

:::caution[Euclidean does not mean causal]
The local UV counterterms extracted from Euclidean methods are the same local counterterms needed in Lorentzian signature after analytic continuation. But retarded response, dissipation, particle creation, and state-dependent stress tensors require Lorentzian contour information.
:::

## Massive fields and the low-energy expansion

Suppose a heavy scalar of mass $M$ is integrated out in a background whose curvature and derivative scales satisfy

$$
R\ll M^2,
\qquad
\nabla^2R\ll M^2R.
$$

Then the loop cannot resolve long-distance details of the geometry. Its effect can be expanded in local curvature invariants:

$$
\Gamma_{\text{heavy}}[g]
=\int d^4x\sqrt{-g}\left(
A_0M^4+A_1M^2R
+A_2R^2+A_3R_{\mu\nu}R^{\mu\nu}
+\frac{A_4}{M^2}R^3
+\frac{A_5}{M^2}R\nabla^2R
+\cdots
\right).
$$

This is curved-spacetime EFT matching. The coefficients depend on the spin, mass, nonminimal couplings, and scheme. At energies well below $M$, the heavy field no longer appears explicitly, but it leaves local curvature operators behind.

Massless fields behave differently. They generate nonlocal terms such as

$$
R\log\left(\frac{-\nabla^2}{\mu^2}\right)R.
$$

There is no large mass that turns the full answer into a purely local expansion.

## Common pitfalls

**Confusing $W[g]$ and $\Gamma[g,\bar\Phi]$.** The connected generating functional and the 1PI effective action are related but not identical. Ask which variables have been Legendre transformed.

**Assuming the effective action is local.** The UV divergent part is local. The full effective action generally contains nonlocal finite terms.

**Forgetting state dependence.** Local counterterms are state independent, but Lorentzian stress-tensor expectation values are not.

**Treating the trace anomaly as explicit classical breaking.** A trace anomaly can occur even when the classical theory is Weyl invariant.

**Using Euclidean determinants for causal response without qualification.** Euclidean methods give UV data and equilibrium quantities. Causal real-time response requires in-in methods.

**Dropping curvature terms because the metric is “only a background.”** A background source still requires source renormalization. If $g_{\mu\nu}$ couples to $T_{\mu\nu}$, then $W[g]$ must be renormalized as a functional of $g$.

## Relations to other pages

This page connects [Stress-Tensor Renormalization](/renormalization-rg-eft/renormalization-curved-spacetime/stress-tensor-renormalization/) to [Curvature Counterterms](/renormalization-rg-eft/renormalization-curved-spacetime/curvature-counterterms/) by explaining the functional whose variations define the stress tensor and whose UV divergences require local curvature terms. [Trace Anomaly Preview](/renormalization-rg-eft/renormalization-curved-spacetime/trace-anomaly-preview/) studies the Weyl variation of this functional. [Heat-Kernel Methods Preview](/renormalization-rg-eft/renormalization-curved-spacetime/heat-kernel-methods-preview/) explains a systematic way to compute its local UV expansion.

For dynamical gravity, connect this page to [Gravitational Effective Field Theory](/renormalization-rg-eft/major-efts/gravitational-effective-field-theory/). For gauge theories, compare with [Background Field Method](/renormalization-rg-eft/gauge-theories-and-rg/background-field-method/). For real-time expectation values, later pages should connect this material to Schwinger–Keldysh QFT.

## Research status

The local UV structure of the effective action in curved backgrounds is well established: short-distance divergences are local curvature invariants, and metric variations generate renormalized stress-tensor correlators.

Active areas include nonlocal effective actions, causal in-in response, quantum fields on time-dependent spacetimes, semiclassical-gravity stability, anomaly-induced actions, black-hole stress tensors, cosmological correlators, boundaries and defects, and the interface with holographic renormalization.

## Exercises

### Exercise 1: Stress tensor from metric variation

Assume the Lorentzian matter action varies as

$$
\delta S[\Phi,g]
=-\frac12\int d^d x\sqrt{-g}\,T_{\mu\nu}\delta g^{\mu\nu}.
$$

Using $Z[g]=e^{iW[g]}$, derive

$$
\langle T_{\mu\nu}(x)\rangle
=-\frac{2}{\sqrt{-g(x)}}\frac{\delta W[g]}{\delta g^{\mu\nu}(x)}.
$$

<details><summary><strong>Solution</strong></summary>

The path-integral variation is

$$
\delta Z[g]
=\int\mathcal D\Phi\,i\delta S\,e^{iS}
=iZ[g]\langle\delta S\rangle.
$$

Since $Z=e^{iW}$,

$$
\delta Z=iZ\delta W.
$$

Therefore

$$
\delta W=\langle\delta S\rangle
=-\frac12\int d^d x\sqrt{-g}\,\langle T_{\mu\nu}\rangle\delta g^{\mu\nu}.
$$

Reading off the functional derivative gives the desired formula.

</details>

### Exercise 2: Gaussian determinant

Let

$$
S_E[\phi]=\frac12(\phi,\Delta\phi)
$$

for a real bosonic field with positive operator $\Delta$. Show formally that

$$
\Gamma_E^{(1)}=\frac12\operatorname{Tr}\log\Delta.
$$

<details><summary><strong>Solution</strong></summary>

A finite-dimensional Gaussian integral gives

$$
\int d^n\phi\,\exp\left(-\frac12\phi^T\Delta\phi\right)
=(2\pi)^{n/2}(\det\Delta)^{-1/2}.
$$

The functional integral is the infinite-dimensional analogue:

$$
Z_E\propto(\det\Delta)^{-1/2}.
$$

With $Z_E=e^{-\Gamma_E}$,

$$
\Gamma_E^{(1)}=-\log Z_E
=\frac12\log\det\Delta
=\frac12\operatorname{Tr}\log\Delta,
$$

up to field-independent normalization constants.

</details>

### Exercise 3: Local or nonlocal?

Classify the following terms as local or nonlocal functionals of the metric:

$$
\int\sqrt g\,R^2,
\qquad
\int\sqrt g\,R\frac{1}{-\nabla^2}R,
\qquad
\int\sqrt g\,C_{\mu\nu\rho\sigma}\log\left(\frac{-\nabla^2}{\mu^2}\right)C^{\mu\nu\rho\sigma}.
$$

<details><summary><strong>Solution</strong></summary>

The first term is local: it is an integral of a scalar density built from the metric and finitely many derivatives at the same point.

The second term is nonlocal because $(-\nabla^2)^{-1}$ is a Green function. It depends on curvature at separated points.

The third term is also nonlocal because $\log(-\nabla^2/\mu^2)$ is a non-polynomial function of a differential operator. It cannot be represented by finitely many local curvature invariants.

</details>

## References

- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, for the standard curved-spacetime QFT treatment of effective actions, stress tensors, and anomalies.
- L. Parker and D. Toms, *Quantum Field Theory in Curved Spacetime*, for detailed renormalization and effective-action methods.
- R. M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, for the algebraic and stress-tensor viewpoint.
- B. S. DeWitt, *The Dynamical Theory of Groups and Fields*, for the background-field and heat-kernel tradition.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on effective actions, Schwinger proper time, and background fields.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on effective actions and general relativity as an EFT.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I and II, for effective actions, renormalization, and gravitational applications.

## Version history

- 2026-06-19: First polished draft. Added curved-spacetime generating functionals, one-loop determinants, local/nonlocal decomposition, in-out versus in-in caveats, stress-tensor variation, examples, exercises, and figure.
