---
title: "Path Integral Measure"
description: "How the formal measure Dφ is defined by regulators, how Jacobians arise under field redefinitions, and why gauge fixing, anomalies, zero modes, and normalization subtleties matter."
sidebar:
  label: "Path Integral Measure"
  order: 9
---

## Summary

The symbol

$$
\int\mathcal D\phi
$$

is not a literal infinite product with all the usual properties of a finite-dimensional volume form. It is shorthand for a regulated limiting procedure. A path-integral measure is defined by choosing a finite-dimensional approximation, doing ordinary integrals there, and then studying the continuum limit.

For a scalar field one may write, formally,

$$
\phi(x)=\sum_n c_n f_n(x),
\qquad
\mathcal D\phi\equiv\prod_n dc_n,
$$

where the product is made finite by a regulator. Under a change of variables $c=c(c')$,

$$
\boxed{
\prod_n dc_n
=\det\left(\frac{\partial c_m}{\partial c'_n}\right)
\prod_n dc'_n
}
$$

for bosonic variables. For Grassmann variables the determinant is inverted:

$$
\boxed{
\prod_n d\theta_n
=\det\left(\frac{\partial\theta_m}{\partial\theta'_n}\right)^{-1}
\prod_n d\theta'_n.
}
$$

In finite dimensions this is just calculus. In field theory the determinant becomes an infinite-dimensional functional determinant, and that is where the physics begins. Some Jacobians are harmless constants. Some become local counterterms. Some are anomalies. Gauge theories add another complication: the naive measure integrates over infinitely many descriptions of the same physical configuration, so gauge fixing and the Faddeev–Popov determinant are needed.

Srednicki's path-integral derivation of the chiral anomaly is the clean cautionary example: the classical action may be invariant under a transformation while the regulated fermion measure is not (Srednicki 2007, §77). Coleman explains the complementary gauge-fixing issue by first doing a finite-dimensional model and then copying it into function space: gauge transformations move along redundant directions, and the Faddeev–Popov determinant is the Jacobian for slicing those directions once (Coleman 2019, chs. 31 and 47). Zee gives the same idea with the concrete analogy of changing to polar coordinates and factoring out an angular group volume (Zee 2010, ch. III.4).

## Prerequisites

You should know [Finite-Dimensional Gaussians](/foundations/path-integral-formalism/finite-dimensional-gaussians/), [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/), [Grassmann Variables](/foundations/path-integral-formalism/grassmann-variables/), [Fermionic Path Integral](/foundations/path-integral-formalism/fermionic-path-integral/), [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/), [Constraints](/foundations/classical-field-theory/constraints/), and [Semiclassical Expansion](/foundations/path-integral-formalism/semiclassical-expansion/).

## Core idea

A measure is part of the definition of the quantum theory. The action tells you how to weight configurations; the measure tells you what counts as one configuration.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Path integral measure map from regulator basis to Jacobians, anomalies, and gauge fixing](/figures/foundations/path-integral-measure-map.svg)

<figcaption>

A functional measure begins as an ordinary product measure after choosing a regulator or basis. Changes of variables produce Jacobians. In field theory those Jacobians may be constants, counterterms, anomalies, or Faddeev–Popov determinants, depending on the regulator and the symmetry.

</figcaption>
</figure>

The slogan is:

```txt
formal measure = regulator + coordinates + limiting prescription
```

This is why one should be suspicious of arguments that begin, “The measure is clearly invariant.” Maybe it is. Maybe it is not. The right question is:

```txt
Can I choose a regulator for the measure that preserves this symmetry?
```

If the answer is yes, the symmetry survives quantization. If the answer is no, the failure is often an anomaly.

## Finite-dimensional prototype

Let $x^i$ be $N$ ordinary real variables. A change of variables

$$
x^i=x^i(y)
$$

gives

$$
\boxed{
\int d^Nx\,F(x)=\int d^Ny\,
\left|\det\frac{\partial x^i}{\partial y^j}\right|F(x(y)).
}
$$

For an infinitesimal transformation

$$
x^i\to x'^i=x^i+\alpha R^i(x),
$$

the Jacobian is

$$
\frac{\partial x'^i}{\partial x^j}
=\delta^i_j+\alpha\partial_jR^i.
$$

Thus

$$
\det\left(\frac{\partial x'}{\partial x}\right)
=\exp\left[\operatorname{tr}\log(1+\alpha\partial R)\right]
=1+\alpha\partial_iR^i+O(\alpha^2).
$$

So ordinary volume is invariant only when the vector field $R^i$ is divergence-free. Translations and rotations pass this test; general nonlinear transformations do not.

The field-theory version is the same formula with an infinite number of coordinates.

## Defining a scalar field measure

Choose an orthonormal basis $f_n(x)$ with respect to some inner product, for example

$$
\int d^dx\,f_m(x)f_n(x)=\delta_{mn}.
$$

Expand

$$
\phi(x)=\sum_{n=1}^{N}c_nf_n(x)
$$

with a finite cutoff $N$. Define

$$
\mathcal D_N\phi=\prod_{n=1}^{N}dc_n.
$$

All manipulations are now finite-dimensional. The continuum notation

$$
\mathcal D\phi
$$

means some regulated limit of $\mathcal D_N\phi$, or a different regulator such as a lattice, heat-kernel cutoff, Pauli–Villars fields, dimensional regularization, or mode cutoff.

On a spacetime lattice, the same idea looks like

$$
\mathcal D\phi=\prod_x d\phi_x.
$$

This expression is simple, but not innocent. It depends on the lattice, the field variables, the boundary conditions, and the continuum limit.

## Translation invariance and source shifts

Gaussian path integrals repeatedly use shifts such as

$$
\phi\to\phi+A^{-1}J.
$$

In a finite-dimensional regulated scalar integral,

$$
\prod_i d\phi_i
$$

is invariant under translations:

$$
\prod_i d(\phi_i+a_i)=\prod_i d\phi_i.
$$

This is why completing the square works. The statement remains reliable in field theory when the shift is performed inside a regulator and no boundary or zero-mode subtlety is being crossed.

But this does not imply that every field redefinition has unit Jacobian. Translation invariance is special.

## Bosonic Jacobians

For a linear bosonic transformation

$$
\phi_i=M_{ij}\phi'_j,
$$

the finite-dimensional measure transforms as

$$
\prod_i d\phi_i=|\det M|\prod_i d\phi'_i.
$$

In field theory this becomes

$$
\mathcal D\phi=\det M\,\mathcal D\phi'
$$

formally. If $M$ is independent of fields and backgrounds, the determinant is often an infinite constant that cancels in normalized correlation functions. If $M$ depends on a background, a metric, a gauge field, or the field itself, the determinant can contribute to the action:

$$
\det M=\exp(\operatorname{Tr}\log M).
$$

This is the same trace-log structure that appeared in [Semiclassical Expansion](/foundations/path-integral-formalism/semiclassical-expansion/). Determinants are not decorative; they encode quantum fluctuations and changes of variables.

## Grassmann Jacobians

Grassmann variables transform oppositely. For one variable,

$$
\theta=a\theta',
$$

Berezin integration requires

$$
\int d\theta\,\theta=1.
$$

Since $\theta=a\theta'$, we need

$$
d\theta=a^{-1}d\theta'
$$

so that

$$
\int d\theta\,\theta
=\int a^{-1}d\theta'\,a\theta'
=1.
$$

For many variables,

$$
\boxed{
\prod_i d\theta_i
=\det M^{-1}\prod_i d\theta'_i
\qquad
\text{if}\qquad
\theta_i=M_{ij}\theta'_j.
}
$$

This inverse determinant is why fermionic Gaussian integrals produce determinants in the numerator. It is also why fermion measure transformations are central in anomaly calculations.

## Symmetries of the action versus symmetries of the measure

Suppose a transformation sends

$$
\phi\to\phi'
$$

and leaves the classical action invariant:

$$
S[\phi']=S[\phi].
$$

The quantum path integral is invariant only if the measure is invariant too:

$$
\mathcal D\phi'=\mathcal D\phi.
$$

If the measure transforms as

$$
\mathcal D\phi'=J[\phi]\mathcal D\phi,
$$

then the path integral becomes

$$
\int\mathcal D\phi'\,e^{iS[\phi']}
=
\int\mathcal D\phi\,J[\phi]e^{iS[\phi]}.
$$

Writing

$$
J[\phi]=e^{i\Delta S[\phi]}
$$

shows that a measure Jacobian is equivalent to an extra quantum term in the action. In Euclidean signature, the same statement is

$$
J[\phi]=e^{-\Delta S_E[\phi]}.
$$

This is the formal source of anomaly terms, Wess–Zumino terms, ghost actions, and many determinant-induced effective actions.

## Regulated traces and anomaly preview

For an infinitesimal linear transformation of fields,

$$
\phi\to\phi'=\phi+\alpha R\phi,
$$

the formal Jacobian is

$$
J=\det(1+\alpha R)=\exp[\alpha\operatorname{Tr}R+O(\alpha^2)].
$$

In field theory, $\operatorname{Tr}R$ usually contains a factor like

$$
\delta^{(d)}(0),
$$

so it is meaningless without a regulator. A typical regulated trace is

$$
\boxed{
\operatorname{Tr}R
\quad\longrightarrow\quad
\lim_{M\to\infty}\operatorname{Tr}\left(R e^{-\mathcal K/M^2}\right),
}
$$

where $\mathcal K$ is a regulator operator chosen to preserve as many desired symmetries as possible.

The chiral anomaly is the canonical example. For a massless Dirac field, the classical action may be invariant under an axial rotation, but the fermionic measure transforms with a regulated Jacobian. Schematically,

$$
\mathcal D\bar\psi\mathcal D\psi
\to
\mathcal D\bar\psi\mathcal D\psi\,
\exp\left[-i\int d^4x\,\alpha(x)\,\mathcal A(x)\right],
$$

where

$$
\mathcal A(x)\propto \epsilon^{\mu\nu\rho\sigma}\operatorname{Tr}F_{\mu\nu}F_{\rho\sigma}
$$

for the usual four-dimensional gauge-background anomaly. The proportionality constant and representation factors belong to a dedicated anomaly page; the foundational lesson here is that the anomaly is a regulated measure Jacobian.

## Gauge redundancy and Faddeev–Popov determinants

Gauge theories have a different measure problem. The issue is not only that the measure may have a Jacobian; it is that the naive integral counts the same physical configuration infinitely many times.

For a gauge field,

$$
A_\mu\sim A_\mu^g
$$

are different descriptions of the same physical configuration. The naive expression

$$
\int\mathcal D A\,e^{iS[A]}
$$

integrates along every gauge orbit. If the gauge group is continuous, this includes an infinite gauge volume.

The Faddeev–Popov idea is to insert a gauge condition

$$
F[A]=0
$$

that slices each gauge orbit once, at least locally. The formal identity is

$$
1=\Delta_{\rm FP}[A]
\int\mathcal Dg\,\delta(F[A^g]),
$$

where

$$
\boxed{
\Delta_{\rm FP}[A]
=\det\left(\frac{\delta F[A^g]}{\delta g}\right)_{F=0}.
}
$$

After factoring out the gauge-group volume, one obtains

$$
\boxed{
Z=N\int\mathcal D A\,
\Delta_{\rm FP}[A]\,\delta(F[A])\,e^{iS[A]}.
}
$$

In nonabelian gauge theory the determinant depends on the gauge field and is represented by Grassmann scalar ghost fields. That subject belongs to the gauge-theory groups, but its origin is purely measure-theoretic: it is the Jacobian for slicing gauge orbits.

## Measures and constraints

Constrained Hamiltonian systems also teach the same lesson. If the Legendre transform is singular, not every canonical variable is independent. A naive phase-space measure

$$
\mathcal Dq\,\mathcal Dp
$$

may integrate over redundant or forbidden directions. Constraints introduce delta functions, determinants, and sometimes gauge-fixing conditions.

The schematic structure is

$$
\int\mathcal Dq\,\mathcal Dp\;
\delta(\text{constraints})\,
\delta(\text{gauge fixing})\,
\det(\text{brackets})\;e^{iS}.
$$

The details depend on whether the constraints are first class or second class. Foundations has already introduced that distinction in [Constraints](/foundations/classical-field-theory/constraints/); the path-integral version is the same independence problem in integral form.

## Normalization and absolute partition functions

Many QFT calculations normalize

$$
Z[0]=1.
$$

This cancels field-independent measure constants. For ordinary flat-space correlation functions, that is often exactly what one wants.

But absolute normalizations are not always ignorable. They matter in:

```txt
vacuum energy and cosmological constant questions
finite-temperature free energies
curved-spacetime partition functions
topological field theories
anomaly phases
semiclassical tunneling prefactors
lattice simulations
```

A determinant that looks like “just a constant” in one calculation can become physical in another. The safe habit is to say what has been normalized away.

## Regulator choices and symmetry tradeoffs

A regulator is not only a computational device. It helps define the measure.

Common regulators include:

```txt
lattice cutoffs
mode cutoffs
heat-kernel regulators
Pauli–Villars fields
dimensional regularization
zeta-function regularization
```

Different regulators preserve different symmetries. For example:

```txt
lattice scalar measures preserve locality and many internal symmetries, but not continuous rotations exactly at finite spacing;
dimensional regularization preserves gauge invariance efficiently in many perturbative calculations, but treats intrinsically four-dimensional objects such as γ5 carefully;
heat-kernel regulators are natural for anomalies and curved backgrounds;
lattice gauge theory preserves gauge invariance exactly by using group-valued link variables and Haar measure.
```

When two symmetries cannot be preserved simultaneously by any regulator, the conflict is physical. That is the anomaly story in one sentence.

## Field redefinitions

Local invertible field redefinitions often do not change the S-matrix, but they do change the action, sources, composite operators, and sometimes the measure. A simple schematic example is

$$
\phi=f(\chi).
$$

Then

$$
\mathcal D\phi
=\det\left(\frac{\delta f(\chi(x))}{\delta\chi(y)}\right)\mathcal D\chi.
$$

For a pointwise change,

$$
\frac{\delta f(\chi(x))}{\delta\chi(y)}
=f'(\chi(x))\delta^{(d)}(x-y),
$$

so formally

$$
\log J=\operatorname{Tr}\log[f'(\chi)]
=\delta^{(d)}(0)\int d^dx\,\log f'(\chi(x)).
$$

This expression screams “regulate me.” In many perturbative schemes, such local Jacobians are set to zero or absorbed into counterterms. In other contexts they are physical. The answer is not a slogan; it is a regulator-dependent statement that must preserve the desired quantum theory.

## Measure in operator language

The operator formalism does not usually speak of $\mathcal D\phi$, but it contains the same information.

A path integral derived by time slicing starts with resolutions of identity, such as

$$
1=\int dq\,|q\rangle\langle q|
$$

or phase-space resolutions involving $dq\,dp$. The measure comes from those identities and from the normalization of states. For constrained systems, gauge systems, and fermions, the operator derivation determines which degrees of freedom are actually independent.

So the measure is not extra mystical input. It is the path-integral encoding of Hilbert-space normalization, independent degrees of freedom, and regulator choice.

## Common pitfalls

### Saying the measure is invariant without a regulator

In finite dimensions, this is easy to check. In field theory, the trace that decides the Jacobian is often divergent. A regulator is part of the statement.

### Confusing gauge symmetry with ordinary symmetry

Gauge transformations do not relate different physical configurations. They relate different descriptions of the same configuration. The measure must avoid overcounting gauge orbits.

### Dropping all determinants

Some determinants cancel in normalized free correlators. Others are the whole point: fermion loops, ghosts, one-loop effective actions, tunneling prefactors, and anomalies.

### Treating Grassmann and bosonic Jacobians the same way

They are inverse to each other. This sign/determinant reversal is not optional bookkeeping; it is built into Berezin integration.

### Forgetting zero modes

A zero mode means the Gaussian coordinate system has failed in one direction. One must use collective coordinates, gauge fixing, or constraints, depending on what the zero mode represents.

### Assuming all field redefinitions are harmless

Many are harmless for S-matrix elements after proper treatment, but they can change local operators, sources, counterterms, anomalies, and the transparent form of symmetries.

## Relation to other topics

- [Semiclassical Expansion](/foundations/path-integral-formalism/semiclassical-expansion/) uses determinant primes and collective-coordinate Jacobians.
- [Grassmann Variables](/foundations/path-integral-formalism/grassmann-variables/) derives the inverse determinant for Berezin integration.
- [Fermionic Path Integral](/foundations/path-integral-formalism/fermionic-path-integral/) shows how fermion determinants and Pfaffians arise.
- [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) explains when the functional integral can be treated like a statistical measure.
- [Constraints](/foundations/classical-field-theory/constraints/) supplies the Hamiltonian reason gauge and constrained systems need special treatment.
- Later pages on gauge fixing, BRST, anomalies, instantons, lattice QFT, and curved-spacetime QFT will refine these measure issues.

## Research status

- **Established:** Regulated product measures, bosonic and fermionic Jacobians, Faddeev–Popov determinants, and anomaly Jacobians are standard QFT material.
- **Active:** Chiral gauge-theory regulators, lattice fermion measures, global anomalies, sign problems, determinant phases, and nonperturbative definitions of functional measures remain active.
- **Speculative:** None at the level of the foundational warning: the measure must be regulated before its symmetry properties are asserted.

## Exercises

### Exercise 1: Bosonic Jacobian

Let $x_i=M_{ij}y_j$, where $M$ is an invertible real $N\times N$ matrix. Show that

$$
d^Nx=|\det M|d^Ny.
$$

<details>
<summary><strong>Solution</strong></summary>

The Jacobian matrix is

$$
\frac{\partial x_i}{\partial y_j}=M_{ij}.
$$

The multidimensional change-of-variables theorem gives

$$
d^Nx=\left|\det\frac{\partial x}{\partial y}\right|d^Ny
=|\det M|d^Ny.
$$

For complex oscillatory integrals one often drops the absolute value and keeps track of phases by contour prescriptions. For ordinary real Euclidean integrals, the absolute value is the standard calculus result.

</details>

### Exercise 2: Grassmann Jacobian for one variable

Let $\theta=a\theta'$ with $a\ne0$. Use $\int d\theta\,\theta=1$ to show that $d\theta=a^{-1}d\theta'$.

<details>
<summary><strong>Solution</strong></summary>

Assume $d\theta=C\,d\theta'$. Then

$$
1=\int d\theta\,\theta
=\int C\,d\theta'\,a\theta'
=Ca\int d\theta'\,\theta'
=Ca.
$$

Therefore

$$
C=a^{-1},
$$

so

$$
\boxed{d\theta=a^{-1}d\theta'.}
$$

</details>

### Exercise 3: Infinitesimal trace determinant

Let $M=1+\alpha R+O(\alpha^2)$ for a finite-dimensional matrix $R$. Show that

$$
\det M=1+\alpha\operatorname{tr}R+O(\alpha^2).
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\det M=\exp(\operatorname{tr}\log M).
$$

Since

$$
\log(1+\alpha R)=\alpha R+O(\alpha^2),
$$

we get

$$
\det M=\exp[\alpha\operatorname{tr}R+O(\alpha^2)]
=1+\alpha\operatorname{tr}R+O(\alpha^2).
$$

</details>

### Exercise 4: Gauge fixing in a finite model

Consider an integral over variables $(x,y)$ with an integrand $F(x)$ independent of $y$. Explain why

$$
\int dx\,dy\,F(x)
$$

is divergent if $y$ ranges over an infinite line, and show how inserting $\delta(y)$ removes the redundancy.

<details>
<summary><strong>Solution</strong></summary>

Since $F$ is independent of $y$,

$$
\int dx\,dy\,F(x)=\left(\int dy\right)\left(\int dx\,F(x)\right).
$$

If $y\in\mathbb R$, then $\int dy$ is infinite. This is the finite-dimensional analogue of gauge-orbit overcounting.

Insert a delta function:

$$
\int dx\,dy\,F(x)\delta(y)
=\int dx\,F(x)\int dy\,\delta(y)
=\int dx\,F(x).
$$

The delta function picks one representative from each redundant $y$-line.

</details>

### Exercise 5: Local field redefinition Jacobian

Let

$$
\phi(x)=f(\chi(x))
$$

for a pointwise invertible function $f$. Compute the formal functional derivative $\delta\phi(x)/\delta\chi(y)$ and the formal logarithm of the Jacobian.

<details>
<summary><strong>Solution</strong></summary>

Varying $\chi$ gives

$$
\delta\phi(x)=f'(\chi(x))\delta\chi(x).
$$

Therefore

$$
\boxed{
\frac{\delta\phi(x)}{\delta\chi(y)}
=f'(\chi(x))\delta^{(d)}(x-y).
}
$$

The formal Jacobian is

$$
J=\det\left[f'(\chi(x))\delta^{(d)}(x-y)\right].
$$

Thus

$$
\log J=\operatorname{Tr}\log\left[f'(\chi(x))\delta^{(d)}(x-y)\right].
$$

Formally this becomes

$$
\boxed{
\log J=\delta^{(d)}(0)\int d^dx\,\log f'(\chi(x)).
}
$$

The factor $\delta^{(d)}(0)$ shows that the expression requires regularization before it has meaning.

</details>

### Exercise 6: Why anomaly calculations regulate the trace

For an infinitesimal field transformation, suppose the formal Jacobian is

$$
J=\exp[\alpha\operatorname{Tr}R].
$$

Explain why $\operatorname{Tr}R$ is ambiguous in a continuum field theory and why inserting a regulator such as $e^{-\mathcal K/M^2}$ can produce a finite local answer.

<details>
<summary><strong>Solution</strong></summary>

In field theory, the trace includes both discrete labels and spacetime points. Schematically,

$$
\operatorname{Tr}R=\int d^dx\,\operatorname{tr}R(x,x).
$$

For local transformations, $R(x,y)$ often contains a delta function $\delta^{(d)}(x-y)$, so evaluating $R(x,x)$ produces $\delta^{(d)}(0)$. That is undefined.

A regulator replaces the formal trace by

$$
\operatorname{Tr}R
\to
\lim_{M\to\infty}\operatorname{Tr}\left(Re^{-\mathcal K/M^2}\right).
$$

The operator $e^{-\mathcal K/M^2}$ suppresses high eigenmodes of $\mathcal K$, making the trace finite before the limit is taken. If the regulated limit leaves a nonzero local term, the measure is not invariant under the transformation. That nonzero term is the anomaly density.

</details>

## Sources and further reading

### Primary references

- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” for the gauge-fixing determinant.
- K. Fujikawa, “Path-Integral Measure for Gauge-Invariant Fermion Theories,” for the anomaly as a regulated fermion-measure Jacobian.
- J. Schwinger, “On Gauge Invariance and Vacuum Polarization,” for early anomaly-related current and regulator ideas.
- K. Wilson, “Confinement of Quarks,” for the lattice gauge-theory viewpoint in which the measure is defined nonperturbatively.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 31 and 47, for the finite-dimensional Faddeev–Popov analogy and its extension to abelian and nonabelian gauge theories.
- M. Srednicki, *Quantum Field Theory*, §§43–44, §53, and §§76–77, for Grassmann measures, functional determinants, and the Fujikawa anomaly derivation.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §9 and Vol. II, §§15.5–15.8, for path-integral measures, gauge fixing, ghosts, and BRST.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. II.5 and III.4, for Grassmann determinants and the intuitive Faddeev–Popov “polar coordinates” analogy.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§9.4–9.5 and ch. 19, for gauge fixing, ghosts, and anomalies.

### For a first pass

- Zee, ch. III.4.
- Coleman, ch. 31.
- Srednicki, §77.

### For mathematical precision

- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for rigorous constructive functional integrals.
- B. Simon, *Functional Integration and Quantum Physics*, for measure-theoretic foundations.
- M. Nakahara, *Geometry, Topology and Physics*, for geometric language behind gauge orbits, bundles, and characteristic classes.
- M. Lüscher, lattice-gauge-theory papers on chiral gauge theories and fermion measures, for a more advanced nonperturbative perspective.

## Version history

- **2026-05-23:** Initial qft.org page on defining functional measures by regulators, bosonic and Grassmann Jacobians, symmetry of the measure, anomaly previews, gauge-orbit overcounting, Faddeev–Popov determinants, constraints, normalization, and field redefinitions.
