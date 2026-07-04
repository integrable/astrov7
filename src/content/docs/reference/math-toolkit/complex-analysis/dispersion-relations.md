---
title: "Dispersion Relations"
description: "Explains dispersion relations as Cauchy formulas for functions with cuts, including discontinuities, spectral densities, Kramers–Kronig relations, subtractions, retarded correlators, scattering amplitudes, and QFT caveats."
sidebar:
  label: "Dispersion Relations"
  order: 6
level: Graduate
status: "Polished draft"
source: "Standard references on complex analysis, causality, spectral representations, scattering theory, thermal and real-time QFT, and dispersion methods, including Titchmarsh, Ahlfors, Eden–Landshoff–Olive–Polkinghorne, Nussenzveig, Weinberg, Srednicki, Schwartz, Zee, Zinn-Justin, Peskin–Schroeder, Le Bellac, Kapusta–Gale, and condensed-matter treatments of Kramers–Kronig relations."
topics:
  - dispersion relations
  - Cauchy representation
  - discontinuity
  - spectral density
  - Kramers–Kronig relations
  - retarded Green functions
  - causality
  - subtractions
  - Hilbert transforms
  - optical theorem
  - analytic structure
canonicalTopics:
  - dispersion-relation
  - cauchy-representation
  - discontinuity
  - spectral-density
  - kramers-kronig-relation
  - retarded-green-function
  - causality
  - subtraction
  - hilbert-transform
  - optical-theorem
  - analytic-structure
researchStatus:
  established:
    - "Dispersion relations are standard consequences of analyticity, boundary values, and growth assumptions. In QFT they connect spectral densities, causal response functions, and scattering amplitudes to real parts of correlators or amplitudes."
    - "Subtractions encode polynomial ambiguities when a function does not decay fast enough at complex infinity."
  active:
    - "Modern uses include S-matrix positivity bounds, EFT constraints, finite-temperature spectral reconstruction, conformal dispersion formulas, real-time numerical analytic continuation, and rigorous treatments of analyticity and causality."
---

## Summary

A dispersion relation reconstructs an analytic function from its singularities, usually from its discontinuity across a cut. It is not a mysterious extra physical principle. It is Cauchy’s theorem plus analyticity plus a growth condition.

The prototype is this: suppose $F(z)$ is analytic in the complex $z$-plane except for a cut on the real axis and decays sufficiently fast at infinity. Then

$$
F(z)=\int_{\mathrm{cut}}\frac{ds}{2\pi i}\,
\frac{\operatorname{Disc}F(s)}{s-z},
$$

where

$$
\operatorname{Disc}F(s)=F(s+i0)-F(s-i0).
$$

If $F(s-i0)=F(s+i0)^*$ on the cut, then

$$
\operatorname{Disc}F(s)=2i\operatorname{Im}F(s+i0),
$$

and the formula becomes

$$
F(z)=\frac{1}{\pi}\int_{\mathrm{cut}}ds\,
\frac{\operatorname{Im}F(s+i0)}{s-z}.
$$

<figure class="doc-figure" style="--figure-width: 55rem;">

![Two-panel diagram showing a Cauchy contour around a branch cut and a retarded response function analytic in the upper half-plane.](/figures/math-toolkit/dispersion-relation-contour.svg)

<figcaption>

A dispersion relation is a Cauchy representation in disguise. The contour is deformed onto the cut, so the analytic function is reconstructed from boundary data. For retarded correlators, causality puts the analytic domain in the upper half of the complex frequency plane.

</figcaption>
</figure>

The QFT slogan is

$$
\text{analyticity turns absorptive data into dispersive data.}
$$

Here “absorptive” usually means an imaginary part or discontinuity, often fixed by unitarity or a spectral density. “Dispersive” means the real part or off-cut value reconstructed from it.

## Prerequisites

You should know [Analytic Functions](/math-toolkit/complex-analysis/analytic-functions/), [Residues and Contours](/math-toolkit/complex-analysis/residues-and-contours/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), [Principal Values](/math-toolkit/analysis-distributions-fourier/principal-values/), [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/), and [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/).

We use the site Fourier convention

$$
f(t)=\int\frac{d\omega}{2\pi}\,e^{-i\omega t}\widetilde f(\omega),
\qquad
\widetilde f(\omega)=\int dt\,e^{i\omega t}f(t).
$$

With this convention, a causal function supported at $t\ge0$ has a Fourier transform analytic in the upper half-plane, under suitable boundedness assumptions.

## The Cauchy derivation

Let $F(z)$ be analytic in the complex plane except for a cut along some interval or ray on the real axis. Assume first that $F(z)$ decays fast enough as $|z|\to\infty$ that the large-circle contribution vanishes. Consider

$$
\frac{1}{2\pi i}\oint_C ds\,\frac{F(s)}{s-z},
$$

where $C$ circles the singularities and encloses the point $z$. By Cauchy’s integral formula, this is $F(z)$.

Now deform $C$ onto the two sides of the cut. The upper edge contributes $F(s+i0)$ and the lower edge contributes $-F(s-i0)$ because its orientation is opposite. Therefore

$$
F(z)=\int_{\mathrm{cut}}\frac{ds}{2\pi i}\,
\frac{F(s+i0)-F(s-i0)}{s-z}.
$$

That is the basic dispersion relation:

$$
F(z)=\int_{\mathrm{cut}}\frac{ds}{2\pi i}\,
\frac{\operatorname{Disc}F(s)}{s-z}.
$$

Define

$$
\rho_F(s)=\frac{1}{2\pi i}\operatorname{Disc}F(s).
$$

Then

$$
F(z)=\int_{\mathrm{cut}}ds\,\frac{\rho_F(s)}{s-z}.
$$

If the boundary values obey the Schwarz reflection property, $F(s-i0)=F(s+i0)^*$, then

$$
\rho_F(s)=\frac{1}{\pi}\operatorname{Im}F(s+i0).
$$

This is why spectral densities and imaginary parts are basically the same object up to convention-dependent factors.

## Boundary values and principal values

The dispersion formula becomes a relation between real and imaginary parts when $z$ approaches the cut. Put $z=\omega+i0$. Then

$$
\frac{1}{s-\omega-i0}
=\operatorname{PV}\frac{1}{s-\omega}+i\pi\delta(s-\omega).
$$

Thus

$$
F(\omega+i0)
=
\operatorname{PV}\int_{\mathrm{cut}}ds\,\frac{\rho_F(s)}{s-\omega}
+i\pi\rho_F(\omega),
$$

when $\omega$ lies on the cut and the formula is understood distributionally. If $\rho_F=(1/\pi)\operatorname{Im}F$, this says

$$
\operatorname{Re}F(\omega+i0)
=
\frac{1}{\pi}\operatorname{PV}\int_{\mathrm{cut}}ds\,
\frac{\operatorname{Im}F(s+i0)}{s-\omega}.
$$

This is one form of a Kramers–Kronig relation. Under the same decay assumptions, the inverse relation is

$$
\operatorname{Im}F(\omega+i0)
=
-\frac{1}{\pi}\operatorname{PV}\int_{\mathrm{cut}}ds\,
\frac{\operatorname{Re}F(s+i0)}{s-\omega},
$$

up to possible subtraction constants. These are Hilbert transforms: analyticity ties the two boundary components together.

The $i0$ is not cosmetic. The sign in

$$
\frac{1}{x\mp i0}=\operatorname{PV}\frac{1}{x}\pm i\pi\delta(x)
$$

is what makes the imaginary part match the chosen side of the cut.

## Retarded correlators and causality

Let

$$
G_R(t)=-i\theta(t)\langle[A(t),B(0)]\rangle
$$

be a retarded correlator. Its Fourier transform is

$$
G_R(\omega)=\int_{-\infty}^{\infty}dt\,e^{i\omega t}G_R(t).
$$

Because $G_R(t)$ vanishes for $t<0$, the exponential factor

$$
e^{i(\omega_R+i\omega_I)t}=e^{i\omega_R t}e^{-\omega_I t}
$$

damps the integral for $\omega_I>0$, assuming no worse-than-exponential growth. Therefore $G_R(\omega)$ is analytic in the upper half-plane.

If $G_R(\omega)$ decays sufficiently fast at infinity in the upper half-plane, closing the contour there gives Kramers–Kronig relations:

$$
\operatorname{Re}G_R(\omega)
=
\frac{1}{\pi}\operatorname{PV}\int_{-\infty}^{\infty}d\omega'\,
\frac{\operatorname{Im}G_R(\omega')}{\omega'-\omega},
$$

and

$$
\operatorname{Im}G_R(\omega)
=
-\frac{1}{\pi}\operatorname{PV}\int_{-\infty}^{\infty}d\omega'\,
\frac{\operatorname{Re}G_R(\omega')}{\omega'-\omega}.
$$

Many physics texts define a spectral function by

$$
\rho(\omega)=-2\operatorname{Im}G_R(\omega+i0),
$$

especially for bosonic commutator response. Other pages may use

$$
\rho_F(\omega)=\frac{1}{\pi}\operatorname{Im}F(\omega+i0).
$$

Both conventions are common. The safest habit is to state which object is called $\rho$ before using positivity or sum rules.

## Subtractions and polynomial ambiguities

The cleanest dispersion formula assumed that the large contour vanishes. QFT amplitudes and correlators often grow too fast. Then one uses **subtracted dispersion relations**.

Suppose $F(z)$ does not decay, but

$$
\frac{F(z)}{z-z_0}
$$

has good enough behavior at infinity. Apply the unsubtracted relation to

$$
\frac{F(z)-F(z_0)}{z-z_0}.
$$

One obtains the once-subtracted formula

$$
F(z)=F(z_0)+(z-z_0)
\int_{\mathrm{cut}}ds\,
\frac{\rho_F(s)}{(s-z)(s-z_0)}.
$$

More generally, after $N$ subtractions,

$$
F(z)=P_{N-1}(z)
+(z-z_0)^N
\int_{\mathrm{cut}}ds\,
\frac{\rho_F(s)}{(s-z)(s-z_0)^N},
$$

where $P_{N-1}$ is a polynomial of degree at most $N-1$ fixed by subtraction constants.

This polynomial is not a technical nuisance. In QFT, it is often exactly the local ambiguity allowed by counterterms, contact terms, or EFT Wilson coefficients. Dispersion relations reconstruct the nonlocal part from cuts; local polynomial pieces require extra input.

## Källén–Lehmann as a dispersion relation

The Källén–Lehmann representation is one of the most important QFT examples. For a scalar two-point function, positivity and translation invariance imply a spectral representation of the form

$$
\Delta_F(p^2)
=
\int_0^\infty d\mu^2\,
\rho(\mu^2)\,
\frac{i}{p^2-\mu^2+i0},
$$

up to convention-dependent normalization. The analytic variable is $p^2$. The spectral density has support on physical invariant masses. A stable one-particle state gives a delta-function term,

$$
\rho(\mu^2)\supset Z\delta(\mu^2-m^2),
$$

while multiparticle states produce a continuum starting at thresholds.

In Euclidean momentum, with $Q^2=-p^2>0$, the same idea becomes a Stieltjes transform:

$$
\Delta_E(Q^2)=\int_0^\infty d\mu^2\,
\frac{\rho(\mu^2)}{Q^2+\mu^2}.
$$

This formula is a dispersion relation in friendly clothes: Euclidean data are values of an analytic function away from the cut, while the spectral density is the discontinuity across the physical cut.

## Scattering amplitudes and the optical theorem

In scattering theory, an amplitude $\mathcal M(s,t)$ is often studied as a function of the Mandelstam variable $s$ at fixed $t$. Analyticity places poles and branch cuts in the complex $s$-plane. Unitarity fixes the discontinuity across physical cuts. Schematically,

$$
\operatorname{Disc}_s\mathcal M(s,t)
$$

is related to sums over intermediate on-shell states. In forward scattering, the optical theorem gives a particularly direct relation between the imaginary part and a total cross section.

A fixed-$t$ dispersion relation has the schematic form

$$
\mathcal M(s,t)
=P(s,t)+\frac{1}{\pi}\int_{s_{\mathrm{th}}}^\infty ds'\,
\frac{\operatorname{Im}\mathcal M(s'+i0,t)}{s'-s}
+\text{crossed-channel cuts},
$$

with enough subtractions to make the integral meaningful. The polynomial $P$ contains subtraction data.

Modern EFT positivity bounds start from this logic. Analyticity, crossing, unitarity, and boundedness constrain low-energy Taylor coefficients of amplitudes. But the assumptions matter: mass gaps, IR behavior, gravity, fixed-$t$ analyticity, and high-energy growth can all change the conclusion.

## Thermal and numerical analytic continuation

At finite temperature, Euclidean correlators are often computed at Matsubara frequencies:

$$
\omega_n=2\pi nT
\quad\text{for bosons},
\qquad
\omega_n=(2n+1)\pi T
\quad\text{for fermions}.
$$

The retarded correlator is obtained by analytic continuation

$$
i\omega_n\to\omega+i0,
$$

but that notation compresses a real mathematical problem. Values on a discrete set do not, by themselves, determine a unique analytic function without growth conditions. In numerical work, reconstructing $\rho(\omega)$ from Euclidean data is ill-conditioned because the Euclidean kernel smears spectral information.

This is why “analytic continuation” in thermal Monte Carlo is hard even though the symbolic rule looks easy. The symbolic rule assumes the analytic function has already been identified.

## Common pitfalls

The most common mistake is to write an unsubtracted dispersion relation without checking the behavior at infinity. If the large contour does not vanish, missing subtractions show up as wrong constants or wrong polynomials.

A second mistake is to confuse the discontinuity with the imaginary part when Schwarz reflection fails or when matrix-valued correlators are involved. The discontinuity is the primitive object:

$$
\operatorname{Disc}F=F_+-F_-.
$$

The imaginary part is a shortcut only under extra reality conditions.

A third mistake is to forget principal values. Boundary-value formulas on the cut are distributional.

A fourth mistake is to infer a spectral density from Euclidean data by naive substitution. Analytic continuation from discrete or noisy data is an inverse problem, not algebra.

A fifth mistake is to ignore contact terms. Local terms in position space become polynomials in momentum space, and dispersion integrals over cuts do not determine them unless subtraction data are supplied.

## Exercises

### Exercise 1: A delta-function spectral density

Let

$$
\rho(s)=\delta(s-m^2),
\qquad
F(z)=\int_0^\infty ds\,\frac{\rho(s)}{s-z}.
$$

Compute $F(z)$ and its boundary value $F(\omega+i0)$.

<details><summary><strong>Solution</strong></summary>

The integral is immediate:

$$
F(z)=\frac{1}{m^2-z}.
$$

For $z=\omega+i0$,

$$
F(\omega+i0)=\frac{1}{m^2-\omega-i0}.
$$

Using

$$
\frac{1}{x-i0}=\operatorname{PV}\frac{1}{x}+i\pi\delta(x),
$$

with $x=m^2-\omega$, we get

$$
F(\omega+i0)
=
\operatorname{PV}\frac{1}{m^2-\omega}
+i\pi\delta(m^2-\omega).
$$

Therefore

$$
\frac{1}{\pi}\operatorname{Im}F(\omega+i0)=\delta(\omega-m^2),
$$

as required.

</details>

### Exercise 2: Once-subtracted dispersion relation

Assume $F$ has one cut and that $(F(z)-F(z_0))/(z-z_0)$ decays fast enough for an unsubtracted dispersion relation. Derive

$$
F(z)=F(z_0)+(z-z_0)
\int_{\mathrm{cut}}ds\,
\frac{\rho_F(s)}{(s-z)(s-z_0)}.
$$

<details><summary><strong>Solution</strong></summary>

Define

$$
H(z)=\frac{F(z)-F(z_0)}{z-z_0}.
$$

By assumption, $H$ satisfies an unsubtracted dispersion relation:

$$
H(z)=\int_{\mathrm{cut}}ds\,\frac{\rho_H(s)}{s-z}.
$$

Since $F(z_0)$ has no discontinuity,

$$
\operatorname{Disc}H(s)=\frac{\operatorname{Disc}F(s)}{s-z_0},
$$

so

$$
\rho_H(s)=\frac{\rho_F(s)}{s-z_0}.
$$

Multiplying by $z-z_0$ and adding $F(z_0)$ gives

$$
F(z)=F(z_0)+(z-z_0)
\int_{\mathrm{cut}}ds\,
\frac{\rho_F(s)}{(s-z)(s-z_0)}.
$$

</details>

### Exercise 3: Retarded analyticity

Suppose $g(t)$ vanishes for $t<0$ and obeys $|g(t)|\le Ce^{\alpha t}$ for $t>0$. Show that

$$
G(\omega)=\int_0^\infty dt\,e^{i\omega t}g(t)
$$

is analytic for $\operatorname{Im}\omega>\alpha$.

<details><summary><strong>Solution</strong></summary>

Write $\omega=u+iv$. Then

$$
|e^{i\omega t}g(t)|
\le
Ce^{-vt}e^{\alpha t}
=Ce^{-(v-\alpha)t}.
$$

For $v>\alpha$, this bound is integrable on $[0,\infty)$. The same argument applies after differentiating under the integral sign in a slightly smaller half-plane, giving

$$
\partial_\omega G(\omega)=
\int_0^\infty dt\,it\,e^{i\omega t}g(t),
$$

and similarly for higher derivatives. Therefore $G$ is holomorphic for $\operatorname{Im}\omega>\alpha$.

</details>

## References

For complex-analysis foundations, see Ahlfors, Titchmarsh, and standard texts on analytic boundary values. For scattering dispersion relations, classic references include Eden–Landshoff–Olive–Polkinghorne and Nussenzveig, with modern QFT treatments in Weinberg, Srednicki, Schwartz, Zee, and Zinn-Justin. For response theory and Kramers–Kronig relations, see thermal and condensed-matter field theory texts such as Le Bellac, Kapusta–Gale, Altland–Simons, and Fradkin. Modern EFT positivity bounds build on the same analytic machinery with sharper assumptions about unitarity, crossing, and high-energy behavior.

## Version history

- 2026-06-26: First polished draft.
