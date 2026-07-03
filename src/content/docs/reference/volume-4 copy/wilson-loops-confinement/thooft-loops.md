---
title: "’t Hooft Loops"
description: "Defines ’t Hooft loops as magnetic disorder line operators and explains their relation to Wilson loops, Dirac quantization, global form, and confinement diagnostics."
sidebar:
  label: "’t Hooft Loops"
  order: 2
level: Graduate
status: "Polished draft"
source: "Polyakov, Gauge Fields and Strings, Chs. 5 and 7; Srednicki §82; Coleman, Aspects of Symmetry; Gaiotto–Kapustin–Seiberg–Willett 2015."
topics:
  - ’t Hooft loops
  - magnetic line operators
  - Wilson loops
  - confinement
  - center symmetry
  - global form
canonicalTopics:
  - thooft-loop
  - line-operator
  - magnetic-charge
  - dirac-quantization
  - center-symmetry
researchStatus:
  established:
    - "’t Hooft loops are standard magnetic disorder line operators; together with Wilson loops they organize electric, magnetic, and dyonic probes of gauge theory."
  active:
    - "The complete spectrum of genuine line operators, their higher-form symmetry interpretation, and their behavior in strongly coupled phases depend on global form, matter content, and possible discrete theta data."
---

## Summary

A **’t Hooft loop** is the magnetic partner of a Wilson loop. A Wilson loop inserts the holonomy of the gauge connection along a closed curve. A ’t Hooft loop instead inserts a prescribed magnetic singularity along a closed curve. In short,

$$
\text{Wilson loop} = \text{electric order operator},
\qquad
\text{’t Hooft loop} = \text{magnetic disorder operator}.
$$

The path-integral definition is direct. Inserting $T_B(C)$ means integrating over gauge fields whose behavior near the curve $C$ has magnetic charge $B$. If $S^2$ is a small sphere linking the line, then schematically

$$
\frac{g}{2\pi}\int_{S^2}F = B.
$$

For a non-Abelian gauge group, $B$ is chosen in a Cartan subalgebra, modulo Weyl transformations, and Dirac quantization restricts it to the cocharacter lattice appropriate to the chosen global form and matter content.

The reason ’t Hooft loops are indispensable is that Wilson loops see only electric probes. Gauge theories also have magnetic probes. The relative behavior of Wilson and ’t Hooft loops distinguishes Coulomb, Higgs, confining, and obliquely confining phases much more sharply than either observable by itself.

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 55rem;">

![A linked Wilson loop and ’t Hooft loop, with the linking number producing a center phase in the Wilson–’t Hooft algebra.](/figures/gauge-theories-standard-model/thooft-loop-linking.svg)

<figcaption>

A Wilson loop $W_R(C_e)$ is an electric line operator; a ’t Hooft loop $T_B(C_m)$ is a magnetic line operator. When the two loops link, the magnetic singularity can act on the electric probe by a center phase. For $SU(N)$-type examples this phase depends on the $N$-ality of $R$, the magnetic charge, and the linking number $L(C_e,C_m)$.

</figcaption>
</figure>

## Prerequisites

You should know [Wilson Loops](/gauge-theories-standard-model/wilson-loops-confinement/wilson-loops/), [Gauge-Invariant Observables](/gauge-theories-standard-model/gauge-principle/gauge-invariant-observables/), [Non-Abelian Gauge Transformations](/gauge-theories-standard-model/yang-mills/non-abelian-gauge-transformations/), and [Global Form and Center](/gauge-theories-standard-model/yang-mills/global-form-and-center/).

It also helps to know the conceptual distinction between gauge redundancy and global symmetry from [Global Versus Gauge Symmetry](/gauge-theories-standard-model/gauge-principle/global-versus-gauge-symmetry/). The modern statement of line operators uses higher-form global symmetries, but this page gives the minimum needed for the gauge-theory reading path.

## Core idea

A Wilson loop is built directly from the gauge field:

$$
W_R(C)=\frac{1}{d_R}\operatorname{tr}_R P\exp\left[-ig\oint_C A\right].
$$

A ’t Hooft loop is not built by writing a local polynomial in $A_\mu$. It is a **boundary condition** or **defect** in the path integral. Inserting $T_B(C)$ means that, near $C$, the gauge field looks like the field of an external magnetic monopole whose worldline is $C$.

This is why ’t Hooft loops are called disorder operators. They do not measure the gauge field; they change the class of gauge-field configurations being summed over.

In four Euclidean dimensions, a line has three transverse directions. A small two-sphere $S^2$ can link the line. The magnetic charge is the flux through that linking sphere. For an Abelian gauge field, this is literally the magnetic flux of a monopole. For a non-Abelian gauge field, the magnetic charge is chosen in a maximal torus and then identified under the Weyl group.

The slogan is:

$$
\text{Wilson inserts holonomy};\qquad
\text{’t Hooft inserts magnetic topology}.
$$

## Setup and conventions

We keep the volume convention

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a,
$$

with Hermitian generators. A Wilson loop in representation $R$ uses

$$
W_R(C)=\frac{1}{d_R}\operatorname{tr}_R P\exp\left[-ig\oint_C dx^\mu A_\mu^aT_R^a\right].
$$

A ’t Hooft loop $T_B(C)$ is labeled by a magnetic charge $B$. In local coordinates near the line, with $S^2$ a small sphere linking $C$, the defining singularity may be represented schematically as

$$
gF\sim \frac{B}{2}\sin\theta\,d\theta\wedge d\phi,
\qquad
\frac{g}{2\pi}\int_{S^2}F=B.
$$

This formula is a local model, not a complete definition of the renormalized operator. Just as Wilson loops have perimeter and cusp divergences, ’t Hooft loops require ultraviolet regularization near the defect core.

The allowed $B$ obeys Dirac quantization. A compact way to state it is

$$
\lambda(B)\in\mathbb Z
$$

for every electric weight $\lambda$ carried by a dynamical field that must be single-valued around the magnetic defect. Equivalently, $B$ is a cocharacter of the gauge group compatible with the matter content and global form. Physicists often say that magnetic charges are weights of the Langlands dual group. That sentence is compact, elegant, and mildly treacherous until one remembers the global-form caveats.

## Abelian warm-up

In $U(1)$ gauge theory, a Wilson loop of electric charge $q$ is

$$
W_q(C)=\exp\left[-iqg\oint_C A\right].
$$

A ’t Hooft loop of magnetic charge $m$ inserts a monopole worldline. Around a small sphere linking the line,

$$
\frac{g}{2\pi}\int_{S^2}F=m
$$

in units where the minimal electric charge is one. Dirac quantization says that the phase of any allowed electric particle is single-valued around the Dirac string:

$$
qm\in\mathbb Z.
$$

Free Maxwell theory in four dimensions has electric-magnetic duality. Under this duality, Wilson and ’t Hooft loops are exchanged. This is the cleanest cartoon of why ’t Hooft loops should exist: if a theory can be described equally well in electric or magnetic variables, then an electric line in one description becomes a magnetic line in the other.

But one should not confuse the Abelian warm-up with the full non-Abelian story. Non-Abelian ’t Hooft loops are not merely “Wilson loops of a dual gauge field” in an ordinary weakly coupled local Lagrangian. Sometimes there is such a dual description; usually there is not.

## Non-Abelian magnetic charge

For a compact non-Abelian group $G$, choose a maximal torus and write the magnetic charge as a Cartan element $B$. Around the defect, the gauge field has a Dirac-monopole-like singularity embedded along $B$.

Two restrictions matter.

First, $B$ is defined modulo Weyl transformations. Different Cartan elements related by a Weyl reflection describe the same magnetic charge after a gauge transformation.

Second, $B$ must satisfy a global quantization condition. If a field of weight $\lambda$ is transported around the Dirac string, it should return single-valued:

$$
e^{2\pi i\lambda(B)}=1.
$$

Thus $B$ belongs to a lattice determined by the allowed electric representations. This is where the global form of the gauge group enters.

For example, saying only that the Lie algebra is $\mathfrak{su}(N)$ is not enough. The theories with gauge group $SU(N)$ and $PSU(N)=SU(N)/\mathbb Z_N$ have the same local gauge bosons but different genuine line operators. Fundamental Wilson loops are genuine in $SU(N)$ gauge theory but not in pure $PSU(N)$ gauge theory unless supplemented by additional topological data. Conversely, the magnetic line spectrum changes.

That statement sounds like a technicality until one studies confinement. Then it becomes impossible to ignore. Line operators remember the global form.

## The Wilson–’t Hooft linking algebra

The simplest physical distinction between Wilson and ’t Hooft loops appears when they link.

Let $C_e$ be an electric loop and $C_m$ a magnetic loop. If $C_e$ links $C_m$, the electric probe detects the singular gauge transformation of the magnetic defect. In many $SU(N)$-type examples, the result is a center phase:

$$
T_m(C_m)W_R(C_e)
=
\zeta_R(m)^{L(C_e,C_m)}W_R(C_e)T_m(C_m),
$$

where $L(C_e,C_m)$ is the linking number and $\zeta_R(m)$ is the phase by which the relevant center element acts in representation $R$.

For $SU(N)$, a representation $R$ has $N$-ality $k_R$. A minimal magnetic loop labeled by $m\in\mathbb Z_N$ gives the phase

$$
\zeta_R(m)=\exp\left(\frac{2\pi i\,m k_R}{N}\right).
$$

Thus a fundamental Wilson loop, with $k_R=1$, linked once with a minimal magnetic loop gets the phase

$$
e^{2\pi i/N}.
$$

This algebra is the line-operator analogue of canonical commutation relations. It says electric and magnetic probes cannot always be simultaneously trivialized. Their mutual topology is measurable.

## Order and disorder operators

The Wilson loop is often called an order operator, and the ’t Hooft loop a disorder operator. The terminology comes from statistical mechanics, where an order operator measures the local order parameter while a disorder operator creates a branch cut, vortex, or defect.

In gauge theory:

| Operator | What it inserts | What it probes |
|---|---|---|
| Wilson loop $W_R(C)$ | External electric charge worldline | Electric flux and screening of representation $R$ |
| ’t Hooft loop $T_B(C)$ | External magnetic charge worldline | Magnetic flux and screening of magnetic charge $B$ |
| Wilson–’t Hooft loop | Dyonic external charge | Oblique confinement and mixed electric-magnetic phases |

This is not just vocabulary. Different phases can make electric probes costly while magnetic probes are screened, or the other way around.

## Phase diagnostics

The classic phase diagnosis compares the large-loop behavior of Wilson and ’t Hooft loops. Schematically:

| Phase | Wilson loop | ’t Hooft loop | Cartoon |
|---|---|---|---|
| Coulomb | Coulombic behavior, not pure area law | Coulombic behavior, not pure area law | Massless gauge field; long-range electric and magnetic fields. |
| Confining | Area law for unscreened electric probes | Perimeter law for corresponding magnetic probes | Electric flux tubes; magnetic objects effectively condensed. |
| Higgs | Perimeter law for screened electric probes | Area law for magnetic probes | Electric condensate squeezes magnetic flux. |
| Oblique confinement | Area law for some dyonic loop | Complementary dyonic loops may be screened | Condensed dyons rather than pure magnetic objects. |

This table is a map, not a theorem applying blindly to every theory. Matter content, dimensions, global form, discrete theta terms, and the spectrum of genuine line operators can change the precise statements.

The basic lesson is robust: to diagnose a gauge-theory phase, ask not only what electric probes do, but also what magnetic and dyonic probes do.

## A path-integral definition

A Wilson loop can be inserted into the path integral by multiplying the integrand by $W_R(C)$. A ’t Hooft loop changes the integration domain:

$$
\langle T_B(C)\mathcal O\rangle
=
\frac{1}{Z}\int_{\text{fields with magnetic singularity }B\text{ along }C}\mathcal D A\,\mathcal O[A]e^{-S_E[A]}.
$$

This definition makes three things clear.

First, $T_B(C)$ is nonlocal. The operator is supported on a curve, but its definition constrains fields in a punctured neighborhood of the curve.

Second, renormalization is required. The singularity near $C$ contributes local defect counterterms, much as a Wilson line has a static-source self-energy.

Third, the definition is intrinsically nonperturbative. Around a magnetic defect, one generally cannot expand globally around a smooth $A_\mu=0$ configuration. This is one reason ’t Hooft loops are better thought of as disorder operators than as ordinary composite operators.

## Relation to center one-form symmetry

In pure $SU(N)$ Yang–Mills theory, Wilson loops with nonzero $N$-ality are charged under the electric $\mathbb Z_N$ one-form symmetry. The charge operator is supported on a codimension-two surface and links the Wilson loop.

A ’t Hooft loop can be viewed as a magnetic line operator whose linking with Wilson loops measures this center charge. In modern language, line operators are charged objects for generalized global symmetries, and topological symmetry operators act by linking.

This viewpoint clarifies why dynamical fundamental matter changes the story. Fundamental matter explicitly breaks the electric center one-form symmetry, because a fundamental Wilson line can end on a dynamical fundamental particle. Once it can end, it is no longer a conserved line charge. The large Wilson loop may cross over from an area law to a perimeter law through string breaking.

## What changes with dynamical matter

With dynamical matter, neither Wilson nor ’t Hooft loops should be interpreted too quickly.

If the theory contains dynamical electrically charged fields, an external electric probe can be screened. A Wilson loop that had an area law in the pure gauge theory may eventually show a perimeter law at very large distances.

If the theory contains dynamical magnetically charged objects, a magnetic probe can be screened. Then the ’t Hooft loop may show a perimeter law.

If the theory contains dyons, the screened operators may be Wilson–’t Hooft loops rather than purely electric or purely magnetic loops. This is the origin of **oblique confinement**: the condensed object has both electric and magnetic charge, so the area-law diagnostic selects a different lattice of line operators.

The moral is delightfully inconvenient: “the Wilson loop” is not a universal confinement detector. The full line-operator lattice is the better object.

## Common pitfalls

**Pitfall 1: trying to write a ’t Hooft loop as an ordinary trace of $A_\mu$.** A ’t Hooft loop is a disorder operator. It changes boundary conditions by inserting magnetic flux.

**Pitfall 2: ignoring Dirac quantization.** Magnetic charges are not arbitrary Lie-algebra elements. They live on a lattice fixed by the allowed electric charges and global form of the gauge group.

**Pitfall 3: saying $SU(N)$ and $PSU(N)$ are the same gauge theory.** They have the same Lie algebra, but not the same genuine Wilson and ’t Hooft line operators.

**Pitfall 4: thinking Wilson and ’t Hooft loops always commute.** Linked electric and magnetic loops can differ by a center phase. This linking algebra is one of their main uses.

**Pitfall 5: treating “Higgs” and “confining” as always sharply distinct.** In theories with matter in certain representations, there may be no gauge-invariant local order parameter distinguishing them. Line operators still reveal useful screening behavior, but the phase diagram can be subtler than the cartoon.

**Pitfall 6: assuming magnetic duality is always weakly coupled.** Abelian Maxwell theory makes electric-magnetic duality look easy. Non-Abelian duality is far richer and usually not available as a simple local weakly coupled gauge field.

## Relations to other pages

[Wilson Loops](/gauge-theories-standard-model/wilson-loops-confinement/wilson-loops/) defines electric line operators and the static-potential diagnostic. This page adds the magnetic line operators needed for a complete phase vocabulary.

[Global Form and Center](/gauge-theories-standard-model/yang-mills/global-form-and-center/) explains why global form changes the line-operator spectrum.

[Area Law and Perimeter Law](/gauge-theories-standard-model/wilson-loops-confinement/area-law-and-perimeter-law/) compares the asymptotic behaviors used to interpret both Wilson and ’t Hooft loops.

The later page on Center Symmetry and Confinement will make the one-form symmetry interpretation more systematic.

## Research status

The definition of ’t Hooft loops as magnetic disorder operators, their Dirac quantization, and their use as phase diagnostics are standard.

The refined classification of line operators is more delicate. It depends on the global form of the gauge group, possible discrete theta angles, allowed matter representations, and the chosen lattice of mutually local Wilson–’t Hooft charges. This line-operator viewpoint became especially central in modern treatments of higher-form symmetries and duality.

The nonperturbative expectation values of ’t Hooft loops are hard in generic four-dimensional gauge theories. Supersymmetric localization can compute certain protected ’t Hooft loop observables in special theories, while lattice and semiclassical methods give other windows. Ordinary QCD-like theories remain mostly outside exact analytic control.

## Exercises

### Exercise 1: Dirac quantization from single-valuedness

In $U(1)$ gauge theory, let a Wilson loop have electric charge $q\in\mathbb Z$ in units of the minimal electric charge. Let a ’t Hooft loop have magnetic charge $m$. Explain why transporting the electric probe around the Dirac string requires $qm\in\mathbb Z$.

<details><summary><strong>Solution</strong></summary>

The magnetic defect can be described using gauge potentials that differ across a Dirac string by a gauge transformation. An electric probe of charge $q$ picks up a phase under this gauge transformation. If the magnetic flux is normalized by $m$, the phase is

$$
e^{2\pi i q m}.
$$

The Dirac string is not physical, so this phase must be one for every allowed electric charge. Therefore

$$
qm\in\mathbb Z.
$$

When $q=1$ is allowed, $m$ must be an integer in this normalization.

</details>

### Exercise 2: Center phase for linked loops

For an $SU(N)$-type theory, suppose a Wilson loop in representation $R$ has $N$-ality $k_R$, and a magnetic loop has charge $m\in\mathbb Z_N$. What phase appears when the two loops link once?

<details><summary><strong>Solution</strong></summary>

The linked loops obey the algebra

$$
T_m(C_m)W_R(C_e)=\zeta_R(m)W_R(C_e)T_m(C_m)
$$

for linking number one. The center phase is

$$
\zeta_R(m)=\exp\left(\frac{2\pi i m k_R}{N}\right).
$$

For the fundamental representation, $k_R=1$, so the phase is $e^{2\pi i m/N}$.

</details>

### Exercise 3: Which loop has the area law?

Use the electric-magnetic language to explain why a confining phase is often summarized as “Wilson area, ’t Hooft perimeter,” while a Higgs phase is summarized as “Wilson perimeter, ’t Hooft area.”

<details><summary><strong>Solution</strong></summary>

In a confining phase, external electric charges are joined by an electric flux tube. The energy of the flux tube grows with separation, so a large Wilson loop has an area law. Magnetic probes, by contrast, are screened in the dual-superconductor cartoon, so the ’t Hooft loop has a perimeter law.

In a Higgs phase, dynamical electrically charged fields condense. External electric charges are screened, so Wilson loops have perimeter behavior. Magnetic flux is squeezed into tubes, so magnetic probes can have an area law, giving the ’t Hooft loop the complementary behavior.

This is a useful cartoon, but the precise statement depends on matter content and the line-operator spectrum.

</details>

### Exercise 4: Why global form matters

Explain why two gauge theories with the same Lie algebra can have different ’t Hooft loop spectra.

<details><summary><strong>Solution</strong></summary>

The local gauge bosons depend on the Lie algebra, but genuine line operators depend on the global form of the gauge group. Magnetic charges are cocharacters of the gauge group, subject to Dirac quantization with the allowed electric charges. Changing the global form changes the allowed electric representations and therefore changes the dual magnetic lattice.

Thus $SU(N)$ and $PSU(N)$ have the same local Lie algebra $\mathfrak{su}(N)$ but different Wilson and ’t Hooft line spectra.

</details>

## References

### Standard first pass

- Polyakov, *Gauge Fields and Strings*, Chs. 5 and 7, for confinement criteria, phase factors, and loop dynamics.
- Srednicki, *Quantum Field Theory*, §82, for Wilson loops, lattice gauge theory, and confinement diagnostics.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry” and “Classical Lumps,” for gauge fields, magnetic monopoles, and the physical role of topological defects.

### Deeper references

- ’t Hooft, “On the Phase Transition Towards Permanent Quark Confinement,” for the classic Wilson–’t Hooft loop phase-diagnostic viewpoint.
- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for the modern higher-form symmetry treatment of line operators.
- Aharony, Seiberg, and Tachikawa, “Reading Between the Lines of Four-Dimensional Gauge Theories,” for line-operator lattices, global form, and discrete theta data.
- Kapustin, “Wilson–’t Hooft Operators in Four-Dimensional Gauge Theories and S-Duality,” for the classification of Wilson–’t Hooft charges and duality.

## Version history

- **2026-06-18:** Initial polished draft. Added magnetic disorder definition, Dirac quantization, non-Abelian magnetic charges, Wilson–’t Hooft linking algebra, phase diagnostics, and exercises.
