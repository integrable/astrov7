---
title: "Three-Point Functions and Bulk Couplings"
description: "How cubic interactions in AdS determine CFT three-point coefficients and OPE data."
sidebar:
  order: 20
---

## Why this matters

Two-point functions define the normalization and spectrum of a CFT. Three-point functions are the next layer of data: they determine OPE coefficients. For scalar primary operators, conformal symmetry fixes the position dependence of a three-point function completely:

$$
\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)
\rangle
=
\frac{C_{123}}
{|x_{12}|^{\Delta_1+\Delta_2-\Delta_3}
 |x_{13}|^{\Delta_1+\Delta_3-\Delta_2}
 |x_{23}|^{\Delta_2+\Delta_3-\Delta_1}}.
$$

The dynamical information is the number $C_{123}$, after the two-point functions are normalized.

In AdS/CFT, the leading large-$N$ value of $C_{123}$ is computed by a cubic bulk coupling. This is one of the cleanest versions of the slogan:

$$
\text{bulk interactions}
\quad\longleftrightarrow\quad
\text{CFT OPE coefficients}.
$$

This page derives that statement for scalar operators. It also explains the normalization caveats that often cause confusion when comparing formulas across papers.

<figure class="doc-figure" style="--figure-width: 39rem;">

![A bulk cubic coupling determines a boundary three-point coefficient](/figures/course/three-point-functions-bulk-couplings.svg)

<figcaption>

A local cubic coupling in AdS fixes the conformally allowed three-point structure of the dual scalar primaries. The raw bulk coefficient becomes a CFT OPE coefficient only after two-point normalizations and convention-dependent factors are included.

</figcaption>
</figure>

## Setup

Consider three scalar bulk fields $\phi_i$ in Euclidean AdS$_{d+1}$, dual to scalar primary operators $\mathcal O_i$ with dimensions $\Delta_i$. The masses satisfy

$$
m_i^2L^2=\Delta_i(\Delta_i-d).
$$

Work in Poincaré coordinates and set $L=1$ unless explicitly restored:

$$
ds^2
=
\frac{dz^2+d x^i d x^i}{z^2},
\qquad
\sqrt g = z^{-(d+1)}.
$$

Take the interaction to be

$$
S_{\rm int}
=
g_{123}
\int_{\mathrm{AdS}}d^{d+1}X\sqrt g\,
\phi_1\phi_2\phi_3.
$$

If the fields are identical, one may instead write $g\phi^3/3!$. The final three-point function is the same once the combinatorial convention is treated consistently.

The linear solution sourced by $J_i(x)$ is

$$
\phi_i^{(1)}(X)
=
\int d^d x_i\,K_{\Delta_i}(X;x_i)J_i(x_i),
$$

with

$$
K_\Delta(z,x;x_i)
=
C_\Delta
\left(
\frac{z}{z^2+|x-x_i|^2}
\right)^\Delta,
\qquad
C_\Delta
=
\frac{\Gamma(\Delta)}{\pi^{d/2}\Gamma(\Delta-d/2)}.
$$

This $K_\Delta$ is the Euclidean boundary-to-bulk propagator for standard quantization.

## From the cubic action to the three-point diagram

At leading order in the cubic coupling, the interaction contribution to the on-shell action is obtained by substituting the linearized solutions into $S_{\rm int}$. Since

$$
W_{\rm CFT}[J]
\approx
-S_{\text{ren,on-shell}}[J],
$$

the cubic contribution to the connected generating functional is

$$
W^{(3)}[J]
=
-g_{123}
\int dX\sqrt g
\prod_{i=1}^3
\left[
\int d^d x_i\,K_{\Delta_i}(X;x_i)J_i(x_i)
\right].
$$

Differentiating with respect to the three sources gives

$$
\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)
\rangle_{\rm conn}
=
-g_{123}
\int_{\mathrm{AdS}}dX\sqrt g\,
K_{\Delta_1}(X;x_1)K_{\Delta_2}(X;x_2)K_{\Delta_3}(X;x_3),
$$

up to the overall sign convention in the Euclidean action. This is the three-point contact Witten diagram.

The entire computation is therefore reduced to an AdS integral.

## The AdS three-point integral

Substitute the explicit propagators. Define

$$
\Sigma=\Delta_1+\Delta_2+\Delta_3.
$$

The integral is

$$
I_3(x_1,x_2,x_3)
=
C_{\Delta_1}C_{\Delta_2}C_{\Delta_3}
\int_0^\infty \frac{dz\,d^d x}{z^{d+1}}
\prod_{i=1}^3
\left(
\frac{z}{z^2+|x-x_i|^2}
\right)^{\Delta_i}.
$$

Thus

$$
I_3
=
C_{\Delta_1}C_{\Delta_2}C_{\Delta_3}
\int_0^\infty dz\,d^d x\,
\frac{z^{\Sigma-d-1}}
{(z^2+|x-x_1|^2)^{\Delta_1}
 (z^2+|x-x_2|^2)^{\Delta_2}
 (z^2+|x-x_3|^2)^{\Delta_3}}.
$$

Conformal symmetry already tells us the answer must have the form

$$
I_3(x_1,x_2,x_3)
=
\frac{\mathcal I_{123}}
{|x_{12}|^{\Delta_1+\Delta_2-\Delta_3}
 |x_{13}|^{\Delta_1+\Delta_3-\Delta_2}
 |x_{23}|^{\Delta_2+\Delta_3-\Delta_1}}.
$$

The task is to compute the constant $\mathcal I_{123}$.

## Evaluating the constant

Use Schwinger parameters:

$$
\frac{1}{A_i^{\Delta_i}}
=
\frac{1}{\Gamma(\Delta_i)}
\int_0^\infty d\alpha_i\,\alpha_i^{\Delta_i-1}e^{-\alpha_i A_i}.
$$

For the three denominators

$$
A_i=z^2+|x-x_i|^2,
$$

the exponent is

$$
-\sum_i\alpha_i\left(z^2+|x-x_i|^2\right).
$$

Let

$$
\alpha=\alpha_1+\alpha_2+\alpha_3,
\qquad
\bar x=\frac{\alpha_1x_1+\alpha_2x_2+\alpha_3x_3}{\alpha}.
$$

Completing the square gives

$$
\sum_i\alpha_i|x-x_i|^2
=
\alpha |x-\bar x|^2
+
\frac{1}{\alpha}
\sum_{i<j}\alpha_i\alpha_j |x_{ij}|^2.
$$

The $x$-integral is Gaussian:

$$
\int d^d x\,e^{-\alpha|x-\bar x|^2}
=
\left(\frac{\pi}{\alpha}\right)^{d/2}.
$$

The $z$-integral is

$$
\int_0^\infty dz\,z^{\Sigma-d-1}e^{-\alpha z^2}
=
\frac12\alpha^{-(\Sigma-d)/2}\Gamma\left(\frac{\Sigma-d}{2}\right),
$$

valid initially for $\Sigma>d$ and then by analytic continuation in the dimensions.

After changing variables from $\alpha_i$ to an overall scale and simplex variables, one obtains the standard coefficient

$$
\mathcal I_{123}
=
\frac{\pi^{d/2}}{2}
\frac{C_{\Delta_1}C_{\Delta_2}C_{\Delta_3}}
{\Gamma(\Delta_1)\Gamma(\Delta_2)\Gamma(\Delta_3)}
\Gamma\left(\frac{\Delta_1+\Delta_2+\Delta_3-d}{2}\right)
\Gamma\left(\frac{\Delta_1+\Delta_2-\Delta_3}{2}\right)
\Gamma\left(\frac{\Delta_1+\Delta_3-\Delta_2}{2}\right)
\Gamma\left(\frac{\Delta_2+\Delta_3-\Delta_1}{2}\right).
$$

Therefore, with the Euclidean sign convention above,

$$
C_{123}^{\rm raw}
=
-g_{123}\,\mathcal I_{123}.
$$

This is the raw coefficient produced by the chosen bulk action and field normalization. To get the CFT OPE coefficient in normalized conventions, one must divide by the square roots of the two-point-function normalizations.

## Normalizing the OPE coefficient

Suppose the two-point functions are

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\delta_{ij}\frac{\mathcal N_i}{|x|^{2\Delta_i}}.
$$

Define normalized operators

$$
\widehat{\mathcal O}_i
=
\frac{\mathcal O_i}{\sqrt{\mathcal N_i}}.
$$

Then

$$
\langle \widehat{\mathcal O}_i(x)\widehat{\mathcal O}_j(0)\rangle
=
\frac{\delta_{ij}}{|x|^{2\Delta_i}},
$$

and the normalized three-point coefficient is

$$
\widehat C_{123}
=
\frac{C_{123}^{\rm raw}}
{\sqrt{\mathcal N_1\mathcal N_2\mathcal N_3}}.
$$

This step is essential. A bulk cubic coupling by itself is not yet a convention-independent OPE coefficient. It becomes one after the kinetic terms, propagator normalizations, and operator normalizations are fixed.

In many supergravity papers, fields are normalized by dimensional reduction from ten or eleven dimensions. In many CFT papers, operators are normalized so that their two-point functions are unity. Translating between these conventions is often the hardest part of comparing results.

## Large-$N$ scaling

For normalized single-trace operators in a large-$N$ gauge theory,

$$
\langle \widehat{\mathcal O}_1\widehat{\mathcal O}_2\widehat{\mathcal O}_3\rangle
\sim
\frac{1}{N}.
$$

The bulk explanation is simple. The gravitational action has an overall factor

$$
S_{\rm bulk}
\sim
\frac{L^{d-1}}{G_N}
\int d^{d+1}X\sqrt g\,\mathcal L
\sim
N^2\int \mathcal L
$$

in the canonical AdS$_5$/CFT$_4$ example. After rescaling fields so that the quadratic action is canonically normalized, a cubic vertex is suppressed by

$$
\frac{1}{N}.
$$

Thus the Witten diagram reproduces the expected single-trace scaling.

If one uses unnormalized single-trace operators such as $\operatorname{Tr}(X^k)$, the apparent $N$-power changes. The invariant statement is that connected three-point functions are suppressed relative to two-point functions in exactly the way expected from a weakly interacting bulk theory.

## Why the answer has the CFT form

The result has the standard conformal three-point structure because the integral is invariant under AdS isometries. In Poincaré coordinates, the most transparent checks are translations, rotations, and dilations. The less obvious check is inversion or special conformal transformations. These also hold because they arise from AdS isometries acting on the boundary conformal group.

Under a dilation $x_i\to \lambda x_i$, each boundary-to-bulk propagator contributes $\lambda^{-\Delta_i}$ while the AdS measure is invariant. Therefore

$$
I_3(\lambda x_1,\lambda x_2,\lambda x_3)
=
\lambda^{-\Sigma}I_3(x_1,x_2,x_3).
$$

The conformal three-point structure has exactly this scaling. The exponents in the denominator are determined by requiring the correct scaling at each point.

For example, the power of $|x_{12}|$ is

$$
\Delta_1+\Delta_2-\Delta_3.
$$

This is not arbitrary. It is the unique value compatible with separate scaling weights $\Delta_1$, $\Delta_2$, and $\Delta_3$ at the three insertion points.

## OPE interpretation

The scalar OPE has the schematic form

$$
\mathcal O_1(x)\mathcal O_2(0)
\sim
\sum_k C_{12k}
\frac{1}{|x|^{\Delta_1+\Delta_2-\Delta_k}}
\left[\mathcal O_k(0)+\text{descendants}\right].
$$

Taking the expectation value with $\mathcal O_3(y)$ and using the two-point function gives the three-point function. Thus the coefficient extracted from the Witten diagram is precisely the OPE coefficient once the operators are normalized.

On the bulk side, the same statement reads:

$$
\phi_1\phi_2\phi_3\text{ vertex}
\quad\Longleftrightarrow\quad
\mathcal O_3\text{ appears in }\mathcal O_1\times\mathcal O_2.
$$

If $g_{123}=0$ because of a symmetry, then the corresponding leading large-$N$ OPE coefficient vanishes. If the coupling is allowed, the three-point diagram computes it.

## Selection rules

Bulk interactions inherit the symmetries of the background. In AdS$_5\times S^5$, Kaluza–Klein modes carry $SO(6)_R$ quantum numbers. A cubic coupling is allowed only if the product of the corresponding representations contains a singlet:

$$
R_1\otimes R_2\otimes R_3
\supset
\mathbf 1.
$$

The same condition appears in the CFT as an R-symmetry selection rule for

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle.
$$

This is a good example of the difference between kinematics and dynamics. Conformal symmetry fixes the spacetime dependence. Internal symmetries restrict which coefficients can be nonzero. The actual numerical values of the allowed coefficients are dynamical data, computed from the bulk couplings in the gravity limit.

## Derivative cubic couplings

Not every cubic interaction is simply $\phi_1\phi_2\phi_3$. One may have terms such as

$$
S_{\rm int}
\supset
h_{123}\int dX\sqrt g\,\phi_1\nabla_M\phi_2\nabla^M\phi_3.
$$

For a three-point function of scalar primaries, conformal symmetry still permits only one spacetime structure. Therefore a derivative cubic coupling changes only the overall coefficient, not the functional form.

Using integration by parts and the equations of motion,

$$
\nabla^2\phi_i=m_i^2\phi_i,
$$

one can relate the derivative vertex to a non-derivative one plus boundary/contact terms. For example,

$$
\int \sqrt g\,\phi_1\nabla_M\phi_2\nabla^M\phi_3
=
\frac12\left(m_1^2-m_2^2-m_3^2\right)
\int \sqrt g\,\phi_1\phi_2\phi_3
+\text{boundary terms},
$$

provided the fields obey their linear equations and the boundary terms are treated carefully.

At four points and higher, derivative interactions are more consequential because conformal symmetry leaves nontrivial functions of cross ratios. There, derivative couplings change the cross-ratio dependence and encode genuine bulk effective-field-theory data.

## Extremal and near-extremal cases

The gamma-function expression contains factors such as

$$
\Gamma\left(\frac{\Delta_1+\Delta_2-\Delta_3}{2}\right).
$$

If

$$
\Delta_3=\Delta_1+\Delta_2,
$$

this factor becomes $\Gamma(0)$, suggesting a divergence. Such correlators are called extremal. They occur naturally for certain protected operators in supersymmetric AdS/CFT examples.

The divergence does not mean the CFT correlator is ill-defined. It means the naive bulk contact integral needs a more careful treatment. In many supergravity examples, the corresponding cubic coupling vanishes in just the right way so that the product of coupling and divergent integral has a finite limit. Boundary terms and analytic continuation in dimensions can also be important.

For this foundations course, the main lesson is:

$$
\text{special dimension relations may require more than the naive contact integral.}
$$

Generic non-extremal three-point functions are captured cleanly by the formula above.

## Spinning operators

For currents and stress tensors, the same logic applies but the tensor structures are richer. A conserved current three-point function has vector indices and is constrained by conformal symmetry plus current conservation. A stress-tensor three-point function is constrained by conformal symmetry plus diffeomorphism Ward identities.

On the bulk side:

| Boundary three-point function | Bulk cubic interaction |
|---|---|
| $\langle \mathcal O\mathcal O\mathcal O\rangle$ | scalar cubic vertex |
| $\langle J\mathcal O\mathcal O\rangle$ | gauge-scalar-scalar vertex |
| $\langle JJJ\rangle$ | Yang–Mills and possible Chern–Simons vertices |
| $\langle T\mathcal O\mathcal O\rangle$ | graviton-scalar-scalar vertex |
| $\langle TTT\rangle$ | graviton cubic vertex and higher-derivative gravitational terms |

For spinning correlators, a bulk vertex determines not just a number but a linear combination of allowed tensor structures. Higher-derivative bulk terms correspond to additional CFT tensor structures, subject to Ward identities and consistency constraints.

## Protected versus unprotected data

In $\mathcal N=4$ SYM, many important scalar operators are protected chiral primaries. Their dimensions do not depend on the coupling. Certain three-point functions among protected operators are also protected, so their strong-coupling supergravity values agree with weak-coupling field-theory calculations after matching normalizations.

This protection is special. In a generic holographic CFT, dimensions and OPE coefficients depend on the coupling. The bulk computation gives their values in the regime where the CFT has a weakly curved gravity dual.

A good mental picture is:

$$
\text{protected data}
\quad\text{can survive across coupling space},
$$

while

$$
\text{unprotected data}
\quad\text{are generally different at weak and strong coupling}.
$$

## Contact terms and scheme dependence

The nonlocal three-point structure at separated points is the universal data. Local terms supported when points coincide are different. For example, terms proportional to

$$
\delta^{(d)}(x_1-x_2)\frac{1}{|x_{23}|^{2\Delta_3}}
$$

are contact terms. They can be shifted by local counterterms in the generating functional.

The coefficient $C_{123}$ in the separated-point three-point function is physical CFT data. Contact terms are also meaningful in Ward identities and when sources are spacetime-dependent, but they are scheme-dependent unless fixed by symmetry, anomaly matching, or a precise renormalization prescription.

When computing Witten diagrams, always separate:

$$
\text{nonlocal separated-point data}
\quad\text{from}\quad
\text{local contact terms}.
$$

## Dictionary checkpoint

The three-point dictionary is:

| Bulk quantity | Boundary meaning |
|---|---|
| scalar mass $m_i^2$ | dimension $\Delta_i$ |
| boundary-to-bulk propagator $K_{\Delta_i}$ | insertion of $\mathcal O_i$ |
| cubic coupling $g_{123}$ | leading large-$N$ three-point/OPE data |
| AdS contact integral | conformally fixed three-point position dependence |
| two-point normalization $\mathcal N_i$ | operator normalization convention |
| derivative cubic vertex | same scalar structure, different coefficient at three points |
| internal symmetry of bulk fields | CFT selection rule |
| bulk counterterm | contact-term ambiguity |

In one line:

$$
\widehat C_{123}
\propto
\frac{g_{123}\,\mathcal I_{123}}
{\sqrt{\mathcal N_1\mathcal N_2\mathcal N_3}},
$$

with proportionality signs hiding only convention-dependent signs, radii, and field-normalization factors.

## Common confusions

### “The three-point function is fixed, so there is no dynamics.”

The position dependence is fixed by conformal symmetry, but the coefficient $C_{123}$ is dynamical. The bulk cubic coupling computes that coefficient.

### “The bulk coupling is directly the OPE coefficient.”

Not quite. The OPE coefficient is the bulk coupling times an AdS integral and divided by the square roots of the two-point-function normalizations. Field normalizations matter.

### “A vanishing cubic coupling means the operator does not exist.”

No. It means that particular leading three-point coefficient vanishes, usually because of a symmetry or selection rule. The operator can still appear in other correlators or at subleading order.

### “Derivative couplings create new scalar three-point shapes.”

For scalar primaries, conformal symmetry allows only one three-point spacetime structure. Derivative couplings change its coefficient, not its position dependence, up to contact terms. New shape data first become unavoidable in scalar four-point functions.

### “Divergent gamma functions always mean a mistake.”

They often signal a special kinematic case, such as extremal dimensions, where the naive bulk integral must be interpreted by analytic continuation, boundary terms, or a cancellation with a vanishing coupling.

## Exercises

### Exercise 1: Recover the conformal exponents

Assume the scalar three-point function has the form

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\rangle
=
\frac{C_{123}}{|x_{12}|^a|x_{13}|^b|x_{23}|^c}.
$$

Use scaling at each point to solve for $a$, $b$, and $c$.

<details>
<summary><strong>Solution</strong></summary>

Under a local scaling of the coordinates around $x_1$, the operator $\mathcal O_1$ has dimension $\Delta_1$. Equivalently, the powers of distances involving $x_1$ must add to $2\Delta_1$:

$$
a+b=2\Delta_1.
$$

Similarly,

$$
a+c=2\Delta_2,
\qquad
b+c=2\Delta_3.
$$

Solving gives

$$
a=\Delta_1+\Delta_2-\Delta_3,
$$

$$
b=\Delta_1+\Delta_3-\Delta_2,
$$

and

$$
c=\Delta_2+\Delta_3-\Delta_1.
$$

Therefore

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle
=
\frac{C_{123}}
{|x_{12}|^{\Delta_1+\Delta_2-\Delta_3}
 |x_{13}|^{\Delta_1+\Delta_3-\Delta_2}
 |x_{23}|^{\Delta_2+\Delta_3-\Delta_1}}.
$$

</details>

### Exercise 2: Large-$N$ scaling of a cubic vertex

Suppose a bulk action has the schematic form

$$
S=N^2\int dX\sqrt g\left[\frac12(\partial\phi)^2+\frac12m^2\phi^2+\lambda_3\phi^3+\cdots\right].
$$

Rescale the field to make the kinetic term canonical. What is the $N$-scaling of the cubic vertex?

<details>
<summary><strong>Solution</strong></summary>

Define the canonically normalized field

$$
\varphi=N\phi.
$$

Then

$$
N^2\frac12(\partial\phi)^2
=
\frac12(\partial\varphi)^2.
$$

The cubic term becomes

$$
N^2\lambda_3\phi^3
=
N^2\lambda_3\left(\frac{\varphi}{N}\right)^3
=
\frac{\lambda_3}{N}\varphi^3.
$$

Thus the canonically normalized cubic vertex is of order $1/N$. This matches the large-$N$ scaling of normalized single-trace three-point functions.

</details>

### Exercise 3: Derivative coupling reduction

Using integration by parts, show that on shell

$$
\int \sqrt g\,\phi_1\nabla_M\phi_2\nabla^M\phi_3
=
\frac12(m_1^2-m_2^2-m_3^2)
\int \sqrt g\,\phi_1\phi_2\phi_3
+\text{boundary terms}.
$$

<details>
<summary><strong>Solution</strong></summary>

Start from

$$
\nabla^2(\phi_2\phi_3)
=
(\nabla^2\phi_2)\phi_3
+
\phi_2(\nabla^2\phi_3)
+
2\nabla_M\phi_2\nabla^M\phi_3.
$$

Therefore

$$
\nabla_M\phi_2\nabla^M\phi_3
=
\frac12\left[
\nabla^2(\phi_2\phi_3)
-(\nabla^2\phi_2)\phi_3
-\phi_2(\nabla^2\phi_3)
\right].
$$

Multiply by $\phi_1$ and integrate:

$$
\int\sqrt g\,\phi_1\nabla_M\phi_2\nabla^M\phi_3
=
\frac12\int\sqrt g\,\phi_1\nabla^2(\phi_2\phi_3)
-
\frac12\int\sqrt g\,\phi_1(\nabla^2\phi_2)\phi_3
-
\frac12\int\sqrt g\,\phi_1\phi_2(\nabla^2\phi_3).
$$

Integrating the first term by parts twice gives

$$
\int\sqrt g\,\phi_1\nabla^2(\phi_2\phi_3)
=
\int\sqrt g\,(\nabla^2\phi_1)\phi_2\phi_3
+\text{boundary terms}.
$$

Using the on-shell equations

$$
\nabla^2\phi_i=m_i^2\phi_i,
$$

gives

$$
\frac12(m_1^2-m_2^2-m_3^2)
\int\sqrt g\,\phi_1\phi_2\phi_3
+
\text{boundary terms}
$$

if the Laplacian convention is $\nabla^2\phi=m^2\phi$ as written. If the action is written with the operator $-\nabla^2+m^2$, the equivalent reduction is often displayed with the opposite sign convention. The important lesson is that the derivative vertex is proportional on shell to a non-derivative vertex plus boundary terms, with the coefficient fixed by the masses and sign conventions.

</details>

### Exercise 4: Normalize a raw coefficient

Suppose a Witten diagram gives

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle
=
C_{123}^{\rm raw}F_{123}(x_i),
$$

and the two-point functions are

$$
\langle \mathcal O_i(x)\mathcal O_i(0)\rangle
=
\frac{\mathcal N_i}{|x|^{2\Delta_i}}.
$$

What is the coefficient for normalized operators?

<details>
<summary><strong>Solution</strong></summary>

Define

$$
\widehat{\mathcal O}_i=\frac{\mathcal O_i}{\sqrt{\mathcal N_i}}.
$$

Then

$$
\langle \widehat{\mathcal O}_1\widehat{\mathcal O}_2\widehat{\mathcal O}_3\rangle
=
\frac{1}{\sqrt{\mathcal N_1\mathcal N_2\mathcal N_3}}
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle.
$$

Therefore

$$
\widehat C_{123}
=
\frac{C_{123}^{\rm raw}}
{\sqrt{\mathcal N_1\mathcal N_2\mathcal N_3}}.
$$

</details>

## Further reading

- D. Z. Freedman, S. D. Mathur, A. Matusis, and L. Rastelli, [Correlation Functions in the CFT$_d$/AdS$_{d+1}$ Correspondence](https://arxiv.org/abs/hep-th/9804058).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).
- S. Lee, S. Minwalla, M. Rangamani, and N. Seiberg, [Three-Point Functions of Chiral Operators in D=4, N=4 SYM at Large N](https://arxiv.org/abs/hep-th/9806074).
- E. D'Hoker and D. Z. Freedman, [Supersymmetric Gauge Theories and the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0201253).
- J. Penedones, [TASI Lectures on AdS/CFT](https://arxiv.org/abs/1608.04948).
