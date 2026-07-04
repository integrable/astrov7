---
title: "Notation"
description: "A compact convention sheet for spacetime indices, CFT data, two-dimensional notation, large-N counting, and AdS/CFT symbols."
sidebar:
  order: 1
---

This appendix fixes the notation used throughout **Modern CFT for AdS/CFT**. The goal is not to impose a universal convention on the literature. The goal is more practical: when a symbol appears on this site, the reader should know what it means, which signature is being used, and which normalization choices are implicit.

The most important convention is this one:

> Unless explicitly stated otherwise, CFT formulas are written in **Euclidean signature**. Lorentzian signature is introduced when discussing causality, real-time correlators, thermal response, unitarity, or bulk spacetime physics.

This is the least painful convention for a CFT course aimed at AdS/CFT. Euclidean CFT is where conformal symmetry, OPE convergence, radial quantization, conformal blocks, modular invariance, and many exact formulas are cleanest. Lorentzian CFT is where causality, commutators, spectral functions, black holes, chaos, and bulk locality become sharp.

## Spacetime conventions

The boundary CFT dimension is denoted by $d$. The dual bulk, when present, has dimension $d+1$.

### Euclidean CFT

Euclidean coordinates are

$$
x^\mu, \qquad \mu=1,\ldots,d.
$$

The metric is

$$
\delta_{\mu\nu}=\operatorname{diag}(1,\ldots,1),
\qquad
x^2=\delta_{\mu\nu}x^\mu x^\nu.
$$

Repeated spacetime indices are summed. We use

$$
x_{ij}^\mu=x_i^\mu-x_j^\mu,
\qquad
x_{ij}^2=(x_i-x_j)^2,
\qquad
x_{ij}=|x_i-x_j|.
$$

For scalar CFT correlators, powers such as $x_{ij}^{2\Delta}$ always mean $(x_{ij}^2)^\Delta$.

### Lorentzian CFT

Lorentzian coordinates are

$$
x^\mu=(t,\mathbf x),
\qquad
\mu=0,1,\ldots,d-1.
$$

The metric convention is mostly plus:

$$
\eta_{\mu\nu}=\operatorname{diag}(-,+,\ldots,+),
\qquad
x^2=-t^2+|\mathbf x|^2.
$$

The Lorentzian separation between two points is

$$
x_{ij}^2=-(t_i-t_j)^2+|\mathbf x_i-\mathbf x_j|^2.
$$

For Lorentzian correlators, the formula $1/(x^2)^\Delta$ is incomplete until the operator ordering is specified. The Wightman ordering is encoded by an $i\epsilon$ prescription. For example, for a scalar primary in the vacuum,

$$
\langle \mathcal O(t,\mathbf x)\mathcal O(0)\rangle
=
\frac{C_{\mathcal O}}{[-(t-i\epsilon)^2+|\mathbf x|^2]^\Delta}.
$$

Retarded correlators are denoted by

$$
G_R(t,\mathbf x)
=
-i\theta(t)\langle [\mathcal O(t,\mathbf x),\mathcal O(0)]\rangle.
$$

### Curved backgrounds

A curved Euclidean or Lorentzian metric is denoted by $g_{\mu\nu}$. The determinant is $g=\det g_{\mu\nu}$, and the volume element is

$$
\sqrt{|g|}\,d^d x.
$$

For Euclidean metrics, $\sqrt{|g|}=\sqrt{g}$. For Lorentzian metrics, $g<0$ in standard coordinates, hence $\sqrt{|g|}=\sqrt{-g}$.

Curvature conventions are used only when needed. The Ricci scalar is denoted by $R$. The Weyl tensor is denoted by $W_{\mu\nu\rho\sigma}$.

## Index conventions

The following table summarizes the default use of indices.

| Symbol | Meaning |
|---|---|
| $\mu,\nu,\rho,\sigma$ | Boundary spacetime indices |
| $M,N,P,Q$ | Bulk spacetime indices |
| $A,B,C$ | Embedding-space indices or adjoint/global-symmetry indices, depending on context |
| $a,b,c$ | Local frame indices or Lie-algebra indices, depending on context |
| $i,j,k$ | Operator labels, lattice labels, or generic discrete labels |
| $I,J,K$ | $R$-symmetry vector indices, especially $SO(6)_R$ in $\mathcal N=4$ SYM |
| $\alpha,\dot\alpha$ | Four-dimensional spinor indices |
| $r,s$ | Two-dimensional Virasoro/Kac-table labels or radial coordinates, depending on context |

When two uses could collide, the text will say so explicitly. For example, $A,B$ are convenient both for embedding-space indices and for Lie-algebra adjoint indices. On pages where both appear, embedding-space indices are usually written as $A,B=-1,0,1,\ldots,d$, while adjoint indices are written as $a,b,c$.

Symmetrization and antisymmetrization use unit weight:

$$
A_{(\mu\nu)}=\frac12(A_{\mu\nu}+A_{\nu\mu}),
\qquad
A_{[\mu\nu]}=\frac12(A_{\mu\nu}-A_{\nu\mu}).
$$

The traceless symmetric part is sometimes denoted schematically by angle brackets:

$$
A_{\langle\mu\nu\rangle}
=
A_{(\mu\nu)}-\frac1d\delta_{\mu\nu}A^\rho{}_{\rho}
$$

in Euclidean signature. The precise projector is written explicitly when needed.

## Fourier transform conventions

The default Fourier transform is

$$
\mathcal O(p)=\int d^d x\,e^{-ip\cdot x}\mathcal O(x),
$$

with inverse

$$
\mathcal O(x)=\int\frac{d^d p}{(2\pi)^d}\,e^{ip\cdot x}\mathcal O(p).
$$

Thus

$$
\int d^d x\,e^{ip\cdot x}=(2\pi)^d\delta^{(d)}(p),
$$

and momentum conservation in an $n$-point function is written as

$$
\langle \mathcal O_1(p_1)\cdots \mathcal O_n(p_n)\rangle
=(2\pi)^d\delta^{(d)}(p_1+\cdots+p_n)
\langle \mathcal O_1(p_1)\cdots \mathcal O_n(p_n)\rangle'.
$$

The prime means that the momentum-conserving delta function has been stripped off.

## CFT operator conventions

A local operator is denoted by

$$
\mathcal O_i(x).
$$

The label $i$ includes all discrete quantum numbers: scaling dimension, spin, global-symmetry representation, parity, charge, and possible degeneracy label. A primary operator is characterized by

$$
(\Delta_i,\ell_i,\mathcal R_i),
$$

where $\Delta_i$ is the scaling dimension, $\ell_i$ is the spin for symmetric traceless tensors, and $\mathcal R_i$ is a representation of any internal global symmetry.

A scalar primary transforms under Euclidean dilatations as

$$
\mathcal O(x)\mapsto \lambda^{-\Delta}\mathcal O(\lambda^{-1}x),
$$

or equivalently

$$
\mathcal O(\lambda x)=\lambda^{-\Delta}\mathcal O(x)
$$

inside scale-covariant correlation functions.

A descendant is obtained by acting with translations:

$$
P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle
\quad\leftrightarrow\quad
\partial_{\mu_1}\cdots\partial_{\mu_n}\mathcal O(x).
$$

The twist of a symmetric traceless operator is

$$
\tau=\Delta-\ell.
$$

The twist is especially useful in lightcone bootstrap and large-spin physics.

## Normalization of scalar correlators

For scalar primaries, the default orthonormal two-point convention is

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{\delta_{ij}}{(x^2)^{\Delta_i}},
\qquad
\Delta_i=\Delta_j.
$$

If a non-unit normalization is useful, we write

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\frac{C_{\mathcal O}}{(x^2)^\Delta}.
$$

For three scalar primaries,

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\rangle
=
\frac{C_{123}}{
(x_{12}^2)^{(\Delta_1+\Delta_2-\Delta_3)/2}
(x_{23}^2)^{(\Delta_2+\Delta_3-\Delta_1)/2}
(x_{13}^2)^{(\Delta_1+\Delta_3-\Delta_2)/2}
}.
$$

With the two-point normalization above, the numbers $C_{123}$ are physical OPE coefficients up to choices of basis in degenerate operator spaces.

## OPE and conformal blocks

The operator product expansion is written schematically as

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ijk}\,\mathcal D_{ij}{}^k(x,\partial)\mathcal O_k(0),
$$

where $\mathcal D_{ij}{}^k$ is fixed by conformal symmetry once the primary $\mathcal O_k$ and the three-point tensor structure are specified.

For identical scalar four-point functions, we use

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{1}{(x_{12}^2)^\Delta(x_{34}^2)^\Delta}\,\mathcal G(u,v),
$$

with cross-ratios

$$
u=
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=
\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The conformal block expansion in the $12\to34$ channel is written as

$$
\mathcal G(u,v)
=
\sum_{\mathcal O}\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(u,v),
$$

where the sum is over primary operators appearing in the $\phi\times\phi$ OPE.

When using complex variables for four-point kinematics, the convention is

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

In Euclidean signature, $\bar z$ is the complex conjugate of $z$. In Lorentzian signature, $z$ and $\bar z$ are often analytically continued as independent variables.

## Stress tensor and currents

The stress tensor is denoted by

$$
T_{\mu\nu}.
$$

In a flat-space CFT without anomalies,

$$
\partial^\mu T_{\mu\nu}=0,
\qquad
T^\mu{}_{\mu}=0.
$$

In a curved background, the stress tensor is defined by varying the generating functional:

$$
\langle T_{\mu\nu}(x)\rangle
=
-\frac{2}{\sqrt{|g|}}\frac{\delta W[g]}{\delta g^{\mu\nu}(x)}.
$$

The overall sign can depend on Euclidean versus Lorentzian conventions. Whenever this distinction matters, the page will state the convention explicitly.

For a conserved internal symmetry current,

$$
J_\mu^a,
\qquad
\partial^\mu J_\mu^a=0.
$$

The corresponding charge is

$$
Q^a=\int_{\Sigma}d\Sigma^\mu J_\mu^a.
$$

The two-point normalization of the stress tensor is usually described by $C_T$, and the current two-point normalization by $C_J$. Precise tensor structures are written on the relevant pages.

## Conformal generators

The Euclidean conformal group in $d$ dimensions is $SO(d+1,1)$. The Lorentzian conformal group is $SO(d,2)$.

The generators are

$$
P_\mu,\qquad M_{\mu\nu},\qquad D,\qquad K_\mu.
$$

Their interpretation is:

| Generator | Meaning |
|---|---|
| $P_\mu$ | translations |
| $M_{\mu\nu}$ | rotations or Lorentz transformations |
| $D$ | dilatations |
| $K_\mu$ | special conformal transformations |

The most important commutators are

$$
[D,P_\mu]=P_\mu,
\qquad
[D,K_\mu]=-K_\mu,
$$

$$
[K_\mu,P_\nu]=2\delta_{\mu\nu}D-2M_{\mu\nu}
$$

in a common Euclidean convention without explicit factors of $i$. Some references use Hermitian generators and insert factors of $i$. This course usually prioritizes clean representation-theoretic formulas; when comparing to a reference, check whether its generators are Hermitian or anti-Hermitian.

A primary state obeys

$$
K_\mu|\mathcal O\rangle=0,
\qquad
D|\mathcal O\rangle=\Delta |\mathcal O\rangle.
$$

Descendants are generated by $P_\mu$.

## Radial quantization

The radial coordinate is

$$
r=|x|,
\qquad
\tau=\log r.
$$

The flat Euclidean metric becomes

$$
ds^2=dr^2+r^2d\Omega_{d-1}^2
=e^{2\tau}(d\tau^2+d\Omega_{d-1}^2).
$$

After the Weyl transformation, the CFT lives on the cylinder

$$
S^{d-1}\times\mathbb R_\tau.
$$

The cylinder Hamiltonian is the dilatation operator:

$$
H_{\mathrm{cyl}}=D.
$$

The state-operator map is denoted by

$$
\mathcal O(0)|0\rangle
\longleftrightarrow
|\mathcal O\rangle.
$$

For a primary state,

$$
H_{\mathrm{cyl}}|\mathcal O\rangle=\Delta|\mathcal O\rangle.
$$

## Embedding-space conventions

Embedding space uses coordinates $P^A$ in $\mathbb R^{d+1,1}$ for Euclidean CFT or $\mathbb R^{d,2}$ for Lorentzian CFT. Boundary points are represented by null rays:

$$
P^2=0,
\qquad
P^A\sim\lambda P^A,
\qquad
\lambda>0.
$$

A scalar primary is lifted to a homogeneous function

$$
\mathcal O(\lambda P)=\lambda^{-\Delta}\mathcal O(P).
$$

The standard invariant is

$$
P_{ij}=-2P_i\cdot P_j.
$$

In a Poincare section, this reduces to

$$
P_{ij}=x_{ij}^2.
$$

Bulk AdS points are denoted by $X^A$ and satisfy

$$
X^2=-L^2.
$$

Often we set $L=1$ temporarily. When comparing with dimensions or bulk masses, $L$ is restored.

## Two-dimensional CFT notation

In two Euclidean dimensions,

$$
z=x^1+ix^2,
\qquad
\bar z=x^1-ix^2.
$$

Derivatives are

$$
\partial=\partial_z=\frac12(\partial_1-i\partial_2),
\qquad
\bar\partial=\partial_{\bar z}=\frac12(\partial_1+i\partial_2).
$$

A primary field has left and right conformal weights

$$
(h,\bar h).
$$

The scaling dimension and spin are

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

The holomorphic stress tensor is $T(z)$ and the antiholomorphic stress tensor is $\bar T(\bar z)$. Their mode expansions are

$$
T(z)=\sum_{n\in\mathbb Z}\frac{L_n}{z^{n+2}},
\qquad
\bar T(\bar z)=\sum_{n\in\mathbb Z}\frac{\bar L_n}{\bar z^{n+2}}.
$$

The Virasoro algebra is

$$
[L_m,L_n]
=(m-n)L_{m+n}+\frac{c}{12}m(m^2-1)\delta_{m+n,0},
$$

with an identical barred copy. The central charge is $c$.

A highest-weight state obeys

$$
L_0|h\rangle=h|h\rangle,
\qquad
L_n|h\rangle=0\quad n>0.
$$

The torus modular parameter is

$$
\tau=\tau_1+i\tau_2,
\qquad
q=e^{2\pi i\tau}.
$$

A torus partition function is usually written as

$$
Z(\tau,\bar\tau)=\operatorname{Tr}_{\mathcal H}
q^{L_0-c/24}\bar q^{\bar L_0-c/24}.
$$

## Supersymmetry and $\mathcal N=4$ SYM notation

For four-dimensional $\mathcal N=4$ SYM, the gauge group is usually $SU(N)$ unless stated otherwise. The 't Hooft coupling is

$$
\lambda=g_{\mathrm{YM}}^2N.
$$

The complexified coupling is

$$
\tau_{\mathrm{YM}}=\frac{\theta}{2\pi}+\frac{4\pi i}{g_{\mathrm{YM}}^2}.
$$

The superconformal algebra is

$$
\mathfrak{psu}(2,2|4).
$$

The bosonic subalgebra contains

$$
\mathfrak{so}(4,2)\oplus\mathfrak{su}(4)_R.
$$

The $R$-symmetry groups are related by

$$
SU(4)_R\simeq SO(6)_R.
$$

The six real scalars are denoted by

$$
\Phi^I,
\qquad
I=1,\ldots,6.
$$

Half-BPS single-trace chiral primaries are schematically

$$
\mathcal O_p^{I_1\cdots I_p}
=\operatorname{Tr}(\Phi^{(I_1}\cdots\Phi^{I_p)})-\text{traces},
$$

with protected dimension

$$
\Delta=p.
$$

As $SU(4)_R$ representations, these operators lie in

$$
[0,p,0].
$$

The $p=2$ operator is the primary of the stress-tensor multiplet and transforms in the $20'$ representation:

$$
[0,2,0].
$$

## Large-$N$ notation

Single-trace operators are denoted schematically by

$$
\mathcal O_{\mathrm{st}}=\frac{1}{N}\operatorname{Tr}(\Phi\cdots\Phi),
$$

with normalization chosen so that

$$
\langle \mathcal O_{\mathrm{st}}(x)\mathcal O_{\mathrm{st}}(0)\rangle=O(1).
$$

For adjoint matrix large-$N$ CFTs with this normalization, connected correlators of single-trace operators scale as

$$
\langle \mathcal O_1\cdots\mathcal O_n\rangle_c
=O(N^{2-n}).
$$

Thus

$$
C_T\sim N^2,
\qquad
\frac{G_N}{L^{d-1}}\sim\frac{1}{C_T}.
$$

A double-trace operator is written schematically as

$$
[\mathcal O_1\mathcal O_2]_{n,\ell}.
$$

At leading large $N$, its dimension is

$$
\Delta_{n,\ell}^{(0)}
=\Delta_1+\Delta_2+2n+\ell.
$$

At finite but large $N$,

$$
\Delta_{n,\ell}
=\Delta_1+\Delta_2+2n+\ell
+\gamma_{n,\ell},
\qquad
\gamma_{n,\ell}=O(N^{-2})
$$

for tree-level bulk interactions in a standard holographic large-$N$ theory.

## AdS/CFT dictionary symbols

The AdS radius is $L$. The bulk Newton constant is $G_N$. The boundary dimension is $d$, so the bulk dimension is $d+1$.

A scalar bulk field is denoted by $\phi$. The dual CFT operator is $\mathcal O$. The source is $J$.

The basic source relation is

$$
Z_{\mathrm{CFT}}[J]
=
Z_{\mathrm{bulk}}[\phi\to J].
$$

At large $N$ and strong coupling, the right-hand side is approximated by the classical on-shell action:

$$
Z_{\mathrm{bulk}}[\phi\to J]
\approx
\exp\bigl(-S_{\mathrm{bulk}}^{\mathrm{on-shell}}[J]\bigr)
$$

in Euclidean signature.

For a scalar field in $\mathrm{AdS}_{d+1}$,

$$
m^2L^2=\Delta(\Delta-d).
$$

The two roots are

$$
\Delta_\pm=\frac d2\pm\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

The standard quantization uses $\Delta=\Delta_+$ unless alternative quantization is explicitly discussed.

The most common field/operator pairs are:

| Bulk field | Boundary operator |
|---|---|
| scalar $\phi$ | scalar primary $\mathcal O$ |
| metric $g_{MN}$ | stress tensor $T_{\mu\nu}$ |
| gauge field $A_M^a$ | conserved current $J_\mu^a$ |
| graviton | energy and momentum transport |
| bulk mass | CFT scaling dimension |
| bulk spin | CFT spin |
| radial position | RG scale |

The radial direction is not literally the energy scale, but in holographic renormalization the radial cutoff plays the role of a UV cutoff in the boundary theory.

## Common equation labels in prose

Because these notes are written as webpages rather than as a single book, equations are usually referred to by their content rather than by global equation numbers. For example:

- “the scalar two-point function” means $\langle \mathcal O(x)\mathcal O(0)\rangle=C_{\mathcal O}/(x^2)^\Delta$;
- “the mass-dimension relation” means $m^2L^2=\Delta(\Delta-d)$;
- “the crossing equation” means equality of different OPE expansions of the same four-point function;
- “the state-operator map” means $\mathcal O(0)|0\rangle\leftrightarrow |\mathcal O\rangle$.

This avoids making each page depend on a global numbering system.

## A few convention traps

### $d$ versus $D$

In these notes, $d$ almost always means the **boundary CFT dimension**. The bulk dimension is $d+1$. Some references use $D$ for the bulk dimension; when comparing formulas, check whether the formula was written for $d$ or $D$.

### $z$ in two-dimensional CFT versus AdS radial coordinate

In two-dimensional CFT, $z$ is the complex coordinate. In Poincare AdS, many references also use $z$ for the radial coordinate. To avoid confusion, these notes may write the AdS radial coordinate as $z_{\mathrm{AdS}}$, $u$, or simply state the convention on the page.

### $c$ as central charge versus speed of light

In two-dimensional CFT, $c$ denotes the Virasoro central charge. The speed of light is set to one and is not denoted by $c$.

### $N$ versus $\mathcal N$

The symbol $N$ usually means gauge-group rank or a large-$N$ parameter. The symbol $\mathcal N$ denotes the number of supersymmetries in common physics notation, as in $\mathcal N=4$ SYM.

### $\tau$ as twist, torus modulus, or Yang-Mills coupling

The symbol $\tau$ has three common meanings:

$$
\tau=\Delta-\ell
\quad\text{twist},
$$

$$
\tau=\tau_1+i\tau_2
\quad\text{torus modular parameter},
$$

$$
\tau_{\mathrm{YM}}=\frac{\theta}{2\pi}+\frac{4\pi i}{g_{\mathrm{YM}}^2}
\quad\text{complexified Yang-Mills coupling}.
$$

The context should make the meaning clear; when it does not, the notes add a subscript.

## Exercises

### Exercise 1: check the dimension of the scalar two-point function

Let a scalar primary have dimension $\Delta$. Show that

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=\frac{C}{(x^2)^\Delta}
$$

has the correct scaling behavior under $x\mapsto \lambda x$.

<details><summary><strong>Solution</strong></summary>

A scalar primary has scaling dimension $\Delta$, so a two-point function of two such operators must scale as $\lambda^{-2\Delta}$. The proposed expression gives

$$
\frac{C}{((\lambda x)^2)^\Delta}
=
\frac{C}{(\lambda^2x^2)^\Delta}
=
\lambda^{-2\Delta}\frac{C}{(x^2)^\Delta}.
$$

This is exactly the required scaling.

</details>

### Exercise 2: recover $\Delta$ and spin from two-dimensional weights

A two-dimensional primary has weights $(h,\bar h)$. Under a rotation,

$$
z\mapsto e^{i\theta}z,
\qquad
\bar z\mapsto e^{-i\theta}\bar z.
$$

Using the primary transformation law, show that the scaling dimension and spin are

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

<details><summary><strong>Solution</strong></summary>

Under a scale transformation $z\mapsto \lambda z$ and $\bar z\mapsto \lambda\bar z$, a primary transforms with a factor

$$
\lambda^{-h}\lambda^{-\bar h}=\lambda^{-(h+\bar h)}.
$$

Therefore $\Delta=h+\bar h$.

Under a rotation,

$$
\frac{dw}{dz}=e^{i\theta},
\qquad
\frac{d\bar w}{d\bar z}=e^{-i\theta}.
$$

The primary transformation factor is

$$
(e^{i\theta})^{-h}(e^{-i\theta})^{-\bar h}
=e^{-i(h-\bar h)\theta}.
$$

The coefficient of $-i\theta$ is the spin, so $s=h-\bar h$.

</details>

### Exercise 3: large-$N$ connected correlator scaling

Assume single-trace operators are normalized so that their two-point functions are $O(1)$. In a matrix large-$N$ theory, connected $n$-point functions scale as

$$
\langle \mathcal O_1\cdots\mathcal O_n\rangle_c=O(N^{2-n}).
$$

What are the large-$N$ scalings of the connected three- and four-point functions?

<details><summary><strong>Solution</strong></summary>

For $n=3$,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle_c
=O(N^{-1}).
$$

For $n=4$,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle_c
=O(N^{-2}).
$$

This is the CFT form of weak bulk coupling: cubic interactions scale like $1/N$, while tree-level connected four-point interactions scale like $1/N^2$.

</details>

### Exercise 4: mass-dimension relation

A scalar field in $\mathrm{AdS}_{d+1}$ obeys

$$
m^2L^2=\Delta(\Delta-d).
$$

Solve for $\Delta$.

<details><summary><strong>Solution</strong></summary>

This is a quadratic equation:

$$
\Delta^2-d\Delta-m^2L^2=0.
$$

Therefore

$$
\Delta_\pm
=
\frac d2\pm\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

The standard quantization usually chooses $\Delta=\Delta_+$.

</details>

## Minimal checklist

Before using the rest of the appendices, make sure the following conventions feel automatic:

1. $d$ is the CFT dimension; the AdS bulk has dimension $d+1$.
2. Euclidean CFT uses $x^2>0$ for separated points; Lorentzian CFT needs an $i\epsilon$ prescription.
3. A CFT is specified by spectrum plus OPE coefficients.
4. In two dimensions, $\Delta=h+\bar h$ and $s=h-\bar h$.
5. At large $N$, connected single-trace correlators scale as $N^{2-n}$.
6. In AdS/CFT, $m^2L^2=\Delta(\Delta-d)$ is the first bridge between bulk fields and boundary operators.

These six items remove a surprising amount of notational friction.
