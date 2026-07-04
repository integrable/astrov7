---
title: "Cutoffs"
description: "Explains ultraviolet and infrared cutoffs, hard and smooth regulators, lattice and proper-time cutoffs, Wilsonian effective actions, cutoff dependence, counterterms, power divergences, logarithms, and regulator artifacts."
sidebar:
  label: "Cutoffs"
  order: 3
level: Graduate
status: "Polished draft"
source: "Standard references on Wilsonian renormalization, QFT regularization, EFT, lattice field theory, and perturbative renormalization, including Wilson–Kogut, Weinberg, Srednicki, Schwartz, Zee, Zinn-Justin, Burgess, Polyakov, Coleman, Peskin–Schroeder, and lattice field theory references."
topics:
  - cutoff
  - ultraviolet regulator
  - infrared regulator
  - Wilsonian effective action
  - hard cutoff
  - smooth cutoff
  - lattice cutoff
  - proper-time cutoff
  - counterterms
  - power divergences
canonicalTopics:
  - cutoff
  - ultraviolet-regulator
  - infrared-regulator
  - wilsonian-effective-action
  - hard-cutoff
  - smooth-cutoff
  - lattice-cutoff
  - proper-time-cutoff
  - counterterm
  - power-divergence
researchStatus:
  established:
    - "Cutoffs are standard regulators and Wilsonian resolution scales; physical predictions require regulator dependence to cancel against counterterms, matching data, or cutoff effects."
    - "Different cutoff schemes can preserve or break different symmetries, and power divergences are generally more scheme-dependent than logarithmic running of marginal couplings."
  active:
    - "Constructing regulators that preserve locality, gauge symmetry, supersymmetry, chiral symmetry, boundaries, defects, real-time structure, or numerical efficiency remains technically important across QFT."
---

## Summary

A cutoff is a promise not to ask a theory questions at arbitrarily short or long distances. As a **regulator**, it makes divergent expressions finite. As a **Wilsonian scale**, it says which degrees of freedom are still being resolved. Those two roles are related but not identical, and mixing them up is a reliable way to make renormalization feel more mysterious than it is.

A UV cutoff $\Lambda$ suppresses or removes modes with momenta larger than $\Lambda$. In a continuum Euclidean scalar theory, a hard cutoff might mean

$$
\lvert k\rvert<\Lambda.
$$

A smooth cutoff might replace this sharp rule by a damping function $R(k^2/\Lambda^2)$. A lattice cutoff replaces continuum space by spacing $a$, with maximum resolvable momentum of order

$$
\Lambda\sim {\pi\over a}.
$$

In a Wilsonian effective action, lowering the cutoff means integrating out modes between two resolutions:

$$
e^{-S_{\Lambda'}[\phi_<]}
=
\int_{\Lambda'<\lvert k\rvert<\Lambda}\mathcal D\phi_>\,e^{-S_{\Lambda}[\phi_<+\phi_>]},
\qquad
\Lambda'<\Lambda.
$$

The result is a new action with new local coefficients. Observables should not depend on the arbitrary cutoff after the parameters have been matched or renormalized, up to controlled truncation errors.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Flow diagram showing a bare action, mode split at a cutoff, integration of high modes, Wilsonian effective action, observables, regulator choices, and counterterms.](/figures/math-toolkit/cutoff-wilsonian-flow.svg)

<figcaption>

A cutoff can be implemented as a hard momentum restriction, smooth damping function, lattice spacing, proper-time lower bound, or other regulator. In Wilsonian language, changing the cutoff changes the effective action, while matched physical observables stay fixed.

</figcaption>
</figure>

This page explains what cutoffs are, how they differ from renormalization scales, how hard, smooth, lattice, and proper-time cutoffs work, what power and logarithmic divergences mean, and why a regulator is never innocent about symmetries.

## Prerequisites and conventions

You should know Fourier transforms, loop integrals, Gaussian path integrals, and basic dimensional analysis. Useful nearby pages are [Dimensional Analysis](/math-toolkit/asymptotics-regularization-resurgence/dimensional-analysis/), [Asymptotic Series](/math-toolkit/asymptotics-regularization-resurgence/asymptotic-series/), [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/), [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/), [Heat Equation and Heat Kernel](/math-toolkit/differential-equations-green-functions/heat-equation-and-heat-kernel/), and [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/).

Unless stated otherwise, loop-integral examples are Euclidean and use mass dimension $[k]=1$. The cutoff is denoted by $\Lambda$. A renormalization scale is denoted by $\mu$. They may be related in a calculation, but conceptually they are different.

:::note[Cutoff versus renormalization scale]
A cutoff $\Lambda$ is a regulator or resolution limit. A renormalization scale $\mu$ is a reference scale used to define renormalized parameters. A calculation may contain both. Do not silently identify them unless the setup explicitly does so.
:::

## Why cutoffs appear

Many QFT expressions ask for contributions from infinitely many modes. For a field expanded in Fourier modes,

$$
\phi(x)=\int {d^d k\over(2\pi)^d}\,e^{-ik\cdot x}\tilde\phi(k),
$$

a continuum path integral formally integrates over all $\tilde\phi(k)$, including modes with arbitrarily large $|k|$. Interactions then produce loop integrals such as

$$
\int {d^d k\over(2\pi)^d}{1\over k^2+m^2}.
$$

At large $k$, this behaves like

$$
\int d^d k\,{1\over k^2},
$$

which diverges for $d\ge2$ in the ultraviolet.

A UV cutoff makes the expression finite, for example by replacing it with

$$
\int_{\lvert k\rvert<\Lambda}{d^d k\over(2\pi)^d}{1\over k^2+m^2}.
$$

The cutoff is not the final answer. It is a controlled way to expose how the expression depends on short-distance physics. Renormalization then says which cutoff dependence is absorbed into local parameters and which parts are meaningful predictions.

## Hard momentum cutoffs

The simplest cutoff is a hard momentum cutoff:

$$
\int {d^d k\over(2\pi)^d}\,f(k)
\quad\longrightarrow\quad
\int_{\lvert k\rvert<\Lambda}{d^d k\over(2\pi)^d}\,f(k).
$$

In Euclidean signature, this can preserve rotational symmetry $SO(d)$ if the cutoff is a sphere. In Lorentzian signature, a naive condition on $|\mathbf k|$ or $k^2$ can break Lorentz invariance or create contour problems. In gauge theories, a hard momentum cutoff can also break gauge invariance because momentum restrictions do not automatically respect Ward identities.

That does not make hard cutoffs useless. They are excellent for intuition and many Wilsonian estimates. They make power-law sensitivity visible. They are also common in condensed matter, where a microscopic lattice or bandwidth really does provide a physical short-distance scale. But if a calculation depends on gauge cancellations, chiral symmetry, supersymmetry, or delicate analytic continuation, a hard cutoff may create artifacts that must be repaired or avoided.

## Smooth cutoffs

A smooth cutoff replaces the sharp domain $\lvert k\rvert<\Lambda$ by a damping function. For example,

$$
\int {d^d k\over(2\pi)^d}\,f(k)
\quad\longrightarrow\quad
\int {d^d k\over(2\pi)^d}\,R\!\left({k^2\over\Lambda^2}\right)f(k),
$$

where

$$
R(0)=1,
\qquad
R(z)\to0\quad\text{rapidly as }z\to\infty.
$$

A common choice for intuition is

$$
R(z)=e^{-z}.
$$

Smooth cutoffs avoid the sharp boundary artifacts of hard cutoffs. They are also natural in exact renormalization-group equations, where one introduces a cutoff profile and studies how the action changes as the profile scale changes.

But smooth cutoffs are still schemes. Different choices of $R$ change nonuniversal finite parts and power-divergent pieces. Universal quantities must not depend on the arbitrary shape of $R$ after matching and renormalization.

## Lattice cutoffs

A lattice with spacing $a$ provides a physical and nonperturbative UV cutoff. In one dimension, momenta are restricted to a Brillouin zone such as

$$
-\frac{\pi}{a}<k\le\frac{\pi}{a}.
$$

In $d$ dimensions on a hypercubic lattice, each component lies in a similar interval. The cutoff is therefore of order

$$
\Lambda\sim {\pi\over a}.
$$

The lattice changes derivatives into finite differences. For a scalar field, one replaces schematically

$$
\partial_\mu\phi(x)
\quad\longrightarrow\quad
{\phi(x+a\hat\mu)-\phi(x)\over a}.
$$

As $a\to0$, the continuum theory is recovered only if the bare parameters are tuned appropriately. This tuning is not optional housekeeping; it is the continuum limit.

The lattice has a huge virtue: gauge invariance can be preserved exactly by putting group-valued variables on links. It also has costs: continuous rotations and Lorentz symmetry are broken at finite $a$, chiral fermions require special care, and continuum behavior appears only after extrapolation.

Cutoff artifacts often have an expansion in powers of $a$:

$$
\mathcal O(a)=\mathcal O_{\text{continuum}}+c_1a\mathcal O_1+c_2a^2\mathcal O_2+\cdots,
$$

with the allowed corrections controlled by symmetry. Improving a lattice action means canceling leading artifacts by adding higher-dimension operators. That is EFT logic in computational clothing.

## Proper-time and heat-kernel cutoffs

For a positive operator $A$, one may represent determinants or inverse operators using proper time:

$$
\log\det A=-\int_0^\infty {ds\over s}\,\operatorname{Tr}\,e^{-sA}
$$

up to convention-dependent constants and zero-mode subtleties. UV divergences come from the small-$s$ region, because small proper time probes short distances and high eigenvalues. A proper-time cutoff imposes

$$
s>{1\over\Lambda^2}.
$$

Then

$$
\log\det A\big|_{\Lambda}
=-\int_{1/\Lambda^2}^\infty {ds\over s}\,\operatorname{Tr}\,e^{-sA}.
$$

This is closely tied to heat-kernel methods. If

$$
\operatorname{Tr}\,e^{-sA}\sim {1\over(4\pi s)^{d/2}}\sum_{n=0}^\infty a_n s^n,
\qquad s\to0^+,
$$

then the cutoff dependence is read off term by term from powers of $s$. Local heat-kernel coefficients produce local counterterms.

Proper-time cutoffs are geometrically transparent and excellent for background-field calculations, but they are still regulators. They can obscure real-time analytic structure and may not preserve every symmetry automatically.

## UV and IR cutoffs

A UV cutoff removes short-distance or high-momentum sensitivity:

$$
\lvert k\rvert<\Lambda.
$$

An IR cutoff removes long-distance or low-momentum sensitivity. Examples include a finite box of size $L$, a small mass $m$, an external momentum $p$, a temperature $T$, or an explicit lower momentum cutoff

$$
\lvert k\rvert>\lambda_{\text{IR}}.
$$

The two should not be confused. In a massless theory, an integral can be both UV and IR divergent. For example,

$$
\int {d^4k\over(2\pi)^4}{1\over k^4}
$$

has logarithmic behavior both at large $k$ and at small $k$. A UV cutoff alone does not fix the small-$k$ problem. An IR regulator alone does not fix the large-$k$ problem.

Dimensional regularization can hide this distinction because UV and IR poles may both look like $1/\epsilon$. One must identify which momentum region produced the pole. The notation does not save you; the analysis does.

## A concrete scalar integral

Consider the Euclidean integral

$$
I_1(\Lambda,m)=\int_{\lvert k\rvert<\Lambda}{d^4k\over(2\pi)^4}{1\over k^2+m^2}.
$$

Using the area of the unit three-sphere, $2\pi^2$, gives

$$
I_1(\Lambda,m)
={1\over 8\pi^2}\int_0^\Lambda dk\,{k^3\over k^2+m^2}.
$$

The radial integral is

$$
\int_0^\Lambda dk\,{k^3\over k^2+m^2}
={1\over2}\left[\Lambda^2-m^2\log\left(1+{\Lambda^2\over m^2}\right)\right].
$$

Therefore

$$
I_1(\Lambda,m)
={1\over16\pi^2}\left[\Lambda^2-m^2\log\left(1+{\Lambda^2\over m^2}\right)\right].
$$

For large $\Lambda$,

$$
I_1(\Lambda,m)
={\Lambda^2\over16\pi^2}
-{m^2\over16\pi^2}\log{\Lambda^2\over m^2}
+O\!\left({m^4\over\Lambda^2}\right).
$$

The quadratic term is a local power divergence. The logarithm signals scale dependence tied to a dimension-four structure after multiplying by appropriate couplings. Which pieces are physical depends on the observable and renormalization condition.

A related integral is

$$
I_2(\Lambda,m)=\int_{\lvert k\rvert<\Lambda}{d^4k\over(2\pi)^4}{1\over(k^2+m^2)^2}.
$$

The same calculation gives

$$
I_2(\Lambda,m)
={1\over16\pi^2}\left[
\log\left(1+{\Lambda^2\over m^2}\right)
-{\Lambda^2\over\Lambda^2+m^2}
\right].
$$

For large $\Lambda$,

$$
I_2(\Lambda,m)
={1\over16\pi^2}\left[
\log{\Lambda^2\over m^2}-1+O\!\left({m^2\over\Lambda^2}\right)
\right].
$$

This one is logarithmically divergent. Logarithms are the natural habitat of renormalization-group equations.

## Cutoff dependence and counterterms

Suppose a regulated calculation gives a two-point function depending on a bare mass $m_0^2$ and cutoff $\Lambda$:

$$
\Gamma^{(2)}(p;\Lambda)=p^2+m_0^2+\Sigma(p;\Lambda).
$$

A renormalization condition might define the physical mass $m_R$ by

$$
\Gamma^{(2)}(p=0;\Lambda)=m_R^2.
$$

Then

$$
m_0^2(\Lambda)=m_R^2-\Sigma(0;\Lambda).
$$

The bare parameter depends on the cutoff so that the measured quantity stays fixed. This is not cheating. It is the definition of the continuum theory in terms of physical inputs.

For a coupling,

$$
\lambda_0(\Lambda)=\lambda_R(\mu)+\delta\lambda(\Lambda,\mu),
$$

where $\mu$ labels the renormalization convention. The cutoff dependence of $\delta\lambda$ cancels the cutoff dependence of loop integrals. The remaining $\mu$ dependence is compensated by the running of $\lambda_R(\mu)$ in physical predictions.

The slogan is:

$$
\text{bare quantities absorb cutoff dependence; observables do not care about arbitrary regulators.}
$$

A better slogan is: observables do not care **after you have included every counterterm required by the symmetries and your desired accuracy**. Leaving out allowed terms and then complaining about cutoff dependence is like leaving your umbrella at home and blaming the rain.

## Wilsonian effective actions

The Wilsonian viewpoint treats the cutoff as a moving resolution scale. Start with an action $S_{\Lambda_0}$ defined at a high cutoff $\Lambda_0$. Split the field into low and high modes relative to a lower scale $\Lambda$:

$$
\phi=\phi_<+\phi_>,
\qquad
\phi_<: \lvert k\rvert<\Lambda,
\qquad
\phi_>: \Lambda<\lvert k\rvert<\Lambda_0.
$$

Define the Wilsonian action $S_\Lambda$ by

$$
e^{-S_\Lambda[\phi_<]}
=
\int_{\Lambda<\lvert k\rvert<\Lambda_0}\mathcal D\phi_>\,e^{-S_{\Lambda_0}[\phi_<+\phi_>]}
$$

in Euclidean notation. The lower-resolution action $S_\Lambda$ contains every local operator allowed by symmetries:

$$
S_\Lambda=\sum_i g_i(\Lambda)\int d^d x\,\mathcal O_i(x).
$$

Changing $\Lambda$ changes the coefficients $g_i(\Lambda)$. This is not an error; it is the renormalization group.

Dimensionless Wilsonian couplings are often written

$$
\tilde g_i(\Lambda)=g_i(\Lambda)\Lambda^{\Delta_i-d}.
$$

Their tree-level flow is

$$
\Lambda{d\tilde g_i\over d\Lambda}=(\Delta_i-d)\tilde g_i+\text{loop and mixing terms}.
$$

Relevant couplings grow as the cutoff is lowered. Irrelevant couplings shrink. Marginal couplings need loop information.

## Power divergences and logarithms

With a cutoff, divergences often appear as powers and logarithms:

$$
A(\Lambda)=c_4\Lambda^4+c_2m^2\Lambda^2+c_{\log}m^4\log{\Lambda\over\mu}+A_{\text{finite}}+O(\Lambda^{-1}).
$$

Power divergences usually multiply local operators of lower dimension. Their numerical coefficients are strongly regulator-dependent. Change a hard cutoff to a smooth cutoff and the coefficient of $\Lambda^2$ generally changes.

Logarithmic divergences are special because they signal dependence on ratios of scales. The leading coefficients of logarithms associated with marginal couplings are often universal within a class of schemes, especially at low loop order, though the precise statement depends on what is being compared.

The safe hierarchy is:

- cutoff powers diagnose sensitivity to local terms;
- logarithms diagnose scale dependence;
- finite constants are scheme-dependent unless tied to an observable;
- nonlocal dependence on external momenta is harder to fake and often carries direct physical content.

In particular, a term like

$$
p^2\log{p^2\over\mu^2}
$$

cannot be canceled by a purely local counterterm polynomial in $p^2$. A term like $c_0+c_1p^2+c_2p^4$ can be shifted by local counterterms.

## Regulator artifacts and symmetries

A regulator may break symmetries even when the original formal theory has them. Examples:

| Regulator | Possible virtue | Possible artifact |
|---|---|---|
| hard Euclidean momentum cutoff | transparent power counting | may break gauge invariance or shift Ward identities |
| spatial momentum cutoff | useful in Hamiltonian settings | breaks Lorentz invariance |
| lattice cutoff | nonperturbative, can preserve gauge invariance | breaks continuous rotations and translations at finite spacing |
| Pauli–Villars | preserves many perturbative structures | heavy regulator fields must be chosen carefully |
| dimensional regularization | preserves gauge and Lorentz symmetry in many perturbative calculations | hides power divergences and can complicate chiral objects |
| proper-time cutoff | geometric and heat-kernel friendly | scheme-dependent and not always symmetry-preserving |

If the regulator breaks a symmetry that should be present in the continuum theory, one must restore the symmetry by counterterms, improved definitions, or a different regulator. If the symmetry is anomalous, no regulator preserves all desired symmetries simultaneously. In that case the failure is physical, not just a bad choice of cutoff.

## Physical cutoffs versus auxiliary cutoffs

Some cutoffs are physical. A crystal has a lattice spacing. A material has a bandwidth. An EFT has a heavy threshold beyond which new degrees of freedom appear. A detector has finite resolution. In these cases, the cutoff represents real physics.

Other cutoffs are auxiliary. A continuum relativistic QFT may be defined by a limiting procedure in which $\Lambda\to\infty$ while renormalized observables are held fixed. In that case, $\Lambda$ is not a measured particle mass or physical threshold; it is a regulator used to define the theory.

The difference matters. If $\Lambda$ is physical, operators suppressed by $\Lambda$ encode real short-distance structure. If $\Lambda$ is auxiliary, physical predictions must be independent of it after renormalization.

In EFT, both viewpoints coexist. A regulator cutoff may be arbitrary, while the EFT breakdown scale $\Lambda_*$ is physical. One should not blindly set

$$
\Lambda=\Lambda_*.
$$

Sometimes it is convenient. Sometimes it muddies the water. The regulator is a tool; the breakdown scale is a fact about the theory's domain of validity.

## Cutoffs and locality

Why do counterterms look local? Because high-momentum modes are short-distance modes. When external momenta are small compared with a cutoff or heavy scale, high-energy effects can be expanded in powers of external momenta:

$$
{1\over M^2+p^2}
={1\over M^2}-{p^2\over M^4}+{p^4\over M^6}-\cdots,
\qquad
\lvert p^2\rvert\ll M^2.
$$

In position space, powers of $p$ become derivatives. Thus short-distance physics produces local operators:

$$
\mathcal O,
\qquad
\partial^2\mathcal O,
\qquad
\partial^4\mathcal O,
\qquad\ldots
$$

This locality argument is the engine behind EFT and Wilsonian renormalization. It can fail or require refinement when there are massless particles, thresholds, long-range forces, nonlocal defects, or IR singularities. Then the low-energy action must keep the relevant light degrees of freedom rather than integrating them out.

## Common pitfalls

**Thinking the cutoff is always physical.** Sometimes it is; sometimes it is just scaffolding. Ask whether the calculation takes $\Lambda\to\infty$, keeps $a$ finite, or identifies a real breakdown scale $\Lambda_*$.

**Confusing UV and IR regulators.** A small mass used to tame soft divergences is not the same as a UV cutoff. A pole in a regulator may come from either end of an integral.

**Expecting every regulator to preserve every symmetry.** Most do not. Choose a regulator compatible with the symmetry you need, or add counterterms that restore it in the continuum limit.

**Overinterpreting power divergences.** The coefficient of a quadratic divergence can change with regulator. The sensitivity to a relevant local operator is meaningful; the raw coefficient is usually scheme-dependent.

**Underinterpreting logarithms.** Logs are not just ugly leftovers. They record scale dependence and lead to renormalization-group equations.

**Dropping cutoff-dependent terms without a renormalization condition.** A subtraction is a definition. State what parameter or observable is being held fixed.

**Using a cutoff outside its domain.** A Euclidean cutoff formula cannot always be moved into real time without thinking about contours, causality, and analytic continuation.

## Exercises

### Exercise 1: Hard cutoff tadpole

Compute

$$
I_1(\Lambda,m)=\int_{\lvert k\rvert<\Lambda}{d^4k\over(2\pi)^4}{1\over k^2+m^2}
$$

and extract the leading large-$\Lambda$ terms.

<details><summary><strong>Solution</strong></summary>

In four Euclidean dimensions,

$$
d^4k=2\pi^2 k^3dk.
$$

Therefore

$$
I_1(\Lambda,m)=\frac{2\pi^2}{(2\pi)^4}\int_0^\Lambda dk\,{k^3\over k^2+m^2}
={1\over8\pi^2}\int_0^\Lambda dk\,{k^3\over k^2+m^2}.
$$

Now

$$
\frac{k^3}{k^2+m^2}=k-{m^2k\over k^2+m^2},
$$

so

$$
\int_0^\Lambda dk\,{k^3\over k^2+m^2}
={\Lambda^2\over2}-{m^2\over2}\log\left(1+{\Lambda^2\over m^2}\right).
$$

Thus

$$
I_1(\Lambda,m)
={1\over16\pi^2}\left[\Lambda^2-m^2\log\left(1+{\Lambda^2\over m^2}\right)\right].
$$

For large $\Lambda$,

$$
I_1(\Lambda,m)
={\Lambda^2\over16\pi^2}-{m^2\over16\pi^2}\log{\Lambda^2\over m^2}+O\!\left({m^4\over\Lambda^2}\right).
$$

</details>

### Exercise 2: Logarithmic integral

Show that

$$
I_2(\Lambda,m)=\int_{\lvert k\rvert<\Lambda}{d^4k\over(2\pi)^4}{1\over(k^2+m^2)^2}
$$

has a logarithmic divergence.

<details><summary><strong>Solution</strong></summary>

Again using $d^4k=2\pi^2k^3dk$,

$$
I_2(\Lambda,m)={1\over8\pi^2}\int_0^\Lambda dk\,{k^3\over(k^2+m^2)^2}.
$$

Set $u=k^2+m^2$, so $du=2kdk$ and $k^2=u-m^2$. Then

$$
\int_0^\Lambda dk\,{k^3\over(k^2+m^2)^2}
={1\over2}\int_{m^2}^{\Lambda^2+m^2}du\,{u-m^2\over u^2}.
$$

This equals

$$
{1\over2}\left[\log u+{m^2\over u}\right]_{m^2}^{\Lambda^2+m^2}
={1\over2}\left[
\log\left(1+{\Lambda^2\over m^2}\right)
-{\Lambda^2\over\Lambda^2+m^2}
\right].
$$

Therefore

$$
I_2(\Lambda,m)
={1\over16\pi^2}\left[
\log\left(1+{\Lambda^2\over m^2}\right)
-{\Lambda^2\over\Lambda^2+m^2}
\right].
$$

For large $\Lambda$,

$$
I_2(\Lambda,m)
={1\over16\pi^2}\log{\Lambda^2\over m^2}+O(1),
$$

so the divergence is logarithmic.

</details>

### Exercise 3: Smooth cutoff dependence

Let

$$
I_R(\Lambda)=\int {d^4k\over(2\pi)^4}\,{R(k^2/\Lambda^2)\over k^2+m^2},
$$

where $R(z)$ decays rapidly as $z\to\infty$ and $R(0)=1$. Use dimensional analysis to show the leading divergence is proportional to $\Lambda^2$.

<details><summary><strong>Solution</strong></summary>

Rescale $k=\Lambda q$. Then

$$
I_R(\Lambda)=\Lambda^4\int {d^4q\over(2\pi)^4}\,{R(q^2)\over \Lambda^2q^2+m^2}.
$$

Factor $\Lambda^2$ out of the denominator:

$$
I_R(\Lambda)=\Lambda^2\int {d^4q\over(2\pi)^4}\,{R(q^2)\over q^2+m^2/\Lambda^2}.
$$

As $\Lambda\to\infty$, the integral tends to a regulator-dependent dimensionless constant if the small-$q$ region is controlled by nonzero $m$. Hence

$$
I_R(\Lambda)\sim C_R\Lambda^2+\cdots,
$$

where $C_R$ depends on the cutoff profile $R$.

</details>

### Exercise 4: Lattice cutoff scale

A one-dimensional lattice has spacing $a$ and $N$ sites with periodic boundary conditions. Allowed momenta are

$$
k_n={2\pi n\over Na}.
$$

What is the natural UV momentum scale?

<details><summary><strong>Solution</strong></summary>

Because momenta differing by reciprocal lattice vectors are equivalent, the first Brillouin zone can be chosen as

$$
-\frac{\pi}{a}<k\le\frac{\pi}{a}.
$$

Thus the largest independent momentum is of order

$$
\Lambda\sim {\pi\over a}.
$$

The precise numerical factor depends on the convention for defining the cutoff, but the scale is $a^{-1}$.

</details>

### Exercise 5: Local expansion from a heavy propagator

Show that for $\lvert p^2\rvert\ll M^2$,

$$
{1\over M^2+p^2}
$$

has a local derivative expansion.

<details><summary><strong>Solution</strong></summary>

Factor out $M^2$:

$$
{1\over M^2+p^2}={1\over M^2}{1\over 1+p^2/M^2}.
$$

For $|p^2|<M^2$, expand the geometric series:

$$
{1\over 1+p^2/M^2}=1-{p^2\over M^2}+{p^4\over M^4}-\cdots.
$$

Thus

$$
{1\over M^2+p^2}
={1\over M^2}-{p^2\over M^4}+{p^4\over M^6}-\cdots.
$$

In position space, powers of $p^2$ correspond to derivatives such as $-\partial^2$, so the expansion becomes a series of local higher-derivative operators.

</details>

## References and further reading

For Wilsonian cutoffs, renormalization, and the conceptual meaning of integrating out modes, see Wilson and Kogut, "The Renormalization Group and the $\epsilon$ Expansion"; Steven Weinberg, *The Quantum Theory of Fields*, Vols. I and II; Mark Srednicki, *Quantum Field Theory*; Matthew Schwartz, *Quantum Field Theory and the Standard Model*; A. Zee, *Quantum Field Theory in a Nutshell*; Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*; and C. P. Burgess, *Introduction to Effective Field Theory*.

For proper-time and heat-kernel cutoffs, see standard heat-kernel references, QFT treatments of functional determinants, and the pages on heat kernels and zeta regularization in this volume. For lattice cutoffs and continuum limits, see lattice field theory references and condensed-matter field theory texts where the microscopic cutoff is often physical.

## Version history

- 2026-06-26: First polished draft. Added definitions of UV and IR cutoffs, hard and smooth cutoffs, lattice and proper-time cutoffs, scalar cutoff integrals, counterterm logic, Wilsonian effective action, power divergences, logarithms, regulator artifacts, physical versus auxiliary cutoffs, locality, exercises with solutions, and Wilsonian-flow figure.
