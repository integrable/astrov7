---
title: "Ghosts, Antifields, and Cohomology"
description: "Organizes the ghost, antifield, and grading conventions of BRST-BV theory and explains the cohomology groups that classify observables, counterterms, and anomalies."
sidebar:
  label: "Ghosts, Antifields, and Cohomology"
  order: 6
level: Advanced
status: "Polished draft"
source: "Henneaux–Teitelboim; Gomis–París–Samuel; Barnich–Brandt–Henneaux; algebraic renormalization literature"
topics:
  - ghosts
  - antifields
  - BRST cohomology
  - Koszul–Tate differential
  - local cohomology
canonicalTopics:
  - ghosts
  - antifields
  - brst-cohomology
  - koszul-tate-resolution
  - local-brst-cohomology
researchStatus:
  established:
    - "BRST-BV cohomology gives the standard local classification of gauge-invariant observables, consistent deformations, counterterms, and anomaly candidates in perturbative gauge theory."
  active:
    - "Boundary observables, global quotient effects, nonlocal operators, and nonperturbative sectors require refinements beyond the local cohomology of polynomial functionals."
---

## Summary

Ghosts and antifields are not optional decorations in the rigorous treatment of gauge theory. They are the variables that make the gauge quotient and the equations of motion visible as a cohomological object.

For a simple gauge theory the basic BRST-BV variables look like this:

| Variable | Meaning | Ghost number | Antifield number |
|---|---|---:|---:|
| $\phi^i$ | original fields | $0$ | $0$ |
| $c^\alpha$ | ghosts for gauge parameters | $1$ | $0$ |
| $\phi_i^*$ | antifields for equations and gauge transformations | $-1$ | $1$ |
| $c_\alpha^*$ | antifields for gauge-algebra data | $-2$ | $2$ |
| $\bar c_\alpha,b_\alpha$ | nonminimal gauge-fixing pair | $-1,0$ | $0,0$ |

The BRST-BV differential has ghost number $+1$. In many useful situations it decomposes schematically as

$$
s=\delta+\gamma+\text{higher terms},
$$

where $\delta$ is the Koszul–Tate part resolving the equations of motion and $\gamma$ is the longitudinal gauge part along gauge orbits.

The cohomology of this differential is the mathematical home of many familiar physical statements:

$$
\begin{array}{ccl}
H^0(s) &\rightsquigarrow& \text{physical observables},\\
H^{0,d}(s\mid d) &\rightsquigarrow& \text{local counterterms and deformations},\\
H^{1,d}(s\mid d) &\rightsquigarrow& \text{anomaly candidates}.
\end{array}
$$

This page explains the gradings, the role of ghosts and antifields, the double-complex picture, and the main cohomology groups used in perturbative gauge theory.

## Prerequisites

Read [BRST Complex](/rigorous-qft/bv-brst-gauge-theory/brst-complex/), [BV Formalism](/rigorous-qft/bv-brst-gauge-theory/bv-formalism/), [Classical Master Equation](/rigorous-qft/bv-brst-gauge-theory/classical-master-equation/), and [Quantum Master Equation](/rigorous-qft/bv-brst-gauge-theory/quantum-master-equation/) first. For local functionals modulo total derivatives, see [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/) and [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/).

## Core idea

Gauge theory contains two kinds of redundancy.

First, field configurations related by infinitesimal gauge transformations represent the same physical configuration. This is the quotient problem. Ghosts encode the directions along gauge orbits.

Second, the Euler–Lagrange equations are not independent. Gauge invariance implies Noether identities. Antifields encode these equations and identities homologically.

The BV complex combines both into a single differential graded object. In local coordinates, one should not imagine ghosts and antifields as mysterious particles. They are bookkeeping variables with precise grading rules. Their job is to make a singular quotient and a dependent system of equations into a computable cohomology problem.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Ghosts, antifields, and the BRST-BV double complex](/figures/rigorous-qft/ghosts-antifields-cohomology.svg)

<figcaption>

Ghosts move along gauge directions, antifields resolve equations of motion and Noether identities, and the BV differential combines these roles. In local BRST cohomology, counterterms and anomalies are computed using the total differential modulo spacetime exterior derivatives.

</figcaption>
</figure>

The core slogan is:

$$
\text{ghosts resolve gauge orbits},
\qquad
\text{antifields resolve equations of motion}.
$$

## Setup and conventions

Let $\phi^i$ denote the original classical fields and let

$$
\delta_\epsilon\phi^i=R^i_\alpha(\phi)\epsilon^\alpha
$$

be the infinitesimal gauge transformation. Replace each gauge parameter $\epsilon^\alpha$ by a ghost $c^\alpha$. The minimal BV variables are

$$
\Phi^A=(\phi^i,c^\alpha),
\qquad
\Phi_A^*=(\phi_i^*,c_\alpha^*).
$$

The ghost number convention is

$$
\operatorname{gh}(\Phi_A^*)
  =-1-\operatorname{gh}(\Phi^A).
$$

The antifield number is assigned by

$$
\operatorname{afn}(\phi^i)=0,
\qquad
\operatorname{afn}(c^\alpha)=0,
\qquad
\operatorname{afn}(\phi_i^*)=1,
\qquad
\operatorname{afn}(c_\alpha^*)=2.
$$

For irreducible Yang–Mills theory, the classical BV action begins as

$$
S_{\mathrm{BV}}
= S_{\mathrm{cl}}[A]
+\int_M \operatorname{tr}(A^{*\mu}D_\mu c)
-\frac12\int_M \operatorname{tr}(c^*[c,c]).
$$

The BV differential is

$$
sF=(S_{\mathrm{BV}},F),
\qquad
\operatorname{gh}(s)=1.
$$

If $S_{\mathrm{BV}}$ satisfies the classical master equation, then

$$
s^2=0.
$$

This one equation contains the Euler–Lagrange equations, the gauge transformations, the gauge algebra, and their compatibility.

## The three gradings

Three gradings are commonly used. Mixing them up is one of the fastest ways to get lost.

**Ghost number.** This is the total cohomological degree relevant for BRST/BV cohomology. Physical classical observables usually live in ghost number $0$. Anomaly candidates live in ghost number $1$.

**Pure ghost number.** This counts ghosts but not antifields. For ordinary irreducible gauge theory,

$$
\operatorname{pgh}(c^\alpha)=1,
\qquad
\operatorname{pgh}(\phi^i)=0.
$$

**Antifield number.** This counts how far one has moved into the homological resolution of the stationary surface. The usual relation is

$$
\operatorname{gh}
=\operatorname{pgh}-\operatorname{afn}.
$$

For the minimal Yang–Mills variables:

| Variable | Parity | Pure ghost number | Antifield number | Ghost number |
|---|---:|---:|---:|---:|
| $A_\mu$ | even | $0$ | $0$ | $0$ |
| $c$ | odd | $1$ | $0$ | $1$ |
| $A^{*\mu}$ | odd | $0$ | $1$ | $-1$ |
| $c^*$ | even | $0$ | $2$ | $-2$ |

The antibracket raises ghost number by one:

$$
\operatorname{gh}(F,G)
=\operatorname{gh}(F)+\operatorname{gh}(G)+1.
$$

Therefore a ghost-number-zero BV action generates a ghost-number-one differential.

## Koszul–Tate resolution

The Koszul–Tate differential $\delta$ is the part of the BV differential that implements the equations of motion. For an ordinary action $S_{\mathrm{cl}}[\phi]$, it acts schematically as

$$
\delta\phi^i=0,
\qquad
\delta\phi_i^*=\frac{\delta S_{\mathrm{cl}}}{\delta\phi^i}.
$$

Thus antifields are paired with Euler–Lagrange equations. The cohomology of $\delta$ at antifield number zero is the algebra of functions on the stationary surface:

$$
H_0(\delta)
\simeq
\frac{\text{functions on field space}}
     {\text{functions vanishing on shell}}.
$$

For a gauge theory, the equations of motion satisfy Noether identities. If

$$
R^i_\alpha(\phi)\frac{\delta S_{\mathrm{cl}}}{\delta\phi^i}=0,
$$

then the Koszul–Tate complex must include higher antifields. For irreducible gauge theory, the ghost antifield $c_\alpha^*$ resolves these identities:

$$
\delta c_\alpha^*
\sim
R^i_\alpha(\phi)\phi_i^*.
$$

The symbol $\sim$ hides signs, densities, and possible integration by parts. The meaning is precise: $c^*$ exists because the equations of motion obey a gauge identity.

## Longitudinal gauge differential

The second basic piece is the longitudinal gauge differential $\gamma$. It acts along gauge orbits. For Yang–Mills theory,

$$
\gamma A_\mu=D_\mu c,
\qquad
\gamma c=-\frac12[c,c].
$$

The equation $\gamma^2=0$ encodes closure of the gauge algebra. If the gauge algebra is open or closes only on shell, then $\gamma^2=0$ is no longer true by itself on the naive variables. BV fixes this by adding antifield-dependent terms to the full differential.

The relation between the pieces is often summarized as

$$
s=\delta+\gamma+s_1+s_2+\cdots,
$$

where $s_k$ changes antifield number in theory-dependent ways. The equation

$$
s^2=0
$$

then unfolds into a hierarchy of compatibility conditions.

For a closed irreducible algebra such as ordinary Yang–Mills theory, the hierarchy is simple. For gravity, supersymmetric systems, reducible gauge theories, or theories with boundary structure, the hierarchy can be much more informative.

## The full BV cohomology

The BV cohomology of $s$ is the invariant object. In the simplest classical language,

$$
H^0(s)
$$

is the algebra of gauge-invariant on-shell observables. The words “on-shell” and “gauge-invariant” both matter. The Koszul–Tate part implements the equations of motion; the longitudinal part implements the gauge quotient.

For local field theory one usually studies local forms. Let $a$ be a local $p$-form built from fields, ghosts, antifields, and finitely many derivatives. The relevant equivalence relation often identifies expressions differing by a total derivative. One writes

$$
s a+d b=0,
$$

and identifies

$$
a\sim a+s m+d n.
$$

The resulting local BRST cohomology is denoted

$$
H^{g,p}(s\mid d),
$$

where $g$ is ghost number and $p$ is form degree.

The most common cases are:

| Cohomology group | Physical meaning |
|---|---|
| $H^0(s)$ | Gauge-invariant observables, usually on shell. |
| $H^{0,d}(s\mid d)$ | Local action deformations and finite counterterms. |
| $H^{1,d}(s\mid d)$ | Candidate anomalies. |
| $H^{-1,d}(s\mid d)$ | Conserved currents and global symmetries in many standard settings. |

This table is not a theorem without hypotheses. It assumes the usual local field-theoretic setting and appropriate regularity, locality, and irreducibility conditions. The hypotheses matter in research applications.

## Nonminimal variables and doublets

Gauge fixing often introduces the antighost $\bar c$ and the Nakanishi–Lautrup field $b$. They form a BRST doublet:

$$
s\bar c=b,
\qquad
sb=0.
$$

A basic cohomological lemma says that doublets do not change the cohomology under suitable regularity assumptions. Intuitively, $\bar c$ and $b$ are gauge-fixing variables, not new physical observables.

In BV language, the nonminimal sector also has antifields $\bar c^*$ and $b^*$. Their role is to make gauge fixing canonical. A gauge-fixing fermion $\Psi$ sets antifields by

$$
\Phi_A^*=\frac{\delta\Psi}{\delta\Phi^A}.
$$

The nonminimal variables are therefore essential for practical covariant gauges but inessential for physical cohomology.

## Example: Yang–Mills local cohomology

For a semisimple Yang–Mills theory in four dimensions, the classical BRST differential includes

$$
sA= Dc,
\qquad
sc=-\frac12[c,c],
\qquad
sF=[F,c],
$$

where $A$ is the connection one-form and $F=dA+A\wedge A$ is the curvature.

Gauge-invariant local action terms at ghost number zero include expressions such as

$$
\int_M\operatorname{tr}(F\wedge *F)
$$

and, in four dimensions,

$$
\int_M\operatorname{tr}(F\wedge F).
$$

Anomaly candidates at ghost number one are constrained by

$$
s a^{1,4}+d a^{2,3}=0.
$$

In familiar chiral gauge theories, the consistent anomaly is represented by a descent sequence starting from an invariant polynomial such as

$$
\operatorname{tr}(F^3)
$$

in six dimensions. The details belong on the later anomaly page, but the cohomological pattern already appears here:

$$
\text{invariant polynomial}
\longrightarrow
\text{descent}
\longrightarrow
\text{ghost-number-one anomaly density}.
$$

This is why local BRST cohomology is more than formal algebra. It predicts which quantum breakings can occur and which cannot.

## Reducible gauge symmetries

Some gauge theories have gauge transformations that themselves have gauge redundancies. A standard example is a two-form gauge field $B$ with

$$
B\longmapsto B+d\Lambda.
$$

The one-form parameter $\Lambda$ has its own redundancy

$$
\Lambda\longmapsto \Lambda+d\alpha.
$$

The BRST-BV complex then needs ghosts-for-ghosts. Schematically,

$$
B
\quad\leadsto\quad
c_1
\quad\leadsto\quad
c_2,
$$

with increasing ghost number. The antifield tower also lengthens. This is one of the original motivations for the full BV formalism: it handles reducible and higher-stage gauge systems systematically.

The modern language of higher gauge theory and $L_\infty$ algebras makes this structure natural, but the BV bookkeeping already contains the essential data.

## Common pitfalls

**Ghost number is not particle number.** It is a cohomological grading. A field with ghost number $1$ is not “one ghost particle” in the physical spectrum.

**Antifield number is not anti-particle number.** Antifields are dual resolution variables. The antifield $A^*$ is not the antiparticle of $A$.

**Antighosts are not antifields.** The antighost $\bar c$ is a nonminimal gauge-fixing variable. The antifield $c^*$ is the BV partner of the ghost $c$. They have different jobs.

**Gauge-fixed BRST cohomology can hide the BV resolution.** Gauge fixing is useful for computations, but the invariant classification of counterterms and anomalies is often clearest before eliminating antifields.

**Local cohomology is not the same as global cohomology.** $H^{g,p}(s\mid d)$ classifies local expressions. It does not automatically classify line operators, boundary charges, global bundles, or nonperturbative sectors.

**Doublets should not create physics.** A BRST doublet such as $(\bar c,b)$ is normally cohomologically trivial. If a calculation produces physical dependence on a doublet variable, something is wrong or a hypothesis has changed.

## Relations to other pages

[BRST Complex](/rigorous-qft/bv-brst-gauge-theory/brst-complex/) introduced $s$ for simple closed gauge algebras. [BV Formalism](/rigorous-qft/bv-brst-gauge-theory/bv-formalism/) introduced antifields and the antibracket. [Classical Master Equation](/rigorous-qft/bv-brst-gauge-theory/classical-master-equation/) explained why $s^2=0$. [Quantum Master Equation](/rigorous-qft/bv-brst-gauge-theory/quantum-master-equation/) explained why anomaly candidates live in ghost number $1$.

The next natural pages are `observables-as-cohomology.md`, `gauge-fixing-as-lagrangian-submanifold.md`, and `anomalies-as-obstructions.md`. For perturbative renormalization, compare with [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/).

## Research status

**Established.** Local BRST/BV cohomology is a standard tool for classifying consistent deformations, counterterms, anomalies, and conservation laws in gauge theories under explicit locality and regularity assumptions.

**Subtle.** The relation between local cohomology and the full physical observable algebra can be delicate. Boundaries, defects, asymptotic symmetries, higher-form symmetries, and global topology can create observables not visible in the simplest local polynomial cohomology.

**Active.** Modern work connects BV cohomology to derived geometry, factorization algebras, shifted symplectic geometry, higher gauge theory, and perturbative quantization on curved spacetimes. These developments refine rather than replace the classical BRST-BV complex.

## Exercises

### Exercise 1: ghost numbers in Yang–Mills BV theory

Use

$$
\operatorname{gh}(\Phi_A^*)=-1-\operatorname{gh}(\Phi^A)
$$

for $A_\mu$ and $c$. Compute the ghost numbers of $A_\mu$, $c$, $A^{*\mu}$, and $c^*$.

<details><summary><strong>Solution</strong></summary>

The original gauge field has ghost number zero:

$$
\operatorname{gh}(A_\mu)=0.
$$

The ghost has ghost number one:

$$
\operatorname{gh}(c)=1.
$$

Therefore

$$
\operatorname{gh}(A^{*\mu})=-1-0=-1,
$$

and

$$
\operatorname{gh}(c^*)=-1-1=-2.
$$

</details>

### Exercise 2: the doublet lemma in one line

Suppose $su=v$ and $sv=0$. Let $N$ count the total number of $u$ and $v$ variables. Explain why a cohomology class with $N>0$ should be trivial under suitable regularity assumptions.

<details><summary><strong>Solution</strong></summary>

Define a homotopy operator $h$ by

$$
hv=u,
\qquad
hu=0.
$$

On polynomials in the doublet variables one has schematically

$$
sh+hs=N.
$$

If $a$ is $s$-closed and has $Na=na$ with $n>0$, then

$$
a=\frac1nNa=\frac1n(sh+hs)a
= s\left(\frac1nha\right).
$$

Thus $a$ is $s$-exact. This is why BRST doublets such as $(\bar c,b)$ normally do not contribute to physical cohomology.

</details>

### Exercise 3: anomaly consistency

Let $a^{1,d}$ be a local $d$-form of ghost number $1$. If it represents an anomaly density, why is the condition

$$
s a^{1,d}+d a^{2,d-1}=0
$$

natural?

<details><summary><strong>Solution</strong></summary>

An integrated anomaly is insensitive to total derivatives on a spacetime without boundary or with suitable boundary conditions. Therefore the local density need not be strictly $s$-closed; it only needs to be closed modulo $d$. The equation

$$
s a^{1,d}+d a^{2,d-1}=0
$$

says exactly that the integrated anomaly is $s$-closed. The extra term begins the descent sequence. Changing the anomaly by

$$
a^{1,d}\mapsto a^{1,d}+s m^{0,d}+d n^{1,d-1}
$$

corresponds to adding a local counterterm and a total derivative.

</details>

## References

### Standard references

- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*, Princeton University Press, 1992. [doi:10.1515/9780691213866](https://doi.org/10.1515/9780691213866).
- J. Gomis, J. París, and S. Samuel, “Antibracket, Antifields and Gauge-Theory Quantization,” *Physics Reports* **259** (1995), 1–145. [arXiv:hep-th/9412228](https://arxiv.org/abs/hep-th/9412228), [doi:10.1016/0370-1573(94)00112-G](https://doi.org/10.1016/0370-1573(94)00112-G).
- G. Barnich, F. Brandt, and M. Henneaux, “Local BRST Cohomology in Gauge Theories,” *Physics Reports* **338** (2000), 439–569. [arXiv:hep-th/0002245](https://arxiv.org/abs/hep-th/0002245), [doi:10.1016/S0370-1573(00)00049-1](https://doi.org/10.1016/S0370-1573(00)00049-1).
- G. Barnich, F. Brandt, and M. Henneaux, “Local BRST Cohomology in the Antifield Formalism: I. General Theorems,” *Communications in Mathematical Physics* **174** (1995), 57–91. [arXiv:hep-th/9405109](https://arxiv.org/abs/hep-th/9405109), [doi:10.1007/BF02099464](https://doi.org/10.1007/BF02099464).

### Algebraic renormalization and applications

- O. Piguet and S. P. Sorella, *Algebraic Renormalization: Perturbative Renormalization, Symmetries and Anomalies*, Springer, 1995. [doi:10.1007/978-3-540-49192-7](https://doi.org/10.1007/978-3-540-49192-7).
- J. A. Dixon, “Cohomology and Renormalization of Gauge Theories. I,” unpublished notes and related early BRST cohomology literature.
- M. Dubois-Violette, M. Henneaux, M. Talon, and C.-M. Viallet, “Some Results on Local Cohomologies in Field Theory,” *Physics Letters B* **267** (1991), 81–87. [doi:10.1016/0370-2693(91)90527-W](https://doi.org/10.1016/0370-2693(91)90527-W).
- K. Fredenhagen and K. Rejzner, “Batalin–Vilkovisky Formalism in Perturbative Algebraic Quantum Field Theory,” *Communications in Mathematical Physics* **317** (2013), 697–725. [arXiv:1110.5232](https://arxiv.org/abs/1110.5232), [doi:10.1007/s00220-012-1601-1](https://doi.org/10.1007/s00220-012-1601-1).

## Version history

- **2026-07-01:** Initial polished draft.
