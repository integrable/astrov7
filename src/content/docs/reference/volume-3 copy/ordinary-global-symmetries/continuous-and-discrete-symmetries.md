---
title: "Continuous and Discrete Symmetries"
description: "Explains the difference between continuous and discrete global symmetries in QFT, including charges, currents, topological operators, selection rules, breaking patterns, and anomaly-sensitive caveats."
sidebar:
  label: "Continuous and Discrete"
  order: 3
level: Graduate
status: "Polished draft"
source: "Coleman, Srednicki, Zee, Weinberg; Gaiotto–Kapustin–Seiberg–Willett for the topological-operator language."
topics:
  - continuous symmetries
  - discrete symmetries
  - Lie groups
  - Noether currents
  - selection rules
  - topological symmetry defects
canonicalTopics:
  - continuous-symmetry
  - discrete-symmetry
  - noether-charge
  - finite-group-selection-rule
researchStatus:
  established:
    - "The distinction between continuous Lie symmetries and discrete symmetries, including the existence of Noether currents only for continuous ordinary symmetries, is standard QFT material."
  active:
    - "Discrete generalized symmetries, finite-group gauging, non-invertible defects, and anomaly-sensitive global forms remain active parts of modern QFT research."
---

## Summary

A global symmetry can be continuous or discrete.

A **continuous symmetry** has transformations connected smoothly to the identity. It has infinitesimal generators. In ordinary local QFT, a continuous internal symmetry usually gives a conserved current,

$$
\partial_\mu j_a^\mu=0,
$$

and a conserved charge,

$$
Q_a=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x).
$$

A **discrete symmetry** has isolated transformations. A $\mathbb Z_2$ sign flip,

$$
\phi(x)\mapsto -\phi(x),
$$

has no infinitesimal generator and no ordinary Noether current. It can still be a powerful physical symmetry, producing selection rules, protected degeneracies, domain walls when broken, constraints on effective actions, and possible ’t Hooft anomalies.

The fastest comparison is:

| Feature | Continuous ordinary symmetry | Discrete ordinary symmetry |
|---|---|---|
| Example | $U(1)$, $SU(N)$, translations | $\mathbb Z_2$, charge conjugation, parity, finite flavor group |
| Connected to identity? | Yes, at least in the identity component | No, except for the identity element |
| Infinitesimal generators? | Yes | Usually no |
| Ordinary Noether current? | Usually yes | No ordinary local Noether current |
| Selection rules? | Yes | Yes |
| Symmetry defect viewpoint? | Topological family $U_g(\Sigma)$ | Topological defects labeled by finite group elements |
| Spontaneous breaking? | Goldstone modes under suitable assumptions | Degenerate vacua and domain walls, but no Goldstone modes |

<figure class="doc-figure" style="--figure-width: 52rem;">

![A diagram showing an identity component with a Lie algebra, disconnected components, and a finite cyclic group with isolated elements.](/figures/symmetry-anomalies-topology/continuous-discrete-symmetry-components.svg)

<figcaption>

The Lie algebra $\mathfrak g$ sees the identity component $G_0$. It does not by itself see disconnected components, finite groups such as $\mathbb Z_4$, or quotient data that affect representations and backgrounds.

</figcaption>
</figure>

The word “usually” matters. Gauge constraints, anomalies, boundaries, higher-form symmetries, topological theories, nonrelativistic systems, and non-invertible symmetries all introduce caveats. This page explains the basic distinction before those refinements appear.

## Prerequisites

You should know [What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/) and [Internal versus Spacetime Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/internal-versus-spacetime-symmetries/). We use the convention

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

You should also know that a group can have disconnected components. A group such as $O(N)$ has a continuous identity component $SO(N)$ and a discrete reflection component. A finite group such as $\mathbb Z_N$ is purely discrete.

## Core idea

The distinction between continuous and discrete symmetry is the distinction between transformations that can be infinitesimally varied and transformations that cannot.

For a continuous symmetry near the identity, write

$$
g(\alpha)=e^{-i\alpha^aT_a},
$$

or, on the Hilbert space,

$$
U(\alpha)=e^{-i\alpha^aQ_a}.
$$

The small parameters $\alpha^a$ allow us to differentiate the symmetry. That derivative is what produces infinitesimal field variations, Lie algebras, conserved currents, Ward identities, and charges.

For a discrete symmetry, there is no small parameter. The nontrivial element of $\mathbb Z_2$ is not “almost the identity.” It is just a separate transformation. Therefore the standard Noether theorem, which starts by making the transformation parameter spacetime dependent and reading off the coefficient of $\partial_\mu\alpha(x)$, has no ordinary discrete analogue.

But discrete symmetry is not weaker. It is less differential and more global. It can forbid operators, classify sectors, enforce exact degeneracies, protect topological phases, and obstruct gauging through anomalies.

A useful slogan is

$$
\text{continuous symmetry gives currents; discrete symmetry gives constraints without currents}.
$$

## Setup and conventions

This page mainly discusses ordinary internal symmetries. Spacetime and antiunitary discrete symmetries, such as parity and time reversal, are treated in a later chapter. The logic here still helps with them, but antiunitarity and coordinate reflection add extra structure.

For a continuous symmetry with Hermitian charges $Q_a$, we use

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c
$$

for a Lie algebra with real structure constants in the chosen basis. The infinitesimal action on an operator is

$$
\delta_\alpha\mathcal O=i\alpha^a[Q_a,\mathcal O].
$$

For a finite abelian group $\mathbb Z_N$, it is often convenient to write charges modulo $N$. If the generator $g$ acts on an operator $\mathcal O_q$ by

$$
g\cdot\mathcal O_q=e^{2\pi iq/N}\mathcal O_q,
\qquad
q\in\mathbb Z_N,
$$

then a correlator in an invariant vacuum can be nonzero only if the total discrete charge is zero modulo $N$.

:::note[Source note]
Some texts reserve the word “charge” for continuous Noether charges and use “quantum number” for discrete labels. This volume allows both phrases, but keeps the distinction clear: a continuous charge is generated by an operator such as $Q$; a discrete charge is a representation label, often defined modulo $N$.
:::

## Continuous symmetries and infinitesimal transformations

A continuous symmetry group has a neighborhood of the identity. This lets us study finite transformations by first understanding infinitesimal ones.

For a one-parameter $U(1)$ symmetry,

$$
U(\alpha)=e^{-i\alpha Q}.
$$

An operator of charge $q$ obeys

$$
[Q,\mathcal O_q]=q\mathcal O_q,
$$

and therefore

$$
U(\alpha)^\dagger\mathcal O_qU(\alpha)
=e^{iq\alpha}\mathcal O_q.
$$

For a nonabelian continuous symmetry, generators satisfy a Lie algebra. Operators do not usually have a single charge number; they sit in representations. If $\mathcal O_i$ belongs to a representation $R$, then

$$
\delta_a\mathcal O_i=i(T_a^{(R)})_i{}^j\mathcal O_j,
$$

with convention-dependent factors of $i$ depending on whether the matrices are chosen Hermitian or anti-Hermitian.

The infinitesimal point of view has three major payoffs.

First, it gives **charges** that act on states and operators. These charges organize the Hilbert space into multiplets.

Second, in local Lagrangian QFT it gives **currents**. If the action is invariant under a constant parameter $\alpha$, then allowing $\alpha$ to vary slowly with spacetime exposes a current $j^\mu$.

Third, it gives **Ward identities**. In correlation functions, current conservation becomes a precise statement with contact terms when the current insertion collides with charged operators.

## Noether currents belong to continuous symmetries

Consider a field transformation depending on a small constant parameter,

$$
\Phi^I(x)\mapsto \Phi^I(x)+\alpha^a\Delta_a\Phi^I(x)+O(\alpha^2).
$$

If the action changes by at most a boundary term, Noether’s theorem gives a current $j_a^\mu$ satisfying the equations-of-motion conservation law

$$
\partial_\mu j_a^\mu=0.
$$

The associated charge is

$$
Q_a(t)=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x),
$$

and current conservation implies that $Q_a$ is time independent, assuming suitable boundary conditions.

For the complex scalar with $U(1)$ symmetry,

$$
\phi\mapsto e^{i\alpha}\phi,
\qquad
\phi^\dagger\mapsto e^{-i\alpha}\phi^\dagger,
$$

a common current convention is

$$
j^\mu=i\left(\phi^\dagger\partial^\mu\phi-(\partial^\mu\phi^\dagger)\phi\right),
$$

up to an overall sign depending on whether one defines $\delta\phi=+i\alpha\phi$ or $-i\alpha\phi$ and how the charge is inserted in $U(\alpha)$.

:::note[Convention-sensitive formula]
The overall sign of $j^\mu$ is tied to the convention for $U(\alpha)$ and $\delta\phi$. The invariant statement is that the charge generated by $j^0$ must satisfy $[Q,\phi]=\phi$ for a unit-charge field in the convention of this volume.
:::

The next chapter treats Noether currents and Ward identities in detail. For now the lesson is narrow: the current exists because the transformation can be differentiated at the identity.

## Discrete symmetries and finite transformations

A discrete symmetry has no infinitesimal generator. The simplest example is a real scalar theory with

$$
\phi(x)\mapsto -\phi(x).
$$

If the action and measure preserve this transformation, then correlators with an odd number of $\phi$ insertions vanish in an invariant vacuum:

$$
\langle\phi(x_1)\cdots\phi(x_{2n+1})\rangle=0.
$$

This selection rule is just as exact as charge conservation in a $U(1)$ theory. The difference is that it does not come from a local current $j^\mu$.

For a $\mathbb Z_N$ symmetry, choose a generator $g$ with $g^N=1$. If

$$
g\cdot\mathcal O_q=e^{2\pi iq/N}\mathcal O_q,
$$

then a correlator in an invariant vacuum obeys

$$
\left\langle\prod_i\mathcal O_{q_i}(x_i)\right\rangle
=e^{2\pi i(\sum_iq_i)/N}
\left\langle\prod_i\mathcal O_{q_i}(x_i)\right\rangle.
$$

Therefore

$$
\sum_iq_i=0\pmod N
$$

is required for the correlator to be nonzero.

For a nonabelian finite group, the rule is representation-theoretic: the tensor product of representations carried by the insertions must contain the trivial representation.

## Discrete subgroups of continuous groups

Discrete symmetries often arise as subgroups of continuous symmetries. This is useful, but it can also mislead.

Suppose a theory of a complex scalar has a $U(1)$ symmetry,

$$
\phi\mapsto e^{i\alpha}\phi.
$$

Adding the interaction

$$
\Delta\mathcal L=\epsilon\phi^N+\epsilon^*(\phi^\dagger)^N
$$

breaks $U(1)$ explicitly to $\mathbb Z_N$, because the term is invariant only when

$$
e^{iN\alpha}=1.
$$

The continuous Noether current is no longer conserved. But the discrete subgroup remains exact if the quantum theory respects it.

The corresponding selection rule changes from

$$
\sum_iq_i=0
$$

to

$$
\sum_iq_i=0\pmod N.
$$

This is one of the cleanest ways to see the difference between continuous and discrete symmetry. Continuous charge conservation is stronger; discrete charge conservation only remembers charge modulo $N$.

:::caution[Do not infer a current from a subgroup]
A discrete group can sit inside a continuous group without inheriting a conserved current in the actual theory. If the continuous symmetry is explicitly broken to $\mathbb Z_N$, only the discrete symmetry remains.
:::

## Connected components and global form

Not every symmetry group is purely continuous or purely discrete. Many groups have both.

The group $O(N)$ has two connected components. The identity component is $SO(N)$, a continuous group. The other component contains reflections. There is a short exact sequence

$$
1\to SO(N)\to O(N)\to\mathbb Z_2\to1.
$$

A theory with full $O(N)$ symmetry therefore has continuous rotations and a discrete orientation-reversing part. The $SO(N)$ currents do not automatically generate the reflection. The reflection is a separate disconnected transformation.

This is why the global form of the group matters. Knowing only the Lie algebra tells you the connected continuous part. It misses discrete components and global identifications.

For example, $SU(2)$ and $SO(3)$ have the same Lie algebra but different global forms. Their continuous infinitesimal currents may look locally similar, but their allowed representations, line operators, bundles, and anomalies can differ.

## Topological-operator viewpoint

Both continuous and discrete ordinary symmetries can be represented by codimension-one topological operators,

$$
U_g(\Sigma_{d-1}),
\qquad
g\in G.
$$

For a continuous group, $g$ varies continuously. For a discrete group, $g$ is one of a finite or countable set of isolated elements. In both cases, the operator can be deformed without changing correlation functions unless it crosses charged insertions.

For $G=U(1)$,

$$
U_\alpha(\Sigma)\mathcal O_q
\quad\leadsto\quad
 e^{iq\alpha}\mathcal O_q
$$

when the symmetry surface crosses $\mathcal O_q$.

For $G=\mathbb Z_N$,

$$
U_g(\Sigma)\mathcal O_q
\quad\leadsto\quad
 e^{2\pi iq/N}\mathcal O_q.
$$

The topology of the defect gives the same selection rules derived algebraically. Surround a collection of insertions by a closed symmetry surface and shrink it. The correlator survives only if the combined symmetry action is trivial.

This is why discrete symmetries are not “currentless afterthoughts.” They have perfectly good topological symmetry operators, even when they have no ordinary local Noether current.

## Background fields and gauging preview

Continuous and discrete symmetries are also probed differently by background fields.

For a continuous $U(1)$ symmetry, one couples a background gauge field $A_\mu$ to the current,

$$
\Delta S=\int d^dx\,A_\mu j^\mu,
$$

up to sign and Euclidean-continuation conventions.

For a finite group $G$, there is no local current $j^\mu$ and no ordinary small background gauge potential. Instead, one couples to a background finite $G$ bundle. On a lattice or in a cut-and-glue picture, this can be represented by transition functions or branch cuts labeled by group elements.

Gauging also differs. Gauging a continuous symmetry involves integrating over continuous gauge fields, gauge fixing, and ghosts in perturbative treatments. Gauging a finite symmetry means summing over finite-group background bundles. Both are forms of “summing over backgrounds,” but the technical realizations are different.

Anomalies are obstructions to gauging. A continuous symmetry can have a perturbative anomaly visible in current conservation. A discrete symmetry can have an anomaly even without a current. The anomaly is then detected by failure of consistent coupling to background bundles, or by anomaly inflow from one higher dimension.

## Spontaneous breaking: Goldstones versus domain walls

Continuous and discrete symmetries behave very differently when spontaneously broken.

If a continuous internal symmetry $G$ breaks to a subgroup $H$,

$$
G\to H,
$$

then under suitable assumptions there are gapless Goldstone modes parameterizing directions in $G/H$. The number and dispersion of Goldstone modes depend on Lorentz invariance, charge densities, and other details, but the existence of soft modes is the key signature.

If a discrete symmetry breaks, there is no continuous manifold of nearby vacua. There are multiple isolated vacua instead. For a $\mathbb Z_2$ scalar theory, the two vacua might have

$$
\langle\phi\rangle=+v,
\qquad
\langle\phi\rangle=-v.
$$

The broken discrete symmetry gives degenerate vacua and domain walls between them, not Goldstone bosons.

Both statements have qualifications in low dimensions, finite volume, gauge theories, and systems with long-range interactions. The Spontaneous Symmetry Breaking chapter handles those carefully.

## Explicit, spontaneous, and anomalous breaking

The continuous/discrete distinction cuts across three different ways a symmetry can fail.

**Explicit breaking** means the symmetry is not a symmetry of the action or Hamiltonian. For example, adding $\epsilon\phi$ to a $\mathbb Z_2$ scalar theory explicitly breaks $\phi\mapsto-\phi$.

**Spontaneous breaking** means the theory has the symmetry but the chosen vacuum does not. The equations still respect the symmetry; the state chooses a direction.

**Anomalous breaking** means a classical symmetry cannot be preserved by the quantum theory together with the required regulator, measure, locality, and background coupling. This can happen for continuous or discrete symmetries.

These are not interchangeable. A discrete symmetry can be exact, explicitly broken, spontaneously broken, or anomalous. A continuous symmetry can also be exact, explicitly broken, spontaneously broken, or anomalous.

:::caution[Common language trap]
Do not say “there is no current, so the symmetry is broken.” Discrete symmetries have no ordinary Noether current even when exact. Currentlessness is not breaking.
:::

## Approximate symmetries

Many useful symmetries are approximate. Approximate continuous symmetry can produce pseudo-Goldstone bosons. Approximate discrete symmetry can produce long-lived but not absolutely stable domain walls or particles.

For example, suppose a theory has an approximate $U(1)$ symmetry broken weakly to $\mathbb Z_N$. At energies or timescales where the breaking is negligible, the theory may behave as if charge is conserved. At sufficiently high precision, only charge modulo $N$ is conserved.

Effective field theory makes this precise. Operators that violate a symmetry can be suppressed by a high scale, small coupling, or RG irrelevance. The question is not whether the symmetry is emotionally pleasing; the question is which terms are allowed and how large they are.

Approximate symmetry should always be labeled as approximate. Exact selection rules become approximate suppressions.

## Common pitfalls

**Thinking discrete symmetries are less real.** They are just as physical as continuous symmetries. They lack infinitesimal currents, not consequences.

**Looking for a Noether current for $\mathbb Z_2$.** There is no ordinary local Noether current for an isolated sign flip. Use finite transformations, topological defects, or background finite bundles instead.

**Confusing a discrete subgroup with the full continuous group.** If $U(1)$ is explicitly broken to $\mathbb Z_N$, charge is conserved only modulo $N$.

**Using Lie algebras to answer global questions.** Lie algebras see the identity component. They miss disconnected components, centers, quotients, allowed representations, and finite-group anomalies.

**Assuming broken discrete symmetry gives Goldstone bosons.** Goldstone modes require continuous degeneracy. Broken discrete symmetry gives isolated vacua and domain walls.

**Forgetting antiunitary complications.** Time reversal is discrete, but it is also antiunitary. It cannot be treated as just another unitary finite group element.

**Assuming every continuous classical symmetry survives quantization.** Continuous symmetries can have anomalies. Discrete symmetries can too.

## Relations to other pages

- [What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/) explains the operator and correlator definition used for both continuous and discrete symmetry.
- [Internal versus Spacetime Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/internal-versus-spacetime-symmetries/) distinguishes a separate axis: whether the transformation moves spacetime support.
- [Conventions and Notation](/symmetry-anomalies-topology/conventions/) fixes the charge convention $U(\alpha)=e^{-i\alpha^aQ_a}$ used for continuous symmetries.
- [Ordinary Global Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/) gives the chapter-level reading path.

Later chapters use this distinction in different ways: Noether currents and Ward identities use the continuous side; background fields and gauging treat both continuous and finite groups; spontaneous symmetry breaking separates Goldstone modes from domain walls; anomaly chapters explain how both continuous and discrete symmetries can fail to be gaugeable.

## Research status

The basic continuous/discrete distinction is settled. It is part of the standard grammar of QFT, statistical mechanics, and condensed matter theory.

The active research frontier lies in generalized and categorical versions: finite-group gauging in diverse dimensions, non-invertible defects produced by gauging non-anomalous subgroups, discrete higher-form symmetries, subsystem symmetries, anomaly classification, symmetry TFT, and the role of discrete symmetry in quantum gravity. These topics build on the elementary distinction here but replace “group with currents” by a broader algebra of topological operators and defects.

## Exercises

### Exercise 1: The $\mathbb Z_N$ selection rule

Let $g$ generate a $\mathbb Z_N$ symmetry, and let

$$
g\cdot\mathcal O_{q_i}=e^{2\pi iq_i/N}\mathcal O_{q_i}.
$$

Assuming the vacuum is invariant, show that

$$
\left\langle\prod_i\mathcal O_{q_i}(x_i)\right\rangle
$$

vanishes unless $\sum_iq_i=0\pmod N$.

<details>
<summary><strong>Solution</strong></summary>

Use vacuum invariance and transform every insertion by $g$:

$$
\left\langle\prod_i\mathcal O_{q_i}(x_i)\right\rangle
=
\left\langle\prod_i g\cdot\mathcal O_{q_i}(x_i)\right\rangle.
$$

The right-hand side is

$$
e^{2\pi i(\sum_iq_i)/N}
\left\langle\prod_i\mathcal O_{q_i}(x_i)\right\rangle.
$$

If $\sum_iq_i$ is not divisible by $N$, the phase is not $1$, so the correlator must equal a nontrivial phase times itself. Therefore it vanishes.

</details>

### Exercise 2: Breaking $U(1)$ to $\mathbb Z_N$

A complex scalar transforms as $\phi\mapsto e^{i\alpha}\phi$. Show that the interaction

$$
\Delta\mathcal L=\epsilon\phi^N+\epsilon^*(\phi^\dagger)^N
$$

preserves only a $\mathbb Z_N$ subgroup of the original $U(1)$ symmetry, assuming $\epsilon\neq0$.

<details>
<summary><strong>Solution</strong></summary>

Under the $U(1)$ transformation,

$$
\phi^N\mapsto e^{iN\alpha}\phi^N,
\qquad
(\phi^\dagger)^N\mapsto e^{-iN\alpha}(\phi^\dagger)^N.
$$

For $\Delta\mathcal L$ to be invariant for general nonzero $\epsilon$, we need

$$
e^{iN\alpha}=1.
$$

Thus

$$
\alpha=\frac{2\pi k}{N},
\qquad
k=0,1,\ldots,N-1.
$$

These transformations form $\mathbb Z_N$.

</details>

### Exercise 3: Why a sign flip has no ordinary Noether current

Explain why the $\mathbb Z_2$ transformation $\phi\mapsto-\phi$ does not produce an ordinary Noether current by the standard infinitesimal argument.

<details>
<summary><strong>Solution</strong></summary>

The standard Noether construction begins with a continuous transformation near the identity,

$$
\phi\mapsto\phi+\alpha\Delta\phi+O(\alpha^2),
$$

and then lets $\alpha$ depend on spacetime. The coefficient of $\partial_\mu\alpha(x)$ defines the current.

The transformation $\phi\mapsto-\phi$ is not infinitesimally close to the identity. There is no small real parameter $\alpha$ with $\phi+\alpha\Delta\phi=-\phi$ for arbitrary small $\alpha$. Therefore the standard Noether-current derivation has no input. The symmetry is still real and can still impose selection rules, but it has no ordinary local Noether current.

</details>

### Exercise 4: Broken discrete symmetry and domain walls

Consider a real scalar potential

$$
V(\phi)=\frac\lambda4(\phi^2-v^2)^2.
$$

Identify the symmetry and the classical vacua. Why does breaking this symmetry not imply a Goldstone boson?

<details>
<summary><strong>Solution</strong></summary>

The potential is invariant under

$$
\phi\mapsto-\phi,
$$

so the symmetry is $\mathbb Z_2$. The classical vacua are

$$
\phi=+v,
\qquad
\phi=-v.
$$

Choosing either vacuum spontaneously breaks the $\mathbb Z_2$ symmetry. There is no Goldstone boson because the vacuum manifold consists of two isolated points, not a continuous manifold of degenerate vacua. There can instead be domain-wall configurations interpolating between $+v$ and $-v$ in space.

</details>

### Exercise 5: Continuous versus discrete charge conservation

Suppose an operator $\mathcal O$ has charge $1$ under a $U(1)$ symmetry. Compare the correlators

$$
\langle\mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\rangle
$$

in a theory with exact $U(1)$ symmetry and in a theory where only the $\mathbb Z_3$ subgroup remains.

<details>
<summary><strong>Solution</strong></summary>

With exact $U(1)$ symmetry, the total charge is

$$
1+1+1=3,
$$

which is not zero. Therefore the correlator is forbidden by $U(1)$ charge conservation.

With only $\mathbb Z_3$, charges are conserved modulo $3$. The total charge is

$$
3=0\pmod3.
$$

So the correlator is allowed by the $\mathbb Z_3$ symmetry, though it may still vanish for other dynamical reasons.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chapters 5–6. Internal and spacetime symmetries, currents, and conservation laws.
- Sidney Coleman, *Aspects of Symmetry*, especially “Secret Symmetry” and “Classical Lumps and Their Quantum Descendants.” Symmetry breaking, Goldstone physics, and topological consequences.
- Mark Srednicki, *Quantum Field Theory*, sections 22–24 and 30–32. Continuous, discrete, nonabelian, and spontaneously broken symmetries.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 2. Symmetries in quantum theory and the role of unitary and antiunitary implementations.
- A. Zee, *Quantum Field Theory in a Nutshell*, chapters on symmetry and symmetry breaking. Physical motivation and examples.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.” Topological symmetry operators and the bridge to higher-form symmetries.

## Version history

- **2026-06-17:** Initial polished page comparing continuous and discrete ordinary global symmetries, currents, selection rules, and breaking patterns.
