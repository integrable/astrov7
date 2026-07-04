---
title: "Brown–Henneaux central charge"
description: "A detailed derivation and interpretation of the Brown–Henneaux central charge c = 3L/(2G_3) in AdS3/CFT2."
sidebar:
  order: 20
---

The Brown–Henneaux central charge is one of the most important formulas in holography:

$$
\boxed{c_L=c_R=\frac{3L}{2G_3}}.
$$

It turns the geometric ratio $L/G_3$ into the central charge of a two-dimensional conformal field theory. In higher-dimensional AdS/CFT, the statement “large $N$ means classical gravity” is often expressed by formulas such as $L^{d-1}/G_{d+1}\sim N^2$. In AdS$_3$/CFT$_2$, the corresponding statement is sharper:

$$
\frac{L}{G_3}\gg 1
\quad\Longleftrightarrow\quad
c\gg 1.
$$

The goal of this page is to explain what is being computed, why a classical central charge can appear at all, and how the result fits into the holographic dictionary.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Brown-Henneaux central charge](/figures/course/brown-henneaux-central-charge.svg)

<figcaption>

Brown–Henneaux boundary conditions allow two functions of one light-cone coordinate, producing two Virasoro algebras. The canonical charge algebra has central charge $c=3L/(2G_3)=6k$, where $k=L/(4G_3)$ is the Chern–Simons level.

</figcaption>
</figure>

## The problem Brown and Henneaux solved

Start with three-dimensional Einstein gravity with negative cosmological constant:

$$
I
=
\frac{1}{16\pi G_3}
\int_M d^3x\sqrt{-g}\left(R+\frac{2}{L^2}\right)
+
I_{\mathrm{GHY}}
+
I_{\mathrm{ct}}.
$$

The global AdS$_3$ metric is

$$
ds^2
=
L^2\left(
-\cosh^2\rho\,d\tau^2
+
d\rho^2
+
\sinh^2\rho\,d\phi^2
\right),
\qquad
\phi\sim\phi+2\pi.
$$

The conformal boundary is the cylinder $\mathbb R_\tau\times S^1_\phi$. Introduce light-cone coordinates

$$
x^+=\tau+\phi,
\qquad
x^-=\tau-\phi.
$$

The exact isometry group of AdS$_3$ is

$$
SO(2,2)
\simeq
SL(2,\mathbb R)_L\times SL(2,\mathbb R)_R.
$$

This is finite-dimensional. Brown and Henneaux asked a more subtle question:

> What is the algebra of diffeomorphisms that preserve asymptotically AdS$_3$ boundary conditions and have well-defined canonical charges?

The answer is not merely $SO(2,2)$. It is two copies of the Virasoro algebra.

## Boundary conditions

A convenient large-radius form of asymptotically AdS$_3$ metrics is

$$
ds^2
\sim
L^2\frac{dr^2}{r^2}
+
r^2\,\eta_{ij}dx^i dx^j
+
\text{subleading terms},
$$

where $i,j$ run over the two boundary directions. Brown–Henneaux boundary conditions allow the leading boundary metric to be fixed while permitting certain finite subleading fluctuations.

In light-cone coordinates, a standard schematic version of the falloffs is

$$
g_{+-}=-\frac{r^2}{2}+O(1),
\qquad
g_{rr}=\frac{L^2}{r^2}+O(r^{-4}),
$$

$$
g_{++}=O(1),
\qquad
g_{--}=O(1),
\qquad
g_{r+}=O(r^{-3}),
\qquad
g_{r-}=O(r^{-3}).
$$

The precise numerical factors depend on coordinate conventions. The essential point is that the leading boundary conformal class is fixed, while the $O(1)$ components $g_{++}$ and $g_{--}$ are allowed to fluctuate. These subleading pieces encode the boundary stress tensor.

## Asymptotic diffeomorphisms

The diffeomorphisms preserving these falloffs are parameterized by two arbitrary functions,

$$
\epsilon^+(x^+),
\qquad
\epsilon^-(x^-).
$$

Their leading action near the boundary is

$$
\xi^+ = \epsilon^+(x^+) + O(r^{-2}),
$$

$$
\xi^- = \epsilon^-(x^-) + O(r^{-2}),
$$

$$
\xi^r
=
-\frac{r}{2}
\left(\partial_+\epsilon^+ + \partial_-\epsilon^-\right)
+
O(r^{-1}).
$$

The first two components are boundary conformal transformations. The radial component is forced on us: it compensates the boundary Weyl rescaling so that the metric remains in the allowed asymptotically AdS form.

Choosing Fourier modes

$$
\epsilon^+_n=e^{inx^+},
\qquad
\epsilon^-_n=e^{inx^-},
$$

the corresponding vector fields obey two copies of the Witt algebra:

$$
[\ell_m,\ell_n]=(m-n)\ell_{m+n},
$$

$$
[\bar\ell_m,\bar\ell_n]=(m-n)\bar\ell_{m+n},
\qquad
[\ell_m,\bar\ell_n]=0.
$$

This is the classical algebra of conformal vector fields before central extension.

## Why a central charge can appear

At first sight, a central charge in a classical gravity calculation sounds strange. Central charges are often introduced in quantum CFT. Brown–Henneaux central charge is different in origin: it appears in the classical Poisson-bracket algebra of canonical surface charges.

In a gauge theory on a noncompact space, a gauge transformation with nonzero behavior at infinity can carry a boundary charge. Schematically, the generator has the form

$$
H[\xi]
=
\int_\Sigma \xi^\mu \mathcal C_\mu
+
Q[\xi],
$$

where $\mathcal C_\mu$ are constraints and $Q[\xi]$ is a boundary term required for a well-defined variation.

On shell, the constraints vanish, but the boundary charge remains:

$$
H[\xi]_{\mathrm{on\ shell}}=Q[\xi].
$$

The Poisson brackets of these charges can contain a field-independent term:

$$
\{Q[\xi],Q[\eta]\}
=
Q[[\xi,\eta]]+K[\xi,\eta].
$$

The cocycle $K[\xi,\eta]$ is the classical central extension. It cannot be removed by redefining the charges if it is cohomologically nontrivial.

This is what happens for AdS$_3$ with Brown–Henneaux boundary conditions.

## The Virasoro charge algebra

The quantum version of the resulting algebra is

$$
[L_m,L_n]
=
(m-n)L_{m+n}
+
\frac{c}{12}m(m^2-1)\delta_{m+n,0},
$$

$$
[\bar L_m,\bar L_n]
=
(m-n)\bar L_{m+n}
+
\frac{\bar c}{12}m(m^2-1)\delta_{m+n,0},
$$

$$
[L_m,\bar L_n]=0.
$$

For parity-invariant Einstein gravity,

$$
c=\bar c=\frac{3L}{2G_3}.
$$

The form $m(m^2-1)$ is the cylinder convention in which the global subalgebra generated by $L_{-1},L_0,L_1$ has no central term. In a classical Poisson-bracket convention one often sees an $m^3$ central term; the two forms differ by a shift of the zero mode, which corresponds physically to the Casimir energy of the CFT on the cylinder.

## A stress-tensor way to see the answer

Holographic renormalization gives a boundary stress tensor by varying the renormalized gravitational action with respect to the boundary metric:

$$
\langle T^{ij}\rangle
=
\frac{2}{\sqrt{-g_{(0)}}}
\frac{\delta S_{\mathrm{ren}}}{\delta g_{(0)ij}}.
$$

In Fefferman–Graham coordinates for AdS$_3$,

$$
ds^2
=
L^2d\rho^2
+
g_{ij}(\rho,x)dx^i dx^j,
$$

with

$$
g_{ij}(\rho,x)
=
e^{2\rho}g_{(0)ij}(x)
+
g_{(2)ij}(x)
+
e^{-2\rho}g_{(4)ij}(x).
$$

In two boundary dimensions, $g_{(2)ij}$ contains the stress tensor data. For a flat boundary cylinder and no additional sources, the left- and right-moving components are functions of one variable:

$$
T_{++}=T_{++}(x^+),
\qquad
T_{--}=T_{--}(x^-).
$$

Under an infinitesimal conformal transformation generated by $\epsilon^+(x^+)$, a CFT stress tensor transforms as

$$
\delta_\epsilon T_{++}
=
\epsilon^+\partial_+T_{++}
+
2(\partial_+\epsilon^+)T_{++}
-
\frac{c}{12}\partial_+^3\epsilon^+,
$$

up to conventional factors of $2\pi$ depending on the normalization of $T$. The same transformation can be computed from the asymptotic diffeomorphism acting on the Fefferman–Graham coefficient $g_{(2)++}$. Comparing the coefficient of $\partial_+^3\epsilon^+$ gives

$$
c=\frac{3L}{2G_3}.
$$

This route is conceptually useful because it shows that the central charge is also the coefficient of the two-dimensional Weyl anomaly.

## A Chern–Simons way to remember the answer

Three-dimensional AdS gravity can be written as

$$
I_{\mathrm{grav}}
=
I_{\mathrm{CS}}[A]-I_{\mathrm{CS}}[\bar A],
$$

where

$$
A=\omega+\frac{1}{L}e,
\qquad
\bar A=\omega-\frac{1}{L}e,
$$

and the gauge group is

$$
SL(2,\mathbb R)_L\times SL(2,\mathbb R)_R.
$$

The Chern–Simons level is

$$
k=\frac{L}{4G_3}.
$$

With Brown–Henneaux boundary conditions, the boundary symmetry obtained from the Chern–Simons theory is Virasoro with

$$
c=6k.
$$

Therefore

$$
c=6\left(\frac{L}{4G_3}\right)=\frac{3L}{2G_3}.
$$

This derivation is compact and memorable. It also explains why a bulk topological theory can produce a boundary conformal symmetry: Chern–Simons theory has no local bulk propagating modes, but it induces boundary degrees of freedom when the manifold has a boundary.

## Why the answer is finite

The central charge is dimensionless, as it must be. In three bulk dimensions,

$$
[G_3]=\text{length},
$$

so $L/G_3$ is dimensionless. This is special to AdS$_3$/CFT$_2$. In higher dimensions the analogous dimensionless measure of gravitational coupling is $L^{d-1}/G_{d+1}$.

The formula

$$
c=\frac{3L}{2G_3}
$$

also tells us when the classical gravity approximation is reliable:

$$
c\gg 1.
$$

At finite $c$, quantum-gravity effects are not suppressed. In stringy AdS$_3$ backgrounds, there may also be string-scale corrections and additional light degrees of freedom. The Brown–Henneaux formula is still a robust asymptotic statement for Einstein gravity, but the full spectrum of the dual CFT depends on the complete theory.

## Relation to the Weyl anomaly

In a two-dimensional CFT, the trace anomaly on a curved background is

$$
\langle T^i{}_i\rangle
=
-\frac{c}{24\pi}R[g_{(0)}]
$$

in a common Lorentzian convention. Holographic renormalization of AdS$_3$ gravity gives precisely this anomaly with

$$
c=\frac{3L}{2G_3}.
$$

This is another way to see that $c$ measures the coefficient of the stress-tensor sector. It appears in:

- the Virasoro algebra;
- the stress-tensor two-point function;
- the Weyl anomaly;
- the Cardy density of states;
- the BTZ black-hole entropy.

This unity is one reason AdS$_3$/CFT$_2$ is so powerful.

## Global AdS$_3$ and the cylinder vacuum

The plane and cylinder descriptions of a CFT differ by a conformal transformation. The stress tensor is not a primary operator; it transforms with a Schwarzian derivative. As a result, the vacuum on the plane maps to a state on the cylinder with Casimir energy.

In cylinder Virasoro conventions, the global AdS$_3$ vacuum corresponds to

$$
L_0=\bar L_0=-\frac{c}{24}
$$

before shifting to the standard CFT Hamiltonian convention in which the vacuum state has $L_0=\bar L_0=0$ and the cylinder Hamiltonian includes $-c/12$ Casimir energy. Different gravity papers distribute this constant in slightly different ways, so one must always check the zero-mode convention.

The invariant lesson is this:

$$
\text{the } -\frac{c}{24}\text{ shift is the cylinder Casimir energy.}
$$

It is not a mysterious extra black-hole contribution.

## Boundary conditions matter

The Brown–Henneaux result is not independent of boundary conditions. It follows from a specific, physically natural set of asymptotically AdS$_3$ falloffs that fix the boundary conformal class and allow finite stress-tensor excitations.

Other consistent boundary conditions can produce different asymptotic symmetry algebras, such as Virasoro–Kac–Moody structures or enhanced algebras. These are important in modern three-dimensional gravity, warped holography, and chiral boundary-condition studies.

For this foundations course, however, “AdS$_3$/CFT$_2$” means the Brown–Henneaux setup unless stated otherwise.

## What the central charge does for holography

The Brown–Henneaux formula is not only an elegant symmetry result. It is the number that makes the rest of the AdS$_3$/CFT$_2$ dictionary work.

### Stress-tensor normalization

The two-point function of the CFT stress tensor is fixed by $c$:

$$
\langle T(z)T(0)\rangle
=
\frac{c/2}{z^4}.
$$

On the gravity side, this normalization is controlled by $1/G_3$.

### Entanglement entropy

For an interval of length $\ell$ in the CFT vacuum,

$$
S_A
=
\frac{c}{3}\log\frac{\ell}{\epsilon}.
$$

The RT geodesic calculation gives

$$
S_A
=
\frac{\mathrm{Length}(\gamma_A)}{4G_3}.
$$

Using $c=3L/(2G_3)$ makes the two answers match.

### BTZ entropy

The Cardy formula for a high-energy CFT$_2$ state is controlled by $c$. With the Brown–Henneaux value, it reproduces the Bekenstein–Hawking entropy of the BTZ black hole:

$$
S_{\mathrm{BTZ}}
=
\frac{\mathrm{Length}(\mathrm{horizon})}{4G_3}.
$$

This is the central payoff of the next two pages.

## Dictionary checkpoint

The Brown–Henneaux page refines the dictionary as follows:

| Gravity quantity | CFT$_2$ quantity |
|---|---|
| $L/G_3$ | central charge $c$ |
| $G_3/L\ll 1$ | large-$c$ limit |
| Brown–Henneaux diffeomorphisms | local conformal transformations |
| canonical surface charges | Virasoro generators |
| classical central extension | CFT central charge |
| global $SO(2,2)$ isometries | $SL(2,\mathbb R)_L\times SL(2,\mathbb R)_R$ global conformal subgroup |
| $g_{(2)++},g_{(2)--}$ | $T_{++},T_{--}$ |
| Chern–Simons level $k=L/(4G_3)$ | $c/6$ |

## Common confusions

### “The central charge is quantum, so it cannot appear classically.”

The Brown–Henneaux central charge appears in the classical Poisson-bracket algebra of surface charges. The corresponding quantum algebra is the Virasoro algebra. Classical central extensions are common in systems with boundaries and nontrivial charge algebras.

### “The Virasoro algebra is generated by exact Killing vectors.”

Only the global $SL(2,\mathbb R)_L\times SL(2,\mathbb R)_R$ subalgebra corresponds to exact AdS$_3$ Killing vectors. The full Virasoro algebra comes from asymptotic Killing vectors that preserve the boundary conditions but generally change the state.

### “Changing coordinates can create physical gravitons.”

A small diffeomorphism with zero charge is gauge. A large diffeomorphism with nonzero Brown–Henneaux charge creates a distinct physical boundary-graviton state. The distinction is not local curvature; it is the boundary charge.

### “Every AdS$_3$ theory has $c_L=c_R$.”

Parity-invariant Einstein gravity has $c_L=c_R$. Theories with gravitational Chern–Simons terms, such as topologically massive gravity, can have $c_L\ne c_R$. The Brown–Henneaux formula here is for pure Einstein gravity with negative cosmological constant.

## Exercises

### Exercise 1: The global conformal subalgebra

Show that the central term

$$
\frac{c}{12}m(m^2-1)\delta_{m+n,0}
$$

vanishes for $m=-1,0,1$. Why is this physically expected?

<details>
<summary><strong>Solution</strong></summary>

For $m=-1,0,1$,

$$
m(m^2-1)=0.
$$

Therefore the central term vanishes on the modes $L_{-1},L_0,L_1$. These modes generate the global conformal group $SL(2,\mathbb R)$, which is the exact isometry subgroup of AdS$_3$ in one chiral sector. It is physically expected that the exact finite-dimensional isometry algebra is represented without a central extension in these cylinder conventions.

</details>

### Exercise 2: Central charge from the Chern–Simons level

Use

$$
k=\frac{L}{4G_3},
\qquad
c=6k,
$$

to derive the Brown–Henneaux central charge.

<details>
<summary><strong>Solution</strong></summary>

Substitute the gravitational Chern–Simons level into $c=6k$:

$$
c=6\left(\frac{L}{4G_3}\right)
=
\frac{6L}{4G_3}
=
\frac{3L}{2G_3}.
$$

Thus the Chern–Simons normalization of AdS$_3$ gravity gives exactly the Brown–Henneaux central charge.

</details>

### Exercise 3: Semiclassical gravity and large central charge

Suppose $L/G_3=200$. What is the Brown–Henneaux central charge? Is the bulk expected to be semiclassical?

<details>
<summary><strong>Solution</strong></summary>

The central charge is

$$
c=\frac{3L}{2G_3}
=
\frac32\frac{L}{G_3}
=
\frac32(200)=300.
$$

This is large compared with one, so quantum fluctuations of the metric are parametrically suppressed. Whether the bulk is accurately described by pure Einstein gravity also depends on the absence of additional light stringy or matter degrees of freedom, but $c\gg1$ is the basic semiclassical condition in the gravitational sector.

</details>

### Exercise 4: Why the zero-mode shift matters

The plane Virasoro algebra is often written with central term proportional to $m^3$, while the cylinder algebra is often written with $m(m^2-1)$. Explain the origin of the difference.

<details>
<summary><strong>Solution</strong></summary>

The difference comes from shifting the zero mode by a constant. The conformal map from the plane to the cylinder produces a Schwarzian derivative in the stress-tensor transformation. This creates the cylinder Casimir energy. In Virasoro language, the shift changes

$$
L_0\to L_0-\frac{c}{24}
$$

or the inverse, depending on convention. The $m^3$ and $m(m^2-1)$ forms are the same central extension expressed with different zero-mode normalizations. The cylinder form is useful because the global $SL(2,\mathbb R)$ subalgebra has no central term.

</details>

## Further reading

- J. D. Brown and M. Henneaux, [Central Charges in the Canonical Realization of Asymptotic Symmetries: An Example from Three-Dimensional Gravity](https://ui.adsabs.harvard.edu/abs/1986CMaPh.104..207B/abstract).
- M. Henneaux and C. Teitelboim, [Asymptotically anti-de Sitter Spaces](https://projecteuclid.org/journals/communications-in-mathematical-physics/volume-98/issue-3/Asymptotically-anti-de-Sitter-spaces/cmp/1103942446.full).
- M. Bañados, [Three-Dimensional Quantum Geometry and Black Holes](https://arxiv.org/abs/hep-th/9901148).
- O. Coussaert, M. Henneaux, and P. van Driel, [The Asymptotic Dynamics of Three-Dimensional Einstein Gravity with a Negative Cosmological Constant](https://arxiv.org/abs/gr-qc/9506019).
- V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).
- K. Skenderis and S. N. Solodukhin, [Quantum Effective Action from the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/9910023).
- E. Witten, [Three-Dimensional Gravity Revisited](https://arxiv.org/abs/0706.3359).
