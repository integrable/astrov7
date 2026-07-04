---
title: "Gross–Neveu Model: Preview"
description: "Introduces the two-dimensional Gross–Neveu model as a rigorous constructive fermionic QFT example with asymptotic freedom, dynamical mass generation, and Grassmann RG control."
sidebar:
  label: "Gross–Neveu Preview"
  order: 8
level: Advanced
status: "Polished draft"
source: "Gross–Neveu model; Feldman–Magnen–Rivasseau–Sénéor construction; Zinn-Justin ch. 20; modern Polchinski-flow construction."
topics:
  - Gross–Neveu model
  - constructive QFT
  - fermionic fields
  - asymptotic freedom
  - dynamical mass generation
  - Grassmann integration
canonicalTopics:
  - constructive-quantum-field-theory
  - gross-neveu-model
  - asymptotic-freedom
  - fermionic-quantum-field-theory
  - rigorous-renormalization
researchStatus:
  established:
    - "The two-dimensional massive Euclidean Gross–Neveu model is a major rigorous constructive example of a just-renormalizable asymptotically free fermionic QFT."
  active:
    - "Massless, finite-volume, phase-structure, and modern flow-equation formulations remain active points of comparison, especially beyond the classic weak-coupling massive construction."
---

## Summary

The Gross–Neveu model is a two-dimensional fermionic QFT with a quartic self-interaction. In a common Lorentzian notation it has Lagrangian density

$$
\mathcal L
=
\sum_{i=1}^N \bar\psi_i\,i\gamma^\mu\partial_\mu\psi_i
+
\frac{g^2}{2N}
\left(\sum_{i=1}^N\bar\psi_i\psi_i\right)^2.
$$

The Euclidean constructive version replaces the formal path integral over anticommuting fields by finite-dimensional Grassmann Gaussian integrals, cutoffs, renormalized effective interactions, and Schwinger functions. The model is important because it is not merely superrenormalizable like $P(\phi)_2$ or $\phi^4_3$; in two dimensions it is **just renormalizable** and **asymptotically free**.

The model is also a laboratory for dynamical mass generation. A discrete chiral symmetry can forbid a bare mass term, but the interacting quantum theory generates a mass scale nonperturbatively. Schematically,

$$
m_{\mathrm{dyn}}
\sim
\Lambda\exp\!\left(-\frac{\mathrm{const}}{g^2(\Lambda)}\right),
$$

so the mass is invisible at every finite order of perturbation theory around $g=0$.

This page is a preview rather than a full proof. Its job is to explain what is constructed, why fermionic models are technically different from bosonic scalar models, and why the Gross–Neveu model is a milestone in constructive renormalization.

## Prerequisites

You should know [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/), [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/), [φ⁴₃ Theory](/rigorous-qft/constructive-qft/phi-four-three/), and [Sine-Gordon Model: Rigorous Construction](/rigorous-qft/constructive-qft/sine-gordon-model-rigorous-construction/). You should also know the difference between bosonic probability measures and fermionic Berezin or Grassmann integration.

## Core idea

Constructive scalar field theory must control probability measures on distribution-valued bosonic fields. Constructive fermionic field theory has a different starting point: Grassmann algebras are finite after an ultraviolet and volume cutoff, and high powers vanish by anticommutation. This gives powerful cancellations, but it does not make renormalization trivial.

The Gross–Neveu model asks whether one can construct the continuum limit of a two-dimensional interacting fermion theory whose coupling runs logarithmically. This is harder than a superrenormalizable model because the interaction remains marginal at short distances. It is easier than many bosonic just-renormalizable theories because fermionic anticommutation and determinant bounds give strong control.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Gross–Neveu constructive and RG map](/figures/rigorous-qft/gross-neveu-rg-construction.svg)

<figcaption>

The Gross–Neveu model combines two pieces of structure: a fermionic constructive setup based on Grassmann Gaussian integrals, and an asymptotically free renormalization-group flow. The ultraviolet limit is governed by the free theory, while the infrared physics is nonperturbative and contains a dynamically generated scale.

</figcaption>
</figure>

## Setup and conventions

Work in two Euclidean dimensions with $N$ flavors of Dirac fermions. A convenient formal Euclidean action is

$$
S_E(\bar\psi,\psi)
=
\int d^2x\left[
\sum_{i=1}^N\bar\psi_i(\gamma^\mu\partial_\mu+m_0)\psi_i
-
\frac{g_0}{2N}
\left(\sum_{i=1}^N\bar\psi_i\psi_i\right)^2
\right].
$$

The sign conventions vary. What matters for this page is the quartic local interaction

$$
(\bar\psi\psi)^2
=
\left(\sum_i\bar\psi_i\psi_i\right)^2,
$$

its flavor symmetry, and its marginality in two dimensions. In $d=2$ the Dirac field has dimension

$$
[\psi]=\frac12,
\qquad
[\bar\psi\psi]=1,
\qquad
[(\bar\psi\psi)^2]=2,
$$

so the coupling is dimensionless.

A finite cutoff construction replaces the field by finitely many Grassmann generators and writes

$$
Z_{\Lambda,\epsilon}(\eta,\bar\eta)
=
\int
\exp\!\left[-S_{\Lambda,\epsilon}(\bar\psi,\psi)
+
(\bar\eta,\psi)+(\bar\psi,\eta)
\right]D\bar\psi\,D\psi.
$$

The Schwinger functions are coefficients of this Grassmann generating functional. The constructive task is to tune the bare parameters, remove the cutoffs, and prove convergence of these coefficients as distributions satisfying the desired Euclidean axioms.

## Fermions are not probability measures

For bosons, a Euclidean construction often starts from a positive Gaussian probability measure $d\mu_C(\phi)$ and then defines an interacting measure

$$
d\nu(\phi)
\propto
\exp[-V(\phi)]d\mu_C(\phi).
$$

For fermions, there is no positive probability measure over ordinary field values. The Gaussian object is a linear functional on a Grassmann algebra, determined by covariance $C$ and Wick's rule with signs:

$$
\int \psi_{a_1}\cdots \psi_{a_{2n}}\,d\mu_C(\psi)
=
\operatorname{Pf}\!\big(C_{a_i a_j}\big)_{1\le i,j\le 2n}.
$$

Equivalently, complex Dirac fermion expectations are determinants. This algebraic nature has two consequences.

| Feature | Bosonic scalar fields | Fermionic fields |
|---|---|---|
| Basic object | Probability measure, often on distributions. | Grassmann Gaussian functional. |
| Products | Powers become more singular. | High powers vanish locally by anticommutation. |
| Positivity | Reflection positivity is a probability/Hilbert-space issue. | Positivity must be formulated through reconstructed Schwinger functions. |
| Estimates | Gaussian hypercontractivity, cluster expansions, correlation inequalities. | Determinant/Pfaffian bounds, Gram inequalities, fermionic RG. |

This is why the Gross–Neveu construction is not just the scalar $\phi^4$ construction with $\phi$ replaced by $\psi$.

## Renormalization and asymptotic freedom

The Gross–Neveu interaction is marginal in two dimensions. The coupling runs logarithmically. In a common normalization for a dimensionless coupling $u$, the beta function has the form

$$
\beta(u)
=
\mu\frac{du}{d\mu}
=
-b_0 u^2+O(u^3),
\qquad b_0>0,
$$

for the asymptotically free cases. A more detailed convention, using $\widetilde N$ real fermionic components, gives the leading behavior

$$
\beta(u)
=
-\frac{\widetilde N-2}{2\pi}u^2+O(u^3).
$$

Thus the ultraviolet limit is controlled by the Gaussian fixed point. At high momenta the effective coupling becomes small; at large distances it grows. This is the same qualitative pattern that makes four-dimensional non-Abelian gauge theory perturbatively tractable at short distance and nonperturbative in the infrared.

For constructive QFT, the useful ultraviolet statement is not merely "the beta function is negative." One needs estimates that hold across all scales and prove that the Schwinger functions have a regulator-independent limit after the bare mass and coupling have been chosen appropriately.

## Dynamical mass generation

Introduce an auxiliary scalar field $\sigma$ formally by a Hubbard–Stratonovich transformation:

$$
\exp\!\left[
\frac{g^2}{2N}\int(\bar\psi\psi)^2
\right]
\propto
\int D\sigma\,
\exp\!\left[-\int\left(
\frac{N}{2g^2}\sigma^2
-\sigma\bar\psi\psi
\right)d^2x\right].
$$

After integrating out fermions at large $N$, one obtains an effective action for $\sigma$. The saddle-point equation produces a nonzero scale even when the bare mass is zero. Schematically,

$$
\frac{1}{g^2}
\sim
\int^{\Lambda}\frac{d^2p}{(2\pi)^2}\frac{1}{p^2+m^2}
\sim
\frac{1}{2\pi}\log\frac{\Lambda}{m},
$$

so

$$
m
\sim
\Lambda\exp\!\left(-\frac{2\pi}{g^2}\right),
$$

up to convention-dependent constants. The exponential dependence is the key point. No Taylor series in $g^2$ around zero can see this mass scale.

The generated mass is often described as spontaneous breaking of a discrete chiral symmetry. Because the symmetry is discrete, the two-dimensional model does not violate the Mermin–Wagner obstruction that forbids spontaneous breaking of continuous internal symmetries under suitable hypotheses in two dimensions.

## What the classic constructive result gives

The landmark constructive results for the massive Euclidean Gross–Neveu model prove that, at weak renormalized coupling and with appropriate mass renormalization, the ultraviolet cutoff can be removed and the resulting Schwinger functions satisfy the Osterwalder–Schrader axioms. The model is thereby a genuine continuum QFT in the Euclidean constructive sense.

A rough proof map is:

| Step | Constructive role |
|---|---|
| Ultraviolet cutoff | Makes the Grassmann algebra finite-dimensional. |
| Multiscale decomposition | Splits the fermion covariance into momentum shells. |
| Running couplings | Tracks the marginal quartic interaction and mass term. |
| Determinant bounds | Control sums over fermionic contractions. |
| Renormalization conditions | Tune bare parameters to a fixed physical mass and coupling. |
| Uniform estimates | Prove convergence as the ultraviolet cutoff is removed. |
| OS verification | Turns Euclidean Schwinger functions into relativistic QFT data. |

The striking feature is that the model is **renormalizable**, not merely superrenormalizable. There are logarithmic scale accumulations, but asymptotic freedom makes the ultraviolet flow small enough to control.

## Why the Pauli principle helps

At a fixed spacetime point, products of too many identical Grassmann generators vanish. More generally, fermionic Gaussian integrals produce determinants rather than unrestricted sums of positive terms. Determinant bounds can turn the factorial growth that appears in naive diagram counting into controlled estimates.

This is not magic. The number of scales is still unbounded in the continuum limit, and marginal interactions require a renormalization group. But the Pauli principle gives constructive fermion models a kind of ultraviolet discipline that is absent for bosonic fields with pointwise powers.

A useful slogan is

$$
\text{fermionic construction}
=
\text{RG flow}
+
\text{determinant bounds}
+
\text{careful counterterms}.
$$

## Relation to Gross–Neveu–Yukawa models

The Gross–Neveu model is a four-fermion theory. The Gross–Neveu–Yukawa model introduces a bosonic scalar $\sigma$ as an independent field with Yukawa coupling

$$
g\sigma\bar\psi\psi
$$

and scalar potential. In critical-phenomena language, Gross–Neveu–Yukawa models describe fermionic quantum critical points in dimensions near four and in three-dimensional condensed-matter systems. The two descriptions are related in large-$N$ and renormalization-group analyses, but they are not the same constructive problem.

For this chapter, the Gross–Neveu page belongs here because it is a constructive fermionic QFT example. The Gross–Neveu–Yukawa critical points will later connect to CFT, bootstrap, lattice, and condensed-matter field theory pages.

## Relation to Thirring and sine-Gordon

The $N=1$ and current-current variants overlap with the Thirring family of two-dimensional fermion models. Through bosonization, parts of the Thirring family are related to sine-Gordon theory. This web is one reason two-dimensional QFT is so rich: scalar exponentials, fermion quartic interactions, solitons, and vertex operators can be different languages for related physics.

For rigorous purposes, however, one should keep the models separated until the theorem identifies them. A massive Gross–Neveu construction, a massive Thirring construction, a sine-Gordon construction, and a bosonization equivalence theorem are four different kinds of mathematical result.

## Common pitfalls

**Treating Grassmann integration as an ordinary measure.** Fermionic path integrals are algebraic Berezin integrals. They are not probability measures over numerical fermion fields.

**Assuming asymptotic freedom proves construction.** A negative beta function is a perturbative guide. A constructive proof requires uniform multiscale estimates and control of counterterms.

**Confusing perturbative masslessness with physical masslessness.** The mass scale of the Gross–Neveu model is nonperturbative and can be invisible in a formal expansion around zero coupling.

**Ignoring flavor conventions.** Different authors count Dirac, Majorana, or real components differently. This changes coefficients such as $b_0$, but not the qualitative statements: marginality, asymptotic freedom, and dynamical mass generation.

**Equating Gross–Neveu and Gross–Neveu–Yukawa.** They are related but not identical. One has a four-fermion interaction; the other has an auxiliary or dynamical scalar field.

**Assuming all two-dimensional four-fermion models behave the same.** The Thirring model, chiral Gross–Neveu model, and ordinary Gross–Neveu model have different symmetries, sectors, and constructive status.

## Relations to other pages

This page complements [Sine-Gordon Model: Rigorous Construction](/rigorous-qft/constructive-qft/sine-gordon-model-rigorous-construction/) by showing the fermionic side of two-dimensional constructive QFT. It also prepares for later constructive pages on cluster expansions, continuum limits, and fermionic Berezin integrals in the Path Integrals as Measures chapter.

For physical applications, the model will reappear in Renormalization, RG, and EFT, CFT and Bootstrap, and Condensed Matter Field Theory. For exact-solution aspects, compare later with Thirring and sine-Gordon pages in the Integrable and Exactly Solvable Models chapter.

## Research status

**Established.** The massive two-dimensional Euclidean Gross–Neveu model is a landmark rigorous construction of a just-renormalizable asymptotically free fermionic QFT. It supplies a genuine example beyond the superrenormalizable scalar models emphasized earlier in this chapter.

**Established but specialized.** The classic construction is not a blanket theorem for every Gross–Neveu variant, coupling regime, volume limit, symmetry realization, or boundary condition. It is important because it proves a hard and representative case.

**Active.** Modern renormalization-group, Polchinski-flow, finite-volume, and massless analyses continue to refine how the model is constructed and how different constructive frameworks compare.

**Bridge to physics.** The model remains a standard toy model for asymptotic freedom, dynamical mass generation, discrete chiral symmetry breaking, and large-$N$ methods.

## Exercises

### Exercise 1

Show by dimensional analysis that the four-fermion interaction $(\bar\psi\psi)^2$ is marginal in two Euclidean dimensions.

<details><summary><strong>Solution</strong></summary>

The kinetic term is

$$
\int d^2x\,\bar\psi\gamma^\mu\partial_\mu\psi.
$$

Since $[d^2x]=-2$ and $[\partial_\mu]=1$, scale invariance of the kinetic term gives

$$
2[\psi]+1-2=0,
$$

so $[\psi]=1/2$. Therefore

$$
[\bar\psi\psi]=1,
\qquad
[(\bar\psi\psi)^2]=2.
$$

The interaction has the same dimension as the Lagrangian density in two dimensions, so its coupling is dimensionless and the interaction is marginal by power counting.

</details>

### Exercise 2

Suppose the one-loop beta function has the form

$$
\mu\frac{du}{d\mu}=-b_0u^2,
\qquad b_0>0.
$$

Solve for $u(\mu)$ and show that the coupling decreases at large $\mu$.

<details><summary><strong>Solution</strong></summary>

Separate variables:

$$
\frac{du}{u^2}=-b_0\frac{d\mu}{\mu}.
$$

Integrating between $\mu_0$ and $\mu$ gives

$$
-\frac{1}{u(\mu)}+\frac{1}{u(\mu_0)}
=-b_0\log\frac{\mu}{\mu_0}.
$$

Thus

$$
\frac{1}{u(\mu)}
=
\frac{1}{u(\mu_0)}+b_0\log\frac{\mu}{\mu_0}.
$$

For $\mu\to\infty$, the denominator grows and $u(\mu)\to0$. This is asymptotic freedom.

</details>

### Exercise 3

Use the schematic gap equation

$$
\frac{1}{g^2}
\sim
\frac{1}{2\pi}\log\frac{\Lambda}{m}
$$

to solve for $m$ in terms of $g$ and $\Lambda$. Why is this nonperturbative in $g$?

<details><summary><strong>Solution</strong></summary>

Multiplying by $2\pi$ gives

$$
\log\frac{\Lambda}{m}
\sim
\frac{2\pi}{g^2}.
$$

Exponentiating,

$$
\frac{\Lambda}{m}
\sim
\exp\!\left(\frac{2\pi}{g^2}\right),
$$

so

$$
m
\sim
\Lambda\exp\!\left(-\frac{2\pi}{g^2}\right).
$$

The function $e^{-2\pi/g^2}$ has an essential singularity at $g=0$. Its Taylor series around $g=0$ is identically zero as an asymptotic perturbative signal, so finite-order perturbation theory cannot detect the generated scale.

</details>

## References

### Standard first pass

- David J. Gross and André Neveu, "Dynamical Symmetry Breaking in Asymptotically Free Field Theories," *Physical Review D* **10** (1974), 3235–3253. DOI: [10.1103/PhysRevD.10.3235](https://doi.org/10.1103/PhysRevD.10.3235).
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, fifth edition, Oxford University Press, 2021, chapter 20. DOI: [10.1093/oso/9780198834625.001.0001](https://doi.org/10.1093/oso/9780198834625.001.0001).
- Vincent Rivasseau, *From Perturbative to Constructive Renormalization*, Princeton University Press, 1991. DOI: [10.1515/9781400862085](https://doi.org/10.1515/9781400862085).

### Constructive references

- Joel Feldman, Jacques Magnen, Vincent Rivasseau, and Roland Sénéor, "Massive Gross-Neveu Model: A Rigorous Perturbative Construction," *Physical Review Letters* **54** (1985), 1479–1481. DOI: [10.1103/PhysRevLett.54.1479](https://doi.org/10.1103/PhysRevLett.54.1479).
- Joel Feldman, Jacques Magnen, Vincent Rivasseau, and Roland Sénéor, "A Renormalizable Field Theory: The Massive Gross-Neveu Model in Two Dimensions," *Communications in Mathematical Physics* **103** (1986), 67–103. DOI: [10.1007/BF01464282](https://doi.org/10.1007/BF01464282).
- Joel Feldman, Jacques Magnen, Vincent Rivasseau, and Roland Sénéor, "Bounds on Renormalized Feynman Graphs," *Communications in Mathematical Physics* **100** (1985), 23–55. DOI: [10.1007/BF01212687](https://doi.org/10.1007/BF01212687).
- Paweł Duch, "Construction of Gross-Neveu Model Using Polchinski Flow Equation," arXiv: [2403.18562](https://arxiv.org/abs/2403.18562).
- Jonathan Dimock, "Structural Stability of the RG Flow in the Gross-Neveu Model," arXiv: [2303.07916](https://arxiv.org/abs/2303.07916).

### Related models and physics background

- R. F. Dashen, Shang-keng Ma, and R. Rajaraman, "Finite-Temperature Behavior of a Relativistic Field Theory with Dynamical Symmetry Breaking," *Physical Review D* **11** (1975), 1499–1514. DOI: [10.1103/PhysRevD.11.1499](https://doi.org/10.1103/PhysRevD.11.1499).
- Eduardo Fradkin, *Field Theories of Condensed Matter Physics*, second edition, Cambridge University Press, 2013. DOI: [10.1017/CBO9781139015509](https://doi.org/10.1017/CBO9781139015509).
- G. Benfatto, P. Falco, and V. Mastropietro, "Functional Integral Construction of the Massive Thirring Model: Verification of Axioms and Massless Limit," *Communications in Mathematical Physics* **273** (2007), 67–118. DOI: [10.1007/s00220-007-0254-y](https://doi.org/10.1007/s00220-007-0254-y). arXiv: [math-ph/0609028](https://arxiv.org/abs/math-ph/0609028).

## Version history

- **2026-06-29:** Initial page created.
