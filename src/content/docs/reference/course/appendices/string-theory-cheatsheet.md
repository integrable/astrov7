---
title: "String Theory Cheatsheet"
description: "A compact reference for the string-theory ingredients used in AdS/CFT: strings, branes, alpha prime, string coupling, supergravity limits, RR flux, and the D3-brane parameter map."
sidebar:
  order: 70
---

This appendix collects the string-theory facts used throughout the course. It is not a substitute for a string-theory course. The goal is narrower: when the main text says “take the D3-brane decoupling limit,” “suppress $\alpha'$ corrections,” “turn on RR five-form flux,” or “expand the DBI action,” this page should tell you exactly what is meant.

The guiding lesson is simple. String theory supplies two kinds of degrees of freedom that AdS/CFT needs at once:

- **closed strings**, whose massless excitations include gravity;
- **open strings ending on D-branes**, whose massless excitations include gauge fields.

D-branes are the bridge. They support gauge theories through open strings, but they also source closed-string geometry. The canonical AdS$_5$/CFT$_4$ example comes from recognizing that the same stack of $N$ D3-branes has two low-energy descriptions.

<figure class="doc-figure" style="--figure-width: 50rem;">

![A compact map of string theory inputs for AdS/CFT.](/figures/course/string-theory-cheatsheet-map.svg)

<figcaption>

The minimal string-theory data used in this course: $\alpha'$ controls the string length, $g_s$ controls topology, closed strings give gravity, open strings on D-branes give gauge fields, and D3-branes lead to the $\mathrm{AdS}_5\times S^5$ dictionary.

</figcaption>
</figure>

## Basic scales and couplings

The fundamental string length is

$$
\ell_s = \sqrt{\alpha'} .
$$

The fundamental string tension is

$$
T_F = \frac{1}{2\pi\alpha'} .
$$

A long, nearly classical string with worldsheet area $A_{\mathrm{ws}}$ contributes roughly

$$
\exp(-T_F A_{\mathrm{ws}})
=
\exp\!\left(-\frac{A_{\mathrm{ws}}}{2\pi\alpha'}\right).
$$

Thus $\alpha'$ is not merely a notation. It is the parameter that measures how stringy the dynamics is. Curvatures much smaller than the string scale admit an effective field theory expansion; curvatures comparable to the string scale require the full tower of string modes.

The string coupling is determined by the expectation value of the dilaton,

$$
g_s = e^{\Phi_\infty} .
$$

Perturbative closed-string amplitudes are organized by worldsheet topology. For a closed oriented worldsheet of genus $h$,

$$
\mathcal A_h \sim g_s^{2h-2} .
$$

The sphere has $h=0$ and is the classical closed-string contribution. The torus has $h=1$ and is the one-loop closed-string contribution. In AdS/CFT language, bulk quantum loops are controlled not directly by the slogan “$g_s$ is small,” but by the dimensionless Newton coupling in AdS units. In the canonical D3-brane example this becomes

$$
\frac{G_5}{L^3} \sim \frac{1}{N^2} .
$$

The two independent expansion parameters one should keep mentally separate are therefore

$$
\text{stringy corrections:}\quad \frac{\alpha'}{L^2},
\qquad
\text{bulk quantum loops:}\quad \frac{G_{d+1}}{L^{d-1}} .
$$

For AdS$_5\times S^5$/CFT$_4$,

$$
\frac{L^2}{\alpha'} = \sqrt{\lambda},
\qquad
\frac{L^3}{G_5} = \frac{2N^2}{\pi} .
$$

So the classical supergravity regime is

$$
N \gg 1,
\qquad
\lambda \gg 1 .
$$

The first condition suppresses bulk loops. The second condition makes the background large compared with the string length.

## Worldsheet action

The bosonic part of the string worldsheet action in a background metric $G_{MN}(X)$ is the Polyakov action

$$
S_P
=
\frac{1}{4\pi\alpha'}
\int d^2\sigma\,\sqrt{h}\,h^{ab}
G_{MN}(X)\partial_a X^M\partial_b X^N
+
\cdots .
$$

Here:

| symbol | meaning |
|---|---|
| $\sigma^a$ | coordinates on the two-dimensional worldsheet |
| $X^M(\sigma)$ | embedding of the string into spacetime |
| $h_{ab}$ | auxiliary worldsheet metric |
| $G_{MN}$ | target-space metric |
| $\alpha'$ | inverse string tension scale |

The omitted terms include couplings to the NS-NS two-form $B_{MN}$, the dilaton $\Phi$, worldsheet fermions in superstring theory, and possible boundary terms for open strings.

A rough but useful lesson follows from the coefficient $1/\alpha'$. When the spacetime curvature radius $L$ is large compared with $\ell_s$, the worldsheet sigma model is weakly curved:

$$
\frac{\ell_s^2}{L^2}
=
\frac{\alpha'}{L^2}
\ll 1 .
$$

This is the origin of the statement that large $\lambda$ suppresses stringy corrections in AdS$_5$/CFT$_4$.

## Closed strings and gravity

Closed strings are loops. Their perturbative spectrum contains universal massless modes:

| closed-string field | common name | boundary interpretation in AdS/CFT |
|---|---|---|
| $G_{MN}$ | metric / graviton | stress tensor $T_{\mu\nu}$ |
| $B_{MN}$ | NS-NS two-form | antisymmetric tensor sources/operators where present |
| $\Phi$ | dilaton | coupling-like scalar operator |
| $C_p$ | RR $p$-form potentials | brane charges, fluxes, R-symmetry/topological data |

The most important fact for holography is that the massless spin-two closed-string state is the graviton. This is why a theory of closed strings is automatically a theory of gravity.

At energies much lower than the string scale, closed-string dynamics is described by a spacetime effective action. For type II strings, the schematic string-frame action includes

$$
S_{\mathrm{II}}
=
\frac{1}{2\kappa_{10}^2}
\int d^{10}x\,\sqrt{-G_s}\,
 e^{-2\Phi}
\left(
R_s + 4(\partial\Phi)^2 - \frac{1}{2}|H_3|^2
\right)
+
S_{\rm RR}+\cdots,
$$

where $H_3=dB_2$. The ellipsis includes fermions, Chern-Simons terms, and higher-derivative $\alpha'$ corrections.

The ten-dimensional gravitational coupling is commonly normalized as

$$
2\kappa_{10}^2
=
(2\pi)^7 g_s^2 \alpha'^4 .
$$

The dependence on $g_s^2$ is the spacetime version of the closed-string loop expansion.

## String frame versus Einstein frame

String theory naturally presents the low-energy action in **string frame**, where the NS-NS sector has the prefactor $e^{-2\Phi}$. General relativity intuition is cleaner in **Einstein frame**, where the Ricci scalar has no dilaton prefactor.

In ten dimensions the two metrics are related by

$$
G^{(E)}_{MN}
=
e^{-\Phi/2}G^{(s)}_{MN} .
$$

When the dilaton is constant, the two frames differ only by an overall scale. In backgrounds with running dilaton, the distinction matters.

For the simplest AdS$_5\times S^5$ background, the dilaton is constant, so the frame distinction is usually invisible in elementary calculations. In confining models, D$p$-brane backgrounds with $p\ne3$, or backgrounds with nontrivial scalar profiles, one must keep track of it.

## Open strings and gauge fields

Open strings have endpoints. Their massless excitations include gauge fields living on the locus where the endpoints are allowed to move. If there are $N$ identical branes, the endpoints carry Chan-Paton labels $i,j=1,\dots,N$. The open-string field becomes an $N\times N$ matrix,

$$
A_\mu = (A_\mu)^i{}_j .
$$

This is the string-theory origin of non-Abelian gauge symmetry on coincident D-branes.

The low-energy spectrum on $N$ coincident D$p$-branes contains a maximally supersymmetric Yang-Mills theory in $p+1$ dimensions. Its bosonic fields are:

| field | origin | interpretation |
|---|---|---|
| $A_a$, $a=0,\dots,p$ | open strings polarized along the brane | worldvolume gauge field |
| $X^I$, $I=p+1,\dots,9$ | open strings polarized transverse to the brane | matrix-valued brane positions |

For separated branes, the diagonal entries of $X^I$ describe brane positions. Off-diagonal open strings stretch between different branes and become massive. This is the stringy picture of Higgsing,

$$
U(N) \longrightarrow U(1)^N .
$$

For coincident branes, those off-diagonal modes become light, and the full non-Abelian gauge symmetry is restored.

## D-branes

A D$p$-brane is a $(p+1)$-dimensional hypersurface on which open strings can end. The letter “D” refers to Dirichlet boundary conditions in directions transverse to the brane.

For an open string ending on a flat D$p$-brane,

$$
\partial_\sigma X^a\big|_{\partial\Sigma}=0,
\qquad
 a=0,\dots,p,
$$

along the brane, and

$$
\delta X^I\big|_{\partial\Sigma}=0,
\qquad
 I=p+1,\dots,9,
$$

transverse to the brane. Thus open-string endpoints move freely along the brane but are fixed in transverse directions.

D-branes are not just places where open strings end. They are also charged objects in the closed-string theory. A D$p$-brane couples electrically to a Ramond-Ramond potential $C_{p+1}$:

$$
S_{\rm WZ}
\supset
\mu_p \int_{\mathcal W_{p+1}} C_{p+1} .
$$

The worldvolume $\mathcal W_{p+1}$ is the brane trajectory in spacetime.

In type IIA string theory, stable supersymmetric D$p$-branes have even $p$:

$$
p=0,2,4,6,8 .
$$

In type IIB string theory, they have odd $p$:

$$
p=-1,1,3,5,7,9 .
$$

The D3-brane is therefore a type IIB object.

## DBI and Wess-Zumino actions

The low-energy action of a single D$p$-brane contains a Dirac-Born-Infeld term and a Wess-Zumino term:

$$
S_{Dp}=S_{\rm DBI}+S_{\rm WZ} .
$$

In string frame,

$$
S_{\rm DBI}
=
-T_p
\int d^{p+1}\xi\,
 e^{-\Phi}
\sqrt{-\det\!\left(P[G_s+B]_{ab}+2\pi\alpha' F_{ab}\right)} .
$$

Here $P[\cdots]$ denotes pullback to the brane worldvolume, and $F=dA$ is the worldvolume field strength. The Wess-Zumino coupling is schematically

$$
S_{\rm WZ}
=
\mu_p
\int_{\mathcal W_{p+1}}
P\!\left[\sum_q C_q\right]
\wedge e^{2\pi\alpha' F + P[B]} .
$$

Expanding the DBI action for small field strength gives a Yang-Mills kinetic term. With common string-theory trace conventions one finds

$$
g_{\rm YM,p}^2
\sim
g_s(\alpha')^{(p-3)/2},
$$

with powers of $2\pi$ and sometimes a factor of $2$ depending on generator normalization. For the D3-brane convention used in this course,

$$
g_{\rm YM}^2 = 4\pi g_s,
\qquad
\lambda = g_{\rm YM}^2 N = 4\pi g_s N .
$$

The convention-independent lesson is that D-brane gauge coupling is controlled by the string coupling and the string scale.

## Type IIA, type IIB, and M-theory at a glance

The best-controlled AdS/CFT examples usually use type IIB string theory, type IIA string theory, or M-theory.

| theory | spacetime dimension | important AdS/CFT examples |
|---|---:|---|
| type IIB | $10$ | AdS$_5\times S^5$, AdS$_3\times S^3\times M_4$, many AdS$_5$ flux backgrounds |
| type IIA | $10$ | reductions of M-theory backgrounds, ABJM at suitable levels, D$p$-brane limits |
| M-theory | $11$ | AdS$_4\times S^7$, AdS$_7\times S^4$ |

The type IIA string coupling is related to the radius $R_{11}$ of the M-theory circle by

$$
R_{11} = g_s\ell_s .
$$

At strong type IIA coupling, the eleventh dimension decompactifies and the better description is eleven-dimensional M-theory.

This is why some AdS$_4$/CFT$_3$ and AdS$_7$/CFT$_6$ examples are naturally M-theoretic rather than purely ten-dimensional string backgrounds.

## The D3-brane supergravity solution

The extremal D3-brane solution of type IIB supergravity has metric

$$
ds^2
=
H(r)^{-1/2} \eta_{\mu\nu}dx^\mu dx^\nu
+
H(r)^{1/2}\left(dr^2+r^2d\Omega_5^2\right),
$$

where

$$
H(r)=1+\frac{L^4}{r^4} .
$$

The radius $L$ is fixed by five-form flux quantization:

$$
L^4 = 4\pi g_s N \alpha'^2 .
$$

The background also contains a self-dual five-form field strength,

$$
F_5 = {}^\star F_5,
$$

with $N$ units of flux through the $S^5$:

$$
\frac{1}{(2\pi)^4\alpha'^2}\int_{S^5} F_5 = N .
$$

In the near-horizon region $r\ll L$,

$$
H(r)\approx \frac{L^4}{r^4}.
$$

The metric becomes

$$
ds^2
=
\frac{r^2}{L^2}\eta_{\mu\nu}dx^\mu dx^\nu
+
\frac{L^2}{r^2}dr^2
+
L^2d\Omega_5^2 .
$$

With

$$
z=\frac{L^2}{r},
$$

this is

$$
ds^2
=
\frac{L^2}{z^2}\left(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu\right)
+
L^2d\Omega_5^2,
$$

which is $\mathrm{AdS}_5\times S^5$ in Poincaré coordinates.

## The D3-brane parameter map

For the canonical example,

$$
\mathcal N=4\; SU(N)\;\text{SYM}
\quad\longleftrightarrow\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5,
$$

the most important relations are

$$
g_{\rm YM}^2 = 4\pi g_s,
\qquad
\lambda = g_{\rm YM}^2N,
\qquad
\frac{L^4}{\alpha'^2}=\lambda .
$$

The five-dimensional Newton constant is obtained by reducing type IIB supergravity on $S^5$:

$$
G_5 = \frac{G_{10}}{\mathrm{Vol}(S^5)}
=
\frac{G_{10}}{\pi^3L^5} .
$$

With the standard flux quantization, this gives

$$
\frac{L^3}{G_5} = \frac{2N^2}{\pi} .
$$

A useful summary is:

| CFT parameter | bulk meaning |
|---|---|
| $N$ | flux number, rank of gauge group, controls bulk loop expansion |
| $\lambda$ | AdS radius in string units, controls $\alpha'$ corrections |
| $1/N^2$ | genus expansion / bulk quantum loops |
| $1/\sqrt{\lambda}$ | curvature in string units |
| $SO(6)_R$ | isometry group of $S^5$ |
| $\theta_{\rm YM}$ | RR axion $C_0$ |

The classical Einstein-gravity corner is not simply “large $N$.” It is large $N$ **and** large $\lambda$, plus a consistent truncation to the low-lying supergravity fields.

## Open strings versus closed strings in the D3-brane argument

The D3-brane derivation of AdS/CFT compares two low-energy descriptions of one physical system.

On the open-string side, the low-energy theory on $N$ coincident D3-branes is

$$
\mathcal N=4\; U(N)\;\text{SYM}
$$

plus decoupled free closed strings in asymptotically flat space. The center-of-mass $U(1)$ usually decouples, leaving the interacting $SU(N)$ theory.

On the closed-string side, the same D3-branes are heavy charged sources. Their backreaction creates the D3-brane geometry. The low-energy excitations split into asymptotically flat closed strings and excitations localized in the near-horizon throat.

Because the same free closed-string sector appears on both sides, one identifies the remaining interacting sectors:

$$
\mathcal N=4\; SU(N)\;\text{SYM}
\quad\longleftrightarrow\quad
\text{type IIB strings on }\mathrm{AdS}_5\times S^5 .
$$

This is the string-theory origin of the duality.

## Compactification and Kaluza-Klein modes

An AdS background in string theory is rarely just $\mathrm{AdS}_{d+1}$. It is usually

$$
\mathrm{AdS}_{d+1}\times X,
$$

where $X$ is a compact internal space such as $S^5$, $S^7$, $S^4$, a Sasaki-Einstein manifold, or an orbifold.

Fields propagating on $X$ decompose into Kaluza-Klein modes. If $Y_n(y)$ is an eigenfunction of the Laplacian on $X$,

$$
-\nabla_X^2 Y_n = \lambda_n Y_n,
$$

then a higher-dimensional field can be expanded as

$$
\Phi(x,z,y)=\sum_n \phi_n(x,z)Y_n(y).
$$

The eigenvalue contributes to the effective AdS mass of $\phi_n$. Through

$$
m_n^2L^2 = \Delta_n(\Delta_n-d),
$$

Kaluza-Klein masses become CFT operator dimensions.

In AdS$_5\times S^5$, the isometry group of the sphere is

$$
SO(6) \simeq SU(4),
$$

which matches the R-symmetry of $\mathcal N=4$ SYM. Kaluza-Klein modes on $S^5$ therefore organize into $SU(4)_R$ representations.

A common beginner mistake is to think that “classical gravity” always means pure gravity in five dimensions. For AdS$_5\times S^5$, the compact $S^5$ has the same radius as AdS$_5$. Its Kaluza-Klein tower is not parametrically heavier than the AdS scale. Pure five-dimensional Einstein gravity is a useful truncation for some observables, not the full low-energy spectrum.

## Fluxes and Freund-Rubin backgrounds

Many AdS backgrounds are supported by form-field flux. The intuitive mechanism is that flux through the internal space balances curvature.

For AdS$_5\times S^5$, the relevant field is the self-dual five-form $F_5$. The solution is schematically

$$
F_5 \sim N\left(\mathrm{vol}_{S^5}+\mathrm{vol}_{\mathrm{AdS}_5}\right),
$$

with a quantization condition fixing $N$. The positive curvature of $S^5$, negative curvature of AdS$_5$, and flux stress tensor together solve the type IIB equations.

For M-theory examples, one has analogous Freund-Rubin backgrounds such as

$$
\mathrm{AdS}_4\times S^7,
\qquad
\mathrm{AdS}_7\times S^4,
$$

supported by four-form flux $G_4$ or its dual.

The boundary rank parameter $N$ is usually a flux number. This is one reason large $N$ becomes a geometric limit.

## Supersymmetry and BPS protection

Supersymmetry is not required for the logical idea of holography, but it is extremely useful in controlled examples.

A BPS object is one that preserves some supersymmetry and saturates a mass/charge bound. For D-branes, BPS protection has several consequences:

- the brane tension and RR charge are related;
- forces between identical parallel BPS branes cancel;
- some quantities are protected against quantum corrections;
- strong-coupling extrapolations can be more trustworthy.

For the D3-brane stack, maximal supersymmetry helps make $\mathcal N=4$ SYM exactly conformal and makes the AdS$_5\times S^5$ background exceptionally symmetric.

But this course does not assume that every holographic model is supersymmetric. Many applications intentionally study nonsupersymmetric states, finite temperature, finite density, deformations, or bottom-up models.

## The tower of corrections

When a bulk calculation is performed using classical two-derivative Einstein gravity, several approximations have already been made.

The full hierarchy is roughly:

$$
\text{CFT}
\quad\leftrightarrow\quad
\text{quantum string theory on AdS}
\quad\to\quad
\text{classical string theory}
\quad\to\quad
\text{classical supergravity}
\quad\to\quad
\text{Einstein truncation}.
$$

The corrections are:

| correction | boundary meaning | bulk meaning |
|---|---|---|
| $1/N^2$ | non-planar corrections | quantum loops of bulk fields/strings |
| $1/\sqrt{\lambda}$ | finite-coupling corrections | $\alpha'$ / higher-derivative terms |
| KK modes | R-symmetry/internal dynamics | fields on compact space $X$ |
| string excitations | unprotected high-dimension single-trace operators | massive string tower |
| nonperturbative effects | finite-$N$ phenomena | D-branes, instantons, topology changes |

For AdS$_5\times S^5$, the mass scale of string excitations in AdS units is

$$
M_sL \sim \frac{L}{\ell_s}=\lambda^{1/4} .
$$

The corresponding single-trace operator dimensions are large when $\lambda\gg1$:

$$
\Delta_{\rm stringy} \sim \lambda^{1/4} .
$$

This is the origin of the large-gap condition used in discussions of local bulk effective field theory.

## Which string facts are used where?

| course topic | string-theory input |
|---|---|
| D3-brane origin | open/closed strings, D-branes, decoupling limit |
| parameter map | D3-brane flux quantization, $g_{\rm YM}^2\sim g_s$ |
| classical gravity limit | $1/N^2$ loops and $\alpha'/L^2$ corrections |
| Wilson loops | fundamental strings ending on boundary loops |
| flavor branes | probe D-branes with $N_f\ll N_c$ |
| entanglement and RT | Einstein gravity limit, $G_N$ normalization |
| finite-density models | bulk gauge fields from symmetries or branes |
| stringy corrections | higher-derivative terms and massive string modes |
| black-hole microphysics | finite $N$, D-brane states, quantum gravity corrections |

The important habit is to ask: **which approximation am I using?** A statement derived in two-derivative gravity may be universal in a class of holographic theories, but it is rarely universal across all quantum field theories.

## Common confusions

### “String theory is only used to motivate AdS/CFT.”

Not quite. The D3-brane argument motivates the canonical duality, but string theory also controls the parameter map, the spectrum of corrections, flux quantization, brane probes, Wilson loops, top-down consistency, and the meaning of finite $N$ and finite $\lambda$.

### “Large $N$ automatically gives Einstein gravity.”

Large $N$ suppresses bulk loops, but it does not by itself suppress stringy corrections. One also needs a large gap to stringy higher-spin states. In $\mathcal N=4$ SYM, this requires large $\lambda$.

### “D-branes are rigid surfaces.”

D-branes are dynamical objects. Their transverse positions become scalar fields on the worldvolume. A stack of coincident branes has matrix-valued position fields.

### “The $S^5$ can always be ignored.”

Only for some questions. The $S^5$ encodes R-symmetry and Kaluza-Klein towers. Many protected operators, selection rules, and correlation functions know about the internal space.

### “Small $g_s$ is the same as classical gravity.”

Small $g_s$ suppresses string splitting/joining in flat-space perturbation theory. In AdS/CFT, the clean bulk-loop parameter is $G_{d+1}/L^{d-1}\sim 1/N^2$. Curvature corrections are separately controlled by $\alpha'/L^2$.

### “Bottom-up models are string backgrounds.”

Not necessarily. A bottom-up action can be a useful effective model, but unless it is embedded in a UV-complete string construction, it should not automatically be treated as an exact holographic dual.

## Dictionary checkpoint

For quick reference:

| string/bulk object | CFT meaning |
|---|---|
| closed string | quantum gravity excitation |
| massless graviton | stress tensor sector |
| open strings on $N$ D-branes | $U(N)$ gauge theory degrees of freedom |
| D3-brane stack | $\mathcal N=4$ SYM / AdS$_5\times S^5$ source |
| RR flux number $N$ | gauge-group rank / central-charge scale |
| string length $\ell_s$ | inverse scale of stringy operator gap |
| string coupling $g_s$ | related to gauge coupling; controls string topology |
| $\alpha'$ corrections | finite-$\lambda$ corrections |
| string loops | finite-$N$ corrections |
| compact space $X$ | global symmetry and KK spectrum |
| fundamental string worldsheet | Wilson loop saddle |
| probe D-brane | flavor or defect sector |

## Quick checks

### Check 1: string scale versus AdS scale

In AdS$_5\times S^5$,

$$
\frac{L^4}{\alpha'^2}=\lambda .
$$

Show that the string mass scale in AdS units behaves as $M_sL\sim \lambda^{1/4}$.

<details>
<summary><strong>Solution</strong></summary>

The string mass scale is $M_s\sim 1/\ell_s=1/\sqrt{\alpha'}$. Therefore

$$
M_sL \sim \frac{L}{\sqrt{\alpha'}} .
$$

Using

$$
\frac{L^4}{\alpha'^2}=\lambda,
$$

we take the fourth root:

$$
\frac{L}{\sqrt{\alpha'}}=\lambda^{1/4} .
$$

Thus

$$
M_sL\sim\lambda^{1/4}.
$$

At large $\lambda$, string excitations are heavy in AdS units and can often be integrated out.

</details>

### Check 2: why D3-branes are conformal

The Yang-Mills coupling on a D$p$-brane has dimension

$$
[g_{\rm YM,p}^2]=3-p
$$

in mass units. Why is $p=3$ special?

<details>
<summary><strong>Solution</strong></summary>

For $p=3$,

$$
[g_{\rm YM,3}^2]=0.
$$

So the gauge coupling is dimensionless in four spacetime dimensions. This is a necessary condition for conformal invariance. The full statement for the D3-brane theory is stronger: maximal supersymmetry makes $\mathcal N=4$ SYM exactly conformal, with vanishing beta function.

For $p\ne3$, the gauge coupling is dimensionful, and the corresponding D$p$-brane worldvolume theories are not ordinary conformal field theories.

</details>

### Check 3: loop versus stringy corrections

Suppose $N\to\infty$ while $\lambda$ is held fixed and small. Which corrections are suppressed, and which are not?

<details>
<summary><strong>Solution</strong></summary>

Taking $N\to\infty$ suppresses non-planar corrections in the CFT and bulk quantum loops in the dual description:

$$
\frac{G_5}{L^3}\sim \frac{1}{N^2}\to0 .
$$

However, if $\lambda$ is fixed and small, then

$$
\frac{L^2}{\alpha'}=\sqrt{\lambda}
$$

is not large. The AdS radius is not large compared with the string length, so $\alpha'$ corrections and massive string states are not suppressed. The dual is not classical Einstein gravity. It is closer to a weakly coupled planar gauge theory, whose bulk description, if used, is highly stringy.

</details>

### Check 4: why $N$ is geometric

Use

$$
\frac{L^3}{G_5}=\frac{2N^2}{\pi}
$$

to explain why large $N$ is a semiclassical gravity limit.

<details>
<summary><strong>Solution</strong></summary>

Quantum gravitational fluctuations are controlled by the dimensionless Newton coupling in AdS units,

$$
\frac{G_5}{L^3} = \frac{\pi}{2N^2} .
$$

As $N\to\infty$, this ratio tends to zero. Equivalently, the gravitational action in units of $\hbar$ becomes large, so the saddle-point approximation becomes reliable. This is the bulk version of large-$N$ factorization in the boundary theory.

</details>

## Further reading

- J. Polchinski, [TASI Lectures on D-Branes](https://arxiv.org/abs/hep-th/9611050).
- J. Polchinski, [Dirichlet-Branes and Ramond-Ramond Charges](https://arxiv.org/abs/hep-th/9510017).
- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- C. P. Bachas, [Lectures on D-Branes](https://arxiv.org/abs/hep-th/9806199).
- E. Kiritsis, *String Theory in a Nutshell*, 2nd edition.
- J. Polchinski, *String Theory*, Volumes 1 and 2.
