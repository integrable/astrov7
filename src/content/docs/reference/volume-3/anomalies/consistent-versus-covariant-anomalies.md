---
title: "Consistent Versus Covariant Anomalies"
description: "Explains the distinction between consistent and covariant anomalies, Wess–Zumino consistency, Bardeen–Zumino currents, and when each representative is useful."
sidebar:
  label: "Consistent vs Covariant"
  order: 11
level: Advanced
status: "Polished draft"
source: "Bardeen; Wess–Zumino; Zumino descent; Bardeen–Zumino currents; Weinberg Vol. II consistency conditions; standard anomaly-polynomial and BRST-cohomology treatments."
topics:
  - consistent anomaly
  - covariant anomaly
  - Bardeen-Zumino current
  - Wess-Zumino consistency
  - descent equations
  - anomaly current
  - gauge covariance
canonicalTopics:
  - consistent-anomaly
  - covariant-anomaly
  - bardeen-zumino-current
  - wess-zumino-consistency
  - anomaly-representative
researchStatus:
  established:
    - "Consistent anomalies are variations of an effective action and obey the Wess–Zumino consistency condition."
    - "Covariant anomalies transform covariantly under gauge transformations but are not, by themselves, the ordinary variation of a local effective action."
  active:
    - "The consistent/covariant distinction remains important in anomaly inflow, hydrodynamics, chiral transport, lattice chiral fermions, and modern higher-form or generalized-symmetry anomaly discussions."
---

## Summary

The same anomaly can be written in two common local forms.

A **consistent anomaly** is obtained by varying the quantum effective action:

$$
\delta_\alpha W[A]=\int_{M_d}\alpha^a\,\mathcal A^{a}_{\rm cons}[A].
$$

Because it comes from an action, it obeys the **Wess–Zumino consistency condition**. The price is that $\mathcal A_{\rm cons}$ need not transform covariantly under gauge transformations.

A **covariant anomaly** is written in a manifestly gauge-covariant way, schematically

$$
\mathcal A_{\rm cov}\sim \operatorname{tr}(\alpha F^n).
$$

The price is that it is not the ordinary variation of the same effective action. It is obtained by modifying the current by a local Bardeen–Zumino current.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing the effective action leading to a consistent current and consistent anomaly. Adding a Bardeen-Zumino local polynomial gives a covariant current and covariant anomaly. Both representatives encode the same anomaly class and inflow data.](/figures/symmetry-anomalies-topology/consistent-covariant-anomaly-map.svg)

<figcaption>

The consistent anomaly is the variation of $W[A]$ and satisfies Wess–Zumino consistency. Adding the local Bardeen–Zumino current gives a covariant current and a covariant anomaly. The representative changes; the anomaly class does not.

</figcaption>
</figure>

The distinction is not pedantry. If you are checking integrability of the effective action, use the consistent anomaly. If you are writing a local Ward identity that should transform covariantly under background gauge transformations, use the covariant anomaly. If you are matching anomalies across descriptions, keep track of which representative you are using.

## Prerequisites

Read [Triangle Anomaly](/symmetry-anomalies-topology/anomalies/triangle-anomaly/), [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), [Mixed Anomalies](/symmetry-anomalies-topology/anomalies/mixed-anomalies/), and [BRST Cohomology](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-cohomology/) first.

You should be comfortable with background gauge transformations,

$$
\delta_\alpha A=D\alpha,
$$

and with the idea that local counterterms can move an anomaly among Ward identities without changing the anomaly class.

## Core idea

Suppose a chiral theory is coupled to a background gauge field $A$. Integrating out the fermions gives an effective action $W[A]$. If the theory is anomalous, then

$$
\delta_\alpha W[A]\ne0.
$$

This variation defines the consistent anomaly.

The adjective **consistent** means “consistent with being the variation of a functional.” It does not mean “physically consistent gauge theory.” In fact, a nonzero consistent anomaly for a dynamical gauge symmetry usually means the theory is inconsistent unless the anomaly cancels.

Because gauge transformations form an algebra, two successive variations of $W[A]$ must obey that algebra. This gives the Wess–Zumino consistency condition. For gauge parameters $\alpha$ and $\beta$,

$$
\delta_\alpha\mathcal A_{\rm cons}(\beta)
-\delta_\beta\mathcal A_{\rm cons}(\alpha)
=\mathcal A_{\rm cons}([\alpha,\beta]),
$$

up to conventional factors of $i$ depending on Hermitian versus anti-Hermitian generators.

The consistent anomaly therefore has an integrability property. But its local expression often looks ugly and is not gauge covariant.

The covariant anomaly repairs that aesthetic problem. One defines

$$
J^\mu_{\rm cov}=J^\mu_{\rm cons}+J^\mu_{\rm BZ},
$$

where $J^\mu_{\rm BZ}$ is a local Bardeen–Zumino polynomial built from $A$ and $F$. Then

$$
D_\mu J^\mu_{\rm cov}=\mathcal A_{\rm cov},
$$

with $\mathcal A_{\rm cov}$ transforming covariantly.

## Setup and conventions

We use Hermitian generators and

$$
D_\mu=\partial_\mu-iA_\mu,
\qquad
A_\mu=A_\mu^aT^a.
$$

In differential-form notation, write

$$
A=A_\mu dx^\mu,
\qquad
F=dA-iA\wedge A.
$$

Many anomaly references use anti-Hermitian generators, in which the same formulas appear with different factors of $i$ and different signs. In this page, coefficients are mostly schematic unless a convention is explicitly stated. The distinction between consistent and covariant representatives is independent of these choices.

The effective action defines the consistent current by

$$
\delta W[A]=\int d^dx\,\langle J^{\mu a}_{\rm cons}\rangle\delta A^a_\mu.
$$

If the gauge field is a background field, the anomalous Ward identity is a statement about the non-invariance of $W[A]$. If the gauge field is dynamical, the same non-invariance would spoil the gauge redundancy unless all gauge-anomaly contributions cancel.

:::note[Convention-sensitive source note]
The words “consistent” and “covariant” refer to representatives of the same anomaly class, not to two different physical anomalies. Coefficients differ between references because authors choose different normalizations for generators, $F$, $\epsilon^{\mu\nu\rho\sigma}$, chirality, and $W$ versus $W_E$. Always compare the descent convention before comparing factors such as $1/24\pi^2$ or $1/32\pi^2$.
:::

## Consistent anomalies

A consistent anomaly is defined by

$$
\delta_\alpha W[A]=\mathcal A_{\rm cons}(\alpha;A),
$$

where $\mathcal A_{\rm cons}$ is linear in the gauge parameter $\alpha$.

Because the gauge transformations satisfy

$$
[\delta_\alpha,\delta_\beta]=\delta_{[\alpha,\beta]},
$$

we must have

$$
\delta_\alpha\delta_\beta W
-\delta_\beta\delta_\alpha W
=\delta_{[\alpha,\beta]}W.
$$

Therefore

$$
\delta_\alpha\mathcal A_{\rm cons}(\beta;A)
-\delta_\beta\mathcal A_{\rm cons}(\alpha;A)
=\mathcal A_{\rm cons}([\alpha,\beta];A).
$$

This is the Wess–Zumino consistency condition.

In BRST language, replace the gauge parameter by a ghost $c$. The consistent anomaly is a local ghost-number-one functional $\mathcal A_{\rm cons}[c,A]$ satisfying

$$
s\mathcal A_{\rm cons}=0,
$$

modulo anomalies of the form

$$
\mathcal A_{\rm cons}=s\mathcal B
$$

that can be removed by local counterterms. Thus consistent anomalies are BRST cohomology classes at ghost number one.

This is why consistent anomalies are the natural output of descent equations and cohomological classifications.

## Covariant anomalies

A covariant anomaly is arranged to transform covariantly under gauge transformations. In $d=2n$ dimensions, its schematic form is

$$
\mathcal A_{\rm cov}(\alpha;A)
\propto\int_{M_{2n}}\operatorname{tr}(\alpha F^n).
$$

For an abelian chiral anomaly in four dimensions, one often summarizes the relation by saying:

$$
\mathcal A_{\rm cov}=3\,\mathcal A_{\rm cons}
$$

in a common normalization. Do not memorize this as a universal law. The ratio depends on dimension and on the precise anomaly being compared. The durable point is that the covariant expression is simpler and gauge covariant, while the consistent expression is integrable as a variation of $W[A]$.

The covariant current is

$$
J^\mu_{\rm cov}=J^\mu_{\rm cons}+J^\mu_{\rm BZ}.
$$

The Bardeen–Zumino current is local in the background fields. It is not obtained by varying an ordinary gauge-invariant local counterterm in the same way as $J_{\rm cons}$; it is the current-level correction that converts the consistent representative into the covariant representative.

The covariant anomaly is the one you want when writing equations that should transform cleanly under gauge transformations:

$$
D_\mu J^\mu_{\rm cov}=\mathcal A_{\rm cov},
\qquad
\mathcal A_{\rm cov}\mapsto g\mathcal A_{\rm cov}g^{-1}.
$$

## Bardeen–Zumino current

The relation between the two currents is local:

$$
J_{\rm cov}=J_{\rm cons}+J_{\rm BZ}.
$$

Here $J_{\rm BZ}$ is built from Chern–Simons-like polynomials in the background connection. Its divergence accounts for the difference between the two anomaly representatives:

$$
\mathcal A_{\rm cov}=\mathcal A_{\rm cons}+D_\mu J^\mu_{\rm BZ}.
$$

This formula is schematic: for nonabelian symmetries, the current and anomaly carry adjoint indices, and the derivative is covariant.

The Bardeen–Zumino construction is best understood through inflow. A bulk Chern–Simons form has a boundary variation that gives the consistent anomaly. Varying the bulk action with respect to the boundary value of the gauge field also produces a boundary current contribution. That local contribution is the Bardeen–Zumino current, and it is what converts consistent boundary currents into covariant ones.

A useful memory aid is:

$$
\begin{array}{ccl}
\text{variation of boundary effective action} &\Rightarrow& \text{consistent current},\\
\text{variation of bulk-plus-boundary inflow system} &\Rightarrow& \text{covariant current}.
\end{array}
$$

## Descent viewpoint

Let $I_{2n+2}$ be the anomaly polynomial. The descent equations are

$$
I_{2n+2}=dI_{2n+1}^{(0)},
\qquad
\delta_\alpha I_{2n+1}^{(0)}=dI_{2n}^{(1)}(\alpha,A).
$$

The consistent anomaly is

$$
\mathcal A_{\rm cons}(\alpha;A)=2\pi i\int_{M_{2n}}I_{2n}^{(1)}(\alpha,A),
$$

again up to convention. This is the descent representative that automatically satisfies Wess–Zumino consistency.

The covariant anomaly is obtained by a different representative involving $F^n$ directly. It is not the same descent form $I_{2n}^{(1)}$, but it represents the same underlying characteristic class.

In a sentence:

$$
\text{consistent anomaly} = \text{descent variation},
\qquad
\text{covariant anomaly} = \text{gauge-covariant representative}.
$$

## Two-dimensional abelian example

For a single chiral fermion in two dimensions coupled to an abelian background field, the consistent and covariant divergences differ by a local current. Suppressing chirality signs and charge factors, one commonly writes the relation schematically as

$$
\partial_\mu J^\mu_{\rm cons}\sim \epsilon^{\mu\nu}\partial_\mu A_\nu,
$$

while

$$
\partial_\mu J^\mu_{\rm cov}\sim \epsilon^{\mu\nu}F_{\mu\nu}.
$$

Since

$$
\epsilon^{\mu\nu}F_{\mu\nu}=2\epsilon^{\mu\nu}\partial_\mu A_\nu,
$$

the two expressions differ by a numerical factor in common normalizations. That factor is not the lesson. The lesson is that the consistent expression is tied to $\delta W$, while the covariant expression is tied to a covariantly transforming current.

For abelian symmetries, Wess–Zumino consistency looks trivial because the gauge algebra is abelian. The distinction still matters because the current obtained by varying the effective action is not the same as the covariant current used in many local transport and inflow formulas.

## Four-dimensional nonabelian example

In four dimensions, the consistent anomaly for a left-handed Weyl fermion has the schematic structure

$$
\mathcal A_{\rm cons}(\alpha;A)
\sim
\int\operatorname{tr}\left[
\alpha\,d\left(A\,dA+\frac12 A^3\right)
\right],
$$

where products are wedge products and normalization depends on generator conventions.

This expression is not manifestly covariant. It contains $A$ explicitly, not only $F$. That is exactly what one expects from a descent form.

The covariant anomaly has the simpler schematic form

$$
\mathcal A_{\rm cov}(\alpha;A)
\sim
\int\operatorname{tr}(\alpha F\wedge F).
$$

This expression transforms covariantly. It is the natural local formula for

$$
D_\mu J^\mu_{\rm cov}.
$$

The two are connected by the Bardeen–Zumino polynomial.

## Bardeen counterterms versus Bardeen–Zumino currents

Two related names can cause confusion.

A **Bardeen counterterm** is a local term added to the effective action to move an anomaly between different currents. The classic use is the vector/axial system: choose a counterterm so that the vector gauge current is conserved and the axial current carries the anomaly.

A **Bardeen–Zumino current** is the local current polynomial that relates the consistent and covariant currents:

$$
J_{\rm cov}=J_{\rm cons}+J_{\rm BZ}.
$$

Both are local-polynomial technology. But they answer different questions.

The Bardeen counterterm asks:

$$
\text{Which Ward identity should carry the anomaly?}
$$

The Bardeen–Zumino current asks:

$$
\text{Which representative of the same anomalous current should I use?}
$$

In a dynamical gauge theory, one must choose counterterms so that all gauge redundancies are non-anomalous. In a background-field problem, one may deliberately choose a scheme that makes one global symmetry manifest at the expense of another.

## Which current is physical?

The answer depends on the question.

The consistent current is the source derivative:

$$
J_{\rm cons}=\frac{\delta W}{\delta A}.
$$

It is the right object when discussing variational principles, effective actions, Ward identities as variations of $W$, and Wess–Zumino consistency.

The covariant current transforms cleanly under gauge transformations. It is often the right object for local response formulas, hydrodynamic constitutive relations, chiral magnetic and vortical effects, and inflow-cancelled boundary currents.

Neither current is “fake.” They are different representatives. A careful calculation must say which one it uses.

A compact comparison is:

| Feature | Consistent current/anomaly | Covariant current/anomaly |
|---|---|---|
| Defined by varying $W[A]$ | yes | not directly |
| Satisfies Wess–Zumino consistency | yes | not in the same sense |
| Transforms covariantly | not generally | yes |
| Natural in BRST cohomology | yes | less directly |
| Natural in local response/inflow | sometimes | yes |
| Related by local Bardeen–Zumino term | yes | yes |

## Gauge anomaly cancellation

For a dynamical gauge symmetry, the anomaly must vanish as a class. It is not enough to make a noncovariant expression look nicer.

If the consistent anomaly cancels among all fermions, then the covariant anomaly cancels too. Conversely, if the covariant anomaly class is nonzero, there is no clever choice of Bardeen–Zumino current that makes the gauge theory consistent.

The cancellation condition is a statement about the anomaly class, such as

$$
\sum_i\operatorname{tr}_{R_i}(T^a\{T^b,T^c\})=0
$$

for four-dimensional perturbative nonabelian gauge anomalies. The consistent/covariant distinction is about representatives after the class has been computed.

## Relation to global anomalies and global symmetries

The consistent/covariant distinction is mainly a local, perturbative anomaly distinction. It lives in the world of infinitesimal transformations, local functionals, and descent.

Global anomalies under large transformations require additional data, such as eta invariants, determinant-line holonomies, or mapping tori. A global anomaly may not be visible in a local consistent-versus-covariant comparison.

For global symmetries, either representative may be useful. If the symmetry is not gauged, an anomaly is not an inconsistency. The choice of representative becomes a choice of how to describe anomalous background response. This is especially important in mixed anomalies, where counterterms can move the anomaly from one global current to another.

## Common pitfalls

**Thinking “consistent” means anomaly-free.** It does not. It means the anomaly obeys the consistency condition required of a variation of $W[A]$.

**Thinking “covariant” means more correct.** Covariance is useful, but the covariant anomaly is not the direct variation of the ordinary effective action. For some questions, the consistent representative is the correct one.

**Comparing coefficients without identifying the representative.** A factor-of-two or factor-of-three disagreement often means one source uses the consistent anomaly while another uses the covariant anomaly.

**Adding Bardeen–Zumino currents and claiming the anomaly disappeared.** The representative changed. The anomaly class did not.

**Confusing Bardeen counterterms with Bardeen–Zumino currents.** Counterterms move anomalies between symmetries. Bardeen–Zumino currents move between consistent and covariant representatives of a current.

**Using covariant anomalies inside Wess–Zumino consistency checks.** Wess–Zumino consistency is naturally a condition on the consistent anomaly.

## Relations to other pages

This page refines the anomaly language introduced in [Triangle Anomaly](/symmetry-anomalies-topology/anomalies/triangle-anomaly/) and [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/). It also explains why [Mixed Anomalies](/symmetry-anomalies-topology/anomalies/mixed-anomalies/) can be moved among currents by local counterterms without being removed.

It connects to [BRST Cohomology](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-cohomology/) because consistent anomalies are ghost-number-one BRST cohomology classes. It connects to [Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/) because the difference between currents is local and affects coincident-point Ward identities.

The next natural topic is the Wess–Zumino consistency condition itself, followed by the anomaly-polynomial and descent machinery that produces consistent representatives systematically.

## Research status

The distinction between consistent and covariant anomalies is settled and standard. It is part of the working language of chiral gauge theory, anomaly inflow, and BRST cohomology.

It remains actively useful in modern contexts: anomalous hydrodynamics, chiral kinetic theory, edge modes of topological phases, lattice constructions of chiral fermions, anomaly inflow in systems with boundaries, and generalized-symmetry analogues where “current” may mean a higher-form or defect current.

In frontier settings, the old lesson remains valuable: before arguing about coefficients, first identify the representative.

## Exercises

### Exercise 1: Derive Wess–Zumino consistency

Let

$$
\delta_\alpha W=\mathcal A(\alpha;A).
$$

Assume gauge transformations obey

$$
[\delta_\alpha,\delta_\beta]=\delta_{[\alpha,\beta]}.
$$

Derive the Wess–Zumino consistency condition for $\mathcal A$.

<details><summary><strong>Solution</strong></summary>

Apply the commutator to $W$:

$$
[\delta_\alpha,\delta_\beta]W
=\delta_\alpha\mathcal A(\beta;A)
-\delta_\beta\mathcal A(\alpha;A).
$$

But the gauge algebra says

$$
[\delta_\alpha,\delta_\beta]W
=\delta_{[\alpha,\beta]}W
=\mathcal A([\alpha,\beta];A).
$$

Therefore

$$
\delta_\alpha\mathcal A(\beta;A)
-\delta_\beta\mathcal A(\alpha;A)
=\mathcal A([\alpha,\beta];A).
$$

This is Wess–Zumino consistency.

</details>

### Exercise 2: Abelian consistency

Why does the Wess–Zumino consistency condition simplify for an abelian gauge symmetry?

<details><summary><strong>Solution</strong></summary>

For an abelian gauge symmetry,

$$
[\alpha,\beta]=0.
$$

The consistency condition becomes

$$
\delta_\alpha\mathcal A(\beta;A)
-\delta_\beta\mathcal A(\alpha;A)=0.
$$

This is an integrability condition: the anomaly must be compatible with being a second variation of a functional $W[A]$. It is simpler than in the nonabelian case, but it is not empty.

</details>

### Exercise 3: Current shift and anomaly shift

Suppose

$$
J^\mu_{\rm cov}=J^\mu_{\rm cons}+J^\mu_{\rm BZ}.
$$

Show schematically how the divergence of the anomaly changes.

<details><summary><strong>Solution</strong></summary>

Taking a covariant divergence gives

$$
D_\mu J^\mu_{\rm cov}
=D_\mu J^\mu_{\rm cons}+D_\mu J^\mu_{\rm BZ}.
$$

If

$$
D_\mu J^\mu_{\rm cons}=\mathcal A_{\rm cons},
$$

then

$$
D_\mu J^\mu_{\rm cov}
=\mathcal A_{\rm cons}+D_\mu J^\mu_{\rm BZ}.
$$

Thus

$$
\mathcal A_{\rm cov}
=\mathcal A_{\rm cons}+D_\mu J^\mu_{\rm BZ}.
$$

The additional term is local in background fields and changes the representative, not the anomaly class.

</details>

### Exercise 4: Which representative should be used?

For each task, choose “consistent” or “covariant” and explain briefly:

1. Checking Wess–Zumino consistency.
2. Writing a gauge-covariant hydrodynamic current equation.
3. Taking a functional derivative of $W[A]$.
4. Matching anomaly inflow to a boundary response current.

<details><summary><strong>Solution</strong></summary>

1. Use the consistent anomaly. Wess–Zumino consistency is the integrability condition for variations of $W[A]$.
2. Usually use the covariant anomaly. Hydrodynamic equations are often organized in covariant form.
3. Use the consistent current. By definition, $J_{\rm cons}=\delta W/\delta A$.
4. Often use the covariant current after including the Bardeen–Zumino inflow contribution, while keeping track of the consistent anomaly as the variation of the boundary effective action.

</details>

## References

- W. A. Bardeen, “Anomalous Ward Identities in Spinor Field Theories,” *Physical Review* **184** (1969).
- J. Wess and B. Zumino, “Consequences of Anomalous Ward Identities,” *Physics Letters B* **37** (1971).
- B. Zumino, Y.-S. Wu, and A. Zee, “Chiral Anomalies, Higher Dimensions, and Differential Geometry,” *Nuclear Physics B* **239** (1984).
- W. A. Bardeen and B. Zumino, “Consistent and Covariant Anomalies in Gauge and Gravitational Theories,” *Nuclear Physics B* **244** (1984).
- R. Stora, “Algebraic Structure and Topological Origin of Anomalies.”
- S. Weinberg, *The Quantum Theory of Fields*, Volume II, sections on consistency conditions and BRST cohomology.
- M. Srednicki, *Quantum Field Theory*, sections on chiral gauge theories and anomalies.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Chapter 30.
- R. A. Bertlmann, *Anomalies in Quantum Field Theory*.

## Version history

- 2026-06-18: First polished draft. Added Wess–Zumino consistency derivation, Bardeen–Zumino current explanation, descent viewpoint, two- and four-dimensional examples, representative table, and exercises.
