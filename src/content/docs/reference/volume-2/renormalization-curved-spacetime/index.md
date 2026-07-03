---
title: "Renormalization in Curved Spacetime"
description: "Chapter overview for stress-tensor renormalization, trace anomalies, curvature counterterms, effective actions, heat-kernel methods, and gravitational EFT previews."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Birrell and Davies; Wald; Parker and Toms; Fulling; DeWitt; Christensen; Duff; Donoghue; Burgess 2020; Weinberg 1995."
topics:
  - QFT in curved spacetime
  - stress tensor renormalization
  - curvature counterterms
  - trace anomaly
  - heat-kernel methods
  - gravitational EFT
canonicalTopics:
  - renormalization-in-curved-spacetime
  - stress-tensor-renormalization
  - curvature-counterterms
  - trace-anomaly
researchStatus:
  established:
    - "Locality and covariance require gravitational counterterms when quantum matter fields are renormalized on curved backgrounds; the renormalized stress tensor is defined up to local curvature ambiguities constrained by Ward identities."
  active:
    - "Interacting theories, gauge theories, boundaries, dynamical gravity, de Sitter observables, nonequilibrium states, and nonperturbative definitions require care beyond the first-pass material in this chapter."
---

## Summary

Renormalization in Curved Spacetime is the chapter in the Renormalization, RG, and EFT volume where the slogan “counterterms are local” is tested against geometry. In flat spacetime, ultraviolet divergences force us to renormalize masses, couplings, fields, and composite operators. On a curved background, the same short-distance singularities also generate local terms built from the metric.

The chapter exists because the stress tensor is not just another composite operator. It is the response of the quantum theory to geometry, the source for gravity, the object that appears in Ward identities, and the operator whose trace records the failure of scale invariance after quantization.

The guiding idea is

$$
\text{short-distance singularities in curved spacetime}
\quad\Longrightarrow\quad
\text{local covariant curvature counterterms}.
$$

Read this chapter when you want to understand why a quantum field theory on a background metric naturally produces terms such as $\Lambda$, $R$, $R^2$, $R_{\mu\nu}R^{\mu\nu}$, trace anomalies, and gravitational EFT corrections.

## Prerequisites

You should know [Conventions and Notation](/renormalization-rg-eft/conventions/), [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/), [Composite Operator Renormalization Preview](/renormalization-rg-eft/regularization-counterterms/composite-operator-renormalization-preview/), [Local Operators and OPE](/renormalization-rg-eft/local-operators-and-ope/), and [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/).

You also need the differential-geometry basics of metrics, covariant derivatives, curvature tensors, volume forms, and integration by parts on manifolds. This chapter uses those tools but does not teach differential geometry from scratch.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Stress-Tensor Renormalization](/renormalization-rg-eft/renormalization-curved-spacetime/stress-tensor-renormalization/) | Why $T_{\mu\nu}$ is a composite operator, how it is defined by metric variation, and why local curvature counterterms are unavoidable. |
| 2 | [Trace Anomaly Preview](/renormalization-rg-eft/renormalization-curved-spacetime/trace-anomaly-preview/) | How a classically traceless stress tensor can acquire a local quantum trace built from curvature and beta functions. |
| 3 | [Curvature Counterterms](/renormalization-rg-eft/renormalization-curved-spacetime/curvature-counterterms/) | The local gravitational terms required by renormalization: $\Lambda$, $R$, $R^2$, $R_{\mu\nu}R^{\mu\nu}$, $C^2$, Euler density, and boundary terms. |
| 4 | [Effective Action in Curved Spacetime](/renormalization-rg-eft/renormalization-curved-spacetime/effective-action-in-curved-spacetime/) | How the quantum effective action $W[g,J]$ packages stress tensors, currents, anomalies, and nonlocal state-dependent response. |
| 5 | [Heat-Kernel Methods Preview](/renormalization-rg-eft/renormalization-curved-spacetime/heat-kernel-methods-preview/) | The Seeley–DeWitt expansion as the efficient way to extract local UV divergences in curved backgrounds. |
| 6 | [Gravitational EFT Preview](/renormalization-rg-eft/renormalization-curved-spacetime/gravitational-eft-preview/) | How curvature counterterms become the low-energy EFT expansion of quantum gravity and matter coupled to gravity. |

After this path, you should be able to read formulas for $\langle T_{\mu\nu}\rangle_{\text{ren}}$, trace anomalies, and curvature counterterms without confusing local UV subtraction with global state-dependent physics.

## Landmarks

| Landmark | Meaning | Where it appears |
|---|---|---|
| Background metric $g_{\mu\nu}$ | A classical source coupled to the stress tensor. | Stress-tensor definition, generating functionals. |
| Hilbert stress tensor | The operator obtained by varying the action with respect to the metric. | $T_{\mu\nu}=2\delta S/\sqrt{-g}\delta g^{\mu\nu}$ in the convention stated on each page. |
| Composite-operator divergence | A short-distance singularity in local products such as $\partial_\mu\phi\partial_\nu\phi$. | Stress-tensor renormalization. |
| Curvature counterterms | Local metric functionals needed to absorb UV dependence. | $\int\sqrt{-g}$, $\int\sqrt{-g}R$, $\int\sqrt{-g}R^2$, $\int\sqrt{-g}R_{\mu\nu}R^{\mu\nu}$. |
| Effective action $W[g,J]$ | The generating functional of connected correlators in external sources. | Stress tensors, currents, anomalies. |
| Trace anomaly | A local trace for $\langle T^\mu{}_{\mu}\rangle$ even when the classical theory is Weyl invariant. | Trace anomaly preview, local RG. |
| State dependence | The finite nonlocal part of $\langle T_{\mu\nu}\rangle$ depends on the quantum state or density matrix. | Curved-spacetime applications, black holes, cosmology. |
| Scheme dependence | Local finite curvature counterterms shift local pieces of $\langle T_{\mu\nu}\rangle$ and the $\Box R$ part of the anomaly. | Stress-tensor renormalization, curvature counterterms. |
| Semiclassical Einstein equation | Geometry sourced by $\langle T_{\mu\nu}\rangle_{\text{ren}}$. | Gravitational EFT preview, spacetime and gravity applications. |

The repeated pattern is that the UV part is local and covariant, while the finite physical response may be nonlocal and state-dependent.

## Common confusions

**A divergent stress tensor is not fixed by normal ordering alone.** Normal ordering works in simple flat-space Fock representations, but curved spacetime has no preferred global notion of positive frequency in general. Renormalization must be local, covariant, and compatible with Ward identities.

**Curvature counterterms are not optional once the metric is a source.** If $g_{\mu\nu}$ is allowed to vary, loop divergences can generate all local terms compatible with diffeomorphism invariance. Even a matter-only QFT on a fixed curved background needs gravitational counterterms in its generating functional.

**The trace anomaly is not the same as explicit mass breaking.** A mass term contributes a classical trace. A trace anomaly remains even for classically Weyl-invariant massless theories after renormalization.

**The renormalized stress tensor is not unique as a local operator.** It is defined up to local conserved curvature tensors coming from finite counterterms. Physical questions must specify which local convention is being used or focus on invariant differences.

**Covariance is not a decorative constraint.** Renormalization prescriptions that violate diffeomorphism covariance can produce spurious non-conservation of $\langle T_{\mu\nu}\rangle$. If diffeomorphism symmetry is non-anomalous, the renormalized expectation value must obey the corresponding Ward identity.

## Boundaries

This chapter does:

- define the stress tensor as a metric response and explain its composite-operator renormalization;
- explain why curvature counterterms are required by locality and covariance;
- preview trace anomalies and their scheme dependence;
- introduce heat-kernel logic as a way to identify local UV divergences;
- connect curved-spacetime renormalization to gravitational EFT.

This chapter does not try to do:

- teach general relativity or differential geometry from scratch;
- develop the full physics of Hawking radiation, Unruh radiation, inflationary correlators, or black-hole backreaction;
- prove the algebraic axioms of QFT in curved spacetime;
- replace the Spacetime, Gravity, and Holography volume;
- replace the Effective Field Theory chapter’s general development of matching, power counting, and Wilson coefficients.

The boundary is important: this chapter is about renormalization and scale dependence in curved backgrounds. The broader physics of quantum fields and gravity lives in the dedicated spacetime and gravity material.

## Where to go next

Start with [Stress-Tensor Renormalization](/renormalization-rg-eft/renormalization-curved-spacetime/stress-tensor-renormalization/). Then read [Trace Anomaly Preview](/renormalization-rg-eft/renormalization-curved-spacetime/trace-anomaly-preview/) and [Curvature Counterterms](/renormalization-rg-eft/renormalization-curved-spacetime/curvature-counterterms/) together, because the same local terms control both UV subtraction and local ambiguity.

For the EFT interpretation, connect this chapter to [Gravitational Effective Field Theory](/renormalization-rg-eft/major-efts/gravitational-effective-field-theory/), [Gravitational EFT Preview](/renormalization-rg-eft/renormalization-curved-spacetime/gravitational-eft-preview/), and [Naturalness in Wilsonian Language](/renormalization-rg-eft/naturalness-power-counting/naturalness-in-wilsonian-language/).

For operator and anomaly technology, return to [Composite Operator Renormalization Preview](/renormalization-rg-eft/regularization-counterterms/composite-operator-renormalization-preview/), [Local RG](/renormalization-rg-eft/advanced-rg-methods/local-renormalization-group/), and [Conformal Perturbation Theory](/renormalization-rg-eft/advanced-rg-methods/conformal-perturbation-theory/).

## References

- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, for the classic physics treatment of particle creation, stress tensors, and anomalies.
- R. M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, for local covariance, stress-tensor renormalization, and the axiomatic viewpoint.
- L. Parker and D. Toms, *Quantum Field Theory in Curved Spacetime*, for renormalization, effective action methods, and applications.
- S. M. Christensen, papers on stress-tensor renormalization in curved spacetime, for point-splitting and conserved local counterterms.
- B. S. DeWitt, *The Dynamical Theory of Groups and Fields*, for heat-kernel and effective-action foundations.
- M. J. Duff, "Twenty years of the Weyl anomaly," for trace-anomaly conventions and coefficient dictionaries.
- J. F. Donoghue, papers and reviews on general relativity as an effective field theory, for the connection between curvature counterterms and low-energy quantum gravity.
- C. P. Burgess, *Introduction to Effective Field Theory*, for gravitational EFT as a scale-separated effective description.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I and II, for effective field theory, renormalization, and gravity-adjacent QFT perspective.

## Version history

- 2026-06-19: First polished draft. Opened the Renormalization in Curved Spacetime chapter with reading path, landmarks, boundaries, and references.
