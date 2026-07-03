---
title: "Gauge-Boson Self-Interactions"
description: "Expands the Yang–Mills kinetic term to derive the cubic and quartic gauge-boson self-interactions and their basic momentum-space vertex rules."
sidebar:
  label: "Gauge-Boson Self-Interactions"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§69, 72; Weinberg Vol. II §§15.1–15.2; Schwartz Chs. 25–26; Coleman, Aspects of Symmetry, Secret Symmetry."
topics:
  - gauge-boson self-interactions
  - Yang–Mills Feynman rules
  - three-gluon vertex
  - four-gluon vertex
  - non-Abelian gauge theory
canonicalTopics:
  - gauge-boson-self-interactions
  - three-gauge-boson-vertex
  - four-gauge-boson-vertex
  - yang-mills-feynman-rules
  - non-abelian-self-coupling
researchStatus:
  established:
    - "The cubic and quartic gauge-boson self-interactions follow algebraically from the Yang–Mills kinetic term and are standard perturbative ingredients of non-Abelian gauge theory."
  active:
    - "The gauge-invariant physical meaning of gauge-boson self-interactions in strongly coupled regimes is tied to confinement, mass gaps, Wilson loops, and nonperturbative observables."
---

## Summary

Gauge bosons self-interact in Yang–Mills theory because the non-Abelian field strength is nonlinear. In this volume's convention,

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
$$

the field strength is

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

The Yang–Mills Lagrangian is

$$
\mathcal L_{\mathrm{YM}}
=-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
$$

Because $F_{\mu\nu}^a$ contains a term quadratic in $A_\mu^a$, the kinetic term contains terms cubic and quartic in $A_\mu^a$:

$$
\mathcal L_{\mathrm{YM}}
=
\mathcal L_2+\mathcal L_3+\mathcal L_4.
$$

The cubic term gives the three-gauge-boson vertex. The quartic term gives the four-gauge-boson vertex. These interactions vanish in the Abelian limit $f^{abc}=0$, which is why minimal QED has no elementary photon self-interaction.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Expansion of the Yang–Mills kinetic term into a quadratic gauge-boson term, a cubic three-gauge-boson interaction, and a quartic four-gauge-boson interaction.](/figures/gauge-theories-standard-model/yang-mills-self-interactions.svg)

<figcaption>

The non-Abelian term in $F_{\mu\nu}^a$ turns the pure gauge kinetic term into an interacting theory. The same $-\frac14F^2$ produces the propagating gauge field, the three-gauge-boson vertex proportional to $g f^{abc}$, and the four-gauge-boson vertex proportional to $g^2ff$.

</figcaption>
</figure>

## Prerequisites

You should know the local Yang–Mills setup from [Yang–Mills Action](/gauge-theories-standard-model/yang-mills/yang-mills-action/) and [Non-Abelian Field Strength](/gauge-theories-standard-model/yang-mills/non-abelian-field-strength/). You should also be comfortable with the perturbative rule used in the QED chapter: a local interaction term contributes $i$ times its momentum-space coefficient to the Feynman rule, with all momenta incoming unless otherwise stated.

The page uses generator normalization

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

so that

$$
\mathcal L_{\mathrm{YM}}=-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
$$

## Core idea

The difference between Maxwell theory and Yang–Mills theory is not that Yang–Mills has more gauge bosons. A theory with gauge group $U(1)^k$ has many photons but is still Abelian. The difference is that the non-Abelian generators do not commute:

$$
[T^a,T^b]=if^{abc}T^c.
$$

That one commutator appears in the curvature:

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu].
$$

In components, the commutator is the product $-gf^{abc}A_\mu^bA_\nu^c$. Squaring $F$ in the action inevitably gives

$$
(\partial A)^2,
\qquad
 g(\partial A)AA,
\qquad
 g^2AAAA.
$$

So non-Abelian gauge invariance does not merely allow gauge-boson self-interactions. It demands them.

## Setup and signs

It is useful to split the field strength into a linear Abelian-looking part and a nonlinear part:

$$
f_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a,
\qquad
h_{\mu\nu}^a=f^{abc}A_\mu^bA_\nu^c.
$$

Then, in this volume's convention,

$$
F_{\mu\nu}^a=f_{\mu\nu}^a-gh_{\mu\nu}^a.
$$

The Lagrangian becomes

$$
\mathcal L_{\mathrm{YM}}
=-\frac14(f_{\mu\nu}^a-gh_{\mu\nu}^a)(f^{a\mu\nu}-gh^{a\mu\nu}).
$$

Expanding gives

$$
\mathcal L_{\mathrm{YM}}
=
-\frac14f_{\mu\nu}^af^{a\mu\nu}
+\frac{g}{2}f_{\mu\nu}^ah^{a\mu\nu}
-\frac{g^2}{4}h_{\mu\nu}^ah^{a\mu\nu}.
$$

Thus

$$
\boxed{
\mathcal L_2=-\frac14f_{\mu\nu}^af^{a\mu\nu},
}
$$

$$
\boxed{
\mathcal L_3
=g f^{abc}(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu},
}
$$

and

$$
\boxed{
\mathcal L_4
=-\frac{g^2}{4}f^{abc}f^{ade}
A_\mu^bA_\nu^cA^{d\mu}A^{e\nu}.
}
$$

The cubic expression follows from the antisymmetry of $f_{\mu\nu}^a$ and $h_{\mu\nu}^a$: the two derivative terms in $f_{\mu\nu}^a$ combine into the single compact expression above.

## The cubic interaction

The cubic term is

$$
\mathcal L_3
=g f^{abc}(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu}.
$$

It contains one derivative and three gauge fields. The derivative means the vertex depends on momenta. The structure constant means the vertex vanishes unless the gauge indices participate in a noncommuting part of the Lie algebra.

With all momenta incoming, a convenient three-gauge-boson vertex convention is

$$
A_\mu^a(p)\,A_\nu^b(q)\,A_\rho^c(r):
\qquad
V_{3}^{abc;\mu\nu\rho}(p,q,r),
\qquad
p+q+r=0,
$$

where the vertex factor is

$$
\boxed{
V_{3}^{abc;\mu\nu\rho}(p,q,r)
=
g f^{abc}
\left[
\eta^{\mu\nu}(p-q)^\rho
+\eta^{\nu\rho}(q-r)^\mu
+\eta^{\rho\mu}(r-p)^\nu
\right].
}
$$

There is no analogous elementary three-photon vertex in QED because $f^{abc}=0$ for an Abelian group.

The three-gauge-boson vertex has two signatures worth remembering:

- its color part is antisymmetric, $f^{abc}$;
- its Lorentz part is linear in momenta.

Those two features are tied together by gauge invariance. They are not independent decorations.

## The quartic interaction

The quartic term is

$$
\mathcal L_4
=-\frac{g^2}{4}f^{abc}f^{ade}
A_\mu^bA_\nu^cA^{d\mu}A^{e\nu}.
$$

It contains no derivatives. Its group theory is quadratic in structure constants, so it is sensitive to the non-Abelian algebra even though no momentum appears explicitly.

With all momenta incoming, the four-gauge-boson vertex for external labels

$$
A_\mu^a,
\quad
A_\nu^b,
\quad
A_\rho^c,
\quad
A_\sigma^d
$$

is

$$
\boxed{
\begin{aligned}
V_4^{abcd;\mu\nu\rho\sigma}
=
-ig^2\Big\{&
 f^{eab}f^{ecd}
 (\eta^{\mu\rho}\eta^{\nu\sigma}-\eta^{\mu\sigma}\eta^{\nu\rho})
\\
&+f^{eac}f^{ebd}
 (\eta^{\mu\nu}\eta^{\rho\sigma}-\eta^{\mu\sigma}\eta^{\nu\rho})
\\
&+f^{ead}f^{ebc}
 (\eta^{\mu\nu}\eta^{\rho\sigma}-\eta^{\mu\rho}\eta^{\nu\sigma})
\Big\}.
\end{aligned}
}
$$

Equivalent forms appear in the literature because authors choose different momentum flow, metric signature, covariant-derivative sign, or ordering of external labels. The invariant content is simpler than the displayed formula: the vertex is local, has no momentum dependence, and is built from the three independent ways of pairing four adjoint indices through two structure constants.

:::note[Do not memorize the quartic vertex too early]
The compact Lagrangian $-\frac14F_{\mu\nu}^aF^{a\mu\nu}$ is more important than the expanded four-gauge-boson rule. In serious calculations, derive or import the rule with a fixed convention. The quartic vertex is where casual sign memory goes to get humbled.
:::

## Why gauge bosons carry adjoint charge

The curvature transforms by conjugation:

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U.
$$

Infinitesimally, with $U=1+ig\alpha^aT^a+O(\alpha^2)$,

$$
\delta F_{\mu\nu}^a
=g f^{abc}\alpha^bF_{\mu\nu}^c.
$$

This is the adjoint action of the gauge algebra. The gauge boson quanta associated with $A_\mu^a$ are therefore adjoint-labeled perturbative excitations.

This statement needs a little care. A gauge boson is not a gauge-invariant local particle in the same sense as a scalar particle in a theory with a gauge-invariant field. In perturbation theory around a gauge-fixed vacuum, it is extremely useful to speak of gauge bosons carrying adjoint gauge labels. In a confining theory such as pure Yang–Mills or low-energy QCD, the gauge-invariant spectrum is instead built from color-singlet operators such as glueball operators, Wilson loops, and hadronic composites.

So the safe statement is:

$$
\text{the elementary gauge field transforms in the adjoint local algebra,}
$$

while the physical Hilbert-space interpretation depends on the phase and on the observables being studied.

## A quick comparison with QED

For QED,

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
$$

so

$$
-\frac14F_{\mu\nu}F^{\mu\nu}
$$

is purely quadratic in $A_\mu$. The photon propagates freely until it couples to charged matter. Any photon self-interaction in minimal QED is loop-induced or effective. For example, integrating out the electron at energies below $m_e$ gives Euler–Heisenberg operators such as

$$
\frac{1}{m_e^4}(F_{\mu\nu}F^{\mu\nu})^2,
\qquad
\frac{1}{m_e^4}(F_{\mu\nu}\widetilde F^{\mu\nu})^2.
$$

For Yang–Mills theory, the self-interactions are already present in the renormalizable kinetic term. This is why pure Yang–Mills theory is a genuinely interacting quantum field theory, while pure Maxwell theory is free.

## Product groups and Abelian factors

For a product gauge algebra, self-interactions occur factor by factor. If

$$
\mathfrak g=\mathfrak g_1\oplus\mathfrak g_2\oplus\mathfrak u(1),
$$

then the structure constants vanish between different direct-summand factors. Gauge bosons belonging to different simple factors do not have a cubic vertex with one another from the pure gauge kinetic term.

For the Standard Model gauge algebra,

$$
\mathfrak{su}(3)_c\oplus\mathfrak{su}(2)_L\oplus\mathfrak u(1)_Y,
$$

there are pure self-interactions among the $SU(3)_c$ gluons and among the $SU(2)_L$ weak gauge bosons before electroweak symmetry breaking. There is no elementary pure $U(1)_Y$ self-interaction in the gauge basis. After electroweak symmetry breaking, the physical $W^\pm$, $Z$, and photon are mixtures of the gauge-basis fields, so the familiar electroweak triple and quartic gauge couplings must be read in the broken-phase basis.

## Gauge invariance checks

The cubic and quartic vertices are separately useful but not separately sacred. Gauge invariance relates them. In non-Abelian scattering amplitudes, replacing a polarization vector by its momentum often produces terms that cancel only after diagrams with different topologies are summed.

For example, tree-level gauge-boson scattering receives contributions from exchange diagrams built from two cubic vertices and a contact diagram built from the quartic vertex. The exchange diagrams alone do not have the correct gauge-variation behavior. The quartic vertex is not an optional extra; it is part of the same $F^2$ structure.

This is the non-Abelian analogue of the scalar-QED seagull lesson. In scalar QED, the two-photon scalar contact term is required by gauge invariance. In Yang–Mills theory, the four-gauge-boson vertex is required by gauge invariance.

## Classical nonlinearity

The self-interactions are already visible in the classical equations of motion. Varying the pure Yang–Mills action gives

$$
(D_\mu F^{\mu\nu})^a=0,
$$

or with matter,

$$
(D_\mu F^{\mu\nu})^a=gJ^{a\nu}
$$

up to the current normalization convention. The covariant derivative contains $A_\mu^a$, and $F_{\mu\nu}^a$ contains $AA$, so the equations are nonlinear even when $J^{a\nu}=0$.

This is why Yang–Mills theory has classical waves that interact with each other, nontrivial classical field configurations, and a much richer quantum life than Maxwell theory. The nonlinearity is not a quantum correction. Quantization makes it more dramatic; it does not create it from nothing.

## Common pitfalls

**Thinking self-interaction means gauge bosons are gauge-invariant charged particles.** The perturbative gauge field carries an adjoint label. Physical gauge-invariant states require more care, especially in confining theories.

**Forgetting the quartic vertex.** In gauge-boson scattering, diagrams with two cubic vertices are not enough. The four-gauge-boson contact term is required by the same gauge-invariant kinetic term.

**Importing QED intuition too aggressively.** Minimal QED has no photon self-coupling because $U(1)$ is Abelian. Yang–Mills theory is not “several copies of QED.”

**Mixing sign conventions across books.** If a source uses $D_\mu=\partial_\mu-igA_\mu$ or defines $F_{\mu\nu}^a$ with the opposite commutator sign, the expanded cubic terms and vertex signs change.

**Treating the expanded terms as individually gauge invariant.** The compact object $-\frac14F^2$ is gauge invariant. The pieces $\mathcal L_2$, $\mathcal L_3$, and $\mathcal L_4$ are bookkeeping devices for perturbation theory after a choice of variables.

**Expecting different simple gauge factors to self-mix.** Direct-product factors have independent structure constants. Cross-couplings between gauge factors arise through matter fields charged under both factors, symmetry breaking, kinetic mixing for Abelian factors, or higher-dimension operators, not from the pure non-Abelian kinetic term alone.

## Relations to other pages

This page builds directly on [Non-Abelian Field Strength](/gauge-theories-standard-model/yang-mills/non-abelian-field-strength/) and [Yang–Mills Action](/gauge-theories-standard-model/yang-mills/yang-mills-action/). The previous page, [Covariant Derivative in Representations](/gauge-theories-standard-model/yang-mills/covariant-derivative-in-representations/), explains how gauge bosons couple to matter. This page explains why gauge bosons also couple to themselves.

The quantized version of these interactions appears again in Gauge Quantization, where gauge fixing introduces ghost fields and Slavnov–Taylor identities. The loop consequences appear in Gauge Renormalization, where gauge-boson and ghost loops produce the famous non-Abelian contribution to the beta function. In QCD, these same vertices become the gluon self-interactions responsible for much of the theory's short- and long-distance behavior.

## Research status

The local expansion of the Yang–Mills action and the perturbative three- and four-gauge-boson vertices are established textbook material.

What remains deep is not the existence of these vertices but their consequences. In four-dimensional pure Yang–Mills theory, the same self-interactions are believed to generate a mass gap and confinement, but a fully rigorous proof for the continuum theory remains one of the central mathematical problems in QFT. In phenomenological QCD, gluon self-interactions underlie asymptotic freedom, jets, parton showers, hadronization, glueball spectroscopy, and nonperturbative vacuum structure.

## Exercises

### Exercise 1: Expand the Yang–Mills kinetic term

Starting from

$$
F_{\mu\nu}^a=f_{\mu\nu}^a-gh_{\mu\nu}^a,
\qquad
h_{\mu\nu}^a=f^{abc}A_\mu^bA_\nu^c,
$$

show that

$$
\mathcal L_3=g f^{abc}(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu}
$$

and

$$
\mathcal L_4=-\frac{g^2}{4}f^{abc}f^{ade}A_\mu^bA_\nu^cA^{d\mu}A^{e\nu}.
$$

<details><summary><strong>Solution</strong></summary>

Insert $F=f-gh$ into

$$
\mathcal L=-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
$$

This gives

$$
\mathcal L=-\frac14f_{\mu\nu}^af^{a\mu\nu}
+\frac{g}{2}f_{\mu\nu}^ah^{a\mu\nu}
-\frac{g^2}{4}h_{\mu\nu}^ah^{a\mu\nu}.
$$

The quartic term follows immediately from the definition of $h$.

For the cubic term,

$$
f_{\mu\nu}^ah^{a\mu\nu}
=(\partial_\mu A_\nu^a-\partial_\nu A_\mu^a)f^{abc}A^{b\mu}A^{c\nu}.
$$

Relabel $\mu\leftrightarrow\nu$ in the second term and then use antisymmetry of $f^{abc}$ under $b\leftrightarrow c$. The two terms become equal, so

$$
f_{\mu\nu}^ah^{a\mu\nu}
=2f^{abc}(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu}.
$$

Multiplying by $g/2$ gives the stated $\mathcal L_3$.

</details>

### Exercise 2: Abelian limit

Set $f^{abc}=0$. What remains of $\mathcal L_2$, $\mathcal L_3$, and $\mathcal L_4$?

<details><summary><strong>Solution</strong></summary>

If $f^{abc}=0$, then

$$
h_{\mu\nu}^a=0,
\qquad
F_{\mu\nu}^a=f_{\mu\nu}^a.
$$

Thus

$$
\mathcal L_3=0,
\qquad
\mathcal L_4=0,
$$

and only

$$
\mathcal L_2=-\frac14f_{\mu\nu}^af^{a\mu\nu}
$$

survives. For a single $U(1)$ factor this is Maxwell theory. For $U(1)^k$ it is a sum of free Maxwell kinetic terms, up to possible Abelian kinetic mixing if allowed by the theory's field basis.

</details>

### Exercise 3: Contract the three-gauge-boson vertex

Using the all-incoming three-gauge-boson vertex

$$
V_{3}^{abc;\mu\nu\rho}(p,q,r)
=
g f^{abc}
\left[
\eta^{\mu\nu}(p-q)^\rho
+\eta^{\nu\rho}(q-r)^\mu
+\eta^{\rho\mu}(r-p)^\nu
\right],
$$

with $p+q+r=0$, show that contracting with $p_\mu$ gives the difference of two transverse inverse kinetic operators.

<details><summary><strong>Solution</strong></summary>

A direct contraction gives

$$
\begin{aligned}
p_\mu V_{3}^{abc;\mu\nu\rho}
=gf^{abc}\Big[
&p^\nu(p-q)^\rho
+\eta^{\nu\rho}p\cdot(q-r)
+p^\rho(r-p)^\nu
\Big].
\end{aligned}
$$

Using $p=-(q+r)$, this becomes

$$
p_\mu V_{3}^{abc;\mu\nu\rho}
=gf^{abc}\left[
(r^2\eta^{\nu\rho}-r^\nu r^\rho)
-(q^2\eta^{\nu\rho}-q^\nu q^\rho)
\right].
$$

The bracket is the difference of the transverse inverse kinetic operators for the two adjacent gauge lines. In a gauge-fixed amplitude, such terms cancel neighboring propagators or combine with other diagrams according to the Slavnov–Taylor identities. This is the non-Abelian analogue of the Ward-identity cancellation in QED, with color and additional vertices now along for the ride.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§69 and 72, for non-Abelian gauge theory and the Feynman rules of Yang–Mills theory.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, §§15.1–15.2, for non-Abelian gauge invariance, Yang–Mills Lagrangians, and gauge-field self-couplings.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–26, for Yang–Mills theory, gluon propagators, non-Abelian perturbation theory, and running coupling.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for the conceptual role of gauge fields and non-Abelian gauge symmetry.
- Zee, *Quantum Field Theory in a Nutshell*, Part IV.5 and Part VII.1–VII.3, for a compact physical introduction to non-Abelian gauge theory, quantization, and QCD.

## Version history

- **2026-06-17:** Initial polished draft for the improved Gauge Theories and the Standard Model volume.
