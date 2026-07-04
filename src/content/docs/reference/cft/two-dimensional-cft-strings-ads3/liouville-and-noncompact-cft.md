---
title: "Liouville and Noncompact CFT"
description: "Continuous spectra, Liouville theory, background charge, reflection, non-normalizable operators, and why noncompact CFTs matter for strings and AdS3/CFT2."
sidebar:
  order: 4
---

The previous pages emphasized **rational** and highly algebraic two-dimensional CFTs: minimal models, modular invariant partition functions, affine current algebras, and WZW models with compact symmetry. Those theories often have a discrete set of primary fields, finite fusion rules, and characters that transform among themselves under $SL(2,\mathbb Z)$.

Noncompact CFTs are different. Their fields often take values in a noncompact target space. Their Hilbert spaces often contain continuous spectra. Their OPEs usually involve integrals rather than finite sums. Their two-point functions contain delta functions. Some of their most useful operators are not normalizable states. This sounds less tidy, but it is exactly what one should expect from a CFT describing a radial direction, a scattering problem, a linear dilaton, or the worldsheet of strings moving in a noncompact spacetime.

For AdS/CFT preparation, the main lesson is this:

$$
\text{compact rational CFTs teach exact algebraic control,}
$$

while

$$
\text{noncompact CFTs teach spectra, scattering, radial directions, and sources.}
$$

Liouville theory is the paradigmatic example. It is a two-dimensional CFT with a noncompact scalar field $\phi$, a background charge $Q$, an exponential potential $\mu e^{2b\phi}$, central charge

$$
c_L=1+6Q^2,
\qquad
Q=b+b^{-1},
$$

and a continuous spectrum of normalizable primary states

$$
\alpha=\frac Q2+iP,
\qquad
P\in \mathbb R_{\ge 0},
\qquad
h_\alpha=\bar h_\alpha=\frac{Q^2}{4}+P^2.
$$

This page introduces Liouville theory and then places it in the broader class of noncompact CFTs relevant for string theory and AdS$_3$/CFT$_2$.

<figure class="doc-figure" style="--figure-width: 44rem; --caption-width: 55rem;">

![Liouville theory as scattering from an exponential wall, with continuum spectrum alpha equals Q over 2 plus iP.](/figures/cft/liouville-noncompact-spectrum.svg)

<figcaption>

Liouville theory is usefully pictured as scattering in the zero mode $\phi$. The weak-coupling region is $\phi\to -\infty$, while the exponential interaction $\mu e^{2b\phi}$ creates a wall toward $\phi\to +\infty$. Normalizable states are labeled by $\alpha=Q/2+iP$ with $P\in\mathbb R_{\ge0}$. Reflection from the wall identifies the two Liouville momenta $P$ and $-P$, equivalently $V_\alpha\sim V_{Q-\alpha}$ up to a reflection amplitude.

</figcaption>
</figure>

## 1. What changes in a noncompact CFT?

In a compact rational CFT, one often writes the Hilbert space schematically as a discrete sum

$$
\mathcal H
=
\bigoplus_{i,j}N_{ij}\,\mathcal V_i\otimes \bar{\mathcal V}_j,
$$

where $\mathcal V_i$ are irreducible representations of the chiral algebra, and the multiplicities $N_{ij}$ are nonnegative integers. The OPE of two primaries is likewise a discrete sum,

$$
\mathcal O_i\times \mathcal O_j
\sim
\sum_k C_{ij}{}^k\,\mathcal O_k+\text{descendants}.
$$

In a noncompact CFT, the corresponding formulas are often direct integrals. A typical Hilbert space has the form

$$
\mathcal H
=
\int_{\mathcal S}^{\oplus} d\mu(\lambda)\,
\mathcal V_\lambda\otimes\bar{\mathcal V}_\lambda
\oplus
\mathcal H_{\rm discrete},
$$

where $\lambda$ is a continuous label and $d\mu(\lambda)$ is a spectral measure. The OPE becomes

$$
\mathcal O_{\lambda_1}(x)\mathcal O_{\lambda_2}(0)
\sim
\int_{\mathcal S} d\mu(\lambda)\,
C(\lambda_1,\lambda_2,\lambda)\,
|x|^{\Delta_\lambda-\Delta_1-\Delta_2}\,
\mathcal O_\lambda(0)+\cdots .
$$

The two-point function of normalizable primaries contains delta functions rather than Kronecker deltas:

$$
\langle \mathcal O_\lambda(x)\mathcal O_{\lambda'}(0)\rangle
\propto
\frac{\delta(\lambda-\lambda')}{|x|^{2\Delta_\lambda}}.
$$

This is not a pathology. It is the CFT version of plane-wave normalization in ordinary quantum mechanics. Momentum eigenstates in $\mathbb R^d$ are not square-integrable, but they form a perfectly useful delta-normalized basis. Noncompact CFTs are similar, except that the continuous label may be momentum, spin, Liouville momentum, or a representation-theoretic parameter.

There are three recurring distinctions to keep straight.

First, **normalizable states** are states in the Hilbert space, usually delta-normalized. They are the analogues of scattering states.

Second, **non-normalizable operators** are often not states in the Hilbert space but are still excellent local insertions. In a path integral, they may specify boundary conditions or sources. This is conceptually close to the AdS/CFT distinction between normalizable bulk modes and non-normalizable source modes, although the two contexts should not be identified too literally.

Third, **analytic continuation** is not optional window dressing. Many exact formulas in noncompact CFT are first derived in a convergent domain and then analytically continued to the physical spectrum. The price of exact solvability is that one must be comfortable with distributions and meromorphic functions, not just finite-dimensional matrices.

## 2. Warm-up: the noncompact free boson

The simplest noncompact CFT is a free scalar field $X$ valued on the real line rather than on a circle:

$$
X\in \mathbb R.
$$

Its vertex operators are momentum eigenoperators,

$$
V_p(z,\bar z)=e^{ipX(z,\bar z)},
\qquad
p\in\mathbb R.
$$

The label $p$ is continuous. Momentum conservation gives

$$
\langle V_{p_1}(z_1,\bar z_1)\cdots V_{p_n}(z_n,\bar z_n)\rangle
\propto
\delta\!\left(\sum_i p_i\right)
\times
\text{position-dependent factor}.
$$

If instead $X$ is compactified on a circle $X\sim X+2\pi R$, momenta become quantized and winding appears:

$$
p_L=\frac nR+wR,
\qquad
p_R=\frac nR-wR,
\qquad
n,w\in\mathbb Z,
$$

up to convention-dependent factors. This is why compact bosons behave more like rational or nearly rational CFTs at special radii, while noncompact bosons have continuous spectra.

The noncompact free boson already teaches a basic lesson: a CFT can be unitary, local, and perfectly consistent even when its spectrum is continuous and its partition function has volume divergences.

Liouville theory adds a background charge and an exponential wall. Those two ingredients turn the free noncompact boson into a much richer interacting CFT.

## 3. The linear dilaton and background charge

Consider a scalar field $\phi$ with a background charge $Q$. In standard Liouville conventions, the free linear-dilaton part of the action is

$$
S_{\rm lin}
=
\frac{1}{4\pi}
\int_\Sigma d^2x\sqrt g\,
\left(
 g^{ab}\partial_a\phi\partial_b\phi
 +Q R\phi
\right).
$$

The curvature coupling $Q R\phi$ is a total derivative on a flat worldsheet, but it is not irrelevant. It changes the stress tensor and the central charge. In local complex coordinates, the holomorphic stress tensor is

$$
T(z)
=
-\frac12 :\partial\phi\partial\phi:
+Q\partial^2\phi.
$$

With these conventions,

$$
c=1+6Q^2.
$$

The exponential operators are written

$$
V_\alpha(z,\bar z)=e^{2\alpha\phi(z,\bar z)}.
$$

Their holomorphic and antiholomorphic dimensions are

$$
h_\alpha=\bar h_\alpha=\alpha(Q-\alpha).
$$

This formula is one of the most important formulas on the page. It implies the reflection symmetry

$$
h_\alpha=h_{Q-\alpha}.
$$

So $\alpha$ and $Q-\alpha$ label operators with the same conformal dimension. In Liouville theory, this degeneracy is not accidental: the two operators are related by a reflection amplitude.

The continuous normalizable spectrum is obtained by writing

$$
\alpha=\frac Q2+iP,
\qquad
P\in\mathbb R.
$$

Then

$$
h_\alpha
=
\left(\frac Q2+iP\right)
\left(\frac Q2-iP\right)
=
\frac{Q^2}{4}+P^2.
$$

Thus the spectrum begins at $h=Q^2/4$ and is continuous above it. This lower edge is sometimes called the continuum threshold.

## 4. Liouville theory

Liouville theory adds the exponential interaction

$$
S_L
=
\frac{1}{4\pi}
\int_\Sigma d^2x\sqrt g\,
\left(
 g^{ab}\partial_a\phi\partial_b\phi
 +Q R\phi
 +4\pi\mu e^{2b\phi}
\right).
$$

The parameter $\mu$ is the Liouville cosmological constant. The interaction is conformal only if $e^{2b\phi}$ is a $(1,1)$ operator. Since

$$
h_b=b(Q-b),
$$

marginality requires

$$
b(Q-b)=1.
$$

This is solved by

$$
Q=b+b^{-1}.
$$

With this choice,

$$
c_L=1+6(b+b^{-1})^2.
$$

For real positive $b$, this gives $c_L>25$. This is the usual **spacelike Liouville theory**, the unitary version most often used in noncritical string theory and in discussions of two-dimensional quantum gravity. There are also timelike continuations, but they are subtler and are not needed for the basic AdS/CFT preparation path.

The Liouville interaction creates an exponential wall. For $\mu>0$ and $b>0$, the potential grows rapidly as

$$
\phi\to +\infty,
$$

while the region

$$
\phi\to -\infty
$$

is approximately a linear-dilaton region. A normalizable state is therefore naturally interpreted as a wave coming from the weak-coupling region, reflecting off the Liouville wall, and returning.

This scattering picture explains why the spectrum is continuous and why reflection is fundamental.

## 5. Reflection: $V_\alpha$ and $V_{Q-\alpha}$

Because

$$
h_\alpha=h_{Q-\alpha},
$$

Liouville theory identifies the two exponential operators up to a reflection coefficient:

$$
V_\alpha
=
\mathcal R(\alpha)\,V_{Q-\alpha}.
$$

On the physical line

$$
\alpha=\frac Q2+iP,
$$

reflection sends

$$
P\mapsto -P.
$$

This is why one may restrict the physical momentum to

$$
P\in\mathbb R_{\ge0}.
$$

The two-point function is consequently not just a simple power law with an ordinary constant. Schematically, for states on the physical line one finds a delta-normalized structure of the form

$$
\langle V_{Q/2+iP}(z,\bar z)V_{Q/2+iP'}(0)\rangle
\sim
\frac{\delta(P-P')+\mathcal R(P)\delta(P+P')}{|z|^{4h_P}},
$$

where

$$
h_P=\frac{Q^2}{4}+P^2.
$$

The precise normalization depends on conventions and on whether one lets $P$ range over all real values or only $P\ge0$. The invariant point is the physical one: Liouville primaries are scattering states, and the reflection amplitude is part of the CFT data.

## 6. Correlation functions and the DOZZ structure constant

A generic three-point function of scalar primaries is fixed by global conformal invariance up to a structure constant:

$$
\langle
V_{\alpha_1}(z_1,\bar z_1)
V_{\alpha_2}(z_2,\bar z_2)
V_{\alpha_3}(z_3,\bar z_3)
\rangle
=
\frac{C_L(\alpha_1,\alpha_2,\alpha_3)}
{|z_{12}|^{2(h_1+h_2-h_3)}
 |z_{23}|^{2(h_2+h_3-h_1)}
 |z_{13}|^{2(h_1+h_3-h_2)}}.
$$

Here

$$
h_i=\alpha_i(Q-\alpha_i).
$$

In a generic CFT, $C_L$ would be unknown dynamical data. The remarkable fact about Liouville theory is that this structure constant is known exactly. It is called the **DOZZ structure constant**, after Dorn-Otto and Zamolodchikov-Zamolodchikov.

For this course, the exact special-function expression is less important than its meaning. The DOZZ constant is the continuous-spectrum analogue of the three-point coefficients $C_{ijk}$ in a compact CFT. It is one of the fundamental pieces of Liouville CFT data.

The OPE is then an integral over the physical Liouville spectrum:

$$
V_{\alpha_1}(z,\bar z)V_{\alpha_2}(0)
\sim
\int_0^\infty dP\,
C_L\!\left(\alpha_1,\alpha_2,\frac Q2+iP\right)
|z|^{2(h_P-h_1-h_2)}
\left[V_{Q/2+iP}(0)+\text{descendants}\right].
$$

This formula should be compared with the minimal-model OPE

$$
\phi_i\times\phi_j
\sim
\sum_k C_{ij}{}^k\phi_k.
$$

The conceptual replacement is

$$
\sum_k
\quad\longrightarrow\quad
\int_0^\infty dP.
$$

The conformal block expansion of a Liouville four-point function is therefore

$$
\langle V_1V_2V_3V_4\rangle
=
\int_0^\infty dP\,
C_L(\alpha_1,\alpha_2,Q/2+iP)
C_L(Q/2-iP,\alpha_3,\alpha_4)
\left|\mathcal F_P(z)\right|^2,
$$

up to conventional normalizations and position-dependent prefactors. The internal channel is labeled by a continuous momentum $P$.

This is the cleanest two-dimensional example of a conformal bootstrap with a continuous spectrum.

## 7. Degenerate operators and BPZ equations

Although the physical Liouville spectrum is continuous, Liouville theory also contains special non-normalizable operators whose Virasoro representations are degenerate. These are labeled by positive integers $(m,n)$ and have momenta

$$
\alpha_{m,n}
=
\frac{1-m}{2}b+\frac{1-n}{2b}.
$$

The corresponding Verma modules contain null states. For example, the $(2,1)$ degenerate field has a level-two null vector. Correlation functions involving such a field satisfy a second-order BPZ differential equation.

This is one of the most powerful ways to solve Liouville theory. The logic is:

$$
\text{degenerate insertion}
\quad\Longrightarrow\quad
\text{BPZ differential equation}
\quad\Longrightarrow\quad
\text{shift equations for } C_L
\quad\Longrightarrow\quad
\text{DOZZ constant}.
$$

The important point is subtle. Degenerate operators are not generic normalizable states in the Liouville Hilbert space. They are analytic probes. Nevertheless, they constrain the exact CFT data.

This is a recurring theme in noncompact CFT: useful local operators need not be ordinary normalizable states.

## 8. Liouville theory and noncritical string theory

Liouville theory appeared historically in the quantization of the string worldsheet metric. In conformal gauge, one writes the worldsheet metric as

$$
g_{ab}=e^{2\varphi}\hat g_{ab}.
$$

The conformal factor $\varphi$ does not simply disappear in the quantum theory unless the total Weyl anomaly vanishes. In bosonic string theory, the ghost system contributes

$$
c_{\rm gh}=-26.
$$

If the matter CFT has central charge $c_m$, Weyl anomaly cancellation requires

$$
c_m+c_L-26=0.
$$

Thus

$$
c_L=26-c_m.
$$

Using

$$
c_L=1+6Q^2,
$$

one obtains

$$
Q^2=\frac{25-c_m}{6}.
$$

The Liouville field is then the quantum remnant of the worldsheet scale factor. It becomes a dynamical field because the conformal anomaly makes the Weyl mode physical.

This is why Liouville theory is so central to noncritical strings and two-dimensional quantum gravity. It is not just one more CFT; it is the CFT of the fluctuating worldsheet scale.

## 9. Noncompact WZW models and AdS$_3$

Liouville theory is not the only noncompact CFT relevant for strings. Another central family comes from noncompact group manifolds and cosets.

For strings on Euclidean AdS$_3$, one encounters the $H_3^+$ WZW model,

$$
H_3^+=SL(2,\mathbb C)/SU(2).
$$

For Lorentzian AdS$_3$, the relevant worldsheet theory is closely related to the $SL(2,\mathbb R)$ WZW model. These theories are noncompact, and their spectra involve continuous and discrete representations. In Lorentzian AdS$_3$, spectral flow sectors are essential for the string spectrum.

A related and very important coset is the two-dimensional cigar CFT,

$$
\frac{SL(2,\mathbb R)_k}{U(1)}.
$$

Geometrically, it describes the Euclidean two-dimensional black hole. Far from the tip, it looks like an asymptotic cylinder with a linear dilaton. Near the tip, the circle caps off smoothly.

This collection of examples gives a useful hierarchy:

$$
\begin{array}{ccl}
\text{linear dilaton} &:& \text{free noncompact field with background charge},\\
\text{Liouville} &:& \text{linear dilaton plus exponential wall},\\
SL(2,\mathbb R)/U(1) &:& \text{asymptotic linear dilaton plus smooth cigar cap},\\
SL(2,\mathbb R)\text{ WZW} &:& \text{worldsheet model for strings on AdS}_3.
\end{array}
$$

The common theme is that noncompact directions lead to continuous spectra, scattering data, and subtleties in separating states from sources.

## 10. Toda theory: many Liouville walls

Liouville theory has one scalar field and one exponential wall. Toda theory generalizes this to several scalar fields. For a simple Lie algebra $\mathfrak g$ of rank $r$, Toda theory has an $r$-component scalar

$$
\vec\phi\in\mathbb R^r
$$

and exponential interactions associated with the simple roots $\vec e_i$:

$$
S_{\rm Toda}
\sim
\frac{1}{4\pi}\int d^2x\sqrt g\,
\left[
(\partial\vec\phi)^2
+Q\,R\,\vec\rho\cdot\vec\phi
+4\pi\mu\sum_{i=1}^r e^{b\vec e_i\cdot\vec\phi}
\right].
$$

Here $\vec\rho$ is the Weyl vector. Liouville theory is the $A_1$ case. Toda theories have extended chiral algebras called $W$-algebras. They are important in AGT-type correspondences, higher-spin holography, and the representation theory of noncompact CFTs.

For this course, the takeaway is simple: Liouville is the one-dimensional prototype of a much broader class of noncompact CFTs with exponential walls and continuous momenta.

## 11. Normalizable versus non-normalizable: the holographic lesson

In an ordinary compact unitary CFT, local operators and states are tightly related by the state-operator correspondence. Every local operator inserted at the origin creates a state on the circle:

$$
\mathcal O(0)|0\rangle.
$$

In noncompact CFTs, the state-operator relation still exists, but the functional-analytic status of states becomes more delicate. Some operators create delta-normalizable states. Others create non-normalizable states or analytic continuations of states.

The distinction is physically valuable:

$$
\begin{array}{ccl}
\text{normalizable} &\leftrightarrow& \text{states in the Hilbert space},\\
\text{delta-normalizable} &\leftrightarrow& \text{scattering states},\\
\text{non-normalizable} &\leftrightarrow& \text{sources, boundary conditions, probes}.
\end{array}
$$

This is one reason Liouville theory is excellent preparation for AdS/CFT. In AdS/CFT, a bulk field near the boundary behaves schematically as

$$
\Phi(z,x)
\sim
z^{d-\Delta}J(x)+z^\Delta A(x).
$$

The coefficient $J(x)$ is a source for the boundary operator, while $A(x)$ is related to the expectation value or state data. This is not the same mathematical setup as Liouville reflection, but the conceptual habit is similar: one must distinguish source-like data from normalizable state-like data.

Noncompact CFTs train exactly this habit.

## 12. What survives from rational CFT?

Many rational-CFT tools survive, but in modified form.

The Virasoro algebra still controls descendants and conformal blocks:

$$
\mathcal F_P(z)
$$

is still a Virasoro conformal block.

Crossing symmetry still holds:

$$
\int dP\,
C_{12P}C_{P34}\,\mathcal F_P^{(s)}(z)\bar{\mathcal F}_P^{(s)}(\bar z)
=
\int dP\,
C_{14P}C_{P32}\,\mathcal F_P^{(t)}(1-z)\bar{\mathcal F}_P^{(t)}(1-\bar z).
$$

But the sum over intermediate primaries becomes an integral.

Modular invariance still exists, but the torus partition function is generally not a finite sesquilinear combination of characters. It contains integrals over continuous labels and often has volume divergences from noncompact zero modes.

Fusion still exists, but fusion coefficients become kernels or measures.

So the rational-CFT dictionary changes as follows:

$$
\begin{array}{ccl}
\text{finite set of primaries} &\longrightarrow& \text{continuous families of primaries},\\
\text{finite fusion coefficients} &\longrightarrow& \text{fusion kernels},\\
\text{Kronecker-normalized two-point functions} &\longrightarrow& \text{delta-normalized two-point functions},\\
\text{finite character vectors} &\longrightarrow& \text{characters plus continuous spectral integrals},\\
\text{operator sums} &\longrightarrow& \text{operator integrals}.
\end{array}
$$

This is not a loss of structure. It is a different kind of structure.

## 13. AdS/CFT checkpoint

Noncompact CFTs are not optional if one wants to understand holography deeply.

They prepare several AdS/CFT ideas:

1. **Radial directions.** Liouville theory has a noncompact coordinate $\phi$ with an exponential wall. This is a simple arena for thinking about radial motion, asymptotic regions, and reflection.

2. **Normalizable versus non-normalizable data.** Liouville separates scattering states from source-like insertions. AdS/CFT separates normalizable bulk modes from boundary sources.

3. **Continuous spectra.** Bulk physics often has continua: scattering states, black-hole thresholds, long strings, and noncompact momenta. Noncompact CFTs provide exact two-dimensional examples.

4. **Worldsheet AdS$_3$.** String theory on AdS$_3$ is described by noncompact current algebra, not by a compact rational CFT. Continuous representations, discrete representations, and spectral flow are essential.

5. **Exact solvability beyond rationality.** Liouville theory is exactly solvable but not rational. It shows that exact CFT does not mean finite CFT.

The most compact slogan is:

$$
\boxed{
\text{Liouville theory is the CFT of a radial scattering problem.}
}
$$

That is why it belongs in a modern CFT course aimed at AdS/CFT.

## 14. Common pitfalls

A few warnings save a lot of confusion.

**Pitfall 1: thinking continuous spectrum means nonunitary.** A theory can be perfectly unitary and have continuous spectrum. The noncompact free boson is the simplest example. Spacelike Liouville theory with real $b$ is also unitary.

**Pitfall 2: treating every local insertion as a normalizable state.** In noncompact CFT, many useful local insertions are non-normalizable. They are still part of the analytic CFT machinery.

**Pitfall 3: expecting rational-CFT modular formulas.** Modular invariance still matters, but the partition function generally involves integrals and regularized volumes.

**Pitfall 4: confusing Liouville momentum with target-space momentum.** The Liouville label $P$ is momentum conjugate to the Liouville zero mode. In string applications, it may be related to radial momentum, but the precise interpretation depends on the background.

**Pitfall 5: ignoring reflection.** The labels $\alpha$ and $Q-\alpha$ are not independent physical states. Reflection is part of the definition of Liouville CFT data.

## 15. Minimal formula sheet

The formulas most worth remembering are these:

$$
S_L
=
\frac{1}{4\pi}\int d^2x\sqrt g\,
\left[(\partial\phi)^2+QR\phi+4\pi\mu e^{2b\phi}\right],
$$

$$
Q=b+b^{-1},
\qquad
c_L=1+6Q^2,
$$

$$
V_\alpha=e^{2\alpha\phi},
\qquad
h_\alpha=\bar h_\alpha=\alpha(Q-\alpha),
$$

$$
\alpha=\frac Q2+iP,
\qquad
h_P=\bar h_P=\frac{Q^2}{4}+P^2,
\qquad
P\in\mathbb R_{\ge0},
$$

$$
V_\alpha=\mathcal R(\alpha)V_{Q-\alpha},
$$

$$
\mathcal H_L
=
\int_0^\infty dP\,
\mathcal V_{Q/2+iP}\otimes\bar{\mathcal V}_{Q/2+iP}.
$$

These are enough to recognize Liouville theory whenever it appears in string theory, two-dimensional gravity, or noncompact bootstrap problems.

## Exercises

### Exercise 1. Marginality of the Liouville interaction

Using

$$
h_\alpha=\alpha(Q-\alpha),
$$

show that the operator $e^{2b\phi}$ is marginal if $Q=b+b^{-1}$.

<details><summary><strong>Solution</strong></summary>

The interaction $e^{2b\phi}$ is the operator $V_b$, so its holomorphic dimension is

$$
h_b=b(Q-b).
$$

The full operator is marginal if

$$
h_b=\bar h_b=1.
$$

Using $Q=b+b^{-1}$ gives

$$
h_b=b(b+b^{-1}-b)=b\cdot b^{-1}=1.
$$

Therefore $e^{2b\phi}$ is a $(1,1)$ operator and can be added to the action without breaking conformal invariance.

</details>

### Exercise 2. The continuum threshold

Let

$$
\alpha=\frac Q2+iP,
\qquad
P\in\mathbb R.
$$

Show that

$$
h_\alpha=\frac{Q^2}{4}+P^2.
$$

Explain why $P$ and $-P$ have the same conformal dimension.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
h_\alpha=\alpha(Q-\alpha).
$$

For $\alpha=Q/2+iP$,

$$
Q-\alpha=\frac Q2-iP.
$$

Hence

$$
h_\alpha
=\left(\frac Q2+iP\right)\left(\frac Q2-iP\right)
=\frac{Q^2}{4}+P^2.
$$

This depends only on $P^2$, so $P$ and $-P$ have the same dimension. In Liouville theory this degeneracy is implemented by reflection,

$$
V_{Q/2+iP}\sim \mathcal R(P)V_{Q/2-iP}.
$$

</details>

### Exercise 3. From sums to integrals in the OPE

In a rational CFT, a four-point function of scalar primaries has a schematic conformal block decomposition

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\sum_p C_{12p}C_{p34}\,\mathcal F_p(z)\bar{\mathcal F}_p(\bar z).
$$

Write the analogous formula for Liouville theory, where the intermediate primary is labeled by $P\in\mathbb R_{\ge0}$.

<details><summary><strong>Solution</strong></summary>

The discrete sum over intermediate primaries becomes an integral over the Liouville momentum:

$$
\langle V_1V_2V_3V_4\rangle
=
\int_0^\infty dP\,
C_L(\alpha_1,\alpha_2,Q/2+iP)
C_L(Q/2-iP,\alpha_3,\alpha_4)
\mathcal F_P(z)\bar{\mathcal F}_P(\bar z),
$$

up to standard position-dependent prefactors and normalization conventions. The qualitative replacement is

$$
\sum_p
\quad\longrightarrow\quad
\int_0^\infty dP.
$$

</details>

### Exercise 4. Liouville central charge in noncritical strings

In bosonic noncritical string theory, suppose the matter CFT has central charge $c_m$. The ghost system has $c_{\rm gh}=-26$, and the Liouville field has

$$
c_L=1+6Q^2.
$$

Use total Weyl anomaly cancellation to find $Q^2$ in terms of $c_m$.

<details><summary><strong>Solution</strong></summary>

Weyl anomaly cancellation requires

$$
c_m+c_L+c_{\rm gh}=0.
$$

Since $c_{\rm gh}=-26$,

$$
c_m+c_L-26=0.
$$

Thus

$$
c_L=26-c_m.
$$

Using $c_L=1+6Q^2$ gives

$$
1+6Q^2=26-c_m,
$$

so

$$
Q^2=\frac{25-c_m}{6}.
$$

</details>

### Exercise 5. Semiclassical heavy operators

Let $b\to0$ with

$$
Q=b+b^{-1}\sim b^{-1}.
$$

Consider a Liouville momentum of the form

$$
\alpha=\frac{\eta}{b},
$$

where $\eta$ is fixed. Show that the dimension scales like $1/b^2$ and find the leading term.

<details><summary><strong>Solution</strong></summary>

We use

$$
h_\alpha=\alpha(Q-\alpha).
$$

For $b\to0$,

$$
Q=b+b^{-1}\sim b^{-1}.
$$

With $\alpha=\eta/b$,

$$
Q-\alpha
\sim
\frac{1}{b}-\frac{\eta}{b}
=
\frac{1-\eta}{b}.
$$

Therefore

$$
h_\alpha
\sim
\frac{\eta}{b}\cdot\frac{1-\eta}{b}
=
\frac{\eta(1-\eta)}{b^2}.
$$

So these are heavy operators in the semiclassical Liouville limit. Since

$$
c_L=1+6Q^2\sim \frac{6}{b^2},
$$

their dimensions scale like the central charge.

</details>

## Further reading

For the exact solution of Liouville theory, the classic references are the DOZZ papers by Dorn-Otto and by the Zamolodchikov brothers, together with Teschner's work on Liouville conformal blocks and crossing. For a pedagogical review, Nakayama's review of Liouville field theory is especially useful. For noncompact WZW models and AdS$_3$ strings, the standard path runs through work on $H_3^+$, $SL(2,\mathbb R)$ WZW models, spectral flow, and the $SL(2,\mathbb R)/U(1)$ cigar CFT.

The next page moves from noncompact 2D CFT to CFT on curved spaces and cylinders, where Weyl maps, finite-size effects, and Casimir energies become the bridge to thermal CFT and black holes.
