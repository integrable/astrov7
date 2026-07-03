---
title: "Linearization and Normal Modes"
description: "Small fluctuations around classical backgrounds, quadratic actions, stability, normal modes, Fourier modes, zero modes, and the oscillator decomposition underlying free quantum fields."
sidebar:
  label: "Linearization and Normal Modes"
  order: 7
level: Graduate
status: "Polished draft"
topics:
  - linearization
  - normal modes
  - quadratic actions
  - stability
  - zero modes
  - Fourier modes
canonicalTopics:
  - quadratic-action
  - normal-mode-decomposition
  - fluctuation-operator
  - zero-mode
  - oscillator-decomposition
---

## Summary

Linearization is the move from a nonlinear field theory to the theory of small fluctuations around a chosen background. Write

$$
\phi^A(x)=\bar\phi^A(x)+\eta^A(x).
$$

Expanding the action gives

$$
S[\bar\phi+\eta]
=S[\bar\phi]+S_1[\eta]+S_2[\eta]+S_3[\eta]+\cdots .
$$

If the background $\bar\phi^A$ satisfies the classical equations of motion and the variations obey the chosen boundary conditions, the linear term $S_1$ vanishes. The leading fluctuation dynamics is the quadratic action

$$
S_2=\frac12\int d^4x\,d^4y\,\eta^A(x)K_{AB}(x,y)\eta^B(y),
$$

or a local differential-operator version of the same expression. The linearized equation is

$$
K_{AB}\eta^B=0,
$$

up to a conventional sign in $K$.

Normal modes are the fluctuation patterns that diagonalize this quadratic problem. For a scalar field around a translation-invariant vacuum,

$$
\omega_{\mathbf k}^2=\mathbf k^2+M^2.
$$

The quadratic Hamiltonian is a sum of independent harmonic oscillators, one per mode:

$$
\boxed{\text{free field theory begins as normal-mode mechanics.}}
$$

That sentence is the bridge from classical fields to creation and annihilation operators.

## What to know before reading

You should know the action principle from [Fields, Actions, and Equations](/foundations/classical-field-theory/fields-actions-equations/), scalar potentials from [Scalar Fields](/foundations/classical-field-theory/scalar-fields/), Hamiltonian phase space from [Hamiltonian Field Theory](/foundations/classical-field-theory/hamiltonian-field-theory/), and the constraint warning from [Constraints](/foundations/classical-field-theory/constraints/).

We use the qft.org conventions from [Conventions and Normalizations](/foundations/conventions-and-normalizations/):

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
\qquad \hbar=c=1.
$$

:::note[Scope]
This page is classical. Quantization comes later. Gauge fields require constraint reduction or gauge fixing before their normal modes can be counted physically. Fermions require a first-order, graded version of the same idea.
:::

## Core idea

Most field theories are nonlinear. Near a well-chosen classical configuration, the leading approximation is quadratic. Quadratic theories are special: their equations are linear, their modes decouple, and their Hamiltonians are sums of oscillators.

The chain is

$$
\text{background}
\longrightarrow
\text{small fluctuation}
\longrightarrow
\text{quadratic action}
\longrightarrow
\text{normal modes}
\longrightarrow
\text{oscillators}.
$$

<figure class="doc-figure" style="--figure-width: 46rem;">

![From small fluctuations to quadratic actions, normal modes, and decoupled oscillators](/figures/foundations/linearization-normal-modes.svg)

<figcaption>

Linearization expands a field near a background, keeps the quadratic action, diagonalizes the resulting operator, and rewrites the small-fluctuation dynamics as independent oscillator modes. Quantization later replaces each oscillator by creation and annihilation operators.

</figcaption>
</figure>

A quadratic Hamiltonian of the form

$$
H_2=\sum_n\frac12\left(p_n^2+\omega_n^2q_n^2\right)
$$

is not a metaphor. It literally is the Hamiltonian of a collection of harmonic oscillators. The field-theory novelty is that there may be infinitely many modes.

## Expanding around a background

Let

$$
S[\phi]=\int d^4x\,\mathcal L(\phi^A,\partial_\mu\phi^A)
$$

and choose a background field $\bar\phi^A(x)$. Write

$$
\phi^A(x)=\bar\phi^A(x)+\eta^A(x).
$$

The first variation has the form

$$
\delta S
=\int d^4x\,E_A(\bar\phi)\eta^A
+\text{boundary term},
$$

where

$$
E_A(\phi)
=\frac{\partial\mathcal L}{\partial\phi^A}
-\partial_\mu\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}
$$

is the Euler–Lagrange expression. If

$$
E_A(\bar\phi)=0
$$

and the boundary term vanishes, then $S_1[\eta]=0$. The leading fluctuation action is $S_2$.

:::caution[Do not drop the linear term unless the background is stationary]
Expanding around an arbitrary field configuration is allowed, but the linear term usually remains. Dropping it is equivalent to pretending that the background solves the equations of motion.
:::

## Quadratic action for a scalar field

For one real scalar field,

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi-V(\phi),
$$

the equation of motion is

$$
\Box\phi+V'(\phi)=0,
\qquad
\Box=\partial_t^2-\nabla^2.
$$

Write

$$
\phi=\bar\phi+\eta.
$$

The potential expands as

$$
V(\bar\phi+\eta)
=V(\bar\phi)+V'(\bar\phi)\eta
+\frac12V''(\bar\phi)\eta^2
+\frac1{3!}V'''(\bar\phi)\eta^3+\cdots .
$$

The kinetic term gives a cross term $\partial_\mu\bar\phi\partial^\mu\eta$, which becomes part of the linear term after integration by parts. If $\bar\phi$ is on shell, the linear terms vanish and the quadratic Lagrangian is

$$
\boxed{
\mathcal L_2
=\frac12\partial_\mu\eta\partial^\mu\eta
-\frac12V''(\bar\phi)\eta^2.
}
$$

If $\bar\phi$ is constant, define

$$
M^2=V''(\bar\phi),
$$

so the fluctuation satisfies

$$
\boxed{(\Box+M^2)\eta=0.}
$$

This is the Klein–Gordon equation for the fluctuation field.

## Stability and mass squared

For a constant scalar background, the quadratic Hamiltonian density is

$$
\mathcal H_2
=\frac12\dot\eta^2+\frac12(\nabla\eta)^2+\frac12M^2\eta^2.
$$

The sign of $M^2$ diagnoses the background:

| $M^2$ | Meaning near the background |
|---:|---|
| $M^2>0$ | stable small oscillations |
| $M^2=0$ | flat direction, massless mode, symmetry mode, or critical fluctuation |
| $M^2<0$ | instability of the chosen background |

For a plane-wave fluctuation,

$$
\eta(t,\mathbf x)=\eta_{\mathbf k}(t)e^{i\mathbf k\cdot\mathbf x},
$$

the linearized equation becomes

$$
\ddot\eta_{\mathbf k}+\omega_{\mathbf k}^2\eta_{\mathbf k}=0,
\qquad
\boxed{\omega_{\mathbf k}^2=\mathbf k^2+M^2.}
$$

If $M^2<0$, modes with $\mathbf k^2<|M^2|$ grow exponentially. This is often called a **tachyonic instability**, but the phrase means the background is unstable. It does not mean the stable theory contains faster-than-light particles.

## Normal modes in finite volume

Place the system in a box and choose boundary conditions. Suppose the quadratic Lagrangian is

$$
L_2=\frac12\int d^3\mathbf x\,
\left[\dot\eta^2-\eta\,\Omega^2\eta\right],
$$

where, for a scalar field,

$$
\Omega^2=-\nabla^2+M^2.
$$

Let $u_n(\mathbf x)$ be orthonormal eigenfunctions:

$$
\Omega^2u_n=\omega_n^2u_n,
\qquad
\int d^3\mathbf x\,u_m u_n=\delta_{mn}.
$$

Expand

$$
\eta(t,\mathbf x)=\sum_n q_n(t)u_n(\mathbf x).
$$

Then

$$
\boxed{L_2=\sum_n\frac12(\dot q_n^2-\omega_n^2q_n^2)}
$$

and

$$
\boxed{H_2=\sum_n\frac12(p_n^2+\omega_n^2q_n^2).}
$$

That is the oscillator decomposition in its cleanest classical form.

## Fourier modes in infinite volume

On $\mathbb R^3$ with a translation-invariant background, plane waves diagonalize the quadratic action. With qft.org Fourier conventions,

$$
\eta(t,\mathbf x)
=\int\frac{d^3\mathbf k}{(2\pi)^3}\,
\eta_{\mathbf k}(t)e^{i\mathbf k\cdot\mathbf x}.
$$

For a real field,

$$
\eta_{-\mathbf k}=\eta_{\mathbf k}^*.
$$

The linearized equation gives

$$
\ddot\eta_{\mathbf k}+\omega_{\mathbf k}^2\eta_{\mathbf k}=0,
\qquad
\omega_{\mathbf k}=\sqrt{\mathbf k^2+M^2}.
$$

A real solution may be written as

$$
\eta(t,\mathbf x)
=\int\frac{d^3\mathbf k}{(2\pi)^3}
\left[
A_{\mathbf k}e^{-i\omega_{\mathbf k}t+i\mathbf k\cdot\mathbf x}
+A_{\mathbf k}^*e^{+i\omega_{\mathbf k}t-i\mathbf k\cdot\mathbf x}
\right].
$$

Later, canonical quantization replaces the classical amplitudes by operators and inserts the normalization $1/\sqrt{2\omega_{\mathbf k}}$ required by the equal-time commutator and relativistic one-particle normalization.

## Coupled fields and mass matrices

For several real scalar fields,

$$
\mathcal L
=\frac12\partial_\mu\phi^A\partial^\mu\phi^A
-V(\phi^1,\ldots,\phi^N),
$$

expand around a constant stationary point $v^A$:

$$
\phi^A=v^A+\eta^A,
\qquad
\left.\frac{\partial V}{\partial\phi^A}\right|_v=0.
$$

The quadratic Lagrangian is

$$
\boxed{
\mathcal L_2
=\frac12\partial_\mu\eta^A\partial^\mu\eta^A
-\frac12\eta^A M^2_{AB}\eta^B,
}
$$

where

$$
\boxed{
M^2_{AB}
=\left.\frac{\partial^2V}{\partial\phi^A\partial\phi^B}\right|_v.
}
$$

If $M^2_{AB}$ is real and symmetric, an orthogonal rotation diagonalizes it. The normal fields obey independent Klein–Gordon equations:

$$
(\Box+m_a^2)\chi^a=0.
$$

At the classical quadratic level,

$$
\boxed{\text{mass eigenstates are normal modes.}}
$$

In the full quantum theory, quantum corrections shift masses and unstable excitations require a more careful interpretation.

## Example: double-well scalar theory

Consider

$$
V(\phi)=\frac\lambda4(\phi^2-v^2)^2,
\qquad
\lambda>0,
\qquad
v>0.
$$

The stationary points are

$$
\phi=0,\qquad \phi=+v,\qquad \phi=-v.
$$

Since

$$
V''(\phi)=\lambda(3\phi^2-v^2),
$$

we get

$$
V''(\pm v)=2\lambda v^2>0,
\qquad
V''(0)=-\lambda v^2<0.
$$

The minima $\phi=\pm v$ support stable massive fluctuations with

$$
M^2=2\lambda v^2.
$$

The point $\phi=0$ has a tachyonic fluctuation. The linearized theory is not saying “there is a tachyon particle.” It is saying “you expanded around the top of the hill.”

## Spatially varying backgrounds

Backgrounds need not be constant. Solitons, domain walls, vortices, instantons after Wick rotation, time-dependent classical solutions, and backgrounds with defects all require expanding around nontrivial field profiles.

For a static scalar background $\phi_0^A(\mathbf x)$, the fluctuation operator often has the Schrödinger-like form

$$
\mathcal O_{AB}=-\delta_{AB}\nabla^2+U_{AB}(\mathbf x),
$$

with

$$
U_{AB}(\mathbf x)
=\left.\frac{\partial^2V}{\partial\phi^A\partial\phi^B}\right|_{\phi_0(\mathbf x)}.
$$

Separated solutions

$$
\eta^A(t,\mathbf x)=q_n(t)u_n^A(\mathbf x)
$$

lead to

$$
\mathcal O_{AB}u_n^B=\omega_n^2u_n^A,
\qquad
\ddot q_n+\omega_n^2q_n=0.
$$

The spectrum of $\mathcal O$ distinguishes stable oscillations, zero modes, negative modes, bound modes, and continuum modes.

## Zero modes

A zero mode is a fluctuation with zero eigenvalue of the quadratic operator. It can mean different things in different contexts.

| Situation | What the zero mode means |
|---|---|
| flat direction | motion along degenerate classical vacua |
| broken global symmetry | Goldstone mode, when assumptions apply |
| soliton translation | collective coordinate for the soliton position |
| gauge redundancy | unphysical direction to be fixed or divided out |
| critical point | diverging correlation length or massless fluctuation |

A useful general source of zero modes is a continuous family of solutions. If

$$
\bar\phi^A(x;\alpha)
$$

solves the equations for every $\alpha$, then differentiating the equations with respect to $\alpha$ gives

$$
K_{AB}\frac{\partial\bar\phi^B}{\partial\alpha}=0.
$$

So the derivative along a family of solutions is a zero mode.

:::caution[Not every zero mode is a particle]
A zero mode from a global broken symmetry can become a Goldstone field. A soliton translation mode becomes a collective coordinate. A gauge zero mode is not physical at all. The eigenvalue alone does not tell the whole story.
:::

## Boundary conditions matter

Normal modes are determined by the operator **and** the boundary conditions. In one spatial dimension on $0<x<L$:

| Boundary condition | Typical modes |
|---|---|
| periodic | $e^{i2\pi n x/L}$ |
| Dirichlet | $\sin(n\pi x/L)$ |
| Neumann | $\cos(n\pi x/L)$ |

In infinite volume, sums over modes often become integrals:

$$
\frac1V\sum_{\mathbf k}\longrightarrow\int\frac{d^3\mathbf k}{(2\pi)^3}.
$$

This replacement assumes the volume is large and the observable is insensitive to boundary effects.

## Interactions are higher-order terms

The quadratic action gives the free theory of fluctuations. Cubic and higher terms give interactions among those fluctuations:

$$
\mathcal L
=\mathcal L(v)
+\frac12\partial_\mu\eta\partial^\mu\eta
-\frac12V''(v)\eta^2
-\frac1{3!}V'''(v)\eta^3
-\frac1{4!}V''''(v)\eta^4
-\cdots .
$$

| Term | Role |
|---|---|
| constant | vacuum energy density |
| linear | vanishes if the background is on shell |
| quadratic | free propagation and normal modes |
| cubic and higher | interactions among fluctuations |

Perturbation theory starts from the quadratic part and treats the higher-order terms as interactions. This is why normal modes are not just a classical warm-up; they are the starting point for propagators, Wick contractions, Feynman diagrams, and loop corrections.

## Path-integral viewpoint

Around a classical background,

$$
S[\bar\phi+\eta]=S[\bar\phi]+\frac12\eta K\eta+O(\eta^3),
$$

schematically. Keeping only the quadratic part gives the Gaussian approximation

$$
Z\approx e^{iS[\bar\phi]}
\int\mathcal D\eta\,
\exp\left(\frac i2\eta K\eta\right).
$$

In Euclidean signature,

$$
Z_E\approx e^{-S_E[\bar\phi]}
\int\mathcal D\eta\,
\exp\left(-\frac12\eta K_E\eta\right)
\propto
\frac{e^{-S_E[\bar\phi]}}{\sqrt{\det K_E}},
$$

when $K_E$ is positive and has no zero modes. Normal modes diagonalize the determinant:

$$
\det K_E=\prod_n\lambda_n.
$$

Zero modes, negative modes, and infinite products require special treatment. Those issues return in semiclassical methods, instantons, anomalies, and one-loop effective actions.

## What this page is not doing

This page does not quantize the modes. The next operator steps are

$$
q_n,p_n\longrightarrow\hat q_n,\hat p_n,
\qquad
[\hat q_m,\hat p_n]=i\delta_{mn},
$$

and then

$$
a_n=\sqrt{\frac{\omega_n}{2}}\,\hat q_n
+\frac{i}{\sqrt{2\omega_n}}\,\hat p_n,
\qquad
H_2=\sum_n\omega_n\left(a_n^\dagger a_n+\frac12\right).
$$

That belongs in [Harmonic Oscillator Modes](/foundations/canonical-quantization/harmonic-oscillator-modes/) and [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/).

This page also does not fully treat gauge-field normal modes. Maxwell theory has two physical propagating modes, but seeing that correctly requires constraints, gauge fixing, or covariant quantization. Counting every component of $A_\mu$ as an ordinary scalar-like oscillator gives the wrong answer.

## Common pitfalls

### Linearizing around an off-shell background

If $\bar\phi$ does not satisfy the equations of motion, then the linear term does not vanish. The fluctuation is being driven by a source.

### Calling every negative mass squared a particle mass

A negative quadratic coefficient around a proposed vacuum usually means the proposed vacuum is unstable. It is not a healthy particle mass.

### Forgetting the reality condition

For a real scalar field,

$$
\eta_{-\mathbf k}=\eta_{\mathbf k}^*.
$$

The modes at $\mathbf k$ and $-\mathbf k$ are not independent complex degrees of freedom.

### Using plane waves when translation symmetry is absent

Plane waves diagonalize the quadratic action only when the background and boundary conditions are translation invariant.

### Ignoring zero modes

Zero modes may represent collective coordinates, Goldstone directions, gauge redundancies, or critical fluctuations. They should not be casually dropped.

### Confusing free modes with exact particles

Normal modes of the quadratic action are the starting point for particle language. In an interacting theory, exact particles are determined by the full quantum theory.

## Relation to nearby pages

- [Fields, Actions, and Equations](/foundations/classical-field-theory/fields-actions-equations/) defines the action principle and Euler–Lagrange equations used to identify backgrounds.
- [Scalar Fields](/foundations/classical-field-theory/scalar-fields/) explains scalar potentials and fluctuation masses.
- [Hamiltonian Field Theory](/foundations/classical-field-theory/hamiltonian-field-theory/) explains how a quadratic Lagrangian becomes a Hamiltonian on phase space.
- [Constraints](/foundations/classical-field-theory/constraints/) explains why gauge-field normal modes require constraint reduction or gauge fixing.
- [Harmonic Oscillator Modes](/foundations/canonical-quantization/harmonic-oscillator-modes/) quantizes the oscillator variables found here.
- [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/) applies the oscillator decomposition to the real Klein–Gordon field.
- [Finite-Dimensional Gaussians](/foundations/path-integral-formalism/finite-dimensional-gaussians/) and [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/) develop the Gaussian/determinant side of the same quadratic structure.
- [Semiclassical Expansion](/foundations/path-integral-formalism/semiclassical-expansion/) returns to nontrivial saddle points, zero modes, and determinants.

## Research status

- **Established:** Linearization, quadratic actions, stability tests, normal-mode decompositions, Fourier modes, and mass matrices are standard tools across classical field theory, QFT, statistical field theory, and condensed matter.
- **Active:** Zero modes, gauge redundancies, boundary conditions, negative modes, collective coordinates, and determinants remain technically important in semiclassical physics, solitons, instantons, gauge theory, and curved backgrounds.
- **Speculative:** None at the level of this page.

## Exercises

### Exercise 1: Quadratic action for a scalar field

Let

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi-V(\phi),
\qquad
\phi=\bar\phi+\eta.
$$

Assume $\bar\phi$ is a constant solution with $V'(\bar\phi)=0$. Show that

$$
\mathcal L_2=\frac12\partial_\mu\eta\partial^\mu\eta-\frac12V''(\bar\phi)\eta^2.
$$

<details>
<summary><strong>Solution</strong></summary>

Since $\bar\phi$ is constant, the kinetic term becomes $\frac12\partial_\mu\eta\partial^\mu\eta$. The potential expands as

$$
V(\bar\phi+\eta)=V(\bar\phi)+V'(\bar\phi)\eta+\frac12V''(\bar\phi)\eta^2+O(\eta^3).
$$

The linear term vanishes because $V'(\bar\phi)=0$. Dropping the constant leaves the desired quadratic Lagrangian.

</details>

### Exercise 2: Fourier modes of a Klein–Gordon fluctuation

For

$$
(\partial_t^2-\nabla^2+M^2)\eta=0,
$$

insert

$$
\eta(t,\mathbf x)=\eta_{\mathbf k}(t)e^{i\mathbf k\cdot\mathbf x}
$$

and identify $\omega_{\mathbf k}$.

<details>
<summary><strong>Solution</strong></summary>

Since $\nabla^2e^{i\mathbf k\cdot\mathbf x}=-\mathbf k^2e^{i\mathbf k\cdot\mathbf x}$, the equation becomes

$$
\ddot\eta_{\mathbf k}+(\mathbf k^2+M^2)\eta_{\mathbf k}=0.
$$

Thus

$$
\boxed{\omega_{\mathbf k}=\sqrt{\mathbf k^2+M^2}.}
$$

</details>

### Exercise 3: Hamiltonian as a sum of oscillators

For

$$
L_2=\sum_n\frac12(\dot q_n^2-\omega_n^2q_n^2),
$$

find the canonical momenta and Hamiltonian.

<details>
<summary><strong>Solution</strong></summary>

The momenta are

$$
p_n=\frac{\partial L_2}{\partial\dot q_n}=\dot q_n.
$$

Therefore

$$
H_2=\sum_n p_n\dot q_n-L_2
=\sum_n\frac12(p_n^2+\omega_n^2q_n^2).
$$

</details>

### Exercise 4: Two-field mass mixing

For

$$
\mathcal L_2
=\frac12\partial_\mu\eta_1\partial^\mu\eta_1
+\frac12\partial_\mu\eta_2\partial^\mu\eta_2
-\frac12
\begin{pmatrix}\eta_1&\eta_2\end{pmatrix}
\begin{pmatrix}m_1^2&\mu^2\\ \mu^2&m_2^2\end{pmatrix}
\begin{pmatrix}\eta_1\\ \eta_2\end{pmatrix},
$$

find the two mass-squared eigenvalues.

<details>
<summary><strong>Solution</strong></summary>

The eigenvalues of

$$
M^2=\begin{pmatrix}m_1^2&\mu^2\\ \mu^2&m_2^2\end{pmatrix}
$$

are

$$
\boxed{
\lambda_\pm
=\frac12\left[m_1^2+m_2^2
\pm\sqrt{(m_1^2-m_2^2)^2+4\mu^4}\right].
}
$$

</details>

### Exercise 5: Instability in the double well

For

$$
V(\phi)=\frac\lambda4(\phi^2-v^2)^2,
\qquad \lambda>0,
$$

show that $\phi=0$ is unstable and $\phi=\pm v$ support stable massive fluctuations.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
V'(\phi)=\lambda\phi(\phi^2-v^2),
\qquad
V''(\phi)=\lambda(3\phi^2-v^2).
$$

At $\phi=0$,

$$
V''(0)=-\lambda v^2<0,
$$

so long-wavelength modes have $\omega_{\mathbf k}^2=\mathbf k^2-\lambda v^2<0$. At $\phi=\pm v$,

$$
V''(\pm v)=2\lambda v^2>0,
$$

so the fluctuation mass squared is positive.

</details>

### Exercise 6: Zero mode from a family of solutions

Suppose $\bar\phi(x;\alpha)$ is a continuous family of solutions of $E(\phi)=0$. Show that

$$
\eta_0(x)=\frac{\partial\bar\phi(x;\alpha)}{\partial\alpha}
$$

solves the linearized equation.

<details>
<summary><strong>Solution</strong></summary>

Since $E(\bar\phi(x;\alpha))=0$ for every $\alpha$, differentiate with respect to $\alpha$:

$$
0=\frac{\partial}{\partial\alpha}E(\bar\phi(x;\alpha))
=\left.\frac{\delta E}{\delta\phi}\right|_{\bar\phi}
\frac{\partial\bar\phi}{\partial\alpha}.
$$

The operator $K=\left.\delta E/\delta\phi\right|_{\bar\phi}$ is the linearized equation-of-motion operator. Therefore $K\eta_0=0$.

</details>

## References

### Primary references

- J. L. Lagrange, *Mécanique Analytique* (1788), for the classical small-oscillation and normal-mode tradition.
- P. A. M. Dirac, *The Principles of Quantum Mechanics*, for the canonical oscillator language that later becomes creation and annihilation operators.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 2–4, for the occupation-number and harmonic-oscillator route to quantum fields.
- M. Srednicki, *Quantum Field Theory*, §§3 and 8, for scalar field mode expansion, canonical quantization, and the free-field path integral.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§7.1–7.2, for canonical variables and the transition to Hamiltonian form.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed., Parts I.3 and I.8, for the mattress-to-field intuition and canonical quantization.
- A. M. Polyakov, *Gauge Fields and Strings*, ch. 1, for the broad view of quantum fields as systems of infinitely many interacting degrees of freedom.

### For mathematical precision

- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, Vol. I, for Hilbert-space methods and spectral theory.
- G. B. Folland, *Quantum Field Theory: A Tourist Guide for Mathematicians*, for free fields, distributions, and mode decompositions.
- L. C. Evans, *Partial Differential Equations*, for eigenfunction expansions and linear PDE background.

## Version history

- **2026-06-08:** Revised for the Classical Field Theory chapter index pass: tightened the path from fluctuations to oscillators, reduced overlap with scalar-field and canonical-quantization pages, clarified zero-mode caveats, and made the handoff to quantization explicit.
- **2026-05-22:** Initial qft.org page on linearization, quadratic actions, stability, normal modes, Fourier modes, mass matrices, zero modes, boundary conditions, and the path-integral Gaussian viewpoint.
