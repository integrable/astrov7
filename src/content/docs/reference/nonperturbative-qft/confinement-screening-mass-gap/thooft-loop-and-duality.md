---
title: "’t Hooft Loop and Duality"
description: "Explains ’t Hooft loops as magnetic disorder lines, their Wilson–’t Hooft algebra, and their role in electric–magnetic duality and confinement diagnostics."
sidebar:
  label: "’t Hooft Loop and Duality"
  order: 10
level: Advanced
status: "Polished draft"
source: "’t Hooft; Srednicki, ch. 82; Shifman, chs. 1 and 9; Gaiotto–Kapustin–Seiberg–Willett."
topics:
  - "’t Hooft loops"
  - Wilson loops
  - electric-magnetic duality
  - magnetic disorder operators
  - oblique confinement
  - one-form symmetry
  - line operators
canonicalTopics:
  - nonperturbative-qft
  - confinement
  - thooft-loops
  - electric-magnetic-duality
  - line-operators
  - one-form-symmetry
researchStatus:
  established:
    - "’t Hooft loops are standard magnetic disorder line operators, complementary to Wilson loops, and are central to the Wilson–’t Hooft classification of gauge-theory phases."
  active:
    - "A complete phase classification of arbitrary non-Abelian gauge theories requires global form, matter content, discrete theta angles, anomalies, and the full lattice of genuine Wilson–’t Hooft lines."
---

## Summary

A **Wilson loop** inserts an external electric probe. An **’t Hooft loop** inserts an external magnetic probe. The Wilson loop is built from the gauge connection along a curve; the ’t Hooft loop is usually defined by a prescribed magnetic singularity, a twisted boundary condition, or a codimension-two disorder operation along a curve.

The slogan is useful:

$$
\text{Wilson loop: electric line},
\qquad
\text{’t Hooft loop: magnetic line}.
$$

But the real content is the mutual nonlocality. In a theory with a $\mathbb Z_N$ electric–magnetic pairing, a minimal Wilson loop $W(C')$ and a minimal ’t Hooft loop $T(C)$ obey the linking algebra

$$
T(C)W(C')
=e^{2\pi i\operatorname{Lk}(C,C')/N}W(C')T(C).
$$

That phase is the diagnostic heartbeat of electric–magnetic duality. It says that electric and magnetic line operators cannot all be ordinary mutually local probes at once.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Electric and magnetic line operators, their linking algebra, and the way electric-magnetic duality rotates Wilson and ’t Hooft loops.](/figures/nonperturbative-qft/thooft-loop-duality-map.svg)

<figcaption>

An ’t Hooft loop is a magnetic disorder line. Its defining property is not that it is a Wilson loop in disguise, but that it has a prescribed linking phase with electric Wilson loops. Electric–magnetic duality rotates the lattice of line charges and can exchange Wilson and ’t Hooft descriptions of the same physics.

</figcaption>
</figure>

In a confining phase, suitable electric Wilson loops have area law and suitable magnetic ’t Hooft loops have perimeter law. In a Higgs phase, the roles are reversed. In a Coulomb phase, both show long-range Coulomb behavior. In an oblique-confining phase, the perimeter-law line is dyonic rather than purely electric or purely magnetic.

## Prerequisites

Read [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/), [Perimeter Law and Screening](/nonperturbative-qft/confinement-screening-mass-gap/perimeter-law-and-screening/), [Center Symmetry](/nonperturbative-qft/confinement-screening-mass-gap/center-symmetry/), and [One-Form Symmetry and Confinement](/nonperturbative-qft/confinement-screening-mass-gap/one-form-symmetry-confinement/) first. The short diagnostic companion page is [’t Hooft-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/thooft-loop-diagnostics/).

You should also know the idea of a disorder parameter from [Disorder Parameters](/nonperturbative-qft/order-parameters-diagnostics/disorder-parameters/) and the role of finite-energy boundary data from [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/).

## Core idea

A Wilson loop is defined by parallel transport:

$$
W_R(C)=\operatorname{tr}_R\,\mathcal P\exp\left(i\oint_C A\right).
$$

It is an electric probe because a heavy charged particle moving along $C$ contributes exactly such a holonomy to the path integral.

An ’t Hooft loop is different. It is not usually built by tracing $A$ around $C$. Instead, it changes the allowed gauge-field configurations near $C$. On a small two-sphere or two-disk linking the loop, the gauge field has a prescribed magnetic flux. In words,

$$
\text{insert }T_m(C)
\quad\Longleftrightarrow\quad
\text{sum over fields with magnetic charge }m\text{ around }C.
$$

The label $m$ belongs to the allowed magnetic-charge lattice of the theory. Which $m$ are allowed depends on the global form of the gauge group, the matter content, and the choice of genuine line operators.

This is why ’t Hooft loops are a natural nonperturbative diagnostic. They ask what the vacuum does to external magnetic probes, just as Wilson loops ask what the vacuum does to external electric probes.

## Disorder definition

The cleanest local definition is by a singularity transverse to the loop. Let $C$ be a line in four-dimensional Euclidean spacetime. Around a small circle linking $C$, choose angular coordinate $\varphi$. A magnetic line labeled by a cocharacter $m$ has local behavior schematically like

$$
A\sim m\,d\varphi
$$

up to normalization and gauge conventions. Equivalently, the field strength has magnetic flux through a small two-sphere linking the line.

For a non-Abelian theory, $m$ is not just a number. It is a homomorphism

$$
U(1)\to G
$$

up to Weyl equivalence, or more precisely a point in the appropriate magnetic charge lattice. Dirac quantization requires that all genuine electric lines have integral pairing with all genuine magnetic lines.

On a lattice, the same idea often appears as a magnetic twist sheet. One modifies plaquettes on a surface $\Sigma$ whose boundary is the loop $C$:

$$
\partial\Sigma=C.
$$

Moving the sheet without moving its boundary should not change physics, except when the sheet crosses an electric line. Thus the memorable definition is

$$
\text{an ’t Hooft loop is the boundary of a magnetic twist sheet.}
$$

The sheet is auxiliary. The boundary is the line operator. Its effect is detected by linking with Wilson loops.

## Wilson–’t Hooft algebra

Let $W_e(C')$ be an electric Wilson line with charge $e$, and let $T_m(C)$ be a magnetic ’t Hooft line with charge $m$. Their defining algebra is

$$
T_m(C)W_e(C')
=\exp\left(2\pi i\,\langle e,m\rangle\operatorname{Lk}(C,C')\right)
W_e(C')T_m(C).
$$

Here $\langle e,m\rangle$ is the electric–magnetic pairing and $\operatorname{Lk}(C,C')$ is the linking number. In a simple $\mathbb Z_N$ center example,

$$
\langle e,m\rangle=\frac{em}{N}\pmod{1}.
$$

For a fundamental Wilson loop and a minimal magnetic loop, this gives

$$
T(C)W(C')
=e^{2\pi i\operatorname{Lk}(C,C')/N}W(C')T(C).
$$

This algebra is the loop-operator analog of canonical commutation. It is topological because only the linking number matters, not the metric details of the curves.

The algebra also shows why global form matters. If a proposed set of line operators contains mutually nonlocal lines, they cannot all be genuine in the same four-dimensional theory without extra attached surfaces or other data.

## Global form and genuine lines

The local gauge algebra does not determine the full set of line operators. Gauge theories with the same Lie algebra can differ by global form and discrete theta angle.

For example, theories with Lie algebra $\mathfrak{su}(N)$ include different choices such as

$$
SU(N),
\qquad
PSU(N)=SU(N)/\mathbb Z_N,
$$

and, for quotient groups, possible discrete theta-angle choices. These theories have the same local gluons but different genuine electric and magnetic lines.

A useful rough guide is:

| Theory data | Typical line consequence |
|---|---|
| $SU(N)$ pure gauge theory | Fundamental Wilson lines are genuine; minimal magnetic lines may require extra surface data. |
| $PSU(N)$ pure gauge theory | The fundamental Wilson line is not genuine; magnetic lines become part of the genuine spectrum. |
| Dynamical fundamental matter | Fundamental Wilson lines can end on matter worldlines; electric center one-form symmetry is explicitly broken. |
| Discrete theta angle | The allowed dyonic line lattice changes. |

The safe workflow is therefore:

1. Specify the gauge algebra.
2. Specify the global form of the gauge group.
3. Specify dynamical matter representations.
4. Specify discrete theta-angle data, when present.
5. Determine the genuine line-operator lattice.
6. Only then interpret area and perimeter laws.

Skipping these steps is a surprisingly efficient machine for producing almost-correct statements.

## Electric–magnetic duality

Electric–magnetic duality says that two descriptions of the same long-distance physics can exchange electric and magnetic variables. In an Abelian Maxwell theory without dynamical charges, the equations of motion and Bianchi identity are exchanged by

$$
F\longleftrightarrow \widetilde F.
$$

At the level of line charges, an $S$-duality transformation acts schematically as

$$
(e,m)\longmapsto (m,-e).
$$

Thus a Wilson line in one description can become an ’t Hooft line in a dual description, and a general Wilson–’t Hooft line can rotate to another dyonic line.

In non-Abelian gauge theory, this statement becomes much subtler. The duality may require a different gauge group, different global form, different coupling, supersymmetry, or extra matter. But the principle survives:

$$
\text{gauge redundancies may look different in dual frames,}
\qquad
\text{global symmetries and genuine line operators must match.}
$$

This is one reason the Wilson–’t Hooft algebra is so useful. It gives a representation-independent diagnostic of what duality must preserve.

## Loop laws and phases

Wilson and ’t Hooft proposed a phase diagnostic based on the large-loop behavior of electric and magnetic probes.

For a large loop $C$,

$$
\langle W(C)\rangle\sim e^{-\sigma A(C)}
$$

is an electric area law, while

$$
\langle T(C)\rangle\sim e^{-\widetilde\sigma A(C)}
$$

is a magnetic area law. Perimeter behavior means

$$
\langle W(C)\rangle\sim e^{-\mu P(C)},
\qquad
\langle T(C)\rangle\sim e^{-\widetilde\mu P(C)},
$$

after local line renormalization. Coulomb behavior includes long-range power-law or logarithmic effects rather than purely area or perimeter behavior.

The classic table is:

| Phase language | Wilson loop | ’t Hooft loop | Intuition |
|---|---|---|---|
| Confining phase | area | perimeter | Electric flux forms strings; magnetic probes are not confined. |
| Higgs phase | perimeter | area | Electric charge is screened; magnetic flux forms vortices. |
| Coulomb phase | Coulomb | Coulomb | Both electric and magnetic fields have long-range photons. |
| Oblique confinement | depends on dyonic charge | depends on dyonic charge | Condensed objects carry both electric and magnetic charge. |

The table is not a substitute for specifying the theory. It assumes the relevant lines are genuine and not explicitly broken by dynamical matter. It is best understood as a diagnostic template.

## Dual superconductivity

The ’t Hooft loop is the natural language for the **dual superconductor** picture of confinement.

In an ordinary superconductor, electric charges condense. Magnetic flux is squeezed into Abrikosov vortex tubes. A magnetic probe is confined by a flux tube, so an appropriate ’t Hooft loop has area law.

In a dual superconductor, magnetic objects condense. Electric flux is squeezed into tubes. An electric probe is confined, so an appropriate Wilson loop has area law.

The analogy is:

| Condensate | Confined flux | Area-law line |
|---|---|---|
| Electric condensate | Magnetic flux | ’t Hooft loop |
| Magnetic condensate | Electric flux | Wilson loop |
| Dyonic condensate | Mutually nonlocal dyonic flux | Dyonic Wilson–’t Hooft line |

This picture is powerful, but it has a trap. A condensate of a gauge-charged object is not automatically a gauge-invariant local order parameter. The safer gauge-invariant claims involve line-operator behavior, one-form symmetry realization, and the spectrum.

The Seiberg–Witten solution gives controlled examples where monopoles or dyons condense and electric confinement can be shown in a weakly coupled dual description. Ordinary four-dimensional nonsupersymmetric QCD is not analytically solved this way. The dual-superconductor picture is influential and physically suggestive, but a complete analytic derivation of QCD confinement remains out of reach.

## Oblique confinement and dyonic lines

A purely magnetic condensate confines electric charges. A dyonic condensate can confine a different set of probes. This is **oblique confinement**.

Suppose the condensed object has charge vector

$$
(e_c,m_c).
$$

A line of charge $(e,m)$ is mutually local with the condensate if its electric–magnetic pairing with $(e_c,m_c)$ vanishes modulo integers. Lines mutually local with the condensate can have perimeter behavior; mutually nonlocal lines tend to have area behavior.

Thus the clean statement is not “Wilson area, ’t Hooft perimeter” or the reverse. The clean statement is:

$$
\text{the perimeter-law line is the one compatible with the condensed charge lattice.}
$$

In an oblique phase, that line is dyonic. The purely electric Wilson loop and purely magnetic ’t Hooft loop may both fail to be the simplest diagnostic.

This is one reason modern treatments prefer the full lattice of Wilson–’t Hooft lines and one-form symmetries. They remember information that the old phase labels compress too aggressively.

## Relation to one-form symmetry

Wilson loops are charged under electric one-form symmetries. ’t Hooft loops are charged under magnetic one-form symmetries, when such symmetries exist.

For a compact $U(1)$ gauge theory with no dynamical electric charges and no monopoles, there are two continuous one-form symmetries:

$$
U(1)^{(1)}_e,
\qquad
U(1)^{(1)}_m.
$$

Wilson loops are charged under the electric one-form symmetry. ’t Hooft loops are charged under the magnetic one-form symmetry. Adding dynamical electric charges explicitly breaks the electric one-form symmetry; adding monopoles explicitly breaks the magnetic one-form symmetry.

In non-Abelian theories, the electric center one-form symmetry and the magnetic one-form symmetry depend on global form. For example, $SU(N)$ and $PSU(N)$ theories have different genuine line operators and different one-form symmetry descriptions.

The generalized-symmetry rule for loop laws is:

| One-form symmetry realization | Charged line behavior |
|---|---|
| Unbroken | area law in a gapped phase. |
| Broken | perimeter law or Coulomb behavior. |
| Broken to subgroup | lines charged under the unbroken subgroup have area law. |

Electric–magnetic duality can exchange which symmetry is called electric and which is called magnetic, but it cannot change the underlying line algebra.

## Finite temperature and magnetic loops

At finite temperature, wrapping electric Wilson lines around the Euclidean time circle gives Polyakov loops, as explained in [Polyakov Loop and Deconfinement](/nonperturbative-qft/confinement-screening-mass-gap/polyakov-loop-and-deconfinement/). Magnetic line operators have analogous thermal uses, but the interpretation is more theory-dependent.

In pure gauge theory, spatial ’t Hooft loops can diagnose interfaces between center-related deconfined vacua. In a high-temperature center-broken phase, the insertion of a spatial magnetic disorder loop can force a discontinuity in the Polyakov-loop phase across a surface. The corresponding area coefficient is often called a dual string tension or an interface tension, depending on the precise setup.

This is useful but subtle. The thermal Polyakov loop has a simple order-parameter role in pure gauge theory because it is a wrapped electric line charged under center symmetry. A thermal ’t Hooft loop depends more sensitively on which magnetic lines are genuine, what global form is chosen, and which spatial or temporal orientation is used.

## Common pitfalls

**Pitfall: defining an ’t Hooft loop as a Wilson loop of a dual photon.** That is sometimes possible in a weakly coupled Abelian dual frame. The general definition is a magnetic disorder line or bundle modification, not a trace of a dual gauge field.

**Pitfall: ignoring the global form.** The Lie algebra alone does not determine the genuine magnetic lines. $SU(N)$ and $PSU(N)$ theories have the same local gluons but different line spectra.

**Pitfall: treating the twist sheet as physical.** The auxiliary sheet used to define a disorder loop should be deformable. Its boundary is the operator; its intersection with electric lines gives the observable linking phase.

**Pitfall: taking the Wilson–’t Hooft table too literally.** The simple confinement/Higgs/Coulomb table assumes a suitable theory with suitable genuine lines. Dynamical matter, discrete theta angles, and oblique phases require the full line lattice.

**Pitfall: saying a gauge symmetry is broken because an ’t Hooft loop has perimeter law.** Gauge redundancy is not an ordinary symmetry. The gauge-invariant statement concerns line operators and global one-form symmetry realization.

## Relations to other pages

[Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/) gives the electric half of the Wilson–’t Hooft pair.

[One-Form Symmetry and Confinement](/nonperturbative-qft/confinement-screening-mass-gap/one-form-symmetry-confinement/) gives the modern symmetry language for area and perimeter laws.

[Center Symmetry](/nonperturbative-qft/confinement-screening-mass-gap/center-symmetry/) explains the electric center charge whose magnetic dual depends on global form.

[Polyakov Loop and Deconfinement](/nonperturbative-qft/confinement-screening-mass-gap/polyakov-loop-and-deconfinement/) treats the thermal wrapped Wilson line; this page treats the magnetic line and its duality role.

[Disorder Parameters](/nonperturbative-qft/order-parameters-diagnostics/disorder-parameters/) gives the broader logic of operators defined by twists and singularities.

[Compact QED in Three Dimensions](/nonperturbative-qft/confinement-screening-mass-gap/compact-qed-three-dimensions/) gives a concrete Abelian model where magnetic monopole events disorder electric Wilson loops and generate confinement. [Higgs versus Confinement](/nonperturbative-qft/confinement-screening-mass-gap/higgs-versus-confinement/) uses the same Wilson–’t Hooft logic to explain why Higgs and confinement can be sharply distinct or smoothly connected depending on matter and global form.

## Research status

The existence and diagnostic role of ’t Hooft loops are textbook-standard. The Wilson–’t Hooft algebra, electric–magnetic pairing, and area/perimeter/Coulomb phase diagnostics are established tools in continuum and lattice gauge theory.

The active part is not the basic definition; it is the classification problem. For a general quantum field theory, one must specify global form, matter content, discrete theta angles, anomalies, boundary conditions, and the full lattice of genuine line operators. Modern generalized-symmetry language has made this problem much sharper, but many strongly coupled nonsupersymmetric theories still lack a complete analytic phase description.

## Exercises

### Exercise 1: Linking phase in a center theory

In a theory with $\mathbb Z_N$ electric–magnetic pairing, let $W_e(C')$ and $T_m(C)$ have charges $e,m\in\mathbb Z_N$. Write the phase obtained when $C$ and $C'$ link once.

<details>
<summary><strong>Solution</strong></summary>

The Wilson–’t Hooft algebra gives

$$
T_m(C)W_e(C')
=\exp\left(\frac{2\pi iem}{N}\operatorname{Lk}(C,C')\right)
W_e(C')T_m(C).
$$

If $\operatorname{Lk}(C,C')=1$, the phase is

$$
\exp\left(\frac{2\pi iem}{N}\right).
$$

For $e=m=1$, this is $e^{2\pi i/N}$.

</details>

### Exercise 2: Duality rotation of charges

Suppose an $S$-duality transformation acts on charge vectors by

$$
(e,m)\mapsto(m,-e).
$$

What happens to a pure Wilson line $(e,0)$? What happens to a pure ’t Hooft line $(0,m)$?

<details>
<summary><strong>Solution</strong></summary>

A pure Wilson line has charge $(e,0)$. Under the transformation,

$$
(e,0)\mapsto(0,-e),
$$

so it becomes a magnetic line, up to orientation or charge conjugation.

A pure ’t Hooft line has charge $(0,m)$. It maps to

$$
(0,m)\mapsto(m,0),
$$

so it becomes a Wilson line. This is the simplest charge-lattice expression of electric–magnetic exchange.

</details>

### Exercise 3: Identify the phase from loop laws

Suppose a four-dimensional gauge theory has suitable genuine Wilson and ’t Hooft loops with

$$
\langle W(C)\rangle\sim e^{-\mu P(C)},
\qquad
\langle T(C)\rangle\sim e^{-\widetilde\sigma A(C)}.
$$

Which entry of the Wilson–’t Hooft phase table does this resemble?

<details>
<summary><strong>Solution</strong></summary>

The Wilson loop has perimeter law, while the ’t Hooft loop has area law. This is the Higgs pattern: electric charges are screened, while magnetic flux is confined into tubes.

The answer assumes the relevant Wilson and ’t Hooft loops are genuine and not explicitly broken by dynamical matter. Without that information, the table is only a guide.

</details>

### Exercise 4: Why the global form matters

Explain why an $SU(N)$ theory and a $PSU(N)$ theory can have the same local gluons but different ’t Hooft-loop spectra.

<details>
<summary><strong>Solution</strong></summary>

The local gluons are determined by the Lie algebra $\mathfrak{su}(N)$, which is the same for $SU(N)$ and $PSU(N)$. Line operators, however, are sensitive to the global form of the gauge group.

The electric weight lattice and magnetic cocharacter lattice depend on the global group, not only on the algebra. In an $SU(N)$ theory, fundamental Wilson lines can be genuine. In a $PSU(N)$ theory, the fundamental Wilson line is not a genuine line of the same kind, while magnetic lines that were not genuine in the $SU(N)$ description may become genuine. Thus the ’t Hooft-loop spectrum changes even though the local gluons are the same.

</details>

## References

### Standard first pass

- G. ’t Hooft, original papers on magnetic disorder operators and the Wilson–’t Hooft classification of phases.
- M. Srednicki, *Quantum Field Theory*, especially the chapter on Wilson loops, lattice theory, and confinement.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapters on phases of gauge theories, vortices, monopoles, confinement, and the dual Meissner effect.

### Deeper references

- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the modern one-form symmetry and genuine-line-operator framework.
- J. Greensite, *An Introduction to the Confinement Problem*, for confinement diagnostics involving Wilson loops, ’t Hooft loops, center symmetry, and lattice gauge theory.
- N. Seiberg and E. Witten, papers on electric–magnetic duality and monopole condensation in supersymmetric gauge theory, for controlled realizations of the dual-superconductor mechanism.

## Version history

- **2026-06-27:** Initial polished page on ’t Hooft loops, Wilson–’t Hooft algebra, duality, global form, and phase diagnostics.
- **2026-06-27:** Linked Compact QED in Three Dimensions as a concrete monopole-disorder confinement mechanism.
