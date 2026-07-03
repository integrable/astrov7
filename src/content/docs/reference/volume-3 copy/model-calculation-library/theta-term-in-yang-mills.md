---
title: "Theta Term in Yang–Mills"
description: "Derives the normalization, topology, instanton-sector weighting, and CP properties of the Yang–Mills theta term."
sidebar:
  label: "Theta Term in Yang–Mills"
  order: 8
level: Graduate
status: "Polished draft"
source: "Srednicki §§92–94; Coleman, Aspects of Symmetry; Polyakov Chs. 4 and 6; Altland–Simons Ch. 8."
topics:
  - theta term
  - Yang–Mills theory
  - instantons
  - topological charge
  - CP violation
canonicalTopics:
  - yang-mills-theta-term
  - instanton-number
  - topological-charge
  - theta-vacuum
researchStatus:
  established:
    - "The Yang–Mills theta term, instanton number, theta vacua, and CP properties are standard nonperturbative QFT material."
  active:
    - "Global-form refinements, boundary effects, mixed anomalies at special theta angles, and generalized-symmetry interpretations remain active structural topics."
---

## Summary

The Yang–Mills theta term is

$$
S_\theta
=
\frac{\theta}{8\pi^2}\int \operatorname{tr}(F\wedge F).
$$

With

$$
\operatorname{tr}_{\mathbf N}(T^aT^b)=\frac12\delta^{ab},
$$

this is

$$
S_\theta
=
\theta\, k,
\qquad
k=
\frac{1}{32\pi^2}\int d^4x\,F^a_{\mu\nu}\widetilde F^{a\mu\nu}.
$$

For ordinary $SU(N)$ bundles on closed Euclidean four-manifolds, the integer

$$
k\in\mathbb Z
$$

is the instanton number, also called the second Chern number or topological charge.

The theta term is locally a total derivative, so it does not change the classical Yang–Mills equations on a closed spacetime. It still changes the quantum theory because the path integral sums over topological sectors:

$$
Z(\theta)=\sum_{k\in\mathbb Z} e^{i\theta k}Z_k.
$$

<figure class="doc-figure" style="--figure-width: 48rem;">

![A schematic of Yang–Mills topological sectors labeled by integer k, with theta weighting each sector by a phase.](/figures/symmetry-anomalies-topology/yang-mills-theta-sectors.svg)

<figcaption>

The Yang–Mills path integral decomposes into topological sectors labeled by $k$. The theta angle does not change the local equations of motion, but it weights each sector by $e^{i\theta k}$.

</figcaption>
</figure>

The physics slogan is:

$$
\text{total derivative locally}
\quad\not\Rightarrow\quad
\text{irrelevant globally}.
$$

## Prerequisites

You should know the instanton and anomaly pages in this calculation library, plus the conventions page for the volume. This page uses Hermitian generators and

$$
F=dA+iA\wedge A.
$$

For component formulas,

$$
\widetilde F^{\mu\nu}
=
\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma},
\qquad
\epsilon^{0123}=+1
$$

in Lorentzian signature.

:::note[Convention-sensitive normalization]
Some sources put the gauge coupling inside $F_{\mu\nu}$, some put it only in front of the kinetic term, and many mathematics references use anti-Hermitian connections. This page uses Hermitian generators, $F=dA+iA\wedge A$, and $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$.
:::

## Core idea

The Yang–Mills action has two natural four-dimensional gauge-invariant densities:

$$
\operatorname{tr}(F\wedge *F),
\qquad
\operatorname{tr}(F\wedge F).
$$

The first is metric-dependent and gives the usual kinetic term. The second is metric-independent and topological.

In Lorentzian components, with the gauge coupling outside $F$,

$$
\mathcal L_{\rm YM}
=
-\frac{1}{4g^2}F^a_{\mu\nu}F^{a\mu\nu}
+
\frac{\theta}{32\pi^2}F^a_{\mu\nu}\widetilde F^{a\mu\nu}.
$$

The theta density is a total derivative locally:

$$
\operatorname{tr}(F\wedge F)=d\,\operatorname{CS}_3(A),
$$

where, for the Hermitian convention,

$$
\operatorname{CS}_3(A)
=
\operatorname{tr}\left(A\wedge dA+\frac{2i}{3}A\wedge A\wedge A\right).
$$

A total derivative can matter whenever the gauge bundle, boundary conditions, or spacetime topology are nontrivial.

## The topological charge

Let

$$
A=A^aT^a,
\qquad
F=dA+iA\wedge A.
$$

Define

$$
k=\frac{1}{8\pi^2}\int_M\operatorname{tr}(F\wedge F).
$$

In components,

$$
F= \frac12 F^a_{\mu\nu}T^a\,dx^\mu\wedge dx^\nu.
$$

Using

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

one gets

$$
\frac{1}{8\pi^2}\int \operatorname{tr}(F\wedge F)
=
\frac{1}{32\pi^2}
\int d^4x\,F^a_{\mu\nu}\widetilde F^{a\mu\nu}.
$$

For smooth $SU(N)$ bundles over closed Euclidean four-manifolds,

$$
k\in\mathbb Z.
$$

On $\mathbb R^4$, finite-action configurations approach pure gauge at infinity. Compactifying

$$
\mathbb R^4\cup\{\infty\}\simeq S^4,
$$

the boundary behavior is classified by a map

$$
S^3_\infty\to SU(N).
$$

Since

$$
\pi_3(SU(N))\cong\mathbb Z
$$

for $N\ge2$, finite-action gauge fields fall into integer topological sectors.

## Euclidean action and instantons

The Euclidean Yang–Mills action with theta angle is

$$
S_E
=
\frac{1}{g^2}\int \operatorname{tr}(F\wedge *F)
-
i\frac{\theta}{8\pi^2}\int\operatorname{tr}(F\wedge F).
$$

The path-integral weight is

$$
e^{-S_E}
=
\exp\left[
-\frac{1}{g^2}\int \operatorname{tr}(F\wedge *F)
+i\theta k
\right].
$$

For a self-dual field strength,

$$
F=*F,
$$

with $k>0$,

$$
\int \operatorname{tr}(F\wedge *F)
=
\int \operatorname{tr}(F\wedge F)
=
8\pi^2 k.
$$

Thus an instanton of charge $k=1$ contributes the characteristic semiclassical factor

$$
e^{-8\pi^2/g^2+i\theta}.
$$

Anti-instantons have $k=-1$ and contribute

$$
e^{-8\pi^2/g^2-i\theta}.
$$

This is one of the cleanest places where nonperturbative effects appear: they are invisible in ordinary power series in $g^2$ but visible as

$$
e^{-8\pi^2/g^2}.
$$

## Theta periodicity

If all allowed sectors have integer $k$, then

$$
e^{i(\theta+2\pi)k}=e^{i\theta k}.
$$

Therefore

$$
\theta\sim\theta+2\pi.
$$

This periodicity can be refined in theories with different global forms of the gauge group, matter representations, boundaries, or background fields. The simplest $SU(N)$ statement is enough for the model calculation here, but later pages on global forms and one-form symmetry explain why the phrase “allowed sectors” deserves respect.

## Why the term is locally invisible

Varying the theta term gives

$$
\delta \operatorname{tr}(F\wedge F)
=
2\,\operatorname{tr}(D\delta A\wedge F).
$$

Using the Bianchi identity

$$
DF=0,
$$

this becomes a total derivative:

$$
\delta \operatorname{tr}(F\wedge F)
=
2\,d\,\operatorname{tr}(\delta A\wedge F).
$$

On a closed spacetime, or with boundary conditions that kill the boundary term, the theta term does not change the classical Yang–Mills equations of motion.

But the path integral is not a variational calculation in a single topological sector only. It sums over sectors, and each sector is weighted by $e^{i\theta k}$. That is why the theta term is physically meaningful.

## Theta vacua

Canonical Yang–Mills theory on space $\mathbb R^3$ has classical vacua labeled by winding number. Large gauge transformations connect neighboring labels. A theta vacuum is a superposition

$$
|\theta\rangle=\sum_{n\in\mathbb Z}e^{in\theta}|n\rangle.
$$

A large gauge transformation shifts $n\mapsto n+1$ and acts on $|\theta\rangle$ by a phase. The theta parameter labels a choice of quantum vacuum compatible with large gauge transformations.

The Euclidean instanton picture and the canonical theta-vacuum picture are the same physics from two angles. Instantons tunnel between neighboring classical vacua, and the theta angle controls the interference phase between tunneling paths.

## CP and the strong CP problem

The density

$$
F^a_{\mu\nu}\widetilde F^{a\mu\nu}
$$

is odd under parity and time reversal. Equivalently, in terms of chromoelectric and chromomagnetic fields,

$$
F^a_{\mu\nu}\widetilde F^{a\mu\nu}\propto \mathbf E^a\cdot\mathbf B^a,
$$

and $\mathbf E\cdot\mathbf B$ is $P$-odd and $T$-odd.

Therefore a generic theta angle violates $P$, $T$, and hence $CP$ in a CPT-invariant theory. The special values

$$
\theta=0,\qquad \theta=\pi
$$

are invariant under $\theta\mapsto-\theta$ modulo $2\pi$, though $\theta=\pi$ can have additional subtleties such as degenerate vacua or mixed anomalies depending on the theory.

In QCD, the physical parameter is not just the bare gluonic theta angle. Chiral rotations of quark fields shift the theta angle through the axial anomaly. The invariant combination is schematically

$$
\overline\theta=\theta+\arg\det M_q,
$$

with convention-dependent signs. The experimental smallness of $\overline\theta$ is the strong CP problem.

:::note[Source note]
The formula for $\overline\theta$ is convention-sensitive because it depends on the sign convention for the axial anomaly and on how quark mass phases are defined. The physical statement is invariant: anomalous chiral rotations move phase between the quark mass matrix and the gluonic theta term.
:::

## Boundaries and Chern–Simons terms

Since

$$
\operatorname{tr}(F\wedge F)=d\,\operatorname{CS}_3(A),
$$

a spacetime with boundary turns the theta term into a boundary Chern–Simons-like contribution. This is not a small detail. Boundary conditions, edge modes, anomaly inflow, and gauge invariance under large gauge transformations can all depend on it.

This is the same structural idea that appears throughout the volume:

$$
\text{bulk topological term}
\quad\leadsto\quad
\text{boundary response or anomaly inflow}.
$$

The theta term is one of the first four-dimensional examples where that idea becomes concrete.

## Common pitfalls

**Saying “it is a total derivative, so it is zero.”** It is locally a total derivative. It can still distinguish topological sectors and boundary conditions.

**Forgetting the trace normalization.** The factor $1/(32\pi^2)$ in components assumes $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$.

**Putting the gauge coupling in two places.** Decide whether $g$ is inside $F_{\mu\nu}$ or only in front of the kinetic term. This page keeps $g$ outside $F$.

**Confusing instanton number with particle number.** The integer $k$ labels topology of the gauge field configuration, not a number of particles.

**Ignoring global form.** $SU(N)$ and $SU(N)/\mathbb Z_N$ can differ in allowed bundles and theta periodicities once background fields are included.

**Forgetting quark mass phases.** In QCD, the physical CP-violating angle includes the anomalous effect of chiral rotations on the quark mass matrix.

## Relations to other pages

The ABJ and Fujikawa pages explain why chiral rotations can shift theta angles. The Standard Model anomaly-cancellation page explains why gauge anomalies must cancel. The Topological Terms chapter develops theta terms, Chern–Simons terms, Wess–Zumino terms, and BF terms systematically. The Instantons and Topological Sectors pages explain the semiclassical origin of the integer $k$ in more detail. The Higher-Form Symmetry chapter explains how the global form of the gauge group and line-operator spectrum refine theta periodicity.

## Research status

The basic theta-term story for $SU(N)$ Yang–Mills is settled. Active structural refinements include theta dependence at large $N$, behavior at $\theta=\pi$, mixed anomalies with center symmetry and time reversal, domain walls, global forms of gauge groups, and generalizations involving higher-form background fields.

The strong CP problem remains an open phenomenological and theoretical problem: the measured neutron electric dipole moment strongly constrains $\overline\theta$, and the Standard Model by itself does not explain why it is so small.

## Exercises

### Exercise 1: Component normalization

Starting from

$$
k=\frac{1}{8\pi^2}\int\operatorname{tr}(F\wedge F),
$$

show that

$$
k=\frac{1}{32\pi^2}\int d^4x\,F^a_{\mu\nu}\widetilde F^{a\mu\nu}
$$

when $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$.

<details><summary><strong>Solution</strong></summary>

Write

$$
F=\frac12F^a_{\mu\nu}T^a dx^\mu\wedge dx^\nu.
$$

Then

$$
\operatorname{tr}(F\wedge F)
=
\frac14F^a_{\mu\nu}F^b_{\rho\sigma}
\operatorname{tr}(T^aT^b)
dx^\mu\wedge dx^\nu\wedge dx^\rho\wedge dx^\sigma.
$$

Using $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$ and

$$
dx^\mu\wedge dx^\nu\wedge dx^\rho\wedge dx^\sigma
=
\epsilon^{\mu\nu\rho\sigma}d^4x,
$$

we get

$$
\operatorname{tr}(F\wedge F)
=
\frac18\epsilon^{\mu\nu\rho\sigma}F^a_{\mu\nu}F^a_{\rho\sigma}d^4x.
$$

Since

$$
F^a_{\mu\nu}\widetilde F^{a\mu\nu}
=
\frac12\epsilon^{\mu\nu\rho\sigma}F^a_{\mu\nu}F^a_{\rho\sigma},
$$

this becomes

$$
\operatorname{tr}(F\wedge F)
=
\frac14F^a_{\mu\nu}\widetilde F^{a\mu\nu}d^4x.
$$

Multiplying by $1/(8\pi^2)$ gives $1/(32\pi^2)$.

</details>

### Exercise 2: Theta periodicity

Assume $k\in\mathbb Z$. Show that the path integral is invariant under $\theta\mapsto\theta+2\pi$.

<details><summary><strong>Solution</strong></summary>

Each sector is weighted by

$$
e^{i\theta k}.
$$

After shifting $\theta\mapsto\theta+2\pi$,

$$
e^{i(\theta+2\pi)k}=e^{i\theta k}e^{i2\pi k}.
$$

Since $k\in\mathbb Z$,

$$
e^{i2\pi k}=1.
$$

Thus every sector has the same weight as before.

</details>

### Exercise 3: Self-dual instanton action

For a self-dual field strength $F=*F$ with $k=1$, show that the Euclidean Yang–Mills action without the theta phase is $8\pi^2/g^2$.

<details><summary><strong>Solution</strong></summary>

The Euclidean kinetic action is

$$
S_E^{\rm kin}=\frac{1}{g^2}\int\operatorname{tr}(F\wedge *F).
$$

For $F=*F$,

$$
\int\operatorname{tr}(F\wedge *F)
=
\int\operatorname{tr}(F\wedge F).
$$

For $k=1$,

$$
\frac{1}{8\pi^2}\int\operatorname{tr}(F\wedge F)=1,
$$

so

$$
\int\operatorname{tr}(F\wedge F)=8\pi^2.
$$

Therefore

$$
S_E^{\rm kin}=\frac{8\pi^2}{g^2}.
$$

</details>

### Exercise 4: CP at special theta angles

Why can $\theta=0$ and $\theta=\pi$ be special under CP?

<details><summary><strong>Solution</strong></summary>

The theta density is CP-odd, so CP sends

$$
\theta\mapsto-\theta.
$$

The theory is periodic under $\theta\sim\theta+2\pi$. Therefore CP maps a theory to itself when

$$
\theta=-\theta\mod 2\pi.
$$

The solutions are

$$
\theta=0,\qquad \theta=\pi
$$

modulo $2\pi$. The point $\theta=\pi$ can still have nontrivial dynamics, such as spontaneous CP breaking or mixed anomalies, depending on the theory.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§92–94 for solitons, monopoles, instantons, theta vacua, and quarks with theta vacua.
- S. Coleman, *Aspects of Symmetry*, especially “The Uses of Instantons.”
- A. M. Polyakov, *Gauge Fields and Strings*, chs. 4 and 6 for instantons and topology of gauge fields.
- R. Jackiw and C. Rebbi, “Vacuum Periodicity in a Yang–Mills Quantum Theory.”
- C. G. Callan, R. Dashen, and D. J. Gross, “The Structure of the Gauge Theory Vacuum.”
- E. Witten, “Theta Dependence in the Large N Limit of Four-Dimensional Gauge Theories.”
- A. Altland and B. Simons, *Condensed Matter Field Theory*, ch. 8 for theta terms, Wess–Zumino terms, and Chern–Simons terms in topological quantum matter.

## Version history

- 2026-06-17: Initial polished calculation page. Added theta-term normalization, component conversion, instanton-sector weighting, theta periodicity, CP discussion, boundary Chern–Simons relation, and exercises.
