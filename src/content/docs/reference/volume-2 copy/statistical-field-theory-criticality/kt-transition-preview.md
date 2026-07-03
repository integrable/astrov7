---
title: "KT Transition Preview"
description: "A graduate-level preview of the Kosterlitz–Thouless transition, vortex unbinding, essential scaling, stiffness jumps, and why ordinary power-law criticality fails."
sidebar:
  label: "KT Transition Preview"
  order: 10
level: Graduate
status: "Polished draft"
source: "Kosterlitz and Thouless 1973; Kosterlitz 1974; Wilson and Kogut 1974; Zinn-Justin 2021; Altland and Simons 2023, §6.5."
topics:
  - Kosterlitz–Thouless transition
  - vortices
  - two-dimensional XY model
  - marginal RG flow
  - essential singularity
canonicalTopics:
  - kt-transition
  - bkt-transition
  - vortex-unbinding
  - compact-boson-rg
researchStatus:
  established:
    - "The KT transition is the standard example of a topological transition controlled by vortex unbinding and marginal RG flow rather than an ordinary relevant thermal eigenvalue."
  active:
    - "Precision finite-size analysis, disorder, quantum realizations, driven systems, generalized defects, and finite-temperature experiments continue to make KT scaling a living subject."
---

## Summary

The Kosterlitz–Thouless transition is the transition that breaks the habit of thinking every continuous transition has an ordinary local order parameter and a power-law divergent correlation length.

The canonical example is the two-dimensional XY model. Its microscopic variables are angles

$$
\theta_i\sim \theta_i+2\pi,
$$

with Hamiltonian

$$
H=-J\sum_{\langle ij\rangle}\cos(\theta_i-\theta_j).
$$

At low temperature, spin waves produce algebraic correlations,

$$
\langle e^{i\theta(x)}e^{-i\theta(0)}\rangle
\sim
\frac{1}{|x|^{\eta(T)}}.
$$

At high temperature, vortices proliferate and correlations become exponential. The transition is driven by vortex–antivortex unbinding, not by a scalar mass term becoming relevant in the ordinary Wilson–Fisher sense.

The hallmark is the essential singularity

$$
\xi(T)
\sim
a\exp\!\left(\frac{b}{\sqrt{(T-T_c)/T_c}}\right),
\qquad T\downarrow T_c^+,
$$

instead of $\xi\sim |T-T_c|^{-\nu}$. This is why the page is a preview: KT transitions are simple to state, famously slippery to fit, and a superb stress test for RG intuition.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 54rem;">

![Kosterlitz-Thouless RG flow showing low-temperature bound-vortex flow toward zero fugacity and high-temperature unbound-vortex flow toward strong fugacity](/figures/renormalization-rg-eft/kt-vortex-unbinding-flow.svg)

<figcaption>

The KT transition is controlled by two running quantities: a stiffness $K$ and a vortex fugacity $y$. Low-temperature flows send $y\to0$, giving a line of Gaussian fixed points with algebraic order. High-temperature flows send $y$ to strong coupling, where vortices proliferate and correlations become short-ranged. The separatrix ends at the universal condition $K_c=2/\pi$ in the conventional normalization.

</figcaption>
</figure>

## Prerequisites

You should know [Finite-Size Scaling](/renormalization-rg-eft/statistical-field-theory-criticality/finite-size-scaling/), [Correlation Length](/renormalization-rg-eft/statistical-field-theory-criticality/correlation-length/), [Scale Invariance](/renormalization-rg-eft/fixed-points-critical-phenomena/scale-invariance/), and [Marginal Operators](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/). The page also uses the idea that compact fields can support topological defects.

We work in two Euclidean dimensions. The stiffness $K$ is dimensionless and is proportional to $J/T$ in the XY model. Different communities absorb factors of $2\pi$ into $K$ or into the vortex fugacity; this page states the convention before using formulas.

## Core idea

The low-temperature XY model looks, at first, like a free compact scalar. For slowly varying configurations,

$$
H\approx \frac{J}{2}\int d^2x\,(\nabla\theta)^2,
$$

or, in dimensionless Euclidean action form,

$$
S_{\text{sw}}=\frac{K}{2}\int d^2x\,(\nabla\theta)^2,
\qquad
K\sim \frac{J}{T}.
$$

If this were the whole story, the theory would be Gaussian at every temperature. But $\theta$ is compact. That compactness permits vortex configurations

$$
\oint d\theta=2\pi n,
\qquad n\in\mathbb Z.
$$

A vortex is invisible in a purely local Taylor expansion around smooth $\theta$, but it dominates the global physics of the transition. The KT transition is the moment when vortices stop being tightly bound in neutral pairs and begin to proliferate.

The slogan is

$$
\text{spin waves give algebraic order; vortices decide whether it survives.}
$$

## Spin waves and algebraic order

In the Gaussian approximation,

$$
S_{\text{sw}}=\frac{K}{2}\int d^2x\,(\nabla\theta)^2.
$$

The field $\theta$ itself has logarithmic fluctuations in two dimensions:

$$
\langle(\theta(x)-\theta(0))^2\rangle
\sim
\frac{1}{\pi K}\log\frac{|x|}{a}.
$$

Therefore the order-parameter correlator behaves as

$$
\langle e^{i\theta(x)}e^{-i\theta(0)}\rangle
=
\exp\!\left[-\frac12\langle(\theta(x)-\theta(0))^2\rangle\right]
\sim
\left(\frac{a}{|x|}\right)^{\eta},
$$

with

$$
\eta=\frac{1}{2\pi K}.
$$

This is quasi-long-range order: correlations decay as a power law, but there is no nonzero magnetization in the thermodynamic limit. This is consistent with the Mermin–Wagner theorem.

At the KT transition,

$$
K_c=\frac2\pi,
\qquad
\eta_c=\frac14.
$$

The value $\eta_c=1/4$ is one of the cleanest fingerprints of the transition, although finite-size logarithms can make it hard to observe directly.

## Vortex energy and entropy

A unit vortex centered at the origin has

$$
\theta(\mathbf x)=\arg(x+iy),
\qquad
|\nabla\theta|=\frac1r.
$$

Its dimensionless energy cost in the spin-wave action is

$$
S_{\text{vortex}}
=
\frac{K}{2}\int_a^L d^2x\,\frac1{r^2}
=
\pi K\log\frac{L}{a}+O(1),
$$

where $a$ is the core scale. The number of possible vortex positions grows like

$$
\frac{L^2}{a^2},
$$

so the entropy is

$$
S_{\text{entropy}}\sim 2\log\frac{L}{a}.
$$

Thus the free-energy cost of one isolated vortex is, schematically,

$$
\frac{F_{\text{vortex}}}{T}
\sim
(\pi K-2)\log\frac{L}{a}.
$$

If $\pi K>2$, isolated vortices are suppressed at large $L$. If $\pi K<2$, entropy wins and isolated vortices proliferate. This crude argument already predicts

$$
K_c=\frac2\pi.
$$

The RG makes this argument controlled by including vortex–antivortex pairs, screening, and the scale dependence of the stiffness.

:::note[The transition is topological]
The local angle field does not acquire an ordinary expectation value across the transition. What changes is the fate of topological defects: bound vortex pairs below $T_c$, proliferating free vortices above $T_c$.
:::

## Coulomb-gas picture

A vortex configuration with charges $n_i\in\mathbb Z$ behaves like a two-dimensional Coulomb gas. The interaction between vortices is logarithmic:

$$
S_{\text{vortices}}
\sim
-\pi K\sum_{i\neq j}n_i n_j\log\frac{|x_i-x_j|}{a}
+
\sum_i E_{\text{core}}n_i^2.
$$

Neutral vortex–antivortex pairs have finite energy at fixed separation. Widely separated unpaired vortices cost logarithmic energy, but also gain logarithmic entropy. The competition is exactly the KT mechanism.

The vortex fugacity is roughly

$$
y\sim e^{-E_{\text{core}}},
$$

where $E_{\text{core}}$ is the nonuniversal microscopic core action. The stiffness $K$ controls the long-distance logarithmic interaction. The RG tracks both.

## KT RG equations

In a common normalization, the leading KT equations are

$$
\frac{dK^{-1}}{d\ell}=4\pi^3 y^2+O(y^4),
$$

and

$$
\frac{dy}{d\ell}=(2-\pi K)y+O(y^3),
$$

where $\ell=\log b$ is the coarse-graining scale and $y$ is the vortex fugacity.

The second equation says vortices are irrelevant if

$$
\pi K>2,
$$

and relevant if

$$
\pi K<2.
$$

The first equation says vortex pairs screen the stiffness: once vortices become important, the effective stiffness is reduced.

There is a line of low-temperature fixed points at

$$
y=0,
\qquad
K>\frac2\pi.
$$

This is already unusual. Instead of an isolated critical fixed point, the low-temperature phase is a line of scale-invariant Gaussian theories with continuously varying exponent

$$
\eta(T)=\frac{1}{2\pi K_R(T)}.
$$

## Essential singularity

Ordinary critical points have a relevant eigenvalue $y_t=1/\nu$, so the correlation length diverges as a power law. The KT transition is controlled by a marginal flow near the separatrix. This produces an essential singularity:

$$
\xi(T)
\sim
a\exp\!\left(\frac{b}{\sqrt{t}}\right),
\qquad
 t=\frac{T-T_c}{T_c}>0.
$$

The constant $b$ is nonuniversal. The essential form is universal.

This singularity is more dramatic than any power law, but also harder to fit. Over a finite range, an exponential of $1/\sqrt t$ can masquerade as many different powers. This is one reason KT transitions are numerically treacherous.

## Universal stiffness jump

In superfluid language, the stiffness is the superfluid stiffness $\rho_s$ divided by temperature:

$$
K=\frac{\rho_s}{T}.
$$

The KT transition predicts the universal jump

$$
\rho_s(T_c^-)=\frac{2T_c}{\pi},
\qquad
\rho_s(T_c^+)=0,
$$

in ideal thermodynamic equilibrium. More precisely, the renormalized long-distance stiffness approaches $2T_c/\pi$ from below the transition and vanishes above it. Finite systems smooth the jump into a rounded crossover with logarithmic corrections.

This jump is one of the sharpest experimental signatures of KT physics in two-dimensional superfluids and superconducting films.

## Why ordinary finite-size scaling fails

For an ordinary critical point, the scaling variable is

$$
tL^{1/\nu}.
$$

For a KT transition, there is no finite $\nu$ describing the divergence. Instead,

$$
\xi\sim e^{b/\sqrt t}.
$$

The finite-size crossover occurs when $\xi\sim L$, so

$$
\log L\sim \frac{b}{\sqrt t}.
$$

Thus the distance from the transition scales as

$$
t_L\sim \frac{b^2}{(\log L)^2},
$$

up to further logarithmic corrections.

This is much slower than any power law. If one uses ordinary finite-size scaling over modest sizes, one often extracts an effective exponent with no asymptotic meaning. The humble logarithm, once again, is where overconfident fits go to embarrass themselves.

## Relation to the sine-Gordon theory

The vortex gas has a dual sine-Gordon description. Schematically,

$$
S_{\text{dual}}
=
\frac{1}{2\widetilde K}\int d^2x\,(\nabla\varphi)^2
-2y\int d^2x\,\cos\varphi.
$$

The cosine term inserts vortices. Its scaling dimension depends on the stiffness. The KT transition occurs when this cosine changes from irrelevant to relevant.

This is why the KT transition also appears in one-dimensional quantum systems, compact bosons, Luttinger liquids, Coulomb gases, sine-Gordon models, superfluids, superconducting films, and roughening transitions. Different costumes, same RG skeleton.

## Comparison with ordinary criticality

| Feature | Ordinary Wilson–Fisher-type transition | KT transition |
|---|---|---|
| Driving mechanism | relevant thermal scaling field | vortex fugacity and marginal stiffness flow |
| Order parameter | often local | no ordinary long-range order in 2D XY case |
| Correlation length | $\xi\sim |t|^{-\nu}$ | $\xi\sim e^{b/\sqrt t}$ |
| Low-temperature phase | ordered or massive, depending on model | quasi-long-range order with variable exponent |
| Fixed point | isolated critical fixed point | separatrix ending on a line of fixed points |
| Finite-size scaling | powers of $L$ | logarithmic corrections and $1/(\log L)^2$ drift |
| Defects | often secondary | central degrees of freedom |

## Common pitfalls

**Calling the low-temperature phase ordered.** It has algebraic order, not true long-range order, in the two-dimensional XY model.

**Ignoring compactness.** A noncompact free scalar has spin waves but no vortices. The transition depends on $\theta\sim\theta+2\pi$.

**Fitting KT data to ordinary power laws.** Over limited sizes, KT scaling can fake power laws. The asymptotic singularity is essential.

**Using bare stiffness instead of renormalized stiffness.** The universal jump is a statement about the long-distance stiffness.

**Forgetting vortex core physics.** The core energy is nonuniversal but controls the bare fugacity and therefore the crossover scale.

**Thinking the transition is only about the XY model.** The XY model is the canonical example, but the RG structure appears in compact bosons, Coulomb gases, sine-Gordon theory, thin superfluids, Josephson arrays, and Luttinger-liquid transitions.

## Relations to other pages

The KT transition is a boundary case for [Finite-Size Scaling](/renormalization-rg-eft/statistical-field-theory-criticality/finite-size-scaling/): it shows why marginal operators can replace power-law scaling by logarithms and essential singularities. It also connects to [Gaussian Fixed Point](/renormalization-rg-eft/statistical-field-theory-criticality/gaussian-fixed-point/), [Crossover and Dangerously Irrelevant Operators](/renormalization-rg-eft/fixed-points-critical-phenomena/crossover-and-dangerously-irrelevant-operators/), [Blocking and Coarse Graining](/renormalization-rg-eft/wilsonian-renormalization/blocking-and-coarse-graining/), and later pages on vortices, compact gauge fields, bosonization, and topological defects.

## Research status

The KT mechanism, leading RG equations, essential singularity, algebraic low-temperature phase, and universal stiffness jump are established. Active research concerns precise finite-size analysis, disordered KT transitions, nonequilibrium and driven transitions, quantum simulator realizations, topological defects in multicomponent systems, generalized Coulomb gases, and the interplay of KT physics with gauge constraints and higher-form symmetries.

## Exercises

### Exercise 1: Vortex energy

For a unit vortex $\theta=\arg(x+iy)$ in the action

$$
S=\frac{K}{2}\int d^2x\,(\nabla\theta)^2,
$$

show that

$$
S_{\text{vortex}}=\pi K\log\frac{L}{a}+O(1).
$$

<details><summary><strong>Solution</strong></summary>

For a unit vortex,

$$
|\nabla\theta|=\frac1r.
$$

Using polar coordinates and cutting off the core at $r=a$ and the system at $r=L$,

$$
S_{\text{vortex}}
=\frac{K}{2}\int_a^L r\,dr\int_0^{2\pi}d\phi\,\frac1{r^2}.
$$

Thus

$$
S_{\text{vortex}}
=\frac{K}{2}(2\pi)\int_a^L\frac{dr}{r}
=\pi K\log\frac{L}{a}.
$$

Core details contribute only an $O(1)$ term.

</details>

### Exercise 2: Entropy estimate for the transition

Use the entropy estimate $S_{\text{entropy}}\sim 2\log(L/a)$ and the vortex energy above to estimate the critical stiffness.

<details><summary><strong>Solution</strong></summary>

The dimensionless free-energy cost of one vortex is

$$
\frac{F}{T}
\sim
\pi K\log\frac{L}{a}-2\log\frac{L}{a}
=
(\pi K-2)\log\frac{L}{a}.
$$

If $\pi K>2$, this grows with system size and isolated vortices are suppressed. If $\pi K<2$, the entropy wins and vortices proliferate. The transition estimate is therefore

$$
\pi K_c=2,
\qquad
K_c=\frac2\pi.
$$

</details>

### Exercise 3: Critical exponent eta

Using the spin-wave result

$$
\eta=\frac{1}{2\pi K},
$$

show that the KT transition predicts $\eta_c=1/4$.

<details><summary><strong>Solution</strong></summary>

At the transition,

$$
K_c=\frac2\pi.
$$

Therefore

$$
\eta_c
=
\frac{1}{2\pi K_c}
=
\frac{1}{2\pi(2/\pi)}
=
\frac14.
$$

</details>

### Exercise 4: Finite-size shift for an essential singularity

Assume

$$
\xi(t)=a\exp\left(\frac{b}{\sqrt t}\right)
$$

above the transition. Estimate the value $t_L$ at which a finite system of size $L$ begins to feel critical.

<details><summary><strong>Solution</strong></summary>

The finite-size crossover occurs when

$$
\xi(t_L)\sim L.
$$

Thus

$$
\frac{L}{a}\sim \exp\left(\frac{b}{\sqrt{t_L}}\right).
$$

Taking logarithms,

$$
\log\frac{L}{a}\sim \frac{b}{\sqrt{t_L}}.
$$

Therefore

$$
t_L\sim \frac{b^2}{\left(\log(L/a)\right)^2}.
$$

This logarithmic drift is much slower than ordinary power-law finite-size scaling.

</details>

## References

- J. M. Kosterlitz and D. J. Thouless, "Ordering, Metastability and Phase Transitions in Two-Dimensional Systems," *Journal of Physics C* **6** (1973) 1181–1203.
- J. M. Kosterlitz, "The Critical Properties of the Two-Dimensional XY Model," *Journal of Physics C* **7** (1974) 1046–1060.
- V. L. Berezinskii, "Destruction of Long-Range Order in One-Dimensional and Two-Dimensional Systems Possessing a Continuous Symmetry Group," *Soviet Physics JETP* **32** (1971) 493–500.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the field-theoretic and RG perspective on critical phenomena.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially the renormalization-group discussion of the Berezinskii–Kosterlitz–Thouless transition.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for a concise RG treatment of two-dimensional transitions and scaling.

## Version history

- 2026-06-19: First polished draft. Added spin-wave correlations, vortex energy–entropy estimate, KT RG equations, essential singularity, stiffness jump, finite-size caveats, and exercises.
