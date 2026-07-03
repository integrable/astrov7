---
title: "Heavy-Quark Effective Theory"
description: "Heavy-quark effective theory as the EFT of QCD with one heavy quark: velocity labels, residual momentum, static limit, heavy-quark symmetry, 1/m corrections, matching, running, and applications to heavy hadrons."
sidebar:
  label: "Heavy-Quark Effective Theory"
  order: 40
level: Graduate
status: "Polished draft"
source: "Isgur and Wise 1989–1991; Georgi 1990; Neubert 1994; Manohar and Wise 2000; Schwartz 2014, ch. 35; Burgess 2020, chs. 2–3 and 8."
topics:
  - heavy-quark effective theory
  - HQET
  - heavy-quark symmetry
  - velocity superselection
  - matching and running
  - heavy hadrons
canonicalTopics:
  - heavy-quark-effective-theory
  - hqet
  - heavy-quark-symmetry
researchStatus:
  established:
    - "HQET is the standard EFT for hadrons containing one heavy quark with mass much larger than the QCD scale."
  active:
    - "Precision heavy-flavor phenomenology, lattice-QCD matching, inclusive-decay expansions, renormalon-safe mass schemes, and higher-order perturbative matching remain active research areas."
---

## Summary

Heavy-quark effective theory, usually abbreviated HQET, is the effective field theory of QCD for hadrons containing a single heavy quark. The basic hierarchy is

$$
m_Q\gg \Lambda_{\mathrm{QCD}},
$$

where $Q$ is a charm or bottom quark in most applications. The heavy quark is not treated as a relativistic particle being created and destroyed freely. Instead, inside a heavy hadron it moves almost with a fixed four-velocity $v^\mu$, with only a small residual momentum $k^\mu$ of order $\Lambda_{\mathrm{QCD}}$:

$$
p_Q^\mu=m_Q v^\mu+k^\mu,
\qquad
v^2=1,
\qquad
k^\mu\sim \Lambda_{\mathrm{QCD}}.
$$

HQET removes the large, almost trivial rest-mass oscillation from the heavy-quark field, expands in powers of $1/m_Q$, and keeps the soft QCD dynamics that acts on the residual momentum. The leading Lagrangian is

$$
\mathcal L_{\mathrm{HQET}}^{(0)}
=\bar h_v\,i v\cdot D\,h_v,
$$

where $h_v$ is a projected heavy-quark field satisfying

$$
v\!\!\!/\,h_v=h_v,
\qquad
v\!\!\!/\equiv \gamma^\mu v_\mu.
$$

The first corrections are

$$
\mathcal L_{\mathrm{HQET}}
=\bar h_v i v\cdot D h_v
+\frac{1}{2m_Q}\mathcal O_{\mathrm{kin}}
+\frac{C_{\mathrm{mag}}(\mu)}{2m_Q}\mathcal O_{\mathrm{mag}}
+O\!\left(\frac{1}{m_Q^2}\right),
$$

with

$$
\mathcal O_{\mathrm{kin}}
=\bar h_v (iD_\perp)^2 h_v,
\qquad
\mathcal O_{\mathrm{mag}}
=\frac{g_s}{2}\bar h_v\sigma_{\mu\nu}G^{\mu\nu}h_v,
$$

and

$$
D_\perp^\mu=D^\mu-v^\mu v\cdot D.
$$

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Heavy-quark effective theory map from QCD heavy-quark momentum split through field projection and static dynamics to 1 over m corrections, matching coefficients, and heavy-hadron observables](/figures/renormalization-rg-eft/hqet-velocity-expansion-map.svg)

<figcaption>

HQET separates the large mechanical momentum $m_Qv^\mu$ from the residual soft momentum $k^\mu$. After rephasing and projecting the Dirac field, QCD becomes a static leading theory plus a controlled tower of $1/m_Q$ corrections.

</figcaption>
</figure>

:::note[The punchline]
HQET turns the statement $m_Q\gg\Lambda_{\mathrm{QCD}}$ into a systematic expansion. The heavy quark becomes a nearly static color source at leading order, and all dependence on its spin and finite mass is organized in local operators suppressed by powers of $1/m_Q$.
:::

## Prerequisites

You should know [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/), [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), and [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/). You should also be comfortable with QCD covariant derivatives, Dirac projectors, and Wilson coefficients.

This page uses the mostly-minus metric and the convention $v\!\!\!/\equiv\gamma^\mu v_\mu$. For a time-like velocity $v^2=1$. In the heavy-hadron rest frame,

$$
v^\mu=(1,\mathbf 0).
$$

## Core idea

A heavy quark inside a heavy-light hadron carries a large rest energy $m_Q$ and a much smaller dynamical momentum set by the surrounding light degrees of freedom. The large rest energy does not control the long-distance structure of the hadron. It mostly says that the heavy quark is heavy.

The light cloud sees the heavy quark as a color source moving with velocity $v^\mu$. If $m_Q\to\infty$, the heavy quark does not recoil under soft QCD interactions. Its spin also decouples, because spin-flip interactions require the chromomagnetic moment, which is suppressed by $1/m_Q$.

This creates two approximate symmetries:

| Symmetry | Meaning | Broken by |
|---|---|---|
| Heavy-quark spin symmetry | The light cloud is insensitive to the orientation of the heavy-quark spin. | Chromomagnetic interactions of order $1/m_Q$. |
| Heavy-quark flavor symmetry | The light cloud is insensitive to whether the static source is $b$ or $c$. | Kinetic and matching effects suppressed by $1/m_Q$ and by different short-distance coefficients. |

These symmetries are not exact symmetries of QCD. They are infrared consequences of a hierarchy of scales. The EFT makes them visible by removing $m_Q$ from the leading long-distance dynamics.

## The heavy-quark momentum split

For a heavy quark close to its mass shell, write

$$
p_Q^\mu=m_Qv^\mu+k^\mu,
$$

where $v^\mu$ is a reference four-velocity and $k^\mu$ is residual. The on-shell condition gives

$$
p_Q^2=m_Q^2
\quad\Rightarrow\quad
2m_Q v\cdot k+k^2=0.
$$

If $k\sim\Lambda_{\mathrm{QCD}}$, then $v\cdot k$ is also of order $\Lambda_{\mathrm{QCD}}$ for generic off-shell fluctuations inside a hadron. The point is that $k$ is not of order $m_Q$.

The split is not unique. A small change

$$
v^\mu\longrightarrow v^\mu+\frac{\delta v^\mu}{m_Q},
\qquad
k^\mu\longrightarrow k^\mu-\delta v^\mu,
$$

can leave $p_Q^\mu$ unchanged. The EFT remembers this redundancy as **reparametrization invariance**. It constrains Wilson coefficients, most famously protecting the coefficient of the kinetic operator.

## Field redefinition and projection

Start from the QCD heavy-quark term

$$
\mathcal L_Q=\bar Q(iD\!\!\!/-m_Q)Q,
\qquad
D\!\!\!/\equiv\gamma^\mu D_\mu.
$$

Remove the large phase by defining

$$
Q(x)=e^{-im_Q v\cdot x}Q_v(x).
$$

Then split $Q_v$ into projected components

$$
h_v=P_+Q_v,
\qquad
H_v=P_-Q_v,
\qquad
P_\pm=\frac{1\pm v\!\!\!/}{2}.
$$

The field $h_v$ describes the large component that remains in the low-energy theory. The field $H_v$ describes the small component separated by an energy of order $2m_Q$. Inserting the decomposition into the heavy-quark Lagrangian gives schematically

$$
\mathcal L_Q
=\bar h_v i v\cdot D h_v
-\bar H_v(2m_Q+i v\cdot D)H_v
+\bar h_v iD\!\!\!/_{\perp}H_v
+\bar H_v iD\!\!\!/_{\perp}h_v.
$$

The small component $H_v$ is not an independent low-energy degree of freedom. Its equation of motion gives

$$
H_v=\frac{1}{2m_Q+i v\cdot D}iD\!\!\!/_{\perp}h_v.
$$

Expanding the inverse in powers of $1/m_Q$ produces the HQET operator tower.

## The leading static theory

At leading order,

$$
\mathcal L_{\mathrm{HQET}}^{(0)}=\bar h_v i v\cdot D h_v.
$$

In the hadron rest frame this is

$$
\mathcal L_{\mathrm{HQET}}^{(0)}=h_v^\dagger iD_0 h_v.
$$

There is no spatial kinetic term at leading order. This is not a typo. The heavy quark is infinitely massive in this limit, so changing its spatial momentum costs no leading recoil energy. It propagates forward in time as a static color source.

The corresponding leading propagator is

$$
\frac{i}{v\cdot k+i\epsilon}P_+,
$$

up to convention-dependent choices about whether projectors are included in propagators or external spinors. In the rest frame this becomes

$$
\frac{i}{k^0+i\epsilon}P_+.
$$

The leading interaction with soft gluons comes only through $v\cdot A^aT^a$. The heavy-quark spin matrices do not appear. That is the origin of heavy-quark spin symmetry.

## Heavy-quark spin and flavor symmetry

The leading HQET Lagrangian

$$
\bar h_v i v\cdot D h_v
$$

contains no gamma matrices except the implicit projection condition. Therefore it is invariant under independent rotations of the heavy-quark spin:

$$
h_v\longrightarrow S h_v,
\qquad
S v\!\!\!/=v\!\!\!/S.
$$

For several heavy flavors with the same velocity, it is also independent of $m_Q$. Thus the light cloud in a heavy-light meson does not care whether the static source is $b$ or $c$, except through corrections.

Consequences include approximate degeneracy between heavy-light pseudoscalar and vector mesons:

$$
B\quad\text{and}\quad B^*,
\qquad
D\quad\text{and}\quad D^*.
$$

The observed mass splittings are not zero because $m_b$ and $m_c$ are finite. HQET predicts their parametric scaling:

$$
M_{B^*}-M_B\sim \frac{\Lambda_{\mathrm{QCD}}^2}{m_b},
\qquad
M_{D^*}-M_D\sim \frac{\Lambda_{\mathrm{QCD}}^2}{m_c}.
$$

The symmetry is more useful than this simple mass statement. It relates form factors in semileptonic heavy-hadron decays and reduces many nonperturbative functions to universal ones in the heavy-quark limit.

## The first power corrections

At order $1/m_Q$, the two central operators are the kinetic operator and the chromomagnetic operator:

$$
\mathcal O_{\mathrm{kin}}
=\bar h_v (iD_\perp)^2h_v,
$$

and

$$
\mathcal O_{\mathrm{mag}}
=\frac{g_s}{2}\bar h_v\sigma_{\mu\nu}G^{\mu\nu}h_v.
$$

The kinetic operator describes the residual motion of the heavy quark inside the hadron. It breaks heavy-flavor symmetry because its coefficient contains $1/m_Q$, but it does not break spin symmetry.

The chromomagnetic operator describes the coupling of the heavy-quark spin to the gluon field. It breaks spin symmetry and produces hyperfine splittings such as $B^*-B$.

A compact way to remember the hierarchy is

$$
\text{static color source}
\quad+
\frac{\text{recoil}}{m_Q}
\quad+
\frac{\text{chromomagnetic spin coupling}}{m_Q}
\quad+
O\!\left(\frac{1}{m_Q^2}\right).
$$

The coefficient of $\mathcal O_{\mathrm{kin}}$ is fixed to one by reparametrization invariance in standard conventions. The coefficient $C_{\mathrm{mag}}(\mu)$ is a Wilson coefficient determined by matching QCD onto HQET and then running to lower scales.

## Matching and running

HQET is not obtained merely by deleting $m_Q$ from QCD. Hard virtual fluctuations with momenta of order $m_Q$ are not described explicitly in the low-energy theory. Their effects appear in Wilson coefficients.

A typical matching relation for a heavy-light current is

$$
\bar q\,\Gamma Q
= C_\Gamma(\mu)\,\bar q\,\Gamma h_v
+\frac{1}{2m_Q}\sum_i B_i(\mu)\mathcal O_i
+O\!\left(\frac{1}{m_Q^2}\right).
$$

Here $\Gamma$ is a Dirac matrix structure, and the subleading operators include derivatives and chromomagnetic insertions. The matching coefficient $C_\Gamma(\mu)$ is chosen so that QCD and HQET matrix elements agree at a matching scale of order $m_Q$.

Running then evolves the coefficients from $\mu\sim m_Q$ down to hadronic scales:

$$
\mu\frac{d}{d\mu}C_\Gamma(\mu)
=\gamma_\Gamma(\alpha_s)C_\Gamma(\mu).
$$

This separates short-distance logarithms involving $m_Q$ from long-distance hadronic matrix elements. The slogan is

$$
\text{QCD at }m_Q
\quad\xrightarrow{\text{match}}\quad
\text{HQET coefficients}
\quad\xrightarrow{\text{run}}\quad
\text{hadronic matrix elements}.
$$

## Heavy-hadron masses

For a heavy-light hadron $H_Q$, HQET organizes the mass as

$$
M_{H_Q}=m_Q+\bar\Lambda
-\frac{\lambda_1}{2m_Q}
+d_H\frac{\lambda_2}{2m_Q}
+O\!\left(\frac{1}{m_Q^2}\right).
$$

The parameter $\bar\Lambda$ is the energy of the light cloud in the static limit. The matrix element $\lambda_1$ comes from the kinetic operator, while $\lambda_2$ comes from the chromomagnetic operator. The coefficient $d_H$ depends on the spin of the heavy hadron.

Do not over-interpret $m_Q$ in this formula. The heavy-quark mass is not a directly measured pole of an isolated quark. Different short-distance mass schemes organize perturbation theory differently. In precision work, pole-mass renormalon ambiguities are avoided by using short-distance masses.

## Heavy-to-heavy transitions

HQET is especially powerful for transitions such as

$$
B\to D\ell\nu,
\qquad
B\to D^*\ell\nu.
$$

In the heavy-quark limit, the light cloud adjusts to the velocity change of the heavy source. Many form factors are controlled by a single universal function, the Isgur–Wise function $\xi(w)$, where

$$
w=v\cdot v'.
$$

At zero recoil, $v=v'$ and hence $w=1$. Heavy-quark symmetry fixes the normalization

$$
\xi(1)=1
$$

up to perturbative and power corrections. This is not a miracle of a model. It is a statement that, at zero recoil in the static limit, the light cloud is not being shaken into a different state by changing the heavy flavor.

## Inclusive decays and the operator product expansion

HQET also underlies inclusive heavy-hadron decay theory. For sufficiently inclusive observables, one combines HQET with an operator product expansion. The result is an expansion in local heavy-hadron matrix elements:

$$
\Gamma(H_b\to X)
=\Gamma_0
\left[
1+O\!\left(\frac{\Lambda_{\mathrm{QCD}}^2}{m_b^2}\right)
+O\!\left(\frac{\Lambda_{\mathrm{QCD}}^3}{m_b^3}\right)
+\cdots
\right],
$$

where the absence of a generic $1/m_b$ correction is a nontrivial consequence of the absence of an independent gauge-invariant dimension-four operator contributing to total widths.

Inclusive decay theory is delicate near endpoints, where final-state hadrons carry restricted kinematics and new modes appear. Then one usually needs additional EFT structure, such as soft-collinear effective theory.

## Relation to NRQCD and NRQED

HQET is for one heavy quark interacting with light degrees of freedom. It is not the right EFT for a heavy quark and heavy antiquark bound into quarkonium. In quarkonium, both constituents are heavy and nonrelativistic, with momentum and energy scales

$$
p\sim m_Q v,
\qquad
E\sim m_Q v^2.
$$

The appropriate EFTs are NRQCD and, after additional scale separation, potential NRQCD. The analogous electromagnetic EFT for nonrelativistic charged particles is [Nonrelativistic QED](/renormalization-rg-eft/major-efts/nonrelativistic-qed/).

The distinction is worth tattooing on the blackboard:

| System | Good EFT | Expansion |
|---|---|---|
| One heavy quark plus light cloud | HQET | $\Lambda_{\mathrm{QCD}}/m_Q$ |
| Heavy quarkonium | NRQCD or potential NRQCD | velocity $v$ and $\Lambda_{\mathrm{QCD}}/m_Q$ |
| Hydrogenic atoms | NRQED or potential NRQED | $v\sim\alpha$ and $1/m$ |

## What HQET predicts and what it does not

HQET predicts symmetry relations, power-counting structure, and the form of corrections. It does not compute all long-distance hadronic matrix elements by itself. Those matrix elements require experiment, lattice QCD, sum rules, models, or other nonperturbative input.

For example, HQET tells us that many form factors collapse into an Isgur–Wise function in the heavy-quark limit. It does not determine the full function $\xi(w)$ from symmetry alone. It also tells us the allowed subleading operators and their scaling, but the corresponding hadronic matrix elements are nonperturbative.

This is standard EFT behavior. EFTs do not eliminate nonperturbative physics. They isolate it.

## Common pitfalls

**Treating the heavy quark as literally static at all orders.** Static propagation is the leading limit. Recoil and spin interactions enter systematically in powers of $1/m_Q$.

**Forgetting the velocity label.** The field $h_v$ is associated with a chosen velocity sector. Soft gluons cannot change the heavy quark's velocity by an amount of order one.

**Confusing HQET with NRQCD.** HQET describes one heavy quark in a light cloud. Heavy quarkonium requires an EFT with nonrelativistic heavy quark and antiquark fields.

**Using the pole mass carelessly.** The pole mass is intuitive but problematic in precision QCD because of infrared sensitivity. Short-distance mass schemes are usually better for precision work.

**Assuming symmetry fixes everything.** Heavy-quark symmetry fixes normalizations and relations in special limits, but not arbitrary nonperturbative functions away from those limits.

## Relation to other pages

This page is a model example of [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), and [Symmetry Protection](/renormalization-rg-eft/naturalness-power-counting/symmetry-protection/). It also prepares the reader for [Nonrelativistic QED](/renormalization-rg-eft/major-efts/nonrelativistic-qed/), [Nonrelativistic QCD](/renormalization-rg-eft/major-efts/nonrelativistic-qcd/), and [Soft-Collinear Effective Theory](/renormalization-rg-eft/major-efts/soft-collinear-effective-theory/).

## Research status

The leading structure of HQET, heavy-quark spin-flavor symmetry, the $1/m_Q$ expansion, and current matching are standard. Active work concerns precision: high-order perturbative matching, lattice-QCD determinations of matrix elements, inclusive and exclusive heavy-flavor phenomenology, renormalon-free mass definitions, endpoint factorization, and combinations with SCET.

## Exercises

### Exercise 1: Derive the leading static Lagrangian

Starting from

$$
\mathcal L_Q=\bar Q(iD\!\!\!/-m_Q)Q,
$$

write $Q=e^{-im_Qv\cdot x}Q_v$ and $Q_v=h_v+H_v$, with $h_v=P_+Q_v$ and $H_v=P_-Q_v$. Show that the leading low-energy term is $\bar h_v i v\cdot D h_v$.

<details><summary><strong>Solution</strong></summary>

After the phase redefinition,

$$
iD\!\!\!/-m_Q
\longrightarrow
m_Q v\!\!\!/+iD\!\!\!/-m_Q.
$$

Use

$$
P_+v\!\!\!/P_+=P_+,
\qquad
P_-v\!\!\!/P_-=-P_-,
\qquad
P_+\gamma_\perp^\mu P_+=0.
$$

The $h_v$ mass term cancels because $(v\!\!\!/-1)h_v=0$. The $H_v$ component retains a mass gap of order $2m_Q$. The unsuppressed $h_v$ term is therefore

$$
\bar h_v i v\cdot D h_v.
$$

The transverse derivative terms mix $h_v$ and $H_v$ and generate $1/m_Q$ corrections after $H_v$ is eliminated.

</details>

### Exercise 2: Hyperfine scaling

The chromomagnetic operator is suppressed by $1/m_Q$ and has a hadronic matrix element of order $\Lambda_{\mathrm{QCD}}^2$. Estimate the scaling of the pseudoscalar-vector mass splitting in a heavy-light meson doublet.

<details><summary><strong>Solution</strong></summary>

The chromomagnetic contribution to the mass is parametrically

$$
\Delta M_{\mathrm{mag}}
\sim \frac{1}{m_Q}\langle H_Q|\mathcal O_{\mathrm{mag}}|H_Q\rangle
\sim \frac{\Lambda_{\mathrm{QCD}}^2}{m_Q}.
$$

The spin-dependent splitting between the vector and pseudoscalar members of the heavy-quark spin doublet is therefore

$$
M_{H_Q^*}-M_{H_Q}\sim \frac{\Lambda_{\mathrm{QCD}}^2}{m_Q}.
$$

This is why the $B^*-B$ splitting is smaller than the $D^*-D$ splitting.

</details>

### Exercise 3: Why there is no generic first-order correction to inclusive widths

In an inclusive heavy-hadron decay expansion, explain why there is no generic $\Lambda_{\mathrm{QCD}}/m_Q$ correction to the total width.

<details><summary><strong>Solution</strong></summary>

Inclusive widths can be written as forward matrix elements of local operators. The leading operator is

$$
\bar h_v h_v,
$$

with dimension three. A correction of order $1/m_Q$ would require an independent gauge-invariant dimension-four operator. The natural candidate is

$$
\bar h_v i v\cdot D h_v,
$$

but this vanishes by the leading HQET equation of motion inside matrix elements up to contact or higher-order effects. Therefore the first generic nontrivial corrections arise from dimension-five kinetic and chromomagnetic operators, giving order $\Lambda_{\mathrm{QCD}}^2/m_Q^2$ corrections.

</details>

## References

- N. Isgur and M. B. Wise, original papers on heavy-quark symmetry and heavy-to-heavy form-factor relations.
- H. Georgi, original formulation of HQET as an effective field theory for heavy quarks.
- M. Neubert, "Heavy-Quark Symmetry," for a classic review of HQET and heavy-flavor applications.
- A. V. Manohar and M. B. Wise, *Heavy Quark Physics*, for a systematic EFT treatment.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter 35, for a modern QFT-textbook introduction to heavy-quark physics.
- C. P. Burgess, *Introduction to Effective Field Theory*, for the general EFT logic behind matching, decoupling, and power counting.

## Version history

- 2026-06-19: First polished draft. Added the momentum split, field projection, leading static theory, $1/m_Q$ operators, matching and running, heavy-quark symmetry consequences, inclusive-decay OPE comments, pitfalls, exercises, and figure.
