---
title: "Proca Field"
description: "The free massive spin-one field: Proca Lagrangian, equations of motion, transversality constraint, three polarizations, mode expansion, propagator, conserved-current coupling, and the subtle massless limit."
sidebar:
  label: "Proca Field"
  order: 6
---

## Summary

The Proca field is the free massive spin-one field. It is described by a real Lorentz vector field $A_\mu(x)$ with Lagrangian

$$
\boxed{
\mathcal L_\text{Proca}
=-\frac14F_{\mu\nu}F^{\mu\nu}
+\frac12m^2A_\mu A^\mu,
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
}
$$

The field equation is

$$
\boxed{
\partial_\mu F^{\mu\nu}+m^2A^\nu=0.
}
$$

Taking the divergence gives the transversality constraint

$$
\boxed{\partial_\mu A^\mu=0\qquad(m\neq0).}
$$

With this constraint, every component satisfies the Klein–Gordon equation,

$$
\boxed{(\Box+m^2)A^\mu=0.}
$$

A massive vector particle has three physical polarizations. For on-shell momentum $p^2=m^2$, choose polarization vectors $\varepsilon_\lambda^\mu(p)$, with $\lambda=1,2,3$, satisfying

$$
p_\mu\varepsilon_\lambda^\mu(p)=0,
\qquad
\varepsilon_\lambda^*(p)\cdot\varepsilon_{\lambda'}(p)=-\delta_{\lambda\lambda'}.
$$

Their completeness relation is

$$
\boxed{
\sum_{\lambda=1}^3
\varepsilon_\lambda^\mu(p)\varepsilon_\lambda^{\nu*}(p)
=-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}.
}
$$

The Feynman propagator is

$$
\boxed{
D_F^{\mu\nu}(p)
=\frac{-i}{p^2-m^2+i\epsilon}
\left(\eta^{\mu\nu}-\frac{p^\mu p^\nu}{m^2}\right).
}
$$

Coleman gives a detailed treatment of the Proca equation, its three polarization vectors, canonical quantization, completeness relation, propagator, and massless limit; Zee presents the same massive-vector propagator and polarization logic in the context of a massive vector coupled to a Dirac field; Weinberg treats massive vector fields as causal spin-one fields and contrasts them with massless gauge fields (Coleman 2019, ch. 26; Zee 2010, ch. II.5; Weinberg 1995, Vol. I, §§5.3, 6.2, 7.1, and 8.1).

## Prerequisites

You should know [Maxwell Field](/foundations/free-fields/maxwell-field/), [Constraints](/foundations/classical-field-theory/constraints/), [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/), [Canonical Commutation Relations](/foundations/canonical-quantization/canonical-commutation-relations/), [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), and [Conventions and Normalizations](/foundations/conventions-and-normalizations/). We use the mostly-minus metric and the scalar propagator denominator $p^2-m^2+i\epsilon$.

## Core idea

The Proca field is the clean comparison case for the photon. It is a Lorentz vector field, but unlike the Maxwell potential it is not gauge-redundant. The mass term makes the longitudinal spin-one polarization physical.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Proca field constraint and three physical spin-one polarizations](/figures/foundations/proca-polarizations.svg)

<figcaption>

The Proca mass term removes gauge redundancy. The equation of motion implies the constraint $\partial\cdot A=0$, leaving three physical massive spin-one polarizations: two transverse modes and one longitudinal mode. In the massless limit the longitudinal polarization behaves like $p^\mu/m$, so the limit is smooth only in special contexts, such as conserved-current exchange.

</figcaption>
</figure>

The key contrast is this:

| Theory | Gauge redundancy? | Constraint | Physical polarizations |
| --- | --- | --- | ---: |
| Maxwell | yes | gauge plus Gauss law | 2 |
| Proca | no | dynamical transversality | 3 |

Both use the same antisymmetric field strength $F_{\mu\nu}$. The mass term changes the constraint structure.

:::note[Assumptions]
This page treats a free real massive vector field in flat Minkowski spacetime. Couplings to matter are discussed only as a diagnostic for the massless limit and propagator numerator. Non-Abelian massive vector bosons, Higgs mechanisms, Stückelberg fields, and BRST quantization belong in later gauge-theory pages.
:::

## Lagrangian and equation of motion

The Proca action is

$$
S[A]=\int d^4x\left(
-\frac14F_{\mu\nu}F^{\mu\nu}
+\frac12m^2A_\mu A^\mu
\right).
$$

Varying $A_\mu$ gives

$$
\delta S
=\int d^4x\left(\partial_\mu F^{\mu\nu}+m^2A^\nu\right)\delta A_\nu
+\text{boundary term}.
$$

Therefore

$$
\partial_\mu F^{\mu\nu}+m^2A^\nu=0.
$$

Writing out $F^{\mu\nu}$,

$$
\partial_\mu F^{\mu\nu}
=\partial_\mu(\partial^\mu A^\nu-\partial^\nu A^\mu)
=\Box A^\nu-\partial^\nu(\partial\cdot A).
$$

So the equation is

$$
\Box A^\nu-\partial^\nu(\partial\cdot A)+m^2A^\nu=0.
$$

Taking $\partial_\nu$ of the Proca equation gives

$$
\partial_\nu\partial_\mu F^{\mu\nu}+m^2\partial_\nu A^\nu=0.
$$

The first term vanishes because $F^{\mu\nu}$ is antisymmetric, while $\partial_\nu\partial_\mu$ is symmetric. For $m\neq0$,

$$
\partial_\nu A^\nu=0.
$$

Substituting this back into the equation of motion gives

$$
(\Box+m^2)A^\nu=0.
$$

The transversality condition is not a gauge choice. It is a consequence of the equation of motion when $m\neq0$.

## Degrees of freedom

The field $A_\mu$ has four components. The Proca equation implies one constraint,

$$
\partial_\mu A^\mu=0.
$$

That leaves three physical degrees of freedom. These are the three spin states of a massive spin-one particle.

In momentum space, with

$$
A^\mu(x)=\varepsilon^\mu(p)e^{-ip\cdot x},
$$

the transversality condition becomes

$$
p_\mu\varepsilon^\mu(p)=0.
$$

In the rest frame,

$$
p^\mu=(m,0,0,0),
$$

so transversality gives

$$
\varepsilon^0=0.
$$

The three independent polarizations are purely spatial. A convenient rest-frame basis is

$$
\varepsilon_1^\mu=(0,1,0,0),
\qquad
\varepsilon_2^\mu=(0,0,1,0),
\qquad
\varepsilon_3^\mu=(0,0,0,1).
$$

These are the ordinary spin-one polarization states in the rest frame. In a boosted frame, one linear combination becomes the longitudinal polarization.

## Polarization vectors

For an on-shell massive momentum

$$
p^\mu=(E_{\mathbf p},\mathbf p),
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2},
$$

choose three polarization vectors satisfying

$$
p\cdot\varepsilon_\lambda=0,
\qquad
\varepsilon_\lambda^*\cdot\varepsilon_{\lambda'}=-\delta_{\lambda\lambda'}.
$$

If $\mathbf p$ points along the $z$-axis,

$$
p^\mu=(E,0,0,k),
\qquad
E^2-k^2=m^2.
$$

A useful basis is

$$
\varepsilon_1^\mu=(0,1,0,0),
\qquad
\varepsilon_2^\mu=(0,0,1,0),
$$

and

$$
\varepsilon_L^\mu=\frac{1}{m}(k,0,0,E).
$$

Check transversality:

$$
p\cdot\varepsilon_L=\frac{1}{m}(Ek-kE)=0.
$$

Check normalization:

$$
\varepsilon_L\cdot\varepsilon_L
=\frac{k^2-E^2}{m^2}=-1.
$$

The longitudinal polarization is physical for a massive vector field. It is not a gauge artifact.

## Completeness relation

The three polarization vectors span the subspace orthogonal to $p^\mu$. The Lorentz-covariant projector onto this subspace is

$$
P^{\mu\nu}(p)=-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}.
$$

It is transverse:

$$
p_\mu P^{\mu\nu}=0,
$$

using $p^2=m^2$. It acts as the identity on spacelike polarization vectors in the sign convention appropriate to mostly-minus metric. Therefore

$$
\sum_{\lambda=1}^3
\varepsilon_\lambda^\mu(p)\varepsilon_\lambda^{\nu*}(p)
=-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}.
$$

This is the spin-one analogue of the spinor completeness relations

$$
\sum_s u_s(p)\overline u_s(p)=p\!\!/+m,
\qquad
\sum_s v_s(p)\overline v_s(p)=p\!\!/-m.
$$

It is the numerator structure that appears when one sums over external massive-vector polarizations.

## Mode expansion

The free real Proca field has the mode expansion

$$
A^\mu(x)=\sum_{\lambda=1}^3\int d\mu(p)
\left[
\varepsilon_\lambda^\mu(p)a_\lambda(\mathbf p)e^{-ip\cdot x}
+\varepsilon_\lambda^{\mu*}(p)a_\lambda^\dagger(\mathbf p)e^{ip\cdot x}
\right],
$$

where

$$
d\mu(p)=\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}.
$$

The relativistically normalized oscillator algebra is

$$
[a_\lambda(\mathbf p),a_{\lambda'}^\dagger(\mathbf q)]
=(2\pi)^3 2E_{\mathbf p}\delta_{\lambda\lambda'}\delta^{(3)}(\mathbf p-\mathbf q),
$$

with all other commutators zero.

The one-particle states are

$$
|\mathbf p,\lambda\rangle
=a_\lambda^\dagger(\mathbf p)|0\rangle,
$$

and satisfy

$$
\langle \mathbf q,\lambda'|\mathbf p,\lambda\rangle
=(2\pi)^3 2E_{\mathbf p}\delta_{\lambda\lambda'}\delta^{(3)}(\mathbf p-\mathbf q).
$$

The free Hamiltonian is

$$
H=\sum_{\lambda=1}^3\int d\mu(p)\,E_{\mathbf p}
\,a_\lambda^\dagger(\mathbf p)a_\lambda(\mathbf p)
+E_0,
$$

where $E_0$ is the zero-point energy. As usual, normal ordering subtracts $E_0$ in flat-space scattering calculations.

## Canonical structure

The Proca field is constrained, but not gauge-redundant. The canonical momentum conjugate to $A_i$ is related to $F^{0i}$, while the momentum conjugate to $A_0$ vanishes. This looks similar to Maxwell theory at first glance, but the interpretation is different.

For Maxwell theory, the constraints are first class and generate gauge redundancy. For Proca theory, the mass term converts the constraint structure into a second-class system. There is no gauge freedom left: the constraint removes a nondynamical component rather than identifying gauge-equivalent configurations.

The equation with $\nu=0$ is not an independent wave equation for a fourth oscillator. In components it determines $A^0$ in terms of the spatial fields and their momenta. Equivalently, the covariant constraint

$$
\partial\cdot A=0
$$

removes one of the four components.

This is why the Proca field has exactly three physical polarizations.

## Propagator

The Proca propagator is the inverse of the quadratic kinetic operator on the constrained vector field. In qft.org conventions,

$$
\boxed{
D_F^{\mu\nu}(p)
=\frac{-i}{p^2-m^2+i\epsilon}
\left(\eta^{\mu\nu}-\frac{p^\mu p^\nu}{m^2}\right).
}
$$

Equivalently,

$$
D_F^{\mu\nu}(p)
=\frac{i}{p^2-m^2+i\epsilon}
\left(-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}\right).
$$

The numerator is the massive spin-one polarization sum continued off shell. On shell it matches

$$
\sum_{\lambda=1}^3
\varepsilon_\lambda^\mu(p)\varepsilon_\lambda^{\nu*}(p).
$$

The term $p^\mu p^\nu/m^2$ is the signature of the longitudinal polarization. It also announces the subtlety of the massless limit.

## Coupling to a current

Couple the Proca field to a current by

$$
\mathcal L_\text{int}=-j_\mu A^\mu.
$$

The equation of motion becomes

$$
\partial_\mu F^{\mu\nu}+m^2A^\nu=j^\nu.
$$

Taking the divergence gives

$$
m^2\partial_\nu A^\nu=\partial_\nu j^\nu.
$$

For a conserved current,

$$
\partial_\nu j^\nu=0,
$$

we recover

$$
\partial_\nu A^\nu=0.
$$

For a nonconserved current, the longitudinal component is sourced. This is not automatically inconsistent for a massive vector effective theory, but it is dangerous: amplitudes involving the longitudinal mode can grow with energy, and the massless limit is singular.

For conserved currents, the tree-level exchange amplitude contains

$$
j_\mu(p)D_F^{\mu\nu}(p)j'_\nu(-p).
$$

The longitudinal part gives

$$
j_\mu(p)\frac{p^\mu p^\nu}{m^2}j'_\nu(-p),
$$

which vanishes if

$$
p_\mu j^\mu(p)=0,
\qquad
p_\nu j'^\nu(-p)=0.
$$

This explains why massive-vector exchange coupled to conserved currents can have a smoother small-mass behavior than the propagator itself suggests.

## The massless limit

It is tempting to set $m=0$ in Proca theory and declare victory. That is not the right way to think.

The Proca propagator contains

$$
\frac{p^\mu p^\nu}{m^2},
$$

which is singular as $m\to0$. The longitudinal polarization for momentum along $z$ is

$$
\varepsilon_L^\mu=\frac{1}{m}(k,0,0,E).
$$

At high energy or small mass,

$$
\varepsilon_L^\mu\sim\frac{p^\mu}{m}
$$

up to terms that remain finite. This is why longitudinal massive vector bosons are so important in electroweak theory and why gauge-invariant UV completions require care.

The Maxwell theory is not simply "Proca with $m=0$". At $m=0$, a new gauge redundancy appears:

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

That redundancy removes the longitudinal mode and leaves two photon helicities.

The smoothest statement is this:

- a massive spin-one particle has three physical polarizations;
- a massless helicity-one particle has two physical helicities;
- conserved currents can make some Proca amplitudes approach Maxwell-like amplitudes as $m\to0$;
- the field-theoretic constraint and gauge structure nevertheless changes discontinuously.

## Relation to the Higgs mechanism

The Proca Lagrangian is a perfectly good free massive spin-one theory. As an interacting fundamental theory, however, a bare vector mass often signals missing structure. In gauge theories, massive vector bosons arise consistently through gauge symmetry plus spontaneous symmetry breaking. In that setting the longitudinal polarization is supplied by what would have been a Goldstone mode.

That later story should not be imported too early. The Proca page has a simpler job: understand the free massive vector field and its three polarizations. The Higgs mechanism explains how such fields can arise in a gauge-invariant interacting theory.

## Common pitfalls

**Pitfall 1: Calling the Proca constraint a gauge choice.** The condition $\partial\cdot A=0$ follows from the equations of motion for $m\neq0$. It is not a freely imposed gauge condition.

**Pitfall 2: Counting four spin states.** A massive vector field has four components, but one constraint. It describes three physical polarizations.

**Pitfall 3: Erasing the longitudinal mode.** The longitudinal polarization is a real physical state for a massive spin-one particle.

**Pitfall 4: Taking the massless limit too casually.** The $p^\mu p^\nu/m^2$ term and $\varepsilon_L^\mu\sim p^\mu/m$ show that the limit is singular before current conservation or gauge structure is used.

**Pitfall 5: Confusing Proca and Maxwell quantization.** Both have $A_0$ as a nondynamical variable, but Maxwell has gauge redundancy while Proca has second-class constraints.

## Relation to other pages

- [Maxwell Field](/foundations/free-fields/maxwell-field/) is the massless gauge-field comparison.
- [Polarizations](/foundations/free-fields/polarizations/) will systematize massive and massless polarization vectors and spin sums.
- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) will explain why Maxwell's gauge symmetry is not an ordinary physical symmetry.
- [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/) will compare first-class constraints, gauge conditions, and covariant propagators.
- The [Sigma Model Preview](/foundations/foundational-models/sigma-model-preview/) and later gauge-theory pages explain how symmetry breaking can give masses to collective modes and gauge bosons without treating the Proca mass term as fundamental.

## Research status

The free Proca field is textbook-standard. Its role in interacting theories is more nuanced: massive vector effective theories have limited regimes of validity unless embedded in a gauge-invariant or otherwise consistent high-energy completion. That issue belongs to gauge theory, EFT, and the Higgs mechanism, not to the free-field formulas collected here.

## Exercises

### Exercise 1

Derive the Proca equation from

$$
\mathcal L=-\frac14F_{\mu\nu}F^{\mu\nu}+\frac12m^2A_\mu A^\mu.
$$

### Exercise 2

Show that the Proca equation implies $\partial_\mu A^\mu=0$ for $m\neq0$.

### Exercise 3

Show that, after imposing $\partial\cdot A=0$, each component of $A^\mu$ satisfies the Klein–Gordon equation.

### Exercise 4

For $p^\mu=(E,0,0,k)$, verify that

$$
\varepsilon_L^\mu=\frac{1}{m}(k,0,0,E)
$$

is transverse and normalized to $-1$.

### Exercise 5

Verify that

$$
P^{\mu\nu}(p)=-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}
$$

is transverse on shell, meaning $p_\mu P^{\mu\nu}=0$ when $p^2=m^2$.

### Exercise 6

Show that the longitudinal part of the Proca propagator does not contribute to exchange between two conserved currents.

## Solutions

### Solution 1

The variation of the field strength is

$$
\delta F_{\mu\nu}=\partial_\mu\delta A_\nu-\partial_\nu\delta A_\mu.
$$

Thus

$$
\delta\left(-\frac14F_{\mu\nu}F^{\mu\nu}\right)
=-\frac12F^{\mu\nu}\delta F_{\mu\nu}
=-F^{\mu\nu}\partial_\mu\delta A_\nu.
$$

Integrating by parts gives

$$
\delta S_\text{kin}
=\int d^4x\,(\partial_\mu F^{\mu\nu})\delta A_\nu.
$$

The mass term varies as

$$
\delta S_\text{mass}
=\int d^4x\,m^2A^\nu\delta A_\nu.
$$

Therefore

$$
\delta S
=\int d^4x\,(\partial_\mu F^{\mu\nu}+m^2A^\nu)\delta A_\nu.
$$

Stationarity gives

$$
\partial_\mu F^{\mu\nu}+m^2A^\nu=0.
$$

### Solution 2

Take the divergence:

$$
\partial_\nu\partial_\mu F^{\mu\nu}+m^2\partial_\nu A^\nu=0.
$$

Because $F^{\mu\nu}$ is antisymmetric and $\partial_\nu\partial_\mu$ is symmetric,

$$
\partial_\nu\partial_\mu F^{\mu\nu}=0.
$$

Therefore

$$
m^2\partial_\nu A^\nu=0.
$$

For $m\neq0$,

$$
\partial_\nu A^\nu=0.
$$

### Solution 3

Expand the equation of motion:

$$
\partial_\mu F^{\mu\nu}+m^2A^\nu
=\Box A^\nu-\partial^\nu(\partial\cdot A)+m^2A^\nu=0.
$$

Using $\partial\cdot A=0$, this becomes

$$
(\Box+m^2)A^\nu=0.
$$

### Solution 4

With mostly-minus metric,

$$
p\cdot\varepsilon_L
=\frac{1}{m}(Ek-kE)=0.
$$

The norm is

$$
\varepsilon_L\cdot\varepsilon_L
=\frac{k^2-E^2}{m^2}.
$$

Since $E^2-k^2=m^2$,

$$
\varepsilon_L\cdot\varepsilon_L=-1.
$$

### Solution 5

Compute

$$
p_\mu P^{\mu\nu}
=p_\mu\left(-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}\right)
=-p^\nu+\frac{p^2p^\nu}{m^2}.
$$

On shell, $p^2=m^2$, so

$$
p_\mu P^{\mu\nu}=-p^\nu+p^\nu=0.
$$

### Solution 6

The propagator numerator contains the longitudinal term

$$
\frac{p^\mu p^\nu}{m^2}.
$$

Inserted between two currents, it contributes

$$
j_\mu(p)\frac{p^\mu p^\nu}{m^2}j'_\nu(-p)
=\frac{(p\cdot j)(p\cdot j')}{m^2}.
$$

For conserved currents,

$$
p\cdot j=0,
\qquad
p\cdot j'=0.
$$

Therefore this contribution vanishes.

## Sources and further reading

### Primary references

- A. Proca, "Sur la théorie ondulatoire des électrons positifs et négatifs," *Journal de Physique et le Radium* **7** (1936) 347–353.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 26.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.3, 6.2, 7.1, and 8.1.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. II.5.
- M. Srednicki, *Quantum Field Theory*, especially the massive-vector discussion in the Abelian Higgs context, §85.

### For a first pass

- L. Ryder, *Quantum Field Theory*, for a conventional introductory treatment of massive vector fields.

### For mathematical precision

- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*, for constrained Hamiltonian systems.
- C. Itzykson and J.-B. Zuber, *Quantum Field Theory*, for covariant propagators and spin-one field conventions.
