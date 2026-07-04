---
title: "φ⁴₂ Theory"
description: "Explains the constructive two-dimensional quartic scalar model, including Wick ordering, cutoff removal, phase structure, and theorem-level status."
sidebar:
  label: "φ⁴₂ Theory"
  order: 5
level: Advanced
status: "Polished draft"
source: "Glimm–Jaffe λφ⁴₂ construction; Simon P(φ)₂; Glimm–Jaffe–Spencer phase transitions."
topics:
  - phi four two
  - constructive QFT
  - Wick ordering
  - superrenormalizable scalar field theory
  - phase transitions
canonicalTopics:
  - constructive-quantum-field-theory
  - phi-four-two
  - p-phi-two-models
  - wick-ordering
researchStatus:
  established:
    - 'The $\phi^4_2$ model is a classic rigorously constructed interacting relativistic QFT in two spacetime dimensions.'
  active:
    - "The construction is settled, but scaling limits, phase structure, and comparisons with lattice critical models require additional hypotheses and methods."
---

## Summary

The $\phi^4_2$ model is the quartic special case of $P(\phi)_2$. It is a two-dimensional Euclidean scalar field theory, hence a $1+1$-dimensional Lorentzian QFT after Osterwalder–Schrader reconstruction.

The formal interaction is

$$
\lambda \int_\Lambda \phi(x)^4 d^2x,
\qquad \lambda>0,
$$

but the field is too singular for $\phi(x)^4$ to be an ordinary function. The constructive definition replaces the formal local power by a Wick-ordered cutoff interaction. With $\phi_\epsilon(x)$ a mollified free field and

$$
c_\epsilon=\mathbb E[\phi_\epsilon(x)^2],
$$

the quartic Wick polynomial is

$$
:\!\phi_\epsilon^4\!:(x)
=
\phi_\epsilon(x)^4
-6c_\epsilon\phi_\epsilon(x)^2
+3c_\epsilon^2.
$$

In two dimensions $c_\epsilon$ diverges logarithmically as $\epsilon\downarrow0$. Wick ordering subtracts the local Gaussian self-contractions. The finite-volume measure is then schematically

$$
d\mu_{\Lambda,\epsilon}
=
Z_{\Lambda,\epsilon}^{-1}
\exp\left[-\lambda\int_\Lambda
:\!\phi_\epsilon^4\!:(x)d^2x\right]d\mu_C,
$$

possibly with lower-order Wick terms. The theorem-level work is proving that the ultraviolet and thermodynamic limits exist and have the Euclidean positivity, covariance, and nontriviality properties needed for a QFT.

:::note[Normalization]
This page writes the interaction as $\lambda\phi^4$. If a source writes $\lambda\phi^4/4!$, all numerical coefficients in the Wick-polynomial and counterterm formulas are rescaled. The mathematical content is unchanged.
:::

## Prerequisites

You should know [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/), [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/), [Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/), and [P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/). The reconstruction target is explained in [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/).

## Core idea

The model is simple enough to state in one line and singular enough to force the central constructive ideas. In two Euclidean dimensions the scalar field has engineering dimension

$$
[\phi]=\frac{d-2}{2}=0,
\qquad d=2,
$$

so the quartic coupling has positive mass dimension,

$$
[\lambda]=d-4[\phi]=2.
$$

That positive dimension is why $\phi^4_2$ is superrenormalizable: only finitely many ultraviolet subtractions are needed. At the same time, the free field is still a random distribution rather than a pointwise function, so $\phi(x)^4$ is not literally defined.

<figure class="doc-figure" style="--figure-width: 48rem;">

![φ⁴₂ construction map](/figures/rigorous-qft/phi-four-two-construction-map.svg)

<figcaption>

The $\phi^4_2$ construction is the quartic specialization of $P(\phi)_2$. Wick ordering removes logarithmic ultraviolet self-contractions, after which estimates control the finite-volume measure, the thermodynamic limit, and OS reconstruction.

</figcaption>
</figure>

The page is worth isolating from the general $P(\phi)_2$ story because $\phi^4$ is the scalar interaction most readers already know from perturbative QFT and critical phenomena.

## Setup and conventions

Work on Euclidean $\mathbb R^2$ with coordinates $x=(\tau,y)$. Let

$$
C=(-\Delta+m^2)^{-1},
\qquad m>0,
$$

and let $\mu_C$ be the centered Gaussian measure on distributions. Let $\rho_\epsilon$ be a smooth mollifier and define

$$
\phi_\epsilon(x)=\phi(\rho_\epsilon(x-\cdot)).
$$

For a bounded region $\Lambda\subset\mathbb R^2$, a useful cutoff interaction is

$$
V_{\Lambda,\epsilon}(\phi)
=
\int_\Lambda
\left(
\lambda :\!\phi_\epsilon^4\!:(x)
+\nu :\!\phi_\epsilon^2\!:(x)
+h\phi_\epsilon(x)
\right)d^2x.
$$

Here $\lambda>0$ gives stability, $\nu$ is a quadratic coupling, and $h$ is an external field. The symmetric model has $h=0$. The finite-cutoff measure is

$$
d\mu_{\Lambda,\epsilon}
=
Z_{\Lambda,\epsilon}^{-1}
\exp[-V_{\Lambda,\epsilon}(\phi)]d\mu_C.
$$

For fixed $\Lambda$ and $\epsilon$, this is an honest probability measure under the usual stability assumptions. The constructive problem is to control it as

$$
\epsilon\downarrow0,
\qquad
\Lambda\uparrow\mathbb R^2.
$$

## Wick ordering as counterterms

The Wick quartic can be read two ways. Probabilistically, it is the fourth Hermite polynomial adapted to a Gaussian variable of variance $c_\epsilon$. Field-theoretically, it is the quartic interaction plus the local counterterms forced by Gaussian contractions:

$$
\lambda:\!\phi_\epsilon^4\!:
=
\lambda\phi_\epsilon^4
-6\lambda c_\epsilon\phi_\epsilon^2
+3\lambda c_\epsilon^2.
$$

The term proportional to $\phi_\epsilon^2$ has the form of a mass counterterm. The constant term shifts the normalization or vacuum energy. For standard mollifiers in two dimensions,

$$
c_\epsilon
\sim
\frac{1}{2\pi}\log\frac1\epsilon+O(1).
$$

The first constructive lesson is that renormalization is part of the definition. The object inserted into the measure is the renormalized local polynomial, not the divergent bare monomial.

## Finite-volume continuum measure

For fixed bounded $\Lambda$, one proves that

$$
V_{\Lambda,\epsilon}
\longrightarrow
V_\Lambda
$$

in a suitable $L^p(d\mu_C)$ sense, and that the exponential densities converge strongly enough to define

$$
d\mu_\Lambda
=
Z_\Lambda^{-1}e^{-V_\Lambda}d\mu_C.
$$

This is already a genuine theorem. It is not enough to know that Wick powers exist as random distributions; one must also control the exponential of the integrated interaction.

The stabilizing condition $\lambda>0$ matters here. With the wrong sign, the finite-dimensional analogy already warns that the action is unbounded below. Perturbation theory can temporarily ignore this; a probability measure cannot.

The finite-volume Schwinger functions are

$$
S_{n,\Lambda}(f_1,\ldots,f_n)
=
\int \phi(f_1)\cdots\phi(f_n)d\mu_\Lambda(\phi).
$$

They are the objects one tries to pass to infinite volume.

## Infinite volume and phases

The thermodynamic limit asks whether, for compactly supported test functions,

$$
S_n(f_1,\ldots,f_n)
=
\lim_{\Lambda\uparrow\mathbb R^2}
S_{n,\Lambda}(f_1,\ldots,f_n)
$$

exists. The answer may depend on boundary conditions, on $h\to0^+$ or $h\to0^-$, and on the parameter regime.

For the symmetric double-well regime, the model has a discrete symmetry

$$
\phi\mapsto -\phi
$$

when $h=0$. Since this is a discrete symmetry, it can break in two Lorentzian dimensions. This does not contradict Coleman's theorem, which concerns continuous internal symmetries under its hypotheses.

The phase-transition results for $\phi^4_2$ show that constructive QFT is not only about ultraviolet existence. It also sees genuine many-body phenomena: multiple infinite-volume states, pure phases, correlation inequalities, Lee–Yang methods, and critical behavior.

## What the construction proves

A clean way to read the literature is to separate several theorem types.

| Statement | Meaning |
|---|---|
| Hamiltonian construction | The interacting Hamiltonian is self-adjoint and bounded below after removing cutoffs. |
| Euclidean construction | Wick-ordered densities define Schwinger functions in finite and infinite volume. |
| OS positivity | The Euclidean Schwinger functions reconstruct a Hilbert space with positive inner product. |
| Wightman axioms | The Lorentzian fields satisfy the structural axioms. |
| Particle structure | In suitable weak-coupling regimes there is an isolated mass shell and controlled low-energy spectrum. |
| Phase transition | In other regimes there can be more than one infinite-volume phase. |

These are related but not identical. A construction of the local interacting measure is not automatically a theorem about the particle spectrum. A phase-transition theorem is not merely an ultraviolet renormalization statement.

## Relation to perturbation theory

Perturbatively, $\phi^4_2$ has only simple ultraviolet divergences. Tadpole contractions give the logarithmic $c_\epsilon$ divergence; Wick ordering subtracts them. Vacuum diagrams contribute normalization constants.

Constructively, the perturbative picture is only the guide. The actual object is the non-Gaussian measure or its Schwinger functions. In favorable regimes the perturbation series can be asymptotic or Borel summable, but the constructive theory is not defined by summing Feynman diagrams term by term.

This gives three complementary meanings of "renormalized."

| Viewpoint | What is renormalized? |
|---|---|
| Diagrammatic | Divergent tadpoles and vacuum diagrams. |
| Probabilistic | Local polynomial functions of a Gaussian random distribution. |
| Constructive | Cutoff measures and Schwinger functions with regulator-independent limits. |

## Common pitfalls

**Do not read the subscript as a power.** In $\phi^4_2$, the exponent $4$ is the power of the field and the subscript $2$ is the Euclidean spacetime dimension.

**Do not write $\phi(x)^4$ as a literal function.** The two-dimensional free field is a distribution. The local quartic interaction is defined by a limiting Wick polynomial.

**Do not identify finite volume with the final theory.** Finite volume is a regulator. Infinite-volume limits carry phase information and are needed for translation-invariant vacuum QFT.

**Do not overstate the analogy with four dimensions.** The model is superrenormalizable. Its constructive success does not imply that $\phi^4_4$ has a nontrivial continuum limit.

**Do not confuse discrete and continuous symmetry breaking.** The double-well $\phi^4_2$ model can exhibit $\mathbb Z_2$ symmetry breaking. Coleman's obstruction is about continuous symmetries.

## Relations to other pages

[P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/) gives the general polynomial construction of which this page is the quartic specialization.

[Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/) explains the reference measure and Wick-polynomial technology.

[φ⁴₃ Theory](/rigorous-qft/constructive-qft/phi-four-three/) is the next scalar model: it remains superrenormalizable but needs deeper multiscale renormalization.

[Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/) and [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) explain how Euclidean estimates become Lorentzian QFT statements.

## Research status

The construction of $\phi^4_2$ is established. It is one of the foundational successes of constructive QFT and helped demonstrate that interacting relativistic QFTs can satisfy rigorous axioms.

The model remains useful because different parameter regimes emphasize different questions: weak coupling emphasizes particle structure and mass gaps; double-well regimes emphasize phase transitions and symmetry breaking; critical regimes connect to scaling limits and statistical mechanics.

## Exercises

### Exercise 1: Power counting

Using $[\phi]=(d-2)/2$, compute the mass dimension of the quartic coupling in $d=2$ and explain why this is called superrenormalizable.

<details><summary><strong>Solution</strong></summary>

The interaction $\int d^dx\,\lambda\phi^4$ is dimensionless, so

$$
[\lambda]+4[\phi]-d=0.
$$

In $d=2$, $[\phi]=0$, hence $[\lambda]=2$. A positive mass dimension means the coupling is relevant by power counting and only finitely many ultraviolet counterterms are needed.

</details>

### Exercise 2: Zero mean of the Wick quartic

Let $X$ be centered Gaussian with variance $c$. Verify that $:\!X^4\!:=X^4-6cX^2+3c^2$ has expectation zero.

<details><summary><strong>Solution</strong></summary>

For a centered Gaussian variable,

$$
\mathbb E[X^2]=c,
\qquad
\mathbb E[X^4]=3c^2.
$$

Therefore

$$
\mathbb E[:\!X^4\!:]
=3c^2-6c^2+3c^2=0.
$$

</details>

### Exercise 3: Identify the counterterms

In

$$
\lambda:\!\phi_\epsilon^4\!:
=
\lambda\phi_\epsilon^4
-6\lambda c_\epsilon\phi_\epsilon^2
+3\lambda c_\epsilon^2,
$$

which terms look like mass and vacuum-energy counterterms?

<details><summary><strong>Solution</strong></summary>

The term $-6\lambda c_\epsilon\phi_\epsilon^2$ has the same field dependence as a quadratic mass term. The term $3\lambda c_\epsilon^2$ is independent of the field and contributes, after integration over volume, a normalization or vacuum-energy shift.

</details>

## References

### Standard first pass

- Barry Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.
- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- James Glimm and Arthur Jaffe, "A $\lambda\phi^4$ Quantum Field Theory without Cutoffs. I," *Physical Review* **176** (1968), 1945–1951. DOI: [10.1103/PhysRev.176.1945](https://doi.org/10.1103/PhysRev.176.1945).

### Constructive and phase-structure references

- James Glimm and Arthur Jaffe, "The $\lambda(\varphi^4)_2$ Quantum Field Theory without Cutoffs. II. The Field Operators and the Approximate Vacuum," *Annals of Mathematics* **91** (1970), 362–401. DOI: [10.2307/1970582](https://doi.org/10.2307/1970582).
- James Glimm and Arthur Jaffe, "The $\lambda(\phi^4)_2$ Quantum Field Theory without Cut-Offs. III. The Physical Vacuum," *Acta Mathematica* **125** (1970), 203–267. DOI: [10.1007/BF02392335](https://doi.org/10.1007/BF02392335).
- James Glimm, Arthur Jaffe, and Thomas Spencer, "The Wightman Axioms and Particle Structure in the $P(\phi)_2$ Quantum Field Model," *Annals of Mathematics* **100** (1974), 585–632. DOI: [10.2307/1970959](https://doi.org/10.2307/1970959).
- James Glimm, Arthur Jaffe, and Thomas Spencer, "Phase Transitions for $\phi^4_2$ Quantum Fields," *Communications in Mathematical Physics* **45** (1975), 203–216. DOI: [10.1007/BF01608328](https://doi.org/10.1007/BF01608328).

## Version history

- **2026-06-29:** Initial page created.
