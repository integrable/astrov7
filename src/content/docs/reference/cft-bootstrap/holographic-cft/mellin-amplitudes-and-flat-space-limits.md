---
title: "Mellin Amplitudes and Flat-Space Limits"
description: "How holographic CFT correlators in Mellin space resemble scattering amplitudes, and how bulk flat-space S-matrix data emerge from large Mellin variables."
sidebar:
  label: "Mellin Amplitudes and Flat-Space Limits"
  order: 6
level: Advanced
status: "Polished draft"
source: "Mack; Penedones; Fitzpatrick, Kaplan, Penedones, Raju, and van Rees; Rastelli and Zhou; holographic Mellin-amplitude and flat-space-limit literature."
topics:
  - Mellin amplitudes
  - flat-space limit
  - AdS/CFT
  - holographic CFT
  - scattering amplitudes
canonicalTopics:
  - mellin-amplitudes-and-flat-space-limits
  - holographic-mellin-amplitudes
  - cft-to-s-matrix-limit
researchStatus:
  established:
    - "Mellin amplitudes provide an amplitude-like representation of holographic CFT correlators, and controlled large-Mellin-variable limits recover flat-space scattering amplitudes in appropriate AdS/CFT regimes."
  active:
    - "Current research develops loop-level Mellin amplitudes, dispersion relations, spinning and supersymmetric correlators, stringy corrections, celestial links, and precision flat-space limits."
---

## Summary

**Mellin amplitudes** are one of the cleanest ways to see scattering-amplitude physics inside CFT correlators. A four-point CFT correlator can be represented by an inverse Mellin transform with variables usually called

$$
s,\qquad t,
$$

and a third variable $u_M$ fixed by a constraint. In holographic CFTs, these variables behave like AdS analogues of Mandelstam invariants.

The basic idea is

$$
\mathcal G(u,v)
\quad\longleftrightarrow\quad
M(s,t),
$$

where $\mathcal G(u,v)$ is a position-space reduced correlator and $M(s,t)$ is a Mellin amplitude.

In this language:

| Mellin feature | Bulk meaning |
|---|---|
| polynomial | local AdS contact interaction |
| pole | exchanged bulk field |
| residue polynomial | spin and OPE structure |
| large-variable growth | high-energy behavior and locality |
| crossing symmetry | permutation symmetry of external operators |
| flat-space limit | recovery of a bulk S-matrix |

The slogan is

$$
\text{Mellin amplitudes are AdS scattering amplitudes before the flat-space limit}.
$$

This page focuses on the holographic meaning of Mellin amplitudes and how flat-space scattering emerges when the AdS radius is taken large compared with local bulk scales.

## Prerequisites

Read [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/), [Witten Diagrams](/cft-bootstrap/holographic-cft/witten-diagrams/), and [AdS Effective Field Theory](/cft-bootstrap/holographic-cft/ads-effective-field-theory/) first.

You should know scalar four-point functions, conformal cross-ratios,

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z),
$$

large-$N$ factorization, contact and exchange Witten diagrams, and the difference between CFT correlators and ordinary flat-space S-matrix elements.

## Core idea

CFTs do not have ordinary scattering amplitudes in the same sense as flat-space QFT. There are no asymptotic particles moving in Minkowski infinity. But holographic CFTs secretly encode scattering in AdS. Mellin space makes that encoding look amplitude-like.

A schematic four-point Mellin representation is

$$
\mathcal G(u,v)
=\int\frac{ds\,dt}{(2\pi i)^2}\,
 u^{s/2}v^{t/2}\,
\Gamma\text{-factors}(s,t)\,M(s,t).
$$

The Gamma factors are universal kinematic pieces. The Mellin amplitude $M(s,t)$ contains the dynamical information.

The conceptual chain is

$$
\text{CFT correlator}
\quad\to\quad
\text{Mellin amplitude}
\quad\to\quad
\text{AdS interaction data}
\quad\to\quad
\text{flat-space amplitude in a limit}.
$$

The last arrow requires a controlled holographic limit. Mellin space is not automatically flat space. It is the bridge.

## Mellin variables as AdS Mandelstam variables

For four scalar operators, Mellin variables can be arranged so that

$$
s+t+u_M=\sum_i\Delta_i,
$$

where $u_M$ is a Mellin variable, not the cross-ratio $u$.

This resembles flat-space kinematics:

$$
s_{\rm flat}+t_{\rm flat}+u_{\rm flat}=\sum_i m_i^2.
$$

The analogy is not accidental. In the flat-space limit of AdS, dimensions scale like energies in AdS units, and large Mellin variables become related to flat-space Mandelstam invariants.

A rough dictionary is:

| Flat-space scattering | Mellin/AdS-CFT analogue |
|---|---|
| Mandelstam variables | Mellin variables $s,t,u_M$ |
| particle mass | operator dimension or bulk mass |
| exchange pole | Mellin pole from single-trace exchange |
| contact interaction | Mellin polynomial |
| high-energy limit | large Mellin variables |
| crossing of amplitudes | CFT crossing symmetry |

This dictionary is powerful, but every entry has AdS curvature and CFT normalization caveats attached. The caveats are not optional accessories. They are the seatbelts.

## Contact interactions

A local contact interaction in AdS gives a polynomial Mellin amplitude. For a non-derivative quartic scalar interaction,

$$
\int_{\rm AdS} d^{d+1}X\sqrt g\,g_4\Phi^4,
$$

the Mellin amplitude is constant:

$$
M(s,t)=\text{constant}.
$$

A derivative interaction gives powers of Mellin variables. For example,

$$
\frac{1}{\Lambda^2}(\nabla\Phi)^4
$$

contributes schematically

$$
M(s,t)\sim \frac{s^2+t^2+u_M^2}{\Lambda^2R_{\rm AdS}^2}.
$$

The denominator appears because Mellin variables are dimensionless in AdS units, while $\Lambda$ is a bulk energy scale. Equivalently,

$$
\Lambda R_{\rm AdS}\sim \Delta_{\rm gap}.
$$

Thus local derivative counting becomes polynomial Mellin counting.

## Exchange diagrams

A single-trace operator $\mathcal X$ exchanged in a CFT four-point function appears as a sequence of Mellin poles. For an exchanged operator of dimension $\Delta_X$ and spin $\ell_X$, the poles are schematically

$$
s=\Delta_X-\ell_X+2m,
\qquad
m=0,1,2,\ldots .
$$

The residues are polynomials in the other Mellin variable:

$$
\operatorname*{Res}_{s=\Delta_X-\ell_X+2m}M(s,t)
\sim \lambda_{12X}\lambda_{34X}Q_{m,\ell_X}(t).
$$

These polynomials encode the spin of the exchanged field and the descendant structure of the conformal multiplet.

In flat-space scattering, one exchanged particle gives one pole. In AdS/Mellin space, one exchanged primary gives an infinite sequence of poles, reflecting the AdS normal modes or conformal descendants.

That infinite ladder is the price of living in AdS. Rent is high, but the view is excellent.

## Gamma factors and double-trace data

The Mellin representation contains Gamma factors multiplying $M(s,t)$. These factors produce universal families of poles associated with double-trace operators. Therefore not every pole in the full Mellin integrand is a dynamical single-trace exchange pole.

A useful distinction is:

| Object | Role |
|---|---|
| Gamma-factor poles | universal double-trace and descendant structure |
| Mellin-amplitude poles | dynamical single-trace exchange |
| Mellin-amplitude polynomial | local contact interaction |
| contour prescription | selects OPE expansion and separates pole families |

This is why one must define precisely what is called the Mellin amplitude. Different conventions move factors between the amplitude and the measure.

When comparing formulas, ask:

$$
\text{Which Gamma factors are included in }M(s,t)?
$$

That one question prevents a surprising number of tiny disasters.

## Flat-space limit

The flat-space limit takes the AdS radius large compared with the local scattering scale:

$$
R_{\rm AdS}\to\infty
$$

while keeping proper bulk energies fixed. In CFT terms, this means considering large operator dimensions and large Mellin variables scaled with $R_{\rm AdS}$.

The rough statement is that the bulk flat-space S-matrix $\mathcal T(S,T)$ is obtained from a large-Mellin-variable limit of $M(s,t)$:

$$
M(s,t)\quad\longrightarrow\quad\mathcal T(S,T)
$$

after a normalization and smearing procedure.

A schematic scaling is

$$
s\sim R_{\rm AdS}^2 S,
\qquad
 t\sim R_{\rm AdS}^2 T,
$$

where $S,T$ are flat-space Mandelstam invariants. The exact relation depends on conventions, external dimensions, and normalization of states.

The important lesson is:

$$
\text{flat-space scattering is a high-energy, large-radius limit of CFT correlators}.
$$

## Why smearing is needed

AdS acts like a box. Its spectrum is discrete in global time. Flat-space scattering requires wavepackets that interact in a local region much smaller than the AdS radius.

Therefore the flat-space limit is not just “set $R$ to infinity” inside one formula. One constructs states or Mellin integrals that localize the interaction in the center of AdS and then takes the radius large.

The CFT version involves large dimensions and saddle-point approximations of Mellin integrals. The Gamma factors and Mellin amplitude combine to reproduce the energy-conserving delta functions and phase space of flat-space scattering.

This explains why the flat-space limit is subtle:

- AdS has a discrete spectrum;
- flat space has continuum scattering states;
- CFT operators create global AdS states, not plane waves;
- Mellin variables must scale with the AdS radius;
- normalization factors matter.

The limit exists, but it is a controlled procedure, not a button labeled “S-matrix please.”

## Locality and polynomial boundedness

In flat-space QFT, locality constrains high-energy amplitude growth. In AdS/CFT, locality constrains Mellin growth.

A finite-derivative contact interaction gives a polynomial in Mellin variables. A local EFT below a cutoff should therefore have controlled polynomial growth for

$$
s,t\ll (\Lambda R_{\rm AdS})^2.
$$

If $M(s,t)$ grows too rapidly, it suggests nonlocality or missing heavy states. In a UV-complete theory, such growth is softened by new physics: string states, higher-spin states, black-hole formation, or other quantum-gravity effects.

The CFT statement is:

$$
\text{Mellin boundedness is a diagnostic of bulk locality}.
$$

This connects directly to [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/).

## Stringy corrections

In stringy holographic CFTs, the flat-space limit of Mellin amplitudes should reproduce string scattering rather than just field-theory scattering. The higher-spin gap is finite but large:

$$
\Delta_{\rm gap}\sim R_{\rm AdS}/\ell_s.
$$

At energies below the string scale, one sees local AdS EFT. Near the string scale, an infinite tower of string states modifies the amplitude. In Mellin space, this appears as new pole structure and softer Regge behavior.

A schematic hierarchy is

$$
1\ll E R_{\rm AdS}\ll \Delta_{\rm gap}
\quad\Rightarrow\quad
\text{AdS EFT},
$$

while

$$
E R_{\rm AdS}\sim \Delta_{\rm gap}
\quad\Rightarrow\quad
\text{stringy physics}.
$$

Thus the flat-space limit can reveal whether the CFT's bulk completion is Einstein-like, stringy, or higher-spin-like.

## Regge limits

The Regge limit of Mellin amplitudes probes high-energy fixed-impact-parameter behavior. In holographic theories, this is connected to graviton exchange, string Reggeization, chaos, and causality.

In a local gravitational EFT, stress-tensor exchange gives strong Regge effects. Stringy corrections soften these effects by replacing a single spin-two exchange with a Regge trajectory.

CFT Regge boundedness constrains which Mellin amplitudes are acceptable. A polynomial contact term with too high a degree can produce bad Regge growth unless accompanied by new states below the corresponding scale.

This is the Mellin-space version of a core holographic lesson:

$$
\text{causality constrains EFT coefficients and the gap to new states}.
$$

## Relation to conformal blocks

Mellin amplitudes do not replace conformal blocks; they reorganize the same data.

A conformal block expansion makes the exchanged CFT operators manifest. Mellin space makes pole structure and AdS interactions manifest. A local contact term may be simple in Mellin space but complicated as an infinite sum of conformal blocks. A single conformal block is simple in the OPE but not necessarily simple as a crossing-symmetric Mellin object.

The comparison is:

| Conformal-block language | Mellin language |
|---|---|
| primary plus descendants | pole family and residue polynomial |
| double-trace tower | Gamma-factor and contour structure |
| crossing equations | permutation symmetry plus pole constraints |
| contact Witten diagram | polynomial amplitude |
| exchange Witten diagram | meromorphic amplitude |
| flat-space limit | large Mellin variables |

Both languages are useful. The best one depends on the question.

## Practical workflow

A holographic Mellin calculation often follows this pattern:

1. Choose external operators and their dimensions.
2. Decide which single-trace fields are light enough to exchange explicitly.
3. Write a crossing-compatible Mellin ansatz.
4. Include exchange poles for light fields.
5. Add polynomial contact terms allowed by symmetries and derivative counting.
6. Impose Ward identities, supersymmetry, or protected OPE data when available.
7. Check Regge growth and locality assumptions.
8. Extract double-trace anomalous dimensions and OPE corrections.
9. Take the flat-space limit if an S-matrix comparison is desired.
10. Track normalization conventions obsessively.

That last step is not glamorous, but neither is discovering a missing Gamma function three weeks later. Ask any amplitudes gremlin.

## Common pitfalls

**Do not confuse Mellin variables with cross-ratios.** The cross-ratios are $u,v$ or $z,\bar z$. Mellin variables are conjugate variables such as $s,t,u_M$.

**Do not identify Mellin amplitudes with flat-space amplitudes without a limit.** The flat-space S-matrix emerges only after a controlled large-radius, large-Mellin-variable procedure.

**Do not ignore Gamma factors.** They encode universal double-trace structure and affect pole interpretation.

**Do not treat every pole as a new particle.** Some poles are kinematic or descendant-related; dynamical exchange poles live in the Mellin amplitude as conventionally defined.

**Do not forget polynomial ambiguities.** Exchange diagrams are defined modulo contact terms.

**Do not assume polynomial growth is harmless.** Too much growth can violate locality or Regge constraints.

**Do not compare flat-space normalizations casually.** State normalizations, AdS radius conventions, and Mellin conventions all matter.

## Relations to other pages

This page follows [AdS Effective Field Theory](/cft-bootstrap/holographic-cft/ads-effective-field-theory/) and prepares [Stress Tensor, Graviton, and Causality](/cft-bootstrap/holographic-cft/stress-tensor-graviton-and-causality/) and [Stringy Corrections and Higher-Spin Gaps](/cft-bootstrap/holographic-cft/stringy-corrections-and-higher-spin-gaps/).

It connects back to [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/), [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/), and [Polyakov Bootstrap](/cft-bootstrap/analytic-bootstrap/polyakov-bootstrap/).

For the bulk-diagram side, see [Witten Diagrams](/cft-bootstrap/holographic-cft/witten-diagrams/). For locality diagnostics, see [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/).

## Research status

Mellin amplitudes and their flat-space limits are established tools in holographic CFT. Contact and exchange Witten diagrams have simple Mellin representations, and flat-space scattering can be extracted from suitable large-radius limits.

Active research develops loop-level Mellin techniques, dispersion relations, spinning and supersymmetric correlators, stringy corrections, black-hole thresholds, celestial connections, and sharper bootstrap constraints on which Mellin amplitudes can arise from consistent quantum gravity.

## Exercises

### Exercise 1

What does a non-derivative AdS contact interaction look like in Mellin space?

<details><summary><strong>Solution</strong></summary>

A non-derivative contact interaction gives a constant Mellin amplitude, up to normalization and convention-dependent Gamma factors in the full Mellin representation. Derivative contact interactions give polynomials in the Mellin variables.

</details>

### Exercise 2

What is the Mellin-space signature of a single-trace exchange?

<details><summary><strong>Solution</strong></summary>

A single-trace operator of dimension $\Delta_X$ and spin $\ell_X$ produces a family of Mellin poles, schematically

$$
s=\Delta_X-\ell_X+2m,
\qquad
m=0,1,2,\ldots .
$$

The residues are polynomials in the other Mellin variable and encode spin and OPE data.

</details>

### Exercise 3

Why are Gamma factors important in the Mellin representation?

<details><summary><strong>Solution</strong></summary>

Gamma factors contain universal kinematic pole families associated with double-trace operators and descendants. If one ignores them, one may misidentify kinematic poles as dynamical exchange poles. The separation between Gamma factors and the Mellin amplitude is convention-dependent and must be tracked carefully.

</details>

### Exercise 4

Why does the flat-space limit require large Mellin variables?

<details><summary><strong>Solution</strong></summary>

Flat-space scattering is recovered by taking the AdS radius large while keeping local bulk energies fixed. Since Mellin variables measure energy-like quantities in AdS units, they scale with powers of $R_{\rm AdS}$ times flat-space Mandelstam invariants. Thus the flat-space limit probes large Mellin variables.

</details>

### Exercise 5

How does Mellin growth diagnose bulk locality?

<details><summary><strong>Solution</strong></summary>

A local AdS EFT with finitely many derivatives gives Mellin amplitudes with controlled polynomial growth below the cutoff. If the Mellin amplitude grows too rapidly, it suggests nonlocality or missing heavy states. Thus Mellin boundedness is a CFT diagnostic of bulk locality and EFT validity.

</details>

## References

- G. Mack, “D-dimensional conformal field theories with anomalous dimensions as dual resonance models,” *Bulg. J. Phys.* **36** (2009).
- J. Penedones, “Writing CFT correlation functions as AdS scattering amplitudes,” *Journal of High Energy Physics* **2011**.
- A. L. Fitzpatrick, J. Kaplan, J. Penedones, S. Raju, and B. C. van Rees, “A natural language for AdS/CFT correlators,” *Journal of High Energy Physics* **2011**.
- L. Rastelli and X. Zhou, “Mellin amplitudes for AdS5 × S5,” *Physical Review Letters* **118** (2017).
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, “Holography from conformal field theory,” *Journal of High Energy Physics* **2009**.

## Version history

- 2026-07-01: First polished draft. Added Mellin variable dictionary, contact and exchange structures, Gamma-factor caveats, flat-space limit explanation, smearing and large-radius logic, locality and Regge diagnostics, stringy corrections, practical workflow, exercises, and references.
