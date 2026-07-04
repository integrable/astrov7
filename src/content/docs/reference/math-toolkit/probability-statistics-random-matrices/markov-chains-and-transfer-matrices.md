---
title: "Markov Chains and Transfer Matrices"
description: "A QFT-oriented guide to Markov kernels, stationary measures, detailed balance, spectral gaps, transfer matrices, Euclidean time evolution, and correlation lengths."
sidebar:
  label: "Markov Chains and Transfer Matrices"
  order: 5
level: Graduate
status: "Polished draft"
source: "Finite and continuous Markov chains, statistical mechanics transfer matrices, Perron-Frobenius theory, Euclidean lattice field theory, and quantum Hamiltonian limits."
topics:
  - Markov chains
  - transfer matrices
  - detailed balance
  - stationary measures
  - spectral gaps
  - Euclidean time evolution
  - correlation length
canonicalTopics:
  - markov-kernel
  - transfer-matrix
  - detailed-balance
  - stationary-distribution
  - correlation-length
  - euclidean-time-transfer-matrix
researchStatus:
  established:
    - "Markov kernels, stationary distributions, detailed balance, transfer matrices, Perron-Frobenius dominance, and spectral-gap control of correlations are standard tools in probability and statistical mechanics."
    - "Transfer matrices connect Euclidean lattice systems to Hamiltonian evolution and provide a precise route from classical statistical mechanics to quantum systems."
  active:
    - "Modern applications include nonequilibrium field theory, Markov-chain Monte Carlo, stochastic quantization, tensor-network transfer matrices, metastability, and dynamical large deviations."
---

## Summary

A Markov chain evolves probability distributions by a kernel. A transfer matrix evolves Boltzmann weights by a positive operator. They look similar because they are both linear propagation rules:

$$
p_{n+1}(y)=\sum_x K(y|x)p_n(x),
$$

and

$$
Z=\operatorname{Tr}T^N.
$$

The difference is normalization. A Markov kernel preserves total probability:

$$
\sum_y K(y|x)=1.
$$

A transfer matrix need not. Its largest eigenvalue controls the free energy, while ratios of eigenvalues control correlation lengths.

The physics dictionary is:

| Probability language | Statistical/QFT language |
|---|---|
| Markov state | spin configuration, field slice, coarse variable |
| transition kernel | local update rule, stochastic dynamics |
| stationary distribution | equilibrium Gibbs distribution |
| detailed balance | reversibility, self-adjointness after weighting |
| spectral gap | mixing rate, mass gap analog |
| transfer matrix | Euclidean-time evolution operator |
| largest eigenvalue | free-energy density |
| subleading eigenvalues | correlation lengths and masses |

For QFT, the transfer-matrix idea is one of the cleanest bridges between Euclidean path integrals and Hilbert-space Hamiltonians. In a lattice theory with Euclidean time spacing $a$, one often has

$$
T\sim e^{-aH}.
$$

Then long Euclidean time projects onto low-energy states.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A flowchart linking Markov kernels, stationary distributions, transfer matrices, Hamiltonians, eigenvalues, and correlation lengths.](/figures/math-toolkit/markov-transfer-matrix-flow.svg)

<figcaption>

Markov kernels and transfer matrices are both propagation operators. Stochastic normalization gives probability evolution; transfer-matrix normalization gives partition functions, Hamiltonians, free energies, and correlation lengths.

</figcaption>
</figure>

## Prerequisites

You should know basic probability measures, eigenvalues and eigenvectors, and the partition function of a classical statistical system. It helps to know [Spectral Theorem](/math-toolkit/functional-analysis-spectral-theory/spectral-theorem/), [Compact Operators](/math-toolkit/functional-analysis-spectral-theory/compact-operators/), and [Large Deviations](/math-toolkit/probability-statistics-random-matrices/large-deviations/), but the finite-state parts are self-contained.

We use discrete finite chains first. Infinite state spaces and continuum limits add functional-analysis issues, but the same ideas remain visible.

## Markov kernels

Let $S$ be a finite set of states. A Markov kernel is a matrix

$$
K(y|x)
$$

such that

$$
K(y|x)\ge0,
\qquad
\sum_y K(y|x)=1.
$$

If $p_n(x)$ is the probability of being in state $x$ at step $n$, then

$$
p_{n+1}(y)=\sum_x K(y|x)p_n(x).
$$

With column-vector conventions, this says

$$
p_{n+1}=Kp_n.
$$

The Markov property is the statement that the next state depends on the past only through the present:

$$
\mathbb P(X_{n+1}=x_{n+1}|X_n=x_n,\ldots,X_0=x_0)
=K(x_{n+1}|x_n).
$$

The probability of a path is therefore

$$
\mathbb P(x_0,x_1,\ldots,x_N)
=p_0(x_0)\prod_{n=0}^{N-1}K(x_{n+1}|x_n).
$$

That product form is why Markov chains look like one-dimensional lattice path integrals.

## Stationary distributions

A probability distribution $\pi$ is stationary if

$$
\pi(y)=\sum_x K(y|x)\pi(x).
$$

In vector notation,

$$
K\pi=\pi.
$$

Thus $\pi$ is an eigenvector with eigenvalue $1$.

If the chain is irreducible and aperiodic, then under standard finite-state hypotheses,

$$
K^n p_0\to \pi
$$

for any initial distribution $p_0$. The approach to equilibrium is controlled by subleading eigenvalues.

This is already a baby version of Euclidean projection. Repeated application of a positive operator singles out the dominant eigenvector.

## Detailed balance

A Markov chain satisfies detailed balance with respect to $\pi$ if

$$
\pi(x)K(y|x)=\pi(y)K(x|y).
$$

This says that, in equilibrium, probability current from $x$ to $y$ is exactly balanced by current from $y$ to $x$.

Detailed balance implies stationarity:

$$
\sum_x \pi(x)K(y|x)
=\sum_x \pi(y)K(x|y)
=\pi(y)\sum_xK(x|y)=\pi(y).
$$

It also implies that the transition operator is self-adjoint in the weighted inner product

$$
\langle f,g\rangle_\pi=\sum_x \pi(x)f(x)^*g(x).
$$

Indeed,

$$
\langle f,Kg\rangle_\pi
=
\sum_{x,y}\pi(x)f(x)^*K(y|x)g(y)
=
\sum_{x,y}\pi(y)K(x|y)f(x)^*g(y)
=\langle Kf,g\rangle_\pi.
$$

This is the stochastic counterpart of Hermitian Euclidean evolution.

## Spectral gap and mixing

For a reversible finite Markov chain, eigenvalues can be ordered as

$$
1=\lambda_0>\lambda_1\ge\lambda_2\ge\cdots\ge -1.
$$

The spectral gap is often

$$
\Delta=1-\lambda_1,
$$

assuming $\lambda_1$ is the largest subleading eigenvalue. A small gap means slow mixing; a large gap means rapid relaxation.

For an observable $f$ with zero mean,

$$
\sum_x\pi(x)f(x)=0,
$$

its time autocorrelation behaves schematically as

$$
\mathbb E_\pi[f(X_n)f(X_0)]
=\sum_{k\ge1} c_k\lambda_k^n.
$$

At long times, the largest relevant $|\lambda_k|$ dominates. Thus the correlation time is

$$
\tau^{-1}=-\log |\lambda_*|.
$$

If $\lambda_*=e^{-aE_*}$, this becomes an energy gap.

## Transfer matrices

A transfer matrix is a positive matrix that propagates statistical weights rather than normalized probabilities. For a one-dimensional classical system with variables $s_n$, nearest-neighbor Boltzmann weights often factor as

$$
Z_N=\sum_{s_1,\ldots,s_N}\prod_{n=1}^N T_{s_n s_{n+1}},
$$

with periodic boundary condition $s_{N+1}=s_1$. Therefore

$$
Z_N=\operatorname{Tr}T^N.
$$

If $T$ has eigenvalues $\lambda_0,\lambda_1,\ldots$ with

$$
|\lambda_0|>|\lambda_1|\ge\cdots,
$$

then at large $N$,

$$
Z_N\sim \lambda_0^N.
$$

The free energy per site is

$$
f=-\frac1\beta\lim_{N\to\infty}\frac1N\log Z_N
=-\frac1\beta\log\lambda_0.
$$

Correlation functions receive contributions from subleading eigenvalues. If an operator couples to the eigenvalue $\lambda_1$, then

$$
\langle O_nO_0\rangle_c\sim \left(\frac{\lambda_1}{\lambda_0}\right)^n,
$$

so the correlation length is

$$
\xi^{-1}=\log\left|\frac{\lambda_0}{\lambda_1}\right|.
$$

This formula is one of the great tiny machines of statistical mechanics.

## Transfer matrix versus Markov kernel

A positive transfer matrix can often be normalized into a Markov kernel, but the normalization is not always the naive column sum.

Suppose $T$ is a positive matrix with Perron-Frobenius eigenvalue $\lambda_0$ and positive right eigenvector $r$:

$$
\sum_y T_{xy}r_y=\lambda_0 r_x.
$$

Then

$$
K(y|x)=\frac{T_{xy}r_y}{\lambda_0 r_x}
$$

is a Markov kernel because

$$
\sum_yK(y|x)=1.
$$

This is called a Doob transform in probability. It converts positive weight propagation into stochastic evolution conditioned by the dominant eigenvector.

The distinction matters. A transfer matrix computes partition functions. A Markov kernel computes normalized path probabilities. Same linear algebra; different normalization and interpretation.

## The one-dimensional Ising transfer matrix

Consider the classical Ising chain with spins $\sigma_n=\pm1$ and Hamiltonian

$$
H=-J\sum_{n=1}^N\sigma_n\sigma_{n+1}-h\sum_{n=1}^N\sigma_n.
$$

With periodic boundary conditions, split the magnetic field symmetrically across bonds:

$$
T_{\sigma\sigma'}
=
\exp\!\left[\beta J\sigma\sigma'
+\frac{\beta h}{2}(\sigma+\sigma')\right].
$$

Then

$$
Z_N=\operatorname{Tr}T^N.
$$

Explicitly,

$$
T=\begin{pmatrix}
e^{\beta J+\beta h} & e^{-\beta J}\\
e^{-\beta J} & e^{\beta J-\beta h}
\end{pmatrix}.
$$

For $h=0$, the eigenvalues are

$$
\lambda_0=e^{\beta J}+e^{-\beta J}=2\cosh(\beta J),
$$

and

$$
\lambda_1=e^{\beta J}-e^{-\beta J}=2\sinh(\beta J).
$$

The spin-spin connected correlation length is

$$
\xi^{-1}=\log\left(\frac{\lambda_0}{\lambda_1}\right)
=\log\coth(\beta J).
$$

There is no finite-temperature phase transition in the one-dimensional Ising model because $\lambda_0$ remains analytic and separated from $\lambda_1$ for finite $\beta J$.

## Euclidean time and Hamiltonians

In quantum statistical mechanics,

$$
Z=\operatorname{Tr}e^{-\beta H}.
$$

If Euclidean time is discretized with spacing $a$, one writes

$$
\beta=Na,
\qquad
T=e^{-aH},
$$

so

$$
Z=\operatorname{Tr}T^N.
$$

This is formally identical to the transfer-matrix expression. Conversely, given a positive transfer matrix $T$, one may define an effective Hamiltonian

$$
H=-\frac1a\log T,
$$

provided $T$ is sufficiently nice and has positive spectrum.

Correlation functions along Euclidean time behave as

$$
\langle O(n)O(0)\rangle_c
\sim e^{-na(E_1-E_0)}.
$$

Thus the transfer-matrix correlation length is the inverse mass gap in lattice units:

$$
\xi_t^{-1}=a(E_1-E_0).
$$

This is why Euclidean lattice simulations extract masses from exponential decay.

## Trotter decomposition

The transfer matrix also arises by splitting a Hamiltonian into pieces. If

$$
H=A+B,
$$

then the Trotter product formula says

$$
e^{-\beta H}
=
\lim_{N\to\infty}\left(e^{-aA}e^{-aB}\right)^N,
\qquad
 a=\frac\beta N.
$$

This converts quantum evolution into a product of local Euclidean-time layers. In spin systems, bosonic systems, and lattice gauge theory, this is a route from Hamiltonian quantum mechanics to classical statistical weights in one higher Euclidean dimension.

At finite $a$, the replacement

$$
e^{-a(A+B)}\approx e^{-aA}e^{-aB}
$$

has errors controlled by commutators such as $[A,B]$. The continuum limit requires controlling these errors.

## Reflection positivity

Not every positive-looking transfer matrix gives a physical quantum theory. To reconstruct a Hilbert space with positive norm from Euclidean correlations, one needs reflection positivity.

Very schematically, if $\Theta$ reflects Euclidean time and $F$ is an observable supported at positive times, reflection positivity requires

$$
\langle (\Theta F)F\rangle_E\ge0.
$$

This condition ensures that the inner product defined by Euclidean correlation functions is positive. In lattice field theory, reflection positivity is the mathematical condition that makes the Euclidean transfer matrix compatible with unitary Lorentzian time evolution after continuation.

This is a common place where probability intuition needs a seatbelt. A Euclidean measure can be positive but still fail to reconstruct the desired quantum theory if reflection positivity or locality is lost.

## Continuous-time Markov chains

A continuous-time Markov chain is generated by a matrix $L$ with

$$
L(y|x)\ge0\quad (y\ne x),
$$

and

$$
\sum_y L(y|x)=0.
$$

The probability distribution evolves by the master equation

$$
\frac{d}{dt}p_t(y)=\sum_x L(y|x)p_t(x).
$$

The solution is

$$
p_t=e^{tL}p_0.
$$

Compare this with Euclidean quantum evolution:

$$
|\psi(\tau)\rangle=e^{-\tau H}|\psi(0)\rangle.
$$

The Markov generator has largest eigenvalue $0$ and nonpositive real parts for the rest. The quantum Hamiltonian has lowest energy $E_0$ and nonnegative excitation energies after shifting $E_0$ to zero. The analogy is

$$
L\leftrightarrow -H.
$$

Detailed balance makes $L$ self-adjoint after a similarity transformation, just as a Hamiltonian is self-adjoint in its Hilbert-space inner product.

## Fokker-Planck operators

For a diffusion process in $\mathbb R^n$,

$$
dX_t=b(X_t)dt+\sigma(X_t)dW_t,
$$

the probability density evolves by a Fokker-Planck equation

$$
\partial_t p = L^*p,
$$

where $L$ is the generator acting on observables. For simple overdamped Langevin dynamics,

$$
dX_t=-\nabla V(X_t)dt+\sqrt{2T}\,dW_t,
$$

the stationary distribution is

$$
\pi(x)=\frac1Z e^{-V(x)/T}.
$$

This is the continuum stochastic analog of a Gibbs measure. It is also the starting point for stochastic quantization and for many algorithms that sample Euclidean field configurations.

The warning is familiar: simulation time in a Markov chain is not automatically physical time. It may be an auxiliary time used to sample a measure.

## Transfer matrices in lattice field theory

A Euclidean lattice field theory can often be sliced by Euclidean time. Let $\varphi_n$ denote the spatial field configuration on time slice $n$. A local Euclidean action has a form that can be organized as

$$
S_E[\varphi]
=\sum_n L_E(\varphi_{n+1},\varphi_n).
$$

Then define a transfer kernel

$$
T(\varphi_{n+1},\varphi_n)
=e^{-L_E(\varphi_{n+1},\varphi_n)}.
$$

The partition function is schematically

$$
Z=\operatorname{Tr}T^{N_t}
=\int \prod_n D\varphi_n\,
\prod_n T(\varphi_{n+1},\varphi_n).
$$

If $T$ defines a positive self-adjoint operator after choosing the right Hilbert-space measure, one can set

$$
T=e^{-aH}
$$

and recover a Hamiltonian. The continuum theory is then studied by sending the lattice spacing $a\to0$ while tuning couplings appropriately.

## Correlation lengths and masses

Let $T$ have eigenstates $|n\rangle$ with eigenvalues

$$
\lambda_n=e^{-aE_n}.
$$

Assume $E_0$ is the lowest energy. A Euclidean two-point function has spectral decomposition

$$
\langle O(\tau)O(0)\rangle
=\sum_n |\langle 0|O|n\rangle|^2 e^{-\tau(E_n-E_0)}.
$$

At large $\tau$, the smallest nonzero gap that couples to $O$ dominates:

$$
\langle O(\tau)O(0)\rangle_c
\sim e^{-\tau m_O},
$$

where

$$
m_O=E_1-E_0
$$

in that channel. On the lattice,

$$
\xi_O^{-1}=a m_O.
$$

This is the operational reason transfer matrices are not just formal machinery: their eigenvalues are measured as masses and correlation lengths.

## Perron-Frobenius dominance

For a finite matrix with strictly positive entries, the Perron-Frobenius theorem says there is a unique largest positive eigenvalue $\lambda_0$ with positive left and right eigenvectors. All other eigenvalues have smaller absolute value.

This theorem is the linear-algebra engine behind:

- uniqueness of equilibrium in many one-dimensional classical systems,
- dominance of the leading transfer-matrix eigenvalue in the thermodynamic limit,
- exponential decay of correlations when there is a spectral gap,
- positivity of the ground-state wavefunction in many sign-problem-free systems.

In QFT language, Perron-Frobenius is one reason Euclidean evolution projects onto a vacuum state.

## Coarse-graining and blocked transfer matrices

Blocking $b$ time steps replaces

$$
T\mapsto T^b.
$$

Eigenvalues transform as

$$
\lambda_n\mapsto \lambda_n^b.
$$

The free energy rescales, but ratios behave as

$$
\left(\frac{\lambda_n}{\lambda_0}\right)^b.
$$

Thus irrelevant short-time details are suppressed under repeated blocking, while the largest eigenvalues control long-distance physics. This is a transfer-matrix version of renormalization-group thinking.

Near a critical point, the spectral gap closes:

$$
\frac{\lambda_1}{\lambda_0}\to 1,
\qquad
\xi\to\infty.
$$

That is the transfer-matrix signature of a continuum limit.

## Common pitfalls

### Confusing stochastic and statistical normalization

A Markov kernel has columns or rows summing to one, depending on convention. A transfer matrix does not. Multiplying a transfer matrix by a constant changes the free energy but not normalized correlations; multiplying a Markov kernel by a constant usually destroys probability conservation.

### Calling every positive matrix a Hamiltonian

To write $T=e^{-aH}$ with self-adjoint $H$, one needs positivity and suitable symmetry or reflection-positivity properties. A generic positive matrix need not define a physical quantum Hamiltonian.

### Ignoring left and right eigenvectors

If $T$ is not symmetric, left and right eigenvectors differ. Correlation functions and stochastic normalizations must use the correct biorthogonal structure.

### Mistaking Monte Carlo time for physical time

Markov-chain Monte Carlo uses a stochastic process to sample a target measure. Its update time is usually algorithmic, not physical. Autocorrelation in Monte Carlo time affects error bars, not necessarily physical dynamics.

### Forgetting boundary conditions

$Z=\operatorname{Tr}T^N$ assumes periodic boundary conditions. Open boundaries give matrix elements such as

$$
\langle L|T^N|R\rangle.
$$

The leading free energy is often the same, but boundary observables and finite-size corrections change.

### Assuming a spectral gap away from finite systems

Finite irreducible Markov chains have discrete spectra, but infinite-volume or continuum limits can close gaps. Gap closing is exactly what happens at criticality.

## Exercises

### Exercise 1: Stationarity from detailed balance

Show that detailed balance implies stationarity for a finite Markov chain.

<details><summary><strong>Solution</strong></summary>

Detailed balance says

$$
\pi(x)K(y|x)=\pi(y)K(x|y).
$$

Sum over $x$:

$$
\sum_x\pi(x)K(y|x)
=\sum_x\pi(y)K(x|y)
=\pi(y)\sum_xK(x|y).
$$

Since $K$ is a Markov kernel,

$$
\sum_xK(x|y)=1.
$$

Therefore

$$
\sum_x\pi(x)K(y|x)=\pi(y),
$$

which is stationarity.

</details>

### Exercise 2: Ising transfer matrix at zero field

For the one-dimensional Ising transfer matrix at $h=0$,

$$
T=\begin{pmatrix}
e^{\beta J} & e^{-\beta J}\\
e^{-\beta J} & e^{\beta J}
\end{pmatrix},
$$

find its eigenvalues and correlation length.

<details><summary><strong>Solution</strong></summary>

The vectors $(1,1)$ and $(1,-1)$ are eigenvectors. Their eigenvalues are

$$
\lambda_0=e^{\beta J}+e^{-\beta J}=2\cosh(\beta J),
$$

and

$$
\lambda_1=e^{\beta J}-e^{-\beta J}=2\sinh(\beta J).
$$

The correlation length is determined by

$$
\left(\frac{\lambda_1}{\lambda_0}\right)^n=e^{-n/\xi},
$$

so

$$
\xi^{-1}=\log\frac{\lambda_0}{\lambda_1}
=\log\coth(\beta J).
$$

</details>

### Exercise 3: Transfer matrix to Hamiltonian

Suppose a transfer matrix has eigenvalues $\lambda_n=e^{-aE_n}$. Show that the ratio $\lambda_n/\lambda_0$ determines the excitation energy $E_n-E_0$.

<details><summary><strong>Solution</strong></summary>

Taking the ratio gives

$$
\frac{\lambda_n}{\lambda_0}
=\frac{e^{-aE_n}}{e^{-aE_0}}
=e^{-a(E_n-E_0)}.
$$

Therefore

$$
E_n-E_0
=-\frac1a\log\left(\frac{\lambda_n}{\lambda_0}\right).
$$

This is why subleading transfer-matrix eigenvalues give masses or inverse correlation lengths.

</details>

### Exercise 4: Normalizing a transfer matrix into a Markov kernel

Let $T$ be a positive matrix with largest eigenvalue $\lambda_0$ and positive right eigenvector $r$, satisfying

$$
\sum_yT_{xy}r_y=\lambda_0r_x.
$$

Define

$$
K(y|x)=\frac{T_{xy}r_y}{\lambda_0r_x}.
$$

Show that $K$ is normalized as a Markov kernel.

<details><summary><strong>Solution</strong></summary>

Compute the sum over $y$:

$$
\sum_yK(y|x)
=\sum_y\frac{T_{xy}r_y}{\lambda_0r_x}
=\frac1{\lambda_0r_x}\sum_yT_{xy}r_y.
$$

Using the eigenvector equation,

$$
\sum_yT_{xy}r_y=\lambda_0r_x.
$$

Therefore

$$
\sum_yK(y|x)=1.
$$

Since $T_{xy}\ge0$ and $r_y>0$, also $K(y|x)\ge0$. Thus $K$ is a Markov kernel.

</details>

## References

- Norris, *Markov Chains*.
- Levin, Peres, and Wilmer, *Markov Chains and Mixing Times*.
- Baxter, *Exactly Solved Models in Statistical Mechanics*.
- Simon, *The Statistical Mechanics of Lattice Gases*.
- Glimm and Jaffe, *Quantum Physics: A Functional Integral Point of View*.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- Altland and Simons, *Condensed Matter Field Theory*.
- Fradkin, *Field Theories of Condensed Matter Physics*.

## Version history

- **2026-06-27:** First polished draft. Introduces Markov kernels, stationarity, detailed balance, spectral gaps, transfer matrices, the one-dimensional Ising example, Euclidean Hamiltonian reconstruction, reflection positivity, continuous-time generators, and correlation-length extraction.
