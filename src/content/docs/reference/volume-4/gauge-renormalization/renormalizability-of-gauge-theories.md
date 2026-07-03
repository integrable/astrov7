---
title: "Renormalizability of Gauge Theories"
description: "Explains why four-dimensional gauge theories are perturbatively renormalizable when locality, power counting, BRST symmetry, and anomaly cancellation work together."
sidebar:
  label: "Renormalizability of Gauge Theories"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §§69–75, 78; Weinberg Vol. II Chs. 15 and 17; Coleman lectures on renormalization and gauge-field Feynman rules; Schwartz Chs. 21, 25–26."
topics:
  - gauge-theory renormalizability
  - BRST symmetry
  - Slavnov–Taylor identities
  - counterterms
  - power counting
  - anomaly cancellation
canonicalTopics:
  - gauge-theory-renormalizability
  - brst-consistency
  - slavnov-taylor-identities
  - gauge-invariant-counterterms
  - anomaly-cancellation
researchStatus:
  established:
    - "Perturbative renormalizability of anomaly-free four-dimensional Yang–Mills theories with renormalizable matter interactions is a standard structural result of quantum field theory."
  active:
    - "Nonperturbative definitions of chiral gauge theories, gauge theories near conformal windows, and gauge-theory EFTs remain active research areas beyond the first-pass perturbative theorem."
---

## Summary

Gauge theories are renormalizable for a deeper reason than “the coupling has dimension zero.” Power counting says which divergences are possible, but gauge symmetry says how they must fit together.

A massless spin-one field has too many components if treated as an ordinary vector field. Gauge redundancy removes the unphysical components. After gauge fixing, BRST symmetry remembers that removal and forces the quantum theory to preserve the same physical degrees of freedom. The renormalizability statement is therefore not just about dimensions. It is about the compatibility of four facts:

$$
\text{locality},\qquad
\text{power counting},\qquad
\text{BRST symmetry},\qquad
\text{absence of gauge anomalies}.
$$

Together they imply that ultraviolet divergences can be absorbed into a finite set of local counterterms: field normalizations, couplings, masses, gauge-fixing parameters, and matter-interaction parameters already allowed by the symmetry.

In a slogan,

$$
\boxed{
\text{renormalizable gauge theory}
=
\text{local spin-one QFT whose counterterms respect BRST consistency}.
}
$$

This page explains the structural statement. The next page classifies the counterterms themselves.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Renormalizability of gauge theories follows from locality, power counting, and BRST consistency.](/figures/gauge-theories-standard-model/gauge-renormalizability-filter.svg)

<figcaption>

Gauge-theory renormalizability is a filter, not a miracle. Locality makes ultraviolet divergences local. Power counting restricts candidate counterterms to dimension at most four in four spacetime dimensions. BRST consistency then forces those local terms to combine into gauge-covariant structures plus harmless field redefinitions and gauge-fixing terms.

</figcaption>
</figure>

## Prerequisites

You should know [Gauge Fixing and Faddeev–Popov](/gauge-theories-standard-model/gauge-quantization/gauge-fixing-and-faddeev-popov/), [Ghosts and Gauge-Fixed Action](/gauge-theories-standard-model/gauge-quantization/ghosts-and-gauge-fixed-action/), [BRST Symmetry in Gauge Theory](/gauge-theories-standard-model/gauge-quantization/brst-symmetry-in-gauge-theory/), [Covariant Gauges](/gauge-theories-standard-model/gauge-quantization/covariant-gauges/), and [Background-Field Gauge](/gauge-theories-standard-model/gauge-quantization/background-field-gauge/).

You should also be comfortable with ordinary perturbative renormalization: divergent loop integrals, local counterterms, wavefunction renormalization, coupling renormalization, and the distinction between bare and renormalized parameters.

We use the volume convention

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
[D_\mu,D_\nu]=igF_{\mu\nu}^aT^a,
$$

so

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a
-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

## Core idea

A theory is **perturbatively renormalizable by power counting** if, at every loop order, all ultraviolet divergences can be absorbed into a finite set of local parameters whose operators have mass dimension at most four in four spacetime dimensions. For scalar $\phi^4$ theory this is almost visible from dimensional analysis alone. For gauge theory it is more subtle.

The subtlety is that the fields used in perturbation theory are not all physical. In a covariant gauge, the path integral contains

$$
A_\mu^a,\qquad c^a,\qquad \bar c^a,
$$

and sometimes an auxiliary field $B^a$. The gauge field has longitudinal and timelike components; the ghosts are Grassmann scalar fields; none of this enlarged field space is the physical spectrum. The enlarged description is acceptable only because BRST symmetry pairs unphysical modes and restricts the allowed quantum corrections.

Thus the central question is not merely:

$$
\text{Which divergent diagrams exist?}
$$

It is:

$$
\text{Which divergent local terms are compatible with the quantum gauge symmetry?}
$$

The answer is the heart of gauge-theory renormalization. In an anomaly-free theory, the divergent part of the effective action can be canceled by local counterterms that preserve the Slavnov–Taylor identity. The nontrivial counterterms are gauge-invariant operators. The remaining terms are BRST-exact pieces, field redefinitions, gauge-parameter renormalizations, or source redefinitions.

That is why a Yang–Mills theory is predictive even though individual gauge-fixed diagrams look wildly non-gauge-invariant.

## Setup and conventions

Consider a four-dimensional gauge theory with compact gauge group $G$ and Lie algebra generators $T^a$ satisfying

$$
[T^a,T^b]=if^{abc}T^c.
$$

The gauge field is

$$
A_\mu=A_\mu^aT^a,
$$

and the Yang–Mills Lagrangian is

$$
\mathcal L_{\rm YM}
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
$$

For a matter field $\psi$ in a representation $R$,

$$
D_\mu\psi=(\partial_\mu+igA_\mu^aT_R^a)\psi.
$$

For an adjoint field $X^a$,

$$
(D_\mu X)^a
=
\partial_\mu X^a-gf^{abc}A_\mu^bX^c.
$$

In four dimensions,

$$
[A_\mu]=1,\qquad
[F_{\mu\nu}]=2,\qquad
[\psi]=\frac32,\qquad
[\phi]=1,\qquad
[g]=0.
$$

The ghost fields in a covariant gauge have

$$
[c]=[\bar c]=1.
$$

A typical gauge-fixed Yang–Mills Lagrangian is

$$
\mathcal L
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2
-\bar c^a\partial^\mu D_\mu^{ab}c^b
+\mathcal L_{\rm matter}.
$$

Equivalently, with an auxiliary field $B^a$,

$$
\mathcal L
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
+B^a\partial^\mu A_\mu^a
+\frac{\xi}{2}B^aB^a
-\bar c^a\partial^\mu D_\mu^{ab}c^b
+\mathcal L_{\rm matter}.
$$

The BRST transformations are

$$
sA_\mu^a=(D_\mu c)^a,
\qquad
sc^a=\frac{g}{2}f^{abc}c^bc^c,
\qquad
s\bar c^a=B^a,
\qquad
sB^a=0.
$$

For matter transforming as $\psi\mapsto U^{-1}\psi$,

$$
s\psi=-igc^aT^a\psi.
$$

The gauge-fixed action is BRST invariant:

$$
sS=0.
$$

In perturbation theory this symmetry becomes the Slavnov–Taylor identity for the effective action.

## What renormalizable means here

There are several nearby meanings of “renormalizable.” Mixing them is a dependable way to get lost.

### Power-counting renormalizable

A Lagrangian is power-counting renormalizable in four dimensions if it contains only operators of dimension at most four:

$$
\mathcal L=\sum_{[\mathcal O_i]\leq 4}c_i\mathcal O_i.
$$

The coefficients have nonnegative mass dimension. This condition limits the superficial degree of divergence of graphs. It says that only finitely many operator structures can appear as ultraviolet counterterms.

Power counting alone is not enough for gauge theory, because a random collection of dimension-four vector interactions does not describe a consistent massless spin-one theory.

### Symmetry-renormalizable

A theory is symmetry-renormalizable if its counterterms can be chosen to preserve the symmetries that define the theory. For gauge theory, after gauge fixing, the relevant symmetry is BRST symmetry. In practice this means that the renormalized effective action must obey the Slavnov–Taylor identity order by order.

A counterterm that is allowed by dimension but violates BRST symmetry is not allowed in a gauge theory. For example,

$$
\frac12m_A^2A_\mu^aA^{a\mu}
$$

has dimension two, but it is not a Yang–Mills counterterm for an unbroken gauge theory. It gives the gauge boson a mass and changes the gauge redundancy. It can appear only if the theory has an additional mechanism, such as the Higgs mechanism or a Stueckelberg field, that preserves a gauge-invariant description.

### Perturbatively renormalizable

A theory is perturbatively renormalizable if all divergences in formal loop expansion can be absorbed into redefinitions of finitely many parameters and fields:

$$
A_{0\mu}^a=Z_A^{1/2}A_\mu^a,\qquad
\psi_0=Z_\psi^{1/2}\psi,\qquad
g_0=\mu^\epsilon Z_g g,
$$

with analogous definitions for masses, scalar fields, Yukawa couplings, scalar quartics, and gauge-fixing parameters. Here dimensional regularization in $d=4-2\epsilon$ is implicit.

The bare theory is independent of the renormalization scale $\mu$. The renormalized parameters therefore run with $\mu$.

### Effective-field-theory renormalizable

An EFT with higher-dimensional operators is not power-counting renormalizable in the old sense, but it is still renormalizable order by order in an expansion in $E/\Lambda$. For example,

$$
\frac{c}{\Lambda^2}(D_\mu F^{\mu\nu})^a(D^\rho F_{\rho\nu})^a
$$

requires additional counterterms at higher orders, but the EFT remains predictive once an accuracy target is specified.

This chapter uses “renormalizable gauge theory” in the traditional four-dimensional perturbative sense unless stated otherwise.

## Power counting is necessary but not sufficient

In a generic local theory, the superficial degree of divergence has the schematic form

$$
\omega
=
4L-\sum_{\text{internal lines }I}2I+\sum_{\text{vertices }v}N_{\partial,v},
$$

where $L$ is the number of loops and $N_{\partial,v}$ counts derivatives at a vertex. The exact form depends on field types, but the meaning is simple: in four dimensions, interactions with couplings of nonnegative mass dimension lead to only finitely many superficially divergent local structures.

For Yang–Mills theory the coupling is dimensionless, and every interaction in

$$
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
$$

has dimension four. Expanding $F^2$ gives a kinetic term, a three-gauge-boson vertex, and a four-gauge-boson vertex. The derivative structure is just mild enough for power counting.

But a generic massless vector theory could also contain many dimension-four-looking terms. For instance,

$$
(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu},
\qquad
A_\mu^aA_\nu^bA^{c\mu}A^{d\nu},
$$

with arbitrary coefficients. Power counting does not force these coefficients to be the Yang–Mills ones. Gauge symmetry does.

This is the first major lesson:

$$
\text{dimensionless coupling}
\quad\not\Rightarrow\quad
\text{consistent massless spin-one theory}.
$$

The self-interactions of the gauge bosons must be tied to the same structure constants that define the covariant derivative. Otherwise loop corrections and longitudinal polarizations do not organize into a unitary, predictive theory.

## Why spin-one particles are special

A massless spin-one particle has two physical helicities, but a Lorentz vector $A_\mu$ has four components. Gauge redundancy is the mechanism that lets us write Lorentz-covariant formulas without introducing extra physical particles.

In an Abelian theory,

$$
A_\mu\mapsto A_\mu-\partial_\mu\alpha
$$

removes the unphysical components. In a non-Abelian theory,

$$
A_\mu\mapsto
U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U
$$

does the same, but now the gauge bosons themselves carry gauge charge and interact.

This is why one cannot freely add a mass or arbitrary potential for $A_\mu$. A term like

$$
(A_\mu^aA^{a\mu})^2
$$

is Lorentz invariant and dimension four, but it is not gauge invariant. It treats all components of $A_\mu$ as physical vector components. That is not the theory of massless spin-one particles.

The gauge-invariant kinetic term

$$
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
$$

is special because it packages the correct cubic and quartic interactions together. In components,

$$
F_{\mu\nu}^a
=
(\partial_\mu A_\nu^a-\partial_\nu A_\mu^a)
-gf^{abc}A_\mu^bA_\nu^c.
$$

Squaring this expression gives

$$
\mathcal L_{\rm YM}
=
\mathcal L_{\rm kinetic}
+\mathcal L_{AAA}
+\mathcal L_{AAAA}.
$$

The relative coefficients of these three pieces are fixed. Renormalization is allowed to change the overall normalization and the coupling, but not to split the three-gauge-boson and four-gauge-boson interactions into unrelated independent parameters.

That fixed relation is one of the physical faces of renormalizability.

## Locality of divergences

Perturbative renormalization relies on a local statement: ultraviolet divergences are local. A high loop momentum cannot resolve widely separated external points. The divergent part of an amplitude therefore looks like a polynomial in external momenta, which is the momentum-space form of a local operator.

For an effective action $\Gamma$, the divergent part has the form

$$
\Gamma_{\rm div}
=
\int d^4x\,\mathcal L_{\rm div}(x),
$$

where $\mathcal L_{\rm div}$ is a local expression built from fields and derivatives.

Locality alone still leaves too many terms. The next filters are:

1. Lorentz invariance.
2. Ghost number zero.
3. Power counting.
4. Internal symmetries.
5. BRST consistency.

The first four are familiar. The fifth is the gauge-theory workhorse.

## BRST consistency and the Slavnov–Taylor identity

The classical gauge-fixed action satisfies

$$
sS=0.
$$

In the quantum theory this becomes a Slavnov–Taylor identity for the effective action $\Gamma$,

$$
\mathcal S(\Gamma)=0.
$$

The exact form of $\mathcal S$ depends on sources for BRST variations, but the structural meaning is universal: the effective action must encode BRST invariance.

Suppose the theory has been renormalized through $n-1$ loops. At $n$ loops the divergent part $\Gamma_{\rm div}^{(n)}$ must satisfy the linearized Slavnov–Taylor condition

$$
\mathcal B_{\Gamma_0}\Gamma_{\rm div}^{(n)}=0,
$$

where $\mathcal B_{\Gamma_0}$ is the BRST differential linearized around the classical action. This says that the divergent counterterm is BRST-closed.

Two kinds of BRST-closed local terms appear:

| Type | Meaning | Physical effect |
|---|---|---|
| Nontrivial BRST cohomology | Gauge-invariant local operators, such as $F_{\mu\nu}^aF^{a\mu\nu}$ | Renormalize physical couplings and masses |
| BRST-exact or redundant terms | Gauge-fixing changes, field redefinitions, source redefinitions | Change bookkeeping, not physical observables |

This is the cohomological version of the familiar statement that gauge symmetry restricts counterterms.

The precise theorem requires hypotheses: locality, absence of anomalies, a sensible regulator or subtraction scheme, and the usual perturbative assumptions. For the ordinary gauge theories used in particle physics, these hypotheses are exactly the reason BRST is so central.

## The role of anomalies

Gauge anomalies are not small corrections to gauge theories. They are obstructions to defining the quantum theory.

In BRST language, an anomaly means that the effective action fails to satisfy the Slavnov–Taylor identity:

$$
\mathcal S(\Gamma)=\mathcal A.
$$

The anomaly $\mathcal A$ is a local ghost-number-one functional satisfying a consistency condition. If $\mathcal A$ is BRST-exact, it can be removed by a local counterterm. If it represents a nontrivial BRST cohomology class, it cannot be removed.

An anomalous gauge symmetry cannot be treated as a harmless broken global symmetry. Gauge symmetry is the redundancy that removes unphysical states. If it fails quantum mechanically, the longitudinal modes and ghosts do not cancel correctly, and the theory loses unitarity or consistency.

This is why anomaly cancellation is a structural prerequisite for chiral gauge theories such as the Standard Model.

The statement of this page should therefore always be read as:

$$
\boxed{
\text{Four-dimensional gauge theories are perturbatively renormalizable when the gauge symmetry is anomaly-free.}
}
$$

## General renormalizable gauge-theory Lagrangian

A broad four-dimensional renormalizable gauge theory has the schematic form

$$
\mathcal L
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
+i\bar\psi\gamma^\mu D_\mu\psi
+(D_\mu\phi)^\dagger D^\mu\phi
-\mathcal V(\phi)
-\mathcal L_{\rm Yukawa}
+\mathcal L_{\rm gauge\ fixing}
+\mathcal L_{\rm ghost}.
$$

The scalar potential contains gauge-invariant operators of dimension at most four:

$$
\mathcal V(\phi)
=
m^2_{ij}\phi_i^\dagger\phi_j
+\kappa_{ijk}\phi_i\phi_j\phi_k
+\lambda_{ijkl}\phi_i\phi_j\phi_k\phi_l
+\cdots,
$$

with the representation indices contracted to singlets. Terms that are forbidden by the gauge representation content are absent.

Yukawa couplings have the schematic form

$$
y_{I J k}\psi_I\psi_J\phi_k+\text{h.c.},
$$

again only when the product of representations contains a gauge singlet.

Fermion mass terms are allowed in vector-like theories when gauge-invariant bilinears exist. In chiral gauge theories they may be forbidden before symmetry breaking.

Renormalization changes the coefficients in this Lagrangian, but it does not create gauge-non-invariant terms if the regularization and subtraction preserve BRST consistency.

## What gets renormalized

In a renormalizable gauge theory, the bare and renormalized quantities are related by constants such as

$$
A_{0\mu}^a=Z_A^{1/2}A_\mu^a,\qquad
c_0^a=Z_c^{1/2}c^a,\qquad
\psi_0=Z_\psi^{1/2}\psi,\qquad
\phi_0=Z_\phi^{1/2}\phi.
$$

The gauge coupling is written

$$
g_0=\mu^\epsilon Z_g g
$$

in $d=4-2\epsilon$ dimensions. For matter parameters,

$$
m_0=Z_m m,\qquad
y_0=\mu^\epsilon Z_y y,\qquad
\lambda_0=\mu^{2\epsilon}Z_\lambda\lambda
$$

schematically. The powers of $\mu$ depend on dimension and convention.

The gauge-fixing parameter also renormalizes:

$$
\xi_0=Z_\xi\xi.
$$

This does not make $\xi$ a physical coupling. It is a gauge-choice parameter. Physical gauge-invariant observables cannot depend on it, though off-shell Green functions usually do.

In background-field gauge there is an especially useful relation between the renormalization of the background field and the gauge coupling:

$$
Z_g Z_{\bar A}^{1/2}=1.
$$

This is not a new physical law. It is the background Ward identity saying that the background covariant derivative retains its form after renormalization. It is one reason background-field gauge is so efficient for computing gauge beta functions.

## Pure Yang–Mills as the clean example

For pure Yang–Mills theory,

$$
\mathcal L_{\rm YM}
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu},
$$

the only physical dimension-four gauge-invariant counterterm is

$$
-\frac14\delta Z_A\,F_{\mu\nu}^aF^{a\mu\nu},
$$

plus the topological density

$$
\theta\,\frac{g^2}{32\pi^2}F_{\mu\nu}^a\widetilde F^{a\mu\nu}
$$

if the theory includes a $\theta$ angle. Perturbative renormalization of ordinary amplitudes mostly concerns the $F^2$ term; the $F\widetilde F$ term is a total derivative locally but has important nonperturbative meaning.

Expanding $F^2$ gives counterterms for the propagator, three-gluon vertex, and four-gluon vertex. Gauge symmetry says these are not independent. Their divergent parts are related so that the counterterm can be written as $F^2$.

In an ordinary covariant gauge this relation is hidden across many diagrams involving gauge bosons and ghosts. In background-field gauge it is visible because the divergent effective action $\Gamma_{\rm div}[\bar A]$ must be gauge invariant under transformations of $\bar A$.

## QED as the Abelian comparison

In QED with a Dirac fermion,

$$
\mathcal L_{\rm QED}
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu+iqA_\mu,
$$

renormalization introduces

$$
-\frac14\delta Z_3F_{\mu\nu}F^{\mu\nu}
+\delta Z_2\bar\psi i\gamma^\mu D_\mu\psi
-\delta m\,\bar\psi\psi
+\cdots.
$$

The Ward–Takahashi identity relates the electron-photon vertex renormalization to the electron wavefunction renormalization. In a common notation,

$$
Z_1=Z_2.
$$

This identity is the Abelian predecessor of the Slavnov–Taylor identities. It ensures that charge renormalization can be read from the photon vacuum polarization once the fields are normalized. That is why the running electric charge is governed by vacuum polarization in the cleanest formulation.

## Non-Abelian theories with matter

With matter fields, the list of counterterms grows, but still finitely. Gauge invariance permits:

| Sector | Typical counterterm | Meaning |
|---|---|---|
| Gauge | $F_{\mu\nu}^aF^{a\mu\nu}$ | Gauge-field and coupling renormalization |
| Fermion kinetic | $\bar\psi i\gamma^\mu D_\mu\psi$ | Fermion field renormalization |
| Fermion mass | $m\bar\psi\psi$ when gauge invariant | Mass renormalization |
| Scalar kinetic | $(D_\mu\phi)^\dagger D^\mu\phi$ | Scalar field renormalization |
| Scalar potential | $\phi^2,\phi^3,\phi^4$ singlets | Scalar mass and self-couplings |
| Yukawa | $\psi\psi\phi+\text{h.c.}$ singlets | Yukawa coupling renormalization |
| Topological | $F_{\mu\nu}^a\widetilde F^{a\mu\nu}$ | $\theta$ angle, nonperturbative sectors |

The words “when gauge invariant” are doing serious work. A mass term or Yukawa coupling is not allowed merely because its dimension is small. It must be a singlet under the gauge group and compatible with any imposed global or discrete symmetries.

## Relation to unitarity

Renormalizability and unitarity are distinct but entangled in gauge theories.

Power counting is an ultraviolet statement. Unitarity is a Hilbert-space statement. Gauge symmetry connects them because the same Ward or Slavnov–Taylor identities that restrict counterterms also ensure cancellations among unphysical polarizations and ghosts.

In covariant gauges, the internal propagators include unphysical modes. The physical $S$-matrix is unitary only after projecting onto the BRST cohomology. If counterterms spoiled BRST symmetry, the projection would not be stable under time evolution, and the theory would not define a consistent scattering theory.

This is why the phrase “renormalizable massive vector boson” should make you suspicious unless a gauge-invariant mass mechanism is present. Massive Yang–Mills written by simply adding

$$
\frac12m^2A_\mu^aA^{a\mu}
$$

is not the same as a spontaneously broken gauge theory. The Higgs mechanism preserves the gauge redundancy and therefore preserves the Slavnov–Taylor structure.

## A useful checklist

When deciding whether a four-dimensional gauge theory is perturbatively renormalizable, ask:

1. **Are the interaction operators dimension at most four?**  
   If not, the theory may still be an EFT, but not power-counting renormalizable in the traditional sense.

2. **Is the gauge symmetry well defined?**  
   The gauge fields, matter representations, and covariant derivatives must fit one Lie algebra representation structure.

3. **Can the theory be gauge-fixed with a BRST-invariant action?**  
   This is the perturbative mechanism that controls unphysical degrees of freedom.

4. **Are gauge anomalies absent?**  
   Chiral matter must satisfy the relevant anomaly cancellation conditions.

5. **Are all counterterms compatible with the symmetry?**  
   Divergences must be absorbable into gauge-invariant operators plus BRST-exact bookkeeping terms.

If all five answers are yes, the theory is in the standard class of perturbatively renormalizable gauge theories.

## Common pitfalls

**“Dimension four” is not enough.** Arbitrary dimension-four interactions among vector fields are not Yang–Mills theory. The relative coefficients must be tied to a gauge algebra.

**Gauge-fixing terms are not physical counterterms.** They are needed for perturbation theory, and they may renormalize, but they do not represent new physical interactions.

**Ghosts are not optional in non-Abelian covariant gauges.** They are required by the Faddeev–Popov determinant and by BRST symmetry. Omitting them ruins the Slavnov–Taylor identities.

**Anomaly-free is part of the hypothesis.** A chiral gauge theory with uncanceled gauge anomalies is not rescued by renormalization. The anomaly is a failure of the quantum gauge symmetry.

**Renormalizable does not mean UV complete nonperturbatively.** Perturbative renormalizability says the loop expansion can be consistently renormalized. It does not by itself prove a nonperturbative continuum construction or a mass gap.

**The beta function is not the whole renormalization story.** The beta function describes coupling running. Renormalization also involves fields, masses, composite operators, gauge parameters, and sometimes operator mixing.

**Gauge symmetry can be hidden but not discarded.** A regulator or gauge choice may hide gauge invariance. The final renormalized theory must still obey the corresponding identities.

## Relations to other pages

This page sits between [Background-Field Gauge](/gauge-theories-standard-model/gauge-quantization/background-field-gauge/) and [Gauge-Invariant Counterterms](/gauge-theories-standard-model/gauge-renormalization/gauge-invariant-counterterms/). Background-field gauge makes the symmetry of the effective action visible. Counterterm classification turns that visibility into a list.

For Abelian examples, see [QED Renormalization](/gauge-theories-standard-model/gauge-renormalization/qed-renormalization/) after it is written, together with [Vacuum Polarization](/gauge-theories-standard-model/qed/vacuum-polarization/) and [Running Electric Charge](/gauge-theories-standard-model/qed/running-electric-charge/).

For non-Abelian running, continue to [Beta Function of Yang–Mills](/gauge-theories-standard-model/gauge-renormalization/beta-function-of-yang-mills/) and [Asymptotic Freedom](/gauge-theories-standard-model/gauge-renormalization/asymptotic-freedom/) when those pages are available.

For the broader meaning of renormalization and EFT, use the Renormalization, RG, and EFT volume. For anomaly constraints on the Standard Model, return later to the Standard Model anomalies chapter.

## Research status

The perturbative renormalizability of anomaly-free Yang–Mills theories is established textbook physics. The modern view is sharper than the original diagrammatic one: BRST symmetry, Slavnov–Taylor identities, and local cohomology explain why the allowed counterterms have the right form.

There are still important active directions around this stable core. Nonperturbative definitions of chiral gauge theories are subtle. Strongly coupled gauge theories near conformal windows are active. Gauge theories as EFTs require systematic higher-dimensional operator bases. Gauge theories with boundaries, defects, higher-form symmetries, or nontrivial global form require care beyond the first-pass perturbative treatment.

## Exercises

### Exercise 1: Dimensions in four dimensions

Using the kinetic terms, derive the canonical dimensions

$$
[A_\mu]=1,\qquad [\psi]=\frac32,\qquad [\phi]=1,\qquad [c]=[\bar c]=1.
$$

Then show that $g$ is dimensionless in the Yang–Mills covariant derivative.

<details>
<summary><strong>Solution</strong></summary>

The action is dimensionless and $d^4x$ has dimension $-4$, so $\mathcal L$ has dimension $4$.

For the gauge field, the kinetic term contains $(\partial A)^2$, so

$$
2(1+[A])=4,
$$

hence $[A]=1$.

For a Dirac fermion,

$$
\bar\psi i\gamma^\mu\partial_\mu\psi
$$

has dimension $4$, so

$$
[\bar\psi]+1+[\psi]=4.
$$

Since $[\bar\psi]=[\psi]$, we get $[\psi]=3/2$.

For a scalar,

$$
(\partial_\mu\phi)^\dagger\partial^\mu\phi
$$

gives

$$
2(1+[\phi])=4,
$$

so $[\phi]=1$.

The ghost kinetic term is

$$
-\bar c^a\partial^2 c^a
$$

at quadratic order, so

$$
[\bar c]+2+[c]=4.
$$

Taking $[c]=[\bar c]$ gives $[c]=[\bar c]=1$.

Finally, $D_\mu=\partial_\mu+igA_\mu$ requires

$$
[g]+[A]=1.
$$

Since $[A]=1$, $[g]=0$.

</details>

### Exercise 2: Why a gauge-boson mass counterterm is forbidden

Show that

$$
\frac12m_A^2A_\mu^aA^{a\mu}
$$

has dimension four or less, but is not an allowed counterterm in an unbroken Yang–Mills theory.

<details>
<summary><strong>Solution</strong></summary>

Since $[A_\mu]=1$, the operator $A_\mu^aA^{a\mu}$ has dimension $2$. Therefore $m_A^2$ has dimension $2$, and the full term has dimension $4$.

Power counting alone would allow it. Gauge symmetry does not. Under an infinitesimal gauge transformation,

$$
\delta A_\mu^a=(D_\mu\alpha)^a,
$$

so

$$
\delta(A_\mu^aA^{a\mu})
=
2A^{a\mu}(D_\mu\alpha)^a,
$$

which is not a total derivative in general. Equivalently, in BRST language,

$$
s(A_\mu^aA^{a\mu})=2A^{a\mu}(D_\mu c)^a
$$

is not zero modulo a total derivative. Thus the term is not BRST invariant and cannot appear as a counterterm in the unbroken theory.

A gauge boson can become massive in a renormalizable theory through the Higgs mechanism because the mass term then arises from a gauge-invariant scalar kinetic term, not from adding $A_\mu^2$ by hand.

</details>

### Exercise 3: Relative coefficients in Yang–Mills

Expand $F_{\mu\nu}^aF^{a\mu\nu}$ using

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

Identify the schematic forms of the quadratic, cubic, and quartic gauge-field terms.

<details>
<summary><strong>Solution</strong></summary>

Write

$$
F_{\mu\nu}^a=f_{\mu\nu}^a-gf^{abc}A_\mu^bA_\nu^c,
$$

where

$$
f_{\mu\nu}^a=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a.
$$

Then

$$
F_{\mu\nu}^aF^{a\mu\nu}
=
f_{\mu\nu}^af^{a\mu\nu}
-2g f^{abc}f_{\mu\nu}^aA^{b\mu}A^{c\nu}
+g^2 f^{abc}f^{ade}A_\mu^bA_\nu^cA^{d\mu}A^{e\nu}.
$$

Thus the Yang–Mills Lagrangian contains

$$
(\partial A)^2,\qquad
g(\partial A)AA,\qquad
g^2AAAA,
$$

with all relative coefficients fixed by the same structure constants and the same coupling $g$. Renormalization may rescale fields and $g$, but BRST symmetry prevents these structures from splitting into arbitrary independent interactions.

</details>

### Exercise 4: EFT versus renormalizable theory

The operator

$$
\frac{1}{\Lambda^2}f^{abc}F_{\mu}^{a\ \nu}F_{\nu}^{b\ \rho}F_{\rho}^{c\ \mu}
$$

is gauge invariant. Why is it not part of the traditional renormalizable Yang–Mills Lagrangian in four dimensions?

<details>
<summary><strong>Solution</strong></summary>

Each field strength has dimension $2$, so $F^3$ has dimension $6$. The coefficient must have dimension $-2$, written as $1/\Lambda^2$.

The operator is gauge invariant, so symmetry allows it. But it is not power-counting renormalizable in four dimensions. If included as an unsuppressed interaction, it would require an infinite tower of higher-dimensional counterterms.

As an EFT operator it is perfectly legitimate. Its effects are suppressed by powers of $E^2/\Lambda^2$, and the theory is predictive order by order in that expansion.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§69–75 and §78, for non-Abelian gauge theory, group representations, gauge fixing, Feynman rules, beta functions, BRST symmetry, anomalies, and background-field gauge.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Chs. 15 and 17, for the general structure of non-Abelian gauge theories, Faddeev–Popov quantization, ghosts, BRST symmetry, and renormalization of gauge theories.
- Coleman, *Aspects of Symmetry*, lectures “Renormalization and Symmetry,” “Secret Symmetry,” and “Asymptotic Freedom,” for the conceptual connection between symmetry, renormalization, gauge fields, and ultraviolet behavior.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 21 and 25–26, for renormalizability, Yang–Mills theory, quantum Yang–Mills theory, and one-loop non-Abelian running.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, Ch. 26 and related sections, for the BRST and Zinn-Justin-equation approach to gauge-theory renormalization.

## Version history

- **2026-06-18:** Initial polished draft.
