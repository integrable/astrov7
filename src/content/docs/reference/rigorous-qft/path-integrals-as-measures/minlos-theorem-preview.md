---
title: "Minlos Theorem Preview"
description: "States the Bochner–Minlos theorem in the form used for Gaussian random fields and explains how characteristic functionals become probability measures on distributions."
sidebar:
  label: "Minlos Theorem Preview"
  order: 4
level: Advanced
status: "Polished draft"
source: "Bochner–Minlos theorem; Gel'fand–Vilenkin generalized random processes; Kuo and Bogachev on Gaussian measures; Simon functional integration."
topics:
  - Minlos theorem
  - characteristic functionals
  - nuclear spaces
  - Gaussian measures
  - generalized random fields
canonicalTopics:
  - bochner-minlos-theorem
  - characteristic-functional
  - nuclear-space
  - gaussian-random-field
researchStatus:
  established:
    - "The Bochner–Minlos theorem is a standard way to construct probability measures on spaces of distributions from continuous positive-definite characteristic functionals on nuclear test-function spaces."
  active:
    - "Applying this construction to interacting QFT requires additional estimates, renormalization, and Osterwalder–Schrader checks beyond the theorem itself."
---

## Summary

The Bochner–Minlos theorem is one of the cleanest bridges between formal path-integral characteristic functionals and honest probability measures on distributions. In finite dimensions, Bochner's theorem says that a normalized continuous positive-definite function is the Fourier transform of a probability measure. Minlos extends this idea to nuclear test-function spaces.

A useful form is this:

$$
\boxed{
\begin{gathered}
E\text{ nuclear},\qquad
\chi:E\to\mathbb C, \\
\chi(0)=1,\quad
\chi\text{ continuous},\quad
\chi\text{ positive-definite}
\end{gathered}
\Longrightarrow
\exists!\,\mu\text{ on }E'
}
$$

such that

$$
\chi(f)=
\int_{E'}e^{i u(f)}\,d\mu(u).
$$

In QFT language, $E$ is the test-function space, $E'$ is a space of generalized fields, and $u(f)$ is the smeared field. Thus Minlos is a theorem that turns a suitable characteristic functional into a probability law for a random distribution.

The theorem does **not** say that every formal path integral is a measure, and it does not by itself prove reflection positivity, locality, clustering, or existence of an interacting Lorentzian QFT. It is a construction theorem for measures, not a full QFT reconstruction theorem.

## Prerequisites

You should know [Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/) and [Cylinder Measures](/rigorous-qft/path-integrals-as-measures/cylinder-measures/). The relation to Lorentzian QFT uses [OS Axioms](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-axioms/) and [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/). The reason fields are tested against smooth functions is explained in [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/).

## Core idea

A probability measure can be described by its Fourier transform. For an ordinary random vector $X\in\mathbb R^n$, the characteristic function is

$$
\chi(t)=\mathbb E\,e^{i t\cdot X}.
$$

For a generalized random field $u\in E'$, the analogous object is the characteristic functional

$$
\chi(f)=\mathbb E\,e^{i u(f)},
\qquad f\in E.
$$

The Bochner–Minlos theorem gives conditions under which such a functional really is the Fourier transform of a probability measure on $E'$.

<figure class="doc-figure" style="--figure-width: 55rem;">

![The Bochner–Minlos pipeline: nuclear test-function space, normalized continuous positive-definite characteristic functional, probability measure on the dual, and smeared random fields.](/figures/rigorous-qft/minlos-characteristic-functional.svg)

<figcaption>

Minlos converts characteristic-functional data into a measure on distributions. The output is a probability measure on $E'$, so it gives random smeared fields $u(f)$. To obtain a Euclidean QFT suitable for Osterwalder–Schrader reconstruction, one must still check Euclidean covariance, reflection positivity, regularity, symmetry properties, and clustering.

</figcaption>
</figure>

The reason this matters is that many field theories are first specified by their correlation functions or generating functionals, not by a pre-existing sample space. Minlos tells us when the finite-dimensional cylinder laws encoded by $\chi$ glue into an actual measure on distributions.

## Setup and conventions

Let $E$ be a real nuclear locally convex topological vector space. In Euclidean QFT, the main examples are spaces of test functions such as

$$
\mathcal S(\mathbb R^d),
\qquad
C_c^\infty(M),
$$

with appropriate locally convex topologies. Let $E'$ be the continuous dual, with pairing

$$
\langle u,f\rangle=u(f),
\qquad u\in E',\quad f\in E.
$$

A function $\chi:E\to\mathbb C$ is **positive-definite** if for every finite list $f_1,\ldots,f_n\in E$ and complex numbers $c_1,\ldots,c_n$,

$$
\sum_{i,j=1}^n
\overline{c_i}c_j\,
\chi(f_j-f_i)
\geq 0.
$$

It is normalized if

$$
\chi(0)=1.
$$

Continuity is meant with respect to the chosen topology on $E$. The topology is part of the theorem, not decoration.

## The theorem

A standard form of the Bochner–Minlos theorem says:

:::note[Bochner–Minlos theorem]
Let $E$ be a real nuclear locally convex space. If $\chi:E\to\mathbb C$ is continuous, positive-definite, and normalized by $\chi(0)=1$, then there exists a unique probability measure $\mu$ on $E'$ such that

$$
\chi(f)=
\int_{E'}e^{i\langle u,f\rangle}\,d\mu(u)
$$

for every $f\in E$.
:::

Different references formulate the target $\sigma$-algebra and regularity conclusion with slightly different topological precision: cylinder $\sigma$-algebra, weak dual, strong dual, Radon measure, or Radon measure on a suitable dual. The guiding point for QFT is stable: nuclearity upgrades a compatible characteristic functional into a genuine probability measure on generalized fields.

## Why positive-definiteness is the right condition

If $\mu$ is already a probability measure on $E'$, then

$$
\chi(f)=\int e^{i\langle u,f\rangle}\,d\mu(u)
$$

is automatically positive-definite. Indeed,

$$
\begin{aligned}
\sum_{i,j}\overline{c_i}c_j\chi(f_j-f_i)
&=
\int_{E'}
\sum_{i,j}\overline{c_i}c_j
 e^{i\langle u,f_j-f_i\rangle}\,d\mu(u) \\
&=
\int_{E'}
\left|\sum_j c_j e^{i\langle u,f_j\rangle}\right|^2
\,d\mu(u)
\geq 0.
\end{aligned}
$$

Thus positive-definiteness is not an arbitrary technical hypothesis. It is exactly the finite-dimensional remnant of positivity of probability.

Conversely, if $\chi$ is positive-definite, then for each finite-dimensional subspace $F\subset E$, its restriction to $F$ is a finite-dimensional characteristic function. Bochner's theorem gives a probability measure $\mu_F$ on $F^*$. These measures are consistent under restriction. Minlos supplies the infinite-dimensional extension to $E'$.

## Gaussian example

Let $Q:E\times E\to\mathbb R$ be a continuous symmetric positive semidefinite bilinear form. Define

$$
\chi_Q(f)=
\exp\!\left(-\frac12 Q(f,f)\right).
$$

This functional is normalized and continuous. It is also positive-definite because every finite restriction is the characteristic function of a centered Gaussian vector with covariance matrix

$$
Q_{ij}=Q(f_i,f_j).
$$

By Minlos, there is a probability measure $\mu_Q$ on $E'$ such that

$$
\int_{E'}e^{i\langle u,f\rangle}\,d\mu_Q(u)
=
\exp\!\left(-\frac12 Q(f,f)\right).
$$

The corresponding random distribution satisfies

$$
\mathbb E[u(f)]=0,
\qquad
\mathbb E[u(f)u(g)]=Q(f,g).
$$

Higher moments are given by Wick's rule. For instance,

$$
\begin{aligned}
\mathbb E[u(f_1)u(f_2)u(f_3)u(f_4)]
&=Q(f_1,f_2)Q(f_3,f_4) \\
&\quad +Q(f_1,f_3)Q(f_2,f_4) \\
&\quad +Q(f_1,f_4)Q(f_2,f_3).
\end{aligned}
$$

For the massive Euclidean free scalar field on $\mathbb R^d$, one takes $E=\mathcal S(\mathbb R^d)$ and

$$
Q_m(f,g)=
\int\frac{d^dp}{(2\pi)^d}\,
\frac{\widetilde f(-p)\widetilde g(p)}{p^2+m^2},
\qquad m>0.
$$

The resulting measure on $\mathcal S'(\mathbb R^d)$ is the Gaussian free field measure. It is a probability measure on distributions, not usually on ordinary functions.

## Why nuclearity appears

Nuclearity is the topological condition that makes the infinite-dimensional Fourier transform behave more like the finite-dimensional one. Without it, a continuous positive-definite cylindrical characteristic functional may fail to define a countably additive measure on the desired space.

A useful warning comes from Hilbert space. On an infinite-dimensional separable Hilbert space $H$, the formal characteristic functional

$$
\chi(h)=\exp\!\left(-\frac12\|h\|_H^2\right)
$$

defines a perfectly consistent Gaussian cylinder measure with covariance identity. But it does not define an $H$-valued standard Gaussian random variable. If $X_n$ are the coordinates in an orthonormal basis, then $X_n\sim N(0,1)$ independently, and

$$
\sum_{n=1}^\infty X_n^2=\infty
$$

almost surely. The random object lies in a larger distribution space.

For a genuine Gaussian measure on a Hilbert space, the covariance operator must be trace class. Nuclear test-function spaces are designed so that natural QFT covariances can define measures on their dual distribution spaces even when they do not produce samples in the test-function space or in a naive Hilbert space.

## Relation to Schwinger functions

Given a measure $\mu$ on $E'$, the $n$-point Schwinger distributions are moments:

$$
S_n(f_1,\ldots,f_n)
=
\int_{E'}
\langle u,f_1\rangle\cdots\langle u,f_n\rangle
\,d\mu(u),
$$

when the moments exist. Equivalently, they can be recovered from derivatives of $\chi$ near zero:

$$
S_n(f_1,\ldots,f_n)
=
\left.
\frac{1}{i^n}
\frac{\partial^n}{\partial t_1\cdots\partial t_n}
\chi\!\left(\sum_{j=1}^n t_j f_j\right)
\right|_{t_1=\cdots=t_n=0}.
$$

For a Gaussian measure, all odd moments vanish and all even moments are sums over pairings. For an interacting measure, the characteristic functional is typically not Gaussian, and connected correlation functions are encoded in

$$
W(f)=\log\chi(f)
$$

when this logarithm is defined near $f=0$.

## What Minlos does not prove

Minlos is a measure-construction theorem. A Euclidean QFT needs more.

| Additional property | Meaning | Why Minlos alone does not give it |
|---|---|---|
| Euclidean covariance | The measure or Schwinger functions respect Euclidean transformations. | A positive-definite functional may have no spacetime symmetry. |
| Reflection positivity | The Euclidean theory reconstructs a positive Hilbert space. | Ordinary probability positivity is not OS positivity. |
| Regularity | Schwinger functions are distributions with suitable growth. | The theorem gives a measure, but not automatically all analytic bounds needed later. |
| Clustering | Widely separated observables factorize in a pure vacuum phase. | This is an infrared and phase property. |
| Locality after reconstruction | Lorentzian fields commute at spacelike separation. | This is a consequence of the full OS/Wightman framework, not only of measure existence. |
| Renormalized interactions | Singular products are controlled by counterterms. | Minlos does not construct $e^{-V}$ when $V$ is ill-defined. |

Thus the pipeline is

$$
\text{characteristic functional}
\xrightarrow{\text{Minlos}}
\text{Euclidean measure}
\xrightarrow{\text{OS checks}}
\text{Hilbert-space QFT}.
$$

The second arrow is just as important as the first.

## How it appears in rigorous QFT

For free Euclidean fields, Minlos gives a compact construction. The covariance defines a Gaussian characteristic functional, and the theorem produces a probability measure on distributions.

For interacting scalar theories, one often tries to write a measure formally as

$$
d\mu(\phi)=Z^{-1}e^{-V(\phi)}\,d\mu_C(\phi).
$$

Minlos constructs $d\mu_C$ when $C$ is a valid Gaussian covariance. It does not automatically define $V(\phi)$, because $\phi(x)$ and powers such as $\phi(x)^4$ are singular in the continuum. Wick ordering, ultraviolet cutoffs, counterterms, and estimates enter at this point.

For gauge theories, there are further complications: gauge redundancy, quotient spaces, Gribov-type issues, ghosts or BRST/BV methods in perturbation theory, and nontrivial topology. Minlos is not a substitute for those structures.

## Common pitfalls

**Treating positivity as reflection positivity.** The positive-definite condition in Minlos is probability positivity. Osterwalder–Schrader reflection positivity is a different condition involving time reflection and observables supported in positive Euclidean time.

**Forgetting continuity.** Algebraic positive-definiteness on $E$ does not by itself control the topology. Continuity is what links the characteristic functional to the chosen distribution space.

**Forgetting nuclearity.** In infinite dimensions, finite-dimensional intuition fails. Nuclearity is one standard hypothesis that repairs the Fourier-transform theorem.

**Believing the theorem constructs interacting QFTs automatically.** It constructs measures from suitable characteristic functionals. For interacting models, building such a functional with the right bounds and axioms is the main problem.

**Confusing support with the dual space.** Saying that $\mu$ is a measure on $E'$ does not describe its sharp regularity. A Gaussian free field may almost surely lie in particular negative Sobolev or Besov spaces and not in smoother ones.

## Relations to other pages

[Cylinder Measures](/rigorous-qft/path-integrals-as-measures/cylinder-measures/) supplies the projective finite-dimensional viewpoint. [Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/) gives the main free-field example. [Gaussian Free Field](/rigorous-qft/osterwalder-schrader-euclidean-qft/gaussian-free-field/) connects the resulting measure to the Osterwalder–Schrader framework.

For interacting models, continue to [Constructive QFT](/rigorous-qft/constructive-qft/) and especially [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/), [P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/), and [φ⁴₂](/rigorous-qft/constructive-qft/phi-four-two/). For the operator-valued distribution side, return to [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/).

## Research status

The Bochner–Minlos theorem and Gaussian measure construction on nuclear-space duals are established mathematical tools. They are part of the standard rigorous foundation of generalized random processes and free Euclidean fields.

The frontier is not the theorem itself. The hard QFT questions are whether a physically interesting interacting model admits a continuum measure, whether the measure satisfies OS positivity and covariance, whether the reconstructed Lorentzian theory has the expected particles and phases, and whether four-dimensional interacting gauge theories can be constructed with a mass gap.

## Exercises

### Exercise 1: Positive-definiteness of a Gaussian characteristic functional

Let $Q$ be a symmetric positive semidefinite bilinear form on $E$. Explain why

$$
\chi_Q(f)=e^{-Q(f,f)/2}
$$

is positive-definite.

<details><summary><strong>Solution</strong></summary>

For any finite list $f_1,\ldots,f_n$, the matrix

$$
Q_{ij}=Q(f_i,f_j)
$$

is positive semidefinite. The restricted function

$$
(t_1,\ldots,t_n)
\mapsto
\exp\!\left(
-\frac12\sum_{i,j}t_i t_j Q_{ij}
\right)
$$

is the characteristic function of a centered Gaussian vector with covariance $Q_{ij}$, possibly degenerate. Every characteristic function is positive-definite. Since positive-definiteness is tested on finite lists, $\chi_Q$ is positive-definite on $E$.

</details>

### Exercise 2: Recovering the covariance

Let

$$
\chi(t,s)=
\exp\!\left[-\frac12\left(t^2Q(f,f)+2tsQ(f,g)+s^2Q(g,g)\right)\right].
$$

Use derivatives of $\chi$ to show that $\mathbb E[u(f)u(g)]=Q(f,g)$.

<details><summary><strong>Solution</strong></summary>

For the two variables $u(f)$ and $u(g)$,

$$
\mathbb E[u(f)u(g)]
=
\left.\frac{1}{i^2}
\frac{\partial^2}{\partial t\,\partial s}\chi(t,s)
\right|_{t=s=0}.
$$

Since $1/i^2=-1$ and

$$
\left.
\frac{\partial^2}{\partial t\,\partial s}\chi(t,s)
\right|_{t=s=0}
=-Q(f,g),
$$

we get

$$
\mathbb E[u(f)u(g)]=Q(f,g).
$$

</details>

### Exercise 3: Why OS positivity is extra

Suppose $\mu$ is any probability measure on $E'$ produced by Minlos. Does ordinary positivity

$$
\int |F(u)|^2\,d\mu(u)\geq0
$$

imply reflection positivity?

<details><summary><strong>Solution</strong></summary>

No. Reflection positivity has the form

$$
\int \overline{F(\theta u)}F(u)\,d\mu(u)\geq0
$$

for a time-reflection operation $\theta$ and for observables $F$ supported in positive Euclidean time. This condition involves spacetime structure and a particular reflection. Ordinary positivity of $\int |F|^2d\mu$ holds for every probability measure and does not imply the OS condition.

</details>

## References

### Standard first pass

- Barry Simon, *Functional Integration and Quantum Physics*, second edition, AMS Chelsea Publishing, 2005. AMS page: [bookstore.ams.org/view?ProductCode=CHEL%2F351.H](https://bookstore.ams.org/view?ProductCode=CHEL%2F351.H).
- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- I. M. Gel'fand and N. Ya. Vilenkin, *Generalized Functions, Volume 4: Applications of Harmonic Analysis*, Academic Press, 1964. Classic source for generalized random processes and nuclear-space formulations.

### Deeper references

- R. A. Minlos, "Generalized Random Processes and Their Extension to a Measure," *Selected Translations in Mathematical Statistics and Probability* **3** (1963), 291–313; translated from *Trudy Moskov. Mat. Obšč.* **8** (1959), 497–518.
- Hui-Hsiung Kuo, *Gaussian Measures in Banach Spaces*, Lecture Notes in Mathematics **463**, Springer, 1975. DOI: [10.1007/BFb0082007](https://doi.org/10.1007/BFb0082007).
- Vladimir I. Bogachev, *Gaussian Measures*, Mathematical Surveys and Monographs **62**, AMS, 1998. DOI: [10.1090/surv/062](https://doi.org/10.1090/surv/062).
- Svante Janson, *Gaussian Hilbert Spaces*, Cambridge University Press, 1997. Cambridge Core DOI: [10.1017/CBO9780511526169](https://doi.org/10.1017/CBO9780511526169).
- François Trèves, *Topological Vector Spaces, Distributions and Kernels*, Academic Press, 1967. Standard background for nuclear spaces and distributions.
- N. N. Vakhania, V. I. Tarieladze, and S. A. Chobanyan, *Probability Distributions on Banach Spaces*, Springer, 1987. DOI: [10.1007/978-94-009-3873-1](https://doi.org/10.1007/978-94-009-3873-1).
- H. Biermé, O. Durieu, and Y. Wang, "Generalized random fields and Lévy's continuity theorem on the space of tempered distributions," arXiv: [1706.09326](https://arxiv.org/abs/1706.09326).
- Sergio Albeverio, Raphael Høegh-Krohn, and Sonia Mazzucchi, *Mathematical Theory of Feynman Path Integrals: An Introduction*, second edition, Springer, 2008. DOI: [10.1007/978-3-540-76956-9](https://doi.org/10.1007/978-3-540-76956-9).

## Version history

- **2026-06-30:** Initial preview of the Bochner–Minlos theorem, characteristic functionals, Gaussian construction, and QFT caveats.
