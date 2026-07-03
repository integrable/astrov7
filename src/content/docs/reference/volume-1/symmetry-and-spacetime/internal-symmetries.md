---
title: "Internal Symmetries"
description: "Global internal symmetries in QFT: field multiplets, Lie groups, representations, invariant tensors, selection rules, and the distinction between ordinary global symmetry and gauge redundancy."
sidebar:
  label: "Internal Symmetries"
  order: 4
---

## Summary

An **internal symmetry** acts on field labels, not on spacetime points. A spacetime symmetry moves or rotates the argument of a field,

$$
x^\mu\mapsto x'^\mu=\Lambda^\mu{}_{\nu}x^\nu+a^\mu,
$$

while an internal symmetry transforms fields at the same point:

$$
\boxed{
\Phi_i(x)\mapsto \Phi'_i(x)=D_R(g)_i{}^j\Phi_j(x),
\qquad x\text{ fixed}.}
$$

Here $g$ is an element of a group $G$, $D_R(g)$ is a matrix in a representation $R$ of $G$, and $i,j$ label components inside a multiplet. Coleman phrases this nicely: internal symmetries are “non-geometrical” symmetries; they do not relate fields at different spacetime points, but transform fields at the same point into one another (Coleman 2019, ch. 6). Srednicki develops the same idea through continuous currents and then non-Abelian examples such as $SO(N)$ and $SU(N)$ multiplets (Srednicki 2007, §§22 and 24). Weinberg uses internal symmetries as part of the general symmetry structure of QFT, including their role in conserved charges, Ward identities, and spontaneous symmetry breaking (Weinberg 1995, Vol. I, §7.3; Vol. II, ch. 19).

Internal symmetries are where “particles with the same spacetime quantum numbers” become organized into multiplets: the real and imaginary parts of a complex scalar, the components of an isospin doublet, the flavors of a fermion multiplet, or the adjoint components of a current. They constrain the Lagrangian, correlation functions, and scattering amplitudes by forcing all allowed local terms to be singlets under the symmetry group.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Internal symmetry map](/figures/foundations/internal-symmetry-map.svg)

<figcaption>

A global internal group $G$ acts on the components of a field multiplet $\Phi_i(x)$ at fixed spacetime point $x$. Representation matrices and invariant tensors determine the allowed singlet terms in $\mathcal L$, the Noether currents $j_a^\mu$, the charge algebra, and the resulting selection rules. Promoting the constant parameter $\alpha^a$ to $\alpha^a(x)$ is a different problem: it requires gauge fields or constraints.

</figcaption>
</figure>

## Prerequisites

You should know [Noether Theorem](/foundations/classical-field-theory/noether-theorem/), [Scalar Fields](/foundations/classical-field-theory/scalar-fields/), [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/), [Poincaré Symmetry](/foundations/symmetry-and-spacetime/poincare-symmetry/), [Lorentz Representations](/foundations/symmetry-and-spacetime/lorentz-representations/), and [Spinors from Lorentz Symmetry](/foundations/symmetry-and-spacetime/spinors-from-lorentz-symmetry/).

:::note[Conventions]
This page uses Hermitian Lie-algebra generators,

$$
[T_R^a,T_R^b]=if^{ab}{}_cT_R^c.
$$

A field in representation $R$ transforms as

$$
\Phi(x)\mapsto e^{-i\alpha^aT_R^a}\Phi(x),
\qquad
\delta\Phi=-i\alpha^aT_R^a\Phi.
$$

The corresponding Hilbert-space operator is written

$$
U(\alpha)=e^{i\alpha^aQ_a},
\qquad
U(\alpha)\Phi U(\alpha)^{-1}=e^{-i\alpha^aT_R^a}\Phi,
$$

so that

$$
[Q_a,\Phi_i]=-(T_R^a)_i{}^j\Phi_j.
$$

Some books use the opposite sign convention for $Q_a$ or $T_R^a$. The invariant content is unchanged once one convention is used consistently.
:::

## What internal means

A spacetime symmetry changes the coordinates, or the inertial frame, or both. For example, a scalar field transforms under a Poincaré transformation by

$$
\phi(x)\mapsto \phi'(x')=\phi(x).
$$

The field value is compared at different spacetime points. Lorentz representations then tell us how tensor or spinor indices rotate or boost.

An internal symmetry does not do this. It acts at each spacetime point independently of the spacetime coordinates, but with the same group element everywhere for a **global** symmetry. For a multiplet $\Phi_i(x)$,

$$
\Phi_i(x)\mapsto D_R(g)_i{}^j\Phi_j(x).
$$

The symbol $R$ denotes a representation of $G$. A representation respects group multiplication:

$$
D_R(g_1g_2)=D_R(g_1)D_R(g_2),
\qquad
D_R(e)=\mathbf 1.
$$

For a connected Lie group, a transformation near the identity may be written as

$$
D_R(g)=\exp[-i\alpha^a T_R^a].
$$

The generators obey the Lie algebra

$$
\boxed{
[T_R^a,T_R^b]=if^{ab}{}_cT_R^c.}
$$

If all $f^{ab}{}_c$ vanish, the group is Abelian. If some are nonzero, the group is non-Abelian. The group $U(1)$ is Abelian. The groups $SU(N)$ for $N\ge2$ and $SO(N)$ for $N\ge3$ are non-Abelian.

:::note[Internal versus spacetime]
For ordinary internal symmetries, the charges commute with the connected Poincaré generators:

$$
[Q_a,P^\mu]=0,
\qquad
[Q_a,M^{\mu\nu}]=0.
$$

This is why internal charges are Lorentz scalars. Supersymmetry is different: its generators transform as spinors, so it is not an ordinary internal symmetry.
:::

## Multiplets and singlets

A field multiplet is a collection of fields that the symmetry mixes. For example, a pair of real scalar fields

$$
\phi_1(x),\quad \phi_2(x)
$$

may be grouped as

$$
\vec\phi(x)=
\begin{pmatrix}
\phi_1(x)\\
\phi_2(x)
\end{pmatrix}.
$$

The rotation

$$
\vec\phi(x)\mapsto
\begin{pmatrix}
\cos\alpha & \sin\alpha\\
-\sin\alpha & \cos\alpha
\end{pmatrix}
\vec\phi(x)
$$

is an internal $SO(2)$ symmetry if the Lagrangian depends on the fields only through rotationally invariant combinations such as

$$
\phi_1^2+\phi_2^2,
\qquad
\partial_\mu\phi_1\partial^\mu\phi_1+
\partial_\mu\phi_2\partial^\mu\phi_2.
$$

Equivalently, define

$$
\phi=\frac{1}{\sqrt2}(\phi_1+i\phi_2).
$$

Then the same symmetry is the phase rotation

$$
\phi(x)\mapsto e^{-i\alpha}\phi(x).
$$

This is the familiar $U(1)$ symmetry of a complex scalar field. The equality between the real $SO(2)$ description and the complex $U(1)$ description is not a new physical symmetry; it is two notations for the same rotation in field space.

The practical rule is simple:

```txt
Allowed local terms in the Lagrangian must be singlets under every exact global symmetry.
```

If $\Phi$ transforms in a unitary representation $R$, then $\Phi^\dagger\Phi$ is a singlet:

$$
\Phi^\dagger\Phi
\mapsto
\Phi^\dagger U_R^\dagger U_R\Phi
=\Phi^\dagger\Phi.
$$

More complicated singlets are built by contracting indices with invariant tensors.

## Invariant tensors

An invariant tensor is a tensor whose components are unchanged by the group action. These are the building blocks for symmetry-invariant Lagrangians.

For $SO(N)$, the most basic invariant tensor is

$$
\delta_{ij}.
$$

It lets us build terms such as

$$
\phi_i\phi_i,
\qquad
\partial_\mu\phi_i\partial^\mu\phi_i,
\qquad
(\phi_i\phi_i)^2.
$$

For $SU(N)$, the fundamental invariant tensors include

$$
\delta^i{}_j,
\qquad
\epsilon_{i_1i_2\cdots i_N}.
$$

The tensor $\delta^i{}_j$ contracts a fundamental index with an antifundamental index, while $\epsilon_{i_1\cdots i_N}$ builds antisymmetric singlets from $N$ fundamentals. In the adjoint representation, non-Abelian groups also carry structure constants $f^{ab}{}_c$, defined by

$$
[T^a,T^b]=if^{ab}{}_cT^c.
$$

For $SU(N)$ one also encounters symmetric tensors $d^{abc}$, defined by the anticommutator of generators in the fundamental representation. Which invariant tensors exist is not a cosmetic detail: it determines which interaction terms can appear.

For example, if $\Phi_i$ is an $SU(N)$ fundamental scalar, then

$$
\Phi^\dagger_i\Phi_i
$$

is invariant, but

$$
\Phi_i\Phi_i
$$

is not an invariant expression for a general $SU(N)$ fundamental. The index structure itself tells you what the symmetry allows.

## Abelian example: complex scalar

The complex scalar Lagrangian

$$
\mathcal L
=\partial_\mu\phi^\dagger\partial^\mu\phi
-m^2\phi^\dagger\phi
-V(\phi^\dagger\phi)
$$

is invariant under

$$
\phi\mapsto e^{-iq\alpha}\phi,
\qquad
\phi^\dagger\mapsto e^{iq\alpha}\phi^\dagger,
$$

where $q$ is the charge of the field and $\alpha$ is constant.

Noether's theorem gives the current

$$
\boxed{
j^\mu=iq\,\phi^\dagger\overleftrightarrow{\partial^\mu}\phi
=iq\left(\phi^\dagger\partial^\mu\phi-(\partial^\mu\phi^\dagger)\phi\right).}
$$

Here

$$
f\overleftrightarrow{\partial^\mu}g
\equiv f\partial^\mu g-(\partial^\mu f)g.
$$

The corresponding charge is

$$
Q=\int d^3x\,j^0(x).
$$

After canonical quantization, this charge counts particles minus antiparticles:

$$
Q=q(N_a-N_b)
$$

for the free complex scalar. This result was derived in [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/). It is the first place where a classical internal symmetry becomes a particle-number selection rule.

A real scalar field does not carry a conserved $U(1)$ charge of this kind. A complex scalar field does because its two real components form a two-dimensional internal multiplet.

## Nonabelian example: real O(N) scalars

Take $N$ real scalar fields $\phi_i(x)$ with

$$
\boxed{
\mathcal L
=\frac12\partial_\mu\phi_i\partial^\mu\phi_i
-\frac12m^2\phi_i\phi_i
-\frac{\lambda}{4}(\phi_i\phi_i)^2.}
$$

This Lagrangian is invariant under

$$
\phi_i(x)\mapsto R_i{}^j\phi_j(x),
\qquad
R^TR=1.
$$

The connected part is $SO(N)$; including reflections gives $O(N)$. For infinitesimal $SO(N)$ transformations,

$$
R_i{}^j=\delta_i{}^j+\omega_i{}^j,
\qquad
\omega_{ij}=-\omega_{ji}.
$$

There are $N(N-1)/2$ independent generators, one for each plane of rotation in the internal field space. When $N=2$, the group has only one generator and is Abelian. When $N\ge3$, the rotations in different internal planes do not commute, and the group is non-Abelian.

The Noether current for the rotation in the $ij$ plane is proportional to

$$
j_{ij}^\mu
=\phi_i\partial^\mu\phi_j-
\phi_j\partial^\mu\phi_i,
\qquad
j_{ij}^\mu=-j_{ji}^\mu.
$$

The conservation of all these currents expresses the fact that the dynamics does not prefer one internal direction over another. In condensed-matter language this is the symmetry behind $O(N)$ vector models; in particle physics it is the prototype for multiplet symmetries such as isospin.

## Nonabelian example: complex SU(N) multiplet

Let $\Phi_i(x)$ be $N$ complex scalar fields in the fundamental representation of $SU(N)$. The transformation law is

$$
\Phi_i(x)\mapsto U_i{}^j\Phi_j(x),
\qquad
U\in SU(N),
\qquad
U^\dagger U=1,
\qquad
\det U=1.
$$

The infinitesimal form is

$$
\delta\Phi_i=-i\alpha^a(T^a)_i{}^j\Phi_j,
\qquad
\delta\Phi^\dagger_i=+i\alpha^a\Phi^\dagger_j(T^a)_j{}^i.
$$

For

$$
\mathcal L
=\partial_\mu\Phi^\dagger_i\partial^\mu\Phi_i
-m^2\Phi^\dagger_i\Phi_i
-\frac{\lambda}{4}(\Phi^\dagger_i\Phi_i)^2,
$$

the currents are

$$
\boxed{
j_a^\mu
=i\,\Phi^\dagger T_a\overleftrightarrow{\partial^\mu}\Phi.}
$$

The charges

$$
Q_a=\int d^3x\,j_a^0(x)
$$

obey the same Lie algebra as the generators:

$$
\boxed{
[Q_a,Q_b]=if_{ab}{}^cQ_c.}
$$

For a non-Abelian group, the individual charges cannot all be simultaneously diagonalized. Instead, one chooses a commuting Cartan subalgebra and labels states by its eigenvalues, while the remaining generators act as raising and lowering operators inside multiplets.

This is exactly what happens in familiar angular momentum theory. The spin operators $J_x,J_y,J_z$ do not commute, so states are labeled by $J^2$ and $J_z$, not by all three components. Non-Abelian internal symmetries work similarly, except that the group acts on internal labels rather than on spatial orientation.

## What symmetry forbids

Internal symmetry is often most powerful when it says what cannot happen.

A Lagrangian with a $U(1)$ symmetry cannot contain terms such as

$$
\phi^2+\phi^{\dagger 2}
$$

unless the field is neutral or the symmetry is explicitly broken. This term carries charge and is not a singlet.

An $SU(N)$ theory with a fundamental field $\Phi_i$ cannot contain arbitrary tensors with free internal indices. All internal indices must be contracted to a singlet. For example,

$$
\Phi^\dagger_i M^i{}_j\Phi^j
$$

is invariant under the full $SU(N)$ only if $M$ is proportional to the identity. If $M$ has unequal eigenvalues, it picks preferred internal directions and explicitly breaks the symmetry to a subgroup.

This is why equal masses inside a multiplet are a diagnostic of an unbroken internal symmetry. If fields $\Phi_1,\ldots,\Phi_N$ form an irreducible multiplet of an exact symmetry, the mass term must be proportional to the identity in that multiplet. Different masses mean either that the symmetry is absent, approximate, explicitly broken, or spontaneously realized in a less obvious way.

## Symmetry in the operator language

In the quantum theory, a continuous global internal symmetry is generated by Hermitian charges $Q_a$. With the convention used above,

$$
U(\alpha)=e^{i\alpha^aQ_a},
$$

and a field in representation $R$ transforms as

$$
U(\alpha)\Phi_i(x)U(\alpha)^{-1}
=\left(e^{-i\alpha^aT_R^a}\right)_i{}^j\Phi_j(x).
$$

Infinitesimally,

$$
\boxed{
[Q_a,\Phi_i(x)]=-(T_R^a)_i{}^j\Phi_j(x).}
$$

If the symmetry is exact and unbroken, the charges commute with the Hamiltonian,

$$
[Q_a,H]=0.
$$

Therefore time evolution preserves the representation content of states. A state that begins with total electric charge $q$ cannot evolve into a state with charge $q'\ne q$. For non-Abelian symmetries, scattering amplitudes must transform as invariant tensors; equivalently, the tensor product of external representations must contain a singlet for a fully invariant amplitude to exist.

This is the operator version of the classical singlet rule for the Lagrangian.

:::caution[Vacuum assumptions]
The statement “the symmetry is generated by charges $Q_a$” assumes that the charge operators are well-defined on the states being considered. In theories with spontaneous symmetry breaking, massless modes, gauge constraints, or nontrivial boundary conditions, the current may exist while the global charge has subtleties. The next page, [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/), treats this more carefully.
:::

## Symmetry in the path integral

In the path integral, a transformation is a quantum symmetry only if both the action and the measure are invariant:

$$
S[\Phi']=S[\Phi],
\qquad
\mathcal D\Phi'=\mathcal D\Phi.
$$

This second condition is easy to forget. A transformation can be a symmetry of the classical action but fail to be a symmetry of the regulated quantum measure. When that happens, the symmetry is **anomalous**.

For ordinary scalar multiplets with linear unitary transformations, the measure is usually harmless. For chiral fermions, the measure can carry a nontrivial Jacobian. This is one reason anomalies are not optional fine print: they decide whether a proposed global or gauge symmetry actually survives quantization. The Foundations page [Path Integral Measure](/foundations/path-integral-formalism/path-integral-measure/) gives the first preview; the full story belongs in the later Symmetry, Anomalies, and Topology group.

The path-integral viewpoint also gives the most economical route to Ward identities. If the change of variables preserves the measure, then the integral of a total variation vanishes. That statement becomes a relation among correlation functions. This page stops before deriving those identities; see [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/).

## Global, local, exact, approximate, accidental

Several words are used around internal symmetries. They should not be blended together.

**Global symmetry.** The parameter is constant in spacetime:

$$
\alpha^a=\text{constant}.
$$

A global symmetry relates physically distinct configurations or states. It usually has conserved Noether currents and charges.

**Local gauge redundancy.** The parameter is allowed to vary:

$$
\alpha^a=\alpha^a(x).
$$

This is not automatically a physical global symmetry. To make a local version consistent, one usually introduces gauge fields and covariant derivatives. Gauge transformations relate different descriptions of the same physical configuration, not different physical states. The first-principles gauge pages later in Foundations make this distinction explicit.

**Exact symmetry.** The full quantum theory, including regulator, counterterms, and measure, preserves the symmetry. Exact symmetries imply exact selection rules.

**Approximate symmetry.** The symmetry is broken by small terms. Isospin in hadron physics is a classic approximate internal symmetry: it works well because some parameters are close, but it is not exact.

**Accidental symmetry.** A symmetry may appear because the field content and low-dimension operators happen not to allow symmetry-breaking terms. Such a symmetry need not survive once higher-dimension operators or ultraviolet physics are included.

**Anomalous symmetry.** The classical action has the symmetry, but the quantum measure or regulator does not. An anomalous global symmetry can still be useful; an anomalous gauge symmetry is usually inconsistent unless the anomaly cancels.

## Relation to gauge symmetry

Internal symmetries are the seed from which gauge theories grow, but they are not the same thing.

For a global $U(1)$ symmetry,

$$
\phi(x)\mapsto e^{-iq\alpha}\phi(x),
$$

with constant $\alpha$, the derivative transforms in the same way:

$$
\partial_\mu\phi(x)\mapsto e^{-iq\alpha}\partial_\mu\phi(x).
$$

If $\alpha$ depends on $x$, then

$$
\partial_\mu(e^{-iq\alpha(x)}\phi)
=e^{-iq\alpha(x)}\left(\partial_\mu\phi-iq(\partial_\mu\alpha)\phi\right),
$$

and the extra derivative of $\alpha$ spoils invariance. The cure is to introduce a gauge field and a covariant derivative,

$$
D_\mu\phi=(\partial_\mu+iqA_\mu)\phi,
$$

with a compensating transformation of $A_\mu$. That construction belongs to [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) and [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/).

The moral:

```txt
Global symmetry is a physical symmetry of states.
Gauge symmetry is a redundancy of description.
```

They are related, but confusing them is one of the fastest ways to get lost in QFT.

## Operator, path-integral, structural lenses

The same internal symmetry has three equivalent faces.

**Operator lens.** There are charges $Q_a$ that generate transformations of fields and states:

$$
[Q_a,\Phi_i]=-(T_a)_i{}^j\Phi_j.
$$

If $[Q_a,H]=0$, the symmetry gives selection rules.

**Path-integral lens.** A change of variables leaves $S$ and $\mathcal D\Phi$ invariant. Functional identities follow from the vanishing of the integral of a total variation.

**Structural lens.** The Hilbert space decomposes into representations of $G$; local operators transform in representations of $G$; correlation functions and amplitudes must combine into singlets. This is why group theory is not a decorative afterthought. It is part of the grammar of QFT.

## Common pitfalls

**Calling every internal symmetry a gauge symmetry.** A global $SU(N)$ flavor symmetry and a local Yang–Mills gauge redundancy are different structures. A global transformation can change a physical state; a gauge transformation changes the description.

**Forgetting the measure.** In the path integral, symmetry of the action is not always symmetry of the quantum theory. The measure and regulator matter.

**Diagonalizing all non-Abelian charges.** Non-Abelian generators do not all commute. States are labeled by commuting Cartan charges and Casimirs, not by every generator separately.

**Mistaking a basis choice for a symmetry.** You can always relabel fields by an invertible linear transformation. It is a symmetry only if it leaves the action, measure, and physical structure invariant.

**Ignoring explicit breaking.** Unequal masses or couplings inside a would-be multiplet usually break the symmetry. Approximate symmetries are useful precisely because the breaking terms are small and controlled.

**Treating anomalies as optional.** An anomalous global symmetry may still organize physics, but an anomalous gauge redundancy is a consistency problem.

## Relations to other pages

- [Noether Theorem](/foundations/classical-field-theory/noether-theorem/) derives the current associated with a continuous symmetry.
- [Scalar Fields](/foundations/classical-field-theory/scalar-fields/) introduces the complex-scalar $U(1)$ current.
- [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/) quantizes the charged scalar and shows that the charge counts particles minus antiparticles.
- [Poincaré Symmetry](/foundations/symmetry-and-spacetime/poincare-symmetry/) and [Lorentz Representations](/foundations/symmetry-and-spacetime/lorentz-representations/) treat spacetime symmetries rather than internal ones.
- [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/) will study the current algebra and charge action more carefully.
- [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) will turn internal symmetry into identities among correlation functions.
- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) will explain what changes when an internal symmetry is promoted to a local redundancy.

## Research status

- **Established:** Global internal symmetries, Lie algebras, representation multiplets, invariant tensors, Noether currents, and charge selection rules are textbook-standard.
- **Subtle:** Whether a classical internal symmetry survives quantization depends on the regulator and measure. Spontaneous breaking, boundary conditions, infrared effects, and anomalies can all change how currents and charges are realized.
- **Beyond this page:** Spontaneous symmetry breaking, Goldstone bosons, anomaly matching, generalized global symmetries, higher-form symmetries, and non-invertible symmetries belong to later parts of qft.org.

## Exercises

### Exercise 1: U(1) invariance of the complex scalar

Show that

$$
\mathcal L
=\partial_\mu\phi^\dagger\partial^\mu\phi
-m^2\phi^\dagger\phi
-\lambda(\phi^\dagger\phi)^2
$$

is invariant under

$$
\phi\mapsto e^{-iq\alpha}\phi,
\qquad
\phi^\dagger\mapsto e^{iq\alpha}\phi^\dagger,
$$

for constant $\alpha$.

<details>
<summary><strong>Solution</strong></summary>

The mass and interaction terms depend only on $\phi^\dagger\phi$. Under the transformation,

$$
\phi^\dagger\phi
\mapsto
(e^{iq\alpha}\phi^\dagger)(e^{-iq\alpha}\phi)
=\phi^\dagger\phi.
$$

For constant $\alpha$,

$$
\partial_\mu\phi
\mapsto e^{-iq\alpha}\partial_\mu\phi,
\qquad
\partial_\mu\phi^\dagger
\mapsto e^{iq\alpha}\partial_\mu\phi^\dagger.
$$

Therefore

$$
\partial_\mu\phi^\dagger\partial^\mu\phi
\mapsto
\partial_\mu\phi^\dagger\partial^\mu\phi.
$$

All terms are invariant, so the Lagrangian is invariant.

</details>

### Exercise 2: Derive the U(1) current

Using

$$
\delta\phi=-iq\alpha\phi,
\qquad
\delta\phi^\dagger=iq\alpha\phi^\dagger,
$$

derive the Noether current for the complex scalar.

<details>
<summary><strong>Solution</strong></summary>

The Noether current is

$$
\alpha j^\mu
=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\delta\phi
+\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^\dagger)}\delta\phi^\dagger.
$$

For

$$
\mathcal L=\partial_\nu\phi^\dagger\partial^\nu\phi-V(\phi^\dagger\phi),
$$

we have

$$
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}=\partial^\mu\phi^\dagger,
\qquad
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^\dagger)}=\partial^\mu\phi.
$$

Thus

$$
\alpha j^\mu
=(\partial^\mu\phi^\dagger)(-iq\alpha\phi)
+(\partial^\mu\phi)(iq\alpha\phi^\dagger).
$$

Cancel $\alpha$ and rewrite:

$$
\boxed{
j^\mu=iq\left(\phi^\dagger\partial^\mu\phi
-(\partial^\mu\phi^\dagger)\phi\right)
=iq\,\phi^\dagger\overleftrightarrow{\partial^\mu}\phi.}
$$

</details>

### Exercise 3: Invariance of the O(N) scalar theory

Let $R^TR=1$ and define

$$
\phi_i\mapsto R_i{}^j\phi_j.
$$

Show that $\phi_i\phi_i$ and $\partial_\mu\phi_i\partial^\mu\phi_i$ are invariant.

<details>
<summary><strong>Solution</strong></summary>

For the quadratic field term,

$$
\phi_i\phi_i
\mapsto
R_i{}^j\phi_j R_i{}^k\phi_k
=(R^TR)^{jk}\phi_j\phi_k
=\delta^{jk}\phi_j\phi_k
=\phi_j\phi_j.
$$

For the kinetic term, $R$ is constant, so

$$
\partial_\mu\phi_i
\mapsto R_i{}^j\partial_\mu\phi_j.
$$

Therefore

$$
\partial_\mu\phi_i\partial^\mu\phi_i
\mapsto
R_i{}^jR_i{}^k
\partial_\mu\phi_j\partial^\mu\phi_k
=\delta^{jk}\partial_\mu\phi_j\partial^\mu\phi_k.
$$

So the kinetic term is invariant.

</details>

### Exercise 4: Why unequal masses break SU(N)

Consider $N$ complex fields $\Phi_i$ with mass term

$$
\mathcal L_m=-\Phi_i^\dagger M^i{}_j\Phi^j.
$$

Show that this term is invariant under all $SU(N)$ transformations only if $M$ commutes with all $SU(N)$ matrices. For the fundamental irreducible representation, this implies $M$ is proportional to the identity.

<details>
<summary><strong>Solution</strong></summary>

Under $\Phi\mapsto U\Phi$,

$$
\Phi^\dagger M\Phi
\mapsto
\Phi^\dagger U^\dagger M U\Phi.
$$

For this to equal $\Phi^\dagger M\Phi$ for arbitrary $\Phi$, we need

$$
U^\dagger M U=M,
$$

or equivalently

$$
MU=UM
$$

for every $U\in SU(N)$. In an irreducible representation, Schur's lemma says that a matrix commuting with all representation matrices must be proportional to the identity:

$$
M=m^2\mathbf 1.
$$

Thus unequal masses break the full $SU(N)$ symmetry.

</details>

### Exercise 5: Selection rule from charge conservation

Suppose $Q$ is an exact conserved charge and

$$
Q|i\rangle=q_i|i\rangle,
\qquad
Q|f\rangle=q_f|f\rangle.
$$

If the scattering operator $S$ commutes with $Q$, show that $\langle f|S|i\rangle$ can be nonzero only when $q_f=q_i$.

<details>
<summary><strong>Solution</strong></summary>

Since $[Q,S]=0$,

$$
\langle f|QS|i\rangle=\langle f|SQ|i\rangle.
$$

Using the charge eigenvalue equations,

$$
q_f\langle f|S|i\rangle=q_i\langle f|S|i\rangle.
$$

Therefore

$$
(q_f-q_i)\langle f|S|i\rangle=0.
$$

If $q_f\neq q_i$, then

$$
\boxed{\langle f|S|i\rangle=0.}
$$

This is the simplest selection rule.

</details>

### Exercise 6: Why local U(1) needs a gauge field

Let

$$
\phi(x)\mapsto e^{-iq\alpha(x)}\phi(x).
$$

Show explicitly that $\partial_\mu\phi$ does not transform in the same way as $\phi$ unless $\alpha$ is constant.

<details>
<summary><strong>Solution</strong></summary>

Differentiate the transformed field:

$$
\partial_\mu(e^{-iq\alpha(x)}\phi)
=e^{-iq\alpha(x)}\partial_\mu\phi
-iq(\partial_\mu\alpha)e^{-iq\alpha(x)}\phi.
$$

This is

$$
e^{-iq\alpha(x)}
\left(\partial_\mu\phi-iq(\partial_\mu\alpha)\phi\right).
$$

The second term is absent only when

$$
\partial_\mu\alpha=0,
$$

that is, when $\alpha$ is constant. Therefore the ordinary derivative transforms covariantly under global $U(1)$ transformations but not under local ones. A gauge field is introduced precisely to cancel this extra term.

</details>

## Sources and further reading

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 6, for the clean distinction between internal and spacetime symmetries and the construction of internal Noether currents.
- M. Srednicki, *Quantum Field Theory*, §§22 and 24, for continuous currents, $U(1)$ charges, $SO(N)$ and $SU(N)$ generator conventions, and non-Abelian current algebra.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§2.2 and 7.3, for symmetry generators, global symmetries, and Noether currents in the general QFT framework.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, ch. 19, for spontaneous breaking of global internal symmetries and the role of vacuum degeneracy.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. I.10 and Appendix B, for a compact physical introduction to internal symmetries and group theory.
- H. Georgi, *Lie Algebras in Particle Physics*, for a focused treatment of internal symmetry groups, representations, tensor methods, and particle-physics applications.

## Version history

- **2026-05-23:** Initial qft.org page on global internal symmetries, field multiplets, representation matrices, invariant tensors, Abelian and non-Abelian examples, selection rules, global-versus-gauge distinctions, and the operator/path-integral/structural lenses.
