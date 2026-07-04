---
title: "Bulk Causality and Boundary Consistency"
description: "How boundary microcausality, crossing, positivity, Regge behavior, and chaos constrain bulk effective field theories in AdS/CFT."
sidebar:
  order: 70
---

The previous pages treated Witten diagrams, OPE coefficients, four-point functions, geodesic probes, Wilson loops, and probe branes as tools. This page explains a sharper lesson: **not every apparently reasonable bulk model is allowed**. The boundary theory is a complete quantum system, and its basic consistency conditions constrain the bulk action, the signs of higher-derivative interactions, the spectrum of massive particles, and even the possible speed of signals in curved backgrounds.

The slogan is:

$$
\text{boundary consistency}
\quad\Longrightarrow\quad
\text{bulk causality and locality constraints}.
$$

This is one of the most powerful uses of AdS/CFT. Instead of guessing which gravitational effective field theories are healthy, one can ask whether their boundary correlators obey causality, unitarity, crossing symmetry, positivity, and high-energy boundedness. If they do not, the bulk theory is not merely aesthetically suspicious. It cannot be the low-energy limit of a consistent holographic CFT.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Boundary consistency conditions constrain bulk effective field theory.](/figures/course/bulk-causality-boundary-consistency.svg)

<figcaption>

Boundary consistency filters bulk effective field theory. Microcausality, crossing, positivity, and Regge boundedness constrain the CFT data; through the AdS/CFT dictionary they constrain bulk propagation, higher-derivative couplings, and the spectrum above the low-energy gravitational sector.

</figcaption>
</figure>

## Why this matters

The bulk equations of motion may look perfectly covariant while still failing the boundary theory's consistency tests. This can happen when higher-derivative terms make some graviton polarizations propagate too quickly, when a truncated bulk action has no massive tower capable of restoring causality, or when a proposed four-point function cannot be made crossing symmetric with positive OPE coefficients.

This is especially important for bottom-up holography. A model may have an AdS solution, a black brane, and a plausible-looking on-shell action. That is not enough. A candidate holographic dual must also produce boundary correlators with the right causal support, analytic structure, positivity properties, and operator algebra.

The clean lesson is:

$$
\text{AdS solution}
\neq
\text{consistent holographic theory}.
$$

A consistent holographic model must pass both bulk and boundary tests.

## The two causalities

There are two notions of causality in the correspondence.

The first is **boundary microcausality**. For local boundary operators in Lorentzian signature,

$$
[\mathcal O_1(x),\mathcal O_2(y)] = 0
\qquad
\text{when } x-y \text{ is spacelike}.
$$

Equivalently, the retarded Green's function

$$
G_R(x,y)
=
-i\theta(t_x-t_y)
\langle [\mathcal O(x),\mathcal O(y)]\rangle
$$

has no support outside the boundary light cone.

The second is **bulk causality**. In the bulk, fields propagate according to the causal structure determined by the equations of motion. For two-derivative Einstein gravity minimally coupled to standard matter, causal propagation is governed by the bulk metric light cone. For higher-derivative theories, however, the characteristic surfaces of fluctuations can differ from the metric light cone. Different polarizations may even see different effective light cones.

The correspondence requires these two notions to be compatible. A bulk causal curve connecting two boundary insertions must not allow the boundary theory to send information outside its own light cone.

A useful boundary statement is:

$$
\text{spacelike boundary separation}
\quad\Longrightarrow\quad
\text{no boundary signal}.
$$

The corresponding bulk statement is:

$$
\text{no bulk shortcut between spacelike-separated boundary points}.
$$

The subtle word is “shortcut.” A causal curve may leave the boundary, move through the bulk, and return to the boundary. If that curve connects boundary points faster than any boundary null curve, the dual CFT would exhibit superluminal propagation.

## A warm-up: no shortcut in pure Poincaré AdS

Pure Poincaré AdS$_{d+1}$ has metric

$$
ds^2
=
\frac{L^2}{z^2}
\left(
-dt^2+d\vec x^{\,2}+dz^2
\right),
\qquad z>0.
$$

For a future-directed causal curve,

$$
-dt^2+d\vec x^{\,2}+dz^2 \le 0,
$$

so

$$
dt \ge \sqrt{d\vec x^{\,2}+dz^2}
$$

along the curve. Integrating between two boundary endpoints gives

$$
\Delta t
\ge
\int \sqrt{d\vec x^{\,2}+dz^2}
\ge
|\Delta \vec x|.
$$

Thus a causal curve through the bulk cannot connect boundary points with

$$
\Delta t < |\Delta \vec x|.
$$

The conformal factor $L^2/z^2$ does not change null cones. In pure AdS, the bulk is not a faster-than-light tunnel for boundary observers.

This elementary argument is worth remembering. Many sophisticated causality constraints are refined versions of this simple idea: boundary causality is a strict test of the bulk causal structure.

## Boundary causality in asymptotically AdS spacetimes

Pure AdS is special. Real bulk states contain matter, black holes, gravitational waves, and quantum corrections. The question becomes: can a perturbed asymptotically AdS geometry create a bulk shortcut?

Classically, under suitable assumptions such as appropriate energy conditions and causality conditions in the bulk, positive-energy perturbations produce a **time delay**, not a time advance. The intuitive reason is gravitational focusing: null rays are delayed by the matter or curvature they encounter.

In holography this becomes a consistency requirement:

$$
\text{bulk time advance between boundary points}
\quad\Rightarrow\quad
\text{boundary microcausality violation}.
$$

This does not mean every individual bulk path must be slower than every boundary path in an informal coordinate sense. The invariant statement concerns the causal relation induced on the conformal boundary. If two boundary points are spacelike in the boundary metric, bulk propagation must not make them causally related.

## Retarded response and signal propagation

Boundary causality is most directly visible in retarded correlators. Suppose we perturb the CFT by a source

$$
\delta S_{\mathrm{CFT}}
=
\int d^d x\,J(x)\mathcal O(x).
$$

To first order in $J$, the response of another operator is

$$
\delta\langle \mathcal O(y)\rangle
=
\int d^d x\,G_R(y,x)J(x),
$$

where

$$
G_R(y,x)
=
-i\theta(t_y-t_x)
\langle [\mathcal O(y),\mathcal O(x)]\rangle.
$$

If $G_R(y,x)$ were nonzero for spacelike-separated $x$ and $y$, a source at $x$ could influence a measurement at $y$ faster than allowed by the boundary light cone. Thus the support of $G_R$ is not a minor technical detail. It is the operational content of causality.

In the bulk, the same response is computed by solving a boundary-value problem. A source $J$ fixes the non-normalizable mode of a bulk field. The retarded prescription imposes infalling, regular, or otherwise causal interior conditions depending on the state. The response is extracted from the normalizable mode. The consistency condition is that this bulk computation must produce a boundary retarded function with causal support.

## What higher-derivative terms can do

A low-energy bulk action generally contains higher-derivative corrections:

$$
S
=
\frac{1}{16\pi G_N}
\int d^{d+1}x\sqrt{-g}
\left[
R+\frac{d(d-1)}{L^2}
+L^2\alpha_1 R^2
+L^4\alpha_2 R^3
+\cdots
\right].
$$

This expression is schematic. Some curvature-squared terms can be moved by field redefinitions, and the precise independent terms depend on dimension and on the fields kept in the truncation. The important point is physical: higher-derivative interactions modify high-energy scattering and the propagation of fluctuations in nontrivial backgrounds.

In an ordinary effective field theory, one might say: “as long as $\alpha_i$ are small, the theory is fine below the cutoff.” Holography teaches a sharper lesson. Some signs and magnitudes of higher-derivative terms lead to boundary causality violations unless new higher-spin states appear at a scale low enough to repair the problem.

The bulk EFT expansion should really look like

$$
S
=
S_{\mathrm{Einstein}}
+
\sum_{n}
\frac{c_n}{\Delta_{\mathrm{gap}}^{\;n}}
\int \sqrt{-g}\,\mathcal I_n,
$$

where $\Delta_{\mathrm{gap}}$ is the dimension of the lightest single-trace operator with spin greater than two, or equivalently the scale of stringy or higher-spin physics in AdS units. Large gap means the non-Einstein corrections are parametrically suppressed.

The lesson is not merely that higher-derivative corrections exist. The lesson is that a large-gap holographic CFT severely restricts them.

## Shapiro time delay and its holographic meaning

A classic diagnostic is high-energy scattering through a gravitational shock wave. A probe crosses a shock created by another highly boosted excitation. The result is an eikonal phase shift

$$
\mathcal A(s,b)
\sim
\exp\!\left(i\delta(s,b)\right),
$$

where $s$ is the center-of-mass energy and $b$ is the impact parameter. The associated time shift is schematically

$$
\Delta t
\sim
\frac{\partial \delta}{\partial E}.
$$

Einstein gravity gives a positive Shapiro time delay. Some higher-derivative graviton couplings can instead give a negative time delay for certain polarizations:

$$
\Delta t < 0.
$$

A negative time delay is a time advance. In AdS, this can translate into a boundary signal arriving before boundary causality permits. That is not a harmless artifact of coordinates; it is a physical inconsistency of the would-be dual CFT.

The sharp modern lesson is:

$$
\text{large higher-derivative graviton coupling}
\quad\Rightarrow\quad
\text{need new higher-spin states nearby}.
$$

If no such states exist, the theory cannot be completed into a causal, unitary theory with a weakly coupled gravitational sector.

For AdS$_5$/CFT$_4$ theories with a weakly coupled gravity dual, a famous schematic constraint is

$$
\left|\frac{a-c}{c}\right|
\lesssim
\frac{1}{\Delta_{\mathrm{gap}}^2},
$$

where $a$ and $c$ are the four-dimensional CFT Weyl-anomaly coefficients. The precise numerical coefficient depends on conventions and on the setup, but the parametric message is robust: if the bulk has a large gap, the graviton three-point function must be very close to the Einstein-gravity value.

## Conformal collider physics

A purely boundary way to see related constraints is conformal collider physics. Prepare a localized excitation by inserting an operator, then measure the energy flux at null infinity in direction $\vec n$:

$$
\mathcal E(\vec n)
=
\lim_{r\to\infty}r^{d-2}
\int_{-\infty}^{\infty}dt\, n^i T_{0i}(t,r\vec n).
$$

For a physical state $|\psi\rangle$, energy flux should be nonnegative:

$$
\frac{\langle \psi|\mathcal E(\vec n)|\psi\rangle}
{\langle \psi|\psi\rangle}
\ge 0.
$$

This positivity condition constrains three-point functions such as

$$
\langle TTT\rangle,
\qquad
\langle JJT\rangle,
\qquad
\langle \mathcal O\mathcal O T\rangle.
$$

In four-dimensional parity-even CFTs with a unique stress tensor, conformal collider bounds imply constraints on the anomaly coefficients. A standard result is

$$
\frac{1}{3}\le \frac{a}{c}\le \frac{31}{18},
$$

with a narrower range in supersymmetric theories,

$$
\frac{1}{2}\le \frac{a}{c}\le \frac{3}{2}.
$$

These are boundary statements. In holographic language they become restrictions on higher-curvature gravitational couplings. The same physics that says energy flux cannot be negative says that bulk gravitons cannot acquire pathological time advances.

## Example: Gauss–Bonnet gravity as a warning sign

A commonly studied toy model is five-dimensional Gauss–Bonnet gravity,

$$
S
=
\frac{1}{16\pi G_5}
\int d^5x\sqrt{-g}
\left[
R+\frac{12}{L^2}
+\frac{\lambda_{\mathrm{GB}}L^2}{2}
\left(
R^2-4R_{ab}R^{ab}+R_{abcd}R^{abcd}
\right)
\right].
$$

This model is useful because it keeps the equations of motion second order while changing many observables. For example, in a standard normalization,

$$
\frac{\eta}{s}
=
\frac{1-4\lambda_{\mathrm{GB}}}{4\pi}.
$$

It may look tempting to choose $\lambda_{\mathrm{GB}}$ freely and produce very small $\eta/s$. But boundary causality restricts the allowed range. In the usual AdS$_5$/CFT$_4$ setup, microcausality and positivity analyses give the familiar window

$$
-\frac{7}{36}
\le
\lambda_{\mathrm{GB}}
\le
\frac{9}{100}.
$$

At the upper end,

$$
\frac{\eta}{s}
=
\frac{16}{25}\frac{1}{4\pi}.
$$

This example is pedagogically valuable because it shows how a bulk transport coefficient, a higher-curvature coupling, a stress-tensor three-point function, and boundary microcausality are all the same consistency problem viewed from different angles.

The warning is also important: Gauss–Bonnet gravity by itself is not automatically a complete string theory. It is a useful effective model only when embedded in a spectrum and coupling structure compatible with the full boundary consistency conditions.

## Crossing symmetry and bulk locality

Causality is not the only boundary consistency condition. Crossing symmetry is just as important.

For identical scalar primaries $\mathcal O$ of dimension $\Delta$, write the four-point function as

$$
\langle
\mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\mathcal O(x_4)
\rangle
=
\frac{1}{x_{12}^{2\Delta}x_{34}^{2\Delta}}
\mathcal G(u,v),
$$

where

$$
u
=
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v
=
\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

Crossing symmetry requires

$$
v^\Delta \mathcal G(u,v)
=
u^\Delta \mathcal G(v,u).
$$

In a large-$N$ CFT, the leading disconnected answer gives generalized free fields. At order $1/N^2$, connected four-point functions encode bulk interactions. A local contact interaction in AdS produces a specific correction to $\mathcal G(u,v)$; an exchange diagram produces another. These corrections must fit into a crossing-symmetric CFT correlator with positive-norm operators.

This is the boundary origin of a major result: large $N$, sparse spectrum, and crossing symmetry strongly suggest a local bulk effective field theory. Conversely, arbitrary bulk vertices are not free parameters. They must correspond to CFT data that solve crossing.

A useful dictionary line is:

$$
\text{crossing symmetry of four-point functions}
\quad\Longleftrightarrow\quad
\text{consistent factorization of bulk scattering}.
$$

## Regge behavior and high-energy scattering

The Lorentzian Regge limit of CFT correlators probes high-energy bulk scattering. Roughly, it asks what happens when operators are boosted relative to each other. In the bulk, this corresponds to high-energy scattering near a shock wave or near a black-hole horizon.

A healthy CFT does not allow arbitrary growth in this limit. Analyticity, unitarity, and causality impose boundedness conditions. In the bulk, these become constraints on eikonal scattering amplitudes, high-spin exchange, and the possible signs of higher-derivative interactions.

The same principle appears in thermal physics through out-of-time-order correlators. A thermal OTOC can diagnose the growth of chaos:

$$
C(t)
\sim
\frac{1}{N^2}e^{\lambda_L t}
$$

for an intermediate range of times. Under standard assumptions, the Lyapunov exponent obeys

$$
\lambda_L \le 2\pi T.
$$

Einstein black holes saturate this bound. Stringy and higher-derivative corrections generally modify the high-energy scattering that controls the OTOC. Thus the chaos bound is another boundary consistency condition with a bulk interpretation: gravitational scattering near horizons cannot be arbitrarily violent.

This page is not a course on chaos. The key point is narrower: high-energy Lorentzian correlators are not optional observables. They are stress tests for the causal structure of holographic bulk dynamics.

## Bulk-point singularities

Local bulk physics leaves especially sharp traces in Lorentzian boundary correlators. In the strict large-$N$, large-gap limit, a boundary correlator can develop a **bulk-point singularity** when several boundary insertions are arranged so that null geodesics from them meet at a common point in the bulk.

This is a striking phenomenon. The boundary theory lives in $d$ dimensions, but its Lorentzian singularity structure can reveal a local scattering event in $d+1$ dimensions.

However, one must be careful. At finite $N$, finite gap, or finite string length, the singularity is softened. Stringy physics smears the pointlike interaction. Quantum gravity effects also regulate overly sharp bulk locality.

The lesson is:

$$
\text{sharp bulk locality}
\quad
\text{is an emergent large-}N\text{, large-gap property}.
$$

It is not an exact microscopic property of the boundary theory.

## What the boundary forbids

The following table summarizes common consistency filters.

| Boundary requirement | Bulk consequence | What can go wrong |
|---|---|---|
| Microcausality | no boundary superluminal signal through the bulk | bulk shortcut or time advance |
| Unitarity / reflection positivity | no negative-norm states | ghosts, wrong-sign kinetic terms |
| Crossing symmetry | compatible OPE in all channels | inconsistent exchange/contact data |
| Energy flux positivity / ANEC | nonnegative gravitational time delay | forbidden higher-derivative signs |
| Regge boundedness | controlled high-energy scattering | excessive growth, acausal eikonal phase |
| Large $N$ factorization | weak bulk interactions | no semiclassical expansion |
| Large single-trace gap | local bulk EFT below the gap | unsuppressed stringy or higher-spin physics |

These conditions are not independent decorations. They reinforce one another. A violation may appear in different languages depending on the observable: a negative energy flux, a superluminal graviton mode, a wrong-sign OPE coefficient, a bad Regge limit, or a boundary commutator with spacelike support.

## A practical diagnostic for bulk EFTs

Suppose someone proposes a bulk action. How should you test it holographically?

First, identify the boundary sources and operators. Metric fluctuations map to $T_{ij}$, bulk gauge fields to currents $J_i$, and scalar fields to scalar primaries. Higher-derivative bulk terms modify two-, three-, and four-point functions of these operators.

Second, compute the CFT data affected by the new terms. For example:

$$
R^2 \text{ and } R^3 \text{ terms}
\quad\Longrightarrow\quad
\langle TTT\rangle \text{ and stress-tensor four-point data}.
$$

Third, check positivity constraints. Does the energy flux remain nonnegative in every polarization? Are OPE coefficients compatible with unitarity?

Fourth, check causality in a high-energy background. Do gravitons, gauge fields, or scalar perturbations develop effective superluminal propagation relative to the boundary light cone?

Fifth, ask whether a gap exists. If the higher-derivative term is not parametrically suppressed, the bulk EFT should include additional massive stringy or higher-spin states. Omitting them may create artificial causality problems.

This leads to a reliable rule of thumb:

$$
\text{large higher-derivative effect}
\quad\Rightarrow\quad
\text{do not trust a small-field truncation alone}.
$$

A large correction may be physically allowed only together with the degrees of freedom that complete it.

## Boundary consistency versus bulk energy conditions

It is tempting to summarize everything by saying “the bulk must satisfy the null energy condition.” That is too simple.

Classical energy conditions are useful, and the Gao–Wald time-delay intuition is essential. But holographic consistency is broader. Quantum fields can violate pointwise energy conditions. Higher-derivative theories can change characteristic cones. Stringy corrections can smear local interactions. Boundary causality is the sharper invariant statement.

A better hierarchy is:

$$
\text{classical energy conditions}
\quad\subset\quad
\text{bulk causal propagation tests}
\quad\subset\quad
\text{full boundary consistency}.
$$

The boundary theory is the final judge. If the boundary correlators are unitary, causal, crossing symmetric, and appropriately bounded, the bulk description is healthy in the regime where it is meant to apply. If the boundary correlators fail these tests, the bulk model is not a consistent holographic theory.

## Why large gap matters again

The phrase “large gap” has appeared several times in this course. Here is the causality reason for it.

A low-energy gravitational EFT assumes that massive higher-spin particles are far away. In AdS units, this means

$$
\Delta_{\mathrm{gap}} \gg 1.
$$

If the gap is large, higher-derivative terms are suppressed by powers of $1/\Delta_{\mathrm{gap}}$. Bulk scattering at energies below the gap is then approximately local and causal.

If the gap is not large, the theory may still be perfectly consistent, but the simple Einstein-like bulk EFT is not. The bulk may be stringy or higher-spin at the AdS scale. In such a theory, trying to keep only a few low-spin fields while throwing away the tower is dangerous.

This is why the following two statements are different:

$$
\text{the CFT has a holographic dual}
$$

and

$$
\text{the CFT has a weakly curved local Einstein-gravity dual}.
$$

The second statement is much stronger. It requires large $N$, strong coupling or large gap, and consistency of the resulting bulk EFT.

## How to read causality constraints in papers

Research papers often discuss causality constraints in different languages. Here is how to translate them.

If a paper studies **front velocities** or **microcausality**, it is asking whether boundary retarded correlators have support outside the light cone.

If a paper studies **shock waves** or **time delay**, it is testing high-energy bulk scattering and asking whether some polarization receives a time advance.

If a paper studies **conformal collider bounds**, it is testing positivity of energy flux in states created by local operators.

If a paper studies **Regge limits** or **chaos**, it is testing high-energy Lorentzian analyticity and bounded growth.

If a paper studies **crossing plus a large gap**, it is asking whether the CFT data can be organized into a local bulk EFT.

These languages are not identical, but they often constrain the same physical data.

## Dictionary checkpoint

The main translations from this page are:

| Boundary statement | Bulk interpretation |
|---|---|
| $[\mathcal O(x),\mathcal O(y)]=0$ for spacelike separation | no bulk signal connects spacelike-separated boundary points |
| retarded correlators have causal support | bulk boundary-value problem has causal propagation |
| crossing symmetry of four-point functions | consistent factorization of bulk exchange and contact interactions |
| energy flux positivity / ANEC | no negative Shapiro time delay in the corresponding bulk process |
| conformal collider bounds on $\langle TTT\rangle$ | constraints on higher-curvature graviton couplings |
| Regge boundedness and chaos bounds | controlled high-energy gravitational scattering |
| large single-trace gap | local bulk EFT with suppressed higher-derivative corrections |

The deepest point is that bulk causality is not an extra assumption added to AdS/CFT. It is encoded in the analytic and algebraic consistency of the boundary CFT.

## Common confusions

### “Any covariant bulk action with AdS boundary conditions defines a CFT.”

No. Covariance and an AdS solution are not enough. The dual boundary correlators must be causal, unitary, crossing symmetric, and positive in the appropriate sense. Many bottom-up actions are useful phenomenological models but are not guaranteed to define complete holographic CFTs.

### “Small higher-derivative terms are always harmless.”

Not automatically. Even small higher-derivative terms can have dangerous signs in high-energy scattering. If they are parametrically suppressed by a large gap and have the signs dictated by a healthy UV completion, they are usually safe. If they are inserted arbitrarily, they may violate boundary causality.

### “Superluminal propagation in the bulk is always a coordinate-independent violation.”

One must be precise. The invariant holographic question is whether boundary signals can arrive outside the boundary light cone. Effective light cones for fluctuations can be gauge- or field-variable dependent in some descriptions, but boundary microcausality is physical.

### “The null energy condition is the whole story.”

The classical null energy condition is useful, but full holographic consistency involves quantum positivity, crossing symmetry, Regge behavior, and the spectrum. Boundary consistency is more fundamental than any particular classical energy condition.

### “Large $N$ automatically implies local bulk physics.”

Large $N$ gives weak bulk interactions, but not necessarily local Einstein gravity. For that one also needs a sparse spectrum or large gap in higher-spin single-trace operators. Without the gap, the bulk may be stringy or higher-spin at the AdS scale.

### “Causality constraints kill all higher-derivative gravity.”

No. Higher-derivative terms are expected in any effective theory. The point is that their coefficients and signs are constrained, and large effects usually require the tower of additional states that completes the EFT.

## Exercises

### Exercise 1: No bulk shortcut in pure Poincaré AdS

Use the Poincaré AdS metric

$$
ds^2
=
\frac{L^2}{z^2}
\left(-dt^2+d\vec x^{\,2}+dz^2\right)
$$

to show that a causal bulk curve connecting two boundary points must satisfy

$$
\Delta t \ge |\Delta \vec x|.
$$

<details>
<summary><strong>Solution</strong></summary>

For a causal curve,

$$
-dt^2+d\vec x^{\,2}+dz^2\le 0,
$$

because the conformal factor $L^2/z^2$ is positive and does not affect the null cone. Therefore

$$
dt\ge \sqrt{d\vec x^{\,2}+dz^2}
$$

for a future-directed causal curve. Integrating along the curve gives

$$
\Delta t
\ge
\int \sqrt{d\vec x^{\,2}+dz^2}
\ge
\int |d\vec x|
\ge
|\Delta \vec x|.
$$

Thus if two boundary points obey $\Delta t<|\Delta\vec x|$, no causal bulk curve in pure Poincaré AdS can connect them.

</details>

### Exercise 2: Retarded response and microcausality

Suppose the CFT is perturbed by

$$
\delta S=\int d^d x\,J(x)\mathcal O(x).
$$

Show that if the retarded correlator $G_R(y,x)$ has support at spacelike separation, then the source can produce a spacelike response.

<details>
<summary><strong>Solution</strong></summary>

Linear response gives

$$
\delta\langle \mathcal O(y)\rangle
=
\int d^d x\,G_R(y,x)J(x),
$$

where

$$
G_R(y,x)
=
-i\theta(t_y-t_x)
\langle[\mathcal O(y),\mathcal O(x)]\rangle.
$$

If $G_R(y,x)$ is nonzero when $x$ and $y$ are spacelike separated, then a source localized near $x$ changes the expectation value measured near $y$ even though no boundary causal curve connects the two regions. That is precisely a violation of boundary microcausality.

</details>

### Exercise 3: Estimating higher-derivative suppression

Assume a large-gap holographic CFT has

$$
\left|\frac{a-c}{c}\right|
\lesssim
\frac{1}{\Delta_{\mathrm{gap}}^2}.
$$

If $\Delta_{\mathrm{gap}}=20$, what is the expected parametric size of $|(a-c)/c|$?

<details>
<summary><strong>Solution</strong></summary>

The estimate gives

$$
\frac{1}{\Delta_{\mathrm{gap}}^2}
=
\frac{1}{20^2}
=
\frac{1}{400}
=0.0025.
$$

Thus $|(a-c)/c|$ should be at most of order $2.5\times 10^{-3}$, up to coefficients that depend on the precise theory and convention. The important point is the parametric suppression: a large gap forces the stress-tensor three-point function to be close to the Einstein-gravity value.

</details>

### Exercise 4: Gauss–Bonnet viscosity bound

In five-dimensional Gauss–Bonnet gravity, use

$$
\frac{\eta}{s}
=
\frac{1-4\lambda_{\mathrm{GB}}}{4\pi}
$$

and the causality upper bound

$$
\lambda_{\mathrm{GB}}\le \frac{9}{100}
$$

to find the corresponding lower bound on $\eta/s$ in this model.

<details>
<summary><strong>Solution</strong></summary>

Since $\eta/s$ decreases as $\lambda_{\mathrm{GB}}$ increases, the smallest value occurs at

$$
\lambda_{\mathrm{GB}}=\frac{9}{100}.
$$

Then

$$
1-4\lambda_{\mathrm{GB}}
=
1-\frac{36}{100}
=
\frac{64}{100}
=
\frac{16}{25}.
$$

Therefore

$$
\frac{\eta}{s}
\ge
\frac{16}{25}\frac{1}{4\pi}.
$$

This is a model-dependent causality bound, not a universal theorem for all quantum field theories.

</details>

### Exercise 5: Why a tower can restore causality

Explain qualitatively why adding a finite number of low-spin fields may fail to repair a causality violation from a higher-derivative graviton coupling, while an infinite tower of higher-spin states can.

<details>
<summary><strong>Solution</strong></summary>

A higher-derivative graviton coupling changes high-energy scattering in a way that grows with energy and depends on polarization. If the resulting eikonal phase produces a time advance, the problem appears in a regime sensitive to arbitrarily high spin exchange. A finite number of low-spin fields can adjust only finitely many structures and usually cannot reorganize the high-energy amplitude enough to restore causal Regge behavior.

An infinite tower of higher-spin states, as in string theory, changes the high-energy amplitude nonlocally over the string scale. It softens pointlike gravitational scattering and modifies the Regge behavior. In the CFT, this corresponds to the absence of a parametrically large higher-spin gap: the would-be dangerous higher-derivative coupling is completed by additional single-trace operators before it causes an observable causality violation.

</details>

## Further reading

- S. Gao and R. M. Wald, [Theorems on Gravitational Time Delay and Related Issues](https://arxiv.org/abs/gr-qc/0007021).
- D. M. Hofman and J. Maldacena, [Conformal Collider Physics: Energy and Charge Correlations](https://arxiv.org/abs/0803.1467).
- M. Brigante, H. Liu, R. C. Myers, S. Shenker, and S. Yaida, [Viscosity Bound and Causality Violation](https://arxiv.org/abs/0802.3318).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151).
- X. O. Camanho, J. D. Edelstein, J. Maldacena, and A. Zhiboedov, [Causality Constraints on Corrections to the Graviton Three-Point Coupling](https://arxiv.org/abs/1407.5597).
- T. Hartman, S. Kundu, and A. Tajdini, [Averaged Null Energy Condition from Causality](https://arxiv.org/abs/1610.05308).
- J. Maldacena, S. H. Shenker, and D. Stanford, [A Bound on Chaos](https://arxiv.org/abs/1503.01409).
