---
title: "Why Classical Gravity Emerges"
description: "How large N and large coupling turn quantum string theory in AdS into classical supergravity."
sidebar:
  order: 70
---

The previous pages derived the canonical D3-brane parameter map

$$
g_{\mathrm{YM}}^2=4\pi g_s,
\qquad
\lambda=g_{\mathrm{YM}}^2N=4\pi g_sN,
\qquad
\frac{L^4}{\alpha'^2}=\lambda.
$$

This page explains why that map leads to classical gravity in a special corner of parameter space.

The exact AdS$_5$/CFT$_4$ statement is not

$$
\text{CFT}=\text{classical Einstein gravity}.
$$

It is instead

$$
\mathcal N=4\;SU(N)\;\text{super-Yang–Mills}
\quad\longleftrightarrow\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5.
$$

Classical gravity emerges only after two different effects become small:

$$
\frac{G_5}{L^3}\sim \frac{1}{N^2},
\qquad
\frac{\alpha'}{L^2}=\frac{1}{\sqrt{\lambda}}.
$$

The first ratio controls bulk quantum loops. The second controls string-scale corrections to point-particle gravity. Thus the familiar classical-supergravity regime is

$$
N\gg1,
\qquad
\lambda\gg1,
\qquad
g_s=\frac{\lambda}{4\pi N}\ll1.
$$

A clean weakly coupled type IIB supergravity window is

$$
1\ll\lambda\ll N.
$$

The exact duality is much larger than this window. Finite $N$ and finite $\lambda$ correspond to quantum string theory in AdS, not to a classical metric.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Regimes in which large N and large lambda suppress quantum loops and stringy corrections.](/figures/course/classical-gravity-emergence.svg)

<figcaption>

Classical gravity is a controlled corner of the exact AdS$_5$/CFT$_4$ duality. Large $N$ suppresses bulk loops through $G_5/L^3\sim N^{-2}$. Large $\lambda$ makes the AdS radius large compared with the string length, $L/\ell_s=\lambda^{1/4}$, suppressing $\alpha'$ corrections. Keeping $g_s=\lambda/(4\pi N)$ small gives weakly coupled type IIB supergravity on $\mathrm{AdS}_5\times S^5$.

</figcaption>
</figure>

## Why this matters

Most practical uses of holography begin by solving classical equations of motion in a curved spacetime. One solves Einstein's equation for a black brane, a Maxwell equation for a bulk gauge field, or a scalar wave equation in AdS. It is easy to forget how dramatic this is.

The boundary theory is a quantum field theory. It has no dynamical spacetime metric. It is usually strongly coupled in the regime where gravity is useful. Yet the dual calculation can reduce to a classical boundary-value problem.

That simplification is not magic. It is a saddle-point approximation. The CFT has many degrees of freedom, and the bulk action becomes large in AdS units. At the same time, the AdS curvature becomes small compared with the string scale.

Schematically,

$$
Z_{\mathrm{CFT}}[J]
=
Z_{\mathrm{string}}[J]
\longrightarrow
Z_{\mathrm{sugra}}[J]
\approx
\exp\left(-S_{\text{sugra,ren,on-shell}}[J]\right).
$$

The arrow to $Z_{\mathrm{sugra}}$ uses large $\lambda$. The saddle-point approximation uses large $N$.

## The exact theory first

Before taking limits, the bulk dual is full type IIB string theory. That means it includes:

- closed strings, whose massless modes include the graviton;
- massive string oscillator modes;
- Ramond–Ramond fields, including the self-dual five-form flux;
- D-branes and other extended objects;
- quantum corrections, including string loops;
- possible sums over bulk topologies, whenever such a formulation is meaningful.

The boundary theory is the quantum CFT. The rank $N$ is the number of five-form flux units through the $S^5$:

$$
\int_{S^5} F_5 \propto N.
$$

The exact duality is therefore a statement about quantum gravity. Classical supergravity is an approximation to this exact theory, not a replacement for it.

This distinction matters. Many famous holographic formulas are leading terms in an expansion. When we compute an area, an on-shell action, or a classical wave equation, we are usually keeping the leading large-$N$, large-$\lambda$ answer.

## Large $N$ suppresses bulk quantum loops

The first emergence mechanism is large-$N$ factorization.

For normalized single-trace operators, the connected correlators have the schematic scaling

$$
\langle \mathcal O_1\mathcal O_2\rangle_c \sim N^0,
$$

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle_c \sim \frac{1}{N},
$$

and more generally

$$
\langle \mathcal O_1\cdots\mathcal O_k\rangle_c\sim N^{2-k}.
$$

The precise powers depend on normalization conventions, but the physical message is robust: connected higher-point interactions become weak. If single-trace operators create single-particle bulk states, then large-$N$ factorization says that bulk particles interact weakly.

The same statement appears in the gravitational action. A five-dimensional Einstein-like action has the form

$$
S_{\mathrm{grav}}
=
\frac{1}{16\pi G_5}
\int d^5x\sqrt{-g}\left(R+\frac{12}{L^2}+\cdots\right).
$$

A classical AdS-scale solution has a dimensionless action of order

$$
S_{\text{on-shell}}\sim \frac{L^3}{G_5}.
$$

For AdS$_5$/CFT$_4$,

$$
\frac{L^3}{G_5}=\frac{2N^2}{\pi}
$$

in the standard normalization. Thus the bulk path integral looks like

$$
Z_{\mathrm{bulk}}
\sim
\int \mathcal D\Phi\;\exp\left(-N^2 I[\Phi]\right)
$$

in Euclidean signature. The large-$N$ limit is a stationary-phase limit. The effective bulk Planck constant scales as

$$
\hbar_{\mathrm{bulk,eff}}\sim \frac{G_5}{L^3}\sim\frac{1}{N^2}.
$$

So large $N$ makes the bulk semiclassical.

## Deriving the $N^2$ gravitational prefactor

The $N^2$ scaling can be seen directly from the ten-dimensional parameters. Type IIB Newton's constant scales as

$$
G_{10}\sim g_s^2\alpha'^4.
$$

The D3-brane radius relation gives

$$
L^4\sim g_sN\alpha'^2.
$$

Squaring this relation gives

$$
L^8\sim g_s^2N^2\alpha'^4.
$$

Therefore

$$
\frac{L^8}{G_{10}}\sim N^2.
$$

Reducing on the $S^5$, whose volume is of order $L^5$, gives

$$
G_5\sim \frac{G_{10}}{L^5},
\qquad
\frac{L^3}{G_5}\sim \frac{L^8}{G_{10}}\sim N^2.
$$

This is the gravitational origin of the $N^2$ scaling of central charges, free energies, and entropy densities in the adjoint gauge theory.

For example, the entropy density of the strongly coupled thermal CFT is computed by a black-brane horizon area:

$$
s\sim \frac{L^3}{G_5}T^3\sim N^2T^3.
$$

The power $T^3$ follows from four-dimensional conformal invariance. The coefficient is dynamical, but the $N^2$ scaling is already visible from the classical gravitational prefactor.

## Large $\lambda$ suppresses stringy corrections

Large $N$ suppresses loops, but it does not make the bulk weakly curved. The second requirement is large 't Hooft coupling.

From

$$
\frac{L^4}{\alpha'^2}=\lambda
$$

we get

$$
\frac{L}{\ell_s}=\lambda^{1/4},
\qquad
\frac{\alpha'}{L^2}=\lambda^{-1/2},
$$

where $\ell_s=\sqrt{\alpha'}$.

The curvature scale of $\mathrm{AdS}_5\times S^5$ is of order $1/L^2$. Stringy corrections compare the string length to this curvature radius:

$$
\alpha' R \sim \frac{\alpha'}{L^2}=\frac{1}{\sqrt{\lambda}}.
$$

Thus:

- if $\lambda\ll1$, the gauge theory may be perturbative, but the bulk is highly stringy;
- if $\lambda\sim1$, neither perturbative Yang–Mills nor classical supergravity is generally reliable;
- if $\lambda\gg1$, the bulk is weakly curved in string units.

This is one of the central reversals in AdS/CFT:

$$
\text{strong boundary 't Hooft coupling}
\quad\longleftrightarrow\quad
\text{weakly curved bulk geometry}.
$$

The gravitational description is useful precisely where ordinary gauge-theory perturbation theory is least useful.

## The stringy gap

The same statement can be phrased in spectral language. A massive string oscillator has mass of order

$$
m_s\sim \frac{1}{\ell_s}.
$$

In AdS units,

$$
m_sL\sim \frac{L}{\ell_s}=\lambda^{1/4}.
$$

For a heavy bulk field, the dual CFT operator dimension is roughly

$$
\Delta\sim mL.
$$

Therefore stringy single-trace operators acquire dimensions of order

$$
\Delta_{\mathrm{stringy}}\sim \lambda^{1/4}.
$$

At large $\lambda$, these stringy operators move far above the low-dimension spectrum. The low-energy bulk theory can then be described by supergravity fields rather than by the full tower of string excitations.

This is the CFT-side signature of a local bulk effective field theory: there is a large gap to stringy higher-spin single-trace operators.

## The role of the string coupling

One might guess that the classical gravity limit is simply $g_s\to0$. That is incomplete.

The string coupling is

$$
g_s=\frac{\lambda}{4\pi N}.
$$

Taking $N\to\infty$ with fixed $\lambda$ sends $g_s\to0$, so it suppresses string loops. But the curvature in string units is controlled by $\lambda$, not by $g_s$:

$$
\frac{\ell_s}{L}=\lambda^{-1/4}.
$$

Thus a theory can have very small $g_s$ and still be highly stringy if $\lambda$ is not large.

Conversely, if $\lambda$ is made large at fixed $N$, the curvature becomes weak in string units, but

$$
g_s=\frac{\lambda}{4\pi N}
$$

may become large. Then quantum string effects are not suppressed in the usual perturbative string expansion.

The safest beginner hierarchy is therefore

$$
1\ll\lambda\ll N.
$$

The first inequality makes the geometry smooth in string units. The second keeps the string coupling small.

## Classical string theory versus classical gravity

The hierarchy of descriptions is worth making explicit.

### 1. Full quantum string theory

For finite $N$ and finite $\lambda$, the dual bulk is quantum type IIB string theory on $\mathrm{AdS}_5\times S^5$. This is the exact but generally difficult description.

### 2. Classical string theory

In the planar limit

$$
N\to\infty,
\qquad
\lambda\;\text{fixed},
$$

string loops are suppressed because $g_s\sim\lambda/N\to0$. The bulk becomes classical in the genus expansion.

But if $\lambda$ is not large, the curvature radius is comparable to the string length. The bulk is tree-level string theory in a curved Ramond–Ramond background, not ordinary supergravity.

### 3. Classical supergravity

When

$$
N\gg1,
\qquad
\lambda\gg1,
$$

bulk loops and stringy corrections are both suppressed. The leading bulk dynamics is classical type IIB supergravity.

This is the regime behind the simplest holographic calculations of two-point functions, thermodynamics, Wilson loops at strong coupling, and black-brane transport.

### 4. Einstein-like truncations

Type IIB supergravity on $\mathrm{AdS}_5\times S^5$ is ten-dimensional. A five-dimensional Einstein gravity model is an additional truncation.

The $S^5$ radius equals the AdS radius:

$$
L_{S^5}=L_{\mathrm{AdS}}.
$$

Therefore Kaluza–Klein modes on $S^5$ have masses

$$
m_{\mathrm{KK}}L\sim1,
$$

not masses of order $\lambda^{1/4}$. They do not decouple simply because $\lambda$ is large. They are dual to protected operators in the CFT.

Pure five-dimensional Einstein gravity can still be a consistent and useful sector, especially for universal stress-tensor observables. But it is not the whole classical limit of the canonical duality.

## A saddle-point derivation of classical equations

The emergence of classical equations can be seen directly from the path integral. Suppose a bulk field $\phi$ is dual to a CFT operator $\mathcal O$, and the boundary value of $\phi$ is the source $J$.

The bulk partition function is schematically

$$
Z_{\mathrm{bulk}}[J]
=
\int_{\phi\to J}\mathcal D\phi\;e^{-S[\phi]}.
$$

If

$$
S[\phi]=N^2 I[\phi],
$$

then at large $N$ the integral is dominated by stationary points:

$$
\frac{\delta I}{\delta\phi}=0.
$$

Thus the leading answer comes from solving the classical bulk equation of motion with boundary condition $\phi\to J$.

Expanding around a solution,

$$
\phi=\phi_{\mathrm{cl}}+\delta\phi,
$$

one obtains a loop expansion. After canonically normalizing fluctuations, cubic bulk interactions scale as $1/N$, quartic interactions scale as $1/N^2$, and loops are suppressed by powers of $1/N^2$.

This is the bulk counterpart of large-$N$ factorization in the CFT.

## What the CFT sees

A CFT with a simple classical gravity dual has several characteristic features.

First, it has many degrees of freedom. In four-dimensional $\mathcal N=4$ SYM,

$$
a=c=\frac{N^2-1}{4}.
$$

Holographically,

$$
a=c=\frac{\pi L^3}{8G_5}.
$$

Thus large central charge means a small Newton constant in AdS units.

Second, connected correlators of normalized single-trace operators factorize at large $N$:

$$
\langle \mathcal O_1\cdots\mathcal O_k\rangle_c\sim N^{2-k}.
$$

Third, the spectrum is sparse at low dimensions compared with the string scale. A large gap to higher-spin single-trace operators is what allows a local low-energy bulk derivative expansion.

These features are diagnostics, not a mechanical algorithm. They explain why not every large-$N$ theory has a simple Einstein gravity dual.

## What does emergence mean here?

The phrase "gravity emerges" is useful, but it should not be overinterpreted.

It does not mean that the CFT first lives on the boundary of a pre-existing bulk spacetime and then emits a gravitational field into the interior. The CFT is a complete quantum system. In a suitable limit, some collective variables of that system are reorganized as fields propagating in an emergent higher-dimensional geometry.

It also does not mean that the boundary theory becomes classical. The CFT remains a quantum theory. The classical approximation appears in the bulk variables because the bulk action has a large prefactor of order $N^2$.

A good slogan is

$$
\text{many quantum degrees of freedom}
+
\text{large gap}
\quad\Longrightarrow\quad
\text{classical local bulk EFT}.
$$

In the D3-brane example, "many degrees of freedom" means $N^2\gg1$, and the stringy gap is controlled by $\lambda^{1/4}$.

## Correction dictionary

Classical supergravity is the leading term in a double expansion. A typical large-$N$, strong-coupling observable has the schematic form

$$
\mathcal Q(N,\lambda)
=
\mathcal Q_{\mathrm{sugra}}
+\mathcal Q_{\alpha'}
+\mathcal Q_{\mathrm{loops}}
+\cdots.
$$

The terms have different physical origins:

| Boundary correction | Bulk interpretation |
|---|---|
| finite $\lambda$ | stringy $\alpha'$ corrections |
| finite $N$ | bulk quantum loops |
| non-planar gauge-theory effects | higher-genus string contributions |
| anomalous dimensions of stringy operators | masses of string excitations in AdS units |
| large central charge | small Newton constant in AdS units |

For type IIB string theory on $\mathrm{AdS}_5\times S^5$, maximal supersymmetry forbids some lower-order higher-derivative corrections. A famous leading correction in the ten-dimensional effective action is schematically

$$
\alpha'^3 R^4.
$$

Since $R\sim1/L^2$, such terms often produce corrections of order

$$
\left(\frac{\alpha'}{L^2}\right)^3\sim\lambda^{-3/2}
$$

for many observables. The exact first correction depends on the observable, but the organizing principle is always the same: finite $\lambda$ is finite string length.

## Example: why perturbative Yang–Mills and classical gravity do not overlap

The perturbative gauge-theory regime is

$$
\lambda\ll1.
$$

The classical supergravity regime is

$$
\lambda\gg1.
$$

Therefore ordinary perturbative Yang–Mills and classical Einstein gravity are opposite limits of the same exact duality.

This is why AdS/CFT is useful: it gives a weakly coupled description of strongly coupled physics. It is also why the duality is hard to prove directly. The simplest calculations on one side usually correspond to hard calculations on the other side.

The planar limit alone does not remove this tension. Taking

$$
N\to\infty,
\qquad
\lambda\ll1
$$

gives planar perturbative gauge theory, not classical supergravity. The dual bulk is still string-scale curved.

## Example: why black-brane entropy scales as $N^2$

A planar AdS$_5$ black brane has entropy density

$$
s=\frac{\text{horizon area density}}{4G_5}.
$$

Dimensional analysis in a four-dimensional CFT gives

$$
s\propto \frac{L^3}{G_5}T^3.
$$

Using

$$
\frac{L^3}{G_5}\sim N^2,
$$

we find

$$
s\sim N^2T^3.
$$

This matches the expectation that a deconfined adjoint gauge theory has order $N^2$ degrees of freedom. The numerical coefficient differs from the weak-coupling free gas result, but the scaling is the same.

## Dictionary checkpoint

| Boundary statement | Bulk statement |
|---|---|
| $N\gg1$ | bulk loops are suppressed |
| $1/N^2$ expansion | quantum gravity loop expansion |
| large central charge $C_T$ | small $G_N/L^{d-1}$ |
| large-$N$ factorization | weakly interacting bulk particles |
| $\lambda\gg1$ | weak curvature in string units |
| $1/\sqrt\lambda$ expansion | stringy $\alpha'$ expansion |
| large stringy gap $\Delta_{\mathrm{gap}}$ | local bulk EFT below the string scale |
| planar limit at fixed $\lambda$ | tree-level string theory, not necessarily supergravity |
| large $N$, large $\lambda$, small $g_s$ | classical type IIB supergravity |

The most important takeaway is

$$
\boxed{
\text{AdS/CFT is exact quantum/string duality; classical gravity is a controlled corner.}
}
$$

## Common confusions

### "Large $N$ is the same as classical gravity."

Not quite. Large $N$ suppresses bulk loops. It does not suppress string-scale curvature corrections. At large $N$ and finite $\lambda$, the bulk is better described as tree-level string theory, not necessarily supergravity.

### "Strong coupling is the same as classical gravity."

Also not quite. Large $\lambda$ suppresses stringy corrections, but if $N$ is not large, quantum gravity effects can still be important.

### "Einstein gravity is the whole duality."

No. The exact dual is quantum string theory. Classical Einstein gravity, or a five-dimensional Einstein truncation, is a leading approximation in a restricted sector.

### "The boundary theory becomes classical."

No. The boundary CFT remains quantum. Classicality appears in the bulk variables because the large-$N$ gravitational action is dominated by saddle points.

### "The $S^5$ can always be ignored."

No. In the canonical example the $S^5$ has the same radius as AdS$_5$. Its Kaluza–Klein modes are part of the ten-dimensional supergravity spectrum. Ignoring them is an additional truncation, not a consequence of $\lambda\gg1$.

## Exercises

### Exercise 1: Derive $L^3/G_5=2N^2/\pi$

Use

$$
G_{10}=8\pi^6g_s^2\alpha'^4,
\qquad
\mathrm{Vol}(S^5)=\pi^3L^5,
\qquad
G_5=\frac{G_{10}}{\mathrm{Vol}(S^5)},
$$

and

$$
L^4=4\pi g_sN\alpha'^2
$$

to show that

$$
\frac{L^3}{G_5}=\frac{2N^2}{\pi}.
$$

<details>
<summary><strong>Solution</strong></summary>

First reduce Newton's constant on $S^5$:

$$
G_5
=
\frac{G_{10}}{\pi^3L^5}
=
\frac{8\pi^6g_s^2\alpha'^4}{\pi^3L^5}
=
\frac{8\pi^3g_s^2\alpha'^4}{L^5}.
$$

Therefore

$$
\frac{L^3}{G_5}
=
\frac{L^8}{8\pi^3g_s^2\alpha'^4}.
$$

Now square the D3-brane radius relation:

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

Thus the inverse gravitational coupling in AdS units scales like $N^2$.

</details>

### Exercise 2: Estimate the stringy gap

Use

$$
\frac{L}{\ell_s}=\lambda^{1/4}
$$

to estimate the AdS energy of a massive string oscillator. What happens to the corresponding CFT operator dimension when $\lambda\to\infty$?

<details>
<summary><strong>Solution</strong></summary>

A typical massive string oscillator has mass

$$
m_s\sim\frac{1}{\ell_s}.
$$

Its dimensionless AdS mass is

$$
m_sL\sim\frac{L}{\ell_s}=\lambda^{1/4}.
$$

For a heavy bulk field, the dual operator dimension scales roughly as

$$
\Delta\sim mL.
$$

Therefore

$$
\Delta_{\mathrm{stringy}}\sim\lambda^{1/4}.
$$

As $\lambda\to\infty$, stringy operators become very heavy in CFT units. This creates a large gap above the low-energy supergravity sector.

</details>

### Exercise 3: Why large $N$ alone is not enough

Consider

$$
N\to\infty,
\qquad
\lambda\ll1\;\text{fixed}.
$$

Which bulk corrections are suppressed, and which are not?

<details>
<summary><strong>Solution</strong></summary>

Since

$$
g_s=\frac{\lambda}{4\pi N},
$$

taking $N\to\infty$ at fixed $\lambda$ suppresses string loops. Equivalently, bulk quantum corrections are suppressed.

However,

$$
\frac{\alpha'}{L^2}=\frac{1}{\sqrt\lambda}.
$$

If $\lambda\ll1$, this is large. The curvature is string-scale or worse, so the two-derivative supergravity approximation is not reliable. The bulk is tree-level string theory in a highly curved background, not classical Einstein gravity.

</details>

### Exercise 4: Identify the correction

A holographic observable has the schematic expansion

$$
\mathcal Q
=
N^2q_0
+
N^2q_1\lambda^{-3/2}
+q_2
+\cdots.
$$

Identify the classical supergravity term, the stringy correction, and the bulk loop correction.

<details>
<summary><strong>Solution</strong></summary>

The term

$$
N^2q_0
$$

is the classical supergravity result.

The term

$$
N^2q_1\lambda^{-3/2}
$$

is a finite-coupling, stringy correction. In the maximally supersymmetric example, powers like $\lambda^{-3/2}$ often arise from the leading $\alpha'^3R^4$ correction.

The term

$$
q_2
$$

is smaller than the leading $N^2$ term by $1/N^2$. It is therefore a bulk loop correction.

</details>

## Further reading

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- G. 't Hooft, [A Planar Diagram Theory for Strong Interactions](https://webspace.science.uu.nl/~hooft101/gthpub/planar_diagram_theory.pdf).
- J. Polchinski, [Introduction to Gauge/Gravity Duality](https://arxiv.org/abs/1010.6134).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151).

The next unit turns this approximation into a computational dictionary: boundary sources become boundary values of bulk fields, and CFT correlation functions become variations of renormalized on-shell actions.
