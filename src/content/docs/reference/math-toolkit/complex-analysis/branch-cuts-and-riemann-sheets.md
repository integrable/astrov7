---
title: "Branch Cuts and Riemann Sheets"
description: "Explains multivalued functions, branch points, branch cuts, monodromy, discontinuities, Riemann sheets, physical and unphysical sheets, and their use in QFT thresholds, spectral densities, and resonances."
sidebar:
  label: "Branch Cuts and Riemann Sheets"
  order: 3
level: Graduate
status: "Polished draft"
source: "Standard references on complex analysis, analytic structure, scattering theory, and QFT, including Ahlfors, Stein–Shakarchi, Conway, Titchmarsh, Whittaker–Watson, Eden–Landshoff–Olive–Polkinghorne, Weinberg, Srednicki, Schwartz, Zee, Zinn-Justin, Di Francesco–Mathieu–Sénéchal, and mathematical-physics treatments of boundary values and spectral representations."
topics:
  - branch cuts
  - branch points
  - Riemann sheets
  - monodromy
  - discontinuities
  - logarithms
  - square roots
  - thresholds
  - spectral density
  - resonance poles
  - analytic structure
canonicalTopics:
  - branch-cut
  - branch-point
  - riemann-sheet
  - monodromy
  - discontinuity
  - logarithm
  - square-root
  - threshold
  - spectral-density
  - resonance-pole
  - analytic-structure
researchStatus:
  established:
    - "Branch points, branch cuts, monodromy, discontinuities, and Riemann sheets are standard complex-analysis tools for describing multivalued functions and QFT analytic structure."
    - "Threshold cuts and sheet changes are standard in spectral representations, scattering theory, loop integrals, and resonance physics."
  active:
    - "Modern work continues to refine branch-cut and sheet structures in amplitudes, Landau singularities, finite-density QFT, Lorentzian CFT, resurgence, and analytic bootstrap methods."
---

## Summary

A branch cut is a bookkeeping device for making a multivalued analytic expression single-valued on a chosen domain. A Riemann sheet is one copy of that domain; moving around a branch point can take the value of the function to another sheet. In QFT, this is not decorative complex-analysis folklore. It is how thresholds, continua, spectral densities, unstable particles, and many loop integrals advertise themselves.

The simplest examples already contain the whole story:

$$
\log z \mapsto \log z+2\pi i,
\qquad
\sqrt z \mapsto -\sqrt z,
$$

when $z$ makes one counterclockwise loop around the origin. No single-valued holomorphic function on the punctured plane can behave this way. To use such expressions, one either cuts the plane or replaces the plane by a multi-sheeted surface.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Diagram showing a branch point, a branch cut in the complex plane, and two Riemann sheets glued along the cut.](/figures/math-toolkit/branch-cuts-riemann-sheets.svg)

<figcaption>

A branch cut turns a multivalued expression into a single-valued branch on a chosen domain. The underlying analytic object is better pictured as living on sheets glued along cut edges. Crossing the cut changes sheet; circling the branch point measures monodromy.

</figcaption>
</figure>

The important invariant is not the exact position of the cut. Cuts can often be moved. The invariant data are the branch points, the monodromy around them, and the discontinuity between boundary values on opposite sides of the cut.

## Prerequisites

You should know [Analytic Functions](/math-toolkit/complex-analysis/analytic-functions/), [Residues and Contours](/math-toolkit/complex-analysis/residues-and-contours/), [Principal Values](/math-toolkit/analysis-distributions-fourier/principal-values/), [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/), and [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/).

We use the boundary-value notation

$$
F(x\pm i0)=\lim_{\epsilon\downarrow0}F(x\pm i\epsilon),
$$

whenever the limit exists as a function or distribution. The discontinuity across a cut on the real axis is

$$
\operatorname{Disc}F(x)=F(x+i0)-F(x-i0).
$$

This sign convention is fixed on this page. Other books sometimes define the opposite sign. The sign is not deep; consistency is.

## Multivaluedness is path dependence

A holomorphic function on a connected open domain is single-valued by definition: at each point of the domain it has one value. Expressions like $\log z$ and $\sqrt z$ are different. They are locally holomorphic after a choice of value, but continuing that value around a closed loop can change it.

For the logarithm, write

$$
z=re^{i\theta}.
$$

Locally,

$$
\log z=\log r+i\theta.
$$

The problem is that $\theta$ is not single-valued on $\mathbb C^\times$. A loop around the origin sends

$$
\theta\mapsto\theta+2\pi,
$$

so

$$
\log z\mapsto\log z+2\pi i.
$$

For the square root,

$$
\sqrt z=\sqrt r\,e^{i\theta/2}.
$$

A loop around the origin sends

$$
\sqrt z\mapsto \sqrt r\,e^{i(\theta+2\pi)/2}
=-\sqrt r\,e^{i\theta/2}
=-\sqrt z.
$$

The logarithm needs infinitely many sheets. The square root needs two. Already here you can see the physics vocabulary trying to sneak in: a branch point is a place where analytic continuation around a loop changes the state of the function.

## Branches and cuts

A **branch** is a single-valued choice of a multivalued expression on a domain. A **branch cut** is a curve removed from the plane so that such a choice becomes possible.

For example, choose an angle interval

$$
\theta_0<\operatorname{Arg}_{\theta_0}z<\theta_0+2\pi.
$$

Then define

$$
\operatorname{Log}_{\theta_0}z
=\log|z|+i\operatorname{Arg}_{\theta_0}z.
$$

This is a branch of the logarithm on the plane cut along the ray

$$
\arg z=\theta_0.
$$

On this branch,

$$
\frac{d}{dz}\operatorname{Log}_{\theta_0}z=\frac1z.
$$

The derivative is local, so it does not care where the cut is. The global value does care, because moving around the origin changes the integral of $1/z$:

$$
\oint_{|z|=R}\frac{dz}{z}=2\pi i.
$$

This integral is the obstruction to a single-valued logarithm on $\mathbb C^\times$. If there were a single-valued holomorphic $L$ with $L'(z)=1/z$ on $\mathbb C^\times$, then the integral of $L'$ around every closed loop would vanish. It does not.

The cut is therefore not the obstruction itself. The obstruction is the puncture and the nontrivial winding around it. The cut is our way of refusing to allow the offending loop inside the chosen domain.

## The logarithm and its discontinuity

Take the principal logarithm

$$
\operatorname{Log}z=\log|z|+i\operatorname{Arg}z,
\qquad -\pi<\operatorname{Arg}z<\pi.
$$

The cut is the negative real axis. For $a>0$,

$$
\operatorname{Log}(-a+i0)=\log a+i\pi,
$$

while

$$
\operatorname{Log}(-a-i0)=\log a-i\pi.
$$

Therefore

$$
\operatorname{Disc}\operatorname{Log}(-a)=2\pi i.
$$

The same formula changes sign if the function is written as $\operatorname{Log}(-s)$ and the discontinuity is taken in the variable $s$ across $s>0$:

$$
\operatorname{Disc}_s\operatorname{Log}(-s)
=\operatorname{Log}(-s-i0)-\operatorname{Log}(-s+i0)
=-2\pi i,
\qquad s>0.
$$

The two statements are compatible. The minus sign comes from the map $z=-s$, which flips which side of the cut is approached. This is exactly the kind of sign that makes loop calculations look haunted when the variables are not named carefully.

In perturbative QFT, logarithms of kinematic invariants are everywhere. A one-loop answer may contain terms like

$$
\log\frac{-s-i0}{\mu^2},
$$

and the imaginary part for $s>0$ is not an accident. It is the boundary value of a logarithm across its cut.

## Square roots and threshold behavior

The square root is the local model for many thresholds. Choose the branch

$$
\sqrt z=\sqrt r\,e^{i\theta/2},
\qquad -\pi<\theta<\pi.
$$

Again the cut is the negative real axis. For $a>0$,

$$
\sqrt{-a+i0}=i\sqrt a,
\qquad
\sqrt{-a-i0}=-i\sqrt a,
$$

so

$$
\operatorname{Disc}\sqrt{-a}=2i\sqrt a.
$$

For a two-particle threshold, a typical square-root variable is

$$
k(s)=\sqrt{\frac{s}{4}-m^2}.
$$

The threshold is at

$$
s_0=4m^2.
$$

A standard choice puts a cut along $s\ge s_0$. Just above the cut,

$$
k(s+i0)=+\sqrt{\frac{s}{4}-m^2},
\qquad s>s_0,
$$

while crossing to the other side gives

$$
k(s-i0)=-\sqrt{\frac{s}{4}-m^2}
$$

on the adjacent sheet. The sign flip is the algebraic shadow of a new sheet.

This is why square roots appear in phase space. In $3+1$ dimensions, the two-body phase-space factor contains a threshold square root. The cut beginning at $s=4m^2$ is the analytic signal that a continuum of two-particle states can go on shell.

## Boundary values and spectral densities

A branch cut often represents a continuum rather than an isolated singularity. In a spectral representation, a two-point function may have the schematic form

$$
G(z)=\int_{\mu_0^2}^{\infty}d\mu^2\,\frac{\rho(\mu^2)}{z-\mu^2},
$$

where $z$ is a complex invariant. The integrand has a pole at $z=\mu^2$ for each value in the continuum. The integral over continuum masses produces a cut on

$$
z\in[\mu_0^2,\infty).
$$

Using

$$
\frac{1}{x+i0}=\operatorname{PV}\frac1x-i\pi\delta(x),
$$

one finds

$$
\operatorname{Disc}G(s)
=G(s+i0)-G(s-i0)
=-2\pi i\,\rho(s),
$$

for this particular denominator convention. If instead the denominator is written as $\mu^2-z$, the sign changes. The important point is not the sign in isolation. The important point is that the discontinuity is local spectral data.

This is the clean distinction between a pole and a cut:

| Analytic feature | Typical physical meaning |
|---|---|
| isolated pole | stable particle, bound state, normal mode, zero mode, collective excitation |
| branch point | threshold, massless singularity, accumulation point, endpoint of continuum |
| branch cut | continuum of states, spectral support, multiparticle channel |
| second-sheet pole | resonance or unstable excitation |

This table is schematic, not a theorem that covers every model. But it is a reliable map for first contact with QFT analytic structure.

## Riemann sheets

A Riemann sheet is one branch of a multivalued object. The full Riemann surface is obtained by gluing sheets along cuts in such a way that the multivalued expression becomes single-valued.

For $w=\sqrt z$, the relation

$$
w^2=z
$$

defines a two-sheeted surface over the $z$-plane. Away from $z=0$, there are two values of $w$. Going once around $z=0$ swaps them. Going twice returns to the original value.

For $w=\log z$, there are infinitely many sheets:

$$
w_n=\log r+i(\theta+2\pi n),
\qquad n\in\mathbb Z.
$$

A loop around the origin sends

$$
n\mapsto n+1.
$$

The Riemann-surface viewpoint is often cleaner than cutting the plane by hand. A branch cut is like choosing where to place a seam on a coat. The coat is the same coat if you move the seam, provided you sew it correctly.

## Physical and unphysical sheets

In scattering theory, the **physical sheet** is the sheet reached from the physical region with the prescribed $i0$ boundary value. For a two-particle channel with invariant $s$, the physical amplitude is usually the boundary value

$$
\mathcal A_{\mathrm{phys}}(s)=\mathcal A(s+i0),
\qquad s>s_0.
$$

Crossing the unitarity cut takes the amplitude to an adjacent, often called **second**, sheet. Stable bound states appear as poles on the physical sheet below threshold. Resonances typically appear as poles on an unphysical sheet near the physical region.

A useful toy model is a denominator depending on threshold momentum:

$$
D(s)=E(s)-E_0+ig^2 k(s),
\qquad
k(s)=\sqrt{s-s_0}.
$$

Crossing the cut sends $k\mapsto-k$. Therefore the analytic equation for poles changes from

$$
E(s)-E_0+ig^2 k(s)=0
$$

on one sheet to

$$
E(s)-E_0-ig^2 k(s)=0
$$

on the adjacent sheet. This sign flip is why the sheet matters. The same complex number $s$ is not enough data; you must also specify which branch of $k(s)$ is being used.

This language is central for unstable particles, resonances, hadron spectroscopy, finite-volume scattering, and analytic S-matrix methods. It is also a healthy antidote to the phrase “the pole moved off the real axis” when the sheet is left unspecified. Off which real axis? On which sheet? Complex analysis is annoyingly literal, and it is right to be.

## Monodromy

The **monodromy** of a multivalued function is how its value changes after analytic continuation around a closed loop. For the logarithm around the origin,

$$
\operatorname{Log}z\mapsto\operatorname{Log}z+2\pi i.
$$

For the square root,

$$
\sqrt z\mapsto-\sqrt z.
$$

For powers,

$$
z^\alpha=e^{\alpha\Log z},
$$

a loop around the origin gives

$$
z^\alpha\mapsto e^{2\pi i\alpha}z^\alpha.
$$

If $\alpha$ is an integer, the monodromy is trivial. If $\alpha$ is rational, only finitely many sheets are needed. If $\alpha$ is irrational, infinitely many sheets are needed.

In CFT, monodromy is especially visible. When one local operator moves around another in the complex plane, correlation functions can acquire phases, mix conformal blocks, or move between branches. In scattering amplitudes, monodromy around thresholds tracks which singularity channel has been crossed.

## Moving cuts without changing physics

The cut of $\operatorname{Log}z$ can be placed along any ray from the origin to infinity. The cut of $\sqrt{z-a}$ can be any curve beginning at $a$ and ending at another branch point or infinity. The freedom to move cuts is useful, but it has a catch: while the cut is movable, the boundary values relative to the physical region are not arbitrary.

Suppose an amplitude is specified by a Feynman prescription. Then the statement

$$
\mathcal A(s)=\log(-s-i0)
$$

contains more information than “there is a logarithm.” It says which side of the logarithmic cut is used when $s>0$. Moving the cut in a drawing must preserve that boundary value. Otherwise one has silently changed the physical function.

A safe workflow is:

1. Identify branch points.
2. Choose cuts that do not cross the region where the answer will be evaluated.
3. Define the branch by specifying one value in a reference region.
4. Track continuations by path, not by wishful simplification.
5. Compute discontinuities using explicit boundary values.

The third step is crucial. A formula like $\sqrt{s-s_0}$ is ambiguous until one says what it means just above or below the cut.

## Worked example: a logarithmic discontinuity

Let

$$
F(s)=\operatorname{Log}\left(\frac{-s}{\mu^2}\right),
$$

where $\operatorname{Log}$ is the principal logarithm. For $s>0$,

$$
F(s+i0)=\operatorname{Log}\left(\frac{-s-i0}{\mu^2}\right)
=\log\frac{s}{\mu^2}-i\pi,
$$

and

$$
F(s-i0)=\operatorname{Log}\left(\frac{-s+i0}{\mu^2}\right)
=\log\frac{s}{\mu^2}+i\pi.
$$

Thus

$$
\operatorname{Disc}F(s)=-2\pi i,
\qquad s>0.
$$

This is the sign convention that often appears in amplitudes written with the Feynman boundary value $-s-i0$. If your source uses $\operatorname{Disc}F=F(s-i0)-F(s+i0)$, it will report $+2\pi i$. Both are fine if stated.

## Worked example: a square-root threshold

Let

$$
k(s)=\sqrt{s-s_0}
$$

with a cut along $[s_0,\infty)$ and branch chosen by

$$
k(s+i0)=+\sqrt{s-s_0},
\qquad s>s_0.
$$

Then on the lower edge of the same cut,

$$
k(s-i0)=-\sqrt{s-s_0}.
$$

Therefore

$$
\operatorname{Disc}k(s)=2\sqrt{s-s_0}.
$$

The branch point at $s=s_0$ is not a pole. A contour circling $s_0$ does not pick up a residue; it changes sheet. This distinction is the beginning of threshold analysis.

## Common pitfalls

**Confusing the cut with the branch point.** The branch point is an obstruction to single-valued continuation. The cut is a choice of seam. Moving the seam does not remove the obstruction.

**Writing $\sqrt{x^2}=x$ without a domain.** As real functions, $\sqrt{x^2}=|x|$. As complex functions, $\sqrt{z^2}$ depends on a branch and is not globally equal to $z$.

**Forgetting which variable carries the discontinuity.** The discontinuity of $\operatorname{Log}z$ across the negative $z$-axis and the discontinuity of $\operatorname{Log}(-s)$ across positive $s$ have opposite signs under the convention used here.

**Treating cuts as lines of poles.** This can be a useful approximation, for example in finite volume or Padé approximants, but a genuine branch cut is not an isolated singularity.

**Calling a resonance pole physical without specifying the sheet.** Resonance poles are usually on unphysical sheets. Their nearness to the physical sheet controls their observable effect.

**Assuming a branch choice is harmless inside algebra.** Identities like $\log(ab)=\log a+\log b$ and $\sqrt{ab}=\sqrt a\sqrt b$ are not globally valid for chosen branches. Use them only with domains under control.

**Ignoring endpoint behavior.** A branch point at the endpoint of a cut can dominate asymptotics. Threshold expansions, late-time tails, and discontinuity integrals are sensitive to endpoint powers.

## Exercises

### Exercise 1: Monodromy of a fractional power

Let

$$
f(z)=z^\alpha=e^{\alpha\Log z}
$$

locally near $z=1$. Analytically continue $f$ once counterclockwise around the origin. What happens for integer, rational, and irrational $\alpha$?

<details><summary><strong>Solution</strong></summary>

A loop around the origin sends

$$
\Log z\mapsto \Log z+2\pi i.
$$

Therefore

$$
z^\alpha\mapsto e^{\alpha(\Log z+2\pi i)}=e^{2\pi i\alpha}z^\alpha.
$$

If $\alpha\in\mathbb Z$, this factor is $1$, so the monodromy is trivial. If $\alpha=p/q$ in lowest terms, then after $q$ loops the factor is $e^{2\pi i p}=1$, so there are $q$ sheets. If $\alpha$ is irrational, the factors $e^{2\pi i n\alpha}$ never repeat, so infinitely many sheets are needed.

</details>

### Exercise 2: Discontinuity of the principal logarithm

Using the principal logarithm with $-\pi<\operatorname{Arg}z<\pi$, compute

$$
\operatorname{Disc}\operatorname{Log}z
$$

across the negative real axis.

<details><summary><strong>Solution</strong></summary>

For $a>0$, the two boundary values at $z=-a$ are

$$
\operatorname{Log}(-a+i0)=\log a+i\pi,
$$

and

$$
\operatorname{Log}(-a-i0)=\log a-i\pi.
$$

Therefore, with $\operatorname{Disc}F=F_+-F_-$,

$$
\operatorname{Disc}\operatorname{Log}(-a)=2\pi i.
$$

</details>

### Exercise 3: The square-root sheet change

Let $k(s)=\sqrt{s-s_0}$ with a cut along $[s_0,\infty)$ and the branch fixed by $k(s+i0)>0$ for $s>s_0$. Show that crossing the cut sends $k\mapsto-k$.

<details><summary><strong>Solution</strong></summary>

Near the cut, write $s-s_0=re^{i\theta}$. Above the cut, $\theta=0^+$ and

$$
k(s+i0)=\sqrt r.
$$

Continuing around the branch point to the lower edge gives $\theta=2\pi^-$ on the same analytic continuation, so

$$
k(s-i0)=\sqrt r\,e^{i\pi}=-\sqrt r.
$$

Thus crossing from the chosen physical edge to the adjacent sheet changes the sign of $k$.

</details>

### Exercise 4: Why the logarithm cannot be globally single-valued

Show that there is no single-valued holomorphic function $L$ on $\mathbb C^\times$ satisfying $L'(z)=1/z$.

<details><summary><strong>Solution</strong></summary>

If such an $L$ existed, then the integral of its derivative around any closed contour would vanish:

$$
\oint_C dz\,L'(z)=0.
$$

But for the unit circle $C: z=e^{i\theta}$,

$$
\oint_C\frac{dz}{z}=\int_0^{2\pi} i\,d\theta=2\pi i.
$$

This contradiction shows that no global single-valued holomorphic logarithm exists on $\mathbb C^\times$.

</details>

## References

- L. Ahlfors, *Complex Analysis*. Standard reference for branches, logarithms, conformal maps, and Riemann surfaces.
- E. Stein and R. Shakarchi, *Complex Analysis*. Clear introduction to analytic continuation, branch cuts, and contour methods.
- J. B. Conway, *Functions of One Complex Variable*. Useful for a careful mathematical treatment of branches and monodromy.
- E. T. Whittaker and G. N. Watson, *A Course of Modern Analysis*. Classic source for multivalued functions and special-function continuation.
- R. Eden, P. Landshoff, D. Olive, and J. Polkinghorne, *The Analytic S-Matrix*. Classic treatment of branch cuts, thresholds, and sheet structure in scattering.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Useful for analytic structure, spectral representations, and scattering foundations.
- M. Srednicki, *Quantum Field Theory*. Useful for propagator prescriptions, cuts, and practical perturbative examples.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for loop-integral branch cuts, discontinuities, and physical thresholds.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Useful for analytic continuation, cuts, critical behavior, and asymptotic analysis.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*. Useful for branch cuts, monodromy, and Riemann-surface language in two-dimensional CFT.

## Version history

- **2026-06-26:** Initial polished draft. Added branch cuts, branch points, monodromy, logarithmic and square-root discontinuities, QFT thresholds, physical and second sheets, exercises with solutions, and TikZ/SVG figure.
