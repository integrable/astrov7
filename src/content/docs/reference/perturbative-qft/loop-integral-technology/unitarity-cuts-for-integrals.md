---
title: "Unitarity Cuts for Integrals"
description: "A practical explanation of unitarity cuts at the level of loop integrals: cut propagators, discontinuities, phase-space measures, generalized cuts, and reconstruction caveats."
sidebar:
  label: "Unitarity Cuts"
  order: 8
level: Graduate
status: "Polished draft"
source: "Cutkosky 1960; Eden et al., The Analytic S-Matrix; Bern–Dixon–Kosower reviews; Britto–Cachazo–Feng; Smirnov, Feynman Integral Calculus"
topics:
  - unitarity cuts
  - loop integrals
  - discontinuities
  - Cutkosky rules
  - generalized unitarity
canonicalTopics:
  - unitarity-cuts-for-integrals
  - cut-propagators
  - discontinuities
  - generalized-unitarity
  - phase-space-cuts
researchStatus:
  established:
    - "Cutting rules and generalized unitarity are standard tools for extracting discontinuities, integral coefficients, and analytic structure in perturbative QFT."
  active:
    - "Modern multi-loop calculations continue to develop stronger cut-based, finite-field, intersection-theory, and numerical-unitarity methods for large integral families."
---

## Summary

A **unitarity cut** turns part of a loop integral into an on-shell phase-space integral. In qft.org conventions, the basic cut replacement is

$$
\frac{i}{q^2-m^2+i0}
\quad\longmapsto\quad
2\pi\,\delta_+(q^2-m^2),
$$

where

$$
\delta_+(q^2-m^2)\equiv \theta(q^0)\delta(q^2-m^2).
$$

This replacement is not a new Feynman rule for an ordinary diagram. It is the distributional statement that the discontinuity of a Feynman propagator is supported when the internal line goes on shell.

For example, the two-particle cut of a scalar bubble integral in the channel $P^2=s$ becomes the Lorentz-invariant two-body phase space:

$$
\operatorname{Disc}_s B(s)
=\int d\Pi_2^{(d)}(P;k_1,k_2)
$$

up to the overall sign and normalization conventions used to define the scalar integral and the discontinuity. With the convention used on this page, the cut of each Feynman propagator $i/(D+i0)$ contributes $2\pi\delta_+(D)$.

Cuts are useful in three related ways. They compute discontinuities across branch cuts, expose thresholds and physical intermediate states, and determine coefficients of master integrals by matching on enough generalized cuts. The caveat is just as important: a cut sees discontinuities, not automatically the whole function. Rational terms, subtraction constants, boundary data, and analytic-continuation choices still have to be controlled.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![A scalar bubble cut replaces the two cut propagators by positive-energy on-shell delta functions, turning the discontinuity into a two-body phase-space integral](/figures/perturbative-qft/unitarity-cuts-for-integrals.svg)

<figcaption>

A unitarity cut replaces selected Feynman propagators by positive-energy on-shell delta functions. For the scalar bubble, the two-particle cut in the $P^2$ channel turns the discontinuity into the invariant two-body phase-space measure $d\Pi_2^{(d)}$.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/), [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/), and [Differential Equations for Integrals](/perturbative-qft/loop-integral-technology/differential-equations-for-integrals/).

This page assumes dimensional regularization with $d=4-2\epsilon$ when loop integrals need a regulator. It focuses on scalar denominators first. Spin, color, numerator algebra, and gauge theory do not change the logic of cutting denominators; they change the numerator and the allowed intermediate states.

## Core idea

Loop integrals have singularities because integration contours can be pinched by poles. A unitarity cut isolates the part of the integral where chosen internal propagators are forced onto their mass shells. In a physical channel, this is exactly what unitarity predicts: an amplitude can develop an imaginary part when the external energy is large enough to produce real intermediate states.

The conceptual chain is

$$
\text{propagator pole}
\quad\longrightarrow\quad
\text{pinched loop contour}
\quad\longrightarrow\quad
\text{branch cut}
\quad\longrightarrow\quad
\text{on-shell intermediate states}.
$$

At the level of a full amplitude, this is the optical theorem and its multi-particle generalizations. At the level of a loop integral, it becomes a precise replacement rule for selected propagators. That is why cuts are both physical and computational: the same operation explains discontinuities and gives a way to identify integral coefficients.

The cut does **not** say that an internal line in the original Feynman diagram was secretly an observed particle. It says that the discontinuity of the integral is supported on a region of loop momentum where that internal line can be interpreted as an on-shell intermediate state.

## Setup and conventions

Write a scalar denominator as

$$
D(q)=q^2-m^2.
$$

The Feynman propagator is

$$
\frac{i}{D(q)+i0}.
$$

The discontinuity of a function across a branch cut in a variable $s$ is

$$
\operatorname{Disc}_s F(s)
\equiv F(s+i0)-F(s-i0).
$$

For a single real variable $x$, the distribution identity is

$$
\frac{1}{x+i0}=\operatorname{PV}\frac{1}{x}-i\pi\delta(x),
$$

so

$$
\operatorname{Disc}\left[\frac{1}{x+i0}\right]
=-2\pi i\delta(x),
$$

and therefore

$$
\operatorname{Disc}\left[\frac{i}{x+i0}\right]
=2\pi\delta(x).
$$

For a physical cut through a propagator carrying momentum $q$, we also keep the positive-energy part:

$$
\frac{i}{q^2-m^2+i0}
\quad\longmapsto\quad
2\pi\delta_+(q^2-m^2).
$$

The positive-energy condition is not decorative. It orients the cut as a sum over physical intermediate states. Algebraic or generalized cuts sometimes drop the explicit $\theta(q^0)$ and instead impose complex on-shell equations. That is a useful computational move, but it is no longer literally a physical phase-space integral.

For loop integrals, we use

$$
\int_\ell
\equiv
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d},
\qquad d=4-2\epsilon,
$$

unless stated otherwise.

## Cut propagators from the distribution identity

The cut rule follows from the difference between two pole prescriptions. If a propagator denominator crosses the real axis, the two sides of the branch cut differ by

$$
\frac{i}{D+i0}-\frac{i}{D-i0}
=2\pi\delta(D).
$$

In a loop integral, the discontinuity in an external invariant such as $s=P^2$ is more subtle than replacing every possible propagator by a delta function. Only those propagators whose poles pinch the contour in that channel contribute to the corresponding discontinuity. The cut diagram is a compact way to record which denominators are being placed on shell.

For a set $C$ of cut propagators, a schematic cut integral has the form

$$
\operatorname{Cut}_C I
=
\int\prod_{r=1}^{L}\frac{d^d\ell_r}{(2\pi)^d}
\left[\prod_{a\in C}2\pi\delta_+(D_a)\right]
\left[\prod_{b\notin C}\frac{i}{D_b+i0}\right]
N(\ell,p),
$$

where $N(\ell,p)$ is the numerator. For scalar master integrals, $N=1$ or a simple polynomial. For full amplitudes, $N$ contains spinor chains, polarization vectors, color factors, and numerator momenta.

The cut denominators reduce the dimension of the loop integration by imposing on-shell constraints. If enough denominators are cut, the remaining integral may become algebraic. Such **maximal cuts** are especially useful for diagnosing master integrals and leading singularities.

## The scalar bubble cut

Consider the scalar bubble

$$
B(s;m_1^2,m_2^2)
=
\int_\ell
\frac{i}{\ell^2-m_1^2+i0}
\frac{i}{(P-\ell)^2-m_2^2+i0},
\qquad P^2=s.
$$

The two-particle cut in the $s$ channel is

$$
\operatorname{Cut}_s B
=
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}
(2\pi)\delta_+(\ell^2-m_1^2)
(2\pi)\delta_+((P-\ell)^2-m_2^2).
$$

This is exactly the two-body phase-space integral:

$$
\operatorname{Cut}_s B
=
\int d\Pi_2^{(d)}(P;k_1,k_2).
$$

In four dimensions, after integrating over the final-state angles, the two-body phase space is

$$
\int d\Pi_2(P;k_1,k_2)
=
\frac{\lambda^{1/2}(s,m_1^2,m_2^2)}{8\pi s}\,\theta\big(s-(m_1+m_2)^2\big),
$$

where

$$
\lambda(s,m_1^2,m_2^2)
=s^2+m_1^4+m_2^4-2sm_1^2-2sm_2^2-2m_1^2m_2^2.
$$

For equal masses, $m_1=m_2=m$,

$$
\int d\Pi_2(P)
=\frac{1}{8\pi}\sqrt{1-\frac{4m^2}{s}}\,\theta(s-4m^2).
$$

This formula is the cleanest sanity check on the cut. The bubble has a branch point at $s=4m^2$ because two internal particles can go on shell at that invariant mass.

## Cuts of full amplitudes versus cuts of integrals

For full amplitudes, unitarity relates a discontinuity to a sum over complete intermediate states. Schematically,

$$
\operatorname{Disc}\mathcal M_{i\to f}
\sim
\sum_n
\int d\Pi_n\,
\mathcal M_{i\to n}\,
\mathcal M^*_{f\to n},
$$

with convention-dependent factors of $i$ and signs determined by the precise definition of $S=1+iT$ and $\mathcal M$.

For a scalar integral, the cut is the denominator part of the same statement. If the numerator of a diagram factorizes into the product of two lower-order amplitudes across the cut, the cut diagram literally computes a contribution to the unitarity sum. If the numerator is an arbitrary tensor numerator, the cut still defines a valid discontinuity of that integral, but it may not by itself have the interpretation of a physical probability.

This distinction is useful:

| Object | What the cut means |
|---|---|
| Full amplitude | Sum over physical intermediate states required by unitarity. |
| Scalar master integral | Discontinuity of a basis function in a chosen channel. |
| Tensor integral | Discontinuity with numerator inserted on the cut surface. |
| Generalized cut | Algebraic projection onto selected on-shell propagators. |

So the phrase “unitarity cut” is used in two nearby ways: physical unitarity of amplitudes and cut analysis of loop integrals. The second borrows its notation and intuition from the first.

## Generalized cuts

A physical two-particle cut places enough internal lines on shell to split a diagram into two lower-order pieces. A **generalized cut** places any chosen set of propagators on shell:

$$
D_{a_1}=D_{a_2}=\cdots=D_{a_k}=0.
$$

If $k$ is large enough, the remaining loop momentum degrees of freedom are highly constrained. In one-loop four-dimensional calculations, cutting four propagators of a box integral typically freezes the loop momentum to a finite set of complex solutions. This is the basic reason one-loop amplitudes can often be reconstructed efficiently from quadruple cuts.

At higher loop order, generalized cuts are used to compare two integrands or two integral reductions. If two candidate integrands agree on a sufficiently complete set of cuts, their difference has no support on the corresponding propagator structures. In practical amplitude calculations, one often uses cuts to determine the coefficients in an ansatz:

$$
\mathcal A^{(L)}
=
\sum_a c_a(\{s\},\epsilon)\,I_a
+\text{terms with fewer propagators}.
$$

Cutting both sides gives algebraic equations for the $c_a$.

### Maximal cuts

A maximal cut cuts as many propagators as possible. It isolates the highest-codimension on-shell surface of an integral family. In favorable cases, the maximal cut of a master integral reveals its leading singularity or the homogeneous part of its differential equation.

For a one-loop integral with $L=1$ and four denominators in four dimensions, a maximal cut imposes four equations on the four components of $\ell$. For multi-loop integrals, the counting is richer because irreducible scalar products can remain even after all propagators are placed on shell.

### D-dimensional cuts

Four-dimensional cuts can miss information that vanishes on strictly four-dimensional on-shell kinematics but survives in dimensional regularization. This is a common source of rational terms in one-loop amplitudes and of regulator-dependent information at higher loops.

A safer statement is:

$$
\text{to reconstruct a dimensionally regulated amplitude, use cuts consistent with } d=4-2\epsilon.
$$

Four-dimensional cuts are still extremely useful, especially for helicity amplitudes, but they must be supplemented when regulator-dependent terms matter.

## Cuts and master-integral bases

Cuts are a powerful diagnostic for master integrals. Suppose a reduction gives

$$
I_{\boldsymbol\nu}
=
\sum_a c_a M_a.
$$

Apply a cut $C$:

$$
\operatorname{Cut}_C I_{\boldsymbol\nu}
=
\sum_a c_a\,\operatorname{Cut}_C M_a.
$$

If only a few masters have nonzero support on that cut, the equation becomes much simpler. This is one reason modern integral bases are often organized by propagator topology and cut structure.

A cut can also reveal whether a candidate master integral has the right analytic structure for a physical problem. For instance, if an amplitude has a physical two-particle threshold in a channel, the master basis must contain functions whose discontinuities can reproduce that threshold. Conversely, if a candidate term has a cut in a channel where the full amplitude should not, its coefficient must vanish or its discontinuity must cancel against other terms.

## Reconstructing functions from cuts

Cuts give discontinuities. They do not automatically give the full integral.

A function with the same discontinuity can differ by a term analytic in the cut variable. In a dispersion relation, such terms appear as subtraction constants or polynomials. In differential-equation methods, they appear as boundary constants. In amplitude reconstruction, they appear as rational terms or contact terms that have no branch cut in the channel being studied.

A typical reconstruction problem therefore needs three ingredients:

$$
\text{cuts}
+\text{analytic input}
+\text{boundary or subtraction data}
=\text{full result}.
$$

The analytic input may include mass dimension, crossing symmetry, absence of spurious poles, behavior at infinity, known soft or collinear limits, regularity at special kinematic points, or comparison with a low-energy expansion.

This is also why cuts pair so naturally with differential equations. Cuts identify branch points and discontinuities; differential equations organize how the integral changes as kinematics move; boundary data fixes the integration constants.

## Practical workflow

A reliable cut calculation usually follows this sequence.

1. **Choose the channel.** Decide which external invariant, such as $s=P^2$, is being continued across a branch cut.

2. **Identify the cut propagators.** These are the internal denominators whose on-shell momenta can carry the chosen channel momentum.

3. **Replace cut propagators.** Use

   $$
   \frac{i}{D+i0}\to 2\pi\delta_+(D)
   $$

   for physical cuts, or impose $D=0$ algebraically for generalized cuts.

4. **Keep uncut propagators.** Propagators not crossed by the cut remain ordinary Feynman propagators unless a more specialized cutting prescription is being used.

5. **Evaluate or match.** Either perform the resulting phase-space integral or match it against cuts of a master-integral basis.

6. **Restore analytic information.** Use boundary conditions, crossing, known limits, or dispersion relations to reconstruct information not visible on the cut.

The main check is threshold support. If the cut claims a discontinuity below the physical threshold, an energy-flow convention or $\theta(q^0)$ condition has usually gone missing.

## Common pitfalls

**Treating a cut as a new ordinary diagram.** A cut diagram computes a discontinuity or a projection. It is not inserted into the original perturbative expansion as a separate Feynman diagram.

**Dropping the positive-energy condition.** For physical unitarity cuts, $\theta(q^0)$ selects the correct intermediate-state orientation. Without it, the result may include unphysical or pseudo-threshold contributions.

**Confusing an integral cut with an amplitude cut.** A scalar integral cut is a discontinuity of a basis function. A full amplitude cut includes sums over physical states and products of lower-order amplitudes.

**Assuming cuts determine everything.** Cuts determine branch discontinuities. Rational pieces, subtraction constants, and boundary data can remain invisible to a given set of cuts.

**Using four-dimensional cuts when regulator terms matter.** Dimensional regularization can store important information in $(-2\epsilon)$-dimensional components of loop momenta.

**Ignoring analytic continuation.** The same algebraic cut equation can represent a physical threshold, pseudo-threshold, or anomalous threshold depending on sheet, energy flow, and kinematic region.

## Relations to other pages

- [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/) explains the amplitude-level origin of cuts from $S$-matrix unitarity.
- [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/) defines the on-shell measures that appear after cutting propagators.
- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) provides the simplest loop integral whose cut is a two-body phase-space integral.
- [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/) explains how cut information helps organize integral bases.
- [Differential Equations for Integrals](/perturbative-qft/loop-integral-technology/differential-equations-for-integrals/) explains how cuts, singular points, and boundary data enter integral evaluation.
- [Landau Singularities](/perturbative-qft/loop-integral-technology/landau-singularities/) describes the kinematic loci where cuts and branch points can arise.

## Research status

- **Established:** The distributional cut replacement, Cutkosky rules, and generalized unitarity are standard parts of perturbative QFT and amplitude technology.
- **Active:** Multi-loop generalized unitarity, finite-field reconstruction, numerical unitarity, integrand bases, and cut-compatible master bases remain active tools in precision scattering calculations.
- **Subtle:** A cut is not the whole analytic function. Reconstructing full loop integrals requires boundary data, analytic-continuation choices, and careful treatment of regulator-dependent terms.

## Exercises

### Exercise 1: Discontinuity of a propagator

Use

$$
\frac{1}{x+i0}=\operatorname{PV}\frac{1}{x}-i\pi\delta(x)
$$

to show that

$$
\operatorname{Disc}\left[\frac{i}{x+i0}\right]=2\pi\delta(x).
$$

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
\operatorname{Disc}\left[\frac{i}{x+i0}\right]
=
\frac{i}{x+i0}-\frac{i}{x-i0}.
$$

Using

$$
\frac{1}{x+i0}=\operatorname{PV}\frac{1}{x}-i\pi\delta(x),
\qquad
\frac{1}{x-i0}=\operatorname{PV}\frac{1}{x}+i\pi\delta(x),
$$

we find

$$
\frac{i}{x+i0}=i\operatorname{PV}\frac{1}{x}+\pi\delta(x),
$$

and

$$
\frac{i}{x-i0}=i\operatorname{PV}\frac{1}{x}-\pi\delta(x).
$$

Subtracting gives

$$
\operatorname{Disc}\left[\frac{i}{x+i0}\right]
=2\pi\delta(x).
$$

</details>

### Exercise 2: Bubble cut as phase space

Show that

$$
\int\frac{d^d\ell}{(2\pi)^d}
(2\pi)\delta_+(\ell^2-m_1^2)
(2\pi)\delta_+((P-\ell)^2-m_2^2)
$$

is the two-body phase-space integral $\int d\Pi_2^{(d)}(P;k_1,k_2)$.

<details>
<summary><strong>Solution</strong></summary>

Insert the definition

$$
\delta_+(k^2-m^2)=\theta(k^0)\delta(k^2-m^2).
$$

For any test function $F(k)$,

$$
\int d^d k\,\delta_+(k^2-m^2)F(k)
=
\int\frac{d^{d-1}\mathbf k}{2E_{\mathbf k}}F(E_{\mathbf k},\mathbf k).
$$

Apply this to $k_1=\ell$ and $k_2=P-\ell$. The second delta function enforces the on-shell condition for $k_2$, while the shared integration variable enforces momentum conservation $P=k_1+k_2$. Restoring the $(2\pi)$ factors gives

$$
\int d\Pi_2^{(d)}(P;k_1,k_2)
=(2\pi)^d\delta^{(d)}(P-k_1-k_2)
\prod_{a=1}^2
\frac{d^{d-1}\mathbf k_a}{(2\pi)^{d-1}2E_a},
$$

which is equivalent to the loop-momentum expression above after using the momentum-conserving delta function to remove one final-state momentum.

</details>

### Exercise 3: Equal-mass threshold

For the equal-mass bubble with internal mass $m$, use two-particle kinematics to show that the physical cut begins at $s=4m^2$.

<details>
<summary><strong>Solution</strong></summary>

In the center-of-momentum frame,

$$
P^\mu=(\sqrt{s},\mathbf 0),
$$

and the two on-shell cut momenta are

$$
k_1^\mu=(E,\mathbf k),
\qquad
k_2^\mu=(E,-\mathbf k),
\qquad
E=\sqrt{\mathbf k^2+m^2}.
$$

Momentum conservation gives

$$
\sqrt{s}=2E.
$$

Therefore

$$
s=4(\mathbf k^2+m^2).
$$

A real solution requires $\mathbf k^2\ge0$, so

$$
s\ge4m^2.
$$

The threshold occurs at $\mathbf k=0$, hence $s=4m^2$.

</details>

### Exercise 4: Why a cut may miss rational terms

Explain why knowing $\operatorname{Disc}_s F(s)$ does not necessarily determine $F(s)$ uniquely.

<details>
<summary><strong>Solution</strong></summary>

If two functions have the same discontinuity across a given cut, their difference has zero discontinuity across that cut. The difference can still be a nonzero function analytic in that channel. For example, adding a polynomial in $s$ changes $F(s)$ but does not create a branch cut in $s$.

In dispersion language, these analytic terms are subtraction constants or subtraction polynomials. In differential-equation language, they are boundary constants. In amplitude reconstruction, they often appear as rational terms or contact terms. Therefore cuts are powerful but must be supplemented by analytic input or boundary data.

</details>

## References

- R. E. Cutkosky, “Singularities and discontinuities of Feynman amplitudes,” *Journal of Mathematical Physics* **1** (1960), for the original cutting rules.
- R. J. Eden, P. V. Landshoff, D. I. Olive, and J. C. Polkinghorne, *The Analytic S-Matrix*, for analytic structure, thresholds, and discontinuities.
- G. 't Hooft and M. Veltman, “Diagrammar,” for a classic practical discussion of perturbative diagrams and cutting logic.
- Z. Bern, L. Dixon, and D. A. Kosower, reviews and papers on generalized unitarity and amplitude reconstruction.
- R. Britto, F. Cachazo, and B. Feng, early modern unitarity papers for one-loop amplitudes.
- V. A. Smirnov, *Feynman Integral Calculus*, for loop integrals, cuts, analytic continuation, and dimensional regularization.
- M. Srednicki, *Quantum Field Theory*, especially the one-loop scattering and infrared-divergence chapters.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 24, for unitarity and the optical theorem.

## Version history

- **2026-06-12:** Initial polished draft. Added scalar bubble cut normalization, generalized cuts, D-dimensional caveats, reconstruction warnings, solved exercises, and a compact SVG figure.
