---
title: "What Bootstrap Can and Cannot Prove"
description: "Clarifies the logical status of bootstrap bounds, exclusions, islands, extremal spectra, numerical certificates, and physical interpretations."
sidebar:
  label: "What Bootstrap Can Prove"
  order: 10
level: Graduate
status: "Polished draft"
source: "Rattazzi, Rychkov, Tonni, and Vichi 2008; Simmons-Duffin TASI; Poland, Rychkov, and Vichi 2019; Rychkov and Su 2024"
topics:
  - conformal bootstrap
  - bootstrap logic
  - numerical bounds
  - allowed regions
  - rigorous exclusion
canonicalTopics:
  - bootstrap-logic
  - bootstrap-proof-status
  - conformal-bootstrap-interpretation
researchStatus:
  established:
    - "Bootstrap exclusion is a conditional mathematical statement: under explicit assumptions, a positive crossing solution cannot exist."
  active:
    - "Making large-scale numerical bootstrap results fully rigorous, interpreting islands, and connecting bootstrap data to microscopic models remain active parts of the field."
---

## Summary

The conformal bootstrap is strongest when its logical status is stated plainly.

A bootstrap exclusion has the form

$$
\text{assumptions}
\quad\Longrightarrow\quad
\text{no unitary crossing-symmetric solution}.
$$

A bootstrap allowed region means something weaker:

$$
\text{no exclusion certificate was found at the chosen truncation and assumptions}.
$$

A bootstrap island means that many constraints have localized a small allowed region in CFT-data space. It is excellent evidence when stable and independently checked, but it is not automatically an existence proof. An extremal spectrum extracted from the boundary of an island or a bound is a candidate spectrum, not a theorem that a microscopic model flows to it.

<figure class="doc-figure" style="--figure-width: 43rem;">

![Bootstrap proof scope](/figures/cft-bootstrap/bootstrap-proof-scope.svg)

<figcaption>

The bootstrap proves conditional consistency statements. Assumptions and numerical choices feed into a crossing problem; the output is an exclusion, allowed region, island, or candidate extremal data. Physical identification requires further evidence.

</figcaption>
</figure>

This page is a logic-and-hygiene guide. It explains what bootstrap results prove, what they suggest, what they do not prove, and how to write claims so that they remain true after the next higher-precision computation arrives.

## Prerequisites

You should know [Bootstrap Equations](/cft-bootstrap/crossing-bootstrap-logic/bootstrap-equations/), [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/), [Gaps and Assumptions](/cft-bootstrap/crossing-bootstrap-logic/gaps-and-assumptions/), [Islands in Parameter Space](/cft-bootstrap/crossing-bootstrap-logic/islands-in-parameter-space/), and [Extremal Functional Method](/cft-bootstrap/crossing-bootstrap-logic/extremal-functional-method/).

For background, it also helps to know [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/) and [Conformal Data from OPE](/cft-bootstrap/operator-product-expansion/conformal-data-from-ope/). The bootstrap constrains CFT data; it does not begin with a Lagrangian.

## Core idea

The bootstrap is not a black box that prints “the theory.” It is a machine for proving or testing compatibility among assumptions.

A typical numerical bootstrap problem specifies:

- spacetime dimension $d$;
- global symmetry or lack of global symmetry;
- external operators and their representations;
- crossing equations for selected correlators;
- unitarity and reflection positivity;
- assumed gaps or spectral ordering;
- normalization conventions;
- a finite derivative order or other truncation;
- numerical precision and block approximations.

The output must be read relative to this input. Change the assumptions and the theorem changes.

The safest slogan is:

$$
\text{bootstrap result}
=
\text{CFT consistency}
+
\text{specified assumptions}
+
\text{specified numerical control}.
$$

This is not a weakness. It is why the method is powerful. The bootstrap can make statements about all unitary CFTs satisfying a list of assumptions, including theories with no known Lagrangian. But the price of this universality is that every assumption must be visible.

## What an exclusion proves

In its cleanest form, a bootstrap exclusion is a separating-functional theorem.

Let the crossing equation be written as

$$
T=\sum_a p_aV_a,
\qquad
p_a\ge0,
$$

where $T$ is the target vector and $V_a$ run over conformal-block vectors allowed by the assumptions. If there exists a linear functional $\alpha$ such that

$$
\alpha(T)<0,
\qquad
\alpha(V_a)\ge0
$$

for every allowed $a$, then no such positive solution can exist. Indeed, if the crossing equation held, applying $\alpha$ would give

$$
\alpha(T)=\sum_a p_a\alpha(V_a)\ge0,
$$

contradicting $\alpha(T)<0$.

That is a real proof, but of a conditional statement. The condition “for every allowed $a$” includes all the spectral assumptions. For example, if we imposed a scalar gap, the proof rules out theories with that gap. It does not rule out theories with an extra scalar below the gap.

For semidefinite programs, the scalar inequalities are replaced by positive semidefinite matrix inequalities. The same logic applies: a positive functional on every allowed matrix block cannot reproduce a target with the wrong sign.

:::note[The important word is assumptions]
A rigorous exclusion statement is never “the CFT does not exist” in the void. It is “no CFT exists satisfying these assumptions.” A missing global-symmetry sector, a wrong gap, or a neglected external operator can change the statement.
:::

## What a bound proves

A numerical upper bound on an operator dimension usually has the form

$$
\Delta_{\mathrm{lowest}}\le \Delta_{\mathrm{max}}(\Delta_{\mathrm{external}})
$$

for all unitary CFTs satisfying the chosen assumptions. The proof is by exclusion: every larger trial gap is ruled out by a functional.

Thus a bound is a universal constraint. It does not say that a CFT saturating the bound exists. It says that a CFT violating the bound does not exist under the assumptions.

This distinction matters near kinks. A kink in a bound plot may indicate an important CFT, and historically that intuition has been very productive. But the bound itself proves only that the region above the curve is impossible. The claim that a particular theory sits at the kink requires additional evidence: spectrum extraction, mixed-correlator islands, agreement with Monte Carlo or perturbation theory, known symmetries, Ward identities, or exact results.

## What an allowed region means

An allowed region is not the same thing as an existence theorem.

At a fixed derivative order $\Lambda$, “allowed” means that the search did not find a functional excluding that point. In geometric language, the finite-dimensional target was not separated from the approximated cone by the functionals considered in the search.

There are three common reasons a point can be allowed:

1. A genuine CFT exists there.
2. No genuine CFT exists, but the chosen constraints are too weak to rule it out.
3. A numerical or approximation limitation prevents the exclusion certificate from being found.

Only the first option is physics. The other two are normal parts of numerical bootstrap life.

Allowed regions become more persuasive when they shrink and stabilize as constraints are strengthened. A small island that persists under increasing $\Lambda$, additional correlators, and independent checks is much more meaningful than a broad allowed blob from a single correlator.

## What an island means

A bootstrap island is a small allowed region in a space of CFT data, often external dimensions and OPE coefficients. The typical logic is:

$$
\text{crossing}
+\text{unitarity}
+\text{symmetry}
+\text{gaps}
+\text{mixed correlators}
\quad\Longrightarrow\quad
\text{small allowed region}.
$$

An island is stronger than a kink because it localizes data in more than one direction. It also tests mutual compatibility among several OPE channels. In mixed-correlator systems, matrix positivity makes the allowed region far more rigid than in a single-correlator problem.

Still, an island is an allowed region. It is evidence of consistency, not automatically a constructive proof of a CFT. To identify an island with a known universality class, one should compare:

- critical exponents;
- symmetry and representation assignments;
- relevant-operator count;
- current and stress-tensor normalizations;
- known Ward identities;
- perturbative expansions when available;
- Monte Carlo or lattice data when applicable;
- exact data in special dimensions;
- stability under stronger bootstrap assumptions.

The more independent checks agree, the more confident the physical identification becomes.

## What extremal spectra mean

An extremal spectrum is extracted from a functional near the boundary of an allowed region. The zeros of the functional suggest which exchanged operators appear in a candidate solution, and a truncated crossing solve estimates OPE coefficients.

This is one of the most useful interpretive tools in numerical bootstrap. It can reveal approximate spectra long before a full analytic solution is available.

But the logical status is:

$$
\text{extremal spectrum}
=
\text{candidate finite-truncation boundary solution}.
$$

It is not automatically:

$$
\text{actual Hilbert space of a CFT}.
$$

The extracted data become credible when they converge with increasing truncation, satisfy positivity, match Ward identities, and agree with independent calculations. Low-lying stable operators are usually more trustworthy than high-lying noisy zeros.

## What bootstrap cannot prove by itself

The bootstrap cannot, by itself, prove every statement that physicists want to say.

It usually does **not** prove that a particular lattice model flows to a particular CFT. That requires RG or statistical-mechanics evidence connecting the microscopic model to the fixed point.

It does **not** automatically prove that an allowed island contains an actual CFT. It proves only that the imposed constraints have not excluded it.

It does **not** identify a Lagrangian. A CFT may be non-Lagrangian, and different Lagrangians may flow to the same CFT.

It does **not** determine all operator data from one correlator. A single four-point function sees only the operators appearing in one OPE channel and only through the structures present in that correlator.

It does **not** replace assumptions with conclusions. If a gap was imposed, the resulting island is conditional on that gap. If a global symmetry was assumed, the result lives in that symmetry class.

It does **not** make numerical precision irrelevant. Solver tolerances, conformal-block approximations, derivative order, and truncation choices all matter.

It does **not** always distinguish two nearby CFTs. If two theories share the same limited set of low-lying data in the chosen correlators, a given bootstrap setup may not separate them.

This list is not a dunk on the bootstrap. It is the user manual. The method is powerful because it is sharp about what it assumes.

## What bootstrap can prove

Now the happier list.

Bootstrap can prove that no unitary CFT satisfying specified assumptions exists in a region of parameter space.

Bootstrap can prove universal bounds on dimensions, OPE coefficients, central charges, and other CFT data, conditional on the chosen assumptions.

Bootstrap can show that a hypothetical spectrum is inconsistent with crossing and positivity.

Bootstrap can localize candidate theories into tiny islands when enough correlators and assumptions are combined.

Bootstrap can extract candidate spectra and OPE data at boundaries and islands.

Bootstrap can test proposed dualities by comparing symmetry, dimensions, OPE coefficients, central charges, and selection rules.

Bootstrap can rule out overly simple stories. For example, if a proposed critical point requires a relevant-operator spectrum incompatible with crossing bounds, that proposal is in trouble.

Bootstrap can constrain non-Lagrangian theories, where perturbative Feynman diagrams are not available.

Bootstrap can turn vague words like “strongly coupled fixed point” into numerical data that can be checked, reused, and falsified.

## Degrees of rigor

Not all bootstrap statements have the same rigor. A useful taxonomy is:

| Level | Statement type | Example language |
|---|---|---|
| Conceptual | Formal consequence of crossing and unitarity. | “OPE coefficients enter positively in this channel.” |
| Numerical evidence | Stable finite-truncation observation. | “The island appears stable up to the derivative orders studied.” |
| Numerical exclusion | Solver finds a certificate at stated precision. | “This point is excluded at derivative order $\Lambda$ with the stated setup.” |
| Certified numerical theorem | All approximations and inequalities are controlled rigorously. | “No solution exists in this interval under these assumptions.” |
| Physical identification | Bootstrap data are matched to an external theory. | “The island is identified with the 3D Ising CFT based on agreement with independent data.” |

Most research papers contain several levels at once. Good writing labels them rather than blending them into one fog bank.

## Responsible phrasing

Here is a practical translation table.

| Tempting phrase | Better phrase |
|---|---|
| “The bootstrap proves the 3D Ising model exists.” | “The bootstrap isolates data consistent with the 3D Ising CFT under the stated assumptions, and the identification is supported by independent evidence.” |
| “The allowed region is the space of CFTs.” | “The allowed region is the set not excluded by the chosen bootstrap constraints.” |
| “This kink is a CFT.” | “This kink is a candidate location for a CFT; further checks are needed.” |
| “The extremal functional gives the spectrum.” | “The extremal functional gives a candidate spectrum at finite truncation.” |
| “The gap assumption is harmless.” | “The conclusion is conditional on the gap assumption.” |
| “Numerics prove it.” | “The computation provides an exclusion certificate at the stated truncation and precision.” |
| “No Lagrangian, no theory.” | “The bootstrap can constrain CFT data without a Lagrangian description.” |

The small words are doing real work. “Candidate,” “conditional,” “finite-truncation,” “under the stated assumptions,” and “not excluded” keep the statement honest.

## How to make a bootstrap claim stronger

Several moves strengthen a bootstrap conclusion.

**Increase truncation.** A result that survives increasing derivative order is more reliable than one seen once.

**Add correlators.** Mixed-correlator systems test more OPE channels and often convert broad allowed regions into islands.

**Use symmetry sectors carefully.** Decomposing into irreducible representations prevents accidental mixing and sharpens positivity.

**State gaps explicitly.** Gaps are legitimate assumptions, but hidden gaps are not.

**Check Ward identities.** Currents and stress tensors have protected dimensions and normalization relations. They are excellent calibration tools.

**Compare to external data.** Monte Carlo, perturbation theory, large-$N$, exact 2D results, supersymmetric localization, and lattice simulations are not rivals. They are cross-examiners.

**Track numerical certificates.** Precision, block approximations, and solver status matter, especially near boundaries.

**Vary assumptions.** If a conclusion collapses when one plausible assumption is relaxed, say so.

## A miniature proof template

A clean bootstrap exclusion can be written in this template:

1. Define the class of theories: unitary CFTs in dimension $d$ with symmetry $G$, specified external operators, and stated gaps.
2. Write the crossing equation in block-vector form.
3. Define the functional space used at truncation $\Lambda$.
4. Exhibit or numerically certify a functional satisfying positivity on all allowed exchanged operators.
5. Show that the target has the opposite sign.
6. Conclude that no theory in the stated class exists at that parameter point.

The last sentence should not exceed the first sentence. If the first sentence says “with a singlet scalar gap above $1.6$,” the conclusion must keep that condition.

## Common pitfalls

**Allowed means exists.** It does not. Allowed means not excluded by the current constraints.

**Excluded means impossible in nature.** It means impossible under the stated assumptions. Nature is not obligated to obey your hidden gap.

**Kink worship.** Kinks are useful clues, not saints. Some correspond to known CFTs; others may be artifacts, crossovers between bounds, or features of a weakened problem.

**Forgetting invisible operators.** A four-point function only sees operators appearing in the chosen OPE. Operators absent from that OPE are not constrained directly.

**Over-reading high operators.** Extremal extraction is usually most reliable for low-lying stable data. High-dimension data can be truncation-sensitive.

**Ignoring finite precision.** A pretty plot can still have numerically delicate boundaries. Keep the solver logs, tolerances, and assumptions.

**Confusing universality class evidence with proof of RG flow.** Identifying a CFT with a lattice universality class needs evidence that the microscopic model flows to that fixed point.

## Relations to other pages

[Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) explains the equality among OPE channels that gives the bootstrap its main consistency equation.

[Bootstrap Equations](/cft-bootstrap/crossing-bootstrap-logic/bootstrap-equations/) explains how crossing becomes a vector equation.

[Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/) explains the positivity assumptions behind exclusion functionals.

[Gaps and Assumptions](/cft-bootstrap/crossing-bootstrap-logic/gaps-and-assumptions/) is the companion page on how assumptions enter the theorem.

[Islands in Parameter Space](/cft-bootstrap/crossing-bootstrap-logic/islands-in-parameter-space/) explains how small allowed regions are produced and interpreted.

[Extremal Functional Method](/cft-bootstrap/crossing-bootstrap-logic/extremal-functional-method/) explains how candidate spectra are extracted at boundaries.

Later, [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) treats solver technology, semidefinite programming, derivative bases, and numerical certification in more detail.

## Research status

The logic of exclusion by separating functionals is established. It is the conceptual core of modern numerical bootstrap.

The active frontier is not the slogan but the control. Modern computations are large, use sophisticated conformal-block approximations, include mixed correlators and matrix positivity, and may involve parameter searches with navigator or skydive-type methods. Each improvement strengthens the method, but also adds numerical and interpretive layers that must be documented.

A second active frontier is existence. The bootstrap is exceptionally good at ruling out inconsistent data and isolating candidate data. Constructing or proving the existence of a CFT with those data is a different kind of problem, connected to constructive QFT, lattice models, RG flows, exact solutions, and mathematical analysis.

The best practice is therefore pluralistic: let bootstrap give sharp nonperturbative constraints, then compare them with every other reliable method. Physics is not offended by independent checks. It gets stronger.

## Exercises

### Exercise 1: Allowed is not existence

Explain why the absence of an exclusion functional at derivative order $\Lambda$ does not prove that a CFT exists at the corresponding point.

<details><summary><strong>Solution</strong></summary>

At finite $\Lambda$, the bootstrap has tested only a finite-dimensional projection of the full crossing problem and only the functionals included in the chosen search space. It is possible that a higher-derivative functional, another correlator, a sharper gap assumption, or a more accurate block approximation would exclude the point. Therefore “allowed” means “not excluded by this setup,” not “realized by a CFT.”

</details>

### Exercise 2: Conditional exclusion

Suppose a bootstrap calculation assumes that the lowest scalar singlet above the identity has $\Delta_S\ge 2.0$ and finds an exclusion functional. What exactly has been proved?

<details><summary><strong>Solution</strong></summary>

The result proves that no unitary crossing-symmetric solution exists satisfying all the assumptions of the calculation, including the singlet scalar gap $\Delta_S\ge2.0$. It does not rule out a CFT with a scalar singlet at $\Delta_S=1.7$, nor a CFT with different symmetry assignments, different external operators, or different assumptions.

</details>

### Exercise 3: Kink versus island

Why is an island usually stronger evidence for a candidate CFT than a kink in a one-dimensional bound?

<details><summary><strong>Solution</strong></summary>

A kink is a feature of a boundary curve. It may indicate a change in the extremal solution or the presence of an interesting CFT, but by itself it localizes data weakly. An island is a small allowed region produced by simultaneous constraints, often from mixed correlators and multiple assumptions. It localizes several pieces of CFT data at once and tests compatibility among more OPE channels. It is still not automatically an existence proof, but it is typically stronger evidence than a single kink.

</details>

### Exercise 4: The proof cannot be stronger than the input

A paper claims: “We prove that there is no CFT with symmetry $G$ in this range.” Reading the setup, you find that the computation imposed an extra gap in a $G$-singlet scalar sector. Rewrite the claim responsibly.

<details><summary><strong>Solution</strong></summary>

A responsible version is:

> We prove that there is no unitary crossing-symmetric CFT with symmetry $G$ in this range, under the additional assumption that the $G$-singlet scalar sector has the stated gap.

The gap must appear in the conclusion because it was part of the input used to obtain the exclusion.

</details>

## References

- R. Rattazzi, V. S. Rychkov, E. Tonni, and A. Vichi, “Bounding Scalar Operator Dimensions in 4D CFT,” *Journal of High Energy Physics* **2008**.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures, 2016.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024 review.
- S. El-Showk, M. F. Paulos, D. Poland, S. Rychkov, D. Simmons-Duffin, and A. Vichi, “Solving the 3D Ising Model with the Conformal Bootstrap,” *Physical Review D* **86** (2012).
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Precision Islands in the Ising and $O(N)$ Models,” modern mixed-correlator bootstrap literature.

## Version history

- 2026-06-28: First polished draft. Added proof-status taxonomy, exclusion logic, island interpretation, responsible phrasing, exercises, and figure.
