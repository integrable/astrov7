---
title: "The Decoupling Limit"
description: "The low-energy D3-brane limit that separates flat-space gravity from the interacting sectors and leads to the equivalence between N=4 SYM and type IIB string theory on AdS5 x S5."
sidebar:
  order: 50
---

The previous page derived the most visible geometric fact behind the canonical duality: the near-horizon region of the extremal D3-brane solution is

$$
\mathrm{AdS}_5\times S^5.
$$

This page explains the more delicate physical step. We do not simply declare that the D3-brane throat is interesting. We take a limit in which the throat becomes an independent dynamical system, the asymptotically flat region becomes a decoupled free sector, and the open-string theory on the branes becomes four-dimensional $\mathcal N=4$ super-Yang–Mills theory.

The logic is:

$$
\text{one D3-brane system}
\quad\xrightarrow{\text{low-energy decoupling limit}}\quad
\begin{cases}
\mathcal N=4\;\text{SYM} + \text{free flat-space closed strings},\\
\text{IIB strings on }\mathrm{AdS}_5\times S^5 + \text{free flat-space closed strings}.
\end{cases}
$$

Since the same free flat-space sector appears on both sides, the nontrivial sectors are identified:

$$
\mathcal N=4\;SU(N)\;\text{SYM}
\quad\longleftrightarrow\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5.
$$

This is the D3-brane decoupling argument for AdS$_5$/CFT$_4$.

<figure class="doc-figure" style="--figure-width: 60rem;">

![D3-brane decoupling limit](/figures/course/d3-decoupling-limit.svg)

<figcaption>

The decoupling limit isolates the interacting low-energy sectors of one D3-brane system. In the open-string description, massive string modes and dynamical bulk gravity decouple, leaving $\mathcal N=4$ SYM on the branes plus a free flat-space closed-string sector. In the closed-string description, the near-horizon throat remains as type IIB string theory on $\mathrm{AdS}_5\times S^5$, while the same free asymptotically flat closed-string sector decouples. Removing this common free factor gives the canonical AdS$_5$/CFT$_4$ statement.

</figcaption>
</figure>

## Why this matters

The near-horizon metric alone does not yet give AdS/CFT. It only says that a region of the D3-brane supergravity solution looks like $\mathrm{AdS}_5\times S^5$. The duality requires a stronger statement: that the physics of this throat can be isolated, and that the isolated throat is equivalent to a non-gravitational quantum field theory.

The decoupling limit is the bridge between these claims.

It answers three questions at once.

First, why does the boundary theory not include ordinary four-dimensional gravity? Because the interactions between the brane degrees of freedom and the asymptotically flat ten-dimensional gravitons vanish in the low-energy limit.

Second, why is the bulk theory not the full asymptotically flat D3-brane spacetime? Because the near-horizon throat separates from the asymptotically flat region and becomes its own spacetime.

Third, why does the full string theory survive in the throat, even though we are taking a low-energy limit? Because the gravitational redshift down the throat keeps finite-energy throat excitations in the low-energy spectrum as measured from infinity. At finite $\lambda$, string-scale local physics in the throat is not thrown away; it becomes string theory on AdS.

That last point is easy to miss. The low-energy limit removes massive string modes from the flat-space open-string description, but it does not say that the AdS throat is automatically classical supergravity. Classical supergravity requires the additional conditions

$$
N\gg1,
\qquad
\lambda\gg1,
$$

with quantum and stringy corrections suppressed. The exact decoupled throat theory is type IIB string theory on $\mathrm{AdS}_5\times S^5$ with $N$ units of five-form flux.

## The full D3-brane system

Start with type IIB string theory in ten-dimensional asymptotically flat spacetime containing $N$ coincident D3-branes. The system has several kinds of degrees of freedom.

There are open strings ending on the branes. Their endpoints carry Chan–Paton labels, so for $N$ coincident branes their light modes are $N\times N$ matrix-valued fields living in the four D3-brane directions.

There are also closed strings moving in the ten-dimensional bulk. Their massless modes include the graviton, dilaton, antisymmetric tensor fields, and Ramond–Ramond fields.

Finally, open and closed strings interact. Open strings can join and split. Closed strings can be emitted by brane excitations. Closed strings can scatter off the branes. The full system is not initially a field theory by itself or a pure throat geometry by itself. It is one coupled string-theoretic system.

The decoupling limit isolates the low-energy physics of this system in two equivalent descriptions.

## The open-string low-energy limit

The open-string description is the most direct from the brane worldvolume point of view.

The string length is

$$
\ell_s=\sqrt{\alpha'}.
$$

Massive open-string oscillator modes have masses of order

$$
m_{\mathrm{open}}^2\sim \frac{1}{\alpha'}.
$$

At energies $E$ satisfying

$$
E\ell_s\ll1,
$$

only the massless open-string modes remain. Taking

$$
\alpha'\to0
$$

at fixed worldvolume energy $E$ makes this separation exact.

For a stack of D3-branes, the surviving open-string modes form the field content of four-dimensional $\mathcal N=4$ $U(N)$ super-Yang–Mills theory:

$$
A_\mu,
\qquad
\Phi^I\quad (I=1,\ldots,6),
\qquad
\text{fermions},
$$

all in the adjoint representation of $U(N)$.

The gauge coupling is held fixed. In the convention used throughout this course,

$$
g_{\mathrm{YM}}^2=4\pi g_s,
$$

so the open-string limit keeps

$$
g_{\mathrm{YM}}^2\;\text{fixed},
\qquad
N\;\text{fixed}.
$$

Equivalently, the 't Hooft coupling

$$
\lambda=g_{\mathrm{YM}}^2N
$$

is fixed. Later we may take $N$ and $\lambda$ large, but the decoupling limit itself is not the same thing as the classical gravity limit.

## Why bulk gravity decouples on the open-string side

The massless closed strings in the asymptotically flat bulk also survive as low-energy particles. Why do they not remain interacting with the D3-brane gauge theory?

The ten-dimensional gravitational coupling scales as

$$
2\kappa_{10}^2=(2\pi)^7g_s^2\alpha'^4.
$$

With $g_s$ fixed, taking $\alpha'\to0$ gives

$$
\kappa_{10}\to0.
$$

Thus the asymptotically flat closed-string sector becomes a free ten-dimensional bulk sector. Its interactions with itself vanish, and its interactions with the brane fields are suppressed by powers of the same gravitational coupling. Schematically,

$$
S_{\mathrm{low\;energy}}
\longrightarrow
S_{\mathcal N=4\;U(N)\;\mathrm{SYM}}
+
S_{\mathrm{free\;bulk}}.
$$

The $U(1)$ part of $U(N)$ describes the center-of-mass motion of the brane stack and is also free. The interacting worldvolume theory is usually taken to be the $SU(N)$ sector:

$$
U(N)\simeq \frac{SU(N)\times U(1)}{\mathbb Z_N},
\qquad
\text{interacting sector: } SU(N).
$$

This is why the canonical correspondence is usually written with $SU(N)$ $\mathcal N=4$ SYM. The free center-of-mass sector is harmless for most local observables and is omitted from the interacting AdS/CFT dictionary.

## The closed-string low-energy limit

Now describe the same D3-brane system from the closed-string geometry side.

The extremal D3-brane metric is

$$
ds^2
=
H(r)^{-1/2}dx_{1,3}^2
+
H(r)^{1/2}\left(dr^2+r^2d\Omega_5^2\right),
$$

with

$$
H(r)=1+\frac{L^4}{r^4},
\qquad
L^4=4\pi g_sN\alpha'^2.
$$

Using $g_{\mathrm{YM}}^2=4\pi g_s$, this becomes

$$
L^4=\lambda\alpha'^2.
$$

There are two kinds of low-energy closed-string excitations.

The first are ordinary massless closed strings far from the branes in the asymptotically flat region. These become the same free ten-dimensional bulk sector described above.

The second are excitations deep in the D3-brane throat. These remain in the low-energy spectrum because of gravitational redshift. For a static excitation at radius $r$,

$$
E_\infty=\sqrt{-g_{tt}(r)}\,E_{\mathrm{local}}
=H(r)^{-1/4}E_{\mathrm{local}}.
$$

In the near-horizon region,

$$
H(r)\simeq \frac{L^4}{r^4},
$$

so

$$
E_\infty\simeq \frac{r}{L}E_{\mathrm{local}}.
$$

As $r\to0$, finite local energies are redshifted to arbitrarily small energies as measured by the time coordinate at infinity. Therefore the low-energy closed-string limit keeps the near-horizon throat.

This is the closed-string counterpart of the open-string statement that the low-energy brane theory survives.

## The correct scaling variable: $U=r/\alpha'$

The decoupling limit is often written using the variable

$$
U=\frac{r}{\alpha'}.
$$

This is not a random change of notation. The quantity $U$ has dimensions of energy and has a direct open-string interpretation.

Imagine moving one D3-brane a distance $r$ away from the stack. An open string stretched between the separated brane and the stack has mass

$$
m_W=\frac{r}{2\pi\alpha'}.
$$

Thus, up to the conventional factor $2\pi$,

$$
U=\frac{r}{\alpha'}
$$

is the energy scale of a stretched-string excitation, or equivalently a W-boson mass on the Coulomb branch of the worldvolume gauge theory. Keeping $U$ fixed means keeping gauge-theory energy scales fixed while the string length goes to zero.

The D3-brane decoupling limit is therefore

$$
\boxed{
\alpha'\to0,
\qquad
U=\frac{r}{\alpha'}\;\text{fixed},
\qquad
g_{\mathrm{YM}}^2\;\text{fixed},
\qquad
N\;\text{fixed}.
}
$$

In this limit,

$$
r=\alpha' U\to0,
$$

so we zoom into the near-horizon region. But we do not merely set $r=0$. We keep the energy-like variable $U$ finite.

## The throat metric in the decoupling limit

Substitute

$$
r=\alpha' U,
\qquad
L^4=\lambda\alpha'^2
$$

into the harmonic function:

$$
H(r)
=
1+\frac{L^4}{r^4}
=
1+\frac{\lambda\alpha'^2}{\alpha'^4U^4}
=
1+\frac{\lambda}{\alpha'^2U^4}.
$$

As $\alpha'\to0$ at fixed $U$ and fixed $\lambda$,

$$
\frac{\lambda}{\alpha'^2U^4}\to\infty,
$$

so

$$
H(r)\simeq \frac{\lambda}{\alpha'^2U^4}.
$$

The constant $1$ in $H(r)$ disappears. This is the precise sense in which the asymptotically flat region is removed from the interacting sector.

Now divide the metric by $\alpha'$, which is the natural unit for the string worldsheet sigma model. Since

$$
H(r)^{-1/2}\simeq \frac{\alpha' U^2}{\sqrt\lambda},
\qquad
H(r)^{1/2}\simeq \frac{\sqrt\lambda}{\alpha' U^2},
$$

and

$$
dr=\alpha' dU,
$$

we find

$$
\frac{ds^2}{\alpha'}
=
\frac{U^2}{\sqrt\lambda}dx_{1,3}^2
+
\sqrt\lambda\frac{dU^2}{U^2}
+
\sqrt\lambda\,d\Omega_5^2.
$$

Equivalently, using

$$
z=\frac{\sqrt\lambda}{U},
$$

up to the same convention for $\lambda$, this becomes the Poincaré form

$$
ds^2
=
\frac{L^2}{z^2}\left(dz^2+dx_{1,3}^2\right)
+
L^2d\Omega_5^2,
$$

with

$$
\frac{L^2}{\alpha'}=\sqrt\lambda.
$$

Thus the decoupling limit does not give a small neighborhood of a horizon. It blows up the near-horizon region into a complete AdS throat measured in string units.

## Why string theory survives in the throat

A possible puzzle is now visible.

On the open-string side, massive open-string oscillators decouple because their masses scale like $1/\sqrt{\alpha'}$. Why do stringy excitations not also disappear from the throat?

The answer is that the throat has an infinite redshift. A local string-scale excitation has

$$
E_{\mathrm{local}}\sim \frac{1}{\sqrt{\alpha'}}.
$$

At radius

$$
r=\alpha'U,
$$

the near-horizon redshift gives

$$
E_\infty
\simeq
\frac{r}{L}E_{\mathrm{local}}
=
\frac{\alpha'U}{L}\frac{1}{\sqrt{\alpha'}}.
$$

Since

$$
L=\lambda^{1/4}\sqrt{\alpha'},
$$

we obtain

$$
E_\infty
\sim
\frac{U}{\lambda^{1/4}}.
$$

This is finite at fixed $U$ and fixed $\lambda$. Therefore string-scale local excitations in the throat remain as finite-energy states of the decoupled theory.

This is why the exact statement is not

$$
\mathcal N=4\;\mathrm{SYM}
\quad\longleftrightarrow\quad
\text{classical supergravity on }\mathrm{AdS}_5\times S^5.
$$

The exact statement is instead

$$
\mathcal N=4\;\mathrm{SYM}
\quad\longleftrightarrow\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5.
$$

Classical supergravity appears only after imposing the additional strong-coupling and large-$N$ conditions that suppress stringy and quantum corrections.

## The flat region separates

On the closed-string side, the low-energy spectrum contains both throat excitations and massless closed strings in the asymptotically flat region. Why do these two sectors decouple from one another?

One way to see the answer is geometric. The extremal D3-brane throat has infinite proper length in the near-horizon limit. Signals traveling between the asymptotically flat region and the deep throat are redshifted, and the low-energy absorption probability of a wave from the flat region into the throat is suppressed by positive powers of the energy.

For example, for low-frequency modes the absorption probability has the schematic form

$$
P_{\mathrm{abs}}\sim (\omega L)^p,
\qquad
p>0,
$$

with the precise power depending on the mode and angular momentum. In the decoupling limit, at fixed asymptotic energy $\omega$,

$$
\omega L
=
\omega\lambda^{1/4}\sqrt{\alpha'}
\to0.
$$

Thus the communication between the flat region and the throat shuts off. The closed-string low-energy limit becomes

$$
S_{\mathrm{closed,low\;energy}}
\longrightarrow
S_{\mathrm{IIB\;on\;}\mathrm{AdS}_5\times S^5}
+
S_{\mathrm{free\;bulk}}.
$$

The free bulk sector is the same sector that appeared on the open-string side.

## Equating the nontrivial sectors

We have now described the same low-energy limit in two languages.

The open-string description gives

$$
\text{full D3 system}
\quad\longrightarrow\quad
\mathcal N=4\;U(N)\;\text{SYM}
+
\text{free flat-space closed strings}.
$$

The closed-string description gives

$$
\text{full D3 system}
\quad\longrightarrow\quad
\text{IIB strings on }\mathrm{AdS}_5\times S^5
+
\text{free flat-space closed strings}.
$$

Since both limits come from the same original system, and since the free flat-space factor is common, the interacting sectors must be two descriptions of the same physics:

$$
\mathcal N=4\;U(N)\;\text{SYM, modulo its free center-of-mass sector}
\quad\longleftrightarrow\quad
\text{IIB strings on }\mathrm{AdS}_5\times S^5.
$$

Equivalently, for the interacting nonabelian theory,

$$
\boxed{
\mathcal N=4\;SU(N)\;\text{super-Yang–Mills}
\quad\longleftrightarrow\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5
\text{ with }N\text{ units of }F_5\text{ flux}.
}
$$

This is the canonical AdS$_5$/CFT$_4$ duality.

## What is fixed, and what can later be varied?

It is useful to separate the decoupling limit from the later approximation limits.

The decoupling limit keeps

$$
g_{\mathrm{YM}}^2,
\qquad
N,
\qquad
U=\frac{r}{\alpha'}
$$

fixed while sending $\alpha'\to0$. This produces the exact proposed dual pair.

After this, one can choose a regime of the duality.

At fixed $N$ and fixed $\lambda$, the bulk description is full type IIB string theory on a curved background with radius

$$
\frac{L^2}{\alpha'}=\sqrt\lambda.
$$

If

$$
\lambda\gg1,
$$

then the curvature radius is large in string units, and $\alpha'$ corrections are suppressed.

If

$$
N\gg1,
$$

then bulk quantum loops are suppressed. More precisely, the five-dimensional gravitational coupling satisfies

$$
\frac{L^3}{G_5}\sim N^2,
$$

so classical gravity is the leading term in a $1/N$ expansion.

The familiar classical supergravity regime is therefore

$$
N\gg1,
\qquad
\lambda\gg1.
$$

If one also wants weak ten-dimensional string perturbation theory, one asks for

$$
g_s\sim\frac{\lambda}{N}\ll1.
$$

These are not assumptions of the exact duality. They are assumptions that make the bulk easy to compute with.

## Why D3-branes are special

The same logic can be applied to D$p$-branes, but D3-branes are special because their worldvolume Yang–Mills coupling is dimensionless.

For D$p$-branes, the Yang–Mills coupling has schematic dimension

$$
[g_{\mathrm{YM}}^2]=\text{length}^{p-3}.
$$

Only for $p=3$ is it dimensionless. This is one reason the D3-brane low-energy theory can be conformal, and why the near-horizon geometry is exactly AdS$_5\times S^5$ rather than a more general domain-wall-like geometry with a running effective coupling.

For $p\ne3$, decoupling limits still exist and are extremely important, but the resulting theories are generally nonconformal. Their gravitational descriptions are not simply AdS spaces in the same way. This course focuses first on the D3-brane case because it gives the cleanest realization of holography.

## The UV/IR lesson in the decoupling limit

The variable

$$
U=\frac{r}{\alpha'}
$$

has the interpretation of an energy scale. Since

$$
z=\frac{L^2}{r}
=
\frac{\sqrt\lambda}{U},
$$

large $U$ corresponds to small $z$, near the AdS boundary:

$$
U\to\infty
\quad\Longleftrightarrow\quad
z\to0.
$$

Small $U$ corresponds to large $z$, deep in the bulk:

$$
U\to0
\quad\Longleftrightarrow\quad
z\to\infty.
$$

Thus the decoupling limit already contains the first version of the holographic UV/IR relation:

$$
\text{high field-theory energy}
\quad\longleftrightarrow\quad
\text{near the AdS boundary},
$$

and

$$
\text{low field-theory energy}
\quad\longleftrightarrow\quad
\text{deep interior of AdS}.
$$

This statement will become more precise when we introduce holographic renormalization. For now, $U$ is the cleanest way to see why the radial coordinate is tied to gauge-theory energy.

## The role of the AdS boundary

Before the decoupling limit, the D3-brane geometry has an ordinary asymptotically flat infinity at $r\to\infty$.

After the decoupling limit, the isolated throat has an AdS conformal boundary. This boundary is not the same physical region as the original flat-space infinity. It is the upper end of the throat after the zoom.

This point is worth repeating because it prevents a persistent confusion:

$$
\text{original flat infinity}
\ne
\text{AdS conformal boundary of the decoupled throat}.
$$

The original flat-space modes form a free sector and are discarded from the interacting duality. The CFT is associated with boundary conditions at the conformal boundary of the isolated AdS throat.

This is why the duality is not a statement about a brane sitting inside a larger ten-dimensional laboratory. It is a statement about the autonomous low-energy theory obtained after the decoupling limit.

## A compact derivation

The whole argument can be compressed into the following chain.

On the open-string side,

$$
\alpha'\to0,
\qquad
E\sqrt{\alpha'}\to0
$$

removes massive string modes. At fixed $g_{\mathrm{YM}}^2$ and fixed $N$, the brane worldvolume theory becomes

$$
\mathcal N=4\;U(N)\;\mathrm{SYM},
$$

while ten-dimensional gravity becomes free because

$$
\kappa_{10}^2\sim g_s^2\alpha'^4\to0.
$$

On the closed-string side,

$$
r=\alpha'U,
\qquad
U\;\text{fixed}
$$

zooms into the D3-brane throat. The metric becomes

$$
\frac{ds^2}{\alpha'}
=
\frac{U^2}{\sqrt\lambda}dx_{1,3}^2
+
\sqrt\lambda\frac{dU^2}{U^2}
+
\sqrt\lambda d\Omega_5^2,
$$

which is $\mathrm{AdS}_5\times S^5$ in string units. The flat-space closed-string sector decouples from the throat.

Therefore,

$$
\mathcal N=4\;SU(N)\;\mathrm{SYM}
\quad\longleftrightarrow\quad
\text{IIB strings on }\mathrm{AdS}_5\times S^5.
$$

## Dictionary checkpoint

The decoupling limit gives the following translations.

$$
\alpha'\to0,\quad g_{\mathrm{YM}}^2\text{ fixed}
\quad\longrightarrow\quad
\text{massive open strings decouple from the brane theory}.
$$

$$
\kappa_{10}^2\sim g_s^2\alpha'^4\to0
\quad\longrightarrow\quad
\text{asymptotically flat bulk gravity becomes a free sector}.
$$

$$
U=\frac{r}{\alpha'}\text{ fixed}
\quad\longrightarrow\quad
\text{near-horizon throat retained at finite gauge-theory energy}.
$$

$$
H(r)=1+\frac{L^4}{r^4}
\quad\longrightarrow\quad
H(r)\simeq \frac{L^4}{r^4}
\quad\longrightarrow\quad
\mathrm{AdS}_5\times S^5.
$$

$$
\text{free flat-space closed strings on both sides}
\quad\longrightarrow\quad
\text{discard common decoupled sector}.
$$

$$
\mathcal N=4\;SU(N)\;\mathrm{SYM}
\quad\longleftrightarrow\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5.
$$

## Common confusions

### “The decoupling limit is just the near-horizon approximation.”

Not quite. The near-horizon approximation is the geometric step $r\ll L$, where $H(r)\simeq L^4/r^4$. The decoupling limit is a physical scaling limit:

$$
\alpha'\to0,
\qquad
U=\frac{r}{\alpha'}\;\text{fixed}.
$$

It explains why the near-horizon region becomes an autonomous theory and why the asymptotically flat region decouples.

### “Since $\alpha'\to0$, the bulk cannot contain string theory.”

The flat-space massive string modes decouple at fixed asymptotic energy, but throat string modes are redshifted. At finite $\lambda$, local string excitations in the throat have finite boundary energy. The decoupled bulk theory is type IIB string theory on AdS, not automatically classical supergravity.

### “The field theory is dual to the entire D3-brane geometry.”

No. The field theory is dual to the isolated near-horizon throat. The full asymptotically flat D3-brane spacetime contains an extra flat-space sector that decouples in the limit.

### “The AdS boundary is where the original branes sit.”

No. The branes sit at $r=0$ in the original transverse coordinates, which maps to the Poincaré horizon $z=\infty$ of the throat. The AdS boundary $z=0$ is the upper end of the isolated throat after the decoupling zoom.

### “Large $N$ is part of the decoupling limit.”

Not necessarily. The decoupling limit defines the exact dual pair. Large $N$ is a later approximation that suppresses bulk quantum loops. Large $\lambda$ is another later approximation that suppresses stringy curvature corrections.

### “The $U(1)$ part of $U(N)$ is the interesting holographic theory.”

The overall $U(1)$ describes the free center-of-mass motion of the brane stack. The interacting holographic theory is the nonabelian $SU(N)$ sector. This is why the canonical boundary theory is usually written as $\mathcal N=4$ $SU(N)$ SYM.

## Exercises

### Exercise 1: Massive open strings decouple

A massive open-string oscillator has

$$
m^2\sim \frac{1}{\alpha'}.
$$

Show that at fixed field-theory energy $E$, such a state decouples as $\alpha'\to0$.

<details>
<summary><strong>Solution</strong></summary>

The relevant dimensionless ratio is

$$
\frac{E}{m}\sim E\sqrt{\alpha'}.
$$

At fixed $E$,

$$
E\sqrt{\alpha'}\to0
$$

as $\alpha'\to0$. Therefore massive open-string oscillators become infinitely heavy relative to the energies kept in the low-energy theory. Only the massless open-string modes remain, giving the worldvolume gauge theory.

</details>

### Exercise 2: The ten-dimensional gravitational coupling

Use

$$
2\kappa_{10}^2=(2\pi)^7g_s^2\alpha'^4
$$

and fixed $g_s$ to show that ten-dimensional gravitational interactions vanish in the open-string decoupling limit.

<details>
<summary><strong>Solution</strong></summary>

At fixed $g_s$,

$$
\kappa_{10}^2\propto \alpha'^4.
$$

Thus

$$
\lim_{\alpha'\to0}\kappa_{10}^2=0.
$$

Gravitational interactions in the asymptotically flat bulk are controlled by powers of $\kappa_{10}$. Therefore the bulk closed-string sector becomes free and decouples from the brane theory in the low-energy limit.

</details>

### Exercise 3: Derive the decoupled throat metric

Start from

$$
ds^2
=
H^{-1/2}dx_{1,3}^2
+
H^{1/2}(dr^2+r^2d\Omega_5^2),
$$

where

$$
H(r)=1+\frac{L^4}{r^4},
\qquad
L^4=\lambda\alpha'^2.
$$

Set $r=\alpha'U$ and take $\alpha'\to0$ at fixed $U$ and fixed $\lambda$. Show that

$$
\frac{ds^2}{\alpha'}
=
\frac{U^2}{\sqrt\lambda}dx_{1,3}^2
+
\sqrt\lambda\frac{dU^2}{U^2}
+
\sqrt\lambda d\Omega_5^2.
$$

<details>
<summary><strong>Solution</strong></summary>

With $r=\alpha'U$,

$$
H(r)
=
1+\frac{\lambda\alpha'^2}{\alpha'^4U^4}
=
1+\frac{\lambda}{\alpha'^2U^4}.
$$

As $\alpha'\to0$,

$$
H(r)\simeq \frac{\lambda}{\alpha'^2U^4}.
$$

Therefore

$$
H^{-1/2}\simeq \frac{\alpha'U^2}{\sqrt\lambda},
\qquad
H^{1/2}\simeq \frac{\sqrt\lambda}{\alpha'U^2}.
$$

Also,

$$
dr=\alpha'dU.
$$

Then

$$
\frac{1}{\alpha'}H^{-1/2}dx_{1,3}^2
=
\frac{U^2}{\sqrt\lambda}dx_{1,3}^2,
$$

and

$$
\frac{1}{\alpha'}H^{1/2}dr^2
=
\frac{1}{\alpha'}\frac{\sqrt\lambda}{\alpha'U^2}\alpha'^2dU^2
=
\sqrt\lambda\frac{dU^2}{U^2}.
$$

Finally,

$$
\frac{1}{\alpha'}H^{1/2}r^2d\Omega_5^2
=
\frac{1}{\alpha'}\frac{\sqrt\lambda}{\alpha'U^2}\alpha'^2U^2d\Omega_5^2
=
\sqrt\lambda d\Omega_5^2.
$$

Combining the three terms gives the desired metric.

</details>

### Exercise 4: Why $U$ has dimensions of energy

A string stretched a distance $r$ has tension

$$
T_s=\frac{1}{2\pi\alpha'}.
$$

Show that its mass is proportional to $U=r/\alpha'$.

<details>
<summary><strong>Solution</strong></summary>

The mass of a stretched string is tension times length:

$$
m=T_sr
=
\frac{r}{2\pi\alpha'}.
$$

Using

$$
U=\frac{r}{\alpha'},
$$

we get

$$
m=\frac{U}{2\pi}.
$$

Thus $U$ is an energy scale up to the conventional factor $2\pi$. This is why keeping $U$ fixed is natural from the gauge-theory point of view.

</details>

### Exercise 5: String-scale throat excitations remain finite

A local string-scale excitation has

$$
E_{\mathrm{local}}\sim \frac{1}{\sqrt{\alpha'}}.
$$

Using

$$
E_\infty\simeq \frac{r}{L}E_{\mathrm{local}},
\qquad
r=\alpha'U,
\qquad
L=\lambda^{1/4}\sqrt{\alpha'},
$$

show that $E_\infty$ remains finite at fixed $U$ and $\lambda$.

<details>
<summary><strong>Solution</strong></summary>

Substitute the scalings:

$$
E_\infty
\simeq
\frac{\alpha'U}{\lambda^{1/4}\sqrt{\alpha'}}\frac{1}{\sqrt{\alpha'}}.
$$

The factors of $\alpha'$ cancel:

$$
E_\infty
\simeq
\frac{U}{\lambda^{1/4}}.
$$

At fixed $U$ and fixed $\lambda$, this is finite. Therefore string-scale local excitations in the throat are not removed by the decoupling limit. They become part of type IIB string theory on $\mathrm{AdS}_5\times S^5$.

</details>

## Further reading

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- J. Polchinski, [TASI Lectures on D-Branes](https://arxiv.org/abs/hep-th/9611050).
- J. Polchinski, [Introduction to Gauge/Gravity Duality](https://arxiv.org/abs/1010.6134).
- N. Itzhaki, J. Maldacena, J. Sonnenschein, and S. Yankielowicz, [Supergravity and the Large $N$ Limit of Theories with Sixteen Supercharges](https://arxiv.org/abs/hep-th/9802042).

The next page collects the parameter map of the duality: how $N$, $\lambda$, $g_s$, $\alpha'$, $L$, $G_{10}$, and $G_5$ translate between the gauge theory and the bulk.
