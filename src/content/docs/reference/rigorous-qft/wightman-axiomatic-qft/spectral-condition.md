---
title: "Spectral Condition"
description: "Explains the positive-energy spectral condition in Wightman QFT, its momentum-space support form, and its consequences for stability and analyticity."
sidebar:
  label: "Spectral Condition"
  order: 4
level: Graduate
status: "Polished draft"
source: "Wightman; Streater–Wightman; Jost; Haag; Reed–Simon; Källén–Lehmann spectral representation."
topics:
  - spectral condition
  - positive energy
  - Wightman functions
  - analytic continuation
  - spectrum of translations
canonicalTopics:
  - wightman-axioms
  - spectral-condition
  - positive-energy-representation
researchStatus:
  established:
    - "The Wightman spectral condition requires the joint spectrum of the translation generators to lie in the closed future light cone."
    - "Equivalently, the Fourier transforms of vacuum correlation functions have one-sided support in relative momenta, leading to tube analyticity."
  active:
    - "Massless charged sectors, infraparticles, and gauge constraints often require more refined algebraic or scattering-theoretic formulations than the simplest particle-spectrum picture."
---

## Summary

The spectral condition is the positive-energy axiom of Wightman QFT. If translations are represented by

$$
U(a,I)=e^{ia^\mu P_\mu},
$$

then their joint spectrum must obey

$$
\operatorname{Spec}(P)
\subset \overline V_+
=
\{p\in\mathbb R^d:p^0\ge0,\ p^2\ge0\}.
$$

Here $\overline V_+$ is the closed future light cone in momentum space. In the mostly-minus convention, $p^2=(p^0)^2-\mathbf p^2$. The condition says more than $H=P^0\ge0$: it says the whole energy-momentum spectrum is compatible with relativistic positivity.

For vacuum $n$-point functions, translation invariance lets us write

$$
W_n(x_1,\ldots,x_n)
=
w_n(\xi_1,\ldots,\xi_{n-1}),
\qquad
\xi_j=x_j-x_{j+1}.
$$

With this choice of relative variables and the Fourier convention of this volume, the spectral condition becomes the support statement

$$
\operatorname{supp}\widetilde w_n
\subset
(\overline V_+)^{n-1}.
$$

This support property is one of the hidden engines behind Wightman theory. It gives vacuum stability, excludes negative-energy excitations, controls the Källén–Lehmann representation, and makes Wightman functions boundary values of analytic functions in complexified spacetime.

<figure class="doc-figure" style="--figure-width: 40rem;">

![The spectral condition in momentum space](/figures/rigorous-qft/spectral-condition-cone.svg)

<figcaption>

In a $1+1$-dimensional momentum-space slice, the spectral condition puts the joint energy-momentum spectrum inside the closed future cone $\overline V_+$. The vacuum is at $p=0$; one-particle states may lie on mass hyperbolae; multiparticle states form continua still contained in the cone.

</figcaption>
</figure>

## Prerequisites

You should know the basic Wightman data from [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/), the Hilbert-space setup from [Hilbert Space and Fields](/rigorous-qft/wightman-axiomatic-qft/hilbert-space-and-fields/), and the transformation law from [Poincaré Covariance](/rigorous-qft/wightman-axiomatic-qft/poincare-covariance/).

The distributional support statement uses the Fourier-transform conventions fixed in [Conventions and Logical Status](/rigorous-qft/conventions/) and the smearing language from [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/).

## Core idea

A relativistic quantum theory should have a stable vacuum. In ordinary quantum mechanics, this usually means the Hamiltonian is bounded below. In relativistic QFT, the sharper invariant statement is about the joint spectrum of all translation generators.

Translations form an Abelian group, so the self-adjoint generators $P_\mu$ have a joint spectral resolution. The spectral condition says that the energy-momentum values seen by the theory lie in the future cone:

$$
\operatorname{Spec}(P)
\subset \overline V_+.
$$

This is exactly the region occupied by possible total momenta of physical states built from particles with nonnegative mass squared and positive energy. The condition does not say that the spectrum consists only of particle mass shells. Interacting QFTs usually have continuous multiparticle spectrum, possible bound-state shells, thresholds, and sometimes no ordinary isolated one-particle mass shell at all.

The important point is the **one-sidedness** of the spectrum. When a field creates an excitation from the vacuum, it can create positive-energy momentum, not arbitrary Fourier modes with both signs of energy.

A useful slogan is:

$$
\text{spectral condition}
=
\text{relativistic stability plus positive time direction}.
$$

## Setup and conventions

Work in $d$-dimensional Minkowski space with mostly-minus metric. The proper orthochronous Poincaré group acts on states by a strongly continuous unitary representation $U$. For translations,

$$
U(a,I)=e^{ia\cdot P},
\qquad
 a\cdot P=a^\mu P_\mu.
$$

With the usual physical notation,

$$
P^\mu=(H,\mathbf P),
\qquad
P_\mu=(H,-\mathbf P).
$$

The closed future cone is

$$
\overline V_+
=
\{p:p^0\ge0,\ p^2\ge0\}.
$$

The open future cone is

$$
V_+
=
\{p:p^0>0,\ p^2>0\}.
$$

The vacuum vector satisfies

$$
P_\mu\Omega=0,
$$

so the origin $p=0$ is always part of the spectrum. If the vacuum is unique and the theory has a mass gap $m>0$, then the spectrum has the schematic form

$$
\operatorname{Spec}(P)
\subset
\{0\}
\cup
\{p\in\overline V_+:p^2\ge m^2\}.
$$

This last display is an additional mass-gap hypothesis, not part of the bare spectral condition.

## The Hilbert-space statement

The translation subgroup is represented by commuting self-adjoint operators in the spectral-theorem sense. There is a projection-valued measure $E(\Delta)$ on momentum space such that

$$
U(a,I)=
\int_{\mathbb R^d} e^{ia\cdot p}\,dE(p).
$$

The joint spectrum is the closed support of this projection-valued measure. The Wightman spectral condition is

$$
E(\mathbb R^d\setminus\overline V_+)=0.
$$

Equivalently, every state has spectral support in $\overline V_+$. If $\Psi\in\mathcal H$, then

$$
\Psi=E(\overline V_+)\Psi.
$$

This formulation is more precise than saying "all particles have positive energy." A Wightman theory may not have a complete particle interpretation. The spectrum belongs to the representation of translations on the Hilbert space, whether or not the states are decomposed into particles.

## The Wightman-function support statement

Let

$$
W_n(x_1,\ldots,x_n)
=
\langle\Omega,
\phi_1(x_1)\cdots\phi_n(x_n)\Omega\rangle
$$

in distributional kernel notation. Translation invariance gives a distribution $w_n$ in $n-1$ variables:

$$
W_n(x_1,\ldots,x_n)
=
w_n(x_1-x_2,\ldots,x_{n-1}-x_n).
$$

With the Fourier convention

$$
w_n(\xi_1,\ldots,\xi_{n-1})
=
\int
\prod_{j=1}^{n-1}\frac{d^dp_j}{(2\pi)^d}
\,e^{-i\sum_j p_j\cdot\xi_j}
\widetilde w_n(p_1,\ldots,p_{n-1}),
$$

the spectral condition implies

$$
\operatorname{supp}\widetilde w_n
\subset
(\overline V_+)^{n-1}.
$$

This support statement is one of the most efficient ways to use the axiom. It turns Hilbert-space positivity of energy into a concrete analytic property of vacuum distributions.

The sign and cone depend on the choice of relative variables and Fourier phase. This page uses $\xi_j=x_j-x_{j+1}$ and $e^{-ip\cdot x}$, so the support lies in the future cone. If a source uses $x_{j+1}-x_j$ or the opposite Fourier phase, the displayed cone may appear with the opposite sign.

## Why the cone is stable under multiparticle sums

The future cone is convex. If $p,q\in\overline V_+$, then

$$
p+q\in\overline V_+.
$$

This is why the total momentum of a multiparticle state remains allowed. For ordinary massive particles,

$$
p_i^2=m_i^2\ge0,
\qquad
p_i^0\ge0,
$$

so the total momentum

$$
P_{\mathrm{tot}}=p_1+\cdots+p_N
$$

also lies in $\overline V_+$. Interactions can turn sharp sums of particle momenta into continuous spectral regions, but they do not change the future-cone constraint.

This convexity is also what makes the spectral condition compatible with local field products. Field polynomials acting on the vacuum can create states with total momentum in the cone, and further products still respect the same one-sided support.

## The two-point function and Källén–Lehmann positivity

For a scalar field, the two-point Wightman distribution has the form

$$
W_2(x-y)=\langle\Omega,\phi(x)\phi(y)\Omega\rangle.
$$

The spectral condition says

$$
\operatorname{supp}\widetilde W_2
\subset \overline V_+.
$$

If the theory is Lorentz invariant and the field is scalar, the two-point function can be decomposed spectrally as

$$
W_2(x)
=
\int_0^\infty d\mu^2\,\rho(\mu^2)\,
\Delta_+(x;\mu^2),
$$

where $\rho$ is a positive spectral measure and

$$
\Delta_+(x;\mu^2)
=
\int\frac{d^dp}{(2\pi)^{d-1}}
\theta(p^0)\delta(p^2-\mu^2)e^{-ip\cdot x}.
$$

This is the Källén–Lehmann picture. It says that the exact two-point function is a positive superposition of free positive-frequency two-point functions. An isolated atom of $\rho$ at $\mu^2=m^2$ corresponds to a stable one-particle mass shell. Continuous parts of $\rho$ describe multiparticle or continuum contributions.

The spectral measure is not determined by the spectral condition alone. Dynamics determines $\rho$. The axiom determines where its support is allowed to live and how positivity constrains it.

## Analyticity from positive energy

The one-sided Fourier support gives analytic continuation. For the two-point function, suppose schematically that

$$
W_2(\xi)=\int_{\overline V_+} d\sigma(p)\,e^{-ip\cdot\xi}.
$$

Replace the real variable by

$$
z=\xi-i\eta,
\qquad
\eta\in V_+.
$$

Then

$$
e^{-ip\cdot z}
=
e^{-ip\cdot\xi}e^{-p\cdot\eta}.
$$

For $p\in\overline V_+$ and $\eta\in V_+$, one has $p\cdot\eta\ge0$. The exponential factor therefore damps the Fourier integral or distributional pairing. This is the basic reason Wightman functions are boundary values of analytic functions in tube domains.

For $n$-point functions, the corresponding tube is

$$
\mathcal T_{n-1}
=
\{(z_1,\ldots,z_{n-1}):
 z_j=\xi_j-i\eta_j,
\ \eta_j\in V_+\}.
$$

The analytic function in this tube has the original Wightman distribution as a boundary value as $\eta_j\downarrow0$. Locality then extends this analyticity to larger domains after complex Lorentz transformations. Those enlarged domains are part of the route to the CPT and spin–statistics theorems.

## Relation to particles and mass gaps

The spectral condition is weaker than a particle interpretation. It allows several possibilities.

| Spectral feature | Meaning | Extra hypothesis? |
|---|---|---|
| Isolated vacuum at $0$ | Unique stable vacuum. | Often assumed separately. |
| Mass gap | No spectrum between $0$ and positive mass $m$. | Yes. |
| One-particle shell | Stable particle species. | Yes. |
| Multiparticle continuum | Sums and interactions of excitations. | Common but dynamical. |
| Massless continuum | Photons, Goldstone modes, or conformal behavior. | Model-dependent. |
| Infraparticle behavior | Charged sectors without sharp mass hyperbolae. | Beyond simplest Wigner-particle picture. |

The axiom says all of these must live in $\overline V_+$. It does not promise that a theory has particles, scattering states, or a mass gap.

## Checks in basic examples

For the free massive scalar field,

$$
\widetilde W_2(p)
=2\pi\theta(p^0)\delta(p^2-m^2)
$$

up to the normalization convention for Fourier transforms. Its support is the positive-energy mass shell, which lies in $\overline V_+$.

For a generalized free scalar field,

$$
\widetilde W_2(p)
=2\pi\theta(p^0)\rho(p^2),
$$

where $\rho$ is a positive measure supported on $p^2\ge0$. The support is again inside $\overline V_+$. This example is important because it satisfies many structural axioms while showing that the axioms alone do not force a theory to come from a familiar Lagrangian.

For a theory with a unique vacuum and a mass gap, the spectral picture is schematically

$$
\operatorname{Spec}(P)
=
\{0\}
\cup
\text{massive excitations in }\overline V_+.
$$

The exact positions and multiplicities of shells and continua are dynamical information, not convention.

## Common pitfalls

**Thinking $H\ge0$ is the whole condition.** Positive Hamiltonian is necessary, but the Wightman condition is a joint spectral statement for energy and momentum.

**Confusing the spectral condition with a mass gap.** A massless free scalar satisfies the spectral condition but has no mass gap.

**Assuming the spectrum must be a union of mass shells.** Interacting theories can have continua and thresholds. The spectral condition constrains their location, not their detailed shape.

**Ignoring Fourier-sign conventions.** The cone in the support statement depends on whether one writes $x_j-x_{j+1}$ or $x_{j+1}-x_j$, and on the Fourier phase. Translate before comparing formulas.

**Using gauge-fixed auxiliary spaces too literally.** Ghost fields or indefinite-metric spaces may have formal energy-momentum properties, but the Wightman axiom is about the physical positive Hilbert space or a framework replacing it.

## Relations to other pages

[Poincaré Covariance](/rigorous-qft/wightman-axiomatic-qft/poincare-covariance/) explains the unitary representation whose translation generators appear here.

[Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/) combines with the spectral condition to produce strong analytic and structural consequences.

The future Wightman Functions page will use the support condition directly in momentum-space statements.

The future Reconstruction Theorem page reverses the logic: suitable distributions with spectral support and positivity reconstruct the Hilbert space and fields.

The later Haag–Ruelle Scattering page will add mass-gap and isolated-shell hypotheses to build scattering states.

## Research status

The spectral condition is a settled part of Wightman and algebraic formulations of relativistic QFT. Its consequences for analyticity, CPT, spin–statistics, and scattering theory are classical theorem-level material.

What remains hard is not the statement of the axiom but the construction and interpretation of models satisfying it. Four-dimensional interacting gauge theories, charged sectors in theories with massless gauge bosons, confinement, and infraparticles all require care. In many of these settings the spectral condition survives, but the simple particle-spectrum intuition has to be replaced by local-algebra, sector, or inclusive-observable language.

## Exercises

### Exercise 1: Convexity of the future cone

Show that if $p,q\in\overline V_+$, then $p+q\in\overline V_+$.

<details><summary><strong>Solution</strong></summary>

The time component is immediate:

$$
(p+q)^0=p^0+q^0\ge0.
$$

For future-directed causal vectors in mostly-minus signature, $p\cdot q\ge0$. Therefore

$$
(p+q)^2=p^2+q^2+2p\cdot q\ge0.
$$

Hence $p+q\in\overline V_+$. Geometrically, the closed future cone is a convex cone.

</details>

### Exercise 2: Free scalar support

For a free scalar two-point function with

$$
\widetilde W_2(p)=2\pi\theta(p^0)\delta(p^2-m^2),
\qquad m^2\ge0,
$$

verify the spectral condition.

<details><summary><strong>Solution</strong></summary>

The delta function restricts the support to $p^2=m^2\ge0$. The step function restricts it to $p^0\ge0$. These two conditions are precisely

$$
p\in\overline V_+.
$$

Thus $\operatorname{supp}\widetilde W_2\subset\overline V_+$.

</details>

### Exercise 3: Why the tube uses negative imaginary part

Suppose

$$
W(\xi)=\int_{\overline V_+}d\sigma(p)\,e^{-ip\cdot\xi}.
$$

Explain why the analytic continuation naturally uses $z=\xi-i\eta$ with $\eta\in V_+$ rather than $z=\xi+i\eta$.

<details><summary><strong>Solution</strong></summary>

For $z=\xi-i\eta$,

$$
e^{-ip\cdot z}
=e^{-ip\cdot\xi}e^{-p\cdot\eta}.
$$

Since $p\in\overline V_+$ and $\eta\in V_+$ imply $p\cdot\eta\ge0$, the factor $e^{-p\cdot\eta}$ damps the integral. With $z=\xi+i\eta$, the factor would be $e^{+p\cdot\eta}$, which grows rather than damps. The sign is tied to the Fourier convention $e^{-ip\cdot x}$.

</details>

## References

### Standard first pass

- A. S. Wightman, "Quantum Field Theory in Terms of Vacuum Expectation Values," *Physical Review* **101** (1956), 860–866. DOI: [10.1103/PhysRev.101.860](https://doi.org/10.1103/PhysRev.101.860).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- R. Jost, *The General Theory of Quantized Fields*, American Mathematical Society, 1965.

### Spectral and analytic background

- R. Haag, *Local Quantum Physics: Fields, Particles, Algebras*, Springer. DOI: [10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- H. Lehmann, "Über Eigenschaften von Ausbreitungsfunktionen und Renormierungskonstanten quantisierter Felder," *Il Nuovo Cimento* **11** (1954), 342–357. DOI: [10.1007/BF02783624](https://doi.org/10.1007/BF02783624).
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics I: Functional Analysis*, Academic Press.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics II: Fourier Analysis, Self-Adjointness*, Academic Press.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).

## Version history

- **2026-06-28:** Initial polished draft.
