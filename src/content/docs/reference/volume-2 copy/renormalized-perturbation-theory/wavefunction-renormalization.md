---
title: "Wavefunction Renormalization"
description: "How field-strength renormalization cancels momentum-dependent UV divergences, fixes pole residues in physical schemes, and produces anomalous dimensions."
sidebar:
  label: "Wavefunction Renormalization"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki §§13–18 and §§27–29; Schwartz chs. 18–19 and 23; Weinberg Vol. I ch. 12; Coleman, renormalization lectures; Zinn-Justin, renormalization and composite-operator chapters."
topics:
  - wavefunction renormalization
  - field strength renormalization
  - pole residue
  - LSZ reduction
  - anomalous dimensions
  - self-energy
canonicalTopics:
  - wavefunction-renormalization
  - field-strength-renormalization
  - pole-residue
  - anomalous-dimension
researchStatus:
  established:
    - "Field-strength renormalization is a standard part of perturbative renormalization: it absorbs momentum-dependent local divergences in two-point functions and organizes pole residues and anomalous dimensions."
  active:
    - "Gauge dependence, unstable particles, confined fields, infrared singularities, operator mixing, and high-order anomalous dimensions require careful scheme-aware treatment."
---

## Summary

**Wavefunction renormalization** is the renormalization of the normalization of a field. For a scalar field one writes

$$
\phi_0=Z_\phi^{1/2}\phi,
$$

where $\phi_0$ is the bare regulated field, $\phi$ is the renormalized field, and $Z_\phi$ is the field-strength renormalization factor. In the Lagrangian this is equivalent to adding a kinetic counterterm,

$$
\mathcal L_{\text{ct}}\supset
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi.
$$

The job of $Z_\phi$ is not to make the field a probability wavefunction. The name is historical and a little treacherous. Its actual jobs are:

| Role | Meaning |
|---|---|
| UV subtraction | cancel local divergences proportional to $p^2$ in two-point functions |
| pole normalization | fix or track the residue of a stable one-particle pole |
| LSZ bookkeeping | relate correlators of interpolating fields to scattering amplitudes |
| RG data | produce the field anomalous dimension $\gamma_\phi$ |
| operator normalization | remind us that fields themselves are scheme-dependent coordinates |

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Wavefunction renormalization relates the bare field to a renormalized field, introduces a kinetic counterterm, and determines the pole residue used by LSZ reduction](/figures/renormalization-rg-eft/wavefunction-renormalization-pole-residue.svg)

<figcaption>

Wavefunction renormalization separates three related but distinct ideas: the bare-to-renormalized field relation $\phi_0=Z_\phi^{1/2}\phi$, the kinetic counterterm that subtracts local $p^2$ divergences, and the physical pole residue $Z_{\text{pole}}$ that enters LSZ reduction for stable particles.

</figcaption>
</figure>

The practical warning is:

$$
Z_\phi\text{ is scheme dependent; pole residues and S-matrix normalizations must be handled consistently.}
$$

## Prerequisites

You should know [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/), [Renormalization Conditions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalization-conditions/), [On-Shell Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/on-shell-scheme/), and [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/). For the local origin of the kinetic counterterm, review [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/) and [Renormalization of Correlation Functions](/renormalization-rg-eft/regularization-counterterms/renormalization-of-correlation-functions/).

We use the mostly-minus metric and the scalar tree-level propagator convention

$$
\frac{i}{p^2-m^2+i\epsilon}.
$$

## Core idea

A local field is not itself an observable. It is an interpolating variable used to build correlation functions. Rescaling it by a finite constant changes many Green functions but does not change physical predictions if sources, counterterms, and LSZ factors are treated consistently.

Loop corrections to the two-point function typically produce divergences that are polynomial in $p^2$ near large loop momentum. The constant part renormalizes the mass. The $p^2$ part renormalizes the kinetic term. For a scalar field, the relevant local structures are

$$
\phi^2,
\qquad
\partial_\mu\phi\,\partial^\mu\phi.
$$

In momentum space, these correspond to

$$
1,
\qquad
p^2.
$$

So the divergent part of a scalar self-energy has the schematic local form

$$
\Pi_{\text{div}}(p^2)=A+Bp^2,
$$

and the counterterms $\delta m^2$ and $\delta Z$ cancel $A$ and $B$.

That is the ultraviolet role of wavefunction renormalization. Separately, the exact propagator near a stable one-particle pole has a residue. In an on-shell scheme one often chooses field normalization so that this residue is one. In minimal subtraction, one usually subtracts only the UV pole part and leaves the finite residue to be handled explicitly or indirectly.

## Setup and conventions

For a scalar field, write

$$
\mathcal L_{\text{ren}}
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
+\mathcal L_{\text{int}}(\phi),
$$

and

$$
\mathcal L_{\text{ct}}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2
+\mathcal L_{\text{ct,int}}.
$$

Equivalently, the bare quadratic Lagrangian is

$$
\mathcal L_{0,\text{quad}}
=
\frac12 Z_\phi\partial_\mu\phi\,\partial^\mu\phi
-
\frac12 Z_{m^2}m^2\phi^2,
$$

with

$$
Z_\phi=1+
\delta Z.
$$

Let $\Pi_{\text{loop}}(p^2)$ denote the loop self-energy contribution. With the counterterm convention above, write the renormalized self-energy as

$$
\Pi_R(p^2)=
\Pi_{\text{loop}}(p^2)
+
\delta Z(p^2-m^2)
-
\delta m^2.
$$

Then the corrected scalar propagator is written schematically as

$$
G_R(p^2)=
\frac{i}{p^2-m^2-\Pi_R(p^2)+i\epsilon}.
$$

Different books distribute signs between $\Pi$, $-i\Pi$, and the inverse propagator differently. The invariant content is the same: the counterterm proportional to $p^2$ changes the slope of the inverse propagator, while the mass counterterm changes its intercept.

## Momentum-dependent divergences

The easiest way to see why $\delta Z$ exists is to expand the divergent part of a self-energy in external momentum. Locality says that ultraviolet divergences are local in position space, hence polynomial in external momentum. For a scalar two-point function, the divergent part has the form

$$
\Pi_{\text{div}}(p^2)
=A_0+A_1p^2+A_2p^4+\cdots.
$$

In a power-counting renormalizable scalar theory in four dimensions, only the first two terms are allowed as counterterms in the renormalizable Lagrangian:

$$
A_0\quad\leftrightarrow\quad \delta m^2\phi^2,
\qquad
A_1p^2\quad\leftrightarrow\quad \delta Z(\partial\phi)^2.
$$

Terms such as $p^4$ correspond to higher-derivative operators, for example

$$
(\Box\phi)^2.
$$

They belong naturally in an EFT expansion and are suppressed by powers of the heavy scale or cutoff.

In real $\phi^4$ theory in four dimensions, the one-loop tadpole is independent of $p^2$. Therefore it renormalizes the mass but not the wavefunction at one loop:

$$
\delta Z=0
\qquad
\text{at one loop in ordinary }\phi^4\text{ theory}.
$$

Wavefunction renormalization appears at two loops in that theory. In Yukawa theory, QED, and Yang–Mills theory, momentum-dependent self-energies already occur at one loop.

## Pole residue

For a stable particle, the exact two-point function has a pole at the physical mass. Near the pole,

$$
G_R(p^2)
\underset{p^2\to m_{\text{pole}}^2}{\sim}
\frac{iZ_{\text{pole}}}{p^2-m_{\text{pole}}^2+i\epsilon}
+
\text{terms regular at }p^2=m_{\text{pole}}^2.
$$

Here $Z_{\text{pole}}$ is the residue of the pole for the chosen interpolating field. It is not automatically equal to $Z_\phi^{-1}$, because $Z_\phi$ is the counterterm normalization in a chosen scheme, while $Z_{\text{pole}}$ is extracted from the full renormalized propagator.

Let the inverse propagator denominator be

$$
D_R^{-1}(p^2)=p^2-m^2-\Pi_R(p^2).
$$

The pole position satisfies

$$
D_R^{-1}(m_{\text{pole}}^2)=0.
$$

Expanding around the pole gives

$$
D_R^{-1}(p^2)
=
(p^2-m_{\text{pole}}^2)
\left[1-\Pi_R'(m_{\text{pole}}^2)\right]
+
O\left((p^2-m_{\text{pole}}^2)^2\right).
$$

Therefore

$$
Z_{\text{pole}}
=
\frac{1}{1-\Pi_R'(m_{\text{pole}}^2)}.
$$

In an on-shell scheme for a stable scalar particle, the counterterm $\delta Z$ is chosen so that

$$
\Pi_R'(m^2)=0,
$$

and hence

$$
Z_{\text{pole}}=1.
$$

In $\overline{\mathrm{MS}}$, $\delta Z$ removes only the pole part of the derivative divergence. The finite pole residue is generally not one.

## LSZ and external legs

Scattering amplitudes are not raw time-ordered correlators. LSZ reduction extracts pole residues from correlators and amputates external propagators. For scalar external particles, schematically,

$$
\mathcal M
\sim
\left[\prod_{a=1}^n Z_{\text{pole},a}^{-1/2}\right]
\left[\prod_{a=1}^n(p_a^2-m_a^2)\right]
G_{\text{conn}}^{(n)}(p_1,\ldots,p_n)
\bigg|_{p_a^2\to m_a^2}.
$$

The exact normalization depends on the scattering conventions, but the residue logic is universal. If the on-shell scheme has set $Z_{\text{pole}}=1$, these explicit factors do not appear. If another scheme is used, the residues must be included or canceled by an equivalent convention.

This is why one sometimes hears that wavefunction renormalization is "for external legs." That phrase is only half right. Wavefunction renormalization also subtracts UV divergences in two-point functions and enters anomalous dimensions of fields and operators. External-leg residues are one important place where the normalization becomes visible.

## Field renormalization versus pole residue

It is useful to keep three symbols distinct:

| Symbol | What it means | Scheme dependence |
|---|---|---|
| $Z_\phi$ | bare-to-renormalized field factor, $\phi_0=Z_\phi^{1/2}\phi$ | yes |
| $\delta Z$ | kinetic counterterm coefficient | yes |
| $Z_{\text{pole}}$ | residue of the physical one-particle pole for a chosen field | depends on field normalization, physical only inside LSZ-consistent amplitudes |

In perturbative notation these objects are related, but they are not synonyms. For example, in $\overline{\mathrm{MS}}$, $Z_\phi$ contains only pole terms, while $Z_{\text{pole}}$ can contain finite logarithms and threshold dependence.

A finite field rescaling

$$
\phi\to c\phi
$$

rescales ordinary Green functions but does not change the S-matrix if sources and LSZ residues are adjusted consistently. This is a small example of a larger principle: fields are coordinates on theory space, not directly measured objects.

## Anomalous dimension of a field

Field-strength renormalization produces an anomalous dimension. With

$$
\phi_0=Z_\phi^{1/2}\phi,
$$

we define

$$
\gamma_\phi
\equiv
\frac12
\left.\mu\frac{d\log Z_\phi}{d\mu}\right|_{\text{bare parameters fixed}}.
$$

For an $n$-point renormalized Green function of scalar fields, the homogeneous massless Callan–Symanzik equation takes the schematic form

$$
\left(
\mu\frac{\partial}{\partial\mu}
+
\beta^i\frac{\partial}{\partial g^i}
+n\gamma_\phi
\right)
G_R^{(n)}=0,
$$

away from contact terms and explicit mass terms.

At a fixed point, anomalous dimensions contribute to scaling dimensions. If the engineering dimension of a scalar field in $d$ spacetime dimensions is

$$
\Delta_\phi^{\text{eng}}=\frac{d-2}{2},
$$

then its full scaling dimension has the form

$$
\Delta_\phi=\frac{d-2}{2}+\gamma_\phi^*,
$$

where $\gamma_\phi^*$ is the fixed-point value in the convention being used. For gauge-dependent elementary fields, one must be cautious: the scaling dimensions of gauge-invariant operators are the physical objects in a gauge theory.

## Fermions

For a Dirac field one writes

$$
\psi_0=Z_\psi^{1/2}\psi.
$$

The renormalized inverse fermion propagator can be decomposed as

$$
S_R^{-1}(p)=
p\!\!\!/-m-\Sigma_R(p),
$$

where the self-energy has the general Lorentz structure

$$
\Sigma_R(p)=
A(p^2)p\!\!\!/+B(p^2)m
$$

in a parity-preserving theory with one fermion mass. The coefficient of $p\!\!\!/$ is the fermionic analogue of wavefunction renormalization; the coefficient of $m$ contributes to mass renormalization.

Near a stable pole, the fermion propagator has the form

$$
S_R(p)
\sim
\frac{iZ_{\text{pole}}(p\!\!\!/+m)}{p^2-m^2+i\epsilon}
+
\text{regular terms}.
$$

In an on-shell scheme, the fermion field-strength counterterm is chosen so that the residue has the canonical value. In $\overline{\mathrm{MS}}$, one subtracts only the UV pole parts, and the finite residue remains scheme dependent.

## Gauge fields and ghosts

For a gauge field,

$$
A_{0\mu}=Z_A^{1/2}A_\mu.
$$

For Faddeev–Popov ghosts,

$$
c_0=Z_c^{1/2}c.
$$

These renormalization constants are usually gauge-parameter dependent. That is not a scandal. Gauge fields and ghosts are not gauge-invariant observables. Their $Z$ factors are bookkeeping devices used to renormalize Green functions and maintain the identities imposed by gauge symmetry.

In QED, Ward identities relate the electron wavefunction renormalization to the vertex renormalization in common schemes:

$$
Z_1=Z_2,
$$

where $Z_2$ is the electron field-strength factor and $Z_1$ is the electron-photon vertex factor. This identity is one reason charge renormalization in QED can be tied directly to photon vacuum polarization. In non-Abelian gauge theory, Slavnov–Taylor identities play the corresponding role, but the bookkeeping is richer because gauge bosons, ghosts, and matter fields all interact.

## Composite operators are different

Wavefunction renormalization of an elementary field should not be confused with renormalization of composite operators. A composite operator such as

$$
\mathcal O(x)=\phi^2(x)
$$

has its own short-distance singularities. Its renormalization is written as

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R},
$$

with possible mixing among all operators with the same quantum numbers. Even if $\phi$ is renormalized, $\phi^2$ generally needs additional renormalization.

This is not double counting. Renormalizing the field makes separated-point correlators of $\phi$ finite. Renormalizing composite operators handles the extra singularity of multiplying fields at the same point.

## Example: why the one-loop tadpole does not renormalize the wavefunction

In real $\phi^4$ theory, the one-loop correction to the two-point function is the tadpole. Its loop integral has no dependence on the external momentum $p$:

$$
\Pi_{\text{tadpole}}(p^2)=\text{constant depending on }m^2\text{ and the regulator}.
$$

A momentum-independent divergence can only be canceled by a mass counterterm:

$$
-\frac12\delta m^2\phi^2.
$$

It cannot determine a kinetic counterterm because there is no divergent coefficient multiplying $p^2$. Therefore

$$
\delta Z=0
$$

at this order in ordinary $\phi^4$ theory. This is a useful diagnostic: before writing a wavefunction counterterm, ask whether the divergent part of the two-point function actually depends on external momentum.

In contrast, in a Yukawa theory the one-loop fermion self-energy and scalar self-energy do depend on external momentum. Wavefunction renormalization appears immediately.

## Field redefinitions and normalization choices

A finite field redefinition

$$
\phi'=c\phi
$$

changes the kinetic term normalization unless the Lagrangian parameters are transformed. For example,

$$
\frac12\partial_\mu\phi\partial^\mu\phi
-
\frac{\lambda}{4!}\phi^4
=
\frac{1}{2c^2}\partial_\mu\phi'\partial^\mu\phi'
-
\frac{\lambda}{4!c^4}\phi'^4.
$$

One usually chooses canonical kinetic normalization for convenience. But this is a convention, not a physical law. The invariant content lies in correlation functions with specified operator normalization and in physical observables.

This becomes especially important in EFT, where field redefinitions can move contributions between operators. Some apparent changes in interactions are merely changes of variables. The S-matrix is invariant under suitable local field redefinitions, though off-shell Green functions and operator bases change.

## Common pitfalls

**Thinking $Z_\phi$ is a probability.** It is not a nonrelativistic wavefunction normalization. It is a field-strength renormalization factor.

**Confusing $Z_\phi$ with $Z_{\text{pole}}$.** They are related but not identical. $Z_\phi$ is a scheme counterterm factor; $Z_{\text{pole}}$ is the residue of the full propagator for the chosen field.

**Forgetting LSZ residues.** In schemes where the residue is not set to one, external-leg factors must be handled consistently.

**Demanding $\delta Z$ at every loop order.** A two-point divergence renormalizes the wavefunction only if it has momentum dependence of the kinetic form.

**Treating gauge-field $Z$ factors as observables.** Gauge-field, ghost, and gauge-dependent matter-field renormalizations are often gauge dependent. Gauge-invariant observables are the physical quantities.

**Renormalizing composite operators by field renormalization alone.** Composite operators require their own renormalization and may mix with other operators.

**Ignoring finite normalization conventions.** A different finite field normalization changes Green functions and anomalous-dimension conventions but not physical predictions when consistently translated.

## Relations to other pages

[Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/) introduces the split between renormalized terms and counterterms. This page explains the kinetic part of that split.

[On-Shell Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/on-shell-scheme/) uses pole residue conditions to set $Z_{\text{pole}}=1$ for stable particles. [MS-bar Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/msbar-scheme/) instead subtracts only the UV pole part.

[Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/) will develop $\gamma_\phi$ and operator anomalous dimensions as RG objects. [Composite-Operator Renormalization Preview](/renormalization-rg-eft/regularization-counterterms/composite-operator-renormalization-preview/) explains why local operator insertions need more than field renormalization.

The Perturbative QFT and Scattering volume contains the LSZ and scattering-amplitude technology in more detail.

## Research status

Wavefunction renormalization is settled textbook material, but it becomes subtle in advanced settings. Gauge-dependent fields have gauge-dependent anomalous dimensions. Unstable particles do not have ordinary asymptotic one-particle states. Confined fields, such as quark and gluon fields in QCD, do not correspond directly to asymptotic particles. In massless theories, infrared divergences can obscure naive pole-residue reasoning. In EFT and composite-operator calculations, field redefinitions and operator mixing must be tracked carefully.

The mature lesson is not that $Z_\phi$ is mysterious. It is that field normalization is a coordinate choice, while physical predictions require the whole coordinate system to be used consistently.

## Exercises

### Exercise 1: Residue from the inverse propagator

Let

$$
G(p^2)=\frac{i}{p^2-m^2-\Pi(p^2)+i\epsilon}
$$

and suppose the pole is at $p^2=m_*^2$, where

$$
m_*^2-m^2-\Pi(m_*^2)=0.
$$

Show that the pole residue is

$$
Z_{\text{pole}}=\frac{1}{1-\Pi'(m_*^2)}.
$$

<details><summary><strong>Solution</strong></summary>

Expand the denominator near $p^2=m_*^2$:

$$
p^2-m^2-\Pi(p^2)
=
\left[m_*^2-m^2-\Pi(m_*^2)\right]
+
(p^2-m_*^2)\left[1-\Pi'(m_*^2)\right]
+
\cdots.
$$

The first bracket vanishes by the pole condition. Therefore

$$
G(p^2)
\sim
\frac{i}{(p^2-m_*^2)\left[1-\Pi'(m_*^2)\right]+i\epsilon}
=
\frac{iZ_{\text{pole}}}{p^2-m_*^2+i\epsilon},
$$

with

$$
Z_{\text{pole}}=\frac{1}{1-\Pi'(m_*^2)}.
$$

</details>

### Exercise 2: A tadpole cannot fix the kinetic counterterm

Suppose the divergent part of a scalar self-energy is independent of $p^2$:

$$
\Pi_{\text{div}}(p^2)=A.
$$

Which counterterm cancels it: $\delta m^2$ or $\delta Z$?

<details><summary><strong>Solution</strong></summary>

A mass counterterm contributes a momentum-independent local term to the inverse propagator. A kinetic counterterm contributes a term proportional to $p^2$ or, depending on convention, $p^2-m^2$. Since the divergence has no momentum dependence, it is canceled by $\delta m^2$, not by $\delta Z$.

</details>

### Exercise 3: Finite field rescaling

Let $\phi'=c\phi$. If an $n$-point function is defined by

$$
G^{(n)}(x_1,\ldots,x_n)=\langle\phi(x_1)\cdots\phi(x_n)\rangle,
$$

how does it transform under the rescaling?

<details><summary><strong>Solution</strong></summary>

Since $\phi=\phi'/c$,

$$
G^{(n)}_\phi(x_1,\ldots,x_n)
=
\frac{1}{c^n}
\langle\phi'(x_1)\cdots\phi'(x_n)\rangle.
$$

Equivalently,

$$
G^{(n)}_{\phi'}=c^nG^{(n)}_\phi.
$$

Ordinary Green functions depend on the normalization of the field. Physical amplitudes remain invariant only after the corresponding source and LSZ normalizations are transformed consistently.

</details>

### Exercise 4: Anomalous-dimension sign

Assume

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
G_0^{(n)}=Z_\phi^{n/2}G_R^{(n)}.
$$

At fixed bare quantities, derive the sign of the $n\gamma_\phi$ term in

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+n\gamma_\phi
\right)G_R^{(n)}=0.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate $G_0^{(n)}=Z_\phi^{n/2}G_R^{(n)}$ at fixed bare quantities:

$$
0=\mu\frac{d}{d\mu}\left(Z_\phi^{n/2}G_R^{(n)}\right).
$$

Using

$$
\gamma_\phi=\frac12\mu\frac{d\log Z_\phi}{d\mu},
$$

we get

$$
0=Z_\phi^{n/2}
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+n\gamma_\phi
\right)G_R^{(n)}.
$$

Dividing by $Z_\phi^{n/2}$ gives the displayed equation with a plus sign.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially the sections on exact propagators, loop corrections to propagators, renormalization schemes, and the renormalization group.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on mass renormalization, renormalized perturbation theory, and RG equations.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, for systematic renormalization and field-strength conventions.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on renormalization and counterterms.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the relation between field renormalization, anomalous dimensions, and critical exponents.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*, for standard on-shell and LSZ-oriented examples.

## Version history

- 2026-06-17: First polished draft. Added scalar, fermion, gauge-field, pole-residue, LSZ, anomalous-dimension, and composite-operator distinctions, plus a TikZ figure for the pole-residue bookkeeping.
