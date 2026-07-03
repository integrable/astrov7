---
title: "QED Vacuum Polarization"
description: "Computes the one-loop spinor-QED vacuum polarization tensor, verifies transversality, and extracts the renormalized scalar function controlling charge screening."
sidebar:
  label: "QED Vacuum Polarization"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §§62, 66–68; Schwartz Chs. 16 and 19; Weinberg Vol. I QED renormalization chapters."
topics:
  - QED
  - vacuum polarization
  - photon self-energy
  - dimensional regularization
  - running electric charge
  - Ward identity
canonicalTopics:
  - qed-vacuum-polarization
  - photon-self-energy
  - charge-renormalization
  - qed-beta-function
researchStatus:
  established:
    - "The one-loop spinor-QED vacuum polarization tensor is a standard calculation; its transverse tensor structure follows from the Ward–Takahashi identity."
  active:
    - "Precision applications require multi-loop, threshold, hadronic, finite-temperature, and scheme-specific refinements beyond this one-loop template."
---

## Summary

This page computes the one-loop photon self-energy in spinor QED. For a Dirac fermion of charge $q_f$ and mass $m$, define

$$
i\Pi^{\mu\nu}(k)
$$

as the one-particle-irreducible two-photon amplitude. With the scalar-function convention

$$
i\Pi^{\mu\nu}(k)
=
i\left(k^\mu k^\nu-k^2\eta^{\mu\nu}\right)\Pi(k^2),
$$

dimensional regularization gives

$$
\Pi(k^2)
=
\frac{q_f^2}{2\pi^2}
\int_0^1 dx\,x(1-x)
\left[
\frac{1}{\bar\epsilon}
-
\ln\frac{m^2-k^2x(1-x)-i0}{\mu^2}
\right]
+\delta Z_3,
$$

where

$$
\frac{1}{\bar\epsilon}=\frac{1}{\epsilon}-\gamma_E+\ln 4\pi,
\qquad
 d=4-2\epsilon.
$$

The Ward identity enforces

$$
k_\mu\Pi^{\mu\nu}(k)=0.
$$

After subtracting at $k^2=0$, the finite renormalized function is

$$
\Pi_R(k^2)
=
-\frac{q_f^2}{2\pi^2}
\int_0^1 dx\,x(1-x)
\ln\left[1-\frac{k^2}{m^2}x(1-x)-i0\right].
$$

<figure class="doc-figure" style="--figure-width: 42rem;">

![One-loop QED vacuum polarization calculation flow](/figures/gauge-theories-standard-model/qed-vacuum-polarization-transversality.svg)

<figcaption>

Contracting the photon self-energy with $k_\mu$ turns the current insertion into a difference of inverse fermion propagators. With a shift-invariant regulator, the two terms cancel and the allowed tensor is transverse.

</figcaption>
</figure>

For spacelike momentum $k^2=-Q^2$, the subtracted function is negative at large $Q$:

$$
\Pi_R(-Q^2)
\simeq
-\frac{q_f^2}{12\pi^2}\ln\frac{Q^2}{m^2}+\text{constant}.
$$

Since the transverse photon propagator is proportional to $1/[1+\Pi_R(-Q^2)]$ in this convention, the effective electric charge grows at short distances. QED screens charge in the infrared and anti-screens it as one probes inward through the polarization cloud.

## Setup and conventions

The spinor-QED Lagrangian is

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-q_fA_\mu\bar\psi\gamma^\mu\psi.
$$

The Feynman rules are

$$
\text{fermion propagator:}\qquad
\frac{i(p\!\!\!/+m)}{p^2-m^2+i0},
$$

and

$$
\text{photon--fermion vertex:}\qquad
-iq_f\gamma^\mu.
$$

We use dimensional regularization in

$$
d=4-2\epsilon
$$

and introduce the renormalization scale $\mu$ so that the charge remains dimensionless away from four dimensions.

The scalar vacuum-polarization function is convention-dependent. This page uses

$$
i\Pi^{\mu\nu}(k)
=
i(k^\mu k^\nu-k^2\eta^{\mu\nu})\Pi(k^2).
$$

Some sources define instead

$$
\Pi^{\mu\nu}(k)
=
(k^2\eta^{\mu\nu}-k^\mu k^\nu)\widehat\Pi(k^2),
$$

which means $\widehat\Pi=-\Pi$. The tensor is physical; the sign assigned to the scalar function is a convention. Do not mix scalar conventions midstream. That way lies swamp algebra.

## One-loop amplitude

The one-loop diagram gives

$$
i\Pi^{\mu\nu}(k)
=
(-1)(-iq_f)^2
\int\frac{d^d\ell}{(2\pi)^d}
\operatorname{tr}\left[
\gamma^\mu
\frac{i(\ell\!\!\!/+m)}{\ell^2-m^2+i0}
\gamma^\nu
\frac{i(\ell\!\!\!/+k\!\!\!/+m)}{(\ell+k)^2-m^2+i0}
\right].
$$

The factor $(-1)$ is the closed fermion-loop sign. The two vertices contribute $(-iq_f)^2$, so the final answer is proportional to $q_f^2$. Vacuum polarization is insensitive to the sign of the charge.

The gamma trace is

$$
\operatorname{tr}\left[\gamma^\mu(\ell\!\!\!/+m)\gamma^\nu(\ell\!\!\!/+k\!\!\!/+m)\right]
=
4\left[
\ell^\mu(\ell+k)^\nu
+\ell^\nu(\ell+k)^\mu
-\eta^{\mu\nu}\ell\cdot(\ell+k)
+m^2\eta^{\mu\nu}
\right].
$$

This trace is the only spinor-specific part of the calculation. Everything afterward is loop-integral bookkeeping plus the Ward-identity check.

## Feynman parameter and shift

Combine denominators with

$$
\frac{1}{ab}
=
\int_0^1 dx\,\frac{1}{[xa+(1-x)b]^2}.
$$

After shifting the loop momentum to

$$
r=\ell+xk,
$$

the denominator becomes

$$
(r^2-\Delta+i0)^2,
\qquad
\Delta=m^2-k^2x(1-x).
$$

Odd powers of $r$ vanish after integration. Lorentz invariance in $d$ dimensions gives

$$
\int\frac{d^dr}{(2\pi)^d}\,r^\mu r^\nu f(r^2)
=
\frac{\eta^{\mu\nu}}{d}
\int\frac{d^dr}{(2\pi)^d}\,r^2 f(r^2).
$$

Using these identities, the non-transverse pieces cancel in dimensional regularization, and the remaining tensor structure is

$$
i\Pi^{\mu\nu}(k)
=
i(k^\mu k^\nu-k^2\eta^{\mu\nu})\Pi(k^2).
$$

This cancellation is not an accident. It is the loop-integral form of the Ward identity. A regulator that does not respect gauge invariance can produce apparent non-transverse power-divergent terms; such terms must be removed by symmetry-restoring counterterms. Dimensional regularization avoids that mess in this calculation.

## Scalar function before subtraction

The scalar function is

$$
\Pi(k^2)
=
\frac{q_f^2}{2\pi^2}
\int_0^1 dx\,x(1-x)
\left[
\frac{1}{\bar\epsilon}
-
\ln\frac{m^2-k^2x(1-x)-i0}{\mu^2}
\right]
+\delta Z_3.
$$

The counterterm $\delta Z_3$ is fixed by a renormalization condition. In minimal subtraction it cancels only the pole and associated $\overline{\mathrm{MS}}$ constants. In an on-shell charge scheme one often subtracts at $k^2=0$, so that the long-distance Coulomb charge is the renormalized charge.

The divergent part is simple because

$$
\int_0^1 dx\,x(1-x)=\frac16.
$$

Thus the pole is

$$
\Pi(k^2)\supset
\frac{q_f^2}{12\pi^2}\frac{1}{\bar\epsilon}.
$$

For several Dirac fermions, replace

$$
q_f^2\longrightarrow \sum_f N_c^{(f)}q_f^2,
$$

where $N_c^{(f)}$ is the color multiplicity of the fermion. In QED alone $N_c=1$; for quarks in the Standard Model, $N_c=3$.

## Subtracted vacuum polarization

If the renormalized electric charge is defined at $k^2=0$, choose $\delta Z_3$ so that

$$
\Pi_R(0)=0.
$$

Then

$$
\Pi_R(k^2)
=
\Pi(k^2)-\Pi(0),
$$

so

$$
\Pi_R(k^2)
=
-\frac{q_f^2}{2\pi^2}
\int_0^1 dx\,x(1-x)
\ln\left[1-\frac{k^2}{m^2}x(1-x)-i0\right].
$$

This expression is finite and scheme-independent up to the choice of subtraction point.

For small $|k^2|\ll m^2$,

$$
\ln(1-y)=-y+O(y^2),
$$

so

$$
\Pi_R(k^2)
=
\frac{q_f^2 k^2}{2\pi^2m^2}
\int_0^1 dx\,x^2(1-x)^2+O(k^4/m^4).
$$

Since

$$
\int_0^1 dx\,x^2(1-x)^2=\frac{1}{30},
$$

we get

$$
\Pi_R(k^2)
=
\frac{q_f^2}{60\pi^2}\frac{k^2}{m^2}+O(k^4/m^4).
$$

This is the beginning of the low-energy expansion obtained by integrating out a heavy charged fermion. In effective-field-theory language it corresponds to higher-derivative operators built from $F_{\mu\nu}$.

## Spacelike momentum and running charge

Set

$$
k^2=-Q^2,
\qquad
Q^2>0.
$$

Then

$$
\Pi_R(-Q^2)
=
-\frac{q_f^2}{2\pi^2}
\int_0^1 dx\,x(1-x)
\ln\left[1+\frac{Q^2}{m^2}x(1-x)\right].
$$

For $Q^2\gg m^2$,

$$
\Pi_R(-Q^2)
=
-\frac{q_f^2}{12\pi^2}\ln\frac{Q^2}{m^2}+\text{constant}+O(m^2/Q^2).
$$

In this page's convention, the transverse photon propagator is corrected schematically as

$$
D_T(k)
\sim
\frac{-i}{k^2[1+\Pi_R(k^2)]}.
$$

Thus for spacelike momentum, a negative $\Pi_R(-Q^2)$ increases the effective electric charge at short distances. For one Dirac fermion of unit charge magnitude, the one-loop beta function is equivalently

$$
\beta(e)=\mu\frac{de}{d\mu}=\frac{e^3}{12\pi^2},
$$

or

$$
\beta(\alpha)=\mu\frac{d\alpha}{d\mu}=\frac{2\alpha^2}{3\pi},
\qquad
\alpha=\frac{e^2}{4\pi}.
$$

For multiple charged Dirac fermions, multiply the coefficient by $\sum_f N_c^{(f)}Q_f^2$.

## Checks

**Transversality.** The final tensor satisfies

$$
k_\mu(k^\mu k^\nu-k^2\eta^{\mu\nu})=0.
$$

If your answer contains an uncanceled term proportional to $\eta^{\mu\nu}m^2$ or $\eta^{\mu\nu}\Lambda^2$, the calculation has either broken gauge invariance or not yet included the symmetry-restoring subtraction.

**Charge conjugation.** The answer is proportional to $q_f^2$, not $q_f$. Reversing the sign of the fermion charge leaves the vacuum polarization unchanged.

**Dimensional analysis.** The scalar function $\Pi(k^2)$ is dimensionless. The tensor $\Pi^{\mu\nu}$ has mass dimension $2$, carried by the projector $k^\mu k^\nu-k^2\eta^{\mu\nu}$.

**Low-energy decoupling.** After subtracting at $k^2=0$, the effect of a heavy fermion begins at order $k^2/m^2$. Heavy charged matter decouples from very low-energy photon propagation, except through the definition of the renormalized charge.

## Common mistakes

**Forgetting the closed fermion-loop sign.** The loop carries a factor $(-1)$ before the two vertex factors and propagators are multiplied.

**Dropping the $m^2\eta^{\mu\nu}$ trace term.** It is needed for the cancellation that gives a transverse answer.

**Using four-dimensional tensor reduction before regulating.** In divergent integrals, replacing $r^\mu r^\nu$ by $\eta^{\mu\nu}r^2/4$ too early can hide gauge-violating artifacts. Use $\eta^{\mu\nu}r^2/d$ in dimensional regularization.

**Confusing $\Pi$ with $-\Pi$.** Some authors define the scalar function with the opposite transverse projector. Always compare the full tensor, not just the named scalar.

**Interpreting the loop alone as an observable.** The unrenormalized self-energy is not directly measurable. Physical predictions use a renormalized charge and a specified subtraction scheme.

## Exercises

### Trace check

Show that

$$
\operatorname{tr}\left[\gamma^\mu(\ell\!\!\!/+m)\gamma^\nu(\ell\!\!\!/+k\!\!\!/+m)\right]
=
4\left[
\ell^\mu(\ell+k)^\nu
+\ell^\nu(\ell+k)^\mu
-\eta^{\mu\nu}\ell\cdot(\ell+k)
+m^2\eta^{\mu\nu}
\right].
$$

<details><summary><strong>Solution</strong></summary>

Expand the trace. Terms with an odd number of gamma matrices vanish. The four-gamma trace gives

$$
\operatorname{tr}(\gamma^\mu\gamma^\alpha\gamma^\nu\gamma^\beta)
=
4(\eta^{\mu\alpha}\eta^{\nu\beta}-\eta^{\mu\nu}\eta^{\alpha\beta}+\eta^{\mu\beta}\eta^{\alpha\nu}).
$$

Therefore

$$
\operatorname{tr}(\gamma^\mu\ell\!\!\!/\gamma^\nu(\ell\!\!\!/+k\!\!\!/))
=
4\left[\ell^\mu(\ell+k)^\nu+\ell^\nu(\ell+k)^\mu-\eta^{\mu\nu}\ell\cdot(\ell+k)\right].
$$

The mass term gives

$$
m^2\operatorname{tr}(\gamma^\mu\gamma^\nu)=4m^2\eta^{\mu\nu}.
$$

Adding the pieces gives the stated result.

</details>

### Low-energy expansion

Starting from

$$
\Pi_R(k^2)
=
-\frac{q_f^2}{2\pi^2}
\int_0^1 dx\,x(1-x)
\ln\left[1-\frac{k^2}{m^2}x(1-x)-i0\right],
$$

show that

$$
\Pi_R(k^2)=\frac{q_f^2}{60\pi^2}\frac{k^2}{m^2}+O(k^4/m^4).
$$

<details><summary><strong>Solution</strong></summary>

For $|k^2|\ll m^2$, use

$$
\ln(1-y)=-y+O(y^2),
\qquad
 y=\frac{k^2}{m^2}x(1-x).
$$

Then

$$
\Pi_R(k^2)
=
\frac{q_f^2}{2\pi^2}\frac{k^2}{m^2}
\int_0^1 dx\,x^2(1-x)^2+O(k^4/m^4).
$$

The integral is

$$
\int_0^1 dx\,x^2(1-x)^2
=\int_0^1 dx\,(x^2-2x^3+x^4)
=\frac13-\frac12+\frac15
=\frac{1}{30}.
$$

Thus

$$
\Pi_R(k^2)=\frac{q_f^2}{60\pi^2}\frac{k^2}{m^2}+O(k^4/m^4).
$$

</details>

### One-loop QED beta function

Use the pole

$$
\Pi(k^2)\supset \frac{q_f^2}{12\pi^2}\frac{1}{\bar\epsilon}
$$

for a unit-charged Dirac fermion to recover

$$
\beta(e)=\frac{e^3}{12\pi^2}.
$$

<details><summary><strong>Solution</strong></summary>

For a unit-charged Dirac fermion, $q_f=e$. The photon-field counterterm cancels the divergent part of the transverse two-point function, so in minimal subtraction the charge renormalization is controlled by the same coefficient because the Ward identity gives $Z_1=Z_2$.

Equivalently, the spacelike renormalized vacuum polarization behaves as

$$
\Pi_R(-Q^2)
\simeq
-\frac{e^2}{12\pi^2}\ln\frac{Q^2}{\mu^2}.
$$

Since the effective charge is proportional to $e^2/[1+\Pi_R(-Q^2)]$, differentiating with respect to $\ln Q$ gives

$$
\mu\frac{d e}{d\mu}=\frac{e^3}{12\pi^2}
$$

at one loop. In terms of $\alpha=e^2/(4\pi)$,

$$
\beta(\alpha)=\frac{2\alpha^2}{3\pi}.
$$

</details>

## Related pages

- [QED Ward Identity](/gauge-theories-standard-model/calculation-library/qed-ward-identity/) derives the identity that enforces transversality.
- [Vacuum Polarization](/gauge-theories-standard-model/qed/vacuum-polarization/) gives the conceptual QED page.
- [Running Electric Charge](/gauge-theories-standard-model/qed/running-electric-charge/) explains the physical interpretation as charge screening.
- [QED Renormalization](/gauge-theories-standard-model/gauge-renormalization/qed-renormalization/) organizes the counterterms and $Z$ factors.
- [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/) explains the transverse projector used here.

## References

- Srednicki, *Quantum Field Theory*, especially the QED loop-correction, beta-function, and Ward-identity chapters.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the vacuum-polarization and renormalized-QED chapters.
- Weinberg, *The Quantum Theory of Fields*, Vol. I, for QED renormalization and charge renormalization.

## Version history

- **2026-06-19:** Initial calculation-library derivation of the one-loop spinor-QED vacuum polarization, including transversality, subtracted scalar function, low-energy expansion, and beta-function check.
