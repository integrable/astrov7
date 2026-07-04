---
title: "Entanglement Entropy in QFT"
description: "Reduced density matrices, Rényi entropies, UV divergences, modular Hamiltonians, and the field-theory concepts behind holographic entanglement entropy."
sidebar:
  order: 10
---

Entanglement entropy is one of the places where quantum field theory most clearly remembers that it is a theory with infinitely many local degrees of freedom. It is also one of the places where AdS/CFT turns a hard field-theory question into a geometric one.

The field-theory question is simple to state. Take a quantum state of a QFT on a spatial slice. Divide the slice into a region $A$ and its complement $A^c$. How much information about the full state is lost when an observer has access only to $A$?

The answer is encoded in the reduced density matrix

$$
\rho_A = \operatorname{Tr}_{A^c} \rho,
$$

and in particular in the von Neumann entropy

$$
S_A = -\operatorname{Tr}_A \rho_A \log \rho_A .
$$

This page builds the QFT side carefully. The next page explains why, in holographic theories at large $N$, the same quantity is computed by the area of a surface in the bulk.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A spatial slice is divided into a region A and its complement. The reduced density matrix is obtained by tracing over the complement.](/figures/course/entanglement-entropy-qft.svg)

<figcaption>

A spatial slice $\Sigma$ divided into $A$ and $A^c$. The entangling surface $\partial A$ is the locus where UV entanglement across the cut produces the leading area-law divergence.

</figcaption>
</figure>

## Why this matters for AdS/CFT

The original AdS/CFT dictionary relates local boundary operators to bulk fields. Entanglement entropy goes beyond local operators. It asks about the organization of quantum information in a spatial region.

This matters for three reasons.

First, QFT entanglement entropy has a characteristic UV divergence controlled by the area of the entangling surface $\partial A$. Holographically, the Ryu–Takayanagi formula turns that divergence into the near-boundary divergence of a bulk area. The match is almost too direct to ignore:

$$
\text{short-distance entanglement across }\partial A
\quad
\longleftrightarrow
\quad
\text{near-boundary area divergence of }\gamma_A .
$$

Second, entanglement entropy is sensitive to phases. In large-$N$ gauge theories, entanglement can diagnose confinement, thermal entropy, and phase transitions. In the bulk, these features become competing extremal surfaces, horizons, and topology.

Third, entanglement is now one of the main languages for emergent spacetime. Later in the course, relative entropy, entanglement wedges, and quantum extremal surfaces will make the slogan more precise: parts of the bulk are encoded in boundary subregions.

## Setup: a region and its reduced density matrix

Let $\Sigma$ be a Cauchy slice of the boundary QFT, and choose a spatial subregion $A\subset \Sigma$. Its complement is $A^c=\Sigma\setminus A$, and the common boundary

$$
\partial A = \partial A^c
$$

is called the entangling surface.

In a finite-dimensional quantum system with Hilbert-space factorization

$$
\mathcal H = \mathcal H_A \otimes \mathcal H_{A^c},
$$

the reduced density matrix is unambiguous:

$$
\rho_A = \operatorname{Tr}_{A^c}\rho .
$$

For a pure global state $\rho = |\Psi\rangle\langle\Psi|$, the entropy $S_A$ measures entanglement between $A$ and $A^c$.

In continuum QFT, one should be more careful. The Hilbert space does not literally factorize across a sharp spatial cut without a regulator. Gauge theories add another subtlety: Gauss constraints couple the two sides of the entangling surface. A practical way to proceed in this foundations course is:

1. regulate the QFT, for example by putting it on a spatial lattice or introducing a UV cutoff $\epsilon$;
2. define $\rho_A$ in the regulated theory;
3. study the cutoff dependence and universal terms as $\epsilon\to 0$.

This is the right level of precision for the classical holographic formulas developed here. The divergences are not a bug. They are part of the physics.

## Von Neumann entropy and Rényi entropies

The von Neumann entropy of the reduced density matrix is

$$
S_A = -\operatorname{Tr}\rho_A\log\rho_A .
$$

It is often useful to package the same information into Rényi entropies:

$$
S_n(A)
=
\frac{1}{1-n}\log \operatorname{Tr}\rho_A^n,
\qquad n>0,
\qquad n\neq 1 .
$$

The entanglement entropy is recovered by analytic continuation:

$$
S_A
=
\lim_{n\to 1} S_n(A)
=
-\left.\partial_n \log \operatorname{Tr}\rho_A^n\right|_{n=1} .
$$

This formula is the seed of the replica trick. In Euclidean QFT, $\operatorname{Tr}\rho_A^n$ can often be represented as a path integral on an $n$-sheeted geometry branched over $\partial A$.

A useful normalized version is

$$
\operatorname{Tr}\rho_A^n
=
\frac{Z_n}{(Z_1)^n},
$$

where $Z_n$ is the partition function on the replicated geometry. Then

$$
S_A
=
\left.\partial_n\left(n\log Z_1-\log Z_n\right)\right|_{n=1} .
$$

In holography, this replica expression becomes a gravitational problem: find a bulk saddle whose asymptotic boundary is the replicated boundary geometry. The Ryu–Takayanagi area term emerges from that gravitational replica construction.

## The area law

The most important structural fact is that entanglement entropy in local QFT is UV divergent. For a smooth entangling surface in a $d$-dimensional spacetime QFT, the leading divergence scales like

$$
S_A
\sim
\alpha_{d-2}\frac{\operatorname{Area}(\partial A)}{\epsilon^{d-2}}
+
\cdots,
\qquad d>2,
$$

where $\epsilon$ is a short-distance cutoff. In $d=2$, the entangling surface consists of points, and the leading divergence is logarithmic.

The area law is easy to understand physically. Most entanglement between $A$ and $A^c$ comes from short-distance modes straddling the entangling surface. A thin layer of thickness $\epsilon$ around $\partial A$ contributes roughly one independent amount of entanglement per cutoff cell. The number of such cells is proportional to $\operatorname{Area}(\partial A)/\epsilon^{d-2}$.

The coefficient $\alpha_{d-2}$ is not universal. It depends on the regulator and microscopic details. Universal information sits in more delicate terms:

- in even spacetime dimension $d$, smooth entangling surfaces can have logarithmic terms whose coefficients are related to conformal anomaly data;
- in odd spacetime dimension $d$, constant terms for special regions, such as spheres, can be universal;
- mutual information between separated regions is finite and cutoff independent.

This non-universality is important. Entanglement entropy is not usually a finite observable by itself. Universal pieces, variations, inequalities, and differences are often more physical than the full regulated entropy.

## The two-dimensional CFT benchmark

For a two-dimensional CFT on the infinite line in the vacuum, the entanglement entropy of an interval of length $\ell$ is

$$
S_A
=
\frac{c}{3}\log\frac{\ell}{\epsilon}+s_0,
$$

where $c$ is the central charge and $s_0$ is a non-universal constant. This formula is one of the basic checks of holographic entanglement entropy. In AdS$_3$/CFT$_2$, the Ryu–Takayanagi surface is a bulk geodesic, and its regularized length reproduces exactly the logarithm above when one uses the Brown–Henneaux relation

$$
c = \frac{3L}{2G_3} .
$$

At finite temperature $T=1/\beta$, the interval entropy becomes

$$
S_A
=
\frac{c}{3}\log\left(\frac{\beta}{\pi\epsilon}\sinh\frac{\pi\ell}{\beta}\right)+s_0 .
$$

For $\ell\gg \beta$, this grows linearly with $\ell$:

$$
S_A \sim \frac{\pi c}{3\beta}\ell + \cdots,
$$

which is the ordinary thermal entropy density times the interval length. In the bulk, that crossover is tied to geodesics probing a BTZ black-hole geometry.

## Pure states, mixed states, and complements

If the full state on $\Sigma$ is pure, then $A$ and $A^c$ have the same nonzero eigenvalues in their reduced density matrices. Therefore

$$
S_A = S_{A^c}
$$

for a pure global state.

If the full state is mixed, this equality need not hold. For example, in a thermal state, the entropy of a large region includes ordinary thermal entropy. In holography, this distinction becomes geometric. In a black-hole spacetime, the RT surface for a sufficiently large region may include a contribution related to the horizon.

This is one of the reasons the homology condition in the RT formula matters. The surface is not merely any minimal surface anchored at $\partial A$; it must be compatible with a bulk region whose boundary includes $A$.

## Entanglement inequalities

Entanglement entropy obeys powerful inequalities. These are field-theory constraints that holographic areas must reproduce.

For two regions $A$ and $B$, subadditivity says

$$
S_A + S_B \geq S_{A\cup B} .
$$

A sharper inequality is strong subadditivity:

$$
S_{A\cup B} + S_{B\cup C}
\geq
S_B + S_{A\cup B\cup C} .
$$

Equivalently, the conditional mutual information is nonnegative:

$$
I(A:C|B)
=
S_{A\cup B}+S_{B\cup C}-S_B-S_{A\cup B\cup C}
\geq 0 .
$$

The mutual information is

$$
I(A:B)
=
S_A+S_B-S_{A\cup B} .
$$

It measures correlations between $A$ and $B$ and is nonnegative. For separated regions in a local QFT, the leading area-law divergences cancel, so $I(A:B)$ is finite.

Holographically, these inequalities become geometric inequalities about minimal areas. This was one of the early signs that the RT formula knows nontrivial quantum-information structure.

## Modular Hamiltonian

It is often useful to write the reduced density matrix as

$$
\rho_A = \frac{e^{-K_A}}{\operatorname{Tr}e^{-K_A}},
$$

where $K_A$ is the modular Hamiltonian. This is just a definition, but $K_A$ is usually highly nonlocal.

There are special cases where $K_A$ is local. For the vacuum of a relativistic QFT restricted to a half-space $x^1>0$, the modular Hamiltonian is the generator of boosts:

$$
K_A
=
2\pi\int_{x^1>0} d^{d-1}x\, x^1 T_{00}(x) .
$$

For a spherical ball of radius $R$ centered at the origin in the vacuum of a CFT,

$$
K_A
=
2\pi\int_{|\mathbf x|<R} d^{d-1}x\,
\frac{R^2-|\mathbf x|^2}{2R}\,T_{00}(x) .
$$

These local formulas are extremely important in holography. They allow one to relate entanglement variations to stress-tensor expectation values, and eventually to gravitational equations in the bulk.

## The first law of entanglement

For a small perturbation of the state around a reference density matrix, entanglement entropy satisfies

$$
\delta S_A = \delta\langle K_A\rangle .
$$

This is called the first law of entanglement. It is not a dynamical equation; it is a consequence of expanding the von Neumann entropy to first order.

A quick derivation is as follows. Write

$$
K_A = -\log \rho_A^{(0)}
$$

for the modular Hamiltonian of the reference state. For a small perturbation

$$
\rho_A = \rho_A^{(0)} + \delta\rho_A,
\qquad
\operatorname{Tr}\delta\rho_A=0,
$$

one finds

$$
\delta S_A
=
-\operatorname{Tr}\delta\rho_A\log\rho_A^{(0)}
=
\operatorname{Tr}\delta\rho_A K_A
=
\delta\langle K_A\rangle .
$$

This formula is a key bridge between entanglement and dynamics. In holography, applying the first law to ball-shaped regions leads to deep relations between linearized Einstein equations and CFT entanglement.

## Relative entropy

Given two density matrices $\rho_A$ and $\sigma_A$ on the same region, the relative entropy is

$$
S(\rho_A||\sigma_A)
=
\operatorname{Tr}\rho_A\log\rho_A
-
\operatorname{Tr}\rho_A\log\sigma_A .
$$

If $\sigma_A$ defines a modular Hamiltonian $K_A^{(\sigma)}=-\log\sigma_A$ up to normalization, then

$$
S(\rho_A||\sigma_A)
=
\Delta\langle K_A^{(\sigma)}\rangle - \Delta S_A .
$$

Relative entropy is nonnegative:

$$
S(\rho_A||\sigma_A)\geq 0 .
$$

This inequality is a precise form of the idea that distinguishability cannot increase when we restrict to a subregion. Later, it becomes one of the cleanest ways to connect boundary positivity to bulk energy conditions and gravitational constraints.

## CFT spheres and thermal physics on hyperbolic space

For a spherical region in the vacuum of a CFT, there is an especially elegant trick. The causal domain of a ball in flat space is conformally equivalent to

$$
\mathbb R \times \mathbb H^{d-1} .
$$

Under this conformal map, the reduced density matrix of the ball becomes a thermal density matrix on hyperbolic space at temperature

$$
T = \frac{1}{2\pi R},
$$

where $R$ is the radius of the ball.

This observation is important for two reasons. First, it gives a field-theory way to understand universal sphere entanglement in CFTs. Second, in holographic CFTs, the corresponding bulk geometry is related to a hyperbolic black hole. The entanglement entropy of the sphere becomes a horizon entropy.

This is one of the cleanest conceptual bridges between entanglement entropy and black-hole entropy.

## Entanglement entropy versus thermal entropy

Entanglement entropy and thermal entropy are related but distinct.

Entanglement entropy is defined for a spatial subregion. It can be nonzero even in a pure global state. Thermal entropy is the entropy of a mixed thermal state and is extensive in volume.

For small regions in a thermal state, entanglement entropy is dominated by UV entanglement across $\partial A$. For very large regions, an extensive thermal contribution can appear. Holographically, this is why RT surfaces in black-brane geometries can run close to the horizon and pick up an area proportional to the region volume.

A useful slogan is:

$$
\text{short-distance entanglement}
\leftrightarrow
\text{near-boundary area},
\qquad
\text{thermal entropy}
\leftrightarrow
\text{horizon area}.
$$

## What makes entanglement hard in QFT

Entanglement entropy is hard to compute for several reasons.

The first difficulty is that $\rho_A$ is an operator on a huge Hilbert space. Even in ordinary many-body systems, tracing over $A^c$ is computationally expensive.

The second difficulty is that the modular Hamiltonian is usually nonlocal. The expression $\rho_A=e^{-K_A}/\operatorname{Tr}e^{-K_A}$ is formal unless one knows $K_A$.

The third difficulty is UV sensitivity. The leading entropy is divergent and regulator dependent.

The fourth difficulty is real-time dynamics. Time-dependent entanglement requires Lorentzian evolution of density matrices or real-time path integrals.

Holography does not make all of these difficulties disappear. But in the large-$N$, classical-bulk limit, it replaces a nonlocal quantum-information computation by a geometric variational problem.

## Dictionary checkpoint

This page gives the boundary-side concepts needed for the geometric dictionary:

| QFT concept | Holographic preview |
|---|---|
| spatial region $A$ | boundary anchor of a bulk surface |
| entangling surface $\partial A$ | boundary of the RT surface $\partial\gamma_A$ |
| area-law divergence | near-boundary area divergence |
| pure-state equality $S_A=S_{A^c}$ | homology and complementary surfaces |
| thermal entropy | horizon-area contribution |
| replica trick | gravitational replica saddle |
| modular Hamiltonian | generator related to bulk canonical energy in special cases |
| relative entropy | positive bulk energy/canonical-energy statement |

The next page turns the preview into the Ryu–Takayanagi formula.

## Common confusions

### “Entanglement entropy is finite because the region is finite.”

Not in continuum QFT. A finite spatial region still has infinitely many short-distance modes near $\partial A$. The entropy is UV divergent unless regulated.

### “The area law means entanglement entropy is geometric in any QFT.”

The area law is a general short-distance statement, but the RT formula is much stronger. It says that in holographic theories at large $N$, the full leading entropy is computed by a dynamical bulk extremal surface area.

### “The reduced density matrix always comes from an exact tensor product.”

This is true for ordinary finite-dimensional tensor-product systems. In continuum QFT and gauge theory, one must regulate or use an algebraic definition. For the purposes of classical holography, the regulated picture captures the essential divergences and universal structures.

### “Entanglement entropy and thermal entropy are the same thing.”

They can be related, but they are not the same. Entanglement entropy is associated with a subregion. Thermal entropy is associated with a mixed state of the whole system. In holography, both can appear as areas, but of different geometric objects.

### “The modular Hamiltonian is usually the physical Hamiltonian.”

Usually it is not. The modular Hamiltonian for a general region and state is highly nonlocal. It becomes a simple geometric generator only in special cases, such as half-spaces and spherical regions in the vacuum of a CFT.

## Exercises

### Exercise 1: Reduced density matrix of a Bell pair

Let

$$
|\Psi\rangle
=
\frac{1}{\sqrt 2}(|00\rangle+|11\rangle)
$$

be a state of two qubits. Trace over the second qubit and compute the entropy of the first.

<details>
<summary><strong>Solution</strong></summary>

The full density matrix is

$$
\rho = |\Psi\rangle\langle\Psi|
=\frac12\left(
|00\rangle\langle 00|
+|00\rangle\langle 11|
+|11\rangle\langle 00|
+|11\rangle\langle 11|
\right).
$$

Tracing over the second qubit gives

$$
\rho_1
=
\operatorname{Tr}_2\rho
=
\frac12\left(|0\rangle\langle0|+|1\rangle\langle1|\right)
=
\frac12 I .
$$

The eigenvalues are $1/2$ and $1/2$, so

$$
S_1
=-2\left(\frac12\log\frac12\right)
=\log 2 .
$$

The global state is pure, but the subsystem is maximally mixed.

</details>

### Exercise 2: Rényi entropy limit

Show that

$$
\lim_{n\to 1}\frac{1}{1-n}\log\operatorname{Tr}\rho_A^n
=
-\operatorname{Tr}\rho_A\log\rho_A .
$$

<details>
<summary><strong>Solution</strong></summary>

Let

$$
f(n)=\operatorname{Tr}\rho_A^n .
$$

Since $\operatorname{Tr}\rho_A=1$, we have $f(1)=1$. The Rényi entropy is

$$
S_n=\frac{\log f(n)}{1-n}.
$$

Both numerator and denominator vanish as $n\to1$, so use l'Hôpital's rule:

$$
\lim_{n\to1}S_n
=
\lim_{n\to1}\frac{f'(n)/f(n)}{-1}
=-f'(1).
$$

But

$$
f'(n)=\operatorname{Tr}\rho_A^n\log\rho_A,
$$

so

$$
f'(1)=\operatorname{Tr}\rho_A\log\rho_A .
$$

Therefore

$$
\lim_{n\to1}S_n
=-\operatorname{Tr}\rho_A\log\rho_A .
$$

</details>

### Exercise 3: Area-law scaling

In a $d$-dimensional spacetime QFT, the entangling surface has dimension $d-2$. Explain why the leading divergence should scale as

$$
\frac{\operatorname{Area}(\partial A)}{\epsilon^{d-2}} .
$$

<details>
<summary><strong>Solution</strong></summary>

The leading contribution comes from modes localized within a distance of order $\epsilon$ of the entangling surface. The number of independent cutoff cells along $\partial A$ is approximately

$$
\frac{\operatorname{Area}(\partial A)}{\epsilon^{d-2}},
$$

because $\partial A$ has dimension $d-2$. If each cell contributes an order-one amount of short-distance entanglement, the leading divergence has the stated form. The coefficient is regulator dependent because the argument depends on the microscopic definition of a cutoff cell.

</details>

### Exercise 4: Entanglement first law

Let $\rho=\rho_0+\delta\rho$ with $\operatorname{Tr}\delta\rho=0$, and define $K_0=-\log\rho_0$. Show that

$$
\delta S = \delta\langle K_0\rangle .
$$

<details>
<summary><strong>Solution</strong></summary>

The entropy is

$$
S(\rho)=-\operatorname{Tr}\rho\log\rho .
$$

To first order around $\rho_0$,

$$
\delta S
=-\operatorname{Tr}\delta\rho\log\rho_0
-\operatorname{Tr}\rho_0\rho_0^{-1}\delta\rho .
$$

The second term is $-\operatorname{Tr}\delta\rho=0$. Therefore

$$
\delta S
=-\operatorname{Tr}\delta\rho\log\rho_0
=\operatorname{Tr}\delta\rho K_0
=\delta\langle K_0\rangle .
$$

</details>

## Further reading

- P. Calabrese and J. Cardy, [Entanglement Entropy and Quantum Field Theory](https://arxiv.org/abs/hep-th/0405152).
- H. Casini and M. Huerta, [Entanglement Entropy in Free Quantum Field Theory](https://arxiv.org/abs/0905.2562).
- H. Casini and M. Huerta, [Lectures on Entanglement in Quantum Field Theory](https://arxiv.org/abs/2201.13310).
- H. Casini, M. Huerta, and R. C. Myers, [Towards a Derivation of Holographic Entanglement Entropy](https://arxiv.org/abs/1102.0440).
- S. Ryu and T. Takayanagi, [Holographic Derivation of Entanglement Entropy from AdS/CFT](https://arxiv.org/abs/hep-th/0603001).
