---
title: "Theta Angle and Strong CP Problem"
description: "Explains the QCD theta term, topological sectors, axial rotations, the physical strong CP phase, and why its observed smallness is a major puzzle."
sidebar:
  label: "Theta Angle and Strong CP"
  order: 9
level: Graduate
status: "Polished draft"
source: "Srednicki §§93–94; Schwartz §§29.5 and 30.5; Weinberg Vol. II Chs. 22–23; Coleman, Aspects of Symmetry, Ch. 7."
topics:
  - QCD theta angle
  - strong CP problem
  - instantons
  - topological charge
  - axial anomaly
  - quark mass phases
canonicalTopics:
  - theta-angle
  - strong-cp-problem
  - qcd-topology
  - axial-anomaly
  - instantons
  - neutron-electric-dipole-moment
researchStatus:
  established:
    - "The physical QCD CP-violating parameter is the invariant combination of the bare theta angle and the phase of the quark mass determinant."
  active:
    - "The origin of the extremely small effective strong CP phase is not explained within the minimal Standard Model and remains a major motivation for axions and other ultraviolet mechanisms."
---

## Summary

QCD allows a term that is invisible in ordinary perturbation theory but physically important nonperturbatively:

$$
\mathcal L_\theta
=
\theta\,
\frac{g_s^2}{32\pi^2}
G_{\mu\nu}^A\widetilde G^{A\mu\nu},
\qquad
\widetilde G^{A\mu\nu}
=
\frac12\epsilon^{\mu\nu\rho\sigma}G_{\rho\sigma}^A.
$$

Locally, $G\widetilde G$ is a total derivative. Globally, its spacetime integral measures topological charge in Euclidean gauge-field sectors. The path integral therefore contains weights

$$
e^{i\theta Q},
\qquad
Q=
\frac{g_s^2}{32\pi^2}
\int d^4x\,
G_{\mu\nu}^A\widetilde G^{A\mu\nu}.
$$

The subtlety is that $\theta$ by itself is not always the physical parameter. Chiral rotations of quark fields shift the theta term and move phases into or out of the quark mass matrix. With a general complex quark mass matrix $M_q$, the invariant strong CP phase is conventionally written

$$
\bar\theta
=
\theta+\arg\det M_q.
$$

A nonzero $\bar\theta$ violates CP in the strong interaction. Experimentally, strong CP violation is astonishingly small, requiring roughly

$$
|\bar\theta|\ll1,
$$

in fact many orders of magnitude below a generic number of order one. The **strong CP problem** is the question:

$$
\text{Why is }\bar\theta\text{ so small?}
$$

<figure class="doc-figure" style="--figure-width: 44rem;">

![Map of the QCD theta angle, quark mass phase, axial rotations, the invariant strong CP phase, and the main classes of proposed solutions.](/figures/gauge-theories-standard-model/qcd-theta-strong-cp-map.svg)

<figcaption>

The bare theta angle and the complex phase of the quark mass determinant are separately convention-dependent. Axial rotations move phase between them. The invariant combination $\bar\theta=\theta+\arg\det M_q$ controls strong CP violation. Its tiny observed value is the strong CP problem.

</figcaption>
</figure>

## Prerequisites

You should know [QCD Lagrangian](/gauge-theories-standard-model/qcd/qcd-lagrangian/), [Chiral Symmetry in QCD](/gauge-theories-standard-model/qcd/chiral-symmetry-in-qcd/), [Spontaneous Chiral Symmetry Breaking](/gauge-theories-standard-model/qcd/spontaneous-chiral-symmetry-breaking/), and [Confinement in QCD](/gauge-theories-standard-model/qcd/confinement-in-qcd/).

You should also know the axial anomaly at the level of the Gauge Quantization and Standard Model consistency chapters. This page uses

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3,
\qquad
\epsilon^{0123}=+1,
$$

and the QCD covariant derivative

$$
D_\mu q=(\partial_\mu+ig_sG_\mu^AT^A)q.
$$

The sign of $\mathcal L_\theta$ is a convention. What matters physically is the invariant parameter $\bar\theta$ after all quark-field phase conventions have been fixed.

## Core idea

The theta term is the canonical example of a term that looks disposable locally but is not disposable globally.

The density

$$
q(x)
=
\frac{g_s^2}{32\pi^2}
G_{\mu\nu}^A\widetilde G^{A\mu\nu}
$$

can be written as a divergence,

$$
q(x)=\partial_\mu K^\mu,
$$

where $K^\mu$ is a Chern–Simons current. Therefore a naive perturbative argument says the theta term is a total derivative and should not affect Feynman rules. That statement is correct in perturbation theory around topologically trivial fields. It is not the full quantum theory.

In Euclidean gauge theory, finite-action gauge configurations can fall into topological sectors labeled by an integer $Q$. The theta term weights those sectors. Equivalently, the true vacuum can be a theta superposition of winding-number vacua. Instantons are semiclassical configurations that interpolate between neighboring sectors, but the existence of theta dependence is more general than a dilute-instanton approximation.

The theta term is also tied to chiral symmetry. Because the singlet axial rotation is anomalous, changing quark phases changes the coefficient of $G\widetilde G$. The measurable CP-violating parameter is not the bare $\theta$ alone but the invariant combination with the quark mass phase.

That is the trapdoor under the Standard Model. Weak interactions have a large CKM CP-violating phase, but the strong CP phase is experimentally tiny. The minimal Standard Model allows it, and yet nature seems to have chosen it almost zero.

## The topological density

The non-Abelian field strength is

$$
G_{\mu\nu}=G_{\mu\nu}^AT^A,
\qquad
\operatorname{tr}(T^AT^B)=\frac12\delta^{AB}.
$$

The dual field strength is

$$
\widetilde G^{A\mu\nu}
=
\frac12\epsilon^{\mu\nu\rho\sigma}G_{\rho\sigma}^A.
$$

The CP-odd density is

$$
G_{\mu\nu}^A\widetilde G^{A\mu\nu}.
$$

In terms of color electric and magnetic fields, it is proportional to

$$
\mathbf E^A\cdot \mathbf B^A
$$

up to signature and sign conventions. Since $\mathbf E$ and $\mathbf B$ transform oppositely under parity and time reversal, this density violates $P$ and $T$, and therefore CP if CPT is assumed.

The theta term is

$$
\mathcal L_\theta
=
\theta q(x),
\qquad
q(x)=
\frac{g_s^2}{32\pi^2}
G_{\mu\nu}^A\widetilde G^{A\mu\nu}.
$$

The normalization is chosen so that, for suitable finite-action Euclidean configurations,

$$
Q=\int d^4x_E\,q_E(x)\in\mathbb Z.
$$

The Euclidean action then contains an imaginary term

$$
S_E\supset -i\theta Q
$$

in one common continuation convention, so the path integral weights sectors by $e^{i\theta Q}$. Different Wick-rotation sign conventions move signs around, but the periodicity

$$
\theta\sim\theta+2\pi
$$

is the invariant statement.

## Why a total derivative can matter

The topological density satisfies

$$
G_{\mu\nu}^A\widetilde G^{A\mu\nu}
=
\partial_\mu K^\mu
$$

for a Chern–Simons current $K^\mu$. The current $K^\mu$ is not gauge invariant, but its divergence is. For field configurations that are small fluctuations around zero and vanish gently at infinity, the integral of a total derivative seems irrelevant.

The loophole is global. Gauge fields with finite Euclidean action approach a pure gauge at infinity,

$$
G_\mu(x)\to \frac{i}{g_s}U(x)\partial_\mu U^{-1}(x)
\qquad
\text{as } |x|\to\infty,
$$

up to convention-dependent signs. The boundary at infinity is topologically a three-sphere $S^3$, and the map

$$
U:S^3\to SU(3)
$$

can have nonzero winding number because

$$
\pi_3(SU(3))=\mathbb Z.
$$

Thus a total derivative can integrate to a topological invariant. The lesson is not mysterious: local expressions do not always see global sectors.

## Theta vacua and instantons

In canonical language, Yang–Mills theory has classical vacua labeled by winding number. Large gauge transformations relate these vacua but can act nontrivially on quantum states. The energy eigenstates are theta superpositions, schematically

$$
|\theta\rangle
=
\sum_{n\in\mathbb Z} e^{-in\theta}|n\rangle.
$$

Instantons are finite-action Euclidean field configurations that interpolate between neighboring winding sectors. For a one-instanton configuration in pure Yang–Mills, the Euclidean action is

$$
S_{\rm inst}
=
\frac{8\pi^2}{g_s^2}.
$$

This shows why theta physics is nonperturbative at weak coupling: instanton effects carry factors like

$$
e^{-8\pi^2/g_s^2}.
$$

However, one should not overstate dilute instantons in real low-energy QCD. At the scale where QCD is strongly coupled, large instantons and other nonperturbative effects are not controlled by a simple dilute gas. The theta term is real physics, but quantitative low-energy theta dependence is usually handled through chiral effective theory, lattice QCD, large-$N$ arguments, or topological susceptibility, not by pretending every effect is a tiny semiclassical instanton.

## Axial rotations and quark mass phases

Now add quarks. The quark mass term can be written as

$$
\mathcal L_m
=
-\bar q_L M_q q_R
-\bar q_R M_q^\dagger q_L.
$$

If $M_q$ is complex, it contains phases. Some phases are removable by flavor rotations; some contribute to the CKM phase in the weak interaction; and one particular invariant combination contributes to strong CP.

The singlet axial rotation

$$
q\mapsto e^{i\alpha\gamma^5}q
$$

rotates left- and right-handed quarks oppositely. Classically, for massless quarks this would be a symmetry. Quantum mechanically, the path-integral measure is anomalous. The result is that an axial rotation shifts the theta angle while also changing the phase of the mass determinant.

The invariant combination is conventionally

$$
\bar\theta
=
\theta+\arg\det M_q.
$$

In the full Standard Model, after electroweak symmetry breaking, $M_q$ represents the product of up-type and down-type quark mass matrices in the appropriate convention, so one often writes

$$
\bar\theta
=
\theta_{\rm QCD}
+
\arg\det(M_uM_d).
$$

Some texts use a minus sign because they define the anomalous rotation or theta term with the opposite sign. The physical content is unchanged: only the invariant combination matters.

## Why one massless quark would remove theta

If at least one quark were exactly massless, an axial rotation of that quark could shift $\theta$ without making its mass complex, because there would be no corresponding mass term. Then $\bar\theta$ would be unphysical.

This observation motivated the old idea that the up quark might be massless. Modern lattice QCD and chiral analyses do not support an exactly massless up quark. The idea is historically important and pedagogically useful, but it is not the accepted solution of the strong CP problem.

The massless-quark lesson remains conceptually valuable:

$$
\text{theta is physical only after accounting for anomalous chiral rotations and quark masses.}
$$

You cannot decide whether strong CP exists by looking only at the bare $G\widetilde G$ coefficient.

## CP violation from theta

For nonzero $\bar\theta$, strong interactions violate CP. The most famous observable is the neutron electric dipole moment. A permanent electric dipole moment of a spin-$\frac12$ particle requires a vector aligned with spin,

$$
\mathbf d_n=d_n\frac{\mathbf S}{|\mathbf S|}.
$$

The spin is an axial vector, while the electric dipole is a polar vector. Such a term violates parity and time reversal, hence CP assuming CPT. QCD with $\bar\theta\neq0$ naturally produces such effects.

The striking empirical fact is that no strong CP violation has been observed at the level one would expect for $\bar\theta$ of order one. The usual order-of-magnitude statement is

$$
|\bar\theta|\lesssim 10^{-10},
$$

with the exact numerical coefficient depending on hadronic matrix elements and experimental input. The precise bound belongs in a date-stamped data table, not in the conceptual definition. The conceptual point is clear: $\bar\theta$ is extraordinarily small.

## The strong CP problem

The minimal Standard Model contains two very different CP stories.

First, the weak interaction contains a CKM phase. It is physical, observed, and not tiny in the same sense. CP violation in kaons and $B$ mesons is a triumph of the Standard Model flavor structure.

Second, QCD permits $\bar\theta$. It is also physical in principle, but experimentally tiny.

The strong CP problem asks why these facts coexist:

$$
\delta_{\rm CKM}\sim O(1),
\qquad
\bar\theta\lesssim 10^{-10}.
$$

This is not a logical inconsistency. One can set $\bar\theta$ to a very small number. The problem is naturalness and explanation: no symmetry of the minimal Standard Model forces $\bar\theta=0$, and radiative or ultraviolet effects must not regenerate a large value.

A good strong CP solution should explain why the invariant combination is small, not merely why a chosen convention has $\theta_{\rm QCD}=0$.

## Main solution strategies

There are several broad strategies.

| Strategy | Basic idea | Status |
|---|---|---|
| Massless up quark | If one quark is exactly massless, $\bar\theta$ is unphysical. | Disfavored by modern QCD evidence. |
| Peccei–Quinn symmetry and axion | Promote $\bar\theta$ to a dynamical field whose potential relaxes at CP-conserving values. | Leading solution class; axion searches are a major experimental frontier. |
| Spontaneous CP or parity | CP is exact in the ultraviolet and broken in a controlled way that keeps $\bar\theta$ small. | Viable in special model classes, but requires structure. |
| Nelson–Barr mechanisms | Arrange CP breaking so the CKM phase is large while $\bar\theta$ vanishes or is suppressed at tree level. | Interesting but model-dependent. |
| Environmental or anthropic ideas | Small $\bar\theta$ follows from selection or cosmological history. | Speculative and not a standard resolution. |

The axion solution is especially important because it turns a conceptual problem into a new particle prediction. In the simplest version, a global $U(1)_{\rm PQ}$ symmetry is anomalous under QCD. Its pseudo-Goldstone field $a(x)$ appears through

$$
\frac{a(x)}{f_a}
\frac{g_s^2}{32\pi^2}
G_{\mu\nu}^A\widetilde G^{A\mu\nu}.
$$

The QCD vacuum energy then generates a potential for $a/f_a+\bar\theta$, dynamically relaxing the effective strong CP phase to a CP-conserving minimum.

The axion is not just a trick for a homework problem. It is one of the cleanest examples where a field-theory naturalness problem points to a concrete experimental program. Tiny angle, giant industry. Physics has range.

## Vacuum energy and topological susceptibility

The theta dependence of QCD can be encoded in the vacuum energy density

$$
E(\theta).
$$

For small $\bar\theta$,

$$
E(\bar\theta)
=
E(0)
+
\frac12\chi_{\rm top}\bar\theta^2
+
O(\bar\theta^4),
$$

where

$$
\chi_{\rm top}
=
\left.\frac{\partial^2 E}{\partial\theta^2}\right|_{\theta=0}
=
\frac{\langle Q^2\rangle}{V}
$$

in Euclidean finite-volume notation, up to standard connected and normalization conventions.

The topological susceptibility is a nonperturbative observable. In pure Yang–Mills theory it is tied to large-$N$ arguments and to the large mass of the $\eta'$ relative to the pseudoscalar octet. With light quarks, chiral dynamics suppresses theta dependence, and if a quark were exactly massless, $\chi_{\rm top}$ would vanish in the appropriate sense because theta would become unphysical.

This is one of the best bridges between the formal theta term and measurable hadronic physics.

## Theta at pi

Because $\theta$ is periodic, $\theta=\pi$ can be special. Depending on the theory and matter content, CP may be spontaneously broken at $\theta=\pi$, or the theory may have nontrivial infrared behavior constrained by anomalies and global structure.

This page focuses on QCD near $\bar\theta=0$, because that is what the strong CP problem demands. But $\theta$ dependence as a function on the whole circle is a rich subject in its own right, especially in pure Yang–Mills theory, large-$N$ limits, lower-dimensional analogues, and theories with generalized symmetries.

## Common pitfalls

**Pitfall: saying the theta term is a total derivative, so it never matters.** It is a total derivative locally. Its integral can be a topological invariant over nontrivial gauge sectors.

**Pitfall: treating $\theta$ and $\arg\det M_q$ as separately physical.** They are convention-dependent. The invariant strong CP phase is $\bar\theta$.

**Pitfall: confusing strong CP violation with CKM CP violation.** The CKM phase lives in weak charged-current flavor physics. The strong CP phase multiplies $G\widetilde G$ after accounting for quark mass phases. They are different invariants.

**Pitfall: thinking instantons are the whole story.** Instantons beautifully show how topology enters at weak coupling, but real low-energy QCD is strongly coupled. Theta dependence is broader than the dilute-instanton approximation.

**Pitfall: assuming $\theta=0$ is automatic because CP is “nice.”** The minimal Standard Model does not force $\bar\theta=0$. A small value requires a symmetry, dynamics, model-building structure, or an unexplained fine tuning.

**Pitfall: forgetting quark masses.** The physical theta parameter is inseparable from the complex quark mass matrix. Any strong CP discussion that ignores $M_q$ is missing half the mechanism.

## Relations to other pages

This page follows [Confinement in QCD](/gauge-theories-standard-model/qcd/confinement-in-qcd/) because theta physics is nonperturbative and tied to QCD vacuum structure. It also leans on [Chiral Symmetry in QCD](/gauge-theories-standard-model/qcd/chiral-symmetry-in-qcd/) because anomalous axial rotations decide which CP-odd phase is physical.

Later Standard Model pages should return to this topic when discussing fermion mass matrices, CKM CP violation, anomaly cancellation, and limitations of the Standard Model. The Symmetry, Anomalies, and Topology volume should eventually contain the broader anomaly, instanton, topological-charge, and theta-periodicity story. The Beyond the Standard Model chapter should return to axions and other strong CP solution mechanisms.

## Research status

The established structural facts are:

- QCD admits a theta term.
- $G\widetilde G$ is locally a total derivative but globally topological.
- Anomalous axial rotations shift theta and mass phases.
- The invariant strong CP phase is $\bar\theta=\theta+\arg\det M_q$ up to convention.
- Nonzero $\bar\theta$ violates CP and would induce hadronic CP-odd observables.
- The observed smallness of strong CP violation requires $\bar\theta$ to be extremely small.

The active frontier includes:

- axion model building and axion searches;
- ultraviolet explanations of small $\bar\theta$ with spontaneous CP, parity, Nelson–Barr structure, or other mechanisms;
- lattice determinations of theta dependence, topological susceptibility, and CP-odd hadronic matrix elements;
- theta dependence at finite temperature and its relevance to axion cosmology;
- the global structure of theta periodicity, anomalies, and CP behavior at $\theta=\pi$.

The strong CP problem is not a failure of QCD. It is QCD being too permissive: it allows a parameter that nature has made absurdly small.

## Exercises

### Exercise 1: Periodicity of theta

Assume Euclidean topological sectors are labeled by integer $Q$ and the path integral contains the factor $e^{i\theta Q}$. Show that physics is invariant under $\theta\mapsto\theta+2\pi$.

<details><summary><strong>Solution</strong></summary>

Under $\theta\mapsto\theta+2\pi$,

$$
e^{i\theta Q}
\mapsto
e^{i(\theta+2\pi)Q}
=
e^{i\theta Q}e^{2\pi i Q}.
$$

Since $Q\in\mathbb Z$,

$$
e^{2\pi i Q}=1.
$$

Therefore the weighting of each topological sector is unchanged, and all path-integral observables are periodic with period $2\pi$ in $\theta$, up to possible subtleties involving global form, matter content, and branch structure.

</details>

### Exercise 2: Why a massless quark removes theta

Consider one massless quark and assume the anomalous axial rotation can shift $\theta$. Explain why $\theta$ is not physical.

<details><summary><strong>Solution</strong></summary>

If the quark is exactly massless, there is no mass term for that quark whose phase changes under the axial rotation. The anomalous axial rotation shifts the coefficient of $G\widetilde G$, but it does not introduce a compensating complex mass phase for the massless quark.

Therefore one can choose the axial rotation angle so that the theta coefficient is set to zero. Since this is only a change of variables in the path integral, observables cannot depend on the original value of $\theta$. Equivalently, the invariant $\bar\theta$ is not defined as a physical CP-violating parameter when $\det M_q=0$.

</details>

### Exercise 3: CP-odd nature of the theta density

Use the electromagnetic analogy $G\widetilde G\propto \mathbf E^A\cdot\mathbf B^A$ to explain why the theta term violates parity and time reversal.

<details><summary><strong>Solution</strong></summary>

Under parity, the color electric field transforms as a vector while the color magnetic field transforms as a pseudovector. Thus

$$
\mathbf E^A\cdot\mathbf B^A
\mapsto
-
\mathbf E^A\cdot\mathbf B^A.
$$

Under time reversal, $\mathbf E^A$ is even and $\mathbf B^A$ is odd, again giving

$$
\mathbf E^A\cdot\mathbf B^A
\mapsto
-
\mathbf E^A\cdot\mathbf B^A.
$$

Thus the theta density violates $P$ and $T$. Assuming CPT, $T$ violation is equivalent to CP violation. Hence nonzero $\bar\theta$ is a strong CP-violating parameter.

</details>

### Exercise 4: Invariance of the strong CP phase

Suppose a chiral field redefinition shifts

$$
\theta\mapsto \theta-2\alpha,
\qquad
\arg\det M_q\mapsto \arg\det M_q+2\alpha.
$$

Show that $\bar\theta=\theta+\arg\det M_q$ is invariant.

<details><summary><strong>Solution</strong></summary>

Substitute the shifted quantities:

$$
\bar\theta'
=
(\theta-2\alpha)
+
(\arg\det M_q+2\alpha)
=
\theta+\arg\det M_q
=
\bar\theta.
$$

Thus $\theta$ and $\arg\det M_q$ are separately convention-dependent, while $\bar\theta$ is invariant under the anomalous chiral redefinition.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§93–94, for instantons, theta vacua, quarks, and theta-angle physics.
- Schwartz, *Quantum Field Theory and the Standard Model*, §§29.5 and 30.5, for strong CP violation, chiral rotations, and the relation to anomalies.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Chs. 22–23, for chiral dynamics, anomalies, and QCD theta dependence.
- Coleman, *Aspects of Symmetry*, Ch. 7, for instantons, vacuum structure, and theta vacua.
- Peccei and Quinn, Weinberg, and Wilczek’s original axion papers for the classic dynamical solution to the strong CP problem.
- Di Vecchia, Veneziano, Witten, and large-$N$ QCD literature for theta dependence, topological susceptibility, and the $\eta'$ connection.

## Version history

- **2026-06-18:** Initial page. Added theta term conventions, topological charge, theta vacua, axial rotations, $\bar\theta$, the strong CP problem, solution strategies, and exercises.
