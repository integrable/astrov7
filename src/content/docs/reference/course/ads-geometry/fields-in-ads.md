---
title: "Fields in AdS"
description: "Bulk scalar fields in Anti-de Sitter spacetime, near-boundary falloffs, normalizable modes, source-response data, and the first field/operator dictionary."
sidebar:
  order: 60
---

The first pages of this geometry unit treated AdS as a spacetime: its embedding, coordinate systems, conformal boundary, global cylinder, and symmetry group. Now we let fields propagate in it.

This is the first point where the geometry begins to look like a quantum field theory dictionary. A bulk field in AdS is not merely a field living in a curved background. Its asymptotic behavior near the AdS boundary is interpreted as field-theory data: a source, an expectation value, and later correlation functions.

The scalar field is the cleanest training example. It already contains the central ideas:

$$
\text{bulk mass}
\quad \longleftrightarrow \quad
\text{operator dimension},
$$

$$
\text{boundary value of a bulk field}
\quad \longleftrightarrow \quad
\text{source for a CFT operator},
$$

$$
\text{normalizable bulk response}
\quad \longleftrightarrow \quad
\text{state-dependent expectation value}.
$$

The goal of this page is to make those statements precise enough that the later GKPW prescription does not feel like a mysterious formula suddenly dropped from the sky.

## Why this matters

In ordinary quantum field theory, a source $J(x)$ couples to an operator $\mathcal O(x)$ through

$$
S_{\mathrm{QFT}} \to S_{\mathrm{QFT}} + \int d^d x\, J(x)\mathcal O(x).
$$

Correlation functions are obtained by differentiating the generating functional with respect to $J$. In AdS/CFT, the role of the source is played by the leading boundary behavior of a bulk field. A classical bulk equation of motion with boundary condition $J$ becomes a machine for computing strong-coupling CFT observables.

For a scalar field, the key result is

$$
m^2 L^2 = \Delta(\Delta-d),
$$

where $m$ is the bulk mass, $L$ is the AdS radius, $d$ is the boundary spacetime dimension, and $\Delta$ is the scaling dimension of the dual scalar primary operator.

This relation is one of the simplest and most important examples of the holographic dictionary. It says that a geometric or gravitational property in the bulk, namely the mass of a field in AdS units, is the same information as a field-theory scaling dimension.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Near-boundary source-response data for a scalar field in AdS](/figures/course/fields-in-ads-source-response.svg)

<figcaption>

A bulk field $\phi(z,x)$ is fixed by boundary data near $z=0$ together with an interior condition. In standard quantization, the leading falloff $z^{d-\Delta}\phi_{(0)}(x)$ is the source, while the subleading falloff $z^\Delta A(x)$ is related to the expectation value $\langle \mathcal O(x)\rangle$ after holographic renormalization.

</figcaption>
</figure>

## Setup: a scalar in Poincaré AdS

Work in Lorentzian Poincaré AdS$_{d+1}$,

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2 + \eta_{\mu\nu}dx^\mu dx^\nu
\right),
\qquad
z>0,
$$

where the boundary is at $z=0$. The boundary coordinates are $x^\mu$, with $\mu=0,1,\ldots,d-1$. The bulk coordinates are $X^M=(z,x^\mu)$.

For a real scalar field $\phi$, take the quadratic action

$$
S_\phi
=
-\frac12
\int d^{d+1}X\,\sqrt{-g}
\left(
 g^{MN}\partial_M\phi\,\partial_N\phi
 + m^2\phi^2
\right),
$$

up to possible boundary terms. The equation of motion is the curved-space Klein–Gordon equation

$$
(\nabla^2-m^2)\phi=0.
$$

In Poincaré coordinates,

$$
\sqrt{-g}=\left(\frac{L}{z}\right)^{d+1},
\qquad
\nabla^2\phi
=
\frac{z^2}{L^2}
\left(
\partial_z^2\phi
-
\frac{d-1}{z}\partial_z\phi
+
\eta^{\mu\nu}\partial_\mu\partial_\nu\phi
\right).
$$

Thus the wave equation becomes

$$
\left[
 z^2\partial_z^2
 -(d-1)z\partial_z
 +z^2\eta^{\mu\nu}\partial_\mu\partial_\nu
 -m^2L^2
\right]
\phi(z,x)=0.
$$

This equation is simple enough to analyze near the boundary and rich enough to contain the source-response structure of holography.

## Near-boundary behavior

Near $z=0$, the term with boundary derivatives is suppressed by $z^2$. To find the leading powers, try

$$
\phi(z,x) \sim z^\alpha f(x).
$$

Substituting into the near-boundary equation gives

$$
\alpha(\alpha-d)-m^2L^2=0.
$$

The two roots are

$$
\alpha = \Delta_\pm,
\qquad
\Delta_\pm
=
\frac d2 \pm \nu,
\qquad
\nu
=
\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

It is conventional in standard quantization to define

$$
\Delta \equiv \Delta_+,
\qquad
\Delta_- = d-\Delta.
$$

Then the near-boundary expansion has the schematic form

$$
\phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)
+
z^\Delta A(x)
+
\cdots .
$$

The omitted terms include derivatives of $\phi_{(0)}$, possible local terms, and sometimes logarithms. Those details matter in holographic renormalization, but the main lesson is already visible: the scalar equation has two independent asymptotic behaviors.

In standard quantization:

$$
\boxed{\text{source: }\phi_{(0)}(x)}
$$

and

$$
\boxed{\text{response: }A(x)\text{, related to }\langle \mathcal O(x)\rangle.}
$$

The coefficient $A(x)$ is not chosen independently once the source and the state are fixed. It is determined by solving the bulk equation with an interior condition: regularity in Euclidean AdS, normalizability in global AdS, infalling behavior at a Lorentzian horizon, or some other state-dependent prescription.

## The mass-dimension relation

The near-boundary exponent is not just a property of a differential equation. It is the CFT scaling dimension.

A scalar primary operator of dimension $\Delta$ transforms under scale transformations as

$$
\mathcal O(\lambda x)=\lambda^{-\Delta}\mathcal O(x).
$$

The source term in the QFT action,

$$
\int d^d x\,\phi_{(0)}(x)\mathcal O(x),
$$

must be dimensionless. Therefore the source has scaling dimension

$$
[\phi_{(0)}]=d-\Delta.
$$

Now recall that in Poincaré AdS the transformation

$$
z\to \lambda z,
\qquad
x^\mu\to \lambda x^\mu
$$

is an AdS isometry. The near-boundary term

$$
z^{d-\Delta}\phi_{(0)}(x)
$$

has exactly the right scaling if $\phi_{(0)}$ is a source of dimension $d-\Delta$. Thus the bulk falloff and the CFT scaling law are the same statement in two languages.

The result is

$$
\boxed{m^2L^2=\Delta(\Delta-d).}
$$

Several quick checks are useful:

- If $m^2=0$, then $\Delta=0$ or $\Delta=d$. In standard quantization, the nontrivial scalar operator usually has $\Delta=d$.
- A positive $m^2$ gives $\Delta>d$.
- A negative $m^2$ can still be stable in AdS, as long as it is not too negative.

The last point is special to AdS and is important enough to discuss separately.

## Negative mass squared and the BF bound

In flat space, a scalar with $m^2<0$ is tachyonic: long-wavelength modes grow exponentially, signaling an instability. In AdS, negative mass squared is not automatically unstable. The gravitational potential of AdS acts like a confining box, and stability is controlled by the Breitenlohner–Freedman bound.

The parameter

$$
\nu
=
\sqrt{\frac{d^2}{4}+m^2L^2}
$$

must be real for the two asymptotic powers to be real. This gives

$$
\boxed{m^2L^2\ge -\frac{d^2}{4}.}
$$

This is the BF bound.

At the bound,

$$
\Delta_+=\Delta_- = \frac d2,
$$

and logarithmic behavior appears. Below the bound, $\nu$ is imaginary and the theory is unstable under the usual AdS boundary conditions.

The BF bound is a good example of why intuition imported from flat spacetime must be used carefully in AdS. A scalar can have negative $m^2$ and still correspond to a perfectly acceptable CFT operator, provided the dimension is real and respects the appropriate CFT unitarity constraints.

## Standard and alternate quantization

For most scalar masses, the standard quantization is the only usual choice: the coefficient of $z^{d-\Delta}$ is the source, and the coefficient of $z^\Delta$ is the response.

However, when the mass lies in the window

$$
-\frac{d^2}{4}
<
m^2L^2
<
-\frac{d^2}{4}+1,
$$

both falloffs are sufficiently normalizable to allow another consistent choice of boundary condition. In this alternate quantization, the roles of the two modes are exchanged, and the dual operator has dimension

$$
\Delta_- = d-\Delta_+.
$$

This is not merely a notational trick. It corresponds to a different CFT or to a different boundary condition for the same bulk field. Mixed boundary conditions are also possible and are related to multi-trace deformations on the field-theory side.

For this foundations course, the default convention is standard quantization unless explicitly stated otherwise.

## Solving the scalar equation in momentum space

Now solve the equation more explicitly. Fourier transform along the boundary directions:

$$
\phi(z,x)
=
\int \frac{d^d k}{(2\pi)^d}\,e^{ik\cdot x}\phi(z,k).
$$

In Euclidean signature, with $k^2\ge 0$, the scalar equation becomes

$$
\left[
 z^2\partial_z^2
 -(d-1)z\partial_z
 -z^2 k^2
 -m^2L^2
\right]
\phi(z,k)=0.
$$

The two independent solutions are modified Bessel functions:

$$
\phi(z,k)
=
z^{d/2}
\left[
 a(k) I_\nu(|k|z)
 +
 b(k) K_\nu(|k|z)
\right].
$$

For Euclidean AdS, regularity in the interior $z\to\infty$ selects $K_\nu$, since $I_\nu$ grows exponentially. Near $z=0$,

$$
K_\nu(|k|z)
\sim
\frac12\Gamma(\nu)\left(\frac{|k|z}{2}\right)^{-\nu}
+
\frac12\Gamma(-\nu)\left(\frac{|k|z}{2}\right)^\nu
+
\cdots,
$$

for non-integer $\nu$. Multiplying by $z^{d/2}$ gives precisely the two powers

$$
z^{d/2-\nu}=z^{d-\Delta},
\qquad
z^{d/2+\nu}=z^\Delta.
$$

Thus regularity in the interior fixes the ratio between the source coefficient and the response coefficient. This is the seed of the two-point function calculation: the on-shell action evaluated on this regular solution becomes a functional of the boundary source.


## The on-shell action is a boundary term

The source-response interpretation becomes more concrete when we look at the action. Integrating the quadratic scalar action by parts gives

$$
S_\phi
=
\frac12
\int d^{d+1}X\,\sqrt{-g}\,\phi(\nabla^2-m^2)\phi
-
\frac12
\int_{z=\epsilon} d^d x\,\sqrt{|\gamma|}\,\phi\,n^M\partial_M\phi,
$$

up to sign conventions for the outward normal. Here $\gamma_{\mu\nu}$ is the induced metric on the cutoff surface $z=\epsilon$, and $n^M$ is the unit normal.

On a solution of the equation of motion, the bulk term vanishes, so the regulated on-shell action is a boundary functional:

$$
S_{\text{on-shell}}^{\epsilon}
=
-\frac12
\int_{z=\epsilon} d^d x\,\sqrt{|\gamma|}\,\phi\,n^M\partial_M\phi.
$$

This is the mechanical reason the boundary data matter so much. In the classical approximation, the bulk path integral is dominated by

$$
\exp\!\left(iS_{\text{on-shell}}[\phi_{(0)}]\right)
$$

in Lorentzian signature, or

$$
\exp\!\left(-S_{E,\text{on-shell}}[\phi_{(0)}]\right)
$$

in Euclidean signature. The on-shell action is a functional of the boundary source because the classical solution is determined by that source and by the interior condition.

As $\epsilon\to0$, this boundary term usually diverges. The divergent pieces are local functionals of the source and are removed by holographic counterterms. The finite nonlocal piece is what carries CFT correlator data.

This is the first appearance of a theme that will return many times:

$$
\text{radial canonical momentum}
\quad
\longleftrightarrow
\quad
\text{boundary one-point function}.
$$

For a scalar, the radial momentum is schematically

$$
\Pi_\phi
=
\frac{\delta S}{\delta(\partial_z\phi)}
\sim
\sqrt{|\gamma|}\,n^z\partial_z\phi.
$$

After renormalization, varying the on-shell action with respect to $\phi_{(0)}$ gives $\langle\mathcal O\rangle$. Thus the normal derivative of the bulk field near the boundary is the gravitational ancestor of the boundary response.

## Bulk-to-boundary propagator

The Euclidean solution can also be written directly in position space. The bulk-to-boundary propagator for a scalar of dimension $\Delta$ in Euclidean Poincaré AdS is

$$
K_\Delta(z,x;x')
=
C_\Delta
\left(
\frac{z}{z^2+|x-x'|^2}
\right)^\Delta,
$$

where

$$
C_\Delta
=
\frac{\Gamma(\Delta)}{
\pi^{d/2}\Gamma\left(\Delta-\frac d2\right)
}
$$

for a common normalization. Then a classical solution sourced by $\phi_{(0)}$ can be written schematically as

$$
\phi(z,x)
=
\int d^d x'\,K_\Delta(z,x;x')\phi_{(0)}(x').
$$

The normalization convention is not universal, and different choices shift constants in correlators. What matters structurally is that the bulk solution is determined by boundary source data and an interior regularity condition.

Later, Witten diagrams will use this propagator as the line connecting a boundary insertion to a bulk interaction point.

## Normalizable modes in global AdS

Poincaré AdS is natural for flat-space CFT correlators. Global AdS is natural for states.

In global coordinates,

$$
ds^2
=
L^2
\left(
-\cosh^2\rho\,dt^2
+d\rho^2
+\sinh^2\rho\,d\Omega_{d-1}^2
\right),
$$

try separated solutions

$$
\phi(t,\rho,\Omega)
=
e^{-i\omega t}Y_\ell(\Omega)R(\rho).
$$

Regularity at the center $\rho=0$ and normalizability near the boundary quantize the frequencies:

$$
\boxed{\omega_{n,\ell}=\Delta+\ell+2n,}
\qquad
n=0,1,2,\ldots,
\qquad
\ell=0,1,2,\ldots .
$$

This formula has a beautiful CFT interpretation. On the cylinder, a primary operator of dimension $\Delta$ creates a state of energy $\Delta$. Acting with derivatives produces descendants with energies increased by integers. The bulk quantum numbers $\ell$ and $n$ organize the angular and radial excitations of the corresponding bulk particle.

The lowest global AdS mode has frequency

$$
\omega=\Delta.
$$

This matches the state-operator correspondence:

$$
\text{CFT primary of dimension }\Delta
\quad\longleftrightarrow\quad
\text{single-particle bulk state of energy }\Delta.
$$

This is the Hilbert-space version of the same mass-dimension relation.

## Source, response, and state

It is tempting to say that the two coefficients in

$$
\phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)
+
z^\Delta A(x)
$$

are simply independent boundary data. That is not the holographic interpretation.

In a well-posed problem, one usually fixes the source $\phi_{(0)}(x)$ and then solves the bulk equation with a condition in the interior. The resulting solution determines $A(x)$. In the dual QFT, this is exactly how a one-point function behaves: once the source and state are specified, $\langle \mathcal O(x)\rangle$ is determined.

A useful schematic formula is

$$
\langle \mathcal O(x)\rangle
=
(2\Delta-d)A(x)
+
\text{local terms in }\phi_{(0)}.
$$

The local terms are fixed by holographic renormalization and depend on conventions, counterterms, and possible logarithmic terms. Therefore one should not identify $A(x)$ with the renormalized expectation value too naively. The correct statement is:

$$
\boxed{
A(x)\text{ is the nonlocal, state-dependent response data from which }\langle\mathcal O(x)\rangle\text{ is extracted.}
}
$$

This distinction becomes essential when computing stress tensors, anomalies, finite-density observables, and real-time response functions.

## What changes in Lorentzian signature?

In Euclidean signature, regularity usually selects a unique solution for a given source. Lorentzian signature is subtler because waves can propagate, reflect, fall through horizons, or be prepared in different states.

For pure global AdS, one can impose normalizability and specify initial data. The spectrum is discrete because AdS behaves like a box.

For Poincaré AdS, the horizon-like surface at $z\to\infty$ requires a prescription, especially for real-time correlators.

For AdS black holes or black branes, the horizon condition is central. Retarded Green's functions are computed by imposing infalling boundary conditions at the future horizon. This is the real-time analogue of selecting the physically appropriate interior behavior.

So the schematic instruction

$$
\text{fix source at boundary, impose interior condition, read response}
$$

is universal, but the correct interior condition depends on the state and signature.

## Beyond scalars

The scalar field teaches the main lesson, but AdS/CFT also uses fields with spin.

A few core examples are:

| Bulk field | Boundary data | Dual operator |
|---|---|---|
| scalar $\phi$ | leading scalar coefficient $\phi_{(0)}$ | scalar operator $\mathcal O$ |
| gauge field $A_M$ | boundary gauge potential $A_{(0)\mu}$ | conserved current $J^\mu$ |
| metric $g_{MN}$ | boundary metric $g_{(0)\mu\nu}$ | stress tensor $T^{\mu\nu}$ |
| spinor $\psi$ | leading spinor component | fermionic operator $\mathcal O_\psi$ |

For a massless bulk gauge field, the dual current is conserved:

$$
\nabla_\mu J^\mu=0,
$$

and its scaling dimension is fixed by conservation:

$$
\Delta_J=d-1.
$$

For the bulk metric, the dual operator is the stress tensor, with

$$
\Delta_T=d.
$$

This matching is not accidental. Bulk gauge invariance becomes boundary current conservation, and bulk diffeomorphism invariance becomes boundary stress-tensor Ward identities. Later pages will make these statements precise.

### Gauge fields

For a Maxwell field in AdS,

$$
S_A
=
-\frac{1}{4g_{d+1}^2}
\int d^{d+1}X\sqrt{-g}\,F_{MN}F^{MN},
$$

a convenient near-boundary gauge is $A_z=0$. For $d>2$, the boundary components have the schematic expansion

$$
A_\mu(z,x)
=
A_{(0)\mu}(x)
+
\cdots
+
z^{d-2}A_{(d-2)\mu}(x)
+
\cdots.
$$

The leading coefficient $A_{(0)\mu}$ is a background gauge field coupled to the conserved current:

$$
\int d^dx\sqrt{|g_{(0)}|}\,A_{(0)\mu}J^\mu.
$$

Since $A_{(0)\mu}$ has dimension one, current conservation is consistent with

$$
\Delta_J=d-1.
$$

The subleading coefficient is related to $\langle J^\mu\rangle$. Gauge invariance of the bulk action implies the boundary Ward identity, schematically

$$
\nabla_\mu\langle J^\mu\rangle=0,
$$

unless external sources or anomalies modify it. The important conceptual point is that a bulk gauge symmetry is dual to a boundary global symmetry. The source $A_{(0)\mu}$ is usually a nondynamical background field in the CFT, not automatically a dynamical boundary photon.

### Metric fluctuations

The metric itself is the bulk field dual to the stress tensor. In Fefferman–Graham gauge,

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2+g_{\mu\nu}(z,x)dx^\mu dx^\nu
\right),
$$

with expansion

$$
g_{\mu\nu}(z,x)
=
g_{(0)\mu\nu}(x)
+
z^2g_{(2)\mu\nu}(x)
+
\cdots
+
z^d g_{(d)\mu\nu}(x)
+
\cdots.
$$

The leading term $g_{(0)\mu\nu}$ is the boundary metric, or more precisely a representative of the boundary conformal class. It sources the stress tensor:

$$
\frac12\int d^dx\sqrt{|g_{(0)}|}\,h_{(0)\mu\nu}T^{\mu\nu}.
$$

After holographic renormalization, the response data in the metric expansion determine $\langle T_{\mu\nu}\rangle$. Bulk diffeomorphism invariance becomes stress-tensor conservation, while Weyl transformations of the boundary representative control the trace Ward identity. In even boundary dimension this trace identity can include a conformal anomaly.

### Spinors

Spinors are slightly different because the radial Dirac equation is first order. A bulk spinor of mass $m$ has asymptotic behavior of the schematic form

$$
\psi
\sim
z^{d/2-mL}\psi_{(0)}
+
z^{d/2+mL}\psi_{(1)},
$$

with the two coefficients living in opposite eigenspaces of the radial gamma matrix. In standard quantization, the dual fermionic operator has dimension

$$
\Delta_\psi=\frac d2+|mL|,
$$

with alternate quantization possible in a restricted mass range.

## A useful physical picture

A bulk scalar field has two personalities.

First, it is a normal field in a curved spacetime. You can solve its wave equation, quantize its normal modes, study its propagators, and compute its interactions.

Second, because the spacetime is asymptotically AdS, the same field also defines a boundary-value problem. Its leading behavior is not merely an arbitrary asymptotic coefficient; it is a source in the dual QFT. Its subleading behavior is not merely another coefficient; it is the response of the dual operator.

The same object therefore knows about both sides of the duality:

$$
\text{bulk dynamics}
\quad
\longrightarrow
\quad
\text{boundary response}.
$$

This is why the scalar wave equation is the first real computational bridge between geometry and quantum field theory.

## Dictionary checkpoint

For a scalar field in AdS$_{d+1}$:

$$
(\nabla^2-m^2)\phi=0
$$

near the boundary gives

$$
\phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)
+
z^\Delta A(x).
$$

In standard quantization,

$$
\phi_{(0)}(x)
\quad\longleftrightarrow\quad
\text{source for }\mathcal O(x),
$$

$$
A(x)
\quad\longleftrightarrow\quad
\text{response data related to }\langle\mathcal O(x)\rangle,
$$

and

$$
m^2L^2=\Delta(\Delta-d).
$$

In global AdS, normalizable scalar modes have frequencies

$$
\omega_{n,\ell}=\Delta+\ell+2n,
$$

matching the energies of a primary operator and its descendants on the CFT cylinder.

## Common confusions

### “The boundary value is literally $\phi(z=0,x)$.”

Usually not. For $\Delta>d/2$, the leading term behaves as $z^{d-\Delta}$, which may diverge or vanish as $z\to0$ depending on $\Delta$. The source is the coefficient $\phi_{(0)}(x)$ after extracting the prescribed power of $z$, not the naive value of the field at $z=0$.

### “The normalizable coefficient is always the vev.”

It is related to the vev, but holographic renormalization can add local terms. The safer statement is that the normalizable coefficient contains the state-dependent response data. The renormalized one-point function is obtained by varying the renormalized on-shell action.

### “Negative $m^2$ means an instability.”

Not necessarily in AdS. Scalars are stable above the BF bound,

$$
m^2L^2\ge -\frac{d^2}{4}.
$$

AdS permits stable fields with negative mass squared because the asymptotic structure changes the stability problem.

### “The two falloffs are always source and vev in the same way.”

That is true in standard quantization for the usual mass range. In the alternate-quantization window, the interpretation can be exchanged. Mixed boundary conditions are also possible and correspond to multi-trace deformations.

### “Euclidean regularity and Lorentzian infalling boundary conditions are the same thing.”

They are related but not identical. Euclidean regularity is appropriate for Euclidean correlators and thermal saddle points. Lorentzian retarded correlators require causal boundary conditions, such as infalling behavior at a horizon.

## Exercises

### Exercise 1: Derive the indicial equation

Starting from

$$
\left[
 z^2\partial_z^2
 -(d-1)z\partial_z
 +z^2\Box_x
 -m^2L^2
\right]
\phi=0,
$$

insert the near-boundary ansatz $\phi(z,x)=z^\alpha f(x)$ and derive the equation for $\alpha$.

<details>
<summary><strong>Solution</strong></summary>

Near $z=0$, the term $z^2\Box_x\phi$ is subleading compared with the radial derivative terms, assuming $f(x)$ is smooth. We compute

$$
\partial_z z^\alpha = \alpha z^{\alpha-1},
\qquad
\partial_z^2 z^\alpha=\alpha(\alpha-1)z^{\alpha-2}.
$$

Therefore

$$
z^2\partial_z^2 z^\alpha
=
\alpha(\alpha-1)z^\alpha,
$$

and

$$
-(d-1)z\partial_z z^\alpha
=
-(d-1)\alpha z^\alpha.
$$

The leading equation is

$$
\left[
\alpha(\alpha-1)-(d-1)\alpha-m^2L^2
\right]z^\alpha f(x)=0.
$$

Thus

$$
\alpha(\alpha-d)-m^2L^2=0.
$$

The two roots are

$$
\alpha=\frac d2\pm\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

</details>

### Exercise 2: Find the operator dimension of a massless scalar

For a scalar field with $m^2=0$ in AdS$_{d+1}$, solve

$$
m^2L^2=\Delta(\Delta-d)
$$

for $\Delta$. Which root is used in standard quantization?

<details>
<summary><strong>Solution</strong></summary>

For $m^2=0$,

$$
\Delta(\Delta-d)=0.
$$

The roots are

$$
\Delta=0,
\qquad
\Delta=d.
$$

In standard quantization, one normally takes

$$
\Delta=d.
$$

The other root corresponds to the alternate branch and is not the usual choice for the standard scalar operator in the basic AdS/CFT dictionary.

</details>

### Exercise 3: Check the BF bound in AdS$_5$

For AdS$_5$, the boundary dimension is $d=4$. What is the BF bound? What are the possible dimensions for a scalar with $m^2L^2=-3$?

<details>
<summary><strong>Solution</strong></summary>

For AdS$_5$, $d=4$, so the BF bound is

$$
m^2L^2\ge -\frac{d^2}{4}=-4.
$$

The value $m^2L^2=-3$ is above the BF bound. The dimension relation is

$$
-3=\Delta(\Delta-4).
$$

Thus

$$
\Delta^2-4\Delta+3=0,
$$

so

$$
(\Delta-1)(\Delta-3)=0.
$$

The two roots are

$$
\Delta_-=1,
\qquad
\Delta_+=3.
$$

In standard quantization, the operator dimension is $\Delta=3$. This value sits at the upper endpoint of the usual alternate-quantization window,

$$
-4<m^2L^2<-3,
$$

with the alternate branch $\Delta_-=1$ saturating the scalar unitarity bound. Endpoint cases require some care because logarithmic or marginal effects can appear depending on the boundary condition. For the basic standard-quantization dictionary, the answer is $\Delta=3$.

</details>

### Exercise 4: Global normal modes and descendants

A scalar field in global AdS$_{d+1}$ has normal mode frequencies

$$
\omega_{n,\ell}=\Delta+\ell+2n.
$$

Explain why the lowest mode has a natural interpretation as a CFT primary state.

<details>
<summary><strong>Solution</strong></summary>

The lowest mode has $n=0$ and $\ell=0$, so

$$
\omega_{0,0}=\Delta.
$$

In a CFT quantized on the cylinder $\mathbb R\times S^{d-1}$, the Hamiltonian is the dilatation operator of the flat-space theory. A primary operator of dimension $\Delta$ creates a cylinder state of energy $\Delta$.

Therefore the lowest normalizable scalar mode in global AdS has exactly the energy expected for the state created by the dual primary operator. Modes with larger $\ell$ and $n$ correspond to descendants and additional bulk excitations.

</details>

## Further reading

- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- P. Breitenlohner and D. Z. Freedman, [Stability in Gauged Extended Supergravity](https://doi.org/10.1016/0003-4916(82)90116-6).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
