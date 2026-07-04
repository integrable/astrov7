---
title: "Islands and Information"
description: "How quantum extremal surfaces, islands, and replica wormholes reproduce the Page curve and sharpen the black-hole information problem in holography."
sidebar:
  order: 70
---

The previous page introduced quantum extremal surfaces as the quantum-corrected version of RT/HRT. This page applies that idea to its most dramatic use: the fine-grained entropy of Hawking radiation.

The central lesson is simple to state and subtle to interpret. In a gravitational theory, the entropy of a nongravitating radiation region $R$ is not always computed by the entropy of $R$ alone. One must also allow for **islands**: gravitating regions $I$ whose boundaries are quantum extremal surfaces and whose degrees of freedom are included in the entropy calculation for $R$.

The island formula is

$$
\boxed{
S(R)
=
\min_I\,\operatorname*{ext}_{\partial I}
\left[
\frac{\operatorname{Area}(\partial I)}{4G_N}
+S_{\mathrm{bulk}}(R\cup I)
+\cdots
\right].
}
$$

The dots include local counterterms and, in higher-derivative gravity, the appropriate corrections to the area functional. If the island is empty, $I=\varnothing$, the formula reduces to the ordinary semiclassical entropy of the radiation. If a nonempty island dominates, part of the black-hole interior belongs to the quantum entanglement wedge of the radiation.

That last sentence is easy to misunderstand. An island is not a chunk of spacetime that has flown into the laboratory. It is a region in the gravitating spacetime that must be included when computing the fine-grained entropy of the radiation Hilbert space.

<figure class="doc-figure" style="--figure-width: 56rem;">

![The island formula as a competition between the empty-island saddle and a nonempty-island saddle. The minimum of their generalized entropies gives the Page curve.](/figures/course/islands-and-information.svg)

<figcaption>

The radiation entropy is computed by minimizing over quantum extremal saddles. At early times the empty-island saddle $I=\varnothing$ dominates. At late times a nonempty island $I$ can dominate, and the quantum entanglement wedge $\mathcal E_Q[R]$ of the radiation includes part of the black-hole interior. The Page transition is a change of dominant saddle in the generalized entropy.

</figcaption>
</figure>

## Why this matters

Hawking's semiclassical calculation predicts that black holes emit nearly thermal radiation. If one treats each newly emitted Hawking quantum as entangled with an interior partner and then traces over the black-hole interior, the entropy of the emitted radiation grows roughly monotonically.

For an evaporating black hole formed from a pure state, that cannot be the full story in a unitary theory. The full state of “black hole plus radiation” remains pure, and after complete evaporation only the radiation remains. Thus the fine-grained entropy of all radiation should start at zero, rise for a while, and eventually return to zero. The expected curve is the **Page curve**.

The paradox is not that Hawking radiation is approximately thermal at early times. It should be. The paradox is that the naive semiclassical computation seems to keep increasing the fine-grained entropy long after unitarity says it must turn over.

AdS/CFT already strongly suggests that information is not destroyed in black-hole evaporation, because the dual boundary quantum system evolves unitarily. Islands explain how a semiclassical bulk computation can reproduce the fine-grained Page curve.

## The Page curve in one line

Let $R(t)$ be the radiation collected up to time $t$. Its fine-grained entropy is

$$
S(R(t))=-\operatorname{Tr}\rho_{R(t)}\log\rho_{R(t)}.
$$

The naive Hawking calculation gives a growing answer,

$$
S_{\varnothing}(R(t))\sim S_{\mathrm{Hawking}}(R(t)),
$$

where the subscript $\varnothing$ means that no island has been included.

The island saddle gives another candidate entropy,

$$
S_I(R(t))
=
\frac{\operatorname{Area}(\partial I)}{4G_N}
+S_{\mathrm{bulk}}(R(t)\cup I)
+\cdots.
$$

The physical fine-grained entropy is the smaller extremized answer:

$$
S(R(t))=\min\left\{S_{\varnothing}(R(t)),S_I(R(t)),\ldots\right\}.
$$

At early times, $S_{\varnothing}$ is small and wins. Around the Page time, the two saddles exchange dominance. At late times, the island saddle wins and prevents the radiation entropy from continuing to grow.

This is the same logic as ordinary saddle-point physics. A subdominant saddle can be invisible for one range of parameters and then become dominant after a phase transition.

## The physical setup

A technically clean island setup usually contains two parts:

1. a **gravitating region**, containing a black hole;
2. a **nongravitating bath**, which collects Hawking radiation.

In AdS/CFT, this can be engineered by coupling the boundary CFT to an auxiliary nongravitating system that absorbs radiation. Without such a bath, a large AdS black hole with reflecting boundary conditions does not evaporate away in the same way; the AdS boundary acts like a box.

Let $R$ be a region in the bath containing some collected Hawking radiation. The bath has an ordinary Hilbert-space interpretation, so asking for $S(R)$ is meaningful. The gravitating region is more subtle because local subregions in quantum gravity are constrained by diffeomorphism invariance. The island formula says that when computing $S(R)$, one must extremize over possible gravitating regions $I$ that are included together with $R$.

The candidate region whose bulk entropy appears in the formula is

$$
R\cup I.
$$

The boundary of $I$ is a quantum extremal surface:

$$
\delta_{\partial I}
\left[
\frac{\operatorname{Area}(\partial I)}{4G_N}
+S_{\mathrm{bulk}}(R\cup I)
+\cdots
\right]=0.
$$

After finding all candidate extrema, choose the one with smallest generalized entropy.

## The empty island saddle

The simplest candidate is

$$
I=\varnothing.
$$

Then there is no island boundary and no area term. The entropy is simply

$$
S_{\varnothing}(R)=S_{\mathrm{bulk}}(R).
$$

In Hawking's semiclassical picture, each emitted quantum is entangled with a partner mode behind the horizon. If the partner is not included in the entropy region, the radiation looks mixed. As radiation accumulates in the bath, $S_{\mathrm{bulk}}(R)$ grows.

This is not wrong at early times. Before the Page time, the empty-island saddle is the correct dominant saddle. Hawking's calculation captures the leading semiclassical physics of the outgoing radiation.

The failure is extrapolating that saddle beyond its domain of dominance.

## The island saddle

The island saddle includes a region $I$ behind or near the black-hole horizon. In that case,

$$
S_I(R)
=
\frac{\operatorname{Area}(\partial I)}{4G_N}
+S_{\mathrm{bulk}}(R\cup I)
+\cdots.
$$

Why can this be smaller at late times?

The emitted Hawking quanta in $R$ are correlated with interior partner modes. If the island $I$ contains the partner modes, then the bulk entropy of $R\cup I$ can be much smaller than the entropy of $R$ alone. The price is the area term $\operatorname{Area}(\partial I)/(4G_N)$.

So the competition is:

$$
\text{empty island:}
\quad
S_{\varnothing}\sim \text{entropy of emitted radiation},
$$

versus

$$
\text{nonempty island:}
\quad
S_I\sim \text{area cost} + \text{entropy after including partners}.
$$

At early times, the radiation entropy is small, so the empty island wins. At late times, the empty-island entropy is large, while the island saddle is controlled by a horizon-area-like term. The island wins.

## A toy Page-curve estimate

A useful caricature is

$$
S_{\varnothing}(t)=\gamma t,
$$

where $\gamma$ is the rate at which coarse-grained Hawking entropy accumulates, and

$$
S_I(t)=S_{\mathrm{BH}}(t),
$$

where $S_{\mathrm{BH}}(t)$ is the remaining Bekenstein–Hawking entropy of the black hole. For a simple model, take

$$
S_{\mathrm{BH}}(t)=S_0-\gamma t.
$$

Then

$$
S(R(t))=\min\{\gamma t,S_0-\gamma t\}.
$$

The Page time occurs when

$$
\gamma t_{\mathrm{Page}}=S_0-\gamma t_{\mathrm{Page}},
$$

so

$$
t_{\mathrm{Page}}=\frac{S_0}{2\gamma}.
$$

This toy model is not a realistic evaporation calculation. The real evaporation rate is time-dependent, greybody factors matter, and the precise island location is found by extremizing generalized entropy. But the toy model captures the core mechanism: the entropy is the minimum of competing generalized-entropy saddles.

## What is an island?

An island is a gravitating region $I$ included in the entropy computation of a nongravitating region $R$.

More precisely, for a candidate island $I$, the island boundary $\partial I$ is a codimension-two surface in the gravitating spacetime. In two-dimensional dilaton gravity, $\partial I$ is a set of points. In higher-dimensional gravity, it is an ordinary codimension-two surface, like an RT/HRT/QES surface.

The island is selected by extremizing generalized entropy:

$$
\delta_{\partial I}S_{\mathrm{gen}}(I;R)=0.
$$

The selected island is not chosen by hand. It is a saddle of the gravitational entropy calculation.

A useful slogan is:

$$
\boxed{
\text{an island is a part of the gravitational region encoded in the radiation wedge.}
}
$$

But the word “encoded” is doing serious work. It means quantum-error-correcting, entanglement-wedge reconstruction, not naive local duplication.

## Entanglement wedge interpretation

Before the Page time, the quantum entanglement wedge of the radiation is essentially the radiation region itself:

$$
\mathcal E_Q[R]\approx R.
$$

After the Page transition, the radiation's quantum entanglement wedge includes the island:

$$
\mathcal E_Q[R]\approx R\cup I.
$$

This statement has a powerful consequence. Operators supported inside the island can, in principle, be reconstructed from the radiation degrees of freedom.

This is one of the sharpest modern formulations of black-hole information recovery. After the Page time, part of the black-hole interior is encoded in the Hawking radiation.

However, this does not mean an outside observer can send a local signal from the interior to the radiation region. Entanglement-wedge reconstruction is nonlocal, code-subspace dependent, and usually computationally fantastical. It is a statement about what the radiation Hilbert space contains, not about easy experimental access.

## Why this does not violate no-cloning

A common worry is that the island seems to place the same interior information in two places: inside the black hole and in the radiation.

This is not ordinary duplication. In holography, the same bulk operator can sometimes be reconstructed from different boundary regions. These reconstructions are not independent copies acting on a tensor-product Hilbert space. They are different boundary representations of the same logical operator within a code subspace.

This is familiar from quantum error correction. A logical qubit can be reconstructible from several different subsets of physical qubits without being cloned. The reconstructions agree on the code subspace, but they are not independent physical copies.

Thus the island statement is compatible with quantum mechanics:

$$
\text{interior operator}
\quad\longleftrightarrow\quad
\text{logical operator reconstructible from radiation after Page time}.
$$

The price is that semiclassical locality is not a fundamental notion across the whole Hilbert space.

## Replica wormholes

Where does the island formula come from?

The cleanest derivation uses the gravitational replica trick. For an ordinary nongravitating QFT,

$$
S(R)
=
-\left.\partial_n \log \operatorname{Tr}\rho_R^n\right|_{n=1}.
$$

Equivalently, one computes a replicated path integral with $n$ copies glued cyclically along the region $R$, then analytically continues in $n$.

In gravity, the replicated path integral must also sum over gravitational saddles. The naive saddle has $n$ disconnected gravitational copies. This saddle gives the no-island answer.

But there can be additional saddles in which the replicas are connected through the gravitational region. These are called **replica wormholes**. In the limit $n\to 1$, the fixed locus of the replica symmetry becomes the quantum extremal surface $\partial I$, and the gravitational action produces the area term.

Schematic logic:

$$
\text{replica wormhole saddle}
\quad\Longrightarrow\quad
\partial I\text{ QES}
\quad\Longrightarrow\quad
S_I(R).
$$

The Page transition is the point where the replica-wormhole saddle becomes dominant in the entropy calculation.

Two cautions are important.

First, replica wormholes are saddles of the entropy path integral. They are not ordinary Lorentzian wormholes that an observer travels through.

Second, they correct the fine-grained entropy, not necessarily local low-point observables of the Hawking radiation. The outgoing radiation can remain locally very close to thermal while its fine-grained entropy is governed by a different saddle.

## Why Hawking's local calculation can still be right

The island formula does not say that Hawking's calculation was silly. Hawking's calculation is a local semiclassical calculation of radiation production. It correctly captures many coarse-grained features: temperature, flux, and the approximate thermality of early radiation.

The Page curve is a statement about fine-grained entropy, which is a highly nonlocal observable. Fine-grained entropy is sensitive to which saddle dominates the replicated gravitational path integral.

Thus there is no contradiction in saying:

$$
\text{local radiation looks thermal}
$$

while also saying

$$
\text{the fine-grained radiation entropy follows the Page curve}.
$$

The first statement concerns local or low-order observables. The second concerns a global entropy calculation.

## Islands in AdS/CFT language

In ordinary AdS/CFT with reflecting boundary conditions, a large AdS black hole is dual to a thermal state or ensemble in the boundary CFT. It does not evaporate away into empty space because radiation reflects off the AdS boundary.

To model evaporation, one often couples the boundary CFT to an auxiliary bath. Radiation can then leave the holographic system and enter a nongravitating reservoir. The full system is still an ordinary quantum system:

$$
\mathcal H_{\mathrm{total}}
=
\mathcal H_{\mathrm{CFT}}\otimes\mathcal H_{\mathrm{bath}}.
$$

The combined evolution is unitary. One can ask for the entropy of radiation degrees of freedom in the bath. The island formula gives a bulk semiclassical calculation of that entropy.

Before the Page time, the radiation wedge is outside the black hole. After the Page time, the radiation wedge includes an island behind the horizon. This is the bulk version of the statement that late enough radiation contains enough information to purify earlier radiation and reconstruct part of the interior.

## Eternal black holes and saturation

Many textbook island computations use eternal black holes coupled to baths. In those setups the radiation entropy can grow linearly without islands. The island saddle appears and makes the entropy saturate at an order-$S_{\mathrm{BH}}$ value.

This is slightly different from a one-sided evaporating black hole that disappears completely, where the final entropy of all radiation should return to zero if the initial state was pure. But the mechanism is the same: the entropy is determined by the minimum among generalized-entropy saddles, and the island saddle prevents indefinite growth.

So there are several related curves:

- for an evaporating pure-state black hole, the radiation entropy rises and then falls;
- for an eternal black hole with baths, the entropy may rise and then saturate;
- for subregions of radiation, there can be additional phase transitions.

All of them are island/QES saddle competitions.

## What information is recovered?

The island formula computes von Neumann entropy. Entropy is not the same thing as an explicit decoding protocol.

From the Page curve one learns that the radiation contains the correlations required by unitarity. From the entanglement-wedge interpretation one learns that some interior operators are encoded in the radiation after the Page time. But actually extracting those operators may be exponentially hard, and the reconstruction may depend on a code subspace.

Thus a careful hierarchy is:

$$
\text{Page curve}
\quad\Rightarrow\quad
\text{fine-grained entropy consistent with unitarity},
$$

$$
\text{island wedge}
\quad\Rightarrow\quad
\text{interior encoded in radiation},
$$

$$
\text{explicit decoder}
\quad\Rightarrow\quad
\text{operational recovery protocol}.
$$

The first two are what the island formula gives. The third is a harder quantum-information problem.

## What islands do and do not solve

Islands are a major advance because they show how semiclassical gravity, when used correctly for fine-grained entropy, can reproduce Page-curve behavior in controlled models.

They do not mean that every question about black holes is finished. Important open questions remain:

- How should the island story be formulated in the most realistic asymptotically flat settings?
- How precisely do replica wormholes arise in a complete microscopic theory in all examples?
- What is the operational meaning of reconstruction from radiation for realistic observers?
- How do complexity, decoding difficulty, and state dependence fit into the story?
- What is the endpoint description of evaporation in models beyond controlled semiclassical approximations?

The right attitude is neither “the information problem is trivial now” nor “islands are just a trick.” The correct statement is more interesting: islands give a concrete semiclassical mechanism for Page-curve entropy in quantum gravity, and they reveal that the entanglement wedge of radiation can include black-hole interior regions.

## Relation to the previous pages

The chain of ideas in this unit is now:

$$
\text{QFT entanglement}
\longrightarrow
\text{RT/HRT}
\longrightarrow
\text{entanglement wedges}
\longrightarrow
\text{QES}
\longrightarrow
\text{islands}.
$$

Islands are not an extra principle detached from holographic entanglement. They are the quantum extremal surface prescription applied to radiation systems that include nongravitating baths.

The conceptual upgrade is that the entropy region can be disconnected:

$$
R\quad\leadsto\quad R\cup I.
$$

The bulk region used in the entropy calculation is not determined only by where the radiation is located in semiclassical spacetime. It is determined by the dominant generalized-entropy saddle.

## Dictionary checkpoint

| Boundary/radiation description | Bulk gravitational description |
|---|---|
| radiation Hilbert space $\mathcal H_R$ | bath region $R$ plus possible island $I$ |
| fine-grained entropy $S(R)$ | minimum generalized entropy over islands |
| early radiation entropy growth | empty-island saddle dominates |
| Page transition | change of dominant QES saddle |
| late-time information recovery | radiation wedge includes an island |
| interior reconstruction from radiation | entanglement-wedge reconstruction in a code subspace |
| unitarity constraint | Page curve rather than monotonic Hawking entropy |

The core formula is

$$
S(R)
=
\min_I\,\operatorname*{ext}_{\partial I}S_{\mathrm{gen}}(I;R),
$$

with

$$
S_{\mathrm{gen}}(I;R)
=
\frac{\operatorname{Area}(\partial I)}{4G_N}
+S_{\mathrm{bulk}}(R\cup I)+\cdots.
$$

## Common confusions

### “The island is physically located in the bath.”

No. The island is a region in the gravitating spacetime. It is included in the entropy computation for the bath radiation because it lies in the radiation's quantum entanglement wedge.

### “The island formula contradicts Hawking radiation.”

No. Hawking's calculation gives the local semiclassical production of radiation and the empty-island entropy saddle. The island formula says that for fine-grained entropy, another saddle can dominate at late times.

### “Replica wormholes are traversable wormholes.”

No. Replica wormholes are saddles of a replicated gravitational path integral used to compute entropy. They are not ordinary Lorentzian bridges through which signals pass.

### “After the Page time, the whole black-hole interior is simply outside.”

No. The statement is region-dependent. The island belongs to the quantum entanglement wedge of a specified radiation region. This is a reconstruction statement, not a simple relocation of spacetime points.

### “Islands give an easy decoder.”

No. Entanglement-wedge reconstruction establishes that a representation exists in a code-subspace sense. It does not imply that decoding Hawking radiation is practical.

### “The island can be chosen arbitrarily.”

No. The island boundary must extremize generalized entropy, and among the extrema one chooses the smallest generalized entropy. The formula is variational, not discretionary.

## Exercises

### Exercise 1: Toy Page time

Suppose the empty-island entropy and island entropy are approximated by

$$
S_{\varnothing}(t)=\gamma t,
\qquad
S_I(t)=S_0-\gamma t.
$$

Find the Page time and the resulting entropy curve.

<details>
<summary><strong>Solution</strong></summary>

The physical entropy is

$$
S(R(t))=\min\{\gamma t,S_0-\gamma t\}.
$$

The Page time is where the two candidate entropies are equal:

$$
\gamma t_{\mathrm{Page}}=S_0-\gamma t_{\mathrm{Page}}.
$$

Therefore

$$
t_{\mathrm{Page}}=\frac{S_0}{2\gamma}.
$$

The entropy rises linearly until $t_{\mathrm{Page}}$ and then decreases linearly in this simplified model:

$$
S(R(t))=
\begin{cases}
\gamma t, & t\le t_{\mathrm{Page}},\\
S_0-\gamma t, & t\ge t_{\mathrm{Page}}.
\end{cases}
$$

</details>

### Exercise 2: Why including partners lowers the bulk entropy

In the Hawking pair picture, suppose a radiation mode $r$ is nearly maximally entangled with an interior partner $p$. Compare the entropy of $r$ with the entropy of $r\cup p$.

<details>
<summary><strong>Solution</strong></summary>

If $r$ and $p$ are approximately in a pure entangled state, then the reduced state of $r$ alone is mixed, so

$$
S(r)>0.
$$

But the joint state of the pair is approximately pure, so

$$
S(r\cup p)\approx0.
$$

In an island saddle, the island can contain many partner modes. Then the bulk entropy $S_{\mathrm{bulk}}(R\cup I)$ can be much smaller than $S_{\mathrm{bulk}}(R)$, even after paying the area cost at $\partial I$.

</details>

### Exercise 3: Extremizing the island boundary

Let $x$ be a simple coordinate describing the candidate island boundary. Suppose

$$
S_{\mathrm{gen}}(x)
=
\frac{A(x)}{4G_N}+S_{\mathrm{bulk}}(x).
$$

Write the QES condition.

<details>
<summary><strong>Solution</strong></summary>

The QES condition is stationarity of generalized entropy:

$$
0=\frac{dS_{\mathrm{gen}}}{dx}
=\frac{1}{4G_N}\frac{dA}{dx}
+\frac{dS_{\mathrm{bulk}}}{dx}.
$$

Equivalently,

$$
\frac{dA}{dx}
=-4G_N\frac{dS_{\mathrm{bulk}}}{dx}.
$$

The area gradient is balanced by the shape dependence of the bulk entropy.

</details>

### Exercise 4: Why the Page transition is a saddle transition

Suppose a gravitational entropy calculation has two candidate saddles with generalized entropies $S_1(t)$ and $S_2(t)$. Explain why the physical entropy can be nonanalytic at the time when $S_1(t)=S_2(t)$.

<details>
<summary><strong>Solution</strong></summary>

At leading semiclassical order, the entropy is the smaller generalized entropy:

$$
S(t)=\min\{S_1(t),S_2(t)\}.
$$

If $S_1$ dominates before the crossing and $S_2$ dominates after it, then the first derivative of $S(t)$ can jump at the crossing if

$$
\left.\frac{dS_1}{dt}\right|_{t=t_*}
\ne
\left.\frac{dS_2}{dt}\right|_{t=t_*}.
$$

This is a leading-order phase transition between entropy saddles. At finite $G_N$ or finite $N$, sharp transitions are often smoothed.

</details>

### Exercise 5: No-cloning and reconstruction

Why does the statement “an island is reconstructible from the radiation” not imply that the same interior degree of freedom has been cloned?

<details>
<summary><strong>Solution</strong></summary>

Entanglement-wedge reconstruction is a statement about logical operators in a code subspace. The same logical bulk operator can have different boundary reconstructions on different regions, but these reconstructions are not independent copies acting on independent tensor factors. They are equivalent representations on the code subspace.

This is analogous to quantum error correction: a logical qubit can be recoverable from more than one subset of physical qubits without violating no-cloning. The reconstructions agree where the code description is valid.

</details>

## Further reading

- D. N. Page, [Information in Black Hole Radiation](https://arxiv.org/abs/hep-th/9306083).
- G. Penington, [Entanglement Wedge Reconstruction and the Information Paradox](https://arxiv.org/abs/1905.08255).
- A. Almheiri, N. Engelhardt, D. Marolf, and H. Maxfield, [The entropy of bulk quantum fields and the entanglement wedge of an evaporating black hole](https://arxiv.org/abs/1905.08762).
- A. Almheiri, R. Mahajan, J. Maldacena, and Y. Zhao, [The Page curve of Hawking radiation from semiclassical geometry](https://arxiv.org/abs/1908.10996).
- A. Almheiri, T. Hartman, J. Maldacena, E. Shaghoulian, and A. Tajdini, [Replica Wormholes and the Entropy of Hawking Radiation](https://arxiv.org/abs/1911.12333).
- A. Almheiri, T. Hartman, J. Maldacena, E. Shaghoulian, and A. Tajdini, [The entropy of Hawking radiation](https://arxiv.org/abs/2006.06872).
