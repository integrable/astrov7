---
title: "Unitarity"
description: "Probability conservation, positive-norm physical states, S-matrix unitarity, the optical theorem, cutting rules, partial-wave bounds, and gauge-theory caveats."
sidebar:
  label: "Unitarity"
  order: 2
---

## Summary

**Unitarity** is the quantum statement that probabilities add up to one. In ordinary quantum mechanics it is expressed by unitary time evolution,

$$
U(t)^\dagger U(t)=1,
$$

or, when $U(t)=e^{-iHt}$, by a self-adjoint Hamiltonian $H$.

In scattering theory the same principle becomes **S-matrix unitarity**,

$$
\boxed{S^\dagger S=1.}
$$

This single equation has many faces. It says that probability is conserved, that total cross sections are positive, that the imaginary part of a forward scattering amplitude is fixed by physical intermediate states, and that loop amplitudes know about lower-order on-shell processes. In the convention

$$
S=1+iT,
$$

S-matrix unitarity gives

$$
\boxed{-i(T-T^\dagger)=T^\dagger T.}
$$

Taking the forward matrix element and inserting a complete set of physical final states gives the schematic identity

$$
\boxed{2\operatorname{Im}T_{ii}=\sum_n |T_{ni}|^2\ge 0.}
$$

That is the algebraic heart of the optical theorem: the imaginary part of a forward scattering amplitude measures the total probability for all possible final states. Coleman derives the relativistic optical theorem directly from $S^\dagger S=1$ and relates the imaginary part of the forward invariant amplitude to the total cross section times the appropriate flux factor (Coleman 2019, ch. 12). Weinberg treats this as one of the basic implications of S-matrix unitarity, alongside total rates, partial waves, and diffraction behavior (Weinberg 1995, Vol. I, §§3.2 and 3.6). Zee emphasizes the same identity in the language of cutting rules: unitarity turns imaginary parts of amplitudes into sums over on-shell intermediate states (Zee 2010, ch. III.8).

<figure class="doc-figure" style="--figure-width: 55rem;">

![Unitarity, the S matrix, and the optical theorem](/figures/foundations/unitarity-optical-theorem-map.svg)

<figcaption>

Unitarity begins with positive-norm states and self-adjoint dynamics, becomes $S^\dagger S=1$ in scattering theory, and yields the optical theorem after writing $S=1+iT$ and inserting a complete set of physical intermediate states.

</figcaption>
</figure>

## Prerequisites

You should know [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/), [Multiparticle States](/foundations/relativistic-particles-and-fields/multiparticle-states/), [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/), [Interaction Picture](/foundations/interactions-and-wick-expansion/interaction-picture/), [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/), [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/), [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/), [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/), [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/), [BRST Preview](/foundations/gauge-fields-first-principles/brst-preview/), and [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/).

:::note[Conventions]
We use qft.org's mostly-minus metric and relativistic normalization. For a one-particle state,

$$
\langle p'|p\rangle=(2\pi)^3 2E_{\mathbf p}\,\delta^{(3)}(\mathbf p-\mathbf p').
$$

For scattering amplitudes, we use

$$
\langle f|T|i\rangle
=(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

Thus

$$
S_{fi}=\delta_{fi}+i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi},
$$

where $\delta_{fi}$ denotes the identity contribution in the continuum-normalized basis. Different books absorb signs, factors of $i$, and normalization constants differently. The optical theorem is invariant; the prefactors are conventional.
:::

:::note[Assumptions]
The clean scattering statement assumes a Hilbert space with positive norm, a stable vacuum, well-defined asymptotic particle states, and a unitary map between in-states and out-states. In gauge-fixed theories, the intermediate state space may contain negative-norm or ghost states; physical unitarity is then a statement about the gauge-invariant or BRST cohomology sector, not about every state in the enlarged bookkeeping space.
:::

## Three meanings of unitarity

The same word appears in several related places.

| Setting | Statement | Meaning |
|---|---|---|
| Hilbert space | $\langle\psi|\psi\rangle\ge0$ | probabilities are nonnegative |
| Time evolution | $U(t)^\dagger U(t)=1$ | total probability is conserved |
| Scattering | $S^\dagger S=1$ | all final-state probabilities sum to one |
| Perturbation theory | $-i(T-T^\dagger)=T^\dagger T$ | imaginary parts are fixed by lower-order processes |
| Gauge theory | $S^\dagger S=1$ on physical states | unphysical gauge modes and ghosts decouple |

These are not independent ideas. A healthy Lorentzian QFT should have a positive physical Hilbert space and unitary time evolution. If it also has well-defined scattering states, then the scattering operator is unitary. Conversely, scattering unitarity is one of the sharpest ways to test whether a proposed interaction is compatible with quantum mechanics.

## Time evolution and Hermiticity

In ordinary quantum mechanics,

$$
i\frac{d}{dt}|\psi(t)\rangle=H|\psi(t)\rangle.
$$

Then

$$
\frac{d}{dt}\langle\psi(t)|\psi(t)\rangle
=i\langle\psi(t)|H^\dagger|\psi(t)\rangle
-i\langle\psi(t)|H|\psi(t)\rangle.
$$

If $H=H^\dagger$, the norm is time-independent.

In QFT this simple calculation hides real mathematical work. The Hamiltonian may be an unbounded operator, fields are distributions, and renormalization can change the relation between a formal Lagrangian and a well-defined operator. The physical requirement is not just a Hermitian-looking density on paper; it is a self-adjoint generator of time evolution on the physical Hilbert space.

For time-dependent interactions, the interaction-picture evolution operator is

$$
U_I(t_2,t_1)=T\exp\left[-i\int_{t_1}^{t_2}dt\,H_I(t)\right].
$$

If $H_I(t)$ is Hermitian, then

$$
U_I(t_2,t_1)^\dagger
=\overline T\exp\left[+i\int_{t_1}^{t_2}dt\,H_I(t)\right],
$$

where $\overline T$ denotes anti-time ordering. This anti-time-ordered adjoint is what makes the perturbative proof of unitarity work order by order.

## S-matrix unitarity

The S matrix compares asymptotic states. An incoming state looks free in the far past, evolves through the interaction region, and looks like a superposition of outgoing free states in the far future. The S matrix is the map between those free labels:

$$
\langle f|S|i\rangle
={}_{\rm out}\!\langle f|i\rangle_{\rm in}.
$$

If the in-states and out-states are complete orthonormal bases for the same physical Hilbert space, then

$$
\boxed{S^\dagger S=1.}
$$

For any incoming state $|i\rangle$,

$$
1=\langle i|S^\dagger S|i\rangle
=\sum_f |\langle f|S|i\rangle|^2.
$$

This is the scattering version of probability conservation.

The word **complete** is doing real work. If we include only elastic two-particle channels while the theory also allows particle production, decays, bound states, or soft radiation, the elastic submatrix is not unitary by itself. It is a sub-block of a larger unitary matrix. What looks like probability loss in the elastic sector is really probability flow into other channels.

## The algebraic identity behind the optical theorem

Write

$$
S=1+iT.
$$

Insert this into $S^\dagger S=1$:

$$
(1-iT^\dagger)(1+iT)=1.
$$

Expanding gives

$$
iT-iT^\dagger+T^\dagger T=0,
$$

or

$$
\boxed{-i(T-T^\dagger)=T^\dagger T.}
$$

Taking matrix elements gives

$$
-i(T_{fi}-T_{if}^*)
=\sum_n T_{nf}^*T_{ni}.
$$

For $f=i$,

$$
\boxed{2\operatorname{Im}T_{ii}=\sum_n |T_{ni}|^2.}
$$

This is already the optical theorem in abstract Hilbert-space form. The right-hand side is a nonnegative sum over all possible final states.

## Phase space and total cross sections

In relativistic scattering, the sum over intermediate states becomes an invariant phase-space integral. With the convention

$$
\langle f|T|i\rangle
=(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi},
$$

and an intermediate state $X$ with momenta $q_a$, the phase-space measure is

$$
d\Pi_X(P)
=\frac{1}{S_X}\prod_{a\in X}
\frac{d^3q_a}{(2\pi)^3 2E_a}
(2\pi)^4\delta^{(4)}\left(P-\sum_{a\in X}q_a\right),
$$

where $S_X$ is the identical-particle symmetry factor. The forward unitarity condition becomes

$$
\boxed{
2\operatorname{Im}\mathcal M_{i\to i}
=\sum_X\int d\Pi_X(P_i)\,|\mathcal M_{i\to X}|^2.
}
$$

For a two-particle initial state, the total cross section is

$$
\sigma_{\rm tot}
=\frac{1}{4E_1E_2v_{\rm rel}}
\sum_X\int d\Pi_X(P_i)\,|\mathcal M_{i\to X}|^2.
$$

Therefore

$$
\boxed{
\sigma_{\rm tot}
=\frac{1}{4E_1E_2v_{\rm rel}}\,2\operatorname{Im}\mathcal M_{i\to i}.
}
$$

In the center-of-momentum frame, this is commonly rewritten as a relation between $\operatorname{Im}\mathcal M(s,t=0)$ and $\sigma_{\rm tot}$. The precise prefactor depends on amplitude normalization and spin averaging. The invariant statement is the phase-space formula above.

The physical content is simple: **the total probability for anything to happen is measured by the forward scattering amplitude**.

## Perturbative unitarity and cuts

In perturbation theory,

$$
\mathcal M=\mathcal M^{(1)}+\mathcal M^{(2)}+\cdots,
$$

where $\mathcal M^{(1)}$ might be a tree amplitude and $\mathcal M^{(2)}$ a one-loop amplitude. Since the unitarity relation is nonlinear, it relates different orders. Schematically,

$$
2\operatorname{Im}\mathcal M_{i\to i}^{(2)}
=\sum_X\int d\Pi_X\,|\mathcal M_{i\to X}^{(1)}|^2.
$$

This is the conceptual content behind Cutkosky cutting rules and modern unitarity methods. Internal propagators of the form

$$
\frac{i}{p^2-m^2+i\epsilon}
$$

can produce an imaginary part when the internal momentum can go on shell. Cutting a line replaces the propagator by an on-shell delta function, schematically

$$
\frac{i}{p^2-m^2+i\epsilon}
\quad\leadsto\quad
2\pi\,\theta(p^0)\delta(p^2-m^2),
$$

with the cut lines integrated over physical phase space. The details belong in Perturbative QFT and Scattering, but the foundational point belongs here: **the imaginary part is probability flowing through physical on-shell channels**.

## Partial-wave unitarity

For two-particle scattering, unitarity can be sharpened by decomposing into angular momentum channels. In a single elastic channel, write

$$
S_\ell=e^{2i\delta_\ell}.
$$

If

$$
S_\ell=1+2ia_\ell,
$$

then elastic unitarity gives

$$
\boxed{\operatorname{Im}a_\ell=|a_\ell|^2.}
$$

Equivalently,

$$
\left|a_\ell-\frac{i}{2}\right|=\frac12.
$$

So each elastic partial wave lies on the **unitarity circle** in the complex $a_\ell$ plane. If inelastic channels are open, the elastic partial wave lies inside the circle, and

$$
\operatorname{Im}a_\ell\ge |a_\ell|^2.
$$

This is the origin of many perturbative unitarity bounds. A tree-level amplitude that grows too quickly with energy cannot remain a small perturbation indefinitely. Something must happen: additional diagrams become important, new degrees of freedom enter, a resonance appears, a symmetry cancels the growth, or the effective theory leaves its domain of validity.

:::caution[Do not overread tree-level bounds]
A tree-level unitarity bound is not automatically a theorem that a theory is inconsistent. It is usually a warning that perturbation theory has left its comfort zone. In an effective field theory, that may simply mean the cutoff has been reached.
:::

## Unitarity is not manifest in every formalism

The operator formalism makes unitarity natural: a self-adjoint Hamiltonian generates unitary time evolution. But Lorentz invariance may be less manifest.

The Lorentzian path integral makes covariance and diagrammatics efficient, but unitarity is less visible term by term. It reappears through the $i\epsilon$ prescription, cutting rules, largest-time equations, and the operator interpretation of the path integral. Weinberg stresses this useful division of labor: path integrals are excellent for deriving covariant Feynman rules, while the canonical formalism keeps the quantum-mechanical origin of the construction clearer (Weinberg 1995, Vol. I, ch. 9).

Euclidean path integrals are even subtler. The Euclidean weight $e^{-S_E}$ is not a unitary time-evolution operator. A Euclidean theory reconstructs a unitary Lorentzian theory only if it satisfies the appropriate positivity condition, usually called reflection positivity. That is why reflection positivity is a structural principle, not a decorative theorem.

## Gauge theories and physical unitarity

Gauge theories add a beautiful nuisance. Covariant gauge fixing introduces unphysical polarizations, and non-Abelian gauge fixing introduces ghosts. The gauge-fixed Fock space is not the physical Hilbert space.

The unitarity statement is therefore not

$$
S^\dagger S=1
$$

on the naive gauge-fixed state space. The physical statement is unitarity on the physical Hilbert space. In modern covariant language, that means BRST cohomology:

$$
\mathcal H_{\rm phys}
=\frac{\ker Q_{\rm BRST}}{\operatorname{im}Q_{\rm BRST}}.
$$

Physical states are BRST-closed, and BRST-exact states are null or gauge-redundant. Ghosts and longitudinal polarizations are allowed internally because they enforce gauge consistency, but they are not external physical particles. Their job is partly to make the cancellation of unphysical degrees of freedom work in perturbation theory. Srednicki and Weinberg both use BRST symmetry to organize these cancellations in non-Abelian gauge theory (Srednicki 2007, §74; Weinberg 1996, Vol. II, §§15.7–15.8).

This is why gauge theory unitarity is often harder to see than scalar theory unitarity. It is not because gauge theories are less unitary. It is because a redundant description has extra states that must cancel before the physical answer emerges.

## Locality and unitarity together

Locality and unitarity are independent-looking requirements, but QFT needs them together.

Locality says spacelike separated observables commute. Unitarity says time evolution preserves probability. Together they imply strong analytic and causal constraints on amplitudes and correlators. The optical theorem, spectral representations, dispersion relations, and many positivity bounds are descendants of this pairing.

The slogan is useful:

$$
\boxed{
\text{locality controls where influence can go; unitarity controls how probability flows.}
}
$$

This page focuses on probability flow. The next structural pages add positive energy, clustering of distant experiments, Euclidean reflection positivity, and analyticity.

## Common pitfalls

**Pitfall 1: “Unitarity means every amplitude has absolute value at most one.”** Not in that raw form. Continuum-normalized amplitudes include delta functions and phase-space conventions. Bounds are cleanest for probabilities, S-matrix eigenvalues, or properly normalized partial waves.

**Pitfall 2: “The elastic channel must be unitary by itself.”** Only if no other channels are open. Once particle production or absorption into other states is possible, the elastic submatrix is not unitary alone.

**Pitfall 3: “A complex amplitude violates unitarity.”** Quite the opposite. Imaginary parts are required by unitarity when real intermediate states can go on shell.

**Pitfall 4: “Ghosts violate unitarity because they have the wrong statistics.”** Ghosts are not physical external states. In a consistent gauge theory, BRST symmetry ensures that unphysical polarizations and ghosts cancel from physical probabilities.

**Pitfall 5: “Euclidean convergence is the same as Lorentzian unitarity.”** No. A convergent Euclidean integral is not automatically a unitary Lorentzian QFT. Reflection positivity is the bridge.

**Pitfall 6: “A non-Hermitian effective Hamiltonian proves the fundamental theory is nonunitary.”** Usually it proves that a subsystem has been isolated from its environment. Open-system descriptions can be nonunitary even when the combined system is unitary.

## Takeaway equations

The formulas to remember are:

$$
U^\dagger U=1,
$$

$$
S^\dagger S=1,
$$

$$
S=1+iT,
\qquad
\boxed{-i(T-T^\dagger)=T^\dagger T,}
$$

$$
\boxed{
2\operatorname{Im}\mathcal M_{i\to i}
=
\sum_X\int d\Pi_X\,|\mathcal M_{i\to X}|^2,
}
$$

and, in one elastic partial wave,

$$
\boxed{\operatorname{Im}a_\ell=|a_\ell|^2.}
$$

## Relations to other pages

- [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/) explains the causal algebraic condition that complements unitarity.
- The later Spectral Condition page will explain positive energy and vacuum stability.
- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) already shows how positivity of Hilbert-space norms enters two-point functions.
- [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/) explains how correlators become on-shell amplitudes.
- [BRST Preview](/foundations/gauge-fields-first-principles/brst-preview/) explains why gauge-fixed unitarity must be stated on the BRST physical Hilbert space.
- Later scattering pages will develop cross sections, cutting rules, partial waves, and the optical theorem in calculational detail.

## Research status

Unitarity is a **structural axiom** of ordinary quantum theory and of relativistic QFT. Its consequences for the S matrix, optical theorem, and partial waves are textbook-standard.

Active research often asks how unitarity is realized or constrained in special settings: gauge theories with redundant variables, effective field theories with finite cutoffs, theories without a conventional S matrix, curved spacetime, thermal systems, nonperturbative QFT, holography, and bootstrap programs. The principle remains stable; the correct formulation depends on the setting.

## Exercises

### Exercise 1: Norm conservation

Let $|\psi(t)\rangle$ obey

$$
i\frac{d}{dt}|\psi(t)\rangle=H|\psi(t)\rangle.
$$

Show that $\langle\psi(t)|\psi(t)\rangle$ is time-independent if $H=H^\dagger$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{d}{dt}\langle\psi|\psi\rangle
=\langle\dot\psi|\psi\rangle+\langle\psi|\dot\psi\rangle.
$$

From the Schrödinger equation,

$$
|\dot\psi\rangle=-iH|\psi\rangle,
\qquad
\langle\dot\psi|=i\langle\psi|H^\dagger.
$$

Therefore

$$
\frac{d}{dt}\langle\psi|\psi\rangle
=i\langle\psi|(H^\dagger-H)|\psi\rangle.
$$

If $H=H^\dagger$, this vanishes.

</details>

### Exercise 2: The basic S-matrix identity

Starting from $S=1+iT$ and $S^\dagger S=1$, derive

$$
-i(T-T^\dagger)=T^\dagger T.
$$

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
S^\dagger S
=(1-iT^\dagger)(1+iT)
=1+iT-iT^\dagger+T^\dagger T.
$$

Setting this equal to $1$ gives

$$
iT-iT^\dagger+T^\dagger T=0,
$$

or

$$
-i(T-T^\dagger)=T^\dagger T.
$$

</details>

### Exercise 3: Abstract optical theorem

Take the $i\to i$ matrix element of

$$
-i(T-T^\dagger)=T^\dagger T
$$

and insert a complete set of states. Show that

$$
2\operatorname{Im}T_{ii}=\sum_n|T_{ni}|^2.
$$

<details>
<summary><strong>Solution</strong></summary>

The left-hand side is

$$
-i\langle i|(T-T^\dagger)|i\rangle
=-i(T_{ii}-T_{ii}^*)
=2\operatorname{Im}T_{ii}.
$$

The right-hand side is

$$
\langle i|T^\dagger T|i\rangle
=\sum_n \langle i|T^\dagger|n\rangle\langle n|T|i\rangle
=\sum_n T_{ni}^*T_{ni}
=\sum_n|T_{ni}|^2.
$$

</details>

### Exercise 4: Elastic partial-wave circle

Suppose a single elastic partial wave obeys

$$
S_\ell=1+2ia_\ell,
\qquad
|S_\ell|=1.
$$

Show that

$$
\operatorname{Im}a_\ell=|a_\ell|^2
$$

and that $a_\ell$ lies on a circle in the complex plane.

<details>
<summary><strong>Solution</strong></summary>

Write

$$
1=|1+2ia_\ell|^2
=(1+2ia_\ell)(1-2ia_\ell^*)
=1+2i(a_\ell-a_\ell^*)+4|a_\ell|^2.
$$

Since

$$
a_\ell-a_\ell^*=2i\operatorname{Im}a_\ell,
$$

we get

$$
0=-4\operatorname{Im}a_\ell+4|a_\ell|^2,
$$

so

$$
\operatorname{Im}a_\ell=|a_\ell|^2.
$$

Writing $a_\ell=x+iy$, this becomes

$$
y=x^2+y^2,
$$

or

$$
x^2+\left(y-\frac12\right)^2=\frac14.
$$

That is a circle of radius $1/2$ centered at $i/2$.

</details>

### Exercise 5: One-loop imaginary part from tree amplitudes

Let a theory have an expansion

$$
\mathcal M=\lambda\mathcal M^{(1)}+\lambda^2\mathcal M^{(2)}+O(\lambda^3).
$$

Assume the tree-level amplitude $\mathcal M^{(1)}$ is real. Use the optical theorem to determine the order-$\lambda^2$ imaginary part of the forward amplitude.

<details>
<summary><strong>Solution</strong></summary>

The optical theorem says

$$
2\operatorname{Im}\mathcal M_{i\to i}
=\sum_X\int d\Pi_X\,|\mathcal M_{i\to X}|^2.
$$

Substitute the expansion. The left-hand side through order $\lambda^2$ is

$$
2\lambda^2\operatorname{Im}\mathcal M^{(2)}_{i\to i},
$$

because $\mathcal M^{(1)}$ is real. The right-hand side through order $\lambda^2$ is

$$
\lambda^2\sum_X\int d\Pi_X\,|\mathcal M^{(1)}_{i\to X}|^2.
$$

Therefore

$$
\boxed{
2\operatorname{Im}\mathcal M^{(2)}_{i\to i}
=\sum_X\int d\Pi_X\,|\mathcal M^{(1)}_{i\to X}|^2.
}
$$

This is the simplest perturbative version of a cutting rule.

</details>

### Exercise 6: Why an elastic submatrix need not be unitary

A theory has a two-particle elastic channel $|e\rangle$ and an inelastic channel $|x\rangle$. Suppose the full S matrix is unitary on the two-dimensional space spanned by these channels. Explain why the number $S_{ee}$ alone need not have unit modulus.

<details>
<summary><strong>Solution</strong></summary>

Unitary means each column has norm one. For the column corresponding to incoming $|e\rangle$,

$$
|S_{ee}|^2+|S_{xe}|^2=1.
$$

If the inelastic transition amplitude $S_{xe}$ is nonzero, then

$$
|S_{ee}|^2=1-|S_{xe}|^2<1.
$$

So the elastic channel alone loses probability, but the full system does not. The missing probability went into the inelastic channel.

</details>

## Sources and further reading

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 12, for a direct derivation of the optical theorem from $S^\dagger S=1$ and its relation to relativistic cross sections.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§3.2, 3.6, and 3.7, for S-matrix unitarity, the optical theorem, rates, partial waves, and consequences of unitarity.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. III.8, for the connection between unitarity, imaginary parts, and Cutkosky cutting rules.
- M. Srednicki, *Quantum Field Theory*, §§5, 10, 13, and 25, for LSZ, scattering amplitudes, the Lehmann–Källén representation, and unstable particles.
- M. E. Peskin and D. V. Schroeder, *An Introduction to Quantum Field Theory*, §§4.5 and 7.3, for the optical theorem, unitarity cuts, and perturbative checks.
- C. Itzykson and J.-B. Zuber, *Quantum Field Theory*, chs. 3 and 6, for a more formal treatment of the S matrix and unitarity.
- R. J. Eden, P. V. Landshoff, D. I. Olive, and J. C. Polkinghorne, *The Analytic S-Matrix*, for the classic analytic-S-matrix treatment of unitarity, causality, and analyticity.

## Version history

- **2026-05-23:** Initial qft.org page on Hilbert-space unitarity, S-matrix unitarity, the T-matrix identity, optical theorem, partial-wave unitarity, path-integral and Euclidean viewpoints, gauge-theory caveats, and exercises.
