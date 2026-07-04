---
title: "Mean-Field Theory CFT"
description: "How generalized-free-field correlators decompose into conformal blocks, producing the canonical mean-field spectrum of double-trace operators."
sidebar:
  label: "Mean-Field Theory CFT"
  order: 8
level: Graduate
status: "Polished draft"
source: "Rychkov lectures; Simmons-Duffin TASI lectures; Heemskerk, Penedones, Polchinski, and Sully 2009; analytic bootstrap literature."
topics:
  - mean-field theory
  - generalized free fields
  - conformal blocks
  - double-trace operators
  - large-N CFT
canonicalTopics:
  - mean-field-theory-cft
  - generalized-free-field-block-decomposition
  - double-trace-ope-data
researchStatus:
  established:
    - "Mean-field theory CFT gives an exact crossing-symmetric scalar four-point function whose conformal block decomposition contains identity exchange and a tower of double-trace primaries."
  active:
    - "Mean-field data remain the starting point for large-N perturbation theory, AdS effective field theory, analytic bootstrap, and numerical studies near generalized-free solutions."
---

## Summary

**Mean-field theory CFT** is the conformal block decomposition of generalized-free-field correlators. For an identical scalar primary $\phi$ of dimension $\Delta_\phi$, the normalized four-point function is

$$
\mathcal G_{\rm MFT}(u,v)
=
1+u^{\Delta_\phi}
+\left(\frac{u}{v}\right)^{\Delta_\phi}.
$$

This function is exactly crossing-symmetric. In the $\phi\times\phi$ OPE, it is reproduced by the identity plus an infinite tower of symmetric traceless double-trace primaries,

$$
[\phi\phi]_{n,\ell},
\qquad
\Delta_{n,\ell}^{(0)}=2\Delta_\phi+2n+\ell,
\qquad
n=0,1,2,\ldots ,
$$

with even $\ell$ for identical bosonic $\phi$.

The phrase “mean-field theory” here does not mean a microscopic Landau approximation with an order parameter set equal to its expectation value. It means the exact CFT data associated with disconnected, Wick-like correlators. These data are the zeroth-order solution around which large-$N$ CFTs, holographic correlators, and analytic bootstrap perturbation theory are organized.

The most important caveat is that mean-field CFT data by themselves usually do not define a complete local CFT with a stress tensor. They are best interpreted as a consistent crossing-symmetric sector, or as the $N\to\infty$ limit of a sector in a full large-$N$ CFT where the stress tensor effectively decouples from the chosen single-particle operator.

## Prerequisites

Read [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/), [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/), and [Identical Scalar Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/identical-scalar-bootstrap/) first.

You should know that a scalar four-point function can be expanded as

$$
\mathcal G(u,v)
=
\sum_{\mathcal O}
a_{\mathcal O}G_{\Delta,\ell}(u,v),
$$

where $G_{\Delta,\ell}$ is a conformal block and $a_{\mathcal O}$ is a squared OPE coefficient in a unitary identical-scalar normalization.

## Core idea

The generalized-free four-point function is simple in position space but nontrivial in the OPE. The term

$$
1
$$

is identity exchange in the $\phi\times\phi$ channel. The remaining two terms,

$$
u^{\Delta_\phi},
\qquad
\left(\frac{u}{v}\right)^{\Delta_\phi},
$$

must be reproduced by infinitely many conformal blocks.

This is the basic miracle of mean-field theory CFT:

$$
\text{disconnected correlator}
\quad\Longleftrightarrow\quad
\text{infinite tower of double-trace conformal blocks}.
$$

The tower has dimensions

$$
\Delta_{n,\ell}^{(0)}=2\Delta_\phi+2n+\ell.
$$

The superscript $(0)$ means “mean-field order.” In large-$N$ perturbation theory, interactions shift these dimensions:

$$
\Delta_{n,\ell}
=
2\Delta_\phi+2n+\ell
+\frac{1}{N^p}\gamma_{n,\ell}
+\cdots ,
$$

where $p=2$ in many matrix-like large-$N$ CFTs and $p=1$ in many vector-like large-$N$ CFTs.

Mean-field theory is therefore not merely a toy example. It is the free-particle kinematics of CFT.

## Setup and conventions

We consider an identical scalar primary $\phi$ in a unitary Euclidean CFT in $d>2$. The two-point function is normalized as

$$
\langle \phi(x)\phi(0)\rangle=\frac{1}{(x^2)^{\Delta_\phi}}.
$$

The four-point function is written

$$
\langle\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}
\mathcal G(u,v),
$$

with

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The mean-field four-point function is

$$
\mathcal G_{\rm MFT}(u,v)
=
1+u^{\Delta_\phi}
+\left(\frac{u}{v}\right)^{\Delta_\phi}.
$$

The conformal block expansion in the $12\to34$ channel is

$$
\mathcal G_{\rm MFT}(u,v)
=
1+
\sum_{n=0}^{\infty}
\sum_{\ell=0,2,4,\ldots}
a_{n,\ell}^{(0)}
G_{2\Delta_\phi+2n+\ell,\ell}(u,v),
$$

where the identity contribution is written separately. The coefficients

$$
a_{n,\ell}^{(0)}\ge0
$$

are completely fixed by crossing and by the normalization of conformal blocks. Their explicit closed form is useful in calculations, but it is convention-dependent; the spectrum and positivity are the invariant content.

## Why infinitely many operators are needed

In the OPE limit

$$
x_1\to x_2,
\qquad
u\to0,
$$

a conformal block behaves schematically like

$$
G_{\Delta,\ell}(u,v)\sim u^{(\Delta-\ell)/2}\times(\text{angular function of }v)
$$

up to descendants and normalization conventions. The identity gives the leading constant term.

The term

$$
u^{\Delta_\phi}
$$

has the right leading power for operators of twist

$$
\tau=\Delta-\ell=2\Delta_\phi+2n.
$$

Thus the MFT spectrum contains towers of fixed twist:

$$
\tau_n=2\Delta_\phi+2n.
$$

For each $n$, infinitely many spins appear:

$$
\ell=0,2,4,\ldots .
$$

This infinite spin tower is not an accident. It is the conformal block form of a two-particle continuum on the cylinder. A product of two identical generalized free quanta can carry arbitrary even angular momentum.

## Double-trace primaries

The double-trace primaries are schematically

$$
[\phi\phi]_{n,\ell}
\sim
\phi\,\partial_{\mu_1}\cdots\partial_{\mu_\ell}(\partial^2)^n\phi
-\text{traces}
-\text{descendants}.
$$

The phrase “schematically” is doing work. A primary operator is not obtained by simply writing a product of fields and derivatives. One must subtract descendants so that the operator is annihilated by the special conformal generators at the origin.

The labels have transparent meaning:

| Label | Meaning |
|---:|---|
| $n$ | radial excitation number, or number of two-derivative excitations |
| $\ell$ | spin under $SO(d)$ |
| $2\Delta_\phi$ | dimension of two generalized free quanta |
| $2n+\ell$ | derivative excitation energy |

The leading-twist operators have $n=0$:

$$
[\phi\phi]_{0,\ell},
\qquad
\Delta_{0,\ell}^{(0)}=2\Delta_\phi+\ell.
$$

These leading-twist operators play a central role in large-spin perturbation theory.

## OPE coefficients

The MFT OPE coefficients

$$
a_{n,\ell}^{(0)}
$$

are positive in a unitary normalization and can be written in closed form using Gamma functions or Pochhammer symbols. Their exact appearance depends on the convention used for scalar conformal blocks.

For this page, the important facts are:

1. They are fully determined by $\Delta_\phi$, $d$, and the block normalization.
2. They are nonnegative for unitary $\Delta_\phi$.
3. They decay in a controlled way at large $n$ and large $\ell$.
4. They become the zeroth-order data corrected in large-$N$ perturbation theory.

It is useful to write the block expansion as

$$
a_{n,\ell}
=
a_{n,\ell}^{(0)}
+\frac{1}{N^p}a_{n,\ell}^{(1)}
+\cdots ,
$$

and

$$
\Delta_{n,\ell}
=
\Delta_{n,\ell}^{(0)}
+\frac{1}{N^p}\gamma_{n,\ell}
+\cdots .
$$

The corrections $a_{n,\ell}^{(1)}$ and $\gamma_{n,\ell}$ are dynamical data. The leading MFT values are kinematic data.

## Mean-field crossing equation

For identical scalars, crossing can be written as

$$
v^{\Delta_\phi}\mathcal G(u,v)
=
u^{\Delta_\phi}\mathcal G(v,u).
$$

Substituting the MFT solution gives

$$
v^{\Delta_\phi}\left[
1+u^{\Delta_\phi}+\left(\frac{u}{v}\right)^{\Delta_\phi}
\right]
=
u^{\Delta_\phi}\left[
1+v^{\Delta_\phi}+\left(\frac{v}{u}\right)^{\Delta_\phi}
\right].
$$

Both sides are

$$
u^{\Delta_\phi}+v^{\Delta_\phi}+u^{\Delta_\phi}v^{\Delta_\phi}.
$$

So MFT solves crossing exactly before one has computed a single conformal block. The block decomposition is the harder statement: it says that the exact crossing-symmetric answer can be reproduced by a positive sum over conformal multiplets.

## Mean-field theory and free fields

The ordinary free scalar is a special point:

$$
\Delta_\phi=\frac{d-2}{2}.
$$

At this value, the scalar saturates the unitarity bound and obeys the null-state equation

$$
\partial^2\phi=0.
$$

For generic MFT,

$$
\Delta_\phi>\frac{d-2}{2},
$$

there is no local free equation of motion. The correlators still factorize, but the theory is not an ordinary local free scalar theory.

This difference shows up in the operator spectrum. The ordinary free scalar has additional shortening relations and a genuine local stress tensor. A generic generalized free field has neither. Its mean-field block decomposition is perfectly crossing-symmetric, but it is not usually a complete standalone local CFT.

A useful way to remember the distinction is:

$$
\text{ordinary free field}
=
\text{GFF}
+
\text{equation of motion}
+
\text{stress tensor}
+
\text{locality data}.
$$

## Stress-tensor caveat

A complete local CFT should have a conserved stress tensor with

$$
\Delta_T=d,
\qquad
\ell=2.
$$

The MFT double-trace spectrum contains spin-two operators with dimensions

$$
\Delta_{n,2}^{(0)}=2\Delta_\phi+2n+2.
$$

For a generic value of $\Delta_\phi$, no such operator has dimension $d$. Even when an accidental equality occurs, the Ward identity that makes an operator the stress tensor is not automatic.

This is why one often says that generalized free fields have

$$
C_T=\infty
$$

from the viewpoint of the $\phi$ sector. More precisely, in a large-$N$ CFT, the actual stress tensor exists but its coupling to a normalized single-trace-like scalar can be suppressed. In the strict large-$N$ limit, stress-tensor exchange can disappear from the connected four-point function of $\phi$, leaving the MFT answer.

This caveat prevents a common overstatement:

$$
\text{crossing-symmetric}
\quad\ne\quad
\text{complete local CFT}.
$$

## Perturbing mean-field theory

Mean-field theory becomes physically powerful when perturbed. Write

$$
\mathcal G(u,v)
=
\mathcal G_{\rm MFT}(u,v)
+\epsilon\,\mathcal G^{(1)}(u,v)
+\epsilon^2\mathcal G^{(2)}(u,v)
+\cdots .
$$

The parameter $\epsilon$ might be

$$
\frac{1}{N^2},
\qquad
\frac{1}{N},
\qquad
\varepsilon=4-d,
\qquad
\text{or another small coupling}.
$$

At first order, anomalous dimensions produce logarithms in the block expansion:

$$
u^{\Delta_{n,\ell}/2}
=
u^{\Delta_{n,\ell}^{(0)}/2}
\left[
1+\frac{\epsilon}{2}\gamma_{n,\ell}\log u+\cdots
\right].
$$

Thus the coefficient of $\log u$ in $\mathcal G^{(1)}$ contains anomalous-dimension data. This is one of the workhorses of analytic bootstrap.

The practical workflow is:

1. Start with the MFT spectrum.
2. Add a small connected correction to the correlator.
3. Decompose the correction into conformal blocks.
4. Read off $\gamma_{n,\ell}$ and $a_{n,\ell}^{(1)}$.
5. Impose crossing, unitarity, Regge behavior, or bulk locality constraints.

## Large-spin interpretation

At large spin, CFT dynamics often becomes close to mean-field theory. The lightcone bootstrap shows that if an operator $\mathcal O$ appears in one channel, then crossing forces large-spin double-trace families in the crossed channel.

For a scalar $\phi$, the large-spin towers look like

$$
\Delta_{n,\ell}
=
2\Delta_\phi+2n+\ell+\gamma_{n,\ell},
\qquad
\gamma_{n,\ell}\to0
\quad
\text{as }
\ell\to\infty
$$

under broad assumptions.

This is one reason MFT is more than a large-$N$ trick. It is the asymptotic skeleton of many CFT spectra. Interactions bend the skeleton by anomalous dimensions and OPE coefficient corrections, but the double-trace organization remains.

In holographic CFTs, this becomes the statement that high-angular-momentum two-particle states in AdS are weakly interacting at large separation.

## Relation to AdS contact interactions

In holography, MFT is the boundary correlator of a free bulk field in AdS. A bulk contact interaction adds a connected Witten diagram. In the boundary CFT, that connected diagram produces anomalous dimensions and OPE coefficient corrections for double-trace operators.

For example, a quartic bulk interaction schematically

$$
g\,\Phi^4
$$

contributes to

$$
\langle\phi\phi\phi\phi\rangle_{\rm conn}
$$

at order $g$. The resulting CFT data are not new single-particle states; they are shifts in the double-trace data:

$$
[\phi\phi]_{n,\ell}
\quad\longrightarrow\quad
\Delta_{n,\ell}^{(0)}+\gamma_{n,\ell}.
$$

This is the bootstrap version of perturbation theory around free particles in AdS.

## Mean-field theory in numerical bootstrap

MFT often appears as a boundary point, limiting solution, or benchmark in numerical bootstrap. For example, if one maximizes or minimizes scalar dimensions subject only to basic crossing and unitarity, generalized-free solutions often sit at simple corners of the allowed space.

This has two lessons.

First, MFT is a useful test case. If a bootstrap code cannot reproduce MFT-like spectra and OPE positivity in simple limits, something is probably wrong.

Second, MFT is not the target when one wants an interacting local CFT such as the three-dimensional Ising CFT. One must impose assumptions that distinguish the desired CFT from generalized-free behavior, such as gaps, global symmetry information, relevant operator counts, stress-tensor normalization, or mixed-correlator constraints.

Mean-field theory is the “flat ground” of bootstrap space. Real interacting CFTs are the interesting terrain above it.

## Common pitfalls

**Do not confuse MFT with ordinary free scalar theory.** Ordinary free scalars have canonical dimension, an equation of motion, and a stress tensor. Generic MFT has only Wick-like correlators with arbitrary allowed $\Delta_\phi$.

**Do not think disconnected means OPE-trivial.** The disconnected four-point function has an infinite conformal block decomposition.

**Do not include odd spins for identical bosonic scalars.** The $\phi\times\phi$ OPE contains only even spin symmetric traceless tensors.

**Do not treat MFT OPE coefficients as independent data.** Once $\Delta_\phi$, $d$, and block normalization are chosen, the coefficients are fixed.

**Do not forget the stress-tensor caveat.** MFT data alone usually do not define a complete local CFT.

**Do not assume anomalous dimensions are optional in interacting large-$N$ CFTs.** Interactions shift double-trace dimensions; the shifts are often the main physical data.

**Do not overinterpret the word “trace.”** Double-trace language comes from matrix large-$N$ theories, but the same conformal multiplet structure exists without literal matrix traces.

## Relations to other pages

This page follows [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/) by focusing on the conformal block and OPE-data interpretation. It prepares [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/), where MFT becomes the leading large-$N$ approximation to single-trace correlators.

It also connects to [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), [Conformal Blocks in Higher Dimensions](/cft-bootstrap/conformal-blocks/conformal-blocks-in-higher-dimensions/), [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/), and the later [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/) chapter.

For holographic interpretation, see [Holographic CFT](/cft-bootstrap/holographic-cft/) and the pages on AdS contact diagrams and large-spin perturbation theory.

## Research status

Mean-field theory CFT data are established. The generalized-free four-point function, its crossing symmetry, and its double-trace conformal block decomposition are standard tools in conformal bootstrap and AdS/CFT.

Active research uses MFT as a base point for more refined questions: systematic large-$N$ perturbation theory, constraints from bulk locality, large-spin expansions, Polyakov bootstrap methods, Mellin-space amplitudes, numerical bootstrap near generalized-free solutions, and the structure of multi-trace mixing at higher orders.

## Exercises

### Exercise 1

Check crossing for

$$
\mathcal G_{\rm MFT}(u,v)=1+u^\Delta+\left(\frac{u}{v}\right)^\Delta.
$$

<details><summary><strong>Solution</strong></summary>

Identical scalar crossing requires

$$
\mathcal G(u,v)=\left(\frac{u}{v}\right)^\Delta\mathcal G(v,u).
$$

Now

$$
\left(\frac{u}{v}\right)^\Delta\mathcal G(v,u)
=
\left(\frac{u}{v}\right)^\Delta
\left[
1+v^\Delta+\left(\frac{v}{u}\right)^\Delta
\right].
$$

This equals

$$
\left(\frac{u}{v}\right)^\Delta+u^\Delta+1,
$$

which is the same as $\mathcal G_{\rm MFT}(u,v)$.

</details>

### Exercise 2

Why does the identity operator appear in the MFT block expansion?

<details><summary><strong>Solution</strong></summary>

In the $x_1\to x_2$ OPE limit, the disconnected contraction

$$
\langle\phi(x_1)\phi(x_2)\rangle\langle\phi(x_3)\phi(x_4)\rangle
$$

produces the leading term

$$
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}.
$$

In the reduced correlator this is the constant term $1$. A constant leading term in the $\phi\times\phi$ OPE channel is the identity conformal block.

</details>

### Exercise 3

Explain why the double-trace dimensions are

$$
2\Delta_\phi+2n+\ell.
$$

<details><summary><strong>Solution</strong></summary>

A schematic double-trace primary is built from two copies of $\phi$, $\ell$ spin-carrying derivatives, and $n$ powers of a two-derivative scalar structure:

$$
[\phi\phi]_{n,\ell}\sim
\phi\,\partial_{\mu_1}\cdots\partial_{\mu_\ell}(\partial^2)^n\phi
-\text{traces and descendants}.
$$

The two fields contribute $2\Delta_\phi$, the spin derivatives contribute $\ell$, and $(\partial^2)^n$ contributes $2n$. Thus

$$
\Delta_{n,\ell}^{(0)}=2\Delta_\phi+2n+\ell.
$$

</details>

### Exercise 4

Why is MFT usually not a complete local CFT?

<details><summary><strong>Solution</strong></summary>

A complete local CFT should contain a conserved stress tensor with dimension $d$, spin two, and the correct Ward identity. A generic MFT double-trace spectrum has spin-two dimensions

$$
2\Delta_\phi+2n+2.
$$

For generic $\Delta_\phi$, none of these equals $d$. Even if a dimension happens to equal $d$, the stress-tensor Ward identity is not automatic. Therefore MFT is usually a consistent crossing-symmetric sector or large-$N$ limiting data, not a complete standalone local CFT.

</details>

### Exercise 5

Show how anomalous dimensions produce logarithms in perturbation theory around MFT.

<details><summary><strong>Solution</strong></summary>

Suppose

$$
\Delta_{n,\ell}=\Delta_{n,\ell}^{(0)}+\epsilon\gamma_{n,\ell}+\cdots .
$$

A conformal block contains a leading power schematically

$$
u^{\Delta_{n,\ell}/2}.
$$

Expanding at small $\epsilon$ gives

$$
u^{\Delta_{n,\ell}/2}
=
u^{\Delta_{n,\ell}^{(0)}/2}
\left[
1+\frac{\epsilon}{2}\gamma_{n,\ell}\log u+\cdots
\right].
$$

Thus $\log u$ terms in the first correction to a correlator encode anomalous dimensions.

</details>

## References

- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2016.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, “Holography from conformal field theory,” *Journal of High Energy Physics* **2009**.
- A. L. Fitzpatrick, J. Kaplan, D. Poland, and D. Simmons-Duffin, “The analytic bootstrap and AdS superhorizon locality,” *Journal of High Energy Physics* **2013**.
- L. F. Alday, “Large spin perturbation theory for conformal field theories,” *Physical Review Letters* **119** (2017).
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.

## Version history

- 2026-07-01: First polished draft. Added MFT block decomposition, double-trace spectrum, crossing check, stress-tensor caveat, large-$N$ and AdS interpretations, perturbative corrections, exercises, and references.
