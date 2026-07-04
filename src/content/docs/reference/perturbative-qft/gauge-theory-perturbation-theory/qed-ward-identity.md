---
title: "QED Ward Identity"
description: "How Abelian gauge invariance becomes the Ward–Takahashi identity, why longitudinal photons decouple, and why QED has Z₁ = Z₂."
sidebar:
  label: "QED Ward Identity"
  order: 3
level: Graduate
status: "Polished draft"
source: "Ward 1950; Takahashi 1957; Srednicki §§58, 62, 67–68; Schwartz chs. 14 and 19; Coleman ch. 33; Weinberg Vol. I ch. 8"
topics:
  - QED
  - Ward identity
  - Ward–Takahashi identity
  - gauge invariance
  - renormalization
canonicalTopics:
  - qed-ward-identity
  - ward-takahashi-identity
  - longitudinal-photon-decoupling
  - z1-equals-z2
researchStatus:
  established:
    - "The QED Ward–Takahashi identity is an exact consequence of Abelian gauge invariance when the regulator and renormalization scheme preserve the symmetry."
  active:
    - "The non-Abelian generalization is organized by Slavnov–Taylor identities and BRST symmetry; global gauge-fixing and nonperturbative issues belong to later pages."
---

## Summary

The QED Ward identity is the perturbative face of Abelian gauge invariance. It says that a photon whose polarization is purely longitudinal does not create a physical effect, and it gives precise algebraic identities among Green functions and amplitudes.

For the exact fermion propagator

$$
S(p)=\frac{i}{\mathcal S^{-1}(p)+i\epsilon},
\qquad
\mathcal S^{-1}(p)=p\!\!\!/-m-\Sigma(p),
$$

and the exact amputated current vertex $\Gamma^\mu(p+k,p)$ normalized so that $\Gamma^\mu_{\rm tree}=\gamma^\mu$, the Ward–Takahashi identity is

$$
k_\mu\Gamma^\mu(p+k,p)
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p).
$$

The practical scattering version is even shorter:

$$
{k_\mu\mathcal M^\mu=0,}
$$

where $\mathcal M^\mu\epsilon_\mu(k)$ is an amplitude with one external photon. Replacing an external polarization vector by the photon momentum gives zero. This is why unphysical photon polarizations decouple from properly summed QED amplitudes.

The same identity also explains the famous QED renormalization relation

$$
{Z_1=Z_2,}
$$

where $Z_1$ renormalizes the fermion–photon vertex and $Z_2$ renormalizes the fermion field. In QED, charge renormalization is therefore tied to the photon field renormalization rather than to an independent vertex renormalization.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![The QED Ward identity relates a longitudinal current insertion to inverse propagators on adjacent fermion lines](/figures/perturbative-qft/qed-ward-identity.svg)

<figcaption>

The Ward–Takahashi identity says that contracting a current insertion with its momentum turns the insertion into the difference of inverse fermion propagators on the two sides. On external on-shell legs those inverse propagators vanish, giving the scattering rule $k_\mu\mathcal M^\mu=0$.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/), [Gauge Fixing for Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/gauge-fixing-for-perturbation-theory/), [Wavefunction Renormalization](/perturbative-qft/renormalized-perturbation-theory/wavefunction-renormalization/), and [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/). From Foundations, review [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/) and [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/).

## Core idea

Gauge redundancy means that the replacement

$$
\epsilon_\mu(k)\mapsto \epsilon_\mu(k)+\alpha k_\mu
$$

cannot change a physical amplitude. Therefore the coefficient of the unphysical piece $k_\mu$ must vanish:

$$
k_\mu\mathcal M^\mu=0.
$$

That statement is not a coincidence of tree diagrams. It is the on-shell shadow of an off-shell identity among Green functions. A current insertion carrying momentum $k$ into a fermion line obeys

$$
k_\mu\Gamma^\mu(p+k,p)
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p).
$$

This is the cleanest way to understand why QED is easier than a generic vector theory. Longitudinal photons couple to differences of inverse propagators. If the adjacent fermion lines are external physical particles, the inverse propagators kill the spinors. If the adjacent fermion lines are internal, the inverse propagators cancel neighboring propagators and produce telescoping cancellations across diagrams.

The slogan is simple: a longitudinal photon insertion is the inverse propagator on the right minus the inverse propagator on the left. That little subtraction is the algebraic engine behind many QED gauge cancellations.

## Setup and conventions

We use the qft.org mostly-minus metric and the QED covariant derivative

$$
D_\mu=\partial_\mu+iQ A_\mu.
$$

For a Dirac field of charge $Q$,

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\overline\psi(i\gamma^\mu D_\mu-m)\psi.
$$

Expanding the covariant derivative gives

$$
\mathcal L_{\rm int}
=-Q\overline\psi\gamma^\mu A_\mu\psi,
$$

so the photon–fermion vertex is

$$
{-iQ\gamma^\mu.}
$$

For the electron, $Q=-e$ with $e>0$, so the electron–photon vertex is $+ie\gamma^\mu$ in this convention.

To state the Ward–Takahashi identity without burying it under charge signs, define $\Gamma^\mu$ as the amputated vertex for the unit-normalized current insertion

$$
J^\mu=\overline\psi\gamma^\mu\psi.
$$

Then

$$
\Gamma^\mu_{\rm tree}=\gamma^\mu.
$$

The physical photon vertex for a charge-$Q$ field is obtained by multiplying by $-iQ$.

The exact fermion propagator is written as

$$
S(p)=\frac{i}{\mathcal S^{-1}(p)+i\epsilon},
\qquad
\mathcal S^{-1}(p)=p\!\!\!/-m-\Sigma(p),
$$

where $\Sigma(p)$ is the fermion self-energy. The placement of the factor of $i$ in $S(p)$ is conventional; the Ward identity below uses $\mathcal S^{-1}$ as the denominator operator.

## The Ward–Takahashi identity

Let $G^\mu(p+k,p)$ be the unamputated momentum-space three-point function with one current insertion and two fermion legs. With our momentum routing,

$$
G^\mu(p+k,p)=S(p+k)\Gamma^\mu(p+k,p)S(p).
$$

The Ward–Takahashi identity for the unamputated Green function is

$$
k_\mu G^\mu(p+k,p)
=
iS(p)-iS(p+k),
$$

up to the same overall Fourier and current-normalization convention on both sides. Multiplying by inverse propagators on the left and right gives the amputated form

$$
k_\mu\Gamma^\mu(p+k,p)
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p).
$$

At tree level,

$$
\Gamma^\mu_{\rm tree}=\gamma^\mu,
\qquad
\mathcal S^{-1}_{\rm tree}(p)=p\!\!\!/-m,
$$

so the identity reduces to the elementary Clifford-algebra statement

$$
k_\mu\gamma^\mu
=(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m).
$$

The full identity says that loop corrections preserve the same structure once they are regularized and renormalized in a gauge-invariant way.

## Position-space form and contact terms

The same identity appears in position space as a conservation equation with contact terms. For the unit-normalized current $J^\mu=\overline\psi\gamma^\mu\psi$,

$$
\partial_\mu^x
\langle0|T\{J^\mu(x)\psi(y)\overline\psi(z)\}|0\rangle
=
-\delta^{(4)}(x-y)\langle0|T\{\psi(y)\overline\psi(z)\}|0\rangle
+\delta^{(4)}(x-z)\langle0|T\{\psi(y)\overline\psi(z)\}|0\rangle.
$$

Away from the operator insertions, the current is conserved. At the insertions, the current acts on the charged fields and produces delta-function contact terms. These contact terms are not a nuisance; they are the source of the inverse-propagator difference in momentum space.

If one uses the physical electric current $j^\mu=Q\overline\psi\gamma^\mu\psi$, both contact terms are multiplied by $Q$. If one uses the opposite convention for the sign of $D_\mu$, the displayed charge signs move. The invariant content is that the current insertion measures the charge flowing through the fermion line.

## External photons and longitudinal decoupling

Consider an amplitude with one external photon written as

$$
\mathcal M=\epsilon_\mu(k)\mathcal M^\mu.
$$

Gauge invariance requires

$$
{k_\mu\mathcal M^\mu=0.}
$$

For photon exchange between two equal-mass fermion currents, this is just current conservation. If

$$
J^\mu(p',p)=\overline u(p')\gamma^\mu u(p),
\qquad
k=p-p',
$$

then

$$
\begin{aligned}
k_\mu J^\mu
&=\overline u(p')(p\!\!\!/-p'\!\!\!/)u(p)\\
&=m\overline u(p')u(p)-m\overline u(p')u(p)\\
&=0.
\end{aligned}
$$

This explains why the longitudinal part of a covariant photon propagator drops out between conserved external currents. In a general covariant gauge,

$$
D_{\mu\nu}(k)
=
\frac{-i}{k^2+i\epsilon}
\left[
\eta_{\mu\nu}-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}
\right],
$$

and the $k_\mu k_\nu$ term vanishes between conserved currents.

For processes with more diagrams, such as Compton scattering, the same cancellation happens only after all diagrams required by the interaction are summed. One diagram by itself usually fails the test. The Ward identity is a statement about gauge-invariant sets of diagrams, not about every drawing in isolation.

## Diagrammatic telescoping on a fermion line

The off-shell identity is especially useful on an internal fermion line. Suppose a longitudinal photon with momentum $k$ attaches between two neighboring fermion propagators. The relevant factor contains

$$
S(p+k)\,k\!\!\!/\,S(p).
$$

At tree level,

$$
k\!\!\!/
=(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m),
$$

so

$$
\begin{aligned}
S(p+k)\,k\!\!\!/\,S(p)
&=S(p+k)\left[\mathcal S_0^{-1}(p+k)-\mathcal S_0^{-1}(p)\right]S(p)\\
&=iS(p)-iS(p+k),
\end{aligned}
$$

with the factor of $i$ following our propagator convention. The longitudinal insertion turns into a difference of two diagrams in which one neighboring propagator has been canceled.

Along a longer fermion line, these differences telescope. Endpoints vanish against external on-shell spinors, or become contact terms if the line ends at an operator insertion. This is the diagrammatic reason that gauge-dependent longitudinal pieces do not survive in physical QED amplitudes.

## Consequence for renormalization: Z₁ equals Z₂

In renormalized QED, write the counterterm part schematically as

$$
\mathcal L_{\rm ct}
\supset
\delta_2\overline\psi i\gamma^\mu\partial_\mu\psi
-\delta_m m\overline\psi\psi
-Q\delta_1\overline\psi\gamma^\mu A_\mu\psi
+\cdots.
$$

The coefficient $\delta_2$ corrects the fermion kinetic term, while $\delta_1$ corrects the fermion–photon vertex. Equivalently, one often writes renormalization constants $Z_2$ and $Z_1$.

Take the Ward–Takahashi identity at small momentum transfer:

$$
k_\mu\Gamma^\mu(p+k,p)
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p).
$$

Expanding to first order in $k$ gives

$$
\Gamma^\mu(p,p)=\frac{\partial\mathcal S^{-1}(p)}{\partial p_\mu}.
$$

The ultraviolet divergence in the vertex at zero momentum transfer must therefore match the ultraviolet divergence in the derivative of the inverse fermion propagator. In a gauge-preserving regulator and scheme,

$$
{Z_1=Z_2.}
$$

This identity has an important consequence for charge renormalization. In general,

$$
Z_e=Z_1 Z_2^{-1} Z_3^{-1/2},
$$

where $Z_3$ renormalizes the photon field. Since $Z_1=Z_2$ in QED,

$$
{Z_e=Z_3^{-1/2}.}
$$

So in Abelian QED, the running of the electric charge can be extracted from photon vacuum polarization. This is one reason the QED beta function is often introduced through the photon two-point function.

## What changes in non-Abelian gauge theory

The QED Ward identity is linear because the gauge group is Abelian. Photons do not carry electric charge, and the Faddeev–Popov ghosts decouple in ordinary covariant gauges.

In Yang–Mills theory, gauge bosons carry gauge charge and interact with each other. The simple QED identity is replaced by Slavnov–Taylor identities involving gluons, ghosts, quarks, and BRST transformations. The spirit remains the same: gauge redundancy imposes algebraic relations among Green functions and counterterms. But the algebra is no longer just a difference of inverse fermion propagators. That is why non-Abelian perturbation theory needs the ghost and BRST machinery developed in the neighboring pages.

## Common pitfalls

**Checking one diagram instead of the gauge-invariant sum.** Ward identities usually apply after summing all diagrams required at a given order. Compton scattering is the first warning sign.

**Confusing global current conservation with gauge invariance.** Current conservation explains some tree-level cancellations. The full Ward–Takahashi identity is stronger: it relates off-shell Green functions, contact terms, inverse propagators, and counterterms.

**Forgetting charge conventions.** The identity $k_\mu\Gamma^\mu=\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p)$ uses a unit-normalized current vertex. The physical photon vertex includes the charge factor $-iQ$ in qft.org conventions.

**Using a regulator that breaks the symmetry without repairing it.** If a regulator violates gauge invariance, the naive Ward identity can fail at intermediate steps. A consistent calculation must either use a gauge-preserving regulator or add symmetry-restoring counterterms when possible.

**Overgeneralizing Z₁ equals Z₂.** The equality $Z_1=Z_2$ is an Abelian QED statement. Non-Abelian gauge theories have related but more elaborate Slavnov–Taylor constraints.

## Relations to other pages

- [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/) uses the on-shell Ward check $k_\mu\mathcal M^\mu=0$ for photon exchange and Compton scattering.
- [Gauge Fixing for Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/gauge-fixing-for-perturbation-theory/) explains where the longitudinal part of the covariant photon propagator enters.
- [Faddeev–Popov Ghosts in Diagrams](/perturbative-qft/gauge-theory-perturbation-theory/faddeev-popov-ghosts-in-diagrams/) explains why the Abelian story is too simple for Yang–Mills theory.
- [Wavefunction Renormalization](/perturbative-qft/renormalized-perturbation-theory/wavefunction-renormalization/) defines $Z_2$ and the residue of the fermion pole.
- [Coupling Renormalization](/perturbative-qft/renormalized-perturbation-theory/coupling-renormalization/) explains how vertex and field renormalization combine into a renormalized coupling.

## Research status

The QED Ward–Takahashi identity is an exact, textbook-standard consequence of Abelian gauge invariance. Its perturbative use is completely established in ordinary QED. The subtle points are not the identity itself, but the framework surrounding it: infrared-safe observables, gauge-preserving regularization, anomalous symmetries in chiral theories, and the non-Abelian generalization through BRST and Slavnov–Taylor identities.

## Exercises

### Exercise 1: Tree-level Ward–Takahashi identity

Verify directly that

$$
k_\mu\gamma^\mu
=\mathcal S_0^{-1}(p+k)-\mathcal S_0^{-1}(p)
$$

for a free Dirac fermion.

<details>
<summary><strong>Solution</strong></summary>

For a free Dirac fermion,

$$
\mathcal S_0^{-1}(p)=p\!\!\!/-m.
$$

Therefore

$$
\mathcal S_0^{-1}(p+k)-\mathcal S_0^{-1}(p)
=(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m)=k\!\!\!/.
$$

Since

$$
k\!\!\!/ = \gamma^\mu k_\mu,
$$

the identity follows.

</details>

### Exercise 2: Longitudinal photon exchange

Show that the gauge-dependent term proportional to $k_\mu k_\nu$ in the covariant photon propagator does not contribute to scattering between two equal-mass conserved Dirac currents.

<details>
<summary><strong>Solution</strong></summary>

The gauge-dependent contribution is proportional to

$$
J_1^\mu k_\mu\,k_\nu J_2^\nu.
$$

For one fermion current,

$$
k_\mu J^\mu
=\overline u(p')k\!\!\!/u(p).
$$

With $k=p-p'$,

$$
\overline u(p')k\!\!\!/u(p)
=\overline u(p')(p\!\!\!/-p'\!\!\!/)u(p).
$$

Using

$$
p\!\!\!/u(p)=mu(p),
\qquad
\overline u(p')p'\!\!\!/=m\overline u(p'),
$$

we get

$$
k_\mu J^\mu=0.
$$

The same argument applies to the second current, so the longitudinal propagator term vanishes.

</details>

### Exercise 3: From unamputated to amputated identity

Assume

$$
G^\mu(p+k,p)=S(p+k)\Gamma^\mu(p+k,p)S(p)
$$

and

$$
k_\mu G^\mu(p+k,p)=iS(p)-iS(p+k).
$$

Show that the amputated identity is

$$
k_\mu\Gamma^\mu(p+k,p)=\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p).
$$

<details>
<summary><strong>Solution</strong></summary>

Using

$$
S(p)=\frac{i}{\mathcal S^{-1}(p)},
$$

we have

$$
\mathcal S^{-1}(p)S(p)=i,
\qquad
S(p)\mathcal S^{-1}(p)=i.
$$

Multiply

$$
k_\mu S(p+k)\Gamma^\mu S(p)=iS(p)-iS(p+k)
$$

on the left by $\mathcal S^{-1}(p+k)$ and on the right by $\mathcal S^{-1}(p)$. The left-hand side becomes

$$
\mathcal S^{-1}(p+k)S(p+k)\,k_\mu\Gamma^\mu S(p)\mathcal S^{-1}(p)
=i^2 k_\mu\Gamma^\mu.
$$

The right-hand side becomes

$$
i\mathcal S^{-1}(p+k)S(p)\mathcal S^{-1}(p)
-i\mathcal S^{-1}(p+k)S(p+k)\mathcal S^{-1}(p)
=
-\mathcal S^{-1}(p+k)+\mathcal S^{-1}(p).
$$

Since $i^2=-1$, multiplying by $-1$ gives

$$
k_\mu\Gamma^\mu
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p).
$$

</details>

### Exercise 4: The origin of Z₁ equals Z₂

Use the small-$k$ limit of the Ward–Takahashi identity to explain why the divergent part of the QED vertex at zero momentum transfer is fixed by the divergent part of the fermion kinetic term.

<details>
<summary><strong>Solution</strong></summary>

Start with

$$
k_\mu\Gamma^\mu(p+k,p)
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p).
$$

For small $k$,

$$
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p)
=k_\mu\frac{\partial\mathcal S^{-1}(p)}{\partial p_\mu}+O(k^2).
$$

Therefore

$$
\Gamma^\mu(p,p)=\frac{\partial\mathcal S^{-1}(p)}{\partial p_\mu}.
$$

The coefficient of $p\!\!\!/$ in $\mathcal S^{-1}(p)$ is controlled by the fermion field renormalization $Z_2$. The zero-momentum-transfer vertex divergence is controlled by $Z_1$. Since the identity equates the two divergent structures, gauge-preserving renormalization gives

$$
Z_1=Z_2.
$$

</details>

## References

### Standard first pass

- Mark Srednicki, *Quantum Field Theory*, §§58, 62, and 67–68, for spinor electrodynamics, QED loop corrections, and Ward identities.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 14 and 19, for path-integral Ward–Takahashi identities and the relation $Z_1=Z_2$.
- Sidney Coleman, *Lectures on Quantum Field Theory*, ch. 33, for counterterms, Green functions, and the Ward identity in QED.

### Deeper references

- J. C. Ward, “An Identity in Quantum Electrodynamics,” *Physical Review* **78** (1950), 182.
- Y. Takahashi, “On the Generalized Ward Identity,” *Nuovo Cimento* **6** (1957), 371–375.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 8, for electrodynamics and Ward identities in covariant perturbation theory.
- Michael E. Peskin and Daniel V. Schroeder, *An Introduction to Quantum Field Theory*, chs. 7 and 10, for QED renormalization and Ward identities.

## Version history

- **2026-06-13:** Initial page for the Perturbative QFT and Scattering volume.
