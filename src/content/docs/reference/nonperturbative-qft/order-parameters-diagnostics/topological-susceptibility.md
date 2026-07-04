---
title: "Topological Susceptibility"
description: "Defines topological susceptibility as theta curvature and topological-charge fluctuation, with gauge-theory, lattice, and chiral caveats."
sidebar:
  label: "Topological Susceptibility"
  order: 10
level: Graduate
status: "Polished draft"
source: "Coleman; Witten; Veneziano; Zinn-Justin; Mariño; Shifman; Lüscher; Leutwyler–Smilga."
topics:
  - topological susceptibility
  - theta angle
  - topological charge
  - instantons
  - Yang–Mills theory
  - axial anomaly
  - lattice topology
canonicalTopics:
  - nonperturbative-qft
  - topological-susceptibility
  - theta-dependence
  - topological-charge
  - instanton-diagnostics
researchStatus:
  established:
    - "Topological susceptibility is the curvature of the vacuum free-energy density with respect to theta and equals the connected topological-charge fluctuation per Euclidean volume when the sector sum is well defined."
  active:
    - "Precise continuum extraction on the lattice, finite-temperature behavior, topology freezing, and theta dependence in QCD-like theories remain active computational and conceptual topics."
---

## Summary

**Topological susceptibility** measures how strongly a theory fluctuates among topological sectors. In four-dimensional Yang–Mills theory, with the conventions of this volume,

$$
Q=\int d^4x\,q(x),
\qquad
q(x)=\frac{1}{16\pi^2}\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu},
$$

and the theta-dependent Euclidean partition function is

$$
Z(\theta)=\sum_Q e^{i\theta Q}Z_Q.
$$

The free-energy density is

$$
f(\theta)=-\frac{1}{\mathcal V}\log Z(\theta),
$$

where $\mathcal V$ is the Euclidean spacetime volume. The topological susceptibility is

$$
\chi_t
=\left.\frac{\partial^2 f(\theta)}{\partial\theta^2}\right|_{\theta=0}
=\frac{1}{\mathcal V}\left(\langle Q^2\rangle-\langle Q\rangle^2\right)_{\theta=0},
$$

provided the theta expansion and sector sum are defined in the usual way. If CP is unbroken at $\theta=0$, then $\langle Q\rangle=0$ and

$$
\chi_t=\frac{\langle Q^2\rangle}{\mathcal V}.
$$

<figure class="doc-figure" style="--figure-width: 54rem;">

![Topological susceptibility as the curvature of the theta-dependent free-energy density and the variance of the topological charge distribution.](/figures/nonperturbative-qft/topological-susceptibility-theta-curvature.svg)

<figcaption>

Topological susceptibility has two equivalent faces: it is the curvature of $f(\theta)$ at $\theta=0$ and the connected fluctuation of topological charge per Euclidean volume. This equivalence is useful because theta dependence can be hard to simulate directly, while $Q$ can often be measured at $\theta=0$.

</figcaption>
</figure>

This is a nonperturbative diagnostic, but it is not a confinement order parameter. It probes vacuum topology, theta dependence, anomalous chiral symmetry, instanton physics, large-N structure, and axion physics. It often changes across thermal regimes, but its interpretation depends strongly on the theory and matter content.

## Prerequisites

You should know [Conventions and Notation](/nonperturbative-qft/conventions/), especially the section on gauge fields and topological sectors, plus [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/), [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/), [Condensates](/nonperturbative-qft/order-parameters-diagnostics/condensates/), and [Spectral Density](/nonperturbative-qft/order-parameters-diagnostics/spectral-density/).

The page assumes basic Yang–Mills theory, Euclidean path integrals, and the idea that smooth finite-action gauge fields may be classified by an integer topological charge under suitable boundary conditions.

## Core idea

A theta angle weights topological sectors by phases:

$$
Z(\theta)=\sum_Q e^{i\theta Q}Z_Q.
$$

If the theory frequently samples sectors with different $Q$, then changing $\theta$ changes the vacuum energy appreciably. If the theory is insensitive to topological sectors, the vacuum energy is nearly flat in $\theta$.

The topological susceptibility is the first nontrivial local measurement of this dependence:

$$
\chi_t=f''(0).
$$

It is called a susceptibility because it is a response coefficient. It is the response of the vacuum free-energy density to the source $\theta$ conjugate to the topological charge $Q$.

The analogy with ordinary susceptibilities is exact at the formal level:

| Source | Conjugate quantity | Susceptibility |
|---|---|---|
| Magnetic field $h$ | Magnetization $M$ | $\partial^2 f/\partial h^2$ |
| Scalar source $J$ | Operator $\mathcal O$ | $\int d^dx\,\langle\mathcal O(x)\mathcal O(0)\rangle_c$ |
| Theta angle $\theta$ | Topological charge $Q$ | $\chi_t=\mathcal V^{-1}\langle Q^2\rangle_c$ |

The big difference is that $Q$ is global and topological, not a generic local order parameter. That makes $\chi_t$ both powerful and subtle.

## Setup and conventions

For four-dimensional Euclidean Yang–Mills theory we use

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu+i[A_\mu,A_\nu],
\qquad
\widetilde F_{\mu\nu}=\frac12\epsilon_{\mu\nu\rho\sigma}F_{\rho\sigma},
\qquad
\epsilon_{1234}=+1.
$$

The topological charge is

$$
Q
=\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}
=\frac{1}{8\pi^2}\int \operatorname{tr}F\wedge F.
$$

If $\operatorname{tr}T^aT^b=\frac12\delta^{ab}$, this is equivalently

$$
Q=\frac{1}{32\pi^2}\int d^4x\,F^a_{\mu\nu}\widetilde F^a_{\mu\nu}.
$$

For smooth finite-action $SU(N)$ gauge fields on $\mathbb R^4$ with the usual boundary conditions, $Q\in\mathbb Z$. On a finite torus, with other gauge groups, with boundaries, or on rough lattice configurations, one must say more carefully what is meant by $Q$.

The Euclidean Yang–Mills action with theta angle is

$$
S_E
=\frac{1}{2g^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}-i\theta Q.
$$

Thus the path-integral weight contains

$$
e^{-S_E}=e^{-S_{E,0}+i\theta Q}.
$$

That is why $Z(\theta)$ contains $e^{i\theta Q}$.

## Theta curvature and charge fluctuations

Let

$$
Z(\theta)=\sum_Q e^{i\theta Q}Z_Q,
\qquad
f(\theta)=-\frac{1}{\mathcal V}\log Z(\theta).
$$

Then

$$
\frac{\partial\log Z}{\partial\theta}=i\langle Q\rangle_\theta,
$$

and

$$
\frac{\partial^2\log Z}{\partial\theta^2}
=-\left(\langle Q^2\rangle_\theta-\langle Q\rangle_\theta^2\right).
$$

Therefore

$$
\frac{\partial^2 f}{\partial\theta^2}
=\frac{1}{\mathcal V}
\left(\langle Q^2\rangle_\theta-\langle Q\rangle_\theta^2\right).
$$

At $\theta=0$ this gives

$$
\chi_t
=\frac{\langle Q^2\rangle_c}{\mathcal V}.
$$

The connected subscript is not decorative. In a CP-violating background or away from $\theta=0$, $\langle Q\rangle$ need not vanish. The variance, not the raw second moment, is the susceptibility.

For small theta, if the theory is analytic at $\theta=0$, one may write

$$
f(\theta)=f(0)+\frac12\chi_t\theta^2+O(\theta^4).
$$

Higher derivatives measure higher cumulants of the topological charge distribution. For example, the fourth derivative is related to

$$
\langle Q^4\rangle_c
=\langle Q^4\rangle-3\langle Q^2\rangle^2
$$

at $\theta=0$ when $\langle Q\rangle=0$.

## Correlator representation and contact terms

Since

$$
Q=\int d^4x\,q(x),
$$

translation invariance suggests

$$
\chi_t=\int d^4x\,\langle q(x)q(0)\rangle_c.
$$

This formula is useful, but it hides a subtlety. The topological charge density is a composite operator, and the product $q(x)q(0)$ is singular at coincident points. Contact terms at $x=0$ are part of the definition of the integrated susceptibility.

This matters because the noncoincident correlator can have signs that look surprising. For example, in a reflection-positive Euclidean theory, a pseudoscalar density correlator can be negative at nonzero separation, while the integrated susceptibility is nonnegative because it is a variance:

$$
\chi_t=\frac{\langle Q^2\rangle_c}{\mathcal V}\ge0.
$$

The contact term resolves the apparent tension. The safe lesson is:

$$
\text{define }\chi_t\text{ through }f''(0)\text{ or }\langle Q^2\rangle_c/\mathcal V,\text{ then interpret }\int\langle q q\rangle\text{ with the required contact terms.}
$$

## Semiclassical interpretation

In a weakly coupled semiclassical regime, topological sectors may be dominated by instantons and anti-instantons. A charge-one instanton contributes schematically

$$
e^{-8\pi^2/g^2+i\theta},
$$

and an anti-instanton contributes

$$
e^{-8\pi^2/g^2-i\theta}.
$$

In a dilute gas approximation, the theta dependence often takes the simple form

$$
f(\theta)-f(0)\approx \kappa(1-\cos\theta),
$$

so

$$
\chi_t\approx \kappa.
$$

Here $\kappa$ is roughly the instanton-event density in that controlled dilute regime.

This picture is pedagogically valuable, but it is not universally reliable. Four-dimensional Yang–Mills theory at zero temperature is strongly coupled in the infrared, and its topological susceptibility is not generally computed by a dilute gas of small instantons. Semiclassics becomes more controlled in special regimes: high temperature, small circles with suitable deformations, supersymmetric theories, or lower-dimensional models where a controlled saddle expansion exists.

## Matter dependence and massless quarks

Topological susceptibility depends dramatically on matter content.

In pure Yang–Mills theory, $\chi_t$ is nonzero. In QCD with light quarks, the axial anomaly and chiral dynamics strongly constrain theta dependence. If there is an exactly massless quark, theta can be removed by an anomalous chiral rotation, so physical observables are independent of $\theta$ and

$$
\chi_t=0.
$$

For $N_f$ light quarks with masses $m_f$ and chiral condensate $\Sigma$ in the standard chiral regime, the leading small-mass behavior is

$$
\chi_t
=\frac{\Sigma}{\sum_{f=1}^{N_f}m_f^{-1}}+\text{higher-order corrections}.
$$

For degenerate quarks of mass $m$, this becomes

$$
\chi_t=\frac{m\Sigma}{N_f}+\cdots.
$$

This formula says something physically important: light fermions suppress topological charge fluctuations. A gauge background with nonzero topological charge has fermion zero modes, and the fermion determinant penalizes such sectors when the quark masses are small.

The contrast is worth remembering:

| Theory | Typical $\chi_t$ behavior |
|---|---|
| Pure Yang–Mills | Nonzero at zero temperature; measures theta curvature of gluodynamics. |
| QCD with one exactly massless quark | Vanishes because theta is unphysical. |
| QCD with light massive quarks | Suppressed by chiral dynamics; leading behavior proportional to light masses. |
| High-temperature dilute regime | Often approximated by instanton-gas-like theta dependence when controlled. |

## Lattice definition and continuum extraction

Topological susceptibility is one of the classic quantities where the lattice is conceptually clean but technically delicate.

On a smooth continuum field, $Q$ is an integer under suitable boundary conditions. On a rough lattice field, a naive discretization of $F\widetilde F$ need not be integer and may require renormalization. Standard strategies include:

| Strategy | Basic idea | Caveat |
|---|---|---|
| Field-theoretic definition | Discretize $q(x)$ and renormalize. | Operator mixing and contact terms must be controlled. |
| Cooling or smearing | Smooth ultraviolet noise before measuring $Q$. | Smoothing prescription must not distort continuum physics. |
| Gradient flow | Flow fields to positive flow time, then measure a smoother topological density. | Requires controlled extrapolation in lattice spacing and flow time. |
| Fermionic/index definition | Use chiral lattice Dirac operators to define $Q$ by an index. | More expensive; depends on lattice fermion setup. |

A second difficulty is **topology freezing**. As the continuum limit is approached, Monte Carlo histories may move slowly between topological sectors. Then the measured distribution of $Q$ can underestimate fluctuations. Open boundary conditions, improved algorithms, and fixed-topology correction formulas are among the tools used to diagnose and mitigate this problem.

The lesson is not that lattice topology is unreliable. The lesson is that $\chi_t$ is a precision nonperturbative observable whose definition and sampling must be stated.

## Large-N and theta branches

In large-N Yang–Mills theory, theta dependence has a distinctive structure. The standard expectation is that the vacuum energy has the scaling form

$$
f(\theta)=N^2\,h\left(\frac{\theta}{N}\right)
$$

locally near $\theta=0$, with branch structure needed to preserve $2\pi$ periodicity. More explicitly, one often writes schematically

$$
f(\theta)=N^2\min_{k\in\mathbb Z}h\left(\frac{\theta+2\pi k}{N}\right).
$$

This implies

$$
\chi_t=O(N^0)
$$

in pure Yang–Mills theory. It also suggests interesting physics near $\theta=\pi$, where different branches can compete. The details depend on dimension, gauge group, matter content, and anomalies, so this page treats the large-N statement as orientation rather than a full derivation.

## Physical uses

Topological susceptibility appears in several important places.

| Use | What $\chi_t$ tells you |
|---|---|
| Theta dependence | Curvature of the vacuum free energy at $\theta=0$. |
| Instanton physics | Density of topology-changing semiclassical events in dilute regimes. |
| $U(1)_A$ problem | Pure-gauge $\chi_t$ enters the Witten–Veneziano explanation of the large $\eta'$ mass. |
| Axion physics | The axion mass satisfies $m_a^2f_a^2=\chi_t$ for the relevant QCD susceptibility. |
| Finite-temperature topology | Thermal suppression or rearrangement of topological fluctuations. |
| Lattice benchmarking | A precise test of topological sampling and continuum extrapolation. |

The $U(1)_A$ example is especially instructive. The topological susceptibility of pure Yang–Mills theory is not just a formal response coefficient; it is tied to the anomalous singlet axial channel and to why the $\eta'$ is much heavier than a naive Goldstone boson.

## Common pitfalls

**Calling $\chi_t$ a confinement order parameter.** Pure Yang–Mills has both confinement and nonzero topological susceptibility at low temperature, but these are different statements. $\chi_t$ measures theta curvature and topological charge fluctuations, not the area law for Wilson loops.

**Forgetting contact terms.** The formula $\chi_t=\int d^4x\,\langle q(x)q(0)\rangle$ requires a definition of the coincident-point singularity. The variance definition is safer.

**Assuming $Q$ is automatically an integer on the lattice.** Smooth continuum topology and rough lattice fields are not the same object. One must specify the lattice definition, smoothing, flow, or index prescription.

**Ignoring light fermions.** Pure Yang–Mills susceptibility and full QCD susceptibility are not the same. Light quarks suppress topology, and an exactly massless quark removes theta dependence.

**Equating instantons with all topology.** Instantons are semiclassical representatives of topological sectors in some regimes. Topological susceptibility can be nonzero even when a dilute instanton gas is not the right description.

**Confusing finite-volume sector fixing with physics at theta.** Simulations at fixed $Q$ can be useful, but fixed-topology expectation values require finite-volume corrections before they are interpreted as theta-vacuum observables.

## Relations to other pages

[Conventions and Notation](/nonperturbative-qft/conventions/) fixes the normalization of $Q$, $F\widetilde F$, and the theta-sector sum used here.

[Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/) explains why topological sectors are part of the global definition of a Euclidean QFT rather than a perturbative afterthought.

[Condensates](/nonperturbative-qft/order-parameters-diagnostics/condensates/) gives the chiral condensate language needed for the small-quark-mass formula. [Spectral Density](/nonperturbative-qft/order-parameters-diagnostics/spectral-density/) gives the correlator language behind pseudoscalar channels.

[Polyakov-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/polyakov-loop-diagnostics/) is a complementary finite-temperature gauge-theory diagnostic. Polyakov loops diagnose thermal center symmetry; $\chi_t$ diagnoses topological fluctuations and theta curvature.

Later pages on instantons, theta vacua, fermion zero modes, and Yang–Mills instantons will develop the topological and semiclassical mechanisms behind this diagnostic.

## Research status

**Established.** The equality between theta curvature and connected topological charge fluctuations follows directly from the theta-sector partition function. The normalization of $Q$ is standard once the trace convention is fixed.

**Established with technical caveats.** Lattice calculations of $\chi_t$ are mature, but require careful definitions of the topological charge, continuum extrapolation, and control over topology sampling.

**Established in appropriate regimes.** Chiral Ward identities imply strong suppression of $\chi_t$ by light quark masses, and an exactly massless quark removes physical theta dependence.

**Active.** High-temperature QCD topology, topology freezing, finite-density topology, theta dependence at large N and near $\theta=\pi$, and the relation between topology and real-time sphaleron-like transitions are active areas of work.

## Exercises

### Exercise 1: Susceptibility from theta curvature

Starting from

$$
Z(\theta)=\sum_Q e^{i\theta Q}Z_Q,
\qquad
f(\theta)=-\frac{1}{\mathcal V}\log Z(\theta),
$$

show that

$$
\left.\frac{\partial^2f}{\partial\theta^2}\right|_{\theta=0}
=\frac{1}{\mathcal V}\left(\langle Q^2\rangle-\langle Q\rangle^2\right)_{\theta=0}.
$$

<details><summary><strong>Solution</strong></summary>

First,

$$
\frac{\partial\log Z}{\partial\theta}
=\frac{1}{Z}\sum_Q iQ e^{i\theta Q}Z_Q
=i\langle Q\rangle_\theta.
$$

Differentiating again,

$$
\frac{\partial^2\log Z}{\partial\theta^2}
=-\langle Q^2\rangle_\theta+\langle Q\rangle_\theta^2.
$$

Since $f=-(1/\mathcal V)\log Z$,

$$
\frac{\partial^2 f}{\partial\theta^2}
=\frac{1}{\mathcal V}
\left(\langle Q^2\rangle_\theta-\langle Q\rangle_\theta^2\right).
$$

Evaluating at $\theta=0$ gives the result.

</details>

### Exercise 2: Gaussian charge distribution

Suppose the topological charge distribution at $\theta=0$ is approximately Gaussian,

$$
P(Q)\propto \exp\left(-\frac{Q^2}{2\chi_t\mathcal V}\right).
$$

Show that the corresponding small-$\theta$ free-energy density is

$$
f(\theta)-f(0)=\frac12\chi_t\theta^2+O(\theta^4)
$$

in the large-volume saddle approximation.

<details><summary><strong>Solution</strong></summary>

The theta-dependent partition function is proportional to the Fourier transform of the $Q$ distribution:

$$
Z(\theta)\propto \sum_Q e^{i\theta Q}P(Q).
$$

At large volume, approximate the sum by an integral:

$$
Z(\theta)\propto \int dQ\,
\exp\left(-\frac{Q^2}{2\chi_t\mathcal V}+i\theta Q\right).
$$

Completing the square gives

$$
Z(\theta)\propto Z(0)\exp\left(-\frac12\chi_t\mathcal V\theta^2\right).
$$

Therefore

$$
f(\theta)-f(0)
=-\frac{1}{\mathcal V}\log\frac{Z(\theta)}{Z(0)}
=\frac12\chi_t\theta^2.
$$

Corrections come from non-Gaussian cumulants and periodicity in $\theta$.

</details>

### Exercise 3: Massless quark and theta independence

Suppose a QCD-like theory contains one exactly massless quark. Explain why physical observables can be independent of $\theta$, and conclude that $\chi_t=0$.

<details><summary><strong>Solution</strong></summary>

A chiral rotation of a massless quark field has no mass term whose phase must be preserved. Because of the axial anomaly, the fermion measure shifts the effective theta angle. With at least one exactly massless quark, this anomalous chiral rotation can be used to remove $\theta$ from the action.

If $\theta$ can be removed by a field redefinition, physical observables cannot depend on it. Therefore

$$
f(\theta)=f(0)
$$

and

$$
\chi_t=f''(0)=0.
$$

Equivalently, the fermion determinant suppresses sectors with nonzero topological charge when the corresponding zero modes are unsaturated and the quark mass is exactly zero.

</details>

### Exercise 4: Dilute instanton gas curvature

Assume a dilute instanton gas gives

$$
f(\theta)-f(0)=\kappa(1-\cos\theta).
$$

Compute $\chi_t$.

<details><summary><strong>Solution</strong></summary>

Differentiate twice:

$$
\frac{d f}{d\theta}=\kappa\sin\theta,
\qquad
\frac{d^2 f}{d\theta^2}=\kappa\cos\theta.
$$

At $\theta=0$,

$$
\chi_t=f''(0)=\kappa.
$$

In this approximation, the topological susceptibility equals the coefficient controlling the density of dilute topological events.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially the lectures on instantons, theta dependence, and anomalous symmetry.
- E. Witten, “Current Algebra Theorems for the U(1) Goldstone Boson,” for the large-N and $U(1)_A$ perspective on topological susceptibility.
- G. Veneziano, “U(1) Without Instantons,” for the Witten–Veneziano relation and the role of pure-gauge topology.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean field integrals, theta dependence, and nonperturbative definitions.
- M. Mariño, *Instantons and Large N*, for instantons, theta vacua, large-order behavior, and large-N topological structure.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, for instantons, anomalies, $U(1)_A$ physics, confinement examples, and theta-related phenomena.
- M. Lüscher, “Topology of Lattice Gauge Fields,” for a foundational lattice viewpoint on defining topological charge.
- H. Leutwyler and A. Smilga, “Spectrum of Dirac Operator and Role of Winding Number in QCD,” for chiral constraints and finite-volume topology.

## Version history

- **2026-06-26:** Initial polished draft.
