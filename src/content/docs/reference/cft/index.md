---
title: "Modern CFT for AdS/CFT"
description: "A graduate course on conformal field theory designed as preparation for the AdS/CFT correspondence."
sidebar:
  order: 0
---

:::caution[Site under construction]
The initial drafts were prepared with the assistance of AI and have since been reviewed and edited by me. Although I have tried to ensure accuracy, some errors may remain. Especially, almost all figures were drawn by AI, and many are inaccurate. If you notice any significant mistakes, I would greatly appreciate your [feedback](/feedback/send-feedback).
:::

## Why this course exists

The AdS/CFT correspondence is often introduced as a striking equality between two theories,

$$
Z_{\mathrm{CFT}}[J] = Z_{\mathrm{bulk}}[\phi_{\partial}=J],
$$

but this equation is only useful once the left-hand side is understood with some maturity. The boundary theory is not merely a source of examples. It is the definition of the quantum-gravity problem in asymptotically AdS spacetime. The bulk metric, fields, particles, black holes, strings, and semiclassical expansion are all encoded in CFT quantities: operator dimensions, OPE coefficients, correlation functions, Ward identities, thermal states, global symmetries, supersymmetry, and large-$N$ factorization.

This course is therefore a course on conformal field theory with a deliberately holographic bias. We will learn CFT not as an isolated subject, but as the language in which AdS/CFT is written.

:::note[The organizing claim]
A CFT is specified by its operator spectrum and OPE data, and AdS/CFT is a special large-$N$ organization of that data.
:::

More explicitly, the basic CFT data are

$$
\left\{\Delta_i,\, \ell_i,\, R_i,\, C_{ijk}\right\},
$$

where $\Delta_i$ is the scaling dimension, $\ell_i$ is the spin, $R_i$ denotes global-symmetry quantum numbers, and $C_{ijk}$ are OPE coefficients. In a holographic CFT, this same data is reorganized as the spectrum and interactions of fields in AdS.

The slogan is simple, but its content is deep:

$$
\begin{array}{ccl}
\text{CFT primary operator } \mathcal O_i &\longleftrightarrow& \text{bulk field } \phi_i,\\[4pt]
\text{dimension } \Delta_i &\longleftrightarrow& \text{bulk mass } m_i,\\[4pt]
\text{OPE coefficient } C_{ijk} &\longleftrightarrow& \text{bulk cubic coupling},\\[4pt]
\text{large } N \text{ factorization} &\longleftrightarrow& \text{weak bulk coupling},\\[4pt]
\text{sparse low-dimension spectrum} &\longleftrightarrow& \text{local effective gravity in AdS}.
\end{array}
$$

The purpose of this course is to make every line of this dictionary feel inevitable rather than mysterious.

<figure class="doc-figure" style="--figure-width: 60rem; --caption-width: 55rem;">

![Roadmap for the course Modern CFT for AdS/CFT](/figures/cft/modern-cft-roadmap.svg)

<figcaption>

The course follows a higher-dimensional CFT spine from RG fixed points to conformal data, crossing, large $N$, and finally the pre-AdS/CFT dictionary. The two-dimensional branch gives the exact-solution technology needed for strings, AdS$_3$/CFT$_2$, modular invariance, and worldsheet CFT.

</figcaption>
</figure>

## What makes this different from a standard CFT course

A traditional two-dimensional CFT course usually begins with holomorphic maps, the stress tensor $T(z)$, the Virasoro algebra, minimal models, modular invariance, and WZW models. That is a beautiful subject, and part of this course will treat it seriously. But AdS/CFT usually requires a different first emphasis.

For holography, the most important CFT concepts are the ones that survive in general dimension:

- conformal symmetry as $SO(d,2)$,
- the state-operator correspondence,
- primary operators and conformal multiplets,
- stress-tensor and current Ward identities,
- two-, three-, and four-point functions,
- the OPE and conformal blocks,
- unitarity and crossing,
- thermal CFT and entanglement,
- supersymmetric shortening,
- large-$N$ factorization,
- single-trace and multi-trace operator structure.

The two-dimensional theory then enters twice. First, it is the most powerful exactly solvable laboratory for CFT. Second, it is indispensable for string theory and AdS$_3$/CFT$_2$. But the main line of the course is higher-dimensional and operator-algebraic, because that is the shortest path to AdS/CFT.

## Prerequisites

The expected background is graduate quantum field theory at the level of path integrals, symmetries, Noether currents, canonical quantization, and basic renormalization. Familiarity with general relativity and string theory is helpful but not required for the CFT part. The course will repeatedly point toward AdS/CFT, but it will not assume that the reader already knows the holographic dictionary.

The minimum technical toolkit is:

$$
\begin{array}{ll}
\text{QFT:} & \text{path integrals, correlation functions, Ward identities, RG flow},\\[3pt]
\text{Group theory:} & \text{Lie algebras, representations, weights at a basic level},\\[3pt]
\text{Geometry:} & \text{manifolds, conformal maps, spheres, cylinders, Euclidean vs Lorentzian signature},\\[3pt]
\text{SUSY:} & \text{useful but introduced where needed}.
\end{array}
$$

When a tool is essential, we will derive it. When a tool is merely convenient, we will isolate it in an appendix.

## The conceptual spine

The course is built around five transitions.

### 1. From RG fixed points to conformal symmetry

A CFT is first of all a local QFT at an RG fixed point. In a theory deformed by local operators,

$$
S = S_{\ast} + \sum_i g_i \int d^d x\, \mathcal O_i(x),
$$

the beta functions describe how couplings change with scale:

$$
\mu \frac{d g_i}{d\mu} = \beta_i(g).
$$

At a fixed point, $\beta_i=0$. In a local relativistic theory, this is closely tied to the trace of the stress tensor,

$$
T^\mu{}_{\mu} = \sum_i \beta_i \mathcal O_i + \text{possible anomalies and improvement terms}.
$$

At the fixed point in flat space, after suitable improvement and in the absence of explicit anomalies, one expects

$$
T^\mu{}_{\mu}=0.
$$

This condition is the seed of conformal invariance.

### 2. From conformal symmetry to representation theory

The conformal group in $d$-dimensional Lorentzian spacetime is $SO(d,2)$. Its generators are translations $P_\mu$, Lorentz transformations $M_{\mu\nu}$, dilatations $D$, and special conformal transformations $K_\mu$.

Local operators are organized into conformal multiplets. A primary operator $\mathcal O(0)$ obeys

$$
[K_\mu,\mathcal O(0)] = 0,
$$

and descendants are obtained by acting with translations:

$$
P_{\mu_1}\cdots P_{\mu_n}\mathcal O(0) \quad \longleftrightarrow \quad \partial_{\mu_1}\cdots\partial_{\mu_n}\mathcal O(0).
$$

The scaling dimension $\Delta$ is the eigenvalue of $D$. Under radial quantization, $D$ becomes the Hamiltonian on the cylinder $S^{d-1}\times \mathbb R$:

$$
\mathcal O(0) \longleftrightarrow |\mathcal O\rangle,
\qquad
D|\mathcal O\rangle = \Delta |\mathcal O\rangle.
$$

This is the first major bridge to AdS/CFT: CFT scaling dimensions become energies of states on global AdS.

### 3. From symmetry to correlators

Conformal symmetry fixes two- and three-point functions almost completely. For scalar primary operators,

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
= \frac{\delta_{ij}}{|x|^{2\Delta_i}},
$$

after a convenient normalization, and

$$
\langle \mathcal O_i(x_1)\mathcal O_j(x_2)\mathcal O_k(x_3)\rangle
=
\frac{C_{ijk}}
{|x_{12}|^{\Delta_i+\Delta_j-\Delta_k}
 |x_{23}|^{\Delta_j+\Delta_k-\Delta_i}
 |x_{13}|^{\Delta_i+\Delta_k-\Delta_j}}.
$$

Four-point functions are different. They depend on conformal cross-ratios and therefore contain dynamical information. For identical scalar primaries,

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\mathcal O(x_4)\rangle
=
\frac{1}{|x_{12}|^{2\Delta}|x_{34}|^{2\Delta}}\,G(u,v),
$$

where

$$
u = \frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v = \frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The function $G(u,v)$ is where the theory starts to breathe. In AdS/CFT, its singularities, OPE limits, and large-$N$ expansion know about bulk particles, interactions, locality, and causality.

### 4. From OPE associativity to bootstrap

The operator product expansion says that nearby local operators can be replaced by a convergent sum of local operators:

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ijk}\, |x|^{\Delta_k-\Delta_i-\Delta_j}
\left(\mathcal O_k(0)+\text{descendants}\right).
$$

Associativity of this operator algebra is the conformal bootstrap. In a four-point function, performing the OPE in different channels must give the same answer. Schematically,

$$
\sum_{\mathcal O} C_{12\mathcal O}C_{34\mathcal O}\,G_{\Delta,\ell}^{(s)}(u,v)
=
\sum_{\mathcal O} C_{14\mathcal O}C_{23\mathcal O}\,G_{\Delta,\ell}^{(t)}(u,v).
$$

Here $G_{\Delta,\ell}$ are conformal blocks. In a holographic CFT, the block expansion has a particularly sharp interpretation: single-trace exchanges are single-particle exchanges in AdS, and double-trace towers are multi-particle states.

### 5. From large $N$ to semiclassical AdS

A generic CFT is not holographic in the Einstein-gravity sense. The key additional condition is not simply conformal symmetry, but a special organization of the operator algebra.

The most important features are:

$$
\begin{array}{ll}
\text{large } N \text{ factorization:}
& \langle \mathcal O_1\cdots \mathcal O_n\rangle_{\mathrm{conn}} \ll 1,\\[4pt]
\text{single-trace sector:}
& \text{a distinguished set of low-dimension single-particle operators},\\[4pt]
\text{multi-trace sector:}
& \text{composite operators corresponding to multi-particle states},\\[4pt]
\text{sparse light spectrum:}
& \text{few low-spin operators below the high-spin/stringy gap}.
\end{array}
$$

In matrix large-$N$ theories, a common normalization gives

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_{\mathrm{conn}} \sim N^{2-n}
$$

for single-trace operators normalized so that their two-point functions are $O(1)$. This is the CFT origin of the classical bulk expansion:

$$
\frac{1}{N^2} \quad \longleftrightarrow \quad G_N^{\mathrm{bulk}}.
$$

## Course structure

The course is organized into fourteen parts. The plan below makes the Lorentzian, large-$N$, and holographic-locality themes explicit while keeping the reading sequence clean.

| Part | Main purpose |
|---:|---|
| 01 | Why CFT is the boundary language of AdS/CFT; observables, sources, signatures, and the map from CFT data to bulk interpretation. |
| 02 | Wilsonian RG, critical phenomena, stress-tensor trace, beta functions, improvements, and CFT data. |
| 03 | Conformal transformations, $SO(d,2)$, compactification, cylinder, causal structure, and embedding space. |
| 04 | Primary operators, currents, stress tensor, generating functionals, source dependence, and Ward identities. |
| 05 | Scalar and spinning correlators, cross-ratios, Lorentzian correlators, analyticity, and $i\epsilon$ prescriptions. |
| 06 | State-operator correspondence, reflection positivity, unitarity bounds, shortening, and conformal Casimirs. |
| 07 | OPE convergence, conformal blocks, crossing equations, numerical bootstrap, lightcone bootstrap, and causality constraints. |
| 08 | Complex coordinates, local conformal symmetry, $T(z)$, Virasoro, central charge, highest-weight modules, and free fields. |
| 09 | Minimal models, modular invariance, Cardy formula, current algebras, WZW models, Liouville theory, and AdS$_3$/strings. |
| 10 | CFT on curved spaces, Weyl anomaly, thermal CFT, modular Hamiltonians, entanglement, and black-hole preparation. |
| 11 | Global symmetries, flavor currents, anomalies, superconformal algebras, BPS multiplets, and conformal manifolds. |
| 12 | Generalized free fields, single- and multi-trace operators, planar expansion, large-$N$ OPE, and CFT signals of bulk locality. |
| 13 | $\mathcal N=4$ SYM, chiral primaries, Wilson loops, defects, spin chains, and the pre-dictionary for AdS$_5$/CFT$_4$. |
| 14 | Notation, Lie algebra reference, embedding-space formulas, supersymmetry cheatsheets, problems, glossary, and bibliography. |

Each lecture page contains a short “AdS/CFT checkpoint.” This is not decoration. It is the main guardrail of the course: every major CFT concept should eventually answer the question, “What does this become in the bulk?”

## The source viewpoint

One of the most important habits in AdS/CFT is to think of a QFT through sources. Given local operators $\mathcal O_i$, define a source-dependent generating functional

$$
Z[J] = \left\langle \exp\left(\sum_i \int d^d x\,J_i(x)\mathcal O_i(x)\right)\right\rangle.
$$

The connected generating functional is

$$
W[J] = \log Z[J].
$$

Connected correlation functions are obtained by functional differentiation:

$$
\langle \mathcal O_{i_1}(x_1)\cdots \mathcal O_{i_n}(x_n)\rangle_{\mathrm{conn}}
=
\left.
\frac{\delta^n W[J]}{\delta J_{i_1}(x_1)\cdots \delta J_{i_n}(x_n)}
\right|_{J=0}.
$$

This formula is the CFT side of the basic AdS/CFT prescription. The bulk boundary condition $\phi_i|_{\partial \mathrm{AdS}}=J_i$ says that the boundary value of a bulk field is the source for the dual CFT operator.

Thus, even before learning any bulk gravity, one should become fluent with the CFT meaning of sources, contact terms, Ward identities, and functional derivatives.

## Euclidean and Lorentzian thinking

Most of the course will begin in Euclidean signature because conformal symmetry, OPE convergence, radial quantization, and reflection positivity are cleanest there. But AdS/CFT is also profoundly Lorentzian. Black holes, causality, horizons, chaos, scattering, and real-time response all require Lorentzian correlators.

A useful mental division is:

$$
\begin{array}{ll}
\text{Euclidean CFT:} & \text{operator algebra, OPE convergence, bootstrap, path integrals},\\[3pt]
\text{Lorentzian CFT:} & \text{causality, commutators, Regge limits, thermal response, chaos},\\[3pt]
\text{Cylinder CFT:} & \text{Hamiltonian interpretation and state-operator correspondence}.
\end{array}
$$

We will move among these viewpoints repeatedly. The same CFT data controls all of them, but different physics becomes visible in each frame.

## Normalizations and conventions

Unless otherwise stated, $d$ denotes the spacetime dimension of the CFT. Euclidean coordinates are written as $x^\mu$, with $x^2=x^\mu x_\mu$. Lorentzian signature will be introduced explicitly when needed.

For scalar primary operators, we often choose the two-point normalization

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle = \frac{\delta_{ij}}{|x|^{2\Delta_i}}.
$$

With this convention, the coefficients $C_{ijk}$ appearing in three-point functions are physical CFT data, up to choices of operator basis in degenerate sectors.

The stress tensor is normalized by its Ward identity. Its two-point function defines a central-charge-like coefficient $C_T$ in any dimension:

$$
\langle T_{\mu\nu}(x)T_{\rho\sigma}(0)\rangle
=
\frac{C_T}{x^{2d}}\,\mathcal I_{\mu\nu,\rho\sigma}(x),
$$

where $\mathcal I_{\mu\nu,\rho\sigma}(x)$ is the tensor structure fixed by conformal symmetry. In a holographic theory, $C_T$ scales like the inverse bulk Newton constant:

$$
C_T \sim \frac{R_{\mathrm{AdS}}^{d-1}}{G_N}.
$$

## What success looks like

By the end of the course, a reader should be able to do the following without treating AdS/CFT as a black box:

1. identify the CFT data contained in two-, three-, and four-point functions;
2. use Ward identities to constrain correlators involving $T_{\mu\nu}$ and conserved currents;
3. explain the state-operator map and its relation to global AdS energies;
4. decompose four-point functions into conformal blocks and state the crossing equations;
5. understand why large-$N$ factorization suggests a weakly coupled bulk theory;
6. distinguish single-trace, double-trace, and multi-trace operators;
7. explain why $\mathcal N=4$ SYM is the canonical CFT in AdS$_5$/CFT$_4$;
8. read basic holographic formulas such as $m^2R^2=\Delta(\Delta-d)$ with confidence.

The goal is not memorization. The goal is to make the structure of AdS/CFT feel forced by the structure of CFT.

## Exercises

### Exercise 1. Dimensions and bulk masses

For a scalar operator $\mathcal O$ in a $d$-dimensional CFT, the corresponding scalar field in AdS$_{d+1}$ obeys

$$
m^2R^2 = \Delta(\Delta-d).
$$

Show that the two possible dimensions solving this equation are

$$
\Delta_{\pm}=\frac d2 \pm \sqrt{\frac{d^2}{4}+m^2R^2}.
$$

What happens when $m^2R^2=0$?

<details>
<summary><strong>Solution</strong></summary>

The equation is quadratic in $\Delta$:

$$
\Delta^2-d\Delta-m^2R^2=0.
$$

Solving gives

$$
\Delta_{\pm}
=
\frac{d\pm\sqrt{d^2+4m^2R^2}}{2}
=
\frac d2 \pm \sqrt{\frac{d^2}{4}+m^2R^2}.
$$

For $m^2R^2=0$, the two roots are

$$
\Delta_+=d,
\qquad
\Delta_-=0.
$$

The $\Delta=d$ solution is the standard dimension for a massless bulk scalar dual to a nontrivial scalar operator. The $\Delta=0$ behavior corresponds to the non-normalizable constant mode, interpreted as a source or coupling rather than an ordinary fluctuating operator in the standard quantization.

</details>

### Exercise 2. Why connected correlators matter

Suppose single-trace operators are normalized so that

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle \sim O(1),
$$

and connected correlators scale as

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_{\mathrm{conn}} \sim N^{2-n}.
$$

Explain why this resembles a weakly coupled classical theory in the bulk.

<details>
<summary><strong>Solution</strong></summary>

A weakly coupled classical bulk theory has tree-level interactions controlled by a small coupling. In AdS/CFT, the role of the small coupling is played by $1/N$ or, more precisely in many matrix theories, by $1/N^2$.

The two-point function is order one, so single-particle states have finite norm. The three-point connected function scales like

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle_{\mathrm{conn}}\sim \frac{1}{N},
$$

which means cubic interactions are weak. The four-point connected function scales like

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle_{\mathrm{conn}}\sim \frac{1}{N^2},
$$

which is the same order as tree-level exchange or contact interactions built from two cubic vertices or one quartic vertex.

Meanwhile, disconnected pieces dominate. That is the boundary version of a Fock-space description: multi-particle states are approximately products of single-particle states. Interactions are suppressed by powers of $1/N$.

</details>

### Exercise 3. Sources and one-point functions

Let

$$
W[J]=\log Z[J],
\qquad
Z[J]=\left\langle \exp\left(\int d^d x\,J(x)\mathcal O(x)\right)\right\rangle.
$$

Show that

$$
\frac{\delta W[J]}{\delta J(x)}=\langle \mathcal O(x)\rangle_J,
$$

where $\langle\cdots\rangle_J$ means expectation value in the presence of the source $J$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate $W[J]=\log Z[J]$:

$$
\frac{\delta W[J]}{\delta J(x)}
=
\frac{1}{Z[J]}\frac{\delta Z[J]}{\delta J(x)}.
$$

The derivative of $Z[J]$ brings down the operator:

$$
\frac{\delta Z[J]}{\delta J(x)}
=
\left\langle
\mathcal O(x)\exp\left(\int d^d y\,J(y)\mathcal O(y)\right)
\right\rangle.
$$

Therefore

$$
\frac{\delta W[J]}{\delta J(x)}
=
\frac{
\left\langle
\mathcal O(x)\exp\left(\int d^d y\,J(y)\mathcal O(y)\right)
\right\rangle
}{
\left\langle
\exp\left(\int d^d y\,J(y)\mathcal O(y)\right)
\right\rangle
}
=\langle \mathcal O(x)\rangle_J.
$$

This is the precise CFT statement behind the holographic rule that varying the on-shell bulk action with respect to the boundary value of a field gives the expectation value of the dual operator.

</details>

## Reading guide

The first reading path is the core higher-dimensional path:

$$
\text{RG} \to SO(d,2) \to \text{operators} \to \text{Ward identities} \to \text{OPE} \to \text{bootstrap} \to \text{large }N.
$$

The second path is the two-dimensional exact-solution path:

$$
\text{complex coordinates} \to T(z) \to \text{Virasoro} \to \text{minimal models} \to \text{modular invariance} \to \text{WZW/Liouville}.
$$

The third path is the AdS/CFT bridge:

$$
\text{sources} \to \text{single-trace operators} \to \text{large }N \to \mathcal N=4\text{ SYM} \to \text{bulk fields and interactions}.
$$

A reader focused on AdS$_5$/CFT$_4$ should prioritize the first and third paths. A reader focused on strings or AdS$_3$/CFT$_2$ should also follow the second path carefully.

## AdS/CFT checkpoint

The first checkpoint is the most important one:

$$
\boxed{
\text{Before learning the bulk dictionary, learn what the CFT can say without the bulk.}
}
$$

The CFT knows its Hilbert space, symmetries, operator algebra, correlation functions, thermal states, and entanglement structure. AdS/CFT does not replace these ideas. It geometrizes them.
