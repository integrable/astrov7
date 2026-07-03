---
title: "QED Ward Identity"
description: "Derives the QED Ward–Takahashi identity, its tree-level diagrammatic form, and its consequences for on-shell Ward identities, transversality, and Z_1 = Z_2."
sidebar:
  label: "QED Ward Identity"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki §§67–68; Schwartz §14.8 and §19.5; Coleman lectures on Ward identities and QED renormalization."
topics:
  - QED
  - Ward identity
  - Ward–Takahashi identity
  - current conservation
  - charge renormalization
  - vacuum polarization
canonicalTopics:
  - qed-ward-identity
  - ward-takahashi-identity
  - current-insertion
  - charge-renormalization
researchStatus:
  established:
    - "The Abelian Ward–Takahashi identity is an exact consequence of current conservation and gauge-invariant regularization."
  active:
    - "Infrared dressings, asymptotic symmetries, finite-density backgrounds, and precision multi-loop implementations require refined versions of the same identity."
---

## Summary

This page derives the spinor-QED Ward–Takahashi identity in the convention

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\mathcal L_{\mathrm{int}}=-qA_\mu\bar\psi\gamma^\mu\psi,
$$

so the tree-level photon–fermion vertex factor is

$$
-iq\gamma^\mu.
$$

Let the exact fermion propagator be written as

$$
S(p)=\frac{i}{\mathcal S^{-1}(p)},
\qquad
\mathcal S_0^{-1}(p)=p\!\!\!/-m,
$$

and let the exact proper vertex be normalized by

$$
\text{proper vertex factor}=-iq\Gamma^\mu(p+k,p),
\qquad
\Gamma_0^\mu=\gamma^\mu.
$$

Then the amputated Ward–Takahashi identity is

$$
k_\mu\Gamma^\mu(p+k,p)
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p).
$$

At tree level this is the one-line identity

$$
k_\mu\gamma^\mu
=
(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m).
$$

<figure class="doc-figure" style="--figure-width: 43rem;">

![QED Ward–Takahashi identity as an amputated current-insertion calculation](/figures/gauge-theories-standard-model/qed-ward-identity-flow.svg)

<figcaption>

Contracting the exact QED current vertex with the incoming photon momentum gives the difference of inverse fermion propagators on the two sides of the insertion. On external on-shell legs this difference vanishes; on internal lines it cancels neighboring propagators.

</figcaption>
</figure>

This calculation is the repair manual for several familiar statements:

$$
\begin{aligned}
&\text{external photon Ward identity:}
&&k_\mu\mathcal M^\mu=0,\\
&\text{photon self-energy transversality:}
&&k_\mu\Pi^{\mu\nu}(k)=0,\\
&\text{spinor-QED renormalization:}
&&Z_1=Z_2.
\end{aligned}
$$

The Ward identity is not a decorative identity at the end of a chapter. It is the algebraic way gauge redundancy prevents longitudinal photons from becoming physical.

## What is being calculated

There are three closely related objects that are often all called “the Ward identity.” They should not be mashed into one sentence.

| Statement | Formula | Meaning |
|---|---|---|
| current-divergence identity | $\partial_\mu\langle Tj^\mu(x)\cdots\rangle=\text{contact terms}$ | Current conservation inside correlation functions, with charged insertions. |
| Ward–Takahashi identity | $k_\mu\Gamma^\mu=\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p)$ | The amputated off-shell identity for the exact vertex. |
| on-shell Ward identity | $k_\mu\mathcal M^\mu=0$ | Replacing an external photon polarization by its momentum gives zero. |

The strongest version is the Ward–Takahashi identity. The on-shell Ward identity follows from it after the inverse propagators vanish on external physical fermion states.

## Setup

Use spinor QED with one Dirac field of charge $q$:

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-qA_\mu\bar\psi\gamma^\mu\psi.
$$

It is useful to separate the charge from the current insertion. Define the unit-normalized current

$$
j_0^\mu=\bar\psi\gamma^\mu\psi,
$$

so the physical electromagnetic current is

$$
j^\mu=qj_0^\mu.
$$

The local phase transformation of the charged field is

$$
\psi(x)\mapsto e^{-i\alpha(x)}\psi(x),
\qquad
\bar\psi(x)\mapsto \bar\psi(x)e^{i\alpha(x)}.
$$

For the moment, do not transform $A_\mu$. We are deriving the current identity from a change of integration variables in the matter path integral. The kinetic term changes by

$$
\delta\mathcal L
=
(\partial_\mu\alpha)j_0^\mu.
$$

Integrating by parts will produce $-\alpha\partial_\mu j_0^\mu$. The inserted charged fields also transform, and those variations become contact terms.

## Current-divergence identity

Consider the time-ordered correlator with two charged fields:

$$
\langle Tj_0^\mu(x)\psi(y)\bar\psi(z)\rangle.
$$

The path integral is invariant under the change of variables

$$
\psi\to e^{-i\alpha}\psi,
\qquad
\bar\psi\to\bar\psi e^{i\alpha}.
$$

Keeping terms linear in $\alpha$ gives

$$
\partial_\mu\langle Tj_0^\mu(x)\psi(y)\bar\psi(z)\rangle
=
-\delta^{(4)}(x-y)\langle T\psi(y)\bar\psi(z)\rangle
+\delta^{(4)}(x-z)\langle T\psi(y)\bar\psi(z)\rangle,
$$

up to the standard overall $i$ conventions used in defining time-ordered Green functions. The important information is independent of that bookkeeping: the divergence of the current vanishes except when the current insertion collides with a charged field.

This is the part beginners tend to miss. The classical equation $\partial_\mu j_0^\mu=0$ is true inside quantum correlators only away from operator insertions. At the insertions there are delta-function terms that remember the charge of the operator.

For a product of many charged fields $\mathcal O_i(x_i)$ with charges $Q_i$ under the unit-normalized phase rotation, the same identity has the schematic form

$$
\partial_\mu\langle Tj_0^\mu(x)\prod_i\mathcal O_i(x_i)\rangle
=
\sum_i Q_i\delta^{(4)}(x-x_i)\langle T\prod_i\mathcal O_i(x_i)\rangle,
$$

with a sign determined by whether the operator transforms like $\psi$ or $\bar\psi$.

## Momentum-space identity

Fourier transform the three-point function so that the current carries incoming momentum $k$, the incoming fermion carries momentum $p$, and the outgoing fermion carries momentum $p+k$. The derivative $\partial_\mu$ becomes multiplication by $ik_\mu$, while the two contact terms shift the momentum flowing through the two-point function.

After amputating the two external fermion propagators and using the proper-vertex normalization

$$
\text{vertex factor}=-iq\Gamma^\mu(p+k,p),
$$

the result is

$$
k_\mu\Gamma^\mu(p+k,p)
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p).
$$

This is the Ward–Takahashi identity in the convention used throughout the QED pages.

If the charge is included in the vertex function instead, define

$$
\Lambda^\mu(p+k,p)=q\Gamma^\mu(p+k,p).
$$

Then the identity becomes

$$
k_\mu\Lambda^\mu(p+k,p)
=
q\left[\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p)\right].
$$

Both forms are common. They differ only by where the factor of $q$ is stored.

## Tree-level check

At tree level,

$$
\Gamma_0^\mu=\gamma^\mu,
\qquad
\mathcal S_0^{-1}(p)=p\!\!\!/-m.
$$

Therefore

$$
k_\mu\Gamma_0^\mu
=
k_\mu\gamma^\mu
=
k\!\!\!/
=
(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m).
$$

The identity is trivial at tree level because the kinetic operator and the photon vertex came from the same covariant derivative. The nontrivial statement is that the identity survives loop corrections, provided the regulator and counterterms preserve the Abelian gauge symmetry.

## Internal-line cancellation

The tree-level identity has a useful diagrammatic form. With

$$
S_0(p)=\frac{i}{p\!\!\!/-m+i0},
$$

we find

$$
S_0(p+k)(-iqk_\mu\gamma^\mu)S_0(p)
=
q\left[S_0(p)-S_0(p+k)\right].
$$

Derivation:

$$
\begin{aligned}
S_0(p+k)(-iqk_\mu\gamma^\mu)S_0(p)
&=S_0(p+k)(-iq)\left[\mathcal S_0^{-1}(p+k)-\mathcal S_0^{-1}(p)\right]S_0(p)\\
&=q\left[S_0(p)-S_0(p+k)\right].
\end{aligned}
$$

This is the algebra behind the familiar cancellation of diagrams when an external photon polarization is replaced by its momentum. The contracted photon vertex collapses a charged propagator on one side or the other. In a full amplitude, these terms cancel between neighboring photon insertions or vanish on external on-shell legs.

## On-shell Ward identity

For an amplitude with an external photon,

$$
\mathcal M=\epsilon_\mu(k)\mathcal M^\mu,
$$

physical gauge invariance requires invariance under

$$
\epsilon_\mu(k)\mapsto\epsilon_\mu(k)+c k_\mu.
$$

Equivalently,

$$
k_\mu\mathcal M^\mu=0.
$$

The Ward–Takahashi identity proves this statement for amplitudes with external charged fermions. On an outgoing spinor,

$$
\bar u(p+k)\mathcal S^{-1}(p+k)=0,
$$

and on an incoming spinor,

$$
\mathcal S^{-1}(p)u(p)=0.
$$

Therefore

$$
\bar u(p+k)k_\mu\Gamma^\mu(p+k,p)u(p)=0.
$$

The same cancellation holds in multi-leg amplitudes after summing over all possible photon attachments. That summation is not optional: the Ward identity is a statement about the gauge-invariant set of diagrams.

## Zero-momentum limit and Z₁ equals Z₂

Take the Ward–Takahashi identity at small $k$:

$$
k_\mu\Gamma^\mu(p+k,p)
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p).
$$

Expand the right-hand side:

$$
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p)
=
k_\mu\frac{\partial\mathcal S^{-1}(p)}{\partial p_\mu}+O(k^2).
$$

Thus

$$
\Gamma^\mu(p,p)
=
\frac{\partial\mathcal S^{-1}(p)}{\partial p_\mu}.
$$

The divergent coefficient multiplying $\gamma^\mu$ in the vertex must match the divergent coefficient multiplying $p\!\!\!/$ in the inverse fermion propagator. In the usual QED renormalization notation this gives

$$
Z_1=Z_2.
$$

This is why charge renormalization in spinor QED is controlled by the photon field-strength renormalization $Z_3$. The vertex and external-fermion wavefunction factors cancel in the renormalized charge. Said less politely: the Ward identity refuses to let the electric charge renormalize independently at every place it appears.

## Vacuum-polarization transversality

The same identity applied to two electromagnetic currents gives

$$
k_\mu\Pi^{\mu\nu}(k)=0.
$$

Lorentz invariance then forces the photon self-energy to have the form

$$
\Pi^{\mu\nu}(k)
=
\left(k^\mu k^\nu-k^2\eta^{\mu\nu}\right)\Pi(k^2),
$$

up to convention-dependent signs in the scalar function. This is why a gauge-invariant regulator cannot generate a photon mass term proportional to $\eta^{\mu\nu}$ alone. The next page uses this as the main check on the one-loop vacuum-polarization calculation.

## Common mistakes

**Dropping contact terms.** The divergence of the current is zero only away from charged insertions. The contact terms are the identity.

**Confusing the exact inverse propagator with the free inverse propagator.** The identity is exact:

$$
k_\mu\Gamma^\mu=\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p),
$$

not merely a tree-level mnemonic.

**Including the charge on one side but not the other.** If the vertex is $-iq\Gamma^\mu$, the charge does not appear in the displayed Ward–Takahashi identity. If the vertex is defined as a current insertion $q\Gamma^\mu$, the right-hand side gets multiplied by $q$.

**Checking only one diagram.** The on-shell Ward identity is generally true only after summing the gauge-invariant set of diagrams at a given order.

**Using a regulator that breaks gauge symmetry without repairing it.** A hard cutoff can produce gauge-noninvariant intermediate terms. Dimensional regularization preserves the identity more cleanly in perturbative QED.

## Exercises

### Tree-level propagator cancellation

Show that

$$
S_0(p+k)(-iqk_\mu\gamma^\mu)S_0(p)
=
q\left[S_0(p)-S_0(p+k)\right]
$$

for

$$
S_0(p)=\frac{i}{p\!\!\!/-m+i0}.
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
k_\mu\gamma^\mu
=
\mathcal S_0^{-1}(p+k)-\mathcal S_0^{-1}(p),
$$

where $\mathcal S_0^{-1}(p)=p\!\!\!/-m$. Then

$$
\begin{aligned}
S_0(p+k)(-iqk_\mu\gamma^\mu)S_0(p)
&=S_0(p+k)(-iq)\left[\mathcal S_0^{-1}(p+k)-\mathcal S_0^{-1}(p)\right]S_0(p).
\end{aligned}
$$

Since $S_0(p)=i[\mathcal S_0^{-1}(p)]^{-1}$, the two terms become

$$
qS_0(p)-qS_0(p+k).
$$

Therefore

$$
S_0(p+k)(-iqk_\mu\gamma^\mu)S_0(p)
=
q\left[S_0(p)-S_0(p+k)\right].
$$

</details>

### Zero-momentum limit

Starting from

$$
k_\mu\Gamma^\mu(p+k,p)
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p),
$$

derive

$$
\Gamma^\mu(p,p)=\frac{\partial\mathcal S^{-1}(p)}{\partial p_\mu}.
$$

<details><summary><strong>Solution</strong></summary>

Expand both sides to first order in $k$. The right-hand side is

$$
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p)
=
k_\mu\frac{\partial\mathcal S^{-1}(p)}{\partial p_\mu}+O(k^2).
$$

The left-hand side is

$$
k_\mu\Gamma^\mu(p,p)+O(k^2).
$$

Equating the coefficients of arbitrary $k_\mu$ gives

$$
\Gamma^\mu(p,p)=\frac{\partial\mathcal S^{-1}(p)}{\partial p_\mu}.
$$

</details>

### Photon self-energy tensor

Assume Lorentz invariance and the Ward identity

$$
k_\mu\Pi^{\mu\nu}(k)=0.
$$

Show that the photon self-energy must have the form

$$
\Pi^{\mu\nu}(k)=\left(k^\mu k^\nu-k^2\eta^{\mu\nu}\right)\Pi(k^2).
$$

<details><summary><strong>Solution</strong></summary>

The most general Lorentz-covariant rank-two tensor built only from $k^\mu$ and $\eta^{\mu\nu}$ is

$$
\Pi^{\mu\nu}=A(k^2)\eta^{\mu\nu}+B(k^2)k^\mu k^\nu.
$$

Contract with $k_\mu$:

$$
k_\mu\Pi^{\mu\nu}=\left[A(k^2)+B(k^2)k^2\right]k^\nu.
$$

Transversality requires

$$
A(k^2)=-B(k^2)k^2.
$$

Writing $B(k^2)=\Pi(k^2)$ gives

$$
\Pi^{\mu\nu}=\left(k^\mu k^\nu-k^2\eta^{\mu\nu}\right)\Pi(k^2).
$$

</details>

## Related pages

- [QED Vertices](/gauge-theories-standard-model/qed/qed-vertices/) gives the tree-level spinor and scalar QED vertices.
- [Ward–Takahashi Identity](/gauge-theories-standard-model/qed/ward-takahashi-identity/) gives the conceptual QED page for the same identity.
- [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/) explains the transverse and longitudinal parts of the photon propagator.
- [QED Renormalization](/gauge-theories-standard-model/gauge-renormalization/qed-renormalization/) uses $Z_1=Z_2$ to organize charge renormalization.
- [QED Vacuum Polarization](/gauge-theories-standard-model/calculation-library/qed-vacuum-polarization/) performs the one-loop self-energy calculation.

## References

- Srednicki, *Quantum Field Theory*, especially the Ward identities in QED chapters.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the Ward–Takahashi identity and QED renormalization sections.
- Coleman, *Lectures on Quantum Field Theory* and *Aspects of Symmetry*, for Ward identities and symmetry-current reasoning.

## Version history

- **2026-06-19:** Initial calculation-library derivation of the QED Ward–Takahashi identity, tree-level cancellation formula, $Z_1=Z_2$ consequence, and vacuum-polarization transversality.
