---
title: "Lattice Regularization Preview"
description: "How lattice regularization replaces continuum fields by variables on a spacetime grid, why it gives a nonperturbative cutoff, and what the continuum limit means."
sidebar:
  label: "Lattice Regularization Preview"
  order: 4
level: Graduate
status: "Polished draft"
source: "Wilson 1974; Wilson and Kogut 1974; Srednicki §82; Zee ch. VII.1; Schwartz chs. 23 and 25; Zinn-Justin, lattice regularization chapters; Altland and Simons 2023, chs. 3, 6, 9, and 10."
topics:
  - lattice regularization
  - continuum limit
  - Wilson action
  - Brillouin zone
  - fermion doubling
canonicalTopics:
  - lattice-regularization
  - continuum-limit
  - lattice-cutoff
  - wilson-action
  - fermion-doubling
researchStatus:
  established:
    - "Lattice regularization gives a finite-cutoff definition of many Euclidean QFTs and is the standard nonperturbative regulator for gauge theories."
  active:
    - "Chiral gauge theories, real-time dynamics, finite-density sign problems, continuum extrapolations, and quantum-simulation approaches remain active research areas."
---

## Summary

**Lattice regularization** replaces continuum spacetime by a grid with spacing $a$. In finite volume, a field theory path integral becomes an ordinary high-dimensional integral or sum. The lattice spacing acts as a short-distance cutoff,

$$
\Lambda_{\text{lat}}\sim \frac{\pi}{a},
$$

because lattice momenta live in a Brillouin zone rather than in all of $\mathbb R^d$.

For a scalar field on a hypercubic Euclidean lattice, the continuum action

$$
S_E=\int d^d x\,
\left[\frac12(\partial_\mu\phi)^2+\frac12m^2\phi^2+\frac{\lambda}{4!}\phi^4\right]
$$

is replaced by a lattice action such as

$$
S_a=a^d\sum_n
\left[
\frac12\sum_\mu
\left(\frac{\phi_{n+\hat\mu}-\phi_n}{a}\right)^2
+\frac12m_0^2\phi_n^2
+\frac{\lambda_0}{4!}\phi_n^4
\right].
$$

At finite $a$, this is a regulator. To recover a continuum QFT, one takes $a\to0$ while tuning bare parameters so that physical quantities remain fixed. Equivalently, the correlation length in lattice units must diverge:

$$
\frac{\xi}{a}\longrightarrow\infty.
$$

Lattice regularization is more than a perturbative trick. It can define QFT nonperturbatively. It is the natural home of Wilson's formulation of gauge theory, where gauge fields live on links and gauge-invariant dynamics are built from plaquettes.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Lattice regularization introduces a grid spacing a, a Brillouin-zone cutoff pi over a, and a continuum window a much smaller than physical distances much smaller than the correlation length](/figures/renormalization-rg-eft/lattice-continuum-window.svg)

<figcaption>

A lattice regulator replaces continuum spacetime by a grid with spacing $a$, so momenta are bounded by a Brillouin-zone scale of order $\pi/a$. Continuum physics is extracted from the window $a\ll r\ll \xi$, or equivalently $1/\xi\ll p\ll 1/a$. The continuum limit sends $a\to0$ while holding physical scales fixed, so $\xi/a\to\infty$.

</figcaption>
</figure>

## Prerequisites

You should know [Cutoff Regularization](/renormalization-rg-eft/regularization-counterterms/cutoff-regularization/), [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/), and [Pauli–Villars Regularization](/renormalization-rg-eft/regularization-counterterms/pauli-villars-regularization/) as three continuum regulator languages. You should also know the basic Wilsonian idea that changing the short-distance description changes local couplings but should not change long-distance physics when the theory is tuned consistently.

This page is a preview. It explains the conceptual role of the lattice inside the Renormalization, RG, and EFT volume. Detailed lattice Monte Carlo algorithms, lattice gauge theory practice, fermion discretizations, scale setting, and continuum extrapolation belong in the Nonperturbative QFT and Computational QFT volumes.

## Core idea

A lattice regulator makes the short-distance structure explicit. Instead of asking what a field $\phi(x)$ does at arbitrarily close points, one defines variables $\phi_n$ at lattice sites

$$
x_n=a n,
\qquad n\in\mathbb Z^d,
$$

and replaces derivatives by finite differences. The ultraviolet problem is softened because the theory no longer has independent degrees of freedom at distances shorter than $a$.

The conceptual difference from a hard momentum cutoff is important. A hard cutoff modifies the momentum integration region but leaves spacetime formally continuous. A lattice modifies spacetime itself, replacing continuous translation and rotation symmetry by a discrete subgroup. A continuum theory can emerge only if those broken spacetime symmetries are restored as $a\to0$.

The practical power is enormous. At finite lattice spacing and finite volume, many Euclidean QFTs are honest finite-dimensional statistical systems:

$$
Z_a=\int\prod_n d\phi_n\,e^{-S_a[\phi]}.
$$

This expression is not a formal oscillatory Lorentzian path integral. It is a Euclidean statistical weight, suitable for nonperturbative definitions and, when the weight is positive, numerical sampling.

## Setup and conventions

We work in Euclidean signature on a $d$-dimensional hypercubic lattice. The lattice spacing is $a$. The lattice sites are

$$
x_n=a n,
\qquad n=(n_1,\ldots,n_d).
$$

A finite box with $N$ sites in each direction has physical size

$$
L=N a.
$$

The continuum integral is replaced by

$$
\int d^d x\,f(x)
\quad\longrightarrow\quad
 a^d\sum_n f_n.
$$

A forward finite difference is

$$
\partial_\mu\phi(x)
\quad\longrightarrow\quad
\nabla_\mu^+\phi_n
\equiv
\frac{\phi_{n+\hat\mu}-\phi_n}{a}.
$$

A symmetric difference is

$$
\nabla_\mu^{\text{sym}}\phi_n
\equiv
\frac{\phi_{n+\hat\mu}-\phi_{n-\hat\mu}}{2a}.
$$

Different choices agree in the continuum limit but differ at finite $a$. Those finite-$a$ differences are not mistakes. They are different regulator choices, usually differing by irrelevant operators.

## Scalar field on a lattice

A common Euclidean lattice action for scalar $\phi^4$ theory is

$$
S_a=a^d\sum_n
\left[
\frac12\sum_\mu
\left(\frac{\phi_{n+\hat\mu}-\phi_n}{a}\right)^2
+\frac12m_0^2\phi_n^2
+\frac{\lambda_0}{4!}\phi_n^4
\right].
$$

Here $m_0^2$ and $\lambda_0$ are bare lattice parameters. They depend on $a$ if the continuum physics is to be held fixed.

The free lattice action can be diagonalized in momentum space. For a periodic lattice, momenta lie in the Brillouin zone

$$
-\frac{\pi}{a}<p_\mu\le \frac{\pi}{a}.
$$

The lattice kinetic term gives

$$
\hat p^2
=\frac{4}{a^2}\sum_\mu\sin^2\frac{a p_\mu}{2}.
$$

Thus the free lattice propagator is

$$
G_a(p)=\frac{1}{\hat p^2+m_0^2}.
$$

For small lattice momentum $a|p|\ll1$,

$$
\hat p^2=p^2+O(a^2p^4),
$$

so the continuum propagator is recovered at long distances. For momenta near the edge of the Brillouin zone, the theory differs strongly from the continuum. That difference is the UV regulator.

## The Brillouin zone as a cutoff

The lattice does not simply impose $|p|<\pi/a$ in a rotationally invariant way. It replaces momentum space by a periodic Brillouin zone. For a hypercubic lattice,

$$
p_\mu\sim p_\mu+\frac{2\pi}{a}.
$$

The UV cutoff is therefore not a sphere but a compact momentum torus with hypercubic symmetry. Continuous rotation symmetry is broken at finite $a$. The small-momentum expansion

$$
\hat p^2=p^2-\frac{a^2}{12}\sum_\mu p_\mu^4+O(a^4p^6)
$$

shows how the violation enters: finite-$a$ corrections are higher-derivative operators that vanish as $a\to0$ for fixed physical momentum.

This is the lattice version of a general Wilsonian lesson. Different short-distance regulators produce different irrelevant operators. The continuum limit is universal only after one identifies which parameters must be tuned and which corrections vanish.

## Continuum limit

The continuum limit is not merely the phrase "take $a\to0$." One must specify what is held fixed.

Let $m_{\text{phys}}$ be a physical mass. The dimensionless lattice mass is

$$
am_{\text{phys}}.
$$

Taking the continuum limit at fixed $m_{\text{phys}}$ requires

$$
am_{\text{phys}}\to0.
$$

Since the physical correlation length is $\xi=1/m_{\text{phys}}$, this is equivalent to

$$
\frac{\xi}{a}\to\infty.
$$

Thus a continuum QFT appears near a critical point of the lattice statistical system. The lattice spacing becomes much shorter than the physical correlation length, and the long-distance observer cannot see the grid.

In scalar theory, this typically requires tuning the bare mass parameter toward a critical value:

$$
m_0^2\to m_{0,c}^2(\lambda_0).
$$

In an asymptotically free gauge theory, the continuum limit is approached as the bare gauge coupling goes to zero in a controlled way:

$$
g_0(a)\to0
\qquad \text{as}\qquad a\to0,
$$

while a physical scale such as $\Lambda_{\text{QCD}}$ or a string tension is held fixed.

The continuum limit is therefore an RG statement. A continuum QFT is a scaling limit of a lattice model, not simply a fine mesh drawing of a continuum formula.

## Gauge fields on links

The lattice formulation of gauge theory is one of the great ideas of modern QFT. A continuum gauge field is not placed directly on sites. Instead, the fundamental lattice variables are group elements on links:

$$
U_{n,\mu}\in G.
$$

For small lattice spacing, one may think schematically of

$$
U_{n,\mu}\approx \exp\left(iag_0 A_\mu(n+\tfrac12\hat\mu)\right),
$$

where $A_\mu$ is the continuum gauge field. Under a lattice gauge transformation $\Omega_n\in G$,

$$
U_{n,\mu}\longrightarrow
\Omega_n U_{n,\mu}\Omega_{n+\hat\mu}^{-1}.
$$

The elementary gauge-invariant object is the plaquette,

$$
U_{n,\mu\nu}
=U_{n,\mu}
U_{n+\hat\mu,\nu}
U_{n+\hat\nu,\mu}^{-1}
U_{n,\nu}^{-1}.
$$

For small $a$,

$$
U_{n,\mu\nu}
\approx
\exp\left(ia^2g_0F_{\mu\nu}(n)\right).
$$

For $G=SU(N)$, the Wilson gauge action is commonly written as

$$
S_W=\frac{\beta}{N}\sum_{n,\mu<\nu}
\operatorname{Re}\operatorname{tr}\left[\mathbf 1-U_{n,\mu\nu}\right],
\qquad
\beta=\frac{2N}{g_0^2},
$$

up to convention-dependent normalizations of generators and traces. Expanding the plaquette for small $a$ gives the continuum Yang–Mills action.

The beauty of this formulation is that local gauge invariance is exact at finite $a$. There is no need to gauge-fix in order to define the Euclidean path integral for gauge-invariant observables. The gauge-field integration is over compact group variables with Haar measure:

$$
Z=\int\prod_{n,\mu} dU_{n,\mu}\,e^{-S_W[U]}.
$$

## Wilson loops and confinement preview

Lattice gauge theory also gives a natural definition of Wilson loops. For a closed lattice path $C$,

$$
W(C)=\operatorname{tr}\prod_{\ell\in C}U_\ell,
$$

with the product ordered along the path. This is the lattice version of

$$
\operatorname{tr}\,P\exp\left(i\oint_C dx^\mu A_\mu\right).
$$

In a confining gauge theory, large rectangular Wilson loops behave like

$$
\langle W(R,T)\rangle\sim e^{-\sigma R T}
$$

for large $R$ and $T$, where $\sigma$ is the string tension. The exponent is proportional to the area $RT$, hence the name **area law**. Comparing with

$$
\langle W(R,T)\rangle\sim e^{-V(R)T}
$$

suggests a linear potential

$$
V(R)\sim \sigma R.
$$

This page only previews that logic. The full story of confinement belongs in Nonperturbative QFT and Gauge Theories and the Standard Model. Here the point is that lattice regularization makes such questions meaningful without expanding around weak coupling.

## Fermions and doubling

Fermions on the lattice are subtle. A naive symmetric derivative gives

$$
\partial_\mu\psi(x)
\quad\longrightarrow\quad
\frac{\psi_{n+\hat\mu}-\psi_{n-\hat\mu}}{2a},
$$

which in momentum space becomes

$$
p_\mu\quad\longrightarrow\quad
\frac{1}{a}\sin(ap_\mu).
$$

The sine function vanishes not only at $p_\mu=0$, but also at the edges of the Brillouin zone. In $d$ dimensions, the naive lattice Dirac operator therefore has extra low-energy zeros. These are the famous **fermion doublers**.

The doubling problem is not a harmless detail. It is tied to chirality, locality, translation invariance, and the topology of the Brillouin zone. Common fermion discretizations make different compromises:

| Formulation | Basic idea | Tradeoff |
|---|---|---|
| Wilson fermions | add a lattice irrelevant term that lifts doublers | explicitly breaks chiral symmetry at finite $a$ |
| Staggered fermions | reduce the number of doublers by distributing spin components | leaves residual tastes and requires care |
| Domain-wall fermions | realize chiral modes on higher-dimensional defects | computationally more expensive |
| Overlap fermions | satisfy a lattice version of chiral symmetry | elegant but expensive |

This is one reason lattice regularization is a preview here rather than a one-page complete subject. The lattice is simple to define for scalars, beautiful for gauge fields, and technically deep for fermions.

## What lattice regularization preserves and breaks

At finite lattice spacing, the regulator preserves some structures and breaks others.

| Structure | Lattice behavior |
|---|---|
| locality | preserved if action couples nearby sites or decays rapidly |
| Euclidean translations | reduced to discrete translations |
| rotations | reduced to hypercubic rotations |
| Lorentz symmetry | not manifest; recovered after Euclidean continuum limit if the theory is tuned correctly |
| internal global symmetries | can often be preserved exactly |
| gauge invariance | can be preserved exactly with link variables |
| chiral symmetry | subtle for fermions |
| reflection positivity | must be checked; important for reconstructing unitary Lorentzian QFT |
| unitarity | not manifest in Euclidean form; recovered after analytic continuation when conditions hold |

A regulator that breaks a symmetry can still be acceptable if the symmetry is restored in the continuum limit without forbidden fine-tuning. But if the broken symmetry forbids relevant or marginal operators, losing it can make the continuum limit much harder. This is why exact lattice gauge invariance is so powerful.

## Regulator lattice versus physical lattice

The word lattice appears in two different physical contexts.

In high-energy lattice field theory, the lattice is usually a regulator. The continuum limit is part of the definition of the desired QFT. The spacing $a$ is sent to zero and should not appear in final physical predictions.

In condensed matter physics, the lattice may be real: ions sit in a crystal, spins live on sites, and the Brillouin zone is physical. In that case one may still take a continuum limit to describe long-wavelength collective behavior, but the microscopic lattice is not a fake regulator. It is part of the material.

The same RG language covers both cases. Long-distance universality can make many microscopic lattices flow to the same continuum field theory. But the interpretation of $a$ differs:

| Context | Meaning of $a$ |
|---|---|
| regulator lattice | artificial cutoff to be removed |
| crystal lattice | physical microscopic spacing |
| statistical lattice model | microscopic definition whose critical scaling limit may be a continuum QFT |

This distinction prevents a common confusion: lattice regularization does not say spacetime is literally a grid. It says a grid can define or regulate the field theory whose continuum limit is being studied.

## Lattice artifacts and improvement

Finite-$a$ calculations contain lattice artifacts. For a scalar action using nearest-neighbor differences,

$$
\hat p^2=p^2-\frac{a^2}{12}\sum_\mu p_\mu^4+O(a^4p^6),
$$

so the leading errors are often $O(a^2)$ for sufficiently symmetric bosonic actions. Other discretizations may have $O(a)$ errors. The Symanzik improvement program interprets lattice artifacts as higher-dimension operators in an effective continuum action:

$$
S_a
\sim
S_{\text{cont}}
+a\sum_i c_i^{(5)}\int d^d x\,\mathcal O_i^{(5)}
+a^2\sum_i c_i^{(6)}\int d^d x\,\mathcal O_i^{(6)}+\cdots.
$$

By adding carefully chosen irrelevant operators to the lattice action, one can cancel leading artifacts and approach the continuum faster. This is EFT logic applied to the regulator itself.

## Relation to Wilsonian renormalization

Lattice regularization and Wilsonian RG are natural partners. A lattice action is a point in a large space of possible local actions. Blocking or coarse-graining maps one lattice action to another with a larger effective spacing. A continuum limit corresponds to approaching an RG fixed point or critical surface such that the correlation length in lattice units diverges.

Schematically,

$$
\text{lattice action at }a
\quad\longrightarrow\quad
\text{blocked action at }ba
\quad\longrightarrow\quad
\text{RG flow in theory space}.
$$

Relevant operators must be tuned to reach a chosen continuum theory. Irrelevant operators determine lattice artifacts but not the universal long-distance limit. Marginal operators require beta-function analysis.

This is the conceptual reason lattice regularization belongs in this volume: it is not only a numerical method. It is one of the clearest concrete realizations of theory space, scaling limits, fixed points, and universality.

## Comparison with other regulators

| Regulator | What it changes | Main advantage | Main caveat |
|---|---|---|---|
| hard cutoff | integration region | direct UV scale | often breaks Lorentz/gauge symmetry |
| dimensional regularization | spacetime dimension | efficient and symmetry-friendly | hides power sensitivity; subtle for $\gamma^5$ |
| Pauli–Villars | adds heavy subtractions | Lorentz-covariant and intuitive | wrong-sign fields; chiral/gauge subtleties |
| lattice | short-distance spacetime structure | nonperturbative definition; exact gauge invariance possible | breaks continuous spacetime symmetries; fermions and continuum extrapolation are subtle |

A mature calculation chooses a regulator because it fits the question. For perturbative multi-loop QCD, dimensional regularization is usually the efficient language. For nonperturbative confinement, lattice regularization is the natural language. For anomaly pedagogy, Pauli–Villars can be revealing. For Wilsonian intuition, a cutoff is often clearest.

## Common pitfalls

**Thinking a lattice is just a hard cutoff.** The lattice imposes a compact Brillouin zone and changes derivatives into finite differences. It breaks continuous rotations at finite $a$ and introduces lattice artifacts.

**Taking $a\to0$ without tuning.** The continuum limit requires keeping physical quantities fixed. Usually this means tuning bare parameters toward a critical surface.

**Confusing finite volume with finite lattice spacing.** A calculation has both IR and UV regulators: $L=Na$ controls volume, while $a$ controls short distances. One usually needs both $L\to\infty$ and $a\to0$ extrapolations.

**Assuming exact gauge invariance means no renormalization.** Lattice gauge invariance restricts counterterms powerfully, but couplings still run and continuum limits still require RG analysis.

**Ignoring fermion doubling.** Naive lattice fermions do not produce a single continuum Dirac fermion. Chiral fermions are among the deepest parts of lattice field theory.

**Treating Euclidean positivity as automatic.** A Euclidean lattice action suitable for Monte Carlo does not automatically reconstruct a unitary Lorentzian QFT. Reflection positivity and analytic continuation matter.

**Believing lattice data are automatically continuum predictions.** A finite lattice calculation must control statistical errors, finite-volume effects, lattice-spacing artifacts, scale setting, and continuum extrapolation.

## Relations to other pages

This page completes the first regulator quartet in the Regularization and Counterterms chapter: [Cutoff Regularization](/renormalization-rg-eft/regularization-counterterms/cutoff-regularization/), [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/), [Pauli–Villars Regularization](/renormalization-rg-eft/regularization-counterterms/pauli-villars-regularization/), and lattice regularization.

The next page, [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), explains how regulator-dependent local terms are absorbed into the action. [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/) explains which counterterms are needed. Later chapters on Wilsonian Renormalization and Fixed Points and Critical Phenomena will return to the lattice as a concrete model of RG flow.

For full lattice gauge theory, Wilson loops, confinement, numerical Monte Carlo, and fermion discretizations, this page should be read as an entry ramp, not the destination.

## Research status

Lattice regularization is established and indispensable. It gives the standard nonperturbative formulation of QCD and many statistical/QFT continuum limits. It is also a conceptual foundation for Wilsonian RG and universality.

The active frontier is large: chiral gauge theories on the lattice, finite-density sign problems, real-time dynamics, quantum simulation, tensor-network alternatives, improved actions, multi-scale algorithms, topological terms, chiral fermions, and precision continuum extrapolations remain lively research areas.

## Exercises

### Exercise 1: Continuum limit of the lattice kinetic term

Show that

$$
\hat p^2=\frac{4}{a^2}\sum_\mu\sin^2\frac{ap_\mu}{2}
$$

satisfies $\hat p^2=p^2+O(a^2p^4)$ for $a|p|\ll1$.

<details><summary><strong>Solution</strong></summary>

Use

$$
\sin z=z-\frac{z^3}{6}+O(z^5).
$$

Then

$$
\sin^2\frac{ap_\mu}{2}
=\frac{a^2p_\mu^2}{4}-\frac{a^4p_\mu^4}{48}+O(a^6p_\mu^6).
$$

Multiplying by $4/a^2$ and summing gives

$$
\hat p^2
=\sum_\mu p_\mu^2-\frac{a^2}{12}\sum_\mu p_\mu^4+O(a^4p^6).
$$

Thus $\hat p^2=p^2+O(a^2p^4)$.

</details>

### Exercise 2: Correlation length in lattice units

Suppose a lattice theory has a physical mass $m_{\text{phys}}$ held fixed while $a\to0$. Show that the correlation length in lattice units diverges.

<details><summary><strong>Solution</strong></summary>

The physical correlation length is

$$
\xi=\frac{1}{m_{\text{phys}}}.
$$

The dimensionless correlation length measured in lattice spacings is

$$
\frac{\xi}{a}=\frac{1}{a m_{\text{phys}}}.
$$

If $m_{\text{phys}}$ is fixed and $a\to0$, then $a m_{\text{phys}}\to0$ and therefore

$$
\frac{\xi}{a}\to\infty.
$$

This is why the continuum limit is a critical scaling limit.

</details>

### Exercise 3: Gauge covariance of a link variable

Let a lattice matter field transform as $\psi_n\to\Omega_n\psi_n$ and a link transform as

$$
U_{n,\mu}\to\Omega_nU_{n,\mu}\Omega_{n+\hat\mu}^{-1}.
$$

Show that $U_{n,\mu}\psi_{n+\hat\mu}$ transforms like a field at site $n$.

<details><summary><strong>Solution</strong></summary>

Under the gauge transformation,

$$
U_{n,\mu}\psi_{n+\hat\mu}
\to
\Omega_nU_{n,\mu}\Omega_{n+\hat\mu}^{-1}\Omega_{n+\hat\mu}\psi_{n+\hat\mu}.
$$

The two middle factors cancel, giving

$$
U_{n,\mu}\psi_{n+\hat\mu}
\to
\Omega_nU_{n,\mu}\psi_{n+\hat\mu}.
$$

This is the same transformation law as $\psi_n$. Therefore the link variable parallel-transports the neighboring field back to site $n$.

</details>

### Exercise 4: Why naive fermions double

In one lattice dimension, the naive derivative gives momentum factor $a^{-1}\sin(ap)$. Where are its zeros in the Brillouin zone $-\pi/a<p\le\pi/a$?

<details><summary><strong>Solution</strong></summary>

The zeros of $\sin(ap)$ occur when

$$
ap=0,\ \pm\pi,\ \pm2\pi,\ldots.
$$

Inside the Brillouin zone $-\pi/a<p\le\pi/a$, the relevant zeros are

$$
p=0,
\qquad
p=\pi/a
$$

with $p=-\pi/a$ identified with the zone edge by periodicity. Near each zero, the dispersion is linear. Thus the lattice derivative produces two low-energy species in one dimension. In $d$ dimensions, the analogous naive construction gives zeros at every corner of the Brillouin zone, producing $2^d$ species.

</details>

## References

- Kenneth G. Wilson, "Confinement of Quarks," *Physical Review D* **10** (1974) 2445.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Mark Srednicki, *Quantum Field Theory*, especially the section on Wilson loops, lattice theory, and confinement.
- A. Zee, *Quantum Field Theory in a Nutshell*, especially the introduction to lattice Yang–Mills theory and Wilson loops.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the discussions of Wilsonian RG and lattice gauge theory.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the sections on lattice regularization, continuum limits, and statistical field theory.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially the discussions of continuum limits, RG, Dirac fermions on lattices, and lattice gauge theory.

## Version history

- 2026-06-17: First polished draft. Introduced lattice spacing as a UV cutoff, scalar lattice action, Brillouin-zone propagator, continuum limit, gauge links, plaquettes, Wilson loops, fermion doubling, and lattice artifacts.
