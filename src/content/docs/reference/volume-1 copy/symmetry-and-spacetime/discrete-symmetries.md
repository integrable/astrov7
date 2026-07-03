---
title: "Discrete Symmetries"
description: "Parity, time reversal, charge conjugation, intrinsic phases, field transformations, selection rules, CP and CPT previews, and the operator/path-integral meaning of discrete symmetries in QFT."
sidebar:
  label: "Discrete Symmetries"
  order: 7
---

## Summary

Continuous symmetries come with infinitesimal generators, currents, and Ward identities. Discrete symmetries do not. They are instead implemented by operators such as parity $P$, charge conjugation $C$, and time reversal $T$, whose job is to map fields, states, and scattering processes into transformed ones.

The three basic transformations have different characters:

| Symmetry | Acts on spacetime? | Acts on charges? | Operator type | First idea |
| --- | --- | --- | --- | --- |
| Parity $P$ | yes: $(t,\mathbf x)\mapsto(t,-\mathbf x)$ | possibly, through intrinsic phases or field mixing | unitary | mirror reflection of space |
| Charge conjugation $C$ | no | yes: representation $R\mapsto\bar R$ | usually unitary | particle–antiparticle exchange |
| Time reversal $T$ | yes: $(t,\mathbf x)\mapsto(-t,\mathbf x)$ | possibly | antiunitary | reverse motion and spin |

A theory has one of these symmetries only if the full quantum theory respects it: the action or Hamiltonian, the operator algebra, the path-integral measure, the vacuum, and the boundary conditions must all transform appropriately. This is why the phrase “the Lagrangian is invariant” is useful but not the whole story.

Srednicki’s scalar-field treatment makes two foundational points especially clean: parity and time reversal may include intrinsic signs, and time reversal must be antiunitary so that the Hamiltonian is mapped to itself rather than to its negative (Srednicki 2007, §23). Coleman’s spinor treatment emphasizes the basis dependence of individual phase conventions, the transformation of Dirac bilinears, the particle–antiparticle action of charge conjugation, and the usefulness of discussing $PT$ before $T$ in relativistic spinor theory (Coleman 2019, ch. 22). Weinberg develops the same structures from Wigner’s theorem, one-particle states, the $S$-matrix, and the transformation of creation and annihilation operators (Weinberg 1995, Vol. I, §§2.2, 2.6, 3.3, 4.2, and 5.8).

<figure class="doc-figure" style="--figure-width: 48rem;">

![Discrete symmetry actions](/figures/foundations/discrete-symmetry-actions.svg)

<figcaption>

The three basic discrete operations have different meanings. $P$ reverses spatial orientation, $C$ conjugates internal charge representations, and $T$ reverses time while complex-conjugating numbers because it is antiunitary. Their combinations, especially $CP$, $PT$, and $CPT$, can be symmetries even when individual factors are not.

</figcaption>
</figure>

## Prerequisites

You should know [Poincaré Symmetry](/foundations/symmetry-and-spacetime/poincare-symmetry/), [Lorentz Representations](/foundations/symmetry-and-spacetime/lorentz-representations/), [Spinors from Lorentz Symmetry](/foundations/symmetry-and-spacetime/spinors-from-lorentz-symmetry/), [Internal Symmetries](/foundations/symmetry-and-spacetime/internal-symmetries/), [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/), [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/), [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/), [Dirac Field](/foundations/free-fields/dirac-field/), and [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/).

:::note[Conventions]
We use the qft.org default mostly-minus metric. Let

$$
x_P=(x^0,-\mathbf x),
\qquad
x_T=(-x^0,\mathbf x).
$$

For fields we write transformations in the operator convention

$$
U^{-1}\mathcal O(x)U=\mathcal O'(x).
$$

The time-reversal operator is antiunitary:

$$
T^{-1}iT=-i.
$$

Intrinsic phases such as $\eta_P$, $\eta_C$, and $\eta_T$ are convention-dependent unless they appear in invariant relative combinations.
:::

:::note[Assumptions]
A clean discrete symmetry statement assumes that the transformation is well-defined on the Hilbert space, preserves the operator algebra, maps the action into itself, preserves the path-integral measure, and either preserves the vacuum or maps it to a physically equivalent vacuum. Background fields, boundary conditions, regulator choices, anomalies, degenerate vacua, and chiral gauge interactions can all modify the naive statement.
:::

## Discrete symmetry versus continuous symmetry

A continuous internal symmetry has transformations close to the identity,

$$
\Phi\mapsto \Phi+\alpha^a\Delta_a\Phi+\cdots,
$$

and therefore has generators $Q_a$, currents $j_a^\mu$, and Ward identities.

A discrete symmetry has no infinitesimal parameter. For a $\mathbb Z_2$ symmetry, the entire group is

$$
\{1,Z\},
\qquad
Z^2=1.
$$

There is no Noether current for $Z$ itself. Instead, $Z$ imposes selection rules. If

$$
Z^{-1}\mathcal O_i Z=\eta_i\mathcal O_i,
\qquad
\eta_i=\pm1,
$$

and the vacuum is invariant,

$$
Z|0\rangle=|0\rangle,
$$

then

$$
\langle0|\mathcal O_1\cdots\mathcal O_n|0\rangle
=\left(\prod_i\eta_i\right)
\langle0|\mathcal O_1\cdots\mathcal O_n|0\rangle.
$$

Thus the correlator vanishes unless

$$
\prod_i\eta_i=+1.
$$

That is the discrete analogue of a charge-conservation selection rule.

## Parity

Parity reverses spatial orientation while leaving time fixed:

$$
x_P=(t,-\mathbf x).
$$

For a real spin-zero field one may have

$$
P^{-1}\phi(x)P=\eta_P\phi(x_P),
\qquad
\eta_P=\pm1.
$$

A field with $\eta_P=+1$ is called a scalar under parity; a field with $\eta_P=-1$ is called a pseudoscalar. Both are still scalar under proper orthochronous Lorentz transformations. The difference appears only after adding the disconnected Lorentz transformation $P$.

Parity acts differently on polar vectors and axial vectors. A polar vector $V^\mu$ transforms as

$$
P^{-1}V^0(t,\mathbf x)P=+V^0(t,-\mathbf x),
\qquad
P^{-1}V^i(t,\mathbf x)P=-V^i(t,-\mathbf x).
$$

An axial vector $A^\mu$, such as $\bar\psi\gamma^\mu\gamma^5\psi$, has the opposite intrinsic spatial-orientation behavior:

$$
A^0(t,\mathbf x)\mapsto -A^0(t,-\mathbf x),
\qquad
A^i(t,\mathbf x)\mapsto +A^i(t,-\mathbf x).
$$

For a Dirac field, a common parity convention is

$$
P^{-1}\psi(t,\mathbf x)P=\eta_P\gamma^0\psi(t,-\mathbf x),
\qquad
|\eta_P|=1.
$$

The phase $\eta_P$ is called an intrinsic parity. For a single isolated field it is mostly convention; relative intrinsic parities among fields can be physical when interactions compare them.

### Example: pseudoscalar Yukawa coupling

Consider

$$
\mathcal L_{\text{int}}=g\,\phi\,\bar\psi i\gamma^5\psi.
$$

The bilinear $\bar\psi i\gamma^5\psi$ is a pseudoscalar. Therefore the interaction is parity invariant if $\phi$ is also a pseudoscalar:

$$
P^{-1}\phi(t,\mathbf x)P=-\phi(t,-\mathbf x).
$$

This is the practical meaning of intrinsic parity: we choose field transformation rules so that the interaction terms transform consistently.

## Time reversal

Time reversal sends

$$
x_T=(-t,\mathbf x),
$$

but the associated Hilbert-space operator is not unitary. It is antiunitary:

$$
T^{-1}iT=-i.
$$

This is not an optional decoration. If time reversal were unitary, the transformation law of spacetime translations would imply that the Hamiltonian changes sign. Antiunitarity supplies the extra sign needed for

$$
T^{-1}HT=H,
\qquad
T^{-1}\mathbf P T=-\mathbf P.
$$

Thus time reversal preserves energy but reverses momentum. It also reverses angular momentum and spin:

$$
T^{-1}\mathbf J T=-\mathbf J,
\qquad
T^{-1}\mathbf S T=-\mathbf S.
$$

For a scalar field one may write schematically

$$
T^{-1}\phi(x)T=\eta_T\phi(x_T),
\qquad
\eta_T=\pm1,
$$

but because $T$ is antiunitary, this equation must be read antilinearly:

$$
T^{-1}\big(a\mathcal O+b\mathcal O'\big)T
=a^*T^{-1}\mathcal O T+b^*T^{-1}\mathcal O'T.
$$

For spinors, a common Dirac-basis convention is

$$
T^{-1}\psi(t,\mathbf x)T=\eta_T B\psi(-t,\mathbf x),
\qquad
B=i\gamma^1\gamma^3,
$$

with antiunitarity understood. Different gamma-matrix bases move the complex conjugation between the antiunitary operator and an explicit matrix. The invariant content is not the particular matrix $B$, but the way states, spins, and bilinears transform.

### What time reversal says about amplitudes

Time reversal does not usually say that a complex amplitude equals itself. Because $T$ is antiunitary and reverses the temporal order of a scattering process, it relates an amplitude to the amplitude for the time-reversed process, with initial and final states interchanged and phases conjugated. This is why final-state phases matter in discussions of $T$ and $CP$ violation.

A useful rule of thumb:

```txt
P reverses spatial orientation.
T reverses motion and spin, and complex conjugates numbers.
```

## Charge conjugation

Charge conjugation does not move the spacetime point. It maps fields in a representation of an internal symmetry group to fields in the conjugate representation.

For a complex scalar with charge $q$,

$$
C^{-1}\Phi(x)C=\eta_C\Phi^\dagger(x),
\qquad
C^{-1}\Phi^\dagger(x)C=\eta_C^*\Phi(x).
$$

The charge operator changes sign:

$$
C^{-1}QC=-Q.
$$

For a Dirac field, one common convention is

$$
C^{-1}\psi(x)C=\eta_C\,\mathsf C\,\bar\psi(x)^T,
$$

where the charge-conjugation matrix obeys

$$
\mathsf C^{-1}\gamma^\mu\mathsf C=-(\gamma^\mu)^T.
$$

This formula says that the charge-conjugated spinor solves the Dirac equation with the opposite gauge charge. In mode language, $C$ exchanges particle and antiparticle creation operators, but it does not turn an annihilation operator into a creation operator.

In Abelian electrodynamics one also takes

$$
C^{-1}A_\mu(x)C=-A_\mu(x).
$$

The vector current

$$
j^\mu=\bar\psi\gamma^\mu\psi
$$

is odd under $C$, so the interaction $eA_\mu j^\mu$ is even.

## Ordinary internal Z₂ symmetries

Not every discrete symmetry is $C$, $P$, or $T$. A real scalar theory may have

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2-\frac{\lambda}{4!}\phi^4,
$$

with a simple internal symmetry

$$
Z^{-1}\phi(x)Z=-\phi(x).
$$

This transformation does not reverse spacetime and does not exchange particles with antiparticles. It is just an internal $\mathbb Z_2$ symmetry.

If the vacuum preserves $Z$, then all odd correlators vanish:

$$
\langle0|T\phi(x_1)\cdots\phi(x_{2n+1})|0\rangle=0.
$$

If the symmetry is spontaneously broken, the Lagrangian may still be $Z$ invariant, but a chosen vacuum need not be. Then the selection rule for correlators in that vacuum is modified.

## Spinor bilinears

The five standard Dirac bilinears have characteristic transformation behavior. The following table records their $C$ parity and parity type. The $P$ column says how the object transforms as a Lorentz object; component signs follow from scalar, pseudoscalar, vector, axial-vector, or tensor behavior.

| Bilinear | Lorentz type | Under C | Under P |
| --- | --- | --- | --- |
| $\bar\psi\psi$ | scalar | even | scalar |
| $\bar\psi i\gamma^5\psi$ | pseudoscalar | even | pseudoscalar |
| $\bar\psi\gamma^\mu\psi$ | vector | odd | vector |
| $\bar\psi\gamma^\mu\gamma^5\psi$ | axial vector | even | axial vector |
| $\bar\psi\sigma^{\mu\nu}\psi$ | tensor | odd | tensor |

This table is one of the fastest ways to test whether a proposed interaction respects $C$ and $P$. For example, a neutral scalar coupled to $\bar\psi\psi$ is parity even, while a neutral pseudoscalar coupled to $\bar\psi i\gamma^5\psi$ is also parity even because the two minus signs cancel.

## Electromagnetic fields

For ordinary electromagnetism, the electric field is a polar vector and the magnetic field is an axial vector. With the standard choices,

| Operation | Electric field | Magnetic field |
| --- | --- | --- |
| $C$ | $\mathbf E\mapsto-\mathbf E$ | $\mathbf B\mapsto-\mathbf B$ |
| $P$ | $\mathbf E\mapsto-\mathbf E$ | $\mathbf B\mapsto+\mathbf B$ |
| $T$ | $\mathbf E\mapsto+\mathbf E$ | $\mathbf B\mapsto-\mathbf B$ |

These signs make Maxwell theory invariant under each of $C$, $P$, and $T$ in vacuum. Coupling to charged matter preserves or breaks these symmetries depending on how the matter fields and interactions transform.

The pseudoscalar combination

$$
\mathbf E\cdot\mathbf B
$$

is odd under both $P$ and $T$, and even under $C$. In covariant notation it is proportional to

$$
F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

This is why topological theta terms are natural first examples where discrete symmetry questions become subtle.

## Combinations

A theory may fail to be invariant under $C$, $P$, or $T$ separately while preserving a combination.

For example, a left-handed Weyl fermion is not mapped to itself by parity; parity exchanges left-handed and right-handed Lorentz representations. A chiral theory with only one of the two may therefore violate $P$. Charge conjugation also changes representation data. But a combination such as $CP$ can still be meaningful if it maps the field content into itself.

The most common combinations are:

| Combination | Meaning |
| --- | --- |
| $CP$ | mirror reflection plus particle–antiparticle exchange |
| $CT$ | charge conjugation plus time reversal |
| $PT$ | spacetime inversion $x\mapsto -x$, with antiunitarity from $T$ |
| $CPT$ | full charge conjugation plus spacetime inversion |

The next pages separate two logically different ideas:

- [Spin–Statistics](/foundations/symmetry-and-spacetime/spin-statistics/) explains why relativistic local quantum fields connect spin to Bose or Fermi statistics.
- [CPT Theorem](/foundations/symmetry-and-spacetime/cpt-theorem/) explains why any local, Lorentz-invariant, unitary QFT with the usual spectrum assumptions has $CPT$, even if $C$, $P$, $T$, or $CP$ are individually violated.

## Operator viewpoint

In the operator formalism, a unitary discrete symmetry $U$ is a map of the Hilbert space satisfying

$$
U^{-1}HU=H.
$$

For time reversal, the operator is antiunitary but the invariance condition is still

$$
T^{-1}HT=H.
$$

If $U$ is a symmetry and the vacuum is invariant,

$$
U|0\rangle=e^{i\alpha}|0\rangle,
$$

then correlation functions obey

$$
\langle0|T\mathcal O_1\cdots\mathcal O_n|0\rangle
=
\langle0|T(U^{-1}\mathcal O_1U)\cdots(U^{-1}\mathcal O_nU)|0\rangle,
$$

with the important warning that if $U=T$ is antiunitary, complex coefficients are conjugated and time ordering is affected by the reversal of time arguments.

For states, a discrete symmetry maps quantum numbers. Parity reverses momentum but not energy:

$$
P|E,\mathbf p,s\rangle
\propto |E,-\mathbf p,s_P\rangle.
$$

Time reversal reverses momentum and spin:

$$
T|E,\mathbf p,s\rangle
\propto |E,-\mathbf p,-s\rangle,
$$

where the precise spin label depends on basis conventions. Charge conjugation maps particle states to antiparticle states:

$$
C|\text{particle},q\rangle
\propto |\text{antiparticle},-q\rangle.
$$

## Path-integral viewpoint

In the path integral, a discrete symmetry is a change of integration variables plus, for spacetime transformations, a change of coordinates. Schematically,

$$
Z[J]=\int\mathcal D\Phi\,e^{iS[\Phi]+i\int J\Phi}.
$$

A unitary discrete symmetry gives

$$
S[\Phi']=S[\Phi],
\qquad
\mathcal D\Phi'=\mathcal D\Phi,
$$

and therefore relates $Z[J]$ to $Z[J']$ with transformed sources.

For time reversal, the Lorentzian path integral needs extra care because $T$ is antiunitary. It conjugates $i$ as well as reversing the time coordinate. In Euclidean field theory, the closely related operation is reflection of Euclidean time, but reflection positivity is an additional condition; Euclidean reflection is not automatically the same thing as a well-defined Lorentzian time-reversal symmetry.

The path-integral viewpoint is also where anomalies can appear. A classical transformation may leave $S$ invariant while the regulated measure changes by a Jacobian. For continuous symmetries this gives anomalous Ward identities. For discrete symmetries it can produce a discrete anomaly or an obstruction to gauging the symmetry.

## Intrinsic phases and convention dependence

Many discrete transformation laws contain phases:

$$
P^{-1}\psi P=\eta_P\gamma^0\psi(x_P),
\qquad
C^{-1}\psi C=\eta_C\mathsf C\bar\psi^T,
\qquad
T^{-1}\psi T=\eta_TB\psi(x_T).
$$

These phases are not all physical. If the theory has an internal $U(1)$ symmetry, one can multiply $C$, $P$, or $T$ by a $U(1)$ rotation and obtain a different but equally valid representative of the same physical transformation.

The physical information is usually in relative signs and phases that cannot be removed by internal symmetries. Examples include:

```txt
relative intrinsic parity between two species,
CP phases that cannot be removed by field redefinitions,
signs in transformation laws of composite operators,
T² acting on a one-particle state or superselection sector.
```

This is why tables of $C$, $P$, and $T$ conventions must always be read together with the stated phase and gamma-matrix conventions.

## Common pitfalls

### Pitfall 1: Treating time reversal as unitary

Time reversal is antiunitary. Forgetting this gives the wrong transformation of the Hamiltonian and wrong statements about amplitudes.

### Pitfall 2: Confusing charge conjugation with Hermitian conjugation

For a complex scalar, $C$ sends $\Phi$ to something proportional to $\Phi^\dagger$. For a Dirac spinor, $C$ involves the charge-conjugation matrix and transpose. Charge conjugation is a symmetry operation on fields and states, not merely taking the Hermitian adjoint of an operator.

### Pitfall 3: Assuming intrinsic phases are absolute

Intrinsic parity, charge-conjugation phases, and time-reversal phases can often be changed by internal transformations. Relative phases are what matter.

### Pitfall 4: Saying “the Lagrangian is invariant” and stopping there

A quantum symmetry also requires the measure, regulator, vacuum, and boundary conditions to cooperate. This is especially important for anomalies, theta terms, finite density, thermal states, and systems with boundaries.

### Pitfall 5: Confusing CP violation with CPT violation

$CP$ can be violated in a perfectly consistent local relativistic QFT. The $CPT$ theorem is a different and more robust statement, with different assumptions.

## Relation to the rest of QFT

Discrete symmetries are everywhere:

| Topic | Role of discrete symmetries |
| --- | --- |
| Free fields | classify scalars, pseudoscalars, vector currents, axial currents, Majorana fields |
| Scattering | relate amplitudes for transformed processes |
| Spin-statistics | uses locality, Lorentz symmetry, and positivity assumptions rather than a chosen discrete symmetry alone |
| CPT theorem | proves a universal combined symmetry under standard QFT assumptions |
| Gauge theory | charge conjugation and parity constrain allowed terms and theta terms |
| Standard Model | weak interactions violate $C$ and $P$, and the CKM phase violates $CP$ |
| Anomalies | the measure can obstruct a classically valid discrete transformation |

Discrete symmetries are therefore not just labels in a particle table. They are tests of which terms can appear, which correlators vanish, which amplitudes are related, and which assumptions a QFT is really using.

## Exercises

### Exercise 1: Why time reversal is antiunitary

Let spacetime translations be represented by

$$
U(a)=e^{-iP_\mu a^\mu}.
$$

Assume time reversal sends

$$
a^\mu\mapsto T^\mu{}_{\nu}a^\nu,
\qquad
T^\mu{}_{\nu}=\operatorname{diag}(-1,1,1,1).
$$

Show that if $T$ were unitary, one would get $T^{-1}HT=-H$. Then show how antiunitarity fixes the sign.

<details>
<summary><strong>Solution</strong></summary>

For a unitary implementation one would compare

$$
T^{-1}e^{-iP_\mu a^\mu}T
=e^{-i(T^{-1}P_\mu T)a^\mu}
$$

with the transformed translation

$$
U(Ta)=e^{-iP_\mu T^\mu{}_{\nu}a^\nu}.
$$

Equating the infinitesimal generators would give

$$
T^{-1}P^\mu T=T^\mu{}_{\nu}P^\nu.
$$

For $\mu=0$, this says

$$
T^{-1}HT=-H,
$$

which is incompatible with a positive-energy Hamiltonian unless $H=0$.

For an antiunitary time-reversal operator,

$$
T^{-1}iT=-i.
$$

The extra sign from conjugating $i$ changes the generator relation to

$$
T^{-1}P^\mu T=-T^\mu{}_{\nu}P^\nu.
$$

Thus

$$
T^{-1}HT=H,
\qquad
T^{-1}\mathbf P T=-\mathbf P.
$$

</details>

### Exercise 2: Z₂ selection rule

Suppose a real scalar theory has

$$
Z^{-1}\phi Z=-\phi,
\qquad
Z|0\rangle=|0\rangle.
$$

Show that every odd-point vacuum correlator vanishes.

<details>
<summary><strong>Solution</strong></summary>

Let

$$
G_n=\langle0|T\phi(x_1)\cdots\phi(x_n)|0\rangle.
$$

Insert $1=ZZ^{-1}$ around the operator product and use the invariant vacuum:

$$
G_n
=\langle0|Z^{-1}T\phi(x_1)\cdots\phi(x_n)Z|0\rangle.
$$

Each field contributes a factor $-1$, so

$$
G_n=(-1)^nG_n.
$$

If $n$ is odd, this gives

$$
G_n=-G_n,
$$

and therefore

$$
G_n=0.
$$

</details>

### Exercise 3: Charge conjugation of a complex scalar charge

Let

$$
C^{-1}\Phi C=\Phi^\dagger,
\qquad
C^{-1}\Phi^\dagger C=\Phi.
$$

The global charge acts as

$$
[Q,\Phi]=-q\Phi,
\qquad
[Q,\Phi^\dagger]=q\Phi^\dagger.
$$

Show that

$$
C^{-1}QC=-Q.
$$

<details>
<summary><strong>Solution</strong></summary>

Conjugate the first commutator by $C$:

$$
C^{-1}[Q,\Phi]C=[C^{-1}QC,C^{-1}\Phi C].
$$

The left-hand side is

$$
C^{-1}(-q\Phi)C=-q\Phi^\dagger.
$$

Thus

$$
[C^{-1}QC,\Phi^\dagger]=-q\Phi^\dagger.
$$

But the original charge satisfies

$$
[Q,\Phi^\dagger]=q\Phi^\dagger.
$$

Therefore $C^{-1}QC$ acts on $\Phi^\dagger$ as $-Q$ does. Checking the action on $\Phi$ gives the same conclusion, so

$$
C^{-1}QC=-Q
$$

up to a possible additive constant, which is fixed to zero by taking the vacuum charge to vanish.

</details>

### Exercise 4: Parity of a pseudoscalar Yukawa interaction

Assume

$$
P^{-1}\psi(t,\mathbf x)P=\gamma^0\psi(t,-\mathbf x).
$$

Show that $\bar\psi i\gamma^5\psi$ is parity odd. Then determine the parity of $\phi$ required for

$$
\mathcal L_{\text{int}}=g\phi\bar\psi i\gamma^5\psi
$$

to be parity invariant.

<details>
<summary><strong>Solution</strong></summary>

Under parity,

$$
\psi\mapsto\gamma^0\psi,
\qquad
\bar\psi\mapsto\bar\psi\gamma^0,
$$

with the spacetime argument changed to $x_P$. Therefore

$$
\bar\psi i\gamma^5\psi
\mapsto
\bar\psi(x_P)\gamma^0 i\gamma^5\gamma^0\psi(x_P).
$$

Since

$$
\gamma^0\gamma^5\gamma^0=-\gamma^5,
$$

we get

$$
\bar\psi i\gamma^5\psi\mapsto-\bar\psi(x_P)i\gamma^5\psi(x_P).
$$

The bilinear is parity odd. For the product

$$
\phi\bar\psi i\gamma^5\psi
$$

to be parity even, $\phi$ must also be parity odd:

$$
P^{-1}\phi(x)P=-\phi(x_P).
$$

Thus $\phi$ must be a pseudoscalar.

</details>

### Exercise 5: Charge conjugation of the vector current

Using the standard result

$$
C^{-1}\psi C=\mathsf C\bar\psi^T,
\qquad
\mathsf C^{-1}\gamma^\mu\mathsf C=-(\gamma^\mu)^T,
$$

show that the Dirac vector current

$$
j^\mu=\bar\psi\gamma^\mu\psi
$$

is odd under charge conjugation.

<details>
<summary><strong>Solution</strong></summary>

A direct component calculation gives

$$
C^{-1}\big(\bar\psi\gamma^\mu\psi\big)C
=-\bar\psi\gamma^\mu\psi.
$$

The minus sign comes from two places: the charge-conjugation matrix sends $\gamma^\mu$ to minus its transpose, and the fermion fields must be reordered after transposition. The result is

$$
C^{-1}j^\mu C=-j^\mu.
$$

This is physically necessary: $j^0$ is charge density, and charge conjugation reverses electric charge.

</details>

### Exercise 6: A simple CP constraint on a complex coupling

Let a complex scalar have an interaction

$$
\mathcal L_{\text{int}}=-\lambda\Phi^4-\lambda^*(\Phi^\dagger)^4.
$$

Assume parity acts trivially on the scalar and charge conjugation sends $\Phi\leftrightarrow\Phi^\dagger$. What condition on $\lambda$ is required for $CP$ invariance under this definition?

<details>
<summary><strong>Solution</strong></summary>

Since parity acts trivially, $CP$ acts like charge conjugation on the field:

$$
\Phi\mapsto\Phi^\dagger,
\qquad
\Phi^\dagger\mapsto\Phi.
$$

Therefore

$$
-\lambda\Phi^4-\lambda^*(\Phi^\dagger)^4
\mapsto
-\lambda(\Phi^\dagger)^4-\lambda^*\Phi^4.
$$

For this to equal the original interaction, the coefficient of $\Phi^4$ must match:

$$
\lambda=\lambda^*.
$$

Thus $\lambda$ must be real under this particular definition of $CP$.

If the theory has additional internal phase rotations, one may be able to combine $CP$ with such a rotation. Then the invariant condition is not simply that a particular displayed coefficient is real, but that no redefinition-invariant complex phase remains.

</details>

## Sources and further reading

- M. Srednicki, *Quantum Field Theory*, §23, for discrete symmetries of scalar fields, $P$, $T$, $C$, and internal $\mathbb Z_2$ transformations; §40, for spinor parity, time reversal, and charge conjugation.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 6, for internal and discrete symmetries; ch. 22, for parity, charge conjugation, $PT$, and $CPT$ with Fermi fields.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §2.6, for space inversion and time reversal in relativistic quantum mechanics; §3.3, for discrete symmetries of the $S$-matrix; §4.2, for $C$, $P$, and $T$ properties of creation and annihilation operators; §5.8, for the $CPT$ theorem.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§3.6 and 4.4, for discrete symmetries, spinor bilinears, and QED examples.
- C. Itzykson and J.-B. Zuber, *Quantum Field Theory*, chs. 2 and 3, for Lorentz transformations, spinors, and discrete symmetries.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for a theorem-first treatment of the structural results behind spin-statistics and CPT.

## Version history

- **2026-05-23:** Initial qft.org page on parity, time reversal, charge conjugation, internal $\mathbb Z_2$ symmetries, spinor bilinears, electromagnetic fields, combined discrete symmetries, intrinsic phases, operator/path-integral viewpoints, pitfalls, and exercises.
