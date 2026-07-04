---
title: "Large-N CFTs"
description: "How large-N conformal field theories organize CFT data by factorization, single-trace and multi-trace operators, planar counting, vector models, and holographic limits."
sidebar:
  label: "Large-N CFTs"
  order: 9
level: Graduate
status: "Polished draft"
source: "'t Hooft 1974; Witten 1979; Rychkov lectures; Simmons-Duffin TASI lectures; Heemskerk et al. 2009; large-N and holographic bootstrap literature."
topics:
  - large-N CFT
  - factorization
  - single-trace operators
  - double-trace operators
  - holography
canonicalTopics:
  - large-n-cfts
  - large-n-factorization
  - single-trace-double-trace
researchStatus:
  established:
    - "Large-N CFTs have factorized correlators at leading order and organize spectra into single-trace-like and multi-trace-like sectors, with generalized free fields as the leading approximation for normalized single-trace correlators."
  active:
    - "Current research refines which large-N CFTs admit local AdS duals, how bulk locality emerges, how higher-spin symmetry is weakly broken, and how bootstrap constraints control 1/N corrections."
---

## Summary

A **large-$N$ CFT** is a family of conformal field theories labeled by a large parameter $N$ such that correlation functions simplify as $N\to\infty$. The central structural feature is **factorization**. For suitably normalized single-trace-like scalar operators,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\langle \mathcal O_1\mathcal O_2\rangle
\langle \mathcal O_3\mathcal O_4\rangle
+\text{pairings}
+\text{connected corrections}.
$$

At leading order, the connected correction is suppressed. Therefore each single-trace-like operator behaves like a generalized free field, and the OPE contains multi-trace families such as

$$
[\mathcal O\mathcal O]_{n,\ell},
\qquad
\Delta_{n,\ell}^{(0)}=2\Delta_{\mathcal O}+2n+\ell.
$$

Large-$N$ CFTs come in several flavors. Matrix or gauge-theory large $N$ often has

$$
C_T\sim N^2,
\qquad
\langle \mathcal O_1\cdots\mathcal O_m\rangle_{\rm conn}\sim N^{2-m}
$$

for normalized single-trace operators. Vector-model large $N$ often has

$$
C_T\sim N,
\qquad
\langle \mathcal O_1\cdots\mathcal O_m\rangle_{\rm conn}\sim N^{1-m/2}
$$

for suitable singlet single-particle-like operators.

Large $N$ is important because it turns complicated CFTs into perturbative problems in $1/N$. In holographic examples, it is also the CFT origin of weakly coupled bulk physics in AdS.

## Prerequisites

Read [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/), [Mean-Field Theory CFT](/cft-bootstrap/higher-dimensional-cft/mean-field-theory-cft/), [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/), and [Conformal Collider Bounds](/cft-bootstrap/higher-dimensional-cft/conformal-collider-bounds/) first.

You should know what conformal data are: operator dimensions, spin representations, and OPE coefficients. You should also know that $C_T$ normalizes the stress-tensor two-point function.

## Core idea

Large $N$ is a controlled expansion of CFT data. Instead of solving one theory at one value of a coupling, we study a sequence of theories whose correlators admit an expansion:

$$
\mathcal G(u,v)
=
\mathcal G^{(0)}(u,v)
+\frac{1}{N^p}\mathcal G^{(1)}(u,v)
+\frac{1}{N^{2p}}\mathcal G^{(2)}(u,v)
+\cdots .
$$

The leading term is often generalized free:

$$
\mathcal G^{(0)}(u,v)=
1+u^{\Delta}
+\left(\frac{u}{v}\right)^{\Delta}.
$$

The subleading terms contain actual dynamics: anomalous dimensions, corrected OPE coefficients, exchange of additional single-trace operators, and constraints from crossing.

The slogan is

$$
\text{large }N
\quad=\quad
\text{mean-field CFT}
+\text{controlled connected corrections}.
$$

The expansion parameter depends on the kind of large-$N$ limit. Matrix large $N$ and vector large $N$ have different counting, different spectra, and different possible bulk interpretations.

## Setup and normalization

Let $\mathcal O$ be a scalar single-trace-like primary normalized by

$$
\langle\mathcal O(x)\mathcal O(0)\rangle=\frac{1}{(x^2)^\Delta}.
$$

In a large-$N$ family, connected correlators are suppressed:

$$
\langle\mathcal O_1\cdots\mathcal O_m\rangle_{\rm conn}\to0
\qquad
(N\to\infty)
$$

for fixed $m>2$. The precise power of $N$ depends on the theory.

In matrix-like large-$N$ CFTs, one often chooses operators so that

$$
\langle\mathcal O\mathcal O\rangle\sim1,
\qquad
\langle\mathcal O_1\cdots\mathcal O_m\rangle_{\rm conn}\sim N^{2-m}.
$$

Thus three-point functions scale as

$$
\lambda_{\mathcal O_1\mathcal O_2\mathcal O_3}\sim \frac1N,
$$

and connected four-point functions scale as

$$
\langle\mathcal O\mathcal O\mathcal O\mathcal O\rangle_{\rm conn}\sim\frac1{N^2}.
$$

In vector-like large-$N$ CFTs, singlet correlators often scale instead as

$$
\langle\mathcal O_1\cdots\mathcal O_m\rangle_{\rm conn}\sim N^{1-m/2}.
$$

For both cases, factorization is the key. The powers tell you how strong interactions between the large-$N$ “particles” are.

## Single-trace and multi-trace language

The terms **single-trace** and **multi-trace** come from matrix gauge theory. If $\Phi$ is an $N\times N$ matrix field, a typical single-trace operator is

$$
\operatorname{Tr}(\Phi^2),
$$

while a double-trace operator is

$$
\operatorname{Tr}(\Phi^2)\operatorname{Tr}(\Phi^2).
$$

In a general CFT, the phrase “single-trace” is often used more broadly. It means a primary operator whose correlators scale like a single-particle excitation in the large-$N$ expansion.

The CFT Hilbert space then organizes into:

| Sector | CFT language | Bulk intuition when holographic |
|---|---|---|
| single-trace | elementary large-$N$ primaries | one-particle states |
| double-trace | $[\mathcal O_i\mathcal O_j]_{n,\ell}$ | two-particle states |
| triple-trace | composites of three single-trace operators | three-particle states |
| stress tensor | universal spin-two single-trace-like operator | graviton |
| conserved currents | symmetry currents | gauge fields in AdS |

This language is useful even when no literal matrix trace is present, but one should not forget its origin. In vector models, “single-trace” may mean a singlet bilinear such as

$$
\phi_i\phi_i,
$$

not a matrix trace.

## Factorization

Large-$N$ factorization says that products of single-trace-like operators behave classically at leading order. For normalized operators,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\langle \mathcal O_1\mathcal O_2\rangle
\langle \mathcal O_3\mathcal O_4\rangle
+
\langle \mathcal O_1\mathcal O_3\rangle
\langle \mathcal O_2\mathcal O_4\rangle
+
\langle \mathcal O_1\mathcal O_4\rangle
\langle \mathcal O_2\mathcal O_3\rangle
+O(N^{-p}).
$$

This is why generalized free fields appear. The leading connected correlator vanishes, so the leading four-point function is exactly the mean-field answer.

Factorization has two immediate consequences.

First, multi-trace dimensions are additive at leading order:

$$
\Delta_{[\mathcal O_i\mathcal O_j]_{n,\ell}}^{(0)}
=
\Delta_i+\Delta_j+2n+\ell.
$$

Second, interactions appear as small anomalous dimensions:

$$
\Delta_{[\mathcal O_i\mathcal O_j]_{n,\ell}}
=
\Delta_i+\Delta_j+2n+\ell+\gamma_{n,\ell}.
$$

The anomalous dimension $\gamma_{n,\ell}$ is suppressed by the large-$N$ expansion.

## Matrix large N and planarity

In gauge theories with gauge group such as $SU(N)$, the classic large-$N$ limit keeps the ’t Hooft coupling fixed:

$$
\lambda=g_{\rm YM}^2N
$$

as

$$
N\to\infty.
$$

Feynman diagrams can be drawn in double-line notation. Each diagram is associated with a two-dimensional surface, and its scaling is governed by topology:

$$
N^{2-2g-b},
$$

where $g$ is the genus and $b$ counts boundaries associated with operator insertions in a schematic sense.

Planar diagrams dominate:

$$
g=0.
$$

Nonplanar diagrams are suppressed by powers of

$$
\frac1{N^2}.
$$

This is the origin of the genus expansion and the connection to string theory:

$$
\frac1N
\quad\text{behaves like a string coupling}.
$$

In a conformal gauge theory, the planar limit organizes CFT data into leading planar values plus $1/N^2$ corrections.

## Vector large N

In vector models, the fundamental fields carry one index:

$$
\phi_i,
\qquad
i=1,\ldots,N.
$$

The singlet sector contains operators such as

$$
\phi_i\phi_i,
\qquad
\phi_i\partial_{\mu_1}\cdots\partial_{\mu_\ell}\phi_i-\text{traces}.
$$

The large-$N$ expansion is controlled by index loops, but the counting differs from matrix theories. Typically

$$
C_T\sim N,
$$

not $N^2$.

Vector models often have approximate higher-spin symmetry at large $N$. In the critical $O(N)$ model, for example, there is an infinite tower of nearly conserved higher-spin currents whose anomalous dimensions vanish as $N\to\infty$:

$$
\Delta_\ell
=
\ell+d-2+O\left(\frac1N\right).
$$

This is why vector models are associated holographically not with ordinary Einstein gravity, but with higher-spin theories in AdS.

## Large N and the stress tensor

The stress-tensor two-point coefficient grows with the number of degrees of freedom. In common large-$N$ families,

$$
C_T\sim N^2
$$

for matrix-like theories, and

$$
C_T\sim N
$$

for vector-like theories.

Since the stress tensor is normalized by its two-point function, its coupling to a normalized light single-trace scalar is suppressed. Ward identities imply that stress-tensor exchange in normalized scalar four-point functions scales like

$$
\frac{\Delta_\phi^2}{C_T}.
$$

Therefore, when

$$
C_T\to\infty,
$$

the stress tensor decouples from that correlator at leading order. This is the precise version of the stress-tensor caveat in generalized free fields.

The stress tensor still exists in the full CFT. It is just invisible at leading order in a restricted normalized correlator.

## Double-trace mixing

At leading order, double-trace operators can have degenerate dimensions. For example, if several single-trace scalars $\mathcal O_i$ exist, then different composites

$$
[\mathcal O_i\mathcal O_j]_{n,\ell}
$$

can share the same mean-field dimension.

At subleading order, interactions mix degenerate operators. One must diagonalize an anomalous-dimension matrix rather than assign a single number to a schematic composite.

This is a frequent source of confusion. The expression

$$
[\mathcal O\mathcal O]_{n,\ell}
$$

is often a label for a family. When there are multiple operators with the same quantum numbers, the true primaries are linear combinations.

The safe statement is:

$$
\text{large }N\text{ gives a multi-trace basis; interactions diagonalize it order by order.}
$$

## Holographic large N

A large-$N$ CFT is a candidate for a weakly coupled AdS dual only if it satisfies stronger conditions than factorization alone.

A standard holographic CFT has:

1. Large stress-tensor normalization:

$$
C_T\gg1.
$$

2. A sparse spectrum of low-dimension single-trace operators above the stress tensor and a small set of light fields.

3. A hierarchy separating low-spin single-particle states from heavy higher-spin or stringy states.

4. Controlled connected correlators compatible with local bulk interactions.

In such a theory,

$$
\frac1N
$$

or

$$
\frac1{\sqrt{C_T}}
$$

acts like the bulk gravitational coupling, while the gap to higher-spin single-trace operators controls the scale of bulk locality.

Not every large-$N$ CFT is holographic in the Einstein-gravity sense. Vector models are large-$N$ CFTs, but their natural duals involve higher-spin fields rather than only a small number of low-spin bulk fields.

## Large N as a bootstrap expansion

Crossing symmetry can be imposed order by order in $1/N$. Write

$$
\mathcal G=\mathcal G^{(0)}+\frac1{N^p}\mathcal G^{(1)}+\cdots .
$$

At leading order,

$$
\mathcal G^{(0)}=\mathcal G_{\rm MFT}.
$$

At first subleading order, crossing relates:

- anomalous dimensions of double-trace operators;
- corrections to double-trace OPE coefficients;
- exchange of single-trace operators;
- possible contact-term-like ambiguities.

This is the analytic bootstrap logic behind many holographic calculations. Instead of starting with a bulk Lagrangian, one can ask:

$$
\text{Which }1/N\text{ corrections to MFT are compatible with crossing, unitarity, and Regge behavior?}
$$

The answer often reconstructs the same structures as AdS effective field theory.

## Example: critical O(N) vector models

The $O(N)$ vector models are among the most important large-$N$ CFTs. The basic field transforms as a vector

$$
\phi_i,
\qquad
i=1,\ldots,N.
$$

The singlet scalar

$$
\sigma\sim \phi_i\phi_i
$$

plays a central role, though its precise definition depends on whether one uses a Hubbard–Stratonovich description or another formulation.

At $N=\infty$, the theory is close to a generalized free or constrained free description, depending on which operator sector is studied. At large but finite $N$, dimensions and OPE coefficients have expansions in

$$
\frac1N.
$$

In $2<d<4$, the critical $O(N)$ model is an interacting CFT. It has approximate higher-spin currents at large $N$:

$$
\Delta_\ell=\ell+d-2+O\left(\frac1N\right).
$$

This makes it a laboratory for higher-spin symmetry breaking, analytic bootstrap, and comparison with numerical bootstrap results at finite $N$.

## Example: large-N gauge CFTs

Gauge theories with matrix degrees of freedom are the classic setting for large $N$. Examples include conformal gauge theories in four dimensions, Chern–Simons–matter theories in three dimensions, and supersymmetric theories with known holographic duals.

In matrix large-$N$ CFTs, normalized single-trace operators have connected correlators suppressed as

$$
\langle \mathcal O_1\cdots\mathcal O_m\rangle_{\rm conn}\sim N^{2-m}.
$$

This means:

$$
\lambda_{\mathcal O\mathcal O\mathcal O}\sim \frac1N,
\qquad
\langle\mathcal O\mathcal O\mathcal O\mathcal O\rangle_{\rm conn}\sim\frac1{N^2}.
$$

The single-trace spectrum is analogous to one-particle states. Double-trace and higher-trace sectors are multiparticle states. If the theory has a sparse single-trace spectrum and a large gap to higher-spin single-trace operators, it may admit an effective gravitational dual in AdS.

## Large N versus weak coupling

Large $N$ is not the same as weak coupling.

The ’t Hooft coupling

$$
\lambda=g_{\rm YM}^2N
$$

can be small, large, or intermediate as $N\to\infty$. At small $\lambda$, perturbative Feynman diagrams may be reliable. At large $\lambda$, the same theory may be strongly coupled, but large-$N$ factorization can still hold.

In holographic examples, the classical gravity limit usually requires both:

$$
N\to\infty
$$

and a large gap or strong coupling condition that suppresses stringy corrections. The first controls quantum loops in the bulk; the second controls higher-derivative or string-scale corrections.

Thus:

$$
\text{large }N
\ne
\text{weak coupling}
\ne
\text{Einstein gravity dual}.
$$

These are related but distinct limits.

## Common pitfalls

**Do not say large $N$ always means $N^2$ degrees of freedom.** Matrix theories often have $C_T\sim N^2$, but vector models often have $C_T\sim N$.

**Do not confuse factorization with triviality.** Leading correlators factorize, but subleading connected correlators contain rich dynamics.

**Do not assume every large-$N$ CFT has an Einstein gravity dual.** A sparse single-trace spectrum and a large higher-spin gap are additional requirements.

**Do not treat double-trace operators as literal products without mixing.** At subleading order, operators with the same quantum numbers can mix and must be diagonalized.

**Do not confuse single-trace language with a Lagrangian trace.** The terminology is often generalized to any single-particle-like primary in a large-$N$ expansion.

**Do not forget the stress tensor.** It exists in the full CFT even when it decouples from a normalized correlator at leading order.

**Do not use one large-$N$ counting for all theories.** Matrix, vector, tensor, and supersymmetric theories can have different powers of $N$.

## Relations to other pages

This page follows [Mean-Field Theory CFT](/cft-bootstrap/higher-dimensional-cft/mean-field-theory-cft/) and explains why mean-field data arise as the leading approximation in large-$N$ CFTs.

It prepares [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/), [Gauge-Theory CFTs](/cft-bootstrap/higher-dimensional-cft/gauge-theory-cfts/), [Holographic CFT](/cft-bootstrap/holographic-cft/), and [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/). It also connects to [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/) through $C_T$ scaling and to [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/) through factorization.

For nonperturbative large-$N$ methods outside CFT, see the later large-$N$ pages in the nonperturbative QFT volume.

## Research status

Large-$N$ expansions, planar counting, factorization, vector models, and the single-trace/multi-trace organization of CFT data are established tools. Their role in AdS/CFT and conformal bootstrap is standard.

Active research concerns the boundary between large-$N$ CFT and local bulk physics: how sparse spectra imply locality, how Regge behavior constrains interactions, how higher-spin symmetry is broken, how finite-$N$ effects restore exact consistency, how tensor models fit into the landscape, and how numerical bootstrap can isolate large-$N$ solutions.

## Exercises

### Exercise 1

In a matrix-like large-$N$ CFT, normalized single-trace connected correlators scale as

$$
\langle \mathcal O_1\cdots\mathcal O_m\rangle_{\rm conn}\sim N^{2-m}.
$$

What are the scalings of the three-point and connected four-point functions?

<details><summary><strong>Solution</strong></summary>

Set $m=3$:

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle_{\rm conn}\sim N^{-1}.
$$

Set $m=4$:

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle_{\rm conn}\sim N^{-2}.
$$

Thus single-trace three-point coefficients are order $1/N$, and connected four-point functions are order $1/N^2$ in this normalization.

</details>

### Exercise 2

Why does large-$N$ factorization lead to generalized free fields?

<details><summary><strong>Solution</strong></summary>

Large-$N$ factorization says that connected correlators of normalized single-trace-like operators vanish at leading order. Therefore the leading four-point function is just the sum of pairwise contractions:

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\langle \mathcal O_1\mathcal O_2\rangle\langle \mathcal O_3\mathcal O_4\rangle
+\text{pairings}
+O(N^{-p}).
$$

This is exactly the Wick-like structure of generalized free field correlators. The operator need not be an ordinary free field; it is generalized free at leading order in the large-$N$ expansion.

</details>

### Exercise 3

Explain why $C_T\to\infty$ suppresses stress-tensor exchange in a normalized scalar four-point function.

<details><summary><strong>Solution</strong></summary>

The stress tensor two-point coefficient $C_T$ normalizes the stress-tensor conformal block contribution. Ward identities fix the scalar-scalar-stress-tensor coupling in terms of $\Delta_\phi$ and $C_T$. In common conventions, the squared OPE coefficient scales like

$$
\lambda_{\phi\phi T}^2\propto \frac{\Delta_\phi^2}{C_T}.
$$

Thus when $C_T\to\infty$ with $\Delta_\phi$ fixed, the stress-tensor contribution to the normalized four-point function is suppressed.

</details>

### Exercise 4

What extra condition, beyond large $N$, is needed for an Einstein-like holographic dual?

<details><summary><strong>Solution</strong></summary>

Large $N$ gives factorization and suppresses bulk quantum loops. An Einstein-like local AdS dual also needs a sparse low-dimension single-trace spectrum and a large gap to higher-spin or stringy single-trace operators. This gap suppresses higher-derivative and string-scale corrections, leaving a small number of low-spin bulk fields governed approximately by Einstein gravity.

</details>

### Exercise 5

Why is double-trace mixing unavoidable when several operators have the same quantum numbers?

<details><summary><strong>Solution</strong></summary>

At leading large $N$, schematic composites such as

$$
[\mathcal O_i\mathcal O_j]_{n,\ell}
$$

can have equal dimensions and identical spin and global symmetry quantum numbers. Subleading interactions do not respect the arbitrary basis of schematic products; they act as a matrix on the degenerate subspace. The true conformal primaries are eigenvectors of this anomalous-dimension matrix. Therefore one must diagonalize mixing rather than assign a single anomalous dimension to each schematic product.

</details>

## References

- G. ’t Hooft, “A planar diagram theory for strong interactions,” *Nuclear Physics B* **72** (1974).
- E. Witten, “Baryons in the 1/N expansion,” *Nuclear Physics B* **160** (1979).
- S. Coleman, *Aspects of Symmetry*, Cambridge University Press, 1985.
- M. Marino, *Instantons and Large N*, Cambridge University Press, 2015.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2016.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, “Holography from conformal field theory,” *Journal of High Energy Physics* **2009**.
- A. L. Fitzpatrick, J. Kaplan, D. Poland, and D. Simmons-Duffin, “The analytic bootstrap and AdS superhorizon locality,” *Journal of High Energy Physics* **2013**.
- I. R. Klebanov and A. M. Polyakov, “AdS dual of the critical O(N) vector model,” *Physics Letters B* **550** (2002).

## Version history

- 2026-07-01: First polished draft. Added factorization, single-trace and multi-trace organization, matrix and vector large-$N$ counting, stress-tensor scaling, holographic criteria, bootstrap expansion, examples, pitfalls, exercises, and references.
