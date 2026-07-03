---
title: "Quarks and Gluons"
description: "Explains the quark and gluon fields of QCD as short-distance degrees of freedom, their color and flavor labels, their perturbative interactions, and their relation to color-singlet hadrons."
sidebar:
  label: "Quarks and Gluons"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §§81–83; Schwartz Chs. 25–26 and 32; Weinberg Vol. II Chs. 15–19; Coleman, Aspects of Symmetry, Chs. 1 and 5–8."
topics:
  - quarks
  - gluons
  - QCD degrees of freedom
  - partons
  - jets
  - hadrons
  - confinement
canonicalTopics:
  - quarks-and-gluons
  - qcd-partons
  - gluon-field
  - quark-field
  - color-singlet-spectrum
researchStatus:
  established:
    - "Quarks and gluons are the local colored fields of QCD and the correct short-distance partonic degrees of freedom in high-energy processes."
  active:
    - "The real-time transition from colored partons to color-singlet hadrons, especially hadronization and finite-density dynamics, remains a central nonperturbative problem."
---

## Summary

Quarks and gluons are the microscopic fields of QCD. A quark is a spin-$\frac12$ Dirac field carrying color in the fundamental representation of $SU(3)_c$ and a flavor label such as $u,d,s,c,b,t$. A gluon is the $SU(3)_c$ gauge field, equivalently a connection, with eight adjoint components.

In the QCD Lagrangian,

$$
\mathcal L_{\rm QCD,min}
=
-\frac14G_{\mu\nu}^AG^{A\mu\nu}
+
\sum_f\bar q_f(i\gamma^\mu D_\mu-m_f)q_f,
$$

quarks and gluons look like ordinary relativistic fields. In high-energy scattering they behave as the partonic degrees of freedom resolved by hard probes. In the infrared, however, they are not isolated asymptotic particles. Physical zero-temperature QCD states are color singlets: mesons, baryons, glueball-like states, hybrids, and multihadron states.

This page explains both truths without letting either erase the other:

$$
\text{quarks and gluons are real QCD degrees of freedom,}
\qquad
\text{but not gauge-invariant isolated hadrons.}
$$

<figure class="doc-figure" style="--figure-width: 43rem;">

![Map from short-distance quark and gluon fields to hard partons and long-distance color-singlet hadrons.](/figures/gauge-theories-standard-model/quarks-gluons-partons-hadrons.svg)

<figcaption>

The same QCD Lagrangian is read differently at different scales. At short distances, quark and gluon fields are the right variables for perturbative amplitudes and parton factorization. At long distances, confinement and strong coupling reorganize the physics into color-singlet hadrons.

</figcaption>
</figure>

## Prerequisites

You should know [QCD Lagrangian](/gauge-theories-standard-model/qcd/qcd-lagrangian/) and [Color SU(3)](/gauge-theories-standard-model/qcd/color-su3/). This page assumes the volume convention

$$
D_\mu q_f=(\partial_\mu+ig_sG_\mu^AT^A)q_f,
$$

so that the quark–gluon interaction term is

$$
\mathcal L_{q\bar qG}
=
-g_s\bar q_f\gamma^\mu T^Aq_fG_\mu^A.
$$

You should also know why gauge fixing introduces unphysical gluon polarizations and ghosts in perturbative calculations. The physical content is recovered by BRST symmetry and gauge-invariant observables, not by treating every covariant-gauge field component as a particle.

## Core idea

Quarks and gluons have three roles that should be kept separate.

First, they are **fields in the microscopic Lagrangian**. The QCD action is written in terms of $q_f$ and $G_\mu^A$, and locality plus $SU(3)_c$ gauge invariance determine their leading interactions.

Second, they are **partonic degrees of freedom at short distances**. When a process involves a hard scale $Q\gg\Lambda_{\rm QCD}$, asymptotic freedom makes the coupling small enough that quarks and gluons are the right perturbative variables.

Third, they are **not isolated color-singlet asymptotic states** in ordinary zero-temperature QCD. A detector does not see a free red quark or a free adjoint gluon. It sees hadrons and jets, whose organization remembers quark and gluon dynamics but does not violate color confinement.

The slogan is:

$$
\text{fields} \neq \text{asymptotic particles} \neq \text{detector objects}.
$$

For QCD this distinction is not philosophical housekeeping. It is the difference between a correct parton calculation and a wrong picture of free colored particles.

## Setup and conventions

For each flavor $f$, the quark field is a Dirac spinor and a color triplet:

$$
q_f^i(x),
\qquad
f=1,\ldots,n_f,
\qquad
 i=1,2,3.
$$

The Dirac adjoint is

$$
\bar q_{f i}=q_f^{\dagger j}\gamma^0\delta_{ji},
$$

and transforms in the antifundamental color representation. Color indices are often suppressed, so the compact expression

$$
\bar q_f i\gamma^\mu D_\mu q_f
$$

really means

$$
\bar q_{f i}i\gamma^\mu
\left(\delta^i_j\partial_\mu+ig_sG_\mu^A(T^A)^i{}_j\right)q_f^j.
$$

The gluon is the matrix-valued gauge field

$$
G_\mu=G_\mu^AT^A,
$$

with field strength

$$
G_{\mu\nu}^A
=
\partial_\mu G_\nu^A-
\partial_\nu G_\mu^A
-g_sf^{ABC}G_\mu^BG_\nu^C.
$$

The non-Abelian term in $G_{\mu\nu}^A$ is why gluons interact with gluons. This is the decisive structural difference between QCD and QED.

## Quark quantum numbers

A quark field carries several independent kinds of data:

| Data | Symbol | Meaning |
|---|---|---|
| Spin | Dirac index, suppressed | Quarks are spin-$\frac12$ fermions. |
| Color | $i=1,2,3$ | Fundamental $SU(3)_c$ gauge index. |
| Flavor | $f$ or $u,d,s,c,b,t$ | Species label; masses and electroweak charges depend on it. |
| Baryon number | $1/3$ per quark field | Global quantum number in perturbative QCD and an accidental symmetry of the Standard Model at the renormalizable level. |
| Chirality | $q_{L,R}=P_{L,R}q$ | Important for chiral symmetry and electroweak interactions. |

Color and flavor are the pair most often confused. Color is gauged. Flavor is not the same structure; it labels different quark species. In the strong-interaction Lagrangian alone, if $n_f$ quark masses are equal, there is a global flavor symmetry rotating those $n_f$ species. This flavor symmetry is separate from local color rotations.

For very light quark masses, QCD has an approximate chiral flavor symmetry. For heavy quarks, different approximate symmetries become useful. These approximations are not part of the definition of QCD; they are ways of exploiting limits of the same Lagrangian.

## The quark–gluon vertex

Expanding the quark kinetic term gives

$$
\bar q_fi\gamma^\mu D_\mu q_f
=
\bar q_fi\gamma^\mu\partial_\mu q_f
-g_s\bar q_f\gamma^\mu T^Aq_fG_\mu^A.
$$

Thus the minimal quark–gluon interaction is

$$
\mathcal L_{q\bar qG}
=
-g_s\bar q_f\gamma^\mu T^Aq_fG_\mu^A.
$$

With the usual $e^{iS}$ perturbative convention, the corresponding quark–quark–gluon vertex carries the factor

$$
-ig_s\gamma^\mu T^A,
$$

up to the usual choices of momentum flow, fermion arrow direction, and whether all fields are treated as incoming. The essential structure is the product

$$
\gamma^\mu T^A.
$$

The gamma matrix acts on spinor indices. The generator acts on color indices. The vertex preserves flavor in pure QCD: the gluon couples to color, not to flavor. Flavor-changing interactions are electroweak, not strong.

The same term also explains why a quark can radiate a gluon, why a gluon can split into a quark–antiquark pair, and why the quark contribution to the QCD beta function is proportional to $T_Fn_f$.

## Gluons as gauge bosons

Gluons are the gauge bosons of $SU(3)_c$. Locally one writes eight fields $G_\mu^A$, but the gauge-invariant statement is that $G_\mu=G_\mu^AT^A$ is a connection. The field strength contains

$$
G_{\mu\nu}=\partial_\mu G_\nu-\partial_\nu G_\mu+ig_s[G_\mu,G_\nu]
$$

in matrix notation, equivalent to the component convention used above.

The gauge kinetic term

$$
-\frac14G_{\mu\nu}^AG^{A\mu\nu}
$$

contains:

| Piece | Origin | Perturbative interpretation |
|---|---|---|
| Quadratic term | $(\partial G)^2$ | Gluon propagator after gauge fixing |
| Cubic term | $g_sf^{ABC}(\partial G)GG$ | Three-gluon vertex |
| Quartic term | $g_s^2f^{ABE}f^{CDE}GGGG$ | Four-gluon vertex |

There is no photon-like version of QCD in which gluons carry no charge under their own gauge group. The gluon self-interactions are forced by the non-Abelian gauge principle.

In covariant gauges, the propagating fields include unphysical polarizations and ghosts. These are not additional particles in the spectrum. They are bookkeeping devices that preserve locality, Lorentz covariance, and unitarity in perturbative calculations.

## Quarks and gluons as partons

A parton is a short-distance constituent resolved by a high-energy probe. In QCD, the partons are quarks, antiquarks, and gluons. The language becomes sharp when there is a hard scale $Q$ much larger than the confinement scale:

$$
Q\gg\Lambda_{\rm QCD}.
$$

Then asymptotic freedom makes

$$
\alpha_s(Q)=\frac{g_s^2(Q)}{4\pi}
$$

small enough for perturbative calculations of short-distance kernels. Long-distance information is packaged into nonperturbative but universal objects such as parton distribution functions, fragmentation functions, or hadronic matrix elements.

The conceptual split is not

$$
\text{perturbative QCD} = \text{ignore confinement}.
$$

It is instead

$$
\text{perturbative QCD} = \text{separate short-distance coefficients from long-distance matrix elements}.
$$

That separation is the heart of factorization. A hard scattering may produce energetic colored partons, but the detector sees color-singlet hadrons arranged into jets. The jet remembers the initiating quark or gluon statistically and kinematically, not as a free colored particle.

## Hadrons and color singlets

The simplest color-singlet patterns are:

$$
\text{meson-like:}\qquad \bar q_i\Gamma q^i,
$$

and

$$
\text{baryon-like:}\qquad \epsilon_{ijk}q^iq^jq^k.
$$

Purely gluonic operators such as

$$
\operatorname{tr}(G_{\mu\nu}G^{\mu\nu})
$$

can create glueball-like states in the pure gauge theory, and can mix with quark operators when dynamical quarks are included. More complicated color-singlet operators create hybrids, tetraquark-like channels, pentaquark-like channels, and multiparticle states. The operator vocabulary is broader than the simple quark-model vocabulary.

Color singlet does not mean weakly bound. In QCD, the binding dynamics is often the main event. A color-singlet operator is allowed by gauge invariance; whether it creates a narrow resonance, a broad resonance, a continuum state, or a strongly mixed state is a dynamical question.

## Why quarks and gluons are still real

Because quarks and gluons are not isolated asymptotic states, one sometimes hears the overcorrection that they are “just mathematical artifacts.” That is not right.

They are real in several precise senses:

| Sense | Meaning |
|---|---|
| Lagrangian variables | They are the local fields in the microscopic QCD action. |
| Short-distance degrees of freedom | Hard probes resolve quark and gluon partons. |
| Renormalization data | The QCD beta function, anomalous dimensions, and operator mixing depend on quark and gluon fields. |
| Operator building blocks | Gauge-invariant hadron operators are built from quark and gluon fields. |
| Jet substructure | High-energy jets carry calculable memories of quark or gluon initiation. |

They are not real in the sense of being gauge-invariant isolated one-particle states in the zero-temperature hadron spectrum. QFT happily distinguishes these notions. Confusing them is where the swamp begins, and not the fun topological kind.

## Equations of motion and currents

Varying the action with respect to $\bar q_f$ gives the Dirac equation in the gluon background:

$$
(i\gamma^\mu D_\mu-m_f)q_f=0.
$$

Varying with respect to the gluon field gives the Yang–Mills equation with a quark color current:

$$
(D_\mu G^{\mu\nu})^A
=
g_s\sum_f\bar q_f\gamma^\nu T^Aq_f.
$$

With the sign convention inherited from $D_\mu=\partial_\mu+ig_sG_\mu^AT^A$, the source is the color current

$$
J^{A\nu}=\sum_f\bar q_f\gamma^\nu T^Aq_f.
$$

This current is not a gauge-invariant global Noether current like electric charge in QED. It is a gauge-covariant source for the non-Abelian field equation. Physical global charges in QCD must be gauge invariant, such as baryon number, flavor charges in appropriate mass limits, or momentum.

## Chirality, mass, and flavor

The strong interaction is vectorlike: left- and right-handed components of a quark flavor transform in the same color representation. Splitting

$$
q_f=q_{fL}+q_{fR},
\qquad
q_{fL,R}=P_{L,R}q_f,
$$

the massless quark kinetic term is

$$
\bar q_{fL}i\gamma^\mu D_\mu q_{fL}
+
\bar q_{fR}i\gamma^\mu D_\mu q_{fR}.
$$

For $n_f$ massless quark flavors, this has a large classical flavor symmetry,

$$
SU(n_f)_L\times SU(n_f)_R\times U(1)_B\times U(1)_A,
$$

with the usual caveat that $U(1)_A$ is anomalous. Quark masses explicitly break the chiral symmetry. The light-quark sector approximately remembers it; the heavy-quark sector suggests different expansions.

This separation is one reason QCD is richer than a generic Yang–Mills theory with fermions. Color dynamics is universal across flavors, but flavor masses determine which low-energy approximations are useful.

## Common pitfalls

**Saying quarks and gluons are “not real” because they are confined.** They are not isolated asymptotic color-singlet particles. They are still the microscopic fields and the short-distance partons of QCD.

**Saying quarks and gluons are ordinary particles because we draw them as external lines.** External colored partons are useful in partonic calculations and factorized amplitudes. Physical incoming and outgoing states are color singlets.

**Confusing partons with constituent quarks.** Partons are scale-dependent quarks, antiquarks, and gluons resolved in high-energy processes. Constituent quarks are effective low-energy model degrees of freedom with masses and dynamics very different from Lagrangian current quarks.

**Thinking gluons only mediate the force between quarks.** Gluons also interact with each other. That self-interaction is central to asymptotic freedom and the infrared dynamics of QCD.

**Forgetting ghosts in loop calculations.** Ghosts are not physical hadrons or partons, but they are required in covariant-gauge perturbation theory. Leaving them out breaks gauge consistency.

**Treating flavor changes as strong interactions.** QCD preserves quark flavor labels in the absence of electroweak interactions and mass mixing conventions. Charged weak currents change flavor; gluons do not.

**Equating color singlet with experimentally narrow.** Gauge invariance says which operators are allowed. It does not guarantee a narrow state, a simple quark-model interpretation, or weak mixing with other channels.

## Relations to other pages

This page follows [Color SU(3)](/gauge-theories-standard-model/qcd/color-su3/) and prepares the perturbative pages [QCD Beta Function](/gauge-theories-standard-model/qcd/qcd-beta-function/) and [Running Alpha s](/gauge-theories-standard-model/qcd/running-alpha-s/). The one-loop beta function knows about the same degrees of freedom described here: gluon self-interactions, ghost loops, and quark loops.

The later pages [Chiral Symmetry in QCD](/gauge-theories-standard-model/qcd/chiral-symmetry-in-qcd/) and [Spontaneous Chiral Symmetry Breaking](/gauge-theories-standard-model/qcd/spontaneous-chiral-symmetry-breaking/) use the left- and right-handed quark decomposition introduced above. The page [Confinement in QCD](/gauge-theories-standard-model/qcd/confinement-in-qcd/) will return to the tension between colored microscopic fields and color-singlet asymptotic states.

For the scattering technology behind partons and jets, use the Perturbative QFT and Scattering volume. For lattice, mass gap, confinement mechanisms, and hadronization as nonperturbative dynamics, use the Nonperturbative QFT volume.

## Research status

The existence of quarks and gluons as QCD degrees of freedom is established by the structure and experimental success of the Standard Model, by asymptotic freedom, by scaling violations, by jet physics, and by lattice QCD. The perturbative theory of hard processes is extremely mature.

Several related questions remain active. Real-time hadronization is not derived from first principles with the same completeness as Euclidean lattice observables. Finite-density QCD is obstructed by the sign problem in many regimes. The detailed emergence of hadron spectra, exotic hadrons, and transport from quark and gluon dynamics remains a major meeting point of perturbative methods, lattice QCD, effective field theory, phenomenological modeling, and experiment.

## Exercises

### Exercise 1: Derive the sign of the quark–gluon interaction

Using

$$
D_\mu=\partial_\mu+ig_sG_\mu^AT^A,
$$

expand $\bar q i\gamma^\mu D_\mu q$ and identify the interaction term.

<details><summary><strong>Solution</strong></summary>

We compute

$$
\bar q i\gamma^\mu D_\mu q
=
\bar q i\gamma^\mu(\partial_\mu+ig_sG_\mu^AT^A)q.
$$

The second term is

$$
\bar q i\gamma^\mu ig_sG_\mu^AT^Aq
=-g_s\bar q\gamma^\mu T^AqG_\mu^A.
$$

Therefore

$$
\mathcal L_{q\bar qG}
=-g_s\bar q\gamma^\mu T^AqG_\mu^A.
$$

With the usual $e^{iS}$ perturbative rule, this corresponds to a vertex factor $-ig_s\gamma^\mu T^A$, up to the standard arrow and momentum-flow conventions.

</details>

### Exercise 2: Which of these are color singlets?

For quarks in $\mathbf3$ and antiquarks in $\bar{\mathbf3}$, decide whether the following schematic operators can be made into color singlets:

$$
q^i,
\qquad
\bar q_iq^i,
\qquad
q^iq^j,
\qquad
\epsilon_{ijk}q^iq^jq^k,
\qquad
\operatorname{tr}(G_{\mu\nu}G^{\mu\nu}).
$$

<details><summary><strong>Solution</strong></summary>

A single quark $q^i$ is not a color singlet. The bilinear $\bar q_iq^i$ is a singlet because the fundamental and antifundamental indices are contracted with $\delta^i_j$.

The product $q^iq^j$ alone is not a singlet; it decomposes into $\mathbf6\oplus\bar{\mathbf3}$. Three quarks can form a singlet using the invariant tensor $\epsilon_{ijk}$:

$$
\epsilon_{ijk}q^iq^jq^k.
$$

The gluonic operator $\operatorname{tr}(G_{\mu\nu}G^{\mu\nu})$ is also a color singlet because the color indices are traced.

</details>

### Exercise 3: Why does a gluon not change quark flavor?

Use the quark–gluon interaction

$$
-g_s\sum_f\bar q_f\gamma^\mu T^Aq_fG_\mu^A
$$

to explain why a gluon vertex preserves the flavor label $f$.

<details><summary><strong>Solution</strong></summary>

The generator $T^A$ acts on color indices, not flavor indices. Written with color indices, the interaction is

$$
-g_s\sum_f\bar q_{f i}\gamma^\mu(T^A)^i{}_jq_f^jG_\mu^A.
$$

The same flavor label $f$ appears on $\bar q_f$ and $q_f$, and there is no matrix mixing different flavors. Thus a pure QCD gluon vertex preserves flavor. Flavor-changing processes come from the electroweak charged current, not from the strong interaction.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§81–83, for QCD scattering, Wilson-loop context, and chiral-symmetry material.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–26 and 32, for Yang–Mills theory, quantum Yang–Mills, running coupling, partons, and QCD factorization ideas.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Chs. 15–19, for non-Abelian gauge theory, renormalization, RG methods, and strong-interaction applications.
- Coleman, *Aspects of Symmetry*, Chs. 1 and 5–8, for $SU(3)$, gauge fields, asymptotic freedom, instantons, and large-$N$ perspectives.
- Altarelli, *Partons in Quantum Chromodynamics*, and Sterman, *An Introduction to Quantum Field Theory*, for deeper bridges from quark/gluon fields to parton phenomenology.

## Version history

- **2026-06-18:** Initial page. Added the quark/gluon field dictionary, parton versus hadron distinction, quark–gluon vertex sign in the volume convention, scale interpretation, exercises, and figure.
