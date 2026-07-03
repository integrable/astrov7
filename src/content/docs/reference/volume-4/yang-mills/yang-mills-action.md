---
title: "Yang–Mills Action"
description: "Constructs the gauge-invariant Yang–Mills kinetic term, derives the classical field equations, and explains how non-Abelian self-interactions enter before matter is added."
sidebar:
  label: "Yang–Mills Action"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki §69; Weinberg Vol. II §§15.1–15.3; Schwartz Ch. 25; Coleman, Aspects of Symmetry, Secret Symmetry."
topics:
  - Yang–Mills action
  - gauge invariance
  - non-Abelian equations of motion
  - gauge-boson self-interactions
  - covariant conservation
canonicalTopics:
  - yang-mills-action
  - gauge-invariant-action
  - non-abelian-field-equations
  - yang-mills-self-interactions
researchStatus:
  established:
    - "The local Yang–Mills action and its classical equations are textbook-standard once the normalization of generators and the sign of the covariant derivative are fixed."
  active:
    - "The quantum and nonperturbative consequences of this action, including asymptotic freedom, confinement, theta sectors, and the mass gap, are treated in later chapters."
---

## Summary

The Yang–Mills action is the simplest local, Lorentz-invariant, gauge-invariant action for a massless non-Abelian gauge field. In this volume's convention,

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a,
\qquad
[D_\mu,D_\nu]=igF_{\mu\nu},
$$

the field strength transforms by conjugation,

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U.
$$

Therefore the trace

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
$$

is gauge invariant. The Yang–Mills Lagrangian is

$$
\boxed{
\mathcal L_{\mathrm{YM}}
=-\frac12\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
}
$$

With $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$, this becomes

$$
\boxed{
\mathcal L_{\mathrm{YM}}
=-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
}
$$

That formula looks almost identical to Maxwell theory, but the resemblance is a trap. The non-Abelian field strength contains the gauge field itself,

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c,
$$

so $\mathcal L_{\mathrm{YM}}$ contains cubic and quartic gauge-boson self-interactions. Yang–Mills theory is already interacting before any matter field is introduced.

<figure class="doc-figure" style="--figure-width: 44rem;">

![The Yang–Mills action architecture: connection to curvature, gauge-invariant trace, equations of motion, and self-interactions.](/figures/gauge-theories-standard-model/yang-mills-action-architecture.svg)

<figcaption>

The Yang–Mills action is built from the curvature of the connection. The trace of $F_{\mu\nu}F^{\mu\nu}$ is gauge invariant, while a bare mass term $m^2\operatorname{tr}A_\mu A^\mu$ is not.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/), especially the sign convention

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

You should also have read [Non-Abelian Gauge Transformations](/gauge-theories-standard-model/yang-mills/non-abelian-gauge-transformations/), which proves the two transformation laws used here:

$$
A_\mu\mapsto U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U,
\qquad
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U.
$$

The only group theory needed on this page is the trace normalization of generators and the invariance of the trace under conjugation.

## Core idea

Gauge invariance does not allow us to write arbitrary functions of $A_\mu$. The gauge field is a connection, and a connection transforms inhomogeneously. This inhomogeneous term is the same feature that makes $A_\mu$ useful: it cancels derivatives of local frame rotations in $D_\mu\psi$. But it also means that $A_\mu$ itself is not a gauge-covariant tensor.

The curvature $F_{\mu\nu}$ is different. It transforms homogeneously:

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U.
$$

A trace removes the endpoint conjugation:

$$
\operatorname{tr}(U^{-1}F_{\mu\nu}UU^{-1}F^{\mu\nu}U)
=\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

So the most economical local kinetic term is the trace of curvature squared. In words,

$$
\text{Yang–Mills dynamics}=\text{curvature squared}.
$$

This slogan is exact enough to remember and dangerous enough to check. It hides the nonlinearity of $F_{\mu\nu}$, which is where the physical novelty lives.

## Setup and conventions

Let $G$ be a compact gauge group with Lie algebra generators

$$
[T^a,T^b]=if^{abc}T^c.
$$

We use Hermitian generators. For the fundamental representation of $SU(N)$,

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}.
$$

The gauge field is Lie-algebra-valued:

$$
A_\mu=A_\mu^aT^a.
$$

The field strength is

$$
F_{\mu\nu}
=\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu],
$$

or

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

The sign of the last term is not an independent choice. It follows from using $D_\mu=\partial_\mu+igA_\mu$ and $[D_\mu,D_\nu]=igF_{\mu\nu}$.

## Building the gauge-invariant kinetic term

Under a gauge transformation,

$$
F_{\mu\nu}^U=U^{-1}F_{\mu\nu}U.
$$

Therefore

$$
\begin{aligned}
\operatorname{tr}(F_{\mu\nu}^UF^{U\mu\nu})
&=\operatorname{tr}(U^{-1}F_{\mu\nu}UU^{-1}F^{\mu\nu}U)\\
&=\operatorname{tr}(U^{-1}F_{\mu\nu}F^{\mu\nu}U)\\
&=\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
\end{aligned}
$$

The Yang–Mills action is

$$
S_{\mathrm{YM}}
=-\frac12\int d^4x\,\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

With $F_{\mu\nu}=F_{\mu\nu}^aT^a$ and $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$,

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
=\frac12F_{\mu\nu}^aF^{a\mu\nu},
$$

so

$$
S_{\mathrm{YM}}
=-\frac14\int d^4x\,F_{\mu\nu}^aF^{a\mu\nu}.
$$

This normalization gives the usual free kinetic term for each gauge boson in the weak-field limit.

## Why there is no bare gauge-boson mass

A tempting Lorentz scalar is

$$
\operatorname{tr}(A_\mu A^\mu).
$$

It is not gauge invariant. The reason is the inhomogeneous term in the gauge transformation:

$$
A_\mu\mapsto U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

Even in QED, $A_\mu A^\mu$ changes under $A_\mu\mapsto A_\mu+\partial_\mu\alpha$. In Yang–Mills theory the problem is worse, not better. Thus a bare term

$$
\frac12m^2A_\mu^aA^{a\mu}
$$

would explicitly break gauge invariance.

This is the classical seed of a major fact: gauge boson masses require either gauge-invariant mechanisms such as the Higgs mechanism, lower-dimensional topological terms such as Chern–Simons terms, boundary conditions, or effective descriptions in which gauge invariance is realized differently. A Proca mass added by hand is not the Yang–Mills theory of an unbroken gauge group.

:::note[Massless does not mean noninteracting]
Gauge invariance forbids a bare mass term for an unbroken Yang–Mills gauge boson, but it does not forbid gauge-boson self-interactions. Those self-interactions are already inside $F_{\mu\nu}^aF^{a\mu\nu}$.
:::

## Self-interactions from curvature squared

Split the field strength into a derivative piece and a nonlinear piece:

$$
F_{\mu\nu}^a
=f_{\mu\nu}^a-gf^{abc}A_\mu^bA_\nu^c,
\qquad
f_{\mu\nu}^a=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a.
$$

Then

$$
F_{\mu\nu}^aF^{a\mu\nu}
=
 f_{\mu\nu}^af^{a\mu\nu}
-2g f^{abc}f_{\mu\nu}^a A^{b\mu}A^{c\nu}
+g^2 f^{abc}f^{ade}A_\mu^bA_\nu^cA^{d\mu}A^{e\nu}.
$$

Thus

$$
\mathcal L_{\mathrm{YM}}
=\mathcal L_{\mathrm{free}}
+\mathcal L_{AAA}
+\mathcal L_{AAAA},
$$

where schematically

$$
\mathcal L_{AAA}\sim g(\partial A)AA,
\qquad
\mathcal L_{AAAA}\sim g^2A^4.
$$

This is the sharp classical difference from Maxwell theory. In an Abelian theory, $f^{abc}=0$, so the photon has no self-coupling from $F^2$. In a non-Abelian theory, the gauge bosons carry adjoint gauge charge and interact with each other.

The detailed three- and four-gauge-boson Feynman rules are derived later. On this page the important point is structural: self-interactions are not optional decorations; they are forced by gauge invariance once the group is non-Abelian.

## Classical equations of motion

For a variation $\delta A_\mu$, the field strength varies covariantly:

$$
\delta F_{\mu\nu}
=D_\mu\delta A_\nu-D_\nu\delta A_\mu,
$$

where the adjoint covariant derivative is

$$
D_\mu X=\partial_\mu X+ig[A_\mu,X].
$$

The variation of the pure Yang–Mills action is

$$
\delta S_{\mathrm{YM}}
=-\int d^4x\,\operatorname{tr}(F^{\mu\nu}\delta F_{\mu\nu}).
$$

Using antisymmetry of $F^{\mu\nu}$,

$$
\delta S_{\mathrm{YM}}
=-2\int d^4x\,\operatorname{tr}(F^{\mu\nu}D_\mu\delta A_\nu).
$$

After integrating by parts covariantly and dropping the boundary term,

$$
\delta S_{\mathrm{YM}}
=2\int d^4x\,\operatorname{tr}((D_\mu F^{\mu\nu})\delta A_\nu).
$$

Therefore the source-free Yang–Mills equation is

$$
\boxed{
D_\mu F^{\mu\nu}=0.
}
$$

In components,

$$
(D_\mu F^{\mu\nu})^a
=\partial_\mu F^{a\mu\nu}-gf^{abc}A_\mu^bF^{c\mu\nu}=0.
$$

This equation is nonlinear even in the absence of matter, because $F_{\mu\nu}$ itself contains $A_\mu A_\nu$ and the covariant derivative contains $A_\mu$.

## Coupling to matter currents

For a Dirac field in representation $R$,

$$
\mathcal L_{\mathrm{matter}}
=\bar\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu+igA_\mu^aT_R^a.
$$

Since

$$
i\gamma^\mu D_\mu
=i\gamma^\mu\partial_\mu-g\gamma^\mu A_\mu^aT_R^a,
$$

the interaction term is

$$
\mathcal L_{\mathrm{int}}
=-gA_\mu^a\bar\psi\gamma^\mu T_R^a\psi.
$$

Define the matter current

$$
J^{a\mu}=\bar\psi\gamma^\mu T_R^a\psi.
$$

Then the coupled classical equation is

$$
\boxed{
(D_\mu F^{\mu\nu})^a=gJ^{a\nu}.
}
$$

For several matter fields, $J^{a\nu}$ is the sum over all fields, each with the generator in its own representation. For scalars, the current contains covariant derivatives of the scalar field rather than the Dirac bilinear above.

A subtle but important statement replaces ordinary current conservation. The Yang–Mills equation implies a covariant conservation law,

$$
(D_\nu J^\nu)^a=0,
$$

when matter equations of motion are used. This is not the same as $\partial_\nu J^{a\nu}=0$. In a gauge theory, the adjoint index is itself frame-dependent; the covariant derivative is the natural one.

## Bianchi identity

The field strength also obeys a geometric identity independent of the action:

$$
D_{[\lambda}F_{\mu\nu]}=0.
$$

Equivalently,

$$
D_\lambda F_{\mu\nu}+D_\mu F_{\nu\lambda}+D_\nu F_{\lambda\mu}=0.
$$

This is the non-Abelian Bianchi identity. It follows from the Jacobi identity for covariant derivatives:

$$
[D_\lambda,[D_\mu,D_\nu]]
+[D_\mu,[D_\nu,D_\lambda]]
+[D_\nu,[D_\lambda,D_\mu]]=0.
$$

In Maxwell theory, the Bianchi identity is the pair of homogeneous equations

$$
\nabla\cdot\mathbf B=0,
\qquad
\nabla\times\mathbf E+\partial_t\mathbf B=0.
$$

In Yang–Mills theory the same geometric idea survives, but every derivative is covariant.

## Energy density and sign check

With mostly-minus metric,

$$
F_{\mu\nu}^aF^{a\mu\nu}=2(\mathbf B^a\cdot\mathbf B^a-\mathbf E^a\cdot\mathbf E^a).
$$

Therefore

$$
\mathcal L_{\mathrm{YM}}
=\frac12(\mathbf E^a\cdot\mathbf E^a-\mathbf B^a\cdot\mathbf B^a).
$$

The Hamiltonian density is positive classically:

$$
\mathcal H_{\mathrm{YM}}
=\frac12(\mathbf E^a\cdot\mathbf E^a+\mathbf B^a\cdot\mathbf B^a),
$$

subject to the Gauss-law constraint. This is a good sign check: the Lorentzian Lagrangian is not positive definite, but the classical energy density is.

## The theta term is a separate invariant

In four dimensions there is another local gauge-invariant Lorentz scalar made from $F$:

$$
F_{\mu\nu}^a\widetilde F^{a\mu\nu},
\qquad
\widetilde F^{a\mu\nu}=\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma}^a.
$$

It is usually written as

$$
\mathcal L_\theta
=\frac{\theta g^2}{32\pi^2}F_{\mu\nu}^a\widetilde F^{a\mu\nu},
$$

up to convention choices for $\epsilon^{\mu\nu\rho\sigma}$. Locally this term is a total derivative, so it does not change the classical equations of motion on topologically trivial field configurations with suitable boundary behavior. Globally it matters enormously: instantons, theta vacua, the strong CP problem, and topological susceptibility all know about it.

For that reason, $\mathcal L_\theta$ is not treated as part of the minimal Yang–Mills kinetic term here. It returns in the QCD and topology pages.

## Abelian comparison

The replacement

$$
G\to U(1),
\qquad
f^{abc}\to0,
$$

turns Yang–Mills theory into Maxwell theory. The field strength becomes

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
$$

the equation of motion becomes

$$
\partial_\mu F^{\mu\nu}=J^\nu,
$$

and the Bianchi identity becomes

$$
\partial_{[\lambda}F_{\mu\nu]}=0.
$$

The non-Abelian formulas are therefore not an unrelated invention. They are the unique local generalization that keeps covariance under spacetime-dependent internal frame rotations.

## Common pitfalls

**Thinking the action is free because it is quadratic in $F$.** It is quadratic in the curvature, not quadratic in the gauge potential. Since $F$ contains $A^2$, the action contains $A^3$ and $A^4$ terms.

**Adding a mass term by analogy with Proca theory.** A Proca mass is compatible with Lorentz invariance but not with unbroken Yang–Mills gauge invariance. Massive $W$ and $Z$ bosons arise through the Higgs mechanism, not by adding $m^2A_\mu^aA^{a\mu}/2$ to an unbroken gauge theory.

**Forgetting generator normalization.** The equality $-\frac12\operatorname{tr}(F^2)=-\frac14F^aF^a$ assumes $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$. With a different normalization, factors move between the trace, the coupling, and component fields.

**Calling $\partial_\mu F^{a\mu\nu}=0$ the Yang–Mills equation.** The correct equation is covariant: $(D_\mu F^{\mu\nu})^a=0$. The ordinary derivative alone misses the gauge-field self-coupling.

**Confusing gauge invariance with global color conservation.** The equation $D_\mu F^{\mu\nu}=gJ^\nu$ uses a covariant current. Whether a global charge exists depends on boundary conditions and the treatment of gauge transformations at infinity.

**Treating the theta term as just another harmless total derivative.** Perturbatively around the trivial vacuum it often disappears, but nonperturbatively it labels physically distinct theories in four-dimensional non-Abelian gauge theory.

## Relations to other pages

- [Non-Abelian Gauge Transformations](/gauge-theories-standard-model/yang-mills/non-abelian-gauge-transformations/) derives the transformation laws that make the action gauge invariant.
- [Non-Abelian Field Strength](/gauge-theories-standard-model/yang-mills/non-abelian-field-strength/) expands the curvature formula, Bianchi identity, and small-loop interpretation in detail.
- [Field Strength and Curvature](/gauge-theories-standard-model/gauge-principle/field-strength-and-curvature/) gives the gauge-principle version before specializing to Yang–Mills dynamics.
- [Gauge-Invariant Observables](/gauge-theories-standard-model/gauge-principle/gauge-invariant-observables/) explains why traces and Wilson loops, not bare gauge potentials, are physical objects.
- Gauge-Boson Self-Interactions derives the three- and four-gauge-boson vertices implied by this action.
- Gauge Quantization later explains why gauge fixing, ghosts, and BRST symmetry are needed to quantize the same action covariantly.

## Research status

The classical Yang–Mills action is settled. Its local gauge invariance, equations of motion, Bianchi identity, and perturbative expansion are standard ingredients of modern QFT.

The deep research questions begin when this action is quantized. Pure Yang–Mills theory in four dimensions is expected to have a mass gap and confinement for compact simple gauge groups such as $SU(3)$, but a complete mathematical proof remains a landmark open problem. The perturbative running coupling, instantons, theta dependence, center symmetry, line operators, and large-$N$ limits are different windows into the same deceptively compact action.

## Exercises

### Exercise 1: Gauge invariance of the Yang–Mills kinetic term

Use

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U
$$

and cyclicity of the trace to show that

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
$$

is gauge invariant.

<details>
<summary><strong>Solution</strong></summary>

Under a gauge transformation,

$$
\begin{aligned}
\operatorname{tr}(F_{\mu\nu}^UF^{U\mu\nu})
&=\operatorname{tr}(U^{-1}F_{\mu\nu}UU^{-1}F^{\mu\nu}U)\\
&=\operatorname{tr}(U^{-1}F_{\mu\nu}F^{\mu\nu}U).
\end{aligned}
$$

Cyclicity gives

$$
\operatorname{tr}(U^{-1}F_{\mu\nu}F^{\mu\nu}U)
=\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}UU^{-1})
=\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

</details>

### Exercise 2: Component normalization

Assume

$$
F_{\mu\nu}=F_{\mu\nu}^aT^a,
\qquad
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}.
$$

Show that

$$
-\frac12\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
=-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
$$

<details>
<summary><strong>Solution</strong></summary>

Insert $F_{\mu\nu}=F_{\mu\nu}^aT^a$:

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
=F_{\mu\nu}^aF^{b\mu\nu}\operatorname{tr}(T^aT^b).
$$

Using the normalization,

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
=\frac12F_{\mu\nu}^aF^{a\mu\nu}.
$$

Therefore

$$
-\frac12\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
=-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
$$

</details>

### Exercise 3: Variation of the action

Using

$$
\delta F_{\mu\nu}=D_\mu\delta A_\nu-D_\nu\delta A_\mu,
$$

show that the source-free Yang–Mills equation is

$$
D_\mu F^{\mu\nu}=0.
$$

<details>
<summary><strong>Solution</strong></summary>

The variation is

$$
\delta S_{\mathrm{YM}}
=-\int d^4x\,\operatorname{tr}(F^{\mu\nu}\delta F_{\mu\nu}).
$$

Substitute the variation of $F$:

$$
\delta S_{\mathrm{YM}}
=-\int d^4x\,\operatorname{tr}\{F^{\mu\nu}(D_\mu\delta A_\nu-D_\nu\delta A_\mu)\}.
$$

Relabel $\mu\leftrightarrow\nu$ in the second term and use $F^{\nu\mu}=-F^{\mu\nu}$ to get

$$
\delta S_{\mathrm{YM}}
=-2\int d^4x\,\operatorname{tr}(F^{\mu\nu}D_\mu\delta A_\nu).
$$

Covariant integration by parts gives

$$
\delta S_{\mathrm{YM}}
=2\int d^4x\,\operatorname{tr}((D_\mu F^{\mu\nu})\delta A_\nu),
$$

up to a boundary term. Since $\delta A_\nu$ is arbitrary,

$$
D_\mu F^{\mu\nu}=0.
$$

</details>

### Exercise 4: Identify the self-interactions

Let

$$
F_{\mu\nu}^a=f_{\mu\nu}^a-gf^{abc}A_\mu^bA_\nu^c,
\qquad
f_{\mu\nu}^a=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a.
$$

Expand $-\frac14F_{\mu\nu}^aF^{a\mu\nu}$ and identify the terms cubic and quartic in $A$.

<details>
<summary><strong>Solution</strong></summary>

Substitute the split:

$$
F_{\mu\nu}^aF^{a\mu\nu}
=
 f_{\mu\nu}^af^{a\mu\nu}
-2g f^{abc}f_{\mu\nu}^aA^{b\mu}A^{c\nu}
+g^2 f^{abc}f^{ade}A_\mu^bA_\nu^cA^{d\mu}A^{e\nu}.
$$

Therefore

$$
\mathcal L_{\mathrm{YM}}
=-\frac14f_{\mu\nu}^af^{a\mu\nu}
+\frac{g}{2}f^{abc}f_{\mu\nu}^aA^{b\mu}A^{c\nu}
-\frac{g^2}{4}f^{abc}f^{ade}A_\mu^bA_\nu^cA^{d\mu}A^{e\nu}.
$$

The second term is cubic in $A$ and gives the three-gauge-boson vertex. The third term is quartic in $A$ and gives the four-gauge-boson vertex.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §69, for non-Abelian gauge theory and the Yang–Mills Lagrangian in a compact graduate-textbook treatment.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 25, for Yang–Mills theory, Wilson lines, and gauge-invariant structures.
- Zee, *Quantum Field Theory in a Nutshell*, non-Abelian gauge theory chapters, for intuition about why non-Abelian gauge bosons self-interact.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, §§15.1–15.3, for non-Abelian gauge invariance, Yang–Mills Lagrangians, field equations, and conservation laws.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for a classic route through gauge fields, spontaneous symmetry breaking, and the Higgs phenomenon.
- Polyakov, *Gauge Fields and Strings*, Chs. 1–3, for gauge fields as dynamical systems whose action later supports strong-coupling and loop-based viewpoints.

## Version history

- **2026-06-17:** Initial polished draft. Added the action architecture figure and derived the classical Yang–Mills equations in the volume convention.
