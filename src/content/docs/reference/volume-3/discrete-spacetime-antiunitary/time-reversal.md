---
title: "Time Reversal"
description: "Defines time reversal as an antiunitary symmetry in Lorentzian QFT, derives its action on states, fields, currents, electromagnetic fields, spinors, and response terms, and explains Kramers degeneracy and time-reversal-odd observables."
sidebar:
  label: "Time Reversal"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki §§23, 40; Weinberg Vol. I §§2.2, 2.6; Coleman, Lectures on QFT ch. 22; Schwartz ch. 11; standard discrete-symmetry and antiunitary-symmetry treatments."
topics:
  - time reversal
  - antiunitary symmetry
  - discrete spacetime symmetry
  - Kramers degeneracy
  - time-reversal parity
  - Dirac bilinears
  - electromagnetic fields
  - topological terms
canonicalTopics:
  - time-reversal
  - antiunitary-symmetry
  - kramers-degeneracy
  - time-reversal-square
  - dirac-bilinears
  - topological-theta-term
researchStatus:
  established:
    - "Time reversal in Lorentzian quantum theory is represented antiunitarily; it complex-conjugates coefficients, reverses momenta and angular momenta, and may square to an internal symmetry such as fermion parity."
    - "The transformation rules for scalar fields, spinor bilinears, currents, electromagnetic fields, and ordinary response coefficients are standard QFT material."
  active:
    - "Time reversal remains active in modern QFT through reflection positivity, Pin structures, fermionic phases, parity anomalies, time-reversal anomalies, topological response, and duality-dependent symmetry realizations."
---

## Summary

Time reversal compares a process with the process in which motion is reversed. In Lorentzian quantum theory it is represented by an **antiunitary** operator, denoted $\Theta$ on this page:

$$
\Theta i\Theta^{-1}=-i.
$$

This minus sign is the central fact. It is why time reversal can reverse momenta while preserving positive energy, why magnetic fields are time-reversal odd, why spin flips, why Kramers degeneracy exists, and why sign tables involving explicit factors of $i$ must be handled with care.

The spacetime argument of a local operator is reflected as

$$
(t,\mathbf x)\mapsto(-t,\mathbf x),
$$

so one often writes

$$
\Theta\mathcal O_a(t,\mathbf x)\Theta^{-1}
=R_T{}_a{}^b\mathcal O_b(-t,\mathbf x).
$$

But this compact formula hides anti-linearity:

$$
\Theta(c_1\mathcal O_1+c_2\mathcal O_2)\Theta^{-1}
=c_1^*\Theta\mathcal O_1\Theta^{-1}
+c_2^*\Theta\mathcal O_2\Theta^{-1}.
$$

<figure class="doc-figure" style="--figure-width: 56rem;">

![Time reversal reflects the time coordinate, complex-conjugates coefficients, reverses momenta, spin, current, and magnetic field, and leaves position, charge density, and electric field even.](/figures/symmetry-anomalies-topology/time-reversal-antiunitary-map.svg)

<figcaption>

Time reversal is a reflection of operator insertions across a time slice plus an antiunitary action on the Hilbert space. Position and charge density are even. Momentum, angular momentum, spin, electric current, and magnetic field are odd. The electric field is even. The antiunitary rule $\Theta i\Theta^{-1}=-i$ is essential, not decorative.

</figcaption>
</figure>

The most useful slogan is

$$
\text{time reversal reverses motion, not energy.}
$$

In a time-reversal-invariant system,

$$
\Theta H\Theta^{-1}=H,
$$

not $\Theta H\Theta^{-1}=-H$.

## Prerequisites

Read [Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/parity/) before this page. You should also know [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/), [Projective Representations Preview](/symmetry-anomalies-topology/ordinary-global-symmetries/projective-representations-preview/), and [Charges Acting on Local Operators](/symmetry-anomalies-topology/noether-currents-ward-identities/charges-acting-on-local-operators/).

We use the mostly-minus metric and gamma-matrix convention

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
\qquad
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}.
$$

For spinors,

$$
\bar\psi=\psi^\dagger\gamma^0,
\qquad
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3.
$$

## Core idea

Time reversal is not merely the instruction “replace $t$ by $-t$.” It is a quantum symmetry operation that reverses time evolution:

$$
\Theta U(t)\Theta^{-1}=U(-t),
\qquad
U(t)=e^{-iHt}.
$$

If $\Theta$ were unitary and $\Theta H\Theta^{-1}=H$, then

$$
\Theta e^{-iHt}\Theta^{-1}=e^{-iHt},
$$

which is not $U(-t)$. Antiunitarity fixes this because it conjugates $i$:

$$
\Theta e^{-iHt}\Theta^{-1}
=e^{+i(\Theta H\Theta^{-1})t}.
$$

Therefore, if

$$
\Theta H\Theta^{-1}=H,
$$

then

$$
\Theta U(t)\Theta^{-1}=e^{+iHt}=U(-t).
$$

This is the clean derivation of antiunitarity. Time reversal is not chosen to be antiunitary because spinor matrices are annoying. Spinor matrices are annoying because time reversal is antiunitary.

:::note[Convention-sensitive source note]
Many references write the transformation as $T^{-1}\mathcal O(t)T$ rather than $\Theta\mathcal O(t)\Theta^{-1}$. This page uses $\Theta$ for the antiunitary Hilbert-space operator and writes transformed operators as $\Theta\mathcal O\Theta^{-1}$. Translate source formulas by tracking both the side on which the inverse appears and the complex conjugation of coefficients.
:::

## Setup and notation

We use three pieces of notation.

| Symbol | Meaning |
|---|---|
| $\tau$ | The time-reflection map on arguments: $\tau(t,\mathbf x)=(-t,\mathbf x)$. |
| $\Theta$ | The antiunitary Hilbert-space operator implementing time reversal, when it exists. |
| $\eta_T$ | An intrinsic time-reversal sign, phase, or matrix acting on fields or species labels. |

For a multiplet of local operators,

$$
\Theta\mathcal O_a(t,\mathbf x)\Theta^{-1}
=R_T{}_a{}^b\mathcal O_b(-t,\mathbf x).
$$

Because $\Theta$ is antiunitary, applying it twice gives a complex-conjugated product. For a field multiplet with

$$
\Theta\Phi\Theta^{-1}=U_T\Phi\circ\tau,
$$

the square acts as

$$
\Theta^2:\Phi\mapsto U_TU_T^*\Phi.
$$

This is why the invariant square of time reversal is not simply $U_T^2$.

Depending on the system, time reversal can obey

$$
\Theta^2=1,
\qquad
\Theta^2=-1,
\qquad
\Theta^2=(-1)^F,
$$

or can square to another internal symmetry. For an isolated spin-$s$ quantum-mechanical particle with the standard rotational action,

$$
\Theta^2=(-1)^{2s}.
$$

For fermionic QFTs, the relation $\Theta^2=(-1)^F$ is often the natural global statement.

## Position, momentum, and spin

For a nonrelativistic particle,

$$
\Theta\mathbf X\Theta^{-1}=\mathbf X,
\qquad
\Theta\mathbf P\Theta^{-1}=-\mathbf P.
$$

The canonical commutator is compatible with this precisely because $\Theta$ is antiunitary. Acting on the commutator gives

$$
\Theta[X^i,P^j]\Theta^{-1}
=\Theta(i\delta^{ij})\Theta^{-1}
=-i\delta^{ij}.
$$

The transformed operators obey

$$
[\Theta X^i\Theta^{-1},\Theta P^j\Theta^{-1}]
=[X^i,-P^j]
=-i\delta^{ij}.
$$

Angular momentum reverses:

$$
\mathbf L=\mathbf X\times\mathbf P
\quad\Longrightarrow\quad
\Theta\mathbf L\Theta^{-1}=-\mathbf L.
$$

Spin reverses too:

$$
\Theta\mathbf S\Theta^{-1}=-\mathbf S.
$$

Therefore helicity is time-reversal even:

$$
h=\frac{\mathbf S\cdot\mathbf P}{|\mathbf P|}
\quad\Longrightarrow\quad
h\mapsto h.
$$

This contrasts with parity, where $\mathbf P$ flips but spin does not. Parity flips helicity; time reversal preserves it.

## Scalars and canonical fields

For a real scalar field, a standard time-reversal action is

$$
\Theta\phi(t,\mathbf x)\Theta^{-1}
=\eta_T\phi(-t,\mathbf x),
\qquad
\eta_T=\pm1.
$$

For the usual kinetic term, the canonical momentum

$$
\pi(t,\mathbf x)=\partial_t\phi(t,\mathbf x)
$$

transforms as

$$
\Theta\pi(t,\mathbf x)\Theta^{-1}
=-\eta_T\pi(-t,\mathbf x).
$$

The free scalar Lagrangian

$$
\mathcal L=\frac12(\partial_t\phi)^2
-\frac12(\nabla\phi)^2
-\frac12m^2\phi^2
$$

is invariant for either $\eta_T=+1$ or $\eta_T=-1$. Time derivatives change sign, but they appear quadratically.

If $a$ is time-reversal odd and $\phi$ is time-reversal even, then

$$
a\phi^2
$$

is time-reversal odd, while

$$
a^2\phi^2
$$

is time-reversal even.

## Complex fields and charge

For a complex scalar multiplet,

$$
\Theta\phi_I(t,\mathbf x)\Theta^{-1}
=(U_T)_I{}^J\phi_J(-t,\mathbf x),
$$

where $U_T$ is a unitary matrix on species labels. Antiunitarity means that the time-reversal square is

$$
U_TU_T^*,
$$

not $U_T^2$.

Time reversal should not be confused with charge conjugation. Antiunitarity conjugates complex coefficients, but it does not automatically map a charged field to its Hermitian conjugate. In ordinary electromagnetic systems, time reversal preserves electric charge:

$$
\Theta Q\Theta^{-1}=Q.
$$

Charge conjugation, by contrast, reverses it:

$$
\mathcal C Q\mathcal C^{-1}=-Q.
$$

This distinction is one of the most common sources of mistakes in discrete-symmetry tables.

## Currents and charges

For an ordinary conserved number current,

$$
\partial_\mu j^\mu=0,
$$

time reversal acts as

$$
\Theta j^0(t,\mathbf x)\Theta^{-1}=+j^0(-t,\mathbf x),
$$

$$
\Theta j^i(t,\mathbf x)\Theta^{-1}=-j^i(-t,\mathbf x).
$$

The conserved charge

$$
Q=\int d^3\mathbf x\,j^0(t,\mathbf x)
$$

is therefore time-reversal even:

$$
\Theta Q\Theta^{-1}=Q.
$$

The spatial current is odd because it is charge flow. Reversing motion reverses flow.

:::note[Convention-sensitive source note]
A charge current under time reversal is usually summarized as $j^0$ even and $j^i$ odd. This is the physically useful convention for density and flow. It should not be naively replaced by the component rule for a passive Lorentz-coordinate time inversion. Time reversal here is an active antiunitary symmetry of the quantum theory.
:::

## Electromagnetic fields

Choose the gauge potential transformation

$$
\Theta A_0(t,\mathbf x)\Theta^{-1}=+A_0(-t,\mathbf x),
$$

$$
\Theta A_i(t,\mathbf x)\Theta^{-1}=-A_i(-t,\mathbf x),
$$

up to a gauge transformation. With

$$
\mathbf E=-\nabla A_0-\partial_t\mathbf A,
\qquad
\mathbf B=\nabla\times\mathbf A,
$$

we get

$$
\Theta\mathbf E(t,\mathbf x)\Theta^{-1}=+\mathbf E(-t,\mathbf x),
$$

$$
\Theta\mathbf B(t,\mathbf x)\Theta^{-1}=-\mathbf B(-t,\mathbf x).
$$

The Maxwell kinetic term is time-reversal even:

$$
F_{\mu\nu}F^{\mu\nu}=2(\mathbf B^2-\mathbf E^2).
$$

The theta density is time-reversal odd:

$$
F_{\mu\nu}\widetilde F^{\mu\nu}
=-4\mathbf E\cdot\mathbf B.
$$

The overall sign convention in the last equation is not the important part. The invariant statement is that $\mathbf E$ is time-reversal even, $\mathbf B$ is time-reversal odd, and therefore $\mathbf E\cdot\mathbf B$ is time-reversal odd.

Thus a four-dimensional theta term

$$
S_\theta\propto\theta\int F\wedge F
$$

usually violates time reversal. If the theta angle is periodic, special values such as $\theta=0$ and $\theta=\pi$ may need separate analysis. At $\theta=\pi$, a theory may have a candidate time-reversal symmetry but also a mixed anomaly or spontaneous time-reversal breaking.

## Dirac fields

For a Dirac field, time reversal involves a spinor matrix and antiunitarity. A convenient abstract convention is

$$
\Theta\psi(t,\mathbf x)\Theta^{-1}
=\eta_T B_T\psi(-t,\mathbf x),
$$

where antiunitarity complex-conjugates the coefficients and $B_T$ is chosen so that the Dirac equation is mapped to itself. One common convention requires

$$
B_T\gamma^{0*}B_T^{-1}=\gamma^0,
\qquad
B_T\gamma^{i*}B_T^{-1}=-\gamma^i.
$$

In a standard Dirac basis, a common choice is

$$
B_T=i\gamma^1\gamma^3,
$$

up to phase and representation conventions.

The free Dirac Lagrangian

$$
\mathcal L=\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
$$

is invariant because three signs work together: $i$ is conjugated, the time derivative changes sign, and the spinor matrix flips the spatial gamma matrices appropriately.

Unlike parity, ordinary time reversal does not exchange left and right chirality. Using

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3,
$$

the conjugation of the explicit $i$ and the three spatial gamma-matrix signs combine so that $\gamma^5$ is effectively time-reversal even. This matches the helicity result for massless particles: both momentum and spin reverse, so helicity is unchanged.

:::note[Convention-sensitive source note]
The exact matrix $B_T$ is representation-dependent. Some references write the transformation with an explicit complex conjugation on spinor components; others let antiunitarity do that work. The invariant content is that time reversal is antiunitary, reverses spin and momentum, preserves the free Dirac equation, and has a nontrivial square on spinor states.
:::

## Dirac bilinears

With the standard time-reversal action on Dirac fields, the common Hermitian bilinears transform as follows.

| Bilinear | Name | Time reversal |
|---|---|---|
| $\bar\psi\psi$ | scalar | even |
| $i\bar\psi\gamma^5\psi$ | pseudoscalar | odd |
| $\bar\psi\gamma^0\psi$ | vector charge density | even |
| $\bar\psi\gamma^i\psi$ | vector current | odd |
| $\bar\psi\gamma^0\gamma^5\psi$ | axial charge density | even |
| $\bar\psi\gamma^i\gamma^5\psi$ | axial spin density | odd |

The factor of $i$ in the pseudoscalar matters. Charge conjugation does not conjugate this $i$; time reversal does.

The vector current behaves like charge density plus flow:

$$
j^0\mapsto+j^0,
\qquad
\mathbf j\mapsto-\mathbf j.
$$

The spatial axial current is related to spin density in the nonrelativistic limit, so it is time-reversal odd.

## Kramers degeneracy

Suppose

$$
\Theta H\Theta^{-1}=H
$$

and, on a Hilbert-space sector,

$$
\Theta^2=-1.
$$

If

$$
H|\psi\rangle=E|\psi\rangle,
$$

then

$$
H\Theta|\psi\rangle=E\Theta|\psi\rangle,
$$

so the time-reversed state has the same energy. It is also orthogonal to $|\psi\rangle$. Using antiunitarity,

$$
\langle\psi|\Theta\psi\rangle
=\langle\Theta^2\psi|\Theta\psi\rangle
=\langle-\psi|\Theta\psi\rangle
=-\langle\psi|\Theta\psi\rangle.
$$

Therefore

$$
\langle\psi|\Theta\psi\rangle=0.
$$

This is Kramers degeneracy. In many-fermion systems it is often phrased through

$$
\Theta^2=(-1)^F.
$$

Odd-fermion-number states then have Kramers partners, while even-fermion-number states need not.

## Response coefficients and backgrounds

Time reversal constrains response. The key rule is that sources must transform.

A magnetic field is time-reversal odd:

$$
\mathbf B\mapsto-\mathbf B.
$$

So a Hamiltonian with a fixed nonzero magnetic field generally satisfies

$$
\Theta H(\mathbf B)\Theta^{-1}=H(-\mathbf B),
$$

not $H(\mathbf B)$. The family of theories may be time-reversal covariant, while a particular background breaks time reversal.

The Hall response in $2+1$ dimensions is encoded by a Chern–Simons term

$$
S_{\mathrm{CS}}=\frac{k}{4\pi}\int A\wedge dA.
$$

This term is odd under time reversal. Therefore a strictly time-reversal-invariant gapped state cannot have an ordinary nonzero Hall conductivity unless some additional sector, boundary, anomaly, or symmetry-breaking background is involved.

The same source logic applies to chemical potentials, angular velocity, strain-rate sources, and thermal response. A parameter that couples to a time-reversal-odd operator must transform if the symmetry is to be preserved.

## Time reversal in path integrals

In the Lorentzian path integral, time reversal complex-conjugates the phase:

$$
e^{iS}\mapsto e^{-iS[\Phi^T]}
$$

before the time-reflection change of variables is accounted for. A time-reversal-invariant theory gives the expected complex-conjugate relation between amplitudes and reversed amplitudes.

In Euclidean QFT, the related structural property is reflection positivity. Euclidean time reflection is not just a sign rule; it is an antilinear reflection operation used to build a positive Hilbert-space inner product after analytic continuation. This is why [Reflection Positivity and Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/reflection-positivity-and-time-reversal/) is a separate page.

## Time reversal, topology, and anomalies

Time reversal is sensitive to orientation, spin, and boundary structure. Chern–Simons terms in odd spacetime dimensions are time-reversal odd. Theta terms in four dimensions are time-reversal odd. Fermionic theories may require Pin structures to define time reversal globally.

A classical time-reversal rule can fail quantum mechanically if no regulator and counterterm choice preserves all required structures. In modern language, the diagnostic is the background-field partition function:

$$
Z[\mathcal B]\stackrel{?}{=}Z[\mathcal B^T]^*,
$$

possibly up to allowed local counterterms. Failure of this equality is an anomaly or an anomaly-inflow statement.

This is the modern home of time-reversal subtleties in topological phases, parity anomalies, fermion path integrals, and dualities.

## Common pitfalls

**Treating time reversal as unitary.** The relation $\Theta U(t)\Theta^{-1}=U(-t)$ requires antiunitarity in ordinary quantum mechanics.

**Saying time reversal sends energy to negative energy.** It reverses motion while preserving the Hamiltonian in a time-reversal-invariant theory. Momentum is odd; energy is even.

**Forgetting complex conjugation of coefficients.** Antiunitarity changes the sign of $i$. This affects pseudoscalars, Chern–Simons terms, path-integral phases, and spinor transformations.

**Confusing time reversal with charge conjugation.** Time reversal may complex-conjugate components or matrices, but it does not automatically reverse charge.

**Holding time-reversal-odd backgrounds fixed.** A magnetic field, Hall source, angular velocity, or other odd background must transform. Otherwise the background breaks time reversal.

**Assuming $\Theta^2=1$.** Spin and fermion parity matter. Many important systems have $\Theta^2=-1$ or $\Theta^2=(-1)^F$.

**Using parity sign tables for time reversal.** Parity leaves spin unchanged and flips momentum. Time reversal flips both. Electromagnetic fields also differ: under parity, $\mathbf E$ is odd and $\mathbf B$ is even; under time reversal, $\mathbf E$ is even and $\mathbf B$ is odd.

**Ignoring global structure.** On nontrivial manifolds or with fermions, time reversal requires more than local field signs. It may require Pin structures and anomaly data.

## Relations to other pages

[Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/parity/) is the unitary spatial-reflection cousin of this page.

[Charge Conjugation](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/charge-conjugation/) explains the charge-reversing operation that is often combined with parity and time reversal.

[Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/) explains why fixed sources and chemical potentials must transform when testing a symmetry.

The later pages on the CPT theorem, antiunitary symmetries, reflection positivity, spin structures, and discrete anomalies refine the global and Euclidean aspects of this page.

## Research status

The antiunitary representation of time reversal, the basic operator signs, Kramers degeneracy, and the standard transformations of scalar, spinor, current, and electromagnetic operators are established textbook QFT.

The research frontier begins when time reversal is imposed globally: fermionic path integrals, Pin structures, topological phases, boundaries, dualities, anomalies, and nonperturbative gauge dynamics. In those settings, the statement “the theory has time reversal” is not only a local sign table. It is a claim about the existence of a consistent action on all allowed backgrounds and all topological sectors.

A practical modern warning is that time reversal can be realized differently in dual descriptions. One description may realize it as geometric time reversal; another may realize it as time reversal combined with charge conjugation, a flavor rotation, a one-form symmetry operation, or a topological defect.

## Exercises

### Exercise 1: Why antiunitary?

Let $U(t)=e^{-iHt}$. Show that if $\Theta$ is antiunitary and $\Theta H\Theta^{-1}=H$, then

$$
\Theta U(t)\Theta^{-1}=U(-t).
$$

<details><summary><strong>Solution</strong></summary>

Antiunitarity gives

$$
\Theta i\Theta^{-1}=-i.
$$

Therefore

$$
\Theta e^{-iHt}\Theta^{-1}
=e^{+i(\Theta H\Theta^{-1})t}.
$$

If $\Theta H\Theta^{-1}=H$, this becomes

$$
\Theta e^{-iHt}\Theta^{-1}=e^{+iHt}=U(-t).
$$

</details>

### Exercise 2: Scalar canonical commutator

For a real scalar field with

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]=i\delta^3(\mathbf x-\mathbf y),
$$

assume

$$
\Theta\phi(t,\mathbf x)\Theta^{-1}=\phi(-t,\mathbf x),
$$

$$
\Theta\pi(t,\mathbf x)\Theta^{-1}=-\pi(-t,\mathbf x).
$$

Show that this is compatible with antiunitarity.

<details><summary><strong>Solution</strong></summary>

Acting with $\Theta$ on the commutator gives

$$
\Theta[\phi(t,\mathbf x),\pi(t,\mathbf y)]\Theta^{-1}
=\Theta(i\delta^3(\mathbf x-\mathbf y))\Theta^{-1}
=-i\delta^3(\mathbf x-\mathbf y).
$$

Using the transformed fields gives

$$
[\phi(-t,\mathbf x),-\pi(-t,\mathbf y)]
=-i\delta^3(\mathbf x-\mathbf y).
$$

The two sides agree.

</details>

### Exercise 3: Electromagnetic signs

Assume

$$
A_0(t,\mathbf x)\mapsto A_0(-t,\mathbf x),
\qquad
\mathbf A(t,\mathbf x)\mapsto-\mathbf A(-t,\mathbf x).
$$

Using

$$
\mathbf E=-\nabla A_0-\partial_t\mathbf A,
\qquad
\mathbf B=\nabla\times\mathbf A,
$$

show that $\mathbf E$ is time-reversal even and $\mathbf B$ is time-reversal odd.

<details><summary><strong>Solution</strong></summary>

For the electric field,

$$
-\nabla A_0(t,\mathbf x)
\mapsto
-\nabla A_0(-t,\mathbf x),
$$

and

$$
-\partial_t\mathbf A(t,\mathbf x)
\mapsto
-\partial_t[-\mathbf A(-t,\mathbf x)]
=-\partial_t\mathbf A(-t,\mathbf x).
$$

Thus $\mathbf E(t,\mathbf x)\mapsto\mathbf E(-t,\mathbf x)$.

For the magnetic field,

$$
\nabla\times\mathbf A(t,\mathbf x)
\mapsto
\nabla\times[-\mathbf A(-t,\mathbf x)]
=-\mathbf B(-t,\mathbf x).
$$

So $\mathbf B$ is time-reversal odd.

</details>

### Exercise 4: Kramers degeneracy

Suppose $\Theta H\Theta^{-1}=H$ and $\Theta^2=-1$. If $H|\psi\rangle=E|\psi\rangle$, show that $|\psi\rangle$ and $\Theta|\psi\rangle$ are degenerate and orthogonal.

<details><summary><strong>Solution</strong></summary>

First,

$$
H\Theta|\psi\rangle
=\Theta H|\psi\rangle
=E\Theta|\psi\rangle,
$$

where $E$ is real. Thus $\Theta|\psi\rangle$ has the same energy.

For orthogonality, use antiunitarity:

$$
\langle\psi|\Theta\psi\rangle
=\langle\Theta^2\psi|\Theta\psi\rangle
=\langle-\psi|\Theta\psi\rangle
=-\langle\psi|\Theta\psi\rangle.
$$

Therefore

$$
\langle\psi|\Theta\psi\rangle=0.
$$

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §§23 and 40. Discrete transformations of scalar and spinor fields.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, especially §§2.2 and 2.6. Wigner’s theorem, antiunitary transformations, space inversion, and time reversal.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 22. CPT and Fermi fields.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 11. Spinor solutions and discrete transformations.
- Eugene Wigner, *Group Theory and Its Application to the Quantum Mechanics of Atomic Spectra*. The classic source for unitary and antiunitary symmetry representations.
- R. Streater and A. Wightman, *PCT, Spin and Statistics, and All That*. The theorem-level background for time reversal and CPT in axiomatic QFT.
- Edward Witten, “Fermion Path Integrals and Topological Phases,” *Rev. Mod. Phys.* 88, 035001 (2016). Modern global aspects of time reversal, fermions, and topology.

## Version history

- 2026-06-17: Initial polished page. Added antiunitary derivation, operator conventions, scalar and spinor transformations, electromagnetic signs, bilinear table, Kramers degeneracy, response constraints, Euclidean reflection handoff, anomaly and topology warnings, and exercises with solutions.
