---
title: "Eikonal Approximation"
description: "How soft gauge bosons couple universally to energetic external particles through eikonal denominators, classical currents, and Wilson lines."
sidebar:
  label: "Eikonal Approximation"
  order: 5
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. I on infrared effects; Srednicki §26; Schwartz ch. 20; Sterman on factorization"
topics:
  - infrared divergences
  - eikonal approximation
  - soft factorization
  - Wilson lines
  - soft radiation
canonicalTopics:
  - eikonal-approximation
  - eikonal-factor
  - soft-factorization
  - wilson-line-soft-limit
researchStatus:
  established:
    - "The leading eikonal approximation for soft gauge-boson emission is a standard consequence of the near-on-shell propagation of energetic external charged particles."
  active:
    - "Systematic subleading-power factorization, Glauber exchange, non-Abelian exponentiation, and eikonal methods for realistic collider observables remain active research topics."
---

## Summary

The **eikonal approximation** is the leading-power approximation to how a soft gauge boson couples to a hard charged particle. If a particle with momentum $p^\mu$ emits a soft photon of momentum $k^\mu$, with $k$ much smaller than the hard scale $Q$, the detailed spin and recoil structure of the external line collapses to the universal factor

$$
 eQ\,\frac{p^\mu}{p\cdot k}
$$

up to signs and $i0$ prescriptions fixed by whether the line is incoming or outgoing. Contracting with the photon polarization gives

$$
 eQ\,\frac{p\cdot\varepsilon^*(k)}{p\cdot k}.
$$

For a process with many external charged particles, the leading soft current is

$$
J^\mu_{\rm eik}(k)
=
e\sum_i \eta_i Q_i\frac{p_i^\mu}{p_i\cdot k},
$$

where $Q_i$ is the charge in units of $e$, and $\eta_i=+1$ for an outgoing charged leg and $\eta_i=-1$ for an incoming charged leg. The same approximation, with $eQ_i$ replaced by $gT_i^a$, is the starting point for soft-gluon factorization in non-Abelian gauge theory.

The eikonal approximation is the local engine behind soft divergences, the soft-photon theorem, Bloch–Nordsieck cancellation, Wilson-line soft functions, and many factorization formulas. Its message is simple: very long-wavelength radiation cannot resolve the microscopic details of the hard interaction. It sees only the charges, color representations, and directions of the energetic particles.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 55rem;">

![A soft gauge boson emitted from a hard external line reduces to an eikonal factor and can be represented by a Wilson line](/figures/perturbative-qft/eikonal-approximation.svg)

<figcaption>

The eikonal approximation replaces the exact external-line emission factor by the leading soft denominator $1/(p\cdot k)$ times the hard momentum $p^\mu$. In this limit the hard particle behaves like a classical straight-line source, which is why Wilson lines naturally appear in soft factorization.

</figcaption>
</figure>

## Prerequisites

You should know [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/), [Bloch–Nordsieck Theorem](/perturbative-qft/infrared-physics-factorization/bloch-nordsieck-theorem/), [Gauge Fixing for Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/gauge-fixing-for-perturbation-theory/), and [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/). For conventions, use [Conventions and Notation](/perturbative-qft/conventions/) and the qft.org mostly-minus metric.

## Core idea

A soft photon has wavelength much larger than the length scale of the hard scattering. If the hard interaction has characteristic momentum transfer $Q$, and the emitted photon has energy $\omega\ll Q$, then the photon cannot resolve the difference between one hard vertex and another inside the short-distance process. To leading order, it couples as though each energetic charged particle were a classical current moving on a straight line.

This is why the soft approximation is universal. The hard amplitude knows about spin, couplings, angles, loop corrections, and short-distance dynamics. The leading soft factor knows only

```txt
external momentum direction,
charge or color generator,
incoming/outgoing orientation,
soft momentum and polarization.
```

The approximation is called “eikonal” by analogy with geometric optics: the hard particle follows a nearly undeflected ray, while the soft field accumulates a phase along that ray. In gauge theory that phase is a Wilson line.

## Setup and conventions

Consider a hard process with external momenta $p_i^\mu$ and an additional soft photon of momentum $k^\mu$. The soft scaling is

$$
k^\mu\sim \lambda Q,
\qquad
\lambda\ll1,
$$

while hard momenta satisfy $p_i^\mu\sim Q$. For real photons,

$$
k^2=0,
\qquad
k^0=\omega>0.
$$

For a massive external particle,

$$
p_i^2=m_i^2,
$$

and

$$
(p_i+k)^2-m_i^2
=2p_i\cdot k+k^2
=2p_i\cdot k.
$$

Since $p_i\cdot k\sim Q\omega$, the propagator next to the external leg becomes singular as $\omega\to0$. This singular near-on-shell propagator is the entire reason the external-line emission dominates the leading soft limit.

We use the sign convention

$$
\eta_i=
\begin{cases}
+1, & \text{outgoing charged particle},\\
-1, & \text{incoming charged particle}.
\end{cases}
$$

The compact leading soft current is then

$$
J_{\rm eik}^\mu(k)
=e\sum_i\eta_iQ_i\frac{p_i^\mu}{p_i\cdot k}.
$$

For real emission the $i0$ prescription does not affect the singular factor. For virtual soft exchange it matters. A common schematic prescription is

$$
\frac{1}{p_i\cdot k}
\longrightarrow
\frac{1}{p_i\cdot k+i0\,\eta_i},
$$

but detailed sign conventions depend on momentum routing and whether all momenta are taken incoming or physical.

## Scalar derivation from an external line

The cleanest derivation uses scalar QED. Suppose a charged scalar with outgoing on-shell momentum $p$ emits a soft photon of momentum $k$ from the external leg adjacent to a hard subdiagram $\mathcal H$. The scalar-photon vertex contributes a factor proportional to

$$
-ieQ(2p+k)^\mu,
$$

and the nearly on-shell scalar propagator contributes

$$
\frac{i}{(p+k)^2-m^2+i0}
=
\frac{i}{2p\cdot k+i0},
$$

where $k^2=0$ and $p^2=m^2$ were used. Multiplying and keeping only the leading term as $k\to0$ gives

$$
(-ieQ)(2p+k)^\mu
\frac{i}{(p+k)^2-m^2+i0}
\simeq
 eQ\frac{p^\mu}{p\cdot k+i0}.
$$

The exact sign can move depending on the orientation convention for external legs. The invariant content is the same: the leading soft emission from that external charged leg is proportional to $p^\mu/(p\cdot k)$.

After contraction with the photon polarization, the factor becomes

$$
eQ\frac{p\cdot\varepsilon^*(k)}{p\cdot k}.
$$

The hard subdiagram is not touched at leading power. Hence the amplitude factorizes:

$$
\mathcal M_{n+1}^{\rm soft}
\simeq
\left[eQ\frac{p\cdot\varepsilon^*(k)}{p\cdot k}\right]
\mathcal M_n
$$

for emission from this one external leg.

## Spinor derivation

For a Dirac fermion, the external-line emission factor contains the numerator algebra

$$
\overline u(p)(-ieQ\gamma^\mu)
\frac{i(p\!\!\!/+k\!\!\!/+m)}{(p+k)^2-m^2+i0}.
$$

Using the on-shell Dirac equation

$$
\overline u(p)(p\!\!\!/-m)=0,
$$

and the Clifford algebra, one obtains

$$
\overline u(p)\gamma^\mu(p\!\!\!/+m)
=2p^\mu\overline u(p).
$$

The $k\!\!\!/$ term in the numerator is suppressed by one power of the soft momentum compared with the leading denominator. Therefore

$$
\overline u(p)(-ieQ\gamma^\mu)
\frac{i(p\!\!\!/+k\!\!\!/+m)}{(p+k)^2-m^2+i0}
\simeq
 eQ\frac{p^\mu}{p\cdot k+i0}\overline u(p),
$$

again up to the same convention-dependent global orientation sign.

This is important: the leading eikonal factor is spin independent. Spin appears at subleading order in the soft expansion. That is why the leading soft-photon theorem has the same form for charged scalars and charged fermions.

## Why internal emissions are not leading soft singularities

A photon can also be emitted from an internal charged line. In a generic diagram, an internal line carries momentum $q$ that is not on shell. Its denominator changes as

$$
(q+k)^2-m^2
=q^2-m^2+2q\cdot k+k^2.
$$

If $q^2-m^2$ is of order $Q^2$, this denominator does not become small when $k\to0$. The internal emission is therefore finite in the strict soft limit.

This is the basic separation:

| Emission region | Denominator behavior | Leading soft role |
|---|---:|---|
| External on-shell charged leg | $2p\cdot k\sim Q\omega$ | Singular and universal |
| Generic internal off-shell line | $q^2-m^2+O(Q\omega)$ | Finite and process-dependent |
| Internal line forced on shell by another singular limit | Needs separate factorization | Can overlap with collinear or threshold regions |

The last row is where the analysis becomes more subtle. Soft factorization is cleanest when the only singular soft attachments are to external hard lines. In realistic gauge theories, soft, collinear, Glauber, and threshold regions can overlap. Factorization theorems are the systematic way of separating those regions without double counting.

## Eikonal current and gauge invariance

For many external charged particles, the leading soft emission amplitude is

$$
\mathcal M_{n+1}^{\rm soft}
\simeq
\varepsilon_\mu^*(k)J_{\rm eik}^\mu(k)\mathcal M_n,
$$

with

$$
J_{\rm eik}^\mu(k)
=e\sum_i\eta_iQ_i\frac{p_i^\mu}{p_i\cdot k}.
$$

Gauge invariance of the emitted photon requires the amplitude to vanish when

$$
\varepsilon^\mu(k)\to k^\mu.
$$

The eikonal current gives

$$
k_\mu J_{\rm eik}^\mu(k)
=e\sum_i\eta_iQ_i.
$$

Thus the leading soft factor is gauge invariant precisely when total charge is conserved between the incoming and outgoing hard states:

$$
\sum_i\eta_iQ_i=0.
$$

This is one of the nicest sanity checks in perturbative QFT. The same formula that produces the infrared divergence also knows about charge conservation.

For non-Abelian gauge theory, the abelian charges $Q_i$ become color generators $T_i^a$ acting on the color indices of external leg $i$:

$$
J_{\rm eik}^{a\mu}(k)
=g\sum_i\eta_i\frac{p_i^\mu}{p_i\cdot k}T_i^a.
$$

Gauge invariance becomes color-charge conservation acting on the hard amplitude,

$$
\sum_i\eta_i T_i^a\,\mathcal M_n=0,
$$

for a color-singlet gauge-invariant amplitude. Unlike QED, the color generators do not commute in general, so multiple soft-gluon emission requires path ordering and Wilson lines.

## Classical-current interpretation

The eikonal factor is not a mysterious quantum accident. A hard charged particle moving almost undeflected behaves like a classical current. For a particle following a straight worldline

$$
x^\mu(s)=p^\mu s,
$$

the current has the schematic form

$$
j^\mu(x)=eQ\int ds\,p^\mu\delta^{(4)}(x-p s).
$$

Fourier transforming gives

$$
j^\mu(k)
=eQp^\mu\int ds\,e^{is p\cdot k}.
$$

Depending on whether the line is incoming, outgoing, semi-infinite, or infinite, the $s$ integral gives a pole prescription and a delta-function piece. The pole part is the eikonal denominator

$$
\frac{p^\mu}{p\cdot k+i0}.
$$

So the leading soft field is emitted by the classical trajectory of the hard charge. Quantum recoil, spin, and finite-size information live at subleading power.

## Wilson-line interpretation

The eikonal coupling of a hard particle to a soft gauge field is encoded by a Wilson line. For an outgoing abelian charged particle moving in direction $p^\mu$, the Wilson line is schematically

$$
W_p
=
\exp\left[ieQ\int_0^\infty ds\,p\cdot A(sp)\right].
$$

Expanding to first order in $A_\mu$ gives

$$
ieQ\int_0^\infty ds\,p^\mu A_\mu(sp),
$$

and in momentum space this produces

$$
eQ\frac{p^\mu}{p\cdot k+i0}.
$$

For non-Abelian gauge theory the Wilson line becomes path ordered:

$$
W_p
=\mathcal P\exp\left[ig\int_0^\infty ds\,p\cdot A^a(sp)T^a\right].
$$

This is the bridge from elementary soft-emission diagrams to modern factorization. A soft function is often a vacuum matrix element of several Wilson lines, one for each energetic external direction. The hard function knows short-distance physics; the Wilson lines know universal soft radiation.

## Power counting

Let $k\sim\lambda Q$ with $\lambda\ll1$. For a hard on-shell external leg,

$$
(p+k)^2-m^2\sim Q^2\lambda.
$$

The soft emission factor scales as

$$
\frac{p\cdot\varepsilon}{p\cdot k}
\sim
\frac{Q}{Q^2\lambda}
\sim
\frac{1}{Q\lambda}.
$$

The amplitude is therefore singular like $1/\omega$. Squaring and multiplying by soft phase space gives

$$
d\Pi_k\,|S(k)|^2
\sim
\omega d\omega\,\frac{1}{\omega^2}
=
\frac{d\omega}{\omega}.
$$

That is the logarithmic soft divergence.

The eikonal approximation therefore supplies both the factorized soft amplitude and the infrared power counting behind the divergence.

## What the approximation does not include

The eikonal approximation is leading power in the soft expansion. It deliberately ignores effects suppressed by powers of $k/Q$. These include:

- recoil of the hard particle;
- spin-dependent magnetic couplings;
- derivatives of the hard amplitude with respect to external momenta;
- subleading soft factors;
- finite detector-resolution effects;
- pure collinear dynamics not captured by the soft limit alone.

This is not a defect. It is the point of an approximation. Leading eikonal physics is universal because it forgets these details. Subleading soft physics is richer because some of the details return.

## Common pitfalls

**Treating the eikonal factor as a full amplitude.** The eikonal factor multiplies a hard amplitude. By itself it is not the whole physical process.

**Forgetting incoming–outgoing signs.** The charge of an incoming particle contributes with the opposite sign from an outgoing particle in the physical-momentum convention used here.

**Dropping the hard scale.** The approximation assumes $k\ll Q$. A photon can be low energy relative to one scale but not another; the relevant hard scale must be identified.

**Confusing soft and collinear limits.** Soft means $k^\mu\to0$. Collinear means a massless momentum becomes parallel to another massless momentum. They can overlap but are not the same limit.

**Assuming spin never matters.** Spin does not affect the leading eikonal factor, but it enters at subleading order.

**Ignoring gauge invariance.** Replacing $\varepsilon$ by $k$ is the fastest check. The eikonal current is gauge invariant only after summing all external charged legs and using charge conservation.

## Relations to other pages

- [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) uses the eikonal factor to explain the logarithmic soft singularity.
- [Soft Photon Theorem](/perturbative-qft/infrared-physics-factorization/soft-photon-theorem/) upgrades the eikonal approximation into a universal amplitude theorem.
- [Bloch–Nordsieck Theorem](/perturbative-qft/infrared-physics-factorization/bloch-nordsieck-theorem/) uses eikonal real–virtual cancellation in inclusive QED rates.
- [KLN Theorem](/perturbative-qft/infrared-physics-factorization/kln-theorem/) places the cancellation of soft and collinear singularities in the broader degenerate-state framework.
- [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/) explains the singularities that appear when $p\cdot k$ becomes small because of angle rather than energy.
- [Gauge Parameter Independence](/perturbative-qft/gauge-theory-perturbation-theory/gauge-parameter-independence/) explains why physical predictions cannot depend on the gauge parameter used in propagators.

## Research status

- **Established:** The leading eikonal approximation is textbook-standard and follows directly from external-line propagators near the mass shell.
- **Active:** Subleading-power factorization, non-Abelian exponentiation, Glauber modes, rapidity divergences, non-global logarithms, and eikonal methods in precision collider observables remain active research areas.
- **Speculative:** The leading eikonal approximation itself is not speculative. Broader claims connecting soft factors, asymptotic symmetries, memory effects, and celestial structures require additional assumptions and belong to later pages.

## Exercises

### Exercise 1: Scalar eikonal denominator

For an outgoing scalar of mass $m$ and momentum $p$, show that emission of a real soft photon of momentum $k$ from the adjacent external line produces the denominator

$$
(p+k)^2-m^2+i0=2p\cdot k+i0.
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
p^2=m^2,
\qquad
k^2=0.
$$

Then

$$
(p+k)^2-m^2
=p^2+2p\cdot k+k^2-m^2
=2p\cdot k.
$$

The Feynman prescription gives the displayed $+i0$.

</details>

### Exercise 2: Spinor numerator at leading soft order

Use the Dirac equation to show that

$$
\overline u(p)\gamma^\mu(p\!\!\!/+m)=2p^\mu\overline u(p).
$$

<details>
<summary><strong>Solution</strong></summary>

Start from the Clifford algebra,

$$
\gamma^\mu p\!\!\!/+p\!\!\!/\gamma^\mu=2p^\mu.
$$

Thus

$$
\gamma^\mu p\!\!\!/=2p^\mu-p\!\!\!/\gamma^\mu.
$$

Multiplying on the left by $\overline u(p)$ gives

$$
\overline u(p)\gamma^\mu p\!\!\!/
=2p^\mu\overline u(p)-\overline u(p)p\!\!\!/\gamma^\mu.
$$

The outgoing spinor satisfies

$$
\overline u(p)(p\!\!\!/-m)=0,
$$

so

$$
\overline u(p)p\!\!\!/=m\overline u(p).
$$

Therefore

$$
\overline u(p)\gamma^\mu p\!\!\!/
=2p^\mu\overline u(p)-m\overline u(p)\gamma^\mu.
$$

Adding the second term from $\gamma^\mu(p\!\!\!/+m)$ gives

$$
\overline u(p)\gamma^\mu(p\!\!\!/+m)
=2p^\mu\overline u(p).
$$

</details>

### Exercise 3: Gauge-invariance check

Show that the eikonal current

$$
J_{\rm eik}^\mu(k)=e\sum_i\eta_iQ_i\frac{p_i^\mu}{p_i\cdot k}
$$

satisfies $k_\mu J_{\rm eik}^\mu=0$ if total charge is conserved.

<details>
<summary><strong>Solution</strong></summary>

Contract with $k_\mu$:

$$
k_\mu J_{\rm eik}^\mu(k)
=e\sum_i\eta_iQ_i\frac{k\cdot p_i}{p_i\cdot k}
=e\sum_i\eta_iQ_i.
$$

Charge conservation between incoming and outgoing hard states is

$$
\sum_i\eta_iQ_i=0.
$$

Therefore

$$
k_\mu J_{\rm eik}^\mu(k)=0.
$$

</details>

### Exercise 4: Soft logarithm from eikonal scaling

For a real soft photon, use

$$
d\Pi_k=\frac{d^3\mathbf k}{(2\pi)^3 2\omega}
$$

and the eikonal scaling $|S(k)|^2\sim 1/\omega^2$ to show that soft emission produces a logarithmic energy integral.

<details>
<summary><strong>Solution</strong></summary>

For a massless photon,

$$
d^3\mathbf k=\omega^2d\omega\,d\Omega.
$$

Thus

$$
d\Pi_k
=\frac{\omega^2d\omega\,d\Omega}{(2\pi)^3 2\omega}
=\frac{\omega d\omega\,d\Omega}{2(2\pi)^3}.
$$

Multiplying by $|S(k)|^2\sim1/\omega^2$ gives

$$
d\Pi_k|S(k)|^2
\sim
\frac{d\omega}{\omega}\,d\Omega.
$$

The energy integral therefore contains

$$
\int_0^{\Delta E}\frac{d\omega}{\omega},
$$

which is logarithmically singular at the lower endpoint.

</details>

### Exercise 5: First term of a Wilson line

Expand the abelian Wilson line

$$
W_p=\exp\left[ieQ\int_0^\infty ds\,p\cdot A(sp)\right]
$$

to first order in $A_\mu$ and explain why it represents one soft-photon emission from an eikonal line.

<details>
<summary><strong>Solution</strong></summary>

The first-order expansion is

$$
W_p=1+ieQ\int_0^\infty ds\,p^\mu A_\mu(sp)+O(A^2).
$$

Writing the soft field in momentum space gives a factor

$$
\int_0^\infty ds\,e^{-is p\cdot k},
$$

up to Fourier-sign conventions. This semi-infinite line integral produces the eikonal pole prescription proportional to

$$
\frac{1}{p\cdot k+i0}.
$$

Together with the numerator $p^\mu$, this is the one-photon eikonal emission factor.

</details>

## References

- F. Bloch and A. Nordsieck, “Note on the Radiation Field of the Electron,” *Physical Review* **52** (1937), for the original soft-photon cancellation idea.
- F. E. Low, “Bremsstrahlung of Very Low-Energy Quanta in Elementary Particle Collisions,” *Physical Review* **110** (1958), for the classic low-energy photon theorem.
- S. Weinberg, “Infrared Photons and Gravitons,” *Physical Review* **140** (1965), for the universal infrared soft-factor viewpoint.
- D. R. Yennie, S. C. Frautschi, and H. Suura, “The Infrared Divergence Phenomena and High-Energy Processes,” *Annals of Physics* **13** (1961), for exponentiation and infrared organization in QED.
- M. Srednicki, *Quantum Field Theory*, §26, for infrared divergences in a compact scalar/QED-oriented treatment.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 20, for soft and collinear divergences with physical cross-section examples.
- G. Sterman, *An Introduction to Quantum Field Theory*, and J. Collins, *Foundations of Perturbative QCD*, for factorization and Wilson-line perspectives.

## Version history

- **2026-06-13:** Initial polished draft for the Perturbative QFT and Scattering volume.
