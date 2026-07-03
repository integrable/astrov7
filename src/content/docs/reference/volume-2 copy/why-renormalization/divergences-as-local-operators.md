---
title: "Divergences as Local Operators"
description: "How ultraviolet divergences are classified as coefficients of local operators, and why this is the organizing principle behind counterterms and EFT."
sidebar:
  label: "Divergences as Local Operators"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §§17–19 and 27–29; Coleman, Renormalization and Symmetry; Weinberg Vol. I ch. 12; Weinberg Vol. II ch. 18; Schwartz chs. 19–23; Wilson and Kogut 1974; Zinn-Justin, renormalization and short-distance expansion chapters."
topics:
  - ultraviolet divergences
  - local operators
  - counterterms
  - operator bases
  - power counting
  - effective field theory
canonicalTopics:
  - local-counterterm
  - divergent-effective-action
  - operator-basis
  - renormalizability
  - effective-field-theory
researchStatus:
  established:
    - "The divergent part of a local QFT can be expressed as a sum of local operators consistent with the regulator, fields, and symmetries, after subdivergences are treated."
  active:
    - "The same local-operator logic appears in modern EFT matching, gauge-theory cohomology, curved-spacetime renormalization, defect renormalization, and nonperturbative formulations of QFT."
---

## Summary

The phrase “a diagram diverges” is too crude. A divergence is not just a large number floating in the calculation. In a local QFT, an ultraviolet divergence has the form of a **coefficient multiplying a local operator**.

Schematically, the divergent part of the effective action has the form

$$
\Gamma_{\text{div}}
=\sum_i C_i^{\text{div}}(\Lambda,\epsilon,\mu)
\int d^d x\,\mathcal O_i(x),
$$

where the operators $\mathcal O_i$ are local expressions built from fields and derivatives, and the coefficients $C_i^{\text{div}}$ depend on the regulator and the subtraction convention.

This statement is the conceptual engine behind counterterms. If loop corrections generate

$$
C_i^{\text{div}}\int d^d x\,\mathcal O_i(x),
$$

then the bare Lagrangian must contain a counterterm

$$
-C_i^{\text{div}}\int d^d x\,\mathcal O_i(x)
$$

or, more carefully, a coefficient whose regulator dependence cancels the divergence after the renormalization condition is imposed.

The slogan is

$$
\text{UV divergence}
\quad=\quad
\text{regulator-dependent coefficient of a local operator}.
$$

:::note[The important upgrade]
The question is not “does the integral diverge?” The better question is “which local operator does the divergent part multiply?” Once you ask that question, renormalization starts looking like a classification problem rather than a ritual for hiding infinities.
:::

## Prerequisites

You should have read [Short-Distance Singularities](/renormalization-rg-eft/why-renormalization/short-distance-singularities/) and [Loops and Locality](/renormalization-rg-eft/why-renormalization/loops-and-locality/). The main inputs are:

- coincident products of local fields are singular;
- hard loop momenta produce polynomial dependence on external momenta;
- polynomial dependence in momentum space is local in position space.

You should also keep the volume [Conventions and Notation](/renormalization-rg-eft/conventions/) nearby for the distinction between a cutoff $\Lambda$, a renormalization scale $\mu$, and a physical scale $Q$.

## Core idea

A local QFT is built from local operators. A general action can be written as

$$
S=\sum_i g_i\int d^d x\,\mathcal O_i(x),
$$

where $g_i$ are couplings and $\mathcal O_i$ are local operators. Perturbation theory then asks how correlation functions and amplitudes depend on these couplings.

Because loop diagrams probe arbitrarily short distances, their ultraviolet parts can change the coefficients of local operators. They can renormalize operators already present in the Lagrangian, and they can reveal that additional operators are needed for a closed description at the desired accuracy.

Thus renormalization is not merely

$$
\infty-\infty=\text{finite}.
$$

It is the statement that short-distance sensitivity has a local expansion:

$$
\text{short-distance physics}
\longrightarrow
\sum_i \text{coefficient}_i\times \text{local operator}_i.
$$

The allowed operators are constrained by locality, spacetime symmetry, internal symmetry, gauge redundancy or BRST symmetry, discrete symmetries, and the choice of degrees of freedom.

## Setup and conventions

We use the mostly-minus Lorentzian convention in the volume. When displaying ultraviolet power counting, Euclidean notation is often cleaner. Nothing essential depends on that choice.

A regulator is always assumed when divergent expressions are written. We use $\Lambda$ for a hard cutoff and $d=4-2\epsilon$ for dimensional regularization near four dimensions. The renormalization scale $\mu$ is not a physical cutoff; it labels the convention used to define renormalized parameters.

A local operator is a field expression at one spacetime point, built from fields and finitely many derivatives:

$$
\mathcal O(x)
=\phi^4(x),
\qquad
\partial_\mu\phi(x)\partial^\mu\phi(x),
\qquad
\bar\psi(x)\gamma^\mu D_\mu\psi(x),
\qquad
F_{\mu\nu}(x)F^{\mu\nu}(x),
$$

and so on. Integrating a local operator over spacetime gives a local term in the action.

Operators that differ by a total derivative are usually identified inside the action, assuming boundary terms do not contribute:

$$
\int d^d x\,\partial_\mu V^\mu=0.
$$

Operators proportional to the equations of motion are subtler. They are often redundant for on-shell observables and can be moved by field redefinitions, but they may still appear in off-shell Green functions, composite-operator renormalization, and intermediate operator bases.

## Divergent effective action

The cleanest organizational object is the effective action. Let $\varphi$ denote a background or classical field. The one-particle-irreducible effective action has an expansion

$$
\Gamma[\varphi]
=S[\varphi]+\Gamma^{(1)}[\varphi]+\Gamma^{(2)}[\varphi]+\cdots,
$$

where $\Gamma^{(L)}$ is the $L$-loop contribution.

For a local QFT, the ultraviolet divergent part has the form

$$
\Gamma_{\text{div}}[\varphi]
=\sum_i C_i^{\text{div}}\int d^d x\,\mathcal O_i(\varphi,\partial\varphi,\ldots;x).
$$

This is a local functional of the background field. The finite part of $\Gamma$ is not generally local. It contains logarithms, branch cuts, thresholds, and other nonlocal information. The locality statement is about the UV divergent part, after smaller divergent subgraphs have been subtracted.

Counterterms are chosen so that

$$
S_{\text{bare}}=S_{\text{ren}}+S_{\text{ct}},
$$

with

$$
S_{\text{ct}}
=-\Gamma_{\text{div}}+\text{finite local convention-dependent terms}
$$

in a minimal subtraction style of language. Other schemes choose the finite local terms differently.

The counterterm action is therefore not arbitrary. It is a local functional drawn from the same operator space that the divergent effective action lives in.

## Correlation-function viewpoint

The same statement appears directly in correlation functions. Suppose two local operators approach one another. The operator product expansion says, schematically,

$$
\mathcal O_A(x)\mathcal O_B(0)
\sim
\sum_C C_{AB}{}^C(x)\mathcal O_C(0)
\qquad x\to0.
$$

The coefficient functions $C_{AB}{}^C(x)$ can be singular. If a perturbative calculation integrates over the separation $x$, a singular coefficient can produce a UV divergence.

For example, if in $d$ dimensions

$$
C_{AB}{}^C(x)\sim \frac{1}{|x|^d},
$$

then the short-distance integral behaves as

$$
\int_{a<|x|<R} d^d x\,\frac{1}{|x|^d}
\sim
\Omega_{d-1}\log\frac{R}{a},
$$

where $a$ is a short-distance cutoff and $\Omega_{d-1}$ is the area of the unit $(d-1)$-sphere.

The divergent result multiplies $\mathcal O_C(0)$. Once integrated over the center-of-mass point, it becomes a divergent coefficient of

$$
\int d^d x\,\mathcal O_C(x).
$$

This is the position-space version of “divergences are local operators.” The OPE makes it especially transparent: singular short-distance products close onto local operators.

## Momentum-space viewpoint

Momentum space says the same thing in a different accent. A UV divergent loop subgraph can be expanded in external momenta. The divergent part is polynomial:

$$
\mathcal A_{\text{div}}(p_i)
=C_0+C_1^{\mu}p_{1\mu}+C_2^{\mu\nu}p_{1\mu}p_{2\nu}+\cdots.
$$

A polynomial in momenta Fourier transforms to derivatives of delta functions. For example,

$$
1\quad\longleftrightarrow\quad \delta^{(d)}(x),
$$

and

$$
p^2\quad\longleftrightarrow\quad -\partial^2\delta^{(d)}(x).
$$

So a divergent polynomial in momenta is a contact term in position space. Contact terms are generated by local terms in the action.

Nonpolynomial structures are different. A term like

$$
\log\frac{-p^2-i\epsilon}{\mu^2}
$$

or a threshold branch cut cannot be canceled by changing a finite number of local operators. Such terms encode finite-distance propagation and physical intermediate states. Renormalization subtracts the local UV ambiguity; it does not erase the nonlocal physics.

## The phi-four operator basis near four dimensions

Consider one real scalar field with $\mathbb Z_2$ symmetry,

$$
\phi\mapsto -\phi,
$$

in four spacetime dimensions. The local operators of engineering dimension at most four include

| Operator | Dimension | Comment |
|---|---:|---|
| $1$ | $0$ | vacuum energy or cosmological constant term |
| $\phi^2$ | $2$ | mass operator |
| $\partial_\mu\phi\partial^\mu\phi$ | $4$ | kinetic operator or field normalization |
| $\phi^4$ | $4$ | quartic interaction |

The symmetry forbids odd powers such as $\phi$ and $\phi^3$. Lorentz invariance forbids uncontracted indices. Total derivatives can be dropped from the action.

The most general local Lagrangian using these operators is

$$
\mathcal L
= -\rho
+\frac12 Z\,\partial_\mu\phi\partial^\mu\phi
-\frac12 m^2\phi^2
-\frac{\lambda}{4!}\phi^4.
$$

The vacuum-energy term $\rho$ is often ignored in flat-space scattering because it cancels from normalized correlators, but it is a perfectly legitimate local counterterm. It matters in thermodynamics, curved spacetime, and gravity.

Operators of dimension greater than four are also allowed by the same symmetry:

$$
\phi^6,
\qquad
\phi^2\partial_\mu\phi\partial^\mu\phi,
\qquad
(\partial^2\phi)^2,
\qquad
\ldots
$$

In the old perturbatively renormalizable treatment of $\lambda\phi^4$ theory in four dimensions, only the finite list of dimension $\le4$ operators is needed as counterterms. In the EFT treatment, the higher-dimension operators are included too, organized by powers of a heavy scale.

## Example: the tadpole is a mass operator

In $\lambda\phi^4$ theory, the one-loop tadpole correction to the two-point function has the schematic form

$$
\Sigma_{\text{tad}}
\propto
\lambda\int\frac{d^d\ell}{(2\pi)^d}\frac{1}{\ell^2+m^2}
$$

in Euclidean notation. With a hard cutoff in four dimensions, the integral contains

$$
\int^{\Lambda}\frac{d^4\ell}{(2\pi)^4}\frac{1}{\ell^2+m^2}
=\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\log\frac{\Lambda^2+m^2}{m^2}
\right].
$$

The important structural fact is that the tadpole is independent of the external momentum. It has the same momentum dependence as a mass insertion. The corresponding local counterterm is therefore

$$
\mathcal L_{\text{ct}}\supset -\frac12\delta m^2\phi^2.
$$

The divergence is not merely “in the two-point diagram.” More precisely, it is a divergent coefficient multiplying the operator $\phi^2$.

## Example: the bubble is a quartic operator

The one-loop correction to the four-point function in the same theory contains a bubble integral. One channel has the schematic Euclidean form

$$
\mathcal A^{(1)}(p)
\propto
\lambda^2\int\frac{d^4\ell}{(2\pi)^4}
\frac{1}{(\ell^2+m^2)((\ell+p)^2+m^2)}.
$$

At large loop momentum,

$$
\frac{1}{(\ell^2+m^2)((\ell+p)^2+m^2)}
\sim
\frac{1}{\ell^4}+O\!\left(\frac{p}{\ell^5},\frac{m^2}{\ell^6},\frac{p^2}{\ell^6}\right).
$$

The leading term gives a logarithmic UV divergence in four dimensions:

$$
\int^\Lambda \frac{d^4\ell}{(2\pi)^4}\frac{1}{\ell^4}
\sim
\frac{1}{8\pi^2}\log\Lambda
$$

up to convention-dependent details of the cutoff. This leading divergent part is independent of the external momenta. It therefore has the same local structure as the original $\phi^4$ interaction.

The corresponding counterterm is

$$
\mathcal L_{\text{ct}}\supset -\frac{\delta\lambda}{4!}\phi^4.
$$

The next terms in the hard-momentum expansion carry powers of external momentum and correspond to higher-derivative local operators. In four-dimensional $\lambda\phi^4$ theory, those terms are not UV divergent at one loop. In a general EFT, such higher-derivative operators are not embarrassing; they are part of the expansion.

## Renormalizability as closure of an operator set

A theory is perturbatively renormalizable in the traditional sense if the divergences can be absorbed into a finite set of operators already included in the Lagrangian. In four dimensions, this usually means operators of engineering dimension at most four, together with symmetry constraints.

In scalar $\lambda\phi^4$ theory, the required counterterms are of the form

$$
1,
\qquad
\phi^2,
\qquad
\partial_\mu\phi\partial^\mu\phi,
\qquad
\phi^4.
$$

In QED, gauge invariance and Lorentz invariance restrict the counterterms to the familiar electron kinetic term, mass term, photon kinetic term, and charge interaction, plus gauge-fixing and possible vacuum terms. A photon mass term would be local, but it is not gauge invariant, so it is not an allowed counterterm in a gauge-preserving scheme.

In an EFT, the requirement is different. The Lagrangian contains infinitely many local operators consistent with symmetries:

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\le d}
+\sum_{\Delta_i>d}\frac{C_i(\mu)}{M^{\Delta_i-d}}\mathcal O_i.
$$

Loop divergences are still local operators. They are absorbed into the coefficients $C_i(\mu)$. Predictivity is maintained not by having finitely many operators in total, but by power counting: at any fixed order in $Q/M$, only finitely many operators contribute.

So “nonrenormalizable” never meant “not renormalizable by local counterterms.” It meant “not renormalizable using only a finite number of parameters if one insists on predictions at arbitrarily high energies.” EFT changes the question to a low-energy expansion, where the operator tower is a feature.

## Symmetry constraints

Locality tells us that UV divergences are local. Symmetry tells us which local terms are allowed.

For example, if the theory has a $\mathbb Z_2$ symmetry $\phi\mapsto-\phi$, then a divergence proportional to $\phi^3$ cannot appear if the regulator and subtraction scheme respect the symmetry. If a regulator breaks the symmetry, symmetry-violating local terms may appear temporarily, but they must be canceled by symmetry-restoring counterterms if the target theory is symmetric.

Gauge theories are the sharpest version of this lesson. A naive hard cutoff can obscure gauge invariance. Dimensional regularization is popular partly because it preserves many spacetime and gauge-theory structures more naturally. Even then, chiral gauge theories, $\gamma^5$, evanescent operators, and anomalies require careful treatment.

The general rule is:

$$
\Gamma_{\text{div}}
\in
\{\text{local functionals compatible with the quantum symmetries and anomalies}\}.
$$

An anomaly is precisely a case where a classical symmetry cannot be preserved by the quantum regulator and counterterms simultaneously. Then the symmetry does not constrain the quantum effective action in the naive classical way.

## Operator bases and redundancy

Saying that divergences are local operators is only the beginning. One still has to choose an operator basis.

Different-looking local expressions may be related by integration by parts. For example,

$$
\int d^d x\,\phi^3\partial^2\phi
=-3\int d^d x\,\phi^2\partial_\mu\phi\partial^\mu\phi
$$

up to boundary terms.

Other operators are related by field redefinitions or equations of motion. If the leading scalar equation of motion is

$$
\partial^2\phi+m^2\phi+\frac{\lambda}{3!}\phi^3=0,
$$

then an operator containing $\partial^2\phi$ can often be traded for operators with no $\partial^2\phi$, plus terms proportional to lower-dimension interactions. Such manipulations are safe for on-shell amplitudes when done consistently, but off-shell Green functions and composite-operator insertions may require a larger basis.

This is why serious EFT and operator-mixing calculations spend so much time on bases, redundancies, equations of motion, Fierz identities, Bianchi identities, and total derivatives. The physics is local; the technical work lies in choosing a basis and translating consistently between equivalent bases.

## Power counting as a search filter

Power counting estimates which local operators can appear as divergent counterterms. If a diagram has superficial degree of divergence $D$, then its overall UV divergence, if present, is polynomial in external momenta up to degree $D$:

$$
\mathcal A_{\text{div}}(p_i)
=\sum_{n\le D} C_n P_n(p_i,m).
$$

Here $P_n$ is a polynomial compatible with the tensor structure and symmetries. If $D<0$, the diagram is superficially convergent, although subdivergences may still appear inside it.

For a scalar two-point function in four dimensions:

| Divergent momentum structure | Local operator |
|---|---|
| constant | $\phi^2$ |
| $p^2$ | $\partial_\mu\phi\partial^\mu\phi$ |
| $p^4$ | $(\partial^2\phi)^2$ or equivalent higher-derivative operators |

For a four-point function:

| Divergent momentum structure | Local operator type |
|---|---|
| constant | $\phi^4$ |
| two powers of external momenta | $\phi^2(\partial\phi)^2$ or related dimension-six operators |
| four powers of external momenta | dimension-eight four-field derivative operators |

Power counting does not replace calculation. Symmetries may cancel terms. Tensor algebra may reduce structures. Subdivergences require recursive subtraction. But power counting tells us where to look.

## Local finite terms and scheme dependence

Divergent local terms must be canceled or absorbed. Finite local terms are conventional unless fixed by renormalization conditions or matching.

For example, after subtracting a logarithmic divergence, one may still choose whether the finite local part of the four-point amplitude is assigned to the coupling $\lambda(\mu)$ or left inside the loop remainder. Minimal subtraction, $\overline{\mathrm{MS}}$, momentum subtraction, and on-shell schemes make different choices.

Changing the scheme changes the finite local coefficients. It does not change the nonlocal part of the amplitude or properly computed observables.

This is why the operator viewpoint is so useful. A scheme is a convention for assigning local pieces between parameters and loop corrections. Nonlocal physics cannot be moved around in the same way.

## Common pitfalls

**Thinking every local divergence is a problem.** Local UV sensitivity is exactly what local QFT and EFT predict. The problem would be an uncancelable nonlocal UV divergence, which would indicate that the assumed local description is not closed.

**Forgetting the identity operator.** Vacuum energy is a local operator. It is often irrelevant for flat-space scattering, but not for thermodynamics or gravity.

**Confusing allowed by locality with allowed by symmetry.** A photon mass term is local. Gauge invariance forbids it in ordinary QED.

**Treating the operator basis as unique.** Integration by parts, equations of motion, field redefinitions, Fierz identities, and Bianchi identities can move terms between operators.

**Thinking EFT loses predictivity because infinitely many operators exist.** Predictivity comes from power counting. At a fixed order in $Q/M$, only finitely many coefficients are needed.

## Relations to other pages

[Short-Distance Singularities](/renormalization-rg-eft/why-renormalization/short-distance-singularities/) explains why coincident local products are singular. [Loops and Locality](/renormalization-rg-eft/why-renormalization/loops-and-locality/) explains why the hard part of a loop is polynomial in external momenta. This page turns that locality statement into the operator classification used by counterterms and EFT.

The next page, [Bare versus Renormalized](/renormalization-rg-eft/why-renormalization/bare-versus-renormalized/), explains how the coefficients of these local operators are split into bare parameters, renormalized parameters, and counterterms.

Later chapters use the same language in more specialized settings: Regularization and Counterterms classifies regulators and subtraction terms; Renormalized Perturbation Theory explains concrete schemes; Wilsonian Renormalization turns local operators into coordinates on theory space; Effective Field Theory treats the infinite tower of local operators as a controlled expansion.

## Research status

The basic locality of UV divergences is established and is one of the foundations of perturbative renormalization, BPHZ-type subtractions, Epstein–Glaser renormalization, Wilsonian RG, and EFT.

Active work refines this statement in technically rich settings: gauge-theory cohomology, evanescent operators, higher-loop EFT bases, curved-spacetime counterterms, defects and boundaries, nonlocal observables such as Wilson lines, and rigorous perturbative algebraic QFT.

## Exercises

### Exercise 1: Polynomial momentum dependence is a contact term

Let a two-point 1PI contribution in momentum space have divergent part

$$
\Gamma_{\text{div}}^{(2)}(p)=A+Bp^2,
$$

where $A$ and $B$ are regulator-dependent constants. Show that the corresponding position-space kernel is local.

<details><summary><strong>Solution</strong></summary>

Using the Fourier convention

$$
K(x-y)=\int\frac{d^d p}{(2\pi)^d}e^{ip\cdot(x-y)}\Gamma^{(2)}(p),
$$

we have

$$
\int\frac{d^d p}{(2\pi)^d}e^{ip\cdot(x-y)}=\delta^{(d)}(x-y),
$$

and

$$
\int\frac{d^d p}{(2\pi)^d}e^{ip\cdot(x-y)}p^2
=-\partial_x^2\delta^{(d)}(x-y).
$$

Therefore

$$
K_{\text{div}}(x-y)
=A\delta^{(d)}(x-y)-B\partial_x^2\delta^{(d)}(x-y).
$$

The kernel has support only at coincident points. It is local.

</details>

### Exercise 2: Identify the tadpole counterterm

In four-dimensional $\lambda\phi^4$ theory, suppose a one-loop two-point diagram contributes a divergent constant $\Sigma_{\text{div}}$ independent of external momentum. Which local operator does this divergence multiply?

<details><summary><strong>Solution</strong></summary>

A two-point contribution independent of external momentum has the same structure as a mass insertion. In the quadratic action, the mass term is

$$
-\frac12m^2\phi^2.
$$

The divergent constant can therefore be absorbed by

$$
\mathcal L_{\text{ct}}\supset -\frac12\delta m^2\phi^2,
$$

with $\delta m^2$ chosen according to the scheme. The divergence multiplies the local operator $\phi^2$.

</details>

### Exercise 3: Operators allowed by a scalar symmetry

For a real scalar field in four spacetime dimensions with $\mathbb Z_2$ symmetry $\phi\mapsto-\phi$, list the independent Lorentz-invariant local operators of engineering dimension at most four that can appear in the action, ignoring total derivatives.

<details><summary><strong>Solution</strong></summary>

The scalar has engineering dimension $[\phi]=1$ in four dimensions. The allowed $\mathbb Z_2$-even Lorentz scalars of dimension at most four are

$$
1,
\qquad
\phi^2,
\qquad
\partial_\mu\phi\partial^\mu\phi,
\qquad
\phi^4.
$$

A term $\phi\partial^2\phi$ is equivalent to $-\partial_\mu\phi\partial^\mu\phi$ up to a total derivative. Odd powers such as $\phi$ and $\phi^3$ are forbidden by the $\mathbb Z_2$ symmetry.

</details>

### Exercise 4: Superficial degree and derivative order

A scalar two-point diagram has superficial degree of divergence $D=2$. What momentum structures can its overall divergence contain, and which local quadratic operators do they correspond to?

<details><summary><strong>Solution</strong></summary>

If the superficial degree of divergence is $D=2$, the overall divergent part can be at most quadratic in external momentum:

$$
\Gamma_{\text{div}}^{(2)}(p)=A+Bp^2.
$$

The constant term corresponds to the mass operator

$$
\phi^2.
$$

The $p^2$ term corresponds to the kinetic operator

$$
\partial_\mu\phi\partial^\mu\phi,
$$

up to signs and integration by parts. A $p^4$ divergence would require superficial degree at least four.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially "Renormalization and Symmetry" and "Dilatations."
- Mark Srednicki, *Quantum Field Theory*, especially the chapters on 1PI vertices, renormalizability, renormalization schemes, the renormalization group, and effective field theory.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, and Vol. II, chapter 18.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 19–23.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on renormalization, composite operators, and the short-distance expansion.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on effective actions, power counting, and matching.

## Version history

- 2026-06-16: First polished draft. Added local-operator classification of UV divergences, scalar examples, operator-basis caveats, symmetry constraints, and exercises.
