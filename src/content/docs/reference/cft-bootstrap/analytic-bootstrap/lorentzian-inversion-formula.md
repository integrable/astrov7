---
title: "Lorentzian Inversion Formula"
description: "How the Lorentzian inversion formula reconstructs CFT data as a function of spin from double discontinuities of four-point functions."
sidebar:
  label: "Lorentzian Inversion Formula"
  order: 5
level: Advanced
status: "Polished draft"
source: "Caron-Huot 2017; Simmons-Duffin TASI lectures; Poland, Rychkov, and Vichi 2019; analytic bootstrap literature."
topics:
  - Lorentzian inversion formula
  - analytic conformal bootstrap
  - double discontinuity
  - large spin
  - crossing symmetry
canonicalTopics:
  - lorentzian-inversion-formula
  - double-discontinuity-inversion
  - analyticity-in-spin
researchStatus:
  established:
    - "The Lorentzian inversion formula reconstructs CFT data at sufficiently large spin from the double discontinuity of a four-point function under suitable Regge-boundedness assumptions."
  active:
    - "Current work extends inversion methods to spinning correlators, defects, thermal systems, finite-spin subtleties, holographic loops, nonunitary cases, and dispersion-relation approaches."
---

## Summary

The **Lorentzian inversion formula** is a central tool of modern analytic bootstrap. It reconstructs CFT data as a function of spin from a Lorentzian object called the **double discontinuity** of a four-point function.

In a schematic scalar setup, the formula says that a partial-wave coefficient

$$
c(\Delta,J)
$$

can be obtained from an integral of the form

$$
c(\Delta,J)
\sim
\int dz\,d\bar z\;\mu(z,\bar z)\,G_{J+d-1,\Delta-d+1}(z,\bar z)\,
\operatorname{dDisc}\mathcal G(z,\bar z),
$$

up to convention-dependent normalization and channel choices. The poles of $c(\Delta,J)$ in $\Delta$ encode operator dimensions and OPE coefficients:

$$
c(\Delta,J)\sim \frac{a_{\mathcal O}}{\Delta_{\mathcal O}-\Delta}
\quad\text{near an exchanged operator.}
$$

The formula systematizes the lightcone bootstrap. Instead of matching singularities by hand, one integrates a positive Lorentzian discontinuity against a known kernel. This explains why large-spin CFT data are analytic in spin and why crossed-channel low-twist operators determine direct-channel double-twist anomalous dimensions.

The slogan is

$$
\text{CFT data}=\text{Lorentzian integral of double discontinuities}.
$$

## Prerequisites

Read [Anomalous Dimensions from Crossing](/cft-bootstrap/analytic-bootstrap/anomalous-dimensions-from-crossing/), [Large-Spin Perturbation Theory](/cft-bootstrap/analytic-bootstrap/large-spin-perturbation-theory/), and [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/) first.

You should know scalar conformal blocks, crossing symmetry, the lightcone limit, and the idea that poles in a spectral parameter can encode operator dimensions and OPE coefficients.

Some comfort with Lorentzian analytic continuation, branch cuts, and contour deformation is helpful. The main physics can be understood before mastering the full derivation.

## Core idea

Euclidean four-point functions have OPE expansions in different channels. Lorentzian continuation reveals branch cuts associated with operator ordering and causal singularities. The double discontinuity isolates the part of the correlator that carries physical crossed-channel information in a positive way.

The inversion formula says that this double discontinuity determines the direct-channel CFT data, at least for spins above a threshold fixed by Regge behavior.

The conceptual chain is

$$
\text{crossed-channel operator content}
\quad\to\quad
\operatorname{dDisc}\mathcal G
\quad\to\quad
c(\Delta,J)
\quad\to\quad
\{\Delta_{\mathcal O},a_{\mathcal O}\}.
$$

This makes analytic bootstrap feel like a dispersion relation. Singularities and discontinuities determine expansion data.

The formula is powerful because it avoids guessing an infinite tower of double-twist operators. The tower appears automatically as poles of the inverted function.

## Setup and conventions

Consider identical scalar primaries $\phi$ of dimension $\Delta_\phi$. The four-point function is

$$
\langle\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}\mathcal G(z,\bar z),
$$

with

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

A Euclidean conformal block expansion has the form

$$
\mathcal G(z,\bar z)=\sum_{\mathcal O}a_{\mathcal O}G_{\Delta,J}(z,\bar z),
$$

where $J$ denotes spin and

$$
a_{\mathcal O}=\lambda_{\phi\phi\mathcal O}^2
$$

for identical scalar external operators in a unitary normalization.

The inversion formula constructs a function

$$
c(\Delta,J)
$$

whose poles in $\Delta$ reproduce these data. The precise normalization of $c$ depends on the chosen conformal partial waves, shadow conventions, and block normalization.

## From Euclidean inversion to Lorentzian inversion

Ordinary Euclidean partial-wave expansions resemble harmonic analysis. One expands a correlator in a basis of conformal partial waves and inverts using orthogonality.

The Lorentzian inversion formula is sharper. By deforming contours and using causal analyticity, the Euclidean inversion integral can be rewritten in terms of Lorentzian double discontinuities. This removes many analytic terms that do not carry the same physical information and produces a formula with positivity properties.

Schematically:

$$
\text{Euclidean partial-wave inversion}
\quad\Longrightarrow\quad
\text{Lorentzian dDisc inversion}.
$$

This move is analogous to replacing a Euclidean expansion coefficient by a dispersion integral over a discontinuity. The discontinuity knows about branch cuts created by operator products in Lorentzian signature.

The resulting formula is not merely a computational shortcut. It reveals analyticity in spin and explains why large-spin perturbation theory works.

## Double discontinuity

The double discontinuity is a specific combination of analytic continuations around a branch point. Around a channel such as $\bar z=1$, one can define schematically

$$
\operatorname{dDisc}[\mathcal G]
=\mathcal G-\frac12\mathcal G^{\circlearrowleft}-\frac12\mathcal G^{\circlearrowright},
$$

where $\mathcal G^{\circlearrowleft}$ and $\mathcal G^{\circlearrowright}$ denote the two continuations around the branch cut.

For a simple power,

$$
(1-\bar z)^a,
$$

the double discontinuity is proportional to

$$
\sin^2(\pi a)(1-\bar z)^a,
$$

up to the convention for phases and channel normalization.

This has two important consequences. First, analytic pieces with no branch cut may be killed by the double discontinuity. Second, nontrivial exchanged operators with branch cuts contribute positively in unitary settings.

The double discontinuity is therefore the part of the correlator that the inversion formula really wants. It is the crunchy Lorentzian filling, not the decorative Euclidean pastry.

## The schematic formula

For scalar four-point functions, the Lorentzian inversion formula has the schematic structure

$$
c(\Delta,J)=\frac{\kappa_{\Delta+J}}{4}
\int_0^1 dz\,d\bar z\;\mu(z,\bar z)
G_{J+d-1,\Delta-d+1}(z,\bar z)
\operatorname{dDisc}\mathcal G(z,\bar z),
$$

where:

| Symbol | Meaning |
|---|---|
| $c(\Delta,J)$ | meromorphic function whose poles encode CFT data |
| $\kappa_{\Delta+J}$ | normalization factor |
| $\mu(z,\bar z)$ | known measure depending on dimension and conventions |
| $G_{J+d-1,\Delta-d+1}$ | inversion kernel, related to a shadow-like conformal block |
| $\operatorname{dDisc}\mathcal G$ | double discontinuity in the crossed channel |

The exact formula has channel labels and convention-dependent factors. This page emphasizes the structure; detailed calculations should specify the normalization before quoting coefficients.

## Poles and CFT data

The output $c(\Delta,J)$ is a function of complex $\Delta$ and spin $J$. Physical operators appear as poles in $\Delta$ at fixed spin:

$$
\Delta=\Delta_{\mathcal O}(J).
$$

Near a simple pole,

$$
c(\Delta,J)\sim \frac{a_{\mathcal O}(J)}{\Delta_{\mathcal O}(J)-\Delta}.
$$

The pole location gives the operator dimension. The residue gives the OPE coefficient squared, up to normalization.

For double-twist families, the poles occur near

$$
\Delta_{n,J}=2\Delta_\phi+2n+J+\gamma_{n,J}.
$$

Expanding the pole location at large $J$ gives the anomalous dimension

$$
\gamma_{n,J}.
$$

Thus the inversion formula converts a correlator into spectral data.

## Analyticity in spin

One of the biggest lessons of the inversion formula is **analyticity in spin**. Under suitable Regge-boundedness assumptions, CFT data are organized by functions analytic in spin for

$$
J>J_0,
$$

where the threshold is often $J_0=1$ in standard scalar setups.

This means that large-spin families are not just informal sequences. They are values of analytic trajectories. The inversion formula constructs those trajectories.

This is why large-spin perturbation theory is so systematic. Once data are analytic in $J$, a crossed-channel low-twist expansion produces asymptotic series along a trajectory.

Finite spin remains subtle. Operators at spin zero or spin one may not be fully determined by the same formula without additional input, depending on Regge behavior and subtractions.

## Regge boundedness and low-spin ambiguities

The inversion formula requires assumptions about Lorentzian high-energy behavior, often called Regge behavior. Roughly, the correlator must not grow too quickly in an appropriate Lorentzian limit.

If the Regge behavior is good enough, the contour deformation used in the derivation has no dangerous boundary term. If not, subtractions or extra low-spin data may be needed.

The result is that the formula is most reliable above a spin threshold. A common shorthand is:

$$
\text{inversion determines CFT data for sufficiently large spin.}
$$

This does not mean low spin is hopeless. It means low spin can receive contact-term-like or subtraction ambiguities not visible in the same double-discontinuity integral.

In holographic language, this is related to the fact that local contact interactions can affect finitely many low spins in certain Mellin-space descriptions.

## Positivity

In unitary CFTs, the double discontinuity has positivity properties. For identical scalar correlators, one can often interpret it as a positive quantity in a suitable Lorentzian regime.

This positivity is crucial. It underlies:

- sign constraints on anomalous dimensions;
- convexity properties of twist trajectories;
- causality constraints;
- bootstrap bounds related to averaged null energy;
- the reliability of inversion as a reconstruction from physical spectral data.

The double discontinuity is not merely a technical discontinuity. It is a positivity-preserving object adapted to Lorentzian CFT.

This is one reason the Lorentzian inversion formula sits at the center of modern analytic bootstrap.

## Recovering lightcone bootstrap

Take the inversion formula and evaluate it in a regime where the crossed-channel double discontinuity is dominated by one low-twist operator. Then the integral can be estimated at large spin.

The result is exactly the large-spin structure found by lightcone bootstrap:

$$
\gamma_{n,J}^{(m)}\sim \frac{1}{J^{\tau_m}}.
$$

The identity contribution produces mean-field double-twist data. Non-identity low-twist operators shift pole locations and residues.

Thus:

$$
\text{lightcone bootstrap}
=\text{large-spin asymptotics of Lorentzian inversion}.
$$

The inversion formula gives a more systematic way to compute subleading terms and to understand which spin values are controlled.

## Holographic interpretation

In holographic CFTs, the inversion formula resembles a boundary version of a dispersion relation for AdS scattering. The double discontinuity plays a role analogous to an absorptive part or physical cut.

Bulk exchange diagrams produce characteristic double discontinuities. Inverting them gives anomalous dimensions of double-trace operators:

$$
[\mathcal O\mathcal O]_{n,J}.
$$

Loop diagrams produce more complicated double discontinuities, including products of tree-level data. Contact terms may have limited or subtle double discontinuity and can correspond to low-spin ambiguities or polynomial Mellin terms.

This makes the inversion formula a powerful tool for AdS effective field theory. It reconstructs bulk interaction data from boundary analytic structure.

## Relation to numerical bootstrap

The numerical bootstrap works with Euclidean crossing, positivity, and finite-dimensional derivative truncations. The Lorentzian inversion formula works with analytic continuation, double discontinuities, and spin analyticity.

They complement each other:

| Numerical bootstrap | Lorentzian inversion |
|---|---|
| rigorous-looking finite-cutoff bounds | asymptotic analytic reconstruction |
| works well for low-lying spectra with assumptions | controls large-spin trajectories |
| produces islands and kinks | explains large-spin tails and convexity |
| needs spin truncation or high-spin treatment | supplies high-spin asymptotic data |
| computationally intensive | analytically powerful but assumption-sensitive |

Analytic inversion can improve numerical setups by supplying large-spin information and explaining extremal spectra. Numerical data can test finite-spin extrapolations of analytic formulas.

## Practical workflow

A typical inversion-based calculation follows this pattern:

1. Choose the four-point function and channel.
2. Identify the crossed-channel contribution to the double discontinuity.
3. Insert it into the inversion formula.
4. Evaluate or approximate the integral.
5. Locate poles in $\Delta$.
6. Extract pole locations and residues.
7. Interpret pole shifts as anomalous dimensions.
8. Check spin threshold and Regge assumptions.
9. Compare with lightcone expansion, perturbation theory, or holographic diagrams.
10. Track normalization conventions before quoting coefficients.

The integral can be simple for a single exchanged conformal block and difficult for loops or spinning correlators. But the conceptual output is always the same: poles are operators.

## Common pitfalls

**Do not treat the schematic formula as convention-free.** Measures, kernels, normalization factors, and channel labels vary.

**Do not ignore Regge assumptions.** The inversion formula can require subtractions or fail below a spin threshold if the correlator grows too fast.

**Do not assume low spin is automatically determined.** Spin zero and spin one often require special care.

**Do not confuse discontinuity with double discontinuity.** The double discontinuity is a specific combination with special positivity properties.

**Do not forget shadow conventions.** The kernel uses a block with transformed labels; different presentations hide this differently.

**Do not say identity exchange is always simply captured by dDisc.** Disconnected and analytic pieces can require separate treatment depending on conventions.

**Do not quote residues as OPE coefficients without matching normalization.** Pole residues depend on the definition of $c(\Delta,J)$ and the block normalization.

## Relations to other pages

This page follows [Anomalous Dimensions from Crossing](/cft-bootstrap/analytic-bootstrap/anomalous-dimensions-from-crossing/) and prepares [Double Discontinuity](/cft-bootstrap/analytic-bootstrap/double-discontinuity/) and [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/).

It also connects to [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/) and [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/) because inversion is especially useful in holographic large-$N$ CFTs.

For the numerical side, see [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) and [Error Bars and Reliability](/cft-bootstrap/numerical-bootstrap/error-bars-and-reliability/), where large-spin analytic data help interpret finite numerical systems.

## Research status

The Lorentzian inversion formula is established as a central theorem and method in analytic conformal bootstrap under standard assumptions. It explains analyticity in spin and systematizes large-spin perturbation theory.

Active research extends inversion methods to spinning external operators, supersymmetric correlators, defects and boundaries, thermal CFT, nonunitary theories, loop-level holography, Regge-subtracted dispersion relations, and sharper finite-spin reconstruction.

## Exercises

### Exercise 1

What information is contained in a pole of $c(\Delta,J)$?

<details><summary><strong>Solution</strong></summary>

A pole in $\Delta$ at fixed spin $J$ indicates a physical primary operator. If

$$
c(\Delta,J)\sim \frac{a_{\mathcal O}}{\Delta_{\mathcal O}-\Delta},
$$

then the pole location gives the operator dimension $\Delta_{\mathcal O}$, and the residue gives the squared OPE coefficient $a_{\mathcal O}$ up to normalization conventions.

</details>

### Exercise 2

Why is the double discontinuity useful rather than an ordinary discontinuity?

<details><summary><strong>Solution</strong></summary>

The double discontinuity is a special combination of analytic continuations around a branch cut. It removes many analytic or contact-like contributions and has positivity properties in unitary Lorentzian CFT. These properties make it the natural input for the inversion formula and for deriving sign and large-spin constraints.

</details>

### Exercise 3

How does the Lorentzian inversion formula recover the lightcone bootstrap result $\gamma\sim J^{-\tau_m}$?

<details><summary><strong>Solution</strong></summary>

If the crossed-channel double discontinuity is dominated by an operator of twist $\tau_m$, then the inversion integral can be evaluated at large spin using the lightcone region. The resulting poles corresponding to double-twist operators are shifted by an amount proportional to

$$
J^{-\tau_m}.
$$

This reproduces the lightcone-bootstrap scaling of anomalous dimensions.

</details>

### Exercise 4

Why can low spin require extra care in the inversion formula?

<details><summary><strong>Solution</strong></summary>

The derivation uses contour deformation and Regge-boundedness assumptions. If the correlator has insufficiently bounded growth, boundary terms or subtractions can affect low spins. Even when the formula works above a threshold such as $J>1$, spin zero or spin one may require additional input or may contain ambiguities not fixed by the same double-discontinuity integral.

</details>

### Exercise 5

Explain the holographic meaning of the double discontinuity in broad terms.

<details><summary><strong>Solution</strong></summary>

In holographic CFTs, the double discontinuity is analogous to an absorptive or physical-cut part of an AdS scattering process. Exchange and loop diagrams produce double discontinuities. Inverting them reconstructs anomalous dimensions and OPE coefficients of double-trace operators, which correspond to two-particle states in AdS.

</details>

## References

- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- A. L. Fitzpatrick, J. Kaplan, D. Poland, and D. Simmons-Duffin, “The analytic bootstrap and AdS superhorizon locality,” *Journal of High Energy Physics* **2013**.
- L. F. Alday, “Large spin perturbation theory for conformal field theories,” *Physical Review Letters* **119** (2017).

## Version history

- 2026-07-01: First polished draft. Added schematic inversion formula, double-discontinuity interpretation, poles and residues, analyticity in spin, Regge caveats, positivity, lightcone recovery, holographic and numerical-bootstrap connections, exercises, and references.
