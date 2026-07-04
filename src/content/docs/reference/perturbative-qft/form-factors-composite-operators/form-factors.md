---
title: "Form Factors"
description: "How local operator matrix elements are extracted from correlators with insertions, how they encode momentum-transfer dependence, and how renormalization and infrared physics enter."
sidebar:
  label: "Form Factors"
  order: 2
level: Graduate
status: "Polished draft"
source: "Weinberg, Vol. I scattering theory and Vol. II operator methods; Srednicki, LSZ, spectral representation, and scattering chapters; Schwartz, unitarity, form-factor examples, and QCD chapters; standard current-form-factor and amplitudes literature."
topics:
  - form factors
  - matrix elements
  - composite operators
  - LSZ reduction
  - current matrix elements
canonicalTopics:
  - form-factors
  - operator-matrix-elements
  - current-form-factors
  - lsz-with-operator-insertions
researchStatus:
  established:
    - "Form factors as matrix elements of local operators are standard observables in QFT, particle physics, hadron physics, and amplitude theory."
  active:
    - "High-loop form factors, infrared factorization, operator mixing, nonperturbative hadronic form factors, and conformal or celestial representations remain active research areas."
---

## Summary

A **form factor** is a matrix element of a local operator between physical states. For a local renormalized operator $\mathcal O_R(0)$, the basic object is

$$
F_{f\leftarrow i}^{\mathcal O}
=
\langle f,{\rm out}|\mathcal O_R(0)|i,{\rm in}\rangle.
$$

Unlike an ordinary scattering amplitude, a form factor contains a distinguished local insertion. That insertion can carry momentum, charge, spin, flavor, color-singlet quantum numbers, or stress-tensor quantum numbers. It is the QFT version of probing a system with a local current or density.

For a one-particle scalar current matrix element, Lorentz invariance gives the familiar structure

$$
\langle p'|J^\mu(0)|p\rangle
=
(p'+p)^\mu F(q^2),
\qquad
q=p'-p,
$$

for equal-mass scalar states and a conserved vector current. The function $F(q^2)$ is the form factor. Its dependence on $q^2$ encodes how the state responds to a probe of invariant momentum transfer $q^2$.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 54rem;">

![A form factor as a local operator matrix element and as an LSZ-amputated correlator with one insertion](/figures/perturbative-qft/form-factors.svg)

<figcaption>

A form factor is a local operator matrix element. Perturbatively, compute a Green function with one composite-operator insertion, then amputate and put the external particle legs on shell. The operator insertion itself is not amputated unless it is promoted to a dynamical external field.

</figcaption>
</figure>

Form factors sit between correlation functions and scattering amplitudes. They use the same operator insertions as composite-operator Green functions, and the same external-state reduction as scattering theory. They are therefore a natural bridge between perturbative diagrams, symmetry currents, hadronic structure, EFT matching, and modern amplitude methods.

## Prerequisites

You should know [Composite Operator Insertions](/perturbative-qft/form-factors-composite-operators/composite-operator-insertions/), [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/), [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/), [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/), [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/), and [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/).

## Core idea

An S-matrix element asks how asymptotic particles scatter into other asymptotic particles. A form factor asks how a local operator couples to those particles.

That difference is small in notation and large in meaning. The local operator may be a conserved current, a stress tensor, a scalar density, a weak-interaction operator, an EFT operator, or a gauge-invariant composite operator such as $\operatorname{tr}F^2$. Its matrix element measures the internal response of the state to that probe.

Common examples include:

| Operator | Typical form factor question |
|---|---|
| electromagnetic current $J^\mu$ | What charge and magnetic structure does a particle or hadron have? |
| axial current $J_5^\mu$ | How does chiral symmetry act on hadronic states? |
| stress tensor $T^{\mu\nu}$ | How are energy, momentum, pressure, and angular momentum distributed? |
| scalar density $\overline\psi\psi$ or $\phi^2$ | How does the state respond to a mass deformation? |
| EFT operator $\mathcal O_i$ | What Wilson coefficient multiplies this physical matrix element? |
| color-singlet operator $\operatorname{tr}F^2$ | How does a local gauge-invariant source create gluonic states? |

A form factor can be perturbative or nonperturbative, depending on the states and the momentum scale. The definition is general; the calculational method is context dependent.

## Setup and conventions

Let $|i,{\rm in}\rangle$ and $|f,{\rm out}\rangle$ be asymptotic states with total momenta $P_i$ and $P_f$. Translation invariance gives

$$
\langle f|\mathcal O_R(x)|i\rangle
=
e^{i(P_f-P_i)\cdot x}
\langle f|\mathcal O_R(0)|i\rangle.
$$

The physical momentum transfer is

$$
q=P_f-P_i.
$$

Fourier-transform conventions determine whether the delta function is written as $\delta^{(4)}(q-P_f+P_i)$ or with the opposite sign. The invariant content is the reduced matrix element at $x=0$.

For vacuum-to-particle form factors, one often writes

$$
F_n^{\mathcal O}(1,\ldots,n)
=
\langle p_1,\ldots,p_n;{\rm out}|\mathcal O_R(0)|0\rangle,
\qquad
q=\sum_{a=1}^n p_a.
$$

This notation is common in amplitudes and in studies of local operator insertions. The operator carries the total momentum of the final state.

## LSZ extraction

Start from a time-ordered Green function with one operator insertion,

$$
G_{\mathcal O,n}(x;x_1,\ldots,x_n)
=
\langle0|T\{\mathcal O_R(x)\phi(x_1)\cdots\phi(x_n)\}|0\rangle.
$$

Fourier transform the elementary-field points and isolate the poles associated with the external particles. Near the scalar one-particle poles,

$$
\widetilde G_{\mathcal O,n}(p_1,\ldots,p_n)
\sim
\left[\prod_{a=1}^n
\frac{iZ^{1/2}}{p_a^2-m^2+i\epsilon}
\right]
F_n^{\mathcal O}(p_1,\ldots,p_n)
+
\text{less singular terms}.
$$

Thus the reduced form factor is extracted by removing the external propagator poles and field-state residues:

$$
F_n^{\mathcal O}(p_1,\ldots,p_n)
=
\lim_{p_a^2\to m^2}
\left[\prod_{a=1}^n\frac{p_a^2-m^2}{iZ^{1/2}}\right]
\widetilde G_{\mathcal O,n}(p_1,\ldots,p_n),
$$

with the usual incoming/outgoing phase conventions understood. If one instead first amputates with inverse full propagators $G_2^{-1}$, then the amputated insertion differs from the form factor by the inverse residue factors; equivalently $F_n^{\mathcal O}=Z^{n/2}G_{\mathcal O,n}^{\rm amp}$ at the pole.

This is the form-factor version of LSZ. The elementary external legs are amputated. The operator insertion is not amputated: it is the local probe whose matrix element is being measured.

For spinor and vector particles, the same logic applies with the appropriate external spinors, polarization vectors, residues, and physical-state sums.

## Vacuum-to-particle form factors

The simplest vacuum-to-particle form factor in a free scalar theory is

$$
\langle p|\phi(0)|0\rangle=1
$$

with the site-wide state normalization. The next simplest is

$$
\left\langle p_1,p_2\middle|\frac12\phi(0)^2\middle|0\right\rangle=1
$$

for the connected two-particle matrix element.

These examples explain why the insertion rule for $\phi^2/2$ is $1$. The operator creates two scalar quanta at the same point. Perturbative interactions then correct this minimal form factor through loops, counterterms, and operator renormalization.

In modern amplitude language, vacuum-to-multiparticle form factors are often used for gauge-invariant local operators. For example, one studies objects of the schematic form

$$
\langle 1,2,\ldots,n|\operatorname{tr}F^2(0)|0\rangle
$$

or their supersymmetric analogues. These look like amplitudes with a color-singlet local source inserted. They retain many on-shell simplifications while probing operator structure.

## Current form factors

For a conserved vector current between equal-mass scalar states,

$$
\langle p'|J^\mu(0)|p\rangle
=
(p'+p)^\mu F(q^2),
\qquad
q=p'-p.
$$

Current conservation is automatic on shell:

$$
q_\mu(p'+p)^\mu
=
p'^2-p^2
=
0.
$$

If the current is normalized as the charge current, then

$$
F(0)=Q,
$$

where $Q$ is the charge of the state in the units used for the current.

For a spin-one-half particle, Lorentz invariance, parity, and current conservation allow the standard Dirac and Pauli decomposition

$$
\langle p',s'|J^\mu(0)|p,s\rangle
=
\overline u(p',s')
\left[
\gamma^\mu F_1(q^2)
+
\frac{i\sigma^{\mu\nu}q_\nu}{2m}F_2(q^2)
\right]
u(p,s).
$$

Here $F_1$ is the Dirac form factor and $F_2$ is the Pauli form factor. In QED, $F_2(0)$ is related to the anomalous magnetic moment. In hadron physics, analogous decompositions define electromagnetic and weak form factors of composite states.

## Scalar and stress-tensor form factors

A scalar operator has fewer Lorentz indices but can carry important physical information. For a scalar state,

$$
\langle p'|\mathcal O_S(0)|p\rangle
=
F_S(q^2)
$$

if no other tensor structures are available. If $\mathcal O_S$ is a mass derivative of the Lagrangian, then its form factor measures the response of the state to a change in a mass parameter.

The stress tensor has a richer decomposition because it carries two Lorentz indices. Between scalar states one can write a basis built from $p+p'$, $q$, and the metric, constrained by symmetry and conservation. Between spin-one-half states, additional spin structures appear. The detailed basis belongs on a dedicated stress-tensor form-factor page, but the logic is the same: local operator, external states, Lorentz decomposition, symmetry constraints, scalar functions of invariants.

## Analytic structure and unitarity

Form factors are functions of Lorentz invariants such as $q^2$. They generally have poles and branch cuts. Poles correspond to one-particle states that can be created by the operator. Branch cuts begin at multiparticle thresholds.

For a scalar form factor depending on $s=q^2$, the discontinuity across a cut is controlled by unitarity. Schematically,

$$
\operatorname{Disc} F_{f\leftarrow i}^{\mathcal O}
\sim
\sum_X
\int d\Pi_X\,
\mathcal M_{f\leftarrow X}^{*}
F_{X\leftarrow i}^{\mathcal O},
$$

where the sum runs over intermediate on-shell states $X$ allowed by quantum numbers. This is the form-factor analogue of the optical theorem and Cutkosky rules: discontinuities are built from on-shell lower-complexity objects.

This analytic viewpoint is crucial in hadron physics, dispersion relations, and bootstrap-inspired approaches. A form factor is not just a perturbative series; it is an analytic function with physical singularities.

## Renormalization of form factors

Because the local operator is composite, form factors inherit operator renormalization:

$$
\mathcal O_i^B=Z_{ij}\mathcal O_j^R.
$$

A renormalized form factor is a matrix element of $\mathcal O_i^R$, not of an arbitrary bare monomial. If operators mix, the vector of form factors mixes as well.

Conserved currents are special. A properly normalized exactly conserved current often has protected normalization, reflected in Ward identities and in conditions like $F(0)=Q$. Nonconserved composite operators generally require independent renormalization, and their form factors depend on the renormalization scale and scheme.

In massless gauge theories, form factors can also contain infrared divergences. These are not ultraviolet operator-renormalization divergences. A massless quark or gluon form factor, for example, has soft and collinear singularities in perturbation theory. Physical cross sections require inclusive definitions, factorization, or cancellation against real radiation.

## Sudakov behavior

At large momentum transfer in a gauge theory, form factors often contain large logarithms. A typical schematic behavior is

$$
F(q^2)
=
1+\frac{\alpha}{4\pi}
\left[-A\log^2\frac{-q^2}{\mu^2}+B\log\frac{-q^2}{\mu^2}+\cdots\right]+O(\alpha^2).
$$

The double logarithm is a Sudakov logarithm, coming from overlapping soft and collinear regions. At higher orders these logarithms can exponentiate or be resummed using factorization and renormalization-group methods.

This is one of the reasons form factors are central in precision QFT. They are simple enough to compute deeply, but rich enough to display ultraviolet renormalization, infrared factorization, anomalous dimensions, analytic structure, and resummation.

## Form factors versus amplitudes

The distinction is worth keeping sharp.

| Object | Typical notation | External local operator? | Momentum conservation |
|---|---|---:|---|
| scattering amplitude | $\langle f|S|i\rangle$ | no distinguished local insertion | $P_f=P_i$ |
| form factor | $\langle f|\mathcal O(0)|i\rangle$ | yes | $P_f=P_i+q$ if the operator injects $q$ |
| vacuum form factor | $\langle f|\mathcal O(0)|0\rangle$ | yes | $q=P_f$ |
| correlator with insertion | $\langle T\{\mathcal O\phi\cdots\phi\}\rangle$ | yes | off-shell external momenta allowed |

A form factor can be viewed as an amplitude with one external source, but the source is usually not integrated over as a dynamical field. If the source is promoted to a real particle, then one obtains a scattering amplitude in an enlarged theory. That is a useful trick, not the definition.

## Common pitfalls

**Amputating the operator insertion.** LSZ removes poles from external particle legs. The local operator insertion is not an external propagator unless a source field has been made dynamical.

**Confusing ultraviolet and infrared divergences.** Operator renormalization removes short-distance divergences of the local insertion. Soft and collinear divergences come from long-distance massless propagation and require different tools.

**Assuming a form factor is always a function of one variable.** A two-state current form factor may depend only on $q^2$ in simple cases. Multiparticle form factors depend on many invariants.

**Forgetting operator mixing.** A form factor of $\mathcal O_i$ is only meaningful after specifying the renormalized operator basis and scheme.

**Using off-shell Green functions as observables.** The form factor is the on-shell matrix element after LSZ extraction. Off-shell insertion vertices are useful intermediate objects but are generally convention dependent.

**Overinterpreting $F(0)$.** For conserved currents, zero-momentum form factors are often fixed by charges or normalization. For nonconserved operators, $F(0)$ may be scheme dependent or require subtractions.

## Relations to other pages

- [Composite Operator Insertions](/perturbative-qft/form-factors-composite-operators/composite-operator-insertions/) defines the local insertion machinery used here.
- [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/) explains the pole extraction for external states.
- [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/) distinguishes amputated Green functions from on-shell matrix elements.
- [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/) and [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/) explain the unitarity logic behind discontinuities.
- [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) and [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/) explain infrared singularities in massless form factors.
- [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/) gives the surrounding renormalized perturbative framework.

## Research status

**Established.** Form factors are standard QFT observables. Their Lorentz decompositions, Ward-identity constraints, LSZ extraction, renormalization, and analytic structure are textbook material.

**Active.** High-loop form factors, infrared anomalous dimensions, nonperturbative hadronic form factors, lattice determinations, integrable form factors, conformal form factors, and celestial or bootstrap representations remain active research directions.

**Approximation-dependent.** Perturbative form factors are reliable when the external states and kinematic regime are perturbative. Hadronic form factors at low energies often require nonperturbative methods, dispersion theory, lattice QCD, EFT, or experimental input.

## Exercises

### Exercise 1: Translation invariance

Use $\mathcal O(x)=e^{iP\cdot x}\mathcal O(0)e^{-iP\cdot x}$ to derive

$$
\langle f|\mathcal O(x)|i\rangle
=
e^{i(P_f-P_i)\cdot x}\langle f|\mathcal O(0)|i\rangle.
$$

<details>
<summary><strong>Solution</strong></summary>

Momentum eigenstates obey

$$
P^\mu|i\rangle=P_i^\mu|i\rangle,
\qquad
\langle f|P^\mu=\langle f|P_f^\mu.
$$

Therefore

$$
\begin{aligned}
\langle f|\mathcal O(x)|i\rangle
&=
\langle f|e^{iP\cdot x}\mathcal O(0)e^{-iP\cdot x}|i\rangle\\
&=
e^{iP_f\cdot x}e^{-iP_i\cdot x}
\langle f|\mathcal O(0)|i\rangle\\
&=
e^{i(P_f-P_i)\cdot x}
\langle f|\mathcal O(0)|i\rangle.
\end{aligned}
$$

</details>

### Exercise 2: Scalar current conservation

For equal-mass scalar states, show that

$$
\langle p'|J^\mu(0)|p\rangle=(p'+p)^\mu F(q^2),
\qquad q=p'-p,
$$

is conserved on shell.

<details>
<summary><strong>Solution</strong></summary>

Contract with $q_\mu$:

$$
q_\mu(p'+p)^\mu
=(p'-p)\cdot(p'+p)
=p'^2-p^2.
$$

For equal-mass on-shell states, $p'^2=p^2=m^2$, so

$$
q_\mu\langle p'|J^\mu(0)|p\rangle=0.
$$

</details>

### Exercise 3: Tree-level φ² form factor

In a free real scalar theory, compute

$$
\left\langle p_1,p_2\middle|\frac12\phi(0)^2\middle|0\right\rangle
$$

for the connected two-particle matrix element.

<details>
<summary><strong>Solution</strong></summary>

The field $\phi(0)$ contains a creation part and an annihilation part. The only term contributing between the vacuum and a two-particle bra is the term with two creation operators in $\phi(0)^2$. There are two ways to assign the two fields to the two outgoing identical bosons, and the factor $1/2$ cancels this multiplicity. With the standard normalization of the field and states used in this volume, the reduced form factor is

$$
\left\langle p_1,p_2\middle|\frac12\phi(0)^2\middle|0\right\rangle=1.
$$

</details>

### Exercise 4: Pole extraction

Suppose a Green function with one scalar operator insertion behaves near two external scalar poles as

$$
\widetilde G_{\mathcal O,2}(p_1,p_2)
\sim
\frac{iZ^{1/2}}{p_1^2-m^2+i\epsilon}
\frac{iZ^{1/2}}{p_2^2-m^2+i\epsilon}
F_{\mathcal O}(p_1,p_2).
$$

Show how to extract $F_{\mathcal O}$.

<details>
<summary><strong>Solution</strong></summary>

Multiply by the inverse pole factors and take the on-shell limit:

$$
F_{\mathcal O}(p_1,p_2)
=
\lim_{p_1^2,p_2^2\to m^2}
\frac{p_1^2-m^2}{iZ^{1/2}}
\frac{p_2^2-m^2}{iZ^{1/2}}
\widetilde G_{\mathcal O,2}(p_1,p_2).
$$

The less singular terms vanish in this limit. This is LSZ pole extraction applied to the external scalar legs. If the correlator is first amputated with inverse full propagators, the same result is written with the compensating factor $Z$ multiplying the amputated two-leg insertion.

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for scattering theory, state normalization, LSZ, and current matrix elements; Vol. II for operator methods and applications.
- M. Srednicki, *Quantum Field Theory*, for LSZ, spectral representations, scattering, currents, and renormalized perturbation theory.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on cross sections, LSZ, unitarity, QED form factors, QCD, and jets.
- J. Collins, *Renormalization*, for operator renormalization and factorization logic.
- G. Sterman, *An Introduction to Quantum Field Theory*, for form factors, factorization, and infrared structure in perturbative gauge theories.

## Version history

- **2026-06-13:** Initial polished draft for QFT.org, defining form factors as local operator matrix elements and relating them to operator insertions, LSZ, renormalization, analyticity, and infrared physics.
