---
title: "Beta Functions"
description: "Defines beta functions as vector fields on coupling space, explains their extraction from fixed bare parameters, and shows how they encode running couplings, fixed points, and scheme dependence."
sidebar:
  label: "Beta Functions"
  order: 2
level: Graduate
status: "Polished draft"
source: "Coleman, Dilatations and Asymptotic Freedom; Wilson and Kogut 1974; Srednicki §§27–29 and §§52, 66, 73; Schwartz ch. 23 and gauge-theory chapters; Weinberg Vol. II ch. 18; Zinn-Justin, RG chapters."
topics:
  - beta functions
  - running couplings
  - fixed points
  - scheme dependence
  - asymptotic freedom
  - theory space
canonicalTopics:
  - beta-function
  - running-coupling
  - rg-flow
  - fixed-point
  - scheme-dependence
researchStatus:
  established:
    - "Perturbative beta functions are standard renormalization group data extracted from how renormalized couplings must change with the subtraction scale at fixed bare theory."
  active:
    - "High-loop beta functions, scheme transformations, conformal windows, nonperturbative beta functions, functional RG approximations, and beta functions in theories without weakly coupled Lagrangians remain active research areas."
---

## Summary

A **beta function** tells how a renormalized coupling changes when the renormalization scale $\mu$ is varied while the bare theory is held fixed:

$$
\beta^i(g)
\equiv
\left.\mu\frac{d g^i}{d\mu}\right|_{\text{bare}}.
$$

For one coupling $g$, the RG equation is

$$
\frac{dg}{d\log\mu}=\beta(g).
$$

For several couplings, the beta functions form a vector field on theory space:

$$
\frac{dg^i}{d\log\mu}=\beta^i(g^1,g^2,\ldots).
$$

<figure class="doc-figure" style="--figure-width: 44rem; --caption-width: 52rem;">

![Beta functions drawn as a vector field on coupling space with fixed points, flow lines, relevant and irrelevant directions, and a scheme-coordinate grid](/figures/renormalization-rg-eft/beta-function-vector-field.svg)

<figcaption>

A beta function is a vector field on coupling space. Its zeros are fixed points. A change of renormalization scheme changes the coordinate grid, but physical scaling data at a fixed point are invariant when computed consistently.

</figcaption>
</figure>

The sign convention used throughout this volume is ultraviolet-oriented: increasing $\mu$ moves toward shorter distances. With this convention,

$$
\beta_e=\frac{e^3}{12\pi^2}+O(e^5)
$$

for QED with one Dirac fermion, while

$$
\beta_g=-\frac{g^3}{16\pi^2}
\left(\frac{11}{3}C_A-\frac{4}{3}T_R N_f\right)+O(g^5)
$$

for a non-Abelian gauge theory with $N_f$ Dirac fermions in a representation with trace normalization $T_R$. The first grows toward the ultraviolet in perturbation theory; the second is asymptotically free when the bracket is positive.

## Prerequisites

You should know [Conventions and Notation](/renormalization-rg-eft/conventions/), [Callan–Symanzik Equation](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/), [Mass and Coupling Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/mass-and-coupling-renormalization/), [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/), and [MSbar Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/msbar-scheme/).

The page assumes comfort with differentiating bare-renormalized coupling relations. Detailed loop integrals are not needed here; the point is how beta functions are defined, interpreted, and used.

## Core idea

A renormalized coupling is a coordinate, not a sacred number. Once a regulator and subtraction prescription are chosen, the same bare theory can be described by different values of $g(\mu)$ at different subtraction scales.

The beta function is the differential rule for this change:

$$
\mu\frac{d}{d\mu}
\begin{pmatrix}
 g^1 \\
 g^2 \\
 \vdots
\end{pmatrix}
=
\begin{pmatrix}
 \beta^1(g) \\
 \beta^2(g) \\
 \vdots
\end{pmatrix}.
$$

This viewpoint is more robust than saying "the coupling depends on energy." A physical process has energy scales such as $Q$, masses, thresholds, temperatures, or external momenta. The renormalization scale $\mu$ is a convention. We often choose $\mu\sim Q$ because this reduces large logarithms, but the beta function itself is defined by changing $\mu$ at fixed bare data.

Beta functions matter because they organize:

| RG object | What the beta function tells you |
|---|---|
| Running couplings | how parameters change between scales |
| Fixed points | where scale dependence can disappear |
| Relevant and irrelevant directions | how perturbations grow or shrink near a fixed point |
| Large logarithms | how to resum logarithms between separated scales |
| Dimensional transmutation | how a dimensionless coupling can be exchanged for a scale |
| UV behavior | whether a theory becomes weakly coupled, strongly coupled, or singular at high energies |

## Setup and conventions

Let $t=\log\mu$. The RG equation is

$$
\frac{dg^i}{dt}=\beta^i(g).
$$

For a single coupling,

$$
\int_{g(\mu_0)}^{g(\mu)}\frac{dg}{\beta(g)}
=\log\frac{\mu}{\mu_0}.
$$

This formula is often the simplest way to solve one-coupling running.

For a dimensionful coupling $c_i$ multiplying an operator $\mathcal O_i$ of engineering dimension $\Delta_i^{\text{eng}}$ in $d$ dimensions,

$$
S\supset c_i\int d^d x\,\mathcal O_i(x),
\qquad
[c_i]=d-\Delta_i^{\text{eng}}.
$$

Define the dimensionless coupling

$$
\tilde c_i(\mu)=\mu^{\Delta_i^{\text{eng}}-d}c_i(\mu).
$$

At tree level,

$$
\mu\frac{d\tilde c_i}{d\mu}
=(\Delta_i^{\text{eng}}-d)\tilde c_i.
$$

Quantum corrections add higher-order terms and operator mixing. Near an interacting fixed point, engineering dimensions are replaced by full scaling data.

## Extracting beta functions from bare couplings

The definition of a beta function follows from the fact that a bare coupling does not depend on $\mu$:

$$
0=\left.\mu\frac{d g_0}{d\mu}\right|_{\text{bare}}.
$$

In dimensional regularization, a marginal coupling in four dimensions is commonly written as

$$
g_0=\mu^{\kappa\epsilon}Z_g(g,\epsilon)g,
\qquad d=4-2\epsilon.
$$

Taking $\mu d/d\mu$ at fixed $g_0$ gives

$$
0=
\kappa\epsilon
+\frac{\beta(g)}{g}
+\beta(g)\frac{\partial}{\partial g}\log Z_g(g,\epsilon).
$$

Thus

$$
\beta(g)=
-\frac{\kappa\epsilon g}{1+g\partial_g\log Z_g(g,\epsilon)}.
$$

This formula looks as if it vanishes when $\epsilon\to0$, but $Z_g$ contains poles in $\epsilon$. The poles combine with the explicit $\epsilon$ to leave a finite beta function in the physical dimension.

In minimal subtraction schemes, this is why the pole part of a counterterm determines the beta function. The finite parts define the scheme, while the pole structure records how renormalized parameters must run to keep bare quantities fixed.

:::caution[Do not memorize a pole formula without its convention]
The exact sign and normalization of a beta function extracted from a counterterm depend on how the interaction is written, whether the coupling is $g$, $g^2$, $\lambda$, or $\alpha=g^2/(4\pi)$, and whether one uses MS or $\overline{\mathrm{MS}}$. The invariant definition is always $\beta^i=\mu dg^i/d\mu$ at fixed bare quantities.
:::

## One-loop examples

For scalar $\phi^4$ theory in four dimensions with

$$
\mathcal L\supset -\frac{\lambda}{4!}\phi^4,
$$

the one-loop beta function is

$$
\beta_\lambda=\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

In four-dimensional QED with one Dirac fermion,

$$
\beta_e=\frac{e^3}{12\pi^2}+O(e^5).
$$

Equivalently, for

$$
\alpha=\frac{e^2}{4\pi},
$$

one finds

$$
\beta_\alpha
\equiv \mu\frac{d\alpha}{d\mu}
=\frac{2}{3\pi}\alpha^2+O(\alpha^3).
$$

For a non-Abelian gauge theory with gauge group generators normalized by

$$
\operatorname{tr}(T^a_R T^b_R)=T_R\delta^{ab},
\qquad
f^{acd}f^{bcd}=C_A\delta^{ab},
$$

the one-loop gauge beta function is

$$
\beta_g=-\frac{g^3}{16\pi^2}
\left(\frac{11}{3}C_A-\frac{4}{3}T_RN_f\right)+O(g^5).
$$

For $SU(N)$ with $N_f$ Dirac fermions in the fundamental representation,

$$
C_A=N,
\qquad
T_R=\frac12,
$$

so

$$
\beta_g=-\frac{g^3}{16\pi^2}
\left(\frac{11}{3}N-\frac{2}{3}N_f\right)+O(g^5).
$$

These examples already show the main possibilities: positive beta function, negative beta function, and zeros that can appear when competing terms balance.

## Solving the simplest beta functions

Consider

$$
\beta(g)=b g^3+O(g^5).
$$

Keeping only the leading term,

$$
\frac{dg}{d\log\mu}=bg^3.
$$

Integrating gives

$$
\frac{1}{g^2(\mu)}
=\frac{1}{g^2(\mu_0)}-2b\log\frac{\mu}{\mu_0}.
$$

If $b>0$, then $g(\mu)$ grows toward the ultraviolet and formally diverges at a finite scale in this one-loop approximation. This is the perturbative Landau-pole behavior.

If $b<0$, then $g(\mu)$ decreases toward the ultraviolet:

$$
g^2(\mu)
\simeq
\frac{1}{2|b|\log(\mu/\Lambda)}.
$$

This is asymptotic freedom. The integration constant has been rewritten as a scale $\Lambda$; this is the beginning of dimensional transmutation.

## Fixed points

A fixed point is a zero of all beta functions:

$$
\beta^i(g_*)=0.
$$

At a fixed point, dimensionless couplings stop running. This does not mean every correlation function becomes trivial. Fields and operators may still have anomalous dimensions, and the theory may be an interacting CFT.

Linearize near the fixed point:

$$
g^i=g_*^i+\delta g^i,
$$

so

$$
\frac{d\delta g^i}{dt}
=B^i{}_j\delta g^j+O(\delta g^2),
\qquad
B^i{}_j=\left.\frac{\partial\beta^i}{\partial g^j}\right|_{g_*}.
$$

The eigenvalues of $B$ determine whether perturbations grow or shrink as $\mu$ is increased toward the ultraviolet. If one instead uses an infrared Wilsonian time $\ell=\log(\Lambda_0/\Lambda)$, the signs are reversed. This is why every fixed-point discussion must specify the flow parameter.

For one coupling,

$$
\frac{d\delta g}{dt}=\beta'(g_*)\delta g.
$$

If $\beta'(g_*)<0$, then the fixed point is ultraviolet-attractive along that direction. If $\beta'(g_*)>0$, it is infrared-attractive along that direction.

## Scheme dependence

A change of renormalization scheme is a change of coordinates on coupling space:

$$
g^i\longrightarrow g^{\prime i}(g).
$$

The beta function transforms as a vector field:

$$
\beta^{\prime i}(g')
=\frac{\partial g^{\prime i}}{\partial g^j}\beta^j(g).
$$

This is why it is both true that beta functions are scheme-dependent and false that they are meaningless. The components of a vector field depend on coordinates; the existence of a fixed point, the dimension of stable and unstable manifolds, and the eigenvalues of the linearized flow at a fixed point are invariant under ordinary nonsingular reparametrizations.

For a single coupling with perturbative expansion

$$
\beta(g)=b_1g^3+b_2g^5+b_3g^7+\cdots,
$$

the first coefficient $b_1$ is invariant under analytic redefinitions of the form

$$
g'=g+a g^3+O(g^5).
$$

In many mass-independent gauge-theory schemes, the first two coefficients are universal. Higher coefficients generally depend on scheme.

## Beta functions and anomalous dimensions

Beta functions describe the flow of couplings. Anomalous dimensions describe the flow of fields and operators. They meet in the Callan–Symanzik equation:

$$
\left[
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+n\gamma_\phi
\right]G_R^{(n)}=0.
$$

At a fixed point, $\beta^i=0$, but anomalous dimensions can remain nonzero. That is why an interacting fixed point can have scaling dimensions different from engineering dimensions.

For composite operators, the anomalous dimensions often form a matrix:

$$
\mu\frac{d}{d\mu}\mathcal O_{a,R}
=-\gamma_a{}^b\mathcal O_{b,R}.
$$

In EFT, the same matrix controls Wilson-coefficient running, with a transpose and sign determined by the convention used for the operator basis and coefficient vector.

## Physical interpretation

The beta function is not directly an observable, but it controls observable scale dependence after a measurement convention is chosen.

In QED, the positive beta function can be interpreted physically through vacuum polarization: the effective electromagnetic charge measured at shorter distances is larger in perturbation theory.

In non-Abelian gauge theory, gauge-boson self-interactions dominate over matter screening when $N_f$ is small enough. The negative beta function means the coupling gets weaker at shorter distances. This is asymptotic freedom, and it explains why high-energy quark and gluon processes can be treated perturbatively even though the long-distance theory is strongly coupled.

In EFT, beta functions evolve Wilson coefficients between a matching scale and a lower measurement scale. The running can resum large logarithms such as

$$
\log\frac{M}{Q},
$$

where $M$ is a heavy threshold and $Q$ is a low-energy process scale.

In statistical field theory, beta functions classify universality classes. Fixed points describe scale-invariant critical behavior, and the linearized flow gives critical exponents.

## A small dictionary of beta-function uses

| Phrase | Beta-function meaning |
|---|---|
| Running coupling | Solution of $dg/d\log\mu=\beta(g)$. |
| Fixed point | Zero of $\beta^i$. |
| Relevant direction | Perturbation that grows toward the infrared near a fixed point. |
| Marginally relevant | Coupling whose tree-level beta function vanishes but loop terms make it grow toward the infrared. |
| Marginally irrelevant | Coupling whose tree-level beta function vanishes but loop terms make it shrink toward the infrared. |
| Asymptotic freedom | Coupling approaches zero toward the ultraviolet. |
| Landau pole | Perturbative running becomes singular at finite scale. |
| Conformal window | Range of parameters where an interacting fixed point may exist. |
| Dimensional transmutation | Running trades a dimensionless coupling for an RG-invariant scale. |

## Common pitfalls

**Calling $\beta$ an observable.** A beta function depends on coupling definitions and scheme. Physical scaling laws and measured predictions are scheme-independent when computed consistently.

**Forgetting the direction of RG time.** This volume uses $t=\log\mu$, which increases toward the ultraviolet. Wilsonian discussions often use an infrared time $\ell=\log(\Lambda_0/\Lambda)$, which increases toward the infrared.

**Comparing beta functions for different variables.** The beta function for $e$, $e^2$, $\alpha=e^2/(4\pi)$, and $a=e^2/(16\pi^2)$ have different coefficients. Translate variables before comparing.

**Thinking a zero in a truncated beta function is automatically a real fixed point.** A perturbative zero is trustworthy only if it occurs at small coupling or is supported by other evidence. Strong-coupling zeros can be artifacts of scheme or truncation.

**Treating Landau poles as always literal.** A perturbative Landau pole can mean inconsistency, a finite cutoff, a missing threshold, or simply that the chosen weak-coupling description has failed.

**Ignoring thresholds.** A beta function changes when degrees of freedom are integrated out. Running across a mass threshold requires matching, not just blindly continuing the same differential equation.

**Confusing beta functions with Wilsonian coarse graining.** Renormalized beta functions track coordinates at fixed bare theory. Wilsonian beta functions track the changing effective action as modes are removed. They overlap, but their operational definitions differ.

## Relations to other pages

[Callan–Symanzik Equation](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/) shows where beta functions enter correlation-function RG equations. [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/) explains the companion quantities for fields and operators. [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/) solves beta-function equations in common examples.

[Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/) develops finite redefinitions of couplings more systematically. [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/) explains how the integration constant of a beta-function equation becomes a physical scale. [Landau Poles](/renormalization-rg-eft/renormalization-group-equations/landau-poles/) and [Asymptotic Freedom](/renormalization-rg-eft/renormalization-group-equations/asymptotic-freedom/) study the two most famous ultraviolet behaviors.

[Wilsonian Renormalization](/renormalization-rg-eft/wilsonian-renormalization/) gives the coarse-graining interpretation of RG flow. [Fixed Points and Critical Phenomena](/renormalization-rg-eft/fixed-points-critical-phenomena/) develops the physical consequences of fixed points, linearized flow, scaling laws, and universality classes.

## Research status

Perturbative beta functions are a mature subject. One-loop and multi-loop beta functions are standard tools across scalar theories, gauge theories, supersymmetric theories, EFTs, and statistical field theory.

Active research includes high-loop calculations, conformal windows, strong-coupling fixed points, scheme-invariant ways to characterize flows, nonperturbative functional RG, lattice determinations of running couplings, RG flows in theories without weakly coupled Lagrangians, and the relation between RG monotonicity theorems and quantum information.

## Exercises

### Exercise 1: Solve a cubic beta function

Let

$$
\beta(g)=bg^3.
$$

Solve for $g(\mu)$ in terms of $g(\mu_0)$.

<details><summary><strong>Solution</strong></summary>

The equation is

$$
\frac{dg}{d\log\mu}=bg^3.
$$

Separate variables:

$$
\int_{g(\mu_0)}^{g(\mu)}\frac{dg}{g^3}
=b\int_{\mu_0}^{\mu}d\log\mu.
$$

This gives

$$
-\frac{1}{2g^2(\mu)}+\frac{1}{2g^2(\mu_0)}
=b\log\frac{\mu}{\mu_0}.
$$

Therefore

$$
\frac{1}{g^2(\mu)}
=\frac{1}{g^2(\mu_0)}-2b\log\frac{\mu}{\mu_0}.
$$

</details>

### Exercise 2: Transform a beta function under a coupling redefinition

Suppose

$$
g'=g+a g^3+O(g^5),
\qquad
\beta(g)=b_1g^3+b_2g^5+O(g^7).
$$

Show that the coefficient $b_1$ is unchanged in the beta function for $g'$.

<details><summary><strong>Solution</strong></summary>

The transformed beta function is

$$
\beta'(g')=\frac{dg'}{dg}\beta(g).
$$

Since

$$
\frac{dg'}{dg}=1+3a g^2+O(g^4),
$$

we get

$$
\beta'(g')=(1+3a g^2)(b_1g^3+b_2g^5+O(g^7)).
$$

The leading term is

$$
\beta'(g')=b_1g^3+O(g^5).
$$

Since $g'=g+O(g^3)$, we also have $g^3=g'^3+O(g'^5)$. Therefore

$$
\beta'(g')=b_1g'^3+O(g'^5),
$$

so $b_1$ is invariant.

</details>

### Exercise 3: Tree-level flow of an irrelevant coupling

Let $c$ multiply an operator of engineering dimension $\Delta>d$. Define

$$
\tilde c(\mu)=\mu^{\Delta-d}c.
$$

Assuming no loop corrections, determine whether $\tilde c$ grows or shrinks as $\mu$ is lowered toward the infrared.

<details><summary><strong>Solution</strong></summary>

At tree level,

$$
\mu\frac{d\tilde c}{d\mu}=(\Delta-d)\tilde c.
$$

Solving gives

$$
\tilde c(\mu)=\tilde c(\mu_0)
\left(\frac{\mu}{\mu_0}\right)^{\Delta-d}.
$$

Because $\Delta>d$, the exponent is positive. If $\mu<\mu_0$, then

$$
\left(\frac{\mu}{\mu_0}\right)^{\Delta-d}<1.
$$

Thus the dimensionless coupling shrinks toward the infrared. This is why the operator is called irrelevant near the fixed point.

</details>

### Exercise 4: Linearized flow near a fixed point

For one coupling, suppose $\beta(g_*)=0$ and $\beta'(g_*)=y$. Solve the linearized flow for $\delta g=g-g_*$. Which sign of $y$ makes the fixed point attractive as $\mu$ increases?

<details><summary><strong>Solution</strong></summary>

The linearized equation is

$$
\frac{d\delta g}{d\log\mu}=y\delta g.
$$

Therefore

$$
\delta g(\mu)=\delta g(\mu_0)
\left(\frac{\mu}{\mu_0}\right)^y.
$$

As $\mu$ increases, $\delta g$ shrinks if $y<0$. Thus $y<0$ is ultraviolet-attractive in the convention $t=\log\mu$.

</details>

## References

- Sidney Coleman, "Dilatations" and "Asymptotic Freedom" in *Aspects of Symmetry*, for a classic explanation of anomalous scaling and beta functions.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200, for the modern view of RG flow and fixed points.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on renormalization schemes, the renormalization group, Yukawa beta functions, QED beta functions, and non-Abelian gauge beta functions.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on renormalization, running couplings, renormalizability, QED, and Yang–Mills theory.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for sliding scales, asymptotic behavior, multiple couplings, mass effects, critical phenomena, and minimal subtraction.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for beta functions, fixed points, RG functions, and applications to critical phenomena.

## Version history

- 2026-06-17: First polished draft. Defined beta functions with the volume sign convention, derived them from fixed bare quantities, added standard one-loop examples, explained fixed points and scheme dependence, and included exercises on running and coordinate changes.
