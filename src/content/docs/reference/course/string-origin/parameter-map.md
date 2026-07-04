---
title: "The Parameter Map"
description: "How N, lambda, gYM, theta, gs, alpha prime, L, G10, G5, and five-form flux are matched between N=4 SYM and type IIB string theory on AdS5 x S5."
sidebar:
  order: 60
---

The decoupling argument identifies two interacting sectors of one D3-brane system:

$$
\mathcal N=4\;SU(N)\;\text{super-Yang–Mills}
\quad\longleftrightarrow\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5.
$$

This page translates the knobs. On the boundary side we can choose the rank $N$, the Yang–Mills coupling $g_{\mathrm{YM}}$, and the theta angle $\theta_{\mathrm{YM}}$. On the bulk side we have the number of five-form flux units, the string coupling $g_s$, the axion $C_0$, the string length $\ell_s=\sqrt{\alpha'}$, the AdS radius $L$, and Newton constants such as $G_{10}$ and $G_5$.

The main map, in the conventions used in this course, is

$$
g_{\mathrm{YM}}^2 = 4\pi g_s,
\qquad
\theta_{\mathrm{YM}} = 2\pi C_0,
\qquad
\lambda = g_{\mathrm{YM}}^2N = 4\pi g_sN,
\qquad
\frac{L^4}{\alpha'^2}=\lambda.
$$

The two expansion parameters that matter most are therefore

$$
\frac{\alpha'}{L^2}=\frac{1}{\sqrt{\lambda}},
\qquad
\frac{G_5}{L^3}\sim \frac{1}{N^2}.
$$

This is the quantitative reason behind the most famous qualitative slogan of AdS/CFT:

$$
\text{strongly coupled large-}N\text{ gauge theory}
\quad\longleftrightarrow\quad
\text{weakly curved weakly quantum gravity}.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![Parameter map between N=4 SYM and type IIB string theory on AdS5 x S5](/figures/course/ads-cft-parameter-map.svg)

<figcaption>

The basic parameter map of the canonical AdS$_5$/CFT$_4$ duality. The boundary rank $N$ becomes the five-form flux number through $S^5$, the Yang–Mills coupling fixes the string coupling, and the 't Hooft coupling $\lambda$ fixes the AdS radius in string units. Large $N$ suppresses bulk loops, while large $\lambda$ suppresses string-scale curvature corrections.

</figcaption>
</figure>

## Why this matters

The parameter map is not a decorative table. It tells us which calculations are controlled.

If $\lambda\ll1$, the boundary gauge theory may be perturbative, but the bulk curvature radius is string-scale or smaller:

$$
\frac{L}{\ell_s}=\lambda^{1/4}\ll 1.
$$

A classical spacetime description is then not reliable. The dual bulk is still supposed to exist, but it is a highly stringy quantum-gravity system.

If $\lambda\gg1$, the curvature radius is large compared with the string length:

$$
L\gg \ell_s.
$$

Stringy $\alpha'$ corrections are suppressed, and a supergravity description becomes plausible.

If $N\gg1$, connected bulk quantum loops are suppressed. In the five-dimensional description this is encoded in

$$
\frac{G_5}{L^3}\sim \frac{1}{N^2}.
$$

Thus the classical supergravity limit is not just “large coupling.” It is the combined regime

$$
N\gg1,
\qquad
\lambda\gg1,
\qquad
g_s=\frac{\lambda}{4\pi N}\ll1.
$$

A useful way to say this is:

$$
1\ll \lambda \ll N
$$

for a simple weakly coupled type IIB supergravity approximation. In the strict 't Hooft limit, one takes $N\to\infty$ with $\lambda$ fixed; then $g_s\to0$. To get weakly curved classical gravity, one subsequently wants $\lambda$ large.

## The boundary parameters

The boundary theory is four-dimensional $\mathcal N=4$ super-Yang–Mills. Its microscopic continuous parameters are usually packaged into the complex coupling

$$
\tau_{\mathrm{YM}}
=
\frac{\theta_{\mathrm{YM}}}{2\pi}
+
\frac{4\pi i}{g_{\mathrm{YM}}^2}.
$$

The rank $N$ is discrete. In the canonical statement one often writes $SU(N)$ rather than $U(N)$. The $U(1)$ center-of-mass sector of the D3-brane stack is free and decouples from the interacting $SU(N)$ theory. At large $N$ this distinction rarely affects leading holographic observables, but conceptually the interacting CFT is the $SU(N)$ part.

The most important real coupling is the 't Hooft coupling

$$
\lambda = g_{\mathrm{YM}}^2N.
$$

This is the parameter held fixed in the planar limit. Ordinary perturbation theory in the gauge theory is an expansion at small $g_{\mathrm{YM}}^2$, but large-$N$ perturbation theory reorganizes diagrams at fixed $\lambda$. In the planar limit, the genus expansion is controlled by $1/N^2$, while the dynamics within each planar diagram depends on $\lambda$.

For AdS/CFT, this distinction is priceless. The two parameters $N$ and $\lambda$ separately control two different bulk approximations:

$$
N \quad\text{controls bulk quantum loops},
\qquad
\lambda \quad\text{controls string-scale curvature corrections}.
$$

## The bulk parameters

The bulk theory is type IIB string theory on

$$
\mathrm{AdS}_5\times S^5
$$

with both factors having the same radius $L$. The string length is

$$
\ell_s=\sqrt{\alpha'}.
$$

The string coupling is

$$
g_s=e^{\Phi},
$$

where $\Phi$ is the type IIB dilaton, which is constant in the maximally supersymmetric AdS$_5\times S^5$ background.

The background also has $N$ units of self-dual Ramond–Ramond five-form flux through the sphere. Schematically,

$$
\int_{S^5} F_5 \propto N.
$$

The precise normalization depends on the convention used for Ramond–Ramond fields, but the physical statement is invariant: the integer $N$ is the quantized five-form flux number. The same integer is the number of D3-branes before the near-horizon limit and the rank of the gauge group after the open-string description is taken.

The bulk axion $C_0$ combines with the dilaton into the type IIB axio-dilaton

$$
\tau_{\mathrm{IIB}}=C_0+i e^{-\Phi}=C_0+\frac{i}{g_s}.
$$

With our convention $g_{\mathrm{YM}}^2=4\pi g_s$, the complex couplings match as

$$
\tau_{\mathrm{YM}}=\tau_{\mathrm{IIB}}.
$$

This matching is one of the cleanest places where the duality knows about more than the metric. The boundary theta angle is not a geometric radius; it is the boundary avatar of a bulk Ramond–Ramond scalar.

## Deriving $g_{\mathrm{YM}}^2=4\pi g_s$

The relation between the Yang–Mills coupling and the string coupling comes from the D3-brane worldvolume action. A D3-brane supports open strings. The massless open-string modes include a gauge field $A_\mu$ along the brane. For $N$ coincident branes the Chan–Paton labels make the fields matrix-valued, giving a non-Abelian gauge theory.

The low-energy D3-brane action contains a Yang–Mills term of the form

$$
S_{\mathrm{YM}}
=
-\frac{1}{4g_{\mathrm{YM}}^2}
\int d^4x\; \mathrm{Tr}\,F_{\mu\nu}F^{\mu\nu}
+
\cdots .
$$

Expanding the D3-brane Dirac–Born–Infeld action to quadratic order in the worldvolume field strength gives, in the trace convention used here,

$$
g_{\mathrm{YM}}^2=4\pi g_s.
$$

This numerical factor is a convention magnet. Authors who normalize generators or traces differently may write a factor of $2\pi$ instead of $4\pi$. For this course the convention is fixed by the two equations

$$
g_{\mathrm{YM}}^2=4\pi g_s,
\qquad
\lambda=4\pi g_sN.
$$

The invariant lesson is not the lonely factor of $4\pi$. The invariant lesson is that the open-string loop-counting parameter and the gauge coupling are the same physical knob.

## Deriving $L^4=4\pi g_sN\alpha'^2$

The relation between $L$ and $N$ comes from the closed-string description. A stack of $N$ coincident D3-branes is a source for the Ramond–Ramond five-form field strength. The extremal D3-brane solution has metric

$$
ds^2
=
H(r)^{-1/2}dx_{1,3}^2
+
H(r)^{1/2}\left(dr^2+r^2d\Omega_5^2\right),
$$

with harmonic function

$$
H(r)=1+\frac{L^4}{r^4}.
$$

Solving the type IIB equations with $N$ units of five-form flux fixes

$$
L^4=4\pi g_sN\alpha'^2.
$$

Combining this with the open-string relation gives

$$
\frac{L^4}{\alpha'^2}
=4\pi g_sN
=g_{\mathrm{YM}}^2N
=\lambda.
$$

Therefore

$$
\frac{L}{\ell_s}=\lambda^{1/4}.
$$

This is the key strong/weak feature of the duality. A strongly coupled boundary theory, $\lambda\gg1$, corresponds to a bulk spacetime whose curvature radius is large in string units. A weakly coupled boundary theory, $\lambda\ll1$, corresponds to a bulk background that is too stringy for classical Einstein gravity.

## The curvature expansion

String theory corrects supergravity by higher-derivative terms. Schematically, the low-energy action contains terms of the form

$$
S_{\mathrm{IIB}}
\sim
\frac{1}{2\kappa_{10}^2}
\int d^{10}x\sqrt{-g}\left(
R
+
\alpha'^3 R^4
+
\cdots
\right),
$$

where the detailed supersymmetric completion is complicated but the scaling lesson is simple. Curvature in AdS units is of order

$$
R_{\mathrm{curv}}\sim \frac{1}{L^2}.
$$

Thus the expansion parameter for stringy curvature corrections is roughly

$$
\alpha' R_{\mathrm{curv}}
\sim
\frac{\alpha'}{L^2}
=
\frac{1}{\sqrt{\lambda}}.
$$

This does not mean every correction appears at order $1/\sqrt{\lambda}$. Supersymmetry often removes lower-order corrections; in type IIB on AdS$_5\times S^5$, the famous leading higher-derivative correction is associated with an $\alpha'^3R^4$ term, giving effects that scale as a power such as $\lambda^{-3/2}$ in many observables. But the organizing principle is still

$$
\text{large }\lambda
\quad\Longrightarrow\quad
\text{small string-scale curvature corrections}.
$$

So when a holographic calculation uses only the two-derivative Einstein action, it is secretly assuming a strong-coupling expansion on the boundary side.

## The loop expansion and $N^2$

The ten-dimensional Newton constant is related to string parameters by

$$
2\kappa_{10}^2=(2\pi)^7g_s^2\alpha'^4,
\qquad
G_{10}=8\pi^6g_s^2\alpha'^4.
$$

Compactifying on $S^5$ gives the five-dimensional Newton constant

$$
G_5=\frac{G_{10}}{\mathrm{Vol}(S^5)}.
$$

Since

$$
\mathrm{Vol}(S^5)=\pi^3L^5,
$$

we have

$$
G_5=\frac{8\pi^3g_s^2\alpha'^4}{L^5}.
$$

Using

$$
L^4=4\pi g_sN\alpha'^2,
$$

one finds

$$
\frac{L^3}{G_5}
=
\frac{2N^2}{\pi}.
$$

Equivalently,

$$
G_5=\frac{\pi L^3}{2N^2}.
$$

This is the gravitational version of the statement that the boundary theory has order $N^2$ degrees of freedom. The small parameter for bulk quantum loops in five-dimensional AdS units is

$$
\frac{G_5}{L^3}\sim \frac{1}{N^2}.
$$

This also explains why classical black-hole entropy scales like $N^2$ in the boundary theory. A horizon area is measured in units of $G_5$, so

$$
S_{\mathrm{BH}}
\sim
\frac{L^3}{G_5}
\sim
N^2.
$$

For the canonical theory, the central charges at leading large $N$ are

$$
a=c=\frac{\pi L^3}{8G_5}=\frac{N^2}{4}.
$$

For $SU(N)$, the exact free-field value is proportional to $N^2-1$ rather than $N^2$. The difference is subleading at large $N$, which is why the gravity formula captures the leading classical result.

## The full map in one table

| Boundary quantity | Bulk quantity | Meaning |
|---|---|---|
| rank $N$ | $N$ units of $F_5$ flux through $S^5$ | quantized D3-brane charge |
| $g_{\mathrm{YM}}^2$ | $4\pi g_s$ | open-string coupling equals gauge coupling |
| $\theta_{\mathrm{YM}}$ | $2\pi C_0$ | gauge theta angle equals RR axion |
| $\tau_{\mathrm{YM}}$ | $\tau_{\mathrm{IIB}}$ | complex coupling equals axio-dilaton |
| $\lambda=g_{\mathrm{YM}}^2N$ | $L^4/\alpha'^2$ | AdS radius in string units |
| $1/\sqrt{\lambda}$ | $\alpha'/L^2$ | stringy curvature corrections |
| $1/N^2$ | $G_5/L^3$ | bulk loop corrections |
| central charge $c\sim N^2$ | $L^3/G_5$ | number of degrees of freedom |
| single-trace stringy gap $\Delta_{\mathrm{gap}}$ | $L/\ell_s\sim\lambda^{1/4}$ | separation between supergravity and string modes |

The last entry deserves emphasis. A massive string state has mass of order

$$
m_s\sim \frac{1}{\ell_s}.
$$

In AdS units, this corresponds roughly to a boundary scaling dimension

$$
\Delta_{\mathrm{string}}
\sim m_sL
\sim \frac{L}{\ell_s}
=\lambda^{1/4}.
$$

Thus at large $\lambda$, stringy single-trace operators become very heavy. Low-dimension single-trace operators are then described by supergravity modes. This is the first concrete version of the “large gap” idea that will reappear later when we discuss what kind of CFT can have a local Einstein-like bulk dual.

## Regimes of the correspondence

The same duality exists across all values of $N$ and $\lambda$, but different languages are useful in different regimes.

| Boundary regime | Bulk description | Controlled by |
|---|---|---|
| finite $N$, finite $\lambda$ | full quantum type IIB string theory on AdS$_5\times S^5$ | exact duality, not usually calculable |
| $N\gg1$, $\lambda$ finite | weak string coupling but generally string-scale curvature | planar string theory |
| $N\gg1$, $\lambda\ll1$ | perturbative SYM; bulk is highly stringy | gauge perturbation theory |
| $N\gg1$, $\lambda\gg1$ | weakly curved bulk; supergravity useful if $g_s\ll1$ | classical gravity plus corrections |
| $N\gg1$, $1\ll\lambda\ll N$ | clean classical type IIB supergravity | two-derivative gravity limit |

The phrase “classical gravity dual” usually refers to the last two rows, especially the regime in which both bulk loops and string corrections are suppressed.

## A note on $S^5$: it does not decouple

It is tempting to say that the dual of a four-dimensional CFT is simply a five-dimensional gravitational theory on AdS$_5$. That is often a useful shorthand, but the canonical string background is ten-dimensional:

$$
\mathrm{AdS}_5\times S^5.
$$

The sphere is not small compared with AdS. Its radius is also $L$. Therefore the Kaluza–Klein masses on $S^5$ are of order

$$
m_{\mathrm{KK}}\sim \frac{1}{L},
$$

which means the corresponding operator dimensions are of order one, not parametrically large. The Kaluza–Klein tower is an essential part of the spectrum.

So why do people often use five-dimensional gravity? Because for many questions there are consistent truncations: subsectors of the ten-dimensional theory in which setting all other fields to zero is compatible with the equations of motion. But this is not the same as saying the $S^5$ modes are heavy and can be integrated out in a Wilsonian sense.

This distinction prevents a common misunderstanding. Large $\lambda$ makes the string scale heavy compared with the AdS scale. It does not make the $S^5$ Kaluza–Klein scale heavy compared with the AdS scale.

## Relation to central charge and entropy

The parameter map also explains the normalization of thermodynamic quantities.

A four-dimensional CFT with order $N^2$ adjoint degrees of freedom has thermal entropy density of the form

$$
s \sim N^2T^3.
$$

The planar AdS$_5$ black brane gives

$$
s = \frac{\pi^2}{2}N^2T^3
$$

at infinite $N$ and infinite $\lambda$ for strongly coupled $\mathcal N=4$ SYM. The same $N^2$ comes from

$$
\frac{1}{G_5}\sim \frac{N^2}{L^3}.
$$

This is why black-brane computations naturally know about the rank of the boundary gauge group. The horizon area is a geometric quantity, but the unit in which it is measured is Newton's constant, and Newton's constant is fixed by $N$.

## What is exact and what is conventional

There are two kinds of statements on this page.

Some are exact structural identifications of the canonical duality:

$$
N \leftrightarrow \text{five-form flux},
\qquad
\tau_{\mathrm{YM}}\leftrightarrow\tau_{\mathrm{IIB}}.
$$

Others include convention-dependent numerical factors:

$$
g_{\mathrm{YM}}^2=4\pi g_s.
$$

The factor $4\pi$ depends on how the Yang–Mills action and Lie-algebra generators are normalized. Changing conventions should not change physics. It only changes where factors of $2$ and $\pi$ appear.

In this course we keep one convention throughout so that formulas line up cleanly:

$$
\lambda=g_{\mathrm{YM}}^2N=4\pi g_sN=\frac{L^4}{\alpha'^2}.
$$

When comparing to other references, always check the author's normalization of

$$
\mathrm{Tr}\,F^2,
\qquad
T^a,
\qquad
\tau_{\mathrm{YM}},
\qquad
\kappa_{10}.
$$

A surprising fraction of apparent disagreements in AdS/CFT notes are just trace-normalization disagreements wearing a fake moustache.

## Dictionary checkpoint

The parameter map gives the following working translations:

$$
\boxed{
\lambda = \frac{L^4}{\alpha'^2}
}
\qquad\Longrightarrow\qquad
\boxed{
\lambda\gg1\;\text{means weak curvature in string units}
}
$$

and

$$
\boxed{
\frac{G_5}{L^3}\sim \frac{1}{N^2}
}
\qquad\Longrightarrow\qquad
\boxed{
N\gg1\;\text{means suppressed bulk quantum loops}.
}
$$

The cleanest classical gravity regime is therefore

$$
N\gg1,
\qquad
\lambda\gg1,
\qquad
\frac{\lambda}{N}\ll1.
$$

The exact duality is broader than this regime. The classical gravity limit is only the corner in which the bulk description becomes easiest.

## Common confusions

### “Large $N$ is enough for classical gravity.”

Large $N$ suppresses bulk loops, but it does not suppress stringy curvature corrections. If $\lambda$ is not large, then $L$ is not large compared with $\ell_s$, and the bulk is stringy even at infinite $N$.

### “Large $\lambda$ means large string coupling.”

Not necessarily. In the canonical map,

$$
g_s=\frac{\lambda}{4\pi N}.
$$

One can have $\lambda\gg1$ and still have $g_s\ll1$ if $N$ is much larger than $\lambda$. This is why the classical supergravity regime requires a hierarchy, not just a single large number.

### “Setting $L=1$ removes the physics of $L$.”

Setting $L=1$ is a unit choice. The physical information is in dimensionless ratios such as

$$
\frac{L}{\ell_s},
\qquad
\frac{L^3}{G_5}.
$$

You can set $L=1$ in equations, but you cannot set both $L/\ell_s$ and $L^3/G_5$ to arbitrary values. They encode $\lambda$ and $N$.

### “The $S^5$ is small and can be ignored.”

No. In the canonical background, $S^5$ has the same radius as AdS$_5$. Some five-dimensional truncations are consistent and extremely useful, but the full spectrum includes Kaluza–Klein modes on $S^5$ with masses of order $1/L$.

### “The parameter map proves the duality.”

The map is part of the evidence and part of the definition of the correspondence, but by itself it is not a proof. It comes from comparing two decoupled descriptions of the same D3-brane system and matching symmetries, charges, couplings, spectra, and protected observables.

## Exercises

### Exercise 1: Radius in string units

Using

$$
\lambda=\frac{L^4}{\alpha'^2},
\qquad
\ell_s=\sqrt{\alpha'},
$$

show that

$$
\frac{L}{\ell_s}=\lambda^{1/4}.
$$

What happens to the curvature radius in string units when $\lambda\to\infty$?

<details>
<summary><strong>Solution</strong></summary>

Since $\ell_s^2=\alpha'$, we have

$$
\ell_s^4=\alpha'^2.
$$

Therefore

$$
\lambda=\frac{L^4}{\alpha'^2}
=\frac{L^4}{\ell_s^4}
=\left(\frac{L}{\ell_s}\right)^4.
$$

Taking the fourth root gives

$$
\frac{L}{\ell_s}=\lambda^{1/4}.
$$

As $\lambda\to\infty$, the AdS radius becomes much larger than the string length. This is the weak-curvature limit of the bulk string background.

</details>

### Exercise 2: Five-dimensional Newton constant

Use

$$
G_{10}=8\pi^6g_s^2\alpha'^4,
\qquad
\mathrm{Vol}(S^5)=\pi^3L^5,
\qquad
L^4=4\pi g_sN\alpha'^2
$$

to show that

$$
\frac{L^3}{G_5}=\frac{2N^2}{\pi}.
$$

<details>
<summary><strong>Solution</strong></summary>

Dimensional reduction on the sphere gives

$$
G_5=\frac{G_{10}}{\mathrm{Vol}(S^5)}.
$$

Using the given formulas,

$$
G_5
=
\frac{8\pi^6g_s^2\alpha'^4}{\pi^3L^5}
=
\frac{8\pi^3g_s^2\alpha'^4}{L^5}.
$$

Thus

$$
\frac{L^3}{G_5}
=
\frac{L^8}{8\pi^3g_s^2\alpha'^4}.
$$

Now square

$$
L^4=4\pi g_sN\alpha'^2
$$

to get

$$
L^8=16\pi^2g_s^2N^2\alpha'^4.
$$

Substituting gives

$$
\frac{L^3}{G_5}
=
\frac{16\pi^2g_s^2N^2\alpha'^4}{8\pi^3g_s^2\alpha'^4}
=
\frac{2N^2}{\pi}.
$$

</details>

### Exercise 3: Which regime is classical supergravity?

For each regime, decide whether classical two-derivative gravity is reliable.

1. $N=10^6$, $\lambda=0.01$.
2. $N=10^6$, $\lambda=10^3$.
3. $N=100$, $\lambda=10^6$.

<details>
<summary><strong>Solution</strong></summary>

1. $N$ is large, so bulk loops are suppressed, but $\lambda$ is tiny. The bulk curvature radius is smaller than the string scale: $L/\ell_s=\lambda^{1/4}\ll1$. Classical supergravity is not reliable.

2. $N$ is large and $\lambda$ is large. Also

   $$
   g_s=\frac{\lambda}{4\pi N}
   \approx
   \frac{10^3}{4\pi\times10^6}
   \ll1.
   $$

   This is a good classical supergravity regime.

3. $\lambda$ is large, so curvature corrections are suppressed, but

   $$
   g_s=\frac{10^6}{4\pi\times100}
   $$

   is very large. The simple weakly coupled type IIB supergravity expansion is not reliable. One should not call this the standard classical gravity limit.

</details>

### Exercise 4: The stringy gap

A massive string excitation has $m_s\sim1/\ell_s$. Estimate the scaling of the corresponding boundary operator dimension at large $\lambda$.

<details>
<summary><strong>Solution</strong></summary>

For a heavy bulk particle in AdS, the boundary scaling dimension is roughly its mass in AdS units:

$$
\Delta\sim mL.
$$

For a string-scale excitation,

$$
m_s\sim\frac{1}{\ell_s}.
$$

Therefore

$$
\Delta_{\mathrm{string}}
\sim
\frac{L}{\ell_s}
=
\lambda^{1/4}.
$$

At large $\lambda$, stringy operators become parametrically heavy compared with the low-lying supergravity spectrum.

</details>

## Further reading

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- G. T. Horowitz and J. Polchinski, [Gauge/gravity duality](https://arxiv.org/abs/gr-qc/0602037).
- N. Itzhaki, J. Maldacena, J. Sonnenschein, and S. Yankielowicz, [Supergravity and The Large $N$ Limit of Theories With Sixteen Supercharges](https://arxiv.org/abs/hep-th/9802042).
- J. Polchinski, [TASI Lectures on D-branes](https://arxiv.org/abs/hep-th/9611050).

The next page explains why these same relations imply the emergence of classical gravity in the large-$N$, large-$\lambda$ corner of the duality.
