---
title: "BV Formalism"
description: "Introduces the Batalin–Vilkovisky field–antifield formalism: extended fields, antifields, the antibracket, the BV differential, and the master action."
sidebar:
  label: "BV Formalism"
  order: 3
level: Advanced
status: "Polished draft"
source: "Batalin–Vilkovisky; Henneaux–Teitelboim; Gomis–París–Samuel; Barnich–Brandt–Henneaux"
topics:
  - Batalin–Vilkovisky formalism
  - antifields
  - antibracket
  - gauge theory
  - BRST cohomology
canonicalTopics:
  - bv-formalism
  - antifields
  - antibracket
  - master-action
  - gauge-cohomology
researchStatus:
  established:
    - "The BV formalism gives a systematic cohomological encoding of gauge symmetries, equations of motion, gauge algebra, and gauge-fixing data for perturbative gauge theory."
  active:
    - "Infinite-dimensional analytic foundations, nonperturbative gauge fixing, boundaries, and global quotient geometry require additional structure beyond the local BV complex."
---

## Summary

The Batalin–Vilkovisky formalism, often called the **field–antifield formalism**, is the systematic extension of BRST theory that treats gauge redundancy, equations of motion, gauge algebra, and gauge fixing in one cohomological package. Its central move is deliberately counterintuitive: instead of reducing the field space by gauge transformations, BV first enlarges the field space.

Starting from fields and ghosts $\Phi^A$, BV introduces antifields $\Phi_A^*$ with opposite parity and shifted ghost number. The extended space carries an odd Poisson bracket, the **BV antibracket**,

$$
(F,G),
$$

and a degree-zero functional $S_{\mathrm{BV}}$ called the **BV action** or **master action**. The classical BV differential is then

$$
s_{\mathrm{BV}}F=(S_{\mathrm{BV}},F).
$$

The next page studies the condition that makes this a genuine differential:

$$
(S_{\mathrm{BV}},S_{\mathrm{BV}})=0.
$$

This page explains the ingredients of the formalism, how they extend the BRST complex, what antifields mean, and why BV is the right language for general gauge theories.

:::note[Status]
BV is a rigorous algebraic framework for local and perturbative gauge theory. It is not, by itself, a nonperturbative construction of four-dimensional Yang–Mills theory, nor a global solution of all gauge-fixing problems.
:::

## Prerequisites

You should first read [Gauge Symmetry as Redundancy](/rigorous-qft/bv-brst-gauge-theory/gauge-symmetry-as-redundancy-rigorous-view/) and [BRST Complex](/rigorous-qft/bv-brst-gauge-theory/brst-complex/). The formal-series viewpoint in [Perturbative QFT as Formal Power Series](/rigorous-qft/perturbative-algebraic-qft/perturbative-qft-as-formal-power-series/) explains why this chapter works order by order. The pages on [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/) and [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/) give the perturbative algebraic setting where BV is often used.

## Core idea

Gauge theory has two linked problems.

First, physical configurations are not points of the naive field space $\Phi$ but gauge-equivalence classes. Second, the Euler–Lagrange equations are not independent, because gauge invariance implies Noether identities. Ordinary BRST handles the infinitesimal gauge quotient for simple closed algebras, but it does not by itself fully resolve the stationary surface of the action or encode more complicated gauge algebras.

BV solves this by replacing the naive quotient by a derived or cohomological object. In modern language, the minimal BV space is locally modeled on a shifted cotangent space

$$
\mathcal F_{\mathrm{BV}}
    =T^*[-1]\mathcal F_{\mathrm{ext}},
$$

where $\mathcal F_{\mathrm{ext}}$ is the space of original fields together with ghosts. The shift $[-1]$ is what makes the canonical bracket odd.

<figure class="doc-figure" style="--figure-width: 46rem;">

![BV fields, antifields, antibracket, and master action](/figures/rigorous-qft/bv-antifield-extension.svg)

<figcaption>

The BV formalism enlarges the BRST field space by adding antifields. The antibracket pairs each field or ghost with its antifield, and the master action $S_{\mathrm{BV}}$ generates the BV differential $s_{\mathrm{BV}}=(S_{\mathrm{BV}},-)$.

</figcaption>
</figure>

The geometric slogan is therefore:

$$
\text{BV formalism}
= \text{odd symplectic resolution of the gauge quotient}.
$$

This slogan is useful, but the concrete formulas are what make the formalism usable.

## Setup and conventions

Let $M$ be spacetime and let $\phi^i$ denote the original classical fields. Gauge transformations are written schematically as

$$
\delta_\epsilon \phi^i
  = R^i_\alpha(\phi)\epsilon^\alpha,
$$

where $\epsilon^\alpha$ are gauge parameters. In the BRST complex one replaces $\epsilon^\alpha$ by ghosts $c^\alpha$ of ghost number $+1$.

BV collects fields, ghosts, and possible nonminimal variables into a list

$$
\Phi^A=(\phi^i,c^\alpha,\bar c_\alpha,b_\alpha,\ldots).
$$

For every $\Phi^A$ there is an antifield $\Phi_A^*$. The ghost number convention used here is

$$
\operatorname{gh}(\Phi_A^*)
  =-1-\operatorname{gh}(\Phi^A).
$$

The parity is shifted by one:

$$
\epsilon(\Phi_A^*)
  =\epsilon(\Phi^A)+1
  \pmod 2.
$$

For an ordinary bosonic Yang–Mills connection $A_\mu$ and its ghost $c$, this gives the minimal table.

| Variable | Role | Ghost number | Parity |
|---|---|---:|---:|
| $A_\mu$ | gauge field | $0$ | even |
| $c$ | ghost | $+1$ | odd |
| $A^{*\mu}$ | antifield for $A_\mu$ | $-1$ | odd |
| $c^*$ | antifield for $c$ | $-2$ | even |

The word **antifield** does not mean antiparticle. An antifield is a dual coordinate in the shifted cotangent direction. It records equations of motion, gauge variations, and higher gauge-algebra data.

## The BV antibracket

The BV antibracket is the canonical odd Poisson bracket on fields and antifields. In Darboux coordinates it is characterized by

$$
(\Phi^A(x),\Phi_B^*(y))
  =\delta^A_B\, \delta(x-y),
$$

with the remaining basic brackets zero, up to the usual graded signs.

For local functionals $F$ and $G$, one common convention is

$$
(F,G)
=
\sum_A\int_M d^dx\,
\left(
  \frac{\delta^R F}{\delta \Phi^A(x)}
  \frac{\delta^L G}{\delta \Phi_A^*(x)}
  -
  \frac{\delta^R F}{\delta \Phi_A^*(x)}
  \frac{\delta^L G}{\delta \Phi^A(x)}
\right),
$$

with left and right variational derivatives inserted to control signs. Different sources place some signs elsewhere. What matters invariantly is that the bracket has ghost number $+1$, odd parity, and satisfies the graded Jacobi identity.

If $S_{\mathrm{BV}}$ has ghost number zero and even parity, then

$$
s_{\mathrm{BV}}F=(S_{\mathrm{BV}},F)
$$

has ghost number $+1$ and odd parity. Thus the BV action generates a BRST-like differential, provided the classical master equation holds.

## Antifields as sources for BRST variations

For a simple closed gauge algebra, the first practical meaning of antifields is this:

$$
S_{\mathrm{BV}}
  = S_0[\phi]
    +\int_M \phi_i^* s\phi^i
    +\int_M c_\alpha^* sc^\alpha
    +\cdots .
$$

The dots are not decorative. They are absent only in the simplest cases. In general they encode field-dependent structure functions, open algebras, reducibility, and higher homotopy data.

For Yang–Mills theory, using the BRST convention

$$
sA_\mu=D_\mu c,
\qquad
sc=-\frac12[c,c],
$$

the minimal BV action is

$$
S_{\mathrm{BV}}
=
S_{\mathrm{YM}}
+
\int_M d^dx\,\operatorname{tr}
\left(
  A^{*\mu}D_\mu c
  -\frac12 c^*[c,c]
\right).
$$

Taking the antibracket with $S_{\mathrm{BV}}$ recovers the BRST transformations of $A_\mu$ and $c$:

$$
(S_{\mathrm{BV}},A_\mu)=D_\mu c,
\qquad
(S_{\mathrm{BV}},c)=-\frac12[c,c],
$$

up to the sign convention chosen for the antibracket. This is why antifields are often introduced in perturbative gauge theory as “sources for BRST transformations.” That phrase is correct but incomplete: geometrically they are coordinates on the shifted cotangent resolution.

## Antifields as a Koszul–Tate resolution

Antifields also resolve the equations of motion. Let

$$
E_i(S_0)=\frac{\delta S_0}{\delta\phi^i}
$$

be the Euler–Lagrange expressions. The first antifield differential, called the **Koszul–Tate differential**, has the schematic form

$$
\delta_{\mathrm{KT}}\phi_i^*
  = E_i(S_0),
\qquad
\delta_{\mathrm{KT}}\phi^i=0.
$$

Its purpose is to implement the stationary surface

$$
E_i(S_0)=0
$$

cohomologically rather than by literally quotienting functions. Gauge theories have Noether identities among the $E_i(S_0)$, so the resolution must continue: ghost antifields encode those identities, higher ghost antifields encode reducibility identities, and so on.

This is the deeper reason BV is better than ordinary BRST for general gauge theory. It does not merely encode the gauge orbits; it also encodes the equations of motion and their relations.

## Minimal and nonminimal sectors

The **minimal BV sector** contains the original fields, ghosts, and the antifields required by the gauge structure. For an irreducible gauge theory with a closed algebra, it contains

$$
(\phi^i,c^\alpha;\phi_i^*,c_\alpha^*).
$$

Gauge fixing usually requires a **nonminimal sector**. For a bosonic gauge symmetry this often adds an antighost $\bar c_\alpha$, a Nakanishi–Lautrup field $b_\alpha$, and their antifields:

$$
(\bar c_\alpha,b_\alpha;\bar c^{*\alpha},b^{*\alpha}).
$$

The nonminimal pair is normally arranged as a contractible BRST doublet,

$$
s\bar c_\alpha=b_\alpha,
\qquad
sb_\alpha=0,
$$

so it does not change the physical cohomology. It gives enough variables to impose a gauge condition cleanly.

In BV language, gauge fixing is not the act of simply setting a condition $G(A)=0$. It is the choice of a Lagrangian submanifold in the odd symplectic BV space. In common coordinates this is implemented by a gauge-fixing fermion $\Psi$ of ghost number $-1$:

$$
\Phi_A^*=
\frac{\delta\Psi}{\delta\Phi^A}.
$$

This topic gets its own page later in the chapter because the same idea controls perturbative gauge independence.

## What BV adds beyond ordinary BRST

For Yang–Mills in flat spacetime with a familiar gauge condition, ordinary BRST can look sufficient. BV becomes essential as soon as one wants a framework that is stable under generalization.

**Open gauge algebras.** A gauge algebra is open if commutators of gauge transformations close only modulo the equations of motion. Then the BRST rule $sc=-\frac12[c,c]$ is not enough; extra antifield terms are required so that the full BV differential squares to zero.

**Reducible gauge symmetries.** A $p$-form gauge field has transformations with transformations among gauge parameters. For example, $B\mapsto B+d\Lambda$ is unchanged if $\Lambda\mapsto\Lambda+d\lambda$. BV handles this by introducing ghosts for ghosts and their antifields.

**Systematic deformation theory.** Consistent interactions of a gauge theory are governed by deformations of the BV master action. The first-order deformation problem becomes a BRST cohomology problem.

**Renormalization and anomalies.** In perturbative algebraic QFT, the BV differential organizes Ward identities, time-ordered products, renormalization ambiguities, and anomaly candidates. An anomaly is not merely a bad diagram; it is an obstruction to maintaining the quantum version of the master equation.

## A compact dictionary

| BV object | Operational meaning | Geometric meaning |
|---|---|---|
| $\Phi^A$ | fields, ghosts, nonminimal variables | coordinates on extended field space |
| $\Phi_A^*$ | sources for variations and equations | shifted cotangent coordinates |
| $(F,G)$ | antibracket | odd Poisson bracket |
| $S_{\mathrm{BV}}$ | action plus symmetry data | Hamiltonian for the cohomological vector field |
| $s_{\mathrm{BV}}=(S_{\mathrm{BV}},-)$ | BRST-BV differential | odd vector field on BV space |
| $(S_{\mathrm{BV}},S_{\mathrm{BV}})=0$ | consistency identities | classical master equation |
| gauge-fixing fermion $\Psi$ | choice of gauge | Lagrangian submanifold |

The key idea is that the BV action is not simply the original action with extra harmless variables. It is a single object whose Taylor coefficients encode the action, gauge transformations, gauge algebra, reducibility, and Noether identities.

## This is the most important part of this page

BV is the local homological replacement for the gauge quotient together with the equations of motion. Ordinary BRST remembers the infinitesimal gauge directions. BV remembers those directions, the stationary surface, Noether identities, and the algebraic relations among all of them.

The conceptual chain is

$$
\text{fields and ghosts}
\longrightarrow
\text{add antifields}
\longrightarrow
\text{odd antibracket}
\longrightarrow
S_{\mathrm{BV}}
\longrightarrow
s_{\mathrm{BV}}=(S_{\mathrm{BV}},-).
$$

Antifields are therefore not optional bookkeeping. They are the variables that let one write the full classical gauge structure as a single cohomological Hamiltonian system. Gauge fixing comes later as a choice of Lagrangian submanifold; it is not the definition of the BV theory.

## Common pitfalls

**Antifields are antiparticles.** They are not. Antifields are auxiliary graded coordinates paired with fields by the BV antibracket.

**BV is needed only for exotic theories.** BV is already useful for ordinary Yang–Mills because it records BRST symmetry, gauge fixing, renormalization identities, and anomaly candidates in one language. It becomes indispensable for open or reducible gauge systems.

**The BV action is just a gauge-fixed action.** The master action is usually written before gauge fixing. Gauge fixing is a later choice of Lagrangian submanifold or gauge-fixing fermion.

**The antibracket is the physical Poisson bracket.** The BV antibracket is an odd bracket on the extended field–antifield space. It is not the canonical equal-time Poisson bracket of classical mechanics.

**Classical master equation means the quantum theory exists.** The classical master equation is a consistency condition for the classical gauge structure. Quantum construction requires regularization, renormalization, and possibly the quantum master equation.

## Relations to other pages

The [BRST Complex](/rigorous-qft/bv-brst-gauge-theory/brst-complex/) page gives the first layer: ghosts and a nilpotent differential. The present page explains why antifields are added and how the BV action generates the full differential.

The next page, [Classical Master Equation](/rigorous-qft/bv-brst-gauge-theory/classical-master-equation/), studies the equation $(S_{\mathrm{BV}},S_{\mathrm{BV}})=0$ and unpacks the gauge identities it contains.

For renormalization, compare [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/) and [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/). For curved spacetime, compare [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/). For the later factorization-algebra viewpoint, BV will reappear as the natural input for perturbative classical field theory.

## Research status

At the algebraic and perturbative level, BV is one of the most robust languages for gauge theory. It is standard in perturbative gauge theory, perturbative algebraic QFT, deformation theory, topological field theory, and modern derived geometry formulations of field theory.

The main analytic caveat is infinite dimensionality. Formal BV geometry is clean in finite-dimensional or formal local models; actual functional integrals and global gauge quotients require choices of topology, regularization, boundary conditions, and renormalization. Nonperturbative Yang–Mills existence and mass gap are not solved by writing down a BV complex.

The main conceptual frontier is global structure: boundaries, defects, asymptotic symmetries, higher-form symmetries, stacks of fields, and derived moduli spaces all refine what “the gauge quotient” means.

## Exercises

### Exercise 1: ghost numbers of antifields

Let $\operatorname{gh}(\Phi_A^*)=-1-\operatorname{gh}(\Phi^A)$. Compute the ghost numbers of the antifields of a gauge field $A_\mu$, ghost $c$, antighost $\bar c$, and Nakanishi–Lautrup field $b$, where

$$
\operatorname{gh}(A_\mu)=0,
\qquad
\operatorname{gh}(c)=1,
\qquad
\operatorname{gh}(\bar c)=-1,
\qquad
\operatorname{gh}(b)=0.
$$

<details><summary><strong>Solution</strong></summary>

Apply the rule directly:

$$
\operatorname{gh}(A^{*\mu})=-1,
\qquad
\operatorname{gh}(c^*)=-2,
$$

and

$$
\operatorname{gh}(\bar c^*)=0,
\qquad
\operatorname{gh}(b^*)=-1.
$$

The antighost has ghost number $-1$, so its antifield has ghost number $0$. This is a useful reminder that antifield number and ghost number are different gradings.

</details>

### Exercise 2: recover the BRST rule from the Yang–Mills BV action

Using the schematic canonical rule

$$
(S_{\mathrm{BV}},\Phi^A)
  =\frac{\delta S_{\mathrm{BV}}}{\delta\Phi_A^*},
$$

show that

$$
S_{\mathrm{BV}}
=
S_{\mathrm{YM}}
+
\int d^dx\,\operatorname{tr}
\left(
  A^{*\mu}D_\mu c
  -\frac12 c^*[c,c]
\right)
$$

generates $sA_\mu=D_\mu c$ and $sc=-\frac12[c,c]$, up to the global sign convention for the antibracket.

<details><summary><strong>Solution</strong></summary>

Differentiate $S_{\mathrm{BV}}$ with respect to the antifield $A^{*\mu}$:

$$
\frac{\delta S_{\mathrm{BV}}}{\delta A^{*\mu}}
  =D_\mu c.
$$

Therefore

$$
(S_{\mathrm{BV}},A_\mu)=D_\mu c.
$$

Similarly,

$$
\frac{\delta S_{\mathrm{BV}}}{\delta c^*}
  =-\frac12[c,c],
$$

so

$$
(S_{\mathrm{BV}},c)=-\frac12[c,c].
$$

Different sources may place an overall sign in the definition of the bracket. Once that convention is fixed, the action and bracket must be adjusted together.

</details>

### Exercise 3: why an antifield for the ghost is necessary

Suppose one tried to write a Yang–Mills BV action with the term $\int A^*D c$ but no term involving $c^*$. Explain why this cannot generate the full BRST differential.

<details><summary><strong>Solution</strong></summary>

The term $\int A^*D c$ generates the transformation of $A_\mu$, because differentiating with respect to $A^*$ gives $D_\mu c$. But the transformation of the ghost is

$$
sc=-\frac12[c,c].
$$

To generate this transformation by the antibracket, the action must contain a term whose derivative with respect to $c^*$ is $-\frac12[c,c]$. That is precisely the term

$$
-\frac12\int c^*[c,c].
$$

This term records the Lie bracket of the gauge algebra inside the master action.

</details>

## References

### Standard first pass

- I. A. Batalin and G. A. Vilkovisky, “Gauge Algebra and Quantization,” *Physics Letters B* **102** (1981), 27–31. [doi:10.1016/0370-2693(81)90205-7](https://doi.org/10.1016/0370-2693(81)90205-7).
- I. A. Batalin and G. A. Vilkovisky, “Quantization of Gauge Theories with Linearly Dependent Generators,” *Physical Review D* **28** (1983), 2567–2582. [doi:10.1103/PhysRevD.28.2567](https://doi.org/10.1103/PhysRevD.28.2567). Erratum: *Physical Review D* **30** (1984), 508. [doi:10.1103/PhysRevD.30.508](https://doi.org/10.1103/PhysRevD.30.508).
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*, Princeton University Press, 1992. [doi:10.1515/9780691213866](https://doi.org/10.1515/9780691213866).
- J. Gomis, J. París, and S. Samuel, “Antibracket, Antifields and Gauge-Theory Quantization,” *Physics Reports* **259** (1995), 1–145. [arXiv:hep-th/9412228](https://arxiv.org/abs/hep-th/9412228), [doi:10.1016/0370-1573(94)00112-G](https://doi.org/10.1016/0370-1573(94)00112-G).

### Deeper references

- G. Barnich, F. Brandt, and M. Henneaux, “Local BRST Cohomology in Gauge Theories,” *Physics Reports* **338** (2000), 439–569. [arXiv:hep-th/0002245](https://arxiv.org/abs/hep-th/0002245), [doi:10.1016/S0370-1573(00)00049-1](https://doi.org/10.1016/S0370-1573(00)00049-1).
- G. Barnich, F. Brandt, and M. Henneaux, “Local BRST Cohomology in the Antifield Formalism: I. General Theorems,” *Communications in Mathematical Physics* **174** (1995), 57–92. [arXiv:hep-th/9405109](https://arxiv.org/abs/hep-th/9405109), [doi:10.1007/BF02099461](https://doi.org/10.1007/BF02099461).
- M. Alexandrov, M. Kontsevich, A. Schwarz, and O. Zaboronsky, “The Geometry of the Master Equation and Topological Quantum Field Theory,” *International Journal of Modern Physics A* **12** (1997), 1405–1429. [arXiv:hep-th/9502010](https://arxiv.org/abs/hep-th/9502010), [doi:10.1142/S0217751X97001031](https://doi.org/10.1142/S0217751X97001031).
- K. Costello and O. Gwilliam, *Factorization Algebras in Quantum Field Theory*, Cambridge University Press, 2021. See especially the BV interpretation of perturbative classical and quantum field theories.

## Version history

- **2026-07-01:** Initial polished draft. Introduced BV fields and antifields, antibracket, master action, Yang–Mills example, Koszul–Tate interpretation, and exercises.
