---
title: "Noether's Theorem"
description: "Continuous symmetries of classical field theories, conserved currents, charges, current ambiguities, and the bridge to Ward identities in QFT."
sidebar:
  label: "Noether's Theorem"
  order: 3
level: Graduate
status: "Polished draft"
topics:
  - Noether theorem
  - conserved currents
  - global symmetries
  - charges
  - Ward identities
  - gauge redundancy
canonicalTopics:
  - noether-theorem
  - conserved-current
  - noether-charge
---

## Summary

Noether's theorem is the precise bridge between continuous symmetry and conservation. For fields $\phi^A(x)$ with Euler–Lagrange expressions

$$
E_A(\mathcal L)
=\frac{\partial\mathcal L}{\partial\phi^A}
-\partial_\mu\left(\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}\right),
$$

an infinitesimal internal transformation

$$
\delta\phi^A=\epsilon\Delta^A
$$

that changes the Lagrangian density by at most a total derivative,

$$
\delta\mathcal L=\epsilon\partial_\mu B^\mu,
$$

has current

$$
\boxed{
j^\mu=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}\Delta^A-B^\mu.
}
$$

The current satisfies the off-shell identity

$$
\boxed{\partial_\mu j^\mu=-E_A(\mathcal L)\Delta^A.}
$$

Therefore, on classical solutions,

$$
\boxed{\partial_\mu j^\mu=0.}
$$

In QFT, the corresponding charge normally generates the symmetry on fields and states, while current conservation becomes a Ward identity for correlation functions.

## What to know before reading

Use [Fields, Actions, and Equations](/foundations/classical-field-theory/fields-actions-equations/) for the variational identity. This page assumes a local first-derivative action and classical equations of motion. Quantum anomalies, BRST symmetry, and generalized symmetries are previews here, not the main event.

## Conservation is local

A conserved current obeys

$$
\partial_\mu j^\mu=0.
$$

In components,

$$
\partial_t j^0+\partial_i j^i=0.
$$

Integrating over a spatial region $V$ gives

$$
\frac{d}{dt}\int_Vd^3\mathbf x\,j^0
=-\oint_{\partial V}dS_i\,j^i.
$$

So charge changes inside $V$ only when current flows through the boundary. For all space, with sufficiently fast falloff, the total charge

$$
Q(t)=\int d^3\mathbf x\,j^0(t,\mathbf x)
$$

is conserved.

This is why Noether's theorem gives more than a conserved number. It gives a local continuity equation.

## The variational identity

For

$$
\mathcal L=\mathcal L(\phi^A,\partial_\mu\phi^A,x),
$$

define

$$
\Pi_A^\mu=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}.
$$

For any variation,

$$
\delta\mathcal L
=E_A(\mathcal L)\delta\phi^A
+\partial_\mu(\Pi_A^\mu\delta\phi^A).
$$

This identity is the engine of Noether's theorem. On shell, the first term vanishes; the second term tells you the current.

## Internal symmetries

Consider a transformation that does not move spacetime points:

$$
x^\mu\mapsto x^\mu,
\qquad
\phi^A(x)\mapsto\phi^A(x)+\epsilon\Delta^A(x),
$$

where $\epsilon$ is a constant infinitesimal parameter. If

$$
\delta\mathcal L=\epsilon\partial_\mu B^\mu,
$$

then substituting into the variational identity gives

$$
\partial_\mu(\Pi_A^\mu\Delta^A-B^\mu)=-E_A(\mathcal L)\Delta^A.
$$

Thus

$$
\boxed{j^\mu=\Pi_A^\mu\Delta^A-B^\mu.}
$$

The Lagrangian density need not be strictly invariant. A total derivative is enough for the action to be invariant under suitable boundary conditions.

:::tip[The local-parameter trick]
To find a current quickly, temporarily promote the constant parameter to $\epsilon(x)$. The coefficient of $\partial_\mu\epsilon$ in $\delta\mathcal L$ is the current, up to sign conventions and improvements. This trick later becomes the path-integral route to Ward identities.
:::

## Example: shift symmetry

For a massless scalar,

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi,
$$

the transformation

$$
\phi\mapsto\phi+\epsilon
$$

has $\Delta=1$ and $B^\mu=0$. Since $\Pi^\mu=\partial^\mu\phi$, the current is

$$
\boxed{j^\mu=\partial^\mu\phi.}
$$

On shell, $\Box\phi=0$, so $\partial_\mu j^\mu=0$.

If one adds a nonconstant potential $V(\phi)$, the same current candidate has on-shell divergence

$$
\partial_\mu j^\mu=-V'(\phi),
$$

so the shift symmetry is explicitly broken.

## Example: complex scalar U(1)

Take

$$
\mathcal L=\partial_\mu\phi^\dagger\partial^\mu\phi
-V(\phi^\dagger\phi).
$$

It is invariant under

$$
\phi\mapsto e^{-i\alpha}\phi,
\qquad
\phi^\dagger\mapsto e^{i\alpha}\phi^\dagger.
$$

For infinitesimal $\alpha$,

$$
\delta\phi=-i\alpha\phi,
\qquad
\delta\phi^\dagger=i\alpha\phi^\dagger.
$$

Treating $\phi$ and $\phi^\dagger$ independently,

$$
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}=\partial^\mu\phi^\dagger,
\qquad
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^\dagger)}=\partial^\mu\phi.
$$

With $B^\mu=0$, the current is

$$
\boxed{
j^\mu=i\phi^\dagger\overleftrightarrow{\partial^\mu}\phi
=i\left(\phi^\dagger\partial^\mu\phi-(\partial^\mu\phi^\dagger)\phi\right).
}
$$

Changing the sign convention for the phase rotation flips the current. That is not a contradiction; it only changes which sign of charge is called positive.

## Example: O(N) scalar symmetry

For $N$ real scalar fields,

$$
\mathcal L
=\frac12\partial_\mu\phi^a\partial^\mu\phi^a
-V(\phi^a\phi^a),
\qquad a=1,\ldots,N,
$$

the theory is invariant under constant $O(N)$ rotations. For an infinitesimal rotation in the $(a,b)$ plane,

$$
\delta\phi^a=\epsilon\phi^b,
\qquad
\delta\phi^b=-\epsilon\phi^a.
$$

The current is

$$
\boxed{
j_{ab}^\mu
=\phi^b\partial^\mu\phi^a-\phi^a\partial^\mu\phi^b,
\qquad
j_{ab}^\mu=-j_{ba}^\mu.
}
$$

There are $N(N-1)/2$ independent currents. For $N=2$, this is the same symmetry as the phase rotation of a complex scalar, written in real variables.

## Spacetime translations and the stress tensor

Noether's theorem also applies to spacetime transformations. For active translations,

$$
\delta_a\phi^A=a^\nu\partial_\nu\phi^A,
$$

the Lagrangian density changes by

$$
\delta_a\mathcal L=a^\nu\partial_\nu\mathcal L
=\partial_\mu(a^\nu\delta^\mu{}_{\nu}\mathcal L).
$$

The associated current is $a^\nu T^\mu{}_{\nu}$, with

$$
\boxed{
T^\mu{}_{\nu}
=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}\partial_\nu\phi^A
-\delta^\mu{}_{\nu}\mathcal L.
}
$$

This is the canonical stress tensor. It is developed in detail on [Stress Tensor](/foundations/classical-field-theory/stress-tensor/), because it has several legitimate representatives and many subtleties.

## Charges as generators

In Hamiltonian field theory, charges generate transformations. When the transformation has no time derivatives in $\Delta^A$ and $B^0=0$,

$$
Q=\int d^3\mathbf x\,\pi_A\Delta^A,
\qquad
\pi_A=\frac{\partial\mathcal L}{\partial\dot\phi^A}.
$$

Using the equal-time Poisson bracket,

$$
\{\phi^A(t,\mathbf x),\pi_B(t,\mathbf y)\}
=\delta^A{}_B\delta^{(3)}(\mathbf x-\mathbf y),
$$

one finds

$$
\{\phi^A,Q\}=\Delta^A.
$$

After quantization, the corresponding operator $\widehat Q$ acts as the generator of the symmetry on field operators and states, up to the usual convention-dependent factors of $i$.

## Ward identity preview

In QFT, a conserved current constrains correlation functions. Schematically,

$$
\partial_\mu
\langle T\{j^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\}\rangle
$$

is not simply zero. It contains contact terms when $x$ reaches one of the insertions. These contact terms encode how the operators transform.

That is the Ward identity version of Noether's theorem.

Quantum anomalies are serious because they replace the classical statement with something like

$$
\partial_\mu j^\mu=\mathcal A
$$

inside correlation functions. The advanced home for that subject is [Symmetry, Anomalies, and Topology](/symmetry-anomalies-topology/).

## Current non-uniqueness

Noether currents are not unique. If $K^{\mu\nu}=-K^{\nu\mu}$, then

$$
j'^\mu=j^\mu+\partial_\nu K^{\mu\nu}
$$

has the same divergence as $j^\mu$, because

$$
\partial_\mu\partial_\nu K^{\mu\nu}=0.
$$

The charges agree when the resulting surface term vanishes:

$$
Q'-Q=\int d^3\mathbf x\,\partial_iK^{0i}.
$$

This ambiguity is not a flaw. It explains stress-tensor improvements, conformal improvements, and the recurring role of boundary conditions.

## Global symmetry versus gauge redundancy

A global symmetry relates physically distinct configurations or states. A gauge transformation usually relates different descriptions of the same physical configuration.

A useful first-pass slogan is

$$
\text{global symmetry}\Rightarrow\text{Noether current},
\qquad
\text{gauge redundancy}\Rightarrow\text{constraint, identity, possible boundary charge}.
$$

The slogan is not the full theorem. Gauge theory requires Noether's second theorem, constraints, gauge fixing, and boundary conditions. But it prevents the most common conceptual mistake: treating every gauge parameter as if it produced an ordinary conserved charge.

## Common pitfalls

**Treating conservation as off shell.** The Noether current obeys $\partial_\mu j^\mu=-E_A\Delta^A$, so it is generally conserved only on shell.

**Forgetting $B^\mu$.** If $\delta\mathcal L=\partial_\mu B^\mu$, then the current is $j^\mu=\Pi_A^\mu\Delta^A-B^\mu$.

**Confusing the local-parameter trick with gauge symmetry.** Letting $\epsilon\to\epsilon(x)$ is a way to find currents. It does not mean the theory is gauge invariant.

**Ignoring boundary conditions.** Local conservation gives a conserved total charge only if boundary flux vanishes or is included.

**Assuming classical symmetries survive quantization.** Regularization and the path-integral measure may break a classical symmetry, producing an anomaly.

## Relation to nearby pages

- [Fields, Actions, and Equations](/foundations/classical-field-theory/fields-actions-equations/) derives the variational identity used here.
- [Scalar Fields](/foundations/classical-field-theory/scalar-fields/) supplies the scalar examples.
- [Stress Tensor](/foundations/classical-field-theory/stress-tensor/) develops spacetime-translation currents.
- [Hamiltonian Field Theory](/foundations/classical-field-theory/hamiltonian-field-theory/) explains charges as phase-space generators.
- [Constraints](/foundations/classical-field-theory/constraints/) explains why gauge redundancy is not an ordinary global symmetry.
- [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) turns current conservation into correlation-function identities.

## Exercises

### Exercise 1: Derive the current formula

Starting from

$$
\delta\mathcal L=E_A\delta\phi^A+\partial_\mu(\Pi_A^\mu\delta\phi^A),
$$

show that $\delta\phi^A=\epsilon\Delta^A$ and $\delta\mathcal L=\epsilon\partial_\mu B^\mu$ imply $j^\mu=\Pi_A^\mu\Delta^A-B^\mu$ is conserved on shell.

<details>
<summary><strong>Solution</strong></summary>

Substitute the symmetry variation and cancel $\epsilon$:

$$
\partial_\mu B^\mu=E_A\Delta^A+\partial_\mu(\Pi_A^\mu\Delta^A).
$$

Rearrange to get

$$
\partial_\mu(\Pi_A^\mu\Delta^A-B^\mu)=-E_A\Delta^A.
$$

On shell, $E_A=0$.

</details>

### Exercise 2: Shift symmetry breaking

For $\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi-V(\phi)$, compute $\partial_\mu j^\mu$ for $j^\mu=\partial^\mu\phi$. When is it conserved?

<details>
<summary><strong>Solution</strong></summary>

The divergence is $\Box\phi$. On shell, $\Box\phi=-V'(\phi)$, so the current is conserved only when $V$ is constant.

</details>

### Exercise 3: Current improvement

Show that if $K^{\mu\nu}=-K^{\nu\mu}$, then $j'^\mu=j^\mu+\partial_\nu K^{\mu\nu}$ has the same divergence as $j^\mu$.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
\partial_\mu j'^\mu=\partial_\mu j^\mu+\partial_\mu\partial_\nu K^{\mu\nu}.
$$

The second term vanishes because the derivative pair is symmetric in $\mu,\nu$ while $K^{\mu\nu}$ is antisymmetric.

</details>

## References

- E. Noether, “Invariante Variationsprobleme,” *Nachrichten von der Gesellschaft der Wissenschaften zu Göttingen* (1918).
- M. Srednicki, *Quantum Field Theory*, §22.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§7.3–7.4.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 5–6.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed., Part I.10.

## Version history

- **2026-06-08:** Revised for cleaner theorem flow, stronger global/gauge distinction, less repetition with scalar and stress-tensor pages, and clearer reader-facing warnings.
- **2026-05-22:** Initial qft.org page.
