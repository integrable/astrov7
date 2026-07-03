---
title: "Spin–Statistics Theorem"
description: "The spin–statistics theorem in local relativistic QFT: assumptions, statement, intuition, consequences, wrong-statistics failures, physical observables, ghosts, anyons, and common pitfalls."
sidebar:
  label: "Spin–Statistics"
  order: 8
---

## Summary

The spin–statistics theorem says that, in ordinary local relativistic QFT in three spatial dimensions,

$$
\boxed{\text{integer spin}\Longleftrightarrow \text{Bose statistics}},
\qquad
\boxed{\text{half-integer spin}\Longleftrightarrow \text{Fermi statistics}}.
$$

Equivalently, local integer-spin fields commute at spacelike separation, while local half-integer-spin fields anticommute at spacelike separation:

$$
[\Phi(x),\Phi(y)]=0,
\qquad
(x-y)^2<0,
$$

for bosonic fields, and

$$
\{\Psi_\alpha(x),\Psi_\beta(y)\}=0,
\qquad
(x-y)^2<0,
$$

for fermionic fields, with the appropriate adjoint or conjugate fields included when needed.

This is not a convention about notation. It is a structural theorem. The spin–statistics connection uses the same deep ingredients that keep QFT relativistic and causal: Lorentz invariance, locality, positive energy, a stable vacuum, and a positive-norm Hilbert space. If one tries to quantize a scalar field with anticommutators, or a spinor field with ordinary commutators, something essential breaks: locality, positivity, or both.

A compact way to state the theorem is through the graded local algebra:

| Field type | Spin | Local bracket | Particle statistics |
| --- | ---: | --- | --- |
| scalar, vector, tensor gauge-invariant field strength | integer | commutator | Bose–Einstein |
| Weyl, Dirac, Majorana spinor | half-integer | anticommutator | Fermi–Dirac |

Weinberg derives the connection in the general construction of causal fields and emphasizes that Lorentz invariance requires causality and antiparticles before the spin–statistics result emerges (Weinberg 1995, Vol. I, §§5.1–5.8). Srednicki places the theorem early, immediately after scalar-field quantization, as one of the first major structural constraints of local QFT (Srednicki 2007, §4). Zee stresses its physical impact: the Pauli exclusion principle, atomic structure, condensed matter, and many macroscopic phenomena rest on this connection (Zee 2010, ch. II.4).

<figure class="doc-figure" style="--figure-width: 50rem;">

![Spin-statistics theorem map](/figures/foundations/spin-statistics-theorem-map.svg)

<figcaption>

The spin–statistics theorem is a compatibility condition among Lorentz covariance, positive energy, locality, and Hilbert-space positivity. Integer-spin fields must use local commutators and half-integer-spin fields must use local anticommutators. Wrong-statistics fields are useful as formal devices only when at least one physical assumption, usually positivity, has been relaxed.

</figcaption>
</figure>

## Prerequisites

You should know [Bosons and Fermions](/foundations/relativistic-particles-and-fields/bosons-and-fermions/), [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/), [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/), [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/), [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/), [Lorentz Representations](/foundations/symmetry-and-spacetime/lorentz-representations/), and [Discrete Symmetries](/foundations/symmetry-and-spacetime/discrete-symmetries/).

:::note[Conventions]
We use the qft.org default mostly-minus metric. A separation is spacelike when

$$
(x-y)^2<0.
$$

For two homogeneous operators, define the graded bracket by

$$
[A,B]_{\mathrm g}=AB-(-1)^{|A||B|}BA,
$$

where $|A|=0$ for bosonic or even operators and $|A|=1$ for fermionic or odd operators. Graded locality means

$$
[A(x),B(y)]_{\mathrm g}=0,
\qquad
(x-y)^2<0.
$$
:::

:::note[Assumptions]
The standard spin–statistics theorem assumes a relativistic local QFT in a positive-norm Hilbert space, with Poincaré invariance, positive energy, a stable vacuum, and local fields transforming covariantly. The theorem is not a theorem of arbitrary nonrelativistic many-body systems, indefinite-metric gauge-fixed systems, nonlocal theories, or QFTs in two spatial dimensions with braid statistics.
:::

## What the theorem says

For identical particles of spin $s$ in ordinary three-dimensional space, the exchange rule is

$$
a^\dagger(p,\sigma)a^\dagger(q,\tau)
=(-1)^{2s}
a^\dagger(q,\tau)a^\dagger(p,\sigma),
$$

so

$$
(-1)^{2s}=+1
\quad\text{for integer spin},
$$

and

$$
(-1)^{2s}=-1
\quad\text{for half-integer spin}.
$$

Thus a spin-zero particle is a boson, a photon is a boson, a massive vector particle is a boson, and a spin-one-half electron is a fermion.

In field language, the same statement is local. A scalar field is quantized so that

$$
[\phi(x),\phi(y)]=i\Delta(x-y),
$$

and the Pauli–Jordan function satisfies

$$
\Delta(x-y)=0
\qquad
\text{for spacelike }x-y.
$$

A Dirac field is quantized so that

$$
\{\psi_\alpha(x),\bar\psi_\beta(y)\}
=(i\gamma^\mu\partial_\mu+m)_{\alpha\beta}i\Delta(x-y),
$$

which also vanishes at spacelike separation. The bracket changes because the Lorentz representation changed.

The theorem is often remembered as a statement about particle exchange, but the sharper QFT statement is about local fields. Exchange statistics is what the local field algebra implies for multiparticle states.

## Why this is not a convention

In nonrelativistic quantum mechanics, one may build a many-body Hilbert space using symmetric or antisymmetric wavefunctions. The spin of the particles does not by itself force the choice. That is why bosonic and fermionic cold-atom models can be written as separate nonrelativistic theories.

Relativistic local QFT is more rigid. The same operator must satisfy three demands at once:

1. it must transform in a Lorentz representation;
2. it must create and annihilate positive-energy particles;
3. its local algebra must prevent spacelike separated operations from influencing one another.

The spin–statistics theorem says that these demands are compatible only with the usual spin-statistics pairing. The sign is not appended after quantization. It is part of making the local relativistic field exist as a physical operator.

## Locality as the first diagnostic

The easiest way to feel the theorem is to try the wrong sign.

For the free real scalar field,

$$
\phi(x)=\int d\mu(p)
\left[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

with

$$
[a(\mathbf p),a^\dagger(\mathbf q)]
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q),
$$

one obtains

$$
[\phi(x),\phi(y)]=i\Delta(x-y),
$$

and the right-hand side vanishes outside the light cone. This is microcausality.

If one replaces the commutator by an anticommutator while keeping the same scalar mode expansion, the corresponding anticommutator contains

$$
\Delta^+(x-y)+\Delta^+(y-x),
$$

not the Pauli–Jordan difference. That sum does not vanish at spacelike separation. The wrong statistics has converted a local scalar field into an operator with spacelike tails.

Spinors work the other way. The Dirac field needs anticommutators so that the gamma-matrix differential operator multiplies the same Pauli–Jordan function. With ordinary commutators, one loses the compatible package of locality and positive energy.

## Positivity as the second diagnostic

Locality is not the only constraint. QFT also needs a physical Hilbert space with nonnegative norms and a Hamiltonian bounded below.

This is why one must be cautious with formal “wrong-statistics” fields. Faddeev–Popov ghosts, for example, are Lorentz-scalar fields with anticommuting Grassmann variables. They do not contradict spin–statistics because they are not physical particles in a positive-norm Hilbert space. They are gauge-fixing auxiliaries inside an indefinite or constrained description; they disappear from the physical state space after the gauge constraints or BRST cohomology are imposed.

That caveat is not a technicality. It is exactly where the theorem’s assumptions are being bypassed.

## Exchange and rotation intuition

There is a famous geometric intuition behind the theorem. In three spatial dimensions, exchanging two identical particles twice can be continuously related to a $2\pi$ rotation. A spin-$s$ state acquires the phase

$$
e^{2\pi i s}=(-1)^{2s}
$$

under a full rotation. This suggests that integer-spin particles should return with a plus sign and half-integer-spin particles with a minus sign.

That picture is useful, but it is not the proof. The proof has to explain why the exchange operation is tied to local relativistic fields and why the Hilbert space stays positive. Topology supplies the smell of the theorem; locality and positivity supply the theorem.

## What is actually local

A fermionic field is not itself a directly measurable bosonic observable. It is an odd operator. Two fermionic fields anticommute at spacelike separation, but physical observables built from an even number of fermionic fields commute at spacelike separation.

For example, if $\psi(x)$ and $\psi(y)$ are spacelike separated, then schematically

$$
\{\psi(x),\psi(y)\}=0,
\qquad
\{\psi(x),\bar\psi(y)\}=0,
$$

but bilinears such as

$$
\bar\psi\psi,
\qquad
\bar\psi\gamma^\mu\psi,
\qquad
\bar\psi\gamma^\mu\gamma^5\psi
$$

are even operators. Even local observables commute at spacelike separation:

$$
[\bar\psi\psi(x),\bar\psi\psi(y)]=0,
\qquad
(x-y)^2<0.
$$

This is why fermions do not allow superluminal signaling. The local algebra is graded, but the observable algebra is ordinary local.

## Path-integral viewpoint

In the path integral, Bose fields are ordinary commuting integration variables, while Fermi fields are Grassmann variables:

$$
Z_{\text{boson}}[J]
=\int \mathcal D\phi\,e^{iS[\phi]+i\int J\phi},
$$

and

$$
Z_{\text{fermion}}[\eta,\bar\eta]
=\int \mathcal D\psi\,\mathcal D\bar\psi\,
\exp\left(iS[\psi,\bar\psi]+i\int \bar\eta\psi+i\int\bar\psi\eta\right).
$$

The Grassmann character is not merely a calculational trick. It is the functional-integral way of encoding the same Fermi signs that appear in the operator algebra. Closed fermion loops carry an extra minus sign, fermionic correlation functions change sign under exchange of insertions, and the Gaussian integral gives a determinant rather than the inverse square root of a determinant.

The path integral makes the sign rules efficient. The operator theorem explains why those are the sign rules for physical spin-one-half particles.

## Consequences

The theorem has enormous reach.

For bosons, occupation numbers can be arbitrary:

$$
n_i=0,1,2,\ldots.
$$

This underlies Bose condensation, coherent states, classical field limits, and gauge-boson fields.

For fermions, one mode can be occupied at most once:

$$
(a_i^\dagger)^2=0,
\qquad
n_i=0,1.
$$

This is the Pauli exclusion principle. It is why atoms have shell structure, why ordinary matter is stable, why Fermi surfaces exist, and why fermion determinants appear throughout QFT.

The theorem also constrains model building. A proposed elementary local field with spin one-half and bosonic statistics is not an exotic ordinary particle; it is a signal that one of the assumptions of local relativistic QFT has been abandoned.

## Boundaries of the theorem

### Two spatial dimensions

In two spatial dimensions, the configuration space of identical particles has the braid group rather than the permutation group. Exchange phases need not be only $+1$ or $-1$; anyonic statistics become possible. This is not a counterexample to the ordinary spin–statistics theorem. It is a different topological setting.

### Gauge-fixed ghosts

Anticommuting scalar ghosts occur in gauge theory, but they are not physical asymptotic particles. They live in the gauge-fixed formalism and are removed from the physical Hilbert space. The theorem is about physical local relativistic QFT with positive norm.

### Nonrelativistic systems

Nonrelativistic many-body theories can be written with bosonic or fermionic fields. They inherit particle statistics from the system being modeled; they do not derive it from Lorentz invariance.

### Nonlocal or indefinite theories

Nonlocal models, higher-derivative theories with negative-norm states, and regulator fields may violate the naive spin-statistics pairing. Such fields are not counterexamples unless the full assumptions of the theorem are satisfied.

## Common pitfalls

**“Spin–statistics is just because of exchange symmetry.”** Exchange symmetry tells you that identical-particle states must carry a representation of the permutation group. It does not by itself tell you why spin one-half chooses the antisymmetric representation. The relativistic theorem supplies that link.

**“Fermion fields violate locality because they anticommute.”** The local algebra is graded. Fermionic fields anticommute at spacelike separation, while physical even observables commute.

**“Ghosts disprove the theorem.”** Ghosts evade the theorem’s positive-norm physical-particle assumption.

**“A minus sign under a full rotation is already the whole proof.”** It is a powerful intuition, but the theorem also needs locality, positivity, and relativistic covariance.

## Exercises

### Exercise 1: Wrong-statistics scalar field

Suppose one tries to quantize a real scalar field using anticommutators,

$$
\{a(\mathbf p),a^\dagger(\mathbf q)\}
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q).
$$

Show that the field anticommutator is proportional to

$$
\Delta^+(x-y)+\Delta^+(y-x),
$$

rather than the Pauli–Jordan function. Why is this bad for locality?

<details>
<summary><strong>Solution</strong></summary>

Using

$$
\phi(x)=\int d\mu(p)
\left[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

and the anticommutator algebra, the nonzero terms in $\{\phi(x),\phi(y)\}$ are

$$
\int d\mu(p)e^{-ip\cdot(x-y)}
+
\int d\mu(p)e^{ip\cdot(x-y)}.
$$

Thus

$$
\{\phi(x),\phi(y)\}
=\Delta^+(x-y)+\Delta^+(y-x),
$$

up to the conventional factors of $i$ used in defining $\Delta^+$. This is a sum of positive-frequency functions, not the difference that forms the Pauli–Jordan commutator.

At equal time and spatial separation $r=|\mathbf x-\mathbf y|$, this sum is proportional to

$$
\int\frac{d^3\mathbf p}{(2\pi)^3E_{\mathbf p}}\cos(\mathbf p\cdot\mathbf r),
$$

which is nonzero for $r>0$. Therefore the wrong-statistics scalar field does not vanish at spacelike separation. It is not a local scalar field in the physical sense.

</details>

### Exercise 2: Pauli exclusion from the fermion algebra

Let a single fermionic mode obey

$$
\{f,f^\dagger\}=1,
\qquad
\{f^\dagger,f^\dagger\}=0.
$$

Show that the mode has at most one particle.

<details>
<summary><strong>Solution</strong></summary>

The second anticommutator gives

$$
\{f^\dagger,f^\dagger\}=2(f^\dagger)^2=0.
$$

Therefore

$$
(f^\dagger)^2=0.
$$

Acting twice on the vacuum gives

$$
(f^\dagger)^2|0\rangle=0.
$$

So there is no two-particle state in the same mode. The allowed occupation numbers are $0$ and $1$.

</details>

### Exercise 3: Even fermion operators commute locally

Let $\psi_1,\psi_2$ be odd fermionic operators localized in one spacetime region, and let $\chi_1,\chi_2$ be odd fermionic operators localized in a spacelike separated region. Assume every $\psi_i$ anticommutes with every $\chi_j$. Show that

$$
[\psi_1\psi_2,\chi_1\chi_2]=0.
$$

<details>
<summary><strong>Solution</strong></summary>

Move the two $\psi$ operators through the two $\chi$ operators:

$$
\psi_1\psi_2\chi_1\chi_2.
$$

To rewrite this as $\chi_1\chi_2\psi_1\psi_2$, each of the two $\psi$ operators must cross each of the two $\chi$ operators. That gives four minus signs:

$$
(-1)^4=+1.
$$

Therefore

$$
\psi_1\psi_2\chi_1\chi_2
=\chi_1\chi_2\psi_1\psi_2,
$$

and hence

$$
[\psi_1\psi_2,\chi_1\chi_2]=0.
$$

This is the algebraic reason even fermion bilinears can be physical local observables.

</details>

### Exercise 4: Why ghosts are not counterexamples

Faddeev–Popov ghosts are Lorentz-scalar anticommuting fields. Explain why they do not contradict the spin–statistics theorem.

<details>
<summary><strong>Solution</strong></summary>

The theorem applies to physical particles in a positive-norm Hilbert space. Faddeev–Popov ghosts are not physical asymptotic particles. They are introduced by gauge fixing to represent a determinant in the path integral. The gauge-fixed state space is not the final physical Hilbert space; physical states are selected by constraints or BRST cohomology.

Thus ghosts evade the assumptions of the theorem. Their scalar spin and anticommuting algebra are allowed because they are auxiliary fields, not physical positive-norm scalar particles.

</details>

### Exercise 5: Anyons and the role of dimension

Why does the ordinary spin–statistics theorem allow only Bose and Fermi statistics in three spatial dimensions, while two spatial dimensions can support anyons?

<details>
<summary><strong>Solution</strong></summary>

In three spatial dimensions, exchanging identical particles is governed by the permutation group. Its one-dimensional unitary representations give only the phases $+1$ and $-1$.

In two spatial dimensions, particle worldlines cannot always be untangled in the same way. The relevant group is the braid group, which has more possible phases and more general representations. Therefore exchange can produce phases other than $\pm1$, giving anyonic statistics.

This does not contradict the ordinary theorem. It changes one of the theorem’s background assumptions: the topology of configuration space in three spatial dimensions.

</details>

## Sources and further reading

- M. Srednicki, *Quantum Field Theory*, §4, for the spin-statistics theorem immediately after scalar-field quantization; §§37–39, for fermionic canonical quantization.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.1–5.8, for causal fields, the general spin-statistics connection, and its relation to the CPT theorem.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. II.4, for a physically vivid discussion of the spin-statistics connection and its consequences.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for a theorem-first axiomatic treatment.
- I. Duck and E. C. G. Sudarshan, *Pauli and the Spin-Statistics Theorem*, for historical and conceptual perspectives.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §3.5, for the canonical scalar and spinor field argument.

## Version history

- **2026-05-23:** Initial qft.org page on the spin–statistics theorem, assumptions, local graded brackets, wrong-statistics failures, exchange intuition, ghost and anyon caveats, and exercises.
