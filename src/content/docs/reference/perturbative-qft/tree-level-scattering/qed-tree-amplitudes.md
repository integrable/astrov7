---
title: "QED Tree Amplitudes"
description: "A worked calculation of basic tree-level QED amplitudes, including photon exchange, pair annihilation, Compton scattering, Ward-identity checks, and spin-sum normalization."
sidebar:
  label: "QED Tree Amplitudes"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§56–60; Weinberg 1995, Vol. I, chs. 6 and 8; Coleman 2019, chs. 30 and 34; Schwartz 2014, chs. 8 and 13; Zee 2010, chs. II.6–II.8"
topics:
  - QED
  - tree amplitudes
  - photon exchange
  - Ward identities
  - Compton scattering
canonicalTopics:
  - qed-tree-amplitudes
  - photon-exchange-amplitudes
  - pair-annihilation-amplitudes
  - compton-scattering-tree-amplitude
  - ward-identity-checks
researchStatus:
  established:
    - "Tree-level QED amplitudes, their spinor-current structure, and their Ward-identity checks are standard consequences of perturbative spinor electrodynamics."
  active:
    - "Precision QED requires loop corrections, infrared-safe observables, real radiation, renormalization, and finite-resolution detector definitions; those issues belong to later pages."
---

## Summary

QED tree amplitudes are the first gauge-theory amplitudes most students compute. They introduce three habits that never go away: attach external spinors and photon polarizations carefully, keep fermion-line order fixed, and check gauge invariance by replacing a polarization vector with its momentum.

In qft.org conventions, a field of charge $q$ has

$$
D_\mu=\partial_\mu+iqA_\mu,
$$

so the charge-$q$ Dirac–photon vertex is

$$
-iq\gamma^\mu.
$$

For the electron, $q=-e$ with $e>0$, and the electron–photon vertex is therefore

$$
+ie\gamma^\mu.
$$

The simplest photon-exchange amplitude is distinct charged-fermion scattering,

$$
f_a(p_1)+f_b(p_2)\to f_a(p_3)+f_b(p_4),
$$

with charges $q_a,q_b$. In Feynman gauge,

$$
\mathcal M_t
=
\frac{q_aq_b}{t+i\epsilon}
\left[\overline u_a(p_3)\gamma^\mu u_a(p_1)\right]
\left[\overline u_b(p_4)\gamma_\mu u_b(p_2)\right].
$$

For electron–muon scattering, $q_aq_b=e^2$. For pair annihilation $e^-e^+\to\mu^-\mu^+$, the same structure appears in the $s$ channel with $t$ replaced by $s$ and with the incoming positron represented by a $v$ spinor.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![QED tree diagrams: photon exchange, pair annihilation, and Compton scattering](/figures/perturbative-qft/qed-tree-amplitudes.svg)

<figcaption>

Basic QED tree amplitudes are built from conserved Dirac currents, photon propagators, and, for Compton scattering, internal electron propagators. The two Compton orderings are both required; their sum is what satisfies the Ward identity for external photons.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), and [Yukawa Tree Amplitudes](/perturbative-qft/tree-level-scattering/yukawa-tree-amplitudes/). For the field-theory background, review [Dirac Field](/foundations/free-fields/dirac-field/) and [Maxwell Field](/foundations/free-fields/maxwell-field/).

## Core idea

A QED tree amplitude is a Lorentz-invariant contraction of charged currents and photon polarizations. The scalar Yukawa bilinear $\overline u(p')u(p)$ is replaced by a vector current,

$$
J^\mu(p',p)=\overline u(p')\gamma^\mu u(p),
$$

or by the corresponding antifermion current. Internal photons contract these currents with a propagator; external photons contract the current with a polarization vector.

The essential dictionary is:

| Ingredient | QED tree-level role |
|---|---|
| $-iq\gamma^\mu$ | photon–fermion vertex for charge $q$ |
| $-i\eta_{\mu\nu}/(k^2+i\epsilon)$ | Feynman-gauge photon propagator |
| $u$, $\overline u$, $v$, $\overline v$ | external electron or positron spinors |
| $\epsilon_\mu(k)$ | external photon polarization |
| current conservation | removes gauge-dependent longitudinal pieces |
| Ward identity | checks that unphysical photon polarizations decouple |

QED signs are a convention trap because many textbooks choose the opposite sign for $D_\mu$. The physical amplitude is unchanged when the entire convention is translated consistently.

## Setup and conventions

The spinor-QED Lagrangian is

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\overline\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu+iqA_\mu.
$$

Expanding the covariant derivative gives

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\overline\psi(i\gamma^\mu\partial_\mu-m)\psi
-q\overline\psi\gamma^\mu A_\mu\psi.
$$

Therefore the charge-$q$ vertex is

$$
{-iq\gamma^\mu.}
$$

For an electron, $q=-e$ with $e>0$, so the vertex is

$$
{+ie\gamma^\mu.}
$$

In Feynman gauge, the photon propagator is

$$
\frac{-i\eta_{\mu\nu}}{k^2+i\epsilon}.
$$

The Dirac propagator is

$$
\frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon},
\qquad
p\!\!\!/\equiv\gamma^\mu p_\mu.
$$

For external photons we use polarization vectors $\epsilon_\mu(k)$ with

$$
k^2=0,
\qquad
k\cdot\epsilon(k)=0,
$$

and physical amplitudes are invariant under

$$
\epsilon_\mu(k)\mapsto\epsilon_\mu(k)+\alpha k_\mu.
$$

That invariance is the practical tree-level form of the Ward identity for external photons.

## Photon exchange: charged-fermion scattering

Consider distinct charged fermions

$$
f_a(p_1,s_1)+f_b(p_2,s_2)
\to
f_a(p_3,s_3)+f_b(p_4,s_4).
$$

Let

$$
q=p_1-p_3=p_4-p_2,
\qquad
q^2=t.
$$

The two currents are

$$
J_a^\mu=\overline u_a(p_3,s_3)\gamma^\mu u_a(p_1,s_1),
\qquad
J_b^\nu=\overline u_b(p_4,s_4)\gamma^\nu u_b(p_2,s_2).
$$

The diagram gives

$$
\begin{aligned}
i\mathcal M_t
&=
\left[\overline u_a(p_3)(-iq_a\gamma^\mu)u_a(p_1)\right]
\frac{-i\eta_{\mu\nu}}{t+i\epsilon}
\left[\overline u_b(p_4)(-iq_b\gamma^\nu)u_b(p_2)\right] \\
&=
i\frac{q_aq_b}{t+i\epsilon}J_a^\mu J_{b\mu}.
\end{aligned}
$$

Therefore

$$
\mathcal M_t
=
\frac{q_aq_b}{t+i\epsilon}J_a\cdot J_b.
$$

For electron–muon scattering, both particles have charge $-e$, so

$$
\mathcal M(e^-\mu^-\to e^-\mu^-)
=
\frac{e^2}{t+i\epsilon}
\left[\overline u_e(p_3)\gamma^\mu u_e(p_1)\right]
\left[\overline u_\mu(p_4)\gamma_\mu u_\mu(p_2)\right].
$$

Because physical spacelike momentum transfer has $t<0$, this amplitude has the correct nonrelativistic sign for repulsion between like electric charges.

## Pair annihilation: electron–positron to muons

For

$$
e^-(p_1,s_1)+e^+(p_2,s_2)
\to
\mu^-(p_3,s_3)+\mu^+(p_4,s_4),
$$

the tree diagram is $s$-channel photon exchange. The incoming positron is represented by $v_e(p_2,s_2)$, and the outgoing antimuon is represented by $v_\mu(p_4,s_4)$.

The amplitude is

$$
\mathcal M_s
=
\frac{e^2}{s+i\epsilon}
\left[\overline v_e(p_2,s_2)\gamma^\mu u_e(p_1,s_1)\right]
\left[\overline u_\mu(p_3,s_3)\gamma_\mu v_\mu(p_4,s_4)\right].
$$

The sign is the same as in electron–muon scattering in the qft.org convention. What changes is the spinor placement and the invariant in the photon propagator.

This formula is often the cleanest first test of QED spinor algebra. Squaring it, summing over final spins, and averaging over initial spins gives the classic angular dependence for massless fermions:

$$
\overline{|\mathcal M_s|^2}
=
e^4(1+\cos^2\theta).
$$

The cross section itself additionally requires the phase-space and flux factors.

## Compton scattering: two electron-line orderings

Compton scattering,

$$
e^-(p,s)+\gamma(k,\epsilon)
\to
e^-(p',s')+\gamma(k',\epsilon'),
$$

has two tree diagrams. One has an internal electron with momentum $p+k$, and the other has an internal electron with momentum $p-k'$. Define

$$
s=(p+k)^2,
\qquad
u=(p-k')^2.
$$

Write

$$
\epsilon\!\!\!/\equiv\gamma^\mu\epsilon_\mu,
\qquad
\epsilon'\!\!\!/^{\,*}\equiv\gamma^\mu\epsilon'^*_\mu.
$$

The tree amplitude is

$$
\begin{aligned}
\mathcal M_{\rm Comp}
=
-e^2\overline u(p',s')
\Bigg[
&\epsilon'\!\!\!/^{\,*}
\frac{p\!\!\!/+k\!\!\!/+m}{s-m^2+i\epsilon}
\epsilon\!\!\!/ \\
&+
\epsilon\!\!\!/
\frac{p\!\!\!/-k'\!\!\!/+m}{u-m^2+i\epsilon}
\epsilon'\!\!\!/^{\,*}
\Bigg]
u(p,s).
\end{aligned}
$$

The order of the matrices follows the fermion line. The rightmost factor acts first on the incoming spinor $u(p,s)$, and the leftmost factor is next to the outgoing $\overline u(p',s')$.

The two terms are not separately gauge invariant with respect to the external photons. Their sum is. This is the small but important lesson of Compton scattering: gauge invariance can require summing all diagrams of a given order.

## Ward-identity checks

The fastest check of a photon-exchange amplitude is current conservation. For the $a$-fermion current,

$$
q_\mu J_a^\mu
=
\overline u_a(p_3)(p_1\!\!\!/-p_3\!\!\!/)u_a(p_1).
$$

Using the Dirac equation and its adjoint,

$$
p_1\!\!\!/u_a(p_1)=m_a u_a(p_1),
\qquad
\overline u_a(p_3)p_3\!\!\!/=m_a\overline u_a(p_3),
$$

we get

$$
{q_\mu J_a^\mu=0.}
$$

The same holds for $J_b$. Therefore a more general covariant photon propagator of the form

$$
\frac{-i}{q^2+i\epsilon}
\left[\eta_{\mu\nu}-(1-\xi)\frac{q_\mu q_\nu}{q^2+i\epsilon}\right]
$$

produces the same tree amplitude between conserved external currents.

For Compton scattering, the analogous statement is that the amplitude vanishes when an external polarization is replaced by its momentum:

$$
\mathcal M_{\rm Comp}(\epsilon\to k)=0,
\qquad
\mathcal M_{\rm Comp}(\epsilon'^*\to k')=0.
$$

The proof uses identities such as

$$
k\!\!\!/
=(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m),
$$

so factors cancel against inverse propagators and the external Dirac equations. This is the tree-level Ward identity in action.

## Spin sums and a massless annihilation check

For unpolarized $e^-e^+\to\mu^-\mu^+$ at energies much larger than the fermion masses, use

$$
\sum_s u(p,s)\overline u(p,s)=p\!\!\!/, 
\qquad
\sum_s v(p,s)\overline v(p,s)=p\!\!\!/,
$$

for massless external fermions. Averaging over the two electron and two positron spin states gives

$$
\overline{|\mathcal M|^2}
=
\frac{e^4}{s^2}\frac14
\operatorname{Tr}\left[p_2\!\!\!/\gamma^\mu p_1\!\!\!/\gamma^\nu\right]
\operatorname{Tr}\left[p_3\!\!\!/\gamma_\mu p_4\!\!\!/\gamma_\nu\right].
$$

Evaluating the traces gives

$$
\overline{|\mathcal M|^2}
=
2e^4\frac{t^2+u^2}{s^2}.
$$

In the center-of-momentum frame for massless $2\to2$ scattering,

$$
t=-\frac{s}{2}(1-\cos\theta),
\qquad
u=-\frac{s}{2}(1+\cos\theta),
$$

so

$$
\overline{|\mathcal M|^2}=e^4(1+\cos^2\theta).
$$

This is a useful checkpoint before inserting the result into the two-body phase-space formula.

## Common pitfalls

**Importing the wrong QED vertex sign.** In qft.org conventions, $D_\mu=\partial_\mu+iqA_\mu$, so an electron with $q=-e$ has vertex $+ie\gamma^\mu$. Many textbooks write $-ie\gamma^\mu$ because they choose the opposite covariant-derivative convention; both are fine if used consistently.

**Forgetting antifermion spinors.** In the usual external-line convention, an incoming positron contributes a $\overline v$ spinor and an outgoing positron contributes a $v$ spinor. Replacing antifermion wavefunctions by $u$ spinors gives the wrong amplitude.

**Checking one Compton diagram by itself.** The two Compton diagrams are not separately gauge invariant. The Ward identity works only after adding both electron-line orderings.

**Confusing the photon propagator with a physical photon sum.** The internal Feynman-gauge propagator contains unphysical components. External photon polarizations and gauge-invariant sums over physical states are separate issues.

**Squaring before fixing spinor order.** Spinor chains are ordered matrix products. Only after all spinor indices are contracted and the spin sums are performed may the result be simplified into traces and scalar invariants.

## Relations to other pages

- [Yukawa Tree Amplitudes](/perturbative-qft/tree-level-scattering/yukawa-tree-amplitudes/) introduces external spinors and fermion propagators without the extra gauge-invariance checks required in QED.
- [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) supplies the $s$, $t$, and $u$ kinematics used in the photon-exchange and annihilation formulas.
- [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/) fixes the spinor and polarization conventions for LSZ-reduced amplitudes.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) explains the stripped-diagram convention used for $i\mathcal M$.
- [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/) explains how amplitudes are constrained by unitarity before loop-level QED is introduced.

## Research status

The tree amplitudes on this page are textbook-standard. Their gauge-invariance checks are exact at tree level and are the simplest examples of Ward identities in scattering amplitudes. Precision QED, however, requires renormalized loop corrections, soft-photon emission, inclusive observables, detector resolution, and careful treatment of infrared divergences.

## Exercises

### Exercise 1: Photon-exchange sign

Using the charge-$q$ vertex $-iq\gamma^\mu$ and the Feynman-gauge photon propagator $-i\eta_{\mu\nu}/(t+i\epsilon)$, derive

$$
\mathcal M_t=\frac{q_aq_b}{t+i\epsilon}J_a\cdot J_b.
$$

<details>
<summary><strong>Solution</strong></summary>

The diagram gives

$$
i\mathcal M_t
=(-iq_a)(-iq_b)\frac{-i}{t+i\epsilon}J_a\cdot J_b.
$$

Since

$$
(-i)(-i)(-i)=i,
$$

we have

$$
i\mathcal M_t
=i\frac{q_aq_b}{t+i\epsilon}J_a\cdot J_b.
$$

Therefore

$$
\mathcal M_t=\frac{q_aq_b}{t+i\epsilon}J_a\cdot J_b.
$$

</details>

### Exercise 2: Current conservation

Show that

$$
q_\mu\overline u(p')\gamma^\mu u(p)=0
$$

for $q=p-p'$ when the incoming and outgoing fermions have the same mass.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
q_\mu\overline u(p')\gamma^\mu u(p)
=\overline u(p')(p\!\!\!/-p'\!\!\!/)u(p).
$$

The Dirac equations give

$$
p\!\!\!/u(p)=mu(p),
\qquad
\overline u(p')p'\!\!\!/=m\overline u(p').
$$

Thus

$$
\overline u(p')p\!\!\!/u(p)-\overline u(p')p'\!\!\!/u(p)
=m\overline u(p')u(p)-m\overline u(p')u(p)=0.
$$

</details>

### Exercise 3: Massless annihilation trace

Starting from

$$
\mathcal M
=
\frac{e^2}{s}
\left[\overline v(p_2)\gamma^\mu u(p_1)\right]
\left[\overline u(p_3)\gamma_\mu v(p_4)\right],
$$

show that, for massless external fermions,

$$
\overline{|\mathcal M|^2}
=2e^4\frac{t^2+u^2}{s^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Average over the two initial electron and positron spin states and sum over final spins:

$$
\overline{|\mathcal M|^2}
=
\frac{e^4}{s^2}\frac14
\operatorname{Tr}(p_2\!\!\!/\gamma^\mu p_1\!\!\!/\gamma^\nu)
\operatorname{Tr}(p_3\!\!\!/\gamma_\mu p_4\!\!\!/\gamma_\nu).
$$

Using

$$
\operatorname{Tr}(a\!\!\!/\gamma^\mu b\!\!\!/\gamma^\nu)
=4(a^\mu b^\nu+a^\nu b^\mu-\eta^{\mu\nu}a\cdot b),
$$

and the massless relations

$$
s=2p_1\cdot p_2=2p_3\cdot p_4,
$$

$$
t=-2p_1\cdot p_3=-2p_2\cdot p_4,
\qquad
u=-2p_1\cdot p_4=-2p_2\cdot p_3,
$$

the contraction gives

$$
\overline{|\mathcal M|^2}
=2e^4\frac{t^2+u^2}{s^2}.
$$

</details>

### Exercise 4: Why both Compton diagrams are needed

Explain why a single Compton diagram cannot satisfy the external-photon Ward identity by itself.

<details>
<summary><strong>Solution</strong></summary>

If the incoming polarization is replaced by $k_\mu$, the $s$-channel numerator contains

$$
k\!\!\!/
=(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m).
$$

The first term cancels the adjacent internal electron propagator, while the second term vanishes only when it reaches the external spinor. This leaves a nonzero contact-like remainder. The $u$-channel diagram produces the opposite remainder. Only the sum of both diagrams vanishes under $\epsilon\to k$, which is the Ward-identity check.

</details>

## References

### Standard first pass

- Mark Srednicki, *Quantum Field Theory*, §§56–60, for LSZ reduction for photons, spinor electrodynamics, QED scattering, and spinor-helicity previews.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 8 and 13, for QED Feynman rules and explicit tree-level QED scattering examples.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. II.6–II.8 and appendix C, for electron scattering, gauge invariance, photon–electron scattering, and compact Feynman rules.

### Deeper references

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 6 and 8, for the general Feynman-rule derivation and electrodynamics in covariant perturbation theory.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 30 and 34, for spinor electrodynamics, gauge-field quantization, Coulomb's law, and famous QED results.
- Michael E. Peskin and Daniel V. Schroeder, *An Introduction to Quantum Field Theory*, chs. 4–5, for QED scattering, Ward identities, and spinor trace technology.

## Version history

- **2026-06-12:** Initial polished draft. Added photon exchange, annihilation, Compton scattering, spin-sum checks, Ward checks, and one compact TikZ figure.
