---
title: "Mass Gap in Gauge Theory"
description: "Explains the physical mass gap in gauge theories through spectra, Euclidean correlators, finite-volume limits, glueballs, and the Yang–Mills mass-gap problem."
sidebar:
  label: "Mass Gap"
  order: 3
level: Advanced
status: "Polished draft"
source: "Srednicki ch. 82; Polyakov; Shifman chs. 1 and 9; Jaffe–Witten; Clay Mathematics Institute."
topics:
  - mass gap
  - Yang–Mills theory
  - glueballs
  - confinement
  - Euclidean correlators
  - spectral representation
  - finite volume
  - lattice gauge theory
canonicalTopics:
  - nonperturbative-qft
  - confinement
  - mass-gap
  - yang-mills-theory
  - spectral-representation
researchStatus:
  established:
    - "A mass gap is a spectral statement about the physical Hilbert space and is detected by exponential decay of gauge-invariant Euclidean correlators."
  active:
    - "Four-dimensional pure Yang–Mills theory is physically and numerically believed to have a mass gap, but a rigorous construction with proof of the mass gap remains an open Millennium problem."
---

## Summary

A **mass gap** means that the vacuum is isolated from all non-vacuum physical excitations by a positive energy. In an infinite-volume relativistic theory normalized so that the vacuum energy is zero, the basic statement is

$$
\Delta
=\inf\bigl(\operatorname{spec}H\setminus\{0\}\bigr)>0.
$$

In a gauge theory, this must be read carefully: $H$ acts on the **physical**, gauge-invariant Hilbert space. A gauge-fixed gluon propagator may show a scale, and a perturbative gauge boson may be massless in the Lagrangian, but neither statement by itself decides whether the physical theory has a mass gap.

The Euclidean diagnostic is exponential decay of connected, gauge-invariant correlators. For an operator $O$ with vacuum quantum numbers removed,

$$
C_O(\tau)
=\int d^{d-1}\mathbf x\,
\langle O(\tau,\mathbf x)O(0,\mathbf 0)\rangle_c
=\sum_{n\ne0}|\langle0|O|n\rangle|^2e^{-E_n\tau}.
$$

If $O$ overlaps with the lightest state in its quantum-number channel, then at large Euclidean time

$$
C_O(\tau)\sim A_O e^{-m_O\tau}.
$$

The mass gap is the smallest such physical mass over all non-vacuum channels.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A spectral picture of a mass gap and the corresponding exponential decay of Euclidean correlators.](/figures/nonperturbative-qft/mass-gap-spectral-diagnostics.svg)

<figcaption>

A mass gap is a statement about the physical spectrum. In Euclidean signature, the same gap appears as exponential decay of connected gauge-invariant correlation functions. Finite-volume gaps, gauge-fixed propagator scales, and perturbative mass parameters are not substitutes for the infinite-volume physical gap $\Delta$.

</figcaption>
</figure>

For pure Yang–Mills theory in four dimensions, the expected low-energy excitations are color-singlet glueballs and other gauge-invariant states. Physics and lattice calculations strongly support a nonzero gap, but the corresponding constructive theorem is much stronger than measuring a lattice correlation length. The official Millennium problem asks for a nontrivial quantum Yang–Mills theory on $\mathbb R^4$ with a positive mass gap; see [Yang–Mills Mass Gap Problem](/nonperturbative-qft/confinement-screening-mass-gap/yang-mills-mass-gap-problem/) for the theorem-level formulation.

## Prerequisites

Read [What Is Confinement?](/nonperturbative-qft/confinement-screening-mass-gap/what-is-confinement/) first for the separation between confinement, screening, and the absence of colored asymptotic states. Also read [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/), [Spectral Density](/nonperturbative-qft/order-parameters-diagnostics/spectral-density/), and [Correlation Length](/nonperturbative-qft/order-parameters-diagnostics/correlation-length/).

For the definition-sensitive parts, you should know [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/), [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/), [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/), and [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/).

## Physical question

The physical question is not “did we write a mass term in the Lagrangian?” The physical question is:

> How much energy is required to create the lightest non-vacuum, gauge-invariant excitation above the infinite-volume vacuum?

This question is easy to answer in a free massive scalar theory. It is subtle in a non-Abelian gauge theory because the elementary fields in the Lagrangian are not the same as the physical particles. In pure Yang–Mills theory, the gauge potential $A_\mu^a$ is not a gauge-invariant observable, and perturbation theory around $A_\mu^a=0$ contains massless gluons. But the expected physical spectrum is not a spectrum of isolated gluons. It is a spectrum of gauge-invariant bound states, usually called **glueballs**, together with multi-particle states made from them.

So the mass-gap question is a test of the nonperturbative vacuum. It asks whether the interacting gauge-field vacuum rearranges the theory so that all physical excitations are separated from the vacuum by a nonzero mass scale.

## Setup and conventions

We use the conventions of the [Nonperturbative QFT Conventions](/nonperturbative-qft/conventions/). Lorentzian signature is mostly minus, and Euclidean correlators are obtained by Wick rotation when the Euclidean theory satisfies the needed positivity and reconstruction properties.

Let $H$ be the Hamiltonian in a physical Hilbert space $\mathcal H_{\rm phys}$. In a gauge theory, $\mathcal H_{\rm phys}$ means states obeying the constraints, or equivalently states created from the vacuum by gauge-invariant operators after the theory is correctly defined. We set the vacuum energy to zero:

$$
H|0\rangle=0.
$$

The theory has a mass gap if there is a number $\Delta>0$ such that

$$
\operatorname{spec}(H)\cap(0,\Delta)=\varnothing.
$$

For a relativistic theory, the invariant mass of a one-particle state is read from the joint spectrum of energy and momentum:

$$
P_\mu P^\mu=m^2.
$$

At zero spatial momentum, the energy of a one-particle state is its mass. Thus lattice and Euclidean calculations often extract masses from zero-momentum projected correlators.

## Definition through correlators

Let $O(x)$ be a gauge-invariant local operator. In pure Yang–Mills theory, typical choices are built from the field strength, for example

$$
O_S(x)=\operatorname{tr}F_{\mu\nu}F^{\mu\nu}(x),
\qquad
O_P(x)=\operatorname{tr}F_{\mu\nu}\widetilde F^{\mu\nu}(x),
$$

where $O_S$ couples to scalar glueball quantum numbers and $O_P$ to pseudoscalar glueball quantum numbers. The zero-momentum Euclidean connected correlator is

$$
C_O(\tau)
=\int d^{d-1}\mathbf x\,
\langle O(\tau,\mathbf x)O(0,\mathbf 0)\rangle_c.
$$

Inserting a complete set of physical energy eigenstates gives

$$
C_O(\tau)
=\sum_{n\ne0}|\langle0|O|n\rangle|^2e^{-E_n\tau}.
$$

The connected correlator matters. If $O$ has a vacuum expectation value, then the disconnected term

$$
|\langle0|O|0\rangle|^2
$$

would otherwise survive at large $\tau$ and hide the spectral decay. The connected correlator removes the vacuum contribution.

At large $\tau$, the lightest state with nonzero overlap dominates:

$$
C_O(\tau)
\sim A_Oe^{-m_O\tau},
\qquad
A_O=|\langle0|O|O_{\rm light}\rangle|^2.
$$

The mass gap is not necessarily the $m_O$ seen by a randomly chosen operator. It is the minimum over all physical non-vacuum sectors:

$$
\Delta=\min_{O\,\mathrm{physical}}m_O,
$$

when the minimum is attained by a stable one-particle state. More generally, $\Delta$ is the bottom of the non-vacuum spectrum.

## Spatial correlation length

In a Euclidean theory with rotational invariance restored in the continuum limit, the same scale controls long-distance spatial decay. A connected correlator at large separation behaves schematically as

$$
\langle O(x)O(0)\rangle_c
\sim \frac{e^{-m_O|x|}}{|x|^{(d-1)/2}}
$$

for an isolated massive particle in $d$ Euclidean dimensions. The power-law prefactor depends on dimension and on the nature of the spectral threshold, but the exponential scale is robust.

The corresponding correlation length is

$$
\xi_O=\frac{1}{m_O}.
$$

Thus a mass gap can be detected either as a nonzero lowest energy in the Hamiltonian spectrum or as exponential clustering of Euclidean correlators. In a gapped relativistic theory, both are two views of the same infrared fact.

## Gauge theories and physical states

Gauge theory adds two layers of caution.

First, the physical Hilbert space is not the naive Fock space of gauge potentials. In perturbation theory, one often computes with gauge-fixed gluon and ghost fields. Those fields are useful variables, not physical particles. The statement “the gluon is massless in the Lagrangian” does not prevent the physical spectrum from being gapped, and the statement “a gauge-fixed propagator has an infrared scale” does not prove a physical mass gap.

Second, the local operators used to detect the spectrum must be gauge-invariant. In pure Yang–Mills theory, examples include traces of products of field strengths, Wilson loops, Polyakov loops at finite temperature, and extended gauge-invariant operators. A glueball mass is extracted from an operator basis with the desired quantum numbers, not from a single gauge component.

A useful slogan is:

$$
\text{mass gap in gauge theory}
=\text{gap in the gauge-invariant spectrum}.
$$

That slogan is safe. The unsafe version is “the gauge boson got a mass,” because it confuses a physical spectral statement with a statement about fields in a particular description.

## Pure Yang–Mills theory

Pure Yang–Mills theory in four dimensions has action

$$
S_E[A]
=\frac{1}{2g^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}
$$

in Euclidean conventions, up to normalization of the generators. Classically, there is no mass parameter. Perturbatively, the theory contains massless gauge bosons. Quantum mechanically, asymptotic freedom generates a scale by dimensional transmutation:

$$
\Lambda_{\rm YM}
=\mu\,\exp\left[-\int^{g(\mu)}\frac{dg}{\beta(g)}\right].
$$

The expected physical spectrum is then measured in units of $\Lambda_{\rm YM}$ or in units of the string tension $\sqrt\sigma$. The lightest states are glueballs, with quantum numbers such as

$$
0^{++},\qquad 2^{++},\qquad 0^{-+},\quad \ldots
$$

The mass gap is the mass of the lightest gauge-invariant excitation, commonly expected to be the lightest scalar glueball in pure Yang–Mills theory.

The important distinction is this:

| Statement | Meaning | Status |
|---|---|---|
| Lattice simulations find a nonzero lightest glueball mass. | Nonperturbative numerical evidence using a regulator and continuum extrapolation. | Very strong physics evidence. |
| Pure Yang–Mills has a mass gap. | Physical continuum statement about the infinite-volume gauge-invariant spectrum. | Standard belief in QFT. |
| The Yang–Mills existence and mass gap problem is solved. | Construct a nontrivial four-dimensional quantum Yang–Mills theory satisfying rigorous axioms and prove $\Delta>0$. | Open. |

One page can explain the physics. It cannot honestly pretend that the theorem exists.

## Mass gap is not confinement

A mass gap and confinement often travel together in pure non-Abelian gauge theory, but they are logically different.

A massive scalar theory has a mass gap but no confinement. A Higgs phase can have a fully gapped gauge-invariant spectrum while external charges are screened rather than confined. A conformal field theory has no mass gap, even though it may be strongly coupled. A gauge theory with dynamical fundamental matter can have a mass gap and no exact Wilson-loop area law for fundamental probes, because the flux tube can break.

The clean separation is:

$$
\begin{array}{ccl}
\text{mass gap} &:& \text{spectrum above the vacuum},\\
\text{confinement} &:& \text{behavior of charges, line operators, or colored states},\\
\text{screening} &:& \text{ability of dynamical matter to neutralize probes}.
\end{array}
$$

In pure Yang–Mills theory, a Wilson-loop area law and a mass gap are both expected consequences of the same strongly coupled infrared dynamics. But neither definition should be collapsed into the other.

## Finite volume and the order of limits

Finite volume is a trap. A finite box often has a discrete spectrum even when the infinite-volume theory is gapless. For example, a free massless scalar field in a spatial box of size $L$ has nonzero momentum modes with energies of order

$$
E\sim \frac{2\pi}{L},
$$

but this is not a mass gap. It vanishes as $L\to\infty$.

Therefore a physical mass gap is an infinite-volume statement:

$$
\Delta=\lim_{L\to\infty}\Delta(L),
$$

provided the limit exists. In a lattice theory with spacing $a$, one must also take the continuum limit. A careful continuum statement has the schematic form

$$
\Delta_{\rm phys}
=\lim_{a\to0}\lim_{L\to\infty}\frac{\Delta(a,L)}{a},
$$

with the bare parameters tuned so that physical ratios remain fixed.

The order and meaning of limits depend on the regulator, but the principle is stable: the gap must survive the removal of infrared and ultraviolet regulators.

## Effective mass extraction

On a lattice with Euclidean time spacing $a$, suppose the zero-momentum correlator behaves as

$$
C(n a)=A e^{-mna}+B e^{-m'na}+\cdots,
\qquad m<m'.
$$

An effective mass is often defined by

$$
am_{\rm eff}(n)=\log\frac{C(na)}{C((n+1)a)}.
$$

At large $n$,

$$
m_{\rm eff}(n)\to m.
$$

In real calculations, a single operator may have poor overlap with the true ground state in a channel. One uses a basis of operators $O_i$ and computes a matrix

$$
C_{ij}(\tau)=\langle O_i(\tau)O_j(0)\rangle_c.
$$

A variational analysis then improves the separation of ground and excited states. The conceptual point is simple: the mass gap is extracted from the exponential decay of the best gauge-invariant correlators, after controlling excited-state contamination, finite-volume effects, and lattice-spacing effects.

## Glueballs and channels

In pure Yang–Mills theory, glueballs are color-singlet excitations created by gauge-invariant operators. Operators are classified by spin, parity, and charge conjugation in the continuum. On a cubic lattice, continuum rotations are reduced to lattice rotations, so the practical operator classification uses irreducible representations of the lattice symmetry group and then extrapolates toward continuum spin assignments.

The scalar channel is usually probed by operators resembling

$$
\operatorname{tr}F_{\mu\nu}F_{\mu\nu},
$$

while pseudoscalar and tensor channels use other combinations. Extended loop operators often have better overlap with flux-tube-like or glueball states than ultra-local operators. This is not a contradiction: different operators can create the same physical state with different amplitudes.

A channel mass $m_{0^{++}}$ is not automatically the global mass gap unless it is the smallest mass in the whole physical spectrum. In pure Yang–Mills theory, the lightest scalar glueball is expected to be the lowest state, but conceptually the gap is the minimum over all sectors.

## Mechanisms and examples

A mass gap can arise in several different ways. Do not confuse them.

### Explicit mass

A free scalar field with action

$$
S=\int d^dx\left[\frac12(\partial\phi)^2+\frac12m^2\phi^2\right]
$$

has a gap $m$ by construction. This is not a nonperturbative mass gap.

### Higgs mechanism

A gauge theory in a Higgs regime can have a gapped gauge-invariant spectrum. The gauge field variables may combine with scalar degrees of freedom, but the gauge-invariant statement is about massive physical excitations and screened charges. Higgs mass generation is not the same as confining mass generation.

### Compact QED in three dimensions

In [Compact QED in Three Dimensions](/nonperturbative-qft/confinement-screening-mass-gap/compact-qed-three-dimensions/), monopole instantons generate a potential for the dual photon. The dual photon becomes massive, producing a mass gap and a Wilson-loop area law. This is a controlled analytic mechanism in a lower-dimensional compact gauge theory.

### Pure non-Abelian Yang–Mills

In four-dimensional pure Yang–Mills theory, asymptotic freedom generates the scale $\Lambda_{\rm YM}$, and the infrared theory is expected to have only massive color-singlet excitations. This is the central physical example, but not one with a complete analytic derivation from first principles.

## Relation to line operators

Line operators diagnose how external probes behave, not directly what the lightest local particle is. Still, in pure confining Yang–Mills theory the two are deeply connected.

An area law for a large Wilson loop,

$$
\langle W(C)\rangle\sim e^{-\sigma A(C)},
$$

indicates a stable flux tube between external charges. A nonzero string tension $\sigma$ is a separate infrared scale. The mass gap is detected by local or extended gauge-invariant correlators. The flux tube has a thickness set by bulk correlation lengths, so a gapped bulk helps make a string-like long-distance description possible.

But one should not infer

$$
\Delta>0
\quad\Longleftrightarrow\quad
\sigma>0
$$

as a universal theorem. The relationship depends on dimension, matter content, global form of the gauge group, and which line operators are genuine.

## Research status

**Established.** In a well-defined quantum theory, a mass gap is a spectral statement and can be diagnosed by exponential decay of connected Euclidean correlators. In lattice gauge theory, glueball masses and other gaps are extracted by transfer-matrix and correlation-function methods using gauge-invariant operators.

**Physically settled but not theorem-level.** Four-dimensional pure Yang–Mills theory is overwhelmingly believed to have a mass gap. Lattice calculations and the phenomenology of strong interactions support this picture. It is also consistent with the Wilson-loop and flux-tube diagnostics of confinement.

**Open.** A rigorous construction of nontrivial four-dimensional pure Yang–Mills theory on $\mathbb R^4$ with a positive mass gap remains open. The Clay Millennium problem is not asking for more evidence; it is asking for a proof at the level of mathematical quantum field theory.

## Common mistakes

**Mistake 1: Using a gauge-fixed two-point function as the definition.** Gauge-fixed gluon propagators are useful, but the mass gap is a physical spectral statement. It should be formulated using gauge-invariant observables or a physical Hilbert space.

**Mistake 2: Calling every finite-volume level spacing a mass gap.** A finite box discretizes momenta. The gap must remain positive as $L\to\infty$.

**Mistake 3: Equating mass gap and confinement.** They are related in pure Yang–Mills, but not equivalent in general.

**Mistake 4: Forgetting vacuum subtraction.** If $\langle O\rangle\ne0$, the two-point function includes a constant disconnected term. Use connected correlators to see spectral decay.

**Mistake 5: Treating the Clay problem as a numerical benchmark.** Lattice evidence is indispensable physics, but the Millennium problem asks for existence and proof in the continuum.

## Relation to other topics

[Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/) gives the general spectral and correlator toolkit. [Spectral Density](/nonperturbative-qft/order-parameters-diagnostics/spectral-density/) explains how poles, thresholds, and continua encode the spectrum.

[Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/) and [String Tension](/nonperturbative-qft/confinement-screening-mass-gap/string-tension/) explain the line-operator side of confinement. [Flux Tubes](/nonperturbative-qft/confinement-screening-mass-gap/flux-tubes/) explains the string-like states between heavy probes.

[Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) explains why the expected color-singlet spectrum becomes narrow and string-like as $N\to\infty$. [Yang–Mills Mass Gap Problem](/nonperturbative-qft/confinement-screening-mass-gap/yang-mills-mass-gap-problem/) separates the physical gap from the open constructive theorem.

[Strong-Coupling Expansion](/nonperturbative-qft/confinement-screening-mass-gap/strong-coupling-expansion/) gives a controlled lattice-regulated area-law argument at strong coupling. [Compact QED in Three Dimensions](/nonperturbative-qft/confinement-screening-mass-gap/compact-qed-three-dimensions/) gives a controlled analytic mass-gap mechanism through monopole instantons. [Confinement Mechanisms](/nonperturbative-qft/confinement-screening-mass-gap/confinement-mechanisms/) compares this and other dynamical explanations for gaps, area laws, and flux tubes.

## Exercises

### Exercise 1: Spectral dominance

Suppose

$$
C(\tau)=A_1e^{-E_1\tau}+A_2e^{-E_2\tau}+\cdots,
\qquad
0<E_1<E_2<\cdots,
$$

with $A_1\ne0$. Show that

$$
-\lim_{\tau\to\infty}\frac{1}{\tau}\log C(\tau)=E_1.
$$

<details>
<summary><strong>Solution</strong></summary>

Factor out the leading term:

$$
C(\tau)=A_1e^{-E_1\tau}
\left[1+\frac{A_2}{A_1}e^{-(E_2-E_1)\tau}+\cdots\right].
$$

Taking the logarithm gives

$$
\log C(\tau)=\log A_1-E_1\tau+
\log\left[1+O(e^{-(E_2-E_1)\tau})\right].
$$

Dividing by $-\tau$ and taking $\tau\to\infty$ yields

$$
-\lim_{\tau\to\infty}\frac{1}{\tau}\log C(\tau)=E_1.
$$

</details>

### Exercise 2: A finite box is not a mass gap

Consider a free massless scalar in a spatial box of length $L$ with periodic boundary conditions. Ignoring the zero mode, the lowest nonzero momentum is $2\pi/L$. What happens to the corresponding energy as $L\to\infty$?

<details>
<summary><strong>Solution</strong></summary>

For a massless particle,

$$
E=|\mathbf p|.
$$

The lowest nonzero momentum has magnitude

$$
|\mathbf p|=\frac{2\pi}{L}.
$$

Thus

$$
E_{\min}(L)=\frac{2\pi}{L}\to0
$$

as $L\to\infty$. The finite-volume level spacing is therefore not an infinite-volume mass gap.

</details>

### Exercise 3: Vacuum subtraction

Let $O$ be an operator with $\langle O\rangle=v\ne0$. Explain why the unconnected correlator does not decay to zero at large Euclidean time, and write the connected correlator.

<details>
<summary><strong>Solution</strong></summary>

The unconnected correlator contains the vacuum contribution

$$
\langle O(\tau)O(0)\rangle\supset
\langle0|O|0\rangle\langle0|O|0\rangle=v^2.
$$

Therefore it approaches $v^2$ at large separation rather than zero. The connected correlator is

$$
\langle O(\tau)O(0)\rangle_c
=\langle O(\tau)O(0)\rangle-\langle O\rangle^2.
$$

This removes the vacuum term and exposes the exponential decay from non-vacuum states.

</details>

### Exercise 4: Gap and correlation length

If a connected Euclidean correlator decays as

$$
G(r)\sim e^{-mr}
$$

at large distance, what is the corresponding correlation length $\xi$?

<details>
<summary><strong>Solution</strong></summary>

The standard form of exponential decay is

$$
G(r)\sim e^{-r/\xi}.
$$

Comparing with $e^{-mr}$ gives

$$
\xi=\frac{1}{m}.
$$

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, especially chapter 82, for Wilson loops, lattice gauge theory, and confinement diagnostics.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapters 1 and 9, for phases of gauge theories, confinement, flux tubes, glueballs, and mass-gap context.
- K. Wilson and J. Kogut’s lattice and renormalization-group literature, for the regulated-lattice and continuum-limit viewpoint behind confinement and mass-gap diagnostics.

### Deeper references

- A. M. Polyakov, *Gauge Fields and Strings*, for strong-coupling, compact-gauge-theory, mass-gap, and confinement mechanisms.
- A. Jaffe and E. Witten, “Quantum Yang–Mills Theory,” for the Millennium problem statement and constructive-theory expectations.
- Clay Mathematics Institute, “Yang–Mills and Mass Gap,” for the official status of the problem.
- M. Lüscher and P. Weisz, and the lattice glueball-spectrum literature, for numerical extraction of the pure-gauge spectrum.

## Version history

- **2026-06-27:** Initial polished page. Added spectral definition, Euclidean correlator extraction, finite-volume and continuum-limit caveats, glueball-channel discussion, mass-gap/confinement distinction, Clay-problem status, and exercises.
- **2026-06-27:** Linked Large-N Confinement and Yang–Mills Mass Gap Problem as companion pages for planar/string organization and theorem-level status.
