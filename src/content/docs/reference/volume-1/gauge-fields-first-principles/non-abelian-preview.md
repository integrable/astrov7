---
title: "Non-Abelian Preview"
description: "A first-principles preview of non-Abelian gauge theory: local internal rotations, covariant derivatives, Yang–Mills field strength, self-interactions, matter representations, gauge fixing, and ghosts."
sidebar:
  label: "Non-Abelian Preview"
  order: 5
---

## Summary

A **non-Abelian gauge theory** is a gauge theory whose gauge transformations do not commute. Instead of one local phase rotation, as in Abelian QED, the fields carry a local internal orientation in a representation of a Lie group $G$. Making that local orientation arbitrary forces the introduction of a matrix-valued gauge potential,

$$
A_\mu(x)=A_\mu^a(x)T^a,
$$

and a covariant derivative. With qft.org's Abelian sign convention extended to non-Abelian fields, we use

$$
\boxed{D_\mu=\partial_\mu+igA_\mu.}
$$

If a matter multiplet transforms as

$$
\Phi(x)\mapsto U(x)\Phi(x),
\qquad
U(x)\in G,
$$

then the gauge field transforms so that

$$
\boxed{D_\mu\Phi\mapsto U(x)D_\mu\Phi.}
$$

The non-Abelian field strength is the curvature of this connection:

$$
\boxed{
F_{\mu\nu}=\frac{1}{ig}[D_\mu,D_\nu]
=\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu].
}
$$

The commutator term is the whole new thing. It makes the gauge bosons interact with themselves. With $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$, the Yang–Mills action is

$$
\boxed{
\mathcal L_\text{YM}
=-\frac12\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
=-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
}
$$

This page is a preview, not the full Yang–Mills course. The goal is to see what changes when the gauge group is non-Abelian: covariant derivatives carry matrices, the field strength contains a commutator, the pure gauge action contains cubic and quartic gauge-boson vertices, and covariant gauge fixing introduces interacting ghosts.

Weinberg's non-Abelian gauge-theory chapter gives the clean formal development: gauge transformations, structure constants, adjoint representation, covariant derivatives, field strengths, Yang–Mills Lagrangians, quantization, Faddeev–Popov ghosts, and BRST symmetry (Weinberg 1996, ch. 15). Coleman motivates the same structure by extending the Faddeev–Popov argument from QED to a gauge group with one gauge condition for each generator, and derives the ghost determinant $\det(\partial_\mu D^\mu)$ in Lorenz-like gauges (Coleman 2019, ch. 47). Srednicki's sections on non-Abelian symmetries, gauge theory, and Yang–Mills path integrals provide a concise calculation-oriented route (Srednicki 2007, sections 69–74).

<figure class="doc-figure" style="--figure-width: 56rem;">

![The non-Abelian gauge-theory map from local rotations to Yang–Mills action](/figures/foundations/nonabelian-gauge-theory-map.svg)

<figcaption>

A non-Abelian gauge theory promotes a global internal group $G$ to local rotations $U(x)$. The gauge field is a connection, the field strength is its curvature, and the Yang–Mills action contains self-interactions. Quantization requires gauge fixing, and in covariant gauges the Faddeev–Popov determinant becomes ghost dynamics.

</figcaption>
</figure>

## Prerequisites

You should know [Internal Symmetries](/foundations/symmetry-and-spacetime/internal-symmetries/), [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/), [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/), [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/), [Charged Matter](/foundations/gauge-fields-first-principles/charged-matter/), and [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/).

:::note[Conventions]
Let $T^a$ be Hermitian generators of a representation of $G$, normalized by

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}
$$

in the fundamental representation of $SU(N)$, and obeying

$$
[T^a,T^b]=if^{abc}T^c.
$$

qft.org extends the Abelian convention $D_\mu=\partial_\mu+iqA_\mu$ to

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a.
$$

With this convention,

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu].
$$

In components this is

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

Many books use $D_\mu=\partial_\mu-igA_\mu$; then the signs in the transformation law and in the component commutator term flip. The matrix equation is usually the safest way to compare conventions.
:::

:::note[Scope]
This page gives the first structural layer of non-Abelian gauge theory. It does not yet derive complete Yang–Mills Feynman rules, beta functions, confinement, Wilson loops, BRST cohomology, anomalies, spontaneous gauge-symmetry breaking, QCD, or the Standard Model.
:::

## From phases to internal frames

In Abelian gauge theory, the matter field can be multiplied by a local phase:

$$
\Phi(x)\mapsto e^{-iq\alpha(x)}\Phi(x).
$$

In a non-Abelian theory, the field is usually a multiplet,

$$
\Phi_i(x),
\qquad i=1,\ldots,\dim R,
$$

transforming in a representation $R$ of a Lie group $G$:

$$
\Phi(x)\mapsto U(x)\Phi(x),
\qquad
U(x)=\exp[-ig\alpha^a(x)T^a_R].
$$

The ordinary derivative fails for the same reason it failed in QED, but now the problem is matrix-valued:

$$
\partial_\mu(U\Phi)
=(\partial_\mu U)\Phi+U\partial_\mu\Phi.
$$

The extra term $(\partial_\mu U)\Phi$ means that ordinary differentiation compares fields using different local internal frames. The covariant derivative supplies the rule for parallel comparison in that internal space.

## The connection and its transformation law

Define

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a.
$$

We demand

$$
D_\mu'\Phi'=U D_\mu\Phi.
$$

Since $\Phi'=U\Phi$, this implies

$$
(\partial_\mu+igA_\mu')U\Phi
=U(\partial_\mu+igA_\mu)\Phi.
$$

For arbitrary $\Phi$,

$$
(\partial_\mu U)+igA_\mu'U=igUA_\mu.
$$

Therefore

$$
\boxed{
A_\mu'
=UA_\mu U^{-1}+\frac{i}{g}(\partial_\mu U)U^{-1}.
}
$$

This is the non-Abelian version of the Abelian shift $A_\mu\mapsto A_\mu+\partial_\mu\alpha$. The first term rotates the matrix $A_\mu$ in the internal space; the second term is the inhomogeneous connection term.

For infinitesimal

$$
U=1-ig\alpha+O(\alpha^2),
\qquad
\alpha=\alpha^aT^a,
$$

we get

$$
\delta A_\mu
=\partial_\mu\alpha-ig[\alpha,A_\mu].
$$

In components,

$$
\delta A_\mu^a
=\partial_\mu\alpha^a+g f^{abc}\alpha^b A_\mu^c
$$

with the convention stated above. This can be written as a covariant derivative acting on an adjoint-valued gauge parameter.

## Field strength as curvature

The field strength is defined by the commutator of covariant derivatives:

$$
[D_\mu,D_\nu]=igF_{\mu\nu}.
$$

Using $D_\mu=\partial_\mu+igA_\mu$ gives

$$
F_{\mu\nu}
=\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu].
$$

For an Abelian group, the commutator vanishes, and this reduces to the Maxwell field strength.

Under a gauge transformation,

$$
D_\mu'=UD_\mu U^{-1}.
$$

Therefore

$$
[D_\mu',D_\nu']=U[D_\mu,D_\nu]U^{-1},
$$

so

$$
\boxed{F_{\mu\nu}'=UF_{\mu\nu}U^{-1}.}
$$

This is covariant, not invariant. The matrix field strength rotates in the adjoint representation. Gauge-invariant local quantities are made by tracing over internal indices, for example

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

## The Yang–Mills action

The pure non-Abelian gauge-field Lagrangian is

$$
\mathcal L_\text{YM}
=-\frac12\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

Because $F_{\mu\nu}\mapsto UF_{\mu\nu}U^{-1}$, the trace is gauge invariant:

$$
\operatorname{tr}(F_{\mu\nu}'F'^{\mu\nu})
=\operatorname{tr}(UF_{\mu\nu}F^{\mu\nu}U^{-1})
=\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

With $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$,

$$
\mathcal L_\text{YM}
=-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
$$

The field strength contains two terms:

$$
F_{\mu\nu}^a
=(\partial A)^a_{\mu\nu}
-gf^{abc}A_\mu^bA_\nu^c.
$$

Squaring it gives

1. a quadratic kinetic term for gauge bosons;
2. a cubic term schematically of the form $g(\partial A)AA$;
3. a quartic term schematically of the form $g^2A^4$.

Thus non-Abelian gauge bosons interact with each other even in the absence of matter. This is the sharpest practical difference from Maxwell theory. Photons in pure QED do not self-couple at the classical Lagrangian level; gluons in pure Yang–Mills theory do.

## Equations of motion and Bianchi identity

Varying the Yang–Mills action gives the source-free equation

$$
\boxed{D_\mu F^{\mu\nu}=0.}
$$

With matter, it becomes

$$
\boxed{D_\mu F^{\mu\nu}=J^\nu,}
$$

where $J^\nu=J^{a\nu}T^a$ is an adjoint-valued current.

The Bianchi identity is

$$
\boxed{D_{[\lambda}F_{\mu\nu]}=0.}
$$

This follows from the Jacobi identity for covariant derivatives:

$$
[D_\lambda,[D_\mu,D_\nu]]
+[D_\mu,[D_\nu,D_\lambda]]
+[D_\nu,[D_\lambda,D_\mu]]=0.
$$

For Abelian theory, $D$ reduces to $\partial$ and this identity becomes

$$
\partial_{[\lambda}F_{\mu\nu]}=0,
$$

the familiar homogeneous Maxwell equation.

## Matter representations

Matter fields can transform in different representations of $G$.

For a scalar multiplet in representation $R$,

$$
\mathcal L_\text{matter}
=(D_\mu\Phi)^\dagger D^\mu\Phi-V(\Phi^\dagger\Phi),
$$

where

$$
D_\mu\Phi=(\partial_\mu+igA_\mu^aT_R^a)\Phi.
$$

For a Dirac multiplet,

$$
\mathcal L_\text{matter}
=\bar\psi(i\gamma^\mu D_\mu-m)\psi.
$$

The generators $T_R^a$ depend on the representation. For example, quark fields in QCD transform in the fundamental representation of $SU(3)$, while gluons transform in the adjoint representation.

In the adjoint representation, a field $X=X^aT^a$ transforms as

$$
X\mapsto UXU^{-1}.
$$

The covariant derivative acting on an adjoint field is

$$
D_\mu X=\partial_\mu X+ig[A_\mu,X].
$$

The field strength itself is an adjoint field.

## Covariant conservation

In Abelian gauge theory, current conservation is ordinary:

$$
\partial_\mu j^\mu=0.
$$

In non-Abelian gauge theory, the natural statement is covariant conservation:

$$
\boxed{D_\mu J^\mu=0.}
$$

This is not the same as $\partial_\mu J^\mu=0$ component by component. The current carries gauge charge, so comparing it at nearby points requires the gauge connection. The covariant derivative is the correct comparison rule.

Covariant conservation also follows from the equation of motion and the Bianchi identity. Schematically, applying $D_\nu$ to

$$
D_\mu F^{\mu\nu}=J^\nu
$$

is compatible with

$$
D_\nu J^\nu=0.
$$

This is one reason non-Abelian gauge theory is far more constrained than a random theory of many vector fields.

## Gauge fixing and ghosts

The Yang–Mills action is gauge invariant, so the path integral again overcounts gauge-equivalent configurations. A Lorenz-type gauge condition is

$$
G^a[A]=\partial_\mu A^{a\mu}-f^a=0.
$$

For an infinitesimal gauge transformation,

$$
\delta A_\mu^a=(D_\mu\alpha)^a.
$$

Therefore

$$
\delta G^a[A]
=\partial_\mu(D^\mu\alpha)^a.
$$

The Faddeev–Popov determinant is

$$
\Delta_\text{FP}[A]
=\det(\partial_\mu D^\mu[A]).
$$

Since $D_\mu[A]$ contains the gauge field, this determinant depends on $A$. Exponentiating it introduces anticommuting ghost fields. In a common convention the ghost Lagrangian is schematically

$$
\mathcal L_\text{gh}
=-\partial_\mu\bar c^a(D^\mu c)^a.
$$

The ghosts interact with gauge bosons because $D_\mu$ contains $A_\mu$.

This is exactly where the non-Abelian theory departs from ordinary QED in perturbation theory. In Abelian linear gauges the Faddeev–Popov determinant is field independent; in non-Abelian covariant gauges it is a dynamical part of the gauge-fixed action.

## Abelian limit

If the gauge group is $U(1)$, there is only one generator and

$$
[T,T]=0.
$$

Equivalently,

$$
f^{abc}=0.
$$

Then

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
$$

the Yang–Mills action reduces to Maxwell theory, there are no classical photon self-interactions, and the Lorenz-gauge Faddeev–Popov determinant is field independent.

This is why QED is the simplest gauge theory and why non-Abelian gauge theory is a genuine leap rather than a notational upgrade.

## Common pitfalls

**Pitfall 1: Treating non-Abelian gauge symmetry as an ordinary physical symmetry.** The local transformations are still redundancy. Physical global charges can arise from boundary behavior and global transformations, but the local gauge orbit is not a family of distinct physical states.

**Pitfall 2: Forgetting the commutator term.** The term $ig[A_\mu,A_\nu]$ in $F_{\mu\nu}$ is responsible for gauge-boson self-interactions. Dropping it turns Yang–Mills theory back into several unrelated Abelian theories.

**Pitfall 3: Confusing invariance and covariance.** The field strength is not usually invariant. It transforms by conjugation. Traces such as $\operatorname{tr}F^2$ are invariant.

**Pitfall 4: Ignoring representation labels.** The same gauge field acts on different matter multiplets using different matrices $T_R^a$. The representation is physical input.

**Pitfall 5: Thinking ghosts are optional decorations.** In covariant perturbation theory, non-Abelian ghosts encode the gauge-fixing Jacobian and are required for consistent physical amplitudes.

## Relations to nearby pages

- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) explains why local gauge transformations are redundancy rather than ordinary symmetry.
- [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/) is the Abelian limit of this page.
- [Charged Matter](/foundations/gauge-fields-first-principles/charged-matter/) introduces the Abelian covariant derivative that this page generalizes.
- [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/) explains why non-Abelian gauge fixing produces ghosts.
- [BRST Preview](/foundations/gauge-fields-first-principles/brst-preview/) will explain the symmetry of the gauge-fixed theory.
- Later Gauge Theory pages will develop Yang–Mills quantization, Slavnov–Taylor identities, anomalies, asymptotic freedom, QCD, and the Standard Model.

## Exercises

### Exercise 1: Covariance of the field strength

Assume $D_\mu'=UD_\mu U^{-1}$. Show that

$$
F_{\mu\nu}'=UF_{\mu\nu}U^{-1}.
$$

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
[D_\mu,D_\nu]=igF_{\mu\nu}.
$$

Then

$$
[D_\mu',D_\nu']
=[UD_\mu U^{-1},UD_\nu U^{-1}]
=U[D_\mu,D_\nu]U^{-1}
=igUF_{\mu\nu}U^{-1}.
$$

But also

$$
[D_\mu',D_\nu']=igF_{\mu\nu}'.
$$

Therefore

$$
F_{\mu\nu}'=UF_{\mu\nu}U^{-1}.
$$

</details>

### Exercise 2: Gauge invariance of the Yang–Mills action

Use cyclicity of the trace to show that

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
$$

is gauge invariant.

<details>
<summary><strong>Solution</strong></summary>

Since $F\mapsto UFU^{-1}$,

$$
\operatorname{tr}(F'_{\mu\nu}F'^{\mu\nu})
=\operatorname{tr}(UF_{\mu\nu}U^{-1}UF^{\mu\nu}U^{-1})
=\operatorname{tr}(UF_{\mu\nu}F^{\mu\nu}U^{-1}).
$$

By cyclicity,

$$
\operatorname{tr}(UF_{\mu\nu}F^{\mu\nu}U^{-1})
=\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

</details>

### Exercise 3: Abelian limit of the field strength

Show that if all generators commute, the non-Abelian field strength reduces to the Maxwell form.

<details>
<summary><strong>Solution</strong></summary>

The non-Abelian field strength is

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu].
$$

If the generators commute, then $[A_\mu,A_\nu]=0$. Therefore

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

This is the Abelian field strength.

</details>

### Exercise 4: Self-interactions from the action

Explain why $-\frac14F_{\mu\nu}^aF^{a\mu\nu}$ contains cubic and quartic gauge-boson interactions.

<details>
<summary><strong>Solution</strong></summary>

Write schematically

$$
F=\partial A+gAA.
$$

Then

$$
F^2=(\partial A)^2+2g(\partial A)AA+g^2A^4.
$$

The first term is the kinetic term, the second gives cubic gauge-boson interactions, and the third gives quartic gauge-boson interactions.

</details>

### Exercise 5: Why the ghost determinant depends on the gauge field

For $G^a[A]=\partial_\mu A^{a\mu}$ and $\delta A_\mu^a=(D_\mu\alpha)^a$, show that the Faddeev–Popov operator contains $A_\mu$.

<details>
<summary><strong>Solution</strong></summary>

The variation of the gauge condition is

$$
\delta G^a[A]
=\partial_\mu\delta A^{a\mu}
=\partial_\mu(D^\mu\alpha)^a.
$$

Thus the Faddeev–Popov operator is

$$
M^{ab}[A]=\partial_\mu D^{\mu ab}[A].
$$

Because the covariant derivative $D_\mu[A]$ contains $A_\mu$, the operator and its determinant depend on the gauge field.

</details>

### Exercise 6: Adjoint covariant derivative

Let $X=X^aT^a$ transform as $X\mapsto UXU^{-1}$. Show that

$$
D_\mu X=\partial_\mu X+ig[A_\mu,X]
$$

transforms covariantly.

<details>
<summary><strong>Solution</strong></summary>

The gauge potential transforms as

$$
A_\mu'=UA_\mu U^{-1}+\frac{i}{g}(\partial_\mu U)U^{-1}.
$$

Compute

$$
D_\mu'X'
=\partial_\mu(UXU^{-1})+ig[A_\mu',UXU^{-1}].
$$

Using $\partial_\mu(U^{-1})=-U^{-1}(\partial_\mu U)U^{-1}$ and substituting $A_\mu'$, the derivative terms involving $\partial_\mu U$ cancel, leaving

$$
D_\mu'X'=U(\partial_\mu X+ig[A_\mu,X])U^{-1}=U(D_\mu X)U^{-1}.
$$

Thus the adjoint covariant derivative transforms covariantly.

</details>

## Sources and further reading

- C. N. Yang and R. Mills, “Conservation of Isotopic Spin and Isotopic Gauge Invariance,” *Physical Review* **96** (1954), for the original non-Abelian gauge theory.
- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* **25** (1967), for the gauge-fixing determinant.
- M. Srednicki, *Quantum Field Theory*, sections 69–74, for non-Abelian gauge theory, group representations, path-integral quantization, Feynman rules, beta function preview, and BRST.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 46–47, for Yang–Mills fields, spontaneous symmetry breaking preview, Faddeev–Popov quantization, and ghosts.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, ch. 15, for the systematic treatment of gauge transformations, field strengths, Yang–Mills Lagrangians, ghosts, and BRST.
- A. M. Polyakov, *Gauge Fields and Strings*, ch. 1, for the statistical and geometrical intuition behind gauge fields.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, chs. 15–16, for practical Yang–Mills perturbation theory and QCD.

## Version history

- **2026-05-23:** Initial qft.org preview page on non-Abelian gauge transformations, covariant derivatives, field strength, Yang–Mills action, self-interactions, covariant conservation, gauge fixing, and ghost preview.
