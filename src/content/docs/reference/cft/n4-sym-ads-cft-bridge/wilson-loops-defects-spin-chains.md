---
title: "Wilson Loops, Defects, and Spin Chains"
description: "Line defects, defect local operators, and planar spin-chain sectors of N=4 SYM as bridges to strings in AdS."
sidebar:
  order: 3
---

## Goal

So far, the course has treated a CFT mainly as a theory of local operators: primaries, descendants, OPE coefficients, conformal blocks, chiral primaries, and large-$N$ single-trace states. That is the right foundation, but it is not the whole story. A gauge CFT also contains extended operators. In $\mathcal N=4$ super Yang--Mills, the most important extended operators are Wilson loops.

This page explains three related structures:

1. Wilson loops, which are gauge-invariant observables supported on curves.
2. Defect CFT data, which arise when a Wilson line creates a lower-dimensional conformal defect.
3. Planar spin chains, which reorganize the anomalous-dimension problem for long single-trace operators.

They are deeply tied to AdS/CFT. Wilson loops become string worldsheets, defect operators become open-string fluctuations, and planar spin chains become the weak-coupling face of closed-string dynamics on $\mathrm{AdS}_5\times S^5$.

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 55rem;">

![Wilson loops, defects, and spin chains in the AdS/CFT bridge](/figures/cft/wilson-defect-spin-chain-dictionary.svg)

<figcaption>

Wilson loops, defect operators, and planar spin chains are three structured observables in $\mathcal N=4$ SYM. At large $N$ and strong $\lambda$, they map respectively to string worldsheets, open-string or brane-localized modes, and closed-string states in $\mathrm{AdS}_5\times S^5$.

</figcaption>
</figure>

## Wilson loops in gauge theory

In a gauge theory, the gauge potential $A_\mu(x)$ is not gauge invariant. Local gauge-invariant operators are built from traces such as $\operatorname{Tr}F_{\mu\nu}F^{\mu\nu}$ or $\operatorname{Tr}(\Phi^I\Phi^J)$. But gauge theory also has natural nonlocal observables.

Given a path $C$ from $x_i$ to $x_f$, the Wilson line in a representation $R$ is

$$
U_R[C_{x_i\to x_f}]
=
\mathcal P\exp\left(i\int_C A_\mu dx^\mu\right)
=
\mathcal P\exp\left(i\int ds\,A_\mu(x(s))\dot x^\mu(s)\right),
$$

where $A_\mu=A_\mu^aT_R^a$ and $\mathcal P$ denotes path ordering. Under a gauge transformation,

$$
A_\mu\mapsto gA_\mu g^{-1}-i(\partial_\mu g)g^{-1},
$$

the Wilson line transforms as

$$
U_R[C_{x_i\to x_f}]
\mapsto
R(g(x_f))U_R[C_{x_i\to x_f}]R(g(x_i))^{-1}.
$$

Thus an open Wilson line is not gauge invariant by itself. For a closed curve $C$, the traced Wilson loop

$$
W_R[C]
=
\frac{1}{\dim R}\operatorname{Tr}_R U_R[C]
$$

is gauge invariant by cyclicity of the trace.

In $\mathcal N=4$ SYM, the canonical supersymmetric loop couples also to the six adjoint scalar fields $\Phi^I$. It is usually called the Maldacena--Wilson loop:

$$
W_R[C,n]
=
\frac{1}{\dim R}\operatorname{Tr}_R\mathcal P
\exp\int_C ds\left(iA_\mu(x(s))\dot x^\mu(s)+|\dot x(s)|n_I(s)\Phi^I(x(s))\right),
$$

with

$$
n_In_I=1.
$$

The scalar coupling is essential. It is what makes the straight line and the circle compatible with supersymmetry. Different sign conventions appear in the literature, especially between Euclidean and Lorentzian signature; the invariant point is that the loop couples to a ten-dimensional-looking connection built from $A_\mu$ and the six scalars.

## The half-BPS straight line and circle

The most important example is the half-BPS straight Wilson line. Place the line along a coordinate $\tau$ and choose a fixed scalar direction, say $\Phi^6$:

$$
W_{\mathrm{line}}
=
\frac{1}{N}\operatorname{Tr}\mathcal P
\exp\int_{-\infty}^{\infty}d\tau\left(iA_\tau+\Phi^6\right).
$$

The line preserves the one-dimensional conformal group acting along $\tau$:

$$
SL(2,\mathbb R).
$$

It also preserves rotations transverse to the line,

$$
SO(3),
$$

and the scalar coupling breaks the original $SO(6)_R$ symmetry to

$$
SO(5)_R.
$$

Together with preserved supercharges, the full symmetry of the half-BPS line is often denoted $OSp(4^*|4)$, whose bosonic subgroup contains

$$
SL(2,\mathbb R)\times SO(3)\times SO(5)_R.
$$

A circle is conformally related to a straight line. Quantum mechanically, the half-BPS circular Wilson loop has a nontrivial expectation value, while the line has expectation value $1$ in the usual supersymmetric normalization. The difference is not a contradiction: the conformal map between the line and the circle involves the point at infinity and changes the infrared/ultraviolet treatment of the operator.

## Wilson line as a defect CFT

The insertion of a straight Wilson line breaks the ambient four-dimensional conformal symmetry, but preserves a lower-dimensional conformal subgroup. Therefore the theory in the presence of the line is a defect CFT.

There are two kinds of operators:

- ambient operators $\mathcal O(x)$, inserted away from the line;
- defect operators $\widehat{\mathcal O}(\tau)$, inserted on the line.

A normalized ambient one-point function in the presence of the line is

$$
\langle \mathcal O(x)\rangle_W
=
\frac{\langle W\mathcal O(x)\rangle}{\langle W\rangle}.
$$

For a scalar primary of dimension $\Delta$, transverse rotations and one-dimensional conformal symmetry fix

$$
\langle \mathcal O(\tau,x_\perp)\rangle_W
=
\frac{a_{\mathcal O}}{|x_\perp|^\Delta},
$$

if the preserved quantum numbers allow the one-point function. The coefficient $a_{\mathcal O}$ is part of the defect CFT data.

A defect operator is an insertion inside the path-ordered exponential. Schematically,

$$
W[\widehat{\mathcal O}_1(\tau_1)\cdots \widehat{\mathcal O}_n(\tau_n)]
=
\frac{1}{N}\operatorname{Tr}\mathcal P\left[
\widehat{\mathcal O}_1(\tau_1)\cdots \widehat{\mathcal O}_n(\tau_n)
\exp\int d\tau\,(iA_\tau+\Phi^6)
\right].
$$

The normalized defect correlator is

$$
\left\langle\widehat{\mathcal O}_1(\tau_1)\cdots \widehat{\mathcal O}_n(\tau_n)\right\rangle_W
=
\frac{\left\langle W[\widehat{\mathcal O}_1(\tau_1)\cdots \widehat{\mathcal O}_n(\tau_n)]\right\rangle}{\langle W\rangle}.
$$

## One-dimensional conformal kinematics

The group $SL(2,\mathbb R)$ acts on the line by fractional linear transformations:

$$
\tau\mapsto \tau'=
\frac{a\tau+b}{c\tau+d},
\qquad ad-bc=1.
$$

A defect primary of dimension $\widehat\Delta$ transforms as

$$
\widehat{\mathcal O}'(\tau')
=
\left|\frac{d\tau'}{d\tau}\right|^{-\widehat\Delta}\widehat{\mathcal O}(\tau).
$$

Consequently, in an orthonormal basis of defect primaries,

$$
\left\langle\widehat{\mathcal O}_a(\tau_1)\widehat{\mathcal O}_b(\tau_2)\right\rangle_W
=
\frac{\delta_{ab}}{|\tau_{12}|^{2\widehat\Delta_a}}.
$$

The three-point function is

$$
\left\langle
\widehat{\mathcal O}_a(\tau_1)
\widehat{\mathcal O}_b(\tau_2)
\widehat{\mathcal O}_c(\tau_3)
\right\rangle_W
=
\frac{\widehat C_{abc}}
{|\tau_{12}|^{\widehat\Delta_a+\widehat\Delta_b-\widehat\Delta_c}
 |\tau_{23}|^{\widehat\Delta_b+\widehat\Delta_c-\widehat\Delta_a}
 |\tau_{13}|^{\widehat\Delta_a+\widehat\Delta_c-\widehat\Delta_b}}.
$$

Four-point functions depend on one cross-ratio,

$$
\chi=
\frac{\tau_{12}\tau_{34}}{\tau_{13}\tau_{24}}.
$$

Thus a Wilson line gives a lower-dimensional CFT problem with data

$$
\left\{\widehat\Delta_a,\widehat C_{abc},a_{\mathcal O},b_{\mathcal O\widehat{\mathcal O}},\ldots\right\}.
$$

Here $b_{\mathcal O\widehat{\mathcal O}}$ are bulk-to-defect OPE coefficients. As an ambient operator approaches the line,

$$
\mathcal O(\tau,x_\perp)
\sim
\sum_{\widehat{\mathcal O}}
\frac{b_{\mathcal O\widehat{\mathcal O}}}{|x_\perp|^{\Delta-\widehat\Delta}}
\widehat{\mathcal O}(\tau)+\cdots.
$$

This is the defect analogue of the ordinary OPE.

## The displacement operator

The most universal defect operator is the displacement operator $D^i(\tau)$, where $i$ labels transverse directions. A line defect breaks translations transverse to the line. The corresponding Ward identity has the schematic form

$$
\partial_\mu T^{\mu i}(x)
=
\delta^{(3)}(x_\perp)D^i(\tau).
$$

Away from the defect, the stress tensor is conserved. At the defect, transverse momentum can be absorbed by the line. The operator $D^i$ measures the response of the defect to small shape deformations.

For a line defect, the displacement operator has protected dimension

$$
\widehat\Delta_D=2.
$$

Its two-point function is fixed up to one coefficient:

$$
\langle D^i(\tau)D^j(0)\rangle_W
=
\frac{C_D\delta^{ij}}{|\tau|^4}.
$$

In the half-BPS Wilson line of $\mathcal N=4$ SYM, this coefficient is related to the Bremsstrahlung function $B$, which also controls the small-angle expansion of the cusp anomalous dimension.

## Cusps and anomalous dimensions

A smooth Wilson loop has local UV divergences associated with its length. A Wilson loop with a cusp has an additional logarithmic divergence. For a cusp with spacetime angle $\varphi$ and scalar internal angle $\theta$, one writes schematically

$$
\langle W_{\mathrm{cusp}}\rangle
\sim
\exp\left[-\Gamma_{\mathrm{cusp}}(\varphi,\theta)\log\frac{\Lambda_{\mathrm{UV}}}{\mu}\right].
$$

The function $\Gamma_{\mathrm{cusp}}$ is the cusp anomalous dimension. It is important far beyond Wilson loops: it appears in the infrared structure of gauge-theory scattering amplitudes, in anomalous dimensions of large-spin operators, and in integrability.

Near a BPS cusp in $\mathcal N=4$ SYM,

$$
\Gamma_{\mathrm{cusp}}(\varphi,\theta)
=
B(\lambda,N)(\theta^2-\varphi^2)+O(\varphi^4,\theta^4,\varphi^2\theta^2),
$$

up to sign conventions associated with Euclidean versus Lorentzian continuation. The key lesson is structural: deforming a conformal line defect produces universal defect observables.

## Wilson loops in AdS/CFT

At large $N$ and large 't Hooft coupling,

$$
\lambda=g_{\mathrm{YM}}^2N,
$$

a Wilson loop in the fundamental representation is dual to a fundamental string worldsheet ending on the contour $C$ at the AdS boundary:

$$
\boxed{
\langle W[C]\rangle
\sim
\exp\left[-S_{\mathrm{F1}}^{\mathrm{ren}}(\Sigma_C)\right]
}.
$$

More explicitly,

$$
S_{\mathrm{F1}}^{\mathrm{cl}}
=
\frac{1}{2\pi\alpha'}A(\Sigma_C),
\qquad
\frac{L^2}{\alpha'}=\sqrt\lambda,
$$

so the semiclassical answer is

$$
\langle W[C]\rangle
\approx
\exp\left[-\frac{\sqrt\lambda}{2\pi}A_{\mathrm{ren}}(\Sigma_C)\right].
$$

The scalar coupling $n_I\Phi^I$ specifies boundary conditions on $S^5$. Thus a supersymmetric Wilson loop is not only a contour in spacetime; it is also a choice of internal path on the sphere.

For a rectangular Wilson loop of spatial size $R$ and time extent $T\gg R$,

$$
\langle W_{\mathrm{rect}}\rangle
\sim e^{-TV(R)}.
$$

Conformal invariance requires

$$
V(R)=-\frac{c(\lambda)}{R}.
$$

The strong-coupling classical string computation gives

$$
V(R)
=
-\frac{4\pi^2}{\Gamma(1/4)^4}\frac{\sqrt\lambda}{R}
+O(\lambda^0).
$$

For the half-BPS circle, supersymmetric localization gives, in the planar limit,

$$
\langle W_\circ\rangle
=
\frac{2}{\sqrt\lambda}I_1(\sqrt\lambda),
$$

so at strong coupling

$$
\log\langle W_\circ\rangle
=
\sqrt\lambda+O(\log\lambda),
$$

matching the classical string area.

## Defect operators as open-string fluctuations

The straight half-BPS Wilson line is dual to a fundamental string whose induced worldsheet geometry is $\mathrm{AdS}_2$. Defect operators inserted on the line correspond to fluctuations of this open string.

The schematic dictionary is

$$
\widehat{\mathcal O}(\tau)
\quad\longleftrightarrow\quad
\text{field on the }\mathrm{AdS}_2\text{ worldsheet}.
$$

For a scalar fluctuation of mass $m$ on $\mathrm{AdS}_2$ with radius $\ell$, the defect dimension obeys

$$
m^2\ell^2=\widehat\Delta(\widehat\Delta-1).
$$

This is the $\mathrm{AdS}_{p+1}/\mathrm{CFT}_p$ version of the ordinary scalar mass-dimension relation, specialized to $p=1$.

Thus the Wilson line is not merely a number whose expectation value one computes. It is a lower-dimensional holographic system embedded inside the original four-dimensional CFT.

## From single traces to spin chains

Now return to local single-trace operators. A long single-trace operator is a cyclic word:

$$
\mathcal O
=
\operatorname{Tr}(X_1X_2\cdots X_L),
$$

where each $X_\ell$ is an adjoint field, covariant derivative, or composite letter. In the planar limit, the ordering of letters inside the trace is meaningful. The trace behaves like a closed chain.

The dilatation operator acts on these words:

$$
D\mathcal O_\alpha=\Delta_\alpha\mathcal O_\alpha.
$$

Perturbatively,

$$
D=D_0+\lambda D_1+\lambda^2D_2+\cdots.
$$

At planar one loop, interactions are nearest-neighbor along the trace. Therefore $D_1$ is a spin-chain Hamiltonian.

The cleanest example is the $SU(2)$ scalar sector. Define

$$
Z=\Phi^1+i\Phi^2,
\qquad
X=\Phi^3+i\Phi^4,
$$

and consider operators made only from $Z$ and $X$:

$$
\mathcal O_{\mathrm{word}}
=
\operatorname{Tr}(ZXXZZX\cdots).
$$

Each site has two states,

$$
Z\equiv |\uparrow\rangle,
\qquad
X\equiv |\downarrow\rangle.
$$

The planar one-loop anomalous dimension in this sector is governed by

$$
\gamma^{(1)}
=
\frac{\lambda}{8\pi^2}\sum_{\ell=1}^{L}(1-P_{\ell,\ell+1}),
$$

where $P_{\ell,\ell+1}$ swaps neighboring spin-chain sites and periodicity means $P_{L,L+1}=P_{L,1}$. This is the ferromagnetic Heisenberg $XXX_{1/2}$ spin chain, up to normalization.

The state

$$
\operatorname{Tr}Z^L
$$

is the ferromagnetic vacuum. It is half-BPS, so its anomalous dimension vanishes. In spin-chain language, $(1-P_{\ell,\ell+1})$ annihilates every neighboring pair.

## Magnons and Bethe equations

Replacing one $Z$ by an $X$ creates a magnon. On a long chain,

$$
|p\rangle
=
\sum_{n=1}^{L}e^{ipn}\operatorname{Tr}(Z^{n-1}XZ^{L-n}).
$$

The one-loop energy is

$$
\gamma^{(1)}(p)
=
\frac{\lambda}{2\pi^2}\sin^2\frac p2.
$$

For a closed single trace, cyclicity imposes the zero-total-momentum condition

$$
e^{i(p_1+\cdots+p_M)}=1.
$$

A single magnon with nonzero momentum is therefore not a physical closed-chain state by itself, but it is a useful building block of multi-magnon states.

The one-loop Bethe ansatz introduces rapidities $u_k$ related to magnon momenta by

$$
e^{ip_k}=\frac{u_k+i/2}{u_k-i/2}.
$$

The Bethe equations are

$$
\left(\frac{u_k+i/2}{u_k-i/2}\right)^L
=
\prod_{j\ne k}^{M}\frac{u_k-u_j+i}{u_k-u_j-i},
\qquad k=1,\ldots,M.
$$

Cyclicity gives

$$
\prod_{k=1}^{M}\frac{u_k+i/2}{u_k-i/2}=1,
$$

and the anomalous dimension is

$$
\gamma^{(1)}
=
\frac{\lambda}{8\pi^2}\sum_{k=1}^{M}\frac{1}{u_k^2+1/4}.
$$

The key point is conceptual: in planar $\mathcal N=4$ SYM, computing anomalous dimensions becomes a quantum many-body spectral problem.

## Spin chains and strings

The AdS interpretation is

$$
\operatorname{Tr}(X_1\cdots X_L)
\quad\longleftrightarrow\quad
\text{single closed-string state}.
$$

The scaling dimension is the string energy:

$$
\Delta\quad\longleftrightarrow\quad E_{\mathrm{string}}.
$$

The half-BPS vacuum $\operatorname{Tr}Z^L$ is dual to a pointlike string moving along a great circle of $S^5$. Magnons are string excitations. In the all-loop integrability description, the elementary magnon dispersion relation is

$$
\varepsilon(p)
=
\sqrt{1+16g^2\sin^2\frac p2},
\qquad
 g=\frac{\sqrt\lambda}{4\pi}.
$$

Equivalently,

$$
\varepsilon(p)
=
\sqrt{1+\frac{\lambda}{\pi^2}\sin^2\frac p2}.
$$

At weak coupling,

$$
\varepsilon(p)=1+\frac{\lambda}{2\pi^2}\sin^2\frac p2+O(\lambda^2),
$$

which matches the one-loop spin-chain magnon energy after subtracting the classical impurity contribution. At strong coupling, related excitations are semiclassical string solitons such as giant magnons.

## Open spin chains from Wilson-line insertions

Wilson loops and spin chains meet when one inserts many fields along a Wilson line. Schematically,

$$
W[\Phi^{I_1}(\tau_1)\Phi^{I_2}(\tau_2)\cdots\Phi^{I_L}(\tau_L)].
$$

The ordered sequence of insertions can mix under renormalization. In planar perturbation theory this mixing often resembles an open spin chain, because the Wilson line supplies boundary conditions rather than cyclic trace identification.

Thus we have two parallel spectral problems:

$$
\begin{array}{ccl}
\text{closed single traces} &\longleftrightarrow& \text{closed spin chains} \longleftrightarrow \text{closed strings},\\
\text{Wilson-line insertions} &\longleftrightarrow& \text{open spin chains} \longleftrightarrow \text{open strings}.
\end{array}
$$

This is one reason defect CFT is so useful in AdS/CFT: it exposes the open-string sector directly inside the gauge theory.

## AdS/CFT checkpoint

The three dictionaries to remember are

$$
\boxed{
W[C]
\longleftrightarrow
\text{fundamental string worldsheet }\Sigma_C\text{ with }\partial\Sigma_C=C
}
$$

$$
\boxed{
\widehat{\mathcal O}(\tau)\text{ on a Wilson line}
\longleftrightarrow
\text{open-string fluctuation on }\mathrm{AdS}_2
}
$$

$$
\boxed{
\operatorname{Tr}(X_1\cdots X_L)
\longleftrightarrow
\text{closed spin chain}
\longleftrightarrow
\text{closed string state}
}
$$

Local single-trace operators teach us about bulk fields and closed strings. Wilson loops teach us about open strings and branes. Spin chains teach us that the string spectrum is already encoded in the CFT dilatation operator.

## Common pitfalls

A Wilson loop is not just a complicated local operator. It is an extended operator. A straight Wilson line changes the problem into a defect CFT.

The scalar coupling in the Maldacena--Wilson loop is essential. Without it, the line generally preserves less supersymmetry and is not the canonical half-BPS defect.

A spin chain is not a separate microscopic theory replacing the gauge theory. It is the planar organization of the dilatation operator acting on single-trace operators.

Large $N$ and large $\lambda$ are logically different. Spin chains appear already at weak coupling in the planar limit. Classical strings require strong 't Hooft coupling.

## Exercises

### Exercise 1: Gauge covariance of an open Wilson line

Show that

$$
U[C_{x_i\to x_f}]
=
\mathcal P\exp\left(i\int_{x_i}^{x_f}A_\mu dx^\mu\right)
$$

transforms as

$$
U[C_{x_i\to x_f}]
\mapsto
 g(x_f)U[C_{x_i\to x_f}]g(x_i)^{-1}.
$$

Then explain why $\operatorname{Tr}U[C]$ is gauge invariant for a closed curve.

<details>
<summary><strong>Solution</strong></summary>

Parametrize the path by $s$. The Wilson line satisfies

$$
\frac{d}{ds}U(s,s_i)
=i\dot x^\mu(s)A_\mu(x(s))U(s,s_i),
\qquad
U(s_i,s_i)=1.
$$

Define

$$
U^g(s,s_i)=g(x(s))U(s,s_i)g(x_i)^{-1}.
$$

Using

$$
A_\mu^g=gA_\mu g^{-1}-i(\partial_\mu g)g^{-1},
$$

one verifies directly that

$$
\frac{d}{ds}U^g(s,s_i)
=i\dot x^\mu A_\mu^g(x(s))U^g(s,s_i).
$$

The initial condition is also correct. Therefore

$$
U^g[C_{x_i\to x_f}]=g(x_f)U[C_{x_i\to x_f}]g(x_i)^{-1}.
$$

If $x_f=x_i$, then

$$
\operatorname{Tr}\left(g(x_i)Ug(x_i)^{-1}\right)=\operatorname{Tr}U
$$

by cyclicity.

</details>

### Exercise 2: Defect two-point function

Use one-dimensional conformal invariance to show that the two-point function of scalar defect primaries is

$$
\langle \widehat{\mathcal O}_a(\tau_1)\widehat{\mathcal O}_b(\tau_2)\rangle_W
=
\frac{C_{ab}}{|\tau_{12}|^{\widehat\Delta_a+\widehat\Delta_b}},
$$

and that $C_{ab}$ can be nonzero only when $\widehat\Delta_a=\widehat\Delta_b$.

<details>
<summary><strong>Solution</strong></summary>

Translation invariance gives a function of $\tau_{12}$ only. Scale invariance gives

$$
f(\lambda\tau)=\lambda^{-\widehat\Delta_a-\widehat\Delta_b}f(\tau),
$$

hence

$$
f(\tau)=\frac{C_{ab}}{|\tau|^{\widehat\Delta_a+\widehat\Delta_b}}.
$$

Now impose inversion $\tau\mapsto 1/\tau$. A primary transforms as

$$
\widehat{\mathcal O}'(\tau')
=\left|\frac{d\tau'}{d\tau}\right|^{-\widehat\Delta}\widehat{\mathcal O}(\tau)
=|\tau|^{2\widehat\Delta}\widehat{\mathcal O}(\tau).
$$

Since

$$
|\tau_1'-\tau_2'|
=\left|\frac{\tau_{12}}{\tau_1\tau_2}\right|,
$$

the transformed answer agrees with the same functional form only when $\widehat\Delta_a=\widehat\Delta_b$, unless $C_{ab}=0$.

</details>

### Exercise 3: One-magnon energy

For

$$
H=\sum_{\ell=1}^{L}(1-P_{\ell,\ell+1}),
$$

show that the one-magnon plane wave

$$
|p\rangle=\sum_{n=1}^{L}e^{ipn}|n\rangle
$$

has energy

$$
E(p)=4\sin^2\frac p2.
$$

Deduce the one-loop anomalous dimension.

<details>
<summary><strong>Solution</strong></summary>

Only the two links adjacent to the impurity act nontrivially, so

$$
H|n\rangle=2|n\rangle-|n-1\rangle-|n+1\rangle.
$$

Therefore

$$
H|p\rangle
=\sum_n e^{ipn}(2|n\rangle-|n-1\rangle-|n+1\rangle).
$$

Relabeling sums gives

$$
H|p\rangle
=(2-e^{ip}-e^{-ip})|p\rangle
=4\sin^2\frac p2\,|p\rangle.
$$

Thus

$$
\gamma^{(1)}(p)
=\frac{\lambda}{8\pi^2}E(p)
=\frac{\lambda}{2\pi^2}\sin^2\frac p2.
$$

</details>

### Exercise 4: Dimension of the displacement operator

For a flat $p$-dimensional defect in a $d$-dimensional CFT, use

$$
\partial_\mu T^{\mu i}(x)
=
\delta^{(d-p)}(x_\perp)D^i(x_\parallel)
$$

to determine $\widehat\Delta_D$.

<details>
<summary><strong>Solution</strong></summary>

The stress tensor has dimension $d$, so $\partial_\mu T^{\mu i}$ has dimension $d+1$. The transverse delta function has dimension $d-p$. Therefore the defect operator must have dimension

$$
\widehat\Delta_D=(d+1)-(d-p)=p+1.
$$

For a line defect, $p=1$, so

$$
\widehat\Delta_D=2.
$$

</details>

## Further reading

For Wilson loops in $\mathcal N=4$ SYM and their string duals, start with the Maldacena--Wilson loop construction, the classical string computation of rectangular and circular loops, and the localization result for the half-BPS circle.

For defect CFT, focus on the half-BPS Wilson line, the displacement operator, the bulk-to-defect OPE, and the $\mathrm{AdS}_2$ open-string fluctuation spectrum.

For spin chains, start with the one-loop $SU(2)$ sector, then study the planar dilatation operator in larger sectors, Bethe equations, magnon dispersion, and semiclassical strings on $\mathrm{AdS}_5\times S^5$.
