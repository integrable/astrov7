---
title: "Dimensional Regularization Identities"
description: "Collects and derives the core dimensional-regularization identities used in QFT: master integrals, Schwinger parameters, Feynman parameters, tensor reduction, gamma-function expansions, scaleless integrals, MS and MS-bar bookkeeping, and common traps."
sidebar:
  label: "Dimensional Regularization Identities"
  order: 4
level: Graduate
status: "Polished draft"
source: "Standard references on perturbative QFT, dimensional regularization, renormalization, and effective field theory, including Wilson–Kogut, Weinberg, Srednicki, Schwartz, Zee, Zinn-Justin, Burgess, Coleman, Peskin–Schroeder, and 't Hooft–Veltman."
topics:
  - dimensional regularization
  - loop integrals
  - gamma functions
  - Feynman parameters
  - Schwinger parameters
  - tensor reduction
  - scaleless integrals
  - minimal subtraction
  - MS-bar scheme
  - ultraviolet divergences
canonicalTopics:
  - dimensional-regularization
  - loop-integral
  - gamma-function-identity
  - feynman-parameter
  - schwinger-parameter
  - tensor-reduction
  - scaleless-integral
  - minimal-subtraction
  - ms-bar-scheme
  - ultraviolet-divergence
researchStatus:
  established:
    - "Dimensional regularization, Feynman-parameter identities, Schwinger-parameter identities, tensor reduction, and minimal-subtraction bookkeeping are standard perturbative QFT tools."
    - "Scaleless integrals vanish in dimensional regularization only after ultraviolet and infrared contributions have been analytically combined."
  active:
    - "Extensions involving chiral fermions, gamma-five, supersymmetry, boundaries, defects, real-time finite-density systems, noninteger-dimensional fixed points, and automated multi-loop reduction remain technically subtle."
---

## Summary

Dimensional regularization is the art of making divergent integrals honest by asking them to live in $d$ dimensions before asking what happens near the physical integer dimension. Instead of cutting off large momenta at $\Lambda$, one replaces

$$
4\longrightarrow d=4-2\epsilon
$$

and regards loop integrals as analytic functions of $d$. Divergences become poles in $\epsilon$, and renormalization becomes the controlled subtraction of local pole terms.

The basic Euclidean identity is

$$
\int \frac{d^d \ell}{(2\pi)^d}\,{1\over (\ell^2+\Delta)^\alpha}
=
{1\over (4\pi)^{d/2}}
{\Gamma(\alpha-d/2)\over \Gamma(\alpha)}
\Delta^{d/2-\alpha},
\qquad
\Delta>0.
$$

Everything else in one-loop dimensional regularization is, morally, a footnote to this formula: combine denominators, shift the loop momentum, reduce tensor numerators by rotational invariance, evaluate the master integral, expand gamma functions, and subtract pole terms.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Flow diagram for dimensional regularization: continue dimension, combine denominators, evaluate gamma-function master integrals, expand poles, and subtract local counterterms.](/figures/math-toolkit/dimensional-regularization-identity-flow.svg)

<figcaption>

Dimensional regularization replaces a divergent four-dimensional integral by a meromorphic function of $d$. The poles in $\epsilon$ expose local UV or IR sensitivity; the finite part becomes meaningful only after a renormalization convention is specified.

</figcaption>
</figure>

This page is a reference and a derivation. It does not try to replace a full renormalization course. Its job is to make the identities used in perturbative pages reproducible, convention-consistent, and difficult to misuse.

## Prerequisites and conventions

You should be comfortable with Gaussian integrals, gamma functions, Fourier integrals, and basic loop-momentum manipulations. Useful nearby pages are [Gamma and Beta Functions](/math-toolkit/special-functions-exact-equations/gamma-and-beta-functions/), [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/), [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), [Dimensional Analysis](/math-toolkit/asymptotics-regularization-resurgence/dimensional-analysis/), [Cutoffs](/math-toolkit/asymptotics-regularization-resurgence/cutoffs/), and [Borel Transform](/math-toolkit/asymptotics-regularization-resurgence/borel-transform/).

The site default metric is mostly-minus,

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
$$

but most identities below are written first in Euclidean signature because the formulas are cleaner. Lorentzian integrals are obtained by the usual $i0$ prescription and Wick rotation. The safest workflow is:

$$
\text{Lorentzian propagators with }i0
\quad\longrightarrow\quad
\text{Wick-rotated Euclidean integral}
\quad\longrightarrow\quad
\text{dimensionally regularized formula}.
$$

For perturbative QFT in four dimensions we write

$$
d=4-2\epsilon.
$$

For critical phenomena or conformal perturbation theory one may instead expand around $d=d_c-\epsilon$, such as $d=4-\epsilon$. The factor of $2$ is convention, not physics. In loop calculations with relativistic four-dimensional QFT, $4-2\epsilon$ is especially common because many gamma-function arguments then become integers plus $\epsilon$.

:::note[What dimensional regularization preserves]
Dimensional regularization preserves translation invariance, Lorentz or Euclidean rotational invariance, and gauge symmetry unusually well. It does not automatically preserve every structure. Chiral algebra, $\gamma^5$, Levi-Civita tensors, supersymmetry, boundaries, and topological terms require extra care.
:::

## Why a scale must be inserted

In $d=4$, a typical coupling such as the Yang–Mills coupling or a $\phi^4$ coupling is dimensionless. In $d=4-2\epsilon$, the same coupling has engineering dimension. To keep the renormalized coupling dimensionless one introduces a reference scale $\mu$.

For example, a bare coupling may be written schematically as

$$
g_0=\mu^\epsilon Z_g(g,\epsilon)g.
$$

For a quartic scalar coupling one often writes

$$
\lambda_0=\mu^{2\epsilon}Z_\lambda(\lambda,\epsilon)\lambda.
$$

The power of $\mu$ is fixed by dimensional analysis. The physical meaning of $\mu$ appears after renormalization: changing $\mu$ while holding bare quantities fixed produces the renormalization group.

A common $\overline{\mathrm{MS}}$ loop measure is

$$
\int_\ell^{\overline{\mathrm{MS}}}
\equiv
\left({e^{\gamma_E}\mu^2\over 4\pi}\right)^\epsilon
\int {d^{4-2\epsilon}\ell\over (2\pi)^{4-2\epsilon}},
$$

where $\gamma_E$ is Euler's constant. This convention absorbs the ubiquitous $\log 4\pi-\gamma_E$ combination into the definition of the scale. Other authors absorb these factors differently. When comparing formulas, check the measure before hunting ghosts in the finite part.

## Schwinger parameters

The cleanest derivation of the master integral uses the Schwinger representation

$$
{1\over A^\alpha}
=
{1\over \Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1}e^{-sA},
\qquad
\operatorname{Re}\alpha>0,
\qquad
\operatorname{Re}A>0.
$$

Apply this to $A=\ell^2+\Delta$:

$$
{1\over (\ell^2+\Delta)^\alpha}
=
{1\over \Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1}e^{-s(\ell^2+\Delta)}.
$$

The Gaussian integral in $d$ Euclidean dimensions is

$$
\int {d^d\ell\over (2\pi)^d}e^{-s\ell^2}
=
{1\over (4\pi s)^{d/2}}.
$$

Therefore

$$
\int {d^d\ell\over (2\pi)^d}{1\over (\ell^2+\Delta)^\alpha}
=
{1\over (4\pi)^{d/2}\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1-d/2}e^{-s\Delta}.
$$

The remaining integral is a gamma function:

$$
\int_0^\infty ds\,s^{\alpha-1-d/2}e^{-s\Delta}
=
\Gamma(\alpha-d/2)\Delta^{d/2-\alpha}.
$$

Thus

$$
\boxed{
\int {d^d \ell\over (2\pi)^d}{1\over (\ell^2+\Delta)^\alpha}
=
{1\over (4\pi)^{d/2}}
{\Gamma(\alpha-d/2)\over \Gamma(\alpha)}
\Delta^{d/2-\alpha}
}.
$$

The formula was derived in the region where the integrals converge. Dimensional regularization then **defines** the answer elsewhere by analytic continuation in $d$ and $\alpha$.

That last sentence is doing real work. The right-hand side is not a cutoff estimate. It is a meromorphic continuation.

## Numerator powers

For scalar numerator powers, the useful identity is

$$
\int {d^d\ell\over(2\pi)^d}\,{(\ell^2)^r\over (\ell^2+\Delta)^\alpha}
=
{1\over (4\pi)^{d/2}}
{\Gamma(r+d/2)\over \Gamma(d/2)}
{\Gamma(\alpha-r-d/2)\over \Gamma(\alpha)}
\Delta^{d/2+r-\alpha},
$$

valid by analytic continuation from the convergent region. For integer $r$, this can also be obtained by writing

$$
\ell^2=(\ell^2+\Delta)-\Delta
$$

repeatedly and reducing to denominator-only integrals.

A particularly common case is

$$
\int {d^d\ell\over(2\pi)^d}\,{\ell^2\over (\ell^2+\Delta)^\alpha}
=
{d\over 2}
{1\over (4\pi)^{d/2}}
{\Gamma(\alpha-1-d/2)\over \Gamma(\alpha)}
\Delta^{d/2+1-\alpha}.
$$

The factor $d/2$ is one of the places where four-dimensional reflexes cause mistakes. In dimensional regularization, $d$ is not secretly $4$ until after the pole structure is handled.

## Tensor reduction

Euclidean rotational invariance gives

$$
\int {d^d\ell\over(2\pi)^d}\,\ell_i\ell_j f(\ell^2)
=
{\delta_{ij}\over d}
\int {d^d\ell\over(2\pi)^d}\,\ell^2 f(\ell^2).
$$

For four indices,

$$
\int {d^d\ell\over(2\pi)^d}\,\ell_i\ell_j\ell_k\ell_l f(\ell^2)
=
{\delta_{ij}\delta_{kl}+\delta_{ik}\delta_{jl}+\delta_{il}\delta_{jk}\over d(d+2)}
\int {d^d\ell\over(2\pi)^d}\,(\ell^2)^2 f(\ell^2).
$$

In Lorentzian notation the corresponding covariant replacements are, schematically,

$$
\int d^d\ell\,\ell_\mu\ell_\nu f(\ell^2)
={\eta_{\mu\nu}\over d}
\int d^d\ell\,\ell^2 f(\ell^2),
$$

with the appropriate contour and $i0$ prescription. In practice, Wick rotate or use known covariant master formulas consistently.

Odd powers vanish after the shift if the integration measure and regulator preserve $\ell\mapsto -\ell$:

$$
\int {d^d\ell\over(2\pi)^d}\,\ell_i f(\ell^2)=0.
$$

This statement is not true for a regulator that breaks translation symmetry or for an integral whose shift is illegal before regularization. Dimensional regularization is popular partly because these shifts are clean.

## Feynman parameters

To combine denominators, use the beta-function identity

$$
{1\over A^\alpha B^\beta}
=
{\Gamma(\alpha+\beta)\over \Gamma(\alpha)\Gamma(\beta)}
\int_0^1 dx\,
{x^{\alpha-1}(1-x)^{\beta-1}\over [xA+(1-x)B]^{\alpha+\beta}},
$$

for positive real $A,B$ and by analytic continuation with $i0$ prescriptions in Minkowski problems.

The $N$-denominator version is

$$
\prod_{i=1}^N {1\over A_i^{\alpha_i}}
=
{\Gamma(\alpha)\over \prod_{i=1}^N\Gamma(\alpha_i)}
\int_0^1\prod_{i=1}^N dx_i\,
\delta\!\left(1-\sum_{i=1}^N x_i\right)
{\prod_{i=1}^N x_i^{\alpha_i-1}\over \left(\sum_{i=1}^N x_i A_i\right)^\alpha},
$$

where

$$
\alpha=\sum_{i=1}^N\alpha_i.
$$

For two ordinary propagator denominators, the most-used special case is

$$
{1\over AB}=\int_0^1 dx\,{1\over [xA+(1-x)B]^2}.
$$

A one-loop two-point integral then follows the pattern

$$
\int {d^d\ell\over(2\pi)^d}
{1\over [\ell^2+m_1^2][(\ell+p)^2+m_2^2]}
=
\int_0^1 dx
\int {d^d k\over(2\pi)^d}
{1\over [k^2+\Delta(x,p^2)]^2},
$$

where the shifted momentum is

$$
k=\ell+(1-x)p
$$

and, in Euclidean signature,

$$
\Delta(x,p^2)=xm_1^2+(1-x)m_2^2+x(1-x)p^2.
$$

Then the master formula gives

$$
\int {d^d k\over(2\pi)^d}{1\over [k^2+\Delta]^2}
=
{1\over(4\pi)^{d/2}}\Gamma(2-d/2)\Delta^{d/2-2}.
$$

For $d=4-2\epsilon$, the factor $\Gamma(\epsilon)$ produces the pole.

## Useful gamma-function expansions

Near $\epsilon=0$,

$$
\Gamma(\epsilon)=
{1\over\epsilon}-\gamma_E+O(\epsilon),
$$

$$
\Gamma(1+\epsilon)=
1-\gamma_E\epsilon+O(\epsilon^2),
$$

and

$$
\Gamma(1-\epsilon)=
1+\gamma_E\epsilon+O(\epsilon^2).
$$

Also

$$
X^{-\epsilon}=e^{-\epsilon\log X}
=1-\epsilon\log X+{\epsilon^2\over2}\log^2X+O(\epsilon^3).
$$

The combination that appears before $\overline{\mathrm{MS}}$ subtraction is often

$$
{1\over \bar\epsilon}
\equiv
{1\over\epsilon}-\gamma_E+\log 4\pi.
$$

Minimal subtraction, or MS, subtracts only pole terms in $1/\epsilon$. Modified minimal subtraction, or $\overline{\mathrm{MS}}$, subtracts the combination $1/\bar\epsilon$. Equivalently, one can build $e^{\gamma_E}/4\pi$ factors into the loop measure so that formulas naturally contain $1/\epsilon$ rather than $1/\bar\epsilon$.

The relation between schemes is a finite redefinition of parameters. It can change beta functions beyond universal orders, anomalous dimensions beyond universal pieces, and finite matching constants. It cannot change physical observables.

## Standard one-loop expansions

With the $\overline{\mathrm{MS}}$ measure

$$
\int_\ell^{\overline{\mathrm{MS}}}
=
\left({e^{\gamma_E}\mu^2\over 4\pi}\right)^\epsilon
\int {d^{4-2\epsilon}\ell\over (2\pi)^{4-2\epsilon}},
$$

one has

$$
\int_\ell^{\overline{\mathrm{MS}}}
{1\over (\ell^2+M^2)^2}
=
{1\over 16\pi^2}
\left[
{1\over\epsilon}-\log{M^2\over\mu^2}+O(\epsilon)
\right].
$$

Also,

$$
\int_\ell^{\overline{\mathrm{MS}}}
{1\over \ell^2+M^2}
=
-{M^2\over 16\pi^2}
\left[
{1\over\epsilon}+1-
\log{M^2\over\mu^2}+O(\epsilon)
\right].
$$

The minus sign in the Euclidean tadpole surprises people. It comes from $\Gamma(-1+\epsilon)$. The integral is positive for fixed integer dimension below two where it converges, but the analytic continuation to $d=4-2\epsilon$ has a pole and a finite part whose sign is not an ordinary positive integral statement. This is another reminder that dimensional regularization is analytic continuation, not a cutoff with a hidden positive measure.

For logarithms, differentiating with respect to $\alpha$ gives identities such as

$$
\int {d^d\ell\over(2\pi)^d}
{\log(\ell^2+\Delta)\over(\ell^2+\Delta)^\alpha}
=
-\partial_\alpha
\int {d^d\ell\over(2\pi)^d}
{1\over(\ell^2+\Delta)^\alpha}.
$$

This derivative trick is often cleaner than evaluating logarithmic integrals directly.

## Scaleless integrals vanish

A central dimensional-regularization identity is

$$
\int {d^d\ell\over(2\pi)^d}(\ell^2)^\alpha=0
$$

whenever the integral has no dimensionful scale and is defined by dimensional regularization.

A scaling argument explains the result. Let

$$
I=\int d^d\ell\,(\ell^2)^\alpha.
$$

If the integral existed as a number, then under $\ell\mapsto \lambda \ell$ it would obey

$$
I=\lambda^{d+2\alpha}I.
$$

For arbitrary $\lambda$, this implies $I=0$ unless the exponent vanishes. In dimensional regularization the meromorphic continuation assigns zero to such scaleless integrals.

But the phrase “scaleless integrals vanish” is among the most abused in perturbation theory. A scaleless integral may contain both a UV and an IR divergence. Dimensional regularization can make them cancel algebraically:

$$
0\sim {1\over\epsilon_{\rm UV}}-{1\over\epsilon_{\rm IR}}.
$$

If a calculation needs to distinguish UV from IR physics, setting the integral to zero without labeling the origin of the pole can hide the answer. This matters in matching, effective field theory, factorization, and anomalous-dimension calculations.

## Power divergences and what dim-reg hides

With a hard cutoff, one often finds terms such as

$$
\Lambda^2,
\qquad
\Lambda^4,
\qquad
\log\Lambda.
$$

In dimensional regularization, power divergences are often absent in massless scaleless integrals, while logarithmic divergences appear as $1/\epsilon$ poles. This does not mean quadratic sensitivity is never physical. It means dimensional regularization expresses local power sensitivity differently, usually through the dependence of renormalized parameters and matching coefficients.

For example, the naturalness question for scalar masses is not solved by saying “dim-reg has no quadratic divergence.” A regulator-independent statement is: scalar mass terms are relevant operators, and heavy thresholds can contribute local terms proportional to the square of heavy masses unless protected by symmetry. Dimensional regularization makes this statement appear through matching, not through a literal $\Lambda^2$ integral.

So the correct slogan is:

> Dimensional regularization removes many regulator artifacts, not all physical sensitivity to scales.

That slogan saves a lot of grief.

## Minimal subtraction and locality

Suppose a regulated amplitude has the form

$$
\mathcal A(p_i,m_i;\epsilon)
=
{1\over\epsilon}P(p_i,m_i)+F(p_i,m_i)+O(\epsilon),
$$

where $P$ is polynomial in external momenta and masses. The pole part is local in position space. A counterterm can subtract it.

In MS, subtract

$$
{1\over\epsilon}P.
$$

In $\overline{\mathrm{MS}}$, subtract the corresponding $1/\bar\epsilon$ expression or use the $\overline{\mathrm{MS}}$ measure and subtract $1/\epsilon$.

The local nature of the pole is crucial. Nonlocal divergences would signal something more serious: a missing degree of freedom, an inconsistent expansion, an infrared singularity being mistaken for a UV divergence, or a broken assumption.

The renormalized amplitude then depends on $\mu$:

$$
\mathcal A_{\rm ren}=\mathcal A_{\rm ren}(p_i,m_i;\mu,g(\mu)).
$$

Physical observables cannot depend on the arbitrary scale $\mu$, so explicit logarithms and implicit running must compensate:

$$
\mu {d\over d\mu}\mathcal A_{\rm phys}=0.
$$

This is the computational origin of many renormalization-group equations.

## Lorentzian master formula

For many Feynman-integral calculations, one uses the Lorentzian identity

$$
\int {d^d\ell\over(2\pi)^d}
{1\over(\ell^2-\Delta+i0)^\alpha}
=
{i(-1)^\alpha\over(4\pi)^{d/2}}
{\Gamma(\alpha-d/2)\over\Gamma(\alpha)}
(\Delta-i0)^{d/2-\alpha},
$$

for integer $\alpha$ and with the usual continuation for powers. Different sign conventions for the metric and propagator move factors of $i$ and $(-1)$ around. The invariant content is the same: the pole structure is governed by $\Gamma(\alpha-d/2)$, and the branch is fixed by the $i0$ prescription.

If signs are important, do not memorize this formula in isolation. Derive it by Wick rotation from the propagator convention used on the page. This is slower once and faster forever.

## Feynman-parameter example

Consider the Euclidean integral

$$
I(p^2)=\int {d^d\ell\over(2\pi)^d}
{1\over(\ell^2+m^2)[(\ell+p)^2+m^2]}.
$$

Using

$$
{1\over AB}=\int_0^1 dx\,{1\over[xA+(1-x)B]^2},
$$

we get

$$
I(p^2)=\int_0^1 dx
\int {d^d\ell\over(2\pi)^d}
{1\over\left[\ell^2+2(1-x)\ell\cdot p+(1-x)p^2+m^2\right]^2}.
$$

Shift

$$
k=\ell+(1-x)p.
$$

Then

$$
I(p^2)=\int_0^1 dx
\int {d^d k\over(2\pi)^d}
{1\over[k^2+m^2+x(1-x)p^2]^2}.
$$

Applying the master formula gives

$$
I(p^2)=
{1\over(4\pi)^{d/2}}\Gamma(2-d/2)
\int_0^1 dx\,[m^2+x(1-x)p^2]^{d/2-2}.
$$

In $d=4-2\epsilon$ and with the $\overline{\mathrm{MS}}$ measure, this becomes

$$
I(p^2)=
{1\over16\pi^2}
\left[
{1\over\epsilon}
-
\int_0^1 dx\,\log{m^2+x(1-x)p^2\over\mu^2}
+O(\epsilon)
\right].
$$

The pole is independent of $p^2$ and $m^2$ except through local dimensions. The nonlocal dependence sits in the logarithm.

## Dimensional algebra rules

When computing in $d$ dimensions, use $d$-dimensional algebra consistently:

$$
\delta^i{}_i=d,
\qquad
\eta^\mu{}_{\mu}=d.
$$

For gamma matrices in a vectorlike theory one uses

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu},
\qquad
\gamma^\mu\gamma_\mu=d.
$$

The identity

$$
\gamma^\mu\gamma^\nu\gamma_\mu=(2-d)\gamma^\nu
$$

is a common source of sign and factor errors. In four dimensions it gives $-2\gamma^\nu$, but in dimensional regularization the $O(\epsilon)$ part can multiply a $1/\epsilon$ pole and contribute a finite term.

The Levi-Civita tensor and $\gamma^5$ are more delicate because their defining properties are intrinsically four-dimensional. A page using chiral fermions, anomalies, or parity-odd terms must state its gamma-five scheme. There is no one-line convention that avoids the issue in all calculations.

## Dimensional regularization versus dimensional continuation of physics

Dimensional regularization is a regulator. It does not mean spacetime literally has $4-2\epsilon$ dimensions. In perturbative QFT one usually treats $d$ as an analytic variable in loop integrals while continuing tensor algebra in a controlled way.

In critical phenomena, however, one often studies theories in noninteger $d$ more physically, for example in the $\epsilon$ expansion around $d=4$. There the continuation is not merely a bookkeeping trick; it is a systematic expansion around an upper critical dimension. Even there, observables at noninteger $d$ require careful definitions.

The same formulas appear in both contexts, but the interpretation differs.

## Common pitfalls

**Setting $d=4$ too early.** Do not replace $d$ by $4$ inside tensor contractions before expanding poles. Terms proportional to $\epsilon$ can multiply $1/\epsilon$ and leave finite contributions.

**Forgetting the scale $\mu$.** Loop integrals in $d=4-2\epsilon$ have different dimensions than in four dimensions. Missing powers of $\mu$ cause nonsense logarithms such as $\log M^2$ without a reference scale.

**Confusing MS and $\overline{\mathrm{MS}}$.** The difference is finite but real. A finite constant in a loop result may be a scheme convention, not a physics disagreement.

**Treating scaleless zero as physically empty.** A scaleless integral may hide a cancellation between UV and IR poles. In matching calculations, label the origin of divergences before discarding scaleless integrals.

**Using four-dimensional gamma identities blindly.** Identities involving $\gamma^5$, Levi-Civita tensors, or dimension-specific Fierz rearrangements may not continue naively to $d$ dimensions.

**Thinking dim-reg eliminates naturalness questions.** Dimensional regularization hides cutoff power divergences, but it does not remove threshold sensitivity to heavy masses or relevant operators.

**Dropping $i0$ data.** Analytic continuation and branch choices matter. The $i0$ prescription tells you how to continue logarithms and powers across cuts.

**Forgetting infrared divergences.** A $1/\epsilon$ pole is not automatically UV. Massless theories often produce IR poles with the same symbol.

## Exercises

### Exercise 1: Derive the scalar master integral

Starting from the Schwinger representation, derive

$$
\int {d^d \ell\over(2\pi)^d}{1\over(\ell^2+\Delta)^\alpha}
=
{1\over (4\pi)^{d/2}}
{\Gamma(\alpha-d/2)\over\Gamma(\alpha)}
\Delta^{d/2-\alpha}.
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
{1\over(\ell^2+\Delta)^\alpha}
=
{1\over\Gamma(\alpha)}\int_0^\infty ds\,s^{\alpha-1}e^{-s(\ell^2+\Delta)}.
$$

Then

$$
\int {d^d\ell\over(2\pi)^d}e^{-s\ell^2}
=(4\pi s)^{-d/2}.
$$

The remaining integral is

$$
{1\over(4\pi)^{d/2}\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1-d/2}e^{-s\Delta}
=
{1\over(4\pi)^{d/2}}
{\Gamma(\alpha-d/2)\over\Gamma(\alpha)}\Delta^{d/2-\alpha}.
$$

</details>

### Exercise 2: Tensor reduction

Show that

$$
\int d^d\ell\,\ell_i\ell_j f(\ell^2)
={\delta_{ij}\over d}\int d^d\ell\,\ell^2 f(\ell^2).
$$

<details><summary><strong>Solution</strong></summary>

Rotational invariance implies the left-hand side must be proportional to $\delta_{ij}$:

$$
\int d^d\ell\,\ell_i\ell_j f(\ell^2)=C\delta_{ij}.
$$

Contract with $\delta_{ij}$:

$$
\int d^d\ell\,\ell_i\ell_i f(\ell^2)=C\delta_{ii}=Cd.
$$

Since $\ell_i\ell_i=\ell^2$, we get

$$
C={1\over d}\int d^d\ell\,\ell^2 f(\ell^2),
$$

which proves the formula.

</details>

### Exercise 3: Expand a logarithmically divergent integral

Using the $\overline{\mathrm{MS}}$ measure, show that

$$
\int_\ell^{\overline{\mathrm{MS}}}
{1\over(\ell^2+M^2)^2}
=
{1\over16\pi^2}
\left[{1\over\epsilon}-\log{M^2\over\mu^2}+O(\epsilon)\right].
$$

<details><summary><strong>Solution</strong></summary>

The master formula gives, with $d=4-2\epsilon$ and $\alpha=2$,

$$
\int {d^d\ell\over(2\pi)^d}{1\over(\ell^2+M^2)^2}
=
{1\over(4\pi)^{2-\epsilon}}\Gamma(\epsilon)(M^2)^{-\epsilon}.
$$

Multiplying by the $\overline{\mathrm{MS}}$ factor $(e^{\gamma_E}\mu^2/4\pi)^\epsilon$ gives

$$
{1\over(4\pi)^2}
\Gamma(\epsilon)e^{\gamma_E\epsilon}
\left({\mu^2\over M^2}\right)^\epsilon.
$$

Use

$$
\Gamma(\epsilon)=\frac1\epsilon-\gamma_E+O(\epsilon),
\qquad
 e^{\gamma_E\epsilon}=1+\gamma_E\epsilon+O(\epsilon^2),
$$

and

$$
\left({\mu^2\over M^2}\right)^\epsilon
=1+\epsilon\log{\mu^2\over M^2}+O(\epsilon^2).
$$

The $\gamma_E$ terms cancel, leaving

$$
{1\over16\pi^2}\left[{1\over\epsilon}+\log{\mu^2\over M^2}+O(\epsilon)\right]
=
{1\over16\pi^2}\left[{1\over\epsilon}-\log{M^2\over\mu^2}+O(\epsilon)\right].
$$

</details>

### Exercise 4: Why a scaleless integral vanishes

Use scale invariance to explain why dimensional regularization assigns

$$
\int d^d\ell\,(\ell^2)^\alpha=0.
$$

What is the caveat?

<details><summary><strong>Solution</strong></summary>

Let

$$
I=\int d^d\ell\,(\ell^2)^\alpha.
$$

Under $\ell\mapsto\lambda\ell$,

$$
I=\lambda^{d+2\alpha}I.
$$

Since there is no dimensionful scale that could compensate the factor $\lambda^{d+2\alpha}$, analytic continuation assigns $I=0$.

The caveat is that the integral may contain both UV and IR divergences. Dimensional regularization can make them cancel algebraically. In matching or factorization problems, one must know whether a pole is UV or IR before discarding a scaleless expression.

</details>

## References

For QFT uses of dimensional regularization and minimal subtraction, see standard treatments in Weinberg, Srednicki, Schwartz, Zee, Zinn-Justin, and Burgess. The original method was developed by 't Hooft and Veltman. For Wilsonian interpretation and the relation to cutoff reasoning, compare with Wilson–Kogut and modern EFT references. For special-function identities used here, see the Gamma and Beta Functions page in this volume.

## Version history

- 2026-06-26: First polished draft. Added master integrals, Schwinger and Feynman parameters, tensor reduction, gamma-function expansions, scaleless-integral cautions, MS and $\overline{\mathrm{MS}}$ bookkeeping, exercises, and a workflow figure.
