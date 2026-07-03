---
title: "Free Field Summary"
description: "Reference tables for the basic free relativistic fields: equations, propagators, mass dimensions, physical degrees of freedom, spin sums, and common interaction terms."
sidebar:
  label: "Free Field Summary"
  order: 8
---

## Summary

This page is a compact reference for the free fields introduced in this subsection. It fixes the data you usually need before moving on to correlation functions, path integrals, and perturbation theory:

- field equation,
- mass dimension,
- physical one-particle degrees of freedom,
- propagator,
- spin or polarization sums,
- typical interaction terms.

All formulas use the qft.org default mostly-minus metric

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
\qquad
p^2=(p^0)^2-\mathbf p^2,
$$

and the scalar denominator

$$
p^2-m^2+i\epsilon.
$$

The free-field pages are not meant to imply that nature is free. They identify the linearized building blocks around which perturbation theory, mode expansions, spectral representations, and asymptotic particle states are organized. Srednicki's textbook deliberately organizes introductory QFT by spin zero, spin one-half, and spin one; Coleman develops scalar, spinor, and vector free fields as the operator backbone of the course; Weinberg derives free fields from particle representations and locality rather than taking field equations as primitive (Srednicki 2007, parts I–III; Coleman 2019, chs. 3, 20–21, and 26–31; Weinberg 1995, Vol. I, chs. 2, 5, 6, 7, and 8).

## Prerequisites

You should know [Conventions and Normalizations](/foundations/conventions-and-normalizations/), [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), [Dirac Field](/foundations/free-fields/dirac-field/), [Weyl and Majorana Fields](/foundations/free-fields/weyl-and-majorana-fields/), [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/), [Maxwell Field](/foundations/free-fields/maxwell-field/), [Proca Field](/foundations/free-fields/proca-field/), and [Polarizations](/foundations/free-fields/polarizations/).

## How to use this page

Use this page when you need to remember a convention quickly. Use the individual pages when you need the derivation.

:::caution[Reference tables are not derivations]
A table can tell you that a photon has two physical helicities. It cannot by itself teach the constraint analysis, gauge redundancy, or little-group reason why that is true. Follow the links when a formula looks too magic.
:::

## Inventory by field

| Field | Spin | Statistics | Mass dimension in four dimensions | Physical one-particle states |
|---|---:|---|---:|---:|
| real scalar $\phi$ | 0 | boson | 1 | 1 |
| complex scalar $\phi$ | 0 | boson | 1 | 2 real modes; particle and antiparticle |
| Weyl spinor $\chi_\alpha$ | 1/2 | fermion | 3/2 | one helicity particle plus conjugate antiparticle |
| Majorana spinor $\psi_M$ | 1/2 | fermion | 3/2 | 2 massive spin states; self-conjugate |
| Dirac spinor $\psi$ | 1/2 | fermion | 3/2 | 2 particle spin states plus 2 antiparticle spin states |
| Maxwell potential $A_\mu$ | 1 | boson | 1 | 2 photon helicities |
| Proca field $A_\mu$ | 1 | boson | 1 | 3 massive spin-one polarizations |

The count in the final column is a count of physical one-particle states at fixed momentum. It is not the number of components in the field variable. The Maxwell potential $A_\mu$ has four components but only two physical photon helicities; the Dirac spinor has four complex components but the physical on-shell particle content is better described as particle/antiparticle species times spin labels.

## Free Lagrangians and equations

| Field | Free Lagrangian density | Equation of motion |
|---|---|---|
| real scalar | $\frac12 \partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2$ | $(\Box+m^2)\phi=0$ |
| complex scalar | $\partial_\mu\phi^\dagger\partial^\mu\phi-m^2\phi^\dagger\phi$ | $(\Box+m^2)\phi=0$ |
| Dirac spinor | $\overline\psi(i\gamma^\mu\partial_\mu-m)\psi$ | $(i\gamma^\mu\partial_\mu-m)\psi=0$ |
| Majorana spinor | $\frac12\overline\psi_M(i\gamma^\mu\partial_\mu-m)\psi_M$ | Dirac equation plus $\psi_M^c=\psi_M$ |
| Maxwell field | $-\frac14F_{\mu\nu}F^{\mu\nu}$ | $\partial_\mu F^{\mu\nu}=0$, with $A_\mu\sim A_\mu+\partial_\mu\alpha$ |
| Proca field | $-\frac14F_{\mu\nu}F^{\mu\nu}+\frac12m^2A_\mu A^\mu$ | $\partial_\mu F^{\mu\nu}+m^2A^\nu=0$, hence $\partial\cdot A=0$ |

Here

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
\qquad
\Box=\partial_t^2-\nabla^2.
$$

The Proca mass-term sign is written in the qft.org mostly-minus convention, so the Proca equation is $\partial_\mu F^{\mu\nu}+m^2A^\nu=0$ and the Hamiltonian is positive after the nondynamical component is eliminated.

## Propagators

The propagators below are momentum-space Feynman propagators. We write

$$
\int_p \equiv \int \frac{d^4p}{(2\pi)^4}.
$$

| Field | Propagator |
|---|---|
| real scalar | $D_F(p)=\dfrac{i}{p^2-m^2+i\epsilon}$ |
| complex scalar | $\langle T\phi(p)\phi^\dagger(-p)\rangle=\dfrac{i}{p^2-m^2+i\epsilon}$ |
| Dirac spinor | $S_F(p)=\dfrac{i(p\!\!/+m)}{p^2-m^2+i\epsilon}$ |
| Majorana spinor | same Dirac numerator and denominator, with Majorana Wick-contraction rules |
| Maxwell field, Feynman gauge | $D_F^{\mu\nu}(p)=\dfrac{-i\eta^{\mu\nu}}{p^2+i\epsilon}$ |
| Maxwell field, covariant gauge | $D_F^{\mu\nu}(p)=\dfrac{-i}{p^2+i\epsilon}\left[\eta^{\mu\nu}-(1-\xi)\dfrac{p^\mu p^\nu}{p^2+i\epsilon}\right]$ |
| Proca field | $D_F^{\mu\nu}(p)=\dfrac{-i}{p^2-m^2+i\epsilon}\left(\eta^{\mu\nu}-\dfrac{p^\mu p^\nu}{m^2}\right)$ |

Gauge-field propagators depend on gauge fixing. This does not make physical amplitudes gauge-dependent. Gauge-dependent terms must cancel or decouple in gauge-invariant quantities.

:::tip[Fast sign check]
With qft.org conventions,

$$
(\Box+m^2)D_F(x)=-i\delta^{(4)}(x),
$$

and

$$
(i\gamma^\mu\partial_\mu-m)S_F(x)=i\delta^{(4)}(x).
$$

These two equations are the quickest way to catch many propagator sign errors.
:::

## Mode expansions

The on-shell measure is

$$
d\mu(p)=\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}},
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

For a real scalar,

$$
\phi(x)=\int d\mu(p)
\left[
a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}
\right].
$$

For a complex scalar,

$$
\phi(x)=\int d\mu(p)
\left[
a(\mathbf p)e^{-ip\cdot x}+b^\dagger(\mathbf p)e^{ip\cdot x}
\right],
$$

where $a^\dagger$ creates particles and $b^\dagger$ creates antiparticles.

For a Dirac field,

$$
\psi(x)=\sum_s\int d\mu(p)
\left[
b_s(\mathbf p)u_s(p)e^{-ip\cdot x}
+d_s^\dagger(\mathbf p)v_s(p)e^{ip\cdot x}
\right].
$$

For a Proca field,

$$
A^\mu(x)=\sum_{r=1}^3\int d\mu(p)
\left[
a_r(\mathbf p)\varepsilon_r^\mu(p)e^{-ip\cdot x}
+a_r^\dagger(\mathbf p)\varepsilon_r^{\mu *}(p)e^{ip\cdot x}
\right].
$$

For a Maxwell field, a similar expansion can be written in a physical gauge using the two transverse photon helicities. Covariant gauges introduce unphysical components that are removed by constraints or BRST methods in the full gauge-theory treatment.

## Canonical brackets

For bosonic fields,

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

For a real scalar,

$$
\pi=\dot \phi.
$$

For a complex scalar, one treats $\phi$ and $\phi^\dagger$ as independent canonical variables, with momenta

$$
\pi=\dot \phi^\dagger,
\qquad
\pi^\dagger=\dot \phi.
$$

For a Dirac field,

$$
\{\psi_\alpha(t,\mathbf x),\psi_\beta^\dagger(t,\mathbf y)\}
=\delta_{\alpha\beta}\delta^{(3)}(\mathbf x-\mathbf y).
$$

For Maxwell and Proca fields, canonical quantization requires constraint analysis. Maxwell has first-class constraints and gauge redundancy. Proca has second-class constraints and no gauge redundancy. This is why their physical spin-one counts differ.

## Spin and polarization sums

The scalar spin sum is trivial. The useful nontrivial sums are:

### Dirac spinors

$$
\boxed{
\sum_s u_s(p)\overline u_s(p)=p\!\!/+m,
\qquad
\sum_s v_s(p)\overline v_s(p)=p\!\!/-m.
}
$$

### Massive vector polarizations

$$
\boxed{
\sum_{r=1}^3
\varepsilon_r^\mu(p)\varepsilon_r^{\nu *}(p)
=-\eta^{\mu\nu}+\frac{p^\mu p^\nu}{m^2}.
}
$$

### Photon polarizations

For a reference vector $n^\mu$ with $n\cdot k\neq0$,

$$
\boxed{
\sum_{\lambda=\pm}
\varepsilon_\lambda^\mu(k;n)\varepsilon_\lambda^{\nu *}(k;n)
= -\eta^{\mu\nu}
+\frac{k^\mu n^\nu+n^\mu k^\nu}{k\cdot n}
-\frac{n^2 k^\mu k^\nu}{(k\cdot n)^2}.
}
$$

Inside conserved-current or gauge-invariant contractions, the reference-vector terms often vanish, allowing the computational shortcut

$$
\sum_{\lambda=\pm}
\varepsilon_\lambda^\mu\varepsilon_\lambda^{\nu *}
\leadsto -\eta^{\mu\nu}.
$$

Do not use this shortcut before verifying the Ward identity or current conservation.

## Mass dimensions

In $d$ spacetime dimensions,

$$
[\phi]=\frac{d-2}{2},
\qquad
[\psi]=\frac{d-1}{2},
\qquad
[A_\mu]=\frac{d-2}{2}.
$$

In four dimensions,

| Object | Dimension |
|---|---:|
| $\partial_\mu$ | 1 |
| $d^4x$ | -4 |
| $\mathcal L$ | 4 |
| scalar field $\phi$ | 1 |
| spinor field $\psi$ | 3/2 |
| vector potential $A_\mu$ | 1 |
| field strength $F_{\mu\nu}$ | 2 |
| scalar source $J\phi$ | $[J]=3$ |
| current coupling $j_\mu A^\mu$ | $[j_\mu]=3$ |

These dimensions come from the kinetic terms. Interactions are then classified by the dimension of their coupling constants.

## Common interaction terms

This table is a preview. The Foundations section introduces interactions later; the point here is to recognize the common free-field building blocks.

| Interaction | Schematic term | Coupling dimension in four dimensions | Comments |
|---|---|---:|---|
| scalar cubic | $g\phi^3/3!$ | 1 | super-renormalizable in four dimensions |
| scalar quartic | $\lambda\phi^4/4!$ | 0 | basic self-interaction |
| complex scalar quartic | $\lambda(\phi^\dagger\phi)^2$ | 0 | preserves global $U(1)$ |
| Yukawa | $y\phi\overline\psi\psi$ | 0 | couples scalar and fermions |
| Abelian gauge coupling | $-j_\mu A^\mu$ | 0 if $j_\mu=q\overline\psi\gamma_\mu\psi$ | requires current conservation/gauge invariance |
| scalar electrodynamics | $|D_\mu\phi|^2$ | 0 | uses $D_\mu=\partial_\mu+iqA_\mu$ |
| Proca current coupling | $-J_\mu A^\mu$ | depends on source | smooth massless limit requires $\partial_\mu J^\mu=0$ |

The phrase "typical interaction" does not mean "allowed in every theory." Symmetries decide which terms are actually present.

## Degrees of freedom by constraint logic

| Field | Components before constraints | Constraint or redundancy | Physical count |
|---|---:|---|---:|
| real scalar | 1 | none | 1 |
| complex scalar | 2 real | none | 2 real |
| massive Dirac | 4 complex components | first-order equation; particle/antiparticle spin states | 4 one-particle states |
| Majorana | 4 real components | reality condition | 2 massive spin states |
| Maxwell | 4 components | gauge redundancy plus Gauss constraint | 2 helicities |
| Proca | 4 components | equation implies $\partial\cdot A=0$ | 3 polarizations |

The Maxwell and Proca rows are worth memorizing together. Maxwell removes unphysical components by gauge redundancy. Proca removes one component by a dynamical constraint and keeps the longitudinal polarization physical.

## Fast comparison of spin zero, one-half, and one

| Feature | Spin zero | Spin one-half | Spin one |
|---|---|---|---|
| Basic free equation | Klein–Gordon | Dirac, Weyl, Majorana | Maxwell or Proca |
| Statistics | bosonic | fermionic | bosonic |
| Field dimension in four dimensions | 1 | 3/2 | 1 |
| Propagator numerator | $1$ | $p\!\!/+m$ | polarization/gauge projector |
| Antiparticles | if complex; real scalar is self-conjugate | Dirac has distinct antiparticles; Majorana is self-conjugate | photon is self-conjugate; charged vectors need complex fields |
| Main subtlety | vacuum energy and normalization | spinor indices and signs | constraints and gauge redundancy |

## Relation to later sections

The next major subsection, **Correlation Functions and Propagators**, will reinterpret these free-field data as vacuum two-point functions and Green functions. The same free-field formulas will reappear in three increasingly powerful languages:

1. operator mode expansions,
2. path-integral Gaussian inverses,
3. perturbative Feynman rules.

For example, the scalar propagator

$$
D_F(p)=\frac{i}{p^2-m^2+i\epsilon}
$$

will be seen as all of the following:

- the time-ordered vacuum two-point function $\langle0|T\phi(x)\phi(y)|0\rangle$,
- the inverse of the quadratic Klein–Gordon operator with Feynman boundary conditions,
- the internal scalar line in perturbation theory.

That three-way identity is one of the reasons free fields are worth getting exactly right.

## Common pitfalls

### Counting components instead of states

Four components of $A_\mu$ do not mean four photons. Four components of a Dirac spinor do not mean four independent classical scalar fields. The physical one-particle interpretation comes after the equation of motion, constraints, and representation theory are applied.

### Forgetting that propagators are convention-sensitive

A different metric convention changes signs in the Klein–Gordon operator, the Dirac numerator, and vector propagators. Always translate through the denominator and equation of motion, not by pattern matching.

### Treating gauge-dependent propagators as observables

Gauge-field propagators are tools. Physical S-matrix elements and gauge-invariant correlation functions are the objects whose gauge independence matters.

### Confusing real, complex, and charged fields

A real scalar is self-conjugate. A complex scalar has independent particle and antiparticle creation operators. A Dirac fermion has distinct particle and antiparticle operators. A Majorana fermion is neutral and self-conjugate. These are not cosmetic differences.

### Using free equations inside interacting operator identities too casually

Free equations hold for free fields. In interacting theories, equations of motion contain interaction terms and composite-operator subtleties. Free-field equations remain essential for asymptotic states and perturbative expansions, but they are not universal operator identities in the interacting theory.

## Exercises

### Exercise 1: Dimensions from kinetic terms

Use the four-dimensional scalar, Dirac, and Maxwell kinetic terms to derive

$$
[\phi]=1,
\qquad
[\psi]=\frac32,
\qquad
[A_\mu]=1.
$$

<details>
<summary><strong>Solution</strong></summary>

In four dimensions, $[\mathcal L]=4$ and $[\partial_\mu]=1$.

For a scalar kinetic term,

$$
\frac12\partial_\mu\phi\partial^\mu\phi,
$$

we have

$$
2+2[\phi]=4,
$$

so

$$
[\phi]=1.
$$

For the Dirac term,

$$
\overline\psi i\gamma^\mu\partial_\mu\psi,
$$

we have

$$
[\overline\psi]+1+[\psi]=4.
$$

Since $[\overline\psi]=[\psi]$,

$$
2[\psi]+1=4,
$$

so

$$
[\psi]=\frac32.
$$

For Maxwell theory,

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
$$

so

$$
[F]=1+[A].
$$

The kinetic term $F_{\mu\nu}F^{\mu\nu}$ has dimension four, so

$$
2(1+[A])=4.
$$

Thus

$$
[A]=1.
$$

</details>

### Exercise 2: Proca transversality

Starting from

$$
\partial_\mu F^{\mu\nu}+m^2A^\nu=0,
$$

show that $\partial_\nu A^\nu=0$ for $m\neq0$.

<details>
<summary><strong>Solution</strong></summary>

Take $\partial_\nu$ of the equation:

$$
\partial_\nu\partial_\mu F^{\mu\nu}+m^2\partial_\nu A^\nu=0.
$$

The first term vanishes because $\partial_\nu\partial_\mu$ is symmetric in $\mu,\nu$, while $F^{\mu\nu}$ is antisymmetric. Therefore

$$
m^2\partial_\nu A^\nu=0.
$$

For $m\neq0$,

$$
\partial_\nu A^\nu=0.
$$

</details>

### Exercise 3: Scalar propagator inversion

Using

$$
D_F(x)=\int_p \frac{i e^{-ip\cdot x}}{p^2-m^2+i\epsilon},
$$

show that

$$
(\Box+m^2)D_F(x)=-i\delta^{(4)}(x).
$$

<details>
<summary><strong>Solution</strong></summary>

With the mostly-minus convention,

$$
\Box e^{-ip\cdot x}=-p^2e^{-ip\cdot x}.
$$

Therefore

$$
(\Box+m^2)D_F(x)
=\int_p \frac{i(-p^2+m^2)e^{-ip\cdot x}}{p^2-m^2+i\epsilon}.
$$

Ignoring the infinitesimal away from its role in boundary conditions,

$$
\frac{-p^2+m^2}{p^2-m^2+i\epsilon}=-1.
$$

Thus

$$
(\Box+m^2)D_F(x)
=-i\int_p e^{-ip\cdot x}
=-i\delta^{(4)}(x).
$$

</details>

### Exercise 4: Dirac propagator inversion

Show that

$$
(i\gamma^\mu\partial_\mu-m)S_F(x)=i\delta^{(4)}(x)
$$

for

$$
S_F(p)=\frac{i(p\!\!/+m)}{p^2-m^2+i\epsilon}.
$$

<details>
<summary><strong>Solution</strong></summary>

In momentum space, $i\partial_\mu$ acting on $e^{-ip\cdot x}$ gives $p_\mu$. Hence the Dirac operator gives

$$
(p\!\!/-m)\frac{i(p\!\!/+m)}{p^2-m^2+i\epsilon}.
$$

Use

$$
(p\!\!/-m)(p\!\!/+m)=p\!\!/p\!\!/-m^2=p^2-m^2.
$$

Therefore the product is

$$
\frac{i(p^2-m^2)}{p^2-m^2+i\epsilon}.
$$

Fourier transforming gives

$$
i\delta^{(4)}(x),
$$

with the $i\epsilon$ again specifying the boundary prescription.

</details>

### Exercise 5: Maxwell degree-of-freedom count

Explain why the Maxwell potential $A_\mu$ has two physical photon helicities, not four.

<details>
<summary><strong>Solution</strong></summary>

The four-vector $A_\mu$ has four components, but Maxwell theory has gauge redundancy:

$$
A_\mu\sim A_\mu+\partial_\mu\alpha.
$$

In Hamiltonian language, $A_0$ is nondynamical and Gauss's law is a first-class constraint. A first-class constraint removes one phase-space direction by the constraint itself and another by the gauge orbit. Equivalently, in momentum space for a photon moving along $z$, only two transverse polarizations survive as physical helicities:

$$
\lambda=+1,
\qquad
\lambda=-1.
$$

The timelike and longitudinal components are gauge or constraint artifacts, not physical photons.

</details>

### Exercise 6: Current conservation and the Proca massless limit

In Proca exchange, the numerator contains $p^\mu p^\nu/m^2$. Show that this term vanishes between conserved currents.

<details>
<summary><strong>Solution</strong></summary>

The dangerous contribution is proportional to

$$
J_\mu(p)\frac{p^\mu p^\nu}{m^2}J'_\nu(-p)
=\frac{(p\cdot J)(p\cdot J')}{m^2}.
$$

For conserved currents,

$$
p\cdot J=0,
\qquad
p\cdot J'=0.
$$

Therefore the longitudinal term contributes zero:

$$
\frac{(p\cdot J)(p\cdot J')}{m^2}=0.
$$

This explains why current conservation is essential for a smooth massless limit of massive-vector exchange.

</details>


## Relation to other pages

- [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/) derives the scalar equations, mode expansion, and scalar propagator.
- [Dirac Field](/foundations/free-fields/dirac-field/) derives the spinor equations, mode expansion, spin sums, and propagator.
- [Weyl and Majorana Fields](/foundations/free-fields/weyl-and-majorana-fields/) explains the chiral and self-conjugate spinor cases.
- [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/) classifies the standard Lorentz-covariant fermion bilinears.
- [Maxwell Field](/foundations/free-fields/maxwell-field/) derives the gauge-field equations, gauge redundancy, and photon propagator logic.
- [Proca Field](/foundations/free-fields/proca-field/) derives the massive-vector constraint, three-polarization count, and Proca propagator.
- [Polarizations](/foundations/free-fields/polarizations/) explains the spin sums and little-group interpretation behind the compact formulas above.

## Research status

- **Established:** The free equations, propagators, canonical brackets, field dimensions, spin sums, and degree-of-freedom counts listed here are textbook-standard.
- **Active:** Efficient free-field bases, especially helicity and spinor-helicity bases, remain central in modern amplitude calculations.
- **Speculative:** None in this page. The page is a convention-locked reference, not a frontier survey.

## Sources and further reading

### Primary references

- E. P. Wigner, "On Unitary Representations of the Inhomogeneous Lorentz Group," *Annals of Mathematics* **40** (1939) 149–204, for the particle-representation foundation.
- P. A. M. Dirac, "The Quantum Theory of the Electron," *Proceedings of the Royal Society A* **117** (1928), for the Dirac equation.
- P. Jordan and W. Pauli, "Zur Quantenelektrodynamik ladungsfreier Felder," *Zeitschrift für Physik* **47** (1928), for early free-field commutator structure.
- A. Proca, "Sur la théorie ondulatoire des électrons positifs et négatifs," *Journal de Physique et le Radium* **7** (1936) 347–353, for the massive vector field.

### Standard textbook treatments

- M. Srednicki, *Quantum Field Theory*, parts I–III, especially §§3, 34–39, 42, and 54–57.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 3, 20–21, and 26–31.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 2, 5, 6, 7, and 8.
- A. Zee, *Quantum Field Theory in a Nutshell*, parts I–III, for a compact physics-first view of scalar, Dirac, and gauge fields.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, chs. 2–5 and 9, for the standard perturbative conventions.

### For a first pass

- Zee, chs. I.3–I.9 and II.1–II.2.
- Srednicki, §§1–5, 34–39, and 54–55.
- Coleman, chs. 3, 20–21, and 26–27.

### For mathematical precision

- Weinberg, Vol. I, chs. 2 and 5, for the representation-theoretic derivation of fields and antiparticles.
- R. Streater and A. Wightman, *PCT, Spin and Statistics, and All That*, for axiomatic free-field and spin-statistics foundations.
- R. Haag, *Local Quantum Physics*, for the operator-algebraic perspective on fields, observables, and sectors.

## Version history

- **2026-05-23:** Initial qft.org free-field summary page, collecting Lagrangians, equations, propagators, spin sums, physical degrees of freedom, mass dimensions, and common interaction previews for scalar, spinor, Maxwell, and Proca fields.
