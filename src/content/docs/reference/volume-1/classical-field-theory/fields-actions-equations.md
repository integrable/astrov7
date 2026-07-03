---
title: "Fields, Actions, and Equations"
description: "Classical fields as spacetime degrees of freedom, local actions, variational derivatives, Euler–Lagrange equations, boundary terms, and the first examples used throughout QFT."
sidebar:
  label: "Fields, Actions, and Equations"
  order: 1
level: Graduate
status: "Polished draft"
topics:
  - classical field theory
  - action principle
  - Euler–Lagrange equations
  - boundary terms
  - scalar field
  - Maxwell theory
canonicalTopics:
  - fields-actions-equations
  - field-euler-lagrange-equations
  - local-action
---

## Summary

A classical field theory assigns dynamical variables to every spacetime point. Instead of finitely many generalized coordinates $q^a(t)$, one studies fields

$$
\phi^A(x),
\qquad x^\mu=(t,\mathbf x),
$$

where $A$ labels field components, species, or internal indices. The basic object is the action

$$
S[\phi]=\int d^4x\,\mathcal L(\phi,\partial\phi,x).
$$

For local first-derivative theories, stationary action gives the field Euler–Lagrange equations

$$
\boxed{
\frac{\partial\mathcal L}{\partial\phi^A}
-\partial_\mu\left(\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}\right)=0.
}
$$

Everything nearby in Foundations uses this formula. Canonical quantization starts from $\phi$ and its conjugate momentum. Path integrals start from $e^{iS}$. Noether's theorem studies how $S$ changes under transformations. The stress tensor comes from spacetime translations of the same action.

## What to know before reading

You should know the variational principle in ordinary mechanics, special relativity, integration by parts, and the conventions in [Conventions and Normalizations](/foundations/conventions-and-normalizations/). We use mostly-minus signature,

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
$$

and natural units $\hbar=c=1$.

## Mechanics to fields

The essential replacement is

$$
q^a(t)
\quad\longrightarrow\quad
\phi^A(t,\mathbf x).
$$

In mechanics, $a$ labels a finite set of coordinates. In field theory, the pair $(A,\mathbf x)$ labels continuously many degrees of freedom. This is why the free quantum scalar field later decomposes into infinitely many oscillator modes.

The action upgrades in the same way:

$$
S[q]=\int dt\,L(q,\dot q,t)
\quad\longrightarrow\quad
S[\phi]=\int d^4x\,\mathcal L(\phi,\partial_\mu\phi,x).
$$

The ordinary Lagrangian is recovered by integrating the Lagrangian density over space:

$$
L(t)=\int d^3\mathbf x\,\mathcal L(t,\mathbf x).
$$

A useful reader habit: say “Lagrangian density” when you mean $\mathcal L$ and “Lagrangian” when you mean $L$. Many sign and dimension mistakes begin as innocent vocabulary fuzz.

## Fields are configuration variables

A classical field configuration is a function on spacetime, possibly with several components.

| Field | Notation | Value at a point | First role in QFT |
|---|---|---|---|
| real scalar | $\phi(x)$ | one real number | neutral spin-zero fields and order parameters |
| complex scalar | $\phi(x)$ | two real numbers | charged spin-zero fields |
| vector field | $A_\mu(x)$ | Lorentz vector | electromagnetism and gauge fields |
| spinor field | $\psi_\alpha(x)$ | spinor components | fermions after quantization |
| metric field | $g_{\mu\nu}(x)$ | symmetric tensor | gravity as a field theory |

On this page, fields are classical commuting variables. Later, quantum fields become operator-valued distributions in the canonical formalism, while path integrals integrate over field histories.

:::caution[A field is not automatically a wavefunction]
A classical field is a configuration variable. A quantum field is an operator-valued object or a path-integral variable. A single-particle wavefunction is a state-dependent object. They coincide only in special limits.
:::

## Local actions

A local first-derivative action has the form

$$
S[\phi]=\int_\Omega d^4x\,
\mathcal L(\phi^A(x),\partial_\mu\phi^A(x),x).
$$

“Local” means that the Lagrangian density at $x$ depends on fields and finitely many derivatives at $x$, not directly on field values far away. Higher-derivative and nonlocal effective actions occur later, but the first pass through QFT begins here.

Relativistic flat-space theories are usually built so that $\mathcal L$ is a Lorentz scalar. With qft.org conventions, common invariant terms include

$$
\partial_\mu\phi\partial^\mu\phi,
\qquad
m^2\phi^2,
\qquad
F_{\mu\nu}F^{\mu\nu},
\qquad
\overline\psi i\gamma^\mu\partial_\mu\psi.
$$

The action is dimensionless in units $\hbar=c=1$, so in four spacetime dimensions

$$
[S]=0,
\qquad
[d^4x]=-4,
\qquad
[\mathcal L]=4.
$$

Dimensional analysis starts as bookkeeping and becomes a theory of scale in renormalization and EFT.

## Deriving the field equations

Vary the fields by

$$
\phi^A(x)\mapsto\phi^A(x)+\delta\phi^A(x).
$$

For a first-derivative Lagrangian density,

$$
\delta\mathcal L
=\frac{\partial\mathcal L}{\partial\phi^A}\delta\phi^A
+\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}
\partial_\mu\delta\phi^A.
$$

Integrating the second term by parts gives

$$
\delta S
=\int_\Omega d^4x\,
\left[
\frac{\partial\mathcal L}{\partial\phi^A}
-\partial_\mu\left(\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}\right)
\right]\delta\phi^A
+\int_{\partial\Omega}d\Sigma_\mu\,
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}\delta\phi^A.
$$

If the allowed variations vanish on the boundary, or have compact support in the bulk, the boundary term drops out. Since the remaining variations are arbitrary, the bulk coefficient must vanish:

$$
\boxed{
\frac{\partial\mathcal L}{\partial\phi^A}
-\partial_\mu\left(\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}\right)=0.
}
$$

:::tip[Boundary terms are part of the problem]
For local bulk equations, compact-support variations are the cleanest first derivation. Boundary terms return later as conserved charges, gauge generators, variational-principle data, topological terms, and gravitational boundary terms.
:::

## Example: real scalar field

Take

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi - V(\phi).
$$

Then

$$
\frac{\partial\mathcal L}{\partial\phi}=-V'(\phi),
\qquad
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}=\partial^\mu\phi,
$$

so the equation of motion is

$$
\boxed{\Box\phi+V'(\phi)=0,}
\qquad
\Box=\partial_\mu\partial^\mu=\partial_t^2-\nabla^2.
$$

For

$$
V(\phi)=\frac12m^2\phi^2,
$$

this becomes the Klein–Gordon equation

$$
\boxed{(\Box+m^2)\phi=0.}
$$

With an external source,

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2+J\phi,
$$

the equation is

$$
(\Box+m^2)\phi=J.
$$

That source term is the classical ancestor of the source $J$ used in generating functionals.

## Example: complex scalar field

A complex scalar is treated as two independent real fields, or as $\phi$ and $\phi^\dagger$ varied independently. For

$$
\mathcal L
=\partial_\mu\phi^\dagger\partial^\mu\phi
-m^2\phi^\dagger\phi
-V(\phi^\dagger\phi),
$$

varying with respect to $\phi^\dagger$ gives

$$
(\Box+m^2)\phi+V'(\phi^\dagger\phi)\phi=0,
$$

and varying with respect to $\phi$ gives the conjugate equation. If the potential depends only on $\phi^\dagger\phi$, the theory has the global phase symmetry

$$
\phi\mapsto e^{i\alpha}\phi,
\qquad
\phi^\dagger\mapsto e^{-i\alpha}\phi^\dagger.
$$

The corresponding current is derived on [Noether's Theorem](/foundations/classical-field-theory/noether-theorem/).

## Example: Maxwell theory

Electromagnetism is written in terms of a vector potential $A_\mu$ and field strength

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

With an external current $j^\mu$,

$$
\mathcal L=-\frac14F_{\mu\nu}F^{\mu\nu}-j^\mu A_\mu.
$$

Varying $A_\mu$ gives

$$
\boxed{\partial_\mu F^{\mu\nu}=j^\nu.}
$$

Taking $\partial_\nu$ of both sides gives the consistency condition

$$
\partial_\nu j^\nu=0,
$$

because $\partial_\nu\partial_\mu F^{\mu\nu}=0$ by antisymmetry. The remaining Maxwell equations are the identity

$$
\partial_\rho F_{\mu\nu}+\partial_\mu F_{\nu\rho}+\partial_\nu F_{\rho\mu}=0,
$$

which follows from $F=dA$.

The transformation

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha
$$

leaves $F_{\mu\nu}$ invariant. In Hamiltonian language this becomes a constraint; in path-integral language it requires gauge fixing.

## Equivalent Lagrangians and total derivatives

If

$$
\mathcal L'=\mathcal L+\partial_\mu K^\mu,
$$

then

$$
S'[\phi]=S[\phi]+\int_{\partial\Omega}d\Sigma_\mu K^\mu.
$$

For fixed boundary values, the bulk Euler–Lagrange equations are unchanged. This is why one often integrates by parts and says that two Lagrangian densities are equivalent up to a total derivative.

The phrase is useful but not harmless. Boundary terms may change canonical momenta, conserved charges, topological phases, variational principles, and edge degrees of freedom.

## Off shell and on shell

An arbitrary field configuration is **off shell**. A field configuration satisfying the Euler–Lagrange equations is **on shell**.

This distinction matters because:

- the action is defined on off-shell fields;
- classical solutions are on shell;
- the path integral formally sums over off-shell configurations;
- external scattering states are eventually put on shell;
- field redefinitions can differ off shell while preserving on-shell observables.

## Relation to nearby pages

- [Classical Field Theory Overview](/foundations/classical-field-theory/) explains the chapter map.
- [Scalar Fields](/foundations/classical-field-theory/scalar-fields/) develops the scalar examples in more detail.
- [Noether's Theorem](/foundations/classical-field-theory/noether-theorem/) applies the same variation formula to symmetries.
- [Stress Tensor](/foundations/classical-field-theory/stress-tensor/) studies spacetime-translation currents.
- [Hamiltonian Field Theory](/foundations/classical-field-theory/hamiltonian-field-theory/) performs the Legendre transform on an equal-time slice.
- [Linearization and Normal Modes](/foundations/classical-field-theory/linearization-and-normal-modes/) expands the action around backgrounds.

## Exercises

### Exercise 1: Derive the field Euler–Lagrange equation

Starting from $S=\int d^4x\,\mathcal L(\phi^A,\partial_\mu\phi^A)$, derive the field Euler–Lagrange equations, keeping track of the boundary term.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\delta\mathcal L
=\frac{\partial\mathcal L}{\partial\phi^A}\delta\phi^A
+\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}\partial_\mu\delta\phi^A.
$$

Integrate the second term by parts. If the boundary term vanishes, stationarity for arbitrary $\delta\phi^A$ gives

$$
\frac{\partial\mathcal L}{\partial\phi^A}
-\partial_\mu\left(\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}\right)=0.
$$

</details>

### Exercise 2: Scalar source equation

For

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2+J\phi,
$$

derive the equation of motion.

<details>
<summary><strong>Solution</strong></summary>

Here $\partial\mathcal L/\partial\phi=-m^2\phi+J$ and $\partial\mathcal L/\partial(\partial_\mu\phi)=\partial^\mu\phi$. The Euler–Lagrange equation gives

$$
-m^2\phi+J-\Box\phi=0,
$$

or

$$
(\Box+m^2)\phi=J.
$$

</details>

### Exercise 3: Total derivative equivalence

Show that

$$
\frac12\partial_\mu\phi\partial^\mu\phi
$$

and

$$
-\frac12\phi\Box\phi
$$

differ by a total derivative.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\partial_\mu(\phi\partial^\mu\phi)
=\partial_\mu\phi\partial^\mu\phi+\phi\Box\phi.
$$

Therefore

$$
\frac12\partial_\mu\phi\partial^\mu\phi
=-\frac12\phi\Box\phi
+\frac12\partial_\mu(\phi\partial^\mu\phi).
$$

</details>

## References

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 4.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§7.1–7.2.
- M. Srednicki, *Quantum Field Theory*, §§2–3 and §12.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed., Parts I.3 and I.10.

## Version history

- **2026-06-08:** Revised for reader flow, reduced repetition, clarified field/wavefunction distinction, tightened examples, and added a chapter overview link.
- **2026-05-22:** Initial qft.org page.
