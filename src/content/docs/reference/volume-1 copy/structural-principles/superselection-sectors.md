---
title: "Superselection Sectors"
description: "How charges, fermion parity, boundary data, and topological labels decompose the Hilbert space into sectors that local observables cannot coherently mix."
sidebar:
  label: "Superselection Sectors"
  order: 7
---

## Summary

A **superselection sector** is a piece of the Hilbert space that cannot be coherently mixed with another piece by the observables under discussion. The slogan is:

$$
\boxed{\text{observables are block diagonal}\quad\Longrightarrow\quad\text{relative phases between blocks are unobservable}.}
$$

If the physical observable algebra is $\mathcal A_{\rm obs}$, a superselection decomposition has the schematic form

$$
\mathcal H=\bigoplus_\alpha \mathcal H_\alpha,
\qquad
P_\alpha A P_\beta=0
\quad (A\in\mathcal A_{\rm obs},\; \alpha\ne\beta),
$$

where $P_\alpha$ projects onto the sector $\mathcal H_\alpha$. A state such as

$$
|\Psi\rangle=a|\psi_\alpha\rangle+b|\chi_\beta\rangle,
\qquad \alpha\ne\beta,
$$

may be a perfectly good vector in a formal enlarged Hilbert space, but no observable in $\mathcal A_{\rm obs}$ can detect the relative phase between $a$ and $b$. For all such observables, it behaves like the incoherent mixture

$$
|a|^2|\psi_\alpha\rangle\langle\psi_\alpha|
+|b|^2|\chi_\beta\rangle\langle\chi_\beta|.
$$

<figure class="doc-figure" style="--figure-width: 40rem;">

![A Hilbert space decomposed into charge sectors, with observables acting block diagonally](/figures/foundations/superselection-sector-map.svg)

<figcaption>

A superselection decomposition of the Hilbert space. Neutral local observables act within each sector. Charged fields or nonlocal intertwiners can map between sectors, but they are not the same as physical neutral observables.

</figcaption>
</figure>

This page is a concept-first guide. The theorem-first account belongs in algebraic QFT, where superselection sectors are studied as inequivalent representations of a net of local observable algebras. Here the goal is to understand why sectors appear, how they differ from ordinary symmetry multiplets, and why QFT forces us to take the distinction between **field algebra** and **observable algebra** seriously.

Weinberg's discussion of projective representations is a useful warning: some apparent superselection rules depend on whether one uses a group or its universal cover, so not every phase in a representation automatically settles what physical superpositions can be prepared (Weinberg 1995, Vol. I, §2.7). In local QFT, the more robust question is: **which operators count as observables, and what sectors do they preserve?**

## Prerequisites

You should know [Internal Symmetries](/foundations/symmetry-and-spacetime/internal-symmetries/), [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/), [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/), [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/), [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/), [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/), [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/), [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/), and [Cluster Decomposition](/foundations/structural-principles/cluster-decomposition/).

:::note[Assumptions]
The cleanest statements below assume a Hilbert-space formulation of a flat-spacetime QFT with a physical algebra of local, gauge-invariant observables. In gauge theories, the observable algebra is not the same as the gauge-fixed field algebra. In infinite volume, different sectors may correspond to inequivalent Hilbert-space representations rather than literal orthogonal subspaces of one separable Hilbert space. In finite volume, some distinctions can be softened by tunneling or boundary conditions.
:::

## The operational definition

Let $\mathcal A_{\rm obs}$ be the algebra of observables we are allowed to measure. A decomposition

$$
\mathcal H=\bigoplus_\alpha\mathcal H_\alpha
$$

is a superselection decomposition if every observable preserves each summand:

$$
A\mathcal H_\alpha\subseteq\mathcal H_\alpha,
\qquad A\in\mathcal A_{\rm obs}.
$$

Equivalently,

$$
P_\alpha A P_\beta=0
\qquad (\alpha\ne\beta).
$$

The projectors $P_\alpha$ are then central relative to the observable algebra:

$$
[P_\alpha,A]=0,
\qquad A\in\mathcal A_{\rm obs}.
$$

That is the algebraic core. A superselection label is a label that all observables preserve.

Now take two normalized vectors $|\psi\rangle\in\mathcal H_\alpha$ and $|\chi\rangle\in\mathcal H_\beta$ with $\alpha\ne\beta$. For

$$
|\Psi\rangle=a|\psi\rangle+b e^{i\theta}|\chi\rangle,
$$

we find

$$
\langle\Psi|A|\Psi\rangle
=|a|^2\langle\psi|A|\psi\rangle
+|b|^2\langle\chi|A|\chi\rangle,
$$

because the cross terms vanish:

$$
\langle\psi|A|\chi\rangle=0,
\qquad
\langle\chi|A|\psi\rangle=0.
$$

The relative phase $\theta$ never appears. That is why a superselection rule is not merely a statement about dynamics. It is a statement about what the observable algebra can distinguish.

## Charge sectors from a commuting charge

The easiest textbook example is a conserved charge $Q$. Suppose physical observables commute with $Q$:

$$
[Q,A]=0,
\qquad A\in\mathcal A_{\rm obs}.
$$

If

$$
Q|\psi_q\rangle=q|\psi_q\rangle,
\qquad
Q|\chi_{q'}\rangle=q'|\chi_{q'}\rangle,
$$

then

$$
0=\langle\chi_{q'}|[Q,A]|\psi_q\rangle
=(q'-q)\langle\chi_{q'}|A|\psi_q\rangle.
$$

Therefore, if $q'\ne q$,

$$
\langle\chi_{q'}|A|\psi_q\rangle=0.
$$

The observable is block diagonal in charge.

This is the clean algebraic statement behind the informal phrase “charge is superselected.” But the phrase hides a choice: **what is counted as an observable?** In a complex scalar theory with a global $U(1)$ symmetry, the charged field $\phi$ obeys a relation of the form

$$
[Q,\phi]=q_\phi\phi,
$$

so it maps one charge sector to another. It is part of a larger field algebra. The neutral subalgebra, built from charge-zero combinations such as $\phi^\dagger\phi$, preserves total charge. If the measuring apparatus and allowed observables are neutral, then total charge sectors are superselected operationally.

That distinction is often the thing students are missing. A symmetry can act nontrivially on fields, but physical measurements may be restricted to invariant combinations.

## Symmetry multiplets are not superselection sectors

A symmetry multiplet is a set of states related by symmetry transformations. A superselection decomposition is a set of sectors that observables cannot coherently mix. These are different ideas.

For example, in an $SU(2)$ theory, a proton and neutron may be treated as two states in an isospin multiplet in an idealized strong-interaction limit. Isospin generators rotate them into each other. That is not, by itself, a superselection rule. It is an ordinary representation of a symmetry.

By contrast, if the observable algebra commutes with a central charge or preserves a boundary flux, then states with different labels cannot be connected by any observable in that algebra. The obstruction is not just “the Hamiltonian happens to conserve the label.” It is that the whole observable algebra is block diagonal.

A useful diagnostic:

| Structure | What it means |
|---|---|
| symmetry multiplet | symmetry generators relate states |
| conserved quantum number | the Hamiltonian preserves a label |
| superselection sector | all physical observables preserve a label |
| inequivalent representation | sectors may not live in one common Hilbert representation |

Every superselection label is conserved by physical observables. Not every conserved label is superselected.

## Fermion parity

Fermion parity is one of the most robust superselection structures in ordinary relativistic QFT. The operator

$$
(-1)^F
$$

takes value $+1$ on states with even fermion number and $-1$ on states with odd fermion number. Local bosonic observables are even in fermion fields, so they commute with $(-1)^F$:

$$
[(-1)^F,A]=0,
\qquad A\in\mathcal A_{\rm obs}.
$$

Thus the physical observable algebra does not see relative phases between even- and odd-fermion sectors.

This is closely related to the spin-statistics theorem, but it is not just a repetition of it. Spin-statistics tells us which fields must commute or anticommute at spacelike separation. Fermion-parity superselection says that odd fermionic operators are not ordinary bosonic observables. They are fields that create or destroy fermionic excitations, and they can appear inside calculations, but physical local measurement operators are even.

This distinction is also why it is misleading to say that anticommuting fields are “unphysical.” Fermion fields are indispensable. They are just not elements of the neutral bosonic observable algebra in the same way as currents, stress tensors, densities, or gauge-invariant bilinears.

## Gauge theories and Gauss law

Gauge theory gives a deeper and more geometric source of sectors. In QED, Gauss law relates total electric charge to electric flux through a sphere at infinity:

$$
Q=\int_{\mathbb R^3} d^3x\,\rho(x)
=\lim_{R\to\infty}\int_{S_R^2} dS_i\,E^i.
$$

A compactly supported gauge-invariant local observable cannot change the flux at spatial infinity. Therefore it cannot change total electric charge.

This is not merely a matter of a global $U(1)$ generator. It is tied to locality and boundary data. Charged states in gauge theory are accompanied by long-range or boundary-sensitive gauge-field data. A charged operator cannot be a strictly local gauge-invariant operator with compact support; it must be dressed, for example by a Wilson line or by a Coulombic dressing. The dressing remembers the boundary.

So in gauge theory, superselection sectors may be labeled by asymptotic fluxes, center charges, topological data, or other boundary conditions. This is one reason algebraic QFT treats observables locally and sectors representation-theoretically: the physical charged sectors can be invisible to strictly local neutral observables but visible through how the representation behaves at infinity.

The foundation-level message is simple:

$$
\boxed{\text{local gauge-invariant observables cannot change boundary charge data}.}
$$

That is why gauge theories naturally produce sectors.

## Spontaneous symmetry breaking and vacuum sectors

Spontaneous symmetry breaking introduces another source of sector-like behavior. In finite volume, a system with a symmetric Hamiltonian often has a unique symmetric ground state. In infinite volume, the thermodynamic limit can produce multiple pure vacua labeled by an order parameter:

$$
\langle\Omega_v|\mathcal O(x)|\Omega_v\rangle=v.
$$

Different vacua can become inequivalent representations of the local observable algebra. A local experiment in one vacuum does not prepare a coherent superposition with a macroscopically different vacuum at infinity.

For a broken discrete symmetry, such as a $\mathbb Z_2$ scalar theory with two vacua, the two infinite-volume vacua behave like distinct sectors. Domain walls interpolate between them, but a finite local observable cannot flip the entire universe from one vacuum to the other.

For a broken continuous global symmetry, the story is subtler because Goldstone modes can produce long-range correlations, and the order parameter lies on a continuous manifold of vacua. Still, the same conceptual distinction appears: local physics is organized around a chosen representation, and different choices of boundary condition at infinity may define different sectors.

This is why cluster decomposition matters. A physical vacuum should give clustering for local observables. A symmetric superposition of infinitely separated broken vacua generally fails to behave like a pure clustered vacuum. Weinberg's treatment of broken global symmetries makes this connection between vacuum choice, clustering, and superselection especially clear in the context of degenerate vacua (Weinberg 1996, Vol. II, §19.1).

## Topological sectors

Topological labels can also define sectors or sector-like decompositions. Examples include:

- winding number sectors in sigma models,
- magnetic flux sectors in gauge theories,
- theta-vacuum sectors in Yang–Mills theory,
- soliton-number sectors in theories with stable topological defects,
- line-operator charge sectors in theories with one-form symmetries.

The precise meaning depends on the theory and on boundary conditions. Sometimes the path integral sums over topological sectors with weights such as $e^{i\theta n}$. Sometimes sectors are separated by superselection rules because no local operator changes the topological label. Sometimes instantons connect classical sectors quantum mechanically, changing what is conserved.

So the safe foundation-level sentence is:

$$
\boxed{\text{topological labels become superselection labels only when the observable algebra cannot change them}.}
$$

Topology alone is not enough. The operator algebra and boundary conditions decide.

## Field algebra versus observable algebra

A recurring source of confusion is that QFT calculations use many operators that are not physical observables.

The **field algebra** may include charged fields, gauge-fixed fields, fermion fields, ghost fields, or nonlocal dressed operators. These are often the most convenient objects for constructing the theory.

The **observable algebra** consists of operators that are gauge invariant, neutral under redundancies, physically measurable, and usually local or localized in an appropriate region. The observable algebra is the natural algebra for superselection.

For example:

| Object | Often in field algebra? | Usually in physical observable algebra? |
|---|---:|---:|
| complex scalar field $\phi$ | yes | no, if observables are charge neutral |
| bilinear $\phi^\dagger\phi$ | yes | yes |
| Dirac field $\psi$ | yes | no, odd fermionic field |
| current $\bar\psi\gamma^\mu\psi$ | yes | yes |
| gauge potential $A_\mu$ | yes, after gauge choice | not by itself |
| field strength $F_{\mu\nu}$ | yes | yes in QED |
| ghost field $c$ | yes in gauge-fixed formalism | no |
| Wilson loop | yes | yes, if gauge invariant |

Superselection rules are clearest when stated for the observable algebra. Charged fields may connect sectors, but that does not mean neutral observables can measure relative phases between sectors.

## Locality and the meaning of “cannot mix”

There are two common meanings of “cannot mix.” They should not be blurred.

First, there is **dynamical conservation**:

$$
[H,Q]=0.
$$

This says time evolution preserves charge. It does not by itself imply superselection, because other operators might still connect different charge sectors.

Second, there is **observable superselection**:

$$
[A,Q]=0
\qquad \text{for all }A\in\mathcal A_{\rm obs}.
$$

This says all observables preserve charge. It is stronger.

Locality often supplies the extra strength. A compactly supported local observable cannot change boundary data at infinity. A gauge-invariant local observable cannot create an isolated net gauge charge without the accompanying long-range dressing. A bosonic local observable cannot be an odd fermion operator. These are not merely accidents of a particular Hamiltonian.

That is why superselection sectors are structural.

## Path-integral viewpoint

In path-integral language, sectors appear in several related ways.

For an ordinary conserved charge, one can project onto fixed-charge sectors by inserting a group average. For a compact $U(1)$ symmetry,

$$
P_Q=\int_0^{2\pi}\frac{d\alpha}{2\pi}\,e^{-i\alpha Q}e^{i\alpha \widehat Q}.
$$

Thermal or Euclidean path integrals can also introduce a chemical potential or twisted boundary condition to keep track of charge sectors.

For topological sectors, the path integral may decompose as

$$
Z=\sum_n Z_n,
$$

or, in a theta vacuum,

$$
Z(\theta)=\sum_n e^{i\theta n}Z_n.
$$

For gauge theories, gauge fixing and BRST introduce a large field algebra, but physical quantities are built from BRST-invariant or gauge-invariant observables. The physical sectors are not read off from the gauge-fixed fields alone; they are read off from the physical observable algebra and boundary conditions.

The path integral is powerful here, but also treacherous. It can make us sum over configurations before we have said which Hilbert space, boundary condition, and observable algebra we mean.

## Common pitfalls

**Pitfall 1: Confusing a conserved quantity with a superselection label.** Conservation by the Hamiltonian is not enough. Superselection is about all physical observables.

**Pitfall 2: Treating charged fields as ordinary observables.** Charged fields are often excellent interpolating fields. They need not be gauge-invariant or neutral observables.

**Pitfall 3: Saying superpositions are mathematically forbidden.** Usually the sharper statement is operational: relative phases between sectors are not observable by the chosen observable algebra.

**Pitfall 4: Forgetting the boundary.** Gauge charges and topological charges often live partly at infinity. Compact local observables cannot change them.

**Pitfall 5: Treating finite volume and infinite volume alike.** In finite volume, tunneling and unique symmetric ground states can blur sector distinctions. In infinite volume, inequivalent representations and broken-vacuum sectors become sharper.

**Pitfall 6: Calling every topological label superselected.** Instantons, defects, boundaries, and allowed nonlocal operators can change the answer.

## Relation to other topics

- [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/) defines conserved charges and their action on fields.
- [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) explains the correlation-function consequences of exact symmetries.
- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) explains why gauge transformations are not ordinary physical symmetries.
- [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/) gives the Gauss-law origin of electric charge sectors.
- [BRST Preview](/foundations/gauge-fields-first-principles/brst-preview/) explains how physical states are selected after gauge fixing.
- [Cluster Decomposition](/foundations/structural-principles/cluster-decomposition/) explains why a physical vacuum should represent one pure phase rather than a macroscopic superposition.
- [Axiomatic QFT Preview](/foundations/structural-principles/axiomatic-qft-preview/) explains how algebraic QFT turns superselection into a representation-theoretic notion.
- Nonperturbative QFT studies vacuum sectors, theta vacua, defects, instantons, and confinement in depth.

## Exercises

### Exercise 1: Block diagonal observables

Let $Q$ be self-adjoint, and suppose $[Q,A]=0$. If $Q|\psi_q\rangle=q|\psi_q\rangle$ and $Q|\chi_{q'}\rangle=q'|\chi_{q'}\rangle$, show that $\langle\chi_{q'}|A|\psi_q\rangle=0$ for $q\ne q'$.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
0=\langle\chi_{q'}|[Q,A]|\psi_q\rangle.
$$

Using $Q|\psi_q\rangle=q|\psi_q\rangle$ and $\langle\chi_{q'}|Q=q'\langle\chi_{q'}|$, this becomes

$$
0=q'\langle\chi_{q'}|A|\psi_q\rangle
-q\langle\chi_{q'}|A|\psi_q\rangle
=(q'-q)\langle\chi_{q'}|A|\psi_q\rangle.
$$

If $q'\ne q$, the matrix element must vanish.

</details>

### Exercise 2: Relative phases are invisible

Let $|\Psi_\theta\rangle=a|\psi_\alpha\rangle+b e^{i\theta}|\chi_\beta\rangle$, with $\alpha\ne\beta$, and suppose $P_\alpha A P_\beta=0$ for every observable $A$. Show that $\langle\Psi_\theta|A|\Psi_\theta\rangle$ is independent of $\theta$.

<details>
<summary><strong>Solution</strong></summary>

Expanding the expectation value gives four terms:

$$
\begin{aligned}
\langle\Psi_\theta|A|\Psi_\theta\rangle
={}&|a|^2\langle\psi_\alpha|A|\psi_\alpha\rangle
+|b|^2\langle\chi_\beta|A|\chi_\beta\rangle \\
&+a^*b e^{i\theta}\langle\psi_\alpha|A|\chi_\beta\rangle
+b^*a e^{-i\theta}\langle\chi_\beta|A|\psi_\alpha\rangle.
\end{aligned}
$$

The cross terms vanish because $A$ is block diagonal between sectors. The remaining terms do not contain $\theta$.

</details>

### Exercise 3: Charged fields as intertwiners

Suppose a field $\Phi_r$ obeys $[Q,\Phi_r]=r\Phi_r$. If $|\psi_q\rangle$ has charge $q$, what is the charge of $\Phi_r|\psi_q\rangle$?

<details>
<summary><strong>Solution</strong></summary>

Act with $Q$:

$$
Q\Phi_r|\psi_q\rangle
=\Phi_r Q|\psi_q\rangle+[Q,\Phi_r]|\psi_q\rangle
=q\Phi_r|\psi_q\rangle+r\Phi_r|\psi_q\rangle.
$$

Therefore

$$
Q\Phi_r|\psi_q\rangle=(q+r)\Phi_r|\psi_q\rangle.
$$

The charged field maps $\mathcal H_q$ into $\mathcal H_{q+r}$.

</details>

### Exercise 4: Fermion parity

Let $A$ be an even polynomial in fermion creation and annihilation operators. Show that $A$ commutes with $(-1)^F$.

<details>
<summary><strong>Solution</strong></summary>

Each fermion creation or annihilation operator changes fermion number by one, so it anticommutes with $(-1)^F$ in the sense that

$$
(-1)^F a (-1)^F=-a,
\qquad
(-1)^F a^\dagger (-1)^F=-a^\dagger.
$$

An even monomial contains an even number of such operators, so it picks up an even number of minus signs. Hence

$$
(-1)^F A (-1)^F=A,
$$

which is equivalent to $[(-1)^F,A]=0$.

</details>

### Exercise 5: Gauss law and local observables

In QED, explain why a gauge-invariant operator supported in a bounded region cannot change the electric flux through a sphere at spatial infinity.

<details>
<summary><strong>Solution</strong></summary>

The electric flux at infinity is determined by fields arbitrarily far from the bounded region. A compactly supported local gauge-invariant operator cannot alter the asymptotic electric field. By Gauss law, the flux at infinity equals total charge. Therefore such an operator cannot change the total charge sector.

A charged operator must carry a dressing that reaches to infinity or otherwise changes boundary data; it is not a strictly compact local gauge-invariant observable.

</details>

### Exercise 6: Broken vacua and clustering

Why can a symmetric superposition of two infinite-volume broken vacua fail to be the right vacuum for a clustered phase?

<details>
<summary><strong>Solution</strong></summary>

Let the two vacua have opposite values of an order parameter $\mathcal O$:

$$
\langle\Omega_+|\mathcal O|\Omega_+\rangle=v,
\qquad
\langle\Omega_-|\mathcal O|\Omega_-\rangle=-v.
$$

A symmetric superposition can have zero one-point function, but its distant two-point function can retain memory of the two components rather than factorizing as a pure phase would. In the infinite-volume limit, the two vacua represent distinct boundary conditions or inequivalent representations. A pure clustered vacuum chooses one phase.

</details>

## Sources and further reading

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§2.2 and 2.7, for symmetries, projective representations, covering groups, and the cautionary discussion of superselection rules.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, §19.1 and ch. 23, for broken vacua, cluster decomposition, theta angles, and topological sectors.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 6, 27, 31, 43, and 46, for internal symmetries, charges, gauge invariance, Faddeev–Popov gauge fixing, and spontaneous symmetry breaking.
- M. Srednicki, *Quantum Field Theory*, §§22–24, 54–61, 69–74, and 82–84, for currents, discrete symmetries, gauge fields, BRST, Wilson loops, and gauge-theory sectors.
- R. Haag, *Local Quantum Physics*, for the algebraic QFT formulation of superselection sectors and local observable algebras.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for the Wightman-framework background.
- S. Doplicher, R. Haag, and J. E. Roberts, “Local observables and particle statistics,” for the classic DHR superselection analysis.
- J. Fröhlich, G. Morchio, and F. Strocchi, “Charged sectors and scattering states in quantum electrodynamics,” for charged sectors in QED.

## Version history

- **2026-05-24:** Initial qft.org page on superselection sectors, observable algebras, charge sectors, fermion parity, Gauss law, broken vacua, topological labels, path-integral projections, and exercises.
