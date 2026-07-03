---
title: "QCD Beta Function"
description: "Derives and interprets the perturbative beta function of QCD, including the group-theory coefficients, active quark flavors, and the origin of asymptotic freedom."
sidebar:
  label: "QCD Beta Function"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §§73 and 81–83; Schwartz Ch. 26; Weinberg Vol. II Chs. 17–18; Coleman, Aspects of Symmetry, Ch. 5."
topics:
  - QCD beta function
  - asymptotic freedom
  - non-Abelian gauge theory
  - quark screening
  - gluon anti-screening
  - renormalization group
canonicalTopics:
  - qcd-beta-function
  - asymptotic-freedom
  - yang-mills-beta-function
  - strong-coupling-running
  - renormalization-group
researchStatus:
  established:
    - "The first two perturbative coefficients of the QCD beta function are universal and imply ultraviolet asymptotic freedom for QCD with the physical number of quark flavors."
  active:
    - "The strongly coupled infrared regime, the conformal-window boundary for many-flavor gauge theories, and scheme-independent information away from weak coupling remain active research areas."
---

## Summary

The QCD beta function describes how the strong coupling changes with the renormalization scale. With

$$
\alpha_s\equiv \frac{g_s^2}{4\pi},
$$

the perturbative beta function is conventionally written

$$
\beta_{g_s}(g_s)
\equiv
\mu\frac{dg_s}{d\mu}
=
-\frac{b_0}{16\pi^2}g_s^3
-\frac{b_1}{(16\pi^2)^2}g_s^5
+O(g_s^7).
$$

For QCD with gauge group $SU(3)_c$ and $n_f$ active Dirac quark flavors in the fundamental representation,

$$
b_0=11-\frac23 n_f,
\qquad
b_1=102-\frac{38}{3}n_f.
$$

The minus sign is the famous part. For ordinary QCD, $n_f\le 6$, so $b_0>0$ and the weak-coupling beta function is negative. The strong coupling decreases at high energy and short distance. This is asymptotic freedom.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Diagrammatic balance behind the QCD one-loop beta function: gluon and ghost loops anti-screen color while quark loops screen color.](/figures/gauge-theories-standard-model/qcd-beta-function-balance.svg)

<figcaption>

At one loop, QCD running is a competition between gluon/ghost anti-screening and quark screening. The non-Abelian self-interactions of the gluon dominate for ordinary QCD, giving $b_0=11-\frac23 n_f$ and hence $\beta_{g_s}<0$ at weak coupling.

</figcaption>
</figure>

## Prerequisites

You should know [QCD Lagrangian](/gauge-theories-standard-model/qcd/qcd-lagrangian/), [Color SU(3)](/gauge-theories-standard-model/qcd/color-su3/), and [Quarks and Gluons](/gauge-theories-standard-model/qcd/quarks-and-gluons/). This page uses the QCD covariant derivative

$$
D_\mu q_f=(\partial_\mu+ig_sG_\mu^AT^A)q_f,
$$

with fundamental generators normalized by

$$
\operatorname{tr}(T^AT^B)=\frac12\delta^{AB}.
$$

You should also know the general [Beta Function of Yang–Mills](/gauge-theories-standard-model/gauge-renormalization/beta-function-of-yang-mills/) and [Asymptotic Freedom](/gauge-theories-standard-model/gauge-renormalization/asymptotic-freedom/) pages. This page specializes those results to the physical $SU(3)_c$ theory with quarks in the fundamental representation.

## Core idea

A beta function measures how a coupling changes when the renormalization scale changes. In QCD, the coupling changes because quantum fluctuations polarize the vacuum around a color source.

The surprise is that non-Abelian gauge bosons polarize the vacuum with the opposite sign from charged matter. Fermion loops screen color charge, in the same broad sense that electron–positron loops screen electric charge in QED. Gluon and ghost loops anti-screen color. In QCD the anti-screening contribution wins.

This is the structural reason QCD has two very different faces:

$$
\text{large }\mu:
\quad
\alpha_s(\mu)\ll1,
\quad
\text{quarks and gluons are perturbative partons},
$$

while

$$
\text{small }\mu:
\quad
\alpha_s(\mu)\text{ grows},
\quad
\text{confinement and chiral dynamics take over}.
$$

The beta function is not a proof of confinement. It is the ultraviolet half of the QCD story: it tells us why weak-coupling calculations become better at shorter distances and why a dimensionless classical coupling is traded for a scale.

## Setup and conventions

The minimal QCD Lagrangian for $n_f$ active quark flavors is

$$
\mathcal L_{\rm QCD,min}
=
-\frac14G_{\mu\nu}^AG^{A\mu\nu}
+
\sum_{f=1}^{n_f}\bar q_f(i\gamma^\mu D_\mu-m_f)q_f.
$$

The field strength convention is

$$
G_{\mu\nu}^A
=
\partial_\mu G_\nu^A
-
\partial_\nu G_\mu^A
-g_sf^{ABC}G_\mu^BG_\nu^C.
$$

The group-theory factors are defined by

$$
f^{ACD}f^{BCD}=C_A\delta^{AB},
$$

$$
\operatorname{tr}_R(T_R^AT_R^B)=T_R\delta^{AB},
$$

and

$$
T_R^AT_R^A=C_R\mathbf 1_R.
$$

For $SU(N)$ with fundamental quarks,

$$
C_A=N,
\qquad
T_F=\frac12,
\qquad
C_F=\frac{N^2-1}{2N}.
$$

For QCD,

$$
C_A=3,
\qquad
T_F=\frac12,
\qquad
C_F=\frac43.
$$

The number $n_f$ in the perturbative beta function is the number of **active** Dirac quark flavors at the scale of interest. It is not always the total number of quark species in the Standard Model. Heavy quarks are integrated in or out depending on the scale and the chosen effective description.

## Definition of the beta function

The renormalized coupling $g_s(\mu)$ depends on the arbitrary renormalization scale $\mu$. The beta function is

$$
\beta_{g_s}(g_s)
=
\mu\frac{dg_s}{d\mu}
$$

with bare parameters held fixed. In dimensional regularization, one often works in $d=4-2\epsilon$ and writes schematically

$$
g_{s,0}=\mu^\epsilon Z_g(g_s,\epsilon)g_s.
$$

The bare coupling $g_{s,0}$ does not depend on $\mu$. Differentiating this statement gives the beta function. In minimal-subtraction schemes, the beta function is determined by the pole terms in the renormalization constants.

There are several equivalent ways to extract the same result:

| Method | What is computed | Why it works |
|---|---|---|
| Vertex and field renormalization | $Z_g$ from gauge, ghost, and quark Green functions | Slavnov–Taylor identities relate the allowed counterterms. |
| Background-field gauge | The background gluon two-point function | Background gauge invariance gives a direct relation between coupling and background-field renormalization. |
| Effective action | The coefficient of $G_{\mu\nu}^AG^{A\mu\nu}$ | Gauge invariance forces the divergent local term to have Yang–Mills form. |
| Physical short-distance observable | A chosen definition of a strong effective charge | The same universal first coefficients appear after translating conventions. |

The separate Feynman diagrams can be gauge dependent. The coefficients $b_0$ and $b_1$ are not.

## One-loop result

For a general non-Abelian gauge theory with $n_f$ Dirac fermions in representation $R$, the one-loop coefficient is

$$
b_0
=
\frac{11}{3}C_A
-
\frac{4}{3}T_Rn_f.
$$

For QCD, $R$ is the fundamental representation of $SU(3)$, so $T_R=T_F=1/2$. Hence

$$
b_0
=
\frac{11}{3}\cdot 3
-
\frac{4}{3}\cdot\frac12 n_f
=
11-\frac23n_f.
$$

Therefore

$$
\beta_{g_s}(g_s)
=
-\frac{g_s^3}{16\pi^2}\left(11-\frac23n_f\right)+O(g_s^5).
$$

The condition for asymptotic freedom at one loop is

$$
b_0>0.
$$

For $SU(3)$ fundamental quarks this gives

$$
11-\frac23n_f>0
\qquad\Longleftrightarrow\qquad
n_f<\frac{33}{2}.
$$

Since $n_f$ is an integer, asymptotic freedom holds for $n_f\le16$. Real QCD has at most six quark flavors, so it is safely asymptotically free.

## What screens and what anti-screens

The one-loop coefficient can be read as

$$
b_0
=
\underbrace{\frac{11}{3}C_A}_{\text{gluon and ghost anti-screening}}
-
\underbrace{\frac{4}{3}T_Fn_f}_{\text{quark screening}}.
$$

The quark term has the same qualitative sign as charged matter in QED: virtual quark–antiquark pairs screen an external color source. If this were the whole story, the coupling would grow at short distances rather than shrink.

The gluon term is special to non-Abelian gauge theory. Gluons carry color charge, and their self-interactions are forced by gauge invariance. The associated gauge and ghost fluctuations produce anti-screening. The ghost contribution is not optional bookkeeping; in covariant gauges it is part of the gauge-invariant answer.

One should not picture this as a literal dielectric medium with colored particles sitting in the vacuum. That picture is good for memory and bad for precision. The precise statement is the renormalization-group equation above.

## Two-loop coefficient

The two-loop coefficient for $n_f$ Dirac quarks in the fundamental representation of $SU(N)$ is

$$
b_1
=
\frac{34}{3}C_A^2
-
\frac{20}{3}C_AT_Fn_f
-4C_FT_Fn_f.
$$

For $SU(3)$, this becomes

$$
b_1
=
\frac{34}{3}\cdot 9
-
\frac{20}{3}\cdot 3\cdot\frac12 n_f
-4\cdot\frac43\cdot\frac12 n_f,
$$

so

$$
b_1=102-\frac{38}{3}n_f.
$$

The first two coefficients are universal in the usual sense: they are independent of the renormalization scheme under ordinary analytic redefinitions of a single coupling. Higher-loop coefficients depend on the scheme, though they are of course meaningful once the scheme is specified.

For physical values $n_f\le6$, both $b_0$ and $b_1$ are positive. Thus the first two terms both push $g_s$ downward in the ultraviolet. For larger $n_f$, the two-loop coefficient can change sign while $b_0$ remains positive. This is the perturbative hint behind Banks–Zaks fixed points and the broader conformal-window problem, but that is not ordinary low-flavor QCD.

## Beta function for alpha s

Because phenomenology usually uses

$$
\alpha_s=\frac{g_s^2}{4\pi},
$$

it is useful to translate the beta function. Differentiating gives

$$
\mu\frac{d\alpha_s}{d\mu}
=
\frac{g_s}{2\pi}\mu\frac{dg_s}{d\mu}.
$$

Therefore

$$
\mu\frac{d\alpha_s}{d\mu}
=
-
\frac{b_0}{2\pi}\alpha_s^2
-
\frac{b_1}{8\pi^2}\alpha_s^3
+O(\alpha_s^4).
$$

At one loop, the right-hand side is negative whenever $b_0>0$. Thus $\alpha_s$ decreases as $\mu$ increases.

The one-loop solution is

$$
\frac{1}{\alpha_s(\mu)}
=
\frac{1}{\alpha_s(\mu_0)}
+
\frac{b_0}{2\pi}\ln\frac{\mu}{\mu_0}.
$$

Equivalently,

$$
\alpha_s(\mu)
=
\frac{4\pi}{b_0\ln(\mu^2/\Lambda^2)},
$$

where $\Lambda$ is an integration constant. The next page explains how to use this formula without turning it into folklore soup.

## Relation to dimensional transmutation

Classically, massless QCD has a dimensionless coupling and no built-in mass scale. Quantum mechanically, renormalization introduces the scale $\mu$, and the RG equation lets us trade $g_s(\mu)$ for an RG-invariant scale.

At one loop,

$$
\Lambda
=
\mu\exp\left[-\frac{2\pi}{b_0\alpha_s(\mu)}\right].
$$

This is dimensional transmutation. A dimensionless coupling has become a dimensionful scale. In QCD, this scale is the rough origin of hadron masses, string tensions, and condensates, although precise infrared quantities require nonperturbative definitions and calculations.

The exponential form is worth staring at. A moderately small coupling at high energy can generate a much lower strong scale. That is not a bug; it is the RG doing physics.

## What is actually universal

The phrase “the QCD beta function” is sometimes used too loosely. Here is the careful version.

| Statement | Status |
|---|---|
| The sign of the one-loop coefficient in QCD is negative for $\beta_{g_s}$ at weak coupling. | Universal perturbative fact. |
| $b_0=11-\frac23n_f$ for $SU(3)$ with $n_f$ fundamental Dirac quarks. | Universal one-loop result. |
| $b_1=102-\frac{38}{3}n_f$ in the same theory. | Universal two-loop result. |
| Three-loop and higher coefficients. | Scheme-dependent, though standard in schemes such as $\overline{\rm MS}$. |
| The exact beta function at strong coupling. | Not known in ordinary QCD. |
| The fact that real QCD confines. | Strongly supported by lattice gauge theory and physics evidence, but not derived from the perturbative beta function alone. |

Asymptotic freedom is a weak-coupling ultraviolet statement. Confinement is an infrared nonperturbative statement. The two are deeply connected in QCD, but they are not the same theorem.

## Common pitfalls

**Forgetting the overall minus sign.** In the convention of this page,

$$
\beta_{g_s}=-\frac{b_0}{16\pi^2}g_s^3+\cdots.
$$

Positive $b_0$ means the coupling decreases in the ultraviolet.

**Calling every quark flavor active at every scale.** The $n_f$ in the running coupling is the number of active flavors in the effective theory at the scale being used. Heavy quarks are matched across thresholds.

**Thinking ghosts cause asymptotic freedom by themselves.** Ghosts are part of the covariant-gauge calculation. The physical statement is non-Abelian gauge anti-screening, encoded in the gauge-invariant coefficient $\frac{11}{3}C_A$.

**Treating the beta function as a confinement proof.** The beta function tells us the coupling grows toward the infrared. It does not by itself prove a mass gap, an area law, or the absence of colored asymptotic states.

**Comparing coefficients without checking generator normalization.** The standard QCD formula assumes $\operatorname{tr}(T^AT^B)=\frac12\delta^{AB}$. Different normalizations move factors between $g_s$, $T^A$, and the coefficients.

**Confusing scheme dependence with arbitrariness.** Higher-loop coefficients depend on the renormalization scheme, but physical observables do not when computed consistently to all orders. At finite order, residual scheme and scale dependence estimate missing higher-order information.

## Relations to other pages

This page specializes [Beta Function of Yang–Mills](/gauge-theories-standard-model/gauge-renormalization/beta-function-of-yang-mills/) to $SU(3)_c$ with fundamental quarks. It prepares [Running Alpha s](/gauge-theories-standard-model/qcd/running-alpha-s/), where the beta function is solved and used as a practical coupling.

It also feeds into later QCD pages. [Chiral Symmetry in QCD](/gauge-theories-standard-model/qcd/chiral-symmetry-in-qcd/) starts from the same Lagrangian but asks about flavor. [Confinement in QCD](/gauge-theories-standard-model/qcd/confinement-in-qcd/) asks what happens after the running coupling leaves perturbative control. [Theta Angle and Strong CP Problem](/gauge-theories-standard-model/qcd/theta-angle-and-strong-cp-problem/) adds the topological term that ordinary perturbative beta-function calculations do not see.

## Research status

The perturbative beta function of QCD is established textbook physics. The one-loop and two-loop coefficients are universal. Higher-loop coefficients have been computed in standard schemes and are essential for precision QCD, but the coefficients themselves are scheme-dependent beyond two loops.

The frontier begins when one asks what the beta function means away from weak coupling. Many-flavor gauge theories may have infrared fixed points; locating the conformal window is a mixture of perturbation theory, lattice gauge theory, and nonperturbative reasoning. Ordinary low-flavor QCD is strongly coupled in the infrared, and its confinement, chiral symmetry breaking, and hadronization are not solved by perturbative running alone.

## Exercises

### Asymptotic freedom bound

For an $SU(N)$ gauge theory with $n_f$ Dirac fermions in the fundamental representation, derive the one-loop condition for asymptotic freedom.

<details><summary><strong>Solution</strong></summary>

For fundamental fermions,

$$
C_A=N,
\qquad
T_F=\frac12.
$$

The one-loop coefficient is

$$
b_0=\frac{11}{3}N-\frac{4}{3}\frac12 n_f
=\frac{11}{3}N-\frac{2}{3}n_f.
$$

Asymptotic freedom requires $b_0>0$, so

$$
\frac{11}{3}N-\frac{2}{3}n_f>0
\qquad\Longleftrightarrow\qquad
n_f<\frac{11}{2}N.
$$

For $SU(3)$ this gives $n_f<33/2$, hence $n_f\le16$ for integer $n_f$.

</details>

### Convert the beta function to alpha s

Starting from

$$
\mu\frac{dg_s}{d\mu}
=
-\frac{b_0}{16\pi^2}g_s^3
-\frac{b_1}{(16\pi^2)^2}g_s^5+O(g_s^7),
$$

show that

$$
\mu\frac{d\alpha_s}{d\mu}
=
-\frac{b_0}{2\pi}\alpha_s^2
-\frac{b_1}{8\pi^2}\alpha_s^3+O(\alpha_s^4).
$$

<details><summary><strong>Solution</strong></summary>

Use $\alpha_s=g_s^2/(4\pi)$. Then

$$
\mu\frac{d\alpha_s}{d\mu}
=
\frac{g_s}{2\pi}\mu\frac{dg_s}{d\mu}.
$$

The first term gives

$$
\frac{g_s}{2\pi}\left(-\frac{b_0}{16\pi^2}g_s^3\right)
=
-\frac{b_0g_s^4}{32\pi^3}
=
-\frac{b_0}{32\pi^3}(4\pi\alpha_s)^2
=
-\frac{b_0}{2\pi}\alpha_s^2.
$$

The second term gives

$$
\frac{g_s}{2\pi}\left(-\frac{b_1}{(16\pi^2)^2}g_s^5\right)
=
-\frac{b_1g_s^6}{512\pi^5}
=
-\frac{b_1}{512\pi^5}(4\pi\alpha_s)^3
=
-\frac{b_1}{8\pi^2}\alpha_s^3.
$$

</details>

### Two-loop coefficient for SU(3)

Use

$$
b_1
=
\frac{34}{3}C_A^2
-
\frac{20}{3}C_AT_Fn_f
-4C_FT_Fn_f
$$

and the $SU(3)$ values $C_A=3$, $T_F=1/2$, $C_F=4/3$ to obtain $b_1=102-\frac{38}{3}n_f$.

<details><summary><strong>Solution</strong></summary>

Substitute the group factors:

$$
\frac{34}{3}C_A^2=\frac{34}{3}\cdot9=102,
$$

$$
\frac{20}{3}C_AT_Fn_f
=
\frac{20}{3}\cdot3\cdot\frac12 n_f
=10n_f,
$$

and

$$
4C_FT_Fn_f
=4\cdot\frac43\cdot\frac12 n_f
=\frac83n_f.
$$

Therefore

$$
b_1=102-10n_f-\frac83n_f
=102-\frac{38}{3}n_f.
$$

</details>

## References

- Srednicki, *Quantum Field Theory*, §§73 and 81–83, for the non-Abelian beta function and QCD applications.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 26, for quantum Yang–Mills theory, vacuum polarization, renormalization, and the running coupling.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Chs. 17–18, for renormalization of gauge theories and RG methods.
- Coleman, *Aspects of Symmetry*, lecture 5, for the classic physical discussion of gauge fields and asymptotic freedom.
- Gross and Wilczek, “Ultraviolet Behavior of Non-Abelian Gauge Theories,” and Politzer, “Reliable Perturbative Results for Strong Interactions,” for the original asymptotic-freedom papers.

## Version history

- **2026-06-18:** Initial page. Added the QCD beta-function coefficients, group-theory conventions, physical interpretation, exercises, and a beta-function balance figure.
