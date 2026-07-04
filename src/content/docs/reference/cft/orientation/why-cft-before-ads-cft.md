---
title: "Why CFT Before AdS/CFT?"
description: "Why conformal field theory is the natural language of holography, and which CFT ideas become bulk AdS physics."
sidebar:
  order: 1
---

## The point of this page

The fastest way to misunderstand AdS/CFT is to treat it as a mysterious equivalence between two unrelated things: a gravitational theory in one spacetime and a quantum field theory in another. The fastest way to understand it is to notice that the boundary theory is not just any QFT. It is a **conformal field theory**, and conformal field theory already knows an astonishing amount about anti-de Sitter spacetime.

This course starts with CFT because the basic objects of AdS/CFT are already CFT objects:

- the conformal group $SO(d,2)$ is the isometry group of $AdS_{d+1}$,
- local CFT operators become bulk fields,
- CFT sources become boundary conditions for bulk fields,
- scaling dimensions become bulk masses,
- CFT Ward identities become bulk gauge and diffeomorphism constraints,
- CFT OPE coefficients become bulk interaction vertices,
- large-$N$ factorization becomes semiclassical gravity,
- thermal CFT states become black holes or black branes,
- entanglement data becomes geometric data.

The slogan is not that CFT is useful background. The slogan is sharper:

$$
\text{the CFT is the nonperturbative definition of the AdS quantum gravity theory.}
$$

So this first page explains why the CFT side must be learned carefully before one can read AdS/CFT as physics rather than as a dictionary of formulas.

<figure class="doc-figure" style="--figure-width: 44rem; --caption-width: 55rem;">

![A map from CFT data to AdS bulk data](/figures/cft/cft-before-ads-cft-dictionary.svg)

<figcaption>

The preparation problem for AdS/CFT. The complete CFT data $\{\Delta_i,\ell_i,C_{ijk}\}$ determines the boundary theory. In holographic CFTs, the same data reorganizes itself into bulk fields, interactions, and geometry. The arrows are not independent assumptions; they are the first semiclassical shadows of the equality of complete quantum theories.

</figcaption>
</figure>

## CFT is the natural boundary language

A local QFT is usually described by local operators and their correlation functions. A CFT is a local QFT whose spacetime symmetries are enlarged from the Poincare group to the conformal group. In $d$ Lorentzian dimensions, this group is

$$
SO(d,2).
$$

That same group is the isometry group of $AdS_{d+1}$. This is the first and most elementary reason CFT is the right boundary theory for AdS/CFT.

In Poincare coordinates, the metric of $AdS_{d+1}$ is

$$
ds^2 = \frac{R^2}{z^2}\left(dz^2 + \eta_{\mu\nu} dx^\mu dx^\nu\right),
\qquad z>0,
$$

where $R$ is the AdS radius and the conformal boundary sits at $z=0$. The simultaneous scaling

$$
x^\mu \to \lambda x^\mu,
\qquad
z \to \lambda z
$$

leaves the metric invariant. Thus a scale transformation of the boundary coordinates is literally an AdS isometry. The radial coordinate $z$ transforms like a length scale, so smaller $z$ corresponds to shorter boundary distances or higher boundary energy. This is the beginning of the radial/RG relation:

$$
\text{AdS radial direction} \quad \leftrightarrow \quad \text{CFT energy scale}.
$$

This observation is simple, but it is profound. A bulk direction is not put into the boundary QFT by hand. It emerges as the bookkeeping direction for scale.

> **AdS/CFT checkpoint.** The phrase “the boundary is one dimension lower” is geometrically true, but holographically incomplete. The missing radial dimension is encoded in the CFT's scale dependence, operator dimensions, and renormalization-group structure.

## The CFT observables are the holographic observables

In asymptotically flat quantum gravity, one often discusses an $S$-matrix. In global AdS, the situation is different. The AdS boundary behaves like a reflective box: excitations can travel to the boundary and return in finite global time. There is no ordinary flat-space scattering problem unless one takes special limits. Instead, the natural gauge-invariant observables are boundary observables.

On the CFT side, the basic observables are correlation functions of local operators:

$$
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle.
$$

AdS/CFT says that these are not merely analogous to bulk observables. They are the fundamental observables from which bulk physics is reconstructed.

A particularly efficient way to package them is the generating functional. If $J_i(x)$ are sources coupled to CFT operators $\mathcal O_i(x)$, define

$$
Z_{\rm CFT}[J]
=
\left\langle
\exp\left(\sum_i \int d^d x\, J_i(x)\mathcal O_i(x)\right)
\right\rangle_{\rm CFT}.
$$

Correlation functions are obtained by differentiating with respect to the sources:

$$
\langle \mathcal O_{i_1}(x_1)\cdots \mathcal O_{i_n}(x_n)\rangle
=
\left.
\frac{\delta^n Z_{\rm CFT}[J]}
{\delta J_{i_1}(x_1)\cdots \delta J_{i_n}(x_n)}
\right|_{J=0}
$$

up to the usual distinction between connected and disconnected correlators depending on whether one differentiates $Z_{\rm CFT}$ or $W_{\rm CFT}=\log Z_{\rm CFT}$.

The central AdS/CFT statement is then

$$
Z_{\rm CFT}[J]
=
Z_{\rm bulk}\left[\phi_i\;\text{with boundary value determined by}\;J_i\right].
$$

In a semiclassical gravity limit, this becomes

$$
Z_{\rm CFT}[J]
\simeq
\exp\left(-S_{\rm bulk}^{\rm ren}[\phi_{\rm cl};J]\right),
$$

where $\phi_{\rm cl}$ is the classical bulk solution with prescribed asymptotic boundary behavior, and $S_{\rm bulk}^{\rm ren}$ is the renormalized on-shell action.

This formula is the first version of the holographic dictionary. But it is easy to over-read it. It is not saying that every CFT has a simple Einstein gravity dual. It says that, when a CFT has a holographic dual, the generating functional of CFT correlators is computed by a bulk path integral with boundary conditions fixed by CFT sources.

## Operators are the CFT's particles

In ordinary perturbative QFT, one often starts with fields in a Lagrangian. In CFT, the more invariant starting point is the set of local operators. A scalar primary operator $\mathcal O(x)$ has a scaling dimension $\Delta$ defined by

$$
\mathcal O(x) \to \lambda^{-\Delta}\mathcal O(\lambda^{-1}x)
$$

or equivalently by its two-point function,

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\frac{C_{\mathcal O}}{|x|^{2\Delta}}.
$$

In AdS/CFT, a primary operator corresponds to a single-particle bulk field. For a scalar field in $AdS_{d+1}$,

$$
\mathcal O_\Delta(x)
\quad \leftrightarrow \quad
\phi(z,x),
$$

and the mass of the bulk scalar is related to the CFT dimension by

$$
m^2R^2 = \Delta(\Delta-d).
$$

This equation is one of the best examples of why CFT preparation matters. The CFT number $\Delta$ is not just an abstract critical exponent. In a holographic CFT, it is a bulk mass in disguise.

Near the AdS boundary, a scalar solution behaves schematically as

$$
\phi(z,x)
\sim
z^{d-\Delta}J(x)+z^\Delta A(x),
\qquad z\to 0.
$$

The coefficient $J(x)$ is interpreted as the source for the boundary operator $\mathcal O(x)$. The coefficient $A(x)$ is related to the expectation value $\langle \mathcal O(x)\rangle$, after holographic renormalization. Thus the two independent near-boundary behaviors of a bulk field are translated into the two natural CFT notions:

$$
\text{source} \quad \text{and} \quad \text{response}.
$$

This is the same logic as linear response theory, but upgraded to a gravitational setting.

## CFT data is the real input

A CFT is not specified only by symmetry. Symmetry fixes much, but not everything. The actual dynamical data of a unitary CFT are usually organized as

$$
\boxed{
\text{CFT data}
=
\left\{\Delta_i,\ell_i,\text{global symmetry representations},C_{ijk}\right\}.
}
$$

Here $\Delta_i$ are scaling dimensions, $\ell_i$ are spins, and $C_{ijk}$ are OPE coefficients. The operator product expansion says that local products can be expanded as sums over local operators:

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ijk}\, |x|^{\Delta_k-\Delta_i-\Delta_j}\,\mathcal O_k(0)+\cdots,
$$

where the omitted terms include descendants and tensor structures. This formula is not merely a short-distance trick. In a CFT, the OPE is convergent inside correlation functions in an appropriate radial-quantization domain. That convergence is what makes the CFT operator algebra powerful.

In holography, this data becomes bulk data:

| CFT datum | Bulk interpretation in a semiclassical regime |
|---|---|
| primary operator $\mathcal O_i$ | bulk field $\phi_i$ or bulk particle species |
| dimension $\Delta_i$ | bulk mass, energy, or Kaluza-Klein level |
| spin $\ell_i$ | bulk spin |
| conserved stress tensor $T_{\mu\nu}$ | graviton $g_{MN}$ |
| conserved current $J_\mu$ | bulk gauge field $A_M$ |
| OPE coefficient $C_{ijk}$ | cubic interaction or three-point coupling |
| conformal block decomposition | exchange of conformal families; in the bulk, exchange Witten diagrams |
| crossing symmetry | consistency of bulk factorization, locality, and causality |

The course will keep returning to this table. It is the skeleton key of AdS/CFT.

## The stress tensor is the first holographic operator

Every local relativistic QFT has a stress tensor $T_{\mu\nu}$, at least under suitable assumptions. In a CFT, the stress tensor is conserved and traceless in flat space:

$$
\partial^\mu T_{\mu\nu}=0,
\qquad
T^\mu{}_{\mu}=0.
$$

Its scaling dimension is fixed:

$$
\Delta_T=d,
\qquad
\ell_T=2.
$$

The stress tensor generates conformal transformations through Ward identities. Because AdS/CFT identifies boundary symmetries with bulk gauge redundancies, the stress tensor is dual to the bulk metric:

$$
T_{\mu\nu}
\quad \leftrightarrow \quad
g_{MN}.
$$

This is not a decorative part of the dictionary. It is why a CFT dual can contain gravity at all. A CFT without a stress tensor would not be a standard local CFT; a holographic theory without a stress-tensor dual would not contain the usual bulk graviton.

The normalization of the stress-tensor two-point function is usually denoted $C_T$:

$$
\langle T_{\mu\nu}(x)T_{\rho\sigma}(0)\rangle
\sim
\frac{C_T}{|x|^{2d}}\times \text{fixed tensor structure}.
$$

In holographic CFTs with an Einstein gravity dual, $C_T$ is proportional to the inverse bulk Newton constant in AdS units:

$$
C_T \sim \frac{R^{d-1}}{G_N}.
$$

Large $C_T$ therefore means weak gravitational coupling in the bulk. This is the first serious hint that a large-$N$ CFT can produce classical gravity.

## Why large $N$ matters

Not every CFT has a useful geometric dual. A generic CFT may be holographic in the broad sense that it is equivalent to some quantum gravity-like theory, but a simple local bulk spacetime requires extra conditions.

The most important condition is a large parameter, usually called $N$, such that connected correlators factorize. For single-trace operators normalized so that two-point functions are order one, the large-$N$ structure often takes the schematic form

$$
\langle \mathcal O_1\mathcal O_2\rangle_{\rm conn}\sim N^0,
$$

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle_{\rm conn}\sim \frac{1}{N},
$$

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_{\rm conn}\sim N^{2-n}
\quad \text{in matrix-like large-}N\text{ theories}.
$$

This is the CFT version of weak bulk interactions. If connected higher-point functions are suppressed, then the leading bulk theory is approximately classical. The $1/N$ expansion becomes the loop expansion of the bulk theory:

$$
\frac{1}{N}
\quad \leftrightarrow \quad
\text{bulk quantum corrections}.
$$

But large $N$ alone is not enough. To get a local Einstein-like bulk, the CFT also needs a sparse low-dimension spectrum of single-trace higher-spin operators. Roughly, there should be a large gap

$$
\Delta_{\rm gap}\gg 1
$$

above the low-spin single-trace sector. This gap suppresses higher-derivative bulk corrections and makes local effective field theory in AdS possible.

So the slogan “large $N$ CFT equals gravity” should be sharpened:

$$
\boxed{
\text{large }N
+
\text{sparse single-trace spectrum}
+
\text{strong enough coupling}
\quad \Rightarrow \quad
\text{semiclassical local AdS gravity.}
}
$$

## Why the OPE is more fundamental than a Lagrangian

Many familiar CFTs have useful Lagrangian descriptions: free scalar theory, Wilson-Fisher fixed points, WZW models, gauge theories, and $\mathcal N=4$ SYM. But a CFT need not be defined by a weakly coupled Lagrangian. In modern CFT, the deeper object is the operator algebra.

The OPE turns the product of two local measurements into a sum over possible local outcomes. Four-point functions can be decomposed in different OPE channels. For identical scalar operators,

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\mathcal O(x_4)\rangle
=
\frac{1}{x_{12}^{2\Delta}x_{34}^{2\Delta}}\,\mathcal G(u,v),
$$

where the conformal cross-ratios are

$$
u = \frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v = \frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The same four-point function can be expanded in the $12\to34$ channel or in the $14\to23$ channel. Equality of these descriptions is crossing symmetry. Schematically,

$$
\sum_{\mathcal O_k} C_{\mathcal O\mathcal O k}^2\,G_{\Delta_k,\ell_k}(u,v)
=
\sum_{\mathcal O_k} C_{\mathcal O\mathcal O k}^2\,G_{\Delta_k,\ell_k}(v,u),
$$

up to conventional prefactors. This is the bootstrap equation.

In AdS, the same equality is read as consistency of different bulk exchange processes. The bootstrap is therefore not merely a CFT game. It is a nonperturbative consistency condition on quantum gravity in AdS.

> **AdS/CFT checkpoint.** In a holographic CFT, bulk locality is encoded in special properties of CFT four-point functions. Conformal blocks organize boundary operator exchange; Witten diagrams organize bulk particle exchange. The fact that these two languages fit together is one of the miracles of the correspondence.

## Why two-dimensional CFT is important, but not enough

Two-dimensional CFT is exceptionally powerful because the conformal algebra enhances to two copies of the Virasoro algebra:

$$
\text{Virasoro}\times \overline{\text{Virasoro}}.
$$

This infinite-dimensional symmetry makes many 2D CFTs exactly solvable. It is essential for string worldsheet theory, minimal models, WZW models, modular invariance, Cardy growth, and $AdS_3/CFT_2$.

But a course preparing for AdS/CFT cannot be only a classic 2D CFT course. The canonical example of AdS/CFT is

$$
\mathcal N=4\; SU(N)\;\text{super Yang-Mills in }d=4
\quad \leftrightarrow \quad
\text{type IIB string theory on }AdS_5\times S^5.
$$

For this, the most important CFT tools are higher-dimensional: conformal representation theory, Ward identities, spinning correlators, OPE convergence, conformal blocks, supersymmetry, large $N$, and the structure of single-trace operators.

Thus this course treats 2D CFT as a crucial module, not as the whole subject. The logic is:

$$
\text{higher-dimensional CFT structure first, 2D exact methods second, holographic CFTs throughout.}
$$

## The first dictionary, with caveats

It is useful to memorize the first version of the dictionary early, as long as one also memorizes its caveats.

| Boundary CFT | Bulk AdS |
|---|---|
| spacetime dimension $d$ | spacetime dimension $d+1$ |
| conformal group $SO(d,2)$ | AdS isometry group $SO(d,2)$ |
| local primary $\mathcal O_i$ | bulk field $\phi_i$ |
| source $J_i$ for $\mathcal O_i$ | boundary value of $\phi_i$ |
| scaling dimension $\Delta_i$ | AdS energy or bulk mass |
| $T_{\mu\nu}$ | metric fluctuation, graviton |
| conserved current $J_\mu$ | bulk gauge field |
| global symmetry | bulk gauge symmetry |
| large $N$ | weak bulk coupling |
| sparse spectrum | local bulk EFT |
| finite-temperature state | black hole or thermal gas in AdS |
| entanglement entropy | extremal surface area plus corrections |

The caveats are just as important:

1. The CFT is not living “inside” the bulk in an ordinary local way. It is a complete alternative description.
2. Boundary global symmetries become bulk gauge symmetries, not bulk global symmetries.
3. A simple classical bulk exists only for special CFTs.
4. Bulk locality is approximate and emergent.
5. The dictionary is most transparent at large $N$ and strong coupling, but the equivalence is expected to be exact when both sides are properly defined.

## What one must learn before AdS/CFT becomes natural

This course is designed around the CFT ideas that later become indispensable in holography.

First, we need RG and fixed points. A CFT is a QFT at a fixed point, and AdS radial evolution is deeply tied to scale evolution. The stress-tensor trace relation

$$
T^\mu{}_{\mu}\sim \sum_i \beta_i\mathcal O_i
$$

is one of the cleanest ways to understand why conformality means vanishing beta functions, up to anomalies and improvement subtleties.

Second, we need conformal representation theory. Bulk particles correspond to CFT representations. Conserved currents and the stress tensor correspond to shortened multiplets. Unitarity bounds become positivity and stability constraints.

Third, we need correlation functions and Ward identities. These are the actual observables computed by bulk boundary-value problems.

Fourth, we need the OPE and conformal blocks. They are the CFT language of locality, factorization, and exchange.

Fifth, we need large $N$. Without it, one may still have holography, but not a weakly curved classical bulk.

Sixth, we need supersymmetry and $\mathcal N=4$ SYM. They are not merely decorative. Supersymmetry gives protected data, exactly marginal couplings, BPS sectors, and the most controlled examples of AdS/CFT.

## A useful mental model

A CFT is like a complete table of possible local measurements and their multiplication rules. The spectrum tells us what can exist. The OPE coefficients tell us how things interact. Crossing symmetry tells us whether the algebra is consistent.

AdS/CFT says that, for special CFTs, this table can be reorganized into a higher-dimensional gravitational theory. The bulk is not an extra assumption; it is a different basis for the same quantum data.

In this mental model,

$$
\begin{aligned}
\text{spectrum} &\longrightarrow \text{particle content},\\
\text{OPE coefficients} &\longrightarrow \text{interaction vertices},\\
\text{large }N\text{ factorization} &\longrightarrow \text{classical limit},\\
\text{crossing symmetry} &\longrightarrow \text{bulk consistency},\\
\text{stress tensor} &\longrightarrow \text{dynamical geometry}.
\end{aligned}
$$

Once this becomes natural, AdS/CFT stops looking like a surprising dictionary and starts looking like the most efficient organization of CFT data.

## Common traps

A few misconceptions are worth eliminating immediately.

**Trap 1: “Conformal symmetry determines the whole CFT.”**

No. Symmetry fixes the form of two- and three-point functions up to constants, but the spectrum and OPE coefficients are dynamical. The CFT data are highly nontrivial.

**Trap 2: “All CFTs have Einstein gravity duals.”**

No. A simple weakly curved gravity dual requires large $N$, sparse low-dimension single-trace spectrum, and strong coupling in the right sense.

**Trap 3: “The radial coordinate is just another spacetime coordinate added by hand.”**

No. In holography the radial direction is encoded in scale, energy, and RG structure on the boundary.

**Trap 4: “The CFT is only the boundary condition for the bulk.”**

No. The CFT is the complete quantum theory. The bulk is an emergent gravitational description of certain CFT observables.

**Trap 5: “The dictionary is a list of pairings.”**

The pairings are only the beginning. The real dictionary is the equality of generating functionals, Hilbert spaces, symmetries, spectra, and correlation functions.

## Summary

The reason to learn CFT before AdS/CFT is not historical convenience. It is structural necessity.

A CFT gives us:

- a Hilbert space organized by conformal representations,
- local operators with dimensions and spins,
- correlation functions constrained by symmetry,
- an OPE that defines the local operator algebra,
- Ward identities generated by conserved currents and the stress tensor,
- crossing equations expressing associativity,
- special large-$N$ limits that can produce semiclassical bulk physics.

AdS/CFT then says that, for special CFTs, this data admits a dual description as quantum gravity in one higher dimension. The task of this course is to make each item precise enough that the holographic dictionary becomes inevitable.

## Exercises

### Exercise 1. The AdS scaling isometry

Show that the Poincare-patch AdS metric

$$
ds^2 = \frac{R^2}{z^2}\left(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu\right)
$$

is invariant under

$$
z\to \lambda z,
\qquad
x^\mu\to \lambda x^\mu.
$$

Explain why this suggests a relation between the radial coordinate and the boundary RG scale.

<details><summary><strong>Solution</strong></summary>

Under the transformation,

$$
dz\to \lambda dz,
\qquad
 dx^\mu\to \lambda dx^\mu.
$$

The numerator transforms as

$$
dz^2+\eta_{\mu\nu}dx^\mu dx^\nu
\to
\lambda^2\left(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu\right),
$$

while the denominator transforms as

$$
z^2\to \lambda^2 z^2.
$$

The two factors cancel, so $ds^2$ is invariant. Since $z$ scales like a length, moving toward smaller $z$ corresponds to probing shorter boundary distances, or higher boundary energy. This is the first geometric hint that the AdS radial direction is related to the RG scale of the boundary CFT.

</details>

### Exercise 2. Two-point functions from scale invariance

Let $\mathcal O$ be a scalar primary of scaling dimension $\Delta$ in a Euclidean CFT. Assume translation and rotation invariance, so

$$
\langle \mathcal O(x)\mathcal O(0)\rangle = f(|x|).
$$

Use scale invariance to show that

$$
f(|x|)=\frac{C}{|x|^{2\Delta}}.
$$

<details><summary><strong>Solution</strong></summary>

Scale invariance gives

$$
\mathcal O(x)\to \lambda^{-\Delta}\mathcal O(\lambda^{-1}x).
$$

Equivalently, the two-point function must obey

$$
f(\lambda |x|)=\lambda^{-2\Delta}f(|x|).
$$

Set $r=|x|$ and choose $\lambda=1/r$. Then

$$
f(1)=r^{2\Delta}f(r),
$$

so

$$
f(r)=\frac{f(1)}{r^{2\Delta}}.
$$

Writing $C=f(1)$ gives the desired result.

</details>

### Exercise 3. Scalar mass and boundary dimension

A scalar field in $AdS_{d+1}$ obeys

$$
(\nabla^2-m^2)\phi=0.
$$

Near the boundary of the Poincare patch, ignore boundary derivatives and use the ansatz

$$
\phi(z,x)\sim z^\alpha.
$$

Show that

$$
\alpha(\alpha-d)=m^2R^2.
$$

Conclude that the two possible exponents are

$$
\alpha=\Delta_\pm=\frac d2\pm \sqrt{\frac{d^2}{4}+m^2R^2}.
$$

<details><summary><strong>Solution</strong></summary>

For the metric

$$
ds^2=\frac{R^2}{z^2}(dz^2+dx^\mu dx_\mu),
$$

the radial part of the scalar Laplacian near the boundary is

$$
\nabla^2\phi
\sim
\frac{1}{R^2}\left(z^2\partial_z^2-(d-1)z\partial_z\right)\phi.
$$

For $\phi\sim z^\alpha$,

$$
z\partial_z\phi=\alpha z^\alpha,
\qquad
z^2\partial_z^2\phi=\alpha(\alpha-1)z^\alpha.
$$

Thus

$$
\nabla^2\phi
\sim
\frac{1}{R^2}\left[\alpha(\alpha-1)-(d-1)\alpha\right]z^\alpha
=
\frac{\alpha(\alpha-d)}{R^2}z^\alpha.
$$

The equation $(\nabla^2-m^2)\phi=0$ therefore gives

$$
\alpha(\alpha-d)=m^2R^2.
$$

Solving the quadratic equation gives

$$
\alpha=\frac d2\pm \sqrt{\frac{d^2}{4}+m^2R^2}.
$$

In standard quantization, the larger root is identified with the CFT scaling dimension $\Delta$ of the dual scalar operator.

</details>

### Exercise 4. Why factorization suggests classical bulk physics

Suppose normalized single-trace operators obey the large-$N$ scaling

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_{\rm conn}\sim N^{2-n}.
$$

Explain why this resembles a weakly coupled classical theory in the bulk.

<details><summary><strong>Solution</strong></summary>

For $n>2$, connected correlators are suppressed by powers of $1/N$. This means that, at leading order in large $N$, higher-point functions factorize into products of two-point functions. Such factorization is the hallmark of a classical or weakly interacting theory: fluctuations and connected interactions are small.

In the bulk interpretation, $1/N$ plays the role of a loop-counting parameter. Tree-level diagrams survive at leading nontrivial order, while loop corrections are suppressed. Thus large-$N$ factorization is the CFT signal of semiclassical bulk dynamics.

</details>

### Exercise 5. Source versus expectation value

In the near-boundary expansion

$$
\phi(z,x)\sim z^{d-\Delta}J(x)+z^\Delta A(x),
$$

which coefficient is interpreted as the source, and which is related to the expectation value? Why is this distinction natural from the CFT generating functional?

<details><summary><strong>Solution</strong></summary>

In standard quantization, $J(x)$ is the source for the CFT operator $\mathcal O(x)$. The coefficient $A(x)$ is related to the expectation value $\langle \mathcal O(x)\rangle$, after holographic renormalization.

This matches the CFT generating functional because a source appears as the coefficient of the deformation

$$
\int d^d x\,J(x)\mathcal O(x).
$$

Differentiating $W_{\rm CFT}[J]=\log Z_{\rm CFT}[J]$ with respect to $J(x)$ gives the response,

$$
\frac{\delta W_{\rm CFT}}{\delta J(x)}=\langle \mathcal O(x)\rangle_J.
$$

Thus the bulk distinction between boundary condition and response is the gravitational version of the CFT distinction between source and one-point function.

</details>

## Further reading

For the CFT side, use Rychkov's and Simmons-Duffin's lectures for modern higher-dimensional CFT and bootstrap ideas. Use Di Francesco, Mathieu, and Senechal for the 2D CFT machinery: Virasoro symmetry, minimal models, modular invariance, WZW models, and cosets. For AdS/CFT itself, the classic starting points are Maldacena's original paper, the Gubser-Klebanov-Polyakov and Witten dictionary papers, and modern lecture notes on holographic renormalization, large-$N$ CFT, and black-hole thermodynamics.
