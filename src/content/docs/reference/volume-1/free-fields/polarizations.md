---
title: "Polarizations"
description: "Polarization vectors, spinor spin sums, helicity bases, little groups, and the projector formulas used for free scalar, spinor, Maxwell, and Proca fields."
sidebar:
  label: "Polarizations"
  order: 7
---

## Summary

A polarization is the extra finite-dimensional data carried by a one-particle state after its momentum has been specified. For a scalar particle there is no extra label. For a massive spin-one-half particle there are two spin states. For a massive spin-one particle there are three vector polarizations. For a massless photon there are only two physical helicities, even though the vector potential has four components.

The clean way to organize this is by the **little group** of a standard momentum:

| Momentum type | Standard momentum | Little group | Physical labels |
|---|---|---|---|
| massive | $p^\mu=(m,0,0,0)$ | $SO(3)$ | spin multiplet $m_s=-s,\ldots,s$ |
| massless | $k^\mu=(\omega,0,0,\omega)$ | $ISO(2)$ | helicity $\lambda$ |

For the free fields already introduced, the main completeness relations are

$$
\boxed{\sum_s u_s(p)\overline u_s(p)=p\!\!/+m,}
\qquad
\boxed{\sum_s v_s(p)\overline v_s(p)=p\!\!/-m,}
$$

for Dirac spinors, and

$$
\boxed{
\sum_{r=1}^3\varepsilon_r^\mu(p)\varepsilon_r^{\nu *}(p)
=-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}
}
$$

for a massive spin-one field. For a massless gauge field, a physical polarization vector is defined only up to

$$
\boxed{\varepsilon^\mu(k)\sim\varepsilon^\mu(k)+\alpha(k)k^\mu.}
$$

This is why photon polarization sums are gauge-dependent unless they are contracted into conserved, gauge-invariant amplitudes. Weinberg derives the little-group origin of massive and massless one-particle labels and explains why a massless helicity-one field needs gauge redundancy; Coleman develops massive vector polarizations, their completeness relation, and the smooth massless limit with conserved currents; Srednicki gives the standard spin sums and photon polarization conventions used in perturbative calculations (Weinberg 1995, Vol. I, §§2.5, 5.3, 5.9, and 8.6; Coleman 2019, chs. 20, 21, 26, and 27; Srednicki 2007, §§38, 46, 50, and 54–57).

## Prerequisites

You should know [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/), [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/), [Dirac Field](/foundations/free-fields/dirac-field/), [Maxwell Field](/foundations/free-fields/maxwell-field/), [Proca Field](/foundations/free-fields/proca-field/), and [Conventions and Normalizations](/foundations/conventions-and-normalizations/). We use the mostly-minus metric, $p^2=m^2$ for massive particles, and the on-shell measure $d\mu(p)=d^3\mathbf p/[(2\pi)^3 2E_{\mathbf p}]$.

## Core idea

Polarization data do two jobs at once. First, they describe the internal spin or helicity state of an external particle. Second, when summed over, they become projectors that appear in propagator numerators and squared amplitudes.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Massive and massless spin-one polarization projectors](/figures/foundations/polarization-projectors.svg)

<figcaption>

Massive particles use the little group $SO(3)$ and carry a spin multiplet. Massless particles use the little group $ISO(2)$; finite-helicity particles carry helicity labels, and for vector fields the translation part of the little group appears as the gauge equivalence $\varepsilon^\mu\sim\varepsilon^\mu+\alpha k^\mu$.

</figcaption>
</figure>

This page is mainly a dictionary. It tells you which polarization objects to use, what they sum to, and what must not be summed before gauge invariance has done its job.

:::note[Assumptions]
We discuss free one-particle states in flat Minkowski spacetime. Interacting scattering amplitudes are mentioned only to explain how polarization sums are used. Non-Abelian gauge fixing, BRST cohomology, spinor-helicity variables, and massive higher-spin consistency conditions are later topics.
:::

## Scalars have no polarization

A real scalar one-particle state is specified by its momentum alone:

$$
|\mathbf p\rangle=a^\dagger(\mathbf p)|0\rangle.
$$

With the qft.org normalization,

$$
\langle\mathbf p|\mathbf q\rangle
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q).
$$

There is no spin label and no polarization sum. In a scattering calculation, a scalar external line contributes just the scalar external-state normalization and whatever coupling appears at the vertex. In a propagator, the scalar numerator is simply $1$:

$$
D_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

A complex scalar has particle and antiparticle species, but not spin polarizations. Species labels and spin labels are different. A complex scalar has charge labels; it still has spin zero.

## Massive spin one-half

For a massive Dirac field, a one-particle state has momentum plus a two-valued spin label,

$$
b_s^\dagger(\mathbf p)|0\rangle,
\qquad s=1,2.
$$

The corresponding plane-wave spinors obey

$$
(p\!\!/-m)u_s(p)=0,
\qquad
(p\!\!/+m)v_s(p)=0.
$$

With the conventions of [Dirac Field](/foundations/free-fields/dirac-field/), their normalizations are

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

The spin sums are

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

These are projectors onto the positive-energy and negative-frequency solution spaces of the Dirac equation. The word "projector" is slightly informal here because the normalization includes factors of $2m$; for example,

$$
\left(\frac{p\!\!/+m}{2m}\right)^2
=\frac{p\!\!/+m}{2m}
$$

on shell.

The Dirac propagator numerator is built from these spin sums:

$$
S_F(p)=\frac{i(p\!\!/+m)}{p^2-m^2+i\epsilon}.
$$

That numerator should not be mistaken for an individual spinor. It is what appears after the spin information has been summed over in an internal line or in an unobserved external spin state.

## Massive spin one

For a massive vector particle, choose three polarization vectors $\varepsilon_r^\mu(p)$, $r=1,2,3$, satisfying

$$
p_\mu\varepsilon_r^\mu(p)=0,
\qquad
\varepsilon_r^*(p)\cdot\varepsilon_s(p)=-\delta_{rs}.
$$

The minus sign is just the mostly-minus metric: physical massive-vector polarizations are spacelike.

In the rest frame,

$$
p^\mu=(m,0,0,0),
$$

transversality gives $\varepsilon^0=0$. A convenient basis is

$$
\varepsilon_1^\mu=(0,1,0,0),
\qquad
\varepsilon_2^\mu=(0,0,1,0),
\qquad
\varepsilon_3^\mu=(0,0,0,1).
$$

For momentum along the $z$ direction,

$$
p^\mu=(E,0,0,k),
\qquad E^2=k^2+m^2,
$$

two transverse polarizations may be chosen as

$$
\varepsilon_1^\mu=(0,1,0,0),
\qquad
\varepsilon_2^\mu=(0,0,1,0),
$$

and a longitudinal polarization as

$$
\boxed{
\varepsilon_L^\mu(p)=\frac{1}{m}(k,0,0,E).
}
$$

Check:

$$
p\cdot\varepsilon_L
=\frac{1}{m}(Ek-kE)=0,
$$

and

$$
\varepsilon_L\cdot\varepsilon_L
=\frac{k^2-E^2}{m^2}=-1.
$$

The completeness relation is

$$
\boxed{
\sum_{r=1}^3\varepsilon_r^\mu(p)\varepsilon_r^{\nu *}(p)
=-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}.
}
$$

The right-hand side is the covariant projector onto the subspace orthogonal to $p^\mu$. Indeed,

$$
p_\mu\left(-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}\right)=0
$$

on shell. This is the spin-one version of a spin sum.

The Proca propagator is therefore often written as

$$
D_F^{\mu\nu}(p)
=\frac{i}{p^2-m^2+i\epsilon}
\left(-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}\right),
$$

or equivalently

$$
D_F^{\mu\nu}(p)
=\frac{-i}{p^2-m^2+i\epsilon}
\left(\eta^{\mu\nu}-\frac{p^\mu p^\nu}{m^2}\right).
$$

These are the same formula.

## Helicity basis

The linear polarizations $\varepsilon_1$ and $\varepsilon_2$ are often replaced by circular polarizations. For a momentum along the $z$ direction, define

$$
\varepsilon_\pm^\mu
=\frac{1}{\sqrt2}\left(\varepsilon_1^\mu\pm i\varepsilon_2^\mu\right),
$$

up to a conventional overall phase. Under a rotation about the direction of motion, these transform by phases. That is the content of helicity: the spin component along the momentum direction.

For a massive spin-one particle, one can use the helicity basis

$$
\varepsilon_+^\mu,
\qquad
\varepsilon_-^\mu,
\qquad
\varepsilon_0^\mu\equiv\varepsilon_L^\mu.
$$

The longitudinal state $\lambda=0$ is physical when $m\neq0$. It is not a gauge artifact. It is one of the three spin states of a massive spin-one particle.

For a massless spin-one particle, the physical helicities are only

$$
\lambda=+1,
\qquad
\lambda=-1.
$$

There is no physical longitudinal photon.

## Massless spin one and gauge equivalence

For a photon moving along the $z$ direction,

$$
k^\mu=(\omega,0,0,\omega),
$$

a convenient pair of transverse linear polarization vectors is

$$
\varepsilon_1^\mu=(0,1,0,0),
\qquad
\varepsilon_2^\mu=(0,0,1,0).
$$

They obey

$$
k\cdot\varepsilon_i=0,
\qquad
\varepsilon_i\cdot\varepsilon_j=-\delta_{ij}.
$$

A circular basis is

$$
\varepsilon_\pm^\mu
=\frac{1}{\sqrt2}(\varepsilon_1^\mu\pm i\varepsilon_2^\mu),
$$

again up to phase conventions. These are the two photon helicities.

The important extra fact is that, for a gauge field, the replacement

$$
\varepsilon^\mu(k)\mapsto\varepsilon^\mu(k)+\alpha(k)k^\mu
$$

is a change of representative, not a change of physical photon state. In position space, it is the plane-wave version of

$$
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x).
$$

This is why a covariant four-vector potential can describe a massless helicity-one particle without carrying four physical one-particle states.

## Massless polarization sums

For a massive vector, the polarization sum is a Lorentz-covariant projector with no reference vector. For a massless vector, the physical polarization sum cannot be written as a Lorentz-covariant projector using only $k^\mu$ and $\eta^{\mu\nu}$. One must either fix a gauge or introduce an auxiliary vector.

Choose a reference vector $n^\mu$ with $n\cdot k\neq0$. A standard physical polarization sum is

$$
\boxed{
\sum_{\lambda=\pm}
\varepsilon_\lambda^\mu(k;n)\varepsilon_\lambda^{\nu *}(k;n)
= -\eta^{\mu\nu}
+\frac{k^\mu n^\nu+n^\mu k^\nu}{k\cdot n}
-\frac{n^2 k^\mu k^\nu}{(k\cdot n)^2}.
}
$$

This tensor is transverse to $k^\mu$ and to $n^\mu$:

$$
k_\mu\sum_\lambda\varepsilon_\lambda^\mu\varepsilon_\lambda^{\nu *}=0,
\qquad
n_\mu\sum_\lambda\varepsilon_\lambda^\mu\varepsilon_\lambda^{\nu *}=0.
$$

The reference vector encodes a gauge choice. Physical quantities cannot depend on it.

In many QED calculations, one uses the shortcut

$$
\sum_{\lambda=\pm}
\varepsilon_\lambda^\mu(k)\varepsilon_\lambda^{\nu *}(k)
\leadsto -\eta^{\mu\nu}.
$$

This is safe only when the omitted gauge terms vanish after contraction with conserved currents or gauge-invariant amplitudes. If an amplitude has the form

$$
\mathcal M=\varepsilon_\mu(k)\mathcal M^\mu(k),
$$

then the gauge shift decouples precisely when

$$
k_\mu\mathcal M^\mu(k)=0.
$$

This is the external-photon version of a Ward identity.

:::caution[The shortcut is not the definition]
The replacement $\sum_\lambda\varepsilon_\lambda^\mu\varepsilon_\lambda^{\nu *}\to-\eta^{\mu\nu}$ is not the physical photon polarization sum by itself. It is a computational shortcut inside gauge-invariant contractions. Outside that context, it includes unphysical polarizations.
:::

## Massive versus massless vector limit

The massive spin-one projector contains a longitudinal term,

$$
-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}.
$$

As $m\to0$, the longitudinal polarization behaves like

$$
\varepsilon_L^\mu(p)=\frac{1}{m}(k,0,0,E),
$$

which becomes large. This is one reason the massless limit of a massive vector field is delicate.

However, if a massive vector is coupled to a conserved current, the dangerous longitudinal contribution decouples from current exchange:

$$
j_\mu(p)\frac{p^\mu p^\nu}{m^2}j'_\nu(-p)
=\frac{(p\cdot j)(p\cdot j')}{m^2}=0.
$$

This is the clean physical origin of Coleman's observation that the massless limit is sensible only in the presence of current conservation. It is also the seed of the later gauge-theory lesson: massless spin-one particles force gauge invariance onto their consistent interactions.

## Little groups and why the counts differ

A one-particle state is labeled by a momentum $p$ and by an irreducible representation of the subgroup of the Lorentz group that leaves a chosen standard momentum fixed. That subgroup is the little group.

For a massive particle, choose

$$
p_0^\mu=(m,0,0,0).
$$

The Lorentz transformations that leave $p_0$ fixed are ordinary spatial rotations. The little group is $SO(3)$, or its double cover $SU(2)$ when spinors are included. Therefore massive particles are labeled by spin $s$, and the spin multiplet has

$$
2s+1
$$

states.

For a massless particle, choose

$$
k_0^\mu=(\omega,0,0,\omega).
$$

The little group is the two-dimensional Euclidean group $ISO(2)$: rotations around the direction of motion plus two null-plane "translations." For ordinary finite-helicity particles, the translation part acts trivially on physical one-particle states, while the rotation part gives the helicity phase. Thus a massless spin-one particle has helicities $\lambda=+1$ and $\lambda=-1$ rather than three spin projections.

For a vector potential $A_\mu$, the little-group translations do not disappear from the covariant field representation. They show up as gauge transformations of the polarization vector. This is the group-theoretic reason gauge redundancy is tied so tightly to massless spin one.

## External states and internal lines

A common source of confusion is that external polarization vectors and internal propagator numerators look similar. They are related but not identical.

For an external massive vector particle, one inserts a definite polarization vector,

$$
\varepsilon_r^\mu(p),
$$

or sums over $r$ if the final spin is unobserved. For an internal Proca line, one uses the propagator

$$
D_F^{\mu\nu}(p)
=\frac{i}{p^2-m^2+i\epsilon}
\left(-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}\right).
$$

The numerator resembles the on-shell polarization sum, but the internal momentum is generally off shell. In a perturbative rule, the propagator is the inverse of the quadratic kinetic operator, not literally a sum over on-shell particle polarizations at every internal momentum.

Similarly, for a Dirac external particle one uses a spinor $u_s(p)$ or $v_s(p)$; for an internal Dirac line one uses

$$
S_F(p)=\frac{i(p\!\!/+m)}{p^2-m^2+i\epsilon}.
$$

The numerator is the covariant object made possible by the spin sums.

## Unpolarized rates

If the spin or polarization of an initial particle is not prepared, one averages over its physical spin states. If the spin or polarization of a final particle is not measured, one sums over its physical spin states.

For example, for a massive spin-one particle, an unobserved final polarization gives

$$
\sum_{r=1}^3
\varepsilon_r^\mu(p)\varepsilon_r^{\nu *}(p)
=-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}.
$$

For an unpolarized initial massive spin-one particle, one averages:

$$
\frac{1}{3}\sum_{r=1}^3
\varepsilon_r^\mu(p)\varepsilon_r^{\nu *}(p).
$$

For a photon, the corresponding factors are

$$
\sum_{\lambda=\pm}
\varepsilon_\lambda^\mu(k)\varepsilon_\lambda^{\nu *}(k)
$$

for an unobserved final photon, and

$$
\frac12\sum_{\lambda=\pm}
\varepsilon_\lambda^\mu(k)\varepsilon_\lambda^{\nu *}(k)
$$

for an unpolarized initial photon. The factor $1/2$ is the average over the two physical helicities.

## Common pitfalls

### Confusing components with physical polarizations

A Lorentz vector has four components. A massive vector particle has three physical polarizations. A photon has two. The number of field components is not the number of physical one-particle states.

### Treating a gauge choice as an observable

Photon polarization vectors depend on gauge choices and reference vectors. Physical amplitudes do not. If a result depends on the reference vector $n^\mu$, some gauge-invariance check has failed or the object is not an observable.

### Forgetting the longitudinal massive mode

A massive spin-one particle has a genuine longitudinal polarization. Dropping it because photons are transverse is wrong. This mistake is especially damaging in massive-vector exchange and in high-energy scattering.

### Using negative-metric states as physical photons

Covariant photon propagators contain unphysical components. Gauge invariance, constraints, or BRST cohomology remove them from the physical spectrum. They are not extra photons.

### Applying on-shell sums to off-shell propagators without context

Spin sums are identities for on-shell external states. Propagator numerators are inverses of quadratic operators. They agree in useful ways, but the conceptual origin is different.

## Checklist

When using a polarization formula, ask:

1. Is the particle massive or massless?
2. Is this an external state or an internal line?
3. Is the spin or polarization fixed, summed, or averaged?
4. For a photon or gauge boson, has gauge invariance been used correctly?
5. Are the normalization conventions the same as the rest of the calculation?

Most polarization mistakes are failures of one of these five checks. Tiny list, huge blast radius.

## Exercises

### Exercise 1: Longitudinal Proca polarization

For momentum

$$
p^\mu=(E,0,0,k),
\qquad E^2=k^2+m^2,
$$

show that

$$
\varepsilon_L^\mu=\frac{1}{m}(k,0,0,E)
$$

obeys $p\cdot\varepsilon_L=0$ and $\varepsilon_L^2=-1$.

<details>
<summary><strong>Solution</strong></summary>

With mostly-minus metric,

$$
p\cdot\varepsilon_L
=E\frac{k}{m}-k\frac{E}{m}=0.
$$

The norm is

$$
\varepsilon_L^2
=\left(\frac{k}{m}\right)^2-\left(\frac{E}{m}\right)^2
=\frac{k^2-E^2}{m^2}
=-1,
$$

because $E^2-k^2=m^2$.

</details>

### Exercise 2: Massive vector projector

Suppose

$$
P^{\mu\nu}(p)=\sum_{r=1}^3\varepsilon_r^\mu(p)\varepsilon_r^{\nu *}(p).
$$

Use Lorentz covariance and transversality to show that

$$
P^{\mu\nu}=A\eta^{\mu\nu}+B p^\mu p^\nu,
$$

with $A=-1$ and $B=1/m^2$.

<details>
<summary><strong>Solution</strong></summary>

Lorentz covariance says that the only available rank-two tensors built from $p^\mu$ and $\eta^{\mu\nu}$ are

$$
\eta^{\mu\nu},
\qquad
p^\mu p^\nu.
$$

Thus

$$
P^{\mu\nu}=A\eta^{\mu\nu}+Bp^\mu p^\nu.
$$

Transversality gives

$$
0=p_\mu P^{\mu\nu}=A p^\nu+B p^2 p^\nu.
$$

On shell $p^2=m^2$, so

$$
A+Bm^2=0.
$$

In the rest frame, $p=(m,0,0,0)$ and the three polarizations are purely spatial. Therefore

$$
P^{ij}=\delta^{ij}.
$$

Since $\eta^{ij}=-\delta^{ij}$ and $p^i=0$, this implies

$$
A\eta^{ij}=\delta^{ij},
$$

so $A=-1$. Then $B=1/m^2$.

</details>

### Exercise 3: Gauge shift and conserved amplitudes

Let

$$
\mathcal M=\varepsilon_\mu(k)\mathcal M^\mu(k).
$$

Show that the gauge shift $\varepsilon_\mu\to\varepsilon_\mu+\alpha k_\mu$ leaves $\mathcal M$ invariant if $k_\mu\mathcal M^\mu=0$.

<details>
<summary><strong>Solution</strong></summary>

Under the shift,

$$
\delta\mathcal M
=\alpha k_\mu\mathcal M^\mu.
$$

If

$$
k_\mu\mathcal M^\mu=0,
$$

then

$$
\delta\mathcal M=0.
$$

Thus the amplitude depends only on the gauge-equivalence class of the polarization vector.

</details>

### Exercise 4: Photon polarization sum in conserved-current exchange

Using the reference-vector formula

$$
\sum_{\lambda=\pm}
\varepsilon_\lambda^\mu\varepsilon_\lambda^{\nu *}
= -\eta^{\mu\nu}
+\frac{k^\mu n^\nu+n^\mu k^\nu}{k\cdot n}
-\frac{n^2 k^\mu k^\nu}{(k\cdot n)^2},
$$

show that the $n^\mu$-dependent terms vanish when contracted into conserved currents $j_\mu$ and $j'_\nu$ satisfying $k\cdot j=k\cdot j'=0$.

<details>
<summary><strong>Solution</strong></summary>

Contract the reference-dependent part with currents:

$$
j_\mu\left(
\frac{k^\mu n^\nu+n^\mu k^\nu}{k\cdot n}
-\frac{n^2 k^\mu k^\nu}{(k\cdot n)^2}
\right)j'_\nu.
$$

The first term gives

$$
\frac{(j\cdot k)(n\cdot j')+(j\cdot n)(k\cdot j')}{k\cdot n}=0.
$$

The second gives

$$
-\frac{n^2(j\cdot k)(k\cdot j')}{(k\cdot n)^2}=0.
$$

Therefore only

$$
-j_\mu\eta^{\mu\nu}j'_\nu
$$

survives.

</details>

### Exercise 5: Dirac spin-sum projector

Using $p^2=m^2$, show that

$$
\Pi_+(p)=\frac{p\!\!/+m}{2m}
$$

satisfies $\Pi_+^2=\Pi_+$.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
(p\!\!/+m)^2
=p\!\!/p\!\!/+2mp\!\!/+m^2.
$$

The Clifford algebra gives

$$
p\!\!/p\!\!/=p^2=m^2.
$$

Thus

$$
(p\!\!/+m)^2=2m(p\!\!/+m).
$$

Therefore

$$
\Pi_+^2
=\frac{(p\!\!/+m)^2}{4m^2}
=\frac{2m(p\!\!/+m)}{4m^2}
=\frac{p\!\!/+m}{2m}
=\Pi_+.
$$

</details>

### Exercise 6: Counting polarizations

Use the little group to explain why a massive spin-one particle has three physical polarizations while a photon has two.

<details>
<summary><strong>Solution</strong></summary>

For a massive particle, the standard momentum is

$$
p_0=(m,0,0,0).
$$

The little group is $SO(3)$, whose spin-one representation has

$$
2s+1=3
$$

states. These are the three spin projections $m_s=-1,0,+1$.

For a massless particle, the standard momentum is

$$
k_0=(\omega,0,0,\omega).
$$

The little group is $ISO(2)$. Ordinary finite-helicity one-particle representations use the rotation subgroup to label helicity and represent the translation part trivially on physical states. A massless spin-one particle therefore has two helicities,

$$
\lambda=+1,
\qquad
\lambda=-1.
$$

In the vector-potential description, the translation part appears as gauge redundancy, which removes the unphysical longitudinal and timelike components.

</details>


## Relation to other pages

- [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/) gives the little-group classification behind spin and helicity labels.
- [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/) fixes the one-particle normalization used with external polarization states.
- [Dirac Field](/foundations/free-fields/dirac-field/) derives the spinor completeness relations and Dirac propagator.
- [Maxwell Field](/foundations/free-fields/maxwell-field/) explains why massless spin one requires gauge redundancy.
- [Proca Field](/foundations/free-fields/proca-field/) derives the massive vector transversality condition, completeness relation, and propagator.
- [Free Field Summary](/foundations/free-fields/free-field-summary/) collects these spin sums in a compact reference table.

## Research status

- **Established:** The little-group classification, Dirac spin sums, massive-vector completeness relation, photon helicity count, and gauge-dependent photon polarization sums are textbook-standard.
- **Active:** Efficient polarization variables, especially helicity spinors and on-shell polarization bases, are central to modern scattering-amplitude methods.
- **Speculative:** None in this page. The subtleties are conventional and structural, not conjectural.

## Sources and further reading

### Primary references

- E. P. Wigner, "On Unitary Representations of the Inhomogeneous Lorentz Group," *Annals of Mathematics* **40** (1939) 149–204, for the little-group classification of one-particle states.
- A. Proca, "Sur la théorie ondulatoire des électrons positifs et négatifs," *Journal de Physique et le Radium* **7** (1936) 347–353, for the massive vector field.
- H. Weyl, "Elektron und Gravitation," *Zeitschrift für Physik* **56** (1929) 330–352, for the gauge principle in its early modern form.

### Standard textbook treatments

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§2.5, 5.3, 5.9, and 8.6, for little groups, causal vector fields, massless helicity-one fields, and photon polarization sums.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 20, 21, 26, and 27, for spinor completeness relations, massive-vector polarizations, Proca completeness, and the conserved-current massless limit.
- M. Srednicki, *Quantum Field Theory*, §§38, 46, 50, and 54–57, for spinor technology, spin sums, spinor-helicity preliminaries, and photon quantization.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. III.4 and N.2, for the physical interpretation of massive and massless spin-one polarization vectors.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, chs. 3 and 5, for spinor sums and polarization sums in scattering calculations.

### For a first pass

- Coleman, ch. 26, for massive-vector polarizations.
- Peskin and Schroeder, §§5.1–5.2, for how polarization sums enter cross-section calculations.

### For mathematical precision

- Weinberg, Vol. I, chs. 2 and 5, for the representation-theoretic origin of polarization labels.
- R. Streater and A. Wightman, *PCT, Spin and Statistics, and All That*, for the axiomatic relation between spin, locality, and representation theory.

## Version history

- **2026-05-23:** Initial qft.org page on polarization vectors, spin sums, helicity, little groups, photon gauge equivalence, massive-vector completeness, and unpolarized sums, with a TikZ-generated polarization-projector figure.
