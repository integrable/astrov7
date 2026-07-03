---
title: "QCD Lagrangian"
description: "Defines the QCD Lagrangian in the volume conventions, including quark representations, gluon field strength, gauge fixing, ghosts, the theta term, and the main symmetry checks."
sidebar:
  label: "QCD Lagrangian"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §§69–73 and §§81–83; Schwartz Chs. 25–26 and 32; Weinberg Vol. II Chs. 15–18."
topics:
  - QCD Lagrangian
  - color SU(3)
  - quarks
  - gluons
  - covariant derivative
  - theta term
  - ghosts
canonicalTopics:
  - qcd-lagrangian
  - quantum-chromodynamics
  - gluon-field-strength
  - quark-gluon-coupling
  - qcd-theta-term
researchStatus:
  established:
    - "The local QCD Lagrangian and its perturbative gauge-fixed form are standard consequences of SU(3)c gauge invariance, Lorentz invariance, locality, and the quark field content."
  active:
    - "Many consequences of the same Lagrangian are nonperturbative, including confinement, hadronization, finite-density QCD, and the dynamical origin of the small effective theta angle."
---

## Summary

Quantum chromodynamics is the $SU(3)_c$ gauge theory of quarks and gluons. In the conventions of this volume, the gauge-invariant Lorentzian Lagrangian density without gauge fixing is

$$
\mathcal L_{\rm QCD,inv}
=
-\frac14G_{\mu\nu}^AG^{A\mu\nu}
+
\sum_{f=1}^{n_f}\bar q_f(i\gamma^\mu D_\mu-m_f)q_f
+
\frac{\theta g_s^2}{32\pi^2}G_{\mu\nu}^A\widetilde G^{A\mu\nu}.
$$

Here $q_f$ is a Dirac quark field of flavor $f$ in the fundamental representation $\mathbf 3$ of $SU(3)_c$, $G_\mu^A$ is the gluon field with $A=1,\ldots,8$, and

$$
D_\mu q_f=(\partial_\mu+ig_sG_\mu^AT^A)q_f.
$$

The first term gives gluon propagation and gluon self-interactions. The second gives quark propagation, quark masses, and the quark–gluon vertex. The last term is locally a total derivative, but it is globally physical and leads to the theta-angle and strong CP story.

For perturbative calculations one adds gauge-fixing and ghost terms. In covariant gauges,

$$
\mathcal L_{\rm QCD,pert}
=
\mathcal L_{\rm QCD,inv}
-
\frac{1}{2\xi}(\partial^\mu G_\mu^A)^2
+
(\partial^\mu\bar c^A)(D_\mu c)^A.
$$

The gauge-fixed Lagrangian is not more fundamental than the gauge-invariant one. It is the efficient representation used to compute Green functions, amplitudes, beta functions, and short-distance observables.

<figure class="doc-figure" style="--figure-width: 44rem;">

![The architecture of the QCD Lagrangian: SU(3)c data, quark fields, parameters, gauge-invariant terms, gauge fixing, and ultraviolet/infrared uses.](/figures/gauge-theories-standard-model/qcd-lagrangian-architecture.svg)

<figcaption>

The QCD Lagrangian packages local $SU(3)_c$ gauge structure, quark matter, the coupling $g_s$, quark masses, gauge-fixing data, ghosts, and the optional theta term. Its ultraviolet face is asymptotic freedom; its infrared face is confinement and chiral dynamics.

</figcaption>
</figure>

## Prerequisites

You should know the volume [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/), especially the mostly-minus metric, the Dirac convention $\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}$, the dual tensor convention $\epsilon^{0123}=+1$, and the gauge convention

$$
D_\mu=\partial_\mu+igA_\mu^aT^a.
$$

You should also know [Yang–Mills Action](/gauge-theories-standard-model/yang-mills/yang-mills-action/), [Non-Abelian Field Strength](/gauge-theories-standard-model/yang-mills/non-abelian-field-strength/), [Covariant Derivative in Representations](/gauge-theories-standard-model/yang-mills/covariant-derivative-in-representations/), and [Color and Representations](/gauge-theories-standard-model/yang-mills/color-and-representations/).

For the gauge-fixed form, use [Gauge Fixing and Faddeev–Popov](/gauge-theories-standard-model/gauge-quantization/gauge-fixing-and-faddeev-popov/) and [Ghosts and Gauge-Fixed Action](/gauge-theories-standard-model/gauge-quantization/ghosts-and-gauge-fixed-action/). For the scale dependence, use [Beta Function of Yang–Mills](/gauge-theories-standard-model/gauge-renormalization/beta-function-of-yang-mills/) and [Asymptotic Freedom](/gauge-theories-standard-model/gauge-renormalization/asymptotic-freedom/).

## Core idea

The QCD Lagrangian is the smallest local relativistic Lagrangian for spin-$1$ gauge bosons and spin-$\frac12$ quarks with local $SU(3)_c$ gauge redundancy. Once the gauge group and matter representation are chosen, the leading terms are forced.

The input data are:

| Input | QCD choice | Consequence |
|---|---|---|
| Gauge group | $SU(3)_c$ | Eight gluons in the adjoint representation. |
| Matter representation | Quarks $q_f$ in $\mathbf 3$ | Quarks carry color; antiquarks transform in $\bar{\mathbf 3}$. |
| Locality and Lorentz invariance | Operators of dimension at most four | Gauge kinetic term, quark kinetic term, quark masses, theta term. |
| Coupling convention | $D_\mu=\partial_\mu+ig_sG_\mu^AT^A$ | Fixes signs in $G_{\mu\nu}^A$ and the quark–gluon vertex. |
| Quantization choice | Gauge fixing plus ghosts | Gives invertible propagators and consistent loop calculations. |

This page is deliberately Lagrangian-centered. It does not prove confinement or compute hadron masses. It explains the object from which those harder questions start.

## Setup and conventions

Use fundamental $SU(3)$ generators $T^A$, with

$$
[T^A,T^B]=if^{ABC}T^C,
\qquad
\operatorname{tr}(T^AT^B)=\frac12\delta^{AB}.
$$

Color indices in the fundamental representation are written as $i,j=1,2,3$, while adjoint indices are written as $A,B,C=1,\ldots,8$. A quark flavor $f$ is a Dirac spinor and a color triplet,

$$
q_f(x)=
\begin{pmatrix}
q_f^1(x)\\ q_f^2(x)\\ q_f^3(x)
\end{pmatrix}.
$$

The gluon connection is

$$
G_\mu(x)=G_\mu^A(x)T^A,
$$

and the covariant derivative on a fundamental quark is

$$
D_\mu q_f
=\left(\partial_\mu+ig_sG_\mu^AT^A\right)q_f.
$$

The field strength is defined by

$$
[D_\mu,D_\nu]=ig_sG_{\mu\nu}^AT^A.
$$

Therefore, in this volume’s convention,

$$
G_{\mu\nu}^A
=
\partial_\mu G_\nu^A-
\partial_\nu G_\mu^A
-g_sf^{ABC}G_\mu^BG_\nu^C.
$$

The dual field strength is

$$
\widetilde G^{A\mu\nu}
=
\frac12\epsilon^{\mu\nu\rho\sigma}G_{\rho\sigma}^A,
\qquad
\epsilon^{0123}=+1.
$$

The mass dimensions in four spacetime dimensions are

$$
[G_\mu]=1,
\qquad
[q]=\frac32,
\qquad
[g_s]=0,
\qquad
[m_f]=1,
\qquad
[\theta]=0.
$$

This is why QCD is power-counting renormalizable: the gauge coupling is dimensionless, quark masses are relevant parameters, and the theta term is marginal but topological.

## Gauge-invariant QCD action

Ignoring gauge fixing for the moment, the minimal strong-interaction Lagrangian with diagonal quark masses is

$$
\mathcal L_{\rm QCD,min}
=
-\frac14G_{\mu\nu}^AG^{A\mu\nu}
+
\sum_{f=1}^{n_f}\bar q_f(i\gamma^\mu D_\mu-m_f)q_f.
$$

Equivalently, using a flavor vector $q=(q_1,\ldots,q_{n_f})^T$ and a mass matrix $M_q$, one can write

$$
\mathcal L_{\rm QCD,min}
=
-\frac14G_{\mu\nu}^AG^{A\mu\nu}
+
\bar q(i\gamma^\mu D_\mu-M_q)q.
$$

In a basis where $M_q$ is diagonal and real with positive entries,

$$
M_q=\operatorname{diag}(m_1,m_2,\ldots,m_{n_f}).
$$

Expanding the quark kinetic term gives

$$
\bar q_f i\gamma^\mu D_\mu q_f
=
\bar q_f i\gamma^\mu\partial_\mu q_f
-
g_sG_\mu^A\bar q_f\gamma^\mu T^Aq_f.
$$

Thus the quark–gluon interaction is

$$
\mathcal L_{q\bar qG}
=
-g_sG_\mu^A\bar q_f\gamma^\mu T^Aq_f,
$$

with an implicit sum over $f$ and $A$. In the usual all-momenta-incoming convention, this term gives the quark–gluon vertex proportional to

$$
-ig_s\gamma^\mu T^A.
$$

The gluon kinetic term also contains interactions, because $G_{\mu\nu}^A$ is nonlinear:

$$
-\frac14G_{\mu\nu}^AG^{A\mu\nu}
=
\mathcal L_{GG}
+\mathcal L_{GGG}
+\mathcal L_{GGGG}.
$$

Schematic power counting gives

$$
\mathcal L_{GG}\sim (\partial G)^2,
\qquad
\mathcal L_{GGG}\sim g_s(\partial G)G^2,
\qquad
\mathcal L_{GGGG}\sim g_s^2G^4.
$$

So QCD has gluon self-interactions even before quarks are added. This is the microscopic origin of antiscreening, asymptotic freedom, glueball-like excitations in pure gauge theory, and much of the non-Abelian infrared story.

## Gauge transformations

A local color transformation is a spacetime-dependent matrix

$$
U(x)=\exp\{ig_s\alpha^A(x)T^A\}\in SU(3)_c.
$$

With the volume convention, quarks transform as

$$
q_f\mapsto U^{-1}q_f,
\qquad
\bar q_f\mapsto \bar q_fU.
$$

The gluon connection transforms as

$$
G_\mu\mapsto
U^{-1}G_\mu U-
\frac{i}{g_s}U^{-1}\partial_\mu U.
$$

These laws ensure

$$
D_\mu q_f\mapsto U^{-1}D_\mu q_f,
\qquad
G_{\mu\nu}\mapsto U^{-1}G_{\mu\nu}U.
$$

Therefore

$$
\bar q_f i\gamma^\mu D_\mu q_f
\quad\text{and}\quad
\operatorname{tr}(G_{\mu\nu}G^{\mu\nu})
$$

are gauge invariant. In components,

$$
\operatorname{tr}(G_{\mu\nu}G^{\mu\nu})
=\frac12G_{\mu\nu}^AG^{A\mu\nu},
$$

so

$$
-\frac12\operatorname{tr}(G_{\mu\nu}G^{\mu\nu})
=-\frac14G_{\mu\nu}^AG^{A\mu\nu}.
$$

Gauge invariance is not an ordinary global color symmetry acting on physical isolated colored particles. It is a redundancy in the variables. Gauge-invariant observables are color singlets: traces, closed Wilson loops, hadronic interpolating operators, and suitably dressed or nonlocal objects.

## Gauge fixing and ghosts

The gauge-invariant kinetic operator for $G_\mu^A$ is not invertible because gauge-related fields describe the same physical configuration. Perturbation theory therefore requires gauge fixing. In a covariant gauge,

$$
\mathcal L_{\rm gf}
=-\frac{1}{2\xi}(\partial^\mu G_\mu^A)^2.
$$

The Faddeev–Popov determinant is represented by anticommuting ghost fields $c^A$ and $\bar c^A$ in the adjoint representation. In the convention used earlier in the Gauge Quantization chapter,

$$
\mathcal L_{\rm gh}
=
(\partial^\mu\bar c^A)(D_\mu c)^A,
$$

where the adjoint covariant derivative is

$$
(D_\mu c)^A
=
\partial_\mu c^A-g_sf^{ABC}G_\mu^Bc^C.
$$

Thus

$$
\mathcal L_{\rm gh}
=
(\partial^\mu\bar c^A)(\partial_\mu c^A)
-
g_sf^{ABC}(\partial^\mu\bar c^A)G_\mu^Bc^C.
$$

The ghost interaction is absent in QED because the structure constants vanish. In QCD it is essential. Ghost loops cancel unphysical gauge-polarization effects and make BRST symmetry and unitarity work in covariant gauges.

The complete covariant-gauge perturbative Lagrangian is therefore

$$
\mathcal L_{\rm QCD,pert}
=
-\frac14G_{\mu\nu}^AG^{A\mu\nu}
+
\sum_f\bar q_f(i\gamma^\mu D_\mu-m_f)q_f
-
\frac{1}{2\xi}(\partial^\mu G_\mu^A)^2
+
(\partial^\mu\bar c^A)(D_\mu c)^A
+
\mathcal L_\theta.
$$

The gauge parameter $\xi$ affects gauge-fixed Green functions, not physical gauge-invariant observables.

## The theta term

Four-dimensional non-Abelian gauge theory allows the Lorentz scalar

$$
G_{\mu\nu}^A\widetilde G^{A\mu\nu}.
$$

With the dual convention above, write

$$
\mathcal L_\theta
=
\frac{\theta g_s^2}{32\pi^2}G_{\mu\nu}^A\widetilde G^{A\mu\nu}.
$$

Locally, this term is a total derivative:

$$
G_{\mu\nu}^A\widetilde G^{A\mu\nu}=\partial_\mu K^\mu
$$

for a Chern–Simons current $K^\mu$ that is not itself gauge invariant. This is why $\mathcal L_\theta$ does not change the classical local equations of motion on topologically trivial field configurations with suitable boundary conditions.

Globally, however, the integral

$$
Q=\frac{g_s^2}{32\pi^2}\int d^4x\,G_{\mu\nu}^A\widetilde G^{A\mu\nu}
$$

measures topological winding for finite-action Euclidean configurations. The path integral weights sectors by phases involving $\theta Q$. In QCD with quark masses, axial rotations can shift the theta angle by a phase of the quark mass determinant. The physical CP-violating parameter is therefore a convention-dependent combination usually denoted $\bar\theta$.

This is not a small technical afterthought. The observed absence of large strong CP violation is one of the sharpest conceptual puzzles left by the Standard Model.

## Classical equations and color current

Varying the gauge field gives the Yang–Mills equation with a quark color current:

$$
(D_\mu G^{\mu\nu})^A
=
g_s\sum_f\bar q_f\gamma^\nu T^Aq_f.
$$

The quark equation of motion is

$$
(i\gamma^\mu D_\mu-m_f)q_f=0,
$$

with the conjugate equation for $\bar q_f$. Define

$$
J^{A\nu}=\sum_f\bar q_f\gamma^\nu T^Aq_f.
$$

Then the field equation is

$$
(D_\mu G^{\mu\nu})^A=g_sJ^{A\nu}.
$$

The corresponding conservation statement is covariant:

$$
(D_\nu J^\nu)^A=0
$$

when the equations of motion hold. It is not the ordinary conservation law $\partial_\nu J^{A\nu}=0$. A color index is a gauge-frame index, so the covariant derivative is the natural derivative.

This is a good place to remember the difference between useful variables and physical states. The current above is a local expression in gauge-fixed variables. Physical asymptotic states are color singlets.

## Global symmetries and parameters

With $n_f$ quark flavors and equal treatment by color, QCD has flavor symmetries that depend on the quark mass matrix.

If all quark masses are generic and nonzero, the exact continuous flavor symmetry is a product of conserved quark-number symmetries, modulo the details of weak interactions that are not part of QCD alone. If $n_f$ quarks are massless, the classical QCD Lagrangian has a larger chiral symmetry

$$
U(n_f)_L\times U(n_f)_R.
$$

It is useful to separate this as

$$
SU(n_f)_L\times SU(n_f)_R\times U(1)_V\times U(1)_A.
$$

Here $U(1)_V$ is baryon-number-like quark number. The axial $U(1)_A$ is broken by the quantum anomaly. The non-Abelian chiral symmetry is approximate in the real world because the light quark masses are small but not zero.

At low energies the most important qualitative fact is

$$
SU(n_f)_L\times SU(n_f)_R
\longrightarrow
SU(n_f)_V,
$$

in the massless idealization, signaled by the quark condensate

$$
\langle\bar q q\rangle\ne0.
$$

That statement is not derived from the Lagrangian by weak-coupling expansion. It is an infrared nonperturbative property of QCD.

The independent parameters of QCD, before electroweak unification is considered, are the gauge coupling, the quark masses, and the theta angle:

$$
g_s,
\qquad
m_f,
\qquad
\theta.
$$

After renormalization, $g_s$ becomes scale dependent. One often trades it for $\alpha_s(\mu)$ or for a dimensionful scale $\Lambda_{\rm QCD}$ in a chosen scheme.

## How to read the Lagrangian at different scales

At short distances, the one-loop running has the form

$$
\mu\frac{d g_s}{d\mu}
=-\frac{g_s^3}{16\pi^2}\left(11-\frac23n_f\right)+O(g_s^5)
$$

for $n_f$ active Dirac quark flavors in the fundamental representation. For $n_f\le16$, the one-loop coefficient is positive inside the parentheses, so $g_s$ decreases at high scales. This is asymptotic freedom.

At long distances, perturbation theory in $g_s$ fails. The same Lagrangian then expresses itself through color-singlet hadrons, flux tubes, condensates, pions, glueball-like states in pure gauge theory, and thermal phases. There is no contradiction. A Lagrangian is not a list of particles seen by a detector; it is a microscopic definition of local degrees of freedom and symmetries.

A useful mental split is

$$
\begin{array}{ccl}
\mu\gg \Lambda_{\rm QCD} &:& \text{quarks and gluons are efficient perturbative variables},\\
\mu\sim \Lambda_{\rm QCD} &:& \text{nonperturbative dynamics dominates},\\
\mu\ll \Lambda_{\rm QCD} &:& \text{hadrons and effective fields are efficient variables}.
\end{array}
$$

The rest of the QCD chapter explains these regimes without pretending that one method solves them all.

## Common pitfalls

**Forgetting the sign convention in $G_{\mu\nu}^A$.** With $D_\mu=\partial_\mu+ig_sG_\mu^AT^A$, the nonlinear component term is $-g_sf^{ABC}G_\mu^BG_\nu^C$. Sources using $D_\mu=\partial_\mu-ig_sG_\mu^AT^A$ move this sign elsewhere.

**Calling the gauge-fixed Lagrangian the gauge-invariant Lagrangian.** The gauge-fixing and ghost terms are essential for perturbative quantization, but they are not gauge-invariant physical interactions. They are part of a chosen representation of the gauge-redundant path integral.

**Treating ghosts as new hadrons.** Ghosts are anticommuting scalar fields in the adjoint representation used to represent the Faddeev–Popov determinant. They do not appear as physical asymptotic particles.

**Confusing color $SU(3)_c$ with flavor $SU(3)$.** Color $SU(3)_c$ is gauged and exact in QCD. Approximate flavor $SU(3)$ acts on $u,d,s$ quarks and is broken by their unequal masses. Same group name, very different physics. Tiny notation trap; huge conceptual trap.

**Assuming quark masses are fundamental in the full Standard Model.** In QCD treated alone, $m_f$ are parameters. In the Standard Model, quark masses arise from Yukawa couplings after electroweak symmetry breaking. QCD is often studied with masses inserted because that is the correct low-energy description below the electroweak scale.

**Expecting confinement from one line of the Lagrangian.** The Lagrangian is short. The confinement problem is not. The hard part is the strongly coupled path integral generated by the Lagrangian.

**Ignoring the theta term because it is a total derivative locally.** Local total derivative does not mean globally irrelevant. The theta term is invisible in many perturbative computations but matters for topological sectors and CP.

## Relations to other pages

This page is the direct specialization of [Yang–Mills Action](/gauge-theories-standard-model/yang-mills/yang-mills-action/) and [Covariant Derivative in Representations](/gauge-theories-standard-model/yang-mills/covariant-derivative-in-representations/) to the gauge group $SU(3)_c$ with fundamental Dirac matter.

It relies on [Gauge-Boson Self-Interactions](/gauge-theories-standard-model/yang-mills/gauge-boson-self-interactions/) for the origin of three- and four-gluon vertices, and on [Ghosts and Gauge-Fixed Action](/gauge-theories-standard-model/gauge-quantization/ghosts-and-gauge-fixed-action/) for the covariant-gauge ghost sector.

It prepares the later QCD pages on Color SU(3), Quarks and Gluons, QCD Beta Function, Running Alpha s, Chiral Symmetry in QCD, Confinement in QCD, and the Theta Angle and Strong CP Problem.

It also prepares the Standard Model field-content page. In the full Standard Model, quarks carry color, weak isospin, hypercharge, flavor labels, and chirality-dependent electroweak representations. This page isolates the color part before the electroweak complications arrive.

## Research status

The local Lagrangian formulation of QCD is established. The gauge group, field content, covariant derivative, field strength, gauge-fixed perturbative action, BRST structure, and beta-function expansion are standard material.

The physical consequences of the Lagrangian include both settled and active topics. Asymptotic freedom is perturbatively controlled and experimentally central. Many hadron properties are computed nonperturbatively with lattice QCD. But confinement as a continuum mathematical theorem, real-time hadronization, finite-density QCD, topological fluctuations, and the strong CP problem remain deep research areas.

The honest slogan is: the Lagrangian is simple; the measure is hard.

## Exercises

### Exercise 1: Field strength sign check

Starting from

$$
D_\mu=\partial_\mu+ig_sG_\mu^AT^A,
\qquad
[T^A,T^B]=if^{ABC}T^C,
$$

show that $[D_\mu,D_\nu]=ig_sG_{\mu\nu}^AT^A$ gives

$$
G_{\mu\nu}^A
=
\partial_\mu G_\nu^A-
\partial_\nu G_\mu^A
-g_sf^{ABC}G_\mu^BG_\nu^C.
$$

<details><summary><strong>Solution</strong></summary>

Compute the commutator on a fundamental field:

$$
[D_\mu,D_\nu]
=ig_s(\partial_\mu G_\nu-\partial_\nu G_\mu)
+(ig_s)^2[G_\mu,G_\nu].
$$

Now

$$
[G_\mu,G_\nu]
=G_\mu^BG_\nu^C[T^B,T^C]
=i f^{BCD}G_\mu^BG_\nu^CT^D.
$$

Therefore

$$
(ig_s)^2[G_\mu,G_\nu]
=-g_s^2 i f^{BCD}G_\mu^BG_\nu^CT^D.
$$

Factor out $ig_s$:

$$
[D_\mu,D_\nu]
=ig_s\left(\partial_\mu G_\nu^A-\partial_\nu G_\mu^A-g_sf^{BCA}G_\mu^BG_\nu^C\right)T^A.
$$

Relabeling dummy indices gives the stated formula.

</details>

### Exercise 2: Quark–gluon interaction term

Expand

$$
\bar q(i\gamma^\mu D_\mu-m)q
$$

using $D_\mu=\partial_\mu+ig_sG_\mu^AT^A$. Identify the interaction term and the corresponding vertex factor in the usual all-momenta-incoming convention.

<details><summary><strong>Solution</strong></summary>

Substitute the covariant derivative:

$$
\bar q i\gamma^\mu D_\mu q
=
\bar q i\gamma^\mu\partial_\mu q
+
\bar q i\gamma^\mu(ig_sG_\mu^AT^A)q.
$$

Since $i\cdot i=-1$,

$$
\bar q i\gamma^\mu D_\mu q
=
\bar q i\gamma^\mu\partial_\mu q
-g_sG_\mu^A\bar q\gamma^\mu T^Aq.
$$

Thus

$$
\mathcal L_{q\bar qG}
=-g_sG_\mu^A\bar q\gamma^\mu T^Aq.
$$

Multiplying by $i$ in the perturbative expansion gives the vertex factor

$$
-ig_s\gamma^\mu T^A,
$$

with color indices carried by the matrix $T^A$.

</details>

### Exercise 3: Gauge invariance of the gluon kinetic term

Use

$$
G_{\mu\nu}\mapsto U^{-1}G_{\mu\nu}U
$$

and cyclicity of the trace to show that $\operatorname{tr}(G_{\mu\nu}G^{\mu\nu})$ is gauge invariant.

<details><summary><strong>Solution</strong></summary>

Under the gauge transformation,

$$
\operatorname{tr}(G_{\mu\nu}G^{\mu\nu})
\mapsto
\operatorname{tr}(U^{-1}G_{\mu\nu}UU^{-1}G^{\mu\nu}U).
$$

The adjacent $UU^{-1}$ cancels, leaving

$$
\operatorname{tr}(U^{-1}G_{\mu\nu}G^{\mu\nu}U).
$$

By cyclicity of the trace,

$$
\operatorname{tr}(U^{-1}G_{\mu\nu}G^{\mu\nu}U)
=
\operatorname{tr}(G_{\mu\nu}G^{\mu\nu}UU^{-1})
=
\operatorname{tr}(G_{\mu\nu}G^{\mu\nu}).
$$

Hence the gluon kinetic term is gauge invariant.

</details>

### Exercise 4: Covariant conservation

Assume the Yang–Mills equation with quark current,

$$
(D_\mu G^{\mu\nu})^A=g_sJ^{A\nu}.
$$

Explain why the natural conservation equation is covariant rather than ordinary.

<details><summary><strong>Solution</strong></summary>

The current $J^{A\nu}$ has an adjoint color index. Under a local gauge transformation, this index rotates by the adjoint action. Therefore $\partial_\nu J^{A\nu}$ is not a gauge-covariant expression by itself; it differentiates a vector whose internal frame changes from point to point.

The adjoint covariant derivative corrects for the changing color frame:

$$
(D_\nu J^\nu)^A
=
\partial_\nu J^{A\nu}-g_sf^{ABC}G_\nu^BJ^{C\nu}.
$$

Using the matter equations of motion, the Yang–Mills equation implies

$$
(D_\nu J^\nu)^A=0.
$$

That is the gauge-covariant conservation law.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§69–73 for non-Abelian gauge theory and §§81–83 for QCD scattering, Wilson loops, and chiral symmetry breaking.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–26 and 32, for Yang–Mills theory, quantum Yang–Mills, QCD running, and parton-model applications.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Chs. 15–18, for non-Abelian gauge theory, BRST/Faddeev–Popov quantization, gauge-theory renormalization, and RG methods.

### Deeper references

- Coleman, *Aspects of Symmetry*, for gauge fields, instantons, large-$N$ methods, and symmetry lessons that feed directly into QCD.
- Polyakov, *Gauge Fields and Strings*, for strong-coupling expansions, confinement criteria, loop dynamics, and the nonperturbative gauge-theory viewpoint.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*, for standard QCD Feynman rules and perturbative examples.
- Manohar and Wise, *Heavy Quark Physics*, for heavy-quark effective theory as a controlled low-energy expansion of QCD.

## Version history

- **2026-06-18:** Initial polished draft. Fixed the QCD Lagrangian, field-strength sign, quark–gluon vertex sign, ghost convention, theta-term convention, and the Lagrangian architecture figure.
