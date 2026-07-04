---
title: "Ultraviolet Cutoffs"
description: "Explains the main ultraviolet regularizations used to make Euclidean field measures finite before renormalized continuum limits are taken."
sidebar:
  label: "Ultraviolet Cutoffs"
  order: 6
level: Graduate
status: "Polished draft"
source: "Wilson–Kogut RG; Glimm–Jaffe constructive QFT; Simon functional integration; Osterwalder–Schrader Euclidean QFT."
topics:
  - ultraviolet cutoffs
  - regularization
  - renormalization
  - cutoff measures
  - lattice regularization
  - covariance cutoffs
canonicalTopics:
  - ultraviolet-cutoff
  - regularized-measure
  - lattice-cutoff
  - covariance-cutoff
  - renormalization
researchStatus:
  established:
    - "Finite-volume and ultraviolet-regularized Euclidean field models can often be defined as honest finite-dimensional or smooth random-field measures."
  active:
    - "The existence, nontriviality, universality, and Osterwalder–Schrader properties of cutoff-removed limits are model-dependent constructive questions."
---

## Summary

An ultraviolet cutoff removes the short-distance modes that make local field expressions singular. With a cutoff in place, the field may be a smooth random function, a finite collection of lattice variables, or a finite-mode random vector. The cutoff theory is not the final continuum QFT; it is a controlled approximation from which one tries to take a renormalized limit.

A typical regularized covariance is

$$
\widehat C_\kappa(p)
=
\frac{\chi(p^2/\kappa^2)}{p^2+m^2},
$$

where $\chi$ suppresses momenta $|p|\gg\kappa$. The regularized field then has finite point variance

$$
C_\kappa(x,x)
=
\int\frac{d^dp}{(2\pi)^d}
\frac{\chi(p^2/\kappa^2)}{p^2+m^2},
$$

for fixed $\kappa$. This makes local expressions such as $\phi_\kappa(x)^4$ meaningful before the limit $\kappa\to\infty$ is attempted.

The central lesson is that a cutoff is part of a construction, not an embarrassment to erase from notation. The hard theorem is not that the cutoff model exists; the hard theorem is that, after adding the correct counterterms, the cutoff can be removed and the resulting Schwinger functions define the same continuum theory independent of regulator details.

## Prerequisites

You should know [Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/), [Euclidean Action as Density](/rigorous-qft/path-integrals-as-measures/euclidean-action-as-density/), and [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/). Reflection positivity is explained in [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/).

## Core idea

A continuum free field is usually distribution-valued. Products at the same point are not automatically defined. In a Gaussian scalar theory,

$$
\mathbb E[\phi(x)^2]
\quad\text{is represented formally by}\quad
C(x,x),
$$

and $C(x,x)$ is typically divergent. A UV cutoff replaces the singular continuum object by a regularized one. Then one defines the interacting theory at cutoff, studies its dependence on the cutoff, and renormalizes.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A map of ultraviolet cutoff choices and the renormalized continuum limit problem.](/figures/rigorous-qft/ultraviolet-cutoff-map.svg)

<figcaption>

A UV cutoff makes local field expressions meaningful by suppressing short-distance degrees of freedom. Renormalization chooses cutoff-dependent parameters so that Schwinger functions have a finite, nontrivial limit as the cutoff is removed.

</figcaption>
</figure>

The basic pattern is

$$
\text{singular continuum notation}
\longrightarrow
\text{cutoff measure}
\longrightarrow
\text{renormalized limit}.
$$

Only the middle term is easy in general.

## Setup and conventions

Let $\mu_C$ be a Gaussian free-field measure with covariance $C$. A UV cutoff replaces $C$ by a regularized covariance $C_\kappa$, or replaces the field space by a finite-dimensional approximation. The parameter $\kappa$ is a momentum scale; increasing $\kappa$ means resolving shorter distances. On a lattice, the corresponding parameter is the lattice spacing $a$, with $a\to 0$.

A scalar cutoff interaction in a finite Euclidean volume $\Omega$ often has the schematic form

$$
V_{\Omega,\kappa}(\phi)
=
\int_\Omega
U_\kappa\bigl(\phi_\kappa(x)\bigr)
\,d^dx,
$$

and the cutoff measure is

$$
d\mu_{\Omega,\kappa}(\phi)
=
Z_{\Omega,\kappa}^{-1}
\exp\bigl(-V_{\Omega,\kappa}(\phi)\bigr)
\,d\mu_{C_\kappa}(\phi).
$$

The interaction $U_\kappa$ may contain bare couplings and counterterms depending on $\kappa$. A finite volume $\Omega$ controls infrared behavior; it is not itself a UV cutoff.

## Why local products need cutoffs

Consider the massive free scalar covariance in $d$ Euclidean dimensions,

$$
C_m(x-y)
=
\int\frac{d^dp}{(2\pi)^d}
\frac{e^{ip\cdot(x-y)}}{p^2+m^2}.
$$

At coincident points, the formal variance is

$$
C_m(0)
=
\int\frac{d^dp}{(2\pi)^d}
\frac{1}{p^2+m^2}.
$$

For large $p$, the integrand behaves like $p^{-2}$, while the measure contributes $p^{d-1}dp$. Thus the large-momentum behavior is

$$
\int^{\infty} p^{d-3}\,dp,
$$

which diverges for $d\geq 2$. This is the elementary reason why the expression $\phi(x)^2$ is not a harmless random variable in the continuum free theory.

With a smooth cutoff,

$$
C_{m,\kappa}(0)
=
\int\frac{d^dp}{(2\pi)^d}
\frac{\chi(p^2/\kappa^2)}{p^2+m^2},
$$

is finite for fixed $\kappa$ if $\chi$ decays sufficiently fast. Local powers of $\phi_\kappa(x)$ then make sense. The divergence reappears as $\kappa\to\infty$ and must be handled by Wick ordering or counterterms.

## Common types of UV cutoff

### Mode or momentum cutoff

A momentum cutoff suppresses high Fourier modes:

$$
\widehat\phi_\kappa(p)=\chi(p^2/\kappa^2)\widehat\phi(p).
$$

It is convenient in perturbation theory and in translation-invariant Euclidean scalar models. A sharp cutoff is simple but can be unfriendly to locality or reflection positivity. A smooth cutoff is analytically nicer but still has to be checked against the structural properties one wants in the limit.

### Covariance cutoff

Instead of cutting the field directly, one replaces the covariance by

$$
C_\kappa=f_\kappa(-\Delta)C,
$$

or by a heat-kernel regularization such as

$$
C_\epsilon
=\int_\epsilon^\infty e^{-t(-\Delta+m^2)}\,dt.
$$

This is common in constructive and probabilistic treatments because the covariance determines the Gaussian reference measure. Heat-kernel cutoffs interact well with geometry, but again one must track reflection positivity and locality.

### Lattice cutoff

A lattice cutoff replaces spacetime by a lattice $a\mathbb Z^d$ in a finite box. The field becomes a finite family of random variables $\phi_x$, and a typical lattice action is

$$
S_{a,\Omega}(\phi)
=
a^d\sum_{x\in\Omega_a}
\left[
\frac12\sum_{\mu=1}^d
\left(\frac{\phi_{x+a\hat\mu}-\phi_x}{a}\right)^2
+U_a(\phi_x)
\right].
$$

For finite volume and finite lattice spacing, this is an ordinary finite-dimensional integral. Lattice cutoffs are especially important because some choices preserve reflection positivity and provide a transfer-matrix route to a Hilbert space. They usually break continuous rotations and translations, which must be recovered in the continuum limit.

### Spectral cutoff

On a compact Riemannian manifold, one may project to eigenfunctions of an elliptic operator with eigenvalues below $\kappa^2$. If

$$
-\Delta e_n=\lambda_n e_n,
$$

then a spectral cutoff keeps only modes with $\lambda_n\leq\kappa^2$. This is geometrically clean in finite volume, but it may be nonlocal in position space.

### Mollifier cutoff

A mollifier replaces $\phi(x)$ by the smeared variable

$$
\phi_\epsilon(x)=\phi(\rho_{\epsilon,x}),
$$

where $\rho_{\epsilon,x}$ is concentrated in a ball of radius $\epsilon$. This keeps the distributional nature of the underlying field visible. It is often the most transparent cutoff for explaining Wick powers.

## Counterterms are part of the cutoff family

A regulator alone rarely produces a finite interacting continuum limit. One must also tune parameters. For a scalar $\phi^4$ model, a schematic cutoff action might be

$$
V_{\Omega,\kappa}^{\rm ren}(\phi)
=
\int_\Omega
\left[
 g_\kappa\phi_\kappa(x)^4
+c_\kappa\phi_\kappa(x)^2
+e_\kappa
\right]d^dx.
$$

The coefficients $g_\kappa,c_\kappa,e_\kappa$ are not arbitrary decoration. They encode renormalization conditions. In two dimensions, Wick ordering removes the basic tadpole divergence in many scalar models. In three dimensions, additional mass and energy counterterms appear. In four dimensions, the situation is more delicate because nontrivial continuum limits of interacting scalar theories are constrained by triviality questions.

The right question is not "what is the cutoff action?" but

$$
\text{which cutoff-dependent family has a finite, nontrivial limit?}
$$

This question is one form of the renormalization problem.

## Cutoff removal

A useful continuum limit should say what converges. Possibilities include:

- smeared Schwinger functions $S^{(n)}_{\Omega,\kappa}(f_1,
  \ldots,f_n)$;
- characteristic functionals $\chi_{\Omega,\kappa}(f)$;
- probability measures on distribution spaces;
- connected correlation functions or cumulants;
- renormalized local composite fields.

For example, one may try to prove

$$
\lim_{\kappa\to\infty}\lim_{\Omega\nearrow\mathbb R^d}
S^{(n)}_{\Omega,\kappa}(f_1,
\ldots,f_n)
=
S^{(n)}(f_1,
\ldots,f_n).
$$

A theorem must also specify topology, order of limits or joint limiting procedure, and field-strength normalizations if needed. After convergence, the limiting functions must be checked against the Euclidean axioms: symmetry, Euclidean covariance, reflection positivity, regularity, and clustering.

## Regulator choice and universality

Different regulators can lead to the same continuum theory, but this is a theorem or a controlled expectation, not a slogan. Two cutoff schemes may differ at short distances while producing the same long-distance limit after their couplings are matched. This is the mathematical side of universality.

However, a bad regulator can obscure or break useful structures. A cutoff may violate reflection positivity, gauge invariance, locality, or Euclidean symmetry. Sometimes those violations are harmless if they disappear in the limit. Sometimes they make the construction much harder. In rigorous work, the regulator is chosen not only for convenience but also for the properties it preserves.

## Common pitfalls

**Confusing UV and IR cutoffs.** A finite volume is an infrared cutoff. It prevents large-distance problems. A UV cutoff prevents short-distance singularities. Most constructive problems need both at intermediate stages.

**Thinking the cutoff theory is the continuum theory.** A finite lattice or smooth cutoff model is an honest mathematical object, but it is not yet a continuum QFT. The continuum limit is a separate theorem.

**Using a regulator that destroys the property being proved.** For Osterwalder–Schrader reconstruction, reflection positivity matters. For gauge theory, gauge symmetry or a controlled substitute matters. Not every convenient cutoff preserves the structure one wants.

**Assuming counterterms are optional.** Counterterms are often required to keep physical quantities finite and nontrivial. Omitting them may produce divergent, trivial, or regulator-dependent limits.

**Expecting pointwise convergence of fields.** The natural convergence is usually distributional: smeared fields, Schwinger functions, or measures on distribution spaces. Bare point fields may not converge as ordinary random variables.

**Calling regulator independence obvious.** Universality is powerful, but proving that different cutoffs yield the same continuum theory can be as hard as proving the continuum limit itself.

## Relations to other pages

This page supplies the regularization language used in [Euclidean Action as Density](/rigorous-qft/path-integrals-as-measures/euclidean-action-as-density/). The next step in this chapter is the continuum problem itself; the constructive version is developed in [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/).

For the probabilistic free-field side, see [Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/). For the Hilbert-space meaning of Euclidean cutoff limits, see [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/). For the RG viewpoint, continue later to the Rigorous Renormalization and RG chapter.

## Research status

The existence of finite cutoff Euclidean measures is elementary in many scalar models and highly developed in lattice gauge theory. The hard part is the limit. Constructive QFT has produced rigorous interacting continuum models in low dimensions and powerful renormalization techniques, but physically central four-dimensional interacting continuum theories remain much harder.

For scalar theories, the status depends strongly on dimension and scaling. For gauge theories, a lattice cutoff is central to nonperturbative definitions, but proving a continuum four-dimensional Yang–Mills theory with mass gap remains a major open problem. For fermions, UV cutoffs interact with determinants, Pfaffians, anomalies, and chiral symmetry. For Lorentzian path integrals, ultraviolet regularization does not by itself solve the oscillatory-integral problem.

## Exercises

### Exercise 1: Divergence of the coincident covariance

For the massive scalar covariance in $d$ Euclidean dimensions, estimate the large-momentum behavior of

$$
C_m(0)=
\int\frac{d^dp}{(2\pi)^d}\frac{1}{p^2+m^2}.
$$

For which $d$ does the ultraviolet part diverge?

<details>
<summary><strong>Solution</strong></summary>

At large $p$, the denominator behaves like $p^2$. In spherical coordinates, $d^dp$ contributes a factor proportional to $p^{d-1}dp$. Thus the large-$p$ behavior is

$$
\int^\infty p^{d-1}\frac{dp}{p^2}
=
\int^\infty p^{d-3}\,dp.
$$

This converges at infinity only when $d-3<-1$, namely $d<2$. It diverges logarithmically for $d=2$ and by powers for $d>2$. This is why coincident local products of continuum fields require renormalization in dimensions $d\geq 2$.

</details>

### Exercise 2: Heat-kernel cutoff covariance

Show that

$$
C_\epsilon
=\int_\epsilon^\infty e^{-t(-\Delta+m^2)}\,dt
$$

formally approaches $(-\Delta+m^2)^{-1}$ as $\epsilon\downarrow0$.

<details>
<summary><strong>Solution</strong></summary>

For a positive operator $A=-\Delta+m^2$, the functional-calculus identity is

$$
A^{-1}=\int_0^\infty e^{-tA}\,dt.
$$

Indeed, on an eigenvector with eigenvalue $\lambda>0$,

$$
\int_0^\infty e^{-t\lambda}\,dt=\frac{1}{\lambda}.
$$

The cutoff covariance omits the interval $0<t<\epsilon$:

$$
C_\epsilon=\int_\epsilon^\infty e^{-tA}\,dt.
$$

As $\epsilon\downarrow0$, it formally converges to $A^{-1}$. The omitted small-$t$ part corresponds to high-frequency, short-distance behavior.

</details>

### Exercise 3: Why finite volume is not a UV cutoff

Consider a continuum Gaussian field restricted to a bounded region $\Omega$. Does this restriction by itself make $C(x,x)$ finite? Explain.

<details>
<summary><strong>Solution</strong></summary>

No. Restricting to finite volume controls large-distance behavior and may discretize momenta if boundary conditions are imposed, but high-frequency modes are still present unless a UV cutoff is added. The coincident covariance is sensitive to arbitrarily short distances. In a finite box, the momentum spectrum may be discrete, but the sum over high modes can still diverge. A UV cutoff must suppress or remove those high modes, for example by a lattice spacing, spectral truncation, mollifier, or covariance cutoff.

</details>

## References

### Standard first pass

- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Barry Simon, *Functional Integration and Quantum Physics*, second edition, AMS Chelsea Publishing, 2005. AMS page: [bookstore.ams.org/view?ProductCode=CHEL%2F351.H](https://bookstore.ams.org/view?ProductCode=CHEL%2F351.H).
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974), 75–200. DOI: [10.1016/0370-1573(74)90023-4](https://doi.org/10.1016/0370-1573(74)90023-4).
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, fifth edition, Oxford University Press, 2021. DOI: [10.1093/oso/9780198834625.001.0001](https://doi.org/10.1093/oso/9780198834625.001.0001).

### Deeper references

- Kurt Symanzik, "Euclidean Quantum Field Theory. I. Equations for a Scalar Model," *Journal of Mathematical Physics* **7** (1966), 510–525. DOI: [10.1063/1.1704960](https://doi.org/10.1063/1.1704960).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- Vincent Rivasseau, *From Perturbative to Constructive Renormalization*, Princeton University Press, 1991.
- Erhard Seiler, *Gauge Theories as a Problem of Constructive Quantum Field Theory and Statistical Mechanics*, Lecture Notes in Physics **159**, Springer, 1982. DOI: [10.1007/BFb0091467](https://doi.org/10.1007/BFb0091467).

## Version history

- **2026-06-30:** Initial polished draft.
