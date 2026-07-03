---
title: "Weyl and Majorana Fields"
description: "Chiral and Majorana spinor fields: two-component notation, massless Weyl equations, Dirac and Majorana packaging, mass terms, gauge-representation constraints, quantization, and chirality versus helicity."
sidebar:
  label: "Weyl and Majorana Fields"
  order: 3
---

## Summary

A Dirac field is not the only useful spin-one-half field. In four spacetime dimensions, the most economical spinor fields are **Weyl fields**, which carry definite chirality. A **Majorana field** is a neutral four-component spinor whose particle and antiparticle modes are identified.

With qft.org's mostly-minus convention, define

$$
\sigma^\mu_{\alpha\dot\alpha}=(\mathbf 1,\sigma^i),
\qquad
\bar\sigma^{\mu\dot\alpha\alpha}=(\mathbf 1,-\sigma^i),
$$

so that

$$
\sigma^\mu\bar\sigma^\nu+\sigma^\nu\bar\sigma^\mu
=2\eta^{\mu\nu}\mathbf 1,
\qquad
\bar\sigma^\mu\sigma^\nu+\bar\sigma^\nu\sigma^\mu
=2\eta^{\mu\nu}\mathbf 1.
$$

A free massless left-handed Weyl field has Lagrangian

$$
\boxed{
\mathcal L_\text{Weyl}
=i\chi^\dagger_{\dot\alpha}\bar\sigma^{\mu\dot\alpha\alpha}\partial_\mu\chi_\alpha .
}
$$

Its equation of motion is

$$
\boxed{
\bar\sigma^{\mu\dot\alpha\alpha}\partial_\mu\chi_\alpha=0.
}
$$

A Dirac spinor can be written as two independent left-handed Weyl fields,

$$
\boxed{
\Psi_D=
\begin{pmatrix}
\chi_\alpha\\
\xi^{\dagger\dot\alpha}
\end{pmatrix},
}
$$

with Dirac mass term

$$
\boxed{
\mathcal L_m=-m(\xi\chi+\chi^\dagger\xi^\dagger)
=-m\overline\Psi_D\Psi_D
}
$$

for real $m$. A Majorana spinor instead uses one Weyl field and its Hermitian conjugate,

$$
\boxed{
\Psi_M=
\begin{pmatrix}
\chi_\alpha\\
\chi^{\dagger\dot\alpha}
\end{pmatrix},
\qquad
\Psi_M^c=\Psi_M,
}
$$

with Majorana mass term

$$
\boxed{
\mathcal L_m=-\frac12\left(m\chi\chi+m^*\chi^\dagger\chi^\dagger\right).
}
$$

The factor $1/2$ avoids double-counting: the lower half of a Majorana spinor is not an independent field.

Srednicki stresses that a Dirac field in a representation $R$ is equivalent to two left-handed Weyl fields, one in $R$ and one in the conjugate representation, while a Majorana field is possible when the representation is real; Coleman develops Weyl spinors, the Dirac equation, Majorana representation, charge conjugation, and bilinears in a basis-conscious way; Weinberg derives spinor fields from Lorentz covariance, causality, and the relation between particles and antiparticles (Srednicki 2007, §§34–40 and §75; Coleman 2019, chs. 19–22; Weinberg 1995, Vol. I, §§5.4–5.7).

## Prerequisites

You should know [Dirac Field](/foundations/free-fields/dirac-field/), [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/), [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/), and [Conventions and Normalizations](/foundations/conventions-and-normalizations/). The page [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/) will use the fields introduced here to classify interactions.

## Core idea

Weyl fields are the irreducible spin-one-half building blocks in four dimensions. A Dirac field combines two independent Weyl fields. A Majorana field combines one Weyl field with its own Hermitian conjugate.

<figure class="doc-figure" style="--figure-width: 36rem;">

![Map from a Weyl field to Dirac and Majorana spinor packages](/figures/foundations/weyl-majorana-map.svg)

<figcaption>

A left-handed Weyl field and its Hermitian conjugate transform in conjugate Lorentz representations. A Dirac spinor packages two independent Weyl fields, while a Majorana spinor packages one Weyl field with its own conjugate. The mass terms reflect this difference.

</figcaption>
</figure>

This distinction is not cosmetic. It controls chirality, gauge charges, neutrino mass terms, supersymmetric fermions, anomaly constraints, and how one counts physical degrees of freedom.

:::note[Assumptions]
We work on flat Minkowski spacetime, in four spacetime dimensions, with mostly-minus metric. Spinor fields are operator-valued distributions. Two-component notation is used for clarity, but the final physical statements are representation-independent.
:::

## Two-component notation

The proper Lorentz group is locally related to $SL(2,\mathbb C)$. In four dimensions this gives two inequivalent two-component spinor representations:

$$
\left(\frac12,0\right),
\qquad
\left(0,\frac12\right).
$$

A left-handed Weyl spinor is written

$$
\chi_\alpha,
\qquad
\alpha=1,2.
$$

Its Hermitian conjugate is written

$$
\chi^\dagger_{\dot\alpha},
\qquad
\dot\alpha=\dot 1,\dot 2.
$$

The dotted index reminds us that the conjugate transforms in the conjugate Lorentz representation. In this convention,

$$
\sigma^\mu_{\alpha\dot\alpha}=(\mathbf 1,\sigma^i),
\qquad
\bar\sigma^{\mu\dot\alpha\alpha}=(\mathbf 1,-\sigma^i),
$$

where $\sigma^i$ are the Pauli matrices. The identities

$$
\sigma^\mu\bar\sigma^\nu+\sigma^\nu\bar\sigma^\mu
=2\eta^{\mu\nu}\mathbf 1,
$$

and

$$
\bar\sigma^\mu\sigma^\nu+\bar\sigma^\nu\sigma^\mu
=2\eta^{\mu\nu}\mathbf 1
$$

are the two-component version of the Clifford algebra.

The antisymmetric tensors $\epsilon_{\alpha\beta}$ and $\epsilon^{\alpha\beta}$ raise and lower undotted spinor indices; their dotted analogues do the same for dotted indices. We use compact contractions such as

$$
\xi\chi\equiv \xi^\alpha\chi_\alpha,
\qquad
\chi^\dagger\xi^\dagger
\equiv \chi^\dagger_{\dot\alpha}\xi^{\dagger\dot\alpha}.
$$

Because fermion fields anticommute, signs in two-component formulas are convention-sensitive. The invariant information is simple: Lorentz scalars are built by contracting undotted indices with undotted indices or dotted indices with dotted indices.

## Massless Weyl fields

The free massless left-handed Weyl Lagrangian is

$$
\mathcal L=i\chi^\dagger\bar\sigma^\mu\partial_\mu\chi.
$$

Written with indices,

$$
\mathcal L
=i\chi^\dagger_{\dot\alpha}\bar\sigma^{\mu\dot\alpha\alpha}\partial_\mu\chi_\alpha.
$$

Varying with respect to $\chi^\dagger_{\dot\alpha}$ gives

$$
i\bar\sigma^{\mu\dot\alpha\alpha}\partial_\mu\chi_\alpha=0.
$$

The conjugate equation is

$$
i\sigma^\mu_{\alpha\dot\alpha}\partial_\mu\chi^{\dagger\dot\alpha}=0.
$$

Squaring the Weyl operator gives the massless Klein–Gordon equation. Acting with $\sigma^\nu\partial_\nu$ on the left equation gives

$$
\sigma^\nu\bar\sigma^\mu\partial_\nu\partial_\mu\chi=0.
$$

Only the symmetric part contributes, so

$$
\eta^{\mu\nu}\partial_\mu\partial_\nu\chi=\Box\chi=0.
$$

A Weyl field is therefore a spinor field whose components obey the massless wave equation, but whose Lorentz transformation law carries spin-one-half information.

## Chirality and helicity

Chirality is a Lorentz-representation label. In four-component notation,

$$
\psi_L=P_L\psi,
\qquad
\psi_R=P_R\psi,
$$

where

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2}.
$$

A left-handed Weyl field is the two-component form of $\psi_L$. A right-handed Weyl field is the two-component form of $\psi_R$.

Helicity is the projection of spin along momentum. For a massless positive-energy particle, chirality and helicity are tied together: left-chiral particle modes have one helicity and right-chiral particle modes have the opposite helicity. For antiparticle modes, the relation is reversed. For massive particles, helicity is frame-dependent while chirality is not. This is why a massive Dirac field contains both chiralities.

A useful slogan is:

```txt
chirality = Lorentz representation;
helicity = spin projected along momentum.
```

The slogan is safe only if one remembers the massless versus massive distinction.

## Dirac fields from Weyl fields

A Dirac field can be built from two independent left-handed Weyl fields $\chi_\alpha$ and $\xi_\alpha$:

$$
\Psi_D=
\begin{pmatrix}
\chi_\alpha\\
\xi^{\dagger\dot\alpha}
\end{pmatrix}.
$$

The upper component is left-handed. The lower component is the Hermitian conjugate of a left-handed Weyl field, so it is right-handed. In this basis, a Dirac field is a left-handed field plus a right-handed field.

The kinetic terms are

$$
\mathcal L_\text{kin}
=i\chi^\dagger\bar\sigma^\mu\partial_\mu\chi
+i\xi^\dagger\bar\sigma^\mu\partial_\mu\xi.
$$

The Lorentz-invariant Dirac mass term is

$$
\mathcal L_m=-m(\xi\chi+\chi^\dagger\xi^\dagger),
$$

for real $m$. This is the two-component version of

$$
\mathcal L_m=-m\overline\Psi_D\Psi_D.
$$

The mass term couples the two chiralities. This is why a single isolated massless Weyl field cannot be made massive by an ordinary Dirac mass term: it needs a second Weyl field in the conjugate internal-symmetry representation.

If $\Psi_D$ has charge $q$ under a U(1) symmetry, then $\chi$ and $\xi^\dagger$ carry charge $q$, while $\xi$ carries charge $-q$. Thus a charged Dirac fermion is naturally built from two left-handed Weyl fields with opposite charges.

## Majorana fields

A Majorana field is a spinor equal to its own charge conjugate:

$$
\Psi_M^c=\Psi_M.
$$

In two-component notation it can be written as

$$
\Psi_M=
\begin{pmatrix}
\chi_\alpha\\
\chi^{\dagger\dot\alpha}
\end{pmatrix}.
$$

The lower component is not independent. Therefore a Majorana field has half the independent field content of a Dirac field.

The free Majorana Lagrangian is most transparently written in two-component form:

$$
\boxed{
\mathcal L
=i\chi^\dagger\bar\sigma^\mu\partial_\mu\chi
-\frac12\left(m\chi\chi+m^*\chi^\dagger\chi^\dagger\right).
}
$$

If $m$ is nonzero and there is no other phase-sensitive coupling, the phase of $\chi$ can be used to make $m$ real and nonnegative. Then

$$
\mathcal L
=i\chi^\dagger\bar\sigma^\mu\partial_\mu\chi
-\frac12m(\chi\chi+\chi^\dagger\chi^\dagger).
$$

The factor $1/2$ is important. Without it, the mass term would count the same physical degree of freedom twice.

A Majorana mass term is possible only when the internal quantum numbers allow it. For an ordinary U(1) charge,

$$
\chi\mapsto e^{-iq\alpha}\chi
\quad\Rightarrow\quad
\chi\chi\mapsto e^{-2iq\alpha}\chi\chi.
$$

Thus a Majorana mass term for a field with nonzero unbroken U(1) charge is forbidden. More generally, a Majorana mass is allowed when the gauge representation is real, or when additional fields and symmetry breaking make the total term gauge invariant.

## Mass terms and symmetry

There are three common spin-one-half mass patterns.

| Type | Two-component form | Gauge condition | Physical content |
| --- | --- | --- | --- |
| Weyl, massless | $i\chi^\dagger\bar\sigma^\mu\partial_\mu\chi$ | any representation, subject to anomaly constraints | one chiral field |
| Dirac | $-m(\xi\chi+\text{h.c.})$ | $\chi$ and $\xi$ in conjugate representations | particle and antiparticle independent |
| Majorana | $-\frac12(m\chi\chi+\text{h.c.})$ | real representation, or gauge singlet | particle equals antiparticle |

This table is the spinor version of a recurring QFT lesson: **Lorentz invariance is necessary, but not sufficient.** Internal symmetries decide which Lorentz-invariant terms are actually allowed.

## Quantization

The canonical momentum conjugate to $\chi_\alpha$ is

$$
\pi^\alpha
=\frac{\partial\mathcal L}{\partial(\partial_0\chi_\alpha)}
=i\chi^\dagger_{\dot\alpha}\bar\sigma^{0\dot\alpha\alpha}.
$$

Since $\bar\sigma^0=\mathbf 1$, the equal-time anticommutation relation can be written as

$$
\boxed{
\{\chi_\alpha(t,\mathbf x),\chi^\dagger_{\dot\beta}(t,\mathbf y)\}
=\sigma^0_{\alpha\dot\beta}\delta^{(3)}(\mathbf x-\mathbf y).
}
$$

The other equal-time anticommutators vanish:

$$
\{\chi_\alpha(t,\mathbf x),\chi_\beta(t,\mathbf y)\}=0,
\qquad
\{\chi^\dagger_{\dot\alpha}(t,\mathbf x),\chi^\dagger_{\dot\beta}(t,\mathbf y)\}=0.
$$

A massless Weyl field has one annihilation species and one creation species, but the particle and antiparticle helicities are locked to the chirality. A massive Majorana field has creation and annihilation operators related by charge conjugation; it still has positive-energy particle states, but there is no independent antiparticle species.

In four-component notation, the Majorana propagator has the same Dirac-operator inverse as a Dirac propagator,

$$
\langle0|T\Psi_M(x)\overline\Psi_M(y)|0\rangle
=\int\frac{d^4p}{(2\pi)^4}
\frac{i(p\!\!/+m)e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon},
$$

but Wick contractions involving $\Psi_M\Psi_M$ and $\overline\Psi_M\overline\Psi_M$ also occur because $\Psi_M$ and $\Psi_M^c$ are not independent.

## Dimensions and interactions

The Weyl kinetic term fixes the engineering dimension of a spinor field. Since $[\mathcal L]=4$ and $[\partial_\mu]=1$ in four spacetime dimensions,

$$
2[\chi]+1=4,
$$

so

$$
\boxed{[\chi]=\frac32.}
$$

This is the same as the dimension of a Dirac field. Therefore a mass term has coefficient dimension one:

$$
[m\chi\chi]=1+3=4.
$$

A scalar Yukawa coupling such as

$$
y\phi\xi\chi+\text{h.c.}
$$

has dimension four if $[\phi]=1$, so $y$ is dimensionless in four spacetime dimensions. This is why Weyl notation is so natural in chiral gauge theories and in the Standard Model: the allowed Yukawa couplings are just the gauge-invariant ways to pair Weyl fields with scalar fields.

## Discrete symmetries

Parity exchanges the two inequivalent Weyl representations. A theory of a single left-handed Weyl field is therefore not parity invariant by itself. To define parity as a symmetry, the theory must contain a matching right-handed field with appropriate internal quantum numbers.

Charge conjugation exchanges particles and antiparticles. A Majorana field is invariant under charge conjugation up to a phase convention, because it is equal to its own charge conjugate. A charged Dirac field is not Majorana: its charge conjugate has opposite charge.

Time reversal does not exchange chirality in the same way parity does. The precise transformation law depends on the spinor basis and phase conventions, but physical statements about whether a term is allowed must be basis-independent. Coleman’s Majorana-representation treatment is especially useful because charge conjugation becomes complex conjugation in that basis, making these statements less mysterious (Coleman 2019, ch. 22).

## Examples

### Massless neutrino as a Weyl field

Before neutrino masses are included, a neutrino can be modeled as a left-handed Weyl field. Its kinetic term is simply

$$
i\nu_L^\dagger\bar\sigma^\mu\partial_\mu\nu_L.
$$

This captures the chiral nature of weak interactions. It does not by itself decide whether a neutrino mass, if present, is Dirac or Majorana.

### Charged electron as a Dirac field

A charged electron field cannot be Majorana because electric charge is unbroken. Instead, the electron is described by a Dirac field, equivalently by two Weyl fields whose charges allow the mass term after electroweak symmetry breaking.

### Neutral Majorana fermion

A gauge-singlet Weyl field $N$ can have a Majorana mass term

$$
-\frac12(MNN+\text{h.c.}).
$$

This is the basic algebraic possibility behind many neutrino-mass models. The detailed phenomenology belongs in the Standard Model and Beyond the Standard Model sections, not in this Foundations page.

## Common pitfalls

**Confusing chirality with helicity.** They coincide in a simple way only for massless positive-energy modes. They are different concepts.

**Thinking a Majorana field is “half a fermion.”** It has half the independent field components of a Dirac field, but its quantized modes still describe ordinary fermionic one-particle states.

**Writing a Majorana mass for a charged field.** A Majorana mass violates any unbroken U(1) charge carried by the field.

**Forgetting the factor one half.** Majorana kinetic and mass terms often carry factors of $1/2$ in four-component notation because the field is constrained by a reality condition.

**Assuming every four-component spinor is Dirac.** Four-component notation is a container. It may contain a Dirac field, a Majorana field, or a pair of Weyl fields arranged for convenience.

**Treating basis conventions as physics.** The Weyl, Dirac, and Majorana gamma-matrix bases are different coordinate systems on the same spinor algebra.

## Relation to other topics

- [Dirac Field](/foundations/free-fields/dirac-field/) gives the four-component spin-one-half free field and its propagator.
- [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/) classifies the scalar, pseudoscalar, vector, axial-vector, and tensor bilinears built from spinors.
- [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/) explains anticommutators, fermionic oscillators, and Fock-space signs.
- [Bosons and Fermions](/foundations/relativistic-particles-and-fields/bosons-and-fermions/) introduces the statistics distinction at the level of multiparticle states.
- [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/) explains why antiparticle modes are required in relativistic QFT.
- [Lorentz Representations](/foundations/symmetry-and-spacetime/lorentz-representations/) will give the representation-theoretic derivation of Weyl and Dirac spinors.
- [Spinors from Lorentz Symmetry](/foundations/symmetry-and-spacetime/spinors-from-lorentz-symmetry/) will develop the $SL(2,\mathbb C)$ spinor formalism in more detail.
- [Discrete Symmetries](/foundations/symmetry-and-spacetime/discrete-symmetries/) will treat $C$, $P$, and $T$ systematically.
- The Standard Model section should later explain how chiral Weyl fields assemble into the observed fermion spectrum.

## Research status

- **Established:** Weyl, Dirac, and Majorana spinors; chiral projectors; free equations; canonical anticommutators; and the allowed Lorentz-invariant mass terms are textbook-standard.
- **Subtle:** Chiral gauge theories can have anomalies; Majorana conditions depend on spacetime dimension and signature; Euclidean continuation of Majorana fermions is delicate.
- **Out of scope here:** Anomaly cancellation, neutrino phenomenology, supersymmetric Majorana fermions, Majorana path integrals, and spinor-helicity methods.

## Exercises

### Exercise 1: Square the Weyl equation

Show that the massless Weyl equation implies the massless Klein–Gordon equation.

<details>
<summary><strong>Solution</strong></summary>

Start with

$$
\bar\sigma^\mu\partial_\mu\chi=0.
$$

Act on the left with $\sigma^\nu\partial_\nu$:

$$
\sigma^\nu\bar\sigma^\mu\partial_\nu\partial_\mu\chi=0.
$$

Since ordinary derivatives commute, only the symmetric part of $\sigma^\nu\bar\sigma^\mu$ contributes:

$$
\frac12(\sigma^\nu\bar\sigma^\mu+\sigma^\mu\bar\sigma^\nu)
\partial_\nu\partial_\mu\chi
=\eta^{\mu\nu}\partial_\mu\partial_\nu\chi.
$$

Thus

$$
\Box\chi=0.
$$

</details>

### Exercise 2: Find the Weyl field dimension

Use the kinetic term $i\chi^\dagger\bar\sigma^\mu\partial_\mu\chi$ to show that $[\chi]=3/2$ in four spacetime dimensions.

<details>
<summary><strong>Solution</strong></summary>

The action is dimensionless and $d^4x$ has dimension $-4$, so $[\mathcal L]=4$. The derivative has dimension one. Therefore

$$
[\chi^\dagger]+1+[\chi]=4.
$$

Since $\chi$ and $\chi^\dagger$ have the same dimension,

$$
2[\chi]+1=4.
$$

Hence

$$
[\chi]=\frac32.
$$

</details>

### Exercise 3: Check a U(1) Majorana mass

Let $\chi$ have charge $q$ under a U(1) symmetry, so $\chi\mapsto e^{-iq\alpha}\chi$. For which $q$ is the Majorana mass term $\chi\chi+\text{h.c.}$ invariant?

<details>
<summary><strong>Solution</strong></summary>

The bilinear transforms as

$$
\chi\chi\mapsto e^{-2iq\alpha}\chi\chi.
$$

For this to be invariant for arbitrary $\alpha$, we need

$$
e^{-2iq\alpha}=1
$$

for all $\alpha$, which implies $q=0$ for an ordinary continuous U(1). Thus a Majorana mass is forbidden for a field carrying nonzero unbroken U(1) charge.

</details>

### Exercise 4: Dirac mass as a Weyl pairing

Suppose $\chi$ and $\xi$ are left-handed Weyl fields with U(1) charges $q_\chi$ and $q_\xi$. What condition is required for $\xi\chi+\text{h.c.}$ to be U(1)-invariant?

<details>
<summary><strong>Solution</strong></summary>

The product transforms as

$$
\xi\chi\mapsto e^{-i(q_\xi+q_\chi)\alpha}\xi\chi.
$$

It is invariant for arbitrary $\alpha$ if

$$
q_\xi+q_\chi=0.
$$

Thus the two left-handed Weyl fields must lie in conjugate U(1) representations. In four-component language, this is why a charged Dirac field contains a right-handed component with the same physical charge as the left-handed component, but is built from the conjugate of a left-handed field with the opposite charge.

</details>

### Exercise 5: Count independent components

A Dirac spinor has four complex components before equations of motion are imposed. Explain why a Majorana condition halves the independent components.

<details>
<summary><strong>Solution</strong></summary>

A Dirac spinor has two independent two-component spinors:

$$
\Psi_D=(\chi,\xi^\dagger).
$$

The data are $\chi$ and $\xi$, or four complex Grassmann components in total. A Majorana spinor instead has

$$
\Psi_M=(\chi,\chi^\dagger).
$$

The lower component is determined by the upper component. Thus only the two complex components of $\chi$ are independent. Equivalently, the four-component Majorana field satisfies a reality condition $\Psi_M^c=\Psi_M$.

</details>

### Exercise 6: Why a single Weyl field is parity violating

Explain why a theory containing only one left-handed Weyl field cannot be invariant under parity unless another field is added.

<details>
<summary><strong>Solution</strong></summary>

Parity reverses spatial orientation and exchanges the two inequivalent Weyl representations:

$$
\left(\frac12,0\right)\longleftrightarrow\left(0,\frac12\right).
$$

A single left-handed Weyl field transforms in only one of these representations. Under parity it would have to map to a right-handed field. If no such field exists with the appropriate internal quantum numbers, parity cannot be represented as a symmetry of the theory.

</details>

## References

### Primary references

- H. Weyl, “Elektron und Gravitation. I,” *Zeitschrift für Physik* **56** (1929), for the Weyl equation in the early spinor context.
- P. A. M. Dirac, “The Quantum Theory of the Electron,” *Proceedings of the Royal Society A* **117** (1928), for the Dirac equation.
- E. Majorana, “Teoria simmetrica dell'elettrone e del positrone,” *Il Nuovo Cimento* **14** (1937), for the Majorana construction.

### Standard textbook treatments

- M. Srednicki, *Quantum Field Theory*, §§34–40 and §75, for left- and right-handed spinor fields, spinor-index manipulation, Weyl and Dirac Lagrangians, canonical quantization, discrete symmetries, and chiral gauge theories.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 19–22, for Weyl spinors, the Dirac equation, bilinear spinor products, quantization, charge conjugation, and Majorana representation.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.4–5.7, for Dirac fields, general Lorentz representations, causal fields, and the spin-statistics connection.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. II.1–II.4 and Appendix E, for a compact physical introduction to Dirac, Weyl, Majorana spinors, and the spin-statistics connection.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, chs. 3 and 4, for the standard four-component treatment and chiral spinor technology.

### For a first pass

- Zee, chs. II.1–II.3.
- Srednicki, §§34–37.
- Coleman, chs. 19–20.

### For mathematical precision

- Weinberg, Vol. I, §§5.4–5.7.
- P. Deligne et al., *Quantum Fields and Strings: A Course for Mathematicians*, Vol. I, for spin representations and fermionic fields.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for structural results about spinor fields, locality, and CPT.

## Version history

- **2026-05-22:** Initial qft.org page on Weyl and Majorana fields, including two-component notation, chiral and Majorana mass terms, gauge constraints, quantization, chirality versus helicity, common pitfalls, exercises, and a TikZ-generated structural figure.
