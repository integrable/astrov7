---
title: "Minimal Coupling"
description: "Explains minimal coupling as the replacement of ordinary derivatives by gauge-covariant derivatives, with scalar, spinor, non-Abelian, background-field, and EFT caveats."
sidebar:
  label: "Minimal Coupling"
  order: 5
level: Graduate
status: "Polished draft"
source: "Coleman, Secret Symmetry; Srednicki §§58, 61, 69; Weinberg Vol. II §15.1; Schwartz §§8.3, 9, 13, 25; Zee Parts II.6 and IV.5."
topics:
  - minimal coupling
  - gauge currents
  - matter representations
  - scalar QED
  - spinor QED
canonicalTopics:
  - minimal-coupling
  - gauge-matter-coupling
  - covariant-derivative
researchStatus:
  established:
    - "Minimal coupling is the standard lowest-derivative way to couple charged matter to a gauge connection while preserving local gauge covariance."
  active:
    - "Effective field theory systematically adds all nonminimal gauge-invariant operators allowed by symmetries, so minimal coupling is a leading structure rather than the complete possible interaction."
---

## Summary

Minimal coupling is the lowest-derivative way to couple charged matter to a gauge field. In practice it is the replacement

$$
\partial_\mu\longrightarrow D_\mu
$$

inside matter kinetic terms, together with a gauge-field kinetic term built from $F_{\mu\nu}$ when the gauge field is dynamical.

For an Abelian field of charge $q$,

$$
D_\mu=\partial_\mu+iqA_\mu.
$$

For a non-Abelian gauge group,

$$
D_\mu=\partial_\mu+igA_\mu^aT_R^a,
$$

where $T_R^a$ are the generators in the representation $R$ carried by the matter field.

Minimal coupling is compact, but it is not a magic substitution rule. It says:

$$
\text{ordinary comparison of nearby matter fields}
\quad\longrightarrow\quad
\text{comparison using the gauge connection}.
$$

It also says that the leading gauge interactions are tightly controlled by charge and representation theory. A charged scalar automatically gets both one-gauge-boson and two-gauge-boson couplings from $(D_\mu\phi)^\dagger D^\mu\phi$. A Dirac field gets a one-gauge-boson coupling from $\overline\psi i\gamma^\mu D_\mu\psi$. Non-Abelian gauge bosons get self-interactions from the nonlinear field strength in the Yang–Mills kinetic term.

<figure class="doc-figure" style="--figure-width: 43rem;">

![Minimal coupling replaces ordinary derivatives by covariant derivatives and generates the leading gauge interactions.](/figures/gauge-theories-standard-model/minimal-coupling-map.svg)

<figcaption>

Minimal coupling promotes a globally symmetric kinetic term to a locally gauge-covariant one. Expanding the result produces current couplings; for scalar matter it also produces contact terms required by gauge invariance. Nonminimal effective operators can be added separately when allowed by symmetries.

</figcaption>
</figure>

## Prerequisites

You should know [Local Symmetry and Covariant Derivatives](/gauge-theories-standard-model/gauge-principle/local-symmetry-and-covariant-derivatives/) and [Field Strength and Curvature](/gauge-theories-standard-model/gauge-principle/field-strength-and-curvature/). You should also be comfortable with scalar and Dirac kinetic terms, Noether currents for internal symmetries, and basic Lie-group representations.

This page is classical and Lagrangian-level. Quantization, gauge fixing, Ward identities, renormalization, and anomaly cancellation come later.

## Core idea

A free or globally symmetric matter theory uses ordinary derivatives because all internal frames are fixed once and for all. If the internal frame is allowed to vary with position, ordinary derivatives stop transforming covariantly. The gauge field repairs that failure.

Minimal coupling is the instruction to build the matter Lagrangian using the covariant derivative associated with that repair:

$$
\mathcal L_{\mathrm{matter}}(\Phi,\partial\Phi)
\quad\longrightarrow\quad
\mathcal L_{\mathrm{matter}}(\Phi,D\Phi).
$$

If the gauge field is dynamical, one also includes

$$
\mathcal L_{\mathrm{gauge}}
=
-\frac12\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
$$

when $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$.

The word “minimal” means lowest-derivative and connection-based. It does **not** mean “the only gauge-invariant interaction.” Once the symmetries are fixed, effective field theory allows additional gauge-invariant operators, usually suppressed by powers of a high scale.

## Setup and conventions

For a $U(1)$ gauge field,

$$
\psi\mapsto e^{-iq\alpha(x)}\psi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
\qquad
D_\mu=\partial_\mu+iqA_\mu.
$$

For a non-Abelian gauge group,

$$
\psi_R\mapsto U_R^{-1}(x)\psi_R,
\qquad
D_\mu\psi_R
=
\left(\partial_\mu+igA_\mu^aT_R^a\right)\psi_R.
$$

The field strength is

$$
[D_\mu,D_\nu]=igF_{\mu\nu},
$$

with

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

For a field charged under several gauge factors, the full covariant derivative is the sum of the contributions from all factors. In the Standard Model convention used in this volume,

$$
D_\mu
=
\partial_\mu
+ig_sG_\mu^A T_c^A
+igW_\mu^I T_L^I
+ig'YB_\mu,
\qquad
Q=T^3+Y.
$$

Each term acts only if the field carries the corresponding representation or charge.

## From global current to gauge source

Minimal coupling has a useful Noether-current interpretation. Consider an Abelian matter theory invariant under a global transformation

$$
\Phi\mapsto e^{-iq\alpha}\Phi
$$

with constant $\alpha$. If we let $\alpha=\alpha(x)$ vary, the free matter Lagrangian is generally no longer invariant. Its variation takes the form

$$
\delta\mathcal L_0=j^\mu\partial_\mu\alpha
$$

up to terms proportional to the equations of motion or total derivatives, where $j^\mu$ is the Noether current for the global symmetry.

A background gauge field cancels this variation at leading order if we add

$$
\mathcal L_{\mathrm{int}}=-j^\mu A_\mu
$$

and let

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

Then

$$
\delta(-j^\mu A_\mu)=-j^\mu\partial_\mu\alpha
$$

to first order. For spinor QED this is the whole story at the level of the matter kinetic term. For scalar QED, gauge invariance also forces a term quadratic in $A_\mu$. The covariant-derivative expression packages the entire answer at once.

This is the slogan:

$$
\text{gauging a symmetry couples a gauge field to the current of that symmetry}.
$$

The slogan is correct as a first pass, but the covariant derivative is safer than the slogan because it automatically includes the nonlinear terms required by exact local gauge invariance.

## Spinor QED

Let $\psi$ be a Dirac field of charge $q$. The free Lagrangian is

$$
\mathcal L_0
=
\overline\psi(i\gamma^\mu\partial_\mu-m)\psi.
$$

The minimally coupled Lagrangian is

$$
\mathcal L
=
\overline\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu+iqA_\mu.
$$

Expanding,

$$
\begin{aligned}
\mathcal L
&=
\overline\psi(i\gamma^\mu\partial_\mu-m)\psi
+\overline\psi i\gamma^\mu(iqA_\mu)\psi\\
&=
\mathcal L_0
-qA_\mu\overline\psi\gamma^\mu\psi.
\end{aligned}
$$

The Noether current associated with the global $U(1)$ transformation is

$$
j^\mu=q\overline\psi\gamma^\mu\psi,
$$

so the interaction is simply

$$
\mathcal L_{\mathrm{int}}=-j^\mu A_\mu.
$$

For the electron, $q=-e$ with $e>0$, so

$$
D_\mu\psi_e=(\partial_\mu-ieA_\mu)\psi_e,
$$

and the interaction term is

$$
+eA_\mu\overline\psi_e\gamma^\mu\psi_e.
$$

The sign of this intermediate expression is convention-dependent. What matters is that the sign of the charge, the transformation law, and the covariant derivative are used consistently.

## Scalar QED

Let $\phi$ be a complex scalar of charge $q$. The free Lagrangian is

$$
\mathcal L_0
=
\partial_\mu\phi^\dagger\partial^\mu\phi
-m^2\phi^\dagger\phi.
$$

Minimal coupling gives

$$
\mathcal L
=
(D_\mu\phi)^\dagger D^\mu\phi
-m^2\phi^\dagger\phi,
\qquad
D_\mu=\partial_\mu+iqA_\mu.
$$

Because

$$
(D_\mu\phi)^\dagger
=
\partial_\mu\phi^\dagger-iqA_\mu\phi^\dagger,
$$

the kinetic term expands to

$$
\begin{aligned}
(D_\mu\phi)^\dagger D^\mu\phi
&=
\partial_\mu\phi^\dagger\partial^\mu\phi
+iqA^\mu\phi\partial_\mu\phi^\dagger
-iqA_\mu\phi^\dagger\partial^\mu\phi\\
&\quad
+q^2A_\mu A^\mu\phi^\dagger\phi.
\end{aligned}
$$

The scalar Noether current is

$$
j^\mu
=
iq\left(\phi^\dagger\partial^\mu\phi-(\partial^\mu\phi^\dagger)\phi\right).
$$

The terms linear in $A_\mu$ combine into

$$
-j^\mu A_\mu.
$$

The final term,

$$
q^2A_\mu A^\mu\phi^\dagger\phi,
$$

is the scalar contact or seagull term. It is not optional. It is required by the exact local gauge invariance of $(D_\mu\phi)^\dagger D^\mu\phi$.

This difference between scalar and spinor QED is a useful diagnostic. Spinor minimal coupling is linear in $A_\mu$ because the Dirac kinetic term is first order in derivatives. Scalar minimal coupling contains a quadratic gauge-field term because the scalar kinetic term is second order in derivatives.

## Non-Abelian matter coupling

For a Dirac field in representation $R$ of a non-Abelian group,

$$
D_\mu\psi_R
=
(\partial_\mu+igA_\mu^aT_R^a)\psi_R,
$$

and

$$
\mathcal L_\psi
=
\overline\psi_R(i\gamma^\mu D_\mu-m)\psi_R.
$$

Expanding gives

$$
\mathcal L_\psi
=
\overline\psi_R(i\gamma^\mu\partial_\mu-m)\psi_R
-gA_\mu^a\,\overline\psi_R\gamma^\mu T_R^a\psi_R.
$$

The current coupled to the gauge field is

$$
J^{a\mu}
=
\overline\psi_R\gamma^\mu T_R^a\psi_R,
$$

so

$$
\mathcal L_{\mathrm{int}}
=
-gA_\mu^aJ^{a\mu}.
$$

For a non-Abelian scalar,

$$
\mathcal L_\phi
=
(D_\mu\phi_R)^\dagger D^\mu\phi_R
-V(\phi_R),
$$

with

$$
D_\mu\phi_R
=
(\partial_\mu+igA_\mu^aT_R^a)\phi_R.
$$

Expanding again produces linear current couplings and quadratic gauge-field contact terms. The difference from the Abelian case is that the matrices $T_R^a$ need not commute.

A subtle but important point: the non-Abelian current $J^{a\mu}$ is not by itself a gauge-invariant observable. It transforms in the adjoint representation. The equation of motion for a dynamical Yang–Mills field takes the schematic covariant form

$$
D_\mu F^{\mu\nu}=gJ^\nu,
$$

not the ordinary conservation equation $\partial_\mu J^\mu=0$ for each adjoint component. Gauge covariance replaces naive component-by-component conservation.

## Gauge fields can be background or dynamical

Minimal coupling does not require the gauge field to be dynamical. One can couple a QFT to a nondynamical background gauge field to probe its current, derive Ward identities, define response functions, or ask whether a global symmetry can be gauged.

In that case $A_\mu$ transforms as a connection, but we do not integrate over it in the path integral. It is an external source.

A dynamical gauge theory goes further. It gives $A_\mu$ its own kinetic term and treats gauge-related $A_\mu$ configurations as redundant descriptions of the same physical field configuration. In Lorentzian signature,

$$
\mathcal L
=
\mathcal L_{\mathrm{matter}}(\Phi,D\Phi)
-\frac12\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
$$

is the prototype.

For non-Abelian gauge theory, the gauge kinetic term itself contains interactions because $F_{\mu\nu}$ contains $ig[A_\mu,A_\nu]$. Thus even “pure” Yang–Mills theory has cubic and quartic gauge-boson vertices.

## Minimal coupling in product gauge groups

Suppose a field transforms under several gauge factors. Then minimal coupling adds the corresponding connections.

For example, a Standard Model quark doublet $Q_L=(u_L,d_L)^T$ transforms as

$$
Q_L:\quad (\mathbf 3,\mathbf 2)_{1/6}.
$$

Its covariant derivative is

$$
D_\mu Q_L
=
\left(
\partial_\mu
+ig_sG_\mu^A T_{\mathbf 3}^A
+igW_\mu^I\frac{\tau^I}{2}
+ig'\frac16 B_\mu
\right)Q_L.
$$

The same compact formula says many things at once:

- gluons mix color components but not weak-isospin components;
- $W_\mu^1$ and $W_\mu^2$ mix the up and down entries in the weak doublet;
- $B_\mu$ couples in proportion to hypercharge;
- if a field is a singlet under one factor, that factor contributes nothing.

For a right-handed charged lepton $e_R$,

$$
e_R:\quad(\mathbf 1,\mathbf 1)_{-1},
$$

so

$$
D_\mu e_R=(\partial_\mu-ig'B_\mu)e_R.
$$

The phrase “minimal coupling” in the Standard Model is largely the statement that all gauge interactions follow from the representation table and the single covariant derivative.

## Minimal versus nonminimal

Gauge invariance permits many interactions that are not produced by the replacement $\partial_\mu\to D_\mu$ in the lowest-derivative kinetic term. These are called nonminimal couplings.

Examples include Pauli or dipole-type operators such as

$$
\frac{c}{\Lambda}\overline\psi\sigma^{\mu\nu}\psi F_{\mu\nu},
$$

or, in a non-Abelian theory,

$$
\frac{c}{\Lambda}\overline\psi\sigma^{\mu\nu}T^a\psi F_{\mu\nu}^a,
$$

when the representation contractions are gauge invariant. Scalar examples include

$$
\frac{c}{\Lambda^2}(\phi^\dagger\phi)F_{\mu\nu}F^{\mu\nu}.
$$

These terms are not forbidden by gauge symmetry. They are nonminimal because they involve the field strength directly, contain more derivatives or higher mass dimension, and are naturally organized as effective field theory corrections.

This distinction matters. Minimal coupling gives the leading renormalizable gauge interaction for many familiar theories, but it is not a law saying nature cannot contain higher-dimension gauge-invariant interactions.

## Charge normalization and the meaning of coupling

In Abelian theory, one can move normalization between the gauge field, the coupling, and the charge labels. This volume writes

$$
D_\mu=\partial_\mu+iqA_\mu.
$$

For QED it is common to write

$$
q=eQ,
$$

where $e>0$ is the proton-charge magnitude and $Q$ is a dimensionless charge. Then

$$
D_\mu=\partial_\mu+ieQA_\mu.
$$

For non-Abelian simple gauge factors, the coupling $g$ is common to all fields charged under that factor, while the representation matrices $T_R^a$ determine how strongly each state responds to each generator. The overall normalization of $T^a$ and $g$ must be fixed together. With

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}
$$

in the fundamental representation of $SU(N)$, the usual QCD and electroweak couplings have their standard normalization.

A gauge singlet has $T_R^a=0$ for that gauge factor. Minimal coupling then reduces to the ordinary derivative for that factor.

## Common pitfalls

**Thinking minimal coupling means only $-j^\mu A_\mu$.** That is true for a Dirac kinetic term, but scalar QED also has the $q^2A_\mu A^\mu\phi^\dagger\phi$ seagull term. The covariant derivative knows about both.

**Forgetting the representation.** The symbol $D_\mu=\partial_\mu+igA_\mu^aT_R^a$ is incomplete until the representation $R$ is specified.

**Confusing background gauging with dynamical gauging.** A background gauge field probes a current. A dynamical gauge field is integrated over or quantized and introduces gauge redundancy into the physical configuration space.

**Assuming minimal coupling is the most general coupling.** Gauge-invariant Pauli terms, dipole operators, polarizabilities, and higher-derivative operators are nonminimal but allowed in effective field theory.

**Changing charge signs by changing the derivative convention.** In this volume the Abelian convention is $D_\mu=\partial_\mu+iqA_\mu$. The electron has $q=-e$. Do not flip the derivative convention just because a charge is negative.

**Calling the non-Abelian current gauge invariant.** The adjoint current $J^{a\mu}$ transforms covariantly. Gauge-invariant observables require fully contracted combinations or dressings.

## Relations to other pages

- [Local Symmetry and Covariant Derivatives](/gauge-theories-standard-model/gauge-principle/local-symmetry-and-covariant-derivatives/) explains why $\partial_\mu$ must be replaced by $D_\mu$ under local internal frame changes.
- [Field Strength and Curvature](/gauge-theories-standard-model/gauge-principle/field-strength-and-curvature/) defines the gauge kinetic term through $F_{\mu\nu}$.
- The next page on matter representations explains how charges, color, weak isospin, hypercharge, and conjugate representations determine the matrices inside $D_\mu$.
- Later QED, Yang–Mills, QCD, and electroweak pages expand these compact Lagrangians into propagators, vertices, Ward identities, and physical processes.

## Research status

Minimal coupling is established classical and perturbative QFT machinery. It is the basis of QED, Yang–Mills theory, QCD, electroweak theory, and the gauge part of the Standard Model.

The active and subtle questions begin when we ask which global symmetries can be gauged quantum mechanically, what global form of the gauge group is intended, which line operators are genuine, how boundary modes transform, and which higher-dimension nonminimal operators should be included in a given effective field theory.

## Exercises

### Exercise 1: Dirac current coupling

Let

$$
\mathcal L=\overline\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu+iqA_\mu.
$$

Expand the Lagrangian and identify the current $j^\mu$ such that $\mathcal L_{\mathrm{int}}=-j^\mu A_\mu$.

<details>
<summary><strong>Solution</strong></summary>

Expand:

$$
\begin{aligned}
\mathcal L
&=
\overline\psi(i\gamma^\mu\partial_\mu-m)\psi
+\overline\psi i\gamma^\mu(iqA_\mu)\psi\\
&=
\mathcal L_0
-qA_\mu\overline\psi\gamma^\mu\psi.
\end{aligned}
$$

Thus

$$
j^\mu=q\overline\psi\gamma^\mu\psi,
$$

and

$$
\mathcal L_{\mathrm{int}}=-j^\mu A_\mu.
$$

</details>

### Exercise 2: Scalar seagull term

For scalar QED with

$$
D_\mu=\partial_\mu+iqA_\mu,
$$

expand $(D_\mu\phi)^\dagger D^\mu\phi$ and identify the terms linear and quadratic in $A_\mu$.

<details>
<summary><strong>Solution</strong></summary>

Since

$$
D_\mu\phi=\partial_\mu\phi+iqA_\mu\phi,
\qquad
(D_\mu\phi)^\dagger=\partial_\mu\phi^\dagger-iqA_\mu\phi^\dagger,
$$

we find

$$
\begin{aligned}
(D_\mu\phi)^\dagger D^\mu\phi
&=
\partial_\mu\phi^\dagger\partial^\mu\phi
+iqA^\mu\phi\partial_\mu\phi^\dagger
-iqA_\mu\phi^\dagger\partial^\mu\phi\\
&\quad
+q^2A_\mu A^\mu\phi^\dagger\phi.
\end{aligned}
$$

The linear terms combine as $-j^\mu A_\mu$ with

$$
j^\mu=iq\left(\phi^\dagger\partial^\mu\phi-(\partial^\mu\phi^\dagger)\phi\right).
$$

The quadratic term is

$$
q^2A_\mu A^\mu\phi^\dagger\phi.
$$

</details>

### Exercise 3: Local variation and the current

For the free Dirac Lagrangian

$$
\mathcal L_0=\overline\psi(i\gamma^\mu\partial_\mu-m)\psi,
$$

let

$$
\delta\psi=-iq\alpha(x)\psi,
\qquad
\delta\overline\psi=iq\alpha(x)\overline\psi.
$$

Show that the variation contains $j^\mu\partial_\mu\alpha$ and identify $j^\mu$.

<details>
<summary><strong>Solution</strong></summary>

The mass term and the terms proportional to $\alpha$ cancel because the transformation is a symmetry for constant $\alpha$. The only new term comes when the derivative hits $\alpha(x)$:

$$
\delta(\partial_\mu\psi)
=
-iq(\partial_\mu\alpha)\psi-iq\alpha\partial_\mu\psi.
$$

Thus

$$
\delta\mathcal L_0
=
\overline\psi i\gamma^\mu[-iq(\partial_\mu\alpha)\psi]
=
q\overline\psi\gamma^\mu\psi\,\partial_\mu\alpha.
$$

Therefore

$$
j^\mu=q\overline\psi\gamma^\mu\psi.
$$

</details>

### Exercise 4: Standard Model covariant derivative for a lepton doublet

Using $Q=T^3+Y$, the lepton doublet $L_L=(\nu_L,e_L)^T$ has $Y=-1/2$. Write its electroweak covariant derivative before symmetry breaking.

<details>
<summary><strong>Solution</strong></summary>

The lepton doublet is an $SU(2)_L$ doublet and an $SU(3)_c$ singlet. Therefore no gluon term appears. With $T_L^I=\tau^I/2$ and $Y=-1/2$,

$$
D_\mu L_L
=
\left(
\partial_\mu
+igW_\mu^I\frac{\tau^I}{2}
- i\frac{g'}{2}B_\mu
\right)L_L.
$$

The upper component has $T^3=+1/2$, so $Q=+1/2-1/2=0$. The lower component has $T^3=-1/2$, so $Q=-1/2-1/2=-1$.

</details>

### Exercise 5: A nonminimal Pauli term

For Abelian gauge theory, show that

$$
\overline\psi\sigma^{\mu\nu}\psi F_{\mu\nu}
$$

is gauge invariant if $\psi\mapsto e^{-iq\alpha}\psi$ and $F_{\mu\nu}$ is gauge invariant. Why is it not part of minimal coupling?

<details>
<summary><strong>Solution</strong></summary>

Under the gauge transformation,

$$
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
\overline\psi\mapsto \overline\psi e^{iq\alpha}.
$$

Therefore the phases cancel:

$$
\overline\psi\sigma^{\mu\nu}\psi
\mapsto
\overline\psi e^{iq\alpha}\sigma^{\mu\nu}e^{-iq\alpha}\psi
=
\overline\psi\sigma^{\mu\nu}\psi,
$$

because the phase acts on internal $U(1)$ charge and commutes with $\sigma^{\mu\nu}$. Since $F_{\mu\nu}$ is gauge invariant, the full operator is gauge invariant.

It is nonminimal because it couples directly to the field strength, is not generated by the replacement $\partial_\mu\to D_\mu$ in the lowest-derivative Dirac kinetic term, and has higher mass dimension than the minimal current coupling in four spacetime dimensions.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§58, 61, and 69, for spinor QED, scalar QED, and the non-Abelian generalization.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, §§8.3, 9, 13, and 25, for covariant derivatives, scalar QED, spinor QED, and Yang–Mills theory.
- A. Zee, *Quantum Field Theory in a Nutshell*, Parts II.6 and IV.5, for the physical route from gauge invariance to gauge couplings.

### Deeper references

- S. Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for a classic conceptual treatment of gauge fields, minimal coupling, and the Higgs phenomenon.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, §15.1, for a systematic formulation of gauge invariance and matter couplings.
- C. P. Burgess, *Introduction to Effective Field Theory*, for the modern viewpoint that minimal coupling is the leading term in a larger effective expansion.

## Version history

- **2026-06-17:** Initial polished draft for the Gauge Principle and Classical Gauge Theory chapter.
