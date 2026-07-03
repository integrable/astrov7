---
title: "Matching S-Matrix Elements"
description: "How to determine EFT Wilson coefficients by equating low-energy on-shell amplitudes in the full theory and the EFT."
sidebar:
  label: "Matching S-Matrix Elements"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, LSZ, renormalization, RG, and EFT chapters; Weinberg Vol. I, scattering and renormalization, and Vol. II, RG methods; Schwartz 2014, S-matrix, renormalized perturbation theory, nonrenormalizable theories, and EFT chapters; Burgess 2020, matching and power counting."
topics:
  - S-matrix matching
  - on-shell amplitudes
  - Wilson coefficients
  - LSZ reduction
  - redundant operators
  - EFT matching
canonicalTopics:
  - matching-s-matrix-elements
  - on-shell-eft-matching
  - wilson-coefficient-extraction
researchStatus:
  established:
    - "Matching on-shell S-matrix elements is a standard EFT method for determining Wilson coefficients that affect physical scattering amplitudes."
  active:
    - "Modern on-shell matching, helicity-basis matching, amplitude bases, infrared subtractions, and automated multi-loop EFT matching remain active technical and conceptual frontiers."
---

## Summary

**S-matrix matching** determines EFT Wilson coefficients by requiring that the full theory and the EFT give the same low-energy on-shell scattering amplitudes. It is often the cleanest matching method when the observable of interest is a scattering amplitude, decay amplitude, or matrix element between asymptotic states.

The basic condition is

$$
\mathcal A_{\text{full}}(1,\ldots,n)
=
\mathcal A_{\text{EFT}}(1,\ldots,n;C_i(\mu),\mu)
+
O\left(\frac{Q^{N+1}}{M^{N+1}}\right),
\qquad Q\ll M,
$$

where all external particles are light and on shell. The equality is imposed order by order in the EFT expansion, in perturbation theory, and in a specified renormalization scheme.

The method has a practical virtue:

$$
\text{on-shell amplitudes automatically ignore many redundant operator directions.}
$$

Operators proportional to the classical equations of motion, total derivatives, and local field redefinitions can change off-shell Green functions but do not change ordinary on-shell $S$-matrix elements. This makes amplitude matching efficient. It also means that amplitude matching determines only the combinations of Wilson coefficients visible in the chosen on-shell processes.

The guiding slogan is:

$$
\text{same low-energy particles, same low-energy amplitudes, different short-distance bookkeeping.}
$$

## Prerequisites

You should know [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Tree-Level Matching](/renormalization-rg-eft/matching-running-decoupling/tree-level-matching/), [One-Loop Matching](/renormalization-rg-eft/matching-running-decoupling/one-loop-matching/), [Matching Correlation Functions](/renormalization-rg-eft/matching-running-decoupling/matching-correlation-functions/), and [Renormalized S-Matrix](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-s-matrix/).

You should also be comfortable with [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/), [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), and [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/).

## Core idea

A Wilson coefficient is fixed by comparing two descriptions in their common domain of validity. For S-matrix matching, the comparison object is an on-shell amplitude involving only light external states.

Choose a process,

$$
a_1+\cdots+a_r\longrightarrow a_{r+1}+\cdots+a_n,
$$

with all external momenta satisfying

$$
p_a^2=m_a^2,
\qquad
p_a^0>0,
\qquad
Q\sim |p_a|\ll M.
$$

Compute the full-theory amplitude, expand it for $Q/M\ll1$, compute the EFT amplitude from local operators, and equate the two:

$$
\mathcal M_{\text{full}}
=
\mathcal M_{\text{EFT}}
=
\mathcal M_{\text{light EFT loops}}
+
\sum_i C_i(\mu)\mathcal M_i^{\text{local}}
+\cdots.
$$

At tree level, the comparison often amounts to expanding a heavy propagator. At loop level, it amounts to subtracting the EFT long-distance amplitude from the full-theory amplitude and projecting the remaining local polynomial onto the operator basis.

The result is a set of Wilson coefficients or coefficient combinations. The EFT then predicts other amplitudes related by symmetry, crossing, unitarity, and the operator basis.

## Setup and conventions

This page uses the mostly-minus conventions of [Conventions and Notation](/renormalization-rg-eft/conventions/). For scattering amplitudes we use the convention

$$
S=\mathbf 1+iT,
\qquad
\langle f|iT|i\rangle
=
i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi},
$$

as in the perturbative scattering conventions.

The matching scales are:

| Symbol | Meaning |
|---|---|
| $M$ | heavy mass or threshold scale |
| $Q$ | typical light external momentum or mass |
| $\mu_M$ | matching scale, usually near $M$ |
| $\mu_L$ | low scale where matrix elements may be evaluated |
| $C_i(\mu)$ | Wilson coefficients in the EFT |
| $\mathcal M_i$ | amplitude generated by the operator $\mathcal O_i$ |

External light particles are placed on shell. For scalars,

$$
p^2=m^2.
$$

For fermions, external spinors obey

$$
(p\!\!\!/-m)u(p)=0,
\qquad
\bar u(p)(p\!\!\!/-m)=0,
$$

with analogous equations for antiparticles. For external gauge bosons, physical polarizations obey transversality conditions appropriate to the gauge and mass:

$$
p\cdot \varepsilon(p)=0
$$

for an external massless gauge boson in a physical polarization state.

## Why match S-matrix elements?

S-matrix matching is attractive because the $S$ matrix is physical. It does not care about many unphysical choices that complicate Green functions:

| Off-shell nuisance | What happens on shell |
|---|---|
| Field redefinitions | Leave the $S$ matrix invariant under standard assumptions. |
| EOM operators | Vanish or reduce to other operators between on-shell states. |
| Gauge-dependent Green functions | Physical amplitudes are gauge independent after all contributions are included. |
| External propagator normalization | LSZ extracts pole residues and physical external states. |
| Contact-term conventions | Only combinations that affect amplitudes matter. |

This does not mean on-shell matching is magic. It still requires a complete operator basis, consistent normalization, compatible infrared regulators, and enough independent processes to determine the desired coefficients. But it removes a great deal of coordinate clutter.

The cost is that amplitude matching sees only physical on-shell combinations. If two different operator bases give the same on-shell amplitudes, amplitude matching alone will not distinguish them. That is usually a feature, not a bug.

## LSZ and what is being matched

The $S$ matrix is obtained from time-ordered correlation functions by LSZ reduction. Schematically, for scalar external particles,

$$
\mathcal M
\sim
\left[\prod_{a=1}^n Z_a^{-1/2}\right]
\left[\prod_{a=1}^n(p_a^2-m_a^2)\right]
G_{\text{conn}}^{(n)}(p_1,\ldots,p_n)
\bigg|_{p_a^2\to m_a^2}.
$$

The details depend on conventions, spin, gauge fixing, and state normalization, but the lesson is stable:

$$
\text{amplitude matching}
=
\text{matching residues of poles, not arbitrary off-shell functions.}
$$

This is why field-redefinition effects often disappear. A local field redefinition can change the off-shell correlator $G^{(n)}$, but after amputation and on-shell limiting, the physical amplitude is unchanged.

However, the LSZ factors themselves must be handled consistently. If the full theory and EFT use different field normalizations, threshold wavefunction factors or residue conventions can enter the matching. In an on-shell scheme this is often hidden by choosing unit pole residues. In an MS-like scheme it may appear as finite external-leg or field-renormalization factors.

A careful matching statement therefore compares physical amplitudes, not merely amputated diagrams with whatever external-leg convention happened to appear first.

## The practical workflow

A reliable S-matrix matching calculation follows a disciplined sequence.

| Step | Task | Reason |
|---:|---|---|
| 1 | Choose light external states and kinematics. | The EFT contains only light asymptotic states. |
| 2 | Choose the perturbative and power-counting order. | Coefficients are meaningful only at a specified accuracy. |
| 3 | Compute the full-theory amplitude. | Include all diagrams at that order. |
| 4 | Expand for $Q\ll M$. | Heavy propagation becomes local. |
| 5 | Compute the EFT amplitude. | Include known lower-order coefficients and EFT loops. |
| 6 | Subtract common infrared pieces. | Wilson coefficients should contain short-distance information. |
| 7 | Project onto independent on-shell structures. | Solve for coefficient combinations. |
| 8 | Convert to the chosen operator basis. | Basis conventions determine the reported $C_i$. |
| 9 | Check symmetry, gauge independence, and scale dependence. | These catch missing terms. |

The projection step is important. An amplitude is not just a scalar number; it may have spinor, Lorentz, color, flavor, helicity, and crossing structures. Wilson coefficients multiply independent local structures. Matching equates the coefficients of those structures.

## Amplitude basis and operator basis

The EFT Lagrangian is written in an operator basis,

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\text{light}}
+
\sum_i C_i\mathcal O_i.
$$

On shell, each operator produces amplitudes. The map

$$
\mathcal O_i
\longrightarrow
\mathcal M_i^{\text{on shell}}
$$

can have a kernel. Operators in the kernel are redundant for the chosen on-shell processes. Examples include total derivatives, equation-of-motion operators, and operators that vanish by spinor-helicity identities, flavor symmetries, or kinematic restrictions.

Therefore one often works with an amplitude basis:

$$
\mathcal M_{\text{local}}
=
\sum_A a_A\,\mathcal B_A,
$$

where $\mathcal B_A$ are independent on-shell local amplitude structures. The coefficients $a_A$ are related to Wilson coefficients by a linear map:

$$
a_A = R_A{}^i C_i.
$$

If $R$ has a nontrivial kernel, the amplitude determines only combinations of $C_i$. To report Wilson coefficients in a Lagrangian basis, one must choose a representative by using equations of motion, integration by parts, symmetries, and field redefinitions.

This is not a defect of S-matrix matching. It is a reminder that the $S$ matrix measures physical directions in theory space.

## Tree-level example: a heavy scalar mediator

Consider a full theory with a light scalar $\phi$ and a heavy scalar $H$,

$$
\mathcal L_{\text{int}}=-\frac{g}{2}H\phi^2.
$$

The tree-level full-theory amplitude for $\phi\phi\to\phi\phi$ receives $s$, $t$, and $u$ channel heavy-exchange contributions:

$$
i\mathcal M_{\text{full}}
=
(-ig)^2
\left[
\frac{i}{s-M^2}
+\frac{i}{t-M^2}
+\frac{i}{u-M^2}
\right],
$$

suppressing the $i\epsilon$ prescription. For $|s|,|t|,|u|\ll M^2$,

$$
\mathcal M_{\text{full}}
=
g^2\left[
\frac{1}{M^2}+\frac{s}{M^4}+\cdots
+
\frac{1}{M^2}+\frac{t}{M^4}+\cdots
+
\frac{1}{M^2}+\frac{u}{M^4}+\cdots
\right],
$$

up to the sign convention inherited from the interaction and amplitude definition.

The EFT contains local interactions such as

$$
\Delta\mathcal L_{\text{EFT}}
=
\frac{c_0}{4!}\phi^4
+
\frac{c_2}{M^2}\phi^2\partial_\mu\phi\partial^\mu\phi
+\cdots.
$$

Matching the constant and momentum-dependent terms determines $c_0,c_2,\ldots$ in the chosen basis.

For equal-mass external scalars,

$$
s+t+u=4m^2.
$$

On shell, this relation can make some derivative operators indistinguishable from mass-suppressed non-derivative operators. A correlator matching calculation off shell may separate them; an amplitude matching calculation naturally fixes only the on-shell combination.

## Tree-level example: Fermi theory from W exchange

The classic particle-physics example is the low-energy weak interaction. At momentum transfer $q^2\ll M_W^2$, the $W$ propagator collapses into a local interaction. Schematically,

$$
\frac{-ig_{\mu\nu}}{q^2-M_W^2}
=
\frac{ig_{\mu\nu}}{M_W^2}
\left(1+\frac{q^2}{M_W^2}+\cdots\right).
$$

The leading EFT amplitude is reproduced by the four-fermion operator

$$
\mathcal L_{\text{Fermi}}
=
-\frac{G_F}{\sqrt2}
(\bar\psi_1\gamma^\mu(1-\gamma^5)\psi_2)
(\bar\psi_3\gamma_\mu(1-\gamma^5)\psi_4)
+\cdots.
$$

Matching fixes the relation, schematically,

$$
\frac{G_F}{\sqrt2}\sim \frac{g^2}{8M_W^2},
$$

with precise factors depending on the electroweak normalization conventions. Higher powers of $q^2/M_W^2$ correspond to derivative corrections. Loop effects and electroweak renormalization produce threshold corrections to the simple tree-level relation.

This example shows why matching is not merely dimensional analysis. Dimensional analysis says the coefficient scales as $1/M_W^2$. Matching determines the coefficient, spin structure, flavor structure, and normalization.

## Loop-level amplitude matching

At loop level the amplitude matching condition is

$$
\mathcal M_{\text{full}}^{(1)}
=
\mathcal M_{\text{EFT}}^{(1)}.
$$

More explicitly,

$$
\mathcal M_{\text{full}}^{(1)}
-
\mathcal M_{\text{EFT, known}}^{(1)}
=
\sum_i C_i^{(1)}(\mu)\mathcal M_i^{\text{tree}}.
$$

Here $\mathcal M_{\text{EFT, known}}^{(1)}$ is computed using Wilson coefficients already fixed at lower order. The difference should be local in the external momenta:

$$
\mathcal M_{\text{full}}^{(1)}
-
\mathcal M_{\text{EFT, known}}^{(1)}
=
a_0+a_2\frac{Q^2}{M^2}+a_4\frac{Q^4}{M^4}+\cdots.
$$

Nonanalytic dependence on light scales, such as

$$
\log(-s/\mu^2),
\qquad
\sqrt{1-4m^2/s},
\qquad
\frac{1}{\epsilon_{\text{IR}}},
$$

must cancel between the full and EFT sides if the EFT contains the correct light degrees of freedom. If such terms remain in the Wilson coefficient, something has been double counted or omitted.

Dimensional regularization often makes this subtraction elegant: many EFT loop integrals become scaleless and vanish when all light masses and external momenta are set to zero. In that setup, the full-theory amplitude expanded in small external quantities directly gives the matching coefficient. But one must remember what happened: the vanishing scaleless EFT integral contains both UV and IR poles that cancel. The matching coefficient is still a UV short-distance object; the calculation has hidden the IR bookkeeping rather than eliminated it.

## Infrared safety and massless particles

Massless particles make amplitude matching delicate. Individual amplitudes may have soft or collinear infrared divergences. Matching Wilson coefficients remains possible, but the full and EFT calculations must share the same infrared regulator and external-state definition.

Common choices include:

| IR treatment | Use |
|---|---|
| Small fictitious masses | Simple for abelian examples, but may obscure gauge symmetry. |
| Dimensional regularization | Standard in gauge-theory matching, with UV and IR poles distinguished conceptually. |
| Off-shell Euclidean kinematics | Useful for Green-function matching, less directly an $S$-matrix method. |
| Inclusive observables | Required for physical rates with real soft radiation. |
| Factorized amplitudes | Separates hard matching coefficients from soft and collinear functions. |

The hard matching coefficient should not depend on the arbitrary infrared regulator after subtracting the EFT contribution. It may depend on $\mu$, the renormalization scheme, and the matching scale.

A sharp way to say the rule is:

$$
\text{Wilson coefficients are hard functions, not full cross sections.}
$$

Soft radiation, collinear physics, bound-state dynamics, and hadronic matrix elements belong in EFT matrix elements or factorized low-energy functions, not inside the short-distance matching coefficient.

## Gauge invariance and Ward identities

On-shell matching is often the safest way to match gauge theories because physical amplitudes satisfy Ward identities. For external photons or gluons, replacing a polarization vector by its momentum should give zero for a gauge-invariant physical amplitude:

$$
\varepsilon_\mu(p)\longrightarrow p_\mu
\quad\Longrightarrow\quad
\mathcal M=0,
$$

up to the standard qualifications about gauge fixing, external states, ghosts, and color ordering.

This provides a powerful check. If the matched EFT amplitude violates the Ward identity, possible causes include:

- missing operators required by gauge invariance;
- inconsistent use of equations of motion;
- omitted ghost or Goldstone contributions in a gauge-fixed calculation;
- incorrect external-state normalization;
- projecting onto a gauge-noninvariant operator basis;
- dropping terms that vanish only after summing diagrams.

The EFT should be organized in gauge-invariant operators whenever possible. Gauge-variant intermediate expressions are tolerable only if the final matched amplitude is gauge independent and gauge invariant in the appropriate sense.

## Matching decays and unstable particles

S-matrix matching also applies to decay amplitudes. If a heavy virtual particle mediates a low-energy decay, the EFT local operator is fixed by matching the decay amplitude between light external states.

However, one must be careful with unstable particles. A truly unstable particle is not an asymptotic state. Matching calculations involving unstable heavy particles usually treat them as internal fields to be integrated out, not as external states. If the unstable particle is near resonance, the ordinary local EFT expansion may fail because the denominator

$$
q^2-M^2+iM\Gamma
$$

is not expandable in $q^2/M^2$ near $q^2\simeq M^2$.

The local EFT expansion requires being far below the heavy threshold:

$$
|q^2|\ll M^2.
$$

Near threshold or near resonance one may need a different EFT with the near-on-shell heavy mode retained explicitly, a nonrelativistic EFT, or a width-resummed treatment.

## Spin, helicity, and polarization structures

For particles with spin, matching means equating independent spin and helicity structures. A four-fermion amplitude, for example, may contain several possible bilinears:

$$
(\bar\psi\psi)(\bar\psi\psi),
\qquad
(\bar\psi\gamma^\mu\psi)(\bar\psi\gamma_\mu\psi),
\qquad
(\bar\psi\sigma^{\mu\nu}\psi)(\bar\psi\sigma_{\mu\nu}\psi),
\qquad
\cdots.
$$

On shell these structures may be related by Fierz identities, chirality constraints, equations of motion, or dimension-specific identities. In dimensional regularization, additional care is needed because identities valid strictly in four dimensions may generate evanescent operators in $d=4-2\epsilon$.

For gauge bosons, helicity amplitudes are often an efficient basis. Local operators map to polynomials in spinor-helicity variables. Matching then becomes the problem of expanding the full amplitude at low energy and reading off the coefficients of local helicity structures.

This is one reason modern amplitude methods are increasingly useful in EFT: they match directly onto the physical on-shell data.

## Crossing and process choice

One process can determine a coefficient; crossing-related processes should then agree. For example, if an operator contributes to

$$
1+2\to3+4,
$$

the same local interaction also determines crossed amplitudes such as

$$
1+\bar3\to \bar2+4,
$$

with the usual analytic continuation of momenta and quantum numbers.

Crossing is a useful check, but it does not eliminate the need to match enough independent structures. A single process at a special kinematic point may accidentally miss an operator. Safer choices include:

- matching several helicity configurations;
- matching several flavor assignments;
- using generic Mandelstam variables before imposing special limits;
- checking crossed channels;
- comparing with a correlator or background-field computation when possible.

A matching calculation should avoid kinematics that accidentally kills the operator being determined.

## S-matrix matching versus correlation-function matching

Both methods are valid. They answer slightly different bookkeeping questions.

| Feature | S-matrix matching | Correlation-function matching |
|---|---|---|
| External states | On-shell light particles | Fields, operators, or sources |
| Redundant operators | Often invisible | Visible unless quotiented out |
| Gauge dependence | Reduced for physical amplitudes | Must be controlled off shell |
| Contact terms | Enter only through amplitudes | Explicit and important |
| Best use | Scattering, decays, helicity amplitudes | Background actions, response functions, operator mixing |
| Main hazard | Missing invisible operator directions | Mistaking off-shell coordinates for observables |

A mature EFT calculation often uses both. On-shell amplitudes determine physical combinations efficiently; correlators and background fields organize symmetry, operator mixing, and source dependence.

## What S-matrix matching cannot do

S-matrix matching is powerful, but it does not determine everything in an arbitrary Lagrangian basis.

It cannot uniquely determine:

- coefficients of operators that vanish by equations of motion;
- total derivatives;
- field-redefinition directions;
- contact terms that never affect the chosen external states;
- source-dependent terms if no source is probed;
- off-shell Green-function conventions;
- gauge-fixing artifacts;
- evanescent operator effects unless the calculation is formulated in a $d$-dimensional basis.

This is not a limitation on physics. It is a limitation on using physical amplitudes to reconstruct unphysical coordinates. If the desired final output is a standard operator basis, additional basis choices must be supplied.

## Common pitfalls

**Matching diagrams instead of amplitudes.** Individual diagrams can be gauge dependent, field-redefinition dependent, or IR divergent. Match the complete amplitude at the chosen order.

**Forgetting LSZ factors.** Amputated Green functions are not automatically physical amplitudes unless the external-state and residue conventions are accounted for.

**Matching at a special kinematic point.** Special kinematics can hide operators. Match generic enough kinematics to separate independent structures.

**Putting soft physics into Wilson coefficients.** Soft and collinear effects must cancel against the EFT side or be assigned to low-energy matrix elements and factorized functions.

**Using equations of motion inconsistently.** EOM reductions are valid for on-shell amplitudes, but changing basis also changes coefficient definitions. Do not compare coefficients across bases without the map.

**Ignoring evanescent operators.** In dimensional regularization, operators that vanish in four dimensions can affect finite matching at loop level.

**Confusing resonance physics with local matching.** If the heavy particle can nearly go on shell, the local expansion in $Q/M$ is not the right description.

**Assuming one process fixes the whole EFT.** It fixes only the operator combinations visible in that process.

## Relations to other pages

This page is the on-shell companion to [Matching Correlation Functions](/renormalization-rg-eft/matching-running-decoupling/matching-correlation-functions/). Use correlation matching for source functionals, off-shell Green functions, background fields, and contact terms. Use $S$-matrix matching when the target is physical scattering or decay amplitudes.

It also connects to [Renormalized S-Matrix](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-s-matrix/), [Tree-Level Matching](/renormalization-rg-eft/matching-running-decoupling/tree-level-matching/), [One-Loop Matching](/renormalization-rg-eft/matching-running-decoupling/one-loop-matching/), [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/), [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/), and [Operator Basis Choice](/renormalization-rg-eft/matching-running-decoupling/operator-basis-choice/).

Later model pages will show this method in explicit examples: heavy scalar exchange, Fermi theory from $W$ exchange, Euler–Heisenberg matching, and nonrelativistic matching.

## Research status

The basic principle of S-matrix matching is settled. It is one of the central tools of modern EFT.

Active work focuses on scaling the method: multi-loop matching, automated helicity-basis matching, gauge-invariant amplitude bases, EFTs with massless particles and factorization, evanescent-operator bookkeeping, and matching calculations involving many operators and many thresholds.

A particularly lively interface is between EFT and modern amplitudes. On-shell methods can expose the physical content of operator bases more directly than Lagrangian enumeration, but translating between amplitude bases and traditional Wilson-coefficient bases remains an important practical skill.

## Exercises

### Exercise 1: EOM operator and on-shell amplitudes

Let a scalar EFT contain an operator

$$
\mathcal O_{\text{EOM}}=F(\phi)(\Box+m^2)\phi.
$$

Explain why this operator does not affect ordinary on-shell amplitudes at first order in its coefficient, up to contact and field-redefinition subtleties.

<details><summary><strong>Solution</strong></summary>

For an external on-shell scalar, LSZ amputation applies a factor of $p^2-m^2$ and then takes $p^2\to m^2$ in the mostly-minus convention. An insertion proportional to the classical equation of motion can be removed by a local field redefinition of the form

$$
\phi\to \phi+aF(\phi).
$$

The equivalence theorem states that local invertible field redefinitions do not change the ordinary $S$ matrix under the usual assumptions. Therefore $\mathcal O_{\text{EOM}}$ can change off-shell Green functions and contact terms, but it does not create an independent on-shell amplitude structure at first order in the coefficient.

</details>

### Exercise 2: Heavy scalar amplitude expansion

For identical light scalars of mass $m$, show that the low-energy expansion of heavy scalar exchange depends on $s+t+u=4m^2$ on shell. What does this imply for derivative operator matching?

<details><summary><strong>Solution</strong></summary>

For a $2\to2$ process with identical external masses,

$$
s=(p_1+p_2)^2,
\qquad
t=(p_1-p_3)^2,
\qquad
u=(p_1-p_4)^2,
$$

and the on-shell relation is

$$
s+t+u=4m^2.
$$

The heavy-exchange amplitude expands as a polynomial in $s,t,u$ divided by powers of $M^2$. At first derivative order, a symmetric combination proportional to $s+t+u$ is just proportional to $m^2$ on shell. Therefore some derivative operators are indistinguishable from mass-suppressed non-derivative operators in on-shell matching. A basis choice or off-shell correlator matching is needed if one wants to assign the contribution to a particular Lagrangian operator.

</details>

### Exercise 3: IR cancellation in amplitude matching

Suppose a one-loop full-theory amplitude contains

$$
\mathcal M_{\text{full}}^{(1)}
=
A\log\frac{-s}{\mu^2}
+
B\log\frac{M^2}{\mu^2}
+
D,
$$

while the EFT loop from lower-order operators contains

$$
\mathcal M_{\text{EFT, known}}^{(1)}
=
A\log\frac{-s}{\mu^2}
+
E.
$$

What determines the one-loop Wilson coefficient?

<details><summary><strong>Solution</strong></summary>

The matching coefficient is determined by the local difference

$$
\mathcal M_{\text{full}}^{(1)}
-
\mathcal M_{\text{EFT, known}}^{(1)}
=
B\log\frac{M^2}{\mu^2}
+
D-E.
$$

The nonlocal light logarithm $A\log(-s/\mu^2)$ cancels. The remaining terms are independent of the low-energy branch cut and can be projected onto local amplitude structures. Those projections determine the one-loop Wilson coefficients in the chosen scheme.

</details>

### Exercise 4: How many amplitudes are enough?

Suppose an EFT has two operators $\mathcal O_1,\mathcal O_2$, but for one chosen helicity amplitude they produce the same local structure:

$$
\mathcal M_1^{++++}=\mathcal M_2^{++++}.
$$

Can this helicity amplitude determine $C_1$ and $C_2$ separately?

<details><summary><strong>Solution</strong></summary>

No. The chosen helicity amplitude only sees the combination $C_1+C_2$ multiplying that local structure. To separate $C_1$ and $C_2$, one needs another independent observable: a different helicity configuration, a different external species, a correlator, a background-field matching condition, or a basis convention that removes one operator as redundant. Matching can only determine directions visible to the chosen probes.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, for LSZ reduction, scattering amplitudes, renormalization, RG, and EFT examples.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I and Vol. II, for the $S$-matrix viewpoint, renormalization, and RG methods.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, for amplitude normalization, renormalized perturbation theory, nonrenormalizable theories, and EFT examples.
- C. P. Burgess, *Introduction to Effective Field Theory*, for matching, power counting, field redefinitions, and the low-energy expansion.
- Aneesh V. Manohar and collaborators, EFT lectures and reviews, for practical on-shell matching, operator bases, and modern EFT workflows.

## Version history

- 2026-06-18: First polished draft. Added on-shell matching workflow, LSZ interpretation, amplitude-basis discussion, tree and loop examples, infrared and gauge-theory cautions, and exercises.
