---
title: "Fermionic Canonical Quantization"
description: "Canonical quantization of fermionic fields: anticommutators, fermionic oscillators, Dirac field modes, particle and antiparticle operators, charge, normal ordering, and graded locality."
sidebar:
  label: "Fermionic Canonical Quantization"
  order: 7
---

## Summary

Bosonic canonical quantization replaces classical Poisson brackets by commutators. Fermionic canonical quantization replaces the corresponding fermionic brackets by anticommutators.

For one fermionic oscillator,

$$
\{f,f^\dagger\}=1,
\qquad
f^2=(f^\dagger)^2=0.
$$

The number operator is

$$
N=f^\dagger f,
$$

and its eigenvalues are only

$$
n=0,1.
$$

This algebra is the operator form of Pauli exclusion: a fixed fermionic mode is either empty or occupied once.

For a Dirac field in qft.org's mostly-minus convention,

$$
\mathcal L=\overline\psi(i\gamma^\mu\partial_\mu-m)\psi,
\qquad
\overline\psi=\psi^\dagger\gamma^0,
$$

canonical quantization imposes the equal-time anticommutators

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

Equivalently,

$$
\boxed{
\{\psi_\alpha(t,\mathbf x),\overline\psi_\beta(t,\mathbf y)\}
=(\gamma^0)_{\alpha\beta}\delta^{(3)}(\mathbf x-\mathbf y).
}
$$

The free Dirac field has the mode expansion

$$
\boxed{
\psi(x)=\sum_s\int d\mu(p)
\left[
 b_s(\mathbf p)u_s(p)e^{-ip\cdot x}
 +d_s^\dagger(\mathbf p)v_s(p)e^{ip\cdot x}
\right],
}
$$

where $p^0=E_{\mathbf p}>0$. The nonzero oscillator anticommutators are

$$
\boxed{
\{b_s(\mathbf p),b_r^\dagger(\mathbf q)\}
=(2\pi)^3 2E_{\mathbf p}\delta_{sr}\delta^{(3)}(\mathbf p-\mathbf q),
}
$$

and

$$
\boxed{
\{d_s(\mathbf p),d_r^\dagger(\mathbf q)\}
=(2\pi)^3 2E_{\mathbf p}\delta_{sr}\delta^{(3)}(\mathbf p-\mathbf q).
}
$$

After normal ordering, the Hamiltonian and charge are

$$
\boxed{
:H:=\sum_s\int d\mu(p)\,E_{\mathbf p}
\left[
 b_s^\dagger(\mathbf p)b_s(\mathbf p)
 +d_s^\dagger(\mathbf p)d_s(\mathbf p)
\right],
}
$$

and, for the phase convention $\psi\mapsto e^{-iq\alpha}\psi$,

$$
\boxed{
Q=q\sum_s\int d\mu(p)
\left[
 b_s^\dagger(\mathbf p)b_s(\mathbf p)
 -d_s^\dagger(\mathbf p)d_s(\mathbf p)
\right].
}
$$

Thus $b_s^\dagger(\mathbf p)$ creates a particle of charge $+q$ and energy $E_{\mathbf p}$, while $d_s^\dagger(\mathbf p)$ creates an antiparticle of charge $-q$ and the same positive energy. Srednicki gives the canonical Weyl and Dirac anticommutation relations before solving the Dirac equation in modes; Coleman emphasizes the resulting fermionic Fock space, antisymmetric multiparticle states, and exclusion principle; Weinberg treats fermionic fields as the causal spin-one-half realization of the general quantum-field construction (Srednicki 2007, §§37–39; Coleman 2019, ch. 21; Weinberg 1995, Vol. I, §§5.5 and 7.1).

## Prerequisites

You should know [Bosons and Fermions](/foundations/relativistic-particles-and-fields/bosons-and-fermions/), [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/), [Canonical Commutation Relations](/foundations/canonical-quantization/canonical-commutation-relations/), [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/), and [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/). We use the conventions of [Conventions and Normalizations](/foundations/conventions-and-normalizations/): mostly-minus metric, $p\cdot x=p^0t-\mathbf p\cdot\mathbf x$, gamma matrices satisfying $\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}$, and covariant on-shell measure

$$
d\mu(p)=\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}.
$$

This page uses Dirac spinors $u_s(p)$ and $v_s(p)$. The detailed construction of these spinors belongs to [Dirac Field](/foundations/free-fields/dirac-field/); here we only need their standard normalization and completeness relations.

## Core idea

A scalar mode is a bosonic oscillator. A spinor mode is a fermionic oscillator. The difference is not cosmetic: it changes the algebra, the occupation numbers, the sign rules, and the causal bracket.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Fermionic oscillator occupancy and Dirac particle-antiparticle sectors](/figures/foundations/fermionic-mode-algebra.svg)

<figcaption>

A single fermionic oscillator has only two states, $|0\rangle$ and $f^\dagger|0\rangle$, because $(f^\dagger)^2=0$. A Dirac field has two fermionic oscillator species for each momentum and spin: $b_s^\dagger(\mathbf p)$ creates a particle and $d_s^\dagger(\mathbf p)$ creates an antiparticle. Both carry positive energy; the charge operator counts them with opposite signs.

</figcaption>
</figure>

The bosonic scalar field made locality visible through commutators. The fermionic spinor field makes locality visible through anticommutators. More precisely, the local algebra is graded: spacelike separated bosonic fields commute, spacelike separated fermionic fields anticommute, and physical even operators built from fermions commute at spacelike separation.

:::note[Assumptions]
This page treats free spin-one-half fields in flat Minkowski spacetime. It does not prove the spin-statistics theorem. Instead, it explains the canonical fermionic algebra that is compatible with positive energy, Pauli exclusion, and local relativistic field theory. A full proof of the spin-statistics theorem uses additional assumptions such as Lorentz invariance, locality, positive energy, and a stable vacuum.
:::

## One fermionic oscillator

A fermionic oscillator is generated by two operators $f$ and $f^\dagger$ obeying

$$
\{f,f^\dagger\}=ff^\dagger+f^\dagger f=1,
$$

and

$$
\{f,f\}=0,
\qquad
\{f^\dagger,f^\dagger\}=0.
$$

The last two equations imply

$$
f^2=0,
\qquad
(f^\dagger)^2=0.
$$

Let $|0\rangle$ be the state annihilated by $f$:

$$
f|0\rangle=0.
$$

Then

$$
|1\rangle=f^\dagger|0\rangle
$$

is the one-particle state. There is no two-particle state in the same mode, because

$$
(f^\dagger)^2|0\rangle=0.
$$

The number operator is

$$
N=f^\dagger f.
$$

It acts as

$$
N|0\rangle=0,
\qquad
N|1\rangle=|1\rangle.
$$

It also satisfies

$$
N^2=N,
$$

so its only eigenvalues are $0$ and $1$.

For a free oscillator with energy $E$, define

$$
H=E f^\dagger f.
$$

Then

$$
[H,f]=-Ef,
\qquad
[H,f^\dagger]=Ef^\dagger.
$$

The brackets in this last line are ordinary commutators because $H$ is an even operator. Odd operators such as $f$ and $f^\dagger$ are moved past each other using anticommutators; even observables act by ordinary commutators.

This tiny algebra already contains the major qualitative facts about fermions: finite occupancy, exchange signs, and a number operator with integer eigenvalues $0$ and $1$.

## Why anticommutators are not optional

For scalar fields, the canonical equal-time algebra is a commutator algebra. For spinor fields, the canonical equal-time algebra is an anticommutator algebra.

That statement can feel like an unexplained rule when first encountered. The reason is structural. A local relativistic spin-one-half field quantized with the wrong statistics does not give the right causal algebra and positive-energy Fock space. In the fully developed theory, this is part of the spin-statistics theorem: half-integer spin fields are fermionic, while integer-spin fields are bosonic.

On this page, the practical lesson is enough:

$$
\text{spinor field}\quad\Longrightarrow\quad\text{fermionic oscillator modes}\quad\Longrightarrow\quad\text{anticommutators}.
$$

The anticommutator is not a stylistic variant of the commutator. It changes the Hilbert space.

## The Dirac Lagrangian and canonical variables

The free Dirac Lagrangian is

$$
\mathcal L
=\overline\psi(i\gamma^\mu\partial_\mu-m)\psi.
$$

Using $\overline\psi=\psi^\dagger\gamma^0$, this can be written as

$$
\mathcal L
=i\psi^\dagger\dot\psi
+i\overline\psi\gamma^i\partial_i\psi
-m\overline\psi\psi.
$$

The momentum conjugate to $\psi_\alpha$ is therefore

$$
\pi_\alpha
=\frac{\partial\mathcal L}{\partial\dot\psi_\alpha}
=i\psi_\alpha^\dagger.
$$

The canonical fermionic relation is

$$
\{\psi_\alpha(t,\mathbf x),\pi_\beta(t,\mathbf y)\}
=i\delta_{\alpha\beta}\delta^{(3)}(\mathbf x-\mathbf y).
$$

Substituting $\pi_\beta=i\psi_\beta^\dagger$ gives

$$
\{\psi_\alpha(t,\mathbf x),\psi_\beta^\dagger(t,\mathbf y)\}
=\delta_{\alpha\beta}\delta^{(3)}(\mathbf x-\mathbf y).
$$

The remaining elementary equal-time anticommutators vanish:

$$
\{\psi_\alpha(t,\mathbf x),\psi_\beta(t,\mathbf y)\}=0,
$$

and

$$
\{\psi_\alpha^\dagger(t,\mathbf x),\psi_\beta^\dagger(t,\mathbf y)\}=0.
$$

In terms of the Dirac adjoint,

$$
\overline\psi_\beta=\psi_\rho^\dagger(\gamma^0)_{\rho\beta},
$$

so

$$
\{\psi_\alpha(t,\mathbf x),\overline\psi_\beta(t,\mathbf y)\}
=(\gamma^0)_{\alpha\beta}\delta^{(3)}(\mathbf x-\mathbf y).
$$

:::caution[First-order systems are constrained]
The Dirac Lagrangian is first order in time derivatives. If one treats $\psi$ and $\psi^\dagger$ as ordinary independent canonical variables, the momentum conjugate to $\psi^\dagger$ vanishes and the system is constrained. A careful derivation uses fermionic variables and Dirac brackets, or equivalently Grassmann variables in the path integral. For the free canonical construction, the equal-time anticommutator above is the standard result.
:::

## Equations of motion

Varying the Dirac action with respect to $\overline\psi$ gives

$$
\boxed{
(i\gamma^\mu\partial_\mu-m)\psi=0.
}
$$

The adjoint equation is

$$
\boxed{
\overline\psi(i\overleftarrow{\partial}_\mu\gamma^\mu+m)=0,
}
$$

where the derivative acts to the left:

$$
\overline\psi\overleftarrow{\partial}_\mu
=\partial_\mu\overline\psi.
$$

Acting on the Dirac equation with $(i\gamma^\nu\partial_\nu+m)$ gives

$$
(\Box+m^2)\psi=0,
$$

so each component of a free Dirac field also obeys the Klein–Gordon equation. The Dirac equation is stronger: it is first order and ties the components together.

## Mode expansion

Let $u_s(p)$ and $v_s(p)$ be positive-energy spinor wavefunctions satisfying

$$
(p\!\!/-m)u_s(p)=0,
\qquad
(p\!\!/+m)v_s(p)=0,
$$

where

$$
p\!\!/ = \gamma^\mu p_\mu,
\qquad
p^0=E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

A convenient normalization is

$$
u_s^\dagger(p)u_r(p)=2E_{\mathbf p}\delta_{sr},
\qquad
v_s^\dagger(p)v_r(p)=2E_{\mathbf p}\delta_{sr},
$$

and

$$
\overline u_s(p)u_r(p)=2m\delta_{sr},
\qquad
\overline v_s(p)v_r(p)=-2m\delta_{sr}.
$$

The completeness relations are

$$
\sum_s u_s(p)\overline u_s(p)=p\!\!/+m,
$$

and

$$
\sum_s v_s(p)\overline v_s(p)=p\!\!/-m.
$$

With these conventions, the free Dirac field is expanded as

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

The operators $b_s^\dagger(\mathbf p)$ and $b_s(\mathbf p)$ create and annihilate particles. The operators $d_s^\dagger(\mathbf p)$ and $d_s(\mathbf p)$ create and annihilate antiparticles.

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

All $bb$, $b^\dagger b^\dagger$, $dd$, $d^\dagger d^\dagger$, and mixed $b$-$d$ anticommutators vanish.

The vacuum is defined by

$$
b_s(\mathbf p)|0\rangle=0,
\qquad
d_s(\mathbf p)|0\rangle=0.
$$

The one-particle states are

$$
|\mathbf p,s;+\rangle=b_s^\dagger(\mathbf p)|0\rangle,
$$

and

$$
|\mathbf p,s;-\rangle=d_s^\dagger(\mathbf p)|0\rangle.
$$

The plus and minus labels here denote particle and antiparticle charge sectors, not positive and negative energy sectors.

## Hamiltonian and charge

The canonical Hamiltonian density for the Dirac field is

$$
\mathcal H
=\psi^\dagger(-i\boldsymbol\alpha\cdot\boldsymbol\nabla+\beta m)\psi,
$$

where

$$
\alpha^i=\gamma^0\gamma^i,
\qquad
\beta=\gamma^0.
$$

Substituting the mode expansion gives a formal expression of the form

$$
H=\sum_s\int d\mu(p)\,E_{\mathbf p}
\left[
 b_s^\dagger(\mathbf p)b_s(\mathbf p)
 -d_s(\mathbf p)d_s^\dagger(\mathbf p)
\right].
$$

Using the anticommutator to move $d_s^\dagger$ to the left produces a divergent c-number plus a positive antiparticle number operator:

$$
H=E_{\mathrm{vac}}
+\sum_s\int d\mu(p)\,E_{\mathbf p}
\left[
 b_s^\dagger(\mathbf p)b_s(\mathbf p)
 +d_s^\dagger(\mathbf p)d_s(\mathbf p)
\right].
$$

Normal ordering subtracts the vacuum c-number:

$$
:H:=\sum_s\int d\mu(p)\,E_{\mathbf p}
\left[
 b_s^\dagger(\mathbf p)b_s(\mathbf p)
 +d_s^\dagger(\mathbf p)d_s(\mathbf p)
\right].
$$

Thus

$$
:H:b_s^\dagger(\mathbf q)|0\rangle
=E_{\mathbf q}b_s^\dagger(\mathbf q)|0\rangle,
$$

and

$$
:H:d_s^\dagger(\mathbf q)|0\rangle
=E_{\mathbf q}d_s^\dagger(\mathbf q)|0\rangle.
$$

Both particles and antiparticles have positive energy.

The Dirac Lagrangian is invariant under the global phase rotation

$$
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
\overline\psi\mapsto \overline\psi e^{iq\alpha}.
$$

The corresponding current is

$$
j^\mu=q\overline\psi\gamma^\mu\psi.
$$

The normal-ordered charge is

$$
Q=q\sum_s\int d\mu(p)
\left[
 b_s^\dagger(\mathbf p)b_s(\mathbf p)
 -d_s^\dagger(\mathbf p)d_s(\mathbf p)
\right].
$$

Therefore

$$
[Q,b_s^\dagger(\mathbf p)]=q b_s^\dagger(\mathbf p),
$$

and

$$
[Q,d_s^\dagger(\mathbf p)]=-q d_s^\dagger(\mathbf p).
$$

The antiparticle has the opposite charge because the operator creating it appears in the opposite frequency part of the field and contributes with the opposite sign to the normal-ordered charge.

## Fermionic normal ordering

Normal ordering for fermions also means “put creation operators to the left of annihilation operators,” but now every interchange of two fermionic operators contributes a minus sign.

For one fermionic oscillator,

$$
:f^\dagger f:=f^\dagger f,
$$

but

$$
:ff^\dagger:=-f^\dagger f.
$$

That minus sign is not optional. It is the same exchange sign that makes two-fermion states antisymmetric.

For example,

$$
f f^\dagger=1-f^\dagger f,
$$

so

$$
\langle0|f f^\dagger|0\rangle=1,
$$

whereas

$$
\langle0|:f f^\dagger:|0\rangle=0.
$$

The field-theory version is the same. Normal-ordered fermion bilinears subtract the vacuum c-number relative to the chosen free vacuum, with signs determined by fermionic exchange.

## Equal-time anticommutators from modes

The mode expansion reproduces the canonical equal-time algebra. The key input is the spinor completeness relation.

At equal time $x^0=y^0=t$, the particle part of

$$
\{\psi_\alpha(t,\mathbf x),\psi_\beta^\dagger(t,\mathbf y)\}
$$

comes from the $b$-$b^\dagger$ anticommutator. The antiparticle part comes from the $d^\dagger$-$d$ anticommutator. Schematically,

$$
\{\psi_\alpha(t,\mathbf x),\psi_\beta^\dagger(t,\mathbf y)\}
=\int\frac{d^3\mathbf p}{(2\pi)^3}
\left[\text{spin sum}\right]_{\alpha\beta}
 e^{i\mathbf p\cdot(\mathbf x-\mathbf y)}.
$$

With the standard normalization of $u_s$ and $v_s$, the spin sum reduces to the identity matrix in spinor space, giving

$$
\{\psi_\alpha(t,\mathbf x),\psi_\beta^\dagger(t,\mathbf y)\}
=\delta_{\alpha\beta}\delta^{(3)}(\mathbf x-\mathbf y).
$$

The equal-time anticommutators

$$
\{\psi_\alpha(t,\mathbf x),\psi_\beta(t,\mathbf y)\}=0,
$$

and

$$
\{\psi_\alpha^\dagger(t,\mathbf x),\psi_\beta^\dagger(t,\mathbf y)\}=0
$$

follow from the vanishing $bb$, $dd$, $b^\dagger b^\dagger$, $d^\dagger d^\dagger$, and mixed anticommutators.

## Graded locality

For a scalar field, the causal bracket is a commutator:

$$
[\phi(x),\phi(y)]=0
\quad\text{for}\quad (x-y)^2<0.
$$

For a Dirac field, the corresponding causal bracket is an anticommutator. One finds

$$
\boxed{
\{\psi_\alpha(x),\overline\psi_\beta(y)\}
=\left(i\gamma^\mu\partial_\mu+m\right)_{\alpha\beta}i\Delta(x-y),
}
$$

where $\Delta$ is the Pauli–Jordan function for mass $m$. Since $\Delta(x-y)$ has causal support,

$$
\boxed{
\{\psi_\alpha(x),\overline\psi_\beta(y)\}=0
\quad\text{for}\quad (x-y)^2<0.
}
$$

Similarly,

$$
\{\psi_\alpha(x),\psi_\beta(y)\}=0
\quad\text{for spacelike separation}.
$$

This is called graded locality. Odd fermionic fields anticommute at spacelike separation. Even operators built from an even number of fermion fields, such as currents and stress tensors, commute with other even local operators at spacelike separation.

For example, the current

$$
j^\mu(x)=q\overline\psi(x)\gamma^\mu\psi(x)
$$

is bosonic. It is built from two fermion fields, so it belongs to the even part of the local operator algebra.

## Weyl and Majorana variants

The Dirac field is not the only spinor field. The same canonical idea applies to Weyl and Majorana fields, with the appropriate independent variables.

For a left-handed Weyl field $\chi_a$, the massless kinetic term is

$$
\mathcal L=i\chi^\dagger \overline\sigma^\mu\partial_\mu\chi.
$$

The basic equal-time anticommutator is

$$
\{\chi_a(t,\mathbf x),\chi_b^\dagger(t,\mathbf y)\}
=\delta_{ab}\delta^{(3)}(\mathbf x-\mathbf y),
$$

with

$$
\{\chi_a(t,\mathbf x),\chi_b(t,\mathbf y)\}=0.
$$

A Majorana field obeys a reality condition relating the field to its charge conjugate. In a compact notation,

$$
\psi_M=\psi_M^c.
$$

Its free mode expansion has only one independent oscillator species:

$$
\psi_M(x)=\sum_s\int d\mu(p)
\left[
 b_s(\mathbf p)u_s(p)e^{-ip\cdot x}
 +b_s^\dagger(\mathbf p)v_s(p)e^{ip\cdot x}
\right].
$$

A Majorana particle is its own antiparticle in the sense that there is no independent conserved $U(1)$ charge distinguishing $b$ from $d$. This does not mean the field is bosonic. A Majorana field is still fermionic and still obeys anticommutation relations.

## Comparison with scalar quantization

| Feature | Real scalar field | Dirac field |
|---|---|---|
| Spin | $0$ | $1/2$ |
| Basic bracket | commutator | anticommutator |
| One-mode algebra | $[a,a^\dagger]=1$ | $\{f,f^\dagger\}=1$ |
| Occupancy of one mode | $0,1,2,\ldots$ | $0,1$ |
| Free-field expansion | $a+a^\dagger$ | $b+d^\dagger$ |
| Antiparticle sector | absent for real scalar; separate for complex scalar | present for Dirac field |
| Causal bracket | $[\phi(x),\phi(y)]$ | $\{\psi(x),\overline\psi(y)\}$ |
| Normal-ordering sign | no sign from swapping bosons | minus sign for each fermion swap |

The slogan is useful but incomplete:

$$
\text{bosons commute, fermions anticommute.}
$$

The more precise statement is that local QFT has a graded operator algebra. Integer-spin fields are even and use commutators; half-integer-spin fields are odd and use anticommutators.

## Common pitfalls

### Treating anticommutators as a cosmetic minus sign

The fermionic algebra changes the Hilbert space. The equation $(f^\dagger)^2=0$ removes multiple occupancy of a single mode. This is not a small perturbation of the bosonic oscillator.

### Saying antiparticles have negative energy

The negative-frequency term in the field expansion contains the antiparticle creation operator $d^\dagger$. The physical state $d_s^\dagger(\mathbf p)|0\rangle$ has positive energy $E_{\mathbf p}$.

### Forgetting signs in fermionic normal ordering

For fermions,

$$
:ff^\dagger:=-f^\dagger f.
$$

Every swap of two odd operators costs a minus sign.

### Confusing field anticommutation with observable anticommutation

The spinor field itself is not a bosonic classical observable. Physical local bosonic operators such as $\overline\psi\psi$, $\overline\psi\gamma^\mu\psi$, and the stress tensor are even in fermion fields and obey ordinary spacelike commutativity with other even local operators.

### Ignoring the constrained nature of first-order systems

The Dirac Lagrangian is first order in time derivatives. A fully systematic canonical derivation uses fermionic constraints or Grassmann variables. The standard equal-time anticommutators encode the result.

## Relation to other topics

- [Bosons and Fermions](/foundations/relativistic-particles-and-fields/bosons-and-fermions/) explains the exchange-statistics side before fields are quantized.
- [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/) explains why the negative-frequency part of a relativistic field is reinterpreted as antiparticle creation.
- [Normal Ordering](/foundations/canonical-quantization/normal-ordering/) explains the bosonic version of vacuum subtraction; this page adds the fermionic sign rule.
- [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/) gives the scalar Pauli–Jordan commutator; here the analogous object is the Dirac anticommutator.
- [Dirac Field](/foundations/free-fields/dirac-field/) develops the spinor solutions, bilinears, spin sums, and propagator in detail.
- [Grassmann Variables](/foundations/path-integral-formalism/grassmann-variables/) and [Fermionic Path Integral](/foundations/path-integral-formalism/fermionic-path-integral/) translate this operator algebra into Berezin integration.
- [Spin-Statistics](/foundations/symmetry-and-spacetime/spin-statistics/) will give the structural theorem behind the boson/fermion assignment.

## Exercises

### Exercise 1: Finite occupancy

Let $f$ and $f^\dagger$ obey

$$
\{f,f^\dagger\}=1,
\qquad
f^2=(f^\dagger)^2=0.
$$

Show that $N=f^\dagger f$ satisfies $N^2=N$. Conclude that the only eigenvalues of $N$ are $0$ and $1$.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
N^2=f^\dagger f f^\dagger f.
$$

Using

$$
f f^\dagger=1-f^\dagger f,
$$

we get

$$
N^2=f^\dagger(1-f^\dagger f)f
=f^\dagger f-f^\dagger f^\dagger f f.
$$

But $(f^\dagger)^2=0$ and $f^2=0$, so the second term vanishes:

$$
N^2=N.
$$

If $N|n\rangle=n|n\rangle$, then

$$
N^2|n\rangle=n^2|n\rangle=N|n\rangle=n|n\rangle.
$$

Thus

$$
n^2=n,
$$

so

$$
n=0\quad\text{or}\quad n=1.
$$

</details>

### Exercise 2: Raising and lowering operators

For

$$
H=Ef^\dagger f,
$$

show that

$$
[H,f]=-Ef,
\qquad
[H,f^\dagger]=Ef^\dagger.
$$

<details>
<summary><strong>Solution</strong></summary>

First,

$$
[H,f]=E(f^\dagger f f-f f^\dagger f).
$$

The first term vanishes because $f^2=0$:

$$
f^\dagger f f=0.
$$

For the second term,

$$
f f^\dagger f=(1-f^\dagger f)f=f-f^\dagger f^2=f.
$$

Therefore

$$
[H,f]=-Ef.
$$

Similarly,

$$
[H,f^\dagger]=E(f^\dagger f f^\dagger-f^\dagger f^\dagger f).
$$

The second term vanishes, and

$$
f^\dagger f f^\dagger=f^\dagger(1-f^\dagger f)=f^\dagger.
$$

Thus

$$
[H,f^\dagger]=Ef^\dagger.
$$

</details>

### Exercise 3: Antisymmetry of two-fermion states

Let

$$
\{b_s^\dagger(\mathbf p),b_r^\dagger(\mathbf q)\}=0.
$$

Show that

$$
b_s^\dagger(\mathbf p)b_r^\dagger(\mathbf q)|0\rangle
=-b_r^\dagger(\mathbf q)b_s^\dagger(\mathbf p)|0\rangle.
$$

Then show that two identical fermions cannot occupy the same momentum-spin mode.

<details>
<summary><strong>Solution</strong></summary>

The anticommutator gives

$$
b_s^\dagger(\mathbf p)b_r^\dagger(\mathbf q)
+b_r^\dagger(\mathbf q)b_s^\dagger(\mathbf p)=0.
$$

Thus

$$
b_s^\dagger(\mathbf p)b_r^\dagger(\mathbf q)
=-b_r^\dagger(\mathbf q)b_s^\dagger(\mathbf p).
$$

Acting on the vacuum gives the desired antisymmetry of the two-particle state.

If the two modes are identical, then

$$
b_s^\dagger(\mathbf p)b_s^\dagger(\mathbf p)
=-b_s^\dagger(\mathbf p)b_s^\dagger(\mathbf p),
$$

so

$$
2b_s^\dagger(\mathbf p)b_s^\dagger(\mathbf p)=0.
$$

Therefore

$$
\left(b_s^\dagger(\mathbf p)\right)^2=0.
$$

</details>

### Exercise 4: Particle and antiparticle charges

Given

$$
Q=q\sum_s\int d\mu(p)
\left[b_s^\dagger(\mathbf p)b_s(\mathbf p)-d_s^\dagger(\mathbf p)d_s(\mathbf p)\right],
$$

show that

$$
[Q,b_r^\dagger(\mathbf q)]=q b_r^\dagger(\mathbf q),
$$

and

$$
[Q,d_r^\dagger(\mathbf q)]=-q d_r^\dagger(\mathbf q).
$$

<details>
<summary><strong>Solution</strong></summary>

For one mode, the number operators satisfy

$$
[N_b,b^\dagger]=b^\dagger,
\qquad
[N_d,d^\dagger]=d^\dagger.
$$

The $b$ and $d$ sectors anticommute as odd operators, but the number operators are even and commute with the opposite sector. Therefore

$$
[Q,b_r^\dagger(\mathbf q)]=q b_r^\dagger(\mathbf q),
$$

and

$$
[Q,d_r^\dagger(\mathbf q)]=-q d_r^\dagger(\mathbf q).
$$

If $Q|0\rangle=0$, then

$$
Qb_r^\dagger(\mathbf q)|0\rangle
=q b_r^\dagger(\mathbf q)|0\rangle,
$$

while

$$
Qd_r^\dagger(\mathbf q)|0\rangle
=-q d_r^\dagger(\mathbf q)|0\rangle.
$$

</details>

### Exercise 5: Fermionic normal-ordering sign

Show that

$$
:ff^\dagger:=-f^\dagger f.
$$

Then verify that

$$
\langle0|:ff^\dagger:|0\rangle=0,
$$

while

$$
\langle0|ff^\dagger|0\rangle=1.
$$

<details>
<summary><strong>Solution</strong></summary>

Normal ordering moves the creation operator $f^\dagger$ to the left of the annihilation operator $f$. Since both are fermionic, one swap introduces a minus sign:

$$
:ff^\dagger:=-f^\dagger f.
$$

Because $f|0\rangle=0$,

$$
\langle0|:ff^\dagger:|0\rangle
=-\langle0|f^\dagger f|0\rangle=0.
$$

But

$$
ff^\dagger=1-f^\dagger f,
$$

so

$$
\langle0|ff^\dagger|0\rangle
=\langle0|0\rangle-0=1.
$$

</details>

### Exercise 6: Dirac anticommutator from the scalar commutator function

Using

$$
i\Delta(z)=\int d\mu(p)\left(e^{-ip\cdot z}-e^{ip\cdot z}\right),
$$

show that

$$
\left(i\gamma^\mu\partial_\mu+m\right)i\Delta(z)
=\int d\mu(p)
\left[(p\!\!/+m)e^{-ip\cdot z}+(p\!\!/-m)e^{ip\cdot z}\right].
$$

Explain why this expression has causal support.

<details>
<summary><strong>Solution</strong></summary>

Act on the first exponential:

$$
i\gamma^\mu\partial_\mu e^{-ip\cdot z}
=\gamma^\mu p_\mu e^{-ip\cdot z}=p\!\!/ e^{-ip\cdot z}.
$$

Act on the second exponential:

$$
i\gamma^\mu\partial_\mu e^{ip\cdot z}
=-p\!\!/ e^{ip\cdot z}.
$$

Since $i\Delta$ contains $e^{-ip\cdot z}-e^{ip\cdot z}$,

$$
\begin{aligned}
\left(i\gamma^\mu\partial_\mu+m\right)i\Delta(z)
&=\int d\mu(p)
\left[(p\!\!/+m)e^{-ip\cdot z}-(-p\!\!/+m)e^{ip\cdot z}\right] \\
&=\int d\mu(p)
\left[(p\!\!/+m)e^{-ip\cdot z}+(p\!\!/-m)e^{ip\cdot z}\right].
\end{aligned}
$$

The Pauli–Jordan function $\Delta(z)$ has support only on and inside the light cone as a distribution. Applying the local differential operator $(i\gamma^\mu\partial_\mu+m)$ cannot enlarge that support. Therefore the Dirac anticommutator constructed from it vanishes for spacelike $z$.

</details>

## References

### Primary references

- P. A. M. Dirac, “The Quantum Theory of the Electron,” *Proceedings of the Royal Society A* **117** (1928), for the Dirac equation.
- W. Pauli and V. Weisskopf, “Über die Quantisierung der skalaren relativistischen Wellengleichung,” *Helvetica Physica Acta* **7** (1934), for the contrast between scalar commutation and fermionic quantization.
- M. Fierz, “Über die relativistische Theorie kräftefreier Teilchen mit beliebigem Spin,” *Helvetica Physica Acta* **12** (1939), and W. Pauli, “The Connection Between Spin and Statistics,” *Physical Review* **58** (1940), for early spin-statistics results.
- E. Majorana, “Teoria simmetrica dell'elettrone e del positrone,” *Il Nuovo Cimento* **14** (1937), for the Majorana field idea.

### Standard textbook treatments

- M. Srednicki, *Quantum Field Theory*, §§36–39, for Weyl and Dirac Lagrangians, canonical anticommutators, spinor technology, and Dirac field mode quantization.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 20–21, for the Dirac equation, plane-wave spinors, canonical quantization of the Dirac field, and fermionic Wick rules.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.5 and 7.1, for causal Dirac fields, antiparticles, spin-statistics, and canonical variables.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. II.2, for a compact physics-first treatment of quantizing the Dirac field and the fermionic vacuum-energy sign.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§3.1–3.5, for the standard Dirac field quantization, spin sums, and propagator.

### For a first pass

- Zee, ch. II.2.
- Peskin and Schroeder, §§3.1–3.3.
- Coleman, ch. 21.

### For mathematical precision

- Weinberg, Vol. I, chs. 5 and 7.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for a theorem-oriented treatment of spin, statistics, and locality.
- P. Deligne et al., *Quantum Fields and Strings: A Course for Mathematicians*, Vol. I, for fermionic fields and Clifford-algebraic structures from a mathematical viewpoint.

## Version history

- **2026-05-22:** Initial qft.org page on fermionic canonical quantization, including fermionic oscillator algebra, Dirac equal-time anticommutators, mode expansion, Hamiltonian, charge, normal ordering, graded locality, Weyl and Majorana variants, pitfalls, and exercises.
