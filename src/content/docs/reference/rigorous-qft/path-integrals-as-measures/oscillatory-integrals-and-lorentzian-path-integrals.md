---
title: "Oscillatory Integrals and Lorentzian Path Integrals"
description: "Explains how finite-dimensional oscillatory integrals, stationary phase, time slicing, contour choices, and the iε prescription inform Lorentzian path-integral notation."
sidebar:
  label: "Oscillatory and Lorentzian"
  order: 9
level: Graduate
status: "Polished draft"
source: "Feynman–Hibbs path integrals; Schulman path integration; Albeverio–Høegh-Krohn–Mazzucchi Feynman integrals; Hörmander oscillatory integrals; Witten analytic continuation."
topics:
  - oscillatory integrals
  - Lorentzian path integrals
  - stationary phase
  - time slicing
  - i epsilon prescription
  - Picard–Lefschetz theory
  - real-time quantum mechanics
canonicalTopics:
  - oscillatory-integral
  - lorentzian-path-integral
  - stationary-phase
  - time-slicing
  - feynman-integral
  - picard-lefschetz
  - rigorous-path-integrals
researchStatus:
  established:
    - "Finite-dimensional oscillatory integrals and many time-sliced quantum-mechanical propagators have precise interpretations under suitable hypotheses."
  active:
    - "Infinite-dimensional Lorentzian QFT path integrals usually require additional structure, such as analytic continuation, perturbative algebraic constructions, contour choices, or operator-theoretic definitions."
---

## Summary

A Euclidean path integral with real positive action can sometimes be an honest probability measure. A Lorentzian path integral is different. Its formal weight is

$$
e^{iS[\text{history}]},
$$

so it is a phase, not a positive density. The finite-dimensional model for this object is not probability theory but **oscillatory integration**.

The guiding finite-dimensional expression is

$$
I(\tau)=\int_{\mathbb R^n} a(x)e^{i\tau\Phi(x)}\,d^nx,
\qquad \tau\to +\infty,
$$

where $a$ is an amplitude, $\Phi$ is a real phase, and the symbol $\int^{\mathrm{osc}}$ reminds us that the integral may be defined by cutoff, distributional, contour, or asymptotic procedures rather than by absolute convergence.

In quantum mechanics, time slicing turns the formal kernel

$$
K(q_f,t_f;q_i,t_i)
\stackrel{\mathrm{formal}}{=}
\int_{q(t_i)=q_i}^{q(t_f)=q_f}
\mathcal Dq\,e^{iS[q]}
$$

into a limit of finite-dimensional oscillatory integrals. In QFT, the same notation is vastly more singular: the dimension is infinite, the fields are distributions, local interactions require renormalization, and gauge theories have redundant directions.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Oscillatory integral data and interpretations](/figures/rigorous-qft/oscillatory-integral-data.svg)

<figcaption>

A Lorentzian path integral is best read through finite-dimensional approximations: choose a phase, amplitude, regulator or contour, then prove a limit, derive an asymptotic expansion, or identify the result with an independently defined operator object.

</figcaption>
</figure>

## Prerequisites

You should know [Finite-Dimensional Measures](/rigorous-qft/path-integrals-as-measures/finite-dimensional-measures/), [Ultraviolet Cutoffs](/rigorous-qft/path-integrals-as-measures/ultraviolet-cutoffs/), and [Continuum Limit of Measures](/rigorous-qft/path-integrals-as-measures/continuum-limit-of-measures/). The pages [Wick Rotation: Rigorous View](/rigorous-qft/osterwalder-schrader-euclidean-qft/wick-rotation-rigorous-view/) and [Euclidean versus Lorentzian QFT](/rigorous-qft/osterwalder-schrader-euclidean-qft/euclidean-versus-lorentzian-qft/) explain the Euclidean comparison point.

## Core idea

The phrase "path integral" hides several different mathematical objects. In this chapter we have already seen three of them:

| Symbolic expression | Rigorous model | Status |
|---|---|---|
| $Z^{-1}e^{-S(x)}d^nx$ | finite-dimensional probability measure | honest measure when $Z<\infty$ |
| $\Phi(f)$ | Gaussian random distribution | probability law on distributions |
| $\int D(\bar\psi,\psi)e^{-\bar\psi A\psi}$ | Berezin integral | algebraic operation, not probability |

The Lorentzian expression

$$
\int \mathcal D\phi\,e^{iS[\phi]}
$$

has a fourth status. It is normally an **oscillatory object**. It should not be read as integration against a positive measure. Its meaning may come from one of several constructions:

1. a finite-dimensional oscillatory integral with a specified limiting prescription;
2. a time-sliced approximation to a unitary operator;
3. an asymptotic stationary-phase expansion;
4. analytic continuation from Euclidean correlation functions;
5. a contour choice in a complexified space;
6. perturbative construction of time-ordered products;
7. a formal notation for Schwinger–Dyson identities and Feynman rules.

These interpretations overlap, but they are not identical. The main discipline of this page is to identify which interpretation is being used.

:::caution[Not a probability measure]
The phrase "integrate over histories with weight $e^{iS}$" is physically vivid but mathematically dangerous. The factor $e^{iS}$ does not define a positive density and usually does not define a complex measure of finite total variation.
:::

## Setup and conventions

We keep the mostly-minus Lorentzian convention of the volume. For one degree of freedom,

$$
S[q]=\int_{t_i}^{t_f}
\left(\frac{m}{2}\dot q^2-V(q)\right)dt.
$$

The corresponding Euclidean action after the formal substitution $t=-i\tau$ is

$$
S_E[q]=\int_{\tau_i}^{\tau_f}
\left(\frac{m}{2}\left(\frac{dq}{d\tau}\right)^2+V(q)\right)d\tau,
$$

when the potential and boundary conditions permit such a continuation. The Euclidean weight $e^{-S_E}$ may be positive and damping; the Lorentzian weight $e^{iS}$ is purely oscillatory.

For a scalar field in Minkowski space,

$$
S[\phi]=\int d^dx\,
\left(
\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-V_{\mathrm{int}}(\phi)
\right).
$$

The formal Lorentzian generating functional is

$$
Z[J]
\stackrel{\mathrm{formal}}{=}
\int \mathcal D\phi\,
\exp\left(iS[\phi]+i\int d^dx\,J\phi\right).
$$

Everything after the equality sign is notation until a definition is supplied.

## Finite-dimensional oscillatory integrals

In finite dimensions, a Lebesgue integral

$$
\int_{\mathbb R^n} a(x)e^{i\Phi(x)}d^nx
$$

is absolutely convergent if $a\in L^1(\mathbb R^n)$. Many physically important oscillatory integrals are not absolutely convergent. For instance,

$$
\int_{\mathbb R}e^{ix^2/2}dx
$$

is not absolutely convergent because $|e^{ix^2/2}|=1$, but it has a well-defined oscillatory value.

One common definition is damping and removal of the damping:

$$
\int_{\mathbb R}^{\mathrm{osc}}e^{ix^2/2}dx
=
\lim_{\epsilon\downarrow 0}
\int_{\mathbb R}e^{-\epsilon x^2}e^{ix^2/2}dx.
$$

The ordinary Gaussian formula gives

$$
\int_{\mathbb R}e^{-(\epsilon-i/2)x^2}dx
=
\left(\frac{\pi}{\epsilon-i/2}\right)^{1/2},
$$

where the square-root branch is chosen continuously from $\epsilon>0$. Hence

$$
\int_{\mathbb R}^{\mathrm{osc}}e^{ix^2/2}dx
=(2\pi)^{1/2}e^{i\pi/4}.
$$

The important lesson is not the phase $e^{i\pi/4}$ by itself. The lesson is that an oscillatory integral must specify a prescription. Without the damping limit, contour, distributional pairing, or asymptotic context, the symbol is ambiguous.

More generally, for a real nondegenerate symmetric matrix $A$,

$$
\int_{\mathbb R^n}^{\mathrm{osc}}
\exp\left(\frac{i}{2}x^TAx\right)d^nx
=(2\pi)^{n/2}
\frac{e^{i\pi\operatorname{sgn}(A)/4}}
{|\det A|^{1/2}},
$$

where

$$
\operatorname{sgn}(A)=n_+(A)-n_-(A).
$$

The signature phase is the finite-dimensional ancestor of many one-loop phases and Maslov-type factors.

## Stationary phase

Oscillatory integrals are controlled by stationary points. Let

$$
I(\tau)=\int_{\mathbb R^n}a(x)e^{i\tau\Phi(x)}d^nx,
\qquad \tau\to +\infty,
$$

with $a$ smooth and compactly supported. Suppose $x_0$ is the only critical point of $\Phi$ on the support of $a$ and the Hessian

$$
H_{ij}=\partial_i\partial_j\Phi(x_0)
$$

is nondegenerate. Then stationary phase gives

$$
I(\tau)
\sim
\left(\frac{2\pi}{\tau}\right)^{n/2}
\frac{e^{i\tau\Phi(x_0)}
 e^{i\pi\operatorname{sgn}(H)/4}}
{|\det H|^{1/2}}
\left(a(x_0)+O(\tau^{-1})\right).
$$

This is the finite-dimensional prototype of the semiclassical path integral:

$$
\text{path integral}
\sim
\sum_{\text{classical histories}}
 e^{iS[\phi_{\mathrm{cl}}]}
 \times
 \text{one-loop determinant}
 \times
 \text{higher-loop corrections}.
$$

The phrase "classical histories dominate" means precisely that nonstationary regions cancel by rapid phase oscillation. It does **not** mean that histories near a classical solution have large positive probability.

## Time slicing in quantum mechanics

For a particle with Hamiltonian

$$
H=\frac{p^2}{2m}+V(q),
$$

the unitary evolution kernel is

$$
K(q_f,t;q_i,0)=\langle q_f|e^{-itH}|q_i\rangle.
$$

A time-sliced path integral approximates this kernel by inserting many intermediate positions. Put $\Delta t=t/N$ and $q_0=q_i$, $q_N=q_f$. A typical formal approximation is

$$
K_N(q_f,t;q_i,0)
=
\left(\frac{m}{2\pi i\Delta t}\right)^{N/2}
\int_{\mathbb R^{N-1}}
\prod_{j=1}^{N-1}dq_j\,
\exp\left(
 iS_N[q]
\right),
$$

where

$$
S_N[q]=\sum_{j=1}^{N}
\Delta t\left[
\frac{m}{2}\left(
\frac{q_j-q_{j-1}}{\Delta t}
\right)^2
-V(q_{j-1})
\right].
$$

For each $N$, this is a finite-dimensional oscillatory integral, not a probability integral. Under appropriate hypotheses on $V$, the limit can be justified by operator theory, for example through product formulas for self-adjoint operators. The rigorous object is the unitary operator $e^{-itH}$; the path integral is then a representation, approximation, or asymptotic expansion of that object.

This point is worth stressing. In Euclidean quantum mechanics, the Feynman–Kac formula can express

$$
\langle q_f|e^{-tH}|q_i\rangle
$$

in terms of Wiener-type probability measures for suitable $V$. In real time,

$$
\langle q_f|e^{-itH}|q_i\rangle
$$

is governed by unitary evolution, not by a positive Markov semigroup. The two kernels are analytically related in simple cases, but their measure-theoretic meanings are different.

## Free Lorentzian Gaussian fields

The free scalar generating functional is formally Gaussian. If

$$
S_0[\phi]=\frac12\int d^dx\,
\phi(x)(-\Box-m^2)\phi(x),
$$

then completing the square suggests

$$
Z_0[J]
\propto
\exp\left(-\frac{i}{2}
\int d^dx\,d^dy\,
J(x)\Delta_F(x-y)J(y)
\right),
$$

where $\Delta_F$ is the Feynman propagator. In momentum space, with the conventions of the volume,

$$
\Delta_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

The $i\epsilon$ term is not decoration. It says how the poles are displaced and which distribution is meant. The same symbol also encodes vacuum boundary conditions. In a finite-dimensional analogy, $i\epsilon$ is a damping or contour prescription; in QFT, it is tied to spectrum, time ordering, and the choice of state.

For the free field, one can define the Lorentzian two-point distribution directly by Fourier transform with the $i\epsilon$ prescription. That does not mean the expression

$$
\int\mathcal D\phi\,e^{iS_0[\phi]}
$$

is an ordinary measure on fields. It means the formal Gaussian is shorthand for a definite distributional kernel and its Wick contractions.

## From quantum mechanics to fields

The jump from quantum mechanics to QFT adds several singularities at once.

First, paths become fields. Instead of functions $q(t)$, one integrates over histories $\phi(t,\mathbf x)$ with infinitely many spatial degrees of freedom.

Second, continuum fields are distributions. The free Euclidean scalar field is already distribution-valued in typical dimensions. Lorentzian time ordering adds further singularities along light cones and coincident points.

Third, local interactions require renormalization. A symbolic term such as

$$
\int d^dx\,\phi(x)^4
$$

is not automatically defined for distribution-valued $\phi$. In Euclidean constructive QFT one introduces cutoffs, Wick ordering, counterterms, and then proves a limit. In Lorentzian perturbation theory one defines time-ordered products as distributions and extends them across diagonals.

Fourth, gauge theories require quotienting redundant variables or adding ghosts, gauge fixing, and identities. A naive integral over all gauge potentials overcounts gauge orbits and introduces zero modes in the quadratic form.

Thus the formal Lorentzian QFT expression

$$
Z[J]=\int\mathcal D\phi\,e^{iS[\phi]+i\langle J,\phi\rangle}
$$

usually has to be replaced by a framework-specific object.

## Contours and the iε prescription

A finite-dimensional oscillatory integral may be defined by moving the contour into complex space. For example, the integral

$$
\int_{\mathbb R}e^{ix^2/2}dx
$$

can be evaluated by rotating the real line to a steepest-descent contour on which the real part of the exponent decays. The contour matters. Different contours can give different linear combinations of saddle contributions.

In QFT, one often writes

$$
S\mapsto S+i\epsilon\,\text{damping term}
$$

or equivalently displaces propagator poles as

$$
p^2-m^2\mapsto p^2-m^2+i\epsilon.
$$

This should be read as a boundary-condition and distribution prescription. It is not simply a trick for convergence. It selects vacuum time ordering and controls how analytic continuation is performed.

In finite-dimensional complexified integrals, Picard–Lefschetz theory organizes contour choices by decomposing integration cycles into steepest-descent cycles attached to critical points. This language has become important in discussions of real-time path integrals, Chern–Simons theory, sign problems, and complex saddles. It is powerful, but it is not a universal replacement for constructive QFT: in infinite-dimensional interacting theories, defining the space, contours, determinant factors, renormalization, and Stokes jumps remains highly nontrivial.

## What is rigorous here?

The following status distinctions are useful.

| Object | Typical rigorous status |
|---|---|
| Finite-dimensional oscillatory integral with compact amplitude | Standard distribution/asymptotic analysis. |
| Nondegenerate stationary phase expansion | Theorem under smoothness and support hypotheses. |
| Quadratic real-time Gaussian integral | Defined by damping, contour, or distribution prescription. |
| Time-sliced quantum-mechanical path integral | Often justified by operator product formulas under hypotheses on $H$. |
| Free Lorentzian QFT two-point function | Tempered distribution with specified pole prescription. |
| Perturbative Lorentzian QFT | Formal power series whose terms require distribution extension and renormalization. |
| Interacting nonperturbative Lorentzian QFT path integral | Usually not available as a literal measure; often defined via Euclidean reconstruction, algebraic methods, lattice limits, or model-specific constructions. |

A good rule is:

$$
\text{formal Lorentzian path integral}
\quad\leadsto\quad
\text{ask: which theorem, limit, contour, or algebra defines it?}
$$

## Common pitfalls

**Confusing phase with probability.** The factor $e^{iS}$ does not weight histories probabilistically. Its cancellations are interference, not statistical suppression.

**Writing a Lorentzian path integral as if it were a Euclidean measure.** The Euclidean weight $e^{-S_E}$ may define a measure after cutoffs and renormalization. The Lorentzian weight $e^{iS}$ generally does not.

**Ignoring the prescription.** An expression such as $1/(p^2-m^2)$ is incomplete in QFT. Feynman, retarded, advanced, and Wightman distributions differ by boundary values and pole prescriptions.

**Assuming stationary phase is exact.** Stationary phase is an asymptotic expansion. In QFT, the loop expansion around a saddle is normally formal and may miss nonperturbative sectors.

**Treating Wick rotation as automatic.** Wick rotation requires analyticity, spectral support, boundary conditions, and control of singularities. In curved spacetime, finite temperature, real-time nonequilibrium, and gauge theories, the continuation can be subtle.

**Forgetting renormalization.** A time-sliced particle path integral is already delicate. A local interacting field theory adds ultraviolet divergences that must be renormalized before taking a continuum limit.

**Thinking that contour deformation solves all real-time problems.** Picard–Lefschetz theory is a finite-dimensional and model-dependent guide. Infinite-dimensional contours and renormalized measures require more than a saddle diagram.

## Relations to other pages

This page sits at the end of the Path Integrals as Measures chapter because it explains the first major object in the chapter that is usually **not** a measure.

- [Finite-Dimensional Measures](/rigorous-qft/path-integrals-as-measures/finite-dimensional-measures/) gives the positive Euclidean baseline.
- [Euclidean Action as Density](/rigorous-qft/path-integrals-as-measures/euclidean-action-as-density/) explains why an interaction should be a density relative to a reference measure, not a density relative to infinite-dimensional Lebesgue measure.
- [Fermionic Berezin Integrals: Rigorous View](/rigorous-qft/path-integrals-as-measures/fermionic-berezin-integrals-rigorous-view/) gives the other non-probabilistic kind of path-integral notation.
- [Why Lorentzian Path Integrals Are Hard](/rigorous-qft/path-integrals-as-measures/why-lorentzian-path-integrals-are-hard/) lists the obstruction stack behind the formal real-time QFT integral.
- [Wick Rotation: Rigorous View](/rigorous-qft/osterwalder-schrader-euclidean-qft/wick-rotation-rigorous-view/) explains when Euclidean data can be analytically continued.
- [Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/) and [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) explain how Lorentzian singularities are controlled by microlocal methods.

## Research status

Finite-dimensional oscillatory integrals and stationary phase are classical analysis. Real-time path integrals in quantum mechanics have several rigorous formulations for important classes of Hamiltonians, especially when the path integral is understood as a representation of unitary evolution rather than as a countably additive measure on path space.

In QFT, the situation is more fragmented. Free Lorentzian fields are rigorously defined as operator-valued distributions or algebraic fields. Perturbative Lorentzian QFT can be treated through causal perturbation theory and microlocal extension of distributions. Nonperturbative interacting Lorentzian QFTs are usually obtained, when they are available, by Euclidean construction plus Osterwalder–Schrader reconstruction, by algebraic methods, by integrable-model constructions, or by model-specific arguments.

The phrase "Lorentzian path integral" is therefore best treated as a high-level notation family, not as a single universal mathematical object.

## Exercises

### Exercise 1: The one-dimensional oscillatory Gaussian

Use the damping prescription

$$
I_\epsilon=\int_{\mathbb R}e^{-\epsilon x^2}e^{ix^2/2}dx,
\qquad \epsilon>0,
$$

to compute

$$
\lim_{\epsilon\downarrow0}I_\epsilon.
$$

<details><summary><strong>Solution</strong></summary>

For $\epsilon>0$,

$$
I_\epsilon=\int_{\mathbb R}
 e^{-(\epsilon-i/2)x^2}dx
=\left(\frac{\pi}{\epsilon-i/2}\right)^{1/2},
$$

where the square-root branch is chosen with positive real value for positive real argument. Since

$$
\epsilon-i/2\longrightarrow -i/2
=\frac12 e^{-i\pi/2},
$$

we get

$$
(\epsilon-i/2)^{-1/2}
\longrightarrow
\sqrt{2}\,e^{i\pi/4}.
$$

Thus

$$
\lim_{\epsilon\downarrow0}I_\epsilon
=(2\pi)^{1/2}e^{i\pi/4}.
$$

</details>

### Exercise 2: Why absolute convergence fails

Explain why

$$
\int_{\mathbb R}e^{ix^2/2}dx
$$

is not absolutely convergent even though its oscillatory value exists.

<details><summary><strong>Solution</strong></summary>

Absolute convergence would require

$$
\int_{\mathbb R}\left|e^{ix^2/2}\right|dx<\infty.
$$

But

$$
\left|e^{ix^2/2}\right|=1,
$$

so the absolute-value integral is

$$
\int_{\mathbb R}dx=\infty.
$$

The finite answer comes only after using oscillatory cancellation through a prescription such as damping, contour rotation, or distributional interpretation.

</details>

### Exercise 3: Stationary phase for a quadratic form

Let $A$ be a real symmetric invertible $n\times n$ matrix. Diagonalize $A$ orthogonally and use the one-dimensional result to justify

$$
\int_{\mathbb R^n}^{\mathrm{osc}}
\exp\left(\frac{i}{2}x^TAx\right)d^nx
=(2\pi)^{n/2}
\frac{e^{i\pi\operatorname{sgn}(A)/4}}
{|\det A|^{1/2}}.
$$

<details><summary><strong>Solution</strong></summary>

Choose an orthogonal matrix $O$ such that

$$
O^TAO=\operatorname{diag}(\lambda_1,\ldots,\lambda_n).
$$

The Jacobian of $x=Oy$ is one. The integral factors into one-dimensional oscillatory Gaussians:

$$
\prod_{j=1}^n
\int_{\mathbb R}^{\mathrm{osc}}
\exp\left(\frac{i}{2}\lambda_j y_j^2\right)dy_j.
$$

For $\lambda_j>0$ the factor is

$$
(2\pi)^{1/2}\lambda_j^{-1/2}e^{i\pi/4},
$$

and for $\lambda_j<0$ it is

$$
(2\pi)^{1/2}|\lambda_j|^{-1/2}e^{-i\pi/4}.
$$

Multiplying all factors gives

$$
(2\pi)^{n/2}
|\lambda_1\cdots\lambda_n|^{-1/2}
 e^{i\pi(n_+-n_-)/4},
$$

which is the stated formula.

</details>

## References

### Standard first pass

- Richard P. Feynman, "Space-Time Approach to Non-Relativistic Quantum Mechanics," *Reviews of Modern Physics* **20** (1948), 367–387. DOI: [10.1103/RevModPhys.20.367](https://doi.org/10.1103/RevModPhys.20.367).
- Richard P. Feynman and Albert R. Hibbs, *Quantum Mechanics and Path Integrals*, McGraw–Hill, 1965; emended edition by Daniel F. Styer, Dover, 2010. ISBN: [9780486477220](https://store.doverpublications.com/products/9780486477220).
- L. S. Schulman, *Techniques and Applications of Path Integration*, Dover, 2005. Dover page: [store.doverpublications.com/products/9780486445281](https://store.doverpublications.com/products/9780486445281).
- Gerald B. Folland, *Harmonic Analysis in Phase Space*, Princeton University Press, 1989. Princeton page: [press.princeton.edu/books/paperback/9780691085289/harmonic-analysis-in-phase-space](https://press.princeton.edu/books/paperback/9780691085289/harmonic-analysis-in-phase-space).
- Lars Hörmander, *The Analysis of Linear Partial Differential Operators I*, second edition, Springer, 1990. DOI: [10.1007/978-3-642-61497-2](https://doi.org/10.1007/978-3-642-61497-2).

### Deeper references

- Sergio A. Albeverio, Raphael J. Høegh-Krohn, and Sonia Mazzucchi, *Mathematical Theory of Feynman Path Integrals: An Introduction*, second corrected and enlarged edition, Lecture Notes in Mathematics **523**, Springer, 2008. DOI: [10.1007/978-3-540-76956-9](https://doi.org/10.1007/978-3-540-76956-9).
- Cécile Morette DeWitt, "Feynman's Path Integral: Definition Without Limiting Procedure," *Communications in Mathematical Physics* **28** (1972), 47–67. DOI: [10.1007/BF02099371](https://doi.org/10.1007/BF02099371).
- Daisuke Fujiwara, *Rigorous Time Slicing Approach to Feynman Path Integrals*, SpringerBriefs in Mathematical Physics, Springer, 2017. DOI: [10.1007/978-4-431-56553-6](https://doi.org/10.1007/978-4-431-56553-6).
- Edward Witten, "Analytic Continuation Of Chern-Simons Theory," arXiv: [1001.2933](https://arxiv.org/abs/1001.2933); in *Chern–Simons Gauge Theory: 20 Years After*, AMS/IP Studies in Advanced Mathematics **50**, 2011.
- Michael Dütsch and Klaus Fredenhagen, "Perturbative Algebraic Field Theory, and Deformation Quantization," arXiv: [hep-th/0101079](https://arxiv.org/abs/hep-th/0101079).
- Romeo Brunetti, Michael Dütsch, and Klaus Fredenhagen, "Perturbative Algebraic Quantum Field Theory and the Renormalization Groups," *Advances in Theoretical and Mathematical Physics* **13** (2009), 1541–1599. arXiv: [0901.2038](https://arxiv.org/abs/0901.2038).
- Christopher J. Fewster and Kasia Rejzner, "Algebraic Quantum Field Theory — an introduction," arXiv: [1904.04051](https://arxiv.org/abs/1904.04051).

## Version history

- **2026-06-30:** Initial polished draft.
