---
title: "Currents and Charges"
description: "Conserved currents, charge operators, symmetry action on fields and states, current algebra, selection rules, and the bridge to Ward identities."
sidebar:
  label: "Currents and Charges"
  order: 5
---

## Summary

A continuous global symmetry has two closely related faces.

Locally, it gives a conserved current:

$$
\partial_\mu j_a^\mu(x)=0.
$$

Globally, it gives a charge operator:

$$
\boxed{
Q_a(t)=\int_{\Sigma_t} d^3\mathbf x\,j_a^0(t,\mathbf x).
}
$$

If there is no flux through spatial infinity, the charge is time independent. Quantum mechanically, the same charge generates the symmetry on fields and states:

$$
\boxed{
\delta_a\mathcal O(x)=i[Q_a,\mathcal O(x)].
}
$$

For a field multiplet transforming as

$$
\Phi_i(x)\mapsto \Phi_i(x)-i\alpha^a(T_a)_i{}^j\Phi_j(x),
$$

our convention is

$$
\boxed{
[Q_a,\Phi_i(x)]=-(T_a)_i{}^j\Phi_j(x).
}
$$

This page turns the representation-level discussion of [Internal Symmetries](/foundations/symmetry-and-spacetime/internal-symmetries/) into operator algebra. The main lesson is that currents are local densities, while charges are Hilbert-space generators. Currents appear inside correlation functions and Ward identities. Charges act on fields, states, amplitudes, and superselection sectors.

Srednicki derives Noether currents, the complex-scalar charge, the operator identity $[\phi,Q]=i\delta\phi$, and the Ward identity with contact terms in his continuous-symmetry section (Srednicki 2007, §22). Weinberg emphasizes that the Lagrangian formalism naturally implements symmetry principles and gives conserved currents, charge operators, and current commutation relations (Weinberg 1995, Vol. I, §7.3). Coleman treats currents and charges in both spacetime and internal symmetry lectures and later uses equal-time current commutators as the engine of current algebra (Coleman 2019, chs. 5–6 and ch. 41).

<figure class="doc-figure" style="--figure-width: 50rem;">

![Currents and charges generator map](/figures/foundations/current-charge-generator-map.svg)

<figcaption>

A continuous symmetry gives a local current $j_a^\mu$. Integrating $j_a^0$ over a time slice gives a charge $Q_a$, provided boundary fluxes are under control. The charge generates the symmetry on fields and states, gives a charge algebra, imposes selection rules, and leads to Ward identities when inserted in time-ordered correlators.

</figcaption>
</figure>

## Prerequisites

You should know [Noether Theorem](/foundations/classical-field-theory/noether-theorem/), [Stress Tensor](/foundations/classical-field-theory/stress-tensor/), [Hamiltonian Field Theory](/foundations/classical-field-theory/hamiltonian-field-theory/), [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/), [Internal Symmetries](/foundations/symmetry-and-spacetime/internal-symmetries/), and [Poincaré Symmetry](/foundations/symmetry-and-spacetime/poincare-symmetry/).

:::note[Conventions]
We use the qft.org default mostly-minus metric. Lie-algebra generators are Hermitian:

$$
[T_a,T_b]=if_{ab}{}^cT_c.
$$

An infinitesimal internal symmetry is written

$$
\delta_\alpha\mathcal O=\alpha^a\Delta_a\mathcal O.
$$

The charge convention on this page is

$$
\Delta_a\mathcal O=i[Q_a,\mathcal O].
$$

For a field in representation $R$,

$$
\Delta_a\Phi_i=-i(T_a)_i{}^j\Phi_j,
\qquad
[Q_a,\Phi_i]=-(T_a)_i{}^j\Phi_j.
$$

Changing the sign convention for $Q_a$ or $T_a$ changes several displayed signs, but not the physical content.
:::

:::note[Assumptions]
The clean statements below assume an exact continuous global symmetry, a regulator or renormalization prescription that preserves it, no anomaly, no explicit time dependence in the symmetry, and boundary conditions that make surface terms vanish. Gauge symmetries, spontaneously broken symmetries, boundaries, defects, and anomalous symmetries require extra care.
:::

## Local conservation and global charge

A conserved current is a local operator $j_a^\mu(x)$ satisfying

$$
\partial_\mu j_a^\mu=0.
$$

Writing $j_a^\mu=(j_a^0,\mathbf j_a)$, this is the continuity equation

$$
\frac{\partial j_a^0}{\partial t}+\nabla\cdot\mathbf j_a=0.
$$

The charge on a constant-time slice is

$$
Q_a(t)=\int d^3\mathbf x\,j_a^0(t,\mathbf x).
$$

Taking the time derivative gives

$$
\frac{dQ_a}{dt}
=\int d^3\mathbf x\,\partial_t j_a^0
=-\int d^3\mathbf x\,\nabla\cdot\mathbf j_a
=-\oint_{S_\infty}d\mathbf S\cdot\mathbf j_a.
$$

Thus $Q_a$ is conserved if the current through spatial infinity vanishes. This is the first important caveat: **local conservation does not automatically imply global charge conservation unless the boundary behavior is controlled**.

A covariant version is useful. For a Cauchy surface $\Sigma$ with future-directed unit normal $n_\mu$,

$$
Q_a[\Sigma]=\int_\Sigma d\Sigma\,n_\mu j_a^\mu.
$$

If $\partial_\mu j_a^\mu=0$ and no current escapes through the boundary, then $Q_a[\Sigma]$ is independent of the choice of $\Sigma$. This is why the charge can be a time-independent operator on the Hilbert space.

## Noether current with parameter stripped

Let the fields be denoted collectively by $\Phi^I(x)$, where $I$ includes all species, Lorentz, spinor, and internal indices. Suppose an infinitesimal continuous transformation is

$$
\delta\Phi^I=\alpha^a\Delta_a\Phi^I,
$$

and suppose the Lagrangian changes by a total derivative,

$$
\delta\mathcal L=\alpha^a\partial_\mu K_a^\mu
$$

for constant $\alpha^a$. Then the Noether current with the parameter stripped off is

$$
\boxed{
 j_a^\mu
 =\frac{\partial\mathcal L}{\partial(\partial_\mu\Phi^I)}\Delta_a\Phi^I-K_a^\mu.
}
$$

When the equations of motion hold,

$$
\partial_\mu j_a^\mu=0.
$$

For an internal symmetry of an ordinary scalar or spinor theory, usually $K_a^\mu=0$. For spacetime symmetries, improvements, and derivative symmetries, the $K_a^\mu$ term is often essential.

The current is not unique. If $B_a^{\mu\nu}=-B_a^{\nu\mu}$, then

$$
 j_a^\mu\mapsto j_a^\mu+\partial_\nu B_a^{\mu\nu}
$$

has the same divergence because

$$
\partial_\mu\partial_\nu B_a^{\mu\nu}=0.
$$

Usually this improvement does not change the charge:

$$
\Delta Q_a=\int d^3\mathbf x\,\partial_iB_a^{0i}
=\oint_{S_\infty}dS_i\,B_a^{0i},
$$

which vanishes under standard boundary conditions. With boundaries, long-range fields, or defects, the surface term may matter. That is not pedantry; it is the seed of surface charges and edge modes.

## Charges generate transformations

In canonical quantization, Noether charges act by commutator. If

$$
U(\alpha)=e^{i\alpha^aQ_a},
$$

then a local operator transforms as

$$
U(\alpha)\mathcal O(x)U(\alpha)^{-1}
=\mathcal O(x)+i\alpha^a[Q_a,\mathcal O(x)]+O(\alpha^2).
$$

Therefore

$$
\Delta_a\mathcal O(x)=i[Q_a,\mathcal O(x)].
$$

For an internal multiplet,

$$
\Delta_a\Phi_i=-i(T_a)_i{}^j\Phi_j,
$$

so

$$
[Q_a,\Phi_i]=-(T_a)_i{}^j\Phi_j.
$$

Similarly,

$$
[Q_a,\Phi^\dagger{}^i]=\Phi^\dagger{}^j(T_a)_j{}^i
$$

for a unitary representation with Hermitian generators. The exact placement of indices depends on whether $\Phi^\dagger$ is written as a row vector or with an antifundamental index, but the invariant statement is simple: $Q_a$ acts on every operator according to its representation.

Because $j_a^0(x)$ is a local density, the unsmeared expression

$$
Q_a=\int d^3\mathbf x\,j_a^0(x)
$$

should be understood with the usual field-theory caution. Composite local operators are distributions. A safer definition first smears $j_a^0$ with a smooth function equal to one in a large region and then takes the large-region limit. In ordinary textbook examples, this refinement changes nothing. In rigorous or infrared-sensitive settings, it can be the whole story.

## Abelian example: complex scalar

For a complex scalar field with

$$
\mathcal L
=\partial_\mu\Phi^\dagger\partial^\mu\Phi
-m^2\Phi^\dagger\Phi
-V(\Phi^\dagger\Phi),
$$

the global $U(1)$ transformation is

$$
\Phi\mapsto e^{-iq\alpha}\Phi,
\qquad
\Phi^\dagger\mapsto e^{iq\alpha}\Phi^\dagger.
$$

The infinitesimal variations are

$$
\Delta\Phi=-iq\Phi,
\qquad
\Delta\Phi^\dagger=iq\Phi^\dagger.
$$

The Noether current is

$$
\boxed{
 j^\mu
 =iq\,\Phi^\dagger\overleftrightarrow{\partial^\mu}\Phi
 =iq\left(\Phi^\dagger\partial^\mu\Phi-(\partial^\mu\Phi^\dagger)\Phi\right).
}
$$

The charge is

$$
Q=\int d^3\mathbf x\,j^0.
$$

In the free quantum theory, using the mode expansion of [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/), the normal-ordered charge becomes

$$
\boxed{
Q=q\int d\mu(p)\,
\left[a^\dagger(\mathbf p)a(\mathbf p)-b^\dagger(\mathbf p)b(\mathbf p)\right],
}
$$

where the covariant on-shell measure is

$$
d\mu(p)=\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}.
$$

Thus $a^\dagger$ creates a particle of charge $+q$, while $b^\dagger$ creates an antiparticle of charge $-q$. If one uses noncovariantly normalized oscillators, the same counting formula is written with $d^3\mathbf p/(2\pi)^3$ instead. The current is local; the charge is the integrated operator that counts the global additive quantum number.

This also explains why charged correlation functions vanish. If the vacuum is neutral and $Q$ is conserved, then

$$
\langle0|\Phi(x)\Phi(y)|0\rangle=0,
$$

because the operator product carries charge $-2q$. By contrast,

$$
\langle0|T\Phi(x)\Phi^\dagger(y)|0\rangle
$$

is neutral and can be nonzero.

## Non-Abelian charges

For a field multiplet in representation $R$ of a Lie group $G$,

$$
\Phi\mapsto e^{-i\alpha^aT_a}\Phi.
$$

The charge operators satisfy

$$
[Q_a,\Phi]= -T_a\Phi.
$$

If the quantum theory realizes the same Lie algebra without anomaly, then the charges obey

$$
\boxed{
[Q_a,Q_b]=if_{ab}{}^cQ_c.
}
$$

One way to see the sign and normalization is to act on a field and use the Jacobi identity:

$$
[[Q_a,Q_b],\Phi]
=[Q_a,[Q_b,\Phi]]-[Q_b,[Q_a,\Phi]].
$$

Using $[Q_a,\Phi]=-T_a\Phi$, the right-hand side gives

$$
-[T_a,T_b]\Phi=-if_{ab}{}^cT_c\Phi.
$$

This is the same as the action of $if_{ab}{}^cQ_c$ on $\Phi$.

For a Dirac multiplet,

$$
\psi\mapsto e^{-i\alpha^aT_a}\psi,
$$

the standard internal current is

$$
\boxed{
 j_a^\mu=\bar\psi\gamma^\mu T_a\psi.
}
$$

For a complex scalar multiplet with the same convention,

$$
\boxed{
 j_a^\mu=i\Phi^\dagger T_a\overleftrightarrow{\partial^\mu}\Phi
}
$$

up to interaction-dependent terms if the Lagrangian contains derivative couplings.

## Current algebra

The integrated charges obey the Lie algebra. The local current densities satisfy a stronger, distribution-valued statement. In a simple canonical theory one expects an equal-time relation of the form

$$
[j_a^0(t,\mathbf x),j_b^0(t,\mathbf y)]
=if_{ab}{}^c j_c^0(t,\mathbf x)\delta^{(3)}(\mathbf x-\mathbf y)+\text{Schwinger terms}.
$$

The first term is the local version of the charge algebra. Integrating over $\mathbf x$ and $\mathbf y$ gives

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c
$$

if the Schwinger terms integrate to zero.

The phrase **Schwinger terms** refers to possible derivative-of-delta or central terms in equal-time current commutators. They may be harmless for the integrated algebra, or they may encode important quantum effects. Coleman makes this point in his current-algebra discussion: the delta function structure gives the charge algebra after integration, while derivative terms can disappear in the integrated charges but still matter locally (Coleman 2019, ch. 41).

This is the right attitude to current algebra in QFT: the algebra is not merely abstract group theory. It is realized by local operator distributions, and local operator distributions can carry contact terms.

## Charges on states

Let $|\psi\rangle$ be a charge eigenstate:

$$
Q_a|\psi\rangle=q_a|\psi\rangle
$$

for an Abelian charge, or a state in some representation of a non-Abelian group. If the symmetry is exact, then

$$
[Q_a,H]=0.
$$

Therefore $Q_a|\psi\rangle$ has the same energy as $|\psi\rangle$:

$$
H(Q_a|\psi\rangle)=Q_aH|\psi\rangle.
$$

For an unbroken non-Abelian symmetry, this organizes states into multiplets. Members of the same irreducible representation have the same mass when the symmetry is exact. Small explicit symmetry-breaking terms split these multiplets.

For scattering, exact global symmetry implies

$$
[Q_a,S]=0.
$$

For an Abelian charge, if

$$
Q|i\rangle=q_i|i\rangle,
\qquad
Q|f\rangle=q_f|f\rangle,
$$

then

$$
(q_f-q_i)\langle f|S|i\rangle=0.
$$

So amplitudes vanish unless the total charge is conserved:

$$
q_f=q_i.
$$

This is the cleanest form of a selection rule.

## The vacuum matters

The above statements assume that the vacuum is invariant:

$$
Q_a|0\rangle=0.
$$

If this holds, then correlation functions obey ordinary charge selection rules. A product of local operators has a nonzero vacuum expectation value only if it contains the singlet part of the tensor product of their representations.

For spontaneous symmetry breaking, the action and current may still be symmetric, but the vacuum is not invariant in the naive sense. One often says

$$
Q_a|0\rangle\ne0,
$$

but in infinite volume this can be too quick: the charge may fail to exist as an ordinary operator because the corresponding current has long-range matrix elements associated with Goldstone modes. The robust statement is that the symmetry is not implemented by a unitary operator that leaves the chosen vacuum fixed.

This subtlety is not an optional advanced flourish. It is why the same current algebra can lead either to degenerate multiplets or to Goldstone bosons, depending on how the vacuum represents the symmetry.

## Current insertions and Ward identities

Current conservation inside time-ordered correlation functions is not simply

$$
\partial_\mu\langle0|Tj_a^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)|0\rangle=0.
$$

The derivative also acts on the time-ordering step functions. The result contains contact terms at the operator insertions:

$$
\boxed{
\partial_\mu\langle0|Tj_a^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)|0\rangle
=-i\sum_{r=1}^n\delta^{(4)}(x-x_r)
\langle0|T\mathcal O_1\cdots(\Delta_a\mathcal O_r)\cdots\mathcal O_n|0\rangle.
}
$$

This is the operator form of a Ward identity. The next page, [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/), develops this systematically from both the operator and path-integral viewpoints.

The path-integral version says the same thing in different clothes. If the action and measure are invariant under a change of variables, then the generating functional is unchanged. Localizing the symmetry parameter produces an insertion of $\partial_\mu j_a^\mu$, while variations of the inserted operators produce the contact terms. If the measure is not invariant, an anomaly term appears.

## Explicit breaking and partial conservation

If the Lagrangian contains a small term that breaks the symmetry, the current is no longer conserved. Instead,

$$
\partial_\mu j_a^\mu=\mathcal B_a,
$$

where $\mathcal B_a$ is the breaking operator. Then

$$
\frac{dQ_a}{dt}=\int d^3\mathbf x\,\mathcal B_a
$$

up to boundary flux.

This is the operator reason approximate symmetries are useful. If $\mathcal B_a$ is small in an appropriate sense, the charge is slowly varying or approximately conserved, and the selection rules are approximate.

The famous partially conserved axial current idea has this shape:

$$
\partial_\mu A^{\mu a}\propto m_\pi^2\pi^a.
$$

In the chiral limit $m_\pi\to0$, the axial current becomes conserved. Away from that limit, it is not exactly conserved but remains powerful because the breaking is controlled.

## Global charges versus gauge constraints

A global symmetry maps one physical state to another physical state. Its charge is a physical operator, and nonzero eigenvalues label charge sectors.

A gauge symmetry is different. Gauge transformations are redundancies of description. The generators of infinitesimal gauge transformations act as constraints on physical states, not as ordinary global charges rotating physical states into distinct physical states.

For electromagnetism and Yang–Mills theory, the situation is subtler still because global transformations at infinity can define genuine physical charges. Electric charge is not just the volume integral of a matter density; by Gauss's law it is also a surface flux at infinity. That story belongs to [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) and [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/), but the warning belongs here:

```txt
Do not confuse a global symmetry charge with a gauge redundancy generator.
```

## Renormalized currents

In an interacting quantum theory, a current is a composite operator and usually needs renormalization. The classical Noether expression is the starting point, not always the final renormalized operator.

For an exact non-anomalous symmetry, there is a renormalized current whose divergence vanishes inside correlation functions up to contact terms. For an anomalous symmetry, no regulator preserves all desired symmetries, and the divergence equation is modified:

$$
\partial_\mu j_a^\mu=\mathcal A_a.
$$

Here $\mathcal A_a$ is the anomaly operator. This is why the page [Path-Integral Measure](/foundations/path-integral-formalism/path-integral-measure/) emphasized that invariance of the action is not enough; the measure matters too.

## Operator, path-integral, and structural views

The three standard languages say the same thing in complementary ways.

| Viewpoint | Statement |
| --- | --- |
| Operator | $Q_a=\int d^3x\,j_a^0$ and $\Delta_a\mathcal O=i[Q_a,\mathcal O]$. |
| Path integral | Localizing a change of variables produces current insertions and contact terms. |
| Structural | Exact charges classify sectors, multiplets, selection rules, and possible anomalies. |

A trustworthy QFT calculation keeps all three visible. The current gives locality; the charge gives representation theory; the Ward identity gives correlation-function constraints.

## Common pitfalls

### Treating the current as unique

Noether currents are defined up to improvements. Local formulas can differ while giving the same integrated charge under ordinary boundary conditions.

### Forgetting boundary flux

The step

$$
\frac{dQ}{dt}=0
$$

requires the surface integral at infinity to vanish. Long-range fields, massless modes, boundaries, and topological sectors can invalidate the quick textbook argument.

### Confusing current conservation with Ward identities

Inside time-ordered correlation functions, current conservation becomes a contact-term identity. Dropping the contact terms loses the actual symmetry action on operator insertions.

### Confusing global and gauge symmetry

A global charge labels physical states. A gauge generator usually imposes a redundancy constraint. Boundary symmetries and asymptotic charges are real, but they require their own treatment.

### Ignoring anomalies

A symmetry of the classical action may fail as a quantum symmetry if the regulator or path-integral measure does not preserve it. Then the current divergence is modified.

### Assuming broken charges behave like ordinary operators

In spontaneous symmetry breaking, the current is still central, but the charge may not exist as a normal Hilbert-space operator in infinite volume. Goldstone modes carry the infrared subtlety.

## Relations to nearby pages

- [Internal Symmetries](/foundations/symmetry-and-spacetime/internal-symmetries/) explains field multiplets, representation matrices, invariant tensors, and selection rules before introducing currents.
- [Noether Theorem](/foundations/classical-field-theory/noether-theorem/) derives conserved currents from classical variational symmetry.
- [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/) computes the simplest charge-counting operator explicitly.
- [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) turns current conservation into constraints on correlation functions and amplitudes.
- [Path-Integral Measure](/foundations/path-integral-formalism/path-integral-measure/) explains how Jacobians and anomalies can modify current conservation.
- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) will separate physical global charges from gauge constraints.

## Exercises

### Exercise 1: Charge conservation from local conservation

Assume

$$
\partial_t j^0+\nabla\cdot\mathbf j=0.
$$

Define

$$
Q(t)=\int d^3\mathbf x\,j^0(t,\mathbf x).
$$

Show that

$$
\frac{dQ}{dt}=-\oint_{S_\infty}d\mathbf S\cdot\mathbf j.
$$

When is $Q$ conserved?

<details>
<summary><strong>Solution</strong></summary>

Differentiate under the integral:

$$
\frac{dQ}{dt}=\int d^3\mathbf x\,\partial_t j^0.
$$

Use the continuity equation:

$$
\frac{dQ}{dt}=-\int d^3\mathbf x\,\nabla\cdot\mathbf j.
$$

Gauss's theorem gives

$$
\frac{dQ}{dt}=-\oint_{S_\infty}d\mathbf S\cdot\mathbf j.
$$

Thus $Q$ is conserved when the flux through spatial infinity vanishes. This is usually true for localized massive configurations, but it must be checked in theories with boundaries, long-range fields, or massless radiation.

</details>

### Exercise 2: Complex scalar current

For

$$
\mathcal L=\partial_\mu\Phi^\dagger\partial^\mu\Phi-m^2\Phi^\dagger\Phi
$$

and

$$
\Delta\Phi=-iq\Phi,
\qquad
\Delta\Phi^\dagger=iq\Phi^\dagger,
$$

derive the Noether current.

<details>
<summary><strong>Solution</strong></summary>

Treat $\Phi$ and $\Phi^\dagger$ as independent fields. The current is

$$
j^\mu
=\frac{\partial\mathcal L}{\partial(\partial_\mu\Phi)}\Delta\Phi
+\frac{\partial\mathcal L}{\partial(\partial_\mu\Phi^\dagger)}\Delta\Phi^\dagger.
$$

Since

$$
\frac{\partial\mathcal L}{\partial(\partial_\mu\Phi)}=\partial^\mu\Phi^\dagger,
\qquad
\frac{\partial\mathcal L}{\partial(\partial_\mu\Phi^\dagger)}=\partial^\mu\Phi,
$$

we get

$$
j^\mu
=(\partial^\mu\Phi^\dagger)(-iq\Phi)
+(\partial^\mu\Phi)(iq\Phi^\dagger).
$$

Therefore

$$
\boxed{
j^\mu=iq\left(\Phi^\dagger\partial^\mu\Phi-(\partial^\mu\Phi^\dagger)\Phi\right)
=iq\,\Phi^\dagger\overleftrightarrow{\partial^\mu}\Phi.
}
$$

</details>

### Exercise 3: Charge action on a complex scalar

Suppose the equal-time canonical commutators are

$$
[\Phi(t,\mathbf x),\Pi_\Phi(t,\mathbf y)]=i\delta^{(3)}(\mathbf x-\mathbf y),
$$

$$
[\Phi^\dagger(t,\mathbf x),\Pi_{\Phi^\dagger}(t,\mathbf y)]=i\delta^{(3)}(\mathbf x-\mathbf y),
$$

with

$$
\Pi_\Phi=\dot\Phi^\dagger,
\qquad
\Pi_{\Phi^\dagger}=\dot\Phi.
$$

Using the charge from Exercise 2, show that

$$
[Q,\Phi]=-q\Phi.
$$

<details>
<summary><strong>Solution</strong></summary>

The charge density is

$$
j^0=iq(\Phi^\dagger\dot\Phi-\dot\Phi^\dagger\Phi)
=iq(\Phi^\dagger\Pi_{\Phi^\dagger}-\Pi_\Phi\Phi).
$$

Thus

$$
Q=iq\int d^3\mathbf y\,
\left(\Phi^\dagger\Pi_{\Phi^\dagger}-\Pi_\Phi\Phi\right)(t,\mathbf y).
$$

The first term commutes with $\Phi(t,\mathbf x)$. The second term gives

$$
[Q,\Phi(t,\mathbf x)]
=-iq\int d^3\mathbf y\,[\Pi_\Phi(t,\mathbf y)\Phi(t,\mathbf y),\Phi(t,\mathbf x)].
$$

Using

$$
[\Pi_\Phi(t,\mathbf y),\Phi(t,\mathbf x)]
=-i\delta^{(3)}(\mathbf x-\mathbf y),
$$

we find

$$
[Q,\Phi(t,\mathbf x)]
=-iq\int d^3\mathbf y\,[-i\delta^{(3)}(\mathbf x-\mathbf y)]\Phi(t,\mathbf y)
=-q\Phi(t,\mathbf x).
$$

Therefore

$$
\boxed{[Q,\Phi]=-q\Phi.}
$$

Then

$$
i[Q,\Phi]=-iq\Phi,
$$

which is exactly the infinitesimal transformation $\Delta\Phi=-iq\Phi$.

</details>

### Exercise 4: Selection rule from charge conservation

Let $Q$ be an exact Abelian charge with

$$
[Q,S]=0.
$$

If

$$
Q|i\rangle=q_i|i\rangle,
\qquad
Q|f\rangle=q_f|f\rangle,
$$

show that $\langle f|S|i\rangle=0$ unless $q_f=q_i$.

<details>
<summary><strong>Solution</strong></summary>

Start with

$$
\langle f|QS|i\rangle=\langle f|SQ|i\rangle.
$$

Use the charge eigenvalue equations:

$$
q_f\langle f|S|i\rangle=q_i\langle f|S|i\rangle.
$$

Therefore

$$
(q_f-q_i)\langle f|S|i\rangle=0.
$$

If $q_f\ne q_i$, then

$$
\boxed{\langle f|S|i\rangle=0.}
$$

</details>

### Exercise 5: Improvement terms and charges

Let

$$
j^\mu\mapsto j'^\mu=j^\mu+\partial_\nu B^{\mu\nu},
\qquad
B^{\mu\nu}=-B^{\nu\mu}.
$$

Show that $\partial_\mu j'^\mu=\partial_\mu j^\mu$. Then show that the charge changes only by a surface term.

<details>
<summary><strong>Solution</strong></summary>

The divergence changes by

$$
\partial_\mu\partial_\nu B^{\mu\nu}.
$$

Because $\partial_\mu\partial_\nu$ is symmetric in $\mu,\nu$, while $B^{\mu\nu}$ is antisymmetric,

$$
\partial_\mu\partial_\nu B^{\mu\nu}=0.
$$

Thus

$$
\partial_\mu j'^\mu=\partial_\mu j^\mu.
$$

The charge changes by

$$
\Delta Q=\int d^3\mathbf x\,\partial_\nu B^{0\nu}.
$$

Since $B^{00}=0$ by antisymmetry,

$$
\Delta Q=\int d^3\mathbf x\,\partial_iB^{0i}
=\oint_{S_\infty}dS_i\,B^{0i}.
$$

So the improvement does not change the charge if the surface term vanishes.

</details>

### Exercise 6: Non-Abelian charge algebra from field transformations

Assume

$$
[Q_a,\Phi]=-T_a\Phi,
\qquad
[T_a,T_b]=if_{ab}{}^cT_c.
$$

Show that the commutator $[Q_a,Q_b]$ acts on $\Phi$ like $if_{ab}{}^cQ_c$.

<details>
<summary><strong>Solution</strong></summary>

Use the Jacobi identity in the form

$$
[[Q_a,Q_b],\Phi]
=[Q_a,[Q_b,\Phi]]-[Q_b,[Q_a,\Phi]].
$$

Since $[Q_b,\Phi]=-T_b\Phi$,

$$
[Q_a,[Q_b,\Phi]]
=-T_b[Q_a,\Phi]
=T_bT_a\Phi.
$$

Similarly,

$$
[Q_b,[Q_a,\Phi]]=T_aT_b\Phi.
$$

Therefore

$$
[[Q_a,Q_b],\Phi]
=(T_bT_a-T_aT_b)\Phi
=-[T_a,T_b]\Phi.
$$

Using the Lie algebra,

$$
[[Q_a,Q_b],\Phi]
=-if_{ab}{}^cT_c\Phi.
$$

But

$$
[if_{ab}{}^cQ_c,\Phi]
=if_{ab}{}^c[Q_c,\Phi]
=if_{ab}{}^c(-T_c\Phi)
=-if_{ab}{}^cT_c\Phi.
$$

Thus $[Q_a,Q_b]$ and $if_{ab}{}^cQ_c$ act identically on the field multiplet. Under the usual assumption that there are no extra central operators acting trivially on all fields,

$$
\boxed{[Q_a,Q_b]=if_{ab}{}^cQ_c.}
$$

</details>

## Sources and further reading

- E. Noether, “Invariante Variationsprobleme,” *Nachrichten von der Gesellschaft der Wissenschaften zu Göttingen* (1918), for the original theorem connecting continuous variational symmetries and conservation laws.
- M. Srednicki, *Quantum Field Theory*, §22, for continuous symmetries, Noether currents, charge operators, and Ward identities with contact terms.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 5–6, for conserved currents, charge operators, internal symmetries, and Lorentz properties of charges.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 40–42, for current algebra, equal-time current commutators, and PCAC applications.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §7.3, for the canonical formalism, global symmetries, conserved currents, quantum symmetry generators, and current commutation relations.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, ch. 19, for vector and axial charges, chiral algebras, and spontaneously broken global symmetries.
- S. Treiman, R. Jackiw, D. Gross, *Lectures on Current Algebra and Its Applications*, for classic current-algebra methods.
- S. Treiman, R. Jackiw, B. Zumino, E. Witten, *Current Algebra and Anomalies*, for the deeper relation between current algebra, Schwinger terms, and anomalies.

## Version history

- **2026-05-23:** Initial qft.org page on conserved currents, charge operators, symmetry generation, current algebra, selection rules, Ward-identity contact terms, explicit breaking, global-versus-gauge caveats, and renormalized currents.
