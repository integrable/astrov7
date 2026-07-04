---
title: "Large-N Analytic Bootstrap"
description: "How analytic bootstrap treats large-N CFTs by perturbing generalized free fields, extracting double-trace anomalous dimensions, and organizing holographic AdS effective interactions."
sidebar:
  label: "Large-N Analytic Bootstrap"
  order: 10
level: Advanced
status: "Polished draft"
source: "Heemskerk, Penedones, Polchinski, and Sully; Fitzpatrick, Kaplan, Penedones, Raju, and van Rees; Alday; Caron-Huot; Mellin and holographic bootstrap literature."
topics:
  - large-N CFT
  - analytic conformal bootstrap
  - holographic CFT
  - double-trace operators
  - AdS effective field theory
canonicalTopics:
  - large-n-analytic-bootstrap
  - holographic-bootstrap
  - double-trace-anomalous-dimensions
researchStatus:
  established:
    - "Large-N analytic bootstrap treats connected CFT correlators as perturbations around generalized free field data and relates double-trace anomalous dimensions to AdS interactions."
  active:
    - "Current research develops loop-level holographic bootstrap, mixing and degeneracy control, stringy corrections, dispersion relations, spinning correlators, supersymmetric correlators, and nonperturbative large-N constraints."
---

## Summary

The **large-N analytic bootstrap** studies CFTs with a large parameter $N$ that suppresses connected correlators. At leading order, many single-trace operators behave like generalized free fields. Their four-point functions factorize, and the spectrum contains double-trace operators with mean-field dimensions

$$
\Delta_{n,\ell}^{(0)}=\Delta_1+\Delta_2+2n+\ell.
$$

At subleading order, crossing determines anomalous dimensions and OPE coefficient corrections:

$$
\Delta_{n,\ell}=\Delta_1+\Delta_2+2n+\ell+\frac{1}{N^p}\gamma_{n,\ell}^{(1)}+\cdots .
$$

In holographic CFTs, these corrections are interaction energies of two-particle states in AdS. Contact Witten diagrams, exchange diagrams, Mellin amplitudes, Lorentzian inversion, and Polyakov bootstrap are different languages for the same perturbative problem.

The slogan is

$$
\text{large }N=\text{generalized free field plus controlled crossing corrections}.
$$

## Prerequisites

Read [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/), [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/), [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/), [Polyakov Bootstrap](/cft-bootstrap/analytic-bootstrap/polyakov-bootstrap/), and [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/) first.

You should know generalized free field four-point functions, double-trace operators, OPE coefficients, anomalous dimensions, and the basic AdS/CFT dictionary.

## Core idea

Large $N$ gives a small parameter. In a normalized basis, connected correlators of single-trace operators are suppressed. For a scalar single-trace operator $\mathcal O$, the four-point function has the schematic expansion

$$
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle
=
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle_{\rm GFF}
+\frac{1}{N^p}\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle_{\rm conn}^{(1)}+\cdots .
$$

The first term is generalized free field. The second term is the leading interaction. The bootstrap problem is to impose crossing order by order in $1/N$.

The conceptual chain is

$$
\text{factorization}\to\text{mean-field double traces}\to\text{subleading crossing}\to\text{AdS interactions or CFT data corrections}.
$$

## Large-N factorization

A large-$N$ CFT has operators whose connected correlators scale with powers of $1/N$. For single-trace-like operators normalized by

$$
\langle \mathcal O(x)\mathcal O(0)\rangle=\frac{1}{(x^2)^\Delta},
$$

factorization means schematically

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\langle \mathcal O_1\mathcal O_2\rangle\langle \mathcal O_3\mathcal O_4\rangle
+\text{permutations}+O(N^{-p}).
$$

In many matrix-like gauge-theory normalizations, connected single-trace four-point functions scale as $1/N^2$. The exponent is convention-dependent, so this page writes $p$.

Factorization implies that the leading four-point function is generalized free. This does not make the full CFT trivial. It says that connected interactions are suppressed in this sector at leading large $N$.

## Single-trace and double-trace data

Large-$N$ language distinguishes several operator types.

| Operator type | CFT meaning | AdS meaning |
|---|---|---|
| identity | vacuum contribution | empty AdS |
| single-trace | elementary large-$N$ primary | one-particle bulk field |
| double-trace | composite of two single-trace operators | two-particle state |
| multi-trace | composite of several single-trace operators | multi-particle state |
| stress tensor | conserved spin-two operator | graviton |
| conserved current | global-symmetry current | bulk gauge field |

For two scalar single-trace operators $\mathcal O_1$ and $\mathcal O_2$, the double-trace family is

$$
[\mathcal O_1\mathcal O_2]_{n,\ell}.
$$

At leading large $N$,

$$
\Delta_{n,\ell}^{(0)}=\Delta_1+\Delta_2+2n+\ell.
$$

At subleading order,

$$
\Delta_{n,\ell}=\Delta_{n,\ell}^{(0)}+\frac{1}{N^p}\gamma_{n,\ell}^{(1)}+\cdots .
$$

The anomalous dimension $\gamma_{n,\ell}^{(1)}$ is one of the main observables of large-$N$ analytic bootstrap.

## Crossing at first subleading order

At order $1/N^p$, the reduced correlator has a correction

$$
\mathcal G(u,v)=\mathcal G_{\rm GFF}(u,v)+\frac{1}{N^p}\mathcal G^{(1)}(u,v)+\cdots .
$$

The direct-channel double-trace contribution expands as

$$
a_{n,\ell}G_{\Delta_{n,\ell},\ell}
=a_{n,\ell}^{(0)}G_{\Delta_{n,\ell}^{(0)},\ell}
+\frac{1}{N^p}a_{n,\ell}^{(0)}
\left[
\delta a_{n,\ell}^{(1)}G_{\Delta_{n,\ell}^{(0)},\ell}
+
\gamma_{n,\ell}^{(1)}\partial_\Delta G_{\Delta,\ell}\big|_{\Delta=\Delta_{n,\ell}^{(0)}}
\right]+\cdots .
$$

The derivative term generates logarithms in cross-ratio space. Therefore the logarithmic part of $\mathcal G^{(1)}$ determines $\gamma_{n,\ell}^{(1)}$. The non-logarithmic part determines OPE coefficient corrections, up to contact-term and mixing subtleties.

## Exchange and contact terms

If the OPE $\mathcal O\times\mathcal O$ contains a single-trace operator $\mathcal X$, then $\mathcal X$ exchange contributes to $\mathcal G^{(1)}$. At large spin, it gives

$$
\gamma_{n,\ell}^{(X)}\sim \frac{1}{J^{\tau_X}},
\qquad
\tau_X=\Delta_X-\ell_X.
$$

Examples include stress-tensor exchange, current exchange, scalar exchange, and higher-spin single-trace exchange.

A large-$N$ CFT can also have connected four-point data not generated by exchange of a light single-trace operator. In AdS, these are contact Witten diagrams. In Mellin space, contact interactions are polynomials:

$$
M_{\rm contact}(s,t)=c_0+c_1(s^2+t^2+u_M^2)+\cdots .
$$

The degree of the polynomial reflects the number of derivatives in the bulk interaction. Thus

$$
\text{AdS locality}\quad\Longleftrightarrow\quad
\text{controlled Mellin growth and structured double-trace data}.
$$

## Mellin and inversion organization

Mellin space packages large-$N$ crossing by writing

$$
M(s,t)=M_{\rm exchange}(s,t)+M_{\rm contact}(s,t).
$$

Exchange terms have physical poles. Contact terms are polynomials. Crossing symmetrizes the variables.

Lorentzian inversion gives a complementary route. Starting from the double discontinuity of $\mathcal G^{(1)}$, one computes

$$
c^{(1)}(\Delta,J)
$$

and extracts double-trace anomalous dimensions and OPE corrections from pole shifts and residues. The inversion perspective makes spin analyticity explicit and separates physical double discontinuities from contact ambiguities.

## Mixing and degeneracy

Large-$N$ spectra are full of degeneracies. Several double-trace operators can have the same leading dimension and spin. At order $1/N^p$, one must diagonalize an anomalous-dimension matrix

$$
\Gamma_{AB}(n,\ell).
$$

The physical anomalous dimensions are eigenvalues, and the physical operators are eigenvectors.

A single correlator may see only weighted averages of anomalous dimensions. To fully diagonalize mixing, one often needs a matrix of correlators involving several external operators.

## Loop-level large-N bootstrap

At the next order, large-$N$ bootstrap becomes loop-level. If tree-level corrections are order $1/N^p$, then loop data often appear at order

$$
\frac{1}{N^{2p}}.
$$

In AdS, this corresponds to one-loop Witten diagrams. In CFT, loop-level double discontinuities are often determined by products of tree-level anomalous dimensions and OPE coefficients. Lorentzian inversion can reconstruct much of the loop-level correlator from these cuts, up to contact-term or subtraction ambiguities.

## Sparse spectra

A large-$N$ CFT is not automatically holographic in the Einstein-gravity sense. For an Einstein-like local bulk dual, one usually needs a sparse low-dimension single-trace spectrum, especially a gap to higher-spin single-trace operators:

$$
\Delta_{\rm gap}\gg1.
$$

If many higher-spin single-trace operators are light, the bulk dual is stringy or higher-spin-like at low scales. Regge behavior and Mellin growth are then very different.

Large $N$ is the start of the story. Sparseness and Regge behavior decide what kind of story it is.

## Common pitfalls

**Do not equate large $N$ with weak coupling.** Factorization suppresses connected correlators, but individual operator dimensions can still be strongly coupled.

**Do not assume every large-$N$ CFT has an Einstein gravity dual.** Sparseness and a higher-spin gap are additional assumptions.

**Do not ignore mixing.** Degenerate double-trace families require anomalous-dimension matrices.

**Do not treat contact terms as arbitrary decoration.** They encode local AdS interactions and are constrained by crossing, Regge behavior, and EFT power counting.

**Do not quote double-trace anomalous dimensions without specifying normalization and order in $1/N$.** Conventions matter.

**Do not extrapolate large-spin data blindly to spin zero.** Low spin can contain ambiguities and strong mixing.

## Relations to other pages

This page follows [Polyakov Bootstrap](/cft-bootstrap/analytic-bootstrap/polyakov-bootstrap/) and prepares [Tauberian and Asymptotic Methods](/cft-bootstrap/analytic-bootstrap/tauberian-and-asymptotic-methods/) and [Analytic-Numerical Bridges](/cft-bootstrap/analytic-bootstrap/analytic-numerical-bridges/).

It also connects to [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/), [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/), and [Double Discontinuity](/cft-bootstrap/analytic-bootstrap/double-discontinuity/).

For physics context, see [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/), [Gauge-Theory CFTs](/cft-bootstrap/higher-dimensional-cft/gauge-theory-cfts/), and [Holographic CFT](/cft-bootstrap/holographic-cft/).

## Research status

Large-$N$ analytic bootstrap is established for tree-level perturbations around generalized free fields, including contact and exchange Witten diagrams, Mellin amplitudes, and large-spin anomalous dimensions.

Active research studies loop-level reconstruction, double-trace mixing, Regge-subtracted dispersion relations, stringy corrections, supersymmetric holographic correlators, spinning external operators, finite-spin ambiguities, and nonperturbative constraints on the emergence of local AdS physics.

## Exercises

### Exercise 1

Explain why generalized free field appears at leading order in many large-$N$ CFTs.

<details><summary><strong>Solution</strong></summary>

Large-$N$ factorization says that connected correlators of normalized single-trace operators are suppressed by powers of $1/N$. Therefore the leading four-point function is a sum of products of two-point functions. This is exactly the generalized-free-field structure. Interactions appear in the connected part at subleading order.

</details>

### Exercise 2

What is the leading large-$N$ dimension of $[\mathcal O_1\mathcal O_2]_{n,\ell}$?

<details><summary><strong>Solution</strong></summary>

At leading order,

$$
\Delta_{n,\ell}^{(0)}=\Delta_1+\Delta_2+2n+\ell.
$$

At subleading order this receives anomalous corrections:

$$
\Delta_{n,\ell}=\Delta_{n,\ell}^{(0)}+\frac{1}{N^p}\gamma_{n,\ell}^{(1)}+\cdots .
$$

</details>

### Exercise 3

Why do contact Witten diagrams become polynomial Mellin amplitudes?

<details><summary><strong>Solution</strong></summary>

A contact Witten diagram has no internal propagator, so it has no exchange pole. Derivatives in the local AdS interaction translate into powers of Mellin variables. Therefore a non-derivative contact term gives a constant Mellin amplitude, while higher-derivative contact interactions give higher-degree polynomials.

</details>

### Exercise 4

Why can a single four-point function fail to determine all double-trace anomalous dimensions when mixing is present?

<details><summary><strong>Solution</strong></summary>

If several double-trace operators have the same quantum numbers and degenerate mean-field dimensions, interactions produce an anomalous-dimension matrix. A single correlator may see only weighted averages of its eigenvalues. To diagonalize the matrix, one often needs several correlators involving different external operators.

</details>

## References

- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, “Holography from conformal field theory,” *Journal of High Energy Physics* **2009**.
- A. L. Fitzpatrick, J. Kaplan, J. Penedones, S. Raju, and B. C. van Rees, “A natural language for AdS/CFT correlators,” *Journal of High Energy Physics* **2011**.
- J. Penedones, “Writing CFT correlation functions as AdS scattering amplitudes,” *Journal of High Energy Physics* **2011**.
- L. F. Alday, “Large spin perturbation theory for conformal field theories,” *Physical Review Letters* **119** (2017).
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- D. Meltzer, E. Perlmutter, and A. Sivaramakrishnan, “Unitarity methods in AdS/CFT,” *Journal of High Energy Physics* **2020**.

## Version history

- 2026-07-01: First polished draft. Added large-$N$ factorization, mean-field double traces, subleading crossing, single-trace exchange, contact terms, Mellin and inversion organization, mixing, loop-level comments, sparse-spectrum criteria, exercises, and references.
