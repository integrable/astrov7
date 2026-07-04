---
title: "External-Leg Normalization"
description: "How relativistic state normalization, one-particle residues, scalar LSZ factors, spinor wavefunctions, polarization vectors, and phase-space measures fit together."
sidebar:
  label: "External-Leg Normalization"
  order: 6
level: Graduate
status: "Polished draft"
source: "Weinberg 1995, Vol. I, chs. 2–3, 5–6, and 10; Srednicki 2007, §§2–5, 10, 41, and 56; Coleman 2019, chs. 13–14 and 20–21; Schwartz 2014, chs. 5–7 and 13"
topics:
  - external legs
  - state normalization
  - LSZ residues
  - spinor wavefunctions
  - polarization vectors
  - phase space
canonicalTopics:
  - external-leg-normalization
  - one-particle-state-normalization
  - external-wavefunctions
  - lsz-residue-factors
researchStatus:
  established:
    - "External-state normalization, one-particle pole residues, spinor and polarization external factors, and Lorentz-invariant phase-space measures are standard textbook ingredients of scattering calculations."
  active:
    - "Massless gauge theories, unstable particles, infraparticles, bound states, finite-volume amplitudes, and automated higher-order calculations require refined external-state and residue prescriptions."
---

## Summary

External-leg normalization is the bookkeeping that makes four things agree:

$$
\text{state normalization}
\quad\leftrightarrow\quad
\text{field pole residues}
\quad\leftrightarrow\quad
\text{external wavefunctions}
\quad\leftrightarrow\quad
\text{phase space}.
$$

QFT.org uses covariantly normalized one-particle states,

$$
\langle \mathbf p',s'|\mathbf p,s\rangle
=(2\pi)^3 2E_{\mathbf p}\,
\delta^{(3)}(\mathbf p-\mathbf p')\delta_{ss'},
$$

and the corresponding one-particle completeness relation

$$
\mathbf 1_{1\text{-particle}}
=
\sum_s\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
|\mathbf p,s\rangle\langle\mathbf p,s|.
$$

With this normalization, the invariant amplitude is defined by

$$
S_{fi}=\delta_{fi}+i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

Scalar external legs contribute LSZ residue factors. Fermion external legs contribute spinors such as $u$, $v$, $\bar u$, and $\bar v$. Vector external legs contribute polarization vectors. The same $2E_{\mathbf p}$ convention then appears in decay rates and cross sections through Lorentz-invariant phase space.

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Asymptotic States](/perturbative-qft/from-correlators-to-s-matrix/asymptotic-states/), [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/), and [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/). For spinor and vector examples, also review the free-field pages on Dirac fields, Maxwell fields, and polarizations in the Foundations volume.

## Core idea

External legs are where local fields meet asymptotic particle states. The field creates a one-particle state with some residue. LSZ removes the external propagator and divides by the residue normalization. The practical Feynman rules package this into simple external factors.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![External-leg normalization ties state normalization, one-particle residues, external wavefunctions, invariant amplitudes, and phase-space measures together](/figures/perturbative-qft/external-leg-normalization-map.svg)

<figcaption>

External-leg normalization is a consistency loop. The same covariant state normalization that fixes $\langle p'|p\rangle$ also fixes the completeness measure, the LSZ residue factors, the external spinors or polarization vectors, and the phase-space measure used in rates.

</figcaption>
</figure>

At tree level with canonically normalized free fields, this often looks deceptively simple: scalar external legs contribute no visible factor after amputation, fermion legs get spinors, and vector legs get polarization vectors. At loop level, the invisible part becomes visible again as pole residues and wavefunction renormalization.

## Setup and conventions

The on-shell energy is

$$
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2},
\qquad
p^0=E_{\mathbf p},
\qquad
p^2=m^2.
$$

The Lorentz-invariant one-particle measure is

$$
d\Pi_p
\equiv
\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
=
\frac{d^4p}{(2\pi)^3}\theta(p^0)\delta(p^2-m^2).
$$

For many final-state particles,

$$
d\Pi_n(P)
=
(2\pi)^4\delta^{(4)}\!\left(P-\sum_{a=1}^n p_a\right)
\prod_{a=1}^n\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a}.
$$

This page uses the same S-matrix normalization as the rest of this volume:

$$
\langle f|S|i\rangle
=
\langle f|i\rangle
+i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi},
$$

with disconnected identity and spectator pieces understood separately from the connected amplitude.

## Three normalizations, one convention

There are three common places to hide normalization factors.

| Place | What is fixed there |
|---|---|
| One-particle states | factors of $2E_{\mathbf p}$ and $(2\pi)^3\delta^{(3)}$ |
| Field residues | factors of $Z^{1/2}$ relating local fields to physical particles |
| Observables | phase-space and flux factors |

These are not independent choices. If one changes state normalization, the amplitude and phase-space formulas must change. If one rescales a field, the pole residue changes and LSZ compensates. If one changes the definition of $\mathcal M$, the cross-section formula must be rewritten.

The qft.org convention is deliberately boring: put the $2E_{\mathbf p}$ in the state normalization and phase-space measure, define $\mathcal M$ by the S-matrix equation above, and let LSZ handle the field residues.

## Scalar external particles

For a scalar interpolating field, the one-particle residue is defined by

$$
\langle0|\phi(0)|\mathbf p\rangle=\sqrt Z.
$$

The exact two-point function then has the pole

$$
\widetilde G_2(p)
\underset{p^2\to m^2}{\sim}
\frac{iZ}{p^2-m^2+i\epsilon}
+\text{regular terms}.
$$

For an $n$-point connected correlator of scalar fields, LSZ supplies one factor

$$
Z_a^{-1/2}\lim_{p_a^2\to m_a^2}\frac{p_a^2-m_a^2}{i}
$$

for each external scalar leg. Equivalently, exact amputation removes the exact two-point function and LSZ restores one factor of $Z_a^{1/2}$ per external particle.

At tree level in a canonically normalized scalar theory,

$$
Z=1,
\qquad
D_0(p)=\frac{i}{p^2-m^2+i\epsilon},
$$

so the rule is visually simple: erase the external scalar propagators. There is no additional scalar wavefunction like $u(p)$ or $\epsilon_\mu(p)$.

:::note[Field rescaling check]
If $\phi\mapsto c\phi$, then $G_n\mapsto c^nG_n$ and $Z\mapsto c^2Z$. The LSZ combination is unchanged. Physical amplitudes cannot depend on how enthusiastically you normalized your interpolating field.
:::

## Fermion external particles

For a Dirac field, the local field creates a one-particle fermion with a spinor wavefunction:

$$
\langle0|\psi(0)|\mathbf p,s\rangle
=\sqrt{Z_\psi}\,u_s(p),
\qquad
\langle \mathbf p,s|\overline\psi(0)|0\rangle
=\sqrt{Z_\psi}\,\bar u_s(p).
$$

For antiparticles,

$$
\langle0|\overline\psi(0)|\overline{\mathbf p},s\rangle
=\sqrt{Z_\psi}\,\bar v_s(p),
\qquad
\langle \overline{\mathbf p},s|\psi(0)|0\rangle
=\sqrt{Z_\psi}\,v_s(p).
$$

With $p\!\!\!/\equiv\gamma^\mu p_\mu$, the spinors obey the on-shell equations

$$
(p\!\!\!/-m)u_s(p)=0,
\qquad
(p\!\!\!/+m)v_s(p)=0,
$$

with the common normalization

$$
\bar u_s(p)u_r(p)=2m\delta_{sr},
\qquad
\bar v_s(p)v_r(p)=-2m\delta_{sr}.
$$

The spin sums are

$$
\sum_s u_s(p)\bar u_s(p)=p\!\!\!/+m,
\qquad
\sum_s v_s(p)\bar v_s(p)=p\!\!\!/-m.
$$

The practical external-fermion factors are:

| External particle | Factor |
|---|---|
| incoming fermion | $u_s(p)$ |
| outgoing fermion | $\bar u_s(p)$ |
| incoming antifermion | $\bar v_s(p)$ |
| outgoing antifermion | $v_s(p)$ |

At loop level, include the appropriate residue factors or use a renormalization prescription in which the external pole residues are already normalized as desired. The spinors are not optional decoration; they are the spin-index residues of the external fermion poles.

## Vector external particles

For a massive vector field or a gauge field after choosing physical external states, the one-particle matrix element has the form

$$
\langle0|A_\mu(0)|\mathbf p,\lambda\rangle
=
\sqrt{Z_A}\,\epsilon^{(\lambda)}_\mu(p).
$$

For a massive spin-one particle, physical polarizations obey

$$
p^\mu\epsilon^{(\lambda)}_\mu(p)=0,
\qquad
\epsilon^{(\lambda)}(p)^*\cdot\epsilon^{(\lambda')}(p)=-\delta_{\lambda\lambda'},
$$

and the polarization sum is

$$
\sum_{\lambda=1}^3
\epsilon^{(\lambda)}_\mu(p)\epsilon^{(\lambda)}_\nu(p)^*
=
-\eta_{\mu\nu}+\frac{p_\mu p_\nu}{m^2}.
$$

For photons and gluons, only physical transverse polarizations are external states. In covariant gauges one often replaces the physical polarization sum by $-\eta_{\mu\nu}$ inside a squared amplitude, but only after gauge invariance or Ward identities ensure that longitudinal pieces vanish. For an external photon,

| External photon | Factor |
|---|---|
| incoming photon | $\epsilon^{(\lambda)}_\mu(p)$ |
| outgoing photon | $\epsilon^{(\lambda)}_\mu(p)^*$ |

For non-Abelian gauge bosons, add the color label and the corresponding color sums or averages when squaring the amplitude. The gauge field itself is gauge-dependent, but the physical external polarizations and the final gauge-invariant observable are not.

## Crossing and all-incoming notation

Many amplitude formulas use all-incoming notation, where every momentum is written as entering the diagram and total momentum conservation is

$$
\sum_{a=1}^n p_a=0.
$$

This is a notation for analytic continuation and bookkeeping. It does not mean that an outgoing physical particle has negative energy in the detector. When converting to a physical process, assign positive-energy momenta to the actual incoming and outgoing particles, then put the signs into the momentum-conservation convention consistently.

Crossing also changes which external wavefunction appears. An outgoing fermion uses $\bar u(p)$; the crossed incoming antifermion uses $\bar v(p)$. Similar statements hold for bosons, with complex conjugation for outgoing polarization vectors. A surprising number of sign mistakes are just crossing mistakes wearing a tiny fake mustache.

## Observables use the same normalization

The covariant state normalization fixes the standard phase-space formulas. For a decay of a particle of mass $M$,

$$
d\Gamma
=
\frac{1}{2M}\,
\overline{|\mathcal M|^2}\,d\Pi_n(P),
$$

where the bar indicates any required average over initial spin or color and sum over final spin or color.

For two incoming particles $A$ and $B$,

$$
d\sigma
=
\frac{1}{4\sqrt{(p_A\cdot p_B)^2-m_A^2m_B^2}}
\,
\overline{|\mathcal M|^2}\,d\Pi_n(P).
$$

The denominator is the invariant flux. The phase-space pages derive these formulas carefully. Here the point is normalization: the same $2E$ convention appears in the state normalization, completeness relation, and final-state measure.

Spin averages are not external-leg factors. They are part of the experimental question. If the initial beam is unpolarized, average over initial spin states. If the final spin is not measured, sum over final spin states.

## Example: scalar φ⁴ scattering

In real scalar $\phi^4$ theory,

$$
\mathcal L
=
\frac12\partial_\mu\phi\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\lambda}{4!}\phi^4,
$$

the tree-level connected four-point correlator has four external scalar propagators multiplying the contact vertex. After amputation and the on-shell limit,

$$
i\mathcal M_{\rm tree}=-i\lambda.
$$

There are no spinors, no polarization vectors, and no extra $1/\sqrt{2E}$ factors in $\mathcal M$. The $2E$ factors live in the external-state normalization and in $d\Pi_n$.

If a different convention uses noncovariantly normalized one-particle states,

$$
\langle\mathbf p'|\mathbf p\rangle=(2\pi)^3\delta^{(3)}(\mathbf p-\mathbf p'),
$$

then factors of $\sqrt{2E}$ move into states, external wavefunctions, and observable formulas. The physics is the same, but formula-snatching across conventions becomes a little haunted.

## Example: spinor factors in QED

For a QED-like scattering process with two fermion currents exchanging a photon, the amplitude contains spinor bilinears of the form

$$
\bar u(p')\gamma^\mu u(p),
$$

not just a scalar vertex factor. Schematically,

$$
i\mathcal M
\sim
\big[\bar u(p_3)(-ie\gamma^\mu)u(p_1)\big]
\frac{-i\eta_{\mu\nu}}{q^2+i\epsilon}
\big[\bar u(p_4)(-ie\gamma^\nu)u(p_2)\big],
$$

in Feynman gauge for a photon exchanged between two fermion lines. The exact sign and charge labels depend on the process and momentum flow, but the normalization lesson is stable: the external fermion residues are spinors, and the internal photon is a propagator.

## Loop-level external legs

Beyond tree level, external self-energy corrections shift the pole position and residue. The exact scalar propagator near its physical pole has

$$
\widetilde G_2(p)
\sim
\frac{iZ_{\rm pole}}{p^2-m_{\rm phys}^2+i\epsilon}.
$$

For fermions and vectors, the residue may carry spinor, Lorentz, flavor, or gauge structure. In an on-shell renormalization scheme, counterterms are chosen so that the propagator has the desired physical pole mass and residue. In a minimal-subtraction scheme, the residue factors needed to relate the renormalized Green function to on-shell external particles may remain as finite conversion factors.

The rule of thumb is:

1. internal self-energy corrections belong in the Green function;
2. external pole residues belong in LSZ;
3. a renormalization scheme may hide some of this bookkeeping, but it cannot remove it.

For unstable particles, there are no ordinary asymptotic one-particle states. They should not be treated as external stable legs in the same LSZ sense. They appear as internal resonances or require specialized unstable-particle formalisms.

## Common pitfalls

**Putting $1/\sqrt{2E}$ factors into $\mathcal M$ while also using covariant phase space.** That double-counts a convention change.

**Forgetting the pole residue.** A canonically normalized bare field is not automatically a physical field with unit exact pole residue.

**Treating scalar, fermion, and vector external legs as the same.** Scalars have no spin wavefunction. Fermions have spinors. Vectors have polarizations.

**Using polarization sums before checking gauge invariance.** The replacement by $-\eta_{\mu\nu}$ is safe only when longitudinal contributions vanish in the full gauge-invariant expression.

**Averaging over final spins.** Final unobserved spins are summed. Initial unpolarized spins are averaged.

**Using external-particle rules for off-shell correlators.** External spinors and polarizations belong to on-shell asymptotic states. Off-shell Green functions keep external field indices and propagators until amputation and LSZ.

**Treating unstable particles as ordinary external states.** Resonances are not asymptotic states in the same sense as stable particles.

## Relations to other pages

- [Asymptotic States](/perturbative-qft/from-correlators-to-s-matrix/asymptotic-states/) defines the in and out states whose normalization is used here.
- [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/) fixes the normalization of $\mathcal M$.
- [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/) derives the pole-residue factors.
- [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/) explains the off-shell amputation step before external wavefunctions are attached.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) gives the diagrammatic rules that are completed by these external factors.
- The phase-space and cross-section chapter will derive the decay-rate and scattering formulas that use $\overline{|\mathcal M|^2}$.

## Research status

- **Established:** Relativistic state normalization, LSZ residues, spinor and polarization external factors, and invariant phase space are standard QFT.
- **Convention-dependent:** Where factors of $2E_{\mathbf p}$, $\sqrt{2E_{\mathbf p}}$, $Z^{1/2}$, and complex conjugation appear depends on state, field, Fourier, and crossing conventions.
- **Subtle in practice:** Gauge theories with infrared divergences, theories with confinement, unstable particles, finite-volume amplitudes, and bound states require definitions of external states or inclusive observables beyond the simple stable-particle LSZ picture.

## Exercises

### Exercise 1: Covariant versus noncovariant states

Suppose noncovariantly normalized states obey

$$
{}_{\rm nr}\langle\mathbf p'|\mathbf p\rangle_{\rm nr}
=(2\pi)^3\delta^{(3)}(\mathbf p-\mathbf p').
$$

Define

$$
|\mathbf p\rangle_{\rm cov}=\sqrt{2E_{\mathbf p}}\,|\mathbf p\rangle_{\rm nr}.
$$

Show that $|\mathbf p\rangle_{\rm cov}$ has the qft.org covariant normalization.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
\begin{aligned}
{}_{\rm cov}\langle\mathbf p'|\mathbf p\rangle_{\rm cov}
&=
\sqrt{2E_{\mathbf p'}}\sqrt{2E_{\mathbf p}}
\,{}_{\rm nr}\langle\mathbf p'|\mathbf p\rangle_{\rm nr}\\
&=
\sqrt{2E_{\mathbf p'}}\sqrt{2E_{\mathbf p}}
(2\pi)^3\delta^{(3)}(\mathbf p-\mathbf p').
\end{aligned}
$$

The delta function sets $\mathbf p'=\mathbf p$, so $E_{\mathbf p'}=E_{\mathbf p}$. Therefore

$$
{}_{\rm cov}\langle\mathbf p'|\mathbf p\rangle_{\rm cov}
=
(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p').
$$

</details>

### Exercise 2: Field-rescaling invariance of LSZ

Let $\phi'(x)=c\phi(x)$ for a constant $c\neq0$. Show that the scalar LSZ amplitude is unchanged.

<details>
<summary><strong>Solution</strong></summary>

The $n$-point connected Green function scales as

$$
G_n' = c^n G_n.
$$

The one-particle matrix element scales as

$$
\langle0|\phi'(0)|\mathbf p\rangle
=c\sqrt Z,
$$

so

$$
Z'=c^2Z.
$$

The LSZ prefactor contains one $Z'^{-1/2}=c^{-1}Z^{-1/2}$ per external leg, so the product of $n$ residue factors contributes $c^{-n}$. This cancels the $c^n$ from the Green function. Therefore the physical amplitude is unchanged.

</details>

### Exercise 3: Spinor completeness normalization

Assume the positive-energy spinors obey

$$
(p\!\!\!/-m)u_s(p)=0,
\qquad
\bar u_s(p)u_r(p)=2m\delta_{sr}.
$$

Use Lorentz covariance to argue that

$$
\sum_s u_s(p)\bar u_s(p)=p\!\!\!/+m.
$$

<details>
<summary><strong>Solution</strong></summary>

The matrix

$$
\Lambda_+(p)=\sum_s u_s(p)\bar u_s(p)
$$

must project onto positive-energy solutions of the Dirac equation. Lorentz covariance and the Dirac equation imply it is proportional to $p\!\!\!/+m$:

$$
\Lambda_+(p)=A(p\!\!\!/+m).
$$

Take the trace. Since $\operatorname{tr}(p\!\!\!/)=0$ and $\operatorname{tr}(1)=4$,

$$
\operatorname{tr}\Lambda_+(p)=4Am.
$$

On the other hand,

$$
\operatorname{tr}\Lambda_+(p)
=\sum_s\operatorname{tr}(u_s\bar u_s)
=\sum_s\bar u_su_s
=2(2m)=4m,
$$

where there are two spin states. Hence $A=1$, so

$$
\sum_s u_s(p)\bar u_s(p)=p\!\!\!/+m.
$$

</details>

### Exercise 4: Why longitudinal photon polarizations may disappear

Suppose a scattering amplitude with an external photon can be written as

$$
\mathcal M=\epsilon_\mu(p)\mathcal A^\mu(p).
$$

Explain why the replacement $\sum_\lambda\epsilon_\mu^{(\lambda)}\epsilon_\nu^{(\lambda)*}\to -\eta_{\mu\nu}$ is safe only if $p_\mu\mathcal A^\mu=0$.

<details>
<summary><strong>Solution</strong></summary>

The physical photon polarizations are transverse. A covariant polarization sum such as $-\eta_{\mu\nu}$ includes unphysical longitudinal and time-like directions. These extra terms are harmless only if they decouple from the amplitude.

Gauge invariance or a Ward identity gives

$$
p_\mu\mathcal A^\mu=0.
$$

Then shifting a polarization by a longitudinal piece,

$$
\epsilon_\mu\mapsto\epsilon_\mu+\alpha p_\mu,
$$

changes the amplitude by

$$
\Delta\mathcal M=\alpha p_\mu\mathcal A^\mu=0.
$$

Thus longitudinal pieces do not contribute, and the covariant replacement is safe for the complete gauge-invariant amplitude. It need not be safe for an individual gauge-dependent diagram.

</details>

### Exercise 5: Dimension check for a two-to-two amplitude

In four spacetime dimensions, use

$$
d\sigma
=\frac{1}{4\sqrt{(p_A\cdot p_B)^2-m_A^2m_B^2}}
|\mathcal M|^2d\Pi_2
$$

to check that a two-to-two invariant amplitude is dimensionless.

<details>
<summary><strong>Solution</strong></summary>

In natural units, a cross section has mass dimension $-2$. The invariant flux denominator has dimension $2$, so its reciprocal has dimension $-2$.

For two final particles,

$$
d\Pi_2
=(2\pi)^4\delta^{(4)}(P-p_1-p_2)
\frac{d^3\mathbf p_1}{(2\pi)^3 2E_1}
\frac{d^3\mathbf p_2}{(2\pi)^3 2E_2}.
$$

Each $d^3\mathbf p/(2E)$ has dimension $2$, and the four-dimensional delta function has dimension $-4$, so $d\Pi_2$ is dimensionless. Therefore

$$
[d\sigma]=[-2]+[|\mathcal M|^2]+0.
$$

Since $[d\sigma]=-2$, we get

$$
[|\mathcal M|^2]=0,
\qquad
[\mathcal M]=0.
$$

So a four-point invariant amplitude in four dimensions is dimensionless, as expected for a renormalizable quartic or gauge interaction.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§2–5 and 10, for relativistic normalization, LSZ, scalar amplitudes, and cross-section conventions.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5–7 and 13, for cross sections, LSZ, Feynman rules, and QED examples.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 13–14 and 20–21, for asymptotic states, LSZ, spinors, and external wavefunctions.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 2–3, 5–6, and 10, for one-particle normalization, scattering theory, fields, propagators, and reduction formulas.
- H. Lehmann, K. Symanzik, and W. Zimmermann, “Zur Formulierung quantisierter Feldtheorien,” *Nuovo Cimento* **1** (1955), for the original reduction formalism.
- J. D. Bjorken and S. D. Drell, *Relativistic Quantum Fields*, for classic external spinor and polarization conventions.

## Version history

- **2026-06-12:** Initial polished draft for QFT.org, fixing the external-leg normalization flow connecting covariant states, LSZ residues, spinor and polarization wavefunctions, invariant amplitudes, and phase-space measures.
