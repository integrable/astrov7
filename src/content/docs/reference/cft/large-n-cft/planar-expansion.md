---
title: "Planar Expansion"
description: "’t Hooft counting, ribbon graphs, genus expansion, connected correlator scaling, and the emergence of classical bulk physics at large N."
sidebar:
  order: 3
---

## Goal

The previous page explained why single-trace operators behave like one-particle operators and why multi-trace operators behave like multi-particle states. This page explains the organizing principle behind that statement: the **planar expansion**.

The central claim is that matrix large-$N$ theories admit a topological expansion:

$$
\boxed{
\langle \mathcal O_1\cdots \mathcal O_k\rangle_{\rm conn}
=
\sum_{g=0}^{\infty}
N^{2-2g-k}\,G_{g,k}(\lambda)
}
$$

for connected correlators of unit-normalized single-trace operators in an adjoint $U(N)$ or $SU(N)$ gauge theory. Here $g$ is the genus of a ribbon graph and

$$
\lambda=g_{\rm YM}^2N
$$

is the 't Hooft coupling.

This formula is one of the main reasons AdS/CFT is possible. It says that a CFT with many matrix degrees of freedom reorganizes its perturbation theory into the same topology expansion as closed string theory:

$$
\boxed{
\frac{1}{N}\quad\leftrightarrow\quad g_s,
\qquad
\frac{1}{N^2}\quad\leftrightarrow\quad G_N.
}
$$

The large-$N$ limit is therefore not merely a limit with many fields. It is a limit in which the CFT begins to look like a weakly coupled theory of strings and, under additional conditions, like classical gravity in AdS.

## The 't Hooft limit

Consider a gauge theory with gauge group $U(N)$ or $SU(N)$ and adjoint fields. An adjoint field is an $N\times N$ matrix,

$$
\Phi(x)=\Phi^i{}_j(x),
\qquad
 i,j=1,\ldots,N.
$$

A typical Yang-Mills action has the schematic form

$$
S
=
\frac{1}{g_{\rm YM}^2}
\int d^d x\,\operatorname{Tr}\left(F^2+\cdots\right).
$$

The 't Hooft limit is

$$
N\to\infty,
\qquad
\lambda=g_{\rm YM}^2N\quad\text{fixed}.
$$

Equivalently,

$$
g_{\rm YM}^2=\frac{\lambda}{N}.
$$

This is not the same as ordinary weak coupling. If $\lambda$ is held fixed and large, the microscopic gauge coupling $g_{\rm YM}^2$ still goes to zero as $1/N$, but planar diagrams at all orders in $\lambda$ survive. The large-$N$ expansion is an expansion in topology, not an expansion in the number of interaction vertices.

In $\mathcal N=4$ super-Yang-Mills, for example, the planar limit is still a highly interacting quantum theory when $\lambda$ is large. The special thing is that nonplanar corrections are suppressed by powers of $1/N^2$.

Throughout this page, we focus on oriented adjoint matrix theories. Other large-$N$ limits exist. Vector models, theories with many fundamentals, and $SO(N)$ or $Sp(N)$ gauge theories have related but modified counting rules. The oriented ribbon-graph expansion is the one most directly connected to closed oriented strings and the standard AdS$_5$/CFT$_4$ example.

## Double-line notation

The large-$N$ counting is easiest in double-line notation. A matrix field has two color indices, so its propagator carries two index lines:

$$
\langle \Phi^i{}_j\,\Phi^k{}_\ell\rangle
\sim
\delta^i{}_{\ell}\delta^k{}_{j}.
$$

Instead of drawing this as one ordinary line, draw it as a ribbon made from two oriented index lines. Interaction vertices are traces, so their color contractions preserve the cyclic order of matrix indices. The resulting Feynman graphs are not merely graphs; they are discretized two-dimensional surfaces.

The local rules are simple after rescaling fields so that the action takes the schematic form

$$
S
\sim
\frac{N}{\lambda}
\int d^d x\,\operatorname{Tr}\left(\text{quadratic} + \text{interactions}\right).
$$

In this normalization:

| Ingredient | Power of $N$ | Reason |
|---|---:|---|
| closed color-index loop | $N$ | sum over one free color index |
| propagator | $N^{-1}$ | inverse of the quadratic term proportional to $N$ |
| single-trace interaction vertex | $N$ | trace term in the action is multiplied by $N$ |

Therefore a connected ribbon graph with

$$
F=\text{faces},
\qquad
E=\text{edges},
\qquad
V=\text{vertices}
$$

scales as

$$
N^{F-E+V}.
$$

The miracle is that $F-E+V$ is topological. For a closed connected orientable surface of genus $g$,

$$
F-E+V=2-2g.
$$

If the graph has $k$ single-trace operator insertions, these insertions become $k$ marked boundaries or punctures of the ribbon surface. The Euler characteristic becomes

$$
F-E+V=2-2g-k.
$$

Thus

$$
\boxed{
\text{connected genus-$g$ contribution with $k$ single traces}
\sim
N^{2-2g-k}.
}
$$

<figure class="doc-figure" style="--figure-width: 45rem; --caption-width: 55rem;">

![Planar expansion topology](/figures/cft/planar-expansion-topology.svg)

<figcaption>

The planar expansion is a topological expansion of double-line Feynman graphs. A connected genus-$g$ ribbon graph with $k$ unit-normalized single-trace insertions scales as $N^{2-2g-k}$. Adding a handle suppresses the amplitude by $N^{-2}$, matching the closed-string loop expansion with $g_s\sim N^{-1}$.

</figcaption>
</figure>

## Connected correlators and normalization

We use the same convention as in the previous page: a single-trace primary $\mathcal O_A$ is normalized so that

$$
\langle \mathcal O_A(x)\mathcal O_B(0)\rangle
=
\frac{\delta_{AB}}{x^{2\Delta_A}}.
$$

With this convention, the planar connected $k$-point function scales as

$$
\boxed{
\langle \mathcal O_{A_1}\cdots\mathcal O_{A_k}\rangle_{\rm conn,\;planar}
\sim
N^{2-k}.
}
$$

The first few cases are worth memorizing:

| Quantity | Leading connected scaling | Bulk interpretation |
|---|---:|---|
| vacuum free energy | $N^2$ | classical on-shell action |
| one-point function, if allowed | $N$ | classical source response in unit normalization |
| two-point function | $N^0$ | free propagation of one particle |
| three-point function | $N^{-1}$ | cubic bulk coupling |
| connected four-point function | $N^{-2}$ | tree-level bulk exchange or contact interaction |
| genus-one correction to a two-point function | $N^{-2}$ | one-loop bulk correction |
| genus-one correction to a four-point function | $N^{-4}$ | one-loop correction to a tree four-point amplitude |

For many CFT discussions, especially bootstrap discussions, unit two-point normalization is the cleanest convention. For source functionals and classical gravity, another convention is common: define

$$
\mathcal O_A^{\rm source}=N\mathcal O_A.
$$

Then every planar connected correlator of $\mathcal O^{\rm source}$ is of order $N^2$:

$$
\langle \mathcal O_{A_1}^{\rm source}\cdots
\mathcal O_{A_k}^{\rm source}\rangle_{\rm conn,\;planar}
\sim
N^2.
$$

This is why the classical bulk generating functional is of order $N^2$:

$$
W[J]
\sim
N^2\,w_0[J]+N^0\,w_1[J]+N^{-2}\,w_2[J]+\cdots.
$$

The two conventions describe the same physics. Unit-normalized operators make OPE coefficients simple; source-normalized operators make the classical bulk action simple.

## The genus expansion

The full connected large-$N$ expansion has the form

$$
\boxed{
\langle \mathcal O_{A_1}\cdots\mathcal O_{A_k}\rangle_{\rm conn}
=
\sum_{g=0}^{\infty}
N^{2-2g-k}
G_{g;k}(x_i,\lambda).
}
$$

Here $g$ is the genus of the ribbon surface. The leading term is the planar term:

$$
g=0:
\qquad
\langle \mathcal O_1\cdots\mathcal O_k\rangle_{\rm conn}
\sim
N^{2-k}.
$$

The first correction comes from genus one:

$$
g=1:
\qquad
\langle \mathcal O_1\cdots\mathcal O_k\rangle_{\rm conn}^{(g=1)}
\sim
N^{-k}.
$$

Therefore the ratio of genus-one to planar contributions is always

$$
\frac{\text{genus one}}{\text{planar}}
\sim
\frac{1}{N^2}.
$$

Each additional handle gives another factor of $1/N^2$.

This has two immediate consequences. First, for fixed $k$, the large-$N$ expansion is naturally an expansion in even powers of $1/N$ for connected correlators in oriented adjoint theories:

$$
G_{\rm conn}
=
G^{(0)}+\frac{1}{N^2}G^{(1)}+\frac{1}{N^4}G^{(2)}+\cdots
$$

after factoring out the leading $N^{2-k}$.

Second, the planar limit is a closed sector. At $N=\infty$, planar diagrams never mix with nonplanar diagrams. This is the gauge-theory origin of the statement that the dual string theory becomes classical in string perturbation theory.

## Planar does not mean tree-level in the gauge theory

A common trap is to confuse **planar** with **tree-level**. They are completely different notions.

A gauge-theory diagram can be planar and still contain arbitrarily many ordinary momentum loops. In fact, at fixed 't Hooft coupling $\lambda$, the planar contribution includes infinitely many diagrams:

$$
G_{0;k}(\lambda)
=
\sum_{L=0}^{\infty}\lambda^L G_{0;k}^{(L)}.
$$

The index $L$ here counts ordinary perturbative loops in the gauge theory. The index $g$ counts the genus of the color ribbon surface. A diagram can have large $L$ but still have $g=0$.

Thus the large-$N$ expansion and the coupling expansion are independent:

$$
\text{large }N:
\quad
\text{organizes topology},
$$

$$
\text{small }\lambda:
\quad
\text{organizes weak-coupling perturbation theory}.
$$

For AdS/CFT, this distinction is crucial. Classical Einstein gravity is not obtained merely by taking $N\to\infty$. One usually also needs strong 't Hooft coupling and a sparse light spectrum, so that stringy modes are heavy. In $\mathcal N=4$ SYM,

$$
\frac{R_{\rm AdS}^4}{\alpha'^2}
\sim
\lambda,
$$

so large $\lambda$ makes the string length small compared to the AdS radius. Meanwhile,

$$
G_N
\sim
\frac{R_{\rm AdS}^{d-1}}{N^2}
$$

up to theory-dependent constants, so large $N$ suppresses bulk quantum loops.

The two expansions are therefore:

$$
\boxed{
\frac{1}{N}
\quad\text{controls string loops / bulk quantum effects},
}
$$

$$
\boxed{
\frac{1}{\lambda}
\quad\text{controls stringy higher-derivative effects in the canonical example}.
}
$$

Large $N$ gives weakly coupled strings. Large $\lambda$ can turn those strings into weakly curved gravity.

## Why the expansion looks like closed string theory

A closed string worldsheet of genus $g$ with $k$ external closed-string insertions contributes with a power

$$
g_s^{2g-2+k}.
$$

The matrix-theory result is

$$
N^{2-2g-k}.
$$

These match under

$$
g_s\sim \frac{1}{N}.
$$

This is the original 't Hooft insight: the large-$N$ expansion of matrix gauge theory has the topology of a closed-string perturbation expansion.

The match is not just a poetic analogy. In holographic CFTs, single-trace operators are dual to single closed-string states or bulk fields. Their connected correlators compute string scattering amplitudes in AdS. The genus expansion of the CFT is the string loop expansion of the bulk.

The dictionary is:

| CFT large-$N$ object | Bulk/string object |
|---|---|
| planar connected correlator | genus-zero closed-string amplitude |
| nonplanar correction | higher-genus string amplitude |
| $1/N$ | string coupling $g_s$ |
| $1/N^2$ | bulk loop-counting parameter $G_N/R_{\rm AdS}^{d-1}$ |
| single trace | one closed-string state or one bulk field |
| multi trace | multi-particle state |

In a classical gravity regime, genus-zero string amplitudes reduce further to tree-level Witten diagrams in AdS.

## Bulk effective action from large-$N$ counting

The same scaling can be seen from the bulk side. Suppose the bulk has a scalar field $\phi$ dual to a unit-normalized single-trace operator $\mathcal O$. A schematic bulk action has the form

$$
S_{\rm bulk}
=
\frac{1}{G_N}
\int d^{d+1}x\sqrt g
\left[
\frac12(\nabla\phi)^2
+
\frac12m^2\phi^2
+a_3\phi^3
+a_4\phi^4
+\cdots
\right].
$$

Since

$$
\frac{R_{\rm AdS}^{d-1}}{G_N}
\sim
C_T
\sim
N^2,
$$

we can think schematically of

$$
S_{\rm bulk}
\sim
N^2\int
\left[
\frac12(\nabla\phi)^2+\frac12m^2\phi^2+a_3\phi^3+a_4\phi^4+\cdots
\right].
$$

Now define a canonically normalized bulk fluctuation

$$
\varphi=N\phi.
$$

Then

$$
S_{\rm bulk}
\sim
\int
\left[
\frac12(\nabla\varphi)^2
+\frac12m^2\varphi^2
+\frac{a_3}{N}\varphi^3
+\frac{a_4}{N^2}\varphi^4
+\cdots
\right].
$$

Thus cubic couplings of canonically normalized bulk fields scale as

$$
g_3^{\rm bulk}\sim \frac{1}{N},
$$

quartic couplings scale as

$$
g_4^{\rm bulk}\sim \frac{1}{N^2},
$$

and each bulk loop is suppressed by

$$
G_N\sim \frac{1}{N^2}.
$$

This reproduces the CFT scaling:

$$
\langle \mathcal O\mathcal O\mathcal O\rangle
\sim
\frac{1}{N},
$$

$$
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle_{\rm conn}
\sim
\frac{1}{N^2}.
$$

In other words, the bulk classical action is large, of order $N^2$, but canonically normalized interactions are small. This is exactly how classical physics emerges: quantum fluctuations are suppressed because the action is large.

## Factorization and classicality

Large-$N$ factorization says that products of gauge-invariant operators behave classically at leading order. For normalized single-trace operators,

$$
\langle \mathcal O_A\mathcal O_B\rangle
-
\langle \mathcal O_A\rangle\langle \mathcal O_B\rangle
\sim
N^0,
$$

while expectation values of source-normalized operators are of order $N$. More invariantly, relative connected fluctuations are suppressed.

For example, if an operator $X$ has expectation value $\langle X\rangle\sim N^2$, and connected variance $\langle X^2\rangle_c\sim N^2$, then

$$
\frac{\sqrt{\langle X^2\rangle_c}}{\langle X\rangle}
\sim
\frac{1}{N}.
$$

So the collective gauge-invariant variables become sharply peaked at large $N$.

This is the CFT version of a classical saddle point. In the bulk, it appears as a classical geometry or classical field configuration. The connected generating functional has the expansion

$$
W[J]
=
N^2 W_0[J]+W_1[J]+\frac{1}{N^2}W_2[J]+\cdots.
$$

The leading term $W_0[J]$ is computed by the classical on-shell bulk action:

$$
W_0[J]
\quad\leftrightarrow\quad
S_{\rm bulk}^{\rm on-shell}[\phi_{\partial}=J].
$$

The subleading term $W_1[J]$ is a one-loop bulk determinant, and so on.

## Spectral data in the planar expansion

The planar expansion is not only about Feynman diagrams. It organizes CFT data.

For a single-trace primary $\mathcal O_A$, its scaling dimension has an expansion

$$
\Delta_A
=
\Delta_A^{(0)}(\lambda)
+
\frac{1}{N^2}\Delta_A^{(1)}(\lambda)
+
\frac{1}{N^4}\Delta_A^{(2)}(\lambda)
+
\cdots.
$$

The leading function $\Delta_A^{(0)}(\lambda)$ is already the full planar anomalous dimension. It may be highly nontrivial. In planar $\mathcal N=4$ SYM, much of this function is controlled by integrability. The $1/N^2$ correction is nonplanar; in the bulk it is a quantum correction to the mass of the corresponding string or particle state.

For a three-point coefficient of unit-normalized single-trace primaries,

$$
C_{ABC}
=
\frac{1}{N}C_{ABC}^{(0)}(\lambda)
+
\frac{1}{N^3}C_{ABC}^{(1)}(\lambda)
+
\cdots.
$$

For a connected four-point function,

$$
\mathcal G(u,v)
=
\mathcal G_{\rm MFT}(u,v)
+
\frac{1}{N^2}\mathcal G^{(1)}(u,v)
+
\frac{1}{N^4}\mathcal G^{(2)}(u,v)
+
\cdots.
$$

Here $\mathcal G_{\rm MFT}$ is the disconnected generalized-free or mean-field answer. The term $\mathcal G^{(1)}$ is the leading connected correction; in the bulk it comes from tree-level Witten diagrams. The term $\mathcal G^{(2)}$ includes one-loop Witten diagrams and also effects of higher-order corrections to CFT data.

Double-trace anomalous dimensions also have a planar expansion:

$$
\Delta_{n,\ell}
=
2\Delta+2n+\ell
+
\frac{1}{N^2}\gamma_{n,\ell}^{(1)}(\lambda)
+
\frac{1}{N^4}\gamma_{n,\ell}^{(2)}(\lambda)
+
\cdots.
$$

The leading correction $\gamma_{n,\ell}^{(1)}$ is a tree-level bulk binding energy or phase shift. The next correction is a loop correction.

## Disconnected diagrams and mean field theory

For four-point functions, the leading term is often disconnected:

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\langle \mathcal O_1\mathcal O_2\rangle
\langle \mathcal O_3\mathcal O_4\rangle
+
\text{permutations}
+
O(N^{-2}).
$$

This leading disconnected term is not a connected planar surface with $k=4$. Rather, it is a product of connected two-point functions. Each two-point function is order $N^0$, so the product is order $N^0$.

The connected four-point function begins at

$$
N^{2-4}=N^{-2}.
$$

This distinction is vital for the bootstrap. The leading mean-field four-point function already contains an infinite tower of double-trace conformal blocks. The connected $1/N^2$ correction then shifts the dimensions and OPE coefficients of those double-trace operators and may add single-trace exchange.

Schematic bootstrap organization:

$$
\mathcal G
=
\underbrace{\mathcal G_{\rm MFT}}_{\text{identity + leading double traces}}
+
\frac{1}{N^2}
\underbrace{\mathcal G^{(1)}}_{\text{tree-level interactions}}
+
\frac{1}{N^4}
\underbrace{\mathcal G^{(2)}}_{\text{one-loop interactions}}
+
\cdots.
$$

This is one of the cleanest ways to see Witten diagrams directly from CFT data.

## Stress tensor normalization and $C_T$

The stress tensor is not an arbitrary single-trace operator. Its normalization is fixed by Ward identities. The two-point function is usually written schematically as

$$
\langle T_{\mu\nu}(x)T_{\rho\sigma}(0)\rangle
\sim
\frac{C_T}{x^{2d}}
\times
\text{fixed tensor structure}.
$$

In matrix large-$N$ theories with adjoint degrees of freedom,

$$
C_T\sim N^2.
$$

A unit-normalized stress tensor is therefore

$$
\widehat T_{\mu\nu}
=
\frac{T_{\mu\nu}}{\sqrt{C_T}}
\sim
\frac{T_{\mu\nu}}{N}.
$$

Then its connected correlators follow the same rule as other unit-normalized single-trace operators:

$$
\langle \widehat T\widehat T\widehat T\rangle
\sim
\frac{1}{N},
$$

$$
\langle \widehat T\widehat T\widehat T\widehat T\rangle_{\rm conn}
\sim
\frac{1}{N^2}.
$$

The bulk dual of $T_{\mu\nu}$ is the graviton. The statement $C_T\sim N^2$ is the CFT version of

$$
\frac{R_{\rm AdS}^{d-1}}{G_N}
\sim
C_T.
$$

Large $C_T$ suppresses graviton loops. This is why modern bootstrap discussions often use $1/C_T$ rather than $1/N^2$ as the universal expansion parameter:

$$
\frac{1}{C_T}
\quad\leftrightarrow\quad
\frac{G_N}{R_{\rm AdS}^{d-1}}.
$$

In theories whose number of degrees of freedom is not literally $N^2$, such as some M-theory examples, $C_T$ is the more invariant quantity.

## Classical gravity requires more than planarity

The planar expansion gives a weakly coupled closed-string expansion, but a weakly coupled string theory is not automatically Einstein gravity.

For a CFT to have a local Einstein-like AdS dual, one expects at least two additional features:

1. A large central charge:

$$
C_T\gg 1.
$$

2. A sparse spectrum of light single-trace higher-spin operators, often phrased as a large gap $\Delta_{\rm gap}$ to single-trace operators with spin $\ell>2$:

$$
\Delta_{\rm gap}\gg 1.
$$

The first condition suppresses bulk loops. The second condition suppresses stringy or higher-spin effects and allows a local low-energy derivative expansion. Without the second condition, the dual can be a weakly coupled higher-spin theory rather than ordinary gravity.

Thus:

$$
\boxed{
\text{large }N
\Rightarrow
\text{weakly coupled bulk expansion},
}
$$

but

$$
\boxed{
\text{large }N+\text{sparse light spectrum}
\Rightarrow
\text{local semiclassical gravity regime}.
}
$$

This distinction is one of the main lessons of modern holographic CFT.

## What changes for fundamentals and other large-$N$ limits?

The formula

$$
N^{2-2g-k}
$$

is the cleanest statement for connected correlators of single-trace operators in oriented adjoint matrix theories. Other theories modify the topology.

If a gauge theory has fundamental matter with $N_f$ fixed as $N\to\infty$, a closed fundamental loop gives a factor $N_f$ rather than $N$. Such loops are suppressed relative to adjoint loops. In a string interpretation, they often correspond to open-string boundaries or flavor branes.

If $N_f/N$ is kept fixed, fundamental loops can survive at leading order. The holographic interpretation then changes: flavor degrees of freedom backreact on the geometry.

For $SO(N)$ or $Sp(N)$ gauge theories, double-line graphs may become nonorientable. The topological expansion includes crosscaps as well as handles. In such cases, corrections can appear in powers associated with nonorientable worldsheet topology.

For vector models, the natural large-$N$ operators are singlet bilinears rather than matrix traces. Their large-$N$ expansion is not the same as the closed-string genus expansion of adjoint matrix theories. Vector models can still have AdS duals, but the duals are typically higher-spin theories rather than ordinary Einstein gravity.

This course emphasizes matrix large-$N$ CFTs because they are the direct path to standard AdS/CFT.

## AdS/CFT checkpoint

The planar expansion is the CFT origin of perturbative quantum gravity in AdS.

For unit-normalized single-trace operators,

$$
\langle \mathcal O_1\cdots\mathcal O_k\rangle_{\rm conn}
\sim
N^{2-k}
\left(1+O\left(\frac{1}{N^2}\right)\right).
$$

In the bulk, this means that canonically normalized fields have interactions suppressed by $1/N$:

$$
\phi^3:\;\frac{1}{N},
\qquad
\phi^4:\;\frac{1}{N^2},
\qquad
\text{one loop}:\;\frac{1}{N^2}.
$$

Equivalently,

$$
\boxed{
N\to\infty
\quad\leftrightarrow\quad
G_N\to0.
}
$$

The bulk theory becomes classical because connected quantum fluctuations are suppressed. But the detailed classical theory depends on the planar CFT data as a function of $\lambda$. At weak $\lambda$, the planar theory is usually far from gravity. At strong $\lambda$ and with a large higher-spin gap, it can become classical Einstein gravity plus matter fields in AdS.

## Summary

The planar expansion is the topological expansion of large-$N$ matrix theories. In double-line notation, a connected ribbon graph with genus $g$ and $k$ single-trace insertions scales as

$$
N^{2-2g-k}.
$$

Therefore unit-normalized connected correlators obey

$$
\langle \mathcal O_1\cdots\mathcal O_k\rangle_{\rm conn}
=
\sum_{g=0}^{\infty}N^{2-2g-k}G_{g,k}(\lambda).
$$

Planar diagrams are genus zero. Nonplanar corrections are suppressed by $1/N^2$ per handle.

The same expansion is the closed-string genus expansion with

$$
g_s\sim \frac{1}{N}.
$$

In a holographic CFT with $C_T\sim N^2$, the expansion parameter for bulk loops is

$$
\frac{1}{C_T}\sim \frac{G_N}{R_{\rm AdS}^{d-1}}.
$$

Planarity explains why a large-$N$ CFT has weakly interacting single-particle and multi-particle sectors. A further large gap in the single-trace spectrum is what turns this weakly coupled bulk theory into local semiclassical gravity.

## Exercises

### Exercise 1. Euler counting for ribbon graphs

A connected double-line graph has $F$ color faces, $E$ propagators, and $V$ interaction vertices. Show that its color factor is $N^{F-E+V}$. Then explain why a graph of genus $g$ with $k$ single-trace insertions scales as $N^{2-2g-k}$.

<details><summary><strong>Solution</strong></summary>

Each closed color-index loop gives a free sum over an index,

$$
\sum_{i=1}^N 1=N,
$$

so the faces contribute $N^F$. In the standard 't Hooft normalization, each propagator contributes $N^{-1}$ and each single-trace interaction vertex contributes $N$. Thus the total color factor is

$$
N^F N^{-E}N^V=N^{F-E+V}.
$$

A double-line graph is a cell decomposition of an orientable surface. If the connected surface has genus $g$ and $k$ boundaries or punctures associated with single-trace insertions, its Euler characteristic is

$$
\chi=F-E+V=2-2g-k.
$$

Therefore the graph scales as

$$
N^{F-E+V}=N^{2-2g-k}.
$$

</details>

### Exercise 2. Leading scaling of connected correlators

Using

$$
\langle \mathcal O_1\cdots\mathcal O_k\rangle_{\rm conn,g}
\sim
N^{2-2g-k},
$$

compute the leading planar scaling of the connected two-, three-, and four-point functions of unit-normalized single-trace operators.

<details><summary><strong>Solution</strong></summary>

The planar contribution has $g=0$, so

$$
\langle \mathcal O_1\cdots\mathcal O_k\rangle_{\rm conn,planar}
\sim
N^{2-k}.
$$

For $k=2$,

$$
\langle \mathcal O_1\mathcal O_2\rangle_{\rm conn}
\sim
N^0.
$$

For $k=3$,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle_{\rm conn}
\sim
N^{-1}.
$$

For $k=4$,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle_{\rm conn}
\sim
N^{-2}.
$$

These are precisely the expected scalings of the two-point normalization, cubic bulk coupling, and tree-level four-point bulk interaction.

</details>

### Exercise 3. Genus suppression

For fixed $k$, compare the genus-$g+1$ contribution with the genus-$g$ contribution. Show that adding one handle suppresses the amplitude by $1/N^2$.

<details><summary><strong>Solution</strong></summary>

The genus-$g$ contribution scales as

$$
N^{2-2g-k}.
$$

The genus-$(g+1)$ contribution scales as

$$
N^{2-2(g+1)-k}=N^{2-2g-k-2}.
$$

The ratio is therefore

$$
\frac{N^{2-2(g+1)-k}}{N^{2-2g-k}}
=
N^{-2}.
$$

Thus every additional handle is suppressed by one power of $1/N^2$. In the bulk, this is the loop-counting factor.

</details>

### Exercise 4. Bulk coupling normalization

Suppose a bulk scalar has schematic action

$$
S=N^2\int d^{d+1}x\sqrt g
\left[
\frac12(\nabla\phi)^2+\frac12m^2\phi^2+a_3\phi^3+a_4\phi^4
\right].
$$

Define $\varphi=N\phi$. Show that the cubic and quartic interactions of the canonically normalized field scale as $1/N$ and $1/N^2$.

<details><summary><strong>Solution</strong></summary>

Substitute

$$
\phi=\frac{\varphi}{N}
$$

into the action. The quadratic part becomes

$$
N^2\int \frac12(\nabla\phi)^2
=
N^2\int \frac12\frac{(\nabla\varphi)^2}{N^2}
=
\int \frac12(\nabla\varphi)^2,
$$

so $\varphi$ is canonically normalized.

The cubic term becomes

$$
N^2\int a_3\phi^3
=
N^2\int a_3\frac{\varphi^3}{N^3}
=
\frac{1}{N}\int a_3\varphi^3.
$$

The quartic term becomes

$$
N^2\int a_4\phi^4
=
N^2\int a_4\frac{\varphi^4}{N^4}
=
\frac{1}{N^2}\int a_4\varphi^4.
$$

Thus

$$
g_3\sim \frac{1}{N},
\qquad
 g_4\sim \frac{1}{N^2}.
$$

This matches the CFT scaling of unit-normalized three- and connected four-point functions.

</details>

### Exercise 5. Source normalization

Let $\mathcal O$ be a unit-normalized single-trace operator with connected $k$-point functions scaling as

$$
\langle \mathcal O^k\rangle_{\rm conn}
\sim
N^{2-k}.
$$

Define a source-normalized operator

$$
\mathcal O^{\rm source}=N\mathcal O.
$$

Show that planar connected correlators of $\mathcal O^{\rm source}$ are all of order $N^2$.

<details><summary><strong>Solution</strong></summary>

The connected $k$-point function of the source-normalized operator is

$$
\langle (\mathcal O^{\rm source})^k\rangle_{\rm conn}
=
N^k\langle \mathcal O^k\rangle_{\rm conn}.
$$

Using the unit-normalized scaling,

$$
N^k\langle \mathcal O^k\rangle_{\rm conn}
\sim
N^k N^{2-k}=N^2.
$$

So in source normalization all planar connected correlators are order $N^2$. This is why the classical bulk generating functional has the form

$$
W[J]=N^2 W_0[J]+O(N^0).
$$

</details>

### Exercise 6. Planar versus weak coupling

Explain why a planar diagram can contain ordinary momentum loops. Why does this mean that the planar limit need not be a free theory?

<details><summary><strong>Solution</strong></summary>

Planarity refers to the topology of the color-index ribbon graph. A diagram is planar if its double-line structure can be drawn on a sphere without handles. This says nothing about the number of ordinary momentum loops.

At fixed 't Hooft coupling $\lambda$, the planar contribution is a sum over all planar diagrams:

$$
G_{0;k}(\lambda)
=
\sum_{L=0}^{\infty}\lambda^L G_{0;k}^{(L)}.
$$

The integer $L$ counts ordinary perturbative loops. All these terms can contribute at the same genus $g=0$. Therefore the planar theory can be strongly interacting when $\lambda$ is large. Large $N$ suppresses nonplanar topology, not necessarily interactions within the planar sector.

</details>

## Further reading

The classic origin of the topology expansion is 't Hooft's planar-diagram analysis of large-$N$ gauge theory. For AdS/CFT, the essential next step is the identification of the same expansion with string perturbation theory. Useful complementary perspectives include Witten diagrams, conformal perturbation theory around generalized free fields, and the large-$C_T$ bootstrap.

For this course, the most important takeaway is practical: whenever you see a holographic CFT four-point function written as

$$
\mathcal G=\mathcal G_{\rm MFT}+\frac{1}{N^2}\mathcal G^{(1)}+\cdots,
$$

you should immediately read it as

$$
\text{free bulk propagation}
+
\text{tree-level bulk interactions}
+
\text{bulk loops}
+
\cdots.
$$
