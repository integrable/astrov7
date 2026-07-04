---
title: "Single-Trace Operators and Factorization"
description: "How single-trace operators, multi-trace operators, and large-N factorization become the boundary origin of bulk particles, multiparticle states, and weak interactions in AdS/CFT."
sidebar:
  order: 50
---

The previous page explained why the large-$N$ expansion of an adjoint gauge theory is organized by topology. Planar diagrams dominate, each handle costs $1/N^2$, and the expansion begins to look like a closed-string perturbation series.

This page refines that statement into the first real operator dictionary:

$$
\text{single-trace primary operators}
\quad\longleftrightarrow\quad
\text{single-particle bulk states},
$$

while

$$
\text{multi-trace primary operators}
\quad\longleftrightarrow\quad
\text{multiparticle bulk states}.
$$

This is not merely terminology. It is the field-theory origin of bulk Fock space. At $N=\infty$, single-particle states propagate freely, products of single-particle states behave like multiparticle states, and connected interactions are suppressed. At finite but large $N$, those particles interact weakly. The small parameter is $1/N$.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Single-trace operators, multi-trace operators, and large-N factorization](/figures/course/single-trace-factorization.svg)

<figcaption>

At large $N$, particle-normalized single-trace primaries $\mathcal O_i$ behave like single-particle operators. Multi-trace primaries such as $[\mathcal O_i\mathcal O_j]_{n,\ell}$ behave like multiparticle states. Connected $k$-point functions scale as $N^{2-k}$, which is the boundary origin of weak bulk interactions.

</figcaption>
</figure>

## Why this matters

AdS/CFT is often introduced by saying that each bulk field $\phi$ is dual to a boundary operator $\mathcal O$. That statement is true but incomplete. A quantum field in the bulk does not merely have one classical profile. It has particles, multiparticle states, interactions, loops, bound states, and scattering amplitudes. The CFT must contain all of this structure.

Large-$N$ factorization is the mechanism that makes this possible. It says that, to leading order at large $N$, certain gauge-invariant operators behave almost like independent classical variables or, after a different normalization, like free quantum fields. This is why the bulk can have an approximate Fock space.

The central scaling is

$$
\langle \mathcal O_1(x_1)\cdots \mathcal O_k(x_k)\rangle_c
\sim
N^{2-k}
$$

for particle-normalized single-trace operators. Thus

$$
\langle \mathcal O_1\mathcal O_2\rangle_c \sim N^0,
\qquad
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle_c \sim \frac{1}{N},
\qquad
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle_c \sim \frac{1}{N^2}.
$$

This is exactly the pattern expected from a weakly interacting bulk theory. Two-point functions normalize free propagation. Three-point functions measure cubic interactions. Four-point connected functions measure exchange and contact interactions. Bulk loops are further suppressed by powers of $1/N^2$.

## What is a single-trace operator?

In a gauge theory with adjoint fields, a local field can be written as a matrix

$$
X(x)^i{}_{j},
\qquad i,j=1,\ldots,N.
$$

Gauge-invariant local operators are made by contracting color indices. The simplest adjoint-sector gauge invariants are traces over color indices:

$$
\mathrm{Tr}\!\bigl(X_1 X_2\cdots X_L\bigr)(x).
$$

More generally, one may insert covariant derivatives, field strengths, fermions, or scalars:

$$
\mathrm{Tr}\!\left(
X_1 D_{\mu_1}X_2 F_{\mu\nu} X_3\cdots
\right)(x).
$$

The word **trace** always means trace over color indices. It does not mean spacetime trace, Lorentz trace, or trace over a Hilbert space.

A **single-trace operator** is a gauge-invariant local operator built from one color trace. A **multi-trace operator** is a product of two or more such traces at the same spacetime point, properly renormalized:

$$
:\!\mathcal O_A\mathcal O_B\!:(x),
\qquad
:\!\mathcal O_A\mathcal O_B\mathcal O_C\!:(x),
\qquad
\ldots
$$

The colons are a reminder that coincident products of local operators require subtractions. In a CFT, the properly defined product should be decomposed into conformal primaries and descendants, not treated as a naive pointwise product.

A typical double-trace primary is denoted

$$
[\mathcal O_A\mathcal O_B]_{n,\ell}.
$$

The labels $n$ and $\ell$ indicate radial excitation and spin. Schematically,

$$
[\mathcal O_A\mathcal O_B]_{n,\ell}
\sim
\mathcal O_A\,\partial_{\{\mu_1}\cdots\partial_{\mu_\ell\}}(\partial^2)^n\mathcal O_B
-\text{traces and descendants}.
$$

The phrase “schematically” is doing real work here. To construct an actual conformal primary, one must choose the coefficients of descendant subtractions carefully. For the holographic interpretation, however, the important point is simple: a double-trace primary is built from two single-trace ingredients.

## Two useful normalizations

Large-$N$ discussions can be confusing because two normalizations are useful for different purposes.

First, define a **macroscopic** single-trace variable

$$
\mathfrak o_A(x)
\sim
\frac{1}{N}\mathrm{Tr}(X\cdots X)(x).
$$

This normalization is natural when thinking about large-$N$ saddle points. Its expectation value is often order one:

$$
\langle \mathfrak o_A\rangle \sim N^0.
$$

Its connected fluctuations are suppressed:

$$
\langle \mathfrak o_{A_1}\cdots \mathfrak o_{A_k}\rangle_c
\sim
N^{2-2k}.
$$

For example,

$$
\langle \mathfrak o_A\mathfrak o_B\rangle_c \sim \frac{1}{N^2}.
$$

This is the sense in which large-$N$ theories factorize:

$$
\langle \mathfrak o_A\mathfrak o_B\rangle
=
\langle \mathfrak o_A\rangle\langle \mathfrak o_B\rangle
+O\!\left(\frac{1}{N^2}\right).
$$

Second, define a **particle-normalized** operator by extracting the fluctuation with a factor of $N$:

$$
\mathcal O_A(x)
=
N\left(\mathfrak o_A(x)-\langle \mathfrak o_A\rangle\right),
$$

up to convention-dependent finite normalization constants. Then

$$
\langle \mathcal O_A\mathcal O_B\rangle_c \sim N^0,
$$

and more generally

$$
\langle \mathcal O_{A_1}\cdots \mathcal O_{A_k}\rangle_c
\sim
N^{2-k}.
$$

This is the normalization most useful for the bulk particle dictionary. It makes two-point functions order one and shows that cubic interactions scale as $1/N$.

| Normalization | Natural use | Connected scaling |
|---|---|---|
| $\mathfrak o\sim N^{-1}\mathrm{Tr}(\cdots)$ | large-$N$ saddle variables | $\langle \mathfrak o^k\rangle_c\sim N^{2-2k}$ |
| $\mathcal O\sim N\mathfrak o$ fluctuation | bulk particle operators | $\langle \mathcal O^k\rangle_c\sim N^{2-k}$ |

Both are correct. Confusion comes from mixing them in the same sentence.

## Deriving the connected scaling

The previous page gave the topological scaling of ribbon graphs. A connected genus-$g$ diagram with $k$ single-trace insertions scales as

$$
N^{2-2g-k}
$$

when the inserted operators are particle-normalized so that the two-point function is order one. The leading connected contribution is planar, so $g=0$:

$$
\langle \mathcal O_1\cdots \mathcal O_k\rangle_c^{\text{planar}}
\sim
N^{2-k}.
$$

The first nonplanar correction has one handle, $g=1$, and is suppressed by $1/N^2$:

$$
\langle \mathcal O_1\cdots \mathcal O_k\rangle_c^{g=1}
\sim
N^{-k}.
$$

Thus the full large-$N$ expansion has the schematic form

$$
\langle \mathcal O_1\cdots \mathcal O_k\rangle_c
=
N^{2-k}F_k^{(0)}(\lambda)
+
N^{-k}F_k^{(1)}(\lambda)
+
N^{-k-2}F_k^{(2)}(\lambda)
+\cdots,
$$

where $F_k^{(g)}(\lambda)$ is a function of the 't Hooft coupling and other dimensionless parameters.

The important point is that the $N$-dependence is topological. Details of the dynamics affect the functions $F_k^{(g)}(\lambda)$, but the powers of $N$ follow from color-index topology.

## Large-$N$ factorization

For particle-normalized operators with vanishing one-point functions, the simplest visible form of factorization is the four-point function:

$$
\begin{aligned}
\langle
\mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4
\rangle
&=
\langle\mathcal O_1\mathcal O_2\rangle
\langle\mathcal O_3\mathcal O_4\rangle
+
\langle\mathcal O_1\mathcal O_3\rangle
\langle\mathcal O_2\mathcal O_4\rangle
\\
&\quad+
\langle\mathcal O_1\mathcal O_4\rangle
\langle\mathcal O_2\mathcal O_3\rangle
+O\!\left(\frac{1}{N^2}\right).
\end{aligned}
$$

This is the behavior of a **generalized free field**. It is not necessarily a free field in the microscopic Lagrangian. Rather, it is an operator whose leading large-$N$ correlators obey Wick-like factorization.

This distinction is crucial. A strongly coupled large-$N$ gauge theory may have no useful perturbative quasiparticles in the usual field-theory variables, but its single-trace gauge-invariant operators can still behave as generalized free fields at leading order in $1/N$.

From the bulk viewpoint, this is free propagation of particles in a fixed AdS background. The connected $O(1/N^2)$ correction to the four-point function is the first sign of bulk interactions at tree level.

## The bulk interpretation

Suppose a single-trace primary $\mathcal O_A$ has scaling dimension $\Delta_A$ and spin $J_A$. The state-operator correspondence gives a CFT state on the cylinder,

$$
|\mathcal O_A\rangle
=
\mathcal O_A(0)|0\rangle,
$$

with cylinder energy

$$
E_A=\Delta_A.
$$

In global AdS, this state is interpreted as a one-particle state of a bulk field with matching quantum numbers. For a scalar field,

$$
\mathcal O_A
\quad\longleftrightarrow\quad
\phi_A,
$$

and the scalar mass is later related to $\Delta_A$ by

$$
m_A^2L^2 = \Delta_A(\Delta_A-d).
$$

Now consider a double-trace primary. At $N=\infty$, the two particles do not interact, so their energies add. The spectrum contains operators with dimensions

$$
\Delta_{AB,n,\ell}^{(0)}
=
\Delta_A+
\Delta_B+
2n+
\ell.
$$

Thus

$$
[\mathcal O_A\mathcal O_B]_{n,\ell}
\quad\longleftrightarrow\quad
\text{two-particle state in global AdS}.
$$

The $2n+\ell$ is the familiar tower of relative motion in AdS: $\ell$ is angular momentum on $S^{d-1}$, and $n$ labels radial excitation. At finite but large $N$, interactions shift these dimensions:

$$
\Delta_{AB,n,\ell}
=
\Delta_A+
\Delta_B+
2n+
\ell
+
\frac{1}{N^2}\gamma_{AB,n,\ell}^{(1)}
+\cdots.
$$

These anomalous dimensions are not a nuisance. They are precisely the CFT way of encoding bulk binding energies and scattering phase shifts.

## How interactions appear

A bulk effective action for fields dual to single-trace operators often has the schematic form

$$
S_{\mathrm{bulk}}
\sim
N^2\int d^{d+1}x\sqrt g
\left[
\frac12(\nabla\phi)^2
+
\frac12m^2\phi^2
+
\frac{c_3}{3!}\phi^3
+
\frac{c_4}{4!}\phi^4
+\cdots
\right].
$$

The overall $N^2$ reflects the number of degrees of freedom in the boundary theory. It is also the statement that

$$
\frac{L^{d-1}}{G_N}\sim N^2
$$

in many holographic examples.

To put the bulk field in canonical normalization, define

$$
\varphi = N\phi.
$$

Then the action becomes schematically

$$
S_{\mathrm{bulk}}
\sim
\int d^{d+1}x\sqrt g
\left[
\frac12(\nabla\varphi)^2
+
\frac12m^2\varphi^2
+
\frac{c_3}{3!N}\varphi^3
+
\frac{c_4}{4!N^2}\varphi^4
+\cdots
\right].
$$

Therefore

$$
g_3\sim \frac{1}{N},
\qquad
g_4\sim \frac{1}{N^2},
\qquad
\text{bulk loops} \sim \frac{1}{N^2}.
$$

This matches the CFT scaling of connected correlators:

$$
\langle \mathcal O\mathcal O\mathcal O\rangle_c\sim \frac1N,
\qquad
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle_c\sim \frac1{N^2}.
$$

The normalization of individual operators and fields can vary by convention, but the hierarchy is robust.

## Single-trace does not automatically mean light

The single-trace/multi-trace distinction tells us about particle number in the large-$N$ bulk. It does not by itself tell us whether the particle is light, heavy, stringy, or part of a simple Einstein gravity theory.

A generic large-$N$ gauge theory may have many single-trace operators with low or moderate dimensions, including operators of high spin. In the bulk, that means many light fields. If infinitely many higher-spin single-trace operators remain light, the bulk theory is not well approximated by ordinary Einstein gravity coupled to a small number of matter fields.

A simple local bulk effective field theory in AdS requires more than factorization. It requires a sparse low-dimension single-trace spectrum, or equivalently a large gap to higher-spin single-trace operators:

$$
\Delta_{\mathrm{gap}}\gg 1.
$$

In the canonical AdS$_5$/CFT$_4$ example, this large gap appears at strong 't Hooft coupling. Stringy excitations become heavy in AdS units, leaving a low-energy supergravity sector.

So the logic is:

$$
\text{large }N
\quad\Rightarrow\quad
\text{weakly interacting bulk theory},
$$

but

$$
\text{large }N + \text{large gap}
\quad\Rightarrow\quad
\text{local bulk EFT below the gap}.
$$

For classical Einstein gravity, one needs still more structure: the low-energy spectrum and interactions must match gravity plus a controlled set of matter fields.

## Operator mixing

At finite $N$, single-trace and multi-trace operators with the same quantum numbers can mix. Even at large $N$, mixing is important if dimensions become degenerate.

For example, suppose a single-trace operator $\mathcal O_C$ and a double-trace operator $[\mathcal O_A\mathcal O_B]_{n,\ell}$ have the same spin, charges, and nearly the same dimension. Then the physical scaling operators are linear combinations:

$$
\mathcal O_{\pm}
=
a_{\pm}\mathcal O_C
+
b_{\pm}[\mathcal O_A\mathcal O_B]_{n,\ell}
+\cdots.
$$

The statement “single-trace means single-particle” is therefore a leading large-$N$ statement after choosing a basis adapted to the two-point function and dilatation operator. It is not a rigid finite-$N$ classification.

There is also a finite-$N$ limitation: traces are not all independent. For $N\times N$ matrices, trace identities relate sufficiently long traces. This is one of the places where the large-$N$ Fock-space picture must eventually break down. The breakdown is not a bug; it is part of how the finite-$N$ CFT encodes quantum gravity beyond perturbation theory.

## A simple example of factorization

For one scalar single-trace primary $\mathcal O$ normalized by

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\frac{1}{|x|^{2\Delta}},
$$

the leading large-$N$ four-point function is

$$
\begin{aligned}
\langle
\mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\mathcal O(x_4)
\rangle
&=
\frac{1}{x_{12}^{2\Delta}x_{34}^{2\Delta}}
+
\frac{1}{x_{13}^{2\Delta}x_{24}^{2\Delta}}
+
\frac{1}{x_{14}^{2\Delta}x_{23}^{2\Delta}}
\\
&\quad+
O\!\left(\frac{1}{N^2}\right),
\end{aligned}
$$

where $x_{ij}=|x_i-x_j|$ in Euclidean signature.

The leading terms are disconnected pairings. The connected part begins at order $1/N^2$:

$$
\langle
\mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\mathcal O(x_4)
\rangle_c
\sim
\frac{1}{N^2}.
$$

In the bulk, the disconnected terms are free propagation. The connected $1/N^2$ terms come from tree-level Witten diagrams: exchange diagrams and contact diagrams. Bulk loop corrections are smaller, typically starting at order $1/N^4$ in four-point functions.

This is why four-point functions are so important in modern holography. They are the first place where bulk interactions, locality, causality, anomalous dimensions, and effective field theory constraints become visible.

## Dictionary checkpoint

| Boundary statement | Bulk interpretation |
|---|---|
| single-trace primary $\mathcal O_A$ | single-particle state or bulk field $\phi_A$ |
| multi-trace primary $[\mathcal O_A\mathcal O_B]_{n,\ell}$ | two-particle state in global AdS |
| large-$N$ factorization | free propagation at leading order |
| $\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle_c\sim 1/N$ | cubic bulk coupling $g_3\sim 1/N$ |
| connected four-point function $\sim 1/N^2$ | tree-level bulk interaction |
| genus correction $\sim 1/N^2$ | bulk loop correction |
| double-trace anomalous dimension | bulk binding energy or scattering data |
| finite-$N$ trace relations | breakdown of naive perturbative Fock space |

The most important message is that the bulk Hilbert-space picture is not added by hand. It is reconstructed from the large-$N$ operator algebra of the boundary theory.

## Common confusions

### “Single-trace” means “elementary.”

No. A single-trace operator is usually a composite operator in the microscopic gauge theory. It is “elementary” only from the emergent bulk viewpoint, where it creates a single-particle state at leading large $N$.

### Multi-trace operators are unimportant.

No. Multi-trace operators are essential. They are the CFT representation of multiparticle states. Without them, the bulk would not have a Fock space.

### Factorization means the boundary theory is free.

No. Large-$N$ factorization is not ordinary weak coupling in the microscopic variables. The theory may be strongly coupled in terms of gauge fields. Factorization says that a special set of gauge-invariant operators has Wick-like correlators at leading order in $1/N$.

### The two-point function is suppressed by $1/N^2$.

It depends on normalization. For macroscopic operators $\mathfrak o\sim N^{-1}\mathrm{Tr}$, connected two-point fluctuations are suppressed. For particle-normalized operators $\mathcal O\sim N(\mathfrak o-\langle\mathfrak o\rangle)$, the two-point function is order one. The latter is the normalization usually used when matching to bulk particles.

### Every large-$N$ theory has a simple gravity dual.

No. Large $N$ gives a weakly coupled expansion. A simple local Einstein gravity dual requires additional conditions, especially a sparse low-dimension single-trace spectrum and a large gap to stringy or higher-spin states.

### Multi-trace products are just ordinary products.

Not quite. Products of local operators at the same point are singular and must be renormalized. In a CFT, one should decompose them into conformal primaries and descendants. The notation $[\mathcal O_A\mathcal O_B]_{n,\ell}$ denotes this properly organized double-trace primary, not a naive product.

## Exercises

### Exercise 1: Two normalizations

Suppose macroscopic single-trace variables obey

$$
\langle \mathfrak o_1\cdots \mathfrak o_k\rangle_c
\sim
N^{2-2k}.
$$

Define particle-normalized fluctuations by

$$
\mathcal O_i=N(\mathfrak o_i-\langle\mathfrak o_i\rangle).
$$

Show that

$$
\langle \mathcal O_1\cdots \mathcal O_k\rangle_c
\sim
N^{2-k}.
$$

<details>
<summary><strong>Solution</strong></summary>

Connected correlators are unchanged by subtracting one-point functions, except that one-point pieces are removed. Each insertion of $\mathcal O_i$ contributes a factor of $N$ relative to $\mathfrak o_i$. Therefore

$$
\langle \mathcal O_1\cdots \mathcal O_k\rangle_c
=
N^k
\langle \mathfrak o_1\cdots \mathfrak o_k\rangle_c.
$$

Using the assumed scaling,

$$
N^k
\langle \mathfrak o_1\cdots \mathfrak o_k\rangle_c
\sim
N^k N^{2-2k}
=
N^{2-k}.
$$

Thus the particle-normalized two-point function is order one, the three-point function is order $1/N$, and the connected four-point function is order $1/N^2$.

</details>

### Exercise 2: Four-point factorization

Let $\mathcal O$ be a scalar single-trace primary with

$$
\langle \mathcal O(x)\mathcal O(y)\rangle=G(x,y).
$$

Write the leading large-$N$ form of

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\mathcal O(x_4)\rangle.
$$

<details>
<summary><strong>Solution</strong></summary>

At leading order, large-$N$ factorization gives the Wick-like pairings:

$$
\begin{aligned}
\langle \mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\mathcal O(x_4)\rangle
&=
G(x_1,x_2)G(x_3,x_4)
+G(x_1,x_3)G(x_2,x_4)
\\
&\quad+
G(x_1,x_4)G(x_2,x_3)
+O\!\left(\frac{1}{N^2}\right).
\end{aligned}
$$

The connected part begins at order $1/N^2$.

</details>

### Exercise 3: Cubic coupling from a three-point function

Assume particle-normalized single-trace operators obey

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle_c
\sim
\frac{1}{N}.
$$

If these operators create canonically normalized bulk fields $\varphi_i$, what is the expected scaling of the cubic bulk coupling $g_{123}\varphi_1\varphi_2\varphi_3$?

<details>
<summary><strong>Solution</strong></summary>

A tree-level cubic Witten diagram is proportional to the cubic coupling $g_{123}$ after the external fields are canonically normalized. Since the CFT three-point function scales as $1/N$, the matching implies

$$
g_{123}\sim \frac{1}{N}.
$$

This agrees with the canonical-normalization argument from a bulk action with an overall factor $N^2$.

</details>

### Exercise 4: Double-trace dimensions

Let $\mathcal O_A$ and $\mathcal O_B$ be scalar single-trace primaries with dimensions $\Delta_A$ and $\Delta_B$. What is the leading large-$N$ dimension of the double-trace primary $[\mathcal O_A\mathcal O_B]_{n,\ell}$?

<details>
<summary><strong>Solution</strong></summary>

At $N=\infty$, the corresponding bulk particles do not interact, so their global AdS energies add. Derivatives contribute angular momentum and radial excitation. The leading dimension is

$$
\Delta_{AB,n,\ell}^{(0)}
=
\Delta_A+
\Delta_B+2n+\ell.
$$

At finite but large $N$, interactions shift this by anomalous dimensions:

$$
\Delta_{AB,n,\ell}
=
\Delta_A+
\Delta_B+2n+\ell
+
\frac{1}{N^2}\gamma_{AB,n,\ell}^{(1)}+\cdots.
$$

</details>

### Exercise 5: Why a large gap matters

Explain why large-$N$ factorization alone does not guarantee a simple Einstein gravity dual.

<details>
<summary><strong>Solution</strong></summary>

Large-$N$ factorization gives weak interactions among single-trace excitations, so it suggests a weakly coupled bulk theory. But the bulk theory might contain many light fields, including light higher-spin fields or string-scale excitations. A simple local Einstein gravity dual requires these extra single-trace states to be heavy in AdS units, so that a small low-energy set of fields remains. This is the large-gap condition. In the canonical AdS$_5$/CFT$_4$ example, the gap becomes large at strong 't Hooft coupling.

</details>

## Further reading

- G. 't Hooft, [A Planar Diagram Theory for Strong Interactions](https://webspace.science.uu.nl/~hooft101/gthpub/planar_diagram_theory.pdf). The original source of the planar large-$N$ expansion.
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111). The standard AdS/CFT review, including the relation between single-trace operators and single-particle states.
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151). A modern perspective on how large $N$, a sparse spectrum, and crossing symmetry lead toward local bulk effective field theory.
- D. Simmons-Duffin, [TASI Lectures on the Conformal Bootstrap](https://arxiv.org/abs/1602.07982). Useful background on conformal primaries, OPE data, and large-spin double-trace operators.
