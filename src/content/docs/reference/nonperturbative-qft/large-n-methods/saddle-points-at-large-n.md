---
title: "Saddle Points at Large N"
description: "Explains large N as a steepest-descent method, including collective variables, effective actions, Hessians, multiple saddles, and beyond-all-orders effects."
sidebar:
  label: "Saddle Points at Large N"
  order: 9
level: Advanced
status: "Polished draft"
source: "Zinn-Justin; Coleman; Polyakov; Mariño; large-N saddle-point literature."
topics:
  - large-N saddle points
  - steepest descent
  - collective fields
  - gap equations
  - Hessians
  - 1/N expansion
  - multiple saddles
  - nonperturbative in N
canonicalTopics:
  - nonperturbative-qft
  - large-n-methods
  - saddle-points
  - steepest-descent
  - collective-field-methods
researchStatus:
  established:
    - "Many large-N limits reduce leading observables to saddle-point equations for collective fields, eigenvalue densities, or normalized gauge-invariant variables."
  active:
    - "Global saddle structure, complex saddles, finite-N corrections, double-scaling limits, and the relation to resurgence and holography remain model-dependent research topics."
---

## Summary

**Large $N$ turns some quantum field theories into saddle-point problems.** The mechanism is simple in form but varied in practice. If a theory can be rewritten as

$$
Z_N=\int \mathcal D\Phi\,\exp\left[-N s_{\rm eff}[\Phi]\right],
$$

then the leading large-$N$ approximation is obtained from

$$
\frac{\delta s_{\rm eff}}{\delta\Phi}=0.
$$

The field $\Phi$ may be a Hubbard–Stratonovich field, a Lagrange multiplier, an induced gauge field, an eigenvalue density, a bilocal field, or an abstract gauge-invariant master variable. The microscopic theory may be strongly coupled. The large parameter is not necessarily $1/g^2$ or $1/\hbar$; it is $N$.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Anatomy of large-N saddle-point methods: choose a scaling, introduce collective variables, integrate many fields or count topology, obtain an effective exponent, solve saddle equations, compute Hessian fluctuations, handle global saddle issues, and track e to minus N effects.](/figures/nonperturbative-qft/large-n-saddle-point-anatomy.svg)

<figcaption>

A large-$N$ saddle starts by choosing a family of theories and a scaling limit. Vector and sigma models expose collective variables and determinants; matrix and gauge theories often expose topology and factorization. The leading saddle is only the local beginning: global saddles, phases, contours, zero modes, and $e^{-N}$ effects matter for the full nonperturbative story.

</figcaption>
</figure>

This page is the repair manual for large-$N$ calculations. It explains what must be shown before one is allowed to say “the large-$N$ answer is the saddle,” what the first $1/N$ correction means, and why large-$N$ perturbation theory can still miss exponentially small effects of order $e^{-N}$.

## Prerequisites

Read [Large-N Vector Models](/nonperturbative-qft/large-n-methods/large-n-vector-models/), [Large-N Sigma Models](/nonperturbative-qft/large-n-methods/large-n-sigma-models/), [Matrix Large-N Limits](/nonperturbative-qft/large-n-methods/matrix-large-n-limits/), and [Large-N Factorization](/nonperturbative-qft/large-n-methods/large-n-factorization/) first.

You should also know [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/) and [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/). This page uses the same mathematics, but the large parameter is $N$ rather than a small coupling in the classical action.

For examples, keep [CP N-Minus-One Model](/nonperturbative-qft/large-n-methods/cp-n-minus-one-model/), [Large-N Yang–Mills](/nonperturbative-qft/large-n-methods/large-n-yang-mills/), and [Planar Diagrams](/nonperturbative-qft/large-n-methods/planar-diagrams/) nearby.

## Core idea

A saddle-point approximation requires an exponent with a large coefficient. In semiclassical instanton physics one often has

$$
Z\sim \int D\phi\,e^{-S_E[\phi]/g^2},
$$

so $1/g^2$ is large. In large-$N$ physics, the exponent often has the form

$$
Z_N\sim \int D\Phi\,e^{-N s_{\rm eff}[\Phi]}.
$$

The variable $\Phi$ is usually not the original microscopic field. It is a collective variable whose fluctuations are small because it averages over many components or many color indices.

There are two common routes.

| Route | Typical theories | Saddle variable |
|---|---|---|
| Integrate many components | Vector models, sigma models, Gross–Neveu-type models | Auxiliary fields, gap variables, bilocals, induced gauge fields |
| Count topology or eigenvalues | Matrix models, gauge theories | Eigenvalue density, loop variables, normalized traces, planar master data |

The shared structure is

$$
\text{many microscopic degrees of freedom}
\quad\Longrightarrow\quad
\text{collective observable with small relative fluctuations}
\quad\Longrightarrow\quad
\text{classical saddle at }N=\infty.
$$

This is why large $N$ often feels like a classical limit. It is not classical because $\hbar\to0$; it is classical because invariant collective observables factorize.

## Warm-up: finite-dimensional steepest descent

Let

$$
I_N=\int_C dx\,a(x)e^{-N s(x)}.
$$

Suppose $x_*$ is a nondegenerate saddle on the relevant contour:

$$
s'(x_*)=0,
\qquad
s''(x_*)\neq0.
$$

Expanding

$$
s(x)=s(x_*)+\frac12s''(x_*)(x-x_*)^2+\frac16s'''(x_*)(x-x_*)^3+\cdots,
$$

and setting

$$
x=x_*+\frac{\eta}{\sqrt N},
$$

gives

$$
I_N
\sim
e^{-Ns(x_*)}a(x_*)
\left(\frac{2\pi}{N s''(x_*)}\right)^{1/2}
\left[1+O\left(\frac1N\right)\right],
$$

with the usual contour and phase qualifications.

The field-theory version replaces $x$ by a field or density, $s''$ by a Hessian operator, and the square root determinant by a functional determinant.

## Functional saddle expansion

For a large-$N$ functional integral

$$
Z_N=\int\mathcal D\Phi\,e^{-N s[\Phi]},
$$

the saddle is

$$
\left.\frac{\delta s}{\delta\Phi(x)}\right|_{\Phi=\Phi_*}=0.
$$

Write fluctuations as

$$
\Phi(x)=\Phi_*(x)+\frac{1}{\sqrt N}\eta(x).
$$

Then

$$
N s[\Phi]
=
N s[\Phi_*]
+
\frac12\int dx\,dy\,\eta(x)H(x,y)\eta(y)
+
\frac{1}{\sqrt N}V_3[\eta]
+
\frac{1}{N}V_4[\eta]
+\cdots,
$$

where

$$
H(x,y)=
\left.\frac{\delta^2s}{\delta\Phi(x)\delta\Phi(y)}\right|_{\Phi_*}.
$$

The leading connected fluctuation is

$$
\langle \eta(x)\eta(y)\rangle=H^{-1}(x,y),
$$

so the original collective-field fluctuation obeys

$$
\langle \delta\Phi(x)\delta\Phi(y)\rangle
=\frac1N H^{-1}(x,y)+\cdots.
$$

That equation is the beating heart of many large-$N$ calculations. It explains why collective variables are classical at leading order and why their connected fluctuations are suppressed.

## What counts as the saddle variable?

The saddle variable depends on the theory.

### Vector models

For an $O(N)$ model, one introduces

$$
\rho(x)=\frac1N\phi_i(x)\phi_i(x)
$$

and a multiplier or Hubbard–Stratonovich field $\sigma(x)$. After integrating out the $N$ vector components,

$$
S_{\rm eff}[\rho,\sigma]
=N s_{\rm eff}[\rho,\sigma].
$$

The saddle equation is a gap equation. In a translation-invariant phase it often determines a mass parameter.

### Nonlinear sigma models

For constrained fields, the saddle variable is frequently a Lagrange multiplier enforcing the target-space constraint. In the two-dimensional $O(N)$ model and the $CP^{N-1}$ model, the saddle value of this multiplier generates a mass scale.

### Matrix models

For Hermitian matrix integrals, one diagonalizes the matrix and obtains an eigenvalue density

$$
\rho(\lambda)=\frac1N\sum_i\delta(\lambda-\lambda_i).
$$

The saddle is not a single eigenvalue; it is a continuum density. The saddle equation balances the external potential against eigenvalue repulsion.

### Gauge theories

For large-$N$ Yang–Mills, a fully explicit local saddle variable is not known in ordinary four-dimensional flat-space theory. What is known robustly is the topological organization of diagrams and factorization of normalized gauge-invariant observables. The hoped-for object encoding all planar observables is often called a master field.

This is a major distinction: **large-$N$ counting can be established even when the explicit saddle variable is not known.**

## Gap equations as saddle equations

A gap equation is a saddle equation that determines a mass, condensate, density, or Lagrange multiplier self-consistently.

For example, in a two-dimensional large-$N$ sigma model one finds

$$
\frac1{g_0}
=
\int^\Lambda\frac{d^2p}{(2\pi)^2}\frac1{p^2+M^2}.
$$

The right-hand side depends on $M$, and the equation determines $M$ in terms of $g_0$ and the cutoff. Solving gives

$$
M\sim \Lambda e^{-\text{const}/g_0}.
$$

This illustrates two important facts.

First, large $N$ can produce a nonperturbative scale even when the original coupling is weak.

Second, the saddle equation is not just a variational approximation if it was derived from an exact rewriting of the path integral followed by a controlled large-$N$ limit.

## Hessians, propagators, and 1/N corrections

Once the leading saddle is found, the next step is the Hessian. The Gaussian integral over $\eta$ gives

$$
Z_N
\sim
e^{-Ns[\Phi_*]}
\left(\det H\right)^{-1/2}
\left[1+O\left(\frac1N\right)\right],
$$

again with field-space and gauge-fixing caveats.

The inverse Hessian is the propagator for the collective fluctuation. In vector models, this is the propagator of the Hubbard–Stratonovich field. In sigma models, it is the propagator of the Lagrange multiplier or induced gauge field. In matrix models, it controls density fluctuations. In gauge theories, related large-$N$ fluctuations are encoded by connected correlators of normalized traces.

The vertices in the fluctuation theory are suppressed by powers of $1/\sqrt N$. A cubic collective vertex usually scales as

$$
N^{-1/2},
$$

and a quartic one as

$$
N^{-1}.
$$

Thus the $1/N$ expansion becomes ordinary perturbation theory around the collective saddle.

This is often the safest way to compute corrections: do not draw diagrams with the original microscopic fields and then guess the scaling. Derive the collective effective action, expand around the saddle, and read off the powers of $N$.

## Multiple saddles and phases

The local expansion around one saddle is not the whole theory. If there are several saddles $\Phi_a$, the large-$N$ asymptotics has the form

$$
Z_N\sim \sum_a C_a(N)e^{-Ns[\Phi_a]}.
$$

At $N=\infty$, the dominant saddle is the one with smallest real part of $s$. If two saddles exchange dominance as a parameter is varied, the large-$N$ free energy can become nonanalytic. This is a phase transition in the strict large-$N$ limit.

At finite $N$, the partition function may be smooth even when the $N=\infty$ limit is not. The nonanalyticity emerges because the ratio of two saddle contributions behaves as

$$
\frac{e^{-Ns[\Phi_2]}}{e^{-Ns[\Phi_1]}}
=e^{-N(s[\Phi_2]-s[\Phi_1])}.
$$

A small difference in action becomes decisive as $N\to\infty$.

This is the large-$N$ version of a familiar thermodynamic idea. Large $N$ is often a thermodynamic limit in the space of internal degrees of freedom.

## Beyond all orders in 1/N

The ordinary $1/N$ expansion around one saddle is blind to effects of the form

$$
e^{-N\Delta s}.
$$

These are nonperturbative in $1/N$. Examples include eigenvalue tunneling in matrix models, large-$N$ instanton effects, tunneling between metastable large-$N$ saddles, and exponentially small corrections to factorized observables.

This is not a defect of the method. It is a feature of asymptotic expansions. A local expansion around a saddle cannot know everything about other saddles unless supplemented by global information: contours, thimbles, boundary conditions, analytic continuation, or resurgence data.

The slogan is:

$$
\text{large }N\text{ gives a perturbation theory in }1/N,
\quad
\text{not automatically the full nonperturbative answer in }N.
$$

## Contours, constraints, and gauge redundancies

Large-$N$ saddles are often introduced by auxiliary fields. Those fields may have integration contours that are not simply real lines. For example, a Lagrange multiplier imposing a constraint may naturally begin on an imaginary contour but have a real saddle after deformation.

This matters because saddle-point equations alone do not tell you whether a saddle contributes. A saddle must lie on, or be reachable by deformation from, the correct integration cycle. In complexified field space, this is the language of steepest-descent contours and Lefschetz thimbles.

Gauge redundancies add another layer. If the saddle has gauge zero modes, one must gauge-fix or divide by the gauge volume. If the saddle has collective coordinates from a genuine symmetry, those modes are not included in the determinant in the naive way; they become integrals over moduli.

The practical checklist is:

$$
\text{saddle equation}
\quad+
\quad
\text{correct contour}
\quad+
\quad
\text{zero-mode treatment}
\quad+
\quad
\text{renormalization}
\quad=
\quad
\text{a calculation, not just a stationary point}.
$$

## Large-N scaling of observables

The power of $N$ in a connected correlator depends on the large-$N limit.

In vector models, normalized singlet operators often have connected correlators suppressed as powers of $1/N$. A typical singlet is

$$
\rho(x)=\frac1N\phi_i(x)\phi_i(x),
$$

and

$$
\langle \rho(x)\rho(y)\rangle_c=O\left(\frac1N\right).
$$

In matrix and gauge theories, normalized single-trace operators such as

$$
\mathcal O(x)=\frac1N\operatorname{tr}M^k(x)
$$

or

$$
\mathcal O(x)=\frac1N\operatorname{tr}F^2(x)
$$

usually obey

$$
\langle \mathcal O_1\mathcal O_2\rangle_c=O\left(\frac1{N^2}\right)
$$

in the pure adjoint planar limit.

Both statements are called factorization, but the power of $N$ differs because the number of degrees of freedom differs:

$$
\text{vector degrees of freedom}\sim N,
\qquad
\text{matrix adjoint degrees of freedom}\sim N^2.
$$

This is one of the easiest places to lose a factor of $N$ and accidentally compare different large-$N$ limits.

## Checks and diagnostics

| Check | What to ask |
|---|---|
| Family specified | What theory depends on $N$, and what is held fixed as $N\to\infty$? |
| Scaling correct | Does the action, free energy, or diagram weight have a stable large-$N$ limit? |
| Collective variables identified | What variables have small fluctuations at large $N$? |
| Exact rewriting or controlled approximation | Was the collective action derived, or guessed? |
| Saddle equation solved | Is the saddle translation invariant, inhomogeneous, multi-cut, or otherwise structured? |
| Hessian checked | Are there negative modes, zero modes, gauge modes, or IR divergences? |
| Renormalization done | Are cutoff-dependent terms absorbed into couplings or physical scales? |
| Competing saddles considered | Could another saddle dominate in part of parameter space? |
| Observable normalization fixed | Are correlators normalized so the stated $N$ scaling is meaningful? |
| Beyond-all-orders effects labeled | Are $e^{-N}$ effects being ignored, estimated, or included? |

## Common pitfalls

**Saying “large $N$” before saying which large $N$.** Vector, matrix, adjoint gauge, Veneziano, and tensor large-$N$ limits are different limits.

**Assuming the microscopic field has a classical expectation value.** The large-$N$ saddle is often a collective field, not the original field.

**Forgetting the measure.** Matrix models acquire a Vandermonde determinant. Gauge theories require gauge fixing. Constraints can add Jacobians. Measures can change saddle equations.

**Dropping subleading saddles without saying so.** A $1/N$ expansion around one saddle is local. It misses $e^{-N}$ effects and can fail near phase transitions.

**Confusing factorization powers.** Vector-model singlets often factorize with $1/N$ corrections; adjoint single-trace observables often factorize with $1/N^2$ corrections.

**Calling the leading saddle “mean field” as a dismissal.** Some large-$N$ saddles are mean-field-like, but many are exact leading terms in a controlled expansion.

**Ignoring zero modes.** If the saddle has a continuous degeneracy, the Hessian determinant has zero eigenvalues. Those must be converted into collective-coordinate integrals or divided by redundancies.

## Relations to other pages

[Large-N Vector Models](/nonperturbative-qft/large-n-methods/large-n-vector-models/) gives the simplest collective-field saddle. [Large-N Sigma Models](/nonperturbative-qft/large-n-methods/large-n-sigma-models/) and [CP N-Minus-One Model](/nonperturbative-qft/large-n-methods/cp-n-minus-one-model/) show how constraints, mass generation, and induced fields enter.

[Matrix Large-N Limits](/nonperturbative-qft/large-n-methods/matrix-large-n-limits/) is the matrix-integral version of this page, while [Eigenvalue-Density Methods](/nonperturbative-qft/large-n-methods/eigenvalue-density-methods/) develops the continuum-density saddle in detail. [Planar Diagrams](/nonperturbative-qft/large-n-methods/planar-diagrams/) is the topological-counting version. [Large-N Factorization](/nonperturbative-qft/large-n-methods/large-n-factorization/) explains the classical-limit interpretation of suppressed connected correlators.

[Master Field Preview](/nonperturbative-qft/large-n-methods/master-field-preview/) asks what object, if any, encodes all leading large-$N$ invariant observables. [Large-N Yang–Mills](/nonperturbative-qft/large-n-methods/large-n-yang-mills/) explains what is known when the explicit saddle of four-dimensional planar gauge theory is not available.

This page also connects backward to [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/) and forward to [Double-Scaling Limits Preview](/nonperturbative-qft/large-n-methods/double-scaling-limits-preview/), where the large-$N$ saddle is combined with critical tuning.

## Research status

**Established.** Large-$N$ saddle methods are standard and controlled in vector models, sigma models, many matrix models, Gross–Neveu-type models, and related theories where an effective action proportional to $N$ can be derived.

**Established with caveats.** The saddle equations often give exact leading large-$N$ results, but the interpretation of the saddle variable is model-dependent. In gauge theories, factorization and planar counting are robust even when an explicit master saddle is unknown.

**Active.** Complex saddles, resurgence in $1/N$, eigenvalue instantons, double-scaling limits, tensor-model large-$N$ limits, holographic interpretations, finite-density saddles, and real-time contours are active research areas.

## Exercises

### Exercise 1: Finite-dimensional saddle expansion

Let

$$
I_N=\int_{-\infty}^{\infty}dx\,e^{-N s(x)},
$$

where $s'(x_*)=0$ and $s''(x_*)>0$. Derive the leading large-$N$ approximation.

<details>
<summary><strong>Solution</strong></summary>

Expand near the saddle:

$$
s(x)=s(x_*)+\frac12s''(x_*)(x-x_*)^2+\cdots.
$$

Then

$$
I_N\simeq e^{-Ns(x_*)}
\int dx\,\exp\left[-\frac{N}{2}s''(x_*)(x-x_*)^2\right].
$$

The Gaussian integral gives

$$
I_N\simeq e^{-Ns(x_*)}\left(\frac{2\pi}{Ns''(x_*)}\right)^{1/2}.
$$

Corrections come from cubic and higher terms in the expansion of $s(x)$.

</details>

### Exercise 2: Why fluctuations scale as one over square root of N

For

$$
Z_N=\int D\Phi\,e^{-Ns[\Phi]},
$$

show why the natural fluctuation variable is

$$
\Phi=\Phi_*+\frac{\eta}{\sqrt N}.
$$

<details>
<summary><strong>Solution</strong></summary>

Expanding around the saddle,

$$
s[\Phi]=s[\Phi_*]+\frac12\delta\Phi H\delta\Phi+\cdots.
$$

The exponent contains

$$
N\cdot\frac12\delta\Phi H\delta\Phi.
$$

For this quadratic term to be of order one in the fluctuation integral, we need

$$
N(\delta\Phi)^2=O(1),
$$

so

$$
\delta\Phi=O(N^{-1/2}).
$$

Thus the natural variable is $\eta=\sqrt N(\Phi-\Phi_*)$.

</details>

### Exercise 3: Two competing saddles

Suppose

$$
Z_N=e^{-Nf_1(t)}+e^{-Nf_2(t)},
$$

where $f_1(t)<f_2(t)$ for $t<0$ and $f_2(t)<f_1(t)$ for $t>0$, with $f_1(0)=f_2(0)$. Show that the large-$N$ free energy

$$
F(t)=-\lim_{N\to\infty}\frac1N\log Z_N
$$

is the lower envelope of $f_1$ and $f_2$.

<details>
<summary><strong>Solution</strong></summary>

Write

$$
Z_N=e^{-N\min(f_1,f_2)}\left[1+e^{-N|f_1-f_2|}\right].
$$

Then

$$
-\frac1N\log Z_N
=
\min(f_1,f_2)-\frac1N\log\left[1+e^{-N|f_1-f_2|}\right].
$$

For fixed $t\neq0$, the second term vanishes as $N\to\infty$, so

$$
F(t)=\min(f_1(t),f_2(t)).
$$

At $t=0$, both saddles contribute equally at leading exponential order. If the slopes of $f_1$ and $f_2$ differ at $t=0$, the limiting free energy has a cusp, signaling a first-order transition in the large-$N$ limit.

</details>

### Exercise 4: Compare vector and matrix factorization

A vector model has $O(N)$ singlet

$$
\rho=\frac1N\phi_i\phi_i.
$$

A matrix model has normalized single-trace observable

$$
\mathcal O=\frac1N\operatorname{tr}M^2.
$$

Why is it natural for connected correlators of $\rho$ to scale as $1/N$, while connected correlators of $\mathcal O$ often scale as $1/N^2$?

<details>
<summary><strong>Solution</strong></summary>

The vector model has $O(N)$ microscopic components. A normalized average over $N$ components has relative fluctuations suppressed like $1/N$, so connected singlet correlators naturally scale as $1/N$.

The matrix model has $O(N^2)$ microscopic components. In the planar normalization, the free energy scales as $N^2$, and normalized single-trace observables behave classically with connected correlators suppressed by $1/N^2$.

Both are factorization statements, but the number of underlying degrees of freedom differs:

$$
N\quad\text{versus}\quad N^2.
$$

</details>

## References

### Standard first pass

- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on $O(N)$ vector models at large $N$, nonlinear sigma models, saddle-point equations, and corrections to scaling.
- M. Mariño, *Instantons and Large N*, especially the chapters on sigma models, matrix models, and large-$N$ QCD.
- S. Coleman, *Aspects of Symmetry*, especially the lecture “1/N.”
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on large $N$, loop dynamics, and random surfaces.

### Deeper references

- G. ’t Hooft, “A Planar Diagram Theory for Strong Interactions,” for the original topological organization of large-$N$ gauge diagrams.
- E. Witten, classic papers on large-$N$ QCD, baryons, theta dependence, and the $CP^{N-1}$ model.
- E. Brézin, C. Itzykson, G. Parisi, and J.-B. Zuber, “Planar Diagrams,” for matrix-model large-$N$ saddle methods.
- Modern resurgence literature on large-$N$ saddles, eigenvalue instantons, and transseries in matrix and sigma models.

## Version history

- **2026-06-28:** Linked to the dedicated eigenvalue-density and double-scaling pages.
- **2026-06-27:** Initial polished page explaining large $N$ as steepest descent, including collective variables, Hessians, multiple saddles, factorization powers, and beyond-all-orders effects.
