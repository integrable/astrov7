---
title: "Correlation Inequalities"
description: "A theorem-level guide to correlation inequalities and their use in constructive and statistical field theory."
sidebar:
  label: "Correlation Inequalities"
  order: 10
level: Advanced
status: "Polished draft"
source: "Griffiths–Kelly–Sherman inequalities; FKG inequality; Ginibre inequalities; Guerra–Rosen–Simon and Simon applications to P(φ)₂."
topics:
  - constructive QFT
  - correlation inequalities
  - FKG inequality
  - Griffiths inequalities
  - mass gap
canonicalTopics:
  - constructive-quantum-field-theory
  - correlation-inequalities
  - statistical-mechanics
  - euclidean-quantum-field-theory
researchStatus:
  established:
    - "Correlation inequalities are rigorous nonperturbative tools for ferromagnetic spin systems, lattice fields, and selected constructive Euclidean field theories."
  active:
    - "The applicability of a given inequality is highly model-dependent; gauge theories, fermionic theories, frustrated systems, and sign-problem models usually require different positivity structures."
---

## Summary

Correlation inequalities are rigorous statements saying that certain correlations are nonnegative, monotone, or bounded by simpler correlations. They are not approximation schemes. When their hypotheses hold, they give nonperturbative control that survives strong coupling, infinite volume, and sometimes continuum limits.

The two most common templates are positive association and ferromagnetic Griffiths-type inequalities. For an ordered probability space, positive association says

$$
\langle FG\rangle-\langle F\rangle\langle G\rangle\geq0
$$

for increasing functions $F$ and $G$. For ferromagnetic Ising-type systems, Griffiths–Kelly–Sherman inequalities say, schematically,

$$
\langle \sigma_A\rangle\geq0,
\qquad
\langle \sigma_A\sigma_B\rangle
-
\langle \sigma_A\rangle\langle \sigma_B\rangle
\geq0,
$$

where $\sigma_A=\prod_{i\in A}\sigma_i$ and the couplings are ferromagnetic.

In constructive QFT, such inequalities enter through the Euclidean-statistical-mechanics representation of scalar field theories. They help prove existence of limits, monotonicity in couplings and boundary conditions, uniqueness or nonuniqueness of phases, domination of higher correlations by two-point functions, and mass-gap estimates in some models.

The most important warning is that these inequalities are conditional. They rely on positivity: ferromagnetic signs, reflection positivity, positive covariance kernels, partial orders, or special Markov properties. A formal path integral with an interaction does not automatically satisfy them.

## Prerequisites

You should know [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/), [P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/), [φ⁴₂ Theory](/rigorous-qft/constructive-qft/phi-four-two/), and [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/). [Cluster Expansions](/rigorous-qft/constructive-qft/cluster-expansions/) gives a complementary method based on convergent series rather than inequalities.

## Core idea

A cluster expansion controls a model by representing it as a dilute gas. A correlation inequality controls a model by preserving an order or positivity structure. The latter can work even when no small parameter is available.

The key move is to replace a hard analytic question by an order-theoretic or positivity statement. For example, in a ferromagnet, increasing a positive coupling should not decrease spin correlations. A correlation inequality turns this physical expectation into a theorem. In Euclidean scalar QFT, the same style of argument can compare boundary conditions, dominate complicated Schwinger functions by two-point functions, or prove monotonicity of pressures and correlations.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Correlation inequalities as a map from positivity hypotheses to monotonicity, domination, and phase conclusions.](/figures/rigorous-qft/correlation-inequalities-map.svg)

<figcaption>

Correlation inequalities are bridges from positivity hypotheses to nonperturbative conclusions. The hypotheses differ across Ising spins, continuous scalar fields, reflection-positive systems, and infrared-bound arguments, so the first task is always to identify the correct positive cone.

</figcaption>
</figure>

## Setup and conventions

Start with a finite lattice $\Lambda$. For Ising spins $\sigma_i\in\{-1,+1\}$, define

$$
\sigma_A=\prod_{i\in A}\sigma_i.
$$

A ferromagnetic Hamiltonian has nonnegative couplings. In one common normalization,

$$
H(\sigma)
=-\sum_A J_A\sigma_A-\sum_i h_i\sigma_i,
\qquad
J_A\geq0,
\quad h_i\geq0.
$$

Expectations are finite-dimensional Gibbs averages,

$$
\langle F\rangle_\Lambda
=
\frac{1}{Z_\Lambda}
\sum_\sigma F(\sigma)e^{-H(\sigma)}.
$$

For continuous scalar fields, sums are replaced by integrals over fields or lattice fields. The simple Ising partial order may be replaced by an order on real-valued fields, a positivity-preserving Gaussian covariance, or a more specialized Ginibre-type structure. The formulas below are templates; each model requires its own hypotheses.

## FKG positive association

The Fortuin–Kasteleyn–Ginibre inequality applies to probability measures with positive association. On a finite partially ordered set, a function $F$ is increasing if $\omega\leq\omega'$ implies $F(\omega)\leq F(\omega')$. A measure $\mu$ is positively associated if

$$
\int FG\,d\mu
\geq
\left(\int F\,d\mu\right)
\left(\int G\,d\mu\right)
$$

for all bounded increasing $F$ and $G$.

A sufficient finite-lattice condition is log-supermodularity:

$$
\mu(\omega\vee\omega')\mu(\omega\wedge\omega')
\geq
\mu(\omega)\mu(\omega').
$$

In ferromagnetic lattice systems, this condition formalizes the statement that aligned configurations reinforce one another. In field theory language, FKG-type inequalities are useful when the Euclidean measure is genuinely positive and the interaction preserves the relevant order.

Consequences include monotonicity of magnetization and correlations with respect to positive external fields, comparison of boundary conditions, and existence of monotone infinite-volume limits.

## Griffiths–Kelly–Sherman and Ginibre inequalities

For Ising ferromagnets, the Griffiths inequalities say that spin products have nonnegative correlations. A standard form is

$$
\langle \sigma_A\rangle\geq0,
$$

and

$$
\langle \sigma_A\sigma_B\rangle
\geq
\langle \sigma_A\rangle\langle \sigma_B\rangle.
$$

The Kelly–Sherman extension allows more general ferromagnetic many-spin interactions. Ginibre formulated a broader algebraic framework that includes several continuous-spin systems.

These inequalities imply useful monotonicity statements. For example, differentiating a correlation with respect to a ferromagnetic coupling gives a truncated correlation:

$$
\frac{\partial}{\partial J_B}
\langle \sigma_A\rangle
=
\langle \sigma_A\sigma_B\rangle
-
\langle \sigma_A\rangle\langle \sigma_B\rangle
\geq0.
$$

Thus increasing a ferromagnetic coupling cannot decrease a positive spin correlation. This simple formula is one of the cleanest examples of how an inequality becomes a theorem about phase structure.

## Field-theoretic translation

Euclidean scalar QFT can often be approximated by lattice scalar systems. In favorable cases, the lattice measure has the schematic form

$$
d\mu_\Lambda(\phi)
=\frac{1}{Z_\Lambda}
\exp\left(
\sum_{x,y}J_{xy}\phi_x\phi_y
-
\sum_x V(\phi_x)
+\sum_x h_x\phi_x
\right)
\prod_x d\phi_x,
$$

with $J_{xy}\geq0$ and a single-site measure satisfying positivity assumptions. Then lattice correlation inequalities can be proved before taking limits. If the inequalities are uniform in the ultraviolet cutoff and volume, they can pass to the continuum Schwinger functions.

For $P(\phi)_2$ models, Guerra, Rosen, Simon, and related work used the Euclidean field theory as a classical statistical-mechanical system. This viewpoint made correlation inequalities, Markov-field properties, and boundary-condition comparisons available to constructive QFT. One important kind of conclusion is domination: higher truncated Schwinger functions can be bounded in terms of the two-point function under suitable hypotheses.

A typical field-theoretic lesson is:

$$
\text{control of }S_2^T(x,y)
\quad\Longrightarrow\quad
\text{control of larger truncated correlations}.
$$

This matters because the two-point function is where the mass gap is directly visible. If

$$
|S_2^T(x,y)|\leq C e^{-m|x-y|},
$$

then domination estimates may transfer exponential decay to larger correlations.

## What inequalities can prove

Correlation inequalities are especially good at proving qualitative, nonperturbative statements.

| Output | Meaning |
|---|---|
| Positivity | Certain Schwinger or spin correlations are nonnegative. |
| Monotonicity | Correlations increase with ferromagnetic couplings or positive fields. |
| Boundary comparison | Plus, free, periodic, or ordered boundary conditions can be compared. |
| Infinite-volume limits | Monotone limits exist for selected states or pressures. |
| Domination | Higher correlations are bounded by simpler lower correlations. |
| Phase information | Long-range order, uniqueness, or coexistence can sometimes be proved. |
| Mass-gap estimates | Exponential decay of a key two-point function can imply broader clustering. |

These are theorem-level controls. They are valuable precisely because they do not depend on term-by-term perturbation theory.

## Reflection positivity and infrared bounds

Some inequalities used near constructive QFT are not FKG or GKS inequalities, but belong to the same positivity toolkit. Reflection positivity gives a Hilbert-space inner product after OS reconstruction and also supports chessboard estimates in lattice systems. Gaussian domination and infrared bounds compare Fourier-space two-point functions to Gaussian propagators.

For spin systems with continuous symmetry, infrared bounds can prove spontaneous symmetry breaking in dimensions where the integral

$$
\int_{[-\pi,\pi]^d}\frac{d^dk}{(2\pi)^d}\,\frac{1}{\widehat D(k)}
$$

is finite. The same general idea appears in field-theoretic phase-transition arguments: positivity plus comparison with a Gaussian object can give long-distance information.

Do not merge all these tools into one theorem. FKG, GKS, Ginibre, reflection positivity, chessboard estimates, and infrared bounds have different hypotheses and different conclusions. Their common theme is controlled positivity.

## Common pitfalls

**Assuming every bosonic Euclidean measure is positively associated.** Positivity of the measure is not enough. FKG needs an order structure and a log-supermodularity or association hypothesis. GKS and Ginibre require ferromagnetic sign conditions or algebraic positivity assumptions.

**Forgetting the sign of the interaction.** A small antiferromagnetic or frustrated term can destroy the inequality. The theorem is not perturbatively robust unless one proves a replacement estimate.

**Confusing reflection positivity with FKG positivity.** Reflection positivity reflects across a time plane and builds a Hilbert space. FKG positivity is an order-correlation statement for increasing functions. They are both positivity properties, but they are not interchangeable.

**Applying spin inequalities directly to fermions.** Fermionic Grassmann integrals do not define positive probability measures. Constructive fermionic QFT uses determinant bounds, Gram estimates, and RG methods rather than FKG in its naive form.

**Mistaking monotonicity for exact solution.** Inequalities often prove existence, bounds, or phase structure. They usually do not give exact critical exponents or full correlation functions.

## Relations to other pages

- [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/) explains when a Euclidean path integral becomes an actual measure.
- [P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/) is the main scalar field-theory setting where statistical-mechanical inequalities enter constructive QFT.
- [φ⁴₂ Theory](/rigorous-qft/constructive-qft/phi-four-two/) uses the same Euclidean-statistical viewpoint for quartic scalar models and phases.
- [Cluster Expansions](/rigorous-qft/constructive-qft/cluster-expansions/) is the complementary proof technology for analyticity and exponential clustering in regimes with small polymer activities.
- [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/) explains the positivity condition that reconstructs Hilbert space from Euclidean time.

## Research status

Classical correlation inequalities are settled theorems in their proper domains. Their applications to constructive QFT are also well established in important low-dimensional scalar models, especially those connected to $P(\phi)_2$ and ferromagnetic statistical systems.

The active frontier is not whether GKS or FKG are true, but how far positivity methods can be pushed in models that are less ordered: gauge theories, fermionic theories, sign-changing interactions, systems with topological terms, frustrated spin systems, and continuum limits at criticality. In those settings, one often needs different positive structures or entirely different tools.

## Exercises

### Exercise 1: Coupling monotonicity from GKS

For an Ising ferromagnet with Hamiltonian

$$
H(\sigma)=-\sum_A J_A\sigma_A,
$$

show that the second Griffiths inequality implies

$$
\frac{\partial}{\partial J_B}\langle \sigma_A\rangle\geq0.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate the Gibbs expectation:

$$
\frac{\partial}{\partial J_B}\langle \sigma_A\rangle
=
\langle \sigma_A\sigma_B\rangle
-
\langle \sigma_A\rangle\langle \sigma_B\rangle.
$$

The second Griffiths inequality says the right-hand side is nonnegative for ferromagnetic couplings. Therefore $\langle\sigma_A\rangle$ is monotone nondecreasing in $J_B$.

</details>

### Exercise 2: Positive association for indicators

Let $A$ and $B$ be increasing events in a positively associated measure. Show that

$$
\mu(A\cap B)\geq \mu(A)\mu(B).
$$

<details>
<summary><strong>Solution</strong></summary>

Take $F=\mathbf 1_A$ and $G=\mathbf 1_B$. Since $A$ and $B$ are increasing, their indicator functions are increasing. Positive association gives

$$
\int \mathbf 1_A\mathbf 1_B\,d\mu
\geq
\left(\int \mathbf 1_A\,d\mu\right)
\left(\int \mathbf 1_B\,d\mu\right),
$$

which is exactly $\mu(A\cap B)\geq \mu(A)\mu(B)$.

</details>

### Exercise 3: Why fermions are different

Explain why a Grassmann integral cannot satisfy FKG as a probability measure on an ordered configuration space.

<details>
<summary><strong>Solution</strong></summary>

FKG is a statement about expectations with respect to a positive measure on an ordered space. Grassmann variables anticommute and are integrated algebraically; they are not real-valued random variables sampled from a positive probability measure. Fermionic constructive estimates therefore use different structures, such as determinant bounds and Gram inequalities.

</details>

## References

### Standard first pass

- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Barry Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.
- David Ruelle, *Statistical Mechanics: Rigorous Results*, W. A. Benjamin, 1969; World Scientific reprint, 1999. DOI: [10.1142/4090](https://doi.org/10.1142/4090).

### Deeper references

- Robert B. Griffiths, "Correlations in Ising Ferromagnets. I," *Journal of Mathematical Physics* **8** (1967), 478–483. DOI: [10.1063/1.1705219](https://doi.org/10.1063/1.1705219).
- Robert B. Griffiths, "Correlations in Ising Ferromagnets. II. External Magnetic Fields," *Journal of Mathematical Physics* **8** (1967), 484–489. DOI: [10.1063/1.1705220](https://doi.org/10.1063/1.1705220).
- D. G. Kelly and S. Sherman, "General Griffiths' Inequalities on Correlations in Ising Ferromagnets," *Journal of Mathematical Physics* **9** (1968), 466–484. DOI: [10.1063/1.1664600](https://doi.org/10.1063/1.1664600).
- Jean Ginibre, "General Formulation of Griffiths' Inequalities," *Communications in Mathematical Physics* **16** (1970), 310–328. DOI: [10.1007/BF01646537](https://doi.org/10.1007/BF01646537).
- C. M. Fortuin, P. W. Kasteleyn, and J. Ginibre, "Correlation Inequalities on Some Partially Ordered Sets," *Communications in Mathematical Physics* **22** (1971), 89–103. DOI: [10.1007/BF01651330](https://doi.org/10.1007/BF01651330).
- Barry Simon, "Correlation Inequalities and the Mass Gap in $P(\phi)_2$. I. Domination by the Two Point Function," *Communications in Mathematical Physics* **31** (1973), 127–136. DOI: [10.1007/BF01645740](https://doi.org/10.1007/BF01645740).
- Barry Simon, "Correlation Inequalities and the Mass Gap in $P(\phi)_2$. II. Uniqueness of the Vacuum for a Class of Strongly Coupled Theories," *Annals of Mathematics* **101** (1975), 260–267. DOI: [10.2307/1970990](https://doi.org/10.2307/1970990).
- Francesco Guerra, Lon Rosen, and Barry Simon, "Correlation Inequalities and the Mass Gap in $P(\phi)_2$. III. Mass Gap for a Class of Strongly Coupled Theories with Nonzero External Field," *Communications in Mathematical Physics* **41** (1975), 19–32. DOI: [10.1007/BF01608544](https://doi.org/10.1007/BF01608544).
- Jürg Fröhlich, Barry Simon, and Thomas Spencer, "Infrared Bounds, Phase Transitions and Continuous Symmetry Breaking," *Communications in Mathematical Physics* **50** (1976), 79–95. DOI: [10.1007/BF01608557](https://doi.org/10.1007/BF01608557).
- Joel L. Lebowitz, "Bounds on the Correlations and Analyticity Properties of Ferromagnetic Ising Spin Systems," *Communications in Mathematical Physics* **28** (1972), 313–321. DOI: [10.1007/BF01645736](https://doi.org/10.1007/BF01645736).

## Version history

- **2026-06-29:** Initial page on correlation inequalities in constructive and statistical field theory.
