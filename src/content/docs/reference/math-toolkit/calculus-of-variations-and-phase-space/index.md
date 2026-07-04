---
title: "Calculus of Variations and Phase Space"
description: "Chapter overview for functional derivatives, Euler–Lagrange operators, boundary terms, Legendre transforms, symplectic forms, Poisson brackets, and constraint previews in the Mathematical Toolkit volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Standard variational calculus, symplectic geometry, Hamiltonian mechanics, constrained systems, and QFT classical-field-theory references."
topics:
  - calculus of variations
  - functional derivatives
  - Euler–Lagrange equations
  - symplectic geometry
  - Poisson brackets
  - constraints
canonicalTopics:
  - variational-calculus
  - phase-space-geometry
  - functional-derivatives
  - poisson-brackets
researchStatus:
  established:
    - "Functional derivatives, Euler–Lagrange equations, Legendre transforms, symplectic forms, Poisson brackets, and constrained Hamiltonian systems are standard mathematical structures behind classical and quantum field theory."
  active:
    - "Covariant phase space, boundary symplectic structure, edge modes, singular Lagrangians, BV-BRST geometry, and infinite-dimensional functional-analytic foundations remain active in gauge theory, gravity, and modern QFT."
---

Calculus of Variations and Phase Space is the chapter in the Mathematical Toolkit volume where the phrase “vary the action” becomes a precise operation. It explains functional derivatives, Euler–Lagrange operators, boundary terms, Legendre transforms, symplectic forms, Poisson brackets, and the first signs of constraints.

This chapter exists because QFT uses actions in several different ways. The same functional $S[\phi]$ produces classical field equations, perturbative saddle points, canonical momenta, conserved currents, Schwinger–Dyson equations, Ward identities, and eventually the phase-space structure used in canonical quantization.

The basic slogan is

$$
\delta S
=
\int_M E_i(\phi)\,\delta\phi^i
+
\int_{\partial M}\theta(\phi,\delta\phi).
$$

The bulk term gives equations of motion. The boundary term decides differentiability, boundary conditions, conserved charges, and symplectic structure. Ignore the boundary term and, sooner or later, the theory will send you a bill.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Flow diagram from an action functional to its variation, Euler–Lagrange equations, symplectic potential, symplectic form, Poisson bracket, Hamiltonian flow, and constraint degeneracies.](/figures/math-toolkit/variational-phase-space-map.svg)

<figcaption>

The first variation of the action has two outputs: a bulk Euler–Lagrange operator and a boundary term. The same boundary term is the seed of phase-space geometry: symplectic potentials, symplectic forms, Poisson brackets, Hamiltonian flow, and constraints.

</figcaption>
</figure>

## Prerequisites

You should know the [Mathematical Conventions](/math-toolkit/conventions/) page, especially the notation for functional derivatives, distributions, integration by parts, and boundary orientation. The Analysis, Distributions, and Fourier Methods chapter is useful because variational derivatives are often distributions: differentiating $\phi(x)$ with respect to $\phi(y)$ gives a delta function, not an ordinary number.

The Functional Integrals and Determinants chapter is also a useful companion. [Stationary Phase and Saddle Points](/math-toolkit/functional-integrals-determinants/stationary-phase-and-saddle-points/) uses critical points of actions; [Jacobians and Measures](/math-toolkit/functional-integrals-determinants/jacobians-and-measures/) explains why changes of variables in field space carry determinants; and [Faddeev–Popov Determinants Preview](/math-toolkit/functional-integrals-determinants/faddeev-popov-determinants-preview/) shows how gauge redundancy appears as degeneracy along field-space directions.

No deep symplectic geometry is assumed at the beginning. The chapter starts with the same integration-by-parts calculation used in ordinary mechanics and gradually upgrades it to field theory and phase space.

## Reading path

The natural reading path is linear, because each page repairs a specific ambiguity in the phrase “take a variation.”

Start with **Variational Derivatives**. This page should explain what $\delta S/\delta\phi(x)$ means, why it is a distributional derivative, how left and right functional derivatives differ for Grassmann variables, and how source differentiation in generating functionals uses the same idea.

Then read **Euler–Lagrange Operators**. The goal is to derive the field equations from a local Lagrangian density, including higher-derivative examples and the distinction between ordinary partial derivatives and total derivatives.

Next comes **Boundary Terms and Functional Differentiability**. This is the page that prevents bad habits. A functional derivative is not well-defined until the boundary terms in $\delta S$ have been controlled by boundary conditions, boundary counterterms, or boundary degrees of freedom.

After that, read **Legendre Transforms**. This page should explain how Lagrangian data become Hamiltonian data, why momenta are derivatives of the Lagrangian with respect to velocities, and why singular Lagrangians lead to constraints rather than ordinary phase spaces.

Then read **Symplectic Forms**. This page should introduce the canonical one-form, symplectic two-form, covariant symplectic potential, degeneracy directions, and the geometric meaning of phase space.

Then read **Poisson Brackets**. The Poisson bracket is not a formal commutator with $i$ missing. It is the inverse of a symplectic structure, and that inverse may fail to exist when constraints or gauge redundancies are present.

End with **Constraints Preview**. This preview should give just enough Dirac constraint theory to recognize first-class constraints, second-class constraints, gauge generators, Dirac brackets, and why gauge theories require more than naive canonical coordinates.

A good practice checkpoint after the first three pages is to vary the scalar action

$$
S[\phi]=\int d^dx\,\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2
$$

and identify both the Euler–Lagrange operator and the boundary term. A good checkpoint after the phase-space pages is to derive

$$
\{q^i,p_j\}=\delta^i{}_j
$$

from the canonical symplectic form rather than declaring it by memory.

<details><summary><strong>Solution to the scalar-action checkpoint</strong></summary>

Vary

$$
S[\phi]=\int d^dx\,\left(\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2\right).
$$

Then

$$
\delta S
=\int d^dx\,\left(\partial_\mu\phi\partial^\mu\delta\phi-m^2\phi\delta\phi\right).
$$

Integrating by parts gives

$$
\delta S
=\int d^dx\,(-\partial_\mu\partial^\mu\phi-m^2\phi)\delta\phi
+\int_{\partial M}d\Sigma_\mu\,\partial^\mu\phi\,\delta\phi.
$$

The Euler–Lagrange equation is therefore

$$
(\Box+m^2)\phi=0,
$$

while the boundary term is

$$
\int_{\partial M}d\Sigma_\mu\,\partial^\mu\phi\,\delta\phi.
$$

The equation of motion follows only after this boundary term has been made compatible with the allowed variations.

</details>

<details><summary><strong>Solution to the Poisson-bracket checkpoint</strong></summary>

For ordinary canonical coordinates,

$$
\Omega=dq^i\wedge dp_i.
$$

The Hamiltonian vector field $X_F$ is defined by

$$
\iota_{X_F}\Omega=dF.
$$

For $F=q^i$, this gives $X_{q^i}=-\partial/\partial p_i$ with the sign convention used by $\{F,G\}=\Omega(X_F,X_G)$. For $G=p_j$, $X_{p_j}=\partial/\partial q^j$. Therefore

$$
\{q^i,p_j\}=\Omega(X_{q^i},X_{p_j})=\delta^i{}_j,
$$

with the same convention reflected in the coordinate formula

$$
\{F,G\}
=\frac{\partial F}{\partial q^k}\frac{\partial G}{\partial p_k}
-\frac{\partial F}{\partial p_k}\frac{\partial G}{\partial q^k}.
$$

The point is not the sign convention; the point is that the bracket is the inverse of the symplectic form.

</details>

## Landmarks

The first landmark is the functional derivative. For a functional $F[\phi]$, the derivative is defined by

$$
\delta F
=
\int d^dx\,\frac{\delta F}{\delta\phi(x)}\delta\phi(x),
$$

after boundary terms and test-function assumptions have been settled. This is a distributional gradient on field space.

The second landmark is the Euler–Lagrange operator. For a first-derivative local Lagrangian,

$$
S[\phi]=\int_M d^dx\,\mathcal L(\phi,\partial_\mu\phi),
$$

the variation gives

$$
\delta S
=
\int_M d^dx\,
\left(
\frac{\partial\mathcal L}{\partial\phi}
-
\partial_\mu\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\right)\delta\phi
+\int_{\partial M}\theta.
$$

The expression multiplying $\delta\phi$ is the Euler–Lagrange operator.

The third landmark is the boundary term. In mechanics,

$$
\delta S
=\int_{t_i}^{t_f}dt\,
\left(\frac{\partial L}{\partial q^i}-\frac{d}{dt}\frac{\partial L}{\partial\dot q^i}\right)\delta q^i
+\left[p_i\delta q^i\right]_{t_i}^{t_f}.
$$

The endpoint term is not trash. It contains the canonical one-form $p_i\delta q^i$. In field theory, the analogous boundary term becomes the symplectic potential current.

The fourth landmark is the Legendre transform. When the velocity–momentum map is invertible,

$$
p_i=\frac{\partial L}{\partial\dot q^i},
\qquad
H(q,p)=p_i\dot q^i-L(q,\dot q),
$$

with $\dot q$ expressed in terms of $(q,p)$. When this map is not invertible, constraints appear.

The fifth landmark is the symplectic form. On ordinary phase space,

$$
\Theta=p_i\,dq^i,
\qquad
\Omega=dq^i\wedge dp_i.
$$

The symplectic form turns functions into Hamiltonian vector fields by

$$
\iota_{X_F}\Omega=dF.
$$

The sixth landmark is the Poisson bracket:

$$
\{F,G\}=\Omega(X_F,X_G).
$$

In canonical coordinates this becomes

$$
\{F,G\}
=\frac{\partial F}{\partial q^i}\frac{\partial G}{\partial p_i}
-
\frac{\partial F}{\partial p_i}\frac{\partial G}{\partial q^i}.
$$

The seventh landmark is the constraint warning. Gauge theories do not begin with honest symplectic forms on the naive space of fields. They often begin with presymplectic forms whose degeneracy directions are gauge transformations. Quantization without noticing this is a surprisingly efficient way to generate nonsense.

## Common confusions

**“The variation of the action is just the equation of motion.”** Not quite. The first variation contains a bulk term and a boundary term. The bulk term gives the equation of motion. The boundary term controls whether the variational problem is well-posed.

**“Boundary terms vanish.”** Sometimes they vanish because variations are fixed at the boundary. Sometimes they vanish after adding a boundary term to the action. Sometimes they encode charges, fluxes, edge modes, or symplectic structure. They should be killed only after trial, not by assumption.

**“A functional derivative is just an ordinary derivative with an $x$ label.”** It is closer to a distributional derivative. For example,

$$
\frac{\delta\phi(x)}{\delta\phi(y)}=\delta^{(d)}(x-y).
$$

That delta function is why integration by parts, test functions, and boundary conditions matter.

**“The canonical momentum is always the velocity.”** Only for special Lagrangians. In general,

$$
p_i=\frac{\partial L}{\partial\dot q^i},
$$

which may be nonlinear in $\dot q$, independent of some velocities, or constrained.

**“The Poisson bracket is a quantization rule.”** The Poisson bracket is classical phase-space geometry. Canonical quantization later replaces some Poisson brackets by commutators, but the Poisson bracket itself is defined before quantization.

**“Gauge fixing is just choosing coordinates.”** Locally, yes-ish. Globally, gauge fixing can fail. Degenerate symplectic forms, residual gauge transformations, boundary charges, and Gribov-type problems are warnings that field space is not a friendly Euclidean space wearing a fake mustache.

## Boundaries

This chapter is not a complete course on classical mechanics, symplectic geometry, or geometric quantization. It teaches the pieces of variational and phase-space language that a QFT reader repeatedly needs.

It also does not replace the Foundations of QFT treatment of classical fields, canonical quantization, Noether theorem, or path integrals. Those pages explain the physics. This chapter supplies the mathematical operations that those physics pages rely on.

The constraints page is only a preview. A full treatment of Dirac constraints, BRST symmetry, BV formalism, reduced phase spaces, gauge fixing, and ghosts belongs later in gauge theory, symmetry, and rigorous QFT contexts.

The infinite-dimensional geometry is intentionally pragmatic. In finite dimension, symplectic manifolds, Poisson manifolds, and Legendre transforms can be defined cleanly. In field theory, domains, function spaces, boundary behavior, differentiability, and distributional kernels must be specified case by case. This chapter teaches the working language without pretending those analytic issues have disappeared.

## Where to go next

After this chapter, the most immediate physics destination is classical field theory in Foundations of QFT: actions, Euler–Lagrange equations, Noether currents, stress tensors, canonical momenta, and Hamiltonian field theory all use the tools here.

For path integrals, return to the Functional Integrals and Determinants chapter. Variational derivatives control stationary phase, Schwinger–Dyson equations, source differentiation, one-loop fluctuation operators, and changes of variables in field space.

For gauge theory, continue toward Lie groups, geometry of fields, and eventually gauge fixing. Constraints and presymplectic degeneracies are the Hamiltonian face of gauge redundancy; Faddeev–Popov determinants and BRST symmetry are path-integral faces of the same underlying problem.

For modern research, this chapter is the doorway to covariant phase space, boundary charges, edge modes, asymptotic symmetries, BV-BRST geometry, symplectic reduction, and geometric quantization. Those topics are not needed on day one, but they are what the humble boundary term grows up to become.

## References

- I. M. Gelfand and S. V. Fomin, *Calculus of Variations*. Compact classical reference for variational derivatives and Euler–Lagrange equations.
- V. I. Arnold, *Mathematical Methods of Classical Mechanics*. Canonical reference for symplectic geometry, Hamiltonian mechanics, and geometric structure.
- H. Goldstein, C. Poole, and J. Safko, *Classical Mechanics*. Standard physics reference for Lagrangian and Hamiltonian mechanics.
- P. J. Olver, *Applications of Lie Groups to Differential Equations*. Variational calculus, symmetries, conservation laws, and differential equations.
- J. E. Marsden and T. S. Ratiu, *Introduction to Mechanics and Symmetry*. Geometric mechanics, momentum maps, and reduction.
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*. Standard reference for constraints, gauge systems, and Hamiltonian quantization.
- A. Hanson, T. Regge, and C. Teitelboim, *Constrained Hamiltonian Systems*. Concise treatment of constrained dynamics.
- L. D. Faddeev and A. A. Slavnov, *Gauge Fields: Introduction to Quantum Theory*. Gauge fields, constraints, and quantization.
- M. Srednicki, *Quantum Field Theory*. Practical QFT use of classical actions, path integrals, functional derivatives, and constraints.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II. Classical-field and quantum-field uses of actions, symmetries, canonical structures, and gauge constraints.
- C. Crnković, E. Witten, and G. Zuckerman, covariant phase-space papers. Useful for the boundary-term-to-symplectic-form viewpoint in field theory.

## Version history

- 2026-06-24: First polished draft. Established the chapter scope, prerequisites, reading path, landmarks, common confusions, boundaries, handoffs, and a variational-to-phase-space figure.
