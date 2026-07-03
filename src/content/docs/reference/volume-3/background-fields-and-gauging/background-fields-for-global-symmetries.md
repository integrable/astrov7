---
title: "Background Fields for Global Symmetries"
description: "Explains how ordinary global symmetries are coupled to nondynamical background gauge fields, and how background gauge invariance packages Ward identities, contact terms, and anomaly tests."
sidebar:
  label: "Backgrounds for Global Symmetries"
  order: 2
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. II Ch. 16 on external fields; Srednicki §§22, 67–68, 76–78 on currents, Ward identities, anomalies, and background-field gauge; Gaiotto–Kapustin–Seiberg–Willett on generalized global symmetries."
topics:
  - background gauge fields
  - global symmetries
  - Ward identities
  - current sources
  - contact terms
  - anomalies
  - global form
canonicalTopics:
  - background-gauge-field
  - background-gauge-invariance
  - global-symmetry-background
  - covariant-ward-identity
  - obstruction-to-gauging
researchStatus:
  established:
    - "Coupling continuous global symmetries to nondynamical background gauge fields is the standard source-based formulation of current Ward identities and response functions."
  active:
    - "The same logic is actively generalized through higher-form backgrounds, higher-group symmetry, finite-group backgrounds, non-invertible defects, and symmetry TFT."
---

## Summary

A continuous internal global symmetry can be probed by a **background gauge field**. For a global symmetry group $G$ with current $j_a^\mu$, the source is a nondynamical connection

$$
A=A_\mu^a T_a\,dx^\mu,
$$

and the source-coupled theory has the schematic form

$$
Z[A]=\int \mathcal D\phi\,e^{iS[\phi;A]},
\qquad
S[\phi;A]=S[\phi;0]+\int d^dx\,A_\mu^a j_a^\mu+O(A^2).
$$

The point of the $O(A^2)$ terms is not perturbative fussiness. They are often forced by **background gauge invariance**: the statement that the same physical source configuration can be described in different local frames on the symmetry bundle.

<figure class="doc-figure" style="--figure-width: 49rem;">

![A diagram showing the path from a global symmetry to a background connection, a source functional, background gauge covariance, Ward identities, and anomaly tests.](/figures/symmetry-anomalies-topology/global-symmetry-background-field.svg)

<figcaption>

A continuous global symmetry is probed by a nondynamical background connection $A$. Background gauge covariance is the source-functional form of the Ward identities. If this covariance fails in a way no local counterterm can remove, the symmetry has an anomaly.

</figcaption>
</figure>

Background gauge fields are the cleanest way to see three facts at once:

$$
\text{currents generate Ward identities},
\qquad
\text{contact terms are source dependence},
\qquad
\text{anomalies obstruct gauging}.
$$

The background field is not integrated over on this page. It is a probe. Gauging the symmetry is a later operation that sums or integrates over these background fields.

## Prerequisites

Read [Sources and Background Fields](/symmetry-anomalies-topology/background-fields-and-gauging/sources-and-background-fields/) first. You should also know [Noether Currents](/symmetry-anomalies-topology/noether-currents-ward-identities/noether-currents/), [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/), and [Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/).

This page assumes ordinary zero-form internal symmetries. Higher-form backgrounds, finite-group flat bundles, and non-invertible defects appear later.

## Core idea

A global symmetry with constant parameter $g\in G$ acts on operators and states. To extract local consequences, one temporarily lets the symmetry parameter depend on spacetime and compensates by transforming an external field $A_\mu$. The original physical symmetry has not become a dynamical gauge symmetry. Instead, the source has acquired a redundancy:

$$
(\phi,A_\mu)
\sim
(g\phi,\,gA_\mu g^{-1}-i(\partial_\mu g)g^{-1}).
$$

This redundancy is called **background gauge invariance**. It says that $Z[A]$ is a functional on gauge-equivalence classes of background connections, not on a preferred choice of local frame.

For ordinary current conservation, one can work at $A=0$ and derive

$$
\partial_\mu j_a^\mu=0
$$

inside correlators, up to contact terms. Background fields package the whole tower of these identities into a single statement:

$$
Z[A^g]=Z[A]
$$

when there is no anomaly.

That packaging is not just elegant. It is robust enough to handle curved spacetime, nontrivial bundles, topological response, mixed symmetries, anomaly inflow, and the operation of gauging.

## Setup and conventions

We use mostly-minus Lorentzian signature and the source convention

$$
Z[A]=e^{iW[A]},
\qquad
\frac{\delta W}{\delta A_\mu^a(x)}=\langle j_a^\mu(x)\rangle_A
$$

when the current is defined as the first variation of the full source-coupled action.

For compact Lie groups we take Hermitian generators $T_a$ satisfying

$$
[T_a,T_b]=i f_{ab}{}^c T_c.
$$

A matter field in a representation $R$ transforms as

$$
\phi(x)\mapsto g(x)\phi(x),
\qquad
 g(x)=e^{i\lambda^a(x)T_a}.
$$

The background covariant derivative convention is

$$
D_\mu=\partial_\mu-iA_\mu,
\qquad
A_\mu=A_\mu^aT_a.
$$

Then a finite background gauge transformation is

$$
A_\mu\mapsto A_\mu^g=gA_\mu g^{-1}-i(\partial_\mu g)g^{-1},
$$

and infinitesimally

$$
\delta_\lambda A_\mu=\partial_\mu\lambda+i[\lambda,A_\mu].
$$

Equivalently, in components,

$$
(\delta_\lambda A_\mu)^a=\partial_\mu\lambda^a+f_{bc}{}^a A_\mu^b\lambda^c,
$$

with the sign following from the Hermitian-generator convention above and the ordering $A_\mu^b\lambda^c$.

:::note[Convention-sensitive source note]
Some authors use anti-Hermitian Lie-algebra generators, mostly-plus metric, Euclidean $Z=e^{-W}$, or the opposite sign in $D_\mu=\partial_\mu\pm iA_\mu$. The invariant statement is that $A$ is a connection, $D_\mu\phi$ transforms covariantly, and the current is the first variation of the chosen source-coupled action.
:::

## From a global symmetry to a background connection

At $A=0$, a global internal symmetry is generated by charges $Q_a$ acting on local operators as

$$
i[Q_a,\mathcal O_i(x)]=\delta_a\mathcal O_i(x).
$$

For a continuous symmetry, Noether's theorem gives currents $j_a^\mu$ whose time components integrate to these charges,

$$
Q_a=\int_\Sigma d^{d-1}\mathbf x\,j_a^0.
$$

The background-field upgrade asks for a family of theories $Z[A]$ with three properties.

First, at zero background it returns the original theory:

$$
Z[0]=Z.
$$

Second, the first variation inserts the current:

$$
\left.\frac{\delta W[A]}{\delta A_\mu^a(x)}\right|_{A=0}
=\langle j_a^\mu(x)\rangle.
$$

Third, the full functional is invariant, or anomalously covariant, under background gauge transformations.

For a Lagrangian theory this often begins with the replacement

$$
\partial_\mu\longrightarrow D_\mu=\partial_\mu-iA_\mu.
$$

For a general QFT, especially one without a useful Lagrangian, the better definition is more abstract: $Z[A]$ is the partition function or correlation functional of the theory in a background $G$ connection. This is the modern viewpoint because dual theories can have very different microscopic fields but the same response to background symmetry fields.

## The abelian example

Let a complex scalar have a global $U(1)$ symmetry

$$
\phi\mapsto e^{iq\alpha}\phi.
$$

Introduce a background $U(1)$ field by

$$
D_\mu\phi=(\partial_\mu-iqA_\mu)\phi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

For the kinetic term,

$$
(D_\mu\phi)^*D^\mu\phi
=\partial_\mu\phi^*\partial^\mu\phi
+A_\mu j^\mu+q^2A_\mu A^\mu|\phi|^2,
$$

where

$$
j^\mu=iq\left(\phi^*\partial^\mu\phi-(\partial^\mu\phi^*)\phi\right).
$$

The linear term identifies the current. The quadratic term is the first warning that coupling to a background field is not always just "add $A_\mu j^\mu$." The source-coupled action must transform correctly under local background transformations, and that can require nonlinear terms in the source.

For a Dirac fermion with the same convention,

$$
\mathcal L[\psi;A]
=\bar\psi(i\gamma^\mu D_\mu-m)\psi
=\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
+A_\mu j^\mu,
$$

with

$$
j^\mu=q\bar\psi\gamma^\mu\psi.
$$

In this case the coupling is linear in $A_\mu$ because the Dirac kinetic term is first order.

## The nonabelian example

Let the theory have a global $G$ symmetry and let matter fields transform in a representation $R$. With

$$
D_\mu=\partial_\mu-iA_\mu^aT_a,
$$

the kinetic terms are built from $D_\mu\phi$ or $D_\mu\psi$. For fermions,

$$
\mathcal L[\psi;A]
=\bar\psi(i\gamma^\mu D_\mu-m)\psi
=\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
+A_\mu^a\bar\psi\gamma^\mu T_a\psi.
$$

Thus

$$
j_a^\mu=\bar\psi\gamma^\mu T_a\psi.
$$

For scalar matter, $A^2$ terms again appear. These terms are not optional counterterms; they are part of the minimal background-covariant coupling.

Nonabelian background gauge invariance says

$$
W[A^g]=W[A]
$$

if the symmetry is nonanomalous. Differentiating this statement once gives the covariant conservation of the current one-point function in a background:

$$
(D_\mu\langle j^\mu\rangle_A)_a=0,
$$

when no other charged sources are present.

Differentiating again produces current-current Ward identities, including contact terms. Those contact terms remember the $A$ dependence of the current itself.

## Ward identities from background gauge covariance

Let $J_I$ be sources for possibly charged local operators $\mathcal O^I$. The full source functional is

$$
W[A,J].
$$

Under an infinitesimal background transformation,

$$
0=\delta_\lambda W
=\int d^dx\,
\frac{\delta W}{\delta A_\mu^a}(\delta_\lambda A_\mu)^a
+\int d^dx\,
\frac{\delta W}{\delta J_I}\delta_\lambda J_I
$$

for a nonanomalous symmetry.

This compact equation is the source version of the Ward identity. If all charged operator sources are set to zero, it reduces to the covariant current-conservation equation above. If one differentiates with respect to charged sources and then sets the sources to zero, one obtains the familiar contact-term Ward identity,

$$
\partial_\mu\langle j_a^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=
-\sum_{k=1}^n\delta^{(d)}(x-x_k)
\langle\mathcal O_1(x_1)\cdots\delta_a\mathcal O_k(x_k)\cdots\mathcal O_n(x_n)\rangle,
$$

up to the overall factors of $i$ fixed by the operator-variation convention.

:::note[Why the source identity is safer]
A Ward identity written directly inside correlators can hide contact terms and sign conventions. The background-field identity $\delta W[A,J]=0$ keeps all contact terms local and systematic: they arise by differentiating a single source-covariance equation.
:::

## Background fields and twisted boundary conditions

A background connection is not only a local probe. It can carry global information.

On a Euclidean thermal circle of circumference $\beta$, a constant background $A_\tau$ for a $U(1)$ symmetry gives a holonomy

$$
U=\exp\left(iq\oint A\right).
$$

Equivalently, it weights the thermal trace by a symmetry transformation:

$$
Z(\beta,\theta)=\operatorname{Tr}_{\mathcal H}
\left(e^{-\beta H}e^{i\theta Q}\right).
$$

This is a background-field way to impose a twist around the time circle. A spatial holonomy similarly imposes twisted spatial boundary conditions. Flat backgrounds can therefore detect charge sectors even when the local field strength vanishes.

For nonabelian $G$, the holonomy is path ordered:

$$
U(C)=\operatorname{P}\exp\left(i\oint_C A\right),
$$

and only its conjugacy class is gauge invariant for a closed loop in a trivial bundle. On general manifolds, one must also specify the topology of the $G$ bundle.

This is the first place where the **global form** of the symmetry matters. A theory with Lie algebra $\mathfrak{su}(N)$ may have symmetry group $SU(N)$, $PSU(N)=SU(N)/\mathbb Z_N$, or a related quotient depending on the actual charged operators. These choices admit different background bundles.

## Contact terms and counterterms

The functional $W[A]$ is not unique. One may add local counterterms built only from the background fields:

$$
W[A]\longrightarrow W[A]+S_{\text{local}}[A].
$$

Such terms shift contact terms in current correlators and can shift response coefficients. This is not a bug. It is the background-field version of scheme dependence.

For example, in three dimensions a background Chern–Simons counterterm has the form

$$
S_{\text{CS}}[A]
=\frac{k}{4\pi}\int \operatorname{tr}
\left(A\wedge dA-\frac{2i}{3}A\wedge A\wedge A\right)
$$

in the Hermitian-generator convention used here. Its coefficient is quantized on appropriate backgrounds. Changing $k$ changes local current contact terms and topological response.

In four dimensions, background theta-like terms and mixed counterterms can similarly encode response to external symmetry fields.

The important separation is:

$$
\text{removable by local counterterm}
\quad\neq\quad
\text{anomaly}.
$$

An anomaly is a failure of background gauge invariance that no allowed local counterterm can remove.

## The anomaly test

A global symmetry is nonanomalous if $Z[A]$ can be defined consistently on all allowed background fields and is invariant under background gauge transformations. If instead

$$
Z[A^g]=Z[A]e^{i\mathcal A[g,A]},
$$

and the phase $\mathcal A[g,A]$ cannot be removed by a local counterterm, the symmetry has an anomaly.

For a symmetry that one wants to keep global, this can be perfectly consistent. The anomaly becomes powerful information: it constrains RG flow, boundary states, gapped phases, and dual descriptions. For a symmetry one wants to gauge, it is fatal unless additional degrees of freedom or anomaly inflow cancel it.

This is why background fields are the natural language of 't Hooft anomalies. They do not merely ask whether $\partial_\mu j^\mu=0$ at $A=0$. They ask whether the theory can be placed in arbitrary background symmetry fields without contradiction.

## Finite and discrete symmetries preview

A discrete global symmetry has no Noether current and therefore no infinitesimal current source $A_\mu j^\mu$. Still, it has background fields.

For a finite group $G$, a background field is a flat $G$ bundle. On a lattice, this can be represented by group elements on links with flatness constraints around plaquettes. In continuum language, it is topological data specifying how fields are glued across patches.

The continuous and finite cases share the same conceptual pattern:

$$
\text{global symmetry}
\longrightarrow
\text{background symmetry field}
\longrightarrow
\text{Ward identities or twisted sectors}
\longrightarrow
\text{possible gauging or anomaly obstruction}.
$$

The finite case will return in the gauging finite symmetries preview and in low-dimensional orbifold technology.

## Common pitfalls

**Confusing background gauge invariance with a new local physical symmetry.** The local transformation of $A_\mu$ is a redundancy in the source description. The original theory still has a global symmetry at $A=0$.

**Keeping only the linear current coupling.** The expression $\int A_\mu j^\mu$ identifies the current, but it may not define a background-gauge-invariant theory away from infinitesimal $A$. Scalar matter already requires $A^2$ terms.

**Ignoring charged sources.** Ward identities for current correlators alone are not the whole story. Once sources for charged operators are present, the source transformations produce the contact terms that tell currents how to act on operators.

**Treating flat backgrounds as trivial.** A flat connection can have nontrivial holonomy, and a finite-group background is often entirely flat data. Flat does not mean physically invisible.

**Assuming the Lie algebra determines all backgrounds.** The Lie algebra controls local transformations. The actual allowed bundles depend on the global symmetry group and on the spectrum of genuine charged operators.

**Calling every source dependence an anomaly.** Many local variations are removable by counterterms or are just contact-term scheme choices. An anomaly is the nonremovable part.

## Relations to other pages

- [Sources and Background Fields](/symmetry-anomalies-topology/background-fields-and-gauging/sources-and-background-fields/) introduces the general source-functional dictionary used here.
- [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/) derives Ward identities by changing variables in the path integral.
- [Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/) explains how distributional terms appear when insertions collide.
- **Global Form of Symmetry Groups** continues the bundle and quotient-group story later in this chapter.
- **Gauging Global Symmetries** explains what changes when $A$ is summed or integrated over later in this chapter.
- **What Is an Anomaly?** begins the systematic anomaly treatment later in the volume.
- **Higher-Form Symmetries** generalizes $A$ to higher-form background gauge fields later in the volume.

## Research status

The ordinary background-field formalism for continuous global symmetries is established textbook QFT. It is the standard language for current correlators, response functions, Ward identities, and anomalies.

The active frontier is not the basic formula $\delta W/\delta A=\langle j\rangle$. The frontier is the scope of the word "background": higher-form and higher-group gauge fields, finite symmetry defects, non-invertible symmetry backgrounds, relative QFTs, symmetry TFT, and precise global definitions on arbitrary manifolds.

## Exercises

### Exercise 1: Current from a background field

For a complex scalar with

$$
\mathcal L=(D_\mu\phi)^*D^\mu\phi-m^2|\phi|^2,
\qquad
D_\mu=\partial_\mu-iqA_\mu,
$$

show that

$$
\left.\frac{\delta S}{\delta A_\mu(x)}\right|_{A=0}
=iq\left(\phi^*\partial^\mu\phi-(\partial^\mu\phi^*)\phi\right).
$$

<details><summary><strong>Solution</strong></summary>

Expand

$$
(D_\mu\phi)^*D^\mu\phi
=(\partial_\mu\phi^*+iqA_\mu\phi^*)
(\partial^\mu\phi-iqA^\mu\phi).
$$

The terms linear in $A$ are

$$
iqA_\mu\phi^*\partial^\mu\phi
-iqA^\mu(\partial_\mu\phi^*)\phi.
$$

Relabel the index on the second term to write the linear coupling as

$$
A_\mu iq\left(\phi^*\partial^\mu\phi-(\partial^\mu\phi^*)\phi\right).
$$

Therefore the first variation at $A=0$ gives the stated current.

</details>

### Exercise 2: Ward identity from source covariance

Assume $W[A]$ is invariant under the abelian background transformation $A_\mu\mapsto A_\mu+\partial_\mu\alpha$. Show that

$$
\partial_\mu\langle j^\mu(x)\rangle_A=0
$$

when there are no other charged sources and boundary terms vanish.

<details><summary><strong>Solution</strong></summary>

Invariance gives

$$
0=\delta_\alpha W[A]
=\int d^dx\,\frac{\delta W}{\delta A_\mu(x)}\partial_\mu\alpha(x).
$$

Using

$$
\frac{\delta W}{\delta A_\mu(x)}=\langle j^\mu(x)\rangle_A
$$

and integrating by parts,

$$
0=-\int d^dx\,\alpha(x)\partial_\mu\langle j^\mu(x)\rangle_A.
$$

Since $\alpha(x)$ is arbitrary, the integrand vanishes as a distribution.

</details>

### Exercise 3: Holonomy as a twist

A quantum system has Hamiltonian $H$ and conserved charge $Q$. Explain why

$$
Z(\beta,\theta)=\operatorname{Tr}(e^{-\beta H}e^{i\theta Q})
$$

can be interpreted as a thermal partition function with a $U(1)$ background holonomy around the Euclidean time circle.

<details><summary><strong>Solution</strong></summary>

The insertion $e^{i\theta Q}$ implements a global $U(1)$ transformation after Euclidean time evolution by $\beta$. In a path-integral representation, this means fields are glued around the thermal circle by the symmetry transformation

$$
\phi(\tau+\beta)=e^{iq\theta}\phi(\tau)
$$

for a field of charge $q$. A flat background connection with

$$
\oint_{S^1_\beta}A=\theta
$$

produces exactly this holonomy. Thus the trace with $e^{i\theta Q}$ is the partition function in a flat but globally nontrivial background.

</details>

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 16. External-field methods, effective actions, and symmetry constraints.
- Mark Srednicki, *Quantum Field Theory*, especially §§22, 67–68, and 76–78. Continuous symmetries, Ward identities, anomalies, and background-field methods.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters 14, 30, and 34. Source functionals, Ward–Takahashi identities, anomalies, and background gauge fields.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” 2015. A modern source for the statement that global symmetries, including ordinary $q=0$ symmetries, couple to classical background fields and can be gauged by summing over them.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapter 4. Symmetry, spurions, nonlinear realization, and anomaly matching in effective field theory.

## Version history

- **2026-06-17:** Initial polished page on background fields for ordinary global symmetries.
