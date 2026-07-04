---
title: "Observables as Cohomology"
description: "Explains why physical observables in BRST-BV gauge theory are represented by cohomology classes rather than by arbitrary gauge-dependent functionals."
sidebar:
  label: "Observables as Cohomology"
  order: 7
level: Advanced
status: "Polished draft"
source: "Henneaux–Teitelboim; Barnich–Brandt–Henneaux; Gomis–París–Samuel; perturbative algebraic QFT literature"
topics:
  - observables
  - BRST cohomology
  - BV cohomology
  - local functionals
  - gauge invariance
canonicalTopics:
  - observables-as-cohomology
  - brst-cohomology
  - bv-cohomology
  - local-observables
  - gauge-invariant-observables
researchStatus:
  established:
    - "For local perturbative gauge theory, BRST-BV cohomology is the standard mathematical language for gauge-invariant observables, local deformations, counterterms, and anomaly candidates."
  active:
    - "Boundary observables, asymptotic charges, line operators, global quotient effects, and nonperturbative sectors require extra structure beyond the local BRST-BV cohomology of polynomial functionals."
---

## Summary

In a gauge theory, a physical observable is not an arbitrary function of the fields. It must be insensitive to changes of representative along gauge orbits, and in a field theory it is often meaningful only modulo the equations of motion and total derivatives. BRST-BV theory packages these qualifications into cohomology.

The minimal slogan is

$$
\text{physical observable}
\quad=\quad
\text{BRST-closed object modulo BRST-exact object}.
$$

For the BRST-BV differential $s$, a classical observable is represented by a ghost-number-zero class

$$
[\mathcal O]\in H^0(s),
\qquad
s\mathcal O=0,
\qquad
\mathcal O\sim \mathcal O+sK.
$$

For local Lagrangian densities or local integrated functionals in $d$ spacetime dimensions, the relevant object is usually cohomology modulo total derivatives:

$$
[a]\in H^{g,d}(s\mid d),
\qquad
sa+db=0,
\qquad
a\sim a+sm+dn.
$$

The degree $g=0$ part contains gauge-invariant local observables and counterterm candidates; the degree $g=1$ part contains possible anomaly classes. This page explains why cohomology, rather than equality of formulas, is the right language for observables in gauge theory.

:::note[Status]
This page describes the local and perturbative BRST-BV notion of observable. It does not claim that every physically important observable is local. Wilson lines, boundary charges, extended defects, and order parameters in distinct global sectors need additional data.
:::

## Prerequisites

Read [Gauge Symmetry as Redundancy](/rigorous-qft/bv-brst-gauge-theory/gauge-symmetry-as-redundancy-rigorous-view/), [BRST Complex](/rigorous-qft/bv-brst-gauge-theory/brst-complex/), [BV Formalism](/rigorous-qft/bv-brst-gauge-theory/bv-formalism/), and [Ghosts, Antifields, and Cohomology](/rigorous-qft/bv-brst-gauge-theory/ghosts-antifields-and-cohomology/) first. For the local-functional and renormalized-time-ordered-product viewpoint, it helps to know [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/) and [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/).

## Core idea

A gauge theory is described redundantly. If $\phi$ is a field configuration and $\phi^g$ is obtained by a gauge transformation, then $\phi$ and $\phi^g$ represent the same local physical configuration, at least when $g$ is a genuine gauge redundancy rather than an asymptotic or boundary symmetry.

A classical observable should therefore satisfy

$$
\mathcal O(\phi^g)=\mathcal O(\phi).
$$

Infinitesimally, if

$$
\delta_\epsilon\phi^i=R^i_\alpha(\phi)\epsilon^\alpha,
$$

then gauge invariance means

$$
R^i_\alpha(\phi)\frac{\delta \mathcal O}{\delta \phi^i}=0.
$$

BRST replaces the infinitesimal gauge parameter $\epsilon^\alpha$ by an odd ghost $c^\alpha$ and writes the same condition as

$$
s\mathcal O=0.
$$

This is only half of the story. In field theory, observables are also identified when they differ by terms that vanish on shell or by total derivatives. The BV antifields implement this identification homologically. That is why the correct object is not merely “gauge-invariant functions of fields,” but cohomology of the full BRST-BV differential.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Physical observables represented by BRST-BV cohomology classes](/figures/rigorous-qft/observables-as-cohomology.svg)

<figcaption>

The BRST-BV complex turns the gauge quotient, equations of motion, and integration by parts into a cohomology problem. Degree-zero cohomology represents physical observables, while local cohomology modulo $d$ organizes local densities, deformations, counterterms, and anomalies.

</figcaption>
</figure>

## Setup and conventions

Let $\mathcal F$ denote a space of fields, and let $S_0$ be a classical gauge-invariant action. The Euler–Lagrange expressions are

$$
E_i(\phi)=\frac{\delta S_0}{\delta\phi^i}.
$$

Gauge invariance implies Noether identities of the form

$$
R^i_\alpha(\phi)E_i(\phi)=0,
$$

up to signs, integrations by parts, and possible reducibility identities. The BV complex adds ghosts and antifields so that

$$
\Phi^A=(\phi^i,c^\alpha,\ldots),
\qquad
\Phi_A^*=(\phi_i^*,c_\alpha^*,\ldots).
$$

The BV differential is generated by the classical master action:

$$
sF=(S_{\mathrm{BV}},F),
\qquad
(S_{\mathrm{BV}},S_{\mathrm{BV}})=0.
$$

It has ghost number $+1$. A cohomology class of ghost number $g$ is represented by an expression $F$ satisfying

$$
sF=0,
\qquad
F\sim F+sG.
$$

For local differential forms, one also quotients by spacetime exterior derivatives. If $a$ is a local $p$-form of ghost number $g$, then

$$
sa+db=0,
\qquad
a\sim a+sm+dn.
$$

The corresponding class is denoted

$$
[a]\in H^{g,p}(s\mid d).
$$

In this notation, the form degree is displayed because a local density is a $d$-form.

## Why closure means gauge invariance

Start with a functional $F(\phi)$ depending only on the original fields. In a simple closed gauge algebra, the leading BRST transformation is

$$
s\phi^i=R^i_\alpha(\phi)c^\alpha.
$$

Therefore

$$
sF
 =\int dx\,
   \frac{\delta F}{\delta\phi^i(x)}
   R^i_\alpha(\phi)(x)c^\alpha(x).
$$

Since the ghosts are arbitrary odd variables replacing gauge parameters, the condition $sF=0$ says exactly that $F$ is invariant under infinitesimal gauge transformations.

For Yang–Mills theory, for example,

$$
sA_\mu=D_\mu c,
\qquad
sc=-\frac12[c,c],
\qquad
sF_{\mu\nu}=[F_{\mu\nu},c].
$$

Any invariant polynomial in the curvature is BRST-closed. For instance,

$$
s\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
=2\operatorname{tr}([F_{\mu\nu},c]F^{\mu\nu})=0,
$$

because the trace of a commutator vanishes. Closure is therefore the algebraic replacement for gauge invariance.

## Why exactness means no new observable

If $\mathcal O=sK$, then $\mathcal O$ is BRST-exact. Such an expression is treated as cohomologically trivial because it is a pure change along the resolution variables. The physical reason depends on the context.

Classically, the Koszul–Tate part of the BV differential identifies functionals that differ by equations of motion. In a simple irreducible theory one has schematically

$$
s\phi_i^*=E_i+\text{terms involving antifields and ghosts}.
$$

Thus an expression proportional to the Euler–Lagrange equations is exact in the BV complex. If

$$
F-G=\int dx\,K^i(x)E_i(x),
$$

then $F$ and $G$ represent the same on-shell observable, because their difference is implemented by an $s$-exact term involving antifields.

Quantum mechanically, the same idea becomes the statement that inserting an exact observable gives a Ward identity, provided the quantum master equation has no anomaly and the observable is treated in the renormalized quantum complex. The finite-dimensional model is

$$
\int_{\mathcal L} \widehat sK\,
  e^{iS/\hbar}=0,
$$

where $\mathcal L$ is a gauge-fixing Lagrangian submanifold and $\widehat s$ is the quantum BV differential. In local QFT this formula must be understood through renormalized products and formal power series, not as an ordinary Lebesgue integral over fields.

## Off-shell, on-shell, and local observables

There are three related but distinct notions.

An **off-shell gauge-invariant functional** is invariant under gauge transformations before imposing field equations. In simple BRST language it is closed under the longitudinal part $\gamma$:

$$
\gamma F=0.
$$

An **on-shell observable** is a gauge-invariant functional modulo the equations of motion. In BV language this is represented by $H^0(s)$, because the antifield part of $s$ implements the equations and Noether identities.

A **local observable density** is a local $d$-form $a$ considered modulo total derivatives. Its natural home is

$$
H^{0,d}(s\mid d).
$$

The distinction matters. A local density $a$ may fail to be strictly BRST-closed while its integral is closed because the failure is a total derivative:

$$
sa+db=0.
$$

This is the same mechanism behind descent equations for characteristic classes and anomalies. The integrated functional

$$
\int_M a
$$

is BRST-closed on a compact spacetime without boundary if the boundary term integrates to zero.

## The local cohomology table

For local perturbative gauge theory, the following groups appear repeatedly.

| Cohomology group | Typical meaning |
|---|---|
| $H^0(s)$ | Gauge-invariant on-shell observables in the chosen functional class. |
| $H^{0,d}(s\mid d)$ | Local observables, allowed invariant counterterms, and consistent local action deformations. |
| $H^{1,d}(s\mid d)$ | Candidate anomalies satisfying the Wess–Zumino consistency condition. |
| $H^{-1,d}(s\mid d)$ | Global symmetries and conserved currents in many standard settings. |
| $H^{g,p}(s\mid d)$ | Descent data and characteristic cohomology, depending on degree and model. |

The table is useful but not universal. Its interpretation depends on the class of local functionals, boundary conditions, spacetime topology, reducibility of the gauge symmetry, and whether one works classically or quantum mechanically.

## Example: Yang–Mills local observables

Let $G$ be a compact Lie group and let $A$ be a connection. The curvature is

$$
F=dA+\frac12[A,A].
$$

The BRST transformation is

$$
sA=Dc,
\qquad
sF=[F,c],
\qquad
sc=-\frac12[c,c].
$$

Gauge-invariant local polynomials built from $F$, covariant derivatives of $F$, matter fields in representations of $G$, and invariant tensors of the Lie algebra give BRST-closed local observables. For example,

$$
a=\operatorname{tr}(F\wedge *F)
$$

is closed because the trace kills the commutator. The topological density

$$
\operatorname{tr}(F\wedge F)
$$

is also closed and participates in descent equations. Locally,

$$
\operatorname{tr}(F\wedge F)=dQ_3(A),
$$

where $Q_3(A)$ is a Chern–Simons form, but $Q_3(A)$ is not gauge invariant. This is an important warning: being a total derivative in one complex is not the same as being trivial in the gauge-invariant cohomology.

## Quantum observables

At the quantum level the differential can receive corrections. In the finite-dimensional BV model, one writes

$$
\widehat sF=(S_\hbar,F)-i\hbar\Delta F,
$$

and quantum observables satisfy

$$
\widehat s\mathcal O=0,
\qquad
\mathcal O\sim \mathcal O+\widehat sK.
$$

In local QFT, the naive BV Laplacian $\Delta$ is ill-defined on local functionals. Perturbative algebraic QFT and related approaches replace the naive product and naive Laplacian by renormalized objects. The resulting statement is still cohomological: quantum observables are those that survive the renormalized Ward identities, and anomalies are obstructions to making the quantum differential square to zero.

This is why the classical cohomology is not merely decorative. It controls which quantum corrections are possible. If an obstruction appears in a trivial cohomology class, it can be removed by a counterterm. If it appears in a nontrivial anomaly class, the quantum theory cannot preserve the chosen gauge symmetry without changing the field content, interactions, or background assumptions.

## Extended and boundary observables

Local BRST cohomology is not the whole observable algebra of a gauge theory. Important examples lie outside the local polynomial class.

A Wilson loop,

$$
W_R(C)=\operatorname{tr}_R\,P
\exp\left(\oint_C A\right),
$$

is gauge invariant for a closed curve $C$, but it is nonlocal. It is not captured by the same local $H^{0,d}(s\mid d)$ computation that classifies local counterterms.

Boundary charges require even more care. A gauge transformation that is pure redundancy in the bulk can become physical at a boundary or at infinity. Then the statement “observable equals gauge-invariant cohomology class” must be refined by specifying which gauge transformations are quotiented and which become asymptotic symmetries.

In canonical language, the boundary issue is the difference between constraints that annihilate physical states and charges that act nontrivially on them. In covariant BRST-BV language, the same issue appears through boundary terms in the variational principle, the symplectic form, and the BRST current.

## Common pitfalls

**Every gauge-invariant formula is automatically a good quantum observable.** Gauge invariance is necessary but not always sufficient. The operator must also be renormalized, have controlled distributional behavior, and satisfy the quantum Ward identities.

**BRST-exact means numerically zero before choosing a state.** Exactness means cohomologically trivial. It becomes a vanishing statement only after applying a compatible expectation value or integrating under hypotheses that justify the corresponding Ward identity.

**Local cohomology contains Wilson lines.** Wilson lines and other extended defects are gauge-invariant observables, but they are not local functionals. They require separate treatment.

**$H^0(s)$ and $H^{0,d}(s\mid d)$ are interchangeable.** The first concerns functionals or expressions in a chosen complex. The second concerns local top forms modulo total derivatives. They answer related but different questions.

**Gauge invariance and gauge fixing are opposites.** Gauge fixing chooses representatives for computation. Observables are cohomology classes that should not depend on that choice, within the domain where the gauge fixing is valid.

## Relations to other pages

[Ghosts, Antifields, and Cohomology](/rigorous-qft/bv-brst-gauge-theory/ghosts-antifields-and-cohomology/) gives the grading conventions used here. [Quantum Master Equation](/rigorous-qft/bv-brst-gauge-theory/quantum-master-equation/) explains how the cohomological observable condition changes when the measure is included. [Gauge Fixing as a Lagrangian Submanifold](/rigorous-qft/bv-brst-gauge-theory/gauge-fixing-as-lagrangian-submanifold/) explains why different gauge-fixing choices should give the same values for cohomology classes.

The Perturbative Algebraic QFT chapter supplies the renormalized formal-series framework in which local interacting observables are constructed. The Algebraic QFT chapter gives the operator-algebraic viewpoint in which observables are assigned to spacetime regions rather than written as functions on field space.

## Research status

The BRST-BV classification of local observables, counterterms, deformations, and anomalies is a mature part of perturbative gauge theory. For Yang–Mills type theories, gravity, and many reducible gauge systems, the local cohomology literature gives powerful structural results.

The boundaries of the story are equally important. Local BRST-BV cohomology is not a nonperturbative construction of the observable algebra. It does not by itself solve the global topology of the gauge quotient, the Gribov problem, confinement, charged sectors, or the theory of extended operators. It is best understood as a rigorous local and perturbative control mechanism.

## Exercises

### Exercise 1: curvature polynomials are BRST-closed

Let $sA=Dc$, $sF=[F,c]$, and $sc=-\frac12[c,c]$. Show that $\operatorname{tr}(F\wedge F)$ is BRST-closed.

<details><summary><strong>Solution</strong></summary>

Using $sF=[F,c]$ and the graded Leibniz rule,

$$
s\operatorname{tr}(F\wedge F)
 =\operatorname{tr}([F,c]\wedge F+F\wedge [F,c]).
$$

The two terms combine into the trace of a commutator. By cyclicity of the invariant trace,

$$
\operatorname{tr}([c,F\wedge F])=0.
$$

Hence

$$
s\operatorname{tr}(F\wedge F)=0.
$$

This proves BRST closure. It does not by itself prove that the class is nontrivial; that is a question in the appropriate local cohomology.

</details>

### Exercise 2: equations of motion are cohomologically trivial

In a toy BV complex with fields $\phi^i$ and antifields $\phi_i^*$, suppose the Koszul–Tate part satisfies $\delta\phi_i^*=E_i$ and $\delta\phi^i=0$. Show that a functional difference of the form

$$
F-G=\int dx\,K^iE_i
$$

is $\delta$-exact, up to the signs forced by the grading.

<details><summary><strong>Solution</strong></summary>

Since $\delta\phi_i^*=E_i$, define

$$
H=\int dx\,K^i\phi_i^*.
$$

Ignoring the standard graded signs, which depend on the parity of $K^i$ and $\phi^i$, one obtains

$$
\delta H
 =\int dx\,K^i\delta\phi_i^*
  +\text{terms from }\delta K^i.
$$

If $K^i$ depends only on original fields, then $\delta K^i=0$ in this simplified complex, so

$$
\delta H=\int dx\,K^iE_i=F-G.
$$

Thus $F$ and $G$ represent the same on-shell class. The full BV differential refines this statement by adding gauge-orbit terms and higher identities.

</details>

### Exercise 3: why a boundary changes the answer

Suppose $a$ is a local density satisfying $sa+db=0$. Explain why $\int_M a$ is BRST-closed when $M$ is compact without boundary, but need not be BRST-closed when $\partial M\neq\varnothing$.

<details><summary><strong>Solution</strong></summary>

Apply $s$ to the integrated density:

$$
s\int_M a=\int_M sa=-\int_M db.
$$

If $M$ has no boundary, Stokes's theorem gives

$$
\int_M db=0.
$$

Thus $\int_M a$ is BRST-closed. If $M$ has a boundary, then

$$
\int_M db=\int_{\partial M} b.
$$

The boundary term can be nonzero. To recover BRST closure one must impose boundary conditions, add boundary degrees of freedom, modify the observable, or reinterpret the would-be gauge transformation as an actual boundary symmetry.

</details>

## References

### Standard references

- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*, Princeton University Press, 1992. [doi:10.1515/9780691213866](https://doi.org/10.1515/9780691213866).
- J. Gomis, J. París, and S. Samuel, “Antibracket, Antifields and Gauge-Theory Quantization,” *Physics Reports* **259** (1995), 1–145. [arXiv:hep-th/9412228](https://arxiv.org/abs/hep-th/9412228), [doi:10.1016/0370-1573(94)00112-G](https://doi.org/10.1016/0370-1573(94)00112-G).
- G. Barnich, F. Brandt, and M. Henneaux, “Local BRST Cohomology in Gauge Theories,” *Physics Reports* **338** (2000), 439–569. [arXiv:hep-th/0002245](https://arxiv.org/abs/hep-th/0002245), [doi:10.1016/S0370-1573(00)00049-1](https://doi.org/10.1016/S0370-1573(00)00049-1).
- O. Piguet and S. P. Sorella, *Algebraic Renormalization: Perturbative Renormalization, Symmetries and Anomalies*, Springer, 1995. [doi:10.1007/978-3-540-49192-7](https://doi.org/10.1007/978-3-540-49192-7).

### Perturbative and local-QFT references

- K. Fredenhagen and K. Rejzner, “Batalin–Vilkovisky Formalism in Perturbative Algebraic Quantum Field Theory,” *Communications in Mathematical Physics* **317** (2013), 697–725. [arXiv:1110.5232](https://arxiv.org/abs/1110.5232), [doi:10.1007/s00220-012-1601-1](https://doi.org/10.1007/s00220-012-1601-1).
- K. Costello, *Renormalization and Effective Field Theory*, Mathematical Surveys and Monographs **170**, American Mathematical Society, 2011. [doi:10.1090/surv/170](https://doi.org/10.1090/surv/170).
- K. Costello and O. Gwilliam, *Factorization Algebras in Quantum Field Theory*, Vol. 1, Cambridge University Press, 2016. [doi:10.1017/9781316678626](https://doi.org/10.1017/9781316678626).

## Version history

- **2026-07-01:** Initial polished draft.
