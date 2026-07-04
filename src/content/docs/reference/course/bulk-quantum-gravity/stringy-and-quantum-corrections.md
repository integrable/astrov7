---
title: "Stringy and Quantum Corrections"
description: "How finite coupling, finite N, higher-derivative terms, bulk loops, Kaluza-Klein towers, and nonperturbative effects correct the classical AdS/CFT limit."
sidebar:
  order: 60
---

The classical gravity limit is the most calculable corner of AdS/CFT, but it is not the full duality. The exact boundary CFT contains every correction: finite coupling, finite $N$, stringy towers, Kaluza–Klein modes, quantum loops, instantons, and nonperturbative spectral effects. Classical Einstein gravity is the result of taking a very special limit in which most of this structure is invisible.

This page organizes those corrections. The purpose is practical: when you read a holographic calculation, you should be able to identify which approximation is being made, which CFT data are being discarded, and what sort of correction would restore them.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A hierarchy of approximations from exact CFT to quantum string theory, classical supergravity, and the two-derivative Einstein sector.](/figures/course/stringy-quantum-corrections.svg)

<figcaption>

Correction hierarchy in AdS/CFT. The exact CFT is dual to quantum string theory, not merely to two-derivative Einstein gravity. The classical supergravity limit suppresses both bulk loops and stringy higher-derivative effects.

</figcaption>
</figure>

## The hierarchy of descriptions

For the canonical example,

$$
\mathcal N=4\; SU(N)\;\text{SYM}
\quad\longleftrightarrow\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5,
$$

the exact duality relates the full CFT to the full quantum string theory. The commonly used classical-gravity limit is obtained only after several approximations:

$$
\text{exact CFT}
\leftrightarrow
\text{quantum string theory}
\to
\text{classical string theory}
\to
\text{classical supergravity}
\to
\text{two-derivative Einstein sector}.
$$

Each arrow discards something. Classical string theory discards string loops. Supergravity discards massive string excitations. A five-dimensional Einstein truncation discards many Kaluza–Klein and matter fields. A bottom-up model may discard even more.

The most important parameters are

$$
\lambda = g_{\rm YM}^2N,
\qquad
\frac{L^4}{\alpha'^2}=\lambda,
\qquad
g_s = \frac{\lambda}{4\pi N},
\qquad
\frac{G_5}{L^3}\sim \frac{1}{N^2}.
$$

Thus

$$
\frac{\ell_s^2}{L^2}\sim \lambda^{-1/2},
\qquad
\frac{G_5}{L^3}\sim N^{-2}.
$$

The first ratio controls string-scale curvature corrections. The second controls quantum gravity loops in AdS units.

## Three expansions, not one

There is no single “holographic correction.” There are several different expansions.

### The $1/N$ expansion

Large $N$ suppresses connected correlators and bulk loops. In the bulk effective theory, loop corrections are controlled by powers of Newton's constant in AdS units:

$$
\frac{G_{d+1}}{L^{d-1}} \sim \frac{1}{c_T}.
$$

For $\text{AdS}_5/\text{CFT}_4$ with $\text{SU}(N)$ gauge group, $c_T\sim N^2$, so bulk loop effects are typically of order $1/N^2$ for closed-string observables.

CFT meaning: the large-$N$ factorization approximation is no longer exact. Multi-trace mixing, anomalous dimensions, loop corrections to Witten diagrams, and finite-dimensional trace identities begin to matter.

### The $1/\lambda$ expansion

Large $\lambda$ makes the AdS radius large compared with the string length:

$$
L \gg \ell_s.
$$

Finite $\lambda$ restores stringy corrections. In the CFT, this means that the dimensions of stringy single-trace operators are not infinitely heavy. The rough scale is

$$
\Delta_{\rm string} \sim \frac{L}{\ell_s} \sim \lambda^{1/4}.
$$

When $\lambda$ is large, this tower is heavy and can be integrated out. When $\lambda$ is not large, the tower is not decoupled, and a low-derivative bulk gravity action is not enough.

### Nonperturbative corrections

Even the combined expansions in $1/N$ and $1/\lambda$ miss effects that are invisible order by order. Examples include D-instanton effects, brane nucleation effects, finite-spectrum discreteness, and effects of order $e^{-S_{\rm BH}}$ in black-hole physics.

These effects are often negligible for local correlators at finite time, but they can be decisive for fine-grained questions such as black-hole information.

## The effective action viewpoint

A low-energy bulk action is an expansion in local operators:

$$
S_{\rm eff}
=
\frac{1}{2\kappa_{d+1}^2}
\int d^{d+1}x\sqrt{-g}
\left[
R+\frac{d(d-1)}{L^2}
+\sum_{n\ge 2} L^{2n-2}a_n\mathcal R^n
+\cdots
\right].
$$

Here $\mathcal R^n$ schematically denotes curvature invariants and terms involving matter fields and derivatives. The coefficients $a_n$ encode heavy physics that has been integrated out.

In string theory, the expansion is more structured. In type IIB on $\text{AdS}_5\times S^5$, maximal supersymmetry forbids many low-order corrections, and the leading famous correction to the ten-dimensional effective action is an $\alpha'^3 R^4$-type interaction. Since

$$
\left(\frac{\alpha'}{L^2}\right)^3
\sim
\lambda^{-3/2},
$$

many leading finite-coupling corrections in strongly coupled $\mathcal N=4$ SYM appear at order $\lambda^{-3/2}$.

The phrase “$R^4$ correction” is schematic. The actual supersymmetric completion contains a particular contraction of Weyl tensors and additional terms required by type IIB supersymmetry. In many high-level computations, using only the schematic term is not enough.

## Example: thermal free energy of $\mathcal N=4$ SYM

At infinite coupling and large $N$, the entropy density of strongly coupled $\mathcal N=4$ SYM is

$$
s_{\infty}
=\frac{\pi^2}{2}N^2T^3.
$$

The free-field result is larger by a factor of $4/3$, so

$$
\frac{s_{\infty}}{s_{\rm free}}=\frac34.
$$

The leading stringy correction shifts this ratio upward as the coupling is decreased. In a conventional normalization,

$$
\frac{s}{s_{\rm free}}
=
\frac34
+\frac{45}{32}\zeta(3)\lambda^{-3/2}
+\cdots.
$$

The precise coefficient depends on the observable and normalization, but the lesson is robust: finite-$\lambda$ physics is encoded by higher-derivative string corrections to the black-brane geometry and action.

This is an unusually clean example because the leading correction is known from the type IIB effective action. In less supersymmetric or bottom-up settings, the higher-derivative coefficients are usually not known from first principles.

## Example: shear viscosity corrections

For two-derivative Einstein gravity duals,

$$
\frac{\eta}{s}=\frac{1}{4\pi}.
$$

Finite-coupling corrections modify the bulk graviton dynamics. For strongly coupled $\mathcal N=4$ SYM, the leading type IIB correction gives a positive correction of order $\lambda^{-3/2}$:

$$
\frac{\eta}{s}
=\frac{1}{4\pi}
\left[
1+O(\lambda^{-3/2})
\right].
$$

In more general higher-derivative theories, $\eta/s$ can move away from $1/(4\pi)$ in either direction unless the coefficients are constrained by causality, positivity, or a consistent UV completion. This is why arbitrary higher-derivative gravity models should be treated carefully.

## Bulk loops and one-loop determinants

Bulk quantum loops are the gravitational counterpart of $1/N$ corrections. A tree-level Witten diagram computes the leading connected CFT correlator at large $N$. A one-loop Witten diagram computes a subleading term.

Schematically, for normalized single-trace operators,

$$
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle_{\rm conn}
=
\frac{1}{N^2}\mathcal G_{\rm tree}
+\frac{1}{N^4}\mathcal G_{\text{one-loop}}
+\cdots.
$$

In the bulk, the one-loop term includes sums over fields propagating in AdS. In the boundary CFT, the same term contains subleading corrections to OPE coefficients and anomalous dimensions of multi-trace operators.

For entanglement entropy, the leading RT term is the classical area. The first quantum correction is the bulk entanglement entropy across the RT surface:

$$
S_A
=\frac{\mathrm{Area}(\gamma_A)}{4G_N}
+S_{\rm bulk}(\Sigma_A)
+\cdots.
$$

This is a paradigmatic example of a $1/N$ correction that is conceptually essential.

## Kaluza–Klein towers and internal spaces

A common beginner mistake is to say: “The bulk is five-dimensional gravity.” In the canonical example, the bulk is ten-dimensional type IIB string theory on

$$
\mathrm{AdS}_5\times S^5.
$$

Compactifying on $S^5$ gives infinitely many Kaluza–Klein fields in $\text{AdS}_5$. Their masses are of order $1/L$, not the string scale. Therefore they are not decoupled by taking $\lambda\to\infty$.

Some sectors admit consistent truncations: if the truncated fields are set to zero, the remaining lower-dimensional equations imply the full higher-dimensional equations. But a consistent truncation is not the same as a low-energy decoupling of all omitted fields. It is a special dynamical closure property.

CFT meaning: Kaluza–Klein modes are dual to towers of protected or light single-trace operators, often organized by internal-space symmetries such as $SO(6)_R$ for $S^5$.

## Protected versus unprotected quantities

Supersymmetry can protect some observables. For example, certain BPS operator dimensions and protected correlation functions are fixed or constrained across coupling. Other quantities, such as generic anomalous dimensions, transport coefficients, and thermal free energies, receive corrections.

The rough distinction is:

$$
\text{protected data}
\quad\text{may survive extrapolation in }\lambda,
$$

while

$$
\text{unprotected data}
\quad\text{usually depend on }\lambda\text{ and }N.
$$

This is why AdS/CFT can make exact statements about some quantities but only asymptotic strong-coupling statements about others.

## Higher-derivative gravity and consistency

Suppose one writes a five-dimensional action

$$
S=\frac{1}{16\pi G_5}\int d^5x\sqrt{-g}
\left[
R+\frac{12}{L^2}+\gamma L^2 R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}+\cdots
\right].
$$

This is a legitimate effective-field-theory deformation only when $\gamma$ is small and the omitted terms are controlled. If one treats the higher-derivative theory as exact, extra ghostlike degrees of freedom or causality problems may appear.

In a UV-complete string construction, higher-derivative terms come with an infinite tower of massive states and correlated coefficients. Those correlations are what prevent many pathologies. This is one reason that bottom-up higher-derivative models should be used as controlled EFTs, not arbitrary fundamental theories.

Boundary consistency imposes constraints. Causality, positivity of energy flux, Regge behavior, and crossing symmetry all restrict possible bulk interactions. A local-looking bulk action with arbitrary coefficients need not correspond to a consistent CFT.

## Corrections to black-hole physics

Classical black holes capture the thermodynamic leading term

$$
S_{\rm BH}=\frac{A}{4G_N}.
$$

Stringy and quantum corrections modify this in several ways:

1. Higher-derivative terms modify the entropy functional. The correct entropy is then Wald entropy, or a generalized entropy functional including additional corrections, not simply area divided by $4G_N$.
2. Quantum fields contribute bulk entanglement entropy.
3. One-loop determinants correct the black-hole partition function.
4. Nonperturbative effects affect late-time correlators and fine-grained information.

Thus the corrected entropy has the schematic form

$$
S
=\frac{A}{4G_N}
+S_{\rm Wald/HD}
+S_{\rm bulk\ ent}
+S_{\rm nonpert}
+\cdots.
$$

The leading area term is large, of order $N^2$. The corrections may be smaller in powers of $N$, but they encode important physics.

## Corrections to the mass-dimension relation

At the supergravity level, a bulk field mass determines the boundary scaling dimension through

$$
m^2L^2=\Delta(\Delta-d).
$$

This relation remains true for a field in AdS with a given effective mass, but stringy and quantum corrections can shift the mass, mix fields, or invalidate the truncation to a single field.

For example, an unprotected single-trace operator can have

$$
\Delta(\lambda,N)
=
\Delta_0
+\gamma_0(\lambda)
+\frac{1}{N^2}\gamma_1(\lambda)
+\cdots.
$$

On the bulk side, this corresponds to corrections to the spectrum of string states and quantum corrections to bulk masses.

## Corrections to Witten diagrams

Tree-level Witten diagrams are the leading large-$N$ approximation. Corrections come in layers:

$$
\mathcal A_{\rm CFT}
=
\mathcal A_{\rm sugra,tree}
+\mathcal A_{\alpha'}
+\mathcal A_{\rm loop}
+\mathcal A_{\rm nonpert}
+\cdots.
$$

Here:

- $\mathcal A_{\rm sugra,tree}$ comes from two-derivative supergravity interactions;
- $\mathcal A_{\alpha'}$ comes from higher-derivative stringy terms;
- $\mathcal A_{\rm loop}$ comes from bulk loops;
- $\mathcal A_{\rm nonpert}$ comes from instantons, branes, or finite-spectrum effects.

In Mellin-space language, stringy corrections often show up as higher-degree polynomial contact terms or Regge behavior softened by the full string amplitude. In position space, they correct anomalous dimensions and OPE coefficients of double-trace and higher multi-trace operators.

## Practical recipe for using corrections

When doing a corrected holographic computation, follow this checklist.

### 1. Identify the expansion parameter

Ask whether the correction is controlled by $1/N$, $1/\lambda$, a small flavor ratio $N_f/N_c$, a small higher-derivative coupling, or a small deformation of the state.

### 2. Decide whether the correction is top-down or bottom-up

A top-down correction has coefficients fixed by string/M-theory. A bottom-up correction is a phenomenological parameter. Both can be useful, but they carry different evidentiary weight.

### 3. Include all terms required at the same order

It is often inconsistent to keep one higher-derivative term while dropping others of the same order, unless symmetries or a consistent truncation justify it.

### 4. Correct the variational problem

Higher derivatives and quantum terms can change boundary terms, counterterms, canonical momenta, and entropy functionals. Do not simply plug a corrected metric into an uncorrected formula.

### 5. Translate back to CFT data

The final answer should say what changed in the CFT: a scaling dimension, OPE coefficient, transport coefficient, thermal free energy, central charge, spectral density, or entropy.

## Dictionary checkpoint

| Correction | Bulk description | Boundary meaning |
|---|---|---|
| finite $\lambda$ | $\alpha'$ corrections, massive string modes | stringy single-trace operators become less heavy |
| finite $N$ | bulk loops, quantum gravity | connected correlators and mixing beyond factorization |
| Kaluza–Klein modes | fields from compact internal space | towers of operators charged under internal symmetries |
| higher-derivative terms | local EFT corrections | anomalous dimensions/OPE data of heavy-integrated sectors |
| instantons/branes | nonperturbative string effects | effects invisible in perturbative $1/N$ or $1/\lambda$ expansions |
| one-loop entanglement | bulk entropy across RT/QES surfaces | subleading corrections to boundary entropy |
| finite spectral discreteness | late-time nonperturbative effects | exact CFT unitarity and recurrences |

The main principle is simple: every correction on the bulk side is a statement about CFT data. If one cannot say what CFT data are being changed, the bulk correction has not been fully interpreted.

## Common confusions

### “Finite $N$ and finite $\lambda$ are the same kind of correction.”

They are different. Finite $N$ controls quantum bulk loops. Finite $\lambda$ controls string-scale corrections and the mass of stringy states. A theory can have large $N$ but moderate $\lambda$, or large $\lambda$ but not parametrically large $N$.

### “If $g_s$ is small, gravity is classical.”

Small $g_s$ suppresses string loops, but classical Einstein gravity also requires small curvature in string units, $L\gg \ell_s$. That means large $\lambda$ in the canonical example.

### “A five-dimensional Einstein action is the full dual of $\mathcal N=4$ SYM.”

No. It is a truncation of type IIB string theory on $\mathrm{AdS}_5\times S^5$, valid for certain observables in a certain limit. The full dual contains the internal space, Kaluza–Klein towers, massive strings, branes, and quantum effects.

### “Higher-derivative terms can be chosen arbitrarily.”

Not if the model is meant to have a consistent CFT dual. Causality, positivity, crossing symmetry, and UV completion constrain the coefficients.

### “Protected quantities prove that all strong-coupling results are exact.”

Protection is special. Many quantities used in holographic thermal physics and transport are unprotected and do receive finite-coupling or finite-$N$ corrections.

## Exercises

### Exercise 1: Identify the correction

In AdS$_5$/CFT$_4$, suppose an observable receives a correction proportional to $\lambda^{-3/2}$ at leading large $N$. Is this a finite-$N$ correction or a finite-coupling correction?

<details>
<summary><strong>Solution</strong></summary>

It is a finite-coupling correction. In the canonical type IIB example, the leading famous higher-derivative correction is of order

$$
\left(\frac{\alpha'}{L^2}\right)^3
\sim
\lambda^{-3/2}.
$$

Since the correction is taken at leading large $N$, it is not a bulk loop correction. It is a stringy $\alpha'$ correction.

</details>

### Exercise 2: Why does a large gap help bulk locality?

Explain why sending $\Delta_{\rm string}\sim\lambda^{1/4}$ to infinity helps produce a local bulk effective field theory.

<details>
<summary><strong>Solution</strong></summary>

A local low-energy EFT is valid when heavy states can be integrated out. In AdS/CFT, massive string states correspond to single-trace operators with large scaling dimensions. If

$$
\Delta_{\rm string}\gg 1,
$$

then these operators are heavy compared with the AdS scale. Their effects on low-energy correlators can be expanded in local higher-derivative interactions suppressed by powers of the gap. If the gap is not large, infinitely many stringy states participate, and a local two-derivative bulk action is not a good approximation.

</details>

### Exercise 3: Order of a one-loop Witten diagram

For normalized single-trace operators in a large-$N$ CFT, suppose a connected four-point function has the expansion

$$
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle_{\rm conn}
=
\frac{1}{N^2}\mathcal G_0
+\frac{1}{N^4}\mathcal G_1+
\cdots.
$$

Which term is tree level and which term is one loop in the bulk?

<details>
<summary><strong>Solution</strong></summary>

The leading connected term $\mathcal G_0/N^2$ is computed by tree-level Witten diagrams. The next term $\mathcal G_1/N^4$ is computed by one-loop Witten diagrams and related subleading effects. This follows from the identification of $1/N$ with the bulk interaction/loop expansion.

</details>

### Exercise 4: Why area is not always enough

Why is the Bekenstein–Hawking formula $A/(4G_N)$ not the complete entropy formula once higher-derivative and quantum corrections are included?

<details>
<summary><strong>Solution</strong></summary>

The formula $A/(4G_N)$ is the entropy of a stationary horizon in two-derivative Einstein gravity. Higher-derivative interactions change the gravitational entropy functional, often to a Wald-like entropy plus additional terms. Quantum bulk fields also contribute entanglement entropy. Therefore the corrected entropy is schematically

$$
S
=\frac{A}{4G_N}+S_{\rm higher\ derivative}+S_{\rm bulk\ entanglement}+\cdots.
$$

The area term remains the leading contribution in many large-$N$ limits, but it is not the full answer.

</details>

## Further reading

- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- S. S. Gubser, I. R. Klebanov, and A. A. Tseytlin, [Coupling Constant Dependence in the Thermodynamics of $\mathcal N=4$ Supersymmetric Yang–Mills Theory](https://arxiv.org/abs/hep-th/9805156).
- T. Faulkner, A. Lewkowycz, and J. Maldacena, [Quantum Corrections to Holographic Entanglement Entropy](https://arxiv.org/abs/1307.2892).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151).
- A. Buchel, J. T. Liu, and A. O. Starinets, [Coupling Constant Dependence of the Shear Viscosity in $\mathcal N=4$ Supersymmetric Yang–Mills Theory](https://arxiv.org/abs/hep-th/0406264).
- M. B. Green, M. Gutperle, and P. Vanhove, [One Loop in Eleven Dimensions](https://arxiv.org/abs/hep-th/9706175).
