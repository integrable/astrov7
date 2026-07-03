---
title: "Complex Scalar Field"
description: "Canonical quantization of the free complex scalar field: two oscillator species, particles and antiparticles, conserved U(1) charge, and the charge-counting Hamiltonian."
sidebar:
  label: "Complex Scalar Field"
  order: 4
---

## Summary

A complex scalar field is the charged version of the scalar field. Classically,

$$
\mathcal L
=\partial_\mu\Phi^\dagger\,\partial^\mu\Phi
-m^2\Phi^\dagger\Phi.
$$

Treat $\Phi$ and $\Phi^\dagger$ as independent variables when taking canonical derivatives. Their conjugate momenta are

$$
\Pi_\Phi=\dot\Phi^\dagger,
\qquad
\Pi_{\Phi^\dagger}=\dot\Phi.
$$

Canonical quantization imposes

$$
[\Phi(t,\mathbf x),\Pi_\Phi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y),
\qquad
[\Phi^\dagger(t,\mathbf x),\Pi_{\Phi^\dagger}(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y),
$$

with the other elementary equal-time commutators zero.

The free field expansion is

$$
\boxed{
\Phi(x)=\int d\mu(p)
\left[a(\mathbf p)e^{-ip\cdot x}+b^\dagger(\mathbf p)e^{ip\cdot x}\right],
}
$$

and

$$
\boxed{
\Phi^\dagger(x)=\int d\mu(p)
\left[a^\dagger(\mathbf p)e^{ip\cdot x}+b(\mathbf p)e^{-ip\cdot x}\right].
}
$$

The two independent oscillator species obey

$$
[a(\mathbf p),a^\dagger(\mathbf p')]
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p'),
$$

$$
[b(\mathbf p),b^\dagger(\mathbf p')]
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p'),
$$

with all mixed commutators zero. After normal ordering,

$$
\boxed{
:H:=\int d\mu(p)\,E_{\mathbf p}
\left[a^\dagger(\mathbf p)a(\mathbf p)+b^\dagger(\mathbf p)b(\mathbf p)\right].
}
$$

For the phase convention

$$
\Phi\mapsto e^{-iq\alpha}\Phi,
\qquad
\Phi^\dagger\mapsto e^{iq\alpha}\Phi^\dagger,
$$

the conserved charge is

$$
\boxed{
Q=q\int d\mu(p)
\left[a^\dagger(\mathbf p)a(\mathbf p)-b^\dagger(\mathbf p)b(\mathbf p)\right].
}
$$

So $a^\dagger$ creates particles of charge $+q$, while $b^\dagger$ creates antiparticles of charge $-q$. Zee presents this as the cleanest canonical explanation of why a non-Hermitian scalar field needs two oscillator species; Weinberg derives the need for a particle-antiparticle pair from causal scalar fields; Coleman diagonalizes the same charge-counting structure in his charged-scalar discussion (Zee 2010, ch. I.8; Weinberg 1995, Vol. I, §5.2; Coleman 2019, ch. 6).

## Prerequisites

You should know [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/), [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/), [Bosons and Fermions](/foundations/relativistic-particles-and-fields/bosons-and-fermions/), and [Canonical Commutation Relations](/foundations/canonical-quantization/canonical-commutation-relations/). We use the conventions of [Conventions and Normalizations](/foundations/conventions-and-normalizations/): mostly-minus metric, $p\cdot x=p^0t-\mathbf p\cdot\mathbf x$, and covariant on-shell measure $d\mu(p)=d^3\mathbf p/[(2\pi)^3 2E_{\mathbf p}]$.

## Core idea

A real scalar field has one oscillator species. A complex scalar field has two. One species creates and annihilates particles; the other creates and annihilates antiparticles. Both have the same positive energy. Their difference is charge, not energy sign.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Complex scalar field particle and antiparticle sectors](/figures/foundations/complex-scalar-charge-sectors.svg)

<figcaption>

The complex scalar field $\Phi$ contains a particle-annihilation term and an antiparticle-creation term. Its adjoint $\Phi^\dagger$ contains the conjugate operations. The Hamiltonian counts both sectors with positive energy, while the conserved $U(1)$ charge counts them with opposite signs.

</figcaption>
</figure>

This is the canonical place where the phrase “antiparticle” becomes algebra rather than metaphor. There are not negative-energy physical states. There are two positive-energy oscillator sectors with opposite additive charges.

:::note[Assumptions]
This page treats the free complex scalar field with a global $U(1)$ symmetry. Gauge interactions are not included yet. If the $U(1)$ symmetry is later gauged, the ordinary derivative becomes a covariant derivative and the current receives gauge-field-dependent terms.
:::

## Complex field as two real fields

A complex scalar is equivalent to two real scalar fields:

$$
\Phi=\frac{1}{\sqrt2}(\phi_1+i\phi_2),
\qquad
\Phi^\dagger=\frac{1}{\sqrt2}(\phi_1-i\phi_2).
$$

Then

$$
\partial_\mu\Phi^\dagger\partial^\mu\Phi
=\frac12\partial_\mu\phi_1\partial^\mu\phi_1
+\frac12\partial_\mu\phi_2\partial^\mu\phi_2,
$$

and

$$
\Phi^\dagger\Phi=\frac12(\phi_1^2+\phi_2^2).
$$

Thus

$$
\mathcal L
=\frac12\partial_\mu\phi_1\partial^\mu\phi_1
+\frac12\partial_\mu\phi_2\partial^\mu\phi_2
-\frac12m^2(\phi_1^2+\phi_2^2).
$$

The equality of the two masses matters. The global $U(1)$ symmetry is the rotation symmetry in the internal $(\phi_1,\phi_2)$ plane.

In complex notation, this symmetry is

$$
\Phi\mapsto e^{-iq\alpha}\Phi,
\qquad
\Phi^\dagger\mapsto e^{iq\alpha}\Phi^\dagger.
$$

The parameter $q$ fixes the charge unit assigned to the field. Many textbooks set $q=1$ until the field is coupled to electromagnetism.

## Canonical variables

With mostly-minus metric,

$$
\mathcal L
=\dot\Phi^\dagger\dot\Phi
-\nabla\Phi^\dagger\cdot\nabla\Phi
-m^2\Phi^\dagger\Phi.
$$

Treating $\Phi$ and $\Phi^\dagger$ as independent canonical variables gives

$$
\Pi_\Phi
=\frac{\partial\mathcal L}{\partial\dot\Phi}
=\dot\Phi^\dagger,
$$

and

$$
\Pi_{\Phi^\dagger}
=\frac{\partial\mathcal L}{\partial\dot\Phi^\dagger}
=\dot\Phi.
$$

The nonzero equal-time commutators are

$$
[\Phi(t,\mathbf x),\Pi_\Phi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y),
$$

and

$$
[\Phi^\dagger(t,\mathbf x),\Pi_{\Phi^\dagger}(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

Equivalently,

$$
[\Phi(t,\mathbf x),\dot\Phi^\dagger(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y),
$$

and

$$
[\Phi^\dagger(t,\mathbf x),\dot\Phi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

All other elementary equal-time commutators vanish.

The Hamiltonian density is

$$
\mathcal H
=\Pi_\Phi\dot\Phi+\Pi_{\Phi^\dagger}\dot\Phi^\dagger-\mathcal L
=\dot\Phi^\dagger\dot\Phi+\nabla\Phi^\dagger\cdot\nabla\Phi+m^2\Phi^\dagger\Phi.
$$

Equivalently,

$$
\mathcal H
=\Pi_\Phi\Pi_{\Phi^\dagger}
+\nabla\Phi^\dagger\cdot\nabla\Phi
+m^2\Phi^\dagger\Phi.
$$

As a check, in real-field variables this is just the sum of two positive scalar Hamiltonian densities:

$$
\mathcal H
=\frac12\pi_1^2+\frac12(\nabla\phi_1)^2+\frac12m^2\phi_1^2
+\frac12\pi_2^2+\frac12(\nabla\phi_2)^2+\frac12m^2\phi_2^2.
$$

## Mode expansion

The complex field is not Hermitian, so its creation part is not fixed to be the adjoint of its annihilation part inside the same field. The correct free expansion uses two independent oscillator species:

$$
\Phi(x)=\int d\mu(p)
\left[a(\mathbf p)e^{-ip\cdot x}+b^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

and

$$
\Phi^\dagger(x)=\int d\mu(p)
\left[a^\dagger(\mathbf p)e^{ip\cdot x}+b(\mathbf p)e^{-ip\cdot x}\right].
$$

The oscillator algebra is

$$
[a(\mathbf p),a^\dagger(\mathbf p')]
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p'),
$$

$$
[b(\mathbf p),b^\dagger(\mathbf p')]
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p'),
$$

with

$$
[a,b]=[a,b^\dagger]=[a^\dagger,b]=[a^\dagger,b^\dagger]=0.
$$

The conjugate momenta are

$$
\Pi_\Phi(x)=\dot\Phi^\dagger(x)
=\int d\mu(p)
\left[iE_{\mathbf p}a^\dagger(\mathbf p)e^{ip\cdot x}
-iE_{\mathbf p}b(\mathbf p)e^{-ip\cdot x}\right],
$$

and

$$
\Pi_{\Phi^\dagger}(x)=\dot\Phi(x)
=\int d\mu(p)
\left[-iE_{\mathbf p}a(\mathbf p)e^{-ip\cdot x}
+iE_{\mathbf p}b^\dagger(\mathbf p)e^{ip\cdot x}\right].
$$

Using these expansions, one finds

$$
[\Phi(t,\mathbf x),\dot\Phi^\dagger(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y),
$$

and

$$
[\Phi^\dagger(t,\mathbf x),\dot\Phi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

The mixed commutators vanish because the $a$ and $b$ oscillator sectors commute.

## Hamiltonian and momentum

Substituting the mode expansion into the Hamiltonian gives, before normal ordering,

$$
H=\int d\mu(p)\,E_{\mathbf p}
\left[
a^\dagger(\mathbf p)a(\mathbf p)+b^\dagger(\mathbf p)b(\mathbf p)
\right]+E_0^{\mathbb C}.
$$

The complex scalar has twice the real-scalar zero-point energy because it is two real scalar fields:

$$
E_0^{\mathbb C}
=2E_0^{\mathbb R}.
$$

After normal ordering,

$$
\boxed{
:H:=\int d\mu(p)\,E_{\mathbf p}
\left[
a^\dagger(\mathbf p)a(\mathbf p)+b^\dagger(\mathbf p)b(\mathbf p)
\right].
}
$$

The momentum operator is

$$
\boxed{
\mathbf P=\int d\mu(p)\,\mathbf p
\left[
a^\dagger(\mathbf p)a(\mathbf p)+b^\dagger(\mathbf p)b(\mathbf p)
\right].
}
$$

Thus

$$
[:H:,a^\dagger(\mathbf p)]=E_{\mathbf p}a^\dagger(\mathbf p),
\qquad
[:H:,b^\dagger(\mathbf p)]=E_{\mathbf p}b^\dagger(\mathbf p).
$$

Both particle and antiparticle states have positive energy. Likewise,

$$
[\mathbf P,a^\dagger(\mathbf p)]=\mathbf p\,a^\dagger(\mathbf p),
\qquad
[\mathbf P,b^\dagger(\mathbf p)]=\mathbf p\,b^\dagger(\mathbf p).
$$

The antiparticle created by $b^\dagger(\mathbf p)$ has momentum $\mathbf p$, not $-\mathbf p$. The sign in $e^{ip\cdot x}$ is part of the field expansion; the label $\mathbf p$ on $b^\dagger(\mathbf p)$ is the physical momentum of the state it creates.

## U(1) current and charge

The global symmetry

$$
\Phi\mapsto e^{-iq\alpha}\Phi,
\qquad
\Phi^\dagger\mapsto e^{iq\alpha}\Phi^\dagger
$$

has infinitesimal form

$$
\delta\Phi=-iq\alpha\Phi,
\qquad
\delta\Phi^\dagger=iq\alpha\Phi^\dagger.
$$

The Noether current is

$$
\boxed{
j^\mu=iq\,\Phi^\dagger\overleftrightarrow{\partial^\mu}\Phi
=iq\left(\Phi^\dagger\partial^\mu\Phi
-(\partial^\mu\Phi^\dagger)\Phi\right).
}
$$

Using the equations of motion,

$$
(\Box+m^2)\Phi=0,
\qquad
(\Box+m^2)\Phi^\dagger=0,
$$

one finds

$$
\partial_\mu j^\mu=0.
$$

The conserved charge is

$$
Q=\int d^3\mathbf x\,j^0.
$$

Substituting the mode expansion and normal ordering gives

$$
\boxed{
Q=q\int d\mu(p)
\left[
a^\dagger(\mathbf p)a(\mathbf p)-b^\dagger(\mathbf p)b(\mathbf p)
\right].
}
$$

The charge operator generates the field transformation:

$$
[Q,\Phi(x)]=-q\Phi(x),
\qquad
[Q,\Phi^\dagger(x)]=+q\Phi^\dagger(x).
$$

If one uses the convention $\delta\mathcal O=i\alpha[Q,\mathcal O]$, this is exactly the infinitesimal transformation $\delta\Phi=-iq\alpha\Phi$.

## Particle and antiparticle states

Define the vacuum by

$$
a(\mathbf p)|0\rangle=0,
\qquad
b(\mathbf p)|0\rangle=0.
$$

The one-particle and one-antiparticle states are

$$
|\mathbf p,+\rangle=a^\dagger(\mathbf p)|0\rangle,
\qquad
|\mathbf p,-\rangle=b^\dagger(\mathbf p)|0\rangle.
$$

Their energies are the same:

$$
:H:|\mathbf p,+\rangle=E_{\mathbf p}|\mathbf p,+\rangle,
\qquad
:H:|\mathbf p,-\rangle=E_{\mathbf p}|\mathbf p,-\rangle.
$$

Their charges are opposite:

$$
Q|\mathbf p,+\rangle=+q|\mathbf p,+\rangle,
\qquad
Q|\mathbf p,-\rangle=-q|\mathbf p,-\rangle.
$$

This is the clean Hilbert-space meaning of antiparticle for a complex scalar field.

The multiparticle basis is built by acting with both kinds of creation operator:

$$
\prod_i a^\dagger(\mathbf p_i)
\prod_j b^\dagger(\mathbf k_j)
|0\rangle.
$$

The total charge is

$$
Q=q(N_a-N_b),
$$

where $N_a$ counts $a$-quanta and $N_b$ counts $b$-quanta.

## Charge conjugation preview

A charge-conjugation operation, when it is a symmetry of the dynamics, exchanges particle and antiparticle oscillators:

$$
C\,a(\mathbf p)\,C^{-1}=b(\mathbf p),
\qquad
C\,b(\mathbf p)\,C^{-1}=a(\mathbf p).
$$

It also exchanges the fields:

$$
C\,\Phi(x)\,C^{-1}=\Phi^\dagger(x),
\qquad
C\,\Phi^\dagger(x)\,C^{-1}=\Phi(x).
$$

Under this operation,

$$
CQC^{-1}=-Q.
$$

But be careful: the existence of antiparticles does not require charge conjugation to be an exact symmetry. It requires the conjugate charge sector. A theory may contain antiparticles even if its interactions violate $C$.

## Real scalar as a special case

The real scalar field is recovered by imposing a reality condition. Schematically,

$$
\Phi=\Phi^\dagger.
$$

In oscillator language this identifies the antiparticle sector with the particle sector:

$$
b(\mathbf p)=a(\mathbf p).
$$

Then the field becomes

$$
\phi(x)=\int d\mu(p)
\left[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}\right].
$$

There is no independent charge-counting operator of the form $N_a-N_b$ because the two sectors have collapsed into one. A real scalar quantum is neutral and self-conjugate.

The converse is subtler: a neutral particle need not be identical to its antiparticle in every possible theory. But for the single real scalar field, self-conjugacy is built in by $\phi=\phi^\dagger$.

## Commutators and propagators

For the complex scalar field,

$$
[\Phi(x),\Phi(y)]=0,
\qquad
[\Phi^\dagger(x),\Phi^\dagger(y)]=0.
$$

The nontrivial commutator is

$$
[\Phi(x),\Phi^\dagger(y)]=i\Delta(x-y),
$$

with the same Pauli–Jordan function as for the real scalar field:

$$
i\Delta(x-y)
=\int d\mu(p)\left[
e^{-ip\cdot(x-y)}-e^{ip\cdot(x-y)}
\right].
$$

At spacelike separation,

$$
[\Phi(x),\Phi^\dagger(y)]=0,
\qquad
(x-y)^2<0.
$$

The vacuum two-point function is

$$
\langle0|\Phi(x)\Phi^\dagger(y)|0\rangle
=\int d\mu(p)\,e^{-ip\cdot(x-y)}.
$$

The opposite ordering gives

$$
\langle0|\Phi^\dagger(y)\Phi(x)|0\rangle
=\int d\mu(p)\,e^{ip\cdot(x-y)}.
$$

The time-ordered propagator is

$$
D_F(x-y)
=\langle0|T\Phi(x)\Phi^\dagger(y)|0\rangle
=\int\frac{d^4p}{(2\pi)^4}
\frac{i}{p^2-m^2+i\epsilon}e^{-ip\cdot(x-y)}.
$$

There is no nonzero free propagator $\langle0|T\Phi(x)\Phi(y)|0\rangle$ for a complex scalar field with conserved charge. Charge conservation forbids it.

## Common pitfalls

### Treating Φ and Φ† as one canonical variable

During variation and canonical quantization, treat $\Phi$ and $\Phi^\dagger$ as independent variables. Their conjugate momenta are crossed:

$$
\Pi_\Phi=\dot\Phi^\dagger,
\qquad
\Pi_{\Phi^\dagger}=\dot\Phi.
$$

Forgetting this is the fastest way to get the wrong sign or a missing factor of two.

### Using only one oscillator species

A non-Hermitian scalar field needs two oscillator species. If you try to quantize it with only $a$ and $a^\dagger$, you either secretly impose a reality condition or fail to represent an independent charged antiparticle sector.

### Calling b† a negative-energy operator

The operator $b^\dagger(\mathbf p)$ creates a positive-energy antiparticle. Its energy is $E_{\mathbf p}$, and its momentum is $\mathbf p$. The minus sign appears in the charge operator, not in the Hamiltonian.

### Confusing antiparticles with charge conjugation symmetry

Antiparticles are states. Charge conjugation is a possible symmetry operation. A theory can have antiparticles even when $C$ is not an exact symmetry.

### Forgetting charge arrows

In perturbation theory, complex scalar lines carry an orientation associated with charge flow. A real scalar line has no such arrow. This difference becomes important as soon as interactions are introduced.

## Relation to other topics

- [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/) gives the conceptual particle-antiparticle story before the canonical derivation.
- [Normal Ordering](/foundations/canonical-quantization/normal-ordering/) will explain the vacuum-energy subtraction and normal-ordered charge operators.
- [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/) will develop the Pauli–Jordan function and causal support.
- [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/) will treat real and complex scalar fields as free relativistic fields in reference form.
- [Scalar QED](/foundations/foundational-models/scalar-qed/) will gauge the $U(1)$ symmetry and introduce covariant derivatives.
- [Internal Symmetries](/foundations/symmetry-and-spacetime/internal-symmetries/) will generalize the $U(1)$ charge to non-Abelian multiplets.

## Exercises

### Exercise 1: Derive the conjugate momenta

Starting from

$$
\mathcal L
=\dot\Phi^\dagger\dot\Phi
-\nabla\Phi^\dagger\cdot\nabla\Phi
-m^2\Phi^\dagger\Phi,
$$

treat $\Phi$ and $\Phi^\dagger$ as independent variables and show that

$$
\Pi_\Phi=\dot\Phi^\dagger,
\qquad
\Pi_{\Phi^\dagger}=\dot\Phi.
$$

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
\Pi_\Phi=\frac{\partial\mathcal L}{\partial\dot\Phi}.
$$

Only $\dot\Phi^\dagger\dot\Phi$ depends on $\dot\Phi$, so

$$
\Pi_\Phi=\dot\Phi^\dagger.
$$

Similarly,

$$
\Pi_{\Phi^\dagger}
=\frac{\partial\mathcal L}{\partial\dot\Phi^\dagger}
=\dot\Phi.
$$

</details>

### Exercise 2: Check a canonical commutator

Using the mode expansions, show that

$$
[\Phi(t,\mathbf x),\dot\Phi^\dagger(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

<details>
<summary><strong>Solution</strong></summary>

At equal time,

$$
\Phi(t,\mathbf x)=\int d\mu(p)
\left[a(\mathbf p)e^{-iE_{\mathbf p}t+i\mathbf p\cdot\mathbf x}
+b^\dagger(\mathbf p)e^{iE_{\mathbf p}t-i\mathbf p\cdot\mathbf x}\right],
$$

and

$$
\dot\Phi^\dagger(t,\mathbf y)=\int d\mu(p)
\left[iE_{\mathbf p}a^\dagger(\mathbf p)e^{iE_{\mathbf p}t-i\mathbf p\cdot\mathbf y}
-iE_{\mathbf p}b(\mathbf p)e^{-iE_{\mathbf p}t+i\mathbf p\cdot\mathbf y}\right].
$$

The $a$ sector contributes

$$
\frac{i}{2}\int\frac{d^3\mathbf p}{(2\pi)^3}
e^{i\mathbf p\cdot(\mathbf x-\mathbf y)}.
$$

The $b$ sector contributes

$$
\frac{i}{2}\int\frac{d^3\mathbf p}{(2\pi)^3}
e^{-i\mathbf p\cdot(\mathbf x-\mathbf y)}.
$$

Adding both terms gives

$$
[\Phi(t,\mathbf x),\dot\Phi^\dagger(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

</details>

### Exercise 3: Positive energy of particles and antiparticles

Use

$$
:H:=\int d\mu(p)\,E_{\mathbf p}
\left[a^\dagger(\mathbf p)a(\mathbf p)+b^\dagger(\mathbf p)b(\mathbf p)\right]
$$

to show that both $a^\dagger(\mathbf q)|0\rangle$ and $b^\dagger(\mathbf q)|0\rangle$ have energy $E_{\mathbf q}$.

<details>
<summary><strong>Solution</strong></summary>

The oscillator algebra gives

$$
[:H:,a^\dagger(\mathbf q)]
=E_{\mathbf q}a^\dagger(\mathbf q),
$$

and

$$
[:H:,b^\dagger(\mathbf q)]
=E_{\mathbf q}b^\dagger(\mathbf q).
$$

Since the normal-ordered Hamiltonian annihilates the vacuum,

$$
:H:a^\dagger(\mathbf q)|0\rangle
=E_{\mathbf q}a^\dagger(\mathbf q)|0\rangle,
$$

and

$$
:H:b^\dagger(\mathbf q)|0\rangle
=E_{\mathbf q}b^\dagger(\mathbf q)|0\rangle.
$$

Both states have positive energy.

</details>

### Exercise 4: Current conservation

Show that

$$
j^\mu=iq\left(\Phi^\dagger\partial^\mu\Phi
-(\partial^\mu\Phi^\dagger)\Phi\right)
$$

is conserved when $\Phi$ and $\Phi^\dagger$ obey the free Klein–Gordon equation.

<details>
<summary><strong>Solution</strong></summary>

Take the divergence:

$$
\begin{aligned}
\partial_\mu j^\mu
&=iq\left[
(\partial_\mu\Phi^\dagger)(\partial^\mu\Phi)
+\Phi^\dagger\Box\Phi
-(\Box\Phi^\dagger)\Phi
-(\partial_\mu\Phi^\dagger)(\partial^\mu\Phi)
\right] \\
&=iq\left[\Phi^\dagger\Box\Phi-(\Box\Phi^\dagger)\Phi\right].
\end{aligned}
$$

Using

$$
\Box\Phi=-m^2\Phi,
\qquad
\Box\Phi^\dagger=-m^2\Phi^\dagger,
$$

we get

$$
\partial_\mu j^\mu
=iq\left[-m^2\Phi^\dagger\Phi+m^2\Phi^\dagger\Phi\right]=0.
$$

</details>

### Exercise 5: Charge of one-particle states

Given

$$
Q=q\int d\mu(p)
\left[a^\dagger(\mathbf p)a(\mathbf p)-b^\dagger(\mathbf p)b(\mathbf p)\right],
$$

show that $a^\dagger(\mathbf q)|0\rangle$ has charge $+q$ and $b^\dagger(\mathbf q)|0\rangle$ has charge $-q$.

<details>
<summary><strong>Solution</strong></summary>

The commutators are

$$
[Q,a^\dagger(\mathbf q)]=q\,a^\dagger(\mathbf q),
$$

and

$$
[Q,b^\dagger(\mathbf q)]=-q\,b^\dagger(\mathbf q).
$$

With $Q|0\rangle=0$,

$$
Q a^\dagger(\mathbf q)|0\rangle
=q\,a^\dagger(\mathbf q)|0\rangle,
$$

and

$$
Q b^\dagger(\mathbf q)|0\rangle
=-q\,b^\dagger(\mathbf q)|0\rangle.
$$

</details>

### Exercise 6: Charge conjugation flips the charge

Assume a charge-conjugation operator acts as

$$
C a(\mathbf p) C^{-1}=b(\mathbf p),
\qquad
C b(\mathbf p) C^{-1}=a(\mathbf p),
$$

and similarly for the adjoints. Show that

$$
CQC^{-1}=-Q.
$$

<details>
<summary><strong>Solution</strong></summary>

Act on the charge operator:

$$
\begin{aligned}
CQC^{-1}
&=q\int d\mu(p)
\left[
C a^\dagger a C^{-1}
-
C b^\dagger b C^{-1}
\right] \\
&=q\int d\mu(p)
\left[
b^\dagger b-a^\dagger a
\right] \\
&=-q\int d\mu(p)
\left[
a^\dagger a-b^\dagger b
\right] \\
&=-Q.
\end{aligned}
$$

Thus charge conjugation reverses the sign of the conserved charge.

</details>

## References

### Primary references

- W. Pauli and V. Weisskopf, “Über die Quantisierung der skalaren relativistischen Wellengleichung,” *Helvetica Physica Acta* **7** (1934), for the field quantization of the scalar relativistic wave equation and the charged scalar interpretation.
- P. A. M. Dirac, “A Theory of Electrons and Protons,” *Proceedings of the Royal Society A* **126** (1930), for the historical route from negative-energy solutions to antiparticles.
- E. C. G. Stückelberg, “La signification du temps propre en mécanique ondulatoire,” *Helvetica Physica Acta* **14** (1941), for an early reinterpretation of antiparticle propagation.

### Standard textbook treatments

- A. Zee, *Quantum Field Theory in a Nutshell*, ch. I.8, for the canonical complex scalar expansion and the charge $Q=\int(a^\dagger a-b^\dagger b)$.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 6, for charged scalar fields, charge conjugation, and charge-counting operators.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.2 and 7.1, for causal scalar fields, antiparticles, and complex canonical variables.
- M. Srednicki, *Quantum Field Theory*, §§22 and 61, for complex-scalar Noether currents, global $U(1)$ symmetry, and scalar electrodynamics.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§2.2–2.4, for the standard particle-antiparticle interpretation of complex scalar quantization.

### For a first pass

- Zee, ch. I.8.
- Peskin and Schroeder, §2.2.
- Coleman, ch. 6.

### For mathematical precision

- Weinberg, Vol. I, chs. 5 and 7.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for the structural relation between locality, charge conjugation, and antiparticles in relativistic QFT.

## Version history

- **2026-05-22:** Initial qft.org page on canonical quantization of the free complex scalar field, two oscillator species, conserved $U(1)$ charge, particles and antiparticles, charge conjugation preview, propagators, pitfalls, and exercises.
