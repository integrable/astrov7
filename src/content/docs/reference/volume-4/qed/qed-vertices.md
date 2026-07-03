---
title: "QED Vertices"
description: "Collects the tree-level QED interaction vertices for spinor and scalar charged matter in the volume conventions, including the scalar seagull vertex and elementary Ward checks."
sidebar:
  label: "QED Vertices"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki §§58, 61, 67–68; Schwartz Chs. 8–14; Coleman lectures on electromagnetic interactions and QED; Zee QED chapters."
topics:
  - QED vertices
  - Feynman rules
  - scalar QED
  - spinor QED
  - Ward identities
canonicalTopics:
  - qed-vertices
  - spinor-qed-vertex
  - scalar-qed-vertex
  - seagull-vertex
researchStatus:
  established:
    - "The tree-level QED vertices follow directly from minimal coupling and are standard textbook Feynman rules once charge and Fourier conventions are fixed."
  active:
    - "Higher-order, infrared-safe, and effective-field-theory extensions of these vertices are active calculation technology, but the local tree-level rules on this page are settled."
---

## Summary

QED vertices are the interaction factors obtained by expanding the gauge-invariant QED Lagrangian and translating each local interaction into a momentum-space Feynman rule. In this volume the Abelian convention is

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\Phi\mapsto e^{-iq\lambda}\Phi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\lambda,
$$

where $q$ is the physical electric charge of the field. With plane waves $e^{-ip\cdot x}$, the most important tree-level vertices are:

| Interaction | Vertex factor | Comment |
|---|---:|---|
| spinor–spinor–photon | $-iq\gamma^\mu$ | For the electron $q=-e$, so the factor is $+ie\gamma^\mu$. |
| scalar–scalar–photon | $iq(p'-p)^\mu$ | All momenta incoming: $\phi(p)\phi^\dagger(p')A_\mu(k)$ and $p+p'+k=0$. |
| scalar–scalar–two-photon | $2iq^2\eta^{\mu\nu}$ | The scalar-QED seagull vertex, required by gauge invariance. |

Equivalently, when a charged scalar with momentum $p$ enters a vertex and leaves with momentum $p'$ after absorbing a photon, the one-photon scalar vertex is commonly written

$$
-iq(p+p')^\mu.
$$

These rules are not independent decorations attached to a Lagrangian. They are different shadows of the same covariant derivative. The spinor vertex comes from the first-order Dirac kinetic term; the scalar one-photon and two-photon vertices come together from the second-order scalar kinetic term.

<figure class="doc-figure" style="--figure-width: 49rem;">

![The tree-level QED vertices for spinor matter, scalar matter, and the scalar seagull contact interaction.](/figures/gauge-theories-standard-model/qed-vertex-rules.svg)

<figcaption>

Tree-level QED interaction vertices in the convention $D_\mu=\partial_\mu+iqA_\mu$. Spinor QED has one elementary photon–matter vertex. Scalar QED has both a one-photon derivative vertex and a two-photon seagull vertex; the pair is required by local $U(1)$ gauge invariance.

</figcaption>
</figure>

## Prerequisites

You should know [Scalar QED](/gauge-theories-standard-model/qed/scalar-qed/), [Spinor QED](/gauge-theories-standard-model/qed/spinor-qed/), the [QED Lagrangian](/gauge-theories-standard-model/qed/qed-lagrangian/), and the [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/). This page uses the mostly-minus metric, the Fourier convention $e^{-ip\cdot x}$, and the free propagators

$$
S_F(p)=\frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon},
\qquad
\Delta_F(p)=\frac{i}{p^2-m^2+i\epsilon},
$$

for Dirac and scalar matter. In covariant gauge, the photon propagator is

$$
D_{\mu\nu}^{(\xi)}(k)
=
\frac{-i}{k^2+i\epsilon}
\left[
\eta_{\mu\nu}-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}
\right].
$$

The next page, [Ward–Takahashi Identity](/gauge-theories-standard-model/qed/ward-takahashi-identity/), explains why the vertex rules are constrained far beyond tree level.

## Core idea

There is a quick way to get QED vertices, and a safe way.

The quick way is to expand the interaction Lagrangian and attach a factor of $i$ to each coefficient in momentum space. This is how most computations are done.

The safe way is to remember where the interactions came from:

$$
\partial_\mu\longrightarrow D_\mu=\partial_\mu+iqA_\mu.
$$

That replacement does more than introduce a photon line. It ties the one-photon vertex to the charge generator, fixes the scalar seagull interaction, and makes the Ward identities possible. If a proposed vertex rule cannot be traced back to a gauge-covariant expression, you should distrust it until proven otherwise.

The cleanest practical rule is therefore:

$$
\text{derive vertices from }\mathcal L(D),\text{ not from memory.}
$$

Memory is where seagull vertices go to die.

## Setup and conventions

We use the interaction factor convention appropriate to perturbation theory with

$$
Z[J]=\int\mathcal D\Phi\,\exp\left(i\int d^4x\,\mathcal L+\cdots\right).
$$

A local interaction term contributes $i$ times its momentum-space coefficient, including the combinatorial factors from differentiating identical fields. All momenta are taken to be incoming unless a section explicitly states a particle-flow convention.

For a field of charge $q=eQ$, with $e>0$, the dimensionless charge is $Q$. Thus

$$
Q_e=-1,
\qquad
q_e=-e,
$$

and the electron vertex in this convention is $+ie\gamma^\mu$. If you are used to seeing $-ie\gamma^\mu$ for the electron, you are probably using either the opposite covariant-derivative convention or a convention in which the symbol $e$ denotes the electron's charge rather than the positive proton-charge magnitude. Both conventions are fine; mixing them is not.

We will use two momentum assignments:

| Assignment | Meaning | Typical use |
|---|---|---|
| all momenta incoming | Every momentum variable flows into the vertex. | Compact Feynman-rule tables and functional derivations. |
| particle flow | An incoming matter particle with momentum $p$ leaves with momentum $p'$ after photon absorption. | Quick tree-amplitude checks and Ward identities. |

The two descriptions are the same rule written with different bookkeeping.

## What counts as a vertex

A vertex is a local interaction factor in the perturbative expansion. In QED, the minimal vertices come from the matter kinetic terms. The photon kinetic term

$$
-\frac14F_{\mu\nu}F^{\mu\nu}
$$

is quadratic in the Abelian gauge field, so it gives the photon propagator but no photon self-interaction. This is the first big contrast with non-Abelian Yang–Mills theory: in QED there is no elementary three-photon or four-photon vertex in the minimal Lagrangian.

There are still effective photon self-interactions at low energy after charged matter is integrated out. For example, the Euler–Heisenberg effective Lagrangian contains operators schematically of the form

$$
\frac{1}{m_e^4}(F_{\mu\nu}F^{\mu\nu})^2,
\qquad
\frac{1}{m_e^4}(F_{\mu\nu}\widetilde F^{\mu\nu})^2.
$$

Those are not elementary vertices of minimal QED. They are loop-induced effective vertices valid below the electron mass scale.

## Spinor QED vertex

For a Dirac field of charge $q$, the spinor-QED matter Lagrangian is

$$
\mathcal L_\psi
=
\bar\psi(i\gamma^\mu D_\mu-m)\psi.
$$

Expanding the covariant derivative gives

$$
\mathcal L_\psi
=
\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-qA_\mu\bar\psi\gamma^\mu\psi.
$$

The interaction term is

$$
\mathcal L_{\psi\psi A}
=-qA_\mu\bar\psi\gamma^\mu\psi.
$$

Therefore the photon–fermion vertex factor is

$$
\psi\,\bar\psi\,A_\mu:
\qquad
-iq\gamma^\mu.
$$

In a particle-flow convention, the tree-level matrix element for a photon coupling to a charged Dirac line contains

$$
\bar u(p')(-iq\gamma^\mu)u(p)\,\epsilon_\mu(k),
\qquad
p'=p+k,
$$

for photon absorption by a fermion. For an electron, $q=-e$, so this becomes

$$
\bar u(p')\,ie\gamma^\mu\,u(p)\,\epsilon_\mu(k).
$$

The vertex conserves the electric charge carried by the fermion line. A photon can transfer momentum, but it does not change the value of $q$.

## Spinor vertex Ward check

The spinor vertex satisfies a useful single-line identity. With $p'=p+k$,

$$
k_\mu\gamma^\mu
=
k\!\!\!/
=
(p'\!\!\!/-m)-(p\!\!\!/-m).
$$

More plainly, since $p'=p+k$,

$$
k\!\!\!/
=
(p'\!\!\!/-m)-(p\!\!\!/-m).
$$

Multiplying by the vertex factor gives

$$
k_\mu(-iq\gamma^\mu)
=
-iq\left[(p'\!\!\!/-m)-(p\!\!\!/-m)\right].
$$

Between on-shell external spinors, this vanishes:

$$
\bar u(p')k\!\!\!/u(p)
=
\bar u(p')(p'\!\!\!/-m)u(p)-\bar u(p')(p\!\!\!/-m)u(p)=0.
$$

Inside a larger diagram, the inverse Dirac operators cancel adjacent fermion propagators. That cancellation is the diagrammatic seed of the Ward–Takahashi identity.

## Scalar one-photon vertex

For a complex scalar field of charge $q$,

$$
\mathcal L_\phi
=(D_\mu\phi)^\dagger D^\mu\phi-m^2\phi^\dagger\phi.
$$

Using

$$
D_\mu\phi=\partial_\mu\phi+iqA_\mu\phi,
\qquad
(D_\mu\phi)^\dagger=\partial_\mu\phi^\dagger-iqA_\mu\phi^\dagger,
$$

the terms linear in $A_\mu$ are

$$
\mathcal L_{\phi\phi A}
=
-iqA_\mu\phi^\dagger\partial^\mu\phi
+iqA_\mu(\partial^\mu\phi^\dagger)\phi.
$$

Equivalently,

$$
\mathcal L_{\phi\phi A}=-j_0^\mu A_\mu,
\qquad
j_0^\mu
=iq\left(\phi^\dagger\partial^\mu\phi-(\partial^\mu\phi^\dagger)\phi\right).
$$

With all momenta incoming, the vertex is

$$
\phi(p)\,\phi^\dagger(p')\,A_\mu(k):
\qquad
iq(p'-p)^\mu,
\qquad
p+p'+k=0.
$$

In a particle-flow convention, if a scalar with momentum $p$ enters and a scalar with momentum $p'$ leaves after absorbing a photon, the same rule is

$$
V^\mu(p',p)=-iq(p+p')^\mu.
$$

The appearance of momenta is not optional. Scalar QED couples the photon to the scalar current, and the scalar current contains derivatives.

## Scalar seagull vertex

The scalar kinetic term also contains the quadratic photon interaction

$$
\mathcal L_{\phi\phi AA}
=q^2A_\mu A^\mu\phi^\dagger\phi.
$$

Differentiating with respect to two identical photon fields gives the seagull vertex

$$
\phi\,\phi^\dagger\,A_\mu A_\nu:
\qquad
2iq^2\eta^{\mu\nu}.
$$

This vertex has no spinor-QED analogue because the Dirac kinetic term is first order in derivatives. In scalar QED, the seagull vertex is required by gauge invariance. For example, scalar Compton scattering receives contributions from two pole diagrams and one contact diagram. The pole diagrams alone do not satisfy the Ward identity; the contact diagram repairs the result.

The seagull interaction also contributes to loop calculations. In scalar vacuum polarization, both the scalar loop with two one-photon vertices and the seagull loop are needed to obtain a transverse photon self-energy.

## Scalar vertex Ward check

For the particle-flow scalar vertex

$$
V^\mu(p',p)=-iq(p+p')^\mu,
\qquad
k=p'-p,
$$

we get

$$
k_\mu V^\mu(p',p)
=-iq(p'-p)\cdot(p'+p)
=-iq(p'^2-p^2).
$$

Writing the inverse free scalar operator as $p^2-m^2$, this becomes

$$
k_\mu V^\mu(p',p)
=-iq\left[(p'^2-m^2)-(p^2-m^2)\right].
$$

This is the scalar analogue of the spinor check. On external on-shell scalar legs, it vanishes. Inside a diagram, the inverse scalar operators cancel neighboring scalar propagators, leaving terms that cancel against other diagrams. When two photons attach to a scalar line, the seagull term is part of that cancellation.

## Propagators used with the vertices

A minimal tree-level QED calculation usually combines the vertices above with these propagators.

| Field | Propagator |
|---|---:|
| Dirac fermion | $\displaystyle S_F(p)=\frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon}$ |
| complex scalar | $\displaystyle \Delta_F(p)=\frac{i}{p^2-m^2+i\epsilon}$ |
| photon in Feynman gauge | $\displaystyle D_{\mu\nu}(k)=\frac{-i\eta_{\mu\nu}}{k^2+i\epsilon}$ |
| photon in covariant gauge | $\displaystyle D_{\mu\nu}^{(\xi)}(k)=\frac{-i}{k^2+i\epsilon}\left[\eta_{\mu\nu}-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}\right]$ |

The photon propagator is gauge dependent. Vertex identities ensure that the gauge-dependent longitudinal terms cancel from physical amplitudes when all diagrams required by gauge invariance are included.

## How to use the rules

A typical QED amplitude calculation follows this workflow.

1. Choose the charged fields and their charges $q_i$.
2. Write every momentum as incoming to each vertex, or choose a particle-flow convention and stick to it.
3. Attach the appropriate spinor or scalar QED vertex to each photon–matter interaction.
4. Include the scalar seagull vertex whenever scalar QED has two photons attached at one point.
5. Use a covariant-gauge photon propagator for internal photon lines.
6. Sum all diagrams at the same order required by the Lagrangian.
7. Check at least one photon leg by replacing $\epsilon_\mu(k)$ with $k_\mu$.

The last step is not just a classroom trick. It is a fast diagnostic for missing diagrams, wrong signs, or inconsistent charge conventions.

## Counterterm and effective vertices

The table in the summary contains tree-level minimal-QED vertices. Renormalized perturbation theory adds counterterm vertices. For spinor QED one commonly writes, schematically,

$$
\mathcal L_{\mathrm{ct}}
=
-\frac14\delta Z_3 F_{\mu\nu}F^{\mu\nu}
+\delta Z_2\bar\psi i\gamma^\mu\partial_\mu\psi
-\delta m\,\bar\psi\psi
-\delta Z_1 qA_\mu\bar\psi\gamma^\mu\psi.
$$

The Ward–Takahashi identity implies $Z_1=Z_2$ in spinor QED, in standard gauge-invariant schemes and notation. This is a deep statement about renormalization: the charge vertex and fermion wavefunction counterterms are not independent.

Effective-field-theory corrections add higher-dimension vertices. Examples include magnetic dipole terms,

$$
\frac{c_M}{\Lambda}\bar\psi\sigma^{\mu\nu}\psi F_{\mu\nu},
$$

or scalar polarizability terms,

$$
\frac{c}{\Lambda^2}\phi^\dagger\phi F_{\mu\nu}F^{\mu\nu}.
$$

Such terms are gauge invariant but not part of minimal renormalizable QED. They are organized by the Effective Field Theory pages rather than by this basic vertex page.

## Common pitfalls

**Using the wrong sign for the charge convention.** In this volume, a field of charge $q$ has vertex $-iq\gamma^\mu$. The electron has $q=-e$, so the electron vertex is $+ie\gamma^\mu$. If your favorite book uses $-ie\gamma^\mu$ for the electron, translate the convention before comparing formulas.

**Forgetting that scalar QED has two photon vertices.** The one-photon scalar vertex and two-photon seagull vertex come from the same kinetic term. Dropping the seagull almost always breaks Ward identities.

**Treating all momenta as outgoing on one line and incoming on the next.** Momentum-flow conventions are harmless only if used consistently. The scalar vertex is especially good at punishing sloppy signs.

**Expecting an elementary photon self-interaction in QED.** Minimal Abelian QED has no tree-level three-photon or four-photon vertex. Photon self-interactions arise through charged loops or higher-dimension effective operators.

**Checking one diagram instead of the full gauge-invariant set.** Ward identities constrain complete amplitudes, not arbitrary fragments. Individual diagrams often fail the check until the required partner diagrams are included.

## Relations to other pages

- [Scalar QED](/gauge-theories-standard-model/qed/scalar-qed/) derives the scalar current and seagull term from the covariant derivative.
- [Spinor QED](/gauge-theories-standard-model/qed/spinor-qed/) fixes the Dirac current and the sign of the fermion–photon vertex.
- [QED Lagrangian](/gauge-theories-standard-model/qed/qed-lagrangian/) collects the gauge-invariant and gauge-fixed forms from which the rules are derived.
- [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/) supplies the internal photon line used with these vertices.
- [Ward–Takahashi Identity](/gauge-theories-standard-model/qed/ward-takahashi-identity/) explains why the vertices and propagators obey exact gauge-invariance constraints.
- Vacuum Polarization uses the scalar and spinor vertices to compute the first quantum correction to the photon propagator.

## Research status

The minimal QED vertices are established textbook material. Their signs are convention-dependent, but the convention dependence is completely mechanical. The nontrivial modern work lies in higher-order amplitudes, infrared-safe observables, precision calculations, effective operators, background-field methods, and automated symbolic implementations.

The tree rules are simple. The errors they prevent are not.

## Exercises

### Exercise 1: Derive the spinor vertex

Starting from

$$
\mathcal L_{\mathrm{int}}=-qA_\mu\bar\psi\gamma^\mu\psi,
$$

show that the photon–fermion vertex factor is $-iq\gamma^\mu$.

<details>
<summary><strong>Solution</strong></summary>

In perturbation theory the interaction appears through

$$
\exp\left(i\int d^4x\,\mathcal L_{\mathrm{int}}\right).
$$

The coefficient of the local product $A_\mu\bar\psi\psi$ in $\mathcal L_{\mathrm{int}}$ is $-q\gamma^\mu$. Multiplying by the overall factor of $i$ gives

$$
-iq\gamma^\mu.
$$

For an electron, $q=-e$, so this is $+ie\gamma^\mu$ in the conventions of this volume.

</details>

### Exercise 2: Derive the scalar one-photon vertex

Use

$$
\mathcal L_{\phi\phi A}
=
-iqA_\mu\phi^\dagger\partial^\mu\phi
+iqA_\mu(\partial^\mu\phi^\dagger)\phi
$$

and plane waves $e^{-ip\cdot x}$ to derive the all-incoming scalar vertex

$$
\phi(p)\phi^\dagger(p')A_\mu(k):
\qquad
iq(p'-p)^\mu.
$$

<details>
<summary><strong>Solution</strong></summary>

The derivative acting on $\phi(p)$ gives $-ip^\mu$, while the derivative acting on $\phi^\dagger(p')$ gives $-ip'^\mu$. The coefficient in the Lagrangian is therefore

$$
(-iq)(-ip^\mu)+(iq)(-ip'^\mu)
=-q p^\mu+q p'^\mu
=q(p'-p)^\mu.
$$

The vertex factor is $i$ times this coefficient, hence

$$
iq(p'-p)^\mu.
$$

</details>

### Exercise 3: Check the spinor single-vertex Ward identity

Show that for $p'=p+k$,

$$
k_\mu\bar u(p')\gamma^\mu u(p)=0
$$

when both external spinors are on shell.

<details>
<summary><strong>Solution</strong></summary>

Since $k=p'-p$,

$$
k_\mu\gamma^\mu=p'\!\!\!/-p\!\!\!/.
$$

Insert and subtract $m$:

$$
p'\!\!\!/-p\!\!\!/
=(p'\!\!\!/-m)-(p\!\!\!/-m).
$$

Then

$$
\bar u(p')k\!\!\!/u(p)
=
\bar u(p')(p'\!\!\!/-m)u(p)
-
\bar u(p')(p\!\!\!/-m)u(p).
$$

The first term vanishes because $\bar u(p')(p'\!\!\!/-m)=0$, and the second vanishes because $(p\!\!\!/-m)u(p)=0$.

</details>

### Exercise 4: Why the scalar seagull has a factor of two

Starting from

$$
\mathcal L_{\phi\phi AA}=q^2A_\mu A^\mu\phi^\dagger\phi,
$$

explain why the two-photon vertex is $2iq^2\eta^{\mu\nu}$ rather than $iq^2\eta^{\mu\nu}$.

<details>
<summary><strong>Solution</strong></summary>

Write $A_\mu A^\mu=\eta^{\rho\sigma}A_\rho A_\sigma$. Differentiating the interaction twice with respect to photon fields gives two identical contributions:

$$
\frac{\delta^2}{\delta A_\mu\delta A_\nu}
\left(\eta^{\rho\sigma}A_\rho A_\sigma\right)
=2\eta^{\mu\nu}.
$$

Multiplying by the coefficient $q^2$ and by the perturbative factor $i$ gives

$$
2iq^2\eta^{\mu\nu}.
$$

</details>

## References

- Srednicki, *Quantum Field Theory*, §§58 and 61 for spinor and scalar electrodynamics, and §§67–68 for Ward identities.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 8–14 for gauge invariance, scalar QED, spinor QED, Feynman rules, and the Ward–Takahashi identity.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on electromagnetic interactions, Faddeev–Popov, Ward identities, and QED renormalization.
- Zee, *Quantum Field Theory in a Nutshell*, QED and gauge-invariance chapters, especially for diagrammatic Ward-identity intuition.
- Weinberg, *The Quantum Theory of Fields*, Vol. I, for a systematic treatment of QED amplitudes, renormalization, and infrared structure.

## Version history

- **2026-06-17:** Initial polished draft. Fixes QED tree-level vertex rules in the improved volume conventions and prepares the transition to the Ward–Takahashi identity.
