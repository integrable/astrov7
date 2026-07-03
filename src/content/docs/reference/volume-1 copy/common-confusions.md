---
title: "Common Confusions"
description: "A conceptual debugger for the most common QFT misunderstandings: fields versus wavefunctions, particles, propagators, causality, gauge redundancy, path integrals, renormalization, and structural assumptions."
sidebar:
  label: "Common Confusions"
  order: 90
---

## Summary

This page is a **conceptual debugger** for Foundations of QFT. It collects mistakes that are not merely beginner mistakes. Many of them survive into advanced work because the same symbols are reused in different languages: classical fields, operator fields, path-integral variables, background fields, wavefunctions, propagators, and sources all get called things like $\phi$, $A_\mu$, or $\psi$.

The goal is not to shame the confusion. QFT is basically a convention factory attached to a theorem engine. Confusion is normal; leaving it unnamed is the dangerous part.

A useful first diagnostic is:

| If you are looking at... | Ask first... |
|---|---|
| a field $\phi(x)$ | Is it classical, an operator-valued distribution, or a path-integral variable? |
| a propagator | Is it Wightman, Feynman, retarded, advanced, or Euclidean? |
| a symmetry | Is it global physical symmetry or gauge redundancy? |
| a particle | Is it an external asymptotic state, a pole, a quasiparticle, or an internal-line shorthand? |
| a divergence | Is it UV, IR, volume, gauge-orbit overcounting, or a bad variable choice? |
| a theorem | Which assumptions are being used: locality, Lorentz invariance, positive energy, unitarity, stable vacuum? |

## Prerequisites

This page assumes familiarity with the main Foundations spine: [Conventions and Normalizations](/foundations/conventions-and-normalizations/), [Why Fields?](/foundations/relativistic-particles-and-fields/why-fields/), [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/), [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/), [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/), [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/), and [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/).

:::tip[How to use this page]
When a formula feels right but the words around it feel slippery, look here. Each item gives a misleading sentence, a better sentence, and the reason. The better sentence is usually less cute and more useful. Physics has many such tradeoffs.
:::


<figure class="doc-figure" style="--figure-width: 56rem;">

![Common conceptual traps in Foundations of QFT](/figures/foundations/common-confusions-map.svg)

<figcaption>

Most QFT confusions come from treating a useful slogan as a literal definition. The repair is to identify the object, formalism, symmetry, and structural assumptions in play before interpreting the formula.

</figcaption>
</figure>

## Quick correction table

| Misleading sentence | Better sentence |
|---|---|
| “A quantum field is a relativistic wavefunction.” | A quantum field is usually an operator-valued distribution, or a path-integral variable, whose correlators encode quantum dynamics. |
| “The Klein–Gordon equation failed, so we discarded it.” | The Klein–Gordon equation failed as a one-particle probability equation, but it is exactly the free scalar field equation. |
| “Particles are the fundamental ingredients of QFT.” | Particle states are excitations, asymptotic states, or poles, depending on context; the local formalism is written in terms of fields and operators. |
| “The Feynman propagator is the amplitude for a particle to travel.” | It is a time-ordered vacuum two-point function and a Green function with a boundary prescription. |
| “The Feynman propagator is nonzero outside the light cone, so QFT violates causality.” | Causality is controlled by commutators and retarded response functions, not by the Feynman propagator alone. |
| “Gauge symmetry is an ordinary physical symmetry.” | Gauge symmetry is redundancy in the description; global symmetries act on physical states. |
| “Ghosts are weird physical particles.” | Faddeev–Popov ghosts are auxiliary Grassmann fields used to represent gauge-fixing determinants; they are not external physical states. |
| “Normal ordering removes infinities.” | Normal ordering removes a particular free-vacuum contraction; renormalization is a broader statement about local counterterms and scale dependence. |
| “Renormalization means ignoring infinity.” | Renormalization is the controlled organization of short-distance sensitivity into parameters and operators. |
| “Euclidean QFT is always just Lorentzian QFT with imaginary time.” | Wick rotation requires analytic control, and a Euclidean theory must satisfy reflection positivity to reconstruct a unitary Lorentzian theory. |


## A field is not a wavefunction

Reference anchor: Srednicki's opening sections, Coleman's first scalar-field lectures, and Weinberg's causal-field construction all make this distinction in different languages (Srednicki 2007, §§1 and 3; Coleman 2018, Chs. 1–3; Weinberg 1995, Ch. 5).

The symbol $\phi(x)$ is tempting because it looks like the nonrelativistic wavefunction $\psi(\mathbf x,t)$. Resist that temptation.

In nonrelativistic one-particle quantum mechanics, $\psi(\mathbf x,t)$ is a state-dependent probability amplitude. It tells you about one particle's position in a fixed-particle-number Hilbert space.

In operator QFT, a scalar field is instead an operator-valued distribution,

$$
\phi(x)=\int\frac{d^3\mathbf p}{(2\pi)^3}\frac{1}{\sqrt{2E_{\mathbf p}}}
\left(a_{\mathbf p}e^{-ip\cdot x}+a^\dagger_{\mathbf p}e^{ip\cdot x}\right),
$$

for the free real scalar in the qft.org convention. It acts on states. It is not itself the wavefunction of a particle. The state is a vector such as $|0\rangle$, $a^\dagger_{\mathbf p}|0\rangle$, or a wavepacket built from many such states.

In the path-integral language, the same symbol $\phi(x)$ is often reused for an integration variable. That is another object again. It is not an operator inside the integral; it is a dummy variable in a functional integral whose correlation functions reproduce operator expectation values when the formalism is well-defined.

A better slogan is:

$$
\boxed{\text{Fields are local variables/operators; particles are states or excitations.}}
$$

See [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/) and [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/) for the two complementary languages.

## The Klein–Gordon equation is not the mistake

The free scalar equation

$$
(\Box+m^2)\phi=0
$$

is not wrong. What fails is the attempt to treat a general solution of this equation as a one-particle wavefunction with a positive-definite conserved probability density.

The classical Klein–Gordon equation has both positive- and negative-frequency solutions. As a one-particle equation, this leads to the familiar interpretational trouble. As a field equation, it is perfectly natural: the positive- and negative-frequency pieces become creation and annihilation parts of a quantum field. For a complex scalar, the two mode families become particle and antiparticle modes.

So the correction is:

```txt
Wrong: The Klein–Gordon equation is unphysical.
Better: The Klein–Gordon equation is not a satisfactory general one-particle probability equation, but it is the correct free scalar field equation.
```

This is the first major lesson of [Why Fields?](/foundations/relativistic-particles-and-fields/why-fields/), [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/), and [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/). Srednicki's opening chapter and Weinberg's historical introduction are useful references for this transition from failed relativistic wave mechanics to quantum fields.

## Particles are not always fundamental inputs

Reference anchor: Weinberg starts from relativistic particle states and derives causal fields, while LSZ explains how fields interpolate asymptotic particles (Weinberg 1995, Chs. 2, 5, and 10; Coleman 2018, Chs. 13–14; Srednicki 2007, §5).

Particles are indispensable, but the word “particle” changes meaning across QFT.

For a stable massive particle in flat spacetime, a one-particle state is organized by a unitary irreducible representation of the Poincaré group. It has mass, spin, momentum, and possibly internal charges. That is the clean Wigner/Weinberg viewpoint.

For an interacting field theory, a particle can also appear as a pole in a two-point function or an S-matrix element. A stable scalar particle gives a pole of the form

$$
\frac{iZ}{p^2-m^2+i\epsilon}
$$

near $p^2=m^2$. An unstable resonance gives a nearby complex pole, not a stable asymptotic state. In a confining theory, colored quark and gluon fields do not create isolated asymptotic particles. In curved spacetime or time-dependent backgrounds, even the split into positive and negative frequency modes can become observer- or state-dependent.

A better slogan is:

$$
\boxed{\text{Particles are context-dependent states, excitations, or poles.}}
$$

See [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/), [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/), [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/), and [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/).

## A local field does not create a sharply localized particle

It is common to hear that $\phi(x)$ “creates a particle at $x$.” That is useful shorthand, but taken literally it causes trouble.

For the free scalar,

$$
\phi(x)|0\rangle
=\int\frac{d^3\mathbf p}{(2\pi)^3}\frac{e^{ip\cdot x}}{\sqrt{2E_{\mathbf p}}}
a^\dagger_{\mathbf p}|0\rangle.
$$

This is a one-particle superposition over all momenta. It is not a normalizable detector-ready particle sitting at one exact spacetime point. Local fields are distributions, so physically meaningful insertions are smeared with test functions or integrated against sources.

The useful statement is:

```txt
A local field insertion creates a state with the quantum numbers of that field.
It is not the same thing as a sharply localized particle state.
```

This distinction matters in LSZ: scattering amplitudes do not come from a mystical picture of particles emitted at mathematical points. They come from poles of Fourier-transformed correlators and from projecting onto asymptotic one-particle states.

## Virtual particles are bookkeeping, not ontology

Reference anchor: in the perturbative derivation of Feynman rules, internal lines are propagator factors and integration variables, not asymptotic one-particle states (Coleman 2018, Ch. 8; Weinberg 1995, Ch. 6).

“Virtual particle” language is not forbidden. It is just easy to overinterpret.

An internal line in a Feynman diagram represents a propagator. It is integrated over internal momentum, is generally off shell, and is not an independently observable state. Its form depends on field variables, gauge choice, and perturbative organization. In gauge theories, individual internal-line stories are especially gauge-dependent; only gauge-invariant amplitudes and observables carry physical meaning.

The safe version is:

```txt
Virtual particle = informal shorthand for an internal propagator contribution in a chosen perturbative expansion.
```

The physical content is not that a tiny temporary object literally travelled between two points. The physical content is in the full amplitude, its poles, cuts, symmetries, and observable probabilities. For this distinction, see [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/), [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/), and [Analyticity and Causality](/foundations/structural-principles/analyticity-and-causality/).

## The Feynman propagator is not a probability amplitude

Reference anchor: the distinction between Feynman, Wightman, retarded, advanced, and commutator functions is standard in the operator and Green-function treatments of free fields (Coleman 2018, Chs. 3 and 13; Weinberg 1995, Chs. 6 and 10).

The scalar Feynman propagator is

$$
i\Delta_F(x-y)=\langle0|T\phi(x)\phi(y)|0\rangle,
$$

or, in momentum space,

$$
\Delta_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

It is a vacuum correlation function and a Green function with a boundary prescription. It is not directly a probability amplitude for a particle to move from $y$ to $x$.

This matters because probabilities in scattering are built from S-matrix elements, phase space, spin sums, and absolute squares. Correlators become scattering amplitudes only after the LSZ limiting procedure projects external legs onto on-shell asymptotic states.

The better sentence is:

$$
\boxed{\text{The Feynman propagator is a time-ordered two-point function, not a direct probability.}}
$$

See [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) and [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/).

## Spacelike Feynman propagation does not violate causality

The Feynman propagator does not generally vanish at spacelike separation. That sounds scary only if one mistakes it for a signal.

Microcausality is instead the statement that local observables commute at spacelike separation. For a scalar field,

$$
[\phi(x),\phi(y)]=i\Delta(x-y),
$$

and

$$
\Delta(x-y)=0
\qquad\text{if }(x-y)^2<0.
$$

The retarded propagator,

$$
\Delta_R(x-y)=\theta(x^0-y^0)\Delta(x-y),
$$

also has causal support. It is the object suited to response: perturb here, measure there. A time-ordered vacuum correlator is a different object.

So the correction is:

```txt
Wrong: Causality means every two-point function vanishes outside the light cone.
Better: Causality means commutators and retarded response vanish outside the light cone.
```

See [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/), [Retarded and Advanced Propagators](/foundations/correlators-and-propagators/retarded-and-advanced-propagators/), and [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/).

## Time ordering is not causal ordering

The time-ordered product of two bosonic operators is

$$
T\{A(x)B(y)\}
=\theta(x^0-y^0)A(x)B(y)+\theta(y^0-x^0)B(y)A(x),
$$

with signs for fermionic interchanges. This ordering is by the coordinate $x^0$ in a chosen inertial frame.

For timelike separated events, all inertial observers agree on the order. For spacelike separated events, different frames may disagree. QFT survives this because local bosonic observables commute, and fermionic fields anticommute in the graded sense, at spacelike separation. Thus the frame-dependent ordering of spacelike-separated insertions does not become a frame-dependent observable signal.

Also, derivatives of time-ordered products produce contact terms. For example,

$$
\partial_\mu T\{j^\mu(x)\mathcal O(y)\}
$$

can contain delta-function terms at $x^0=y^0$ even when $\partial_\mu j^\mu=0$ away from insertions. This is why Ward identities are local identities with contact terms, not just naive current conservation inside correlators.

See [Time Ordering](/foundations/correlators-and-propagators/time-ordering/) and [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/).

## The i epsilon is not decoration

Reference anchor: the prescription fixes pole placement, boundary conditions, and Wick rotation conventions (Srednicki 2007, §§8 and 13; Weinberg 1995, Ch. 9).

The expression

$$
\frac{i}{p^2-m^2}
$$

is not yet a propagator. The poles need a prescription. The Feynman propagator is

$$
\frac{i}{p^2-m^2+i\epsilon},
$$

which displaces the positive- and negative-energy poles in a particular way. Retarded and advanced propagators use different prescriptions because they impose different boundary conditions.

The $i\epsilon$ also encodes how the vacuum is selected in Lorentzian path integrals. It makes oscillatory Gaussian integrals meaningful by specifying how contours are approached. In exact interacting propagators, the same idea appears inside the Källén–Lehmann representation.

So:

```txt
Wrong: Add iε at the end if needed.
Better: The iε prescription is part of the definition of the Green function.
```

See [iε Prescription](/foundations/correlators-and-propagators/i-epsilon-prescription/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), and [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/).

## Normal ordering is not renormalization

Reference anchor: normal ordering is a free-field subtraction defined relative to a chosen oscillator basis; renormalization is the broader organization of local short-distance sensitivity (Coleman 2018, Ch. 4; Zee 2010, I.9; Weinberg 1995, Ch. 12).

Normal ordering moves annihilation operators to the right of creation operators. For a free oscillator or free field, it subtracts vacuum contractions such as

$$
\langle0|\phi(x)\phi(x)|0\rangle.
$$

This is useful. It is not the same as renormalization.

Normal ordering depends on a chosen split into creation and annihilation operators, usually tied to a free Hamiltonian and vacuum. In an interacting theory, composite operators require renormalization. In curved spacetime or time-dependent backgrounds, the free-vacuum split may not be unique. Even in flat spacetime, normal ordering a Hamiltonian does not automatically make all loop corrections finite.

The safe sentence is:

```txt
Normal ordering is a free-field subtraction convention; renormalization is the systematic treatment of short-distance dependence.
```

See [Normal Ordering](/foundations/canonical-quantization/normal-ordering/) and [UV Divergences Preview](/foundations/interactions-and-wick-expansion/uv-divergences-preview/).

## Canonical quantization and path integrals are not rival theories

Canonical quantization emphasizes Hilbert space, operators, commutators, time evolution, and unitarity. Path integrals emphasize actions, sources, functional differentiation, symmetry, saddle points, and manifest covariance. In ordinary cases they describe the same quantum theory.

Each language hides something:

| Language | Makes transparent | Can obscure |
|---|---|---|
| canonical | Hilbert space, unitarity, particles, constraints | covariance, perturbative bookkeeping |
| path integral | locality of the action, generating functionals, Feynman rules, Euclidean methods | Hilbert-space positivity, measure subtleties, operator domains |

A mature calculation often uses both. For example, one may use canonical quantization to identify states and the path integral to compute correlators.

See [Canonical Commutation Relations](/foundations/canonical-quantization/canonical-commutation-relations/), [Quantum Mechanical Path Integral](/foundations/path-integral-formalism/quantum-mechanical-path-integral/), and [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/). Weinberg's path-integral chapter is particularly explicit that path integrals are excellent for deriving Feynman rules, while the canonical framework keeps the quantum-mechanical meaning visible.

## The path integral is not only a sum over classical paths

The phrase “sum over paths” is fine, but “classical paths” is wrong. The path integral sums over configurations, not just solutions of the classical equations.

The classical equation appears as the stationary point of the action:

$$
\left.\frac{\delta S}{\delta\phi(x)}\right|_{\phi=\phi_{\rm cl}}=0.
$$

The semiclassical expansion then writes

$$
\phi=\phi_{\rm cl}+\eta
$$

and expands in fluctuations $\eta$. But this is an approximation scheme, not the definition of the integral.

Also, the Lorentzian path integral is oscillatory,

$$
\int\mathcal D\phi\,e^{iS[\phi]},
$$

while the Euclidean path integral is often damping,

$$
\int\mathcal D\phi\,e^{-S_E[\phi]}.
$$

Those are not interchangeable without analytic assumptions.

See [Semiclassical Expansion](/foundations/path-integral-formalism/semiclassical-expansion/) and [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/).

## The path-integral measure can carry physics

Reference anchor: the regulated measure and its Jacobian are central in the path-integral treatment of anomalies (Srednicki 2007, §§76–77; Weinberg 1996, Ch. 22; Zee 2010, IV.7).

The symbolic expression

$$
\int\mathcal D\phi
$$

hides a regulator, a choice of variables, and sometimes a Jacobian. In many elementary changes of variables, the measure is harmless. In other cases, especially fermionic chiral transformations and gauge theories, the measure is where the action's formal symmetry may fail.

A schematic anomaly statement is

$$
\mathcal D\psi\,\mathcal D\overline\psi
\longrightarrow
J[\alpha,A]\,\mathcal D\psi\,\mathcal D\overline\psi,
$$

where the Jacobian $J$ can produce a nonzero divergence for a current that looked conserved classically.

So:

```txt
Wrong: If the classical action is invariant, the quantum theory is automatically invariant.
Better: The action, regulator, and measure must all respect the symmetry; if not, an anomaly may appear.
```

See [Path-Integral Measure](/foundations/path-integral-formalism/path-integral-measure/) and [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/). Zee's anomaly discussion is especially good for the “action invariant, measure not invariant” moral.

## Euclidean QFT is not automatically Lorentzian QFT

Reference anchor: Wick rotation is tied to analytic continuation, and reflection positivity is needed to reconstruct a unitary Lorentzian theory from Euclidean correlators (Weinberg 1995, Ch. 9; Osterwalder–Schrader framework).

Euclidean methods are powerful because many integrals become better behaved after Wick rotation. For a scalar theory, the Lorentzian weight $e^{iS}$ is replaced by a Euclidean weight $e^{-S_E}$.

But a Euclidean theory is not automatically a unitary Lorentzian QFT. To reconstruct a Hilbert space with positive norm and unitary time evolution, the Euclidean correlation functions must satisfy reflection positivity, along with other regularity, covariance, symmetry, and clustering conditions in rigorous formulations.

A good warning sign is a Euclidean action with a wrong-sign kinetic term. The integral may be formal, unstable, or define a theory with negative-norm states after continuation.

See [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) and [Reflection Positivity](/foundations/structural-principles/reflection-positivity/).

## Gauge symmetry is redundancy, not ordinary physical symmetry

Reference anchor: gauge redundancy versus global symmetry is central in canonical and path-integral gauge theory (Coleman 2018, Chs. 27 and 31; Weinberg 1995, Ch. 8; Weinberg 1996, Ch. 15).

A global symmetry relates physically distinct configurations. A gauge transformation relates different descriptions of the same physical configuration.

For scalar QED,

$$
\Phi(x)\mapsto e^{-iq\alpha(x)}\Phi(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x),
$$

but configurations related this way represent the same physical electromagnetic state. The gauge-invariant field strength

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu
$$

is unchanged in Abelian gauge theory.

This is why gauge fixing is not optional bureaucratic paperwork. In a path integral, integrating over all gauge-related potentials overcounts the same physical configuration infinitely many times. Gauge fixing chooses representatives, while BRST symmetry keeps track of the redundancy after gauge fixing.

The correct slogan is:

$$
\boxed{\text{Gauge symmetry is redundancy; global symmetry is physical symmetry.}}
$$

See [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/), [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/), and [BRST Preview](/foundations/gauge-fields-first-principles/brst-preview/). Coleman repeatedly emphasizes this distinction in his electrodynamics lectures.

## Gauge fixing does not destroy gauge physics

Reference anchor: Faddeev–Popov gauge fixing and BRST symmetry are the standard way to make gauge-fixed calculations while preserving physical gauge independence (Srednicki 2007, §74; Weinberg 1996, §15.7).

Gauge fixing can make expressions look non-invariant. That does not mean the physical gauge principle has been abandoned.

For example, covariant gauges add a term such as

$$
\mathcal L_{\rm gf}=-\frac{1}{2\xi}(\partial_\mu A^\mu)^2.
$$

This term chooses a representative in each gauge orbit. Physical quantities should not depend on the gauge parameter $\xi$ when computed correctly. In non-Abelian gauge theory, the Faddeev–Popov determinant is represented by ghost fields, and BRST symmetry organizes the proof that physical quantities are independent of gauge choices.

The better sentence is:

```txt
Gauge fixing breaks manifest gauge redundancy in the formula, not the gauge-invariant content of the theory.
```

## Ghosts are not physical particles

Faddeev–Popov ghosts are Grassmann fields introduced to represent a determinant that arises when gauge orbits are gauge-fixed. In non-Abelian Yang–Mills theory, they have propagators and vertices and appear in loops.

That does not make them physical external particles. Physical states are selected by constraints or, in covariant quantization, by BRST cohomology. Ghosts are bookkeeping fields that ensure the cancellation of unphysical gauge modes and preserve unitarity of the physical S matrix.

This is why ghost loops are necessary, not suspicious. Without them, gauge-fixed perturbation theory would generally fail Ward/Slavnov–Taylor identities and unitarity.

See [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/) and [BRST Preview](/foundations/gauge-fields-first-principles/brst-preview/).

## Ward identities are not optional consistency checks

Reference anchor: equal-time commutators and path-integral changes of variables both produce contact terms in Ward identities (Coleman 2018, Ch. 33; Srednicki 2007, §§67–68).

Ward identities are the correlation-function form of symmetry. In operator language, they follow from current conservation plus equal-time commutators. In path-integral language, they follow from changes of variables in the functional integral, provided the measure and regulator respect the symmetry.

A typical local identity has the form

$$
\partial_\mu\langle T\,j^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=\sum_k\delta^{(4)}(x-x_k)
\langle T\,\mathcal O_1\cdots\delta\mathcal O_k\cdots\mathcal O_n\rangle,
$$

up to explicit breaking and anomaly terms. The right-hand side is not a mistake. It is the contact-term expression of how the inserted operators transform.

The bad slogan is:

```txt
The current is conserved, so its divergence inside any correlator is zero.
```

The better one is:

```txt
The current divergence inside a time-ordered correlator gives contact terms, explicit breaking terms, and possibly anomaly terms.
```

See [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/), [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/), and [Path-Integral Measure](/foundations/path-integral-formalism/path-integral-measure/).

## Symmetry breaking does not mean the equations lost the symmetry

In spontaneous symmetry breaking, the action and equations may still be symmetric. The chosen vacuum is not.

For a scalar potential with a circle or sphere of minima, choosing one point on the vacuum manifold hides part of the symmetry in perturbation theory around that vacuum. The broken generators move the chosen vacuum to another degenerate vacuum. The unbroken generators leave it fixed.

For ordinary global internal symmetry in relativistic QFT, broken continuous generators imply Goldstone modes under the usual assumptions. For gauge symmetry, the phrase “spontaneously broken gauge symmetry” is shorthand and must be handled carefully: gauge redundancy is not a physical symmetry, and would-be Goldstone variables become gauge-dependent ingredients of massive vector fields.

The correction is:

```txt
Wrong: The symmetry is no longer present in the theory.
Better: The theory may be symmetric while the vacuum is not invariant under the full symmetry group.
```

See [Sigma Model Preview](/foundations/foundational-models/sigma-model-preview/), [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/), and [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/).

## Antiparticles are not negative-energy particles

Reference anchor: antiparticles enter the causal-field construction and the reinterpretation of relativistic wave equations inside QFT (Srednicki 2007, §1; Weinberg 1995, Ch. 5).

A persistent trap is the sentence “negative-energy modes are antiparticles.” That sentence is close enough to be useful historically and sloppy enough to cause pain.

In the quantum field expansion, what would have looked like a negative-frequency mode in a classical wave equation is reinterpreted as a positive-energy antiparticle creation operator. For a complex scalar,

$$
\Phi(x)=\int\frac{d^3\mathbf p}{(2\pi)^3}\frac{1}{\sqrt{2E_{\mathbf p}}}
\left(a_{\mathbf p}e^{-ip\cdot x}+b^\dagger_{\mathbf p}e^{ip\cdot x}\right).
$$

The $b^\dagger_{\mathbf p}$ operator creates an antiparticle of positive energy $E_{\mathbf p}$. The antiparticle carries opposite charge, not negative energy.

See [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/) and [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/).

## Spin statistics is not a convention

Reference anchor: standard proofs and examples connect spin-statistics to locality, Lorentz invariance, positive energy, and Hilbert-space positivity (Srednicki 2007, §4; Weinberg 1995, Ch. 5; Zee 2010, II.4).

For a free scalar, one might try to use anticommutators. For a Dirac field, one might try to use commutators. Both attempts run into deep structural trouble.

The spin-statistics theorem says, under the usual relativistic QFT assumptions, integer-spin fields are quantized with commutators and half-integer-spin fields with anticommutators. The assumptions include locality or microcausality, Lorentz invariance, positive energy, and a sensible Hilbert-space structure.

The point is not merely that fermions “happen to anticommute.” Anticommutation is tied to locality and positivity for half-integer spin. Commutation is tied to locality and positivity for integer spin.

See [Bosons and Fermions](/foundations/relativistic-particles-and-fields/bosons-and-fermions/), [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/), and [Spin–Statistics](/foundations/symmetry-and-spacetime/spin-statistics/). Srednicki's early scalar-field spin-statistics discussion is especially good for seeing what goes wrong with the wrong statistics in a simple case.

## CPT is not CP, T, or “time reversal plus charge conjugation”

The CPT theorem is a structural theorem of local relativistic QFT. It says, roughly, that under standard assumptions the combined transformation CPT is a symmetry, even if C, P, T, CP, or CT are separately violated.

Do not confuse these statements:

| Statement | Meaning |
|---|---|
| C symmetry | particle-antiparticle exchange is a symmetry |
| P symmetry | spatial inversion is a symmetry |
| T symmetry | time reversal, implemented antiunitarily, is a symmetry |
| CP symmetry | the combined C and P operation is a symmetry |
| CPT theorem | local Lorentz-invariant QFT with the usual assumptions has CPT symmetry |

Time reversal is antiunitary, not just the substitution $t\to -t$ in a formula. CPT also relates particle and antiparticle properties: masses and lifetimes match for particles and antiparticles in a CPT-invariant theory.

See [Discrete Symmetries](/foundations/symmetry-and-spacetime/discrete-symmetries/) and [CPT Theorem](/foundations/symmetry-and-spacetime/cpt-theorem/).

## Locality does not mean no spacelike correlations

Vacuum correlations can be nonzero at spacelike separation. That is not a violation of locality.

The local condition is about operations and observables: measurements in spacelike-separated regions cannot signal to one another. Algebraically, this is expressed by commutators or graded commutators vanishing at spacelike separation.

So:

```txt
Wrong: Locality means ⟨0|φ(x)φ(y)|0⟩ vanishes for spacelike x−y.
Better: Locality means spacelike-separated local observables commute, while vacuum correlations may remain nonzero.
```

This is one of the biggest conceptual returns on learning the difference between Wightman functions, Feynman propagators, commutators, and retarded propagators.

See [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/) and [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/).

## Renormalization is not sweeping infinities under a rug

Reference anchor: modern renormalization organizes short-distance sensitivity into local parameters and scale dependence (Srednicki 2007, §§14–29; Coleman 2018, Ch. 25; Weinberg 1995, Ch. 12).

Loop integrals often probe arbitrarily short distances. If the theory is written as a continuum field theory, this produces UV divergences in intermediate expressions. A regulator makes the short-distance sensitivity explicit. Renormalization then organizes that sensitivity into local operators and parameters.

The modern view is sharper than “subtract infinity.” It says that a QFT is specified by a scale, a regulator or renormalization scheme, fields, symmetries, and an action containing all operators relevant at the desired accuracy. Predictivity comes from symmetry and power counting, not from pretending high-energy physics does not exist.

A better sentence is:

$$
\boxed{\text{Renormalization is how QFT separates short-distance input from long-distance prediction.}}
$$

See [UV Divergences Preview](/foundations/interactions-and-wick-expansion/uv-divergences-preview/) and [Path-Integral Measure](/foundations/path-integral-formalism/path-integral-measure/). Srednicki and Weinberg both emphasize the modern effective-field-theory perspective, while Coleman is especially clear about counterterms as part of perturbation theory.

## Effective theories are real theories

Calling a theory “effective” does not mean it is fake. It means its domain of validity is explicit.

For example, the nonlinear sigma model in four dimensions is not usually a fundamental UV-complete theory. It is still an excellent low-energy theory of Goldstone bosons. QED itself can be treated as an effective theory embedded in the Standard Model and, at still higher energies, whatever comes next.

The better question is not:

```txt
Is this theory fundamental?
```

but:

```txt
At what scale, with what degrees of freedom, and to what accuracy is this theory valid?
```

This perspective prevents two equal-and-opposite mistakes: treating every elegant Lagrangian as final truth, and dismissing useful low-energy theories because they are not final truth.

## Not every Lagrangian defines a healthy QFT

Reference anchor: unitarity, positivity, stability, locality, and gauge consistency are structural constraints beyond simply writing a local-looking formula (Weinberg 1995, Chs. 5, 7, and 12; Coleman 2018, Chs. 25 and 47).

Writing a Lorentz-invariant local expression is not enough. A candidate theory can fail because of an unstable potential, negative-norm states, gauge anomalies, nonunitarity, missing gauge fixing, bad UV behavior outside its EFT domain, wrong-sign kinetic terms, or violation of reflection positivity after Euclidean continuation.

Examples:

- A potential unbounded below does not define a stable vacuum without extra structure.
- A gauge theory with uncancelled gauge anomalies is not quantum-mechanically consistent.
- A Euclidean action with the wrong sign can fail reflection positivity.
- A higher-derivative theory may introduce ghostlike states unless interpreted carefully as an effective theory.

The safer slogan is:

$$
\boxed{\text{A Lagrangian is a proposal; the QFT is the consistent quantum structure built from it.}}
$$

See [Unitarity](/foundations/structural-principles/unitarity/), [Spectral Condition](/foundations/structural-principles/spectral-condition/), [Reflection Positivity](/foundations/structural-principles/reflection-positivity/), and [Axiomatic QFT Preview](/foundations/structural-principles/axiomatic-qft-preview/).

## The same symbol can mean several different things

The same letter often appears in several roles:

| Symbol | Possible meanings |
|---|---|
| $\phi$ | classical field, operator field, path-integral variable, background field, fluctuation field |
| $A_\mu$ | gauge potential, external source, dynamical photon field, background connection |
| $\psi$ | nonrelativistic wavefunction, Dirac field operator, Grassmann path-integral variable, spinor component |
| $J$ | source, current, angular momentum generator, Jacobian, total spin |
| $Z$ | generating functional, field-strength renormalization, partition function |
| $W$ | connected generating functional, Weyl spinor, Wilsonian action, W boson |

There is no universal cure except context. A useful habit is to ask:

```txt
Does this object act on states, label a state, get integrated over, generate correlators, or transform as a source?
```

That one question prevents a shocking number of errors.

## A compact checklist

When stuck, classify the object before manipulating it:

1. **State or operator?** A ket, field, charge, and source obey different rules.
2. **On shell or off shell?** External particles and internal propagators are not the same thing.
3. **Global or gauge?** Physical symmetry and redundancy have different observables.
4. **Wightman, Feynman, retarded, or Euclidean?** They have different support and boundary conditions.
5. **Classical, quantum, or renormalized?** The same Lagrangian symbol may hide counterterms or effective operators.
6. **Exact or perturbative?** A diagrammatic statement may depend on a chosen expansion.
7. **Which assumptions?** Theorems need locality, Lorentz invariance, unitarity, positive energy, and vacuum assumptions in different combinations.

## Relations to other pages

- [Conventions and Normalizations](/foundations/conventions-and-normalizations/) fixes the signs and normalizations that prevent many fake disagreements.
- [Why Fields?](/foundations/relativistic-particles-and-fields/why-fields/) explains why relativistic quantum mechanics pushes us toward fields.
- [States, Operators, Vacuum](/foundations/correlators-and-propagators/states-operators-vacuum/) separates the Hilbert-space ingredients used in correlators.
- [Time Ordering](/foundations/correlators-and-propagators/time-ordering/) explains time-ordered products and fermionic signs.
- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) gives the conceptual core of gauge theory.
- [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/) states the causal algebraic condition precisely.
- [Axiomatic QFT Preview](/foundations/structural-principles/axiomatic-qft-preview/) explains how these conceptual rules become theorem-level frameworks.

## Research status

The corrections on this page are **textbook-standard** within ordinary relativistic QFT. The details become more subtle in gauge theories, curved spacetime, thermal states, topological QFT, non-Lorentz-invariant systems, nonperturbative definitions, algebraic QFT, and theories without a conventional particle S matrix.

That is exactly why the distinctions matter. They are not pedantic cleanup. They are the handles that let the same formalism survive outside its simplest examples.

## Exercises

### Exercise 1: Diagnose the object

For each expression, say whether it is primarily a state, operator, correlator, Green function, source, or path-integral variable in the usual context.

1. $a^\dagger_{\mathbf p}|0\rangle$
2. $\langle0|T\phi(x)\phi(y)|0\rangle$
3. $J(x)$ in $Z[J]$
4. $\phi(x)$ inside $\int\mathcal D\phi\,e^{iS[\phi]}$
5. $Q=\int d^3\mathbf x\,j^0$

<details>
<summary><strong>Solution</strong></summary>

1. A one-particle state.
2. A time-ordered vacuum correlator; for a free field it is also the Feynman Green function up to convention.
3. A source coupled to an operator or field.
4. A path-integral integration variable.
5. A charge operator, usually the generator of a symmetry transformation.

</details>

### Exercise 2: Feynman propagation and causality

Explain why the statement

```txt
The Feynman propagator is nonzero at spacelike separation, so QFT allows faster-than-light signals.
```

is wrong.

<details>
<summary><strong>Solution</strong></summary>

The Feynman propagator is a time-ordered vacuum correlator. It is not the causal response function. Causal response is governed by the retarded propagator, which is built from the commutator:

$$
\Delta_R(x-y)=\theta(x^0-y^0)\Delta(x-y),
\qquad
\Delta(x-y)=\frac1i[\phi(x),\phi(y)].
$$

For the free scalar, $\Delta(x-y)$ vanishes outside the light cone. Thus a local perturbation cannot change spacelike-separated observables, even though vacuum correlations can be nonzero there.

</details>

### Exercise 3: Gauge or global

Classify each transformation as a global physical symmetry, a gauge redundancy, or neither as stated.

1. $\Phi(x)\mapsto e^{-iq\alpha}\Phi(x)$ with constant $\alpha$ in scalar QED.
2. $\Phi(x)\mapsto e^{-iq\alpha(x)}\Phi(x)$ and $A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x)$.
3. $A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x)$ without transforming a charged matter field in an interacting theory.

<details>
<summary><strong>Solution</strong></summary>

1. A global physical symmetry, generated by the conserved charge.
2. A gauge redundancy; it relates different descriptions of the same physical configuration.
3. Not a symmetry of the full interacting description as stated, because the charged matter coupling is not transformed consistently.

</details>

### Exercise 4: Normal ordering versus counterterms

Why does normal ordering remove the free-field vacuum energy but not replace renormalization in an interacting scalar theory?

<details>
<summary><strong>Solution</strong></summary>

Normal ordering subtracts contractions defined with respect to a chosen free vacuum and creation-annihilation split. It can remove terms such as the free zero-point energy or a chosen tadpole contraction. Interacting loop diagrams generate short-distance dependence in masses, couplings, field normalizations, and composite operators. Those require counterterms and renormalization conditions. Normal ordering is therefore one useful subtraction convention, not the full renormalization program.

</details>

### Exercise 5: Antiparticles and energy

In the complex scalar expansion

$$
\Phi(x)=\int\frac{d^3\mathbf p}{(2\pi)^3}\frac{1}{\sqrt{2E_{\mathbf p}}}
\left(a_{\mathbf p}e^{-ip\cdot x}+b^\dagger_{\mathbf p}e^{ip\cdot x}\right),
$$

which operator creates the antiparticle, and what is its energy?

<details>
<summary><strong>Solution</strong></summary>

The operator $b^\dagger_{\mathbf p}$ creates the antiparticle. Its energy is positive, $E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}$. The negative-frequency exponential is reinterpreted in the quantum field expansion as an antiparticle creation term, not as a negative-energy particle state.

</details>

### Exercise 6: Ward identity contact terms

Why can a conserved current have a nonzero divergence inside a time-ordered correlator?

<details>
<summary><strong>Solution</strong></summary>

Because the derivative acts not only on the current but also on the time-ordering step functions. Differentiating those step functions produces delta-function contact terms at coincident times. These contact terms encode the symmetry transformation of the inserted operators. If the symmetry is explicitly broken or anomalous, additional terms can appear.

</details>

## Sources and further reading

- Mark Srednicki, *Quantum Field Theory*, §§1–5, 8–13, 22–24, 54–61, and 67–77, for the transition from relativistic wave mechanics to fields, scalar quantization, LSZ, path integrals, spectral representation, symmetries, discrete transformations, gauge fields, Ward identities, and anomalies.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 1–8, 13–15, 27–33, and 43–47, for particles versus fields, Fock space, scalar causality, symmetries, Wick expansion, Green functions, gauge redundancy, Faddeev–Popov gauge fixing, Ward identities, spontaneous symmetry breaking, and gauge-field quantization.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 2–10, for the particle-state foundation of QFT, cluster decomposition, causal fields, Feynman rules, canonical formalism, electrodynamics, path integrals, Källén–Lehmann representation, and dispersion relations.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chs. 15–22, for non-Abelian gauge theory, BRST symmetry, effective action, renormalization group, spontaneous symmetry breaking, effective field theory, and anomalies.
- Anthony Zee, *Quantum Field Theory in a Nutshell*, Parts I–IV, for conceptual explanations of path integrals, fields as oscillators, propagators, gauge invariance, renormalization, spin-statistics, and symmetry breaking.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*, chs. 2–7, 9–12, and 15–16, for a standard perturbative treatment of fields, Feynman rules, QED, renormalization, gauge theory, and Ward identities.

## Version history

- **2026-05-24:** Initial qft.org common-confusions page: fields versus wavefunctions, particles, virtual particles, propagators, causality, time ordering, $i\epsilon$, normal ordering, canonical/path-integral language, measures, Euclidean continuation, gauge redundancy, ghosts, Ward identities, symmetry breaking, antiparticles, spin-statistics, CPT, renormalization, EFT, and consistency caveats.
