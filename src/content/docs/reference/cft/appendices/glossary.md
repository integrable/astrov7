---
title: "Glossary"
description: "A conceptual glossary for Modern CFT for AdS/CFT, emphasizing definitions, common confusions, and holographic meaning."
sidebar:
  order: 6
---

This glossary is meant to be read actively. Most entries are not dictionary fragments; they are compressed conceptual reminders of how the word is used in this course and why it matters for AdS/CFT.

A useful habit is to attach every CFT term to one of three questions:

1. Is this a statement about **symmetry**?
2. Is this a statement about **operator data**?
3. Is this a statement about **holographic interpretation**?

For example, a primary operator is a representation-theoretic object, an OPE coefficient is dynamical CFT data, and a single-trace primary at large $N$ is usually interpreted as a single-particle bulk field.

## Core symbols

| Symbol | Meaning |
|---|---|
| $d$ | Spacetime dimension of the CFT. The dual bulk is often $(d+1)$-dimensional. |
| $x^\mu$ | CFT spacetime coordinate. In Euclidean signature, $\mu=1,\ldots,d$. |
| $z,\bar z$ | Complex coordinates in two-dimensional Euclidean CFT. |
| $\mathcal O_i$ | Local operator. The subscript labels a basis element in the operator algebra. |
| $\Delta$ | Scaling dimension. On the cylinder, it is the energy of the corresponding state. |
| $\ell$ | Spin, usually for symmetric traceless tensors in $d>2$. |
| $h,\bar h$ | Holomorphic and antiholomorphic weights in 2D CFT, with $\Delta=h+\bar h$ and spin $s=h-\bar h$. |
| $C_{ijk}$ | OPE coefficient or three-point coefficient, depending on normalization. |
| $T_{\mu\nu}$ | Stress tensor. It couples to the background metric. |
| $J_\mu$ | Conserved current. It couples to a background gauge field. |
| $Z[J]$ | Generating functional with source $J$ for an operator $\mathcal O$. |
| $N$ | Large-$N$ parameter, often the rank of a gauge group. |
| $\lambda$ | 't Hooft coupling, typically $\lambda=g_{\rm YM}^2N$ in gauge theory. |
| $L$ | AdS radius. |
| $G_N$ | Bulk Newton constant. Large CFT central charge corresponds to small $G_N/L^{d-1}$. |
| $m$ | Bulk mass of a field. For a scalar, $m^2L^2=\Delta(\Delta-d)$. |

## A

### AdS radius $L$

The curvature scale of anti-de Sitter space. In global AdS, $L$ also sets the natural unit of energy. In CFT units, one often sets $L=1$, so that bulk masses and CFT dimensions are compared through dimensionless combinations such as $m^2L^2$.

The scalar dictionary is

$$
m^2L^2=\Delta(\Delta-d).
$$

The two roots,

$$
\Delta_\pm=\frac d2\pm\sqrt{\frac{d^2}{4}+m^2L^2},
$$

are important near the Breitenlohner-Freedman window, where alternative quantization may be possible.

### AdS/CFT correspondence

A duality between a $d$-dimensional conformal field theory and quantum gravity, or string theory, on an asymptotically $\mathrm{AdS}_{d+1}$ spacetime. The most useful first formula is the source dictionary,

$$
Z_{\rm CFT}[J]
=
Z_{\rm bulk}\!\left[\phi_{\partial}=J\right],
$$

where the CFT source $J$ couples to an operator $\mathcal O$, while the bulk field $\phi$ approaches $J$ at the conformal boundary.

Do not read this as merely a way to compute correlators. It says that the CFT Hilbert space, operator algebra, thermal states, symmetries, and entanglement structure contain the full nonperturbative definition of the bulk theory.

### Affine Lie algebra

The chiral current algebra of a two-dimensional CFT with holomorphic currents $J^a(z)$. Its OPE is

$$
J^a(z)J^b(0)
\sim
\frac{k\,\delta^{ab}}{z^2}
+
\frac{i f^{ab}{}_c J^c(0)}{z}
+\cdots .
$$

The integer $k$ is the level. Affine algebras are the symmetry engines behind WZW models, current algebra fusion rules, and many exactly solvable worldsheet theories.

### Anomalous dimension

The difference between the full scaling dimension of an operator and its classical or engineering dimension. If an operator has classical dimension $\Delta_{\rm cl}$, then

$$
\Delta=\Delta_{\rm cl}+\gamma .
$$

In perturbative QFT, $\gamma$ is computed from renormalization. In a CFT, $\Delta$ itself is the physical quantity. In AdS/CFT, anomalous dimensions of multi-trace operators encode bulk interactions. For example, at large $N$,

$$
\Delta_{n,\ell}
=
\Delta_1+\Delta_2+2n+\ell+\gamma_{n,\ell}
$$

for a double-trace tower, and $\gamma_{n,\ell}$ measures deviations from generalized free behavior.

### Anomaly

A symmetry of the classical theory that fails to hold after quantization or regularization. The two most important anomalies in this course are:

| Anomaly | Form | Meaning |
|---|---|---|
| Weyl anomaly | $\langle T^\mu{}_\mu\rangle\neq 0$ on curved space | Local scale invariance is anomalous in even $d$. |
| 't Hooft anomaly | Non-invariance under background gauge transformations | The global symmetry cannot be gauged without extra inflow or degrees of freedom. |

An anomaly is not a mistake. It is a robust datum of the quantum theory. In holography, anomalies are often reproduced by bulk Chern-Simons terms or by logarithmic divergences in the renormalized on-shell action.

### Asymptotic density of states

The growth of the number of states at high energy or large scaling dimension. In a 2D unitary compact CFT with modular invariance and central charge $c$, the Cardy regime gives

$$
\rho(\Delta)\sim
\exp\!\left(
2\pi\sqrt{\frac{c_{\rm eff}\Delta}{6}}
\right),
$$

up to refinements involving left- and right-moving dimensions. In AdS$_3$/CFT$_2$, this growth reproduces BTZ black-hole entropy.

## B

### Background field

A nondynamical field coupled to a CFT operator. Important examples are

$$
\delta S
=
\int d^dx \sqrt g\,
\left(
J\,\mathcal O
+
A_\mu J^\mu
+
\frac12 h_{\mu\nu}T^{\mu\nu}
\right).
$$

Here $J$, $A_\mu$, and $h_{\mu\nu}$ are sources. In AdS/CFT, these are the boundary values of bulk fields.

### Beta function

The RG flow of a coupling $g^i$ with respect to a renormalization scale $\mu$:

$$
\beta^i(g)=\mu\frac{d g^i}{d\mu}.
$$

A fixed point satisfies $\beta^i=0$. In a CFT, the trace Ward identity schematically reads

$$
T^\mu{}_\mu
=
\sum_i \beta^i \mathcal O_i
+
\text{anomalies}
+
\text{improvements}.
$$

Thus vanishing beta functions are a necessary part of conformal invariance, but one must also handle virial currents, improvements, and anomalies.

### BPS operator

An operator in a supersymmetric theory whose dimension is protected by shortening of a superconformal multiplet. BPS dimensions are fixed by symmetry and $R$-charges rather than by generic dynamics.

For example, in $\mathcal N=4$ SYM, half-BPS single-trace scalar primaries have the schematic form

$$
\mathcal O_p(Y)
=
Y_{I_1}\cdots Y_{I_p}
\operatorname{Tr}
\left(
\Phi^{I_1}\cdots \Phi^{I_p}
\right),
\qquad
Y\cdot Y=0,
$$

and transform in the $SU(4)_R$ representation $[0,p,0]$ with protected dimension

$$
\Delta=p.
$$

In AdS$_5\times S^5$, these map to Kaluza-Klein modes on $S^5$.

### Bootstrap

A method of solving or constraining CFTs from consistency of the operator algebra. The modern bootstrap begins with four-point crossing symmetry,

$$
\sum_{\mathcal O}
C_{12\mathcal O}C_{34\mathcal O}
G_{\Delta,\ell}^{(s)}(u,v)
=
\sum_{\mathcal O}
C_{14\mathcal O}C_{23\mathcal O}
G_{\Delta,\ell}^{(t)}(u,v),
$$

combined with unitarity, positivity, global symmetry, and sometimes large-$N$ or supersymmetric input.

The bootstrap viewpoint is essential for holography because it treats CFT data as the fundamental definition of the theory. Bulk locality becomes a property of special large-$N$ solutions to crossing.

### Boundary condition

In ordinary field theory, a prescription for how fields behave at a boundary. In AdS/CFT, boundary conditions for bulk fields are sources or states of the dual CFT. For a scalar near the AdS boundary,

$$
\phi(z,x)
\sim
z^{d-\Delta}J(x)
+
z^\Delta A(x),
$$

where $J$ is the source and $A$ is related to $\langle\mathcal O\rangle$, after holographic renormalization.

### Bulk locality

The statement that, at low energies compared with the AdS and string scales, the bulk theory can be described by a local effective field theory. From the CFT side, locality is not automatic. It is encoded indirectly in large-$N$ factorization, a sparse low-dimension single-trace spectrum, controlled OPE coefficients, and special analytic behavior of large-spin anomalous dimensions.

## C

### Cardy formula

A high-energy asymptotic formula for the density of states in a two-dimensional CFT. In its simplest diagonal form,

$$
S(\Delta)
\sim
2\pi\sqrt{\frac{c_{\rm eff}\Delta}{6}}.
$$

For left and right movers,

$$
S
\sim
2\pi
\sqrt{\frac{c_L}{6}\left(h-\frac{c_L}{24}\right)}
+
2\pi
\sqrt{\frac{c_R}{6}\left(\bar h-\frac{c_R}{24}\right)}.
$$

The key mechanism is modular invariance: high-temperature physics is related to low-temperature vacuum dominance.

### Casimir operator

An element of the universal enveloping algebra that commutes with all generators of a Lie algebra. For the conformal algebra, the quadratic Casimir acts on a primary representation as

$$
C_2(\Delta,\ell)
=
\Delta(\Delta-d)+\ell(\ell+d-2)
$$

for symmetric traceless spin $\ell$. Conformal blocks are eigenfunctions of the Casimir differential operator.

### Central charge

A number that measures degrees of freedom or normalizes a protected two-point function. In 2D CFT, the Virasoro algebra has central charge $c$:

$$
[L_m,L_n]
=
(m-n)L_{m+n}
+
\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

In higher dimensions, one often uses quantities such as $C_T$, the coefficient of the stress-tensor two-point function. In holographic CFTs, central charges are large and scale roughly as

$$
C_T\sim \frac{L^{d-1}}{G_N}.
$$

### Chiral algebra

A holomorphic operator algebra in two-dimensional CFT. The Virasoro algebra generated by $T(z)$ is the minimal chiral algebra. Extra holomorphic currents enlarge it to affine algebras, $W$-algebras, or superconformal algebras.

### Chiral primary

A protected operator in a supersymmetric CFT, annihilated by some supercharges. The phrase means slightly different things in different dimensions and supersymmetries. In four-dimensional $\mathcal N=1$ theories, a chiral primary satisfies

$$
\bar Q_{\dot\alpha}\mathcal O=0,
\qquad
\Delta=\frac32 R.
$$

In $\mathcal N=4$ SYM, the term is often used for half-BPS scalar primaries in $[0,p,0]$.

### Conformal algebra

The Lie algebra of conformal transformations in $d$ dimensions, isomorphic to $\mathfrak{so}(d,2)$ in Lorentzian signature or $\mathfrak{so}(d+1,1)$ in Euclidean signature. Its generators are

$$
P_\mu,\quad M_{\mu\nu},\quad D,\quad K_\mu.
$$

The most important commutators for representation theory are

$$
[D,P_\mu]=P_\mu,
\qquad
[D,K_\mu]=-K_\mu,
\qquad
[K_\mu,P_\nu]=2\delta_{\mu\nu}D+2M_{\mu\nu},
$$

up to convention-dependent factors of $i$. In radial quantization, $P_\mu$ raises the dimension and $K_\mu$ lowers it.

### Conformal block

The contribution of one conformal family to a four-point function. For scalar external operators,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\sum_{\mathcal O}
C_{12\mathcal O}C_{34\mathcal O}
G_{\Delta,\ell}(u,v).
$$

A block is kinematic: it is fixed by symmetry once the exchanged representation is specified. The dynamical data are the spectrum and OPE coefficients multiplying the blocks.

### Conformal family

A primary operator together with all of its descendants. In $d>2$, descendants are generated by $P_\mu$:

$$
\mathcal O,\quad
P_\mu\mathcal O,\quad
P_{\mu_1}P_{\mu_2}\mathcal O,\quad
\ldots .
$$

In 2D CFT, a Virasoro family is generated by $L_{-n}$ and $\bar L_{-n}$ for $n>0$.

### Conformal manifold

A continuous family of CFTs connected by exactly marginal deformations. If $\mathcal O_i$ are marginal operators with $\Delta_i=d$, then

$$
S
\to
S+\sum_i \lambda^i\int d^dx\,\mathcal O_i(x)
$$

defines a conformal manifold only if the beta functions vanish to all orders after quotienting by redundancies. In $\mathcal N=4$ SYM, the complexified gauge coupling

$$
\tau=\frac{\theta}{2\pi}+\frac{4\pi i}{g_{\rm YM}^2}
$$

is exactly marginal.

### Conformal primary

A local operator annihilated by all special conformal generators at the origin:

$$
[K_\mu,\mathcal O(0)]=0.
$$

A primary is the lowest-weight state of a conformal multiplet in radial quantization. Its quantum numbers are $\Delta$, spin, and global symmetry representation.

### Conformal transformation

A coordinate transformation preserving the metric up to a local scale:

$$
g_{\mu\nu}(x)
\to
\Omega(x)^2 g_{\mu\nu}(x).
$$

For $d>2$, the global conformal group is finite-dimensional. In $d=2$, local holomorphic transformations $z\to f(z)$ generate an infinite-dimensional symmetry algebra.

### Conserved current

A local vector operator obeying

$$
\partial^\mu J_\mu=0.
$$

In a unitary CFT, a conserved spin-one current has protected dimension

$$
\Delta_J=d-1.
$$

It couples to a background gauge field $A_\mu$, and in AdS/CFT it is dual to a bulk gauge field.

### Contact term

A contribution to a correlator supported only when two or more insertion points coincide, often involving delta functions or derivatives of delta functions. Ward identities frequently contain contact terms. They are not optional bookkeeping; they encode how operators transform under symmetries.

### Correlation function

A vacuum expectation value of local operators,

$$
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle.
$$

In a CFT, two- and three-point functions are mostly fixed by symmetry, while four-point functions contain dynamical information. In AdS/CFT, boundary correlators are computed by differentiating the renormalized bulk on-shell action with respect to boundary sources.

### Crossing symmetry

The equality of different OPE expansions of the same correlator. For identical scalars $\phi$,

$$
v^\Delta g(u,v)=u^\Delta g(v,u),
$$

where

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{g(u,v)}{x_{12}^{2\Delta}x_{34}^{2\Delta}}.
$$

Crossing is associativity of the OPE. It is the central equation of the conformal bootstrap.

### Cross-ratios

Conformally invariant combinations of four points. In $d>2$,

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

In 2D, one often writes

$$
u=z\bar z,\qquad v=(1-z)(1-\bar z).
$$

Cross-ratios are the variables on which four-point dynamics depends.

## D

### Descendant

An operator obtained by acting with translation generators on a primary:

$$
P_{\mu_1}\cdots P_{\mu_n}\mathcal O.
$$

In position space, descendants are derivatives and traces of derivatives of primaries. Descendants do not introduce independent OPE data; their contributions are fixed by conformal symmetry once the primary data are known.

### Defect CFT

A CFT with an extended object, such as a line, surface, boundary, or interface, preserving a subgroup of the full conformal group. A straight line in $d$ dimensions preserves $SO(1,2)\times SO(d-1)$ in Lorentzian signature. Wilson lines in $\mathcal N=4$ SYM provide important examples.

### Dilatation operator

The generator $D$ of scale transformations. In radial quantization, $D$ is the Hamiltonian on the cylinder:

$$
\mathbb R^d\setminus\{0\}
\simeq
S^{d-1}\times\mathbb R_\tau,
\qquad
r=e^\tau.
$$

The eigenvalues of $D$ are scaling dimensions. In planar $\mathcal N=4$ SYM, the dilatation operator acts as a spin-chain Hamiltonian in certain sectors.

### Double-trace operator

A multi-particle large-$N$ operator built schematically from two single-trace primaries:

$$
[\mathcal O_1\mathcal O_2]_{n,\ell}
\sim
\mathcal O_1
\partial^{2n}
\partial_{\{\mu_1}\cdots\partial_{\mu_\ell\}}
\mathcal O_2
-\text{traces}.
$$

At leading large $N$,

$$
\Delta_{n,\ell}^{(0)}
=
\Delta_1+\Delta_2+2n+\ell.
$$

Its anomalous dimension is a diagnostic of bulk interactions.

### Dynamical data

The part of the CFT not fixed by symmetry alone. In a CFT, the fundamental dynamical data are

$$
\left\{
\Delta_i,\ell_i,\mathcal R_i;
\ C_{ijk}
\right\},
$$

the spectrum and OPE coefficients, subject to consistency conditions such as crossing, unitarity, locality, and symmetry.

## E

### Embedding space

A formalism that realizes the conformal group linearly by embedding physical space into the projective null cone

$$
P^2=0,
\qquad
P\sim \lambda P
$$

in $\mathbb R^{d+1,1}$. A scalar primary of dimension $\Delta$ is lifted to a homogeneous function

$$
\mathcal O(\lambda P)=\lambda^{-\Delta}\mathcal O(P).
$$

Embedding space is especially useful for spinning correlators and for comparing CFT structures with AdS geometry.

### Entanglement entropy

For a region $A$, the von Neumann entropy of the reduced density matrix

$$
S_A=-\operatorname{Tr}\rho_A\log\rho_A.
$$

In holography, the leading large-$N$ entropy is computed by the Ryu-Takayanagi or HRT formula,

$$
S_A=\frac{\operatorname{Area}(\gamma_A)}{4G_N}+\cdots .
$$

CFT entanglement therefore probes the emergence of bulk geometry.

### Euclidean CFT

A CFT formulated on Euclidean space or a Euclidean manifold. Euclidean correlators are usually the cleanest objects for conformal symmetry, OPE convergence, and bootstrap equations. Lorentzian physics is obtained by analytic continuation with an $i\epsilon$ prescription.

### Exactly marginal operator

An operator with $\Delta=d$ whose integrated deformation preserves conformal invariance to all orders. Not every marginal operator is exactly marginal. The obstruction is the beta function, often constrained by symmetry but not always forced to vanish.

## F

### Flavor central charge

The normalization of a conserved current two-point function. For a global symmetry current,

$$
\langle J_\mu^a(x)J_\nu^b(0)\rangle
=
\frac{C_J\delta^{ab}}{x^{2(d-1)}}
I_{\mu\nu}(x),
$$

up to convention. In holography, $C_J$ is related to the inverse bulk gauge coupling.

### Four-point function

The first correlator containing nontrivial dynamical functions of cross-ratios. For identical scalars,

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{g(u,v)}{x_{12}^{2\Delta}x_{34}^{2\Delta}}.
$$

Its OPE decomposition exposes the spectrum and OPE coefficients. Its crossing symmetry gives bootstrap constraints.

### Free field

A field theory with Gaussian action and Wick factorization. Free fields are CFTs only in special dimensions or with appropriate improvements. Examples include:

| Theory | CFT dimension |
|---|---|
| Free scalar | Any $d$, with improved stress tensor |
| Free fermion | Any $d$ |
| Maxwell theory | Conformal in $d=4$ |

Free fields are useful laboratories, but generalized free fields are a different large-$N$ concept.

## G

### Generalized free field

An operator whose correlators factorize as if Wick's theorem holds, while no local equation of motion or stress tensor need be built from that operator. For a scalar $\mathcal O$,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\langle \mathcal O_1\mathcal O_2\rangle
\langle \mathcal O_3\mathcal O_4\rangle
+
\langle \mathcal O_1\mathcal O_3\rangle
\langle \mathcal O_2\mathcal O_4\rangle
+
\langle \mathcal O_1\mathcal O_4\rangle
\langle \mathcal O_2\mathcal O_3\rangle .
$$

Generalized free fields are the leading large-$N$ limit of single-particle bulk fields in AdS.

### Global symmetry

An internal symmetry acting on operators but not on spacetime coordinates. A continuous global symmetry has conserved currents. In AdS/CFT, a CFT global symmetry corresponds to a bulk gauge symmetry. This is one of the sharpest examples of the boundary/bulk reversal: global on the boundary, gauge in the bulk.

### Graviton

The quantum of the bulk metric. In AdS/CFT, the graviton is dual to the CFT stress tensor $T_{\mu\nu}$. The existence of a conserved stress tensor is universal in local CFTs, but a weakly coupled bulk graviton requires large $C_T$ and a sparse spectrum.

## H

### Holographic CFT

A CFT with properties suggesting a weakly coupled semiclassical AdS dual. Typical criteria include:

- large central charge,
- large-$N$ factorization,
- sparse low-dimension single-trace spectrum,
- a stress tensor as the only low-spin operator universally tied to gravity,
- OPE data consistent with local bulk effective field theory.

Not every CFT is holographic in this strong sense.

### Holomorphic

Depending only on $z$ and not on $\bar z$. In 2D CFT, conservation and tracelessness imply

$$
\bar\partial T(z)=0,
\qquad
\partial \bar T(\bar z)=0
$$

away from insertions. Holomorphic factorization is the source of the power of two-dimensional CFT.

### HRT surface

The covariant generalization of the Ryu-Takayanagi minimal surface. It computes leading holographic entanglement entropy for time-dependent regions. HRT surfaces are extremal rather than minimal on a time slice.

## I

### Improvement term

A modification of the stress tensor by total derivatives that preserves conserved charges but can change the trace. For a scalar theory, one may add a term of the schematic form

$$
T_{\mu\nu}
\to
T_{\mu\nu}
+
\xi
\left(
\partial_\mu\partial_\nu-\delta_{\mu\nu}\partial^2
\right)
\phi^2.
$$

Improvement is crucial for making the free scalar stress tensor traceless at the conformal fixed point.

### Infrared

Long-distance or low-energy physics. In RG language, flowing to the infrared means coarse-graining. A relevant deformation of a UV CFT can produce a new IR fixed point, a mass gap, spontaneous symmetry breaking, or more exotic behavior.

### Inversion tensor

The tensor

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}
$$

appearing in spinning two-point functions. It implements how vector indices transform under inversion.

## K

### Kač table

A table of allowed primary fields in a Virasoro minimal model. For the unitary series,

$$
c=1-\frac{6}{m(m+1)},
\qquad
m=3,4,\ldots,
$$

the weights are

$$
h_{r,s}
=
\frac{\left((m+1)r-ms\right)^2-1}{4m(m+1)}.
$$

The Ising model is $m=3$, with primaries $\mathbf 1$, $\sigma$, and $\epsilon$.

### KMS condition

The real-time thermal periodicity condition. For bosonic operators in thermal equilibrium,

$$
G^>(t)=G^<(t-i\beta),
$$

where $\beta=1/T$. It is the Lorentzian counterpart of periodicity around the Euclidean thermal circle.

### KZ equation

The Knizhnik-Zamolodchikov equation satisfied by WZW correlators. It follows from affine current algebra and the Sugawara construction. For primaries $\Phi_i$ in representations of $\mathfrak g$,

$$
(k+h^\vee)\partial_{z_i}
\langle \Phi_1\cdots\Phi_n\rangle
=
\sum_{j\neq i}
\frac{T_i^aT_j^a}{z_i-z_j}
\langle \Phi_1\cdots\Phi_n\rangle .
$$

## L

### Large-$N$ expansion

An expansion in powers of $1/N$, often organized by topology in matrix gauge theories. Connected correlators of normalized single-trace operators scale as

$$
\langle \mathcal O_1\cdots\mathcal O_k\rangle_{\rm conn}
\sim
N^{2-k}
$$

in the planar large-$N$ limit. In holography, $1/N$ is the bulk loop expansion.

### Lightcone bootstrap

The analysis of crossing symmetry in limits where pairs of operators become null-separated. It predicts large-spin double-twist towers and constrains anomalous dimensions. It is one of the clearest CFT windows into bulk locality and causality.

### Liouville CFT

A noncompact two-dimensional CFT with action

$$
S_{\rm L}
=
\frac{1}{4\pi}
\int d^2z\sqrt g
\left(
g^{ab}\partial_a\phi\partial_b\phi
+
Q R\phi
+
4\pi\mu e^{2b\phi}
\right),
$$

and central charge

$$
c=1+6Q^2,
\qquad
Q=b+b^{-1}.
$$

Liouville theory has a continuous spectrum and reflection symmetry. It is a basic example of a solvable noncompact CFT.

### Local operator

An operator inserted at a point. In CFT, local operators are the analogs of states through radial quantization. A local operator is not necessarily an elementary field in a Lagrangian; it is any pointlike observable in the operator algebra.

### Lorentzian CFT

A CFT in real time. Lorentzian correlators require operator ordering and $i\epsilon$ prescriptions. Lorentzian physics contains causal structure, commutators, retarded functions, chaos, lightcone limits, and energy conditions. These are essential for black holes and bulk causality.

## M

### Marginal operator

An operator with $\Delta=d$. A marginal deformation is classically scale-invariant, but it may become marginally relevant, marginally irrelevant, or exactly marginal after quantum corrections.

### Mellin amplitude

A Mellin-space representation of CFT correlators, especially useful for holographic CFTs. Mellin variables behave somewhat like Mandelstam invariants. Contact Witten diagrams become polynomial Mellin amplitudes, while exchange diagrams have poles.

### Minimal model

A rational 2D CFT with finitely many Virasoro primaries. The unitary minimal models have

$$
c=1-\frac{6}{m(m+1)}.
$$

The Ising CFT is the first unitary minimal model, with $c=1/2$. Minimal models show how much of a CFT can be solved from representation theory, null states, fusion, and modular invariance.

### Modular Hamiltonian

Defined by

$$
K_A=-\log\rho_A
$$

for a reduced density matrix $\rho_A$. Usually $K_A$ is nonlocal, but for a half-space or ball in a CFT vacuum it is local and generated by a conformal Killing vector. The entanglement first law is

$$
\delta S_A=\delta\langle K_A\rangle.
$$

This equation is one bridge between CFT entanglement and bulk gravitational dynamics.

### Modular invariance

Invariance of the torus partition function under

$$
\tau\to \frac{a\tau+b}{c\tau+d},
\qquad
\begin{pmatrix}a&b\\ c&d\end{pmatrix}\in SL(2,\mathbb Z).
$$

The two generators are

$$
S:\tau\to -\frac1\tau,
\qquad
T:\tau\to\tau+1.
$$

Modular invariance constrains the spectrum of 2D CFTs and underlies the Cardy formula.

### Multi-trace operator

An operator built as a product of several single-trace operators, projected to a conformal primary. In the bulk, multi-trace operators correspond to multi-particle states. Their dimensions and OPE coefficients reveal the perturbative bulk interaction structure.

## N

### Noncompact CFT

A CFT whose target, spectrum, or effective field range is noncompact, often producing continuous spectra and delta-function normalizations. Liouville theory is a central example. Noncompact CFTs are common in worldsheet descriptions of strings in curved backgrounds.

### Normal ordering

A prescription for removing singular self-contractions when multiplying operators at the same point. In CFT language, normal ordering is a way to define composite operators carefully. It is scheme-dependent unless protected by symmetry or a specific regularization.

### Null state

A descendant state with zero norm. In a unitary theory, null states are quotiented out. In 2D minimal models, null states imply differential equations for correlators, known as BPZ equations.

## O

### OPE

The operator product expansion,

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k
C_{ijk}
\,x^{\Delta_k-\Delta_i-\Delta_j}
\left[
\mathcal O_k(0)+\text{descendants}
\right].
$$

In a CFT, the OPE is convergent inside correlation functions in appropriate Euclidean configurations. It is the multiplication table of local operators.

### OPE coefficient

A number $C_{ijk}$ specifying how strongly $\mathcal O_k$ appears in the product $\mathcal O_i\times \mathcal O_j$. Once two-point functions are normalized, OPE coefficients are equivalent to three-point coefficients.

### Operator-state correspondence

The map between local operators on $\mathbb R^d$ and states on $S^{d-1}$:

$$
\mathcal O(0)|0\rangle
\longleftrightarrow
|\mathcal O\rangle.
$$

The scaling dimension becomes the cylinder energy:

$$
D|\mathcal O\rangle=\Delta|\mathcal O\rangle.
$$

In AdS/CFT, this is the boundary version of matching CFT states to global AdS states.

## P

### Planar limit

The large-$N$ limit of a gauge theory in which

$$
N\to\infty,
\qquad
\lambda=g_{\rm YM}^2N
\quad
\text{fixed}.
$$

Feynman diagrams organize by genus. Planar diagrams dominate. In AdS/CFT, the planar limit suppresses string splitting and joining, corresponding to classical string theory before bulk loops.

### Primary operator

See conformal primary. In 2D, a primary with weights $(h,\bar h)$ transforms under local conformal maps as

$$
\mathcal O'(w,\bar w)
=
\left(\frac{dw}{dz}\right)^{-h}
\left(\frac{d\bar w}{d\bar z}\right)^{-\bar h}
\mathcal O(z,\bar z).
$$

A quasi-primary transforms this way only under the global conformal group.

### Projective null cone

The embedding-space realization of physical CFT points:

$$
P^2=0,
\qquad
P\sim\lambda P.
$$

The projective equivalence removes one scale and the null condition removes another, leaving $d$ physical coordinates.

### Protected quantity

A quantity fixed by symmetry, topology, anomaly matching, supersymmetry, or nonrenormalization. Protected does not mean trivial. Protected CFT data are often the safest anchors for testing dualities.

## Q

### Quasi-primary

In 2D CFT, an operator transforming covariantly under the global conformal group $SL(2,\mathbb C)$, but not necessarily under all local conformal transformations. The stress tensor $T(z)$ is quasi-primary but not primary when $c\neq 0$, because its transformation includes the Schwarzian derivative.

### Quantum numbers

Labels identifying a representation: dimension, spin, global symmetry representation, $R$-charges, parity, and other discrete data. A CFT spectrum is a list of operators together with their quantum numbers.

## R

### Radial quantization

Quantization with radius as Euclidean time. Write

$$
x^\mu=r n^\mu,
\qquad
r=e^\tau,
\qquad
n^\mu\in S^{d-1}.
$$

Then flat space becomes conformal to the cylinder:

$$
ds^2=dr^2+r^2d\Omega_{d-1}^2
=
e^{2\tau}
\left(
d\tau^2+d\Omega_{d-1}^2
\right).
$$

Radial quantization makes the operator-state correspondence manifest.

### Rational CFT

A 2D CFT with finitely many irreducible representations of its chiral algebra. Minimal models and many WZW models are rational. Rationality leads to finite fusion rules and modular tensor category structures.

### Reflection positivity

The Euclidean condition corresponding to unitarity after analytic continuation. In radial quantization, it guarantees positive norms of states. It leads to unitarity bounds on scaling dimensions.

### Relevant operator

An operator with $\Delta<d$. Adding

$$
g\int d^dx\,\mathcal O
$$

introduces a coupling with positive mass dimension and drives the theory away from the UV fixed point. In AdS/CFT, relevant deformations correspond to changing boundary conditions for fields dual to low-dimension operators.

### Replica trick

A method for computing entanglement entropy from Rényi entropies:

$$
S_A
=
-\operatorname{Tr}\rho_A\log\rho_A
=
\lim_{n\to 1}
\frac{1}{1-n}
\log\operatorname{Tr}\rho_A^n.
$$

In 2D CFT, this is implemented using twist operators. In holography, replica methods lead to cosmic branes and the RT/HRT formula.

### Ryu-Takayanagi formula

For a static holographic state,

$$
S_A
=
\frac{\operatorname{Area}(\gamma_A)}{4G_N},
$$

where $\gamma_A$ is the minimal bulk surface homologous to $A$. Quantum corrections add bulk entanglement across $\gamma_A$.

## S

### Schwarzian derivative

For a holomorphic map $w=f(z)$,

$$
\{f,z\}
=
\frac{f'''(z)}{f'(z)}
-\frac32
\left(
\frac{f''(z)}{f'(z)}
\right)^2.
$$

The 2D stress tensor transforms as

$$
T(z)
=
\left(\frac{dw}{dz}\right)^2
T(w)
+
\frac{c}{12}\{w,z\},
$$

up to convention. The Schwarzian term is the central charge in geometric clothing.

### Short multiplet

A representation smaller than a generic long multiplet because some descendants vanish or become null. Conserved currents, stress tensors, and BPS operators live in short multiplets. Shortening usually protects dimensions.

### Single-trace operator

In a large-$N$ gauge theory, an operator built from one trace over gauge indices, e.g.

$$
\mathcal O(x)=\frac{1}{\sqrt N}\operatorname{Tr}\Phi^2(x)
$$

up to convention. In holographic CFTs, single-trace primaries are interpreted as single-particle bulk fields.

### Source

A nondynamical function coupled linearly to an operator:

$$
S\to S+\int d^dx\,J(x)\mathcal O(x).
$$

Functional derivatives with respect to $J$ generate correlators. In AdS/CFT, $J$ is a boundary condition for the dual bulk field.

### Sparse spectrum

A holographic condition saying that below some high scale there are relatively few single-trace operators, especially higher-spin single-trace operators. Sparse spectra help a CFT admit an Einstein-like bulk dual rather than a stringy or higher-spin bulk at the AdS scale.

### Spinning correlator

A correlation function involving operators with Lorentz indices. Its form is constrained by conformal symmetry, conservation, parity, and permutation symmetries. Embedding-space polarizations turn tensor structures into polynomials.

### State-operator correspondence

See operator-state correspondence.

### Stress tensor

The conserved spin-two operator associated with translations:

$$
\partial^\mu T_{\mu\nu}=0.
$$

In a CFT, after improvement and away from anomalies,

$$
T^\mu{}_\mu=0.
$$

Its dimension is protected:

$$
\Delta_T=d.
$$

It couples to the metric and is dual to the bulk graviton.

### Superconformal algebra

An extension of the conformal algebra by supercharges $Q$ and special supercharges $S$, plus $R$-symmetry generators. The canonical AdS$_5$/CFT$_4$ example is

$$
\mathfrak{psu}(2,2|4),
$$

the symmetry algebra of $\mathcal N=4$ SYM and type IIB string theory on $\mathrm{AdS}_5\times S^5$.

## T

### Thermal CFT

A CFT on $S^{d-1}\times S^1_\beta$ or $\mathbb R^{d-1}\times S^1_\beta$. The thermal density matrix is

$$
\rho=\frac{e^{-\beta H}}{Z(\beta)}.
$$

In holography, high-temperature thermal states of large-$N$ CFTs are often dual to AdS black holes or black branes.

### Three-point function

The correlator that fixes OPE coefficients. For scalar primaries,

$$
\langle
\mathcal O_1(x_1)
\mathcal O_2(x_2)
\mathcal O_3(x_3)
\rangle
=
\frac{C_{123}}
{x_{12}^{\Delta_1+\Delta_2-\Delta_3}
 x_{23}^{\Delta_2+\Delta_3-\Delta_1}
 x_{13}^{\Delta_1+\Delta_3-\Delta_2}}.
$$

With normalized two-point functions, $C_{123}$ is dynamical CFT data.

### Trace Ward identity

The Ward identity for Weyl transformations:

$$
\langle T^\mu{}_\mu\rangle
=
\sum_i \beta^i\langle\mathcal O_i\rangle
+
\mathcal A[g,A,\ldots]
+
\text{contact terms}.
$$

At a flat-space fixed point with no anomaly and no explicit sources, the trace vanishes after improvement.

### Twist operator

In 2D CFT, an operator implementing branch cuts in the replica trick. For an interval, Rényi entropies are computed from twist-field correlators. The twist dimension for a CFT of central charge $c$ is

$$
h_n=\bar h_n
=
\frac{c}{24}\left(n-\frac1n\right).
$$

## U

### Unitarity bound

A lower bound on $\Delta$ required by positive norm states. For a scalar primary in $d>2$,

$$
\Delta\ge \frac{d-2}{2}.
$$

For symmetric traceless spin $\ell\ge 1$,

$$
\Delta\ge \ell+d-2.
$$

Saturation gives shortening. For $\ell=1$, saturation means a conserved current; for $\ell=2$, a conserved stress tensor.

### Universality class

A set of microscopic theories or statistical models flowing to the same IR fixed point. They share critical exponents and CFT data, though their lattice or UV descriptions differ.

## V

### Verma module

A highest-weight representation generated by acting with lowering modes on a highest-weight state. In the Virasoro case,

$$
L_{-n_1}\cdots L_{-n_k}|h\rangle,
\qquad
n_i>0.
$$

Verma modules may contain null states; quotienting by null submodules gives irreducible representations.

### Virasoro algebra

The central extension of the Witt algebra:

$$
[L_m,L_n]
=
(m-n)L_{m+n}
+
\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

It is the local conformal symmetry algebra of 2D CFT. The central charge $c$ is one of the most important invariants of a 2D CFT.

### Wess-Zumino-Witten model

A 2D CFT with target a Lie group $G$ and affine symmetry $\widehat{\mathfrak g}_k$. Its stress tensor can be built from currents by the Sugawara construction,

$$
T(z)
=
\frac{1}{2(k+h^\vee)}
:J^aJ^a:(z).
$$

WZW models are central examples of rational CFTs and worldsheet string backgrounds.

### Weyl anomaly

The nonzero trace of the stress tensor on curved space at a conformal fixed point. In 2D,

$$
\langle T^\mu{}_\mu\rangle
=
-\frac{c}{24\pi}R
$$

up to convention. In 4D,

$$
\langle T^\mu{}_\mu\rangle
=
\frac{c}{16\pi^2}W_{\mu\nu\rho\sigma}^2
-
\frac{a}{16\pi^2}E_4
+
\cdots .
$$

The coefficients $a$ and $c$ are central charges of the CFT.

### Wilson loop

A nonlocal gauge-invariant operator supported on a curve $C$:

$$
W(C)=
\operatorname{Tr}
P\exp\left(
i\int_C A_\mu dx^\mu
\right).
$$

In $\mathcal N=4$ SYM, the half-BPS Maldacena-Wilson loop also couples to scalars. In AdS/CFT, Wilson loops are computed by string worldsheets ending on $C$ at the AdS boundary.

### Witten diagram

A bulk AdS Feynman diagram used to compute boundary CFT correlators. Contact Witten diagrams correspond to local bulk vertices. Exchange Witten diagrams correspond to propagation of a bulk field dual to an exchanged CFT primary.

## Common false friends

### Scale invariant versus conformal

Scale invariance means invariance under global dilatations. Conformal invariance includes local angle-preserving transformations. In many unitary relativistic QFTs, scale invariance plus extra assumptions implies conformal invariance, but this is a theorem only in specific settings.

### Marginal versus exactly marginal

Marginal means $\Delta=d$ at a point. Exactly marginal means the deformation stays conformal along a finite-dimensional family. The difference is the beta function.

### Free field versus generalized free field

A free field is a local field obeying a free equation of motion and usually has an associated stress tensor. A generalized free field is an operator with factorized correlators but no local equation of motion. Generalized free fields are typical at leading large $N$.

### Primary versus elementary field

A primary is defined by conformal representation theory. An elementary field is a Lagrangian variable. These notions need not coincide. Many CFTs have no known Lagrangian.

### Global symmetry in CFT versus gauge symmetry in AdS

A CFT global symmetry corresponds to a bulk gauge symmetry. Gauge symmetry is redundancy, not a physical global symmetry. The physical statement is the existence of a conserved boundary current and a massless bulk gauge field.

### Central charge in 2D versus $C_T$ in higher dimensions

In 2D, $c$ appears in the Virasoro algebra and controls the Weyl anomaly. In higher dimensions, there is no Virasoro algebra, but $C_T$ and anomaly coefficients play analogous roles as measures of degrees of freedom and stress-tensor normalization.

## Quick AdS/CFT translation table

| CFT concept | Bulk interpretation |
|---|---|
| Local primary $\mathcal O$ | Bulk field $\phi$ |
| Scaling dimension $\Delta$ | Bulk mass or energy |
| Source $J$ | Boundary value of $\phi$ |
| One-point function $\langle\mathcal O\rangle$ | Normalizable mode |
| Stress tensor $T_{\mu\nu}$ | Metric/graviton |
| Conserved current $J_\mu$ | Gauge field |
| Global symmetry | Bulk gauge symmetry |
| Large $C_T$ | Small $G_N/L^{d-1}$ |
| Large $N$ factorization | Classical bulk limit |
| Single-trace primary | Single-particle bulk state |
| Multi-trace primary | Multi-particle bulk state |
| OPE coefficient | Bulk coupling or overlap |
| Thermal state | Black hole or black brane, when deconfined |
| Entanglement entropy | Area of extremal surface plus bulk entropy |
| Sparse spectrum | Effective bulk locality |
| Conformal block | Exchange of a conformal family; related to a bulk exchange channel |

## Self-check exercises

### Exercise 1

Classify the following objects as kinematical data, dynamical data, or consistency conditions:

1. The form of a scalar two-point function.
2. The value of an OPE coefficient $C_{123}$.
3. Crossing symmetry of a four-point function.
4. The scalar unitarity bound $\Delta\ge (d-2)/2$.
5. The existence of a conserved stress tensor.

<details>
<summary><strong>Solution</strong></summary>

The scalar two-point form is mostly kinematical: conformal symmetry fixes it up to normalization. The OPE coefficient $C_{123}$ is dynamical data. Crossing symmetry is a consistency condition on the data. The scalar unitarity bound is also a consistency condition, following from positivity. The existence of a stress tensor is a structural condition for a local CFT with spacetime translations; its dimension $\Delta=d$ and conservation are kinematical consequences of symmetry and locality, while its normalization $C_T$ is dynamical data.

</details>

### Exercise 2

Explain why a single-trace primary and a bulk single-particle state are not literally the same object, even though they are matched in the holographic dictionary.

<details>
<summary><strong>Solution</strong></summary>

A single-trace primary is a boundary local operator, defined in the CFT operator algebra. A bulk single-particle state is a state in an approximate bulk effective field theory. The identification is made through the state-operator correspondence and the large-$N$ holographic dictionary: acting with a single-trace primary on the vacuum creates a CFT state whose bulk interpretation is a single-particle excitation in global AdS. This interpretation requires large $N$, factorization, and a regime where bulk effective field theory is valid.

</details>

### Exercise 3

A scalar primary has dimension $\Delta$ in a $d$-dimensional CFT. What is the mass of the dual scalar field in AdS units? What ambiguity can arise near the Breitenlohner-Freedman bound?

<details>
<summary><strong>Solution</strong></summary>

The mass-dimension relation is

$$
m^2L^2=\Delta(\Delta-d).
$$

Solving for $\Delta$ gives

$$
\Delta_\pm
=
\frac d2
\pm
\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

Near the Breitenlohner-Freedman window, both falloffs can be normalizable, and one may have a choice between standard and alternative quantization. In CFT language, this corresponds to choosing which dimension is assigned to the dual operator, subject to unitarity.

</details>

### Exercise 4

What is the difference between the following two equations?

$$
\partial^\mu J_\mu=0,
\qquad
\partial^\mu\langle J_\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=
\text{contact terms}.
$$

<details>
<summary><strong>Solution</strong></summary>

The first equation is the operator conservation equation away from singularities. The second is the Ward identity inside correlation functions. It includes contact terms when $x$ collides with charged operator insertions. These contact terms encode how the other operators transform under the symmetry generated by $J_\mu$.

</details>

### Exercise 5

Why is a four-point function the first place where general CFT dynamics appears?

<details>
<summary><strong>Solution</strong></summary>

Conformal symmetry fixes scalar two-point functions up to normalization and scalar three-point functions up to constants. Four-point functions depend on conformal cross-ratios, such as

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The function of $u$ and $v$ is not fixed by symmetry. Its conformal block decomposition contains the spectrum and OPE coefficients, and its crossing symmetry imposes nontrivial dynamical constraints.

</details>

## Minimal memory list

A student preparing for AdS/CFT should be able to say the following without looking anything up:

- A CFT is specified by its spectrum and OPE coefficients, subject to consistency.
- A primary plus descendants forms a conformal family.
- Four-point functions decompose into conformal blocks.
- Crossing symmetry is associativity of the OPE.
- Large $N$ factorization is the CFT origin of classical bulk physics.
- Single-trace means single-particle only in the holographic large-$N$ regime.
- The stress tensor is dual to the graviton.
- A conserved current is dual to a bulk gauge field.
- A source is a boundary condition for a bulk field.
- Entanglement entropy becomes area in semiclassical holography.
- Supersymmetric shortening protects some dimensions and OPE data.
- 2D CFT has Virasoro symmetry, modular invariance, and exact-solution tools not available in generic higher-dimensional CFT.
