---
title: "CP N-Minus-One Model"
description: "Explains the two-dimensional complex-projective large-N sigma model, including mass generation, theta dependence, topological susceptibility, and confinement-like physics."
sidebar:
  label: "CP N−1 Model"
  order: 8
level: Advanced
status: "Polished draft"
source: "Polyakov; Witten; Shifman; Mariño; large-N sigma-model literature."
topics:
  - CP N minus one model
  - large-N sigma models
  - asymptotic freedom
  - mass gap
  - theta dependence
  - topological susceptibility
  - confinement in two dimensions
  - quasivacua
canonicalTopics:
  - nonperturbative-qft
  - large-n-methods
  - cp-n-minus-one-model
  - sigma-models
  - theta-vacua
  - mass-gap
researchStatus:
  established:
    - "The two-dimensional CP N-minus-one model has a standard large-N solution with dynamical mass generation, induced gauge dynamics, theta dependence, and a calculable topological susceptibility."
  active:
    - "Finite-N theta dependence, resurgence, compactification, boundary conditions, and the relation between instanton calculus and the large-N expansion remain active research themes."
---

## Summary

The **$CP^{N-1}$ model** is a two-dimensional nonlinear sigma model whose field takes values in complex projective space. It is a compact laboratory for nonperturbative QFT because it combines several features that usually appear in much harder gauge theories:

$$
\text{asymptotic freedom},\qquad
\text{dimensional transmutation},\qquad
\text{mass generation},\qquad
\theta\text{ dependence},\qquad
\text{topological sectors}.
$$

At large $N$, the model becomes a controlled saddle-point problem. One writes the projective target space using $N$ complex fields $z_i$ with a local $U(1)$ redundancy, integrates out the $z_i$, and obtains an effective action for a Lagrange multiplier and an auxiliary gauge field. The saddle generates a mass scale,

$$
M\sim \Lambda \exp\left(-\frac{\text{const}}{g_0}\right),
$$

and the gauge field acquires an induced Maxwell term. In two dimensions, that induced gauge field gives a linear potential between the elementary charged fields. The charged $z_i$ fields are therefore not asymptotic particles of the nonsupersymmetric model; the physical excitations are neutral composites.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Large-N map of the CP N-minus-one model: complex projective target, gauged formulation, topological sectors, determinant effective action, gap equation, induced Maxwell term, theta branches, and instanton caveat.](/figures/nonperturbative-qft/cp-n-minus-one-large-n-map.svg)

<figcaption>

The $CP^{N-1}$ model is written with $N$ complex fields and a local phase redundancy. At fixed $A_\mu$ and $\lambda$, the $z_i$ fields are Gaussian; integrating them out gives an effective action proportional to $N$. The large-$N$ saddle generates a mass gap, induced gauge dynamics, theta branches, and two-dimensional confinement-like behavior.

</figcaption>
</figure>

The model is valuable precisely because it is not four-dimensional QCD. It is smaller, sharper, and more solvable. That makes it a good place to learn what words like “mass gap,” “theta dependence,” and “large-$N$ confinement” can mean before meeting them in a less forgiving setting.

## Prerequisites

Read [Large-N Sigma Models](/nonperturbative-qft/large-n-methods/large-n-sigma-models/) first. That page introduces constrained fields, Lagrange multipliers, and the large-$N$ determinant in the $O(N)$ model. This page is the complex-projective analogue.

You should also know [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/), [Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/), [Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/), and [Compact QED in Three Dimensions](/nonperturbative-qft/confinement-screening-mass-gap/compact-qed-three-dimensions/) at a conceptual level. The compact-QED page is not required technically, but it makes the phrase “an auxiliary gauge field becomes dynamically important” feel less mysterious.

For large-$N$ technique, keep [Large-N Vector Models](/nonperturbative-qft/large-n-methods/large-n-vector-models/) and [Saddle Points at Large N](/nonperturbative-qft/large-n-methods/saddle-points-at-large-n/) nearby.

## Core idea

Complex projective space can be described as nonzero complex vectors modulo complex rescaling. For the sigma model it is convenient to use unit vectors modulo phase:

$$
z\in \mathbb C^N,
\qquad
\bar z z=\text{fixed},
\qquad
z\sim e^{i\alpha}z.
$$

When $z=z(x)$ is a field, the phase $\alpha$ may depend on spacetime. The projective redundancy becomes a local $U(1)$ gauge redundancy. One introduces a gauge field $A_\mu$ and writes

$$
D_\mu z_i=(\partial_\mu-iA_\mu)z_i.
$$

The gauge field is not introduced because the microscopic theory necessarily contains an independent photon. It is introduced because it is a clean way to describe the quotient by local phase rotations. At the classical level, $A_\mu$ is often auxiliary. At large $N$, integrating out the $N$ charged fields generates dynamics for $A_\mu$.

The large-$N$ logic is then:

$$
\text{projective constraint}
\quad\Longrightarrow\quad
\text{$U(1)$ gauge redundancy}
\quad\Longrightarrow\quad
N\text{ charged Gaussian fields}
\quad\Longrightarrow\quad
N\operatorname{Tr}\log(-D^2+\lambda)
\quad\Longrightarrow\quad
\text{saddle and induced gauge action}.
$$

This is why the $CP^{N-1}$ model is closer in spirit to gauge theory than the $O(N)$ model. It has a gauge field, a theta term, topological sectors, instantons, and a confinement-like effect. But it is still a two-dimensional sigma model, so every analogy must be labeled carefully.

## Setup and conventions

We work in two Euclidean dimensions. The fields are $N$ complex scalars $z_i(x)$, $i=1,\dots,N$, with local $U(1)$ redundancy

$$
z_i(x)\mapsto e^{i\alpha(x)}z_i(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x).
$$

A useful large-$N$ normalization is

$$
\bar z_i z_i=\frac{N}{g_0},
$$

where $g_0$ is a dimensionless bare coupling at the ultraviolet cutoff scale $\Lambda$. Introduce a Lagrange multiplier $\lambda(x)$ to impose the constraint:

$$
S_E[z,A,\lambda]
=
\int d^2x\left[
(D_\mu z_i)^*(D_\mu z_i)
+
\lambda\left(\bar z_i z_i-\frac{N}{g_0}\right)
\right]
+
i\frac{\theta}{2\pi}\int F.
$$

Here

$$
F=F_{12}\,d^2x,
\qquad
F_{12}=\partial_1A_2-\partial_2A_1.
$$

For smooth finite-action configurations on compactified Euclidean spacetime, the topological charge is

$$
Q=\frac1{2\pi}\int F\in\mathbb Z.
$$

The theta term is therefore

$$
S_\theta=i\theta Q.
$$

This page uses the word “gauge” for the local projective redundancy. Physical observables must be invariant under this redundancy. The elementary field $z_i$ is not by itself a gauge-invariant local operator.

## Projective geometry from a gauge field

The gauge-field formulation is not merely notation. It is a compact way to write the Fubini–Study metric on $CP^{N-1}$.

Start with the kinetic term

$$
(D_\mu z)^*(D_\mu z)
=|\partial_\mu z-iA_\mu z|^2,
$$

with the constraint $\bar z z=N/g_0$. If $A_\mu$ has no bare kinetic term, its equation of motion is algebraic. Varying with respect to $A_\mu$ gives

$$
A_\mu
=
-\frac{i}{2\bar z z}
\left(\bar z\partial_\mu z-(\partial_\mu\bar z)z\right).
$$

Using $\partial_\mu(\bar z z)=0$, this can be written as

$$
A_\mu=-\frac{i}{\bar z z}\bar z\partial_\mu z.
$$

Substituting this back into the kinetic term removes the motion along the local phase direction. The result is the sigma-model metric on the quotient space.

The lesson is important: the gauge field does two jobs. Geometrically, it projects out the redundant phase. Dynamically, after the $z_i$ fields are integrated out at large $N$, fluctuations of $A_\mu$ become part of the low-energy effective description.

## Large-N effective action

At fixed $A_\mu$ and $\lambda$, the $z_i$ fields appear quadratically:

$$
S_E
=
\int d^2x\, z_i^*(-D^2+\lambda)z_i
-
\frac{N}{g_0}\int d^2x\,\lambda
+
i\frac{\theta}{2\pi}\int F.
$$

Performing the Gaussian integral over the $N$ complex fields gives

$$
Z
=
\int \mathcal D A\,\mathcal D\lambda\,e^{-S_{\rm eff}[A,\lambda]},
$$

where, up to convention-dependent constants,

$$
S_{\rm eff}[A,\lambda]
=
N\operatorname{Tr}\log(-D^2+\lambda)
-
\frac{N}{g_0}\int d^2x\,\lambda
+
i\frac{\theta}{2\pi}\int F.
$$

The important structural point is the overall $N$ multiplying the determinant and constraint terms. The effective path integral over $A_\mu$ and $\lambda$ is dominated by saddle points as $N\to\infty$.

The simplest translation-invariant saddle is

$$
A_\mu=0,
\qquad
\lambda=M^2.
$$

The saddle equation with respect to $\lambda$ gives

$$
\frac1{g_0}
=
\int^\Lambda\frac{d^2p}{(2\pi)^2}\frac1{p^2+M^2}.
$$

This is the same determinant logic as in the $O(N)$ nonlinear sigma model, now with complex fields and a projective gauge redundancy.

## Mass generation and dimensional transmutation

In two dimensions,

$$
\int^\Lambda\frac{d^2p}{(2\pi)^2}\frac1{p^2+M^2}
=
\frac1{4\pi}\log\frac{\Lambda^2+M^2}{M^2}.
$$

For $M\ll\Lambda$,

$$
\frac1{g_0}
\simeq
\frac1{2\pi}\log\frac{\Lambda}{M},
$$

so

$$
M\simeq \Lambda\exp\left(-\frac{2\pi}{g_0}\right),
$$

in the normalization used here. A different normalization of $g_0$ changes the coefficient in the exponent, not the phenomenon:

$$
M\sim \Lambda e^{-\text{const}/g_0}.
$$

This is dimensional transmutation. The classical coupling is dimensionless, but the quantum theory generates a physical mass scale. The generated mass is nonperturbative in $g_0$ because no Taylor series in $g_0$ can produce $e^{-\text{const}/g_0}$.

The large-$N$ saddle therefore gives a controlled answer to a question perturbation theory cannot answer: what sets the infrared correlation length?

$$
\xi\sim M^{-1}.
$$

## Induced gauge dynamics

Although $A_\mu$ begins as an auxiliary field in the gauged quotient description, it acquires an effective kinetic term after the $z_i$ fields are integrated out. Expanding

$$
N\operatorname{Tr}\log(-D^2+M^2)
$$

in slowly varying $A_\mu$ gives a Maxwell-type term of the form

$$
S_{\rm eff}[A]
\supset
\int d^2x\,\frac{1}{4e_{\rm eff}^2}F_{\mu\nu}F_{\mu\nu},
$$

with

$$
e_{\rm eff}^2\sim \frac{M^2}{N}.
$$

The exact numerical coefficient depends on the normalization of $z$, $g_0$, and the gauge kinetic term. The scaling is the robust lesson: the induced gauge coupling is small at large $N$, but the gauge field is dynamically meaningful.

In two dimensions, Maxwell theory has no propagating photon. It still mediates a linear potential between static charges. If two external unit charges are separated by distance $R$, Gauss's law gives a constant electric field between them, and the energy grows like

$$
V(R)\sim e_{\rm eff}^2 R.
$$

Thus, parametrically,

$$
V(R)\sim \frac{M^2}{N}R.
$$

This is often called confinement in the $CP^{N-1}$ model. It is real, but it is two-dimensional. The mechanism relies on the absence of propagating gauge-field degrees of freedom and should not be carelessly exported to four-dimensional Yang–Mills.

## What is confined?

The elementary $z_i$ fields carry the projective $U(1)$ gauge charge. They are not gauge-invariant local observables, and the induced gauge dynamics confines them into neutral composites. The physical spectrum is built from gauge-invariant combinations such as

$$
\bar z_i z_j
$$

with the trace part separated as needed.

This sounds like quark confinement, and the analogy is useful, but there are two big caveats.

First, this is a two-dimensional model. Linear Coulomb potentials in two dimensions are much easier to obtain than flux-tube confinement in four-dimensional non-Abelian gauge theory.

Second, the gauge group in the projective formulation is $U(1)$, not the non-Abelian color group of QCD. The global symmetry of the model is $SU(N)$, while the local redundancy is the projective $U(1)$.

The better slogan is therefore:

$$
CP^{N-1}\text{ is a solvable analogue of confinement, not a miniature copy of QCD.}
$$

## Theta dependence and topological susceptibility

The topological charge is

$$
Q=\frac1{2\pi}\int F.
$$

The theta-dependent partition function is formally

$$
Z(\theta)=\sum_{Q\in\mathbb Z} e^{i\theta Q} Z_Q.
$$

The vacuum energy density is

$$
E(\theta)=-\lim_{V\to\infty}\frac1V\log Z(\theta).
$$

Because $\theta$ is $2\pi$ periodic, the large-$N$ answer cannot simply be a single quadratic function of $\theta$ for all $\theta$. A typical large-$N$ branch structure is

$$
E(\theta)=N M^2\min_{k\in\mathbb Z}
 f\left(\frac{\theta+2\pi k}{N}\right),
$$

where $f$ is smooth near the origin. Expanding near $\theta=0$ on the lowest branch gives

$$
E(\theta)-E(0)
=
\frac12\chi_t\theta^2+O\left(\frac{\theta^4}{N^3}\right),
$$

with

$$
\chi_t=O\left(\frac{M^2}{N}\right)
$$

in this two-dimensional large-$N$ model. The precise coefficient is convention-dependent, but the existence and scaling of a nonzero topological susceptibility are central outputs of the large-$N$ solution.

The branch label $k$ is not decorative. At large $N$, there are many long-lived quasivacua. At $\theta=0$, one branch is the true vacuum and nearby branches are split by energies of order $1/N$ in appropriate units. This branch structure is one of the main ways the $CP^{N-1}$ model teaches large-$N$ theta physics.

## Instantons versus the large-N saddle

The $CP^{N-1}$ model has instantons. At finite $N$, classical instanton solutions exist, and the theta term weighs sectors by $e^{i\theta Q}$. So why not solve the model by a dilute instanton gas?

Because the instanton expansion and the large-$N$ expansion emphasize different limits. On the infinite plane, instanton calculus in the $CP^{N-1}$ model suffers from infrared problems. The large-$N$ saddle gives well-defined nonperturbative physics, including the mass gap and topological susceptibility, without assuming a dilute instanton gas.

This is one of the healthiest lessons in nonperturbative QFT: the existence of instantons does not guarantee that instanton calculus is the right controlled approximation for the observable and limit under study.

A compact way to remember the distinction is:

$$
\text{instantons classify sectors and may contribute,}
\qquad
\text{large }N\text{ solves by collective saddles.}
$$

In some compactified or deformed settings, semiclassical constituents of instantons become controlled and connect to resurgence. That is important, but it is a later story. The ordinary infinite-volume large-$N$ $CP^{N-1}$ model should not be taught as merely a dilute instanton gas in disguise.

## Checks and diagnostics

A good calculation in the $CP^{N-1}$ model should pass these checks.

| Check | What to verify |
|---|---|
| Gauge redundancy | The answer should be invariant under $z_i\mapsto e^{i\alpha(x)}z_i$. |
| Constraint | The saddle equation should enforce $\langle \bar z z\rangle=N/g_0$. |
| Mass gap | The $z$ propagator at fixed saddle should contain $p^2+M^2$. |
| Dimensional transmutation | The generated scale should be exponentially small at weak bare coupling in two dimensions. |
| Large-N counting | The effective action for $A_\mu$ and $\lambda$ should be proportional to $N$. |
| Theta periodicity | The full vacuum energy must be $2\pi$ periodic, often through multiple branches. |
| Observable gauge invariance | Physical local operators should be neutral composites, not bare $z_i$. |
| Analogy discipline | Statements about QCD should be phrased as analogies, not derived consequences. |

## Common pitfalls

**Calling $A_\mu$ a fundamental photon without qualification.** In this formulation, $A_\mu$ starts as the connection implementing the projective quotient. It becomes dynamically important after integrating out the large number of charged fields.

**Forgetting that $z_i$ is not gauge invariant.** The field $z_i$ is useful in the calculation, but physical local observables must be invariant under the local phase redundancy.

**Confusing $SU(N)$ and the projective $U(1)$.** The model has a global $SU(N)$ symmetry acting on the index $i$ and a local $U(1)$ redundancy acting by phase rotations. They do different jobs.

**Overstating the QCD analogy.** The model is asymptotically free, has a mass gap, has theta dependence, and has confinement-like behavior. It is still two-dimensional and Abelian in its local gauge redundancy.

**Treating the one-instanton approximation as the whole story.** Instantons exist, but the large-$N$ solution is not the same as a naive dilute instanton gas on the infinite plane.

**Missing the branch structure of theta dependence.** A single smooth function of $\theta/N$ is not enough by itself, because the full answer must be $2\pi$ periodic in $\theta$.

## Relations to other pages

[Large-N Sigma Models](/nonperturbative-qft/large-n-methods/large-n-sigma-models/) introduces this page's saddle method in the simpler $O(N)$ setting. The $CP^{N-1}$ model adds local projective redundancy, induced gauge dynamics, and theta sectors.

[Saddle Points at Large N](/nonperturbative-qft/large-n-methods/saddle-points-at-large-n/) explains the general steepest-descent structure behind the calculation: why $S_{\rm eff}=Ns_{\rm eff}$ produces a classical collective limit and why $e^{-N}$ effects are invisible in the ordinary $1/N$ expansion.

[Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/), [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/), and [Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/) give the general topological language used here.

[Large-N Yang–Mills](/nonperturbative-qft/large-n-methods/large-n-yang-mills/) and [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) are the harder gauge-theory cousins. The analogy with $CP^{N-1}$ is instructive but not a proof of four-dimensional confinement.

For exact low-dimensional models, a later page on $CP^{N-1}$ exact results will treat integrability, finite volume, resurgence, and special supersymmetric variants more systematically.

## Research status

**Established.** The large-$N$ solution of the two-dimensional $CP^{N-1}$ model is a standard nonperturbative result. It gives mass generation, induced gauge dynamics, theta dependence, and topological susceptibility in a controlled expansion.

**Established with caveats.** The model is a powerful analogue of Yang–Mills theory, especially for asymptotic freedom, theta dependence, and confinement-like physics. The analogy is qualitative and structural, not a derivation of four-dimensional QCD.

**Active.** Modern work continues to study finite-$N$ theta dependence, resurgence, renormalons, compactification, boundary conditions, anomalies, supersymmetric versions, and relations between semiclassical and large-$N$ descriptions.

## Exercises

### Exercise 1: Eliminate the auxiliary gauge field classically

Assume $\bar z z=R^2$ is constant and consider

$$
|D_\mu z|^2=|\partial_\mu z-iA_\mu z|^2.
$$

Vary with respect to $A_\mu$ and show that

$$
A_\mu=-\frac{i}{2R^2}
\left(\bar z\partial_\mu z-(\partial_\mu\bar z)z\right).
$$

<details>
<summary><strong>Solution</strong></summary>

Expand

$$
|D_\mu z|^2
=(\partial_\mu\bar z+iA_\mu\bar z)(\partial_\mu z-iA_\mu z).
$$

Keeping only the $A_\mu$ dependence,

$$
|D_\mu z|^2
=
\cdots
+iA_\mu\bar z\partial_\mu z
-iA_\mu(\partial_\mu\bar z)z
+A_\mu^2\bar z z.
$$

Varying gives

$$
0=i\bar z\partial_\mu z-i(\partial_\mu\bar z)z+2A_\mu\bar z z.
$$

Since $\bar z z=R^2$,

$$
A_\mu=-\frac{i}{2R^2}
\left(\bar z\partial_\mu z-(\partial_\mu\bar z)z\right).
$$

</details>

### Exercise 2: Solve the two-dimensional gap equation

Evaluate

$$
\frac1{g_0}
=\int^\Lambda\frac{d^2p}{(2\pi)^2}\frac1{p^2+M^2}
$$

with a rotational cutoff and show that $M$ is exponentially small at weak coupling.

<details>
<summary><strong>Solution</strong></summary>

Using polar coordinates,

$$
\int^\Lambda\frac{d^2p}{(2\pi)^2}\frac1{p^2+M^2}
=
\frac1{2\pi}\int_0^\Lambda dp\,\frac{p}{p^2+M^2}.
$$

The integral is

$$
\frac1{4\pi}\log\frac{\Lambda^2+M^2}{M^2}.
$$

For $M\ll\Lambda$,

$$
\frac1{g_0}\simeq \frac1{2\pi}\log\frac{\Lambda}{M}.
$$

Solving,

$$
M\simeq \Lambda\exp\left(-\frac{2\pi}{g_0}\right).
$$

This is nonanalytic at $g_0=0$, so it cannot be obtained from an ordinary power series in $g_0$.

</details>

### Exercise 3: Linear potential in two-dimensional Maxwell theory

Consider two static charges $+1$ and $-1$ separated by distance $R$ in two-dimensional Maxwell theory with Hamiltonian density

$$
\mathcal H=\frac{1}{2e^2}E^2.
$$

Use Gauss's law to show that the potential is linear in $R$.

<details>
<summary><strong>Solution</strong></summary>

Gauss's law is

$$
\partial_x E=e^2\left[\delta(x)-\delta(x-R)\right].
$$

Taking $E=0$ outside the interval between the charges gives

$$
E=e^2
$$

for $0<x<R$. The energy is therefore

$$
V(R)=\int_0^R dx\,\frac{1}{2e^2}E^2
=\int_0^R dx\,\frac{1}{2e^2}e^4
=\frac{e^2}{2}R.
$$

Thus two-dimensional Maxwell theory produces a linear potential even without propagating photons.

</details>

### Exercise 4: Theta branches and susceptibility scaling

Suppose the large-$N$ theta-dependent vacuum energy has branches

$$
E_k(\theta)=N M^2 f\left(\frac{\theta+2\pi k}{N}\right),
$$

where $f(x)=f(0)+\frac12 c x^2+O(x^4)$ near $x=0$. Show that the topological susceptibility on the $k=0$ branch scales as $M^2/N$.

<details>
<summary><strong>Solution</strong></summary>

On the $k=0$ branch,

$$
E_0(\theta)-E_0(0)
=N M^2\left[\frac12 c\left(\frac{\theta}{N}\right)^2+O\left(\frac{\theta^4}{N^4}\right)\right].
$$

Therefore

$$
E_0(\theta)-E_0(0)
=\frac12\frac{cM^2}{N}\theta^2+O\left(\frac{\theta^4}{N^3}\right).
$$

Since

$$
\chi_t=\left.\frac{\partial^2E}{\partial\theta^2}\right|_{\theta=0},
$$

we find

$$
\chi_t=\frac{cM^2}{N}.
$$

</details>

## References

### Standard first pass

- M. Mariño, *Instantons and Large N*, especially the chapters on sigma models at large $N$ and on the $CP^{N-1}$ model.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the discussions of $CP(N-1)$ models, confinement in lower dimensions, quasivacua, and large-$N$ sigma-model solutions.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on sigma models, instantons, compact gauge fields, and large $N$.

### Deeper references

- E. Witten, “Instantons, the Quark Model, and the 1/N Expansion,” for the classic large-$N$ analysis of $CP^{N-1}$ and theta dependence.
- A. D'Adda, M. Lüscher, and P. Di Vecchia, classic papers on the $CP^{N-1}$ model and its large-$N$ structure.
- A. M. Polyakov, original work on compact gauge dynamics and confinement analogues in lower-dimensional QFT.
- Modern resurgence and compactification literature on the $CP^{N-1}$ model for the relation between semiclassical saddles, renormalons, and large-$N$ physics.

## Version history

- **2026-06-27:** Initial polished page on the large-$N$ $CP^{N-1}$ model, including projective formulation, mass generation, induced gauge dynamics, theta dependence, and confinement caveats.
