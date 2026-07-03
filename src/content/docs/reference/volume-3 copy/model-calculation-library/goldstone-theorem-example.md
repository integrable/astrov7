---
title: "Goldstone Theorem Example"
description: "Model calculation deriving the massless Goldstone mode in the spontaneously broken O(2) scalar model and relating it to the current matrix element."
sidebar:
  label: "Goldstone Theorem Example"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §§30–32; Coleman, Aspects of Symmetry, Secret Symmetry; Coleman QFT Lectures ch. 6; Schwartz §28.2."
topics:
  - Goldstone theorem
  - spontaneous symmetry breaking
  - O(2) model
  - Noether current
  - vacuum manifold
  - massless modes
canonicalTopics:
  - goldstone-theorem
  - spontaneous-symmetry-breaking
  - broken-continuous-symmetry
  - o2-scalar-model
researchStatus:
  established:
    - "The appearance of a massless Goldstone mode for each broken continuous global symmetry generator is a standard result under the usual locality, Lorentz-invariance, and vacuum assumptions."
  active:
    - "Goldstone counting is more subtle without Lorentz invariance, in finite volume, with gauge redundancy, with long-range forces, and in generalized-symmetry settings."
---

## Summary

This page works through the simplest Goldstone theorem example: an $O(2)$-symmetric scalar theory whose vacuum chooses a direction. The Lagrangian is

$$
\mathcal L
=
\frac12\partial_\mu\phi_1\partial^\mu\phi_1
+
\frac12\partial_\mu\phi_2\partial^\mu\phi_2
-
\frac{\lambda}{4}\left(\phi_1^2+\phi_2^2-v^2\right)^2,
$$

with $\lambda>0$ and $v>0$. The potential has a circle of minima,

$$
\phi_1^2+\phi_2^2=v^2.
$$

Choosing the vacuum

$$
\langle\phi_1\rangle=v,\qquad \langle\phi_2\rangle=0,
$$

and expanding

$$
\phi_1=v+h,\qquad \phi_2=\pi,
$$

gives

$$
m_h^2=2\lambda v^2,
\qquad
m_\pi^2=0.
$$

The field $h$ is the radial massive mode, while $\pi$ is the angular massless Goldstone mode.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Mexican-hat potential with a circle of vacua, a radial massive fluctuation h, and a tangential massless Goldstone fluctuation pi.](/figures/symmetry-anomalies-topology/goldstone-theorem-o2-model.svg)

<figcaption>

In the $O(2)$ model, the vacuum manifold is a circle. Radial fluctuations cost potential energy and become massive. Tangential fluctuations move along degenerate vacua and are massless at tree level. Goldstone’s theorem says the tangential masslessness is not an accident of tree-level perturbation theory.

</figcaption>
</figure>

The calculation shows the theorem in one line of physics:

$$
\text{broken continuous global symmetry}
\quad\Longrightarrow\quad
\text{flat direction}
\quad\Longrightarrow\quad
\text{massless mode}.
$$

The current matrix element makes the statement sharper:

$$
\langle 0|j^\mu(0)|\pi(p)\rangle
=
i v p^\mu
$$

up to normalization conventions. The broken current creates the massless particle.

## Prerequisites

You should know the scalar Noether-current calculation, spontaneous symmetry breaking at the level of a classical potential, and the distinction between a symmetry of the Lagrangian and a symmetry of a chosen vacuum.

The page uses mostly-minus metric and the convention that scalar mass terms appear in the Lagrangian as

$$
-\frac12m^2\varphi^2.
$$

## Setup and conventions

Let

$$
\vec\phi=
\begin{pmatrix}
\phi_1\\
\phi_2
\end{pmatrix}.
$$

The $O(2)$ transformation is

$$
\vec\phi\mapsto R(\alpha)\vec\phi,
$$

with

$$
R(\alpha)=
\begin{pmatrix}
\cos\alpha & -\sin\alpha\\
\sin\alpha & \cos\alpha
\end{pmatrix}.
$$

Infinitesimally,

$$
\delta\phi_1=-\alpha\phi_2,
\qquad
\delta\phi_2=\alpha\phi_1.
$$

The Noether current is

$$
j^\mu
=
\phi_1\partial^\mu\phi_2-\phi_2\partial^\mu\phi_1.
$$

The potential is

$$
V(\phi_1,\phi_2)=\frac{\lambda}{4}\left(\phi_1^2+\phi_2^2-v^2\right)^2.
$$

It is invariant because it depends only on the $O(2)$-invariant radius

$$
\phi_1^2+\phi_2^2.
$$

:::note[Convention-sensitive source note]
Some references use $V=\lambda(\phi^\dagger\phi-v^2/2)^2$ with a complex scalar $\phi=(\phi_1+i\phi_2)/\sqrt2$. This is the same physics with a different normalization of $v$ and $\lambda$.
:::

## Core idea

The potential has a continuous set of lowest-energy configurations. These minima are related by the symmetry:

$$
\mathcal M_{\rm vac}
=
\left\{
(\phi_1,\phi_2):\phi_1^2+\phi_2^2=v^2
\right\}
\simeq S^1.
$$

The Lagrangian is $O(2)$ invariant, but any single point on this circle is invariant only under the subgroup that leaves that point fixed. For $O(2)$ acting on the circle, the chosen vacuum breaks the continuous rotational part.

A small fluctuation perpendicular to the circle changes the value of the potential at quadratic order. A small fluctuation tangent to the circle only moves to a neighboring vacuum, so the potential has no quadratic restoring force in that direction. That is the classical shadow of Goldstone’s theorem.

The theorem says this massless mode persists in the full quantum theory under the usual assumptions: exact continuous global symmetry, locality, relativistic vacuum, and spontaneous breaking.

## Step 1: Find the vacuum manifold

The minima of $V$ satisfy

$$
\phi_1^2+\phi_2^2=v^2.
$$

Every point on this circle has zero potential energy. The origin is not a minimum; it has

$$
V(0,0)=\frac{\lambda v^4}{4}.
$$

Choose one vacuum,

$$
\phi_1=v,\qquad \phi_2=0.
$$

This is a choice, not a breaking of the Lagrangian. The Lagrangian still has the $O(2)$ symmetry. The chosen vacuum does not.

In finite volume, the exact ground state can be a symmetric superposition rather than one point on the circle. Spontaneous symmetry breaking is sharp in the infinite-volume limit, where distinct vacua become superselection sectors.

## Step 2: Expand around a chosen vacuum

Write

$$
\phi_1=v+h,\qquad \phi_2=\pi.
$$

Then

$$
\phi_1^2+\phi_2^2-v^2
=
(v+h)^2+\pi^2-v^2
=
2vh+h^2+\pi^2.
$$

The potential becomes

$$
V
=
\frac{\lambda}{4}
\left(2vh+h^2+\pi^2\right)^2.
$$

Keeping only quadratic terms,

$$
V_{\rm quad}
=
\lambda v^2 h^2.
$$

The quadratic Lagrangian is therefore

$$
\mathcal L_{\rm quad}
=
\frac12\partial_\mu h\partial^\mu h
+
\frac12\partial_\mu \pi\partial^\mu \pi
-
\lambda v^2 h^2.
$$

Comparing with

$$
\mathcal L_{\rm mass}
=
-\frac12m_h^2h^2-\frac12m_\pi^2\pi^2,
$$

we get

$$
m_h^2=2\lambda v^2,
\qquad
m_\pi^2=0.
$$

The field $h$ is massive. The field $\pi$ is massless.

## Step 3: Identify the Goldstone direction

The infinitesimal symmetry variation is

$$
\delta\phi_1=-\alpha\phi_2,
\qquad
\delta\phi_2=\alpha\phi_1.
$$

At the chosen vacuum,

$$
\delta\phi_1=0,
\qquad
\delta\phi_2=\alpha v.
$$

Thus the broken generator moves the vacuum in the $\phi_2$ direction. The fluctuation $\pi=\phi_2$ is precisely the Goldstone field.

Geometrically, $h$ is radial and $\pi$ is tangent to the vacuum circle at $(v,0)$.

A more invariant parametrization is

$$
\phi_1=(v+\rho)\cos\theta,
\qquad
\phi_2=(v+\rho)\sin\theta.
$$

The field $\theta$ is the angular coordinate on the vacuum manifold. At low energy, after the massive radial mode $\rho$ is integrated out, the leading effective Lagrangian is

$$
\mathcal L_{\rm eff}
=
\frac{v^2}{2}\partial_\mu\theta\,\partial^\mu\theta+\cdots.
$$

Only derivatives appear. A non-derivative potential for $\theta$ would choose preferred points on the vacuum circle and explicitly break the symmetry.

## Step 4: Current matrix element

The Noether current is

$$
j^\mu
=
\phi_1\partial^\mu\phi_2-\phi_2\partial^\mu\phi_1.
$$

Substitute

$$
\phi_1=v+h,\qquad \phi_2=\pi.
$$

Then

$$
j^\mu
=
(v+h)\partial^\mu\pi-\pi\partial^\mu h.
$$

To leading order in fields,

$$
j^\mu=v\,\partial^\mu\pi+\cdots.
$$

For a one-particle Goldstone state $|\pi(p)\rangle$, the free-field matrix element has the form

$$
\langle 0|\partial^\mu\pi(0)|\pi(p)\rangle
=
i p^\mu
$$

with the usual relativistic normalization convention. Therefore

$$
\langle 0|j^\mu(0)|\pi(p)\rangle
=
ivp^\mu.
$$

This is the current-algebra signature of a Goldstone boson. The broken current has nonzero overlap with a one-particle massless state.

:::note[Physical meaning]
The vacuum expectation value $v$ plays the role of the decay constant in this simple model. In more general theories one writes $\langle0|j_a^\mu(0)|\pi_b(p)\rangle=iF_{ab}p^\mu$.
:::

## Step 5: The theorem behind the example

The example suggests a general statement. Suppose $Q_a$ is a conserved charge of a continuous global symmetry and the vacuum is not invariant:

$$
Q_a|0\rangle\neq0
$$

in the infinite-volume sense. Equivalently, there is an operator $\mathcal O$ such that

$$
\langle0|[Q_a,\mathcal O]|0\rangle\neq0.
$$

Using

$$
Q_a=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x),
$$

locality and spectral decomposition imply that the current correlator must contain a massless pole. In Lorentz-invariant theories this pole is interpreted as a massless scalar particle: the Goldstone boson.

In the $O(2)$ model, the operator can be $\phi_2$ or $\phi_1$ depending on the chosen direction, and the massless field is $\pi$.

## Step 6: Explicit breaking gives a pseudo-Goldstone boson

Add a small symmetry-breaking term

$$
\Delta V=-\epsilon\,\phi_1.
$$

The vacuum is now biased toward positive $\phi_1$. In angular variables,

$$
\Delta V\approx-\epsilon v\cos\theta.
$$

Expanding near $\theta=0$,

$$
\Delta V
\approx
-\epsilon v+\frac{\epsilon v}{2}\theta^2+\cdots.
$$

Since $\pi\approx v\theta$, this gives

$$
\Delta V
\approx
-\epsilon v+\frac{\epsilon}{2v}\pi^2+\cdots.
$$

Thus

$$
m_\pi^2\approx \frac{\epsilon}{v}.
$$

A small explicit breaking turns the Goldstone boson into a light pseudo-Goldstone boson. This is the logic behind pions in chiral symmetry breaking: they are light because the symmetry is approximate, not exact.

## Step 7: Gauge symmetry changes the conclusion

If the broken symmetry is gauged, the massless Goldstone mode is not a physical particle in the same way. Instead, it is eaten by the gauge field, giving the gauge field a mass. This is the Higgs mechanism.

In the Abelian Higgs model, write

$$
\phi(x)=\frac{1}{\sqrt2}(v+h(x))e^{i\theta(x)}.
$$

The covariant derivative contains

$$
|D_\mu\phi|^2
\supset
\frac{v^2}{2}(\partial_\mu\theta+qA_\mu)^2.
$$

A gauge transformation can remove $\theta$ locally, leaving a massive vector field with

$$
m_A^2=q^2v^2.
$$

Goldstone’s theorem applies to broken global symmetries, not to gauge redundancies.

## Common pitfalls

**Saying the symmetry is broken by the Lagrangian.** The Lagrangian is symmetric. A particular vacuum is not.

**Forgetting the infinite-volume limit.** In finite volume, tunneling or quantum averaging can restore a unique symmetric ground state. Spontaneous breaking becomes sharp when the volume is taken to infinity before external symmetry-breaking fields are removed.

**Calling the radial mode the Goldstone boson.** The Goldstone mode is tangent to the vacuum manifold. The radial mode is massive.

**Ignoring explicit breaking.** A small symmetry-breaking term gives the would-be Goldstone boson a small mass. It is then a pseudo-Goldstone boson.

**Applying the theorem unchanged to gauge symmetry.** Gauge symmetry is redundancy. In the Higgs mechanism, the would-be Goldstone mode becomes the longitudinal polarization of a massive gauge boson.

**Forgetting low-dimensional caveats.** In sufficiently low dimensions, infrared fluctuations can prevent spontaneous breaking of continuous internal symmetries under the assumptions of the Coleman–Mermin–Wagner theorem.

## Relations to other pages

[Noether Current for a Scalar Field](/symmetry-anomalies-topology/model-calculation-library/noether-current-for-scalar-field/) gives the current calculation used here. The Spontaneous Symmetry Breaking chapter develops vacuum manifolds, order parameters, degenerate vacua, Goldstone modes, and pseudo-Goldstone bosons systematically.

The Gauge Redundancy and BRST chapter explains why the Higgs mechanism is not ordinary breaking of a physical gauge symmetry. The Low-Dimensional Symmetry Technology and CFT chapters explain the two-dimensional caveats and current-algebra refinements.

## Research status

The relativistic Goldstone theorem is established textbook physics. Its standard form assumes locality, a continuous global symmetry, a Lorentz-invariant vacuum, and spontaneous breaking.

There are important refinements outside this textbook setting. Nonrelativistic systems can have fewer Goldstone modes than broken generators. Gauge theories realize the Higgs mechanism. Low-dimensional systems can evade long-range order. Generalized symmetries have their own symmetry-breaking diagnostics, where area and perimeter laws replace ordinary local order parameters.

## Exercises

### Exercise 1: Quadratic expansion

Starting from

$$
V=\frac{\lambda}{4}\left(\phi_1^2+\phi_2^2-v^2\right)^2
$$

and

$$
\phi_1=v+h,\qquad \phi_2=\pi,
$$

show that $m_h^2=2\lambda v^2$ and $m_\pi^2=0$.

<details><summary><strong>Solution</strong></summary>

Substitute the expansion:

$$
\phi_1^2+\phi_2^2-v^2
=
2vh+h^2+\pi^2.
$$

Thus

$$
V=\frac{\lambda}{4}(2vh+h^2+\pi^2)^2.
$$

The only quadratic term is

$$
V_{\rm quad}=\lambda v^2h^2.
$$

Since the Lagrangian contains $-V$, compare with

$$
-\frac12m_h^2h^2-\frac12m_\pi^2\pi^2.
$$

Therefore

$$
m_h^2=2\lambda v^2,\qquad m_\pi^2=0.
$$

</details>

### Exercise 2: Current expansion

Using

$$
j^\mu=\phi_1\partial^\mu\phi_2-\phi_2\partial^\mu\phi_1,
$$

show that

$$
j^\mu=v\partial^\mu\pi+\cdots
$$

after expanding around $\phi_1=v+h$, $\phi_2=\pi$.

<details><summary><strong>Solution</strong></summary>

Substitute the shifted fields:

$$
j^\mu=(v+h)\partial^\mu\pi-\pi\partial^\mu h.
$$

The term linear in fields is

$$
v\partial^\mu\pi.
$$

The terms $h\partial^\mu\pi$ and $\pi\partial^\mu h$ are quadratic and are included in the ellipsis.

</details>

### Exercise 3: Vacuum manifold

For an $O(N)$ model with

$$
V=\frac{\lambda}{4}(\phi_i\phi_i-v^2)^2,
$$

what is the vacuum manifold? How many Goldstone bosons appear when $O(N)$ breaks to $O(N-1)$?

<details><summary><strong>Solution</strong></summary>

The minima obey

$$
\phi_i\phi_i=v^2,
$$

so the vacuum manifold is

$$
S^{N-1}.
$$

The dimension of $O(N)$ is $N(N-1)/2$, and the dimension of $O(N-1)$ is $(N-1)(N-2)/2$. The difference is

$$
\frac{N(N-1)}2-\frac{(N-1)(N-2)}2=N-1.
$$

So there are $N-1$ Goldstone bosons in a Lorentz-invariant theory.

</details>

### Exercise 4: Pseudo-Goldstone mass

Add $\Delta V=-\epsilon\phi_1$ and use $\phi_1\approx v\cos(\pi/v)$ near the vacuum. Show that $m_\pi^2\approx\epsilon/v$.

<details><summary><strong>Solution</strong></summary>

For small $\pi/v$,

$$
\phi_1\approx v\cos(\pi/v)
\approx v\left(1-\frac{\pi^2}{2v^2}\right).
$$

Then

$$
\Delta V
=
-\epsilon\phi_1
\approx
-\epsilon v+\frac{\epsilon}{2v}\pi^2.
$$

Comparing with $\frac12m_\pi^2\pi^2$ in the potential gives

$$
m_\pi^2=\frac{\epsilon}{v}.
$$

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §§30–32, for spontaneous symmetry breaking and continuous-symmetry Goldstone modes.
- Sidney Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for the classic lecture treatment of spontaneous symmetry breaking, Goldstone bosons, and the Higgs phenomenon.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 6, for internal symmetries and conservation laws.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, §28.2, for spontaneous breaking of continuous global symmetries.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, ch. 5, for broken symmetry and collective phenomena in matter systems.

## Version history

- **2026-06-23:** Initial polished draft. Derived the $O(2)$ Goldstone mode, current matrix element, pseudo-Goldstone mass from explicit breaking, and Higgs-mechanism caveat.
