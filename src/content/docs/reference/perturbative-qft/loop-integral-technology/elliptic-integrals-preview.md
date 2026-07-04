---
title: "Elliptic Integrals Preview"
description: "A practical preview of elliptic sectors in Feynman integrals: elliptic curves, periods, sunrise-type integrals, modular variables, and elliptic generalizations of polylogarithms."
sidebar:
  label: "Elliptic Integrals Preview"
  order: 11
level: Advanced
status: "Polished draft"
source: "Bloch–Vanhove; Adams–Bogner–Weinzierl; Broedel–Duhr–Dulat–Tancredi; Bogner–Schweitzer–Weinzierl; recent reviews on elliptic Feynman integrals"
topics:
  - elliptic integrals
  - elliptic Feynman integrals
  - sunrise integral
  - elliptic curves
  - modular forms
canonicalTopics:
  - elliptic-integrals-preview
  - elliptic-feynman-integrals
  - elliptic-curves-in-loop-integrals
  - sunrise-integral
  - elliptic-polylogarithms
researchStatus:
  established:
    - "Elliptic curves and elliptic periods are established obstructions to expressing many Feynman integrals solely in terms of ordinary multiple polylogarithms."
  active:
    - "The systematic function theory for elliptic and higher-geometric Feynman integrals, including elliptic symbols, modular-form bases, and K3 or higher-dimensional period structures, remains an active research area."
---

## Summary

Some loop integrals are not expressible in ordinary multiple polylogarithms. The first common obstruction is **elliptic geometry**. Instead of repeated integrals of $d\log$ forms on a punctured sphere, the integral contains periods of a genus-one curve, often written as

$$
y^2=P_4(x)
$$

or equivalently as a cubic curve

$$
y^2=4x^3-g_2x-g_3.
$$

The basic new objects are the periods

$$
\omega_i=\oint_{\gamma_i}\frac{dx}{y},
\qquad i=1,2,
$$

and their ratio

$$
\tau=\frac{\omega_2}{\omega_1}.
$$

The two-loop massive sunrise integral is the canonical example. Its maximal cut is an elliptic period, so no amount of ordinary polylogarithm simplification can give the complete answer. The right conclusion is not "the integral is hopeless." The right conclusion is that the function space must be enlarged.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Flow from elliptic Feynman integrals to elliptic curves, periods, modular data, elliptic kernels, and final iterated-integral answers](/figures/perturbative-qft/elliptic-integrals-preview.svg)

<figcaption>

Elliptic sectors appear when the homogeneous part or maximal cut of a Feynman integral contains periods of a genus-one curve. The curve supplies periods $\omega_1,\omega_2$, the modular parameter $\tau$, and the kernels used to build elliptic iterated integrals or iterated integrals of modular forms.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/), [Schwinger Parameters](/perturbative-qft/loop-integral-technology/schwinger-parameters/), [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/), [Differential Equations for Integrals](/perturbative-qft/loop-integral-technology/differential-equations-for-integrals/), [Landau Singularities](/perturbative-qft/loop-integral-technology/landau-singularities/), and [Polylogarithms and Symbols Preview](/perturbative-qft/loop-integral-technology/polylogarithms-and-symbols-preview/).

The page assumes basic familiarity with complex analysis and Riemann surfaces. It does not assume that you already know elliptic curves; the necessary vocabulary is introduced here at the physics level.

## Core idea

Ordinary multiple polylogarithms are iterated integrals on genus-zero geometry: roughly, a sphere with punctures. Elliptic Feynman integrals appear when the integral geometry is genus one: a torus, or an algebraic curve with two independent cycles.

The simplest diagnostic is the maximal cut. If cutting enough propagators leaves an integral of the form

$$
\oint \frac{dx}{\sqrt{P_4(x)}},
$$

where $P_4$ has four distinct roots, then the cut is a period of an elliptic curve. Such a period is a solution of the homogeneous differential equation for the integral family. A function whose homogeneous solution is elliptic cannot usually be built from ordinary multiple polylogarithms alone.

The conceptual chain is

$$
\text{maximal cut}
\quad\Longrightarrow\quad
\text{algebraic curve}
\quad\Longrightarrow\quad
\text{periods}
\quad\Longrightarrow\quad
\text{elliptic function space}.
$$

This chain is the elliptic analog of the polylogarithmic story. In the polylogarithmic case, the basic kernels are $d\log$ forms. In the elliptic case, the curve contributes periods and kernels adapted to genus one.

## Setup and conventions

An elliptic curve can be represented as a double cover of the complex $x$-plane:

$$
E:
\qquad
 y^2=(x-e_1)(x-e_2)(x-e_3)(x-e_4),
$$

with distinct branch points $e_a$. The holomorphic one-form is

$$
\omega=\frac{dx}{y}.
$$

Choosing two independent cycles $\gamma_1$ and $\gamma_2$ gives the periods

$$
\omega_1=\oint_{\gamma_1}\omega,
\qquad
\omega_2=\oint_{\gamma_2}\omega.
$$

The ratio

$$
\tau=\frac{\omega_2}{\omega_1}
$$

is the modular parameter. With a conventional choice of cycles in a Euclidean region, one often has $\operatorname{Im}\tau>0$, so the nome

$$
q=e^{2\pi i\tau}
$$

satisfies $|q|<1$. Expansions in $q$ are then powerful, but only after the correct branch and analytic continuation have been chosen.

A standard complete elliptic integral is

$$
K(k)=\int_0^{\pi/2}\frac{d\theta}{\sqrt{1-k^2\sin^2\theta}}.
$$

The complementary integral is

$$
K'(k)=K(\sqrt{1-k^2}).
$$

For the Legendre form of the elliptic curve, a common period ratio is

$$
\tau=i\frac{K'(k)}{K(k)}
$$

in the region $0<k<1$. Loop-integral applications often use more complicated variables, but the role of periods is the same.

## The sunrise integral as the prototype

The two-loop sunrise graph with nonzero internal masses is the first place many QFT students meet elliptic Feynman integrals. In a schematic scalar form, the integral is

$$
S(p^2;m_1^2,m_2^2,m_3^2)
=
\int_{\ell_1}\int_{\ell_2}
\frac{1}{D_1D_2D_3},
$$

where

$$
D_1=\ell_1^2-m_1^2+i0,
\qquad
D_2=\ell_2^2-m_2^2+i0,
$$

and

$$
D_3=(p-\ell_1-\ell_2)^2-m_3^2+i0.
$$

After Feynman parametrization and appropriate integrations, the maximal cut is controlled by an algebraic curve. For generic nonzero masses and external momentum, this curve is elliptic. In one representation, the relevant square root has the form

$$
y^2=P_4(x),
$$

where the branch points depend on $p^2$ and the masses.

This is a decisive diagnostic. A bubble integral has a square root associated with two-particle phase space; that square root can often be rationalized locally, and the answer remains logarithmic or polylogarithmic. The massive sunrise has a genus-one curve. The period of that curve is part of the homogeneous solution, so a polylogarithmic ansatz is too small.

## Picard–Fuchs equations

Periods of algebraic curves satisfy differential equations as the external parameters vary. For elliptic curves, these are **Picard–Fuchs equations**. In the sunrise problem, the homogeneous differential equation for the master integral has two independent solutions that can be chosen as elliptic periods,

$$
\omega_1(p^2),
\qquad
\omega_2(p^2).
$$

A schematic form is

$$
\mathcal L_{\mathrm{PF}} S_{\mathrm{hom}}(p^2)=0,
$$

with

$$
S_{\mathrm{hom}}=c_1\omega_1+c_2\omega_2.
$$

The full inhomogeneous equation has source terms from simpler master integrals. Therefore the full answer is not just a complete elliptic integral. It is built from periods plus iterated integrals whose kernels are adapted to the elliptic curve.

This is the main reason elliptic sectors feel different from ordinary canonical $d\log$ systems. In many elliptic families, one first normalizes by periods or changes variables to $\tau$. Then the remaining integration kernels become modular forms or elliptic kernels. The resulting functions are elliptic analogs of multiple polylogarithms.

## Complete elliptic integrals and periods

The complete elliptic integral $K(k)$ is a period. It already shows the qualitative difference from ordinary logarithms. For small $k$,

$$
K(k)=\frac{\pi}{2}
\left(
1+\frac{k^2}{4}+\frac{9k^4}{64}+\cdots
\right),
$$

while near degeneration points it develops logarithmic behavior. Degeneration means that two branch points of the curve collide, so the genus-one curve collapses to a singular genus-zero curve. This is why elliptic integrals connect smoothly to logarithms at special kinematic points.

The two periods encode how the integration cycles wind around branch cuts. The ratio $\tau=\omega_2/\omega_1$ is not a decoration; it is the modulus of the elliptic curve. Many efficient representations of elliptic Feynman integrals use the nome

$$
q=e^{2\pi i\tau},
$$

because modular forms and elliptic polylogarithms often have rapidly convergent $q$-series in appropriate regions.

## Elliptic multiple polylogarithms

There is no single universally dominant notation for elliptic Feynman integrals. Several equivalent or overlapping languages are used:

| Language | Main idea | Typical use |
|---|---|---|
| Complete elliptic integrals | Express periods through $K(k)$ and $K'(k)$ | Homogeneous solutions, maximal cuts |
| Elliptic multiple polylogarithms | Iterated integrals on an elliptic curve | Direct generalization of multiple polylogarithms |
| Iterated integrals of modular forms | Use $\tau$ and modular kernels | Differential equations in modular variables |
| $q$-series | Expand in the nome $q$ | Numerical evaluation and analytic continuation |
| Picard–Fuchs systems | Study periods through differential equations | Identifying the geometry and homogeneous solutions |

The best language depends on the integral family, the desired kinematic region, and whether the goal is analytic simplification, numerical evaluation, branch tracking, or comparison to amplitudes.

A typical modular-form representation has the schematic form

$$
F(\tau)=
\int^{\tau}d\tau_1\,f_1(\tau_1)
\int^{\tau_1}d\tau_2\,f_2(\tau_2)
\cdots,
$$

where the $f_i$ are modular forms or modular-type kernels associated with the elliptic curve. This looks formally similar to a multiple polylogarithm, but the kernels are no longer merely rational $d\log$ forms in the original kinematic variable.

## How elliptic sectors are detected

There are several practical diagnostics.

**Maximal cuts.** If the maximal cut is an elliptic period, the family contains an elliptic sector.

**Feynman-parameter geometry.** If the Symanzik-polynomial geometry leads to a square root of a cubic or quartic with distinct roots, an elliptic curve is likely present.

**Differential equations.** If the homogeneous equation has period solutions rather than rational or logarithmic solutions, the sector is elliptic.

**Failure of rationalization.** A stubborn square root is not conclusive, but an irreducible genus-one curve explains why no global rational parametrization exists.

**Landau analysis.** Landau singularities identify degenerations and thresholds. In elliptic sectors, singular loci often correspond to collisions of branch points or degenerations of the elliptic curve.

These diagnostics are related but not identical. A single integral may have elliptic sub-sectors, while other sectors in the same family remain polylogarithmic. A full amplitude may also combine integrals in ways that cancel some elliptic contributions.

## Degenerations and thresholds

Elliptic curves degenerate when branch points collide. For

$$
y^2=(x-e_1)(x-e_2)(x-e_3)(x-e_4),
$$

a degeneration occurs when

$$
e_a=e_b
$$

for some pair of branch points. The discriminant of the quartic vanishes. Physically, these degenerations often line up with thresholds, pseudo-thresholds, or other Landau singularities.

At a degeneration, one cycle may shrink and a period may develop logarithmic behavior. This is why logarithms reappear near thresholds even in elliptic problems. The elliptic nature is not contradicted by logarithmic local expansions; it is the global period structure that is genus one.

## Beyond elliptic geometry

Elliptic integrals are the first step beyond ordinary multiple polylogarithms, not the last. More complicated Feynman integrals can involve higher-genus curves, Calabi–Yau varieties, K3 surfaces, or other period geometries. In such cases, even elliptic multiple polylogarithms may be too small a function space.

This is why the word "elliptic" should be used diagnostically, not as a synonym for "not polylogarithmic." The right question is: what geometry controls the maximal cuts and homogeneous differential equations?

For many phenomenologically important calculations, elliptic sectors are already a major practical frontier. They are difficult enough to require new methods, but structured enough that there is now a mature toolkit: periods, Picard–Fuchs equations, modular variables, elliptic kernels, and numerical analytic continuation.

## Common pitfalls

**Calling every difficult integral elliptic.** Non-polylogarithmic does not automatically mean elliptic. The controlling geometry may be genus one, higher genus, K3, Calabi–Yau, or something else.

**Trying to force a polylogarithmic basis.** If the maximal cut is an elliptic period, ordinary multiple polylogarithms are not a complete ansatz. The obstruction is geometric, not cosmetic.

**Confusing local logarithms with global polylogarithms.** Elliptic integrals often have logarithmic expansions near degeneration points. That does not mean the full function is polylogarithmic.

**Ignoring period normalization.** In elliptic sectors, the choice of periods and cycles affects the representation of the answer. A formula in one period basis can look very different from the same answer in another.

**Expanding in $q$ without checking the region.** Nome expansions are powerful when $|q|<1$ and the analytic continuation is controlled. A naive $q$-series on the wrong sheet is a beautifully efficient way to get the wrong number.

**Forgetting the simpler sub-sectors.** An integral family can mix polylogarithmic and elliptic sectors. Solving the elliptic sector does not remove the need to handle lower sectors, boundary data, and counterterms carefully.

## Relations to other pages

- [Polylogarithms and Symbols Preview](/perturbative-qft/loop-integral-technology/polylogarithms-and-symbols-preview/) explains the function class that elliptic integrals extend.
- [Differential Equations for Integrals](/perturbative-qft/loop-integral-technology/differential-equations-for-integrals/) supplies the master-integral framework in which Picard–Fuchs equations and elliptic kernels appear.
- [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/) explains how elliptic sectors arise inside reduced integral families.
- [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/) gives cut-based diagnostics, including maximal cuts that reveal periods.
- [Landau Singularities](/perturbative-qft/loop-integral-technology/landau-singularities/) explains threshold and degeneration loci that often control the branch structure of elliptic sectors.

## Research status

Elliptic Feynman integrals are established and unavoidable in many multi-scale loop calculations. The massive sunrise, kite, certain double-box integrals, and multi-loop banana graphs are standard examples where elliptic periods and elliptic iterated integrals appear.

The general theory is still developing. There are multiple useful function languages, and no single notation has become universal across all problems. Active work includes elliptic symbols, canonical forms beyond ordinary $d\log$ systems, iterated integrals of modular forms, numerical analytic continuation, and the classification of still more general geometries in higher-loop integrals.

## Exercises

### Exercise 1: Small-k expansion of K(k)

Starting from

$$
K(k)=\int_0^{\pi/2}\frac{d\theta}{\sqrt{1-k^2\sin^2\theta}},
$$

show that

$$
K(k)=\frac{\pi}{2}
\left(1+\frac{k^2}{4}+\frac{9k^4}{64}+O(k^6)\right).
$$

<details>
<summary><strong>Solution</strong></summary>

Use the binomial expansion

$$
(1-k^2\sin^2\theta)^{-1/2}
=1+\frac12 k^2\sin^2\theta+
\frac38 k^4\sin^4\theta+O(k^6).
$$

The needed integrals are

$$
\int_0^{\pi/2}d\theta=\frac{\pi}{2},
\qquad
\int_0^{\pi/2}\sin^2\theta\,d\theta=\frac{\pi}{4},
$$

and

$$
\int_0^{\pi/2}\sin^4\theta\,d\theta=\frac{3\pi}{16}.
$$

Therefore

$$
K(k)=\frac{\pi}{2}
+\frac12 k^2\frac{\pi}{4}
+\frac38 k^4\frac{3\pi}{16}
+O(k^6),
$$

which gives

$$
K(k)=\frac{\pi}{2}
\left(1+\frac{k^2}{4}+\frac{9k^4}{64}+O(k^6)\right).
$$

</details>

### Exercise 2: Nome in the Euclidean region

For $0<k<1$, $K(k)>0$ and $K'(k)>0$. If

$$
\tau=i\frac{K'(k)}{K(k)},
$$

show that $|q|<1$ for

$$
q=e^{2\pi i\tau}.
$$

<details>
<summary><strong>Solution</strong></summary>

Since $K'(k)/K(k)>0$, the parameter $\tau$ is purely imaginary with positive imaginary part:

$$
\tau=i r,
\qquad
r=\frac{K'(k)}{K(k)}>0.
$$

Then

$$
q=e^{2\pi i(i r)}=e^{-2\pi r}.
$$

Thus $q$ is real and satisfies

$$
0<q<1.
$$

In particular, $|q|<1$, so $q$-series representations can converge rapidly in this region.

</details>

### Exercise 3: Degeneration of a quartic curve

Explain why the curve

$$
y^2=(x-e_1)(x-e_2)(x-e_3)(x-e_4)
$$

degenerates when $e_1=e_2$.

<details>
<summary><strong>Solution</strong></summary>

If $e_1=e_2$, the right-hand side has a double root:

$$
y^2=(x-e_1)^2(x-e_3)(x-e_4).
$$

The branch points $e_1$ and $e_2$ have collided. The double cover no longer has four distinct branch points, and one cycle of the elliptic curve shrinks. Geometrically, the smooth genus-one curve degenerates to a singular curve. In Feynman-integral applications, such degenerations often correspond to thresholds or pseudo-thresholds.

</details>

### Exercise 4: Why a period obstructs ordinary polylogarithms

Suppose the maximal cut of an integral is

$$
\oint_\gamma\frac{dx}{\sqrt{(x-e_1)(x-e_2)(x-e_3)(x-e_4)}}
$$

with four distinct branch points. Why is this evidence against an ordinary multiple-polylogarithm answer?

<details>
<summary><strong>Solution</strong></summary>

The integral is a period of the elliptic curve

$$
y^2=(x-e_1)(x-e_2)(x-e_3)(x-e_4).
$$

Ordinary multiple polylogarithms are iterated integrals on genus-zero geometry with logarithmic kernels. A nontrivial period of a smooth genus-one curve is not generated by such kernels. Since the maximal cut is part of the homogeneous solution of the differential equation for the integral family, an ordinary polylogarithmic ansatz is not large enough for the full answer.

</details>

### Exercise 5: Local logarithms do not imply global polylogarithms

Why can an elliptic Feynman integral have logarithmic behavior near a threshold without becoming a polylogarithmic integral?

<details>
<summary><strong>Solution</strong></summary>

Near a threshold, the elliptic curve may degenerate because branch points collide. In that local limit, one period can develop logarithmic behavior, so a local expansion may contain logs. But the global function still knows about the smooth genus-one curve away from the degeneration point. Polylogarithms can describe the local limiting behavior without describing the full elliptic period structure.

</details>

## References

### Standard first pass

- L. Adams, C. Bogner, and S. Weinzierl, works on the two-loop sunrise graph and elliptic Feynman integrals, for the physics entry point.
- S. Bloch and P. Vanhove, "The elliptic dilogarithm for the sunset graph," for the arithmetic and period viewpoint on the sunrise/sunset integral.
- J. Broedel, C. Duhr, F. Dulat, and L. Tancredi, works on elliptic polylogarithms and the sunrise integral, for iterated-integral approaches on elliptic curves.

### Deeper references

- C. Bogner, A. Schweitzer, and S. Weinzierl, work on analytic continuation and numerical evaluation of the kite and sunrise integrals, for practical continuation and $q$-series methods.
- L. Adams and S. Weinzierl, papers on Feynman integrals and iterated integrals of modular forms, for modular-form representations.
- M. Wilhelm and C. Zhang, work on symbols for elliptic multiple polylogarithms, for modern elliptic-symbol technology.
- V. A. Smirnov, *Feynman Integral Calculus*, for the broader loop-integral background preceding elliptic methods.
- Recent work on banana integrals, traintrack integrals, K3 surfaces, and Calabi–Yau geometries for examples beyond the elliptic class.

## Version history

- **2026-06-12:** Initial standardized page.
