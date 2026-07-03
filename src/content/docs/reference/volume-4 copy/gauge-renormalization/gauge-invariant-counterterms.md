---
title: "Gauge-Invariant Counterterms"
description: "Classifies the local counterterms allowed in renormalizable gauge theories and separates physical gauge-invariant counterterms from BRST-exact bookkeeping terms."
sidebar:
  label: "Gauge-Invariant Counterterms"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki §§66–75, 78; Weinberg Vol. II Ch. 17; Coleman lectures on renormalization and gauge-field Feynman rules; Schwartz Chs. 19, 21, 26; Zinn-Justin on BRST and gauge-theory renormalization."
topics:
  - gauge-invariant counterterms
  - BRST cohomology
  - gauge-theory renormalization
  - counterterm classification
  - field redefinitions
  - topological terms
canonicalTopics:
  - gauge-invariant-counterterms
  - brst-cohomology
  - counterterm-lagrangian
  - gauge-theory-renormalization
  - redundant-operators
researchStatus:
  established:
    - "In anomaly-free perturbative gauge theories, physical counterterms are local gauge-invariant operators, while gauge-fixing and ghost counterterms are BRST-exact or equivalent to field and parameter redefinitions."
  active:
    - "Counterterm bases for EFTs, gauge theories with boundaries, chiral gauge theories, and theories with generalized global symmetries remain active areas where this basic logic is refined."
---

## Summary

A counterterm is a local term added to the Lagrangian to cancel regulator dependence. In a gauge theory, a counterterm is not allowed merely because it has the right mass dimension. It must also respect the quantum form of gauge symmetry.

The practical classification in four dimensions is:

$$
S_{\rm ct}
=
\int d^4x\,\sum_i\delta c_i\,\mathcal O_i,
$$

where the $\mathcal O_i$ are local Lorentz-invariant ghost-number-zero operators of dimension at most four, compatible with BRST symmetry. The physically nontrivial ones are gauge-invariant operators such as

$$
F_{\mu\nu}^aF^{a\mu\nu},
\qquad
\bar\psi i\gamma^\mu D_\mu\psi,
\qquad
(D_\mu\phi)^\dagger D^\mu\phi,
\qquad
\psi\psi\phi,
\qquad
\phi^4.
$$

Gauge-fixing and ghost counterterms also appear in practical calculations, but they are bookkeeping terms: BRST-exact pieces, field redefinitions, gauge-parameter redefinitions, or source redefinitions. They are necessary for off-shell Green functions but do not introduce new gauge-invariant observables.

The shortest version is:

$$
\boxed{
\text{physical gauge-theory counterterms}
=
\text{local gauge-invariant operators modulo redundancies}.
}
$$

<figure class="doc-figure" style="--figure-width: 48rem;">

![Gauge-theory counterterms are obtained by filtering local monomials through Lorentz invariance, power counting, and BRST consistency.](/figures/gauge-theories-standard-model/gauge-counterterm-filter.svg)

<figcaption>

Counterterm classification is a sequence of filters. Locality produces local monomials. Lorentz invariance, ghost number, and power counting remove most of them. BRST consistency separates physically meaningful gauge-invariant counterterms from BRST-exact bookkeeping terms such as gauge fixing, ghost normalization, and field redefinitions.

</figcaption>
</figure>

## Prerequisites

You should have read [Renormalizability of Gauge Theories](/gauge-theories-standard-model/gauge-renormalization/renormalizability-of-gauge-theories/). This page assumes the same gauge and BRST conventions.

You should also know the distinction between gauge-invariant observables and gauge-fixed fields from [Gauge-Invariant Observables](/gauge-theories-standard-model/gauge-principle/gauge-invariant-observables/) and the meaning of BRST cohomology from [BRST Symmetry in Gauge Theory](/gauge-theories-standard-model/gauge-quantization/brst-symmetry-in-gauge-theory/).

The covariant derivative convention is

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
$$

and the field strength is defined by

$$
[D_\mu,D_\nu]=igF_{\mu\nu}^aT^a.
$$

Thus

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a
-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

## Core idea

The loop expansion produces divergent local terms. Renormalization cancels them by adding local counterterms. In an ordinary scalar theory, the counterterm list is mostly a matter of power counting and global symmetry. In a gauge theory, the list is controlled by BRST symmetry.

The organizing principle is:

$$
\text{counterterms}
=
\text{BRST-closed local functionals of ghost number }0.
$$

Two BRST-closed terms that differ by a BRST-exact term represent the same physical counterterm:

$$
\mathcal O
\sim
\mathcal O+s\mathcal X+\partial_\mu K^\mu.
$$

The nontrivial equivalence classes are the local BRST cohomology. For ordinary Yang–Mills theories, at ghost number zero and under the usual perturbative assumptions, this cohomology is represented by gauge-invariant local operators built from field strengths, covariant derivatives, and matter fields.

That is the abstract statement. The working physicist’s version is:

1. Write all local operators of dimension at most four.
2. Keep Lorentz scalars with ghost number zero.
3. Keep only gauge-invariant matter contractions.
4. Add gauge-fixing and ghost counterterms only as BRST-exact bookkeeping.
5. Remove redundancies by integration by parts, equations of motion, and field redefinitions when appropriate.

This page makes that list explicit.

## Setup and conventions

We work in four-dimensional Minkowski signature with mostly-minus metric. A counterterm Lagrangian has the form

$$
\mathcal L_{\rm ct}
=
\sum_i\delta c_i\,\mathcal O_i.
$$

The coefficient $\delta c_i$ may contain regulator dependence. In dimensional regularization and minimal subtraction it is usually a Laurent series in $\epsilon$:

$$
\delta c_i
=
\frac{c_i^{(1)}}{\epsilon}
+\frac{c_i^{(2)}}{\epsilon^2}
+\cdots,
\qquad d=4-2\epsilon.
$$

In a cutoff scheme it may contain powers or logarithms of the cutoff. The scheme changes the values of the coefficients, not the symmetry logic of which $\mathcal O_i$ are allowed.

Canonical dimensions are

$$
[A_\mu]=1,\qquad
[F_{\mu\nu}]=2,\qquad
[\psi]=\frac32,\qquad
[\phi]=1,\qquad
[c]=[\bar c]=1.
$$

A four-dimensional power-counting renormalizable counterterm has

$$
[\mathcal O_i]\leq 4.
$$

We assume an unbroken gauge symmetry unless explicitly stated otherwise. Broken gauge theories are still treated gauge-invariantly, but the scalar vacuum expectation value reorganizes the spectrum. Gauge symmetry is not replaced by arbitrary vector-boson mass terms.

## The counterterm filter

A local expression must pass several tests before it is an allowed physical counterterm.

| Filter | Question | Example of what it removes |
|---|---|---|
| Locality | Is it a local polynomial or formal local expansion? | Nonlocal terms such as $F_{\mu\nu}\frac1{\Box}F^{\mu\nu}$ as UV counterterms |
| Lorentz invariance | Are spacetime indices contracted properly? | A preferred-vector term $n^\mu A_\mu$ in Lorentz-invariant vacuum |
| Ghost number | Does it have ghost number zero? | A lone ghost field $c^a$ |
| Power counting | Is dimension at most four? | $F^3$, $(D_\mu F^{\mu\nu})^2$, four-fermion terms in four dimensions |
| Gauge or BRST consistency | Is it gauge invariant modulo BRST-exact terms? | $A_\mu^aA^{a\mu}$ in unbroken Yang–Mills |
| Representation theory | Are internal indices contracted to singlets? | A fermion mass term in a chiral representation where no singlet exists |

The output is a small set of possible counterterms. Which coefficients are actually nonzero depends on the theory and loop order. The classification tells you what can appear; a calculation tells you what does appear.

## Pure Yang–Mills

For a simple unbroken gauge group with no matter, the gauge-invariant local operators of dimension at most four are extremely limited.

The central one is

$$
\mathcal O_F
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
$$

Its counterterm is

$$
\mathcal L_{\rm ct}
\supset
-\frac14\delta Z_F\,F_{\mu\nu}^aF^{a\mu\nu}.
$$

Expanding $F^2$ gives counterterms for the gauge-field two-point function, the three-gauge-boson vertex, and the four-gauge-boson vertex. Gauge symmetry ties them together.

A second dimension-four gauge-invariant density is the topological term

$$
\mathcal O_\theta
=
\frac{g^2}{32\pi^2}
F_{\mu\nu}^a\widetilde F^{a\mu\nu},
$$

where

$$
\widetilde F^{a\mu\nu}
=
\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma}^a.
$$

Locally,

$$
F_{\mu\nu}^a\widetilde F^{a\mu\nu}
=
\partial_\mu K^\mu,
$$

where $K^\mu$ is a Chern–Simons current. Perturbatively around topologically trivial configurations, this total derivative usually does not affect ordinary scattering amplitudes. Nonperturbatively it is crucial: it labels $\theta$ vacua and controls CP violation in QCD-like theories.

Thus for pure Yang–Mills, the physical counterterm list is basically

$$
F^2,
\qquad
F\widetilde F.
$$

Everything else in ordinary covariant gauges is gauge-fixing or ghost bookkeeping.

## Gauge-fixing and ghost counterterms

In a covariant gauge, the gauge-fixed Lagrangian contains

$$
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2
-\bar c^a\partial^\mu D_\mu^{ab}c^b.
$$

Loop calculations generate divergences in off-shell Green functions involving $A_\mu$, $c$, and $\bar c$. These are canceled by field and parameter renormalizations such as

$$
A_{0\mu}^a=Z_A^{1/2}A_\mu^a,\qquad
c_0^a=Z_c^{1/2}c^a,\qquad
\bar c_0^a=Z_c^{1/2}\bar c^a,\qquad
\xi_0=Z_\xi\xi.
$$

One may write these as explicit counterterms for the gauge-fixing and ghost sectors. But they should not be confused with new gauge-invariant physics.

The BRST-exact form makes this clear. With an auxiliary field $B^a$, the gauge-fixing plus ghost term can be written as

$$
\mathcal L_{\rm gf+gh}
=
s\left[
\bar c^a
\left(\partial^\mu A_\mu^a+\frac{\xi}{2}B^a\right)
\right].
$$

Changing the gauge condition, changing $\xi$, or rescaling the trivial pair $(\bar c,B)$ changes a BRST-exact part of the action. Physical BRST cohomology classes do not change.

This is why one often says:

$$
\text{gauge-fixing counterterms are necessary, but not physical couplings}.
$$

## Background-field gauge viewpoint

Background-field gauge makes the physical counterterm structure especially transparent. Split

$$
A_\mu=\bar A_\mu+a_\mu.
$$

After integrating over the quantum fluctuation $a_\mu$ and ghosts, the effective action $\Gamma[\bar A]$ is invariant under background gauge transformations:

$$
\Gamma[\bar A^U]=\Gamma[\bar A].
$$

Therefore its divergent part must be a gauge-invariant functional of $\bar A$:

$$
\Gamma_{\rm div}[\bar A]
=
\int d^4x\,
\left[
-\frac14\delta Z_{\bar A}\bar F_{\mu\nu}^a\bar F^{a\mu\nu}
+\delta\theta\,\frac{g^2}{32\pi^2}\bar F_{\mu\nu}^a\widetilde{\bar F}^{a\mu\nu}
+\cdots
\right].
$$

The ellipsis includes gauge-invariant matter operators if background matter fields are included.

This does not mean ordinary gauge-fixed diagrams are individually gauge invariant. They are not. It means the sum of their divergent contributions, once organized as a background effective action, must be background-gauge invariant.

In background-field gauge the relation

$$
Z_gZ_{\bar A}^{1/2}=1
$$

lets one extract the gauge beta function from the coefficient of $\bar F^2$. This is a calculational convenience, not a separate counterterm principle.

## QED counterterms

For spinor QED,

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu+iqA_\mu.
$$

The standard counterterm Lagrangian is

$$
\mathcal L_{\rm ct}
=
-\frac14\delta Z_3F_{\mu\nu}F^{\mu\nu}
+\delta Z_2\bar\psi i\gamma^\mu\partial_\mu\psi
-\delta m\,\bar\psi\psi
-q\,\delta Z_1\,\bar\psi\gamma^\mu A_\mu\psi.
$$

This form separates the kinetic and vertex counterterms as they appear in diagrams. Gauge invariance relates them. The Ward–Takahashi identity gives

$$
Z_1=Z_2
$$

in the usual notation. Thus the independent physical renormalization of electric charge is tied to the photon field renormalization.

Equivalently, one can package the fermion kinetic and vertex terms into the gauge-covariant expression

$$
\delta Z_2\,\bar\psi i\gamma^\mu D_\mu\psi
$$

plus the appropriate charge renormalization convention.

The photon mass term

$$
\frac12m_\gamma^2A_\mu A^\mu
$$

is forbidden in unbroken QED. The Pauli term

$$
\frac{1}{\Lambda}\bar\psi\sigma^{\mu\nu}\psi F_{\mu\nu}
$$

is gauge invariant but dimension five, so it is not part of renormalizable QED. It is an EFT counterterm in a theory with a finite cutoff scale.

## Non-Abelian gauge theory with fermions

For Dirac fermions in a representation $R$, the kinetic term is

$$
\mathcal L_\psi
=
\bar\psi(i\gamma^\mu D_\mu-m)\psi.
$$

Allowed counterterms include

$$
\delta Z_\psi\,\bar\psi i\gamma^\mu D_\mu\psi,
\qquad
-\delta m\,\bar\psi\psi,
$$

provided the mass term is a gauge singlet.

For multiple fermions, write

$$
\psi_I,
$$

where $I$ labels species and representations. A mass counterterm has the form

$$
-\delta m_{IJ}\bar\psi_I\psi_J,
$$

but only if $\bar R_I\otimes R_J$ contains the trivial representation and all imposed symmetries allow it.

For chiral fermions, it is usually clearer to use Weyl notation. A left-handed Weyl fermion $\chi_i$ in representation $R_i$ has kinetic term

$$
i\chi_i^\dagger\bar\sigma^\mu D_\mu\chi_i.
$$

A Majorana-type mass term for two left-handed Weyl fields has the schematic form

$$
m_{ij}\chi_i\chi_j+\text{h.c.}
$$

It is allowed only if $R_i\otimes R_j$ contains a gauge singlet. In many chiral gauge theories no such singlet exists. The absence of a mass counterterm is then a representation-theoretic fact, not a choice of subtraction scheme.

## Gauge theory with scalars

For complex scalars in representation $R$,

$$
\mathcal L_\phi
=
(D_\mu\phi)^\dagger D^\mu\phi
-\mathcal V(\phi).
$$

The scalar kinetic counterterm is

$$
\delta Z_\phi(D_\mu\phi)^\dagger D^\mu\phi.
$$

The scalar potential counterterms are all gauge-invariant polynomials of dimension at most four:

$$
\mathcal V_{\rm ct}
=
\delta t_i\phi_i
+\delta m^2_{ij}\phi_i^\dagger\phi_j
+\delta\kappa_{ijk}\phi_i\phi_j\phi_k
+\delta\lambda_{ijkl}\phi_i\phi_j\phi_k\phi_l
+\text{h.c.},
$$

where the displayed terms are schematic. Every index contraction must be a singlet of the gauge group and compatible with imposed global symmetries.

In many particle-physics applications, linear and cubic scalar terms are absent because of gauge charges, discrete symmetries, or field definitions. They are not forbidden by power counting in general.

Scalar fields also allow gauge-invariant mass generation through spontaneous symmetry breaking. The counterterm classification should be done in the gauge-invariant theory before expanding around a vacuum.

## Yukawa counterterms

Yukawa interactions have schematic form

$$
\mathcal L_Y
=
-y_{ijA}\psi_i\psi_j\phi_A+\text{h.c.}
$$

or, for Dirac fields,

$$
-y_{ijA}\bar\psi_i\phi_A\psi_j+\text{h.c.},
$$

depending on chirality and representation. A Yukawa counterterm is

$$
-\delta y_{ijA}\psi_i\psi_j\phi_A+\text{h.c.}
$$

It is allowed only if the product of representations contains a gauge singlet.

This simple rule is a powerful constraint. In the Standard Model, for example, the Higgs doublet and the chiral fermion representations are arranged so that the charged-lepton, down-quark, and up-quark Yukawa interactions are gauge invariant, while many other superficially similar terms are not.

Gauge invariance does not determine the numerical Yukawa matrices. It determines which entries are possible. Renormalization then runs the allowed matrices.

## The table of physical dimension-four counterterms

For an ordinary four-dimensional gauge theory with scalars and fermions, the physical counterterms are represented by the following gauge-invariant terms.

| Operator type | Schematic operator | Dimension | Comments |
|---|---:|---:|---|
| Gauge kinetic | $F_{\mu\nu}^aF^{a\mu\nu}$ | 4 | Renormalizes gauge fields and couplings |
| Topological density | $F_{\mu\nu}^a\widetilde F^{a\mu\nu}$ | 4 | Total derivative locally; important nonperturbatively |
| Fermion kinetic | $\bar\psi i\gamma^\mu D_\mu\psi$ | 4 | Includes field normalization and gauge vertex structure |
| Fermion mass | $m\bar\psi\psi$ | 4 | Allowed only for gauge-singlet bilinears |
| Scalar kinetic | $(D_\mu\phi)^\dagger D^\mu\phi$ | 4 | Field normalization and gauge interactions |
| Scalar mass | $m^2\phi^\dagger\phi$ | 4 | Relevant operator; representation-dependent |
| Scalar cubic | $\kappa\phi^3$ | 4 | Super-renormalizable coefficient; only if a singlet exists |
| Scalar quartic | $\lambda\phi^4$ | 4 | Marginal scalar interaction |
| Yukawa | $y\psi\psi\phi+\text{h.c.}$ | 4 | Representation and chirality constrained |
| Vacuum energy | $\Lambda_{\rm vac}$ | 4 | Often ignored in flat-space scattering; important with gravity |

The “dimension” column gives the dimension of the full Lagrangian term including the coefficient. The operator itself may have lower dimension, as with scalar masses or cubic couplings.

If the gauge group has multiple simple factors and $U(1)$ factors, each factor can have its own gauge kinetic term and coupling. Abelian kinetic mixing can also be allowed.

## Abelian kinetic mixing

For two $U(1)$ gauge fields $A_\mu^{(1)}$ and $A_\mu^{(2)}$, the operator

$$
-\frac{\epsilon}{2}F_{\mu\nu}^{(1)}F^{(2)\mu\nu}
$$

is gauge invariant and dimension four. Therefore it is an allowed counterterm unless forbidden by an additional symmetry.

This is special to Abelian factors. For non-Abelian simple groups, a mixed term

$$
F_{\mu\nu}^{a}G^{A\mu\nu}
$$

is not gauge invariant unless the adjoint indices can be contracted in a gauge-invariant way. For independent simple factors, they cannot.

Kinetic mixing is a good reminder that “the counterterm list” depends on the gauge group, representation content, and imposed symmetries. There is no substitute for checking the singlets.

## CP-odd and total-derivative terms

Gauge invariance permits

$$
F_{\mu\nu}^a\widetilde F^{a\mu\nu}.
$$

This term is CP-odd in four-dimensional Yang–Mills theory. Since it is a total derivative locally, perturbative diagrams around trivial backgrounds often do not force one to discuss it. However, in a theory with instantons and nontrivial gauge bundles, the integral

$$
\int d^4x\,F_{\mu\nu}^a\widetilde F^{a\mu\nu}
$$

measures topological information.

Thus it belongs in the gauge-invariant counterterm catalog even when it is invisible in many first-loop calculations. In QCD it becomes the $\theta$ term and leads to the strong CP problem.

The classification of local counterterms sees it. The physics of when it matters is nonperturbative.

## Terms that look allowed but are not

Here is a small museum of tempting wrong counterterms.

| Tempting term | Why it fails in unbroken renormalizable gauge theory |
|---|---|
| $m_A^2A_\mu^aA^{a\mu}$ | Not gauge invariant; not BRST closed |
| $(A_\mu^aA^{a\mu})^2$ | Dimension four but not gauge invariant |
| $\partial_\mu A^{a\mu}$ | Not gauge invariant and usually a gauge-fixing artifact |
| $F_{\mu\nu}^aF^{b\mu\nu}$ with arbitrary $ab$ matrix | Gauge invariance restricts the adjoint-index metric; for simple factors it is proportional to $\delta^{ab}$ |
| $f^{abc}F_\mu^{a\ \nu}F_\nu^{b\ \rho}F_\rho^{c\ \mu}$ | Gauge invariant but dimension six; an EFT operator |
| $\bar\psi\sigma^{\mu\nu}T^a\psi F_{\mu\nu}^a$ | Usually dimension five; EFT operator unless multiplied by additional fields and scales |
| $(\bar\psi\gamma^\mu\psi)^2$ | Dimension six in four dimensions; EFT operator |
| $A_\mu^a\bar\psi\gamma^\mu T^a\psi$ with arbitrary coefficient | The coefficient is tied to the covariant derivative and gauge coupling |

The last line is especially important. In a gauge theory, the gauge-matter vertex is not an independent interaction. It is part of

$$
\bar\psi i\gamma^\mu D_\mu\psi.
$$

Renormalization may change the field normalization and coupling, but it cannot assign unrelated charges to components that belong to the same representation.

## Redundant operators and field redefinitions

Some local operators can be removed by field redefinitions or by using the classical equations of motion. Such terms are called redundant. They matter for off-shell Green functions and for choosing a basis, but not for on-shell observables when handled consistently.

For example, in an EFT one often encounters

$$
(D_\mu F^{\mu\nu})^a(D^\rho F_{\rho\nu})^a.
$$

This is dimension six, not part of the renormalizable counterterm list. But it illustrates the idea: using the gauge-field equation of motion, it can be traded for current-current operators plus terms depending on the chosen basis.

In the renormalizable dimension-four list, field redefinitions show up as wavefunction renormalizations:

$$
A_\mu\mapsto Z_A^{1/2}A_\mu,
\qquad
\psi\mapsto Z_\psi^{1/2}\psi,
\qquad
\phi\mapsto Z_\phi^{1/2}\phi.
$$

These redefinitions change coefficients in the Lagrangian. They are part of renormalization, but they do not correspond one-to-one to new physical observables.

BRST-exact counterterms are the gauge-theory version of this redundancy.

## Counterterms and Ward identities

Gauge-invariant packaging is not just pretty notation. It encodes identities among diagrams.

In QED, one may compute separate divergent contributions to:

1. the electron self-energy,
2. the electron-photon vertex,
3. the photon vacuum polarization.

The Ward–Takahashi identity relates the electron self-energy divergence to the vertex divergence, giving

$$
Z_1=Z_2.
$$

Therefore the electron kinetic counterterm and the electron-photon vertex counterterm assemble into the gauge-covariant structure

$$
\bar\psi i\gamma^\mu D_\mu\psi.
$$

In non-Abelian Yang–Mills theory, the identities are more complicated. Gauge-boson, ghost, and matter diagrams combine so that the two-, three-, and four-gauge-boson counterterms assemble into

$$
F_{\mu\nu}^aF^{a\mu\nu}.
$$

The Slavnov–Taylor identities are the formal machinery behind these relations.

## Counterterms and beta functions

A counterterm coefficient determines how a renormalized coupling depends on the scale $\mu$. For a gauge coupling,

$$
g_0=\mu^\epsilon Z_g(g,\epsilon)g.
$$

The bare coupling $g_0$ is independent of $\mu$:

$$
\mu\frac{d}{d\mu}g_0=0.
$$

This implies a beta function

$$
\beta(g)=\mu\frac{dg}{d\mu}.
$$

In minimal subtraction, the pole part of $Z_g$ determines $\beta(g)$. In background-field gauge, $Z_g$ can be extracted from the gauge-invariant counterterm for $\bar F^2$ using

$$
Z_gZ_{\bar A}^{1/2}=1.
$$

Thus the counterterm classification tells us which coefficient matters; the loop computation tells us its value.

For a simple gauge group with Dirac fermions and scalars, the one-loop beta function has the schematic form

$$
\beta(g)
=
-\frac{g^3}{(4\pi)^2}
\left[
\frac{11}{3}C_A
-\frac{4}{3}T_R n_f
-\frac{1}{6}T_S n_s
\right]
+\cdots,
$$

with representation-dependent conventions for the scalar term. The important point here is not the exact coefficient. It is that one gauge-invariant counterterm, $F^2$, controls the running of the gauge coupling.

## Counterterms in product gauge groups

Many physical theories have a product gauge group,

$$
G=G_1\times G_2\times\cdots\times U(1)_1\times\cdots.
$$

Each simple factor has its own field strength and gauge coupling:

$$
-\frac14\sum_i F_{\mu\nu}^{a_i}F^{a_i\mu\nu}.
$$

The counterterm action includes one gauge kinetic counterterm per simple factor:

$$
-\frac14\sum_i\delta Z_iF_{\mu\nu}^{a_i}F^{a_i\mu\nu}.
$$

For Abelian factors, kinetic mixing terms may also occur:

$$
-\frac12\delta\epsilon_{mn}F_{\mu\nu}^{(m)}F^{(n)\mu\nu}.
$$

Matter counterterms depend on the full product representation. For example, a Yukawa interaction is allowed only if the product of representations under every gauge factor contains a singlet.

This is the logic that eventually organizes the Standard Model: $SU(3)_c$, $SU(2)_L$, and $U(1)_Y$ each have separate gauge kinetic counterterms and running couplings, while the matter interactions are constrained by the full product group.

## Counterterms in spontaneously broken gauge theory

In a Higgs phase, one often writes a Lagrangian in terms of massive gauge bosons. This can obscure the counterterm logic. The renormalizable theory is still organized by gauge-invariant operators before symmetry breaking:

$$
(D_\mu\phi)^\dagger D^\mu\phi
-
V(\phi).
$$

When $\phi$ is expanded around a vacuum expectation value, the scalar kinetic term generates gauge-boson masses, Goldstone interactions, gauge-scalar interactions, and ghost interactions in suitable gauges. Their counterterms are related because they all descend from gauge-invariant structures.

Thus a massive $W$ or $Z$ counterterm in the electroweak theory is not an arbitrary Proca mass counterterm. It is tied to the renormalization of

$$
(D_\mu H)^\dagger D^\mu H,
\qquad
V(H),
\qquad
g,
\qquad
g',
\qquad
v
$$

and to the gauge-fixing prescription.

This distinction is the difference between a renormalizable Higgsed gauge theory and a generic massive vector theory.

## Anomalies as counterterm obstructions

The counterterm procedure assumes the Slavnov–Taylor identity can be maintained. In an anomalous chiral gauge theory, the quantum effective action satisfies

$$
\mathcal S(\Gamma)=\mathcal A
$$

with a nontrivial anomaly $\mathcal A$.

If $\mathcal A$ cannot be written as the BRST variation of a local functional,

$$
\mathcal A\neq s\mathcal X,
$$

then no counterterm can remove it. The theory is not a consistent quantum gauge theory.

This is a different issue from an ordinary divergence. A divergence can be canceled by a counterterm. A nontrivial gauge anomaly is a cohomological obstruction to the symmetry identity itself.

For the Standard Model, anomaly cancellation is therefore not just numerology. It is the condition that the gauge-invariant counterterm program can be consistently carried out for chiral matter.

## Scheme dependence

The counterterm basis is not unique. Different schemes can choose different finite parts:

$$
\delta c_i
=
\delta c_i^{\rm div}
+
\delta c_i^{\rm finite}.
$$

Changing finite parts changes the definition of renormalized parameters. It does not change physical observables when all quantities are computed consistently.

The most common schemes include:

| Scheme | Counterterm idea | Typical use |
|---|---|---|
| On-shell | Fix masses and residues at physical poles | Precision QED and electroweak calculations |
| Minimal subtraction | Subtract only poles in $\epsilon$ | RG and high-energy calculations |
| Modified minimal subtraction | Subtract poles plus standard constants | Standard perturbative QCD and gauge theory |
| Momentum subtraction | Fix Green functions at chosen external momenta | Gauge-dependent off-shell studies and lattice matching |

Gauge invariance does not choose a unique scheme. It restricts the allowed form of the counterterms in any scheme.

## A compact algorithm

To classify counterterms for a concrete gauge theory:

1. **Write the field content and representations.**  
   Include all gauge factors and matter representations.

2. **Assign dimensions and ghost numbers.**  
   Use canonical dimensions for power counting.

3. **Generate local Lorentz scalars of dimension at most four.**  
   Keep all gauge indices explicit at first.

4. **Contract internal indices to gauge singlets.**  
   Use representation theory. For product groups, require a singlet under every factor.

5. **Separate BRST-exact gauge-fixing terms.**  
   Keep them for renormalizing off-shell Green functions, but do not count them as physical interactions.

6. **Remove redundancies.**  
   Use integration by parts, equations of motion, and field redefinitions carefully.

7. **Check anomalies.**  
   If the gauge symmetry is anomalous, counterterm classification cannot rescue the theory.

This algorithm is boring in the same way a good lock is boring: it prevents chaos.

## Common pitfalls

**Do not classify counterterms after gauge fixing as if all fields were physical.** The gauge-fixed Lagrangian contains ghosts and unphysical gauge components. BRST symmetry is the rule that separates physical from bookkeeping terms.

**Do not add every Lorentz-invariant dimension-four vector interaction.** Terms like $(A_\mu A^\mu)^2$ fail gauge invariance.

**Do not treat QED vertex and electron-field counterterms as independent physical data.** The Ward–Takahashi identity relates them.

**Do not ignore representation theory.** A mass term, Yukawa coupling, or scalar cubic is allowed only if the relevant tensor product contains a singlet.

**Do not mistake a total derivative for irrelevance in all contexts.** $F\widetilde F$ is locally a total derivative, but globally it can label physically distinct sectors.

**Do not confuse EFT operators with forbidden operators.** $F^3$ and four-fermion terms can be gauge invariant. They are excluded from the renormalizable dimension-four list, not from effective field theory.

**Do not expect counterterms to be unique.** Operator bases, finite parts, and field definitions can change. Physical predictions do not.

## Relations to other pages

This page follows [Renormalizability of Gauge Theories](/gauge-theories-standard-model/gauge-renormalization/renormalizability-of-gauge-theories/) and prepares for [QED Renormalization](/gauge-theories-standard-model/gauge-renormalization/qed-renormalization/), where the abstract counterterms become the familiar $Z_1$, $Z_2$, $Z_3$, and mass counterterms.

It also prepares for [Beta Function of Yang–Mills](/gauge-theories-standard-model/gauge-renormalization/beta-function-of-yang-mills/), where the coefficient of the $F^2$ counterterm is computed at one loop.

For higher-dimensional gauge-invariant operators, use the Renormalization, RG, and EFT volume and later SMEFT pages. For anomaly constraints, return later to the Standard Model anomalies chapter.

## Research status

The counterterm classification for ordinary perturbative Yang–Mills theories is established. BRST cohomology gives a precise structural explanation of why gauge-invariant operators represent physical counterterms and why BRST-exact terms are redundant.

Active refinements appear in less elementary settings: EFT operator bases, evanescent operators in dimensional regularization, gauge theories with boundaries and defects, chiral gauge theories on the lattice, topological terms, generalized symmetries, and nonperturbative global issues. These do not overturn the first-pass classification; they enrich the hypotheses under which it is applied.

## Exercises

### Exercise 1: Photon mass versus scalar mass

Why is

$$
m^2\phi^\dagger\phi
$$

an allowed scalar counterterm in scalar QED, while

$$
m_\gamma^2A_\mu A^\mu
$$

is not an allowed photon counterterm?

<details>
<summary><strong>Solution</strong></summary>

The scalar field transforms as

$$
\phi\mapsto e^{-iq\alpha}\phi.
$$

Therefore

$$
\phi^\dagger\phi
$$

is gauge invariant. The scalar mass counterterm is allowed by gauge symmetry and power counting.

The photon transforms as

$$
A_\mu\mapsto A_\mu-\partial_\mu\alpha
$$

in Abelian notation. Then

$$
A_\mu A^\mu
$$

is not invariant under local transformations. Its variation contains terms involving $\partial_\mu\alpha$. Thus a photon mass term is not allowed in unbroken QED.

A photon-like gauge boson can acquire mass through the Higgs mechanism, but then the mass arises from a gauge-invariant scalar kinetic term, not from adding $A_\mu A^\mu$ directly.

</details>

### Exercise 2: Gauge invariance of Abelian kinetic mixing

Show that for two Abelian gauge fields,

$$
F_{\mu\nu}^{(1)}F^{(2)\mu\nu}
$$

is gauge invariant.

<details>
<summary><strong>Solution</strong></summary>

For each Abelian gauge field,

$$
A_\mu^{(i)}\mapsto A_\mu^{(i)}-\partial_\mu\alpha^{(i)}.
$$

The field strength

$$
F_{\mu\nu}^{(i)}
=
\partial_\mu A_\nu^{(i)}-\partial_\nu A_\mu^{(i)}
$$

is invariant because the second derivatives of $\alpha^{(i)}$ cancel:

$$
\partial_\mu\partial_\nu\alpha^{(i)}
-\partial_\nu\partial_\mu\alpha^{(i)}=0.
$$

Therefore the product

$$
F_{\mu\nu}^{(1)}F^{(2)\mu\nu}
$$

is also gauge invariant. It has dimension four, so it is an allowed counterterm unless additional symmetries forbid it.

</details>

### Exercise 3: Why four-fermion terms are not in the renormalizable list

In four dimensions, compute the dimension of

$$
(\bar\psi\gamma^\mu\psi)(\bar\psi\gamma_\mu\psi).
$$

Why can it appear in EFT but not in a traditional renormalizable gauge Lagrangian?

<details>
<summary><strong>Solution</strong></summary>

A Dirac field has dimension

$$
[\psi]=\frac32.
$$

Therefore the bilinear $\bar\psi\gamma^\mu\psi$ has dimension

$$
\frac32+\frac32=3.
$$

The product of two such bilinears has dimension

$$
3+3=6.
$$

To include it in a four-dimensional Lagrangian, the coefficient must have dimension $-2$, usually written as $1/\Lambda^2$.

The operator may be gauge invariant, depending on the representation contractions. If so, it is a valid EFT operator. It is not part of the traditional power-counting renormalizable dimension-four Lagrangian because repeated insertions require higher-dimensional counterterms.

</details>

### Exercise 4: Counterterm packaging in QED

Starting from

$$
\bar\psi i\gamma^\mu D_\mu\psi
=
\bar\psi i\gamma^\mu\partial_\mu\psi
-q\bar\psi\gamma^\mu A_\mu\psi,
$$

explain why the Ward identity suggests packaging the electron kinetic and electron-photon vertex counterterms together.

<details>
<summary><strong>Solution</strong></summary>

The covariant kinetic term contains both the electron kinetic term and the electron-photon interaction:

$$
\bar\psi i\gamma^\mu D_\mu\psi
=
\bar\psi i\gamma^\mu\partial_\mu\psi
-q\bar\psi\gamma^\mu A_\mu\psi.
$$

In a diagrammatic calculation one may introduce separate constants for the electron kinetic counterterm and the vertex counterterm. The Ward–Takahashi identity relates them, commonly written

$$
Z_1=Z_2.
$$

This relation says that the divergences combine into the gauge-covariant operator rather than two independent physical structures. Charge renormalization is then tied to the photon field normalization and the chosen definition of $q$.

</details>

### Exercise 5: Classifying scalar quartics

Let $\phi$ be a complex scalar in the fundamental representation of $SU(N)$. Give one gauge-invariant quartic counterterm.

<details>
<summary><strong>Solution</strong></summary>

A simple gauge-invariant bilinear is

$$
\phi^\dagger_i\phi^i,
$$

where $i$ is a fundamental $SU(N)$ index. Squaring it gives the quartic

$$
(\phi^\dagger_i\phi^i)^2.
$$

This has dimension four because $[\phi]=1$. It is therefore an allowed scalar quartic counterterm.

Depending on the number of scalar flavors and representations, additional independent quartic singlets may exist. The classification is a representation-theory problem.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§66–75 and §78, for QED beta functions, non-Abelian gauge theory, group representations, gauge fixing, BRST symmetry, anomalies, and background-field gauge.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Ch. 17, for renormalization of gauge theories, Slavnov–Taylor identities, and background-field methods.
- Coleman, *Aspects of Symmetry*, lectures on renormalization, gauge-field Feynman rules, and asymptotic freedom, for the physical meaning of symmetry-restricted counterterms.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 19, 21, and 26, for counterterm language, renormalizability, and quantum Yang–Mills theory.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the BRST and Zinn-Justin-equation approach to renormalization of gauge theories.

## Version history

- **2026-06-18:** Initial polished draft.
