---
title: "Alternate Quantization and the BF Bound"
description: "Explain the Breitenlohner-Freedman stability bound, the alternate-quantization window, Legendre transforms, and double-trace boundary conditions in AdS/CFT."
sidebar:
  order: 50
---

The mass-dimension relation has two roots:

$$
\Delta_\pm
=
\frac d2\pm\nu,
\qquad
\nu=
\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

In standard quantization, a scalar in $\mathrm{AdS}_{d+1}$ is usually dual to an operator of dimension $\Delta_+$. But for a range of negative masses, the same bulk scalar admits a second consistent quantization in which the dual operator has dimension $\Delta_-$. This is called **alternate quantization**.

The stability bound is the Breitenlohner–Freedman bound:

$$
\boxed{
m^2L^2\ge -\frac{d^2}{4}.
}
$$

The clean alternate-quantization window is

$$
\boxed{
-\frac{d^2}{4}
\le
m^2L^2
<
-\frac{d^2}{4}+1
}
$$

or equivalently

$$
0\le\nu<1.
$$

This page explains why negative mass squared can be stable in AdS, why alternate quantization exists only near the BF bound, and how a choice of boundary condition becomes a choice of CFT data.

<figure class="doc-figure" style="--figure-width: 58rem;">

![The Breitenlohner-Freedman bound and the alternate-quantization window for a scalar in AdS.](/figures/course/alternate-quantization-bf-bound.svg)

<figcaption>

Scalar masses in AdS. Below the BF bound, $\nu$ is imaginary and the AdS vacuum is unstable. In the window $0\le\nu<1$, both asymptotic falloffs can be normalizable, so one may choose standard or alternate quantization. Above the window, the generic unitary choice is standard quantization with $\Delta=\Delta_+$.

</figcaption>
</figure>

## Why this matters

The GKP/Witten prescription says that a CFT source is a bulk boundary condition. This page makes that sentence sharper: near the BF bound, there is more than one consistent choice of boundary condition.

For a scalar with expansion

$$
\phi(z,x)
=
z^{\Delta_-}
\alpha(x)
+
z^{\Delta_+}
\beta(x)
+
\cdots,
$$

standard quantization uses

$$
\alpha
\quad
\text{as the source},
\qquad
\Delta(\mathcal O_+)=\Delta_+,
$$

while alternate quantization uses

$$
\beta
\quad
\text{as the source},
\qquad
\Delta(\mathcal O_-)=\Delta_-.
$$

This is not a semantic relabeling. It changes the variational principle, the generating functional, and the boundary CFT data. It is also the simplest arena in which double-trace deformations become mixed AdS boundary conditions.

## The BF bound

The two roots are real only when

$$
\frac{d^2}{4}+m^2L^2\ge0.
$$

Thus

$$
m^2L^2\ge -\frac{d^2}{4}.
$$

This is the BF bound.

In flat spacetime, a negative mass squared generally means an instability because

$$
\omega^2=\vec k^2+m^2
$$

becomes negative at small momentum. AdS is different. It has a timelike conformal boundary, and fields require boundary conditions there. It also behaves like a gravitational box. A negative local mass term can be compatible with a positive conserved energy if it is not too negative and if the boundary condition is chosen appropriately.

If the bound is violated, write

$$
\nu=i\gamma,
\qquad
\gamma>0.
$$

Then the falloffs are

$$
z^{d/2\pm i\gamma}
=
z^{d/2}
e^{\pm i\gamma\log z}.
$$

The dimensions are complex,

$$
\Delta=\frac d2\pm i\gamma,
$$

which is incompatible with an ordinary unitary CFT spectrum. The bulk and boundary diagnoses agree: below the BF bound, the AdS background is sick.

## Two falloffs and two coefficients

When the BF bound is obeyed, the scalar has the near-boundary expansion

$$
\phi(z,x)
=
z^{\Delta_-}
\left(
\alpha(x)+\cdots
\right)
+
z^{\Delta_+}
\left(
\beta(x)+\cdots
\right),
$$

where

$$
\Delta_-=\frac d2-\nu,
\qquad
\Delta_+=\frac d2+\nu,
\qquad
\Delta_-+\Delta_+=d.
$$

The coefficients $\alpha$ and $\beta$ are the two independent asymptotic data of the second-order radial equation. A choice of quantization tells us which coefficient is held fixed as a source and which one is determined dynamically as a response.

In standard quantization,

$$
\boxed{
\alpha=J_+,
\qquad
\beta\propto \langle\mathcal O_+\rangle,
\qquad
\Delta(\mathcal O_+)=\Delta_+.
}
$$

In alternate quantization,

$$
\boxed{
\beta=J_-,
\qquad
\alpha\propto \langle\mathcal O_-\rangle,
\qquad
\Delta(\mathcal O_-)=\Delta_-.
}
$$

The proportionality constants depend on conventions and counterterms. The source-response exchange does not.

## Normalizability and the alternate window

Why is alternate quantization not always allowed? The quickest answer is that the slower falloff is not always normalizable.

For a scalar mode behaving as

$$
\phi\sim z^\alpha,
$$

the Klein–Gordon norm near the boundary behaves schematically as

$$
\|\phi\|_{\mathrm{KG}}^2
\sim
\int_0 dz\,z^{1-d}|\phi|^2
\sim
\int_0 dz\,z^{2\alpha-d+1}.
$$

This converges near $z=0$ when

$$
2\alpha-d+1>-1,
$$

or

$$
\alpha>\frac{d-2}{2}.
$$

The faster falloff $z^{\Delta_+}$ is normalizable above the BF bound. The slower falloff $z^{\Delta_-}$ is normalizable only if

$$
\Delta_->\frac{d-2}{2}.
$$

Using

$$
\Delta_-=\frac d2-\nu,
$$

we get

$$
\frac d2-\nu>\frac{d-2}{2}
\quad
\Longleftrightarrow
\quad
\nu<1.
$$

Therefore alternate quantization is possible only in the window

$$
0\le\nu<1.
$$

In terms of the mass,

$$
0\le
\frac{d^2}{4}+m^2L^2
<1,
$$

so

$$
\boxed{
-\frac{d^2}{4}
\le
m^2L^2
<
-\frac{d^2}{4}+1.
}
$$

The same window appears from the boundary scalar unitarity bound. A scalar primary in a unitary $d$-dimensional CFT obeys

$$
\Delta\ge \frac{d-2}{2}
$$

for $d\ge3$, apart from the identity. The alternate dimension

$$
\Delta_-=\frac d2-\nu
$$

satisfies this bound only when $\nu\le1$, with endpoint subtleties.

## The variational principle

The source-response interpretation is a statement about the bulk variational principle.

On shell, the scalar action varies as a boundary term. After holographic renormalization, the variation has the schematic form

$$
\delta S_{\mathrm{ren}}
=
(2\nu)
\int d^d x\,
\beta(x)\delta\alpha(x)
+
\text{local terms},
$$

for non-integer $\nu$ in common conventions.

This is naturally a functional of $\alpha$:

$$
S_{\mathrm{ren}}=S_{\mathrm{ren}}[\alpha].
$$

Holding $\alpha$ fixed gives a well-posed Dirichlet-like variational problem. Holographically,

$$
\alpha(x)=J_+(x)
$$

is the source for an operator of dimension $\Delta_+$.

To obtain alternate quantization, one adds a finite boundary term that performs a Legendre transform. Schematically,

$$
\widetilde S_{\mathrm{ren}}[\beta]
=
S_{\mathrm{ren}}[\alpha]
-
(2\nu)
\int d^d x\,\alpha(x)\beta(x),
$$

with $\alpha$ eliminated in favor of $\beta$ through the bulk solution. Then

$$
\delta\widetilde S_{\mathrm{ren}}
=
-(2\nu)
\int d^d x\,
\alpha(x)\delta\beta(x)
+
\text{local terms}.
$$

Now $\beta$ is fixed at the boundary. Holographically,

$$
\beta(x)=J_-(x)
$$

is the source for an operator of dimension $\Delta_-$.

The sign and factor of $2\nu$ are convention-dependent. The invariant statement is

$$
\boxed{
\text{standard quantization fixes }\alpha,
\qquad
\text{alternate quantization fixes }\beta.
}
$$

## Standard and alternate dictionaries

For a scalar in the alternate window, the same bulk mass can describe two possible CFT dimensions:

| choice | source | response | operator dimension |
|---|---:|---:|---:|
| standard | $\alpha$ | $\beta$ | $\Delta_+=d/2+\nu$ |
| alternate | $\beta$ | $\alpha$ | $\Delta_-=d/2-\nu$ |

In standard quantization,

$$
\alpha(x)\equiv J_+(x),
\qquad
\beta(x)\propto\langle\mathcal O_+(x)\rangle.
$$

In alternate quantization,

$$
\beta(x)\equiv J_-(x),
\qquad
\alpha(x)\propto\langle\mathcal O_-(x)\rangle.
$$

Since

$$
d-\Delta_-=\Delta_+,
$$

the faster coefficient has exactly the dimension required to source an operator of dimension $\Delta_-$.

## Endpoint cases

### The BF point $\nu=0$

At the BF bound,

$$
\nu=0,
\qquad
m^2L^2=-\frac{d^2}{4},
\qquad
\Delta_+=\Delta_-=\frac d2.
$$

The two power-law solutions collide. The independent near-boundary solutions take the form

$$
\phi(z,x)
=
z^{d/2}
\left[
\alpha(x)\log(z\mu)
+
\beta(x)
+
\cdots
\right],
$$

where $\mu$ is a renormalization scale introduced by the logarithm.

This case is stable, but it is not just the generic two-root story with $\nu=0$ inserted. The logarithm changes the counterterms, the variational principle, and the scale dependence.

### The upper endpoint $\nu=1$

At the upper edge,

$$
\nu=1,
\qquad
m^2L^2=-\frac{d^2}{4}+1,
\qquad
\Delta_-=\frac{d-2}{2}.
$$

The alternate dimension saturates the scalar unitarity bound. In a unitary CFT, a scalar primary saturating this bound is a free field. Bulk analyses at this endpoint often involve logarithmic or boundary-term subtleties. For a first pass, treat $0<\nu<1$ as the clean open window and handle $\nu=0,1$ separately.

## Mixed boundary conditions and double-trace deformations

The standard and alternate choices are fixed points. More general boundary conditions correspond to deformations of the boundary theory.

A common mixed boundary condition is

$$
\beta=f\alpha.
$$

Depending on which quantization and normalization one starts with, the same physics may be written as $\alpha=f\beta$ or with additional local terms. The invariant idea is that a deformation changes the relation between source and response.

In the alternate theory, the double-trace deformation

$$
\delta S_{\mathrm{CFT}}
=
\frac f2
\int d^d x\,\mathcal O_-^2
$$

corresponds at large $N$ to a mixed boundary condition for the dual scalar. Since

$$
\Delta(\mathcal O_-^2)
\approx
2\Delta_-
=
d-2\nu,
$$

this operator is relevant for $0<\nu<1$. In the simplest large-$N$ story, the RG flow runs from alternate quantization in the ultraviolet to standard quantization in the infrared:

$$
\Delta_-
\quad
\longrightarrow
\quad
\Delta_+.
$$

This is one of the cleanest examples of how boundary conditions in AdS encode RG data in the CFT.

## Examples

### $m^2L^2=-2$ in $\mathrm{AdS}_4$

For $\mathrm{AdS}_4$, the boundary dimension is $d=3$. If

$$
m^2L^2=-2,
$$

then

$$
\nu
=
\sqrt{\frac94-2}
=
\frac12.
$$

Therefore

$$
\Delta_-=1,
\qquad
\Delta_+=2.
$$

Since $0\le\nu<1$, both quantizations are allowed.

The expansion is

$$
\phi(z,x)
=
z\left(\alpha(x)+\cdots\right)
+
z^2\left(\beta(x)+\cdots\right).
$$

Standard quantization gives a dimension-$2$ operator:

$$
\alpha=J_+,
\qquad
\beta\sim\langle\mathcal O_+\rangle,
\qquad
\Delta_+=2.
$$

Alternate quantization gives a dimension-$1$ operator:

$$
\beta=J_-,
\qquad
\alpha\sim\langle\mathcal O_-\rangle,
\qquad
\Delta_-=1.
$$

### $m^2L^2=-4$ in $\mathrm{AdS}_5$

For $\mathrm{AdS}_5$, $d=4$. If

$$
m^2L^2=-4,
$$

then

$$
\nu=0,
\qquad
\Delta=2.
$$

This is the BF bound in $\mathrm{AdS}_5$, and logarithms appear:

$$
\phi
\sim
z^2
\left(
\alpha\log(z\mu)+\beta+\cdots
\right).
$$

### $m^2L^2=-3$ in $\mathrm{AdS}_5$

For $d=4$ and $m^2L^2=-3$,

$$
\nu=1,
\qquad
\Delta_+=3,
\qquad
\Delta_-=1.
$$

The alternate dimension saturates the four-dimensional scalar unitarity bound,

$$
\Delta_-=\frac{d-2}{2}=1.
$$

This is an endpoint case, not the generic interior of the alternate window.

## Lorentzian comments

The near-boundary expansion and the choice of quantization are the same in Euclidean and Lorentzian signature. What changes is the interior condition used to determine the relation between $\alpha$ and $\beta$.

In Euclidean AdS, one usually demands regularity in the interior. In Lorentzian global AdS, one specifies a state and an $i\epsilon$ prescription. In a black-hole background, retarded correlators require incoming boundary conditions at the horizon.

These choices determine the response once the source is fixed. They do not replace the boundary choice between standard and alternate quantization.

## Dictionary checkpoint

For

$$
\phi(z,x)
=
z^{\Delta_-}\alpha(x)
+
z^{\Delta_+}\beta(x)
+
\cdots,
\qquad
\Delta_\pm=\frac d2\pm\nu,
$$

the BF bound is

$$
\boxed{
m^2L^2\ge -\frac{d^2}{4}.
}
$$

The alternate-quantization window is

$$
\boxed{
0\le\nu<1
\quad
\Longleftrightarrow
\quad
-\frac{d^2}{4}
\le
m^2L^2
<
-\frac{d^2}{4}+1.
}
$$

Standard quantization gives

$$
\boxed{
\alpha=J_+,
\qquad
\beta\sim\langle\mathcal O_+\rangle,
\qquad
\Delta(\mathcal O_+)=\Delta_+.
}
$$

Alternate quantization gives

$$
\boxed{
\beta=J_-,
\qquad
\alpha\sim\langle\mathcal O_-\rangle,
\qquad
\Delta(\mathcal O_-)=\Delta_-.
}
$$

Mixed boundary conditions correspond to multi-trace deformations, especially double-trace deformations at large $N$.

## Common confusions

### “The BF bound says negative masses are forbidden.”

No. It says sufficiently negative masses are forbidden. Scalars with

$$
-\frac{d^2}{4}\le m^2L^2<0
$$

can be stable in AdS.

### “If there are two roots, both quantizations are always allowed.”

No. The roots exist whenever the BF bound is satisfied, but alternate quantization requires the slower falloff to be normalizable and compatible with CFT unitarity. This restricts the mass to $0\le\nu<1$.

### “Alternate quantization changes the bulk mass.”

No. The mass is the same. The boundary condition and variational principle change. The same bulk equation can define different boundary CFT data.

### “Both coefficients are vevs if both modes are normalizable.”

No. Normalizability says what is allowed to fluctuate. The source/vev split is fixed by the chosen variational principle.

### “Integer $\nu$ is harmless.”

Integer $\nu$ often produces logarithms in the near-boundary expansion and contact-term ambiguities in correlation functions. The nonlocal part remains meaningful, but the local terms require a renormalization scheme.

## Exercises

### Exercise 1: The alternate window

Show that $0\le\nu<1$ is equivalent to

$$
-\frac{d^2}{4}
\le
m^2L^2
<
-\frac{d^2}{4}+1.
$$

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
\nu^2
=
\frac{d^2}{4}
+
m^2L^2.
$$

The condition $0\le\nu<1$ is equivalent to

$$
0\le\nu^2<1.
$$

Therefore

$$
0
\le
\frac{d^2}{4}
+
m^2L^2
<1.
$$

Subtracting $d^2/4$ gives

$$
-\frac{d^2}{4}
\le
m^2L^2
<
-\frac{d^2}{4}+1.
$$

</details>

### Exercise 2: The scalar unitarity bound

Use the scalar unitarity bound $\Delta\ge(d-2)/2$ to show that $\Delta_-=d/2-\nu$ is allowed only if $\nu\le1$.

<details>
<summary><strong>Solution</strong></summary>

Demanding the bound gives

$$
\frac d2-\nu
\ge
\frac{d-2}{2}
=
\frac d2-1.
$$

Canceling $d/2$ gives

$$
-\nu\ge -1,
$$

so

$$
\nu\le1.
$$

The endpoint $\nu=1$ saturates the bound and is subtle.

</details>

### Exercise 3: $\mathrm{AdS}_4$ with $m^2L^2=-2$

For $d=3$ and $m^2L^2=-2$, compute $\nu$, $\Delta_+$, and $\Delta_-$. Is alternate quantization allowed?

<details>
<summary><strong>Solution</strong></summary>

For $d=3$,

$$
\nu
=
\sqrt{\frac94-2}
=
\frac12.
$$

Thus

$$
\Delta_+
=
\frac32+\frac12
=
2,
\qquad
\Delta_-
=
\frac32-\frac12
=
1.
$$

Because $0\le\nu=1/2<1$, alternate quantization is allowed.

</details>

### Exercise 4: The BF logarithm

At the BF bound, what is $\Delta$ and why does a logarithm appear?

<details>
<summary><strong>Solution</strong></summary>

At the BF bound,

$$
m^2L^2=-\frac{d^2}{4},
$$

so

$$
\nu=0.
$$

Therefore

$$
\Delta_+=\Delta_-=\frac d2.
$$

A second-order radial equation still needs two independent solutions. When the two indicial roots coincide, the second solution typically contains a logarithm:

$$
\phi(z,x)
=
z^{d/2}
\left(
\alpha(x)\log(z\mu)
+
\beta(x)
+
\cdots
\right).
$$

</details>

### Exercise 5: Double-trace relevance

In alternate quantization with $0<\nu<1$, show that the double-trace operator $\mathcal O_-^2$ is relevant at large $N$.

<details>
<summary><strong>Solution</strong></summary>

At large $N$,

$$
\Delta(\mathcal O_-^2)
\approx
2\Delta_-.
$$

Since

$$
\Delta_-=\frac d2-\nu,
$$

we get

$$
2\Delta_-=d-2\nu.
$$

For $0<\nu<1$,

$$
d-2\nu<d.
$$

Therefore $\mathcal O_-^2$ is relevant.

</details>

## Further reading

- P. Breitenlohner and D. Z. Freedman, [Positive Energy in Anti-de Sitter Backgrounds and Gauged Extended Supergravity](https://doi.org/10.1016/0370-2693(82)90643-8).
- P. Breitenlohner and D. Z. Freedman, [Stability in Gauged Extended Supergravity](https://doi.org/10.1016/0003-4916(82)90116-6).
- I. R. Klebanov and E. Witten, [AdS/CFT Correspondence and Symmetry Breaking](https://arxiv.org/abs/hep-th/9905104).
- E. Witten, [Multi-Trace Operators, Boundary Conditions, and AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0112258).
- M. Berkooz, A. Sever, and A. Shomer, [Double-Trace Deformations, Boundary Conditions and Spacetime Singularities](https://arxiv.org/abs/hep-th/0112264).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
