---
title: "Limits of the Dictionary"
description: "A careful guide to what the AdS/CFT dictionary does and does not imply, including finite N, finite coupling, bottom-up models, non-AdS settings, locality, and phenomenological caveats."
sidebar:
  order: 120
---

AdS/CFT is powerful partly because its central statement is so sharp: a quantum theory of gravity in asymptotically AdS spacetime can be exactly equivalent to a non-gravitational quantum theory on the conformal boundary. But the practical dictionary used in calculations is usually a controlled approximation to that exact statement.

This page is about the boundary of confidence. It is a map of where the dictionary is solid, where it is perturbative, where it is phenomenological, and where it becomes speculative.

The point is not to weaken the duality. The point is to avoid using a precise tool imprecisely.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A ladder of holographic control: exact top-down AdS/CFT, semiclassical string theory, classical supergravity, bottom-up models, and non-AdS proposals.](/figures/course/limits-of-the-dictionary.svg)

<figcaption>

The dictionary becomes less automatic as assumptions are removed. Exact top-down AdS/CFT, classical bulk EFT, bottom-up phenomenology, and non-AdS proposals are related but not interchangeable.

</figcaption>
</figure>

## The secure core

The secure conceptual core of AdS/CFT is not the claim that every strongly coupled system is secretly a black hole. It is the claim that in certain controlled examples there is an equality of quantum theories,

$$
Z_{\rm QG/string}[\text{asymptotic data}]
=
Z_{\rm CFT}[\text{sources}],
$$

with the asymptotic bulk data identified with sources for boundary operators.

In a classical gravity limit, this becomes

$$
W_{\rm CFT}[J]
=
\log Z_{\rm CFT}[J]
\approx
-S_{\text{ren,on-shell}}[J].
$$

This formula has assumptions hidden in every symbol:

- the bulk is asymptotically AdS;
- boundary conditions are specified;
- the bulk saddle is dominant;
- quantum loops and string corrections are suppressed;
- the on-shell action is renormalized;
- the source $J$ couples to a well-defined boundary operator;
- the variational principle is well posed.

The formula is trustworthy when these assumptions are trustworthy.

## Three different meanings of “the limit of AdS/CFT”

There are at least three different questions people mean when they ask about limits of the dictionary.

First, there are **regime limits**. These ask when a known duality reduces to a simpler approximation: classical supergravity, probe branes, hydrodynamics, near-horizon AdS$_2$, or a geodesic approximation.

Second, there are **model limits**. These ask whether a chosen bottom-up model really comes from a consistent quantum theory. The answer may be unknown even if the model is useful.

Third, there are **conceptual limits**. These ask whether something like AdS/CFT exists for flat space, de Sitter space, cosmology, realistic QCD, or arbitrary quantum systems. These are research frontiers, not settled entries in the basic dictionary.

Keeping these meanings separate prevents many bad arguments.

## Finite $N$: bulk quantum gravity returns

The classical bulk limit requires large $N$. In a standard holographic normalization,

$$
\frac{L^{d-1}}{G_N} \sim N^2
$$

for adjoint large-$N$ gauge theories. Bulk loops are suppressed by powers of $G_N/L^{d-1}$, hence by powers of $1/N^2$.

At finite $N$, classical geometry is no longer the whole answer. Bulk quantum effects contribute. Correlators no longer factorize perfectly. Black-hole entropy is not just a classical area; it receives quantum corrections. Entanglement entropy is not just the RT/HRT area term but becomes generalized entropy,

$$
S(A)=\underset{X}{\mathrm{ext}}\left[
\frac{\mathrm{Area}(X)}{4G_N}+S_{\rm bulk}(\Sigma_X)+\cdots
\right].
$$

The important point is not that AdS/CFT fails at finite $N$. In exact examples, finite $N$ is where AdS/CFT becomes a nonperturbative definition of quantum gravity. What fails is the simple classical bulk picture.

A finite-$N$ CFT may still be perfectly well defined while the corresponding bulk description is highly quantum, nonlocal in simple geometric variables, or stringy.

## Finite coupling: strings return

In the canonical AdS$_5$/CFT$_4$ example,

$$
\frac{L^4}{\alpha'^2}=\lambda.
$$

Large $\lambda$ means the curvature radius is large compared with the string length. Finite $\lambda$ means stringy corrections become important. The bulk action is no longer just Einstein gravity plus a few light fields; it contains an infinite tower of massive string states and higher-derivative interactions.

A common schematic expansion is

$$
S_{\rm bulk}
=
S_{\rm SUGRA}
+
\alpha'^3 R^4
+\cdots .
$$

The detailed structure depends on the compactification and supersymmetry. The lesson is general: classical two-derivative gravity is not the whole duality. It is a low-energy, large-gap approximation.

From the CFT side, finite coupling means that single-trace operators dual to stringy modes may not be parametrically heavy. The would-be local bulk EFT is contaminated by extra light states.

## Not every CFT has an Einstein gravity dual

A CFT does not automatically have a weakly curved Einstein gravity dual. The practical classical dictionary requires special features.

A useful checklist is:

1. large central charge or large $N$;
2. factorization of correlators;
3. a sparse spectrum of low-dimension single-trace operators;
4. a large gap to higher-spin or stringy single-trace operators;
5. consistent crossing, positivity, and causality properties;
6. a stress tensor with the right role as the unique low-spin spin-two operator.

Large $N$ alone is not enough. Vector models have large $N$, but their singlet sector contains an infinite tower of approximately conserved higher-spin currents. Their holographic duals, when they exist, are higher-spin-like rather than ordinary Einstein gravity.

The rough boundary statement is:

$$
\text{large }N + \text{large sparse gap}
\quad
\Longleftrightarrow
\quad
\text{local bulk EFT below the gap}.
$$

This is a guiding principle, not a theorem in every possible theory. But it is one of the most important guardrails in modern holography.

## Classical bulk locality is emergent and approximate

Bulk locality is not a microscopic axiom of the CFT. It is an emergent property of a special large-$N$ sector.

At leading order in large $N$, single-trace operators behave like weakly interacting bulk fields. Multi-trace operators behave like multiparticle states. At subleading order, interactions, dressing, and gravitational constraints matter.

Even in a good holographic CFT, a local bulk field $\Phi(X)$ is not a fundamental gauge-invariant observable of quantum gravity. Bulk operators must be gravitationally dressed, and their reconstruction depends on a choice of boundary region, gauge, and code subspace. Near black holes, behind horizons, or at finite $N$, these subtleties become sharper.

The safe statement is:

$$
\text{bulk locality}
=
\text{an approximate organizing principle in a semiclassical code subspace}.
$$

It is not a microscopic property that can be extrapolated without qualification.

## Bottom-up models have an extra layer of uncertainty

Bottom-up models use the dictionary without starting from a known microscopic dual. This can be extremely useful, but it changes the epistemic status of the calculation.

A bottom-up model may correctly capture:

- the consequences of a symmetry;
- a horizon-controlled transport coefficient;
- a possible instability mechanism;
- the scaling behavior of an IR geometry;
- qualitative features of a strongly coupled phase.

It may fail as a complete quantum theory because of:

- missing light fields;
- inconsistent higher-derivative couplings;
- causality or positivity violations;
- unstable backgrounds;
- wrong UV asymptotics;
- an IR boundary condition imposed by hand;
- no known string embedding.

This does not make bottom-up work bad. It means the claims should be phrased at the right level. “This model realizes a robust mechanism” is often much stronger and more honest than “this is the dual of the target system.”

## Phenomenological targets are not exact holographic duals

AdS/QCD is not QCD unless a specific duality is found. Holographic strange metals are not literal laboratory materials unless the microscopic map is supplied. Holographic nuclear matter, holographic cosmology, and holographic turbulence can be useful without being exact.

The reason is simple: real-world QCD has finite $N_c=3$, running coupling, asymptotic freedom, quarks in particular representations, chiral physics, confinement, and a complicated spectrum. A bottom-up AdS/QCD model may encode a few of these features, but it does not automatically reproduce the full theory.

Similarly, many condensed matter systems are not relativistic CFTs at large $N$ with sparse single-trace spectra. Holography may still illuminate universal behavior, but the dictionary is then used as a model-building framework rather than as a proven microscopic equivalence.

A good phenomenological holographic paper should state what is universal, what is fitted, and what is merely suggestive.

## Finite cutoff is not the same as an exact Wilsonian RG step

The UV/IR relation says that the radial direction is tied to energy scale. This makes it tempting to say that a finite radial cutoff is simply a Wilsonian cutoff in the boundary theory.

That statement is useful but not automatic. At a finite radial surface, the induced fields are dynamical from the bulk point of view, the Hamiltonian constraints remain, and the relation to a Wilsonian effective action can be scheme-dependent. Multi-trace operators and nonlocal terms can be generated. The cutoff theory is generally not just “the same CFT with modes above $\Lambda$ removed.”

A safer statement is:

$$
\text{radial evolution organizes RG data,}
$$

but the exact Wilsonian interpretation depends on boundary conditions, counterterm scheme, and which variables one holds fixed.

## Non-AdS holography is not just AdS/CFT with a new metric

The AdS dictionary relies heavily on the structure of the AdS boundary. The conformal boundary is timelike. One can impose boundary conditions, define sources, and compute a boundary generating functional.

Flat space and de Sitter space are different.

In asymptotically flat space, the natural observables are often scattering amplitudes at null infinity, not Euclidean or Lorentzian CFT correlation functions on a timelike boundary. There are promising structures involving celestial CFT, BMS symmetry, flat-space limits of AdS correlators, and matrix-theory-like formulations, but there is no single universal flat-space dictionary with the same status as standard AdS/CFT.

In de Sitter space, the boundary is spacelike rather than timelike, cosmological horizons appear, and the interpretation of observables is more subtle. There are dS/CFT-like proposals and wavefunction dictionaries, but they are not simply the AdS source-response dictionary with $L^2\to -L^2$.

The honest lesson for a foundations course is:

$$
\text{AdS/CFT is controlled; non-AdS holography is active research.}
$$

That does not make non-AdS holography unimportant. It makes the distinction essential.

## Euclidean and Lorentzian dictionaries are not interchangeable

The Euclidean GKPW prescription is conceptually clean:

$$
Z_{\rm CFT}[J]
\approx e^{-S_{E,\text{ren,on-shell}}[J]}.
$$

Lorentzian real-time physics requires more data. Retarded correlators need infalling horizon boundary conditions. Time-ordered correlators require a choice of contour. Thermal real-time correlators are naturally Schwinger–Keldysh objects. Behind-horizon questions require even more care.

A common mistake is to compute a Euclidean correlator, analytically continue casually, and forget that different Lorentzian correlators have different boundary conditions. This is not a cosmetic issue; it changes the answer.

## Singularities and strong curvature

Classical bulk solutions can develop singularities. Some singularities are acceptable IR endpoints in an effective sense; others signal that the approximation has failed.

Criteria such as finite temperature cloaking, Gubser-type good-singularity conditions, uplift to a smooth higher-dimensional geometry, or stability under perturbations can help. But in general, if curvature becomes string scale or Planck scale, a two-derivative classical model is no longer enough.

The same warning applies to extreme parameter regimes of bottom-up potentials. A beautiful numerical solution is not automatically meaningful if it lives in a region where the effective bulk action has lost control.

## Global questions and nonperturbative effects

Classical gravity often misses effects that are nonperturbative in $1/N$:

$$
\Delta W \sim e^{-N^2}.
$$

Such effects can matter for questions about exact unitarity, late-time correlators, black-hole information, spectral discreteness, and Poincaré recurrences. A black brane geometry may predict exponential decay of correlators at intermediate times, while the exact finite-volume finite-$N$ CFT has a discrete spectrum and cannot decay forever in the same way.

This is not a contradiction. It is the difference between a semiclassical saddle approximation and the exact finite-$N$ quantum system.

## The dictionary can be scheme-dependent

Some quantities are unambiguous. Others depend on choices of local counterterms.

For example, one-point functions often have contact-term ambiguities. The Weyl anomaly is physical, but the form of local finite terms in $\langle T_{ij}\rangle$ can depend on the renormalization scheme. In transport, contact terms can shift the real part of correlators by polynomials in frequency or momentum. In entanglement entropy, cutoff-dependent area-law terms are not universal, while certain logarithmic or finite terms may be.

The rule is familiar from ordinary QFT: distinguish universal data from scheme-dependent local terms.

## What remains true even at the limits?

Even when the dictionary is stretched, several lessons remain valuable.

First, the boundary generating functional is the organizing object. Sources, responses, Ward identities, and anomalies still provide the cleanest language.

Second, horizons are powerful effective descriptions of dissipation and thermality. Horizon regularity often controls IR response.

Third, large-$N$ factorization explains why weakly interacting bulk fields can emerge.

Fourth, entanglement has geometric avatars in semiclassical holography, but quantum corrections and code-subspace restrictions matter.

Fifth, every bulk statement should have a boundary translation. If one cannot say what boundary observable is being computed, the statement probably needs refinement.

## A practical honesty checklist

Before trusting a holographic calculation, ask:

1. Is there a known microscopic dual, or is this bottom-up?
2. Is the bulk asymptotically AdS, and what is the boundary geometry?
3. What are the sources and operators?
4. Which ensemble is being used?
5. Are $1/N$ and stringy corrections suppressed?
6. Is there a large gap supporting local bulk EFT?
7. Are the boundary conditions well posed?
8. Has the on-shell action been renormalized?
9. Do the Ward identities and thermodynamics work?
10. Are higher-derivative terms perturbative and causal?
11. Are the results universal or model-dependent?
12. Does the claim concern AdS, flat space, de Sitter space, or a phenomenological analogy?

This checklist is not pedantry. It is how the dictionary stays trustworthy.

## Dictionary checkpoint

| Claim | Safe version |
|---|---|
| “Every CFT has a gravity dual.” | Every CFT may define some quantum system; only special large-$N$, sparse CFTs have weakly curved local Einstein-like duals. |
| “Classical gravity is AdS/CFT.” | Classical gravity is a large-$N$, large-gap/large-coupling limit of AdS/CFT. |
| “Bottom-up models are duals.” | Bottom-up models are effective holographic laboratories unless a microscopic dual is known. |
| “The radial direction is the RG scale.” | Radial evolution organizes RG data, but finite-cutoff Wilsonian interpretations require care. |
| “A bulk gauge field means boundary electromagnetism.” | A bulk gauge field usually means a boundary global current unless the boundary symmetry is gauged. |
| “Non-AdS holography works like AdS/CFT.” | Non-AdS holography is an active research area without one universal source-response dictionary. |
| “Local bulk operators are fundamental.” | Bulk locality is approximate and code-subspace dependent in quantum gravity. |

## Common confusions

### “If AdS/CFT is exact, why worry about limits?”

Because most calculations are not done in the exact theory. They are done in classical gravity, classical string theory, probe limits, hydrodynamic limits, geodesic limits, or bottom-up truncations. The exact duality may remain true while a particular approximation fails.

### “Finite $N$ invalidates AdS/CFT.”

No. Finite $N$ invalidates the naive classical bulk approximation. In exact examples, finite $N$ is the genuinely quantum-gravitational regime of the same duality.

### “A large central charge guarantees Einstein gravity.”

No. Large central charge suppresses some fluctuations, but without a large gap to higher-spin or stringy operators the bulk may not be local Einstein gravity. Large-$N$ vector models are the canonical warning sign.

### “If a bottom-up model reproduces one observable, it is correct.”

One fitted observable is weak evidence. A model gains credibility when it explains several observables, satisfies consistency checks, and makes predictions stable under reasonable deformations.

### “Flat-space and de Sitter holography are solved because AdS/CFT exists.”

No. AdS/CFT is a controlled example of holography, not a universal completed dictionary for every asymptotic structure. Flat and de Sitter holography are central research directions precisely because the AdS tools do not transfer automatically.

## Exercises

### Exercise 1: Large $N$ but no large gap

A CFT has a large parameter $N$ and factorized correlators, but it also has infinitely many low-dimension higher-spin conserved currents. Should you expect a weakly curved Einstein gravity dual?

<details>
<summary><strong>Solution</strong></summary>

No. Large $N$ helps suppress interactions, but the low-dimension higher-spin currents indicate many light higher-spin bulk fields. A weakly curved Einstein dual requires not only large $N$ but also a sparse low-dimension spectrum and a large gap to higher-spin or stringy single-trace operators. This theory is more naturally associated, if holographic at all, with higher-spin gravity rather than ordinary Einstein gravity.

</details>

### Exercise 2: Finite coupling correction

In AdS$_5$/CFT$_4$, why does finite $\lambda$ imply stringy corrections?

<details>
<summary><strong>Solution</strong></summary>

The parameter relation is

$$
\frac{L^4}{\alpha'^2}=\lambda.
$$

Equivalently,

$$
\frac{\alpha'}{L^2}=\lambda^{-1/2}.
$$

When $\lambda$ is large, the string length is much smaller than the AdS radius, so the bulk is weakly curved in string units. When $\lambda$ is finite, the curvature is not parametrically small in string units, and the massive string tower and higher-derivative $\alpha'$ corrections cannot be ignored in general.

</details>

### Exercise 3: Scheme dependence

Why are polynomial-in-momentum terms in a two-point function often less physical than nonanalytic terms?

<details>
<summary><strong>Solution</strong></summary>

Polynomial-in-momentum terms correspond to local contact terms in position space. They can often be shifted by adding finite local counterterms to the renormalized action. Nonanalytic terms, such as powers with branch cuts or logarithms fixed by anomalies, usually encode long-distance physics and cannot be removed by local counterterms. The exact statement depends on the operator and dimension, but the distinction between local scheme-dependent terms and nonlocal universal terms is central.

</details>

### Exercise 4: Non-AdS caution

Why can’t the AdS source-response formula be copied directly into de Sitter space?

<details>
<summary><strong>Solution</strong></summary>

The AdS formula relies on a timelike conformal boundary where one can impose boundary conditions and interpret leading asymptotic data as sources for a Lorentzian or Euclidean boundary QFT. De Sitter space has a different causal structure, with spacelike future and past boundaries and cosmological horizons. The relevant object is often closer to a wavefunction of the universe than to an ordinary boundary generating functional. There are dS/CFT-like proposals, but the dictionary is not simply the AdS dictionary with a sign changed.

</details>

## Further reading

- J. Maldacena, [The Large N Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large N Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151).
- X. O. Camanho, J. D. Edelstein, J. Maldacena, and A. Zhiboedov, [Causality Constraints on Corrections to the Graviton Three-Point Coupling](https://arxiv.org/abs/1407.5597).
- J. Maldacena and A. Zhiboedov, [Constraining Conformal Field Theories with a Higher Spin Symmetry](https://arxiv.org/abs/1112.1016).
- D. Anninos, [De Sitter Musings](https://arxiv.org/abs/1205.3855).
- T. Banks, [Holographic Space-Time: The Takeaway](https://arxiv.org/abs/1109.2435).
