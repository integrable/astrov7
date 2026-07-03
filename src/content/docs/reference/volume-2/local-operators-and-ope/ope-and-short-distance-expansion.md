---
title: "OPE and Short-Distance Expansion"
description: "How products of nearby local operators are replaced by a tower of local operators with coefficient functions, and how the OPE organizes short-distance physics."
sidebar:
  label: "OPE and Short-Distance Expansion"
  order: 6
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Coleman 1985, Dilatations; Weinberg 1995–1996; Zinn-Justin 2021; Cardy 1996; Rychkov 2017."
topics:
  - operator product expansion
  - short-distance expansion
  - Wilson coefficients
  - local operators
  - scaling operators
canonicalTopics:
  - operator-product-expansion
  - short-distance-expansion
  - local-operator-expansion
researchStatus:
  established:
    - "The OPE is a standard local short-distance expansion of products of operators in QFT and becomes especially powerful at RG fixed points and in CFT."
  active:
    - "Questions about convergence, nonperturbative definitions, Lorentzian regimes, defects, boundaries, gauge theories, and bootstrap applications remain active across modern QFT."
---

## Summary

The **operator product expansion** says that when two local operators approach each other, their product can be replaced, inside correlation functions, by a sum of local operators at one point:

$$
\mathcal O_a(x)\mathcal O_b(0)
\sim
\sum_c C_{ab}{}^c(x,\mu,g)\mathcal O_{c,R}(0).
$$

The coefficient functions $C_{ab}{}^c$ contain the singular and scale-dependent short-distance information. The operators $\mathcal O_c$ form the local basis allowed by symmetries. The symbol $\sim$ means a short-distance expansion, not an ordinary pointwise equality of operator-valued functions.

At a fixed point, in a basis of scaling operators, the leading scalar part has the schematic form

$$
\mathcal O_a(x)\mathcal O_b(0)
\sim
\sum_c
\frac{C_{ab}{}^c}{|x|^{\Delta_a+\Delta_b-\Delta_c}}
\mathcal O_c(0)
+\text{descendants}.
$$

This is one of the deepest local statements in QFT. It says that short-distance singularities are not unstructured pathologies. They are organized by the spectrum of local operators.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 54rem;">

![Two nearby operator insertions shrink to an operator tower at one point with coefficient functions.](/figures/renormalization-rg-eft/ope-short-distance-expansion.svg)

<figcaption>

The OPE replaces two nearby insertions by a tower of local operators at one point. The coefficient functions $C_{ab}{}^c(x,\mu)$ know about the short separation $x$; the operators $\mathcal O_c(0)$ carry the long-distance response to spectator insertions.

</figcaption>
</figure>

:::note[The local slogan]
The OPE is Wilsonian locality in operator form: physics inside a tiny ball can be summarized by local operators seen from outside the ball.
:::

## Prerequisites

You should know [Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/), [Anomalous Dimensions of Operators](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimensions-of-operators/), [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), and [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/). It is also useful to have read [Short-Distance Singularities](/renormalization-rg-eft/why-renormalization/short-distance-singularities/) and [Divergences as Local Operators](/renormalization-rg-eft/why-renormalization/divergences-as-local-operators/).

The OPE is used heavily in CFT, but this page treats it first as a general QFT idea: a short-distance expansion inside correlation functions.

## Core idea

A local operator is an instruction to probe a field theory at a point. A product of two local operators at nearby points probes a small region. If all other insertions are far away compared with $|x|$, then the far-away observers cannot resolve the internal details of that small region. They can only see the total effect through local operators inserted at one representative point.

This is the same logic as multipole expansion in electrodynamics. A localized charge distribution looks, from far away, like a monopole plus dipole plus quadrupole plus higher multipoles. In QFT, a cluster of nearby operator insertions looks, from far away, like a tower of local operators:

$$
\text{two nearby insertions}
\longrightarrow
\text{local operator tower}.
$$

The expansion is powerful because the tower is constrained by symmetry, scaling, spin, internal charges, locality, and RG equations. In a CFT, this tower is organized into primaries and descendants. In a generic massive QFT, it is an asymptotic short-distance expansion valid when the separation is much smaller than all physical long-distance scales.

## Setup and conventions

We write the OPE as

$$
\mathcal O_a(x)\mathcal O_b(0)
\sim
\sum_c C_{ab}{}^c(x,\mu,g)\mathcal O_{c,R}(0).
$$

The operators on the right-hand side are renormalized operators in a chosen basis. The coefficient functions depend on:

- the separation $x$;
- the renormalization scale $\mu$;
- the renormalized couplings $g^i(\mu)$;
- the operator basis and subtraction scheme;
- masses or other relevant scales, if present.

The expansion is defined by inserting both sides into correlation functions with spectator operators far away:

$$
\left\langle
\mathcal O_a(x)\mathcal O_b(0)X
\right\rangle
\sim
\sum_c C_{ab}{}^c(x,\mu,g)
\left\langle
\mathcal O_{c,R}(0)X
\right\rangle,
$$

where all insertions in $X$ are separated from $0$ by distances much larger than $|x|$.

The OPE is local. It does not say that two arbitrary operators at arbitrary separation are equal to a convergent series. It says that their short-distance behavior can be expanded in local data.

## Why the coefficients are singular

If $\mathcal O_a$ and $\mathcal O_b$ have scaling dimensions $\Delta_a$ and $\Delta_b$, their product has dimension $\Delta_a+\Delta_b$. If $\mathcal O_c$ has dimension $\Delta_c$, then the coefficient multiplying $\mathcal O_c$ must have dimension

$$
\Delta_a+\Delta_b-\Delta_c.
$$

At a scale-invariant fixed point, dimensional analysis therefore suggests

$$
C_{ab}{}^c(x)
\propto
\frac{1}{|x|^{\Delta_a+\Delta_b-\Delta_c}}
$$

for scalar operators, up to angular dependence when spin is present. If

$$
\Delta_c<\Delta_a+\Delta_b,
$$

then the coefficient is singular as $x\to0$. The singularity is not a bug. It is the short-distance structure of the product.

The identity operator often gives the most singular term. For example, if $\mathcal O$ is a scalar primary in a CFT with two-point normalization

$$
\langle \mathcal O(x)\mathcal O(0)\rangle=\frac{1}{|x|^{2\Delta}},
$$

then the OPE contains

$$
\mathcal O(x)\mathcal O(0)
\sim
\frac{\mathbf 1}{|x|^{2\Delta}}+\cdots.
$$

The identity coefficient reproduces the leading two-point singularity.

## Free scalar example

For a free scalar field, Wick's theorem gives a clean first example. Let $D(x)$ be the free two-point function

$$
D(x)=\langle \phi(x)\phi(0)\rangle.
$$

Then

$$
\phi(x)\phi(0)
=
D(x)\mathbf 1+:\!\phi(x)\phi(0)\!:.
$$

Now expand the normal-ordered product around $x=0$:

$$
:\!\phi(x)\phi(0)\!:
=
:\!\phi^2(0)\!:
+x^\mu:\!\partial_\mu\phi(0)\phi(0)\!:
+\frac12x^\mu x^\nu:\!\partial_\mu\partial_\nu\phi(0)\phi(0)\!:
+\cdots.
$$

Thus

$$
\phi(x)\phi(0)
\sim
D(x)\mathbf 1
+:\!\phi^2(0)\!:
+x^\mu:\!\partial_\mu\phi(0)\phi(0)\!:
+\cdots.
$$

This simple formula already contains the general pattern:

- singular coefficient functions, such as $D(x)$;
- local operators at one point;
- derivative operators, which are descendants in conformal language;
- an expansion meaningful inside correlators with distant spectator insertions.

In an interacting theory, normal ordering is replaced by renormalized composite operators, and the coefficient functions receive quantum corrections.

## OPE versus Taylor expansion

The OPE is not just a Taylor expansion. A Taylor expansion of one operator would give

$$
\mathcal O_a(x)=\mathcal O_a(0)+x^\mu\partial_\mu\mathcal O_a(0)+\cdots.
$$

But the product $\mathcal O_a(x)\mathcal O_b(0)$ has singularities as $x\to0$. Those singularities cannot be captured by an ordinary Taylor expansion with finite coefficients. The OPE includes singular coefficient functions multiplying local operators.

For the free scalar,

$$
\phi(x)\phi(0)
$$

contains the singular identity term $D(x)\mathbf 1$. No Taylor expansion of the normal-ordered local product alone would produce that term.

The OPE is therefore better thought of as a **singular Taylor expansion plus renormalization**. It separates the short-distance singular coefficients from the finite local operator basis.

## RG equation for OPE coefficients

Because the product on the left-hand side is independent of the arbitrary scale $\mu$, the OPE coefficients and renormalized operators must run oppositely.

Suppose

$$
\mu\frac{d}{d\mu}\mathcal O_{c,R}
=-\gamma_c{}^d\mathcal O_{d,R}.
$$

For simplicity, first assume $\mathcal O_a$ and $\mathcal O_b$ are fixed external renormalized operators whose anomalous dimensions are already included. Then the coefficient functions satisfy an RG equation of the schematic form

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
\right)C_{ab}{}^d
-
C_{ab}{}^c\gamma_c{}^d
+\text{terms from the running of }\mathcal O_a\text{ and }\mathcal O_b
=0.
$$

If all three operators belong to mixing sectors, the clean matrix form is obtained by treating the OPE coefficient as a tensor with one dual index and two input operator indices. It transforms with the anomalous-dimension matrices of all three sectors.

For multiplicatively renormalized operators,

$$
\mu\frac{d}{d\mu}\mathcal O_i=-\gamma_i\mathcal O_i,
$$

the coefficient satisfies

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^k\frac{\partial}{\partial g^k}
+\gamma_a+\gamma_b-\gamma_c
\right)C_{ab}{}^c=0,
$$

up to explicit masses and contact terms.

At a fixed point, this equation turns into the power-law dependence expected from scaling dimensions.

## OPE at a fixed point

At an RG fixed point, choose a basis of scaling operators. For scalar operators in Euclidean signature, the leading OPE takes the form

$$
\mathcal O_a(x)\mathcal O_b(0)
\sim
\sum_c
\frac{C_{ab}{}^c}{|x|^{\Delta_a+\Delta_b-\Delta_c}}
\mathcal O_c(0)
+\text{descendants}.
$$

The constants $C_{ab}{}^c$ are OPE coefficients. Together with the scaling dimensions and spin labels, they are part of the **CFT data**.

Descendants are fixed by symmetry once the primary contribution is known. For example, if $\mathcal O_c$ appears, derivatives such as

$$
\partial_\mu\mathcal O_c,
\qquad
\partial_\mu\partial_\nu\mathcal O_c,
\qquad
\Box\mathcal O_c
$$

also appear with coefficients constrained by translation and conformal symmetry.

In nonconformal QFT, one still has a short-distance expansion, but coefficient functions can include logarithms, running couplings, and ratios involving masses:

$$
C_{ab}{}^c(x,\mu,g,m)
=
|x|^{\Delta_c^{\text{eng}}-\Delta_a^{\text{eng}}-\Delta_b^{\text{eng}}}
\left[
A_{ab}{}^c(g(\mu),\mu|x|)+O(m|x|)
\right].
$$

The RG can be used to improve the logarithms by choosing $\mu\sim1/|x|$.

## Coefficient functions as Wilson coefficients

The OPE coefficient functions are Wilson coefficients in position space. They encode what a small region looks like to long-distance probes.

This is the same logic as EFT matching. In EFT, integrating out a heavy particle gives

$$
\mathcal L_{\text{EFT}}
=\sum_i C_i(\mu)\mathcal O_i.
$$

In the OPE, shrinking a pair of nearby operators gives

$$
\mathcal O_a(x)\mathcal O_b(0)
\sim
\sum_c C_{ab}{}^c(x,\mu)\mathcal O_c(0).
$$

Both statements separate short-distance coefficients from long-distance matrix elements. The difference is that the OPE is local in operator insertion space, while EFT matching is usually organized around a physical heavy scale or momentum threshold.

This viewpoint is especially useful in deep Euclidean limits, current algebra, QCD sum rules, conformal perturbation theory, critical phenomena, and factorization problems.

## Symmetry selection rules

The right-hand side can contain only operators allowed by exact symmetries. If $\mathcal O_a$ and $\mathcal O_b$ carry internal charges, then every $\mathcal O_c$ appearing in the OPE must carry the product charge. For an additive Abelian charge,

$$
q_c=q_a+q_b.
$$

Lorentz or rotation symmetry constrains spin. If the product of two scalar operators is expanded, scalar operators can appear with scalar coefficient functions, while spin-$\ell$ operators appear multiplied by tensor structures built from $x^\mu$.

Discrete symmetries also matter. For example, if a theory has a $\mathbb Z_2$ symmetry with $\phi\to-\phi$, then

$$
\phi(x)\phi(0)
$$

is even, so its OPE contains only even operators:

$$
\mathbf 1,
\qquad
\phi^2,
\qquad
(\partial\phi)^2,
\qquad
\phi^4,
\qquad
\ldots
$$

whereas

$$
\phi(x)\phi^2(0)
$$

is odd and can contain odd operators such as $\phi$ and $\phi^3$.

Gauge theories require additional care. Gauge-invariant local operators have gauge-invariant OPEs. Gauge-variant fields require gauge fixing or Wilson lines to make gauge-covariant short-distance statements.

## Contact terms and distributions

Products of local operators are distributions. The OPE therefore often contains contact terms supported at $x=0$:

$$
\delta^{(d)}(x)\mathcal O_c(0),
\qquad
\partial_\mu\delta^{(d)}(x)\mathcal O_c(0),
\qquad
\ldots
$$

These terms are invisible at separated points but essential in Ward identities, current algebra, trace anomalies, and integrated operator relations.

For example, a current conservation Ward identity can contain

$$
\partial_\mu\langle J^\mu(x)\mathcal O(0)\cdots\rangle
=\delta^{(d)}(x)\langle \delta\mathcal O(0)\cdots\rangle+\text{other contacts}.
$$

The separated-point OPE and the full distributional OPE are therefore not identical pieces of data. A serious calculation must state whether contact terms are included and which renormalization convention fixes them.

## Associativity and consistency

Consider three nearby operators. One may first fuse $\mathcal O_a(x)$ with $\mathcal O_b(y)$, or first fuse $\mathcal O_b(y)$ with $\mathcal O_c(0)$. Locality requires consistent answers in overlapping regions of validity. Symbolically,

$$
(\mathcal O_a\mathcal O_b)\mathcal O_c
\sim
\mathcal O_a(\mathcal O_b\mathcal O_c).
$$

In CFT this becomes the crossing-symmetry and bootstrap constraint on four-point functions. In general QFT it is a powerful local consistency condition, though less often expressed as a closed algebraic problem.

This is why the OPE is not merely a computational shortcut. It is a local algebraic structure on the space of operators. In favorable theories, knowing the operator spectrum and OPE coefficients is close to knowing the theory.

## Convergence, asymptotics, and domains of validity

The status of the OPE depends on the theory and kinematics.

In a Euclidean CFT, the OPE has a genuine convergence property inside correlation functions under radial-ordering conditions. Roughly, the expansion converges when the spectator insertions lie outside a sphere enclosing the two fused operators.

In a generic massive or asymptotically free QFT, the OPE is usually used as an asymptotic short-distance expansion:

$$
|x|\ll \text{all other distances},
\qquad
|x|\ll m^{-1}
$$

for masses $m$ that set long-distance scales. The expansion may include logarithms and running couplings, and nonperturbative terms can be invisible at any finite order in the short-distance expansion.

In Lorentzian signature, lightcone limits introduce additional singularities. Operators can approach each other along null directions, and the relevant expansion may differ from the ordinary Euclidean short-distance OPE. Lightcone OPEs, Regge limits, and real-time commutators require their own care.

## Common pitfalls

**Treating the OPE as an operator equality at finite separation.** The OPE is a short-distance expansion inside correlation functions. Its validity depends on the domain and on the theory.

**Forgetting the identity operator.** The most singular term is often the identity. Dropping it can make two-point singularities look mysterious.

**Confusing Wilson coefficients with matrix elements.** The coefficient functions are short-distance data. The expectation values or matrix elements of $\mathcal O_c$ contain long-distance physics.

**Using unrenormalized composite operators.** In interacting theories, the operator tower must be a renormalized local basis. Otherwise the OPE coefficients are not well-defined finite objects.

**Ignoring mixing.** If several operators share the same quantum numbers, the OPE coefficient is a vector or matrix in that sector, not a single number attached to a monomial.

**Dropping descendants without saying so.** In CFT, descendants are not arbitrary extra terms; symmetry fixes them. In non-CFT language, derivative operators are part of the local expansion.

**Forgetting contact terms.** Ward identities and integrated relations often depend on distributional contact terms that vanish at separated points.

**Assuming Euclidean convergence in Lorentzian limits.** Lightcone and real-time singularities can reorganize the expansion.

## Relations to other pages

This page completes the conceptual arc from local-operator renormalization to short-distance operator products. [Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/) explains the first power-counting estimate for which operators can appear. [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/) and [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/) explain why the operator basis is matrix-valued. [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/) explains how RG equations act on that basis and on the coefficient functions.

In the CFT and Bootstrap volume, the OPE becomes a central organizing principle: OPE coefficients, scaling dimensions, and crossing symmetry define the conformal bootstrap problem. In EFT chapters, the same short-distance logic appears as matching and Wilson coefficients. In statistical field theory, the OPE organizes critical short-distance behavior and corrections to scaling.

## Research status

The OPE is established as a foundational structure in QFT. Its exact status varies by context: rigorous convergence is best understood in Euclidean CFT and special constructive settings; perturbative and asymptotic OPEs are standard in renormalized QFT; and lightcone, defect, boundary, thermal, gauge-theory, and nonperturbative OPEs remain active subjects.

Modern research uses OPE data in the conformal bootstrap, QCD factorization, conformal perturbation theory, lattice operator matching, generalized symmetries, defect field theories, and quantum-information questions about local operator algebras.

## Exercises

### Exercise 1: Scaling of an OPE coefficient

Assume scalar scaling operators satisfy

$$
\mathcal O_i(\lambda x)=\lambda^{-\Delta_i}\mathcal O_i(x)
$$

in the sense of correlation functions. Show that if

$$
\mathcal O_a(x)\mathcal O_b(0)
\sim
C_{ab}{}^c(x)\mathcal O_c(0),
$$

then scale covariance requires

$$
C_{ab}{}^c(\lambda x)=
\lambda^{-(\Delta_a+\Delta_b-\Delta_c)}C_{ab}{}^c(x).
$$

<details><summary><strong>Solution</strong></summary>

Under $x\to\lambda x$, the left-hand side scales as

$$
\mathcal O_a(\lambda x)\mathcal O_b(0)
=\lambda^{-\Delta_a}\lambda^{-\Delta_b}
\mathcal O_a(x)\mathcal O_b(0),
$$

where the operator at the origin carries its usual scaling when inserted in a correlator. The right-hand side scales as

$$
C_{ab}{}^c(\lambda x)\mathcal O_c(0).
$$

To match the scaling of the left-hand side using

$$
\mathcal O_c(0)\to \lambda^{-\Delta_c}\mathcal O_c(0),
$$

the coefficient must satisfy

$$
C_{ab}{}^c(\lambda x)\lambda^{-\Delta_c}
=
\lambda^{-\Delta_a-\Delta_b}C_{ab}{}^c(x).
$$

Therefore

$$
C_{ab}{}^c(\lambda x)=
\lambda^{-(\Delta_a+\Delta_b-\Delta_c)}C_{ab}{}^c(x).
$$

</details>

### Exercise 2: The first terms in the free scalar OPE

Using Wick's theorem, show that

$$
\phi(x)\phi(0)
\sim
D(x)\mathbf 1+:\!\phi^2(0)\!:+x^\mu:\!\partial_\mu\phi(0)\phi(0)\!:+\cdots.
$$

<details><summary><strong>Solution</strong></summary>

Wick's theorem gives

$$
\phi(x)\phi(0)=\langle \phi(x)\phi(0)\rangle\mathbf 1+:\!\phi(x)\phi(0)\!:.
$$

Writing

$$
D(x)=\langle \phi(x)\phi(0)\rangle,
$$

we get

$$
\phi(x)\phi(0)=D(x)\mathbf 1+:\!\phi(x)\phi(0)\!:.
$$

Now Taylor expand the first field inside the normal-ordered product:

$$
\phi(x)=\phi(0)+x^\mu\partial_\mu\phi(0)+\cdots.
$$

Therefore

$$
:\!\phi(x)\phi(0)\!:
=:\!\phi^2(0)\!:
+x^\mu:\!\partial_\mu\phi(0)\phi(0)\!:
+\cdots.
$$

Combining the two expressions gives the claimed OPE.

</details>

### Exercise 3: A symmetry selection rule

Suppose a theory has a $\mathbb Z_2$ symmetry under which $\phi\to-\phi$. Which of the operators $\mathbf 1$, $\phi$, $\phi^2$, $\phi^3$, and $\partial_\mu\phi\partial^\mu\phi$ can appear in the OPE of $\phi(x)\phi(0)$?

<details><summary><strong>Solution</strong></summary>

The product $\phi(x)\phi(0)$ is even under $\mathbb Z_2$, because it contains two odd fields. Therefore only even operators can appear.

The operators

$$
\mathbf 1,
\qquad
\phi^2,
\qquad
\partial_\mu\phi\partial^\mu\phi
$$

are even and are allowed by this symmetry. The operators

$$
\phi,
\qquad
\phi^3
$$

are odd and cannot appear unless the $\mathbb Z_2$ symmetry is explicitly or spontaneously treated in a way that changes the selection rule.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the Wilsonian and short-distance operator viewpoint.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," for scaling, anomalous dimensions, Callan–Symanzik equations, and the OPE in deep Euclidean limits.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for composite operators, short-distance expansions, and critical phenomena.
- Steven Weinberg, *The Quantum Theory of Fields*, Vols. I–II, for operator methods, renormalization group methods, and short-distance expansions.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for critical phenomena, scaling operators, and the OPE viewpoint in statistical field theory.
- Slava Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, for a modern CFT and bootstrap-oriented account of OPE convergence and conformal data.

## Version history

- 2026-06-17: First polished draft. Introduced the OPE as a short-distance expansion, fixed coefficient-function conventions, included RG equations, free-field example, fixed-point form, contact-term caveats, and CFT/EFT connections.
