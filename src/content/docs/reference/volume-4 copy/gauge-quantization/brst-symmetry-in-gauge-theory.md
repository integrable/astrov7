---
title: "BRST Symmetry in Gauge Theory"
description: "Introduces the nilpotent BRST differential, writes covariant gauge fixing as a BRST-exact term, and explains BRST cohomology as the home of physical gauge-invariant observables."
sidebar:
  label: "BRST Symmetry in Gauge Theory"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §74; Weinberg Vol. II §§15.7–15.8; Coleman lectures on gauge-field Feynman rules; Zinn-Justin Ch. 26; Schwartz Chs. 25–30."
topics:
  - BRST symmetry
  - gauge fixing
  - ghost fields
  - BRST cohomology
  - Slavnov–Taylor identities
  - Nakanishi–Lautrup field
canonicalTopics:
  - brst-symmetry
  - brst-cohomology
  - gauge-fixed-action
  - slavnov-taylor-identities
  - ghost-number
  - nakanishi-lautrup-field
researchStatus:
  established:
    - "BRST symmetry is the standard perturbative symmetry principle behind gauge-fixed Yang–Mills theory, ghost cancellations, physical-state cohomology, and Slavnov–Taylor identities."
  active:
    - "Nonperturbative BRST, Gribov regions, boundaries, anomalies, and the BV extension of BRST remain important advanced topics beyond this first pass."
---

## Summary

Gauge fixing hides ordinary gauge redundancy in the Lagrangian, but it does not destroy the structure that made the theory consistent. The surviving structure is BRST symmetry: an odd, nilpotent operation $s$ satisfying

$$
s^2=0.
$$

In the conventions of this volume, the BRST transformations for Yang–Mills theory in a covariant gauge are

$$
\boxed{
\begin{aligned}
sA_\mu^a&=(D_\mu c)^a,\\
sc^a&=\frac{g}{2}f^{abc}c^b c^c,\\
s\bar c^a&=B^a,\\
sB^a&=0.
\end{aligned}
}
$$

For a matter field $\psi$ transforming as $\psi\mapsto U^{-1}\psi$, the corresponding BRST variation is

$$
s\psi=-igc^aT^a\psi.
$$

The auxiliary field $B^a$ makes nilpotence off-shell. After integrating it out, one recovers the usual gauge-fixing term

$$
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2,
$$

but the algebra is clearest before doing so.

The compact structural statement is

$$
\boxed{
\mathcal L
=
\mathcal L_{\rm YM}+\mathcal L_{\rm matter}
+s\left[\bar c^a\left(\partial^\mu A_\mu^a+\frac{\xi}{2}B^a\right)\right].
}
$$

Because $s^2=0$, the gauge-fixing plus ghost sector is BRST invariant. Physical observables are BRST-closed quantities modulo BRST-exact ones:

$$
\boxed{
H^0_{\rm BRST}
=
\frac{\ker s\text{ at ghost number }0}{\operatorname{im}s\text{ from ghost number }-1}.
}
$$

That quotient is the cohomological version of “gauge-invariant information after removing redundancy.” It is not decoration. It is the mechanism behind gauge-parameter independence, ghost cancellations, Slavnov–Taylor identities, and the unitarity of the physical sector.

<figure class="doc-figure" style="--figure-width: 39rem;">

![The BRST differential raises ghost number by one and organizes physical observables as cohomology.](/figures/gauge-theories-standard-model/brst-complex-map.svg)

<figcaption>

The BRST differential $s$ raises ghost number by one and satisfies $s^2=0$. The pair $(\bar c^a,B^a)$ is cohomologically trivial, while gauge transformations are encoded by replacing the gauge parameter with the ghost $c^a$. Physical ghost-number-zero observables live in $H^0_{\rm BRST}$.

</figcaption>
</figure>

## Prerequisites

You should have read [Gauge Fixing and Faddeev–Popov](/gauge-theories-standard-model/gauge-quantization/gauge-fixing-and-faddeev-popov/) and [Ghosts and Gauge-Fixed Action](/gauge-theories-standard-model/gauge-quantization/ghosts-and-gauge-fixed-action/). We will use the gauge-fixed Yang–Mills Lagrangian in auxiliary-field form,

$$
\mathcal L
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
+B^a\partial^\mu A_\mu^a
+\frac{\xi}{2}B^aB^a
-\bar c^a\partial^\mu D_\mu^{ab}c^b
+\mathcal L_{\rm matter}.
$$

The adjoint covariant derivative is

$$
(D_\mu c)^a=\partial_\mu c^a-gf^{abc}A_\mu^b c^c.
$$

You should also remember that a gauge-invariant functional $\mathcal O[A,\psi]$ is unchanged under infinitesimal gauge transformations. BRST symmetry begins by replacing the infinitesimal gauge parameter with the ghost field.

## Core idea

BRST symmetry is gauge redundancy rewritten as a nilpotent differential on an enlarged field space.

Gauge fixing adds unphysical variables: longitudinal gauge modes, ghosts, antighosts, and the auxiliary field. If these variables were arbitrary new degrees of freedom, the theory would be in serious trouble. BRST symmetry says they are not arbitrary. They are organized into a complex,

$$
\cdots\xrightarrow{s}\text{fields of ghost number }-1
\xrightarrow{s}
\text{fields of ghost number }0
\xrightarrow{s}
\text{fields of ghost number }+1
\xrightarrow{s}\cdots,
$$

with

$$
s^2=0.
$$

Nilpotence means that every BRST-exact object is automatically BRST-closed. This lets us define cohomology: closed objects modulo exact ones. In gauge theory, this cohomology is the algebraic replacement for “functions on the quotient by gauge transformations.”

For a first pass, the slogan is:

$$
\text{BRST cohomology} = \text{gauge-invariant physics inside a gauge-fixed formalism}.
$$

## The BRST differential

Use matrix notation for a moment:

$$
A_\mu=A_\mu^aT^a,
\qquad
c=c^aT^a.
$$

The finite gauge transformation convention in this volume is

$$
A_\mu\mapsto U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U,
\qquad
\psi\mapsto U^{-1}\psi.
$$

For $U=e^{ig\alpha}$, the infinitesimal gauge variation is

$$
\delta_\alpha A_\mu=D_\mu\alpha,
\qquad
\delta_\alpha\psi=-ig\alpha\psi.
$$

BRST replaces the commuting gauge parameter $\alpha^a(x)$ with the anticommuting ghost field $c^a(x)$:

$$
sA_\mu=D_\mu c,
\qquad
s\psi=-igc\psi.
$$

In components,

$$
sA_\mu^a=(D_\mu c)^a
=\partial_\mu c^a-gf^{abc}A_\mu^b c^c.
$$

The transformation of $c$ itself is not optional. It is fixed by the requirement that $s^2=0$. With the above sign convention,

$$
\boxed{
sc^a=\frac{g}{2}f^{abc}c^b c^c.
}
$$

In matrix notation this is

$$
sc=-igc^2.
$$

Many books use the opposite sign for $sc$ because they define the ghost to replace the negative of the infinitesimal gauge parameter. That is only a convention. Once $sA_\mu$, $s\psi$, and $D_\mu$ are fixed, the sign of $sc$ is fixed by nilpotence.

The antighost and auxiliary field transform as

$$
s\bar c^a=B^a,
\qquad
sB^a=0.
$$

This pair is deliberately simple: $\bar c$ is the preimage of $B$, and $B$ has no further image.

## Ghost number and Grassmann parity

BRST has two gradings.

First, it is Grassmann odd: it changes the Grassmann parity of a field. Acting on an even field such as $A_\mu$ gives an odd expression; acting on an odd field such as $c$ gives an even expression.

Second, it raises ghost number by one:

$$
\operatorname{gh}(sX)=\operatorname{gh}(X)+1.
$$

The assignments are

| Object | Grassmann parity | Ghost number |
|---|---:|---:|
| $A_\mu^a$ | even | $0$ |
| matter bosons | even | $0$ |
| matter fermions | odd | $0$ |
| $c^a$ | odd | $+1$ |
| $\bar c^a$ | odd | $-1$ |
| $B^a$ | even | $0$ |
| $s$ | odd | $+1$ |

The BRST transformation obeys the graded Leibniz rule:

$$
s(XY)=(sX)Y+(-1)^{|X|}X(sY),
$$

where $|X|=0$ for Grassmann-even $X$ and $|X|=1$ for Grassmann-odd $X$.

That sign is not ceremonial. It is the sign that makes nilpotence work.

## Nilpotence on matter fields

Let $\psi$ transform as

$$
s\psi=-igc\psi.
$$

Then

$$
s^2\psi
=-ig(sc)\psi+igc(s\psi),
$$

where the second sign comes from moving the odd operation $s$ past the odd field $c$. Substituting

$$
sc=-igc^2,
\qquad
s\psi=-igc\psi,
$$

gives

$$
s^2\psi
=-ig(-igc^2)\psi+igc(-igc\psi)=0.
$$

Thus nilpotence on matter fields is exactly the statement that the ghost transformation is chosen to reproduce the Lie algebra of gauge transformations.

## Nilpotence on the gauge field

For the gauge field,

$$
sA_\mu=D_\mu c=\partial_\mu c+ig[A_\mu,c].
$$

Apply $s$ again. Using the graded Leibniz rule,

$$
s^2A_\mu
=D_\mu(sc)+ig[sA_\mu,c]_+,
$$

where $[X,c]_+=Xc+cX$ because both $X=sA_\mu$ and $c$ are Grassmann odd. With

$$
sc=-igc^2,
$$

one finds

$$
D_\mu(sc)=-igD_\mu(c^2),
$$

while

$$
ig[sA_\mu,c]_+
=ig[(D_\mu c)c+c(D_\mu c)]
=igD_\mu(c^2).
$$

The two terms cancel:

$$
s^2A_\mu=0.
$$

In components, the same cancellation is the Jacobi identity for $f^{abc}$. This is the algebraic reason BRST belongs with non-Abelian gauge theory: nilpotence knows the Lie algebra.

## Gauge fixing as a BRST-exact term

Now define the gauge-fixing fermion

$$
\Psi
=
\bar c^a\left(\partial^\mu A_\mu^a+\frac{\xi}{2}B^a\right).
$$

It has ghost number $-1$ and is Grassmann odd. Apply $s$:

$$
s\Psi
= B^a\left(\partial^\mu A_\mu^a+\frac{\xi}{2}B^a\right)
-\bar c^a\partial^\mu(D_\mu c)^a.
$$

Therefore

$$
\boxed{
\mathcal L_{\rm gf+gh}
=s\Psi
=B^a\partial^\mu A_\mu^a
+\frac{\xi}{2}B^aB^a
-\bar c^a\partial^\mu D_\mu^{ab}c^b.
}
$$

This is precisely the gauge-fixing plus ghost Lagrangian from the previous page.

Since $s^2=0$,

$$
s\mathcal L_{\rm gf+gh}=s^2\Psi=0.
$$

The Yang–Mills and matter Lagrangians are gauge invariant, so they are BRST invariant:

$$
s(\mathcal L_{\rm YM}+\mathcal L_{\rm matter})=0.
$$

Thus the complete gauge-fixed theory is BRST invariant:

$$
s\mathcal L=0.
$$

This is the key payoff. Gauge fixing destroys manifest local gauge redundancy, but the gauge-fixed action has a precise nilpotent symmetry that remembers it.

## Integrating out the auxiliary field

The $B^a$ equation of motion is

$$
B^a=-\frac{1}{\xi}\partial^\mu A_\mu^a.
$$

Substituting back gives

$$
\mathcal L_{\rm gf+gh}
\longrightarrow
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2
-\bar c^a\partial^\mu D_\mu^{ab}c^b.
$$

If one eliminates $B^a$, the BRST variation of the antighost becomes

$$
s\bar c^a=-\frac{1}{\xi}\partial^\mu A_\mu^a.
$$

Then $s^2\bar c^a$ vanishes only using the field equations, rather than as a purely algebraic identity. This is why the auxiliary-field formulation is not pedantry. It preserves off-shell nilpotence:

$$
s^2=0\quad\text{without using equations of motion}.
$$

For derivations of identities, renormalization constraints, and cohomology, off-shell nilpotence is the clean version.

## BRST-closed and BRST-exact objects

An object $\mathcal O$ is BRST closed if

$$
s\mathcal O=0.
$$

It is BRST exact if there exists another object $\mathcal X$ such that

$$
\mathcal O=s\mathcal X.
$$

Because $s^2=0$, every exact object is closed:

$$
\mathcal O=s\mathcal X
\quad\Rightarrow\quad
s\mathcal O=s^2\mathcal X=0.
$$

The cohomology is closed modulo exact:

$$
H_{\rm BRST}
=
\frac{\ker s}{\operatorname{im}s}.
$$

In ordinary language, exact objects are pure redundancy. They are invisible in the physical quotient. Closed objects are compatible with the redundancy. Cohomology keeps the compatible objects after identifying those that differ by pure redundancy.

For physical local observables, one usually wants ghost number zero:

$$
H^0_{\rm BRST}.
$$

Gauge-invariant operators built from $F_{\mu\nu}$, covariant matter combinations, Wilson loops, and similar objects are BRST closed. Some BRST-closed objects may differ by BRST-exact terms; the cohomology identifies them.

## Relation to ordinary gauge invariance

Suppose $\mathcal O[A,\psi]$ is gauge invariant. Under an infinitesimal gauge transformation with parameter $\alpha$, its variation vanishes:

$$
\delta_\alpha\mathcal O=0.
$$

BRST transformation is the same infinitesimal gauge transformation with $\alpha$ replaced by the ghost $c$, so

$$
s\mathcal O=0.
$$

Thus gauge-invariant objects are BRST closed.

The converse requires care. BRST cohomology is formulated on the enlarged space including ghosts and antighosts. In ghost number zero and under standard perturbative assumptions, the local BRST cohomology reproduces gauge-invariant local operators modulo redundancies. In more advanced settings, this statement becomes a theorem with hypotheses and caveats; it is the beginning of the cohomological approach to gauge theory.

## Gauge-parameter independence

The gauge parameter $\xi$ appears inside the gauge-fixing fermion:

$$
\Psi_\xi
=
\bar c^a\left(\partial^\mu A_\mu^a+\frac{\xi}{2}B^a\right).
$$

Changing $\xi$ changes the action by a BRST-exact term:

$$
\frac{\partial\mathcal L}{\partial\xi}
=s\left(\frac12\bar c^aB^a\right).
$$

If $\mathcal O$ is BRST closed and the path-integral measure is BRST invariant, then formally

$$
\frac{\partial}{\partial\xi}\langle\mathcal O\rangle
\propto
\left\langle \mathcal O\,s\left(\frac12\int d^4x\,\bar c^aB^a\right)\right\rangle
=
\left\langle s\left[\mathcal O\frac12\int d^4x\,\bar c^aB^a\right]\right\rangle
=0.
$$

This is the BRST explanation for gauge-parameter independence of physical observables.

The assumptions matter. If the measure is not BRST invariant, the gauge symmetry is anomalous. Then the quantum theory is inconsistent as a gauge theory unless the anomaly cancels. This is why anomaly cancellation in the Standard Model is not a decorative miracle; it is a consistency condition for BRST and gauge invariance at the quantum level.

## Slavnov–Taylor identities

Ward identities in QED express current conservation and gauge invariance. In non-Abelian gauge theories after gauge fixing, the corresponding identities are Slavnov–Taylor identities. BRST symmetry is the clean way to derive them.

The path-integral idea is simple. Make a change of variables by an infinitesimal BRST transformation. If the measure and action are invariant, the integral of a BRST variation vanishes:

$$
\langle s\mathcal X\rangle=0.
$$

Choosing different $\mathcal X$ gives relations among Green functions. These relations constrain propagators, vertices, counterterms, and renormalization constants.

The identities are more complicated than the QED Ward–Takahashi identity because the gauge symmetry is non-Abelian and ghosts participate. But conceptually they are the same kind of statement: the redundancy of description imposes exact relations on quantum correlation functions.

## Physical states

In canonical language, BRST symmetry is generated by a charge $Q_{\rm BRST}$:

$$
s\mathcal O=i[Q_{\rm BRST},\mathcal O\}_{\rm graded}.
$$

Nilpotence becomes

$$
Q_{\rm BRST}^2=0.
$$

Physical states are BRST-closed modulo BRST-exact states:

$$
Q_{\rm BRST}|\Psi\rangle=0,
\qquad
|\Psi\rangle\sim |\Psi\rangle+Q_{\rm BRST}|\Lambda\rangle.
$$

This is the Hilbert-space version of the cohomology statement. Unphysical polarizations, ghosts, antighosts, and auxiliary modes arrange into BRST-trivial sectors. The next page develops this into the unitarity story: covariant gauges can use an enlarged indefinite space internally while the physical cohomology has a unitary S-matrix.

## Why BRST is better than just saying gauge invariant

One might ask why we need BRST at all. Why not simply say “compute gauge-invariant quantities”?

For tree-level intuition, that may be enough. For perturbative quantum gauge theory, it is not. Gauge fixing changes the action, the propagators, the field content, and the intermediate Green functions. A proof of consistency must operate inside the gauge-fixed formalism itself.

BRST does exactly that:

- it is a symmetry of the gauge-fixed action;
- it knows about ghosts and antighosts;
- it makes gauge fixing a BRST-exact deformation;
- it defines physical quantities as cohomology classes;
- it generates Slavnov–Taylor identities;
- it controls the allowed counterterms in renormalization.

So BRST is not an extra symmetry imposed on top of gauge theory. It is the algebraic residue of gauge redundancy after one chooses to compute with a gauge-fixed action.

## Abelian limit

In QED, the structure constants vanish. The BRST transformations reduce to

$$
sA_\mu=\partial_\mu c,
\qquad
sc=0,
\qquad
s\bar c=B,
\qquad
sB=0.
$$

The ghost action is free and decouples from photons and charged matter in Lorenz-type gauges. BRST still exists, but it is less visible because the ghost sector does not affect ordinary QED amplitudes.

In non-Abelian gauge theory, $sc$ is nonlinear:

$$
sc^a=\frac{g}{2}f^{abc}c^b c^c.
$$

This nonlinear term is the ghost-level shadow of the non-Abelian Lie algebra.

## Common pitfalls

**Pitfall 1: Calling BRST an ordinary physical symmetry.**

BRST is not a global symmetry that maps one physical particle to another. It is an odd cohomological symmetry of the gauge-fixed description. Its job is to encode redundancy, not to generate new physical multiplets.

**Pitfall 2: Forgetting that $s$ is Grassmann odd.**

The graded Leibniz rule is essential. Missing the sign in

$$
s(XY)=(sX)Y+(-1)^{|X|}X(sY)
$$

usually breaks nilpotence on the second line.

**Pitfall 3: Eliminating $B^a$ and then expecting off-shell nilpotence.**

With $B^a$ included, $s^2=0$ algebraically. After eliminating $B^a$, nilpotence on $\bar c^a$ is typically on-shell. Keep $B^a$ for clean derivations.

**Pitfall 4: Thinking BRST removes the need for anomaly cancellation.**

BRST invariance must hold quantum mechanically, including the measure. Gauge anomalies are failures of quantum BRST invariance. An anomalous gauge theory is not merely ugly; it is inconsistent as a gauge theory.

**Pitfall 5: Treating exact terms as zero before specifying cohomology.**

A BRST-exact operator is not literally the zero operator. It is zero in BRST cohomology and has vanishing expectation in appropriate BRST-invariant correlators. Those hypotheses matter.

**Pitfall 6: Confusing ghost number with particle number.**

Ghost number is a grading of the gauge-fixed formalism. Physical states and ordinary observables usually sit at ghost number zero, but ghost-number assignments are not particle counts.

## Relations to other pages

This page completes the conceptual transition from the [Faddeev–Popov determinant](/gauge-theories-standard-model/gauge-quantization/gauge-fixing-and-faddeev-popov/) to the [ghost action](/gauge-theories-standard-model/gauge-quantization/ghosts-and-gauge-fixed-action/) and then to the cohomological structure of the gauge-fixed theory.

Continue next to Physical States and Unitarity, where $Q_{\rm BRST}$ is used to explain why covariant gauges do not introduce negative-probability physical states. Later, Covariant Gauges develops the role of $\xi$, and Background-Field Gauge shows how a different gauge choice keeps background gauge covariance manifest.

The later Standard Model anomaly chapter will return to the statement that gauge anomalies are quantum failures of BRST invariance. The Mathematical and Rigorous QFT volume treats the BV-BRST formalism and cohomological formulations more systematically.

## Research status

Perturbative BRST symmetry is established and indispensable. It is one of the standard tools for proving gauge-theory renormalizability, deriving Slavnov–Taylor identities, and defining the physical sector in covariant gauges.

The subtleties are mostly global, nonperturbative, or boundary-sensitive. Gribov copies complicate the global meaning of a gauge slice. Boundaries can turn some gauge transformations into physical symmetries with charges. Gauge anomalies obstruct quantum BRST invariance. The Batalin–Vilkovisky formalism generalizes BRST to more complicated gauge systems, especially those with open or reducible gauge algebras. Those topics are not contradictions of the first-pass construction; they are its advanced continuation.

## Exercises

### Exercise 1: Nilpotence on the antighost pair

Using

$$
s\bar c^a=B^a,
\qquad
sB^a=0,
$$

show that $s^2\bar c^a=0$ and $s^2B^a=0$.

<details><summary><strong>Solution</strong></summary>

Apply $s$ twice:

$$
s^2\bar c^a=sB^a=0.
$$

Similarly,

$$
s^2B^a=s(0)=0.
$$

This is why the pair $(\bar c^a,B^a)$ is algebraically simple. The auxiliary field makes nilpotence on the antighost off-shell.

</details>

### Exercise 2: Gauge fixing from a BRST variation

Let

$$
\Psi=\bar c^a\left(G^a+\frac{\xi}{2}B^a\right),
\qquad
G^a=\partial^\mu A_\mu^a.
$$

Using $s\bar c^a=B^a$, $sB^a=0$, and $sA_\mu^a=(D_\mu c)^a$, compute $s\Psi$.

<details><summary><strong>Solution</strong></summary>

Because $\bar c^a$ is Grassmann odd,

$$
s\Psi
=(s\bar c^a)\left(G^a+\frac{\xi}{2}B^a\right)
-\bar c^a\left(sG^a+\frac{\xi}{2}sB^a\right).
$$

Now

$$
s\bar c^a=B^a,
\qquad
sB^a=0,
\qquad
sG^a=\partial^\mu(D_\mu c)^a.
$$

Therefore

$$
s\Psi
=B^a\partial^\mu A_\mu^a
+\frac{\xi}{2}B^aB^a
-\bar c^a\partial^\mu D_\mu^{ab}c^b.
$$

This is the gauge-fixing plus ghost Lagrangian.

</details>

### Exercise 3: Ghost number of the gauge-fixing fermion

Using

$$
\operatorname{gh}(\bar c)=-1,
\qquad
\operatorname{gh}(A_\mu)=0,
\qquad
\operatorname{gh}(B)=0,
\qquad
\operatorname{gh}(s)=+1,
$$

find the ghost number of $\Psi$ and $s\Psi$.

<details><summary><strong>Solution</strong></summary>

The factor in parentheses in

$$
\Psi=\bar c^a\left(\partial^\mu A_\mu^a+\frac{\xi}{2}B^a\right)
$$

has ghost number zero. Since $\bar c^a$ has ghost number $-1$,

$$
\operatorname{gh}(\Psi)=-1.
$$

Because $s$ raises ghost number by one,

$$
\operatorname{gh}(s\Psi)=0.
$$

This is necessary: the Lagrangian must have ghost number zero.

</details>

### Exercise 4: Abelian BRST transformations

Set $f^{abc}=0$. Write the BRST transformations for QED in Lorenz gauge.

<details><summary><strong>Solution</strong></summary>

For an Abelian gauge group, the adjoint covariant derivative becomes an ordinary derivative and the ghost self-transformation vanishes. Thus

$$
sA_\mu=\partial_\mu c,
\qquad
sc=0,
\qquad
s\bar c=B,
\qquad
sB=0.
$$

For a charged matter field with charge $q$ and convention $D_\mu=\partial_\mu+iqA_\mu$,

$$
s\psi=-iqc\psi.
$$

The ghost action is free, so the ghosts decouple from ordinary QED amplitudes in Lorenz gauge.

</details>

### Exercise 5: Gauge-parameter variation is BRST exact

Show that

$$
\frac{\partial}{\partial\xi}s\left[\bar c^a\left(\partial^\mu A_\mu^a+\frac{\xi}{2}B^a\right)\right]
=
s\left(\frac12\bar c^aB^a\right).
$$

<details><summary><strong>Solution</strong></summary>

The only explicit $\xi$ dependence is in the term

$$
\bar c^a\frac{\xi}{2}B^a.
$$

Therefore

$$
\frac{\partial}{\partial\xi}s\left[\bar c^a\left(\partial^\mu A_\mu^a+\frac{\xi}{2}B^a\right)\right]
=
s\left(\frac12\bar c^aB^a\right).
$$

This is the basic reason changes of the gauge parameter are BRST-exact deformations.

</details>

### Exercise 6: BRST-closed gauge-invariant operators

Let $\mathcal O[A,\psi]$ be invariant under all infinitesimal gauge transformations. Explain why $s\mathcal O=0$.

<details><summary><strong>Solution</strong></summary>

BRST transformation acts on $A_\mu$ and $\psi$ like an infinitesimal gauge transformation whose gauge parameter has been replaced by the ghost field $c$. If $\mathcal O$ is invariant for arbitrary infinitesimal gauge parameter $\alpha(x)$, then it is also invariant when $\alpha(x)$ is replaced by $c(x)$.

Therefore

$$
s\mathcal O=0.
$$

This shows that gauge-invariant operators are BRST closed.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §74, for BRST symmetry in non-Abelian gauge theory and its relation to ghosts, antighosts, and the auxiliary field.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, gauge-field lectures around the Faddeev–Popov prescription, for the path-integral and ghost-field motivation.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–30, for Yang–Mills theory, ghost loops, Ward identities, and anomalies in the Standard Model context.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, §§15.7–15.8, for BRST symmetry, BRST cohomology, independence of gauge fixing, and generalizations.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, Ch. 26, for BRST symmetry and the Zinn-Justin equation.
- Henneaux and Teitelboim, *Quantization of Gauge Systems*, for a systematic constrained-Hamiltonian and BRST treatment.

## Version history

- **2026-06-18:** Initial polished draft.
