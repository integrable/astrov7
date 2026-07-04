---
title: "Tauberian and Asymptotic Methods"
description: "How singular limits, positivity, and Tauberian theorems extract averaged high-energy spectral and OPE data from conformal correlators."
sidebar:
  label: "Tauberian and Asymptotic Methods"
  order: 11
level: Advanced
status: "Polished draft"
source: "Hardy-Littlewood Tauberian theory; Cardy; Hellerman; Pappadopulo et al.; Mukhametzhanov and Zhiboedov; Qiao and Rychkov; analytic bootstrap literature."
topics:
  - Tauberian methods
  - asymptotic CFT data
  - density of states
  - OPE asymptotics
  - analytic conformal bootstrap
canonicalTopics:
  - tauberian-and-asymptotic-methods
  - asymptotic-cft-data
  - spectral-density-bootstrap
researchStatus:
  established:
    - "Tauberian methods relate singular behavior of CFT partition functions and correlators to averaged asymptotic spectral and OPE data under positivity assumptions."
  active:
    - "Current research refines error estimates, sparseness assumptions, higher-dimensional OPE asymptotics, microcanonical windows, modular bootstrap, thermal bootstrap, and connections to numerics and holography."
---

## Summary

**Tauberian and asymptotic methods** extract large-dimension or high-energy CFT data from singular limits of generating functions. The prototype is a Laplace transform

$$
F(\beta)=\int_0^\infty dE\,\rho(E)e^{-\beta E}.
$$

If

$$
F(\beta)\sim A\beta^{-p}
\qquad
(\beta\to0^+),
$$

and $\rho(E)$ is positive, then a Tauberian theorem implies the cumulative asymptotic

$$
N(E)=\int_0^E dE'\,\rho(E')
\sim \frac{A}{\Gamma(p+1)}E^p.
$$

In conformal field theory, the same logic applies to partition functions, four-point functions, OPE coefficient sums, modular bootstrap, and heavy-state averages. The key lesson is

$$
\text{singularity}+\text{positivity}
\quad\Longrightarrow\quad
\text{averaged asymptotic CFT data}.
$$

The word **averaged** is load-bearing. These methods usually control cumulative or smeared data, not every individual operator.

## Prerequisites

Read [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/), [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/), [Double Discontinuity](/cft-bootstrap/analytic-bootstrap/double-discontinuity/), [Large-Spin Perturbation Theory](/cft-bootstrap/analytic-bootstrap/large-spin-perturbation-theory/), and [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/) first.

You should know Laplace transforms, asymptotic notation, positive spectral densities, and the idea that CFT correlators can be expanded as sums over operator data.

## Core idea

Many CFT objects are generating functions. A thermal partition function is a sum over states,

$$
Z(\beta)=\sum_i e^{-\beta E_i},
$$

and a four-point function expanded in one OPE channel is a sum over operators,

$$
\mathcal G=\sum_{\mathcal O}a_{\mathcal O}G_{\Delta,\ell}.
$$

When the coefficients are positive, a singularity of the generating function forces growth of the summed coefficients. This is the Tauberian bridge.

The conceptual chain is

$$
\text{positive CFT expansion}
\quad\to\quad
\text{singular limit}
\quad\to\quad
\text{asymptotic spectral or OPE average}.
$$

The hard part is usually not identifying a singularity. The hard part is proving the positivity, the averaging window, and the error estimate.

## Positivity

Tauberian theorems need positivity or controlled signs. If the coefficients can oscillate wildly, singular behavior can arise from cancellations and may not determine the true size of the spectrum.

In CFT, positivity often comes from:

| Source | Positive quantity |
|---|---|
| Hilbert-space trace | degeneracies in $Z(\beta)$ |
| unitary identical-scalar OPE | squared OPE coefficients $\lambda^2$ |
| reflection positivity | Euclidean spectral weights |
| double discontinuity | positive Lorentzian data in suitable regimes |
| modular bootstrap | positive state degeneracies |

The safe slogan is

$$
\text{singularities speak clearly only when coefficients do not cancel maliciously}.
$$

Tiny theorem goblin, large caveat.

## Cumulative versus pointwise data

A Tauberian conclusion usually controls a cumulative sum such as

$$
N(E)=\sum_{E_i\le E}1
$$

or an OPE-weighted cumulative sum such as

$$
A(\Delta)=\sum_{\Delta_i\le\Delta}a_i.
$$

It does not automatically say that the individual level density or each OPE coefficient is smooth. CFT spectra on the cylinder are discrete. Operators can clump, degeneracies can spike, and OPE coefficients can fluctuate.

A precise asymptotic statement should say whether it is:

- cumulative below a cutoff;
- averaged in a microcanonical window;
- spin summed;
- fixed spin;
- fixed twist and large spin;
- weighted by conformal block asymptotics.

Without the averaging prescription, the formula is only half a statement.

## Density of states

Thermal CFT on $S^{d-1}$ has a partition function

$$
Z(\beta)=\sum_i e^{-\beta E_i}.
$$

The high-temperature limit

$$
\beta\to0^+
$$

is controlled by high-energy states. If symmetries or geometric arguments determine the singular behavior of $Z(\beta)$, Tauberian methods convert it into a density-of-states estimate.

In two-dimensional CFT, modular invariance gives the most famous example. High temperature is related to low temperature; the low-temperature channel may be vacuum dominated; this gives Cardy-like growth of high-energy states.

The precise Cardy formula belongs in the two-dimensional CFT chapter. Here the point is methodological:

$$
\text{modular or thermal singularity}
\quad\Rightarrow\quad
\text{averaged spectral growth}.
$$

## OPE coefficient asymptotics

Four-point functions also act as generating functions. In a unitary identical-scalar setup,

$$
\mathcal G(u,v)=\sum_{\mathcal O}\lambda_{\phi\phi\mathcal O}^2G_{\Delta,\ell}(u,v),
$$

with

$$
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

A singularity of $\mathcal G(u,v)$ in a cross-ratio limit constrains averaged OPE data. The conformal block asymptotics determine the precise weight in the sum.

Schematically, one obtains information about

$$
A(\Delta)=\sum_{\Delta_{\mathcal O}\le\Delta}\lambda_{\phi\phi\mathcal O}^2 w_{\mathcal O},
$$

where $w_{\mathcal O}$ depends on spin, dimension, and the chosen limit.

This is the OPE analogue of density-of-states asymptotics. The correlator is the generating function; OPE data are the coefficients.

## Heavy-light and thermal viewpoints

By radial quantization, a primary of dimension $\Delta$ creates a state of energy

$$
E=\Delta/R
$$

on a sphere of radius $R$. Large-dimension data therefore have a thermal or microcanonical interpretation.

Heavy-light correlators study matrix elements involving heavy operators with

$$
\Delta_H\gg1
$$

and light probes. Tauberian methods can constrain averaged heavy-light OPE data from singularities, thermal limits, or modular transformations.

In holographic CFTs, heavy states can correspond to high-energy AdS states or black-hole-like states. Averaged OPE data then have a gravitational interpretation, but the CFT statement remains a statement about spectra and matrix elements.

## Large spin versus large dimension

Do not collapse all asymptotic limits into one bucket. Different limits control different data.

| Limit | Typical data controlled |
|---|---|
| large spin, fixed $n$ | double-twist anomalous dimensions |
| large dimension, spin summed | density of states or averaged OPE data |
| large dimension, fixed spin | fixed-spin spectral asymptotics |
| large $n$ and large spin | high-energy two-particle data in AdS-like settings |
| high temperature | spectrum on $S^{d-1}$ |

Lightcone bootstrap is usually a large-spin method. Tauberian density estimates are usually large-dimension or high-energy methods. They are related, but they are not interchangeable.

## Error estimates and windows

Modern Tauberian bootstrap work cares about error terms and window sizes. A statement might control the number of states in an interval

$$
[E,E+\delta E]
$$

only if $\delta E$ grows with $E$ in a specified way.

A narrow window has better resolution but is harder to control. A broad window is easier to control but less local. This tradeoff is central.

A polished asymptotic result should state:

1. the quantity being averaged;
2. the window size;
3. the leading term;
4. the error estimate;
5. the assumptions, such as positivity or vacuum dominance.

Asymptotic formulas without quantifiers are vibes in formalwear.

## Relation to Lorentzian inversion

Lorentzian inversion and Tauberian methods both extract data from analytic structure, but they do different jobs.

| Lorentzian inversion | Tauberian methods |
|---|---|
| reconstructs spin-dependent CFT data | controls averaged high-energy data |
| uses double discontinuities | uses singularities of positive transforms |
| often strongest at large spin | often strongest after averaging |
| gives poles and residues | gives cumulative densities or averaged sums |
| sensitive to Regge behavior | sensitive to positivity and windows |

They can work together. For example, inversion can express OPE data through positive double discontinuities, while Tauberian estimates can control the asymptotic growth of the resulting spectral sums.

## Practical workflow

A typical Tauberian bootstrap argument follows this pattern:

1. Identify a positive spectral expansion.
2. Define the cumulative or averaged quantity.
3. Determine the singular limit of the generating function.
4. Check whether known low-energy, low-twist, or vacuum data dominate that limit.
5. Verify positivity and boundedness assumptions.
6. Apply a suitable Tauberian theorem.
7. State the asymptotic with its averaging window and error term.
8. Translate the answer back into dimensions, spins, charges, or OPE coefficients.

The theorem is only as good as the hypotheses. The hypotheses are part of the result.

## Common pitfalls

**Do not turn averaged asymptotics into pointwise claims.** Tauberian results usually control cumulative or smeared data.

**Do not ignore positivity.** Without positivity, cancellations can defeat the inference from singularity to growth.

**Do not hide the window.** Window size determines the resolution of the statement.

**Do not confuse large spin with large dimension.** They are different limits.

**Do not quote Cardy-like formulas without assumptions.** Modular invariance, unitarity, compactness, and vacuum dominance matter.

**Do not forget descendants and weights.** CFT spectral sums may include descendants, spin sums, or conformal-block weights.

**Do not treat an asymptotic equivalence as exact equality.** Error estimates matter.

## Relations to other pages

This page follows [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/) and prepares [Analytic-Numerical Bridges](/cft-bootstrap/analytic-bootstrap/analytic-numerical-bridges/).

It connects to [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/), [Double Discontinuity](/cft-bootstrap/analytic-bootstrap/double-discontinuity/), [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/), and [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/).

For two-dimensional applications, see [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) and modular-bootstrap pages when expanded. For thermal interpretations, see [Thermal and Lorentzian CFT](/cft-bootstrap/thermal-lorentzian-cft/).

## Research status

Tauberian methods are established tools for deriving density-of-states and averaged OPE asymptotics from CFT singularities when positivity and symmetry are available.

Active research improves error terms, microcanonical window sizes, higher-dimensional OPE asymptotics, charged and spin-refined densities, heavy-light data, modular bootstrap estimates, holographic entropy bounds, and interfaces with numerical bootstrap and Lorentzian inversion.

## Exercises

### Exercise 1

Suppose

$$
F(\beta)=\int_0^\infty dE\,\rho(E)e^{-\beta E}
\sim A\beta^{-p}
$$

as $\beta\to0^+$, with $\rho(E)\ge0$. What cumulative asymptotic should one expect?

<details><summary><strong>Solution</strong></summary>

One expects

$$
N(E)=\int_0^E dE'\,\rho(E')
\sim \frac{A}{\Gamma(p+1)}E^p
$$

under the hypotheses of the relevant Tauberian theorem.

</details>

### Exercise 2

Why does positivity matter in Tauberian arguments?

<details><summary><strong>Solution</strong></summary>

Positivity prevents large cancellations in the spectral sum. With positive coefficients, a singularity of the transform forces actual cumulative growth. If coefficients can have arbitrary signs, the same singularity might be produced by cancellations and may not determine the size of the data.

</details>

### Exercise 3

What is the difference between cumulative and pointwise asymptotics?

<details><summary><strong>Solution</strong></summary>

Cumulative asymptotics describe sums up to a cutoff, such as

$$
N(E)=\sum_{E_i\le E}1.
$$

Pointwise asymptotics would describe each individual level or coefficient. Tauberian methods usually control cumulative or averaged data, not individual operators one by one.

</details>

### Exercise 4

Why is the Cardy formula Tauberian in spirit?

<details><summary><strong>Solution</strong></summary>

Modular invariance relates high temperature to low temperature. If the low-temperature channel is dominated by the vacuum, this determines a high-temperature singularity. Tauberian reasoning then converts that singularity into averaged high-energy growth of the density of states.

</details>

### Exercise 5

Name two differences between Lorentzian inversion and Tauberian methods.

<details><summary><strong>Solution</strong></summary>

Lorentzian inversion reconstructs spin-dependent CFT data from double discontinuities and often controls large-spin trajectories. Tauberian methods extract averaged high-energy or high-dimension data from singularities of positive generating functions. Inversion gives poles and residues; Tauberian methods usually give cumulative densities or averaged OPE sums.

</details>

## References

- G. H. Hardy and J. E. Littlewood, “Tauberian theorems concerning power series and Dirichlet's series whose coefficients are positive,” *Proceedings of the London Mathematical Society* **13** (1914).
- J. L. Cardy, “Operator content of two-dimensional conformally invariant theories,” *Nuclear Physics B* **270** (1986).
- S. Hellerman, “A universal inequality for CFT and quantum gravity,” *Journal of High Energy Physics* **2011**.
- D. Pappadopulo, S. Rychkov, J. Espin, and R. Rattazzi, “OPE convergence in conformal field theory,” *Physical Review D* **86** (2012).
- B. Mukhametzhanov and A. Zhiboedov, “Analytic Euclidean bootstrap,” *Journal of High Energy Physics* **2019**.
- J. Qiao and S. Rychkov, “A Tauberian theorem for the conformal bootstrap,” *Journal of High Energy Physics* **2017**.

## Version history

- 2026-07-01: First polished draft. Added basic Tauberian example, positivity and averaging discussion, density-of-states and OPE asymptotics, Cardy-style logic, heavy-light and holographic interpretations, error-window caveats, exercises, and references.
