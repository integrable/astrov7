---
title: "Canonical Hamiltonian Definition"
description: "Defines the Hamiltonian route to nonperturbative QFT using regulated Hilbert spaces, local operators, spectra, constraints, and continuum limits."
sidebar:
  label: "Canonical Hamiltonian Definition"
  order: 6
level: Graduate
status: "Polished draft"
source: "Wightman; Kogut–Susskind; Srednicki; Schwartz; Glimm–Jaffe; Wilson–Kogut."
topics:
  - canonical quantization
  - Hamiltonian QFT
  - Hilbert space
  - local operator algebra
  - finite-volume spectra
  - gauge constraints
canonicalTopics:
  - nonperturbative-qft
  - canonical-hamiltonian-definition
  - hilbert-space-qft
  - finite-volume-spectrum
  - gauge-constraints
researchStatus:
  established:
    - "A regulated Hamiltonian QFT is a well-defined quantum system once its Hilbert space, self-adjoint Hamiltonian, local observables, symmetry action, constraints, and limiting prescription are specified."
  active:
    - "Continuum Hamiltonian constructions, chiral gauge theories, real-time dynamics, Hamiltonian truncation, tensor networks, and quantum simulation are active areas where the Hamiltonian viewpoint is powerful but technically delicate."
---

## Summary

A canonical Hamiltonian definition of a QFT starts from quantum mechanics rather than from a formal functional integral. The basic data are a Hilbert space $\mathcal H$, a Hamiltonian $H$, a family of local observables, and a rule for taking regulators away. At finite cutoff and finite volume, this should be an honest quantum system:

$$
H=H^\dagger,
\qquad
H\text{ is bounded below},
\qquad
\mathcal O(t)=e^{iHt}\mathcal O e^{-iHt}.
$$

For a nonperturbative definition, however, writing a formal continuum Hamiltonian density is not enough. One must say what the regulated Hilbert space is, what operators act on it, which constraints define the physical subspace, which counterterms are included, and which thermodynamic and continuum limits are being taken.

The Hamiltonian viewpoint is especially natural for spectra, real-time evolution, finite-volume states, symmetry representations, Gauss-law constraints, tensor networks, Hamiltonian truncation, and quantum simulation. It also gives the cleanest interpretation of the mass gap:

$$
\Delta(L)=E_1(L)-E_0(L),
\qquad
m_{\rm gap}=\lim_{L\to\infty}\Delta(L),
$$

when the limit exists in the sector being studied.

A useful slogan is

$$
\text{a Hamiltonian definition is QFT as a local quantum many-body system, with controlled limits.}
$$

## Prerequisites

You should have read [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/), [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/), and [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/). The relation to Euclidean correlators uses [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/) and [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/).

You should be comfortable with ordinary quantum mechanics, self-adjoint Hamiltonians, commutators, Heisenberg time evolution, and the idea that a lattice or momentum cutoff can turn a field theory into a large but finite quantum system.

## Core idea

The Lagrangian path integral treats spacetime nearly democratically. The Hamiltonian approach chooses a time direction and asks for a quantum system on a spatial slice. The price is that Lorentz symmetry is no longer manifest. The reward is that unitarity, states, spectra, and time evolution are visible from the start.

At finite cutoff, the construction has the flavor of quantum many-body physics:

| Ingredient | Hamiltonian role |
|---|---|
| Spatial regulator | Makes the number or density of degrees of freedom controllable. |
| Hilbert space $\mathcal H_{a,L}$ | The space of states before the continuum and infinite-volume limits. |
| Hamiltonian $H_{a,L}$ | Generates real-time dynamics and defines the spectrum. |
| Local observables $\mathcal A_{a,L}(R)$ | Operators associated with spatial regions $R$. |
| Constraints | Gauge invariance, Gauss laws, fermion parity, or other physical-state conditions. |
| Limits | The prescription for $L\to\infty$, $a\to0$, and parameter tuning. |

The object we want in the end is not merely one operator $H$. It is a compatible family of local quantum systems whose low-energy, long-distance observables converge to a QFT.

<figure class="doc-figure" style="--figure-width: 44rem;">

![A canonical Hamiltonian definition starts with regulated Hilbert-space data, extracts spectra and correlators, and then takes controlled infinite-volume and continuum limits.](/figures/nonperturbative-qft/hamiltonian-definition-map.svg)

<figcaption>

The Hamiltonian route begins with regulated local quantum-mechanical data. At fixed cutoff it gives spectra, matrix elements, real-time correlators, and Euclidean correlators via $e^{-\tau H}$. The QFT is obtained only after the thermodynamic and continuum limits have been specified.

</figcaption>
</figure>

## Setup and conventions

We use the conventions of [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/). In Lorentzian signature, Heisenberg evolution is

$$
\mathcal O(t)=e^{iHt}\mathcal O(0)e^{-iHt}.
$$

In finite spatial volume $L$, write the regulated Hilbert space as

$$
\mathcal H_{a,L},
$$

where $a$ denotes a UV regulator such as a spatial lattice spacing, a momentum cutoff, or a truncation parameter. The Hamiltonian is

$$
H_{a,L}:\mathcal D(H_{a,L})\subset\mathcal H_{a,L}\to\mathcal H_{a,L},
$$

and should be self-adjoint on an appropriate domain. At finite lattice spacing and finite local Hilbert-space dimension this is just a Hermitian matrix. For bosons, continuum fields, and gauge theories the domain issue is not cosmetic: unbounded operators and constraints must be handled carefully.

Euclidean time correlators are recovered from the Hamiltonian by inserting $e^{-\tau H}$. For example, if $0<\tau_1<\cdots<\tau_n$,

$$
\langle\Omega|\mathcal O_n e^{-(\tau_n-\tau_{n-1})H}\cdots
\mathcal O_2e^{-(\tau_2-\tau_1)H}\mathcal O_1|\Omega\rangle
$$

is the Hamiltonian version of a Euclidean Schwinger function. Conversely, a reflection-positive Euclidean lattice theory often gives a transfer matrix

$$
T\simeq e^{-a_\tau H},
$$

which reconstructs a Hamiltonian. This is the bridge between this page and [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/).

## Definition

A Hamiltonian nonperturbative definition of a QFT consists of the following data.

1. **A regulated family of Hilbert spaces.** For each cutoff and volume, there is a Hilbert space $\mathcal H_{a,L}$. On a spin lattice this may be a tensor product of finite-dimensional spaces. For bosonic lattice fields it may be an infinite-dimensional tensor product over finitely many sites. For gauge theory it is first a link Hilbert space and then a constrained physical subspace.

2. **A self-adjoint Hamiltonian bounded below.** The operator $H_{a,L}$ generates unitary time evolution at fixed cutoff. Usually one shifts it so that the ground-state energy is finite or normalized conveniently.

3. **A local structure.** The theory must say which operators are associated with which regions of space. On a lattice, an operator supported in $R$ acts only on sites or links contained in $R$ and a small neighborhood determined by the regulator.

4. **Symmetries and constraints.** The Hilbert space should carry the intended spatial symmetries, internal symmetries, fermion parity, gauge constraints, and superselection sectors. For gauge theories, the physical Hilbert space is not the full tensor product.

5. **A set of observables.** One must specify what is measured: spectra, matrix elements, correlation functions, Wilson loops, local composite operators, scattering amplitudes, response functions, or other quantities.

6. **A limiting prescription.** The continuum QFT is recovered only after specifying how bare parameters are tuned as $a\to0$ and how the volume is taken to infinity.

Symbolically,

$$
\{\mathcal H_{a,L},H_{a,L},\mathcal A_{a,L}(R),\text{constraints},\text{bare parameters}\}
\quad\xrightarrow[\text{limits}]{}\quad
\{\mathcal H,H,\mathcal A(R),\text{QFT observables}\}.
$$

The arrow is the hard part. It is where renormalization, universality, and nonperturbative existence questions live.

## Example: scalar field on a spatial lattice

A real scalar field in $d$ spacetime dimensions can be regulated on a spatial lattice with sites $\mathbf x$ and spacing $a$. A common Hamiltonian is

$$
H_{a,L}=a^{d-1}\sum_{\mathbf x}\left[
\frac12\pi_{\mathbf x}^2
+\frac12\sum_{i=1}^{d-1}\left(\frac{\phi_{\mathbf x+a\hat i}-\phi_{\mathbf x}}{a}\right)^2
+\frac12m_0^2\phi_{\mathbf x}^2
+\frac{\lambda_0}{4!}\phi_{\mathbf x}^4
\right].
$$

With this normalization, the lattice fields approximate continuum fields and obey

$$
[\phi_{\mathbf x},\pi_{\mathbf y}]=\frac{i}{a^{d-1}}\delta_{\mathbf x\mathbf y}.
$$

Equivalently, define canonical variables

$$
q_{\mathbf x}=a^{(d-1)/2}\phi_{\mathbf x},
\qquad
p_{\mathbf x}=a^{(d-1)/2}\pi_{\mathbf x},
$$

so that

$$
[q_{\mathbf x},p_{\mathbf y}]=i\delta_{\mathbf x\mathbf y}.
$$

At fixed $a$ and $L$, this is a finite collection of coupled quantum-mechanical degrees of freedom. The Hilbert space is

$$
\mathcal H_{a,L}=\bigotimes_{\mathbf x}L^2(\mathbb R,dq_{\mathbf x}),
$$

with the usual caveat that infinite-dimensional tensor products should be interpreted through the finite number of lattice sites in the box. The nonperturbative problem is not to formally quantize this finite system; that is ordinary quantum mechanics. The problem is to tune $m_0^2(a)$, $\lambda_0(a)$, and other allowed counterterms so that selected long-distance observables have a finite limit as $a\to0$ and $L\to\infty$.

The finite-volume spectrum gives immediate physical information. If $|n,L,a\rangle$ are eigenstates,

$$
H_{a,L}|n,L,a\rangle=E_n(L,a)|n,L,a\rangle,
$$

then the lowest excitation in a fixed symmetry sector estimates a mass or finite-volume energy level. Correlation functions reveal the same data through their spectral representation. For a local operator $\mathcal O$ with vacuum quantum numbers removed,

$$
C_{a,L}(\tau)=\langle0|\mathcal O(\tau)\mathcal O(0)|0\rangle
=\sum_n |\langle n|\mathcal O|0\rangle|^2e^{-\tau(E_n-E_0)}.
$$

Large Euclidean time filters the smallest energy difference coupled to $\mathcal O$. This is why Hamiltonian spectra and Euclidean lattice correlators are two languages for the same nonperturbative data.

## Example: gauge theory and the physical Hilbert space

Gauge theory adds a decisive lesson: the Hilbert space with simple local variables is usually too large. Physical states must obey constraints.

In Hamiltonian lattice gauge theory, the elementary variables live on spatial links. For gauge group $G$, a link variable $U_\ell\in G$ acts by multiplication, while electric fields $E^a_\ell$ generate left or right group translations. The unconstrained link Hilbert space is schematically

$$
\mathcal H_{\rm link}=L^2(G)
$$

for each link, and the total unconstrained space is a tensor product over links. Gauge transformations at vertices are generated by lattice Gauss-law operators $G^a_{\mathbf x}$. The physical Hilbert space is

$$
\mathcal H_{\rm phys}=\{|\psi\rangle: G^a_{\mathbf x}|\psi\rangle=0
\text{ for all }\mathbf x,a\}.
$$

A schematic Kogut–Susskind Hamiltonian has an electric term and a magnetic plaquette term:

$$
H_{\rm KS}\sim
\frac{g_0^2}{2}\sum_{\ell,a}(E^a_\ell)^2
+\frac{1}{g_0^2}\sum_{p}\left[N-\operatorname{Re}\operatorname{tr}U_p\right],
$$

where $U_p$ is the ordered product of link variables around a plaquette and $N$ is the dimension of the fundamental representation for $G=SU(N)$. The exact powers of the lattice spacing depend on spacetime dimension and normalization; the conceptual structure is the point here.

The gauge-theory example shows why a Hamiltonian definition is not just “choose fields and write $H$.” It must also identify the physical state space, gauge-invariant observables, global form of the gauge group, allowed line operators, boundary conditions, and sectors with external charges or fluxes.

## Spectra, gaps, and finite volume

The Hamiltonian formulation is the natural home of spectral questions. In a finite box, one obtains a discrete spectrum

$$
E_0(L)\leq E_1(L)\leq E_2(L)\leq\cdots.
$$

A mass gap is not the statement that $E_1(L)>E_0(L)$ at finite $L$; that is usually automatic in a finite quantum system. The physical question is whether an appropriate infinite-volume limit remains positive:

$$
m_{\rm gap}=\lim_{L\to\infty}\big(E_1(L)-E_0(L)\big)>0.
$$

The sector matters. In a theory with several superselection sectors, one may ask for the gap above the vacuum sector, the lightest charged excitation, the lowest flux-tube state, or the lowest state with prescribed momentum and global charges. In gauge theory, states with isolated charges may not even lie in the same Hilbert space as the vacuum unless external sources or boundary conditions are specified.

Finite volume is not merely a numerical trick. It determines how tunneling, spontaneous symmetry breaking, topological sectors, and zero modes are represented. For example, a finite-volume Hamiltonian with an exact symmetry generally has a symmetric ground state. Broken-symmetry vacua arise only after an infinite-volume or zero-source limit is taken with care.

This is one reason the Hamiltonian definition belongs in the same chapter as [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/). The order of limits is physics.

## Relation to Euclidean path integrals

The Hamiltonian and Euclidean routes are not enemies. When both are under control, they are two coordinatizations of the same theory.

Starting from a Hamiltonian, Euclidean correlators are matrix elements of $e^{-\tau H}$. For a vacuum state $|\Omega\rangle$,

$$
S_2(\tau,\mathbf x)=
\langle\Omega|\mathcal O(\tau,\mathbf x)\mathcal O(0,\mathbf 0)|\Omega\rangle
$$

with $\tau>0$ has the spectral form

$$
S_2(\tau,\mathbf x)=
\sum_n e^{-\tau(E_n-E_0)}
\langle\Omega|\mathcal O(0,\mathbf x)|n\rangle
\langle n|\mathcal O(0,\mathbf 0)|\Omega\rangle.
$$

Starting from a Euclidean lattice action, one may sometimes construct a transfer matrix $T$ between neighboring Euclidean time slices. If $T$ is positive and self-adjoint, one can define

$$
H=-\frac{1}{a_\tau}\log T
$$

up to an additive normalization. Reflection positivity is the Euclidean condition that makes this reconstruction compatible with a positive Hilbert-space inner product.

The caveat is important: not every Euclidean discretization has a manifestly positive transfer matrix at finite cutoff. Some improved lattice actions, gauge-fixed formulations, chiral fermion constructions, or complex actions may obscure or violate positivity before the continuum limit. The physical theory may still be unitary, but the proof is no longer automatic.

## Locality and operator algebras

A Hamiltonian by itself is not enough to define a local QFT. A completely arbitrary Hamiltonian on a huge Hilbert space might have the same low-energy spectrum as another system but different local physics. One needs a notion of which observables are localized where.

At finite spatial cutoff, locality often means that the Hamiltonian is a sum of terms supported on bounded regions:

$$
H_{a,L}=\sum_X h_X,
$$

where $X$ ranges over sites, links, plaquettes, or small neighborhoods. Operators supported in well-separated regions commute or graded-commute at equal time. In relativistic continuum QFT, locality becomes microcausality:

$$
[\mathcal O_1(x),\mathcal O_2(y)]_{\pm}=0
\quad\text{for spacelike-separated }x,y,
$$

where the graded commutator is used for fermionic operators.

This local structure is what makes the Hamiltonian a field theory rather than just a large quantum system. It also controls Lieb–Robinson-type bounds in lattice systems, relativistic causal propagation in continuum limits, and the meaning of local order parameters, defects, and line operators.

## Why the continuum Hamiltonian is subtle

In a free scalar theory, it is tempting to write

$$
H=\int d^{d-1}\mathbf x\left[
\frac12\pi^2+\frac12(\nabla\phi)^2+\frac12m^2\phi^2
\right]
$$

and declare victory. For a formal first course, this is fine. For a nonperturbative definition, several problems are hiding:

- Fields at a point are operator-valued distributions, not ordinary operators.
- Composite expressions such as $\phi^2(x)$, $\pi^2(x)$, and $\phi^4(x)$ require definition.
- Interactions require counterterms and sometimes vacuum-energy subtraction.
- Domains of unbounded operators must be specified.
- Gauge theories require constraints and physical observables.
- The continuum limit may fail, become trivial, or depend on how parameters are tuned.

The regulated Hamiltonian is therefore not a nuisance. It is often the definition. The continuum Hamiltonian is a limiting object that may exist only indirectly through its spectra, correlation functions, local algebras, or renormalized matrix elements.

## Checks on a Hamiltonian definition

A proposed Hamiltonian definition should pass several checks.

| Check | What to verify |
|---|---|
| Self-adjointness | Time evolution should be unitary at fixed regulator. |
| Stability | The spectrum should be bounded below after allowed subtractions. |
| Locality | Operators assigned to separated regions should commute or graded-commute appropriately. |
| Symmetry | The intended global, spacetime, and gauge symmetries should act correctly. |
| Regulator independence | Long-distance observables should be insensitive to microscopic choices after tuning. |
| Continuum scaling | Correlation lengths in cutoff units should diverge when $a\to0$. |
| Reflection/Euclidean compatibility | Euclidean correlators obtained from $e^{-\tau H}$ should satisfy positivity and clustering properties. |
| Physical-sector projection | Gauge constraints and superselection sectors should be implemented before interpreting spectra. |

A Hamiltonian can be perfectly well-defined as a quantum many-body model and still fail to define the continuum QFT one wanted. Conversely, two very different Hamiltonians can flow to the same continuum universality class.

## Common pitfalls

**Calling a formal Hamiltonian density a definition.** The expression $H=\int d^{d-1}x\,\mathcal H$ is usually a symbolic guide until regularization, renormalization, domains, and limits are supplied. This is especially true for interacting fields and gauge theories.

**Forgetting the physical Hilbert space in gauge theory.** The tensor product of link Hilbert spaces contains gauge-variant states. Physical spectra and matrix elements must be computed after imposing Gauss-law constraints or working entirely with gauge-invariant variables.

**Mistaking finite-volume gaps for mass gaps.** A finite box often has a discrete spectrum even when the infinite-volume theory is gapless. A mass gap is an infinite-volume statement in a specified sector.

**Assuming Lorentz symmetry is manifest.** Hamiltonian regularizations usually preserve spatial locality and time evolution, not full Lorentz invariance. Lorentz symmetry must be recovered in the continuum limit or imposed by a continuum construction.

**Ignoring operator locality.** A spectrum alone does not define a local QFT. The same energy levels can come with different local operator matrix elements, commutation relations, and symmetry actions.

**Taking limits in the wrong order.** Infinite volume, continuum limit, zero external source, and long-time projection do not always commute. Vacuum structure, confinement, and spontaneous symmetry breaking are particularly sensitive.

## Relations to other pages

- [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/) explains why the Hamiltonian is usually first defined in a box and why the order of limits matters.
- [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/) gives the path-integral version of the same cutoff logic and introduces lattice variables.
- [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/) explains how a regulated Hamiltonian family can flow toward a cutoff-independent QFT.
- [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/) explains when Euclidean data reconstruct the positive Hilbert space that this page takes as primary.
- [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/) explains why spectra, line operators, order parameters, and topological sectors are part of the nonperturbative data.

## Research status

The Hamiltonian definition is textbook-standard for regulated systems and for many continuum free theories. It is also the natural framework behind rigorous operator constructions, finite-volume spectra, Hamiltonian lattice gauge theory, and quantum many-body approaches.

The active frontier is not the slogan “QFT has a Hamiltonian.” The frontier is constructing and using Hamiltonians for strongly coupled continuum theories while controlling truncation errors, gauge constraints, chiral fermions, continuum extrapolations, and real-time dynamics. Hamiltonian truncation, tensor networks, light-front methods, and quantum simulation are modern expressions of this older canonical viewpoint.

For four-dimensional Yang–Mills theory, the Hamiltonian lattice theory is well-defined at nonzero cutoff. Proving that the continuum limit exists with the expected mass gap and physical properties is a much deeper mathematical problem.

## Exercises

### Exercise 1: Euclidean projection onto the ground state

Let $H$ have discrete eigenstates $|n\rangle$ with energies $E_n$, and let $|\psi\rangle=\sum_n c_n|n\rangle$ with $c_0\neq0$. Show that $e^{-\beta H}|\psi\rangle$, after normalization, approaches the ground state as $\beta\to\infty$ if $E_0<E_1$.

<details><summary><strong>Solution</strong></summary>

Write

$$
e^{-\beta H}|\psi\rangle=\sum_n c_ne^{-\beta E_n}|n\rangle
=e^{-\beta E_0}\left(c_0|0\rangle+
\sum_{n>0}c_ne^{-\beta(E_n-E_0)}|n\rangle\right).
$$

The common factor $e^{-\beta E_0}$ disappears after normalization. If $E_n-E_0>0$ for $n>0$, all excited-state terms are exponentially suppressed. The normalized state approaches $|0\rangle$ up to the phase of $c_0$.

</details>

### Exercise 2: Spectral form of a Euclidean two-point function

For a time-independent operator $\mathcal O$, derive

$$
C(\tau)=\langle0|\mathcal O(\tau)\mathcal O(0)|0\rangle
=\sum_n |\langle n|\mathcal O|0\rangle|^2e^{-\tau(E_n-E_0)}
$$

for $\tau>0$, assuming $\mathcal O(\tau)=e^{\tau H}\mathcal O e^{-\tau H}$ in Euclidean time.

<details><summary><strong>Solution</strong></summary>

Insert a complete set of energy eigenstates between the two operators:

$$
C(\tau)=\sum_n\langle0|e^{\tau H}\mathcal O e^{-\tau H}|n\rangle
\langle n|\mathcal O|0\rangle.
$$

Using $H|0\rangle=E_0|0\rangle$ and $H|n\rangle=E_n|n\rangle$ gives

$$
\langle0|e^{\tau H}\mathcal O e^{-\tau H}|n\rangle
=e^{\tau E_0}e^{-\tau E_n}\langle0|\mathcal O|n\rangle.
$$

If $\mathcal O$ is Hermitian, $\langle0|\mathcal O|n\rangle=\langle n|\mathcal O|0\rangle^*$, so

$$
C(\tau)=\sum_n |\langle n|\mathcal O|0\rangle|^2e^{-\tau(E_n-E_0)}.
$$

For non-Hermitian operators, the corresponding formula contains the appropriate conjugate operator.

</details>

### Exercise 3: Lattice commutator normalization

Let $q_{\mathbf x}=a^{(d-1)/2}\phi_{\mathbf x}$ and $p_{\mathbf x}=a^{(d-1)/2}\pi_{\mathbf x}$ obey $[q_{\mathbf x},p_{\mathbf y}]=i\delta_{\mathbf x\mathbf y}$. Derive the commutator for $\phi_{\mathbf x}$ and $\pi_{\mathbf y}$.

<details><summary><strong>Solution</strong></summary>

Substitute

$$
\phi_{\mathbf x}=a^{-(d-1)/2}q_{\mathbf x},
\qquad
\pi_{\mathbf y}=a^{-(d-1)/2}p_{\mathbf y}.
$$

Then

$$
[\phi_{\mathbf x},\pi_{\mathbf y}]
=a^{-(d-1)}[q_{\mathbf x},p_{\mathbf y}]
=\frac{i}{a^{d-1}}\delta_{\mathbf x\mathbf y}.
$$

This is the lattice version of $[\phi(\mathbf x),\pi(\mathbf y)]=i\delta^{(d-1)}(\mathbf x-\mathbf y)$, since $\delta^{(d-1)}(\mathbf x-\mathbf y)$ is represented by $\delta_{\mathbf x\mathbf y}/a^{d-1}$.

</details>

### Exercise 4: Why Gauss-law constraints commute with time evolution

Suppose a gauge-theory Hamiltonian satisfies $[H,G^a_{\mathbf x}]=0$ for all Gauss-law generators $G^a_{\mathbf x}$. Show that if $|\psi(0)\rangle$ is physical, then $|\psi(t)\rangle=e^{-iHt}|\psi(0)\rangle$ remains physical.

<details><summary><strong>Solution</strong></summary>

A physical state obeys

$$
G^a_{\mathbf x}|\psi(0)\rangle=0.
$$

Since $[H,G^a_{\mathbf x}]=0$, the generator commutes with $e^{-iHt}$. Therefore

$$
G^a_{\mathbf x}|\psi(t)\rangle
=G^a_{\mathbf x}e^{-iHt}|\psi(0)\rangle
=e^{-iHt}G^a_{\mathbf x}|\psi(0)\rangle
=0.
$$

The physical subspace is invariant under time evolution. This is why gauge-invariant Hamiltonians can be consistently restricted to the Gauss-law subspace.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, chapters on canonical quantization of scalar, spinor, and gauge fields, plus the chapters on Wilson loops, lattice theory, and confinement.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on Hamiltonians and Lagrangians, Hamiltonian derivation of perturbation theory, path integrals, Yang–Mills theory, and lattice gauge theory.
- K. G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” for the statistical-mechanics and transfer-matrix viewpoint behind continuum limits.

### Deeper references

- J. Kogut and L. Susskind, papers and reviews on Hamiltonian lattice gauge theory.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for rigorous Hamiltonian and Euclidean constructions.
- R. Haag, *Local Quantum Physics*, for the operator-algebraic viewpoint on local observables, states, and dynamics.
- I. Montvay and G. Münster, *Quantum Fields on a Lattice*, for transfer matrices, Hamiltonian limits, and lattice gauge-theory details.

## Version history

- **2026-06-26:** Initial polished page.
