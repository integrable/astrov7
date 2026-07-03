---
title: "Harmonic Oscillator Modes"
description: "Quantization of one oscillator, ladder operators, occupation numbers, zero-point energy, and the reason free field modes behave as independent quantum oscillators."
sidebar:
  label: "Harmonic Oscillator Modes"
  order: 1
---

## Summary

The harmonic oscillator is the local grammar of free quantum fields. A single oscillator has canonical variables $Q,P$ satisfying

$$
[Q,P]=i,
$$

and Hamiltonian

$$
H=\frac12\left(P^2+\omega^2Q^2\right).
$$

Defining

$$
a=\sqrt{\frac{\omega}{2}}Q+\frac{i}{\sqrt{2\omega}}P,
\qquad
 a^\dagger=\sqrt{\frac{\omega}{2}}Q-\frac{i}{\sqrt{2\omega}}P,
$$

gives

$$
[a,a^\dagger]=1,
\qquad
H=\omega\left(a^\dagger a+\frac12\right).
$$

Thus the spectrum is an evenly spaced ladder,

$$
E_n=\omega\left(n+\frac12\right),
\qquad n=0,1,2,\ldots .
$$

A free field is the infinite-dimensional version of this statement. After expanding the classical field in normal modes, the quadratic Hamiltonian becomes a sum or integral of independent oscillator Hamiltonians. Quantization turns each mode amplitude into an operator, and the excitation number of that oscillator becomes the occupation number of the corresponding quantum mode.

Coleman’s route from many-particle occupation numbers to field operators leans heavily on exactly this oscillator clue; Srednicki’s scalar-field quantization and Weinberg’s canonical formalism use the same algebra in their standard normalizations (Coleman 2019, ch. 2; Srednicki 2007, §3; Weinberg 1995, Vol. I, ch. 7).

## Prerequisites

You should know [Linearization and Normal Modes](/foundations/classical-field-theory/linearization-and-normal-modes/), [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/), and [Bosons and Fermions](/foundations/relativistic-particles-and-fields/bosons-and-fermions/). The conventions are those of [Conventions and Normalizations](/foundations/conventions-and-normalizations/): mostly-minus metric, natural units $\hbar=c=1$, and plane waves $e^{-ip\cdot x}$.

## Core idea

The classical small-fluctuation problem gives a quadratic Hamiltonian. A quadratic Hamiltonian can be diagonalized into normal modes. Each normal mode is a harmonic oscillator. The oscillator’s ladder operators are then reinterpreted as creation and annihilation operators for field quanta.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Quadratic field modes become independent harmonic oscillator ladders](/figures/foundations/oscillator-modes-to-ladders.svg)

<figcaption>

The quadratic field Hamiltonian decomposes into normal-mode coordinates $(Q_n,P_n)$. Quantization gives the canonical algebra $[Q_n,P_m]=i\delta_{nm}$, which is equivalently the oscillator algebra $[a_n,a_m^\dagger]=\delta_{nm}$. The number operator $N_n=a_n^\dagger a_n$ counts excitations of mode $n$.

</figcaption>
</figure>

The slogan

$$
\text{free field}=\text{many harmonic oscillators}
$$

is correct, but it is easy to overuse. It is a statement about quadratic Hamiltonians after the physical degrees of freedom have been identified. It is not a statement that every field component in every gauge or constrained system is an independent oscillator.

:::note[Assumptions]
This page treats bosonic oscillator modes. Fermionic modes are not ordinary harmonic oscillators; their creation and annihilation operators obey anticommutation relations and have only two occupation states, $n=0,1$. Gauge fields require gauge fixing or constraint reduction before one can identify the physical oscillators.
:::

## One oscillator

Start with one classical oscillator,

$$
H=\frac12\left(P^2+\omega^2Q^2\right),
$$

where $Q$ is the coordinate and $P$ is the conjugate momentum. Canonical quantization promotes them to operators satisfying

$$
[Q,P]=i.
$$

The factors of $\omega$ in the definition of $a$ and $a^\dagger$ are chosen so that $a$ is dimensionless:

$$
a=\sqrt{\frac{\omega}{2}}Q+\frac{i}{\sqrt{2\omega}}P,
\qquad
 a^\dagger=\sqrt{\frac{\omega}{2}}Q-\frac{i}{\sqrt{2\omega}}P.
$$

The inverse relations are

$$
Q=\frac1{\sqrt{2\omega}}(a+a^\dagger),
\qquad
P=-i\sqrt{\frac{\omega}{2}}(a-a^\dagger).
$$

Now compute the commutator:

$$
\begin{aligned}
[a,a^\dagger]
&=\left[\sqrt{\frac{\omega}{2}}Q+\frac{i}{\sqrt{2\omega}}P,
\sqrt{\frac{\omega}{2}}Q-\frac{i}{\sqrt{2\omega}}P\right] \\
&=-\frac{i}{2}[Q,P]+\frac{i}{2}[P,Q]
=1.
\end{aligned}
$$

So $a$ and $a^\dagger$ are annihilation and creation operators for the oscillator.

Substituting the inverse relations into the Hamiltonian gives

$$
H=\omega\left(a^\dagger a+\frac12\right).
$$

The operator

$$
N=a^\dagger a
$$

is the number operator for this oscillator.

## Ladder states

The oscillator algebra implies

$$
[N,a^\dagger]=a^\dagger,
\qquad
[N,a]=-a.
$$

Equivalently,

$$
[H,a^\dagger]=\omega a^\dagger,
\qquad
[H,a]=-\omega a.
$$

Thus $a^\dagger$ raises energy by $\omega$ and $a$ lowers energy by $\omega$. If $\lvert n\rangle$ is an eigenstate of $N$ with eigenvalue $n$, then

$$
N(a^\dagger\lvert n\rangle)=(n+1)a^\dagger\lvert n\rangle,
$$

and

$$
N(a\lvert n\rangle)=(n-1)a\lvert n\rangle.
$$

The bottom of the ladder is the vacuum state of the oscillator,

$$
a\lvert0\rangle=0.
$$

Normalized number states are

$$
\lvert n\rangle=\frac{(a^\dagger)^n}{\sqrt{n!}}\lvert0\rangle,
$$

and the ladder action is

$$
a^\dagger\lvert n\rangle=\sqrt{n+1}\,\lvert n+1\rangle,
\qquad
 a\lvert n\rangle=\sqrt n\,\lvert n-1\rangle.
$$

The energy eigenvalues are

$$
H\lvert n\rangle=\omega\left(n+\frac12\right)\lvert n\rangle.
$$

In QFT, this $n$ will become the occupation number of a field mode.

## Many independent oscillators

For several decoupled oscillators,

$$
H=\sum_n\frac12\left(P_n^2+\omega_n^2Q_n^2\right),
$$

with

$$
[Q_n,P_m]=i\delta_{nm},
\qquad
[Q_n,Q_m]=[P_n,P_m]=0,
$$

define

$$
a_n=\sqrt{\frac{\omega_n}{2}}Q_n+\frac{i}{\sqrt{2\omega_n}}P_n,
\qquad
 a_n^\dagger=\sqrt{\frac{\omega_n}{2}}Q_n-\frac{i}{\sqrt{2\omega_n}}P_n.
$$

Then

$$
[a_n,a_m^\dagger]=\delta_{nm},
\qquad
[a_n,a_m]=[a_n^\dagger,a_m^\dagger]=0,
$$

and

$$
H=\sum_n\omega_n\left(a_n^\dagger a_n+\frac12\right).
$$

A basis of states is labelled by the occupation numbers of all modes:

$$
\lvert n_1,n_2,n_3,\ldots\rangle.
$$

The operator

$$
N_n=a_n^\dagger a_n
$$

counts the excitation number of mode $n$, not the number of spatially localized little balls. In a free relativistic QFT, those excitations are interpreted as particles only after the mode labels are tied to one-particle quantum numbers such as momentum, spin, and species.

## From normal modes to field modes

Suppose a real scalar fluctuation has a quadratic Hamiltonian

$$
H_2=\frac12\int d^3\mathbf x\,
\left[\pi^2+(\nabla\phi)^2+m^2\phi^2\right].
$$

In a finite box, choose an orthonormal spatial mode basis $u_n(\mathbf x)$ satisfying

$$
\int d^3\mathbf x\,u_n^*(\mathbf x)u_m(\mathbf x)=\delta_{nm}.
$$

Expand

$$
\phi(t,\mathbf x)=\sum_n Q_n(t)u_n(\mathbf x),
\qquad
\pi(t,\mathbf x)=\sum_n P_n(t)u_n^*(\mathbf x).
$$

For normal modes that diagonalize the quadratic problem,

$$
H_2=\sum_n\frac12\left(P_n^2+\omega_n^2Q_n^2\right).
$$

So each field mode is an oscillator. Quantization gives one oscillator algebra per mode:

$$
[a_n,a_m^\dagger]=\delta_{nm}.
$$

For a free scalar field in infinite volume, the mode label becomes continuous. The Kronecker delta becomes a Dirac delta, and the sum becomes an integral.

## Momentum-space conventions

There are two common ways to normalize scalar-field modes. Both are useful, and both describe the same physics.

With noncovariantly normalized operators $b(\mathbf p)$,

$$
\phi(x)=\int\frac{d^3\mathbf p}{(2\pi)^3}\frac1{\sqrt{2E_{\mathbf p}}}
\left[b(\mathbf p)e^{-ip\cdot x}+b^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

with

$$
[b(\mathbf p),b^\dagger(\mathbf p')]=(2\pi)^3\delta^{(3)}(\mathbf p-\mathbf p').
$$

With covariantly normalized operators $a(\mathbf p)$,

$$
\phi(x)=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
\left[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

with

$$
[a(\mathbf p),a^\dagger(\mathbf p')]
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p').
$$

They are related by

$$
a(\mathbf p)=\sqrt{2E_{\mathbf p}}\,b(\mathbf p),
\qquad
 a^\dagger(\mathbf p)=\sqrt{2E_{\mathbf p}}\,b^\dagger(\mathbf p).
$$

The qft.org Fock-space pages usually use the covariant normalization because it pairs naturally with the invariant measure

$$
d\mu(p)=\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}.
$$

## Real fields and double counting

For a real scalar field,

$$
\phi^\dagger=\phi.
$$

This does not mean that the positive-frequency and negative-frequency parts are independent. Hermiticity ties them together:

$$
\phi(x)=\phi_+(x)+\phi_-(x),
\qquad
\phi_-=(\phi_+)^\dagger.
$$

In the momentum expansion, $a^\dagger(\mathbf p)$ creates the quantum associated with the complex conjugate mode. The reality condition is already built into the combination

$$
a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}.
$$

If instead one uses real standing-wave modes such as sines and cosines, each real mode has its own real coordinate $Q_n$ and momentum $P_n$. If one uses complex plane waves, one must be careful not to count the same real degree of freedom twice. This is one reason the compact $a,a^\dagger$ notation is so valuable: it packages the reality condition and the oscillator algebra cleanly.

## Zero-point energy

Each oscillator contributes a vacuum energy

$$
\frac12\omega_n.
$$

For a field, this gives formally

$$
E_0=\frac12\sum_n\omega_n
$$

or, in infinite volume,

$$
\frac{E_0}{V}=\frac12\int\frac{d^3\mathbf p}{(2\pi)^3}E_{\mathbf p}.
$$

This integral diverges at large momentum. In ordinary flat-space scattering calculations one often normal-orders the Hamiltonian, replacing

$$
H=\sum_n\omega_n\left(N_n+\frac12\right)
$$

by

$$
:H:=\sum_n\omega_nN_n.
$$

That removes the constant from the chosen Hamiltonian. It does not solve the cosmological constant problem, and it does not mean vacuum energy is physically meaningless in every context. It means that in non-gravitational flat-space QFT, an additive constant in the Hamiltonian is usually unobservable.

The full discussion belongs to [Normal Ordering](/foundations/canonical-quantization/normal-ordering/) and later to QFT in curved spacetime.

## What the oscillator picture means

The oscillator picture means that free quanta are normal-mode excitations of fields. It does not mean that an interacting quantum field is literally a set of permanently independent oscillators. Interactions couple modes, change occupation numbers, and make the physical vacuum more complicated than the free Fock vacuum.

For a free theory,

$$
H_0=\int d\mu(p)\,E_{\mathbf p}\,a^\dagger(\mathbf p)a(\mathbf p)
$$

after subtracting the zero-point constant. A one-particle state is

$$
\lvert\mathbf p\rangle=a^\dagger(\mathbf p)\lvert0\rangle,
$$

and

$$
H_0\lvert\mathbf p\rangle=E_{\mathbf p}\lvert\mathbf p\rangle.
$$

An $N$-particle state is built by applying $N$ creation operators, and its free energy is the sum of the individual mode energies.

That is the bridge between the oscillator algebra and the particle interpretation.

## Worked example: one mode in a box

Take one independent real mode with frequency $\omega$. Its Hamiltonian is

$$
H=\frac12(P^2+\omega^2Q^2).
$$

Define

$$
a=\sqrt{\frac{\omega}{2}}Q+\frac{i}{\sqrt{2\omega}}P.
$$

Then

$$
Q=\frac{a+a^\dagger}{\sqrt{2\omega}},
\qquad
P=-i\sqrt{\frac{\omega}{2}}(a-a^\dagger).
$$

Substituting gives

$$
\begin{aligned}
P^2+\omega^2Q^2
&=-\frac{\omega}{2}(a-a^\dagger)^2
+\frac{\omega}{2}(a+a^\dagger)^2 \\
&=\omega(aa^\dagger+a^\dagger a).
\end{aligned}
$$

Therefore

$$
H=\frac{\omega}{2}(aa^\dagger+a^\dagger a)
=\omega\left(a^\dagger a+\frac12\right),
$$

where $aa^\dagger=a^\dagger a+1$ was used in the last step.

## Common pitfalls

A few traps are responsible for many early sign and normalization errors.

First, $a^\dagger$ is not the complex conjugate of $a$ after quantization. It is the Hermitian adjoint operator. Before quantization, one may use complex mode coefficients. After quantization, those coefficients become noncommuting operators.

Second, $N=a^\dagger a$ counts excitations of a mode. In a free theory these excitations are particles. In an interacting theory, particle number is generally not conserved, and the particle interpretation is clearest for asymptotic states.

Third, the zero-point term is not a small correction. For infinitely many modes it is divergent. It can often be subtracted in flat-space QFT, but that subtraction is a choice in a larger physical context.

Fourth, real fields do not have independent positive- and negative-frequency oscillator sets. Complex fields do: one set creates particles and another creates antiparticles.

Fifth, gauge fields have unphysical oscillator-looking components before constraints are handled. Quantizing every component as an independent positive-norm oscillator gives the wrong theory.

## Relation to other topics

- [Linearization and Normal Modes](/foundations/classical-field-theory/linearization-and-normal-modes/) explains the classical quadratic-mode decomposition.
- [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/) explains why occupation-number states are the natural multiparticle basis.
- [Canonical Commutation Relations](/foundations/canonical-quantization/canonical-commutation-relations/) derives the equal-time field algebra from the mode algebra.
- [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/) applies this oscillator machinery to the real Klein–Gordon field.
- [Normal Ordering](/foundations/canonical-quantization/normal-ordering/) treats the zero-point energy and operator-ordering caveats.
- [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/) gives the graded analogue for fermionic modes.

## Research status

This page is textbook-standard material. Its assumptions are a free or quadratic bosonic system, a stable vacuum, and a set of physical normal modes after any constraints have been removed. The oscillator picture is exact for free fields and is the starting point for perturbation theory, but it is not by itself a nonperturbative definition of an interacting QFT.

## Exercises

### Exercise 1: Derive the oscillator commutator

Let

$$
a=\sqrt{\frac{\omega}{2}}Q+\frac{i}{\sqrt{2\omega}}P,
\qquad
 a^\dagger=\sqrt{\frac{\omega}{2}}Q-\frac{i}{\sqrt{2\omega}}P,
$$

with $[Q,P]=i$. Show that $[a,a^\dagger]=1$.

<details>
<summary><strong>Solution</strong></summary>

Only the cross terms contribute:

$$
\begin{aligned}
[a,a^\dagger]
&=\left[\sqrt{\frac{\omega}{2}}Q, -\frac{i}{\sqrt{2\omega}}P\right]
+\left[\frac{i}{\sqrt{2\omega}}P,\sqrt{\frac{\omega}{2}}Q\right] \\
&=-\frac{i}{2}[Q,P]+\frac{i}{2}[P,Q].
\end{aligned}
$$

Since $[Q,P]=i$ and $[P,Q]=-i$,

$$
[a,a^\dagger]=-\frac{i}{2}(i)+\frac{i}{2}(-i)=1.
$$

</details>

### Exercise 2: Recover the Hamiltonian

Using the inverse relations

$$
Q=\frac{a+a^\dagger}{\sqrt{2\omega}},
\qquad
P=-i\sqrt{\frac{\omega}{2}}(a-a^\dagger),
$$

show that

$$
\frac12(P^2+\omega^2Q^2)=\omega\left(a^\dagger a+\frac12\right).
$$

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
P^2=-\frac{\omega}{2}(a-a^\dagger)^2,
\qquad
\omega^2Q^2=\frac{\omega}{2}(a+a^\dagger)^2.
$$

Adding,

$$
P^2+\omega^2Q^2
=\frac{\omega}{2}\left[(a+a^\dagger)^2-(a-a^\dagger)^2\right].
$$

Expanding without commuting operators past each other gives

$$
(a+a^\dagger)^2-(a-a^\dagger)^2
=2aa^\dagger+2a^\dagger a.
$$

Thus

$$
\frac12(P^2+\omega^2Q^2)
=\frac{\omega}{2}(aa^\dagger+a^\dagger a)
=\omega\left(a^\dagger a+\frac12\right),
$$

where $aa^\dagger=a^\dagger a+1$.

</details>

### Exercise 3: Ladder action

Assume $N=a^\dagger a$ and $[a,a^\dagger]=1$. Show that

$$
[N,a^\dagger]=a^\dagger,
\qquad
[N,a]=-a.
$$

Then explain why $a^\dagger$ raises the occupation number and $a$ lowers it.

<details>
<summary><strong>Solution</strong></summary>

Use $[AB,C]=A[B,C]+[A,C]B$:

$$
[N,a^\dagger]=[a^\dagger a,a^\dagger]
=a^\dagger[a,a^\dagger]+[a^\dagger,a^\dagger]a
=a^\dagger.
$$

Similarly,

$$
[N,a]=[a^\dagger a,a]
=a^\dagger[a,a]+[a^\dagger,a]a
=-a.
$$

If $N\lvert n\rangle=n\lvert n\rangle$, then

$$
N(a^\dagger\lvert n\rangle)=(n+1)a^\dagger\lvert n\rangle,
$$

and

$$
N(a\lvert n\rangle)=(n-1)a\lvert n\rangle.
$$

So $a^\dagger$ raises and $a$ lowers the occupation number.

</details>

### Exercise 4: Mode completeness and the field delta function

Let

$$
\phi(\mathbf x)=\sum_n Q_nu_n(\mathbf x),
\qquad
\pi(\mathbf x)=\sum_n P_nu_n^*(\mathbf x),
$$

with $[Q_n,P_m]=i\delta_{nm}$. Assume the modes obey

$$
\sum_n u_n(\mathbf x)u_n^*(\mathbf y)=\delta^{(3)}(\mathbf x-\mathbf y).
$$

Show that

$$
[\phi(\mathbf x),\pi(\mathbf y)]=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

<details>
<summary><strong>Solution</strong></summary>

Compute directly:

$$
\begin{aligned}
[\phi(\mathbf x),\pi(\mathbf y)]
&=\sum_{n,m}u_n(\mathbf x)u_m^*(\mathbf y)[Q_n,P_m] \\
&=i\sum_{n,m}u_n(\mathbf x)u_m^*(\mathbf y)\delta_{nm} \\
&=i\sum_n u_n(\mathbf x)u_n^*(\mathbf y) \\
&=i\delta^{(3)}(\mathbf x-\mathbf y).
\end{aligned}
$$

</details>

### Exercise 5: The zero-point energy density

For a real scalar field in infinite volume, the zero-point energy density is formally

$$
\rho_0=\frac12\int\frac{d^3\mathbf p}{(2\pi)^3}\sqrt{\mathbf p^2+m^2}.
$$

With a sharp cutoff $|\mathbf p|<\Lambda$ and $\Lambda\gg m$, show that the leading divergence is proportional to $\Lambda^4$.

<details>
<summary><strong>Solution</strong></summary>

For large momentum,

$$
\sqrt{\mathbf p^2+m^2}\sim |\mathbf p|.
$$

Thus the leading part is

$$
\rho_0\sim \frac12\frac{4\pi}{(2\pi)^3}\int_0^\Lambda dp\,p^2p
=\frac{1}{4\pi^2}\frac{\Lambda^4}{4}
=\frac{\Lambda^4}{16\pi^2}.
$$

Mass-dependent terms are subleading at large $\Lambda$.

</details>

### Exercise 6: Compare two normalizations

Let

$$
a(\mathbf p)=\sqrt{2E_{\mathbf p}}\,b(\mathbf p),
$$

and assume

$$
[b(\mathbf p),b^\dagger(\mathbf p')]=(2\pi)^3\delta^{(3)}(\mathbf p-\mathbf p').
$$

Show that

$$
[a(\mathbf p),a^\dagger(\mathbf p')]
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p').
$$

<details>
<summary><strong>Solution</strong></summary>

Using the definition,

$$
[a(\mathbf p),a^\dagger(\mathbf p')]
=\sqrt{2E_{\mathbf p}}\sqrt{2E_{\mathbf p'}}
[b(\mathbf p),b^\dagger(\mathbf p')].
$$

Therefore

$$
[a(\mathbf p),a^\dagger(\mathbf p')]
=(2\pi)^3\sqrt{2E_{\mathbf p}}\sqrt{2E_{\mathbf p'}}
\delta^{(3)}(\mathbf p-\mathbf p').
$$

Because the delta function sets $\mathbf p'=\mathbf p$ inside smooth prefactors,

$$
\sqrt{2E_{\mathbf p}}\sqrt{2E_{\mathbf p'}}\delta^{(3)}(\mathbf p-\mathbf p')
=2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p').
$$

</details>

## References

### Primary references

- P. A. M. Dirac, “The Quantum Theory of the Emission and Absorption of Radiation,” *Proceedings of the Royal Society A* **114** (1927), for the creation-annihilation operator viewpoint in quantum radiation theory.
- M. Born, W. Heisenberg, and P. Jordan, “Zur Quantenmechanik II,” *Zeitschrift für Physik* **35** (1926), for early canonical quantization ideas applied to field-like oscillator systems.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 2, for the occupation-number route to oscillator operators and Fock space.
- M. Srednicki, *Quantum Field Theory*, §3, for canonical quantization of the scalar field and the Hamiltonian as a sum of oscillator energies.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §7.1, for canonical variables and the equal-time algebra in general free fields.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.3 and I.8, for the “mattress to field” intuition and canonical quantization.

### For a first pass

- Coleman, ch. 2.
- Srednicki, §3.
- Zee, ch. I.8.

### For mathematical precision

- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, Vol. II, for self-adjointness and spectral theory of quantum Hamiltonians.
- R. Haag, *Local Quantum Physics*, for the limitations of taking Fock-space oscillator language as fundamental in interacting QFT.

## Version history

- **2026-05-22:** Initial qft.org page on oscillator modes, ladder operators, field-mode quantization, continuum normalizations, zero-point energy, pitfalls, and exercises.
