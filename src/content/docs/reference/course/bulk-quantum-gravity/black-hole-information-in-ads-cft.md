---
title: "Black-Hole Information in AdS/CFT"
description: "How AdS/CFT reframes the black-hole information problem, from unitary boundary evolution to Page curves, islands, interiors, and finite-N effects."
sidebar:
  order: 50
---

Black holes are where the slogan “AdS/CFT is a nonperturbative definition of quantum gravity” becomes most concrete. In semiclassical gravity, a black hole seems to absorb information and later emit nearly thermal Hawking radiation. In an ordinary non-gravitational quantum system, that cannot be the full story: time evolution by a Hamiltonian is unitary, and fine-grained information is not erased.

AdS/CFT puts these two statements in one framework. A black hole in asymptotically AdS spacetime is described by states and operators in an ordinary boundary quantum theory. At finite $N$, the boundary theory evolves unitarily. Therefore the exact bulk quantum gravity dual must also be unitary. The hard question is not whether the exact theory is unitary; it is how unitary information recovery is represented in the semiclassical bulk variables that appear to lose information.

This page is a conceptual bridge. It does not solve all mysteries of black-hole interiors. It explains what AdS/CFT makes sharp, what semiclassical gravity gets wrong, and how modern ideas such as entanglement wedges, quantum extremal surfaces, and islands fit into the logic.

<figure class="doc-figure" style="--figure-width: 56rem;">

![A schematic map from exact boundary unitarity to semiclassical black-hole physics, finite-N corrections, and quantum extremal surfaces.](/figures/course/black-hole-information-ads-cft.svg)

<figcaption>

Black-hole information in AdS/CFT. The exact CFT gives unitary time evolution. The semiclassical black-hole description is a powerful large-$N$ approximation, but the information paradox arises when one treats that approximation as exact.

</figcaption>
</figure>

## Why this matters

A classical AdS black hole already taught us how geometry encodes thermodynamics:

$$
S_{\rm BH} = \frac{\mathrm{Area}(\mathcal H)}{4G_N},
\qquad
T_{\rm CFT}=T_{\rm Hawking}.
$$

But black-hole thermodynamics is only the first layer. The deeper question is whether the black hole has a microscopic Hilbert-space description with approximately $e^{S_{\rm BH}}$ states. AdS/CFT says yes: black-hole states are states of the boundary CFT in an energy range where the density of states is large enough to admit a gravitational black-hole saddle.

This changes the status of the information problem. In semiclassical gravity, one tries to infer the final quantum state from a low-energy bulk calculation and finds a paradox. In AdS/CFT, the exact state is defined by the boundary CFT. The paradox becomes a diagnostic of which bulk approximation has been pushed too far.

The lesson is not “Hawking radiation is not thermal” in a naive sense. At large $N$, over many timescales, black holes are extremely well described by thermal coarse-grained physics. The lesson is subtler:

$$
\text{thermal at leading semiclassical order}
\neq
\text{exactly thermal in the fine-grained theory}.
$$

The difference is invisible in many classical calculations but essential for unitarity.

## Which black hole are we talking about?

There are several related setups. Mixing them is a reliable way to get confused.

### Large AdS black holes with reflecting boundary conditions

In global AdS with the standard reflecting boundary, Hawking radiation does not escape to infinity. A large black hole can be in thermal equilibrium with its radiation. The dual description is a thermal state of the CFT on $S^{d-1}$:

$$
\rho_\beta = \frac{e^{-\beta H_{\rm CFT}}}{Z(\beta)}.
$$

This is the natural setting for equilibrium thermodynamics, quasinormal modes, and thermal correlators.

### Eternal two-sided AdS black holes

The maximally extended eternal AdS black hole has two asymptotic boundaries. Its clean CFT dual is not one CFT but two non-interacting copies prepared in the thermofield-double state

$$
|{\rm TFD}\rangle
=
\frac{1}{\sqrt{Z(\beta)}}
\sum_n e^{-\beta E_n/2}
|n\rangle_L |n\rangle_R .
$$

The two CFTs do not exchange energy. Their entanglement is what prepares the connected two-sided geometry. The wormhole is not a traversable shortcut in the standard setup; it is a geometric representation of entanglement and thermal correlations.

### One-sided black holes from collapse

A one-sided AdS black hole can form from collapse in a single CFT state. The boundary theory has a pure state $|\Psi\rangle$ evolving by

$$
|\Psi(t)\rangle = e^{-iH_{\rm CFT}t}|\Psi(0)\rangle .
$$

At sufficiently high energy and for coarse observables, this state can behave thermally. But the exact state remains pure.

### Evaporating AdS black holes

With reflecting AdS boundary conditions, a black hole does not evaporate away in the same way as an asymptotically flat black hole. To study evaporation, one often couples the boundary CFT to an auxiliary non-gravitating bath or imposes absorbing boundary conditions. Radiation can then leave the AdS region, and one can ask for the fine-grained entropy of the collected radiation.

This is the setting where Page curves, quantum extremal surfaces, and islands are usually discussed.

## The semiclassical paradox

Hawking's calculation treats quantum fields on a fixed black-hole geometry. Near the horizon, the state locally resembles vacuum, but modes separate into outgoing radiation and partners that fall behind the horizon. A simplified pair-production cartoon is

$$
|0\rangle_{\rm near\ horizon}
\sim
\sum_n e^{-\beta E_n/2}
|n\rangle_{\rm outside}|n\rangle_{\rm inside}.
$$

Each outgoing Hawking quantum is entangled with an interior partner. If the black hole completely evaporates and the interior disappears, the outside radiation seems to be left in a mixed state. That would mean that pure states evolve into mixed states, violating ordinary unitary time evolution.

The tension can be phrased as a clash among three principles:

1. **Semiclassical exterior physics:** outside the horizon, low-energy effective field theory works.
2. **Smooth horizon:** an infalling observer sees no violent structure at the horizon of a large black hole.
3. **Unitarity:** the full quantum theory maps pure states to pure states.

AdS/CFT strongly supports the third principle. The challenge is then to understand how the first two principles are modified or reinterpreted.

## What AdS/CFT immediately implies

For a CFT on a compact spatial manifold such as $S^{d-1}$, the Hamiltonian has a discrete spectrum. The exact thermal two-point function has the spectral representation

$$
G_\beta(t)
=
\frac{1}{Z(\beta)}
\sum_{m,n}
 e^{-\beta E_m}
 e^{-i(E_n-E_m)t}
 |\langle m|\mathcal O|n\rangle|^2 .
$$

A classical black-hole calculation often predicts exponential decay of perturbations through quasinormal modes. That is a correct large-$N$ coarse-grained statement. But the exact finite-$N$ spectral sum cannot decay monotonically to zero forever in a finite energy window. It has late-time discreteness effects, small fluctuations, and eventually recurrences.

So the exact CFT already tells us that the classical black-hole saddle misses effects of order roughly

$$
e^{-S_{\rm BH}}
$$

or smaller. These effects are nonperturbative from the viewpoint of the leading semiclassical expansion. They are tiny, but tiny is not the same as absent. The information problem is precisely about fine-grained effects.

## Coarse-grained entropy versus fine-grained entropy

The Bekenstein–Hawking entropy is naturally interpreted as a coarse-grained thermodynamic entropy. In a microcanonical band of the CFT,

$$
S(E) \sim \log \rho(E),
$$

where $\rho(E)$ is the density of CFT states near energy $E$. The bulk saddle represents the collective thermodynamics of many microstates.

A pure black-hole microstate has zero total von Neumann entropy if the entire closed system is included. But coarse observables can behave as though the state were thermal. This is the same basic logic as ordinary statistical mechanics, with an important gravitational twist: the semiclassical black-hole geometry is itself a coarse-grained description.

Thus one should distinguish:

$$
S_{\rm BH}
\quad \text{counts microstates or gives thermodynamic entropy},
$$

from

$$
S_{\rm fine}(\rho_A)
= -\mathrm{Tr}\,\rho_A\log\rho_A,
$$

which is the fine-grained entropy of a chosen subsystem.

The information problem concerns fine-grained entropy. The area law alone is not enough; one must know which subsystem is being considered and which degrees of freedom are included.

## Page curve in one paragraph

For an evaporating black hole initially formed from a pure state, unitarity suggests that the fine-grained entropy of the radiation should first increase and then decrease back to zero. This is the Page curve.

At early times, newly emitted Hawking quanta are entangled mostly with the remaining black hole, so

$$
S_{\rm rad}(t) \;\text{increases}.
$$

After the Page time, the remaining black hole has fewer available microstates than the radiation. If the full evolution is unitary, additional radiation must be correlated with earlier radiation, and the fine-grained radiation entropy decreases.

A purely semiclassical no-island calculation instead gives entropy that keeps growing. That is the Page-curve version of the information paradox.

## Islands and the modern semiclassical answer

The quantum extremal surface prescription says that the entropy of a boundary region or radiation system is computed by extremizing the generalized entropy

$$
S_{\rm gen}(X)
=
\frac{\mathrm{Area}(X)}{4G_N}
+ S_{\rm bulk}(\Sigma_X),
$$

where $X$ is a codimension-two surface and $\Sigma_X$ is the bulk region bounded by $X$ and the boundary subsystem. In evaporating setups, the entropy of the radiation can receive contributions from islands $I$ inside the black-hole region:

$$
S(R)
=
\min_I\;\mathrm{ext}_I
\left[
\frac{\mathrm{Area}(\partial I)}{4G_N}
+ S_{\rm bulk}(R\cup I)
\right].
$$

At early times, the dominant saddle often has no island. At late times, an island saddle dominates. The island includes degrees of freedom that semiclassical reasoning would have assigned to the black-hole interior. The radiation entropy then follows a Page curve.

This is a remarkable result because it uses semiclassical gravity plus the correct entropy prescription to reproduce a unitary-looking answer. But it should not be misread. The island formula does not mean that the interior is literally an ordinary subregion of the external radiation in the semiclassical geometry. It means that the correct fine-grained entropy functional knows about gravitational constraints and entanglement-wedge reconstruction.

## Entanglement wedges and interior reconstruction

In holography, a boundary region $A$ is associated with an entanglement wedge $\mathcal W_E[A]$. Operators in that wedge can be reconstructed from the boundary region $A$, at least within a code subspace.

For black holes, this idea becomes especially important. Before the Page time, interior degrees of freedom may be reconstructible from the black-hole side rather than the radiation. After the Page time in an evaporating setup, part of the interior can lie in the entanglement wedge of the radiation.

This is not ordinary local quantum field theory on a fixed background. It is quantum error correction with gravitational constraints. The same bulk operator can have multiple boundary reconstructions in different regions, and the validity of those reconstructions is limited to an appropriate code subspace.

A useful slogan is:

$$
\text{the black-hole interior is not encoded locally in the boundary in the way a lattice site is encoded in a spin chain.}
$$

It is encoded redundantly, relationally, and state-dependently in the sense required by gravitational dressing and quantum error correction.

## Eternal black holes and the thermofield double

The thermofield double state

$$
|{\rm TFD}\rangle
=
\frac{1}{\sqrt{Z(\beta)}}
\sum_n e^{-\beta E_n/2}|n\rangle_L|n\rangle_R
$$

is dual, at large $N$ and strong coupling, to the eternal two-sided AdS black hole.

Tracing out the right CFT gives the thermal density matrix of the left CFT:

$$
\rho_L
=\mathrm{Tr}_R |{\rm TFD}\rangle\langle {\rm TFD}|
=\frac{e^{-\beta H_L}}{Z(\beta)}.
$$

The entanglement entropy between the two CFTs matches the horizon entropy at leading order:

$$
S(\rho_L)\approx \frac{\mathrm{Area}(\mathcal H)}{4G_N}.
$$

This example is conceptually clean because the total state is pure, while each side separately looks thermal. The bridge between the two exteriors is a geometric representation of entanglement, not a violation of boundary causality.

## One-sided black holes and typical states

A one-sided black hole formed from collapse is dual to a state in a single CFT. At large $N$, many high-energy states have approximately the same exterior geometry. This is the gravitational version of eigenstate thermalization: simple operators cannot easily distinguish individual microstates.

A CFT microstate $|E,a\rangle$ might satisfy, for simple operators,

$$
\langle E,a|\mathcal O_1\cdots \mathcal O_k|E,a\rangle
\approx
\mathrm{Tr}(\rho_\beta\mathcal O_1\cdots\mathcal O_k),
$$

when the energy corresponds to temperature $\beta^{-1}$ and the probes are not too complicated. But the approximation is not exact. Distinguishing microstates requires sufficiently fine probes, long times, or observables outside the classical EFT regime.

This is another way of seeing why classical geometry is a coarse-grained description.

## Nonperturbative effects and long times

A classical black hole absorbs perturbations. In the dual CFT, this is thermalization. Retarded correlators have poles at quasinormal frequencies, and simple perturbations decay.

But exact finite-$N$ CFT dynamics contains more structure:

- the spectrum on a compact spatial manifold is discrete;
- thermal correlators have late-time fluctuations;
- exact evolution preserves purity;
- recurrences may occur on enormous timescales;
- corrections nonperturbative in $1/N$ can matter for fine-grained questions.

The ordering of limits matters. If one first takes $N\to\infty$ and then takes late times, one obtains the classical black-hole answer. If one asks a finite-$N$ question about arbitrarily late times, the answer can differ qualitatively.

Symbolically,

$$
\lim_{t\to\infty}\lim_{N\to\infty} G(t)
\neq
\lim_{N\to\infty}\lim_{t\to\infty} G(t).
$$

This noncommutativity of limits is one reason black-hole information is subtle.

## What AdS/CFT solves, and what remains hard

AdS/CFT gives a precise nonperturbative definition of many quantum-gravity systems in asymptotically AdS spacetime. In that sense it resolves the sharpest version of the information-loss question: the exact theory is unitary because the boundary CFT is unitary.

But several hard questions remain.

First, one wants to understand how semiclassical bulk locality emerges and breaks down in enough detail to see information recovery directly in bulk language.

Second, one wants a microscopic description of black-hole interiors that works broadly, not just in special code subspaces.

Third, one wants to understand singularities. CFT evolution continues, but translating that statement into a smooth bulk story near a spacelike singularity is difficult.

Fourth, one wants to understand whether similar nonperturbative definitions exist for cosmological spacetimes, especially de Sitter-like universes.

So AdS/CFT does not make black holes boring. It gives us a framework in which the questions are sharper.

## Dictionary checkpoint

The information-theoretic dictionary is:

| Boundary statement | Bulk interpretation |
|---|---|
| unitary CFT time evolution | no fundamental information loss in AdS quantum gravity |
| high-energy thermal CFT states | AdS black-hole saddles |
| density of states $\rho(E)$ | Bekenstein–Hawking entropy |
| thermofield double state | eternal two-sided AdS black hole |
| finite-$N$ spectral discreteness | nonperturbative corrections to classical black-hole decay |
| entanglement wedge of radiation | island-inclusive reconstruction after Page time |
| code subspace | range of validity of a semiclassical bulk reconstruction |

The main warning is that the classical black-hole geometry is not the exact quantum state. It is an effective description of a family of states or a saddle approximation to a path integral.

## Common confusions

### “AdS/CFT says Hawking’s calculation was simply wrong.”

Hawking’s calculation is correct within its semiclassical assumptions. The problem is that those assumptions do not include the fine-grained gravitational entropy prescription and nonperturbative quantum-gravity effects needed for unitarity.

### “The CFT has no gravity, so the bulk black hole is fake.”

The CFT has no dynamical gravity on its own spacetime, but it can exactly encode a gravitational bulk. The point of the duality is that the same quantum system has two different descriptions.

### “The island is a literal chunk of space inside the radiation system.”

No. The island is a region included in the gravitational entropy calculation for the radiation. Its appearance reflects the structure of gravitational entanglement and entanglement-wedge reconstruction, not ordinary embedding of one spatial region into another.

### “The thermofield double means two CFTs are connected by a traversable wormhole.”

The standard eternal AdS black hole is not traversable. Traversability requires additional couplings or boundary conditions that violate the relevant averaged null energy condition in a controlled way.

### “Finite $N$ corrections are small, so they cannot matter.”

They are small for many coarse observables and finite times. But information recovery is a fine-grained, long-time question. Tiny corrections accumulated over long times or selected by subtle entropy extremization can change the qualitative answer.

## Exercises

### Exercise 1: Thermal density matrix from the thermofield double

Show that tracing over the right CFT in the thermofield-double state gives a thermal density matrix on the left.

<details>
<summary><strong>Solution</strong></summary>

Start with

$$
|{\rm TFD}\rangle
=
\frac{1}{\sqrt{Z}}
\sum_n e^{-\beta E_n/2}|n\rangle_L|n\rangle_R.
$$

Then

$$
|{\rm TFD}\rangle\langle {\rm TFD}|
=
\frac{1}{Z}
\sum_{m,n}e^{-\beta(E_m+E_n)/2}
|m\rangle_L|m\rangle_R
{}_L\langle n|{}_R\langle n|.
$$

Tracing over the right Hilbert space gives

$$
\rho_L
=\frac{1}{Z}\sum_{m,n}e^{-\beta(E_m+E_n)/2}|m\rangle_L{}_L\langle n|\;{}_R\langle n|m\rangle_R.
$$

Using ${}_R\langle n|m\rangle_R=\delta_{mn}$,

$$
\rho_L
=\frac{1}{Z}\sum_n e^{-\beta E_n}|n\rangle_L{}_L\langle n|
=\frac{e^{-\beta H_L}}{Z}.
$$

</details>

### Exercise 2: Why exact finite-$N$ correlators do not simply decay forever

Consider a thermal correlator on $S^{d-1}$ with spectral representation

$$
G_\beta(t)
=
\frac{1}{Z}\sum_{m,n} e^{-\beta E_m}e^{-i(E_n-E_m)t}|\mathcal O_{mn}|^2.
$$

Why is indefinite monotonic exponential decay not the generic exact finite-$N$ behavior?

<details>
<summary><strong>Solution</strong></summary>

At finite $N$ on compact space, the CFT spectrum is discrete. The correlator is a weighted sum of phases $e^{-i(E_n-E_m)t}$. Such a sum can approximate decay for an intermediate range of times because many phases dephase. But it is not a smooth function with an exactly continuous spectrum unless one has taken an infinite-volume or strict large-$N$ limit. At very late times, discreteness produces fluctuations and possible recurrences. Classical black-hole quasinormal decay is therefore a coarse-grained large-$N$ approximation, not the exact finite-$N$ answer.

</details>

### Exercise 3: Early and late island saddles

Suppose a radiation entropy is approximated by

$$
S(R)=\min\left(S_{\rm no\ island}(R),S_{\rm island}(R)\right),
$$

where $S_{\rm no\ island}(R)$ grows approximately linearly with time and $S_{\rm island}(R)$ is approximately of order the decreasing black-hole entropy. Explain qualitatively how a Page curve arises.

<details>
<summary><strong>Solution</strong></summary>

At early times, $S_{\rm no\ island}$ is small because little radiation has been emitted, while the island saddle carries a large area cost. The no-island saddle dominates, so the radiation entropy grows. At late times, the no-island result keeps growing, but the island saddle is controlled by the remaining black-hole entropy and becomes smaller. The minimization switches to the island saddle near the Page time. The entropy then decreases as the black hole loses entropy, giving the Page-curve shape expected from unitary evaporation.

</details>

## Further reading

- J. Maldacena, [Eternal Black Holes in Anti-de-Sitter](https://arxiv.org/abs/hep-th/0106112).
- D. Harlow, [Jerusalem Lectures on Black Holes and Quantum Information](https://arxiv.org/abs/1409.1231).
- G. Penington, [Entanglement Wedge Reconstruction and the Information Paradox](https://arxiv.org/abs/1905.08255).
- A. Almheiri, N. Engelhardt, D. Marolf, and H. Maxfield, [The Entropy of Bulk Quantum Fields and the Entanglement Wedge of an Evaporating Black Hole](https://arxiv.org/abs/1905.08762).
- A. Almheiri, T. Hartman, J. Maldacena, E. Shaghoulian, and A. Tajdini, [The Entropy of Hawking Radiation](https://arxiv.org/abs/2006.06872).
- T. Faulkner, A. Lewkowycz, and J. Maldacena, [Quantum Corrections to Holographic Entanglement Entropy](https://arxiv.org/abs/1307.2892).
