---
title: "Conventions and Notation"
description: "Scattering, amplitude, phase-space, loop, spin, polarization, and diagrammatic conventions used throughout the Perturbative QFT and Scattering volume."
sidebar:
  label: "Conventions and Notation"
  order: 10
level: "Graduate"
status: "Polished draft"
source: "Srednicki 2007; Coleman 2019; Weinberg 1995; Zee 2010; Schwartz 2014"
topics:
  - "scattering conventions"
  - "S-matrix normalization"
  - "phase space"
  - "Feynman rules"
  - "spin sums"
  - "dimensional regularization"
canonicalTopics:
  - "perturbative-qft-conventions"
  - "scattering-normalizations"
researchStatus:
  established:
    - "The formulas on this page are convention choices and standard scattering-theory normalizations. Different books distribute factors of i, 2π, 2E, and wave-function residues differently."
  active:
    - "No convention choice here is itself an active research question, but conventions become delicate in higher-order QCD, unstable-particle schemes, chiral dimensional regularization, infrared subtraction, and automated amplitude pipelines."
  speculative:
    - "None."
---

## Summary

This page fixes the scattering and perturbative-calculation conventions used in **Perturbative QFT and Scattering**. It extends the site-wide choices in [Foundations: Conventions and Normalizations](/foundations/conventions-and-normalizations/).

The default choices are:

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
\qquad
\hbar=c=1,
\qquad
f(x)=\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot x}\widetilde f(p),
$$

with covariantly normalized one-particle states,

$$
\langle \mathbf p',s'\mid \mathbf p,s\rangle
=(2\pi)^3 2E_{\mathbf p}\,
\delta^{(3)}(\mathbf p-\mathbf p')\delta_{ss'}.
$$

Scattering amplitudes are defined by

$$
S=\mathbf 1+iT,
\qquad
\langle f\mid iT\mid i\rangle
=
i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

If another page uses a different convention, it must say so before formulas are used.

:::note[Why this page exists]
Perturbative QFT is a precision bookkeeping machine. If two readers disagree by a sign, a factor of $2\pi$, a factor of $2E_{\mathbf p}$, or a symmetry factor, they may both understand the physics and still get incompatible numbers. This page is the anti-chaos pact.
:::

## Site-wide conventions inherited here

Unless stated otherwise, this volume inherits the following Foundations conventions:

| Object | Default convention |
|---|---|
| Metric | $\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-)$ |
| Dot product | $p\cdot x=p^0t-\mathbf p\cdot\mathbf x$ |
| On-shell energy | $p^0=E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}$ |
| Plane waves | $e^{-ip\cdot x}$ for positive-energy modes |
| Four-momentum integral | $\displaystyle \int_p\equiv\int\frac{d^4p}{(2\pi)^4}$ |
| Scalar propagator | $\displaystyle \frac{i}{p^2-m^2+i\epsilon}$ |
| Dirac slash notation | $p\!\!\!/\equiv\gamma^\mu p_\mu$ |
| Gamma matrices | $\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}\mathbf 1$ |
| Chirality matrix | $\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3$ |

The symbol $\epsilon$ in $i\epsilon$ is positive and infinitesimal. The $i\epsilon$ prescription is part of the definition of the Feynman propagator, not an optional decoration.

## Momentum labels and all-incoming notation

For a physical scattering process,

$$
1+2+\cdots+r\longrightarrow r+1+\cdots+n,
$$

we use positive-energy external momenta for both incoming and outgoing particles. The total incoming and outgoing four-momenta are

$$
P_i=\sum_{a=1}^r p_a,
\qquad
P_f=\sum_{b=r+1}^n p_b.
$$

The physical momentum-conservation delta function is

$$
(2\pi)^4\delta^{(4)}(P_f-P_i).
$$

For writing compact Feynman rules, it is often useful to use **all-incoming notation**. In that notation every external momentum is treated as flowing into the diagram and the conservation law is

$$
\sum_{a=1}^n k_a=0.
$$

For an outgoing physical particle of momentum $p$, the corresponding all-incoming momentum is $k=-p$. Pages must state clearly when they switch between physical in/out notation and all-incoming notation.

## One-particle states and invariant measure

The one-particle normalization is

$$
\langle \mathbf p',s'\mid \mathbf p,s\rangle
=(2\pi)^3 2E_{\mathbf p}\,
\delta^{(3)}(\mathbf p-\mathbf p')\delta_{ss'}.
$$

The corresponding one-particle completeness relation is

$$
\mathbf 1_{1\text{-particle}}
=
\sum_s\int d\Pi_p\,
\mid \mathbf p,s\rangle\langle \mathbf p,s\mid,
$$

where

$$
d\Pi_p
\equiv
\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
=
\frac{d^4p}{(2\pi)^3}\theta(p^0)\delta(p^2-m^2).
$$

For identical particles, the state normalization is still built from the same one-particle convention. Symmetry factors enter when states, amplitudes, or phase-space sums require them; they should not be inserted by guesswork.

## The S-matrix and invariant amplitude

The S-matrix is written

$$
S=\mathbf 1+iT.
$$

The invariant amplitude $\mathcal M_{fi}$ is defined by

$$
\langle f\mid iT\mid i\rangle
=
i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

Equivalently,

$$
\langle f\mid T\mid i\rangle
=
(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

With this convention:

- propagators and vertices include their usual factors of $i$;
- $\mathcal M$ is the object inserted into phase-space formulas;
- $\overline{|\mathcal M|^2}$ means spin/color sums and averages according to the rule stated below;
- disconnected identity contributions are not included in scattering amplitudes between different asymptotic states.

Some books call the same object $\mathcal A$, $i\mathcal M$, $\mathcal T$, or $T_{fi}$. When comparing sources, first identify whether their delta function, factor of $i$, and state normalization match ours.

## Connected and amputated conventions

The amplitude is extracted from connected time-ordered correlators by LSZ reduction. For scalar external particles, the schematic relation is

$$
\mathcal M
\sim
\left[\prod_{a=1}^n Z_a^{-1/2}\right]
\left[\prod_{a=1}^n (p_a^2-m_a^2)\right]
G_{\text{conn}}^{(n)}(p_1,\ldots,p_n)
\bigg|_{p_a^2\to m_a^2},
$$

up to the convention-dependent overall factors fixed by the detailed LSZ formula.

Here $Z_a$ is the residue of the exact propagator pole for the interpolating field used for particle $a$. If a renormalization condition sets the pole residue to one, the explicit $Z_a^{-1/2}$ factors disappear. If not, they do not disappear by magic; they are part of the LSZ normalization.

:::tip[Amputation is not optional]
External propagators belong to correlators. Scattering amplitudes use external on-shell states. LSZ is the bridge, and amputation is what removes the external propagator poles after taking their residues.
:::

## Phase space

For total incoming momentum $P$, the Lorentz-invariant $n$-body phase-space measure is

$$
d\Phi_n(P;p_1,\ldots,p_n)
=
(2\pi)^4\delta^{(4)}\!\left(P-\sum_{a=1}^n p_a\right)
\prod_{a=1}^n
\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a}.
$$

Usually we abbreviate this to $d\Phi_n(P)$.

When the final state is not being specified explicitly, especially in unitarity sums and inclusive observables, we also write

$$
\sum_X\int d\Pi_X
$$

for the Lorentz-invariant sum over complete on-shell final states. If $X$ is a fixed $n$-particle state with no additional sums, then $d\Pi_X$ is the same phase-space measure as $d\Phi_n(P)$, up to any explicitly stated spin, color, species, or identical-particle sums. Some pages also write $d\Pi_n$ in this completeness-relation sense.

By default, $d\Phi_n$ **does not** include a final-state identical-particle factor. If the final state contains $n_j$ identical particles of species $j$, the rate or cross section includes

$$
\frac{1}{S_f},
\qquad
S_f=\prod_j n_j!.
$$

Some authors absorb this factor into a modified phase-space definition. We do not unless a page explicitly says so.

## Decay rates

For a particle of mass $M$ decaying at rest into $n$ final particles,

$$
d\Gamma
=
\frac{1}{2M}\,\overline{|\mathcal M|^2}\,d\Phi_n(P),
\qquad
P^2=M^2.
$$

If the initial particle has spin or other internal quantum numbers and the decay rate is quoted for an unpolarized ensemble, $\overline{|\mathcal M|^2}$ includes the appropriate initial average. If the decay rate is for a definite initial polarization or internal state, no such average is taken.

The total decay rate is

$$
\Gamma=\int d\Gamma,
$$

and the lifetime is

$$
\tau=\frac{1}{\Gamma}
$$

when a single exponential decay law is valid.

## Cross sections and flux

For two incoming particles with momenta $p_1,p_2$ and masses $m_1,m_2$,

$$
d\sigma
=
\frac{1}{4\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}}
\,\overline{|\mathcal M|^2}\,d\Phi_n(P_i).
$$

Equivalently,

$$
d\sigma
=
\frac{1}{4E_1E_2 v_{\mathrm{rel}}}
\,\overline{|\mathcal M|^2}\,d\Phi_n(P_i),
$$

where the invariant relative velocity is defined by

$$
v_{\mathrm{rel}}
=
\frac{\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}}{E_1E_2}.
$$

For $2\to2$ scattering in the center-of-momentum frame,

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f|}{|\mathbf p_i|}
\overline{|\mathcal M|^2},
$$

with an additional factor $1/S_f$ if the two final particles are identical and phase space has not already been divided by that factor.

## Spin, polarization, and color sums

The notation

$$
\overline{|\mathcal M|^2}
$$

means:

1. sum over unobserved final spin, polarization, color, and internal quantum numbers;
2. average over initial spin, polarization, color, and internal quantum numbers when the beam or ensemble is unpolarized;
3. do **not** average over an initial quantum number if the observable is defined for a definite initial state.

For example, an unpolarized $2\to n$ cross section with incoming particles of degeneracies $g_1$ and $g_2$ uses

$$
\overline{|\mathcal M|^2}
=
\frac{1}{g_1g_2}
\sum_{\text{initial, final}}|\mathcal M|^2.
$$

For Dirac spinors, the default spin sums are

$$
\sum_s u_s(p)\overline u_s(p)=p\!\!\!/+m,
\qquad
\sum_s v_s(p)\overline v_s(p)=p\!\!\!/-m.
$$

For a massive vector particle with physical polarizations,

$$
\sum_{\lambda}\epsilon_\mu^{(\lambda)}(p)
\epsilon_\nu^{(\lambda)}(p)^*
=
-\eta_{\mu\nu}+\frac{p_\mu p_\nu}{m^2}.
$$

For a massless gauge boson, polarization sums are gauge-dependent unless contracted into gauge-invariant amplitudes. A covariant replacement such as $-\eta_{\mu\nu}$ is allowed only when Ward identities ensure that gauge-dependent pieces vanish in the complete amplitude.

## Mandelstam variables

For physical $2\to2$ scattering,

$$
p_1+p_2\longrightarrow p_3+p_4,
$$

we define

$$
s=(p_1+p_2)^2,
\qquad
t=(p_1-p_3)^2,
\qquad
u=(p_1-p_4)^2.
$$

Because the letter $u$ is also used for Dirac spinors, we sometimes write the third Mandelstam variable as $u_{\mathrm M}$ in explanatory text. In equations where no spinor confusion is possible, we use the standard symbol $u$.

The variables obey

$$
s+t+u=m_1^2+m_2^2+m_3^2+m_4^2.
$$

In the center-of-momentum frame, $s=E_{\mathrm{cm}}^2$.

:::caution[Notation clash]
The symbol $u$ can mean a Mandelstam variable or a positive-energy Dirac spinor. Context usually disambiguates it. When the clash is likely, this volume writes the Mandelstam variable as $u_{\mathrm M}$ or uses words.
:::

## Propagators and elementary scalar vertices

For a real scalar field with

$$
\mathcal L_0
=
\frac12\partial_\mu\phi\partial^\mu\phi
-
\frac12m^2\phi^2,
$$

the momentum-space Feynman propagator is

$$
\frac{i}{p^2-m^2+i\epsilon}.
$$

For

$$
\mathcal L_{\text{int}}=-\frac{\lambda}{4!}\phi^4,
$$

the four-scalar vertex is

$$
-i\lambda.
$$

For

$$
\mathcal L_{\text{int}}=-\frac{g}{3!}\phi^3,
$$

the three-scalar vertex is

$$
-ig.
$$

The factorials in the Lagrangian are part of the convention. They are chosen so that the elementary vertex rules are uncluttered.

## Fermion and gauge-interaction signs

The default Dirac Lagrangian is

$$
\mathcal L_0=\overline\psi(i\gamma^\mu\partial_\mu-m)\psi.
$$

For an Abelian gauge field, a field of charge $q$ has

$$
D_\mu=\partial_\mu+iqA_\mu.
$$

The minimally coupled Dirac Lagrangian is

$$
\mathcal L
=\overline\psi(i\gamma^\mu D_\mu-m)\psi
=\overline\psi(i\gamma^\mu\partial_\mu-m)\psi
-q\overline\psi\gamma^\mu A_\mu\psi.
$$

Thus the photon-fermion vertex for a field of charge $q$ is

$$
-iq\gamma^\mu.
$$

For the electron, $q=-e$ with $e>0$, so this convention gives

$$
+ie\gamma^\mu
$$

for the electron-photon vertex. Many textbooks choose the opposite sign convention for the covariant derivative and therefore write the electron vertex as $-ie\gamma^\mu$. Both conventions are fine; mixing them is not.

For non-Abelian gauge theory, generators are Hermitian and obey

$$
[T^a,T^b]=if^{abc}T^c.
$$

The default covariant derivative is

$$
D_\mu=\partial_\mu+igA_\mu^aT^a.
$$

Then

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c,
$$

and the matter-gauge vertex from $\overline\psi i\gamma^\mu D_\mu\psi$ is

$$
-ig\gamma^\mu T^a.
$$

Gauge-field self-interaction signs follow from this $F_{\mu\nu}^a$ convention.

## Symmetry factors in diagrams

There are two related but distinct uses of the phrase “symmetry factor.”

| Context | Meaning |
|---|---|
| Wick expansion and diagrams | A factor from the automorphisms of a diagram after expanding the interaction exponential. |
| Final-state phase space | A factor $1/n!$ for $n$ identical final particles of the same species. |

Do not transfer a factor from one context into the other automatically.

For scalar theories written with factorials, such as

$$
\mathcal L_{\text{int}}=-\frac{\lambda}{4!}\phi^4,
$$

the elementary vertex has no extra $4!$. Diagram symmetry factors are then determined by the graph combinatorics. For example, a vacuum bubble, a tadpole correction, and a four-point tree diagram do not share the same automorphism group merely because they all contain a $\phi^4$ vertex.

When a page quotes a diagram contribution, it should make clear whether the displayed coefficient already includes the diagram symmetry factor.

## Loop integration and dimensional regularization

A four-dimensional loop integral is written

$$
\int_\ell
\equiv
\int\frac{d^4\ell}{(2\pi)^4}.
$$

In dimensional regularization, we use

$$
d=4-2\epsilon,
$$

and write

$$
\int_\ell^{(d)}
\equiv
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d},
$$

where $\mu$ keeps couplings at their four-dimensional mass dimensions.

When using the modified minimal subtraction convention, we define

$$
\overline\mu^{\,2}=4\pi e^{-\gamma_E}\mu^2.
$$

Pages using $\overline{\mathrm{MS}}$ may absorb the associated $4\pi$ and $\gamma_E$ factors into the loop measure. They must state which measure is being used before quoting finite parts.

A typical scalar loop denominator is written with the Feynman prescription,

$$
\frac{1}{\ell^2-m^2+i\epsilon}.
$$

After Wick rotation, denominators become Euclidean denominators of the form

$$
\ell_E^2+m^2,
$$

provided the contour deformation is allowed by the pole prescription and external kinematics. Wick rotation is a theorem in some kinematic regions and a trap in others.

## Renormalized perturbation theory notation

Bare parameters carry a subscript $0$:

$$
\phi_0,
\qquad
m_0,
\qquad
\lambda_0,
\qquad
g_0.
$$

Renormalized parameters usually have no subscript:

$$
\phi,
\qquad
m,
\qquad
\lambda,
\qquad
g.
$$

For a scalar field, a common convention is

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
m_0^2=m^2+\delta m^2,
\qquad
\lambda_0=\mu^{2\epsilon}(\lambda+\delta\lambda),
$$

although the exact placement of $Z$ factors and powers of $\mu$ depends on the renormalization scheme.

Counterterm diagrams are part of perturbation theory. At a fixed order, the amplitude is schematically

$$
\mathcal M
=
\mathcal M_{\text{ordinary diagrams}}
+
\mathcal M_{\text{counterterm diagrams}}.
$$

A divergent loop amplitude without its counterterm contribution is usually not a physical prediction.

## Inclusive observables and infrared notation

Ultraviolet divergences come from large loop momentum. Infrared divergences come from soft or collinear regions. They are different beasts and should not be swatted with the same conceptual flyswatter.

We use:

| Symbol or phrase | Meaning |
|---|---|
| UV | large virtual momentum, short-distance sensitivity |
| IR | low-energy or long-distance sensitivity |
| soft | momentum $k^\mu\to0$ |
| collinear | massless momenta becoming parallel, such as $p_i\cdot p_j\to0$ |
| inclusive observable | an observable that sums over unresolved degenerate final states |
| IR safe observable | an observable insensitive to adding unresolved soft or collinear radiation |

In gauge theories with massless particles, virtual corrections and real-emission corrections are often separately infrared divergent. A physical inclusive observable has the schematic structure

$$
\sigma_{\text{inclusive}}
=
\sigma_{\text{Born}}
+
\sigma_{\text{virtual}}
+
\sigma_{\text{real}}
+
\cdots,
$$

where the infrared-sensitive pieces cancel or factorize according to the observable definition.

## Analytic structure and discontinuities

The Feynman prescription fixes how amplitudes are approached as analytic functions of invariants such as $s,t,u$.

For a function with a branch cut in $s$, the discontinuity across the cut is

$$
\operatorname{Disc}_s\mathcal M(s)
=
\mathcal M(s+i0)-\mathcal M(s-i0).
$$

With our S-matrix convention, unitarity implies

$$
S^\dagger S=\mathbf 1,
$$

or

$$
-i(T-T^\dagger)=T^\dagger T.
$$

The optical theorem and Cutkosky rules are consequences of this relation, with normalization factors inherited from the state conventions above.

## Crossing conventions

Crossing relates amplitudes with different assignments of particles between initial and final states by analytic continuation of external momenta and quantum numbers.

In practice, for an outgoing particle with momentum $p$, the crossed incoming antiparticle carries momentum $-p$ in the all-incoming analytic convention. The physical crossed process then lives in a different real kinematic region.

Crossing is not the instruction “put a minus sign wherever convenient.” It is an analytic statement about amplitudes, singularities, and external-state conventions.

## Common pitfalls

### Losing the identity term in the S-matrix

The expression $S=\mathbf 1+iT$ means the identity part exists. For nontrivial scattering between different states it usually drops out, but for forward scattering and unitarity it matters.

### Confusing T with the amplitude

$T$ is an operator. $\mathcal M$ is the invariant amplitude after stripping off the momentum-conserving delta function according to our convention.

### Averaging over the wrong states

Spin/color averages are part of the observable definition. A polarized cross section and an unpolarized cross section are different observables.

### Double-counting identical-particle factors

The final-state $1/n!$ is not the same as a diagram automorphism factor. Adding both in the wrong place is a classic way to become off by exactly the kind of rational number that ruins a calculation quietly.

### Treating gauge-boson polarization sums too casually

Replacing a massless gauge-boson polarization sum by $-\eta_{\mu\nu}$ is safe only inside a gauge-invariant calculation where Ward identities remove unphysical polarizations.

### Importing textbook QED signs without checking the covariant derivative

The sign of a photon-fermion vertex depends on the sign convention for $D_\mu$. This volume follows the qft.org convention $D_\mu=\partial_\mu+iqA_\mu$.

### Forgetting scheme dependence

A finite part in $\overline{\mathrm{MS}}$ is not necessarily the same finite part in an on-shell scheme. Physical observables agree after all parameters are related consistently.

## Relation to other topics

- [Foundations: Conventions and Normalizations](/foundations/conventions-and-normalizations/) fixes the site-wide metric, Fourier, state, propagator, spinor, path-integral, and Euclidean conventions.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) explains the origin of the scalar $i\epsilon$ prescription.
- [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) and [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) give the first diagrammatic expansion.
- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) introduces why gauge choices are descriptive rather than physical.
- [Renormalization, RG, and EFT](/renormalization-rg-eft/) gives the conceptual home for scale dependence, scheme dependence, Wilsonian RG, and EFT matching.
- [Computational QFT and Tools](/computational-qft/) should use this page as the default normalization standard for symbolic and numerical amplitude workflows.

## References and further reading

- M. Srednicki, *Quantum Field Theory*, §§5, 10–11, 14–20, 26–28, 41, 45–48, for LSZ, amplitudes, cross sections, loops, spin sums, and renormalized perturbation theory.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 7–17 and 30–35, for S-matrix conventions, Wick diagrams, LSZ, scattering, phase space, renormalization, and QED examples.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 3, 6, 8–10, 12, 13, for scattering theory, Feynman rules, QED, path integrals, renormalization, and infrared effects.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5–7, 13, 16–24, 26–27, for cross sections, decay rates, LSZ, Feynman rules, QED, renormalization, unitarity, and Yang–Mills conventions.
- A. Zee, *Quantum Field Theory in a Nutshell*, Appendix C and Parts I–III, for compact Feynman-rule and QED conventions.

## Version history

- **2026-06-11:** Initial perturbative-QFT convention lock. This page contains no exercises because it is a normalization reference rather than a calculation-heavy lecture note.
