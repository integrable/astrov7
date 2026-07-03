---
title: "Wilson Loops"
description: "Defines Wilson lines and Wilson loops, derives their gauge transformation law, and explains how large rectangular loops diagnose static potentials and confinement."
sidebar:
  label: "Wilson Loops"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §82; Polyakov, Gauge Fields and Strings, Chs. 5 and 7; Schwartz Ch. 25; Gaiotto–Kapustin–Seiberg–Willett 2015."
topics:
  - Wilson loops
  - Wilson lines
  - static potential
  - area law
  - perimeter law
  - line operators
canonicalTopics:
  - wilson-loop
  - wilson-line
  - static-potential
  - area-law
  - perimeter-law
researchStatus:
  established:
    - "Wilson loops are standard gauge-invariant line operators; rectangular Wilson loops extract the static potential of external probe charges."
  active:
    - "The precise confinement diagnostics in theories with dynamical matter, nontrivial global form, mixed Wilson–’t Hooft lines, and generalized symmetries remain active research topics."
---

## Summary

A **Wilson line** is the parallel transporter of a gauge connection along a path. A **Wilson loop** is the trace of that transporter around a closed curve. In a gauge theory, this is one of the most important nonlocal observables:

$$
\mathcal W_R(C)
=\frac{1}{d_R}\operatorname{tr}_R P\exp\left[-ig\oint_C dx^\mu A_\mu^a(x)T_R^a\right].
$$

Here $R$ is a representation of the gauge group, $d_R=\dim R$, and $P$ denotes path ordering. The factor $1/d_R$ is a normalization convention, chosen so that $\mathcal W_R(C)=1$ when the connection is trivial.

Wilson loops matter for two reasons. First, they are gauge invariant without choosing a gauge. Second, their expectation values diagnose long-distance gauge dynamics. For a large Euclidean rectangle $C_{R,T}$ of spatial width $R$ and time extent $T$,

$$
\langle \mathcal W_R(C_{R,T})\rangle
\sim e^{-T V_R(R)},
\qquad T\gg R,
$$

up to perimeter self-energy terms that must be subtracted or absorbed into the definition of the external probes. If $V_R(R)\sim \sigma_R R$ at large $R$, the probe charges are connected by a flux tube with string tension $\sigma_R$.

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 55rem;">

![A Wilson loop shown as a closed curve bounding a minimal area, and a rectangular Wilson loop extracting the static potential between an external charge and anticharge.](/figures/gauge-theories-standard-model/wilson-loop-potential.svg)

<figcaption>

A Wilson loop is the trace of parallel transport around a closed curve. For a large rectangle $C_{R,T}$, the logarithm of the expectation value extracts the static potential $V_R(R)$. An area law gives $V_R(R)\simeq \sigma_R R$ and therefore a confining flux tube for the external probe representation $R$.

</figcaption>
</figure>

## Prerequisites

You should know [Gauge Fields as Connections](/gauge-theories-standard-model/gauge-principle/gauge-fields-as-connections/), [Field Strength and Curvature](/gauge-theories-standard-model/gauge-principle/field-strength-and-curvature/), [Gauge-Invariant Observables](/gauge-theories-standard-model/gauge-principle/gauge-invariant-observables/), [Non-Abelian Gauge Transformations](/gauge-theories-standard-model/yang-mills/non-abelian-gauge-transformations/), and [Global Form and Center](/gauge-theories-standard-model/yang-mills/global-form-and-center/).

For the confinement interpretation, it helps to have read [Asymptotic Freedom](/gauge-theories-standard-model/gauge-renormalization/asymptotic-freedom/) and [Dimensional Transmutation in Gauge Theory](/gauge-theories-standard-model/gauge-renormalization/dimensional-transmutation-in-gauge-theory/). The lattice strong-coupling argument below is qualitative; a full lattice treatment belongs in the Nonperturbative QFT and Computational QFT volumes.

## Core idea

A gauge connection is not directly gauge invariant. It tells us how to compare internal vectors at nearby spacetime points. The Wilson line is the finite comparison along a path:

$$
\text{connection}\quad A_\mu dx^\mu
\quad\Longrightarrow\quad
\text{parallel transporter along }C.
$$

The analogy with ordinary geometry is exact enough to be useful. A connection on a curved manifold tells a vector how to rotate under parallel transport. Transporting around a closed loop can return the vector rotated; the failure to return trivially measures curvature and holonomy. A gauge field does the same thing, except the vector lives in an internal representation space.

For small loops, the Wilson loop is controlled by the field strength. For large loops, it is controlled by the long-distance dynamics of the quantum gauge theory. That is the magic: the same object knows both local curvature and infrared phase structure.

## Setup and conventions

We use the volume convention

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a,
$$

with Hermitian generators obeying

$$
[T^a,T^b]=if^{abc}T^c.
$$

Matter fields in representation $R$ transform as

$$
\psi(x)\mapsto U_R^{-1}(x)\psi(x),
$$

and the gauge field transforms as

$$
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

For a path $C$ from $x_i$ to $x_f$, the Wilson line in representation $R$ is

$$
W_R(C;x_f,x_i)
=P\exp\left[-ig\int_C dx^\mu A_\mu^a(x)T_R^a\right].
$$

The minus sign in the exponent is tied to the convention $D_\mu=\partial_\mu+igA_\mu$. Other common texts use the opposite sign in $D_\mu$ and therefore the opposite sign in the Wilson exponent. The gauge-invariant content is unchanged once conventions are translated consistently.

The path ordering $P$ means that matrices are ordered along the path. If $z^\mu(s)$ parametrizes $C$ with $s\in[0,1]$, then $W_R(s,0)$ solves

$$
\frac{d}{ds}W_R(s,0)
=-ig\dot z^\mu(s)A_\mu^a(z(s))T_R^a W_R(s,0),
\qquad
W_R(0,0)=\mathbf 1.
$$

When the gauge group is Abelian, path ordering is unnecessary. When the gauge group is non-Abelian, it is the whole point.

## Gauge transformation of a Wilson line

The Wilson line transforms only at its endpoints:

$$
W_R(C;x_f,x_i)
\mapsto
U_R^{-1}(x_f)W_R(C;x_f,x_i)U_R(x_i).
$$

This is the finite version of the fact that a connection compares frames. The interior gauge rotations cancel along the path, leaving only the mismatch between the initial and final frames.

For a closed loop $C$ based at $x_0$, $x_f=x_i=x_0$. Taking a trace removes the endpoint transformation:

$$
\operatorname{tr}_R W_R(C;x_0,x_0)
\mapsto
\operatorname{tr}_R\left[U_R^{-1}(x_0)W_R(C;x_0,x_0)U_R(x_0)\right]
=\operatorname{tr}_R W_R(C;x_0,x_0).
$$

Thus

$$
\mathcal W_R(C)
=\frac{1}{d_R}\operatorname{tr}_R W_R(C)
$$

is gauge invariant.

The base point does not matter inside the trace. Moving the base point cyclically permutes the ordered product, and the trace is cyclic.

## Small-loop expansion

A Wilson loop around a small plaquette measures the field strength. Let $C$ be a small rectangle in the $\mu\nu$ plane with coordinate area $\Delta S^{\mu\nu}$. Then the untraced holonomy has the form

$$
W_R(C)
=\mathbf 1_R-igF_{\mu\nu}^a(x)T_R^a\Delta S^{\mu\nu}+O(\Delta S^{3/2}).
$$

The sign follows from the Wilson-line convention above and the definition

$$
[D_\mu,D_\nu]=igF_{\mu\nu}.
$$

For an $SU(N)$ representation, $\operatorname{tr}_R T_R^a=0$, so the leading correction to the traced small Wilson loop is quadratic in the area:

$$
\mathcal W_R(C)
=1-\frac{g^2}{2d_R}\operatorname{tr}_R\left(T_R^aT_R^b\right)
F_{\mu\nu}^aF_{\rho\sigma}^b\Delta S^{\mu\nu}\Delta S^{\rho\sigma}+\cdots.
$$

This is why small plaquettes in lattice gauge theory reproduce the Yang–Mills action. The plaquette is the local curvature probe; large loops are the phase probe.

## Rectangular Wilson loops and static potentials

Take Euclidean spacetime and choose a rectangular loop $C_{R,T}$ of spatial extent $R$ and Euclidean time extent $T$. The loop describes an external charge and external anticharge separated by $R$, created at one time, propagated for time $T$, and annihilated.

The spectral decomposition gives

$$
\langle \mathcal W_R(C_{R,T})\rangle
=\sum_n c_n(R)e^{-E_n(R)T}.
$$

At large $T$, the lowest-energy state dominates:

$$
\langle \mathcal W_R(C_{R,T})\rangle
\sim c_0(R)e^{-V_R(R)T}.
$$

Thus

$$
V_R(R)
=-\lim_{T\to\infty}\frac{1}{T}\log\langle \mathcal W_R(C_{R,T})\rangle,
$$

after removing the ultraviolet self-energy of the static probe worldlines. Those self-energies appear as perimeter divergences and do not represent the force between the two probes.

Three common large-distance behaviors are worth separating.

| Behavior | Wilson loop | Static potential | Interpretation |
|---|---|---|---|
| Coulomb | $\log\langle W(C_{R,T})\rangle\sim +\kappa T/R$ after self-energy subtraction | $V(R)\sim -\kappa/R$ | Massless gauge boson exchange. |
| Area law | $\log\langle W(C)\rangle\sim -\sigma A_{\min}(C)$ | $V(R)\sim \sigma R$ | Confining flux tube for the external probe. |
| Perimeter law | $\log\langle W(C)\rangle\sim -\mu P(C)$ | $V(R)$ saturates after subtraction | Screening, Higgs behavior, or absence of a long flux tube. |

The table hides many refinements, but it captures the core diagnostic.

## Abelian warm-up

In free $U(1)$ gauge theory, a Wilson loop can be evaluated exactly because the path integral is Gaussian. The result has the schematic form

$$
\langle \mathcal W_q(C)\rangle
=\exp\left[-\frac{q^2}{2}\oint_C dx^\mu\oint_C dy^\nu\,\Delta_{\mu\nu}(x-y)\right],
$$

in Euclidean signature, with $\Delta_{\mu\nu}$ the photon propagator in a chosen gauge. Gauge dependence drops out for a closed conserved current.

For a smooth large loop, the short-distance singularity where $x\to y$ gives a perimeter divergence. For a rectangle, the long opposite sides give the Coulomb potential. After subtracting the probe self-energies,

$$
V(R)=-\frac{q^2}{4\pi R}
$$

in the usual normalization. The important lesson is not the coefficient; it is the scaling. Free electromagnetism does not produce an area law. It produces massless long-range fields and a Coulomb potential.

## Non-Abelian Wilson loops

For a non-Abelian gauge group, the Wilson loop depends on the representation $R$:

$$
\mathcal W_R(C)
=\frac{1}{d_R}\operatorname{tr}_R P\exp\left[-ig\oint_C dx^\mu A_\mu^aT_R^a\right].
$$

At weak coupling, expanding the exponential gives gauge-boson exchange. To leading perturbative order, the static potential between probes in representation $R$ contains the quadratic Casimir $C_R$:

$$
V_R(R)\sim -\frac{g^2 C_R}{4\pi R}
$$

at short distances in four-dimensional Yang–Mills theory. This short-distance Coulombic behavior is exactly what asymptotic freedom leads us to expect.

At long distances, the answer is nonperturbative. In a confining pure Yang–Mills theory, the expectation is an area law for Wilson loops with nonzero center charge:

$$
\langle \mathcal W_R(C)\rangle
\sim \exp[-\sigma_R A_{\min}(C)]
$$

for sufficiently large loops, with important qualifications about representation, $N$-ality, and screening by gluons.

## Area law from strong coupling on the lattice

The strong-coupling lattice argument is the cleanest place to see how an area law can arise.

Put the gauge theory on a Euclidean hypercubic lattice. Instead of a continuum gauge field $A_\mu(x)$, assign a group element $U_\ell$ to each oriented link $\ell$. Reversing the orientation replaces $U_\ell$ by $U_\ell^{-1}$. The elementary plaquette variable is the ordered product around a square:

$$
U_p=U_{\ell_1}U_{\ell_2}U_{\ell_3}^{-1}U_{\ell_4}^{-1}.
$$

The Wilson lattice action is built from traces of plaquettes. In one common normalization for $SU(N)$,

$$
S_E=-\frac{\beta}{N}\sum_p \operatorname{Re}\operatorname{tr}U_p,
\qquad
\beta=\frac{2N}{g^2}.
$$

A Wilson loop on the lattice is the trace of the product of link variables around a closed path $C$.

At strong coupling, $g^2\gg 1$, equivalently $\beta\ll 1$, expand $e^{-S_E}$ in powers of $\beta$. The integral over a link variable vanishes unless the link is paired with the conjugate link variables needed to make a gauge-invariant Haar integral. A Wilson loop insertion supplies link variables along the boundary $C$. To get a nonzero contribution, the expansion must fill the interior with plaquettes whose boundary cancels the loop links.

The leading contribution therefore scales as

$$
\langle \mathcal W(C)\rangle
\propto \left(\text{const}\times \beta\right)^{A_{\min}(C)/a^2}
=\exp[-\sigma A_{\min}(C)],
$$

where $a$ is the lattice spacing. This is the area law.

The strong-coupling expansion does not by itself prove continuum confinement in four-dimensional Yang–Mills theory. The continuum limit requires taking $a\to 0$ while following the renormalization-group flow toward weak bare coupling. The deep question is whether the area-law phase persists continuously to that limit. For pure non-Abelian Yang–Mills theory, analytic arguments and lattice evidence strongly support confinement, but a full mathematical proof in four dimensions is a famous open problem.

## Center charge and screening

Wilson loops are sensitive to the center of the gauge group. For $SU(N)$, the center is

$$
Z_N=\{e^{2\pi i k/N}\mathbf 1\mid k=0,1,\ldots,N-1\}.
$$

A representation $R$ has an $N$-ality: the number of boxes in its Young diagram modulo $N$. A Wilson loop with nonzero $N$-ality is charged under the center one-form symmetry of pure $SU(N)$ Yang–Mills theory.

This has two important consequences.

First, representations with zero $N$-ality can be screened by gluons, because gluons transform in the adjoint representation and have zero center charge. Their asymptotic string tension can vanish even in a confining pure gauge theory.

Second, if the theory contains dynamical matter in the fundamental representation, the center one-form symmetry is explicitly broken. External fundamental charges can be screened by pair creation of dynamical matter. The flux tube can break. Then the large Wilson loop eventually behaves more like a perimeter law than an area law, even though the theory may still lack isolated colored particles in its physical spectrum.

This is why the phrase “Wilson loop diagnoses confinement” is safest in pure gauge theory. In full QCD, confinement, screening, hadronization, and chiral symmetry breaking are interwoven, and no single large-loop asymptotic says everything.

## Renormalization of Wilson loops

Wilson loops are gauge invariant, but they are not automatically ultraviolet finite. They have their own renormalization.

A smooth Wilson loop has a perimeter divergence associated with the self-energy of the infinitely heavy external probe. Schematically,

$$
\mathcal W_R^{\rm bare}(C)
\sim e^{-\delta m_R P(C)}\mathcal W_R^{\rm ren}(C),
$$

where $P(C)$ is the perimeter and $\delta m_R$ depends on the regulator.

Loops with cusps have additional logarithmic divergences governed by cusp anomalous dimensions. These cusp divergences are not a nuisance detail; they are central in modern scattering amplitudes, soft radiation, heavy-quark effective theory, and the infrared structure of gauge theory.

For this chapter, the practical rule is simple: when extracting a static potential from a rectangular loop, separate the physically meaningful $R$-dependent part from the perimeter self-energies of the external sources.

## What Wilson loops do and do not prove

A Wilson loop is a probe observable. It can diagnose phases, but it does not by itself solve the theory.

It does tell you:

- how external probes in representation $R$ respond to the gauge vacuum;
- whether the static potential is Coulombic, linearly rising, or screened;
- whether pure gauge theory has area-law behavior for center-charged probes;
- how the theory treats line operators and center charge.

It does not automatically tell you:

- the full physical spectrum;
- whether all possible color nonsinglet excitations are absent;
- the chiral symmetry breaking pattern;
- the complete finite-temperature phase diagram;
- a rigorous proof of the mass gap;
- the answer in a theory with dynamical matter without further analysis.

That humility matters. Wilson loops are powerful because they ask a sharp question. They are not magic eight-balls. Gauge theory remains obnoxiously subtle, as if it were designed by a committee of cats.

## Common pitfalls

**Pitfall 1: forgetting path ordering.** In a non-Abelian theory, $A_\mu(x)$ at different points produces matrices that need not commute. Dropping $P$ changes the observable.

**Pitfall 2: treating an open Wilson line as gauge invariant.** An open line transforms at its endpoints. It becomes gauge invariant only when endpoint transformations are traced, canceled by charged fields, or interpreted as boundary charges.

**Pitfall 3: confusing the perimeter divergence with the physical potential.** A rectangular Wilson loop includes divergent static-source self-energies. The force between probes is in the $R$-dependent part after subtraction.

**Pitfall 4: saying “area law equals confinement” without conditions.** The statement is sharpest in pure gauge theory for center-charged probes. Dynamical matter can break strings and change the asymptotic loop behavior.

**Pitfall 5: using the quadratic Casimir at all distances.** Casimir scaling can be a useful intermediate-distance approximation, but the asymptotic confining behavior in pure $SU(N)$ depends on $N$-ality.

**Pitfall 6: assuming Wilson loops are local observables.** They are extended operators. Their dependence on topology, representation, boundary conditions, and global form is part of their physics.

## Relations to other pages

[Gauge-Invariant Observables](/gauge-theories-standard-model/gauge-principle/gauge-invariant-observables/) introduces Wilson loops as one class of gauge-invariant observable. This page develops their dynamical interpretation.

[Global Form and Center](/gauge-theories-standard-model/yang-mills/global-form-and-center/) explains why the allowed line operators and their center charges depend on the global form of the gauge group.

[Asymptotic Freedom](/gauge-theories-standard-model/gauge-renormalization/asymptotic-freedom/) explains why non-Abelian gauge theory is weakly coupled at short distances. Wilson loops show how that same theory can have strongly coupled long-distance behavior.

[Dimensional Transmutation in Gauge Theory](/gauge-theories-standard-model/gauge-renormalization/dimensional-transmutation-in-gauge-theory/) explains how a scale such as a string tension can emerge from a dimensionless coupling.

The next pages in this chapter introduce ’t Hooft loops, area and perimeter laws in more detail, center symmetry, and the Polyakov loop.

## Research status

The definition of Wilson loops, their gauge transformation law, the static-potential extraction from rectangular loops, and the lattice strong-coupling area-law argument are standard.

The hard part is the continuum infrared dynamics. Four-dimensional pure Yang–Mills theory is widely believed, and strongly supported by lattice evidence, to have a mass gap and confinement. A complete rigorous proof remains open. In theories with dynamical matter, supersymmetry, adjoint matter, mixed global forms, or finite temperature, the Wilson-loop story becomes richer: strings can break, one-form symmetries can be explicitly or spontaneously broken, and Wilson loops must be considered together with ’t Hooft and dyonic line operators.

Modern work often phrases these issues in terms of generalized global symmetries. In that language, Wilson loops are charged line operators, and confinement in pure gauge theory is tied to the realization of center one-form symmetry.

## Exercises

### Exercise 1: Endpoint transformation

Show that the Wilson line

$$
W_R(C;y,x)=P\exp\left[-ig\int_x^y dz^\mu A_\mu^a(z)T_R^a\right]
$$

transforms as

$$
W_R(C;y,x)\mapsto U_R^{-1}(y)W_R(C;y,x)U_R(x).
$$

<details><summary><strong>Solution</strong></summary>

Parametrize the path by $z^\mu(s)$ with $s\in[0,1]$, $z(0)=x$, and $z(1)=y$. Let $W(s,0)$ solve

$$
\frac{d}{ds}W(s,0)
=-ig\dot z^\mu A_\mu(z(s))W(s,0),
\qquad
W(0,0)=\mathbf 1.
$$

Define

$$
\widetilde W(s,0)=U^{-1}(z(s))W(s,0)U(z(0)).
$$

Using

$$
A_\mu^U=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U,
$$

one verifies by differentiating that

$$
\frac{d}{ds}\widetilde W(s,0)
=-ig\dot z^\mu A_\mu^U(z(s))\widetilde W(s,0),
\qquad
\widetilde W(0,0)=\mathbf 1.
$$

By uniqueness of the solution to the transport equation, $\widetilde W$ is the Wilson line built from $A^U$. Setting $s=1$ gives

$$
W_R^U(C;y,x)=U_R^{-1}(y)W_R(C;y,x)U_R(x).
$$

</details>

### Exercise 2: Gauge invariance of a closed loop

Use the result of Exercise 1 to show that

$$
\mathcal W_R(C)=\frac{1}{d_R}\operatorname{tr}_R W_R(C)
$$

is gauge invariant for a closed curve $C$.

<details><summary><strong>Solution</strong></summary>

For a closed curve based at $x_0$, Exercise 1 gives

$$
W_R(C)\mapsto U_R^{-1}(x_0)W_R(C)U_R(x_0).
$$

Taking the trace,

$$
\operatorname{tr}_R\left[U_R^{-1}(x_0)W_R(C)U_R(x_0)\right]
=\operatorname{tr}_R\left[W_R(C)U_R(x_0)U_R^{-1}(x_0)\right]
=\operatorname{tr}_R W_R(C),
$$

where cyclicity of the trace was used.

</details>

### Exercise 3: Area law implies a linear potential

Assume a rectangular Wilson loop satisfies

$$
\langle \mathcal W_R(C_{R,T})\rangle\sim e^{-\sigma_R RT}
$$

for $T\gg R$. Show that the corresponding static potential is linear.

<details><summary><strong>Solution</strong></summary>

The static potential is extracted from

$$
\langle \mathcal W_R(C_{R,T})\rangle\sim e^{-T V_R(R)}.
$$

Comparing with

$$
e^{-\sigma_R RT}=e^{-T(\sigma_R R)},
$$

we find

$$
V_R(R)=\sigma_R R.
$$

Thus the energy required to separate the probe pair grows linearly with separation. The coefficient $\sigma_R$ is the string tension.

</details>

### Exercise 4: Screening and zero N-ality

In pure $SU(N)$ Yang–Mills theory, the adjoint representation has zero $N$-ality. Explain why an external probe in a zero-$N$-ality representation can be screened by gluons, while a fundamental probe cannot.

<details><summary><strong>Solution</strong></summary>

Gluons transform in the adjoint representation. The adjoint representation is neutral under the center $Z_N$, so adding any number of gluons cannot change the $N$-ality of an external probe.

A zero-$N$-ality probe can combine with gluons to form a center-neutral state that can be screened. A fundamental probe has $N$-ality one. Since gluons carry $N$-ality zero, no number of gluons can neutralize its center charge. In pure Yang–Mills theory, a fundamental external probe therefore remains charged under center one-form symmetry.

If dynamical fundamental matter is added, this argument changes: fundamental matter itself carries nonzero $N$-ality and can screen a fundamental probe.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §82, for Wilson loops, lattice gauge theory, strong-coupling area law, and the static potential.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 25, for Wilson lines, Yang–Mills theory, and lattice gauge theory.
- Polyakov, *Gauge Fields and Strings*, Ch. 5, for the phase-factor criterion for confinement.

### Deeper references

- Polyakov, *Gauge Fields and Strings*, Ch. 7, for the loop-space viewpoint on non-Abelian phase factors.
- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for Wilson loops as charged operators under higher-form symmetries.
- Wilson, “Confinement of Quarks,” for the original lattice gauge theory confinement criterion.
- Kogut, “An Introduction to Lattice Gauge Theory and Spin Systems,” for a classic review of lattice gauge theory and strong-coupling methods.
- Makeenko and Migdal, “Exact Equation for the Loop Average in Multicolor QCD,” for loop equations in the large-$N$ limit.

## Version history

- **2026-06-18:** Initial polished draft. Added Wilson-line definition, gauge transformation, small-loop expansion, static-potential extraction, area and perimeter laws, strong-coupling lattice intuition, center-charge caveats, and exercises.
