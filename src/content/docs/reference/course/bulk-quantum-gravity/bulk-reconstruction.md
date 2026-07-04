---
title: "Bulk Reconstruction"
description: "How approximately local bulk fields in AdS can be represented as nonlocal operators in the boundary CFT, and why reconstruction is perturbative, state-dependent in practice, and tied to causal and entanglement wedges."
sidebar:
  order: 30
---

AdS/CFT says that the boundary CFT is a complete description of the bulk quantum gravity theory. But a sharp question remains:

> If the CFT has no extra spatial dimension, how can it contain an operator that behaves like a local field at a point inside AdS?

Bulk reconstruction is the answer, at least perturbatively. It is the program of representing approximately local bulk observables as generally nonlocal CFT operators. In the simplest setting, a free scalar field in a fixed AdS background is reconstructed as a smeared boundary operator,

$$
\Phi(X)
=
\int_{\partial \mathrm{AdS}} d^d x\,K(X|x)\,\mathcal O(x),
$$

where $X$ is a bulk point, $x$ is a boundary point, $\mathcal O$ is the CFT operator dual to $\Phi$, and $K$ is a smearing kernel. This formula is the beginning of the story, not the end. In an interacting gravitational theory, it must be corrected order by order in $1/N$, dressed so that it is gauge-invariant, and interpreted inside a code subspace rather than on the entire CFT Hilbert space.

The slogan is:

$$
\text{bulk locality}
\quad
\text{is an emergent, approximate, code-subspace property of the CFT.}
$$

<figure class="doc-figure" style="--figure-width: 54rem;">

![Bulk reconstruction as boundary smearing](/figures/course/bulk-reconstruction.svg)

<figcaption>

A perturbative bulk field $\Phi(X)$ is represented by a nonlocal boundary operator. In global reconstruction the smearing may use the full boundary. In subregion reconstruction the available boundary region is tied to the causal wedge at the simplest HKLL level and, more generally, to the entanglement wedge in the quantum-error-correcting interpretation.

</figcaption>
</figure>

## Why this matters

The previous pages explained how a large-$N$, large-gap CFT produces a weakly coupled bulk effective field theory. A bulk EFT, however, contains local fields such as $\Phi(X)$, while the exact CFT contains only boundary operators such as $\mathcal O(t,\Omega)$. Bulk reconstruction explains how these two descriptions are compatible.

There are three reasons this is foundational.

First, reconstruction makes precise what it means for a boundary theory to contain a radial direction. The bulk point $X=(z,x)$ is not an extra fundamental coordinate in the CFT. It is encoded in a pattern of nonlocal boundary data.

Second, reconstruction tests locality. If the reconstructed operators satisfy

$$
[\Phi(X),\Phi(Y)]\approx 0
\qquad
\text{for spacelike separated }X,Y,
$$

then local bulk physics has emerged from boundary dynamics. The equality is approximate because bulk locality is an effective statement, corrected by interactions, gravitational dressing, and finite-$N$ effects.

Third, reconstruction leads directly to quantum error correction. A bulk operator may be reconstructable on more than one boundary region. This sounds paradoxical if one thinks of bulk information as copied into several places. It becomes natural if the boundary theory encodes the bulk like a quantum error-correcting code.

## The setting: one scalar field in fixed AdS

Start with a scalar field in $\mathrm{AdS}_{d+1}$,

$$
S
=
\frac12\int d^{d+1}X\sqrt{-g}\left[-g^{MN}\partial_M\Phi\partial_N\Phi-m^2\Phi^2\right].
$$

The field obeys

$$
(\Box-m^2)\Phi=0.
$$

Near the boundary in Poincare coordinates,

$$
ds^2
=
\frac{L^2}{z^2}\left(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu\right),
\qquad z\to 0,
$$

the normalizable part of a free field behaves as

$$
\Phi(z,x)
\sim
z^\Delta \mathcal O(x),
$$

more precisely in the operator sense,

$$
\mathcal O(x)
=
\lim_{z\to0} z^{-\Delta}\Phi(z,x)
$$

up to normalization conventions. The mass and dimension obey

$$
m^2L^2=\Delta(\Delta-d).
$$

The reconstruction problem reverses this limiting relation: given the boundary operator $\mathcal O$, recover the bulk field $\Phi(z,x)$.

## Global-mode reconstruction

The cleanest conceptual derivation uses global AdS. For a free scalar, expand the bulk field in normal modes:

$$
\Phi(t,\rho,\Omega)
=
\sum_{n,\ell,m}
\left[
 f_{n\ell m}(t,\rho,\Omega)a_{n\ell m}
 +
 f^*_{n\ell m}(t,\rho,\Omega)a^\dagger_{n\ell m}
\right].
$$

The normal-mode frequencies are

$$
\omega_{n\ell}=\Delta+2n+\ell,
\qquad
n=0,1,2,\ldots .
$$

This spectrum is exactly what the CFT predicts from the state-operator correspondence. A primary of dimension $\Delta$ gives a state of energy $\Delta$ on the cylinder, and derivatives generate descendants with energies $\Delta+2n+\ell$.

The boundary operator has a corresponding mode expansion,

$$
\mathcal O(t,\Omega)
=
\sum_{n,\ell,m}
\left[
 c_{n\ell}\,e^{-i\omega_{n\ell}t}Y_{\ell m}(\Omega)a_{n\ell m}
 +
 c^*_{n\ell}\,e^{i\omega_{n\ell}t}Y^*_{\ell m}(\Omega)a^\dagger_{n\ell m}
\right].
$$

Because the same oscillators $a_{n\ell m}$ and $a^\dagger_{n\ell m}$ appear in both expansions, one can invert the boundary expansion and substitute back into the bulk field. This produces a smearing representation,

$$
\Phi(t,\rho,\Omega)
=
\int dt' d\Omega'\,
K(t,\rho,\Omega|t',\Omega')\,
\mathcal O(t',\Omega').
$$

This is the simplest HKLL idea: bulk locality is reconstructed by combining infinitely many CFT modes in a very special nonlocal way.

## Poincare smearing

In the Poincare patch, for a free scalar satisfying suitable conditions on $\Delta$, one often writes a compact smearing formula of the form

$$
\Phi(z,t,\mathbf x)
=
C_{d,\Delta}
\int_{t'^2+|\mathbf y'|^2<z^2}
 dt'\,d^{d-1}\mathbf y'\,
\left(\frac{z^2-t'^2-|\mathbf y'|^2}{z}\right)^{\Delta-d}
\mathcal O(t+t',\mathbf x+i\mathbf y').
$$

Here

$$
C_{d,\Delta}
=
\frac{\Gamma(\Delta-d/2+1)}{\pi^{d/2}\Gamma(\Delta-d+1)}
$$

in a common normalization. The appearance of $\mathbf x+i\mathbf y'$ is not a typo. One convenient Lorentzian construction uses a complexified boundary spatial coordinate. Other versions use different regions or mode sums. The invariant lesson is not that this exact formula is universal; it is that a local bulk field is encoded in a nonlocal boundary operator with controlled support.

The smearing kernel is not arbitrary. It must solve the bulk wave equation in the bulk variable:

$$
(\Box_X-m^2)K(X|x')=0,
$$

and reproduce the correct boundary behavior,

$$
\lim_{z\to0}z^{-\Delta}K(z,x|x')=\delta^{(d)}(x-x')
$$

up to convention-dependent normalization.

## What has been reconstructed?

The formula reconstructs a free bulk field in a fixed background. That is already impressive, but it is not yet a fully nonperturbative local observable in quantum gravity.

There are several qualifications.

### It is a code-subspace operator

The bulk field $\Phi(X)$ is meaningful in a semiclassical sector, such as states obtained by acting with a finite number of low-energy operators on a given background:

$$
\mathcal H_{\mathrm{code}}
=
\operatorname{span}
\left\{
|\Omega\rangle,
\mathcal O|\Omega\rangle,
\mathcal O\mathcal O|\Omega\rangle,
\ldots
\right\}
$$

with total energy much smaller than the threshold where the background is significantly changed. The exact CFT Hilbert space also contains black-hole states, stringy states, and states that do not admit the same semiclassical geometry. A single fixed smearing formula cannot be expected to act as the same local bulk operator on all of them.

### It is perturbative in $1/N$

The free formula is the leading term:

$$
\Phi(X)
=
\Phi^{(0)}(X)+\frac{1}{N}\Phi^{(1)}(X)+\frac{1}{N^2}\Phi^{(2)}(X)+\cdots .
$$

In the CFT, the corrections generally involve multi-trace operators. Schematic terms look like

$$
\Phi^{(1)}(X)
\sim
\int dx_1dx_2\,
K_2(X|x_1,x_2):\mathcal O(x_1)\mathcal O(x_2):+\text{other operators}.
$$

These corrections are not decorative. They are required so that bulk commutators have the right causal behavior order by order in perturbation theory.

### It must be gravitationally dressed

In a theory with dynamical gravity, a strictly local gauge-invariant operator at a bulk point does not exist. Diffeomorphisms move points. A meaningful bulk operator must specify the point relationally or attach a gravitational dressing to the boundary. Schematically, one reconstructs a dressed operator

$$
\Phi_\Gamma(X),
$$

where $\Gamma$ indicates some choice of dressing or relational prescription. Different dressings agree at leading order in a weak-gravity limit but differ in their boundary charges and commutators.

This is the gravitational version of a familiar gauge-theory fact: a charged local field is not gauge-invariant unless it is dressed by a Wilson line or another dressing.

## Reconstruction and bulk causality

A reconstructed field should reproduce bulk correlation functions. For example,

$$
\langle \Phi(X)\Phi(Y)\rangle
=
\int dx\,dy\,K(X|x)K(Y|y)\langle \mathcal O(x)\mathcal O(y)\rangle
$$

should give the bulk Wightman function in the appropriate state. Similarly, commutators should reproduce the bulk causal structure:

$$
[\Phi(X),\Phi(Y)]
=
0
\qquad
\text{when }X\text{ and }Y\text{ are bulk spacelike separated}
$$

at leading order in the bulk EFT.

This is nontrivial. The boundary operator $\mathcal O(x)$ is local only on the boundary. The bulk notion of spacelike separation is emergent. The smearing kernel arranges many boundary contributions so that the unwanted boundary singularities cancel in the bulk spacelike region.

At finite $N$, exact bulk locality cannot persist without modification. Quantum gravity has a finite entropy in finite regions, black holes form, and gravitational dressing produces long-range commutators. Thus reconstruction teaches a precise lesson:

$$
\text{bulk locality is excellent inside its regime, but it is not fundamental.}
$$

## Causal-wedge reconstruction

For a boundary spatial region $A$, define its domain of dependence $D[A]$. The causal wedge is

$$
\mathcal C[A]
=
J^+_{\mathrm{bulk}}(D[A])\cap J^-_{\mathrm{bulk}}(D[A]).
$$

It is the set of bulk points that can both receive signals from and send signals to $D[A]$. In favorable circumstances, HKLL-type methods reconstruct bulk fields in $\mathcal C[A]$ using operators supported in $D[A]$.

This is intuitive: if a point is in the causal wedge of $A$, boundary observers in $A$ have enough causal access to probe it using boundary sources and responses.

But causal-wedge reconstruction is not the full story. The entanglement wedge $\mathcal W_E[A]$ is generally larger:

$$
\mathcal C[A]
\subseteq
\mathcal W_E[A].
$$

Modern subregion duality says that bulk operators in $\mathcal W_E[A]$ can be reconstructed on $A$, at least within an appropriate code subspace. This stronger statement is one of the main motivations for the quantum-error-correction picture developed on the next page.

## Entanglement-wedge reconstruction preview

Suppose $a$ is a bulk region inside the entanglement wedge of a boundary region $A$:

$$
a\subset \mathcal W_E[A].
$$

Entanglement-wedge reconstruction says that for a bulk operator $\phi_a$ localized in $a$, there exists a boundary operator $O_A$ supported only on $A$ such that

$$
O_A|\psi\rangle
=
\phi_a|\psi\rangle
$$

for all states $|\psi\rangle$ in the chosen code subspace.

More carefully, if $V:\mathcal H_{\mathrm{code}}\to\mathcal H_{\mathrm{CFT}}$ is the encoding map, then

$$
O_A V|\psi\rangle
=
V\phi_a|\psi\rangle
\qquad
\text{for all }|\psi\rangle\in\mathcal H_{\mathrm{code}}.
$$

This is different from saying that $O_A$ equals $\phi_a$ as an operator on the full exact Hilbert space. It only needs to reproduce the correct action on the semiclassical code subspace.

That small phrase, “on the code subspace,” saves bulk reconstruction from many fake paradoxes.

## Why reconstruction is nonlocal on the boundary

A local bulk excitation is not dual to a local boundary excitation. The boundary imprint of a bulk particle is spread out. This is not a bug; it is holography doing its job.

One simple way to see this is from radial depth. A particle near the boundary creates a sharply localized boundary disturbance. A particle deep in AdS is more infrared from the CFT point of view and has a broader boundary representation. Radial position is encoded in scale, not in an extra local coordinate.

Another way to see it is from modes. A bulk point is specified by a coherent superposition of global normal modes. Each normal mode maps to a CFT energy-angular-momentum mode. Combining them to localize in the radial direction requires a nonlocal sum over boundary data.

Thus the dictionary is not

$$
\Phi(z,x)\leftrightarrow \mathcal O(x).
$$

That formula is true only in the boundary limit. In the interior, the correct statement is closer to

$$
\Phi(z,x)
\leftrightarrow
\text{a nonlocal CFT operator built from }\mathcal O\text{ and its multi-trace products}.
$$

## Reconstruction behind horizons

Bulk reconstruction is most subtle in black-hole geometries. Outside a horizon, one can often use HKLL-like reconstruction in the exterior region with appropriate boundary time support. Behind a horizon, reconstruction depends strongly on the state and on what boundary systems are available.

For an eternal two-sided AdS black hole, the thermofield-double state gives two CFTs:

$$
|\mathrm{TFD}\rangle
=
\frac{1}{\sqrt Z}\sum_n e^{-\beta E_n/2}|n\rangle_L|n\rangle_R.
$$

The two-sided geometry has an Einstein–Rosen bridge, and interior reconstruction can use both boundaries in a way tied to the state. For a one-sided black hole formed by collapse, reconstruction is more subtle and may require very complicated CFT operators.

The important point for this foundations course is modest but essential: reconstruction is not a universal recipe that turns every point in every geometry into a simple boundary integral. It is a perturbative construction whose form depends on the background, the state, the chosen code subspace, and the region of the boundary allowed for reconstruction.

## Relation to the extrapolate dictionary

There are two related but distinct statements.

The extrapolate dictionary says

$$
\mathcal O(x)
=
\lim_{z\to0} z^{-\Delta}\Phi(z,x)
$$

up to normalization.

Bulk reconstruction says

$$
\Phi(z,x)
=
\int dx'\,K(z,x|x')\mathcal O(x')+\text{multi-trace corrections}.
$$

The extrapolate dictionary extracts a boundary operator from the near-boundary limit of a bulk field. Reconstruction builds an interior bulk field from boundary operators. The two are compatible, but they answer opposite questions.

## Dictionary checkpoint

| Bulk statement | Boundary interpretation |
|---|---|
| free bulk field $\Phi(X)$ | smeared single-trace operator $\int K\mathcal O$ |
| bulk interactions | multi-trace corrections to reconstruction |
| radial position | scale and nonlocal pattern of boundary support |
| causal wedge $\mathcal C[A]$ | region accessible by causal boundary probes in $D[A]$ |
| entanglement wedge $\mathcal W_E[A]$ | region reconstructable from subregion $A$ in the code subspace |
| gravitational dressing | choice of relational/gauge-invariant boundary anchoring |
| finite $N$ | breakdown of exact local bulk fields as fundamental observables |

The most important takeaway is:

$$
\Phi(X)\text{ is not an elementary CFT operator. It is an emergent operator representation valid in a semiclassical code subspace.}
$$

## Common confusions

### “The boundary operator at $x$ is the bulk field at $(z,x)$.”

Only in the limit $z\to0$. At finite radial position, the bulk field is represented by a nonlocal boundary operator. The deeper the point, the more nonlocal the representation typically becomes.

### “HKLL gives an exact operator in quantum gravity.”

No. HKLL gives a perturbative reconstruction of bulk fields in a chosen semiclassical background. The exact CFT exists nonperturbatively, but exact local bulk operators do not exist in the same simple way.

### “Different reconstructions mean the bulk operator has been copied.”

No. Different boundary operators can have the same action on a code subspace while acting differently outside that subspace. This is precisely the logic of quantum error correction.

### “A local bulk field must commute exactly at spacelike separation.”

In bulk EFT, yes, up to the expected perturbative precision. In quantum gravity, gravitational dressing, constraints, and finite entropy obstruct exact local commuting subalgebras in the naive sense.

### “The entanglement wedge is just the causal wedge.”

Usually not. The entanglement wedge is often larger, especially for large boundary regions or black-hole geometries. The difference is one reason quantum error correction enters holography.

## Exercises

### Exercise 1: Near-boundary consistency

Suppose a smearing kernel satisfies

$$
\Phi(z,x)=\int dx'\,K(z,x|x')\mathcal O(x')
$$

and

$$
\lim_{z\to0}z^{-\Delta}K(z,x|x')=\delta^{(d)}(x-x').
$$

Show that the reconstruction formula is consistent with the extrapolate dictionary.

<details>
<summary><strong>Solution</strong></summary>

Multiply the reconstruction formula by $z^{-\Delta}$ and take $z\to0$:

$$
\lim_{z\to0}z^{-\Delta}\Phi(z,x)
=
\int dx'\,
\lim_{z\to0}z^{-\Delta}K(z,x|x')\mathcal O(x').
$$

Using the assumed boundary behavior of the kernel gives

$$
\lim_{z\to0}z^{-\Delta}\Phi(z,x)
=
\int dx'\,\delta^{(d)}(x-x')\mathcal O(x')
=
\mathcal O(x).
$$

This is the extrapolate dictionary, up to whichever normalization convention was chosen for $K$ and $\mathcal O$.

</details>

### Exercise 2: Why multi-trace corrections are expected

A normalized single-trace operator has connected three-point functions of order $1/N$:

$$
\langle \mathcal O\mathcal O\mathcal O\rangle_c\sim \frac1N.
$$

Explain why an interacting bulk field cannot be reconstructed only as a linear smearing of $\mathcal O$.

<details>
<summary><strong>Solution</strong></summary>

A linear smearing of $\mathcal O$ describes a generalized-free, leading large-$N$ bulk field. But connected three-point functions of order $1/N$ indicate cubic bulk interactions. A bulk field interacting through cubic vertices receives corrections that are quadratic in lower-order fields. In CFT language, these corrections are represented by smeared double-trace operators such as

$$
:\mathcal O(x_1)\mathcal O(x_2):.
$$

Thus the interacting reconstruction has the schematic form

$$
\Phi
=
\int K_1\mathcal O
+
\frac1N\int K_2:\mathcal O\mathcal O:
+
\cdots .
$$

The multi-trace corrections are needed both to reproduce interacting correlators and to restore bulk locality order by order in $1/N$.

</details>

### Exercise 3: Redundant reconstructions

Let $P$ be the projector onto a code subspace. Suppose two boundary operators $O_A$ and $O_B$ satisfy

$$
P O_A P=P O_B P.
$$

Show that all matrix elements inside the code subspace agree.

<details>
<summary><strong>Solution</strong></summary>

For any two code states $|\psi\rangle$ and $|\chi\rangle$, we have

$$
P|\psi\rangle=|\psi\rangle,
\qquad
P|\chi\rangle=|\chi\rangle.
$$

Therefore

$$
\langle\chi|O_A|\psi\rangle
=
\langle\chi|P O_A P|\psi\rangle
=
\langle\chi|P O_B P|\psi\rangle
=
\langle\chi|O_B|\psi\rangle.
$$

So $O_A$ and $O_B$ may be different operators on the full CFT Hilbert space, but they represent the same logical bulk operator inside the code subspace.

</details>

### Exercise 4: Causal wedge versus entanglement wedge

Why is it plausible that causal-wedge reconstruction is not the final answer for subregion duality?

<details>
<summary><strong>Solution</strong></summary>

The causal wedge only uses causal propagation between the boundary domain of dependence $D[A]$ and the bulk. But quantum gravity also encodes information through entanglement. The RT/HRT surface and the entanglement wedge are determined by entropy, not just causal reachability. In many examples the entanglement wedge is larger than the causal wedge:

$$
\mathcal C[A]\subsetneq\mathcal W_E[A].
$$

If bulk information in $\mathcal W_E[A]$ is encoded in the density matrix on $A$, then causal propagation alone misses part of the reconstructable region. This motivates the stronger entanglement-wedge reconstruction statement and, ultimately, the quantum-error-correction interpretation.

</details>

## Further reading

- A. Hamilton, D. Kabat, G. Lifschytz, and D. A. Lowe, [Local Bulk Operators in AdS/CFT: A Boundary View of Horizons and Locality](https://arxiv.org/abs/hep-th/0506118).
- A. Hamilton, D. Kabat, G. Lifschytz, and D. A. Lowe, [Local Bulk Operators in AdS/CFT: A Holographic Description of the Black Hole Interior](https://arxiv.org/abs/hep-th/0612053).
- D. Kabat, G. Lifschytz, and D. A. Lowe, [Constructing Local Bulk Observables in Interacting AdS/CFT](https://arxiv.org/abs/1102.2910).
- T. De Jonckheere, [Modave Lectures on Bulk Reconstruction in AdS/CFT](https://arxiv.org/abs/1711.07787).
- X. Dong, D. Harlow, and A. C. Wall, [Reconstruction of Bulk Operators within the Entanglement Wedge in Gauge-Gravity Duality](https://arxiv.org/abs/1601.05416).
- D. Harlow, [TASI Lectures on the Emergence of the Bulk in AdS/CFT](https://arxiv.org/abs/1802.01040).
