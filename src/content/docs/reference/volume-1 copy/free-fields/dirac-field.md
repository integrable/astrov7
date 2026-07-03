---
title: "Dirac Field"
description: "The free spin-one-half relativistic field: Dirac equation, gamma matrices, plane-wave spinors, canonical anticommutators, particle-antiparticle modes, spin sums, current, and propagator."
sidebar:
  label: "Dirac Field"
  order: 2
---

## Summary

The Dirac field is the free relativistic field of spin one half. It is a spinor-valued quantum field whose Lagrangian is first order in derivatives:

$$
\boxed{
\mathcal L=\overline\psi(i\gamma^\mu\partial_\mu-m)\psi,
\qquad
\overline\psi=\psi^\dagger\gamma^0.
}
$$

The field equation is

$$
\boxed{(i\gamma^\mu\partial_\mu-m)\psi=0.}
$$

The gamma matrices obey

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}\mathbf 1,
$$

with mostly-minus metric $\eta=(+,-,-,-)$. Since

$$
(i\gamma^\mu\partial_\mu+m)(i\gamma^\nu\partial_\nu-m)=-(\Box+m^2),
$$

each component of a free Dirac field also satisfies the Klein–Gordon equation.

For positive-energy on-shell momentum $p^0=E_{\mathbf p}$, the plane-wave spinors obey

$$
(p\!\!/-m)u_s(p)=0,
\qquad
(p\!\!/+m)v_s(p)=0,
$$

where $p\!\!\!/\equiv\gamma^\mu p_\mu$. The free field expansion is

$$
\boxed{
\psi(x)=\sum_s\int d\mu(p)
\left[
 b_s(\mathbf p)u_s(p)e^{-ip\cdot x}
 +d_s^\dagger(\mathbf p)v_s(p)e^{ip\cdot x}
\right].
}
$$

The nonzero anticommutators are

$$
\{b_s(\mathbf p),b_r^\dagger(\mathbf q)\}
=(2\pi)^3 2E_{\mathbf p}\delta_{sr}\delta^{(3)}(\mathbf p-\mathbf q),
$$

and

$$
\{d_s(\mathbf p),d_r^\dagger(\mathbf q)\}
=(2\pi)^3 2E_{\mathbf p}\delta_{sr}\delta^{(3)}(\mathbf p-\mathbf q).
$$

The standard spin sums are

$$
\boxed{
\sum_s u_s(p)\overline u_s(p)=p\!\!/+m,
\qquad
\sum_s v_s(p)\overline v_s(p)=p\!\!/-m.
}
$$

The Feynman propagator is

$$
\boxed{
S_F(x-y)=\langle0|T\psi(x)\overline\psi(y)|0\rangle
=\int\frac{d^4p}{(2\pi)^4}\,
\frac{i(p\!\!/+m)e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
}
$$

It satisfies

$$
(i\gamma^\mu\partial_\mu-m)S_F(x-y)=i\delta^{(4)}(x-y)\mathbf 1.
$$

Srednicki develops the Weyl and Dirac Lagrangians, canonical anticommutators, and free fermion propagator; Coleman gives a detailed construction of plane-wave Dirac spinors, canonical quantization, and the propagator; Weinberg derives the Dirac field as the causal spin-one-half field required by Lorentz invariance, locality, and the spin-statistics connection (Srednicki 2007, §§36–39 and 42; Coleman 2019, chs. 19–21; Weinberg 1995, Vol. I, §§5.5, 6.2, 7.1, and 14.1).

## Prerequisites

You should know [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/), [Bosons and Fermions](/foundations/relativistic-particles-and-fields/bosons-and-fermions/), [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/), [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), and [Conventions and Normalizations](/foundations/conventions-and-normalizations/). We use the default mostly-minus Clifford algebra, $p\cdot x=p^0t-\mathbf p\cdot\mathbf x$, and $d\mu(p)=d^3\mathbf p/[(2\pi)^3 2E_{\mathbf p}]$.

## Core idea

The Dirac field is not just “the square root of the Klein–Gordon equation.” That slogan captures one algebraic fact, but the real content is richer: a Dirac field carries a finite-dimensional Lorentz spinor index, has fermionic anticommutation relations, creates both particles and antiparticles, and packages spin sums into a simple numerator $p\!\!/+m$.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Dirac field map from Clifford algebra to Dirac operator, spinors, quantum field, and propagator](/figures/foundations/dirac-field-structure.svg)

<figcaption>

The Dirac field is built from the Clifford algebra and the first-order Dirac operator. Plane-wave spinors solve the on-shell equations, their completeness relations produce the numerator of the propagator, and fermionic creation operators generate particle and antiparticle sectors with positive energy.

</figcaption>
</figure>

This page collects the free Dirac field as a reference object. The next pages will unpack Weyl and Majorana special cases and the bilinears $\overline\psi\psi$, $\overline\psi\gamma^\mu\psi$, $\overline\psi\gamma^\mu\gamma^5\psi$, and so on.

:::note[Assumptions]
We work with a free massive Dirac field on flat Minkowski spacetime. The field is an operator-valued distribution. The spinor representation is kept representation-independent: no Dirac, Weyl, or Majorana matrix basis is assumed unless explicitly stated.
:::

## Gamma matrices and adjoints

Gamma matrices satisfy

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}\mathbf 1.
$$

With mostly-minus signature,

$$
(\gamma^0)^2=+1,
\qquad
(\gamma^i)^2=-1.
$$

We choose the Hermiticity convention

$$
(\gamma^0)^\dagger=\gamma^0,
\qquad
(\gamma^i)^\dagger=-\gamma^i.
$$

The Dirac adjoint is

$$
\overline\psi=\psi^\dagger\gamma^0.
$$

This adjoint is designed so that $\overline\psi\psi$ is a Lorentz scalar and $\overline\psi\gamma^\mu\psi$ is a Lorentz vector.

Slash notation means

$$
p\!\!/=\gamma^\mu p_\mu.
$$

With $p_\mu=(p^0,-\mathbf p)$ in mostly-minus convention,

$$
p\!\!/=\gamma^0p^0-\boldsymbol\gamma\cdot\mathbf p.
$$

## Dirac equation

The free Dirac Lagrangian is

$$
\mathcal L=\overline\psi(i\gamma^\mu\partial_\mu-m)\psi.
$$

Varying with respect to $\overline\psi$ gives

$$
(i\gamma^\mu\partial_\mu-m)\psi=0.
$$

Varying with respect to $\psi$ and integrating by parts gives the adjoint equation

$$
i(\partial_\mu\overline\psi)\gamma^\mu+m\overline\psi=0,
$$

or equivalently

$$
\overline\psi(i\overleftarrow{\partial}_\mu\gamma^\mu+m)=0.
$$

The Dirac operator implies the Klein–Gordon operator. Since the symmetric part of $\gamma^\mu\gamma^\nu$ is $\eta^{\mu\nu}$ and ordinary derivatives commute,

$$
(i\gamma^\mu\partial_\mu)^2
=-\gamma^\mu\gamma^\nu\partial_\mu\partial_\nu
=-\eta^{\mu\nu}\partial_\mu\partial_\nu
=-\Box.
$$

Therefore

$$
(i\gamma^\mu\partial_\mu+m)(i\gamma^\nu\partial_\nu-m)
=-(\Box+m^2).
$$

If $\psi$ solves the Dirac equation, then

$$
(\Box+m^2)\psi=0.
$$

This does not mean the Dirac field has spin zero. It means each component obeys the same relativistic dispersion relation. The spin information is in how the components transform under Lorentz transformations.

## Plane-wave spinors

Substitute a positive-frequency particle wave

$$
\psi(x)=u_s(p)e^{-ip\cdot x}
$$

into the Dirac equation. Then

$$
(i\gamma^\mu\partial_\mu-m)u_s(p)e^{-ip\cdot x}
=(p\!\!/-m)u_s(p)e^{-ip\cdot x},
$$

so

$$
\boxed{(p\!\!/-m)u_s(p)=0.}
$$

For the antiparticle creation part, use

$$
\psi(x)=v_s(p)e^{ip\cdot x}.
$$

Then

$$
i\gamma^\mu\partial_\mu e^{ip\cdot x}=-p\!\!/e^{ip\cdot x},
$$

so

$$
\boxed{(p\!\!/+m)v_s(p)=0.}
$$

The label $s$ runs over the two spin states for a massive spin-one-half particle. We use the normalization

$$
\overline u_r(p)u_s(p)=2m\delta_{rs},
\qquad
\overline v_r(p)v_s(p)=-2m\delta_{rs},
$$

and

$$
u_r^\dagger(p)u_s(p)=2E_{\mathbf p}\delta_{rs},
\qquad
v_r^\dagger(p)v_s(p)=2E_{\mathbf p}\delta_{rs}.
$$

The mixed orthogonality relations are

$$
\overline u_r(p)v_s(p)=0,
\qquad
\overline v_r(p)u_s(p)=0.
$$

With these conventions, the completeness relations are

$$
\boxed{
\sum_s u_s(p)\overline u_s(p)=p\!\!/+m,
}
$$

and

$$
\boxed{
\sum_s v_s(p)\overline v_s(p)=p\!\!/-m.
}
$$

These identities are the workhorses behind spin sums and the free Dirac propagator.

:::tip[Why the signs differ]
The $u$ spinors solve $(p\!\!/-m)u=0$, so their projector is proportional to $p\!\!/+m$. The $v$ spinors solve $(p\!\!/+m)v=0$, so their projector is proportional to $p\!\!/-m$. The signs are not optional; they are what make the propagator invert the Dirac operator.
:::

## Quantum field expansion

The free Dirac field is expanded as

$$
\psi(x)=\sum_s\int d\mu(p)
\left[
 b_s(\mathbf p)u_s(p)e^{-ip\cdot x}
 +d_s^\dagger(\mathbf p)v_s(p)e^{ip\cdot x}
\right].
$$

The adjoint field is

$$
\overline\psi(x)=\sum_s\int d\mu(p)
\left[
 b_s^\dagger(\mathbf p)\overline u_s(p)e^{ip\cdot x}
 +d_s(\mathbf p)\overline v_s(p)e^{-ip\cdot x}
\right].
$$

The nonzero anticommutators are

$$
\{b_s(\mathbf p),b_r^\dagger(\mathbf q)\}
=(2\pi)^3 2E_{\mathbf p}\delta_{sr}\delta^{(3)}(\mathbf p-\mathbf q),
$$

and

$$
\{d_s(\mathbf p),d_r^\dagger(\mathbf q)\}
=(2\pi)^3 2E_{\mathbf p}\delta_{sr}\delta^{(3)}(\mathbf p-\mathbf q),
$$

with all other elementary anticommutators zero.

Equivalently, at equal time,

$$
\boxed{
\{\psi_\alpha(t,\mathbf x),\psi_\beta^\dagger(t,\mathbf y)\}
=\delta_{\alpha\beta}\delta^{(3)}(\mathbf x-\mathbf y),
}
$$

with

$$
\{\psi_\alpha(t,\mathbf x),\psi_\beta(t,\mathbf y)\}=0,
\qquad
\{\psi_\alpha^\dagger(t,\mathbf x),\psi_\beta^\dagger(t,\mathbf y)\}=0.
$$

The particle interpretation is

$$
b_s^\dagger(\mathbf p)|0\rangle
=\text{one particle of momentum }\mathbf p\text{ and spin }s,
$$

and

$$
d_s^\dagger(\mathbf p)|0\rangle
=\text{one antiparticle of momentum }\mathbf p\text{ and spin }s.
$$

Both carry positive energy.

## Hamiltonian and charge

After normal ordering, the free Hamiltonian is

$$
\boxed{
:H:
=\sum_s\int d\mu(p)\,E_{\mathbf p}
\left[
 b_s^\dagger(\mathbf p)b_s(\mathbf p)
 +d_s^\dagger(\mathbf p)d_s(\mathbf p)
\right].
}
$$

Thus both particles and antiparticles contribute positively to the energy.

For the phase convention

$$
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
\overline\psi\mapsto e^{iq\alpha}\overline\psi,
$$

the conserved current is

$$
\boxed{
j^\mu=q\overline\psi\gamma^\mu\psi.
}
$$

The corresponding normal-ordered charge is

$$
\boxed{
:Q:
=q\sum_s\int d\mu(p)
\left[
 b_s^\dagger(\mathbf p)b_s(\mathbf p)
 -d_s^\dagger(\mathbf p)d_s(\mathbf p)
\right].
}
$$

So $b_s^\dagger$ creates charge $+q$, while $d_s^\dagger$ creates charge $-q$.

## Propagator

The Feynman propagator is

$$
S_F(x-y)=\langle0|T\psi(x)\overline\psi(y)|0\rangle.
$$

Using the mode expansion, the $u$ spinors contribute when $x^0>y^0$, and the $v$ spinors contribute when $y^0>x^0$. The spin sums combine these terms into the covariant expression

$$
\boxed{
S_F(x-y)=\int\frac{d^4p}{(2\pi)^4}\,
\frac{i(p\!\!/+m)e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
}
$$

This is related to the scalar propagator by

$$
\boxed{
S_F(x-y)=(i\gamma^\mu\partial_\mu+m)D_F(x-y).
}
$$

Indeed,

$$
\begin{aligned}
(i\gamma^\mu\partial_\mu-m)S_F(x-y)
&=(i\gamma^\mu\partial_\mu-m)(i\gamma^\nu\partial_\nu+m)D_F(x-y) \\
&=-(\Box+m^2)D_F(x-y) \\
&=i\delta^{(4)}(x-y)\mathbf 1.
\end{aligned}
$$

In momentum space, this says

$$
(p\!\!/-m)\frac{i(p\!\!/+m)}{p^2-m^2+i\epsilon}
=i\frac{p^2-m^2}{p^2-m^2+i\epsilon}\mathbf 1.
$$

The $i\epsilon$ prescription is the same Feynman boundary condition as in the scalar case.

## Locality and observables

The Dirac field is fermionic, so the local bracket is an anticommutator. The causal anticommutator has support only on and inside the light cone. Schematically,

$$
\{\psi_\alpha(x),\overline\psi_\beta(y)\}
=(i\gamma^\mu\partial_\mu+m)_{\alpha\beta}\,i\Delta(x-y),
$$

up to the conventional placement of factors of $i$.

Since $\Delta(z)$ vanishes for spacelike $z$, the anticommutator vanishes for spacelike separation. But $\psi$ itself is not an observable: it changes sign under a $2\pi$ rotation and changes fermion number. Physical local bosonic observables are built from even products of fermion fields, such as

$$
\overline\psi\psi,
\qquad
\overline\psi\gamma^\mu\psi,
\qquad
\overline\psi\gamma^\mu\gamma^5\psi.
$$

Those even operators commute at spacelike separation, as required for local observables.

## Massless limit and chirality preview

When $m=0$, the Dirac equation becomes

$$
i\gamma^\mu\partial_\mu\psi=0.
$$

The chiral projectors

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2}
$$

split the field into

$$
\psi_L=P_L\psi,
\qquad
\psi_R=P_R\psi.
$$

For $m=0$, the left- and right-handed fields decouple in the free equation. The detailed treatment of Weyl spinors, Majorana reality conditions, and chiral mass terms belongs to [Weyl and Majorana Fields](/foundations/free-fields/weyl-and-majorana-fields/).

## Three lenses

### Operator lens

The Dirac field is a fermionic operator-valued distribution. Its modes obey anticommutators, not commutators. The Hamiltonian counts particle and antiparticle modes with positive signs after normal ordering.

### Path-integral lens

The free Dirac action is Gaussian in Grassmann variables. The inverse of the quadratic operator is the Dirac propagator,

$$
S_F(p)=\frac{i(p\!\!/+m)}{p^2-m^2+i\epsilon}.
$$

Fermionic Gaussian integration produces determinants in the numerator or denominator depending on the convention, a fact that becomes central in fermion loops and anomalies.

### Structural lens

The Dirac field realizes the massive spin-one-half representation locally. Lorentz invariance fixes the spinor transformation law, locality fixes the need for both particle and antiparticle modes, and spin-statistics fixes anticommutation rather than commutation.

## Common pitfalls

### Calling the Dirac equation a relativistic Schrödinger equation

The free Dirac equation is first order in time, but in QFT $\psi(x)$ is an operator field, not a one-particle wavefunction. Dirac wavefunctions can be recovered as matrix elements or external-field approximations, but the field-theoretic object is primary.

### Forgetting the antiparticle term

The $d_s^\dagger v_s e^{ip\cdot x}$ term is required. Without it, the field cannot have the right locality and transformation properties. Antiparticles are not optional decoration.

### Quantizing Dirac fields with commutators

Using commutators for Dirac modes leads to negative-energy or negative-norm trouble. Fermionic anticommutators give a Hamiltonian bounded below and enforce Pauli exclusion.

### Dropping spin sums too casually

The compact numerator $p\!\!/+m$ comes from a spin sum. It is not the same object as an individual spinor. In scattering calculations, forgetting where the spin sum came from is a reliable way to lose factors and signs.

### Confusing chirality and helicity

For massless fermions, chirality and helicity are closely related. For massive fermions, they are distinct. The projectors $P_L$ and $P_R$ act on chirality, not directly on spin projection.

### Treating representation choices as physics

Dirac, Weyl, and Majorana bases are matrix representations of the same Clifford algebra. Physical statements should not depend on which explicit gamma matrices are used.

## Relations to other pages

- [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/) derives the anticommutation relations and fermionic Fock-space signs.
- [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/) gives the scalar equation and propagator from which the Dirac propagator can be built.
- [Weyl and Majorana Fields](/foundations/free-fields/weyl-and-majorana-fields/) will split Dirac fields into chiral and real special cases.
- [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/) will classify the local operators built from $\overline\psi$ and $\psi$.
- [Spinors from Lorentz Symmetry](/foundations/symmetry-and-spacetime/spinors-from-lorentz-symmetry/) will explain the representation-theoretic origin of Weyl and Dirac spinors.
- [Fermionic Path Integral](/foundations/path-integral-formalism/fermionic-path-integral/) will turn the free Dirac operator into a Grassmann Gaussian integral.

## Research status

This page is textbook-standard for free massive Dirac fields. The main subtleties are not in the displayed formulas but in their interpretation: spinor fields are operator-valued distributions, fermionic signs are structural rather than notational, and the one-particle Dirac equation is best understood as an approximation or matrix-element statement inside QFT. Interacting chiral fermions, anomalies, Majorana conditions, and gauge-field coupling require additional pages.

## Exercises

### Exercise 1: Squaring the Dirac operator

Show that

$$
(i\gamma^\mu\partial_\mu+m)(i\gamma^\nu\partial_\nu-m)=-(\Box+m^2).
$$

<details>
<summary><strong>Solution</strong></summary>

Expand the product:

$$
(i\gamma^\mu\partial_\mu+m)(i\gamma^\nu\partial_\nu-m)
=(i\gamma^\mu\partial_\mu)^2-m^2.
$$

The cross terms cancel because $m$ is constant. Next,

$$
(i\gamma^\mu\partial_\mu)^2
=-\gamma^\mu\gamma^\nu\partial_\mu\partial_\nu.
$$

Since $\partial_\mu\partial_\nu$ is symmetric in $\mu,\nu$, only the symmetric part of $\gamma^\mu\gamma^\nu$ contributes:

$$
\gamma^\mu\gamma^\nu\partial_\mu\partial_\nu
=\frac12\{\gamma^\mu,\gamma^\nu\}\partial_\mu\partial_\nu
=\eta^{\mu\nu}\partial_\mu\partial_\nu
=\Box.
$$

Therefore

$$
(i\gamma^\mu\partial_\mu+m)(i\gamma^\nu\partial_\nu-m)
=-\Box-m^2=-(\Box+m^2).
$$

</details>

### Exercise 2: Plane-wave spinor equations

Starting from

$$
(i\gamma^\mu\partial_\mu-m)\psi=0,
$$

show that $u_s(p)e^{-ip\cdot x}$ gives $(p\!\!/-m)u_s(p)=0$, while $v_s(p)e^{ip\cdot x}$ gives $(p\!\!/+m)v_s(p)=0$.

<details>
<summary><strong>Solution</strong></summary>

For the $u$ wave,

$$
\partial_\mu e^{-ip\cdot x}=-ip_\mu e^{-ip\cdot x}.
$$

Thus

$$
i\gamma^\mu\partial_\mu u_s(p)e^{-ip\cdot x}
=\gamma^\mu p_\mu u_s(p)e^{-ip\cdot x}
=p\!\!/u_s(p)e^{-ip\cdot x}.
$$

The Dirac equation becomes

$$
(p\!\!/-m)u_s(p)=0.
$$

For the $v$ wave,

$$
\partial_\mu e^{ip\cdot x}=ip_\mu e^{ip\cdot x},
$$

so

$$
i\gamma^\mu\partial_\mu v_s(p)e^{ip\cdot x}
=-p\!\!/v_s(p)e^{ip\cdot x}.
$$

The Dirac equation becomes

$$
(-p\!\!/-m)v_s(p)=0,
$$

or equivalently

$$
(p\!\!/+m)v_s(p)=0.
$$

</details>

### Exercise 3: Current conservation

Using the Dirac equation and the adjoint equation, prove that

$$
j^\mu=q\overline\psi\gamma^\mu\psi
$$

is conserved.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
\partial_\mu j^\mu
=q(\partial_\mu\overline\psi)\gamma^\mu\psi
+q\overline\psi\gamma^\mu\partial_\mu\psi.
$$

The Dirac equation gives

$$
i\gamma^\mu\partial_\mu\psi=m\psi,
$$

so

$$
\overline\psi\gamma^\mu\partial_\mu\psi
=-im\overline\psi\psi.
$$

The adjoint equation is

$$
i(\partial_\mu\overline\psi)\gamma^\mu+m\overline\psi=0,
$$

so

$$
(\partial_\mu\overline\psi)\gamma^\mu\psi
=im\overline\psi\psi.
$$

The two terms cancel:

$$
\partial_\mu j^\mu
=q(im\overline\psi\psi-im\overline\psi\psi)=0.
$$

</details>

### Exercise 4: Propagator from the scalar propagator

Given

$$
S_F(x)=(i\gamma^\mu\partial_\mu+m)D_F(x),
$$

and

$$
D_F(x)=\int\frac{d^4p}{(2\pi)^4}\frac{i e^{-ip\cdot x}}{p^2-m^2+i\epsilon},
$$

show that

$$
S_F(x)=\int\frac{d^4p}{(2\pi)^4}\frac{i(p\!\!/+m)e^{-ip\cdot x}}{p^2-m^2+i\epsilon}.
$$

<details>
<summary><strong>Solution</strong></summary>

Act on the exponential:

$$
i\gamma^\mu\partial_\mu e^{-ip\cdot x}
=p\!\!/e^{-ip\cdot x}.
$$

Therefore

$$
(i\gamma^\mu\partial_\mu+m)e^{-ip\cdot x}
=(p\!\!/+m)e^{-ip\cdot x}.
$$

Substituting into the scalar propagator representation gives

$$
S_F(x)=\int\frac{d^4p}{(2\pi)^4}\frac{i(p\!\!/+m)e^{-ip\cdot x}}{p^2-m^2+i\epsilon}.
$$

</details>

### Exercise 5: Inverting the Dirac operator

Show that

$$
(i\gamma^\mu\partial_\mu-m)S_F(x)=i\delta^{(4)}(x)\mathbf 1.
$$

<details>
<summary><strong>Solution</strong></summary>

Using

$$
S_F(x)=(i\gamma^\mu\partial_\mu+m)D_F(x),
$$

we get

$$
(i\gamma^\mu\partial_\mu-m)S_F(x)
=(i\gamma^\mu\partial_\mu-m)(i\gamma^\nu\partial_\nu+m)D_F(x).
$$

The product is

$$
-(\Box+m^2)D_F(x).
$$

The scalar Feynman propagator satisfies

$$
(\Box+m^2)D_F(x)=-i\delta^{(4)}(x).
$$

Therefore

$$
(i\gamma^\mu\partial_\mu-m)S_F(x)
=i\delta^{(4)}(x)\mathbf 1.
$$

</details>

### Exercise 6: Charge of particles and antiparticles

Using

$$
:Q:
=q\sum_s\int d\mu(p)
\left[b_s^\dagger(\mathbf p)b_s(\mathbf p)-d_s^\dagger(\mathbf p)d_s(\mathbf p)\right],
$$

show that $b_s^\dagger(\mathbf p)|0\rangle$ has charge $+q$ and $d_s^\dagger(\mathbf p)|0\rangle$ has charge $-q$.

<details>
<summary><strong>Solution</strong></summary>

For one fixed mode, the relevant fermionic number operators are

$$
N_b=b^\dagger b,
\qquad
N_d=d^\dagger d.
$$

They obey

$$
[N_b,b^\dagger]=b^\dagger,
\qquad
[N_d,d^\dagger]=d^\dagger,
$$

with all mixed commutators zero. The charge operator has the form

$$
Q=q(N_b-N_d).
$$

Thus

$$
[Q,b^\dagger]=q b^\dagger,
\qquad
[Q,d^\dagger]=-q d^\dagger.
$$

Since $Q|0\rangle=0$,

$$
Q b^\dagger|0\rangle
=[Q,b^\dagger]|0\rangle
=q b^\dagger|0\rangle,
$$

and

$$
Q d^\dagger|0\rangle
=[Q,d^\dagger]|0\rangle
=-q d^\dagger|0\rangle.
$$

Therefore the particle has charge $+q$ and the antiparticle has charge $-q$.

</details>

## References

### Primary references

- P. A. M. Dirac, “The Quantum Theory of the Electron,” *Proceedings of the Royal Society A* **117** (1928), for the Dirac equation.
- P. A. M. Dirac, “A Theory of Electrons and Protons,” *Proceedings of the Royal Society A* **126** (1930), for the historical hole-theory interpretation.
- P. Jordan and E. Wigner, “Über das Paulische Äquivalenzverbot,” *Zeitschrift für Physik* **47** (1928), for early anticommutation ideas.
- E. Majorana, “Teoria simmetrica dell'elettrone e del positrone,” *Il Nuovo Cimento* **14** (1937), for the Majorana variant.

### Standard textbook treatments

- M. Srednicki, *Quantum Field Theory*, §§36–39 and 42, for spinor Lagrangians, canonical quantization, Dirac mode expansion, spinor technology, and the free fermion propagator.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 19–21, for constructing the Dirac equation, solving it in plane waves, canonical quantization, and calculating the propagator.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.5, 6.2, 7.1, and 14.1, for causal Dirac fields, general propagator structure, canonical variables, and the relation between Dirac fields and c-number Dirac wavefunctions.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. II.1–II.2, for a compact physics-first introduction to the Dirac equation and quantization of the Dirac field.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, ch. 3, for the standard particle-physics treatment of spinors, spin sums, and the Dirac propagator.

### For a first pass

- Zee, chs. II.1–II.2.
- Peskin and Schroeder, §§3.1–3.3.
- Coleman, chs. 20–21.

### For mathematical precision

- Weinberg, Vol. I, chs. 5 and 7, for representation-theoretic and canonical foundations.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for a theorem-oriented treatment of fermionic fields, locality, and spin-statistics.
- P. Deligne et al., *Quantum Fields and Strings: A Course for Mathematicians*, Vol. I, for spinors, Clifford algebras, and fermionic fields from a mathematical viewpoint.

## Version history

- **2026-05-22:** Initial qft.org free-field reference page for the Dirac field, including gamma conventions, Dirac equation, plane-wave spinors, mode expansion, Hamiltonian, charge, propagator, locality, massless chirality preview, pitfalls, exercises, and a TikZ-generated structural figure.
