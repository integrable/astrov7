---
title: "Vertex Corrections"
description: "A convention-aware explanation of loop corrections to interaction vertices, using scalar triangle and four-point fish diagrams as canonical examples."
sidebar:
  label: "Vertex Corrections"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§16–20; Coleman 2019, chs. 15–16 and 21–23; Weinberg 1995, Vol. I, chs. 6, 10, and 12; Schwartz 2014, chs. 17 and 19; Zinn-Justin 2021, chs. 7–10"
topics:
  - vertex corrections
  - one-particle-irreducible vertices
  - coupling renormalization
  - scalar triangle diagrams
  - four-point amplitudes
canonicalTopics:
  - vertex-correction
  - one-particle-irreducible-vertex
  - coupling-counterterm
  - phi-three-triangle
  - phi-four-fish-diagram
researchStatus:
  established:
    - "Loop corrections to one-particle-irreducible vertex functions are the standard perturbative source of coupling renormalization, momentum-dependent form factors, and nonlocal finite parts of scattering amplitudes."
  active:
    - "Precision applications require gauge identities, infrared subtraction, unstable-particle prescriptions, multi-loop integral reduction, and scheme-aware definitions of couplings beyond the scalar examples on this page."
---

## Summary

A **vertex correction** is a loop correction to an interaction vertex. Self-energy diagrams modify propagation; vertex corrections modify the interaction kernel itself.

For a scalar cubic interaction,

$$
\mathcal L_{\rm int}=-\frac{g}{3!}\phi^3,
$$

the tree-level three-point vertex is

$$
{\text{tree cubic vertex}=-ig.}
$$

At one loop, the vertex receives a triangle correction of the form

$$
\mathcal V^{(1)}_3(p_1,p_2,p_3)
=
(-ig)^3\mu^{2\epsilon}
\int\frac{d^d\ell}{(2\pi)^d}
\frac{i}{\ell^2-m^2+i\epsilon}
\frac{i}{(\ell+p_1)^2-m^2+i\epsilon}
\frac{i}{(\ell-p_3)^2-m^2+i\epsilon},
$$

with all external momenta incoming, $p_1+p_2+p_3=0$. In six dimensions this triangle is logarithmically divergent and contributes to coupling renormalization.

For a scalar quartic interaction,

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

the one-loop four-point vertex correction is built from bubble integrals in the $s$, $t$, and $u$ channels:

$$
\mathcal V^{(1)}_4(s,t,u)
=
\frac{(-i\lambda)^2}{2}\left[I(s)+I(t)+I(u)\right].
$$

Here

$$
I(P^2)=
\mu^{2\epsilon}
\int\frac{d^d\ell}{(2\pi)^d}
\frac{i}{\ell^2-m^2+i\epsilon}
\frac{i}{(\ell+P)^2-m^2+i\epsilon}.
$$

The local divergent part is canceled by a coupling counterterm. The nonlocal finite part remains as the momentum dependence of the quantum-corrected interaction.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Tree and one-loop scalar vertex corrections: a local four-point vertex, a one-loop four-point fish diagram, and a one-loop three-point triangle diagram](/figures/perturbative-qft/vertex-corrections.svg)

<figcaption>

Vertex corrections are loop corrections to 1PI interaction kernels. A local tree coupling such as $g$ or $\lambda$ becomes a momentum-dependent object after loops. The local divergent part renormalizes the coupling; the finite nonlocal part contributes to physical amplitudes.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/), [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Superficial Degree of Divergence](/perturbative-qft/loop-expansion-regularization/superficial-degree-of-divergence/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), and [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/).

For scattering applications, review [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/) and [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/).

## Core idea

A Lagrangian coupling is local. A vertex correction is usually not.

At tree level, a term such as $-g\phi^3/3!$ or $-\lambda\phi^4/4!$ contributes a constant vertex factor. After loops, the same interaction channel depends on the momenta flowing through the diagram. Schematically,

$$
\text{tree coupling}
\quad\longrightarrow\quad
\text{local counterterm}+\text{finite momentum-dependent vertex function}.
$$

This is why loop-corrected scattering amplitudes contain logarithms, thresholds, branch cuts, and scale dependence. The short-distance part of the loop cannot resolve external kinematics and is local; it can be absorbed into a counterterm. The long-distance or finite part can depend on invariants such as $s$, $t$, $u$, and particle masses.

A useful slogan is

$$
\text{vertex correction} = \text{the 1PI correction to an interaction kernel}.
$$

This slogan is deliberately parallel to the self-energy slogan. Self-energies are 1PI two-point kernels. Vertex corrections are 1PI kernels with three or more external legs.

## Setup and conventions

We use qft.org mostly-minus conventions, with scalar propagator

$$
\frac{i}{p^2-m^2+i\epsilon},
$$

and dimensionally regulated loop measure

$$
\int_\ell
\equiv
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}.
$$

For one-loop four-dimensional examples,

$$
d=4-2\epsilon,
$$

while for the renormalizable cubic scalar theory in six dimensions,

$$
d=6-2\epsilon.
$$

We write

$$
\frac{1}{\overline\epsilon}
\equiv
\frac{1}{\epsilon}-\gamma_E+\ln4\pi.
$$

The phrase “vertex function” has two common meanings. In the effective-action convention, $\Gamma^{(n)}$ denotes the $n$-point 1PI functional derivative of the effective action. In diagrammatic scattering conventions, one often writes the full vertex factor with its factors of $i$ included. This page keeps the diagrammatic factors explicit, because that is where most sign mistakes happen.

For scalar counterterms, write

$$
\mathcal L_{\rm ct}\supset
-\frac{\delta g}{3!}\phi^3
-\frac{\delta\lambda}{4!}\phi^4.
$$

The corresponding counterterm vertex factors are

$$
{\phi^3\text{ counterterm}:\;-i\delta g,}
\qquad
{\phi^4\text{ counterterm}:\;-i\delta\lambda.}
$$

## Vertex functions as 1PI kernels

A connected correlator can contain long chains of propagator corrections, repeated lower-point subgraphs, and reducible pieces. The 1PI vertex isolates the irreducible kernel.

For a three-point scalar correlator, the connected momentum-space object has the schematic form

$$
G_3^{\rm conn}(p_1,p_2,p_3)
\sim
G(p_1)G(p_2)G(p_3)
\times
\text{1PI three-point kernel},
$$

with the overall $(2\pi)^d\delta^{(d)}(p_1+p_2+p_3)$ suppressed. Amputating the external full propagators leaves the vertex kernel.

For four-point functions, the situation is slightly richer. A connected four-point correlator contains a genuinely 1PI four-point vertex, but it can also contain two 1PI three-point vertices connected by a propagator. Thus “connected,” “amputated,” and “1PI” are different filters:

| Object | What it keeps |
|---|---|
| Connected four-point correlator | All connected diagrams. |
| Amputated connected four-point function | Connected diagrams with external propagators removed. |
| 1PI four-point vertex | Diagrams that cannot be disconnected by cutting one internal line. |

In tree-level scattering these distinctions can collapse in simple examples. At loop level they must be kept separate.

## The cubic triangle in six dimensions

The scalar theory

$$
\mathcal L
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{g}{3!}\phi^3
$$

has

$$
[g]=\frac{6-d}{2}.
$$

Thus $g$ is dimensionless in $d=6$. The one-loop correction to the cubic vertex is the triangle diagram

$$
\mathcal V^{(1)}_3(p_1,p_2,p_3)
=
(-ig)^3\int_\ell
\frac{i}{\ell^2-m^2+i\epsilon}
\frac{i}{(\ell+p_1)^2-m^2+i\epsilon}
\frac{i}{(\ell-p_3)^2-m^2+i\epsilon},
$$

where all external momenta are incoming and $p_1+p_2+p_3=0$.

Power counting already predicts the ultraviolet behavior. In $d$ dimensions, the triangle has one loop and three scalar propagators, so its superficial degree of divergence is

$$
D=d-2\times3=d-6.
$$

Therefore in $d=6$ it is logarithmically divergent:

$$
{D=0\qquad (\phi^3\text{ triangle in six dimensions}).}
$$

To expose the local divergence, combine the three denominators with Feynman parameters. The Euclidean scalar triangle master integral has the schematic form

$$
T_3
=
2\mu^{2\epsilon}
\int_0^1 dx\int_0^{1-x}dy
\int\frac{d^{6-2\epsilon}k_E}{(2\pi)^{6-2\epsilon}}
\frac{1}{(k_E^2+\Delta(x,y))^3}.
$$

Using

$$
\mu^{2\epsilon}
\int\frac{d^{6-2\epsilon}k_E}{(2\pi)^{6-2\epsilon}}
\frac{1}{(k_E^2+\Delta)^3}
=
\frac{1}{2(4\pi)^3}
\left[\frac{1}{\overline\epsilon}+O(1)\right],
$$

and the simplex area $1/2$, the divergent part of the scalar parameter integral is proportional to

$$
T_{3,\rm div}
=
\frac{1}{2(4\pi)^3}\frac{1}{\overline\epsilon}
+\text{finite convention-dependent terms}.
$$

The important lesson is not the isolated coefficient. The important lesson is that the divergence is independent of the external momenta. It has exactly the form of the original local operator $\phi^3$, so it can be canceled by $\delta g$.

:::note[Why φ³ in six dimensions keeps appearing]
Four-dimensional $\phi^4$ theory is the standard scalar model for coupling renormalization, but six-dimensional $\phi^3$ theory makes the one-loop three-point vertex logarithmically divergent. It is pedagogically useful because the two-point and three-point loop corrections already show the basic anatomy of renormalized perturbation theory.
:::

## The quartic fish diagrams in four dimensions

In four-dimensional $\phi^4$ theory,

$$
\mathcal L
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4,
$$

the tree-level four-point vertex is

$$
{\mathcal V_4^{(0)}=-i\lambda.}
$$

The one-loop correction to the four-point vertex comes from the fish diagrams in the three channels:

$$
\mathcal V^{(1)}_4(s,t,u)
=
\frac{(-i\lambda)^2}{2}\left[I(s)+I(t)+I(u)\right].
$$

The factor $1/2$ is the symmetry factor of each fish diagram. The channel integrals are

$$
I(P^2)
=
\int_\ell
\frac{i}{\ell^2-m^2+i\epsilon}
\frac{i}{(\ell+P)^2-m^2+i\epsilon}.
$$

Using the bubble convention from [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/),

$$
I(P^2)=-iB(P^2;m^2,m^2),
$$

with

$$
B(P^2;m^2,m^2)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}
-
\int_0^1dx\,
\ln\frac{m^2-x(1-x)P^2-i\epsilon}{\mu^2}
\right]
+O(\epsilon).
$$

The ultraviolet-divergent part of the one-loop four-point vertex is therefore

$$
\mathcal V^{(1)}_{4,\rm div}
=
i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}.
$$

The counterterm contribution is

$$
\mathcal V_{4,\rm ct}=-i\delta\lambda.
$$

Minimal subtraction cancels the pole by choosing

$$
\delta\lambda
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}
\qquad (d=4-2\epsilon).
$$

With the more common parameter $\epsilon_4=4-d=2\epsilon$, the same pole is often written as $3\lambda^2/(16\pi^2\epsilon_4)$. These are the same statement with different names for the dimensional regulator.

The finite logarithms are not removed by a local counterterm. They contain the momentum dependence of the quantum-corrected interaction and, after renormalization, lead to the running of $\lambda$.

## Coupling renormalization as a measurement prescription

A bare Lagrangian coupling is not automatically the number measured by an experiment. A coupling is defined by a convention for extracting it from a physical or off-shell quantity.

For a massive scalar theory, one possible momentum-subtraction condition is

$$
\mathcal V_{4,\rm ren}(s_*,t_*,u_*)=-i\lambda_R,
$$

at a chosen subtraction point $(s_*,t_*,u_*)$. This condition fixes $\delta\lambda$ so that the loop-corrected vertex equals the chosen value at that kinematic point.

In minimal subtraction, the rule is different: $\delta\lambda$ subtracts only poles in $1/\overline\epsilon$. Then $\lambda(\mu)$ depends on the renormalization scale $\mu$. In four-dimensional $\phi^4$ theory, the one-loop beta function is

$$
\beta_\lambda
\equiv
\mu\frac{d\lambda}{d\mu}
=
\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

The factor of two between the pole coefficient in $d=4-2\epsilon$ and the beta-function coefficient comes from differentiating the factor $\mu^{2\epsilon}$ in the bare coupling.

:::tip[What the counterterm can and cannot do]
A local counterterm can cancel the local divergent part of a vertex correction. It cannot erase the finite nonlocal dependence on external momenta, such as logarithms and branch cuts. Those pieces are part of the observable quantum correction.
:::

## Momentum dependence and form factors

A tree-level vertex is often a constant or a low-degree polynomial in momenta. A loop-corrected vertex can depend on invariant momentum transfers.

In scalar $\phi^4$ theory, the four-point vertex correction depends on

$$
s=(p_1+p_2)^2,
\qquad
t=(p_1-p_3)^2,
\qquad
u=(p_1-p_4)^2.
$$

In QED, the loop-corrected electron-photon vertex has the form

$$
\bar u(p')\,\Gamma^\mu(p',p)\,u(p),
\qquad
q=p'-p,
$$

and Lorentz covariance allows a decomposition such as

$$
\Gamma^\mu(p',p)
=
\gamma^\mu F_1(q^2)
+
\frac{i\sigma^{\mu\nu}q_\nu}{2m}F_2(q^2)
+\cdots,
$$

for on-shell external fermions. The functions $F_1$ and $F_2$ are form factors. They are vertex corrections organized by symmetry and kinematics.

Gauge theories add an essential constraint: vertex corrections are not independent of self-energies. In QED, the Ward–Takahashi identity relates the electron-photon vertex to the inverse electron propagator,

$$
q_\mu\Gamma^\mu(p+q,p)
=
S^{-1}(p+q)-S^{-1}(p).
$$

This identity is the reason that charge renormalization, wavefunction renormalization, and gauge invariance are tied together. The full treatment belongs in gauge-theory perturbation theory, but the lesson already belongs here: in a theory with symmetry, vertex corrections must satisfy the symmetry identities.

## Local and nonlocal parts

A vertex correction naturally splits into two kinds of terms.

The **local part** is analytic at low external momenta and can be expanded as a polynomial:

$$
A_0+A_1s+A_2t+A_3u+\cdots.
$$

The constant term renormalizes the original coupling. Higher powers correspond to derivative operators such as

$$
\phi^2\partial_\mu\phi\,\partial^\mu\phi,
\qquad
(\partial_\mu\phi\,\partial^\mu\phi)^2,
$$

depending on the theory. In an effective field theory, these local terms are part of the operator expansion.

The **nonlocal part** contains logarithms, thresholds, and branch cuts. For example, a bubble correction contains terms like

$$
\ln\left[m^2-x(1-x)s-i\epsilon\right].
$$

When $s$ crosses a multiparticle threshold, the logarithm develops an imaginary part. This is not a counterterm artifact; it is the perturbative trace of physical intermediate states.

## Common pitfalls

**Calling every loop diagram a vertex correction.** A loop attached to two external legs is a self-energy. A loop correcting a three-point or higher interaction kernel is a vertex correction.

**Forgetting the symmetry factor.** The $\phi^4$ fish diagram carries a factor $1/2$ in the four-point function. Dropping it doubles the counterterm.

**Confusing the bare coupling with a measured coupling.** A bare parameter depends on the regulator. A renormalized coupling is defined by a subtraction scheme or measurement prescription.

**Subtracting finite physical dependence.** Counterterms remove local regulator dependence. They do not remove threshold logarithms or branch cuts.

**Ignoring identities in gauge theory.** Gauge-theory vertex corrections must satisfy Ward or Slavnov–Taylor identities. Individual diagrams may be gauge-dependent even when the final observable is not.

**Comparing regulator epsilons without translation.** Some books use $d=4-\epsilon$ and others use $d=4-2\epsilon$. Pole coefficients differ by a factor of two when the same letter $\epsilon$ is used differently. Tiny notation goblin, real damage.

## Relations to other pages

- [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) explains the two-point analogue of vertex corrections.
- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) derives the bubble integral used in the $\phi^4$ vertex correction.
- [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/) introduces counterterm vertices as diagrammatic objects.
- [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) explains the pole notation and the role of $\mu$.
- [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/) gives the tree-level amplitudes that vertex corrections modify.
- [Renormalization, RG, and EFT](/renormalization-rg-eft/) gives the conceptual home of running couplings, scheme dependence, and EFT operator expansions.
- [Gauge Theories and the Standard Model](/gauge-theories-standard-model/) develops Ward identities, QED vertex corrections, and non-Abelian gauge-theory vertices.

## Research status

- **Established:** One-loop vertex corrections, coupling counterterms, and the relation between local UV divergences and local operators are standard perturbative QFT.
- **Active:** Modern precision physics requires automated multi-loop vertex calculations, integral reduction, infrared subtraction, gauge-invariant unstable-particle schemes, and careful matching between full theories and EFTs.
- **Convention-dependent:** The sign of a vertex correction and the displayed pole coefficient depend on the definition of amplitudes, the placement of factors of $i$, and whether $d=4-\epsilon$ or $d=4-2\epsilon$ is used.
- **Speculative:** Nothing on this page is speculative, though the same language appears inside speculative model building and UV-completion studies.

## Exercises

### Exercise 1: Power counting the cubic triangle

In scalar $\phi^3$ theory, compute the superficial degree of divergence of the one-loop triangle diagram in $d$ spacetime dimensions. For which dimension is it logarithmically divergent?

<details>
<summary><strong>Solution</strong></summary>

The triangle has one loop and three internal scalar propagators. At large loop momentum, the integral scales as

$$
\int d^d\ell\,\frac{1}{(\ell^2)^3}.
$$

Thus the superficial degree of divergence is

$$
D=d-6.
$$

It is logarithmically divergent when

$$
D=0,
$$

so

$$
{d=6.}
$$

</details>

### Exercise 2: The φ⁴ fish counterterm

Using

$$
I(P^2)=-i\frac{1}{16\pi^2}\frac{1}{\overline\epsilon}+\text{finite},
$$

and

$$
\mathcal V^{(1)}_4(s,t,u)
=
\frac{(-i\lambda)^2}{2}\left[I(s)+I(t)+I(u)\right],
$$

find the one-loop pole in the four-point vertex and the minimal-subtraction counterterm $\delta\lambda$ in $d=4-2\epsilon$.

<details>
<summary><strong>Solution</strong></summary>

Each channel contributes

$$
\frac{(-i\lambda)^2}{2}I(P^2)
=
\frac{-\lambda^2}{2}
\left[-i\frac{1}{16\pi^2}\frac{1}{\overline\epsilon}\right]
+\text{finite}
=
i\frac{\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}
+\text{finite}.
$$

There are three channels, so

$$
\mathcal V^{(1)}_{4,\rm div}
=
i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}.
$$

The counterterm vertex is $-i\delta\lambda$. Cancellation of the pole requires

$$
-i\delta\lambda
+i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}=0.
$$

Therefore

$$
\delta\lambda
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}.
$$

</details>

### Exercise 3: Local versus nonlocal pieces

Explain why a divergent term independent of $s$, $t$, and $u$ can be canceled by a $\phi^4$ counterterm, but a term such as $\ln(m^2-s/4-i\epsilon)$ cannot.

<details>
<summary><strong>Solution</strong></summary>

The operator $\phi^4$ is local. Its momentum-space vertex is a constant, so a $\phi^4$ counterterm can only add a constant local contribution to the four-point vertex.

A divergence independent of $s$, $t$, and $u$ has this same local form, so it can be canceled by $\delta\lambda\phi^4/4!$.

A logarithm such as

$$
\ln(m^2-s/4-i\epsilon)
$$

has non-polynomial dependence on the external kinematics. It contains branch-cut information and cannot be reproduced by a finite number of local counterterms. It is part of the physical loop correction.

</details>

### Exercise 4: A subtraction condition

Suppose a renormalized four-point vertex is written as

$$
\mathcal V_4(s,t,u)=-i\lambda-i\delta\lambda+\mathcal V^{(1)}_4(s,t,u).
$$

Impose the condition

$$
\mathcal V_4(s_*,t_*,u_*)=-i\lambda_R.
$$

Solve for $\delta\lambda$ in terms of $\lambda$, $\lambda_R$, and $\mathcal V^{(1)}_4(s_*,t_*,u_*)$.

<details>
<summary><strong>Solution</strong></summary>

At the subtraction point,

$$
-i\lambda-i\delta\lambda+\mathcal V^{(1)}_4(s_*,t_*,u_*)=-i\lambda_R.
$$

Move terms around:

$$
-i\delta\lambda
=-i\lambda_R+i\lambda-\mathcal V^{(1)}_4(s_*,t_*,u_*).
$$

Multiplying by $i$ gives

$$
\delta\lambda
=
\lambda_R-\lambda-i\,\mathcal V^{(1)}_4(s_*,t_*,u_*).
$$

If one chooses the renormalized parameter in the Lagrangian to already be $\lambda_R$, then the same equation is usually written with $\lambda=\lambda_R$ at tree level and $\delta\lambda$ chosen to cancel the loop correction at the subtraction point.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§16–20, for loop corrections to vertices, 1PI vertices, higher-order corrections, and one-loop two-particle scattering.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 15–16 and 21–23, for scalar self-energies, vertex corrections, renormalization, and fermionic vertex examples.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 6, 10, and 12, for Feynman rules, loop corrections, and renormalization.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 17 and 19, for vertex corrections, counterterms, and renormalized perturbation theory.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 7–10, for 1PI functions, vertex functions, dimensional regularization, and renormalization.

## Version history

- **2026-06-12:** Initial polished draft. Added scalar triangle and $\phi^4$ fish examples, coupling-counterterm conventions, QED form-factor preview, solved exercises, and a compact vertex-correction figure.
