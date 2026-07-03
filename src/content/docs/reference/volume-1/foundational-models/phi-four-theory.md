---
title: "φ⁴ Theory"
description: "The simplest interacting scalar QFT: its Lagrangian, symmetries, phases, Feynman rules, loop corrections, and role as a foundation-level playground."
sidebar:
  label: "φ⁴ Theory"
  order: 1
---

## Summary

The real scalar $\phi^4$ theory is the smallest genuinely useful interacting relativistic QFT. It takes the free Klein–Gordon field and adds one local quartic self-interaction:

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4.
$$

That one extra term already teaches a surprising amount: how local interactions become vertices, why symmetry factors matter, how loop integrals generate ultraviolet divergences, how counterterms respect symmetries, how spontaneous symmetry breaking appears in the simplest relativistic setting, and why renormalization is not optional once interactions are present.

This page is a **model page**, not a full renormalization review. Its job is to give a compact, reusable reference for the model and to connect the foundation pages you have already read: free scalar fields, Wick's theorem, Feynman diagrams, generating functionals, effective action, and the ultraviolet-divergence preview. Srednicki uses scalar theories as the first laboratory for perturbation theory and renormalization; Coleman uses simple scalar models to introduce Wick diagrams, Feynman diagrams, mass renormalization, and spontaneous symmetry breaking; Zee repeatedly returns to scalar fields because they reveal the structure of QFT with minimal spin clutter; Weinberg uses scalar examples throughout the general formalism.

## Prerequisites

You should know [Scalar Fields](/foundations/classical-field-theory/scalar-fields/), [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/), [Wick's Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/), [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/), [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/), [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/), and [UV Divergences Preview](/foundations/interactions-and-wick-expansion/uv-divergences-preview/).

## Why φ⁴ is the first serious model

Free scalar theory is linear. It has particles, propagators, and a perfectly good Hilbert-space interpretation, but the particles do not scatter. A nonzero connected four-point scattering amplitude requires an interaction.

The simplest Lorentz-invariant local polynomial interaction for one real scalar field that is bounded below is quartic:

$$
V(\phi)=\frac12m^2\phi^2+\frac{\lambda}{4!}\phi^4,
\qquad \lambda>0.
$$

The cubic interaction $g\phi^3$ is an excellent perturbative toy model, but a real cubic potential is not bounded below by itself. The quartic model is therefore the cleanest first model in which the same interaction can be used for classical stability, tree-level scattering, loop corrections, and symmetry-breaking physics.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Map of φ⁴ theory as a model](/figures/foundations/phi-four-theory-map.svg)

<figcaption>

The same $\phi^4$ Lagrangian supports two complementary lessons. Classically, the sign of $m^2$ controls the vacuum structure. Perturbatively, the quartic term supplies a four-scalar vertex and loop corrections whose divergences are absorbed by local counterterms.

</figcaption>
</figure>

:::note[Assumptions]
This page studies the model perturbatively around a chosen vacuum. It does not try to prove that the model exists as an interacting continuum QFT in every dimension, nor does it replace the later pages on renormalization, critical phenomena, constructive QFT, or Wilsonian RG.
:::

## The Lagrangian and conventions

For one real scalar field in four-dimensional Minkowski spacetime, qft.org uses

$$
\boxed{
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4
}
$$

with mostly-minus metric

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-).
$$

The free propagator is

$$
\Delta_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

The interaction action is

$$
S_{\rm int}
=-\int d^4x\,\frac{\lambda}{4!}\phi^4(x).
$$

In the Dyson or path-integral expansion, each quartic vertex contributes

$$
\boxed{\text{quartic vertex}=-i\lambda.}
$$

The factor $1/4!$ in the Lagrangian cancels the number of ways to contract four identical fields at the vertex. Without it, every diagram would carry annoying extra combinatorial factors.

## The discrete symmetry

The basic Lagrangian has a $\mathbb Z_2$ symmetry,

$$
\phi(x)\mapsto -\phi(x).
$$

This simple symmetry has real consequences:

$$
\langle 0|T\phi(x_1)\cdots\phi(x_n)|0\rangle=0
\quad\text{for odd }n
$$

when the vacuum is also $\mathbb Z_2$ invariant. It also forbids odd powers such as $\phi$, $\phi^3$, and source-independent tadpole counterterms in the symmetric phase.

If one adds an external source $J\phi$, the source breaks the symmetry unless $J$ is transformed as well. This is useful in the generating-functional formalism: odd correlators are obtained by differentiating with respect to $J$, but they vanish at $J=0$ in the symmetric vacuum.

## Classical phases

The classical potential is

$$
V(\phi)=\frac12m^2\phi^2+\frac{\lambda}{4!}\phi^4.
$$

For $\lambda>0$ and $m^2>0$, the minimum is at

$$
\phi=0.
$$

This is the symmetric phase. Expanding around $\phi=0$, the elementary excitation has mass $m$.

For $\lambda>0$ and $m^2<0$, write

$$
m^2=-\mu^2,
\qquad \mu^2>0.
$$

Then

$$
V(\phi)=-\frac12\mu^2\phi^2+\frac{\lambda}{4!}\phi^4
$$

has two classical minima,

$$
\phi=\pm v,
\qquad
v^2=\frac{6\mu^2}{\lambda}.
$$

Choosing one of them spontaneously breaks the $\mathbb Z_2$ symmetry. If

$$
\phi(x)=v+h(x),
$$

then

$$
m_h^2=V''(v)=2\mu^2,
$$

and

$$
V(v+h)=V(v)+\frac12m_h^2h^2+\frac{\lambda v}{3!}h^3+\frac{\lambda}{4!}h^4.
$$

This is a useful lesson: a theory with an exact symmetry can have perturbation theory around a vacuum that does not make the symmetry manifest.

## Feynman rules and tree scattering

For

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

the four-scalar vertex factor is

$$
\boxed{-i\lambda}.
$$

At tree level, the connected four-point amplitude comes from a single contact diagram:

$$
i\mathcal M_{2\to2}^{\rm tree}=-i\lambda,
\qquad
\mathcal M_{2\to2}^{\rm tree}=-\lambda.
$$

In position space, the first connected four-point contribution is

$$
G_{4,\rm conn}^{(1)}(x_1,x_2,x_3,x_4)
=(-i\lambda)\int d^4z\,
\prod_{a=1}^4\Delta_F(x_a-z),
$$

up to the overall convention for whether the correlator includes factors of $i$. The physics is unambiguous: one local interaction point is integrated over spacetime, and each external insertion is connected to that point by a free propagator.

## Source-functional viewpoint

The scalar generating functional is

$$
Z[J]=\int\mathcal D\phi\,
\exp\left\{i\int d^4x
\left[
\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4
+J\phi
\right]\right\}.
$$

Three related functionals carry different diagrammatic information:

$$
Z[J] \quad\text{generates all diagrams},
$$

$$
W[J]=-i\log Z[J] \quad\text{generates connected diagrams},
$$

and

$$
\Gamma[\varphi]=W[J]-\int d^4x\,J\varphi
\quad\text{generates 1PI diagrams},
\qquad
\varphi=\frac{\delta W}{\delta J}.
$$

In $\phi^4$ theory, this hierarchy is especially transparent. The same quartic vertex appears in all three languages, but the diagram classes are different.

## First loop effects

The one-loop two-point correction is a tadpole. Schematically,

$$
-i\Pi_{\rm 1\,loop}
\propto
(-i\lambda)\int\frac{d^4\ell}{(2\pi)^4}
\frac{i}{\ell^2-m^2+i\epsilon}.
$$

This is ultraviolet divergent. Because the divergence is local, it is absorbed into local counterterms, primarily the mass counterterm at this order.

The one-loop four-point correction contains bubble diagrams. In four dimensions, their divergent part has the same operator structure as $\phi^4$, so it renormalizes $\lambda$. In a common normalization, the one-loop beta function in four dimensions has the form

$$
\beta_\lambda
=\mu\frac{d\lambda}{d\mu}
=\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

Near $d=4-\epsilon$, the leading beta function becomes

$$
\beta_\lambda=-\epsilon\lambda+\frac{3\lambda^2}{16\pi^2}+O(\lambda^3),
$$

with a perturbative Wilson–Fisher fixed point

$$
\lambda_* = \frac{16\pi^2}{3}\epsilon+O(\epsilon^2).
$$

That preview belongs here because it explains why this tiny model appears in both particle theory and critical phenomena. The full RG analysis belongs to the Renormalization/RG/EFT and Statistical Field Theory sections.

## Euclidean and statistical interpretation

After Wick rotation, the Euclidean action is

$$
S_E[\phi]
=\int d^dx\left[
\frac12(\partial\phi)^2+\frac12m^2\phi^2+\frac{\lambda}{4!}\phi^4
\right],
$$

and the Euclidean weight is

$$
e^{-S_E[\phi]}.
$$

For $\lambda>0$, the large-field behavior is damped. This is why the Euclidean $\phi^4$ model is the continuum language of the Landau–Ginzburg description of critical phenomena. Zee emphasizes this link: the same Euclidean scalar functional that begins as a QFT toy model becomes the field theory of an order parameter near a phase transition.

## What the model teaches

| Idea | How it appears in $\phi^4$ theory |
|---|---|
| local interaction | four fields meet at one spacetime point |
| vertex factor | $-i\lambda$ |
| discrete symmetry | $\mathbb Z_2: \phi\mapsto-\phi$ |
| tree scattering | a single contact graph for four scalars |
| loop divergences | tadpoles and bubbles |
| counterterms | $\delta m^2$, $\delta Z$, $\delta\lambda$, and vacuum energy |
| broken symmetry | two classical vacua for $m^2<0$ |
| effective action | quantum-corrected potential and 1PI vertices |
| RG flow | running quartic coupling |
| universality | Landau–Ginzburg and Ising-type critical behavior |

Tiny Lagrangian, huge syllabus. Very efficient little beast.

## Common pitfalls

### Forgetting the factorial convention

With

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

the vertex factor is $-i\lambda$, not $-i\lambda/4!$.

### Confusing stability with the sign of the vertex

Classical stability requires $\lambda>0$. The Lorentzian vertex factor is then $-i\lambda$. These statements refer to different parts of the convention.

### Thinking the broken phase is a different Lagrangian

The broken-phase cubic interaction appears after shifting around a chosen minimum. It is not an arbitrary new cubic theory; its coefficient is tied to $v$ and $\lambda$.

### Dropping the vacuum energy too casually

Vacuum bubbles cancel in normalized scattering amplitudes, but the vacuum energy is meaningful in the effective action, finite-temperature theory, and gravity.

### Treating four-dimensional φ⁴ as completely solved

Perturbation theory is straightforward. The exact continuum theory is a subtler nonperturbative question.

## Relation to other topics

- [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/) introduces the same quartic vertex as part of perturbation theory.
- [Connected Diagrams](/foundations/interactions-and-wick-expansion/connected-diagrams/) explains how disconnected scalar diagrams factorize.
- [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/) turns the model into a generator of 1PI vertices and quantum equations of motion.
- [UV Divergences Preview](/foundations/interactions-and-wick-expansion/uv-divergences-preview/) explains why scalar loops require local counterterms.
- [Yukawa Theory](/foundations/foundational-models/yukawa-theory/) adds fermions and shows how scalar sectors and fermion sectors renormalize each other.
- Renormalization/RG/EFT will develop beta functions, Wilsonian flow, triviality, relevant and irrelevant operators, and EFT power counting.
- Statistical Field Theory will use the Euclidean $\phi^4$ model as the prototype of critical phenomena.

## Research status

Perturbative $\phi^4$ theory, its Feynman rules, one-loop counterterms, effective potential, and Wilson–Fisher expansion are textbook-standard. The nonperturbative status depends strongly on dimension and regulator. Lower-dimensional constructive scalar field theories have rigorous realizations; four-dimensional pure $\phi^4$ theory is generally treated cautiously as an effective theory rather than as a known nontrivial fundamental continuum theory.

## Exercises

### Exercise 1: Dimension of λ

In $d$ spacetime dimensions, use the kinetic term to show that

$$
[\phi]=\frac{d-2}{2},
$$

and then find $[\lambda]$ for the interaction $-\lambda\phi^4/4!$.

<details>
<summary><strong>Solution</strong></summary>

The kinetic term has dimension $d$:

$$
[\partial_\mu\phi\partial^\mu\phi]=2+2[\phi]=d.
$$

Thus

$$
[\phi]=\frac{d-2}{2}.
$$

The quartic term requires

$$
[\lambda]+4[\phi]=d,
$$

so

$$
[\lambda]=d-4\frac{d-2}{2}=4-d.
$$

</details>

### Exercise 2: Classical equation of motion

Derive the equation of motion from

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4.
$$

<details>
<summary><strong>Solution</strong></summary>

The Euler–Lagrange equation gives

$$
\partial_\mu\partial^\mu\phi
+m^2\phi
+\frac{\lambda}{3!}\phi^3=0.
$$

Using $\Box=\partial_\mu\partial^\mu$,

$$
(\Box+m^2)\phi+\frac{\lambda}{3!}\phi^3=0.
$$

</details>

### Exercise 3: Tree-level scalar scattering

Find the tree-level $2\to2$ amplitude from the contact vertex in $\phi^4$ theory.

<details>
<summary><strong>Solution</strong></summary>

The single contact diagram gives

$$
i\mathcal M=-i\lambda.
$$

Therefore

$$
\boxed{\mathcal M=-\lambda.}
$$

</details>

### Exercise 4: Broken-phase minima

For

$$
V(\phi)=-\frac12\mu^2\phi^2+\frac{\lambda}{4!}\phi^4,
$$

with $\lambda>0$, find the nonzero minima and the fluctuation mass.

<details>
<summary><strong>Solution</strong></summary>

The stationary condition is

$$
V'(\phi)=-\mu^2\phi+\frac{\lambda}{3!}\phi^3=0.
$$

The nonzero solutions obey

$$
\phi^2=\frac{6\mu^2}{\lambda}.
$$

Thus

$$
\phi=\pm v,
\qquad
v^2=\frac{6\mu^2}{\lambda}.
$$

The fluctuation mass is

$$
m_h^2=V''(v)=-\mu^2+\frac{\lambda}{2}v^2=2\mu^2.
$$

</details>

### Exercise 5: Superficial divergence

Show that connected $\phi^4$ diagrams in four dimensions have

$$
D=4-E.
$$

<details>
<summary><strong>Solution</strong></summary>

The superficial degree of divergence is

$$
D=4L-2I.
$$

Using

$$
L=I-V+1,
$$

we get

$$
D=4(I-V+1)-2I=2I-4V+4.
$$

The line-counting identity

$$
4V=2I+E
$$

implies

$$
2I=4V-E.
$$

Therefore

$$
D=(4V-E)-4V+4=4-E.
$$

</details>

### Exercise 6: Wilson–Fisher fixed point

For

$$
\beta_\lambda=-\epsilon\lambda+\frac{3\lambda^2}{16\pi^2},
$$

find the fixed points to this order.

<details>
<summary><strong>Solution</strong></summary>

Set $\beta_\lambda=0$:

$$
0=\lambda\left(-\epsilon+\frac{3\lambda}{16\pi^2}\right).
$$

The fixed points are

$$
\lambda=0
$$

and

$$
\boxed{\lambda_* = \frac{16\pi^2}{3}\epsilon.}
$$

The second is the perturbative Wilson–Fisher fixed point for small positive $\epsilon$.

</details>

## Sources and further reading

- Mark Srednicki, *Quantum Field Theory*, §§9–18 and §§28–32, for scalar perturbation theory, loop corrections, renormalizability, the renormalization group, and spontaneous symmetry breaking.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 8, 10, 16, 25, 44, and 50, for Wick diagrams, mass renormalization, scalar loop integrals, counterterms, effective potentials, and the RG in $\phi^4$ theory.
- Anthony Zee, *Quantum Field Theory in a Nutshell*, chs. I.7, III.1–III.3, IV.1–IV.3, V.3, and VI.8, for diagrams, counterterms, effective potentials, Landau–Ginzburg theory, and RG flow.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 6 and 12, and Vol. II, chs. 18–19, for Feynman rules, renormalization theory, RG methods, and broken global symmetries.
- Kenneth G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” *Physics Reports* **12** (1974), 75–199, for the classic Wilsonian perspective.

## Version history

- **2026-05-24:** Initial qft.org foundational model page for $\phi^4$ theory: Lagrangian, symmetry, perturbative rules, phases, counterterms, RG preview, Euclidean/statistical interpretation, pitfalls, and exercises.
