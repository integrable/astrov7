---
title: "Vacuum Polarization"
description: "Derives the one-loop QED photon self-energy, its Ward-identity transversality, and its interpretation as vacuum screening of electric charge."
sidebar:
  label: "Vacuum Polarization"
  order: 9
level: Graduate
status: "Polished draft"
source: "Srednicki §§62, 66–68; Schwartz Chs. 16 and 19–23; Coleman lectures on QED renormalization; Weinberg Vol. I QED renormalization chapters."
topics:
  - vacuum polarization
  - photon self-energy
  - QED renormalization
  - Ward identities
  - running coupling
canonicalTopics:
  - vacuum-polarization
  - qed
  - photon-self-energy
  - charge-renormalization
researchStatus:
  established:
    - "The one-loop QED vacuum polarization is a standard perturbative calculation whose transverse tensor structure follows from the Ward–Takahashi identity."
  active:
    - "Precision vacuum polarization, hadronic contributions, threshold treatments, and infrared-safe definitions of electromagnetic observables remain important in phenomenology and precision tests."
---

## Summary

Vacuum polarization is the one-loop correction to the photon propagator caused by virtual charged particles. In spinor QED, the leading diagram is a closed fermion loop with two photon insertions:

<figure class="doc-figure" style="--figure-width: 30rem;">

![The one-loop spinor-QED vacuum-polarization diagram: an incoming photon splits into a virtual charged fermion loop and recombines into an outgoing photon.](/figures/gauge-theories-standard-model/vacuum-polarization-loop.svg)

<figcaption>

The one-loop vacuum-polarization diagram. The external photon carries momentum $k$, while the charged fermion loop carries loop momentum $\ell$. Gauge invariance forces the answer to be transverse: $k_\mu\Pi^{\mu\nu}(k)=0$.

</figcaption>
</figure>

The photon self-energy is written as

$$
i\Pi^{\mu\nu}(k)
=
 i\left(k^\mu k^\nu-k^2\eta^{\mu\nu}\right)\Pi(k^2),
$$

where this page uses the same mostly-minus metric and QED convention as the rest of the volume,

$$
D_\mu=\partial_\mu+iq_f A_\mu,
\qquad
\mathcal L_{\mathrm{int}}=-q_f A_\mu\bar\psi\gamma^\mu\psi,
$$

for a Dirac field of physical charge $q_f=eQ_f$. The one-loop result is not just “a loop correction.” It is the first place where several deep features of QED meet:

$$
\begin{aligned}
&\text{Ward identity} &&\Rightarrow\quad k_\mu\Pi^{\mu\nu}=0,\\
&\text{UV divergence} &&\Rightarrow\quad F_{\mu\nu}F^{\mu\nu}\text{ counterterm},\\
&\text{charged vacuum fluctuations} &&\Rightarrow\quad \text{screening of electric charge},\\
&\text{renormalization group} &&\Rightarrow\quad \beta(e)>0\text{ in QED}.
\end{aligned}
$$

With an on-shell subtraction $\Pi_R(0)=0$, the finite spinor-QED result is

$$
\Pi_R(k^2)
=
-\frac{q_f^2}{2\pi^2}
\int_0^1 dx\,x(1-x)
\log\frac{m^2-k^2x(1-x)-i\epsilon}{m^2}.
$$

For spacelike momentum $k^2=-Q_E^2<0$,

$$
\Pi_R(-Q_E^2)
=
-\frac{q_f^2}{2\pi^2}
\int_0^1 dx\,x(1-x)
\log\left(1+\frac{Q_E^2}{m^2}x(1-x)\right)<0.
$$

This negative sign is not a problem. With the tensor convention above, the transverse photon propagator is corrected as

$$
\frac{-i}{k^2+i\epsilon}
\longrightarrow
\frac{-i}{(k^2+i\epsilon)\left[1+\Pi_R(k^2)\right]},
$$

so a negative $\Pi_R(-Q_E^2)$ makes the effective electromagnetic interaction stronger at shorter distances.

## Prerequisites

You should read [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/), [QED Vertices](/gauge-theories-standard-model/qed/qed-vertices/), and [Ward–Takahashi Identity](/gauge-theories-standard-model/qed/ward-takahashi-identity/) first.

The calculation also assumes basic familiarity with dimensional regularization, Feynman parameters, and one-loop tensor integrals. Those tools are developed systematically in the Perturbative QFT and Scattering and Renormalization, RG, and EFT volumes; this page recalls only the pieces needed to understand the QED result.

## Core idea

A classical charge distribution changes the electric field around it. A quantum vacuum containing dynamical charged fields does something analogous: the external electromagnetic field polarizes virtual charged particle–antiparticle pairs. The photon propagator is therefore modified even in empty space.

In QED, the modification is constrained far more strongly than a generic vector two-point function. The Ward–Takahashi identity says

$$
k_\mu\Pi^{\mu\nu}(k)=0.
$$

Lorentz invariance and transversality then force the one-particle-irreducible two-photon amplitude to have the form

$$
\Pi^{\mu\nu}(k)
=
\left(k^\mu k^\nu-k^2\eta^{\mu\nu}\right)\Pi(k^2).
$$

This is the structural statement. The loop integral determines the scalar function $\Pi(k^2)$.

The physical interpretation is simple but treacherous in sign conventions. At long distances, a test charge is surrounded by a cloud of virtual charges that partially screens it. At shorter distances, one penetrates more of the cloud and measures a larger effective charge. This is why QED has a positive one-loop beta function.

## Setup and conventions

The spinor-QED Lagrangian for a Dirac field of charge $q_f$ is

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-q_f A_\mu\bar\psi\gamma^\mu\psi.
$$

The photon–fermion vertex is

$$
-iq_f\gamma^\mu.
$$

The fermion propagator is

$$
\frac{i(p\!\!/+m)}{p^2-m^2+i\epsilon}.
$$

The one-loop photon self-energy is defined by the one-particle-irreducible two-photon amplitude

$$
i\Pi^{\mu\nu}(k).
$$

There are two common sign conventions for the scalar function $\Pi(k^2)$. This page uses

$$
i\Pi^{\mu\nu}(k)
=
 i\left(k^\mu k^\nu-k^2\eta^{\mu\nu}\right)\Pi(k^2).
$$

With this choice, the transverse part of the Dyson-resummed photon propagator is

$$
D_{\mu\nu}^{T}(k)
=
\frac{-iP^T_{\mu\nu}}{(k^2+i\epsilon)\left[1+\Pi(k^2)\right]},
\qquad
P^T_{\mu\nu}=\eta_{\mu\nu}-\frac{k_\mu k_\nu}{k^2}.
$$

If a source uses instead

$$
\Pi^{\mu\nu}(k)=\left(k^2\eta^{\mu\nu}-k^\mu k^\nu\right)\widehat\Pi(k^2),
$$

then $\widehat\Pi=-\Pi$. Do not mix the two scalar functions mid-calculation. That path is paved with tiny, vicious minus signs.

## The one-loop amplitude

The spinor loop gives

$$
i\Pi^{\mu\nu}(k)
=
(-1)(-iq_f)^2
\int\frac{d^d\ell}{(2\pi)^d}
\operatorname{tr}\left[
\gamma^\mu
\frac{i(\ell\!\!/+m)}{\ell^2-m^2+i\epsilon}
\gamma^\nu
\frac{i(\ell\!\!/+k\!\!/+m)}{(\ell+k)^2-m^2+i\epsilon}
\right].
$$

The factor $(-1)$ is the closed fermion-loop sign. The result is proportional to $q_f^2$, so the sign of the particle's charge does not matter for vacuum polarization. Electrons and positrons polarize the vacuum just as strongly as a hypothetical unit-charged Dirac particle with opposite charge convention.

After combining denominators with

$$
\frac{1}{ab}
=
\int_0^1 dx\,\frac{1}{[xa+(1-x)b]^2},
$$

shift the loop momentum to

$$
r=\ell+xk,
\qquad
\Delta=m^2-k^2x(1-x).
$$

Odd powers of $r$ integrate to zero. The numerator decomposes into a part proportional to $r^\mu r^\nu$ and a part built from $k^\mu k^\nu$, $\eta^{\mu\nu}$, and $m^2$. Dimensional regularization then uses

$$
\int\frac{d^d r}{(2\pi)^d}
\frac{r^\mu r^\nu}{(r^2-\Delta+i\epsilon)^2}
=
\frac{\eta^{\mu\nu}}{d}
\int\frac{d^d r}{(2\pi)^d}
\frac{r^2}{(r^2-\Delta+i\epsilon)^2}.
$$

A gauge-invariant regulator is doing important work here. It prevents the calculation from generating a spurious photon mass term proportional to $\eta^{\mu\nu}m^2$ with no accompanying $k^2$.

## Transversality before the final integral

The Ward identity can be seen directly from the integrand. Contract the first vertex with the external momentum:

$$
k_\mu\gamma^\mu
=
(\ell\!\!/+k\!\!/-m)-(\ell\!\!/-m).
$$

Inserting this into the loop turns the contracted vertex into a difference of inverse propagators. Schematically,

$$
k_\mu\Pi^{\mu\nu}(k)
\sim
\int d^d\ell\,\operatorname{tr}
\left[
S(\ell)\left(S^{-1}(\ell+k)-S^{-1}(\ell)\right)S(\ell+k)\gamma^\nu
\right].
$$

The two terms differ by a shift of loop momentum. If the regulator respects shifts of the loop integration variable, they cancel:

$$
k_\mu\Pi^{\mu\nu}(k)=0.
$$

This argument is more valuable than the final answer. It explains why any nontransverse term in a QED vacuum-polarization calculation should be treated as a diagnostic failure, not as a new photon mass.

:::note[Dimensional regularization and gauge invariance]
Dimensional regularization preserves the momentum-shift property needed above and is therefore well adapted to perturbative gauge theory. A hard cutoff can obscure transversality unless implemented with great care. A careless cutoff can appear to generate a photon mass, which must be removed by enforcing the Ward identity.
:::

## Renormalized scalar function

The divergent part of the one-loop result is local. In dimensional regularization, with $d=4-2\epsilon$, it has the form

$$
\Pi_{\mathrm{bare}}(k^2)
=
-\frac{q_f^2}{12\pi^2}
\left(
\frac{1}{\epsilon}+\text{scheme constants}
\right)
+\text{finite momentum-dependent terms}.
$$

The divergence is independent of $k^2$ after the transverse tensor has been factored out. Therefore it renormalizes the Maxwell kinetic term,

$$
-\frac14F_{\mu\nu}F^{\mu\nu},
$$

not a photon mass term.

An on-shell subtraction fixes the physical long-distance charge by imposing

$$
\Pi_R(0)=0.
$$

With that subtraction,

$$
\Pi_R(k^2)
=
-\frac{q_f^2}{2\pi^2}
\int_0^1 dx\,x(1-x)
\log\frac{m^2-k^2x(1-x)-i\epsilon}{m^2}.
$$

For small $|k^2|\ll m^2$, expand the logarithm:

$$
\Pi_R(k^2)
=
\frac{q_f^2}{2\pi^2}
\int_0^1 dx\,x(1-x)
\left[\frac{k^2x(1-x)}{m^2}+O(k^4/m^4)\right].
$$

Since

$$
\int_0^1 dx\,x^2(1-x)^2=\frac{1}{30},
$$

we get

$$
\Pi_R(k^2)
=
\frac{q_f^2}{60\pi^2}\frac{k^2}{m^2}+O(k^4/m^4).
$$

At momenta far below a charged particle's mass, its vacuum-polarization effect is suppressed by powers of $k^2/m^2$. This is the elementary decoupling intuition that later EFT pages make systematic.

For large spacelike momentum $k^2=-Q_E^2$ with $Q_E^2\gg m^2$,

$$
\Pi_R(-Q_E^2)
=
-\frac{q_f^2}{12\pi^2}
\log\frac{Q_E^2}{m^2}
+\frac{5q_f^2}{36\pi^2}
+O(m^2/Q_E^2).
$$

Equivalently, for a unit-charged Dirac fermion with $q_f=e$ and $\alpha=e^2/(4\pi)$,

$$
\Pi_R(-Q_E^2)
=
-\frac{\alpha}{3\pi}\log\frac{Q_E^2}{m^2}
+\frac{5\alpha}{9\pi}
+O(m^2/Q_E^2).
$$

The logarithm is the seed of the running electric charge.

## Effective charge from the corrected propagator

When a photon is exchanged between two conserved external currents, longitudinal terms in the photon propagator do not contribute. The tree-level exchange amplitude contains

$$
\frac{-i}{k^2+i\epsilon}J_\mu J'^\mu.
$$

Including the vacuum-polarization insertions gives the geometric series

$$
\frac{-i}{k^2+i\epsilon}
\left[1-\Pi_R(k^2)+\Pi_R(k^2)^2-\cdots\right]
=
\frac{-i}{(k^2+i\epsilon)\left[1+\Pi_R(k^2)\right]}.
$$

This motivates the effective charge definition

$$
e_{\mathrm{eff}}^2(k^2)
=
\frac{e^2}{1+\Pi_R(k^2)}
$$

in this tensor convention. For spacelike momentum,

$$
e_{\mathrm{eff}}^2(Q_E)
\equiv
e_{\mathrm{eff}}^2(k^2=-Q_E^2)
=
\frac{e^2}{1+\Pi_R(-Q_E^2)}.
$$

Because $\Pi_R(-Q_E^2)<0$ at large $Q_E$, the denominator decreases and the effective charge increases at short distances.

This is screening. The long-distance charge is screened by virtual charged pairs. Short-distance probes see through part of the screening cloud and measure a larger charge.

## Thresholds and imaginary parts

The logarithm develops an imaginary part when the photon momentum can create a real charged pair:

$$
k^2>4m^2.
$$

This branch cut is not an accident of the integral. It reflects the physical process

$$
\gamma^*\to\psi\bar\psi.
$$

The imaginary part of the vacuum polarization is related by unitarity to the total rate for producing charged pairs from a virtual photon. This connection between analytic structure and physical production thresholds recurs throughout scattering theory, dispersion relations, and precision electroweak physics.

For the running-coupling discussion, it is usually cleanest to use spacelike momenta, where $Q_E^2=-k^2>0$ and no pair-production cut is crossed.

## Scalar QED comparison

A charged complex scalar also contributes to vacuum polarization. The calculation differs in two important ways.

First, the one-photon scalar vertex contains momenta rather than a gamma matrix. Second, the scalar-QED seagull vertex contributes a separate loop diagram. Both diagrams are required for transversality:

$$
k_\mu\Pi^{\mu\nu}_{\mathrm{scalar}}(k)=0.
$$

At one loop, a complex scalar of physical charge $q_s$ contributes one quarter as much to the QED beta function as a Dirac fermion of the same charge:

$$
\beta(e)_{\mathrm{complex\ scalar}}
=
\frac{e^3Q_s^2}{48\pi^2},
\qquad
\beta(e)_{\mathrm{Dirac\ fermion}}
=
\frac{e^3Q_f^2}{12\pi^2}.
$$

The different coefficient reflects different spin and statistics, not a different gauge principle. Both effects are transverse when calculated correctly.

## Common pitfalls

**Forgetting the tensor convention.** Some sources define $\Pi^{\mu\nu}$ with $k^2\eta^{\mu\nu}-k^\mu k^\nu$ instead of $k^\mu k^\nu-k^2\eta^{\mu\nu}$. The scalar function changes sign. The physics does not.

**Calling a nontransverse term a photon mass.** In QED, gauge invariance forbids a local photon mass term. A nontransverse one-loop answer usually means the regulator or algebra broke the Ward identity.

**Dropping the closed-fermion-loop sign.** The factor $(-1)$ from a closed fermion loop is essential. It combines with vertex and propagator factors to give the standard sign and beta function.

**Confusing charge sign with charge squared.** Vacuum polarization depends on $q_f^2$. An electron and a positron contribute the same way to the photon self-energy.

**Thinking the loop makes photons massive.** Vacuum polarization changes the kinetic term and the propagation of virtual photons. It does not turn QED into Proca theory.

**Using the on-shell formula above as if it were an MS formula.** The condition $\Pi_R(0)=0$ is an on-shell subtraction. In $\overline{\mathrm{MS}}$, one subtracts only the pole and scheme constants, and the remaining finite logarithm is written in terms of a renormalization scale $\mu$.

**Ignoring thresholds.** A single formula may have different interpretations in spacelike and timelike regions. Above $k^2=4m^2$, the logarithm knows about real pair production.

## Relations to other pages

- [Ward–Takahashi Identity](/gauge-theories-standard-model/qed/ward-takahashi-identity/) explains why $k_\mu\Pi^{\mu\nu}=0$ must hold.
- [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/) gives the free propagator that vacuum polarization corrects.
- [QED Vertices](/gauge-theories-standard-model/qed/qed-vertices/) fixes the spinor and scalar QED vertices used in the loop calculation.
- [Running Electric Charge](/gauge-theories-standard-model/qed/running-electric-charge/) converts the logarithmic part of vacuum polarization into the QED beta function.
- Later Yang–Mills pages compare this matter-loop screening with gauge-boson antiscreening.

## Research status

The one-loop spinor-QED vacuum polarization is established textbook physics. Its tensor structure, divergence, threshold behavior, and role in charge renormalization are standard.

The broader subject remains highly relevant. Precision electromagnetic observables require multi-loop vacuum-polarization effects, careful treatment of charged thresholds, and in some contexts hadronic vacuum polarization, where the low-energy strong interaction cannot be computed by elementary perturbative QED alone. Those precision topics are not conceptual obstacles to this page; they are places where this simple one-loop idea grows fangs.

## Exercises

1. **Trace numerator.** Starting from the spinor loop, show that

   $$
   \operatorname{tr}[\gamma^\mu(\ell\!\!/+m)\gamma^\nu(\ell\!\!/+k\!\!/+m)]
   =
   4\left[\ell^\mu(\ell+k)^\nu+\ell^\nu(\ell+k)^\mu-\eta^{\mu\nu}\ell\cdot(\ell+k)+m^2\eta^{\mu\nu}\right].
   $$

   <details><summary><strong>Solution</strong></summary>

   Use

   $$
   \operatorname{tr}(\gamma^\mu\gamma^\alpha\gamma^\nu\gamma^\beta)
   =
   4(\eta^{\mu\alpha}\eta^{\nu\beta}-\eta^{\mu\nu}\eta^{\alpha\beta}+\eta^{\mu\beta}\eta^{\alpha\nu})
   $$

   and $\operatorname{tr}(\gamma^\mu\gamma^\nu)=4\eta^{\mu\nu}$. Terms with an odd number of gamma matrices vanish. Therefore

   $$
   \operatorname{tr}[\gamma^\mu\ell\!\!/\gamma^\nu(\ell\!\!/+k\!\!/)]
   =
   4[\ell^\mu(\ell+k)^\nu+\ell^\nu(\ell+k)^\mu-\eta^{\mu\nu}\ell\cdot(\ell+k)],
   $$

   while the $m^2$ term gives $4m^2\eta^{\mu\nu}$.

   </details>

2. **Low-momentum expansion.** Derive

   $$
   \Pi_R(k^2)
   =
   \frac{q_f^2}{60\pi^2}\frac{k^2}{m^2}+O(k^4/m^4)
   $$

   from the on-shell-subtracted integral.

   <details><summary><strong>Solution</strong></summary>

   Expand

   $$
   \log\left(1-\frac{k^2}{m^2}x(1-x)\right)
   =
   -\frac{k^2}{m^2}x(1-x)+O(k^4/m^4).
   $$

   Since

   $$
   \Pi_R(k^2)
   =
   -\frac{q_f^2}{2\pi^2}\int_0^1 dx\,x(1-x)
   \log\left(1-\frac{k^2}{m^2}x(1-x)\right),
   $$

   the leading term is

   $$
   \frac{q_f^2}{2\pi^2}\frac{k^2}{m^2}
   \int_0^1 dx\,x^2(1-x)^2.
   $$

   The integral is

   $$
   \int_0^1 dx\,(x^2-2x^3+x^4)
   =
   \frac13-\frac12+\frac15=\frac{1}{30}.
   $$

   Thus the coefficient is $q_f^2/(60\pi^2)$.

   </details>

3. **Large-spacelike logarithm.** For $Q_E^2\gg m^2$, show that

   $$
   \int_0^1 dx\,x(1-x)\log\left(1+\frac{Q_E^2}{m^2}x(1-x)\right)
   =
   \frac16\log\frac{Q_E^2}{m^2}-\frac{5}{18}+O(m^2/Q_E^2).
   $$

   <details><summary><strong>Solution</strong></summary>

   At leading order,

   $$
   \log\left(1+\frac{Q_E^2}{m^2}x(1-x)\right)
   =
   \log\frac{Q_E^2}{m^2}+\log[x(1-x)]+O(m^2/Q_E^2)
   $$

   away from endpoint regions. The endpoint corrections are power-suppressed for this weighted integral. Then

   $$
   \int_0^1 dx\,x(1-x)=\frac16.
   $$

   Also,

   $$
   \int_0^1 dx\,x(1-x)\log[x(1-x)]
   =2\int_0^1 dx\,x(1-x)\log x.
   $$

   Using

   $$
   \int_0^1 dx\,x^n\log x=-\frac{1}{(n+1)^2},
   $$

   we find

   $$
   2\left(-\frac14+\frac19\right)=-\frac{5}{18}.
   $$

   </details>

4. **Why no photon mass?** Explain why a term proportional only to $\eta^{\mu\nu}m^2$ in $\Pi^{\mu\nu}$ would violate the Ward identity.

   <details><summary><strong>Solution</strong></summary>

   A photon mass contribution to the inverse propagator has tensor structure proportional to $\eta^{\mu\nu}m_\gamma^2$. Contracting with $k_\mu$ gives

   $$
   k_\mu\eta^{\mu\nu}m_\gamma^2=k^\nu m_\gamma^2,
   $$

   which is not zero for generic $k^\nu$. Therefore such a term is not transverse. The allowed vacuum-polarization tensor must be proportional to $k^\mu k^\nu-k^2\eta^{\mu\nu}$, whose contraction with $k_\mu$ vanishes identically.

   </details>

## References

- Srednicki, *Quantum Field Theory*, §§62 and 66–68, for QED loop corrections, beta functions, and Ward identities.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 16 and Chs. 19–23, for vacuum polarization, renormalized perturbation theory, and running couplings.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on QED renormalization and Ward identities.
- Weinberg, *The Quantum Theory of Fields*, Vol. I, for the systematic relation between photon vacuum polarization, charge renormalization, and scattering.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*, Chs. 6–7, for a standard spinor-QED calculation and renormalization discussion.

## Version history

- **2026-06-17:** Initial polished draft. Derives the one-loop spinor-QED vacuum polarization, fixes the tensor-sign convention, explains transversality, and connects the spacelike logarithm to electric-charge screening.
