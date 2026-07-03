---
title: "Scalar QED"
description: "Charged scalar matter coupled to electromagnetism: the scalar QED Lagrangian, covariant derivative, photon and seagull vertices, Ward identities, loops, and renormalizable closure."
sidebar:
  label: "Scalar QED"
  order: 3
---

## Summary

**Scalar QED** is the Abelian gauge theory of a charged complex scalar field. It is the smallest model in which a scalar particle carries electric charge and interacts with a dynamical photon:

$$
\boxed{
\mathcal L
=-\frac14F_{\mu\nu}F^{\mu\nu}
+(D_\mu\Phi)^\dagger D^\mu\Phi
-m^2\Phi^\dagger\Phi
-\frac{\lambda}{4}(\Phi^\dagger\Phi)^2,
\qquad
D_\mu=\partial_\mu+iqA_\mu.
}
$$

It is the cleanest place to see a fact that is easy to miss in spinor QED: minimal coupling to gauge fields can force **contact interactions**. Expanding the covariant derivative gives both a scalar-scalar-photon vertex and a scalar-scalar-two-photon vertex. The two-photon contact term, often called the **seagull vertex**, is not an aesthetic extra. It is required by local gauge invariance.

As a foundational model, scalar QED connects many earlier pages: complex scalar fields, Maxwell theory, charged matter, Feynman diagrams, Ward identities, gauge fixing, and ultraviolet divergences. Srednicki uses scalar electrodynamics to exhibit the covariant derivative, the gauge-field-dependent scalar current, and the three characteristic vertices of the model. Coleman uses the same model to show how derivative couplings and seagull terms fit into functional-integral Feynman rules, and later to emphasize that scalar electrodynamics needs a scalar self-interaction for renormalizable closure.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Map of scalar QED](/figures/foundations/scalar-qed-model-map.svg)

<figcaption>

Scalar QED packages charged scalar matter and electromagnetism into the single gauge-covariant structure $(D_\mu\Phi)^\dagger D^\mu\Phi$. Expanding it gives a one-photon scalar vertex and a two-photon seagull vertex. Gauge invariance ties them together through Ward identities.

</figcaption>
</figure>

## Prerequisites

You should know [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/), [Maxwell Field](/foundations/free-fields/maxwell-field/), [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/), [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/), [Charged Matter](/foundations/gauge-fields-first-principles/charged-matter/), [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/), [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/), and [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/).

:::note[Conventions]
qft.org uses mostly-minus metric and Abelian covariant derivative

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\Phi\mapsto e^{-iq\alpha}\Phi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

With this convention, a positively charged scalar has $q=+e$ and an electron has $q=-e$, where $e>0$. Many textbooks use the opposite sign in $D_\mu$. The relative signs among the derivative vertex, seagull vertex, and Ward identities are what matter.
:::

:::note[Scope]
This page is a **model page**. It introduces scalar QED as a compact laboratory for gauge invariance and charged scalar perturbation theory. It does not replace the later full QED, scalar electrodynamics, Abelian Higgs, renormalization, infrared, or electroweak pages.
:::

## The model

The ingredients are:

$$
\Phi(x) \quad\text{complex scalar matter},
\qquad
A_\mu(x) \quad\text{Abelian gauge potential}.
$$

The field strength is

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

The local gauge symmetry is

$$
\Phi(x)\mapsto e^{-iq\alpha(x)}\Phi(x),
\qquad
\Phi^\dagger(x)\mapsto e^{+iq\alpha(x)}\Phi^\dagger(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x).
$$

The covariant derivative transforms like the scalar field:

$$
D_\mu\Phi=(\partial_\mu+iqA_\mu)\Phi,
\qquad
D_\mu\Phi\mapsto e^{-iq\alpha}D_\mu\Phi.
$$

Therefore the kinetic term

$$
(D_\mu\Phi)^\dagger D^\mu\Phi
$$

is gauge invariant, while $\partial_\mu\Phi^\dagger\partial^\mu\Phi$ alone is not.

In four dimensions, the standard renormalizable scalar QED Lagrangian is

$$
\boxed{
\mathcal L
=-\frac14F_{\mu\nu}F^{\mu\nu}
+(D_\mu\Phi)^\dagger D^\mu\Phi
-m^2\Phi^\dagger\Phi
-\frac{\lambda}{4}(\Phi^\dagger\Phi)^2.
}
$$

The quartic normalization is chosen so that the four-scalar vertex with two $\Phi$ legs and two $\Phi^\dagger$ legs is $-i\lambda$.

## Expanding the covariant derivative

The scalar kinetic term expands as

$$
\begin{aligned}
(D_\mu\Phi)^\dagger D^\mu\Phi
&=\partial_\mu\Phi^\dagger\partial^\mu\Phi \\
&\quad +iqA_\mu\left[(\partial^\mu\Phi^\dagger)\Phi-\Phi^\dagger\partial^\mu\Phi\right]
+q^2A_\mu A^\mu\Phi^\dagger\Phi.
\end{aligned}
$$

So scalar QED contains three interaction types before loop counterterms are added:

$$
\mathcal L_\text{int}
=iqA_\mu\left[(\partial^\mu\Phi^\dagger)\Phi-\Phi^\dagger\partial^\mu\Phi\right]
+q^2A_\mu A^\mu\Phi^\dagger\Phi
-\frac{\lambda}{4}(\Phi^\dagger\Phi)^2.
$$

The first term is a derivative coupling to one photon. The second is the seagull coupling to two photons. The third is the local scalar self-interaction.

This is the main lesson of the model:

$$
\boxed{
\text{Gauge invariance fixes the one-photon and two-photon scalar couplings together.}
}
$$

You cannot keep the derivative coupling and delete the seagull term without breaking local gauge invariance.

## The scalar current

The electromagnetic current is obtained by varying the matter Lagrangian with respect to $A_\mu$:

$$
\delta\mathcal L_\text{matter}=-j^\mu\delta A_\mu.
$$

For scalar QED, this gives

$$
\boxed{
 j^\mu
=iq\left[\Phi^\dagger D^\mu\Phi-(D^\mu\Phi)^\dagger\Phi\right].
}
$$

In terms of ordinary derivatives,

$$
j^\mu
=iq\left[\Phi^\dagger\partial^\mu\Phi-(\partial^\mu\Phi^\dagger)\Phi\right]
-2q^2A^\mu\Phi^\dagger\Phi.
$$

The current depends explicitly on the gauge field. This feels strange if your only previous current was the free complex-scalar current, but it is exactly what gauge invariance demands. The seagull term is the current's explicit $A_\mu$ dependence in diagrammatic form.

The Maxwell equation is

$$
\partial_\nu F^{\nu\mu}=j^\mu.
$$

The scalar equation of motion is

$$
D_\mu D^\mu\Phi + m^2\Phi + \frac{\lambda}{2}(\Phi^\dagger\Phi)\Phi=0.
$$

The factor $\lambda/2$ comes from differentiating $\frac{\lambda}{4}(\Phi^\dagger\Phi)^2$ with respect to $\Phi^\dagger$.

## Momentum-space rules

In Feynman gauge, after adding the gauge-fixing term

$$
\mathcal L_\text{gf}=-\frac12(\partial_\mu A^\mu)^2,
$$

the photon propagator is

$$
\frac{-ig_{\mu\nu}}{k^2+i\epsilon}.
$$

The scalar propagator is

$$
\frac{i}{p^2-m^2+i\epsilon}.
$$

With all momenta entering the vertex, and with $p_\dagger$ the momentum entering on the $\Phi^\dagger$ leg and $p$ the momentum entering on the $\Phi$ leg, the one-photon scalar vertex is

$$
\boxed{i q(p_\dagger-p)^\mu.}
$$

Equivalently, if one follows a scalar charge arrow through the vertex, many books write the same rule as a multiple of $(p+p')^\mu$, where $p$ and $p'$ are the incoming and outgoing scalar momenta. The overall sign depends on the charge-flow and covariant-derivative convention.

The seagull vertex with two photons is

$$
\boxed{2iq^2g^{\mu\nu}.}
$$

The quartic scalar vertex is

$$
\boxed{-i\lambda.}
$$

These rules are not independent decorations. They are the perturbative expansion of a single gauge-invariant term.

## Why the seagull term matters

Consider scalar Compton scattering,

$$
\Phi+\gamma\to\Phi+\gamma.
$$

There are three tree diagrams:

1. photon absorption followed by photon emission,
2. photon emission followed by photon absorption,
3. the seagull contact diagram.

The first two diagrams alone are not gauge invariant. When an external polarization vector is replaced by its photon momentum,

$$
\epsilon_\mu(k)\to k_\mu,
$$

the derivative-vertex diagrams leave a leftover term. The seagull diagram cancels it. That cancellation is the tree-level Ward identity in action.

The same point appears in pair annihilation,

$$
\Phi+\Phi^\dagger\to\gamma+\gamma.
$$

The two scalar-exchange diagrams and the seagull diagram form one gauge-invariant set. Dropping the contact diagram spoils transversality of the amplitude.

A nice way to say the lesson:

$$
\boxed{
\text{Gauge invariance is a statement about sums of diagrams, not usually about single diagrams.}
}
$$

## Comparison with spinor QED

Spinor QED has the Dirac kinetic term

$$
\overline\psi i\gamma^\mu D_\mu\psi,
$$

which is first order in $D_\mu$. Expanding it gives a one-photon vertex but no minimal two-photon contact term.

Scalar QED has

$$
(D_\mu\Phi)^\dagger D^\mu\Phi,
$$

which is second order in $D_\mu$. Expanding it gives both one-photon and two-photon interactions.

| Feature | Scalar QED | Spinor QED |
|---|---|---|
| matter field | complex scalar $\Phi$ | Dirac spinor $\psi$ |
| kinetic operator | second order | first order |
| one-photon vertex | yes | yes |
| two-photon seagull | yes | no minimal seagull |
| spin sums | none for matter | gamma-matrix traces |
| self-interaction needed for closure | scalar quartic | no analogous electron quartic at dimension four |

This makes scalar QED pedagogically valuable. It is technically simpler than spinor QED in some ways because there are no gamma matrices, but technically richer in another way because gauge invariance ties together multiple vertex types.

## Renormalizable closure

In four dimensions,

$$
[\Phi]=1,
\qquad
[A_\mu]=1,
\qquad
[q]=0,
\qquad
[\lambda]=0.
$$

The gauge coupling and quartic scalar coupling are both dimensionless. For a complete renormalizable scalar QED model, the quartic term must be included unless a larger symmetry or special embedding forbids or relates it.

Why? Photon loops and scalar loops generate local four-scalar divergences. Coleman highlights this in scalar electrodynamics: diagrams involving the seagull coupling and derivative couplings produce logarithmic four-scalar divergences, so a local $(\Phi^\dagger\Phi)^2$ counterterm is required. Srednicki makes the same point directly by including the quartic term in the scalar electrodynamics Lagrangian.

Thus scalar QED is naturally a two-coupling model:

$$
(q,\lambda).
$$

This is analogous to Yukawa theory, where a scalar-fermion vertex usually forces the scalar sector to be included consistently.

## Gauge fixing and ghosts

The path integral for scalar QED formally contains the volume of the gauge group:

$$
Z=\int \mathcal D A\,\mathcal D\Phi\,\mathcal D\Phi^\dagger\,e^{iS[A,\Phi]}.
$$

To define perturbation theory, choose a gauge. A covariant family is

$$
\mathcal L_\text{gf}=-\frac{1}{2\xi}(\partial_\mu A^\mu)^2.
$$

Then the photon propagator is

$$
D_{\mu\nu}(k)
=\frac{-i}{k^2+i\epsilon}
\left[g_{\mu\nu}-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}\right].
$$

For an Abelian theory with ordinary covariant gauges, the Faddeev–Popov determinant is field independent, so ghosts decouple from perturbative scalar QED. This is very different from non-Abelian gauge theory, where ghosts interact with gauge bosons.

## Loop anatomy

Scalar QED has the standard loop structures of an interacting gauge theory:

| Diagram type | What it corrects | Why it matters |
|---|---|---|
| scalar loop with two photons | photon self-energy | charge renormalization and vacuum polarization |
| photon loop on scalar line | scalar self-energy | mass and field renormalization |
| vertex correction | scalar charge vertex | Ward identities constrain renormalization |
| seagull tadpole | scalar or photon two-point terms | contact vertices contribute to counterterms |
| four-scalar loop graphs | scalar quartic coupling | shows why $\lambda$ is needed |

Gauge invariance strongly constrains the counterterms. They must be expressible in terms of gauge-invariant local operators such as

$$
F_{\mu\nu}F^{\mu\nu},
\qquad
(D_\mu\Phi)^\dagger D^\mu\Phi,
\qquad
\Phi^\dagger\Phi,
\qquad
(\Phi^\dagger\Phi)^2.
$$

The full one-loop renormalization of scalar QED belongs in the later renormalization and QED sections, but the structural point belongs here: local gauge invariance organizes the divergences.

## Broken phase and Abelian Higgs preview

If the scalar mass parameter is negative,

$$
m^2<0,
$$

the potential

$$
V(\Phi)=m^2\Phi^\dagger\Phi+\frac{\lambda}{4}(\Phi^\dagger\Phi)^2
$$

has a circle of classical minima. Choosing one can be written as

$$
\Phi(x)=\frac{1}{\sqrt2}\left[v+h(x)\right]e^{i\theta(x)/v}.
$$

Because the phase $\theta$ is gauge dependent, it is not a physical Goldstone boson in the gauge theory. The gauge field becomes massive: this is the Abelian Higgs mechanism. That is not the main topic of this page, but scalar QED is the parent model from which the Abelian Higgs model is obtained by choosing the broken phase.

The careful lesson is not “gauge symmetry is spontaneously broken” in the same sense as a global symmetry. Gauge redundancy is not a physical symmetry relating different states; gauge-invariant statements are about the spectrum and observables after choosing a vacuum and gauge.

## What the model teaches

| Idea | How it appears in scalar QED |
|---|---|
| local gauge covariance | ordinary derivatives become covariant derivatives |
| charged matter | $\Phi$ and $\Phi^\dagger$ carry opposite charges |
| seagull term | $q^2A^2\Phi^\dagger\Phi$ |
| Ward identities | external photon replacements cancel only in diagram sums |
| gauge fixing | needed to invert the photon kinetic operator |
| ghost decoupling | Abelian Faddeev–Popov determinant is field independent |
| renormalizable closure | scalar quartic coupling is required |
| Higgs preview | broken scalar phase gives a massive gauge boson |

## Common pitfalls

### Dropping the seagull vertex

The seagull vertex is forced by $|D\Phi|^2$. Deleting it breaks gauge invariance and spoils Ward identities.

### Treating the scalar current as the free current

The gauge-invariant scalar current contains the covariant derivative. Written in ordinary derivatives, it has an explicit $A_\mu$ term.

### Forgetting charge arrows

Complex scalar lines carry charge flow. Joining scalar lines without respecting the charge arrow gives wrong signs or forbidden vertices.

### Confusing scalar QED with a real charged scalar

A single real scalar cannot carry a nonzero ordinary Abelian charge. Charged scalar matter is complex, or more generally comes in real multiplets that combine into complex charge eigenstates.

### Omitting the quartic coupling

The quartic scalar coupling is part of the renormalizable closure of scalar QED. Even if absent at a chosen scale by hand, loops generally regenerate it unless protected by additional structure.

### Saying the gauge symmetry is physically broken

In the Abelian Higgs regime, the gauge-fixed fields may make the symmetry look broken, but gauge redundancy itself is not an ordinary physical symmetry. The physical claim is about the massive vector spectrum and gauge-invariant observables.

## Relation to other topics

- [Charged Matter](/foundations/gauge-fields-first-principles/charged-matter/) introduces the covariant derivative and the scalar current.
- [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/) supplies the Abelian gauge field and field strength.
- [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) explains why replacing a photon polarization by its momentum gives zero for physical amplitudes.
- [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/) explains how to invert the photon kinetic operator.
- [φ⁴ Theory](/foundations/foundational-models/phi-four-theory/) supplies the scalar self-interaction that scalar QED needs.
- [QED Preview](/foundations/foundational-models/qed-preview/) compares scalar QED with the more physical spinor QED of electrons and photons.
- Gauge Theories and the Standard Model will treat scalar electrodynamics, Abelian Higgs theory, and electroweak symmetry breaking in more detail.

## Research status

Perturbative scalar QED, its Feynman rules, Ward identities, gauge fixing, and renormalizable counterterm structure are textbook-standard. The model is usually studied as a pedagogical laboratory, an effective theory for charged spin-zero particles, or the unbroken-phase parent of the Abelian Higgs model. As always with gauge theories, nonperturbative definitions require a regulator and careful treatment of gauge redundancy.

## Exercises

### Exercise 1: Covariant transformation

Show that if

$$
\Phi\mapsto e^{-iq\alpha}\Phi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
$$

then

$$
D_\mu\Phi\mapsto e^{-iq\alpha}D_\mu\Phi.
$$

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
\begin{aligned}
D'_\mu\Phi'
&=(\partial_\mu+iqA_\mu+iq\partial_\mu\alpha)(e^{-iq\alpha}\Phi) \\
&=e^{-iq\alpha}\partial_\mu\Phi-iq(\partial_\mu\alpha)e^{-iq\alpha}\Phi
+iqA_\mu e^{-iq\alpha}\Phi
+iq(\partial_\mu\alpha)e^{-iq\alpha}\Phi \\
&=e^{-iq\alpha}(\partial_\mu+iqA_\mu)\Phi.
\end{aligned}
$$

Thus $D_\mu\Phi$ transforms like $\Phi$.

</details>

### Exercise 2: Expand the kinetic term

Expand

$$
(D_\mu\Phi)^\dagger D^\mu\Phi
$$

with $D_\mu=\partial_\mu+iqA_\mu$.

<details>
<summary><strong>Solution</strong></summary>

Since

$$
(D_\mu\Phi)^\dagger=\partial_\mu\Phi^\dagger-iqA_\mu\Phi^\dagger,
$$

we get

$$
(D_\mu\Phi)^\dagger D^\mu\Phi
=\partial_\mu\Phi^\dagger\partial^\mu\Phi
+iqA_\mu[(\partial^\mu\Phi^\dagger)\Phi-\Phi^\dagger\partial^\mu\Phi]
+q^2A_\mu A^\mu\Phi^\dagger\Phi.
$$

The last term is the seagull interaction.

</details>

### Exercise 3: Current from variation

Use

$$
\delta\mathcal L_\text{matter}=-j^\mu\delta A_\mu
$$

to derive the scalar QED current.

<details>
<summary><strong>Solution</strong></summary>

Vary the matter kinetic term:

$$
\delta D_\mu\Phi=iq(\delta A_\mu)\Phi,
\qquad
\delta(D_\mu\Phi)^\dagger=-iq(\delta A_\mu)\Phi^\dagger.
$$

Then

$$
\begin{aligned}
\delta\mathcal L_\text{matter}
&=(\delta D_\mu\Phi)^\dagger D^\mu\Phi+(D_\mu\Phi)^\dagger\delta D^\mu\Phi \\
&=-iq\delta A_\mu\Phi^\dagger D^\mu\Phi
+iq\delta A_\mu(D^\mu\Phi)^\dagger\Phi.
\end{aligned}
$$

Therefore

$$
j^\mu=iq[\Phi^\dagger D^\mu\Phi-(D^\mu\Phi)^\dagger\Phi].
$$

</details>

### Exercise 4: Engineering dimensions

Find the dimensions of $q$ and $\lambda$ in four dimensions.

<details>
<summary><strong>Solution</strong></summary>

From the kinetic terms,

$$
[A_\mu]=1,
\qquad
[\Phi]=1.
$$

The one-photon interaction has operator dimension

$$
[A_\mu]+[\Phi]+[\partial\Phi]=1+1+2=4,
$$

so

$$
[q]=0.
$$

The quartic scalar operator has dimension

$$
[(\Phi^\dagger\Phi)^2]=4,
$$

so

$$
[\lambda]=0.
$$

Both couplings are dimensionless in four dimensions.

</details>

### Exercise 5: Why no charged real scalar?

Explain why a single real scalar field cannot carry a nonzero ordinary Abelian charge.

<details>
<summary><strong>Solution</strong></summary>

A charged Abelian transformation multiplies a field by a phase:

$$
\Phi\mapsto e^{-iq\alpha}\Phi.
$$

For $q\ne0$ and generic $\alpha$, this turns a real field into a complex field. A single real scalar can at most transform by discrete signs under an ordinary one-dimensional real representation of $U(1)$, but continuous $U(1)$ has no nontrivial one-dimensional real charge representation. Charged scalar matter must therefore be complex, or built from at least two real fields forming a complex combination.

</details>

### Exercise 6: Ward identity at tree level

In scalar Compton scattering, explain why the seagull graph must be included for the Ward identity.

<details>
<summary><strong>Solution</strong></summary>

The derivative scalar-photon vertex is proportional to scalar momenta. Replacing an external photon polarization by its momentum contracts the vertex with $k_\mu$ and turns adjacent scalar propagators into differences of inverse propagators. In a sum of the two exchange diagrams, most terms cancel, but a local leftover remains. The seagull contact diagram contributes precisely the local term needed to cancel that leftover. Thus the gauge-invariant amplitude obeys

$$
\mathcal M(\epsilon_\mu\to k_\mu)=0,
$$

but the exchange diagrams alone generally do not.

</details>

## Sources and further reading

- Mark Srednicki, *Quantum Field Theory*, §§58, 61, and 65–68, for photon Feynman rules, scalar electrodynamics, scalar QED loop corrections, and Ward identities.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 27, 30–31, and 33, for minimal coupling, scalar electrodynamics Feynman rules, Faddeev–Popov gauge fixing, and the renormalizable closure of scalar electrodynamics.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 8–12, for electrodynamics, path integrals, Ward identities, and renormalization logic.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*, ch. 9, for scalar QED, Ward identities, and gauge invariance in perturbation theory.
- Anthony Zee, *Quantum Field Theory in a Nutshell*, chs. III.4 and VII.1, for gauge invariance, Faddeev–Popov ideas, and the scalar versus spinor contrast.

## Version history

- **2026-05-24:** Initial qft.org foundational model page for scalar QED: covariant derivative, scalar current, one-photon and seagull vertices, Ward-identity role, gauge fixing, renormalizable closure, Abelian Higgs preview, pitfalls, and exercises.
