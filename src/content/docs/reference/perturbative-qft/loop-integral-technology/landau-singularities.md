---
title: "Landau Singularities"
description: "A practical explanation of Landau equations, pinch singularities, physical thresholds, anomalous thresholds, reduced graphs, and the Coleman–Norton interpretation."
sidebar:
  label: "Landau Singularities"
  order: 9
level: Graduate
status: "Polished draft"
source: "Landau 1959; Coleman–Norton 1965; Eden et al.; Bjorken and Drell; Itzykson and Zuber; Smirnov, Feynman Integral Calculus"
topics:
  - Landau equations
  - Feynman integral singularities
  - thresholds
  - anomalous thresholds
  - analytic structure
canonicalTopics:
  - landau-singularities
  - landau-equations
  - pinch-singularities
  - coleman-norton-theorem
  - anomalous-thresholds
researchStatus:
  established:
    - "Landau equations give standard necessary conditions for singularities of Feynman integrals, and the Coleman–Norton interpretation explains physical-region solutions as classical on-shell processes."
  active:
    - "Using Landau analysis to classify symbol alphabets, elliptic sectors, multi-loop singular loci, and physical-sheet structures remains active in modern loop-integral and amplitude research."
---

## Summary

**Landau singularities** are candidate singularities of Feynman integrals as functions of external momenta and masses. They occur when propagator poles pinch the loop-momentum integration contour so that the contour cannot be deformed away.

For a graph with internal momenta $q_j$, masses $m_j$, and denominators

$$
D_j=q_j^2-m_j^2+i\epsilon,
$$

the Landau equations are

$$
\alpha_j(q_j^2-m_j^2)=0
\qquad\text{for every internal line }j,
$$

and, for every independent loop momentum $\ell_r$,

$$
\sum_j \alpha_j\frac{\partial}{\partial \ell_r^\mu}(q_j^2-m_j^2)=0.
$$

Equivalently, since $q_j$ is linear in the loop momenta,

$$
\sum_j \alpha_j\eta_{rj}q_j^\mu=0,
$$

where $\eta_{rj}=0,\pm1$ records whether the line momentum $q_j$ contains $\ell_r$ with positive sign, negative sign, or not at all. The Feynman parameters $\alpha_j$ are not all zero. For physical-region pinch singularities, the relevant solutions have $\alpha_j\ge0$.

The equations are necessary, not sufficient. They tell you where singularities can occur. They do not tell you whether a numerator, a sum over diagrams, a gauge identity, or a choice of sheet removes or hides the singularity.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Landau singularities arise when on-shell propagator poles pinch integration contours, producing candidate singular loci in external invariants](/figures/perturbative-qft/landau-singularities.svg)

<figcaption>

Landau equations encode the pinch condition for loop integrals. Some internal lines are placed on shell, and the weighted on-shell momenta satisfy a loop-stationarity condition. The result is a candidate singular locus in the external invariants. The equations are necessary; the actual discontinuity and sheet structure require more information.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/), [Schwinger Parameters](/perturbative-qft/loop-integral-technology/schwinger-parameters/), and [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/).

It is useful to have seen basic complex analysis: branch points, branch cuts, contour deformation, and the difference between a function and a chosen sheet of that function.

## Core idea

A loop integral is an integral over internal momenta. Its denominators have poles. Usually, when external kinematics change, the integration contour can be deformed away from moving poles. A singularity can occur when this becomes impossible.

The simplest one-variable picture is a contour trapped between two poles approaching from opposite sides:

$$
\text{pole from above}
\quad\downarrow
\qquad
\text{contour}
\qquad
\uparrow\quad
\text{pole from below}.
$$

When the poles pinch, analytic continuation cannot avoid them. The integral then develops a branch point, pole, or more complicated singular behavior.

Landau's insight was that this pinch condition has a graph-theoretic form. A subset of internal lines goes on shell, and the on-shell momenta satisfy a stationarity condition around each loop. In physical regions, Coleman and Norton showed that these equations describe a possible classical spacetime process: internal particles propagate on shell between vertices, with positive parameters corresponding to forward propagation.

The slogan is:

$$
\text{pinched loop contour}
\quad\Longleftrightarrow\quad
\text{on-shell internal classical process}.
$$

## Setup and conventions

Consider an $L$-loop Feynman integral

$$
I(p_i,m_j)
=
\int\prod_{r=1}^{L}\frac{d^d\ell_r}{(2\pi)^d}
\frac{\mathcal N(\ell_r,p_i)}{\prod_{j=1}^{N}(q_j^2-m_j^2+i\epsilon)^{\nu_j}}.
$$

Each internal momentum has the form

$$
q_j=\sum_{r=1}^{L}\eta_{rj}\ell_r+Q_j(p_i),
\qquad
\eta_{rj}\in\{0,\pm1\},
$$

where $Q_j$ is a linear combination of external momenta.

The Landau equations introduce one parameter $\alpha_j$ for each internal line. A possible singularity requires

$$
\alpha_j(q_j^2-m_j^2)=0
$$

for every line, and

$$
\sum_j\alpha_j\eta_{rj}q_j^\mu=0
$$

for each loop $r$. Not all $\alpha_j$ may vanish.

The first equation says that each line is in one of two states:

$$
\alpha_j\ne0
\quad\Rightarrow\quad
q_j^2=m_j^2,
$$

or

$$
q_j^2\ne m_j^2
\quad\Rightarrow\quad
\alpha_j=0.
$$

Thus nonzero $\alpha_j$ select the lines that go on shell. Lines with $\alpha_j=0$ are effectively contracted or removed when studying that Landau solution.

The second equation says that the weighted on-shell momenta close around each loop. It is the loop-momentum stationarity condition.

:::note[Signs and orientations]
The sign $\eta_{rj}$ depends on how the internal momentum $q_j$ is routed through loop $r$. Reversing a line reverses $q_j$ and changes the corresponding sign. The equations themselves are invariant under consistent reroutings.
:::

## How the equations arise

The cleanest route uses the Schwinger-parameter representation. For one propagator,

$$
\frac{i}{q^2-m^2+i\epsilon}
=
\int_0^\infty d\alpha\,
\exp\left[i\alpha(q^2-m^2+i\epsilon)\right]
$$

up to a convention-dependent overall factor. For many propagators, the exponent contains

$$
\Phi(\ell_r,\alpha_j)
=
\sum_j \alpha_j(q_j^2-m_j^2+i\epsilon).
$$

A singularity can occur when the phase is stationary in loop-momentum directions while the exponential damping from the $i\epsilon$ prescription cannot move the integration away. The stationarity condition is

$$
\frac{\partial \Phi}{\partial \ell_r^\mu}
=0,
$$

which gives

$$
\sum_j\alpha_j\frac{\partial}{\partial\ell_r^\mu}(q_j^2-m_j^2)=0.
$$

The endpoint condition in the $\alpha_j$ variables gives

$$
\alpha_j(q_j^2-m_j^2)=0.
$$

This is the Landau system.

In Feynman-parameter language, after loop integration, singularities are often diagnosed from the vanishing of the second Symanzik polynomial $\mathcal F$ and stationarity conditions in the parameter simplex. The loop-momentum form and the Feynman-parameter form are equivalent descriptions of the same pinch geometry, with different variables eliminated.

## Leading and reduced singularities

A **leading Landau singularity** of a graph has

$$
\alpha_j\ne0
$$

for every internal line of the graph. All internal lines participate in the on-shell pinch.

A **subleading Landau singularity** has

$$
\alpha_j=0
$$

for at least one internal line. Setting $\alpha_j=0$ removes that line from the Landau solution. The resulting singularity is associated with a reduced graph obtained by contracting or deleting the corresponding propagator, depending on the representation.

This explains why a complicated graph can have ordinary two-particle thresholds: a subgraph goes on shell while the rest of the diagram behaves as a spectator.

The practical workflow is:

1. choose a graph and a channel;
2. choose a subset of internal lines to put on shell;
3. solve the Landau equations for that subset;
4. eliminate loop variables and $\alpha_j$ to get conditions on external invariants;
5. decide which solutions lie on the physical sheet or relevant unphysical sheets.

The last step is often the hardest. Algebraic solutions of the Landau equations are not automatically physical singularities.

## The Coleman–Norton interpretation

For physical-region solutions with

$$
\alpha_j\ge0,
$$

the Landau equations have a spacetime interpretation.

Each internal line with $\alpha_j>0$ is an on-shell particle. The condition

$$
q_j^2=m_j^2
$$

is its mass shell. The loop equation says that the vertices can be placed in spacetime so that those particles travel classically between them. Roughly, $\alpha_j q_j^\mu$ is proportional to the spacetime displacement along line $j$.

For massive lines, $q_j^\mu$ is timelike on shell and the parameter controls the proper-time separation. For massless lines, the displacement is null.

Thus a physical Landau singularity corresponds to a possible classical process in which all participating internal particles are real, on-shell, and propagate consistently between vertices.

This interpretation is enormously useful. It turns abstract algebraic conditions into a spacetime picture:

$$
\text{Can the internal particles really propagate on shell between the vertices?}
$$

If the answer is no, the solution may live on an unphysical sheet or be absent from the physical region.

## Example: the two-point bubble

Consider the one-loop bubble with external momentum $P$:

$$
D_1=\ell^2-m_1^2,
\qquad
D_2=(P-\ell)^2-m_2^2.
$$

The Landau equations are

$$
\alpha_1(\ell^2-m_1^2)=0,
\qquad
\alpha_2((P-\ell)^2-m_2^2)=0,
$$

and

$$
\alpha_1\ell^\mu-
\alpha_2(P-\ell)^\mu=0.
$$

For the leading singularity, take

$$
\alpha_1,\alpha_2\ne0.
$$

Then both internal lines are on shell:

$$
\ell^2=m_1^2,
\qquad
(P-\ell)^2=m_2^2.
$$

The physical solution occurs when the external momentum can create two on-shell particles. In the rest frame

$$
P^\mu=(\sqrt{s},\mathbf 0),
$$

this requires

$$
\sqrt{s}=E_1+E_2.
$$

At threshold the spatial momenta vanish, so

$$
\sqrt{s}=m_1+m_2.
$$

Therefore the physical branch point is

$$
{s=(m_1+m_2)^2.}
$$

There is also an algebraic pseudo-threshold at

$$
{s=(m_1-m_2)^2.}
$$

It is a solution of the algebraic Landau conditions but does not generally correspond to ordinary production of two positive-energy particles in the physical channel. This distinction between algebraic singular loci and physical-sheet singularities is one of the main reasons Landau analysis must be paired with sheet and energy-flow information.

For equal masses, the physical threshold is

$$
s=4m^2,
$$

matching the onset of the bubble cut.

## Example: massless bubble

For a massless bubble,

$$
m_1=m_2=0.
$$

The physical threshold and pseudo-threshold collide at

$$
s=0.
$$

This is why massless integrals often have singular behavior at vanishing invariants. Depending on the observable, the singularity may be ultraviolet, infrared, collinear, soft, or a mixture after analytic continuation and regularization. The Landau equations identify the kinematic locus. They do not classify the divergence by themselves.

For example, a massless bubble in dimensional regularization has logarithmic dependence on

$$
(-s-i0)^{-\epsilon}.
$$

The branch point at $s=0$ is the Landau singularity. The precise $\epsilon$-pole structure depends on the full integral and the regulator.

## Triangle singularities and anomalous thresholds

A triangle diagram can have a singularity when all three internal lines go on shell and the resulting classical process is kinematically possible. Such a singularity may occur at a value of an external invariant that is not a simple two-particle threshold of the external channel. These are often called **anomalous thresholds**.

The Coleman–Norton picture is the safest guide. A triangle singularity corresponds to a classical sequence:

1. an external particle creates two internal on-shell particles;
2. one internal particle propagates and interacts with another external particle;
3. the final internal on-shell particle reaches the last vertex.

If all spacetime separations can be arranged with forward propagation and all internal particles on shell, the triangle singularity can approach the physical region. If not, the algebraic solution lives elsewhere.

Triangle singularities are not exotic magic. They are the same Landau equations applied to a graph whose classical on-shell spacetime interpretation is more elaborate than a two-particle threshold.

## First-type and second-type singularities

The most familiar Landau singularities are **first-type singularities**. They arise from finite loop momenta and ordinary propagator poles going on shell. Thresholds and anomalous thresholds are first-type examples.

There are also **second-type singularities**, associated with pinch behavior at infinite loop momentum. They are often tied to Gram determinants or special kinematic degenerations. They are more subtle because they are not captured by the same simple finite classical picture.

For many first-pass scattering calculations, first-type singularities are the main concern. But precision multi-loop work, analytic continuation, and special kinematic limits can make second-type singularities unavoidable.

## Relation to unitarity cuts

Landau equations and unitarity cuts answer related but different questions.

| Tool | Main question |
|---|---|
| Landau equations | Where can the integral become singular? |
| Unitarity cuts | What is the discontinuity across a chosen branch cut? |
| Differential equations | How do master integrals vary across kinematic space? |
| Boundary data | Which branch and normalization are physically selected? |

The relation is tight. A physical unitarity cut is supported where cut propagators can be on shell. That support is a Landau condition. Conversely, a Landau threshold often indicates a possible branch cut whose discontinuity is computed by cutting rules.

But Landau equations are broader. They also see anomalous thresholds, subleading singularities, endpoint singularities, and candidate singularities on unphysical sheets. A cut computes a discontinuity in a chosen channel; Landau analysis maps the terrain where discontinuities might exist.

## Relation to symbol alphabets and differential equations

Modern loop calculations often express master integrals in terms of iterated integrals whose differential equations contain letters

$$
d\log W_a(\mathbf x).
$$

The vanishing loci

$$
W_a(\mathbf x)=0
$$

are singular hypersurfaces of the differential equation. Landau analysis is one way to predict or explain which hypersurfaces can occur.

For polylogarithmic integrals, Landau singularities are closely tied to symbol alphabets. For elliptic and more general integrals, the relation is richer: Landau analysis still locates singular loci, but the functions needed to describe the integral may involve periods, elliptic curves, or higher-dimensional geometry.

This is one reason Landau singularities remain useful in modern amplitude research. They are old technology with fresh teeth.

## Necessary does not mean sufficient

The Landau equations give necessary conditions. Several things can prevent a Landau candidate from appearing in a final answer.

A numerator may vanish on the candidate locus. For example, a tensor numerator can cancel a would-be singular denominator.

A sum over diagrams may cancel singularities that appear graph by graph. This is common in gauge theories, where individual diagrams can contain gauge-dependent artifacts.

The candidate singularity may lie on an unphysical sheet. It can still influence analytic continuation, but it may not appear as a physical-region branch point.

The singularity may be softened by dimensional regularization or by cancellations among master-integral coefficients.

The graph may have a Landau singularity, but the observable may be inclusive enough that the corresponding singular behavior cancels after summing real and virtual contributions.

So the correct interpretation is:

$$
\text{Landau solution}
\quad\Rightarrow\quad
\text{candidate singularity, not guaranteed singularity.}
$$

## Common pitfalls

**Calling every Landau solution a physical threshold.** Some solutions are pseudo-thresholds or live on unphysical sheets. Physical thresholds require energy-flow and sheet information.

**Ignoring reduced graphs.** Setting some $\alpha_j=0$ is not a failure of the method. It identifies subleading singularities of reduced graphs.

**Forgetting numerator cancellations.** Landau equations study denominator pinches. Numerators and diagram sums can remove candidate singularities.

**Confusing UV, IR, and threshold singularities.** The same kinematic locus can be entangled with ultraviolet, infrared, soft, or collinear behavior. Landau equations identify pinch loci; regularization and power counting classify divergences.

**Treating the physical sheet as automatic.** The algebraic equations do not know which sheet of the amplitude you want. The $i\epsilon$ prescription and continuation path matter.

**Assuming Landau analysis computes the discontinuity.** It does not. It predicts where discontinuities can occur. Cutting rules, differential equations, or direct integration compute the discontinuity.

## Relations to other pages

- [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/) computes discontinuities across branch cuts whose loci Landau equations often predict.
- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) gives the simplest threshold example.
- [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/) introduces the parameter-space representation in which Landau equations can be written using Symanzik polynomials.
- [Schwinger Parameters](/perturbative-qft/loop-integral-technology/schwinger-parameters/) gives the exponential representation that makes the stationary-phase form of the equations natural.
- [Differential Equations for Integrals](/perturbative-qft/loop-integral-technology/differential-equations-for-integrals/) studies the singular points and branch structure of master-integral systems.
- [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/) explains the basis of functions whose singularities one studies.
- [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/) gives the unitarity origin of physical cuts.

## Research status

- **Established:** Landau equations are the standard necessary conditions for Feynman-integral singularities. Coleman–Norton gives the physical spacetime interpretation for physical-region solutions.
- **Active:** Multi-loop singular-locus classification, Landau analysis for elliptic and more general sectors, symbol-alphabet prediction, physical-sheet determination, and automated singularity analysis remain active.
- **Convention-dependent:** Momentum routing changes the signs in loop equations but not the singular locus after consistent elimination of internal variables.
- **Subtle:** Landau equations alone do not determine residues, branch-cut strengths, sheet placement, or cancellations in full amplitudes.

## Exercises

### Exercise 1: Bubble Landau equations

For the bubble denominators

$$
D_1=\ell^2-m_1^2,
\qquad
D_2=(P-\ell)^2-m_2^2,
$$

write the leading Landau equations.

<details>
<summary><strong>Solution</strong></summary>

The leading solution has

$$
\alpha_1\ne0,
\qquad
\alpha_2\ne0.
$$

Therefore both denominators vanish:

$$
\ell^2=m_1^2,
\qquad
(P-\ell)^2=m_2^2.
$$

The loop-stationarity condition is

$$
\alpha_1\frac{\partial D_1}{\partial\ell^\mu}
+
\alpha_2\frac{\partial D_2}{\partial\ell^\mu}=0.
$$

Since

$$
\frac{\partial D_1}{\partial\ell^\mu}=2\ell_\mu,
\qquad
\frac{\partial D_2}{\partial\ell^\mu}=-2(P-\ell)_\mu,
$$

we get

$$
\alpha_1\ell_\mu-
\alpha_2(P-\ell)_\mu=0.
$$

Equivalently,

$$
\alpha_1\ell^\mu=\alpha_2(P-\ell)^\mu.
$$

</details>

### Exercise 2: Equal-mass threshold

Use the Coleman–Norton interpretation to find the physical threshold of an equal-mass bubble.

<details>
<summary><strong>Solution</strong></summary>

For a physical two-particle threshold, the external momentum $P$ creates two on-shell particles of mass $m$. In the rest frame of $P$,

$$
P^\mu=(\sqrt{s},\mathbf 0).
$$

At threshold, the particles have zero spatial momentum, so each has energy $m$. Energy conservation gives

$$
\sqrt{s}=m+m=2m.
$$

Therefore

$$
s=4m^2.
$$

This is the physical branch point of the equal-mass bubble.

</details>

### Exercise 3: Pseudo-threshold of the unequal-mass bubble

The unequal-mass bubble has algebraic branch points at

$$
s=(m_1+m_2)^2
\qquad\text{and}\qquad
s=(m_1-m_2)^2.
$$

Which one is the ordinary two-particle production threshold in the physical channel?

<details>
<summary><strong>Solution</strong></summary>

The ordinary production threshold occurs when the total center-of-mass energy can create both positive-energy particles:

$$
\sqrt{s}=m_1+m_2.
$$

Thus the physical two-particle threshold is

$$
s=(m_1+m_2)^2.
$$

The branch point

$$
s=(m_1-m_2)^2
$$

is a pseudo-threshold. It is part of the algebraic singularity structure, but it is not the ordinary physical production threshold for two positive-energy particles in this channel.

</details>

### Exercise 4: Reduced graph singularities

What does $\alpha_k=0$ mean in a Landau solution?

<details>
<summary><strong>Solution</strong></summary>

The condition

$$
\alpha_k=0
$$

means line $k$ is not forced on shell by that Landau solution. The singularity is associated with a reduced graph in which that line is removed or contracted in the relevant parameter-space description.

Such solutions are not mistakes. They describe subleading singularities, often ordinary thresholds of subgraphs embedded inside a larger diagram.

</details>

### Exercise 5: Why Landau equations are not sufficient

Give one reason a Landau solution may fail to produce a singularity in a full amplitude.

<details>
<summary><strong>Solution</strong></summary>

One possibility is numerator cancellation. Landau equations analyze the denominators and identify a possible pinch. If the numerator vanishes on the same locus, the candidate singularity can be softened or removed.

Another possibility is cancellation among diagrams. In gauge theories, individual diagrams can have singularities that cancel in gauge-invariant sums. Therefore a Landau solution for one graph is a candidate singularity of that graph, not automatically a singularity of the final physical amplitude.

</details>

## References

- L. D. Landau, “On analytic properties of vertex parts in quantum field theory,” *Nuclear Physics* **13** (1959), for the original Landau equations.
- S. Coleman and R. E. Norton, “Singularities in the physical region,” *Il Nuovo Cimento* **38** (1965), for the classical spacetime interpretation of physical-region Landau singularities.
- R. J. Eden, P. V. Landshoff, D. I. Olive, and J. C. Polkinghorne, *The Analytic S-Matrix*, for classic analytic S-matrix and singularity theory.
- J. D. Bjorken and S. D. Drell, *Relativistic Quantum Fields*, for traditional discussions of Feynman-graph singularities.
- C. Itzykson and J.-B. Zuber, *Quantum Field Theory*, for Landau equations and analytic structure in standard QFT notation.
- V. A. Smirnov, *Feynman Integral Calculus*, for Landau equations, Feynman parameter methods, and singularities of loop integrals.

## Version history

- **2026-06-12:** Initial polished draft. Introduces Landau equations, leading and subleading singularities, bubble thresholds, pseudo-thresholds, triangle singularities, and the relation to cuts and differential equations.
