---
title: "Crossover and Dangerously Irrelevant Operators"
description: "Explains crossover scaling, correction-to-scaling variables, and dangerously irrelevant operators near RG fixed points and critical phenomena."
sidebar:
  label: "Crossover and Dangerous Irrelevance"
  order: 10
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Wegner 1972; Fisher 1974; Zinn-Justin 2021; Cardy 1996; Goldenfeld 1992; Sachdev 2011."
topics:
  - crossover scaling
  - dangerously irrelevant operators
  - corrections to scaling
  - critical phenomena
  - scaling fields
  - universality
canonicalTopics:
  - crossover-scaling
  - dangerously-irrelevant-operators
  - corrections-to-scaling
  - critical-exponents
researchStatus:
  established:
    - "Crossover scaling, correction-to-scaling exponents, and dangerously irrelevant variables are standard parts of Wilsonian critical phenomena and scaling theory."
  active:
    - "Dangerously irrelevant perturbations remain important in finite-size scaling, deconfined criticality, gauge theories, clock anisotropies, multicritical phenomena, and numerical interpretation of slowly drifting critical behavior."
---

## Summary

A fixed point controls a scaling regime, but a physical system need not remain in one scaling regime forever. An RG trajectory can pass near one fixed point, display its approximate exponents over a wide range of scales, and then cross over to behavior controlled by another fixed point, a massive phase, or an ordered phase. **Crossover** is the systematic study of such transitions between scaling descriptions.

The basic crossover scaling form is

$$
f_s(t,g)=|t|^{d/y_t}\,\mathcal F_\pm\!\left(\frac{g}{|t|^\phi}\right),
\qquad
\phi\equiv\frac{y_g}{y_t},
$$

where $f_s$ is the singular part of the free-energy density, $t$ is the primary thermal scaling field, $g$ is a second relevant perturbation, and $\phi$ is the crossover exponent. The dimensionless ratio $g/|t|^\phi$ decides which scaling regime the system sees.

A **dangerously irrelevant operator** is subtler. It has negative RG eigenvalue at the critical fixed point, so it is irrelevant for reaching the fixed point, but some observables depend singularly on it when it is sent to zero. The classic example is the quartic coupling in scalar theory above the upper critical dimension: it is irrelevant at the Gaussian fixed point for $d>4$, but it stabilizes the ordered phase and controls the order-parameter amplitude.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Crossover and dangerously irrelevant operator map](/figures/renormalization-rg-eft/crossover-dangerously-irrelevant-map.svg)

<figcaption>

Crossover occurs when a trajectory passes from one scaling regime to another. An ordinary irrelevant perturbation gives analytic corrections to scaling and fades away near the fixed point. A dangerously irrelevant perturbation also fades away at the fixed point, but setting it to zero can make an ordered-phase observable singular or ill-defined.

</figcaption>
</figure>

:::note[One sentence to remember]
Crossover tells you which fixed point controls a given range of scales; dangerous irrelevance tells you that an irrelevant coupling can still be necessary for some observables to make sense.
:::

## Prerequisites

You should know [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/), [Universality Classes](/renormalization-rg-eft/fixed-points-critical-phenomena/universality-classes/), and [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/).

The most important technical prerequisite is the idea of a **scaling field**. Near a fixed point, the useful variables are not usually the microscopic couplings themselves, but combinations of them that transform simply under linearized RG flow.

## Core idea

Near a fixed point, the RG flow can be linearized. If $u_i$ are scaling fields, then under a coarse-graining factor $b>1$,

$$
u_i(b)=b^{y_i}u_i.
$$

The sign of $y_i$ decides the local role of the perturbation:

| RG eigenvalue | Local behavior near the fixed point | Usual name |
|---:|---|---|
| $y_i>0$ | grows under coarse graining | relevant |
| $y_i=0$ | decided by nonlinear terms | marginal |
| $y_i<0$ | shrinks under coarse graining | irrelevant |

If there is only one relevant perturbation, one tunes it to zero and sees one clean critical point. If there are two or more relevant perturbations, different ratios of scaling fields lead to different regimes. This is crossover.

If an irrelevant perturbation appears only through regular corrections, it can be dropped at leading order. If an irrelevant perturbation appears through a singular scaling function, it cannot be dropped for all purposes. This is dangerous irrelevance.

The slogan is:

$$
\text{irrelevant at the fixed point}
\not\Rightarrow
\text{irrelevant for every observable in every phase}.
$$

That arrow failure is not a loophole in RG. It is one of the things RG teaches you to notice.

## Setup and conventions

This page uses the statistical-physics RG convention in which $b>1$ means coarse graining toward the infrared. Equivalently,

$$
\ell\equiv\log b
$$

increases as short-distance degrees of freedom are removed. Near a fixed point,

$$
\frac{du_i}{d\ell}=y_i u_i+O(u^2).
$$

The thermal scaling field is called $t$. It is proportional to $T-T_c$ in a statistical system, or to a relevant mass-like perturbation in a Euclidean field theory. Its RG eigenvalue is

$$
y_t=\frac{1}{\nu},
$$

where $\nu$ is the correlation-length exponent. A magnetic or source-like scaling field is called $h$, with eigenvalue $y_h$.

The singular part of the free-energy density is denoted by $f_s$. Under RG it obeys the homogeneous scaling law

$$
f_s(t,h,u_1,u_2,\ldots)
=b^{-d}
 f_s(b^{y_t}t,b^{y_h}h,b^{y_1}u_1,b^{y_2}u_2,\ldots),
$$

up to analytic background terms. Other observables follow from differentiating $f_s$ or from their own scaling dimensions.

When the same letter appears in different chapters, the meaning is always local to the discussion. For example, $u$ on this page often denotes a scaling field or quartic coupling, not necessarily a Wilsonian coupling in a specific microscopic action.

## Crossover from two relevant perturbations

Suppose a fixed point has two relevant scaling fields, $t$ and $g$, with eigenvalues

$$
y_t>0,
\qquad
y_g>0.
$$

The singular free energy satisfies

$$
f_s(t,g)=b^{-d} f_s(b^{y_t}t,b^{y_g}g).
$$

Choose $b=|t|^{-1/y_t}$, so that $b^{y_t}t=\pm1$. Then

$$
f_s(t,g)=|t|^{d/y_t}
\mathcal F_\pm\!\left(g|t|^{-y_g/y_t}\right).
$$

The dimensionless crossover variable is

$$
X\equiv\frac{g}{|t|^\phi},
\qquad
\phi\equiv\frac{y_g}{y_t}.
$$

The exponent $\phi$ is the **crossover exponent**. It tells you how rapidly the second perturbation becomes important as the critical point is approached.

If $|X|\ll1$, the flow initially behaves as though $g=0$. If $|X|\gg1$, the perturbation $g$ dominates before the system reaches the asymptotic scaling regime associated with the $g=0$ fixed point. The crossover scale $\xi_\times$ is estimated by the point where

$$
g b^{y_g}\sim1,
$$

so

$$
b_\times\sim |g|^{-1/y_g}.
$$

The system can display the first fixed point only on length scales shorter than this crossover scale. Past it, the flow notices $g$.

This is why experiments and simulations often see **effective exponents**. A finite system or finite measurement window may live in the shoulder between two fixed points rather than in either asymptotic regime.

## Magnetic-field crossover

A simple and important example is an Ising-like critical point in a small magnetic field. The two relevant fields are the reduced temperature $t$ and magnetic field $h$.

The singular free energy has the scaling form

$$
f_s(t,h)=|t|^{d/y_t}
\mathcal F_\pm\!\left(\frac{h}{|t|^{y_h/y_t}}\right).
$$

Using the standard exponent identity

$$
\frac{y_h}{y_t}=\beta\delta,
$$

this becomes

$$
f_s(t,h)=|t|^{2-\alpha}
\mathcal F_\pm\!\left(\frac{h}{|t|^{\beta\delta}}\right).
$$

The magnetic field cuts off the zero-field critical singularity. Along $h=0$, the magnetization behaves as

$$
M\sim(-t)^\beta
\qquad (t<0).
$$

Along the critical isotherm $t=0$, it behaves as

$$
M\sim h^{1/\delta}.
$$

The scaling function is the object that connects these limits. It is not a decoration; it is the mathematical expression of the crossover between temperature-dominated and field-dominated scaling.

## Symmetry-breaking crossover

Another common crossover occurs when a perturbation reduces the symmetry of the fixed point. For instance, an $O(N)$-symmetric fixed point may be perturbed by an anisotropy that preserves only a discrete subgroup. The perturbation has some RG eigenvalue $y_a$ at the $O(N)$ fixed point.

If

$$
y_a>0,
$$

then the anisotropy is relevant and the $O(N)$ fixed point is unstable. The system may show approximate $O(N)$ scaling over intermediate scales, but asymptotically it flows elsewhere.

If

$$
y_a<0,
$$

then the anisotropy is irrelevant at the critical fixed point. The transition can have $O(N)$ critical exponents even though the microscopic Hamiltonian has less symmetry. But in the ordered phase the same anisotropy may select preferred directions and produce domain walls or a secondary length scale. In that case the anisotropy is a classic candidate for dangerous irrelevance.

This pattern is one way emergent symmetry appears. A microscopic lattice system may not have the full rotational or internal symmetry of the fixed point, but the symmetry-breaking perturbations can be irrelevant at criticality.

## Corrections to scaling

Most irrelevant operators are not dangerous. They give ordinary corrections to scaling.

Let $w$ be an irrelevant scaling field with

$$
y_w=-\omega<0.
$$

For an observable $\mathcal O$ with critical exponent $\rho$, the scaling form often looks like

$$
\mathcal O(t,w)=|t|^\rho
\left[A_0+A_1 w |t|^{\omega\nu}+A_2 w^2 |t|^{2\omega\nu}+\cdots\right].
$$

The leading term is universal up to normalization conventions and nonuniversal amplitudes. The corrections vanish as $t\to0$ because

$$
w |t|^{\omega\nu}\to0.
$$

The exponent $\omega$ is the leading correction-to-scaling exponent. It is the negative of the largest irrelevant RG eigenvalue:

$$
\omega=-y_{\text{leading irrelevant}}.
$$

Corrections to scaling matter in practice. In numerical work, if $\omega$ is small, irrelevant perturbations die slowly. A system can look as if it has drifting exponents even when the asymptotic universality class is perfectly ordinary.

The key feature of ordinary irrelevant variables is regularity: the scaling function has a smooth limit as the irrelevant coupling goes to zero.

## Dangerously irrelevant operators

Let $u$ be irrelevant at a fixed point:

$$
y_u<0.
$$

For an ordinary irrelevant variable, setting $u=0$ inside the scaling function is harmless at leading order. For a dangerously irrelevant variable, it is not. The scaling function is singular as $u\to0$.

Consider an observable $\mathcal O$ with scaling dimension $x_\mathcal O$ in the sense that

$$
\mathcal O(t,u)=b^{-x_\mathcal O}
\mathcal O(b^{y_t}t,b^{y_u}u).
$$

Choose $b=|t|^{-1/y_t}$. Then

$$
\mathcal O(t,u)=|t|^{x_\mathcal O/y_t}
\mathcal G_\pm\!\left(u|t|^{-y_u/y_t}\right).
$$

Since $y_u<0$, the argument

$$
z=u|t|^{-y_u/y_t}
$$

goes to zero as $t\to0$. If $\mathcal G_\pm(z)$ is finite at $z=0$, then $u$ only changes amplitudes and corrections. But if

$$
\mathcal G_\pm(z)\sim z^{-\kappa}
\qquad (z\to0),
$$

then

$$
\mathcal O(t,u)
\sim
u^{-\kappa}|t|^{(x_\mathcal O+\kappa y_u)/y_t}.
$$

The exponent is shifted. The amplitude is singular in $u$. The irrelevant variable was not irrelevant to this observable.

This is dangerous irrelevance in one equation.

:::tip[Harmless versus dangerous]
An irrelevant variable is harmless when the limit $u\to0$ and the critical limit commute. It is dangerous when they do not.
:::

## Example: the quartic coupling above four dimensions

The cleanest example is scalar $\phi^4$ theory above its upper critical dimension. Consider the Landau–Ginzburg functional

$$
S=\int d^d x\left[\frac12(\partial\phi)^2+\frac12 r\phi^2+\frac{u}{4!}\phi^4-h\phi\right].
$$

At the Gaussian fixed point, the quartic coupling has engineering RG eigenvalue

$$
y_u=4-d.
$$

For $d>4$, this is negative. The quartic coupling is irrelevant at the critical fixed point.

If one only looked at the critical point itself, one might be tempted to set $u=0$. But for $r<0$, the potential

$$
V(\phi)=\frac12 r\phi^2+\frac{u}{4!}\phi^4
$$

is unstable unless $u>0$. Minimizing at $h=0$ gives

$$
0=\frac{dV}{d\phi}=r\phi+\frac{u}{6}\phi^3,
$$

so the ordered-phase minimum satisfies

$$
M^2=\phi_0^2=-\frac{6r}{u}.
$$

Thus

$$
M\sim u^{-1/2}(-r)^{1/2}.
$$

The exponent $\beta=1/2$ is the mean-field value. The amplitude diverges as $u\to0$ because the quartic term stabilizes the ordered phase.

Now compare this with naive Gaussian scaling. At the Gaussian fixed point in $d>4$,

$$
x_\phi=\frac{d-2}{2},
\qquad
y_t=2,
\qquad
y_u=4-d.
$$

If $u$ were harmless, the order parameter would scale as

$$
M\sim |t|^{x_\phi/y_t}=|t|^{(d-2)/4}.
$$

That is not the mean-field exponent $1/2$ except at $d=4$. The singular dependence

$$
\mathcal G(z)\sim z^{-1/2}
$$

restores

$$
M\sim u^{-1/2}|t|^{(d-2)/4+(4-d)/4}=u^{-1/2}|t|^{1/2}.
$$

This example also explains why hyperscaling fails above the upper critical dimension. The Gaussian fixed point controls the critical singularity, but the dangerously irrelevant quartic coupling prevents the simplest hyperscaling form from applying to all observables.

## Example: clock anisotropy near an XY fixed point

A second useful example is a clock anisotropy near an XY-like fixed point. Let the order parameter be written as

$$
\Phi=\rho e^{i\theta}.
$$

An anisotropy may add a term such as

$$
\delta S=\lambda_q\int d^d x\,\rho^q\cos(q\theta).
$$

At the critical fixed point, $\lambda_q$ may be irrelevant for sufficiently large $q$. Then the transition can display emergent $U(1)$ symmetry and XY critical exponents even if the microscopic model has only a $\mathbb Z_q$ symmetry.

In the ordered phase, however, the same anisotropy selects one of $q$ preferred angles. It can determine domain walls, discrete vacua, and a length scale over which the order parameter realizes that it is not truly $U(1)$-symmetric. Thus it is irrelevant for the leading critical exponents but relevant to the structure of the ordered phase.

The exact relevance of such anisotropies depends on dimension, $q$, and the fixed point. The conceptual lesson is stable: emergent symmetry at criticality does not automatically imply the same symmetry deep in the ordered phase.

## Finite-size crossover

Crossover is not only about extra couplings. Finite size is also a scaling variable.

If a system has linear size $L$, the singular free energy obeys

$$
f_s(t,L)=b^{-d}f_s(b^{y_t}t,L/b).
$$

Choose $b=L$. Then

$$
f_s(t,L)=L^{-d}\mathcal F(tL^{y_t}).
$$

Equivalently, since $y_t=1/\nu$,

$$
f_s(t,L)=L^{-d}\mathcal F(tL^{1/\nu}).
$$

The dimensionless variable

$$
X_L=tL^{1/\nu}
$$

compares the system size $L$ with the infinite-volume correlation length $\xi\sim |t|^{-\nu}$. If $|X_L|\gg1$, the system behaves approximately as infinite. If $|X_L|\lesssim1$, finite-size effects cut off the critical singularity.

Dangerously irrelevant variables can modify finite-size scaling above the upper critical dimension and in systems with multiple long lengths. This is one reason finite-size data must be interpreted with care: the leading asymptotic theory may not contain all lengths visible in finite systems.

## How to diagnose dangerous irrelevance

The following questions are useful in practice.

**First, is the coupling irrelevant at the critical fixed point?** If $y_u\ge0$, the phrase dangerously irrelevant is not the right local classification.

**Second, does setting the coupling to zero change the phase, stability, or observable definition?** If $u=0$ makes an ordered phase unstable, removes a discrete anisotropy, changes a constraint, or eliminates a topological fugacity, danger is plausible.

**Third, is the scaling function singular as $u\to0$?** The mathematical signature is not merely that $u$ appears in a formula. It is that the scaling limit is nonuniform.

**Fourth, does the coupling introduce a second length scale?** In many examples, the critical correlation length is not the only long length. A second scale can govern domain walls, anisotropy locking, confinement, or crossover into the ordered phase.

**Fifth, does the coupling affect exponents or only amplitudes?** Both are possible. The quartic coupling above four dimensions changes naive hyperscaling predictions for some exponents. Clock anisotropy may leave leading transition exponents intact while affecting ordered-phase lengths and finite-size scaling.

## Crossover, dangerous irrelevance, and universality

Crossover does not weaken universality. It refines it. Universality says that sufficiently close to a fixed point, after enough coarse graining, many microscopic details disappear. Crossover says that the phrase "sufficiently close" has quantitative content.

A system may display several universal regimes:

$$
\text{microscopic model}
\longrightarrow
\text{preasymptotic fixed point}
\longrightarrow
\text{asymptotic fixed point}
\longrightarrow
\text{massive or ordered phase}.
$$

Each arrow can have its own crossover function and its own useful approximation.

Dangerously irrelevant operators also do not invalidate universality. The singular powers and scaling forms are themselves universal once the correct scaling fields are identified. What fails is the oversimplified instruction "drop all irrelevant couplings immediately." The more accurate instruction is:

$$
\text{drop irrelevant variables only after checking that the scaling functions are regular in them}.
$$

This distinction is annoying, but it is load-bearing. It is one of the reasons Wilsonian RG is more powerful than dimensional analysis with better branding.

## Common pitfalls

**Thinking crossover is a mistake or artifact.** Crossover is real RG physics. It appears whenever more than one scale or relevant perturbation competes.

**Treating effective exponents as final exponents.** A finite window can show slopes that are not the asymptotic critical exponents. This is especially common near marginal or weakly irrelevant perturbations.

**Dropping all irrelevant couplings blindly.** Irrelevant couplings usually give corrections to scaling, but dangerous irrelevant variables can affect ordered-phase observables, finite-size scaling, and even exponent identities.

**Confusing dangerous irrelevance with relevance.** A dangerously irrelevant operator is still irrelevant at the critical fixed point. Its danger comes from singular dependence away from or at the edge of the critical scaling limit.

**Assuming emergent symmetry persists everywhere.** A symmetry can emerge at the critical point because anisotropy is irrelevant there, while the same anisotropy controls the ordered phase.

**Forgetting nonuniversal amplitudes.** Singular dependence such as $u^{-1/2}$ in the ordered-phase amplitude does not mean $u$ has become a universal number. It means the scaling form knows that the $u\to0$ limit is singular.

## Relations to other pages

This page completes the first pass through the Fixed Points and Critical Phenomena chapter. It relies on [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/) for scaling fields, [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/) for exponent definitions, [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/) for hyperscaling assumptions, and [Universality Classes](/renormalization-rg-eft/fixed-points-critical-phenomena/universality-classes/) for basin-of-attraction language.

It prepares the operator-based material in [Local Operators and OPE](/renormalization-rg-eft/local-operators-and-ope/), where scaling fields become local operator perturbations and where irrelevant, redundant, and equation-of-motion operators must be handled carefully.

It also prepares later pages on effective field theory. EFT power counting routinely says that higher-dimension operators are suppressed. That statement is correct inside its domain, but crossover and dangerous irrelevance explain why one must still ask which observable, which phase, and which limiting procedure are being used.

## Research status

The core ideas on this page are established. Crossover scaling, correction-to-scaling exponents, finite-size scaling, and dangerously irrelevant variables are standard tools in RG and critical phenomena.

The active frontier is not the definition but the diagnosis. In numerical simulations and strongly coupled systems, it can be hard to decide whether slowly drifting behavior comes from an ordinary irrelevant operator with small $\omega$, a dangerously irrelevant perturbation, a nearby fixed point, a weak first-order transition, or a genuinely new universality class. This issue appears in deconfined criticality, lattice gauge theory, clock and anisotropy models, multicritical systems, and quantum critical matter.

## Exercises

### Exercise 1: Derive the crossover exponent

Assume

$$
f_s(t,g)=b^{-d}f_s(b^{y_t}t,b^{y_g}g),
$$

with $y_t>0$ and $y_g>0$. Show that the scaling form can be written as

$$
f_s(t,g)=|t|^{d/y_t}\mathcal F_\pm\!\left(\frac{g}{|t|^\phi}\right),
$$

and find $\phi$.

<details><summary><strong>Solution</strong></summary>

Choose the coarse-graining factor $b=|t|^{-1/y_t}$. Then

$$
b^{y_t}t=\pm1,
$$

and

$$
b^{y_g}g=g|t|^{-y_g/y_t}.
$$

Therefore

$$
f_s(t,g)=|t|^{d/y_t}f_s(\pm1,g|t|^{-y_g/y_t}).
$$

Defining

$$
\mathcal F_\pm(X)=f_s(\pm1,X)
$$

and

$$
\phi=\frac{y_g}{y_t},
$$

gives the desired form.

</details>

### Exercise 2: Correction-to-scaling exponent

Let $w$ be the leading irrelevant scaling field with $y_w=-\omega<0$. Show that an observable of leading critical behavior $\mathcal O(t)\sim |t|^\rho$ has corrections of the form

$$
\mathcal O(t,w)=|t|^\rho\left[A_0+A_1 w |t|^{\omega\nu}+\cdots\right].
$$

<details><summary><strong>Solution</strong></summary>

The scaling form is

$$
\mathcal O(t,w)=b^{-x_\mathcal O}\mathcal O(b^{y_t}t,b^{-\omega}w).
$$

Choose $b=|t|^{-1/y_t}=|t|^{-\nu}$. Then

$$
\mathcal O(t,w)=|t|^{x_\mathcal O/y_t}\mathcal G_\pm(w|t|^{\omega/y_t}).
$$

Since $\nu=1/y_t$,

$$
w|t|^{\omega/y_t}=w|t|^{\omega\nu}.
$$

If $w$ is an ordinary irrelevant variable, $\mathcal G_\pm$ is regular at the origin:

$$
\mathcal G_\pm(z)=A_0+A_1z+\cdots.
$$

Writing $\rho=x_\mathcal O/y_t$ gives the claimed result.

</details>

### Exercise 3: Dangerous irrelevance of the quartic coupling

For

$$
V(\phi)=\frac12 r\phi^2+\frac{u}{4!}\phi^4,
$$

with $r<0$ and $u>0$, minimize $V$ and show that the ordered-phase magnetization scales as

$$
M\sim u^{-1/2}(-r)^{1/2}.
$$

Explain why this shows that $u$ cannot simply be set to zero even when $u$ is irrelevant at the Gaussian fixed point for $d>4$.

<details><summary><strong>Solution</strong></summary>

The minimum obeys

$$
0=\frac{dV}{d\phi}=r\phi+\frac{u}{6}\phi^3.
$$

Besides the solution $\phi=0$, the ordered solutions satisfy

$$
r+\frac{u}{6}\phi^2=0.
$$

Thus

$$
M^2=\phi_0^2=-\frac{6r}{u},
$$

and

$$
M=\sqrt{\frac{-6r}{u}}\sim u^{-1/2}(-r)^{1/2}.
$$

For $d>4$, $u$ has RG eigenvalue $y_u=4-d<0$ at the Gaussian fixed point. It is irrelevant for approaching the critical fixed point. But for $r<0$, setting $u=0$ makes the potential unbounded below and destroys the ordered phase. The dependence on $u$ is singular as $u\to0$, so $u$ is dangerously irrelevant.

</details>

### Exercise 4: Finite-size scaling variable

Starting from

$$
f_s(t,L)=b^{-d}f_s(b^{y_t}t,L/b),
$$

show that

$$
f_s(t,L)=L^{-d}\mathcal F(tL^{1/\nu}).
$$

<details><summary><strong>Solution</strong></summary>

Choose $b=L$. Then $L/b=1$ and

$$
f_s(t,L)=L^{-d}f_s(L^{y_t}t,1).
$$

Define

$$
\mathcal F(X)=f_s(X,1).
$$

Since $y_t=1/\nu$,

$$
L^{y_t}t=tL^{1/\nu}.
$$

Therefore

$$
f_s(t,L)=L^{-d}\mathcal F(tL^{1/\nu}).
$$

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- F. J. Wegner, classic papers on corrections to scaling and scaling fields.
- Michael E. Fisher, classic papers and reviews on scaling, crossover, and critical phenomena.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the discussion of RG, scaling equations, critical behavior, and corrections to scaling.
- John Cardy, *Scaling and Renormalization in Statistical Physics*.
- Nigel Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*.
- Subir Sachdev, *Quantum Phase Transitions*, for quantum critical crossover and dangerously irrelevant couplings in condensed-matter settings.

## Version history

- 2026-06-17: First polished draft. Added crossover scaling, correction-to-scaling variables, dangerously irrelevant operators, examples above the upper critical dimension and with anisotropy, exercises, and figure.
