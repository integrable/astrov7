---
title: "QED Compton Scattering"
description: "A complete tree-level calculation of Compton scattering in QED, emphasizing the two required diagrams, Ward identity, Klein–Nishina formula, and Thomson limit."
sidebar:
  label: "QED Compton Scattering"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§58–60; Schwartz 2014, §13.5; Weinberg 1995, Vol. I, §8.7; Coleman 2019, chs. 30 and 34–35."
topics:
  - QED
  - Compton scattering
  - Ward identities
  - Klein–Nishina formula
  - model calculations
canonicalTopics:
  - qed-tree-amplitudes
  - compton-scattering
  - ward-identities
  - model-calculation-library
researchStatus:
  established:
    - "Tree-level Compton scattering, the Klein–Nishina formula, and the Thomson limit are textbook-standard QED results."
  active:
    - "Precision Compton scattering involves radiative corrections, recoil effects, polarization observables, bound-state corrections, and detector-specific photon definitions."
---

## Summary

Compton scattering is the process

$$
e^-(p)+\gamma(k,\varepsilon)
\to
e^-(p')+\gamma(k',\varepsilon').
$$

At tree level there are two diagrams: an $s$-channel electron propagator and a $u$-channel electron propagator. Neither diagram is gauge invariant by itself. Their sum is.

Using the site’s QED vertex convention, the amplitude may be written as

$$
\mathcal M
=
-e^2\varepsilon_\nu^*(k')\varepsilon_\mu(k)
\overline u(p')
\left[
\gamma^\nu\frac{(p+k)\!\!\!/+m}{s-m^2}\gamma^\mu
+
\gamma^\mu\frac{(p-k')\!\!\!/+m}{u-m^2}\gamma^\nu
\right]
u(p),
$$

where

$$
s=(p+k)^2,
\qquad
u=(p-k')^2.
$$

For an electron initially at rest, the outgoing photon energy is

$$
\frac{\omega'}{\omega}
=
\frac{1}{1+\frac{\omega}{m}(1-\cos\theta)}.
$$

The unpolarized differential cross section is the Klein–Nishina formula,

$$
\frac{d\sigma}{d\Omega}
=
\frac{\alpha^2}{2m^2}
\left(\frac{\omega'}{\omega}\right)^2
\left(
\frac{\omega'}{\omega}
+
\frac{\omega}{\omega'}
-
\sin^2\theta
\right).
$$

In the low-energy limit $\omega\ll m$, this reduces to Thomson scattering,

$$
\frac{d\sigma}{d\Omega}
\to
\frac{\alpha^2}{2m^2}(1+\cos^2\theta).
$$

## Prerequisites

You should know [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/), [Spinor and Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/), [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), and [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/). For the free-field background, review [Dirac Field](/foundations/free-fields/dirac-field/) and [Maxwell Field](/foundations/free-fields/maxwell-field/).

## Core idea

Compton scattering is the first QED calculation where gauge invariance visibly forces a sum of diagrams. A photon can be absorbed before the electron emits the outgoing photon, or it can be emitted before the incoming photon is absorbed. In old language, those are two time orderings. In covariant Feynman language, they are the $s$- and $u$-channel electron propagators.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 56rem;">

![Tree-level Compton scattering in QED](/figures/perturbative-qft/qed-compton-scattering.svg)

<figcaption>

Tree-level Compton scattering requires two electron-exchange diagrams. The $s$-channel diagram carries internal momentum $p+k$, while the $u$-channel diagram carries $p-k'$. The Ward identity works only after the two diagrams are added.

</figcaption>
</figure>

This is why Compton scattering is a better gauge-invariance test than a single photon-exchange process. In electron–muon scattering, each external current is conserved separately. In Compton scattering, the cancellation ties together different diagrams.

## Setup and conventions

The process is

$$
e^-(p,s)+\gamma(k,\lambda)
\to
e^-(p',s')+\gamma(k',\lambda').
$$

The external particles satisfy

$$
p^2=p'^2=m^2,
\qquad
k^2=k'^2=0,
$$

and momentum conservation gives

$$
p+k=p'+k'.
$$

The invariants are

$$
s=(p+k)^2,
\qquad
t=(k-k')^2=(p'-p)^2,
\qquad
u=(p-k')^2,
$$

with

$$
s+t+u=2m^2.
$$

The QED electron vertex is $+ie\gamma^\mu$. The electron propagator is

$$
\frac{i(r\!\!\!/+m)}{r^2-m^2+i\epsilon}.
$$

The incoming photon polarization is $\varepsilon_\mu(k)$ and the outgoing photon polarization is $\varepsilon_\nu^*(k')$.

## Tree-level amplitude

The $s$-channel internal electron has momentum

$$
r_s=p+k,
\qquad r_s^2=s.
$$

The $u$-channel internal electron has momentum

$$
r_u=p-k',
\qquad r_u^2=u.
$$

Adding the two diagrams gives

$$
\begin{aligned}
i\mathcal M
&=
\overline u(p')
(+ie\gamma^\nu)
\frac{i[(p+k)\!\!\!/+m]}{s-m^2+i\epsilon}
(+ie\gamma^\mu)
u(p)
\varepsilon_\nu^*(k')\varepsilon_\mu(k)\\
&\quad+
\overline u(p')
(+ie\gamma^\mu)
\frac{i[(p-k')\!\!\!/+m]}{u-m^2+i\epsilon}
(+ie\gamma^\nu)
u(p)
\varepsilon_\nu^*(k')\varepsilon_\mu(k).
\end{aligned}
$$

Equivalently,

$$
\mathcal M
=
-e^2\varepsilon_\nu^*(k')\varepsilon_\mu(k)
\overline u(p')
\left[
\gamma^\nu\frac{(p+k)\!\!\!/+m}{s-m^2+i\epsilon}\gamma^\mu
+
\gamma^\mu\frac{(p-k')\!\!\!/+m}{u-m^2+i\epsilon}\gamma^\nu
\right]
u(p).
$$

The overall sign is conventional and drops out of the unpolarized cross section. The relative sign and the ordering of gamma matrices do not drop out.

## Ward identity

The amplitude must vanish if either external photon polarization is replaced by its momentum. This is the tree-level Ward identity.

Replace the incoming polarization by $k_\mu$. The relevant contraction is

$$
\overline u(p')
\left[
\gamma^\nu\frac{(p+k)\!\!\!/+m}{s-m^2}k\!\!\!/
+
k\!\!\!/\frac{(p-k')\!\!\!/+m}{u-m^2}\gamma^\nu
\right]
u(p).
$$

For the first term, use

$$
k\!\!\!/=(p+k)\!\!\!/-m-(p\!\!\!/-m),
$$

and $(p\!\!\!/-m)u(p)=0$. Then

$$
\frac{(p+k)\!\!\!/+m}{s-m^2}k\!\!\!/\,u(p)=u(p).
$$

For the second term, write

$$
k\!\!\!/=p'\!\!\!/-(p-k')\!\!\!/,
$$

and use $\overline u(p')(p'\!\!\!/-m)=0$. This gives

$$
\overline u(p')k\!\!\!/\frac{(p-k')\!\!\!/+m}{u-m^2}=-\overline u(p').
$$

The two terms cancel. Thus

$$
\mathcal M(\varepsilon_\mu(k)\to k_\mu)=0.
$$

The same argument applies to the outgoing photon. This cancellation is the key structural lesson of the page: gauge invariance is a property of the complete amplitude, not of each diagram separately.

## Spin and polarization average

For the unpolarized squared amplitude, average over the two initial electron spins and the two initial photon polarizations, and sum over the final ones:

$$
\overline{|\mathcal M|^2}
=
\frac14\sum_{s,s',\lambda,\lambda'}|\mathcal M|^2.
$$

Because the Ward identity has been checked, the photon polarization sums may be evaluated using

$$
\sum_\lambda \varepsilon_\mu(k,\lambda)\varepsilon_\nu^*(k,\lambda)
\to
-\eta_{\mu\nu},
$$

with the understanding that unphysical longitudinal pieces decouple from the full amplitude.

The standard invariant result is

$$
\overline{|\mathcal M|^2}
=
2e^4
\left[
\frac{s-m^2}{m^2-u}
+
\frac{m^2-u}{s-m^2}
+4m^2\left(\frac{1}{s-m^2}-\frac{1}{m^2-u}\right)
+4m^4\left(\frac{1}{s-m^2}-\frac{1}{m^2-u}\right)^2
\right].
$$

This expression is often less memorable than the lab-frame result, but it is a good invariant check on signs. The denominators $s-m^2$ and $m^2-u$ are positive in the physical electron-rest-frame scattering region.

## Electron-rest-frame kinematics

Let the incoming electron be at rest,

$$
p=(m,\mathbf 0),
$$

and write the photon energies as

$$
k^0=\omega,
\qquad
k'^0=\omega'.
$$

The scattering angle $\theta$ is the angle between $\mathbf k$ and $\mathbf k'$. Momentum conservation and $p'^2=m^2$ give

$$
(p+k-k')^2=m^2.
$$

Using $k^2=k'^2=0$, this becomes

$$
2p\cdot(k-k')-2k\cdot k'=0.
$$

In the electron rest frame,

$$
p\cdot k=m\omega,
\qquad
p\cdot k'=m\omega',
\qquad
k\cdot k'=\omega\omega'(1-\cos\theta).
$$

Therefore

$$
m(\omega-\omega')=\omega\omega'(1-\cos\theta),
$$

or

$$
\frac{1}{\omega'}-\frac{1}{\omega}=
\frac{1-\cos\theta}{m}.
$$

Equivalently,

$$
\frac{\omega'}{\omega}
=
\frac{1}{1+\frac{\omega}{m}(1-\cos\theta)}.
$$

This is the Compton wavelength shift written in energy language.

## Klein–Nishina formula

In the electron rest frame, the invariant squared amplitude simplifies to

$$
\overline{|\mathcal M|^2}
=
2e^4
\left(
\frac{\omega'}{\omega}
+
\frac{\omega}{\omega'}
-
\sin^2\theta
\right).
$$

The two-body phase-space formula in this frame gives

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2m^2}
\left(\frac{\omega'}{\omega}\right)^2
\overline{|\mathcal M|^2}.
$$

Thus

$$
\frac{d\sigma}{d\Omega}
=
\frac{\alpha^2}{2m^2}
\left(\frac{\omega'}{\omega}\right)^2
\left(
\frac{\omega'}{\omega}
+
\frac{\omega}{\omega'}
-
\sin^2\theta
\right).
$$

This is the Klein–Nishina cross section. It is the relativistic recoil correction to classical Thomson scattering.

## Thomson limit

For photon energies much smaller than the electron mass,

$$
\omega\ll m,
$$

we have

$$
\frac{\omega'}{\omega}=1+O(\omega/m).
$$

The Klein–Nishina formula becomes

$$
\frac{d\sigma}{d\Omega}
\to
\frac{\alpha^2}{2m^2}(2-\sin^2\theta)
=
\frac{\alpha^2}{2m^2}(1+\cos^2\theta).
$$

Integrating over angles gives the Thomson total cross section,

$$
\sigma_T
=
\frac{8\pi\alpha^2}{3m^2}.
$$

The survival of a finite low-energy cross section is not obvious diagram by diagram. It depends on the cancellation of the leading gauge-noninvariant pieces between the $s$- and $u$-channel contributions.

## Common pitfalls

**Keeping only one diagram.** A single Compton diagram is not gauge invariant. The Ward identity requires the $s$- and $u$-channel diagrams together.

**Using polarization sums before checking gauge invariance.** Replacing physical polarization sums by $-\eta_{\mu\nu}$ is safe only after the amplitude is known to be transverse.

**Mixing up the two denominators.** The $s$-channel internal electron carries $p+k$, while the $u$-channel internal electron carries $p-k'$. Their denominators are $s-m^2$ and $u-m^2$.

**Forgetting recoil.** In Compton scattering, the outgoing photon energy differs from the incoming one unless the low-energy limit is taken.

**Calling the Thomson limit nonrelativistic QED without qualification.** The external electron is nonrelativistic in the low-energy limit, but the derivation still knows about antiparticle structure through the covariant QED diagrams.

**Losing the relative gamma-matrix order.** The two terms have different orderings of $\gamma^\mu$, the propagator numerator, and $\gamma^\nu$. Swapping them carelessly spoils the Ward identity.

## Relations to other pages

- [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/) introduces the QED rules used here.
- [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/) explains the general gauge-invariance logic behind the cancellation.
- [Spinor and Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/) gives the spin and photon-polarization sums used in the squared amplitude.
- [QED Electron–Positron to Muons](/perturbative-qft/model-calculation-library/qed-electron-positron-to-muons/) is the simpler $s$-channel annihilation benchmark.
- [Soft Photon Theorem](/perturbative-qft/infrared-physics-factorization/soft-photon-theorem/) explains the universal low-energy behavior of amplitudes with an extra soft photon.
- [Electroweak Corrections](/perturbative-qft/precision-observables/electroweak-corrections/) and [Fixed-Order Predictions](/perturbative-qft/precision-observables/fixed-order-predictions/) place tree-level QED results inside precision calculations.

## Research status

- **Established:** The tree-level amplitude, Ward identity, Klein–Nishina formula, and Thomson limit are standard QED results.
- **Active:** Precision Compton observables require loop corrections, polarization control, recoil and binding effects, radiative tails, and experimental resolution definitions.
- **Convention-dependent:** The overall sign of $\mathcal M$ depends on vertex and $S$-matrix conventions. The relative sign of the two diagrams and the cross section are physical.

## Exercises

### Exercise 1: Compton energy shift

Derive

$$
\frac{1}{\omega'}-\frac{1}{\omega}=\frac{1-\cos\theta}{m}
$$

for an electron initially at rest.

<details>
<summary><strong>Solution</strong></summary>

Momentum conservation gives

$$
p'=p+k-k'.
$$

Since $p'^2=p^2=m^2$ and $k^2=k'^2=0$,

$$
(p+k-k')^2=m^2
$$

implies

$$
2p\cdot(k-k')-2k\cdot k'=0.
$$

In the rest frame of the incoming electron,

$$
p\cdot k=m\omega,
\qquad
p\cdot k'=m\omega',
\qquad
k\cdot k'=\omega\omega'(1-\cos\theta).
$$

Thus

$$
m(\omega-\omega')=\omega\omega'(1-\cos\theta).
$$

Dividing by $m\omega\omega'$ gives

$$
\frac{1}{\omega'}-\frac{1}{\omega}=\frac{1-\cos\theta}{m}.
$$

</details>

### Exercise 2: Ward cancellation for the incoming photon

Show that the amplitude vanishes when $\varepsilon_\mu(k)$ is replaced by $k_\mu$.

<details>
<summary><strong>Solution</strong></summary>

The contracted spinor structure is

$$
\overline u(p')
\left[
\gamma^\nu\frac{(p+k)\!\!\!/+m}{s-m^2}k\!\!\!/
+
k\!\!\!/\frac{(p-k')\!\!\!/+m}{u-m^2}\gamma^\nu
\right]
u(p).
$$

For the first term,

$$
k\!\!\!/=(p+k)\!\!\!/-m-(p\!\!\!/-m),
$$

and $(p\!\!\!/-m)u(p)=0$. Therefore

$$
\frac{(p+k)\!\!\!/+m}{s-m^2}k\!\!\!/\,u(p)=u(p).
$$

For the second term, use momentum conservation to write

$$
k\!\!\!/=p'\!\!\!/-(p-k')\!\!\!/,
$$

so

$$
\overline u(p')k\!\!\!/\frac{(p-k')\!\!\!/+m}{u-m^2}
=-\overline u(p'),
$$

where $\overline u(p')(p'\!\!\!/-m)=0$ was used. The first term gives $+\overline u(p')\gamma^\nu u(p)$ and the second gives $-\overline u(p')\gamma^\nu u(p)$, so they cancel.

</details>

### Exercise 3: Thomson limit

Use the Klein–Nishina formula to derive the Thomson differential and total cross sections.

<details>
<summary><strong>Solution</strong></summary>

For $\omega\ll m$,

$$
\frac{\omega'}{\omega}\to1.
$$

Therefore

$$
\frac{d\sigma}{d\Omega}
\to
\frac{\alpha^2}{2m^2}(1+1-\sin^2\theta)
=
\frac{\alpha^2}{2m^2}(1+\cos^2\theta).
$$

To integrate,

$$
\int d\Omega\,(1+\cos^2\theta)
=2\pi\int_{-1}^{1}dx\,(1+x^2)
=\frac{16\pi}{3}.
$$

Thus

$$
\sigma_T
=
\frac{\alpha^2}{2m^2}\frac{16\pi}{3}
=
\frac{8\pi\alpha^2}{3m^2}.
$$

</details>

### Exercise 4: Invariant amplitude in the rest frame

Show that the invariant squared amplitude

$$
\overline{|\mathcal M|^2}
=
2e^4
\left[
\frac{s-m^2}{m^2-u}
+
\frac{m^2-u}{s-m^2}
+4m^2\left(\frac{1}{s-m^2}-\frac{1}{m^2-u}\right)
+4m^4\left(\frac{1}{s-m^2}-\frac{1}{m^2-u}\right)^2
\right]
$$

reduces to

$$
2e^4\left(\frac{\omega'}{\omega}+\frac{\omega}{\omega'}-\sin^2\theta\right)
$$

in the electron rest frame.

<details>
<summary><strong>Solution</strong></summary>

In the rest frame,

$$
s-m^2=2m\omega,
\qquad
m^2-u=2m\omega'.
$$

Thus the first two terms become

$$
\frac{s-m^2}{m^2-u}+\frac{m^2-u}{s-m^2}
=
\frac{\omega}{\omega'}+
\frac{\omega'}{\omega}.
$$

Also,

$$
\frac{1}{s-m^2}-\frac{1}{m^2-u}
=
\frac{1}{2m}\left(\frac{1}{\omega}-\frac{1}{\omega'}\right)
=-\frac{1-\cos\theta}{2m^2},
$$

where the Compton energy-shift relation was used. The last two terms are therefore

$$
-2(1-\cos\theta)+(1-\cos\theta)^2.
$$

Since

$$
-2(1-c)+(1-c)^2=c^2-1=-\sin^2\theta,
$$

with $c=\cos\theta$, the result follows.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§58–60, for spinor electrodynamics and tree-level QED scattering.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, §13.5, for Compton scattering and the Klein–Nishina calculation.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §8.7, for Compton scattering in quantum electrodynamics.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 30 and 34–35, for QED quantization and physical QED checks.

## Version history

- **2026-06-14:** Initial model-calculation page for tree-level Compton scattering, including the two QED diagrams, Ward cancellation, invariant squared amplitude, Klein–Nishina formula, and Thomson limit.
