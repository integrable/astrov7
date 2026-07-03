---
title: "Yukawa Theory"
description: "A compact introduction to scalar–fermion interactions: the Yukawa vertex, scalar exchange, chiral symmetry, mass generation, fermion loops, and renormalizable completion."
sidebar:
  label: "Yukawa Theory"
  order: 2
---

## Summary

Yukawa theory is the simplest QFT in which a bosonic field talks directly to a fermion field. In its most basic scalar form,

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m_\phi^2\phi^2
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-y\phi\bar\psi\psi
- V_{\rm self}(\phi).
$$

The interaction

$$
-y\phi\bar\psi\psi
$$

produces a vertex with one scalar line and two fermion lines. It is the first model where spinor algebra, fermion signs, scalar exchange, and radiative generation of scalar counterterms all meet in one small laboratory.

This page treats Yukawa theory as a **Foundational Model**: a concrete playground, not a full phenomenology or renormalization chapter. Srednicki devotes a later sequence to loop corrections and beta functions in Yukawa theory after building scalar, spinor, and Feynman-rule technology; Coleman uses nucleon–meson style scalar–fermion models to teach scattering, mass renormalization, and Feynman diagrams; Weinberg treats Yukawa-type couplings as part of the general local-field formalism; Zee uses scalar exchange and fermion loops as recurring conceptual examples.

## Prerequisites

You should know [Dirac Field](/foundations/free-fields/dirac-field/), [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/), [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/), [Fermionic Path Integral](/foundations/path-integral-formalism/fermionic-path-integral/), [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/), [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/), and [φ⁴ Theory](/foundations/foundational-models/phi-four-theory/).

## Core idea

The scalar field supplies a bosonic mediator or order parameter. The fermion bilinear supplies a Lorentz scalar. Multiplying them gives a local Lorentz-invariant interaction:

$$
\phi\bar\psi\psi.
$$

<figure class="doc-figure" style="--figure-width: 48rem;">

![Map of Yukawa theory](/figures/foundations/yukawa-theory-map.svg)

<figcaption>

Yukawa theory couples one scalar field to a fermion bilinear. The same vertex describes scalar exchange at tree level and produces fermion-loop corrections that force the scalar sector to be included consistently.

</figcaption>
</figure>

At tree level, the vertex lets two fermions exchange a scalar. In a background with $\langle\phi\rangle=v$, the same coupling shifts the fermion mass. At loop level, fermions renormalize scalar masses, scalar self-interactions, and the Yukawa vertex itself.

:::note[Assumptions]
This page uses ordinary perturbation theory around a chosen vacuum and treats the scalar and fermion as elementary fields. It does not cover chiral gauge theories, Standard Model flavor structure, Higgs phenomenology, nonperturbative bound states, or the full renormalization group of general gauge–Yukawa systems.
:::

## The basic scalar Yukawa model

For a real scalar $\phi$ and a Dirac fermion $\psi$, the minimal scalar Yukawa Lagrangian is

$$
\boxed{
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m_\phi^2\phi^2
+\bar\psi(i\slashed\partial-m)\psi
-y\phi\bar\psi\psi
- V_{\rm self}(\phi)
}
$$

where

$$
\slashed\partial=\gamma^\mu\partial_\mu.
$$

A common renormalizable scalar self-potential is

$$
V_{\rm self}(\phi)
=a\phi+\frac12\delta m_\phi^2\phi^2+\frac{\kappa}{3!}\phi^3+\frac{\lambda}{4!}\phi^4,
$$

with some terms absent if symmetries forbid them. The notation here separates the point of the model: the Yukawa interaction itself is the scalar–fermion coupling, but the scalar sector must be specified too.

For the scalar coupling used above, the momentum-space vertex factor is

$$
\boxed{\text{scalar Yukawa vertex}=-iy.}
$$

The fermion propagator is

$$
S_F(p)=\frac{i(\slashed p+m)}{p^2-m^2+i\epsilon},
$$

and the scalar propagator is

$$
\Delta_F(p)=\frac{i}{p^2-m_\phi^2+i\epsilon}.
$$

## Scalar and pseudoscalar couplings

There are two common Lorentz-invariant Yukawa bilinears:

$$
\phi\bar\psi\psi,
\qquad
 a\bar\psi i\gamma^5\psi.
$$

The first couples an ordinary scalar $\phi$ to the scalar bilinear $\bar\psi\psi$. The second couples a pseudoscalar $a$ to the pseudoscalar bilinear $\bar\psi i\gamma^5\psi$.

Under parity, with the standard transformation of a Dirac spinor, the bilinears behave as

| Bilinear | Parity behavior | Natural boson partner |
| --- | --- | --- |
| $\bar\psi\psi$ | even | scalar |
| $\bar\psi i\gamma^5\psi$ | odd | pseudoscalar |

This distinction matters in pion–nucleon effective models, axion-like interactions, CP-odd couplings, and Standard Model Higgs interactions. The scalar coupling is the default on this page; the pseudoscalar variant differs mainly by a matrix factor at the vertex and by discrete-symmetry assignments.

## Engineering dimensions

In $d$ spacetime dimensions,

$$
[\phi]=\frac{d-2}{2},
\qquad
[\psi]=\frac{d-1}{2}.
$$

The Yukawa interaction has dimension

$$
[\phi]+2[\psi]
=\frac{d-2}{2}+d-1
=\frac{3d-4}{2},
$$

so

$$
[y]=d-\frac{3d-4}{2}=\frac{4-d}{2}.
$$

Thus $y$ is dimensionless in four dimensions. This is the same engineering-dimension miracle that makes gauge and quartic scalar couplings so important in four-dimensional relativistic QFT.

## Renormalizable closure

The Yukawa vertex alone is not usually the whole renormalizable model. Once fermion loops are allowed, the scalar sector is renormalized too.

For a generic real scalar and Dirac fermion with no $\mathbb Z_2$-type symmetry, that includes

$$
1,
\quad
\phi,
\quad
\phi^2,
\quad
\phi^3,
\quad
\phi^4,
$$

as well as the fermion kinetic term, fermion mass term, scalar kinetic term, scalar mass term, and Yukawa vertex. If parity or another internal symmetry forbids some of these terms, they may be consistently omitted.

A standard pseudoscalar Yukawa model chooses a parity-odd scalar $a$ and interaction

$$
\mathcal L_Y=-ig a\bar\psi\gamma^5\psi.
$$

In that case $a$ and $a^3$ are forbidden by parity, but $a^4$ is still allowed. Coleman emphasizes a sharp lesson here: in the strict renormalizable sense, a pseudoscalar Yukawa theory is not merely a one-coupling theory. A fermion box with four external scalar legs generates a logarithmic divergence, so the scalar quartic coupling must be part of the model.

A compact renormalizable version is therefore

$$
\mathcal L
=\bar\psi(i\slashed\partial-m)\psi
+\frac12\partial_\mu a\partial^\mu a
-\frac12M^2a^2
-ig a\bar\psi\gamma^5\psi
-\frac{\lambda}{4!}a^4
+\mathcal L_{\rm ct}.
$$

Srednicki's loop treatment makes the same point in diagram language: scalar and fermion self-energies, the Yukawa vertex, and the four-scalar vertex all require their own renormalization constants.

## Tree-level scalar exchange

The Yukawa vertex makes the scalar field mediate a force between fermions. For fermion–fermion scattering by one scalar exchange, the schematic tree amplitude is

$$
i\mathcal M
=(-iy)^2
\left[\overline u(p_3)u(p_1)\right]
\frac{i}{q^2-m_\phi^2+i\epsilon}
\left[\overline u(p_4)u(p_2)\right],
$$

where $q$ is the momentum transferred through the scalar line.

In the nonrelativistic static limit, this gives the Yukawa potential

$$
V(r)=-\frac{y_1y_2}{4\pi r}e^{-m_\phi r},
$$

up to convention-dependent sign choices for the source couplings. The essential physical point is the range:

$$
\boxed{R\sim m_\phi^{-1}.}
$$

A massive exchanged particle gives a short-range force. A massless exchanged particle gives a long-range $1/r$ force.

## Mass generation preview

Suppose the scalar develops a constant background value,

$$
\phi(x)=v+h(x).
$$

Then

$$
-y\phi\bar\psi\psi
=-yv\bar\psi\psi-yh\bar\psi\psi.
$$

The first term is a fermion mass contribution,

$$
\boxed{m_f=yv}
$$

if no other fermion mass is present. The second term says that the fluctuation $h$ still couples to the fermion with the same Yukawa strength.

This is the miniature version of the Standard Model mechanism for fermion masses. The full Standard Model has chiral fermions, gauge symmetry, flavor matrices, and a scalar doublet, but the core local structure is still a Yukawa coupling.

## Loop anatomy

Once the scalar and fermion talk to each other, each sector renormalizes the other.

| Diagram type | What it corrects | New feature |
|---|---|---|
| scalar self-energy with fermion loop | scalar mass and field normalization | closed-fermion-loop minus sign |
| fermion self-energy with scalar line | fermion mass and field normalization | spinor numerator algebra |
| Yukawa vertex correction | coupling $y$ | gamma-matrix structure |
| fermion box with four scalar legs | scalar quartic coupling $\lambda$ | $\phi^4$ counterterm |

This is the first foundational model where scalar diagrams and spinor diagrams are genuinely entangled. The scalar field is no longer just a scalar exercise, and the fermion field is no longer just a free spinor exercise.

## Low-energy effective interaction

If the scalar is heavy compared with the momentum transfer,

$$
|q^2|\ll m_\phi^2,
$$

then

$$
\frac{i}{q^2-m_\phi^2+i\epsilon}
\approx
-\frac{i}{m_\phi^2}+O\left(\frac{q^2}{m_\phi^4}\right).
$$

At low energies, scalar exchange becomes a local four-fermion interaction,

$$
\mathcal L_{\rm eff}\sim \frac{y^2}{2m_\phi^2}(\bar\psi\psi)^2+
\text{higher-derivative terms},
$$

up to signs and factors depending on the precise normalization and whether identical fermions are involved. This is a clean first example of integrating out a heavy mediator.

## Common pitfalls

### Thinking Yukawa theory is only one vertex

The vertex $\phi\bar\psi\psi$ is the signature interaction. The renormalizable theory is the full set of local terms allowed by the symmetries.

### Forgetting the scalar quartic coupling

Even if you do not write $\lambda\phi^4$ at tree level, fermion loops generally generate the corresponding counterterm. A stable scalar sector also usually wants a quartic potential.

### Losing the closed-fermion-loop sign

Every closed fermion loop contributes an extra minus sign. This is not optional bookkeeping; it is the diagrammatic shadow of Grassmann statistics.

### Confusing scalar and pseudoscalar couplings

$\bar\psi\psi$ and $\bar\psi i\gamma^5\psi$ have different parity. Which coupling is allowed depends on the parity assignment of the scalar.

### Treating a background value as a new arbitrary mass

If a fermion mass comes from $\phi=v+h$, the mass and the coupling to $h$ are related. That relation is what makes Yukawa interactions so powerful in symmetry-breaking theories.

## Relation to other topics

- [Dirac Field](/foundations/free-fields/dirac-field/) supplies the spinor equations, spin sums, and propagator.
- [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/) explains why $\bar\psi\psi$ and $\bar\psi i\gamma^5\psi$ have different parity.
- [Fermionic Path Integral](/foundations/path-integral-formalism/fermionic-path-integral/) explains Grassmann sources, fermion determinants, and closed-loop signs.
- [φ⁴ Theory](/foundations/foundational-models/phi-four-theory/) supplies the scalar quartic interaction that Yukawa theory needs for renormalizable closure.
- [UV Divergences Preview](/foundations/interactions-and-wick-expansion/uv-divergences-preview/) explains why loop divergences are absorbed into local counterterms.
- Gauge Theories and the Standard Model will treat QED, Higgs Yukawa matrices, electroweak symmetry breaking, and flavor.
- Renormalization/RG/EFT will treat the coupled beta functions for $y$ and $\lambda$ systematically.

## Research status

Perturbative Yukawa theory, scalar exchange, spinor Feynman rules, fermion-loop signs, and one-loop renormalization are textbook-standard. Its role as a foundational model is stable. Its use as a phenomenological model depends on extra structure: gauge symmetry, flavor, chiral representations, parity assignments, or effective-field-theory power counting.

## Exercises

### Exercise 1: Dimension of the Yukawa coupling

In $d$ spacetime dimensions, use

$$
[\phi]=\frac{d-2}{2},
\qquad
[\psi]=\frac{d-1}{2}
$$

to find the mass dimension of $y$ in $y\phi\bar\psi\psi$.

<details>
<summary><strong>Solution</strong></summary>

The operator has dimension

$$
[\phi]+2[\psi]
=\frac{d-2}{2}+d-1
=\frac{3d-4}{2}.
$$

Since the Lagrangian density has dimension $d$,

$$
[y]=d-\frac{3d-4}{2}=\frac{4-d}{2}.
$$

Thus $y$ is dimensionless in $d=4$.

</details>

### Exercise 2: Vertex factor

Show that

$$
\mathcal L_Y=-y\phi\bar\psi\psi
$$

gives the vertex factor $-iy$.

<details>
<summary><strong>Solution</strong></summary>

The Dyson expansion contains

$$
i\int d^4x\,\mathcal L_Y
=-iy\int d^4x\,\phi\bar\psi\psi.
$$

After the fields are contracted with one scalar line and two fermion lines, the remaining local factor is

$$
\boxed{-iy.}
$$

</details>

### Exercise 3: Pseudoscalar parity

Let $a$ be parity odd:

$$
P^{-1}a(t,\mathbf x)P=-a(t,-\mathbf x).
$$

Explain why $a^3$ is forbidden by parity but $a^4$ is allowed.

<details>
<summary><strong>Solution</strong></summary>

Under $a\mapsto-a$,

$$
a^3\mapsto-a^3,
\qquad
a^4\mapsto+a^4.
$$

A parity-invariant Lagrangian cannot contain the odd term $a^3$, but it may contain the even term $a^4$.

</details>

### Exercise 4: Range of the Yukawa potential

Use

$$
\int\frac{d^3\mathbf q}{(2\pi)^3}
\frac{e^{i\mathbf q\cdot\mathbf r}}{\mathbf q^2+M^2}
=\frac{e^{-Mr}}{4\pi r}
$$

to identify the range of the force mediated by a scalar of mass $M$.

<details>
<summary><strong>Solution</strong></summary>

The static potential is proportional to

$$
\frac{e^{-Mr}}{4\pi r}.
$$

The exponential suppresses the interaction when $Mr\gg1$, so the characteristic range is

$$
\boxed{R\sim M^{-1}.}
$$

</details>

### Exercise 5: Fermion mass from a scalar background

If

$$
\mathcal L_Y=-y\phi\bar\psi\psi,
\qquad
\phi=v+h,
$$

find the induced mass term and the remaining interaction.

<details>
<summary><strong>Solution</strong></summary>

Substitute the shifted field:

$$
-y\phi\bar\psi\psi
=-yv\bar\psi\psi-yh\bar\psi\psi.
$$

The first term is a fermion mass term,

$$
m_f=yv,
$$

if no bare mass is present. The second term is the residual Yukawa interaction of the scalar fluctuation $h$.

</details>

### Exercise 6: Fermion box divergence

Use power counting to show that the fermion box with four external scalar legs is logarithmically divergent in four dimensions.

<details>
<summary><strong>Solution</strong></summary>

At large loop momentum,

$$
S_F(\ell)\sim \frac{\slashed \ell}{\ell^2}\sim \frac{1}{\ell}.
$$

The box has four fermion propagators, so the integrand scales as

$$
\int d^4\ell\,\frac{1}{\ell^4}.
$$

Since $d^4\ell\sim \ell^3d\ell$,

$$
\int^\Lambda d^4\ell\,\frac{1}{\ell^4}
\sim \int^\Lambda \frac{d\ell}{\ell},
$$

which is logarithmically divergent. The counterterm has four external scalar legs, so it is a local $\phi^4$ term.

</details>

## Sources and further reading

- H. Yukawa, “On the Interaction of Elementary Particles,” *Proceedings of the Physico-Mathematical Society of Japan* **17** (1935), 48–57, for the original massive-boson force idea.
- Mark Srednicki, *Quantum Field Theory*, §§36–43 and §§51–52, for spinor Lagrangians, fermionic path integrals, loop corrections in Yukawa theory, and Yukawa beta functions.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 21, 24–25, and 43–45, for fermion Feynman rules, pion–nucleon Yukawa models, renormalizable scalar–fermion interactions, and sigma-model applications.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 5–7, 9, and 12, for causal spinor fields, Feynman rules, path integrals, and renormalization logic.
- Anthony Zee, *Quantum Field Theory in a Nutshell*, chs. II.1–II.5 and III.2, for Dirac fields, fermion diagrams, and renormalizable versus nonrenormalizable couplings.

## Version history

- **2026-05-24:** Initial qft.org foundational model page for Yukawa theory: scalar and pseudoscalar couplings, scalar exchange, mass-generation preview, fermion loops, counterterm closure, low-energy effective interaction, pitfalls, and exercises.
