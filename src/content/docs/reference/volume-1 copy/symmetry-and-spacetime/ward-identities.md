---
title: "Ward Identities"
description: "Ward identities from operator current conservation, path-integral changes of variables, contact terms, source functionals, anomalies, and the first gauge-theory preview."
sidebar:
  label: "Ward Identities"
  order: 6
---

## Summary

A Ward identity is what a symmetry becomes after it is inserted into correlation functions.

For an exact continuous symmetry with current $j_a^\mu$ and infinitesimal action

$$
\delta_a\mathcal O=\Delta_a\mathcal O,
$$

our charge convention is

$$
\Delta_a\mathcal O=i[Q_a,\mathcal O].
$$

Then the local Ward identity for time-ordered correlators is

$$
\boxed{
\partial_\mu
\langle0|T\,j_a^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)|0\rangle
=
-i\sum_{k=1}^n\delta^{(4)}(x-x_k)
\langle0|T\,\mathcal O_1\cdots (\Delta_a\mathcal O_k)(x_k)\cdots\mathcal O_n|0\rangle .
}
$$

That formula is the main point of this page. The divergence of the current is zero away from operator insertions, but the derivative of the time-ordering step functions produces contact terms. Those contact terms are not nuisances; they are exactly how the current knows what charge and representation each operator carries.

Ward identities have several faces:

| Language | What the identity says |
| --- | --- |
| Operator | Current conservation plus equal-time commutators gives contact terms. |
| Path integral | A local change of variables relates source variations, current divergence, and possible Jacobians. |
| Momentum space | Contracting a current or gauge-boson leg with its momentum gives lower-point or transformed Green functions. |
| Structural | Symmetry imposes selection rules, transversality, multiplet relations, and anomaly constraints. |

Srednicki derives Noether currents and Ward identities with contact terms in his continuous-symmetry section, then uses the same logic for QED Ward identities and the statement that an external photon amplitude vanishes when a polarization vector is replaced by the photon momentum (Srednicki 2007, §§22 and 67–68). Coleman uses generating functionals to derive Ward identities for Green functions and one-particle irreducible functions, especially in QED renormalization (Coleman 2019, chs. 32–33). Weinberg treats the operator current algebra in the canonical formalism and the Ward–Takahashi identity in the nonperturbative analysis of QED (Weinberg 1995, Vol. I, §§7.3 and 10.4).

<figure class="doc-figure" style="--figure-width: 50rem;">

![Ward identity contact terms](/figures/foundations/ward-identity-contact-terms.svg)

<figcaption>

A Ward identity is current conservation inside a correlator. Away from insertions, the current divergence vanishes. At insertion points, differentiating the time-ordering step functions produces contact terms. The same identity can be derived from a path-integral change of variables; anomalies appear when the measure is not invariant.

</figcaption>
</figure>

## Prerequisites

You should know [Noether Theorem](/foundations/classical-field-theory/noether-theorem/), [States, Operators, and the Vacuum](/foundations/correlators-and-propagators/states-operators-vacuum/), [Time Ordering](/foundations/correlators-and-propagators/time-ordering/), [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/), [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/), [Internal Symmetries](/foundations/symmetry-and-spacetime/internal-symmetries/), and [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/).

:::note[Conventions]
We use the qft.org default mostly-minus metric. The symmetry generators $T_a$ are Hermitian and obey

$$
[T_a,T_b]=if_{ab}{}^cT_c.
$$

The charge convention is

$$
\Delta_a\mathcal O=i[Q_a,\mathcal O].
$$

For a field multiplet,

$$
\Delta_a\Phi_i=-i(T_a)_i{}^j\Phi_j,
\qquad
[Q_a,\Phi_i]=-(T_a)_i{}^j\Phi_j.
$$

With a different convention for the sign of $Q_a$ or the representation matrices, the signs in the contact terms change accordingly.
:::

:::note[Assumptions]
The clean identity above assumes an exact continuous global symmetry, an invariant vacuum, a regulator that preserves the symmetry, no anomaly, no relevant boundary flux, and operator insertions that are local or suitably renormalized. Gauge redundancies, boundaries, spontaneous symmetry breaking, composite operators, and anomalous symmetries require modifications.
:::

## The identity in one line

Let

$$
X=\mathcal O_1(x_1)\cdots\mathcal O_n(x_n).
$$

The local Ward identity is

$$
\partial_\mu\langle Tj_a^\mu(x)X\rangle
=
-i\sum_k\delta^{(4)}(x-x_k)\langle T\mathcal O_1\cdots\Delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

Away from the insertion points $x=x_k$, the right-hand side vanishes. Thus the current is conserved as an operator insertion except at the places where it acts on charged operators.

This is the correlation-function version of the charge statement

$$
\Delta_a\mathcal O_k=i[Q_a,\mathcal O_k].
$$

The local identity is stronger than the integrated charge statement because it remembers *where* the charge entered the correlator.

## Operator derivation

Start with a conserved current,

$$
\partial_\mu j_a^\mu=0,
$$

and consider a time-ordered product with one insertion $\mathcal O(y)$. For a bosonic current,

$$
T\,j_a^\mu(x)\mathcal O(y)
=\theta(x^0-y^0)j_a^\mu(x)\mathcal O(y)
+\theta(y^0-x^0)\mathcal O(y)j_a^\mu(x).
$$

Taking the divergence gives two kinds of terms. First, $\partial_\mu j_a^\mu$ acts inside the two ordered regions. That part vanishes for an exact conserved current. Second, $\partial_0$ differentiates the step functions. The result is

$$
\partial_\mu T\,j_a^\mu(x)\mathcal O(y)
=\delta(x^0-y^0)[j_a^0(x),\mathcal O(y)]
$$

inside vacuum expectation values, up to the usual distributional interpretation of equal-time products.

Now use the local version of charge generation:

$$
[j_a^0(t,\mathbf x),\mathcal O(t,\mathbf y)]
=-i\delta^{(3)}(\mathbf x-\mathbf y)\Delta_a\mathcal O(t,\mathbf y).
$$

Therefore

$$
\partial_\mu\langle Tj_a^\mu(x)\mathcal O(y)\rangle
=-i\delta^{(4)}(x-y)\langle\Delta_a\mathcal O(y)\rangle.
$$

For many insertions, repeat this argument for each time-ordering step function. One obtains

$$
\boxed{
\partial_\mu\langle Tj_a^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=
-i\sum_k\delta^{(4)}(x-x_k)
\langle T\mathcal O_1\cdots\Delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
}
$$

For fermionic insertions, the current for an ordinary bosonic symmetry is still bosonic, so the same schematic formula holds, but $\Delta_a$ must be applied as a graded derivation when it acts on products of fermionic operators.

## Integrated Ward identities

Integrate the local identity over a spacetime region $R$ containing the operator insertions. Gauss's theorem gives

$$
\int_R d^4x\,\partial_\mu\langle Tj_a^\mu(x)X\rangle
=
\int_{\partial R}d\Sigma_\mu\,\langle Tj_a^\mu(x)X\rangle.
$$

If the boundary term vanishes, then

$$
\boxed{
\sum_k
\langle T\mathcal O_1\cdots\Delta_a\mathcal O_k\cdots\mathcal O_n\rangle=0.
}
$$

This is the integrated Ward identity. It says that a vacuum correlator is invariant under the simultaneous symmetry transformation of all insertions.

For an Abelian symmetry, suppose

$$
\Delta\mathcal O_k=-iq_k\mathcal O_k.
$$

Then

$$
\sum_k (-iq_k)\langle T\mathcal O_1\cdots\mathcal O_n\rangle=0.
$$

Therefore

$$
\boxed{
\left(\sum_k q_k\right)\langle T\mathcal O_1\cdots\mathcal O_n\rangle=0.
}
$$

A nonzero correlator must be neutral. This is the correlation-function version of charge conservation.

## Example: complex scalar U(1)

For a complex scalar with charge $q$,

$$
\Delta\Phi=-iq\Phi,
\qquad
\Delta\Phi^\dagger=iq\Phi^\dagger.
$$

The Noether current is

$$
j^\mu=iq\,\Phi^\dagger\overleftrightarrow{\partial^\mu}\Phi.
$$

For a correlator containing $r$ fields $\Phi$ and $s$ fields $\Phi^\dagger$,

$$
G_{r,s}=\langle T\Phi(x_1)\cdots\Phi(x_r)\Phi^\dagger(y_1)\cdots\Phi^\dagger(y_s)\rangle,
$$

the local Ward identity is

$$
\begin{aligned}
\partial_\mu\langle Tj^\mu(x)\Phi(x_1)\cdots\Phi(x_r)\Phi^\dagger(y_1)\cdots\Phi^\dagger(y_s)\rangle
={}&-q\sum_{i=1}^r\delta^{(4)}(x-x_i)G_{r,s} \\
&+q\sum_{j=1}^s\delta^{(4)}(x-y_j)G_{r,s}.
\end{aligned}
$$

If the boundary term vanishes after integrating over $x$, then

$$
q(s-r)G_{r,s}=0.
$$

Thus

$$
G_{r,s}\ne0
\quad\Rightarrow\quad
r=s
$$

for a vacuum invariant under this $U(1)$ symmetry.

This simple selection rule is often the first practical Ward identity: correlators with net charge vanish.

## Non-Abelian Ward identities

For a field multiplet transforming as

$$
\Delta_a\Phi_i=-i(T_a)_i{}^j\Phi_j,
$$

the local Ward identity becomes

$$
\boxed{
\partial_\mu
\langle Tj_a^\mu(x)\Phi_{i_1}(x_1)\cdots\Phi_{i_n}(x_n)\rangle
=
-\sum_{k=1}^n\delta^{(4)}(x-x_k)(T_a)_{i_k}{}^j
\langle T\Phi_{i_1}(x_1)\cdots\Phi_j(x_k)\cdots\Phi_{i_n}(x_n)\rangle.
}
$$

The integrated identity is

$$
\sum_{k=1}^n
(T_a)_{i_k}{}^j
\langle T\Phi_{i_1}\cdots\Phi_j\cdots\Phi_{i_n}\rangle=0.
$$

This says that the correlator is an invariant tensor in the tensor product of the representations carried by its insertions. It is the non-Abelian version of total charge neutrality.

For example, in an unbroken $SU(N)$ theory with a fundamental field $\Phi_i$ and antifundamental field $\Phi^{\dagger j}$, the two-point function must have the invariant form

$$
\langle T\Phi_i(x)\Phi^{\dagger j}(y)\rangle
=\delta_i{}^j F(x-y),
$$

assuming translation invariance and no other internal tensors.

## Path-integral derivation

Ward identities can also be derived as changes of variables in the path integral. Let

$$
Z[J]=\int\mathcal D\Phi\,
\exp\left\{iS[\Phi]+i\int d^4x\,J_I(x)\mathcal O^I(x)\right\}.
$$

Make an infinitesimal local change of variables

$$
\Phi\mapsto\Phi+\alpha^a(x)\Delta_a\Phi.
$$

If the measure is invariant and the action has the local variation

$$
\delta S=-\int d^4x\,\alpha^a(x)\partial_\mu j_a^\mu(x),
$$

then the change of variables leaves $Z[J]$ unchanged and gives

$$
\boxed{
\langle\partial_\mu j_a^\mu(x)\rangle_J
=J_I(x)\langle\Delta_a\mathcal O^I(x)\rangle_J.
}
$$

Functional differentiation with respect to $J_I$ produces the contact-term Ward identities for ordinary correlators. The contact terms are source variations in disguise.

If the measure is not invariant, the Jacobian contributes an anomaly operator $\mathcal A_a(x)$:

$$
\boxed{
\langle\partial_\mu j_a^\mu(x)\rangle_J
=J_I(x)\langle\Delta_a\mathcal O^I(x)\rangle_J
+\langle\mathcal A_a(x)\rangle_J.
}
$$

After differentiating with respect to sources, this becomes

$$
\partial_\mu\langle Tj_a^\mu(x)X\rangle
= -i\sum_k\delta^{(4)}(x-x_k)\langle T\mathcal O_1\cdots\Delta_a\mathcal O_k\cdots\mathcal O_n\rangle
+\langle T\mathcal A_a(x)X\rangle,
$$

up to sign conventions for the definition of $\mathcal A_a$. This is the cleanest way to remember the anomaly caveat:

```txt
Symmetry of the action is not enough. The measure must also be symmetric.
```

## Z, W, and Γ identities

Ward identities can be written for several generating functionals.

The full generating functional $Z[J]$ encodes all correlators. Its Ward identity is usually the raw change-of-variables identity.

The connected generating functional $W[J]$, defined by

$$
Z[J]=e^{iW[J]},
$$

encodes connected correlators. The same symmetry identity written for $W[J]$ removes disconnected clutter.

The effective action $\Gamma[\varphi]$ is the Legendre transform of $W[J]$. For fields whose expectation values are

$$
\varphi^I(x)=\frac{\delta W}{\delta J_I(x)},
$$

the symmetry of the effective action is schematically

$$
\boxed{
\int d^4x\,\frac{\delta\Gamma}{\delta\varphi^I(x)}\Delta_a\varphi^I(x)=0
}
$$

for a non-anomalous linearly realized global symmetry.

Differentiating this equation gives Ward identities among one-particle irreducible vertices. This is why Ward identities are so powerful in renormalization: they constrain the counterterms and vertex functions directly, not merely the full correlators.

## Momentum-space Ward identities

The Fourier transform of a divergence gives a momentum contraction. If

$$
G_a^\mu(x;x_1,\ldots,x_n)=\langle Tj_a^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle,
$$

then, schematically,

$$
q_\mu \widetilde G_a^\mu(q;p_1,\ldots,p_n)
=\text{Fourier transform of contact terms}.
$$

The contact terms usually become differences of lower-point functions, or the same Green function with one insertion transformed.

For QED, the famous Ward–Takahashi identity relates the exact photon-fermion vertex to the exact fermion propagator. With momentum $q$ entering the photon vertex,

$$
\boxed{
q_\mu\Gamma^\mu(p+q,p)=S^{-1}(p+q)-S^{-1}(p)
}
$$

up to the convention for the electric charge factor in the definition of $\Gamma^\mu$.

For scattering amplitudes with an external photon, write the amplitude as

$$
\mathcal M(\varepsilon)=\varepsilon_\mu(k)\mathcal M^\mu(k,\ldots).
$$

The related on-shell Ward identity is

$$
\boxed{
k_\mu\mathcal M^\mu(k,\ldots)=0.
}
$$

Equivalently, replacing a physical polarization vector by the photon momentum gives zero. This is not merely a trick for simplifying amplitudes. It is the momentum-space form of current conservation and gauge redundancy.

## Gauge-theory preview

This page is mostly about global symmetries. Gauge theories add a new layer.

For QED, the Ward–Takahashi identities express the compatibility of current conservation, gauge fixing, and the coupling of the photon to charged fields. They imply, among other things, the transversality of physical photon amplitudes and relations among renormalization constants.

For non-Abelian gauge theories, gauge fixing hides the naive gauge symmetry and introduces ghost fields. The useful identities are then Slavnov–Taylor identities, most cleanly organized by BRST symmetry. They reduce to Ward identities in simple Abelian limits, but they are structurally richer because they involve ghosts, gauge-fixing terms, and the BRST differential.

The slogan is:

```txt
Global Ward identities constrain physical symmetry.
Gauge Ward identities constrain redundant descriptions and preserve unitarity.
```

The full story belongs in [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/), [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/), and the later gauge-theory sections.

## Explicit breaking and anomalies

If the classical action is not exactly invariant, then the current divergence contains an explicit breaking operator $B_a$:

$$
\partial_\mu j_a^\mu=B_a.
$$

The Ward identity becomes

$$
\partial_\mu\langle Tj_a^\mu(x)X\rangle
=\langle TB_a(x)X\rangle
-i\sum_k\delta^{(4)}(x-x_k)\langle T\mathcal O_1\cdots\Delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

If the action is invariant but the quantum measure is not, then

$$
\partial_\mu j_a^\mu=\mathcal A_a.
$$

For a Dirac fermion with an axial current, a typical schematic form is

$$
\partial_\mu j_5^\mu
=2im\bar\psi\gamma^5\psi+\mathcal A.
$$

The mass term is explicit breaking; the anomaly is quantum breaking. They have very different origins but appear in the same slot of the Ward identity.

## Spontaneously broken symmetries

For spontaneous symmetry breaking, the Lagrangian and current may still be symmetric, but the chosen vacuum is not invariant. The local Ward identity with a current insertion remains the right starting point, but the integrated step can fail because of infrared effects.

In a broken continuous symmetry, the current has matrix elements to massless Goldstone states. As a result, the boundary term that was casually dropped in the integrated identity may not vanish. This is how the Ward identity knows about Goldstone's theorem.

The short moral:

```txt
Unbroken symmetry gives selection rules and multiplets.
Broken symmetry gives Ward identities with massless poles.
Anomalous symmetry gives a modified divergence equation.
```

## What Ward identities are good for

Ward identities are not decorative. They are one of the main ways symmetry does work in QFT.

They imply selection rules for correlation functions and amplitudes. They force nonzero correlators to be singlets under exact unbroken symmetries.

They relate different Green functions. A current insertion can be replaced by symmetry transformations of the other insertions.

They constrain renormalization. Counterterms must respect the same Ward identities unless the symmetry is anomalous or explicitly broken.

They control longitudinal gauge-boson behavior. In QED, amplitudes with external photons are insensitive to replacing a polarization vector by a gauge-equivalent one. In non-Abelian gauge theory, the analogous statements are Slavnov–Taylor identities.

They expose anomalies. A would-be current conservation law that fails by a local operator is not a small bookkeeping error; it can change the consistency of the theory.

## Common pitfalls

### Dropping the contact terms

The most common mistake is to write

$$
\partial_\mu\langle Tj^\mu(x)X\rangle=0.
$$

This is wrong at the insertion points. The correct identity contains delta-function contact terms. Those terms are the whole reason the identity carries representation information.

### Confusing ordinary conservation with time-ordered conservation

The operator equation $\partial_\mu j^\mu=0$ and the time-ordered identity are not the same statement. Time ordering introduces step functions, and derivatives of step functions create equal-time commutators.

### Forgetting the measure

A path-integral derivation uses a change of variables. If the measure has a nontrivial Jacobian, the Ward identity gets an anomaly term.

### Ignoring composite-operator renormalization

Currents and current divergences are local composite operators. In interacting QFT, they must be defined by a regulator and renormalization prescription.

### Treating gauge and global identities as identical

Global Ward identities act on physical operators and states. Gauge identities are identities of a redundant description after gauge fixing. They overlap in QED, but they are not conceptually the same.

### Assuming integration is always harmless

Integrated Ward identities require boundary terms to vanish. In theories with Goldstone bosons, massless gauge fields, boundaries, defects, or asymptotic charges, that assumption can fail.

## Relations to nearby pages

- [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/) defines the charge operators and current algebra that produce the contact terms.
- [Time Ordering](/foundations/correlators-and-propagators/time-ordering/) explains why derivatives of time-ordered products generate delta functions.
- [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) introduces $Z[J]$ and $W[J]$, the natural home of path-integral Ward identities.
- [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/) explains $\Gamma[\varphi]$, whose symmetry gives one-particle irreducible Ward identities.
- [Path-Integral Measure](/foundations/path-integral-formalism/path-integral-measure/) explains how Jacobians and anomalies modify the naive symmetry identity.
- [Discrete Symmetries](/foundations/symmetry-and-spacetime/discrete-symmetries/) comes next, but discrete symmetries do not usually give local Noether currents.
- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) and [BRST Preview](/foundations/gauge-fields-first-principles/brst-preview/) will explain the gauge-theory descendants of Ward identities.

## Exercises

### Exercise 1: One insertion contact term

Let $\mathcal O(y)$ be a bosonic local operator and suppose

$$
\partial_\mu j^\mu=0,
\qquad
\Delta\mathcal O=i[Q,\mathcal O].
$$

Derive

$$
\partial_\mu\langle Tj^\mu(x)\mathcal O(y)\rangle
=-i\delta^{(4)}(x-y)\langle\Delta\mathcal O(y)\rangle.
$$

<details>
<summary><strong>Solution</strong></summary>

Write

$$
Tj^\mu(x)\mathcal O(y)
=\theta(x^0-y^0)j^\mu(x)\mathcal O(y)
+\theta(y^0-x^0)\mathcal O(y)j^\mu(x).
$$

Taking the divergence gives a bulk term and a step-function term. The bulk term is

$$
\langle T(\partial_\mu j^\mu(x))\mathcal O(y)\rangle=0.
$$

The step-function derivative gives

$$
\delta(x^0-y^0)\langle[j^0(x),\mathcal O(y)]\rangle.
$$

Using the local charge action,

$$
[j^0(t,\mathbf x),\mathcal O(t,\mathbf y)]
=-i\delta^{(3)}(\mathbf x-\mathbf y)\Delta\mathcal O(t,\mathbf y),
$$

we get

$$
\partial_\mu\langle Tj^\mu(x)\mathcal O(y)\rangle
=-i\delta^{(4)}(x-y)\langle\Delta\mathcal O(y)\rangle.
$$

</details>

### Exercise 2: Neutrality of complex-scalar correlators

For a complex scalar with

$$
\Delta\Phi=-iq\Phi,
\qquad
\Delta\Phi^\dagger=iq\Phi^\dagger,
$$

show that

$$
\langle T\Phi(x_1)\cdots\Phi(x_r)\Phi^\dagger(y_1)\cdots\Phi^\dagger(y_s)\rangle=0
$$

unless $r=s$, assuming the vacuum is invariant and no boundary term contributes.

<details>
<summary><strong>Solution</strong></summary>

The integrated Ward identity says

$$
\sum_k\langle T\mathcal O_1\cdots\Delta\mathcal O_k\cdots\mathcal O_n\rangle=0.
$$

Each $\Phi$ contributes $-iq$, and each $\Phi^\dagger$ contributes $+iq$. Therefore

$$
[-iqr+iqs]\langle T\Phi^r(\Phi^\dagger)^s\rangle=0.
$$

Equivalently,

$$
iq(s-r)G_{r,s}=0.
$$

If $r\ne s$, then

$$
G_{r,s}=0.
$$

</details>

### Exercise 3: Invariant form of a non-Abelian two-point function

Let $\Phi_i$ transform in the fundamental representation of an unbroken $SU(N)$ symmetry. Use the integrated Ward identity to show that

$$
\langle T\Phi_i(x)\Phi^{\dagger j}(y)\rangle
$$

is proportional to $\delta_i{}^j$.

<details>
<summary><strong>Solution</strong></summary>

Write

$$
G_i{}^j(x-y)=\langle T\Phi_i(x)\Phi^{\dagger j}(y)\rangle.
$$

For $SU(N)$,

$$
\Delta_a\Phi_i=-i(T_a)_i{}^k\Phi_k,
\qquad
\Delta_a\Phi^{\dagger j}=i\Phi^{\dagger k}(T_a)_k{}^j.
$$

The integrated Ward identity gives

$$
-i(T_a)_i{}^kG_k{}^j+iG_i{}^k(T_a)_k{}^j=0.
$$

Thus

$$
T_aG=GT_a
$$

for every generator $T_a$. In the irreducible fundamental representation, Schur's lemma implies

$$
G_i{}^j=F(x-y)\delta_i{}^j.
$$

</details>

### Exercise 4: Ward identity with explicit breaking

Suppose

$$
\partial_\mu j^\mu=B.
$$

Show that the one-insertion Ward identity becomes

$$
\partial_\mu\langle Tj^\mu(x)\mathcal O(y)\rangle
=\langle TB(x)\mathcal O(y)\rangle
-i\delta^{(4)}(x-y)\langle\Delta\mathcal O(y)\rangle.
$$

<details>
<summary><strong>Solution</strong></summary>

Repeat the derivation in Exercise 1, but do not set the bulk term to zero. The divergence of the current inside the time-ordered product gives

$$
\langle T(\partial_\mu j^\mu(x))\mathcal O(y)\rangle
=\langle TB(x)\mathcal O(y)\rangle.
$$

The derivative of the step functions is unchanged and gives

$$
-i\delta^{(4)}(x-y)\langle\Delta\mathcal O(y)\rangle.
$$

Combining the two terms gives the result.

</details>

### Exercise 5: Momentum contraction from a divergence

Let

$$
G^\mu(x;y,z)=\langle Tj^\mu(x)\Phi(y)\Phi^\dagger(z)\rangle
$$

for a complex scalar of charge $q$. Use the local Ward identity to show that the Fourier transform of $\partial_\mu G^\mu$ gives a momentum contraction of the transformed correlator.

<details>
<summary><strong>Solution</strong></summary>

The local Ward identity is

$$
\partial_\mu G^\mu(x;y,z)
=-q\delta^{(4)}(x-y)G(y,z)+q\delta^{(4)}(x-z)G(y,z),
$$

where

$$
G(y,z)=\langle T\Phi(y)\Phi^\dagger(z)\rangle.
$$

Fourier transform in $x$ with momentum $q_\mu$. The left-hand side gives $-iq_\mu\widetilde G^\mu$, up to the sign convention in the exponential. The right-hand side collapses the $x$ integral at $x=y$ and $x=z$. Thus the momentum contraction of the current-insertion correlator is fixed by the difference of two ordinary two-point functions with the current momentum injected at the charged insertions.

This is the same mechanism behind the Ward–Takahashi identity: a divergence becomes a momentum contraction, and contact terms become differences of inverse propagators or lower-point functions.

</details>

### Exercise 6: Symmetry of the effective action

Assume a non-anomalous linearly realized symmetry and an effective action $\Gamma[\varphi]$. Show that if

$$
\delta\varphi^I=\alpha^a\Delta_a\varphi^I,
$$

then invariance of $\Gamma$ implies

$$
\int d^4x\,\frac{\delta\Gamma}{\delta\varphi^I(x)}\Delta_a\varphi^I(x)=0.
$$

Explain why differentiating this relation gives identities among one-particle irreducible vertices.

<details>
<summary><strong>Solution</strong></summary>

If the effective action is invariant under the infinitesimal transformation, then

$$
0=\delta\Gamma
=\int d^4x\,\frac{\delta\Gamma}{\delta\varphi^I(x)}\delta\varphi^I(x).
$$

Substitute

$$
\delta\varphi^I=\alpha^a\Delta_a\varphi^I.
$$

Since $\alpha^a$ is arbitrary,

$$
\int d^4x\,\frac{\delta\Gamma}{\delta\varphi^I(x)}\Delta_a\varphi^I(x)=0.
$$

The one-particle irreducible vertices are functional derivatives of $\Gamma$ evaluated around a chosen background, often the vacuum. Differentiating the identity with respect to $\varphi$ therefore relates different 1PI vertices. These are the 1PI Ward identities.

</details>

## Sources and further reading

- J. C. Ward, “An Identity in Quantum Electrodynamics,” *Physical Review* **78** (1950), for the original QED Ward identity.
- Y. Takahashi, “On the Generalized Ward Identity,” *Nuovo Cimento* **6** (1957), for the generalized Ward–Takahashi identity.
- M. Srednicki, *Quantum Field Theory*, §22, for Noether currents and Ward identities with contact terms; §§67–68 for QED Ward identities.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 32, for generating functionals and Green functions; ch. 33, for Ward identities in QED renormalization.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §7.3, for canonical currents and charges; §10.4, for renormalized charge and Ward identities.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§7.4 and 9.6, for Ward identities, QED, and generating-functional derivations.
- C. Itzykson and J.-B. Zuber, *Quantum Field Theory*, chs. 7 and 12, for Ward identities, current insertions, anomalies, and Slavnov–Taylor identities.
- R. Jackiw, “Field Theoretic Investigations in Current Algebra,” in *Current Algebra and Anomalies*, for the classic current-algebra viewpoint.

## Version history

- **2026-05-23:** Initial qft.org page on Ward identities from operator current conservation, path-integral changes of variables, contact terms, source functionals, momentum-space contractions, effective-action identities, gauge-theory previews, explicit breaking, anomalies, and spontaneous-symmetry-breaking caveats.
