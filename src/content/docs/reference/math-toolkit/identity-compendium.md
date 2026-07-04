---
title: "Identity Compendium"
description: "A convention-consistent lookup page for mathematical identities used across QFT: Fourier transforms, distributions, Gaussian integrals, spinors, Lie algebras, geometry, topology, spectral theory, asymptotics, probability, and numerical checks."
sidebar:
  label: "Identity Compendium"
  order: 997
level: Graduate
status: "Polished draft"
source: "A curated cross-volume formula sheet distilled from the Mathematical Toolkit pages, standard QFT conventions, mathematical physics references, and computational practice."
topics:
  - identity compendium
  - formula sheet
  - conventions
  - Fourier transforms
  - distributions
  - Gaussian integrals
  - spinors
  - Lie algebras
  - geometry
  - topology
  - numerical methods
canonicalTopics:
  - qft-identities
  - mathematical-toolkit-identities
  - formula-conventions
  - derivation-index
researchStatus:
  established:
    - "The identities collected here are standard mathematical infrastructure for graduate-level QFT, statistical field theory, geometry, topology, and numerical analysis."
  active:
    - "The compendium should remain a maintained lookup layer: formulas must be checked against page-level conventions, new derivation pages should be linked, and ambiguous regularized identities should retain explicit caveats."
---

## Summary

This page is the compact lookup layer for the Mathematical Toolkit volume. It collects the identities that readers repeatedly need while moving through QFT: Fourier transforms, delta functions, Gaussian integrals, Grassmann signs, gamma-matrix traces, Lie-algebra normalizations, differential-form identities, characteristic classes, heat-kernel coefficients, saddle-point formulas, probability identities, and numerical error checks.

It is **not** meant to replace the derivation pages. It is a navigation instrument: use it when you need the formula quickly, then follow the linked pages when the sign, normalization, domain, or regularization matters.

The default conventions are those fixed in [Mathematical Conventions](/math-toolkit/conventions/): mostly-minus metric, $c=\hbar=1$, and plane waves $e^{-ip\cdot x}$ unless a page says otherwise.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A map showing conventions feeding into algebra, analysis, geometry, integrals, QFT use, computation, and the identity compendium.](/figures/math-toolkit/identity-compendium-map.svg)

<figcaption>

The identity compendium is a lookup page, not a substitute for assumptions. Every useful identity has a home: conventions fix signs, derivation pages explain hypotheses, and this page gives the short form.

</figcaption>
</figure>

:::caution[Lookup formulas are not licenses to ignore hypotheses]
Many formulas below are identities only under stated assumptions: positive quadratic forms, simple zeros, compact support, trace-class operators, elliptic operators, suitable boundary conditions, or a chosen regulator. The fastest way to get a wrong QFT result is to apply a right identity in the wrong category.
:::

## Navigation map

| Need | Start here | Derivation page |
|---|---|---|
| signs, $2\pi$ factors, metric | conventions | [Mathematical Conventions](/math-toolkit/conventions/) |
| distributions and delta functions | analysis | [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/) |
| Fourier transforms | analysis | [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/) |
| Gaussian and Grassmann identities | functional integrals | [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/) and [Berezin Integration](/math-toolkit/functional-integrals-determinants/berezin-integration/) |
| functional determinants | functional integrals | [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) |
| variational derivatives | phase space | [Variational Derivatives](/math-toolkit/calculus-of-variations-and-phase-space/variational-derivatives/) |
| symplectic and Poisson formulas | phase space | [Symplectic Forms](/math-toolkit/calculus-of-variations-and-phase-space/symplectic-forms/) and [Poisson Brackets](/math-toolkit/calculus-of-variations-and-phase-space/poisson-brackets/) |
| spinors and gamma matrices | Clifford | [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/) |
| bundles, connections, curvature | geometry | [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) |
| characteristic classes | topology | [Characteristic Classes](/math-toolkit/topology-cohomology-characteristic-classes/characteristic-classes/) |
| heat kernels and zeta functions | determinants | [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) and [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/) |
| asymptotics | resurgence | [Asymptotic Series](/math-toolkit/asymptotics-regularization-resurgence/asymptotic-series/) |
| random variables and cumulants | probability | [Probability Measures](/math-toolkit/probability-statistics-random-matrices/probability-measures/) and [Cumulants and Connected Correlators](/math-toolkit/probability-statistics-random-matrices/cumulants-and-connected-correlators/) |
| numerical checks | numerical mathematics | [Error Analysis](/math-toolkit/numerical-mathematics/error-analysis/) |

## Core conventions

The default flat metric is

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
\qquad
p\cdot x=p_\mu x^\mu=p^0x^0-\mathbf p\cdot\mathbf x.
$$

Thus

$$
p^2=(p^0)^2-|\mathbf p|^2,
\qquad
\Box=\partial_\mu\partial^\mu=\partial_t^2-\nabla^2.
$$

The Klein–Gordon operator in Lorentzian signature is

$$
(\Box+m^2)\phi=0,
$$

and a positive-frequency plane wave is written

$$
\phi(x)\sim e^{-ip\cdot x},
\qquad
p^0=E_{\mathbf p}=\sqrt{|\mathbf p|^2+m^2}.
$$

The Feynman scalar propagator convention is

$$
\Delta_F(x-y)=\int\frac{d^dp}{(2\pi)^d}\,
\frac{i\,e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

In Euclidean signature, with a positive Laplacian convention written explicitly on each page,

$$
G_E(x-y)=\int\frac{d^dp}{(2\pi)^d}\,
\frac{e^{ip\cdot(x-y)}}{p^2+m^2}.
$$

## Fourier transforms

For functions or tempered distributions on $\mathbb R^d$, the site convention is

$$
\widetilde f(p)=\int d^dx\,e^{ip\cdot x}f(x),
$$

and

$$
f(x)=\int\frac{d^dp}{(2\pi)^d}\,e^{-ip\cdot x}\widetilde f(p).
$$

The delta-function identities are

$$
\int\frac{d^dp}{(2\pi)^d}\,e^{-ip\cdot(x-y)}=\delta^{(d)}(x-y),
$$

and

$$
\int d^dx\,e^{i(p-q)\cdot x}=(2\pi)^d\delta^{(d)}(p-q).
$$

The derivative dictionary is

$$
\partial_\mu f(x)
\longleftrightarrow
-ip_\mu \widetilde f(p),
$$

and

$$
x^\mu f(x)
\longleftrightarrow
-i\frac{\partial}{\partial p_\mu}\widetilde f(p).
$$

Convolution is defined by

$$
(f*g)(x)=\int d^dy\,f(x-y)g(y),
$$

so that

$$
\widetilde{f*g}(p)=\widetilde f(p)\widetilde g(p).
$$

The inverse relation is

$$
\widetilde{fg}(p)
=\int\frac{d^dq}{(2\pi)^d}\,\widetilde f(q)\widetilde g(p-q).
$$

## Delta functions and distributions

The delta distribution is defined by

$$
\int d^dx\,\delta^{(d)}(x-y)f(x)=f(y).
$$

The basic algebraic identity is

$$
f(x)\delta^{(d)}(x-y)=f(y)\delta^{(d)}(x-y).
$$

For an invertible linear map $A:\mathbb R^d\to\mathbb R^d$,

$$
\delta^{(d)}(Ax)=\frac{1}{|\det A|}\delta^{(d)}(x).
$$

For a smooth one-dimensional function $g$ with simple zeros $x_i$,

$$
\delta(g(x))=\sum_i\frac{\delta(x-x_i)}{|g'(x_i)|}.
$$

For a smooth map $F:\mathbb R^n\to\mathbb R^k$ with regular zero locus $F^{-1}(0)$,

$$
\int d^nx\,\delta^{(k)}(F(x))h(x)
=
\int_{F^{-1}(0)}\frac{d\Sigma(x)}{\sqrt{\det(DF\,DF^T)}}h(x),
$$

where the denominator is the induced Jacobian for the chosen Euclidean measure.

Distributional derivatives are defined by integration by parts:

$$
\langle \partial_\mu T,f\rangle=-\langle T,\partial_\mu f\rangle.
$$

In particular,

$$
\int d^dx\,\partial_\mu\delta^{(d)}(x-y)f(x)
=-\partial_\mu f(y).
$$

The principal value distribution is

$$
\left\langle \operatorname{PV}\frac1x,f\right\rangle
=
\lim_{\epsilon\to0^+}\int_{|x|>\epsilon}dx\,\frac{f(x)}{x}.
$$

The most used boundary-value identity is

$$
\frac{1}{x\pm i0}=\operatorname{PV}\frac1x\mp i\pi\delta(x).
$$

For a denominator with simple zero,

$$
\frac{1}{p^2-m^2+i0}
=
\operatorname{PV}\frac{1}{p^2-m^2}
-i\pi\delta(p^2-m^2).
$$

The on-shell delta identity is

$$
\delta(p^2-m^2)
=\frac{1}{2E_{\mathbf p}}\Bigl[\delta(p^0-E_{\mathbf p})+\delta(p^0+E_{\mathbf p})\Bigr].
$$

The positive-energy on-shell measure is

$$
\int\frac{d^dp}{(2\pi)^d}\,2\pi\theta(p^0)\delta(p^2-m^2)F(p)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}\frac{1}{2E_{\mathbf p}}F(E_{\mathbf p},\mathbf p).
$$

## Linear algebra and tensors

For finite matrices,

$$
\delta\det A=(\det A)\operatorname{Tr}(A^{-1}\delta A),
$$

and

$$
\delta\log\det A=\operatorname{Tr}(A^{-1}\delta A).
$$

For invertible operators where the trace is meaningful,

$$
\log\det A=\operatorname{Tr}\log A.
$$

The matrix determinant lemma is

$$
\det(A+uv^T)=\det A\,(1+v^TA^{-1}u).
$$

The Woodbury identity is

$$
(A+UCV)^{-1}
=A^{-1}-A^{-1}U(C^{-1}+VA^{-1}U)^{-1}VA^{-1}.
$$

For a metric $g_{ij}$,

$$
\delta\sqrt{|g|}=\frac12\sqrt{|g|}\,g^{ij}\delta g_{ij}
=-\frac12\sqrt{|g|}\,g_{ij}\delta g^{ij}.
$$

The Levi-Civita contraction in $n$ dimensions is

$$
\epsilon_{i_1\cdots i_n}\epsilon^{j_1\cdots j_n}
=\operatorname{sgn}(g)\,n!\,\delta_{[i_1}^{j_1}\cdots\delta_{i_n]}^{j_n},
$$

where the sign depends on metric and epsilon conventions. In Euclidean components this reduces to the determinant of Kronecker deltas.

Symmetrization and antisymmetrization use unit weight:

$$
T_{(ij)}=\frac12(T_{ij}+T_{ji}),
\qquad
T_{[ij]}=\frac12(T_{ij}-T_{ji}).
$$

More generally,

$$
T_{[i_1\cdots i_p]}
=\frac1{p!}\sum_{\sigma\in S_p}\operatorname{sgn}(\sigma)
T_{i_{\sigma(1)}\cdots i_{\sigma(p)}}.
$$

## Gaussian integrals

For a real symmetric positive-definite $n\times n$ matrix $A$,

$$
\int_{\mathbb R^n}d^nx\,
\exp\!\left(-\frac12x^TAx+J^Tx\right)
=(2\pi)^{n/2}(\det A)^{-1/2}
\exp\!\left(\frac12J^TA^{-1}J\right).
$$

With normalized expectation,

$$
\langle x_i x_j\rangle=(A^{-1})_{ij}.
$$

Wick’s theorem for a centered Gaussian is

$$
\langle x_{i_1}\cdots x_{i_{2n}}\rangle
=\sum_{\text{pairings}}\prod_{(ab)}(A^{-1})_{i_ai_b},
$$

and odd moments vanish.

For complex variables with positive Hermitian $A$,

$$
\int \prod_i d\overline z_i\,dz_i\,
\exp(-\overline z A z+\overline\eta z+\overline z\eta)
\propto
(\det A)^{-1}\exp(\overline\eta A^{-1}\eta),
$$

where the proportionality depends on the chosen complex measure normalization.

For a quadratic fluctuation expansion around a stationary point $x_*$,

$$
S(x)=S(x_*)+\frac12\xi^iH_{ij}\xi^j+\cdots,
$$

Laplace’s method gives

$$
\int d^nx\,e^{-S(x)/\hbar}
\sim
(2\pi\hbar)^{n/2}e^{-S(x_*)/\hbar}(\det H)^{-1/2}
$$

when $H$ is positive definite.

For oscillatory stationary phase,

$$
\int d^nx\,a(x)e^{i\lambda S(x)}
\sim
\left(\frac{2\pi}{\lambda}\right)^{n/2}
\frac{e^{i\lambda S(x_*)}e^{i\pi\operatorname{sgn}(H)/4}}{|\det H|^{1/2}}a(x_*),
$$

for a nondegenerate critical point.

## Grassmann and Pfaffian identities

Grassmann variables anticommute:

$$
\theta_i\theta_j=-\theta_j\theta_i,
\qquad
\theta_i^2=0.
$$

Berezin integration is differentiation:

$$
\int d\theta\,1=0,
\qquad
\int d\theta\,\theta=1.
$$

For $n$ pairs of independent Grassmann variables,

$$
\int \prod_i d\overline\psi_i\,d\psi_i\,
\exp(-\overline\psi A\psi)=\det A,
$$

up to the ordering convention for the measure. The companion source identity is

$$
\int D\overline\psi D\psi\,
\exp(-\overline\psi A\psi+\overline\eta\psi+\overline\psi\eta)
=\det A\,\exp(\overline\eta A^{-1}\eta).
$$

For real Grassmann variables and antisymmetric $A$,

$$
\int d\theta_{2n}\cdots d\theta_1\,
\exp\!\left(\frac12\theta_iA_{ij}\theta_j\right)
=\operatorname{Pf}(A).
$$

The Pfaffian satisfies

$$
\operatorname{Pf}(A)^2=\det A.
$$

For invertible antisymmetric $A$,

$$
\delta\log\operatorname{Pf}(A)=\frac12\operatorname{Tr}(A^{-1}\delta A).
$$

Grassmann Wick contractions use the inverse quadratic form with signs determined by moving variables into adjacent pairs. When in doubt, derive the sign from the generating functional rather than from memory.

## Functional derivatives

For a functional $F[\phi]$,

$$
\delta F=\int d^dx\,\frac{\delta F}{\delta\phi(x)}\delta\phi(x).
$$

The identity kernel is

$$
\frac{\delta\phi(x)}{\delta\phi(y)}=\delta^{(d)}(x-y).
$$

For a local functional

$$
F[\phi]=\int d^dx\,\mathcal F(\phi,\partial_\mu\phi),
$$

the Euler–Lagrange derivative is

$$
\frac{\delta F}{\delta\phi}
=\frac{\partial\mathcal F}{\partial\phi}
-\partial_\mu\frac{\partial\mathcal F}{\partial(\partial_\mu\phi)},
$$

up to boundary terms.

For higher derivatives,

$$
\frac{\delta F}{\delta\phi}
=\sum_{|I|\ge0}(-\partial)_I
\frac{\partial\mathcal F}{\partial(\partial_I\phi)},
$$

where $I$ is a multi-index.

For a generating functional

$$
Z[J]=\int D\phi\,e^{-S[\phi]+\int J\phi},
$$

correlators are generated by

$$
\langle \phi(x_1)\cdots\phi(x_n)\rangle
=\frac1{Z[0]}\left.\frac{\delta^n Z[J]}{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}.
$$

Connected correlators come from

$$
W[J]=\log Z[J].
$$

## Variational calculus and phase space

For an action

$$
S[\phi]=\int_M d^dx\,\mathcal L(\phi,\partial\phi),
$$

the first variation has the structure

$$
\delta S=\int_M d^dx\,E(\phi)\delta\phi+\int_{\partial M}\Theta(\phi,\delta\phi),
$$

where $E(\phi)=0$ are the equations of motion and $\Theta$ is the boundary or presymplectic potential term.

For mechanics,

$$
p_i=\frac{\partial L}{\partial\dot q^i},
\qquad
H(q,p)=p_i\dot q^i-L(q,\dot q),
$$

assuming the Legendre map is invertible.

The canonical one-form and symplectic form are

$$
\theta=p_i\,dq^i,
\qquad
\omega=dq^i\wedge dp_i.
$$

The Hamiltonian vector field $X_H$ is defined by

$$
iota_{X_H}\omega=dH,
$$

with the sign convention fixed on the symplectic page. In canonical coordinates this gives

$$
\dot q^i=\frac{\partial H}{\partial p_i},
\qquad
\dot p_i=-\frac{\partial H}{\partial q^i}.
$$

The canonical Poisson bracket is

$$
\{F,G\}
=\frac{\partial F}{\partial q^i}\frac{\partial G}{\partial p_i}
-\frac{\partial F}{\partial p_i}\frac{\partial G}{\partial q^i}.
$$

In field theory,

$$
\{\phi^a(t,\mathbf x),\pi_b(t,\mathbf y)\}
=\delta^a_b\delta^{(d-1)}(\mathbf x-\mathbf y).
$$

Canonical quantization promotes this to

$$
[\widehat\phi^a(t,\mathbf x),\widehat\pi_b(t,\mathbf y)]
=i\delta^a_b\delta^{(d-1)}(\mathbf x-\mathbf y),
$$

for bosonic fields.

## Lie groups and Lie algebras

For a Lie group element near the identity,

$$
g=e^{\theta^aT_a}.
$$

The Lie algebra is

$$
[T_a,T_b]=f_{ab}^{\phantom{ab}c}T_c.
$$

In a representation $R$ of a compact simple Lie algebra, a common normalization is

$$
\operatorname{tr}_R(T^aT^b)=T(R)\delta^{ab}.
$$

The quadratic Casimir is

$$
T^a_RT^a_R=C_2(R)\mathbf 1_R.
$$

The adjoint Casimir is

$$
f^{acd}f^{bcd}=C_2(G)\delta^{ab}.
$$

The dimensions obey

$$
C_2(R)\dim R=T(R)\dim G.
$$

For $SU(N)$ in the fundamental convention

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

one has

$$
T(\square)=\frac12,
\qquad
C_2(\square)=\frac{N^2-1}{2N},
\qquad
C_2(G)=N.
$$

The Baker–Campbell–Hausdorff formula begins

$$
\log(e^Xe^Y)=X+Y+\frac12[X,Y]
+\frac1{12}[X,[X,Y]]+\frac1{12}[Y,[Y,X]]+\cdots.
$$

For infinitesimal transformations,

$$
\delta\phi^i=\epsilon^a(T_a\phi)^i.
$$

A continuous symmetry of the action gives a conserved current

$$
\partial_\mu j^\mu_a=0
$$

on shell, up to anomalies or explicit breaking.

## SU(2) and angular momentum

The $SU(2)$ generators obey

$$
[J_i,J_j]=i\epsilon_{ijk}J_k.
$$

Define

$$
J_\pm=J_1\pm iJ_2.
$$

Then

$$
[J_3,J_\pm]=\pm J_\pm,
\qquad
[J_+,J_-]=2J_3.
$$

The spin-$j$ representation has basis $|j,m\rangle$ with

$$
J^2|j,m\rangle=j(j+1)|j,m\rangle,
\qquad
J_3|j,m\rangle=m|j,m\rangle,
$$

and

$$
J_\pm|j,m\rangle
=\sqrt{(j\mp m)(j\pm m+1)}\,|j,m\pm1\rangle.
$$

The tensor product decomposes as

$$
j_1\otimes j_2
=\bigoplus_{j=|j_1-j_2|}^{j_1+j_2}j.
$$

## Lorentz and Poincaré identities

The Lorentz algebra generators $M_{\mu\nu}=-M_{\nu\mu}$ obey

$$
[M_{\mu\nu},M_{\rho\sigma}]
=i(\eta_{\nu\rho}M_{\mu\sigma}-\eta_{\mu\rho}M_{\nu\sigma}
-\eta_{\nu\sigma}M_{\mu\rho}+\eta_{\mu\sigma}M_{\nu\rho}).
$$

The Poincaré algebra includes translations $P_\mu$ with

$$
[P_\mu,P_\nu]=0,
$$

and

$$
[M_{\mu\nu},P_\rho]
=i(\eta_{\nu\rho}P_\mu-\eta_{\mu\rho}P_\nu).
$$

The two standard Casimirs are

$$
P^2=P_\mu P^\mu,
$$

and

$$
W^2=W_\mu W^\mu,
\qquad
W^\mu=\frac12\epsilon^{\mu\nu\rho\sigma}P_\nu M_{\rho\sigma}.
$$

Massive one-particle representations have

$$
P^2=m^2,
\qquad
W^2=-m^2s(s+1).
$$

Massless helicity representations have

$$
P^2=0,
\qquad
W^\mu=hP^\mu.
$$

## Clifford algebras and gamma matrices

The gamma matrices satisfy

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}\mathbf1.
$$

Dirac slash notation is written without the unsupported slash command:

$$
p\!\!\!/\equiv\gamma^\mu p_\mu.
$$

Then

$$
(p\!\!\!/)^2=p^2\mathbf1.
$$

The antisymmetrized gamma matrices are

$$
\gamma^{\mu\nu}=\frac12[\gamma^\mu,\gamma^\nu].
$$

In four dimensions,

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3,
$$

with mostly-minus signature and the stated gamma convention. It obeys

$$
(\gamma^5)^2=1,
\qquad
\{\gamma^5,\gamma^\mu\}=0.
$$

The chiral projectors are

$$
P_L=\frac12(1-\gamma^5),
\qquad
P_R=\frac12(1+\gamma^5).
$$

Trace identities in four dimensions include

$$
\operatorname{tr}(\gamma^\mu\gamma^\nu)=4\eta^{\mu\nu},
$$

$$
\operatorname{tr}(\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma)
=4(\eta^{\mu\nu}\eta^{\rho\sigma}-\eta^{\mu\rho}\eta^{\nu\sigma}+\eta^{\mu\sigma}\eta^{\nu\rho}),
$$

and

$$
\operatorname{tr}(\gamma^5\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma)
=-4i\epsilon^{\mu\nu\rho\sigma},
$$

provided $\epsilon^{0123}=+1$ with the site convention. If your gamma-matrix or epsilon convention differs, this is one of the first signs that changes.

The Dirac adjoint is

$$
\overline\psi=\psi^\dagger\gamma^0.
$$

The free Dirac equation is

$$
(i\gamma^\mu\partial_\mu-m)\psi=0.
$$

The momentum-space spin sums are

$$
\sum_s u_s(p)\overline u_s(p)=p\!\!\!/+m,
$$

and

$$
\sum_s v_s(p)\overline v_s(p)=p\!\!\!/-m,
$$

with spinor normalizations fixed on the spinor pages.

## Spinor-helicity identities

For a null momentum in four dimensions,

$$
p_{\alpha\dot\alpha}=p_\mu\sigma^\mu_{\alpha\dot\alpha}
=\lambda_\alpha\widetilde\lambda_{\dot\alpha}.
$$

Angle and square brackets are

$$
\langle ij\rangle=\epsilon^{\alpha\beta}\lambda_{i\alpha}\lambda_{j\beta},
\qquad
[ij]=\epsilon^{\dot\alpha\dot\beta}\widetilde\lambda_{i\dot\alpha}\widetilde\lambda_{j\dot\beta}.
$$

They are antisymmetric:

$$
\langle ij\rangle=-\langle ji\rangle,
\qquad
[ij]=-[ji].
$$

The massless invariant is

$$
2p_i\cdot p_j=\langle ij\rangle[ji],
$$

with sign sensitive to the sigma-matrix convention.

The Schouten identity is

$$
\langle ij\rangle\langle k\ell\rangle
+\langle ik\rangle\langle \ell j\rangle
+\langle i\ell\rangle\langle jk\rangle=0,
$$

and similarly for square brackets.

Little-group scaling is

$$
\lambda_i\to t_i\lambda_i,
\qquad
\widetilde\lambda_i\to t_i^{-1}\widetilde\lambda_i.
$$

An amplitude with external helicity $h_i$ scales as

$$
\mathcal A_n\to t_i^{-2h_i}\mathcal A_n.
$$

## Differential forms

For a $p$-form

$$
\alpha=\frac1{p!}\alpha_{\mu_1\cdots\mu_p}
 dx^{\mu_1}\wedge\cdots\wedge dx^{\mu_p},
$$

the exterior derivative is

$$
d\alpha=\frac1{p!}\partial_\nu\alpha_{\mu_1\cdots\mu_p}
 dx^\nu\wedge dx^{\mu_1}\wedge\cdots\wedge dx^{\mu_p}.
$$

It satisfies

$$
d^2=0,
$$

and the graded Leibniz rule

$$
d(\alpha\wedge\beta)=d\alpha\wedge\beta+(-1)^p\alpha\wedge d\beta.
$$

The interior product with a vector field $X$ satisfies

$$
\iota_X(\alpha\wedge\beta)
=(\iota_X\alpha)\wedge\beta+(-1)^p\alpha\wedge(\iota_X\beta).
$$

The Lie derivative obeys Cartan’s formula

$$
\mathcal L_X=d\iota_X+\iota_Xd.
$$

Stokes’ theorem is

$$
\int_M d\alpha=\int_{\partial M}\alpha,
$$

with the boundary orientation convention fixed by the outward-normal-first rule or its stated equivalent.

The Hodge star is convention-dependent. In pseudo-Riemannian signature,

$$
**\alpha=(-1)^{p(n-p)+s}\alpha,
$$

where $s$ is the number of minus signs in the metric. In Euclidean signature, $s=0$.

## Connections and curvature

For a gauge connection one-form

$$
A=A_\mu dx^\mu,
$$

with Lie-algebra-valued $A$, the curvature is

$$
F=dA+A\wedge A.
$$

In components,

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu+[A_\mu,A_\nu].
$$

The covariant exterior derivative is

$$
D\omega=d\omega+[A,\omega],
$$

with the graded bracket understood. The Bianchi identity is

$$
DF=0.
$$

Under a gauge transformation $g$,

$$
A\mapsto A^g=gAg^{-1}-dg\,g^{-1},
$$

or equivalently $A\mapsto gAg^{-1}+g\,d g^{-1}$ depending on whether fields transform from the left or right. Fix the matter-field convention before using this formula.

The curvature transforms covariantly:

$$
F\mapsto gFg^{-1}.
$$

The Wilson line along a path $\gamma$ is

$$
U_\gamma=P\exp\!\left(-\int_\gamma A\right),
$$

with the sign determined by the covariant derivative convention. For $D=d+A$, the parallel transport equation is often $D_s\psi=0$, giving the minus sign above.

## Riemannian and Lorentzian geometry

The Levi-Civita connection is torsion-free and metric-compatible:

$$
\Gamma^\rho_{\mu\nu}
=\frac12g^{\rho\sigma}(\partial_\mu g_{\nu\sigma}+\partial_\nu g_{\mu\sigma}-\partial_\sigma g_{\mu\nu}).
$$

The Riemann tensor convention must be stated. With

$$
[\nabla_\mu,\nabla_\nu]V^\rho=R^\rho_{\ \sigma\mu\nu}V^\sigma,
$$

one has

$$
R^\rho_{\ \sigma\mu\nu}
=\partial_\mu\Gamma^\rho_{\nu\sigma}-\partial_\nu\Gamma^\rho_{\mu\sigma}
+\Gamma^\rho_{\mu\lambda}\Gamma^\lambda_{\nu\sigma}
-\Gamma^\rho_{\nu\lambda}\Gamma^\lambda_{\mu\sigma}.
$$

The Ricci tensor and scalar are

$$
R_{\mu\nu}=R^\rho_{\ \mu\rho\nu},
\qquad
R=g^{\mu\nu}R_{\mu\nu}.
$$

The variation of the inverse metric is

$$
\delta g^{\mu\nu}=-g^{\mu\rho}g^{\nu\sigma}\delta g_{\rho\sigma}.
$$

The variation of the Christoffel symbol is

$$
\delta\Gamma^\rho_{\mu\nu}
=\frac12g^{\rho\sigma}(\nabla_\mu\delta g_{\nu\sigma}+\nabla_\nu\delta g_{\mu\sigma}-\nabla_\sigma\delta g_{\mu\nu}).
$$

The Palatini identity is

$$
\delta R_{\mu\nu}
=\nabla_\rho\delta\Gamma^\rho_{\nu\mu}-\nabla_\nu\delta\Gamma^\rho_{\rho\mu}.
$$

## Topology and characteristic classes

For a complex vector bundle with curvature $F$, the total Chern class is formally

$$
c(E)=\det\!\left(1+\frac{iF}{2\pi}\right).
$$

Thus

$$
c_1(E)=\frac{i}{2\pi}\operatorname{tr}F,
$$

and

$$
c_2(E)=\frac12\left[\left(\frac{i}{2\pi}\operatorname{tr}F\right)^2
-\operatorname{tr}\left(\frac{iF}{2\pi}\wedge\frac{iF}{2\pi}\right)\right].
$$

For a real oriented bundle, Pontryagin classes are related to the complexified curvature by

$$
p(E)=\det\!\left(1+\frac{F}{2\pi}\right)
$$

in the formal-root convention, with signs depending on whether $F$ is taken anti-Hermitian or real skew-adjoint. A common first Pontryagin form is

$$
p_1(E)=-\frac{1}{8\pi^2}\operatorname{tr}(F\wedge F).
$$

The Chern character is

$$
\operatorname{ch}(E)=\operatorname{tr}\exp\!\left(\frac{iF}{2\pi}\right).
$$

The Â-genus begins

$$
\widehat A(TM)=1-\frac{p_1(TM)}{24}+\frac{7p_1(TM)^2-4p_2(TM)}{5760}+\cdots.
$$

The Hirzebruch $L$-genus begins

$$
L(TM)=1+\frac{p_1(TM)}{3}+\frac{7p_2(TM)-p_1(TM)^2}{45}+\cdots.
$$

For a spin Dirac operator twisted by $E$,

$$
\operatorname{index}(D_E)=\int_M\widehat A(TM)\operatorname{ch}(E).
$$

Stiefel–Whitney classes obey the first obstruction rules:

$$
w_1(E)=0
\quad\Longleftrightarrow\quad
E\text{ is orientable},
$$

and

$$
w_2(TM)=0
\quad\Longleftrightarrow\quad
M\text{ admits a spin structure}.
$$

For winding number of a map $g:S^1\to U(1)$,

$$
\operatorname{wind}(g)=\frac{1}{2\pi i}\int_{S^1}g^{-1}dg\in\mathbb Z.
$$

For a smooth map $f:M\to N$ between compact oriented manifolds of the same dimension,

$$
\int_M f^*\omega=(\deg f)\int_N\omega.
$$

## Functional determinants and heat kernels

For a positive self-adjoint operator $L$ with discrete nonzero spectrum $\{\lambda_n\}$,

$$
\zeta_L(s)=\sum_n\lambda_n^{-s}.
$$

The zeta-regularized determinant is

$$
\log\det_\zeta L=-\zeta_L'(0).
$$

The heat kernel trace is

$$
K(t)=\operatorname{Tr}(e^{-tL})=\sum_ne^{-t\lambda_n}.
$$

The Mellin relation is

$$
\zeta_L(s)=\frac1{\Gamma(s)}\int_0^\infty dt\,t^{s-1}K(t),
$$

where analytic continuation is understood.

For a Laplace-type operator on a compact $d$-dimensional manifold,

$$
\operatorname{Tr}(e^{-tL})
\sim
\frac{1}{(4\pi t)^{d/2}}\sum_{n\ge0}t^n\int_M d^dx\sqrt g\,a_{2n}(x),
\qquad t\to0^+.
$$

For a scalar Laplace-type operator

$$
L=-(\nabla^2+E),
$$

a common convention gives

$$
a_0=\operatorname{tr}\mathbf1,
$$

and

$$
a_2=\operatorname{tr}\left(E+\frac16R\mathbf1\right).
$$

Boundary conditions add half-integer heat-kernel coefficients and must be stated separately.

The proper-time representation is

$$
\log\det L=-\int_0^\infty\frac{dt}{t}\operatorname{Tr}(e^{-tL})
$$

up to regularization and subtraction.

## Complex analysis

Cauchy’s integral formula is

$$
f(z_0)=\frac{1}{2\pi i}\oint_C\frac{f(z)}{z-z_0}\,dz.
$$

The residue theorem is

$$
\oint_C f(z)\,dz=2\pi i\sum_{z_i\in C}\operatorname{Res}_{z=z_i}f(z).
$$

For a simple pole,

$$
\operatorname{Res}_{z=z_0}\frac{g(z)}{h(z)}=\frac{g(z_0)}{h'(z_0)}
$$

when $h(z_0)=0$ and $h'(z_0)\ne0$.

The argument principle is

$$
\frac1{2\pi i}\oint_C\frac{f'(z)}{f(z)}dz=N_Z-N_P,
$$

counting zeros and poles inside $C$ with multiplicity.

A once-subtracted dispersion relation has the schematic form

$$
F(s)=F(s_0)+\frac{s-s_0}{\pi}\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Im}F(s'+i0)}{(s'-s_0)(s'-s-i0)},
$$

under the appropriate analyticity and growth assumptions.

For a branch cut on the real axis, the discontinuity is

$$
\operatorname{Disc}F(x)=F(x+i0)-F(x-i0).
$$

If $F$ is real analytic across the cut except for the discontinuity, then

$$
\operatorname{Disc}F(x)=2i\operatorname{Im}F(x+i0).
$$

## Special functions

The gamma function is

$$
\Gamma(z)=\int_0^\infty dt\,t^{z-1}e^{-t},
\qquad
\operatorname{Re}z>0.
$$

It satisfies

$$
\Gamma(z+1)=z\Gamma(z),
\qquad
\Gamma(n+1)=n!.
$$

The beta function is

$$
B(x,y)=\int_0^1dt\,t^{x-1}(1-t)^{y-1}
=\frac{\Gamma(x)\Gamma(y)}{\Gamma(x+y)}.
$$

The reflection formula is

$$
\Gamma(z)\Gamma(1-z)=\frac{\pi}{\sin\pi z}.
$$

The Bessel equation is

$$
z^2y''+zy'+(z^2-\nu^2)y=0.
$$

The leading small-$z$ behavior is

$$
J_\nu(z)\sim\frac1{\Gamma(\nu+1)}\left(\frac z2\right)^\nu.
$$

The hypergeometric equation is

$$
z(1-z)y''+[c-(a+b+1)z]y'-aby=0.
$$

The hypergeometric series is

$$
{}_2F_1(a,b;c;z)=\sum_{n=0}^\infty\frac{(a)_n(b)_n}{(c)_n}\frac{z^n}{n!}.
$$

The polylogarithm is

$$
\operatorname{Li}_s(z)=\sum_{n=1}^\infty\frac{z^n}{n^s},
\qquad |z|<1,
$$

with analytic continuation elsewhere. It obeys

$$
z\frac{d}{dz}\operatorname{Li}_s(z)=\operatorname{Li}_{s-1}(z).
$$

The Eisenstein series for even $k\ge4$ is

$$
E_k(\tau)=\frac12\sum_{(m,n)\ne(0,0)}\frac{1}{(m\tau+n)^k},
$$

up to normalization. Its modular weight is $k$:

$$
E_k\!\left(\frac{a\tau+b}{c\tau+d}\right)=(c\tau+d)^kE_k(\tau)
$$

for modular transformations by matrices in $SL(2,\mathbb Z)$, modulo the chosen normalization and exceptions such as $E_2$ being quasimodular.

## Asymptotics and regularization

An asymptotic expansion

$$
f(g)\sim\sum_{n=0}^\infty a_ng^n,
\qquad g\to0,
$$

means that for every fixed $N$,

$$
f(g)-\sum_{n=0}^{N-1}a_ng^n=o(g^{N-1}).
$$

If $a_n\sim C A^{-n}\Gamma(n+b)$, the optimal truncation order is typically

$$
N_*\sim \frac{|A|}{|g|}.
$$

The Borel transform of

$$
f(g)\sim\sum_{n=0}^\infty a_ng^{n+1}
$$

is

$$
\mathcal B f(t)=\sum_{n=0}^\infty\frac{a_n}{n!}t^n.
$$

The Borel–Laplace reconstruction is

$$
\mathcal S f(g)=\int_0^\infty dt\,e^{-t/g}\mathcal B f(t),
$$

when the contour is nonsingular and convergence holds.

Dimensional regularization repeatedly uses

$$
\int\frac{d^dk}{(2\pi)^d}\frac{1}{(k^2+\Delta)^\alpha}
=\frac1{(4\pi)^{d/2}}\frac{\Gamma(\alpha-d/2)}{\Gamma(\alpha)}\Delta^{d/2-\alpha},
$$

in Euclidean signature. The Lorentzian version carries $i$ factors and $i\epsilon$ prescriptions.

Feynman parameters satisfy

$$
\frac{1}{A^\alpha B^\beta}
=\frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)}
\int_0^1dx\,\frac{x^{\alpha-1}(1-x)^{\beta-1}}{[xA+(1-x)B]^{\alpha+\beta}}.
$$

More generally,

$$
\prod_{i=1}^n\frac1{A_i^{\alpha_i}}
=\frac{\Gamma(\sum_i\alpha_i)}{\prod_i\Gamma(\alpha_i)}
\int_0^1\prod_i dx_i\,\delta\!\left(1-\sum_i x_i\right)
\frac{\prod_i x_i^{\alpha_i-1}}{(\sum_i x_iA_i)^{\sum_i\alpha_i}}.
$$

## Probability and statistics

For a probability space $(\Omega,\mathcal F,\mathbb P)$ and random variable $X$, expectation is

$$
\mathbb E[f(X)]=\int_\Omega f(X(\omega))\,d\mathbb P(\omega).
$$

The law of $X$ is the pushforward measure

$$
\mu_X=X_*\mathbb P.
$$

Moments are generated by

$$
M(J)=\mathbb E[e^{JX}],
$$

and cumulants by

$$
K(J)=\log M(J).
$$

For random variables $X,Y$,

$$
\operatorname{Cov}(X,Y)=\mathbb E[XY]-\mathbb E[X]\mathbb E[Y].
$$

In QFT language this is the connected two-point function.

For a normalized Euclidean path-integral measure,

$$
\langle\mathcal O\rangle=\frac1Z\int D\phi\,\mathcal O[\phi]e^{-S_E[\phi]}.
$$

Large deviations are written schematically as

$$
\mathbb P(X_N\approx x)\asymp e^{-NI(x)}.
$$

The rate function $I(x)$ plays the role of an effective action for rare fluctuations.

For a Markov kernel,

$$
p_{n+1}(y)=\int dx\,K(y|x)p_n(x),
$$

with normalization

$$
\int dy\,K(y|x)=1.
$$

For a random Hermitian matrix ensemble,

$$
d\mathbb P(H)\propto e^{-N\operatorname{Tr}V(H)}dH.
$$

After diagonalization, the eigenvalue measure contains

$$
\prod_{i<j}|\lambda_i-\lambda_j|^\beta,
$$

with $\beta=1,2,4$ for the classical orthogonal, unitary, and symplectic ensembles.

## Numerical mathematics

For a centered finite difference,

$$
f'(x)=\frac{f(x+h)-f(x-h)}{2h}+O(h^2).
$$

The centered second derivative is

$$
f''(x)=\frac{f(x+h)-2f(x)+f(x-h)}{h^2}+O(h^2).
$$

The discrete Fourier symbol of the one-dimensional lattice Laplacian is

$$
\widehat{(-\Delta_h)}(k)=\frac{4}{h^2}\sin^2\!\left(\frac{kh}{2}\right).
$$

Thus

$$
\frac{4}{h^2}\sin^2\!\left(\frac{kh}{2}\right)=k^2+O(h^2k^4)
$$

for small $kh$.

For Monte Carlo samples $O_1,\ldots,O_N$ with integrated autocorrelation time $\tau_{\rm int}$,

$$
\operatorname{Var}(\overline O)\approx\frac{2\tau_{\rm int}}{N}\operatorname{Var}(O).
$$

For a method of order $p$,

$$
E(h)=Ch^p+o(h^p).
$$

Richardson extrapolation uses

$$
Q_0\approx\frac{2^pQ(h/2)-Q(h)}{2^p-1}.
$$

The condition number of a linear solve is

$$
\kappa(A)=\|A\|\,\|A^{-1}\|.
$$

A residual $r=b-Ax$ bounds the error by

$$
\|x-x_*\|\le \|A^{-1}\|\,\|r\|,
$$

assuming $Ax_*=b$ and the chosen norm.

## Common mistakes this page cannot save you from

### Missing the measure

The expression $\delta(g(x))$ is meaningless until one knows the measure in which it is inserted. The same delta distribution produces different Jacobians under $dx$, $d^dx$, an invariant phase-space measure, or a functional measure.

### Using Euclidean formulas in Lorentzian signature

Gaussian integrals, heat kernels, and positive operators live most naturally in Euclidean signature. Lorentzian identities need $i\epsilon$ prescriptions, boundary conditions, and oscillatory-contour choices.

### Treating determinants as finite-dimensional too long

The identity $\log\det A=\operatorname{Tr}\log A$ is finite-dimensional algebra. For differential operators it needs a regulator and a choice of domain, boundary conditions, and zero-mode treatment.

### Dropping boundary terms by reflex

Boundary terms vanish only under boundary conditions, compact support, or cancellation by added boundary functionals. In gauge theory, gravity, and phase space, the boundary term is often the physics.

### Forgetting convention dependence

The signs of $\gamma^5$ traces, curvature tensors, Hodge stars, Chern–Simons forms, and Lorentzian propagators are convention-sensitive. The formula is not wrong just because a book uses the opposite sign; the unannounced translation is wrong.

## Sanity-check exercises

### Exercise 1: Fourier derivative sign

Using the convention

$$
\widetilde f(p)=\int d^dx\,e^{ip\cdot x}f(x),
$$

show that $\partial_\mu f(x)$ transforms to $-ip_\mu\widetilde f(p)$, assuming boundary terms vanish.

<details><summary><strong>Solution</strong></summary>

Compute directly:

$$
\widetilde{\partial_\mu f}(p)
=\int d^dx\,e^{ip\cdot x}\partial_\mu f(x).
$$

Integrating by parts gives

$$
\widetilde{\partial_\mu f}(p)
=-\int d^dx\,f(x)\partial_\mu e^{ip\cdot x}.
$$

Since

$$
\partial_\mu e^{ip\cdot x}=ip_\mu e^{ip\cdot x},
$$

we get

$$
\widetilde{\partial_\mu f}(p)=-ip_\mu\widetilde f(p).
$$

</details>

### Exercise 2: determinant variation

Show that

$$
\delta\log\det A=\operatorname{Tr}(A^{-1}\delta A)
$$

for an invertible finite matrix $A$.

<details><summary><strong>Solution</strong></summary>

Use

$$
\det(A+\delta A)=\det A\,\det(1+A^{-1}\delta A).
$$

For infinitesimal $\epsilon$, one has

$$
\det(1+\epsilon B)=1+\epsilon\operatorname{Tr}B+O(\epsilon^2).
$$

Therefore

$$
\delta\det A=(\det A)\operatorname{Tr}(A^{-1}\delta A).
$$

Divide by $\det A$ to obtain

$$
\delta\log\det A=\operatorname{Tr}(A^{-1}\delta A).
$$

</details>

### Exercise 3: delta function of a function

Let $g(x)=x^2-a^2$ with $a>0$. Show that

$$
\delta(x^2-a^2)=\frac{1}{2a}\bigl[\delta(x-a)+\delta(x+a)\bigr].
$$

<details><summary><strong>Solution</strong></summary>

The zeros of $g$ are $x=a$ and $x=-a$. Since

$$
g'(x)=2x,
$$

we have

$$
|g'(a)|=2a,
\qquad
|g'(-a)|=2a.
$$

Using

$$
\delta(g(x))=\sum_i\frac{\delta(x-x_i)}{|g'(x_i)|},
$$

we get

$$
\delta(x^2-a^2)=\frac{\delta(x-a)}{2a}+\frac{\delta(x+a)}{2a}.
$$

</details>

### Exercise 4: Gaussian two-point function

Let

$$
Z[J]=\int d^nx\,\exp\!\left(-\frac12x^TAx+J^Tx\right)
$$

with $A$ positive definite. Show that the normalized two-point function is $(A^{-1})_{ij}$.

<details><summary><strong>Solution</strong></summary>

The Gaussian integral is

$$
Z[J]=Z[0]\exp\!\left(\frac12J^TA^{-1}J\right).
$$

The normalized expectation is generated by $Z[J]/Z[0]$. Thus

$$
\langle x_ix_j\rangle
=\left.\frac{\partial^2}{\partial J_i\partial J_j}
\exp\!\left(\frac12J^TA^{-1}J\right)\right|_{J=0}
=(A^{-1})_{ij}.
$$

</details>

## References

For derivations and context, use the local pages linked above. Standard reference sources include Srednicki, *Quantum Field Theory*; Schwartz, *Quantum Field Theory and the Standard Model*; Weinberg, *The Quantum Theory of Fields*; Zinn-Justin, *Quantum Field Theory and Critical Phenomena*; Coleman, *Aspects of Symmetry* and *Lectures on Quantum Field Theory*; Di Francesco, Mathieu, and Sénéchal, *Conformal Field Theory*; Nakahara, *Geometry, Topology and Physics*; Frankel, *The Geometry of Physics*; Altland and Simons, *Condensed Matter Field Theory*; and the numerical and random-matrix references listed in the bibliography.

## Version history

- **2026-06-27:** First polished draft. Collects the core identities used across Mathematical Toolkit and links them to derivation pages.
