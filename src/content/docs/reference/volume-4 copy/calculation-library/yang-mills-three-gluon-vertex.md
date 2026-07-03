---
title: "Yang–Mills Three-Gluon Vertex"
description: "Derives the three-gauge-boson vertex from the Yang–Mills kinetic term, including the sign convention, all-incoming momentum rule, Bose-symmetry check, and Ward-identity contraction."
sidebar:
  label: "Yang–Mills Three-Gluon Vertex"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §§69, 72; Schwartz Chs. 25–26; Weinberg Vol. II §§15.1–15.2."
topics:
  - Yang–Mills theory
  - three-gluon vertex
  - gauge-boson self-interactions
  - Feynman rules
  - non-Abelian gauge theory
canonicalTopics:
  - yang-mills-three-gluon-vertex
  - three-gauge-boson-vertex
  - non-abelian-feynman-rules
  - gauge-boson-self-interactions
researchStatus:
  established:
    - "The three-gauge-boson vertex is a standard tree-level consequence of the Yang–Mills kinetic term."
  active:
    - "Its use inside amplitudes, loop calculations, and nonperturbative gauge dynamics requires gauge fixing, Slavnov–Taylor identities, and gauge-invariant observables."
---

## Summary

This page derives the cubic gauge-boson interaction and the corresponding all-incoming three-gauge-boson vertex. In this volume's convention,

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
$$

so

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

The Yang–Mills kinetic term

$$
\mathcal L_{\mathrm{YM}}
=-\frac14F_{\mu\nu}^aF^{a\mu\nu}
$$

contains the cubic interaction

$$
\mathcal L_3
=
g f^{abc}(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu}.
$$

With all momenta incoming,

$$
A_\mu^a(p),\qquad A_\nu^b(q),\qquad A_\rho^c(r),
\qquad p+q+r=0,
$$

the vertex factor used in this volume is

$$
V_3^{abc;\mu\nu\rho}(p,q,r)
=
g f^{abc}
\left[
\eta^{\mu\nu}(p-q)^\rho
+\eta^{\nu\rho}(q-r)^\mu
+\eta^{\rho\mu}(r-p)^\nu
\right].
$$

<figure class="doc-figure" style="--figure-width: 46rem;">

![Derivation flow for the Yang–Mills three-gluon vertex](/figures/gauge-theories-standard-model/yang-mills-three-gluon-vertex-flow.svg)

<figcaption>

The cubic vertex is the cross term between the linear and nonlinear parts of $F_{\mu\nu}^a$. The derivative in $f_{\mu\nu}^a$ becomes a momentum, while the structure constant records the noncommutativity of the gauge algebra.

</figcaption>
</figure>

The formula is easy to quote and weirdly easy to mis-sign. The safest memory is not the vertex itself, but its origin:

$$
-\frac14(f-gh)^2
\quad\Longrightarrow\quad
+\frac{g}{2}f\cdot h.
$$

That cross term is the whole story.

## What is being calculated

The three-gauge-boson vertex is the perturbative rule obtained from the cubic part of the pure Yang–Mills action. It is not a new independent interaction added by hand. Gauge invariance fixes it once the kinetic term is

$$
-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
$$

This page calculates three things:

| Object | Result | Why it matters |
|---|---|---|
| cubic Lagrangian term | $\mathcal L_3=g f^{abc}(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu}$ | The local source of the three-gauge-boson interaction. |
| momentum-space rule | $V_3^{abc;\mu\nu\rho}(p,q,r)$ | The rule used in tree diagrams and loop diagrams. |
| contraction check | $p_\mu V_3^{\mu\nu\rho}$ | The local algebra behind Slavnov–Taylor cancellations. |

The page does not derive a full scattering amplitude. For a physical amplitude, this vertex must be combined with propagators, external polarizations, gauge fixing, ghosts at loop level, and the other Yang–Mills vertices.

## Setup and Fourier convention

Split the field strength into a linear part and a nonlinear part:

$$
f_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a,
\qquad
h_{\mu\nu}^a
=f^{abc}A_\mu^bA_\nu^c.
$$

Then

$$
F_{\mu\nu}^a=f_{\mu\nu}^a-gh_{\mu\nu}^a.
$$

For the momentum-space derivation below, use

$$
A_\mu^a(x)=\int\frac{d^4p}{(2\pi)^4}
\,e^{ip\cdot x}A_\mu^a(p).
$$

Thus

$$
\partial_\alpha A_\mu^a(x)
\mapsto ip_\alpha A_\mu^a(p).
$$

This Fourier convention is common when deriving all-incoming Feynman rules from the action. If one uses the opposite Fourier phase, all momenta in the intermediate expressions reverse. The final all-incoming rule is the same after the labels $p,q,r$ are defined consistently.

## Expanding the action

Insert $F=f-gh$ into the Yang–Mills Lagrangian:

$$
\begin{aligned}
\mathcal L_{\mathrm{YM}}
&=-\frac14(f_{\mu\nu}^a-gh_{\mu\nu}^a)(f^{a\mu\nu}-gh^{a\mu\nu})
\\
&=-\frac14 f_{\mu\nu}^af^{a\mu\nu}
+\frac{g}{2}f_{\mu\nu}^ah^{a\mu\nu}
-\frac{g^2}{4}h_{\mu\nu}^ah^{a\mu\nu}.
\end{aligned}
$$

The cubic term is the middle term:

$$
\mathcal L_3=\frac{g}{2}f_{\mu\nu}^ah^{a\mu\nu}.
$$

Substitute the definitions:

$$
f_{\mu\nu}^ah^{a\mu\nu}
=
(\partial_\mu A_\nu^a-\partial_\nu A_\mu^a)
 f^{abc}A^{b\mu}A^{c\nu}.
$$

The first term is

$$
T_1=f^{abc}(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu}.
$$

The second term is

$$
T_2=-f^{abc}(\partial_\nu A_\mu^a)A^{b\mu}A^{c\nu}.
$$

Relabel $\mu\leftrightarrow\nu$ in $T_2$:

$$
T_2=-f^{abc}(\partial_\mu A_\nu^a)A^{b\nu}A^{c\mu}.
$$

Then relabel $b\leftrightarrow c$ and use $f^{acb}=-f^{abc}$:

$$
T_2=f^{abc}(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu}=T_1.
$$

Therefore

$$
f_{\mu\nu}^ah^{a\mu\nu}=2T_1,
$$

and hence

$$
\mathcal L_3
=
g f^{abc}(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu}.
$$

That small relabeling step is a prime location for sign goblins.

## Momentum-space derivation

The cubic action is

$$
S_3
=
\int d^4x\,g f^{abc}(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu}.
$$

After Fourier transforming, the $x$ integral produces momentum conservation:

$$
(2\pi)^4\delta^{(4)}(p+q+r).
$$

The derivative can land on whichever external field occupies the first slot of $\mathcal L_3$. Since the three fields are identical bosonic gauge fields except for labels, the vertex is obtained by summing the six assignments of the external triples

$$
(a,\mu,p),\qquad (b,\nu,q),\qquad (c,\rho,r)
$$

to the three field positions in

$$
(\partial A)AA.
$$

The result, including the factor $i$ from $e^{iS}$ and the derivative factor $ip$, is

$$
V_3^{abc;\mu\nu\rho}(p,q,r)
=
g f^{abc}
\left[
\eta^{\mu\nu}(p-q)^\rho
+\eta^{\nu\rho}(q-r)^\mu
+\eta^{\rho\mu}(r-p)^\nu
\right].
$$

One can view the three terms as the three ways to choose which pair of Lorentz indices is contracted by a metric. The momentum multiplying that metric is the difference of the momenta on the corresponding two gauge legs.

## Bose symmetry check

Gauge bosons are bosons. The vertex must be symmetric under simultaneous exchange of any two full external labels, for example

$$
(a,\mu,p)\leftrightarrow(b,\nu,q).
$$

The structure constant changes sign:

$$
f^{bac}=-f^{abc}.
$$

The Lorentz-momentum bracket also changes sign under the same exchange. Therefore their product is symmetric. This is why the antisymmetric color factor does not violate Bose symmetry. The Lorentz piece compensates it.

This is a useful sanity check. If a proposed three-gluon vertex has $f^{abc}$ but the Lorentz-momentum factor is not antisymmetric under pair exchange, something is wrong.

## Abelian limit

For an Abelian gauge group,

$$
f^{abc}=0.
$$

Then

$$
\mathcal L_3=0,
\qquad
V_3=0.
$$

This is why minimal QED has no elementary three-photon vertex. Photon self-interactions can appear in effective actions, such as the Euler–Heisenberg Lagrangian after integrating out electrons, but not in the renormalizable pure Maxwell kinetic term.

## Contraction check

Contract the vertex with $p_\mu$. Using momentum conservation $p+q+r=0$, one finds

$$
\begin{aligned}
p_\mu V_3^{abc;\mu\nu\rho}(p,q,r)
=
g f^{abc}\Big[
&(r^2\eta^{\nu\rho}-r^\nu r^\rho)
\\
&-(q^2\eta^{\nu\rho}-q^\nu q^\rho)
\Big].
\end{aligned}
$$

The bracket is the difference of two transverse inverse kinetic operators. In a tree amplitude, these terms cancel neighboring propagators or combine with contact diagrams. In loop calculations, the same structure is upgraded to Slavnov–Taylor identities after ghosts and gauge fixing are included.

This is the non-Abelian cousin of the QED Ward-identity repair trick. Contracting a gauge vertex with momentum does not produce random algebra; it produces inverse propagators.

## Relation to the four-gluon vertex

The cubic vertex is not gauge invariant by itself. Neither is the four-gluon vertex by itself. The compact expression

$$
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
$$

is gauge invariant. Its perturbative expansion produces a family of terms that must work together.

For example, four-gauge-boson scattering at tree level receives:

- exchange diagrams with two three-gauge-boson vertices;
- a contact diagram from the four-gauge-boson vertex.

The exchange diagrams alone do not have the correct gauge-variation behavior. The contact term is not optional fine print; it is part of the same curvature-squared operator.

## Common mistakes

**Losing the factor of two in $f\cdot h$.** The two terms in $f_{\mu\nu}^a$ are equal after relabeling indices and using antisymmetry of $f^{abc}$. Missing this gives a vertex off by a factor of two.

**Mixing covariant-derivative conventions.** This page uses $D_\mu=\partial_\mu+igA_\mu$. If a text uses $D_\mu=\partial_\mu-igA_\mu$, the sign of the nonlinear term in $F_{\mu\nu}^a$ changes, and so do intermediate vertex signs.

**Forgetting all momenta are incoming.** The displayed rule assumes $p+q+r=0$. If one leg is outgoing in a diagram, replace its incoming momentum by minus the physical outgoing momentum.

**Checking color symmetry without Lorentz symmetry.** The color factor alone is antisymmetric. Bose symmetry involves the whole label: color, Lorentz index, and momentum.

**Treating the contraction identity as an on-shell statement only.** The contraction produces inverse kinetic operators off shell. The on-shell Ward identity is a consequence after these inverse operators act on external physical states or cancel propagators.

## Exercises

### Exercise 1: Derive the cubic term

Starting from

$$
F_{\mu\nu}^a=f_{\mu\nu}^a-gh_{\mu\nu}^a,
\qquad
h_{\mu\nu}^a=f^{abc}A_\mu^bA_\nu^c,
$$

show that the cubic term in $-\frac14F^2$ is

$$
\mathcal L_3
=
g f^{abc}(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu}.
$$

<details><summary><strong>Solution</strong></summary>

Expanding gives

$$
-\frac14(f-gh)^2
=
-\frac14f^2+\frac{g}{2}f\cdot h-\frac{g^2}{4}h^2.
$$

Thus

$$
\mathcal L_3=\frac{g}{2}(\partial_\mu A_\nu^a-\partial_\nu A_\mu^a)f^{abc}A^{b\mu}A^{c\nu}.
$$

The first term is

$$
f^{abc}(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu}.
$$

In the second term, relabel $\mu\leftrightarrow\nu$ and then $b\leftrightarrow c$. The antisymmetry $f^{acb}=-f^{abc}$ turns it into the same expression. Therefore $f\cdot h=2f^{abc}(\partial_\mu A_\nu^a)A^{b\mu}A^{c\nu}$, giving the stated result.

</details>

### Exercise 2: Check Bose symmetry

Show that

$$
V_3^{abc;\mu\nu\rho}(p,q,r)
$$

is invariant under the simultaneous exchange

$$
(a,\mu,p)\leftrightarrow(b,\nu,q).
$$

<details><summary><strong>Solution</strong></summary>

The color factor changes sign:

$$
f^{bac}=-f^{abc}.
$$

Now exchange $\mu\leftrightarrow\nu$ and $p\leftrightarrow q$ in the Lorentz bracket

$$
B^{\mu\nu\rho}(p,q,r)
=
\eta^{\mu\nu}(p-q)^\rho
+\eta^{\nu\rho}(q-r)^\mu
+\eta^{\rho\mu}(r-p)^\nu.
$$

The first term changes sign immediately. The second and third terms are exchanged and each changes so that the full bracket becomes

$$
B^{\nu\mu\rho}(q,p,r)=-B^{\mu\nu\rho}(p,q,r),
$$

using $p+q+r=0$. Hence the two minus signs cancel:

$$
f^{bac}B^{\nu\mu\rho}(q,p,r)=f^{abc}B^{\mu\nu\rho}(p,q,r).
$$

</details>

### Exercise 3: Contract the vertex

Using $p+q+r=0$, show that

$$
p_\mu V_3^{abc;\mu\nu\rho}(p,q,r)
=
g f^{abc}
\left[
(r^2\eta^{\nu\rho}-r^\nu r^\rho)
-(q^2\eta^{\nu\rho}-q^\nu q^\rho)
\right].
$$

<details><summary><strong>Solution</strong></summary>

Start from

$$
V_3^{abc;\mu\nu\rho}
=
g f^{abc}
\left[
\eta^{\mu\nu}(p-q)^\rho
+\eta^{\nu\rho}(q-r)^\mu
+\eta^{\rho\mu}(r-p)^\nu
\right].
$$

Contract with $p_\mu$:

$$
p_\mu V_3^{abc;\mu\nu\rho}
=
gf^{abc}
\left[
p^\nu(p-q)^\rho
+\eta^{\nu\rho}p\cdot(q-r)
+p^\rho(r-p)^\nu
\right].
$$

Use $p=-(q+r)$. The terms proportional to $q^\nu r^\rho$ and $r^\nu q^\rho$ cancel after simplification, leaving

$$
p_\mu V_3^{abc;\mu\nu\rho}
=
g f^{abc}
\left[
(r^2\eta^{\nu\rho}-r^\nu r^\rho)
-(q^2\eta^{\nu\rho}-q^\nu q^\rho)
\right].
$$

This is the difference of inverse transverse kinetic operators for the two adjacent gauge-boson lines.

</details>

## Related pages

The conceptual home of this interaction is [Gauge-Boson Self-Interactions](/gauge-theories-standard-model/yang-mills/gauge-boson-self-interactions/). The curvature origin is explained in [Non-Abelian Field Strength](/gauge-theories-standard-model/yang-mills/non-abelian-field-strength/), and the action is introduced in [Yang–Mills Action](/gauge-theories-standard-model/yang-mills/yang-mills-action/). The next calculation-library page, [Yang–Mills Beta Function](/gauge-theories-standard-model/calculation-library/yang-mills-beta-function/), uses the three- and four-gauge-boson vertices together with ghosts to obtain asymptotic freedom.

## References

- Srednicki, *Quantum Field Theory*, §§69 and 72, for non-Abelian gauge theory and the Yang–Mills Feynman rules.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–26, for Yang–Mills theory, gluon Feynman rules, and one-loop non-Abelian perturbation theory.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, §§15.1–15.2, for non-Abelian gauge invariance and the local structure of Yang–Mills interactions.

## Version history

- **2026-06-19:** Initial polished calculation-library draft.
