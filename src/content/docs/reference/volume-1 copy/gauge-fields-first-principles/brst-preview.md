---
title: "BRST Preview"
description: "A first-principles preview of BRST symmetry: ghosts, antighosts, auxiliary fields, nilpotence, BRST-exact gauge fixing, Slavnov–Taylor identities, physical cohomology, and anomaly caveats."
sidebar:
  label: "BRST Preview"
  order: 6
---

## Summary

Gauge fixing hides the original local gauge redundancy. **BRST symmetry** is the symmetry that remains after gauge fixing when ghosts are included.

For a Yang–Mills theory, the gauge-fixed path integral contains the gauge field $A_\mu$, matter fields, ghost fields $c$, antighost fields $\bar c$, and an auxiliary field $B$. The BRST differential $s$ acts like a gauge transformation whose infinitesimal gauge parameter has been replaced by the ghost field:

$$
\boxed{sA_\mu=D_\mu c.}
$$

But this is not just a gauge transformation with a funny parameter. The ghost also transforms:

$$
\boxed{sc=-igc^2,}
$$

and the antighost–auxiliary pair transforms as

$$
\boxed{s\bar c=B,\qquad sB=0.}
$$

These rules are chosen so that

$$
\boxed{s^2=0.}
$$

That nilpotence is the whole magic trick. It lets us organize gauge fixing as a BRST-exact deformation,

$$
\boxed{S_\text{tot}=S_0+s\Psi,}
$$

where $S_0$ is the original gauge-invariant action and $\Psi$ is a gauge-fixing fermion. Physical operators and physical states are then described by BRST cohomology: BRST-closed objects modulo BRST-exact ones. The phrase sounds fancy, but the idea is simple: a BRST-exact change is a change of gauge description, not a change of physics.

BRST symmetry was discovered by Becchi, Rouet, and Stora, and independently by Tyutin. Weinberg presents it as the exact symmetry that survives gauge fixing and as the tool that replaces the hidden gauge symmetry in proofs of renormalizability and gauge independence (Weinberg 1996, §§15.7–15.9). Srednicki uses BRST symmetry to derive Slavnov–Taylor identities and to show that unphysical gluon polarizations and ghost-created states decouple from physical amplitudes (Srednicki 2007, §74). Coleman’s lectures introduce the historical role of Slavnov–Taylor identities and the BRST transformation in the renormalization of Yang–Mills theory (Coleman 2019, ch. 47).

<figure class="doc-figure" style="--figure-width: 54rem;">

![BRST as the symmetry of gauge-fixed Yang–Mills theory](/figures/foundations/brst-cohomology-map.svg)

<figcaption>

BRST symmetry packages gauge fixing into the nilpotent differential $s$. The gauge-fixed action has the form $S_0+s\Psi$, the Slavnov–Taylor identities express BRST invariance of the quantum theory, and physical information lives in the ghost-number-zero cohomology of $s$ or of the BRST charge $Q_{\mathrm B}$.

</figcaption>
</figure>

## Prerequisites

You should know [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/), [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/), [Non-Abelian Preview](/foundations/gauge-fields-first-principles/non-abelian-preview/), [Grassmann Variables](/foundations/path-integral-formalism/grassmann-variables/), [Fermionic Path Integral](/foundations/path-integral-formalism/fermionic-path-integral/), [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/), and [Path Integral Measure](/foundations/path-integral-formalism/path-integral-measure/).

:::note[Conventions]
We keep the qft.org non-Abelian convention

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c.
$$

Matter multiplets transform as $\Phi\mapsto U\Phi$, with

$$
U(x)=\exp[-ig\alpha^a(x)T^a].
$$

The corresponding infinitesimal gauge variation of the connection is

$$
\delta_\alpha A_\mu=D_\mu\alpha
=\partial_\mu\alpha-ig[\alpha,A_\mu].
$$

BRST replaces the ordinary gauge parameter $\alpha$ by the Grassmann-odd ghost field $c=c^aT^a$.
:::

:::note[Scope]
This is a conceptual preview. It explains why BRST symmetry exists, how its basic transformations work, and why physical information is cohomological. It does not develop the full Slavnov–Taylor machinery, Zinn–Justin equation, Batalin–Vilkovisky formalism, anti-BRST symmetry, algebraic renormalization, or anomaly classification.
:::

## Why a new symmetry appears

The original Yang–Mills action is invariant under local gauge transformations. But to define perturbation theory we must choose a gauge. For example, in a Lorenz-type covariant gauge we add terms that depend on

$$
G^a[A]=\partial^\mu A_\mu^a.
$$

That gauge-fixing term is deliberately not gauge invariant. If it were gauge invariant, it would not fix the gauge. So after gauge fixing, the original local gauge symmetry is no longer manifest.

This creates a problem. Gauge symmetry was not just decorative. It was the reason the theory had the right number of physical degrees of freedom. It also constrained counterterms, enforced relations among amplitudes, and protected gauge-parameter independence. If the gauge-fixed Lagrangian appears to have lost that structure, what prevents perturbation theory from wandering into nonsense?

BRST symmetry is the answer. The gauge-fixed action is not invariant under the old gauge transformation. It is invariant under a new fermionic symmetry that mixes gauge fields, ghosts, antighosts, and auxiliary fields. This symmetry is weak enough to allow gauge fixing, but strong enough to remember the original gauge redundancy.

## The ghost as a gauge parameter

Start with the gauge variation

$$
\delta_\alpha A_\mu=D_\mu\alpha.
$$

The BRST idea is to replace the infinitesimal gauge parameter $\alpha$ by a Grassmann-odd field $c$:

$$
\boxed{sA_\mu=D_\mu c.}
$$

Here $s$ is not an ordinary infinitesimal variation with a numerical parameter. It is an odd derivation: it changes Grassmann parity and raises ghost number by one.

For a matter field $\Phi$ in representation $R$,

$$
\boxed{s\Phi=-igc\Phi,}
$$

where $c=c^aT_R^a$ in that representation. For a conjugate field,

$$
\boxed{s\Phi^\dagger=ig\Phi^\dagger c.}
$$

In components, the gauge-field rule reads

$$
\boxed{
(sA_\mu)^a
=\partial_\mu c^a+g f^{abc}c^bA_\mu^c.
}
$$

This already looks like a gauge transformation. The difference is that $c^a(x)$ is a field integrated over in the path integral, not an externally chosen function.

## Ghost number

The ghost fields carry a bookkeeping charge called **ghost number**:

| Field | Grassmann parity | Ghost number |
|---|---:|---:|
| $A_\mu^a$, matter fields | even or ordinary matter parity | 0 |
| $c^a$ | odd | +1 |
| $\bar c^a$ | odd | −1 |
| $B^a$ | even | 0 |
| $s$ | odd | +1 |

Physical operators usually have ghost number zero. The ghost number is not an electric charge or a color charge. It is a grading that keeps track of the gauge-fixing complex.

The fact that $s$ raises ghost number by one is why a BRST-exact action deformation can be written as

$$
s\Psi,
$$

where $\Psi$ has ghost number $-1$. The object $\Psi$ is called a **gauge-fixing fermion** because it is Grassmann odd.

## The ghost transformation

If $sA_\mu=D_\mu c$ is to define a genuine symmetry, the ghost itself must transform. With our conventions,

$$
\boxed{sc=-igc^2.}
$$

Because $c$ is Grassmann odd,

$$
c^2=c^a c^bT^aT^b
=\frac12c^ac^b[T^a,T^b]
=\frac{i}{2}f^{abc}c^ac^bT^c.
$$

So in components,

$$
\boxed{sc^a=\frac g2 f^{abc}c^bc^c.}
$$

This formula is the ghost-field version of the non-Abelian gauge algebra. In an Abelian theory, $f^{abc}=0$, so

$$
sc=0.
$$

That is why Abelian BRST symmetry is much simpler.

## Nilpotence

The crucial property is

$$
\boxed{s^2=0.}
$$

For matter fields, the check is short. Since $s$ is an odd derivation,

$$
s(c\Phi)=(sc)\Phi-c(s\Phi).
$$

Using

$$
s\Phi=-igc\Phi,
\qquad
sc=-igc^2,
$$

we get

$$
\begin{aligned}
s^2\Phi
&=s(-igc\Phi) \\
&=-ig(sc)\Phi+igc(s\Phi) \\
&=-ig(-igc^2)\Phi+igc(-igc\Phi) \\
&=0.
\end{aligned}
$$

For the gauge field, the same result follows from the Jacobi identity of the Lie algebra. In matrix notation,

$$
sA_\mu=\partial_\mu c-ig[c,A_\mu],
\qquad
sc=-igc^2.
$$

Applying $s$ again gives terms involving $\partial_\mu(c^2)$ and commutators of $A_\mu$ with $c^2$; the Grassmann signs and the Jacobi identity cancel them. The result is

$$
s^2A_\mu=0.
$$

Nilpotence is not a minor algebraic curiosity. It is the reason BRST-exact terms do not change the physical content and the reason physical states can be described by a cohomology.

## Antighosts and the auxiliary field

Gauge fixing requires an antighost field $\bar c^a$ and an auxiliary bosonic field $B^a$, often called the Nakanishi–Lautrup field. Their BRST transformations are

$$
\boxed{s\bar c^a=B^a,\qquad sB^a=0.}
$$

This pair is deliberately simple. Since

$$
s^2\bar c^a=sB^a=0,
$$

it fits into the nilpotent BRST complex.

The pair $(\bar c,B)$ is not a new physical sector. It is a bookkeeping pair for gauge fixing. In cohomological language it is a trivial pair: one field is the BRST image of the other, so it does not contribute independent physical observables.

## Gauge fixing as a BRST-exact term

For a covariant Yang–Mills gauge, choose the gauge-fixing fermion

$$
\boxed{
\Psi=\int d^4x\,\bar c^a
\left(\partial^\mu A_\mu^a+\frac\xi2 B^a\right).
}
$$

Then

$$
S_\text{tot}=S_0+s\Psi.
$$

The BRST variation of the gauge-fixing fermion gives

$$
\begin{aligned}
\mathcal L_\text{gf+gh}
&=s\left[\bar c^a
\left(\partial^\mu A_\mu^a+\frac\xi2B^a\right)\right] \\
&=B^a\partial^\mu A_\mu^a
+\frac\xi2B^aB^a
-\bar c^a\partial^\mu(D_\mu c)^a.
\end{aligned}
$$

The $B$ field is auxiliary: it has no derivatives. Its equation of motion is

$$
B^a=-\frac1\xi\partial^\mu A_\mu^a.
$$

Substituting it back gives

$$
\boxed{
\mathcal L_\text{gf+gh}
=-\frac1{2\xi}(\partial^\mu A_\mu^a)^2
-\bar c^a\partial^\mu(D_\mu c)^a.
}
$$

This is exactly the covariant gauge-fixing term plus the Faddeev–Popov ghost term. The BRST form explains why these two terms belong together. Gauge fixing and ghosts are not independent hacks; they are the two pieces of one BRST-exact expression.

## BRST invariance of the gauge-fixed action

The original action $S_0$ is gauge invariant. Since BRST acts on $A_\mu$ and matter as a gauge transformation with parameter $c$, we have

$$
sS_0=0.
$$

The gauge-fixing part is $s\Psi$, so

$$
s(s\Psi)=s^2\Psi=0.
$$

Therefore

$$
\boxed{sS_\text{tot}=0.}
$$

This is the cleanest way to say the point: the gauge-fixed action is not gauge invariant, but it is BRST invariant.

## The Abelian limit

In QED, the gauge group is Abelian. Then

$$
sA_\mu=\partial_\mu c,
\qquad
sc=0,
\qquad
s\psi=-iqc\psi.
$$

For Lorenz gauge,

$$
\mathcal L_\text{gh}=-\bar c\,\partial^2 c.
$$

The ghost fields are free and do not couple to $A_\mu$. In normalized QED correlators they usually disappear into the normalization. BRST symmetry is still present, but it is much less visible because the ghosts decouple.

In non-Abelian theory, by contrast,

$$
D_\mu c=\partial_\mu c+\text{terms involving }A_\mu c,
$$

so the ghost Lagrangian contains ghost-gauge interactions. This is why ghost loops appear in Yang–Mills Feynman diagrams.

## Physical observables as cohomology

BRST symmetry suggests the following rule:

$$
\boxed{\text{physical observables are BRST-closed modulo BRST-exact operators.}}
$$

A BRST-closed operator satisfies

$$
s\mathcal O=0.
$$

A BRST-exact operator has the form

$$
\mathcal O=s\mathcal X.
$$

Since $s^2=0$, every exact operator is automatically closed. The physical information is the quotient

$$
\boxed{
H^0(s)=
\frac{\{\mathcal O:\operatorname{gh}(\mathcal O)=0,\ s\mathcal O=0\}}
{\{sX:\operatorname{gh}(X)=-1\}}.
}
$$

In plain language: BRST-closed ghost-number-zero operators respect the gauge redundancy, while BRST-exact changes are pure gauge bookkeeping. Two operators that differ by a BRST-exact term represent the same physical observable.

Gauge-invariant local operators, such as

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}),
\qquad
\bar\psi\psi,
\qquad
\bar\psi\gamma^\mu D_\mu\psi,
$$

are BRST closed. BRST cohomology is the gauge-fixed way of saying which operators are genuinely physical.

## Physical states and the BRST charge

In canonical language, BRST symmetry has a conserved charge $Q_\mathrm B$. It is fermionic and nilpotent:

$$
\boxed{Q_\mathrm B^2=0.}
$$

Physical states are taken to satisfy

$$
\boxed{Q_\mathrm B|\mathrm{phys}\rangle=0.}
$$

States that differ by a BRST-exact state are identified:

$$
|\mathrm{phys}\rangle
\sim
|\mathrm{phys}\rangle+Q_\mathrm B|\chi\rangle.
$$

This removes unphysical gauge modes. In a covariant photon or gluon quantization, intermediate formulas contain longitudinal, timelike, ghost, and antighost states. BRST cohomology is the systematic way to say which combinations survive as physical states.

For a photon, the familiar equivalence

$$
\varepsilon^\mu(k)\sim \varepsilon^\mu(k)+\alpha k^\mu
$$

is the elementary shadow of this idea. The longitudinal polarization shift is not a new physical photon. It is a change of representative.

## Slavnov–Taylor identities

Ward identities are the correlation-function consequences of symmetries. After gauge fixing, the original local gauge symmetry is hidden, so the identities are most naturally written as consequences of BRST symmetry. In non-Abelian gauge theory, these are the **Slavnov–Taylor identities**.

They do several jobs:

| Role | Meaning |
|---|---|
| Gauge-parameter independence | Physical quantities do not depend on the choice of $\xi$ or on small changes of the gauge-fixing fermion. |
| Ghost cancellation | Unphysical gauge modes and ghost states cancel from physical amplitudes. |
| Renormalization constraints | Counterterms must respect BRST symmetry, not arbitrary gauge-fixed power counting. |
| Non-Abelian Ward identities | Vertex and propagator renormalizations obey relations required by the gauge structure. |

For Foundations, the important lesson is this:

$$
\boxed{\text{BRST symmetry is the gauge-fixed form of gauge redundancy.}}
$$

It is not an extra physical symmetry of nature, like a global flavor symmetry. It is the algebraic remnant of the fact that the gauge field description contains redundant variables.

## Gauge-fixing independence

Suppose we change the gauge-fixing fermion,

$$
\Psi\mapsto \Psi+\delta\Psi.
$$

Then the action changes by

$$
\delta S=s(\delta\Psi).
$$

For a BRST-closed observable $\mathcal O$, the formal change in its expectation value is proportional to an expectation value of a BRST-exact insertion:

$$
\delta\langle\mathcal O\rangle
\propto
\langle \mathcal O\,s(\delta\Psi)\rangle.
$$

If the path-integral measure is BRST invariant, this vanishes for physical observables. This is the compact path-integral reason that changing the gauge-fixing convention does not change the physics.

The assumptions matter. If the measure fails to be invariant, the BRST identity can acquire an anomaly. For a dynamical gauge symmetry, such an anomaly is not a small correction; it is a consistency problem.

## Anomaly caveat

Classically, a gauge-fixed action may be BRST invariant. Quantum mechanically, the path-integral measure also has to respect the BRST transformation. If the measure changes anomalously, the Slavnov–Taylor identity is broken.

For a global symmetry, an anomaly can be a physical feature. For a gauge symmetry, an anomaly usually signals that the theory is inconsistent unless the matter content cancels it. This is why gauge-anomaly cancellation is a structural requirement in the Standard Model and in any consistent chiral gauge theory.

At this Foundations level, keep the slogan:

$$
\boxed{\text{Gauge anomaly} = \text{failure of quantum BRST symmetry}.}
$$

The full anomaly story belongs in the later Symmetry, Anomalies, and Topology group.

## Geometric picture

Gauge transformations form directions along a gauge orbit in field-configuration space. Gauge fixing chooses a local slice through those orbits. Ghosts encode infinitesimal motion along the orbit. Antighosts and auxiliary fields encode the choice of slice.

BRST puts this picture into one differential:

$$
\text{move along orbit}\quad\longrightarrow\quad s.
$$

Because moving along a gauge orbit twice in the cohomological sense gives no new physical direction,

$$
s^2=0.
$$

That is why BRST language feels more like differential geometry than ordinary group representation theory. The ghost is morally a one-form along the gauge orbit, and BRST cohomology identifies gauge-invariant information on the quotient space of fields modulo gauge transformations.

## Common pitfalls

**Pitfall 1: Calling BRST an ordinary physical symmetry.** BRST is a symmetry of the gauge-fixed description. It remembers gauge redundancy; it does not relate distinct physical configurations the way an ordinary global symmetry does.

**Pitfall 2: Treating ghosts as physical particles.** Ghost fields are integrated over in the path integral and run in internal loops, but they are not allowed as external physical states.

**Pitfall 3: Forgetting the ghost transformation.** Replacing the gauge parameter by $c$ gives $sA=Dc$, but nilpotence requires $sc=-igc^2$ in a non-Abelian theory.

**Pitfall 4: Thinking gauge fixing and ghosts are unrelated.** In BRST form, they are one object: $s\Psi$.

**Pitfall 5: Assuming BRST always survives quantization.** A gauge anomaly is precisely an obstruction to quantum BRST invariance.

**Pitfall 6: Confusing BRST exact with zero as an operator identity.** A BRST-exact operator need not be literally zero. It is physically trivial inside BRST cohomology and in physical matrix elements under the usual assumptions.

## Relations to nearby pages

- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) explains why gauge transformations are redundancy rather than ordinary symmetry.
- [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/) introduces gauge slices and the Faddeev–Popov determinant.
- [Non-Abelian Preview](/foundations/gauge-fields-first-principles/non-abelian-preview/) introduces the Yang–Mills covariant derivative and ghost interactions.
- [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) gives the general symmetry-to-identity logic that BRST refines into Slavnov–Taylor identities.
- [Path Integral Measure](/foundations/path-integral-formalism/path-integral-measure/) previews why a symmetry of the action can fail if the measure has a nontrivial Jacobian.
- Later gauge-theory pages will develop full Yang–Mills quantization, Slavnov–Taylor identities, gauge anomalies, BRST cohomology, and the Batalin–Vilkovisky formalism.

## Exercises

### Exercise 1: Abelian BRST nilpotence

In Abelian gauge theory, take

$$
sA_\mu=\partial_\mu c,
\qquad
sc=0.
$$

Show that $s^2A_\mu=0$ and that $sF_{\mu\nu}=0$.

<details>
<summary><strong>Solution</strong></summary>

Since $sc=0$,

$$
s^2A_\mu=s(\partial_\mu c)=\partial_\mu(sc)=0.
$$

Also,

$$
sF_{\mu\nu}
=s(\partial_\mu A_\nu-\partial_\nu A_\mu)
=\partial_\mu\partial_\nu c-\partial_\nu\partial_\mu c=0.
$$

Thus the Abelian field strength is BRST invariant.

</details>

### Exercise 2: Matter-field nilpotence

For a non-Abelian matter multiplet, use

$$
s\Phi=-igc\Phi,
\qquad
sc=-igc^2.
$$

Show that $s^2\Phi=0$.

<details>
<summary><strong>Solution</strong></summary>

Because $s$ is odd,

$$
s(c\Phi)=(sc)\Phi-c(s\Phi).
$$

Therefore

$$
\begin{aligned}
s^2\Phi
&=s(-igc\Phi) \\
&=-ig(sc)\Phi+igc(s\Phi) \\
&=-ig(-igc^2)\Phi+igc(-igc\Phi) \\
&=-g^2c^2\Phi+g^2c^2\Phi=0.
\end{aligned}
$$

</details>

### Exercise 3: Eliminating the auxiliary field

Starting from

$$
\mathcal L_B=B^aG^a+\frac\xi2B^aB^a,
$$

where $G^a=\partial^\mu A_\mu^a$, eliminate $B^a$ and show that the result is the usual covariant gauge-fixing term.

<details>
<summary><strong>Solution</strong></summary>

The equation of motion for $B^a$ is

$$
G^a+\xi B^a=0,
$$

so

$$
B^a=-\frac1\xi G^a.
$$

Substituting back,

$$
\mathcal L_B
=-\frac1\xi G^aG^a+\frac\xi2\frac1{\xi^2}G^aG^a
=-\frac1{2\xi}G^aG^a.
$$

Thus

$$
\mathcal L_B=-\frac1{2\xi}(\partial^\mu A_\mu^a)^2.
$$

</details>

### Exercise 4: Ghost number of the gauge-fixing term

Assign

$$
\operatorname{gh}(c)=1,
\qquad
\operatorname{gh}(\bar c)=-1,
\qquad
\operatorname{gh}(B)=\operatorname{gh}(A)=0,
\qquad
\operatorname{gh}(s)=1.
$$

Show that $s\Psi$ has ghost number zero for

$$
\Psi=\int d^4x\,\bar c^a\left(G^a+\frac\xi2B^a\right).
$$

<details>
<summary><strong>Solution</strong></summary>

The factor $G^a+\frac\xi2B^a$ has ghost number zero, while $\bar c^a$ has ghost number $-1$. Therefore

$$
\operatorname{gh}(\Psi)=-1.
$$

Since $s$ has ghost number $+1$,

$$
\operatorname{gh}(s\Psi)=1+(-1)=0.
$$

This is necessary because the action must have ghost number zero.

</details>

### Exercise 5: BRST-exact insertions

Assume the path-integral measure and action are BRST invariant. Show formally that the expectation value of a BRST-exact insertion vanishes:

$$
\langle sX\rangle=0.
$$

<details>
<summary><strong>Solution</strong></summary>

Consider the change of variables generated by BRST in the path integral. If both the action and the measure are invariant, then the integral of a total BRST variation vanishes:

$$
0=s\int\mathcal D\Phi\,X e^{iS}
=\int\mathcal D\Phi\,(sX)e^{iS}
+i\int\mathcal D\Phi\,X(sS)e^{iS}.
$$

Since $sS=0$, the second term vanishes, leaving

$$
\int\mathcal D\Phi\,(sX)e^{iS}=0.
$$

After normalization,

$$
\langle sX\rangle=0.
$$

If the measure is anomalous, this argument can fail.

</details>

### Exercise 6: Why ghosts decouple in Abelian Lorenz gauge

For QED in Lorenz gauge, the ghost Lagrangian is

$$
\mathcal L_\text{gh}=-\bar c\partial^2c.
$$

Explain why ghost lines do not interact with photons.

<details>
<summary><strong>Solution</strong></summary>

The Lagrangian contains only a quadratic ghost kinetic term. There is no term involving $\bar c$, $c$, and $A_\mu$. Therefore the ghost propagator exists, but there is no ghost-photon vertex. In normalized QED correlation functions the free ghost determinant is an overall factor and cancels from physical ratios.

In Yang–Mills theory, $\partial^2$ is replaced by $\partial^\mu D_\mu[A]$, which contains $A_\mu$, so ghost-gauge vertices appear.

</details>

## Sources and further reading

- C. Becchi, A. Rouet, and R. Stora, “Renormalization of Gauge Theories,” *Annals of Physics* **98** (1976), for the original BRST formulation.
- I. V. Tyutin, Lebedev Institute preprint FIAN No. 39 (1975), for the independent discovery of the same symmetry.
- M. Srednicki, *Quantum Field Theory*, §74, for a concise derivation of BRST transformations in non-Abelian gauge theory and their use in Slavnov–Taylor identities.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, §§15.7–15.9, for BRST transformations, nilpotence, physical cohomology, gauge-fixing independence, and the Batalin–Vilkovisky extension.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 47, for the role of BRST transformations and Slavnov–Taylor identities in quantizing non-Abelian gauge fields.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §16.4, for the perturbative gauge-theory version of BRST and its use in proving gauge independence.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the algebraic and renormalization-theoretic role of BRST symmetry.

## Version history

- **2026-05-23:** Initial qft.org page on BRST symmetry, ghost number, nilpotence, BRST-exact gauge fixing, physical cohomology, Slavnov–Taylor identities, and anomaly caveats.
